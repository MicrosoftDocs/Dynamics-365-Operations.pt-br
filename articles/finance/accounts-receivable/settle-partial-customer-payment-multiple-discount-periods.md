---
title: Liquidar um pagamento parcial de cliente com vários períodos de desconto
description: Este artigo mostra como os pagamentos parciais de cliente são liquidados quando há vários períodos de desconto.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/22/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustOpenTrans, LedgerJournalTransCustPaym
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 14471
ms.assetid: b633a7c4-c18d-42e7-91cc-adcdc8a3ba98
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 6f4d5178aeb3294fd3b40815bb294a7f2ff08b71
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2188915"
---
# <a name="settle-a-partial-customer-payment-that-has-multiple-discount-periods"></a><span data-ttu-id="6b800-103">Liquidar um pagamento parcial de cliente com vários períodos de desconto</span><span class="sxs-lookup"><span data-stu-id="6b800-103">Settle a partial customer payment that has multiple discount periods</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="6b800-104">Este artigo mostra como os pagamentos parciais de cliente são liquidados quando há vários períodos de desconto.</span><span class="sxs-lookup"><span data-stu-id="6b800-104">This article shows how partial customer payments are settled when there are multiple discount periods.</span></span>

<span data-ttu-id="6b800-105">A Fabrikam oferece ao cliente 4031 dois períodos de desconto para pagamento à vista.</span><span class="sxs-lookup"><span data-stu-id="6b800-105">Fabrikam offers customer 4031 two cash discount periods.</span></span> <span data-ttu-id="6b800-106">O cliente receberá um desconto à vista de 2% se a fatura for paga em cinco dias, e um desconto à vista de 1% se a fatura for paga em 14 dias.</span><span class="sxs-lookup"><span data-stu-id="6b800-106">The customer receives a 2-percent cash discount if the invoice is paid in five days and a 1-percent cash discount if the invoice is paid in 14 days.</span></span> <span data-ttu-id="6b800-107">A Fabrikam também oferece descontos à vista para pagamentos parciais.</span><span class="sxs-lookup"><span data-stu-id="6b800-107">Fabrikam also offers cash discounts on partial payments.</span></span> <span data-ttu-id="6b800-108">Os parâmetros de pagamento estão localizados na página **Parâmetros de contas a receber**.</span><span class="sxs-lookup"><span data-stu-id="6b800-108">The settlement parameters are located on the **Accounts receivable parameters** page.</span></span>

## <a name="invoice"></a><span data-ttu-id="6b800-109">Fatura</span><span class="sxs-lookup"><span data-stu-id="6b800-109">Invoice</span></span>
<span data-ttu-id="6b800-110">Em 25 de junho, Amanda insere e lança uma fatura de 1.000,00 para o cliente 4031.</span><span class="sxs-lookup"><span data-stu-id="6b800-110">On June 25, Arnie enters and posts an invoice for 1,000.00 for customer 4031.</span></span> <span data-ttu-id="6b800-111">Quando ele revisa os descontos em dinheiro para essa fatura, Arnie vê que o cliente 4031 recebe um desconto de 20,00 se a fatura for paga até 30 de junho.</span><span class="sxs-lookup"><span data-stu-id="6b800-111">When he reviews the cash discounts for this invoice, Arnie sees that customer 4031 receives a 20.00 discount if the invoice is paid by June 30.</span></span> <span data-ttu-id="6b800-112">Se a fatura for paga até 9 de julho, o cliente recebe um desconto de 10,00.</span><span class="sxs-lookup"><span data-stu-id="6b800-112">If the invoice is paid by July 9, the customer receives a 10.00 discount.</span></span>

| <span data-ttu-id="6b800-113">Data do desconto à vista</span><span class="sxs-lookup"><span data-stu-id="6b800-113">Cash discount date</span></span> | <span data-ttu-id="6b800-114">Valor de desconto à vista</span><span class="sxs-lookup"><span data-stu-id="6b800-114">Cash discount amount</span></span> | <span data-ttu-id="6b800-115">Valor na moeda da transação</span><span class="sxs-lookup"><span data-stu-id="6b800-115">Amount in transaction currency</span></span> |
|--------------------|----------------------|--------------------------------|
| <span data-ttu-id="6b800-116">30/6/2015</span><span class="sxs-lookup"><span data-stu-id="6b800-116">6/30/2015</span></span>          | <span data-ttu-id="6b800-117">20,00</span><span class="sxs-lookup"><span data-stu-id="6b800-117">20.00</span></span>                | <span data-ttu-id="6b800-118">980,00</span><span class="sxs-lookup"><span data-stu-id="6b800-118">980.00</span></span>                         |
| <span data-ttu-id="6b800-119">9/7/2015</span><span class="sxs-lookup"><span data-stu-id="6b800-119">7/9/2015</span></span>           | <span data-ttu-id="6b800-120">10.00</span><span class="sxs-lookup"><span data-stu-id="6b800-120">10.00</span></span>                | <span data-ttu-id="6b800-121">990,00</span><span class="sxs-lookup"><span data-stu-id="6b800-121">990.00</span></span>                         |
| <span data-ttu-id="6b800-122">25/7/2015</span><span class="sxs-lookup"><span data-stu-id="6b800-122">7/25/2015</span></span>          | <span data-ttu-id="6b800-123">0,00</span><span class="sxs-lookup"><span data-stu-id="6b800-123">0.00</span></span>                 | <span data-ttu-id="6b800-124">1.000,00</span><span class="sxs-lookup"><span data-stu-id="6b800-124">1,000.00</span></span>                       |

<span data-ttu-id="6b800-125">Alberto pode exibir esta transação na página**Transações do cliente**.</span><span class="sxs-lookup"><span data-stu-id="6b800-125">Arnie can view this transaction on the **Customer transactions** page.</span></span>

| <span data-ttu-id="6b800-126">Comprovante</span><span class="sxs-lookup"><span data-stu-id="6b800-126">Voucher</span></span>   | <span data-ttu-id="6b800-127">Tipo de transação</span><span class="sxs-lookup"><span data-stu-id="6b800-127">Transaction type</span></span> | <span data-ttu-id="6b800-128">Data</span><span class="sxs-lookup"><span data-stu-id="6b800-128">Date</span></span>      | <span data-ttu-id="6b800-129">Fatura</span><span class="sxs-lookup"><span data-stu-id="6b800-129">Invoice</span></span> | <span data-ttu-id="6b800-130">Valor em débito na moeda da transação</span><span class="sxs-lookup"><span data-stu-id="6b800-130">Amount in transaction currency debit</span></span> | <span data-ttu-id="6b800-131">Valor em crédito na moeda da transação</span><span class="sxs-lookup"><span data-stu-id="6b800-131">Amount in transaction currency credit</span></span> | <span data-ttu-id="6b800-132">Saldo</span><span class="sxs-lookup"><span data-stu-id="6b800-132">Balance</span></span>  | <span data-ttu-id="6b800-133">Moeda</span><span class="sxs-lookup"><span data-stu-id="6b800-133">Currency</span></span> |
|-----------|------------------|-----------|---------|--------------------------------------|---------------------------------------|----------|----------|
| <span data-ttu-id="6b800-134">FTI-10030</span><span class="sxs-lookup"><span data-stu-id="6b800-134">FTI-10030</span></span> | <span data-ttu-id="6b800-135">Fatura</span><span class="sxs-lookup"><span data-stu-id="6b800-135">Invoice</span></span>          | <span data-ttu-id="6b800-136">25/6/2015</span><span class="sxs-lookup"><span data-stu-id="6b800-136">6/25/2015</span></span> | <span data-ttu-id="6b800-137">10030</span><span class="sxs-lookup"><span data-stu-id="6b800-137">10030</span></span>   | <span data-ttu-id="6b800-138">1.000,00</span><span class="sxs-lookup"><span data-stu-id="6b800-138">1,000.00</span></span>                             |                                       | <span data-ttu-id="6b800-139">1.000,00</span><span class="sxs-lookup"><span data-stu-id="6b800-139">1,000.00</span></span> | <span data-ttu-id="6b800-140">USD</span><span class="sxs-lookup"><span data-stu-id="6b800-140">USD</span></span>      |

## <a name="partial-payment-before-the-cash-discount-date"></a><span data-ttu-id="6b800-141">Pagamento parcial antes da data de desconto à vista</span><span class="sxs-lookup"><span data-stu-id="6b800-141">Partial payment before the cash discount date</span></span>
<span data-ttu-id="6b800-142">Em 28 de junho, o Cliente 4031 faz um pagamento parcial de 294,00.</span><span class="sxs-lookup"><span data-stu-id="6b800-142">On June 28, Customer 4031 makes a partial payment of 294.00.</span></span> <span data-ttu-id="6b800-143">Como 28 de junho está no período de desconto à vista, o cliente obtém um desconto de 6,00.</span><span class="sxs-lookup"><span data-stu-id="6b800-143">Because June 28 is within the first cash discount period, the customer takes a 6.00 discount.</span></span> <span data-ttu-id="6b800-144">Na página **Liquidar**, o valor de **Valor do desconto à vista** é 20,00 e o valor de **Valor do desconto a ser obtido** é 6,00.</span><span class="sxs-lookup"><span data-stu-id="6b800-144">On the **Settle transactions** page, the **Cash discount amount** value is 20.00, and the **Cash discount amount to take** value is 6.00.</span></span>

| <span data-ttu-id="6b800-145">Marcar</span><span class="sxs-lookup"><span data-stu-id="6b800-145">Mark</span></span>     | <span data-ttu-id="6b800-146">Usar desconto à vista</span><span class="sxs-lookup"><span data-stu-id="6b800-146">Use cash discount</span></span> | <span data-ttu-id="6b800-147">Comprovante</span><span class="sxs-lookup"><span data-stu-id="6b800-147">Voucher</span></span>   | <span data-ttu-id="6b800-148">Conta</span><span class="sxs-lookup"><span data-stu-id="6b800-148">Account</span></span> | <span data-ttu-id="6b800-149">Data</span><span class="sxs-lookup"><span data-stu-id="6b800-149">Date</span></span>      | <span data-ttu-id="6b800-150">Data de conclusão</span><span class="sxs-lookup"><span data-stu-id="6b800-150">Due date</span></span>  | <span data-ttu-id="6b800-151">Fatura</span><span class="sxs-lookup"><span data-stu-id="6b800-151">Invoice</span></span> | <span data-ttu-id="6b800-152">Valor na moeda da transação</span><span class="sxs-lookup"><span data-stu-id="6b800-152">Amount in transaction currency</span></span> | <span data-ttu-id="6b800-153">Moeda</span><span class="sxs-lookup"><span data-stu-id="6b800-153">Currency</span></span> | <span data-ttu-id="6b800-154">Valor para liquidar</span><span class="sxs-lookup"><span data-stu-id="6b800-154">Amount to settle</span></span> |
|----------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------|----------|------------------|
| <span data-ttu-id="6b800-155">Selecionada</span><span class="sxs-lookup"><span data-stu-id="6b800-155">Selected</span></span> | <span data-ttu-id="6b800-156">Normal</span><span class="sxs-lookup"><span data-stu-id="6b800-156">Normal</span></span>            | <span data-ttu-id="6b800-157">FTI-10030</span><span class="sxs-lookup"><span data-stu-id="6b800-157">FTI-10030</span></span> | <span data-ttu-id="6b800-158">4031</span><span class="sxs-lookup"><span data-stu-id="6b800-158">4031</span></span>    | <span data-ttu-id="6b800-159">25/6/2015</span><span class="sxs-lookup"><span data-stu-id="6b800-159">6/25/2015</span></span> | <span data-ttu-id="6b800-160">25/7/2015</span><span class="sxs-lookup"><span data-stu-id="6b800-160">7/25/2015</span></span> | <span data-ttu-id="6b800-161">10030</span><span class="sxs-lookup"><span data-stu-id="6b800-161">10030</span></span>   | <span data-ttu-id="6b800-162">1.000,00</span><span class="sxs-lookup"><span data-stu-id="6b800-162">1,000.00</span></span>                       | <span data-ttu-id="6b800-163">USD</span><span class="sxs-lookup"><span data-stu-id="6b800-163">USD</span></span>      | <span data-ttu-id="6b800-164">294,00</span><span class="sxs-lookup"><span data-stu-id="6b800-164">294.00</span></span>           |

<span data-ttu-id="6b800-165">As informações do desconto aparecem na parte inferior da página **Liquidar transações abertas**.</span><span class="sxs-lookup"><span data-stu-id="6b800-165">Discount information appears at the bottom of the **Settle open transactions** page.</span></span> <span data-ttu-id="6b800-166">Se você não alterar o valor da opção **Valor para liquidar** para **294,00**, os valores da opção **Valor de desconto à vista** que aparecem serão diferentes.</span><span class="sxs-lookup"><span data-stu-id="6b800-166">If you don't change the **Amount to settle** value to **294.00**, the **Cash discount amount** values that appear will differ.</span></span> <span data-ttu-id="6b800-167">No entanto, 6,00 serão obtidos como o desconto à vista quando o pagamento for lançado, pois a liquidação é ajustada automaticamente ao **Valor para liquidar**para você.</span><span class="sxs-lookup"><span data-stu-id="6b800-167">However, 6.00 will be taken as the cash discount when the payment is posted, because settlement automatically adjusts the **Amount to settle** value for you.</span></span>

|                              |           |
|------------------------------|-----------|
| <span data-ttu-id="6b800-168">Data do desconto à vista</span><span class="sxs-lookup"><span data-stu-id="6b800-168">Cash discount date</span></span>           | <span data-ttu-id="6b800-169">30/6/2015</span><span class="sxs-lookup"><span data-stu-id="6b800-169">6/30/2015</span></span> |
| <span data-ttu-id="6b800-170">Valor de desconto à vista</span><span class="sxs-lookup"><span data-stu-id="6b800-170">Cash discount amount</span></span>         | <span data-ttu-id="6b800-171">20,00</span><span class="sxs-lookup"><span data-stu-id="6b800-171">20.00</span></span>     |
| <span data-ttu-id="6b800-172">Usar desconto à vista</span><span class="sxs-lookup"><span data-stu-id="6b800-172">Use cash discount</span></span>            | <span data-ttu-id="6b800-173">Normal</span><span class="sxs-lookup"><span data-stu-id="6b800-173">Normal</span></span>    |
| <span data-ttu-id="6b800-174">Desconto à vista obtido</span><span class="sxs-lookup"><span data-stu-id="6b800-174">Cash discount taken</span></span>          | <span data-ttu-id="6b800-175">0,00</span><span class="sxs-lookup"><span data-stu-id="6b800-175">0.00</span></span>      |
| <span data-ttu-id="6b800-176">Valor do desconto à vista a ser obtido</span><span class="sxs-lookup"><span data-stu-id="6b800-176">Cash discount amount to take</span></span> | <span data-ttu-id="6b800-177">6,00</span><span class="sxs-lookup"><span data-stu-id="6b800-177">6.00</span></span>      |

<span data-ttu-id="6b800-178">Após Arnie lançar o pagamento, o saldo da fatura será de 700,00.</span><span class="sxs-lookup"><span data-stu-id="6b800-178">After Arnie posts the payment, the invoice balance is 700.00.</span></span>

## <a name="partial-payment-before-the-second-cash-discount-date"></a><span data-ttu-id="6b800-179">Pagamento parcial antes da segunda data do desconto à vista</span><span class="sxs-lookup"><span data-stu-id="6b800-179">Partial payment before the second cash discount date</span></span>
<span data-ttu-id="6b800-180">Em 8 de julho, o cliente paga o restante do valor da fatura.</span><span class="sxs-lookup"><span data-stu-id="6b800-180">On July 8, the customer pays the rest of the invoice amount.</span></span> <span data-ttu-id="6b800-181">Um desconto de 7,00 (1%) é obtido, pois o pagamento foi realizado no segundo período de desconto à vista.</span><span class="sxs-lookup"><span data-stu-id="6b800-181">A 7.00 discount (1 percent) is taken, because the payment was made within the second cash discount period.</span></span>

| <span data-ttu-id="6b800-182">Marcar</span><span class="sxs-lookup"><span data-stu-id="6b800-182">Mark</span></span>     | <span data-ttu-id="6b800-183">Usar desconto à vista</span><span class="sxs-lookup"><span data-stu-id="6b800-183">Use cash discount</span></span> | <span data-ttu-id="6b800-184">Comprovante</span><span class="sxs-lookup"><span data-stu-id="6b800-184">Voucher</span></span>   | <span data-ttu-id="6b800-185">Conta</span><span class="sxs-lookup"><span data-stu-id="6b800-185">Account</span></span> | <span data-ttu-id="6b800-186">Data</span><span class="sxs-lookup"><span data-stu-id="6b800-186">Date</span></span>      | <span data-ttu-id="6b800-187">Data de conclusão</span><span class="sxs-lookup"><span data-stu-id="6b800-187">Due date</span></span>  | <span data-ttu-id="6b800-188">Fatura</span><span class="sxs-lookup"><span data-stu-id="6b800-188">Invoice</span></span> | <span data-ttu-id="6b800-189">Valor em débito na moeda da transação</span><span class="sxs-lookup"><span data-stu-id="6b800-189">Amount in transaction currency debit</span></span> | <span data-ttu-id="6b800-190">Valor em crédito na moeda da transação</span><span class="sxs-lookup"><span data-stu-id="6b800-190">Amount in transaction currency credit</span></span> | <span data-ttu-id="6b800-191">Moeda</span><span class="sxs-lookup"><span data-stu-id="6b800-191">Currency</span></span> | <span data-ttu-id="6b800-192">Valor para liquidar</span><span class="sxs-lookup"><span data-stu-id="6b800-192">Amount to settle</span></span> |
|----------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------------|---------------------------------------|----------|------------------|
| <span data-ttu-id="6b800-193">Selecionada</span><span class="sxs-lookup"><span data-stu-id="6b800-193">Selected</span></span> | <span data-ttu-id="6b800-194">Normal</span><span class="sxs-lookup"><span data-stu-id="6b800-194">Normal</span></span>            | <span data-ttu-id="6b800-195">FTI-10030</span><span class="sxs-lookup"><span data-stu-id="6b800-195">FTI-10030</span></span> | <span data-ttu-id="6b800-196">4031</span><span class="sxs-lookup"><span data-stu-id="6b800-196">4031</span></span>    | <span data-ttu-id="6b800-197">25/6/2015</span><span class="sxs-lookup"><span data-stu-id="6b800-197">6/25/2015</span></span> | <span data-ttu-id="6b800-198">25/7/2015</span><span class="sxs-lookup"><span data-stu-id="6b800-198">7/25/2015</span></span> | <span data-ttu-id="6b800-199">10030</span><span class="sxs-lookup"><span data-stu-id="6b800-199">10030</span></span>   | <span data-ttu-id="6b800-200">700.00</span><span class="sxs-lookup"><span data-stu-id="6b800-200">700.00</span></span>                               |                                       | <span data-ttu-id="6b800-201">USD</span><span class="sxs-lookup"><span data-stu-id="6b800-201">USD</span></span>      | <span data-ttu-id="6b800-202">693.00</span><span class="sxs-lookup"><span data-stu-id="6b800-202">693.00</span></span>           |

<span data-ttu-id="6b800-203">As informações do desconto aparecem na parte inferior da página **Liquidar transações abertas**.</span><span class="sxs-lookup"><span data-stu-id="6b800-203">Discount information appears at the bottom of the **Settle open transactions** page.</span></span>

|                              |           |
|------------------------------|-----------|
| <span data-ttu-id="6b800-204">Data do desconto à vista</span><span class="sxs-lookup"><span data-stu-id="6b800-204">Cash discount date</span></span>           | <span data-ttu-id="6b800-205">09/07/2015</span><span class="sxs-lookup"><span data-stu-id="6b800-205">7/09/2015</span></span> |
| <span data-ttu-id="6b800-206">Valor de desconto à vista</span><span class="sxs-lookup"><span data-stu-id="6b800-206">Cash discount amount</span></span>         | <span data-ttu-id="6b800-207">30,00</span><span class="sxs-lookup"><span data-stu-id="6b800-207">30.00</span></span>     |
| <span data-ttu-id="6b800-208">Usar desconto à vista</span><span class="sxs-lookup"><span data-stu-id="6b800-208">Use cash discount</span></span>            | <span data-ttu-id="6b800-209">Normal</span><span class="sxs-lookup"><span data-stu-id="6b800-209">Normal</span></span>    |
| <span data-ttu-id="6b800-210">Desconto à vista obtido</span><span class="sxs-lookup"><span data-stu-id="6b800-210">Cash discount taken</span></span>          | <span data-ttu-id="6b800-211">6,00</span><span class="sxs-lookup"><span data-stu-id="6b800-211">6.00</span></span>      |
| <span data-ttu-id="6b800-212">Valor do desconto à vista a ser obtido</span><span class="sxs-lookup"><span data-stu-id="6b800-212">Cash discount amount to take</span></span> | <span data-ttu-id="6b800-213">7:00</span><span class="sxs-lookup"><span data-stu-id="6b800-213">7.00</span></span>      |

<span data-ttu-id="6b800-214">O saldo da fatura agora é de 0,00.</span><span class="sxs-lookup"><span data-stu-id="6b800-214">The invoice balance is now 0.00.</span></span> <span data-ttu-id="6b800-215">Alberto exibe as informações na página **Transações do cliente**.</span><span class="sxs-lookup"><span data-stu-id="6b800-215">Arnie views the information on the **Customer transactions** page.</span></span>

| <span data-ttu-id="6b800-216">Comprovante</span><span class="sxs-lookup"><span data-stu-id="6b800-216">Voucher</span></span>    | <span data-ttu-id="6b800-217">Tipo de transação</span><span class="sxs-lookup"><span data-stu-id="6b800-217">Transaction type</span></span> | <span data-ttu-id="6b800-218">Data</span><span class="sxs-lookup"><span data-stu-id="6b800-218">Date</span></span>      | <span data-ttu-id="6b800-219">Fatura</span><span class="sxs-lookup"><span data-stu-id="6b800-219">Invoice</span></span> | <span data-ttu-id="6b800-220">Valor em débito na moeda da transação</span><span class="sxs-lookup"><span data-stu-id="6b800-220">Amount in transaction currency debit</span></span> | <span data-ttu-id="6b800-221">Valor em crédito na moeda da transação</span><span class="sxs-lookup"><span data-stu-id="6b800-221">Amount in transaction currency credit</span></span> | <span data-ttu-id="6b800-222">Saldo</span><span class="sxs-lookup"><span data-stu-id="6b800-222">Balance</span></span> | <span data-ttu-id="6b800-223">Moeda</span><span class="sxs-lookup"><span data-stu-id="6b800-223">Currency</span></span> |
|------------|------------------|-----------|---------|--------------------------------------|---------------------------------------|---------|----------|
| <span data-ttu-id="6b800-224">FTI-10030</span><span class="sxs-lookup"><span data-stu-id="6b800-224">FTI-10030</span></span>  | <span data-ttu-id="6b800-225">Fatura</span><span class="sxs-lookup"><span data-stu-id="6b800-225">Invoice</span></span>          | <span data-ttu-id="6b800-226">25/6/2015</span><span class="sxs-lookup"><span data-stu-id="6b800-226">6/25/2015</span></span> | <span data-ttu-id="6b800-227">10030</span><span class="sxs-lookup"><span data-stu-id="6b800-227">10030</span></span>   | <span data-ttu-id="6b800-228">1.000,00</span><span class="sxs-lookup"><span data-stu-id="6b800-228">1,000.00</span></span>                             |                                       | <span data-ttu-id="6b800-229">0,00</span><span class="sxs-lookup"><span data-stu-id="6b800-229">0.00</span></span>    | <span data-ttu-id="6b800-230">USD</span><span class="sxs-lookup"><span data-stu-id="6b800-230">USD</span></span>      |
| <span data-ttu-id="6b800-231">ARP-10030</span><span class="sxs-lookup"><span data-stu-id="6b800-231">ARP-10030</span></span>  |  <span data-ttu-id="6b800-232">Pagamento</span><span class="sxs-lookup"><span data-stu-id="6b800-232">Payment</span></span>         | <span data-ttu-id="6b800-233">28/6/2015</span><span class="sxs-lookup"><span data-stu-id="6b800-233">6/28/2015</span></span> |         |                                      | <span data-ttu-id="6b800-234">294,00</span><span class="sxs-lookup"><span data-stu-id="6b800-234">294.00</span></span>                                | <span data-ttu-id="6b800-235">0,00</span><span class="sxs-lookup"><span data-stu-id="6b800-235">0.00</span></span>    | <span data-ttu-id="6b800-236">USD</span><span class="sxs-lookup"><span data-stu-id="6b800-236">USD</span></span>      |
| <span data-ttu-id="6b800-237">DISC-10030</span><span class="sxs-lookup"><span data-stu-id="6b800-237">DISC-10030</span></span> |  <span data-ttu-id="6b800-238">Desconto à vista</span><span class="sxs-lookup"><span data-stu-id="6b800-238">Cash discount</span></span>   | <span data-ttu-id="6b800-239">28/6/2015</span><span class="sxs-lookup"><span data-stu-id="6b800-239">6/28/2015</span></span> |         |                                      | <span data-ttu-id="6b800-240">6,00</span><span class="sxs-lookup"><span data-stu-id="6b800-240">6.00</span></span>                                  | <span data-ttu-id="6b800-241">0,00</span><span class="sxs-lookup"><span data-stu-id="6b800-241">0.00</span></span>    | <span data-ttu-id="6b800-242">USD</span><span class="sxs-lookup"><span data-stu-id="6b800-242">USD</span></span>      |
| <span data-ttu-id="6b800-243">ARP-10031</span><span class="sxs-lookup"><span data-stu-id="6b800-243">ARP-10031</span></span>  |  <span data-ttu-id="6b800-244">Pagamento</span><span class="sxs-lookup"><span data-stu-id="6b800-244">Payment</span></span>         | <span data-ttu-id="6b800-245">8/7/2015</span><span class="sxs-lookup"><span data-stu-id="6b800-245">7/8/2015</span></span>  |         |                                      | <span data-ttu-id="6b800-246">693.00</span><span class="sxs-lookup"><span data-stu-id="6b800-246">693.00</span></span>                                | <span data-ttu-id="6b800-247">0,00</span><span class="sxs-lookup"><span data-stu-id="6b800-247">0.00</span></span>    | <span data-ttu-id="6b800-248">USD</span><span class="sxs-lookup"><span data-stu-id="6b800-248">USD</span></span>      |
| <span data-ttu-id="6b800-249">DISC-1031</span><span class="sxs-lookup"><span data-stu-id="6b800-249">DISC-1031</span></span>  |  <span data-ttu-id="6b800-250">Desconto à vista</span><span class="sxs-lookup"><span data-stu-id="6b800-250">Cash discount</span></span>   | <span data-ttu-id="6b800-251">8/7/2015</span><span class="sxs-lookup"><span data-stu-id="6b800-251">7/8/2015</span></span>  |         |                                      | <span data-ttu-id="6b800-252">7:00</span><span class="sxs-lookup"><span data-stu-id="6b800-252">7.00</span></span>                                  | <span data-ttu-id="6b800-253">0,00</span><span class="sxs-lookup"><span data-stu-id="6b800-253">0.00</span></span>    | <span data-ttu-id="6b800-254">USD</span><span class="sxs-lookup"><span data-stu-id="6b800-254">USD</span></span>      |




