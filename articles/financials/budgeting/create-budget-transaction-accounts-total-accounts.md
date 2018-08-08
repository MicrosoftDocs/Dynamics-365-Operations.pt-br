---
title: "Criar orçamentos de contas de transação e de contas totais"
description: "Este artigo fornece uma visão geral do processo para criar orçamentos com base nas contas totais. Também explica como ativar o controle de orçamento para as contas totais, se o controle de orçamento for necessário."
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: BudgetControlConfiguration, BudgetPlanGenerate
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 13051
ms.assetid: fb1bb2d3-445c-402f-a9a3-aa6503eed78e
ms.search.region: Global
ms.author: sigitac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 1d98cbff30620256c9d13e7b4a90314db150e33e
ms.openlocfilehash: 6129a5431cba22ea656e4d6f473a4e93a81131ea
ms.contentlocale: pt-br
ms.lasthandoff: 08/07/2018

---

# <a name="create-a-budget-from-transaction-accounts-and-total-accounts"></a><span data-ttu-id="ce2d5-104">Criar orçamentos de contas de transação e de contas totais</span><span class="sxs-lookup"><span data-stu-id="ce2d5-104">Create a budget from transaction accounts and total accounts</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="ce2d5-105">Este artigo fornece uma visão geral do processo para criar orçamentos com base nas contas totais.</span><span class="sxs-lookup"><span data-stu-id="ce2d5-105">This article provides an overview of the process for creating budgets based on total accounts.</span></span> <span data-ttu-id="ce2d5-106">Também explica como ativar o controle de orçamento para as contas totais, se o controle de orçamento for necessário.</span><span class="sxs-lookup"><span data-stu-id="ce2d5-106">It also explains how to turn on budget control for total accounts, if budget control is required.</span></span>

<span data-ttu-id="ce2d5-107">Ambos os documentos de entrada de plano de orçamento e de registro de orçamento permitem fazer o orçamento em contas principais com um tipo de conta principal **Total**.</span><span class="sxs-lookup"><span data-stu-id="ce2d5-107">Both budget plan and budget register entry documents allow for budgeting on main accounts that have a main account type of **Total**.</span></span> <span data-ttu-id="ce2d5-108">Os números reais só podem ser lançados para as contas principais transacionais.</span><span class="sxs-lookup"><span data-stu-id="ce2d5-108">Actuals can be posted only to transactional main accounts.</span></span> 

<span data-ttu-id="ce2d5-109">Para o processo periódico **Gerar plano de orçamento da Contabilidade**, na guia **Origem**, você pode especificar o tipo de conta principal **Total** como um critério.</span><span class="sxs-lookup"><span data-stu-id="ce2d5-109">For the **Generate budget plan from General ledger** periodic process, on the **Source** tab, you can specify the **Total** main account type as a criterion.</span></span> <span data-ttu-id="ce2d5-110">Nesse caso, cada conta principal total será incluída no plano de orçamento de destino, e o valor será igual ao valor total do intervalo de contas principais selecionadas.</span><span class="sxs-lookup"><span data-stu-id="ce2d5-110">In this case, each total main account will be included in the target budget plan, and the amount will equal the total amount of the range of selected main accounts.</span></span> 

<span data-ttu-id="ce2d5-111">Você pode ativar o controle de orçamento para contas principais do tipo **Total**.</span><span class="sxs-lookup"><span data-stu-id="ce2d5-111">You can activate budget control for main accounts of the **Total** type.</span></span> <span data-ttu-id="ce2d5-112">Essa funcionalidade tem suporte por meio do uso de grupos orçamentários.</span><span class="sxs-lookup"><span data-stu-id="ce2d5-112">This functionality is supported through the use of budget groups.</span></span> <span data-ttu-id="ce2d5-113">Para cada conta principal total, o orçamento que deve ser controlado para um grupo orçamentário deverá ser criado na página **Configuração de controle de orçamento**.</span><span class="sxs-lookup"><span data-stu-id="ce2d5-113">For each total main account, the budget that should be controlled for a budget group must be created on the **Budget control configuration **page.</span></span> <span data-ttu-id="ce2d5-114">Os critérios especificados devem incluir a conta principal total e o intervalo de contas.</span><span class="sxs-lookup"><span data-stu-id="ce2d5-114">The criteria that you specify must include the total main account and the range of accounts.</span></span> <span data-ttu-id="ce2d5-115">Para agilizar o processo de criação de grupos orçamentários, é possível aproveitar as vantagens da entidade de dados de grupos de Controle de orçamento.</span><span class="sxs-lookup"><span data-stu-id="ce2d5-115">To speed up the process of creating budget groups, you can take advantage of the Budget control groups data entity.</span></span> 

<span data-ttu-id="ce2d5-116">Quando um orçamento é usado em relatórios, como em um demonstrativo financeiro, a soma do orçamento para a conta de total consiste nos seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="ce2d5-116">When a budget is used in reporting, such as on a financial statement, the budget sum for the total account consists of the following amounts:</span></span>

-   <span data-ttu-id="ce2d5-117">Os orçamentos que são criados de cada conta contábil de transação no intervalo da conta de total.</span><span class="sxs-lookup"><span data-stu-id="ce2d5-117">The budgets that are created from each transaction ledger account in the interval of the total account.</span></span>
-   <span data-ttu-id="ce2d5-118">O total do orçamento especificado diretamente na conta de totais.</span><span class="sxs-lookup"><span data-stu-id="ce2d5-118">The budget amount that is entered directly on the total account.</span></span>

<span data-ttu-id="ce2d5-119">Portanto, você pode criar orçamentos separados para as contas de transação mais significativas no intervalo da conta de total e adicionar o valor de orçamento disponível à conta de total.</span><span class="sxs-lookup"><span data-stu-id="ce2d5-119">Therefore, you can create separate budgets for the most significant transaction accounts in the interval of the total account, and then add the available budget amount to the total account.</span></span>




