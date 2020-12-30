---
title: Reverter lançamento no diário
description: Este tópico descreve recursos que permitem reverter comprovantes da lista de transações de comprovante ou de diários financeiros.
author: MikeFalkner
manager: AnnBe
ms.date: 10/08/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerTransVoucher, LedgerJournalTable
audience: Application User
ms.reviewer: roschloma
ms.search.scope: Core, Operations
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e3244d857a9135249130672501f8b766ff9a0680
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4440360"
---
# <a name="reverse-journal-posting"></a><span data-ttu-id="99908-103">Reverter lançamento no diário</span><span class="sxs-lookup"><span data-stu-id="99908-103">Reverse journal posting</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="99908-104">Este tópico descreve recursos do Microsoft Dynamics 365 Finance que permitem reverter um diário inteiro, ou reverter um ou mais comprovantes da lista de transações de comprovante, independentemente da origem.</span><span class="sxs-lookup"><span data-stu-id="99908-104">This topic describes capabilities Microsoft Dynamics 365 Finance that allows you to reverse an entire journal, or reverse one or more vouchers from the voucher transaction list, regardless of their origin.</span></span> 

## <a name="reversing-journals"></a><span data-ttu-id="99908-105">Revertendo diários</span><span class="sxs-lookup"><span data-stu-id="99908-105">Reversing journals</span></span>

<span data-ttu-id="99908-106">Você pode reverter linhas de diário individualmente.</span><span class="sxs-lookup"><span data-stu-id="99908-106">You can reverse journal lines individually.</span></span> <span data-ttu-id="99908-107">Com a reversão de lançamento no diário, também é possível reverter um diário financeiro inteiro.</span><span class="sxs-lookup"><span data-stu-id="99908-107">With reverse journal posting, you can also reverse an entire financial journal.</span></span> <span data-ttu-id="99908-108">Para reverter um diário:</span><span class="sxs-lookup"><span data-stu-id="99908-108">To reverse a journal:</span></span> 

- <span data-ttu-id="99908-109">Abra o diário financeiro e filtre por diários lançados.</span><span class="sxs-lookup"><span data-stu-id="99908-109">Open the financial journal and filter on posted journals.</span></span>
- <span data-ttu-id="99908-110">Selecione o menu **Reverter** na parte superior da página.</span><span class="sxs-lookup"><span data-stu-id="99908-110">Select the **Reverse** menu at the top of the page.</span></span>
- <span data-ttu-id="99908-111">Você verá o número total de comprovantes e linhas de comprovante, além da quantidade total de linhas que estão sendo revertidas</span><span class="sxs-lookup"><span data-stu-id="99908-111">You will see the total number of vouchers and voucher lines as well as the total amount of the lines being reversed</span></span>
- <span data-ttu-id="99908-112">Selecione **Sim** para usar as datas de transação existentes ou **Não** para inserir uma nova.</span><span class="sxs-lookup"><span data-stu-id="99908-112">Select **Yes** to use the existing transaction dates or **No** to enter a new one.</span></span> <span data-ttu-id="99908-113">Em alguns casos, o período da transação original pode ser fechado e você deve inserir uma nova data de transação para a reversão.</span><span class="sxs-lookup"><span data-stu-id="99908-113">In some cases, the period of the original transaction may be closed and you must enter a new transaction date for the reversal.</span></span>
- <span data-ttu-id="99908-114">Caso selecione **Não**, insira uma data de transação para a reversão.</span><span class="sxs-lookup"><span data-stu-id="99908-114">If you select **No**, enter a transaction date for the reversal.</span></span> 
- <span data-ttu-id="99908-115">Insira um comentário a ser adicionado à transação de reversão.</span><span class="sxs-lookup"><span data-stu-id="99908-115">Enter a comment that you want added to the reversal transaction.</span></span>
- <span data-ttu-id="99908-116">Selecione o botão **Reverter**.</span><span class="sxs-lookup"><span data-stu-id="99908-116">Select the **Reverse** button.</span></span>

<span data-ttu-id="99908-117">As transações serão revertidas.</span><span class="sxs-lookup"><span data-stu-id="99908-117">The transactions will be reversed.</span></span> 

<span data-ttu-id="99908-118">Se o comprovante contiver mais de 100 linhas, o processo de reversão será executado usando o processo em lote.</span><span class="sxs-lookup"><span data-stu-id="99908-118">If the voucher contains more than 100 lines, the reversal process will run using the batch process.</span></span> <span data-ttu-id="99908-119">É possível examinar os resultados exibindo os comentários no trabalho em lotes.</span><span class="sxs-lookup"><span data-stu-id="99908-119">You can review the results by viewing the comments in the batch job.</span></span> <span data-ttu-id="99908-120">Todas as transações que não puderam ser revertidas serão listadas no histórico do trabalho em lotes.</span><span class="sxs-lookup"><span data-stu-id="99908-120">Any transactions that couldn't be reversed will be listed in the batch job history.</span></span>

<span data-ttu-id="99908-121">Se o comprovantes tiverem 100 linhas ou menos, o processo de reversão será executado imediatamente.</span><span class="sxs-lookup"><span data-stu-id="99908-121">If the voucher contains 100 lines or fewer, the reversal process will run immediately.</span></span> <span data-ttu-id="99908-122">Os resultados serão apresentados em uma caixa de diálogo que mostra todos os comprovantes que não puderam ser revertidos junto com o motivo da não reversão.</span><span class="sxs-lookup"><span data-stu-id="99908-122">The results will be presented in a dialog box that shows any voucher that could not be reversed, along with the reason why it could not be reversed.</span></span> <span data-ttu-id="99908-123">Selecione **OK** para fechar a caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="99908-123">Select **OK** to close the dialog box.</span></span>

## <a name="reversing-vouchers-from-the-voucher-transaction-list"></a><span data-ttu-id="99908-124">Revertendo comprovantes da lista de transações de comprovante.</span><span class="sxs-lookup"><span data-stu-id="99908-124">Reversing vouchers from the voucher transaction list.</span></span> 

<span data-ttu-id="99908-125">Você também pode reverter comprovantes da **Lista de transações de comprovante** em todos os sub-razões.</span><span class="sxs-lookup"><span data-stu-id="99908-125">You can also reverse vouchers from the **Voucher transaction list** across all subledgers.</span></span> <span data-ttu-id="99908-126">Além disso, é possível reverter mais de um comprovante por vez.</span><span class="sxs-lookup"><span data-stu-id="99908-126">In addition, you can reverse more than one voucher at a time.</span></span> 

<span data-ttu-id="99908-127">Para reverter um ou vários comprovantes:</span><span class="sxs-lookup"><span data-stu-id="99908-127">To reverse one or more vouchers:</span></span> 

- <span data-ttu-id="99908-128">Selecione o menu **Reverter** na parte superior da página</span><span class="sxs-lookup"><span data-stu-id="99908-128">Select the **Reverse** menu at the top of the page</span></span>
- <span data-ttu-id="99908-129">Você verá o número total de comprovantes e linhas de comprovante, além da quantidade total de linhas que estão sendo revertidas.</span><span class="sxs-lookup"><span data-stu-id="99908-129">You will see the total number of vouchers and voucher lines as well as the total amount of the lines being reversed.</span></span>
- <span data-ttu-id="99908-130">Selecione **Sim** para usar as datas de transação existentes ou **Não** para inserir uma nova.</span><span class="sxs-lookup"><span data-stu-id="99908-130">Select **Yes** to use the existing transaction dates or **No** to enter a new one.</span></span> <span data-ttu-id="99908-131">Em alguns casos, o período da transação original pode ser fechado e você deve inserir uma nova data de transação para revertê-lo.</span><span class="sxs-lookup"><span data-stu-id="99908-131">In some cases, the period of the original transaction may be closed and you must enter a new transaction date to reverse it.</span></span>
- <span data-ttu-id="99908-132">Caso selecione **Não**, insira uma data de transação para a reversão.</span><span class="sxs-lookup"><span data-stu-id="99908-132">If you select **No**, enter a transaction date for the reversal.</span></span> 
- <span data-ttu-id="99908-133">Insira um comentário para descrever a transação de reversão.</span><span class="sxs-lookup"><span data-stu-id="99908-133">Enter a comment to describe the reversal transaction.</span></span>
- <span data-ttu-id="99908-134">Selecione o botão **Reverter**.</span><span class="sxs-lookup"><span data-stu-id="99908-134">Select the **Reverse** button.</span></span>

<span data-ttu-id="99908-135">As transações serão revertidas.</span><span class="sxs-lookup"><span data-stu-id="99908-135">The transactions will be reversed.</span></span> 

<span data-ttu-id="99908-136">Se tiver mais de 100 linhas no comprovante, o processo de reversão será executado usando o processo em lote.</span><span class="sxs-lookup"><span data-stu-id="99908-136">If there are more than 100 voucher lines, the reversal process will run using the batch process.</span></span> <span data-ttu-id="99908-137">É possível examinar os resultados exibindo os comentários no trabalho em lotes.</span><span class="sxs-lookup"><span data-stu-id="99908-137">You can review the results by viewing the comments in the batch job.</span></span> <span data-ttu-id="99908-138">Todas as transações que não puderam ser revertidas serão anotadas no histórico do trabalho em lotes.</span><span class="sxs-lookup"><span data-stu-id="99908-138">Any transactions that couldn't be reversed will be noted in the batch job history.</span></span>

<span data-ttu-id="99908-139">Se o número de linhas do comprovantes for 100 ou menos, o processo de reversão será executado imediatamente.</span><span class="sxs-lookup"><span data-stu-id="99908-139">If the number of voucher lines is 100 lines or fewer, the reversal process will run immediately.</span></span> <span data-ttu-id="99908-140">Os resultados serão exibidos em uma caixa de diálogo que mostra todos os comprovantes que não puderam ser revertidos junto com o motivo.</span><span class="sxs-lookup"><span data-stu-id="99908-140">The results will display in a dialog box that shows any voucher that couldn't be reversed, along with the reason why.</span></span> <span data-ttu-id="99908-141">Selecione **OK** para fechar a caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="99908-141">Select **OK** to close the dialog box.</span></span>

<span data-ttu-id="99908-142">As transações podem ser revertidas somente se atenderem às regras de negócio para a reversão.</span><span class="sxs-lookup"><span data-stu-id="99908-142">Transactions can be reversed only if they meet the business rules for reversing them.</span></span> <span data-ttu-id="99908-143">Os pagamentos de fornecedores não podem ser revertidos usando o recurso descrito neste tópico.</span><span class="sxs-lookup"><span data-stu-id="99908-143">Vendor payments cannot be reversed using the capability described in this topic.</span></span> <span data-ttu-id="99908-144">Os pagamentos de fornecedores devem ser revertidos de acordo com as etapas listadas em [Reverter um pagamento de fornecedor](https://docs.microsoft.com/dynamics365/finance/accounts-payable/reverse-vendor-payment)</span><span class="sxs-lookup"><span data-stu-id="99908-144">Vendor payments must be reversed by following the steps listed in [Reverse a vendor payment](https://docs.microsoft.com/dynamics365/finance/accounts-payable/reverse-vendor-payment).</span></span>

