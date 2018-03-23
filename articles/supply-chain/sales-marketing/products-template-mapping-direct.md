---
title: Sincronizar produtos diretamente do Finance and Operations com produtos no Sales
description: "Este tópico discute os modelos e as tarefas subjacentes usadas para sincronizar produtos do Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition, para o Microsoft Dynamics 365 for Sales."
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
ms.sourcegitcommit: 0d409b3b7f19ca31d9c720bca191f1ddba81caa3
ms.openlocfilehash: def88c291538e3ef278c51e4b87462782e222de2
ms.contentlocale: pt-br
ms.lasthandoff: 03/13/2018

---

# <a name="synchronize-products-directly-from-finance-and-operations-to-products-in-sales"></a><span data-ttu-id="4b8c3-103">Sincronizar produtos diretamente do Finance and Operations com produtos no Sales</span><span class="sxs-lookup"><span data-stu-id="4b8c3-103">Synchronize products directly from Finance and Operations to products in Sales</span></span>

[!include[banner](../includes/banner.md)]

> [!NOTE]
> <span data-ttu-id="4b8c3-104">Antes de usar a solução Prospect to cash, você deve familiarizar-se com a [Integração de dados do Dynamics 365](/common-data-service/entity-reference/dynamics-365-integration).</span><span class="sxs-lookup"><span data-stu-id="4b8c3-104">Before you can use the Prospect to cash solution, you should be familiar with [Dynamics 365 Data integration](/common-data-service/entity-reference/dynamics-365-integration).</span></span>

<span data-ttu-id="4b8c3-105">Este tópico discute os modelos e as tarefas subjacentes usadas para sincronizar produtos diretamente do Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition, para o Microsoft Dynamics 365 for Sales.</span><span class="sxs-lookup"><span data-stu-id="4b8c3-105">This topic discusses the templates and underlying tasks that are used to synchronize products directly from Microsoft Dynamics 365 for Finance and Operations, Enterprise edition, to Microsoft Dynamics 365 for Sales.</span></span>

## <a name="data-flow-in-prospect-to-cash"></a><span data-ttu-id="4b8c3-106">Fluxo de dados no Prospect to cash</span><span class="sxs-lookup"><span data-stu-id="4b8c3-106">Data flow in Prospect to cash</span></span>

<span data-ttu-id="4b8c3-107">A solução Prospect to cash usa o recurso de integração de dados sincronizar dados nas instâncias do Finance and Operations e do Sales.</span><span class="sxs-lookup"><span data-stu-id="4b8c3-107">The Prospect to cash solution uses the Data integration feature to synchronize data across instances of Finance and Operations and Sales.</span></span> <span data-ttu-id="4b8c3-108">Os modelos Prospect to cash que estão disponíveis com o recurso Integração de dados permitem o fluxo de dados sobre contas, contatos, produtos, cotações de vendas, ordens de venda e faturas de vendas entre o Finance and Operations e o Sales.</span><span class="sxs-lookup"><span data-stu-id="4b8c3-108">The Prospect to cash templates that are available with the Data integration feature enable the flow of data about accounts, contacts, products, sales quotations, sales orders, and sales invoices between Finance and Operations and Sales.</span></span> <span data-ttu-id="4b8c3-109">A ilustração a seguir mostra como os dados são sincronizados entre o Finance and Operations e o Sales.</span><span class="sxs-lookup"><span data-stu-id="4b8c3-109">The following illustration shows how the data is synchronized between Finance and Operations and Sales.</span></span>

<span data-ttu-id="4b8c3-110">[![Fluxo de dados em Prospect to cash](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)</span><span class="sxs-lookup"><span data-stu-id="4b8c3-110">[![Data flow in Prospect to cash](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="4b8c3-111">Modelos e tarefas</span><span class="sxs-lookup"><span data-stu-id="4b8c3-111">Templates and tasks</span></span>

<span data-ttu-id="4b8c3-112">Para acessar os modelos disponíveis, abra o [Centro de administração de PowerApps](https://preview.admin.powerapps.com/dataintegration).</span><span class="sxs-lookup"><span data-stu-id="4b8c3-112">To access the available templates, open [PowerApps Admin Center](https://preview.admin.powerapps.com/dataintegration).</span></span> <span data-ttu-id="4b8c3-113">Selecione **Projetos** e, no canto superior direito, selecione **Novo projeto** para selecionar modelos públicos.</span><span class="sxs-lookup"><span data-stu-id="4b8c3-113">Select **Projects**, and then, in the upper-right corner, select **New project** to select public templates.</span></span>

<span data-ttu-id="4b8c3-114">O modelo e as tarefas subjacentes a seguir são usados para sincronizar produtos do Finance and Operations para o Sales.</span><span class="sxs-lookup"><span data-stu-id="4b8c3-114">The following template and underlying tasks are used to synchronize products from Finance and Operations to Sales.</span></span>

- <span data-ttu-id="4b8c3-115">**Nome do modelo na Integração de dados:** Produtos (Fin and Ops para Sales) – Direto</span><span class="sxs-lookup"><span data-stu-id="4b8c3-115">**Name of the template in Data integration:** Products (Fin and Ops to Sales) - Direct</span></span>
- <span data-ttu-id="4b8c3-116">**Nome da tarefa no projeto de Integração de dados:** Produtos</span><span class="sxs-lookup"><span data-stu-id="4b8c3-116">**Name of the task in the Data integration project:** Products</span></span>

<span data-ttu-id="4b8c3-117">Nenhuma tarefa de sincronização é necessária para que a sincronização de produtos ocorra.</span><span class="sxs-lookup"><span data-stu-id="4b8c3-117">No synchronization tasks are required before product synchronization can occur.</span></span>

## <a name="entity-set"></a><span data-ttu-id="4b8c3-118">Conjunto de entidades</span><span class="sxs-lookup"><span data-stu-id="4b8c3-118">Entity set</span></span>

| <span data-ttu-id="4b8c3-119">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="4b8c3-119">Finance and Operations</span></span>     | <span data-ttu-id="4b8c3-120">Vendas</span><span class="sxs-lookup"><span data-stu-id="4b8c3-120">Sales</span></span>    |
|----------------------------|----------|
| <span data-ttu-id="4b8c3-121">Produtos liberados comercializáveis</span><span class="sxs-lookup"><span data-stu-id="4b8c3-121">Sellable released products</span></span> | <span data-ttu-id="4b8c3-122">Produtos</span><span class="sxs-lookup"><span data-stu-id="4b8c3-122">Products</span></span> |

## <a name="entity-flow"></a><span data-ttu-id="4b8c3-123">Fluxo de entidades</span><span class="sxs-lookup"><span data-stu-id="4b8c3-123">Entity flow</span></span>

<span data-ttu-id="4b8c3-124">Os produtos são gerenciados no Finance and Operations e sincronizados para o Sales.</span><span class="sxs-lookup"><span data-stu-id="4b8c3-124">Products are managed in Finance and Operations and synchronized to Sales.</span></span> <span data-ttu-id="4b8c3-125">A entidade de dados **Produtos lançados comercializáveis** no Finance and Operations só exporta produtos *comercializáveis*.</span><span class="sxs-lookup"><span data-stu-id="4b8c3-125">The **Sellable released products** data entity in Finance and Operations exports only products that are *sellable*.</span></span> <span data-ttu-id="4b8c3-126">Os produtos comercializáveis são produtos contendo as informações necessárias para serem usados em uma ordem de venda.</span><span class="sxs-lookup"><span data-stu-id="4b8c3-126">Sellable products are products that have the information that they require in order to be used on a sales order.</span></span> <span data-ttu-id="4b8c3-127">As mesmas regras se aplicam quando um produto é validado usando a função **Validar** na página **Produto liberado**.</span><span class="sxs-lookup"><span data-stu-id="4b8c3-127">The same rules apply when a product is validated by using the **Validate** function on the **Released product** page.</span></span>

<span data-ttu-id="4b8c3-128">O número do produto é usado como uma chave.</span><span class="sxs-lookup"><span data-stu-id="4b8c3-128">The product number is used as a key.</span></span> <span data-ttu-id="4b8c3-129">Portanto, quando variantes do produto são sincronizadas para o Sales, cada variante do produto tem uma ID de produto individual.</span><span class="sxs-lookup"><span data-stu-id="4b8c3-129">Therefore, when product variants are synchronized to Sales, each product variant has an individual product ID.</span></span>

## <a name="prospect-to-cash-solution-for-sales"></a><span data-ttu-id="4b8c3-130">Solução Prospect to cash para o Sales</span><span class="sxs-lookup"><span data-stu-id="4b8c3-130">Prospect to cash solution for Sales</span></span>

<span data-ttu-id="4b8c3-131">No Sales, um novo campo **É Mantido Externamente** foi adicionado em produtos para indicar que determinado produto é mantido externamente.</span><span class="sxs-lookup"><span data-stu-id="4b8c3-131">In Sales, a new **Is Externally Maintained** field has been added on products to indicate that a given product is maintained externally.</span></span> <span data-ttu-id="4b8c3-132">Por padrão, o valor é definido como **Sim** durante uma importação para o Sales.</span><span class="sxs-lookup"><span data-stu-id="4b8c3-132">By default, the value is set to **Yes** during an import to Sales.</span></span> <span data-ttu-id="4b8c3-133">Os valores a seguir estão disponíveis:</span><span class="sxs-lookup"><span data-stu-id="4b8c3-133">The following values are available:</span></span>

- <span data-ttu-id="4b8c3-134">**Sim** – Produto originado do Finance and Operations e não será editável no Sales.</span><span class="sxs-lookup"><span data-stu-id="4b8c3-134">**Yes** – The product originated from Finance and Operations and won't be editable in Sales.</span></span>
- <span data-ttu-id="4b8c3-135">**Não** – O produto foi inserido diretamente no Sales.</span><span class="sxs-lookup"><span data-stu-id="4b8c3-135">**No** – The product was entered directly in Sales.</span></span>
- <span data-ttu-id="4b8c3-136">**(Em branco)** – O produto existia no Sales antes de a solução Prospect to cash ser habilitada.</span><span class="sxs-lookup"><span data-stu-id="4b8c3-136">**(Blank)** – The product existed in Sales before the Prospect to cash solution was enabled.</span></span>

<span data-ttu-id="4b8c3-137">O campo **É Mantido Externamente** ajuda a garantir que somente cotações e ordens de venda com produtos mantidos externamente sejam sincronizadas para o Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="4b8c3-137">The **Is Externally Maintained** field helps guarantee that only quotations and sales orders that have externally maintained products will be synchronized to Finance and Operations.</span></span>

<span data-ttu-id="4b8c3-138">Os Produtos mantidos externamente são adicionados de forma automática à primeira lista de preços válida com a mesma moeda.</span><span class="sxs-lookup"><span data-stu-id="4b8c3-138">Externally maintained products are automatically added to the first valid price list that has the same currency.</span></span> <span data-ttu-id="4b8c3-139">Listas de preços são organizadas em ordem alfabética por nome.</span><span class="sxs-lookup"><span data-stu-id="4b8c3-139">Price lists are organized alphabetically by name.</span></span> <span data-ttu-id="4b8c3-140">O preço de venda do produto do Finance and Operations é usado como o preço na lista de preços.</span><span class="sxs-lookup"><span data-stu-id="4b8c3-140">The product sales price from Finance and Operations is used as the price on the price list.</span></span> <span data-ttu-id="4b8c3-141">Então, é preciso existir uma lista de preços no Sales para cada moeda de venda de produto no Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="4b8c3-141">Therefore, there must be a price list in Sales for every product sales currency in Finance and Operations.</span></span> <span data-ttu-id="4b8c3-142">A moeda dos produtos liberados comercializáveis é definida como a moeda contábil da entidade legal da qual o produto é exportado.</span><span class="sxs-lookup"><span data-stu-id="4b8c3-142">The currency on the released sellable products is set to the accounting currency in the legal entity that the product is exported from.</span></span>

> [!NOTE]
> <span data-ttu-id="4b8c3-143">A sincronização de produto só terá êxito se houver uma lista de preços com uma moeda correspondente.</span><span class="sxs-lookup"><span data-stu-id="4b8c3-143">Product synchronization won't succeed unless there is a price list that has a matching currency.</span></span>

## <a name="preconditions-and-mapping-setup"></a><span data-ttu-id="4b8c3-144">Precondições e configuração de mapeamento</span><span class="sxs-lookup"><span data-stu-id="4b8c3-144">Preconditions and mapping setup</span></span>

- <span data-ttu-id="4b8c3-145">Antes de executar a sincronização pela primeira vez, preencha a Tabela de produtos distintos para produtos existentes no Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="4b8c3-145">Before you run the synchronization for the first time, you must fill the Distinct product table for existing products in Finance and Operations.</span></span> <span data-ttu-id="4b8c3-146">Os produtos existentes não serão sincronizados até que o trabalho seja concluído.</span><span class="sxs-lookup"><span data-stu-id="4b8c3-146">Existing products won't be synchronized until this job is completed.</span></span>

    1. <span data-ttu-id="4b8c3-147">No Finance and Operations, use Pesquisar para procurar **Preencher tabela de produtos distintos**.</span><span class="sxs-lookup"><span data-stu-id="4b8c3-147">In Finance and Operations, use Search to search for **Populate distinct product table**.</span></span>
    2. <span data-ttu-id="4b8c3-148">Selecione **Preencher tabela de produtos distintos** para executar o trabalho.</span><span class="sxs-lookup"><span data-stu-id="4b8c3-148">Select **Populate distinct product table** to run the job.</span></span> <span data-ttu-id="4b8c3-149">Este trabalho deve ser executado apenas uma vez.</span><span class="sxs-lookup"><span data-stu-id="4b8c3-149">This job must be run only one time.</span></span>

- <span data-ttu-id="4b8c3-150">Verifique se existe o mapa de valores obrigatório para a unidade de medida (UDM) de vendas entre o Finance and Operations e o Sales no mapeamento de **SalesUnitSymbol** para **DefaultUnit (Name)**.</span><span class="sxs-lookup"><span data-stu-id="4b8c3-150">Make sure that the required value map for the selling unit of measure (UOM) between Finance and Operations and Sales exists in the mapping of **SalesUnitSymbol** to **DefaultUnit (Name)**.</span></span>
- <span data-ttu-id="4b8c3-151">Atualize o mapa de valores para **Grupo de unidades** (**defaultuomscheduleid.name**) para que corresponda a **Grupos de unidades** no Sales.</span><span class="sxs-lookup"><span data-stu-id="4b8c3-151">Update the value map for **Unit group** (**defaultuomscheduleid.name**) so that it matches **Unit groups** in Sales.</span></span>

    <span data-ttu-id="4b8c3-152">O valor do modelo padrão é **Unidade padrão**.</span><span class="sxs-lookup"><span data-stu-id="4b8c3-152">The default template value is **Default unit**.</span></span>

- <span data-ttu-id="4b8c3-153">Verifique se as UDMs de venda para todos os produtos do Finance and Operations existem no Sales.</span><span class="sxs-lookup"><span data-stu-id="4b8c3-153">Make sure that the selling UOMs for all products from Finance and Operations exist in Sales.</span></span>
- <span data-ttu-id="4b8c3-154">Verifique se existem listas de preços no Sales para cada moeda de venda de produto no Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="4b8c3-154">Make sure that price lists exist in Sales for every product sales currency in Finance and Operations.</span></span>
- <span data-ttu-id="4b8c3-155">Quando os produtos são criados no Sales, eles podem ter um status **Rascunho** ou **Ativo**.</span><span class="sxs-lookup"><span data-stu-id="4b8c3-155">When products are created in Sales, they can have a status of **Draft** or **Active**.</span></span> <span data-ttu-id="4b8c3-156">O comportamento é controlado em **Configurações** > **Administração** > **Configurações do sistema** > **Vendas** no Sales.</span><span class="sxs-lookup"><span data-stu-id="4b8c3-156">The behavior is controlled at **Settings** > **Administration** > **System settings** > **Sales** in Sales.</span></span>

    <span data-ttu-id="4b8c3-157">Produtos com o status **Rascunho** quando são criados devem ser ativados antes de serem adicionados às cotações ou ordens de venda.</span><span class="sxs-lookup"><span data-stu-id="4b8c3-157">Products that have **Draft** status when they are created must be activated before they can be added to quotations or sales orders.</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="4b8c3-158">Mapeamento de modelo na Integração de dados</span><span class="sxs-lookup"><span data-stu-id="4b8c3-158">Template mapping in Data integration</span></span>

<span data-ttu-id="4b8c3-159">A ilustração a seguir mostra um exemplo de um mapeamento de modelo na Integração de dados.</span><span class="sxs-lookup"><span data-stu-id="4b8c3-159">The following illustration shows an example of a template mapping in Data integration.</span></span> 

> [!NOTE]
> <span data-ttu-id="4b8c3-160">O mapeamento mostra quais informações de campo serão sincronizadas do Sales com o Finance and Operations..</span><span class="sxs-lookup"><span data-stu-id="4b8c3-160">The mapping shows which field information will be synchronized from Sales to Finance and Operations.</span></span>

![Mapeamento de modelo no Integrador de dados](./media/products-direct-template-mapping-data-integrator-1.png)


## <a name="related-topics"></a><span data-ttu-id="4b8c3-162">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="4b8c3-162">Related topics</span></span>

[<span data-ttu-id="4b8c3-163">Prospect to cash</span><span class="sxs-lookup"><span data-stu-id="4b8c3-163">Prospect to cash</span></span>](prospect-to-cash.md)

[<span data-ttu-id="4b8c3-164">Sincronizar contas diretamente do Sales com clientes do Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="4b8c3-164">Synchronize accounts directly from Sales to customers in Finance and Operations</span></span>](accounts-template-mapping-direct.md)

[<span data-ttu-id="4b8c3-165">Sincronizar contatos diretamente do Sales com contatos ou clientes do Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="4b8c3-165">Synchronize contacts directly from Sales to contacts or customers in Finance and Operations</span></span>](contacts-template-mapping-direct.md)

[<span data-ttu-id="4b8c3-166">Sincronizar cabeçalhos e linhas de ordem de venda diretamente do Finance and Operations com o Sales</span><span class="sxs-lookup"><span data-stu-id="4b8c3-166">Synchronize sales order headers and lines directly from Finance and Operations to Sales</span></span>](sales-order-template-mapping-direct-two-ways.md)

[<span data-ttu-id="4b8c3-167">Sincronizar cabeçalhos e linhas de fatura diretamente do Finance and Operations com o Sales</span><span class="sxs-lookup"><span data-stu-id="4b8c3-167">Synchronize sales invoice headers and lines directly from Finance and Operations to Sales</span></span>](sales-invoice-template-mapping-direct.md)




