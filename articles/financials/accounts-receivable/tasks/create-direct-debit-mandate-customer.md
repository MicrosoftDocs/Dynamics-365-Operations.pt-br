--- 
title: "Criar um mandato de débito direto para um cliente"
description: "Essa guia de tarefa demonstra como criar uma carta da ordem de débito direto e usá-la em uma nota fiscal."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 10/23/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: d01c7c19925a3c7064ab3f845b92b610b162066c
ms.contentlocale: pt-br
ms.lasthandoff: 09/29/2017

---
# <a name="create-a-direct-debit-mandate-for-a-customer"></a><span data-ttu-id="37988-103">Criar um mandato de débito direto para um cliente</span><span class="sxs-lookup"><span data-stu-id="37988-103">Create a direct debit mandate for a customer</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="37988-104">Essa guia de tarefa demonstra como criar uma carta da ordem de débito direto e usá-la em uma nota fiscal.</span><span class="sxs-lookup"><span data-stu-id="37988-104">This task guide demonstrates how to create a direct debit mandate and use it on an invoice.</span></span>


## <a name="create-a-bank-account"></a><span data-ttu-id="37988-105">Criar uma conta bancária</span><span class="sxs-lookup"><span data-stu-id="37988-105">Create a bank account</span></span>
1. <span data-ttu-id="37988-106">Ir para Contas recebíveis > Clientes > Todos os clientes.</span><span class="sxs-lookup"><span data-stu-id="37988-106">Go to Accounts receivable > Customers > All customers.</span></span>
2. <span data-ttu-id="37988-107">Por exemplo, selecione US-001</span><span class="sxs-lookup"><span data-stu-id="37988-107">For example, select US-001</span></span>
3. <span data-ttu-id="37988-108">No Painel de Ação, clique em Cliente.</span><span class="sxs-lookup"><span data-stu-id="37988-108">On the Action Pane, click Customer.</span></span>
4. <span data-ttu-id="37988-109">Clique em Contas bancárias.</span><span class="sxs-lookup"><span data-stu-id="37988-109">Click Bank accounts.</span></span>
5. <span data-ttu-id="37988-110">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="37988-110">Click New.</span></span>
6. <span data-ttu-id="37988-111">No campo Conta bancária, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="37988-111">In the Bank account field, type a value.</span></span>
7. <span data-ttu-id="37988-112">No campo Nome, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="37988-112">In the Name field, type a value.</span></span>
8. <span data-ttu-id="37988-113">No campo IBAN, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="37988-113">In the IBAN field, type a value.</span></span>
9. <span data-ttu-id="37988-114">No campo Moeda, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="37988-114">In the Currency field, type a value.</span></span>
10. <span data-ttu-id="37988-115">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="37988-115">Click Save.</span></span>
11. <span data-ttu-id="37988-116">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="37988-116">Close the page.</span></span>
12. <span data-ttu-id="37988-117">Vá para Gerenciamento de caixa e bancos > Contas bancárias > Contas bancárias.</span><span class="sxs-lookup"><span data-stu-id="37988-117">Go to Cash and bank management > Bank accounts > Bank accounts.</span></span>
13. <span data-ttu-id="37988-118">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="37988-118">In the list, find and select the desired record.</span></span>
14. <span data-ttu-id="37988-119">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="37988-119">In the list, click the link in the selected row.</span></span>
15. <span data-ttu-id="37988-120">Clique em Editar.</span><span class="sxs-lookup"><span data-stu-id="37988-120">Click Edit.</span></span>
16. <span data-ttu-id="37988-121">Expanda a seção Identificação adicional.</span><span class="sxs-lookup"><span data-stu-id="37988-121">Expand the Additional identification section.</span></span>
17. <span data-ttu-id="37988-122">No campo ID do Débito Direto, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="37988-122">In the Direct debit ID field, type a value.</span></span>
18. <span data-ttu-id="37988-123">No campo IBAN, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="37988-123">In the IBAN field, type a value.</span></span>
19. <span data-ttu-id="37988-124">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="37988-124">Close the page.</span></span>
20. <span data-ttu-id="37988-125">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="37988-125">Close the page.</span></span>

## <a name="define-the-electronic-payment-method"></a><span data-ttu-id="37988-126">Definir o método de pagamento eletrônico</span><span class="sxs-lookup"><span data-stu-id="37988-126">Define the electronic payment method</span></span>
1. <span data-ttu-id="37988-127">Vá para Contas a receber > Configurar pagamentos > Métodos de pagamento.</span><span class="sxs-lookup"><span data-stu-id="37988-127">Go to Accounts receivable > Payments setup > Methods of payment.</span></span>
2. <span data-ttu-id="37988-128">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="37988-128">Click New.</span></span>
3. <span data-ttu-id="37988-129">No campo Método de pagamento, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="37988-129">In the Method of payment field, type a value.</span></span>
4. <span data-ttu-id="37988-130">No campo Descrição, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="37988-130">In the Description field, type a value.</span></span>
5. <span data-ttu-id="37988-131">O tipo de pagamento para um método de carta da ordem de débito direto do pagamento deve ser pagamento eletrônico.</span><span class="sxs-lookup"><span data-stu-id="37988-131">The payment type for a direct debit mandate method of payment must be Electronic payment.</span></span>
6. <span data-ttu-id="37988-132">Selecione Sim no campo de Solicitação obrigatório.</span><span class="sxs-lookup"><span data-stu-id="37988-132">Select Yes in the Require mandate field.</span></span>
7. <span data-ttu-id="37988-133">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="37988-133">Close the page.</span></span>

## <a name="add-a-direct-debit-mandate-to-a-customer"></a><span data-ttu-id="37988-134">Adicionar um mandato de ordem de débito ao cliente.</span><span class="sxs-lookup"><span data-stu-id="37988-134">Add a direct debit mandate to a customer.</span></span>
1. <span data-ttu-id="37988-135">Ir para Contas recebíveis > Clientes > Todos os clientes.</span><span class="sxs-lookup"><span data-stu-id="37988-135">Go to Accounts receivable > Customers > All customers.</span></span>
2. <span data-ttu-id="37988-136">Por exemplo, selecione US-001</span><span class="sxs-lookup"><span data-stu-id="37988-136">For example, select US-001</span></span>
3. <span data-ttu-id="37988-137">Clique em Editar.</span><span class="sxs-lookup"><span data-stu-id="37988-137">Click Edit.</span></span>
4. <span data-ttu-id="37988-138">Expanda a seção de padrões de pagamento.</span><span class="sxs-lookup"><span data-stu-id="37988-138">Expand the Payment defaults section.</span></span>
5. <span data-ttu-id="37988-139">No campo Condições de pagamento, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="37988-139">In the Method of payment field, enter or select a value.</span></span>
6. <span data-ttu-id="37988-140">Expanda a seção de padrões de pagamento.</span><span class="sxs-lookup"><span data-stu-id="37988-140">Expand the Payment defaults section.</span></span>
7. <span data-ttu-id="37988-141">Expanda a seção de cartas da ordem de débito direto.</span><span class="sxs-lookup"><span data-stu-id="37988-141">Expand the Direct debit mandates section.</span></span>
8. <span data-ttu-id="37988-142">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="37988-142">Click Add.</span></span>
9. <span data-ttu-id="37988-143">No campo Conta bancária, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="37988-143">In the Bank account field, enter or select a value.</span></span>
10. <span data-ttu-id="37988-144">No campo Conta bancária do credor, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="37988-144">In the Creditor bank account field, enter or select a value.</span></span>
11. <span data-ttu-id="37988-145">Insira o número de pagamentos que você espera para processar esta carta da ordem.</span><span class="sxs-lookup"><span data-stu-id="37988-145">Enter the number of payments that you expect to process for this mandate.</span></span>
12. <span data-ttu-id="37988-146">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="37988-146">Click OK.</span></span>
13. <span data-ttu-id="37988-147">Clique em Imprimir.</span><span class="sxs-lookup"><span data-stu-id="37988-147">Click Print.</span></span>
14. <span data-ttu-id="37988-148">Clique em Relatório da carta de ordem.</span><span class="sxs-lookup"><span data-stu-id="37988-148">Click Mandate report.</span></span>
15. <span data-ttu-id="37988-149">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="37988-149">Close the page.</span></span>
16. <span data-ttu-id="37988-150">Clique em Editar.</span><span class="sxs-lookup"><span data-stu-id="37988-150">Click Edit.</span></span>
17. <span data-ttu-id="37988-151">No campo Data de assinatura, insira uma data.</span><span class="sxs-lookup"><span data-stu-id="37988-151">In the Signature date field, enter a date.</span></span>
18. <span data-ttu-id="37988-152">Clique em Sim.</span><span class="sxs-lookup"><span data-stu-id="37988-152">Click Yes.</span></span>
19. <span data-ttu-id="37988-153">Insira o local em que a carta de ordem foi assinada.</span><span class="sxs-lookup"><span data-stu-id="37988-153">Enter the location where the mandate was signed.</span></span>
20. <span data-ttu-id="37988-154">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="37988-154">Click OK.</span></span>
21. <span data-ttu-id="37988-155">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="37988-155">Close the page.</span></span>

## <a name="create-a-free-text-invoice-with-mandate"></a><span data-ttu-id="37988-156">Criar uma fatura de texto livre com mandato</span><span class="sxs-lookup"><span data-stu-id="37988-156">Create a free text invoice with mandate</span></span>
1. <span data-ttu-id="37988-157">Vá para Contas recebíveis > Faturas > Todas faturas de texto livre.</span><span class="sxs-lookup"><span data-stu-id="37988-157">Go to Accounts receivable > Invoices > All free text invoices.</span></span>
2. <span data-ttu-id="37988-158">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="37988-158">Click New.</span></span>
3. <span data-ttu-id="37988-159">Selecione o cliente para o qual você adicionou a carta da ordem.</span><span class="sxs-lookup"><span data-stu-id="37988-159">Select the customer that you added the mandate to.</span></span>
4. <span data-ttu-id="37988-160">No campo Carta de ordem de débito direto, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="37988-160">In the Direct debit mandate ID field, enter or select a value.</span></span>


