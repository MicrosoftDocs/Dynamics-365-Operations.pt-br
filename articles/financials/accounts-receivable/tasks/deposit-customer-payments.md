--- 
title: Depositar pagamentos de cliente
description: Depositar pagamentos de cliente.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 1d98cbff30620256c9d13e7b4a90314db150e33e
ms.openlocfilehash: f1f8ddb4b18e4e06fe0a7307ceadf8063d8eba07
ms.contentlocale: pt-br
ms.lasthandoff: 08/07/2018

---
# <a name="deposit-customer-payments"></a><span data-ttu-id="09d71-103">Depositar pagamentos de cliente</span><span class="sxs-lookup"><span data-stu-id="09d71-103">Deposit customer payments</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="09d71-104">Depositar pagamentos de cliente.</span><span class="sxs-lookup"><span data-stu-id="09d71-104">Deposit customer payments.</span></span> <span data-ttu-id="09d71-105">Esta tarefa usa a empresa de demonstração USMF.</span><span class="sxs-lookup"><span data-stu-id="09d71-105">This task uses the USMF demo company.</span></span>

1. <span data-ttu-id="09d71-106">Vá para Contas a receber > Pagamentos > Diário de pagamentos.</span><span class="sxs-lookup"><span data-stu-id="09d71-106">Go to Accounts receivable > Payments > Payment journal.</span></span>
2. <span data-ttu-id="09d71-107">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="09d71-107">Click New.</span></span>
3. <span data-ttu-id="09d71-108">No campo Nome, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="09d71-108">In the Name field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="09d71-109">Selecione o diário de pagamentos.</span><span class="sxs-lookup"><span data-stu-id="09d71-109">Select the payment journal.</span></span> 
5. <span data-ttu-id="09d71-110">Clique em Linhas.</span><span class="sxs-lookup"><span data-stu-id="09d71-110">Click Lines.</span></span>
6. <span data-ttu-id="09d71-111">No campo Conta, selecione o Cliente para o qual você está registrando o pagamento.</span><span class="sxs-lookup"><span data-stu-id="09d71-111">In the Account field, select the Customer for whom you are recording the payment.</span></span>
7. <span data-ttu-id="09d71-112">No campo Crédito, insira o valor do pagamento.</span><span class="sxs-lookup"><span data-stu-id="09d71-112">In the Credit field, enter the amount of the payment.</span></span>
    * <span data-ttu-id="09d71-113">Você pode optar por manter o valor em branco, e fazer com que o sistema o calcule selecionando as faturas que foram pagas.</span><span class="sxs-lookup"><span data-stu-id="09d71-113">You can choose to leave the amount blank, and have the system calculate it by selecting the invoices which were paid.</span></span>  
8. <span data-ttu-id="09d71-114">No campo Referência de pagamento, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="09d71-114">In the Payment reference field, type a value.</span></span>
    * <span data-ttu-id="09d71-115">A referência de pagamento pode ser o número do cheque para pagamento que você está inserindo.</span><span class="sxs-lookup"><span data-stu-id="09d71-115">The payment reference could be the check number for the payment you are entering.</span></span> <span data-ttu-id="09d71-116">A referência do pagamento é necessária para incluir o pagamento em um comprovante de pagamento.</span><span class="sxs-lookup"><span data-stu-id="09d71-116">The payment reference is required in order to include the payment on a deposit slip.</span></span>  
9. <span data-ttu-id="09d71-117">Marque a caixa Usar uma guia de depósito.</span><span class="sxs-lookup"><span data-stu-id="09d71-117">Mark the box Use a deposit slip.</span></span>
    * <span data-ttu-id="09d71-118">Se o pagamento for incluído no depósito, altere essa configuração para Sim.</span><span class="sxs-lookup"><span data-stu-id="09d71-118">If the payment should be included in the deposit, change this setting to Yes.</span></span>  
10. <span data-ttu-id="09d71-119">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="09d71-119">Click New.</span></span>
11. <span data-ttu-id="09d71-120">No campo Conta, selecione o Cliente para o próximo pagamento.</span><span class="sxs-lookup"><span data-stu-id="09d71-120">In the Account field, select the Customer for the next payment.</span></span>
12. <span data-ttu-id="09d71-121">No campo Crédito, insira o valor do pagamento.</span><span class="sxs-lookup"><span data-stu-id="09d71-121">In the Credit field, enter the payment amount.</span></span>
13. <span data-ttu-id="09d71-122">No campo Referência de pagamento, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="09d71-122">In the Payment reference field, type a value.</span></span>
14. <span data-ttu-id="09d71-123">Marque a caixa Usar uma guia de depósito.</span><span class="sxs-lookup"><span data-stu-id="09d71-123">Mark the box Use a deposit slip.</span></span>
15. <span data-ttu-id="09d71-124">Clique em Lançar.</span><span class="sxs-lookup"><span data-stu-id="09d71-124">Click Post.</span></span>
    * <span data-ttu-id="09d71-125">Os pagamentos devem ser lançados antes que a guia de depósito possa ser gerada.</span><span class="sxs-lookup"><span data-stu-id="09d71-125">Payments must be posted before the deposit slip can be generated.</span></span> <span data-ttu-id="09d71-126">Isso garante que os pagamentos não se alterem depois que a guia de depósito for gerada.</span><span class="sxs-lookup"><span data-stu-id="09d71-126">This is to ensure that the payments don't change after the deposit slip is generated.</span></span>  
16. <span data-ttu-id="09d71-127">Clique em Funções.</span><span class="sxs-lookup"><span data-stu-id="09d71-127">Click Functions.</span></span>
17. <span data-ttu-id="09d71-128">Clique em guia de depósito.</span><span class="sxs-lookup"><span data-stu-id="09d71-128">Click Deposit slip.</span></span>
18. <span data-ttu-id="09d71-129">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="09d71-129">Click OK.</span></span>
    * <span data-ttu-id="09d71-130">A primeira página é usada para criar a guia de depósito.</span><span class="sxs-lookup"><span data-stu-id="09d71-130">The first page is used to create the deposit slip.</span></span>  
19. <span data-ttu-id="09d71-131">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="09d71-131">Click OK.</span></span>
    * <span data-ttu-id="09d71-132">A segunda etapa é imprimir a guia de depósito, mas essa etapa não é necessária.</span><span class="sxs-lookup"><span data-stu-id="09d71-132">The second step is to print the deposit slip, but this step is not required.</span></span>  


