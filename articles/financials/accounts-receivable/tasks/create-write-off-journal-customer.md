---
title: Criar um diário de baixa para um cliente
description: Esta guia de tarefa mostrará como configurar parâmetros de baixas contábeis e dar baixa em transações da página das coleções, a página inicial das notas fiscais de clientes, e a página do cliente.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustParameters, CustPosting, DefaultDashboard, CustCollectionsPoolsListPage, CustWriteOff, LedgerJournalTable, LedgerJournalTransDaily, CustCollections, CustOpenInvoicesListPage, CustTable
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 2cd576458bab1e4654d21773b581a5b0f726c928
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2019
ms.locfileid: "339800"
---
# <a name="create-a-write-off-journal-for-a-customer"></a><span data-ttu-id="d3d68-103">Criar um diário de baixa para um cliente</span><span class="sxs-lookup"><span data-stu-id="d3d68-103">Create a write-off journal for a customer</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="d3d68-104">Esta guia de tarefa mostrará como configurar parâmetros de baixas contábeis e dar baixa em transações da página das coleções, a página inicial das notas fiscais de clientes, e a página do cliente.</span><span class="sxs-lookup"><span data-stu-id="d3d68-104">This task guide will show you how to set up the parameters for write-offs and then write off transactions from the Collections page, the Open customer invoices page, and the Customer page.</span></span> <span data-ttu-id="d3d68-105">Esta tarefa usa a empresa de demonstração USMF.</span><span class="sxs-lookup"><span data-stu-id="d3d68-105">This task uses the USMF demo company.</span></span>


## <a name="set-up-the-write-off-parameters"></a><span data-ttu-id="d3d68-106">Configurar os parâmetros de dar baixa</span><span class="sxs-lookup"><span data-stu-id="d3d68-106">Set up the write off parameters</span></span>
1. <span data-ttu-id="d3d68-107">Vá para Crédito e coleções > Configuração > Parâmetros de contas a pagar.</span><span class="sxs-lookup"><span data-stu-id="d3d68-107">Go to Credit and collections > Setup > Accounts receivable parameters.</span></span>
2. <span data-ttu-id="d3d68-108">Clique na guia Coleções.</span><span class="sxs-lookup"><span data-stu-id="d3d68-108">Click the Collections tab.</span></span>
3. <span data-ttu-id="d3d68-109">Expanda ou recolha a seção Dar baixa.</span><span class="sxs-lookup"><span data-stu-id="d3d68-109">Expand or collapse the Write-off section.</span></span>
    * <span data-ttu-id="d3d68-110">O diário de valores é o diário geral que reterá as transações de baixa que você criar.</span><span class="sxs-lookup"><span data-stu-id="d3d68-110">The Write-off journal is the general journal that will hold the write-off transactions that you create.</span></span>  
    * <span data-ttu-id="d3d68-111">Você pode anexar um código de motivo para cada amortização.</span><span class="sxs-lookup"><span data-stu-id="d3d68-111">You can attach a reason code to every write-off.</span></span> <span data-ttu-id="d3d68-112">Você pode sobrepor este padrão no momento de dar baixa.</span><span class="sxs-lookup"><span data-stu-id="d3d68-112">You can override this default at the time of the write-off.</span></span>  
    * <span data-ttu-id="d3d68-113">Defina o como Sim se desejar separar os impostos sobre vendas da transação original na amortização.</span><span class="sxs-lookup"><span data-stu-id="d3d68-113">Set this to Yes if you want to separate the sales tax from the original transaction in the write-off.</span></span>  
4. <span data-ttu-id="d3d68-114">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="d3d68-114">Close the page.</span></span>
5. <span data-ttu-id="d3d68-115">Vá para Crédito e coleções > Configuração > Perfis de lançamento de cliente.</span><span class="sxs-lookup"><span data-stu-id="d3d68-115">Go to Credit and collections > Setup > Customer posting profiles.</span></span>
    * <span data-ttu-id="d3d68-116">A amortização de conta será usada como o ajuste da conta de despesas de reserva ou no diário geral</span><span class="sxs-lookup"><span data-stu-id="d3d68-116">The write-off account will be used as the expense account or reserve adjustment in the general journal</span></span>   
6. <span data-ttu-id="d3d68-117">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="d3d68-117">Close the page.</span></span>

## <a name="write-off-a-customer-balance-from-the-aged-balances-page"></a><span data-ttu-id="d3d68-118">Dar baixa de um saldo do cliente de página de saldos antiga</span><span class="sxs-lookup"><span data-stu-id="d3d68-118">Write off a customer balance from the aged balances page</span></span>
1. <span data-ttu-id="d3d68-119">Vá para Crédito e coleções > Cobranças > Saldos antigos.</span><span class="sxs-lookup"><span data-stu-id="d3d68-119">Go to Credit and collections > Collections > Aged balances.</span></span>
2. <span data-ttu-id="d3d68-120">Marque a linha do cliente que deseja dar baixa.</span><span class="sxs-lookup"><span data-stu-id="d3d68-120">Mark the row for the customer that you want to write off.</span></span> <span data-ttu-id="d3d68-121">Por exemplo, marcar a linha com Vidoeiro de empresa nela.</span><span class="sxs-lookup"><span data-stu-id="d3d68-121">For example, mark the line with Birch Company on it.</span></span>
3. <span data-ttu-id="d3d68-122">No Painel de Ação, clique em Coletar.</span><span class="sxs-lookup"><span data-stu-id="d3d68-122">On the Action Pane, click Collect.</span></span>
4. <span data-ttu-id="d3d68-123">Clique em Dar baixa.</span><span class="sxs-lookup"><span data-stu-id="d3d68-123">Click Write off.</span></span>
5. <span data-ttu-id="d3d68-124">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="d3d68-124">Click OK.</span></span>
6. <span data-ttu-id="d3d68-125">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="d3d68-125">Close the page.</span></span>
7. <span data-ttu-id="d3d68-126">Ir para Contabilidade > Entradas de diários > Diários gerais.</span><span class="sxs-lookup"><span data-stu-id="d3d68-126">Go to General ledger > Journal entries > General journals.</span></span>
8. <span data-ttu-id="d3d68-127">Selecione o número do lote do diário para o diário que contém a amortização.</span><span class="sxs-lookup"><span data-stu-id="d3d68-127">Select the journal batch number for the journal that contains your write-off.</span></span>
    * <span data-ttu-id="d3d68-128">Uma linha é criada para reverter o saldo do cliente.</span><span class="sxs-lookup"><span data-stu-id="d3d68-128">One line is created to reverse the customer balance.</span></span> <span data-ttu-id="d3d68-129">Uma ou mais linhas são criadas para lançar a amortização na conta de valores.</span><span class="sxs-lookup"><span data-stu-id="d3d68-129">One or more lines are created to post the write-off to the write-off account.</span></span>  
9. <span data-ttu-id="d3d68-130">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="d3d68-130">Close the page.</span></span>
10. <span data-ttu-id="d3d68-131">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="d3d68-131">Close the page.</span></span>

## <a name="write-off-transactions-from-the-collections-form"></a><span data-ttu-id="d3d68-132">Dar baixa nas transações do formulário das coleções.</span><span class="sxs-lookup"><span data-stu-id="d3d68-132">Write off transactions from the collections form.</span></span>
1. <span data-ttu-id="d3d68-133">Vá para Crédito e coleções > Cobranças > Saldos antigos.</span><span class="sxs-lookup"><span data-stu-id="d3d68-133">Go to Credit and collections > Collections > Aged balances.</span></span>
2. <span data-ttu-id="d3d68-134">Selecione o nome do cliente que tem as transações que deseja dar baixa.</span><span class="sxs-lookup"><span data-stu-id="d3d68-134">Select the name of the customer that has the transactions that you want to write off.</span></span> <span data-ttu-id="d3d68-135">Por exemplo, selecione Vendas por atacado da cavidade (US-004).</span><span class="sxs-lookup"><span data-stu-id="d3d68-135">For example, select Cave Wholesales (US-004).</span></span>
3. <span data-ttu-id="d3d68-136">Marcar a linha como a primeira transação.</span><span class="sxs-lookup"><span data-stu-id="d3d68-136">Mark the row for the first transaction.</span></span>
4. <span data-ttu-id="d3d68-137">Marcar a linha como a segunda transação.</span><span class="sxs-lookup"><span data-stu-id="d3d68-137">Mark the row for the second transaction.</span></span>
5. <span data-ttu-id="d3d68-138">Clique em Dar baixa.</span><span class="sxs-lookup"><span data-stu-id="d3d68-138">Click Write off.</span></span>
6. <span data-ttu-id="d3d68-139">No campo de comentário do Razão, insira 'Débitos ruins'.</span><span class="sxs-lookup"><span data-stu-id="d3d68-139">In the Reason comment field, type 'Bad debts'.</span></span>
7. <span data-ttu-id="d3d68-140">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="d3d68-140">Click OK.</span></span>
8. <span data-ttu-id="d3d68-141">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="d3d68-141">Close the page.</span></span>
9. <span data-ttu-id="d3d68-142">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="d3d68-142">Close the page.</span></span>
10. <span data-ttu-id="d3d68-143">Ir para Contabilidade > Entradas de diários > Diários gerais.</span><span class="sxs-lookup"><span data-stu-id="d3d68-143">Go to General ledger > Journal entries > General journals.</span></span>
11. <span data-ttu-id="d3d68-144">Selecione o número do lote do diário para o diário que contém a amortização.</span><span class="sxs-lookup"><span data-stu-id="d3d68-144">Select the journal batch number for the journal that contains your write-off.</span></span>
    * <span data-ttu-id="d3d68-145">Uma linha é criada para reverter o saldo do cliente.</span><span class="sxs-lookup"><span data-stu-id="d3d68-145">One line is created to reverse the customer balance.</span></span> <span data-ttu-id="d3d68-146">Uma ou mais linhas são criadas para lançar a amortização na conta de valores.</span><span class="sxs-lookup"><span data-stu-id="d3d68-146">One or more lines are created to post the write-off to the write-off account.</span></span>  
12. <span data-ttu-id="d3d68-147">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="d3d68-147">Close the page.</span></span>
13. <span data-ttu-id="d3d68-148">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="d3d68-148">Close the page.</span></span>

## <a name="write-off-an-invoice-from-the-open-customers-invoices-page"></a><span data-ttu-id="d3d68-149">Dar baixa em uma nota fiscal da página de notas fiscais de clientes em Aberto</span><span class="sxs-lookup"><span data-stu-id="d3d68-149">Write off an invoice from the Open customers invoices page</span></span>
1. <span data-ttu-id="d3d68-150">Vá para Contas recebíveis > Faturas > Faturas de cliente abertas.</span><span class="sxs-lookup"><span data-stu-id="d3d68-150">Go to Accounts receivable > Invoices > Open customer invoices.</span></span>
2. <span data-ttu-id="d3d68-151">Marcar a linha de uma fatura.</span><span class="sxs-lookup"><span data-stu-id="d3d68-151">Mark the line for an invoice.</span></span> <span data-ttu-id="d3d68-152">Por exemplo, marcar a linha de CIV-000667.</span><span class="sxs-lookup"><span data-stu-id="d3d68-152">For example, mark the line for CIV-000667.</span></span>
3. <span data-ttu-id="d3d68-153">No Painel de Ação, clique em Fatura.</span><span class="sxs-lookup"><span data-stu-id="d3d68-153">On the Action Pane, click Invoice.</span></span>
4. <span data-ttu-id="d3d68-154">Clique em Dar baixa.</span><span class="sxs-lookup"><span data-stu-id="d3d68-154">Click Write off.</span></span>
5. <span data-ttu-id="d3d68-155">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="d3d68-155">Click OK.</span></span>
6. <span data-ttu-id="d3d68-156">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="d3d68-156">Close the page.</span></span>

## <a name="write-off-a-customer-balance-from-the-customer-page"></a><span data-ttu-id="d3d68-157">Dar baixa no saldo de um cliente na página do cliente</span><span class="sxs-lookup"><span data-stu-id="d3d68-157">Write off a customer balance from the customer page</span></span>
1. <span data-ttu-id="d3d68-158">Ir para Contas recebíveis > Clientes > Todos os clientes.</span><span class="sxs-lookup"><span data-stu-id="d3d68-158">Go to Accounts receivable > Customers > All customers.</span></span>
2. <span data-ttu-id="d3d68-159">Selecione uma conta de cliente.</span><span class="sxs-lookup"><span data-stu-id="d3d68-159">Select a customer account.</span></span> <span data-ttu-id="d3d68-160">Por exemplo, selecione US-001 (Contoso Retail de São Diego).</span><span class="sxs-lookup"><span data-stu-id="d3d68-160">For example, select US-001 (Contoso Retail San Diego).</span></span>
3. <span data-ttu-id="d3d68-161">No Painel de Ação, clique em Coletar.</span><span class="sxs-lookup"><span data-stu-id="d3d68-161">On the Action Pane, click Collect.</span></span>
4. <span data-ttu-id="d3d68-162">Clique em Dar baixa.</span><span class="sxs-lookup"><span data-stu-id="d3d68-162">Click Write off.</span></span>
5. <span data-ttu-id="d3d68-163">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="d3d68-163">Click OK.</span></span>
6. <span data-ttu-id="d3d68-164">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="d3d68-164">Close the page.</span></span>

