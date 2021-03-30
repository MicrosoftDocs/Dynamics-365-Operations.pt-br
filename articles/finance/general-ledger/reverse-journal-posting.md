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
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 19f7ea540035a3bc9eba445c508cb6f29e4bd20f
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5204993"
---
# <a name="reverse-journal-posting"></a><span data-ttu-id="6ef2e-103">Reverter lançamento no diário</span><span class="sxs-lookup"><span data-stu-id="6ef2e-103">Reverse journal posting</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="6ef2e-104">Este tópico descreve recursos do Microsoft Dynamics 365 Finance que permitem reverter um diário inteiro, ou reverter um ou mais comprovantes da lista de transações de comprovante, independentemente da origem.</span><span class="sxs-lookup"><span data-stu-id="6ef2e-104">This topic describes capabilities Microsoft Dynamics 365 Finance that allows you to reverse an entire journal, or reverse one or more vouchers from the voucher transaction list, regardless of their origin.</span></span> 

## <a name="reversing-journals"></a><span data-ttu-id="6ef2e-105">Revertendo diários</span><span class="sxs-lookup"><span data-stu-id="6ef2e-105">Reversing journals</span></span>

<span data-ttu-id="6ef2e-106">Você pode reverter linhas de diário individualmente.</span><span class="sxs-lookup"><span data-stu-id="6ef2e-106">You can reverse journal lines individually.</span></span> <span data-ttu-id="6ef2e-107">Com a reversão de lançamento no diário, também é possível reverter um diário financeiro inteiro.</span><span class="sxs-lookup"><span data-stu-id="6ef2e-107">With reverse journal posting, you can also reverse an entire financial journal.</span></span> <span data-ttu-id="6ef2e-108">Para reverter um diário:</span><span class="sxs-lookup"><span data-stu-id="6ef2e-108">To reverse a journal:</span></span> 

- <span data-ttu-id="6ef2e-109">Abra o diário financeiro e filtre por diários lançados.</span><span class="sxs-lookup"><span data-stu-id="6ef2e-109">Open the financial journal and filter on posted journals.</span></span>
- <span data-ttu-id="6ef2e-110">Selecione o menu **Reverter** na parte superior da página.</span><span class="sxs-lookup"><span data-stu-id="6ef2e-110">Select the **Reverse** menu at the top of the page.</span></span>
- <span data-ttu-id="6ef2e-111">Você verá o número total de comprovantes e linhas de comprovante, além da quantidade total de linhas que estão sendo revertidas</span><span class="sxs-lookup"><span data-stu-id="6ef2e-111">You will see the total number of vouchers and voucher lines as well as the total amount of the lines being reversed</span></span>
- <span data-ttu-id="6ef2e-112">Selecione **Sim** para usar as datas de transação existentes ou **Não** para inserir uma nova.</span><span class="sxs-lookup"><span data-stu-id="6ef2e-112">Select **Yes** to use the existing transaction dates or **No** to enter a new one.</span></span> <span data-ttu-id="6ef2e-113">Em alguns casos, o período da transação original pode ser fechado e você deve inserir uma nova data de transação para a reversão.</span><span class="sxs-lookup"><span data-stu-id="6ef2e-113">In some cases, the period of the original transaction may be closed and you must enter a new transaction date for the reversal.</span></span>
- <span data-ttu-id="6ef2e-114">Caso selecione **Não**, insira uma data de transação para a reversão.</span><span class="sxs-lookup"><span data-stu-id="6ef2e-114">If you select **No**, enter a transaction date for the reversal.</span></span> 
- <span data-ttu-id="6ef2e-115">Insira um comentário a ser adicionado à transação de reversão.</span><span class="sxs-lookup"><span data-stu-id="6ef2e-115">Enter a comment that you want added to the reversal transaction.</span></span>
- <span data-ttu-id="6ef2e-116">Selecione o botão **Reverter**.</span><span class="sxs-lookup"><span data-stu-id="6ef2e-116">Select the **Reverse** button.</span></span>

<span data-ttu-id="6ef2e-117">As transações serão revertidas.</span><span class="sxs-lookup"><span data-stu-id="6ef2e-117">The transactions will be reversed.</span></span> 

<span data-ttu-id="6ef2e-118">Se o comprovante contiver mais de 100 linhas, o processo de reversão será executado usando o processo em lote.</span><span class="sxs-lookup"><span data-stu-id="6ef2e-118">If the voucher contains more than 100 lines, the reversal process will run using the batch process.</span></span> <span data-ttu-id="6ef2e-119">É possível examinar os resultados exibindo os comentários no trabalho em lotes.</span><span class="sxs-lookup"><span data-stu-id="6ef2e-119">You can review the results by viewing the comments in the batch job.</span></span> <span data-ttu-id="6ef2e-120">Todas as transações que não puderam ser revertidas serão listadas no histórico do trabalho em lotes.</span><span class="sxs-lookup"><span data-stu-id="6ef2e-120">Any transactions that couldn't be reversed will be listed in the batch job history.</span></span>

<span data-ttu-id="6ef2e-121">Se o comprovantes tiverem 100 linhas ou menos, o processo de reversão será executado imediatamente.</span><span class="sxs-lookup"><span data-stu-id="6ef2e-121">If the voucher contains 100 lines or fewer, the reversal process will run immediately.</span></span> <span data-ttu-id="6ef2e-122">Os resultados serão apresentados em uma caixa de diálogo que mostra todos os comprovantes que não puderam ser revertidos junto com o motivo da não reversão.</span><span class="sxs-lookup"><span data-stu-id="6ef2e-122">The results will be presented in a dialog box that shows any voucher that could not be reversed, along with the reason why it could not be reversed.</span></span> <span data-ttu-id="6ef2e-123">Selecione **OK** para fechar a caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="6ef2e-123">Select **OK** to close the dialog box.</span></span>

## <a name="reversing-vouchers-from-the-voucher-transaction-list"></a><span data-ttu-id="6ef2e-124">Revertendo comprovantes da lista de transações de comprovante.</span><span class="sxs-lookup"><span data-stu-id="6ef2e-124">Reversing vouchers from the voucher transaction list.</span></span> 

<span data-ttu-id="6ef2e-125">Você também pode reverter comprovantes da **Lista de transações de comprovante** em todos os sub-razões.</span><span class="sxs-lookup"><span data-stu-id="6ef2e-125">You can also reverse vouchers from the **Voucher transaction list** across all subledgers.</span></span> <span data-ttu-id="6ef2e-126">Além disso, é possível reverter mais de um comprovante por vez.</span><span class="sxs-lookup"><span data-stu-id="6ef2e-126">In addition, you can reverse more than one voucher at a time.</span></span> 

<span data-ttu-id="6ef2e-127">Para reverter um ou vários comprovantes:</span><span class="sxs-lookup"><span data-stu-id="6ef2e-127">To reverse one or more vouchers:</span></span> 

- <span data-ttu-id="6ef2e-128">Selecione o menu **Reverter** na parte superior da página</span><span class="sxs-lookup"><span data-stu-id="6ef2e-128">Select the **Reverse** menu at the top of the page</span></span>
- <span data-ttu-id="6ef2e-129">Você verá o número total de comprovantes e linhas de comprovante, além da quantidade total de linhas que estão sendo revertidas.</span><span class="sxs-lookup"><span data-stu-id="6ef2e-129">You will see the total number of vouchers and voucher lines as well as the total amount of the lines being reversed.</span></span>
- <span data-ttu-id="6ef2e-130">Selecione **Sim** para usar as datas de transação existentes ou **Não** para inserir uma nova.</span><span class="sxs-lookup"><span data-stu-id="6ef2e-130">Select **Yes** to use the existing transaction dates or **No** to enter a new one.</span></span> <span data-ttu-id="6ef2e-131">Em alguns casos, o período da transação original pode ser fechado e você deve inserir uma nova data de transação para revertê-lo.</span><span class="sxs-lookup"><span data-stu-id="6ef2e-131">In some cases, the period of the original transaction may be closed and you must enter a new transaction date to reverse it.</span></span>
- <span data-ttu-id="6ef2e-132">Caso selecione **Não**, insira uma data de transação para a reversão.</span><span class="sxs-lookup"><span data-stu-id="6ef2e-132">If you select **No**, enter a transaction date for the reversal.</span></span> 
- <span data-ttu-id="6ef2e-133">Insira um comentário para descrever a transação de reversão.</span><span class="sxs-lookup"><span data-stu-id="6ef2e-133">Enter a comment to describe the reversal transaction.</span></span>
- <span data-ttu-id="6ef2e-134">Selecione o botão **Reverter**.</span><span class="sxs-lookup"><span data-stu-id="6ef2e-134">Select the **Reverse** button.</span></span>

<span data-ttu-id="6ef2e-135">As transações serão revertidas.</span><span class="sxs-lookup"><span data-stu-id="6ef2e-135">The transactions will be reversed.</span></span> 

<span data-ttu-id="6ef2e-136">Se tiver mais de 100 linhas no comprovante, o processo de reversão será executado usando o processo em lote.</span><span class="sxs-lookup"><span data-stu-id="6ef2e-136">If there are more than 100 voucher lines, the reversal process will run using the batch process.</span></span> <span data-ttu-id="6ef2e-137">É possível examinar os resultados exibindo os comentários no trabalho em lotes.</span><span class="sxs-lookup"><span data-stu-id="6ef2e-137">You can review the results by viewing the comments in the batch job.</span></span> <span data-ttu-id="6ef2e-138">Todas as transações que não puderam ser revertidas serão anotadas no histórico do trabalho em lotes.</span><span class="sxs-lookup"><span data-stu-id="6ef2e-138">Any transactions that couldn't be reversed will be noted in the batch job history.</span></span>

<span data-ttu-id="6ef2e-139">Se o número de linhas do comprovantes for 100 ou menos, o processo de reversão será executado imediatamente.</span><span class="sxs-lookup"><span data-stu-id="6ef2e-139">If the number of voucher lines is 100 lines or fewer, the reversal process will run immediately.</span></span> <span data-ttu-id="6ef2e-140">Os resultados serão exibidos em uma caixa de diálogo que mostra todos os comprovantes que não puderam ser revertidos junto com o motivo.</span><span class="sxs-lookup"><span data-stu-id="6ef2e-140">The results will display in a dialog box that shows any voucher that couldn't be reversed, along with the reason why.</span></span> <span data-ttu-id="6ef2e-141">Selecione **OK** para fechar a caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="6ef2e-141">Select **OK** to close the dialog box.</span></span>

<span data-ttu-id="6ef2e-142">As transações podem ser revertidas somente se atenderem às regras de negócio para a reversão.</span><span class="sxs-lookup"><span data-stu-id="6ef2e-142">Transactions can be reversed only if they meet the business rules for reversing them.</span></span> <span data-ttu-id="6ef2e-143">Os pagamentos de fornecedores não podem ser revertidos usando o recurso descrito neste tópico.</span><span class="sxs-lookup"><span data-stu-id="6ef2e-143">Vendor payments cannot be reversed using the capability described in this topic.</span></span> <span data-ttu-id="6ef2e-144">Os pagamentos de fornecedores devem ser revertidos de acordo com as etapas listadas em [Reverter um pagamento de fornecedor](https://docs.microsoft.com/dynamics365/finance/accounts-payable/reverse-vendor-payment)</span><span class="sxs-lookup"><span data-stu-id="6ef2e-144">Vendor payments must be reversed by following the steps listed in [Reverse a vendor payment](https://docs.microsoft.com/dynamics365/finance/accounts-payable/reverse-vendor-payment).</span></span>



[!INCLUDE[footer-include](../../includes/footer-banner.md)]