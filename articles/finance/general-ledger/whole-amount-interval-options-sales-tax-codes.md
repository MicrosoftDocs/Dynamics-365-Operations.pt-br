---
title: Opções de cálculo de intervalo e valor total para códigos de imposto
description: Este artigo explica as opções para o campo Método de cálculo em códigos de imposto e como o imposto é calculado para intervalos e valores inteiros.
author: ShylaThompson
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: 48569da2d504e4c380ca89bfec4450ad1b9888e5
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5842359"
---
# <a name="whole-amount-and-interval-calculation-options-for-sales-tax-codes"></a><span data-ttu-id="806db-103">Opções de cálculo de intervalo e valor total para códigos de imposto</span><span class="sxs-lookup"><span data-stu-id="806db-103">Whole amount and Interval calculation options for sales tax codes</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="806db-104">Este artigo explica as opções para o campo Método de cálculo em códigos de imposto e como o imposto é calculado para intervalos e valores inteiros.</span><span class="sxs-lookup"><span data-stu-id="806db-104">This article explains the options for the Calculation method field on sales tax codes and how sales tax is calculated for intervals and whole amounts.</span></span>

<span data-ttu-id="806db-105">Você pode configurar um código de imposto a ser calculado com base em um valor inteiro ou em um intervalo de valores.</span><span class="sxs-lookup"><span data-stu-id="806db-105">You can set up a sales tax code to be calculated based on a whole amount or an interval amount.</span></span> <span data-ttu-id="806db-106">Na página Códigos de imposto, use o campo Método de cálculo na Guia Rápida Cálculo para selecionar como calcular um código de imposto.</span><span class="sxs-lookup"><span data-stu-id="806db-106">In the Sales tax codes page, use the Calculation method field on the Calculation FastTab to select how to calculate a sales tax code.</span></span>
- <span data-ttu-id="806db-107">Valor total - a taxa de imposto é aplicada ao valor tributável total.</span><span class="sxs-lookup"><span data-stu-id="806db-107">Whole amount – The tax rate is applied to the whole taxable amount.</span></span>
- <span data-ttu-id="806db-108">Intervalo - o valor tributável é dividido em partes, cada uma dentro de um intervalo que tem uma taxa de imposto sobre vendas específica.</span><span class="sxs-lookup"><span data-stu-id="806db-108">Interval – The taxable amount is divided into parts, each of which falls in a range that has a specific sales tax rate.</span></span> <span data-ttu-id="806db-109">A parte do valor inserida em um determinado intervalo é taxada de acordo com a taxa de imposto do intervalo.</span><span class="sxs-lookup"><span data-stu-id="806db-109">The part of the amount that falls in a given interval is taxed according to the tax rate for that interval.</span></span> <span data-ttu-id="806db-110">O imposto sobre vendas é a soma dos valores de imposto calculados para cada intervalo de valor.</span><span class="sxs-lookup"><span data-stu-id="806db-110">The sales tax is the sum of the tax amounts that are calculated for each amount interval.</span></span>
  > [!NOTE]                                                                                                                              
  > <span data-ttu-id="806db-111">A opção Intervalo está disponível somente quando você seleciona Linha no campo Método de cálculo na área Impostos da página Parâmetros da contabilidade.</span><span class="sxs-lookup"><span data-stu-id="806db-111">The Interval option is available only when you select Line in the Calculation method field in the Sales tax area of the General ledger parameters page.</span></span> 

<span data-ttu-id="806db-112">Os intervalos são configurados na página Valores de código de imposto inserindo valores de limite Mínimo e Máximo por taxa de impostos.</span><span class="sxs-lookup"><span data-stu-id="806db-112">Intervals are set up in the Sales tax code values page by entering Minimum and Maximum limit amounts per tax rate.</span></span> <span data-ttu-id="806db-113">Para que os impostos possam ser calculados em todos os valores tributáveis, independente do método de cálculo selecionado, os intervalos devem seguir as seguintes regras:</span><span class="sxs-lookup"><span data-stu-id="806db-113">For taxes to be calculated on all taxable amounts, regardless of which calculation method is selected, intervals must follow these rules:</span></span>
-   <span data-ttu-id="806db-114">O primeiro intervalo deve ter um limite Mínimo de zero.</span><span class="sxs-lookup"><span data-stu-id="806db-114">The first interval must have a Minimum limit of zero.</span></span>
-   <span data-ttu-id="806db-115">O último intervalo deve ter um limite Máximo de zero, que indica infinito.</span><span class="sxs-lookup"><span data-stu-id="806db-115">The last interval must have a Maximum limit of zero, which indicates infinity.</span></span>
-   <span data-ttu-id="806db-116">O limite Máximo de um intervalo deve ser o limite Mínimo do próximo intervalo.</span><span class="sxs-lookup"><span data-stu-id="806db-116">The Maximum limit of an interval must be the Minimum limit of the next interval.</span></span>

<span data-ttu-id="806db-117">Se um valor for o limite Máximo de um intervalo anterior e o limite Mínimo do próximo intervalo, a taxa de imposto do primeiro intervalo será aplicada ao valor.</span><span class="sxs-lookup"><span data-stu-id="806db-117">If an amount is the Maximum limit of the previous interval and the Minimum limit of the next interval, the sales tax rate of the first interval will be applied to the amount.</span></span> <span data-ttu-id="806db-118">Se um valor estiver fora dos intervalos definidos pelos limites superior e inferior, uma taxa de imposto igual a 0 será aplicada.</span><span class="sxs-lookup"><span data-stu-id="806db-118">If an amount falls outside the intervals that are defined by upper and lower limits, a sales tax rate of zero will be applied.</span></span>

## <a name="example-whole-amount-method-of-calculation"></a><span data-ttu-id="806db-119">Exemplo: método de cálculo de valor total</span><span class="sxs-lookup"><span data-stu-id="806db-119">Example: Whole amount method of calculation</span></span>
<span data-ttu-id="806db-120">Na página Valores do código de imposto, as taxas de imposto são configuradas nos intervalos a seguir:</span><span class="sxs-lookup"><span data-stu-id="806db-120">In the Sales tax code values page, sales tax rates are set up in the following intervals:</span></span>

| <span data-ttu-id="806db-121">Limite mínimo</span><span class="sxs-lookup"><span data-stu-id="806db-121">Minimum limit</span></span>     | <span data-ttu-id="806db-122">Limite máximo</span><span class="sxs-lookup"><span data-stu-id="806db-122">Maximum limit</span></span>     | <span data-ttu-id="806db-123">Taxa de imposto</span><span class="sxs-lookup"><span data-stu-id="806db-123">Tax rate</span></span>     |
|-------------------|-------------------|--------------|
| <span data-ttu-id="806db-124">0,00</span><span class="sxs-lookup"><span data-stu-id="806db-124">0.00</span></span>              | <span data-ttu-id="806db-125">50,00</span><span class="sxs-lookup"><span data-stu-id="806db-125">50.00</span></span>             | <span data-ttu-id="806db-126">30%</span><span class="sxs-lookup"><span data-stu-id="806db-126">30%</span></span>          |
| <span data-ttu-id="806db-127">50,00</span><span class="sxs-lookup"><span data-stu-id="806db-127">50.00</span></span>             | <span data-ttu-id="806db-128">100,00</span><span class="sxs-lookup"><span data-stu-id="806db-128">100.00</span></span>            | <span data-ttu-id="806db-129">20%</span><span class="sxs-lookup"><span data-stu-id="806db-129">20%</span></span>          |
| <span data-ttu-id="806db-130">100,00</span><span class="sxs-lookup"><span data-stu-id="806db-130">100.00</span></span>            | <span data-ttu-id="806db-131">0,00</span><span class="sxs-lookup"><span data-stu-id="806db-131">0.00</span></span>              | <span data-ttu-id="806db-132">10%</span><span class="sxs-lookup"><span data-stu-id="806db-132">10%</span></span>          |

<span data-ttu-id="806db-133">O imposto é calculado sobre o valor tributável total.</span><span class="sxs-lookup"><span data-stu-id="806db-133">The sales tax is calculated on the whole taxable amount.</span></span>

| <span data-ttu-id="806db-134">Valor tributável (preço)</span><span class="sxs-lookup"><span data-stu-id="806db-134">Taxable amount (price)</span></span> | <span data-ttu-id="806db-135">Cálculo</span><span class="sxs-lookup"><span data-stu-id="806db-135">Calculation</span></span>    | <span data-ttu-id="806db-136">Imposto</span><span class="sxs-lookup"><span data-stu-id="806db-136">Sales tax</span></span> |
|------------------------|----------------|-----------|
| <span data-ttu-id="806db-137">35,00</span><span class="sxs-lookup"><span data-stu-id="806db-137">35.00</span></span>                  | <span data-ttu-id="806db-138">35,00 \* 0,30</span><span class="sxs-lookup"><span data-stu-id="806db-138">35.00 \* 0.30</span></span>  | <span data-ttu-id="806db-139">R$ 10,50</span><span class="sxs-lookup"><span data-stu-id="806db-139">10.50</span></span>     |
| <span data-ttu-id="806db-140">50,00</span><span class="sxs-lookup"><span data-stu-id="806db-140">50.00</span></span>                  | <span data-ttu-id="806db-141">50,00 \* 0,30</span><span class="sxs-lookup"><span data-stu-id="806db-141">50.00 \* 0.30</span></span>  | <span data-ttu-id="806db-142">15,00</span><span class="sxs-lookup"><span data-stu-id="806db-142">15.00</span></span>     |
| <span data-ttu-id="806db-143">85,00</span><span class="sxs-lookup"><span data-stu-id="806db-143">85.00</span></span>                  | <span data-ttu-id="806db-144">85,00 \* 0,20</span><span class="sxs-lookup"><span data-stu-id="806db-144">85.00 \* 0.20</span></span>  | <span data-ttu-id="806db-145">17,00</span><span class="sxs-lookup"><span data-stu-id="806db-145">17.00</span></span>     |
| <span data-ttu-id="806db-146">305,00</span><span class="sxs-lookup"><span data-stu-id="806db-146">305.00</span></span>                 | <span data-ttu-id="806db-147">305,00 \* 0,10</span><span class="sxs-lookup"><span data-stu-id="806db-147">305.00 \* 0.10</span></span> | <span data-ttu-id="806db-148">30,50</span><span class="sxs-lookup"><span data-stu-id="806db-148">30.50</span></span>     |

## <a name="example-interval-method-of-calculation"></a><span data-ttu-id="806db-149">Exemplo: método de cálculo de intervalo</span><span class="sxs-lookup"><span data-stu-id="806db-149">Example: Interval method of calculation</span></span>
<span data-ttu-id="806db-150">Na página Valores, as taxas de imposto são configuradas nos intervalos a seguir:</span><span class="sxs-lookup"><span data-stu-id="806db-150">In the Values page, sales tax rates are set up in the following intervals:</span></span>

| <span data-ttu-id="806db-151">Limite mínimo</span><span class="sxs-lookup"><span data-stu-id="806db-151">Minimum limit</span></span>     | <span data-ttu-id="806db-152">Limite máximo</span><span class="sxs-lookup"><span data-stu-id="806db-152">Maximum limit</span></span>     | <span data-ttu-id="806db-153">Taxa de imposto</span><span class="sxs-lookup"><span data-stu-id="806db-153">Tax rate</span></span>     |
|-------------------|-------------------|--------------|
| <span data-ttu-id="806db-154">0,00</span><span class="sxs-lookup"><span data-stu-id="806db-154">0.00</span></span>              | <span data-ttu-id="806db-155">50,00</span><span class="sxs-lookup"><span data-stu-id="806db-155">50.00</span></span>             | <span data-ttu-id="806db-156">30%</span><span class="sxs-lookup"><span data-stu-id="806db-156">30%</span></span>          |
| <span data-ttu-id="806db-157">50,00</span><span class="sxs-lookup"><span data-stu-id="806db-157">50.00</span></span>             | <span data-ttu-id="806db-158">100,00</span><span class="sxs-lookup"><span data-stu-id="806db-158">100.00</span></span>            | <span data-ttu-id="806db-159">20%</span><span class="sxs-lookup"><span data-stu-id="806db-159">20%</span></span>          |
| <span data-ttu-id="806db-160">100,00</span><span class="sxs-lookup"><span data-stu-id="806db-160">100.00</span></span>            | <span data-ttu-id="806db-161">0,00</span><span class="sxs-lookup"><span data-stu-id="806db-161">0.00</span></span>              | <span data-ttu-id="806db-162">10%</span><span class="sxs-lookup"><span data-stu-id="806db-162">10%</span></span>          |

<span data-ttu-id="806db-163">O imposto sobre vendas é a soma dos valores de imposto calculados para cada intervalo de valor.</span><span class="sxs-lookup"><span data-stu-id="806db-163">The sales tax is the sum of the tax amounts that are calculated for each amount interval.</span></span>

| <span data-ttu-id="806db-164">Valor tributável (preço)</span><span class="sxs-lookup"><span data-stu-id="806db-164">Taxable amount (price)</span></span> | <span data-ttu-id="806db-165">Cálculo</span><span class="sxs-lookup"><span data-stu-id="806db-165">Calculation</span></span>                                                               | <span data-ttu-id="806db-166">Imposto</span><span class="sxs-lookup"><span data-stu-id="806db-166">Sales tax</span></span> |
|------------------------|---------------------------------------------------------------------------|-----------|
| <span data-ttu-id="806db-167">35,00</span><span class="sxs-lookup"><span data-stu-id="806db-167">35.00</span></span>                  | <span data-ttu-id="806db-168">35,00 \* 0,30</span><span class="sxs-lookup"><span data-stu-id="806db-168">35.00 \* 0.30</span></span>                                                             | <span data-ttu-id="806db-169">R$ 10,50</span><span class="sxs-lookup"><span data-stu-id="806db-169">10.50</span></span>     |
| <span data-ttu-id="806db-170">50,00</span><span class="sxs-lookup"><span data-stu-id="806db-170">50.00</span></span>                  | <span data-ttu-id="806db-171">50,00 \* 0,30</span><span class="sxs-lookup"><span data-stu-id="806db-171">50.00 \* 0.30</span></span>                                                             | <span data-ttu-id="806db-172">15,00</span><span class="sxs-lookup"><span data-stu-id="806db-172">15.00</span></span>     |
| <span data-ttu-id="806db-173">85,00</span><span class="sxs-lookup"><span data-stu-id="806db-173">85.00</span></span>                  | <span data-ttu-id="806db-174">(50,00 \* 0,30 = 15,00) + (35,00 \* 0,20 = 7,00)</span><span class="sxs-lookup"><span data-stu-id="806db-174">(50.00 \* 0.30 = 15.00) + (35.00 \* 0.20 = 7.00)</span></span>                          | <span data-ttu-id="806db-175">22,00</span><span class="sxs-lookup"><span data-stu-id="806db-175">22.00</span></span>     |
| <span data-ttu-id="806db-176">305,00</span><span class="sxs-lookup"><span data-stu-id="806db-176">305.00</span></span>                 | <span data-ttu-id="806db-177">(50,00 \* 0,30 = 15,00) + (50,00 \* 0,20 = 10,00) + (205 \* 0,10 = 20,50)</span><span class="sxs-lookup"><span data-stu-id="806db-177">(50.00 \* 0.30 = 15.00) + (50.00 \* 0.20 = 10.00) + (205 \* 0.10 = 20.50)</span></span> | <span data-ttu-id="806db-178">45.50</span><span class="sxs-lookup"><span data-stu-id="806db-178">45.50</span></span>     |



<span data-ttu-id="806db-179">Para obter mais informações, consulte [Taxas de imposto baseadas nos métodos Base marginal e Cálculo](marginal-base-field.md)</span><span class="sxs-lookup"><span data-stu-id="806db-179">For more information, see [Sales tax rates based on the Marginal base and Calculation methods](marginal-base-field.md).</span></span>







[!INCLUDE[footer-include](../../includes/footer-banner.md)]