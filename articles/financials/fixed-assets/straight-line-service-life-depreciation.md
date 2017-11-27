---
title: "Depreciação de vida útil linear"
description: "Este artigo oferece uma visão geral do Método de depreciação linear com base na vida útil."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: AssetDepreciationProfile
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 3341
ms.assetid: ae5ceaeb-aeb7-45cd-b835-23cf9c5cf95a
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: bb5715855c7e240cddf4fd264a4b26ca09a2f6c4
ms.contentlocale: pt-br
ms.lasthandoff: 11/03/2017

---

# <a name="straight-line-service-life-depreciation"></a><span data-ttu-id="1bfc3-103">Depreciação de vida útil linear</span><span class="sxs-lookup"><span data-stu-id="1bfc3-103">Straight line service life depreciation</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="1bfc3-104">Este artigo oferece uma visão geral do Método de depreciação linear com base na vida útil.</span><span class="sxs-lookup"><span data-stu-id="1bfc3-104">This article gives an overview of the Straight line service life method of depreciation.</span></span>

<span data-ttu-id="1bfc3-105">Quando você configura um perfil de depreciação de ativo fixo e seleciona Vida útil linear no campo Método, na página Perfis de depreciação, os ativos com esse perfil de depreciação atribuído serão depreciados com base na vida útil total do ativo.</span><span class="sxs-lookup"><span data-stu-id="1bfc3-105">When you set up a fixed asset depreciation profile and select Straight line service life in the Method field in the Depreciation profiles page, the assets that have this depreciation profile assigned to them are depreciated based on the total service life of the asset.</span></span> <span data-ttu-id="1bfc3-106">Esse geralmente é o mesmo valor de depreciação em cada período de depreciação.</span><span class="sxs-lookup"><span data-stu-id="1bfc3-106">This generally is the same depreciation amount in each depreciation period.</span></span> 

<span data-ttu-id="1bfc3-107">A diferença no valor de depreciação calculado entre a vida útil linear restante e a vida útil linear é quando ocorre um ajuste lançado no ativo.</span><span class="sxs-lookup"><span data-stu-id="1bfc3-107">The difference in the depreciation amount that is calculated between straight line service life remaining and straight line service life is when there is an adjustment posted to the asset.</span></span> 

<span data-ttu-id="1bfc3-108">Para configurar a depreciação linear com base na vida útil, também é preciso selecionar opções nos campos Ano de depreciação e Frequência do período na página Perfis de depreciação.</span><span class="sxs-lookup"><span data-stu-id="1bfc3-108">To set up straight line service life depreciation, you must also select options in the Depreciation year and Period frequency fields in the Depreciation profiles page.</span></span>

## <a name="select-a-depreciation-year"></a><span data-ttu-id="1bfc3-109">Selecione um ano de depreciação</span><span class="sxs-lookup"><span data-stu-id="1bfc3-109">Select a depreciation year</span></span>
<span data-ttu-id="1bfc3-110">Você pode selecionar Calendário ou Fiscal no campo Ano de depreciação na página Perfis de depreciação.</span><span class="sxs-lookup"><span data-stu-id="1bfc3-110">You can select either Calendar or Fiscal in the Depreciation year field in the Depreciation profiles page.</span></span> <span data-ttu-id="1bfc3-111">A seleção define as opções disponíveis no campo Frequência do período.</span><span class="sxs-lookup"><span data-stu-id="1bfc3-111">The selection defines the options that are available in the Period frequency field.</span></span> <span data-ttu-id="1bfc3-112">A opção padrão é Calendário.</span><span class="sxs-lookup"><span data-stu-id="1bfc3-112">The default option is Calendar.</span></span>

### <a name="calendar"></a><span data-ttu-id="1bfc3-113">Calendário</span><span class="sxs-lookup"><span data-stu-id="1bfc3-113">Calendar</span></span>

<span data-ttu-id="1bfc3-114">Se você selecionar Calendário, será considerado um ano de 1º de janeiro a 31 de dezembro, mesmo que você tenha definido o calendário fiscal de forma diferente.</span><span class="sxs-lookup"><span data-stu-id="1bfc3-114">If you select Calendar, a year of January 1 to December 31 is assumed, even if you have defined the fiscal calendar differently.</span></span> 

<span data-ttu-id="1bfc3-115">A opção Calendário atualiza a base da depreciação que, normalmente é o valor líquido contábil menos o valor residual, no dia 1º de janeiro de cada ano.</span><span class="sxs-lookup"><span data-stu-id="1bfc3-115">The Calendar option updates the depreciation base, which is typically the net book value minus the salvage value, on January 1 of each year.</span></span> <span data-ttu-id="1bfc3-116">Nos exemplos a seguir deste tópico, a base de depreciação é o numerador na primeira expressão da coluna de cálculos.</span><span class="sxs-lookup"><span data-stu-id="1bfc3-116">In the examples later in this topic, the depreciation base is the numerator in the first expression in the calculations column.</span></span> 

<span data-ttu-id="1bfc3-117">Caso selecione Calendário, você terá estas opções no campo Frequência do período, que define as datas e os valores de lançamento acumulado da depreciação durante todo o ano civil.</span><span class="sxs-lookup"><span data-stu-id="1bfc3-117">If you select Calendar, the following options are available in the Period frequency field, which defines the depreciation accrual posting dates and amounts throughout the calendar year:</span></span>
-   <span data-ttu-id="1bfc3-118">Anualmente lança um valor em 31 de dezembro.</span><span class="sxs-lookup"><span data-stu-id="1bfc3-118">Yearly posts an amount on December 31.</span></span>
-   <span data-ttu-id="1bfc3-119">Mensal lança um valor mensal ao final de cada mês do calendário.</span><span class="sxs-lookup"><span data-stu-id="1bfc3-119">Monthly posts a monthly amount at the end of each calendar month.</span></span>
-   <span data-ttu-id="1bfc3-120">Trimestral lança um valor trimestral ao final de cada trimestre do calendário (31 de março, 30 de junho, 30 de setembro e 31 de dezembro).</span><span class="sxs-lookup"><span data-stu-id="1bfc3-120">Quarterly posts a quarterly amount at the end of each calendar quarter (March 31, June 30, September 30, and December 31).</span></span>
-   <span data-ttu-id="1bfc3-121">Semestral lança um valor semestral no final de cada semestre do calendário (30 de junho e 31 de dezembro).</span><span class="sxs-lookup"><span data-stu-id="1bfc3-121">Half-Yearly posts a half-yearly amount at the end of each calendar half year (June 30 and December 31).</span></span>
-   <span data-ttu-id="1bfc3-122">Diário lança o valor de depreciação do método de depreciação diária usando uma transação para cada dia.</span><span class="sxs-lookup"><span data-stu-id="1bfc3-122">Daily posts the depreciation amount for the daily depreciation method using one transaction for each day.</span></span>

<span data-ttu-id="1bfc3-123">Por exemplo, se você selecionar Anual, a depreciação anual é lançada apenas uma vez, no dia 31 de dezembro de cada ano.</span><span class="sxs-lookup"><span data-stu-id="1bfc3-123">For example, if you select Yearly, the yearly depreciation is posted only one time, on December 31 of each year.</span></span> <span data-ttu-id="1bfc3-124">Se você selecionar Mensal, a depreciação mensal é lançada a cada mês como 1/12 do valor de depreciação anual.</span><span class="sxs-lookup"><span data-stu-id="1bfc3-124">If you select Monthly, the monthly depreciation is posted each month as 1/12 of the yearly depreciation amount.</span></span>

### <a name="fiscal"></a><span data-ttu-id="1bfc3-125">fiscal</span><span class="sxs-lookup"><span data-stu-id="1bfc3-125">Fiscal</span></span>

<span data-ttu-id="1bfc3-126">Caso você selecione Fiscal no campo Ano de depreciação, será usada a depreciação linear com base na vida útil.</span><span class="sxs-lookup"><span data-stu-id="1bfc3-126">If you select Fiscal in the Depreciation year field, the straight line service life depreciation is used.</span></span> <span data-ttu-id="1bfc3-127">Ela é calculada com base no ano fiscal, que é definido pelo calendário fiscal que é especificado para o registro de depreciação, ou pelo calendário fiscal selecionado na página Razão.</span><span class="sxs-lookup"><span data-stu-id="1bfc3-127">It is calculated based on the fiscal year, which is defined by the fiscal calendar that is specified for the book, or by the fiscal calendar that is selected in the Ledger page.</span></span> <span data-ttu-id="1bfc3-128">Os calendários fiscais são configurados na página Calendários fiscais.</span><span class="sxs-lookup"><span data-stu-id="1bfc3-128">Fiscal calendars are set up in the Fiscal calendars page.</span></span>

<span data-ttu-id="1bfc3-129">Por exemplo, no ano fiscal entre 1 de julho e 30 de junho, o cálculo da depreciação começa em 1 de julho.</span><span class="sxs-lookup"><span data-stu-id="1bfc3-129">For example, for fiscal year July 1 through June 30, the depreciation calculation starts on July 1.</span></span> <span data-ttu-id="1bfc3-130">O ano fiscal pode ter mais ou menos do que 12 meses.</span><span class="sxs-lookup"><span data-stu-id="1bfc3-130">The fiscal year can be longer or shorter than 12 months.</span></span> <span data-ttu-id="1bfc3-131">A depreciação é ajustada automaticamente para cada período fiscal.</span><span class="sxs-lookup"><span data-stu-id="1bfc3-131">The depreciation automatically is adjusted for each fiscal period.</span></span> <span data-ttu-id="1bfc3-132">A duração do próximo ano fiscal baseia-se nos períodos fiscais configurados quando você cria um novo ano fiscal no formulário Calendários fiscais.</span><span class="sxs-lookup"><span data-stu-id="1bfc3-132">The length of the next fiscal year is based on the fiscal periods that you set up when you create a new fiscal year in the Fiscal calendars form.</span></span> 

<span data-ttu-id="1bfc3-133">Se você selecionar Fiscal, as opções a seguir estarão disponíveis no campo Frequência do período:</span><span class="sxs-lookup"><span data-stu-id="1bfc3-133">If you select Fiscal, the following options are available in the Period frequency field:</span></span>
-   <span data-ttu-id="1bfc3-134">Anual lança o valor total da depreciação calculada para o ano fiscal como um valor no último dia do ano fiscal.</span><span class="sxs-lookup"><span data-stu-id="1bfc3-134">Yearly posts the total amount of the depreciation that is calculated for the fiscal year as one amount on the last day of the fiscal year.</span></span>
-   <span data-ttu-id="1bfc3-135">Período fiscal calcula o valor total da depreciação para o ano fiscal, acumulado nos períodos definidos no formulário de Calendários fiscais ou no formulário do calendário fiscal.</span><span class="sxs-lookup"><span data-stu-id="1bfc3-135">Fiscal period calculates the total amount of the depreciation for the fiscal year, which is accrued into the periods that are defined in the Fiscal calendars form for the fiscal calendar.</span></span>

## <a name="example-straight-line-depreciation-of-an-unchanged-fixed-asset"></a><span data-ttu-id="1bfc3-136">Exemplo: depreciação linear de um ativo fixo não alterado</span><span class="sxs-lookup"><span data-stu-id="1bfc3-136">Example: Straight line depreciation of an unchanged fixed asset</span></span>
<span data-ttu-id="1bfc3-137">Suponha que um ativo fixo tenha as características a seguir.</span><span class="sxs-lookup"><span data-stu-id="1bfc3-137">Suppose that a fixed asset has the following characteristics.</span></span>

|                     |        |
|---------------------|--------|
| <span data-ttu-id="1bfc3-138">Custo de Aquisição</span><span class="sxs-lookup"><span data-stu-id="1bfc3-138">Acquisition cost</span></span>    | <span data-ttu-id="1bfc3-139">11.000</span><span class="sxs-lookup"><span data-stu-id="1bfc3-139">11,000</span></span> |
| <span data-ttu-id="1bfc3-140">valor residual</span><span class="sxs-lookup"><span data-stu-id="1bfc3-140">Salvage value</span></span>       | <span data-ttu-id="1bfc3-141">1.000</span><span class="sxs-lookup"><span data-stu-id="1bfc3-141">1,000</span></span>  |
| <span data-ttu-id="1bfc3-142">Base de depreciação</span><span class="sxs-lookup"><span data-stu-id="1bfc3-142">Depreciation base</span></span>   | <span data-ttu-id="1bfc3-143">10.000</span><span class="sxs-lookup"><span data-stu-id="1bfc3-143">10,000</span></span> |
| <span data-ttu-id="1bfc3-144">Anos de vida útil</span><span class="sxs-lookup"><span data-stu-id="1bfc3-144">Service life years</span></span>  | <span data-ttu-id="1bfc3-145">5</span><span class="sxs-lookup"><span data-stu-id="1bfc3-145">5</span></span>      |
| <span data-ttu-id="1bfc3-146">Depreciação anual</span><span class="sxs-lookup"><span data-stu-id="1bfc3-146">Yearly depreciation</span></span> | <span data-ttu-id="1bfc3-147">2.000</span><span class="sxs-lookup"><span data-stu-id="1bfc3-147">2,000</span></span>  |

<span data-ttu-id="1bfc3-148">Você tem o mesmo valor de depreciação a cada ano.</span><span class="sxs-lookup"><span data-stu-id="1bfc3-148">You get the same depreciation amount each year.</span></span> <span data-ttu-id="1bfc3-149">(Custo de aquisição - Valor residual)/Anos de vida útil</span><span class="sxs-lookup"><span data-stu-id="1bfc3-149">(Acquisition cost - Salvage value) / Service life years</span></span>

| <span data-ttu-id="1bfc3-150">Período</span><span class="sxs-lookup"><span data-stu-id="1bfc3-150">Period</span></span> | <span data-ttu-id="1bfc3-151">Cálculo do valor de depreciação anual</span><span class="sxs-lookup"><span data-stu-id="1bfc3-151">Calculation of yearly depreciation amount</span></span> | <span data-ttu-id="1bfc3-152">Valor líquido contábil no final do ano</span><span class="sxs-lookup"><span data-stu-id="1bfc3-152">Net book value at the end of the year</span></span> |
|--------|-------------------------------------------|---------------------------------------|
| <span data-ttu-id="1bfc3-153">Ano 1</span><span class="sxs-lookup"><span data-stu-id="1bfc3-153">Year 1</span></span> | <span data-ttu-id="1bfc3-154">(11.000 - 1.000) / 5 = 2.000</span><span class="sxs-lookup"><span data-stu-id="1bfc3-154">(11,000 - 1,000) / 5 = 2,000</span></span>              | <span data-ttu-id="1bfc3-155">9.000</span><span class="sxs-lookup"><span data-stu-id="1bfc3-155">9,000</span></span>                                 |
| <span data-ttu-id="1bfc3-156">Ano 2</span><span class="sxs-lookup"><span data-stu-id="1bfc3-156">Year 2</span></span> | <span data-ttu-id="1bfc3-157">(11.000 - 1.000) / 5 = 2.000</span><span class="sxs-lookup"><span data-stu-id="1bfc3-157">(11,000 - 1,000) / 5 = 2,000</span></span>              | <span data-ttu-id="1bfc3-158">7.000</span><span class="sxs-lookup"><span data-stu-id="1bfc3-158">7,000</span></span>                                 |
| <span data-ttu-id="1bfc3-159">Ano 3</span><span class="sxs-lookup"><span data-stu-id="1bfc3-159">Year 3</span></span> | <span data-ttu-id="1bfc3-160">(11.000 - 1.000) / 5 = 2.000</span><span class="sxs-lookup"><span data-stu-id="1bfc3-160">(11,000 - 1,000) / 5 = 2,000</span></span>              | <span data-ttu-id="1bfc3-161">5.000</span><span class="sxs-lookup"><span data-stu-id="1bfc3-161">5,000</span></span>                                 |
| <span data-ttu-id="1bfc3-162">Ano 4</span><span class="sxs-lookup"><span data-stu-id="1bfc3-162">Year 4</span></span> | <span data-ttu-id="1bfc3-163">(11.000 - 1.000) / 5 = 2.000</span><span class="sxs-lookup"><span data-stu-id="1bfc3-163">(11,000 - 1,000) / 5 = 2,000</span></span>              | <span data-ttu-id="1bfc3-164">3.000</span><span class="sxs-lookup"><span data-stu-id="1bfc3-164">3,000</span></span>                                 |
| <span data-ttu-id="1bfc3-165">Ano 5</span><span class="sxs-lookup"><span data-stu-id="1bfc3-165">Year 5</span></span> | <span data-ttu-id="1bfc3-166">(11.000 - 1.000) / 5 = 2.000</span><span class="sxs-lookup"><span data-stu-id="1bfc3-166">(11,000 - 1,000) / 5 = 2,000</span></span>              | <span data-ttu-id="1bfc3-167">1.000</span><span class="sxs-lookup"><span data-stu-id="1bfc3-167">1,000</span></span>                                 |

## <a name="example-straight-line-depreciation-of-a-modified-fixed-asset"></a><span data-ttu-id="1bfc3-168">Exemplo: depreciação linear de um ativo fixo modificado</span><span class="sxs-lookup"><span data-stu-id="1bfc3-168">Example: Straight line depreciation of a modified fixed asset</span></span>

<span data-ttu-id="1bfc3-169">Suponha que você adicione um ajuste de aquisição de 4.000 no ano 2 para o mesmo ativo fixo.</span><span class="sxs-lookup"><span data-stu-id="1bfc3-169">Suppose that you add an acquisition adjustment of 4,000 in year 2 to the same fixed asset.</span></span> 

<span data-ttu-id="1bfc3-170">A vida útil do ajuste de aquisição é igual a do ativo fixo e começa no momento de sua aquisição.</span><span class="sxs-lookup"><span data-stu-id="1bfc3-170">The service life of the acquisition adjustment is the same as that of the fixed asset and starts at the time of its acquisition.</span></span> <span data-ttu-id="1bfc3-171">Um valor líquido contábil permanecerá no final do ano 5, correspondente ao valor líquido contábil do ajuste de aquisição.</span><span class="sxs-lookup"><span data-stu-id="1bfc3-171">A net book value remains at the end of year 5, corresponding to the net book value of the acquisition adjustment.</span></span> <span data-ttu-id="1bfc3-172">A depreciação por período é calculada conforme mostrado na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="1bfc3-172">The depreciation by period is calculated as shown in the following table.</span></span>

| <span data-ttu-id="1bfc3-173">Período</span><span class="sxs-lookup"><span data-stu-id="1bfc3-173">Period</span></span> | <span data-ttu-id="1bfc3-174">Cálculo do valor de depreciação anual</span><span class="sxs-lookup"><span data-stu-id="1bfc3-174">Calculation of yearly depreciation amount</span></span> | <span data-ttu-id="1bfc3-175">Valor líquido contábil no final do ano</span><span class="sxs-lookup"><span data-stu-id="1bfc3-175">Net book value at the end of the year</span></span> |
|--------|-------------------------------------------|---------------------------------------|
| <span data-ttu-id="1bfc3-176">Ano 1</span><span class="sxs-lookup"><span data-stu-id="1bfc3-176">Year 1</span></span> | <span data-ttu-id="1bfc3-177">10.000 / 5 = 2.000</span><span class="sxs-lookup"><span data-stu-id="1bfc3-177">10,000 / 5 = 2,000</span></span>                        | <span data-ttu-id="1bfc3-178">11.000 - 2.000 = 9.000</span><span class="sxs-lookup"><span data-stu-id="1bfc3-178">11,000 - 2,000 = 9,000</span></span>                |
| <span data-ttu-id="1bfc3-179">Ano 2</span><span class="sxs-lookup"><span data-stu-id="1bfc3-179">Year 2</span></span> | <span data-ttu-id="1bfc3-180">4.000 (ajuste de aquisição)</span><span class="sxs-lookup"><span data-stu-id="1bfc3-180">4,000 (acquisition adjustment)</span></span>            | <span data-ttu-id="1bfc3-181">9.000 + 4.000 =13.000</span><span class="sxs-lookup"><span data-stu-id="1bfc3-181">9,000 + 4,000 =13,000</span></span>                 |
| <span data-ttu-id="1bfc3-182">Ano 2</span><span class="sxs-lookup"><span data-stu-id="1bfc3-182">Year 2</span></span> | <span data-ttu-id="1bfc3-183">14.000 / 5 = 2.800</span><span class="sxs-lookup"><span data-stu-id="1bfc3-183">14,000 / 5 = 2,800</span></span>                        | <span data-ttu-id="1bfc3-184">13.000 - 2.800 = 10.200</span><span class="sxs-lookup"><span data-stu-id="1bfc3-184">13,000 - 2,800 = 10,200</span></span>               |
| <span data-ttu-id="1bfc3-185">Ano 3</span><span class="sxs-lookup"><span data-stu-id="1bfc3-185">Year 3</span></span> | <span data-ttu-id="1bfc3-186">14.000 / 5 = 2.800</span><span class="sxs-lookup"><span data-stu-id="1bfc3-186">14,000 / 5 = 2,800</span></span>                        | <span data-ttu-id="1bfc3-187">10.200 - 2.800 = 7.400</span><span class="sxs-lookup"><span data-stu-id="1bfc3-187">10,200 - 2,800 = 7,400</span></span>                |
| <span data-ttu-id="1bfc3-188">Ano 4</span><span class="sxs-lookup"><span data-stu-id="1bfc3-188">Year 4</span></span> | <span data-ttu-id="1bfc3-189">14.000 / 5 = 2.800</span><span class="sxs-lookup"><span data-stu-id="1bfc3-189">14,000 / 5 = 2,800</span></span>                        | <span data-ttu-id="1bfc3-190">7.400 - 2.800 = 4.600</span><span class="sxs-lookup"><span data-stu-id="1bfc3-190">7,400 - 2,800 = 4,600</span></span>                 |
| <span data-ttu-id="1bfc3-191">Ano 5</span><span class="sxs-lookup"><span data-stu-id="1bfc3-191">Year 5</span></span> | <span data-ttu-id="1bfc3-192">14.000 / 5 = 2.800</span><span class="sxs-lookup"><span data-stu-id="1bfc3-192">14,000 / 5 = 2,800</span></span>                        | <span data-ttu-id="1bfc3-193">4.600 - 2.800 = 1.800</span><span class="sxs-lookup"><span data-stu-id="1bfc3-193">4,600 - 2,800 = 1,800</span></span>                 |
| <span data-ttu-id="1bfc3-194">Ano 6</span><span class="sxs-lookup"><span data-stu-id="1bfc3-194">Year 6</span></span> | <span data-ttu-id="1bfc3-195">Restante 800*\*</span><span class="sxs-lookup"><span data-stu-id="1bfc3-195">Remaining 800\*</span></span>                           | <span data-ttu-id="1bfc3-196">1.800 – 800 = 1.000</span><span class="sxs-lookup"><span data-stu-id="1bfc3-196">1,800 – 800 = 1,000</span></span>                   |

<span data-ttu-id="1bfc3-197">\**Como o valor restante é menor que o valor de depreciação, somente o valor restante menos o valor residual será obtido.</span><span class="sxs-lookup"><span data-stu-id="1bfc3-197">\*Because the remaining amount is less than the depreciation amount, only the remaining amount minus the salvage value is taken.</span></span>






