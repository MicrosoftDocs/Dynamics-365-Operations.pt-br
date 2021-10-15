---
title: Sincronizar cabeçalhos e linhas da cotação de venda diretamente do Sales para o Supply Chain Management
description: O tópico discute os modelos e as tarefas subjacentes que são usados para sincronizar cabeçalhos e linhas da cotação de venda diretamente do Dynamics 365 Sales para o Dynamics 365 Supply Chain Management.
author: Henrikan
ms.date: 10/25/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: henrikan
ms.dyn365.ops.version: July 2017 update
ms.search.validFrom: 2017-07-8
ms.openlocfilehash: 46584f397e83bc68878ff5ef2848a251912811af
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/29/2021
ms.locfileid: "7566398"
---
# <a name="synchronize-sales-quotation-headers-and-lines-directly-from-sales-to-supply-chain-management"></a>Sincronizar cabeçalhos e linhas da cotação de venda diretamente do Sales para o Supply Chain Management

[!include [banner](../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

O tópico discute os modelos e as tarefas subjacentes que são usados para sincronizar cabeçalhos e linhas da cotação de venda diretamente do Dynamics 365 Sales para o Dynamics 365 Supply Chain Management.

> [!NOTE]
> Antes de usar a solução Prospect to cash, você deve familiarizar-se com a [Integração de dados no Microsoft Dataverse para Aplicativos](/powerapps/administrator/data-integrator).

## <a name="data-flow-in-prospect-to-cash"></a>Fluxo de dados no Prospect to cash

A solução Prospect to cash usa o recurso Integração de dados para sincronizar dados entre as instâncias Supply Chain Management e do Sales. Os modelos de Prospect to cash que estão disponíveis com o recurso Integração de dados permitem o fluxo de dados para contas, contatos, produtos, cotações de venda, ordens de venda e faturas de venda entre o Supply Chain Management e o Sales. A ilustração a seguir mostra como os dados são sincronizados entre o Supply Chain Management e o Sales.

[![Fluxo de dados em Prospect to cash.](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)

## <a name="template-and-tasks"></a>Modelo e tarefas

O seguinte modelo e as tarefas subjacentes são usados para sincronizar cabeçalhos e linhas da cotação de venda diretamente do Sales para o Supply Chain Management:

- **Nome do modelo na Integração de dados:** Cotações de Venda (Sales para Supply Chain Management) – Direto
- **Nomes das tarefas no projeto de Integração de dados:**

    - QuoteHeader
    - QuoteLine

As seguintes tarefas de sincronização são obrigatórias para que a sincronização de cabeçalhos e linhas de cotação de venda possa ocorrer:

- Produtos (Supply Chain Management para Sales) – Direto
- Contas (Sales para Supply Chain Management) – Direto (se usado)
- Contatos para Clientes (Sales para Supply Chain Management) – Direto (se usado)

## <a name="entity-set"></a>Conjunto de entidades

| Vendas        | Gerenciamento da Cadeia de Fornecedores     |
|--------------|----------------------------|
| Cotações       | Cabeçalho de cotação de venda do Dataverse |
| QuoteDetails | Linhas de cotação de venda do Dataverse  |

## <a name="entity-flow"></a>Fluxo de entidades

As cotações de venda são criadas no Sales e sincronizadas para o Supply Chain Management.

As cotações de vendas do Sales são sincronizadas somente se as seguintes condições forem atendidas:

- Todos os produtos de cotação na cotação de vendas são mantidos externamente.
- Após você clicar em **Ativar cotação**, a cotação de venda ficará ativa.

## <a name="prospect-to-cash-solution-for-sales"></a>Solução Prospect to cash para o Sales

O campo **Tem Somente Produtos Mantidos Externamente** foi adicionado à entidade **Cotação** para rastrear consistentemente se a cotação de vendas consiste inteiramente em produtos mantidos externamente. Se uma cotação de venda mantiver somente produtos externamente, os produtos serão mantidos no Supply Chain Management. Esse comportamento ajuda a garantir que você não tente sincronizar linhas da cotação de venda que tenham produtos desconhecidos para o Supply Chain Management.

Todos os produtos de cotação da cotação de venda são atualizados com as informações **Tem Somente Produtos Mantidos Externamente** do cabeçalho de cotação de venda. Essas informações se encontram no campo **A Cotação Tem Somente Produtos Mantidos Externamente** na entidade **QuoteDetails**.

Um desconto pode ser adicionado ao produto de cotação e será sincronizado para o Supply Chain Management. Os campos **Desconto**, **Encargos** e **Imposto** no cabeçalho são controlados por uma configuração no Supply Chain Management. No momento, essa configuração não dá suporte ao mapeamento de integração. No design atual, os campos **Preço**, **Desconto**, **Encargo** e **Imposto** são mantidos e tratados no Supply Chain Management.

No Sales, a solução torna os seguintes campos somente leitura, pois os valores não são sincronizados para o Supply Chain Management:

- Campos somente leitura no cabeçalho de cotação de vendas: **% de Desconto**, **Desconto** e **Valor do Frete**
- Campos somente leitura em produtos de cotação: **Imposto**

## <a name="preconditions-and-mapping-setup"></a>Precondições e configuração de mapeamento

Antes de as cotações de venda serem sincronizadas, é importante atualizar as configurações a seguir.

### <a name="setup-in-sales"></a>Configuração no Sales

- Verifique se as permissões estão definidas para a equipe na qual o usuário da conexão configurada no Sales está atribuído. Se estiver usando os dados de demonstração, geralmente o usuário tem acesso admin, mas a equipe não tem acesso admin. Se a equipe não tiver acesso de administrador quando você executar o projeto na Integração de dados, você receberá uma mensagem de erro indicando que a Equipe principal está ausente.

    Para configurar as permissões para a equipe, Acesse **Configurações** &gt; **Segurança** &gt; **Equipes** e selecione a equipe relevante. Selecione **Gerenciar funções** e, em seguida, selecione a função que possui as permissões desejadas, como **Administrador do sistema**.

- Acesse **Configurações** &gt; **Administração** &gt; **Configurações do sistema** &gt; **Vendas** e certifique-se de que as seguintes configurações sejam usadas:

    - A opção **Usar sistema de cálculo de precificação do sistema** está definida como **Sim**.
    - O campo **Método de cálculo de desconto** está definido como **Item de linha**.

### <a name="setup-in-the-data-integration-project"></a>Configuração no Projeto de integração de dados

#### <a name="quoteheader"></a>QuoteHeader

- Verifique se o mapeamento exigido existe para **Shipto\_country** para **DeliveryAddressCountryRegionISOCode**. No mapa de valores, você pode definir um valor padrão para ser usado se o valor for deixado em branco. Deixe apenas o lado esquerdo em branco e defina o lado direito para o país ou a região desejada. Assim, não é necessário digitar o país ou a região de ordens nacionais.

    O valor do modelo é um mapa de valores em que vários países ou regiões são mapeados e um valor em branco é igual a um valor do **EUA**.

#### <a name="quoteline"></a>QuoteLine

- Verifique se existe o mapa de valores necessário para **SalesUnitSymbol** no Supply Chain Management.
- Verifique se as unidades necessários estão definidas no Sales.

    Um valor do modelo que tem um mapa de valores é definido para **oumid.name** como **SalesUnitSymbol**.

- Opcional: Você pode adicionar os seguintes mapeamentos para ajudar a garantir que as linhas da cotação de venda sejam importadas para o Supply Chain Management, caso não haja informações padrão do cliente ou do produto:

    - **SiteId** – Um site é necessário para gerar cotações e linhas da ordem de venda no Supply Chain Management. Não há valor do modelo padrão para **SiteId**.
    - **WarehouseId** – Um depósito é necessário para processar cotações e linhas da ordem de venda no Supply Chain Management. Não há valor do modelo padrão para **WarehouseId**.

## <a name="template-mapping-in-data-integrator"></a>Mapeamento de modelos no integrador de dados

> [!NOTE]
> - Os campos **Desconto**, **Encargos** e **Imposto** são controlados por uma configuração complexa no Supply Chain Management. No momento, essa configuração não dá suporte ao mapeamento de integração. No design atual, os campos **Preço**, **Desconto**, **Encargo** e **Imposto** são tratados pelo Supply Chain Management.
> - Os campos **Termos de pagamento**, **Condições de frete**, **Condições de entrega**, **Método de entrega** e **Modo de entrega** não estão incluídos no mapeamento padrão. Para mapear esses campos, é necessário configurar um mapeamento de valor que é específico para os dados nas organizações às quais a entidade está sincronizada.

As seguintes ilustrações mostram um exemplo de um mapeamento de modelos no integrador de dados.

### <a name="quoteheader"></a>QuoteHeader

![Mapeamento de modelos no integrador de dados: QuoteHeader.](./media/sales-quotation-direct-template-mapping-data-integrator-1.png)

### <a name="quoteline"></a>QuoteLine

![Mapeamento de modelos no integrador de dados: QuoteLine.](./media/sales-quotation-direct-template-mapping-data-integrator-2.png)

## <a name="related-topics"></a>Tópicos relacionados

[De cliente potencial ao pagamento à vista](prospect-to-cash.md)



[!INCLUDE[footer-include](../../includes/footer-banner.md)]