---
title: "Determinando as alíquotas de imposto com base nos campos Base marginal e Métodos de cálculo"
description: "Este tópico explica como os valores com base no método de cálculo marginais dos campos determinam as taxas de impostos sobre vendas e as transações de compra."
author: twheeloc
manager: AnnBe
ms.date: 10/26/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: TaxTable
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 7171
ms.assetid: 381fc309-b32a-4927-b5b8-fa1c31b0bd72
ms.search.region: Global
ms.author: vstehman
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 3e89953a448dcb592c12d5e35f739aeee79e5d0f
ms.contentlocale: pt-br
ms.lasthandoff: 04/13/2018

---

# <a name="sales-tax-rates-based-on-the-marginal-base-and-calculation-methods"></a><span data-ttu-id="67b7d-103">Determinando as alíquotas de imposto com base nos campos Base marginal e Métodos de cálculo</span><span class="sxs-lookup"><span data-stu-id="67b7d-103">Sales tax rates based on the Marginal base and Calculation methods</span></span>

[!INCLUDE [banner](../includes/banner.md)]

<span data-ttu-id="67b7d-104">Este tópico explica como os valores com base no método de cálculo marginais dos campos determinam as taxas de impostos sobre vendas e as transações de compra.</span><span class="sxs-lookup"><span data-stu-id="67b7d-104">This topic explains how the values in the fields Marginal base and Calculation method determine the tax rate(s) in sales and purchase transactions.</span></span>

<span data-ttu-id="67b7d-105">A Base marginal na Guia Rápida Cálculo na página de códigos Imposto determina qual valor será usado para separar as alíquotas apropriadas das taxas na página Valores de código de imposto.</span><span class="sxs-lookup"><span data-stu-id="67b7d-105">The Marginal base on the Calculation FastTab on the Sales tax codes page determines which amount is used to pick the appropriate tax rate(s) from the rates in the Sales tax code values page.</span></span> <span data-ttu-id="67b7d-106">O tipo de valor no campo Base marginal em combinação com o método no campo Método de cálculo determina a lógica para encontrar as alíquotas corretas para uma transação.</span><span class="sxs-lookup"><span data-stu-id="67b7d-106">The amount type in the Marginal base field in combination with the method in the Calculation method field determines the logic to find the correct tax rate(s) for a transaction.</span></span> 

<span data-ttu-id="67b7d-107">As diversas combinações de valores nesses campos produzem cálculos de imposto muito diferentes, como mostram os exemplos a seguir.</span><span class="sxs-lookup"><span data-stu-id="67b7d-107">Various combinations of values in these fields produce very different sales tax calculations, as shown by the following examples.</span></span> <span data-ttu-id="67b7d-108">Os exemplos usam os mesmos valores de intervalo de imposto, configurados para cada código de imposto na página Valores de códigos de imposto.</span><span class="sxs-lookup"><span data-stu-id="67b7d-108">The examples use the same tax interval values, which are set up for each tax code in the Sales tax codes values page.</span></span> <span data-ttu-id="67b7d-109">Para abrir essa página, clique em Código do imposto &gt; Valores na página Códigos de imposto.</span><span class="sxs-lookup"><span data-stu-id="67b7d-109">To open this page, click Sales tax code &gt; Values in the Sales tax codes page.</span></span>

> [!Important]                                                                                                                  
> <span data-ttu-id="67b7d-110">Se a Base marginal em um ou mais dos seus códigos de imposto se basear em valores ou em unidades de linha, o valor do campo Método de cálculo da página Parâmetros de contabilidade deverá ser definido como Linha.</span><span class="sxs-lookup"><span data-stu-id="67b7d-110">If the Marginal base on one or more of your sales tax codes is based on line amounts or units, the value of the Calculation method field in the General ledger parameters page must be set to Line.</span></span> |

## <a name="net-amount-per-line"></a><span data-ttu-id="67b7d-111">Valor líquido por linha</span><span class="sxs-lookup"><span data-stu-id="67b7d-111">Net amount per line</span></span>
<span data-ttu-id="67b7d-112">Selecione essa opção para determinar as taxas de imposto com base no valor líquido das linhas da fatura, excluindo outros impostos.</span><span class="sxs-lookup"><span data-stu-id="67b7d-112">Select this option to determine sales tax rates based on the net amount for the invoice lines, excluding any other taxes.</span></span>

### <a name="example"></a><span data-ttu-id="67b7d-113">exemplo</span><span class="sxs-lookup"><span data-stu-id="67b7d-113">Example</span></span>

<span data-ttu-id="67b7d-114">As taxas de impostos são configuradas nos intervalos a seguir.</span><span class="sxs-lookup"><span data-stu-id="67b7d-114">The sales tax rates are set up in the following intervals.</span></span>

| <span data-ttu-id="67b7d-115">Intervalo de valores</span><span class="sxs-lookup"><span data-stu-id="67b7d-115">Amount interval</span></span>    | <span data-ttu-id="67b7d-116">Taxa de imposto</span><span class="sxs-lookup"><span data-stu-id="67b7d-116">Tax rate</span></span> |
|--------------------|----------|
| <span data-ttu-id="67b7d-117">0 - 50</span><span class="sxs-lookup"><span data-stu-id="67b7d-117">0 - 50</span></span>             | <span data-ttu-id="67b7d-118">30%</span><span class="sxs-lookup"><span data-stu-id="67b7d-118">30%</span></span>      |
| <span data-ttu-id="67b7d-119">50 - 100</span><span class="sxs-lookup"><span data-stu-id="67b7d-119">50 - 100</span></span>           | <span data-ttu-id="67b7d-120">20%</span><span class="sxs-lookup"><span data-stu-id="67b7d-120">20%</span></span>      |
| <span data-ttu-id="67b7d-121">100 - 0 (&gt; 100)</span><span class="sxs-lookup"><span data-stu-id="67b7d-121">100 - 0 (&gt; 100)</span></span> | <span data-ttu-id="67b7d-122">10%</span><span class="sxs-lookup"><span data-stu-id="67b7d-122">10%</span></span>      |

> [!NOTE]                                                                                                             
> <span data-ttu-id="67b7d-123">O limite superior de zero (0) no último intervalo significa que todos os valores que ultrapassam 100 são incluídos no intervalo.</span><span class="sxs-lookup"><span data-stu-id="67b7d-123">The upper limit of zero (0) in the last interval means that all amounts that exceed 100 are included in the interval.</span></span>

<span data-ttu-id="67b7d-124">Base marginal: **Valor líquido por linha**</span><span class="sxs-lookup"><span data-stu-id="67b7d-124">Marginal base: **Net amount per line**</span></span> 

<span data-ttu-id="67b7d-125">Método de cálculo: **Intervalo**</span><span class="sxs-lookup"><span data-stu-id="67b7d-125">Calculation method: **Interval**</span></span> 

<span data-ttu-id="67b7d-126">Você compra oito luminárias que custam 25,00 cada.</span><span class="sxs-lookup"><span data-stu-id="67b7d-126">You buy 8 lamps that cost 25.00 each.</span></span> 

<span data-ttu-id="67b7d-127">O valor líquido da linha da fatura é 200,00.</span><span class="sxs-lookup"><span data-stu-id="67b7d-127">The net amount for the invoice line is 200.00.</span></span> 

<span data-ttu-id="67b7d-128">O imposto é calculado da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="67b7d-128">The tax is calculated as follows:</span></span> 

<span data-ttu-id="67b7d-129">Imposto total = 50 x 30% + 50 x 20% + 100 x 10% = 15 + 10 + 10 = 35,00.</span><span class="sxs-lookup"><span data-stu-id="67b7d-129">Total sales tax = 50 x 30% + 50 x 20% + 100 x 10% = 15 + 10 + 10 = 35.00</span></span> 

<span data-ttu-id="67b7d-130">Valor total da fatura = 200,00 + 35,00 = 235,00</span><span class="sxs-lookup"><span data-stu-id="67b7d-130">Total invoice amount = 200.00 + 35.00 = 235.00</span></span> 

<span data-ttu-id="67b7d-131">**Variação**</span><span class="sxs-lookup"><span data-stu-id="67b7d-131">**Variation**</span></span> 

<span data-ttu-id="67b7d-132">Se a fatura tiver duas linhas com quatro itens em cada, o valor líquido em cada linha será 100,00, e o imposto será calculado da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="67b7d-132">If the invoice has two lines with four items on each line, the net amount on each line is 100.00 and the sales tax is calculated as follows:</span></span> 

<span data-ttu-id="67b7d-133">Linha 1 do imposto = 50 x 30% + 50 x 20% = 15 + 10 = 25,00.</span><span class="sxs-lookup"><span data-stu-id="67b7d-133">Sales tax line 1 = 50 x 30% + 50 x 20% = 15 + 10 = 25.00</span></span> 

<span data-ttu-id="67b7d-134">Linha 2 do imposto = 50 x 30% + 50 x 20% = 15 + 10 = 25,00</span><span class="sxs-lookup"><span data-stu-id="67b7d-134">Sales tax line 2 = 50 x 30% + 50 x 20% = 15 + 10 = 25.00</span></span> 

<span data-ttu-id="67b7d-135">Total de imposto = 25,00 + 25,00 = 50,00</span><span class="sxs-lookup"><span data-stu-id="67b7d-135">Total sales tax = 25.00 + 25.00 = 50.00</span></span> 

<span data-ttu-id="67b7d-136">Valor total da fatura = 200,00 + 50,00 = 250,00</span><span class="sxs-lookup"><span data-stu-id="67b7d-136">Total invoice amount = 200.00 + 50.00 = 250.00</span></span>

## <a name="net-amount-per-unit"></a><span data-ttu-id="67b7d-137">Valor líquido por unidade</span><span class="sxs-lookup"><span data-stu-id="67b7d-137">Net amount per unit</span></span>
<span data-ttu-id="67b7d-138">Selecione essa opção para determinar as taxas de imposto com base no valor de cada unidade, excluindo outros impostos.</span><span class="sxs-lookup"><span data-stu-id="67b7d-138">Select this option to determine sales tax rates based on the value of each unit, excluding any other taxes.</span></span> <span data-ttu-id="67b7d-139">Quando uma Base marginal baseada em unidade for selecionada, então uma Unidade terá de ser especificada para o Código de imposto.</span><span class="sxs-lookup"><span data-stu-id="67b7d-139">When a unit based Marginal base is selected then also a Unit has to be specified for the Sales tax code.</span></span>

### <a name="example"></a><span data-ttu-id="67b7d-140">Exemplo</span><span class="sxs-lookup"><span data-stu-id="67b7d-140">Example</span></span>

<span data-ttu-id="67b7d-141">As taxas de impostos são configuradas nos intervalos a seguir.</span><span class="sxs-lookup"><span data-stu-id="67b7d-141">The sales tax rates are set up in the following intervals.</span></span>

| <span data-ttu-id="67b7d-142">Valor</span><span class="sxs-lookup"><span data-stu-id="67b7d-142">Amount</span></span>             | <span data-ttu-id="67b7d-143">Taxa de imposto</span><span class="sxs-lookup"><span data-stu-id="67b7d-143">Tax rate</span></span> |
|--------------------|----------|
| <span data-ttu-id="67b7d-144">0 - 50</span><span class="sxs-lookup"><span data-stu-id="67b7d-144">0 - 50</span></span>             | <span data-ttu-id="67b7d-145">30%</span><span class="sxs-lookup"><span data-stu-id="67b7d-145">30%</span></span>      |
| <span data-ttu-id="67b7d-146">50 - 100</span><span class="sxs-lookup"><span data-stu-id="67b7d-146">50 - 100</span></span>           | <span data-ttu-id="67b7d-147">20%</span><span class="sxs-lookup"><span data-stu-id="67b7d-147">20%</span></span>      |
| <span data-ttu-id="67b7d-148">100 - 0 (&gt; 100)</span><span class="sxs-lookup"><span data-stu-id="67b7d-148">100 - 0 (&gt; 100)</span></span> | <span data-ttu-id="67b7d-149">10%</span><span class="sxs-lookup"><span data-stu-id="67b7d-149">10%</span></span>      |

<span data-ttu-id="67b7d-150">Base marginal: **Valor líquido por unidade**</span><span class="sxs-lookup"><span data-stu-id="67b7d-150">Marginal base: **Net amount per unit**</span></span> 

<span data-ttu-id="67b7d-151">Método de cálculo: **Valor total**</span><span class="sxs-lookup"><span data-stu-id="67b7d-151">Calculation method: **Whole amount**</span></span> 

<span data-ttu-id="67b7d-152">Você compra oito luminárias que custam 25,00 cada.</span><span class="sxs-lookup"><span data-stu-id="67b7d-152">You buy 8 lamps that cost 25.00 each.</span></span> 

<span data-ttu-id="67b7d-153">O valor líquido da linha da fatura é 200,00.</span><span class="sxs-lookup"><span data-stu-id="67b7d-153">The net amount for the invoice line is 200.00.</span></span> 

<span data-ttu-id="67b7d-154">O imposto é calculado da seguinte maneira: Imposto por unidade = 25,00 x 30% = 7,50 Total de impostos = 7.50 x 8 = 60,00 Valor total da fatura = 200,00 + 60,00 = 260,00</span><span class="sxs-lookup"><span data-stu-id="67b7d-154">The tax is calculated as follows: Sales tax per unit = 25.00 x 30% = 7.50 Total sales tax = 7.50 x 8 units = 60.00 Total invoice amount = 200.00 + 60.00 = 260.00</span></span>

## <a name="net-amount-of-invoice-balance"></a><span data-ttu-id="67b7d-155">Valor líquido do saldo de fatura</span><span class="sxs-lookup"><span data-stu-id="67b7d-155">Net amount of invoice balance</span></span>

<span data-ttu-id="67b7d-156">Selecione essa opção para determinar as taxas de imposto no valor total da fatura, excluindo outros impostos.</span><span class="sxs-lookup"><span data-stu-id="67b7d-156">Select this option to determine sales tax rates based on the total value for the invoice, excluding any other taxes.</span></span>

### <a name="example"></a><span data-ttu-id="67b7d-157">exemplo</span><span class="sxs-lookup"><span data-stu-id="67b7d-157">Example</span></span>

<span data-ttu-id="67b7d-158">As taxas de impostos são configuradas nos intervalos a seguir.</span><span class="sxs-lookup"><span data-stu-id="67b7d-158">The sales tax rates are set up in the following intervals.</span></span>

| <span data-ttu-id="67b7d-159">Valor</span><span class="sxs-lookup"><span data-stu-id="67b7d-159">Amount</span></span>            | <span data-ttu-id="67b7d-160">Taxa de imposto</span><span class="sxs-lookup"><span data-stu-id="67b7d-160">Tax rate</span></span> |
|-------------------|----------|
| <span data-ttu-id="67b7d-161">0 - 50</span><span class="sxs-lookup"><span data-stu-id="67b7d-161">0 - 50</span></span>            | <span data-ttu-id="67b7d-162">30%</span><span class="sxs-lookup"><span data-stu-id="67b7d-162">30%</span></span>      |
| <span data-ttu-id="67b7d-163">50 - 100</span><span class="sxs-lookup"><span data-stu-id="67b7d-163">50 - 100</span></span>          | <span data-ttu-id="67b7d-164">20%</span><span class="sxs-lookup"><span data-stu-id="67b7d-164">20%</span></span>      |
| <span data-ttu-id="67b7d-165">100 -0 (&gt; 100)</span><span class="sxs-lookup"><span data-stu-id="67b7d-165">100 -0 (&gt; 100)</span></span> | <span data-ttu-id="67b7d-166">10%</span><span class="sxs-lookup"><span data-stu-id="67b7d-166">10%</span></span>      |

<span data-ttu-id="67b7d-167">Base marginal: **Valor líquido do saldo de fatura**</span><span class="sxs-lookup"><span data-stu-id="67b7d-167">Marginal base: **Net amount of invoice balance**</span></span> 

<span data-ttu-id="67b7d-168">Método de cálculo: **Intervalo** Uma fatura de venda tem duas linhas com quatro lâmpadas em cada linha por 25,00 cada.</span><span class="sxs-lookup"><span data-stu-id="67b7d-168">Calculation method: **Interval** A sales invoice has 2 lines with 4 lamps on each lines for 25.00 each.</span></span> <span data-ttu-id="67b7d-169">O valor líquido do saldo da fatura é 4 x 25,00 + 4 x 25,00 = 200,00.</span><span class="sxs-lookup"><span data-stu-id="67b7d-169">The net amount of invoice balance is 4 x 25.00 + 4 x 25.00 = 200.00.</span></span> <span data-ttu-id="67b7d-170">O imposto é calculado da seguinte maneira: Total de impostos = 50 x 0,30 + 50 x 0,20 + 100 x 0,10 = 15 + 10 + 10 = 35,00 Valor total da fatura = 200,00 + 35,00 = 235,00</span><span class="sxs-lookup"><span data-stu-id="67b7d-170">The tax is calculated as follows: Total sales tax = 50 x 0.30 + 50 x 0.20 + 100 x 0.10 = 15 + 10 + 10 = 35.00 Total invoice amount = 200.00 + 35.00 = 235.00</span></span>

## <a name="gross-amount-per-line"></a><span data-ttu-id="67b7d-171">Valor bruto por linha</span><span class="sxs-lookup"><span data-stu-id="67b7d-171">Gross amount per line</span></span>

<span data-ttu-id="67b7d-172">Selecione essa opção para determinar as taxas de imposto com base no valor da linha, incluindo todos os outros impostos para essa linha.</span><span class="sxs-lookup"><span data-stu-id="67b7d-172">Select this option to determine sales tax rates based on the value of the line including all other taxes for that line.</span></span>

> [!NOTE]
> <span data-ttu-id="67b7d-173">Em um grupo de impostos sobre vendas, você só pode ter um código de imposto com essa seleção no campo Base marginal.</span><span class="sxs-lookup"><span data-stu-id="67b7d-173">In a sales tax group, you can only have one sales tax code with this selection in the Marginal base field.</span></span>

### <a name="example"></a><span data-ttu-id="67b7d-174">Exemplo</span><span class="sxs-lookup"><span data-stu-id="67b7d-174">Example</span></span>

<span data-ttu-id="67b7d-175">As taxas de impostos são configuradas nos intervalos a seguir.</span><span class="sxs-lookup"><span data-stu-id="67b7d-175">The sales tax rates are set up in the following intervals.</span></span>

| <span data-ttu-id="67b7d-176">Valor</span><span class="sxs-lookup"><span data-stu-id="67b7d-176">Amount</span></span>             | <span data-ttu-id="67b7d-177">Taxa de imposto</span><span class="sxs-lookup"><span data-stu-id="67b7d-177">Tax rate</span></span> |
|--------------------|----------|
| <span data-ttu-id="67b7d-178">0 - 50</span><span class="sxs-lookup"><span data-stu-id="67b7d-178">0 - 50</span></span>             | <span data-ttu-id="67b7d-179">30%</span><span class="sxs-lookup"><span data-stu-id="67b7d-179">30%</span></span>      |
| <span data-ttu-id="67b7d-180">50 - 100</span><span class="sxs-lookup"><span data-stu-id="67b7d-180">50 - 100</span></span>           | <span data-ttu-id="67b7d-181">20%</span><span class="sxs-lookup"><span data-stu-id="67b7d-181">20%</span></span>      |
| <span data-ttu-id="67b7d-182">100 - 0 (&gt; 100)</span><span class="sxs-lookup"><span data-stu-id="67b7d-182">100 - 0 (&gt; 100)</span></span> | <span data-ttu-id="67b7d-183">10%</span><span class="sxs-lookup"><span data-stu-id="67b7d-183">10%</span></span>      |

<span data-ttu-id="67b7d-184">Base marginal: **Valor bruto por linha** Método de cálculo: **Intervalo** Adicionalmente, há um outro código de imposto calculado para um imposto especial de 5,00 sobre cada luminária.</span><span class="sxs-lookup"><span data-stu-id="67b7d-184">Marginal base: **Gross amount per line** Calculation method: **Interval** Additionally there is another tax code calculated for a special duty of 5.00 on each lamp.</span></span> <span data-ttu-id="67b7d-185">O imposto é somado ao valor líquido antes do cálculo do imposto sobre vendas.</span><span class="sxs-lookup"><span data-stu-id="67b7d-185">The duty is added to the net amount before the sales tax calculation.</span></span> <span data-ttu-id="67b7d-186">Você compra oito luminárias que custam 25,00 cada.</span><span class="sxs-lookup"><span data-stu-id="67b7d-186">You buy 8 lamps that cost 25.00 each.</span></span> <span data-ttu-id="67b7d-187">O valor líquido da linha da fatura é 200,00.</span><span class="sxs-lookup"><span data-stu-id="67b7d-187">The net amount for the invoice line is 200.00.</span></span> <span data-ttu-id="67b7d-188">O valor bruto da linha da fatura é 8 x 25,00 + 8 x 5,00 = 240,00.</span><span class="sxs-lookup"><span data-stu-id="67b7d-188">The gross amount for the invoice line is 8 x 25.00 + 8 x 5.00 = 240.00.</span></span> <span data-ttu-id="67b7d-189">O imposto é calculado da seguinte maneira: Total de impostos = 50 x 0,30 + 50 x 0,20 + 140 x 0,10 = 15 + 20 + 14 = 39,00 Total de impostos especiais = 5,00 x 8 = 40,00 Valor total da fatura = 200,00 + 39,00 + 40,00 = 279,00</span><span class="sxs-lookup"><span data-stu-id="67b7d-189">The tax is calculated as follows: Total sales tax = 50 x 0.30 + 50 x 0.20 + 140 x 0.10 = 15 + 20 + 14 = 39.00 Total duty = 5.00 x 8 = 40.00 Total invoice amount = 200.00 + 39.00 + 40.00 = 279.00</span></span>

<span data-ttu-id="67b7d-190">**Variação**</span><span class="sxs-lookup"><span data-stu-id="67b7d-190">**Variation**</span></span> 

<span data-ttu-id="67b7d-191">Se a fatura for criada com duas linhas de fatura com 4 itens em cada linha, o valor líquido por linha da fatura será 100,00.</span><span class="sxs-lookup"><span data-stu-id="67b7d-191">If the invoice is created by using 2 invoice lines with 4 items on each line, the net amount per invoice line is 100.00.</span></span> <span data-ttu-id="67b7d-192">O valor bruto (incluindo o imposto especial de 4 x 5,00) por linha da fatura será 120,00, e os impostos são criados como se segue: Linha da fatura de imposto 1 = 50 x 0,30 + 50 x 0,20 + 20 x 0,.10 = 15 + 10 + 2 = 27,00 Linha da fatura de imposto 2 = 50 x 0,30 + 50 x 0,20 + 20 x 0,10 = 15 + 10 + 2 = 27,00 Total de impostos = 27,00 = 27,00 + 54,00 Total de impostos especiais = 5,00 x 8 = 40,00 Valor total da fatura = 200,00 + 54,00 + 40,00 = 294,00</span><span class="sxs-lookup"><span data-stu-id="67b7d-192">The gross amount (including the duty of 4 x 5.00) per invoice line would be 120.00, and the sales tax is created as follows: Sales tax invoice line 1 = 50 x 0.30 + 50 x 0.20 + 20 x 0.10 = 15 + 10 + 2 = 27.00 Sales tax invoice line 2 = 50 x 0.30 + 50 x 0.20 + 20 x 0.10 = 15 + 10 + 2 = 27.00 Total sales tax = 27.00 + 27.00 = 54.00 Total duty = 5.00 x 8 = 40.00 Total invoice amount = 200.00 + 54.00 + 40.00 = 294.00</span></span>

## <a name="gross-amount-per-unit"></a><span data-ttu-id="67b7d-193">Valor bruto por unidade</span><span class="sxs-lookup"><span data-stu-id="67b7d-193">Gross amount per unit</span></span>

<span data-ttu-id="67b7d-194">Selecione essa opção para determinar as taxas de imposto com base no valor da unidade, incluindo outros impostos.</span><span class="sxs-lookup"><span data-stu-id="67b7d-194">Select this option to determine sales tax rates based on the value of the unit including any other taxes.</span></span>

> [!NOTE]
> <span data-ttu-id="67b7d-195">Em um grupo de impostos sobre vendas, você só pode ter um código de imposto com essa seleção no campo Base marginal.</span><span class="sxs-lookup"><span data-stu-id="67b7d-195">In a sales tax group, you can only have one sales tax code with this selection in the Marginal base field.</span></span>

### <a name="example"></a><span data-ttu-id="67b7d-196">Exemplo</span><span class="sxs-lookup"><span data-stu-id="67b7d-196">Example</span></span>

<span data-ttu-id="67b7d-197">As taxas de impostos são configuradas nos intervalos a seguir.</span><span class="sxs-lookup"><span data-stu-id="67b7d-197">The sales tax rates are set up in the following intervals.</span></span>

| <span data-ttu-id="67b7d-198">Valor</span><span class="sxs-lookup"><span data-stu-id="67b7d-198">Amount</span></span>             | <span data-ttu-id="67b7d-199">Taxa de imposto</span><span class="sxs-lookup"><span data-stu-id="67b7d-199">Tax rate</span></span> |
|--------------------|----------|
| <span data-ttu-id="67b7d-200">0 - 50</span><span class="sxs-lookup"><span data-stu-id="67b7d-200">0 - 50</span></span>             | <span data-ttu-id="67b7d-201">30%</span><span class="sxs-lookup"><span data-stu-id="67b7d-201">30%</span></span>      |
| <span data-ttu-id="67b7d-202">50 - 100</span><span class="sxs-lookup"><span data-stu-id="67b7d-202">50 - 100</span></span>           | <span data-ttu-id="67b7d-203">20%</span><span class="sxs-lookup"><span data-stu-id="67b7d-203">20%</span></span>      |
| <span data-ttu-id="67b7d-204">100 - 0 (&gt; 100)</span><span class="sxs-lookup"><span data-stu-id="67b7d-204">100 - 0 (&gt; 100)</span></span> | <span data-ttu-id="67b7d-205">10%</span><span class="sxs-lookup"><span data-stu-id="67b7d-205">10%</span></span>      |

<span data-ttu-id="67b7d-206">Base marginal: **Valor bruto por unidade** Há um imposto especial de 5,00 sobre cada luminária.</span><span class="sxs-lookup"><span data-stu-id="67b7d-206">Marginal base: **Gross amount per unit** There is a special duty of 5.00 on each lamp.</span></span> <span data-ttu-id="67b7d-207">O imposto é somado ao valor líquido antes do cálculo do imposto sobre vendas.</span><span class="sxs-lookup"><span data-stu-id="67b7d-207">The duty is added to the net amount before the sales tax calculation.</span></span> <span data-ttu-id="67b7d-208">Você compra oito luminárias que custam 25,00 cada.</span><span class="sxs-lookup"><span data-stu-id="67b7d-208">You buy 8 lamps that cost 25.00 each.</span></span> <span data-ttu-id="67b7d-209">O valor bruto por unidade é 30,00.</span><span class="sxs-lookup"><span data-stu-id="67b7d-209">The gross amount per unit is 30.00.</span></span> <span data-ttu-id="67b7d-210">O imposto é calculado da seguinte maneira: Imposto por unidade = 30 x 30% = 9,00 Total de impostos = 9,00 x 8 = 72,00 Total de impostos especiais = 5,00 x 8 = 40,00 Valor total da fatura = 200,00 + 72,00 + 40,00 = 312,00</span><span class="sxs-lookup"><span data-stu-id="67b7d-210">The tax is calculated as follows: Sales tax per unit = 30 x 30% = 9.00 Total sales tax = 9.00 x 8 = 72.00 Total duty = 5.00 x 8 = 40.00 Total invoice amount = 200.00 + 72.00 + 40.00 = 312.00</span></span>

## <a name="invoice-total-incl-other-sales-tax-amounts"></a><span data-ttu-id="67b7d-211">Total da fatura incluindo outros valores de imposto</span><span class="sxs-lookup"><span data-stu-id="67b7d-211">Invoice total incl. other sales tax amounts</span></span>

<span data-ttu-id="67b7d-212">Selecione essa opção para determinar as taxas de imposto no valor total da fatura, incluindo outros impostos.</span><span class="sxs-lookup"><span data-stu-id="67b7d-212">Select this option to determine sales tax rates based on the total value for the invoice including any other taxes.</span></span>
> [!NOTE]
> <span data-ttu-id="67b7d-213">Em um grupo de impostos, você só pode ter um código de imposto com essa seleção no campo Base marginal.</span><span class="sxs-lookup"><span data-stu-id="67b7d-213">In a sales tax group, you can only have one sales tax code with this selection in the Marginal base field</span></span>

### <a name="example"></a><span data-ttu-id="67b7d-214">Exemplo</span><span class="sxs-lookup"><span data-stu-id="67b7d-214">Example</span></span>

<span data-ttu-id="67b7d-215">As taxas de impostos são configuradas nos intervalos a seguir.</span><span class="sxs-lookup"><span data-stu-id="67b7d-215">The sales tax rates are set up in the following intervals.</span></span>

| <span data-ttu-id="67b7d-216">Valor</span><span class="sxs-lookup"><span data-stu-id="67b7d-216">Amount</span></span>             | <span data-ttu-id="67b7d-217">Taxa de imposto</span><span class="sxs-lookup"><span data-stu-id="67b7d-217">Tax rate</span></span> |
|--------------------|----------|
| <span data-ttu-id="67b7d-218">0 - 50</span><span class="sxs-lookup"><span data-stu-id="67b7d-218">0 - 50</span></span>             | <span data-ttu-id="67b7d-219">30%</span><span class="sxs-lookup"><span data-stu-id="67b7d-219">30%</span></span>      |
| <span data-ttu-id="67b7d-220">50 - 100</span><span class="sxs-lookup"><span data-stu-id="67b7d-220">50 - 100</span></span>           | <span data-ttu-id="67b7d-221">20%</span><span class="sxs-lookup"><span data-stu-id="67b7d-221">20%</span></span>      |
| <span data-ttu-id="67b7d-222">100 - 0 (&gt; 100)</span><span class="sxs-lookup"><span data-stu-id="67b7d-222">100 - 0 (&gt; 100)</span></span> | <span data-ttu-id="67b7d-223">10%</span><span class="sxs-lookup"><span data-stu-id="67b7d-223">10%</span></span>      |

<span data-ttu-id="67b7d-224">Base marginal: **Total de fatura incluindo outros valores de imposto** Método de cálculo: **Intervalo** </span><span class="sxs-lookup"><span data-stu-id="67b7d-224">Marginal base: **Invoice total incl. other sales tax amounts** Calculation method: **Interval** </span></span>  
<span data-ttu-id="67b7d-225">Há um imposto especial de 5,00 sobre cada luminária.</span><span class="sxs-lookup"><span data-stu-id="67b7d-225">There is a special duty of 5.00 on each lamp.</span></span> <span data-ttu-id="67b7d-226">O imposto é somado ao valor líquido antes do cálculo do imposto sobre vendas.</span><span class="sxs-lookup"><span data-stu-id="67b7d-226">The duty is added to the net amount before the sales tax calculation.</span></span> <span data-ttu-id="67b7d-227">Você compra oito luminárias que custam 25,00 cada.</span><span class="sxs-lookup"><span data-stu-id="67b7d-227">You buy 8 lamps that cost 25.00 each.</span></span> <span data-ttu-id="67b7d-228">O valor líquido da fatura é 200,00.</span><span class="sxs-lookup"><span data-stu-id="67b7d-228">The net amount for the invoice is 200.00.</span></span> <span data-ttu-id="67b7d-229">O valor bruto da fatura é 200,00 + (8 x 5,00) = 240,00.</span><span class="sxs-lookup"><span data-stu-id="67b7d-229">The gross amount for the invoice is 200.00 + (8 x 5.00) = 240.00.</span></span> <span data-ttu-id="67b7d-230">O imposto é calculado da seguinte maneira: Total de impostos = 50 x 0,30 + 50 x 0,20 + 140 x 0,10 = 15 + 10 + 14 = 39,00 Total de impostos especiais = 5,00 x 8 = 40,00 Valor total da fatura = 200,00 + 39,00 + 40,00 = 279,00</span><span class="sxs-lookup"><span data-stu-id="67b7d-230">The tax is calculated as follows: Total sales tax = 50 x 0.30 + 50 x 0.20 + 140 x 0.10 = 15 + 10 + 14 = 39.00 Total duty = 5.00 x 8 = 40.00 Total invoice amount = 200.00 + 39.00 + 40.00 = 279.00</span></span>

<span data-ttu-id="67b7d-231">Para obter mais informações, consulte [Opções de cálculo de intervalo e valor total para códigos de imposto](whole-amount-interval-options-sales-tax-codes.md) e [Métodos de cálculo de imposto no campo Origem](sales-tax-calculation-methods-origin-field.md).</span><span class="sxs-lookup"><span data-stu-id="67b7d-231">For more information, see [Whole amount and Interval calculation options for sales tax codes](whole-amount-interval-options-sales-tax-codes.md) and [Sales tax calculation methods in the Origin field](sales-tax-calculation-methods-origin-field.md).</span></span>




