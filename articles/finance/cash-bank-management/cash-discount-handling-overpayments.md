---
title: Manuseio de descontos à vista para pagamentos a maior
description: Este artigo fornece os cenários que mostram como um pagamento é manuseado quando o cliente leva um desconto à vista, mas também paga em excesso.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustOpenTrans, CustParameters, LedgerJournalTransCustPaym, LedgerJournalTransVendPaym, VendOpenTrans, VendParameters
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 14171
ms.assetid: a94d0fd0-57ba-4054-93c8-519d01d50e19
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 803cb478bb7631439ebde66ad96182193d3dd1ae
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2188340"
---
# <a name="handling-cash-discounts-for-overpayments"></a><span data-ttu-id="2bc3a-103">Manuseio de descontos à vista para pagamentos a maior</span><span class="sxs-lookup"><span data-stu-id="2bc3a-103">Handling cash discounts for overpayments</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="2bc3a-104">Este artigo fornece os cenários que mostram como um pagamento é manuseado quando o cliente leva um desconto à vista, mas também paga em excesso.</span><span class="sxs-lookup"><span data-stu-id="2bc3a-104">This article provides scenarios that show how a payment is handled when the customer takes a cash discount but also overpays.</span></span> 

<span data-ttu-id="2bc3a-105">Uma fatura será considerada liquidada quando o valor do pagamento for maior do que o valor da fatura menos o desconto à vista.</span><span class="sxs-lookup"><span data-stu-id="2bc3a-105">An invoice is considered overpaid when the payment amount is more than the invoice amount minus the cash discount.</span></span> <span data-ttu-id="2bc3a-106">Para especificar como uma diferença de desconto à vista viável é manuseada quando uma fatura é paga a maior, use os campos **Administração de descontos à vista** e **Pagamento máximo a maior/a menor** na página **Parâmetros de contas a receber**.</span><span class="sxs-lookup"><span data-stu-id="2bc3a-106">To specify how an obtainable cash discount difference is handled when an invoice is overpaid, use the **Cash discount administration** and **Maximum overpayment or underpayment** fields on the **Accounts receivable parameters** page.</span></span> <span data-ttu-id="2bc3a-107">No exemplo a seguir, o cliente pagou em excesso a fatura de 0,50.</span><span class="sxs-lookup"><span data-stu-id="2bc3a-107">In the following example, the customer has overpaid the invoice by 0.50.</span></span>

| <span data-ttu-id="2bc3a-108">Total da fatura</span><span class="sxs-lookup"><span data-stu-id="2bc3a-108">Invoice total</span></span> | <span data-ttu-id="2bc3a-109">Desconto à vista disponível</span><span class="sxs-lookup"><span data-stu-id="2bc3a-109">Cash discount available</span></span> | <span data-ttu-id="2bc3a-110">Valor a ser pago, o que inclui o desconto à vista</span><span class="sxs-lookup"><span data-stu-id="2bc3a-110">Amount to be paid, which includes the cash discount</span></span> | <span data-ttu-id="2bc3a-111">Valor que o cliente realmente paga</span><span class="sxs-lookup"><span data-stu-id="2bc3a-111">Amount the customer actually pays</span></span> |
|---------------|-------------------------|-----------------------------------------------------|-----------------------------------|
| <span data-ttu-id="2bc3a-112">R$ 105,00</span><span class="sxs-lookup"><span data-stu-id="2bc3a-112">105.00</span></span>        | <span data-ttu-id="2bc3a-113">R$ 10,50</span><span class="sxs-lookup"><span data-stu-id="2bc3a-113">10.50</span></span>                   | <span data-ttu-id="2bc3a-114">R$ 94,50</span><span class="sxs-lookup"><span data-stu-id="2bc3a-114">94.50</span></span>                                               | <span data-ttu-id="2bc3a-115">R$ 95,00</span><span class="sxs-lookup"><span data-stu-id="2bc3a-115">95.00</span></span>                             |

## <a name="cash-discount-administration--specific"></a><span data-ttu-id="2bc3a-116">Opção de administração do desconto à vista = Específico</span><span class="sxs-lookup"><span data-stu-id="2bc3a-116">Cash discount administration = Specific</span></span>
<span data-ttu-id="2bc3a-117">Quando **Específico** for selecionado no campo **Administração de descontos à vista** na página **Contas para transações automáticas**, o desconto à vista total será obtido.</span><span class="sxs-lookup"><span data-stu-id="2bc3a-117">When **Specific** is selected in the **Cash discount administration** field on the **Accounts for automatic transactions** page, the full cash discount is taken.</span></span> <span data-ttu-id="2bc3a-118">O valor do pagamento a maior é lançado em uma conta contábil da diferença de desconto à vista ou permanece um saldo da conta de cliente.</span><span class="sxs-lookup"><span data-stu-id="2bc3a-118">The overpayment amount either is posted to a cash discount difference ledger account or remains a balance on the customer’s account.</span></span> <span data-ttu-id="2bc3a-119">O comportamento depende do fato de o valor do pagamento excedente estar entre 0,00 e o valor inserido no campo **Pagamento máximo a maior/a menor** ou se o valor do pagamento a maior for maior do que o valor de **Pagamento máximo a maior/a menor**.</span><span class="sxs-lookup"><span data-stu-id="2bc3a-119">The behavior depends on whether the overpayment amount is between 0.00 and the amount that is entered in the **Maximum overpayment or underpayment** field, or whether the overpayment amount is more than the **Maximum overpayment or underpayment** amount.</span></span>

### <a name="scenario-1"></a><span data-ttu-id="2bc3a-120">Cenário 1</span><span class="sxs-lookup"><span data-stu-id="2bc3a-120">Scenario 1</span></span>

<span data-ttu-id="2bc3a-121">Neste cenário, o valor do pagamento a maior está entre 0,00 e o pagamento máximo a maior/a menor.</span><span class="sxs-lookup"><span data-stu-id="2bc3a-121">In this scenario, the overpayment amount is between 0.00 and the maximum overpayment or underpayment.</span></span> <span data-ttu-id="2bc3a-122">Uma fatura de 105,00 é inserida e um desconto à vista ficará disponível se a fatura for paga em até sete dias.</span><span class="sxs-lookup"><span data-stu-id="2bc3a-122">An invoice for 105.00 is entered, and a cash discount is available if the invoice is paid within seven days.</span></span>

| <span data-ttu-id="2bc3a-123">Total da fatura</span><span class="sxs-lookup"><span data-stu-id="2bc3a-123">Invoice total</span></span> | <span data-ttu-id="2bc3a-124">Desconto à vista disponível</span><span class="sxs-lookup"><span data-stu-id="2bc3a-124">Cash discount available</span></span> | <span data-ttu-id="2bc3a-125">Valor a ser pago, o que inclui o desconto à vista</span><span class="sxs-lookup"><span data-stu-id="2bc3a-125">Amount to be paid, which includes the cash discount</span></span> |
|---------------|-------------------------|-----------------------------------------------------|
| <span data-ttu-id="2bc3a-126">R$ 105,00</span><span class="sxs-lookup"><span data-stu-id="2bc3a-126">105.00</span></span>        | <span data-ttu-id="2bc3a-127">R$ 10,50</span><span class="sxs-lookup"><span data-stu-id="2bc3a-127">10.50</span></span>                   | <span data-ttu-id="2bc3a-128">R$ 94,50</span><span class="sxs-lookup"><span data-stu-id="2bc3a-128">94.50</span></span>                                               |

<span data-ttu-id="2bc3a-129">O cliente envia um pagamento de 95,00 no período de desconto à vista.</span><span class="sxs-lookup"><span data-stu-id="2bc3a-129">The customer submits a payment for 95.00 within the cash discount period.</span></span> <span data-ttu-id="2bc3a-130">O pagamento é liquidado com a fatura de 105,00.</span><span class="sxs-lookup"><span data-stu-id="2bc3a-130">The payment is settled against the invoice for 105.00.</span></span> <span data-ttu-id="2bc3a-131">Depois que a fatura e o pagamento forem liquidados, as transações a seguir serão criadas para o cliente em Contas a receber.</span><span class="sxs-lookup"><span data-stu-id="2bc3a-131">After the invoice and payment are settled, the following transactions are created for the customer in Accounts receivable.</span></span>

| <span data-ttu-id="2bc3a-132">Transação</span><span class="sxs-lookup"><span data-stu-id="2bc3a-132">Transaction</span></span>   | <span data-ttu-id="2bc3a-133">Valor</span><span class="sxs-lookup"><span data-stu-id="2bc3a-133">Amount</span></span> | <span data-ttu-id="2bc3a-134">Saldo</span><span class="sxs-lookup"><span data-stu-id="2bc3a-134">Balance</span></span> |
|---------------|--------|---------|
| <span data-ttu-id="2bc3a-135">Fatura</span><span class="sxs-lookup"><span data-stu-id="2bc3a-135">Invoice</span></span>       | <span data-ttu-id="2bc3a-136">R$ 105,00</span><span class="sxs-lookup"><span data-stu-id="2bc3a-136">105.00</span></span> | <span data-ttu-id="2bc3a-137">0,00</span><span class="sxs-lookup"><span data-stu-id="2bc3a-137">0.00</span></span>    |
| <span data-ttu-id="2bc3a-138">Pagamento</span><span class="sxs-lookup"><span data-stu-id="2bc3a-138">Payment</span></span>       | <span data-ttu-id="2bc3a-139">-95,00</span><span class="sxs-lookup"><span data-stu-id="2bc3a-139">-95.00</span></span> | <span data-ttu-id="2bc3a-140">0,00</span><span class="sxs-lookup"><span data-stu-id="2bc3a-140">0.00</span></span>    |
| <span data-ttu-id="2bc3a-141">Desconto à vista</span><span class="sxs-lookup"><span data-stu-id="2bc3a-141">Cash discount</span></span> | <span data-ttu-id="2bc3a-142">-10,50</span><span class="sxs-lookup"><span data-stu-id="2bc3a-142">-10.50</span></span> | <span data-ttu-id="2bc3a-143">0,00</span><span class="sxs-lookup"><span data-stu-id="2bc3a-143">0.00</span></span>    |

<span data-ttu-id="2bc3a-144">As seguintes entradas contábeis serão geradas para o pagamento e a liquidação.</span><span class="sxs-lookup"><span data-stu-id="2bc3a-144">The following accounting entries are generated for the payment and the settlement.</span></span> <span data-ttu-id="2bc3a-145">**Pagamento**</span><span class="sxs-lookup"><span data-stu-id="2bc3a-145">**Payment**</span></span>

| <span data-ttu-id="2bc3a-146">Conta</span><span class="sxs-lookup"><span data-stu-id="2bc3a-146">Account</span></span>             | <span data-ttu-id="2bc3a-147">Valor do débito</span><span class="sxs-lookup"><span data-stu-id="2bc3a-147">Debit amount</span></span> | <span data-ttu-id="2bc3a-148">Valor de crédito</span><span class="sxs-lookup"><span data-stu-id="2bc3a-148">Credit amount</span></span> |
|---------------------|--------------|---------------|
| <span data-ttu-id="2bc3a-149">Pagamento à vista</span><span class="sxs-lookup"><span data-stu-id="2bc3a-149">Cash</span></span>                | <span data-ttu-id="2bc3a-150">R$ 95,00</span><span class="sxs-lookup"><span data-stu-id="2bc3a-150">95.00</span></span>        |               |
| <span data-ttu-id="2bc3a-151">Contas a Receber</span><span class="sxs-lookup"><span data-stu-id="2bc3a-151">Accounts receivable</span></span> |              | <span data-ttu-id="2bc3a-152">R$ 95,00</span><span class="sxs-lookup"><span data-stu-id="2bc3a-152">95.00</span></span>         |

<span data-ttu-id="2bc3a-153">**Liquidação**</span><span class="sxs-lookup"><span data-stu-id="2bc3a-153">**Settlement**</span></span>

| <span data-ttu-id="2bc3a-154">Conta</span><span class="sxs-lookup"><span data-stu-id="2bc3a-154">Account</span></span>                                                                                                          | <span data-ttu-id="2bc3a-155">Valor do débito</span><span class="sxs-lookup"><span data-stu-id="2bc3a-155">Debit amount</span></span> | <span data-ttu-id="2bc3a-156">Valor de crédito</span><span class="sxs-lookup"><span data-stu-id="2bc3a-156">Credit amount</span></span> |
|------------------------------------------------------------------------------------------------------------------|--------------|---------------|
| <span data-ttu-id="2bc3a-157">Desconto à vista (o campo **Conta principal para descontos do cliente** na página **Descontos à vista**)</span><span class="sxs-lookup"><span data-stu-id="2bc3a-157">Cash discount (the **Main account for customer discounts** field on the **Cash discounts** page)</span></span>                 | <span data-ttu-id="2bc3a-158">R$ 10,50</span><span class="sxs-lookup"><span data-stu-id="2bc3a-158">10.50</span></span>        |               |
| <span data-ttu-id="2bc3a-159">Contas a Receber</span><span class="sxs-lookup"><span data-stu-id="2bc3a-159">Accounts receivable</span></span>                                                                                              |              | <span data-ttu-id="2bc3a-160">R$ 10,50</span><span class="sxs-lookup"><span data-stu-id="2bc3a-160">10.50</span></span>         |
| <span data-ttu-id="2bc3a-161">Desconto à vista do cliente (o campo **Desconto à vista do cliente** na página **Conta para transações automáticas**)</span><span class="sxs-lookup"><span data-stu-id="2bc3a-161">Customer cash discount (the **Customer cash discount** field on the **Account for automatic transactions** page)</span></span> |              | <span data-ttu-id="2bc3a-162">0,50</span><span class="sxs-lookup"><span data-stu-id="2bc3a-162">0.50</span></span>          |
| <span data-ttu-id="2bc3a-163">Contas a Receber</span><span class="sxs-lookup"><span data-stu-id="2bc3a-163">Accounts receivable</span></span>                                                                                              | <span data-ttu-id="2bc3a-164">0,50</span><span class="sxs-lookup"><span data-stu-id="2bc3a-164">0.50</span></span>         |               |

### <a name="scenario-2"></a><span data-ttu-id="2bc3a-165">Cenário 2</span><span class="sxs-lookup"><span data-stu-id="2bc3a-165">Scenario 2</span></span>

<span data-ttu-id="2bc3a-166">Neste cenário, o valor de pagamento a maior excede o valor máximo de pagamento a maior ou a menor.</span><span class="sxs-lookup"><span data-stu-id="2bc3a-166">In this scenario, the overpayment amount exceeds the maximum overpayment or underpayment amount.</span></span> <span data-ttu-id="2bc3a-167">Uma fatura de 105,00 é inserida e um desconto à vista ficará disponível se a fatura for paga em até sete dias.</span><span class="sxs-lookup"><span data-stu-id="2bc3a-167">An invoice for 105.00 is entered, and a cash discount is available if the invoice is paid within seven days.</span></span>

| <span data-ttu-id="2bc3a-168">Total da fatura</span><span class="sxs-lookup"><span data-stu-id="2bc3a-168">Invoice total</span></span> | <span data-ttu-id="2bc3a-169">Desconto à vista disponível</span><span class="sxs-lookup"><span data-stu-id="2bc3a-169">Cash discount available</span></span> | <span data-ttu-id="2bc3a-170">Valor a ser pago, o que inclui o desconto à vista</span><span class="sxs-lookup"><span data-stu-id="2bc3a-170">Amount to be paid, which includes the cash discount</span></span> |
|---------------|-------------------------|-----------------------------------------------------|
| <span data-ttu-id="2bc3a-171">R$ 105,00</span><span class="sxs-lookup"><span data-stu-id="2bc3a-171">105.00</span></span>        | <span data-ttu-id="2bc3a-172">R$ 10,50</span><span class="sxs-lookup"><span data-stu-id="2bc3a-172">10.50</span></span>                   | <span data-ttu-id="2bc3a-173">R$ 94,50</span><span class="sxs-lookup"><span data-stu-id="2bc3a-173">94.50</span></span>                                               |

<span data-ttu-id="2bc3a-174">O cliente envia um pagamento de 95,00 no período de desconto à vista.</span><span class="sxs-lookup"><span data-stu-id="2bc3a-174">The customer submits a payment for 95.00 within the cash discount period.</span></span> <span data-ttu-id="2bc3a-175">O pagamento é liquidado com a fatura de 105,00.</span><span class="sxs-lookup"><span data-stu-id="2bc3a-175">The payment is settled against the invoice for 105.00.</span></span> <span data-ttu-id="2bc3a-176">Depois que a fatura e o pagamento forem liquidados, as transações a seguir serão criadas para o cliente em Contas a receber.</span><span class="sxs-lookup"><span data-stu-id="2bc3a-176">After the invoice and payment are settled, the following transactions are created for the customer in Accounts receivable.</span></span>

| <span data-ttu-id="2bc3a-177">Transação</span><span class="sxs-lookup"><span data-stu-id="2bc3a-177">Transaction</span></span>   | <span data-ttu-id="2bc3a-178">Valor</span><span class="sxs-lookup"><span data-stu-id="2bc3a-178">Amount</span></span> | <span data-ttu-id="2bc3a-179">Saldo</span><span class="sxs-lookup"><span data-stu-id="2bc3a-179">Balance</span></span> |
|---------------|--------|---------|
| <span data-ttu-id="2bc3a-180">Fatura</span><span class="sxs-lookup"><span data-stu-id="2bc3a-180">Invoice</span></span>       | <span data-ttu-id="2bc3a-181">R$ 105,00</span><span class="sxs-lookup"><span data-stu-id="2bc3a-181">105.00</span></span> | <span data-ttu-id="2bc3a-182">0,00</span><span class="sxs-lookup"><span data-stu-id="2bc3a-182">0.00</span></span>    |
| <span data-ttu-id="2bc3a-183">Pagamento</span><span class="sxs-lookup"><span data-stu-id="2bc3a-183">Payment</span></span>       | <span data-ttu-id="2bc3a-184">-95,00</span><span class="sxs-lookup"><span data-stu-id="2bc3a-184">-95.00</span></span> | <span data-ttu-id="2bc3a-185">-0,50</span><span class="sxs-lookup"><span data-stu-id="2bc3a-185">-0.50</span></span>   |
| <span data-ttu-id="2bc3a-186">Desconto à vista</span><span class="sxs-lookup"><span data-stu-id="2bc3a-186">Cash discount</span></span> | <span data-ttu-id="2bc3a-187">-10,50</span><span class="sxs-lookup"><span data-stu-id="2bc3a-187">-10.50</span></span> | <span data-ttu-id="2bc3a-188">0,00</span><span class="sxs-lookup"><span data-stu-id="2bc3a-188">0.00</span></span>    |

<span data-ttu-id="2bc3a-189">O valor do pagamento a maior de 0.50 permanecerá como um saldo em aberto no pagamento e pode ser liquidado outra fatura.</span><span class="sxs-lookup"><span data-stu-id="2bc3a-189">The overpayment amount of 0.50 will remain as an open balance on the payment and can be settled against another invoice.</span></span> <span data-ttu-id="2bc3a-190">As seguintes entradas contábeis serão geradas para o pagamento e a liquidação.</span><span class="sxs-lookup"><span data-stu-id="2bc3a-190">The following accounting entries are generated for the payment and the settlement.</span></span> <span data-ttu-id="2bc3a-191">**Pagamento**</span><span class="sxs-lookup"><span data-stu-id="2bc3a-191">**Payment**</span></span>

| <span data-ttu-id="2bc3a-192">Conta</span><span class="sxs-lookup"><span data-stu-id="2bc3a-192">Account</span></span>             | <span data-ttu-id="2bc3a-193">Valor do débito</span><span class="sxs-lookup"><span data-stu-id="2bc3a-193">Debit amount</span></span> | <span data-ttu-id="2bc3a-194">Valor de crédito</span><span class="sxs-lookup"><span data-stu-id="2bc3a-194">Credit amount</span></span> |
|---------------------|--------------|---------------|
| <span data-ttu-id="2bc3a-195">Pagamento à vista</span><span class="sxs-lookup"><span data-stu-id="2bc3a-195">Cash</span></span>                | <span data-ttu-id="2bc3a-196">R$ 95,00</span><span class="sxs-lookup"><span data-stu-id="2bc3a-196">95.00</span></span>        |               |
| <span data-ttu-id="2bc3a-197">Contas a Receber</span><span class="sxs-lookup"><span data-stu-id="2bc3a-197">Accounts receivable</span></span> |              | <span data-ttu-id="2bc3a-198">R$ 95,00</span><span class="sxs-lookup"><span data-stu-id="2bc3a-198">95.00</span></span>         |

<span data-ttu-id="2bc3a-199">**Liquidação**</span><span class="sxs-lookup"><span data-stu-id="2bc3a-199">**Settlement**</span></span>

| <span data-ttu-id="2bc3a-200">Conta</span><span class="sxs-lookup"><span data-stu-id="2bc3a-200">Account</span></span>                                                                                          | <span data-ttu-id="2bc3a-201">Valor do débito</span><span class="sxs-lookup"><span data-stu-id="2bc3a-201">Debit amount</span></span> | <span data-ttu-id="2bc3a-202">Valor de crédito</span><span class="sxs-lookup"><span data-stu-id="2bc3a-202">Credit amount</span></span> |
|--------------------------------------------------------------------------------------------------|--------------|---------------|
| <span data-ttu-id="2bc3a-203">Desconto à vista (o campo **Conta principal para descontos do cliente** na página **Descontos à vista**)</span><span class="sxs-lookup"><span data-stu-id="2bc3a-203">Cash discount (the **Main account for customer discounts** field on the **Cash discounts** page)</span></span> | <span data-ttu-id="2bc3a-204">R$ 10,50</span><span class="sxs-lookup"><span data-stu-id="2bc3a-204">10.50</span></span>        |               |
| <span data-ttu-id="2bc3a-205">Contas a Receber</span><span class="sxs-lookup"><span data-stu-id="2bc3a-205">Accounts receivable</span></span>                                                                              |              | <span data-ttu-id="2bc3a-206">R$ 10,50</span><span class="sxs-lookup"><span data-stu-id="2bc3a-206">10.50</span></span>         |

## <a name="cash-discount-administration--unspecific"></a><span data-ttu-id="2bc3a-207">Opção de administração do desconto à vista = Não específico</span><span class="sxs-lookup"><span data-stu-id="2bc3a-207">Cash discount administration = Unspecific</span></span>
<span data-ttu-id="2bc3a-208">Quando **Não específico** for selecionado no campo **Administração de descontos à vista** na página **Contas para transações automáticas**, o valor do desconto à vista será reduzido pelo valor do pagamento a maior.</span><span class="sxs-lookup"><span data-stu-id="2bc3a-208">When **Unspecific** is selected in the **Cash discount administration** field on the **Accounts for automatic transactions** page, the cash discount amount is reduced by the overpayment amount.</span></span> <span data-ttu-id="2bc3a-209">Esse comportamento sempre se aplicará, mesmo se o valor do pagamento a maior for maior ou menor do que o valor inserido no campo **Pagamento máximo a maior/menor**.</span><span class="sxs-lookup"><span data-stu-id="2bc3a-209">This behavior always applies, regardless of whether the overpayment amount is over or under the amount that is entered in the **Maximum overpayment or underpayment** field.</span></span>

### <a name="scenario-3"></a><span data-ttu-id="2bc3a-210">Cenário 3</span><span class="sxs-lookup"><span data-stu-id="2bc3a-210">Scenario 3</span></span>

<span data-ttu-id="2bc3a-211">Neste cenário, uma fatura de 105,00 é inserida e um desconto à vista ficará disponível se a fatura for paga em até sete dias.</span><span class="sxs-lookup"><span data-stu-id="2bc3a-211">In this scenario, an invoice for 105.00 is entered, and a cash discount is available if the invoice is paid within seven days.</span></span>

| <span data-ttu-id="2bc3a-212">Total da fatura</span><span class="sxs-lookup"><span data-stu-id="2bc3a-212">Invoice total</span></span> | <span data-ttu-id="2bc3a-213">Desconto à vista disponível</span><span class="sxs-lookup"><span data-stu-id="2bc3a-213">Cash discount available</span></span> | <span data-ttu-id="2bc3a-214">Valor a ser pago, o que inclui o desconto à vista</span><span class="sxs-lookup"><span data-stu-id="2bc3a-214">Amount to be paid, which includes the cash discount</span></span> |
|---------------|-------------------------|-----------------------------------------------------|
| <span data-ttu-id="2bc3a-215">R$ 105,00</span><span class="sxs-lookup"><span data-stu-id="2bc3a-215">105.00</span></span>        | <span data-ttu-id="2bc3a-216">R$ 10,50</span><span class="sxs-lookup"><span data-stu-id="2bc3a-216">10.50</span></span>                   | <span data-ttu-id="2bc3a-217">R$ 94,50</span><span class="sxs-lookup"><span data-stu-id="2bc3a-217">94.50</span></span>                                               |

<span data-ttu-id="2bc3a-218">O cliente envia um pagamento de 95,00 na data de desconto à vista.</span><span class="sxs-lookup"><span data-stu-id="2bc3a-218">The customer submits a payment for 95.00 within the cash discount date.</span></span> <span data-ttu-id="2bc3a-219">O pagamento é liquidado com a fatura de 105,00.</span><span class="sxs-lookup"><span data-stu-id="2bc3a-219">The payment is settled against the invoice for 105.00.</span></span> <span data-ttu-id="2bc3a-220">Depois que a fatura e o pagamento forem liquidados, as transações a seguir serão criadas para o cliente em Contas a receber.</span><span class="sxs-lookup"><span data-stu-id="2bc3a-220">After the invoice and payment are settled, the following transactions are created for the customer in Accounts receivable.</span></span>

| <span data-ttu-id="2bc3a-221">Transação</span><span class="sxs-lookup"><span data-stu-id="2bc3a-221">Transaction</span></span>   | <span data-ttu-id="2bc3a-222">Valor</span><span class="sxs-lookup"><span data-stu-id="2bc3a-222">Amount</span></span> | <span data-ttu-id="2bc3a-223">Saldo</span><span class="sxs-lookup"><span data-stu-id="2bc3a-223">Balance</span></span> |
|---------------|--------|---------|
| <span data-ttu-id="2bc3a-224">Fatura</span><span class="sxs-lookup"><span data-stu-id="2bc3a-224">Invoice</span></span>       | <span data-ttu-id="2bc3a-225">R$ 105,00</span><span class="sxs-lookup"><span data-stu-id="2bc3a-225">105.00</span></span> | <span data-ttu-id="2bc3a-226">0,00</span><span class="sxs-lookup"><span data-stu-id="2bc3a-226">0.00</span></span>    |
| <span data-ttu-id="2bc3a-227">Pagamento</span><span class="sxs-lookup"><span data-stu-id="2bc3a-227">Payment</span></span>       | <span data-ttu-id="2bc3a-228">-95,00</span><span class="sxs-lookup"><span data-stu-id="2bc3a-228">-95.00</span></span> | <span data-ttu-id="2bc3a-229">-0,00</span><span class="sxs-lookup"><span data-stu-id="2bc3a-229">-0.00</span></span>   |
| <span data-ttu-id="2bc3a-230">Desconto à vista</span><span class="sxs-lookup"><span data-stu-id="2bc3a-230">Cash discount</span></span> | <span data-ttu-id="2bc3a-231">-10,00</span><span class="sxs-lookup"><span data-stu-id="2bc3a-231">-10.00</span></span> | <span data-ttu-id="2bc3a-232">0,00</span><span class="sxs-lookup"><span data-stu-id="2bc3a-232">0.00</span></span>    |

<span data-ttu-id="2bc3a-233">O valor do desconto à vista é reduzido de 10,50 para 10,00.</span><span class="sxs-lookup"><span data-stu-id="2bc3a-233">The cash discount amount is reduced from 10.50 to 10.00.</span></span> <span data-ttu-id="2bc3a-234">O pagamento e a fatura são considerados liquidados.</span><span class="sxs-lookup"><span data-stu-id="2bc3a-234">The payment and invoice are considered settled.</span></span> <span data-ttu-id="2bc3a-235">**Pagamento**</span><span class="sxs-lookup"><span data-stu-id="2bc3a-235">**Payment**</span></span>

| <span data-ttu-id="2bc3a-236">Conta</span><span class="sxs-lookup"><span data-stu-id="2bc3a-236">Account</span></span>             | <span data-ttu-id="2bc3a-237">Valor de débito</span><span class="sxs-lookup"><span data-stu-id="2bc3a-237">Debit amount</span></span> | <span data-ttu-id="2bc3a-238">Valor de crédito</span><span class="sxs-lookup"><span data-stu-id="2bc3a-238">Credit amount</span></span> |
|---------------------|--------------|---------------|
| <span data-ttu-id="2bc3a-239">Pagamento à vista</span><span class="sxs-lookup"><span data-stu-id="2bc3a-239">Cash</span></span>                | <span data-ttu-id="2bc3a-240">R$ 95,00</span><span class="sxs-lookup"><span data-stu-id="2bc3a-240">95.00</span></span>        |               |
| <span data-ttu-id="2bc3a-241">Contas a Receber</span><span class="sxs-lookup"><span data-stu-id="2bc3a-241">Accounts receivable</span></span> |              | <span data-ttu-id="2bc3a-242">R$ 95,00</span><span class="sxs-lookup"><span data-stu-id="2bc3a-242">95.00</span></span>         |

<span data-ttu-id="2bc3a-243">**Liquidação**</span><span class="sxs-lookup"><span data-stu-id="2bc3a-243">**Settlement**</span></span>

| <span data-ttu-id="2bc3a-244">Conta</span><span class="sxs-lookup"><span data-stu-id="2bc3a-244">Account</span></span>                                                                                          | <span data-ttu-id="2bc3a-245">Valor do débito</span><span class="sxs-lookup"><span data-stu-id="2bc3a-245">Debit amount</span></span> | <span data-ttu-id="2bc3a-246">Valor de crédito</span><span class="sxs-lookup"><span data-stu-id="2bc3a-246">Credit amount</span></span> |
|--------------------------------------------------------------------------------------------------|--------------|---------------|
| <span data-ttu-id="2bc3a-247">Desconto à vista (o campo **Conta principal para descontos do cliente** na página **Descontos à vista**)</span><span class="sxs-lookup"><span data-stu-id="2bc3a-247">Cash discount (the **Main account for customer discounts** field on the **Cash discounts** page)</span></span> | <span data-ttu-id="2bc3a-248">R$ 10,50</span><span class="sxs-lookup"><span data-stu-id="2bc3a-248">10.50</span></span>        |               |
| <span data-ttu-id="2bc3a-249">Contas a Receber</span><span class="sxs-lookup"><span data-stu-id="2bc3a-249">Accounts receivable</span></span>                                                                              |              | <span data-ttu-id="2bc3a-250">R$ 10,50</span><span class="sxs-lookup"><span data-stu-id="2bc3a-250">10.50</span></span>         |




