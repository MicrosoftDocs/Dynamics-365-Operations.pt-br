---
title: Configurar grades de remuneração
description: As grades de remuneração são usadas para definir e manter as estruturas de pagamento para os planos de remuneração fixa.
author: andreabichsel
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: HRCCompGrid, HRCCompGridView, HcmCompensationWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 5d5ada0817dd73caad38bb2e50302869857c71d8
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4417268"
---
# <a name="set-up-compensation-grids"></a><span data-ttu-id="dbe7f-103">Configurar grades de remuneração</span><span class="sxs-lookup"><span data-stu-id="dbe7f-103">Set up compensation grids</span></span>

<span data-ttu-id="dbe7f-104">As grades de remuneração são usadas para definir e manter as estruturas de pagamento para os planos de remuneração fixa.</span><span class="sxs-lookup"><span data-stu-id="dbe7f-104">Compensation grids are used to define and maintain the pay structures for fixed compensation plans.</span></span> <span data-ttu-id="dbe7f-105">As grades de remuneração poderão ser compartilhadas entre vários planos ou copiadas ao criar um novo plano de remuneração.</span><span class="sxs-lookup"><span data-stu-id="dbe7f-105">Compensation grids can be shared between multiple plans or copied when creating a new compensation plan.</span></span>  <span data-ttu-id="dbe7f-106">Antes de criar uma grade de compensação, os níveis do pontos de Referência devem ser configurados.</span><span class="sxs-lookup"><span data-stu-id="dbe7f-106">Before creating a compensation grid, Levels and Reference points must be set up.</span></span> <span data-ttu-id="dbe7f-107">Este exemplo criará um novo tipo de Classificação da grade de remuneração com dados de demonstração para os níveis e os pontos de Referência.</span><span class="sxs-lookup"><span data-stu-id="dbe7f-107">This example will create a new Grade type of compensation grid using demo data for the Levels and Reference points.</span></span> <span data-ttu-id="dbe7f-108">A empresa de dados demo usada para criar este procedimento é USMF.</span><span class="sxs-lookup"><span data-stu-id="dbe7f-108">The demo data company used to create this procedure is USMF.</span></span>


## <a name="set-up-information-about-the-compensation-grid"></a><span data-ttu-id="dbe7f-109">Configurar informações sobre a grade de remuneração</span><span class="sxs-lookup"><span data-stu-id="dbe7f-109">Set up information about the compensation grid</span></span>
1. <span data-ttu-id="dbe7f-110">Vá para Recursos humanos > Remuneração > Remuneração > Grades de remuneração.</span><span class="sxs-lookup"><span data-stu-id="dbe7f-110">Go to Human resources > Compensation > Fixed compensation > Compensation grids.</span></span>
2. <span data-ttu-id="dbe7f-111">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="dbe7f-111">Click New.</span></span>
3. <span data-ttu-id="dbe7f-112">No campo Grade, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="dbe7f-112">In the Grid field, type a value.</span></span>
4. <span data-ttu-id="dbe7f-113">No campo Descrição, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="dbe7f-113">In the Description field, type a value.</span></span>
5. <span data-ttu-id="dbe7f-114">No campo Tipo, selecione uma opção.</span><span class="sxs-lookup"><span data-stu-id="dbe7f-114">In the Type field, select an option.</span></span>
6. <span data-ttu-id="dbe7f-115">No campo Configuração referência, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="dbe7f-115">In the Reference setup field, enter or select a value.</span></span>
7. <span data-ttu-id="dbe7f-116">No campo Moeda, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="dbe7f-116">In the Currency field, enter or select a value.</span></span>
8. <span data-ttu-id="dbe7f-117">No campo Moeda, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="dbe7f-117">In the Currency field, type a value.</span></span>
9. <span data-ttu-id="dbe7f-118">No campo Data efetiva, insira uma data.</span><span class="sxs-lookup"><span data-stu-id="dbe7f-118">In the Effective date field, enter a date.</span></span>

## <a name="add-levels-to-the-compensation-structure"></a><span data-ttu-id="dbe7f-119">Adicionar níveis à estrutura de remuneração</span><span class="sxs-lookup"><span data-stu-id="dbe7f-119">Add levels to the compensation structure</span></span>
1. <span data-ttu-id="dbe7f-120">Clique em Estrutura de remuneração.</span><span class="sxs-lookup"><span data-stu-id="dbe7f-120">Click Compensation structure.</span></span>
2. <span data-ttu-id="dbe7f-121">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="dbe7f-121">In the list, mark the selected row.</span></span>
3. <span data-ttu-id="dbe7f-122">No campo Nível, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="dbe7f-122">In the Level field, enter or select a value.</span></span>
4. <span data-ttu-id="dbe7f-123">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="dbe7f-123">Click New.</span></span>
5. <span data-ttu-id="dbe7f-124">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="dbe7f-124">In the list, mark the selected row.</span></span>
6. <span data-ttu-id="dbe7f-125">No campo Nível, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="dbe7f-125">In the Level field, enter or select a value.</span></span>
7. <span data-ttu-id="dbe7f-126">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="dbe7f-126">Click New.</span></span>
8. <span data-ttu-id="dbe7f-127">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="dbe7f-127">In the list, mark the selected row.</span></span>
9. <span data-ttu-id="dbe7f-128">No campo Nível, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="dbe7f-128">In the Level field, enter or select a value.</span></span>
10. <span data-ttu-id="dbe7f-129">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="dbe7f-129">Click New.</span></span>
11. <span data-ttu-id="dbe7f-130">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="dbe7f-130">In the list, mark the selected row.</span></span>
12. <span data-ttu-id="dbe7f-131">No campo Nível, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="dbe7f-131">In the Level field, enter or select a value.</span></span>
13. <span data-ttu-id="dbe7f-132">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="dbe7f-132">Click New.</span></span>
14. <span data-ttu-id="dbe7f-133">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="dbe7f-133">In the list, mark the selected row.</span></span>
15. <span data-ttu-id="dbe7f-134">No campo Nível, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="dbe7f-134">In the Level field, enter or select a value.</span></span>

## <a name="fill-in-the-compensation-structure-with-values"></a><span data-ttu-id="dbe7f-135">Preencha a estrutura de remuneração com valores</span><span class="sxs-lookup"><span data-stu-id="dbe7f-135">Fill in the compensation structure with values</span></span>
1. <span data-ttu-id="dbe7f-136">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="dbe7f-136">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="dbe7f-137">Nesse ponto, os valores de remuneração poderão ser inseridos manualmente em todos os campos na tabela, ou a funcionalidade Alteração em massa poderá ser usada para preencher facilmente vários campos e para executar cálculos básicos.</span><span class="sxs-lookup"><span data-stu-id="dbe7f-137">At this point, compensation values can manually be entered into each field in the table, or the Mass change functionality can be used to easily fill in multiple fields and perform basic calculations.</span></span>  
2. <span data-ttu-id="dbe7f-138">Clique em Alteração em massa.</span><span class="sxs-lookup"><span data-stu-id="dbe7f-138">Click Mass change.</span></span>
    * <span data-ttu-id="dbe7f-139">Para essa grade, aplicaremos primeiro o valor do ponto médio do primeiro nível a todos os campos da tabela.</span><span class="sxs-lookup"><span data-stu-id="dbe7f-139">For this grid, we'll first apply the value for the midpoint of the first level's to all the fields in the table.</span></span> <span data-ttu-id="dbe7f-140">Essa será a base para a matriz de remuneração.</span><span class="sxs-lookup"><span data-stu-id="dbe7f-140">This will be the basis for the compensation matrix.</span></span>  
3. <span data-ttu-id="dbe7f-141">No campo Tipo de Ajuste, selecione uma opção.</span><span class="sxs-lookup"><span data-stu-id="dbe7f-141">In the Adjustment type field, select an option.</span></span>
4. <span data-ttu-id="dbe7f-142">No campo Valor do ajuste, insira um número.</span><span class="sxs-lookup"><span data-stu-id="dbe7f-142">In the Adjustment amount field, enter a number.</span></span>
5. <span data-ttu-id="dbe7f-143">Na lista, marque ou desmarque todas as linhas.</span><span class="sxs-lookup"><span data-stu-id="dbe7f-143">In the list, mark or unmark all rows.</span></span>
6. <span data-ttu-id="dbe7f-144">Clique em Aplicar à grade.</span><span class="sxs-lookup"><span data-stu-id="dbe7f-144">Click Apply to grid.</span></span>
    * <span data-ttu-id="dbe7f-145">Agora usaremos a função de alteração em massa para incrementar os valores em cada nível subsequente por uma determinada porcentagem ou valor.</span><span class="sxs-lookup"><span data-stu-id="dbe7f-145">Now we'll use the mass change function to increment the amounts in each subsequent level by a certain percentage or amount.</span></span> <span data-ttu-id="dbe7f-146">Neste exemplo, cada classificação terá 12,5% difundido entre os valores médios.</span><span class="sxs-lookup"><span data-stu-id="dbe7f-146">In this example, each grade will have a 12.5% spread between their midpoints.</span></span>  
7. <span data-ttu-id="dbe7f-147">No campo Tipo de Ajuste, selecione uma opção.</span><span class="sxs-lookup"><span data-stu-id="dbe7f-147">In the Adjustment type field, select an option.</span></span>
8. <span data-ttu-id="dbe7f-148">No campo Valor do ajuste, insira um número.</span><span class="sxs-lookup"><span data-stu-id="dbe7f-148">In the Adjustment amount field, enter a number.</span></span>
9. <span data-ttu-id="dbe7f-149">Na lista, localize e selecione o registro desejado.</span><span class="sxs-lookup"><span data-stu-id="dbe7f-149">In the list, find and select the desired record.</span></span>
10. <span data-ttu-id="dbe7f-150">Na lista, localize e selecione o registro desejado.</span><span class="sxs-lookup"><span data-stu-id="dbe7f-150">In the list, find and select the desired record.</span></span>
11. <span data-ttu-id="dbe7f-151">Na lista, localize e selecione o registro desejado.</span><span class="sxs-lookup"><span data-stu-id="dbe7f-151">In the list, find and select the desired record.</span></span>
12. <span data-ttu-id="dbe7f-152">Na lista, localize e selecione o registro desejado.</span><span class="sxs-lookup"><span data-stu-id="dbe7f-152">In the list, find and select the desired record.</span></span>
13. <span data-ttu-id="dbe7f-153">Clique em Aplicar à grade.</span><span class="sxs-lookup"><span data-stu-id="dbe7f-153">Click Apply to grid.</span></span>
14. <span data-ttu-id="dbe7f-154">Na lista, localize e selecione o registro desejado.</span><span class="sxs-lookup"><span data-stu-id="dbe7f-154">In the list, find and select the desired record.</span></span>
15. <span data-ttu-id="dbe7f-155">Na lista, localize e selecione o registro desejado.</span><span class="sxs-lookup"><span data-stu-id="dbe7f-155">In the list, find and select the desired record.</span></span>
16. <span data-ttu-id="dbe7f-156">Na lista, localize e selecione o registro desejado.</span><span class="sxs-lookup"><span data-stu-id="dbe7f-156">In the list, find and select the desired record.</span></span>
17. <span data-ttu-id="dbe7f-157">Clique em Aplicar à grade.</span><span class="sxs-lookup"><span data-stu-id="dbe7f-157">Click Apply to grid.</span></span>
18. <span data-ttu-id="dbe7f-158">Na lista, localize e selecione o registro desejado.</span><span class="sxs-lookup"><span data-stu-id="dbe7f-158">In the list, find and select the desired record.</span></span>
19. <span data-ttu-id="dbe7f-159">Na lista, localize e selecione o registro desejado.</span><span class="sxs-lookup"><span data-stu-id="dbe7f-159">In the list, find and select the desired record.</span></span>
20. <span data-ttu-id="dbe7f-160">Clique em Aplicar à grade.</span><span class="sxs-lookup"><span data-stu-id="dbe7f-160">Click Apply to grid.</span></span>
21. <span data-ttu-id="dbe7f-161">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="dbe7f-161">In the list, find and select the desired record.</span></span>
22. <span data-ttu-id="dbe7f-162">Clique em Aplicar à grade.</span><span class="sxs-lookup"><span data-stu-id="dbe7f-162">Click Apply to grid.</span></span>
    * <span data-ttu-id="dbe7f-163">Agora usaremos a função de alteração em massa para ajustar os pontos de referência Mínimo e Máximo para cada nível.</span><span class="sxs-lookup"><span data-stu-id="dbe7f-163">Now we'll use the mass change function to adjust the Minimum and Maximum reference points for each level.</span></span> <span data-ttu-id="dbe7f-164">Este exemplo usará 50% difundido, dessa forma, o ponto de referência Mínimo será ajustado para -20% o Máximo será ajustado para +20%.</span><span class="sxs-lookup"><span data-stu-id="dbe7f-164">This example will use a 50% spread so the Minimum reference point will be adjusted -20% and the Maximum will be adjusted +20%.</span></span>  
23. <span data-ttu-id="dbe7f-165">No campo Valor do ajuste, insira um número.</span><span class="sxs-lookup"><span data-stu-id="dbe7f-165">In the Adjustment amount field, enter a number.</span></span>
24. <span data-ttu-id="dbe7f-166">No campo Ponto de referência, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="dbe7f-166">In the Reference point field, enter or select a value.</span></span>
25. <span data-ttu-id="dbe7f-167">Na lista, marque ou desmarque todas as linhas.</span><span class="sxs-lookup"><span data-stu-id="dbe7f-167">In the list, mark or unmark all rows.</span></span>
26. <span data-ttu-id="dbe7f-168">Clique em Aplicar à grade.</span><span class="sxs-lookup"><span data-stu-id="dbe7f-168">Click Apply to grid.</span></span>
27. <span data-ttu-id="dbe7f-169">No campo Valor do ajuste, insira um número.</span><span class="sxs-lookup"><span data-stu-id="dbe7f-169">In the Adjustment amount field, enter a number.</span></span>
28. <span data-ttu-id="dbe7f-170">No campo Ponto de referência, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="dbe7f-170">In the Reference point field, enter or select a value.</span></span>
29. <span data-ttu-id="dbe7f-171">Na lista, marque ou desmarque todas as linhas.</span><span class="sxs-lookup"><span data-stu-id="dbe7f-171">In the list, mark or unmark all rows.</span></span>
30. <span data-ttu-id="dbe7f-172">Clique em Aplicar à grade.</span><span class="sxs-lookup"><span data-stu-id="dbe7f-172">Click Apply to grid.</span></span>

