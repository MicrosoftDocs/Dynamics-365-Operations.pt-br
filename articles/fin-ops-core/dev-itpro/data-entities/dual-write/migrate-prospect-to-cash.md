---
title: Migrar os dados de Cliente potencial ao pagamento à vista do Integrador de Dados para gravação dupla
description: Este tópico descreve como migrar os dados de Cliente potencial ao pagamento à vista do Integrador de Dados para gravação dupla.
author: RamaKrishnamoorthy
ms.date: 01/04/2021
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2020-01-06
ms.openlocfilehash: d216f1c46aa3362730c126ffc33fefdddddf1853
ms.sourcegitcommit: 259ba130450d8a6d93a65685c22c7eb411982c92
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/24/2021
ms.locfileid: "7416368"
---
# <a name="migrate-prospect-to-cash-data-from-data-integrator-to-dual-write"></a>Migrar os dados de Cliente potencial ao pagamento à vista do Integrador de Dados para gravação dupla

[!include [banner](../../includes/banner.md)]

Para migrar os dados de Cliente potencial ao pagamento à vista do Integrador de Dados para gravação dupla, siga estas etapas.

1. Execute os trabalhos do Integrador de Dados de Cliente potencial ao pagamento à vista para executar uma sincronização completa final. Dessa forma, você garantirá que ambos os sistemas (aplicativos do Finance and Operations e Customer Engagement) tenham todos os dados.
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
5. Crie uma conexão de gravação dupla entre o aplicativo Finance and Operations e o aplicativo Customer Engagement para uma ou mais entidades legais.
6. Habilite mapas de tabela de gravação dupla e execute a sincronização inicial dos dados de referência necessários. (Para obter mais informações, consulte [Considerações para sincronização inicial](initial-sync-guidance.md).) Os exemplos de dados necessários incluem grupos de clientes, condições e planos de pagamento. Não habilite mapas de gravação dupla em tabelas que exigem inicialização, como as tabelas de conta, cotação, linha de cotação, ordem e de linha de ordem.
7. No aplicativo Customer Engagement, acesse **Configurações Avançadas \> Configurações do Sistema \> Gerenciamento de Dados \> Regras de detecção de duplicidades** e desabilite todas as regras.
8. Inicialize as tabelas listadas na etapa 2. Para obter instruções, consulte as outras seções deste tópico.
9. Abra o aplicativo Finance and Operations e habilite os mapas de tabela, como os mapas de tabela de contas, cotação, linha de cotação e linha de ordem. Depois, execute a sincronização inicial. (Para obter mais informações, consulte [Considerações para sincronização inicial](initial-sync-guidance.md).) Este processo sincronizará todas as informações adicionais do aplicativo Finance and Operations, como status de processamento, endereços de envio e cobrança, sites e depósitos.

## <a name="account-table"></a>Tabela de contas

1. Na coluna **Empresa**, insira o nome da empresa, como **USMF**.
2. Na coluna **Tipo de Relacionamento**, insira **Cliente** como valor estático. Não convém classificar cada registro de conta como cliente na lógica comercial.
3. Na coluna **ID do Grupo de Clientes**, insira o número do grupo de clientes do aplicativo Finance and Operations. O valor padrão da solução Cliente potencial ao pagamento à vista é **10**.
4. Se você estiver usando a solução Cliente potencial ao pagamento à vista sem qualquer personalização de **Número da Conta**, insira um valor em **Número da Conta** na coluna **Número do Participante**. Se houver personalizações e não souber o número do participante, extraia essas informações do aplicativo Finance and Operations.

## <a name="contact-table"></a>Tabela de contatos

1. Na coluna **Empresa**, insira o nome da empresa, como **USMF**.
2. Defina as seguintes colunas com base no valor **IsActiveCustomer** no arquivo CSV:

    - Se **IsActiveCustomer** estiver definido como **Sim** no arquivo CSV, defina a coluna **Comercializável** como **Sim**. Na coluna **ID do Grupo de Clientes**, insira o número do grupo de clientes do aplicativo Finance and Operations. O valor padrão da solução Cliente potencial ao pagamento à vista é **10**.
    - Se **IsActiveCustomer** estiver definido como **Não** no arquivo CSV, defina a coluna **Comercializável** como **Não** e defina a coluna **Contato Para** como **Cliente**.

3. Se estiver usando a solução Cliente potencial ao pagamento à vista sem qualquer personalização do **Número de Contato**, defina as seguintes colunas:

    - Migre o número do contato do arquivo CSV (**msdynce\_contactnumber**) para o número do contato na tabela **Contato** (**msdyn\_contactnumber**).
    - Use valores da tabela **Número do Contato** na coluna **Número do Participante**.
    - Use valores da tabela **Número do Contato** na coluna **Número da Conta/ID da Pessoa de Contato**.

## <a name="invoice-table"></a>Tabela de faturas

Como os dados da tabela **Fatura** são projetados para fluir do aplicativo Finance and Operations para o aplicativo Customer Engagement, a inicialização não é necessária. Execute a sincronização inicial para migrar todos os dados necessários do aplicativo Finance and Operations para o aplicativo Customer Engagement. Para obter mais informações, consulte [Considerações para sincronização inicial](initial-sync-guidance.md).

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

Como os dados da tabela **Produtos** são projetados para fluir do aplicativo Finance and Operations para o aplicativo Customer Engagement, a inicialização não é necessária. Execute a sincronização inicial para migrar todos os dados necessários do aplicativo Finance and Operations para o aplicativo Customer Engagement. Para obter mais informações, consulte [Considerações para sincronização inicial](initial-sync-guidance.md).

## <a name="quote-and-quote-product-tables"></a>Tabelas de Cotação e Produto da cotação

Para a tabela **Cotação**, siga as instruções na seção [Tabela de ordens](#order-table) anterior neste tópico. Para a tabela **Produto da cotação**, siga as instruções na seção [Tabela de produtos da ordem](#order-products-table).


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]