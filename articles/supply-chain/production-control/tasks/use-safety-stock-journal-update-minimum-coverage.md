--- 
title: "Usar o diário de estoque de segurança para atualizar a cobertura mínima"
description: "Este procedimento mostra como calcular propostas de cobertura mínima baseadas em transações históricas e, em seguida, atualizar a cobertura do item com as propostas."
author: ChristianRytt
manager: AnnBe
ms.date: 10/27/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 1d98cbff30620256c9d13e7b4a90314db150e33e
ms.openlocfilehash: 4abd9bb6513164f11246a3a6b47beec5cd388e11
ms.contentlocale: pt-br
ms.lasthandoff: 08/07/2018

---
# <a name="use-the-safety-stock-journal-to-update-minimum-coverage"></a><span data-ttu-id="b736d-103">Usar o diário de estoque de segurança para atualizar a cobertura mínima</span><span class="sxs-lookup"><span data-stu-id="b736d-103">Use the safety stock journal to update minimum coverage</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="b736d-104">Este procedimento mostra como calcular propostas de cobertura mínima baseadas em transações históricas e, em seguida, atualizar a cobertura do item com as propostas.</span><span class="sxs-lookup"><span data-stu-id="b736d-104">This procedure shows how to calculate minimum coverage proposals based on historical transactions and then update the item coverage with the proposals.</span></span> <span data-ttu-id="b736d-105">Isso é feito usando o diário de estoque de segurança.</span><span class="sxs-lookup"><span data-stu-id="b736d-105">This is done using the safety stock journal.</span></span> <span data-ttu-id="b736d-106">A empresa de dados demo usada para criar esta tarefa é USMF.</span><span class="sxs-lookup"><span data-stu-id="b736d-106">The demo data company used to create this task is USMF.</span></span> <span data-ttu-id="b736d-107">Essa tarefa é pretendida para o planejador da produção, para ajudar a manter a cobertura mínima.</span><span class="sxs-lookup"><span data-stu-id="b736d-107">This task is intended for the production planner, to help maintain minimum coverage.</span></span>


## <a name="create-a-new-safety-stock-journal-name"></a><span data-ttu-id="b736d-108">Crie um novo nome de diário de estoque seguro</span><span class="sxs-lookup"><span data-stu-id="b736d-108">Create a new safety stock journal name</span></span>
1. <span data-ttu-id="b736d-109">Vá para Nomes do diário de estoque de segurança.</span><span class="sxs-lookup"><span data-stu-id="b736d-109">Go to Safety stock journal names.</span></span>
2. <span data-ttu-id="b736d-110">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="b736d-110">Click New.</span></span>
3. <span data-ttu-id="b736d-111">No campo Nome, digite "Material".</span><span class="sxs-lookup"><span data-stu-id="b736d-111">In the Name field, type 'Material'.</span></span>
4. <span data-ttu-id="b736d-112">No campo Descrição, digite "Material".</span><span class="sxs-lookup"><span data-stu-id="b736d-112">In the Description field, type 'Material'.</span></span>
5. <span data-ttu-id="b736d-113">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="b736d-113">Close the page.</span></span>

## <a name="create-a-safety-stock-journal"></a><span data-ttu-id="b736d-114">Criar um diário de estoque de segurança</span><span class="sxs-lookup"><span data-stu-id="b736d-114">Create a safety stock journal</span></span>
1. <span data-ttu-id="b736d-115">Vá para Cálculo de estoque de segurança.</span><span class="sxs-lookup"><span data-stu-id="b736d-115">Go to Safety stock calculation.</span></span>
2. <span data-ttu-id="b736d-116">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="b736d-116">Click New.</span></span>
3. <span data-ttu-id="b736d-117">No campo Nome, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="b736d-117">In the Name field, enter or select a value.</span></span>
    * <span data-ttu-id="b736d-118">Selecione o nome do diário de estoque de segurança que você criou, por exemplo, Material.</span><span class="sxs-lookup"><span data-stu-id="b736d-118">Select the safety stock journal name that you created, for example, Material.</span></span>  
4. <span data-ttu-id="b736d-119">Clique em Criar linhas.</span><span class="sxs-lookup"><span data-stu-id="b736d-119">Click Create lines.</span></span>
5. <span data-ttu-id="b736d-120">No campo De data, insira uma data.</span><span class="sxs-lookup"><span data-stu-id="b736d-120">In the From date field, enter a date.</span></span>
    * <span data-ttu-id="b736d-121">Defina a data para '2015-01-02'.</span><span class="sxs-lookup"><span data-stu-id="b736d-121">Set the date to '2015-01-02'.</span></span>  
6. <span data-ttu-id="b736d-122">No campo Para data, insira uma data.</span><span class="sxs-lookup"><span data-stu-id="b736d-122">In the To date field, enter a date.</span></span>
    * <span data-ttu-id="b736d-123">Defina a data para '2015-12-30'.</span><span class="sxs-lookup"><span data-stu-id="b736d-123">Set the date to '2015-12-30'.</span></span>  
7. <span data-ttu-id="b736d-124">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="b736d-124">Click OK.</span></span>
    * <span data-ttu-id="b736d-125">Isso criará linhas para as dimensões que têm transações de estoque.</span><span class="sxs-lookup"><span data-stu-id="b736d-125">This will create lines for the dimensions that have inventory transactions.</span></span>  

## <a name="calculate-proposal"></a><span data-ttu-id="b736d-126">Calcular proposta</span><span class="sxs-lookup"><span data-stu-id="b736d-126">Calculate proposal</span></span>
1. <span data-ttu-id="b736d-127">Clique em Calcular proposta.</span><span class="sxs-lookup"><span data-stu-id="b736d-127">Click Calculate proposal.</span></span>
2. <span data-ttu-id="b736d-128">Selecione a opção Usar média de saídas durante o prazo de entrega.</span><span class="sxs-lookup"><span data-stu-id="b736d-128">Select the Use average issue during lead time option.</span></span>
3. <span data-ttu-id="b736d-129">Defina o fator de multiplicação como "10".</span><span class="sxs-lookup"><span data-stu-id="b736d-129">Set Multiplication factor to '10'.</span></span>
    * <span data-ttu-id="b736d-130">O fator da multiplicação é usado para ajustar a proposta.</span><span class="sxs-lookup"><span data-stu-id="b736d-130">The Multiply factor is used to adjust the proposal.</span></span> <span data-ttu-id="b736d-131">Como os dados de demonstração têm somente algumas transações, você precisará definir o fator para obter uma proposta realística.</span><span class="sxs-lookup"><span data-stu-id="b736d-131">Because demo data only has a few transactions, you will need to set the factor to get a realistic proposal.</span></span>  
4. <span data-ttu-id="b736d-132">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="b736d-132">Click OK.</span></span>
    * <span data-ttu-id="b736d-133">Role para baixo para encontrar M0002 e M0003.</span><span class="sxs-lookup"><span data-stu-id="b736d-133">Scroll down to find M0002 and M0003.</span></span> <span data-ttu-id="b736d-134">Veja a coluna Quantidade mínima calculada.</span><span class="sxs-lookup"><span data-stu-id="b736d-134">View the Calculated minimum quantity column.</span></span>   

## <a name="update-minimum-quantity"></a><span data-ttu-id="b736d-135">Atualizar quantidade mínima</span><span class="sxs-lookup"><span data-stu-id="b736d-135">Update minimum quantity</span></span>
1. <span data-ttu-id="b736d-136">No campo Nova quantidade mínima, insira um número.</span><span class="sxs-lookup"><span data-stu-id="b736d-136">In the New minimum quantity field, enter a number.</span></span>
    * <span data-ttu-id="b736d-137">Atualize a Nova quantidade mínima para corresponder ao valor na Quantidade mínima calculada.</span><span class="sxs-lookup"><span data-stu-id="b736d-137">Update the New minimum quantity to match the value in the Calculated minimum quantity.</span></span> <span data-ttu-id="b736d-138">Se o mínimo calculado for zero, você poderá inserir o valor futuro desejado.</span><span class="sxs-lookup"><span data-stu-id="b736d-138">If the Calculated minimum is zero,  you can enter the desired future value.</span></span> <span data-ttu-id="b736d-139">Por exemplo, você pode inserir a Quantidade mínima calculada neste campo para o M0002 que tem o armazém 12.</span><span class="sxs-lookup"><span data-stu-id="b736d-139">For example, you can enter the Calculated minimum quantity in this field for M0002 that has warehouse 12.</span></span>  
2. <span data-ttu-id="b736d-140">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="b736d-140">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="b736d-141">Por exemplo, você pode selecionar o M0002 que tem o armazém 12.</span><span class="sxs-lookup"><span data-stu-id="b736d-141">For example, you can select M0002 that has warehouse 12.</span></span>  
3. <span data-ttu-id="b736d-142">No campo Nova quantidade mínima, insira um número.</span><span class="sxs-lookup"><span data-stu-id="b736d-142">In the New minimum quantity field, enter a number.</span></span>
    * <span data-ttu-id="b736d-143">Atualize a Nova quantidade mínima para corresponder ao valor na Quantidade mínima calculada.</span><span class="sxs-lookup"><span data-stu-id="b736d-143">Update the New minimum quantity to match the value in the Calculated minimum quantity.</span></span> <span data-ttu-id="b736d-144">Se o mínimo calculado for zero, você poderá inserir o valor futuro desejado.</span><span class="sxs-lookup"><span data-stu-id="b736d-144">If the Calculated minimum is zero you can enter the desired future value.</span></span>  

## <a name="post-the-new-minimum-quantity-and-validate-the-result"></a><span data-ttu-id="b736d-145">Lançar a nova quantidade mínima e validar o resultado</span><span class="sxs-lookup"><span data-stu-id="b736d-145">Post the new minimum quantity and validate the result</span></span>
1. <span data-ttu-id="b736d-146">Clique em Lançar.</span><span class="sxs-lookup"><span data-stu-id="b736d-146">Click Post.</span></span>
2. <span data-ttu-id="b736d-147">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="b736d-147">Click OK.</span></span>
3. <span data-ttu-id="b736d-148">Clique para seguir o link no campo Número de item.</span><span class="sxs-lookup"><span data-stu-id="b736d-148">Click to follow the link in the Item number field.</span></span>
4. <span data-ttu-id="b736d-149">Clique para seguir o link no campo Número de item.</span><span class="sxs-lookup"><span data-stu-id="b736d-149">Click to follow the link in the Item number field.</span></span>
5. <span data-ttu-id="b736d-150">No Painel de Ação, clique em Plano.</span><span class="sxs-lookup"><span data-stu-id="b736d-150">On the Action Pane, click Plan.</span></span>
6. <span data-ttu-id="b736d-151">Clique em Cobertura de item.</span><span class="sxs-lookup"><span data-stu-id="b736d-151">Click Item coverage.</span></span>
    * <span data-ttu-id="b736d-152">Observe que a Quantidade mínima foi atualizada com a nova quantidade mínima do diário de estoque de segurança.</span><span class="sxs-lookup"><span data-stu-id="b736d-152">Notice that the Minimum quantity has been updated with the new minimum quantity from the safety stock journal.</span></span>  


