---
title: Liquidar um cheque pré-datado de um cliente
description: É possível liquidar um cheque pré-datado após o cheque ter sido liberado pelo banco.
author: kweekley
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustPostDatedChecks, SystemDate, LedgerJournalTable, LedgerJournalTransDaily, LedgerTransVoucher
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 7f8f2f8fe0dfd0eccd61ef76242e2a77c75b3983
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4976232"
---
# <a name="settle-a-postdated-check-from-a-customer"></a><span data-ttu-id="e4141-103">Liquidar um cheque pré-datado de um cliente</span><span class="sxs-lookup"><span data-stu-id="e4141-103">Settle a postdated check from a customer</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="e4141-104">É possível liquidar um cheque pré-datado após o cheque ter sido liberado pelo banco.</span><span class="sxs-lookup"><span data-stu-id="e4141-104">You can settle a postdated check after the check has been cleared by the bank.</span></span> <span data-ttu-id="e4141-105">Esta transação financeira também libera a transação da conta de ponte do cheque pré-datado.</span><span class="sxs-lookup"><span data-stu-id="e4141-105">This financial transaction also clears the bridge account transaction for the postdated check.</span></span> 

<span data-ttu-id="e4141-106">As tarefas a seguir devem ser concluídas antes de iniciar esta.</span><span class="sxs-lookup"><span data-stu-id="e4141-106">The following tasks must be complete before you start this one.</span></span>

1) <span data-ttu-id="e4141-107">Configurar cheques pré-datados</span><span class="sxs-lookup"><span data-stu-id="e4141-107">Set up postdated checks</span></span>

2) <span data-ttu-id="e4141-108">Registrar e lançar um cheque pré-datado para um cliente</span><span class="sxs-lookup"><span data-stu-id="e4141-108">Register and post a postdated check for a customer</span></span> 



<span data-ttu-id="e4141-109">A função desta guias de tarefas é Tesoureiro.</span><span class="sxs-lookup"><span data-stu-id="e4141-109">The role of this task guides is Treasurer.</span></span>



<span data-ttu-id="e4141-110">Este procedimento usa a empresa de dados de demonstração USMF.</span><span class="sxs-lookup"><span data-stu-id="e4141-110">This procedure uses the USMF demo company.</span></span>

1. <span data-ttu-id="e4141-111">Vá para Crédito e cobranças > Consultas e relatórios > Pagamentos > Cheques pré-datados do cliente.</span><span class="sxs-lookup"><span data-stu-id="e4141-111">Go to Credit and collections > Inquiries and reports > Payments > Customer postdated checks.</span></span>
2. <span data-ttu-id="e4141-112">Clique em Liquidar.</span><span class="sxs-lookup"><span data-stu-id="e4141-112">Click Settle.</span></span>
3. <span data-ttu-id="e4141-113">Clique em Liquidar entradas de compensação.</span><span class="sxs-lookup"><span data-stu-id="e4141-113">Click Settle clearing entries.</span></span>
    * <span data-ttu-id="e4141-114">Liquide a conta do cliente para a transação do cheque.</span><span class="sxs-lookup"><span data-stu-id="e4141-114">Settle the customer account for the check transaction.</span></span>  
4. <span data-ttu-id="e4141-115">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="e4141-115">Close the page.</span></span>
5. <span data-ttu-id="e4141-116">Ir para Contabilidade > Entradas de diários > Diários gerais.</span><span class="sxs-lookup"><span data-stu-id="e4141-116">Go to General ledger > Journal entries > General journals.</span></span>
6. <span data-ttu-id="e4141-117">No campo Mostrar, selecione uma opção.</span><span class="sxs-lookup"><span data-stu-id="e4141-117">In the Show field, select an option.</span></span>
7. <span data-ttu-id="e4141-118">Marque ou desmarque a caixa de seleção Mostrar apenas os que foram criados por usuário.</span><span class="sxs-lookup"><span data-stu-id="e4141-118">Select or clear the Show user-created only check box.</span></span>
8. <span data-ttu-id="e4141-119">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="e4141-119">In the list, find and select the desired record.</span></span>
9. <span data-ttu-id="e4141-120">Clique em Linhas.</span><span class="sxs-lookup"><span data-stu-id="e4141-120">Click Lines.</span></span>
10. <span data-ttu-id="e4141-121">Clique em Comprovante.</span><span class="sxs-lookup"><span data-stu-id="e4141-121">Click Voucher.</span></span>
11. <span data-ttu-id="e4141-122">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="e4141-122">Close the page.</span></span>

