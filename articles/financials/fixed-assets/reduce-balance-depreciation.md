---
title: Reduzir depreciação de saldo
description: Este artigo fornece uma visão geral do método de saldo de reduzir a depreciação.
author: ShylaThompson
manager: AnnBe
ms.date: 04/25/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetDepreciationProfile
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 3281
ms.assetid: 1b86763d-d47c-4a6a-a9a6-d97a736750da
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e36a7e1a5d83a95de53b70b8e3c3b667aae9c6c0
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1553659"
---
# <a name="reduce-balance-depreciation"></a><span data-ttu-id="1dd96-103">Reduzir depreciação de saldo</span><span class="sxs-lookup"><span data-stu-id="1dd96-103">Reduce balance depreciation</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="1dd96-104">Este artigo fornece uma visão geral do método de saldo de reduzir a depreciação.</span><span class="sxs-lookup"><span data-stu-id="1dd96-104">This article gives an overview of the Reducing balance method of depreciation.</span></span>

<span data-ttu-id="1dd96-105">Quando você define um perfil de depreciação de ativo fixo e seleciona Saldo decrescente no campo Método da página Perfis de depreciação, os ativos fixos atribuídos ao perfil de depreciação são depreciados na mesma porcentagem em cada um dos períodos de depreciação.</span><span class="sxs-lookup"><span data-stu-id="1dd96-105">When you set up a fixed asset depreciation profile and select Reducing balance in the Method field in the Depreciation profiles page, the assets that have this depreciation profile assigned to them are depreciated by the same percentage in each depreciation period.</span></span>

<span data-ttu-id="1dd96-106">Para definir a depreciação de saldo decrescente, você também deve fazer seleções nos campos da Guia Rápida Geral da página Perfis de depreciação.</span><span class="sxs-lookup"><span data-stu-id="1dd96-106">To set up reducing balance depreciation, you must also make selections in fields on the General FastTab of the Depreciation profiles page.</span></span> <span data-ttu-id="1dd96-107">Primeiro, selecione um ano no campo Ano de depreciação.</span><span class="sxs-lookup"><span data-stu-id="1dd96-107">First, select a year in the Depreciation year field.</span></span> <span data-ttu-id="1dd96-108">Dependendo da seleção, as opções diferentes aparecerão no campo Frequência do período, como explicado nas sessões a seguir.</span><span class="sxs-lookup"><span data-stu-id="1dd96-108">Depending on the selection, different options appear in the Period frequency field, as explained in the following sections.</span></span> 

<span data-ttu-id="1dd96-109">Você também deve inserir um valor no campo Porcentagem relativo ao perfil de depreciação.</span><span class="sxs-lookup"><span data-stu-id="1dd96-109">You must also enter a value in the Percentage field for the depreciation profile.</span></span> <span data-ttu-id="1dd96-110">Caso selecione a opção Depreciação total, a base de depreciação restante será obtida no último período de depreciação e poderá ser um valor muito grande.</span><span class="sxs-lookup"><span data-stu-id="1dd96-110">If you select the Full depreciation option, the remaining depreciation basis is taken in the last depreciation period and could be a large amount.</span></span> <span data-ttu-id="1dd96-111">Alguns países/regiões não usam uma alternativa ao método linear.</span><span class="sxs-lookup"><span data-stu-id="1dd96-111">Some countries/regions do not use a switchover to a straight line method.</span></span> <span data-ttu-id="1dd96-112">A alternativa ocorre quando o método de depreciação alternativa for superior ou igual ao valor do perfil de depreciação principal, e o valor de depreciação obtido é o valor do método alternativo.</span><span class="sxs-lookup"><span data-stu-id="1dd96-112">Switchover occurs when the alternative depreciation method amount is greater than or equal to the primary depreciation profile amount, and the depreciation amount taken is the alternative method amount.</span></span> 

<span data-ttu-id="1dd96-113">Como um ativo jamais será totalmente depreciado com base no cálculo de uma porcentagem, você deve selecionar a opção Depreciação total para depreciar um ativo por completo.</span><span class="sxs-lookup"><span data-stu-id="1dd96-113">Because an asset will never be fully depreciated based on a percentage calculation, you must select the Full depreciation option to fully depreciate an asset.</span></span>

## <a name="select-a-depreciation-year"></a><span data-ttu-id="1dd96-114">Selecione um ano de depreciação</span><span class="sxs-lookup"><span data-stu-id="1dd96-114">Select a depreciation year</span></span>
<span data-ttu-id="1dd96-115">Você pode selecionar Calendário ou Fiscal no campo Ano de depreciação na página Perfis de depreciação.</span><span class="sxs-lookup"><span data-stu-id="1dd96-115">You can select either Calendar or Fiscal in the Depreciation year field in the Depreciation profiles page.</span></span> <span data-ttu-id="1dd96-116">A seleção define as opções disponíveis no campo Frequência do período.</span><span class="sxs-lookup"><span data-stu-id="1dd96-116">The selection defines the options that are available in the Period frequency field.</span></span> <span data-ttu-id="1dd96-117">A opção padrão é Calendário.</span><span class="sxs-lookup"><span data-stu-id="1dd96-117">The default option is Calendar.</span></span>

### <a name="calendar"></a><span data-ttu-id="1dd96-118">Calendário</span><span class="sxs-lookup"><span data-stu-id="1dd96-118">Calendar</span></span>

<span data-ttu-id="1dd96-119">A opção Calendário atualiza a base da depreciação que, normalmente é o valor líquido contábil menos o valor residual, no dia 1º de janeiro de cada ano.</span><span class="sxs-lookup"><span data-stu-id="1dd96-119">The Calendar option updates the depreciation base, which is typically the net book value minus the scrap value, on January 1 of each year.</span></span> <span data-ttu-id="1dd96-120">No exemplo de depreciação do saldo decrescente que será apresentado neste tópico, a base de depreciação é o numerados da primeira expressão na coluna de cálculos.</span><span class="sxs-lookup"><span data-stu-id="1dd96-120">In the reducing balance depreciation example later in this topic, the depreciation base is the numerator in the first expression in the calculations column.</span></span> 

<span data-ttu-id="1dd96-121">Caso selecione Calendário, você terá estas opções no campo Frequência do período, que define as datas e os valores de lançamento acumulado da depreciação durante todo o ano civil.</span><span class="sxs-lookup"><span data-stu-id="1dd96-121">If you select Calendar, the following options are available in the Period frequency field, which defines the depreciation accrual posting dates and amounts throughout the calendar year:</span></span>

-   <span data-ttu-id="1dd96-122">Anual lança no dia 31 de dezembro.</span><span class="sxs-lookup"><span data-stu-id="1dd96-122">Yearly posts on December 31.</span></span>
-   <span data-ttu-id="1dd96-123">Mensal lança um valor mensal ao final de cada mês do calendário.</span><span class="sxs-lookup"><span data-stu-id="1dd96-123">Monthly posts a monthly amount at the end of each calendar month.</span></span>
-   <span data-ttu-id="1dd96-124">Trimestral lança um valor trimestral ao final de cada trimestre do calendário (31 de março, 30 de junho, 30 de setembro e 31 de dezembro).</span><span class="sxs-lookup"><span data-stu-id="1dd96-124">Quarterly posts a quarterly amount at the end of each calendar quarter (March 31, June 30, September 30, and December 31).</span></span>
-   <span data-ttu-id="1dd96-125">Semestral lança um valor semestral no final de cada semestre do calendário (30 de junho e 31 de dezembro).</span><span class="sxs-lookup"><span data-stu-id="1dd96-125">Half-Yearly posts a half-yearly amount at the end of each calendar half-year (June 30 and December 31).</span></span>
-   <span data-ttu-id="1dd96-126">Diário lança o valor de depreciação do método de depreciação diária usando uma transação para cada dia.</span><span class="sxs-lookup"><span data-stu-id="1dd96-126">Daily posts the depreciation amount for the daily depreciation method using one transaction for each day.</span></span>

<span data-ttu-id="1dd96-127">Por exemplo, se você selecionar Anual, a depreciação anual é lançada apenas uma vez, no dia 31 de dezembro de cada ano.</span><span class="sxs-lookup"><span data-stu-id="1dd96-127">For example, if you select Yearly, the yearly depreciation is posted only one time, on December 31 of each year.</span></span> <span data-ttu-id="1dd96-128">Se você selecionar Mensal, a depreciação mensal é lançada a cada mês como 1/12 do valor de depreciação anual.</span><span class="sxs-lookup"><span data-stu-id="1dd96-128">If you select Monthly, the monthly depreciation is posted each month as 1/12 of the yearly depreciation amount.</span></span>

### <a name="fiscal"></a><span data-ttu-id="1dd96-129">fiscal</span><span class="sxs-lookup"><span data-stu-id="1dd96-129">Fiscal</span></span>

<span data-ttu-id="1dd96-130">Caso você selecione Fiscal no campo Ano de depreciação, será usado o método de depreciação linear.</span><span class="sxs-lookup"><span data-stu-id="1dd96-130">If you select Fiscal in the Depreciation year field, the straight line depreciation method is used.</span></span> <span data-ttu-id="1dd96-131">Ele é calculado com base no ano fiscal, definido na página Calendários fiscais para o calendário fiscal selecionado na página Razão.</span><span class="sxs-lookup"><span data-stu-id="1dd96-131">It is calculated based on the fiscal year, which is set up in the Fiscal calendars page for the fiscal calendar that is selected in the Ledger page.</span></span> <span data-ttu-id="1dd96-132">Por exemplo, no ano fiscal entre 1 de julho e 30 de junho, o cálculo da depreciação começa em 1 de julho.</span><span class="sxs-lookup"><span data-stu-id="1dd96-132">For example, for fiscal year July 1 through June 30, the depreciation calculation starts on July 1.</span></span> <span data-ttu-id="1dd96-133">O ano fiscal pode ter mais ou menos do que 12 meses.</span><span class="sxs-lookup"><span data-stu-id="1dd96-133">The fiscal year can be longer or shorter than 12 months.</span></span> <span data-ttu-id="1dd96-134">A depreciação é ajustada para cada período fiscal.</span><span class="sxs-lookup"><span data-stu-id="1dd96-134">The depreciation is adjusted for each fiscal period.</span></span> <span data-ttu-id="1dd96-135">A duração do próximo ano fiscal baseia-se nos períodos fiscais configurados quando você cria um novo ano fiscal na página Calendários fiscais.</span><span class="sxs-lookup"><span data-stu-id="1dd96-135">The length of the next fiscal year is based on the fiscal periods that you set up when you create a new fiscal year in the Fiscal calendars page.</span></span>


<span data-ttu-id="1dd96-136">Se você selecionar Fiscal, as opções a seguir estarão disponíveis no campo Frequência do período:</span><span class="sxs-lookup"><span data-stu-id="1dd96-136">If you select Fiscal, the following options are available in the Period frequency field:</span></span>

-   <span data-ttu-id="1dd96-137">Anual lança o valor total da depreciação calculada para o ano fiscal como um valor no último dia do ano fiscal.</span><span class="sxs-lookup"><span data-stu-id="1dd96-137">Yearly posts the total amount of the depreciation calculated for the fiscal year as one amount on the last day of the fiscal year.</span></span>
-   <span data-ttu-id="1dd96-138">Período fiscal lança o valor total da depreciação calculado para o ano fiscal, que é acumulado em períodos fiscais definidos para o calendário fiscal selecionado na página Razão, ou para o calendário fiscal selecionado para o livro de depreciação para um ativo fixo.</span><span class="sxs-lookup"><span data-stu-id="1dd96-138">Fiscal period posts the total amount of the depreciation calculated for the fiscal year, which is accrued into the fiscal periods that are defined for the fiscal calendar that is selected in the Ledger page, or for the fiscal calendar that is selected for the book for a fixed asset.</span></span>

## <a name="example-of-reducing-balance-depreciation"></a><span data-ttu-id="1dd96-139">Exemplo de depreciação de saldo decrescente</span><span class="sxs-lookup"><span data-stu-id="1dd96-139">Example of reducing balance depreciation</span></span>

<span data-ttu-id="1dd96-140">Suponhamos que o preço de aquisição do ativo fixo seja 11.000, o valor de sucata seja 1.000 e o fator de porcentagem da depreciação seja 30.</span><span class="sxs-lookup"><span data-stu-id="1dd96-140">Suppose that the fixed asset acquisition price is 11,000, the scrap value is 1,000, and the depreciation percentage factor is 30.</span></span> 

<span data-ttu-id="1dd96-141">Usando o método Reduzindo saldo, 30 por cento da base de depreciação (valor líquido contábil menos o valor de sucata) são calculados ao final do período de depreciação anterior.</span><span class="sxs-lookup"><span data-stu-id="1dd96-141">Using the Reducing balance method, 30 percent of the depreciation base (net book value minus scrap value) is calculated at the end of the previous depreciation period.</span></span> <span data-ttu-id="1dd96-142">A depreciação para os três primeiros anos é mostrada na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="1dd96-142">Depreciation for the first three years is shown in the following table.</span></span>

| <span data-ttu-id="1dd96-143">Período</span><span class="sxs-lookup"><span data-stu-id="1dd96-143">Period</span></span> | <span data-ttu-id="1dd96-144">Cálculo do valor de depreciação anual</span><span class="sxs-lookup"><span data-stu-id="1dd96-144">Calculation of yearly depreciation amount</span></span> | <span data-ttu-id="1dd96-145">Valor líquido contábil no final do ano</span><span class="sxs-lookup"><span data-stu-id="1dd96-145">Net book value at the end of the year</span></span> |
|--------|-------------------------------------------|---------------------------------------|
| <span data-ttu-id="1dd96-146">Ano 1</span><span class="sxs-lookup"><span data-stu-id="1dd96-146">Year 1</span></span> | <span data-ttu-id="1dd96-147">(11.000 - 1.000) \* 30% = 3.000</span><span class="sxs-lookup"><span data-stu-id="1dd96-147">(11,000 - 1,000) \* 30% = 3,000</span></span>           | <span data-ttu-id="1dd96-148">(11.000 - 1.000) - 3.000 = 7.000</span><span class="sxs-lookup"><span data-stu-id="1dd96-148">(11,000 - 1,000) - 3,000 = 7,000</span></span>      |
| <span data-ttu-id="1dd96-149">Ano 2</span><span class="sxs-lookup"><span data-stu-id="1dd96-149">Year 2</span></span> | <span data-ttu-id="1dd96-150">(7.000 - 1.000) \* 30% = 1.800</span><span class="sxs-lookup"><span data-stu-id="1dd96-150">(7,000 - 1,000) \* 30% = 1,800</span></span>            | <span data-ttu-id="1dd96-151">(7.000 -1.800) = 5.200</span><span class="sxs-lookup"><span data-stu-id="1dd96-151">(7,000 -1,800) = 5,200</span></span>                |
| <span data-ttu-id="1dd96-152">Ano 3</span><span class="sxs-lookup"><span data-stu-id="1dd96-152">Year 3</span></span> | <span data-ttu-id="1dd96-153">(5.200 - 1.000) \* 30% = 1.260</span><span class="sxs-lookup"><span data-stu-id="1dd96-153">(5,200 - 1,000) \* 30% = 1,260</span></span>            | <span data-ttu-id="1dd96-154">(5.200 - 1.260) = 3.940</span><span class="sxs-lookup"><span data-stu-id="1dd96-154">(5,200 - 1,260) = 3,940</span></span>               |


-





