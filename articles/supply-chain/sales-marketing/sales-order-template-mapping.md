---
title: "Sincronizar cabeçalhos e linhas de ordem de venda do Finance and Operations com o Sales"
description: "O tópico discute os modelos e as tarefas subjacentes que são usados para sincronizar cabeçalhos e linhas de ordem de venda do Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition com o Microsoft Dynamics 365 for Sales."
author: ChristianRytt
manager: AnnBe
ms.date: 10/26/2017
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
ms.openlocfilehash: d7e4c435a3344f6a5d66e1889b633d80cda085eb
ms.contentlocale: pt-br
ms.lasthandoff: 01/17/2018

---

# <a name="synchronize-sales-order-headers-and-lines-from-finance-and-operations-to-sales"></a><span data-ttu-id="9d407-103">Sincronizar cabeçalhos e linhas de ordem de venda do Finance and Operations com o Sales</span><span class="sxs-lookup"><span data-stu-id="9d407-103">Synchronize sales order headers and lines from Finance and Operations to Sales</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="9d407-104">O tópico discute os modelos e as tarefas subjacentes que são usados para sincronizar cabeçalhos e linhas de ordem de venda do Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition com o Microsoft Dynamics 365 for Sales.</span><span class="sxs-lookup"><span data-stu-id="9d407-104">The topic discusses the templates and underlying tasks that are used to synchronize sales order headers and lines from Microsoft Dynamics 365 for Finance and Operations, Enterprise edition to Microsoft Dynamics 365 for Sales.</span></span> 

## <a name="template-and-tasks"></a><span data-ttu-id="9d407-105">Modelo e tarefas</span><span class="sxs-lookup"><span data-stu-id="9d407-105">Template and tasks</span></span>

<span data-ttu-id="9d407-106">Os modelos e as tarefas subjacentes a seguir são usados para sincronizar cabeçalhos e linhas da ordem de venda do Finance and Operations com o Sales:</span><span class="sxs-lookup"><span data-stu-id="9d407-106">The following templates and underlying tasks are used to synchronize sales order headers and lines from Finance and Operations to Sales:</span></span>

- <span data-ttu-id="9d407-107">**Nome do modelo na Integração de dados**</span><span class="sxs-lookup"><span data-stu-id="9d407-107">**Name of template in Data integration**</span></span> 

    - <span data-ttu-id="9d407-108">Ordens de vendas (Fin and Ops com Sales)</span><span class="sxs-lookup"><span data-stu-id="9d407-108">Sales Orders (Fin and Ops to Sales)</span></span>
    
- <span data-ttu-id="9d407-109">**Nomes das tarefas no projeto de Integração de dados**</span><span class="sxs-lookup"><span data-stu-id="9d407-109">**Names of tasks in Data integration project**</span></span>

    - <span data-ttu-id="9d407-110">OrderHeader</span><span class="sxs-lookup"><span data-stu-id="9d407-110">OrderHeader</span></span>
    - <span data-ttu-id="9d407-111">OrderLine</span><span class="sxs-lookup"><span data-stu-id="9d407-111">OrderLine</span></span>

<span data-ttu-id="9d407-112">As tarefas de sincronização necessárias antes da sincronização do cabeçalho e das linhas da fatura do Sales:</span><span class="sxs-lookup"><span data-stu-id="9d407-112">Sync tasks required prior to Sales invoice header and lines sync:</span></span>

- <span data-ttu-id="9d407-113">Produtos (Fin and Ops para Sales)</span><span class="sxs-lookup"><span data-stu-id="9d407-113">Products (Fin and Ops to Sales)</span></span>
- <span data-ttu-id="9d407-114">Contas (Sales para Fin and Ops) (se usadas)</span><span class="sxs-lookup"><span data-stu-id="9d407-114">Accounts (Sales to Fin and Ops) (if used)</span></span>
- <span data-ttu-id="9d407-115">Contatos para Clientes (Sales com o Fin and Ops) (se usados)</span><span class="sxs-lookup"><span data-stu-id="9d407-115">Contacts to Customers (Sales to Fin and Ops) (if used)</span></span>

## <a name="entity-set"></a><span data-ttu-id="9d407-116">Conjunto de entidades</span><span class="sxs-lookup"><span data-stu-id="9d407-116">Entity set</span></span>

| <span data-ttu-id="9d407-117">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="9d407-117">Finance and Operations</span></span> |    <span data-ttu-id="9d407-118">Common Data Service (CDS)</span><span class="sxs-lookup"><span data-stu-id="9d407-118">Common Data Service (CDS)</span></span>         |     <span data-ttu-id="9d407-119">Vendas</span><span class="sxs-lookup"><span data-stu-id="9d407-119">Sales</span></span>      |
|------------------------|----------------|----------------|
| <span data-ttu-id="9d407-120">Cabeçalhos de ordens de venda CDS</span><span class="sxs-lookup"><span data-stu-id="9d407-120">CDS sales order headers</span></span>| <span data-ttu-id="9d407-121">SalesOrder</span><span class="sxs-lookup"><span data-stu-id="9d407-121">SalesOrder</span></span>     | <span data-ttu-id="9d407-122">SalesOrders</span><span class="sxs-lookup"><span data-stu-id="9d407-122">SalesOrders</span></span> |
| <span data-ttu-id="9d407-123">Linhas de ordem de venda do CDS</span><span class="sxs-lookup"><span data-stu-id="9d407-123">CDS sales order lines</span></span>  | <span data-ttu-id="9d407-124">SalesOrderLine</span><span class="sxs-lookup"><span data-stu-id="9d407-124">SalesOrderLine</span></span> | <span data-ttu-id="9d407-125">SalesOrderDetails</span><span class="sxs-lookup"><span data-stu-id="9d407-125">SalesOrderDetails</span></span>|

## <a name="entity-flow"></a><span data-ttu-id="9d407-126">Fluxo de entidades</span><span class="sxs-lookup"><span data-stu-id="9d407-126">Entity flow</span></span>

<span data-ttu-id="9d407-127">As ordens de venda são criadas no Finance and Operations e sincronizadas com o Sales.</span><span class="sxs-lookup"><span data-stu-id="9d407-127">Sales orders are created in Finance and Operations and synchronized to Sales.</span></span>

<span data-ttu-id="9d407-128">Os filtros em modelo garantem que somente as ordens de venda relevantes serão incluídas na sincronização:</span><span class="sxs-lookup"><span data-stu-id="9d407-128">Filters in the template ensure that only relevant sales orders are included in the synchronization:</span></span>

- <span data-ttu-id="9d407-129">A solicitação e faturamento do cliente na ordem de venda originada do Sales serão incluídas na sincronização.</span><span class="sxs-lookup"><span data-stu-id="9d407-129">Both ordering and invoicing customer on the sales order that originate from Sales will be included in the synchronization.</span></span> <span data-ttu-id="9d407-130">No Finance and Operations, os campos **OrderingCustomerIsExternallyMaintained** e **InvoiceCustomerIsExternallyMaintained** são usados para rastrear a sincronização nas entidades de dados.</span><span class="sxs-lookup"><span data-stu-id="9d407-130">In Finance and Operations, the fields **OrderingCustomerIsExternallyMaintained** and **InvoiceCustomerIsExternallyMaintained** are used to track the synchronization in the data entities.</span></span>

- <span data-ttu-id="9d407-131">A **Ordem de venda** no Finance and Operations deve ser confirmada.</span><span class="sxs-lookup"><span data-stu-id="9d407-131">The **Sales order** in Finance and Operations must be confirmed.</span></span> <span data-ttu-id="9d407-132">Somente ordens de venda confirmadas ou as ordens de venda com status superior, por exemplo, Enviado ou Faturado são sincronizadas com o Sales.</span><span class="sxs-lookup"><span data-stu-id="9d407-132">Only the confirmed sales orders or sales orders with higher processing status, for example, Shipped or Invoiced status, are synchronized to Sales.</span></span>

- <span data-ttu-id="9d407-133">Após criar ou modificar uma ordem de venda, o trabalho em lote **Calcular totais de vendas** no Finance and Operations deve ser executado.</span><span class="sxs-lookup"><span data-stu-id="9d407-133">After creating or modifying a sales order, the batch job **Calculate sales totals** in Finance and Operations must be executed.</span></span> <span data-ttu-id="9d407-134">Somente ordens de venda com os totais de vendas calculados serão sincronizadas com o CDS e o Sales.</span><span class="sxs-lookup"><span data-stu-id="9d407-134">Only the sales orders with sales totals calculated will be synced to CDS and Sales.</span></span>

> [!NOTE]
> <span data-ttu-id="9d407-135">Os impostos relacionadas aos encargos no **Cabeçalho de ordem de venda** não são incluídos na sincronização do Finance and Operations com o Sales.</span><span class="sxs-lookup"><span data-stu-id="9d407-135">Tax related to charges on the **Sales order header** is currently not included in synchronization from Finance and Operations to Sales.</span></span> <span data-ttu-id="9d407-136">Isso porque o Sales não oferece suporte às informações de imposto em nível de cabeçalho.</span><span class="sxs-lookup"><span data-stu-id="9d407-136">This is because Sales doesn't support tax information at the header level.</span></span> <span data-ttu-id="9d407-137">Os impostos relacionadas aos encargos em nível de linha são incluídos.</span><span class="sxs-lookup"><span data-stu-id="9d407-137">Tax related to charges at the line level is included.</span></span>

## <a name="prospect-to-cash-solution-for-sales"></a><span data-ttu-id="9d407-138">Solução Prospect to cash para o Sales</span><span class="sxs-lookup"><span data-stu-id="9d407-138">Prospect to cash solution for Sales</span></span>

<span data-ttu-id="9d407-139">Os campos novos são adicionados à entidade **Ordem** e exibidos na página:</span><span class="sxs-lookup"><span data-stu-id="9d407-139">New fields are added to the **Order** entity and displayed on the page:</span></span>

- <span data-ttu-id="9d407-140">**É mantido externamente** - Definido como **Sim** quando a ordem for proveniente do Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="9d407-140">**Is Maintained Externally** - Set to **Yes** when the order is coming from Finance and Operations.</span></span>

- <span data-ttu-id="9d407-141">**Status de processamento** - Usado para mostrar o status de processamento da ordem no Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="9d407-141">**Processing status** - Used to show the processing status of the order in Finance and Operations.</span></span> <span data-ttu-id="9d407-142">Os valores são:</span><span class="sxs-lookup"><span data-stu-id="9d407-142">Values are:</span></span>

    - <span data-ttu-id="9d407-143">Ativos</span><span class="sxs-lookup"><span data-stu-id="9d407-143">Active</span></span>
    - <span data-ttu-id="9d407-144">Confirmada</span><span class="sxs-lookup"><span data-stu-id="9d407-144">Confirmed</span></span>
    - <span data-ttu-id="9d407-145">Guia de remessa</span><span class="sxs-lookup"><span data-stu-id="9d407-145">Packing Slip</span></span>
    - <span data-ttu-id="9d407-146">Faturadas</span><span class="sxs-lookup"><span data-stu-id="9d407-146">Invoiced</span></span>
    - <span data-ttu-id="9d407-147">Separado</span><span class="sxs-lookup"><span data-stu-id="9d407-147">Picked</span></span>
    - <span data-ttu-id="9d407-148">Parcialmente separada</span><span class="sxs-lookup"><span data-stu-id="9d407-148">Partially Picked</span></span>
    - <span data-ttu-id="9d407-149">Parcialmente embalada</span><span class="sxs-lookup"><span data-stu-id="9d407-149">Partially Packed</span></span>
    - <span data-ttu-id="9d407-150">Remetido</span><span class="sxs-lookup"><span data-stu-id="9d407-150">Shipped</span></span>
    - <span data-ttu-id="9d407-151">Parcialmente remetida</span><span class="sxs-lookup"><span data-stu-id="9d407-151">Partially Shipped</span></span>
    - <span data-ttu-id="9d407-152">Parcialmente faturada</span><span class="sxs-lookup"><span data-stu-id="9d407-152">Partially Invoiced</span></span>
    - <span data-ttu-id="9d407-153">Cancelado</span><span class="sxs-lookup"><span data-stu-id="9d407-153">Cancelled</span></span>

<span data-ttu-id="9d407-154">A configuração **Tem Somente Produtos Mantidos Externamente** é usada em outros cenários de ordem de venda (de sincronização do Sales para Finance and Operation) para manter o controle consistentemente se a ordem de venda for composta totalmente de **Produtos Mantidos Externamente**, nesse caso os produtos são mantidos no Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="9d407-154">The **Has Externally Maintained Products Only** setting is used in other sales order scenarios (from Sales to Finance and Operation sync) to consistently keep track of whether the sales order is made up entirely of **Externally Maintained Products**, in which case products are maintained in Finance and Operations.</span></span> <span data-ttu-id="9d407-155">Isso garante que você não tentará sincronizar linhas da ordem de vendas com produtos que são desconhecidos com o Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="9d407-155">This ensures that you don't try to sync sales order lines with products that are unknown to Finance and Operations.</span></span>
 
<span data-ttu-id="9d407-156">Os botões **Criar fatura**, **Cancelar ordem**, **Recalcular**, **Obter produtos** e **Procurar endereço** na página **Ordem de venda** são ocultos das ordens mantidas externamente porque as faturas serão criadas no Finance and Operations e sincronizadas com o Sales.</span><span class="sxs-lookup"><span data-stu-id="9d407-156">The **Create Invoice**, **Cancel Order**, **Recalculate**, **Get Products** and **Lookup Address** buttons on the **Sales order** page are hidden for externally maintained orders because invoices will be created in Finance and Operations and synced to Sales.</span></span> <span data-ttu-id="9d407-157">A página da ordem não é editável porque as informações da ordem de venda serão sincronizadas do Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="9d407-157">The order page is non-editable because sales order information will be synced from Finance and Operations.</span></span>
 
<span data-ttu-id="9d407-158">O **Status da ordem de venda** permanecerá ativo para garantir que as alterações do Finance and Operations podem fluir para a **Ordem de venda** no Sales.</span><span class="sxs-lookup"><span data-stu-id="9d407-158">The **Sales order status** will remain active to ensure that changes from Finance and Operations can flow to the **Sales order** in Sales.</span></span> <span data-ttu-id="9d407-159">Isso é controlado pela definição do **Statecode [Status]** padrão como **Ativo** no projeto de integração de dados.</span><span class="sxs-lookup"><span data-stu-id="9d407-159">This is controlled by setting the default **Statecode [Status]** to **Active** in the Data integration project.</span></span>

## <a name="preconditions-and-mapping-setup"></a><span data-ttu-id="9d407-160">Precondições e configuração de mapeamento</span><span class="sxs-lookup"><span data-stu-id="9d407-160">Preconditions and mapping setup</span></span> 

<span data-ttu-id="9d407-161">Antes de sincronizar as ordens de venda, é importante atualizar os sistemas com a seguinte configuração:</span><span class="sxs-lookup"><span data-stu-id="9d407-161">Before synchronizing sales orders, it is important to update the systems with the following setting:</span></span>

### <a name="setup-in-sales"></a><span data-ttu-id="9d407-162">Configuração no Sales</span><span class="sxs-lookup"><span data-stu-id="9d407-162">Setup in Sales</span></span>

- <span data-ttu-id="9d407-163">Garante permissões para a equipe à qual o usuário (de seu **Conjunto de conexão** do Sales) está atribuído.</span><span class="sxs-lookup"><span data-stu-id="9d407-163">Ensure permissions for the team that the user (from your Sales **Connection set**) is assigned to.</span></span> <span data-ttu-id="9d407-164">Se estiver usando os dados de demonstração, geralmente o usuário tem acesso admin, mas não a equipe.</span><span class="sxs-lookup"><span data-stu-id="9d407-164">If you are using demo data, usually the user has admin access, but not the team.</span></span> <span data-ttu-id="9d407-165">Sem isso você receberá um erro informando que a equipe Principal está faltando ao executar o projeto do Integrador de dados.</span><span class="sxs-lookup"><span data-stu-id="9d407-165">Without this you will get an error that Principal team is missing when running the project from Data integrator.</span></span> 

    - <span data-ttu-id="9d407-166">Em **Configurações** > **Segurança** > **Equipes**, selecione a equipe relevante, clique em **Gerenciar funções** e selecione uma função com as permissões desejadas, por exemplo, Administrador do Sistema.</span><span class="sxs-lookup"><span data-stu-id="9d407-166">Under **Settings** > **Security** > **Teams**, select the relevant team, click **Manage Roles** and select a role with the desired permissions e.g. System Administrator.</span></span>

- <span data-ttu-id="9d407-167">Em **Configurações** > **Administração** > **Configurações do sistema** > **Sales**, certifique-se de que **Usar sistema de cálculo de precificação do sistema** esteja definido como **Sim**.</span><span class="sxs-lookup"><span data-stu-id="9d407-167">Under **Settings** > **Administration** > **System settings** > **Sales**, ensure that **Use system prizing calculation system** is set to **Yes**.</span></span> 

- <span data-ttu-id="9d407-168">Em **Configurações** > **Administração** > **Configurações do sistema** > **Sales**, certifique-se de que o **Método de cálculo de desconto** esteja definido como **Item de linha**.</span><span class="sxs-lookup"><span data-stu-id="9d407-168">Under **Settings** > **Administration** > **System settings** > **Sales**, ensure that **Discount calculation method** is set to **Line item**.</span></span> 

### <a name="setup-in-finance-and-operations"></a><span data-ttu-id="9d407-169">Configuração no Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="9d407-169">Setup in Finance and Operations</span></span>

<span data-ttu-id="9d407-170">Defina**Vendas e marketing** > **Tarefas periódicas** > **Calcular os totais de vendas** para executar como trabalho em lotes, com **Calcular total para ordens de venda** definido como **Sim**.</span><span class="sxs-lookup"><span data-stu-id="9d407-170">Set **Sales and marketing** > **Periodic tasks** > **Calculate sales totals** to run as a batch job, with **Calculate totals for sales orders** set to **Yes**.</span></span> <span data-ttu-id="9d407-171">Isso é importante porque somente as ordens de venda com os totais de vendas calculados serão sincronizados com o CDS e o Sales.</span><span class="sxs-lookup"><span data-stu-id="9d407-171">This is important because only the sales orders with sales totals calculated will be synced to CDS and Sales.</span></span> <span data-ttu-id="9d407-172">A frequência do trabalho em lotes deve ser alinhada à frequência da sincronização de ordens de venda.</span><span class="sxs-lookup"><span data-stu-id="9d407-172">The frequency of the batch job should be alligned with the frequency of the sales order synchronization.</span></span>

### <a name="setup-in-the-data-integration-project"></a><span data-ttu-id="9d407-173">Configuração no Projeto de integração de dados</span><span class="sxs-lookup"><span data-stu-id="9d407-173">Setup in the Data integration project</span></span>

#### <a name="salesheader-task"></a><span data-ttu-id="9d407-174">Tarefa de SalesHeader</span><span class="sxs-lookup"><span data-stu-id="9d407-174">SalesHeader task</span></span>

- <span data-ttu-id="9d407-175">Atualize o mapeamento para **ID da Organização CDS na Origem** > **CDS**.</span><span class="sxs-lookup"><span data-stu-id="9d407-175">Update the mapping for **CDS Organization ID in Source** > **CDS**.</span></span>

    - <span data-ttu-id="9d407-176">O valor do modelo padrão para **Account_Organization_OrganizationId** é ORG001.</span><span class="sxs-lookup"><span data-stu-id="9d407-176">Default template value for **Account_Organization_OrganizationId** is ORG001.</span></span>
    - <span data-ttu-id="9d407-177">O valor do modelo padrão para **InvoiceAccount_Organization_OrganizationId** é ORG001.</span><span class="sxs-lookup"><span data-stu-id="9d407-177">Default template value for **InvoiceAccount_Organization_OrganizationId** is ORG001.</span></span>
    - <span data-ttu-id="9d407-178">O valor do modelo padrão para **Organization_OrganizationId** é ORG001.</span><span class="sxs-lookup"><span data-stu-id="9d407-178">Default template value for **Organization_OrganizationId** is ORG001.</span></span>

- <span data-ttu-id="9d407-179">Verifique se o mapeamento necessário existe em **Origem** > **CDS para InvoiceCountryRegionId para BillingAddress_Country** e para **DeliveryCountryRegionId para DeliveryAddress_Country**.</span><span class="sxs-lookup"><span data-stu-id="9d407-179">Ensure that the needed mapping exists in **Source** > **CDS for InvoiceCountryRegionId to BillingAddress_Country** and for **DeliveryCountryRegionId to DeliveryAddress_Country**.</span></span>

    - <span data-ttu-id="9d407-180">O valor do modelo é **ValueMap** com um número de países mapeado.</span><span class="sxs-lookup"><span data-stu-id="9d407-180">Template value is **ValueMap** with a number of countries mapped.</span></span>

- <span data-ttu-id="9d407-181">**Lista de preços** é necessário para criar ordens no Sales.</span><span class="sxs-lookup"><span data-stu-id="9d407-181">**Price list** is required to create orders in Sales.</span></span> <span data-ttu-id="9d407-182">Atualize o **ValueMap** em **CDS** > **Destino** para **pricelevelid.name [Price List Name]** para a **Lista de preços** usada no Sales por moeda.</span><span class="sxs-lookup"><span data-stu-id="9d407-182">Update the **ValueMap** in **CDS** > **Destination** for **pricelevelid.name [Price List Name]** to the **Price list** used in Sales per currency.</span></span> <span data-ttu-id="9d407-183">Você pode usar a **Lista de preços** padrão para uma única moeda ou usar **ValueMap** se tiver **Listas de preços** em várias moedas.</span><span class="sxs-lookup"><span data-stu-id="9d407-183">You can either used the default **Price list** for single currency or use **ValueMap** if you have **Price lists** in multiple currencies.</span></span>
    
    - <span data-ttu-id="9d407-184">O valor padrão do modelo para **pricelevelid.name [Price List Name]** é Serviço CRM USA (amostra).</span><span class="sxs-lookup"><span data-stu-id="9d407-184">Default template value for **pricelevelid.name [Price List Name]** is CRM Service USA (sample).</span></span> 

#### <a name="salesline-task"></a><span data-ttu-id="9d407-185">Tarefa de SalesLine</span><span class="sxs-lookup"><span data-stu-id="9d407-185">SalesLine task</span></span>

- <span data-ttu-id="9d407-186">Atualize o mapeamento para **ID da Organização CDS na Origem** > **CDS**.</span><span class="sxs-lookup"><span data-stu-id="9d407-186">Update the mapping for **CDS Organization ID in Source** > **CDS**.</span></span> 
    
    - <span data-ttu-id="9d407-187">O valor do modelo padrão para **SalesOrder_Organization_OrganizationId** é ORG001.</span><span class="sxs-lookup"><span data-stu-id="9d407-187">Default template value for **SalesOrder_Organization_OrganizationId** is ORG001.</span></span>
    - <span data-ttu-id="9d407-188">O valor do modelo padrão para **Product_Organization_OrganizationId** é ORG001.</span><span class="sxs-lookup"><span data-stu-id="9d407-188">Default template value for **Product_Organization_OrganizationId** is ORG001.</span></span>

- <span data-ttu-id="9d407-189">Verifique se o mapeamento necessário existe na **Origem** > **CDS** para **DeliveryCountryRegionId** para **DeliveryAddress_Country**.</span><span class="sxs-lookup"><span data-stu-id="9d407-189">Ensure that the needed mapping exists in **Source** > **CDS** for **DeliveryCountryRegionId** to **DeliveryAddress_Country**.</span></span>

    - <span data-ttu-id="9d407-190">O valor do modelo é **ValueMap** com um número de países mapeado.</span><span class="sxs-lookup"><span data-stu-id="9d407-190">Template value is **ValueMap** with a number of countries mapped.</span></span>
    
- <span data-ttu-id="9d407-191">Verifique se o **ValueMap** necessário para **SalesUnitSymbol** no Finance and Operations existe em **Origem** > **Mapeamento de CDS**.</span><span class="sxs-lookup"><span data-stu-id="9d407-191">Ensure that the needed **ValueMap** for **SalesUnitSymbol** in Finance and Operations exists in the **Source** > **CDS mapping**.</span></span>

    - <span data-ttu-id="9d407-192">O valor do modelo com **ValueMap** é definido para **SalesUnitSymbol to Quantity_UOM**.</span><span class="sxs-lookup"><span data-stu-id="9d407-192">Template value with **ValueMap** is defined for **SalesUnitSymbol to Quantity_UOM**.</span></span>

## <a name="template-mapping-in-data-integrator"></a><span data-ttu-id="9d407-193">Mapeamento de modelos no integrador de dados</span><span class="sxs-lookup"><span data-stu-id="9d407-193">Template mapping in data integrator</span></span>

> [!NOTE]
> <span data-ttu-id="9d407-194">Os campos **Termos de pagamento**, **Condições de frete**, **Condições de entrega**, **Método de entrega** e **Modo de entrega** não estão incluídos no mapeamento padrão.</span><span class="sxs-lookup"><span data-stu-id="9d407-194">The **Payment terms**, **Freight terms**, **Delivery terms**, **Shipping method**, and **Delivery mode** fields aren't part of the default mappings.</span></span> <span data-ttu-id="9d407-195">Para mapear esses campos, é necessário configurar um mapeamento de valor que é específico para os dados nas organizações às quais a entidade está sincronizada.</span><span class="sxs-lookup"><span data-stu-id="9d407-195">To map these fields, you must set up a value mapping that is specific to the data in the organizations that the entity is synchronized between.</span></span>

<span data-ttu-id="9d407-196">As seguintes ilustrações mostram um exemplo de um mapeamento de modelos no integrador de dados.</span><span class="sxs-lookup"><span data-stu-id="9d407-196">The following illustrations show an example of a template mapping in data integrator.</span></span>

### <a name="orderheader"></a><span data-ttu-id="9d407-197">OrderHeader</span><span class="sxs-lookup"><span data-stu-id="9d407-197">OrderHeader</span></span>

![Mapeamento de modelos no integrador de dados](./media/sales-order-template-mapping-data-integrator-1.png)

![Mapeamento de modelos no integrador de dados](./media/sales-order-template-mapping-data-integrator-2.png)

### <a name="orderline"></a><span data-ttu-id="9d407-200">OrderLine</span><span class="sxs-lookup"><span data-stu-id="9d407-200">OrderLine</span></span>

![Mapeamento de modelos no integrador de dados](./media/sales-order-template-mapping-data-integrator-3.png)

![Mapeamento de modelos no integrador de dados](./media/sales-order-template-mapping-data-integrator-4.png)


## <a name="related-topics"></a><span data-ttu-id="9d407-203">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="9d407-203">Related topics</span></span>

[<span data-ttu-id="9d407-204">Sincronizar produtos do Finance and Operations com produtos do Sales</span><span class="sxs-lookup"><span data-stu-id="9d407-204">Synchronize products from Finance and Operations to products in Sales</span></span>](products-template-mapping.md)

[<span data-ttu-id="9d407-205">Sincronizar contas do Sales com clientes do Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="9d407-205">Synchronize accounts from Sales to customers in Finance and Operations</span></span>](accounts-template-mapping.md)

[<span data-ttu-id="9d407-206">Sincronizar contatos do Sales com contatos ou clientes do Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="9d407-206">Synchronize contacts from Sales to contacts or customers in Finance and Operations</span></span>](contacts-template-mapping.md)

[<span data-ttu-id="9d407-207">Sincronizar cabeçalhos e linhas de cotação de venda do Sales com o Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="9d407-207">Synchronize sales quotation headers and lines from Sales to Finance and Operations</span></span>](sales-quotation-template-mapping.md)

[<span data-ttu-id="9d407-208">Sincronizar cabeçalhos e linhas de fatura do Finance and Operations com o Sales</span><span class="sxs-lookup"><span data-stu-id="9d407-208">Synchronize sales invoice headers and lines from Finance and Operations to Sales</span></span>](sales-invoice-template-mapping.md)


