---
title: "Reavaliação de moeda em uma empresa de consolidação"
description: "Este tópico descreve como reavaliar a moeda em uma empresa de consolidação."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: LedgerExchAdjHist
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
ms.sourcegitcommit: 029511634e56aec7fdd91bad9441cd12951fbd8d
ms.openlocfilehash: 06490f14ed01c3061b20a0e6977746e9fd2a6ffa
ms.contentlocale: pt-br
ms.lasthandoff: 01/17/2018

---

# <a name="currency-revaluation-in-a-consolidation-company"></a><span data-ttu-id="49e13-103">Reavaliação de moeda em uma empresa de consolidação</span><span class="sxs-lookup"><span data-stu-id="49e13-103">Currency revaluation in a consolidation company</span></span>

[!include[banner](../includes/banner.md)]




<span data-ttu-id="49e13-104">Após consolidar dados de uma moeda contábil para outra, você ainda deverá executar a reavaliação de moeda se houver uma alteração em taxas de câmbio, de forma que os saldos da conta sejam reavaliados corretamente.</span><span class="sxs-lookup"><span data-stu-id="49e13-104">When you consolidate data from one accounting currency to another, you must still run currency revaluation if there is a change in exchange rates, so that your account balances  are correctly revalued.</span></span> <span data-ttu-id="49e13-105">Ao consolidar originalmente os dados, use a guia **Conversão de moeda** para selecionar as taxas de câmbio iniciais para conversão durante o processo de consolidação.</span><span class="sxs-lookup"><span data-stu-id="49e13-105">When you originally consolidate the data, use the **Currency translation** tab to select the initial exchange rates to for translation during the consolidation process.</span></span> <span data-ttu-id="49e13-106">Após inserir uma nova taxa de câmbio (por exemplo, no mês seguinte), você deve reavaliar os saldos da conta.</span><span class="sxs-lookup"><span data-stu-id="49e13-106">After a new exchange rate is entered (for example, in the next month), you must revalue the account balances.</span></span> <span data-ttu-id="49e13-107">Os lucros não realizados ou as perdas são atualizados em conformidade, com base na nova taxa de câmbio e data.</span><span class="sxs-lookup"><span data-stu-id="49e13-107">The unrealized gains or losses are then updated accordingly, based on the new exchange rate and date.</span></span> <span data-ttu-id="49e13-108">O exemplo a seguir ilustra as entradas contábeis que são criadas durante o processo.</span><span class="sxs-lookup"><span data-stu-id="49e13-108">The following example illustrates the accounting entries that are created during the process.</span></span>

## <a name="company-setup"></a><span data-ttu-id="49e13-109">Configuração da empresa</span><span class="sxs-lookup"><span data-stu-id="49e13-109">Company setup</span></span>
-   <span data-ttu-id="49e13-110">**Empresa de origem/operacional (USMF)** – Os dólares norte-americanos (USD) são usados como a contabilidade e a moeda de relatório.</span><span class="sxs-lookup"><span data-stu-id="49e13-110">**Source/operating company (USMF)** – US dollars (USD) are used as the accounting and reporting currency.</span></span>
-   <span data-ttu-id="49e13-111">**Empresa consolidada (CON)** – Os euros (EUR) são usados como a contabilidade e a moeda de relatório.</span><span class="sxs-lookup"><span data-stu-id="49e13-111">**Consolidated company (CON)** – Euros (EUR) are used as the accounting and reporting currency.</span></span>
    -   <span data-ttu-id="49e13-112">**Lucro realizado** – conta contábil 801500</span><span class="sxs-lookup"><span data-stu-id="49e13-112">**Realized gain **– Ledger account 801500</span></span>
    -   <span data-ttu-id="49e13-113">**Perda realizada** – conta contábil 801600</span><span class="sxs-lookup"><span data-stu-id="49e13-113">**Realized loss** – Ledger account 801600</span></span>
    -   <span data-ttu-id="49e13-114">**Lucro não realizado** – conta contábil 801600</span><span class="sxs-lookup"><span data-stu-id="49e13-114">**Unrealized gain** – Ledger account 801600</span></span>
    -   <span data-ttu-id="49e13-115">**Perda não realizada** – conta contábil 801400</span><span class="sxs-lookup"><span data-stu-id="49e13-115">**Unrealized loss** – Ledger account 801400</span></span>

## <a name="original-transactions"></a><span data-ttu-id="49e13-116">Transações originais</span><span class="sxs-lookup"><span data-stu-id="49e13-116">Original transactions</span></span>
### <a name="cash-receipt-transactions-in-usmf"></a><span data-ttu-id="49e13-117">Transações de recebimento à vista em USMF</span><span class="sxs-lookup"><span data-stu-id="49e13-117">Cash receipt transactions in USMF</span></span>

| <span data-ttu-id="49e13-118">Data</span><span class="sxs-lookup"><span data-stu-id="49e13-118">Date</span></span>       | <span data-ttu-id="49e13-119">Conta contábil</span><span class="sxs-lookup"><span data-stu-id="49e13-119">Ledger account</span></span>               | <span data-ttu-id="49e13-120">Moeda</span><span class="sxs-lookup"><span data-stu-id="49e13-120">Currency</span></span> | <span data-ttu-id="49e13-121">Valor</span><span class="sxs-lookup"><span data-stu-id="49e13-121">Amount</span></span> |
|------------|------------------------------|----------|--------|
| <span data-ttu-id="49e13-122">11/10/2015</span><span class="sxs-lookup"><span data-stu-id="49e13-122">10/11/2015</span></span> | <span data-ttu-id="49e13-123">110110 – à vista</span><span class="sxs-lookup"><span data-stu-id="49e13-123">110110 – Cash</span></span>                | <span data-ttu-id="49e13-124">USD</span><span class="sxs-lookup"><span data-stu-id="49e13-124">USD</span></span>      | <span data-ttu-id="49e13-125">500</span><span class="sxs-lookup"><span data-stu-id="49e13-125">500</span></span>    |
| <span data-ttu-id="49e13-126">11/10/2015</span><span class="sxs-lookup"><span data-stu-id="49e13-126">10/11/2015</span></span> | <span data-ttu-id="49e13-127">130100 – Contas a Receber</span><span class="sxs-lookup"><span data-stu-id="49e13-127">130100 – Accounts Receivable</span></span> | <span data-ttu-id="49e13-128">USD</span><span class="sxs-lookup"><span data-stu-id="49e13-128">USD</span></span>      | <span data-ttu-id="49e13-129">-500</span><span class="sxs-lookup"><span data-stu-id="49e13-129">-500</span></span>   |

## <a name="exchange-rates"></a><span data-ttu-id="49e13-130">Taxas de câmbio</span><span class="sxs-lookup"><span data-stu-id="49e13-130">Exchange rates</span></span>
| <span data-ttu-id="49e13-131">Moeda inicial</span><span class="sxs-lookup"><span data-stu-id="49e13-131">From currency</span></span> | <span data-ttu-id="49e13-132">Moeda final</span><span class="sxs-lookup"><span data-stu-id="49e13-132">To currency</span></span> | <span data-ttu-id="49e13-133">Data inicial</span><span class="sxs-lookup"><span data-stu-id="49e13-133">Start date</span></span> | <span data-ttu-id="49e13-134">Taxa de câmbio</span><span class="sxs-lookup"><span data-stu-id="49e13-134">Exchange rate</span></span> |
|---------------|-------------|------------|---------------|
| <span data-ttu-id="49e13-135">EUR</span><span class="sxs-lookup"><span data-stu-id="49e13-135">EUR</span></span>           | <span data-ttu-id="49e13-136">USD</span><span class="sxs-lookup"><span data-stu-id="49e13-136">USD</span></span>         | <span data-ttu-id="49e13-137">1/10/2015</span><span class="sxs-lookup"><span data-stu-id="49e13-137">10/1/2015</span></span>  | <span data-ttu-id="49e13-138">200</span><span class="sxs-lookup"><span data-stu-id="49e13-138">200</span></span>           |
| <span data-ttu-id="49e13-139">EUR</span><span class="sxs-lookup"><span data-stu-id="49e13-139">EUR</span></span>           | <span data-ttu-id="49e13-140">USD</span><span class="sxs-lookup"><span data-stu-id="49e13-140">USD</span></span>         | <span data-ttu-id="49e13-141">1/11/2015</span><span class="sxs-lookup"><span data-stu-id="49e13-141">11/1/2015</span></span>  | <span data-ttu-id="49e13-142">150</span><span class="sxs-lookup"><span data-stu-id="49e13-142">150</span></span>           |
| <span data-ttu-id="49e13-143">EUR</span><span class="sxs-lookup"><span data-stu-id="49e13-143">EUR</span></span>           | <span data-ttu-id="49e13-144">USD</span><span class="sxs-lookup"><span data-stu-id="49e13-144">USD</span></span>         | <span data-ttu-id="49e13-145">1/12/2012</span><span class="sxs-lookup"><span data-stu-id="49e13-145">12/1/2012</span></span>  | <span data-ttu-id="49e13-146">100</span><span class="sxs-lookup"><span data-stu-id="49e13-146">100</span></span>           |

## <a name="perform-the-consolidation-for-october-2015"></a><span data-ttu-id="49e13-147">Execute a consolidação de outubro de 2015</span><span class="sxs-lookup"><span data-stu-id="49e13-147">Perform the consolidation for October 2015</span></span>
### <a name="balances-in-the-consolidation-company"></a><span data-ttu-id="49e13-148">Saldos na empresa de consolidação</span><span class="sxs-lookup"><span data-stu-id="49e13-148">Balances in the consolidation company</span></span>

| <span data-ttu-id="49e13-149">Conta contábil</span><span class="sxs-lookup"><span data-stu-id="49e13-149">Ledger account</span></span> | <span data-ttu-id="49e13-150">Moeda</span><span class="sxs-lookup"><span data-stu-id="49e13-150">Currency</span></span> | <span data-ttu-id="49e13-151">Valor</span><span class="sxs-lookup"><span data-stu-id="49e13-151">Amount</span></span> | <span data-ttu-id="49e13-152">Cálculo</span><span class="sxs-lookup"><span data-stu-id="49e13-152">Calculation</span></span>    |
|----------------|----------|--------|----------------|
| <span data-ttu-id="49e13-153">110110</span><span class="sxs-lookup"><span data-stu-id="49e13-153">110110</span></span>         | <span data-ttu-id="49e13-154">EUR</span><span class="sxs-lookup"><span data-stu-id="49e13-154">EUR</span></span>      | <span data-ttu-id="49e13-155">250</span><span class="sxs-lookup"><span data-stu-id="49e13-155">250</span></span>    | <span data-ttu-id="49e13-156">R$500 × 50%</span><span class="sxs-lookup"><span data-stu-id="49e13-156">500 USD × 50%</span></span>  |
| <span data-ttu-id="49e13-157">130100</span><span class="sxs-lookup"><span data-stu-id="49e13-157">130100</span></span>         | <span data-ttu-id="49e13-158">EUR</span><span class="sxs-lookup"><span data-stu-id="49e13-158">EUR</span></span>      | <span data-ttu-id="49e13-159">-250</span><span class="sxs-lookup"><span data-stu-id="49e13-159">-250</span></span>   | <span data-ttu-id="49e13-160">-R$500 × 50%</span><span class="sxs-lookup"><span data-stu-id="49e13-160">-500 USD × 50%</span></span> |

## <a name="perform-currency-revaluation-for-the-accounts-from-october-1-2015-through-november-30-2015"></a><span data-ttu-id="49e13-161">Execute a reavaliação de moeda para as contas desde 1º de outubro de 2015 até 30 de novembro de 2015</span><span class="sxs-lookup"><span data-stu-id="49e13-161">Perform currency revaluation for the accounts from October 1, 2015, through November 30, 2015</span></span>
### <a name="balances-in-the-consolidation-company"></a><span data-ttu-id="49e13-162">Saldos na empresa de consolidação</span><span class="sxs-lookup"><span data-stu-id="49e13-162">Balances in the consolidation company</span></span>

| <span data-ttu-id="49e13-163">Conta contábil</span><span class="sxs-lookup"><span data-stu-id="49e13-163">Ledger account</span></span> | <span data-ttu-id="49e13-164">Moeda</span><span class="sxs-lookup"><span data-stu-id="49e13-164">Currency</span></span> | <span data-ttu-id="49e13-165">Valor</span><span class="sxs-lookup"><span data-stu-id="49e13-165">Amount</span></span>  | <span data-ttu-id="49e13-166">Cálculo</span><span class="sxs-lookup"><span data-stu-id="49e13-166">Calculation</span></span>                        |
|----------------|----------|---------|------------------------------------|
| <span data-ttu-id="49e13-167">110110</span><span class="sxs-lookup"><span data-stu-id="49e13-167">110110</span></span>         | <span data-ttu-id="49e13-168">EUR</span><span class="sxs-lookup"><span data-stu-id="49e13-168">EUR</span></span>      | <span data-ttu-id="49e13-169">333.33</span><span class="sxs-lookup"><span data-stu-id="49e13-169">333.33</span></span>  | <span data-ttu-id="49e13-170">Valor original de 500 × 66,6667%</span><span class="sxs-lookup"><span data-stu-id="49e13-170">Original amount of 500 × 66.6667%</span></span>  |
| <span data-ttu-id="49e13-171">130100</span><span class="sxs-lookup"><span data-stu-id="49e13-171">130100</span></span>         | <span data-ttu-id="49e13-172">EUR</span><span class="sxs-lookup"><span data-stu-id="49e13-172">EUR</span></span>      | <span data-ttu-id="49e13-173">-333,33</span><span class="sxs-lookup"><span data-stu-id="49e13-173">-333.33</span></span> | <span data-ttu-id="49e13-174">Valor original de -500 × 66,6667%</span><span class="sxs-lookup"><span data-stu-id="49e13-174">Original amount of -500 × 66.6667%</span></span> |
| <span data-ttu-id="49e13-175">801400</span><span class="sxs-lookup"><span data-stu-id="49e13-175">801400</span></span>         | <span data-ttu-id="49e13-176">EUR</span><span class="sxs-lookup"><span data-stu-id="49e13-176">EUR</span></span>      | <span data-ttu-id="49e13-177">83,33</span><span class="sxs-lookup"><span data-stu-id="49e13-177">83.33</span></span>   | <span data-ttu-id="49e13-178">333,33 – 250</span><span class="sxs-lookup"><span data-stu-id="49e13-178">333.33 – 250</span></span>                       |
| <span data-ttu-id="49e13-179">801600</span><span class="sxs-lookup"><span data-stu-id="49e13-179">801600</span></span>         | <span data-ttu-id="49e13-180">EUR</span><span class="sxs-lookup"><span data-stu-id="49e13-180">EUR</span></span>      | <span data-ttu-id="49e13-181">-83,33</span><span class="sxs-lookup"><span data-stu-id="49e13-181">-83.33</span></span>  | <span data-ttu-id="49e13-182">-333,33 – (-250)</span><span class="sxs-lookup"><span data-stu-id="49e13-182">-333.33 – (-250)</span></span>                   |

<span data-ttu-id="49e13-183">Você verá transações adicionais para os valores de moeda de relatório.</span><span class="sxs-lookup"><span data-stu-id="49e13-183">You will see additional transactions for the reporting currency amounts.</span></span>

## <a name="perform-currency-revaluation-for-the-accounts-from-october-1-2015-through-december-31-2015"></a><span data-ttu-id="49e13-184">Execute a reavaliação de moeda para as contas desde 1º de outubro de 2015 até 31 de dezembro de 2015</span><span class="sxs-lookup"><span data-stu-id="49e13-184">Perform currency revaluation for the accounts from October 1, 2015, through December 31, 2015</span></span>
### <a name="balances-in-the-consolidation-company"></a><span data-ttu-id="49e13-185">Saldos na empresa de consolidação</span><span class="sxs-lookup"><span data-stu-id="49e13-185">Balances in the consolidation company</span></span>

| <span data-ttu-id="49e13-186">Conta contábil</span><span class="sxs-lookup"><span data-stu-id="49e13-186">Ledger account</span></span> | <span data-ttu-id="49e13-187">Moeda</span><span class="sxs-lookup"><span data-stu-id="49e13-187">Currency</span></span> | <span data-ttu-id="49e13-188">Valor</span><span class="sxs-lookup"><span data-stu-id="49e13-188">Amount</span></span>  | <span data-ttu-id="49e13-189">Cálculo</span><span class="sxs-lookup"><span data-stu-id="49e13-189">Calculation</span></span>                                          |
|----------------|----------|---------|------------------------------------------------------|
| <span data-ttu-id="49e13-190">110110</span><span class="sxs-lookup"><span data-stu-id="49e13-190">110110</span></span>         | <span data-ttu-id="49e13-191">EUR</span><span class="sxs-lookup"><span data-stu-id="49e13-191">EUR</span></span>      | <span data-ttu-id="49e13-192">500,00</span><span class="sxs-lookup"><span data-stu-id="49e13-192">500.00</span></span>  | <span data-ttu-id="49e13-193">Valor original de 500 × 1</span><span class="sxs-lookup"><span data-stu-id="49e13-193">Original amount of 500 × 1</span></span>                           |
| <span data-ttu-id="49e13-194">130100</span><span class="sxs-lookup"><span data-stu-id="49e13-194">130100</span></span>         | <span data-ttu-id="49e13-195">EUR</span><span class="sxs-lookup"><span data-stu-id="49e13-195">EUR</span></span>      | <span data-ttu-id="49e13-196">-500,00</span><span class="sxs-lookup"><span data-stu-id="49e13-196">-500.00</span></span> | <span data-ttu-id="49e13-197">Valor original de -500 × 1</span><span class="sxs-lookup"><span data-stu-id="49e13-197">Original amount of -500 × 1</span></span>                          |
| <span data-ttu-id="49e13-198">801400</span><span class="sxs-lookup"><span data-stu-id="49e13-198">801400</span></span>         | <span data-ttu-id="49e13-199">EUR</span><span class="sxs-lookup"><span data-stu-id="49e13-199">EUR</span></span>      | <span data-ttu-id="49e13-200">250</span><span class="sxs-lookup"><span data-stu-id="49e13-200">250</span></span>     | <span data-ttu-id="49e13-201">500 – 333,33 = 166,67 166,67 + 83,33 = 250</span><span class="sxs-lookup"><span data-stu-id="49e13-201">500 – 333.33 = 166.67 166.67 + 83.33 = 250</span></span>           |
| <span data-ttu-id="49e13-202">801600</span><span class="sxs-lookup"><span data-stu-id="49e13-202">801600</span></span>         | <span data-ttu-id="49e13-203">EUR</span><span class="sxs-lookup"><span data-stu-id="49e13-203">EUR</span></span>      | <span data-ttu-id="49e13-204">-250</span><span class="sxs-lookup"><span data-stu-id="49e13-204">-250</span></span>    | <span data-ttu-id="49e13-205">-500 – (-333,33) = -166,67 -166,67 + (-83,33) = -250</span><span class="sxs-lookup"><span data-stu-id="49e13-205">-500 – (-333.33) = -166.67 -166.67 + (-83.33) = -250</span></span> |






