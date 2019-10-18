---
title: Criar estruturas de conta
description: Este guia de tarefas aborda a criação de uma estrutura de conta.
author: aprilolson
manager: AnnBe
ms.date: 07/01/2019
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
ms.openlocfilehash: 8b100d5da6ec26dc386c0c6cb0793245531eb0d8
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2186247"
---
# <a name="create-account-structures"></a><span data-ttu-id="10a68-103">Criar estruturas de conta</span><span class="sxs-lookup"><span data-stu-id="10a68-103">Create account structures</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="10a68-104">Este guia de tarefas aborda a criação de uma estrutura de conta.</span><span class="sxs-lookup"><span data-stu-id="10a68-104">This task guide steps through creating an account structure.</span></span> <span data-ttu-id="10a68-105">As etapas usam a empresa USMF de dados de demonstração.</span><span class="sxs-lookup"><span data-stu-id="10a68-105">The steps use demo data company USMF.</span></span>

1. <span data-ttu-id="10a68-106">Vá para **Painel de Navegação > Módulos > Contabilidade > Plano de contas > Estruturas > Configurar estruturas de conta**.</span><span class="sxs-lookup"><span data-stu-id="10a68-106">Go to **Navigation pane > Modules > General ledger > Chart of accounts > Structures > Configure account structures**.</span></span>
2. <span data-ttu-id="10a68-107">No **Painel de Ações**, clique em **Novo** para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="10a68-107">On the **Action pane**, click **New** to open the drop dialog.</span></span>
3. <span data-ttu-id="10a68-108">No campo **Estrutura de conta**, digite um nome para descrever a finalidade da estrutura de conta.</span><span class="sxs-lookup"><span data-stu-id="10a68-108">In the **Account structure** field, type a name to describe the purpose of the account structure.</span></span>
4. <span data-ttu-id="10a68-109">No campo **Descrição**, digite uma descrição para especificar a finalidade da estrutura de conta.</span><span class="sxs-lookup"><span data-stu-id="10a68-109">In the **Description** field, type a description to specify the purpose of the account structure.</span></span>
5. <span data-ttu-id="10a68-110">Clique em **Criar**.</span><span class="sxs-lookup"><span data-stu-id="10a68-110">Click **Create**.</span></span>
6. <span data-ttu-id="10a68-111">Nos **Segmentos e valores permitidos**, clique em **Adicionar segmento**.</span><span class="sxs-lookup"><span data-stu-id="10a68-111">In the **Segments and allowed values**, click **Add segment**.</span></span>
7. <span data-ttu-id="10a68-112">Na lista de dimensões, selecione a dimensão que será adicionada à estrutura de conta.</span><span class="sxs-lookup"><span data-stu-id="10a68-112">In the dimensions list, select the dimension to add to the account structure.</span></span>
8. <span data-ttu-id="10a68-113">No final da lista, clique em **Adicionar segmento**.</span><span class="sxs-lookup"><span data-stu-id="10a68-113">At the end of the list, click **Add segment**.</span></span>
9. <span data-ttu-id="10a68-114">Repita as etapas 6 a 9, conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="10a68-114">Repeat step 6 to 9 as needed.</span></span>
10. <span data-ttu-id="10a68-115">Na seção **Detalhes do valor permitido**, selecione o segmento para editar os valores permitidos.</span><span class="sxs-lookup"><span data-stu-id="10a68-115">In the **Allowed value details** section, select the segment to edit the allowed values.</span></span>
    <span data-ttu-id="10a68-116">Por exemplo, clique no campo **Conta Principal**.</span><span class="sxs-lookup"><span data-stu-id="10a68-116">For example, click the **Main Account** field.</span></span>  
11. <span data-ttu-id="10a68-117">No campo **Operador**, selecione uma opção, como está entre e inclui.</span><span class="sxs-lookup"><span data-stu-id="10a68-117">In the **Operator** field, select an option, such as is between and includes.</span></span>
12. <span data-ttu-id="10a68-118">No campo **Valor**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="10a68-118">In the **Value** field, type a value.</span></span> <span data-ttu-id="10a68-119">Por exemplo, 600000.</span><span class="sxs-lookup"><span data-stu-id="10a68-119">For example, 600000.</span></span>  
13. <span data-ttu-id="10a68-120">No campo **por meio de**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="10a68-120">In the **through** field, type a value.</span></span> <span data-ttu-id="10a68-121">Por exemplo, 699999.</span><span class="sxs-lookup"><span data-stu-id="10a68-121">For example, 699999.</span></span>  
14. <span data-ttu-id="10a68-122">Na seção **Detalhes do valor permitido**, clique em **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="10a68-122">In the **Allowed value details** section, click **Apply**.</span></span>
15. <span data-ttu-id="10a68-123">Repita as etapas 10 a 15, conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="10a68-123">Repeat step 10 to 15 as needed.</span></span>  
16. <span data-ttu-id="10a68-124">Na seção **Detalhes do valor permitido**, clique em **Adicionar novos critérios**.</span><span class="sxs-lookup"><span data-stu-id="10a68-124">In the **Allowed value details** section, click **Add new criteria**.</span></span>
17. <span data-ttu-id="10a68-125">No campo Operador, selecione uma opção, como está entre e inclui.</span><span class="sxs-lookup"><span data-stu-id="10a68-125">In the Operator field, select an option, such as is between and includes.</span></span>
18. <span data-ttu-id="10a68-126">No campo **Valor**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="10a68-126">In the **Value** field, type a value.</span></span> <span data-ttu-id="10a68-127">Por exemplo, 033.</span><span class="sxs-lookup"><span data-stu-id="10a68-127">For example, 033.</span></span>  
19. <span data-ttu-id="10a68-128">No campo **por meio de**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="10a68-128">In the **through** field, type a value.</span></span> <span data-ttu-id="10a68-129">Por exemplo, 034.</span><span class="sxs-lookup"><span data-stu-id="10a68-129">For example, 034.</span></span>  
20. <span data-ttu-id="10a68-130">Clique em **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="10a68-130">Click **Apply**.</span></span>
21. <span data-ttu-id="10a68-131">Na grade, selecione o segmento para editar os valores permitidos.</span><span class="sxs-lookup"><span data-stu-id="10a68-131">In the grid, select the segment to edit the allowed values.</span></span> <span data-ttu-id="10a68-132">Por exemplo, Centro de custo.</span><span class="sxs-lookup"><span data-stu-id="10a68-132">For example, Cost Center.</span></span>  
22. <span data-ttu-id="10a68-133">No campo **Centro de custo**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="10a68-133">In the **CostCenter field**, type a value.</span></span> <span data-ttu-id="10a68-134">Por exemplo, 007..021.</span><span class="sxs-lookup"><span data-stu-id="10a68-134">For example, 007..021.</span></span>  
23. <span data-ttu-id="10a68-135">Nos **Segmentos e valores permitidos**, clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="10a68-135">In the **Segments and allowed values**, click **Add**.</span></span>
24. <span data-ttu-id="10a68-136">No campo **Conta principal**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="10a68-136">In the **MainAccount** field, type a value.</span></span> <span data-ttu-id="10a68-137">Por exemplo, 600000..699999</span><span class="sxs-lookup"><span data-stu-id="10a68-137">For example, 600000..699999</span></span>  
25. <span data-ttu-id="10a68-138">Na grade, selecione o segmento para editar os valores permitidos.</span><span class="sxs-lookup"><span data-stu-id="10a68-138">In the grid, select the segment to edit the allowed values.</span></span> <span data-ttu-id="10a68-139">Por exemplo, Departamento.</span><span class="sxs-lookup"><span data-stu-id="10a68-139">For example, Department.</span></span>  
26. <span data-ttu-id="10a68-140">No campo Departamento, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="10a68-140">In the Department field, type a value.</span></span> <span data-ttu-id="10a68-141">Por exemplo, 032.</span><span class="sxs-lookup"><span data-stu-id="10a68-141">For example, 032.</span></span>  
27. <span data-ttu-id="10a68-142">No campo Centro de custo, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="10a68-142">In the CostCenter field, type a value.</span></span> <span data-ttu-id="10a68-143">Por exemplo, 086.</span><span class="sxs-lookup"><span data-stu-id="10a68-143">For example, 086.</span></span>  
28. <span data-ttu-id="10a68-144">No **Painel de Ações**, clique em **Validar**.</span><span class="sxs-lookup"><span data-stu-id="10a68-144">On the **Action pane**, click **Validate**.</span></span>
29. <span data-ttu-id="10a68-145">No **Painel de Ações**, clique em **Ativar**.</span><span class="sxs-lookup"><span data-stu-id="10a68-145">On the **Action pane**, click **Activate**.</span></span>
30. <span data-ttu-id="10a68-146">Clique em **Ativar**.</span><span class="sxs-lookup"><span data-stu-id="10a68-146">Click **Activate**.</span></span>

