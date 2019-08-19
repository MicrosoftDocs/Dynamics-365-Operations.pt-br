---
title: Criar matérias-primas (Fevereiro de 2016)
description: Esta tarefa tem como foco criar os componentes de produtos finalizados e semifinalizados.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EcoResProductDetailsExtended, EcoResProductCreate, InventItemOrderSetup, InventItemPrice
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 9e20abf8a1b211bff2bc73d1a36a1e5c917ffaab
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/01/2019
ms.locfileid: "1844576"
---
# <a name="create-raw-materials-february-2016"></a><span data-ttu-id="574dd-103">Criar matérias-primas (Fevereiro de 2016)</span><span class="sxs-lookup"><span data-stu-id="574dd-103">Create raw materials (February 2016)</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="574dd-104">Esta tarefa tem como foco criar os componentes de produtos finalizados e semifinalizados.</span><span class="sxs-lookup"><span data-stu-id="574dd-104">This task focuses on creating the components of finished and semi-finished products.</span></span> <span data-ttu-id="574dd-105">Trata-se da terceira tarefa na série de cálculo BOM.</span><span class="sxs-lookup"><span data-stu-id="574dd-105">It is the third task in the BOM calculation series.</span></span> <span data-ttu-id="574dd-106">A empresa de dados demo usada para criar esta tarefa é USMF.</span><span class="sxs-lookup"><span data-stu-id="574dd-106">The demo data company used to create this task is USMF.</span></span>


## <a name="create-the-first-material"></a><span data-ttu-id="574dd-107">Criar o primeiro material</span><span class="sxs-lookup"><span data-stu-id="574dd-107">Create the first material</span></span>
1. <span data-ttu-id="574dd-108">Vá para Gerenciamento de informações do produto > Produtos > Produtos liberados.</span><span class="sxs-lookup"><span data-stu-id="574dd-108">Go to Product information management > Products > Released products.</span></span>
2. <span data-ttu-id="574dd-109">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="574dd-109">Click New.</span></span>
3. <span data-ttu-id="574dd-110">No campo Número do produto, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="574dd-110">In the Product number field, type a value.</span></span>
    * <span data-ttu-id="574dd-111">Neste exemplo, insira ITEM_A.</span><span class="sxs-lookup"><span data-stu-id="574dd-111">For this example, enter ITEM_A.</span></span>  
4. <span data-ttu-id="574dd-112">No campo Grupo de modelos do item, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="574dd-112">In the Item model group field, enter or select a value.</span></span>
    * <span data-ttu-id="574dd-113">Selecione STD.</span><span class="sxs-lookup"><span data-stu-id="574dd-113">Select STD.</span></span> <span data-ttu-id="574dd-114">STD significa "custo padrão" e é o modelo mais comumente utilizado ao se trabalhar com cálculos de custo.</span><span class="sxs-lookup"><span data-stu-id="574dd-114">STD stands for standard cost and is the most commonly used model when working with cost calculations.</span></span>  
5. <span data-ttu-id="574dd-115">No campo Grupo de itens, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="574dd-115">In the Item group field, enter or select a value.</span></span>
    * <span data-ttu-id="574dd-116">Por exemplo, selecione Áudio.</span><span class="sxs-lookup"><span data-stu-id="574dd-116">For example, select Audio.</span></span> <span data-ttu-id="574dd-117">Isso não tem impacto sobre os cálculos de custo.</span><span class="sxs-lookup"><span data-stu-id="574dd-117">This has no impact on cost calculations.</span></span>  
6. <span data-ttu-id="574dd-118">No campo Grupo de dimensões de armazenamento, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="574dd-118">In the Storage dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="574dd-119">Selecione SiteWH.</span><span class="sxs-lookup"><span data-stu-id="574dd-119">Select SiteWH.</span></span> <span data-ttu-id="574dd-120">Apenas Site e Depósito serão usados na demonstração.</span><span class="sxs-lookup"><span data-stu-id="574dd-120">Only Site and Warehouse will be used for the demonstration.</span></span>  
7. <span data-ttu-id="574dd-121">No campo Grupo de dimensões de rastreamento, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="574dd-121">In the Tracking dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="574dd-122">A dimensão de rastreamento não será usada neste exemplo.</span><span class="sxs-lookup"><span data-stu-id="574dd-122">Tracking dimensions will not be used for this example.</span></span> <span data-ttu-id="574dd-123">Selecione Nenhuma.</span><span class="sxs-lookup"><span data-stu-id="574dd-123">Select None.</span></span>  
8. <span data-ttu-id="574dd-124">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="574dd-124">Click OK.</span></span>
9. <span data-ttu-id="574dd-125">No Painel de Ação, clique em Gerenciar estoque.</span><span class="sxs-lookup"><span data-stu-id="574dd-125">On the Action Pane, click Manage inventory.</span></span>
10. <span data-ttu-id="574dd-126">Clique em Configurações de ordem padrão.</span><span class="sxs-lookup"><span data-stu-id="574dd-126">Click Default order settings.</span></span>
11. <span data-ttu-id="574dd-127">No campo Site de compra, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="574dd-127">In the Purchase site field, enter or select a value.</span></span>
    * <span data-ttu-id="574dd-128">Neste exemplo, selecione Site 1.</span><span class="sxs-lookup"><span data-stu-id="574dd-128">For this example, select Site 1.</span></span>  
12. <span data-ttu-id="574dd-129">No campo Site de estoque, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="574dd-129">In the Inventory site field, enter or select a value.</span></span>
    * <span data-ttu-id="574dd-130">Neste exemplo, selecione Site 1.</span><span class="sxs-lookup"><span data-stu-id="574dd-130">For this example, select Site 1.</span></span>  
13. <span data-ttu-id="574dd-131">No campo Site de vendas, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="574dd-131">In the Sales site field, enter or select a value.</span></span>
    * <span data-ttu-id="574dd-132">Neste exemplo, selecione Site 1.</span><span class="sxs-lookup"><span data-stu-id="574dd-132">For this example, select Site 1.</span></span>  
14. <span data-ttu-id="574dd-133">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="574dd-133">Close the page.</span></span>
15. <span data-ttu-id="574dd-134">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="574dd-134">Close the page.</span></span>
16. <span data-ttu-id="574dd-135">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="574dd-135">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="574dd-136">Clique em ITEM_A.</span><span class="sxs-lookup"><span data-stu-id="574dd-136">Click ITEM_A.</span></span>  
17. <span data-ttu-id="574dd-137">Expanda a seção Gerenciar custos.</span><span class="sxs-lookup"><span data-stu-id="574dd-137">Expand the Manage costs section.</span></span>
18. <span data-ttu-id="574dd-138">No campo Grupo de custos, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="574dd-138">In the Cost group field, type a value.</span></span>
    * <span data-ttu-id="574dd-139">Neste exemplo, digite M2.</span><span class="sxs-lookup"><span data-stu-id="574dd-139">For this example, type M2.</span></span>  
19. <span data-ttu-id="574dd-140">No Painel de Ação, clique em Gerenciar custos.</span><span class="sxs-lookup"><span data-stu-id="574dd-140">On the Action Pane, click Manage costs.</span></span>
20. <span data-ttu-id="574dd-141">Clique em Preço de item.</span><span class="sxs-lookup"><span data-stu-id="574dd-141">Click Item price.</span></span>
21. <span data-ttu-id="574dd-142">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="574dd-142">Click New.</span></span>
22. <span data-ttu-id="574dd-143">No campo Versão, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="574dd-143">In the Version field, enter or select a value.</span></span>
    * <span data-ttu-id="574dd-144">Neste exemplo, selecione 10, que é o tipo de custo Custo padrão.</span><span class="sxs-lookup"><span data-stu-id="574dd-144">For this example, select 10, which is the Standard cost costing type.</span></span>  
23. <span data-ttu-id="574dd-145">No campo Local, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="574dd-145">In the Site field, enter or select a value.</span></span>
    * <span data-ttu-id="574dd-146">Neste exemplo, selecione Site 1.</span><span class="sxs-lookup"><span data-stu-id="574dd-146">For this example, select Site 1.</span></span>  
24. <span data-ttu-id="574dd-147">No campo Preço, insira um número.</span><span class="sxs-lookup"><span data-stu-id="574dd-147">In the Price field, enter a number.</span></span>
    * <span data-ttu-id="574dd-148">Neste exemplo, digite 10.</span><span class="sxs-lookup"><span data-stu-id="574dd-148">For this example, type 10.</span></span>  
25. <span data-ttu-id="574dd-149">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="574dd-149">Click Save.</span></span>
26. <span data-ttu-id="574dd-150">Clique em Ativar preço(s) pendente(s).</span><span class="sxs-lookup"><span data-stu-id="574dd-150">Click Activate pending price(s).</span></span>
27. <span data-ttu-id="574dd-151">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="574dd-151">Close the page.</span></span>
28. <span data-ttu-id="574dd-152">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="574dd-152">Close the page.</span></span>

## <a name="create-the-second-material"></a><span data-ttu-id="574dd-153">Criar o segundo material</span><span class="sxs-lookup"><span data-stu-id="574dd-153">Create the second material</span></span>
1. <span data-ttu-id="574dd-154">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="574dd-154">Click New.</span></span>
2. <span data-ttu-id="574dd-155">No campo Número do produto, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="574dd-155">In the Product number field, type a value.</span></span>
    * <span data-ttu-id="574dd-156">Neste exemplo, digite ITEM_B.</span><span class="sxs-lookup"><span data-stu-id="574dd-156">For this example, type ITEM_B.</span></span>  
3. <span data-ttu-id="574dd-157">No campo Grupo de modelos do item, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="574dd-157">In the Item model group field, enter or select a value.</span></span>
    * <span data-ttu-id="574dd-158">Selecione STD.</span><span class="sxs-lookup"><span data-stu-id="574dd-158">Select STD.</span></span> <span data-ttu-id="574dd-159">STD significa "custo padrão" e é o modelo mais comumente utilizado ao se trabalhar com cálculos de custo.</span><span class="sxs-lookup"><span data-stu-id="574dd-159">STD stands for standard cost and is the most commonly used model when working with cost calculations.</span></span>  
4. <span data-ttu-id="574dd-160">No campo Grupo de itens, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="574dd-160">In the Item group field, enter or select a value.</span></span>
    * <span data-ttu-id="574dd-161">Por exemplo, selecione Áudio.</span><span class="sxs-lookup"><span data-stu-id="574dd-161">For example, select Audio.</span></span> <span data-ttu-id="574dd-162">Isso não tem impacto sobre os cálculos de custo.</span><span class="sxs-lookup"><span data-stu-id="574dd-162">This has no impact on cost calculations.</span></span>  
5. <span data-ttu-id="574dd-163">No campo Grupo de dimensões de armazenamento, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="574dd-163">In the Storage dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="574dd-164">Selecione SiteWH.</span><span class="sxs-lookup"><span data-stu-id="574dd-164">Select SiteWH.</span></span> <span data-ttu-id="574dd-165">Apenas Site e Depósito serão usados neste exemplo.</span><span class="sxs-lookup"><span data-stu-id="574dd-165">Only Site and Warehouse will be used for this example.</span></span>  
6. <span data-ttu-id="574dd-166">No campo Grupo de dimensões de rastreamento, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="574dd-166">In the Tracking dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="574dd-167">A dimensão de rastreamento não será usada neste exemplo.</span><span class="sxs-lookup"><span data-stu-id="574dd-167">Tracking dimensions will not be used for this example.</span></span> <span data-ttu-id="574dd-168">Selecione Nenhuma.</span><span class="sxs-lookup"><span data-stu-id="574dd-168">Select None.</span></span>  
7. <span data-ttu-id="574dd-169">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="574dd-169">Click OK.</span></span>
8. <span data-ttu-id="574dd-170">No Painel de Ação, clique em Gerenciar estoque.</span><span class="sxs-lookup"><span data-stu-id="574dd-170">On the Action Pane, click Manage inventory.</span></span>
9. <span data-ttu-id="574dd-171">Clique em Configurações de ordem padrão.</span><span class="sxs-lookup"><span data-stu-id="574dd-171">Click Default order settings.</span></span>
10. <span data-ttu-id="574dd-172">No campo Site de compra, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="574dd-172">In the Purchase site field, enter or select a value.</span></span>
    * <span data-ttu-id="574dd-173">Neste exemplo, selecione Site 1.</span><span class="sxs-lookup"><span data-stu-id="574dd-173">For this example, select Site 1.</span></span>  
11. <span data-ttu-id="574dd-174">No campo Site de estoque, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="574dd-174">In the Inventory site field, enter or select a value.</span></span>
    * <span data-ttu-id="574dd-175">Neste exemplo, selecione Site 1.</span><span class="sxs-lookup"><span data-stu-id="574dd-175">For this example, select Site 1.</span></span>  
12. <span data-ttu-id="574dd-176">No campo Site de vendas, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="574dd-176">In the Sales site field, enter or select a value.</span></span>
    * <span data-ttu-id="574dd-177">Neste exemplo, selecione Site 1.</span><span class="sxs-lookup"><span data-stu-id="574dd-177">For this example, select Site 1.</span></span>  
13. <span data-ttu-id="574dd-178">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="574dd-178">Close the page.</span></span>
14. <span data-ttu-id="574dd-179">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="574dd-179">Close the page.</span></span>
15. <span data-ttu-id="574dd-180">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="574dd-180">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="574dd-181">Clique em ITEM_B.</span><span class="sxs-lookup"><span data-stu-id="574dd-181">Click ITEM_B.</span></span>  
16. <span data-ttu-id="574dd-182">Expanda a seção Gerenciar custos.</span><span class="sxs-lookup"><span data-stu-id="574dd-182">Expand the Manage costs section.</span></span>
17. <span data-ttu-id="574dd-183">No campo Grupo de custos, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="574dd-183">In the Cost group field, type a value.</span></span>
    * <span data-ttu-id="574dd-184">Neste exemplo, digite M2.</span><span class="sxs-lookup"><span data-stu-id="574dd-184">For this example, type M2.</span></span>  
18. <span data-ttu-id="574dd-185">No Painel de Ação, clique em Gerenciar custos.</span><span class="sxs-lookup"><span data-stu-id="574dd-185">On the Action Pane, click Manage costs.</span></span>
19. <span data-ttu-id="574dd-186">Clique em Preço de item.</span><span class="sxs-lookup"><span data-stu-id="574dd-186">Click Item price.</span></span>
20. <span data-ttu-id="574dd-187">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="574dd-187">Click New.</span></span>
21. <span data-ttu-id="574dd-188">No campo Versão, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="574dd-188">In the Version field, enter or select a value.</span></span>
    * <span data-ttu-id="574dd-189">Neste exemplo, selecione 10.</span><span class="sxs-lookup"><span data-stu-id="574dd-189">For this example, select 10.</span></span> <span data-ttu-id="574dd-190">Este é o tipo de custo Custo padrão.</span><span class="sxs-lookup"><span data-stu-id="574dd-190">This is the Standard cost costing type.</span></span>  
22. <span data-ttu-id="574dd-191">No campo Local, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="574dd-191">In the Site field, enter or select a value.</span></span>
    * <span data-ttu-id="574dd-192">Neste exemplo, selecione Site 1.</span><span class="sxs-lookup"><span data-stu-id="574dd-192">For this example, select Site 1.</span></span>  
23. <span data-ttu-id="574dd-193">No campo Preço, insira um número.</span><span class="sxs-lookup"><span data-stu-id="574dd-193">In the Price field, enter a number.</span></span>
    * <span data-ttu-id="574dd-194">Para a demonstração, digite 10.</span><span class="sxs-lookup"><span data-stu-id="574dd-194">For the demonstration, type 10.</span></span>  
24. <span data-ttu-id="574dd-195">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="574dd-195">Click Save.</span></span>
25. <span data-ttu-id="574dd-196">Clique em Ativar preço(s) pendente(s).</span><span class="sxs-lookup"><span data-stu-id="574dd-196">Click Activate pending price(s).</span></span>
26. <span data-ttu-id="574dd-197">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="574dd-197">Close the page.</span></span>
27. <span data-ttu-id="574dd-198">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="574dd-198">Close the page.</span></span>

## <a name="create-the-third-material"></a><span data-ttu-id="574dd-199">Criar o terceiro material</span><span class="sxs-lookup"><span data-stu-id="574dd-199">Create the third material</span></span>
1. <span data-ttu-id="574dd-200">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="574dd-200">Click New.</span></span>
2. <span data-ttu-id="574dd-201">No campo Número do produto, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="574dd-201">In the Product number field, type a value.</span></span>
    * <span data-ttu-id="574dd-202">Para a demonstração, digite ITEM_C</span><span class="sxs-lookup"><span data-stu-id="574dd-202">For the demonstration, type ITEM_C</span></span>  
3. <span data-ttu-id="574dd-203">No campo Grupo de modelos do item, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="574dd-203">In the Item model group field, enter or select a value.</span></span>
    * <span data-ttu-id="574dd-204">Selecione STD.</span><span class="sxs-lookup"><span data-stu-id="574dd-204">Select STD.</span></span> <span data-ttu-id="574dd-205">STD significa "custo padrão" e é o modelo mais comumente utilizado ao se trabalhar com cálculos de custo.</span><span class="sxs-lookup"><span data-stu-id="574dd-205">STD stands for standard cost and is the most commonly used model when working with cost calculations.</span></span>  
4. <span data-ttu-id="574dd-206">No campo Grupo de itens, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="574dd-206">In the Item group field, enter or select a value.</span></span>
    * <span data-ttu-id="574dd-207">Por exemplo, selecione Áudio.</span><span class="sxs-lookup"><span data-stu-id="574dd-207">For example, select Audio.</span></span> <span data-ttu-id="574dd-208">Isso não tem impacto sobre os cálculos de custo.</span><span class="sxs-lookup"><span data-stu-id="574dd-208">This has no impact on cost calculations.</span></span>  
5. <span data-ttu-id="574dd-209">No campo Grupo de dimensões de armazenamento, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="574dd-209">In the Storage dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="574dd-210">Selecione SiteWH.</span><span class="sxs-lookup"><span data-stu-id="574dd-210">Select SiteWH.</span></span> <span data-ttu-id="574dd-211">Apenas Site e Depósito serão usados na demonstração.</span><span class="sxs-lookup"><span data-stu-id="574dd-211">Only Site and Warehouse will be used for the demonstration.</span></span>  
6. <span data-ttu-id="574dd-212">No campo Grupo de dimensões de rastreamento, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="574dd-212">In the Tracking dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="574dd-213">A dimensão de rastreamento não será usada neste exemplo.</span><span class="sxs-lookup"><span data-stu-id="574dd-213">Tracking dimensions will not be used for this example.</span></span> <span data-ttu-id="574dd-214">Selecione Nenhuma.</span><span class="sxs-lookup"><span data-stu-id="574dd-214">Select None.</span></span>  
7. <span data-ttu-id="574dd-215">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="574dd-215">Click OK.</span></span>
8. <span data-ttu-id="574dd-216">No Painel de Ação, clique em Gerenciar estoque.</span><span class="sxs-lookup"><span data-stu-id="574dd-216">On the Action Pane, click Manage inventory.</span></span>
9. <span data-ttu-id="574dd-217">Clique em Configurações de ordem padrão.</span><span class="sxs-lookup"><span data-stu-id="574dd-217">Click Default order settings.</span></span>
10. <span data-ttu-id="574dd-218">No campo Site de compra, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="574dd-218">In the Purchase site field, enter or select a value.</span></span>
    * <span data-ttu-id="574dd-219">Neste exemplo, selecione Site 1.</span><span class="sxs-lookup"><span data-stu-id="574dd-219">For this example, select Site 1.</span></span>  
11. <span data-ttu-id="574dd-220">No campo Site de estoque, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="574dd-220">In the Inventory site field, enter or select a value.</span></span>
    * <span data-ttu-id="574dd-221">Neste exemplo, selecione Site 1.</span><span class="sxs-lookup"><span data-stu-id="574dd-221">For this example, select Site 1.</span></span>  
12. <span data-ttu-id="574dd-222">No campo Site de vendas, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="574dd-222">In the Sales site field, enter or select a value.</span></span>
    * <span data-ttu-id="574dd-223">Neste exemplo, selecione Site 1.</span><span class="sxs-lookup"><span data-stu-id="574dd-223">For this example, select Site 1.</span></span>  
13. <span data-ttu-id="574dd-224">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="574dd-224">Close the page.</span></span>
14. <span data-ttu-id="574dd-225">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="574dd-225">Close the page.</span></span>
15. <span data-ttu-id="574dd-226">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="574dd-226">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="574dd-227">Clique em ITEM_C.</span><span class="sxs-lookup"><span data-stu-id="574dd-227">Click ITEM_C.</span></span>  
16. <span data-ttu-id="574dd-228">Expanda a seção Gerenciar custos.</span><span class="sxs-lookup"><span data-stu-id="574dd-228">Expand the Manage costs section.</span></span>
17. <span data-ttu-id="574dd-229">No campo Grupo de custos, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="574dd-229">In the Cost group field, type a value.</span></span>
    * <span data-ttu-id="574dd-230">Neste exemplo, digite M1.</span><span class="sxs-lookup"><span data-stu-id="574dd-230">For this example, type M1.</span></span>  
18. <span data-ttu-id="574dd-231">No Painel de Ação, clique em Gerenciar custos.</span><span class="sxs-lookup"><span data-stu-id="574dd-231">On the Action Pane, click Manage costs.</span></span>
19. <span data-ttu-id="574dd-232">Clique em Preço de item.</span><span class="sxs-lookup"><span data-stu-id="574dd-232">Click Item price.</span></span>
20. <span data-ttu-id="574dd-233">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="574dd-233">Click New.</span></span>
21. <span data-ttu-id="574dd-234">No campo Versão, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="574dd-234">In the Version field, enter or select a value.</span></span>
    * <span data-ttu-id="574dd-235">Neste exemplo, selecione 10.</span><span class="sxs-lookup"><span data-stu-id="574dd-235">For this example, select 10.</span></span> <span data-ttu-id="574dd-236">Este é o tipo de custo Custo padrão.</span><span class="sxs-lookup"><span data-stu-id="574dd-236">This is the Standard cost costing type.</span></span>  
22. <span data-ttu-id="574dd-237">No campo Local, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="574dd-237">In the Site field, enter or select a value.</span></span>
    * <span data-ttu-id="574dd-238">Neste exemplo, selecione Site 1.</span><span class="sxs-lookup"><span data-stu-id="574dd-238">For this example, select Site 1.</span></span>  
23. <span data-ttu-id="574dd-239">No campo Preço, insira um número.</span><span class="sxs-lookup"><span data-stu-id="574dd-239">In the Price field, enter a number.</span></span>
    * <span data-ttu-id="574dd-240">Neste exemplo, digite 10.</span><span class="sxs-lookup"><span data-stu-id="574dd-240">For this example, type 10.</span></span>  
24. <span data-ttu-id="574dd-241">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="574dd-241">Click Save.</span></span>
25. <span data-ttu-id="574dd-242">Clique em Ativar preço(s) pendente(s).</span><span class="sxs-lookup"><span data-stu-id="574dd-242">Click Activate pending price(s).</span></span>
26. <span data-ttu-id="574dd-243">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="574dd-243">Close the page.</span></span>
27. <span data-ttu-id="574dd-244">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="574dd-244">Close the page.</span></span>

