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
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 6813871a4773d39d4abfdecc896a2aa8b320cbe0
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5222086"
---
# <a name="settle-transactions-between-ledger-accounts"></a><span data-ttu-id="2d493-103">Liquidar transações entre contas contábeis</span><span class="sxs-lookup"><span data-stu-id="2d493-103">Settle transactions between ledger accounts</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="2d493-104">Este procedimento mostra como liquidar transações entre contas contábeis e cancelar uma liquidação do razão.</span><span class="sxs-lookup"><span data-stu-id="2d493-104">This procedure shows how to settle transactions between ledger accounts and cancel a ledger settlement.</span></span> <span data-ttu-id="2d493-105">Este procedimento usa a empresa de dados de demonstração USMF.</span><span class="sxs-lookup"><span data-stu-id="2d493-105">This procedure uses the USMF demo data company.</span></span>


## <a name="settle-transaction-between-ledger-accounts"></a><span data-ttu-id="2d493-106">Liquidar transação entre contas contábeis</span><span class="sxs-lookup"><span data-stu-id="2d493-106">Settle transaction between ledger accounts</span></span>
1. <span data-ttu-id="2d493-107">Vá para Contabilidade > Tarefas periódicas > Liquidações do razão.</span><span class="sxs-lookup"><span data-stu-id="2d493-107">Go to General ledger > Periodic tasks > Ledger settlements.</span></span>
2. <span data-ttu-id="2d493-108">Na lista, localize a transação que você deseja liquidar.</span><span class="sxs-lookup"><span data-stu-id="2d493-108">In the list, find the transaction that you want to settle.</span></span>
   > [!NOTE]
   > <span data-ttu-id="2d493-109">O saldo do valor deve ser zero.</span><span class="sxs-lookup"><span data-stu-id="2d493-109">The amount balance must be zero.</span></span>  
3. <span data-ttu-id="2d493-110">Clique em Incluir.</span><span class="sxs-lookup"><span data-stu-id="2d493-110">Click Include.</span></span>
4. <span data-ttu-id="2d493-111">Clique em Aceitar.</span><span class="sxs-lookup"><span data-stu-id="2d493-111">Click Accept.</span></span>

## <a name="cancel-a-ledger-settlement"></a><span data-ttu-id="2d493-112">Cancelar uma liquidação do razão</span><span class="sxs-lookup"><span data-stu-id="2d493-112">Cancel a ledger settlement</span></span>

1. <span data-ttu-id="2d493-113">Vá para Contabilidade > Consultas e relatórios > Balancete.</span><span class="sxs-lookup"><span data-stu-id="2d493-113">Go to General ledger > Inquiries and reports > Trial balance.</span></span>
2. <span data-ttu-id="2d493-114">Clique em Parâmetros para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="2d493-114">Click Parameters to open the drop dialog.</span></span>
3. <span data-ttu-id="2d493-115">Clique em Atualizar.</span><span class="sxs-lookup"><span data-stu-id="2d493-115">Click Update.</span></span>
4. <span data-ttu-id="2d493-116">Na lista, localize a conta com a transação liquidada.</span><span class="sxs-lookup"><span data-stu-id="2d493-116">In the list, find the account that has the settled transaction.</span></span>
5. <span data-ttu-id="2d493-117">Clique em Todas as transações.</span><span class="sxs-lookup"><span data-stu-id="2d493-117">Click All transactions.</span></span>
6. <span data-ttu-id="2d493-118">Use um filtro para encontrar facilmente a transação na lista.</span><span class="sxs-lookup"><span data-stu-id="2d493-118">Use a filter to easily find the transaction in the list.</span></span>
7. <span data-ttu-id="2d493-119">Clique em Liquidações do razão.</span><span class="sxs-lookup"><span data-stu-id="2d493-119">Click Ledger settlements.</span></span>
8. <span data-ttu-id="2d493-120">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="2d493-120">In the list, mark the selected row.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]