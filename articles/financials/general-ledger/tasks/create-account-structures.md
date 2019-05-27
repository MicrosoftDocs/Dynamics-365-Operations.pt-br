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
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: a7dd71cc072d49f47b1d77d3a688984cd4aaa624
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1571273"
---
# <a name="create-account-structures"></a><span data-ttu-id="abab2-103">Criar estruturas de conta</span><span class="sxs-lookup"><span data-stu-id="abab2-103">Create account structures</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="abab2-104">Este guia de tarefas aborda a criação de uma estrutura de conta.</span><span class="sxs-lookup"><span data-stu-id="abab2-104">This task guide steps through creating an account structure.</span></span> <span data-ttu-id="abab2-105">As etapas usam a empresa USMF de dados de demonstração.</span><span class="sxs-lookup"><span data-stu-id="abab2-105">The steps use demo data company USMF.</span></span>

1. <span data-ttu-id="abab2-106">Vá para Contabilidade > Plano de contas > Estruturas > Configurar estruturas de conta.</span><span class="sxs-lookup"><span data-stu-id="abab2-106">Go to General ledger > Chart of accounts > Structures > Configure account structures.</span></span>
2. <span data-ttu-id="abab2-107">Clique em Novo para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="abab2-107">Click New to open the drop dialog.</span></span>
3. <span data-ttu-id="abab2-108">No campo Estrutura de conta, digite um nome para descrever a finalidade da estrutura de conta.</span><span class="sxs-lookup"><span data-stu-id="abab2-108">In the Account structure field, type a name to describe the purpose of the account structure.</span></span>
4. <span data-ttu-id="abab2-109">No campo Descrição, digite uma descrição para especificar a finalidade da estrutura de conta.</span><span class="sxs-lookup"><span data-stu-id="abab2-109">In the Description field, type a description to specify the purpose of the account structure.</span></span>
5. <span data-ttu-id="abab2-110">Clique em Criar.</span><span class="sxs-lookup"><span data-stu-id="abab2-110">Click Create.</span></span>
6. <span data-ttu-id="abab2-111">Clique em Adicionar segmento.</span><span class="sxs-lookup"><span data-stu-id="abab2-111">Click Add segment.</span></span>
7. <span data-ttu-id="abab2-112">Na lista Dimensões, selecione a dimensão que será adicionada à estrutura de conta.</span><span class="sxs-lookup"><span data-stu-id="abab2-112">In the Dimensions list, select the dimension to add to the account structure.</span></span>
8. <span data-ttu-id="abab2-113">Clique em Adicionar segmento.</span><span class="sxs-lookup"><span data-stu-id="abab2-113">Click Add segment.</span></span>
9. <span data-ttu-id="abab2-114">Clique em Adicionar segmento.</span><span class="sxs-lookup"><span data-stu-id="abab2-114">Click Add segment.</span></span>
10. <span data-ttu-id="abab2-115">Na lista Dimensões, selecione a dimensão que será adicionada à estrutura de conta.</span><span class="sxs-lookup"><span data-stu-id="abab2-115">In the Dimensions list, select the dimension to add to the account structure.</span></span>
11. <span data-ttu-id="abab2-116">Clique em Adicionar segmento.</span><span class="sxs-lookup"><span data-stu-id="abab2-116">Click Add segment.</span></span>
12. <span data-ttu-id="abab2-117">Clique em Adicionar segmento.</span><span class="sxs-lookup"><span data-stu-id="abab2-117">Click Add segment.</span></span>
13. <span data-ttu-id="abab2-118">Na lista Dimensões, selecione a dimensão que será adicionada à estrutura de conta.</span><span class="sxs-lookup"><span data-stu-id="abab2-118">In the Dimensions list, select the dimension to add to the account structure.</span></span>
14. <span data-ttu-id="abab2-119">Clique em Adicionar segmento.</span><span class="sxs-lookup"><span data-stu-id="abab2-119">Click Add segment.</span></span>
15. <span data-ttu-id="abab2-120">Na grade, selecione o segmento para editar os valores permitidos.</span><span class="sxs-lookup"><span data-stu-id="abab2-120">In the grid, select the segment to edit the allowed values.</span></span>
    * <span data-ttu-id="abab2-121">Por exemplo, clique em Conta principal.</span><span class="sxs-lookup"><span data-stu-id="abab2-121">For example, click in Main Account.</span></span>  
16. <span data-ttu-id="abab2-122">No campo Operador, selecione uma opção, como está entre e inclui.</span><span class="sxs-lookup"><span data-stu-id="abab2-122">In the Operator field, select an option, such as is between and includes.</span></span>
17. <span data-ttu-id="abab2-123">No campo Valor, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="abab2-123">In the Value field, type a value.</span></span>
    * <span data-ttu-id="abab2-124">Por exemplo, 600000.</span><span class="sxs-lookup"><span data-stu-id="abab2-124">For example, 600000.</span></span>  
18. <span data-ttu-id="abab2-125">No campo por meio de, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="abab2-125">In the through field, type a value.</span></span>
    * <span data-ttu-id="abab2-126">Por exemplo, 699999.</span><span class="sxs-lookup"><span data-stu-id="abab2-126">For example, 699999.</span></span>  
19. <span data-ttu-id="abab2-127">Clique em Aplicar.</span><span class="sxs-lookup"><span data-stu-id="abab2-127">Click Apply.</span></span>
20. <span data-ttu-id="abab2-128">Na grade, selecione o segmento para editar os valores permitidos.</span><span class="sxs-lookup"><span data-stu-id="abab2-128">In the grid, select the segment to edit the allowed values.</span></span>
    * <span data-ttu-id="abab2-129">Por exemplo, Departamento.</span><span class="sxs-lookup"><span data-stu-id="abab2-129">For example, Department.</span></span>  
21. <span data-ttu-id="abab2-130">No campo Operador, selecione uma opção, como está entre e inclui.</span><span class="sxs-lookup"><span data-stu-id="abab2-130">In the Operator field, select an option, such as is between and includes.</span></span>
22. <span data-ttu-id="abab2-131">No campo Valor, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="abab2-131">In the Value field, type a value.</span></span>
    * <span data-ttu-id="abab2-132">Por exemplo, 022.</span><span class="sxs-lookup"><span data-stu-id="abab2-132">For example, 022.</span></span>  
23. <span data-ttu-id="abab2-133">No campo por meio de, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="abab2-133">In the through field, type a value.</span></span>
    * <span data-ttu-id="abab2-134">Por exemplo, 031.</span><span class="sxs-lookup"><span data-stu-id="abab2-134">For example, 031.</span></span>  
24. <span data-ttu-id="abab2-135">Clique em Adicionar novos critérios.</span><span class="sxs-lookup"><span data-stu-id="abab2-135">Click Add new criteria.</span></span>
25. <span data-ttu-id="abab2-136">No campo Operador, selecione uma opção, como está entre e inclui.</span><span class="sxs-lookup"><span data-stu-id="abab2-136">In the Operator field, select an option, such as is between and includes.</span></span>
26. <span data-ttu-id="abab2-137">No campo Valor, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="abab2-137">In the Value field, type a value.</span></span>
    * <span data-ttu-id="abab2-138">Por exemplo, 033.</span><span class="sxs-lookup"><span data-stu-id="abab2-138">For example, 033.</span></span>  
27. <span data-ttu-id="abab2-139">No campo por meio de, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="abab2-139">In the through field, type a value.</span></span>
    * <span data-ttu-id="abab2-140">Por exemplo, 034.</span><span class="sxs-lookup"><span data-stu-id="abab2-140">For example, 034.</span></span>  
28. <span data-ttu-id="abab2-141">Clique em Aplicar.</span><span class="sxs-lookup"><span data-stu-id="abab2-141">Click Apply.</span></span>
29. <span data-ttu-id="abab2-142">Na grade, selecione o segmento para editar os valores permitidos.</span><span class="sxs-lookup"><span data-stu-id="abab2-142">In the grid, select the segment to edit the allowed values.</span></span>
    * <span data-ttu-id="abab2-143">Por exemplo, Centro de custo.</span><span class="sxs-lookup"><span data-stu-id="abab2-143">For example, Cost Center.</span></span>  
30. <span data-ttu-id="abab2-144">No campo Centro de custo, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="abab2-144">In the CostCenter field, type a value.</span></span>
    * <span data-ttu-id="abab2-145">Por exemplo, 007..021.</span><span class="sxs-lookup"><span data-stu-id="abab2-145">For example, 007..021.</span></span>  
31. <span data-ttu-id="abab2-146">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="abab2-146">Click Add.</span></span>
32. <span data-ttu-id="abab2-147">No campo Conta principal, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="abab2-147">In the MainAccount field, type a value.</span></span>
    * <span data-ttu-id="abab2-148">Por exemplo, 600000..699999</span><span class="sxs-lookup"><span data-stu-id="abab2-148">For example, 600000..699999</span></span>  
33. <span data-ttu-id="abab2-149">Na grade, selecione o segmento para editar os valores permitidos.</span><span class="sxs-lookup"><span data-stu-id="abab2-149">In the grid, select the segment to edit the allowed values.</span></span>
    * <span data-ttu-id="abab2-150">Por exemplo, Departamento.</span><span class="sxs-lookup"><span data-stu-id="abab2-150">For example, Department.</span></span>  
34. <span data-ttu-id="abab2-151">No campo Departamento, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="abab2-151">In the Department field, type a value.</span></span>
    * <span data-ttu-id="abab2-152">Por exemplo, 032.</span><span class="sxs-lookup"><span data-stu-id="abab2-152">For example, 032.</span></span>  
35. <span data-ttu-id="abab2-153">No campo Centro de custo, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="abab2-153">In the CostCenter field, type a value.</span></span>
    * <span data-ttu-id="abab2-154">Por exemplo, 086.</span><span class="sxs-lookup"><span data-stu-id="abab2-154">For example, 086.</span></span>  
36. <span data-ttu-id="abab2-155">Clique em Validar.</span><span class="sxs-lookup"><span data-stu-id="abab2-155">Click Validate.</span></span>
37. <span data-ttu-id="abab2-156">Clique em Ativar.</span><span class="sxs-lookup"><span data-stu-id="abab2-156">Click Activate.</span></span>
38. <span data-ttu-id="abab2-157">Clique em Ativar.</span><span class="sxs-lookup"><span data-stu-id="abab2-157">Click Activate.</span></span>

