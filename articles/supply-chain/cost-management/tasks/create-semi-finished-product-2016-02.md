--- 
title: Criar um produto semi-acabado (apenas fevereiro de 2016)
description: Esta tarefa tem como foco criar um produto semifinalizado.
author: ShylaThompson
manager: AnnBe
ms.date: 02/07/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 1d98cbff30620256c9d13e7b4a90314db150e33e
ms.openlocfilehash: 76fcba3732879f85c9bf0faa6d2481b9c5313a17
ms.contentlocale: pt-br
ms.lasthandoff: 08/07/2018

---
# <a name="create-a-semi-finished-product-february-2016-only"></a><span data-ttu-id="2c9c4-103">Criar um produto semi-acabado (apenas fevereiro de 2016)</span><span class="sxs-lookup"><span data-stu-id="2c9c4-103">Create a semi-finished product (February 2016 only)</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="2c9c4-104">Esta tarefa tem como foco criar um produto semifinalizado.</span><span class="sxs-lookup"><span data-stu-id="2c9c4-104">This task focuses on creating a semi-finished product.</span></span> <span data-ttu-id="2c9c4-105">Trata-se da segunda tarefa na série de cálculo BOM.</span><span class="sxs-lookup"><span data-stu-id="2c9c4-105">It is the second task in the BOM calculation series.</span></span> <span data-ttu-id="2c9c4-106">A empresa de dados demo usada para criar esta tarefa é USMF.</span><span class="sxs-lookup"><span data-stu-id="2c9c4-106">The demo data company used to create this task is USMF.</span></span>

1. <span data-ttu-id="2c9c4-107">Vá para Gerenciamento de informações do produto > Produtos > Produtos liberados.</span><span class="sxs-lookup"><span data-stu-id="2c9c4-107">Go to Product information management > Products > Released products.</span></span>
2. <span data-ttu-id="2c9c4-108">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="2c9c4-108">Click New.</span></span>
3. <span data-ttu-id="2c9c4-109">No campo Número do produto, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="2c9c4-109">In the Product number field, type a value.</span></span>
    * <span data-ttu-id="2c9c4-110">Neste exemplo, digite BOM_2.</span><span class="sxs-lookup"><span data-stu-id="2c9c4-110">For this example, type BOM_2.</span></span>  
4. <span data-ttu-id="2c9c4-111">No campo Grupo de modelos do item, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="2c9c4-111">In the Item model group field, enter or select a value.</span></span>
    * <span data-ttu-id="2c9c4-112">Selecione STD.</span><span class="sxs-lookup"><span data-stu-id="2c9c4-112">Select STD.</span></span> <span data-ttu-id="2c9c4-113">STD significa "custo padrão" e é o modelo mais comumente utilizado ao se trabalhar com cálculos de custo.</span><span class="sxs-lookup"><span data-stu-id="2c9c4-113">STD stands for standard cost and is the most commonly used model when working with cost calculations.</span></span>  
5. <span data-ttu-id="2c9c4-114">No campo Grupo de itens, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="2c9c4-114">In the Item group field, enter or select a value.</span></span>
    * <span data-ttu-id="2c9c4-115">Por exemplo, selecione Áudio.</span><span class="sxs-lookup"><span data-stu-id="2c9c4-115">For example, select Audio.</span></span> <span data-ttu-id="2c9c4-116">Isso não tem impacto sobre os cálculos de custo.</span><span class="sxs-lookup"><span data-stu-id="2c9c4-116">This has no impact on cost calculations.</span></span>  
6. <span data-ttu-id="2c9c4-117">No campo Grupo de dimensões de armazenamento, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="2c9c4-117">In the Storage dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="2c9c4-118">Selecione SiteWH.</span><span class="sxs-lookup"><span data-stu-id="2c9c4-118">Select SiteWH.</span></span> <span data-ttu-id="2c9c4-119">Apenas Site e Depósito serão usados neste exemplo.</span><span class="sxs-lookup"><span data-stu-id="2c9c4-119">Only Site and Warehouse will be used for this example.</span></span>  
7. <span data-ttu-id="2c9c4-120">No campo Grupo de dimensões de rastreamento, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="2c9c4-120">In the Tracking dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="2c9c4-121">A dimensão de rastreamento não será usada neste exemplo. Selecione Nenhuma.</span><span class="sxs-lookup"><span data-stu-id="2c9c4-121">Tracking dimensions will not be used for this example, select None.</span></span>  
8. <span data-ttu-id="2c9c4-122">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="2c9c4-122">Click OK.</span></span>
9. <span data-ttu-id="2c9c4-123">No Painel de Ação, clique em Gerenciar estoque.</span><span class="sxs-lookup"><span data-stu-id="2c9c4-123">On the Action Pane, click Manage inventory.</span></span>
10. <span data-ttu-id="2c9c4-124">Clique em Configurações de ordem padrão.</span><span class="sxs-lookup"><span data-stu-id="2c9c4-124">Click Default order settings.</span></span>
11. <span data-ttu-id="2c9c4-125">No campo Tipo de ordem padrão, selecione "Produção".</span><span class="sxs-lookup"><span data-stu-id="2c9c4-125">In the Default order type field, select 'Production'.</span></span>
    * <span data-ttu-id="2c9c4-126">Como se trata de um produto semifinalizado que será produzido, selecione Produção.</span><span class="sxs-lookup"><span data-stu-id="2c9c4-126">Because this is a semi-finished product that will be produced, select Production.</span></span>  
12. <span data-ttu-id="2c9c4-127">No campo Site de compra, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="2c9c4-127">In the Purchase site field, enter or select a value.</span></span>
    * <span data-ttu-id="2c9c4-128">Neste exemplo, selecione Site 1.</span><span class="sxs-lookup"><span data-stu-id="2c9c4-128">For this example, select Site 1.</span></span>  
13. <span data-ttu-id="2c9c4-129">No campo Site de estoque, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="2c9c4-129">In the Inventory site field, enter or select a value.</span></span>
    * <span data-ttu-id="2c9c4-130">Neste exemplo, selecione Site 1.</span><span class="sxs-lookup"><span data-stu-id="2c9c4-130">For this example, select Site 1.</span></span>  
14. <span data-ttu-id="2c9c4-131">No campo Site de vendas, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="2c9c4-131">In the Sales site field, enter or select a value.</span></span>
    * <span data-ttu-id="2c9c4-132">Neste exemplo, selecione Site 1.</span><span class="sxs-lookup"><span data-stu-id="2c9c4-132">For this example, select Site 1.</span></span>  
15. <span data-ttu-id="2c9c4-133">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="2c9c4-133">Close the page.</span></span>
16. <span data-ttu-id="2c9c4-134">No Painel de Ação, clique em Gerenciar custos.</span><span class="sxs-lookup"><span data-stu-id="2c9c4-134">On the Action Pane, click Manage costs.</span></span>
17. <span data-ttu-id="2c9c4-135">Clique em Preço de item.</span><span class="sxs-lookup"><span data-stu-id="2c9c4-135">Click Item price.</span></span>
18. <span data-ttu-id="2c9c4-136">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="2c9c4-136">Click New.</span></span>
19. <span data-ttu-id="2c9c4-137">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="2c9c4-137">In the list, mark the selected row.</span></span>
20. <span data-ttu-id="2c9c4-138">No campo Versão, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="2c9c4-138">In the Version field, enter or select a value.</span></span>
    * <span data-ttu-id="2c9c4-139">Neste exemplo, selecione Versão 10.</span><span class="sxs-lookup"><span data-stu-id="2c9c4-139">For this example, select Version 10.</span></span>  
21. <span data-ttu-id="2c9c4-140">No campo Local, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="2c9c4-140">In the Site field, enter or select a value.</span></span>
    * <span data-ttu-id="2c9c4-141">Neste exemplo, selecione Site 1.</span><span class="sxs-lookup"><span data-stu-id="2c9c4-141">For this example, select Site 1.</span></span>  
22. <span data-ttu-id="2c9c4-142">Defina o preço como "10".</span><span class="sxs-lookup"><span data-stu-id="2c9c4-142">Set Price to '10'.</span></span>
    * <span data-ttu-id="2c9c4-143">Neste exemplo, digite um preço de custo de 10.</span><span class="sxs-lookup"><span data-stu-id="2c9c4-143">For this example, type a cost price of 10.</span></span>  
23. <span data-ttu-id="2c9c4-144">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="2c9c4-144">Click Save.</span></span>
24. <span data-ttu-id="2c9c4-145">Clique em Ativar preço(s) pendente(s).</span><span class="sxs-lookup"><span data-stu-id="2c9c4-145">Click Activate pending price(s).</span></span>
25. <span data-ttu-id="2c9c4-146">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="2c9c4-146">Close the page.</span></span>
26. <span data-ttu-id="2c9c4-147">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="2c9c4-147">Close the page.</span></span>
27. <span data-ttu-id="2c9c4-148">Clique em BOM_2 para abri-lo.</span><span class="sxs-lookup"><span data-stu-id="2c9c4-148">Click BOM_2 to open it.</span></span>
28. <span data-ttu-id="2c9c4-149">Expanda a seção Gerenciar custos.</span><span class="sxs-lookup"><span data-stu-id="2c9c4-149">Expand the Manage costs section.</span></span>
29. <span data-ttu-id="2c9c4-150">No campo Grupo de custos, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="2c9c4-150">In the Cost group field, enter or select a value.</span></span>
    * <span data-ttu-id="2c9c4-151">Neste exemplo, selecione Grupo de custos M1.</span><span class="sxs-lookup"><span data-stu-id="2c9c4-151">For this example, select Cost group M1.</span></span>  
30. <span data-ttu-id="2c9c4-152">Use o atalho para salvar um registro.</span><span class="sxs-lookup"><span data-stu-id="2c9c4-152">Use the shortcut for saving a record.</span></span>
31. <span data-ttu-id="2c9c4-153">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="2c9c4-153">Close the page.</span></span>


