---
title: Planejamento com quantidades disponíveis negativas
description: Este tópico explica como a quantidade negativa disponível é tratada quando você usa a otimização do planejamento.
author: ChristianRytt
manager: tfehr
ms.date: 02/18/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2020-02-18
ms.dyn365.ops.version: AX 10.0.5
ms.openlocfilehash: 72ed2ba42c6233461743492fe6776f376195ada6
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4983457"
---
# <a name="planning-with-negative-on-hand-quantities"></a><span data-ttu-id="b897a-103">Planejamento com quantidades disponíveis negativas</span><span class="sxs-lookup"><span data-stu-id="b897a-103">Planning with negative on-hand quantities</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="b897a-104">Se o sistema mostrar uma quantidade disponível agregada negativa, o mecanismo de planejamento tratará a quantidade como 0 (zero) para ajudar a evitar o excesso de suprimento.</span><span class="sxs-lookup"><span data-stu-id="b897a-104">If the system shows a negative aggregate on-hand quantity, the planning engine treats the quantity as 0 (zero) to help avoid over-supply.</span></span> <span data-ttu-id="b897a-105">Veja como essa funcionalidade funciona:</span><span class="sxs-lookup"><span data-stu-id="b897a-105">Here is how this functionality works:</span></span>

1. <span data-ttu-id="b897a-106">O recurso de otimização de planejamento agrega quantidades disponíveis no menor nível de dimensões de cobertura.</span><span class="sxs-lookup"><span data-stu-id="b897a-106">The planning optimization feature aggregates on-hand quantities at the lowest level of coverage dimensions.</span></span> <span data-ttu-id="b897a-107">(Por exemplo, se o *local* não é uma dimensão de cobertura, a otimização do planejamento agrega quantidades disponíveis no nível do *depósito*.)</span><span class="sxs-lookup"><span data-stu-id="b897a-107">(For example, if *location* isn't a coverage dimension, planning optimization aggregates on-hand quantities at the *warehouse* level.)</span></span>
1. <span data-ttu-id="b897a-108">Se a quantidade disponível agregada no nível mais baixo das dimensões de cobertura for negativa, o sistema assume que a quantidade disponível é realmente 0 (zero).</span><span class="sxs-lookup"><span data-stu-id="b897a-108">If the aggregate on-hand quantity at the lowest level of coverage dimensions is negative, the system assumes that the on-hand quantity is really 0 (zero).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b897a-109">O sistema de planejamento pode ser tão preciso quanto os dados de entrada.</span><span class="sxs-lookup"><span data-stu-id="b897a-109">The planning system can be only as precise as the input data.</span></span> <span data-ttu-id="b897a-110">Se os dados de entrada forem imprecisos, os registros disponíveis negativos indicarão que as informações de estoque no Microsoft Dynamics 365 Supply Chain Management estão fora de sincronia com o mundo real.</span><span class="sxs-lookup"><span data-stu-id="b897a-110">If the input data is inaccurate, negative on-hand records will indicate that the inventory information in Microsoft Dynamics 365 Supply Chain Management is out of sync with the real world.</span></span> <span data-ttu-id="b897a-111">Portanto, o resultado do planejamento apresentará falha.</span><span class="sxs-lookup"><span data-stu-id="b897a-111">Therefore, the planning result will be flawed.</span></span> <span data-ttu-id="b897a-112">Para obter um resultado de planejamento preciso, é preciso minimizar o número de registros que mostram uma quantidade disponível negativa.</span><span class="sxs-lookup"><span data-stu-id="b897a-112">To get a precise planning result, you should minimize the number of records that show a negative on-hand quantity.</span></span>

## <a name="example-1"></a><span data-ttu-id="b897a-113">Exemplo 1</span><span class="sxs-lookup"><span data-stu-id="b897a-113">Example 1</span></span>

<span data-ttu-id="b897a-114">O depósito 13 é configurado da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="b897a-114">Warehouse 13 is configured in the following manner:</span></span>

- <span data-ttu-id="b897a-115">**Código de cobertura:** mín./máx.</span><span class="sxs-lookup"><span data-stu-id="b897a-115">**Coverage code:** Min./Max.</span></span>
- <span data-ttu-id="b897a-116">**Mínimo:** 15 peças (pcs.)</span><span class="sxs-lookup"><span data-stu-id="b897a-116">**Minimum:** 15 pieces (pcs.)</span></span>
- <span data-ttu-id="b897a-117">**Máximo:** 25 pcs.</span><span class="sxs-lookup"><span data-stu-id="b897a-117">**Maximum:** 25 pcs.</span></span>

<span data-ttu-id="b897a-118">O nível mais baixo das dimensões de cobertura é *depósito* e as seguintes quantidades disponíveis são registradas no nível do *local*:</span><span class="sxs-lookup"><span data-stu-id="b897a-118">The lowest level of coverage dimensions is *warehouse*, and the following on-hand quantities are recorded at the *location* level:</span></span>

- <span data-ttu-id="b897a-119">**Site 1, depósito 13, local 1:** 20 pcs.</span><span class="sxs-lookup"><span data-stu-id="b897a-119">**Site 1, warehouse 13, location 1:** 20 pcs.</span></span>
- <span data-ttu-id="b897a-120">**Site 1, depósito 13, local 2:** &minus;8 pcs.</span><span class="sxs-lookup"><span data-stu-id="b897a-120">**Site 1 warehouse 13, location 2:** &minus;8 pcs.</span></span>

<span data-ttu-id="b897a-121">Portanto, a quantidade disponível agregada para o depósito 13 é de 12 peças.</span><span class="sxs-lookup"><span data-stu-id="b897a-121">Therefore, the aggregate on-hand quantity for warehouse 13 is 12 pcs.</span></span> <span data-ttu-id="b897a-122">(= 20 pcs.</span><span class="sxs-lookup"><span data-stu-id="b897a-122">(= 20 pcs.</span></span> <span data-ttu-id="b897a-123">&minus; 8 pcs.).</span><span class="sxs-lookup"><span data-stu-id="b897a-123">&minus; 8 pcs.).</span></span>

<span data-ttu-id="b897a-124">Nesse caso, o mecanismo de planejamento usa uma quantidade agregada disponível de 12 peças.</span><span class="sxs-lookup"><span data-stu-id="b897a-124">In this case, the planning engine uses an aggregate on-hand quantity of 12 pcs.</span></span> <span data-ttu-id="b897a-125">para depósito 13.</span><span class="sxs-lookup"><span data-stu-id="b897a-125">for warehouse 13.</span></span>

<span data-ttu-id="b897a-126">O resultado é uma ordem planejada de 13 peças.</span><span class="sxs-lookup"><span data-stu-id="b897a-126">The result is a planned order of 13 pcs.</span></span> <span data-ttu-id="b897a-127">(= 25 pcs.</span><span class="sxs-lookup"><span data-stu-id="b897a-127">(= 25 pcs.</span></span> <span data-ttu-id="b897a-128">&minus; 12 pcs.) para reabastecer o depósito 13 de 12 peças.</span><span class="sxs-lookup"><span data-stu-id="b897a-128">&minus; 12 pcs.) to refill warehouse 13 from 12 pcs.</span></span> <span data-ttu-id="b897a-129">a 25 pcs.</span><span class="sxs-lookup"><span data-stu-id="b897a-129">to 25 pcs.</span></span>

## <a name="example-2"></a><span data-ttu-id="b897a-130">Exemplo 2</span><span class="sxs-lookup"><span data-stu-id="b897a-130">Example 2</span></span>

<span data-ttu-id="b897a-131">O depósito 13 é configurado da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="b897a-131">Warehouse 13 is configured in the following manner:</span></span>

- <span data-ttu-id="b897a-132">**Código de cobertura:** mín./máx.</span><span class="sxs-lookup"><span data-stu-id="b897a-132">**Coverage code:** Min./Max.</span></span>
- <span data-ttu-id="b897a-133">**Mínimo:** 15 pcs.</span><span class="sxs-lookup"><span data-stu-id="b897a-133">**Minimum:** 15 pcs.</span></span>
- <span data-ttu-id="b897a-134">**Máximo:** 25 pcs.</span><span class="sxs-lookup"><span data-stu-id="b897a-134">**Maximum:** 25 pcs.</span></span>

<span data-ttu-id="b897a-135">O nível mais baixo das dimensões de cobertura é *depósito* e as seguintes quantidades disponíveis são registradas no nível do *local*:</span><span class="sxs-lookup"><span data-stu-id="b897a-135">The lowest level of coverage dimensions is *warehouse*, and the following on-hand quantities are recorded at the *location* level:</span></span>

- <span data-ttu-id="b897a-136">**Site 1, depósito 13, local 1:** 4 pcs.</span><span class="sxs-lookup"><span data-stu-id="b897a-136">**Site 1, warehouse 13, location 1:** 4 pcs.</span></span>
- <span data-ttu-id="b897a-137">**Site 1, depósito 13, local 2:** &minus;8 pcs.</span><span class="sxs-lookup"><span data-stu-id="b897a-137">**Site 1 warehouse 13, location 2:** &minus;8 pcs.</span></span>

<span data-ttu-id="b897a-138">Portanto, a quantidade disponível agregada para o depósito 13 é de &minus;4 peças.</span><span class="sxs-lookup"><span data-stu-id="b897a-138">Therefore, the aggregate on-hand quantity for warehouse 13 is &minus;4 pcs.</span></span> <span data-ttu-id="b897a-139">(= 4 pcs.</span><span class="sxs-lookup"><span data-stu-id="b897a-139">(= 4 pcs.</span></span> <span data-ttu-id="b897a-140">&minus; 8 pcs.).</span><span class="sxs-lookup"><span data-stu-id="b897a-140">&minus; 8 pcs.).</span></span> <span data-ttu-id="b897a-141">Em outras palavras, é menor que 0 (zero).</span><span class="sxs-lookup"><span data-stu-id="b897a-141">In other words, it's less than 0 (zero).</span></span>

<span data-ttu-id="b897a-142">Nesse caso, o mecanismo de planejamento assume que a quantidade disponível para o depósito 13 é 0 unidades.</span><span class="sxs-lookup"><span data-stu-id="b897a-142">In this case, the planning engine assumes that the on-hand quantity for warehouse 13 is 0 pcs.</span></span> <span data-ttu-id="b897a-143">em vez de &minus;4 pcs.</span><span class="sxs-lookup"><span data-stu-id="b897a-143">instead of &minus;4 pcs.</span></span>

<span data-ttu-id="b897a-144">O resultado é uma ordem planejada de 25 peças.</span><span class="sxs-lookup"><span data-stu-id="b897a-144">The result is a planned order of 25 pcs.</span></span> <span data-ttu-id="b897a-145">(= 25 pcs.</span><span class="sxs-lookup"><span data-stu-id="b897a-145">(= 25 pcs.</span></span> <span data-ttu-id="b897a-146">&minus; 0 pcs.) para reabastecer o depósito 13 de 0 peças.</span><span class="sxs-lookup"><span data-stu-id="b897a-146">&minus; 0 pcs.) to refill warehouse 13 from 0 pcs.</span></span> <span data-ttu-id="b897a-147">a 25 pcs.</span><span class="sxs-lookup"><span data-stu-id="b897a-147">to 25 pcs.</span></span>

## <a name="related-resources"></a><span data-ttu-id="b897a-148">Recursos relacionados</span><span class="sxs-lookup"><span data-stu-id="b897a-148">Related resources</span></span>

[<span data-ttu-id="b897a-149">Visão geral de Otimização do Planejamento</span><span class="sxs-lookup"><span data-stu-id="b897a-149">Planning Optimization overview</span></span>](planning-optimization-overview.md)

[<span data-ttu-id="b897a-150">Introdução à Otimização de Planejamento</span><span class="sxs-lookup"><span data-stu-id="b897a-150">Get started with Planning Optimization</span></span>](get-started.md)

[<span data-ttu-id="b897a-151">Análise de ajuste da Otimização de Planejamento</span><span class="sxs-lookup"><span data-stu-id="b897a-151">Planning Optimization fit analysis</span></span>](planning-optimization-fit-analysis.md)

[<span data-ttu-id="b897a-152">Exibir logs de histórico de plano e de planejamento</span><span class="sxs-lookup"><span data-stu-id="b897a-152">View plan history and planning logs</span></span>](plan-history-logs.md)

[<span data-ttu-id="b897a-153">Cancelar um trabalho de planejamento</span><span class="sxs-lookup"><span data-stu-id="b897a-153">Cancel a planning job</span></span>](cancel-planning-job.md)
