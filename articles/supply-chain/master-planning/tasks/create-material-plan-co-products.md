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
ms.openlocfilehash: d910b89330865b0bcf3f6cd05b761506f339a45f
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5841662"
---
# <a name="create-a-material-plan-for-co-products"></a><span data-ttu-id="1d18f-103">Criar um plano de materiais para coprodutos</span><span class="sxs-lookup"><span data-stu-id="1d18f-103">Create a material plan for co products</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="1d18f-104">O planejador de produção planeja os requisitos de materiais para itens que são coprodutos de fórmula.</span><span class="sxs-lookup"><span data-stu-id="1d18f-104">The production planner plans the material requirements for items that are formula co-products.</span></span> <span data-ttu-id="1d18f-105">A empresa de dados demonstrativos utilizada para criar esse procedimento é a USP2.</span><span class="sxs-lookup"><span data-stu-id="1d18f-105">The demo data company used to create this procedure is USP2.</span></span>


## <a name="create-requirement-for-a-co-product"></a><span data-ttu-id="1d18f-106">Criar requisito para um coproduto</span><span class="sxs-lookup"><span data-stu-id="1d18f-106">Create requirement for a co-product</span></span>
1. <span data-ttu-id="1d18f-107">Ir para o painel Padrão.</span><span class="sxs-lookup"><span data-stu-id="1d18f-107">Go to Default dashboard.</span></span>
2. <span data-ttu-id="1d18f-108">Clique em Consulta e processamento de ordem de venda.</span><span class="sxs-lookup"><span data-stu-id="1d18f-108">Click Sales order processing and inquiry.</span></span>
3. <span data-ttu-id="1d18f-109">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="1d18f-109">Click New.</span></span>
4. <span data-ttu-id="1d18f-110">Clique Ordem de venda.</span><span class="sxs-lookup"><span data-stu-id="1d18f-110">Click Sales order.</span></span>
5. <span data-ttu-id="1d18f-111">No campo Conta de cliente, insira um valor.</span><span class="sxs-lookup"><span data-stu-id="1d18f-111">In the Customer account field, type a value.</span></span>
    * <span data-ttu-id="1d18f-112">Exemplo: US-001</span><span class="sxs-lookup"><span data-stu-id="1d18f-112">Example: US-001</span></span>  
6. <span data-ttu-id="1d18f-113">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="1d18f-113">Click OK.</span></span>
7. <span data-ttu-id="1d18f-114">No campo Número de item, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="1d18f-114">In the Item number field, type a value.</span></span>
    * <span data-ttu-id="1d18f-115">Exemplo: P6003</span><span class="sxs-lookup"><span data-stu-id="1d18f-115">Example: P6003</span></span>  
8. <span data-ttu-id="1d18f-116">No campo Quantidade, insira um número.</span><span class="sxs-lookup"><span data-stu-id="1d18f-116">In the Quantity field, enter a number.</span></span>
    * <span data-ttu-id="1d18f-117">Exemplo: 50000</span><span class="sxs-lookup"><span data-stu-id="1d18f-117">Example: 50000</span></span>  
9. <span data-ttu-id="1d18f-118">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="1d18f-118">Click Save.</span></span>

## <a name="create-a-material-plan-for-co-products"></a><span data-ttu-id="1d18f-119">Criar um plano de materiais para coprodutos</span><span class="sxs-lookup"><span data-stu-id="1d18f-119">Create a material plan for co-products</span></span>
1. <span data-ttu-id="1d18f-120">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="1d18f-120">Close the page.</span></span>
2. <span data-ttu-id="1d18f-121">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="1d18f-121">Close the page.</span></span>
3. <span data-ttu-id="1d18f-122">Clique em Planejamento mestre.</span><span class="sxs-lookup"><span data-stu-id="1d18f-122">Click Master planning.</span></span>
4. <span data-ttu-id="1d18f-123">No campo Plano, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="1d18f-123">In the Plan field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="1d18f-124">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="1d18f-124">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="1d18f-125">Exemplo: Plano Mestre</span><span class="sxs-lookup"><span data-stu-id="1d18f-125">Example: MasterPlan</span></span>  
6. <span data-ttu-id="1d18f-126">Clique em Executar.</span><span class="sxs-lookup"><span data-stu-id="1d18f-126">Click Run.</span></span>
7. <span data-ttu-id="1d18f-127">Expanda ou recolha a seção de Registros a serem incluídos.</span><span class="sxs-lookup"><span data-stu-id="1d18f-127">Expand or collapse the Records to include section.</span></span>
8. <span data-ttu-id="1d18f-128">Clique em Filtro.</span><span class="sxs-lookup"><span data-stu-id="1d18f-128">Click Filter.</span></span>
9. <span data-ttu-id="1d18f-129">Na lista, selecione a linha para Campo = Número do item.</span><span class="sxs-lookup"><span data-stu-id="1d18f-129">In the list, select the row for Field = Item number.</span></span>
10. <span data-ttu-id="1d18f-130">No campo Critérios, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="1d18f-130">In the Criteria field, type a value.</span></span>
    * <span data-ttu-id="1d18f-131">Exemplo: P6003</span><span class="sxs-lookup"><span data-stu-id="1d18f-131">Example: P6003</span></span>  
11. <span data-ttu-id="1d18f-132">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="1d18f-132">Click OK.</span></span>
12. <span data-ttu-id="1d18f-133">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="1d18f-133">Click OK.</span></span>
13. <span data-ttu-id="1d18f-134">Clique em Ordens planejadas.</span><span class="sxs-lookup"><span data-stu-id="1d18f-134">Click Planned orders.</span></span>
14. <span data-ttu-id="1d18f-135">Use o Filtro Rápido para localizar registros.</span><span class="sxs-lookup"><span data-stu-id="1d18f-135">Use the Quick Filter to find records.</span></span> <span data-ttu-id="1d18f-136">Por exemplo, filtre o campo Número do item com um valor de 'P6000'.</span><span class="sxs-lookup"><span data-stu-id="1d18f-136">For example, filter on the Item number field with a value of 'P6000'.</span></span>
    * <span data-ttu-id="1d18f-137">Filtre pelo item de fórmula que contenha uma ordem de venda como coproduto do item que você criou.</span><span class="sxs-lookup"><span data-stu-id="1d18f-137">Filter by the formula item that has as co-product of the item that you created a sales order for.</span></span>  
15. <span data-ttu-id="1d18f-138">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="1d18f-138">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="1d18f-139">Selecione uma das linhas retornadas pelo filtro.</span><span class="sxs-lookup"><span data-stu-id="1d18f-139">Select any of the rows returned by the filter.</span></span>  
16. <span data-ttu-id="1d18f-140">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="1d18f-140">In the list, click the link in the selected row.</span></span>
17. <span data-ttu-id="1d18f-141">Expandir ou recolher a seção Vinculação.</span><span class="sxs-lookup"><span data-stu-id="1d18f-141">Expand or collapse the Pegging section.</span></span>
18. <span data-ttu-id="1d18f-142">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="1d18f-142">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="1d18f-143">A ordem planejada está vinculada a ordem de venda para o coproduto.</span><span class="sxs-lookup"><span data-stu-id="1d18f-143">The planned order is pegged to the sales order for the co-product.</span></span>  
19. <span data-ttu-id="1d18f-144">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="1d18f-144">Close the page.</span></span>

## <a name="create-requirement-for-a-co-product"></a><span data-ttu-id="1d18f-145">Criar requisito para um coproduto</span><span class="sxs-lookup"><span data-stu-id="1d18f-145">Create requirement for a co-product</span></span>
1. <span data-ttu-id="1d18f-146">Ir para o painel Padrão.</span><span class="sxs-lookup"><span data-stu-id="1d18f-146">Go to Default dashboard.</span></span>
2. <span data-ttu-id="1d18f-147">Clique em Consulta e processamento de ordem de venda.</span><span class="sxs-lookup"><span data-stu-id="1d18f-147">Click Sales order processing and inquiry.</span></span>
3. <span data-ttu-id="1d18f-148">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="1d18f-148">Click New.</span></span>
4. <span data-ttu-id="1d18f-149">Clique Ordem de venda.</span><span class="sxs-lookup"><span data-stu-id="1d18f-149">Click Sales order.</span></span>
5. <span data-ttu-id="1d18f-150">No campo Conta de cliente, insira um valor.</span><span class="sxs-lookup"><span data-stu-id="1d18f-150">In the Customer account field, type a value.</span></span>
    * <span data-ttu-id="1d18f-151">Exemplo: US-001</span><span class="sxs-lookup"><span data-stu-id="1d18f-151">Example: US-001</span></span>  
6. <span data-ttu-id="1d18f-152">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="1d18f-152">Click OK.</span></span>
7. <span data-ttu-id="1d18f-153">No campo Número de item, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="1d18f-153">In the Item number field, type a value.</span></span>
    * <span data-ttu-id="1d18f-154">Exemplo: P6003</span><span class="sxs-lookup"><span data-stu-id="1d18f-154">Example: P6003</span></span>  
8. <span data-ttu-id="1d18f-155">No campo Quantidade, insira um número.</span><span class="sxs-lookup"><span data-stu-id="1d18f-155">In the Quantity field, enter a number.</span></span>
    * <span data-ttu-id="1d18f-156">Exemplo: 50000</span><span class="sxs-lookup"><span data-stu-id="1d18f-156">Example: 50000</span></span>  
9. <span data-ttu-id="1d18f-157">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="1d18f-157">Click Save.</span></span>

## <a name="create-a-material-plan-for-co-products"></a><span data-ttu-id="1d18f-158">Criar um plano de materiais para coprodutos</span><span class="sxs-lookup"><span data-stu-id="1d18f-158">Create a material plan for co-products</span></span>
1. <span data-ttu-id="1d18f-159">No campo Plano, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="1d18f-159">In the Plan field, click the drop-down button to open the lookup.</span></span>
2. <span data-ttu-id="1d18f-160">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="1d18f-160">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="1d18f-161">Exemplo: Plano Mestre</span><span class="sxs-lookup"><span data-stu-id="1d18f-161">Example: MasterPlan</span></span>  
3. <span data-ttu-id="1d18f-162">Clique em Executar.</span><span class="sxs-lookup"><span data-stu-id="1d18f-162">Click Run.</span></span>
4. <span data-ttu-id="1d18f-163">Expanda ou recolha a seção de Registros a serem incluídos.</span><span class="sxs-lookup"><span data-stu-id="1d18f-163">Expand or collapse the Records to include section.</span></span>
5. <span data-ttu-id="1d18f-164">Clique em Filtro.</span><span class="sxs-lookup"><span data-stu-id="1d18f-164">Click Filter.</span></span>
6. <span data-ttu-id="1d18f-165">Na lista, selecione a linha para Campo = Número do item.</span><span class="sxs-lookup"><span data-stu-id="1d18f-165">In the list, select the row for Field = Item number.</span></span>
7. <span data-ttu-id="1d18f-166">No campo Critérios, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="1d18f-166">In the Criteria field, type a value.</span></span>
    * <span data-ttu-id="1d18f-167">Exemplo: P6003</span><span class="sxs-lookup"><span data-stu-id="1d18f-167">Example: P6003</span></span>  
8. <span data-ttu-id="1d18f-168">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="1d18f-168">Click OK.</span></span>
9. <span data-ttu-id="1d18f-169">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="1d18f-169">Click OK.</span></span>
10. <span data-ttu-id="1d18f-170">Clique em Ordens planejadas.</span><span class="sxs-lookup"><span data-stu-id="1d18f-170">Click Planned orders.</span></span>
11. <span data-ttu-id="1d18f-171">Use o Filtro Rápido para localizar registros.</span><span class="sxs-lookup"><span data-stu-id="1d18f-171">Use the Quick Filter to find records.</span></span> <span data-ttu-id="1d18f-172">Por exemplo, filtre o campo Número do item com um valor de 'P6000'.</span><span class="sxs-lookup"><span data-stu-id="1d18f-172">For example, filter on the Item number field with a value of 'P6000'.</span></span>
    * <span data-ttu-id="1d18f-173">Filtre pelo item de fórmula que contenha uma ordem de venda como coproduto do item que você criou.</span><span class="sxs-lookup"><span data-stu-id="1d18f-173">Filter by the formula item that has as co-product of the item that you created a sales order for.</span></span>  
12. <span data-ttu-id="1d18f-174">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="1d18f-174">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="1d18f-175">Selecione uma das linhas retornadas pelo filtro.</span><span class="sxs-lookup"><span data-stu-id="1d18f-175">Select any of the rows returned by the filter.</span></span>  
13. <span data-ttu-id="1d18f-176">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="1d18f-176">In the list, click the link in the selected row.</span></span>
14. <span data-ttu-id="1d18f-177">Expandir ou recolher a seção Vinculação.</span><span class="sxs-lookup"><span data-stu-id="1d18f-177">Expand or collapse the Pegging section.</span></span>
15. <span data-ttu-id="1d18f-178">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="1d18f-178">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="1d18f-179">A ordem planejada está vinculada a ordem de venda para o coproduto.</span><span class="sxs-lookup"><span data-stu-id="1d18f-179">The planned order is pegged to the sales order for the co-product.</span></span>  
16. <span data-ttu-id="1d18f-180">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="1d18f-180">Close the page.</span></span>
17. <span data-ttu-id="1d18f-181">Clique em Planejamento mestre.</span><span class="sxs-lookup"><span data-stu-id="1d18f-181">Click Master planning.</span></span>
18. <span data-ttu-id="1d18f-182">Vá para Planejamento mestre > Configurar > Parâmetros de planejamento mestre.</span><span class="sxs-lookup"><span data-stu-id="1d18f-182">Go to Master planning > Setup > Master planning parameters.</span></span>
19. <span data-ttu-id="1d18f-183">Selecione Não no campo Desabilitar todos os processos de planejamento.</span><span class="sxs-lookup"><span data-stu-id="1d18f-183">Select No in the Disable all planning processes field.</span></span>
20. <span data-ttu-id="1d18f-184">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="1d18f-184">Close the page.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]