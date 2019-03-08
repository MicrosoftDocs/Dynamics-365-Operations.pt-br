---
title: Criar e atribuir uma política de distribuição de custos para uma unidade de controle de custos
description: As regras de distribuição de custos são usadas para distribuir custos que foram contados financeiramente em um centro de custos coletivo.
author: ShylaThompson
manager: AnnBe
ms.date: 06/27/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 46ba6322f2cea7828033c214502accdf73f073be
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2019
ms.locfileid: "308451"
---
# <a name="create-and-assign-a-cost-distribution-policy-to-a-cost-control-unit"></a><span data-ttu-id="3db60-103">Criar e atribuir uma política de distribuição de custos para uma unidade de controle de custos</span><span class="sxs-lookup"><span data-stu-id="3db60-103">Create and assign a cost distribution policy to a cost control unit</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="3db60-104">As regras de distribuição de custos são usadas para distribuir custos que foram contados financeiramente em um centro de custos coletivo.</span><span class="sxs-lookup"><span data-stu-id="3db60-104">Cost distribution rules are used to distribute costs that have been financially counted on a collective cost center.</span></span> <span data-ttu-id="3db60-105">O contador de custos garante que o custo é distribuído para os centros de custos, de acordo com a base de alocação selecionada.</span><span class="sxs-lookup"><span data-stu-id="3db60-105">The cost accountant makes sure that the cost is distributed to the cost centers, based on the selected allocation base.</span></span> <span data-ttu-id="3db60-106">Uma política e as regras correspondentes são atribuídas a uma unidade de controle de custo.</span><span class="sxs-lookup"><span data-stu-id="3db60-106">A policy and the corresponding rules are assigned to a cost control unit.</span></span> <span data-ttu-id="3db60-107">Este guia de tarefas usa um exemplo para mostrar como criar uma política de distribuição de custos e as regras correspondentes.</span><span class="sxs-lookup"><span data-stu-id="3db60-107">This task guide uses an example to show how to create a cost distribution policy and the corresponding rules.</span></span>


## <a name="create-a-policy"></a><span data-ttu-id="3db60-108">Criar uma política</span><span class="sxs-lookup"><span data-stu-id="3db60-108">Create a policy</span></span>
1. <span data-ttu-id="3db60-109">Vá para Contabilização de custos > Políticas > Políticas de distribuição de custos.</span><span class="sxs-lookup"><span data-stu-id="3db60-109">Go to Cost accounting > Policies > Cost distribution policies.</span></span>
2. <span data-ttu-id="3db60-110">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="3db60-110">Click New.</span></span>
3. <span data-ttu-id="3db60-111">No campo Nome da política, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="3db60-111">In the Policy name field, type a value.</span></span>
4. <span data-ttu-id="3db60-112">No campo Descrição, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="3db60-112">In the Description field, type a value.</span></span>
5. <span data-ttu-id="3db60-113">No campo Hierarquia da dimensão de objeto de custo, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="3db60-113">In the Cost object dimension hierarchy field, enter or select a value.</span></span>
    * <span data-ttu-id="3db60-114">Selecione Organização.</span><span class="sxs-lookup"><span data-stu-id="3db60-114">Select Organization.</span></span>  
6. <span data-ttu-id="3db60-115">No campo Hierarquia da dimensão de elemento de custo, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="3db60-115">In the Cost element dimension hierarchy field, enter or select a value.</span></span>
    * <span data-ttu-id="3db60-116">Selecione CDS P/L.</span><span class="sxs-lookup"><span data-stu-id="3db60-116">Select CDS P/L.</span></span>  
7. <span data-ttu-id="3db60-117">No campo Dimensão, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="3db60-117">In the Statistical dimension field, enter or select a value.</span></span>
    * <span data-ttu-id="3db60-118">Selecione Elementos estatísticos.</span><span class="sxs-lookup"><span data-stu-id="3db60-118">Select Statistical elements.</span></span>  
8. <span data-ttu-id="3db60-119">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="3db60-119">Click Save.</span></span>

## <a name="create-rules-for-the-policy"></a><span data-ttu-id="3db60-120">Criar regras para a política</span><span class="sxs-lookup"><span data-stu-id="3db60-120">Create rules for the policy</span></span>
1. <span data-ttu-id="3db60-121">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="3db60-121">Click New.</span></span>
2. <span data-ttu-id="3db60-122">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="3db60-122">In the list, mark the selected row.</span></span>
3. <span data-ttu-id="3db60-123">No campo Nó da hierarquia da dimensão de objeto de custo, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="3db60-123">In the Cost object dimension hierarchy node field, enter or select a value.</span></span>
    * <span data-ttu-id="3db60-124">Expanda a hierarquia para selecionar 094.</span><span class="sxs-lookup"><span data-stu-id="3db60-124">Expand the hierarchy to select 094.</span></span>  
4. <span data-ttu-id="3db60-125">No campo Nó da hierarquia da dimensão de elemento de custo, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="3db60-125">In the Cost element dimension hierarchy node field, enter or select a value.</span></span>
    * <span data-ttu-id="3db60-126">Selecione Outras despesas operacionais e depois 605110 Limpeza.</span><span class="sxs-lookup"><span data-stu-id="3db60-126">Select Other operating expenses and then select 605110 Cleaning.</span></span>  
5. <span data-ttu-id="3db60-127">No campo Comportamento de custo, selecione uma opção.</span><span class="sxs-lookup"><span data-stu-id="3db60-127">In the Cost behavior field, select an option.</span></span>
    * <span data-ttu-id="3db60-128">Escolha Custo fixo.</span><span class="sxs-lookup"><span data-stu-id="3db60-128">Select Fixed cost.</span></span>  
6. <span data-ttu-id="3db60-129">No campo Base de alocação, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="3db60-129">In the Allocation base field, enter or select a value.</span></span>
7. <span data-ttu-id="3db60-130">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="3db60-130">Click New.</span></span>
8. <span data-ttu-id="3db60-131">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="3db60-131">In the list, mark the selected row.</span></span>
9. <span data-ttu-id="3db60-132">No campo Nó da hierarquia da dimensão de objeto de custo, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="3db60-132">In the Cost object dimension hierarchy node field, enter or select a value.</span></span>
    * <span data-ttu-id="3db60-133">Expanda a hierarquia para selecionar 094.</span><span class="sxs-lookup"><span data-stu-id="3db60-133">Expand the hierarchy to select 094.</span></span>  
10. <span data-ttu-id="3db60-134">No campo Nó da hierarquia da dimensão de elemento de custo, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="3db60-134">In the Cost element dimension hierarchy node field, enter or select a value.</span></span>
    * <span data-ttu-id="3db60-135">Selecione Outras despesas operacionais e depois 605150 Aluguel.</span><span class="sxs-lookup"><span data-stu-id="3db60-135">Select Other operating expenses and then select 605150 Rent.</span></span>  
11. <span data-ttu-id="3db60-136">No campo Comportamento de custo, selecione uma opção.</span><span class="sxs-lookup"><span data-stu-id="3db60-136">In the Cost behavior field, select an option.</span></span>
    * <span data-ttu-id="3db60-137">Escolha Custo fixo.</span><span class="sxs-lookup"><span data-stu-id="3db60-137">Select Fixed cost.</span></span>  
12. <span data-ttu-id="3db60-138">No campo Base de alocação, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="3db60-138">In the Allocation base field, enter or select a value.</span></span>
13. <span data-ttu-id="3db60-139">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="3db60-139">Click Save.</span></span>

## <a name="assign-rules-to-a-cost-control-unit"></a><span data-ttu-id="3db60-140">Atribuir regras a uma unidade de controle de custos</span><span class="sxs-lookup"><span data-stu-id="3db60-140">Assign rules to a cost control unit</span></span>
1. <span data-ttu-id="3db60-141">Clique em Atribuições de políticas para unidade de controle de custo.</span><span class="sxs-lookup"><span data-stu-id="3db60-141">Click Policy assignments for cost control unit.</span></span>
2. <span data-ttu-id="3db60-142">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="3db60-142">Click New.</span></span>
3. <span data-ttu-id="3db60-143">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="3db60-143">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="3db60-144">No campo Válido a partir da data contábil, insira uma data.</span><span class="sxs-lookup"><span data-stu-id="3db60-144">In the Valid from accounting date field, enter a date.</span></span>
    * <span data-ttu-id="3db60-145">Selecione 1º de setembro no ano fiscal válido.</span><span class="sxs-lookup"><span data-stu-id="3db60-145">Select September 1 in the valid fiscal year.</span></span>  
5. <span data-ttu-id="3db60-146">No campo Unidade de controle de custo, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="3db60-146">In the Cost control unit field, enter or select a value.</span></span>
6. <span data-ttu-id="3db60-147">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="3db60-147">Click Save.</span></span>

