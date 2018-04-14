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
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 165d12efe1e3caf436a7573936e94203bad88330
ms.contentlocale: pt-br
ms.lasthandoff: 04/13/2018

---
# <a name="create-a-cost-rollup-policy"></a><span data-ttu-id="70603-103">Criar uma política de acúmulo de custo</span><span class="sxs-lookup"><span data-stu-id="70603-103">Create a cost rollup policy</span></span>

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="70603-104">Este procedimento mostra como criar uma política de acúmulo de custo e criar regras para a política.</span><span class="sxs-lookup"><span data-stu-id="70603-104">This procedure shows how to create a cost rollup policy and create rules for the policy.</span></span> <span data-ttu-id="70603-105">Os dados demonstrativos utilizados na criação desse procedimento são do conjunto USP2.</span><span class="sxs-lookup"><span data-stu-id="70603-105">The demo data used to create this procedure is USP2.</span></span>


## <a name="create-a-policy"></a><span data-ttu-id="70603-106">Criar uma política</span><span class="sxs-lookup"><span data-stu-id="70603-106">Create a policy</span></span>
1. <span data-ttu-id="70603-107">Vá para Contabilização de custos > Políticas > Políticas de acúmulo de custo.</span><span class="sxs-lookup"><span data-stu-id="70603-107">Go to Cost accounting > Policies > Cost rollup policies.</span></span>
2. <span data-ttu-id="70603-108">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="70603-108">Click New.</span></span>
3. <span data-ttu-id="70603-109">No campo Nome da política, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="70603-109">In the Policy name field, type a value.</span></span>
4. <span data-ttu-id="70603-110">No campo Descrição, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="70603-110">In the Description field, type a value.</span></span>
5. <span data-ttu-id="70603-111">No campo Hierarquia da dimensão de objeto de custo, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="70603-111">In the Cost object dimension hierarchy field, enter or select a value.</span></span>
    * <span data-ttu-id="70603-112">Selecione Acúmulo de custo CC.</span><span class="sxs-lookup"><span data-stu-id="70603-112">Select Cost rollup CC.</span></span>  
6. <span data-ttu-id="70603-113">No campo Hierarquia da dimensão de elemento de custo, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="70603-113">In the Cost element dimension hierarchy field, enter or select a value.</span></span>
    * <span data-ttu-id="70603-114">Selecione Acúmulo de custo CC.</span><span class="sxs-lookup"><span data-stu-id="70603-114">Select Cost rollup CC.</span></span>  
7. <span data-ttu-id="70603-115">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="70603-115">Click Save.</span></span>

## <a name="create-rules-for-the-cost-rollup-policy"></a><span data-ttu-id="70603-116">Criar regras para a política</span><span class="sxs-lookup"><span data-stu-id="70603-116">Create rules for the cost rollup policy</span></span>
1. <span data-ttu-id="70603-117">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="70603-117">Click New.</span></span>
2. <span data-ttu-id="70603-118">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="70603-118">In the list, mark the selected row.</span></span>
3. <span data-ttu-id="70603-119">No campo Nó da hierarquia da dimensão de objeto de custo, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="70603-119">In the Cost object dimension hierarchy node field, enter or select a value.</span></span>
    * <span data-ttu-id="70603-120">Selecione 007.</span><span class="sxs-lookup"><span data-stu-id="70603-120">Select 007.</span></span>  
4. <span data-ttu-id="70603-121">No campo Nó da hierarquia da dimensão de elemento de custo, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="70603-121">In the Cost element dimension hierarchy node field, enter or select a value.</span></span>
    * <span data-ttu-id="70603-122">Selecione Acúmulo de custo CE.</span><span class="sxs-lookup"><span data-stu-id="70603-122">Select Cost rollup CE.</span></span>  
5. <span data-ttu-id="70603-123">No campo Elemento de custo secundário, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="70603-123">In the Secondary cost element field, enter or select a value.</span></span>
    * <span data-ttu-id="70603-124">Para este exemplo, mapeie o elemento de custo secundário CC-007 para o centro de custo.</span><span class="sxs-lookup"><span data-stu-id="70603-124">For this example, map the secondary cost element CC-007 to the cost center.</span></span>  
6. <span data-ttu-id="70603-125">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="70603-125">Click New.</span></span>
7. <span data-ttu-id="70603-126">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="70603-126">In the list, mark the selected row.</span></span>
8. <span data-ttu-id="70603-127">No campo Nó da hierarquia da dimensão de objeto de custo, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="70603-127">In the Cost object dimension hierarchy node field, enter or select a value.</span></span>
    * <span data-ttu-id="70603-128">Selecione 008.</span><span class="sxs-lookup"><span data-stu-id="70603-128">Select 008.</span></span>  
9. <span data-ttu-id="70603-129">No campo Nó da hierarquia da dimensão de elemento de custo, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="70603-129">In the Cost element dimension hierarchy node field, enter or select a value.</span></span>
    * <span data-ttu-id="70603-130">Selecione Acúmulo de custo CE.</span><span class="sxs-lookup"><span data-stu-id="70603-130">Select Cost rollup CE.</span></span>  
10. <span data-ttu-id="70603-131">No campo Elemento de custo secundário, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="70603-131">In the Secondary cost element field, enter or select a value.</span></span>
    * <span data-ttu-id="70603-132">Para este exemplo, mapeie o elemento de custo secundário CC-008 para o centro de custo.</span><span class="sxs-lookup"><span data-stu-id="70603-132">For this example, map the secondary cost element CC-008 to the cost center.</span></span>  
11. <span data-ttu-id="70603-133">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="70603-133">Click New.</span></span>
12. <span data-ttu-id="70603-134">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="70603-134">In the list, mark the selected row.</span></span>
13. <span data-ttu-id="70603-135">No campo Nó da hierarquia da dimensão de objeto de custo, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="70603-135">In the Cost object dimension hierarchy node field, enter or select a value.</span></span>
    * <span data-ttu-id="70603-136">Selecione 009.</span><span class="sxs-lookup"><span data-stu-id="70603-136">Select 009.</span></span>  
14. <span data-ttu-id="70603-137">No campo Nó da hierarquia da dimensão de elemento de custo, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="70603-137">In the Cost element dimension hierarchy node field, enter or select a value.</span></span>
    * <span data-ttu-id="70603-138">Selecione Acúmulo de custo CE.</span><span class="sxs-lookup"><span data-stu-id="70603-138">Select Cost rollup CE.</span></span>  
15. <span data-ttu-id="70603-139">No campo Elemento de custo secundário, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="70603-139">In the Secondary cost element field, enter or select a value.</span></span>
    * <span data-ttu-id="70603-140">Para este exemplo, mapeie o elemento de custo secundário CC-009 para o centro de custo.</span><span class="sxs-lookup"><span data-stu-id="70603-140">For this example, map the secondary cost element CC-009 to the cost center.</span></span>  
    * <span data-ttu-id="70603-141">Continue até todos os centros de custos serem mapeados aos elementos de custo secundários correspondentes.</span><span class="sxs-lookup"><span data-stu-id="70603-141">Continue until all cost centers are mapped to their corresponding secondary cost elements.</span></span>  
16. <span data-ttu-id="70603-142">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="70603-142">Click Save.</span></span>


