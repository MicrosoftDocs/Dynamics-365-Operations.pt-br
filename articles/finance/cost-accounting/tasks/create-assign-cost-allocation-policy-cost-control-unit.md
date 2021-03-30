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
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b22dba0106721c095e6ce2e9b76cb9f5267e1c28
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5208718"
---
# <a name="create-and-assign-a-cost-allocation-policy-to-a-cost-control-unit"></a><span data-ttu-id="a89c8-103">Criar e atribuir uma política de alocação de custos para uma unidade de controle de custos</span><span class="sxs-lookup"><span data-stu-id="a89c8-103">Create and assign a cost allocation policy to a cost control unit</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="a89c8-104">Use esse procedimento para criar e atribuir uma política de alocação de custos e as regras correspondentes para uma unidade de controle de custo.</span><span class="sxs-lookup"><span data-stu-id="a89c8-104">Use this procedure to create and assign a cost allocation policy and the corresponding rules to a cost control unit.</span></span> <span data-ttu-id="a89c8-105">Esta gravação usa os dados da empresa de demonstração USP2.</span><span class="sxs-lookup"><span data-stu-id="a89c8-105">This recording uses the USP2 demo data company.</span></span>


## <a name="create-a-policy"></a><span data-ttu-id="a89c8-106">Criar uma política</span><span class="sxs-lookup"><span data-stu-id="a89c8-106">Create a policy</span></span>
1. <span data-ttu-id="a89c8-107">Vá para Contabilização de custos > Políticas > Políticas de alocação de custos.</span><span class="sxs-lookup"><span data-stu-id="a89c8-107">Go to Cost accounting > Policies > Cost allocation policies.</span></span>
2. <span data-ttu-id="a89c8-108">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="a89c8-108">Click New.</span></span>
3. <span data-ttu-id="a89c8-109">No campo Nome da política, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="a89c8-109">In the Policy name field, type a value.</span></span>
4. <span data-ttu-id="a89c8-110">No campo Hierarquia da dimensão de objeto de custo, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="a89c8-110">In the Cost object dimension hierarchy field, enter or select a value.</span></span>
    * <span data-ttu-id="a89c8-111">Selecione Organização.</span><span class="sxs-lookup"><span data-stu-id="a89c8-111">Select Organization.</span></span>  
5. <span data-ttu-id="a89c8-112">No campo Dimensão, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="a89c8-112">In the Statistical dimension field, enter or select a value.</span></span>
6. <span data-ttu-id="a89c8-113">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="a89c8-113">Click Save.</span></span>

## <a name="create-allocation-rules"></a><span data-ttu-id="a89c8-114">Criar regras de alocação</span><span class="sxs-lookup"><span data-stu-id="a89c8-114">Create allocation rules</span></span>
1. <span data-ttu-id="a89c8-115">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="a89c8-115">Click New.</span></span>
2. <span data-ttu-id="a89c8-116">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="a89c8-116">In the list, mark the selected row.</span></span>
3. <span data-ttu-id="a89c8-117">No campo Nó da hierarquia da dimensão de objeto de custo, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="a89c8-117">In the Cost object dimension hierarchy node field, enter or select a value.</span></span>
4. <span data-ttu-id="a89c8-118">No campo Comportamento de custo, selecione 'Total'.</span><span class="sxs-lookup"><span data-stu-id="a89c8-118">In the Cost behavior field, select 'Total'.</span></span>
5. <span data-ttu-id="a89c8-119">No campo Base de alocação, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="a89c8-119">In the Allocation base field, enter or select a value.</span></span>
6. <span data-ttu-id="a89c8-120">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="a89c8-120">Click New.</span></span>
7. <span data-ttu-id="a89c8-121">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="a89c8-121">In the list, mark the selected row.</span></span>
8. <span data-ttu-id="a89c8-122">No campo Nó da hierarquia da dimensão de objeto de custo, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="a89c8-122">In the Cost object dimension hierarchy node field, enter or select a value.</span></span>
9. <span data-ttu-id="a89c8-123">No campo Comportamento de custo, selecione 'Total'.</span><span class="sxs-lookup"><span data-stu-id="a89c8-123">In the Cost behavior field, select 'Total'.</span></span>
10. <span data-ttu-id="a89c8-124">No campo Base de alocação, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="a89c8-124">In the Allocation base field, enter or select a value.</span></span>
11. <span data-ttu-id="a89c8-125">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="a89c8-125">Click New.</span></span>
12. <span data-ttu-id="a89c8-126">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="a89c8-126">In the list, mark the selected row.</span></span>
13. <span data-ttu-id="a89c8-127">No campo Nó da hierarquia da dimensão de objeto de custo, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="a89c8-127">In the Cost object dimension hierarchy node field, enter or select a value.</span></span>
14. <span data-ttu-id="a89c8-128">No campo Comportamento de custo, selecione 'Total'.</span><span class="sxs-lookup"><span data-stu-id="a89c8-128">In the Cost behavior field, select 'Total'.</span></span>
15. <span data-ttu-id="a89c8-129">No campo Base de alocação, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="a89c8-129">In the Allocation base field, enter or select a value.</span></span>
    * <span data-ttu-id="a89c8-130">Continue até criar todas as regras.</span><span class="sxs-lookup"><span data-stu-id="a89c8-130">Continue until you've created all the rules.</span></span>  
16. <span data-ttu-id="a89c8-131">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="a89c8-131">Click Save.</span></span>

## <a name="assign-the-policy-to-a-cost-control-unit"></a><span data-ttu-id="a89c8-132">Atribua a política a uma unidade de controle de custo</span><span class="sxs-lookup"><span data-stu-id="a89c8-132">Assign the policy to a cost control unit</span></span>
1. <span data-ttu-id="a89c8-133">Clique em Atribuições de políticas para unidade de controle de custo.</span><span class="sxs-lookup"><span data-stu-id="a89c8-133">Click Policy assignments for cost control unit.</span></span>
2. <span data-ttu-id="a89c8-134">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="a89c8-134">Click New.</span></span>
3. <span data-ttu-id="a89c8-135">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="a89c8-135">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="a89c8-136">No campo Válido a partir da data contábil, insira uma data.</span><span class="sxs-lookup"><span data-stu-id="a89c8-136">In the Valid from accounting date field, enter a date.</span></span>
    * <span data-ttu-id="a89c8-137">As regras têm data efetiva.</span><span class="sxs-lookup"><span data-stu-id="a89c8-137">The rules are date-effective.</span></span> <span data-ttu-id="a89c8-138">Um usuário ou o sistema pode expirar as regras, se uma versão mais recente for criada.</span><span class="sxs-lookup"><span data-stu-id="a89c8-138">A user or the system can expire the rules if a newer version is created.</span></span>  
5. <span data-ttu-id="a89c8-139">No campo Unidade de controle de custo, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="a89c8-139">In the Cost control unit field, enter or select a value.</span></span>
6. <span data-ttu-id="a89c8-140">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="a89c8-140">Click Save.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]