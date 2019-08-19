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
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 2f0422a9aaf95184b556293bf6ebcaf4dcfb5b59
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/01/2019
ms.locfileid: "1841384"
---
# <a name="create-and-assign-a-cost-allocation-policy-to-a-cost-control-unit"></a><span data-ttu-id="2754d-103">Criar e atribuir uma política de alocação de custos para uma unidade de controle de custos</span><span class="sxs-lookup"><span data-stu-id="2754d-103">Create and assign a cost allocation policy to a cost control unit</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="2754d-104">Use esse procedimento para criar e atribuir uma política de alocação de custos e as regras correspondentes para uma unidade de controle de custo.</span><span class="sxs-lookup"><span data-stu-id="2754d-104">Use this procedure to create and assign a cost allocation policy and the corresponding rules to a cost control unit.</span></span> <span data-ttu-id="2754d-105">Esta gravação usa os dados da empresa de demonstração USP2.</span><span class="sxs-lookup"><span data-stu-id="2754d-105">This recording uses the USP2 demo data company.</span></span>


## <a name="create-a-policy"></a><span data-ttu-id="2754d-106">Criar uma política</span><span class="sxs-lookup"><span data-stu-id="2754d-106">Create a policy</span></span>
1. <span data-ttu-id="2754d-107">Vá para Contabilização de custos > Políticas > Políticas de alocação de custos.</span><span class="sxs-lookup"><span data-stu-id="2754d-107">Go to Cost accounting > Policies > Cost allocation policies.</span></span>
2. <span data-ttu-id="2754d-108">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="2754d-108">Click New.</span></span>
3. <span data-ttu-id="2754d-109">No campo Nome da política, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="2754d-109">In the Policy name field, type a value.</span></span>
4. <span data-ttu-id="2754d-110">No campo Hierarquia da dimensão de objeto de custo, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="2754d-110">In the Cost object dimension hierarchy field, enter or select a value.</span></span>
    * <span data-ttu-id="2754d-111">Selecione Organização.</span><span class="sxs-lookup"><span data-stu-id="2754d-111">Select Organization.</span></span>  
5. <span data-ttu-id="2754d-112">No campo Dimensão, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="2754d-112">In the Statistical dimension field, enter or select a value.</span></span>
6. <span data-ttu-id="2754d-113">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="2754d-113">Click Save.</span></span>

## <a name="create-allocation-rules"></a><span data-ttu-id="2754d-114">Criar regras de alocação</span><span class="sxs-lookup"><span data-stu-id="2754d-114">Create allocation rules</span></span>
1. <span data-ttu-id="2754d-115">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="2754d-115">Click New.</span></span>
2. <span data-ttu-id="2754d-116">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="2754d-116">In the list, mark the selected row.</span></span>
3. <span data-ttu-id="2754d-117">No campo Nó da hierarquia da dimensão de objeto de custo, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="2754d-117">In the Cost object dimension hierarchy node field, enter or select a value.</span></span>
4. <span data-ttu-id="2754d-118">No campo Comportamento de custo, selecione 'Total'.</span><span class="sxs-lookup"><span data-stu-id="2754d-118">In the Cost behavior field, select 'Total'.</span></span>
5. <span data-ttu-id="2754d-119">No campo Base de alocação, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="2754d-119">In the Allocation base field, enter or select a value.</span></span>
6. <span data-ttu-id="2754d-120">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="2754d-120">Click New.</span></span>
7. <span data-ttu-id="2754d-121">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="2754d-121">In the list, mark the selected row.</span></span>
8. <span data-ttu-id="2754d-122">No campo Nó da hierarquia da dimensão de objeto de custo, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="2754d-122">In the Cost object dimension hierarchy node field, enter or select a value.</span></span>
9. <span data-ttu-id="2754d-123">No campo Comportamento de custo, selecione 'Total'.</span><span class="sxs-lookup"><span data-stu-id="2754d-123">In the Cost behavior field, select 'Total'.</span></span>
10. <span data-ttu-id="2754d-124">No campo Base de alocação, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="2754d-124">In the Allocation base field, enter or select a value.</span></span>
11. <span data-ttu-id="2754d-125">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="2754d-125">Click New.</span></span>
12. <span data-ttu-id="2754d-126">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="2754d-126">In the list, mark the selected row.</span></span>
13. <span data-ttu-id="2754d-127">No campo Nó da hierarquia da dimensão de objeto de custo, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="2754d-127">In the Cost object dimension hierarchy node field, enter or select a value.</span></span>
14. <span data-ttu-id="2754d-128">No campo Comportamento de custo, selecione 'Total'.</span><span class="sxs-lookup"><span data-stu-id="2754d-128">In the Cost behavior field, select 'Total'.</span></span>
15. <span data-ttu-id="2754d-129">No campo Base de alocação, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="2754d-129">In the Allocation base field, enter or select a value.</span></span>
    * <span data-ttu-id="2754d-130">Continue até criar todas as regras.</span><span class="sxs-lookup"><span data-stu-id="2754d-130">Continue until you've created all the rules.</span></span>  
16. <span data-ttu-id="2754d-131">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="2754d-131">Click Save.</span></span>

## <a name="assign-the-policy-to-a-cost-control-unit"></a><span data-ttu-id="2754d-132">Atribua a política a uma unidade de controle de custo</span><span class="sxs-lookup"><span data-stu-id="2754d-132">Assign the policy to a cost control unit</span></span>
1. <span data-ttu-id="2754d-133">Clique em Atribuições de políticas para unidade de controle de custo.</span><span class="sxs-lookup"><span data-stu-id="2754d-133">Click Policy assignments for cost control unit.</span></span>
2. <span data-ttu-id="2754d-134">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="2754d-134">Click New.</span></span>
3. <span data-ttu-id="2754d-135">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="2754d-135">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="2754d-136">No campo Válido a partir da data contábil, insira uma data.</span><span class="sxs-lookup"><span data-stu-id="2754d-136">In the Valid from accounting date field, enter a date.</span></span>
    * <span data-ttu-id="2754d-137">As regras têm data efetiva.</span><span class="sxs-lookup"><span data-stu-id="2754d-137">The rules are date-effective.</span></span> <span data-ttu-id="2754d-138">Um usuário ou o sistema pode expirar as regras, se uma versão mais recente for criada.</span><span class="sxs-lookup"><span data-stu-id="2754d-138">A user or the system can expire the rules if a newer version is created.</span></span>  
5. <span data-ttu-id="2754d-139">No campo Unidade de controle de custo, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="2754d-139">In the Cost control unit field, enter or select a value.</span></span>
6. <span data-ttu-id="2754d-140">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="2754d-140">Click Save.</span></span>

