---
title: "Configuração, autorização, e captura de cartão de crédito"
description: "Este artigo fornece uma visão geral da autorização do cartão de crédito no Microsoft Dynamics 365 for Finance and Operations. Ele inclui informações sobre como configurar o serviço de pagamento, adicionar um cartão de crédito a uma ordem de venda e anular uma autorização."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/22/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CreditCardProcessors, CustTable, SalesTable
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations, Retail
ms.custom: 3041
ms.assetid: 678f6899-bfa5-439b-aaca-b4affcc338ba
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a0739304723d19b910388893d08e8c36a1f49d13
ms.openlocfilehash: 4a6354563fdebff901498f1cd6caed3aedae668b
ms.contentlocale: pt-br
ms.lasthandoff: 03/26/2018

---

# <a name="credit-card-setup-authorization-and-capture"></a><span data-ttu-id="88ccd-104">Configuração, autorização, e captura de cartão de crédito</span><span class="sxs-lookup"><span data-stu-id="88ccd-104">Credit card setup, authorization, and capture</span></span>

[!include[banner](../includes/banner.md)]

[!include[retail name](../includes/retail-name.md)]


<span data-ttu-id="88ccd-105">Este artigo fornece uma visão geral da autorização do cartão de crédito no Microsoft Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="88ccd-105">This article provides an overview of credit card authorization in Microsoft Dynamics 365 for Finance and Operations.</span></span> <span data-ttu-id="88ccd-106">Ele inclui informações sobre como configurar o serviço de pagamento, adicionar um cartão de crédito a uma ordem de venda e anular uma autorização.</span><span class="sxs-lookup"><span data-stu-id="88ccd-106">It includes information about how to set up a payment service, add a credit card to a sales order, and void an authorization.</span></span>

<a name="setting-up-the-credit-card-payment-service"></a><span data-ttu-id="88ccd-107">Configuração do serviço de pagamento com cartão de crédito</span><span class="sxs-lookup"><span data-stu-id="88ccd-107">Setting up the credit card payment service</span></span>
------------------------------------------

<span data-ttu-id="88ccd-108">Para usar cartões de crédito, você deve configurar e ativar um serviço de pagamento na página Serviços de pagamento.</span><span class="sxs-lookup"><span data-stu-id="88ccd-108">To use credit cards, you must set up and activate a payment service on the Payment services page.</span></span> <span data-ttu-id="88ccd-109">Um serviço de pagamento atua como uma ponte entre a entidade legal e o banco que processa encargos de cartão de crédito de um cliente.</span><span class="sxs-lookup"><span data-stu-id="88ccd-109">A payment service acts as a bridge between your legal entity and the bank that processes a customer's credit card charges.</span></span> <span data-ttu-id="88ccd-110">Você deve trabalhar com um provedor de cartão de crédito listado no campo do conector Pagamento configurar uma conta com esse fornecedor.</span><span class="sxs-lookup"><span data-stu-id="88ccd-110">You must work with a credit card provider that is listed in the Payment connector field and set up an account with that provider.</span></span> <span data-ttu-id="88ccd-111">Você deve então configurar as outras opções na página Serviços de pagamento, configurar tipos de cartão de crédito para American Express, Discover, MasterCard na página Tipos de cartão de crédito e ativar o provedor como o provedor padrão.</span><span class="sxs-lookup"><span data-stu-id="88ccd-111">You must then set up the other options on the Payment services page, set up credit card types for American Express, Discover, MasterCard, and Discover on the Credit card types page, and activate the provider as the default provider.</span></span> <span data-ttu-id="88ccd-112">Você também deve concluir estas etapas para concluir sua configuração:</span><span class="sxs-lookup"><span data-stu-id="88ccd-112">You must also follow these steps to complete your setup:</span></span>
-   <span data-ttu-id="88ccd-113">Na página Parâmetros de contas a receber, especifique os parâmetros para o uso de autorizações de cartão de crédito.</span><span class="sxs-lookup"><span data-stu-id="88ccd-113">On the Accounts receivable parameters page, specify parameters for using credit card authorizations.</span></span>
-   <span data-ttu-id="88ccd-114">Na página Condições de pagamento, configure as condições de pagamento para cartões de crédito.</span><span class="sxs-lookup"><span data-stu-id="88ccd-114">On the Terms of payment page, set up payment terms for credit cards.</span></span> <span data-ttu-id="88ccd-115">No campo Tipo de pagamento, selecione Cartão de crédito.</span><span class="sxs-lookup"><span data-stu-id="88ccd-115">In the Payment type field, select Credit card.</span></span>
-   <span data-ttu-id="88ccd-116">Na página Cartões de crédito do cliente, insira as informações de cartão de crédito para os clientes.</span><span class="sxs-lookup"><span data-stu-id="88ccd-116">On the Customer credit cards page, enter credit card information for customers.</span></span>

## <a name="adding-a-new-credit-card"></a><span data-ttu-id="88ccd-117">Adição de um novo cartão de crédito</span><span class="sxs-lookup"><span data-stu-id="88ccd-117">Adding a new credit card</span></span>
<span data-ttu-id="88ccd-118">Você pode criar novos registros de cartão de crédito na página Clientes usando Cliente, Configurar, Cartão de crédito.</span><span class="sxs-lookup"><span data-stu-id="88ccd-118">You can create new credit card records on the Customers page by using Customer, Set up, Credit card.</span></span> <span data-ttu-id="88ccd-119">Você também pode criar registros de cartão de crédito quando inserir ordens de venda na página Ordem de venda usando Gerenciar, Cliente, Cartão de crédito, Registro.</span><span class="sxs-lookup"><span data-stu-id="88ccd-119">You can also create credit card records when you enter sales orders on the Sales order page, by using Manage, Customer, Credit card, Register.</span></span>
<span data-ttu-id="88ccd-120">Adição de um cartão de crédito a uma ordem de venda</span><span class="sxs-lookup"><span data-stu-id="88ccd-120">Adding a credit card to a sales order</span></span>
-------------------------------------

<span data-ttu-id="88ccd-121">Você pode adicionar um cartão de crédito a uma ordem de venda selecionando um cartão de crédito na pesquisa de cartão de crédito da Guia Rápida Preço e descontos na página Ordem de venda.</span><span class="sxs-lookup"><span data-stu-id="88ccd-121">You can add a credit card to a sales order by selecting a credit card in the credit card lookup on the Price and discounts FastTab on the Sales order page.</span></span> <span data-ttu-id="88ccd-122">Para iniciar o processo de autorização, no Painel de Ação, na guia Gerenciar, selecione Cartão de crédito e Autorizar.</span><span class="sxs-lookup"><span data-stu-id="88ccd-122">To start the authorization process, on the Action Pane, on the Manage tab, select Credit card and Authorize.</span></span>
<span data-ttu-id="88ccd-123">Autorização de um cartão de crédito</span><span class="sxs-lookup"><span data-stu-id="88ccd-123">Authorizing a credit card</span></span>
-------------------------

<span data-ttu-id="88ccd-124">Quando um cartão de crédito é autorizado, o número do cartão e o nome do titular são verificados, e a linha de crédito disponível é confirmada.</span><span class="sxs-lookup"><span data-stu-id="88ccd-124">When a credit card is authorized, the card number and cardholder's name are verified, and the available credit balance is confirmed.</span></span> <span data-ttu-id="88ccd-125">Opcionalmente, o valor de verificação do cartão e o endereço do titular do cartão são verificados.</span><span class="sxs-lookup"><span data-stu-id="88ccd-125">Optionally, the card verification value and the cardholder’s address are verified.</span></span> <span data-ttu-id="88ccd-126">A linha de crédito disponível do cliente é, então, reduzida pelo valor da fatura.</span><span class="sxs-lookup"><span data-stu-id="88ccd-126">The customer's available credit balance is then reduced by the amount of the invoice.</span></span> <span data-ttu-id="88ccd-127">O serviço de pagamento envia a informação de que o cartão de crédito foi aprovado ou rejeitado.</span><span class="sxs-lookup"><span data-stu-id="88ccd-127">The payment service sends information that the credit card has been approved or declined.</span></span> <span data-ttu-id="88ccd-128">Quando a ordem de venda é faturada, o cartão é cobrado (capturado) pelo valor da fatura.</span><span class="sxs-lookup"><span data-stu-id="88ccd-128">When the sales order is invoiced, the credit card is charged (captured) for the invoice amount.</span></span>

### <a name="card-verification-value"></a><span data-ttu-id="88ccd-129">Valor de verificação de cartão</span><span class="sxs-lookup"><span data-stu-id="88ccd-129">Card verification value</span></span>

<span data-ttu-id="88ccd-130">Você pode solicitar o número de verificação do cartão, às vezes chamado de código de segurança do cartão.</span><span class="sxs-lookup"><span data-stu-id="88ccd-130">You can require the card verification value, which is sometimes referred to as the card's security code.</span></span> <span data-ttu-id="88ccd-131">Para a American Express, é um número de quatro dígitos.</span><span class="sxs-lookup"><span data-stu-id="88ccd-131">For American Express, this is a four-digit value.</span></span> <span data-ttu-id="88ccd-132">Para Discover, MasterCard e Visa, é um número de três dígitos.</span><span class="sxs-lookup"><span data-stu-id="88ccd-132">For Discover, MasterCard, and Visa, it is a three-digit value.</span></span>

### <a name="address-verification"></a><span data-ttu-id="88ccd-133">Verificação de endereço</span><span class="sxs-lookup"><span data-stu-id="88ccd-133">Address verification</span></span>

<span data-ttu-id="88ccd-134">As informações de verificação de endereço são sempre enviadas ao provedor de pagamento.</span><span class="sxs-lookup"><span data-stu-id="88ccd-134">Address verification information is always sent to the payment provider.</span></span> <span data-ttu-id="88ccd-135">Você pode decidir quais informações são necessárias para que uma transação seja aceita.</span><span class="sxs-lookup"><span data-stu-id="88ccd-135">You can decide how much information is required for a transaction to be accepted.</span></span> <span data-ttu-id="88ccd-136">Verifique com seu fornecedor para determinar se ele aceita essas informações.</span><span class="sxs-lookup"><span data-stu-id="88ccd-136">Be sure to check with your provider to determine whether it accepts this information.</span></span> <span data-ttu-id="88ccd-137">Estas são as opções de verificação de endereço:</span><span class="sxs-lookup"><span data-stu-id="88ccd-137">Here are the options for address verification:</span></span>
-   <span data-ttu-id="88ccd-138">**Sempre aceitar transação** – aceite a transação, independentemente dos resultados de verificação de endereço.</span><span class="sxs-lookup"><span data-stu-id="88ccd-138">**Always accept transaction** – Accept the transaction, regardless of address verification results.</span></span>
-   <span data-ttu-id="88ccd-139">**Titular da conta** – compare o nome do titular do cartão na transação com as informações da empresa de cartão de crédito.</span><span class="sxs-lookup"><span data-stu-id="88ccd-139">**Account holder** – Compare the cardholder's name from the transaction with the credit card company’s information.</span></span>
-   <span data-ttu-id="88ccd-140">**Endereço de cobrança** – compare o nome e o endereço de cobrança do titular do cartão para a transação com as informações da empresa de cartão de crédito.</span><span class="sxs-lookup"><span data-stu-id="88ccd-140">**Billing address** – Compare the cardholder's name and billing address from the transaction with the credit card company’s information.</span></span>
-   <span data-ttu-id="88ccd-141">**CEP de cobrança** – compare o nome, o endereço de cobrança e o CEP do titular do cartão da transação com as informações da empresa de cartão de crédito.</span><span class="sxs-lookup"><span data-stu-id="88ccd-141">**Billing postal code** – Compare the cardholder's name, billing address, and postal code from the transaction with the credit card company’s information.</span></span>

## <a name="data-support"></a><span data-ttu-id="88ccd-142">Suporte de dados</span><span class="sxs-lookup"><span data-stu-id="88ccd-142">Data support</span></span>
<span data-ttu-id="88ccd-143">Para cada tipo de cartão de crédito compatível, você pode especificar o nível de suporte de dados.</span><span class="sxs-lookup"><span data-stu-id="88ccd-143">For each credit card type that is supported, you can specify the level of data support.</span></span> <span data-ttu-id="88ccd-144">O nível controla quantas informações sobre uma transação são transferidas para o serviço de pagamento.</span><span class="sxs-lookup"><span data-stu-id="88ccd-144">The level controls how much information about a transaction is transferred to the payment service.</span></span> <span data-ttu-id="88ccd-145">Verifique com seu fornecedor para determinar se ele pode fornecer essas informações.</span><span class="sxs-lookup"><span data-stu-id="88ccd-145">Be sure to check with your provider to determine whether it can provide this information.</span></span> <span data-ttu-id="88ccd-146">Estas são as opções para o nível de suporte de dados:</span><span class="sxs-lookup"><span data-stu-id="88ccd-146">Here are the options for the level of data support:</span></span>
-   <span data-ttu-id="88ccd-147">**Nível 1** – transfira a data da transação, o valor da transação e a descrição.</span><span class="sxs-lookup"><span data-stu-id="88ccd-147">**Level 1** – Transfer the transaction date, transaction amount, and description.</span></span>
-   <span data-ttu-id="88ccd-148">**Nível 2** – transfira todas as informações de Nível 1, mais os endereços de remessa e do comerciante e as informações sobre impostos.</span><span class="sxs-lookup"><span data-stu-id="88ccd-148">**Level 2** – Transfer all Level 1 information, plus the shipping and merchant addresses, and tax information.</span></span>
-   <span data-ttu-id="88ccd-149">**Nível 3** – transfira todas as informações de Nível 2, além das informações de linha da ordem.</span><span class="sxs-lookup"><span data-stu-id="88ccd-149">**Level 3** – Transfer all Level 2 information, plus order line information.</span></span>

## <a name="partial-payments"></a><span data-ttu-id="88ccd-150">Pagamentos parciais</span><span class="sxs-lookup"><span data-stu-id="88ccd-150">Partial payments</span></span>
<span data-ttu-id="88ccd-151">Se você enviar parte de uma ordem, o valor da ordem parcial será capturado, e a autorização correspondente ao valor da ordem total, será fechada.</span><span class="sxs-lookup"><span data-stu-id="88ccd-151">If you ship part of an order, the amount of the partial order is captured, and the authorization, which was for the amount of the whole order, is closed.</span></span> <span data-ttu-id="88ccd-152">Uma nova autorização será enviada para o valor restante da ordem que ainda não foi remetida.</span><span class="sxs-lookup"><span data-stu-id="88ccd-152">A new authorization is then submitted for the remaining amount of the order that hasn't been shipped.</span></span>

## <a name="voiding-an-authorization"></a><span data-ttu-id="88ccd-153">Anulando uma autorização </span><span class="sxs-lookup"><span data-stu-id="88ccd-153">Voiding an authorization</span></span>
<span data-ttu-id="88ccd-154">Para anular uma autorização de cartão de crédito, você pode alterar o método de pagamento para outro método que não tenha um tipo de Cartão de crédito.</span><span class="sxs-lookup"><span data-stu-id="88ccd-154">To void a credit card authorization, you can change the method of payment to another method that doesn't have a type of Credit card.</span></span>






