---
title: "Reavaliação de moeda em uma empresa de consolidação"
description: "Este tópico descreve como reavaliar a moeda em uma empresa de consolidação."
author: rschloma
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 62183
ms.assetid: 2762baaf-0c10-4ff7-8713-c506d6c29b98
ms.search.region: Global
ms.author: hminzner
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 27059b0d2a781453a7594bdc430005df6ea5c167
ms.contentlocale: pt-br
ms.lasthandoff: 11/03/2017

---

# <a name="currency-revaluation-in-a-consolidation-company"></a><span data-ttu-id="2e3c3-103">Reavaliação de moeda em uma empresa de consolidação</span><span class="sxs-lookup"><span data-stu-id="2e3c3-103">Currency revaluation in a consolidation company</span></span>

[!include[banner](../includes/banner.md)]




<span data-ttu-id="2e3c3-104">Após consolidar dados de uma moeda contábil para outra, você ainda deverá executar a reavaliação de moeda se houver uma alteração em taxas de câmbio, de forma que os saldos da conta sejam reavaliados corretamente.</span><span class="sxs-lookup"><span data-stu-id="2e3c3-104">When you consolidate data from one accounting currency to another, you must still run currency revaluation if there is a change in exchange rates, so that your account balances  are correctly revalued.</span></span> <span data-ttu-id="2e3c3-105">Ao consolidar originalmente os dados, use a guia **Conversão de moeda** para selecionar as taxas de câmbio iniciais para conversão durante o processo de consolidação.</span><span class="sxs-lookup"><span data-stu-id="2e3c3-105">When you originally consolidate the data, use the **Currency translation** tab to select the initial exchange rates to for translation during the consolidation process.</span></span> <span data-ttu-id="2e3c3-106">Após inserir uma nova taxa de câmbio (por exemplo, no mês seguinte), você deve reavaliar os saldos da conta.</span><span class="sxs-lookup"><span data-stu-id="2e3c3-106">After a new exchange rate is entered (for example, in the next month), you must revalue the account balances.</span></span> <span data-ttu-id="2e3c3-107">Os lucros não realizados ou as perdas são atualizados em conformidade, com base na nova taxa de câmbio e data.</span><span class="sxs-lookup"><span data-stu-id="2e3c3-107">The unrealized gains or losses are then updated accordingly, based on the new exchange rate and date.</span></span> <span data-ttu-id="2e3c3-108">O exemplo a seguir ilustra as entradas contábeis que são criadas durante o processo.</span><span class="sxs-lookup"><span data-stu-id="2e3c3-108">The following example illustrates the accounting entries that are created during the process.</span></span>

## <a name="company-setup"></a><span data-ttu-id="2e3c3-109">Configuração da empresa</span><span class="sxs-lookup"><span data-stu-id="2e3c3-109">Company setup</span></span>
-   <span data-ttu-id="2e3c3-110">**Empresa de origem/operacional (USMF)** – Os dólares norte-americanos (USD) são usados como a contabilidade e a moeda de relatório.</span><span class="sxs-lookup"><span data-stu-id="2e3c3-110">**Source/operating company (USMF)** – US dollars (USD) are used as the accounting and reporting currency.</span></span>
-   <span data-ttu-id="2e3c3-111">**Empresa consolidada (CON)** – Os euros (EUR) são usados como a contabilidade e a moeda de relatório.</span><span class="sxs-lookup"><span data-stu-id="2e3c3-111">**Consolidated company (CON)** – Euros (EUR) are used as the accounting and reporting currency.</span></span>
    -   <span data-ttu-id="2e3c3-112">**Lucro realizado** – conta contábil 801500</span><span class="sxs-lookup"><span data-stu-id="2e3c3-112">**Realized gain **– Ledger account 801500</span></span>
    -   <span data-ttu-id="2e3c3-113">**Perda realizada** – conta contábil 801600</span><span class="sxs-lookup"><span data-stu-id="2e3c3-113">**Realized loss** – Ledger account 801600</span></span>
    -   <span data-ttu-id="2e3c3-114">**Lucro não realizado** – conta contábil 801600</span><span class="sxs-lookup"><span data-stu-id="2e3c3-114">**Unrealized gain** – Ledger account 801600</span></span>
    -   <span data-ttu-id="2e3c3-115">**Perda não realizada** – conta contábil 801400</span><span class="sxs-lookup"><span data-stu-id="2e3c3-115">**Unrealized loss** – Ledger account 801400</span></span>

## <a name="original-transactions"></a><span data-ttu-id="2e3c3-116">Transações originais</span><span class="sxs-lookup"><span data-stu-id="2e3c3-116">Original transactions</span></span>
### <a name="cash-receipt-transactions-in-usmf"></a><span data-ttu-id="2e3c3-117">Transações de recebimento à vista em USMF</span><span class="sxs-lookup"><span data-stu-id="2e3c3-117">Cash receipt transactions in USMF</span></span>

| <span data-ttu-id="2e3c3-118">Data</span><span class="sxs-lookup"><span data-stu-id="2e3c3-118">Date</span></span>       | <span data-ttu-id="2e3c3-119">Conta contábil</span><span class="sxs-lookup"><span data-stu-id="2e3c3-119">Ledger account</span></span>               | <span data-ttu-id="2e3c3-120">Moeda</span><span class="sxs-lookup"><span data-stu-id="2e3c3-120">Currency</span></span> | <span data-ttu-id="2e3c3-121">Valor</span><span class="sxs-lookup"><span data-stu-id="2e3c3-121">Amount</span></span> |
|------------|------------------------------|----------|--------|
| <span data-ttu-id="2e3c3-122">11/10/2015</span><span class="sxs-lookup"><span data-stu-id="2e3c3-122">10/11/2015</span></span> | <span data-ttu-id="2e3c3-123">110110 – à vista</span><span class="sxs-lookup"><span data-stu-id="2e3c3-123">110110 – Cash</span></span>                | <span data-ttu-id="2e3c3-124">USD</span><span class="sxs-lookup"><span data-stu-id="2e3c3-124">USD</span></span>      | <span data-ttu-id="2e3c3-125">500</span><span class="sxs-lookup"><span data-stu-id="2e3c3-125">500</span></span>    |
| <span data-ttu-id="2e3c3-126">11/10/2015</span><span class="sxs-lookup"><span data-stu-id="2e3c3-126">10/11/2015</span></span> | <span data-ttu-id="2e3c3-127">130100 – Contas a Receber</span><span class="sxs-lookup"><span data-stu-id="2e3c3-127">130100 – Accounts Receivable</span></span> | <span data-ttu-id="2e3c3-128">USD</span><span class="sxs-lookup"><span data-stu-id="2e3c3-128">USD</span></span>      | <span data-ttu-id="2e3c3-129">-500</span><span class="sxs-lookup"><span data-stu-id="2e3c3-129">-500</span></span>   |

## <a name="exchange-rates"></a><span data-ttu-id="2e3c3-130">Taxas de câmbio</span><span class="sxs-lookup"><span data-stu-id="2e3c3-130">Exchange rates</span></span>
| <span data-ttu-id="2e3c3-131">Moeda inicial</span><span class="sxs-lookup"><span data-stu-id="2e3c3-131">From currency</span></span> | <span data-ttu-id="2e3c3-132">Moeda final</span><span class="sxs-lookup"><span data-stu-id="2e3c3-132">To currency</span></span> | <span data-ttu-id="2e3c3-133">Data inicial</span><span class="sxs-lookup"><span data-stu-id="2e3c3-133">Start date</span></span> | <span data-ttu-id="2e3c3-134">Taxa de câmbio</span><span class="sxs-lookup"><span data-stu-id="2e3c3-134">Exchange rate</span></span> |
|---------------|-------------|------------|---------------|
| <span data-ttu-id="2e3c3-135">EUR</span><span class="sxs-lookup"><span data-stu-id="2e3c3-135">EUR</span></span>           | <span data-ttu-id="2e3c3-136">USD</span><span class="sxs-lookup"><span data-stu-id="2e3c3-136">USD</span></span>         | <span data-ttu-id="2e3c3-137">1/10/2015</span><span class="sxs-lookup"><span data-stu-id="2e3c3-137">10/1/2015</span></span>  | <span data-ttu-id="2e3c3-138">200</span><span class="sxs-lookup"><span data-stu-id="2e3c3-138">200</span></span>           |
| <span data-ttu-id="2e3c3-139">EUR</span><span class="sxs-lookup"><span data-stu-id="2e3c3-139">EUR</span></span>           | <span data-ttu-id="2e3c3-140">USD</span><span class="sxs-lookup"><span data-stu-id="2e3c3-140">USD</span></span>         | <span data-ttu-id="2e3c3-141">1/11/2015</span><span class="sxs-lookup"><span data-stu-id="2e3c3-141">11/1/2015</span></span>  | <span data-ttu-id="2e3c3-142">150</span><span class="sxs-lookup"><span data-stu-id="2e3c3-142">150</span></span>           |
| <span data-ttu-id="2e3c3-143">EUR</span><span class="sxs-lookup"><span data-stu-id="2e3c3-143">EUR</span></span>           | <span data-ttu-id="2e3c3-144">USD</span><span class="sxs-lookup"><span data-stu-id="2e3c3-144">USD</span></span>         | <span data-ttu-id="2e3c3-145">1/12/2012</span><span class="sxs-lookup"><span data-stu-id="2e3c3-145">12/1/2012</span></span>  | <span data-ttu-id="2e3c3-146">100</span><span class="sxs-lookup"><span data-stu-id="2e3c3-146">100</span></span>           |

## <a name="perform-the-consolidation-for-october-2015"></a><span data-ttu-id="2e3c3-147">Execute a consolidação de outubro de 2015</span><span class="sxs-lookup"><span data-stu-id="2e3c3-147">Perform the consolidation for October 2015</span></span>
### <a name="balances-in-the-consolidation-company"></a><span data-ttu-id="2e3c3-148">Saldos na empresa de consolidação</span><span class="sxs-lookup"><span data-stu-id="2e3c3-148">Balances in the consolidation company</span></span>

| <span data-ttu-id="2e3c3-149">Conta contábil</span><span class="sxs-lookup"><span data-stu-id="2e3c3-149">Ledger account</span></span> | <span data-ttu-id="2e3c3-150">Moeda</span><span class="sxs-lookup"><span data-stu-id="2e3c3-150">Currency</span></span> | <span data-ttu-id="2e3c3-151">Valor</span><span class="sxs-lookup"><span data-stu-id="2e3c3-151">Amount</span></span> | <span data-ttu-id="2e3c3-152">Cálculo</span><span class="sxs-lookup"><span data-stu-id="2e3c3-152">Calculation</span></span>    |
|----------------|----------|--------|----------------|
| <span data-ttu-id="2e3c3-153">110110</span><span class="sxs-lookup"><span data-stu-id="2e3c3-153">110110</span></span>         | <span data-ttu-id="2e3c3-154">EUR</span><span class="sxs-lookup"><span data-stu-id="2e3c3-154">EUR</span></span>      | <span data-ttu-id="2e3c3-155">250</span><span class="sxs-lookup"><span data-stu-id="2e3c3-155">250</span></span>    | <span data-ttu-id="2e3c3-156">R$500 × 50%</span><span class="sxs-lookup"><span data-stu-id="2e3c3-156">500 USD × 50%</span></span>  |
| <span data-ttu-id="2e3c3-157">130100</span><span class="sxs-lookup"><span data-stu-id="2e3c3-157">130100</span></span>         | <span data-ttu-id="2e3c3-158">EUR</span><span class="sxs-lookup"><span data-stu-id="2e3c3-158">EUR</span></span>      | <span data-ttu-id="2e3c3-159">-250</span><span class="sxs-lookup"><span data-stu-id="2e3c3-159">-250</span></span>   | <span data-ttu-id="2e3c3-160">-R$500 × 50%</span><span class="sxs-lookup"><span data-stu-id="2e3c3-160">-500 USD × 50%</span></span> |

## <a name="perform-currency-revaluation-for-the-accounts-from-october-1-2015-through-november-30-2015"></a><span data-ttu-id="2e3c3-161">Execute a reavaliação de moeda para as contas desde 1º de outubro de 2015 até 30 de novembro de 2015</span><span class="sxs-lookup"><span data-stu-id="2e3c3-161">Perform currency revaluation for the accounts from October 1, 2015, through November 30, 2015</span></span>
### <a name="balances-in-the-consolidation-company"></a><span data-ttu-id="2e3c3-162">Saldos na empresa de consolidação</span><span class="sxs-lookup"><span data-stu-id="2e3c3-162">Balances in the consolidation company</span></span>

| <span data-ttu-id="2e3c3-163">Conta contábil</span><span class="sxs-lookup"><span data-stu-id="2e3c3-163">Ledger account</span></span> | <span data-ttu-id="2e3c3-164">Moeda</span><span class="sxs-lookup"><span data-stu-id="2e3c3-164">Currency</span></span> | <span data-ttu-id="2e3c3-165">Valor</span><span class="sxs-lookup"><span data-stu-id="2e3c3-165">Amount</span></span>  | <span data-ttu-id="2e3c3-166">Cálculo</span><span class="sxs-lookup"><span data-stu-id="2e3c3-166">Calculation</span></span>                        |
|----------------|----------|---------|------------------------------------|
| <span data-ttu-id="2e3c3-167">110110</span><span class="sxs-lookup"><span data-stu-id="2e3c3-167">110110</span></span>         | <span data-ttu-id="2e3c3-168">EUR</span><span class="sxs-lookup"><span data-stu-id="2e3c3-168">EUR</span></span>      | <span data-ttu-id="2e3c3-169">333.33</span><span class="sxs-lookup"><span data-stu-id="2e3c3-169">333.33</span></span>  | <span data-ttu-id="2e3c3-170">Valor original de 500 × 66,6667%</span><span class="sxs-lookup"><span data-stu-id="2e3c3-170">Original amount of 500 × 66.6667%</span></span>  |
| <span data-ttu-id="2e3c3-171">130100</span><span class="sxs-lookup"><span data-stu-id="2e3c3-171">130100</span></span>         | <span data-ttu-id="2e3c3-172">EUR</span><span class="sxs-lookup"><span data-stu-id="2e3c3-172">EUR</span></span>      | <span data-ttu-id="2e3c3-173">-333,33</span><span class="sxs-lookup"><span data-stu-id="2e3c3-173">-333.33</span></span> | <span data-ttu-id="2e3c3-174">Valor original de -500 × 66,6667%</span><span class="sxs-lookup"><span data-stu-id="2e3c3-174">Original amount of -500 × 66.6667%</span></span> |
| <span data-ttu-id="2e3c3-175">801400</span><span class="sxs-lookup"><span data-stu-id="2e3c3-175">801400</span></span>         | <span data-ttu-id="2e3c3-176">EUR</span><span class="sxs-lookup"><span data-stu-id="2e3c3-176">EUR</span></span>      | <span data-ttu-id="2e3c3-177">83,33</span><span class="sxs-lookup"><span data-stu-id="2e3c3-177">83.33</span></span>   | <span data-ttu-id="2e3c3-178">333,33 – 250</span><span class="sxs-lookup"><span data-stu-id="2e3c3-178">333.33 – 250</span></span>                       |
| <span data-ttu-id="2e3c3-179">801600</span><span class="sxs-lookup"><span data-stu-id="2e3c3-179">801600</span></span>         | <span data-ttu-id="2e3c3-180">EUR</span><span class="sxs-lookup"><span data-stu-id="2e3c3-180">EUR</span></span>      | <span data-ttu-id="2e3c3-181">-83,33</span><span class="sxs-lookup"><span data-stu-id="2e3c3-181">-83.33</span></span>  | <span data-ttu-id="2e3c3-182">-333,33 – (-250)</span><span class="sxs-lookup"><span data-stu-id="2e3c3-182">-333.33 – (-250)</span></span>                   |

<span data-ttu-id="2e3c3-183">Você verá transações adicionais para os valores de moeda de relatório.</span><span class="sxs-lookup"><span data-stu-id="2e3c3-183">You will see additional transactions for the reporting currency amounts.</span></span>

## <a name="perform-currency-revaluation-for-the-accounts-from-october-1-2015-through-december-31-2015"></a><span data-ttu-id="2e3c3-184">Execute a reavaliação de moeda para as contas desde 1º de outubro de 2015 até 31 de dezembro de 2015</span><span class="sxs-lookup"><span data-stu-id="2e3c3-184">Perform currency revaluation for the accounts from October 1, 2015, through December 31, 2015</span></span>
### <a name="balances-in-the-consolidation-company"></a><span data-ttu-id="2e3c3-185">Saldos na empresa de consolidação</span><span class="sxs-lookup"><span data-stu-id="2e3c3-185">Balances in the consolidation company</span></span>

| <span data-ttu-id="2e3c3-186">Conta contábil</span><span class="sxs-lookup"><span data-stu-id="2e3c3-186">Ledger account</span></span> | <span data-ttu-id="2e3c3-187">Moeda</span><span class="sxs-lookup"><span data-stu-id="2e3c3-187">Currency</span></span> | <span data-ttu-id="2e3c3-188">Valor</span><span class="sxs-lookup"><span data-stu-id="2e3c3-188">Amount</span></span>  | <span data-ttu-id="2e3c3-189">Cálculo</span><span class="sxs-lookup"><span data-stu-id="2e3c3-189">Calculation</span></span>                                          |
|----------------|----------|---------|------------------------------------------------------|
| <span data-ttu-id="2e3c3-190">110110</span><span class="sxs-lookup"><span data-stu-id="2e3c3-190">110110</span></span>         | <span data-ttu-id="2e3c3-191">EUR</span><span class="sxs-lookup"><span data-stu-id="2e3c3-191">EUR</span></span>      | <span data-ttu-id="2e3c3-192">500,00</span><span class="sxs-lookup"><span data-stu-id="2e3c3-192">500.00</span></span>  | <span data-ttu-id="2e3c3-193">Valor original de 500 × 1</span><span class="sxs-lookup"><span data-stu-id="2e3c3-193">Original amount of 500 × 1</span></span>                           |
| <span data-ttu-id="2e3c3-194">130100</span><span class="sxs-lookup"><span data-stu-id="2e3c3-194">130100</span></span>         | <span data-ttu-id="2e3c3-195">EUR</span><span class="sxs-lookup"><span data-stu-id="2e3c3-195">EUR</span></span>      | <span data-ttu-id="2e3c3-196">-500,00</span><span class="sxs-lookup"><span data-stu-id="2e3c3-196">-500.00</span></span> | <span data-ttu-id="2e3c3-197">Valor original de -500 × 1</span><span class="sxs-lookup"><span data-stu-id="2e3c3-197">Original amount of -500 × 1</span></span>                          |
| <span data-ttu-id="2e3c3-198">801400</span><span class="sxs-lookup"><span data-stu-id="2e3c3-198">801400</span></span>         | <span data-ttu-id="2e3c3-199">EUR</span><span class="sxs-lookup"><span data-stu-id="2e3c3-199">EUR</span></span>      | <span data-ttu-id="2e3c3-200">250</span><span class="sxs-lookup"><span data-stu-id="2e3c3-200">250</span></span>     | <span data-ttu-id="2e3c3-201">500 – 333,33 = 166,67 166,67 + 83,33 = 250</span><span class="sxs-lookup"><span data-stu-id="2e3c3-201">500 – 333.33 = 166.67 166.67 + 83.33 = 250</span></span>           |
| <span data-ttu-id="2e3c3-202">801600</span><span class="sxs-lookup"><span data-stu-id="2e3c3-202">801600</span></span>         | <span data-ttu-id="2e3c3-203">EUR</span><span class="sxs-lookup"><span data-stu-id="2e3c3-203">EUR</span></span>      | <span data-ttu-id="2e3c3-204">-250</span><span class="sxs-lookup"><span data-stu-id="2e3c3-204">-250</span></span>    | <span data-ttu-id="2e3c3-205">-500 – (-333,33) = -166,67 -166,67 + (-83,33) = -250</span><span class="sxs-lookup"><span data-stu-id="2e3c3-205">-500 – (-333.33) = -166.67 -166.67 + (-83.33) = -250</span></span> |






