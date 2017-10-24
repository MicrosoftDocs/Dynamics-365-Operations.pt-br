--- 
title: "Criar matérias-primas (apenas fevereiro de 2016)"
description: Esta tarefa tem como foco criar os componentes de produtos finalizados e semifinalizados.
author: YuyuScheller
manager: AnnBe
ms.date: 02/07/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: Operations
ms.search.region: Global
ms.author: bis
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 3d77dcc20fe7402af83dd724e7fef848977e5bf8
ms.openlocfilehash: f6af7b93d8d1d9a6f7474f24177b16e5295e90d6
ms.contentlocale: pt-br
ms.lasthandoff: 09/29/2017

---
# <a name="create-raw-materials-february-2016-only"></a><span data-ttu-id="c5ead-103">Criar matérias-primas (apenas fevereiro de 2016)</span><span class="sxs-lookup"><span data-stu-id="c5ead-103">Create raw materials (February 2016 only)</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="c5ead-104">Esta tarefa tem como foco criar os componentes de produtos finalizados e semifinalizados.</span><span class="sxs-lookup"><span data-stu-id="c5ead-104">This task focuses on creating the components of finished and semi-finished products.</span></span> <span data-ttu-id="c5ead-105">Trata-se da terceira tarefa na série de cálculo BOM.</span><span class="sxs-lookup"><span data-stu-id="c5ead-105">It is the third task in the BOM calculation series.</span></span> <span data-ttu-id="c5ead-106">A empresa de dados demo usada para criar esta tarefa é USMF.</span><span class="sxs-lookup"><span data-stu-id="c5ead-106">The demo data company used to create this task is USMF.</span></span>


## <a name="create-the-first-material"></a><span data-ttu-id="c5ead-107">Criar o primeiro material</span><span class="sxs-lookup"><span data-stu-id="c5ead-107">Create the first material</span></span>
1. <span data-ttu-id="c5ead-108">Vá para Gerenciamento de informações do produto > Produtos > Produtos liberados.</span><span class="sxs-lookup"><span data-stu-id="c5ead-108">Go to Product information management > Products > Released products.</span></span>
2. <span data-ttu-id="c5ead-109">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="c5ead-109">Click New.</span></span>
3. <span data-ttu-id="c5ead-110">No campo Número do produto, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="c5ead-110">In the Product number field, type a value.</span></span>
    * <span data-ttu-id="c5ead-111">Neste exemplo, insira ITEM_A.</span><span class="sxs-lookup"><span data-stu-id="c5ead-111">For this example, enter ITEM_A.</span></span>  
4. <span data-ttu-id="c5ead-112">No campo Grupo de modelos do item, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="c5ead-112">In the Item model group field, enter or select a value.</span></span>
    * <span data-ttu-id="c5ead-113">Selecione STD.</span><span class="sxs-lookup"><span data-stu-id="c5ead-113">Select STD.</span></span> <span data-ttu-id="c5ead-114">STD significa "custo padrão" e é o modelo mais comumente utilizado ao se trabalhar com cálculos de custo.</span><span class="sxs-lookup"><span data-stu-id="c5ead-114">STD stands for standard cost and is the most commonly used model when working with cost calculations.</span></span>  
5. <span data-ttu-id="c5ead-115">No campo Grupo de itens, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="c5ead-115">In the Item group field, enter or select a value.</span></span>
    * <span data-ttu-id="c5ead-116">Por exemplo, selecione Áudio.</span><span class="sxs-lookup"><span data-stu-id="c5ead-116">For example, select Audio.</span></span> <span data-ttu-id="c5ead-117">Isso não tem impacto sobre os cálculos de custo.</span><span class="sxs-lookup"><span data-stu-id="c5ead-117">This has no impact on cost calculations.</span></span>  
6. <span data-ttu-id="c5ead-118">No campo Grupo de dimensões de armazenamento, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="c5ead-118">In the Storage dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="c5ead-119">Selecione SiteWH.</span><span class="sxs-lookup"><span data-stu-id="c5ead-119">Select SiteWH.</span></span> <span data-ttu-id="c5ead-120">Apenas Site e Depósito serão usados na demonstração.</span><span class="sxs-lookup"><span data-stu-id="c5ead-120">Only Site and Warehouse will be used for the demonstration.</span></span>  
7. <span data-ttu-id="c5ead-121">No campo Grupo de dimensões de rastreamento, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="c5ead-121">In the Tracking dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="c5ead-122">A dimensão de rastreamento não será usada neste exemplo.</span><span class="sxs-lookup"><span data-stu-id="c5ead-122">Tracking dimensions will not be used for this example.</span></span> <span data-ttu-id="c5ead-123">Selecione Nenhuma.</span><span class="sxs-lookup"><span data-stu-id="c5ead-123">Select None.</span></span>  
8. <span data-ttu-id="c5ead-124">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="c5ead-124">Click OK.</span></span>
9. <span data-ttu-id="c5ead-125">No Painel de Ação, clique em Gerenciar estoque.</span><span class="sxs-lookup"><span data-stu-id="c5ead-125">On the Action Pane, click Manage inventory.</span></span>
10. <span data-ttu-id="c5ead-126">Clique em Configurações de ordem padrão.</span><span class="sxs-lookup"><span data-stu-id="c5ead-126">Click Default order settings.</span></span>
11. <span data-ttu-id="c5ead-127">No campo Site de compra, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="c5ead-127">In the Purchase site field, enter or select a value.</span></span>
    * <span data-ttu-id="c5ead-128">Neste exemplo, selecione Site 1.</span><span class="sxs-lookup"><span data-stu-id="c5ead-128">For this example, select Site 1.</span></span>  
12. <span data-ttu-id="c5ead-129">No campo Site de estoque, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="c5ead-129">In the Inventory site field, enter or select a value.</span></span>
    * <span data-ttu-id="c5ead-130">Neste exemplo, selecione Site 1.</span><span class="sxs-lookup"><span data-stu-id="c5ead-130">For this example, select Site 1.</span></span>  
13. <span data-ttu-id="c5ead-131">No campo Site de vendas, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="c5ead-131">In the Sales site field, enter or select a value.</span></span>
    * <span data-ttu-id="c5ead-132">Neste exemplo, selecione Site 1.</span><span class="sxs-lookup"><span data-stu-id="c5ead-132">For this example, select Site 1.</span></span>  
14. <span data-ttu-id="c5ead-133">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="c5ead-133">Close the page.</span></span>
15. <span data-ttu-id="c5ead-134">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="c5ead-134">Close the page.</span></span>
16. <span data-ttu-id="c5ead-135">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="c5ead-135">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="c5ead-136">Clique em ITEM_A.</span><span class="sxs-lookup"><span data-stu-id="c5ead-136">Click ITEM_A.</span></span>  
17. <span data-ttu-id="c5ead-137">Expanda a seção Gerenciar custos.</span><span class="sxs-lookup"><span data-stu-id="c5ead-137">Expand the Manage costs section.</span></span>
18. <span data-ttu-id="c5ead-138">No campo Grupo de custos, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="c5ead-138">In the Cost group field, type a value.</span></span>
    * <span data-ttu-id="c5ead-139">Neste exemplo, digite M2.</span><span class="sxs-lookup"><span data-stu-id="c5ead-139">For this example, type M2.</span></span>  
19. <span data-ttu-id="c5ead-140">No Painel de Ação, clique em Gerenciar custos.</span><span class="sxs-lookup"><span data-stu-id="c5ead-140">On the Action Pane, click Manage costs.</span></span>
20. <span data-ttu-id="c5ead-141">Clique em Preço de item.</span><span class="sxs-lookup"><span data-stu-id="c5ead-141">Click Item price.</span></span>
21. <span data-ttu-id="c5ead-142">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="c5ead-142">Click New.</span></span>
22. <span data-ttu-id="c5ead-143">No campo Versão, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="c5ead-143">In the Version field, enter or select a value.</span></span>
    * <span data-ttu-id="c5ead-144">Neste exemplo, selecione 10, que é o tipo de custo Custo padrão.</span><span class="sxs-lookup"><span data-stu-id="c5ead-144">For this example, select 10, which is the Standard cost costing type.</span></span>  
23. <span data-ttu-id="c5ead-145">No campo Local, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="c5ead-145">In the Site field, enter or select a value.</span></span>
    * <span data-ttu-id="c5ead-146">Neste exemplo, selecione Site 1.</span><span class="sxs-lookup"><span data-stu-id="c5ead-146">For this example, select Site 1.</span></span>  
24. <span data-ttu-id="c5ead-147">No campo Preço, insira um número.</span><span class="sxs-lookup"><span data-stu-id="c5ead-147">In the Price field, enter a number.</span></span>
    * <span data-ttu-id="c5ead-148">Neste exemplo, digite 10.</span><span class="sxs-lookup"><span data-stu-id="c5ead-148">For this example, type 10.</span></span>  
25. <span data-ttu-id="c5ead-149">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="c5ead-149">Click Save.</span></span>
26. <span data-ttu-id="c5ead-150">Clique em Ativar preço(s) pendente(s).</span><span class="sxs-lookup"><span data-stu-id="c5ead-150">Click Activate pending price(s).</span></span>
27. <span data-ttu-id="c5ead-151">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="c5ead-151">Close the page.</span></span>
28. <span data-ttu-id="c5ead-152">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="c5ead-152">Close the page.</span></span>

## <a name="create-the-second-material"></a><span data-ttu-id="c5ead-153">Criar o segundo material</span><span class="sxs-lookup"><span data-stu-id="c5ead-153">Create the second material</span></span>
1. <span data-ttu-id="c5ead-154">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="c5ead-154">Click New.</span></span>
2. <span data-ttu-id="c5ead-155">No campo Número do produto, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="c5ead-155">In the Product number field, type a value.</span></span>
    * <span data-ttu-id="c5ead-156">Neste exemplo, digite ITEM_B.</span><span class="sxs-lookup"><span data-stu-id="c5ead-156">For this example, type ITEM_B.</span></span>  
3. <span data-ttu-id="c5ead-157">No campo Grupo de modelos do item, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="c5ead-157">In the Item model group field, enter or select a value.</span></span>
    * <span data-ttu-id="c5ead-158">Selecione STD.</span><span class="sxs-lookup"><span data-stu-id="c5ead-158">Select STD.</span></span> <span data-ttu-id="c5ead-159">STD significa "custo padrão" e é o modelo mais comumente utilizado ao se trabalhar com cálculos de custo.</span><span class="sxs-lookup"><span data-stu-id="c5ead-159">STD stands for standard cost and is the most commonly used model when working with cost calculations.</span></span>  
4. <span data-ttu-id="c5ead-160">No campo Grupo de itens, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="c5ead-160">In the Item group field, enter or select a value.</span></span>
    * <span data-ttu-id="c5ead-161">Por exemplo, selecione Áudio.</span><span class="sxs-lookup"><span data-stu-id="c5ead-161">For example, select Audio.</span></span> <span data-ttu-id="c5ead-162">Isso não tem impacto sobre os cálculos de custo.</span><span class="sxs-lookup"><span data-stu-id="c5ead-162">This has no impact on cost calculations.</span></span>  
5. <span data-ttu-id="c5ead-163">No campo Grupo de dimensões de armazenamento, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="c5ead-163">In the Storage dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="c5ead-164">Selecione SiteWH.</span><span class="sxs-lookup"><span data-stu-id="c5ead-164">Select SiteWH.</span></span> <span data-ttu-id="c5ead-165">Apenas Site e Depósito serão usados neste exemplo.</span><span class="sxs-lookup"><span data-stu-id="c5ead-165">Only Site and Warehouse will be used for this example.</span></span>  
6. <span data-ttu-id="c5ead-166">No campo Grupo de dimensões de rastreamento, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="c5ead-166">In the Tracking dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="c5ead-167">A dimensão de rastreamento não será usada neste exemplo.</span><span class="sxs-lookup"><span data-stu-id="c5ead-167">Tracking dimensions will not be used for this example.</span></span> <span data-ttu-id="c5ead-168">Selecione Nenhuma.</span><span class="sxs-lookup"><span data-stu-id="c5ead-168">Select None.</span></span>  
7. <span data-ttu-id="c5ead-169">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="c5ead-169">Click OK.</span></span>
8. <span data-ttu-id="c5ead-170">No Painel de Ação, clique em Gerenciar estoque.</span><span class="sxs-lookup"><span data-stu-id="c5ead-170">On the Action Pane, click Manage inventory.</span></span>
9. <span data-ttu-id="c5ead-171">Clique em Configurações de ordem padrão.</span><span class="sxs-lookup"><span data-stu-id="c5ead-171">Click Default order settings.</span></span>
10. <span data-ttu-id="c5ead-172">No campo Site de compra, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="c5ead-172">In the Purchase site field, enter or select a value.</span></span>
    * <span data-ttu-id="c5ead-173">Neste exemplo, selecione Site 1.</span><span class="sxs-lookup"><span data-stu-id="c5ead-173">For this example, select Site 1.</span></span>  
11. <span data-ttu-id="c5ead-174">No campo Site de estoque, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="c5ead-174">In the Inventory site field, enter or select a value.</span></span>
    * <span data-ttu-id="c5ead-175">Neste exemplo, selecione Site 1.</span><span class="sxs-lookup"><span data-stu-id="c5ead-175">For this example, select Site 1.</span></span>  
12. <span data-ttu-id="c5ead-176">No campo Site de vendas, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="c5ead-176">In the Sales site field, enter or select a value.</span></span>
    * <span data-ttu-id="c5ead-177">Neste exemplo, selecione Site 1.</span><span class="sxs-lookup"><span data-stu-id="c5ead-177">For this example, select Site 1.</span></span>  
13. <span data-ttu-id="c5ead-178">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="c5ead-178">Close the page.</span></span>
14. <span data-ttu-id="c5ead-179">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="c5ead-179">Close the page.</span></span>
15. <span data-ttu-id="c5ead-180">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="c5ead-180">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="c5ead-181">Clique em ITEM_B.</span><span class="sxs-lookup"><span data-stu-id="c5ead-181">Click ITEM_B.</span></span>  
16. <span data-ttu-id="c5ead-182">Expanda a seção Gerenciar custos.</span><span class="sxs-lookup"><span data-stu-id="c5ead-182">Expand the Manage costs section.</span></span>
17. <span data-ttu-id="c5ead-183">No campo Grupo de custos, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="c5ead-183">In the Cost group field, type a value.</span></span>
    * <span data-ttu-id="c5ead-184">Neste exemplo, digite M2.</span><span class="sxs-lookup"><span data-stu-id="c5ead-184">For this example, type M2.</span></span>  
18. <span data-ttu-id="c5ead-185">No Painel de Ação, clique em Gerenciar custos.</span><span class="sxs-lookup"><span data-stu-id="c5ead-185">On the Action Pane, click Manage costs.</span></span>
19. <span data-ttu-id="c5ead-186">Clique em Preço de item.</span><span class="sxs-lookup"><span data-stu-id="c5ead-186">Click Item price.</span></span>
20. <span data-ttu-id="c5ead-187">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="c5ead-187">Click New.</span></span>
21. <span data-ttu-id="c5ead-188">No campo Versão, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="c5ead-188">In the Version field, enter or select a value.</span></span>
    * <span data-ttu-id="c5ead-189">Neste exemplo, selecione 10.</span><span class="sxs-lookup"><span data-stu-id="c5ead-189">For this example, select 10.</span></span> <span data-ttu-id="c5ead-190">Este é o tipo de custo Custo padrão.</span><span class="sxs-lookup"><span data-stu-id="c5ead-190">This is the Standard cost costing type.</span></span>  
22. <span data-ttu-id="c5ead-191">No campo Local, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="c5ead-191">In the Site field, enter or select a value.</span></span>
    * <span data-ttu-id="c5ead-192">Neste exemplo, selecione Site 1.</span><span class="sxs-lookup"><span data-stu-id="c5ead-192">For this example, select Site 1.</span></span>  
23. <span data-ttu-id="c5ead-193">No campo Preço, insira um número.</span><span class="sxs-lookup"><span data-stu-id="c5ead-193">In the Price field, enter a number.</span></span>
    * <span data-ttu-id="c5ead-194">Para a demonstração, digite 10.</span><span class="sxs-lookup"><span data-stu-id="c5ead-194">For the demonstration, type 10.</span></span>  
24. <span data-ttu-id="c5ead-195">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="c5ead-195">Click Save.</span></span>
25. <span data-ttu-id="c5ead-196">Clique em Ativar preço(s) pendente(s).</span><span class="sxs-lookup"><span data-stu-id="c5ead-196">Click Activate pending price(s).</span></span>
26. <span data-ttu-id="c5ead-197">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="c5ead-197">Close the page.</span></span>
27. <span data-ttu-id="c5ead-198">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="c5ead-198">Close the page.</span></span>

## <a name="create-the-third-material"></a><span data-ttu-id="c5ead-199">Criar o terceiro material</span><span class="sxs-lookup"><span data-stu-id="c5ead-199">Create the third material</span></span>
1. <span data-ttu-id="c5ead-200">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="c5ead-200">Click New.</span></span>
2. <span data-ttu-id="c5ead-201">No campo Número do produto, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="c5ead-201">In the Product number field, type a value.</span></span>
    * <span data-ttu-id="c5ead-202">Para a demonstração, digite ITEM_C</span><span class="sxs-lookup"><span data-stu-id="c5ead-202">For the demonstration, type ITEM_C</span></span>  
3. <span data-ttu-id="c5ead-203">No campo Grupo de modelos do item, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="c5ead-203">In the Item model group field, enter or select a value.</span></span>
    * <span data-ttu-id="c5ead-204">Selecione STD.</span><span class="sxs-lookup"><span data-stu-id="c5ead-204">Select STD.</span></span> <span data-ttu-id="c5ead-205">STD significa "custo padrão" e é o modelo mais comumente utilizado ao se trabalhar com cálculos de custo.</span><span class="sxs-lookup"><span data-stu-id="c5ead-205">STD stands for standard cost and is the most commonly used model when working with cost calculations.</span></span>  
4. <span data-ttu-id="c5ead-206">No campo Grupo de itens, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="c5ead-206">In the Item group field, enter or select a value.</span></span>
    * <span data-ttu-id="c5ead-207">Por exemplo, selecione Áudio.</span><span class="sxs-lookup"><span data-stu-id="c5ead-207">For example, select Audio.</span></span> <span data-ttu-id="c5ead-208">Isso não tem impacto sobre os cálculos de custo.</span><span class="sxs-lookup"><span data-stu-id="c5ead-208">This has no impact on cost calculations.</span></span>  
5. <span data-ttu-id="c5ead-209">No campo Grupo de dimensões de armazenamento, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="c5ead-209">In the Storage dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="c5ead-210">Selecione SiteWH.</span><span class="sxs-lookup"><span data-stu-id="c5ead-210">Select SiteWH.</span></span> <span data-ttu-id="c5ead-211">Apenas Site e Depósito serão usados na demonstração.</span><span class="sxs-lookup"><span data-stu-id="c5ead-211">Only Site and Warehouse will be used for the demonstration.</span></span>  
6. <span data-ttu-id="c5ead-212">No campo Grupo de dimensões de rastreamento, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="c5ead-212">In the Tracking dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="c5ead-213">A dimensão de rastreamento não será usada neste exemplo.</span><span class="sxs-lookup"><span data-stu-id="c5ead-213">Tracking dimensions will not be used for this example.</span></span> <span data-ttu-id="c5ead-214">Selecione Nenhuma.</span><span class="sxs-lookup"><span data-stu-id="c5ead-214">Select None.</span></span>  
7. <span data-ttu-id="c5ead-215">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="c5ead-215">Click OK.</span></span>
8. <span data-ttu-id="c5ead-216">No Painel de Ação, clique em Gerenciar estoque.</span><span class="sxs-lookup"><span data-stu-id="c5ead-216">On the Action Pane, click Manage inventory.</span></span>
9. <span data-ttu-id="c5ead-217">Clique em Configurações de ordem padrão.</span><span class="sxs-lookup"><span data-stu-id="c5ead-217">Click Default order settings.</span></span>
10. <span data-ttu-id="c5ead-218">No campo Site de compra, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="c5ead-218">In the Purchase site field, enter or select a value.</span></span>
    * <span data-ttu-id="c5ead-219">Neste exemplo, selecione Site 1.</span><span class="sxs-lookup"><span data-stu-id="c5ead-219">For this example, select Site 1.</span></span>  
11. <span data-ttu-id="c5ead-220">No campo Site de estoque, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="c5ead-220">In the Inventory site field, enter or select a value.</span></span>
    * <span data-ttu-id="c5ead-221">Neste exemplo, selecione Site 1.</span><span class="sxs-lookup"><span data-stu-id="c5ead-221">For this example, select Site 1.</span></span>  
12. <span data-ttu-id="c5ead-222">No campo Site de vendas, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="c5ead-222">In the Sales site field, enter or select a value.</span></span>
    * <span data-ttu-id="c5ead-223">Neste exemplo, selecione Site 1.</span><span class="sxs-lookup"><span data-stu-id="c5ead-223">For this example, select Site 1.</span></span>  
13. <span data-ttu-id="c5ead-224">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="c5ead-224">Close the page.</span></span>
14. <span data-ttu-id="c5ead-225">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="c5ead-225">Close the page.</span></span>
15. <span data-ttu-id="c5ead-226">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="c5ead-226">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="c5ead-227">Clique em ITEM_C.</span><span class="sxs-lookup"><span data-stu-id="c5ead-227">Click ITEM_C.</span></span>  
16. <span data-ttu-id="c5ead-228">Expanda a seção Gerenciar custos.</span><span class="sxs-lookup"><span data-stu-id="c5ead-228">Expand the Manage costs section.</span></span>
17. <span data-ttu-id="c5ead-229">No campo Grupo de custos, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="c5ead-229">In the Cost group field, type a value.</span></span>
    * <span data-ttu-id="c5ead-230">Neste exemplo, digite M1.</span><span class="sxs-lookup"><span data-stu-id="c5ead-230">For this example, type M1.</span></span>  
18. <span data-ttu-id="c5ead-231">No Painel de Ação, clique em Gerenciar custos.</span><span class="sxs-lookup"><span data-stu-id="c5ead-231">On the Action Pane, click Manage costs.</span></span>
19. <span data-ttu-id="c5ead-232">Clique em Preço de item.</span><span class="sxs-lookup"><span data-stu-id="c5ead-232">Click Item price.</span></span>
20. <span data-ttu-id="c5ead-233">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="c5ead-233">Click New.</span></span>
21. <span data-ttu-id="c5ead-234">No campo Versão, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="c5ead-234">In the Version field, enter or select a value.</span></span>
    * <span data-ttu-id="c5ead-235">Neste exemplo, selecione 10.</span><span class="sxs-lookup"><span data-stu-id="c5ead-235">For this example, select 10.</span></span> <span data-ttu-id="c5ead-236">Este é o tipo de custo Custo padrão.</span><span class="sxs-lookup"><span data-stu-id="c5ead-236">This is the Standard cost costing type.</span></span>  
22. <span data-ttu-id="c5ead-237">No campo Local, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="c5ead-237">In the Site field, enter or select a value.</span></span>
    * <span data-ttu-id="c5ead-238">Neste exemplo, selecione Site 1.</span><span class="sxs-lookup"><span data-stu-id="c5ead-238">For this example, select Site 1.</span></span>  
23. <span data-ttu-id="c5ead-239">No campo Preço, insira um número.</span><span class="sxs-lookup"><span data-stu-id="c5ead-239">In the Price field, enter a number.</span></span>
    * <span data-ttu-id="c5ead-240">Neste exemplo, digite 10.</span><span class="sxs-lookup"><span data-stu-id="c5ead-240">For this example, type 10.</span></span>  
24. <span data-ttu-id="c5ead-241">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="c5ead-241">Click Save.</span></span>
25. <span data-ttu-id="c5ead-242">Clique em Ativar preço(s) pendente(s).</span><span class="sxs-lookup"><span data-stu-id="c5ead-242">Click Activate pending price(s).</span></span>
26. <span data-ttu-id="c5ead-243">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="c5ead-243">Close the page.</span></span>
27. <span data-ttu-id="c5ead-244">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="c5ead-244">Close the page.</span></span>


