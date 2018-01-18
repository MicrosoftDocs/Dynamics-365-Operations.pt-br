---
title: "Sincronizar cabeçalhos e linhas de fatura do Finance and Operations com o Sales"
description: "O tópico discute os modelos e as tarefas subjacentes que são usados para sincronizar cabeçalhos e linhas de fatura de venda do Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition para Microsoft Dynamics 365 for Sales."
author: ChristianRytt
manager: AnnBe
ms.date: 08/28/2017
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
ms.openlocfilehash: 22ab02555dcac850b18aac9564af41d6c627eade
ms.contentlocale: pt-br
ms.lasthandoff: 11/03/2017

---

# <a name="synchronize-sales-invoice-headers-and-lines-from-finance-and-operations-to-sales"></a>Sincronizar cabeçalhos e linhas de fatura do Finance and Operations com o Sales

[!include[banner](../includes/banner.md)]

O tópico discute os modelos e as tarefas subjacentes que são usados para sincronizar cabeçalhos e linhas de fatura de venda do Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition para Microsoft Dynamics 365 for Sales. 

## <a name="templates-and-tasks"></a>Modelos e tarefas

Os modelos e as tarefas subjacentes a seguir são usados para sincronizar cabeçalhos e linhas de fatura de venda do Finance and Operations com o Sales:

- **Nome do modelo na Integração de dados** 

     - Faturas de vendas (Fin and Ops para Sales)

- **Nomes das tarefas no projeto de Integração de dados**

    - SalesInvoiceHeader
    - SalesInvoiceLine

As tarefas de sincronização necessárias antes da sincronização do cabeçalho e das linhas da fatura de Vendas:
-   Produtos (Fin and Ops para Sales)
-   Contas (Sales para Fin and Ops) (se usadas)
-   Contatos (Sales para Fin and Ops) (se usados)
-   Cabeçalho e linhas de ordem de venda (Fin and Ops para Sales)

## <a name="entity-set"></a>Conjunto de entidades

| Finance and Operations                               | Common Data Service (CDS)              | Vendas          |
|------------------------------------------------------|------------------|----------------|
| Cabeçalhos de faturas de vendas de cliente mantidas externamente | SalesInvoice     | Faturas       |
| Linhas de faturas de vendas de cliente mantidas externamente   | SalesInvoiceLine | InvoiceDetails |

## <a name="entity-flow"></a>Fluxo de entidades

As faturas de vendas são criadas no Finance and Operations e sincronizadas no Sales.

> [!NOTE]
> Os impostos relacionadas aos encargos no **Cabeçalho de fatura de venda** não são incluídos na sincronização do Finance and Operations para Sales. Isso porque o Sales não oferece suporte às informações de imposto em nível de cabeçalho. Os impostos relacionadas aos encargos em nível de linha são incluídos.

## <a name="prospect-to-cash-solution-for-sales"></a>Solução Prospect to cash para o Sales

-  Um **Campo de número de fatura** é adicionado à entidade **Fatura** e exibido na página.
 
-  O botão **Criar fatura** na página **Ordem de venda** é oculto porque as faturas serão criadas no Finance and Operations e sincronizadas ao Sales. A página **Fatura** não é editável porque as faturas serão sincronizadas do Finance and Operations.
 
-  O **Status da ordem de venda** é alterado automaticamente para **Faturado** quando a fatura relacionada do Finance and Operations for sincronizada ao Sales. Além disso, o proprietário da ordem de venda da qual foi criada a fatura é atribuído como o proprietário da fatura. Isso proporciona ao proprietário da ordem de venda a capacidade de exibir a fatura.
 
## <a name="preconditions-and-mapping-setup"></a>Precondições e configuração de mapeamento

Antes de sincronizar faturas de venda, é importante atualizar os sistemas com a seguinte configuração:

### <a name="setup-in-sales"></a>Configuração no Sales

- Em **Configurações** > **Administração** > **Configurações do sistema** > **Sales**, certifique-se de que **Usar sistema de cálculo de precificação do sistema** esteja definido como **Sim**. 

- Em **Configurações** > **Administração** > **Configurações do sistema** > **Sales**, certifique-se de que o **Método de cálculo de desconto** esteja definido como **Item de linha**. 

### <a name="setup-in-the-data-integration-project"></a>Configuração no Projeto de integração de dados

#### <a name="salesinvoiceheader-task"></a>tarefa SalesInvoiceHeader

- Atualizar o mapeamento para **ID da Organização CDS** em **Origem** > **CDS**. 

    -  O valor do modelo padrão para **SalesOrder_Organization_OrganizationId** é ORG001.
    -  O valor do modelo padrão para **Account_Organization_OrganizationId** é ORG001.
    -  O valor do modelo padrão para **Organization_OrganizationId** é ORG001.

- Verifique se o mapeamento necessário existe na **Origem** > **CDS para InvoiceCountryRegionId** para **BillingAddress_Country**.

    -  O valor do modelo é **ValueMap** com um número de países mapeado.

- **Lista de preços** é necessário para criar faturas em Sales. Atualize o **ValueMap** no **CDS** > **Destino para pricelevelid.name [Price List Name]** para a **Lista de preços** usada no Sales por moeda. Você pode usar uma **Lista de preços** padrão para uma única moeda ou usar **ValueMap** se tiver **Listas de preços** em várias moedas.

    -  O valor do modelo para **pricelevelid.name [Price List Name]** é **ValueMap** com base na **Moeda**.
    -  usd: Serviço CRM USA (amostra). 

#### <a name="salesinvoiceline-task"></a>Tarefa SalesInvoiceLine

- Certifique-se de que o mapeamento necessário existe em **Origem** > **CDS para Unidade de medida**.

- Verifique se o **ValueMap** necessário para **SalesUnitSymbol** no Finance and Operations existe em **Origem** > **Mapeamento de CDS**. 
    
    - O valor do modelo com **ValueMap** é definido para **SalesUnitSymbol to Quantity_UOM**.
    
-  Atualize o mapeamento para **ID da Organização CDS na Origem** > **CDS**. 

    -  O valor do modelo padrão para **SalesInvoicer_Organization_OrganizationId** é ORG001.
    -  O valor do modelo padrão para **Product_Organization_OrganizationId** é ORG001.
 
## <a name="template-mapping-in-data-integrator"></a>Mapeamento de modelo no Integrador de dados

> [!NOTE]
> **Condições de pagamento**, **Condições de frete**, **Condições de entrega**, **Método de remessa** e **Modo de entrega** fazem parte dos mapeamentos padrão. O mapeamento destes campos exige que o mapeamento de valor seja configurado, o que é específico para os dados nas organizações entre as quais a entidade deve ser sincronizada.

As seguintes ilustrações mostram um exemplo de um mapeamento de modelos no integrador de dados.

![Mapeamento de modelos no integrador de dados](./media/sales-invoice-template-mapping-data-integrator-1.png)

![Mapeamento de modelos no integrador de dados](./media/sales-invoice-template-mapping-data-integrator-2.png)

![Mapeamento de modelos no integrador de dados](./media/sales-invoice-template-mapping-data-integrator-3.png)

![Mapeamento de modelos no integrador de dados](./media/sales-invoice-template-mapping-data-integrator-4.png)


## <a name="related-topics"></a>Tópicos relacionados

[Sincronizar produtos do Finance and Operations com produtos do Sales](products-template-mapping.md)

[Sincronizar contas do Sales com clientes do Finance and Operations](accounts-template-mapping.md)

[Sincronizar contatos do Sales com contatos ou clientes do Finance and Operations](contacts-template-mapping.md)

[Sincronizar cabeçalhos e linhas de cotação de venda do Sales com o Finance and Operations](sales-quotation-template-mapping.md)

[Sincronizar cabeçalhos e linhas de ordem de venda do Finance and Operations com o Sales](sales-order-template-mapping.md)


