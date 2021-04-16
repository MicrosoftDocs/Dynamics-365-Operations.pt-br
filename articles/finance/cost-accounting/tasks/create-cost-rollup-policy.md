---
title: Criar uma política de acúmulo de custo
description: Este procedimento mostra como criar uma política de acúmulo de custo e criar regras para a política.
author: ShylaThompson
ms.date: 06/27/2017
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 50a50dc359dc4c2741ac4d280a9f97c6a7f2c259
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5810004"
---
# <a name="create-a-cost-rollup-policy"></a><span data-ttu-id="7fc59-103">Criar uma política de acúmulo de custo</span><span class="sxs-lookup"><span data-stu-id="7fc59-103">Create a cost rollup policy</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="7fc59-104">Este procedimento mostra como criar uma política de acúmulo de custo e criar regras para a política.</span><span class="sxs-lookup"><span data-stu-id="7fc59-104">This procedure shows how to create a cost rollup policy and create rules for the policy.</span></span> <span data-ttu-id="7fc59-105">Os dados demonstrativos utilizados na criação desse procedimento são do conjunto USP2.</span><span class="sxs-lookup"><span data-stu-id="7fc59-105">The demo data used to create this procedure is USP2.</span></span>


## <a name="create-a-policy"></a><span data-ttu-id="7fc59-106">Criar uma política</span><span class="sxs-lookup"><span data-stu-id="7fc59-106">Create a policy</span></span>
1. <span data-ttu-id="7fc59-107">Vá para Contabilização de custos > Políticas > Políticas de acúmulo de custo.</span><span class="sxs-lookup"><span data-stu-id="7fc59-107">Go to Cost accounting > Policies > Cost rollup policies.</span></span>
2. <span data-ttu-id="7fc59-108">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="7fc59-108">Click New.</span></span>
3. <span data-ttu-id="7fc59-109">No campo Nome da política, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="7fc59-109">In the Policy name field, type a value.</span></span>
4. <span data-ttu-id="7fc59-110">No campo Descrição, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="7fc59-110">In the Description field, type a value.</span></span>
5. <span data-ttu-id="7fc59-111">No campo Hierarquia da dimensão de objeto de custo, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="7fc59-111">In the Cost object dimension hierarchy field, enter or select a value.</span></span>
    * <span data-ttu-id="7fc59-112">Selecione Acúmulo de custo CC.</span><span class="sxs-lookup"><span data-stu-id="7fc59-112">Select Cost rollup CC.</span></span>  
6. <span data-ttu-id="7fc59-113">No campo Hierarquia da dimensão de elemento de custo, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="7fc59-113">In the Cost element dimension hierarchy field, enter or select a value.</span></span>
    * <span data-ttu-id="7fc59-114">Selecione Acúmulo de custo CC.</span><span class="sxs-lookup"><span data-stu-id="7fc59-114">Select Cost rollup CC.</span></span>  
7. <span data-ttu-id="7fc59-115">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="7fc59-115">Click Save.</span></span>

## <a name="create-rules-for-the-cost-rollup-policy"></a><span data-ttu-id="7fc59-116">Criar regras para a política</span><span class="sxs-lookup"><span data-stu-id="7fc59-116">Create rules for the cost rollup policy</span></span>
1. <span data-ttu-id="7fc59-117">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="7fc59-117">Click New.</span></span>
2. <span data-ttu-id="7fc59-118">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="7fc59-118">In the list, mark the selected row.</span></span>
3. <span data-ttu-id="7fc59-119">No campo Nó da hierarquia da dimensão de objeto de custo, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="7fc59-119">In the Cost object dimension hierarchy node field, enter or select a value.</span></span>
    * <span data-ttu-id="7fc59-120">Selecione 007.</span><span class="sxs-lookup"><span data-stu-id="7fc59-120">Select 007.</span></span>  
4. <span data-ttu-id="7fc59-121">No campo Nó da hierarquia da dimensão de elemento de custo, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="7fc59-121">In the Cost element dimension hierarchy node field, enter or select a value.</span></span>
    * <span data-ttu-id="7fc59-122">Selecione Acúmulo de custo CE.</span><span class="sxs-lookup"><span data-stu-id="7fc59-122">Select Cost rollup CE.</span></span>  
5. <span data-ttu-id="7fc59-123">No campo Elemento de custo secundário, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="7fc59-123">In the Secondary cost element field, enter or select a value.</span></span>
    * <span data-ttu-id="7fc59-124">Para este exemplo, mapeie o elemento de custo secundário CC-007 para o centro de custo.</span><span class="sxs-lookup"><span data-stu-id="7fc59-124">For this example, map the secondary cost element CC-007 to the cost center.</span></span>  
6. <span data-ttu-id="7fc59-125">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="7fc59-125">Click New.</span></span>
7. <span data-ttu-id="7fc59-126">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="7fc59-126">In the list, mark the selected row.</span></span>
8. <span data-ttu-id="7fc59-127">No campo Nó da hierarquia da dimensão de objeto de custo, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="7fc59-127">In the Cost object dimension hierarchy node field, enter or select a value.</span></span>
    * <span data-ttu-id="7fc59-128">Selecione 008.</span><span class="sxs-lookup"><span data-stu-id="7fc59-128">Select 008.</span></span>  
9. <span data-ttu-id="7fc59-129">No campo Nó da hierarquia da dimensão de elemento de custo, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="7fc59-129">In the Cost element dimension hierarchy node field, enter or select a value.</span></span>
    * <span data-ttu-id="7fc59-130">Selecione Acúmulo de custo CE.</span><span class="sxs-lookup"><span data-stu-id="7fc59-130">Select Cost rollup CE.</span></span>  
10. <span data-ttu-id="7fc59-131">No campo Elemento de custo secundário, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="7fc59-131">In the Secondary cost element field, enter or select a value.</span></span>
    * <span data-ttu-id="7fc59-132">Para este exemplo, mapeie o elemento de custo secundário CC-008 para o centro de custo.</span><span class="sxs-lookup"><span data-stu-id="7fc59-132">For this example, map the secondary cost element CC-008 to the cost center.</span></span>  
11. <span data-ttu-id="7fc59-133">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="7fc59-133">Click New.</span></span>
12. <span data-ttu-id="7fc59-134">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="7fc59-134">In the list, mark the selected row.</span></span>
13. <span data-ttu-id="7fc59-135">No campo Nó da hierarquia da dimensão de objeto de custo, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="7fc59-135">In the Cost object dimension hierarchy node field, enter or select a value.</span></span>
    * <span data-ttu-id="7fc59-136">Selecione 009.</span><span class="sxs-lookup"><span data-stu-id="7fc59-136">Select 009.</span></span>  
14. <span data-ttu-id="7fc59-137">No campo Nó da hierarquia da dimensão de elemento de custo, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="7fc59-137">In the Cost element dimension hierarchy node field, enter or select a value.</span></span>
    * <span data-ttu-id="7fc59-138">Selecione Acúmulo de custo CE.</span><span class="sxs-lookup"><span data-stu-id="7fc59-138">Select Cost rollup CE.</span></span>  
15. <span data-ttu-id="7fc59-139">No campo Elemento de custo secundário, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="7fc59-139">In the Secondary cost element field, enter or select a value.</span></span>
    * <span data-ttu-id="7fc59-140">Para este exemplo, mapeie o elemento de custo secundário CC-009 para o centro de custo.</span><span class="sxs-lookup"><span data-stu-id="7fc59-140">For this example, map the secondary cost element CC-009 to the cost center.</span></span>  
    * <span data-ttu-id="7fc59-141">Continue até todos os centros de custos serem mapeados aos elementos de custo secundários correspondentes.</span><span class="sxs-lookup"><span data-stu-id="7fc59-141">Continue until all cost centers are mapped to their corresponding secondary cost elements.</span></span>  
16. <span data-ttu-id="7fc59-142">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="7fc59-142">Click Save.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]