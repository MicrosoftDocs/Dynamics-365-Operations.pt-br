---
title: Liquidar um pagamento parcial de cliente com descontos em notas de crédito
description: Este artigo mostra um cenário onde um desconto à vista é aplicado a uma nota de crédito quando a fatura original também tinha um desconto à vista.
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
ms.custom: 14564
ms.assetid: d9984cef-ddcf-46bd-816d-c01b8cc5cf48
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f1a37b7c5aea22711938133d43b552eec9260f0a
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2188961"
---
# <a name="settle-a-partial-customer-payment-that-has-discounts-on-credit-notes"></a><span data-ttu-id="b8f61-103">Liquidar um pagamento parcial de cliente com descontos em notas de crédito</span><span class="sxs-lookup"><span data-stu-id="b8f61-103">Settle a partial customer payment that has discounts on credit notes</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b8f61-104">Este artigo mostra um cenário onde um desconto à vista é aplicado a uma nota de crédito quando a fatura original também tinha um desconto à vista.</span><span class="sxs-lookup"><span data-stu-id="b8f61-104">This article walks you through a scenario where a cash discount is taken on a credit note when the original invoice also had a cash discount.</span></span> 

<span data-ttu-id="b8f61-105">A Fabrikam permite que os clientes tenham descontos à vista em pagamentos parciais e também em notas de crédito (memorandos de crédito).</span><span class="sxs-lookup"><span data-stu-id="b8f61-105">Fabrikam allows customers to take cash discounts on partial payments and also on credit notes (credit memos).</span></span> <span data-ttu-id="b8f61-106">Um desconto à vista pode ser obtido em uma nota de crédito quando a nota de crédito for emitida para uma fatura que o cliente obteve em um desconto à vista.</span><span class="sxs-lookup"><span data-stu-id="b8f61-106">A cash discount can be taken on a credit note when the credit note is issued for an invoice that the customer took a cash discount on.</span></span> <span data-ttu-id="b8f61-107">Em vez de fornecer um crédito para o valor total, você pode creditar o saldo do cliente para um valor que exclui a porcentagem de desconto à vista que o cliente obteve.</span><span class="sxs-lookup"><span data-stu-id="b8f61-107">Instead of providing a credit for the full amount, you can credit the customer's balance for an amount that excludes the cash discount percent that the customer took.</span></span> <span data-ttu-id="b8f61-108">Os parâmetros de pagamento estão localizados na página **Parâmetros de contas a receber**.</span><span class="sxs-lookup"><span data-stu-id="b8f61-108">The settlement parameters are located on the **Accounts receivable parameters** page.</span></span>

## <a name="invoice-and-credit-note"></a><span data-ttu-id="b8f61-109">Fatura e nota de crédito</span><span class="sxs-lookup"><span data-stu-id="b8f61-109">Invoice and credit note</span></span>
<span data-ttu-id="b8f61-110">O cliente 4035 possui uma fatura de 1.000,00 e uma nota de crédito de 100,00.</span><span class="sxs-lookup"><span data-stu-id="b8f61-110">Customer 4035 has an invoice for 1,000.00 and a credit note for 100.00.</span></span> <span data-ttu-id="b8f61-111">Cada documento terá um desconto de 1%, se for pago em 14 dias.</span><span class="sxs-lookup"><span data-stu-id="b8f61-111">Each document has a 1 percent discount if it's paid in 14 days.</span></span> <span data-ttu-id="b8f61-112">Arnie pode exibir as informações na página **Transações do cliente**.</span><span class="sxs-lookup"><span data-stu-id="b8f61-112">Arnie can view this information on the **Customer transactions** page.</span></span>

| <span data-ttu-id="b8f61-113">Comprovante</span><span class="sxs-lookup"><span data-stu-id="b8f61-113">Voucher</span></span>    | <span data-ttu-id="b8f61-114">Tipo de transação</span><span class="sxs-lookup"><span data-stu-id="b8f61-114">Transaction type</span></span> | <span data-ttu-id="b8f61-115">Data</span><span class="sxs-lookup"><span data-stu-id="b8f61-115">Date</span></span>      | <span data-ttu-id="b8f61-116">Fatura</span><span class="sxs-lookup"><span data-stu-id="b8f61-116">Invoice</span></span>  | <span data-ttu-id="b8f61-117">Valor em débito na moeda da transação</span><span class="sxs-lookup"><span data-stu-id="b8f61-117">Amount in transaction currency debit</span></span> | <span data-ttu-id="b8f61-118">Valor em crédito na moeda da transação</span><span class="sxs-lookup"><span data-stu-id="b8f61-118">Amount in transaction currency credit</span></span> | <span data-ttu-id="b8f61-119">Saldo</span><span class="sxs-lookup"><span data-stu-id="b8f61-119">Balance</span></span>  | <span data-ttu-id="b8f61-120">Moeda</span><span class="sxs-lookup"><span data-stu-id="b8f61-120">Currency</span></span> |
|------------|------------------|-----------|----------|--------------------------------------|---------------------------------------|----------|----------|
| <span data-ttu-id="b8f61-121">FTI-10050</span><span class="sxs-lookup"><span data-stu-id="b8f61-121">FTI-10050</span></span>  | <span data-ttu-id="b8f61-122">Fatura</span><span class="sxs-lookup"><span data-stu-id="b8f61-122">Invoice</span></span>          | <span data-ttu-id="b8f61-123">28/6/2015</span><span class="sxs-lookup"><span data-stu-id="b8f61-123">6/28/2015</span></span> | <span data-ttu-id="b8f61-124">10050</span><span class="sxs-lookup"><span data-stu-id="b8f61-124">10050</span></span>    | <span data-ttu-id="b8f61-125">1.000,00</span><span class="sxs-lookup"><span data-stu-id="b8f61-125">1,000.00</span></span>                             |                                       | <span data-ttu-id="b8f61-126">1.000,00</span><span class="sxs-lookup"><span data-stu-id="b8f61-126">1,000.00</span></span> | <span data-ttu-id="b8f61-127">USD</span><span class="sxs-lookup"><span data-stu-id="b8f61-127">USD</span></span>      |
| <span data-ttu-id="b8f61-128">CCRN-10050</span><span class="sxs-lookup"><span data-stu-id="b8f61-128">CCRN-10050</span></span> | <span data-ttu-id="b8f61-129">Nota de crédito</span><span class="sxs-lookup"><span data-stu-id="b8f61-129">Credit note</span></span>      | <span data-ttu-id="b8f61-130">28/6/2015</span><span class="sxs-lookup"><span data-stu-id="b8f61-130">6/28/2015</span></span> | <span data-ttu-id="b8f61-131">CR-10050</span><span class="sxs-lookup"><span data-stu-id="b8f61-131">CR-10050</span></span> |                                      | <span data-ttu-id="b8f61-132">100,00</span><span class="sxs-lookup"><span data-stu-id="b8f61-132">100.00</span></span>                                | <span data-ttu-id="b8f61-133">-100,00</span><span class="sxs-lookup"><span data-stu-id="b8f61-133">-100.00</span></span>  | <span data-ttu-id="b8f61-134">USD</span><span class="sxs-lookup"><span data-stu-id="b8f61-134">USD</span></span>      |

## <a name="settle-a-credit-note-with-an-invoice"></a><span data-ttu-id="b8f61-135">Liquidar uma nota de crédito com uma fatura</span><span class="sxs-lookup"><span data-stu-id="b8f61-135">Settle a credit note with an invoice</span></span>
<span data-ttu-id="b8f61-136">Na página **Transações do cliente**, Arnie abre a página **Liquidar transações**.</span><span class="sxs-lookup"><span data-stu-id="b8f61-136">From the **Customer transactions** page, Arnie opens the **Settle transactions** page.</span></span> <span data-ttu-id="b8f61-137">Ele pode usa a página **Liquidar transações** para liquidar a fatura e a nota de crédito.</span><span class="sxs-lookup"><span data-stu-id="b8f61-137">He can use the **Settle transactions** page to settle the invoice and credit note.</span></span> <span data-ttu-id="b8f61-138">Como parte do processo de liquidação ele exibe as datas e os valores de desconto à vista.</span><span class="sxs-lookup"><span data-stu-id="b8f61-138">As part of the settlement process, he views the cash discount dates and amounts.</span></span> <span data-ttu-id="b8f61-139">Ele marca os dois documentos e clica em **Lançar** para liquidar as transações.</span><span class="sxs-lookup"><span data-stu-id="b8f61-139">He marks the two documents and then clicks **Post** to settle the transactions.</span></span> <span data-ttu-id="b8f61-140">Há um desconto de -1,00 na nota de crédito, pois a Fabrikam permite descontos em notas de crédito.</span><span class="sxs-lookup"><span data-stu-id="b8f61-140">There is a discount of -1.00 on the credit note, because Fabrikam allows for discounts on credit notes.</span></span>

| <span data-ttu-id="b8f61-141">Marcar</span><span class="sxs-lookup"><span data-stu-id="b8f61-141">Mark</span></span>     | <span data-ttu-id="b8f61-142">Usar desconto à vista</span><span class="sxs-lookup"><span data-stu-id="b8f61-142">Use cash discount</span></span> | <span data-ttu-id="b8f61-143">Comprovante</span><span class="sxs-lookup"><span data-stu-id="b8f61-143">Voucher</span></span>    | <span data-ttu-id="b8f61-144">Conta</span><span class="sxs-lookup"><span data-stu-id="b8f61-144">Account</span></span> | <span data-ttu-id="b8f61-145">Data</span><span class="sxs-lookup"><span data-stu-id="b8f61-145">Date</span></span>      | <span data-ttu-id="b8f61-146">Data de conclusão</span><span class="sxs-lookup"><span data-stu-id="b8f61-146">Due date</span></span>  | <span data-ttu-id="b8f61-147">Fatura</span><span class="sxs-lookup"><span data-stu-id="b8f61-147">Invoice</span></span>  | <span data-ttu-id="b8f61-148">Valor na moeda da transação</span><span class="sxs-lookup"><span data-stu-id="b8f61-148">Amount in transaction currency</span></span> | <span data-ttu-id="b8f61-149">Moeda</span><span class="sxs-lookup"><span data-stu-id="b8f61-149">Currency</span></span> | <span data-ttu-id="b8f61-150">Valor para liquidar</span><span class="sxs-lookup"><span data-stu-id="b8f61-150">Amount to settle</span></span> |
|----------|-------------------|------------|---------|-----------|-----------|----------|--------------------------------|----------|------------------|
| <span data-ttu-id="b8f61-151">Selecionada</span><span class="sxs-lookup"><span data-stu-id="b8f61-151">Selected</span></span> | <span data-ttu-id="b8f61-152">Normal</span><span class="sxs-lookup"><span data-stu-id="b8f61-152">Normal</span></span>            | <span data-ttu-id="b8f61-153">FTI-10050</span><span class="sxs-lookup"><span data-stu-id="b8f61-153">FTI-10050</span></span>  | <span data-ttu-id="b8f61-154">4035</span><span class="sxs-lookup"><span data-stu-id="b8f61-154">4035</span></span>    | <span data-ttu-id="b8f61-155">28/6/2015</span><span class="sxs-lookup"><span data-stu-id="b8f61-155">6/28/2015</span></span> | <span data-ttu-id="b8f61-156">28/7/2015</span><span class="sxs-lookup"><span data-stu-id="b8f61-156">7/28/2015</span></span> | <span data-ttu-id="b8f61-157">10050</span><span class="sxs-lookup"><span data-stu-id="b8f61-157">10050</span></span>    | <span data-ttu-id="b8f61-158">1.000,00</span><span class="sxs-lookup"><span data-stu-id="b8f61-158">1,000.00</span></span>                       | <span data-ttu-id="b8f61-159">USD</span><span class="sxs-lookup"><span data-stu-id="b8f61-159">USD</span></span>      | <span data-ttu-id="b8f61-160">990,00</span><span class="sxs-lookup"><span data-stu-id="b8f61-160">990.00</span></span>           |
| <span data-ttu-id="b8f61-161">Selecionado</span><span class="sxs-lookup"><span data-stu-id="b8f61-161">Selected</span></span> | <span data-ttu-id="b8f61-162">Normal</span><span class="sxs-lookup"><span data-stu-id="b8f61-162">Normal</span></span>            | <span data-ttu-id="b8f61-163">CCRN-10050</span><span class="sxs-lookup"><span data-stu-id="b8f61-163">CCRN-10050</span></span> | <span data-ttu-id="b8f61-164">4035</span><span class="sxs-lookup"><span data-stu-id="b8f61-164">4035</span></span>    | <span data-ttu-id="b8f61-165">28/6/2015</span><span class="sxs-lookup"><span data-stu-id="b8f61-165">6/28/2015</span></span> | <span data-ttu-id="b8f61-166">28/7/2015</span><span class="sxs-lookup"><span data-stu-id="b8f61-166">7/28/2015</span></span> | <span data-ttu-id="b8f61-167">CR-10050</span><span class="sxs-lookup"><span data-stu-id="b8f61-167">CR-10050</span></span> | <span data-ttu-id="b8f61-168">-100,00</span><span class="sxs-lookup"><span data-stu-id="b8f61-168">-100.00</span></span>                        | <span data-ttu-id="b8f61-169">USD</span><span class="sxs-lookup"><span data-stu-id="b8f61-169">USD</span></span>      | <span data-ttu-id="b8f61-170">-99,00</span><span class="sxs-lookup"><span data-stu-id="b8f61-170">-99.00</span></span>           |

<span data-ttu-id="b8f61-171">As informações do desconto aparecem na parte inferior da página **Liquidar transações**.</span><span class="sxs-lookup"><span data-stu-id="b8f61-171">Discount information appears at the bottom of the **Settle transactions** page.</span></span>

|                              |           |
|------------------------------|-----------|
| <span data-ttu-id="b8f61-172">Data do desconto à vista</span><span class="sxs-lookup"><span data-stu-id="b8f61-172">Cash discount date</span></span>           | <span data-ttu-id="b8f61-173">12/7/2015</span><span class="sxs-lookup"><span data-stu-id="b8f61-173">7/12/2015</span></span> |
| <span data-ttu-id="b8f61-174">Valor de desconto à vista</span><span class="sxs-lookup"><span data-stu-id="b8f61-174">Cash discount amount</span></span>         | <span data-ttu-id="b8f61-175">-1.00</span><span class="sxs-lookup"><span data-stu-id="b8f61-175">-1.00</span></span>     |
| <span data-ttu-id="b8f61-176">Usar desconto à vista</span><span class="sxs-lookup"><span data-stu-id="b8f61-176">Use cash discount</span></span>            | <span data-ttu-id="b8f61-177">Normal</span><span class="sxs-lookup"><span data-stu-id="b8f61-177">Normal</span></span>    |
| <span data-ttu-id="b8f61-178">Desconto à vista obtido</span><span class="sxs-lookup"><span data-stu-id="b8f61-178">Cash discount taken</span></span>          | <span data-ttu-id="b8f61-179">0,00</span><span class="sxs-lookup"><span data-stu-id="b8f61-179">0.00</span></span>      |
| <span data-ttu-id="b8f61-180">Valor do desconto à vista a ser obtido</span><span class="sxs-lookup"><span data-stu-id="b8f61-180">Cash discount amount to take</span></span> | <span data-ttu-id="b8f61-181">-1.00</span><span class="sxs-lookup"><span data-stu-id="b8f61-181">-1.00</span></span>     |

<span data-ttu-id="b8f61-182">A liquidação será de 100,00 e incluirá um pagamento de 99,00 e um desconto de 1,00.</span><span class="sxs-lookup"><span data-stu-id="b8f61-182">The settlement will be 100.00, and will include a payment of 99.00 and a discount of 1.00.</span></span>


