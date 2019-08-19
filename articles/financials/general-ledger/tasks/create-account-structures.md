---
title: Criar estruturas de conta
description: Este guia de tarefas aborda a criação de uma estrutura de conta.
author: aprilolson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DimensionConfigureAccountStructure, DimensionCreateAccountStructure, DimensionHierarchyAddLevel, DimensionHierarchyConstraintActivate
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 2183f88356fc8094781af147bf079c4e53ffb2b4
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/01/2019
ms.locfileid: "1846694"
---
# <a name="create-account-structures"></a><span data-ttu-id="e0306-103">Criar estruturas de conta</span><span class="sxs-lookup"><span data-stu-id="e0306-103">Create account structures</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="e0306-104">Este guia de tarefas aborda a criação de uma estrutura de conta.</span><span class="sxs-lookup"><span data-stu-id="e0306-104">This task guide steps through creating an account structure.</span></span> <span data-ttu-id="e0306-105">As etapas usam a empresa USMF de dados de demonstração.</span><span class="sxs-lookup"><span data-stu-id="e0306-105">The steps use demo data company USMF.</span></span>

1. <span data-ttu-id="e0306-106">Vá para Contabilidade > Plano de contas > Estruturas > Configurar estruturas de conta.</span><span class="sxs-lookup"><span data-stu-id="e0306-106">Go to General ledger > Chart of accounts > Structures > Configure account structures.</span></span>
2. <span data-ttu-id="e0306-107">Clique em Novo para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="e0306-107">Click New to open the drop dialog.</span></span>
3. <span data-ttu-id="e0306-108">No campo Estrutura de conta, digite um nome para descrever a finalidade da estrutura de conta.</span><span class="sxs-lookup"><span data-stu-id="e0306-108">In the Account structure field, type a name to describe the purpose of the account structure.</span></span>
4. <span data-ttu-id="e0306-109">No campo Descrição, digite uma descrição para especificar a finalidade da estrutura de conta.</span><span class="sxs-lookup"><span data-stu-id="e0306-109">In the Description field, type a description to specify the purpose of the account structure.</span></span>
5. <span data-ttu-id="e0306-110">Clique em Criar.</span><span class="sxs-lookup"><span data-stu-id="e0306-110">Click Create.</span></span>
6. <span data-ttu-id="e0306-111">Clique em Adicionar segmento.</span><span class="sxs-lookup"><span data-stu-id="e0306-111">Click Add segment.</span></span>
7. <span data-ttu-id="e0306-112">Na lista Dimensões, selecione a dimensão que será adicionada à estrutura de conta.</span><span class="sxs-lookup"><span data-stu-id="e0306-112">In the Dimensions list, select the dimension to add to the account structure.</span></span>
8. <span data-ttu-id="e0306-113">Clique em Adicionar segmento.</span><span class="sxs-lookup"><span data-stu-id="e0306-113">Click Add segment.</span></span>
9. <span data-ttu-id="e0306-114">Clique em Adicionar segmento.</span><span class="sxs-lookup"><span data-stu-id="e0306-114">Click Add segment.</span></span>
10. <span data-ttu-id="e0306-115">Na lista Dimensões, selecione a dimensão que será adicionada à estrutura de conta.</span><span class="sxs-lookup"><span data-stu-id="e0306-115">In the Dimensions list, select the dimension to add to the account structure.</span></span>
11. <span data-ttu-id="e0306-116">Clique em Adicionar segmento.</span><span class="sxs-lookup"><span data-stu-id="e0306-116">Click Add segment.</span></span>
12. <span data-ttu-id="e0306-117">Clique em Adicionar segmento.</span><span class="sxs-lookup"><span data-stu-id="e0306-117">Click Add segment.</span></span>
13. <span data-ttu-id="e0306-118">Na lista Dimensões, selecione a dimensão que será adicionada à estrutura de conta.</span><span class="sxs-lookup"><span data-stu-id="e0306-118">In the Dimensions list, select the dimension to add to the account structure.</span></span>
14. <span data-ttu-id="e0306-119">Clique em Adicionar segmento.</span><span class="sxs-lookup"><span data-stu-id="e0306-119">Click Add segment.</span></span>
15. <span data-ttu-id="e0306-120">Na grade, selecione o segmento para editar os valores permitidos.</span><span class="sxs-lookup"><span data-stu-id="e0306-120">In the grid, select the segment to edit the allowed values.</span></span>
    * <span data-ttu-id="e0306-121">Por exemplo, clique em Conta principal.</span><span class="sxs-lookup"><span data-stu-id="e0306-121">For example, click in Main Account.</span></span>  
16. <span data-ttu-id="e0306-122">No campo Operador, selecione uma opção, como está entre e inclui.</span><span class="sxs-lookup"><span data-stu-id="e0306-122">In the Operator field, select an option, such as is between and includes.</span></span>
17. <span data-ttu-id="e0306-123">No campo Valor, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="e0306-123">In the Value field, type a value.</span></span>
    * <span data-ttu-id="e0306-124">Por exemplo, 600000.</span><span class="sxs-lookup"><span data-stu-id="e0306-124">For example, 600000.</span></span>  
18. <span data-ttu-id="e0306-125">No campo por meio de, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="e0306-125">In the through field, type a value.</span></span>
    * <span data-ttu-id="e0306-126">Por exemplo, 699999.</span><span class="sxs-lookup"><span data-stu-id="e0306-126">For example, 699999.</span></span>  
19. <span data-ttu-id="e0306-127">Clique em Aplicar.</span><span class="sxs-lookup"><span data-stu-id="e0306-127">Click Apply.</span></span>
20. <span data-ttu-id="e0306-128">Na grade, selecione o segmento para editar os valores permitidos.</span><span class="sxs-lookup"><span data-stu-id="e0306-128">In the grid, select the segment to edit the allowed values.</span></span>
    * <span data-ttu-id="e0306-129">Por exemplo, Departamento.</span><span class="sxs-lookup"><span data-stu-id="e0306-129">For example, Department.</span></span>  
21. <span data-ttu-id="e0306-130">No campo Operador, selecione uma opção, como está entre e inclui.</span><span class="sxs-lookup"><span data-stu-id="e0306-130">In the Operator field, select an option, such as is between and includes.</span></span>
22. <span data-ttu-id="e0306-131">No campo Valor, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="e0306-131">In the Value field, type a value.</span></span>
    * <span data-ttu-id="e0306-132">Por exemplo, 022.</span><span class="sxs-lookup"><span data-stu-id="e0306-132">For example, 022.</span></span>  
23. <span data-ttu-id="e0306-133">No campo por meio de, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="e0306-133">In the through field, type a value.</span></span>
    * <span data-ttu-id="e0306-134">Por exemplo, 031.</span><span class="sxs-lookup"><span data-stu-id="e0306-134">For example, 031.</span></span>  
24. <span data-ttu-id="e0306-135">Clique em Adicionar novos critérios.</span><span class="sxs-lookup"><span data-stu-id="e0306-135">Click Add new criteria.</span></span>
25. <span data-ttu-id="e0306-136">No campo Operador, selecione uma opção, como está entre e inclui.</span><span class="sxs-lookup"><span data-stu-id="e0306-136">In the Operator field, select an option, such as is between and includes.</span></span>
26. <span data-ttu-id="e0306-137">No campo Valor, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="e0306-137">In the Value field, type a value.</span></span>
    * <span data-ttu-id="e0306-138">Por exemplo, 033.</span><span class="sxs-lookup"><span data-stu-id="e0306-138">For example, 033.</span></span>  
27. <span data-ttu-id="e0306-139">No campo por meio de, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="e0306-139">In the through field, type a value.</span></span>
    * <span data-ttu-id="e0306-140">Por exemplo, 034.</span><span class="sxs-lookup"><span data-stu-id="e0306-140">For example, 034.</span></span>  
28. <span data-ttu-id="e0306-141">Clique em Aplicar.</span><span class="sxs-lookup"><span data-stu-id="e0306-141">Click Apply.</span></span>
29. <span data-ttu-id="e0306-142">Na grade, selecione o segmento para editar os valores permitidos.</span><span class="sxs-lookup"><span data-stu-id="e0306-142">In the grid, select the segment to edit the allowed values.</span></span>
    * <span data-ttu-id="e0306-143">Por exemplo, Centro de custo.</span><span class="sxs-lookup"><span data-stu-id="e0306-143">For example, Cost Center.</span></span>  
30. <span data-ttu-id="e0306-144">No campo Centro de custo, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="e0306-144">In the CostCenter field, type a value.</span></span>
    * <span data-ttu-id="e0306-145">Por exemplo, 007..021.</span><span class="sxs-lookup"><span data-stu-id="e0306-145">For example, 007..021.</span></span>  
31. <span data-ttu-id="e0306-146">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="e0306-146">Click Add.</span></span>
32. <span data-ttu-id="e0306-147">No campo Conta principal, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="e0306-147">In the MainAccount field, type a value.</span></span>
    * <span data-ttu-id="e0306-148">Por exemplo, 600000..699999</span><span class="sxs-lookup"><span data-stu-id="e0306-148">For example, 600000..699999</span></span>  
33. <span data-ttu-id="e0306-149">Na grade, selecione o segmento para editar os valores permitidos.</span><span class="sxs-lookup"><span data-stu-id="e0306-149">In the grid, select the segment to edit the allowed values.</span></span>
    * <span data-ttu-id="e0306-150">Por exemplo, Departamento.</span><span class="sxs-lookup"><span data-stu-id="e0306-150">For example, Department.</span></span>  
34. <span data-ttu-id="e0306-151">No campo Departamento, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="e0306-151">In the Department field, type a value.</span></span>
    * <span data-ttu-id="e0306-152">Por exemplo, 032.</span><span class="sxs-lookup"><span data-stu-id="e0306-152">For example, 032.</span></span>  
35. <span data-ttu-id="e0306-153">No campo Centro de custo, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="e0306-153">In the CostCenter field, type a value.</span></span>
    * <span data-ttu-id="e0306-154">Por exemplo, 086.</span><span class="sxs-lookup"><span data-stu-id="e0306-154">For example, 086.</span></span>  
36. <span data-ttu-id="e0306-155">Clique em Validar.</span><span class="sxs-lookup"><span data-stu-id="e0306-155">Click Validate.</span></span>
37. <span data-ttu-id="e0306-156">Clique em Ativar.</span><span class="sxs-lookup"><span data-stu-id="e0306-156">Click Activate.</span></span>
38. <span data-ttu-id="e0306-157">Clique em Ativar.</span><span class="sxs-lookup"><span data-stu-id="e0306-157">Click Activate.</span></span>

