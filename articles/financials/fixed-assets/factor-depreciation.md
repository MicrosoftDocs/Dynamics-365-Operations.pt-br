---
title: Depreciação por fator
description: Este artigo oferece uma visão geral do método de depreciação por fator.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetDepreciationProfile
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 13831
ms.assetid: 2b6c4fe4-02ff-4191-bcad-32f1f34c15f2
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: fa8bc4566def9dd770a97facb459e6b977bfaffb
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1546746"
---
# <a name="factor-depreciation"></a><span data-ttu-id="db52f-103">Depreciação por fator</span><span class="sxs-lookup"><span data-stu-id="db52f-103">Factor depreciation</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="db52f-104">Este artigo oferece uma visão geral do método de depreciação por fator.</span><span class="sxs-lookup"><span data-stu-id="db52f-104">This article gives an overview of the factor depreciation method.</span></span>

<span data-ttu-id="db52f-105">Fatores são as porcentagens usadas na depreciação de ativos.</span><span class="sxs-lookup"><span data-stu-id="db52f-105">Factors are the percentages that are used to depreciate assets.</span></span> <span data-ttu-id="db52f-106">Quando você configura um perfil de depreciação de ativo fixo e seleciona **Fator** no campo **Método** na página **Perfis de depreciação**, é possível configurar depreciação progressiva, digressiva ou linear:</span><span class="sxs-lookup"><span data-stu-id="db52f-106">When you set up a fixed asset depreciation profile and select **Factor** in the **Method** field on the **Depreciation profiles** page, you can set up progressive, digressive, or straight line depreciation:</span></span>

-   <span data-ttu-id="db52f-107">Na depreciação progressiva, o valor da depreciação aumenta a cada período de depreciação.</span><span class="sxs-lookup"><span data-stu-id="db52f-107">In progressive depreciation, the amount of depreciation increases each depreciation period.</span></span>
-   <span data-ttu-id="db52f-108">Na depreciação digressiva, o valor da depreciação por período diminui com o tempo.</span><span class="sxs-lookup"><span data-stu-id="db52f-108">In digressive depreciation, the amount of depreciation per period decreases over time.</span></span>
-   <span data-ttu-id="db52f-109">Na depreciação linear, a depreciação é a mesma em todos os períodos.</span><span class="sxs-lookup"><span data-stu-id="db52f-109">In straight line depreciation, the depreciation is the same in each period.</span></span>

<span data-ttu-id="db52f-110">As regras e os exemplos a seguir indicam como é possível definir fatores para cada tipo de depreciação.</span><span class="sxs-lookup"><span data-stu-id="db52f-110">The rules and examples that follow indicate how you can set up factors for each type of depreciation.</span></span> 

> [!NOTE] 
> <span data-ttu-id="db52f-111">Quando você seleciona **Fator** no campo **Método**, os campos **Fator** e **Intervalo** são exibidos.</span><span class="sxs-lookup"><span data-stu-id="db52f-111">When you select **Factor** in the **Method** field, the **Factor** field and the **Interval** field are displayed.</span></span>

## <a name="progressive-depreciation"></a><span data-ttu-id="db52f-112">Depreciação progressiva</span><span class="sxs-lookup"><span data-stu-id="db52f-112">Progressive depreciation</span></span>
<span data-ttu-id="db52f-113">O valor no campo **Fator** é maior que **50**.</span><span class="sxs-lookup"><span data-stu-id="db52f-113">The value in the **Factor** field is more than **50**.</span></span>

### <a name="example"></a><span data-ttu-id="db52f-114">Exemplo</span><span class="sxs-lookup"><span data-stu-id="db52f-114">Example</span></span>

<span data-ttu-id="db52f-115">O preço de aquisição é 100.000, o fator é 70, a vida útil é 10 anos e a depreciação começa em 1º de janeiro.</span><span class="sxs-lookup"><span data-stu-id="db52f-115">The acquisition price is 100,000, the factor is 70, the service life is 10 years, and depreciation starts on January 1.</span></span> <span data-ttu-id="db52f-116">Os valores de depreciação e os valores líquidos contábeis são mostrados apenas durante os seis primeiros anos de vida útil.</span><span class="sxs-lookup"><span data-stu-id="db52f-116">The depreciation amounts and net book value amounts are shown only for the first six years of service life.</span></span>

| <span data-ttu-id="db52f-117">Ano</span><span class="sxs-lookup"><span data-stu-id="db52f-117">Year</span></span> | <span data-ttu-id="db52f-118">Período</span><span class="sxs-lookup"><span data-stu-id="db52f-118">Period</span></span>      | <span data-ttu-id="db52f-119">Valor de depreciação</span><span class="sxs-lookup"><span data-stu-id="db52f-119">Depreciation amount</span></span> | <span data-ttu-id="db52f-120">Valor líquido contábil</span><span class="sxs-lookup"><span data-stu-id="db52f-120">Net book value amount</span></span> |
|------|-------------|---------------------|-----------------------|
| <span data-ttu-id="db52f-121">1</span><span class="sxs-lookup"><span data-stu-id="db52f-121">1</span></span>    | <span data-ttu-id="db52f-122">31 de dezembro</span><span class="sxs-lookup"><span data-stu-id="db52f-122">December 31</span></span> | <span data-ttu-id="db52f-123">307,69</span><span class="sxs-lookup"><span data-stu-id="db52f-123">307.69</span></span>              | <span data-ttu-id="db52f-124">99.692,31</span><span class="sxs-lookup"><span data-stu-id="db52f-124">99,692.31</span></span>             |
| <span data-ttu-id="db52f-125">2</span><span class="sxs-lookup"><span data-stu-id="db52f-125">2</span></span>    | <span data-ttu-id="db52f-126">31 de dezembro</span><span class="sxs-lookup"><span data-stu-id="db52f-126">December 31</span></span> | <span data-ttu-id="db52f-127">1.447,21</span><span class="sxs-lookup"><span data-stu-id="db52f-127">1,447.21</span></span>            | <span data-ttu-id="db52f-128">98.245,10</span><span class="sxs-lookup"><span data-stu-id="db52f-128">98,245.10</span></span>             |
| <span data-ttu-id="db52f-129">3</span><span class="sxs-lookup"><span data-stu-id="db52f-129">3</span></span>    | <span data-ttu-id="db52f-130">31 de dezembro</span><span class="sxs-lookup"><span data-stu-id="db52f-130">December 31</span></span> | <span data-ttu-id="db52f-131">3.104,50</span><span class="sxs-lookup"><span data-stu-id="db52f-131">3,104.50</span></span>            | <span data-ttu-id="db52f-132">95.140,60</span><span class="sxs-lookup"><span data-stu-id="db52f-132">95,140.60</span></span>             |
| <span data-ttu-id="db52f-133">4</span><span class="sxs-lookup"><span data-stu-id="db52f-133">4</span></span>    | <span data-ttu-id="db52f-134">31 de dezembro</span><span class="sxs-lookup"><span data-stu-id="db52f-134">December 31</span></span> | <span data-ttu-id="db52f-135">5.150,21</span><span class="sxs-lookup"><span data-stu-id="db52f-135">5,150.21</span></span>            | <span data-ttu-id="db52f-136">89.990,39</span><span class="sxs-lookup"><span data-stu-id="db52f-136">89,990.39</span></span>             |
| <span data-ttu-id="db52f-137">5</span><span class="sxs-lookup"><span data-stu-id="db52f-137">5</span></span>    | <span data-ttu-id="db52f-138">31 de dezembro</span><span class="sxs-lookup"><span data-stu-id="db52f-138">December 31</span></span> | <span data-ttu-id="db52f-139">7.522,95</span><span class="sxs-lookup"><span data-stu-id="db52f-139">7,522.95</span></span>            | <span data-ttu-id="db52f-140">82.467,44</span><span class="sxs-lookup"><span data-stu-id="db52f-140">82,467.44</span></span>             |
| <span data-ttu-id="db52f-141">6</span><span class="sxs-lookup"><span data-stu-id="db52f-141">6</span></span>    | <span data-ttu-id="db52f-142">31 de dezembro</span><span class="sxs-lookup"><span data-stu-id="db52f-142">December 31</span></span> | <span data-ttu-id="db52f-143">10.184,06</span><span class="sxs-lookup"><span data-stu-id="db52f-143">10,184.06</span></span>           | <span data-ttu-id="db52f-144">72.283,38</span><span class="sxs-lookup"><span data-stu-id="db52f-144">72,283.38</span></span>             |

## <a name="digressive-depreciation"></a><span data-ttu-id="db52f-145">Depreciação digressiva</span><span class="sxs-lookup"><span data-stu-id="db52f-145">Digressive depreciation</span></span>
<span data-ttu-id="db52f-146">O valor do campo **Fator** é menor do que **50**.</span><span class="sxs-lookup"><span data-stu-id="db52f-146">The value in the **Factor** field is less than **50**.</span></span>

### <a name="example"></a><span data-ttu-id="db52f-147">Exemplo</span><span class="sxs-lookup"><span data-stu-id="db52f-147">Example</span></span>

<span data-ttu-id="db52f-148">O preço de aquisição é 100.000, o fator é 20, a vida útil é 10 anos e a depreciação começa em 1º de janeiro.</span><span class="sxs-lookup"><span data-stu-id="db52f-148">The acquisition price is 100,000, the factor is 20, the service life is 10 years, and depreciation starts on January 1.</span></span> <span data-ttu-id="db52f-149">Os valores de depreciação e os valores líquidos contábeis são mostrados apenas durante os seis primeiros anos de vida útil.</span><span class="sxs-lookup"><span data-stu-id="db52f-149">The depreciation amounts and net book value amounts are shown only for the first six years of service life.</span></span>

| <span data-ttu-id="db52f-150">Ano</span><span class="sxs-lookup"><span data-stu-id="db52f-150">Year</span></span> | <span data-ttu-id="db52f-151">Período</span><span class="sxs-lookup"><span data-stu-id="db52f-151">Period</span></span>      | <span data-ttu-id="db52f-152">Valor de depreciação</span><span class="sxs-lookup"><span data-stu-id="db52f-152">Depreciation amount</span></span> | <span data-ttu-id="db52f-153">Valor líquido contábil</span><span class="sxs-lookup"><span data-stu-id="db52f-153">Net book value amount</span></span> |
|------|-------------|---------------------|-----------------------|
| <span data-ttu-id="db52f-154">1</span><span class="sxs-lookup"><span data-stu-id="db52f-154">1</span></span>    | <span data-ttu-id="db52f-155">31 de dezembro</span><span class="sxs-lookup"><span data-stu-id="db52f-155">December 31</span></span> | <span data-ttu-id="db52f-156">56.080,43</span><span class="sxs-lookup"><span data-stu-id="db52f-156">56,080.43</span></span>           | <span data-ttu-id="db52f-157">43.919,57</span><span class="sxs-lookup"><span data-stu-id="db52f-157">43,919.57</span></span>             |
| <span data-ttu-id="db52f-158">2</span><span class="sxs-lookup"><span data-stu-id="db52f-158">2</span></span>    | <span data-ttu-id="db52f-159">31 de dezembro</span><span class="sxs-lookup"><span data-stu-id="db52f-159">December 31</span></span> | <span data-ttu-id="db52f-160">10.665,70</span><span class="sxs-lookup"><span data-stu-id="db52f-160">10,665.70</span></span>           | <span data-ttu-id="db52f-161">33.253,87</span><span class="sxs-lookup"><span data-stu-id="db52f-161">33,253.87</span></span>             |
| <span data-ttu-id="db52f-162">3</span><span class="sxs-lookup"><span data-stu-id="db52f-162">3</span></span>    | <span data-ttu-id="db52f-163">31 de dezembro</span><span class="sxs-lookup"><span data-stu-id="db52f-163">December 31</span></span> | <span data-ttu-id="db52f-164">7.156,22</span><span class="sxs-lookup"><span data-stu-id="db52f-164">7,156.22</span></span>            | <span data-ttu-id="db52f-165">26.097,65</span><span class="sxs-lookup"><span data-stu-id="db52f-165">26,097.65</span></span>             |
| <span data-ttu-id="db52f-166">4</span><span class="sxs-lookup"><span data-stu-id="db52f-166">4</span></span>    | <span data-ttu-id="db52f-167">31 de dezembro</span><span class="sxs-lookup"><span data-stu-id="db52f-167">December 31</span></span> | <span data-ttu-id="db52f-168">5.538,06</span><span class="sxs-lookup"><span data-stu-id="db52f-168">5,538.06</span></span>            | <span data-ttu-id="db52f-169">20.559,59</span><span class="sxs-lookup"><span data-stu-id="db52f-169">20,559.59</span></span>             |
| <span data-ttu-id="db52f-170">5</span><span class="sxs-lookup"><span data-stu-id="db52f-170">5</span></span>    | <span data-ttu-id="db52f-171">31 de dezembro</span><span class="sxs-lookup"><span data-stu-id="db52f-171">December 31</span></span> | <span data-ttu-id="db52f-172">4.579,89</span><span class="sxs-lookup"><span data-stu-id="db52f-172">4,579.89</span></span>            | <span data-ttu-id="db52f-173">15.979,70</span><span class="sxs-lookup"><span data-stu-id="db52f-173">15,979.70</span></span>             |
| <span data-ttu-id="db52f-174">6</span><span class="sxs-lookup"><span data-stu-id="db52f-174">6</span></span>    | <span data-ttu-id="db52f-175">31 de dezembro</span><span class="sxs-lookup"><span data-stu-id="db52f-175">December 31</span></span> | <span data-ttu-id="db52f-176">3.937,36</span><span class="sxs-lookup"><span data-stu-id="db52f-176">3,937.36</span></span>            | <span data-ttu-id="db52f-177">12.042,34</span><span class="sxs-lookup"><span data-stu-id="db52f-177">12,042.34</span></span>             |

## <a name="straight-line-depreciation"></a><span data-ttu-id="db52f-178">Depreciação linear</span><span class="sxs-lookup"><span data-stu-id="db52f-178">Straight line depreciation</span></span>
<span data-ttu-id="db52f-179">O valor no campo **Fator** é igual a **50**.</span><span class="sxs-lookup"><span data-stu-id="db52f-179">The value in the **Factor** field is equal to **50**.</span></span> <span data-ttu-id="db52f-180">Nesse caso, a depreciação é a mesma em todos os períodos, e devem ser consideradas as implicações de valores que você especificou em outros campos, conforme descrito em [Depreciação linear com base na vida útil](straight-line-service-life-depreciation.md).</span><span class="sxs-lookup"><span data-stu-id="db52f-180">In this case, the depreciation is the same in each period, and you should consider the implications of the values that you have specified in other fields, as described in [Straight line service life depreciation](straight-line-service-life-depreciation.md).</span></span>



