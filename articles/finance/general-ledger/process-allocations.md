---
title: Processar alocações
description: Este artigo fornece informações sobre alocações, opções para processamento no Microsoft Dynamics 365 Finance e como elas podem ser usadas no planejamento de orçamento. As alocações são usadas para distribuir valores nas várias combinações da conta contábil. Elas ajudam a garantir que as despesas ou as receitas sejam cobradas no objeto correto na contabilidade.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AccountingDistribution, LedgerAllocationRule, MainAccount
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 17361
ms.assetid: 04c8548a-0af9-492b-954b-946b4f8ca023
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4c8216ebdd1f26601743e6b35849be0813d06b4a
ms.sourcegitcommit: 4676ea9646fa1a182103ecab93e78a69001f0b8d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/21/2020
ms.locfileid: "3612653"
---
# <a name="process-allocations"></a><span data-ttu-id="a9188-105">​Processar alocações​</span><span class="sxs-lookup"><span data-stu-id="a9188-105">Process allocations</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="a9188-106">Este artigo fornece informações sobre alocações, opções para processamento e como elas podem ser usadas no planejamento de orçamento.</span><span class="sxs-lookup"><span data-stu-id="a9188-106">This article provides information about allocations, the options for processing them, and how they can be used in budget planning.</span></span> <span data-ttu-id="a9188-107">As alocações são usadas para distribuir valores nas várias combinações da conta contábil.</span><span class="sxs-lookup"><span data-stu-id="a9188-107">Allocations are used to distribute amounts across multiple ledger account combinations.</span></span> <span data-ttu-id="a9188-108">Elas ajudam a garantir que as despesas ou as receitas sejam cobradas no objeto correto na contabilidade.</span><span class="sxs-lookup"><span data-stu-id="a9188-108">They help ensure that expenses or revenues are charged to the correct object in accounting.</span></span>

<span data-ttu-id="a9188-109">Os seguintes recursos oferecem suporte a esse processo:</span><span class="sxs-lookup"><span data-stu-id="a9188-109">The following capabilities support this process:</span></span>

-   <span data-ttu-id="a9188-110">Alocar valores de transações manualmente usando a ação dividida em distribuições contábeis, ou aplicando modelos padrão de dimensão financeira para um documento.</span><span class="sxs-lookup"><span data-stu-id="a9188-110">Manually allocate transaction amounts by using the Split action in accounting distributions, or by applying financial dimension default templates to a document.</span></span> <span data-ttu-id="a9188-111">Para obter mais informações, consulte [Distribuições contábeis](../accounts-payable/accounting-distributions.md).</span><span class="sxs-lookup"><span data-stu-id="a9188-111">For more information, see [Accounting distributions](../accounts-payable/accounting-distributions.md).</span></span>
-   <span data-ttu-id="a9188-112">Alocar automaticamente os valores das transações com base nas condições de alocação definidas na lista principal individual.</span><span class="sxs-lookup"><span data-stu-id="a9188-112">Automatically allocate transactions amounts based on allocation terms defined on individual main account.</span></span> <span data-ttu-id="a9188-113">As entradas da conta de alocação serão geradas para cada diário com base na porcentagem e na conta contábil de destino sempre que uma entrada contábil atender aos critérios definidos como a conta contábil de origem.</span><span class="sxs-lookup"><span data-stu-id="a9188-113">Allocation account entries will be generated for each journal based on the percentage and destination ledger account whenever an accounting entry meets the criteria defined as the source ledger account.</span></span> <span data-ttu-id="a9188-114">Para saber mais, consulte [Termos de alocação da conta principal](../general-ledger/main-account-allocation-terms.md)</span><span class="sxs-lookup"><span data-stu-id="a9188-114">For more information, see [Main account allocation terms](../general-ledger/main-account-allocation-terms.md)</span></span>
-   <span data-ttu-id="a9188-115">Alocar automaticamente os saldos ou valores fixos do razão com base nas regras de alocação do razão.</span><span class="sxs-lookup"><span data-stu-id="a9188-115">Automatically allocate ledger balances or fixed amounts based on ledger allocation rules.</span></span> <span data-ttu-id="a9188-116">As regras de alocação do razão são processadas periodicamente usando diários de alocação.</span><span class="sxs-lookup"><span data-stu-id="a9188-116">The ledger allocation rules are processed on a periodic basis using allocation journals.</span></span> <span data-ttu-id="a9188-117">Para obter mais informações, consulte [Regras de alocação](../general-ledger/ledger-allocation-rules.md).</span><span class="sxs-lookup"><span data-stu-id="a9188-117">For more information, see [Allocation rules](../general-ledger/ledger-allocation-rules.md).</span></span>

###  <a name="allocations-in-budget-planning"></a><span data-ttu-id="a9188-118">Alocações no planejamento de orçamento</span><span class="sxs-lookup"><span data-stu-id="a9188-118">Allocations in budget planning</span></span>

<span data-ttu-id="a9188-119">As regras de alocação do razão podem ser usadas para planos de orçamento.</span><span class="sxs-lookup"><span data-stu-id="a9188-119">Ledger allocation rules can be used for budget plans.</span></span> <span data-ttu-id="a9188-120">Quando você usa regras de alocação do razão no planejamento de orçamento, o trabalho regras de alocação funciona da mesma maneira que no razão, mas os dados de origem e destino são originários do plano de orçamento.</span><span class="sxs-lookup"><span data-stu-id="a9188-120">When you use ledger allocation rules in budget planning, the allocation rules work the same way they would in the ledger, but the source data and destination data comes from the budget plan.</span></span> <span data-ttu-id="a9188-121">Você pode selecionar manualmente as regras de alocação do razão a serem usadas para planos do orçamento.</span><span class="sxs-lookup"><span data-stu-id="a9188-121">You can manually select ledger allocation rules to use for budget plans.</span></span> <span data-ttu-id="a9188-122">Como alternativa, você pode usar uma agenda de alocação que seja executada como parte de um processo de fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="a9188-122">Alternatively, you can use an allocation schedule that runs as part of a workflow process.</span></span>

> [!NOTE]
> <span data-ttu-id="a9188-123">Você não pode usar as regras de alocação do razão intercompanhia para o planejamento de orçamento.</span><span class="sxs-lookup"><span data-stu-id="a9188-123">You can’t use intercompany ledger allocation rules for budget planning.</span></span>

