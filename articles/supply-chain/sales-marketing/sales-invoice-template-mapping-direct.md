---
title: Sincronizar cabeçalhos e linhas da fatura de venda diretamente do Supply Chain Management para o Sales
description: Este tópico discute os modelos e as tarefas subjacentes que são usados para sincronizar cabeçalhos e linhas de fatura de venda diretamente do Dynamics 365 Supply Chain Management para o Dynamics 365 Sales.
author: ChristianRytt
manager: AnnBe
ms.date: 10/26/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: crytt
ms.dyn365.ops.version: July 2017 update
ms.search.validFrom: 2017-07-8
ms.openlocfilehash: fa2772db63332319c399999bd5f747b2ac729d9e
ms.sourcegitcommit: 0099fb24f5f40ff442020b488ef4171836c35c48
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/23/2019
ms.locfileid: "2653266"
---
# <a name="synchronize-sales-invoice-headers-and-lines-directly-from-finance-and-operations-to-sales"></a>Sincronizar cabeçalhos e linhas da fatura de venda diretamente do Finance and Operations para o Sales

[!include [banner](../includes/banner.md)]

Este tópico discute os modelos e as tarefas subjacentes que são usados para sincronizar cabeçalhos e linhas de fatura de venda diretamente do Dynamics 365 Supply Chain Management para o Dynamics 365 Sales.

## <a name="data-flow-in-prospect-to-cash"></a>Fluxo de dados no Prospect to cash

A solução Prospect to cash usa o recurso Integração de dados para sincronizar dados entre as instâncias Supply Chain Management e do Sales. Os modelos de Prospect to cash que estão disponíveis com o recurso Integração de dados permitem o fluxo de dados sobre contas, contatos, produtos, cotações de venda, ordens de venda e faturas de venda entre o Supply Chain Management e o Sales. A ilustração a seguir mostra como os dados são sincronizados entre o Supply Chain Management e o Sales.

[![Fluxo de dados em Prospect to cash](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)

## <a name="templates-and-tasks"></a>Modelos e tarefas

Para acessar os modelos disponíveis, abra o [Centro de administração do PowerApps](https://preview.admin.powerapps.com/dataintegration). Selecione **Projetos** e, no canto superior direito, selecione **Novo projeto** para selecionar modelos públicos.

O seguinte modelo e as tarefas subjacentes são usados para sincronizar cabeçalhos e linhas da fatura de venda diretamente do Supply Chain Management para o Sales:

- **Nome do modelo na Integração de dados:** faturas de venda (Fin and Ops para Sales) – Direto
- **Nomes das tarefas no projeto de Integração de dados:**

    - SalesInvoiceHeader
    - SalesInvoiceLine

As seguintes tarefas de sincronização são obrigatórias para que a sincronização de cabeçalhos e linhas de fatura de venda possa ocorrer:

- Produtos (Supply Chain Management para Sales) – Direto
- Contas (Sales para Supply Chain Management) – Direto (se usado)
- Contatos (Sales para Supply Chain Management) – Direto (se usado)
- Cabeçalhos e linhas da ordem de venda (Supply Chain Management para Sales) - Direto

## <a name="entity-set"></a>Conjunto de entidades

| Gerenciamento da Cadeia de Fornecedores                              | Vendas          |
|------------------------------------------------------|----------------|
| Cabeçalhos de faturas de vendas de cliente mantidas externamente | Faturas       |
| Linhas de faturas de vendas de cliente mantidas externamente   | InvoiceDetails |

## <a name="entity-flow"></a>Fluxo de entidades

As faturas de vendas são criadas no Supply Chain Management e sincronizadas no Sales.

> [!NOTE]
> Atualmente, o imposto que está relacionado aos encargos no cabeçalho da fatura de venda não é incluído na sincronização do Supply Chain Management para o Sales. O Sales não dá suporte às informações de imposto em nível de cabeçalho. Entretanto, impostos relativos aos encargos em nível de linha são incluídos na sincronização.

## <a name="prospect-to-cash-solution-for-sales"></a>Solução Prospect to cash para o Sales

- Um campo **Número de fatura** foi adicionado à entidade **Fatura** e aparece na página.
- O botão **Criar fatura** na página **Ordem de venda** é ocultado, pois as faturas serão criadas no Supply Chain Management e sincronizadas com o Sales. A página **Fatura** não pode ser editada, pois as faturas serão sincronizadas do Supply Chain Management.
- O valor do **Status da ordem de venda** é alterado automaticamente para **Faturado** quando a fatura relacionada do Supply Chain Management é sincronizada com o Sales. Além disso, o proprietário da ordem de venda da qual a fatura foi criada é atribuído como o proprietário da fatura. Portanto, o proprietário da ordem de venda pode exibir a fatura.

## <a name="preconditions-and-mapping-setup"></a>Precondições e configuração de mapeamento

Antes de sincronizar faturas de venda, é importante atualizar as configurações a seguir nos sistemas.

### <a name="setup-in-sales"></a>Configuração no Sales

Vá para **Configurações** > **Administração** > **Configurações do sistema** > **Sales** e verifique se as seguintes configurações foram usadas:

- A opção **Usar sistema de cálculo de precificação do sistema** está definida como **Sim**.
- O campo **Método de cálculo de desconto** está definido como **Item de linha**.

### <a name="setup-in-the-data-integration-project"></a>Configuração no Projeto de integração de dados

#### <a name="salesinvoiceheader-task"></a>tarefa SalesInvoiceHeader

- Verifique se há o mapeamento exigido para **InvoiceCountryRegionId** como **BillingAddress\_Country**.

    O valor do modelo é um mapa de valores em que vários países ou regiões são mapeados.

- Uma lista de preços é necessária para criar faturas no Sales. Atualize o mapa de valores para **pricelevelid.name \[Price list name\]** para a lista de preços que é usada no Sales por moeda. Você pode usar a lista de preços padrão para uma única moeda. Caso existam listas de preços em várias moedas, você poderá usar um mapa de valores.

    O valor do método de **pricelevelid.name \[Price list name\]** é um mapa de valores baseado na moeda com USD = Serviço CRM USA (amostra).  
    
#### <a name="salesinvoiceline-task"></a>Tarefa SalesInvoiceLine

- Verifique se há o mapeamento exigido de **Unidade de medida**.
- Verifique se existe o mapa de valores necessário para **SalesUnitSymbol** no Supply Chain Management.

    Um valor do modelo que tem um mapa de valores é definido para **SalesUnitSymbol** como **Quantity\_UOM**.

## <a name="template-mapping-in-data-integration"></a>Mapeamento de modelo na Integração de dados

> [!NOTE]
> Os campos **Termos de pagamento**, **Condições de frete**, **Condições de entrega**, **Método de remessa** e **Modo de entrega** não estão incluídos no mapeamento padrão. Para mapear esses campos, é necessário configurar um mapeamento de valor que é específico para os dados nas organizações às quais a entidade está sincronizada.

As ilustrações a seguir mostram um exemplo de um mapeamento de modelo na Integração de dados. 

> [!NOTE]
> O mapeamento mostra quais informações de campo serão sincronizadas do Sales com o Supply Chain Management.

### <a name="salesinvoiceheader"></a>SalesInvoiceHeader

![Mapeamento de modelo na Integração de dados](./media/sales-invoice-direct-template-mapping-data-integrator-1.png)

### <a name="salesinvoiceline"></a>SalesInvoiceLine

![Mapeamento de modelo na Integração de dados](./media/sales-invoice-direct-template-mapping-data-integrator-2.png)



## <a name="related-topics"></a>Tópicos relacionados

[Cliente potencial ao pagamento à vista](prospect-to-cash.md)

[Sincronizar contas diretamente do Sales com clientes no Supply Chain Management](accounts-template-mapping-direct.md)

[Sincronizar produtos diretamente do Supply Chain Management com produtos do Sales](products-template-mapping-direct.md)

[Sincronizar contatos diretamente do Sales com contatos ou clientes do Supply Chain Management](contacts-template-mapping-direct.md)

[Sincronizar cabeçalhos e linhas da ordem de venda diretamente do Supply Chain Management com o Sales](sales-order-template-mapping-direct-two-ways.md)
