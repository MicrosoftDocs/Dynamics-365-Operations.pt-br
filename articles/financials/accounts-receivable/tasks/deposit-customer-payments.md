---
title: Depositar pagamentos de cliente
description: Depositar pagamentos de cliente.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerJournalTable, LedgerJournalTransCustPaym, CustTableLookup
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f58cebce20e8516dc918e0bad1e020ffd7f791ee
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2019
ms.locfileid: "313373"
---
# <a name="deposit-customer-payments"></a><span data-ttu-id="a1660-103">Depositar pagamentos de cliente</span><span class="sxs-lookup"><span data-stu-id="a1660-103">Deposit customer payments</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="a1660-104">Depositar pagamentos de cliente.</span><span class="sxs-lookup"><span data-stu-id="a1660-104">Deposit customer payments.</span></span> <span data-ttu-id="a1660-105">Esta tarefa usa a empresa de demonstração USMF.</span><span class="sxs-lookup"><span data-stu-id="a1660-105">This task uses the USMF demo company.</span></span>

1. <span data-ttu-id="a1660-106">Vá para Contas a receber > Pagamentos > Diário de pagamentos.</span><span class="sxs-lookup"><span data-stu-id="a1660-106">Go to Accounts receivable > Payments > Payment journal.</span></span>
2. <span data-ttu-id="a1660-107">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="a1660-107">Click New.</span></span>
3. <span data-ttu-id="a1660-108">No campo Nome, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="a1660-108">In the Name field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="a1660-109">Selecione o diário de pagamentos.</span><span class="sxs-lookup"><span data-stu-id="a1660-109">Select the payment journal.</span></span> 
5. <span data-ttu-id="a1660-110">Clique em Linhas.</span><span class="sxs-lookup"><span data-stu-id="a1660-110">Click Lines.</span></span>
6. <span data-ttu-id="a1660-111">No campo Conta, selecione o Cliente para o qual você está registrando o pagamento.</span><span class="sxs-lookup"><span data-stu-id="a1660-111">In the Account field, select the Customer for whom you are recording the payment.</span></span>
7. <span data-ttu-id="a1660-112">No campo Crédito, insira o valor do pagamento.</span><span class="sxs-lookup"><span data-stu-id="a1660-112">In the Credit field, enter the amount of the payment.</span></span>
    * <span data-ttu-id="a1660-113">Você pode optar por manter o valor em branco, e fazer com que o sistema o calcule selecionando as faturas que foram pagas.</span><span class="sxs-lookup"><span data-stu-id="a1660-113">You can choose to leave the amount blank, and have the system calculate it by selecting the invoices which were paid.</span></span>  
8. <span data-ttu-id="a1660-114">No campo Referência de pagamento, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="a1660-114">In the Payment reference field, type a value.</span></span>
    * <span data-ttu-id="a1660-115">A referência de pagamento pode ser o número do cheque para pagamento que você está inserindo.</span><span class="sxs-lookup"><span data-stu-id="a1660-115">The payment reference could be the check number for the payment you are entering.</span></span> <span data-ttu-id="a1660-116">A referência do pagamento é necessária para incluir o pagamento em um comprovante de pagamento.</span><span class="sxs-lookup"><span data-stu-id="a1660-116">The payment reference is required in order to include the payment on a deposit slip.</span></span>  
9. <span data-ttu-id="a1660-117">Marque a caixa Usar uma guia de depósito.</span><span class="sxs-lookup"><span data-stu-id="a1660-117">Mark the box Use a deposit slip.</span></span>
    * <span data-ttu-id="a1660-118">Se o pagamento for incluído no depósito, altere essa configuração para Sim.</span><span class="sxs-lookup"><span data-stu-id="a1660-118">If the payment should be included in the deposit, change this setting to Yes.</span></span>  
10. <span data-ttu-id="a1660-119">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="a1660-119">Click New.</span></span>
11. <span data-ttu-id="a1660-120">No campo Conta, selecione o Cliente para o próximo pagamento.</span><span class="sxs-lookup"><span data-stu-id="a1660-120">In the Account field, select the Customer for the next payment.</span></span>
12. <span data-ttu-id="a1660-121">No campo Crédito, insira o valor do pagamento.</span><span class="sxs-lookup"><span data-stu-id="a1660-121">In the Credit field, enter the payment amount.</span></span>
13. <span data-ttu-id="a1660-122">No campo Referência de pagamento, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="a1660-122">In the Payment reference field, type a value.</span></span>
14. <span data-ttu-id="a1660-123">Marque a caixa Usar uma guia de depósito.</span><span class="sxs-lookup"><span data-stu-id="a1660-123">Mark the box Use a deposit slip.</span></span>
15. <span data-ttu-id="a1660-124">Clique em Lançar.</span><span class="sxs-lookup"><span data-stu-id="a1660-124">Click Post.</span></span>
    * <span data-ttu-id="a1660-125">Os pagamentos devem ser lançados antes que a guia de depósito possa ser gerada.</span><span class="sxs-lookup"><span data-stu-id="a1660-125">Payments must be posted before the deposit slip can be generated.</span></span> <span data-ttu-id="a1660-126">Isso garante que os pagamentos não se alterem depois que a guia de depósito for gerada.</span><span class="sxs-lookup"><span data-stu-id="a1660-126">This is to ensure that the payments don't change after the deposit slip is generated.</span></span>  
16. <span data-ttu-id="a1660-127">Clique em Funções.</span><span class="sxs-lookup"><span data-stu-id="a1660-127">Click Functions.</span></span>
17. <span data-ttu-id="a1660-128">Clique em guia de depósito.</span><span class="sxs-lookup"><span data-stu-id="a1660-128">Click Deposit slip.</span></span>
18. <span data-ttu-id="a1660-129">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="a1660-129">Click OK.</span></span>
    * <span data-ttu-id="a1660-130">A primeira página é usada para criar a guia de depósito.</span><span class="sxs-lookup"><span data-stu-id="a1660-130">The first page is used to create the deposit slip.</span></span>  
19. <span data-ttu-id="a1660-131">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="a1660-131">Click OK.</span></span>
    * <span data-ttu-id="a1660-132">A segunda etapa é imprimir a guia de depósito, mas essa etapa não é necessária.</span><span class="sxs-lookup"><span data-stu-id="a1660-132">The second step is to print the deposit slip, but this step is not required.</span></span>  

