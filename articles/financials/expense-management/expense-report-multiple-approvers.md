---
title: "Relatórios de despesas e vários aprovadores"
description: "Este tópico fornece informações sobre os relatórios de despesas que exigem aprovação por mais de uma pessoa."
author: saraschi2
manager: AnnBe
ms.date: 02/23/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: TrvExpensesReportList
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 25fa39dc81fc721d7593a25a102ce47041ebc5f0
ms.openlocfilehash: 0f7592c580a21040c8b630885939ceaab3855c2c
ms.contentlocale: pt-br
ms.lasthandoff: 03/13/2018

---

# <a name="expense-reports-and-multiple-approvers"></a><span data-ttu-id="690de-103">Relatórios de despesas e vários aprovadores</span><span class="sxs-lookup"><span data-stu-id="690de-103">Expense reports and multiple approvers</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="690de-104">Dependendo das políticas de aprovação de despesas da sua organização, talvez seja necessário que mais de uma pessoa aprove um relatório de despesas enviado por um funcionário.</span><span class="sxs-lookup"><span data-stu-id="690de-104">Depending on your organization's expense approval policies, more than one person might have to approve an expense report that is submitted by an employee.</span></span> <span data-ttu-id="690de-105">Ao configurar o processo de fluxo de trabalho para a aprovação do relatório de despesas, você poderá adicionar os elementos do fluxo de trabalho que incluem tarefas ou etapas para um ou mais aprovadores de relatório de despesas.</span><span class="sxs-lookup"><span data-stu-id="690de-105">When you set up the workflow process for expense report approval, you can add workflow elements that include tasks or steps for one or more expense report approvers.</span></span> <span data-ttu-id="690de-106">Por exemplo, você pode exigir que todos os relatórios de despesas sejam aprovados primeiro pelo gerente do funcionário que enviou o relatório e, em seguida, pelo coordenador de contas a pagar.</span><span class="sxs-lookup"><span data-stu-id="690de-106">For example, you might require that all expense reports be approved first by the manager of the employee who submitted the report and then by the Accounts payable coordinator.</span></span>

<span data-ttu-id="690de-107">Se você decidir exigir vários aprovadores do relatório de despesas, você pode adicionar os elementos do fluxo de trabalho em qualquer uma das seguintes maneiras:</span><span class="sxs-lookup"><span data-stu-id="690de-107">If you decide to require multiple expense report approvers, you can add the workflow elements in any of the following ways:</span></span>

- <span data-ttu-id="690de-108">Adicionar um elemento de aprovação que tenha uma etapa.</span><span class="sxs-lookup"><span data-stu-id="690de-108">Add one approval element that has one step.</span></span> <span data-ttu-id="690de-109">Por exemplo, a etapa pode exigir que um relatório de despesas seja atribuído a um grupo de usuários e que seja aprovado por 50% dos seus membros.</span><span class="sxs-lookup"><span data-stu-id="690de-109">For example, the step might require that an expense report be assigned to a user group, and that it be approved by 50 percent of the user group's members.</span></span>
- <span data-ttu-id="690de-110">Adicionar um elemento de aprovação que tenha várias etapas.</span><span class="sxs-lookup"><span data-stu-id="690de-110">Add one approval element that has multiple steps.</span></span> <span data-ttu-id="690de-111">Por exemplo, o elemento de aprovação pode ter as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="690de-111">For example, the approval element might have the following steps:</span></span>

    1. <span data-ttu-id="690de-112">O gerente do funcionário que enviou o relatório de despesas aprová-lo.</span><span class="sxs-lookup"><span data-stu-id="690de-112">The manager of the employee who submitted the expense report approves it.</span></span>
    2. <span data-ttu-id="690de-113">O funcionário de contas a pagar verificar os recibos e os itens do relatório de despesas.</span><span class="sxs-lookup"><span data-stu-id="690de-113">The Accounts payable clerk verifies the receipts and the expense report items.</span></span>
    3. <span data-ttu-id="690de-114">O proprietário de orçamento aprovar o relatório de despesas.</span><span class="sxs-lookup"><span data-stu-id="690de-114">The budget owner approves the expense report.</span></span>

- <span data-ttu-id="690de-115">Adicionar vários elementos de aprovação, cada um com uma etapa.</span><span class="sxs-lookup"><span data-stu-id="690de-115">Add multiple approval elements, each of which has one step.</span></span> <span data-ttu-id="690de-116">Por exemplo, você pode adicionar um elemento de aprovação separado para cada uma das seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="690de-116">For example, you might add a separate approval element for each of the following steps:</span></span>

    1. <span data-ttu-id="690de-117">O gerente do funcionário aprovar o relatório de despesas.</span><span class="sxs-lookup"><span data-stu-id="690de-117">The employee's manager approves the expense report.</span></span>
    2. <span data-ttu-id="690de-118">O proprietário de orçamento aprovar o relatório de despesas.</span><span class="sxs-lookup"><span data-stu-id="690de-118">The budget owner approves the expense report.</span></span>
