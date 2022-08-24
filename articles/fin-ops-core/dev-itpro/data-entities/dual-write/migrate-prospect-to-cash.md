---
title: Migrar dados de Cliente potencial ao pagamento à vista do Integrador de Dados para gravação dupla
description: Este artigo descreve como migrar os dados de Cliente potencial ao pagamento à vista do Integrador de Dados para gravação dupla.
author: RamaKrishnamoorthy
ms.date: 02/01/2022
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2020-01-26
ms.openlocfilehash: bbf5a7c2f409003816e2becf1a58ee7d7d5aafb2
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9289070"
---
# <a name="migrate-prospect-to-cash-data-from-data-integrator-to-dual-write"></a>Migrar dados de Cliente potencial ao pagamento à vista do Integrador de Dados para gravação dupla

[!include [banner](../../includes/banner.md)]

A solução Cliente potencial ao pagamento à vista disponível para o Integrador de dados não é compatível com a gravação dupla. O motivo para isso é o índice msdynce_AccountNumber na tabela de contas que veio como parte da solução do Cliente potencial ao pagamento à vista. Se esse índice existir, você não poderá criar o mesmo número de conta de cliente em duas entidades legais diferentes. Você pode optar por iniciar o novo com a gravação dupla, migrando os dados do Cliente potencial ao pagamento à vista do Integrador de dados para gravação dupla ou pode instalar a última versão "dorman" da solução do Cliente potencial ao pagamento à vista. Este artigo abranges as essas duas abordagens.

## <a name="install-the-last-dorman-version-of-the-data-integrator-prospect-to-cash-solution"></a>Instale a última versão "dorman" da solução do Cliente potencial ao pagamento à vista do Integrador de Dados

**Versão 15.0.0.2 da P2C** é considerada a última versão "dorman" da solução do Cliente potencial ao pagamento à vista do Integrador de dados. Você pode fazer download de [FastTrack for Dynamics 365](https://github.com/microsoft/Dynamics-365-FastTrack-Implementation-Assets/tree/master/Dual-write/P2C).

É necessário instalá-lo manualmente. Após a instalação, tudo continua exatamente igual, exceto que o índice msdynce_AccountNumber é removido.

## <a name="steps-to-migrate-prospect-to-cash-data-from-data-integrator-to-dual-write"></a>Etapas para migrar dados do Cliente potencial ao pagamento à vista do Integrador de Dados para gravação dupla

Para migrar os dados de Cliente potencial ao pagamento à vista do Integrador de Dados para gravação dupla, siga estas etapas.

1. Execute os trabalhos do Integrador de Dados de Cliente potencial ao pagamento à vista para executar uma sincronização completa final. Dessa forma, você garantirá que ambos os sistemas (aplicativos de finanças e operações e de engajamento do cliente) têm todos os dados.
2. Para ajudar a impedir possíveis perdas de dados, exporte o Cliente potencial ao pagamento à vista do Microsoft Dynamics 365 Sales para um arquivo Excel ou um arquivo de valores separados por vírgula (CSV). Exportar dados das seguintes entidades:

    - [Conta](#account-table)
    - [Contato](#contact-table)
    - [Fatura](#invoice-table)
    - Produtos da fatura
    - [Ordem](#order-table)
    - [Produtos do pedido](#order-products-table)
    - [Produtos](#products-table)
    - [Cotação](#quote-and-quote-product-tables)
    - [Produtos da cotação](#quote-and-quote-product-tables)

3. Desinstale a solução Cliente potencial ao pagamento à vista do ambiente do Sales. Esta etapa remove as colunas e os dados correspondentes introduzidos pela solução Cliente potencial ao pagamento à vista.
4. Instale a solução de gravação dupla.
5. Crie uma conexão de gravação dupla entre o aplicativo de finanças e operações e o aplicativo de engajamento do cliente para uma ou mais entidades legais.
6. Habilite mapas de tabela de gravação dupla e execute a sincronização inicial dos dados de referência necessários. (Para obter mais informações, consulte [Considerações para sincronização inicial](initial-sync-guidance.md).) Os exemplos de dados necessários incluem grupos de clientes, condições e planos de pagamento. Não habilite mapas de gravação dupla em tabelas que exigem inicialização, como as tabelas de conta, cotação, linha de cotação, ordem e de linha de ordem.
7. No aplicativo Customer Engagement, acesse **Configurações Avançadas \> Configurações do Sistema \> Gerenciamento de Dados \> Regras de detecção de duplicidades** e desabilite todas as regras.
8. Inicialize as tabelas listadas na etapa 2. Para obter instruções, consulte as outras seções deste artigo.
9. Abra o aplicativo de finanças e operações e habilite os mapas de tabela, como os mapas de tabela de contas, cotação, linha de cotação e linha de ordem. Depois, execute a sincronização inicial. (Para obter mais informações, consulte [Considerações para sincronização inicial](initial-sync-guidance.md).) Este processo sincronizará todas as informações adicionais do aplicativo de finanças e operações, como status de processamento, endereços de envio e cobrança, locais e depósitos.

## <a name="account-table"></a>Tabela de contas

1. Na coluna **Empresa**, insira o nome da empresa, como **USMF**.
2. Na coluna **Tipo de Relacionamento**, insira **Cliente** como valor estático. Não convém classificar cada registro de conta como cliente na lógica comercial.
3. Na coluna **ID do Grupo de Clientes**, insira o número do grupo de clientes do aplicativo de finanças e operações. O valor padrão da solução Cliente potencial ao pagamento à vista é **10**.
4. Se você estiver usando a solução Cliente potencial ao pagamento à vista sem qualquer personalização de **Número da Conta**, insira um valor em **Número da Conta** na coluna **Número do Participante**. Se houver personalizações e você não souber o número do participante, extraia essas informações do aplicativo de finanças e operações.

## <a name="contact-table"></a>Tabela de contatos

1. Na coluna **Empresa**, insira o nome da empresa, como **USMF**.
2. Defina as seguintes colunas com base no valor **IsActiveCustomer** no arquivo CSV:

    - Se **IsActiveCustomer** estiver definido como **Sim** no arquivo CSV, defina a coluna **Comercializável** como **Sim**. Na coluna **ID do Grupo de Clientes**, insira o número do grupo de clientes do aplicativo de finanças e operações. O valor padrão da solução Cliente potencial ao pagamento à vista é **10**.
    - Se **IsActiveCustomer** estiver definido como **Não** no arquivo CSV, defina a coluna **Comercializável** como **Não** e defina a coluna **Contato Para** como **Cliente**.

3. Se estiver usando a solução Cliente potencial ao pagamento à vista sem qualquer personalização do **Número de Contato**, defina as seguintes colunas:

    - Migre o número do contato do arquivo CSV (**msdynce\_contactnumber**) para o número do contato na tabela **Contato** (**msdyn\_contactnumber**).
    - Use valores da tabela **Número do Contato** na coluna **Número do Participante**.
    - Use valores da tabela **Número do Contato** na coluna **Número da Conta/ID da Pessoa de Contato**.

## <a name="invoice-table"></a>Tabela de faturas

Como os dados da tabela **Fatura** são projetados para fluir do aplicativo de finanças e operações para o aplicativo de engajamento do cliente, a inicialização não é necessária. Execute a sincronização inicial para migrar todos os dados necessários do aplicativo de finanças e operações para o aplicativo de engajamento do cliente. Para obter mais informações, consulte [Considerações para sincronização inicial](initial-sync-guidance.md).

## <a name="order-table"></a>Tabela de ordens

1. Na coluna **Empresa**, insira o nome da empresa, como **USMF**.
2. Copie o valor da coluna **ID da Ordem** no arquivo CSV para a coluna **Número da Ordem de Venda**.
3. Copie o valor da coluna **Cliente** no arquivo CSV para a coluna **Número do cliente da fatura**.
4. Copie o valor da coluna **País/Região para Entrega** no arquivo CSV para a coluna **País/Região para Entrega**. Exemplos desse valor incluem **EUA** e **Estados Unidos**.
5. Defina a coluna **Data de Recebimento Solicitada**. Se você não estiver usando uma data de recebimento, use as colunas **Data de Entrega Solicitada**, **Data de Cumprimento** e **Data do Envio** no arquivo CSV. Um exemplo desse valor é **2020-03-27T00:00:00Z**.
6. Defina a coluna **Idioma**. Um exemplo desse valor é **en-us**.
7. Defina a coluna **Tipo da Ordem** usando a coluna **Baseado em item**.

## <a name="order-products-table"></a>Tabela de produtos da ordem

- Na coluna **Empresa**, insira o nome da empresa, como **USMF**.

## <a name="products-table"></a>Tabela de produtos

Como os dados da tabela **Produtos** são projetados para fluir do aplicativo de finanças e operações para o aplicativo de engajamento do cliente, a inicialização não é necessária. Execute a sincronização inicial para migrar todos os dados necessários do aplicativo de finanças e operações para o aplicativo de engajamento do cliente. Para obter mais informações, consulte [Considerações para sincronização inicial](initial-sync-guidance.md).

## <a name="quote-and-quote-product-tables"></a>Tabelas de Cotação e Produto da cotação

Para a tabela **Cotação**, siga as instruções na seção [Tabela de ordens](#order-table) anterior neste artigo. Para a tabela **Produto da cotação**, siga as instruções na seção [Tabela de produtos da ordem](#order-products-table).


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]

