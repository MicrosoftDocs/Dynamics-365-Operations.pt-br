---
title: depreciação com declínio de 150%
description: Este artigo fornece uma visão geral do método de saldo de reduzem de 150 de porcentagem de depreciação.
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
ms.custom: 13891
ms.assetid: 36d1112d-921c-4fff-abe0-0ff2429848d3
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a132a8d6e5eaf0dad54133fc9d0c12dcf5866c7c
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2176405"
---
# <a name="150-percent-reducing-balance-depreciation"></a><span data-ttu-id="1229b-103">depreciação com declínio de 150%</span><span class="sxs-lookup"><span data-stu-id="1229b-103">150 percent reducing balance depreciation</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="1229b-104">Este artigo fornece uma visão geral do método de saldo de reduzem de 150 de porcentagem de depreciação.</span><span class="sxs-lookup"><span data-stu-id="1229b-104">This article gives an overview of the 150 percent reducing balance method of depreciation.</span></span>

<span data-ttu-id="1229b-105">Ao configurar um perfil de depreciação de ativos fixos e selecionar **declínio de 150%** no campo **Método** na página **Perfis de depreciação**, os ativos fixos que são atribuídos ao perfil de depreciação são depreciados pela mesma porcentagem em cada período de depreciação.</span><span class="sxs-lookup"><span data-stu-id="1229b-105">When you set up a fixed asset depreciation profile and select **150% reducing balance** in the **Method** field on the **Depreciation profiles** page, fixed assets that are assigned the depreciation profile are depreciated by the same percentage in each depreciation period.</span></span> <span data-ttu-id="1229b-106">Essa porcentagem é calculada com base na vida útil do ativo.</span><span class="sxs-lookup"><span data-stu-id="1229b-106">This percentage is calculated based on the service life of the asset.</span></span> <span data-ttu-id="1229b-107">Por exemplo, se um ativo tiver uma vida útil de cinco anos, será calculada uma porcentagem de 30% (150% ÷ 5).</span><span class="sxs-lookup"><span data-stu-id="1229b-107">For example, if an asset has a service life of five years, the percentage is calculated as 30 percent (150% ÷ 5).</span></span> 

<span data-ttu-id="1229b-108">Para configurar uma depreciação por declínio de 150%, você também deve selecionar opções no campo **Ano de depreciação** e no campo **Frequência do período** na página **Perfis de depreciação**.</span><span class="sxs-lookup"><span data-stu-id="1229b-108">To set up 150% reducing balance depreciation, you must also select options in the **Depreciation year** field and the **Period frequency** field on the **Depreciation profiles** page.</span></span> <span data-ttu-id="1229b-109">As opções disponíveis no campo **Frequência do período** variam, dependendo do valor selecionado no campo **Ano de depreciação**.</span><span class="sxs-lookup"><span data-stu-id="1229b-109">The options that are available in the **Period frequency** field vary, depending on the value that is selected in the **Depreciation year** field.</span></span>

## <a name="selection-of-depreciation-year"></a><span data-ttu-id="1229b-110">Seleção do ano da depreciação</span><span class="sxs-lookup"><span data-stu-id="1229b-110">Selection of depreciation year</span></span>
<span data-ttu-id="1229b-111">Você pode selecionar **Calendário** ou **Fiscal** no campo **Ano de depreciação** na página **Perfis de depreciação**.</span><span class="sxs-lookup"><span data-stu-id="1229b-111">You can select either **Calendar** or **Fiscal** in the **Depreciation year** field on the **Depreciation profiles** page.</span></span> 

<span data-ttu-id="1229b-112">O valor padrão é **Calendário**.</span><span class="sxs-lookup"><span data-stu-id="1229b-112">The default value is **Calendar**.</span></span> <span data-ttu-id="1229b-113">Sua seleção determinará as opções disponíveis no campo **Frequência do período**.</span><span class="sxs-lookup"><span data-stu-id="1229b-113">Your selection determines the options that are available in the **Period frequency** field.</span></span> <span data-ttu-id="1229b-114">Esse campo define os valores e as datas de lançamento de acúmulo da depreciação ao longo do ano de calendário.</span><span class="sxs-lookup"><span data-stu-id="1229b-114">This field defines the depreciation accrual posting dates and amounts throughout the calendar year.</span></span>

### <a name="calendar"></a><span data-ttu-id="1229b-115">Calendário</span><span class="sxs-lookup"><span data-stu-id="1229b-115">Calendar</span></span>

<span data-ttu-id="1229b-116">Você pode optar por manter o valor padrão no campo **Ano de depreciação**, **Calendário**.</span><span class="sxs-lookup"><span data-stu-id="1229b-116">You can keep the default value in the **Depreciation year** field, **Calendar**.</span></span> 

<span data-ttu-id="1229b-117">A opção **Calendário** atualiza a base de depreciação em 1º de janeiro de cada ano.</span><span class="sxs-lookup"><span data-stu-id="1229b-117">The **Calendar** option updates the depreciation base on January 1 of each year.</span></span> <span data-ttu-id="1229b-118">Normalmente, a base de depreciação é o valor líquido contábil menos o valor de sucata.</span><span class="sxs-lookup"><span data-stu-id="1229b-118">Typically, the depreciation base is the net book value minus the scrap value.</span></span> <span data-ttu-id="1229b-119">Nos exemplos a seguir deste tópico, a base de depreciação é o numerador na primeira expressão da coluna de cálculos.</span><span class="sxs-lookup"><span data-stu-id="1229b-119">In the examples later in this topic, the depreciation base is the numerator in the first expression in the calculations column.</span></span> 

<span data-ttu-id="1229b-120">Se você selecionar **Calendário** como o ano de depreciação, as seguintes opções ficarão disponíveis no campo **Frequência do período**:</span><span class="sxs-lookup"><span data-stu-id="1229b-120">If you select **Calendar** as the depreciation year, the following options are available in the **Period frequency** field:</span></span>

-   <span data-ttu-id="1229b-121">**Anual** lança um valor em 31 de dezembro.</span><span class="sxs-lookup"><span data-stu-id="1229b-121">**Yearly** posts an amount on December 31.</span></span>
-   <span data-ttu-id="1229b-122">**Mensal** lança um valor mensal ao final de cada mês do calendário.</span><span class="sxs-lookup"><span data-stu-id="1229b-122">**Monthly** posts a monthly amount at the end of each calendar month.</span></span>
-   <span data-ttu-id="1229b-123">**Trimestral** lança um valor trimestral ao final de cada trimestre do calendário (31 de março, 30 de junho, 30 de setembro e 31 de dezembro).</span><span class="sxs-lookup"><span data-stu-id="1229b-123">**Quarterly** posts a quarterly amount at the end of each calendar quarter (March 31, June 30, September 30, and December 31).</span></span>
-   <span data-ttu-id="1229b-124">**Semestral** lança um valor semestral no final de cada semestre do calendário (30 de junho e 31 de dezembro).</span><span class="sxs-lookup"><span data-stu-id="1229b-124">**Half-Yearly** posts a half-yearly amount at the calendar half year (June 30 and December 31).</span></span>
-   <span data-ttu-id="1229b-125">**Diário** lança o valor de depreciação do método de depreciação diária usando uma transação para cada dia.</span><span class="sxs-lookup"><span data-stu-id="1229b-125">**Daily** posts the depreciation amount for the daily depreciation method by using one transaction for each day.</span></span>

### <a name="fiscal"></a><span data-ttu-id="1229b-126">fiscal</span><span class="sxs-lookup"><span data-stu-id="1229b-126">Fiscal</span></span>

<span data-ttu-id="1229b-127">Se você selecionar **Fiscal** no campo **Ano de depreciação**, a depreciação com declínio de 150% será calculada com base no ano fiscal especificado para o registro de depreciação, ou para o calendário fiscal selecionado na página **Razão**.</span><span class="sxs-lookup"><span data-stu-id="1229b-127">If you select **Fiscal** in the **Depreciation year** field, 150% reducing balance depreciation is calculated based on the fiscal year for the fiscal calendar that is specified for the book, or for the fiscal calendar that is selected on the **Ledger** page.</span></span> <span data-ttu-id="1229b-128">Os calendários fiscais são configurados na página **Calendários fiscais**.</span><span class="sxs-lookup"><span data-stu-id="1229b-128">Fiscal calendars are set up on the **Fiscal calendars** page.</span></span> 

<span data-ttu-id="1229b-129">Por exemplo, no ano fiscal entre 1 de julho e 30 de junho, o cálculo da depreciação começa em 1 de julho.</span><span class="sxs-lookup"><span data-stu-id="1229b-129">For example, for the fiscal year July 1 through June 30, the depreciation calculation starts on July 1.</span></span> <span data-ttu-id="1229b-130">O ano fiscal pode ter mais ou menos do que 12 meses.</span><span class="sxs-lookup"><span data-stu-id="1229b-130">The fiscal year can be longer or shorter than 12 months.</span></span> <span data-ttu-id="1229b-131">A depreciação é ajustada para cada período fiscal.</span><span class="sxs-lookup"><span data-stu-id="1229b-131">The depreciation is adjusted for each period.</span></span> <span data-ttu-id="1229b-132">A duração do próximo ano fiscal será determinada pela configuração de períodos na página **Calendários fiscais**.</span><span class="sxs-lookup"><span data-stu-id="1229b-132">The length of the next fiscal year is determined by the setup of periods on the **Fiscal calendars** page.</span></span> 

<span data-ttu-id="1229b-133">Se você selecionar **Fiscal** como o ano de depreciação, as opções a seguir ficarão disponíveis no campo **Frequência do período**:</span><span class="sxs-lookup"><span data-stu-id="1229b-133">If you select **Fiscal** as the depreciation year, the following options are available in the **Period frequency** field:</span></span>

-   <span data-ttu-id="1229b-134">**Anual** lança o valor total da depreciação calculada para o ano fiscal no último dia do ano fiscal.</span><span class="sxs-lookup"><span data-stu-id="1229b-134">**Yearly** posts the total amount of the depreciation that is calculated for the fiscal year on the last day of the fiscal year.</span></span>
-   <span data-ttu-id="1229b-135">**Período fiscal** lança o valor total da depreciação calculada para o ano fiscal.</span><span class="sxs-lookup"><span data-stu-id="1229b-135">**Fiscal period** posts the total amount of the depreciation that is calculated for the fiscal year.</span></span> <span data-ttu-id="1229b-136">Esse valor é acumulado nos períodos fiscais definidos na página **Calendários fiscais**.</span><span class="sxs-lookup"><span data-stu-id="1229b-136">This amount is accrued into the fiscal periods that are defined on the **Fiscal calendars** page.</span></span>

## <a name="example-of-150-reducing-balance-depreciation"></a><span data-ttu-id="1229b-137">Exemplo de depreciação com declínio de 150%</span><span class="sxs-lookup"><span data-stu-id="1229b-137">Example of 150% reducing balance depreciation</span></span>

|                                |        |
|--------------------------------|--------|
| <span data-ttu-id="1229b-138">Custo de Aquisição</span><span class="sxs-lookup"><span data-stu-id="1229b-138">Acquisition cost</span></span>               | <span data-ttu-id="1229b-139">11.000</span><span class="sxs-lookup"><span data-stu-id="1229b-139">11,000</span></span> |
| <span data-ttu-id="1229b-140">valor residual</span><span class="sxs-lookup"><span data-stu-id="1229b-140">Salvage value</span></span>                  | <span data-ttu-id="1229b-141">1.000</span><span class="sxs-lookup"><span data-stu-id="1229b-141">1,000</span></span>  |
| <span data-ttu-id="1229b-142">Base de depreciação</span><span class="sxs-lookup"><span data-stu-id="1229b-142">Depreciation base</span></span>              | <span data-ttu-id="1229b-143">10.000</span><span class="sxs-lookup"><span data-stu-id="1229b-143">10,000</span></span> |
| <span data-ttu-id="1229b-144">Anos de vida útil</span><span class="sxs-lookup"><span data-stu-id="1229b-144">Service life years</span></span>             | <span data-ttu-id="1229b-145">5</span><span class="sxs-lookup"><span data-stu-id="1229b-145">5</span></span>      |
| <span data-ttu-id="1229b-146">porcentagem de depreciação</span><span class="sxs-lookup"><span data-stu-id="1229b-146">Yearly depreciation percentage</span></span> | <span data-ttu-id="1229b-147">30%</span><span class="sxs-lookup"><span data-stu-id="1229b-147">30%</span></span>    |

<span data-ttu-id="1229b-148">O método por declínio de 150% divide 150% pelos anos de vida útil.</span><span class="sxs-lookup"><span data-stu-id="1229b-148">The 150% reducing balance method divides 150 percent by the service life years.</span></span> <span data-ttu-id="1229b-149">Essa porcentagem será multiplicada pelo valor líquido contábil do ativo para determinar o valor da depreciação anual.</span><span class="sxs-lookup"><span data-stu-id="1229b-149">That percentage will be multiplied by the net book value of the asset to determine the depreciation amount for the year.</span></span>

| <span data-ttu-id="1229b-150">Período</span><span class="sxs-lookup"><span data-stu-id="1229b-150">Period</span></span> | <span data-ttu-id="1229b-151">Cálculo do valor de depreciação anual</span><span class="sxs-lookup"><span data-stu-id="1229b-151">Calculation of the yearly depreciation amount</span></span> | <span data-ttu-id="1229b-152">Valor Contábil</span><span class="sxs-lookup"><span data-stu-id="1229b-152">Book value</span></span>             | <span data-ttu-id="1229b-153">Valor líquido contábil no final do ano</span><span class="sxs-lookup"><span data-stu-id="1229b-153">Net book value at the end of the year</span></span> |
|--------|-----------------------------------------------|------------------------|---------------------------------------|
| <span data-ttu-id="1229b-154">Ano 1</span><span class="sxs-lookup"><span data-stu-id="1229b-154">Year 1</span></span> | <span data-ttu-id="1229b-155">(11.000 – 1.000) × 30% = 3.000</span><span class="sxs-lookup"><span data-stu-id="1229b-155">(11,000 – 1,000) × 30% = 3,000</span></span>                | <span data-ttu-id="1229b-156">11.000 – 3.000 = 8.000</span><span class="sxs-lookup"><span data-stu-id="1229b-156">11,000 – 3,000 = 8,000</span></span> | <span data-ttu-id="1229b-157">11.000 – 1.000 – 3.000 = 7.000</span><span class="sxs-lookup"><span data-stu-id="1229b-157">11,000 – 1,000 – 3,000 = 7,000</span></span>        |
| <span data-ttu-id="1229b-158">Ano 2</span><span class="sxs-lookup"><span data-stu-id="1229b-158">Year 2</span></span> | <span data-ttu-id="1229b-159">7.000 × 30% = 2.100</span><span class="sxs-lookup"><span data-stu-id="1229b-159">7,000 × 30% = 2,100</span></span>                           | <span data-ttu-id="1229b-160">8.000 (2.100 -5.900)</span><span class="sxs-lookup"><span data-stu-id="1229b-160">8,000 – 2,100 = 5,900</span></span>  | <span data-ttu-id="1229b-161">7.000 (2.100 -4.900)</span><span class="sxs-lookup"><span data-stu-id="1229b-161">7,000 – 2,100 = 4,900</span></span>                 |
| <span data-ttu-id="1229b-162">Ano 3</span><span class="sxs-lookup"><span data-stu-id="1229b-162">Year 3</span></span> | <span data-ttu-id="1229b-163">4.900 × 30% = 1.470</span><span class="sxs-lookup"><span data-stu-id="1229b-163">4,900 × 30% = 1,470</span></span>                           | <span data-ttu-id="1229b-164">5.900 – 1.470 = 4.430</span><span class="sxs-lookup"><span data-stu-id="1229b-164">5,900 – 1,470 = 4,430</span></span>  | <span data-ttu-id="1229b-165">4.900 – 1.470 = 3.430</span><span class="sxs-lookup"><span data-stu-id="1229b-165">4,900 – 1,470 = 3,430</span></span>                 |

> [!NOTE]
> <span data-ttu-id="1229b-166">Normalmente, quando o valor que é calculado usando o método de depreciação por declínio de 150%, ele se torna menor do que o valor que será calculado usando o método linear. Há uma conversão para o método linear método para a vida restante.</span><span class="sxs-lookup"><span data-stu-id="1229b-166">Typically, when the amount that is calculated by using the 150% reducing balance depreciation method becomes less than the amount that would be calculated by using the straight line method, there is a conversion to the straight line method for the remaining life.</span></span>



