--- 
title: Criar um plano de materiais para coprodutos
description: "O planejador de produção planeja os requisitos de materiais para itens que são coprodutos de fórmula."
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: DefaultDashboard, SalesOrderProcessingWorkspace, SalesCreateOrder, SalesTable, ReqCreatePlanWorkspace, ReqTransPlanCard, SysQueryForm, ReqTransPo
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0312b8cfadd45f8e59225e9daba78b9e216cff51
ms.openlocfilehash: 2958f1e5c2e8a0cfa9cc6312f688d3b11b8e013c
ms.contentlocale: pt-br
ms.lasthandoff: 09/14/2018

---
# <a name="create-a-material-plan-for-co-products"></a><span data-ttu-id="0793b-103">Criar um plano de materiais para coprodutos</span><span class="sxs-lookup"><span data-stu-id="0793b-103">Create a material plan for co products</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="0793b-104">O planejador de produção planeja os requisitos de materiais para itens que são coprodutos de fórmula.</span><span class="sxs-lookup"><span data-stu-id="0793b-104">The production planner plans the material requirements for items that are formula co-products.</span></span> <span data-ttu-id="0793b-105">A empresa de dados demonstrativos utilizada para criar esse procedimento é a USP2.</span><span class="sxs-lookup"><span data-stu-id="0793b-105">The demo data company used to create this procedure is USP2.</span></span>


## <a name="create-requirement-for-a-co-product"></a><span data-ttu-id="0793b-106">Criar requisito para um coproduto</span><span class="sxs-lookup"><span data-stu-id="0793b-106">Create requirement for a co-product</span></span>
1. <span data-ttu-id="0793b-107">Ir para o painel Padrão.</span><span class="sxs-lookup"><span data-stu-id="0793b-107">Go to Default dashboard.</span></span>
2. <span data-ttu-id="0793b-108">Clique em Consulta e processamento de ordem de venda.</span><span class="sxs-lookup"><span data-stu-id="0793b-108">Click Sales order processing and inquiry.</span></span>
3. <span data-ttu-id="0793b-109">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="0793b-109">Click New.</span></span>
4. <span data-ttu-id="0793b-110">Clique Ordem de venda.</span><span class="sxs-lookup"><span data-stu-id="0793b-110">Click Sales order.</span></span>
5. <span data-ttu-id="0793b-111">No campo Conta de cliente, insira um valor.</span><span class="sxs-lookup"><span data-stu-id="0793b-111">In the Customer account field, type a value.</span></span>
    * <span data-ttu-id="0793b-112">Exemplo: US-001</span><span class="sxs-lookup"><span data-stu-id="0793b-112">Example: US-001</span></span>  
6. <span data-ttu-id="0793b-113">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="0793b-113">Click OK.</span></span>
7. <span data-ttu-id="0793b-114">No campo Número de item, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="0793b-114">In the Item number field, type a value.</span></span>
    * <span data-ttu-id="0793b-115">Exemplo: P6003</span><span class="sxs-lookup"><span data-stu-id="0793b-115">Example: P6003</span></span>  
8. <span data-ttu-id="0793b-116">No campo Quantidade, insira um número.</span><span class="sxs-lookup"><span data-stu-id="0793b-116">In the Quantity field, enter a number.</span></span>
    * <span data-ttu-id="0793b-117">Exemplo: 50000</span><span class="sxs-lookup"><span data-stu-id="0793b-117">Example: 50000</span></span>  
9. <span data-ttu-id="0793b-118">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="0793b-118">Click Save.</span></span>

## <a name="create-a-material-plan-for-co-products"></a><span data-ttu-id="0793b-119">Criar um plano de materiais para coprodutos</span><span class="sxs-lookup"><span data-stu-id="0793b-119">Create a material plan for co-products</span></span>
1. <span data-ttu-id="0793b-120">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="0793b-120">Close the page.</span></span>
2. <span data-ttu-id="0793b-121">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="0793b-121">Close the page.</span></span>
3. <span data-ttu-id="0793b-122">Clique em Planejamento mestre.</span><span class="sxs-lookup"><span data-stu-id="0793b-122">Click Master planning.</span></span>
4. <span data-ttu-id="0793b-123">No campo Plano, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="0793b-123">In the Plan field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="0793b-124">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="0793b-124">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="0793b-125">Exemplo: Plano Mestre</span><span class="sxs-lookup"><span data-stu-id="0793b-125">Example: MasterPlan</span></span>  
6. <span data-ttu-id="0793b-126">Clique em Executar.</span><span class="sxs-lookup"><span data-stu-id="0793b-126">Click Run.</span></span>
7. <span data-ttu-id="0793b-127">Expanda ou recolha a seção de Registros a serem incluídos.</span><span class="sxs-lookup"><span data-stu-id="0793b-127">Expand or collapse the Records to include section.</span></span>
8. <span data-ttu-id="0793b-128">Clique em Filtro.</span><span class="sxs-lookup"><span data-stu-id="0793b-128">Click Filter.</span></span>
9. <span data-ttu-id="0793b-129">Na lista, selecione a linha para Campo = Número do item.</span><span class="sxs-lookup"><span data-stu-id="0793b-129">In the list, select the row for Field = Item number.</span></span>
10. <span data-ttu-id="0793b-130">No campo Critérios, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="0793b-130">In the Criteria field, type a value.</span></span>
    * <span data-ttu-id="0793b-131">Exemplo: P6003</span><span class="sxs-lookup"><span data-stu-id="0793b-131">Example: P6003</span></span>  
11. <span data-ttu-id="0793b-132">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="0793b-132">Click OK.</span></span>
12. <span data-ttu-id="0793b-133">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="0793b-133">Click OK.</span></span>
13. <span data-ttu-id="0793b-134">Clique em Ordens planejadas.</span><span class="sxs-lookup"><span data-stu-id="0793b-134">Click Planned orders.</span></span>
14. <span data-ttu-id="0793b-135">Use o Filtro Rápido para localizar registros.</span><span class="sxs-lookup"><span data-stu-id="0793b-135">Use the Quick Filter to find records.</span></span> <span data-ttu-id="0793b-136">Por exemplo, filtre o campo Número do item com um valor de 'P6000'.</span><span class="sxs-lookup"><span data-stu-id="0793b-136">For example, filter on the Item number field with a value of 'P6000'.</span></span>
    * <span data-ttu-id="0793b-137">Filtre pelo item de fórmula que contenha uma ordem de venda como coproduto do item que você criou.</span><span class="sxs-lookup"><span data-stu-id="0793b-137">Filter by the formula item that has as co-product of the item that you created a sales order for.</span></span>  
15. <span data-ttu-id="0793b-138">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="0793b-138">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="0793b-139">Selecione uma das linhas retornadas pelo filtro.</span><span class="sxs-lookup"><span data-stu-id="0793b-139">Select any of the rows returned by the filter.</span></span>  
16. <span data-ttu-id="0793b-140">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="0793b-140">In the list, click the link in the selected row.</span></span>
17. <span data-ttu-id="0793b-141">Expandir ou recolher a seção Vinculação.</span><span class="sxs-lookup"><span data-stu-id="0793b-141">Expand or collapse the Pegging section.</span></span>
18. <span data-ttu-id="0793b-142">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="0793b-142">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="0793b-143">A ordem planejada está vinculada a ordem de venda para o coproduto.</span><span class="sxs-lookup"><span data-stu-id="0793b-143">The planned order is pegged to the sales order for the co-product.</span></span>  
19. <span data-ttu-id="0793b-144">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="0793b-144">Close the page.</span></span>

## <a name="create-requirement-for-a-co-product"></a><span data-ttu-id="0793b-145">Criar requisito para um coproduto</span><span class="sxs-lookup"><span data-stu-id="0793b-145">Create requirement for a co-product</span></span>
1. <span data-ttu-id="0793b-146">Ir para o painel Padrão.</span><span class="sxs-lookup"><span data-stu-id="0793b-146">Go to Default dashboard.</span></span>
2. <span data-ttu-id="0793b-147">Clique em Consulta e processamento de ordem de venda.</span><span class="sxs-lookup"><span data-stu-id="0793b-147">Click Sales order processing and inquiry.</span></span>
3. <span data-ttu-id="0793b-148">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="0793b-148">Click New.</span></span>
4. <span data-ttu-id="0793b-149">Clique Ordem de venda.</span><span class="sxs-lookup"><span data-stu-id="0793b-149">Click Sales order.</span></span>
5. <span data-ttu-id="0793b-150">No campo Conta de cliente, insira um valor.</span><span class="sxs-lookup"><span data-stu-id="0793b-150">In the Customer account field, type a value.</span></span>
    * <span data-ttu-id="0793b-151">Exemplo: US-001</span><span class="sxs-lookup"><span data-stu-id="0793b-151">Example: US-001</span></span>  
6. <span data-ttu-id="0793b-152">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="0793b-152">Click OK.</span></span>
7. <span data-ttu-id="0793b-153">No campo Número de item, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="0793b-153">In the Item number field, type a value.</span></span>
    * <span data-ttu-id="0793b-154">Exemplo: P6003</span><span class="sxs-lookup"><span data-stu-id="0793b-154">Example: P6003</span></span>  
8. <span data-ttu-id="0793b-155">No campo Quantidade, insira um número.</span><span class="sxs-lookup"><span data-stu-id="0793b-155">In the Quantity field, enter a number.</span></span>
    * <span data-ttu-id="0793b-156">Exemplo: 50000</span><span class="sxs-lookup"><span data-stu-id="0793b-156">Example: 50000</span></span>  
9. <span data-ttu-id="0793b-157">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="0793b-157">Click Save.</span></span>

## <a name="create-a-material-plan-for-co-products"></a><span data-ttu-id="0793b-158">Criar um plano de materiais para coprodutos</span><span class="sxs-lookup"><span data-stu-id="0793b-158">Create a material plan for co-products</span></span>
1. <span data-ttu-id="0793b-159">No campo Plano, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="0793b-159">In the Plan field, click the drop-down button to open the lookup.</span></span>
2. <span data-ttu-id="0793b-160">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="0793b-160">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="0793b-161">Exemplo: Plano Mestre</span><span class="sxs-lookup"><span data-stu-id="0793b-161">Example: MasterPlan</span></span>  
3. <span data-ttu-id="0793b-162">Clique em Executar.</span><span class="sxs-lookup"><span data-stu-id="0793b-162">Click Run.</span></span>
4. <span data-ttu-id="0793b-163">Expanda ou recolha a seção de Registros a serem incluídos.</span><span class="sxs-lookup"><span data-stu-id="0793b-163">Expand or collapse the Records to include section.</span></span>
5. <span data-ttu-id="0793b-164">Clique em Filtro.</span><span class="sxs-lookup"><span data-stu-id="0793b-164">Click Filter.</span></span>
6. <span data-ttu-id="0793b-165">Na lista, selecione a linha para Campo = Número do item.</span><span class="sxs-lookup"><span data-stu-id="0793b-165">In the list, select the row for Field = Item number.</span></span>
7. <span data-ttu-id="0793b-166">No campo Critérios, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="0793b-166">In the Criteria field, type a value.</span></span>
    * <span data-ttu-id="0793b-167">Exemplo: P6003</span><span class="sxs-lookup"><span data-stu-id="0793b-167">Example: P6003</span></span>  
8. <span data-ttu-id="0793b-168">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="0793b-168">Click OK.</span></span>
9. <span data-ttu-id="0793b-169">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="0793b-169">Click OK.</span></span>
10. <span data-ttu-id="0793b-170">Clique em Ordens planejadas.</span><span class="sxs-lookup"><span data-stu-id="0793b-170">Click Planned orders.</span></span>
11. <span data-ttu-id="0793b-171">Use o Filtro Rápido para localizar registros.</span><span class="sxs-lookup"><span data-stu-id="0793b-171">Use the Quick Filter to find records.</span></span> <span data-ttu-id="0793b-172">Por exemplo, filtre o campo Número do item com um valor de 'P6000'.</span><span class="sxs-lookup"><span data-stu-id="0793b-172">For example, filter on the Item number field with a value of 'P6000'.</span></span>
    * <span data-ttu-id="0793b-173">Filtre pelo item de fórmula que contenha uma ordem de venda como coproduto do item que você criou.</span><span class="sxs-lookup"><span data-stu-id="0793b-173">Filter by the formula item that has as co-product of the item that you created a sales order for.</span></span>  
12. <span data-ttu-id="0793b-174">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="0793b-174">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="0793b-175">Selecione uma das linhas retornadas pelo filtro.</span><span class="sxs-lookup"><span data-stu-id="0793b-175">Select any of the rows returned by the filter.</span></span>  
13. <span data-ttu-id="0793b-176">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="0793b-176">In the list, click the link in the selected row.</span></span>
14. <span data-ttu-id="0793b-177">Expandir ou recolher a seção Vinculação.</span><span class="sxs-lookup"><span data-stu-id="0793b-177">Expand or collapse the Pegging section.</span></span>
15. <span data-ttu-id="0793b-178">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="0793b-178">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="0793b-179">A ordem planejada está vinculada a ordem de venda para o coproduto.</span><span class="sxs-lookup"><span data-stu-id="0793b-179">The planned order is pegged to the sales order for the co-product.</span></span>  
16. <span data-ttu-id="0793b-180">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="0793b-180">Close the page.</span></span>
17. <span data-ttu-id="0793b-181">Clique em Planejamento mestre.</span><span class="sxs-lookup"><span data-stu-id="0793b-181">Click Master planning.</span></span>
18. <span data-ttu-id="0793b-182">Vá para Planejamento mestre > Configurar > Parâmetros de planejamento mestre.</span><span class="sxs-lookup"><span data-stu-id="0793b-182">Go to Master planning > Setup > Master planning parameters.</span></span>
19. <span data-ttu-id="0793b-183">Selecione Não no campo Desabilitar todos os processos de planejamento.</span><span class="sxs-lookup"><span data-stu-id="0793b-183">Select No in the Disable all planning processes field.</span></span>
20. <span data-ttu-id="0793b-184">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="0793b-184">Close the page.</span></span>


