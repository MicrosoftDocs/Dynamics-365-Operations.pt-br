--- 
title: "Criar matérias-primas (apenas fevereiro de 2016)"
description: Esta tarefa tem como foco criar os componentes de produtos finalizados e semifinalizados.
author: BibiSp
manager: AnnBe
ms.date: 02/07/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.author: bis
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: f1c10e0f8275d928c1455cd99105aece8780e7f0
ms.contentlocale: pt-br
ms.lasthandoff: 08/29/2017

---
# <a name="create-raw-materials-february-2016-only"></a><span data-ttu-id="f716a-103">Criar matérias-primas (apenas fevereiro de 2016)</span><span class="sxs-lookup"><span data-stu-id="f716a-103">Create raw materials (February 2016 only)</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="f716a-104">Esta tarefa tem como foco criar os componentes de produtos finalizados e semifinalizados.</span><span class="sxs-lookup"><span data-stu-id="f716a-104">This task focuses on creating the components of finished and semi-finished products.</span></span> <span data-ttu-id="f716a-105">Trata-se da terceira tarefa na série de cálculo BOM.</span><span class="sxs-lookup"><span data-stu-id="f716a-105">It is the third task in the BOM calculation series.</span></span> <span data-ttu-id="f716a-106">A empresa de dados demo usada para criar esta tarefa é USMF.</span><span class="sxs-lookup"><span data-stu-id="f716a-106">The demo data company used to create this task is USMF.</span></span>


## <a name="create-the-first-material"></a><span data-ttu-id="f716a-107">Criar o primeiro material</span><span class="sxs-lookup"><span data-stu-id="f716a-107">Create the first material</span></span>
1. <span data-ttu-id="f716a-108">Vá para Gerenciamento de informações do produto > Produtos > Produtos liberados.</span><span class="sxs-lookup"><span data-stu-id="f716a-108">Go to Product information management > Products > Released products.</span></span>
2. <span data-ttu-id="f716a-109">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="f716a-109">Click New.</span></span>
3. <span data-ttu-id="f716a-110">No campo Número do produto, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="f716a-110">In the Product number field, type a value.</span></span>
    * <span data-ttu-id="f716a-111">Neste exemplo, insira ITEM_A.</span><span class="sxs-lookup"><span data-stu-id="f716a-111">For this example, enter ITEM_A.</span></span>  
4. <span data-ttu-id="f716a-112">No campo Grupo de modelos do item, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="f716a-112">In the Item model group field, enter or select a value.</span></span>
    * <span data-ttu-id="f716a-113">Selecione STD.</span><span class="sxs-lookup"><span data-stu-id="f716a-113">Select STD.</span></span> <span data-ttu-id="f716a-114">STD significa "custo padrão" e é o modelo mais comumente utilizado ao se trabalhar com cálculos de custo.</span><span class="sxs-lookup"><span data-stu-id="f716a-114">STD stands for standard cost and is the most commonly used model when working with cost calculations.</span></span>  
5. <span data-ttu-id="f716a-115">No campo Grupo de itens, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="f716a-115">In the Item group field, enter or select a value.</span></span>
    * <span data-ttu-id="f716a-116">Por exemplo, selecione Áudio.</span><span class="sxs-lookup"><span data-stu-id="f716a-116">For example, select Audio.</span></span> <span data-ttu-id="f716a-117">Isso não tem impacto sobre os cálculos de custo.</span><span class="sxs-lookup"><span data-stu-id="f716a-117">This has no impact on cost calculations.</span></span>  
6. <span data-ttu-id="f716a-118">No campo Grupo de dimensões de armazenamento, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="f716a-118">In the Storage dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="f716a-119">Selecione SiteWH.</span><span class="sxs-lookup"><span data-stu-id="f716a-119">Select SiteWH.</span></span> <span data-ttu-id="f716a-120">Apenas Site e Depósito serão usados na demonstração.</span><span class="sxs-lookup"><span data-stu-id="f716a-120">Only Site and Warehouse will be used for the demonstration.</span></span>  
7. <span data-ttu-id="f716a-121">No campo Grupo de dimensões de rastreamento, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="f716a-121">In the Tracking dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="f716a-122">A dimensão de rastreamento não será usada neste exemplo.</span><span class="sxs-lookup"><span data-stu-id="f716a-122">Tracking dimensions will not be used for this example.</span></span> <span data-ttu-id="f716a-123">Selecione Nenhuma.</span><span class="sxs-lookup"><span data-stu-id="f716a-123">Select None.</span></span>  
8. <span data-ttu-id="f716a-124">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="f716a-124">Click OK.</span></span>
9. <span data-ttu-id="f716a-125">No Painel de Ação, clique em Gerenciar estoque.</span><span class="sxs-lookup"><span data-stu-id="f716a-125">On the Action Pane, click Manage inventory.</span></span>
10. <span data-ttu-id="f716a-126">Clique em Configurações de ordem padrão.</span><span class="sxs-lookup"><span data-stu-id="f716a-126">Click Default order settings.</span></span>
11. <span data-ttu-id="f716a-127">No campo Site de compra, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="f716a-127">In the Purchase site field, enter or select a value.</span></span>
    * <span data-ttu-id="f716a-128">Neste exemplo, selecione Site 1.</span><span class="sxs-lookup"><span data-stu-id="f716a-128">For this example, select Site 1.</span></span>  
12. <span data-ttu-id="f716a-129">No campo Site de estoque, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="f716a-129">In the Inventory site field, enter or select a value.</span></span>
    * <span data-ttu-id="f716a-130">Neste exemplo, selecione Site 1.</span><span class="sxs-lookup"><span data-stu-id="f716a-130">For this example, select Site 1.</span></span>  
13. <span data-ttu-id="f716a-131">No campo Site de vendas, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="f716a-131">In the Sales site field, enter or select a value.</span></span>
    * <span data-ttu-id="f716a-132">Neste exemplo, selecione Site 1.</span><span class="sxs-lookup"><span data-stu-id="f716a-132">For this example, select Site 1.</span></span>  
14. <span data-ttu-id="f716a-133">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="f716a-133">Close the page.</span></span>
15. <span data-ttu-id="f716a-134">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="f716a-134">Close the page.</span></span>
16. <span data-ttu-id="f716a-135">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="f716a-135">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="f716a-136">Clique em ITEM_A.</span><span class="sxs-lookup"><span data-stu-id="f716a-136">Click ITEM_A.</span></span>  
17. <span data-ttu-id="f716a-137">Expanda a seção Gerenciar custos.</span><span class="sxs-lookup"><span data-stu-id="f716a-137">Expand the Manage costs section.</span></span>
18. <span data-ttu-id="f716a-138">No campo Grupo de custos, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="f716a-138">In the Cost group field, type a value.</span></span>
    * <span data-ttu-id="f716a-139">Neste exemplo, digite M2.</span><span class="sxs-lookup"><span data-stu-id="f716a-139">For this example, type M2.</span></span>  
19. <span data-ttu-id="f716a-140">No Painel de Ação, clique em Gerenciar custos.</span><span class="sxs-lookup"><span data-stu-id="f716a-140">On the Action Pane, click Manage costs.</span></span>
20. <span data-ttu-id="f716a-141">Clique em Preço de item.</span><span class="sxs-lookup"><span data-stu-id="f716a-141">Click Item price.</span></span>
21. <span data-ttu-id="f716a-142">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="f716a-142">Click New.</span></span>
22. <span data-ttu-id="f716a-143">No campo Versão, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="f716a-143">In the Version field, enter or select a value.</span></span>
    * <span data-ttu-id="f716a-144">Neste exemplo, selecione 10, que é o tipo de custo Custo padrão.</span><span class="sxs-lookup"><span data-stu-id="f716a-144">For this example, select 10, which is the Standard cost costing type.</span></span>  
23. <span data-ttu-id="f716a-145">No campo Local, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="f716a-145">In the Site field, enter or select a value.</span></span>
    * <span data-ttu-id="f716a-146">Neste exemplo, selecione Site 1.</span><span class="sxs-lookup"><span data-stu-id="f716a-146">For this example, select Site 1.</span></span>  
24. <span data-ttu-id="f716a-147">No campo Preço, insira um número.</span><span class="sxs-lookup"><span data-stu-id="f716a-147">In the Price field, enter a number.</span></span>
    * <span data-ttu-id="f716a-148">Neste exemplo, digite 10.</span><span class="sxs-lookup"><span data-stu-id="f716a-148">For this example, type 10.</span></span>  
25. <span data-ttu-id="f716a-149">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="f716a-149">Click Save.</span></span>
26. <span data-ttu-id="f716a-150">Clique em Ativar preço(s) pendente(s).</span><span class="sxs-lookup"><span data-stu-id="f716a-150">Click Activate pending price(s).</span></span>
27. <span data-ttu-id="f716a-151">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="f716a-151">Close the page.</span></span>
28. <span data-ttu-id="f716a-152">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="f716a-152">Close the page.</span></span>

## <a name="create-the-second-material"></a><span data-ttu-id="f716a-153">Criar o segundo material</span><span class="sxs-lookup"><span data-stu-id="f716a-153">Create the second material</span></span>
1. <span data-ttu-id="f716a-154">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="f716a-154">Click New.</span></span>
2. <span data-ttu-id="f716a-155">No campo Número do produto, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="f716a-155">In the Product number field, type a value.</span></span>
    * <span data-ttu-id="f716a-156">Neste exemplo, digite ITEM_B.</span><span class="sxs-lookup"><span data-stu-id="f716a-156">For this example, type ITEM_B.</span></span>  
3. <span data-ttu-id="f716a-157">No campo Grupo de modelos do item, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="f716a-157">In the Item model group field, enter or select a value.</span></span>
    * <span data-ttu-id="f716a-158">Selecione STD.</span><span class="sxs-lookup"><span data-stu-id="f716a-158">Select STD.</span></span> <span data-ttu-id="f716a-159">STD significa "custo padrão" e é o modelo mais comumente utilizado ao se trabalhar com cálculos de custo.</span><span class="sxs-lookup"><span data-stu-id="f716a-159">STD stands for standard cost and is the most commonly used model when working with cost calculations.</span></span>  
4. <span data-ttu-id="f716a-160">No campo Grupo de itens, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="f716a-160">In the Item group field, enter or select a value.</span></span>
    * <span data-ttu-id="f716a-161">Por exemplo, selecione Áudio.</span><span class="sxs-lookup"><span data-stu-id="f716a-161">For example, select Audio.</span></span> <span data-ttu-id="f716a-162">Isso não tem impacto sobre os cálculos de custo.</span><span class="sxs-lookup"><span data-stu-id="f716a-162">This has no impact on cost calculations.</span></span>  
5. <span data-ttu-id="f716a-163">No campo Grupo de dimensões de armazenamento, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="f716a-163">In the Storage dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="f716a-164">Selecione SiteWH.</span><span class="sxs-lookup"><span data-stu-id="f716a-164">Select SiteWH.</span></span> <span data-ttu-id="f716a-165">Apenas Site e Depósito serão usados neste exemplo.</span><span class="sxs-lookup"><span data-stu-id="f716a-165">Only Site and Warehouse will be used for this example.</span></span>  
6. <span data-ttu-id="f716a-166">No campo Grupo de dimensões de rastreamento, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="f716a-166">In the Tracking dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="f716a-167">A dimensão de rastreamento não será usada neste exemplo.</span><span class="sxs-lookup"><span data-stu-id="f716a-167">Tracking dimensions will not be used for this example.</span></span> <span data-ttu-id="f716a-168">Selecione Nenhuma.</span><span class="sxs-lookup"><span data-stu-id="f716a-168">Select None.</span></span>  
7. <span data-ttu-id="f716a-169">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="f716a-169">Click OK.</span></span>
8. <span data-ttu-id="f716a-170">No Painel de Ação, clique em Gerenciar estoque.</span><span class="sxs-lookup"><span data-stu-id="f716a-170">On the Action Pane, click Manage inventory.</span></span>
9. <span data-ttu-id="f716a-171">Clique em Configurações de ordem padrão.</span><span class="sxs-lookup"><span data-stu-id="f716a-171">Click Default order settings.</span></span>
10. <span data-ttu-id="f716a-172">No campo Site de compra, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="f716a-172">In the Purchase site field, enter or select a value.</span></span>
    * <span data-ttu-id="f716a-173">Neste exemplo, selecione Site 1.</span><span class="sxs-lookup"><span data-stu-id="f716a-173">For this example, select Site 1.</span></span>  
11. <span data-ttu-id="f716a-174">No campo Site de estoque, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="f716a-174">In the Inventory site field, enter or select a value.</span></span>
    * <span data-ttu-id="f716a-175">Neste exemplo, selecione Site 1.</span><span class="sxs-lookup"><span data-stu-id="f716a-175">For this example, select Site 1.</span></span>  
12. <span data-ttu-id="f716a-176">No campo Site de vendas, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="f716a-176">In the Sales site field, enter or select a value.</span></span>
    * <span data-ttu-id="f716a-177">Neste exemplo, selecione Site 1.</span><span class="sxs-lookup"><span data-stu-id="f716a-177">For this example, select Site 1.</span></span>  
13. <span data-ttu-id="f716a-178">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="f716a-178">Close the page.</span></span>
14. <span data-ttu-id="f716a-179">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="f716a-179">Close the page.</span></span>
15. <span data-ttu-id="f716a-180">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="f716a-180">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="f716a-181">Clique em ITEM_B.</span><span class="sxs-lookup"><span data-stu-id="f716a-181">Click ITEM_B.</span></span>  
16. <span data-ttu-id="f716a-182">Expanda a seção Gerenciar custos.</span><span class="sxs-lookup"><span data-stu-id="f716a-182">Expand the Manage costs section.</span></span>
17. <span data-ttu-id="f716a-183">No campo Grupo de custos, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="f716a-183">In the Cost group field, type a value.</span></span>
    * <span data-ttu-id="f716a-184">Neste exemplo, digite M2.</span><span class="sxs-lookup"><span data-stu-id="f716a-184">For this example, type M2.</span></span>  
18. <span data-ttu-id="f716a-185">No Painel de Ação, clique em Gerenciar custos.</span><span class="sxs-lookup"><span data-stu-id="f716a-185">On the Action Pane, click Manage costs.</span></span>
19. <span data-ttu-id="f716a-186">Clique em Preço de item.</span><span class="sxs-lookup"><span data-stu-id="f716a-186">Click Item price.</span></span>
20. <span data-ttu-id="f716a-187">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="f716a-187">Click New.</span></span>
21. <span data-ttu-id="f716a-188">No campo Versão, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="f716a-188">In the Version field, enter or select a value.</span></span>
    * <span data-ttu-id="f716a-189">Neste exemplo, selecione 10.</span><span class="sxs-lookup"><span data-stu-id="f716a-189">For this example, select 10.</span></span> <span data-ttu-id="f716a-190">Este é o tipo de custo Custo padrão.</span><span class="sxs-lookup"><span data-stu-id="f716a-190">This is the Standard cost costing type.</span></span>  
22. <span data-ttu-id="f716a-191">No campo Local, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="f716a-191">In the Site field, enter or select a value.</span></span>
    * <span data-ttu-id="f716a-192">Neste exemplo, selecione Site 1.</span><span class="sxs-lookup"><span data-stu-id="f716a-192">For this example, select Site 1.</span></span>  
23. <span data-ttu-id="f716a-193">No campo Preço, insira um número.</span><span class="sxs-lookup"><span data-stu-id="f716a-193">In the Price field, enter a number.</span></span>
    * <span data-ttu-id="f716a-194">Para a demonstração, digite 10.</span><span class="sxs-lookup"><span data-stu-id="f716a-194">For the demonstration, type 10.</span></span>  
24. <span data-ttu-id="f716a-195">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="f716a-195">Click Save.</span></span>
25. <span data-ttu-id="f716a-196">Clique em Ativar preço(s) pendente(s).</span><span class="sxs-lookup"><span data-stu-id="f716a-196">Click Activate pending price(s).</span></span>
26. <span data-ttu-id="f716a-197">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="f716a-197">Close the page.</span></span>
27. <span data-ttu-id="f716a-198">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="f716a-198">Close the page.</span></span>

## <a name="create-the-third-material"></a><span data-ttu-id="f716a-199">Criar o terceiro material</span><span class="sxs-lookup"><span data-stu-id="f716a-199">Create the third material</span></span>
1. <span data-ttu-id="f716a-200">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="f716a-200">Click New.</span></span>
2. <span data-ttu-id="f716a-201">No campo Número do produto, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="f716a-201">In the Product number field, type a value.</span></span>
    * <span data-ttu-id="f716a-202">Para a demonstração, digite ITEM_C</span><span class="sxs-lookup"><span data-stu-id="f716a-202">For the demonstration, type ITEM_C</span></span>  
3. <span data-ttu-id="f716a-203">No campo Grupo de modelos do item, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="f716a-203">In the Item model group field, enter or select a value.</span></span>
    * <span data-ttu-id="f716a-204">Selecione STD.</span><span class="sxs-lookup"><span data-stu-id="f716a-204">Select STD.</span></span> <span data-ttu-id="f716a-205">STD significa "custo padrão" e é o modelo mais comumente utilizado ao se trabalhar com cálculos de custo.</span><span class="sxs-lookup"><span data-stu-id="f716a-205">STD stands for standard cost and is the most commonly used model when working with cost calculations.</span></span>  
4. <span data-ttu-id="f716a-206">No campo Grupo de itens, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="f716a-206">In the Item group field, enter or select a value.</span></span>
    * <span data-ttu-id="f716a-207">Por exemplo, selecione Áudio.</span><span class="sxs-lookup"><span data-stu-id="f716a-207">For example, select Audio.</span></span> <span data-ttu-id="f716a-208">Isso não tem impacto sobre os cálculos de custo.</span><span class="sxs-lookup"><span data-stu-id="f716a-208">This has no impact on cost calculations.</span></span>  
5. <span data-ttu-id="f716a-209">No campo Grupo de dimensões de armazenamento, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="f716a-209">In the Storage dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="f716a-210">Selecione SiteWH.</span><span class="sxs-lookup"><span data-stu-id="f716a-210">Select SiteWH.</span></span> <span data-ttu-id="f716a-211">Apenas Site e Depósito serão usados na demonstração.</span><span class="sxs-lookup"><span data-stu-id="f716a-211">Only Site and Warehouse will be used for the demonstration.</span></span>  
6. <span data-ttu-id="f716a-212">No campo Grupo de dimensões de rastreamento, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="f716a-212">In the Tracking dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="f716a-213">A dimensão de rastreamento não será usada neste exemplo.</span><span class="sxs-lookup"><span data-stu-id="f716a-213">Tracking dimensions will not be used for this example.</span></span> <span data-ttu-id="f716a-214">Selecione Nenhuma.</span><span class="sxs-lookup"><span data-stu-id="f716a-214">Select None.</span></span>  
7. <span data-ttu-id="f716a-215">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="f716a-215">Click OK.</span></span>
8. <span data-ttu-id="f716a-216">No Painel de Ação, clique em Gerenciar estoque.</span><span class="sxs-lookup"><span data-stu-id="f716a-216">On the Action Pane, click Manage inventory.</span></span>
9. <span data-ttu-id="f716a-217">Clique em Configurações de ordem padrão.</span><span class="sxs-lookup"><span data-stu-id="f716a-217">Click Default order settings.</span></span>
10. <span data-ttu-id="f716a-218">No campo Site de compra, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="f716a-218">In the Purchase site field, enter or select a value.</span></span>
    * <span data-ttu-id="f716a-219">Neste exemplo, selecione Site 1.</span><span class="sxs-lookup"><span data-stu-id="f716a-219">For this example, select Site 1.</span></span>  
11. <span data-ttu-id="f716a-220">No campo Site de estoque, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="f716a-220">In the Inventory site field, enter or select a value.</span></span>
    * <span data-ttu-id="f716a-221">Neste exemplo, selecione Site 1.</span><span class="sxs-lookup"><span data-stu-id="f716a-221">For this example, select Site 1.</span></span>  
12. <span data-ttu-id="f716a-222">No campo Site de vendas, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="f716a-222">In the Sales site field, enter or select a value.</span></span>
    * <span data-ttu-id="f716a-223">Neste exemplo, selecione Site 1.</span><span class="sxs-lookup"><span data-stu-id="f716a-223">For this example, select Site 1.</span></span>  
13. <span data-ttu-id="f716a-224">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="f716a-224">Close the page.</span></span>
14. <span data-ttu-id="f716a-225">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="f716a-225">Close the page.</span></span>
15. <span data-ttu-id="f716a-226">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="f716a-226">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="f716a-227">Clique em ITEM_C.</span><span class="sxs-lookup"><span data-stu-id="f716a-227">Click ITEM_C.</span></span>  
16. <span data-ttu-id="f716a-228">Expanda a seção Gerenciar custos.</span><span class="sxs-lookup"><span data-stu-id="f716a-228">Expand the Manage costs section.</span></span>
17. <span data-ttu-id="f716a-229">No campo Grupo de custos, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="f716a-229">In the Cost group field, type a value.</span></span>
    * <span data-ttu-id="f716a-230">Neste exemplo, digite M1.</span><span class="sxs-lookup"><span data-stu-id="f716a-230">For this example, type M1.</span></span>  
18. <span data-ttu-id="f716a-231">No Painel de Ação, clique em Gerenciar custos.</span><span class="sxs-lookup"><span data-stu-id="f716a-231">On the Action Pane, click Manage costs.</span></span>
19. <span data-ttu-id="f716a-232">Clique em Preço de item.</span><span class="sxs-lookup"><span data-stu-id="f716a-232">Click Item price.</span></span>
20. <span data-ttu-id="f716a-233">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="f716a-233">Click New.</span></span>
21. <span data-ttu-id="f716a-234">No campo Versão, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="f716a-234">In the Version field, enter or select a value.</span></span>
    * <span data-ttu-id="f716a-235">Neste exemplo, selecione 10.</span><span class="sxs-lookup"><span data-stu-id="f716a-235">For this example, select 10.</span></span> <span data-ttu-id="f716a-236">Este é o tipo de custo Custo padrão.</span><span class="sxs-lookup"><span data-stu-id="f716a-236">This is the Standard cost costing type.</span></span>  
22. <span data-ttu-id="f716a-237">No campo Local, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="f716a-237">In the Site field, enter or select a value.</span></span>
    * <span data-ttu-id="f716a-238">Neste exemplo, selecione Site 1.</span><span class="sxs-lookup"><span data-stu-id="f716a-238">For this example, select Site 1.</span></span>  
23. <span data-ttu-id="f716a-239">No campo Preço, insira um número.</span><span class="sxs-lookup"><span data-stu-id="f716a-239">In the Price field, enter a number.</span></span>
    * <span data-ttu-id="f716a-240">Neste exemplo, digite 10.</span><span class="sxs-lookup"><span data-stu-id="f716a-240">For this example, type 10.</span></span>  
24. <span data-ttu-id="f716a-241">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="f716a-241">Click Save.</span></span>
25. <span data-ttu-id="f716a-242">Clique em Ativar preço(s) pendente(s).</span><span class="sxs-lookup"><span data-stu-id="f716a-242">Click Activate pending price(s).</span></span>
26. <span data-ttu-id="f716a-243">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="f716a-243">Close the page.</span></span>
27. <span data-ttu-id="f716a-244">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="f716a-244">Close the page.</span></span>


