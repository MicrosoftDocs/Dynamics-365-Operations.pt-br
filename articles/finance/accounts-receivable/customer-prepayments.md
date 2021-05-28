---
title: Pagamentos antecipados do cliente
description: Este tópico explica como configurar e processar pagamentos antecipados do cliente (também conhecido como depósitos do cliente).
author: roschlom
ms.date: 04/30/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CustPosting, LedgerJournalTransCustPaym, CustParameters
audience: Application User
ms.reviewer: ''
ms.search.scope: Core, Operations
ms.custom: 24651
ms.assetid: cb82245e-8c02-429c-b36e-8db0e3e6f7e5
ms.search.region: Global
ms.author: raprofit
ms.search.validFrom: ''
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c3314803b994aed40e5b04d8546a45bd305d48b6
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2021
ms.locfileid: "6019411"
---
# <a name="customer-prepayments"></a><span data-ttu-id="976b5-103">Pagamentos antecipados do cliente</span><span class="sxs-lookup"><span data-stu-id="976b5-103">Customer prepayments</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="976b5-104">Pagamentos antecipados do cliente são usados quando você recebe um pagamento de um caixa, mas não há fatura mediante à qual o pagamento pode ser liquidado.</span><span class="sxs-lookup"><span data-stu-id="976b5-104">Customer prepayments are used when you receive a payment from a customer, but there is no invoice that the payment can be settled against.</span></span> <span data-ttu-id="976b5-105">Esses tipos de pagamentos também são chamados de depósitos do cliente.</span><span class="sxs-lookup"><span data-stu-id="976b5-105">These types of payments are also referred to as customer deposits.</span></span>

<span data-ttu-id="976b5-106">O processo de configurar e trabalhar com pagamentos antecipados do cliente consiste nas seguintes etapas básicas.</span><span class="sxs-lookup"><span data-stu-id="976b5-106">The process of setting up and working with customer prepayments consists of the following basic steps.</span></span>

1. <span data-ttu-id="976b5-107">Crie um perfil de postagem do cliente para pagamentos antecipados.</span><span class="sxs-lookup"><span data-stu-id="976b5-107">Create a customer posting profile for prepayments.</span></span>
2. <span data-ttu-id="976b5-108">Defina o parâmetro **Perfil de postagem com comprovante de diário do pagamento antecipado**.</span><span class="sxs-lookup"><span data-stu-id="976b5-108">Set the **Posting profile with prepayment journal voucher** parameter.</span></span>
3. <span data-ttu-id="976b5-109">Crie um diário de pagamento do cliente e marque a caixa de seleção **Comprovante de diário do pagamento antecipado** em cada linha.</span><span class="sxs-lookup"><span data-stu-id="976b5-109">Create a customer payment journal, and select the **Prepayment journal voucher** check box on each line.</span></span>
4. <span data-ttu-id="976b5-110">Lançar o diário de pagamentos do cliente.</span><span class="sxs-lookup"><span data-stu-id="976b5-110">Post the customer payment journal.</span></span>
5. <span data-ttu-id="976b5-111">Quando uma fatura é gerada, liquide o pagamento antecipado com ela usando a página **Liquidar transações em aberto**.</span><span class="sxs-lookup"><span data-stu-id="976b5-111">After an invoice is generated, settle the prepayment with it by using the **Settle open transactions** page.</span></span>

## <a name="create-a-customer-posting-profile-for-prepayments"></a><span data-ttu-id="976b5-112">Criar um perfil de postagem do cliente para pagamentos antecipados</span><span class="sxs-lookup"><span data-stu-id="976b5-112">Create a customer posting profile for prepayments</span></span>

<span data-ttu-id="976b5-113">Normalmente, quando você aceita pagamentos antecipados ou depósitos de seus clientes antes que os produtos ou serviços sejam entregues, ou antes que uma fatura exista no seu sistema, é recomendável que você registre o caixa como um passivo em vez de um ativo em sua tabela de contas.</span><span class="sxs-lookup"><span data-stu-id="976b5-113">Typically, when you accept prepayments or deposits from your customers before goods or services are delivered, or before an invoice exists in your system, you will want to record the cash as a liability instead of an asset in your chart of accounts.</span></span> <span data-ttu-id="976b5-114">Entretanto, os requisitos para registrar esses valores na sua contabilidade geral podem variar, dependendo do seu país ou região.</span><span class="sxs-lookup"><span data-stu-id="976b5-114">However, the requirements for recording these amounts in your general ledger might differ, depending on your country or region.</span></span> <span data-ttu-id="976b5-115">Entretanto, certifique-se de consultar seus contadores sobre quaisquer regulamentos locais que se apliquem.</span><span class="sxs-lookup"><span data-stu-id="976b5-115">Therefore, be sure to consult your accountants about any local regulations that apply.</span></span>

<span data-ttu-id="976b5-116">No geral, o processo para criar um perfil de postagem que pode ser usado para pagamentos antecipados é igual ao processo de criar outros perfis de postagem.</span><span class="sxs-lookup"><span data-stu-id="976b5-116">In general, the process for creating a posting profile that can be used for prepayments is the same as the process for creating other posting profiles.</span></span> <span data-ttu-id="976b5-117">A principal diferença é a conta principal que você seleciona no campo **Conta de resumo**.</span><span class="sxs-lookup"><span data-stu-id="976b5-117">The primary difference is the main account that you select in the **Summary account** field.</span></span> <span data-ttu-id="976b5-118">Para obter mais informações, consulte [Perfis de postagem do cliente](customer-posting-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="976b5-118">For more information, see [Customer posting profiles](customer-posting-profiles.md).</span></span>

## <a name="define-parameters-for-customer-prepayments"></a><span data-ttu-id="976b5-119">Definir parâmetros para pagamentos antecipados do cliente</span><span class="sxs-lookup"><span data-stu-id="976b5-119">Define parameters for customer prepayments</span></span>

<span data-ttu-id="976b5-120">Há dois principais parâmetros de Contas a receber que você deve considerar ao configurar o sistema para pagamentos antecipados do cliente.</span><span class="sxs-lookup"><span data-stu-id="976b5-120">There are two main Accounts receivable parameters that you must consider when you configure the system for customer prepayments.</span></span> <span data-ttu-id="976b5-121">Siga essas etapas para configurar os parâmetros.</span><span class="sxs-lookup"><span data-stu-id="976b5-121">Follow these steps to configure the parameters.</span></span>

1. <span data-ttu-id="976b5-122">Vá para **Contas a receber \> Configuração \> Parâmetros de contas a receber**.</span><span class="sxs-lookup"><span data-stu-id="976b5-122">Go to **Accounts receivable \> Setup \> Accounts receivable parameters**.</span></span>
2. <span data-ttu-id="976b5-123">Opcional: na guia **Razão e imposto de vendas**, na FastTab **Pagamento**, defina a opção **Imposto de vendas no comprovante no diário do pagamento antecipado** como **Sim**.</span><span class="sxs-lookup"><span data-stu-id="976b5-123">Optional: On the **Ledger and sales tax** tab, on the **Payment** FastTab, set the **Sales tax on prepayment journal voucher** option to **Yes**.</span></span>
3. <span data-ttu-id="976b5-124">No campo **Perfil de postagem com comprovante no diário do pagamento antecipado**, selecione o perfil de postagem do cliente para usar quando pagamentos antecipados do cliente são postados.</span><span class="sxs-lookup"><span data-stu-id="976b5-124">In the **Posting profile with prepayment journal voucher** field, select the customer posting profile to use when customer prepayments are posted.</span></span>
4. <span data-ttu-id="976b5-125">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="976b5-125">Close the page.</span></span>

## <a name="create-customer-prepayment-vouchers"></a><span data-ttu-id="976b5-126">Criar comprovantes de pagamento antecipado do cliente</span><span class="sxs-lookup"><span data-stu-id="976b5-126">Create customer prepayment vouchers</span></span>

<span data-ttu-id="976b5-127">Quando você cria o diário de pagamento do cliente, para todo pagamento antecipado, é necessário definir a opção **Comprovante no jornal de pagamento antecipado** como **Sim** na página **Diário de pagamento do cliente**.</span><span class="sxs-lookup"><span data-stu-id="976b5-127">When you create the customer payment journal, for every prepayment, you must set the **Prepayment journal voucher** option to **Yes** on the **Customer payment journal** page.</span></span> <span data-ttu-id="976b5-128">Siga essas etapas para criar um pagamento antecipado do cliente.</span><span class="sxs-lookup"><span data-stu-id="976b5-128">Follow these steps to create a customer prepayment.</span></span>

1. <span data-ttu-id="976b5-129">Acesse **Contas a receber \> Pagamentos \> Diário de pagamento do cliente**.</span><span class="sxs-lookup"><span data-stu-id="976b5-129">Go to **Accounts receivable \> Payments \> Customer payment journal**.</span></span>
2. <span data-ttu-id="976b5-130">Para criar um diário, selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="976b5-130">Select **New** to create a journal.</span></span>
3. <span data-ttu-id="976b5-131">No campo **Nome**, selecione o nome de diário para usar.</span><span class="sxs-lookup"><span data-stu-id="976b5-131">In the **Name** field, select the journal name to use.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="976b5-132">Se você definir a opção **Imposto de vendas no comprovante no diário do pagamento antecipado** como **Sim** no procedimento anterior, você deve selecionar um nome de diário em que o parâmetro **Valor inclui imposto de vendas**.</span><span class="sxs-lookup"><span data-stu-id="976b5-132">If you set the **Sales tax on prepayment journal voucher** option to **Yes** in the previous procedure, you must select a journal name where the **Amount includes sales tax** parameter is selected.</span></span> 

4. <span data-ttu-id="976b5-133">Opcional: no campo **Descrição**, insira uma descrição detalhada.</span><span class="sxs-lookup"><span data-stu-id="976b5-133">Optional: In the **Description** field, enter a detailed description.</span></span>
5. <span data-ttu-id="976b5-134">Selecione **Linhas**.</span><span class="sxs-lookup"><span data-stu-id="976b5-134">Select **Lines**.</span></span>
6. <span data-ttu-id="976b5-135">Se não houver uma linha em branco, selecione **Novo** para criar uma linha.</span><span class="sxs-lookup"><span data-stu-id="976b5-135">If a blank line doesn't exist, select **New** to create a line.</span></span>
7. <span data-ttu-id="976b5-136">No campo **Data**, insira a data em que o pagamento antecipado deve ser postado.</span><span class="sxs-lookup"><span data-stu-id="976b5-136">In the **Date** field, enter the date when the prepayment should be posted.</span></span>
8. <span data-ttu-id="976b5-137">No campo **Conta**, selecione o cliente para o pagamento antecipado.</span><span class="sxs-lookup"><span data-stu-id="976b5-137">In the **Account** field, select the customer for the prepayment.</span></span>
9. <span data-ttu-id="976b5-138">Opcional: no campo **Descrição**, insira uma descrição detalhada da transação.</span><span class="sxs-lookup"><span data-stu-id="976b5-138">Optional: In the **Description** field, enter a detailed description of the transaction.</span></span>
10. <span data-ttu-id="976b5-139">No campo **Crédito**, insira o valor do pagamento antecipado.</span><span class="sxs-lookup"><span data-stu-id="976b5-139">In the **Credit** field, enter the amount of the prepayment.</span></span>
11. <span data-ttu-id="976b5-140">No campo **Conta de compensação**, selecione a conta com a qual o pagamento será compensado.</span><span class="sxs-lookup"><span data-stu-id="976b5-140">In the **Offset account** field, select the account to offset the payment to.</span></span> <span data-ttu-id="976b5-141">Por exemplo, selecione o banco ou conta principal à qual postar o pagamento.</span><span class="sxs-lookup"><span data-stu-id="976b5-141">For example, select the bank or main account to post the payment to.</span></span>
12. <span data-ttu-id="976b5-142">No campo **Método de pagamento**, selecione o método de pagamento do cliente.</span><span class="sxs-lookup"><span data-stu-id="976b5-142">In the **Method of payment** field, select the customer's method of payment.</span></span>
13. <span data-ttu-id="976b5-143">Na guia **Pagamento**, defina a opção **Comprovante no jornal do pagamento antecipado** como **Sim**.</span><span class="sxs-lookup"><span data-stu-id="976b5-143">On the **Payment** tab, set the **Prepayment journal voucher** option to **Yes**.</span></span>
14. <span data-ttu-id="976b5-144">Repita as etapas 7 a 13 para cada pagamento antecipado adicional que deve ser postado.</span><span class="sxs-lookup"><span data-stu-id="976b5-144">Repeat steps 7 through 13 for each additional prepayment that must be posted.</span></span>
15. <span data-ttu-id="976b5-145">Selecione **Postar** para finalizar o diário.</span><span class="sxs-lookup"><span data-stu-id="976b5-145">Select **Post** to finalize the journal.</span></span>

## <a name="settle-prepayments-with-invoices"></a><span data-ttu-id="976b5-146">Liquidar pagamentos antecipados com faturas</span><span class="sxs-lookup"><span data-stu-id="976b5-146">Settle prepayments with invoices</span></span>

<span data-ttu-id="976b5-147">Você pode usar o espaço de trabalho **Pagamentos do cliente** para encontrar e liquidar facilmente pagamentos que não foram totalmente liquidados.</span><span class="sxs-lookup"><span data-stu-id="976b5-147">You can use the **Customer payments** workspace to easily find and settle payments that haven't been fully settled.</span></span>

1. <span data-ttu-id="976b5-148">No painel **Início**, selecione o bloco **Pagamentos do cliente**.</span><span class="sxs-lookup"><span data-stu-id="976b5-148">On the **Home** dashboard, select the **Customer payments** tile.</span></span>
2. <span data-ttu-id="976b5-149">Na seção **Transações do cliente**, na guia **Pagamentos não liquidados**, pesquise e selecione o pagamento a ser liquidado.</span><span class="sxs-lookup"><span data-stu-id="976b5-149">In the **Customer transactions** section, on the **Payments not settled** tab, search for and select the payment to settle.</span></span>
3. <span data-ttu-id="976b5-150">Selecione **Liquidar transações**.</span><span class="sxs-lookup"><span data-stu-id="976b5-150">Select **Settle transactions**.</span></span>
4. <span data-ttu-id="976b5-151">Marque a caixa de seleção **Marcar** para a fatura e o pagamento que serão liquidados.</span><span class="sxs-lookup"><span data-stu-id="976b5-151">Select the **Mark** check box for the invoice and the payment that will be settled.</span></span>
5. <span data-ttu-id="976b5-152">Selecione **Lançar**.</span><span class="sxs-lookup"><span data-stu-id="976b5-152">Select **Post**.</span></span>

<span data-ttu-id="976b5-153">Para obter mais informações sobre como liquidar transações em aberto, consulte [Visão geral da liquidação](/cash-bank-management/settlement-overview.md).</span><span class="sxs-lookup"><span data-stu-id="976b5-153">For more information about how to settle open transactions, see [Settlement overview](/cash-bank-management/settlement-overview.md).</span></span>
