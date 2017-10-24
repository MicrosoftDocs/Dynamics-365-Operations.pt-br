---
title: Pagamentos de fornecedor de uma quantidade parcial
description: "Algumas vezes, você pode fazer um pagamento para um fornecedor que seja menor do que o valor de uma fatura. Este artigo descreve as diversas opções para controlar essa situação. As opções disponíveis dependerão dos seus requisitos empresariais e da sua configuração."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/22/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: LedgerJournalTransVendPaym, VendOpenTrans
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 14321
ms.assetid: 9a17075e-5325-4d55-a1e5-1791b8c460a0
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 4cc8e2864343b5e9fee8eaf058a51360d15e425a
ms.contentlocale: pt-br
ms.lasthandoff: 09/29/2017

---

# <a name="vendor-payments-for-a-partial-amount"></a><span data-ttu-id="2af1e-105">Pagamentos de fornecedor de uma quantidade parcial</span><span class="sxs-lookup"><span data-stu-id="2af1e-105">Vendor payments for a partial amount</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="2af1e-106">Algumas vezes, você pode fazer um pagamento para um fornecedor que seja menor do que o valor de uma fatura.</span><span class="sxs-lookup"><span data-stu-id="2af1e-106">Sometimes, you might make a payment to a vendor that is less than the amount of an invoice.</span></span> <span data-ttu-id="2af1e-107">Este artigo descreve as diversas opções para controlar essa situação.</span><span class="sxs-lookup"><span data-stu-id="2af1e-107">This article describes the various options for handling this situation.</span></span> <span data-ttu-id="2af1e-108">As opções disponíveis dependerão dos seus requisitos empresariais e da sua configuração.</span><span class="sxs-lookup"><span data-stu-id="2af1e-108">The options that are available to you depend on your business requirements and configuration.</span></span> 

<a name="cash-discount-amounts"></a><span data-ttu-id="2af1e-109">Valores de desconto à vista</span><span class="sxs-lookup"><span data-stu-id="2af1e-109">Cash discount amounts</span></span>
---------------------

<span data-ttu-id="2af1e-110">Um fornecedor poderá oferecer um desconto à vista quando você pagar uma fatura antes da data de vencimento.</span><span class="sxs-lookup"><span data-stu-id="2af1e-110">A vendor can offer you a cash discount for paying an invoice before the due date.</span></span> <span data-ttu-id="2af1e-111">Por exemplo, você insere uma fatura de 100,00 que especifica um desconto à vista de 2% caso a fatura seja paga em 10 dias.</span><span class="sxs-lookup"><span data-stu-id="2af1e-111">For example, you enter an invoice for 100.00 that specifies a 2-percent cash discount if the invoice is paid within 10 days.</span></span> <span data-ttu-id="2af1e-112">As condições da data de vencimento serão de 30 dias.</span><span class="sxs-lookup"><span data-stu-id="2af1e-112">The due date terms are 30 days.</span></span> <span data-ttu-id="2af1e-113">Se uma proposta de pagamento usa o desconto de caixa como critério para selecionar uma fatura e se a proposta é executada na data de desconto ou antes dela, a fatura é selecionada para pagamento e o pagamento é criado por 98,00.</span><span class="sxs-lookup"><span data-stu-id="2af1e-113">If a payment proposal uses the cash discount as a criterion for selecting an invoice, and if the proposal is run on or before the cash discount date, the invoice is selected for payment, and the payment is created for 98.00.</span></span> <span data-ttu-id="2af1e-114">Um desconto de dinheiro também pode ser tomado para um pagamento único que foi criado manualmente.</span><span class="sxs-lookup"><span data-stu-id="2af1e-114">A cash discount can also be taken for a one-off payment that was created manually.</span></span>

## <a name="partial-payments-with-cash-discounts"></a><span data-ttu-id="2af1e-115">Pagamentos parciais com descontos à vista</span><span class="sxs-lookup"><span data-stu-id="2af1e-115">Partial payments with cash discounts</span></span>
<span data-ttu-id="2af1e-116">Quando você faz um pagamento parcial, talvez planeje fazer um pagamento parcial adicional para liquidar completamente a fatura.</span><span class="sxs-lookup"><span data-stu-id="2af1e-116">When you make a partial payment, you might plan to make an additional partial payment to fully settle the invoice.</span></span> <span data-ttu-id="2af1e-117">Para receber um desconto de pagamento parcial, você deve definir a opção **Calcular descontos em dinheiro para pagamentos parciais** para **Sim** na página **Parâmetros de contas a pagar**.</span><span class="sxs-lookup"><span data-stu-id="2af1e-117">To take a cash discount for a partial payment, you must set the **Calculate cash discounts for partial payments **option to **Yes** on the **Account payable parameters** page.</span></span> 

<span data-ttu-id="2af1e-118">Por exemplo, você recebe um desconto à vista de 2% caso a fatura seja paga em até 10 dias após a emissão.</span><span class="sxs-lookup"><span data-stu-id="2af1e-118">For example, you receive a 2-percent cash discount if the invoice is paid within 10 days after it's issued.</span></span> <span data-ttu-id="2af1e-119">Uma fatura é lançada para 100,00.</span><span class="sxs-lookup"><span data-stu-id="2af1e-119">An invoice is posted for 100.00.</span></span> <span data-ttu-id="2af1e-120">Se você fizer um pagamento de 49,00 dentro de 10 dias, vai inserir um débito de 49,00 em um diário de pagamento.</span><span class="sxs-lookup"><span data-stu-id="2af1e-120">If you make a payment of 49.00 within 10 days, you enter a debit of 49.00 in a payment journal.</span></span> <span data-ttu-id="2af1e-121">Quando você liquida o pagamento parcial na página **Liquidar transações abertas**, **1,00** aparecerá no campo **Valor do desconto à vista a ser obtido**.</span><span class="sxs-lookup"><span data-stu-id="2af1e-121">When you settle the partial payment on the **Settle open transactions** page, **1.00** appears in the **Cash discount amount to take** field.</span></span> 

> [!NOTE] 
> <span data-ttu-id="2af1e-122">Se você inserir um pagamento parcial e deixar o valor total da fatura no campo **Valor para liquidar**, o campo **Valor do desconto à vista** a ser obtido será automaticamente recalculado quando as transações forem lançadas.</span><span class="sxs-lookup"><span data-stu-id="2af1e-122">If you enter a partial payment and leave the full invoice amount in the **Amount to settle** field, the **Cash discount amount to take** field is automatically recalculated when you post the transactions.</span></span>

## <a name="credit-notes-with-cash-discounts"></a><span data-ttu-id="2af1e-123">Notas de crédito com descontos à vista</span><span class="sxs-lookup"><span data-stu-id="2af1e-123">Credit notes with cash discounts</span></span>
<span data-ttu-id="2af1e-124">Você poderia devolver alguns dos itens em uma fatura e receberia uma nota de crédito.</span><span class="sxs-lookup"><span data-stu-id="2af1e-124">You might return some of the items on an invoice and receive a credit note.</span></span> <span data-ttu-id="2af1e-125">Se um desconto à vista tiver sido retirado da fatura original, você poderá subtrair o valor do desconto e receber um reembolso do valor correto.</span><span class="sxs-lookup"><span data-stu-id="2af1e-125">If a cash discount was taken on the original invoice, you can subtract the value of the discount and receive a refund for the correct amount.</span></span> <span data-ttu-id="2af1e-126">Se a opção **Calcular descontos em dinheiro para notas de crédito** estiver definida como **Sim** na página **Parâmetros de contas a pagar**, o desconto é calculado automaticamente para a nota de crédito.</span><span class="sxs-lookup"><span data-stu-id="2af1e-126">If the **Calculate cash discounts for credit notes **option is set to **Yes** on the **Accounts payable parameters** page, the discount is automatically calculated for the credit note.</span></span> 

<span data-ttu-id="2af1e-127">Por exemplo, você recebe um desconto à vista de 2% caso a fatura seja paga em até 10 dias após a emissão.</span><span class="sxs-lookup"><span data-stu-id="2af1e-127">For example, you receive a 2-percent cash discount if the invoice is paid within 10 days after it's issued.</span></span> <span data-ttu-id="2af1e-128">Uma fatura de 100,00 é lançada.</span><span class="sxs-lookup"><span data-stu-id="2af1e-128">An invoice for 100.00 is posted.</span></span> <span data-ttu-id="2af1e-129">Se você devolver a mercadoria e receber uma nota de crédito, poderá inserir a nota de crédito para o valor total da fatura original, 100,00, juntamente com o desconto de 2% que também é definido na nota de crédito.</span><span class="sxs-lookup"><span data-stu-id="2af1e-129">If you return the goods and receive a credit note, you can enter the credit note for the full amount of the original invoice, 100.00, together with the 2-percent cash discount that is also defined on the credit memo.</span></span>  <span data-ttu-id="2af1e-130">Quando você exibe a nota de crédito na página **Liquidar transações**,**98,00** aparece no campo **Valor para liquidar** e **-2,00** aparece no campo **Valor do desconto à vista**.</span><span class="sxs-lookup"><span data-stu-id="2af1e-130">When you view the credit note on the **Settle transactions** page, **98.00** appears in the **Amount to settle** field, and **-2.00** appears in the **Cash discount amount** field.</span></span> <span data-ttu-id="2af1e-131">O valor do desconto é lançado em uma conta de desconto à vista.</span><span class="sxs-lookup"><span data-stu-id="2af1e-131">The discount amount is posted to a cash discount account.</span></span>

## <a name="overpaymentunderpayment-amounts"></a><span data-ttu-id="2af1e-132">Valores de pagamento a maior/a menor</span><span class="sxs-lookup"><span data-stu-id="2af1e-132">Overpayment/underpayment amounts</span></span>
<span data-ttu-id="2af1e-133">Você pode fazer um pagamento parcial em que o valor a ser liquidado é muito pequeno.</span><span class="sxs-lookup"><span data-stu-id="2af1e-133">You might make a partial payment where the amount that must still be settled is very small.</span></span> <span data-ttu-id="2af1e-134">Por exemplo, a fatura de fornecedor é de 1.000,00 e você paga 999,90.</span><span class="sxs-lookup"><span data-stu-id="2af1e-134">For example, the vendor invoice is for 1,000.00, and you pay 999.90.</span></span> <span data-ttu-id="2af1e-135">Se o valor restante for menor do que o valor especificado para pagamentos a maior ou para pagamentos a menor na página **Parâmetros de contas a pagar**, a diferença será automaticamente lançada em uma conta conta contábil de pagamento a maior/a menor.</span><span class="sxs-lookup"><span data-stu-id="2af1e-135">If the remaining amount is less than the amount that is specified for overpayments or underpayments on the **Accounts payable parameters** page, the difference is automatically posted to an overpayment/underpayment ledger account.</span></span>


<span data-ttu-id="2af1e-136">Para saber mais, consulte [Visão geral de pagamentos a fornecedores](../cash-bank-management/tasks/vendor-payment-overview.md).</span><span class="sxs-lookup"><span data-stu-id="2af1e-136">For more information, see [Vendor payment overview](../cash-bank-management/tasks/vendor-payment-overview.md).</span></span>

