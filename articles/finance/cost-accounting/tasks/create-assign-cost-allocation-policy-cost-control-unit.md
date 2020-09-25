---
title: Criar e atribuir uma política de alocação de custos para uma unidade de controle de custos
description: Use esse procedimento para criar e atribuir uma política de alocação de custos e as regras correspondentes para uma unidade de controle de custo.
author: ShylaThompson
manager: AnnBe
ms.date: 06/28/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CAMCostAccountingLedgerPolicyAssignment
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 80ec8fed2094025ef31114a229c35bee1cd1033b
ms.sourcegitcommit: cd339f48066b1d0fc740b513cb72ea19015acd16
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/02/2020
ms.locfileid: "3759319"
---
# <a name="create-and-assign-a-cost-allocation-policy-to-a-cost-control-unit"></a><span data-ttu-id="b6e99-103">Criar e atribuir uma política de alocação de custos para uma unidade de controle de custos</span><span class="sxs-lookup"><span data-stu-id="b6e99-103">Create and assign a cost allocation policy to a cost control unit</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="b6e99-104">Use esse procedimento para criar e atribuir uma política de alocação de custos e as regras correspondentes para uma unidade de controle de custo.</span><span class="sxs-lookup"><span data-stu-id="b6e99-104">Use this procedure to create and assign a cost allocation policy and the corresponding rules to a cost control unit.</span></span> <span data-ttu-id="b6e99-105">Esta gravação usa os dados da empresa de demonstração USP2.</span><span class="sxs-lookup"><span data-stu-id="b6e99-105">This recording uses the USP2 demo data company.</span></span>


## <a name="create-a-policy"></a><span data-ttu-id="b6e99-106">Criar uma política</span><span class="sxs-lookup"><span data-stu-id="b6e99-106">Create a policy</span></span>
1. <span data-ttu-id="b6e99-107">Vá para Contabilização de custos > Políticas > Políticas de alocação de custos.</span><span class="sxs-lookup"><span data-stu-id="b6e99-107">Go to Cost accounting > Policies > Cost allocation policies.</span></span>
2. <span data-ttu-id="b6e99-108">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="b6e99-108">Click New.</span></span>
3. <span data-ttu-id="b6e99-109">No campo Nome da política, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="b6e99-109">In the Policy name field, type a value.</span></span>
4. <span data-ttu-id="b6e99-110">No campo Hierarquia da dimensão de objeto de custo, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="b6e99-110">In the Cost object dimension hierarchy field, enter or select a value.</span></span>
    * <span data-ttu-id="b6e99-111">Selecione Organização.</span><span class="sxs-lookup"><span data-stu-id="b6e99-111">Select Organization.</span></span>  
5. <span data-ttu-id="b6e99-112">No campo Dimensão, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="b6e99-112">In the Statistical dimension field, enter or select a value.</span></span>
6. <span data-ttu-id="b6e99-113">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="b6e99-113">Click Save.</span></span>

## <a name="create-allocation-rules"></a><span data-ttu-id="b6e99-114">Criar regras de alocação</span><span class="sxs-lookup"><span data-stu-id="b6e99-114">Create allocation rules</span></span>
1. <span data-ttu-id="b6e99-115">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="b6e99-115">Click New.</span></span>
2. <span data-ttu-id="b6e99-116">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="b6e99-116">In the list, mark the selected row.</span></span>
3. <span data-ttu-id="b6e99-117">No campo Nó da hierarquia da dimensão de objeto de custo, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="b6e99-117">In the Cost object dimension hierarchy node field, enter or select a value.</span></span>
4. <span data-ttu-id="b6e99-118">No campo Comportamento de custo, selecione 'Total'.</span><span class="sxs-lookup"><span data-stu-id="b6e99-118">In the Cost behavior field, select 'Total'.</span></span>
5. <span data-ttu-id="b6e99-119">No campo Base de alocação, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="b6e99-119">In the Allocation base field, enter or select a value.</span></span>
6. <span data-ttu-id="b6e99-120">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="b6e99-120">Click New.</span></span>
7. <span data-ttu-id="b6e99-121">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="b6e99-121">In the list, mark the selected row.</span></span>
8. <span data-ttu-id="b6e99-122">No campo Nó da hierarquia da dimensão de objeto de custo, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="b6e99-122">In the Cost object dimension hierarchy node field, enter or select a value.</span></span>
9. <span data-ttu-id="b6e99-123">No campo Comportamento de custo, selecione 'Total'.</span><span class="sxs-lookup"><span data-stu-id="b6e99-123">In the Cost behavior field, select 'Total'.</span></span>
10. <span data-ttu-id="b6e99-124">No campo Base de alocação, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="b6e99-124">In the Allocation base field, enter or select a value.</span></span>
11. <span data-ttu-id="b6e99-125">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="b6e99-125">Click New.</span></span>
12. <span data-ttu-id="b6e99-126">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="b6e99-126">In the list, mark the selected row.</span></span>
13. <span data-ttu-id="b6e99-127">No campo Nó da hierarquia da dimensão de objeto de custo, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="b6e99-127">In the Cost object dimension hierarchy node field, enter or select a value.</span></span>
14. <span data-ttu-id="b6e99-128">No campo Comportamento de custo, selecione 'Total'.</span><span class="sxs-lookup"><span data-stu-id="b6e99-128">In the Cost behavior field, select 'Total'.</span></span>
15. <span data-ttu-id="b6e99-129">No campo Base de alocação, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="b6e99-129">In the Allocation base field, enter or select a value.</span></span>
    * <span data-ttu-id="b6e99-130">Continue até criar todas as regras.</span><span class="sxs-lookup"><span data-stu-id="b6e99-130">Continue until you've created all the rules.</span></span>  
16. <span data-ttu-id="b6e99-131">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="b6e99-131">Click Save.</span></span>

## <a name="assign-the-policy-to-a-cost-control-unit"></a><span data-ttu-id="b6e99-132">Atribua a política a uma unidade de controle de custo</span><span class="sxs-lookup"><span data-stu-id="b6e99-132">Assign the policy to a cost control unit</span></span>
1. <span data-ttu-id="b6e99-133">Clique em Atribuições de políticas para unidade de controle de custo.</span><span class="sxs-lookup"><span data-stu-id="b6e99-133">Click Policy assignments for cost control unit.</span></span>
2. <span data-ttu-id="b6e99-134">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="b6e99-134">Click New.</span></span>
3. <span data-ttu-id="b6e99-135">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="b6e99-135">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="b6e99-136">No campo Válido a partir da data contábil, insira uma data.</span><span class="sxs-lookup"><span data-stu-id="b6e99-136">In the Valid from accounting date field, enter a date.</span></span>
    * <span data-ttu-id="b6e99-137">As regras têm data efetiva.</span><span class="sxs-lookup"><span data-stu-id="b6e99-137">The rules are date-effective.</span></span> <span data-ttu-id="b6e99-138">Um usuário ou o sistema pode expirar as regras, se uma versão mais recente for criada.</span><span class="sxs-lookup"><span data-stu-id="b6e99-138">A user or the system can expire the rules if a newer version is created.</span></span>  
5. <span data-ttu-id="b6e99-139">No campo Unidade de controle de custo, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="b6e99-139">In the Cost control unit field, enter or select a value.</span></span>
6. <span data-ttu-id="b6e99-140">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="b6e99-140">Click Save.</span></span>

