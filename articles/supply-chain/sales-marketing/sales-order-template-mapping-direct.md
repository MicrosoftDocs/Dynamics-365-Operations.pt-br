---
title: "Sincronizar cabeçalhos e linhas de ordem de venda diretamente do Finance and Operations com o Sales"
description: "Este tópico discute os modelos e as tarefas subjacentes que são usados para sincronizar cabeçalhos e linhas de ordem de venda diretamente do Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition, com o Microsoft Dynamics 365 for Sales."
author: ChristianRytt
manager: AnnBe
ms.date: 10/25/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: 
audience: Application User, IT Pro
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.search.industry: 
ms.author: crytt
ms.dyn365.ops.version: July 2017 update
ms.search.validFrom: 2017-07-8
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: cc0be50552ae680ba5291e72b7c482ee67e1e70e
ms.contentlocale: pt-br
ms.lasthandoff: 11/03/2017

---

# <a name="synchronize-sales-order-headers-and-lines-directly-from-finance-and-operations-to-sales"></a>Sincronizar cabeçalhos e linhas de ordem de venda diretamente do Finance and Operations com o Sales

[!include[banner](../includes/banner.md)]

Este tópico discute os modelos e as tarefas subjacentes que são usados para sincronizar cabeçalhos e linhas de ordem de venda diretamente do Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition, com o Microsoft Dynamics 365 for Sales.

## <a name="data-flow-in-prospect-to-cash"></a>Fluxo de dados no Prospect to cash

A solução Prospect to cash usa o recurso de integração de dados sincronizar dados nas instâncias do Finance and Operations e do Sales. Os modelos Prospect to cash que estão disponíveis com o recurso Integração de dados permitem o fluxo de dados sobre contas, contatos, produtos, cotações de vendas, ordens de venda e faturas de vendas entre o Finance and Operations e o Sales. A ilustração a seguir mostra como os dados são sincronizados entre o Finance and Operations e o Sales.

[![Fluxo de dados em Prospect to cash](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)

## <a name="templates-and-tasks"></a>Modelos e tarefas

Para acessar os modelos disponíveis, abra o [Centro de administração de PowerApps](https://preview.admin.powerapps.com/dataintegration). Selecione **Projetos** e, no canto superior direito, selecione **Novo projeto** para selecionar modelos públicos.

O modelo e as tarefas subjacentes a seguir são usados para sincronizar cabeçalhos e linhas da ordem de venda do Finance and Operations com o Sales:

- **Nome do modelo na Integração de dados:** Ordens de venda (Fin and Ops para Sales) – Direto
- **Nomes das tarefas no projeto de Integração de dados:**

    - OrderHeader
    - OrderLine

As seguintes tarefas de sincronização são obrigatórias para que a sincronização de cabeçalhos e linhas de fatura de venda possa ocorrer:

- Produtos (Fin and Ops para Sales) – Direto
- Contas (Sales para Fin and Ops) - Direto (se usado)
- Contatos para Clientes (Sales para Fin and Ops) – Direto (se usados)

## <a name="entity-set"></a>Conjunto de entidades

| Finance and Operations  | Vendas             |
|-------------------------|-------------------|
| Cabeçalhos de ordens de venda CDS | SalesOrders       |
| Linhas de ordem de venda do CDS   | SalesOrderDetails |

## <a name="entity-flow"></a>Fluxo de entidades

As ordens de venda são criadas no Finance and Operations e sincronizadas com o Sales.

Os filtros em modelo ajudam a garantir que somente as ordens de venda relevantes sejam incluídas na sincronização:

- Na ordem de venda, a solicitação do cliente e o faturamento do cliente que originam-se do Sales serão incluídos na sincronização. No Finance and Operations, os campos **OrderingCustomerIsExternallyMaintained** e **InvoiceCustomerIsExternallyMaintained** são usados para rastrear a sincronização nas entidades de dados.
- A ordem de venda no Finance and Operations deve ser confirmada. Somente ordens de venda confirmadas ou ordens de venda com status de processamento superior, como **Enviado** ou **Faturado** são sincronizadas com o Sales.
- Após uma ordem de venda ser criada ou modificada, o trabalho em lotes **Calcular totais de vendas** no Finance and Operations deve ser executado. Somente as ordens de venda em que os totais de vendas são calculados serão sincronizadas para o Sales.

> [!NOTE]
> Atualmente, o imposto que está relacionado aos encargos no cabeçalho de ordem de venda não é incluído na sincronização do Finance and Operations com o Sales. O Sales não dá suporte às informações de imposto em nível de cabeçalho. Entretanto, impostos relativos aos encargos em nível de linha são incluídos na sincronização.

## <a name="prospect-to-cash-solution-for-sales"></a>Solução Prospect to cash para o Sales

Novos campos foram adicionados à entidade **Ordem** e são exibidos na página:

- **É mantido externamente** – Defina esta opção como **Sim** quando a ordem for proveniente do Finance and Operations.
- **Status de processamento** – Este campo mostra o status de processamento da ordem no Finance and Operations. Os valores a seguir estão disponíveis:

    - Ativos
    - Confirmada
    - Guia de remessa
    - Faturadas
    - Separado
    - Parcialmente separada
    - Parcialmente embalada
    - Remetido
    - Parcialmente remetida
    - Parcialmente faturada
    - Cancelado

A configuração **Tem Somente Produtos Mantidos Externamente** é usada em outros cenários de ordem de venda (por exemplo, sincronização do Sales com o Finance and Operation) para rastrear se a ordem de venda consiste totalmente de produtos mantidos externamente. Se uma ordem de venda consiste inteiramente em produtos mantidos externamente, os produtos são mantidos no Finance and Operations. Esta configuração ajuda a garantir que você não tente sincronizar linhas da ordem de venda que tenham produtos que sejam desconhecidos para Finance and Operations.

Os botões **Criar fatura**, **Cancelar Ordem**, **Recalcular**, **Obter Produtos** e **Procurar Endereço** na página **Ordem de venda** são ocultos para ordens mantidas externamente, pois as faturas serão criadas no Finance and Operations e sincronizadas para o Sales. A página da ordem não pode ser editada, porque as informações da ordem de venda serão sincronizadas do Finance and Operations.

O status de uma ordem de venda permanecerá **Ativo** para ajudar a garantir que as alterações do Finance and Operations possam fluir para a ordem de venda do Sales. Para controlar este comportamento, defina o padrão do valor **Statecode \[Status\]** para **Ativo** no Projeto de integração de dados.

## <a name="preconditions-and-mapping-setup"></a>Precondições e configuração de mapeamento

Antes de sincronizar ordens de venda, é importante atualizar as configurações a seguir nos sistemas.

### <a name="setup-in-sales"></a>Configuração no Sales

- Verifique se as permissões estão definidas para a equipe à qual foi atribuído o usuário da conexão do Sales definida. Se estiver usando os dados de demonstração, geralmente o usuário tem acesso admin, mas a equipe não tem acesso admin. Se a equipe não tiver acesso admin, quando o projeto for executado da Integração de dados, você receberá uma mensagem de erro que indica que a Equipe principal está ausente.

    Vá para **Configurações** > **Segurança** > **Equipes**, selecione a equipe relevante, selecione **Gerenciar funções** e selecione a função que tem as permissões desejadas, como **Administrador do Sistema**.

- Vá para **Configurações** > **Administração** > **Configurações do sistema** > **Sales** e certifique-se de que as seguintes configurações sejam usadas:

    - A opção **Usar sistema de cálculo de precificação do sistema** está definida como **Sim**.
    - O campo **Método de cálculo de desconto** está definido como **Item de linha**.

### <a name="setup-in-finance-and-operations"></a>Configuração no Finance and Operations

Vá para **Vendas e marketing** > **Tarefas periódicas** > **Calcular totais de vendas** e configure o trabalho para ser executado como um trabalho em lotes. Defina a opção **Calcular totais de ordens de venda** como **Sim**. Esta etapa é importante, pois somente as ordens de venda em que os totais de vendas são calculados serão sincronizadas para o Sales. A frequência do trabalho em lotes deve ser alinhada à frequência de sincronização da ordem de venda.

### <a name="setup-in-the-data-integration-project"></a>Configuração no Projeto de integração de dados

#### <a name="salesheader-task"></a>Tarefa de SalesHeader

- Verifique se o mapeamento exigido existe para **InvoiceCountryRegionId** para **BillingAddress\_Country** e para **DeliveryCountryRegionId** para **DeliveryAddress\_Country**.

    O valor do modelo é um mapa de valores em que vários países ou regiões são mapeados.

- Uma lista de preços é necessária para criar ordens no Sales. Atualize o mapa de valores para **pricelevelid.name \[Price list name\]** para a lista de preços que é usada no Sales por moeda. Você pode usar a lista de preços padrão para uma única moeda. Caso existam listas de preços em várias moedas, você poderá usar um mapa de valores.

    O valor do modelo padrão para **pricelevelid.name \[Price list name\]** é **CRM Service USA (sample)**.

#### <a name="salesline-task"></a>Tarefa de SalesLine

- Verifique se o mapeamento exigido existe para **DeliveryCountryRegionId** para **DeliveryAddress\_Country**.

    O valor do modelo é um mapa de valores em que vários países ou regiões são mapeados.

- Verifique se existe o mapa de valores necessário para **SalesUnitSymbol** no Finance and Operations.

    Um valor do modelo que tem um mapa de valores é definido para **SalesUnitSymbol** como **Quantity\_UOM**.

## <a name="template-mapping-in-data-integration"></a>Mapeamento de modelo na Integração de dados

> [!NOTE]
> Os campos **Termos de pagamento**, **Condições de frete**, **Condições de entrega**, **Método de remessa** e **Modo de entrega** não estão incluídos no mapeamento padrão. Para mapear esses campos, é necessário configurar um mapeamento de valor que é específico para os dados nas organizações às quais a entidade está sincronizada.

As ilustrações a seguir mostram um exemplo de um mapeamento de modelo na Integração de dados. 

> [!NOTE]
> O mapeamento mostra quais informações de campo serão sincronizadas do Sales com o Finance and Operations..

### <a name="orderheader"></a>OrderHeader

![Mapeamento de modelo no Integrador de dados](./media/sales-order-direct-template-mapping-data-integrator-1.png)

### <a name="orderline"></a>OrderLine

![Mapeamento de modelo no Integrador de dados](./media/sales-order-direct-template-mapping-data-integrator-2.png)



## <a name="related-topics"></a>Tópicos relacionados

[Prospect to cash](prospect-to-cash.md)

[Sincronizar contas diretamente do Sales com clientes do Finance and Operations](accounts-template-mapping-direct.md)

[Sincronizar produtos diretamente do Finance and Operations com produtos no Sales](products-template-mapping-direct.md)

[Sincronizar contatos diretamente do Sales com contatos ou clientes do Finance and Operations](contacts-template-mapping-direct.md)

[Sincronizar cabeçalhos e linhas de fatura diretamente do Finance and Operations com o Sales](sales-invoice-template-mapping-direct.md)




