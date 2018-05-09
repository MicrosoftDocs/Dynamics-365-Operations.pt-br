---
title: Obtenha um desconto maior do que o desconto calculado para um pagamento de fornecedor
description: "Este artigo percorre um cenário onde um desconto à vista é dado para um valor maior do que o desconto originalmente disponível na fatura. Esse cenário que pode ocorrer se uma organização firmar um contrato com o fornecedor para pagar um valor menor na fatura."
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
ms.search.scope: Core, Operations
ms.custom: 14281
ms.assetid: 7f0a4197-95dd-4969-ade9-154815cf659e
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 312da8a3a83335fbdded0509fd3e33cb1f19cdc3
ms.contentlocale: pt-br
ms.lasthandoff: 05/08/2018

---

# <a name="take-a-discount-that-is-more-than-the-calculated-discount-for-a-vendor-payment"></a><span data-ttu-id="6f3b4-104">Obtenha um desconto maior do que o desconto calculado para um pagamento de fornecedor</span><span class="sxs-lookup"><span data-stu-id="6f3b4-104">Take a discount that is more than the calculated discount for a vendor payment</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="6f3b4-105">Este artigo percorre um cenário onde um desconto à vista é dado para um valor maior do que o desconto originalmente disponível na fatura.</span><span class="sxs-lookup"><span data-stu-id="6f3b4-105">This article walks you through a scenario where a cash discount is taken for an amount that is more than the discount that was originally available on the invoice.</span></span> <span data-ttu-id="6f3b4-106">Esse cenário que pode ocorrer se uma organização firmar um contrato com o fornecedor para pagar um valor menor na fatura.</span><span class="sxs-lookup"><span data-stu-id="6f3b4-106">This scenario might occur if an organization comes to an agreement with the vendor to pay a smaller amount on the invoice.</span></span> 

<span data-ttu-id="6f3b4-107">O fornecedor 3051 oferece à Fabrikam um desconto à vista de 4% se uma fatura for paga em sete dias.</span><span class="sxs-lookup"><span data-stu-id="6f3b4-107">Vendor 3051 gives Fabrikam a cash discount of 4 percent if an invoice is paid in seven days.</span></span> <span data-ttu-id="6f3b4-108">Em 29 de junho, Amanda insere uma fatura de 1.000,00.</span><span class="sxs-lookup"><span data-stu-id="6f3b4-108">On June 29, April enters an invoice for 1,000.00.</span></span> <span data-ttu-id="6f3b4-109">O fornecedor deixa Amanda obter um desconto de 60,00 em vez de o desconto padrão de 40,00 disponível para a fatura.</span><span class="sxs-lookup"><span data-stu-id="6f3b4-109">The vendor lets April take a discount of 60.00 instead of the default discount of 40.00 that is available for the invoice.</span></span> <span data-ttu-id="6f3b4-110">Amanda registra um pagamento único usando o diário de pagamentos Contas a pagar.</span><span class="sxs-lookup"><span data-stu-id="6f3b4-110">April records a one-off payment by using the Accounts payable payment journal.</span></span> <span data-ttu-id="6f3b4-111">Ela entra no fornecedor para o pagamento e abre a página **Liquidar transações**.</span><span class="sxs-lookup"><span data-stu-id="6f3b4-111">She enters the vendor for the payment and then opens the **Settle transactions** page.</span></span> <span data-ttu-id="6f3b4-112">Ela marca a fatura e altera o valor no campo **Valor do desconto à vista** para **60,00**.</span><span class="sxs-lookup"><span data-stu-id="6f3b4-112">She marks the invoice and changes the value in the **Cash discount amount** field to **60.00**.</span></span>

| <span data-ttu-id="6f3b4-113">Marcar</span><span class="sxs-lookup"><span data-stu-id="6f3b4-113">Mark</span></span>     | <span data-ttu-id="6f3b4-114">Usar desconto à vista</span><span class="sxs-lookup"><span data-stu-id="6f3b4-114">Use cash discount</span></span> | <span data-ttu-id="6f3b4-115">Comprovante</span><span class="sxs-lookup"><span data-stu-id="6f3b4-115">Voucher</span></span>   | <span data-ttu-id="6f3b4-116">Conta</span><span class="sxs-lookup"><span data-stu-id="6f3b4-116">Account</span></span> | <span data-ttu-id="6f3b4-117">Data</span><span class="sxs-lookup"><span data-stu-id="6f3b4-117">Date</span></span>      | <span data-ttu-id="6f3b4-118">Data de conclusão</span><span class="sxs-lookup"><span data-stu-id="6f3b4-118">Due date</span></span>  | <span data-ttu-id="6f3b4-119">Fatura</span><span class="sxs-lookup"><span data-stu-id="6f3b4-119">Invoice</span></span> | <span data-ttu-id="6f3b4-120">Valor na moeda da transação</span><span class="sxs-lookup"><span data-stu-id="6f3b4-120">Amount in transaction currency</span></span> | <span data-ttu-id="6f3b4-121">Moeda</span><span class="sxs-lookup"><span data-stu-id="6f3b4-121">Currency</span></span> | <span data-ttu-id="6f3b4-122">Valor para liquidar</span><span class="sxs-lookup"><span data-stu-id="6f3b4-122">Amount to settle</span></span> |
|----------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------|----------|------------------|
| <span data-ttu-id="6f3b4-123">Selecionada</span><span class="sxs-lookup"><span data-stu-id="6f3b4-123">Selected</span></span> | <span data-ttu-id="6f3b4-124">Normal</span><span class="sxs-lookup"><span data-stu-id="6f3b4-124">Normal</span></span>            | <span data-ttu-id="6f3b4-125">Inv-10040</span><span class="sxs-lookup"><span data-stu-id="6f3b4-125">Inv-10040</span></span> | <span data-ttu-id="6f3b4-126">3051</span><span class="sxs-lookup"><span data-stu-id="6f3b4-126">3051</span></span>    | <span data-ttu-id="6f3b4-127">29/6/2015</span><span class="sxs-lookup"><span data-stu-id="6f3b4-127">6/29/2015</span></span> | <span data-ttu-id="6f3b4-128">29/7/2015</span><span class="sxs-lookup"><span data-stu-id="6f3b4-128">7/29/2015</span></span> | <span data-ttu-id="6f3b4-129">10040</span><span class="sxs-lookup"><span data-stu-id="6f3b4-129">10040</span></span>   | <span data-ttu-id="6f3b4-130">1.000,00</span><span class="sxs-lookup"><span data-stu-id="6f3b4-130">1,000.00</span></span>                       | <span data-ttu-id="6f3b4-131">USD</span><span class="sxs-lookup"><span data-stu-id="6f3b4-131">USD</span></span>      | <span data-ttu-id="6f3b4-132">940,00</span><span class="sxs-lookup"><span data-stu-id="6f3b4-132">940.00</span></span>           |

<span data-ttu-id="6f3b4-133">As informações do desconto aparecem na parte inferior da página **Liquidar transações**.</span><span class="sxs-lookup"><span data-stu-id="6f3b4-133">Discount information appears at the bottom of the **Settle transactions** page.</span></span>

|                              |           |
|------------------------------|-----------|
| <span data-ttu-id="6f3b4-134">Data do desconto à vista</span><span class="sxs-lookup"><span data-stu-id="6f3b4-134">Cash discount date</span></span>           | <span data-ttu-id="6f3b4-135">12/7/2015</span><span class="sxs-lookup"><span data-stu-id="6f3b4-135">7/12/2015</span></span> |
| <span data-ttu-id="6f3b4-136">Valor de desconto à vista</span><span class="sxs-lookup"><span data-stu-id="6f3b4-136">Cash discount amount</span></span>         | <span data-ttu-id="6f3b4-137">60,00</span><span class="sxs-lookup"><span data-stu-id="6f3b4-137">60.00</span></span>     |
| <span data-ttu-id="6f3b4-138">Usar desconto à vista</span><span class="sxs-lookup"><span data-stu-id="6f3b4-138">Use cash discount</span></span>            | <span data-ttu-id="6f3b4-139">Normal</span><span class="sxs-lookup"><span data-stu-id="6f3b4-139">Normal</span></span>    |
| <span data-ttu-id="6f3b4-140">Desconto à vista obtido</span><span class="sxs-lookup"><span data-stu-id="6f3b4-140">Cash discount taken</span></span>          | <span data-ttu-id="6f3b4-141">0,00</span><span class="sxs-lookup"><span data-stu-id="6f3b4-141">0.00</span></span>      |
| <span data-ttu-id="6f3b4-142">Valor do desconto à vista a ser obtido</span><span class="sxs-lookup"><span data-stu-id="6f3b4-142">Cash discount amount to take</span></span> | <span data-ttu-id="6f3b4-143">60,00</span><span class="sxs-lookup"><span data-stu-id="6f3b4-143">60.00</span></span>     |

<span data-ttu-id="6f3b4-144">Amanda lança o diário de pagamentos.</span><span class="sxs-lookup"><span data-stu-id="6f3b4-144">April posts the payment journal.</span></span> <span data-ttu-id="6f3b4-145">A fatura é totalmente liquidada usando um pagamento de 940,00 e um desconto de 60,00.</span><span class="sxs-lookup"><span data-stu-id="6f3b4-145">The invoice is fully settled by using a payment of 940.00 and a discount of 60.00.</span></span>




