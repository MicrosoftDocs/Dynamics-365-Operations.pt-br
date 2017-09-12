---
title: "Reavaliação de moeda em uma empresa de consolidação"
description: 
author: rschloma
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 62183
ms.assetid: 2762baaf-0c10-4ff7-8713-c506d6c29b98
ms.search.region: Global
ms.author: hminzner
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 08c38aada355583c5a6872f75b57db95d9b81786
ms.openlocfilehash: 643af8d771685fe8fd652b353d41f2679e0bef8b
ms.contentlocale: pt-br
ms.lasthandoff: 07/18/2017

---

# <a name="currency-revaluation-in-a-consolidation-company"></a><span data-ttu-id="f16fd-102">Reavaliação de moeda em uma empresa de consolidação</span><span class="sxs-lookup"><span data-stu-id="f16fd-102">Currency revaluation in a consolidation company</span></span>

[!include[banner](../includes/banner.md)]




<span data-ttu-id="f16fd-103">Após consolidar dados de uma moeda contábil para outra, você ainda deverá executar a reavaliação de moeda se houver uma alteração em taxas de câmbio, de forma que os saldos da conta sejam reavaliados corretamente.</span><span class="sxs-lookup"><span data-stu-id="f16fd-103">When you consolidate data from one accounting currency to another, you must still run currency revaluation if there is a change in exchange rates, so that your account balances  are correctly revalued.</span></span> <span data-ttu-id="f16fd-104">Ao consolidar originalmente os dados, use a guia **Conversão de moeda** para selecionar as taxas de câmbio iniciais para conversão durante o processo de consolidação.</span><span class="sxs-lookup"><span data-stu-id="f16fd-104">When you originally consolidate the data, use the **Currency translation** tab to select the initial exchange rates to for translation during the consolidation process.</span></span> <span data-ttu-id="f16fd-105">Após inserir uma nova taxa de câmbio (por exemplo, no mês seguinte), você deve reavaliar os saldos da conta.</span><span class="sxs-lookup"><span data-stu-id="f16fd-105">After a new exchange rate is entered (for example, in the next month), you must revalue the account balances.</span></span> <span data-ttu-id="f16fd-106">Os lucros não realizados ou as perdas são atualizados em conformidade, com base na nova taxa de câmbio e data.</span><span class="sxs-lookup"><span data-stu-id="f16fd-106">The unrealized gains or losses are then updated accordingly, based on the new exchange rate and date.</span></span> <span data-ttu-id="f16fd-107">O exemplo a seguir ilustra as entradas contábeis que são criadas durante o processo.</span><span class="sxs-lookup"><span data-stu-id="f16fd-107">The following example illustrates the accounting entries that are created during the process.</span></span>

## <a name="company-setup"></a><span data-ttu-id="f16fd-108">Configuração da empresa</span><span class="sxs-lookup"><span data-stu-id="f16fd-108">Company setup</span></span>
-   <span data-ttu-id="f16fd-109">**Empresa de origem/operacional (USMF)** – Os dólares norte-americanos (USD) são usados como a contabilidade e a moeda de relatório.</span><span class="sxs-lookup"><span data-stu-id="f16fd-109">**Source/operating company (USMF)** – US dollars (USD) are used as the accounting and reporting currency.</span></span>
-   <span data-ttu-id="f16fd-110">**Empresa consolidada (CON)** – Os euros (EUR) são usados como a contabilidade e a moeda de relatório.</span><span class="sxs-lookup"><span data-stu-id="f16fd-110">**Consolidated company (CON)** – Euros (EUR) are used as the accounting and reporting currency.</span></span>
    -   <span data-ttu-id="f16fd-111">**Lucro realizado** – conta contábil 801500</span><span class="sxs-lookup"><span data-stu-id="f16fd-111">**Realized gain **– Ledger account 801500</span></span>
    -   <span data-ttu-id="f16fd-112">**Perda realizada** – conta contábil 801600</span><span class="sxs-lookup"><span data-stu-id="f16fd-112">**Realized loss** – Ledger account 801600</span></span>
    -   <span data-ttu-id="f16fd-113">**Lucro não realizado** – conta contábil 801600</span><span class="sxs-lookup"><span data-stu-id="f16fd-113">**Unrealized gain** – Ledger account 801600</span></span>
    -   <span data-ttu-id="f16fd-114">**Perda não realizada** – conta contábil 801400</span><span class="sxs-lookup"><span data-stu-id="f16fd-114">**Unrealized loss** – Ledger account 801400</span></span>

## <a name="original-transactions"></a><span data-ttu-id="f16fd-115">Transações originais</span><span class="sxs-lookup"><span data-stu-id="f16fd-115">Original transactions</span></span>
### <a name="cash-receipt-transactions-in-usmf"></a><span data-ttu-id="f16fd-116">Transações de recebimento à vista em USMF</span><span class="sxs-lookup"><span data-stu-id="f16fd-116">Cash receipt transactions in USMF</span></span>

| <span data-ttu-id="f16fd-117">Data</span><span class="sxs-lookup"><span data-stu-id="f16fd-117">Date</span></span>       | <span data-ttu-id="f16fd-118">Conta contábil</span><span class="sxs-lookup"><span data-stu-id="f16fd-118">Ledger account</span></span>               | <span data-ttu-id="f16fd-119">Moeda</span><span class="sxs-lookup"><span data-stu-id="f16fd-119">Currency</span></span> | <span data-ttu-id="f16fd-120">Valor</span><span class="sxs-lookup"><span data-stu-id="f16fd-120">Amount</span></span> |
|------------|------------------------------|----------|--------|
| <span data-ttu-id="f16fd-121">11/10/2015</span><span class="sxs-lookup"><span data-stu-id="f16fd-121">10/11/2015</span></span> | <span data-ttu-id="f16fd-122">110110 – à vista</span><span class="sxs-lookup"><span data-stu-id="f16fd-122">110110 – Cash</span></span>                | <span data-ttu-id="f16fd-123">USD</span><span class="sxs-lookup"><span data-stu-id="f16fd-123">USD</span></span>      | <span data-ttu-id="f16fd-124">500</span><span class="sxs-lookup"><span data-stu-id="f16fd-124">500</span></span>    |
| <span data-ttu-id="f16fd-125">11/10/2015</span><span class="sxs-lookup"><span data-stu-id="f16fd-125">10/11/2015</span></span> | <span data-ttu-id="f16fd-126">130100 – Contas a Receber</span><span class="sxs-lookup"><span data-stu-id="f16fd-126">130100 – Accounts Receivable</span></span> | <span data-ttu-id="f16fd-127">USD</span><span class="sxs-lookup"><span data-stu-id="f16fd-127">USD</span></span>      | <span data-ttu-id="f16fd-128">-500</span><span class="sxs-lookup"><span data-stu-id="f16fd-128">-500</span></span>   |

## <a name="exchange-rates"></a><span data-ttu-id="f16fd-129">Taxas de câmbio</span><span class="sxs-lookup"><span data-stu-id="f16fd-129">Exchange rates</span></span>
| <span data-ttu-id="f16fd-130">Moeda inicial</span><span class="sxs-lookup"><span data-stu-id="f16fd-130">From currency</span></span> | <span data-ttu-id="f16fd-131">Moeda final</span><span class="sxs-lookup"><span data-stu-id="f16fd-131">To currency</span></span> | <span data-ttu-id="f16fd-132">Data inicial</span><span class="sxs-lookup"><span data-stu-id="f16fd-132">Start date</span></span> | <span data-ttu-id="f16fd-133">Taxa de câmbio</span><span class="sxs-lookup"><span data-stu-id="f16fd-133">Exchange rate</span></span> |
|---------------|-------------|------------|---------------|
| <span data-ttu-id="f16fd-134">EUR</span><span class="sxs-lookup"><span data-stu-id="f16fd-134">EUR</span></span>           | <span data-ttu-id="f16fd-135">USD</span><span class="sxs-lookup"><span data-stu-id="f16fd-135">USD</span></span>         | <span data-ttu-id="f16fd-136">1/10/2015</span><span class="sxs-lookup"><span data-stu-id="f16fd-136">10/1/2015</span></span>  | <span data-ttu-id="f16fd-137">200</span><span class="sxs-lookup"><span data-stu-id="f16fd-137">200</span></span>           |
| <span data-ttu-id="f16fd-138">EUR</span><span class="sxs-lookup"><span data-stu-id="f16fd-138">EUR</span></span>           | <span data-ttu-id="f16fd-139">USD</span><span class="sxs-lookup"><span data-stu-id="f16fd-139">USD</span></span>         | <span data-ttu-id="f16fd-140">1/11/2015</span><span class="sxs-lookup"><span data-stu-id="f16fd-140">11/1/2015</span></span>  | <span data-ttu-id="f16fd-141">150</span><span class="sxs-lookup"><span data-stu-id="f16fd-141">150</span></span>           |
| <span data-ttu-id="f16fd-142">EUR</span><span class="sxs-lookup"><span data-stu-id="f16fd-142">EUR</span></span>           | <span data-ttu-id="f16fd-143">USD</span><span class="sxs-lookup"><span data-stu-id="f16fd-143">USD</span></span>         | <span data-ttu-id="f16fd-144">1/12/2012</span><span class="sxs-lookup"><span data-stu-id="f16fd-144">12/1/2012</span></span>  | <span data-ttu-id="f16fd-145">100</span><span class="sxs-lookup"><span data-stu-id="f16fd-145">100</span></span>           |

## <a name="perform-the-consolidation-for-october-2015"></a><span data-ttu-id="f16fd-146">Execute a consolidação de outubro de 2015</span><span class="sxs-lookup"><span data-stu-id="f16fd-146">Perform the consolidation for October 2015</span></span>
### <a name="balances-in-the-consolidation-company"></a><span data-ttu-id="f16fd-147">Saldos na empresa de consolidação</span><span class="sxs-lookup"><span data-stu-id="f16fd-147">Balances in the consolidation company</span></span>

| <span data-ttu-id="f16fd-148">Conta contábil</span><span class="sxs-lookup"><span data-stu-id="f16fd-148">Ledger account</span></span> | <span data-ttu-id="f16fd-149">Moeda</span><span class="sxs-lookup"><span data-stu-id="f16fd-149">Currency</span></span> | <span data-ttu-id="f16fd-150">Valor</span><span class="sxs-lookup"><span data-stu-id="f16fd-150">Amount</span></span> | <span data-ttu-id="f16fd-151">Cálculo</span><span class="sxs-lookup"><span data-stu-id="f16fd-151">Calculation</span></span>    |
|----------------|----------|--------|----------------|
| <span data-ttu-id="f16fd-152">110110</span><span class="sxs-lookup"><span data-stu-id="f16fd-152">110110</span></span>         | <span data-ttu-id="f16fd-153">EUR</span><span class="sxs-lookup"><span data-stu-id="f16fd-153">EUR</span></span>      | <span data-ttu-id="f16fd-154">250</span><span class="sxs-lookup"><span data-stu-id="f16fd-154">250</span></span>    | <span data-ttu-id="f16fd-155">R$500 × 50%</span><span class="sxs-lookup"><span data-stu-id="f16fd-155">500 USD × 50%</span></span>  |
| <span data-ttu-id="f16fd-156">130100</span><span class="sxs-lookup"><span data-stu-id="f16fd-156">130100</span></span>         | <span data-ttu-id="f16fd-157">EUR</span><span class="sxs-lookup"><span data-stu-id="f16fd-157">EUR</span></span>      | <span data-ttu-id="f16fd-158">-250</span><span class="sxs-lookup"><span data-stu-id="f16fd-158">-250</span></span>   | <span data-ttu-id="f16fd-159">-R$500 × 50%</span><span class="sxs-lookup"><span data-stu-id="f16fd-159">-500 USD × 50%</span></span> |

## <a name="perform-currency-revaluation-for-the-accounts-from-october-1-2015-through-november-30-2015"></a><span data-ttu-id="f16fd-160">Execute a reavaliação de moeda para as contas desde 1º de outubro de 2015 até 30 de novembro de 2015</span><span class="sxs-lookup"><span data-stu-id="f16fd-160">Perform currency revaluation for the accounts from October 1, 2015, through November 30, 2015</span></span>
### <a name="balances-in-the-consolidation-company"></a><span data-ttu-id="f16fd-161">Saldos na empresa de consolidação</span><span class="sxs-lookup"><span data-stu-id="f16fd-161">Balances in the consolidation company</span></span>

| <span data-ttu-id="f16fd-162">Conta contábil</span><span class="sxs-lookup"><span data-stu-id="f16fd-162">Ledger account</span></span> | <span data-ttu-id="f16fd-163">Moeda</span><span class="sxs-lookup"><span data-stu-id="f16fd-163">Currency</span></span> | <span data-ttu-id="f16fd-164">Valor</span><span class="sxs-lookup"><span data-stu-id="f16fd-164">Amount</span></span>  | <span data-ttu-id="f16fd-165">Cálculo</span><span class="sxs-lookup"><span data-stu-id="f16fd-165">Calculation</span></span>                        |
|----------------|----------|---------|------------------------------------|
| <span data-ttu-id="f16fd-166">110110</span><span class="sxs-lookup"><span data-stu-id="f16fd-166">110110</span></span>         | <span data-ttu-id="f16fd-167">EUR</span><span class="sxs-lookup"><span data-stu-id="f16fd-167">EUR</span></span>      | <span data-ttu-id="f16fd-168">333.33</span><span class="sxs-lookup"><span data-stu-id="f16fd-168">333.33</span></span>  | <span data-ttu-id="f16fd-169">Valor original de 500 × 66,6667%</span><span class="sxs-lookup"><span data-stu-id="f16fd-169">Original amount of 500 × 66.6667%</span></span>  |
| <span data-ttu-id="f16fd-170">130100</span><span class="sxs-lookup"><span data-stu-id="f16fd-170">130100</span></span>         | <span data-ttu-id="f16fd-171">EUR</span><span class="sxs-lookup"><span data-stu-id="f16fd-171">EUR</span></span>      | <span data-ttu-id="f16fd-172">-333,33</span><span class="sxs-lookup"><span data-stu-id="f16fd-172">-333.33</span></span> | <span data-ttu-id="f16fd-173">Valor original de -500 × 66,6667%</span><span class="sxs-lookup"><span data-stu-id="f16fd-173">Original amount of -500 × 66.6667%</span></span> |
| <span data-ttu-id="f16fd-174">801400</span><span class="sxs-lookup"><span data-stu-id="f16fd-174">801400</span></span>         | <span data-ttu-id="f16fd-175">EUR</span><span class="sxs-lookup"><span data-stu-id="f16fd-175">EUR</span></span>      | <span data-ttu-id="f16fd-176">83,33</span><span class="sxs-lookup"><span data-stu-id="f16fd-176">83.33</span></span>   | <span data-ttu-id="f16fd-177">333,33 – 250</span><span class="sxs-lookup"><span data-stu-id="f16fd-177">333.33 – 250</span></span>                       |
| <span data-ttu-id="f16fd-178">801600</span><span class="sxs-lookup"><span data-stu-id="f16fd-178">801600</span></span>         | <span data-ttu-id="f16fd-179">EUR</span><span class="sxs-lookup"><span data-stu-id="f16fd-179">EUR</span></span>      | <span data-ttu-id="f16fd-180">-83,33</span><span class="sxs-lookup"><span data-stu-id="f16fd-180">-83.33</span></span>  | <span data-ttu-id="f16fd-181">-333,33 – (-250)</span><span class="sxs-lookup"><span data-stu-id="f16fd-181">-333.33 – (-250)</span></span>                   |

<span data-ttu-id="f16fd-182">Você verá transações adicionais para os valores de moeda de relatório.</span><span class="sxs-lookup"><span data-stu-id="f16fd-182">You will see additional transactions for the reporting currency amounts.</span></span>

## <a name="perform-currency-revaluation-for-the-accounts-from-october-1-2015-through-december-31-2015"></a><span data-ttu-id="f16fd-183">Execute a reavaliação de moeda para as contas desde 1º de outubro de 2015 até 31 de dezembro de 2015</span><span class="sxs-lookup"><span data-stu-id="f16fd-183">Perform currency revaluation for the accounts from October 1, 2015, through December 31, 2015</span></span>
### <a name="balances-in-the-consolidation-company"></a><span data-ttu-id="f16fd-184">Saldos na empresa de consolidação</span><span class="sxs-lookup"><span data-stu-id="f16fd-184">Balances in the consolidation company</span></span>

| <span data-ttu-id="f16fd-185">Conta contábil</span><span class="sxs-lookup"><span data-stu-id="f16fd-185">Ledger account</span></span> | <span data-ttu-id="f16fd-186">Moeda</span><span class="sxs-lookup"><span data-stu-id="f16fd-186">Currency</span></span> | <span data-ttu-id="f16fd-187">Valor</span><span class="sxs-lookup"><span data-stu-id="f16fd-187">Amount</span></span>  | <span data-ttu-id="f16fd-188">Cálculo</span><span class="sxs-lookup"><span data-stu-id="f16fd-188">Calculation</span></span>                                          |
|----------------|----------|---------|------------------------------------------------------|
| <span data-ttu-id="f16fd-189">110110</span><span class="sxs-lookup"><span data-stu-id="f16fd-189">110110</span></span>         | <span data-ttu-id="f16fd-190">EUR</span><span class="sxs-lookup"><span data-stu-id="f16fd-190">EUR</span></span>      | <span data-ttu-id="f16fd-191">500,00</span><span class="sxs-lookup"><span data-stu-id="f16fd-191">500.00</span></span>  | <span data-ttu-id="f16fd-192">Valor original de 500 × 1</span><span class="sxs-lookup"><span data-stu-id="f16fd-192">Original amount of 500 × 1</span></span>                           |
| <span data-ttu-id="f16fd-193">130100</span><span class="sxs-lookup"><span data-stu-id="f16fd-193">130100</span></span>         | <span data-ttu-id="f16fd-194">EUR</span><span class="sxs-lookup"><span data-stu-id="f16fd-194">EUR</span></span>      | <span data-ttu-id="f16fd-195">-500,00</span><span class="sxs-lookup"><span data-stu-id="f16fd-195">-500.00</span></span> | <span data-ttu-id="f16fd-196">Valor original de -500 × 1</span><span class="sxs-lookup"><span data-stu-id="f16fd-196">Original amount of -500 × 1</span></span>                          |
| <span data-ttu-id="f16fd-197">801400</span><span class="sxs-lookup"><span data-stu-id="f16fd-197">801400</span></span>         | <span data-ttu-id="f16fd-198">EUR</span><span class="sxs-lookup"><span data-stu-id="f16fd-198">EUR</span></span>      | <span data-ttu-id="f16fd-199">250</span><span class="sxs-lookup"><span data-stu-id="f16fd-199">250</span></span>     | <span data-ttu-id="f16fd-200">500 – 333,33 = 166,67 166,67 + 83,33 = 250</span><span class="sxs-lookup"><span data-stu-id="f16fd-200">500 – 333.33 = 166.67 166.67 + 83.33 = 250</span></span>           |
| <span data-ttu-id="f16fd-201">801600</span><span class="sxs-lookup"><span data-stu-id="f16fd-201">801600</span></span>         | <span data-ttu-id="f16fd-202">EUR</span><span class="sxs-lookup"><span data-stu-id="f16fd-202">EUR</span></span>      | <span data-ttu-id="f16fd-203">-250</span><span class="sxs-lookup"><span data-stu-id="f16fd-203">-250</span></span>    | <span data-ttu-id="f16fd-204">-500 – (-333,33) = -166,67 -166,67 + (-83,33) = -250</span><span class="sxs-lookup"><span data-stu-id="f16fd-204">-500 – (-333.33) = -166.67 -166.67 + (-83.33) = -250</span></span> |






