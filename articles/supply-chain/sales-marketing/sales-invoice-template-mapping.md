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
ms.dyn365.ops.intro: July 2017 update
ms.search.validFrom: 2017-07-8
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 22ab02555dcac850b18aac9564af41d6c627eade
ms.contentlocale: pt-br
ms.lasthandoff: 11/03/2017

---

# <a name="synchronize-sales-invoice-headers-and-lines-from-finance-and-operations-to-sales"></a><span data-ttu-id="32906-103">Sincronizar cabeçalhos e linhas de fatura do Finance and Operations com o Sales</span><span class="sxs-lookup"><span data-stu-id="32906-103">Synchronize sales invoice headers and lines from Finance and Operations to Sales</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="32906-104">O tópico discute os modelos e as tarefas subjacentes que são usados para sincronizar cabeçalhos e linhas de fatura de venda do Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition para Microsoft Dynamics 365 for Sales.</span><span class="sxs-lookup"><span data-stu-id="32906-104">The topic discusses the templates and underlying tasks that are used to synchronize sales invoice headers and lines from Microsoft Dynamics 365 for Finance and Operations, Enterprise edition to Microsoft Dynamics 365 for Sales.</span></span> 

## <a name="templates-and-tasks"></a><span data-ttu-id="32906-105">Modelos e tarefas</span><span class="sxs-lookup"><span data-stu-id="32906-105">Templates and tasks</span></span>

<span data-ttu-id="32906-106">Os modelos e as tarefas subjacentes a seguir são usados para sincronizar cabeçalhos e linhas de fatura de venda do Finance and Operations com o Sales:</span><span class="sxs-lookup"><span data-stu-id="32906-106">The following templates and underlying tasks are used to synchronize sales invoice headers and lines from Finance and Operations to Sales:</span></span>

- <span data-ttu-id="32906-107">**Nome do modelo na Integração de dados**</span><span class="sxs-lookup"><span data-stu-id="32906-107">**Name of the template in Data integration**</span></span> 

     - <span data-ttu-id="32906-108">Faturas de vendas (Fin and Ops para Sales)</span><span class="sxs-lookup"><span data-stu-id="32906-108">Sales Invoices (Fin and Ops to Sales)</span></span>

- <span data-ttu-id="32906-109">**Nomes das tarefas no projeto de Integração de dados**</span><span class="sxs-lookup"><span data-stu-id="32906-109">**Names of the tasks in the Data integration project**</span></span>

    - <span data-ttu-id="32906-110">SalesInvoiceHeader</span><span class="sxs-lookup"><span data-stu-id="32906-110">SalesInvoiceHeader</span></span>
    - <span data-ttu-id="32906-111">SalesInvoiceLine</span><span class="sxs-lookup"><span data-stu-id="32906-111">SalesInvoiceLine</span></span>

<span data-ttu-id="32906-112">As tarefas de sincronização necessárias antes da sincronização do cabeçalho e das linhas da fatura de Vendas:</span><span class="sxs-lookup"><span data-stu-id="32906-112">Sync tasks required prior to Sales invoice header and lines synchronization:</span></span>
-   <span data-ttu-id="32906-113">Produtos (Fin and Ops para Sales)</span><span class="sxs-lookup"><span data-stu-id="32906-113">Products (Fin and Ops to Sales)</span></span>
-   <span data-ttu-id="32906-114">Contas (Sales para Fin and Ops) (se usadas)</span><span class="sxs-lookup"><span data-stu-id="32906-114">Accounts (Sales to Fin and Ops) (if used)</span></span>
-   <span data-ttu-id="32906-115">Contatos (Sales para Fin and Ops) (se usados)</span><span class="sxs-lookup"><span data-stu-id="32906-115">Contacts (Sales to Fin and Ops) (if used)</span></span>
-   <span data-ttu-id="32906-116">Cabeçalho e linhas de ordem de venda (Fin and Ops para Sales)</span><span class="sxs-lookup"><span data-stu-id="32906-116">Sales order header and lines (Fin and Ops to Sales)</span></span>

## <a name="entity-set"></a><span data-ttu-id="32906-117">Conjunto de entidades</span><span class="sxs-lookup"><span data-stu-id="32906-117">Entity set</span></span>

| <span data-ttu-id="32906-118">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="32906-118">Finance and Operations</span></span>                               | <span data-ttu-id="32906-119">Common Data Service (CDS)</span><span class="sxs-lookup"><span data-stu-id="32906-119">Common Data Service (CDS)</span></span>              | <span data-ttu-id="32906-120">Vendas</span><span class="sxs-lookup"><span data-stu-id="32906-120">Sales</span></span>          |
|------------------------------------------------------|------------------|----------------|
| <span data-ttu-id="32906-121">Cabeçalhos de faturas de vendas de cliente mantidas externamente</span><span class="sxs-lookup"><span data-stu-id="32906-121">Externally maintained customer sales invoice headers</span></span> | <span data-ttu-id="32906-122">SalesInvoice</span><span class="sxs-lookup"><span data-stu-id="32906-122">SalesInvoice</span></span>     | <span data-ttu-id="32906-123">Faturas</span><span class="sxs-lookup"><span data-stu-id="32906-123">Invoices</span></span>       |
| <span data-ttu-id="32906-124">Linhas de faturas de vendas de cliente mantidas externamente</span><span class="sxs-lookup"><span data-stu-id="32906-124">Externally maintained customer sales invoice lines</span></span>   | <span data-ttu-id="32906-125">SalesInvoiceLine</span><span class="sxs-lookup"><span data-stu-id="32906-125">SalesInvoiceLine</span></span> | <span data-ttu-id="32906-126">InvoiceDetails</span><span class="sxs-lookup"><span data-stu-id="32906-126">InvoiceDetails</span></span> |

## <a name="entity-flow"></a><span data-ttu-id="32906-127">Fluxo de entidades</span><span class="sxs-lookup"><span data-stu-id="32906-127">Entity flow</span></span>

<span data-ttu-id="32906-128">As faturas de vendas são criadas no Finance and Operations e sincronizadas no Sales.</span><span class="sxs-lookup"><span data-stu-id="32906-128">Sales invoices are created in Finance and Operations and synchronized to Sales.</span></span>

> [!NOTE]
> <span data-ttu-id="32906-129">Os impostos relacionadas aos encargos no **Cabeçalho de fatura de venda** não são incluídos na sincronização do Finance and Operations para Sales.</span><span class="sxs-lookup"><span data-stu-id="32906-129">Tax related to charges on the **Sales invoice header** is currently not included in synchronization from Finance and Operations to Sales.</span></span> <span data-ttu-id="32906-130">Isso porque o Sales não oferece suporte às informações de imposto em nível de cabeçalho.</span><span class="sxs-lookup"><span data-stu-id="32906-130">This is because Sales doesn't support tax information at the header level.</span></span> <span data-ttu-id="32906-131">Os impostos relacionadas aos encargos em nível de linha são incluídos.</span><span class="sxs-lookup"><span data-stu-id="32906-131">Tax related to charges at the line level is included.</span></span>

## <a name="prospect-to-cash-solution-for-sales"></a><span data-ttu-id="32906-132">Solução Prospect to cash para o Sales</span><span class="sxs-lookup"><span data-stu-id="32906-132">Prospect to cash solution for Sales</span></span>

-  <span data-ttu-id="32906-133">Um **Campo de número de fatura** é adicionado à entidade **Fatura** e exibido na página.</span><span class="sxs-lookup"><span data-stu-id="32906-133">An **Invoice number field** is added to the **Invoice** entity and displayed on the page.</span></span>
 
-  <span data-ttu-id="32906-134">O botão **Criar fatura** na página **Ordem de venda** é oculto porque as faturas serão criadas no Finance and Operations e sincronizadas ao Sales.</span><span class="sxs-lookup"><span data-stu-id="32906-134">The **Create invoice** button on the **Sales order** page is hidden because invoices will be created in Finance and Operations and synced to Sales.</span></span> <span data-ttu-id="32906-135">A página **Fatura** não é editável porque as faturas serão sincronizadas do Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="32906-135">The **Invoice** page is non-editable because invoices will be synced from Finance and Operations.</span></span>
 
-  <span data-ttu-id="32906-136">O **Status da ordem de venda** é alterado automaticamente para **Faturado** quando a fatura relacionada do Finance and Operations for sincronizada ao Sales.</span><span class="sxs-lookup"><span data-stu-id="32906-136">The **Sales order status** changes automatically to **Invoiced** when the related invoice from Finance and Operations has been  synchronized to Sales.</span></span> <span data-ttu-id="32906-137">Além disso, o proprietário da ordem de venda da qual foi criada a fatura é atribuído como o proprietário da fatura.</span><span class="sxs-lookup"><span data-stu-id="32906-137">Also, the owner of the sales order from which the invoice was created is assigned as the owner of the invoice.</span></span> <span data-ttu-id="32906-138">Isso proporciona ao proprietário da ordem de venda a capacidade de exibir a fatura.</span><span class="sxs-lookup"><span data-stu-id="32906-138">This gives the owner of the sales order the ability to view the invoice.</span></span>
 
## <a name="preconditions-and-mapping-setup"></a><span data-ttu-id="32906-139">Precondições e configuração de mapeamento</span><span class="sxs-lookup"><span data-stu-id="32906-139">Preconditions and mapping setup</span></span>

<span data-ttu-id="32906-140">Antes de sincronizar faturas de venda, é importante atualizar os sistemas com a seguinte configuração:</span><span class="sxs-lookup"><span data-stu-id="32906-140">Before synchronizing sales invoices, it is important to update the systems with the following setting:</span></span>

### <a name="setup-in-sales"></a><span data-ttu-id="32906-141">Configuração no Sales</span><span class="sxs-lookup"><span data-stu-id="32906-141">Setup in Sales</span></span>

- <span data-ttu-id="32906-142">Em **Configurações** > **Administração** > **Configurações do sistema** > **Sales**, certifique-se de que **Usar sistema de cálculo de precificação do sistema** esteja definido como **Sim**.</span><span class="sxs-lookup"><span data-stu-id="32906-142">Under **Settings** > **Administration** > **System settings** > **Sales**, ensure that **Use system prizing calculation system** is set to **Yes**.</span></span> 

- <span data-ttu-id="32906-143">Em **Configurações** > **Administração** > **Configurações do sistema** > **Sales**, certifique-se de que o **Método de cálculo de desconto** esteja definido como **Item de linha**.</span><span class="sxs-lookup"><span data-stu-id="32906-143">Under **Settings** > **Administration** > **System settings** > **Sales**, ensure that **Discount calculation method** is set to **Line item**.</span></span> 

### <a name="setup-in-the-data-integration-project"></a><span data-ttu-id="32906-144">Configuração no Projeto de integração de dados</span><span class="sxs-lookup"><span data-stu-id="32906-144">Setup in the Data integration project</span></span>

#### <a name="salesinvoiceheader-task"></a><span data-ttu-id="32906-145">tarefa SalesInvoiceHeader</span><span class="sxs-lookup"><span data-stu-id="32906-145">SalesInvoiceHeader task</span></span>

- <span data-ttu-id="32906-146">Atualizar o mapeamento para **ID da Organização CDS** em **Origem** > **CDS**.</span><span class="sxs-lookup"><span data-stu-id="32906-146">Update the mapping for **CDS Organization ID** in **Source** > **CDS**.</span></span> 

    -  <span data-ttu-id="32906-147">O valor do modelo padrão para **SalesOrder_Organization_OrganizationId** é ORG001.</span><span class="sxs-lookup"><span data-stu-id="32906-147">Default template value for **SalesOrder_Organization_OrganizationId** is ORG001.</span></span>
    -  <span data-ttu-id="32906-148">O valor do modelo padrão para **Account_Organization_OrganizationId** é ORG001.</span><span class="sxs-lookup"><span data-stu-id="32906-148">Default template value for **Account_Organization_OrganizationId** is ORG001.</span></span>
    -  <span data-ttu-id="32906-149">O valor do modelo padrão para **Organization_OrganizationId** é ORG001.</span><span class="sxs-lookup"><span data-stu-id="32906-149">Default template value for **Organization_OrganizationId** is ORG001.</span></span>

- <span data-ttu-id="32906-150">Verifique se o mapeamento necessário existe na **Origem** > **CDS para InvoiceCountryRegionId** para **BillingAddress_Country**.</span><span class="sxs-lookup"><span data-stu-id="32906-150">Ensure that the needed mapping exists in **Source** > **CDS for InvoiceCountryRegionId** to **BillingAddress_Country**.</span></span>

    -  <span data-ttu-id="32906-151">O valor do modelo é **ValueMap** com um número de países mapeado.</span><span class="sxs-lookup"><span data-stu-id="32906-151">Template value is **ValueMap** with a number of countries mapped.</span></span>

- <span data-ttu-id="32906-152">**Lista de preços** é necessário para criar faturas em Sales.</span><span class="sxs-lookup"><span data-stu-id="32906-152">**Price list** is required to create invoices in Sales.</span></span> <span data-ttu-id="32906-153">Atualize o **ValueMap** no **CDS** > **Destino para pricelevelid.name [Price List Name]** para a **Lista de preços** usada no Sales por moeda.</span><span class="sxs-lookup"><span data-stu-id="32906-153">Update the **ValueMap** in **CDS** > **Destination for pricelevelid.name [Price List Name]** to the **Price list** used in Sales per currency.</span></span> <span data-ttu-id="32906-154">Você pode usar uma **Lista de preços** padrão para uma única moeda ou usar **ValueMap** se tiver **Listas de preços** em várias moedas.</span><span class="sxs-lookup"><span data-stu-id="32906-154">You can either use the default **Price list** for single currency or use **ValueMap** if you have **Price lists** in multiple currencies.</span></span>

    -  <span data-ttu-id="32906-155">O valor do modelo para **pricelevelid.name [Price List Name]** é **ValueMap** com base na **Moeda**.</span><span class="sxs-lookup"><span data-stu-id="32906-155">Template value for **pricelevelid.name [Price List Name]** is **ValueMap** based on **Currency**.</span></span>
    -  <span data-ttu-id="32906-156">usd: Serviço CRM USA (amostra).</span><span class="sxs-lookup"><span data-stu-id="32906-156">usd: CRM Service USA (sample).</span></span> 

#### <a name="salesinvoiceline-task"></a><span data-ttu-id="32906-157">Tarefa SalesInvoiceLine</span><span class="sxs-lookup"><span data-stu-id="32906-157">SalesInvoiceLine task</span></span>

- <span data-ttu-id="32906-158">Certifique-se de que o mapeamento necessário existe em **Origem** > **CDS para Unidade de medida**.</span><span class="sxs-lookup"><span data-stu-id="32906-158">Ensure that the needed mapping exists in **Source** > **CDS for Unit of measure**.</span></span>

- <span data-ttu-id="32906-159">Verifique se o **ValueMap** necessário para **SalesUnitSymbol** no Finance and Operations existe em **Origem** > **Mapeamento de CDS**.</span><span class="sxs-lookup"><span data-stu-id="32906-159">Ensure that the needed **ValueMap** for **SalesUnitSymbol** in Finance and Operations exists in the **Source** > **CDS mapping**.</span></span> 
    
    - <span data-ttu-id="32906-160">O valor do modelo com **ValueMap** é definido para **SalesUnitSymbol to Quantity_UOM**.</span><span class="sxs-lookup"><span data-stu-id="32906-160">Template value with **ValueMap** is defined for **SalesUnitSymbol to Quantity_UOM**.</span></span>
    
-  <span data-ttu-id="32906-161">Atualize o mapeamento para **ID da Organização CDS na Origem** > **CDS**.</span><span class="sxs-lookup"><span data-stu-id="32906-161">Update the mapping for **CDS Organization ID in Source** > **CDS**.</span></span> 

    -  <span data-ttu-id="32906-162">O valor do modelo padrão para **SalesInvoicer_Organization_OrganizationId** é ORG001.</span><span class="sxs-lookup"><span data-stu-id="32906-162">Default template value for **SalesInvoicer_Organization_OrganizationId** is ORG001.</span></span>
    -  <span data-ttu-id="32906-163">O valor do modelo padrão para **Product_Organization_OrganizationId** é ORG001.</span><span class="sxs-lookup"><span data-stu-id="32906-163">Default template value for **Product_Organization_OrganizationId** is ORG001.</span></span>
 
## <a name="template-mapping-in-data-integrator"></a><span data-ttu-id="32906-164">Mapeamento de modelo no Integrador de dados</span><span class="sxs-lookup"><span data-stu-id="32906-164">Template mapping in Data integrator</span></span>

> [!NOTE]
> <span data-ttu-id="32906-165">**Condições de pagamento**, **Condições de frete**, **Condições de entrega**, **Método de remessa** e **Modo de entrega** fazem parte dos mapeamentos padrão.</span><span class="sxs-lookup"><span data-stu-id="32906-165">**Payment terms**, **Freight terms**, **Delivery terms**, **Shipping method**, and **Delivery mode** are not part of the default mappings.</span></span> <span data-ttu-id="32906-166">O mapeamento destes campos exige que o mapeamento de valor seja configurado, o que é específico para os dados nas organizações entre as quais a entidade deve ser sincronizada.</span><span class="sxs-lookup"><span data-stu-id="32906-166">Mapping of these fields requires value mapping to be set up, which is specific to the data in the organizations between which the entity is synchronized.</span></span>

<span data-ttu-id="32906-167">As seguintes ilustrações mostram um exemplo de um mapeamento de modelos no integrador de dados.</span><span class="sxs-lookup"><span data-stu-id="32906-167">The following illustrations show an example of a template mapping in data integrator.</span></span>

![Mapeamento de modelos no integrador de dados](./media/sales-invoice-template-mapping-data-integrator-1.png)

![Mapeamento de modelos no integrador de dados](./media/sales-invoice-template-mapping-data-integrator-2.png)

![Mapeamento de modelos no integrador de dados](./media/sales-invoice-template-mapping-data-integrator-3.png)

![Mapeamento de modelos no integrador de dados](./media/sales-invoice-template-mapping-data-integrator-4.png)


## <a name="related-topics"></a><span data-ttu-id="32906-172">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="32906-172">Related topics</span></span>

[<span data-ttu-id="32906-173">Sincronizar produtos do Finance and Operations com produtos do Sales</span><span class="sxs-lookup"><span data-stu-id="32906-173">Synchronize products from Finance and Operations to products in Sales</span></span>](products-template-mapping.md)

[<span data-ttu-id="32906-174">Sincronizar contas do Sales com clientes do Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="32906-174">Synchronize accounts from Sales to customers in Finance and Operations</span></span>](accounts-template-mapping.md)

[<span data-ttu-id="32906-175">Sincronizar contatos do Sales com contatos ou clientes do Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="32906-175">Synchronize contacts from Sales to contacts or customers in Finance and Operations</span></span>](contacts-template-mapping.md)

[<span data-ttu-id="32906-176">Sincronizar cabeçalhos e linhas de cotação de venda do Sales com o Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="32906-176">Synchronize sales quotation headers and lines from Sales to Finance and Operations</span></span>](sales-quotation-template-mapping.md)

[<span data-ttu-id="32906-177">Sincronizar cabeçalhos e linhas de ordem de venda do Finance and Operations com o Sales</span><span class="sxs-lookup"><span data-stu-id="32906-177">Synchronize sales order headers and lines from Finance and Operations to Sales</span></span>](sales-order-template-mapping.md)


