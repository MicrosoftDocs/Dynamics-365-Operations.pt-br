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
# <a name="synchronize-sales-invoice-headers-and-lines-directly-from-finance-and-operations-to-sales"></a><span data-ttu-id="38bc9-103">Sincronizar cabeçalhos e linhas da fatura de venda diretamente do Finance and Operations para o Sales</span><span class="sxs-lookup"><span data-stu-id="38bc9-103">Synchronize sales invoice headers and lines directly from Finance and Operations to Sales</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="38bc9-104">Este tópico discute os modelos e as tarefas subjacentes que são usados para sincronizar cabeçalhos e linhas de fatura de venda diretamente do Dynamics 365 Supply Chain Management para o Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="38bc9-104">This topic discusses the templates and underlying tasks that are used to synchronize sales invoice headers and lines directly from Dynamics 365 Supply Chain Management to Dynamics 365 Sales.</span></span>

## <a name="data-flow-in-prospect-to-cash"></a><span data-ttu-id="38bc9-105">Fluxo de dados no Prospect to cash</span><span class="sxs-lookup"><span data-stu-id="38bc9-105">Data flow in Prospect to cash</span></span>

<span data-ttu-id="38bc9-106">A solução Prospect to cash usa o recurso Integração de dados para sincronizar dados entre as instâncias Supply Chain Management e do Sales.</span><span class="sxs-lookup"><span data-stu-id="38bc9-106">The Prospect to cash solution uses the Data integration feature to synchronize data across instances of Supply Chain Management and Sales.</span></span> <span data-ttu-id="38bc9-107">Os modelos de Prospect to cash que estão disponíveis com o recurso Integração de dados permitem o fluxo de dados sobre contas, contatos, produtos, cotações de venda, ordens de venda e faturas de venda entre o Supply Chain Management e o Sales.</span><span class="sxs-lookup"><span data-stu-id="38bc9-107">The Prospect to cash templates that are available with the Data integration feature enable the flow of data about accounts, contacts, products, sales quotations, sales orders, and sales invoices between Supply Chain Management and Sales.</span></span> <span data-ttu-id="38bc9-108">A ilustração a seguir mostra como os dados são sincronizados entre o Supply Chain Management e o Sales.</span><span class="sxs-lookup"><span data-stu-id="38bc9-108">The following illustration shows how the data is synchronized between Supply Chain Management and Sales.</span></span>

<span data-ttu-id="38bc9-109">[![Fluxo de dados em Prospect to cash](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)</span><span class="sxs-lookup"><span data-stu-id="38bc9-109">[![Data flow in Prospect to cash](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="38bc9-110">Modelos e tarefas</span><span class="sxs-lookup"><span data-stu-id="38bc9-110">Templates and tasks</span></span>

<span data-ttu-id="38bc9-111">Para acessar os modelos disponíveis, abra o [Centro de administração do PowerApps](https://preview.admin.powerapps.com/dataintegration).</span><span class="sxs-lookup"><span data-stu-id="38bc9-111">To access the available templates, open [PowerApps Admin Center](https://preview.admin.powerapps.com/dataintegration).</span></span> <span data-ttu-id="38bc9-112">Selecione **Projetos** e, no canto superior direito, selecione **Novo projeto** para selecionar modelos públicos.</span><span class="sxs-lookup"><span data-stu-id="38bc9-112">Select **Projects**, and then, in the upper-right corner, select **New project** to select public templates.</span></span>

<span data-ttu-id="38bc9-113">O seguinte modelo e as tarefas subjacentes são usados para sincronizar cabeçalhos e linhas da fatura de venda diretamente do Supply Chain Management para o Sales:</span><span class="sxs-lookup"><span data-stu-id="38bc9-113">The following template and underlying tasks are used to synchronize sales invoice headers and lines from Supply Chain Management to Sales:</span></span>

- <span data-ttu-id="38bc9-114">**Nome do modelo na Integração de dados:** faturas de venda (Fin and Ops para Sales) – Direto</span><span class="sxs-lookup"><span data-stu-id="38bc9-114">**Name of the template in Data integration:** Sales Invoices (Fin and Ops to Sales) - Direct</span></span>
- <span data-ttu-id="38bc9-115">**Nomes das tarefas no projeto de Integração de dados:**</span><span class="sxs-lookup"><span data-stu-id="38bc9-115">**Names of the tasks in the Data integration project:**</span></span>

    - <span data-ttu-id="38bc9-116">SalesInvoiceHeader</span><span class="sxs-lookup"><span data-stu-id="38bc9-116">SalesInvoiceHeader</span></span>
    - <span data-ttu-id="38bc9-117">SalesInvoiceLine</span><span class="sxs-lookup"><span data-stu-id="38bc9-117">SalesInvoiceLine</span></span>

<span data-ttu-id="38bc9-118">As seguintes tarefas de sincronização são obrigatórias para que a sincronização de cabeçalhos e linhas de fatura de venda possa ocorrer:</span><span class="sxs-lookup"><span data-stu-id="38bc9-118">The following synchronization tasks are required before synchronization of sales invoice headers and lines can occur:</span></span>

- <span data-ttu-id="38bc9-119">Produtos (Supply Chain Management para Sales) – Direto</span><span class="sxs-lookup"><span data-stu-id="38bc9-119">Products (Supply Chain Management to Sales) - Direct</span></span>
- <span data-ttu-id="38bc9-120">Contas (Sales para Supply Chain Management) – Direto (se usado)</span><span class="sxs-lookup"><span data-stu-id="38bc9-120">Accounts (Sales to Supply Chain Management) - Direct (if used)</span></span>
- <span data-ttu-id="38bc9-121">Contatos (Sales para Supply Chain Management) – Direto (se usado)</span><span class="sxs-lookup"><span data-stu-id="38bc9-121">Contacts (Sales to Supply Chain Management) - Direct (if used)</span></span>
- <span data-ttu-id="38bc9-122">Cabeçalhos e linhas da ordem de venda (Supply Chain Management para Sales) - Direto</span><span class="sxs-lookup"><span data-stu-id="38bc9-122">Sales order header and lines (Supply Chain Management to Sales) - Direct</span></span>

## <a name="entity-set"></a><span data-ttu-id="38bc9-123">Conjunto de entidades</span><span class="sxs-lookup"><span data-stu-id="38bc9-123">Entity set</span></span>

| <span data-ttu-id="38bc9-124">Gerenciamento da Cadeia de Fornecedores</span><span class="sxs-lookup"><span data-stu-id="38bc9-124">Supply Chain Management</span></span>                              | <span data-ttu-id="38bc9-125">Vendas</span><span class="sxs-lookup"><span data-stu-id="38bc9-125">Sales</span></span>          |
|------------------------------------------------------|----------------|
| <span data-ttu-id="38bc9-126">Cabeçalhos de faturas de vendas de cliente mantidas externamente</span><span class="sxs-lookup"><span data-stu-id="38bc9-126">Externally maintained customer sales invoice headers</span></span> | <span data-ttu-id="38bc9-127">Faturas</span><span class="sxs-lookup"><span data-stu-id="38bc9-127">Invoices</span></span>       |
| <span data-ttu-id="38bc9-128">Linhas de faturas de vendas de cliente mantidas externamente</span><span class="sxs-lookup"><span data-stu-id="38bc9-128">Externally maintained customer sales invoice lines</span></span>   | <span data-ttu-id="38bc9-129">InvoiceDetails</span><span class="sxs-lookup"><span data-stu-id="38bc9-129">InvoiceDetails</span></span> |

## <a name="entity-flow"></a><span data-ttu-id="38bc9-130">Fluxo de entidades</span><span class="sxs-lookup"><span data-stu-id="38bc9-130">Entity flow</span></span>

<span data-ttu-id="38bc9-131">As faturas de vendas são criadas no Supply Chain Management e sincronizadas no Sales.</span><span class="sxs-lookup"><span data-stu-id="38bc9-131">Sales invoices are created in Supply Chain Management and synchronized to Sales.</span></span>

> [!NOTE]
> <span data-ttu-id="38bc9-132">Atualmente, o imposto que está relacionado aos encargos no cabeçalho da fatura de venda não é incluído na sincronização do Supply Chain Management para o Sales.</span><span class="sxs-lookup"><span data-stu-id="38bc9-132">Currently, tax that is related to charges on the sales invoice header isn't included in the synchronization from Supply Chain Managements to Sales.</span></span> <span data-ttu-id="38bc9-133">O Sales não dá suporte às informações de imposto em nível de cabeçalho.</span><span class="sxs-lookup"><span data-stu-id="38bc9-133">Sales doesn't support tax information at the header level.</span></span> <span data-ttu-id="38bc9-134">Entretanto, impostos relativos aos encargos em nível de linha são incluídos na sincronização.</span><span class="sxs-lookup"><span data-stu-id="38bc9-134">However, tax that is related to charges at the line level is included in the synchronization.</span></span>

## <a name="prospect-to-cash-solution-for-sales"></a><span data-ttu-id="38bc9-135">Solução Prospect to cash para o Sales</span><span class="sxs-lookup"><span data-stu-id="38bc9-135">Prospect to cash solution for Sales</span></span>

- <span data-ttu-id="38bc9-136">Um campo **Número de fatura** foi adicionado à entidade **Fatura** e aparece na página.</span><span class="sxs-lookup"><span data-stu-id="38bc9-136">An **Invoice number** field has been added to the **Invoice** entity and appears on the page.</span></span>
- <span data-ttu-id="38bc9-137">O botão **Criar fatura** na página **Ordem de venda** é ocultado, pois as faturas serão criadas no Supply Chain Management e sincronizadas com o Sales.</span><span class="sxs-lookup"><span data-stu-id="38bc9-137">The **Create invoice** button on the **Sales order** page is hidden, because invoices will be created in Supply Chain Management and synchronized to Sales.</span></span> <span data-ttu-id="38bc9-138">A página **Fatura** não pode ser editada, pois as faturas serão sincronizadas do Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="38bc9-138">The **Invoice** page can't be edited, because invoices will be synchronized from Supply Chain Management.</span></span>
- <span data-ttu-id="38bc9-139">O valor do **Status da ordem de venda** é alterado automaticamente para **Faturado** quando a fatura relacionada do Supply Chain Management é sincronizada com o Sales.</span><span class="sxs-lookup"><span data-stu-id="38bc9-139">The **Sales order status** value is automatically changed to **Invoiced** when the related invoice from Supply Chain Management has been synchronized to Sales.</span></span> <span data-ttu-id="38bc9-140">Além disso, o proprietário da ordem de venda da qual a fatura foi criada é atribuído como o proprietário da fatura.</span><span class="sxs-lookup"><span data-stu-id="38bc9-140">Additionally, the owner of the sales order that the invoice was created from is assigned as the owner of the invoice.</span></span> <span data-ttu-id="38bc9-141">Portanto, o proprietário da ordem de venda pode exibir a fatura.</span><span class="sxs-lookup"><span data-stu-id="38bc9-141">Therefore, the owner of the sales order can view the invoice.</span></span>

## <a name="preconditions-and-mapping-setup"></a><span data-ttu-id="38bc9-142">Precondições e configuração de mapeamento</span><span class="sxs-lookup"><span data-stu-id="38bc9-142">Preconditions and mapping setup</span></span>

<span data-ttu-id="38bc9-143">Antes de sincronizar faturas de venda, é importante atualizar as configurações a seguir nos sistemas.</span><span class="sxs-lookup"><span data-stu-id="38bc9-143">Before you synchronize sales invoices, it's important that you update the following settings in the systems.</span></span>

### <a name="setup-in-sales"></a><span data-ttu-id="38bc9-144">Configuração no Sales</span><span class="sxs-lookup"><span data-stu-id="38bc9-144">Setup in Sales</span></span>

<span data-ttu-id="38bc9-145">Vá para **Configurações** > **Administração** > **Configurações do sistema** > **Sales** e verifique se as seguintes configurações foram usadas:</span><span class="sxs-lookup"><span data-stu-id="38bc9-145">Go to **Settings** > **Administration** > **System settings** > **Sales**, and make sure that the following settings are used:</span></span>

- <span data-ttu-id="38bc9-146">A opção **Usar sistema de cálculo de precificação do sistema** está definida como **Sim**.</span><span class="sxs-lookup"><span data-stu-id="38bc9-146">The **Use system prizing calculation system** option is set to **Yes**.</span></span>
- <span data-ttu-id="38bc9-147">O campo **Método de cálculo de desconto** está definido como **Item de linha**.</span><span class="sxs-lookup"><span data-stu-id="38bc9-147">The **Discount calculation method** field is set to **Line item**.</span></span>

### <a name="setup-in-the-data-integration-project"></a><span data-ttu-id="38bc9-148">Configuração no Projeto de integração de dados</span><span class="sxs-lookup"><span data-stu-id="38bc9-148">Setup in the Data integration project</span></span>

#### <a name="salesinvoiceheader-task"></a><span data-ttu-id="38bc9-149">tarefa SalesInvoiceHeader</span><span class="sxs-lookup"><span data-stu-id="38bc9-149">SalesInvoiceHeader task</span></span>

- <span data-ttu-id="38bc9-150">Verifique se há o mapeamento exigido para **InvoiceCountryRegionId** como **BillingAddress\_Country**.</span><span class="sxs-lookup"><span data-stu-id="38bc9-150">Make sure that the required mapping exists for **InvoiceCountryRegionId** to **BillingAddress\_Country**.</span></span>

    <span data-ttu-id="38bc9-151">O valor do modelo é um mapa de valores em que vários países ou regiões são mapeados.</span><span class="sxs-lookup"><span data-stu-id="38bc9-151">The template value is a value map where several countries or regions are mapped.</span></span>

- <span data-ttu-id="38bc9-152">Uma lista de preços é necessária para criar faturas no Sales.</span><span class="sxs-lookup"><span data-stu-id="38bc9-152">A price list is required in order to create invoices in Sales.</span></span> <span data-ttu-id="38bc9-153">Atualize o mapa de valores para **pricelevelid.name \[Price list name\]** para a lista de preços que é usada no Sales por moeda.</span><span class="sxs-lookup"><span data-stu-id="38bc9-153">Update the value map for **pricelevelid.name \[Price list name\]** to the price list that is used in Sales per currency.</span></span> <span data-ttu-id="38bc9-154">Você pode usar a lista de preços padrão para uma única moeda.</span><span class="sxs-lookup"><span data-stu-id="38bc9-154">You can use the default price list for a single currency.</span></span> <span data-ttu-id="38bc9-155">Caso existam listas de preços em várias moedas, você poderá usar um mapa de valores.</span><span class="sxs-lookup"><span data-stu-id="38bc9-155">Alternatively, if you have price lists in multiple currencies, you can use a value map.</span></span>

    <span data-ttu-id="38bc9-156">O valor do método de **pricelevelid.name \[Price list name\]** é um mapa de valores baseado na moeda com USD = Serviço CRM USA (amostra).</span><span class="sxs-lookup"><span data-stu-id="38bc9-156">The template value for **pricelevelid.name \[Price list name\]** is a value map that is based on currency with USD = CRM Service USA (sample).</span></span>  
    
#### <a name="salesinvoiceline-task"></a><span data-ttu-id="38bc9-157">Tarefa SalesInvoiceLine</span><span class="sxs-lookup"><span data-stu-id="38bc9-157">SalesInvoiceLine task</span></span>

- <span data-ttu-id="38bc9-158">Verifique se há o mapeamento exigido de **Unidade de medida**.</span><span class="sxs-lookup"><span data-stu-id="38bc9-158">Make sure that the required mapping exists for **Unit of measure**.</span></span>
- <span data-ttu-id="38bc9-159">Verifique se existe o mapa de valores necessário para **SalesUnitSymbol** no Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="38bc9-159">Make sure that the required value map for **SalesUnitSymbol** in Supply Chain Management exists.</span></span>

    <span data-ttu-id="38bc9-160">Um valor do modelo que tem um mapa de valores é definido para **SalesUnitSymbol** como **Quantity\_UOM**.</span><span class="sxs-lookup"><span data-stu-id="38bc9-160">A template value that has a value map is defined for **SalesUnitSymbol** to **Quantity\_UOM**.</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="38bc9-161">Mapeamento de modelo na Integração de dados</span><span class="sxs-lookup"><span data-stu-id="38bc9-161">Template mapping in Data integration</span></span>

> [!NOTE]
> <span data-ttu-id="38bc9-162">Os campos **Termos de pagamento**, **Condições de frete**, **Condições de entrega**, **Método de remessa** e **Modo de entrega** não estão incluídos no mapeamento padrão.</span><span class="sxs-lookup"><span data-stu-id="38bc9-162">The **Payment terms**, **Freight terms**, **Delivery terms**, **Shipping method**, and **Delivery mode** fields aren't included in the default mappings.</span></span> <span data-ttu-id="38bc9-163">Para mapear esses campos, é necessário configurar um mapeamento de valor que é específico para os dados nas organizações às quais a entidade está sincronizada.</span><span class="sxs-lookup"><span data-stu-id="38bc9-163">To map these fields, you must set up a value mapping that is specific to the data in the organizations that the entity is synchronized between.</span></span>

<span data-ttu-id="38bc9-164">As ilustrações a seguir mostram um exemplo de um mapeamento de modelo na Integração de dados.</span><span class="sxs-lookup"><span data-stu-id="38bc9-164">The following illustrations show an example of a template mapping in Data integration.</span></span> 

> [!NOTE]
> <span data-ttu-id="38bc9-165">O mapeamento mostra quais informações de campo serão sincronizadas do Sales com o Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="38bc9-165">The mapping shows which field information will be synchronized from Sales to Supply Chain Management.</span></span>

### <a name="salesinvoiceheader"></a><span data-ttu-id="38bc9-166">SalesInvoiceHeader</span><span class="sxs-lookup"><span data-stu-id="38bc9-166">SalesInvoiceHeader</span></span>

![Mapeamento de modelo na Integração de dados](./media/sales-invoice-direct-template-mapping-data-integrator-1.png)

### <a name="salesinvoiceline"></a><span data-ttu-id="38bc9-168">SalesInvoiceLine</span><span class="sxs-lookup"><span data-stu-id="38bc9-168">SalesInvoiceLine</span></span>

![Mapeamento de modelo na Integração de dados](./media/sales-invoice-direct-template-mapping-data-integrator-2.png)



## <a name="related-topics"></a><span data-ttu-id="38bc9-170">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="38bc9-170">Related topics</span></span>

[<span data-ttu-id="38bc9-171">Cliente potencial ao pagamento à vista</span><span class="sxs-lookup"><span data-stu-id="38bc9-171">Prospect to cash</span></span>](prospect-to-cash.md)

[<span data-ttu-id="38bc9-172">Sincronizar contas diretamente do Sales com clientes no Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="38bc9-172">Synchronize accounts directly from Sales to customers in Supply Chain Management</span></span>](accounts-template-mapping-direct.md)

[<span data-ttu-id="38bc9-173">Sincronizar produtos diretamente do Supply Chain Management com produtos do Sales</span><span class="sxs-lookup"><span data-stu-id="38bc9-173">Synchronize products directly from Supply Chain Management to products in Sales</span></span>](products-template-mapping-direct.md)

[<span data-ttu-id="38bc9-174">Sincronizar contatos diretamente do Sales com contatos ou clientes do Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="38bc9-174">Synchronize contacts directly from Sales to contacts or customers in Supply Chain Management</span></span>](contacts-template-mapping-direct.md)

[<span data-ttu-id="38bc9-175">Sincronizar cabeçalhos e linhas da ordem de venda diretamente do Supply Chain Management com o Sales</span><span class="sxs-lookup"><span data-stu-id="38bc9-175">Synchronize sales order headers and lines directly from Supply Chain Management to Sales</span></span>](sales-order-template-mapping-direct-two-ways.md)
