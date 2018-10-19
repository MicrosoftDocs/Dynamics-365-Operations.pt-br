--- 
title: Criar roteiros (Fevereiro de 2016)
description: "Esta tarefa se concentra na criação dos roteiros de produção para produtos finalizados e semifinalizados."
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: EcoResProductDetailsExtended, RouteInventProd, RouteGroup
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 965826f5fddc2f53f33157434929eb265979376e
ms.openlocfilehash: a68b28c0e0ee14429a23d3241cabdae948d706d2
ms.contentlocale: pt-br
ms.lasthandoff: 09/17/2018

---
# <a name="create-routes-february-2016"></a><span data-ttu-id="a4a85-103">Criar roteiros (Fevereiro de 2016)</span><span class="sxs-lookup"><span data-stu-id="a4a85-103">Create routes (February 2016)</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="a4a85-104">Esta tarefa se concentra na criação dos roteiros de produção para produtos finalizados e semifinalizados.</span><span class="sxs-lookup"><span data-stu-id="a4a85-104">This task focuses on creating the production routes for a finished product and a semi-finished product.</span></span> <span data-ttu-id="a4a85-105">Trata-se da quinta tarefa na série de cálculo BOM.</span><span class="sxs-lookup"><span data-stu-id="a4a85-105">It is the fifth task in the BOM calculation series.</span></span> <span data-ttu-id="a4a85-106">A empresa de dados demo usada para criar esta tarefa é USMF.</span><span class="sxs-lookup"><span data-stu-id="a4a85-106">The demo data company used to create this task is USMF.</span></span>


## <a name="create-a-route-for-a-semi-finished-product"></a><span data-ttu-id="a4a85-107">Criar um roteiro para um produto semifinalizado</span><span class="sxs-lookup"><span data-stu-id="a4a85-107">Create a route for a semi-finished product</span></span>
1. <span data-ttu-id="a4a85-108">Vá para Gerenciamento de informações do produto > Produtos > Produtos liberados.</span><span class="sxs-lookup"><span data-stu-id="a4a85-108">Go to Product information management > Products > Released products.</span></span>
2. <span data-ttu-id="a4a85-109">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="a4a85-109">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="a4a85-110">Selecione o número de item BOM_2.</span><span class="sxs-lookup"><span data-stu-id="a4a85-110">Select the item number BOM_2.</span></span>  
3. <span data-ttu-id="a4a85-111">No Painel de Ação, clique em Engenharia.</span><span class="sxs-lookup"><span data-stu-id="a4a85-111">On the Action Pane, click Engineer.</span></span>
4. <span data-ttu-id="a4a85-112">Clique em Rota.</span><span class="sxs-lookup"><span data-stu-id="a4a85-112">Click Route.</span></span>
5. <span data-ttu-id="a4a85-113">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="a4a85-113">Click New.</span></span>
6. <span data-ttu-id="a4a85-114">Clique em Roteiro e versão de roteiro.</span><span class="sxs-lookup"><span data-stu-id="a4a85-114">Click Route and route version.</span></span>
7. <span data-ttu-id="a4a85-115">No campo Descrição, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="a4a85-115">In the Description field, type a value.</span></span>
    * <span data-ttu-id="a4a85-116">Por exemplo, digite ROUTE_2.</span><span class="sxs-lookup"><span data-stu-id="a4a85-116">For example, type ROUTE_2.</span></span>  
8. <span data-ttu-id="a4a85-117">No campo Local, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="a4a85-117">In the Site field, enter or select a value.</span></span>
    * <span data-ttu-id="a4a85-118">Neste exemplo, insira ou selecione Site 1.</span><span class="sxs-lookup"><span data-stu-id="a4a85-118">For this example, enter or select Site 1.</span></span>  
9. <span data-ttu-id="a4a85-119">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="a4a85-119">Click OK.</span></span>
10. <span data-ttu-id="a4a85-120">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="a4a85-120">Click New.</span></span>
11. <span data-ttu-id="a4a85-121">No campo Operação, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="a4a85-121">In the Operation field, enter or select a value.</span></span>
    * <span data-ttu-id="a4a85-122">Neste exemplo, selecione Montagem.</span><span class="sxs-lookup"><span data-stu-id="a4a85-122">For this example, select Assembly.</span></span>  
12. <span data-ttu-id="a4a85-123">No campo Tempo de execução, insira um número.</span><span class="sxs-lookup"><span data-stu-id="a4a85-123">In the Run time field, enter a number.</span></span>
    * <span data-ttu-id="a4a85-124">Por exemplo, digite 1.</span><span class="sxs-lookup"><span data-stu-id="a4a85-124">For example, type 1.</span></span> <span data-ttu-id="a4a85-125">O tempo de execução geralmente faz parte do preço que é calculado para um item.</span><span class="sxs-lookup"><span data-stu-id="a4a85-125">Run times are often part of the price that is calculated for an item.</span></span>  
13. <span data-ttu-id="a4a85-126">No campo Grupo de roteiro, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="a4a85-126">In the Route group field, enter or select a value.</span></span>
    * <span data-ttu-id="a4a85-127">Neste exemplo, selecione Std.</span><span class="sxs-lookup"><span data-stu-id="a4a85-127">For this example, select Std.</span></span>  
14. <span data-ttu-id="a4a85-128">Clique na guia Configuração.</span><span class="sxs-lookup"><span data-stu-id="a4a85-128">Click the Setup tab.</span></span>
15. <span data-ttu-id="a4a85-129">No campo categoria de Configuração, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="a4a85-129">In the Setup category field, enter or select a value.</span></span>
    * <span data-ttu-id="a4a85-130">Neste exemplo, selecione Montagem.</span><span class="sxs-lookup"><span data-stu-id="a4a85-130">For this example, select Assembly.</span></span>  
16. <span data-ttu-id="a4a85-131">Clique na guia Horas.</span><span class="sxs-lookup"><span data-stu-id="a4a85-131">Click the Times tab.</span></span>
17. <span data-ttu-id="a4a85-132">No campo Tempo de preparação, insira um número.</span><span class="sxs-lookup"><span data-stu-id="a4a85-132">In the Setup time field, enter a number.</span></span>
    * <span data-ttu-id="a4a85-133">Neste exemplo, digite 1.</span><span class="sxs-lookup"><span data-stu-id="a4a85-133">For this example, type 1.</span></span> <span data-ttu-id="a4a85-134">O tempo de preparação geralmente faz parte do preço que é calculado para um item.</span><span class="sxs-lookup"><span data-stu-id="a4a85-134">Setup times are often part of the price that is calculated for an item.</span></span>  
18. <span data-ttu-id="a4a85-135">No Painel de Ação, clique em Versão de roteiro.</span><span class="sxs-lookup"><span data-stu-id="a4a85-135">On the Action Pane, click Route version.</span></span>
19. <span data-ttu-id="a4a85-136">Clique em Aprovar.</span><span class="sxs-lookup"><span data-stu-id="a4a85-136">Click Approve.</span></span>
20. <span data-ttu-id="a4a85-137">Selecione Sim em Também deseja aprovar o roteiro? .</span><span class="sxs-lookup"><span data-stu-id="a4a85-137">Select Yes in the Do you also want to approve the route? field.</span></span>
21. <span data-ttu-id="a4a85-138">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="a4a85-138">Click OK.</span></span>
22. <span data-ttu-id="a4a85-139">No Painel de Ação, clique em Versão de roteiro.</span><span class="sxs-lookup"><span data-stu-id="a4a85-139">On the Action Pane, click Route version.</span></span>
23. <span data-ttu-id="a4a85-140">Clique em Ativar.</span><span class="sxs-lookup"><span data-stu-id="a4a85-140">Click Activate.</span></span>
24. <span data-ttu-id="a4a85-141">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="a4a85-141">Close the page.</span></span>
25. <span data-ttu-id="a4a85-142">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="a4a85-142">Close the page.</span></span>

## <a name="create-a-route-for-a-finished-product"></a><span data-ttu-id="a4a85-143">Criar um roteiro para um produto finalizado</span><span class="sxs-lookup"><span data-stu-id="a4a85-143">Create a route for a finished product</span></span>
1. <span data-ttu-id="a4a85-144">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="a4a85-144">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="a4a85-145">Selecione o número do item BOM_1.</span><span class="sxs-lookup"><span data-stu-id="a4a85-145">Select the item number BOM_1.</span></span>  
2. <span data-ttu-id="a4a85-146">No Painel de Ação, clique em Engenharia.</span><span class="sxs-lookup"><span data-stu-id="a4a85-146">On the Action Pane, click Engineer.</span></span>
3. <span data-ttu-id="a4a85-147">Clique em Rota.</span><span class="sxs-lookup"><span data-stu-id="a4a85-147">Click Route.</span></span>
4. <span data-ttu-id="a4a85-148">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="a4a85-148">Click New.</span></span>
5. <span data-ttu-id="a4a85-149">Clique em Roteiro e versão de roteiro.</span><span class="sxs-lookup"><span data-stu-id="a4a85-149">Click Route and route version.</span></span>
6. <span data-ttu-id="a4a85-150">No campo Descrição, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="a4a85-150">In the Description field, type a value.</span></span>
    * <span data-ttu-id="a4a85-151">Neste exemplo, digite ROUTE_1.</span><span class="sxs-lookup"><span data-stu-id="a4a85-151">For this example, type ROUTE_1.</span></span>  
7. <span data-ttu-id="a4a85-152">No campo Local, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="a4a85-152">In the Site field, enter or select a value.</span></span>
    * <span data-ttu-id="a4a85-153">Neste exemplo, insira ou selecione Site 1.</span><span class="sxs-lookup"><span data-stu-id="a4a85-153">For this example, enter or select Site 1.</span></span>  
8. <span data-ttu-id="a4a85-154">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="a4a85-154">Click OK.</span></span>
9. <span data-ttu-id="a4a85-155">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="a4a85-155">Click New.</span></span>
10. <span data-ttu-id="a4a85-156">No campo Operação, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="a4a85-156">In the Operation field, enter or select a value.</span></span>
    * <span data-ttu-id="a4a85-157">Neste exemplo, selecione Embalagem.</span><span class="sxs-lookup"><span data-stu-id="a4a85-157">For this example, select Packing.</span></span>  
11. <span data-ttu-id="a4a85-158">No campo Tempo de execução, insira um número.</span><span class="sxs-lookup"><span data-stu-id="a4a85-158">In the Run time field, enter a number.</span></span>
    * <span data-ttu-id="a4a85-159">Neste exemplo, digite 1.</span><span class="sxs-lookup"><span data-stu-id="a4a85-159">For this example, type 1.</span></span>  
12. <span data-ttu-id="a4a85-160">No campo Grupo de roteiro, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="a4a85-160">In the Route group field, enter or select a value.</span></span>
    * <span data-ttu-id="a4a85-161">Neste exemplo, selecione Std.</span><span class="sxs-lookup"><span data-stu-id="a4a85-161">For this example, select Std.</span></span>  
13. <span data-ttu-id="a4a85-162">Clique na guia Configuração.</span><span class="sxs-lookup"><span data-stu-id="a4a85-162">Click the Setup tab.</span></span>
14. <span data-ttu-id="a4a85-163">No campo categoria de Configuração, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="a4a85-163">In the Setup category field, enter or select a value.</span></span>
    * <span data-ttu-id="a4a85-164">Neste exemplo, selecione Embalagem.</span><span class="sxs-lookup"><span data-stu-id="a4a85-164">For this example, select Packing.</span></span>  
15. <span data-ttu-id="a4a85-165">Clique na guia Horas.</span><span class="sxs-lookup"><span data-stu-id="a4a85-165">Click the Times tab.</span></span>
16. <span data-ttu-id="a4a85-166">No campo Tempo de preparação, insira um número.</span><span class="sxs-lookup"><span data-stu-id="a4a85-166">In the Setup time field, enter a number.</span></span>
    * <span data-ttu-id="a4a85-167">Neste exemplo, digite 1.</span><span class="sxs-lookup"><span data-stu-id="a4a85-167">For this example, type 1.</span></span>  
17. <span data-ttu-id="a4a85-168">No Painel de Ação, clique em Versão de roteiro.</span><span class="sxs-lookup"><span data-stu-id="a4a85-168">On the Action Pane, click Route version.</span></span>
18. <span data-ttu-id="a4a85-169">Clique em Aprovar.</span><span class="sxs-lookup"><span data-stu-id="a4a85-169">Click Approve.</span></span>
19. <span data-ttu-id="a4a85-170">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="a4a85-170">Click OK.</span></span>
20. <span data-ttu-id="a4a85-171">No Painel de Ação, clique em Versão de roteiro.</span><span class="sxs-lookup"><span data-stu-id="a4a85-171">On the Action Pane, click Route version.</span></span>
21. <span data-ttu-id="a4a85-172">Clique em Ativar.</span><span class="sxs-lookup"><span data-stu-id="a4a85-172">Click Activate.</span></span>
22. <span data-ttu-id="a4a85-173">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="a4a85-173">Close the page.</span></span>
23. <span data-ttu-id="a4a85-174">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="a4a85-174">Close the page.</span></span>

## <a name="enable-automatic-consumption-of-setup-time"></a><span data-ttu-id="a4a85-175">Habilitar o consumo automático do tempo de preparação</span><span class="sxs-lookup"><span data-stu-id="a4a85-175">Enable automatic consumption of setup time</span></span>
1. <span data-ttu-id="a4a85-176">Vá para Controle de produção > Configuração > Roteiros > Grupos de roteiros.</span><span class="sxs-lookup"><span data-stu-id="a4a85-176">Go to Production control > Setup > Routes > Route groups.</span></span>
2. <span data-ttu-id="a4a85-177">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="a4a85-177">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="a4a85-178">Selecione Std na lista.</span><span class="sxs-lookup"><span data-stu-id="a4a85-178">Select Std in the list.</span></span>  
3. <span data-ttu-id="a4a85-179">Clique em Editar.</span><span class="sxs-lookup"><span data-stu-id="a4a85-179">Click Edit.</span></span>
4. <span data-ttu-id="a4a85-180">Selecione Sim no campo Tempo de preparação.</span><span class="sxs-lookup"><span data-stu-id="a4a85-180">Select Yes in the Setup time field.</span></span>
    * <span data-ttu-id="a4a85-181">O tempo de preparação geralmente faz parte do preço que é calculado para um item.</span><span class="sxs-lookup"><span data-stu-id="a4a85-181">Setup times are often part of the price that is calculated for an item.</span></span>  
5. <span data-ttu-id="a4a85-182">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="a4a85-182">Click Save.</span></span>
6. <span data-ttu-id="a4a85-183">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="a4a85-183">Close the page.</span></span>


