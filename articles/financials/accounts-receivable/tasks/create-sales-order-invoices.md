--- 
title: Criar faturas de ordem de venda
description: Este guia descreve a tarefa de uma ordem de venda, incluindo mescla de notas fiscais e processamento em lotes.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 11/10/2016
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
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 4b72d5b283f9401d358ee68f4650c486ebb2fd7d
ms.contentlocale: pt-br
ms.lasthandoff: 08/29/2017

---
# <a name="create-sales-order-invoices"></a><span data-ttu-id="660b0-103">Criar faturas de ordem de venda</span><span class="sxs-lookup"><span data-stu-id="660b0-103">Create sales order invoices</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="660b0-104">Este guia descreve a tarefa de uma ordem de venda, incluindo mescla de notas fiscais e processamento em lotes.</span><span class="sxs-lookup"><span data-stu-id="660b0-104">This task guide describes invoicing a sales order, including merging invoices and batch processing.</span></span> <span data-ttu-id="660b0-105">Este procedimento usa a empresa de dados de demonstração USMF.</span><span class="sxs-lookup"><span data-stu-id="660b0-105">This procedure uses the USMF demo company.</span></span>


## <a name="create-an-invoice-from-a-sales-order"></a><span data-ttu-id="660b0-106">Criar uma fatura de uma ordem de venda</span><span class="sxs-lookup"><span data-stu-id="660b0-106">Create an invoice from a sales order</span></span>
1. <span data-ttu-id="660b0-107">Vá para Contas a receber > Ordens > Ordens de venda enviadas mas não faturadas.</span><span class="sxs-lookup"><span data-stu-id="660b0-107">Go to Accounts receivable > Orders > Shipped but not invoiced sales orders.</span></span>
2. <span data-ttu-id="660b0-108">Selecione uma ordem de venda na lista.</span><span class="sxs-lookup"><span data-stu-id="660b0-108">Select a sales order in the list.</span></span> 
3. <span data-ttu-id="660b0-109">No Painel de Ação, clique em Fatura.</span><span class="sxs-lookup"><span data-stu-id="660b0-109">On the Action Pane, click Invoice.</span></span>
4. <span data-ttu-id="660b0-110">Clique em Fatura.</span><span class="sxs-lookup"><span data-stu-id="660b0-110">Click Invoice.</span></span>
    * <span data-ttu-id="660b0-111">Observe que a ordem de venda tem várias guias de remessa associadas a ela.</span><span class="sxs-lookup"><span data-stu-id="660b0-111">Note that this sales order has multiple packing slips associated with it.</span></span> <span data-ttu-id="660b0-112">Ela mostrará apenas a palavra <multiple>, em vez do número da guia de remessa.</span><span class="sxs-lookup"><span data-stu-id="660b0-112">It will only show the word <multiple> instead of the packing slip number.</span></span>  
5. <span data-ttu-id="660b0-113">Expanda a seção Parâmetros.</span><span class="sxs-lookup"><span data-stu-id="660b0-113">Expand the Parameters section.</span></span>
    * <span data-ttu-id="660b0-114">O lançamento deve ser definido como Sim para lançar a fatura.</span><span class="sxs-lookup"><span data-stu-id="660b0-114">Posting must be set to Yes to post the invoice.</span></span> <span data-ttu-id="660b0-115">Também é possível desativar o lançamento e imprimir apenas a nota fiscal.</span><span class="sxs-lookup"><span data-stu-id="660b0-115">You can also turn off posting and just print the invoice.</span></span> <span data-ttu-id="660b0-116">No entanto, você pode realizar o mesmo resultado criando uma nota fiscal do formulário em vez de uma nota fiscal.</span><span class="sxs-lookup"><span data-stu-id="660b0-116">However, you can accomplish the same result by creating a proforma invoice instead of an invoice.</span></span>  
    * <span data-ttu-id="660b0-117">Essa opção é usada para trabalhos em lotes.</span><span class="sxs-lookup"><span data-stu-id="660b0-117">This option is used for batch jobs.</span></span> <span data-ttu-id="660b0-118">A consulta será executada quando o trabalho em lotes for executado.</span><span class="sxs-lookup"><span data-stu-id="660b0-118">The query is run when the batch job is run.</span></span>    
6. <span data-ttu-id="660b0-119">No campo Imprimir, selecione 'Depois'.</span><span class="sxs-lookup"><span data-stu-id="660b0-119">In the Print field, select 'After'.</span></span>
7. <span data-ttu-id="660b0-120">Selecione Sim para imprimir nota fiscal.</span><span class="sxs-lookup"><span data-stu-id="660b0-120">Select Yes for Print invoice.</span></span>
    * <span data-ttu-id="660b0-121">O gerenciamento de impressão pode imprimir várias cópias de notas fiscais e também enviar a nota fiscal por email como um arquivo PDF.</span><span class="sxs-lookup"><span data-stu-id="660b0-121">Print management can print  multiple copies of the invoice and also send the invoice via email as a PDF file.</span></span>  
8. <span data-ttu-id="660b0-122">No campo Imprimir cobranças, selecione 'Resumir'.</span><span class="sxs-lookup"><span data-stu-id="660b0-122">In the Print charges field, select 'Summarize'.</span></span>
9. <span data-ttu-id="660b0-123">No campo Limite de crédito do cheque, selecione 'Saldo'.</span><span class="sxs-lookup"><span data-stu-id="660b0-123">In the Check credit limit field, select 'Balance'.</span></span>
10. <span data-ttu-id="660b0-124">Clique em Cancelar.</span><span class="sxs-lookup"><span data-stu-id="660b0-124">Click Cancel.</span></span>

## <a name="combine-orders-into-a-single-invoice"></a><span data-ttu-id="660b0-125">Combinar ordens em uma única nota fiscal</span><span class="sxs-lookup"><span data-stu-id="660b0-125">Combine orders into a single invoice</span></span>
1. <span data-ttu-id="660b0-126">Vá para Contas a receber > Ordens > Todas as ordens de venda.</span><span class="sxs-lookup"><span data-stu-id="660b0-126">Go to Accounts receivable > Orders > All sales orders.</span></span>
2. <span data-ttu-id="660b0-127">Localize um cliente que tem várias notas fiscais abertas.</span><span class="sxs-lookup"><span data-stu-id="660b0-127">Locate a customer that has multiple invoices open.</span></span>
3. <span data-ttu-id="660b0-128">Selecione uma ordem de venda aberta.</span><span class="sxs-lookup"><span data-stu-id="660b0-128">Select an open sales order.</span></span>
4. <span data-ttu-id="660b0-129">Selecionar outra ordem de venda aberta para o mesmo cliente.</span><span class="sxs-lookup"><span data-stu-id="660b0-129">Select another open sales order for the same customer.</span></span>
5. <span data-ttu-id="660b0-130">No Painel de Ação, clique em Fatura.</span><span class="sxs-lookup"><span data-stu-id="660b0-130">On the Action Pane, click Invoice.</span></span>
6. <span data-ttu-id="660b0-131">Clique em Fatura.</span><span class="sxs-lookup"><span data-stu-id="660b0-131">Click Invoice.</span></span>
7. <span data-ttu-id="660b0-132">Expanda a seção Parâmetros.</span><span class="sxs-lookup"><span data-stu-id="660b0-132">Expand the Parameters section.</span></span>
8. <span data-ttu-id="660b0-133">No campo Quantidade, selecione 'Tudo'.</span><span class="sxs-lookup"><span data-stu-id="660b0-133">In the Quantity field, select 'All'.</span></span>
    * <span data-ttu-id="660b0-134">Observe que há duas notas fiscais listadas na seção da visão geral.</span><span class="sxs-lookup"><span data-stu-id="660b0-134">Note that there are two invoices listed in the overview section.</span></span> <span data-ttu-id="660b0-135">Deixe-nos agora mescla-los em uma única nota fiscal.</span><span class="sxs-lookup"><span data-stu-id="660b0-135">Now let's merge them into a single invoice.</span></span>  
9. <span data-ttu-id="660b0-136">No campo Atualização de conteúdo, seleciona 'Contabilidade de fatura'.</span><span class="sxs-lookup"><span data-stu-id="660b0-136">In the Summary update for field, select 'Invoice account'.</span></span>
10. <span data-ttu-id="660b0-137">Clique em Organizar para mesclar as ordens de venda em uma única fatura.</span><span class="sxs-lookup"><span data-stu-id="660b0-137">Click Arrange to merge the sales orders into a single invoice.</span></span>
    * <span data-ttu-id="660b0-138">As dois ordens de venda são mescladas agora em uma única nota fiscal.</span><span class="sxs-lookup"><span data-stu-id="660b0-138">The two sales orders are now merged into a single invoice.</span></span>   
11. <span data-ttu-id="660b0-139">Clique em Cancelar.</span><span class="sxs-lookup"><span data-stu-id="660b0-139">Click Cancel.</span></span>
12. <span data-ttu-id="660b0-140">Clique em Sim.</span><span class="sxs-lookup"><span data-stu-id="660b0-140">Click Yes.</span></span>

## <a name="post-invoices-in-a-batch"></a><span data-ttu-id="660b0-141">Lançar notas fiscais em um lote</span><span class="sxs-lookup"><span data-stu-id="660b0-141">Post invoices in a batch</span></span>
1. <span data-ttu-id="660b0-142">Vá para Contas a receber > Faturas > Faturamento em lote > Fatura.</span><span class="sxs-lookup"><span data-stu-id="660b0-142">Go to Accounts receivable > Invoices > Batch invoicing > Invoice.</span></span>
2. <span data-ttu-id="660b0-143">Clique em Selecionar.</span><span class="sxs-lookup"><span data-stu-id="660b0-143">Click Select.</span></span>
3. <span data-ttu-id="660b0-144">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="660b0-144">Click OK.</span></span>
4. <span data-ttu-id="660b0-145">Clique em Lote.</span><span class="sxs-lookup"><span data-stu-id="660b0-145">Click Batch.</span></span>
5. <span data-ttu-id="660b0-146">Clique em Sim para ativar o processamento em lotes.</span><span class="sxs-lookup"><span data-stu-id="660b0-146">Click on Yes to turn on batch processing.</span></span>
6. <span data-ttu-id="660b0-147">Clique em Recorrência.</span><span class="sxs-lookup"><span data-stu-id="660b0-147">Click Recurrence.</span></span>
7. <span data-ttu-id="660b0-148">Selecionar dias</span><span class="sxs-lookup"><span data-stu-id="660b0-148">Select Days</span></span>
8. <span data-ttu-id="660b0-149">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="660b0-149">Click OK.</span></span>
9. <span data-ttu-id="660b0-150">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="660b0-150">Click OK.</span></span>
10. <span data-ttu-id="660b0-151">Clique em Cancelar.</span><span class="sxs-lookup"><span data-stu-id="660b0-151">Click Cancel.</span></span>
11. <span data-ttu-id="660b0-152">Clique em Sim.</span><span class="sxs-lookup"><span data-stu-id="660b0-152">Click Yes.</span></span>


