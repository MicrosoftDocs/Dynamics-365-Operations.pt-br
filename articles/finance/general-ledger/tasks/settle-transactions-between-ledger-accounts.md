---
title: Liquidar transações entre contas contábeis
description: Este procedimento mostra como liquidar transações entre contas contábeis e cancelar uma liquidação do razão.
author: aprilolson
manager: AnnBe
ms.date: 10/03/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerTransSettlement, LedgerTrialBalanceListPage, LedgerTrialBalanceListPageBalanceParms, LedgerTransAccount, LedgerTransSettled
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: bb53e9fee35712343f034389f00f3d4539cc652d
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/18/2020
ms.locfileid: "3144665"
---
# <a name="settle-transactions-between-ledger-accounts"></a><span data-ttu-id="d5767-103">Liquidar transações entre contas contábeis</span><span class="sxs-lookup"><span data-stu-id="d5767-103">Settle transactions between ledger accounts</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="d5767-104">Este procedimento mostra como liquidar transações entre contas contábeis e cancelar uma liquidação do razão.</span><span class="sxs-lookup"><span data-stu-id="d5767-104">This procedure shows how to settle transactions between ledger accounts and cancel a ledger settlement.</span></span> <span data-ttu-id="d5767-105">Este procedimento usa a empresa de dados de demonstração USMF.</span><span class="sxs-lookup"><span data-stu-id="d5767-105">This procedure uses the USMF demo data company.</span></span>


## <a name="settle-transaction-between-ledger-accounts"></a><span data-ttu-id="d5767-106">Liquidar transação entre contas contábeis</span><span class="sxs-lookup"><span data-stu-id="d5767-106">Settle transaction between ledger accounts</span></span>
1. <span data-ttu-id="d5767-107">Vá para Contabilidade > Tarefas periódicas > Liquidações do razão.</span><span class="sxs-lookup"><span data-stu-id="d5767-107">Go to General ledger > Periodic tasks > Ledger settlements.</span></span>
2. <span data-ttu-id="d5767-108">Na lista, localize a transação que você deseja liquidar.</span><span class="sxs-lookup"><span data-stu-id="d5767-108">In the list, find the transaction that you want to settle.</span></span>
   > [!NOTE]
   > <span data-ttu-id="d5767-109">O saldo do valor deve ser zero.</span><span class="sxs-lookup"><span data-stu-id="d5767-109">The amount balance must be zero.</span></span>  
3. <span data-ttu-id="d5767-110">Clique em Incluir.</span><span class="sxs-lookup"><span data-stu-id="d5767-110">Click Include.</span></span>
4. <span data-ttu-id="d5767-111">Clique em Aceitar.</span><span class="sxs-lookup"><span data-stu-id="d5767-111">Click Accept.</span></span>

## <a name="cancel-a-ledger-settlement"></a><span data-ttu-id="d5767-112">Cancelar uma liquidação do razão</span><span class="sxs-lookup"><span data-stu-id="d5767-112">Cancel a ledger settlement</span></span>

1. <span data-ttu-id="d5767-113">Vá para Contabilidade > Consultas e relatórios > Balancete.</span><span class="sxs-lookup"><span data-stu-id="d5767-113">Go to General ledger > Inquiries and reports > Trial balance.</span></span>
2. <span data-ttu-id="d5767-114">Clique em Parâmetros para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="d5767-114">Click Parameters to open the drop dialog.</span></span>
3. <span data-ttu-id="d5767-115">Clique em Atualizar.</span><span class="sxs-lookup"><span data-stu-id="d5767-115">Click Update.</span></span>
4. <span data-ttu-id="d5767-116">Na lista, localize a conta com a transação liquidada.</span><span class="sxs-lookup"><span data-stu-id="d5767-116">In the list, find the account that has the settled transaction.</span></span>
5. <span data-ttu-id="d5767-117">Clique em Todas as transações.</span><span class="sxs-lookup"><span data-stu-id="d5767-117">Click All transactions.</span></span>
6. <span data-ttu-id="d5767-118">Use um filtro para encontrar facilmente a transação na lista.</span><span class="sxs-lookup"><span data-stu-id="d5767-118">Use a filter to easily find the transaction in the list.</span></span>
7. <span data-ttu-id="d5767-119">Clique em Liquidações do razão.</span><span class="sxs-lookup"><span data-stu-id="d5767-119">Click Ledger settlements.</span></span>
8. <span data-ttu-id="d5767-120">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="d5767-120">In the list, mark the selected row.</span></span>

