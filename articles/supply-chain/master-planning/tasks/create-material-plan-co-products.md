---
title: Criar um plano de materiais para coprodutos
description: O planejador de produção planeja os requisitos de materiais para itens que são coprodutos de fórmula.
author: ShylaThompson
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, SalesOrderProcessingWorkspace, SalesCreateOrder, SalesTable, ReqCreatePlanWorkspace, ReqTransPlanCard, SysQueryForm, ReqTransPo
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b51e4b4d00da2babb5128d8c4c22139b0c1853d4
ms.sourcegitcommit: fa99a36c3d30d0c0577fd3f63ed6bf2f71599e40
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/20/2021
ms.locfileid: "5920720"
---
# <a name="create-a-material-plan-for-co-products"></a><span data-ttu-id="f57bd-103">Criar um plano de materiais para coprodutos</span><span class="sxs-lookup"><span data-stu-id="f57bd-103">Create a material plan for co products</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="f57bd-104">O planejador de produção planeja os requisitos de materiais para itens que são coprodutos de fórmula.</span><span class="sxs-lookup"><span data-stu-id="f57bd-104">The production planner plans the material requirements for items that are formula co-products.</span></span> <span data-ttu-id="f57bd-105">A empresa de dados demonstrativos utilizada para criar esse procedimento é a USP2.</span><span class="sxs-lookup"><span data-stu-id="f57bd-105">The demo data company used to create this procedure is USP2.</span></span>

## <a name="create-requirement-for-a-co-product"></a><span data-ttu-id="f57bd-106">Criar requisito para um coproduto</span><span class="sxs-lookup"><span data-stu-id="f57bd-106">Create requirement for a co-product</span></span>

1. <span data-ttu-id="f57bd-107">Vá para **Vendas e marketing \> Espaços de trabalho \> Consulta e processamento de ordem de venda**.</span><span class="sxs-lookup"><span data-stu-id="f57bd-107">Go to **Sales and marketing \> Workspaces \> Sales order processing and inquiry**.</span></span>
1. <span data-ttu-id="f57bd-108">Selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="f57bd-108">Select **New**.</span></span>
1. <span data-ttu-id="f57bd-109">Selecione **Ordem de venda**.</span><span class="sxs-lookup"><span data-stu-id="f57bd-109">Select **Sales order**.</span></span>
1. <span data-ttu-id="f57bd-110">No campo **Conta de cliente**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="f57bd-110">In the **Customer account** field, type a value.</span></span>
    * <span data-ttu-id="f57bd-111">Exemplo: US-001</span><span class="sxs-lookup"><span data-stu-id="f57bd-111">Example: US-001</span></span>  
1. <span data-ttu-id="f57bd-112">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="f57bd-112">Select **OK**.</span></span>
1. <span data-ttu-id="f57bd-113">No campo **Número de item**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="f57bd-113">In the **Item number** field, type a value.</span></span>
    * <span data-ttu-id="f57bd-114">Exemplo: P6003</span><span class="sxs-lookup"><span data-stu-id="f57bd-114">Example: P6003</span></span>  
1. <span data-ttu-id="f57bd-115">No campo **Quantidade.**, insira um número</span><span class="sxs-lookup"><span data-stu-id="f57bd-115">In the **Quantity** field, enter a number.</span></span>
    * <span data-ttu-id="f57bd-116">Exemplo: 50000</span><span class="sxs-lookup"><span data-stu-id="f57bd-116">Example: 50000</span></span>  
1. <span data-ttu-id="f57bd-117">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="f57bd-117">Select **Save**.</span></span>

## <a name="create-a-material-plan-for-co-products"></a><span data-ttu-id="f57bd-118">Criar um plano de materiais para coprodutos</span><span class="sxs-lookup"><span data-stu-id="f57bd-118">Create a material plan for co-products</span></span>

1. <span data-ttu-id="f57bd-119">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="f57bd-119">Close the page.</span></span>
1. <span data-ttu-id="f57bd-120">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="f57bd-120">Close the page.</span></span>
1. <span data-ttu-id="f57bd-121">Selecione **Planejamento mestre**.</span><span class="sxs-lookup"><span data-stu-id="f57bd-121">Select **Master planning**.</span></span>
1. <span data-ttu-id="f57bd-122">No campo **Plano**, selecione o botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="f57bd-122">In the **Plan** field, select the drop-down button to open the lookup.</span></span>
1. <span data-ttu-id="f57bd-123">Na lista, selecione o link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="f57bd-123">In the list, select the link in the selected row.</span></span>
    * <span data-ttu-id="f57bd-124">Exemplo: Plano Mestre</span><span class="sxs-lookup"><span data-stu-id="f57bd-124">Example: MasterPlan</span></span>  
1. <span data-ttu-id="f57bd-125">Selecione **Executar**.</span><span class="sxs-lookup"><span data-stu-id="f57bd-125">Select **Run**.</span></span>
1. <span data-ttu-id="f57bd-126">Expanda ou recolha a seção **Registros a serem incluídos**.</span><span class="sxs-lookup"><span data-stu-id="f57bd-126">Expand or collapse the **Records to include** section.</span></span>
1. <span data-ttu-id="f57bd-127">Selecione **Filtro**.</span><span class="sxs-lookup"><span data-stu-id="f57bd-127">Select **Filter**.</span></span>
1. <span data-ttu-id="f57bd-128">Na lista, selecione a linha para **Campo** = *Número do item*.</span><span class="sxs-lookup"><span data-stu-id="f57bd-128">In the list, select the row for **Field** = *Item number*.</span></span>
1. <span data-ttu-id="f57bd-129">No campo **Critérios**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="f57bd-129">In the **Criteria** field, type a value.</span></span>
    * <span data-ttu-id="f57bd-130">Exemplo: P6003</span><span class="sxs-lookup"><span data-stu-id="f57bd-130">Example: P6003</span></span>  
1. <span data-ttu-id="f57bd-131">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="f57bd-131">Select **OK**.</span></span>
1. <span data-ttu-id="f57bd-132">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="f57bd-132">Select **OK**.</span></span>
1. <span data-ttu-id="f57bd-133">Selecione **Ordens planejadas**.</span><span class="sxs-lookup"><span data-stu-id="f57bd-133">Select **Planned orders**.</span></span>
1. <span data-ttu-id="f57bd-134">Use o Filtro Rápido para localizar registros.</span><span class="sxs-lookup"><span data-stu-id="f57bd-134">Use the Quick Filter to find records.</span></span> <span data-ttu-id="f57bd-135">Por exemplo, filtre o campo **Número do item** com um valor de 'P6000'.</span><span class="sxs-lookup"><span data-stu-id="f57bd-135">For example, filter on the **Item number** field with a value of 'P6000'.</span></span>
    * <span data-ttu-id="f57bd-136">Filtre pelo item de fórmula que contenha uma ordem de venda como coproduto do item que você criou.</span><span class="sxs-lookup"><span data-stu-id="f57bd-136">Filter by the formula item that has as co-product of the item that you created a sales order for.</span></span>  
1. <span data-ttu-id="f57bd-137">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="f57bd-137">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="f57bd-138">Selecione uma das linhas retornadas pelo filtro.</span><span class="sxs-lookup"><span data-stu-id="f57bd-138">Select any of the rows returned by the filter.</span></span>  
1. <span data-ttu-id="f57bd-139">Na lista, selecione o link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="f57bd-139">In the list, select the link in the selected row.</span></span>
1. <span data-ttu-id="f57bd-140">Expanda a seção **Vinculação**.</span><span class="sxs-lookup"><span data-stu-id="f57bd-140">Expand the **Pegging** section.</span></span>
1. <span data-ttu-id="f57bd-141">Na lista, selecione o link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="f57bd-141">In the list, select the link in the selected row.</span></span>
    * <span data-ttu-id="f57bd-142">A ordem planejada está vinculada a ordem de venda para o coproduto.</span><span class="sxs-lookup"><span data-stu-id="f57bd-142">The planned order is pegged to the sales order for the co-product.</span></span>  
1. <span data-ttu-id="f57bd-143">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="f57bd-143">Close the page.</span></span>

## <a name="create-a-second-requirement-for-a-co-product"></a><span data-ttu-id="f57bd-144">Crie um segundo requisito para um coproduto</span><span class="sxs-lookup"><span data-stu-id="f57bd-144">Create a second requirement for a co-product</span></span>

1. <span data-ttu-id="f57bd-145">Vá para **Vendas e marketing \> Espaços de trabalho \> Consulta e processamento de ordem de venda**.</span><span class="sxs-lookup"><span data-stu-id="f57bd-145">Go to **Sales and marketing \> Workspaces \> Sales order processing and inquiry**.</span></span>
1. <span data-ttu-id="f57bd-146">Selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="f57bd-146">Select **New**.</span></span>
1. <span data-ttu-id="f57bd-147">Selecione **Ordem de venda**.</span><span class="sxs-lookup"><span data-stu-id="f57bd-147">Select **Sales order**.</span></span>
1. <span data-ttu-id="f57bd-148">No campo **Conta de cliente**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="f57bd-148">In the **Customer account** field, type a value.</span></span>
    * <span data-ttu-id="f57bd-149">Exemplo: US-001</span><span class="sxs-lookup"><span data-stu-id="f57bd-149">Example: US-001</span></span>  
1. <span data-ttu-id="f57bd-150">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="f57bd-150">Select **OK**.</span></span>
1. <span data-ttu-id="f57bd-151">No campo **Número de item**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="f57bd-151">In the **Item number** field, type a value.</span></span>
    * <span data-ttu-id="f57bd-152">Exemplo: P6003</span><span class="sxs-lookup"><span data-stu-id="f57bd-152">Example: P6003</span></span>  
1. <span data-ttu-id="f57bd-153">No campo **Quantidade.**, insira um número</span><span class="sxs-lookup"><span data-stu-id="f57bd-153">In the **Quantity** field, enter a number.</span></span>
    * <span data-ttu-id="f57bd-154">Exemplo: 50000</span><span class="sxs-lookup"><span data-stu-id="f57bd-154">Example: 50000</span></span>  
1. <span data-ttu-id="f57bd-155">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="f57bd-155">Select **Save**.</span></span>

## <a name="create-a-second-material-plan-for-co-products"></a><span data-ttu-id="f57bd-156">Crie um segundo plano de materiais para coprodutos</span><span class="sxs-lookup"><span data-stu-id="f57bd-156">Create a second material plan for co-products</span></span>

1. <span data-ttu-id="f57bd-157">No campo **Plano**, selecione o botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="f57bd-157">In the **Plan** field, select the drop-down button to open the lookup.</span></span>
2. <span data-ttu-id="f57bd-158">Na lista, selecione o link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="f57bd-158">In the list, select the link in the selected row.</span></span>
    * <span data-ttu-id="f57bd-159">Exemplo: Plano Mestre</span><span class="sxs-lookup"><span data-stu-id="f57bd-159">Example: MasterPlan</span></span>  
3. <span data-ttu-id="f57bd-160">Selecione **Executar**.</span><span class="sxs-lookup"><span data-stu-id="f57bd-160">Select **Run**.</span></span>
4. <span data-ttu-id="f57bd-161">Expanda ou recolha a seção **Registros a serem incluídos**.</span><span class="sxs-lookup"><span data-stu-id="f57bd-161">Expand or collapse the **Records to include** section.</span></span>
5. <span data-ttu-id="f57bd-162">Selecione **Filtro**.</span><span class="sxs-lookup"><span data-stu-id="f57bd-162">Select **Filter**.</span></span>
6. <span data-ttu-id="f57bd-163">Na lista, selecione a linha para **Campo** = *Número do item*.</span><span class="sxs-lookup"><span data-stu-id="f57bd-163">In the list, select the row for **Field** = *Item number*.</span></span>
7. <span data-ttu-id="f57bd-164">No campo *Critérios*, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="f57bd-164">In the *Criteria* field, type a value.</span></span>
    * <span data-ttu-id="f57bd-165">Exemplo: P6003</span><span class="sxs-lookup"><span data-stu-id="f57bd-165">Example: P6003</span></span>  
8. <span data-ttu-id="f57bd-166">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="f57bd-166">Select **OK**.</span></span>
9. <span data-ttu-id="f57bd-167">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="f57bd-167">Select **OK**.</span></span>
10. <span data-ttu-id="f57bd-168">Selecione **Ordens planejadas**.</span><span class="sxs-lookup"><span data-stu-id="f57bd-168">Select **Planned orders**.</span></span>
11. <span data-ttu-id="f57bd-169">Use o Filtro Rápido para localizar registros.</span><span class="sxs-lookup"><span data-stu-id="f57bd-169">Use the Quick Filter to find records.</span></span> <span data-ttu-id="f57bd-170">Por exemplo, filtre o campo **Número do item** com um valor de 'P6000'.</span><span class="sxs-lookup"><span data-stu-id="f57bd-170">For example, filter on the **Item number** field with a value of 'P6000'.</span></span>
    * <span data-ttu-id="f57bd-171">Filtre pelo item de fórmula que contenha uma ordem de venda como coproduto do item que você criou.</span><span class="sxs-lookup"><span data-stu-id="f57bd-171">Filter by the formula item that has as co-product of the item that you created a sales order for.</span></span>  
12. <span data-ttu-id="f57bd-172">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="f57bd-172">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="f57bd-173">Selecione uma das linhas retornadas pelo filtro.</span><span class="sxs-lookup"><span data-stu-id="f57bd-173">Select any of the rows returned by the filter.</span></span>  
13. <span data-ttu-id="f57bd-174">Na lista, selecione o link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="f57bd-174">In the list, select the link in the selected row.</span></span>
14. <span data-ttu-id="f57bd-175">Expanda ou recolha a seção **Vinculação**.</span><span class="sxs-lookup"><span data-stu-id="f57bd-175">Expand or collapse the **Pegging** section.</span></span>
15. <span data-ttu-id="f57bd-176">Na lista, selecione o link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="f57bd-176">In the list, select the link in the selected row.</span></span>
    * <span data-ttu-id="f57bd-177">A ordem planejada está vinculada a ordem de venda para o coproduto.</span><span class="sxs-lookup"><span data-stu-id="f57bd-177">The planned order is pegged to the sales order for the co-product.</span></span>  
16. <span data-ttu-id="f57bd-178">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="f57bd-178">Close the page.</span></span>
17. <span data-ttu-id="f57bd-179">Selecione **Planejamento mestre**.</span><span class="sxs-lookup"><span data-stu-id="f57bd-179">Select **Master planning**.</span></span>
18. <span data-ttu-id="f57bd-180">Vá para **Planejamento mestre \> Configurar \> Parâmetros de planejamento mestre**.</span><span class="sxs-lookup"><span data-stu-id="f57bd-180">Go to **Master planning \> Setup \> Master planning parameters**.</span></span>
19. <span data-ttu-id="f57bd-181">Selecione *Não* no campo **Desabilitar todos os processos de planejamento**.</span><span class="sxs-lookup"><span data-stu-id="f57bd-181">Select *No* in the **Disable all planning processes** field.</span></span>
20. <span data-ttu-id="f57bd-182">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="f57bd-182">Close the page.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]