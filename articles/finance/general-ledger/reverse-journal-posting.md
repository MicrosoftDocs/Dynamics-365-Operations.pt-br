---
title: Reverter lançamento no diário
description: Este tópico descreve recursos que permitem reverter comprovantes da lista de transações de comprovante ou de diários financeiros.
author: MikeFalkner
manager: AnnBe
ms.date: 08/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerTransVoucher, LedgerJournalTable
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: mikefalkner
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5a5456e60f1f3cee5f83ac7f725f7e01ba5bd7a1
ms.sourcegitcommit: 2460d0da812c45fce67a061386db52e0ae46b0f3
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/30/2019
ms.locfileid: "2248576"
---
# <a name="reverse-journal-posting"></a><span data-ttu-id="c5da7-103">Reverter lançamento no diário</span><span class="sxs-lookup"><span data-stu-id="c5da7-103">Reverse journal posting</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="c5da7-104">Este tópico descreve recursos do Microsoft Dynamics 365 Finance que permitem reverter um diário inteiro, ou reverter um ou mais comprovantes da lista de transações de comprovante, independentemente da origem.</span><span class="sxs-lookup"><span data-stu-id="c5da7-104">This topic describes capabilities Microsoft Dynamics 365 Finance that allows you to reverse an entire journal or reverse one or more vouchers from the voucher transaction list regardless of their origin.</span></span> 

## <a name="reversing-journals"></a><span data-ttu-id="c5da7-105">Revertendo diários</span><span class="sxs-lookup"><span data-stu-id="c5da7-105">Reversing journals</span></span>

<span data-ttu-id="c5da7-106">Você pode reverter linhas de diário individualmente.</span><span class="sxs-lookup"><span data-stu-id="c5da7-106">You can reverse journal lines individually.</span></span> <span data-ttu-id="c5da7-107">Com a reversão de lançamento no diário, também é possível reverter um diário financeiro inteiro.</span><span class="sxs-lookup"><span data-stu-id="c5da7-107">With reverse journal posting, you can also reverse an entire financial journal.</span></span> <span data-ttu-id="c5da7-108">Para reverter um diário:</span><span class="sxs-lookup"><span data-stu-id="c5da7-108">To reverse a journal:</span></span> 
- <span data-ttu-id="c5da7-109">Abra o diário financeiro e filtre por diários lançados</span><span class="sxs-lookup"><span data-stu-id="c5da7-109">Open the financial journal and filter on posted journals</span></span>
- <span data-ttu-id="c5da7-110">Clique no menu Reverter na parte superior da página</span><span class="sxs-lookup"><span data-stu-id="c5da7-110">Click on the Reverse menu at the top of the page</span></span>
- <span data-ttu-id="c5da7-111">Você verá o número total de comprovantes e linhas de comprovante, além da quantidade total de linhas que estão sendo revertidas</span><span class="sxs-lookup"><span data-stu-id="c5da7-111">You will see the total number of vouchers and voucher lines as well as the total amount of the lines being reversed</span></span>
- <span data-ttu-id="c5da7-112">Selecione Sim para usar as datas de transação existentes ou Não para inserir uma nova.</span><span class="sxs-lookup"><span data-stu-id="c5da7-112">Select Yes to use the existing transaction dates or No to enter a new one.</span></span> <span data-ttu-id="c5da7-113">Em alguns casos, o período da transação original pode ser fechado e você quer inserir uma nova data de transação para a reversão.</span><span class="sxs-lookup"><span data-stu-id="c5da7-113">In some cases, the period of the original transaction may be closed and you want to enter a new transaction date for the reversal.</span></span>
- <span data-ttu-id="c5da7-114">Se selecionou Não, insira uma data de transação para a reversão.</span><span class="sxs-lookup"><span data-stu-id="c5da7-114">If you selected No, enter a transaction date for the reversal.</span></span> 
- <span data-ttu-id="c5da7-115">Insira um comentário a ser adicionado à transação de reversão</span><span class="sxs-lookup"><span data-stu-id="c5da7-115">Enter a comment that you want added to the reversal transaction</span></span>
- <span data-ttu-id="c5da7-116">Clique no botão Reverter</span><span class="sxs-lookup"><span data-stu-id="c5da7-116">Click the Reverse button</span></span>

<span data-ttu-id="c5da7-117">As transações serão revertidas.</span><span class="sxs-lookup"><span data-stu-id="c5da7-117">The transactions will be reversed.</span></span> 

<span data-ttu-id="c5da7-118">Se o número de linhas do comprovante passar de 100, o processo de reversão será executado usando o processo em lote.</span><span class="sxs-lookup"><span data-stu-id="c5da7-118">If the number of voucher lines exceeds 100 lines, the reversal process will be run using the batch process.</span></span> <span data-ttu-id="c5da7-119">É possível examinar os resultados da reversão exibindo os comentários no trabalho em lotes que foi executado.</span><span class="sxs-lookup"><span data-stu-id="c5da7-119">You can review the results of the reversal by viewing the comments in the batch job that was run.</span></span> <span data-ttu-id="c5da7-120">Todas as falhas serão notadas no histórico de trabalho em lotes.</span><span class="sxs-lookup"><span data-stu-id="c5da7-120">All failures will be noted in the batch job history.</span></span>

<span data-ttu-id="c5da7-121">Se o número de linhas do comprovantes for 100 ou menos, o processo de reversão será executado imediatamente.</span><span class="sxs-lookup"><span data-stu-id="c5da7-121">If the number of voucher lines is 100 lines or less, the reversal process will run immediately.</span></span> <span data-ttu-id="c5da7-122">Os resultados serão apresentados em uma caixa de diálogo que mostra todos os comprovantes que não puderam ser revertidos e o motivo da não reversão.</span><span class="sxs-lookup"><span data-stu-id="c5da7-122">The results will be presented in a dialog that shows any voucher that could not be reversed and the reason why it could not be reversed.</span></span> <span data-ttu-id="c5da7-123">Clique em OK para fechar a caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="c5da7-123">Click on Ok to close the dialog.</span></span>

## <a name="reversing-vouchers-from-the-voucher-transaction-list"></a><span data-ttu-id="c5da7-124">Revertendo comprovantes da lista de transações de comprovante.</span><span class="sxs-lookup"><span data-stu-id="c5da7-124">Reversing vouchers from the voucher transaction list.</span></span> 

<span data-ttu-id="c5da7-125">Você também pode reverter comprovantes da **Lista de transações de comprovante** em todos os sub-razões.</span><span class="sxs-lookup"><span data-stu-id="c5da7-125">You can also reverse vouchers from the **Voucher transaction list** across all subledgers.</span></span> <span data-ttu-id="c5da7-126">Além disso, é possível reverter mais de um comprovante por vez.</span><span class="sxs-lookup"><span data-stu-id="c5da7-126">In addition, you can reverse more than one voucher at a time.</span></span> 

<span data-ttu-id="c5da7-127">Para reverter um ou vários comprovantes:</span><span class="sxs-lookup"><span data-stu-id="c5da7-127">To reverse one or more vouchers:</span></span> 
- <span data-ttu-id="c5da7-128">Clique no menu Reverter na parte superior da página</span><span class="sxs-lookup"><span data-stu-id="c5da7-128">Click on the Reverse menu at the top of the page</span></span>
- <span data-ttu-id="c5da7-129">Você verá o número total de comprovantes e linhas de comprovante, além da quantidade total de linhas que estão sendo revertidas</span><span class="sxs-lookup"><span data-stu-id="c5da7-129">You will see the total number of vouchers and voucher lines as well as the total amount of the lines being reversed</span></span>
- <span data-ttu-id="c5da7-130">Selecione Sim para usar as datas de transação existentes ou Não para inserir uma nova.</span><span class="sxs-lookup"><span data-stu-id="c5da7-130">Select Yes to use the existing transaction dates or No to enter a new one.</span></span> <span data-ttu-id="c5da7-131">Em alguns casos, o período da transação original pode ser fechado e você quer inserir uma nova data de transação para a reversão.</span><span class="sxs-lookup"><span data-stu-id="c5da7-131">In some cases, the period of the original transaction may be closed and you want to enter a new transaction date for the reversal.</span></span>
- <span data-ttu-id="c5da7-132">Se selecionou Não, insira uma data de transação para a reversão.</span><span class="sxs-lookup"><span data-stu-id="c5da7-132">If you selected No, enter a transaction date for the reversal.</span></span> 
- <span data-ttu-id="c5da7-133">Insira um comentário a ser adicionado à transação de reversão</span><span class="sxs-lookup"><span data-stu-id="c5da7-133">Enter a comment that you want added to the reversal transaction</span></span>
- <span data-ttu-id="c5da7-134">Clique no botão Reverter</span><span class="sxs-lookup"><span data-stu-id="c5da7-134">Click the Reverse button</span></span>

<span data-ttu-id="c5da7-135">As transações serão revertidas.</span><span class="sxs-lookup"><span data-stu-id="c5da7-135">The transactions will be reversed.</span></span> 

<span data-ttu-id="c5da7-136">Se o número de linhas do comprovante passar de 100, o processo de reversão será executado usando o processo em lote.</span><span class="sxs-lookup"><span data-stu-id="c5da7-136">If the number of voucher lines exceeds 100 lines, the reversal process will be run using the batch process.</span></span> <span data-ttu-id="c5da7-137">É possível examinar os resultados da reversão exibindo os comentários no trabalho em lotes que foi executado.</span><span class="sxs-lookup"><span data-stu-id="c5da7-137">You can review the results of the reversal by viewing the comments in the batch job that was run.</span></span> <span data-ttu-id="c5da7-138">Todas as falhas serão notadas no histórico de trabalho em lotes.</span><span class="sxs-lookup"><span data-stu-id="c5da7-138">All failures will be noted in the batch job history.</span></span>

<span data-ttu-id="c5da7-139">Se o número de linhas do comprovantes for 100 ou menos, o processo de reversão será executado imediatamente.</span><span class="sxs-lookup"><span data-stu-id="c5da7-139">If the number of voucher lines is 100 lines or less, the reversal process will run immediately.</span></span> <span data-ttu-id="c5da7-140">Os resultados serão apresentados em uma caixa de diálogo que mostra todos os comprovantes que não puderam ser revertidos e o motivo da não reversão.</span><span class="sxs-lookup"><span data-stu-id="c5da7-140">The results will be presented in a dialog that shows any voucher that could not be reversed and the reason why it could not be reversed.</span></span> <span data-ttu-id="c5da7-141">Clique em OK para fechar a caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="c5da7-141">Click on Ok to close the dialog.</span></span>

