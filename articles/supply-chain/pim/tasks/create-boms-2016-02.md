---
title: Criar BOMs (Fevereiro de 2016)
description: Esta tarefa tem como foco criar a estrutura de lista de materiais para produtos finalizados e semifinalizados.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EcoResProductDetailsExtended, BOMConsistOf, BOMTable, InventLocationIdLookup
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 0087c53d9cdc3bb65e6fa446c193c752d0f9b4fc
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/01/2019
ms.locfileid: "1845071"
---
# <a name="create-boms-february-2016"></a><span data-ttu-id="a0f92-103">Criar BOMs (Fevereiro de 2016)</span><span class="sxs-lookup"><span data-stu-id="a0f92-103">Create BOMs (February 2016)</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="a0f92-104">Esta tarefa tem como foco criar a estrutura de lista de materiais para produtos finalizados e semifinalizados.</span><span class="sxs-lookup"><span data-stu-id="a0f92-104">This task focuses on creating the bill of materials structure for a finished product and a semi-finished product.</span></span> <span data-ttu-id="a0f92-105">Trata-se da quarta tarefa na série de cálculo BOM.</span><span class="sxs-lookup"><span data-stu-id="a0f92-105">It is the fourth task in the BOM calculation series.</span></span> <span data-ttu-id="a0f92-106">A empresa de dados demo usada para criar esta tarefa é USMF.</span><span class="sxs-lookup"><span data-stu-id="a0f92-106">The demo data company used to create this task is USMF.</span></span>


## <a name="create-bom-for-a-semi-finished-product"></a><span data-ttu-id="a0f92-107">Criar BOM para um produto semifinalizado</span><span class="sxs-lookup"><span data-stu-id="a0f92-107">Create BOM for a semi-finished product</span></span>
1. <span data-ttu-id="a0f92-108">Vá para Gerenciamento de informações do produto > Produtos > Produtos liberados.</span><span class="sxs-lookup"><span data-stu-id="a0f92-108">Go to Product information management > Products > Released products.</span></span>
2. <span data-ttu-id="a0f92-109">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="a0f92-109">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="a0f92-110">Selecione o número de item BOM_2.</span><span class="sxs-lookup"><span data-stu-id="a0f92-110">Select the item number BOM_2.</span></span>  
3. <span data-ttu-id="a0f92-111">No Painel de Ação, clique em Engenharia.</span><span class="sxs-lookup"><span data-stu-id="a0f92-111">On the Action Pane, click Engineer.</span></span>
4. <span data-ttu-id="a0f92-112">Clique em Versões BOM.</span><span class="sxs-lookup"><span data-stu-id="a0f92-112">Click BOM versions.</span></span>
5. <span data-ttu-id="a0f92-113">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="a0f92-113">Click New.</span></span>
6. <span data-ttu-id="a0f92-114">Clique em Nova BOM e versão da BOM.</span><span class="sxs-lookup"><span data-stu-id="a0f92-114">Click BOM and BOM version.</span></span>
7. <span data-ttu-id="a0f92-115">No campo Nome, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="a0f92-115">In the Name field, type a value.</span></span>
    * <span data-ttu-id="a0f92-116">Por exemplo, digite BOM_2.</span><span class="sxs-lookup"><span data-stu-id="a0f92-116">For example, type BOM_2.</span></span>  
8. <span data-ttu-id="a0f92-117">No campo Local, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="a0f92-117">In the Site field, enter or select a value.</span></span>
    * <span data-ttu-id="a0f92-118">Neste exemplo, insira ou selecione Site 1.</span><span class="sxs-lookup"><span data-stu-id="a0f92-118">For this example, enter or select Site 1.</span></span>  
9. <span data-ttu-id="a0f92-119">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="a0f92-119">Click OK.</span></span>
10. <span data-ttu-id="a0f92-120">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="a0f92-120">Click New.</span></span>
11. <span data-ttu-id="a0f92-121">No campo Número de item, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="a0f92-121">In the Item number field, type a value.</span></span>
    * <span data-ttu-id="a0f92-122">Neste exemplo, digite ITEM_C.</span><span class="sxs-lookup"><span data-stu-id="a0f92-122">For this example, type ITEM_C.</span></span>  
12. <span data-ttu-id="a0f92-123">No campo Depósito, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="a0f92-123">In the Warehouse field, enter or select a value.</span></span>
    * <span data-ttu-id="a0f92-124">Neste exemplo, insira ou selecione 11.</span><span class="sxs-lookup"><span data-stu-id="a0f92-124">For this example, enter or select 11.</span></span>  
13. <span data-ttu-id="a0f92-125">Clique em Cabeçalho.</span><span class="sxs-lookup"><span data-stu-id="a0f92-125">Click Header.</span></span>
14. <span data-ttu-id="a0f92-126">Clique em Aprovação para aprovar listas de materiais.</span><span class="sxs-lookup"><span data-stu-id="a0f92-126">Click Approval to approve bills of materials.</span></span>
15. <span data-ttu-id="a0f92-127">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="a0f92-127">Click OK.</span></span>
16. <span data-ttu-id="a0f92-128">Clique em Aprovar.</span><span class="sxs-lookup"><span data-stu-id="a0f92-128">Click Approve.</span></span>
    * <span data-ttu-id="a0f92-129">O botão Aprovar está na Barra de Ferramentas na seção Versões de BOM.</span><span class="sxs-lookup"><span data-stu-id="a0f92-129">The Approve button is on the ToolBar in the  BOM versions section.</span></span> <span data-ttu-id="a0f92-130">Se ele estiver invisível, clique em Cabeçalho no canto superior direito da página Listas de materiais para exibir Aprovar.</span><span class="sxs-lookup"><span data-stu-id="a0f92-130">If it is invisible, click Header at the upper right of the Bills of materials page to display Approve.</span></span>  
17. <span data-ttu-id="a0f92-131">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="a0f92-131">Click OK.</span></span>
18. <span data-ttu-id="a0f92-132">Clique em Ativar.</span><span class="sxs-lookup"><span data-stu-id="a0f92-132">Click Activate.</span></span>
19. <span data-ttu-id="a0f92-133">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="a0f92-133">Close the page.</span></span>
20. <span data-ttu-id="a0f92-134">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="a0f92-134">Close the page.</span></span>
21. <span data-ttu-id="a0f92-135">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="a0f92-135">Close the page.</span></span>

## <a name="create-bom-for-a-finished-product"></a><span data-ttu-id="a0f92-136">Criar BOM para um produto finalizado</span><span class="sxs-lookup"><span data-stu-id="a0f92-136">Create BOM for a finished product</span></span>
1. <span data-ttu-id="a0f92-137">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="a0f92-137">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="a0f92-138">Selecione o número do item BOM_1.</span><span class="sxs-lookup"><span data-stu-id="a0f92-138">Select the item number BOM_1.</span></span>  
2. <span data-ttu-id="a0f92-139">No Painel de Ação, clique em Engenharia.</span><span class="sxs-lookup"><span data-stu-id="a0f92-139">On the Action Pane, click Engineer.</span></span>
3. <span data-ttu-id="a0f92-140">Clique em Versões BOM.</span><span class="sxs-lookup"><span data-stu-id="a0f92-140">Click BOM versions.</span></span>
4. <span data-ttu-id="a0f92-141">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="a0f92-141">Click New.</span></span>
5. <span data-ttu-id="a0f92-142">Clique em Nova BOM e versão da BOM.</span><span class="sxs-lookup"><span data-stu-id="a0f92-142">Click BOM and BOM version.</span></span>
6. <span data-ttu-id="a0f92-143">No campo Nome, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="a0f92-143">In the Name field, type a value.</span></span>
    * <span data-ttu-id="a0f92-144">Por exemplo, digite BOM_1.</span><span class="sxs-lookup"><span data-stu-id="a0f92-144">For example, type BOM_1.</span></span>  
7. <span data-ttu-id="a0f92-145">No campo Local, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="a0f92-145">In the Site field, enter or select a value.</span></span>
    * <span data-ttu-id="a0f92-146">Neste exemplo, insira ou selecione Site 1.</span><span class="sxs-lookup"><span data-stu-id="a0f92-146">For this example, enter or select Site 1.</span></span>  
8. <span data-ttu-id="a0f92-147">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="a0f92-147">Click OK.</span></span>
9. <span data-ttu-id="a0f92-148">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="a0f92-148">Click New.</span></span>
10. <span data-ttu-id="a0f92-149">No campo Número de item, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="a0f92-149">In the Item number field, type a value.</span></span>
    * <span data-ttu-id="a0f92-150">Neste exemplo, digite ITEM_A.</span><span class="sxs-lookup"><span data-stu-id="a0f92-150">For this example, type ITEM_A.</span></span>  
11. <span data-ttu-id="a0f92-151">No campo Depósito, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="a0f92-151">In the Warehouse field, enter or select a value.</span></span>
    * <span data-ttu-id="a0f92-152">Neste exemplo, selecione 11.</span><span class="sxs-lookup"><span data-stu-id="a0f92-152">For this example, select 11.</span></span>  
12. <span data-ttu-id="a0f92-153">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="a0f92-153">Click New.</span></span>
13. <span data-ttu-id="a0f92-154">No campo Número de item, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="a0f92-154">In the Item number field, type a value.</span></span>
    * <span data-ttu-id="a0f92-155">Neste exemplo, digite ITEM_B.</span><span class="sxs-lookup"><span data-stu-id="a0f92-155">For this example, type ITEM_B.</span></span>  
14. <span data-ttu-id="a0f92-156">No campo Depósito, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="a0f92-156">In the Warehouse field, enter or select a value.</span></span>
    * <span data-ttu-id="a0f92-157">Neste exemplo, insira ou selecione 11.</span><span class="sxs-lookup"><span data-stu-id="a0f92-157">For this example, enter or select 11.</span></span>  
15. <span data-ttu-id="a0f92-158">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="a0f92-158">Click New.</span></span>
16. <span data-ttu-id="a0f92-159">No campo Número de item, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="a0f92-159">In the Item number field, type a value.</span></span>
    * <span data-ttu-id="a0f92-160">Neste exemplo, digite BOM_2.</span><span class="sxs-lookup"><span data-stu-id="a0f92-160">For this example, type BOM_2.</span></span>  
17. <span data-ttu-id="a0f92-161">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="a0f92-161">In the list, mark the selected row.</span></span>
18. <span data-ttu-id="a0f92-162">No campo Depósito, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="a0f92-162">In the Warehouse field, enter or select a value.</span></span>
    * <span data-ttu-id="a0f92-163">Neste exemplo, insira ou selecione depósito 11.</span><span class="sxs-lookup"><span data-stu-id="a0f92-163">For this example, enter or select warehouse 11.</span></span>  
19. <span data-ttu-id="a0f92-164">Clique em Cabeçalho.</span><span class="sxs-lookup"><span data-stu-id="a0f92-164">Click Header.</span></span>
20. <span data-ttu-id="a0f92-165">Clique em Aprovação para aprovar listas de materiais.</span><span class="sxs-lookup"><span data-stu-id="a0f92-165">Click Approval to approve bills of materials.</span></span>
21. <span data-ttu-id="a0f92-166">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="a0f92-166">Click OK.</span></span>
22. <span data-ttu-id="a0f92-167">Clique em Aprovar.</span><span class="sxs-lookup"><span data-stu-id="a0f92-167">Click Approve.</span></span>
    * <span data-ttu-id="a0f92-168">O botão Aprovar está na Barra de Ferramentas na seção Versões de BOM.</span><span class="sxs-lookup"><span data-stu-id="a0f92-168">The Approve button is on the ToolBar in the  BOM versions section.</span></span> <span data-ttu-id="a0f92-169">Se ele estiver invisível, clique em Cabeçalho no canto superior direito da página Listas de materiais para exibir Aprovar.</span><span class="sxs-lookup"><span data-stu-id="a0f92-169">If it is invisible, click Header at the upper right of the Bills of materials page to display Approve.</span></span>  
23. <span data-ttu-id="a0f92-170">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="a0f92-170">Click OK.</span></span>
24. <span data-ttu-id="a0f92-171">Clique em Ativar.</span><span class="sxs-lookup"><span data-stu-id="a0f92-171">Click Activate.</span></span>
25. <span data-ttu-id="a0f92-172">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="a0f92-172">Close the page.</span></span>
26. <span data-ttu-id="a0f92-173">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="a0f92-173">Close the page.</span></span>
27. <span data-ttu-id="a0f92-174">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="a0f92-174">Close the page.</span></span>

