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
ms.openlocfilehash: 6ed76f82532d43a3c05b60b12176fe851e327956
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2175289"
---
# <a name="settle-transactions-between-ledger-accounts"></a><span data-ttu-id="5647c-103">Liquidar transações entre contas contábeis</span><span class="sxs-lookup"><span data-stu-id="5647c-103">Settle transactions between ledger accounts</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="5647c-104">Este procedimento mostra como liquidar transações entre contas contábeis e cancelar uma liquidação do razão.</span><span class="sxs-lookup"><span data-stu-id="5647c-104">This procedure shows how to settle transactions between ledger accounts and cancel a ledger settlement.</span></span> <span data-ttu-id="5647c-105">Este procedimento usa a empresa de dados de demonstração USMF.</span><span class="sxs-lookup"><span data-stu-id="5647c-105">This procedure uses the USMF demo data company.</span></span>


## <a name="settle-transaction-between-ledger-accounts"></a><span data-ttu-id="5647c-106">Liquidar transação entre contas contábeis</span><span class="sxs-lookup"><span data-stu-id="5647c-106">Settle transaction between ledger accounts</span></span>
1. <span data-ttu-id="5647c-107">Vá para Contabilidade > Tarefas periódicas > Liquidações do razão.</span><span class="sxs-lookup"><span data-stu-id="5647c-107">Go to General ledger > Periodic tasks > Ledger settlements.</span></span>
2. <span data-ttu-id="5647c-108">Na lista, localize a transação que você deseja liquidar.</span><span class="sxs-lookup"><span data-stu-id="5647c-108">In the list, find the transaction that you want to settle.</span></span>
   > [!NOTE]
   > <span data-ttu-id="5647c-109">O saldo do valor deve ser zero.</span><span class="sxs-lookup"><span data-stu-id="5647c-109">The amount balance must be zero.</span></span>  
3. <span data-ttu-id="5647c-110">Clique em Incluir.</span><span class="sxs-lookup"><span data-stu-id="5647c-110">Click Include.</span></span>
4. <span data-ttu-id="5647c-111">Clique em Aceitar.</span><span class="sxs-lookup"><span data-stu-id="5647c-111">Click Accept.</span></span>

## <a name="cancel-a-ledger-settlement"></a><span data-ttu-id="5647c-112">Cancelar uma liquidação do razão</span><span class="sxs-lookup"><span data-stu-id="5647c-112">Cancel a ledger settlement</span></span>

1. <span data-ttu-id="5647c-113">Vá para Contabilidade > Consultas e relatórios > Balancete.</span><span class="sxs-lookup"><span data-stu-id="5647c-113">Go to General ledger > Inquiries and reports > Trial balance.</span></span>
2. <span data-ttu-id="5647c-114">Clique em Parâmetros para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="5647c-114">Click Parameters to open the drop dialog.</span></span>
3. <span data-ttu-id="5647c-115">Clique em Atualizar.</span><span class="sxs-lookup"><span data-stu-id="5647c-115">Click Update.</span></span>
4. <span data-ttu-id="5647c-116">Na lista, localize a conta com a transação liquidada.</span><span class="sxs-lookup"><span data-stu-id="5647c-116">In the list, find the account that has the settled transaction.</span></span>
5. <span data-ttu-id="5647c-117">Clique em Todas as transações.</span><span class="sxs-lookup"><span data-stu-id="5647c-117">Click All transactions.</span></span>
6. <span data-ttu-id="5647c-118">Use um filtro para encontrar facilmente a transação na lista.</span><span class="sxs-lookup"><span data-stu-id="5647c-118">Use a filter to easily find the transaction in the list.</span></span>
7. <span data-ttu-id="5647c-119">Clique em Liquidações do razão.</span><span class="sxs-lookup"><span data-stu-id="5647c-119">Click Ledger settlements.</span></span>
8. <span data-ttu-id="5647c-120">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="5647c-120">In the list, mark the selected row.</span></span>

