---
title: Criar pagamentos para um cliente que tenha cartas de ordem de débito direto
description: Este procedimento exibe como gerar um arquivo de pagamento de débito direito de ISO20022 para clientes com débito direto configurado e fatura a ser paga.
author: mrolecki
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustFreeInvoice, CustTableLookup, CustPostInvoiceJob, LedgerJournalTable, LedgerJournalTransCustPaym, SysQueryForm, CustPaymProposalEdit, BankAccountTableLookUp
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 129c5291a29994f91ef325aa9b9a3b54a0e958d6
ms.sourcegitcommit: 807dec193cd163c9f5d949e744cfde40f2eb24b4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/01/2019
ms.locfileid: "2468946"
---
# <a name="create-payments-for-a-customer-who-have-direct-debit-mandates"></a><span data-ttu-id="39534-103">Criar pagamentos para um cliente que tenha cartas de ordem de débito direto</span><span class="sxs-lookup"><span data-stu-id="39534-103">Create payments for a customer who have direct debit mandates</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="39534-104">Este procedimento exibe como gerar um arquivo de pagamento de débito direito de ISO20022 para clientes com débito direto configurado e fatura a ser paga.</span><span class="sxs-lookup"><span data-stu-id="39534-104">This procedure shows how to generate an ISO20022 direct debit payment file for a customer who has direct debit configured and an invoice to be paid.</span></span> <span data-ttu-id="39534-105">Criar e lançar uma nota fiscal é opcional.</span><span class="sxs-lookup"><span data-stu-id="39534-105">Creating and posting an invoice is optional.</span></span> <span data-ttu-id="39534-106">Em vez de uma nota fiscal para sê-lo paga pode selecionar uma carta de um ordem em diário antes de gerar um arquivo de pagamento, para oferecer um cenário de pagamento antecipado do cliente.</span><span class="sxs-lookup"><span data-stu-id="39534-106">Instead of having an invoice to be paid you can select a mandate in a journal prior to generating a payment file, to support a customer prepayment scenario.</span></span>



<span data-ttu-id="39534-107">A empresa de dados demonstrativos utilizada para criar esse procedimento é a DEMF.</span><span class="sxs-lookup"><span data-stu-id="39534-107">The demo data company used to create this procedure is DEMF.</span></span>



<span data-ttu-id="39534-108">Este é o quinto dos cinco procedimentos que demonstram o processo de pagamento de clientes usando as configurações de relatório eletrônico.</span><span class="sxs-lookup"><span data-stu-id="39534-108">This is the fifth of five procedures that demonstrate the customer payment process using electronic reporting configurations.</span></span> <span data-ttu-id="39534-109">Para concluir essa tarefa, você deverá concluir tarefas anteriores.</span><span class="sxs-lookup"><span data-stu-id="39534-109">Before you can complete this task, you must complete the earlier tasks.</span></span> <span data-ttu-id="39534-110">Primeiro você deve importar as configurações de relatório eletrônico do pagamento, configurar o método dos pagamentos e definir as informações da empresa e do cliente.</span><span class="sxs-lookup"><span data-stu-id="39534-110">You must first import customer payment electronic reporting configurations, configure method of payments, and set up your company and customer information.</span></span> 


## <a name="post-a-free-text-invoice-with-direct-debit-information"></a><span data-ttu-id="39534-111">Lançar uma fatura de texto livre com informações de débito direto</span><span class="sxs-lookup"><span data-stu-id="39534-111">Post a free text invoice with direct debit information</span></span>
1. <span data-ttu-id="39534-112">Vá para Contas recebíveis > Faturas > Todas faturas de texto livre.</span><span class="sxs-lookup"><span data-stu-id="39534-112">Go to Accounts receivable > Invoices > All free text invoices.</span></span>
2. <span data-ttu-id="39534-113">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="39534-113">Click New.</span></span>
3. <span data-ttu-id="39534-114">No campo Conta de cliente, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="39534-114">In the Customer account field, enter or select a value.</span></span>
    * <span data-ttu-id="39534-115">Por exemplo, selecione DE-010.</span><span class="sxs-lookup"><span data-stu-id="39534-115">For example, select DE-010.</span></span>  
4. <span data-ttu-id="39534-116">No campo Condições de pagamento, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="39534-116">In the Method of payment field, enter or select a value.</span></span>
    * <span data-ttu-id="39534-117">Por exemplo.</span><span class="sxs-lookup"><span data-stu-id="39534-117">For example.</span></span> <span data-ttu-id="39534-118">selecione Eletrônico.</span><span class="sxs-lookup"><span data-stu-id="39534-118">select Electronic.</span></span>  
5. <span data-ttu-id="39534-119">No campo Carta de ordem de débito direto, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="39534-119">In the Direct debit mandate ID field, enter or select a value.</span></span>
6. <span data-ttu-id="39534-120">Clique em Adicionar nova linha.</span><span class="sxs-lookup"><span data-stu-id="39534-120">Click Add line.</span></span>
7. <span data-ttu-id="39534-121">No campo Descrição, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="39534-121">In the Description field, type a value.</span></span>
8. <span data-ttu-id="39534-122">No campo Conta principal, especifique os valores desejados.</span><span class="sxs-lookup"><span data-stu-id="39534-122">In the Main account field, specify the desired values.</span></span>
9. <span data-ttu-id="39534-123">No campo Preço unitário, insira um número.</span><span class="sxs-lookup"><span data-stu-id="39534-123">In the Unit price field, enter a number.</span></span>
10. <span data-ttu-id="39534-124">Clique em Lançar.</span><span class="sxs-lookup"><span data-stu-id="39534-124">Click Post.</span></span>
11. <span data-ttu-id="39534-125">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="39534-125">Click OK.</span></span>

## <a name="create-a-payment"></a><span data-ttu-id="39534-126">Criar um pagamento</span><span class="sxs-lookup"><span data-stu-id="39534-126">Create a payment</span></span>
1. <span data-ttu-id="39534-127">Vá para Contas a receber > Pagamentos > Diário de pagamentos.</span><span class="sxs-lookup"><span data-stu-id="39534-127">Go to Accounts receivable > Payments > Payment journal.</span></span>
2. <span data-ttu-id="39534-128">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="39534-128">Click New.</span></span>
3. <span data-ttu-id="39534-129">No campo Nome, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="39534-129">In the Name field, enter or select a value.</span></span>
4. <span data-ttu-id="39534-130">Clique em Linhas.</span><span class="sxs-lookup"><span data-stu-id="39534-130">Click Lines.</span></span>
5. <span data-ttu-id="39534-131">Clique em Proposta de pagamento.</span><span class="sxs-lookup"><span data-stu-id="39534-131">Click Payment proposal.</span></span>
6. <span data-ttu-id="39534-132">Clique em Criar proposta de pagamento.</span><span class="sxs-lookup"><span data-stu-id="39534-132">Click Create payment proposal.</span></span>
7. <span data-ttu-id="39534-133">Expanda os Registros para incluir a seção.</span><span class="sxs-lookup"><span data-stu-id="39534-133">Expand the Records to include section.</span></span>
8. <span data-ttu-id="39534-134">Clique em Filtro.</span><span class="sxs-lookup"><span data-stu-id="39534-134">Click Filter.</span></span>
9. <span data-ttu-id="39534-135">Na lista, selecione a linha para a tabela de transações de cliente e o método do pagamento.</span><span class="sxs-lookup"><span data-stu-id="39534-135">In the list, select the row for the Customer transactions table and the Method of payment field.</span></span>
    * <span data-ttu-id="39534-136">Você pode aplicar os critérios para selecionar transações de cliente para pagar.</span><span class="sxs-lookup"><span data-stu-id="39534-136">You can apply any criteria for selecting customer transactions to pay.</span></span> <span data-ttu-id="39534-137">Por exemplo, use eletrônico como método de pagamento para filtrar transações.</span><span class="sxs-lookup"><span data-stu-id="39534-137">For this example, use Electronic as a method of payment to filter transactions.</span></span>  
10. <span data-ttu-id="39534-138">No campo Critérios, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="39534-138">In the Criteria field, enter or select a value.</span></span>
11. <span data-ttu-id="39534-139">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="39534-139">Click OK.</span></span>
12. <span data-ttu-id="39534-140">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="39534-140">Click OK.</span></span>
13. <span data-ttu-id="39534-141">Clique em Criar pagamentos.</span><span class="sxs-lookup"><span data-stu-id="39534-141">Click Create payments.</span></span>