---
title: Liquidar um cheque pré-datado de um cliente
description: É possível liquidar um cheque pré-datado após o cheque ter sido liberado pelo banco.
author: kweekley
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: CustPostDatedChecks, SystemDate, LedgerJournalTable, LedgerJournalTransDaily, LedgerTransVoucher
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f714e41f47a31bce16424de18878d2f5acb5028d
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5834539"
---
# <a name="settle-a-postdated-check-from-a-customer"></a><span data-ttu-id="82fac-103">Liquidar um cheque pré-datado de um cliente</span><span class="sxs-lookup"><span data-stu-id="82fac-103">Settle a postdated check from a customer</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="82fac-104">É possível liquidar um cheque pré-datado após o cheque ter sido liberado pelo banco.</span><span class="sxs-lookup"><span data-stu-id="82fac-104">You can settle a postdated check after the check has been cleared by the bank.</span></span> <span data-ttu-id="82fac-105">Esta transação financeira também libera a transação da conta de ponte do cheque pré-datado.</span><span class="sxs-lookup"><span data-stu-id="82fac-105">This financial transaction also clears the bridge account transaction for the postdated check.</span></span> 

<span data-ttu-id="82fac-106">As tarefas a seguir devem ser concluídas antes de iniciar esta.</span><span class="sxs-lookup"><span data-stu-id="82fac-106">The following tasks must be complete before you start this one.</span></span>

1) <span data-ttu-id="82fac-107">Configurar cheques pré-datados</span><span class="sxs-lookup"><span data-stu-id="82fac-107">Set up postdated checks</span></span>

2) <span data-ttu-id="82fac-108">Registrar e lançar um cheque pré-datado para um cliente</span><span class="sxs-lookup"><span data-stu-id="82fac-108">Register and post a postdated check for a customer</span></span> 



<span data-ttu-id="82fac-109">A função desta guias de tarefas é Tesoureiro.</span><span class="sxs-lookup"><span data-stu-id="82fac-109">The role of this task guides is Treasurer.</span></span>



<span data-ttu-id="82fac-110">Este procedimento usa a empresa de dados de demonstração USMF.</span><span class="sxs-lookup"><span data-stu-id="82fac-110">This procedure uses the USMF demo company.</span></span>

1. <span data-ttu-id="82fac-111">Vá para Crédito e cobranças > Consultas e relatórios > Pagamentos > Cheques pré-datados do cliente.</span><span class="sxs-lookup"><span data-stu-id="82fac-111">Go to Credit and collections > Inquiries and reports > Payments > Customer postdated checks.</span></span>
2. <span data-ttu-id="82fac-112">Clique em Liquidar.</span><span class="sxs-lookup"><span data-stu-id="82fac-112">Click Settle.</span></span>
3. <span data-ttu-id="82fac-113">Clique em Liquidar entradas de compensação.</span><span class="sxs-lookup"><span data-stu-id="82fac-113">Click Settle clearing entries.</span></span>
    * <span data-ttu-id="82fac-114">Liquide a conta do cliente para a transação do cheque.</span><span class="sxs-lookup"><span data-stu-id="82fac-114">Settle the customer account for the check transaction.</span></span>  
4. <span data-ttu-id="82fac-115">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="82fac-115">Close the page.</span></span>
5. <span data-ttu-id="82fac-116">Ir para Contabilidade > Entradas de diários > Diários gerais.</span><span class="sxs-lookup"><span data-stu-id="82fac-116">Go to General ledger > Journal entries > General journals.</span></span>
6. <span data-ttu-id="82fac-117">No campo Mostrar, selecione uma opção.</span><span class="sxs-lookup"><span data-stu-id="82fac-117">In the Show field, select an option.</span></span>
7. <span data-ttu-id="82fac-118">Marque ou desmarque a caixa de seleção Mostrar apenas os que foram criados por usuário.</span><span class="sxs-lookup"><span data-stu-id="82fac-118">Select or clear the Show user-created only check box.</span></span>
8. <span data-ttu-id="82fac-119">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="82fac-119">In the list, find and select the desired record.</span></span>
9. <span data-ttu-id="82fac-120">Clique em Linhas.</span><span class="sxs-lookup"><span data-stu-id="82fac-120">Click Lines.</span></span>
10. <span data-ttu-id="82fac-121">Clique em Comprovante.</span><span class="sxs-lookup"><span data-stu-id="82fac-121">Click Voucher.</span></span>
11. <span data-ttu-id="82fac-122">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="82fac-122">Close the page.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]