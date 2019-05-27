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
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 091b6edaf43e86e6e3665bf79871648473e284c7
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1552661"
---
# <a name="create-raw-materials-february-2016"></a><span data-ttu-id="544bb-103">Criar matérias-primas (Fevereiro de 2016)</span><span class="sxs-lookup"><span data-stu-id="544bb-103">Create raw materials (February 2016)</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="544bb-104">Esta tarefa tem como foco criar os componentes de produtos finalizados e semifinalizados.</span><span class="sxs-lookup"><span data-stu-id="544bb-104">This task focuses on creating the components of finished and semi-finished products.</span></span> <span data-ttu-id="544bb-105">Trata-se da terceira tarefa na série de cálculo BOM.</span><span class="sxs-lookup"><span data-stu-id="544bb-105">It is the third task in the BOM calculation series.</span></span> <span data-ttu-id="544bb-106">A empresa de dados demo usada para criar esta tarefa é USMF.</span><span class="sxs-lookup"><span data-stu-id="544bb-106">The demo data company used to create this task is USMF.</span></span>


## <a name="create-the-first-material"></a><span data-ttu-id="544bb-107">Criar o primeiro material</span><span class="sxs-lookup"><span data-stu-id="544bb-107">Create the first material</span></span>
1. <span data-ttu-id="544bb-108">Vá para Gerenciamento de informações do produto > Produtos > Produtos liberados.</span><span class="sxs-lookup"><span data-stu-id="544bb-108">Go to Product information management > Products > Released products.</span></span>
2. <span data-ttu-id="544bb-109">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="544bb-109">Click New.</span></span>
3. <span data-ttu-id="544bb-110">No campo Número do produto, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="544bb-110">In the Product number field, type a value.</span></span>
    * <span data-ttu-id="544bb-111">Neste exemplo, insira ITEM_A.</span><span class="sxs-lookup"><span data-stu-id="544bb-111">For this example, enter ITEM_A.</span></span>  
4. <span data-ttu-id="544bb-112">No campo Grupo de modelos do item, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="544bb-112">In the Item model group field, enter or select a value.</span></span>
    * <span data-ttu-id="544bb-113">Selecione STD.</span><span class="sxs-lookup"><span data-stu-id="544bb-113">Select STD.</span></span> <span data-ttu-id="544bb-114">STD significa "custo padrão" e é o modelo mais comumente utilizado ao se trabalhar com cálculos de custo.</span><span class="sxs-lookup"><span data-stu-id="544bb-114">STD stands for standard cost and is the most commonly used model when working with cost calculations.</span></span>  
5. <span data-ttu-id="544bb-115">No campo Grupo de itens, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="544bb-115">In the Item group field, enter or select a value.</span></span>
    * <span data-ttu-id="544bb-116">Por exemplo, selecione Áudio.</span><span class="sxs-lookup"><span data-stu-id="544bb-116">For example, select Audio.</span></span> <span data-ttu-id="544bb-117">Isso não tem impacto sobre os cálculos de custo.</span><span class="sxs-lookup"><span data-stu-id="544bb-117">This has no impact on cost calculations.</span></span>  
6. <span data-ttu-id="544bb-118">No campo Grupo de dimensões de armazenamento, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="544bb-118">In the Storage dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="544bb-119">Selecione SiteWH.</span><span class="sxs-lookup"><span data-stu-id="544bb-119">Select SiteWH.</span></span> <span data-ttu-id="544bb-120">Apenas Site e Depósito serão usados na demonstração.</span><span class="sxs-lookup"><span data-stu-id="544bb-120">Only Site and Warehouse will be used for the demonstration.</span></span>  
7. <span data-ttu-id="544bb-121">No campo Grupo de dimensões de rastreamento, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="544bb-121">In the Tracking dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="544bb-122">A dimensão de rastreamento não será usada neste exemplo.</span><span class="sxs-lookup"><span data-stu-id="544bb-122">Tracking dimensions will not be used for this example.</span></span> <span data-ttu-id="544bb-123">Selecione Nenhuma.</span><span class="sxs-lookup"><span data-stu-id="544bb-123">Select None.</span></span>  
8. <span data-ttu-id="544bb-124">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="544bb-124">Click OK.</span></span>
9. <span data-ttu-id="544bb-125">No Painel de Ação, clique em Gerenciar estoque.</span><span class="sxs-lookup"><span data-stu-id="544bb-125">On the Action Pane, click Manage inventory.</span></span>
10. <span data-ttu-id="544bb-126">Clique em Configurações de ordem padrão.</span><span class="sxs-lookup"><span data-stu-id="544bb-126">Click Default order settings.</span></span>
11. <span data-ttu-id="544bb-127">No campo Site de compra, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="544bb-127">In the Purchase site field, enter or select a value.</span></span>
    * <span data-ttu-id="544bb-128">Neste exemplo, selecione Site 1.</span><span class="sxs-lookup"><span data-stu-id="544bb-128">For this example, select Site 1.</span></span>  
12. <span data-ttu-id="544bb-129">No campo Site de estoque, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="544bb-129">In the Inventory site field, enter or select a value.</span></span>
    * <span data-ttu-id="544bb-130">Neste exemplo, selecione Site 1.</span><span class="sxs-lookup"><span data-stu-id="544bb-130">For this example, select Site 1.</span></span>  
13. <span data-ttu-id="544bb-131">No campo Site de vendas, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="544bb-131">In the Sales site field, enter or select a value.</span></span>
    * <span data-ttu-id="544bb-132">Neste exemplo, selecione Site 1.</span><span class="sxs-lookup"><span data-stu-id="544bb-132">For this example, select Site 1.</span></span>  
14. <span data-ttu-id="544bb-133">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="544bb-133">Close the page.</span></span>
15. <span data-ttu-id="544bb-134">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="544bb-134">Close the page.</span></span>
16. <span data-ttu-id="544bb-135">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="544bb-135">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="544bb-136">Clique em ITEM_A.</span><span class="sxs-lookup"><span data-stu-id="544bb-136">Click ITEM_A.</span></span>  
17. <span data-ttu-id="544bb-137">Expanda a seção Gerenciar custos.</span><span class="sxs-lookup"><span data-stu-id="544bb-137">Expand the Manage costs section.</span></span>
18. <span data-ttu-id="544bb-138">No campo Grupo de custos, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="544bb-138">In the Cost group field, type a value.</span></span>
    * <span data-ttu-id="544bb-139">Neste exemplo, digite M2.</span><span class="sxs-lookup"><span data-stu-id="544bb-139">For this example, type M2.</span></span>  
19. <span data-ttu-id="544bb-140">No Painel de Ação, clique em Gerenciar custos.</span><span class="sxs-lookup"><span data-stu-id="544bb-140">On the Action Pane, click Manage costs.</span></span>
20. <span data-ttu-id="544bb-141">Clique em Preço de item.</span><span class="sxs-lookup"><span data-stu-id="544bb-141">Click Item price.</span></span>
21. <span data-ttu-id="544bb-142">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="544bb-142">Click New.</span></span>
22. <span data-ttu-id="544bb-143">No campo Versão, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="544bb-143">In the Version field, enter or select a value.</span></span>
    * <span data-ttu-id="544bb-144">Neste exemplo, selecione 10, que é o tipo de custo Custo padrão.</span><span class="sxs-lookup"><span data-stu-id="544bb-144">For this example, select 10, which is the Standard cost costing type.</span></span>  
23. <span data-ttu-id="544bb-145">No campo Local, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="544bb-145">In the Site field, enter or select a value.</span></span>
    * <span data-ttu-id="544bb-146">Neste exemplo, selecione Site 1.</span><span class="sxs-lookup"><span data-stu-id="544bb-146">For this example, select Site 1.</span></span>  
24. <span data-ttu-id="544bb-147">No campo Preço, insira um número.</span><span class="sxs-lookup"><span data-stu-id="544bb-147">In the Price field, enter a number.</span></span>
    * <span data-ttu-id="544bb-148">Neste exemplo, digite 10.</span><span class="sxs-lookup"><span data-stu-id="544bb-148">For this example, type 10.</span></span>  
25. <span data-ttu-id="544bb-149">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="544bb-149">Click Save.</span></span>
26. <span data-ttu-id="544bb-150">Clique em Ativar preço(s) pendente(s).</span><span class="sxs-lookup"><span data-stu-id="544bb-150">Click Activate pending price(s).</span></span>
27. <span data-ttu-id="544bb-151">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="544bb-151">Close the page.</span></span>
28. <span data-ttu-id="544bb-152">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="544bb-152">Close the page.</span></span>

## <a name="create-the-second-material"></a><span data-ttu-id="544bb-153">Criar o segundo material</span><span class="sxs-lookup"><span data-stu-id="544bb-153">Create the second material</span></span>
1. <span data-ttu-id="544bb-154">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="544bb-154">Click New.</span></span>
2. <span data-ttu-id="544bb-155">No campo Número do produto, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="544bb-155">In the Product number field, type a value.</span></span>
    * <span data-ttu-id="544bb-156">Neste exemplo, digite ITEM_B.</span><span class="sxs-lookup"><span data-stu-id="544bb-156">For this example, type ITEM_B.</span></span>  
3. <span data-ttu-id="544bb-157">No campo Grupo de modelos do item, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="544bb-157">In the Item model group field, enter or select a value.</span></span>
    * <span data-ttu-id="544bb-158">Selecione STD.</span><span class="sxs-lookup"><span data-stu-id="544bb-158">Select STD.</span></span> <span data-ttu-id="544bb-159">STD significa "custo padrão" e é o modelo mais comumente utilizado ao se trabalhar com cálculos de custo.</span><span class="sxs-lookup"><span data-stu-id="544bb-159">STD stands for standard cost and is the most commonly used model when working with cost calculations.</span></span>  
4. <span data-ttu-id="544bb-160">No campo Grupo de itens, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="544bb-160">In the Item group field, enter or select a value.</span></span>
    * <span data-ttu-id="544bb-161">Por exemplo, selecione Áudio.</span><span class="sxs-lookup"><span data-stu-id="544bb-161">For example, select Audio.</span></span> <span data-ttu-id="544bb-162">Isso não tem impacto sobre os cálculos de custo.</span><span class="sxs-lookup"><span data-stu-id="544bb-162">This has no impact on cost calculations.</span></span>  
5. <span data-ttu-id="544bb-163">No campo Grupo de dimensões de armazenamento, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="544bb-163">In the Storage dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="544bb-164">Selecione SiteWH.</span><span class="sxs-lookup"><span data-stu-id="544bb-164">Select SiteWH.</span></span> <span data-ttu-id="544bb-165">Apenas Site e Depósito serão usados neste exemplo.</span><span class="sxs-lookup"><span data-stu-id="544bb-165">Only Site and Warehouse will be used for this example.</span></span>  
6. <span data-ttu-id="544bb-166">No campo Grupo de dimensões de rastreamento, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="544bb-166">In the Tracking dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="544bb-167">A dimensão de rastreamento não será usada neste exemplo.</span><span class="sxs-lookup"><span data-stu-id="544bb-167">Tracking dimensions will not be used for this example.</span></span> <span data-ttu-id="544bb-168">Selecione Nenhuma.</span><span class="sxs-lookup"><span data-stu-id="544bb-168">Select None.</span></span>  
7. <span data-ttu-id="544bb-169">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="544bb-169">Click OK.</span></span>
8. <span data-ttu-id="544bb-170">No Painel de Ação, clique em Gerenciar estoque.</span><span class="sxs-lookup"><span data-stu-id="544bb-170">On the Action Pane, click Manage inventory.</span></span>
9. <span data-ttu-id="544bb-171">Clique em Configurações de ordem padrão.</span><span class="sxs-lookup"><span data-stu-id="544bb-171">Click Default order settings.</span></span>
10. <span data-ttu-id="544bb-172">No campo Site de compra, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="544bb-172">In the Purchase site field, enter or select a value.</span></span>
    * <span data-ttu-id="544bb-173">Neste exemplo, selecione Site 1.</span><span class="sxs-lookup"><span data-stu-id="544bb-173">For this example, select Site 1.</span></span>  
11. <span data-ttu-id="544bb-174">No campo Site de estoque, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="544bb-174">In the Inventory site field, enter or select a value.</span></span>
    * <span data-ttu-id="544bb-175">Neste exemplo, selecione Site 1.</span><span class="sxs-lookup"><span data-stu-id="544bb-175">For this example, select Site 1.</span></span>  
12. <span data-ttu-id="544bb-176">No campo Site de vendas, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="544bb-176">In the Sales site field, enter or select a value.</span></span>
    * <span data-ttu-id="544bb-177">Neste exemplo, selecione Site 1.</span><span class="sxs-lookup"><span data-stu-id="544bb-177">For this example, select Site 1.</span></span>  
13. <span data-ttu-id="544bb-178">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="544bb-178">Close the page.</span></span>
14. <span data-ttu-id="544bb-179">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="544bb-179">Close the page.</span></span>
15. <span data-ttu-id="544bb-180">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="544bb-180">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="544bb-181">Clique em ITEM_B.</span><span class="sxs-lookup"><span data-stu-id="544bb-181">Click ITEM_B.</span></span>  
16. <span data-ttu-id="544bb-182">Expanda a seção Gerenciar custos.</span><span class="sxs-lookup"><span data-stu-id="544bb-182">Expand the Manage costs section.</span></span>
17. <span data-ttu-id="544bb-183">No campo Grupo de custos, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="544bb-183">In the Cost group field, type a value.</span></span>
    * <span data-ttu-id="544bb-184">Neste exemplo, digite M2.</span><span class="sxs-lookup"><span data-stu-id="544bb-184">For this example, type M2.</span></span>  
18. <span data-ttu-id="544bb-185">No Painel de Ação, clique em Gerenciar custos.</span><span class="sxs-lookup"><span data-stu-id="544bb-185">On the Action Pane, click Manage costs.</span></span>
19. <span data-ttu-id="544bb-186">Clique em Preço de item.</span><span class="sxs-lookup"><span data-stu-id="544bb-186">Click Item price.</span></span>
20. <span data-ttu-id="544bb-187">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="544bb-187">Click New.</span></span>
21. <span data-ttu-id="544bb-188">No campo Versão, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="544bb-188">In the Version field, enter or select a value.</span></span>
    * <span data-ttu-id="544bb-189">Neste exemplo, selecione 10.</span><span class="sxs-lookup"><span data-stu-id="544bb-189">For this example, select 10.</span></span> <span data-ttu-id="544bb-190">Este é o tipo de custo Custo padrão.</span><span class="sxs-lookup"><span data-stu-id="544bb-190">This is the Standard cost costing type.</span></span>  
22. <span data-ttu-id="544bb-191">No campo Local, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="544bb-191">In the Site field, enter or select a value.</span></span>
    * <span data-ttu-id="544bb-192">Neste exemplo, selecione Site 1.</span><span class="sxs-lookup"><span data-stu-id="544bb-192">For this example, select Site 1.</span></span>  
23. <span data-ttu-id="544bb-193">No campo Preço, insira um número.</span><span class="sxs-lookup"><span data-stu-id="544bb-193">In the Price field, enter a number.</span></span>
    * <span data-ttu-id="544bb-194">Para a demonstração, digite 10.</span><span class="sxs-lookup"><span data-stu-id="544bb-194">For the demonstration, type 10.</span></span>  
24. <span data-ttu-id="544bb-195">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="544bb-195">Click Save.</span></span>
25. <span data-ttu-id="544bb-196">Clique em Ativar preço(s) pendente(s).</span><span class="sxs-lookup"><span data-stu-id="544bb-196">Click Activate pending price(s).</span></span>
26. <span data-ttu-id="544bb-197">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="544bb-197">Close the page.</span></span>
27. <span data-ttu-id="544bb-198">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="544bb-198">Close the page.</span></span>

## <a name="create-the-third-material"></a><span data-ttu-id="544bb-199">Criar o terceiro material</span><span class="sxs-lookup"><span data-stu-id="544bb-199">Create the third material</span></span>
1. <span data-ttu-id="544bb-200">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="544bb-200">Click New.</span></span>
2. <span data-ttu-id="544bb-201">No campo Número do produto, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="544bb-201">In the Product number field, type a value.</span></span>
    * <span data-ttu-id="544bb-202">Para a demonstração, digite ITEM_C</span><span class="sxs-lookup"><span data-stu-id="544bb-202">For the demonstration, type ITEM_C</span></span>  
3. <span data-ttu-id="544bb-203">No campo Grupo de modelos do item, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="544bb-203">In the Item model group field, enter or select a value.</span></span>
    * <span data-ttu-id="544bb-204">Selecione STD.</span><span class="sxs-lookup"><span data-stu-id="544bb-204">Select STD.</span></span> <span data-ttu-id="544bb-205">STD significa "custo padrão" e é o modelo mais comumente utilizado ao se trabalhar com cálculos de custo.</span><span class="sxs-lookup"><span data-stu-id="544bb-205">STD stands for standard cost and is the most commonly used model when working with cost calculations.</span></span>  
4. <span data-ttu-id="544bb-206">No campo Grupo de itens, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="544bb-206">In the Item group field, enter or select a value.</span></span>
    * <span data-ttu-id="544bb-207">Por exemplo, selecione Áudio.</span><span class="sxs-lookup"><span data-stu-id="544bb-207">For example, select Audio.</span></span> <span data-ttu-id="544bb-208">Isso não tem impacto sobre os cálculos de custo.</span><span class="sxs-lookup"><span data-stu-id="544bb-208">This has no impact on cost calculations.</span></span>  
5. <span data-ttu-id="544bb-209">No campo Grupo de dimensões de armazenamento, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="544bb-209">In the Storage dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="544bb-210">Selecione SiteWH.</span><span class="sxs-lookup"><span data-stu-id="544bb-210">Select SiteWH.</span></span> <span data-ttu-id="544bb-211">Apenas Site e Depósito serão usados na demonstração.</span><span class="sxs-lookup"><span data-stu-id="544bb-211">Only Site and Warehouse will be used for the demonstration.</span></span>  
6. <span data-ttu-id="544bb-212">No campo Grupo de dimensões de rastreamento, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="544bb-212">In the Tracking dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="544bb-213">A dimensão de rastreamento não será usada neste exemplo.</span><span class="sxs-lookup"><span data-stu-id="544bb-213">Tracking dimensions will not be used for this example.</span></span> <span data-ttu-id="544bb-214">Selecione Nenhuma.</span><span class="sxs-lookup"><span data-stu-id="544bb-214">Select None.</span></span>  
7. <span data-ttu-id="544bb-215">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="544bb-215">Click OK.</span></span>
8. <span data-ttu-id="544bb-216">No Painel de Ação, clique em Gerenciar estoque.</span><span class="sxs-lookup"><span data-stu-id="544bb-216">On the Action Pane, click Manage inventory.</span></span>
9. <span data-ttu-id="544bb-217">Clique em Configurações de ordem padrão.</span><span class="sxs-lookup"><span data-stu-id="544bb-217">Click Default order settings.</span></span>
10. <span data-ttu-id="544bb-218">No campo Site de compra, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="544bb-218">In the Purchase site field, enter or select a value.</span></span>
    * <span data-ttu-id="544bb-219">Neste exemplo, selecione Site 1.</span><span class="sxs-lookup"><span data-stu-id="544bb-219">For this example, select Site 1.</span></span>  
11. <span data-ttu-id="544bb-220">No campo Site de estoque, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="544bb-220">In the Inventory site field, enter or select a value.</span></span>
    * <span data-ttu-id="544bb-221">Neste exemplo, selecione Site 1.</span><span class="sxs-lookup"><span data-stu-id="544bb-221">For this example, select Site 1.</span></span>  
12. <span data-ttu-id="544bb-222">No campo Site de vendas, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="544bb-222">In the Sales site field, enter or select a value.</span></span>
    * <span data-ttu-id="544bb-223">Neste exemplo, selecione Site 1.</span><span class="sxs-lookup"><span data-stu-id="544bb-223">For this example, select Site 1.</span></span>  
13. <span data-ttu-id="544bb-224">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="544bb-224">Close the page.</span></span>
14. <span data-ttu-id="544bb-225">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="544bb-225">Close the page.</span></span>
15. <span data-ttu-id="544bb-226">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="544bb-226">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="544bb-227">Clique em ITEM_C.</span><span class="sxs-lookup"><span data-stu-id="544bb-227">Click ITEM_C.</span></span>  
16. <span data-ttu-id="544bb-228">Expanda a seção Gerenciar custos.</span><span class="sxs-lookup"><span data-stu-id="544bb-228">Expand the Manage costs section.</span></span>
17. <span data-ttu-id="544bb-229">No campo Grupo de custos, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="544bb-229">In the Cost group field, type a value.</span></span>
    * <span data-ttu-id="544bb-230">Neste exemplo, digite M1.</span><span class="sxs-lookup"><span data-stu-id="544bb-230">For this example, type M1.</span></span>  
18. <span data-ttu-id="544bb-231">No Painel de Ação, clique em Gerenciar custos.</span><span class="sxs-lookup"><span data-stu-id="544bb-231">On the Action Pane, click Manage costs.</span></span>
19. <span data-ttu-id="544bb-232">Clique em Preço de item.</span><span class="sxs-lookup"><span data-stu-id="544bb-232">Click Item price.</span></span>
20. <span data-ttu-id="544bb-233">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="544bb-233">Click New.</span></span>
21. <span data-ttu-id="544bb-234">No campo Versão, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="544bb-234">In the Version field, enter or select a value.</span></span>
    * <span data-ttu-id="544bb-235">Neste exemplo, selecione 10.</span><span class="sxs-lookup"><span data-stu-id="544bb-235">For this example, select 10.</span></span> <span data-ttu-id="544bb-236">Este é o tipo de custo Custo padrão.</span><span class="sxs-lookup"><span data-stu-id="544bb-236">This is the Standard cost costing type.</span></span>  
22. <span data-ttu-id="544bb-237">No campo Local, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="544bb-237">In the Site field, enter or select a value.</span></span>
    * <span data-ttu-id="544bb-238">Neste exemplo, selecione Site 1.</span><span class="sxs-lookup"><span data-stu-id="544bb-238">For this example, select Site 1.</span></span>  
23. <span data-ttu-id="544bb-239">No campo Preço, insira um número.</span><span class="sxs-lookup"><span data-stu-id="544bb-239">In the Price field, enter a number.</span></span>
    * <span data-ttu-id="544bb-240">Neste exemplo, digite 10.</span><span class="sxs-lookup"><span data-stu-id="544bb-240">For this example, type 10.</span></span>  
24. <span data-ttu-id="544bb-241">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="544bb-241">Click Save.</span></span>
25. <span data-ttu-id="544bb-242">Clique em Ativar preço(s) pendente(s).</span><span class="sxs-lookup"><span data-stu-id="544bb-242">Click Activate pending price(s).</span></span>
26. <span data-ttu-id="544bb-243">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="544bb-243">Close the page.</span></span>
27. <span data-ttu-id="544bb-244">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="544bb-244">Close the page.</span></span>

