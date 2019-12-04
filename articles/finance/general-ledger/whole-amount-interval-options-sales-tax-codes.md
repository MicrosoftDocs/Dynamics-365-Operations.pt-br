---
title: Opções de cálculo de intervalo e valor total para códigos de imposto
description: Este artigo explica as opções para o campo Método de cálculo em códigos de imposto e como o imposto é calculado para intervalos e valores inteiros.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TaxData, TaxTable
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations, Retail
ms.custom: 5624
ms.assetid: 96166db4-b7ca-470b-aeb7-0a66fe0554c4
ms.search.region: Global
ms.author: vstehman
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d452ccc94324a695f0d203486fc5fa8fe9db79f6
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/06/2019
ms.locfileid: "2770542"
---
# <a name="whole-amount-and-interval-calculation-options-for-sales-tax-codes"></a><span data-ttu-id="e44b2-103">Opções de cálculo de intervalo e valor total para códigos de imposto</span><span class="sxs-lookup"><span data-stu-id="e44b2-103">Whole amount and Interval calculation options for sales tax codes</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="e44b2-104">Este artigo explica as opções para o campo Método de cálculo em códigos de imposto e como o imposto é calculado para intervalos e valores inteiros.</span><span class="sxs-lookup"><span data-stu-id="e44b2-104">This article explains the options for the Calculation method field on sales tax codes and how sales tax is calculated for intervals and whole amounts.</span></span>

<span data-ttu-id="e44b2-105">Você pode configurar um código de imposto a ser calculado com base em um valor inteiro ou em um intervalo de valores.</span><span class="sxs-lookup"><span data-stu-id="e44b2-105">You can set up a sales tax code to be calculated based on a whole amount or an interval amount.</span></span> <span data-ttu-id="e44b2-106">Na página Códigos de imposto, use o campo Método de cálculo na Guia Rápida Cálculo para selecionar como calcular um código de imposto.</span><span class="sxs-lookup"><span data-stu-id="e44b2-106">In the Sales tax codes page, use the Calculation method field on the Calculation FastTab to select how to calculate a sales tax code.</span></span>
- <span data-ttu-id="e44b2-107">Valor total - a taxa de imposto é aplicada ao valor tributável total.</span><span class="sxs-lookup"><span data-stu-id="e44b2-107">Whole amount – The tax rate is applied to the whole taxable amount.</span></span>
- <span data-ttu-id="e44b2-108">Intervalo - o valor tributável é dividido em partes, cada uma dentro de um intervalo que tem uma taxa de imposto sobre vendas específica.</span><span class="sxs-lookup"><span data-stu-id="e44b2-108">Interval – The taxable amount is divided into parts, each of which falls in a range that has a specific sales tax rate.</span></span> <span data-ttu-id="e44b2-109">A parte do valor inserida em um determinado intervalo é taxada de acordo com a taxa de imposto do intervalo.</span><span class="sxs-lookup"><span data-stu-id="e44b2-109">The part of the amount that falls in a given interval is taxed according to the tax rate for that interval.</span></span> <span data-ttu-id="e44b2-110">O imposto sobre vendas é a soma dos valores de imposto calculados para cada intervalo de valor.</span><span class="sxs-lookup"><span data-stu-id="e44b2-110">The sales tax is the sum of the tax amounts that are calculated for each amount interval.</span></span>
  > [!NOTE]                                                                                                                              
  > <span data-ttu-id="e44b2-111">A opção Intervalo está disponível somente quando você seleciona Linha no campo Método de cálculo na área Impostos da página Parâmetros da contabilidade.</span><span class="sxs-lookup"><span data-stu-id="e44b2-111">The Interval option is available only when you select Line in the Calculation method field in the Sales tax area of the General ledger parameters page.</span></span> 

<span data-ttu-id="e44b2-112">Os intervalos são configurados na página Valores de código de imposto inserindo valores de limite Mínimo e Máximo por taxa de impostos.</span><span class="sxs-lookup"><span data-stu-id="e44b2-112">Intervals are set up in the Sales tax code values page by entering Minimum and Maximum limit amounts per tax rate.</span></span> <span data-ttu-id="e44b2-113">Para que os impostos possam ser calculados em todos os valores tributáveis, independente do método de cálculo selecionado, os intervalos devem seguir as seguintes regras:</span><span class="sxs-lookup"><span data-stu-id="e44b2-113">For taxes to be calculated on all taxable amounts, regardless of which calculation method is selected, intervals must follow these rules:</span></span>
-   <span data-ttu-id="e44b2-114">O primeiro intervalo deve ter um limite Mínimo de zero.</span><span class="sxs-lookup"><span data-stu-id="e44b2-114">The first interval must have a Minimum limit of zero.</span></span>
-   <span data-ttu-id="e44b2-115">O último intervalo deve ter um limite Máximo de zero, que indica infinito.</span><span class="sxs-lookup"><span data-stu-id="e44b2-115">The last interval must have a Maximum limit of zero, which indicates infinity.</span></span>
-   <span data-ttu-id="e44b2-116">O limite Máximo de um intervalo deve ser o limite Mínimo do próximo intervalo.</span><span class="sxs-lookup"><span data-stu-id="e44b2-116">The Maximum limit of an interval must be the Minimum limit of the next interval.</span></span>

<span data-ttu-id="e44b2-117">Se um valor for o limite Máximo de um intervalo anterior e o limite Mínimo do próximo intervalo, a taxa de imposto do primeiro intervalo será aplicada ao valor.</span><span class="sxs-lookup"><span data-stu-id="e44b2-117">If an amount is the Maximum limit of the previous interval and the Minimum limit of the next interval, the sales tax rate of the first interval will be applied to the amount.</span></span> <span data-ttu-id="e44b2-118">Se um valor estiver fora dos intervalos definidos pelos limites superior e inferior, uma taxa de imposto igual a 0 será aplicada.</span><span class="sxs-lookup"><span data-stu-id="e44b2-118">If an amount falls outside the intervals that are defined by upper and lower limits, a sales tax rate of zero will be applied.</span></span>

## <a name="example-whole-amount-method-of-calculation"></a><span data-ttu-id="e44b2-119">Exemplo: método de cálculo de valor total</span><span class="sxs-lookup"><span data-stu-id="e44b2-119">Example: Whole amount method of calculation</span></span>
<span data-ttu-id="e44b2-120">Na página Valores do código de imposto, as taxas de imposto são configuradas nos intervalos a seguir:</span><span class="sxs-lookup"><span data-stu-id="e44b2-120">In the Sales tax code values page, sales tax rates are set up in the following intervals:</span></span>

|                   |                   |              |
|-------------------|-------------------|--------------|
| <span data-ttu-id="e44b2-121">**Limite mínimo**</span><span class="sxs-lookup"><span data-stu-id="e44b2-121">**Minimum limit**</span></span> | <span data-ttu-id="e44b2-122">**Limite máximo**</span><span class="sxs-lookup"><span data-stu-id="e44b2-122">**Maximum limit**</span></span> | <span data-ttu-id="e44b2-123">**Taxa de imposto**</span><span class="sxs-lookup"><span data-stu-id="e44b2-123">**Tax rate**</span></span> |
| <span data-ttu-id="e44b2-124">0,00</span><span class="sxs-lookup"><span data-stu-id="e44b2-124">0.00</span></span>              | <span data-ttu-id="e44b2-125">50,00</span><span class="sxs-lookup"><span data-stu-id="e44b2-125">50.00</span></span>             | <span data-ttu-id="e44b2-126">30%</span><span class="sxs-lookup"><span data-stu-id="e44b2-126">30%</span></span>          |
| <span data-ttu-id="e44b2-127">50,00</span><span class="sxs-lookup"><span data-stu-id="e44b2-127">50.00</span></span>             | <span data-ttu-id="e44b2-128">100,00</span><span class="sxs-lookup"><span data-stu-id="e44b2-128">100.00</span></span>            | <span data-ttu-id="e44b2-129">20%</span><span class="sxs-lookup"><span data-stu-id="e44b2-129">20%</span></span>          |
| <span data-ttu-id="e44b2-130">100,00</span><span class="sxs-lookup"><span data-stu-id="e44b2-130">100.00</span></span>            | <span data-ttu-id="e44b2-131">0,00</span><span class="sxs-lookup"><span data-stu-id="e44b2-131">0.00</span></span>              | <span data-ttu-id="e44b2-132">10%</span><span class="sxs-lookup"><span data-stu-id="e44b2-132">10%</span></span>          |

<span data-ttu-id="e44b2-133">O imposto é calculado sobre o valor tributável total.</span><span class="sxs-lookup"><span data-stu-id="e44b2-133">The sales tax is calculated on the whole taxable amount.</span></span>

| <span data-ttu-id="e44b2-134">Valor tributável (preço)</span><span class="sxs-lookup"><span data-stu-id="e44b2-134">Taxable amount (price)</span></span> | <span data-ttu-id="e44b2-135">Cálculo</span><span class="sxs-lookup"><span data-stu-id="e44b2-135">Calculation</span></span>    | <span data-ttu-id="e44b2-136">Imposto</span><span class="sxs-lookup"><span data-stu-id="e44b2-136">Sales tax</span></span> |
|------------------------|----------------|-----------|
| <span data-ttu-id="e44b2-137">35,00</span><span class="sxs-lookup"><span data-stu-id="e44b2-137">35.00</span></span>                  | <span data-ttu-id="e44b2-138">35,00 \* 0,30</span><span class="sxs-lookup"><span data-stu-id="e44b2-138">35.00 \* 0.30</span></span>  | <span data-ttu-id="e44b2-139">R$ 10,50</span><span class="sxs-lookup"><span data-stu-id="e44b2-139">10.50</span></span>     |
| <span data-ttu-id="e44b2-140">50,00</span><span class="sxs-lookup"><span data-stu-id="e44b2-140">50.00</span></span>                  | <span data-ttu-id="e44b2-141">50,00 \* 0,30</span><span class="sxs-lookup"><span data-stu-id="e44b2-141">50.00 \* 0.30</span></span>  | <span data-ttu-id="e44b2-142">15,00</span><span class="sxs-lookup"><span data-stu-id="e44b2-142">15.00</span></span>     |
| <span data-ttu-id="e44b2-143">85,00</span><span class="sxs-lookup"><span data-stu-id="e44b2-143">85.00</span></span>                  | <span data-ttu-id="e44b2-144">85,00 \* 0,20</span><span class="sxs-lookup"><span data-stu-id="e44b2-144">85.00 \* 0.20</span></span>  | <span data-ttu-id="e44b2-145">17,00</span><span class="sxs-lookup"><span data-stu-id="e44b2-145">17.00</span></span>     |
| <span data-ttu-id="e44b2-146">305,00</span><span class="sxs-lookup"><span data-stu-id="e44b2-146">305.00</span></span>                 | <span data-ttu-id="e44b2-147">305,00 \* 0,10</span><span class="sxs-lookup"><span data-stu-id="e44b2-147">305.00 \* 0.10</span></span> | <span data-ttu-id="e44b2-148">30,50</span><span class="sxs-lookup"><span data-stu-id="e44b2-148">30.50</span></span>     |

## <a name="example-interval-method-of-calculation"></a><span data-ttu-id="e44b2-149">Exemplo: método de cálculo de intervalo</span><span class="sxs-lookup"><span data-stu-id="e44b2-149">Example: Interval method of calculation</span></span>
<span data-ttu-id="e44b2-150">Na página Valores, as taxas de imposto são configuradas nos intervalos a seguir:</span><span class="sxs-lookup"><span data-stu-id="e44b2-150">In the Values page, sales tax rates are set up in the following intervals:</span></span>

|                   |                   |              |
|-------------------|-------------------|--------------|
| <span data-ttu-id="e44b2-151">**Limite mínimo**</span><span class="sxs-lookup"><span data-stu-id="e44b2-151">**Minimum limit**</span></span> | <span data-ttu-id="e44b2-152">**Limite máximo**</span><span class="sxs-lookup"><span data-stu-id="e44b2-152">**Maximum limit**</span></span> | <span data-ttu-id="e44b2-153">**Taxa de imposto**</span><span class="sxs-lookup"><span data-stu-id="e44b2-153">**Tax rate**</span></span> |
| <span data-ttu-id="e44b2-154">0,00</span><span class="sxs-lookup"><span data-stu-id="e44b2-154">0.00</span></span>              | <span data-ttu-id="e44b2-155">50,00</span><span class="sxs-lookup"><span data-stu-id="e44b2-155">50.00</span></span>             | <span data-ttu-id="e44b2-156">30%</span><span class="sxs-lookup"><span data-stu-id="e44b2-156">30%</span></span>          |
| <span data-ttu-id="e44b2-157">50,00</span><span class="sxs-lookup"><span data-stu-id="e44b2-157">50.00</span></span>             | <span data-ttu-id="e44b2-158">100,00</span><span class="sxs-lookup"><span data-stu-id="e44b2-158">100.00</span></span>            | <span data-ttu-id="e44b2-159">20%</span><span class="sxs-lookup"><span data-stu-id="e44b2-159">20%</span></span>          |
| <span data-ttu-id="e44b2-160">100,00</span><span class="sxs-lookup"><span data-stu-id="e44b2-160">100.00</span></span>            | <span data-ttu-id="e44b2-161">0,00</span><span class="sxs-lookup"><span data-stu-id="e44b2-161">0.00</span></span>              | <span data-ttu-id="e44b2-162">10%</span><span class="sxs-lookup"><span data-stu-id="e44b2-162">10%</span></span>          |

<span data-ttu-id="e44b2-163">O imposto sobre vendas é a soma dos valores de imposto calculados para cada intervalo de valor.</span><span class="sxs-lookup"><span data-stu-id="e44b2-163">The sales tax is the sum of the tax amounts that are calculated for each amount interval.</span></span>

| <span data-ttu-id="e44b2-164">Valor tributável (preço)</span><span class="sxs-lookup"><span data-stu-id="e44b2-164">Taxable amount (price)</span></span> | <span data-ttu-id="e44b2-165">Cálculo</span><span class="sxs-lookup"><span data-stu-id="e44b2-165">Calculation</span></span>                                                               | <span data-ttu-id="e44b2-166">Imposto</span><span class="sxs-lookup"><span data-stu-id="e44b2-166">Sales tax</span></span> |
|------------------------|---------------------------------------------------------------------------|-----------|
| <span data-ttu-id="e44b2-167">35,00</span><span class="sxs-lookup"><span data-stu-id="e44b2-167">35.00</span></span>                  | <span data-ttu-id="e44b2-168">35,00 \* 0,30</span><span class="sxs-lookup"><span data-stu-id="e44b2-168">35.00 \* 0.30</span></span>                                                             | <span data-ttu-id="e44b2-169">R$ 10,50</span><span class="sxs-lookup"><span data-stu-id="e44b2-169">10.50</span></span>     |
| <span data-ttu-id="e44b2-170">50,00</span><span class="sxs-lookup"><span data-stu-id="e44b2-170">50.00</span></span>                  | <span data-ttu-id="e44b2-171">50,00 \* 0,30</span><span class="sxs-lookup"><span data-stu-id="e44b2-171">50.00 \* 0.30</span></span>                                                             | <span data-ttu-id="e44b2-172">15,00</span><span class="sxs-lookup"><span data-stu-id="e44b2-172">15.00</span></span>     |
| <span data-ttu-id="e44b2-173">85,00</span><span class="sxs-lookup"><span data-stu-id="e44b2-173">85.00</span></span>                  | <span data-ttu-id="e44b2-174">(50,00 \* 0,30 = 15,00) + (35,00 \* 0,20 = 7,00)</span><span class="sxs-lookup"><span data-stu-id="e44b2-174">(50.00 \* 0.30 = 15.00) + (35.00 \* 0.20 = 7.00)</span></span>                          | <span data-ttu-id="e44b2-175">22,00</span><span class="sxs-lookup"><span data-stu-id="e44b2-175">22.00</span></span>     |
| <span data-ttu-id="e44b2-176">305,00</span><span class="sxs-lookup"><span data-stu-id="e44b2-176">305.00</span></span>                 | <span data-ttu-id="e44b2-177">(50,00 \* 0,30 = 15,00) + (50,00 \* 0,20 = 10,00) + (205 \* 0,10 = 20,50)</span><span class="sxs-lookup"><span data-stu-id="e44b2-177">(50.00 \* 0.30 = 15.00) + (50.00 \* 0.20 = 10.00) + (205 \* 0.10 = 20.50)</span></span> | <span data-ttu-id="e44b2-178">45.50</span><span class="sxs-lookup"><span data-stu-id="e44b2-178">45.50</span></span>     |



<span data-ttu-id="e44b2-179">Para obter mais informações, consulte [Taxas de imposto baseadas nos métodos Base marginal e Cálculo](marginal-base-field.md)</span><span class="sxs-lookup"><span data-stu-id="e44b2-179">For more information, see [Sales tax rates based on the Marginal base and Calculation methods](marginal-base-field.md).</span></span>





