--- 
title: Processar reembolsos para pagamento
description: "Este procedimento demonstra como converter reembolsos de cliente aprovados e processados para notas de crédito."
author: omulvad
manager: AnnBe
ms.date: 11/10/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 791ec304b9ea7c49fbea506d73c4daffd4478739
ms.contentlocale: pt-br
ms.lasthandoff: 08/29/2017

---
# <a name="process-rebates-for-payment"></a><span data-ttu-id="38297-103">Processar reembolsos para pagamento</span><span class="sxs-lookup"><span data-stu-id="38297-103">Process rebates for payment</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="38297-104">Este procedimento demonstra como converter reembolsos de cliente aprovados e processados para notas de crédito.</span><span class="sxs-lookup"><span data-stu-id="38297-104">This procedure demonstrates how to convert approved and processed customer rebates to credit notes.</span></span> <span data-ttu-id="38297-105">Você pode utilizar esse guia na empresa demonstrativa USMF.</span><span class="sxs-lookup"><span data-stu-id="38297-105">You can use this guide in the USMF demo company.</span></span> <span data-ttu-id="38297-106">A pré-condição para essa guia é ter uma ou mais reivindicações de reembolso com status Marcar.</span><span class="sxs-lookup"><span data-stu-id="38297-106">The precondition for this guide is to have one or more rebate claims which have a status of Mark.</span></span> <span data-ttu-id="38297-107">Se você estiver utilizando USMF você deve executar o guia "Gerar e processar reembolsos de cliente" antes de iniciar esse guia.</span><span class="sxs-lookup"><span data-stu-id="38297-107">If you’re using USMF you should run the "Generate and process customer rebates" guide before you start this guide.</span></span>


## <a name="convert-rebate-claims-to-credit-note"></a><span data-ttu-id="38297-108">Converter reivindicações de reembolso para nota de crédito.</span><span class="sxs-lookup"><span data-stu-id="38297-108">Convert rebate claims to credit note</span></span>
1. <span data-ttu-id="38297-109">Vá para Todos os clientes.</span><span class="sxs-lookup"><span data-stu-id="38297-109">Go to All customers.</span></span>
2. <span data-ttu-id="38297-110">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="38297-110">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="38297-111">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="38297-111">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="38297-112">No Painel de Ação, clique em Coletar.</span><span class="sxs-lookup"><span data-stu-id="38297-112">On the Action Pane, click Collect.</span></span>
5. <span data-ttu-id="38297-113">Clique em Liquidar transações.</span><span class="sxs-lookup"><span data-stu-id="38297-113">Click Settle transactions.</span></span>
6. <span data-ttu-id="38297-114">Clique em Funções.</span><span class="sxs-lookup"><span data-stu-id="38297-114">Click Functions.</span></span>
7. <span data-ttu-id="38297-115">Clique em Programa de reembolso.</span><span class="sxs-lookup"><span data-stu-id="38297-115">Click Rebate program.</span></span>
    * <span data-ttu-id="38297-116">A página Reembolso lista as reivindicações de reembolso que você processou na bancada de reembolso de cliente e que estão com status Marcar.</span><span class="sxs-lookup"><span data-stu-id="38297-116">The Rebate page lists the rebate claims that you have processed in the customer rebate workbench and that are in status Mark.</span></span>    
8. <span data-ttu-id="38297-117">Clique em Editar.</span><span class="sxs-lookup"><span data-stu-id="38297-117">Click Edit.</span></span>
    * <span data-ttu-id="38297-118">Defina marcas de verificação no campo Marcar para as reivindicações que você deseja incluir na nota de crédito.</span><span class="sxs-lookup"><span data-stu-id="38297-118">Set checkmarks in the Mark field for the claims that you want to include into credit note.</span></span>   
9. <span data-ttu-id="38297-119">Clique em Funções.</span><span class="sxs-lookup"><span data-stu-id="38297-119">Click Functions.</span></span>
10. <span data-ttu-id="38297-120">Clique em Criar nota de crédito.</span><span class="sxs-lookup"><span data-stu-id="38297-120">Click Create credit note.</span></span>
    * <span data-ttu-id="38297-121">Uma mensagem aparece para informá-lo que um diário foi lançado (Esse é o Diário de consumo de contas a receber, como especificado na página Parâmetros de contas a receber).</span><span class="sxs-lookup"><span data-stu-id="38297-121">A message appears to inform you that a journal has been posted (This is the Accounts receivable consumption journal, as specified in the Accounts receivable parameters page).</span></span> <span data-ttu-id="38297-122">Isso faz com o valor real da dívida (crédito) seja movimentado para o saldo do cliente.</span><span class="sxs-lookup"><span data-stu-id="38297-122">This causes the real liability (credit) amount to be moved to the customer balance.</span></span> <span data-ttu-id="38297-123">Isso significa que a conta do cliente foi creditada, e a Conta de provisão de reembolso foi debitada.</span><span class="sxs-lookup"><span data-stu-id="38297-123">This means that the customer’s account has been credited, and the Rebate accrual account has been debited.</span></span>  
11. <span data-ttu-id="38297-124">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="38297-124">Close the page.</span></span>
12. <span data-ttu-id="38297-125">Clique em Cancelar.</span><span class="sxs-lookup"><span data-stu-id="38297-125">Click Cancel.</span></span>
    * <span data-ttu-id="38297-126">Isso atualiza a página para que você possa ver as atualizações.</span><span class="sxs-lookup"><span data-stu-id="38297-126">This refreshes the page so that you can see the updates.</span></span>  
13. <span data-ttu-id="38297-127">No Painel de Ação, clique em Coletar.</span><span class="sxs-lookup"><span data-stu-id="38297-127">On the Action Pane, click Collect.</span></span>
14. <span data-ttu-id="38297-128">Clique em Liquidar transações.</span><span class="sxs-lookup"><span data-stu-id="38297-128">Click Settle transactions.</span></span>
    * <span data-ttu-id="38297-129">Observe que uma transação para valor negativo, representando o valor total do reembolso, sem referência de fatura foi adicionada ao saldo do cliente.</span><span class="sxs-lookup"><span data-stu-id="38297-129">Note that a transaction for negative amount, representing the total rebate amount, without invoice reference has been added to the customer balance.</span></span>   
15. <span data-ttu-id="38297-130">Clique em Cancelar.</span><span class="sxs-lookup"><span data-stu-id="38297-130">Click Cancel.</span></span>


