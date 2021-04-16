---
title: Criar e atribuir uma política de alocação de custos para uma unidade de controle de custos
description: Use esse procedimento para criar e atribuir uma política de alocação de custos e as regras correspondentes para uma unidade de controle de custo.
author: ShylaThompson
ms.date: 06/28/2017
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: CAMCostAccountingLedgerPolicyAssignment
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1cff10132e8007be885e9c69d97cf96c30d69f50
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5822846"
---
# <a name="create-and-assign-a-cost-allocation-policy-to-a-cost-control-unit"></a><span data-ttu-id="0e0b7-103">Criar e atribuir uma política de alocação de custos para uma unidade de controle de custos</span><span class="sxs-lookup"><span data-stu-id="0e0b7-103">Create and assign a cost allocation policy to a cost control unit</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="0e0b7-104">Use esse procedimento para criar e atribuir uma política de alocação de custos e as regras correspondentes para uma unidade de controle de custo.</span><span class="sxs-lookup"><span data-stu-id="0e0b7-104">Use this procedure to create and assign a cost allocation policy and the corresponding rules to a cost control unit.</span></span> <span data-ttu-id="0e0b7-105">Esta gravação usa os dados da empresa de demonstração USP2.</span><span class="sxs-lookup"><span data-stu-id="0e0b7-105">This recording uses the USP2 demo data company.</span></span>


## <a name="create-a-policy"></a><span data-ttu-id="0e0b7-106">Criar uma política</span><span class="sxs-lookup"><span data-stu-id="0e0b7-106">Create a policy</span></span>
1. <span data-ttu-id="0e0b7-107">Vá para Contabilização de custos > Políticas > Políticas de alocação de custos.</span><span class="sxs-lookup"><span data-stu-id="0e0b7-107">Go to Cost accounting > Policies > Cost allocation policies.</span></span>
2. <span data-ttu-id="0e0b7-108">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="0e0b7-108">Click New.</span></span>
3. <span data-ttu-id="0e0b7-109">No campo Nome da política, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="0e0b7-109">In the Policy name field, type a value.</span></span>
4. <span data-ttu-id="0e0b7-110">No campo Hierarquia da dimensão de objeto de custo, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="0e0b7-110">In the Cost object dimension hierarchy field, enter or select a value.</span></span>
    * <span data-ttu-id="0e0b7-111">Selecione Organização.</span><span class="sxs-lookup"><span data-stu-id="0e0b7-111">Select Organization.</span></span>  
5. <span data-ttu-id="0e0b7-112">No campo Dimensão, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="0e0b7-112">In the Statistical dimension field, enter or select a value.</span></span>
6. <span data-ttu-id="0e0b7-113">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="0e0b7-113">Click Save.</span></span>

## <a name="create-allocation-rules"></a><span data-ttu-id="0e0b7-114">Criar regras de alocação</span><span class="sxs-lookup"><span data-stu-id="0e0b7-114">Create allocation rules</span></span>
1. <span data-ttu-id="0e0b7-115">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="0e0b7-115">Click New.</span></span>
2. <span data-ttu-id="0e0b7-116">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="0e0b7-116">In the list, mark the selected row.</span></span>
3. <span data-ttu-id="0e0b7-117">No campo Nó da hierarquia da dimensão de objeto de custo, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="0e0b7-117">In the Cost object dimension hierarchy node field, enter or select a value.</span></span>
4. <span data-ttu-id="0e0b7-118">No campo Comportamento de custo, selecione 'Total'.</span><span class="sxs-lookup"><span data-stu-id="0e0b7-118">In the Cost behavior field, select 'Total'.</span></span>
5. <span data-ttu-id="0e0b7-119">No campo Base de alocação, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="0e0b7-119">In the Allocation base field, enter or select a value.</span></span>
6. <span data-ttu-id="0e0b7-120">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="0e0b7-120">Click New.</span></span>
7. <span data-ttu-id="0e0b7-121">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="0e0b7-121">In the list, mark the selected row.</span></span>
8. <span data-ttu-id="0e0b7-122">No campo Nó da hierarquia da dimensão de objeto de custo, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="0e0b7-122">In the Cost object dimension hierarchy node field, enter or select a value.</span></span>
9. <span data-ttu-id="0e0b7-123">No campo Comportamento de custo, selecione 'Total'.</span><span class="sxs-lookup"><span data-stu-id="0e0b7-123">In the Cost behavior field, select 'Total'.</span></span>
10. <span data-ttu-id="0e0b7-124">No campo Base de alocação, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="0e0b7-124">In the Allocation base field, enter or select a value.</span></span>
11. <span data-ttu-id="0e0b7-125">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="0e0b7-125">Click New.</span></span>
12. <span data-ttu-id="0e0b7-126">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="0e0b7-126">In the list, mark the selected row.</span></span>
13. <span data-ttu-id="0e0b7-127">No campo Nó da hierarquia da dimensão de objeto de custo, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="0e0b7-127">In the Cost object dimension hierarchy node field, enter or select a value.</span></span>
14. <span data-ttu-id="0e0b7-128">No campo Comportamento de custo, selecione 'Total'.</span><span class="sxs-lookup"><span data-stu-id="0e0b7-128">In the Cost behavior field, select 'Total'.</span></span>
15. <span data-ttu-id="0e0b7-129">No campo Base de alocação, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="0e0b7-129">In the Allocation base field, enter or select a value.</span></span>
    * <span data-ttu-id="0e0b7-130">Continue até criar todas as regras.</span><span class="sxs-lookup"><span data-stu-id="0e0b7-130">Continue until you've created all the rules.</span></span>  
16. <span data-ttu-id="0e0b7-131">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="0e0b7-131">Click Save.</span></span>

## <a name="assign-the-policy-to-a-cost-control-unit"></a><span data-ttu-id="0e0b7-132">Atribua a política a uma unidade de controle de custo</span><span class="sxs-lookup"><span data-stu-id="0e0b7-132">Assign the policy to a cost control unit</span></span>
1. <span data-ttu-id="0e0b7-133">Clique em Atribuições de políticas para unidade de controle de custo.</span><span class="sxs-lookup"><span data-stu-id="0e0b7-133">Click Policy assignments for cost control unit.</span></span>
2. <span data-ttu-id="0e0b7-134">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="0e0b7-134">Click New.</span></span>
3. <span data-ttu-id="0e0b7-135">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="0e0b7-135">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="0e0b7-136">No campo Válido a partir da data contábil, insira uma data.</span><span class="sxs-lookup"><span data-stu-id="0e0b7-136">In the Valid from accounting date field, enter a date.</span></span>
    * <span data-ttu-id="0e0b7-137">As regras têm data efetiva.</span><span class="sxs-lookup"><span data-stu-id="0e0b7-137">The rules are date-effective.</span></span> <span data-ttu-id="0e0b7-138">Um usuário ou o sistema pode expirar as regras, se uma versão mais recente for criada.</span><span class="sxs-lookup"><span data-stu-id="0e0b7-138">A user or the system can expire the rules if a newer version is created.</span></span>  
5. <span data-ttu-id="0e0b7-139">No campo Unidade de controle de custo, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="0e0b7-139">In the Cost control unit field, enter or select a value.</span></span>
6. <span data-ttu-id="0e0b7-140">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="0e0b7-140">Click Save.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]