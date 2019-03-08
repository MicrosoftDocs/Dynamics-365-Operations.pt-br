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
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2019
ms.locfileid: "351047"
---
# <a name="create-raw-materials-february-2016"></a><span data-ttu-id="43505-103">Criar matérias-primas (Fevereiro de 2016)</span><span class="sxs-lookup"><span data-stu-id="43505-103">Create raw materials (February 2016)</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="43505-104">Esta tarefa tem como foco criar os componentes de produtos finalizados e semifinalizados.</span><span class="sxs-lookup"><span data-stu-id="43505-104">This task focuses on creating the components of finished and semi-finished products.</span></span> <span data-ttu-id="43505-105">Trata-se da terceira tarefa na série de cálculo BOM.</span><span class="sxs-lookup"><span data-stu-id="43505-105">It is the third task in the BOM calculation series.</span></span> <span data-ttu-id="43505-106">A empresa de dados demo usada para criar esta tarefa é USMF.</span><span class="sxs-lookup"><span data-stu-id="43505-106">The demo data company used to create this task is USMF.</span></span>


## <a name="create-the-first-material"></a><span data-ttu-id="43505-107">Criar o primeiro material</span><span class="sxs-lookup"><span data-stu-id="43505-107">Create the first material</span></span>
1. <span data-ttu-id="43505-108">Vá para Gerenciamento de informações do produto > Produtos > Produtos liberados.</span><span class="sxs-lookup"><span data-stu-id="43505-108">Go to Product information management > Products > Released products.</span></span>
2. <span data-ttu-id="43505-109">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="43505-109">Click New.</span></span>
3. <span data-ttu-id="43505-110">No campo Número do produto, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="43505-110">In the Product number field, type a value.</span></span>
    * <span data-ttu-id="43505-111">Neste exemplo, insira ITEM_A.</span><span class="sxs-lookup"><span data-stu-id="43505-111">For this example, enter ITEM_A.</span></span>  
4. <span data-ttu-id="43505-112">No campo Grupo de modelos do item, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="43505-112">In the Item model group field, enter or select a value.</span></span>
    * <span data-ttu-id="43505-113">Selecione STD.</span><span class="sxs-lookup"><span data-stu-id="43505-113">Select STD.</span></span> <span data-ttu-id="43505-114">STD significa "custo padrão" e é o modelo mais comumente utilizado ao se trabalhar com cálculos de custo.</span><span class="sxs-lookup"><span data-stu-id="43505-114">STD stands for standard cost and is the most commonly used model when working with cost calculations.</span></span>  
5. <span data-ttu-id="43505-115">No campo Grupo de itens, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="43505-115">In the Item group field, enter or select a value.</span></span>
    * <span data-ttu-id="43505-116">Por exemplo, selecione Áudio.</span><span class="sxs-lookup"><span data-stu-id="43505-116">For example, select Audio.</span></span> <span data-ttu-id="43505-117">Isso não tem impacto sobre os cálculos de custo.</span><span class="sxs-lookup"><span data-stu-id="43505-117">This has no impact on cost calculations.</span></span>  
6. <span data-ttu-id="43505-118">No campo Grupo de dimensões de armazenamento, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="43505-118">In the Storage dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="43505-119">Selecione SiteWH.</span><span class="sxs-lookup"><span data-stu-id="43505-119">Select SiteWH.</span></span> <span data-ttu-id="43505-120">Apenas Site e Depósito serão usados na demonstração.</span><span class="sxs-lookup"><span data-stu-id="43505-120">Only Site and Warehouse will be used for the demonstration.</span></span>  
7. <span data-ttu-id="43505-121">No campo Grupo de dimensões de rastreamento, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="43505-121">In the Tracking dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="43505-122">A dimensão de rastreamento não será usada neste exemplo.</span><span class="sxs-lookup"><span data-stu-id="43505-122">Tracking dimensions will not be used for this example.</span></span> <span data-ttu-id="43505-123">Selecione Nenhuma.</span><span class="sxs-lookup"><span data-stu-id="43505-123">Select None.</span></span>  
8. <span data-ttu-id="43505-124">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="43505-124">Click OK.</span></span>
9. <span data-ttu-id="43505-125">No Painel de Ação, clique em Gerenciar estoque.</span><span class="sxs-lookup"><span data-stu-id="43505-125">On the Action Pane, click Manage inventory.</span></span>
10. <span data-ttu-id="43505-126">Clique em Configurações de ordem padrão.</span><span class="sxs-lookup"><span data-stu-id="43505-126">Click Default order settings.</span></span>
11. <span data-ttu-id="43505-127">No campo Site de compra, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="43505-127">In the Purchase site field, enter or select a value.</span></span>
    * <span data-ttu-id="43505-128">Neste exemplo, selecione Site 1.</span><span class="sxs-lookup"><span data-stu-id="43505-128">For this example, select Site 1.</span></span>  
12. <span data-ttu-id="43505-129">No campo Site de estoque, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="43505-129">In the Inventory site field, enter or select a value.</span></span>
    * <span data-ttu-id="43505-130">Neste exemplo, selecione Site 1.</span><span class="sxs-lookup"><span data-stu-id="43505-130">For this example, select Site 1.</span></span>  
13. <span data-ttu-id="43505-131">No campo Site de vendas, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="43505-131">In the Sales site field, enter or select a value.</span></span>
    * <span data-ttu-id="43505-132">Neste exemplo, selecione Site 1.</span><span class="sxs-lookup"><span data-stu-id="43505-132">For this example, select Site 1.</span></span>  
14. <span data-ttu-id="43505-133">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="43505-133">Close the page.</span></span>
15. <span data-ttu-id="43505-134">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="43505-134">Close the page.</span></span>
16. <span data-ttu-id="43505-135">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="43505-135">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="43505-136">Clique em ITEM_A.</span><span class="sxs-lookup"><span data-stu-id="43505-136">Click ITEM_A.</span></span>  
17. <span data-ttu-id="43505-137">Expanda a seção Gerenciar custos.</span><span class="sxs-lookup"><span data-stu-id="43505-137">Expand the Manage costs section.</span></span>
18. <span data-ttu-id="43505-138">No campo Grupo de custos, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="43505-138">In the Cost group field, type a value.</span></span>
    * <span data-ttu-id="43505-139">Neste exemplo, digite M2.</span><span class="sxs-lookup"><span data-stu-id="43505-139">For this example, type M2.</span></span>  
19. <span data-ttu-id="43505-140">No Painel de Ação, clique em Gerenciar custos.</span><span class="sxs-lookup"><span data-stu-id="43505-140">On the Action Pane, click Manage costs.</span></span>
20. <span data-ttu-id="43505-141">Clique em Preço de item.</span><span class="sxs-lookup"><span data-stu-id="43505-141">Click Item price.</span></span>
21. <span data-ttu-id="43505-142">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="43505-142">Click New.</span></span>
22. <span data-ttu-id="43505-143">No campo Versão, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="43505-143">In the Version field, enter or select a value.</span></span>
    * <span data-ttu-id="43505-144">Neste exemplo, selecione 10, que é o tipo de custo Custo padrão.</span><span class="sxs-lookup"><span data-stu-id="43505-144">For this example, select 10, which is the Standard cost costing type.</span></span>  
23. <span data-ttu-id="43505-145">No campo Local, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="43505-145">In the Site field, enter or select a value.</span></span>
    * <span data-ttu-id="43505-146">Neste exemplo, selecione Site 1.</span><span class="sxs-lookup"><span data-stu-id="43505-146">For this example, select Site 1.</span></span>  
24. <span data-ttu-id="43505-147">No campo Preço, insira um número.</span><span class="sxs-lookup"><span data-stu-id="43505-147">In the Price field, enter a number.</span></span>
    * <span data-ttu-id="43505-148">Neste exemplo, digite 10.</span><span class="sxs-lookup"><span data-stu-id="43505-148">For this example, type 10.</span></span>  
25. <span data-ttu-id="43505-149">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="43505-149">Click Save.</span></span>
26. <span data-ttu-id="43505-150">Clique em Ativar preço(s) pendente(s).</span><span class="sxs-lookup"><span data-stu-id="43505-150">Click Activate pending price(s).</span></span>
27. <span data-ttu-id="43505-151">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="43505-151">Close the page.</span></span>
28. <span data-ttu-id="43505-152">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="43505-152">Close the page.</span></span>

## <a name="create-the-second-material"></a><span data-ttu-id="43505-153">Criar o segundo material</span><span class="sxs-lookup"><span data-stu-id="43505-153">Create the second material</span></span>
1. <span data-ttu-id="43505-154">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="43505-154">Click New.</span></span>
2. <span data-ttu-id="43505-155">No campo Número do produto, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="43505-155">In the Product number field, type a value.</span></span>
    * <span data-ttu-id="43505-156">Neste exemplo, digite ITEM_B.</span><span class="sxs-lookup"><span data-stu-id="43505-156">For this example, type ITEM_B.</span></span>  
3. <span data-ttu-id="43505-157">No campo Grupo de modelos do item, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="43505-157">In the Item model group field, enter or select a value.</span></span>
    * <span data-ttu-id="43505-158">Selecione STD.</span><span class="sxs-lookup"><span data-stu-id="43505-158">Select STD.</span></span> <span data-ttu-id="43505-159">STD significa "custo padrão" e é o modelo mais comumente utilizado ao se trabalhar com cálculos de custo.</span><span class="sxs-lookup"><span data-stu-id="43505-159">STD stands for standard cost and is the most commonly used model when working with cost calculations.</span></span>  
4. <span data-ttu-id="43505-160">No campo Grupo de itens, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="43505-160">In the Item group field, enter or select a value.</span></span>
    * <span data-ttu-id="43505-161">Por exemplo, selecione Áudio.</span><span class="sxs-lookup"><span data-stu-id="43505-161">For example, select Audio.</span></span> <span data-ttu-id="43505-162">Isso não tem impacto sobre os cálculos de custo.</span><span class="sxs-lookup"><span data-stu-id="43505-162">This has no impact on cost calculations.</span></span>  
5. <span data-ttu-id="43505-163">No campo Grupo de dimensões de armazenamento, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="43505-163">In the Storage dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="43505-164">Selecione SiteWH.</span><span class="sxs-lookup"><span data-stu-id="43505-164">Select SiteWH.</span></span> <span data-ttu-id="43505-165">Apenas Site e Depósito serão usados neste exemplo.</span><span class="sxs-lookup"><span data-stu-id="43505-165">Only Site and Warehouse will be used for this example.</span></span>  
6. <span data-ttu-id="43505-166">No campo Grupo de dimensões de rastreamento, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="43505-166">In the Tracking dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="43505-167">A dimensão de rastreamento não será usada neste exemplo.</span><span class="sxs-lookup"><span data-stu-id="43505-167">Tracking dimensions will not be used for this example.</span></span> <span data-ttu-id="43505-168">Selecione Nenhuma.</span><span class="sxs-lookup"><span data-stu-id="43505-168">Select None.</span></span>  
7. <span data-ttu-id="43505-169">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="43505-169">Click OK.</span></span>
8. <span data-ttu-id="43505-170">No Painel de Ação, clique em Gerenciar estoque.</span><span class="sxs-lookup"><span data-stu-id="43505-170">On the Action Pane, click Manage inventory.</span></span>
9. <span data-ttu-id="43505-171">Clique em Configurações de ordem padrão.</span><span class="sxs-lookup"><span data-stu-id="43505-171">Click Default order settings.</span></span>
10. <span data-ttu-id="43505-172">No campo Site de compra, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="43505-172">In the Purchase site field, enter or select a value.</span></span>
    * <span data-ttu-id="43505-173">Neste exemplo, selecione Site 1.</span><span class="sxs-lookup"><span data-stu-id="43505-173">For this example, select Site 1.</span></span>  
11. <span data-ttu-id="43505-174">No campo Site de estoque, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="43505-174">In the Inventory site field, enter or select a value.</span></span>
    * <span data-ttu-id="43505-175">Neste exemplo, selecione Site 1.</span><span class="sxs-lookup"><span data-stu-id="43505-175">For this example, select Site 1.</span></span>  
12. <span data-ttu-id="43505-176">No campo Site de vendas, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="43505-176">In the Sales site field, enter or select a value.</span></span>
    * <span data-ttu-id="43505-177">Neste exemplo, selecione Site 1.</span><span class="sxs-lookup"><span data-stu-id="43505-177">For this example, select Site 1.</span></span>  
13. <span data-ttu-id="43505-178">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="43505-178">Close the page.</span></span>
14. <span data-ttu-id="43505-179">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="43505-179">Close the page.</span></span>
15. <span data-ttu-id="43505-180">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="43505-180">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="43505-181">Clique em ITEM_B.</span><span class="sxs-lookup"><span data-stu-id="43505-181">Click ITEM_B.</span></span>  
16. <span data-ttu-id="43505-182">Expanda a seção Gerenciar custos.</span><span class="sxs-lookup"><span data-stu-id="43505-182">Expand the Manage costs section.</span></span>
17. <span data-ttu-id="43505-183">No campo Grupo de custos, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="43505-183">In the Cost group field, type a value.</span></span>
    * <span data-ttu-id="43505-184">Neste exemplo, digite M2.</span><span class="sxs-lookup"><span data-stu-id="43505-184">For this example, type M2.</span></span>  
18. <span data-ttu-id="43505-185">No Painel de Ação, clique em Gerenciar custos.</span><span class="sxs-lookup"><span data-stu-id="43505-185">On the Action Pane, click Manage costs.</span></span>
19. <span data-ttu-id="43505-186">Clique em Preço de item.</span><span class="sxs-lookup"><span data-stu-id="43505-186">Click Item price.</span></span>
20. <span data-ttu-id="43505-187">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="43505-187">Click New.</span></span>
21. <span data-ttu-id="43505-188">No campo Versão, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="43505-188">In the Version field, enter or select a value.</span></span>
    * <span data-ttu-id="43505-189">Neste exemplo, selecione 10.</span><span class="sxs-lookup"><span data-stu-id="43505-189">For this example, select 10.</span></span> <span data-ttu-id="43505-190">Este é o tipo de custo Custo padrão.</span><span class="sxs-lookup"><span data-stu-id="43505-190">This is the Standard cost costing type.</span></span>  
22. <span data-ttu-id="43505-191">No campo Local, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="43505-191">In the Site field, enter or select a value.</span></span>
    * <span data-ttu-id="43505-192">Neste exemplo, selecione Site 1.</span><span class="sxs-lookup"><span data-stu-id="43505-192">For this example, select Site 1.</span></span>  
23. <span data-ttu-id="43505-193">No campo Preço, insira um número.</span><span class="sxs-lookup"><span data-stu-id="43505-193">In the Price field, enter a number.</span></span>
    * <span data-ttu-id="43505-194">Para a demonstração, digite 10.</span><span class="sxs-lookup"><span data-stu-id="43505-194">For the demonstration, type 10.</span></span>  
24. <span data-ttu-id="43505-195">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="43505-195">Click Save.</span></span>
25. <span data-ttu-id="43505-196">Clique em Ativar preço(s) pendente(s).</span><span class="sxs-lookup"><span data-stu-id="43505-196">Click Activate pending price(s).</span></span>
26. <span data-ttu-id="43505-197">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="43505-197">Close the page.</span></span>
27. <span data-ttu-id="43505-198">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="43505-198">Close the page.</span></span>

## <a name="create-the-third-material"></a><span data-ttu-id="43505-199">Criar o terceiro material</span><span class="sxs-lookup"><span data-stu-id="43505-199">Create the third material</span></span>
1. <span data-ttu-id="43505-200">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="43505-200">Click New.</span></span>
2. <span data-ttu-id="43505-201">No campo Número do produto, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="43505-201">In the Product number field, type a value.</span></span>
    * <span data-ttu-id="43505-202">Para a demonstração, digite ITEM_C</span><span class="sxs-lookup"><span data-stu-id="43505-202">For the demonstration, type ITEM_C</span></span>  
3. <span data-ttu-id="43505-203">No campo Grupo de modelos do item, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="43505-203">In the Item model group field, enter or select a value.</span></span>
    * <span data-ttu-id="43505-204">Selecione STD.</span><span class="sxs-lookup"><span data-stu-id="43505-204">Select STD.</span></span> <span data-ttu-id="43505-205">STD significa "custo padrão" e é o modelo mais comumente utilizado ao se trabalhar com cálculos de custo.</span><span class="sxs-lookup"><span data-stu-id="43505-205">STD stands for standard cost and is the most commonly used model when working with cost calculations.</span></span>  
4. <span data-ttu-id="43505-206">No campo Grupo de itens, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="43505-206">In the Item group field, enter or select a value.</span></span>
    * <span data-ttu-id="43505-207">Por exemplo, selecione Áudio.</span><span class="sxs-lookup"><span data-stu-id="43505-207">For example, select Audio.</span></span> <span data-ttu-id="43505-208">Isso não tem impacto sobre os cálculos de custo.</span><span class="sxs-lookup"><span data-stu-id="43505-208">This has no impact on cost calculations.</span></span>  
5. <span data-ttu-id="43505-209">No campo Grupo de dimensões de armazenamento, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="43505-209">In the Storage dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="43505-210">Selecione SiteWH.</span><span class="sxs-lookup"><span data-stu-id="43505-210">Select SiteWH.</span></span> <span data-ttu-id="43505-211">Apenas Site e Depósito serão usados na demonstração.</span><span class="sxs-lookup"><span data-stu-id="43505-211">Only Site and Warehouse will be used for the demonstration.</span></span>  
6. <span data-ttu-id="43505-212">No campo Grupo de dimensões de rastreamento, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="43505-212">In the Tracking dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="43505-213">A dimensão de rastreamento não será usada neste exemplo.</span><span class="sxs-lookup"><span data-stu-id="43505-213">Tracking dimensions will not be used for this example.</span></span> <span data-ttu-id="43505-214">Selecione Nenhuma.</span><span class="sxs-lookup"><span data-stu-id="43505-214">Select None.</span></span>  
7. <span data-ttu-id="43505-215">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="43505-215">Click OK.</span></span>
8. <span data-ttu-id="43505-216">No Painel de Ação, clique em Gerenciar estoque.</span><span class="sxs-lookup"><span data-stu-id="43505-216">On the Action Pane, click Manage inventory.</span></span>
9. <span data-ttu-id="43505-217">Clique em Configurações de ordem padrão.</span><span class="sxs-lookup"><span data-stu-id="43505-217">Click Default order settings.</span></span>
10. <span data-ttu-id="43505-218">No campo Site de compra, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="43505-218">In the Purchase site field, enter or select a value.</span></span>
    * <span data-ttu-id="43505-219">Neste exemplo, selecione Site 1.</span><span class="sxs-lookup"><span data-stu-id="43505-219">For this example, select Site 1.</span></span>  
11. <span data-ttu-id="43505-220">No campo Site de estoque, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="43505-220">In the Inventory site field, enter or select a value.</span></span>
    * <span data-ttu-id="43505-221">Neste exemplo, selecione Site 1.</span><span class="sxs-lookup"><span data-stu-id="43505-221">For this example, select Site 1.</span></span>  
12. <span data-ttu-id="43505-222">No campo Site de vendas, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="43505-222">In the Sales site field, enter or select a value.</span></span>
    * <span data-ttu-id="43505-223">Neste exemplo, selecione Site 1.</span><span class="sxs-lookup"><span data-stu-id="43505-223">For this example, select Site 1.</span></span>  
13. <span data-ttu-id="43505-224">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="43505-224">Close the page.</span></span>
14. <span data-ttu-id="43505-225">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="43505-225">Close the page.</span></span>
15. <span data-ttu-id="43505-226">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="43505-226">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="43505-227">Clique em ITEM_C.</span><span class="sxs-lookup"><span data-stu-id="43505-227">Click ITEM_C.</span></span>  
16. <span data-ttu-id="43505-228">Expanda a seção Gerenciar custos.</span><span class="sxs-lookup"><span data-stu-id="43505-228">Expand the Manage costs section.</span></span>
17. <span data-ttu-id="43505-229">No campo Grupo de custos, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="43505-229">In the Cost group field, type a value.</span></span>
    * <span data-ttu-id="43505-230">Neste exemplo, digite M1.</span><span class="sxs-lookup"><span data-stu-id="43505-230">For this example, type M1.</span></span>  
18. <span data-ttu-id="43505-231">No Painel de Ação, clique em Gerenciar custos.</span><span class="sxs-lookup"><span data-stu-id="43505-231">On the Action Pane, click Manage costs.</span></span>
19. <span data-ttu-id="43505-232">Clique em Preço de item.</span><span class="sxs-lookup"><span data-stu-id="43505-232">Click Item price.</span></span>
20. <span data-ttu-id="43505-233">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="43505-233">Click New.</span></span>
21. <span data-ttu-id="43505-234">No campo Versão, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="43505-234">In the Version field, enter or select a value.</span></span>
    * <span data-ttu-id="43505-235">Neste exemplo, selecione 10.</span><span class="sxs-lookup"><span data-stu-id="43505-235">For this example, select 10.</span></span> <span data-ttu-id="43505-236">Este é o tipo de custo Custo padrão.</span><span class="sxs-lookup"><span data-stu-id="43505-236">This is the Standard cost costing type.</span></span>  
22. <span data-ttu-id="43505-237">No campo Local, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="43505-237">In the Site field, enter or select a value.</span></span>
    * <span data-ttu-id="43505-238">Neste exemplo, selecione Site 1.</span><span class="sxs-lookup"><span data-stu-id="43505-238">For this example, select Site 1.</span></span>  
23. <span data-ttu-id="43505-239">No campo Preço, insira um número.</span><span class="sxs-lookup"><span data-stu-id="43505-239">In the Price field, enter a number.</span></span>
    * <span data-ttu-id="43505-240">Neste exemplo, digite 10.</span><span class="sxs-lookup"><span data-stu-id="43505-240">For this example, type 10.</span></span>  
24. <span data-ttu-id="43505-241">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="43505-241">Click Save.</span></span>
25. <span data-ttu-id="43505-242">Clique em Ativar preço(s) pendente(s).</span><span class="sxs-lookup"><span data-stu-id="43505-242">Click Activate pending price(s).</span></span>
26. <span data-ttu-id="43505-243">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="43505-243">Close the page.</span></span>
27. <span data-ttu-id="43505-244">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="43505-244">Close the page.</span></span>

