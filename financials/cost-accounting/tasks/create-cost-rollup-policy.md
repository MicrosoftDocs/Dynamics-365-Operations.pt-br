--- 
title: "Criar uma política de acúmulo de custo"
description: "Este procedimento mostra como criar uma política de acúmulo de custo e criar regras para a política."
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
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 42656cbf445fd3f79844884d7d35243c5b051a4a
ms.contentlocale: pt-br
ms.lasthandoff: 08/29/2017

---
# <a name="create-a-cost-rollup-policy"></a><span data-ttu-id="2a72d-103">Criar uma política de acúmulo de custo</span><span class="sxs-lookup"><span data-stu-id="2a72d-103">Create a cost rollup policy</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="2a72d-104">Este procedimento mostra como criar uma política de acúmulo de custo e criar regras para a política.</span><span class="sxs-lookup"><span data-stu-id="2a72d-104">This procedure shows how to create a cost rollup policy and create rules for the policy.</span></span> <span data-ttu-id="2a72d-105">Os dados demonstrativos utilizados na criação desse procedimento são do conjunto USP2.</span><span class="sxs-lookup"><span data-stu-id="2a72d-105">The demo data used to create this procedure is USP2.</span></span>


## <a name="create-a-policy"></a><span data-ttu-id="2a72d-106">Criar uma política</span><span class="sxs-lookup"><span data-stu-id="2a72d-106">Create a policy</span></span>
1. <span data-ttu-id="2a72d-107">Vá para Contabilização de custos > Políticas > Políticas de acúmulo de custo.</span><span class="sxs-lookup"><span data-stu-id="2a72d-107">Go to Cost accounting > Policies > Cost rollup policies.</span></span>
2. <span data-ttu-id="2a72d-108">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="2a72d-108">Click New.</span></span>
3. <span data-ttu-id="2a72d-109">No campo Nome da política, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="2a72d-109">In the Policy name field, type a value.</span></span>
4. <span data-ttu-id="2a72d-110">No campo Descrição, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="2a72d-110">In the Description field, type a value.</span></span>
5. <span data-ttu-id="2a72d-111">No campo Hierarquia da dimensão de objeto de custo, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="2a72d-111">In the Cost object dimension hierarchy field, enter or select a value.</span></span>
    * <span data-ttu-id="2a72d-112">Selecione Acúmulo de custo CC.</span><span class="sxs-lookup"><span data-stu-id="2a72d-112">Select Cost rollup CC.</span></span>  
6. <span data-ttu-id="2a72d-113">No campo Hierarquia da dimensão de elemento de custo, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="2a72d-113">In the Cost element dimension hierarchy field, enter or select a value.</span></span>
    * <span data-ttu-id="2a72d-114">Selecione Acúmulo de custo CC.</span><span class="sxs-lookup"><span data-stu-id="2a72d-114">Select Cost rollup CC.</span></span>  
7. <span data-ttu-id="2a72d-115">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="2a72d-115">Click Save.</span></span>

## <a name="create-rules-for-the-cost-rollup-policy"></a><span data-ttu-id="2a72d-116">Criar regras para a política</span><span class="sxs-lookup"><span data-stu-id="2a72d-116">Create rules for the cost rollup policy</span></span>
1. <span data-ttu-id="2a72d-117">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="2a72d-117">Click New.</span></span>
2. <span data-ttu-id="2a72d-118">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="2a72d-118">In the list, mark the selected row.</span></span>
3. <span data-ttu-id="2a72d-119">No campo Nó da hierarquia da dimensão de objeto de custo, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="2a72d-119">In the Cost object dimension hierarchy node field, enter or select a value.</span></span>
    * <span data-ttu-id="2a72d-120">Selecione 007.</span><span class="sxs-lookup"><span data-stu-id="2a72d-120">Select 007.</span></span>  
4. <span data-ttu-id="2a72d-121">No campo Nó da hierarquia da dimensão de elemento de custo, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="2a72d-121">In the Cost element dimension hierarchy node field, enter or select a value.</span></span>
    * <span data-ttu-id="2a72d-122">Selecione Acúmulo de custo CE.</span><span class="sxs-lookup"><span data-stu-id="2a72d-122">Select Cost rollup CE.</span></span>  
5. <span data-ttu-id="2a72d-123">No campo Elemento de custo secundário, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="2a72d-123">In the Secondary cost element field, enter or select a value.</span></span>
    * <span data-ttu-id="2a72d-124">Para este exemplo, mapeie o elemento de custo secundário CC-007 para o centro de custo.</span><span class="sxs-lookup"><span data-stu-id="2a72d-124">For this example, map the secondary cost element CC-007 to the cost center.</span></span>  
6. <span data-ttu-id="2a72d-125">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="2a72d-125">Click New.</span></span>
7. <span data-ttu-id="2a72d-126">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="2a72d-126">In the list, mark the selected row.</span></span>
8. <span data-ttu-id="2a72d-127">No campo Nó da hierarquia da dimensão de objeto de custo, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="2a72d-127">In the Cost object dimension hierarchy node field, enter or select a value.</span></span>
    * <span data-ttu-id="2a72d-128">Selecione 008.</span><span class="sxs-lookup"><span data-stu-id="2a72d-128">Select 008.</span></span>  
9. <span data-ttu-id="2a72d-129">No campo Nó da hierarquia da dimensão de elemento de custo, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="2a72d-129">In the Cost element dimension hierarchy node field, enter or select a value.</span></span>
    * <span data-ttu-id="2a72d-130">Selecione Acúmulo de custo CE.</span><span class="sxs-lookup"><span data-stu-id="2a72d-130">Select Cost rollup CE.</span></span>  
10. <span data-ttu-id="2a72d-131">No campo Elemento de custo secundário, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="2a72d-131">In the Secondary cost element field, enter or select a value.</span></span>
    * <span data-ttu-id="2a72d-132">Para este exemplo, mapeie o elemento de custo secundário CC-008 para o centro de custo.</span><span class="sxs-lookup"><span data-stu-id="2a72d-132">For this example, map the secondary cost element CC-008 to the cost center.</span></span>  
11. <span data-ttu-id="2a72d-133">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="2a72d-133">Click New.</span></span>
12. <span data-ttu-id="2a72d-134">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="2a72d-134">In the list, mark the selected row.</span></span>
13. <span data-ttu-id="2a72d-135">No campo Nó da hierarquia da dimensão de objeto de custo, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="2a72d-135">In the Cost object dimension hierarchy node field, enter or select a value.</span></span>
    * <span data-ttu-id="2a72d-136">Selecione 009.</span><span class="sxs-lookup"><span data-stu-id="2a72d-136">Select 009.</span></span>  
14. <span data-ttu-id="2a72d-137">No campo Nó da hierarquia da dimensão de elemento de custo, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="2a72d-137">In the Cost element dimension hierarchy node field, enter or select a value.</span></span>
    * <span data-ttu-id="2a72d-138">Selecione Acúmulo de custo CE.</span><span class="sxs-lookup"><span data-stu-id="2a72d-138">Select Cost rollup CE.</span></span>  
15. <span data-ttu-id="2a72d-139">No campo Elemento de custo secundário, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="2a72d-139">In the Secondary cost element field, enter or select a value.</span></span>
    * <span data-ttu-id="2a72d-140">Para este exemplo, mapeie o elemento de custo secundário CC-009 para o centro de custo.</span><span class="sxs-lookup"><span data-stu-id="2a72d-140">For this example, map the secondary cost element CC-009 to the cost center.</span></span>  
    * <span data-ttu-id="2a72d-141">Continue até todos os centros de custos serem mapeados aos elementos de custo secundários correspondentes.</span><span class="sxs-lookup"><span data-stu-id="2a72d-141">Continue until all cost centers are mapped to their corresponding secondary cost elements.</span></span>  
16. <span data-ttu-id="2a72d-142">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="2a72d-142">Click Save.</span></span>


