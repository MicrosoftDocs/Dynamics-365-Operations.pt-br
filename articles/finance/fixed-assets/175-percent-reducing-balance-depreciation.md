---
title: Depreciação por declínio de 175%
description: Este tópico fornece uma visão geral do método de depreciação de redução de 175% do saldo.
author: saraschi2
ms.date: 10/30/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetDepreciationProfile
audience: Application User
ms.reviewer: roschlom
ms.custom: 13911
ms.assetid: cc5d001f-bcfe-4602-9ec1-9e265e9fd188
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f0747c34a4b28340227209adadf367f672deb1ab
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5827137"
---
# <a name="175-percent-reducing-balance-depreciation"></a><span data-ttu-id="ffe3b-103">Depreciação por declínio de 175 por cento</span><span class="sxs-lookup"><span data-stu-id="ffe3b-103">175 percent reducing balance depreciation</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="ffe3b-104">Este tópico fornece uma visão geral do método de depreciação de redução de 175% do saldo.</span><span class="sxs-lookup"><span data-stu-id="ffe3b-104">This topic gives an overview of the 175 percent reducing balance method of depreciation.</span></span>

<span data-ttu-id="ffe3b-105">Ao configurar um perfil de depreciação de ativos fixos e selecionar **declínio de 175%** no campo **Método** na página **Perfis de depreciação**, os ativos fixos que são atribuídos ao perfil de depreciação são depreciados pela mesma porcentagem em cada período de depreciação.</span><span class="sxs-lookup"><span data-stu-id="ffe3b-105">When you set up a fixed asset depreciation profile and select **175% reducing balance** in the **Method** field on the **Depreciation profiles** page, fixed assets that are assigned the depreciation profile are depreciated by the same percentage in each depreciation period.</span></span> 

<span data-ttu-id="ffe3b-106">Para configurar uma depreciação por declínio de 175%, você também deve selecionar opções no campo **Ano de depreciação** e no campo **Frequência do período** na página **Perfis de depreciação**.</span><span class="sxs-lookup"><span data-stu-id="ffe3b-106">To set up 175% reducing balance depreciation, you must also select options in the **Depreciation year** field and the **Period frequency** field on the **Depreciation profiles** page.</span></span> <span data-ttu-id="ffe3b-107">As opções disponíveis no campo **Frequência do período** variam, dependendo do valor selecionado no campo **Ano de depreciação**.</span><span class="sxs-lookup"><span data-stu-id="ffe3b-107">The options that are available in the **Period frequency** field vary, depending on the value that is selected in the **Depreciation year** field.</span></span>

## <a name="select-a-depreciation-year"></a><span data-ttu-id="ffe3b-108">Selecione um ano de depreciação</span><span class="sxs-lookup"><span data-stu-id="ffe3b-108">Select a depreciation year</span></span>
<span data-ttu-id="ffe3b-109">Você pode selecionar **Calendário** ou **Fiscal** no campo **Ano de depreciação** na página **Perfis de depreciação**.</span><span class="sxs-lookup"><span data-stu-id="ffe3b-109">You can select either **Calendar** or **Fiscal** in the **Depreciation year** field on the **Depreciation profiles** page.</span></span> <span data-ttu-id="ffe3b-110">O valor padrão é **Calendário**.</span><span class="sxs-lookup"><span data-stu-id="ffe3b-110">The default value is **Calendar**.</span></span> 

<span data-ttu-id="ffe3b-111">Sua seleção determinará as opções disponíveis no campo **Frequência do período**.</span><span class="sxs-lookup"><span data-stu-id="ffe3b-111">Your selection determines the options that are available in the **Period frequency** field.</span></span> <span data-ttu-id="ffe3b-112">Esse campo define os valores e as datas de lançamento de acúmulo da depreciação ao longo do ano de calendário.</span><span class="sxs-lookup"><span data-stu-id="ffe3b-112">This field defines the depreciation accrual posting dates and amounts throughout the calendar year.</span></span>

### <a name="calendar"></a><span data-ttu-id="ffe3b-113">Calendário</span><span class="sxs-lookup"><span data-stu-id="ffe3b-113">Calendar</span></span>

<span data-ttu-id="ffe3b-114">Você pode optar por manter o valor padrão no campo **Ano de depreciação**, **Calendário**.</span><span class="sxs-lookup"><span data-stu-id="ffe3b-114">You can keep the default value in the **Depreciation year** field, **Calendar**.</span></span> 

<span data-ttu-id="ffe3b-115">A opção **Calendário** atualiza a base de depreciação em 1º de janeiro de cada ano.</span><span class="sxs-lookup"><span data-stu-id="ffe3b-115">The **Calendar** option updates the depreciation base on January 1 of each year.</span></span> <span data-ttu-id="ffe3b-116">Normalmente, a base de depreciação é o valor líquido contábil menos o valor de sucata.</span><span class="sxs-lookup"><span data-stu-id="ffe3b-116">Typically, the depreciation base is the net book value minus the scrap value.</span></span> <span data-ttu-id="ffe3b-117">Nos exemplos a seguir deste tópico, a base de depreciação é o numerador na primeira expressão da coluna de cálculos.</span><span class="sxs-lookup"><span data-stu-id="ffe3b-117">In the examples later in this topic, the depreciation base is the numerator in the first expression in the calculations column.</span></span> 

<span data-ttu-id="ffe3b-118">Se você selecionar **Calendário** como o ano de depreciação, as seguintes opções ficarão disponíveis no campo **Frequência do período**:</span><span class="sxs-lookup"><span data-stu-id="ffe3b-118">If you select **Calendar** as the depreciation year, the following options are available in the **Period frequency** field:</span></span>

-   <span data-ttu-id="ffe3b-119">**Anual** lança um valor em 31 de dezembro.</span><span class="sxs-lookup"><span data-stu-id="ffe3b-119">**Yearly** posts an amount on December 31.</span></span>
-   <span data-ttu-id="ffe3b-120">**Mensal** lança um valor mensal ao final de cada mês do calendário.</span><span class="sxs-lookup"><span data-stu-id="ffe3b-120">**Monthly** posts a monthly amount at the end of each calendar month.</span></span>
-   <span data-ttu-id="ffe3b-121">**Trimestral** lança um valor trimestral ao final de cada trimestre do calendário (31 de março, 30 de junho, 30 de setembro e 31 de dezembro).</span><span class="sxs-lookup"><span data-stu-id="ffe3b-121">**Quarterly** posts a quarterly amount at the end of each calendar quarter (March 31, June 30, September 30, and December 31).</span></span>
-   <span data-ttu-id="ffe3b-122">**Semestral** lança um valor semestral no final de cada semestre do calendário (30 de junho e 31 de dezembro).</span><span class="sxs-lookup"><span data-stu-id="ffe3b-122">**Half-Yearly** posts a half-yearly amount at the calendar half year (June 30 and December 31).</span></span>
-   <span data-ttu-id="ffe3b-123">**Diário** lança o valor de depreciação do método de depreciação diária usando uma transação para cada dia.</span><span class="sxs-lookup"><span data-stu-id="ffe3b-123">**Daily** posts the depreciation amount for the daily depreciation method by using one transaction for each day.</span></span>

### <a name="fiscal"></a><span data-ttu-id="ffe3b-124">fiscal</span><span class="sxs-lookup"><span data-stu-id="ffe3b-124">Fiscal</span></span>

<span data-ttu-id="ffe3b-125">Se você selecionar **Fiscal** no campo **Ano de depreciação**, a depreciação com declínio de 175% será calculada com base no ano fiscal especificado para o registro de depreciação, ou para o calendário fiscal selecionado na página **Razão**.</span><span class="sxs-lookup"><span data-stu-id="ffe3b-125">If you select **Fiscal** in the **Depreciation year** field, 175% reducing balance depreciation is calculated based on the fiscal year for the fiscal calendar that is specified for the book, or for the fiscal calendar that is selected on the **Ledger** page.</span></span> <span data-ttu-id="ffe3b-126">Os calendários fiscais são configurados na página **Calendários fiscais**.</span><span class="sxs-lookup"><span data-stu-id="ffe3b-126">Fiscal calendars are set up on the **Fiscal calendars** page.</span></span> <span data-ttu-id="ffe3b-127">Para obter mais informações, consulte [Calendários fiscais, anos fiscais e períodos](../budgeting/fiscal-calendars-fiscal-years-periods.md).</span><span class="sxs-lookup"><span data-stu-id="ffe3b-127">For more information, see [Fiscal calendars, fiscal years, and periods](../budgeting/fiscal-calendars-fiscal-years-periods.md).</span></span>

<span data-ttu-id="ffe3b-128">Por exemplo, no ano fiscal entre 1 de julho e 30 de junho, o cálculo da depreciação começa em 1 de julho.</span><span class="sxs-lookup"><span data-stu-id="ffe3b-128">For example, for the fiscal year July 1 through June 30, the depreciation calculation starts on July 1.</span></span> <span data-ttu-id="ffe3b-129">O ano fiscal pode ter mais ou menos do que 12 meses.</span><span class="sxs-lookup"><span data-stu-id="ffe3b-129">The fiscal year can be longer or shorter than 12 months.</span></span> <span data-ttu-id="ffe3b-130">A depreciação é ajustada automaticamente para cada período fiscal e a duração do próximo ano fiscal é determinada pela configuração de períodos na página **Calendários fiscais**.</span><span class="sxs-lookup"><span data-stu-id="ffe3b-130">The depreciation is automatically adjusted for each period, and the length of the next fiscal year is determined by the setup of periods on the **Fiscal calendars** page.</span></span> 

<span data-ttu-id="ffe3b-131">Se você selecionar **Fiscal** como o ano de depreciação, as opções a seguir ficarão disponíveis no campo **Frequência do período**:</span><span class="sxs-lookup"><span data-stu-id="ffe3b-131">If you select **Fiscal** as the depreciation year, the following options are available in the **Period frequency** field:</span></span>

-   <span data-ttu-id="ffe3b-132">**Anual** lança o valor total da depreciação calculada para o ano fiscal no último dia do ano fiscal.</span><span class="sxs-lookup"><span data-stu-id="ffe3b-132">**Yearly** posts the total amount of the depreciation that is calculated for the fiscal year on the last day of the fiscal year.</span></span>
-   <span data-ttu-id="ffe3b-133">**Período fiscal** calcula o valor total da depreciação para o ano fiscal.</span><span class="sxs-lookup"><span data-stu-id="ffe3b-133">**Fiscal period** calculates the total amount of the depreciation for the fiscal year.</span></span> <span data-ttu-id="ffe3b-134">Esse valor é acumulado nos períodos fiscais definidos na página **Calendários fiscais**.</span><span class="sxs-lookup"><span data-stu-id="ffe3b-134">This amount is accrued into the fiscal periods that are defined on the **Fiscal calendars** page.</span></span>

## <a name="example-of-175-reducing-balance-depreciation"></a><span data-ttu-id="ffe3b-135">Exemplo de depreciação com declínio de 175%</span><span class="sxs-lookup"><span data-stu-id="ffe3b-135">Example of 175% reducing balance depreciation</span></span>

| <span data-ttu-id="ffe3b-136">Campo</span><span class="sxs-lookup"><span data-stu-id="ffe3b-136">Field</span></span>                          | <span data-ttu-id="ffe3b-137">Alíquota</span><span class="sxs-lookup"><span data-stu-id="ffe3b-137">Value</span></span>  |
|--------------------------------|--------|
| <span data-ttu-id="ffe3b-138">Custo de Aquisição</span><span class="sxs-lookup"><span data-stu-id="ffe3b-138">Acquisition cost</span></span>               | <span data-ttu-id="ffe3b-139">11,000</span><span class="sxs-lookup"><span data-stu-id="ffe3b-139">11,000</span></span> |
| <span data-ttu-id="ffe3b-140">valor residual</span><span class="sxs-lookup"><span data-stu-id="ffe3b-140">Salvage value</span></span>                  | <span data-ttu-id="ffe3b-141">1.000</span><span class="sxs-lookup"><span data-stu-id="ffe3b-141">1,000</span></span>  |
| <span data-ttu-id="ffe3b-142">Base de depreciação</span><span class="sxs-lookup"><span data-stu-id="ffe3b-142">Depreciation base</span></span>              | <span data-ttu-id="ffe3b-143">10.000</span><span class="sxs-lookup"><span data-stu-id="ffe3b-143">10,000</span></span> |
| <span data-ttu-id="ffe3b-144">Anos de vida útil</span><span class="sxs-lookup"><span data-stu-id="ffe3b-144">Service life years</span></span>             | <span data-ttu-id="ffe3b-145">5</span><span class="sxs-lookup"><span data-stu-id="ffe3b-145">5</span></span>      |
| <span data-ttu-id="ffe3b-146">porcentagem de depreciação</span><span class="sxs-lookup"><span data-stu-id="ffe3b-146">Yearly depreciation percentage</span></span> | <span data-ttu-id="ffe3b-147">35%</span><span class="sxs-lookup"><span data-stu-id="ffe3b-147">35%</span></span>    |

<span data-ttu-id="ffe3b-148">O método de depreciação por declínio de 175% divide 175% pelos anos de vida útil.</span><span class="sxs-lookup"><span data-stu-id="ffe3b-148">The 175% reducing balance depreciation method divides 175 percent by the service life years.</span></span> <span data-ttu-id="ffe3b-149">Essa porcentagem será multiplicada pelo valor líquido contábil do ativo para determinar o valor da depreciação anual.</span><span class="sxs-lookup"><span data-stu-id="ffe3b-149">That percentage will be multiplied by the net book value of the asset to determine the depreciation amount for the year.</span></span>

| <span data-ttu-id="ffe3b-150">Período</span><span class="sxs-lookup"><span data-stu-id="ffe3b-150">Period</span></span> | <span data-ttu-id="ffe3b-151">Cálculo do valor de depreciação anual</span><span class="sxs-lookup"><span data-stu-id="ffe3b-151">Calculation of the yearly depreciation amount</span></span> | <span data-ttu-id="ffe3b-152">Valor Contábil</span><span class="sxs-lookup"><span data-stu-id="ffe3b-152">Book value</span></span>                  | <span data-ttu-id="ffe3b-153">Valor líquido contábil no final do ano</span><span class="sxs-lookup"><span data-stu-id="ffe3b-153">Net book value at the end of the year</span></span> |
|--------|-----------------------------------------------|-----------------------------|---------------------------------------|
| <span data-ttu-id="ffe3b-154">Ano 1</span><span class="sxs-lookup"><span data-stu-id="ffe3b-154">Year 1</span></span> | <span data-ttu-id="ffe3b-155">(11.000 – 1.000) × 35% = 3.500</span><span class="sxs-lookup"><span data-stu-id="ffe3b-155">(11,000 – 1,000) × 35% = 3,500</span></span>                | <span data-ttu-id="ffe3b-156">11.000 – 3.500 = 7.500</span><span class="sxs-lookup"><span data-stu-id="ffe3b-156">11,000 – 3,500 = 7,500</span></span>      | <span data-ttu-id="ffe3b-157">11.000 – 1.000 – 3.500 = 6.500</span><span class="sxs-lookup"><span data-stu-id="ffe3b-157">11,000 – 1,000 – 3,500 = 6,500</span></span>        |
| <span data-ttu-id="ffe3b-158">Ano 2</span><span class="sxs-lookup"><span data-stu-id="ffe3b-158">Year 2</span></span> | <span data-ttu-id="ffe3b-159">6.500 × 35% = 2.275</span><span class="sxs-lookup"><span data-stu-id="ffe3b-159">6,500 × 35% = 2,275</span></span>                           | <span data-ttu-id="ffe3b-160">7.500 – 2.275 = 5.225</span><span class="sxs-lookup"><span data-stu-id="ffe3b-160">7,500 – 2,275 = 5,225</span></span>       | <span data-ttu-id="ffe3b-161">6.500 – 2.275 = 4.225</span><span class="sxs-lookup"><span data-stu-id="ffe3b-161">6,500 – 2,275 = 4,225</span></span>                 |
| <span data-ttu-id="ffe3b-162">Ano 3</span><span class="sxs-lookup"><span data-stu-id="ffe3b-162">Year 3</span></span> | <span data-ttu-id="ffe3b-163">4.225 × 35% = 1.478,75</span><span class="sxs-lookup"><span data-stu-id="ffe3b-163">4,225 × 35% = 1,478.75</span></span>                        | <span data-ttu-id="ffe3b-164">5.225 – 1.478,75 = 3.746,25</span><span class="sxs-lookup"><span data-stu-id="ffe3b-164">5,225 – 1,478.75 = 3,746.25</span></span> | <span data-ttu-id="ffe3b-165">4.225 – 1.478,75 = 2.746,25</span><span class="sxs-lookup"><span data-stu-id="ffe3b-165">4,225 – 1,478.75 = 2,746.25</span></span>           |

> [!NOTE] 
> <span data-ttu-id="ffe3b-166">Normalmente, quando o valor que é calculado usando o método de depreciação por declínio de 175% se torna menor do que o valor que será calculado usando o método linear, há uma conversão para o método linear método para a vida restante.</span><span class="sxs-lookup"><span data-stu-id="ffe3b-166">Typically, when the amount that is calculated by using the 175% reducing balance depreciation method becomes less than the amount that would be calculated by using the straight line method, there is a conversion to the straight line method for the remaining life.</span></span>





[!INCLUDE[footer-include](../../includes/footer-banner.md)]