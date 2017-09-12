--- 
title: "Visão geral de pagamentos do cliente"
description: "Este guia de tarefas apresenta vários métodos utilizados para inserir pagamentos de clientes."
author: kweekley
manager: AnnBe
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: e6e10d0d0a05b0594ba5cf6a77f474b461bd9dca
ms.contentlocale: pt-br
ms.lasthandoff: 08/29/2017

---
# <a name="customer-payment-overview"></a><span data-ttu-id="f8797-103">Visão geral de pagamentos do cliente</span><span class="sxs-lookup"><span data-stu-id="f8797-103">Customer payment overview</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="f8797-104">Este guia de tarefas apresenta vários métodos utilizados para inserir pagamentos de clientes.</span><span class="sxs-lookup"><span data-stu-id="f8797-104">This task guide walks through various methods used to enter customer payments.</span></span> <span data-ttu-id="f8797-105">Esta tarefa usa a empresa de demonstração USMF.</span><span class="sxs-lookup"><span data-stu-id="f8797-105">This task uses the USMF demo company.</span></span>

1. <span data-ttu-id="f8797-106">Vá para Contas a receber > Pagamentos > Diário de pagamentos.</span><span class="sxs-lookup"><span data-stu-id="f8797-106">Go to Accounts receivable > Payments > Payment journal.</span></span>
2. <span data-ttu-id="f8797-107">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="f8797-107">Click New.</span></span>
3. <span data-ttu-id="f8797-108">Selecione o diário de pagamentos onde os pagamentos do cliente serão salvos.</span><span class="sxs-lookup"><span data-stu-id="f8797-108">Select the payment journal which the customer payments will be saved.</span></span>
4. <span data-ttu-id="f8797-109">Selecione ou insira manualmente o diário.</span><span class="sxs-lookup"><span data-stu-id="f8797-109">Select or manually enter the journal.</span></span>
5. <span data-ttu-id="f8797-110">Clique em Inserir pagamentos de cliente.</span><span class="sxs-lookup"><span data-stu-id="f8797-110">Click Enter customer payments.</span></span>
    * <span data-ttu-id="f8797-111">Inserir pagamentos de cliente é usado para registrar um pagamento de cliente por vez.</span><span class="sxs-lookup"><span data-stu-id="f8797-111">Enter customer payments is used to record one customer payment at a time.</span></span> <span data-ttu-id="f8797-112">Você insere as informações de pagamento na parte superior e, em seguida, pode marcar as faturas que foram pagas por este pagamento, todas da mesma página.</span><span class="sxs-lookup"><span data-stu-id="f8797-112">You enter the payment information at the top, and then you can mark the invoices that were paid by the payment, all from the same page.</span></span>  
6. <span data-ttu-id="f8797-113">Insira o cliente do qual o pagamento foi recebido.</span><span class="sxs-lookup"><span data-stu-id="f8797-113">Enter the customer from whom you received the payment.</span></span>
    * <span data-ttu-id="f8797-114">Se você não sabe qual é o cliente mas tem informações de uma transação que foi paga, pode usar o campo Transação para inserir o pagamento.</span><span class="sxs-lookup"><span data-stu-id="f8797-114">If you don't know the customer but do know a transaction that was paid, you can use the Transaction field to enter the payment.</span></span> <span data-ttu-id="f8797-115">Insira ou selecione a fatura no campo Transação.</span><span class="sxs-lookup"><span data-stu-id="f8797-115">Enter or select the invoice in the Transaction field.</span></span> <span data-ttu-id="f8797-116">O cliente será inserido automaticamente depois que você selecionar a transação.</span><span class="sxs-lookup"><span data-stu-id="f8797-116">The customer will automatically default after you select the transaction.</span></span>  
7. <span data-ttu-id="f8797-117">No campo Referência de pagamento, insira uma referência de pagamento.</span><span class="sxs-lookup"><span data-stu-id="f8797-117">In the Payment reference field, enter a payment reference.</span></span>
    * <span data-ttu-id="f8797-118">A referência do pagamento pode ser o número do cheque do cliente ou uma referência do pagamento eletrônico do cliente.</span><span class="sxs-lookup"><span data-stu-id="f8797-118">The payment reference could be the customer's check number or a reference from the customer's electronic payment.</span></span> <span data-ttu-id="f8797-119">A referência do pagamento é necessária somente se você marcar para incluir o pagamento em uma guia de depósito.</span><span class="sxs-lookup"><span data-stu-id="f8797-119">The payment reference is only required if you mark to include the payment on a deposit slip.</span></span>  
8. <span data-ttu-id="f8797-120">Selecione se o pagamento será incluído em uma guia de depósito.</span><span class="sxs-lookup"><span data-stu-id="f8797-120">Select whether the payment will be included on a deposit slip.</span></span> 
9. <span data-ttu-id="f8797-121">Insira o valor do pagamento do cliente.</span><span class="sxs-lookup"><span data-stu-id="f8797-121">Enter the amount of the customer payment.</span></span>
    * <span data-ttu-id="f8797-122">O valor do pagamento não será inserido automaticamente.</span><span class="sxs-lookup"><span data-stu-id="f8797-122">The payment amount will not default.</span></span> <span data-ttu-id="f8797-123">Ele deve ser inserido manualmente.</span><span class="sxs-lookup"><span data-stu-id="f8797-123">It must be manually entered.</span></span>  
10. <span data-ttu-id="f8797-124">Marque as faturas que foram pagas pelo cliente.</span><span class="sxs-lookup"><span data-stu-id="f8797-124">Mark the invoices that were paid by the customer.</span></span>
    * <span data-ttu-id="f8797-125">Se este for um pagamento antecipado, não é necessário marcar nenhuma fatura para liquidação.</span><span class="sxs-lookup"><span data-stu-id="f8797-125">If the payment is a prepayment, you are not required to mark any invoices for settlement.</span></span> <span data-ttu-id="f8797-126">O pagamento ainda pode ser salvo e lançado.</span><span class="sxs-lookup"><span data-stu-id="f8797-126">The payment can still be saved and posted.</span></span> <span data-ttu-id="f8797-127">A liquidação de uma fatura pode ocorrer posteriormente.</span><span class="sxs-lookup"><span data-stu-id="f8797-127">Settlement to an invoice can happen at a later time.</span></span>  
11. <span data-ttu-id="f8797-128">Insira o valor do pagamento que deve ser liquidado à fatura marcada.</span><span class="sxs-lookup"><span data-stu-id="f8797-128">Enter the amount of the payment that should be settled to the marked invoice.</span></span> 
    * <span data-ttu-id="f8797-129">Este campo pode ser usado quando o pagamento for para um pagamento parcial.</span><span class="sxs-lookup"><span data-stu-id="f8797-129">This field can be used when the payment is for a partial payment.</span></span> <span data-ttu-id="f8797-130">Se você não inserir um valor, o valor a ser liquidado será definido automaticamente para você.</span><span class="sxs-lookup"><span data-stu-id="f8797-130">If you don't enter an amount, the amount to settle will automatically be determined for you.</span></span>  
12. <span data-ttu-id="f8797-131">Clique em Salvar no diário.</span><span class="sxs-lookup"><span data-stu-id="f8797-131">Click Save in journal.</span></span>
    * <span data-ttu-id="f8797-132">Antes de salvar o pagamento no diário, verifique se a contrapartida está definida.</span><span class="sxs-lookup"><span data-stu-id="f8797-132">Before you save the payment to the journal, make sure that the offset account is defined.</span></span> <span data-ttu-id="f8797-133">Se você usar Salvar no diário, o pagamento será salvo e movido para o diário.</span><span class="sxs-lookup"><span data-stu-id="f8797-133">Using Save in journal will save the payment and move it to the journal.</span></span> <span data-ttu-id="f8797-134">Você pode, em seguida, continuar inserindo o próximo pagamento.</span><span class="sxs-lookup"><span data-stu-id="f8797-134">You can then continue entering the next payment.</span></span>  
13. <span data-ttu-id="f8797-135">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="f8797-135">Close the page.</span></span>
14. <span data-ttu-id="f8797-136">Clique em Linhas.</span><span class="sxs-lookup"><span data-stu-id="f8797-136">Click Lines.</span></span>
    * <span data-ttu-id="f8797-137">Quando você abrir Linhas, verá todos os pagamentos que foram registrados na página Inserir pagamentos de cliente e salvos no diário.</span><span class="sxs-lookup"><span data-stu-id="f8797-137">When opening Lines, you will see any payments you recorded on the Enter customer payments page and saved into the journal.</span></span> <span data-ttu-id="f8797-138">Você também pode usar essa página para inserir novos pagamentos de cliente ou editar os pagamentos de cliente existentes antes que eles sejam lançados.</span><span class="sxs-lookup"><span data-stu-id="f8797-138">You can also use this page to enter new customer payments, or edit existing customer payment before they are posted.</span></span>  
15. <span data-ttu-id="f8797-139">Clique em Novo para criar um outro pagamento.</span><span class="sxs-lookup"><span data-stu-id="f8797-139">Click New to create another payment.</span></span> 
16. <span data-ttu-id="f8797-140">Selecione o cliente do qual o pagamento foi recebido.</span><span class="sxs-lookup"><span data-stu-id="f8797-140">Select the customer from whom you received the payment.</span></span>
    * <span data-ttu-id="f8797-141">Se você não sabe qual é o cliente mas tem as informações de uma fatura paga por este pagamento, use o campo Fatura para inserir manualmente ou selecionar a fatura.</span><span class="sxs-lookup"><span data-stu-id="f8797-141">If you don't know the customer but know an invoice paid by the payment, use the Invoice field to manually enter or select the invoice.</span></span> <span data-ttu-id="f8797-142">O cliente será definido como o padrão após a seleção da fatura.</span><span class="sxs-lookup"><span data-stu-id="f8797-142">The customer will default after the invoice is selected.</span></span>  
17. <span data-ttu-id="f8797-143">Clique em Liquidar transações para marcar as faturas que foram pagas.</span><span class="sxs-lookup"><span data-stu-id="f8797-143">Click Settle transctions to mark invoices that were paid.</span></span>
    * <span data-ttu-id="f8797-144">Você não precisa liquidar o pagamento de nenhuma fatura.</span><span class="sxs-lookup"><span data-stu-id="f8797-144">You are not required to settle the payment to any invoices.</span></span> <span data-ttu-id="f8797-145">Se este for um pagamento antecipado ou se você não souber qual fatura foi paga, você poderá inserir e lançar o pagamento.</span><span class="sxs-lookup"><span data-stu-id="f8797-145">If this is a prepayment or if you don't know what invoice was paid, you can enter and post the payment.</span></span> <span data-ttu-id="f8797-146">O pagamento pode ser liquidado em uma fatura posteriormente.</span><span class="sxs-lookup"><span data-stu-id="f8797-146">The payment can be settled to an invoice at a later point.</span></span>  
18. <span data-ttu-id="f8797-147">Marque as faturas pagas por este pagamento.</span><span class="sxs-lookup"><span data-stu-id="f8797-147">Mark the invoices paid by the payment.</span></span> 
19. <span data-ttu-id="f8797-148">Insira o valor do pagamento que será liquidado à fatura.</span><span class="sxs-lookup"><span data-stu-id="f8797-148">Enter the amount of the payment that will be settled to the invoice.</span></span>
20. <span data-ttu-id="f8797-149">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="f8797-149">Click OK.</span></span>
21. <span data-ttu-id="f8797-150">No campo Referência de pagamento, insira uma referência de pagamento.</span><span class="sxs-lookup"><span data-stu-id="f8797-150">In the Payment reference field, Enter a payment reference.</span></span> <span data-ttu-id="f8797-151">.</span><span class="sxs-lookup"><span data-stu-id="f8797-151">.</span></span>
    * <span data-ttu-id="f8797-152">A referência do pagamento é necessária somente se você marcar para incluir o pagamento em uma guia de depósito.</span><span class="sxs-lookup"><span data-stu-id="f8797-152">The payment reference is only required if you mark to include the payment on a deposit slip.</span></span>  
22. <span data-ttu-id="f8797-153">Lance os pagamentos do cliente.</span><span class="sxs-lookup"><span data-stu-id="f8797-153">Post the customer payments.</span></span> 


