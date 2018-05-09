--- 
title: "Criar e atribuir uma política de comportamento de custos para uma unidade de controle de custos"
description: "O comportamento de custo é a classificação de custos como fixo ou variável."
author: YuyuScheller
manager: AnnBe
ms.date: 06/27/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.author: yuyus
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: c67c3711871527eada83e1dfe26522ab62828047
ms.contentlocale: pt-br
ms.lasthandoff: 05/08/2018

---
# <a name="create-and-assign-a-cost-behavior-policy-to-a-cost-control-unit"></a><span data-ttu-id="80fc2-103">Criar e atribuir uma política de comportamento de custos para uma unidade de controle de custos</span><span class="sxs-lookup"><span data-stu-id="80fc2-103">Create and assign a cost behavior policy to a cost control unit</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="80fc2-104">O comportamento de custo é a classificação de custos como fixo ou variável.</span><span class="sxs-lookup"><span data-stu-id="80fc2-104">Cost behavior is the classification of costs as either fixed or variable.</span></span> <span data-ttu-id="80fc2-105">Uma política e as regras correspondentes precisam ser atribuídas a uma unidade de controle de custo para que a política se torne efetiva.</span><span class="sxs-lookup"><span data-stu-id="80fc2-105">A policy and the corresponding rules have to be assigned to a cost control unit for the policy to become effective.</span></span> <span data-ttu-id="80fc2-106">Use esse procedimento para criar uma política e depois atribua a política a uma unidade de controle de custo.</span><span class="sxs-lookup"><span data-stu-id="80fc2-106">Use this procedure to create a policy and then assign the policy to a cost control unit.</span></span>


## <a name="create-a-cost-behavior-hierarchy"></a><span data-ttu-id="80fc2-107">Criar uma hierarquia de comportamento de custo</span><span class="sxs-lookup"><span data-stu-id="80fc2-107">Create a cost behavior hierarchy</span></span>
1. <span data-ttu-id="80fc2-108">Vá para Contabilização de custos > Dimensões > Hierarquias de dimensões.</span><span class="sxs-lookup"><span data-stu-id="80fc2-108">Go to Cost accounting > Dimensions > Dimension hierarchies.</span></span>
2. <span data-ttu-id="80fc2-109">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="80fc2-109">Click New.</span></span>
3. <span data-ttu-id="80fc2-110">Clique em Criar.</span><span class="sxs-lookup"><span data-stu-id="80fc2-110">Click Create.</span></span>
4. <span data-ttu-id="80fc2-111">No campo Nome de hierarquia de dimensões, digite "Hierarquia de comportamento de custo".</span><span class="sxs-lookup"><span data-stu-id="80fc2-111">In the Dimension hierarchy name field, type 'Cost behavior hierarchy'.</span></span>
5. <span data-ttu-id="80fc2-112">No campo Dimensão, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="80fc2-112">In the Dimension field, enter or select a value.</span></span>
    * <span data-ttu-id="80fc2-113">Selecione Elementos de custo.</span><span class="sxs-lookup"><span data-stu-id="80fc2-113">Select Cost elements.</span></span>  
6. <span data-ttu-id="80fc2-114">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="80fc2-114">Click Save.</span></span>
7. <span data-ttu-id="80fc2-115">Clique em Exibir hierarquia.</span><span class="sxs-lookup"><span data-stu-id="80fc2-115">Click View hierarchy.</span></span>
8. <span data-ttu-id="80fc2-116">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="80fc2-116">Click New.</span></span>
9. <span data-ttu-id="80fc2-117">No campo Nome do nó, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="80fc2-117">In the Node name field, type a value.</span></span>
    * <span data-ttu-id="80fc2-118">Insira Custo fixo.</span><span class="sxs-lookup"><span data-stu-id="80fc2-118">Enter Fixed cost.</span></span>  
10. <span data-ttu-id="80fc2-119">Na árvore, selecione "Hierarquia de comportamento de custo".</span><span class="sxs-lookup"><span data-stu-id="80fc2-119">In the tree, select 'Cost behavior hierarchy'.</span></span>
11. <span data-ttu-id="80fc2-120">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="80fc2-120">Click New.</span></span>
12. <span data-ttu-id="80fc2-121">No campo Nome do nó, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="80fc2-121">In the Node name field, type a value.</span></span>
    * <span data-ttu-id="80fc2-122">Insira Custo variável.</span><span class="sxs-lookup"><span data-stu-id="80fc2-122">Enter Variable cost.</span></span>  
13. <span data-ttu-id="80fc2-123">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="80fc2-123">Click Save.</span></span>
14. <span data-ttu-id="80fc2-124">Na árvore, selecione 'Hierarquia de comportamento de custo\Custo fixo'.</span><span class="sxs-lookup"><span data-stu-id="80fc2-124">In the tree, select 'Cost behavior hierarchy\Fixed cost'.</span></span>
15. <span data-ttu-id="80fc2-125">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="80fc2-125">Click New.</span></span>
16. <span data-ttu-id="80fc2-126">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="80fc2-126">In the list, mark the selected row.</span></span>
17. <span data-ttu-id="80fc2-127">No campo Membro da dimensão de origem, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="80fc2-127">In the From dimension member field, enter or select a value.</span></span>
    * <span data-ttu-id="80fc2-128">O intervalo de membros de dimensão pode conter intervalos, mas os membros não serão sobrepostos.</span><span class="sxs-lookup"><span data-stu-id="80fc2-128">The range of dimension members can contain gaps, but the members cannot overlap.</span></span>  
18. <span data-ttu-id="80fc2-129">No campo Membro da dimensão de destino, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="80fc2-129">In the To dimension member field, enter or select a value.</span></span>
    * <span data-ttu-id="80fc2-130">O intervalo de membros de dimensão pode conter intervalos, mas os membros não serão sobrepostos.</span><span class="sxs-lookup"><span data-stu-id="80fc2-130">The range of dimension members can contain gaps, but the members cannot overlap.</span></span>  
19. <span data-ttu-id="80fc2-131">Na árvore, selecione 'Hierarquia de comportamento de custo\Custo variável'.</span><span class="sxs-lookup"><span data-stu-id="80fc2-131">In the tree, select 'Cost behavior hierarchy\Variable cost'.</span></span>
20. <span data-ttu-id="80fc2-132">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="80fc2-132">Click New.</span></span>
21. <span data-ttu-id="80fc2-133">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="80fc2-133">In the list, mark the selected row.</span></span>
22. <span data-ttu-id="80fc2-134">No campo Membro da dimensão de origem, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="80fc2-134">In the From dimension member field, enter or select a value.</span></span>
    * <span data-ttu-id="80fc2-135">O intervalo de membros de dimensão pode conter intervalos, mas os membros não serão sobrepostos.</span><span class="sxs-lookup"><span data-stu-id="80fc2-135">The range of dimension members can contain gaps, but the members cannot overlap.</span></span>  
23. <span data-ttu-id="80fc2-136">No campo Membro da dimensão de destino, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="80fc2-136">In the To dimension member field, enter or select a value.</span></span>
    * <span data-ttu-id="80fc2-137">O intervalo de membros de dimensão pode conter intervalos, mas os membros não serão sobrepostos.</span><span class="sxs-lookup"><span data-stu-id="80fc2-137">The range of dimension members can contain gaps, but the members cannot overlap.</span></span>  
24. <span data-ttu-id="80fc2-138">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="80fc2-138">Click Save.</span></span>

## <a name="create-the-policy-and-rules"></a><span data-ttu-id="80fc2-139">Criar a política e as regras</span><span class="sxs-lookup"><span data-stu-id="80fc2-139">Create the policy and rules</span></span>
1. <span data-ttu-id="80fc2-140">Vá para Contabilização de custos > Políticas > Políticas de comportamento de custo.</span><span class="sxs-lookup"><span data-stu-id="80fc2-140">Go to Cost accounting > Policies > Cost behavior policies.</span></span>
2. <span data-ttu-id="80fc2-141">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="80fc2-141">Click New.</span></span>
3. <span data-ttu-id="80fc2-142">No campo Nome da política, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="80fc2-142">In the Policy name field, type a value.</span></span>
4. <span data-ttu-id="80fc2-143">No campo Hierarquia da dimensão de elemento de custo, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="80fc2-143">In the Cost element dimension hierarchy field, enter or select a value.</span></span>
    * <span data-ttu-id="80fc2-144">Selecione a hierarquia da política que acabou de criar.</span><span class="sxs-lookup"><span data-stu-id="80fc2-144">Select the policy hierarchy that you just created.</span></span>  
5. <span data-ttu-id="80fc2-145">No campo Hierarquia da dimensão de objeto de custo, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="80fc2-145">In the Cost object dimension hierarchy field, enter or select a value.</span></span>
    * <span data-ttu-id="80fc2-146">Selecione Organização.</span><span class="sxs-lookup"><span data-stu-id="80fc2-146">Select Organization.</span></span>  
6. <span data-ttu-id="80fc2-147">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="80fc2-147">Click Save.</span></span>
7. <span data-ttu-id="80fc2-148">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="80fc2-148">Click New.</span></span>
8. <span data-ttu-id="80fc2-149">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="80fc2-149">In the list, mark the selected row.</span></span>
9. <span data-ttu-id="80fc2-150">No campo Nó da hierarquia da dimensão de elemento de custo, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="80fc2-150">In the Cost element dimension hierarchy node field, enter or select a value.</span></span>
    * <span data-ttu-id="80fc2-151">Expanda a hierarquia para selecionar Custo variável.</span><span class="sxs-lookup"><span data-stu-id="80fc2-151">Expand the hierarchy to select Variable cost.</span></span>  
10. <span data-ttu-id="80fc2-152">No campo Nó da hierarquia da dimensão de objeto de custo, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="80fc2-152">In the Cost object dimension hierarchy node field, enter or select a value.</span></span>
    * <span data-ttu-id="80fc2-153">Por padrão, a porcentagem variável é 100%.</span><span class="sxs-lookup"><span data-stu-id="80fc2-153">By default, the variable percentage is 100 percent.</span></span>  
11. <span data-ttu-id="80fc2-154">Clique em Atribuições de políticas para unidade de controle de custo.</span><span class="sxs-lookup"><span data-stu-id="80fc2-154">Click Policy assignments for cost control unit.</span></span>
12. <span data-ttu-id="80fc2-155">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="80fc2-155">Click New.</span></span>
13. <span data-ttu-id="80fc2-156">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="80fc2-156">In the list, mark the selected row.</span></span>
14. <span data-ttu-id="80fc2-157">No campo Válido a partir da data contábil, insira uma data.</span><span class="sxs-lookup"><span data-stu-id="80fc2-157">In the Valid from accounting date field, enter a date.</span></span>
    * <span data-ttu-id="80fc2-158">As regras são efetivas de acordo com a data, e o usuário ou o sistema podem fazer com que uma regra expire se uma versão mais recente for criada.</span><span class="sxs-lookup"><span data-stu-id="80fc2-158">The rules are date-effective, and a user or the system can expire a rule if a newer version is created.</span></span>  
15. <span data-ttu-id="80fc2-159">No campo Unidade de controle de custo, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="80fc2-159">In the Cost control unit field, enter or select a value.</span></span>
16. <span data-ttu-id="80fc2-160">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="80fc2-160">Click Save.</span></span>


