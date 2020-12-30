---
title: depreciação com declínio de 125%
description: Este artigo fornece uma visão geral do método de saldo de reduzem de 125 de porcentagem de depreciação.
author: saraschi2
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetDepreciationProfile
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 13871
ms.assetid: 3abc263e-59d6-4f1a-986d-1be388948bd3
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5af050fb6099b583be4e9c60ba56dacf38d31c08
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4440469"
---
# <a name="125-percent-reducing-balance-depreciation"></a><span data-ttu-id="a7a09-103">depreciação com declínio de 125%</span><span class="sxs-lookup"><span data-stu-id="a7a09-103">125 percent reducing balance depreciation</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="a7a09-104">Este artigo fornece uma visão geral do método de saldo de reduzem de 125 de porcentagem de depreciação.</span><span class="sxs-lookup"><span data-stu-id="a7a09-104">This article gives an overview of the 125 percent reducing balance method of depreciation.</span></span>

<span data-ttu-id="a7a09-105">Ao configurar um perfil de depreciação de ativos fixos e selecionar **declínio de 125%** no campo **Método** na página **Perfis de depreciação**, os ativos fixos que são atribuídos ao perfil de depreciação são depreciados pela mesma porcentagem em cada período de depreciação.</span><span class="sxs-lookup"><span data-stu-id="a7a09-105">When you set up a fixed asset depreciation profile and select **125% reducing balance** in the **Method** field on the **Depreciation profiles** page, fixed assets that are assigned to the depreciation profile are depreciated by the same percentage in each depreciation period.</span></span> <span data-ttu-id="a7a09-106">Essa porcentagem é calculada com base na vida útil do ativo.</span><span class="sxs-lookup"><span data-stu-id="a7a09-106">This percentage is calculated based on the service life of the asset.</span></span> <span data-ttu-id="a7a09-107">Por exemplo, se um ativo tiver uma vida útil de cinco anos, será calculada uma porcentagem de 25% (125 ÷ 5).</span><span class="sxs-lookup"><span data-stu-id="a7a09-107">For example, if an asset has a service life of five years, the percentage is calculated as 25 percent (125% ÷ 5).</span></span>

<span data-ttu-id="a7a09-108">Para configurar uma depreciação por declínio de 125%, você também deve selecionar opções no campo **Ano de depreciação** e no campo **Frequência do período** na página **Perfis de depreciação**.</span><span class="sxs-lookup"><span data-stu-id="a7a09-108">To set up 125% reducing balance depreciation, you must also select options in the **Depreciation year** field and the **Period frequency** field on the **Depreciation profiles** page.</span></span> <span data-ttu-id="a7a09-109">As opções disponíveis no campo **Frequência do período** variam, dependendo do valor selecionado no campo **Ano de depreciação**.</span><span class="sxs-lookup"><span data-stu-id="a7a09-109">The options that are available in the **Period frequency** field vary, depending on the value that is selected in the **Depreciation year** field.</span></span>

## <a name="select-a-depreciation-year"></a><span data-ttu-id="a7a09-110">Selecione um ano de depreciação</span><span class="sxs-lookup"><span data-stu-id="a7a09-110">Select a depreciation year</span></span>
<span data-ttu-id="a7a09-111">Você pode selecionar **Calendário** ou **Fiscal** no campo **Ano de depreciação** na página **Perfis de depreciação**.</span><span class="sxs-lookup"><span data-stu-id="a7a09-111">You can select either **Calendar** or **Fiscal** in the **Depreciation year** field on the **Depreciation profiles** page.</span></span> <span data-ttu-id="a7a09-112">O valor padrão é **Calendário**.</span><span class="sxs-lookup"><span data-stu-id="a7a09-112">The default value is **Calendar**.</span></span> 

<span data-ttu-id="a7a09-113">Sua seleção determinará as opções disponíveis no campo **Frequência do período**.</span><span class="sxs-lookup"><span data-stu-id="a7a09-113">Your selection determines the options that are available in the **Period frequency** field.</span></span> <span data-ttu-id="a7a09-114">Esse campo define os valores e as datas de lançamento de acúmulo da depreciação ao longo do ano de calendário.</span><span class="sxs-lookup"><span data-stu-id="a7a09-114">This field defines the depreciation accrual posting dates and amounts throughout the calendar year.</span></span>

### <a name="calendar"></a><span data-ttu-id="a7a09-115">Calendário</span><span class="sxs-lookup"><span data-stu-id="a7a09-115">Calendar</span></span>

<span data-ttu-id="a7a09-116">Você pode optar por manter o valor padrão no campo **Ano de depreciação**, **Calendário**.</span><span class="sxs-lookup"><span data-stu-id="a7a09-116">You can keep the default value in the **Depreciation year** field, **Calendar**.</span></span> 

<span data-ttu-id="a7a09-117">A opção **Calendário** atualiza a base de depreciação em 1º de janeiro de cada ano.</span><span class="sxs-lookup"><span data-stu-id="a7a09-117">The **Calendar** option updates the depreciation base on January 1 of each year.</span></span> <span data-ttu-id="a7a09-118">Normalmente, a base de depreciação é o valor líquido contábil menos o valor de sucata.</span><span class="sxs-lookup"><span data-stu-id="a7a09-118">Typically, the depreciation base is the net book value minus the scrap value.</span></span> <span data-ttu-id="a7a09-119">Nos exemplos a seguir deste tópico, a base de depreciação é o numerador na primeira expressão da coluna de cálculos.</span><span class="sxs-lookup"><span data-stu-id="a7a09-119">In the examples later in this topic, the depreciation base is the numerator in the first expression in the calculations column.</span></span> 

<span data-ttu-id="a7a09-120">Se você selecionar **Calendário** como o ano de depreciação, as seguintes opções ficarão disponíveis no campo **Frequência do período**:</span><span class="sxs-lookup"><span data-stu-id="a7a09-120">If you select **Calendar** as the depreciation year, the following options are available in the **Period frequency** field:</span></span>

-   <span data-ttu-id="a7a09-121">**Anual** lança um valor em 31 de dezembro.</span><span class="sxs-lookup"><span data-stu-id="a7a09-121">**Yearly** posts an amount on December 31.</span></span>
-   <span data-ttu-id="a7a09-122">**Mensal** lança um valor mensal ao final de cada mês do calendário.</span><span class="sxs-lookup"><span data-stu-id="a7a09-122">**Monthly** posts a monthly amount at the end of each calendar month.</span></span>
-   <span data-ttu-id="a7a09-123">**Trimestral** lança um valor trimestral ao final de cada trimestre do calendário (31 de março, 30 de junho, 30 de setembro e 31 de dezembro).</span><span class="sxs-lookup"><span data-stu-id="a7a09-123">**Quarterly** posts a quarterly amount at the end of each calendar quarter (March 31, June 30, September 30, and December 31).</span></span>
-   <span data-ttu-id="a7a09-124">**Semestral** lança um valor semestral no final de cada semestre do calendário (30 de junho e 31 de dezembro).</span><span class="sxs-lookup"><span data-stu-id="a7a09-124">**Half-Yearly** posts a half-yearly amount at the calendar half year (June 30 and December 31).</span></span>
-   <span data-ttu-id="a7a09-125">**Diário** lança o valor de depreciação do método de depreciação diária usando uma transação para cada dia.</span><span class="sxs-lookup"><span data-stu-id="a7a09-125">**Daily** posts the depreciation amount for the daily depreciation method by using one transaction for each day.</span></span>

### <a name="fiscal"></a><span data-ttu-id="a7a09-126">fiscal</span><span class="sxs-lookup"><span data-stu-id="a7a09-126">Fiscal</span></span>

<span data-ttu-id="a7a09-127">Se você selecionar **Fiscal** no campo **Ano de depreciação**, a depreciação com declínio de 125% será calculada com base no ano fiscal especificado para o registro de depreciação, ou para o calendário fiscal selecionado na página **Razão**.</span><span class="sxs-lookup"><span data-stu-id="a7a09-127">If you select **Fiscal** in the **Depreciation year** field, 125% reducing depreciation is calculated based on the fiscal year for the fiscal calendar that is specified for the book, or for the fiscal calendar that is selected on the **Ledger** page.</span></span> <span data-ttu-id="a7a09-128">Os calendários fiscais são configurados na página **Calendários fiscais**.</span><span class="sxs-lookup"><span data-stu-id="a7a09-128">Fiscal calendars are set up on the **Fiscal calendars** page.</span></span> 

<span data-ttu-id="a7a09-129">Por exemplo, no ano fiscal entre 1 de julho e 30 de junho, o cálculo da depreciação começa em 1 de julho.</span><span class="sxs-lookup"><span data-stu-id="a7a09-129">For example, for the fiscal year July 1 through June 30, the depreciation calculation starts on July 1.</span></span> <span data-ttu-id="a7a09-130">O ano fiscal pode ter mais ou menos do que 12 meses.</span><span class="sxs-lookup"><span data-stu-id="a7a09-130">The fiscal year can be longer or shorter than 12 months.</span></span> <span data-ttu-id="a7a09-131">A depreciação é ajustada automaticamente para cada período fiscal e a duração do próximo ano fiscal é determinada pela configuração de períodos na página **Calendários fiscais**.</span><span class="sxs-lookup"><span data-stu-id="a7a09-131">The depreciation is automatically adjusted for each period, and the length of the next fiscal year is determined by the setup of periods on the **Fiscal calendars** page.</span></span> 

<span data-ttu-id="a7a09-132">Se você selecionar **Fiscal** como o ano de depreciação, as opções a seguir ficarão disponíveis no campo **Frequência do período**:</span><span class="sxs-lookup"><span data-stu-id="a7a09-132">If you select **Fiscal** as the depreciation year, the following options are available in the **Period frequency** field:</span></span>

-   <span data-ttu-id="a7a09-133">**Anual** lança o valor total da depreciação calculada para o ano fiscal como um valor, no último dia do ano fiscal.</span><span class="sxs-lookup"><span data-stu-id="a7a09-133">**Yearly** posts the total amount of the depreciation that is calculated for the fiscal year as one amount, on the last day of the fiscal year.</span></span>
-   <span data-ttu-id="a7a09-134">**Período fiscal** lança o valor total da depreciação calculada para o ano fiscal.</span><span class="sxs-lookup"><span data-stu-id="a7a09-134">**Fiscal period** posts the total amount of the depreciation that is calculated for the fiscal year.</span></span> <span data-ttu-id="a7a09-135">Esse valor é acumulado nos períodos fiscais definidos na página **Calendários fiscais**.</span><span class="sxs-lookup"><span data-stu-id="a7a09-135">This amount is accrued into the fiscal periods that are defined on the **Fiscal calendars** page.</span></span>

## <a name="example-of-125-reducing-balance-depreciation"></a><span data-ttu-id="a7a09-136">Exemplo de depreciação com declínio de 125%</span><span class="sxs-lookup"><span data-stu-id="a7a09-136">Example of 125% reducing balance depreciation</span></span>

|                                |        |
|--------------------------------|--------|
| <span data-ttu-id="a7a09-137">Custo de Aquisição</span><span class="sxs-lookup"><span data-stu-id="a7a09-137">Acquisition cost</span></span>               | <span data-ttu-id="a7a09-138">11.000</span><span class="sxs-lookup"><span data-stu-id="a7a09-138">11,000</span></span> |
| <span data-ttu-id="a7a09-139">valor residual</span><span class="sxs-lookup"><span data-stu-id="a7a09-139">Salvage value</span></span>                  | <span data-ttu-id="a7a09-140">1.000</span><span class="sxs-lookup"><span data-stu-id="a7a09-140">1,000</span></span>  |
| <span data-ttu-id="a7a09-141">Base de depreciação</span><span class="sxs-lookup"><span data-stu-id="a7a09-141">Depreciation base</span></span>              | <span data-ttu-id="a7a09-142">10.000</span><span class="sxs-lookup"><span data-stu-id="a7a09-142">10,000</span></span> |
| <span data-ttu-id="a7a09-143">Anos de vida útil</span><span class="sxs-lookup"><span data-stu-id="a7a09-143">Service life years</span></span>             | <span data-ttu-id="a7a09-144">5</span><span class="sxs-lookup"><span data-stu-id="a7a09-144">5</span></span>      |
| <span data-ttu-id="a7a09-145">porcentagem de depreciação</span><span class="sxs-lookup"><span data-stu-id="a7a09-145">Yearly depreciation percentage</span></span> | <span data-ttu-id="a7a09-146">25%</span><span class="sxs-lookup"><span data-stu-id="a7a09-146">25%</span></span>    |

<span data-ttu-id="a7a09-147">O método por declínio de 125% divide 125% pelos anos de vida útil.</span><span class="sxs-lookup"><span data-stu-id="a7a09-147">The 125% reducing balance method divides 125 percent by the service life years.</span></span> <span data-ttu-id="a7a09-148">Essa porcentagem será multiplicada pelo valor líquido contábil do ativo para determinar o valor da depreciação anual.</span><span class="sxs-lookup"><span data-stu-id="a7a09-148">That percentage will be multiplied by the net book value of the asset to determine the depreciation amount for the year.</span></span>

| <span data-ttu-id="a7a09-149">Período</span><span class="sxs-lookup"><span data-stu-id="a7a09-149">Period</span></span> | <span data-ttu-id="a7a09-150">Cálculo do valor de depreciação anual</span><span class="sxs-lookup"><span data-stu-id="a7a09-150">Calculation of the yearly depreciation amount</span></span> | <span data-ttu-id="a7a09-151">Valor Contábil</span><span class="sxs-lookup"><span data-stu-id="a7a09-151">Book value</span></span>                    | <span data-ttu-id="a7a09-152">Valor líquido contábil no final do ano</span><span class="sxs-lookup"><span data-stu-id="a7a09-152">Net book value at the end of the year</span></span> |
|--------|-----------------------------------------------|-------------------------------|---------------------------------------|
| <span data-ttu-id="a7a09-153">Ano 1</span><span class="sxs-lookup"><span data-stu-id="a7a09-153">Year 1</span></span> | <span data-ttu-id="a7a09-154">(11.000 – 1.000) × 25% = 2.500</span><span class="sxs-lookup"><span data-stu-id="a7a09-154">(11,000 – 1,000) × 25% = 2,500</span></span>                | <span data-ttu-id="a7a09-155">(11.000 – 2.500) = 8.500</span><span class="sxs-lookup"><span data-stu-id="a7a09-155">(11,000 – 2,500) = 8,500</span></span>      | <span data-ttu-id="a7a09-156">(11.000 – 1.000 – 2.500) = 7.500</span><span class="sxs-lookup"><span data-stu-id="a7a09-156">(11,000 – 1,000 – 2,500) = 7,500</span></span>      |
| <span data-ttu-id="a7a09-157">Ano 2</span><span class="sxs-lookup"><span data-stu-id="a7a09-157">Year 2</span></span> | <span data-ttu-id="a7a09-158">7.500 × 25% = 1.875</span><span class="sxs-lookup"><span data-stu-id="a7a09-158">7,500 × 25% = 1,875</span></span>                           | <span data-ttu-id="a7a09-159">(8.500 – 1.875) = 6.625</span><span class="sxs-lookup"><span data-stu-id="a7a09-159">(8,500 – 1,875) = 6,625</span></span>       | <span data-ttu-id="a7a09-160">(7.500 – 1.875) = 5.625</span><span class="sxs-lookup"><span data-stu-id="a7a09-160">(7,500 – 1,875) = 5,625</span></span>               |
| <span data-ttu-id="a7a09-161">Ano 3</span><span class="sxs-lookup"><span data-stu-id="a7a09-161">Year 3</span></span> | <span data-ttu-id="a7a09-162">5.625 × 25% = 1.406,25</span><span class="sxs-lookup"><span data-stu-id="a7a09-162">5,625 × 25% = 1,406.25</span></span>                        | <span data-ttu-id="a7a09-163">(6.625 – 1.406,25) = 5.218,75</span><span class="sxs-lookup"><span data-stu-id="a7a09-163">(6,625 – 1,406.25) = 5,218.75</span></span> | <span data-ttu-id="a7a09-164">(5.625 – 1.406,25) = 4.218,75</span><span class="sxs-lookup"><span data-stu-id="a7a09-164">(5,625 – 1,406.25) = 4,218.75</span></span>         |

> [!NOTE] 
> <span data-ttu-id="a7a09-165">Normalmente, quando o valor que é calculado usando o método de depreciação por declínio de 125%, ele se torna menor do que o valor que será calculado usando o método linear. Há uma conversão para o método linear método para a vida restante.</span><span class="sxs-lookup"><span data-stu-id="a7a09-165">Typically, when the amount that is calculated by using the 125% reducing balance depreciation method becomes less than the amount that would be calculated by using the straight line method, there is a conversion to the straight line method for the remaining life.</span></span>



