---
title: Depreciação manual
description: Este artigo fornece uma visão geral do método de depreciação manual.
author: ShylaThompson
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetDepreciationProfile
audience: Application User
ms.reviewer: roschlom
ms.custom: 13811
ms.assetid: b0e837c9-515a-4aed-9060-5ec94f37edeb
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0bb8d739f3c6c8315ba8f135e7a71075f34f32f1
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5815635"
---
# <a name="manual-depreciation"></a><span data-ttu-id="3f683-103">Depreciação manual</span><span class="sxs-lookup"><span data-stu-id="3f683-103">Manual depreciation</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="3f683-104">Este artigo fornece uma visão geral do método de depreciação manual.</span><span class="sxs-lookup"><span data-stu-id="3f683-104">This article gives an overview of the manual depreciation method.</span></span>

<span data-ttu-id="3f683-105">Quando um perfil de depreciação do ativo fixo é configurado e você seleciona **Manual** no campo **Método** da página **Perfis de depreciação**, a depreciação de ativos fixos atribuídos a esse perfil de depreciação é determinada pela porcentagem informada para cada intervalo do ano de calendário.</span><span class="sxs-lookup"><span data-stu-id="3f683-105">When you set up a fixed asset depreciation profile and select **Manual** in the **Method** field on the **Depreciation profiles** page, the depreciation of fixed assets that are assigned to the depreciation profile is determined by the percentage that you enter for each interval in the calendar year.</span></span> <span data-ttu-id="3f683-106">Os intervalos para os quais você configura porcentagens são lançados de acordo com o valor selecionado no campo **Frequência de período** da Guia Rápida **Geral** na página **Perfis de depreciação**.</span><span class="sxs-lookup"><span data-stu-id="3f683-106">The intervals that you set up percentages for are posted according to the value that you select in the **Period frequency** field on the **General** FastTab of the **Depreciation profiles** page.</span></span> <span data-ttu-id="3f683-107">Estes são os valores que você pode selecionar:</span><span class="sxs-lookup"><span data-stu-id="3f683-107">Here are the values that you can select:</span></span>

-   <span data-ttu-id="3f683-108">Anualmente</span><span class="sxs-lookup"><span data-stu-id="3f683-108">Yearly</span></span>
-   <span data-ttu-id="3f683-109">Mensalmente</span><span class="sxs-lookup"><span data-stu-id="3f683-109">Monthly</span></span>
-   <span data-ttu-id="3f683-110">Trimestral</span><span class="sxs-lookup"><span data-stu-id="3f683-110">Quarterly</span></span>
-   <span data-ttu-id="3f683-111">Semestral</span><span class="sxs-lookup"><span data-stu-id="3f683-111">Half-Yearly</span></span>
-   <span data-ttu-id="3f683-112">Diariamente</span><span class="sxs-lookup"><span data-stu-id="3f683-112">Daily</span></span>

<span data-ttu-id="3f683-113">Depois de selecionar a frequência de período, clique em **Planos manuais** e configure as porcentagens de cada intervalo de lançamento.</span><span class="sxs-lookup"><span data-stu-id="3f683-113">After you select the period frequency, click **Manual schedules**, and set up percentages for each posting interval.</span></span> <span data-ttu-id="3f683-114">Juntos, os planos manuais e os intervalos de lançamento definem, juntos, o valor da depreciação, como mostram os exemplos posteriormente neste artigo.</span><span class="sxs-lookup"><span data-stu-id="3f683-114">Together, the manual schedules and the posting intervals define the depreciation amount, as shown in the examples later in this article.</span></span> <span data-ttu-id="3f683-115">A depreciação manual sempre é calculada como uma porcentagem do preço de aquisição.</span><span class="sxs-lookup"><span data-stu-id="3f683-115">Manual depreciation is always calculated as a percentage of the acquisition price.</span></span> <span data-ttu-id="3f683-116">Para a depreciação manual, as porcentagens informadas nos intervalos de depreciação não precisam somar 100%.</span><span class="sxs-lookup"><span data-stu-id="3f683-116">For manual depreciation, the percentages that you enter in the intervals of the depreciation don't have to add up to 100 percent.</span></span> <span data-ttu-id="3f683-117">A depreciação manual é um método de depreciação flexível que define um perfil de depreciação extraordinário na página **Registros**, como uma depreciação não periódica para fins especiais (por exemplo, impostos).</span><span class="sxs-lookup"><span data-stu-id="3f683-117">Manual depreciation is a flexible depreciation method that is often used to define an extraordinary depreciation profile on the **Books** page, such as a non-periodic depreciation for special purposes (for example, tax).</span></span>

## <a name="examples"></a><span data-ttu-id="3f683-118">Exemplos</span><span class="sxs-lookup"><span data-stu-id="3f683-118">Examples</span></span>
<span data-ttu-id="3f683-119">Preço de aquisição: 11.000,00 Valor de sucata esperado: 1.000,00 A tabela a seguir mostra os intervalos e as porcentagens que você configura na página **Planos de perfil de depreciação de ativo fixo**.</span><span class="sxs-lookup"><span data-stu-id="3f683-119">Acquisition price: 11,000.00 Expected scrap value: 1,000.00 The following table shows the intervals and percentages that you set up on the **Fixed asset depreciation profile schedules** page.</span></span>

| <span data-ttu-id="3f683-120">Número de intervalo</span><span class="sxs-lookup"><span data-stu-id="3f683-120">Interval number</span></span> | <span data-ttu-id="3f683-121">Porcentagem</span><span class="sxs-lookup"><span data-stu-id="3f683-121">Percentage</span></span> |
|-----------------|------------|
| <span data-ttu-id="3f683-122">1</span><span class="sxs-lookup"><span data-stu-id="3f683-122">1</span></span>               | <span data-ttu-id="3f683-123">10.00</span><span class="sxs-lookup"><span data-stu-id="3f683-123">10.00</span></span>      |
| <span data-ttu-id="3f683-124">2</span><span class="sxs-lookup"><span data-stu-id="3f683-124">2</span></span>               | <span data-ttu-id="3f683-125">50,00</span><span class="sxs-lookup"><span data-stu-id="3f683-125">50.00</span></span>      |
| <span data-ttu-id="3f683-126">3</span><span class="sxs-lookup"><span data-stu-id="3f683-126">3</span></span>               | <span data-ttu-id="3f683-127">8,00</span><span class="sxs-lookup"><span data-stu-id="3f683-127">8.00</span></span>       |

<span data-ttu-id="3f683-128">A tabela a seguir mostra como a depreciação é calculada para cada intervalo.</span><span class="sxs-lookup"><span data-stu-id="3f683-128">The following table shows how the depreciation for each interval is calculated.</span></span>

|  <span data-ttu-id="3f683-129">Número de intervalo</span><span class="sxs-lookup"><span data-stu-id="3f683-129">Interval number</span></span> | <span data-ttu-id="3f683-130">Cálculo do valor de depreciação anual</span><span class="sxs-lookup"><span data-stu-id="3f683-130">Calculation of the yearly depreciation amount</span></span> | <span data-ttu-id="3f683-131">Valor contábil líquido no final do intervalo</span><span class="sxs-lookup"><span data-stu-id="3f683-131">Net book value at the end of the interval</span></span> |
|------------------|-----------------------------------------------|-------------------------------------------|
| <span data-ttu-id="3f683-132">1</span><span class="sxs-lookup"><span data-stu-id="3f683-132">1</span></span>                | <span data-ttu-id="3f683-133">(11.000 – 1.000) × 10% = 1.000</span><span class="sxs-lookup"><span data-stu-id="3f683-133">(11,000 – 1,000) × 10% = 1,000</span></span>                | <span data-ttu-id="3f683-134">10.000 (11.000 – 1.000)</span><span class="sxs-lookup"><span data-stu-id="3f683-134">10,000 (11,000 – 1,000)</span></span>                   |
| <span data-ttu-id="3f683-135">2</span><span class="sxs-lookup"><span data-stu-id="3f683-135">2</span></span>                | <span data-ttu-id="3f683-136">(11.000 – 1.000) × 50% = 5.000</span><span class="sxs-lookup"><span data-stu-id="3f683-136">(11,000 – 1,000) × 50% = 5,000</span></span>                | <span data-ttu-id="3f683-137">5.000 (10.000 – 5.000)</span><span class="sxs-lookup"><span data-stu-id="3f683-137">5,000 (10,000 – 5,000)</span></span>                    |
| <span data-ttu-id="3f683-138">3</span><span class="sxs-lookup"><span data-stu-id="3f683-138">3</span></span>                | <span data-ttu-id="3f683-139">(11.000 – 1.000) × 8% = 800</span><span class="sxs-lookup"><span data-stu-id="3f683-139">(11,000 – 1,000) × 8% = 800</span></span>                   | <span data-ttu-id="3f683-140">4.200 (5.000 – 800)</span><span class="sxs-lookup"><span data-stu-id="3f683-140">4,200 (5,000 – 800)</span></span>                       |

<span data-ttu-id="3f683-141">Se você selecionar **Mensal** no campo **Frequência do período**, configurará 12 intervalos manuais de planejamento.</span><span class="sxs-lookup"><span data-stu-id="3f683-141">If you select **Monthly** in the **Period frequency** field, you set up 12 manual schedule intervals.</span></span> <span data-ttu-id="3f683-142">A tabela a seguir mostra os valores de depreciação para os dois primeiros intervalos.</span><span class="sxs-lookup"><span data-stu-id="3f683-142">The following table shows the depreciation amounts for the first two intervals.</span></span>

| <span data-ttu-id="3f683-143">Intervalo</span><span class="sxs-lookup"><span data-stu-id="3f683-143">Interval</span></span> | <span data-ttu-id="3f683-144">Valor de depreciação</span><span class="sxs-lookup"><span data-stu-id="3f683-144">Depreciation amount</span></span>            |
|----------|--------------------------------|
| <span data-ttu-id="3f683-145">Janeiro</span><span class="sxs-lookup"><span data-stu-id="3f683-145">January</span></span>  | <span data-ttu-id="3f683-146">(11.000 – 1.000) × 10% = 1.000</span><span class="sxs-lookup"><span data-stu-id="3f683-146">(11,000 – 1,000) × 10% = 1,000</span></span> |
| <span data-ttu-id="3f683-147">Fevereiro</span><span class="sxs-lookup"><span data-stu-id="3f683-147">February</span></span> | <span data-ttu-id="3f683-148">(11.000 – 1.000) × 50% = 5.000</span><span class="sxs-lookup"><span data-stu-id="3f683-148">(11,000 – 1,000) × 50% = 5,000</span></span> |

<span data-ttu-id="3f683-149">Se você selecionar <strong>Semestral</strong> no campo *<strong><em>Frequência do período</em>*</strong>, você configurará dois intervalos manuais de agendamento.</span><span class="sxs-lookup"><span data-stu-id="3f683-149">If you select <strong>Half-Yearly</strong> in the *<strong><em>Period frequency</em>* field</strong>, you set up two manual schedule intervals.</span></span> <span data-ttu-id="3f683-150">A tabela a seguir mostra os valores de depreciação para esses dois intervalos.</span><span class="sxs-lookup"><span data-stu-id="3f683-150">The following table shows the depreciation amounts for those two intervals.</span></span>

| <span data-ttu-id="3f683-151">Intervalo</span><span class="sxs-lookup"><span data-stu-id="3f683-151">Interval</span></span>    | <span data-ttu-id="3f683-152">Valor de depreciação</span><span class="sxs-lookup"><span data-stu-id="3f683-152">Depreciation amount</span></span>            |
|-------------|--------------------------------|
| <span data-ttu-id="3f683-153">30 de junho</span><span class="sxs-lookup"><span data-stu-id="3f683-153">June 30</span></span>     | <span data-ttu-id="3f683-154">(11.000 – 1.000) × 10% = 1.000</span><span class="sxs-lookup"><span data-stu-id="3f683-154">(11,000 – 1,000) × 10% = 1,000</span></span> |
| <span data-ttu-id="3f683-155">31 de dezembro</span><span class="sxs-lookup"><span data-stu-id="3f683-155">December 31</span></span> | <span data-ttu-id="3f683-156">(11.000 – 1.000) × 50% = 5.000</span><span class="sxs-lookup"><span data-stu-id="3f683-156">(11,000 – 1,000) × 50% = 5,000</span></span> |

<span data-ttu-id="3f683-157">O total de porcentagens para todos os intervalos não precisa ser 100.</span><span class="sxs-lookup"><span data-stu-id="3f683-157">The total of percentages for all intervals doesn't have to be 100.</span></span> <span data-ttu-id="3f683-158">Entretanto, você receberá uma mensagem se o valor no campo **Porcentagem cumulativa** na página **Planos de perfil de depreciação de ativo fixo** não for **100**.</span><span class="sxs-lookup"><span data-stu-id="3f683-158">However, you receive a message if the value in the **Cumulative percentage** field on the **Fixed asset depreciation profile schedules** page isn't **100**.</span></span>





[!INCLUDE[footer-include](../../includes/footer-banner.md)]