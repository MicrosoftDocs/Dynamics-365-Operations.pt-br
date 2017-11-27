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
ms.dyn365.ops.intro: July 2017 update
ms.search.validFrom: 2017-07-8
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: cc0be50552ae680ba5291e72b7c482ee67e1e70e
ms.contentlocale: pt-br
ms.lasthandoff: 11/03/2017

---

# <a name="synchronize-sales-order-headers-and-lines-directly-from-finance-and-operations-to-sales"></a><span data-ttu-id="cef53-103">Sincronizar cabeçalhos e linhas de ordem de venda diretamente do Finance and Operations com o Sales</span><span class="sxs-lookup"><span data-stu-id="cef53-103">Synchronize sales order headers and lines directly from Finance and Operations to Sales</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="cef53-104">Este tópico discute os modelos e as tarefas subjacentes que são usados para sincronizar cabeçalhos e linhas de ordem de venda diretamente do Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition, com o Microsoft Dynamics 365 for Sales.</span><span class="sxs-lookup"><span data-stu-id="cef53-104">This topic discusses the templates and underlying tasks that are used to synchronize sales order headers and lines directly from Microsoft Dynamics 365 for Finance and Operations, Enterprise edition, to Microsoft Dynamics 365 for Sales.</span></span>

## <a name="data-flow-in-prospect-to-cash"></a><span data-ttu-id="cef53-105">Fluxo de dados no Prospect to cash</span><span class="sxs-lookup"><span data-stu-id="cef53-105">Data flow in Prospect to cash</span></span>

<span data-ttu-id="cef53-106">A solução Prospect to cash usa o recurso de integração de dados sincronizar dados nas instâncias do Finance and Operations e do Sales.</span><span class="sxs-lookup"><span data-stu-id="cef53-106">The Prospect to cash solution uses the Data integration feature to synchronize data across instances of Finance and Operations and Sales.</span></span> <span data-ttu-id="cef53-107">Os modelos Prospect to cash que estão disponíveis com o recurso Integração de dados permitem o fluxo de dados sobre contas, contatos, produtos, cotações de vendas, ordens de venda e faturas de vendas entre o Finance and Operations e o Sales.</span><span class="sxs-lookup"><span data-stu-id="cef53-107">The Prospect to cash templates that are available with the Data integration feature enable the flow of data about accounts, contacts, products, sales quotations, sales orders, and sales invoices between Finance and Operations and Sales.</span></span> <span data-ttu-id="cef53-108">A ilustração a seguir mostra como os dados são sincronizados entre o Finance and Operations e o Sales.</span><span class="sxs-lookup"><span data-stu-id="cef53-108">The following illustration shows how the data is synchronized between Finance and Operations and Sales.</span></span>

<span data-ttu-id="cef53-109">[![Fluxo de dados em Prospect to cash](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)</span><span class="sxs-lookup"><span data-stu-id="cef53-109">[![Data flow in Prospect to cash](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="cef53-110">Modelos e tarefas</span><span class="sxs-lookup"><span data-stu-id="cef53-110">Templates and tasks</span></span>

<span data-ttu-id="cef53-111">Para acessar os modelos disponíveis, abra o [Centro de administração de PowerApps](https://preview.admin.powerapps.com/dataintegration).</span><span class="sxs-lookup"><span data-stu-id="cef53-111">To access the available templates, open [PowerApps Admin Center](https://preview.admin.powerapps.com/dataintegration).</span></span> <span data-ttu-id="cef53-112">Selecione **Projetos** e, no canto superior direito, selecione **Novo projeto** para selecionar modelos públicos.</span><span class="sxs-lookup"><span data-stu-id="cef53-112">Select **Projects**, and then, in the upper-right corner, select **New project** to select public templates.</span></span>

<span data-ttu-id="cef53-113">O modelo e as tarefas subjacentes a seguir são usados para sincronizar cabeçalhos e linhas da ordem de venda do Finance and Operations com o Sales:</span><span class="sxs-lookup"><span data-stu-id="cef53-113">The following template and underlying tasks are used to synchronize sales order headers and lines from Finance and Operations to Sales:</span></span>

- <span data-ttu-id="cef53-114">**Nome do modelo na Integração de dados:** Ordens de venda (Fin and Ops para Sales) – Direto</span><span class="sxs-lookup"><span data-stu-id="cef53-114">**Name of the template in Data integration:** Sales Orders (Fin and Ops to Sales) - Direct</span></span>
- <span data-ttu-id="cef53-115">**Nomes das tarefas no projeto de Integração de dados:**</span><span class="sxs-lookup"><span data-stu-id="cef53-115">**Names of the tasks in the Data integration project:**</span></span>

    - <span data-ttu-id="cef53-116">OrderHeader</span><span class="sxs-lookup"><span data-stu-id="cef53-116">OrderHeader</span></span>
    - <span data-ttu-id="cef53-117">OrderLine</span><span class="sxs-lookup"><span data-stu-id="cef53-117">OrderLine</span></span>

<span data-ttu-id="cef53-118">As seguintes tarefas de sincronização são obrigatórias para que a sincronização de cabeçalhos e linhas de fatura de venda possa ocorrer:</span><span class="sxs-lookup"><span data-stu-id="cef53-118">The following synchronization tasks are required before synchronization of sales invoice headers and lines can occur:</span></span>

- <span data-ttu-id="cef53-119">Produtos (Fin and Ops para Sales) – Direto</span><span class="sxs-lookup"><span data-stu-id="cef53-119">Products (Fin and Ops to Sales) - Direct</span></span>
- <span data-ttu-id="cef53-120">Contas (Sales para Fin and Ops) - Direto (se usado)</span><span class="sxs-lookup"><span data-stu-id="cef53-120">Accounts (Sales to Fin and Ops) - Direct (if used)</span></span>
- <span data-ttu-id="cef53-121">Contatos para Clientes (Sales para Fin and Ops) – Direto (se usados)</span><span class="sxs-lookup"><span data-stu-id="cef53-121">Contacts to Customers (Sales to Fin and Ops) - Direct (if used)</span></span>

## <a name="entity-set"></a><span data-ttu-id="cef53-122">Conjunto de entidades</span><span class="sxs-lookup"><span data-stu-id="cef53-122">Entity set</span></span>

| <span data-ttu-id="cef53-123">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="cef53-123">Finance and Operations</span></span>  | <span data-ttu-id="cef53-124">Vendas</span><span class="sxs-lookup"><span data-stu-id="cef53-124">Sales</span></span>             |
|-------------------------|-------------------|
| <span data-ttu-id="cef53-125">Cabeçalhos de ordens de venda CDS</span><span class="sxs-lookup"><span data-stu-id="cef53-125">CDS sales order headers</span></span> | <span data-ttu-id="cef53-126">SalesOrders</span><span class="sxs-lookup"><span data-stu-id="cef53-126">SalesOrders</span></span>       |
| <span data-ttu-id="cef53-127">Linhas de ordem de venda do CDS</span><span class="sxs-lookup"><span data-stu-id="cef53-127">CDS sales order lines</span></span>   | <span data-ttu-id="cef53-128">SalesOrderDetails</span><span class="sxs-lookup"><span data-stu-id="cef53-128">SalesOrderDetails</span></span> |

## <a name="entity-flow"></a><span data-ttu-id="cef53-129">Fluxo de entidades</span><span class="sxs-lookup"><span data-stu-id="cef53-129">Entity flow</span></span>

<span data-ttu-id="cef53-130">As ordens de venda são criadas no Finance and Operations e sincronizadas com o Sales.</span><span class="sxs-lookup"><span data-stu-id="cef53-130">Sales orders are created in Finance and Operations and synchronized to Sales.</span></span>

<span data-ttu-id="cef53-131">Os filtros em modelo ajudam a garantir que somente as ordens de venda relevantes sejam incluídas na sincronização:</span><span class="sxs-lookup"><span data-stu-id="cef53-131">Filters in the template help guarantee that only relevant sales orders are included in the synchronization:</span></span>

- <span data-ttu-id="cef53-132">Na ordem de venda, a solicitação do cliente e o faturamento do cliente que originam-se do Sales serão incluídos na sincronização.</span><span class="sxs-lookup"><span data-stu-id="cef53-132">On the sales order, both the ordering customer and the invoicing customer that originate from Sales will be included in the synchronization.</span></span> <span data-ttu-id="cef53-133">No Finance and Operations, os campos **OrderingCustomerIsExternallyMaintained** e **InvoiceCustomerIsExternallyMaintained** são usados para rastrear a sincronização nas entidades de dados.</span><span class="sxs-lookup"><span data-stu-id="cef53-133">In Finance and Operations, the **OrderingCustomerIsExternallyMaintained** and **InvoiceCustomerIsExternallyMaintained** fields are used to track the synchronization in the data entities.</span></span>
- <span data-ttu-id="cef53-134">A ordem de venda no Finance and Operations deve ser confirmada.</span><span class="sxs-lookup"><span data-stu-id="cef53-134">The sales order in Finance and Operations must be confirmed.</span></span> <span data-ttu-id="cef53-135">Somente ordens de venda confirmadas ou ordens de venda com status de processamento superior, como **Enviado** ou **Faturado** são sincronizadas com o Sales.</span><span class="sxs-lookup"><span data-stu-id="cef53-135">Only confirmed sales orders or sales orders that have a higher processing status, such as **Shipped** or **Invoiced**, are synchronized to Sales.</span></span>
- <span data-ttu-id="cef53-136">Após uma ordem de venda ser criada ou modificada, o trabalho em lotes **Calcular totais de vendas** no Finance and Operations deve ser executado.</span><span class="sxs-lookup"><span data-stu-id="cef53-136">After a sales order is created or modified, the **Calculate sales totals** batch job in Finance and Operations must be run.</span></span> <span data-ttu-id="cef53-137">Somente as ordens de venda em que os totais de vendas são calculados serão sincronizadas para o Sales.</span><span class="sxs-lookup"><span data-stu-id="cef53-137">Only sales orders where sales totals are calculated will be synchronized to Sales.</span></span>

> [!NOTE]
> <span data-ttu-id="cef53-138">Atualmente, o imposto que está relacionado aos encargos no cabeçalho de ordem de venda não é incluído na sincronização do Finance and Operations com o Sales.</span><span class="sxs-lookup"><span data-stu-id="cef53-138">Currently, tax that is related to charges on the sales order header isn't included in the synchronization from Finance and Operations to Sales.</span></span> <span data-ttu-id="cef53-139">O Sales não dá suporte às informações de imposto em nível de cabeçalho.</span><span class="sxs-lookup"><span data-stu-id="cef53-139">Sales doesn't support tax information at the header level.</span></span> <span data-ttu-id="cef53-140">Entretanto, impostos relativos aos encargos em nível de linha são incluídos na sincronização.</span><span class="sxs-lookup"><span data-stu-id="cef53-140">However, tax that is related to charges at the line level is included in the synchronization.</span></span>

## <a name="prospect-to-cash-solution-for-sales"></a><span data-ttu-id="cef53-141">Solução Prospect to cash para o Sales</span><span class="sxs-lookup"><span data-stu-id="cef53-141">Prospect to cash solution for Sales</span></span>

<span data-ttu-id="cef53-142">Novos campos foram adicionados à entidade **Ordem** e são exibidos na página:</span><span class="sxs-lookup"><span data-stu-id="cef53-142">New fields have been added to the **Order** entity and appear on the page:</span></span>

- <span data-ttu-id="cef53-143">**É mantido externamente** – Defina esta opção como **Sim** quando a ordem for proveniente do Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="cef53-143">**Is Maintained Externally** – Set this option to **Yes** when the order is coming from Finance and Operations.</span></span>
- <span data-ttu-id="cef53-144">**Status de processamento** – Este campo mostra o status de processamento da ordem no Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="cef53-144">**Processing status** – This field shows the processing status of the order in Finance and Operations.</span></span> <span data-ttu-id="cef53-145">Os valores a seguir estão disponíveis:</span><span class="sxs-lookup"><span data-stu-id="cef53-145">The following values are available:</span></span>

    - <span data-ttu-id="cef53-146">Ativos</span><span class="sxs-lookup"><span data-stu-id="cef53-146">Active</span></span>
    - <span data-ttu-id="cef53-147">Confirmada</span><span class="sxs-lookup"><span data-stu-id="cef53-147">Confirmed</span></span>
    - <span data-ttu-id="cef53-148">Guia de remessa</span><span class="sxs-lookup"><span data-stu-id="cef53-148">Packing Slip</span></span>
    - <span data-ttu-id="cef53-149">Faturadas</span><span class="sxs-lookup"><span data-stu-id="cef53-149">Invoiced</span></span>
    - <span data-ttu-id="cef53-150">Separado</span><span class="sxs-lookup"><span data-stu-id="cef53-150">Picked</span></span>
    - <span data-ttu-id="cef53-151">Parcialmente separada</span><span class="sxs-lookup"><span data-stu-id="cef53-151">Partially Picked</span></span>
    - <span data-ttu-id="cef53-152">Parcialmente embalada</span><span class="sxs-lookup"><span data-stu-id="cef53-152">Partially Packed</span></span>
    - <span data-ttu-id="cef53-153">Remetido</span><span class="sxs-lookup"><span data-stu-id="cef53-153">Shipped</span></span>
    - <span data-ttu-id="cef53-154">Parcialmente remetida</span><span class="sxs-lookup"><span data-stu-id="cef53-154">Partially Shipped</span></span>
    - <span data-ttu-id="cef53-155">Parcialmente faturada</span><span class="sxs-lookup"><span data-stu-id="cef53-155">Partially Invoiced</span></span>
    - <span data-ttu-id="cef53-156">Cancelado</span><span class="sxs-lookup"><span data-stu-id="cef53-156">Cancelled</span></span>

<span data-ttu-id="cef53-157">A configuração **Tem Somente Produtos Mantidos Externamente** é usada em outros cenários de ordem de venda (por exemplo, sincronização do Sales com o Finance and Operation) para rastrear se a ordem de venda consiste totalmente de produtos mantidos externamente.</span><span class="sxs-lookup"><span data-stu-id="cef53-157">The **Has Externally Maintained Products Only** setting is used in other sales order scenarios (for example, synchronization from Sales to Finance and Operation) to consistently track whether a sales order consists entirely of externally maintained products.</span></span> <span data-ttu-id="cef53-158">Se uma ordem de venda consiste inteiramente em produtos mantidos externamente, os produtos são mantidos no Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="cef53-158">If a sales order consists entirely of externally maintained products, the products are maintained in Finance and Operations.</span></span> <span data-ttu-id="cef53-159">Esta configuração ajuda a garantir que você não tente sincronizar linhas da ordem de venda que tenham produtos que sejam desconhecidos para Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="cef53-159">This setting helps guarantee that you don't try to synchronize sales order lines that have products that are unknown to Finance and Operations.</span></span>

<span data-ttu-id="cef53-160">Os botões **Criar fatura**, **Cancelar Ordem**, **Recalcular**, **Obter Produtos** e **Procurar Endereço** na página **Ordem de venda** são ocultos para ordens mantidas externamente, pois as faturas serão criadas no Finance and Operations e sincronizadas para o Sales.</span><span class="sxs-lookup"><span data-stu-id="cef53-160">The **Create Invoice**, **Cancel Order**, **Recalculate**, **Get Products**, and **Lookup Address** buttons on the **Sales order** page are hidden for externally maintained orders, because invoices will be created in Finance and Operations and synchronized to Sales.</span></span> <span data-ttu-id="cef53-161">A página da ordem não pode ser editada, porque as informações da ordem de venda serão sincronizadas do Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="cef53-161">The order page can't be edited, because sales order information will be synchronized from Finance and Operations.</span></span>

<span data-ttu-id="cef53-162">O status de uma ordem de venda permanecerá **Ativo** para ajudar a garantir que as alterações do Finance and Operations possam fluir para a ordem de venda do Sales.</span><span class="sxs-lookup"><span data-stu-id="cef53-162">The status of a sales order will remain **Active** to help guarantee that changes from Finance and Operations can flow to the sales order in Sales.</span></span> <span data-ttu-id="cef53-163">Para controlar este comportamento, defina o padrão do valor **Statecode \[Status\]** para **Ativo** no Projeto de integração de dados.</span><span class="sxs-lookup"><span data-stu-id="cef53-163">To control this behavior, set the default **Statecode \[Status\]** value to **Active** in the Data integration project.</span></span>

## <a name="preconditions-and-mapping-setup"></a><span data-ttu-id="cef53-164">Precondições e configuração de mapeamento</span><span class="sxs-lookup"><span data-stu-id="cef53-164">Preconditions and mapping setup</span></span>

<span data-ttu-id="cef53-165">Antes de sincronizar ordens de venda, é importante atualizar as configurações a seguir nos sistemas.</span><span class="sxs-lookup"><span data-stu-id="cef53-165">Before you synchronize sales orders, it's important that you update the following settings in the systems.</span></span>

### <a name="setup-in-sales"></a><span data-ttu-id="cef53-166">Configuração no Sales</span><span class="sxs-lookup"><span data-stu-id="cef53-166">Setup in Sales</span></span>

- <span data-ttu-id="cef53-167">Verifique se as permissões estão definidas para a equipe à qual foi atribuído o usuário da conexão do Sales definida.</span><span class="sxs-lookup"><span data-stu-id="cef53-167">Make sure that permissions are set up for the team that the user from your Sales connection set is assigned to.</span></span> <span data-ttu-id="cef53-168">Se estiver usando os dados de demonstração, geralmente o usuário tem acesso admin, mas a equipe não tem acesso admin.</span><span class="sxs-lookup"><span data-stu-id="cef53-168">If you're using demo data, the user usually has admin access, but the team doesn't have admin access.</span></span> <span data-ttu-id="cef53-169">Se a equipe não tiver acesso admin, quando o projeto for executado da Integração de dados, você receberá uma mensagem de erro que indica que a Equipe principal está ausente.</span><span class="sxs-lookup"><span data-stu-id="cef53-169">If the team doesn't also have admin access, when you run the project from Data integration, you will receive an error message that states that Principal team is missing.</span></span>

    <span data-ttu-id="cef53-170">Vá para **Configurações** > **Segurança** > **Equipes**, selecione a equipe relevante, selecione **Gerenciar funções** e selecione a função que tem as permissões desejadas, como **Administrador do Sistema**.</span><span class="sxs-lookup"><span data-stu-id="cef53-170">Go to **Settings** > **Security** > **Teams**, select the relevant team, select **Manage Roles**, and select a role that has the desired permissions, such as **System Administrator**.</span></span>

- <span data-ttu-id="cef53-171">Vá para **Configurações** > **Administração** > **Configurações do sistema** > **Sales** e certifique-se de que as seguintes configurações sejam usadas:</span><span class="sxs-lookup"><span data-stu-id="cef53-171">Go to **Settings** > **Administration** > **System settings** > **Sales**, and makes sure that the following settings are used:</span></span>

    - <span data-ttu-id="cef53-172">A opção **Usar sistema de cálculo de precificação do sistema** está definida como **Sim**.</span><span class="sxs-lookup"><span data-stu-id="cef53-172">The **Use system prizing calculation system** option is set to **Yes**.</span></span>
    - <span data-ttu-id="cef53-173">O campo **Método de cálculo de desconto** está definido como **Item de linha**.</span><span class="sxs-lookup"><span data-stu-id="cef53-173">The **Discount calculation method** field is set to **Line item**.</span></span>

### <a name="setup-in-finance-and-operations"></a><span data-ttu-id="cef53-174">Configuração no Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="cef53-174">Setup in Finance and Operations</span></span>

<span data-ttu-id="cef53-175">Vá para **Vendas e marketing** > **Tarefas periódicas** > **Calcular totais de vendas** e configure o trabalho para ser executado como um trabalho em lotes.</span><span class="sxs-lookup"><span data-stu-id="cef53-175">Go to **Sales and marketing** > **Periodic tasks** > **Calculate sales totals**, and set the job to run as a batch job.</span></span> <span data-ttu-id="cef53-176">Defina a opção **Calcular totais de ordens de venda** como **Sim**.</span><span class="sxs-lookup"><span data-stu-id="cef53-176">Set the **Calculate totals for sales orders** option to **Yes**.</span></span> <span data-ttu-id="cef53-177">Esta etapa é importante, pois somente as ordens de venda em que os totais de vendas são calculados serão sincronizadas para o Sales.</span><span class="sxs-lookup"><span data-stu-id="cef53-177">This step is important, because only sales orders where sales totals are calculated will be synchronized to Sales.</span></span> <span data-ttu-id="cef53-178">A frequência do trabalho em lotes deve ser alinhada à frequência de sincronização da ordem de venda.</span><span class="sxs-lookup"><span data-stu-id="cef53-178">The frequency of the batch job should be aligned with the frequency of sales order synchronization.</span></span>

### <a name="setup-in-the-data-integration-project"></a><span data-ttu-id="cef53-179">Configuração no Projeto de integração de dados</span><span class="sxs-lookup"><span data-stu-id="cef53-179">Setup in the Data integration project</span></span>

#### <a name="salesheader-task"></a><span data-ttu-id="cef53-180">Tarefa de SalesHeader</span><span class="sxs-lookup"><span data-stu-id="cef53-180">SalesHeader task</span></span>

- <span data-ttu-id="cef53-181">Verifique se o mapeamento exigido existe para **InvoiceCountryRegionId** para **BillingAddress\_Country** e para **DeliveryCountryRegionId** para **DeliveryAddress\_Country**.</span><span class="sxs-lookup"><span data-stu-id="cef53-181">Make sure that the required mapping exists for **InvoiceCountryRegionId** to **BillingAddress\_Country** and for **DeliveryCountryRegionId** to **DeliveryAddress\_Country**.</span></span>

    <span data-ttu-id="cef53-182">O valor do modelo é um mapa de valores em que vários países ou regiões são mapeados.</span><span class="sxs-lookup"><span data-stu-id="cef53-182">The template value is a value map where several countries or regions are mapped.</span></span>

- <span data-ttu-id="cef53-183">Uma lista de preços é necessária para criar ordens no Sales.</span><span class="sxs-lookup"><span data-stu-id="cef53-183">A price list is required in order to create orders in Sales.</span></span> <span data-ttu-id="cef53-184">Atualize o mapa de valores para **pricelevelid.name \[Price list name\]** para a lista de preços que é usada no Sales por moeda.</span><span class="sxs-lookup"><span data-stu-id="cef53-184">Update the value map for **pricelevelid.name \[Price list name\]** to the price list that is used in Sales per currency.</span></span> <span data-ttu-id="cef53-185">Você pode usar a lista de preços padrão para uma única moeda.</span><span class="sxs-lookup"><span data-stu-id="cef53-185">You can use the default price list for a single currency.</span></span> <span data-ttu-id="cef53-186">Caso existam listas de preços em várias moedas, você poderá usar um mapa de valores.</span><span class="sxs-lookup"><span data-stu-id="cef53-186">Alternatively, if you have price lists in multiple currencies, you can use a value map.</span></span>

    <span data-ttu-id="cef53-187">O valor do modelo padrão para **pricelevelid.name \[Price list name\]** é **CRM Service USA (sample)**.</span><span class="sxs-lookup"><span data-stu-id="cef53-187">The default template value for **pricelevelid.name \[Price list name\]** is **CRM Service USA (sample)**.</span></span>

#### <a name="salesline-task"></a><span data-ttu-id="cef53-188">Tarefa de SalesLine</span><span class="sxs-lookup"><span data-stu-id="cef53-188">SalesLine task</span></span>

- <span data-ttu-id="cef53-189">Verifique se o mapeamento exigido existe para **DeliveryCountryRegionId** para **DeliveryAddress\_Country**.</span><span class="sxs-lookup"><span data-stu-id="cef53-189">Make sure that the required mapping exists for **DeliveryCountryRegionId** to **DeliveryAddress\_Country**.</span></span>

    <span data-ttu-id="cef53-190">O valor do modelo é um mapa de valores em que vários países ou regiões são mapeados.</span><span class="sxs-lookup"><span data-stu-id="cef53-190">The template value is a value map where several countries or regions are mapped.</span></span>

- <span data-ttu-id="cef53-191">Verifique se existe o mapa de valores necessário para **SalesUnitSymbol** no Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="cef53-191">Make sure that the required value map for **SalesUnitSymbol** in Finance and Operations exists.</span></span>

    <span data-ttu-id="cef53-192">Um valor do modelo que tem um mapa de valores é definido para **SalesUnitSymbol** como **Quantity\_UOM**.</span><span class="sxs-lookup"><span data-stu-id="cef53-192">A template value that has a value map is defined for **SalesUnitSymbol** to **Quantity\_UOM**.</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="cef53-193">Mapeamento de modelo na Integração de dados</span><span class="sxs-lookup"><span data-stu-id="cef53-193">Template mapping in Data integration</span></span>

> [!NOTE]
> <span data-ttu-id="cef53-194">Os campos **Termos de pagamento**, **Condições de frete**, **Condições de entrega**, **Método de remessa** e **Modo de entrega** não estão incluídos no mapeamento padrão.</span><span class="sxs-lookup"><span data-stu-id="cef53-194">The **Payment terms**, **Freight terms**, **Delivery terms**, **Shipping method**, and **Delivery mode** fields aren't included in the default mappings.</span></span> <span data-ttu-id="cef53-195">Para mapear esses campos, é necessário configurar um mapeamento de valor que é específico para os dados nas organizações às quais a entidade está sincronizada.</span><span class="sxs-lookup"><span data-stu-id="cef53-195">To map these fields, you must set up a value mapping that is specific to the data in the organizations that the entity is synchronized between.</span></span>

<span data-ttu-id="cef53-196">As ilustrações a seguir mostram um exemplo de um mapeamento de modelo na Integração de dados.</span><span class="sxs-lookup"><span data-stu-id="cef53-196">The following illustrations show an example of a template mapping in Data integration.</span></span> 

> [!NOTE]
> <span data-ttu-id="cef53-197">O mapeamento mostra quais informações de campo serão sincronizadas do Sales com o Finance and Operations..</span><span class="sxs-lookup"><span data-stu-id="cef53-197">The mapping shows which field information will be synchronized from Sales to Finance and Operations.</span></span>

### <a name="orderheader"></a><span data-ttu-id="cef53-198">OrderHeader</span><span class="sxs-lookup"><span data-stu-id="cef53-198">OrderHeader</span></span>

![Mapeamento de modelo no Integrador de dados](./media/sales-order-direct-template-mapping-data-integrator-1.png)

### <a name="orderline"></a><span data-ttu-id="cef53-200">OrderLine</span><span class="sxs-lookup"><span data-stu-id="cef53-200">OrderLine</span></span>

![Mapeamento de modelo no Integrador de dados](./media/sales-order-direct-template-mapping-data-integrator-2.png)



## <a name="related-topics"></a><span data-ttu-id="cef53-202">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="cef53-202">Related topics</span></span>

[<span data-ttu-id="cef53-203">Prospect to cash</span><span class="sxs-lookup"><span data-stu-id="cef53-203">Prospect to cash</span></span>](prospect-to-cash.md)

[<span data-ttu-id="cef53-204">Sincronizar contas diretamente do Sales com clientes do Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="cef53-204">Synchronize accounts directly from Sales to customers in Finance and Operations</span></span>](accounts-template-mapping-direct.md)

[<span data-ttu-id="cef53-205">Sincronizar produtos diretamente do Finance and Operations com produtos no Sales</span><span class="sxs-lookup"><span data-stu-id="cef53-205">Synchronize products directly from Finance and Operations to products in Sales</span></span>](products-template-mapping-direct.md)

[<span data-ttu-id="cef53-206">Sincronizar contatos diretamente do Sales com contatos ou clientes do Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="cef53-206">Synchronize contacts directly from Sales to contacts or customers in Finance and Operations</span></span>](contacts-template-mapping-direct.md)

[<span data-ttu-id="cef53-207">Sincronizar cabeçalhos e linhas de fatura diretamente do Finance and Operations com o Sales</span><span class="sxs-lookup"><span data-stu-id="cef53-207">Synchronize sales invoice headers and lines directly from Finance and Operations to Sales</span></span>](sales-invoice-template-mapping-direct.md)




