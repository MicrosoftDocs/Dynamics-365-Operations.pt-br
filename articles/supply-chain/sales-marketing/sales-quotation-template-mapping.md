---
title: "Sincronizar cabeçalhos e linhas de cotação de venda do Sales com o Finance and Operations"
description: "O tópico discute os modelos e as tarefas subjacentes que são usados para sincronizar cabeçalhos e linhas de cotação de venda do Microsoft Dynamics 365 for Sales com o Microsoft Dynamics 365 for Finance and Operations, edição Enterprise."
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
ms.sourcegitcommit: 029511634e56aec7fdd91bad9441cd12951fbd8d
ms.openlocfilehash: d34c808bce5b61b528f50224e3a72590476d8e55
ms.contentlocale: pt-br
ms.lasthandoff: 01/17/2018

---

# <a name="synchronize-sales-quotation-headers-and-lines-from-sales-to-finance-and-operations"></a><span data-ttu-id="d4430-103">Sincronizar cabeçalhos e linhas de cotação de venda do Sales com o Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="d4430-103">Synchronize sales quotation headers and lines from Sales to Finance and Operations</span></span>

[!include[banner](../includes/banner.md)]

> [!NOTE]
> <span data-ttu-id="d4430-104">Antes de usar a solução Prospect to cash, familiarize-se com a [Integração de dados do Dynamics 365](/common-data-service/entity-reference/dynamics-365-integration).</span><span class="sxs-lookup"><span data-stu-id="d4430-104">Before you can use the Prospect to cash solution, be familiar with [Dynamics 365 Data Integration](/common-data-service/entity-reference/dynamics-365-integration).</span></span> 

<span data-ttu-id="d4430-105">O tópico discute os modelos e as tarefas subjacentes que são usados para sincronizar cabeçalhos e linhas de cotação de venda do Microsoft Dynamics 365 for Sales (Sales) com o Microsoft Dynamics 365 for Finance and Operations, edição Enterprise (Finance and Operations).</span><span class="sxs-lookup"><span data-stu-id="d4430-105">The topic discusses the templates and underlying tasks that are used to synchronize sales quotation headers and lines from Microsoft Dynamics 365 for Sales (Sales) to Microsoft Dynamics 365 for Finance and Operations, Enterprise edition (Finance and Operations).</span></span> 

## <a name="template-and-tasks"></a><span data-ttu-id="d4430-106">Modelo e tarefas</span><span class="sxs-lookup"><span data-stu-id="d4430-106">Template and tasks</span></span>

<span data-ttu-id="d4430-107">Os modelos e as tarefas subjacentes a seguir são usados para sincronizar cabeçalhos e linhas de cotação de venda do Sales com o Finance and Operations:</span><span class="sxs-lookup"><span data-stu-id="d4430-107">The following templates and underlying tasks are used to synchronize sales quotation headers and lines from Sales to Finance and Operations:</span></span>

- <span data-ttu-id="d4430-108">**Nome do modelo:** Cotações de venda (Sales para Fin e Ops)</span><span class="sxs-lookup"><span data-stu-id="d4430-108">**Name of the template:** Sales Quotes (Sales to Fin and Ops)</span></span>
- <span data-ttu-id="d4430-109">**Nomes das tarefas no projeto:**</span><span class="sxs-lookup"><span data-stu-id="d4430-109">**Names of the tasks in the project:**</span></span>

    - <span data-ttu-id="d4430-110">QuoteHeader</span><span class="sxs-lookup"><span data-stu-id="d4430-110">QuoteHeader</span></span>
    - <span data-ttu-id="d4430-111">QuoteLine</span><span class="sxs-lookup"><span data-stu-id="d4430-111">QuoteLine</span></span>

<span data-ttu-id="d4430-112">As seguintes tarefas de sincronização são obrigatórias para que a sincronização de cabeçalhos e linhas de cotação de venda possa ocorrer:</span><span class="sxs-lookup"><span data-stu-id="d4430-112">The following synchronization tasks are required before synchronization of sales quotation headers and lines can occur:</span></span>

- <span data-ttu-id="d4430-113">Produtos (Fin and Ops para Sales)</span><span class="sxs-lookup"><span data-stu-id="d4430-113">Products (Fin and Ops to Sales)</span></span>
- <span data-ttu-id="d4430-114">Contas (Sales para Fin and Ops) (se usadas)</span><span class="sxs-lookup"><span data-stu-id="d4430-114">Accounts (Sales to Fin and Ops) (if used)</span></span>
- <span data-ttu-id="d4430-115">Contatos para Clientes (Sales com o Fin and Ops) (se usados)</span><span class="sxs-lookup"><span data-stu-id="d4430-115">Contacts to Customers (Sales to Fin and Ops) (if used)</span></span>

## <a name="entity-set"></a><span data-ttu-id="d4430-116">Conjunto de entidades</span><span class="sxs-lookup"><span data-stu-id="d4430-116">Entity set</span></span>

| <span data-ttu-id="d4430-117">Vendas</span><span class="sxs-lookup"><span data-stu-id="d4430-117">Sales</span></span>        | <span data-ttu-id="d4430-118">CDS</span><span class="sxs-lookup"><span data-stu-id="d4430-118">CDS</span></span>           | <span data-ttu-id="d4430-119">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="d4430-119">Finance and Operations</span></span>    |
|--------------|---------------|---------------------------|
| <span data-ttu-id="d4430-120">Cotações</span><span class="sxs-lookup"><span data-stu-id="d4430-120">Quotes</span></span>       | <span data-ttu-id="d4430-121">Cotação</span><span class="sxs-lookup"><span data-stu-id="d4430-121">Quotation</span></span>     | <span data-ttu-id="d4430-122">Cabeçalhos de cotação de venda</span><span class="sxs-lookup"><span data-stu-id="d4430-122">Sales quotation headers</span></span>   |
| <span data-ttu-id="d4430-123">QuoteDetails</span><span class="sxs-lookup"><span data-stu-id="d4430-123">QuoteDetails</span></span> | <span data-ttu-id="d4430-124">QuotationLine</span><span class="sxs-lookup"><span data-stu-id="d4430-124">QuotationLine</span></span> | <span data-ttu-id="d4430-125">Linhas de cotação de venda do CDS</span><span class="sxs-lookup"><span data-stu-id="d4430-125">CDS sales quotation lines</span></span> |

## <a name="entity-flow"></a><span data-ttu-id="d4430-126">Fluxo de entidades</span><span class="sxs-lookup"><span data-stu-id="d4430-126">Entity flow</span></span>

<span data-ttu-id="d4430-127">As cotações de vendas são criadas no Sales e sincronizadas ao Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="d4430-127">Sales quotations are created in Sales and synchronized to Finance and Operations.</span></span>

<span data-ttu-id="d4430-128">As cotações de vendas do Sales são sincronizadas somente se as seguintes condições forem atendidas:</span><span class="sxs-lookup"><span data-stu-id="d4430-128">Sales quotations from Sales are synchronized only if the following conditions are met:</span></span>

- <span data-ttu-id="d4430-129">Todos os produtos nas linhas de cotação de vendas são mantidas externamente.</span><span class="sxs-lookup"><span data-stu-id="d4430-129">All products on the sales quotation lines are externally maintained.</span></span>
- <span data-ttu-id="d4430-130">A cotação de venda está ativa ou ativada.</span><span class="sxs-lookup"><span data-stu-id="d4430-130">The sales quotation is active or activated.</span></span>

## <a name="prospect-to-cash-solution-for-sales"></a><span data-ttu-id="d4430-131">Solução Prospect to cash para o Sales</span><span class="sxs-lookup"><span data-stu-id="d4430-131">Prospect to cash solution for Sales</span></span>

<span data-ttu-id="d4430-132">O campo **Tem Somente Produtos Mantidos Externamente** foi adicionado à entidade Cotação para rastrear consistentemente se a cotação de vendas consiste totalmente de produtos mantidos externamente.</span><span class="sxs-lookup"><span data-stu-id="d4430-132">The **Has Externally Maintained Products Only** field has been added to the Quote entity to consistently track whether the sales quotation consists entirely of externally maintained products.</span></span> <span data-ttu-id="d4430-133">Se uma cotação de venda mantiver somente produtos externamente, os produtos serão mantidos no Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="d4430-133">If a sales quotation has only externally maintained products, the products are maintained in Finance and Operations.</span></span> <span data-ttu-id="d4430-134">Este comportamento ajuda a garantir que você não tente sincronizar linhas da cotação de vendas com produtos que são desconhecidos para Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="d4430-134">This behavior helps guarantee that you don't try to synchronize sales quotation lines with products that are unknown to Finance and Operations.</span></span>

<span data-ttu-id="d4430-135">Todos os produtos e linhas da cotação são atualizados com as informações **Tem Somente Produtos Mantidos Externamente** do cabeçalho de cotação.</span><span class="sxs-lookup"><span data-stu-id="d4430-135">All products and lines on the quotation are updated with the **Has Externally Maintained Products Only** information from the quotation header.</span></span> <span data-ttu-id="d4430-136">Essas informações podem ser encontradas no campo **A Cotação Tem Somente Produtos Mantidos Externamente** na entidade Linha de cotação.</span><span class="sxs-lookup"><span data-stu-id="d4430-136">This information can be found in the **Quote Has Externally Maintained Products Only** field on the Quote line entity.</span></span>

<span data-ttu-id="d4430-137">Os campos **Desconto**, **Encargos** e **Imposto** são controlados por uma configuração complexa no Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="d4430-137">The **Discount**, **Charges**, and **Tax** fields are controlled by a complex setup in Finance and Operations.</span></span> <span data-ttu-id="d4430-138">Essa configuração não suporta atualmente mapeamento de integração.</span><span class="sxs-lookup"><span data-stu-id="d4430-138">This setup doesn't currently support integration mapping.</span></span> <span data-ttu-id="d4430-139">No design atual, os campos **Preço**, **Desconto**, **Encargo** e **Imposto** são dominados e tratados pelo Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="d4430-139">In the current design, the **Price**, **Discount**, **Charge**, and **Tax** fields are mastered and handled by Finance and Operations.</span></span>

<span data-ttu-id="d4430-140">No Sales, a solução torna os seguintes campos somente para leitura, porque os valores não são sincronizados com o Finance and Operations:</span><span class="sxs-lookup"><span data-stu-id="d4430-140">In Sales, the solution makes the following fields read-only, because the values aren't synchronized to Finance and Operations:</span></span>

- <span data-ttu-id="d4430-141">**Campos somente leitura no cabeçalho de cotação de vendas:** % de Desconto, Desconto, Valor do Frete</span><span class="sxs-lookup"><span data-stu-id="d4430-141">**Read-only fields on the sales quotation header:** Discount %, Discount, Freight Amount</span></span>
- <span data-ttu-id="d4430-142">**Campos somente leitura nas linhas de cotação de venda:** Imposto</span><span class="sxs-lookup"><span data-stu-id="d4430-142">**Read-only fields on sales quotation lines:** Tax</span></span>

## <a name="preconditions-and-mapping-setup"></a><span data-ttu-id="d4430-143">Precondições e configuração de mapeamento</span><span class="sxs-lookup"><span data-stu-id="d4430-143">Preconditions and mapping setup</span></span>

<span data-ttu-id="d4430-144">Antes de sincronizar as ordens de venda, é importante atualizar os sistemas com a seguinte configuração:</span><span class="sxs-lookup"><span data-stu-id="d4430-144">Before synchronizing sales orders, it is important to update the systems with the following setting:</span></span>

### <a name="setup-in-sales"></a><span data-ttu-id="d4430-145">Configuração no Sales</span><span class="sxs-lookup"><span data-stu-id="d4430-145">Setup in Sales</span></span>

- <span data-ttu-id="d4430-146">Vá para **Configurações** &gt; **Administração** &gt; **Configurações do sistema** &gt; **Sales** e certifique-se de que o campo **Método de cálculo de desconto** esteja definido como **Por unidade**.</span><span class="sxs-lookup"><span data-stu-id="d4430-146">Go to **Settings** &gt; **Administration** &gt; **System settings** &gt; **Sales**, and make sure that the **Discount calculation method** field is set to **Per unit**.</span></span> <span data-ttu-id="d4430-147">Esta configuração ajuda a garantir que o desconto do item de linha do Sales corresponde à configuração no Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="d4430-147">This setting helps guarantee that the line item discount from Sales matches the setting in Finance and Operations.</span></span> <span data-ttu-id="d4430-148">Caso contrário, o desconto não será correto no Finance and Operations, porque o Finance and Operations irá ler o desconto como um desconto por unidade, mesmo se ele tiver um desconto por linha no Sales.</span><span class="sxs-lookup"><span data-stu-id="d4430-148">Otherwise, the discount won't be correct in Finance and Operations, because Finance and Operations will read the discount as a per-unit discount even if it was a per-line discount in Sales.</span></span>

### <a name="setup-in-finance-and-operations"></a><span data-ttu-id="d4430-149">Configuração no Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="d4430-149">Setup in Finance and Operations</span></span>

- <span data-ttu-id="d4430-150">Vá para **Contas a receber** &gt; **Configurar** &gt; **Parâmetros de contas a receber**.</span><span class="sxs-lookup"><span data-stu-id="d4430-150">Go to **Accounts receivable** &gt; **Setup** &gt; **Account receivable parameters**.</span></span> <span data-ttu-id="d4430-151">Na guia **Sequência numérica**, selecione a sequência numérica para cotações de venda, e clique em **Exibir detalhes**.</span><span class="sxs-lookup"><span data-stu-id="d4430-151">On the **Number sequence** tab, select the number sequence for sales quotations, and then click **View details**.</span></span> <span data-ttu-id="d4430-152">Em seguida, em **Configuração geral**, defina o campo **Manual** como **Sim**.</span><span class="sxs-lookup"><span data-stu-id="d4430-152">Then, under **General Setup**, set the **Manual** field to **Yes**.</span></span>
- <span data-ttu-id="d4430-153">Vá para **Contas a receber** &gt; **Configurar** &gt; **Parâmetros de contas a receber**.</span><span class="sxs-lookup"><span data-stu-id="d4430-153">Go to **Accounts receivable** &gt; **Setup** &gt; **Accounts receivable parameters**.</span></span> <span data-ttu-id="d4430-154">Em seguida, na guia **Remessas**, defina o campo **Controle da data de entrega** como **Nenhum**.</span><span class="sxs-lookup"><span data-stu-id="d4430-154">Then, on the **Shipments** tab, set the **Delivery date control** field to **None**.</span></span> <span data-ttu-id="d4430-155">Essa configuração ajuda a evitar que a sincronização falhe para cotações de venda.</span><span class="sxs-lookup"><span data-stu-id="d4430-155">This setting helps prevent synchronization from failing for sales quotations.</span></span>

### <a name="setup-in-the-data-integration-project"></a><span data-ttu-id="d4430-156">Configuração no Projeto de integração de dados</span><span class="sxs-lookup"><span data-stu-id="d4430-156">Setup in the Data integration project</span></span>

#### <a name="quoteheader"></a><span data-ttu-id="d4430-157">QuoteHeader</span><span class="sxs-lookup"><span data-stu-id="d4430-157">QuoteHeader</span></span>

- <span data-ttu-id="d4430-158">O campo **Data de entrega solicitada** é obrigatório no Finance and Operations e a sincronização falhará se o campo ficar em branco.</span><span class="sxs-lookup"><span data-stu-id="d4430-158">The **Requested delivery date** field is required in Finance and Operations, and synchronization will fail if the field is left blank.</span></span> <span data-ttu-id="d4430-159">Para evitar esse problema, se o campo estiver em branco, uma data padrão é obtida de **Origem &gt; CDS**.</span><span class="sxs-lookup"><span data-stu-id="d4430-159">To prevent this issue, if the field is blank, a default date is taken from **Source &gt; CDS**.</span></span> <span data-ttu-id="d4430-160">A data deve ser atualizada para um valor preferido.</span><span class="sxs-lookup"><span data-stu-id="d4430-160">The date should be updated to a preferred value.</span></span> <span data-ttu-id="d4430-161">Atualmente, não poderá inserir um valor como **Hoje** para representar a data de hoje.</span><span class="sxs-lookup"><span data-stu-id="d4430-161">Currently, you can't enter a value such as **Today** to represent today's date.</span></span> <span data-ttu-id="d4430-162">Você deve digitar uma data específica.</span><span class="sxs-lookup"><span data-stu-id="d4430-162">You must enter a specific date.</span></span> <span data-ttu-id="d4430-163">O valor do modelo padrão para **Data de entrega solicitada:** é **1/1/2020**.</span><span class="sxs-lookup"><span data-stu-id="d4430-163">The default template value for **Requested delivery date** is **1/1/2020**.</span></span>
- <span data-ttu-id="d4430-164">O **Código de região do país do endereço** é obrigatório no Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="d4430-164">The **Address Country region code** field is required in Finance and Operations.</span></span> <span data-ttu-id="d4430-165">Para ajudar a evitar erros de sincronização, você pode especificar um valor padrão a ser usado, se o campo ficar em branco no Sales.</span><span class="sxs-lookup"><span data-stu-id="d4430-165">To help prevent synchronization errors, you can specify a default value that is used if the field is left blank in Sales.</span></span> <span data-ttu-id="d4430-166">Esse valor padrão também é útil, porque você não precisa inserir um valor manualmente no campo **País/região** para endereços locais.</span><span class="sxs-lookup"><span data-stu-id="d4430-166">This default value is also useful, because you don't have to manually enter a value in the **Country region** field for local addresses.</span></span> <span data-ttu-id="d4430-167">Não há valor do modelo padrão para **DeliveryAddressCountryRegionISOCode**.</span><span class="sxs-lookup"><span data-stu-id="d4430-167">There is no default template value for **DeliveryAddressCountryRegionISOCode**.</span></span>
- <span data-ttu-id="d4430-168">Atualize o mapeamento para **ID da Organização CDS** em **Fonte &gt; CDS**, de forma que ele corresponda a **Organização CDS** na entidade da Organização:</span><span class="sxs-lookup"><span data-stu-id="d4430-168">Update the mapping for **CDS Organization ID** in **Source &gt; CDS** so that it matches **CDS organization** in the Organization entity:</span></span>

    - <span data-ttu-id="d4430-169">O valor do modelo padrão para **Organization_OrganizationId** é **ORG001**.</span><span class="sxs-lookup"><span data-stu-id="d4430-169">The default template value for **Organization_OrganizationId** is **ORG001**.</span></span>
    - <span data-ttu-id="d4430-170">O valor do modelo padrão para **Account_Organization_OrganizationId** é **ORG001**.</span><span class="sxs-lookup"><span data-stu-id="d4430-170">The default template value for **Account_Organization_OrganizationId** is **ORG001**.</span></span>
    - <span data-ttu-id="d4430-171">O valor do modelo padrão para **InvoiceAccount_OrganizationId** é **ORG001**.</span><span class="sxs-lookup"><span data-stu-id="d4430-171">The default template value for **InvoiceAccount_OrganizationId** is **ORG001**.</span></span>

#### <a name="quoteline"></a><span data-ttu-id="d4430-172">QuoteLine</span><span class="sxs-lookup"><span data-stu-id="d4430-172">QuoteLine</span></span>

- <span data-ttu-id="d4430-173">Atualize o mapeamento para **ID da Organização CDS** em **Fonte &gt; CDS**, de forma que ele corresponda a **Organização CDS** na entidade da Organização:</span><span class="sxs-lookup"><span data-stu-id="d4430-173">Update the mapping for **CDS Organization ID** in **Source &gt; CDS** so that it matches **CDS organization** in the Organization entity:</span></span>

    - <span data-ttu-id="d4430-174">O valor do modelo padrão para **Organization_OrganizationId** é **ORG001**.</span><span class="sxs-lookup"><span data-stu-id="d4430-174">The default template value for **Organization_OrganizationId** is **ORG001**.</span></span>
    - <span data-ttu-id="d4430-175">O valor do modelo padrão para **Product_Organization_Organization_OrganizationId** é **ORG001**.</span><span class="sxs-lookup"><span data-stu-id="d4430-175">The default template value for **Product_Organization_Organization_OrganizationId** is **ORG001**.</span></span>
    - <span data-ttu-id="d4430-176">O valor do modelo padrão para **Quotation_Organization_Organization_OrganizationId** é **ORG001**.</span><span class="sxs-lookup"><span data-stu-id="d4430-176">The default template value for **Quotation_Organization_Organization_OrganizationId** is **ORG001**.</span></span>

- <span data-ttu-id="d4430-177">O campo **Data de entrega solicitada** é obrigatório no Finance and Operations e a sincronização falhará se o campo ficar em branco.</span><span class="sxs-lookup"><span data-stu-id="d4430-177">The **Requested delivery date** field is required in Finance and Operations, and synchronization will fail if the field is left blank.</span></span> <span data-ttu-id="d4430-178">Para evitar esse problema, se o campo estiver em branco, uma data padrão é obtida de **Origem &gt; CDS**.</span><span class="sxs-lookup"><span data-stu-id="d4430-178">To prevent this issue, if the field is blank, a default date is taken from **Source &gt; CDS**.</span></span> <span data-ttu-id="d4430-179">A data deve ser atualizada para um valor preferido.</span><span class="sxs-lookup"><span data-stu-id="d4430-179">The date should be updated to a preferred value.</span></span> <span data-ttu-id="d4430-180">Atualmente, não poderá inserir um valor como **Hoje** para representar a data de hoje.</span><span class="sxs-lookup"><span data-stu-id="d4430-180">Currently, you can't enter a value such as **Today** to represent today's date.</span></span> <span data-ttu-id="d4430-181">Você deve digitar uma data específica.</span><span class="sxs-lookup"><span data-stu-id="d4430-181">You must enter a specific date.</span></span> <span data-ttu-id="d4430-182">O valor do modelo padrão para **Data de entrega solicitada:** é **1/1/2020**.</span><span class="sxs-lookup"><span data-stu-id="d4430-182">The default template value for **Requested delivery date** is **1/1/2020**.</span></span>
- <span data-ttu-id="d4430-183">Você pode adicionar os seguintes mapeamentos de **CDS &gt; Destino** para ajudar a garantir que as linhas de cotação serão importadas para Finance and Operations, se não houver informações padrão do cliente ou do produto:</span><span class="sxs-lookup"><span data-stu-id="d4430-183">You can add the following mappings from **CDS &gt; Destination** to help guarantee that quotation lines are imported into Finance and Operations if there is no default information from either the customer or the product:</span></span>

    - <span data-ttu-id="d4430-184">**SiteId** – Um site é necessário para gerar cotações e linhas da ordem de venda no Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="d4430-184">**SiteId** – A site is required in order to generate quotations and sales order lines in Finance and Operations.</span></span> <span data-ttu-id="d4430-185">Não há valor do modelo padrão para **SiteId**.</span><span class="sxs-lookup"><span data-stu-id="d4430-185">There is no default template value for **SiteId**.</span></span>
    - <span data-ttu-id="d4430-186">**WarehouseId** – Um depósito é necessário para processar cotações e linhas da ordem de venda no Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="d4430-186">**WarehouseId** – A warehouse is required in order to process quotations and sales order lines in Finance and Operations.</span></span> <span data-ttu-id="d4430-187">Não há valor do modelo padrão para **WarehouseId**.</span><span class="sxs-lookup"><span data-stu-id="d4430-187">There is no default template value for **WarehouseId**.</span></span>

- <span data-ttu-id="d4430-188">Certifique-se de que existe o mapa de valor obrigatório para a unidade de medida (UDM) de vendas no Finance and Operations no mapeamento de **CDS &gt; Destino** para **Quantity_UOM** para **SALESUNITSYMBOL**.</span><span class="sxs-lookup"><span data-stu-id="d4430-188">Make sure that the required value map for the selling unit of measure (UOM) in Finance and Operations exists in the **CDS &gt; Destination** mapping for **Quantity_UOM** to **SALESUNITSYMBOL**.</span></span>

## <a name="template-mapping-in-data-integrator"></a><span data-ttu-id="d4430-189">Mapeamento de modelos no integrador de dados</span><span class="sxs-lookup"><span data-stu-id="d4430-189">Template mapping in data integrator</span></span>

> [!NOTE]
> - <span data-ttu-id="d4430-190">Os campos **Desconto**, **Encargos** e **Imposto** são controlados por uma configuração complexa no Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="d4430-190">The **Discount**, **Charges**, and **Tax** fields are controlled by a complex setup in Finance and Operations.</span></span> <span data-ttu-id="d4430-191">Essa configuração não suporta atualmente mapeamento de integração.</span><span class="sxs-lookup"><span data-stu-id="d4430-191">This setup doesn't currently support integration mapping.</span></span> <span data-ttu-id="d4430-192">No design atual, os campos **Preço**, **Desconto**, **Encargo** e **Imposto** são tratados pelo Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="d4430-192">In the current design, the **Price**, **Discount**, **Charge**, and **Tax** fields are handled by Finance and Operations.</span></span>
> - <span data-ttu-id="d4430-193">Os campos **Termos de pagamento**, **Condições de frete**, **Condições de entrega**, **Método de entrega** e **Modo de entrega** não estão incluídos no mapeamento padrão.</span><span class="sxs-lookup"><span data-stu-id="d4430-193">The **Payment terms**, **Freight terms**, **Delivery terms**, **Shipping method**, and **Delivery mode** fields aren't part of the default mappings.</span></span> <span data-ttu-id="d4430-194">Para mapear esses campos, é necessário configurar um mapeamento de valor que é específico para os dados nas organizações às quais a entidade está sincronizada.</span><span class="sxs-lookup"><span data-stu-id="d4430-194">To map these fields, you must set up a value mapping that is specific to the data in the organizations that the entity is synchronized between.</span></span>

<span data-ttu-id="d4430-195">As seguintes ilustrações mostram um exemplo de um mapeamento de modelos no integrador de dados.</span><span class="sxs-lookup"><span data-stu-id="d4430-195">The following illustrations show an example of a template mapping in data integrator.</span></span>

### <a name="quoteheader"></a><span data-ttu-id="d4430-196">QuoteHeader</span><span class="sxs-lookup"><span data-stu-id="d4430-196">QuoteHeader</span></span>

![Mapeamento de modelos no integrador de dados](./media/sales-quotation-template-mapping-data-integrator-1.png)

![Mapeamento de modelos no integrador de dados](./media/sales-quotation-template-mapping-data-integrator-2.png)

### <a name="quoteline"></a><span data-ttu-id="d4430-199">QuoteLine</span><span class="sxs-lookup"><span data-stu-id="d4430-199">QuoteLine</span></span>

![Mapeamento de modelos no integrador de dados](./media/sales-quotation-template-mapping-data-integrator-3.png)

![Mapeamento de modelos no integrador de dados](./media/sales-quotation-template-mapping-data-integrator-4.png)

## <a name="related-topics"></a><span data-ttu-id="d4430-202">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="d4430-202">Related topics</span></span>

[<span data-ttu-id="d4430-203">Sincronizar produtos do Finance and Operations com produtos do Sales</span><span class="sxs-lookup"><span data-stu-id="d4430-203">Synchronize products from Finance and Operations to products in Sales</span></span>](products-template-mapping.md)

[<span data-ttu-id="d4430-204">Sincronizar contas do Sales com clientes do Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="d4430-204">Synchronize accounts from Sales to customers in Finance and Operations</span></span>](accounts-template-mapping.md)

[<span data-ttu-id="d4430-205">Sincronizar contatos do Sales com contatos ou clientes do Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="d4430-205">Synchronize contacts from Sales to contacts or customers in Finance and Operations</span></span>](contacts-template-mapping.md)



