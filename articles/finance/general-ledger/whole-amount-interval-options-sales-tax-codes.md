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
ms.custom: 5624
ms.assetid: 96166db4-b7ca-470b-aeb7-0a66fe0554c4
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ec724030e12e504625b2b102cba25b7eddbf7e96
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4978427"
---
# <a name="whole-amount-and-interval-calculation-options-for-sales-tax-codes"></a><span data-ttu-id="59dd1-103">Opções de cálculo de intervalo e valor total para códigos de imposto</span><span class="sxs-lookup"><span data-stu-id="59dd1-103">Whole amount and Interval calculation options for sales tax codes</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="59dd1-104">Este artigo explica as opções para o campo Método de cálculo em códigos de imposto e como o imposto é calculado para intervalos e valores inteiros.</span><span class="sxs-lookup"><span data-stu-id="59dd1-104">This article explains the options for the Calculation method field on sales tax codes and how sales tax is calculated for intervals and whole amounts.</span></span>

<span data-ttu-id="59dd1-105">Você pode configurar um código de imposto a ser calculado com base em um valor inteiro ou em um intervalo de valores.</span><span class="sxs-lookup"><span data-stu-id="59dd1-105">You can set up a sales tax code to be calculated based on a whole amount or an interval amount.</span></span> <span data-ttu-id="59dd1-106">Na página Códigos de imposto, use o campo Método de cálculo na Guia Rápida Cálculo para selecionar como calcular um código de imposto.</span><span class="sxs-lookup"><span data-stu-id="59dd1-106">In the Sales tax codes page, use the Calculation method field on the Calculation FastTab to select how to calculate a sales tax code.</span></span>
- <span data-ttu-id="59dd1-107">Valor total - a taxa de imposto é aplicada ao valor tributável total.</span><span class="sxs-lookup"><span data-stu-id="59dd1-107">Whole amount – The tax rate is applied to the whole taxable amount.</span></span>
- <span data-ttu-id="59dd1-108">Intervalo - o valor tributável é dividido em partes, cada uma dentro de um intervalo que tem uma taxa de imposto sobre vendas específica.</span><span class="sxs-lookup"><span data-stu-id="59dd1-108">Interval – The taxable amount is divided into parts, each of which falls in a range that has a specific sales tax rate.</span></span> <span data-ttu-id="59dd1-109">A parte do valor inserida em um determinado intervalo é taxada de acordo com a taxa de imposto do intervalo.</span><span class="sxs-lookup"><span data-stu-id="59dd1-109">The part of the amount that falls in a given interval is taxed according to the tax rate for that interval.</span></span> <span data-ttu-id="59dd1-110">O imposto sobre vendas é a soma dos valores de imposto calculados para cada intervalo de valor.</span><span class="sxs-lookup"><span data-stu-id="59dd1-110">The sales tax is the sum of the tax amounts that are calculated for each amount interval.</span></span>
  > [!NOTE]                                                                                                                              
  > <span data-ttu-id="59dd1-111">A opção Intervalo está disponível somente quando você seleciona Linha no campo Método de cálculo na área Impostos da página Parâmetros da contabilidade.</span><span class="sxs-lookup"><span data-stu-id="59dd1-111">The Interval option is available only when you select Line in the Calculation method field in the Sales tax area of the General ledger parameters page.</span></span> 

<span data-ttu-id="59dd1-112">Os intervalos são configurados na página Valores de código de imposto inserindo valores de limite Mínimo e Máximo por taxa de impostos.</span><span class="sxs-lookup"><span data-stu-id="59dd1-112">Intervals are set up in the Sales tax code values page by entering Minimum and Maximum limit amounts per tax rate.</span></span> <span data-ttu-id="59dd1-113">Para que os impostos possam ser calculados em todos os valores tributáveis, independente do método de cálculo selecionado, os intervalos devem seguir as seguintes regras:</span><span class="sxs-lookup"><span data-stu-id="59dd1-113">For taxes to be calculated on all taxable amounts, regardless of which calculation method is selected, intervals must follow these rules:</span></span>
-   <span data-ttu-id="59dd1-114">O primeiro intervalo deve ter um limite Mínimo de zero.</span><span class="sxs-lookup"><span data-stu-id="59dd1-114">The first interval must have a Minimum limit of zero.</span></span>
-   <span data-ttu-id="59dd1-115">O último intervalo deve ter um limite Máximo de zero, que indica infinito.</span><span class="sxs-lookup"><span data-stu-id="59dd1-115">The last interval must have a Maximum limit of zero, which indicates infinity.</span></span>
-   <span data-ttu-id="59dd1-116">O limite Máximo de um intervalo deve ser o limite Mínimo do próximo intervalo.</span><span class="sxs-lookup"><span data-stu-id="59dd1-116">The Maximum limit of an interval must be the Minimum limit of the next interval.</span></span>

<span data-ttu-id="59dd1-117">Se um valor for o limite Máximo de um intervalo anterior e o limite Mínimo do próximo intervalo, a taxa de imposto do primeiro intervalo será aplicada ao valor.</span><span class="sxs-lookup"><span data-stu-id="59dd1-117">If an amount is the Maximum limit of the previous interval and the Minimum limit of the next interval, the sales tax rate of the first interval will be applied to the amount.</span></span> <span data-ttu-id="59dd1-118">Se um valor estiver fora dos intervalos definidos pelos limites superior e inferior, uma taxa de imposto igual a 0 será aplicada.</span><span class="sxs-lookup"><span data-stu-id="59dd1-118">If an amount falls outside the intervals that are defined by upper and lower limits, a sales tax rate of zero will be applied.</span></span>

## <a name="example-whole-amount-method-of-calculation"></a><span data-ttu-id="59dd1-119">Exemplo: método de cálculo de valor total</span><span class="sxs-lookup"><span data-stu-id="59dd1-119">Example: Whole amount method of calculation</span></span>
<span data-ttu-id="59dd1-120">Na página Valores do código de imposto, as taxas de imposto são configuradas nos intervalos a seguir:</span><span class="sxs-lookup"><span data-stu-id="59dd1-120">In the Sales tax code values page, sales tax rates are set up in the following intervals:</span></span>

|                   |                   |              |
|-------------------|-------------------|--------------|
| <span data-ttu-id="59dd1-121">**Limite mínimo**</span><span class="sxs-lookup"><span data-stu-id="59dd1-121">**Minimum limit**</span></span> | <span data-ttu-id="59dd1-122">**Limite máximo**</span><span class="sxs-lookup"><span data-stu-id="59dd1-122">**Maximum limit**</span></span> | <span data-ttu-id="59dd1-123">**Taxa de imposto**</span><span class="sxs-lookup"><span data-stu-id="59dd1-123">**Tax rate**</span></span> |
| <span data-ttu-id="59dd1-124">0,00</span><span class="sxs-lookup"><span data-stu-id="59dd1-124">0.00</span></span>              | <span data-ttu-id="59dd1-125">50,00</span><span class="sxs-lookup"><span data-stu-id="59dd1-125">50.00</span></span>             | <span data-ttu-id="59dd1-126">30%</span><span class="sxs-lookup"><span data-stu-id="59dd1-126">30%</span></span>          |
| <span data-ttu-id="59dd1-127">50,00</span><span class="sxs-lookup"><span data-stu-id="59dd1-127">50.00</span></span>             | <span data-ttu-id="59dd1-128">100,00</span><span class="sxs-lookup"><span data-stu-id="59dd1-128">100.00</span></span>            | <span data-ttu-id="59dd1-129">20%</span><span class="sxs-lookup"><span data-stu-id="59dd1-129">20%</span></span>          |
| <span data-ttu-id="59dd1-130">100,00</span><span class="sxs-lookup"><span data-stu-id="59dd1-130">100.00</span></span>            | <span data-ttu-id="59dd1-131">0,00</span><span class="sxs-lookup"><span data-stu-id="59dd1-131">0.00</span></span>              | <span data-ttu-id="59dd1-132">10%</span><span class="sxs-lookup"><span data-stu-id="59dd1-132">10%</span></span>          |

<span data-ttu-id="59dd1-133">O imposto é calculado sobre o valor tributável total.</span><span class="sxs-lookup"><span data-stu-id="59dd1-133">The sales tax is calculated on the whole taxable amount.</span></span>

| <span data-ttu-id="59dd1-134">Valor tributável (preço)</span><span class="sxs-lookup"><span data-stu-id="59dd1-134">Taxable amount (price)</span></span> | <span data-ttu-id="59dd1-135">Cálculo</span><span class="sxs-lookup"><span data-stu-id="59dd1-135">Calculation</span></span>    | <span data-ttu-id="59dd1-136">Imposto</span><span class="sxs-lookup"><span data-stu-id="59dd1-136">Sales tax</span></span> |
|------------------------|----------------|-----------|
| <span data-ttu-id="59dd1-137">35,00</span><span class="sxs-lookup"><span data-stu-id="59dd1-137">35.00</span></span>                  | <span data-ttu-id="59dd1-138">35,00 \* 0,30</span><span class="sxs-lookup"><span data-stu-id="59dd1-138">35.00 \* 0.30</span></span>  | <span data-ttu-id="59dd1-139">R$ 10,50</span><span class="sxs-lookup"><span data-stu-id="59dd1-139">10.50</span></span>     |
| <span data-ttu-id="59dd1-140">50,00</span><span class="sxs-lookup"><span data-stu-id="59dd1-140">50.00</span></span>                  | <span data-ttu-id="59dd1-141">50,00 \* 0,30</span><span class="sxs-lookup"><span data-stu-id="59dd1-141">50.00 \* 0.30</span></span>  | <span data-ttu-id="59dd1-142">15,00</span><span class="sxs-lookup"><span data-stu-id="59dd1-142">15.00</span></span>     |
| <span data-ttu-id="59dd1-143">85,00</span><span class="sxs-lookup"><span data-stu-id="59dd1-143">85.00</span></span>                  | <span data-ttu-id="59dd1-144">85,00 \* 0,20</span><span class="sxs-lookup"><span data-stu-id="59dd1-144">85.00 \* 0.20</span></span>  | <span data-ttu-id="59dd1-145">17,00</span><span class="sxs-lookup"><span data-stu-id="59dd1-145">17.00</span></span>     |
| <span data-ttu-id="59dd1-146">305,00</span><span class="sxs-lookup"><span data-stu-id="59dd1-146">305.00</span></span>                 | <span data-ttu-id="59dd1-147">305,00 \* 0,10</span><span class="sxs-lookup"><span data-stu-id="59dd1-147">305.00 \* 0.10</span></span> | <span data-ttu-id="59dd1-148">30,50</span><span class="sxs-lookup"><span data-stu-id="59dd1-148">30.50</span></span>     |

## <a name="example-interval-method-of-calculation"></a><span data-ttu-id="59dd1-149">Exemplo: método de cálculo de intervalo</span><span class="sxs-lookup"><span data-stu-id="59dd1-149">Example: Interval method of calculation</span></span>
<span data-ttu-id="59dd1-150">Na página Valores, as taxas de imposto são configuradas nos intervalos a seguir:</span><span class="sxs-lookup"><span data-stu-id="59dd1-150">In the Values page, sales tax rates are set up in the following intervals:</span></span>

|                   |                   |              |
|-------------------|-------------------|--------------|
| <span data-ttu-id="59dd1-151">**Limite mínimo**</span><span class="sxs-lookup"><span data-stu-id="59dd1-151">**Minimum limit**</span></span> | <span data-ttu-id="59dd1-152">**Limite máximo**</span><span class="sxs-lookup"><span data-stu-id="59dd1-152">**Maximum limit**</span></span> | <span data-ttu-id="59dd1-153">**Taxa de imposto**</span><span class="sxs-lookup"><span data-stu-id="59dd1-153">**Tax rate**</span></span> |
| <span data-ttu-id="59dd1-154">0,00</span><span class="sxs-lookup"><span data-stu-id="59dd1-154">0.00</span></span>              | <span data-ttu-id="59dd1-155">50,00</span><span class="sxs-lookup"><span data-stu-id="59dd1-155">50.00</span></span>             | <span data-ttu-id="59dd1-156">30%</span><span class="sxs-lookup"><span data-stu-id="59dd1-156">30%</span></span>          |
| <span data-ttu-id="59dd1-157">50,00</span><span class="sxs-lookup"><span data-stu-id="59dd1-157">50.00</span></span>             | <span data-ttu-id="59dd1-158">100,00</span><span class="sxs-lookup"><span data-stu-id="59dd1-158">100.00</span></span>            | <span data-ttu-id="59dd1-159">20%</span><span class="sxs-lookup"><span data-stu-id="59dd1-159">20%</span></span>          |
| <span data-ttu-id="59dd1-160">100,00</span><span class="sxs-lookup"><span data-stu-id="59dd1-160">100.00</span></span>            | <span data-ttu-id="59dd1-161">0,00</span><span class="sxs-lookup"><span data-stu-id="59dd1-161">0.00</span></span>              | <span data-ttu-id="59dd1-162">10%</span><span class="sxs-lookup"><span data-stu-id="59dd1-162">10%</span></span>          |

<span data-ttu-id="59dd1-163">O imposto sobre vendas é a soma dos valores de imposto calculados para cada intervalo de valor.</span><span class="sxs-lookup"><span data-stu-id="59dd1-163">The sales tax is the sum of the tax amounts that are calculated for each amount interval.</span></span>

| <span data-ttu-id="59dd1-164">Valor tributável (preço)</span><span class="sxs-lookup"><span data-stu-id="59dd1-164">Taxable amount (price)</span></span> | <span data-ttu-id="59dd1-165">Cálculo</span><span class="sxs-lookup"><span data-stu-id="59dd1-165">Calculation</span></span>                                                               | <span data-ttu-id="59dd1-166">Imposto</span><span class="sxs-lookup"><span data-stu-id="59dd1-166">Sales tax</span></span> |
|------------------------|---------------------------------------------------------------------------|-----------|
| <span data-ttu-id="59dd1-167">35,00</span><span class="sxs-lookup"><span data-stu-id="59dd1-167">35.00</span></span>                  | <span data-ttu-id="59dd1-168">35,00 \* 0,30</span><span class="sxs-lookup"><span data-stu-id="59dd1-168">35.00 \* 0.30</span></span>                                                             | <span data-ttu-id="59dd1-169">R$ 10,50</span><span class="sxs-lookup"><span data-stu-id="59dd1-169">10.50</span></span>     |
| <span data-ttu-id="59dd1-170">50,00</span><span class="sxs-lookup"><span data-stu-id="59dd1-170">50.00</span></span>                  | <span data-ttu-id="59dd1-171">50,00 \* 0,30</span><span class="sxs-lookup"><span data-stu-id="59dd1-171">50.00 \* 0.30</span></span>                                                             | <span data-ttu-id="59dd1-172">15,00</span><span class="sxs-lookup"><span data-stu-id="59dd1-172">15.00</span></span>     |
| <span data-ttu-id="59dd1-173">85,00</span><span class="sxs-lookup"><span data-stu-id="59dd1-173">85.00</span></span>                  | <span data-ttu-id="59dd1-174">(50,00 \* 0,30 = 15,00) + (35,00 \* 0,20 = 7,00)</span><span class="sxs-lookup"><span data-stu-id="59dd1-174">(50.00 \* 0.30 = 15.00) + (35.00 \* 0.20 = 7.00)</span></span>                          | <span data-ttu-id="59dd1-175">22,00</span><span class="sxs-lookup"><span data-stu-id="59dd1-175">22.00</span></span>     |
| <span data-ttu-id="59dd1-176">305,00</span><span class="sxs-lookup"><span data-stu-id="59dd1-176">305.00</span></span>                 | <span data-ttu-id="59dd1-177">(50,00 \* 0,30 = 15,00) + (50,00 \* 0,20 = 10,00) + (205 \* 0,10 = 20,50)</span><span class="sxs-lookup"><span data-stu-id="59dd1-177">(50.00 \* 0.30 = 15.00) + (50.00 \* 0.20 = 10.00) + (205 \* 0.10 = 20.50)</span></span> | <span data-ttu-id="59dd1-178">45.50</span><span class="sxs-lookup"><span data-stu-id="59dd1-178">45.50</span></span>     |



<span data-ttu-id="59dd1-179">Para obter mais informações, consulte [Taxas de imposto baseadas nos métodos Base marginal e Cálculo](marginal-base-field.md)</span><span class="sxs-lookup"><span data-stu-id="59dd1-179">For more information, see [Sales tax rates based on the Marginal base and Calculation methods](marginal-base-field.md).</span></span>





