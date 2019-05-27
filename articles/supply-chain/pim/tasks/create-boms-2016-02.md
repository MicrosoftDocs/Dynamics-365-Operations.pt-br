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
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 6c5cfb8aae1a61d14f7a7969f688cb282530840d
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1568549"
---
# <a name="create-boms-february-2016"></a><span data-ttu-id="b1699-103">Criar BOMs (Fevereiro de 2016)</span><span class="sxs-lookup"><span data-stu-id="b1699-103">Create BOMs (February 2016)</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="b1699-104">Esta tarefa tem como foco criar a estrutura de lista de materiais para produtos finalizados e semifinalizados.</span><span class="sxs-lookup"><span data-stu-id="b1699-104">This task focuses on creating the bill of materials structure for a finished product and a semi-finished product.</span></span> <span data-ttu-id="b1699-105">Trata-se da quarta tarefa na série de cálculo BOM.</span><span class="sxs-lookup"><span data-stu-id="b1699-105">It is the fourth task in the BOM calculation series.</span></span> <span data-ttu-id="b1699-106">A empresa de dados demo usada para criar esta tarefa é USMF.</span><span class="sxs-lookup"><span data-stu-id="b1699-106">The demo data company used to create this task is USMF.</span></span>


## <a name="create-bom-for-a-semi-finished-product"></a><span data-ttu-id="b1699-107">Criar BOM para um produto semifinalizado</span><span class="sxs-lookup"><span data-stu-id="b1699-107">Create BOM for a semi-finished product</span></span>
1. <span data-ttu-id="b1699-108">Vá para Gerenciamento de informações do produto > Produtos > Produtos liberados.</span><span class="sxs-lookup"><span data-stu-id="b1699-108">Go to Product information management > Products > Released products.</span></span>
2. <span data-ttu-id="b1699-109">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="b1699-109">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="b1699-110">Selecione o número de item BOM_2.</span><span class="sxs-lookup"><span data-stu-id="b1699-110">Select the item number BOM_2.</span></span>  
3. <span data-ttu-id="b1699-111">No Painel de Ação, clique em Engenharia.</span><span class="sxs-lookup"><span data-stu-id="b1699-111">On the Action Pane, click Engineer.</span></span>
4. <span data-ttu-id="b1699-112">Clique em Versões BOM.</span><span class="sxs-lookup"><span data-stu-id="b1699-112">Click BOM versions.</span></span>
5. <span data-ttu-id="b1699-113">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="b1699-113">Click New.</span></span>
6. <span data-ttu-id="b1699-114">Clique em Nova BOM e versão da BOM.</span><span class="sxs-lookup"><span data-stu-id="b1699-114">Click BOM and BOM version.</span></span>
7. <span data-ttu-id="b1699-115">No campo Nome, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="b1699-115">In the Name field, type a value.</span></span>
    * <span data-ttu-id="b1699-116">Por exemplo, digite BOM_2.</span><span class="sxs-lookup"><span data-stu-id="b1699-116">For example, type BOM_2.</span></span>  
8. <span data-ttu-id="b1699-117">No campo Local, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="b1699-117">In the Site field, enter or select a value.</span></span>
    * <span data-ttu-id="b1699-118">Neste exemplo, insira ou selecione Site 1.</span><span class="sxs-lookup"><span data-stu-id="b1699-118">For this example, enter or select Site 1.</span></span>  
9. <span data-ttu-id="b1699-119">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="b1699-119">Click OK.</span></span>
10. <span data-ttu-id="b1699-120">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="b1699-120">Click New.</span></span>
11. <span data-ttu-id="b1699-121">No campo Número de item, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="b1699-121">In the Item number field, type a value.</span></span>
    * <span data-ttu-id="b1699-122">Neste exemplo, digite ITEM_C.</span><span class="sxs-lookup"><span data-stu-id="b1699-122">For this example, type ITEM_C.</span></span>  
12. <span data-ttu-id="b1699-123">No campo Depósito, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="b1699-123">In the Warehouse field, enter or select a value.</span></span>
    * <span data-ttu-id="b1699-124">Neste exemplo, insira ou selecione 11.</span><span class="sxs-lookup"><span data-stu-id="b1699-124">For this example, enter or select 11.</span></span>  
13. <span data-ttu-id="b1699-125">Clique em Cabeçalho.</span><span class="sxs-lookup"><span data-stu-id="b1699-125">Click Header.</span></span>
14. <span data-ttu-id="b1699-126">Clique em Aprovação para aprovar listas de materiais.</span><span class="sxs-lookup"><span data-stu-id="b1699-126">Click Approval to approve bills of materials.</span></span>
15. <span data-ttu-id="b1699-127">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="b1699-127">Click OK.</span></span>
16. <span data-ttu-id="b1699-128">Clique em Aprovar.</span><span class="sxs-lookup"><span data-stu-id="b1699-128">Click Approve.</span></span>
    * <span data-ttu-id="b1699-129">O botão Aprovar está na Barra de Ferramentas na seção Versões de BOM.</span><span class="sxs-lookup"><span data-stu-id="b1699-129">The Approve button is on the ToolBar in the  BOM versions section.</span></span> <span data-ttu-id="b1699-130">Se ele estiver invisível, clique em Cabeçalho no canto superior direito da página Listas de materiais para exibir Aprovar.</span><span class="sxs-lookup"><span data-stu-id="b1699-130">If it is invisible, click Header at the upper right of the Bills of materials page to display Approve.</span></span>  
17. <span data-ttu-id="b1699-131">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="b1699-131">Click OK.</span></span>
18. <span data-ttu-id="b1699-132">Clique em Ativar.</span><span class="sxs-lookup"><span data-stu-id="b1699-132">Click Activate.</span></span>
19. <span data-ttu-id="b1699-133">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="b1699-133">Close the page.</span></span>
20. <span data-ttu-id="b1699-134">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="b1699-134">Close the page.</span></span>
21. <span data-ttu-id="b1699-135">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="b1699-135">Close the page.</span></span>

## <a name="create-bom-for-a-finished-product"></a><span data-ttu-id="b1699-136">Criar BOM para um produto finalizado</span><span class="sxs-lookup"><span data-stu-id="b1699-136">Create BOM for a finished product</span></span>
1. <span data-ttu-id="b1699-137">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="b1699-137">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="b1699-138">Selecione o número do item BOM_1.</span><span class="sxs-lookup"><span data-stu-id="b1699-138">Select the item number BOM_1.</span></span>  
2. <span data-ttu-id="b1699-139">No Painel de Ação, clique em Engenharia.</span><span class="sxs-lookup"><span data-stu-id="b1699-139">On the Action Pane, click Engineer.</span></span>
3. <span data-ttu-id="b1699-140">Clique em Versões BOM.</span><span class="sxs-lookup"><span data-stu-id="b1699-140">Click BOM versions.</span></span>
4. <span data-ttu-id="b1699-141">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="b1699-141">Click New.</span></span>
5. <span data-ttu-id="b1699-142">Clique em Nova BOM e versão da BOM.</span><span class="sxs-lookup"><span data-stu-id="b1699-142">Click BOM and BOM version.</span></span>
6. <span data-ttu-id="b1699-143">No campo Nome, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="b1699-143">In the Name field, type a value.</span></span>
    * <span data-ttu-id="b1699-144">Por exemplo, digite BOM_1.</span><span class="sxs-lookup"><span data-stu-id="b1699-144">For example, type BOM_1.</span></span>  
7. <span data-ttu-id="b1699-145">No campo Local, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="b1699-145">In the Site field, enter or select a value.</span></span>
    * <span data-ttu-id="b1699-146">Neste exemplo, insira ou selecione Site 1.</span><span class="sxs-lookup"><span data-stu-id="b1699-146">For this example, enter or select Site 1.</span></span>  
8. <span data-ttu-id="b1699-147">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="b1699-147">Click OK.</span></span>
9. <span data-ttu-id="b1699-148">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="b1699-148">Click New.</span></span>
10. <span data-ttu-id="b1699-149">No campo Número de item, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="b1699-149">In the Item number field, type a value.</span></span>
    * <span data-ttu-id="b1699-150">Neste exemplo, digite ITEM_A.</span><span class="sxs-lookup"><span data-stu-id="b1699-150">For this example, type ITEM_A.</span></span>  
11. <span data-ttu-id="b1699-151">No campo Depósito, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="b1699-151">In the Warehouse field, enter or select a value.</span></span>
    * <span data-ttu-id="b1699-152">Neste exemplo, selecione 11.</span><span class="sxs-lookup"><span data-stu-id="b1699-152">For this example, select 11.</span></span>  
12. <span data-ttu-id="b1699-153">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="b1699-153">Click New.</span></span>
13. <span data-ttu-id="b1699-154">No campo Número de item, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="b1699-154">In the Item number field, type a value.</span></span>
    * <span data-ttu-id="b1699-155">Neste exemplo, digite ITEM_B.</span><span class="sxs-lookup"><span data-stu-id="b1699-155">For this example, type ITEM_B.</span></span>  
14. <span data-ttu-id="b1699-156">No campo Depósito, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="b1699-156">In the Warehouse field, enter or select a value.</span></span>
    * <span data-ttu-id="b1699-157">Neste exemplo, insira ou selecione 11.</span><span class="sxs-lookup"><span data-stu-id="b1699-157">For this example, enter or select 11.</span></span>  
15. <span data-ttu-id="b1699-158">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="b1699-158">Click New.</span></span>
16. <span data-ttu-id="b1699-159">No campo Número de item, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="b1699-159">In the Item number field, type a value.</span></span>
    * <span data-ttu-id="b1699-160">Neste exemplo, digite BOM_2.</span><span class="sxs-lookup"><span data-stu-id="b1699-160">For this example, type BOM_2.</span></span>  
17. <span data-ttu-id="b1699-161">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="b1699-161">In the list, mark the selected row.</span></span>
18. <span data-ttu-id="b1699-162">No campo Depósito, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="b1699-162">In the Warehouse field, enter or select a value.</span></span>
    * <span data-ttu-id="b1699-163">Neste exemplo, insira ou selecione depósito 11.</span><span class="sxs-lookup"><span data-stu-id="b1699-163">For this example, enter or select warehouse 11.</span></span>  
19. <span data-ttu-id="b1699-164">Clique em Cabeçalho.</span><span class="sxs-lookup"><span data-stu-id="b1699-164">Click Header.</span></span>
20. <span data-ttu-id="b1699-165">Clique em Aprovação para aprovar listas de materiais.</span><span class="sxs-lookup"><span data-stu-id="b1699-165">Click Approval to approve bills of materials.</span></span>
21. <span data-ttu-id="b1699-166">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="b1699-166">Click OK.</span></span>
22. <span data-ttu-id="b1699-167">Clique em Aprovar.</span><span class="sxs-lookup"><span data-stu-id="b1699-167">Click Approve.</span></span>
    * <span data-ttu-id="b1699-168">O botão Aprovar está na Barra de Ferramentas na seção Versões de BOM.</span><span class="sxs-lookup"><span data-stu-id="b1699-168">The Approve button is on the ToolBar in the  BOM versions section.</span></span> <span data-ttu-id="b1699-169">Se ele estiver invisível, clique em Cabeçalho no canto superior direito da página Listas de materiais para exibir Aprovar.</span><span class="sxs-lookup"><span data-stu-id="b1699-169">If it is invisible, click Header at the upper right of the Bills of materials page to display Approve.</span></span>  
23. <span data-ttu-id="b1699-170">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="b1699-170">Click OK.</span></span>
24. <span data-ttu-id="b1699-171">Clique em Ativar.</span><span class="sxs-lookup"><span data-stu-id="b1699-171">Click Activate.</span></span>
25. <span data-ttu-id="b1699-172">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="b1699-172">Close the page.</span></span>
26. <span data-ttu-id="b1699-173">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="b1699-173">Close the page.</span></span>
27. <span data-ttu-id="b1699-174">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="b1699-174">Close the page.</span></span>

