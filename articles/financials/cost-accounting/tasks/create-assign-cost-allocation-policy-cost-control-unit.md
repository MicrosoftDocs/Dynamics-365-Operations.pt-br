--- 
title: "Criar e atribuir uma política de alocação de custos para uma unidade de controle de custos"
description: "Use esse procedimento para criar e atribuir uma política de alocação de custos e as regras correspondentes para uma unidade de controle de custo."
author: ShylaThompson
manager: AnnBe
ms.date: 06/28/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 1d98cbff30620256c9d13e7b4a90314db150e33e
ms.openlocfilehash: 92f41eb99b84bbc596e79b413971f9d92f2555b6
ms.contentlocale: pt-br
ms.lasthandoff: 08/07/2018

---
# <a name="create-and-assign-a-cost-allocation-policy-to-a-cost-control-unit"></a><span data-ttu-id="ecb28-103">Criar e atribuir uma política de alocação de custos para uma unidade de controle de custos</span><span class="sxs-lookup"><span data-stu-id="ecb28-103">Create and assign a cost allocation policy to a cost control unit</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="ecb28-104">Use esse procedimento para criar e atribuir uma política de alocação de custos e as regras correspondentes para uma unidade de controle de custo.</span><span class="sxs-lookup"><span data-stu-id="ecb28-104">Use this procedure to create and assign a cost allocation policy and the corresponding rules to a cost control unit.</span></span> <span data-ttu-id="ecb28-105">Esta gravação usa os dados da empresa de demonstração USP2.</span><span class="sxs-lookup"><span data-stu-id="ecb28-105">This recording uses the USP2 demo data company.</span></span>


## <a name="create-a-policy"></a><span data-ttu-id="ecb28-106">Criar uma política</span><span class="sxs-lookup"><span data-stu-id="ecb28-106">Create a policy</span></span>
1. <span data-ttu-id="ecb28-107">Vá para Contabilização de custos > Políticas > Políticas de alocação de custos.</span><span class="sxs-lookup"><span data-stu-id="ecb28-107">Go to Cost accounting > Policies > Cost allocation policies.</span></span>
2. <span data-ttu-id="ecb28-108">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="ecb28-108">Click New.</span></span>
3. <span data-ttu-id="ecb28-109">No campo Nome da política, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="ecb28-109">In the Policy name field, type a value.</span></span>
4. <span data-ttu-id="ecb28-110">No campo Hierarquia da dimensão de objeto de custo, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="ecb28-110">In the Cost object dimension hierarchy field, enter or select a value.</span></span>
    * <span data-ttu-id="ecb28-111">Selecione Organização.</span><span class="sxs-lookup"><span data-stu-id="ecb28-111">Select Organization.</span></span>  
5. <span data-ttu-id="ecb28-112">No campo Dimensão, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="ecb28-112">In the Statistical dimension field, enter or select a value.</span></span>
6. <span data-ttu-id="ecb28-113">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="ecb28-113">Click Save.</span></span>

## <a name="create-allocation-rules"></a><span data-ttu-id="ecb28-114">Criar regras de alocação</span><span class="sxs-lookup"><span data-stu-id="ecb28-114">Create allocation rules</span></span>
1. <span data-ttu-id="ecb28-115">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="ecb28-115">Click New.</span></span>
2. <span data-ttu-id="ecb28-116">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="ecb28-116">In the list, mark the selected row.</span></span>
3. <span data-ttu-id="ecb28-117">No campo Nó da hierarquia da dimensão de objeto de custo, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="ecb28-117">In the Cost object dimension hierarchy node field, enter or select a value.</span></span>
4. <span data-ttu-id="ecb28-118">No campo Comportamento de custo, selecione 'Total'.</span><span class="sxs-lookup"><span data-stu-id="ecb28-118">In the Cost behavior field, select 'Total'.</span></span>
5. <span data-ttu-id="ecb28-119">No campo Base de alocação, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="ecb28-119">In the Allocation base field, enter or select a value.</span></span>
6. <span data-ttu-id="ecb28-120">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="ecb28-120">Click New.</span></span>
7. <span data-ttu-id="ecb28-121">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="ecb28-121">In the list, mark the selected row.</span></span>
8. <span data-ttu-id="ecb28-122">No campo Nó da hierarquia da dimensão de objeto de custo, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="ecb28-122">In the Cost object dimension hierarchy node field, enter or select a value.</span></span>
9. <span data-ttu-id="ecb28-123">No campo Comportamento de custo, selecione 'Total'.</span><span class="sxs-lookup"><span data-stu-id="ecb28-123">In the Cost behavior field, select 'Total'.</span></span>
10. <span data-ttu-id="ecb28-124">No campo Base de alocação, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="ecb28-124">In the Allocation base field, enter or select a value.</span></span>
11. <span data-ttu-id="ecb28-125">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="ecb28-125">Click New.</span></span>
12. <span data-ttu-id="ecb28-126">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="ecb28-126">In the list, mark the selected row.</span></span>
13. <span data-ttu-id="ecb28-127">No campo Nó da hierarquia da dimensão de objeto de custo, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="ecb28-127">In the Cost object dimension hierarchy node field, enter or select a value.</span></span>
14. <span data-ttu-id="ecb28-128">No campo Comportamento de custo, selecione 'Total'.</span><span class="sxs-lookup"><span data-stu-id="ecb28-128">In the Cost behavior field, select 'Total'.</span></span>
15. <span data-ttu-id="ecb28-129">No campo Base de alocação, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="ecb28-129">In the Allocation base field, enter or select a value.</span></span>
    * <span data-ttu-id="ecb28-130">Continue até criar todas as regras.</span><span class="sxs-lookup"><span data-stu-id="ecb28-130">Continue until you've created all the rules.</span></span>  
16. <span data-ttu-id="ecb28-131">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="ecb28-131">Click Save.</span></span>

## <a name="assign-the-policy-to-a-cost-control-unit"></a><span data-ttu-id="ecb28-132">Atribua a política a uma unidade de controle de custo</span><span class="sxs-lookup"><span data-stu-id="ecb28-132">Assign the policy to a cost control unit</span></span>
1. <span data-ttu-id="ecb28-133">Clique em Atribuições de políticas para unidade de controle de custo.</span><span class="sxs-lookup"><span data-stu-id="ecb28-133">Click Policy assignments for cost control unit.</span></span>
2. <span data-ttu-id="ecb28-134">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="ecb28-134">Click New.</span></span>
3. <span data-ttu-id="ecb28-135">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="ecb28-135">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="ecb28-136">No campo Válido a partir da data contábil, insira uma data.</span><span class="sxs-lookup"><span data-stu-id="ecb28-136">In the Valid from accounting date field, enter a date.</span></span>
    * <span data-ttu-id="ecb28-137">As regras têm data efetiva.</span><span class="sxs-lookup"><span data-stu-id="ecb28-137">The rules are date-effective.</span></span> <span data-ttu-id="ecb28-138">Um usuário ou o sistema pode expirar as regras, se uma versão mais recente for criada.</span><span class="sxs-lookup"><span data-stu-id="ecb28-138">A user or the system can expire the rules if a newer version is created.</span></span>  
5. <span data-ttu-id="ecb28-139">No campo Unidade de controle de custo, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="ecb28-139">In the Cost control unit field, enter or select a value.</span></span>
6. <span data-ttu-id="ecb28-140">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="ecb28-140">Click Save.</span></span>


