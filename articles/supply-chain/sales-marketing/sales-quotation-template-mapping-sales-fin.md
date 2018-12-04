---
title: "Sincronizar cabeçalhos e linhas de cotação de venda diretamente do Sales para o Finance and Operations"
description: "O tópico discute os modelos e as tarefas subjacentes que são usados para sincronizar cabeçalhos e linhas de cotação de venda diretamente do Microsoft Dynamics 365 for Sales para o Microsoft Dynamics 365 for Finance and Operations."
author: ChristianRytt
manager: AnnBe
ms.date: 10/25/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: 
audience: Application User, IT Pro
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.search.industry: 
ms.author: crytt
ms.dyn365.ops.version: July 2017 update
ms.search.validFrom: 2017-07-8
ms.translationtype: HT
ms.sourcegitcommit: 0450326dce0ba6be99aede4ebc871dc58c8039ab
ms.openlocfilehash: efe943f5c874ed041ce7984272ebc19f57cca6ef
ms.contentlocale: pt-br
ms.lasthandoff: 11/01/2018

---

# <a name="synchronize-sales-quotation-headers-and-lines-directly-from-sales-to-finance-and-operations"></a>Sincronizar cabeçalhos e linhas de cotação de venda diretamente do Sales para o Finance and Operations

[!include [banner](../includes/banner.md)]

O tópico discute os modelos e as tarefas subjacentes que são usados para sincronizar cabeçalhos e linhas de cotação de venda diretamente do Microsoft Dynamics 365 for Sales para o Microsoft Dynamics 365 for Finance and Operations.

> [!NOTE]
> Antes de usar a solução Prospect to cash, você deve familiarizar-se com a [Integração de dados no Common Data Service para Aplicativos](https://docs.microsoft.com/en-us/powerapps/administrator/data-integrator).

## <a name="data-flow-in-prospect-to-cash"></a>Fluxo de dados no Prospect to cash

A solução Prospect to cash usa o recurso de integração de dados sincronizar dados nas instâncias do Finance and Operations e do Sales. Os modelos Prospect to cash que estão disponíveis com o recurso Integração de Dados permitem o fluxo de dados para contas, contatos, produtos, cotações de vendas, ordens de venda e faturas de vendas entre o Finance and Operations e o Sales. A ilustração a seguir mostra como os dados são sincronizados entre o Finance and Operations e o Sales.

[![Fluxo de dados em Prospect to cash](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)

## <a name="template-and-tasks"></a>Modelo e tarefas

O seguinte modelo e as tarefas subjacentes são usados para sincronizar cabeçalhos e linhas de cotação de venda diretamente do Sales para o Finance and Operations:

- **Nome do modelo na Integração de dados:** cotações de venda (Sales para Fin and Ops) – Direto
- **Nomes das tarefas no projeto de Integração de dados:**

    - QuoteHeader
    - QuoteLine

As seguintes tarefas de sincronização são obrigatórias para que a sincronização de cabeçalhos e linhas de cotação de venda possa ocorrer:

- Produtos (Fin and Ops para Sales) – Direto
- Contas (Sales para Fin and Ops) - Direto (se usado)
- Contatos para Clientes (Sales para Fin and Ops) – Direto (se usados)

## <a name="entity-set"></a>Conjunto de entidades

| Vendas        | Finance and Operations     |
|--------------|----------------------------|
| Cotações       | Cabeçalho de cotação de venda CDS |
| QuoteDetails | Linhas de cotação de venda do CDS  |

## <a name="entity-flow"></a>Fluxo de entidades

As cotações de vendas são criadas no Sales e sincronizadas ao Finance and Operations.

As cotações de vendas do Sales são sincronizadas somente se as seguintes condições forem atendidas:

- Todos os produtos de cotação na cotação de vendas são mantidos externamente.
- Após você clicar em **Ativar cotação**, a cotação de venda ficará ativa.

## <a name="prospect-to-cash-solution-for-sales"></a>Solução Prospect to cash para o Sales

O campo **Tem Somente Produtos Mantidos Externamente** foi adicionado à entidade **Cotação** para rastrear consistentemente se a cotação de vendas consiste inteiramente em produtos mantidos externamente. Se uma cotação de venda mantiver somente produtos externamente, os produtos serão mantidos no Finance and Operations. Este comportamento ajuda a garantir que você não tente sincronizar linhas da cotação de vendas que tenham produtos que são desconhecidos para o Finance and Operations.

Todos os produtos de cotação da cotação de venda são atualizados com as informações **Tem Somente Produtos Mantidos Externamente** do cabeçalho de cotação de venda. Essas informações se encontram no campo **A Cotação Tem Somente Produtos Mantidos Externamente** na entidade **QuoteDetails**.

Um desconto pode ser adicionado ao produto de cotação e será sincronizado para o Finance and Operations. Os campos **Desconto**, **Encargos** e **Imposto** no cabeçalho são controlados por uma configuração no Finance and Operations. No momento, essa configuração não dá suporte ao mapeamento de integração. No design atual, os campos **Preço**, **Desconto**, **Encargo** e **Imposto** são mantidos e tratados no Finance and Operations.

No Sales, a solução torna os seguintes campos somente para leitura, porque os valores não são sincronizados com o Finance and Operations:

- Campos somente leitura no cabeçalho de cotação de vendas: **% de Desconto**, **Desconto** e **Valor do Frete**
- Campos somente leitura em produtos de cotação: **Imposto**

## <a name="preconditions-and-mapping-setup"></a>Precondições e configuração de mapeamento

Antes de as cotações de venda serem sincronizadas, é importante atualizar as configurações a seguir.

### <a name="setup-in-sales"></a>Configuração no Sales

- Verifique se as permissões estão definidas para a equipe na qual o usuário da conexão configurada no Sales está atribuído. Se estiver usando os dados de demonstração, geralmente o usuário tem acesso admin, mas a equipe não tem acesso admin. Se a equipe não tiver acesso de administrador quando você executar o projeto na Integração de dados, você receberá uma mensagem de erro indicando que a Equipe principal está ausente.

    Para configurar as permissões para a equipe, vá para **Configurações** &gt; **Segurança** &gt; **Equipes** e selecione a equipe relevante. Selecione **Gerenciar funções** e, em seguida, selecione a função que possui as permissões desejadas, como **Administrador do sistema**.

- Vá para **Configurações** &gt; **Administração** &gt; **Configurações do sistema** &gt; **Vendas** e certifique-se de que as seguintes configurações sejam usadas:

    - A opção **Usar sistema de cálculo de precificação do sistema** está definida como **Sim**.
    - O campo **Método de cálculo de desconto** está definido como **Item de linha**.

### <a name="setup-in-the-data-integration-project"></a>Configuração no Projeto de integração de dados

#### <a name="quoteheader"></a>QuoteHeader

- Verifique se o mapeamento exigido existe para **Shipto\_country** para **DeliveryAddressCountryRegionISOCode**. No mapa de valores, você pode definir um valor padrão para ser usado se o valor for deixado em branco. Deixe apenas o lado esquerdo em branco e defina o lado direito para o país ou a região desejada. Assim, não é necessário digitar o país ou a região de ordens nacionais.

    O valor do modelo é um mapa de valores em que vários países ou regiões são mapeados e um valor em branco é igual a um valor do **EUA**.

#### <a name="quoteline"></a>QuoteLine

- Verifique se existe o mapa de valores necessário para **SalesUnitSymbol** no Finance and Operations.
- Verifique se as unidades necessários estão definidas no Sales.

    Um valor do modelo que tem um mapa de valores é definido para **oumid.name** como **SalesUnitSymbol**.

- Opcional: Você pode adicionar os seguintes mapeamentos para ajudar a garantir que as linhas de cotação de venda sejam importadas para o Finance and Operations, caso não haja informações padrão do cliente ou do produto:

    - **SiteId** – Um site é necessário para gerar cotações e linhas da ordem de venda no Finance and Operations. Não há valor do modelo padrão para **SiteId**.
    - **WarehouseId** – Um depósito é necessário para processar cotações e linhas da ordem de venda no Finance and Operations. Não há valor do modelo padrão para **WarehouseId**.

## <a name="template-mapping-in-data-integrator"></a>Mapeamento de modelos no integrador de dados

> [!NOTE]
> - Os campos **Desconto**, **Encargos** e **Imposto** são controlados por uma configuração complexa no Finance and Operations. No momento, essa configuração não dá suporte ao mapeamento de integração. No design atual, os campos **Preço**, **Desconto**, **Encargo** e **Imposto** são tratados pelo Finance and Operations.
> - Os campos **Termos de pagamento**, **Condições de frete**, **Condições de entrega**, **Método de entrega** e **Modo de entrega** não estão incluídos no mapeamento padrão. Para mapear esses campos, é necessário configurar um mapeamento de valor que é específico para os dados nas organizações às quais a entidade está sincronizada.

As seguintes ilustrações mostram um exemplo de um mapeamento de modelos no integrador de dados.

### <a name="quoteheader"></a>QuoteHeader

![Mapeamento de modelos no integrador de dados](./media/sales-quotation-direct-template-mapping-data-integrator-1.png)

### <a name="quoteline"></a>QuoteLine

![Mapeamento de modelos no integrador de dados](./media/sales-quotation-direct-template-mapping-data-integrator-2.png)

## <a name="related-topics"></a>Tópicos relacionados

[Prospect to cash](prospect-to-cash.md)


