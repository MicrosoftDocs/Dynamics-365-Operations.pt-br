--- 
title: "Criar uma lista de materiais para um produto mestre baseado na dimensão"
description: "Para esse procedimento é necessário ter concluído as 4 guias anteriores nesta sequência de oito registros."
author: ShylaThompson
manager: AnnBe
ms.date: 8/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: DefaultDashboard, EcoResProductMaintainWorkspace, EcoResProductOpenCasesFormPart, EcoResProductDetailsExtended, BOMConsistOf, BOMTable, InventItemIdLookupSimple, HcmWorkerLookUp
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 32d71167fdad65cb1dec37671999a497759ca484
ms.openlocfilehash: 9269ab216add42a3bf53d832de4da5eac3b8cf9c
ms.contentlocale: pt-br
ms.lasthandoff: 09/11/2018

---
# <a name="create-a-bill-of-materials-for-a-dimension-based-product-master"></a><span data-ttu-id="51f5b-103">Criar uma lista de materiais para um produto mestre baseado na dimensão</span><span class="sxs-lookup"><span data-stu-id="51f5b-103">Create a bill of materials for a dimension-based product master</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="51f5b-104">Para esse procedimento é necessário ter concluído as 4 guias anteriores nesta sequência de oito registros.</span><span class="sxs-lookup"><span data-stu-id="51f5b-104">For this procedure you should have completed the previous 4 guides in this sequence of eight recordings.</span></span> <span data-ttu-id="51f5b-105">Os primeiras 4 registros configuram os dados necessários para concluir este procedimento.</span><span class="sxs-lookup"><span data-stu-id="51f5b-105">The first 4 recordings set up data that is required to complete this procedure.</span></span> <span data-ttu-id="51f5b-106">A empresa de dados demo usada para criar este procedimento é USMF.</span><span class="sxs-lookup"><span data-stu-id="51f5b-106">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="51f5b-107">Esta tarefa é tratada normalmente pelo designer do produto.</span><span class="sxs-lookup"><span data-stu-id="51f5b-107">This task is typically handled by the product designer.</span></span>


## <a name="select-the-product"></a><span data-ttu-id="51f5b-108">Selecionar o produto</span><span class="sxs-lookup"><span data-stu-id="51f5b-108">Select the product</span></span>
1. <span data-ttu-id="51f5b-109">Clique em Manutenção de produto liberado.</span><span class="sxs-lookup"><span data-stu-id="51f5b-109">Click Released product maintenance.</span></span>
2. <span data-ttu-id="51f5b-110">Clique em Produtos liberados.</span><span class="sxs-lookup"><span data-stu-id="51f5b-110">Click Released products.</span></span>
3. <span data-ttu-id="51f5b-111">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="51f5b-111">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="51f5b-112">Localize o produto mestre liberado com tecnologia de configuração baseada em dimensão que você criou no primeiro guia de tarefa nesta sequência.</span><span class="sxs-lookup"><span data-stu-id="51f5b-112">Find the released product master with dimension-based configuration technology that you created in the first task guide in this sequence.</span></span>  
4. <span data-ttu-id="51f5b-113">No Painel de Ação, clique em Engenharia.</span><span class="sxs-lookup"><span data-stu-id="51f5b-113">On the Action Pane, click Engineer.</span></span>
5. <span data-ttu-id="51f5b-114">Clique em Versões BOM.</span><span class="sxs-lookup"><span data-stu-id="51f5b-114">Click BOM versions.</span></span>

## <a name="create-new-bom-and-bom-version"></a><span data-ttu-id="51f5b-115">Criar uma nova BOM e versão da BOM</span><span class="sxs-lookup"><span data-stu-id="51f5b-115">Create new BOM and BOM version</span></span>
1. <span data-ttu-id="51f5b-116">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="51f5b-116">Click New.</span></span>
2. <span data-ttu-id="51f5b-117">Clique em Nova BOM e versão da BOM.</span><span class="sxs-lookup"><span data-stu-id="51f5b-117">Click BOM and BOM version.</span></span>
3. <span data-ttu-id="51f5b-118">No campo Nome, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="51f5b-118">In the Name field, type a value.</span></span>
    * <span data-ttu-id="51f5b-119">Configurações do site</span><span class="sxs-lookup"><span data-stu-id="51f5b-119">Setting a site</span></span>  
    * <span data-ttu-id="51f5b-120">Nesse procedimento, não definimos um site específico da BOM.</span><span class="sxs-lookup"><span data-stu-id="51f5b-120">In this procedure we don't set a specific site for the BOM.</span></span>  
4. <span data-ttu-id="51f5b-121">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="51f5b-121">Click OK.</span></span>
5. <span data-ttu-id="51f5b-122">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="51f5b-122">Click New.</span></span>
    * <span data-ttu-id="51f5b-123">Nesse procedimento adicionaremos quatro linhas à BOM.</span><span class="sxs-lookup"><span data-stu-id="51f5b-123">In this procedure we will add four lines to the BOM.</span></span> <span data-ttu-id="51f5b-124">Duas linhas representam as opções de aumento e duas linhas representam as opções do gabinete.</span><span class="sxs-lookup"><span data-stu-id="51f5b-124">Two lines represent cable options and two lines represent cabinet options.</span></span>  
6. <span data-ttu-id="51f5b-125">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="51f5b-125">In the list, mark the selected row.</span></span>
7. <span data-ttu-id="51f5b-126">No campo Número do item, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="51f5b-126">In the Item number field, enter or select a value.</span></span>
    * <span data-ttu-id="51f5b-127">Selecionar número de item Cabos A0001, HDMI 6'.</span><span class="sxs-lookup"><span data-stu-id="51f5b-127">Select item number A0001, HDMI 6' Cables.</span></span>  
8. <span data-ttu-id="51f5b-128">No campo Grupo de configuração, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="51f5b-128">In the Configuration group field, enter or select a value.</span></span>
    * <span data-ttu-id="51f5b-129">Selecione o Grupo de configuração de cabo criado na guia 4 nesta sequência.</span><span class="sxs-lookup"><span data-stu-id="51f5b-129">Select the Cable configuration group created in guide 4 in this sequence.</span></span>  
9. <span data-ttu-id="51f5b-130">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="51f5b-130">Click New.</span></span>
    * <span data-ttu-id="51f5b-131">Selecionar número de item Cabos A0002, HDMI 12'.</span><span class="sxs-lookup"><span data-stu-id="51f5b-131">Select item number A0002, HDMI 12' Cables.</span></span>  
10. <span data-ttu-id="51f5b-132">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="51f5b-132">In the list, mark the selected row.</span></span>
11. <span data-ttu-id="51f5b-133">No campo Número do item, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="51f5b-133">In the Item number field, enter or select a value.</span></span>
12. <span data-ttu-id="51f5b-134">No campo Grupo de configuração, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="51f5b-134">In the Configuration group field, enter or select a value.</span></span>
    * <span data-ttu-id="51f5b-135">Selecione o grupo de configurações do cabo novamente.</span><span class="sxs-lookup"><span data-stu-id="51f5b-135">Select the Cable configuration group again.</span></span>  
13. <span data-ttu-id="51f5b-136">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="51f5b-136">Click New.</span></span>
14. <span data-ttu-id="51f5b-137">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="51f5b-137">In the list, mark the selected row.</span></span>
15. <span data-ttu-id="51f5b-138">No campo Número do item, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="51f5b-138">In the Item number field, enter or select a value.</span></span>
    * <span data-ttu-id="51f5b-139">Selecionar número de item Gabinete D0002.</span><span class="sxs-lookup"><span data-stu-id="51f5b-139">Select item number D0002 Cabinet.</span></span>  
16. <span data-ttu-id="51f5b-140">No campo Grupo de configuração, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="51f5b-140">In the Configuration group field, enter or select a value.</span></span>
    * <span data-ttu-id="51f5b-141">Selecione o grupo de configuração do gabinete para esta linha BOM.</span><span class="sxs-lookup"><span data-stu-id="51f5b-141">Select the Cabinet configuration group for this BOM line.</span></span>  
17. <span data-ttu-id="51f5b-142">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="51f5b-142">Click New.</span></span>
18. <span data-ttu-id="51f5b-143">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="51f5b-143">In the list, mark the selected row.</span></span>
19. <span data-ttu-id="51f5b-144">No campo Número do item, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="51f5b-144">In the Item number field, enter or select a value.</span></span>
    * <span data-ttu-id="51f5b-145">Selecione o número do item M0007 StandardCabinet como a linha BOM da última vez.</span><span class="sxs-lookup"><span data-stu-id="51f5b-145">Select Item number M0007 StandardCabinet as the last BOM line.</span></span>  
20. <span data-ttu-id="51f5b-146">No campo Grupo de configuração, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="51f5b-146">In the Configuration group field, enter or select a value.</span></span>
    * <span data-ttu-id="51f5b-147">Selecione o grupo de configuração do gabinete para esta última linha BOM.</span><span class="sxs-lookup"><span data-stu-id="51f5b-147">Select the Cabinet configuration group for the laste BOM line.</span></span>  

## <a name="approve-and-activate"></a><span data-ttu-id="51f5b-148">Aprovar e ativar</span><span class="sxs-lookup"><span data-stu-id="51f5b-148">Approve and activate</span></span>
1. <span data-ttu-id="51f5b-149">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="51f5b-149">Close the page.</span></span>
2. <span data-ttu-id="51f5b-150">Clique em Aprovar.</span><span class="sxs-lookup"><span data-stu-id="51f5b-150">Click Approve.</span></span>
3. <span data-ttu-id="51f5b-151">No campo Aprovado por, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="51f5b-151">In the Approved by field, enter or select a value.</span></span>
4. <span data-ttu-id="51f5b-152">Selecione Sim em Também deseja aprovar a lista de materiais? .</span><span class="sxs-lookup"><span data-stu-id="51f5b-152">Select Yes in the Do you also want to approve the bill of materials? field.</span></span>
5. <span data-ttu-id="51f5b-153">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="51f5b-153">Click OK.</span></span>
6. <span data-ttu-id="51f5b-154">Clique em Ativar.</span><span class="sxs-lookup"><span data-stu-id="51f5b-154">Click Activate.</span></span>


