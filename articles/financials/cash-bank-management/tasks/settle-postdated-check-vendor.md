---
title: Liquidar um cheque pré-datado de um fornecedor
description: Estabeleça um cheque pós-datado emitido para um fornecedor quando o banco tiver compensado a transação de cheque, após o cheque ficar vencido e compensado pelo banco.
author: kweekley
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendPostDatedChecks, LedgerJournalTable, LedgerJournalTransDaily, LedgerTransVoucher
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e46b419ab613425ae2d758f80105ac94f1ec5cc2
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1565963"
---
# <a name="settle-a-postdated-check-for-a-vendor"></a><span data-ttu-id="4d3ad-103">Liquidar um cheque pré-datado de um fornecedor</span><span class="sxs-lookup"><span data-stu-id="4d3ad-103">Settle a postdated check for a vendor</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="4d3ad-104">Estabeleça um cheque pós-datado emitido para um fornecedor quando o banco tiver compensado a transação de cheque, após o cheque ficar vencido e compensado pelo banco.</span><span class="sxs-lookup"><span data-stu-id="4d3ad-104">Settle a postdated check issued to a vendor when the bank has cleared the check transaction after the check has been overdue and cleared by the bank.</span></span> 

<span data-ttu-id="4d3ad-105">Conclua os seguintes procedimentos antes de iniciar este.</span><span class="sxs-lookup"><span data-stu-id="4d3ad-105">Complete the following procedures before you start this one.</span></span>

1) <span data-ttu-id="4d3ad-106">Configurar cheques pré-datados</span><span class="sxs-lookup"><span data-stu-id="4d3ad-106">Set up postdated checks</span></span>

2) <span data-ttu-id="4d3ad-107">Registrar e lançar um cheque pré-datado para um fornecedor</span><span class="sxs-lookup"><span data-stu-id="4d3ad-107">Register and post a postdated check for a vendor</span></span>



<span data-ttu-id="4d3ad-108">A função deste procedimento é Tesoureiro.</span><span class="sxs-lookup"><span data-stu-id="4d3ad-108">The role of this procedure is Treasurer.</span></span> <span data-ttu-id="4d3ad-109">Este procedimento usa a empresa de dados de demonstração USMF.</span><span class="sxs-lookup"><span data-stu-id="4d3ad-109">This procedure uses the USMF demo company.</span></span>

1. <span data-ttu-id="4d3ad-110">Vá para Contas a pagar > Pagamentos > Cheques pós-datados do fornecedor.</span><span class="sxs-lookup"><span data-stu-id="4d3ad-110">Go to Accounts payable > Payments > Vendor postdated checks.</span></span>
2. <span data-ttu-id="4d3ad-111">Clique em Liquidar.</span><span class="sxs-lookup"><span data-stu-id="4d3ad-111">Click Settle.</span></span>
3. <span data-ttu-id="4d3ad-112">Clique em Liquidar entradas de compensação.</span><span class="sxs-lookup"><span data-stu-id="4d3ad-112">Click Settle clearing entries.</span></span>
    * <span data-ttu-id="4d3ad-113">Liquide a conta do fornecedor para a transação do cheque.</span><span class="sxs-lookup"><span data-stu-id="4d3ad-113">Settle the vendor account for the check transaction.</span></span>  
4. <span data-ttu-id="4d3ad-114">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="4d3ad-114">Close the page.</span></span>
5. <span data-ttu-id="4d3ad-115">Ir para Contabilidade > Entradas de diários > Diários gerais.</span><span class="sxs-lookup"><span data-stu-id="4d3ad-115">Go to General ledger > Journal entries > General journals.</span></span>
6. <span data-ttu-id="4d3ad-116">No campo Mostrar, selecione 'Todos.</span><span class="sxs-lookup"><span data-stu-id="4d3ad-116">In the Show field, select 'All'.</span></span>
7. <span data-ttu-id="4d3ad-117">Marque ou desmarque a caixa de seleção Mostrar apenas os que foram criados por usuário.</span><span class="sxs-lookup"><span data-stu-id="4d3ad-117">Select or clear the Show user-created only check box.</span></span>
8. <span data-ttu-id="4d3ad-118">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="4d3ad-118">In the list, mark the selected row.</span></span>
9. <span data-ttu-id="4d3ad-119">Clique em Linhas.</span><span class="sxs-lookup"><span data-stu-id="4d3ad-119">Click Lines.</span></span>
10. <span data-ttu-id="4d3ad-120">Clique em Comprovante.</span><span class="sxs-lookup"><span data-stu-id="4d3ad-120">Click Voucher.</span></span>
11. <span data-ttu-id="4d3ad-121">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="4d3ad-121">Close the page.</span></span>

