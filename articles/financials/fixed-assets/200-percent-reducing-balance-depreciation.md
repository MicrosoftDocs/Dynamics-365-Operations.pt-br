---
title: "depreciação com declínio de 200%"
description: "Este artigo oferece uma visão geral do método de saldo de reduzem de 200 de porcentagem de depreciação."
author: saraschi2
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
ms.custom: 13951
ms.assetid: 69b4e010-7683-4dc2-8a06-6d572f37e903
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: e6600176cbbcb6e30fc451613acff1fb487e7c76
ms.contentlocale: pt-br
ms.lasthandoff: 04/13/2018

---

# <a name="200-percent-reducing-balance-depreciation"></a><span data-ttu-id="5b0aa-103">depreciação com declínio de 200%</span><span class="sxs-lookup"><span data-stu-id="5b0aa-103">200 percent reducing balance depreciation</span></span>

[!INCLUDE [banner](../includes/banner.md)]

<span data-ttu-id="5b0aa-104">Este artigo oferece uma visão geral do método de saldo de reduzem de 200 de porcentagem de depreciação.</span><span class="sxs-lookup"><span data-stu-id="5b0aa-104">This article gives an overview of the 200 percent reducing balance method of depreciation.</span></span>

<span data-ttu-id="5b0aa-105">Ao configurar um perfil de depreciação de ativos fixos e selecionar **declínio de 200%** no campo **Método** na página **Perfis de depreciação**, os ativos fixos que são atribuídos ao perfil de depreciação são depreciados pela mesma porcentagem em cada período de depreciação.</span><span class="sxs-lookup"><span data-stu-id="5b0aa-105">When you set up a fixed asset depreciation profile and select **200% reducing balance** in the **Method** field on the **Depreciation profiles** page, fixed assets that are assigned the depreciation profile are depreciated by the same percentage in each depreciation period.</span></span> <span data-ttu-id="5b0aa-106">A porcentagem é calculada com base na vida útil do ativo.</span><span class="sxs-lookup"><span data-stu-id="5b0aa-106">The percentage is calculated based on the service life of the asset.</span></span> <span data-ttu-id="5b0aa-107">Por exemplo, se um ativo tiver uma vida útil de cinco anos, será calculada uma porcentagem de 40% (200%/5).</span><span class="sxs-lookup"><span data-stu-id="5b0aa-107">For example, if an asset has a service life of five years, the percentage is calculated as 40 percent (200% ÷ 5).</span></span> 

<span data-ttu-id="5b0aa-108">Esse método também é conhecido como saldo decrescente duplo.</span><span class="sxs-lookup"><span data-stu-id="5b0aa-108">This method is also known as double declining balance.</span></span>

<span data-ttu-id="5b0aa-109">Para configurar uma depreciação por declínio de 200%, você também deve selecionar opções no campo **Ano de depreciação** e no campo **Frequência do período** na página **Perfis de depreciação**.</span><span class="sxs-lookup"><span data-stu-id="5b0aa-109">To set up 200% reducing balance depreciation, you must also select options in the **Depreciation year** field and the **Period frequency** field on the **Depreciation profiles** page.</span></span> <span data-ttu-id="5b0aa-110">As opções disponíveis no campo **Frequência do período** variam, dependendo do valor selecionado no campo **Ano de depreciação**.</span><span class="sxs-lookup"><span data-stu-id="5b0aa-110">The options that are available in the **Period frequency** field vary, depending on the value that you select in the **Depreciation year** field.</span></span>

## <a name="select-a-depreciation-year"></a><span data-ttu-id="5b0aa-111">Selecione um ano de depreciação</span><span class="sxs-lookup"><span data-stu-id="5b0aa-111">Select a depreciation year</span></span>
<span data-ttu-id="5b0aa-112">Você pode selecionar **Calendário** ou **Fiscal** no campo **Ano de depreciação** na página **Perfis de depreciação**.</span><span class="sxs-lookup"><span data-stu-id="5b0aa-112">You can select either **Calendar** or **Fiscal** in the **Depreciation year** field on the **Depreciation profiles** page.</span></span> <span data-ttu-id="5b0aa-113">O valor padrão é **Calendário**.</span><span class="sxs-lookup"><span data-stu-id="5b0aa-113">The default value is **Calendar**.</span></span> 

<span data-ttu-id="5b0aa-114">Sua seleção determinará as opções disponíveis no campo **Frequência do período**.</span><span class="sxs-lookup"><span data-stu-id="5b0aa-114">Your selection determines the options that are available in the **Period frequency** field.</span></span> <span data-ttu-id="5b0aa-115">Esse campo define os valores e as datas de lançamento de acúmulo da depreciação ao longo do ano de calendário.</span><span class="sxs-lookup"><span data-stu-id="5b0aa-115">This field defines the depreciation accrual posting dates and amounts throughout the calendar year.</span></span>

### <a name="calendar"></a><span data-ttu-id="5b0aa-116">Calendário</span><span class="sxs-lookup"><span data-stu-id="5b0aa-116">Calendar</span></span>

<span data-ttu-id="5b0aa-117">Você pode optar por manter o valor padrão no campo **Ano de depreciação**, **Calendário**.</span><span class="sxs-lookup"><span data-stu-id="5b0aa-117">You can keep the default value in the **Depreciation year** field, **Calendar**.</span></span> 

<span data-ttu-id="5b0aa-118">A opção **Calendário** atualiza a base de depreciação em 1º de janeiro de cada ano.</span><span class="sxs-lookup"><span data-stu-id="5b0aa-118">The **Calendar** option updates the depreciation base on January 1 of each year.</span></span> <span data-ttu-id="5b0aa-119">Normalmente, a depreciação é o valor líquido contábil menos o valor de sucata.</span><span class="sxs-lookup"><span data-stu-id="5b0aa-119">Typically, the depreciation is the net book value minus the scrap value.</span></span> <span data-ttu-id="5b0aa-120">Nos exemplos a seguir deste tópico, a base de depreciação é o numerador na primeira expressão da coluna de cálculos.</span><span class="sxs-lookup"><span data-stu-id="5b0aa-120">In the examples later in this topic, the depreciation base is the numerator in the first expression in the calculations column.</span></span> 

<span data-ttu-id="5b0aa-121">Se você selecionar **Calendário** como o ano de depreciação, as seguintes opções ficarão disponíveis no campo **Frequência do período**:</span><span class="sxs-lookup"><span data-stu-id="5b0aa-121">If you select **Calendar** as the depreciation year, the following options are available in the **Period frequency** field:</span></span>

-   <span data-ttu-id="5b0aa-122">**Anual** lança um valor em 31 de dezembro.</span><span class="sxs-lookup"><span data-stu-id="5b0aa-122">**Yearly** posts an amount on December 31.</span></span>
-   <span data-ttu-id="5b0aa-123">**Mensal** lança um valor mensal ao final de cada mês do calendário.</span><span class="sxs-lookup"><span data-stu-id="5b0aa-123">**Monthly** posts a monthly amount at the end of each calendar month.</span></span>
-   <span data-ttu-id="5b0aa-124">**Trimestral** lança um valor trimestral ao final de cada trimestre do calendário (31 de março, 30 de junho, 30 de setembro e 31 de dezembro).</span><span class="sxs-lookup"><span data-stu-id="5b0aa-124">**Quarterly** posts a quarterly amount at the end of each calendar quarter (March 31, June 30, September 30, and December 31).</span></span>
-   <span data-ttu-id="5b0aa-125">**Semestral** lança um valor semestral no final de cada semestre do calendário (30 de junho e 31 de dezembro).</span><span class="sxs-lookup"><span data-stu-id="5b0aa-125">**Half-Yearly** posts a half-yearly amount at the calendar half year (June 30 and December 31).</span></span>
-   <span data-ttu-id="5b0aa-126">**Diário** lança o valor de depreciação do método de depreciação diária usando uma transação para cada dia.</span><span class="sxs-lookup"><span data-stu-id="5b0aa-126">**Daily** posts the depreciation amount for the daily depreciation method by using one transaction for each day.</span></span>

### <a name="fiscal"></a><span data-ttu-id="5b0aa-127">fiscal</span><span class="sxs-lookup"><span data-stu-id="5b0aa-127">Fiscal</span></span>

<span data-ttu-id="5b0aa-128">Se você selecionar **Fiscal** no campo **Ano de depreciação**, a depreciação com declínio de 200% será calculada com base no ano fiscal especificado para o registro de depreciação, ou para o calendário fiscal selecionado na página **Razão**.</span><span class="sxs-lookup"><span data-stu-id="5b0aa-128">If you select **Fiscal** in the **Depreciation** year field, 200% reducing balance depreciation is calculated based on the fiscal year for the fiscal calendar that is specified for the book, or for the fiscal calendar that is selected on the **Ledger** page.</span></span> <span data-ttu-id="5b0aa-129">Os calendários fiscais são configurados na página **Calendários fiscais**.</span><span class="sxs-lookup"><span data-stu-id="5b0aa-129">Fiscal calendars are set up on the **Fiscal calendars** page.</span></span> 

<span data-ttu-id="5b0aa-130">Por exemplo, no ano fiscal entre 1 de julho e 30 de junho, o cálculo da depreciação começa em 1 de julho.</span><span class="sxs-lookup"><span data-stu-id="5b0aa-130">For example, for the fiscal year July 1 through June 30, the depreciation calculation starts on July 1.</span></span> <span data-ttu-id="5b0aa-131">O ano fiscal pode ter mais ou menos do que 12 meses.</span><span class="sxs-lookup"><span data-stu-id="5b0aa-131">The fiscal year can be longer or shorter than 12 months.</span></span> <span data-ttu-id="5b0aa-132">A depreciação é ajustada para cada período fiscal.</span><span class="sxs-lookup"><span data-stu-id="5b0aa-132">The depreciation is adjusted for each period.</span></span> <span data-ttu-id="5b0aa-133">A duração do próximo ano fiscal será determinada pela configuração de períodos na página **Calendários fiscais**.</span><span class="sxs-lookup"><span data-stu-id="5b0aa-133">The length of the next fiscal year is determined by the setup of periods on the **Fiscal calendars** page.</span></span> 

<span data-ttu-id="5b0aa-134">Quando **Fiscal** for selecionado como o ano de depreciação, as seguintes opções ficarão disponíveis no campo **Frequência do período**:</span><span class="sxs-lookup"><span data-stu-id="5b0aa-134">When **Fiscal** is selected as the depreciation year, the following options are available in the **Period frequency** field:</span></span>

-   <span data-ttu-id="5b0aa-135">**Anual** lança o valor total da depreciação calculada para o ano fiscal como um valor, no último dia do ano fiscal.</span><span class="sxs-lookup"><span data-stu-id="5b0aa-135">**Yearly** posts the total amount of the depreciation that is calculated for the fiscal year as one amount, on the last day of the fiscal year.</span></span>
-   <span data-ttu-id="5b0aa-136">**Período fiscal** lança o valor total da depreciação calculada para o ano fiscal.</span><span class="sxs-lookup"><span data-stu-id="5b0aa-136">**Fiscal period** posts the total amount of the depreciation that is calculated for the fiscal year.</span></span> <span data-ttu-id="5b0aa-137">Esse valor é acumulado nos períodos fiscais definidos na página **Calendários fiscais**.</span><span class="sxs-lookup"><span data-stu-id="5b0aa-137">This amount is accrued into the fiscal periods that are defined on the **Fiscal calendars** page.</span></span>

## <a name="example-of-200-reducing-balance-depreciation"></a><span data-ttu-id="5b0aa-138">Exemplo de depreciação com declínio de 200%</span><span class="sxs-lookup"><span data-stu-id="5b0aa-138">Example of 200% reducing balance depreciation</span></span>

|                                |        |
|--------------------------------|--------|
| <span data-ttu-id="5b0aa-139">Custo de Aquisição</span><span class="sxs-lookup"><span data-stu-id="5b0aa-139">Acquisition cost</span></span>               | <span data-ttu-id="5b0aa-140">11.000</span><span class="sxs-lookup"><span data-stu-id="5b0aa-140">11,000</span></span> |
| <span data-ttu-id="5b0aa-141">valor residual</span><span class="sxs-lookup"><span data-stu-id="5b0aa-141">Salvage value</span></span>                  | <span data-ttu-id="5b0aa-142">1.000</span><span class="sxs-lookup"><span data-stu-id="5b0aa-142">1, 000</span></span> |
| <span data-ttu-id="5b0aa-143">Base de depreciação</span><span class="sxs-lookup"><span data-stu-id="5b0aa-143">Depreciation base</span></span>              | <span data-ttu-id="5b0aa-144">10.000</span><span class="sxs-lookup"><span data-stu-id="5b0aa-144">10,000</span></span> |
| <span data-ttu-id="5b0aa-145">Anos de vida útil</span><span class="sxs-lookup"><span data-stu-id="5b0aa-145">Service life years</span></span>             | <span data-ttu-id="5b0aa-146">5</span><span class="sxs-lookup"><span data-stu-id="5b0aa-146">5</span></span>      |
| <span data-ttu-id="5b0aa-147">porcentagem de depreciação</span><span class="sxs-lookup"><span data-stu-id="5b0aa-147">Yearly depreciation percentage</span></span> | <span data-ttu-id="5b0aa-148">40%</span><span class="sxs-lookup"><span data-stu-id="5b0aa-148">40%</span></span>    |

<span data-ttu-id="5b0aa-149">O método por declínio de 200% divide 200% pelos anos de vida útil.</span><span class="sxs-lookup"><span data-stu-id="5b0aa-149">The 200% reducing balance method divides 200 percent by the service life years.</span></span> <span data-ttu-id="5b0aa-150">Essa porcentagem será multiplicada pelo valor líquido contábil do ativo para determinar o valor da depreciação anual.</span><span class="sxs-lookup"><span data-stu-id="5b0aa-150">That percentage will be multiplied by the net book value of the asset to determine the depreciation amount for the year.</span></span>

| <span data-ttu-id="5b0aa-151">Período</span><span class="sxs-lookup"><span data-stu-id="5b0aa-151">Period</span></span> | <span data-ttu-id="5b0aa-152">Cálculo do valor de depreciação anual</span><span class="sxs-lookup"><span data-stu-id="5b0aa-152">Calculation of the yearly depreciation amount</span></span> | <span data-ttu-id="5b0aa-153">Valor Contábil</span><span class="sxs-lookup"><span data-stu-id="5b0aa-153">Book value</span></span>             | <span data-ttu-id="5b0aa-154">Valor líquido contábil no final do ano</span><span class="sxs-lookup"><span data-stu-id="5b0aa-154">Net book value at the end of the year</span></span> |
|--------|-----------------------------------------------|------------------------|---------------------------------------|
| <span data-ttu-id="5b0aa-155">Ano 1</span><span class="sxs-lookup"><span data-stu-id="5b0aa-155">Year 1</span></span> | <span data-ttu-id="5b0aa-156">(11.000 – 1.000) × 40% = 4.000</span><span class="sxs-lookup"><span data-stu-id="5b0aa-156">(11,000 – 1,000) × 40% = 4,000</span></span>                | <span data-ttu-id="5b0aa-157">11.000 – 4.000 = 7.000</span><span class="sxs-lookup"><span data-stu-id="5b0aa-157">11,000 – 4,000 = 7,000</span></span> | <span data-ttu-id="5b0aa-158">11.000 – 1.000 – 4.000 = 6.000</span><span class="sxs-lookup"><span data-stu-id="5b0aa-158">11,000 – 1,000 – 4,000 = 6,000</span></span>        |
| <span data-ttu-id="5b0aa-159">Ano 2</span><span class="sxs-lookup"><span data-stu-id="5b0aa-159">Year 2</span></span> | <span data-ttu-id="5b0aa-160">6.000 × 40% = 2.400</span><span class="sxs-lookup"><span data-stu-id="5b0aa-160">6,000 × 40% = 2,400</span></span>                           | <span data-ttu-id="5b0aa-161">7.000 – 2.400 = 4.600</span><span class="sxs-lookup"><span data-stu-id="5b0aa-161">7,000 – 2,400 = 4,600</span></span>  | <span data-ttu-id="5b0aa-162">6.000 – 2.400 = 3.600</span><span class="sxs-lookup"><span data-stu-id="5b0aa-162">6,000 – 2,400 = 3,600</span></span>                 |
| <span data-ttu-id="5b0aa-163">Ano 3</span><span class="sxs-lookup"><span data-stu-id="5b0aa-163">Year 3</span></span> | <span data-ttu-id="5b0aa-164">3.600 × 40% = 1.440</span><span class="sxs-lookup"><span data-stu-id="5b0aa-164">3,600 × 40% = 1,440</span></span>                           | <span data-ttu-id="5b0aa-165">4.600 – 1.440 = 3.160</span><span class="sxs-lookup"><span data-stu-id="5b0aa-165">4,600 – 1,440 = 3,160</span></span>  | <span data-ttu-id="5b0aa-166">3.600 – 1.440 = 2.160</span><span class="sxs-lookup"><span data-stu-id="5b0aa-166">3,600 – 1,440 = 2,160</span></span>                 |

> [!NOTE] 
> <span data-ttu-id="5b0aa-167">Normalmente, quando o valor que é calculado usando o método de depreciação por declínio de 200% se torna menor do que o valor que será calculado usando o método linear, há uma conversão para o método linear método para a vida restante.</span><span class="sxs-lookup"><span data-stu-id="5b0aa-167">Typically, when the amount that is calculated by using the 200% reducing balance depreciation method becomes less than the amount that would be calculated by using the straight line method, there is a conversion to the straight line method for the remaining life.</span></span>




