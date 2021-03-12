---
title: Descontos à vista
description: Os descontos à vista são configurados compartilhados para contas a pagar e contas a receber.  O desconto à vista disponível pode ser definido na nota fiscal do cliente ou na nota fiscal de fornecedor, e será usado se a nota fiscal for paga na data do desconto à vista.
author: kweekley
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CashDisc
audience: Application User
ms.reviewer: roschlom
ms.custom: 3741
ms.assetid: c25f9d85-2702-46aa-8e61-0b4886e069b3
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 9d4f6d5bdf4f2fdc4529d9f51515ed2ac4b5b3b5
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4985303"
---
# <a name="cash-discounts"></a><span data-ttu-id="cf77e-104">Descontos à vista</span><span class="sxs-lookup"><span data-stu-id="cf77e-104">Cash discounts</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="cf77e-105">Os descontos à vista são configurados compartilhados para contas a pagar e contas a receber.</span><span class="sxs-lookup"><span data-stu-id="cf77e-105">Cash discounts are setup and shared for Accounts payable and Accounts receivable.</span></span>  <span data-ttu-id="cf77e-106">O desconto à vista disponível pode ser definido na nota fiscal do cliente ou na nota fiscal de fornecedor, e será usado se a nota fiscal for paga na data do desconto à vista.</span><span class="sxs-lookup"><span data-stu-id="cf77e-106">The cash discount available can be defined on the customer invoice or vendor invoice, and will be taken if the invoice is paid within the cash discount date.</span></span> 

## <a name="cash-discounts"></a><span data-ttu-id="cf77e-107">Descontos à vista</span><span class="sxs-lookup"><span data-stu-id="cf77e-107">Cash discounts</span></span>

<span data-ttu-id="cf77e-108">Os descontos à vista para clientes ou fornecedores podem ser criados na página Descontos à vista.</span><span class="sxs-lookup"><span data-stu-id="cf77e-108">Cash discounts for both customers or vendors can be created in the Cash discounts page.</span></span> <span data-ttu-id="cf77e-109">Você pode definir, usando o campo Próximo código de desconto, uma série de descontos à vista que se sucedem à medida que as datas de vencimento de desconto à vista anteriores se aproxima.</span><span class="sxs-lookup"><span data-stu-id="cf77e-109">You can also define, by using the Next discount code field, a series of cash discounts that succeed each other as previous cash discount dates expire.</span></span> <span data-ttu-id="cf77e-110">Para obter mais informações, consulte “exemplo: série de descontos à vista” posteriormente neste tópico.</span><span class="sxs-lookup"><span data-stu-id="cf77e-110">For more information, see “Example: Series of cash discounts” later in this topic.</span></span> <span data-ttu-id="cf77e-111">Se a fatura, a transação de crédito (um pagamento ou uma nota de crédito), ou ambos forem inseridos em uma moeda diferente da moeda contábil da entidade legal, o desconto à vista é calculado usando a taxa de câmbio baseada na data de pagamento ou nota de crédito.</span><span class="sxs-lookup"><span data-stu-id="cf77e-111">If the invoice, credit transaction (either a payment or a credit note), or both are entered in a currency other than the accounting currency of the legal entity, the cash discount is calculated using the exchange rate based on the date of the payment or credit note.</span></span> <span data-ttu-id="cf77e-112">Se a fatura e o documento de crédito forem inseridos em pessoas jurídicas diferentes, e se as moedas contábeis para a pessoa jurídica forem diferentes, a taxa de câmbio será a mesma da pessoa jurídica da fatura, a partir da data do documento de crédito.</span><span class="sxs-lookup"><span data-stu-id="cf77e-112">If the invoice and credit document are entered in different legal entities, and if the accounting currencies for the legal entities differ, the exchange rate is taken from the legal entity of the invoice, as of the date of the credit document.</span></span> <span data-ttu-id="cf77e-113">Para obter mais informações, consulte “exemplo: taxas de câmbio para descontos à vista” posteriormente neste tópico.</span><span class="sxs-lookup"><span data-stu-id="cf77e-113">For more information, see “Example: Exchange rates for cash discounts” later in this topic.</span></span>

## <a name="defaulting-order-of-cash-discount-main-account"></a><span data-ttu-id="cf77e-114">Usando o padrão da ordem de conta principal do desconto à vista</span><span class="sxs-lookup"><span data-stu-id="cf77e-114">Defaulting order of cash discount main account</span></span>

<span data-ttu-id="cf77e-115">Se uma fatura é liquidada a tempo de obter um desconto à vista, o desconto é automaticamente lançado em uma conta principal de descontos à vista, de acordo com a seguinte prioridade padrão:</span><span class="sxs-lookup"><span data-stu-id="cf77e-115">If an invoice is settled in time to obtain a cash discount, the cash discount is automatically posted to a cash discount main account according to the following defaulting priority:</span></span>
1.  <span data-ttu-id="cf77e-116">A conta principal especificada no campo Conta de desconto à vista alternativa na página Liquidar transações em aberto do cliente ou na página Liquidar transações em aberto do fornecedor.</span><span class="sxs-lookup"><span data-stu-id="cf77e-116">The main account specified in the Alternative cash discount account field on the customer Settle open transactions page or the vendor Settle open transactions page.</span></span>
2.  <span data-ttu-id="cf77e-117">A conta principal que é especificada no campo Desconto à vista do cliente ou no campo Desconto à vista do fornecedor do grupo de lançamento do razão que é atribuído ao código de imposto sobre vendas da fatura.</span><span class="sxs-lookup"><span data-stu-id="cf77e-117">The main account specified in the Customer cash discount field or the Vendor cash discount field of the ledger posting group that is assigned to the sales tax code of the invoice.</span></span> <span data-ttu-id="cf77e-118">Configure grupos de lançamentos contáveis na página Grupos de lançamento contáveis e atribua-os aos códigos de imposto na página Códigos de imposto.</span><span class="sxs-lookup"><span data-stu-id="cf77e-118">Set up ledger posting groups on the Ledger posting groups page and assign them to sales tax codes in the Sales tax codes page.</span></span>
3.  <span data-ttu-id="cf77e-119">A conta de lançamento principal na página Descontos à vista no campo Conta principal para descontos do cliente ou no campo Conta principal para descontos de fornecedor para o código de desconto à vista que está presente na fatura liquidada.</span><span class="sxs-lookup"><span data-stu-id="cf77e-119">The main posting account on the Cash discounts page in either the Main account for customer discounts field or the Main account for vendor discounts field for the cash discount code that is on the settled invoice.</span></span>
4.  <span data-ttu-id="cf77e-120">Conta principal para descontos à vista, conforme definido na página Contas para transações automáticas.</span><span class="sxs-lookup"><span data-stu-id="cf77e-120">The main account for cash discounts, as defined in the Accounts for automatic transactions page.</span></span>

## <a name="example-series-of-cash-discounts"></a><span data-ttu-id="cf77e-121">Exemplo: série de descontos à vista</span><span class="sxs-lookup"><span data-stu-id="cf77e-121">Example: Series of cash discounts</span></span>
<span data-ttu-id="cf77e-122">Configure três códigos de desconto à vista, da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="cf77e-122">Set up three cash discount codes as follows:</span></span>
-   <span data-ttu-id="cf77e-123">Código 5D10% – um código de desconto à vista de 10% quando o valor é pago em 5 dias.</span><span class="sxs-lookup"><span data-stu-id="cf77e-123">Code 5D10% – A cash discount of 10% when the amount is paid within 5 days.</span></span>
-   <span data-ttu-id="cf77e-124">Código 10D5% – um desconto à vista de 5% quando o valor é pago em 10 dias.</span><span class="sxs-lookup"><span data-stu-id="cf77e-124">Code 10D5% – A cash discount of 5% when the amount is paid within 10 days.</span></span>
-   <span data-ttu-id="cf77e-125">Código 14D2% – um desconto à vista de 2% quando o valor é pago em 14 dias.</span><span class="sxs-lookup"><span data-stu-id="cf77e-125">Code 14D2% – A cash discount of 2% when the amount is paid within 14 days.</span></span>

<span data-ttu-id="cf77e-126">No campo Próximo do código de desconto:</span><span class="sxs-lookup"><span data-stu-id="cf77e-126">In the Next discount code field:</span></span>
-   <span data-ttu-id="cf77e-127">Para o código 5D10%, selecione 10D5%.</span><span class="sxs-lookup"><span data-stu-id="cf77e-127">For the 5D10% code, select 10D5%.</span></span>
-   <span data-ttu-id="cf77e-128">Para o código 10D5%, selecione 14D2%.</span><span class="sxs-lookup"><span data-stu-id="cf77e-128">For the 10D5% code, select 14D2%.</span></span>
-   <span data-ttu-id="cf77e-129">Para o código 14D2%, deixe o campo Próximo código de desconto em branco.</span><span class="sxs-lookup"><span data-stu-id="cf77e-129">For the 14D2% code, leave the Next discount code field blank.</span></span>

<span data-ttu-id="cf77e-130">Os três descontos à vista se sucedem conforme a data de pagamento excede a data anterior do desconto à vista na fatura.</span><span class="sxs-lookup"><span data-stu-id="cf77e-130">The three cash discounts succeed each other as the payment date exceeds the previous cash discount date on the invoice.</span></span> <span data-ttu-id="cf77e-131">Somente um desconto à vista é concedido quando a fatura é paga, com base na data do desconto à vista que é atendida na sequência de descontos à vista.</span><span class="sxs-lookup"><span data-stu-id="cf77e-131">Only one cash discount is granted when the invoice is paid, based on which cash discount date is meet in the sequence of cash discounts.</span></span>

## <a name="example-exchange-rates-for-cash-discounts"></a><span data-ttu-id="cf77e-132">Exemplo: taxas de câmbio para descontos à vista</span><span class="sxs-lookup"><span data-stu-id="cf77e-132">Example: Exchange rates for cash discounts</span></span>
<span data-ttu-id="cf77e-133">A moeda contábil da pessoa jurídica é USD e as seguintes taxas de câmbio são especificadas para BRL:</span><span class="sxs-lookup"><span data-stu-id="cf77e-133">Your legal entity’s accounting currency is EUR and the following exchange rates are specified for USD:</span></span>
-   <span data-ttu-id="cf77e-134">1 de fevereiro = 110</span><span class="sxs-lookup"><span data-stu-id="cf77e-134">February 1 = 110</span></span>
-   <span data-ttu-id="cf77e-135">1 de março = 80</span><span class="sxs-lookup"><span data-stu-id="cf77e-135">March 1 = 80</span></span>

<span data-ttu-id="cf77e-136">Uma fatura de US$ 1000 com base nas condições do desconto à vista de 20D2% é lançada o 15 de fevereiro.</span><span class="sxs-lookup"><span data-stu-id="cf77e-136">An invoice for 1000 USD with cash discount terms of 20D2% is posted on February 15.</span></span> <span data-ttu-id="cf77e-137">O valor da moeda contábil da fatura é de € 1100.</span><span class="sxs-lookup"><span data-stu-id="cf77e-137">The accounting currency amount of the invoice is 1100 EUR.</span></span> <span data-ttu-id="cf77e-138">Um pagamento de US$ 980 é liquidado com a fatura em 1 de março.</span><span class="sxs-lookup"><span data-stu-id="cf77e-138">A payment for 980 USD is settled with the invoice on March 1.</span></span> <span data-ttu-id="cf77e-139">O valor do desconto à vista é de US$ 20.</span><span class="sxs-lookup"><span data-stu-id="cf77e-139">The cash discount amount is 20 USD.</span></span> <span data-ttu-id="cf77e-140">O valor da moeda contábil de pagamento é de US$ 490,00.</span><span class="sxs-lookup"><span data-stu-id="cf77e-140">The accounting currency amount of the payment is 784 EUR.</span></span> <span data-ttu-id="cf77e-141">O valor da moeda contábil do desconto à vista é calculado usando a taxa de câmbio de 1 de março: 20 \* 80 / 100 = € 16.</span><span class="sxs-lookup"><span data-stu-id="cf77e-141">The accounting currency amount of the cash discount is calculated by using the exchange rate as of March 1: 20 \* 80 / 100 = 16 EUR.</span></span>

> [!NOTE]
> <span data-ttu-id="cf77e-142">Se a opção Calcular descontos à vista para pagamentos parciais for selecionada nas páginas Parâmetros de contas a receber ou Parâmetros de contas a pagar, a taxa de câmbio que está em vigor na data de cada pagamento parcial será utilizada.</span><span class="sxs-lookup"><span data-stu-id="cf77e-142">If the Calculate cash discounts for partial payments option is selected in the Accounts receivable parameters or Accounts payable parameters pages, the exchange rate that is in effect on the date of each partial payment is used.</span></span> 

