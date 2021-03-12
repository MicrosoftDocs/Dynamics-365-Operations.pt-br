---
title: Criar um mandato de débito direto para um cliente
description: Essa guia de tarefa demonstra como criar uma carta da ordem de débito direto e usá-la em uma nota fiscal.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/08/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustTable, CustBankAccounts, BankAccountTable, CustPaymMode, CustDirectDebitMandate, BankAccountTableLookUp, SrsReportViewerForm,  LogisticsAddressCityLookup, CustFreeInvoice, CustTableLookup
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f746da0bcf2b1e0cb09af6b5e2ea61938213c924
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4991033"
---
# <a name="create-a-direct-debit-mandate-for-a-customer"></a><span data-ttu-id="2683f-103">Criar um mandato de débito direto para um cliente</span><span class="sxs-lookup"><span data-stu-id="2683f-103">Create a direct debit mandate for a customer</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="2683f-104">Essa guia de tarefa demonstra como criar uma carta da ordem de débito direto e usá-la em uma nota fiscal.</span><span class="sxs-lookup"><span data-stu-id="2683f-104">This task guide demonstrates how to create a direct debit mandate and use it on an invoice.</span></span>


## <a name="create-a-bank-account"></a><span data-ttu-id="2683f-105">Criar uma conta bancária</span><span class="sxs-lookup"><span data-stu-id="2683f-105">Create a bank account</span></span>
1. <span data-ttu-id="2683f-106">No **Painel de Navegação**, vá para **Módulos > Contas a receber > Clientes > Todos os clientes**.</span><span class="sxs-lookup"><span data-stu-id="2683f-106">In the **Navigation pane**, go to **Modules > Accounts receivable > Customers > All customers**.</span></span>
2. <span data-ttu-id="2683f-107">Na lista, selecione um registro.</span><span class="sxs-lookup"><span data-stu-id="2683f-107">In the list, select a record.</span></span> <span data-ttu-id="2683f-108">Por exemplo, selecione US-001</span><span class="sxs-lookup"><span data-stu-id="2683f-108">For example, select US-001</span></span>
3. <span data-ttu-id="2683f-109">No Painel de Ações, clique em **Cliente**.</span><span class="sxs-lookup"><span data-stu-id="2683f-109">On the Action Pane, click **Customer**.</span></span>
4. <span data-ttu-id="2683f-110">Clique em **Contas bancárias**.</span><span class="sxs-lookup"><span data-stu-id="2683f-110">Click **Bank accounts**.</span></span>
5. <span data-ttu-id="2683f-111">Clique em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="2683f-111">Click **New**.</span></span>
6. <span data-ttu-id="2683f-112">No campo **Conta bancária**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="2683f-112">In the **Bank account** field, type a value.</span></span>
7. <span data-ttu-id="2683f-113">No campo **Nome**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="2683f-113">In the **Name** field, type a value.</span></span>
8. <span data-ttu-id="2683f-114">No campo **IBAN**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="2683f-114">In the **IBAN** field, type a value.</span></span>
9. <span data-ttu-id="2683f-115">No campo **Moeda**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="2683f-115">In the **Currency** field, type a value.</span></span>
10. <span data-ttu-id="2683f-116">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="2683f-116">Click **Save**.</span></span>
11. <span data-ttu-id="2683f-117">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="2683f-117">Close the page.</span></span>
12. <span data-ttu-id="2683f-118">No **Painel de Navegação**, vá para **Módulos > Gerenciamento de caixa e bancos > Contas bancárias > Contas bancárias**.</span><span class="sxs-lookup"><span data-stu-id="2683f-118">In the **Navigation pane**, go to **Modules > Cash and bank management > Bank accounts > Bank accounts**.</span></span>
13. <span data-ttu-id="2683f-119">Na lista, localize e selecione o registro desejado.</span><span class="sxs-lookup"><span data-stu-id="2683f-119">In the list, find and select the desired record.</span></span>
14. <span data-ttu-id="2683f-120">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="2683f-120">In the list, click the link in the selected row.</span></span>
15. <span data-ttu-id="2683f-121">Clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="2683f-121">Click **Edit**.</span></span>
16. <span data-ttu-id="2683f-122">Expanda a Guia Rápida **Identificação adicional**.</span><span class="sxs-lookup"><span data-stu-id="2683f-122">Expand the **Additional identification** fastTab.</span></span>
17. <span data-ttu-id="2683f-123">No campo **ID do Débito Direto**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="2683f-123">In the **Direct debit ID** field, type a value.</span></span>
18. <span data-ttu-id="2683f-124">No campo **IBAN**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="2683f-124">In the **IBAN** field, type a value.</span></span>
19. <span data-ttu-id="2683f-125">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="2683f-125">Close the page.</span></span>
20. <span data-ttu-id="2683f-126">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="2683f-126">Close the page.</span></span>

## <a name="define-the-electronic-payment-method"></a><span data-ttu-id="2683f-127">Definir o método de pagamento eletrônico</span><span class="sxs-lookup"><span data-stu-id="2683f-127">Define the electronic payment method</span></span>
1. <span data-ttu-id="2683f-128">No **Painel de Navegação**, vá para **Módulos > Contas a receber > Configuração de pagamentos > Formas de pagamento**.</span><span class="sxs-lookup"><span data-stu-id="2683f-128">In the **Navigation pane**, go to **Modules > Accounts receivable > Payments setup > Methods of payment**.</span></span>
2. <span data-ttu-id="2683f-129">Clique em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="2683f-129">Click **New**.</span></span>
3. <span data-ttu-id="2683f-130">No campo **Método de pagamento**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="2683f-130">In the **Method of payment** field, type a value.</span></span>
4. <span data-ttu-id="2683f-131">No campo **Descrição**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="2683f-131">In the **Description** field, type a value.</span></span>
5. <span data-ttu-id="2683f-132">No campo **Tipo de liquidação**, insira "Pagamento eletrônico".</span><span class="sxs-lookup"><span data-stu-id="2683f-132">In the **Payment type** field, enter 'Electronic payment'.</span></span> <span data-ttu-id="2683f-133">O tipo de pagamento para um método de carta da ordem de débito direto do pagamento deve ser pagamento eletrônico.</span><span class="sxs-lookup"><span data-stu-id="2683f-133">The payment type for a direct debit mandate method of payment must be Electronic payment.</span></span>
6. <span data-ttu-id="2683f-134">Selecione Sim no campo **Solicitação obrigatório**.</span><span class="sxs-lookup"><span data-stu-id="2683f-134">Select Yes in the **Require mandate** field.</span></span>
7. <span data-ttu-id="2683f-135">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="2683f-135">Close the page.</span></span>

## <a name="add-a-direct-debit-mandate-to-a-customer"></a><span data-ttu-id="2683f-136">Adicionar um mandato de ordem de débito ao cliente.</span><span class="sxs-lookup"><span data-stu-id="2683f-136">Add a direct debit mandate to a customer.</span></span>
1. <span data-ttu-id="2683f-137">No **Painel de Navegação**, vá para **Módulos > Contas a receber > Clientes > Todos os clientes**.</span><span class="sxs-lookup"><span data-stu-id="2683f-137">In the **Navigation pane**, go to **Modules > Accounts receivable > Customers > All customers**.</span></span>
2. <span data-ttu-id="2683f-138">Na lista, selecione um registro.</span><span class="sxs-lookup"><span data-stu-id="2683f-138">In the list, select a record.</span></span> <span data-ttu-id="2683f-139">Por exemplo, selecione US-001</span><span class="sxs-lookup"><span data-stu-id="2683f-139">For example, select US-001</span></span>
3. <span data-ttu-id="2683f-140">Clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="2683f-140">Click **Edit**.</span></span>
4. <span data-ttu-id="2683f-141">Expanda a Guia Rápida **Padrões de pagamento**.</span><span class="sxs-lookup"><span data-stu-id="2683f-141">Expand the **Payment defaults** fastTab.</span></span>
5. <span data-ttu-id="2683f-142">No campo **Método de pagamento**, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="2683f-142">In the **Method of payment** field, enter or select a value.</span></span>
6. <span data-ttu-id="2683f-143">Expanda a Guia Rápida **Padrões de pagamento**.</span><span class="sxs-lookup"><span data-stu-id="2683f-143">Expand the **Payment defaults** fastTab.</span></span>
7. <span data-ttu-id="2683f-144">Expanda a Guia Rápida **Cartas de ordem de débito direto**.</span><span class="sxs-lookup"><span data-stu-id="2683f-144">Expand the **Direct debit mandates** fastTab.</span></span>
8. <span data-ttu-id="2683f-145">Clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="2683f-145">Click **Add**.</span></span>
9. <span data-ttu-id="2683f-146">No campo **Conta bancária**, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="2683f-146">In the **Bank account** field, enter or select a value.</span></span>
10. <span data-ttu-id="2683f-147">No campo **Conta bancária do credor**, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="2683f-147">In the **Creditor bank account** field, enter or select a value.</span></span>
11. <span data-ttu-id="2683f-148">No campo **Frequência de pagamento**, insira o número de pagamentos que você espera para processar esta carta da ordem.</span><span class="sxs-lookup"><span data-stu-id="2683f-148">In the **Payment frequency** field, enter the number of payments that you expect to process for this mandate.</span></span>
12. <span data-ttu-id="2683f-149">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="2683f-149">Click **OK**.</span></span>
13. <span data-ttu-id="2683f-150">Clique em **Imprimir**.</span><span class="sxs-lookup"><span data-stu-id="2683f-150">Click **Print**.</span></span>
14. <span data-ttu-id="2683f-151">Clique em **Relatório da carta de ordem**.</span><span class="sxs-lookup"><span data-stu-id="2683f-151">Click **Mandate report**.</span></span>
15. <span data-ttu-id="2683f-152">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="2683f-152">Close the page.</span></span>
16. <span data-ttu-id="2683f-153">Clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="2683f-153">Click **Edit**.</span></span>
17. <span data-ttu-id="2683f-154">No campo **Data de assinatura**, insira uma data.</span><span class="sxs-lookup"><span data-stu-id="2683f-154">In the **Signature date** field, enter a date.</span></span>
18. <span data-ttu-id="2683f-155">Clique em **Sim**.</span><span class="sxs-lookup"><span data-stu-id="2683f-155">Click **Yes**.</span></span>
19. <span data-ttu-id="2683f-156">Insira o local em que a carta de ordem foi assinada.</span><span class="sxs-lookup"><span data-stu-id="2683f-156">Enter the location where the mandate was signed.</span></span>
20. <span data-ttu-id="2683f-157">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="2683f-157">Click **OK**.</span></span>
21. <span data-ttu-id="2683f-158">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="2683f-158">Close the page.</span></span>

## <a name="create-a-free-text-invoice-with-mandate"></a><span data-ttu-id="2683f-159">Criar uma fatura de texto livre com mandato</span><span class="sxs-lookup"><span data-stu-id="2683f-159">Create a free text invoice with mandate</span></span>
1. <span data-ttu-id="2683f-160">No **Painel de Navegação**, vá para **Módulos > Contas a receber > Faturas > Todas as faturas de texto livre**.</span><span class="sxs-lookup"><span data-stu-id="2683f-160">In the **Navigation pane**, go to **Modules > Accounts receivable > Invoices > All free text invoices**.</span></span>
2. <span data-ttu-id="2683f-161">Clique em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="2683f-161">Click **New**.</span></span>
3. <span data-ttu-id="2683f-162">Selecione o cliente para o qual você adicionou a carta da ordem.</span><span class="sxs-lookup"><span data-stu-id="2683f-162">Select the customer that you added the mandate to.</span></span>
4. <span data-ttu-id="2683f-163">No campo **Carta de ordem de débito direto**, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="2683f-163">In the **Direct debit mandate ID** field, enter or select a value.</span></span>

