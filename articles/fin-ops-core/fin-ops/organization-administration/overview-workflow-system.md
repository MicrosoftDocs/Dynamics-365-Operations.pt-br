---
title: Visão geral do sistema de fluxo de trabalho
description: Este tópico descreve o sistema de fluxo de trabalho.
author: ChrisGarty
manager: AnnBe
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 56381
ms.assetid: 20b78595-e1d9-439a-ae1c-a776a3438919
ms.search.region: Global
ms.author: cgarty
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 068f464fe5385486827b2f904114eb663e08b2e8
ms.sourcegitcommit: e55efd2f62bf60f678108c09ad4701a76b20cc68
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/17/2020
ms.locfileid: "3697960"
---
# <a name="workflow-system-overview"></a><span data-ttu-id="c151f-103">Visão geral do sistema de fluxo de trabalho</span><span class="sxs-lookup"><span data-stu-id="c151f-103">Workflow system overview</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="c151f-104">Este tópico descreve o sistema de fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="c151f-104">This topic describes the workflow system.</span></span>

## <a name="what-is-workflow"></a><span data-ttu-id="c151f-105">O que é um fluxo de trabalho?</span><span class="sxs-lookup"><span data-stu-id="c151f-105">What is workflow?</span></span>

<span data-ttu-id="c151f-106">O termo *fluxo de trabalho* pode ser definido de duas maneiras: como um sistema e como um processo comercial.</span><span class="sxs-lookup"><span data-stu-id="c151f-106">The term *workflow* can be defined in two ways: as a system and as a business process.</span></span>

### <a name="workflow-is-a-system"></a><span data-ttu-id="c151f-107">O fluxo de trabalho é um sistema</span><span class="sxs-lookup"><span data-stu-id="c151f-107">Workflow is a system</span></span>

<span data-ttu-id="c151f-108">O fluxo de trabalho é um sistema executado no Microsoft Dynamics AX Application Object Server (AOS).</span><span class="sxs-lookup"><span data-stu-id="c151f-108">Workflow is a system that runs on the Application Object Server (AOS).</span></span> <span data-ttu-id="c151f-109">O sistema de fluxo de trabalho fornece uma funcionalidade que você pode usar para criar fluxos de trabalho individuais ou processos comerciais.</span><span class="sxs-lookup"><span data-stu-id="c151f-109">The workflow system provides functionality that you can use to create individual workflows, or business processes.</span></span>

### <a name="workflow-is-a-business-process"></a><span data-ttu-id="c151f-110">O fluxo de trabalho é um processo comercial</span><span class="sxs-lookup"><span data-stu-id="c151f-110">Workflow is a business process</span></span>

<span data-ttu-id="c151f-111">Um fluxo de trabalho representa um processo comercial.</span><span class="sxs-lookup"><span data-stu-id="c151f-111">A workflow represents a business process.</span></span> <span data-ttu-id="c151f-112">Ele define como um documento flui, ou se move, pelo sistema, mostrando quem deve concluir uma tarefa, tomar uma decisão ou aprovar um documento.</span><span class="sxs-lookup"><span data-stu-id="c151f-112">It defines how a document flows, or moves, through the system by showing who must complete a task, make a decision, or approve a document.</span></span> <span data-ttu-id="c151f-113">Por exemplo, a ilustração a seguir mostra um fluxo de trabalho para relatórios de despesas.</span><span class="sxs-lookup"><span data-stu-id="c151f-113">For example, the following illustration shows a workflow for expense reports.</span></span>

![Fluxo de trabalho com elementos que são atribuídos a usuários](./media/workflow_user.gif)

<span data-ttu-id="c151f-115">Para entender melhor esse fluxo de trabalho, suponha que Samuel envie um relatório de despesas no valor de US$ 7.000.</span><span class="sxs-lookup"><span data-stu-id="c151f-115">To better understand this workflow, suppose that Sam submits an expense report for USD 7,000.</span></span> <span data-ttu-id="c151f-116">Nesse cenário, Ivan deve revisar os recibos que Samuel direcionou a ele.</span><span class="sxs-lookup"><span data-stu-id="c151f-116">In this scenario, Ivan must review the receipts that Sam routes to him.</span></span> <span data-ttu-id="c151f-117">Depois, Francisco e Suzana devem aprovar o relatório de despesas.</span><span class="sxs-lookup"><span data-stu-id="c151f-117">Then Frank and Sue must approve the expense report.</span></span> <span data-ttu-id="c151f-118">Agora suponha que Samuel envie um relatório de despesas no valor de US$ 11.000.</span><span class="sxs-lookup"><span data-stu-id="c151f-118">Now suppose that Sam submits an expense report for USD 11,000.</span></span> <span data-ttu-id="c151f-119">Nesse cenário, Ivan deve revisar os recibos e Francisco, Suzana e Ana devem aprovar o relatório de despesas.</span><span class="sxs-lookup"><span data-stu-id="c151f-119">In this scenario, Ivan must review the receipts, and Frank, Sue, and Ann must approve the expense report.</span></span>

## <a name="benefits-of-using-the-workflow-system"></a><span data-ttu-id="c151f-120">Benefícios de usar o sistema de fluxo de trabalho</span><span class="sxs-lookup"><span data-stu-id="c151f-120">Benefits of using the workflow system</span></span>

<span data-ttu-id="c151f-121">O uso do sistema de fluxo de trabalho em sua organização traz vários benefícios:</span><span class="sxs-lookup"><span data-stu-id="c151f-121">There are several benefits of using the workflow system in your organization:</span></span>

- <span data-ttu-id="c151f-122">**Processos consistentes** – você pode definir como documentos específicos, como requisições de compra e relatórios de despesas, são processados.</span><span class="sxs-lookup"><span data-stu-id="c151f-122">**Consistent processes** – You can define how specific documents, such as purchase requisitions and expense reports, are processed.</span></span> <span data-ttu-id="c151f-123">Ao usar esse sistema, você garante que os documentos sejam processados e aprovados de maneira consistente e eficiente.</span><span class="sxs-lookup"><span data-stu-id="c151f-123">By using the workflow system, you ensure that documents are processed and approved in a consistent and efficient manner.</span></span>
- <span data-ttu-id="c151f-124">**Visibilidade do processo** – você pode rastrear o status, o histórico e as métricas de desempenho de instâncias do fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="c151f-124">**Process visibility** – You can track the status, history, and performance metrics of workflow instances.</span></span> <span data-ttu-id="c151f-125">Isso ajuda a determinar se alterações devem ser feitas no fluxo de trabalho para aumentar a eficiência.</span><span class="sxs-lookup"><span data-stu-id="c151f-125">This helps you determine whether changes should be made to the workflow to improve efficiency.</span></span>
- <span data-ttu-id="c151f-126">**Lista de trabalho centralizada** – os usuários podem exibir uma lista de trabalho centralizada que exibe as tarefas e aprovações de fluxo de trabalho que são atribuídas a elas.</span><span class="sxs-lookup"><span data-stu-id="c151f-126">**Centralized work list** – Users can view a centralized work list that displays the workflow tasks and approvals that are assigned to them.</span></span>


## <a name="workflow-content"></a><span data-ttu-id="c151f-127">Contexto do fluxo de trabalho</span><span class="sxs-lookup"><span data-stu-id="c151f-127">Workflow content</span></span>

+ [<span data-ttu-id="c151f-128">Arquitetura do sistema de fluxo de trabalho</span><span class="sxs-lookup"><span data-stu-id="c151f-128">Workflow system architecture</span></span>](workflow-system-architecture.md)
+ [<span data-ttu-id="c151f-129">Elementos de fluxo de trabalho</span><span class="sxs-lookup"><span data-stu-id="c151f-129">Workflow elements</span></span>](workflow-elements.md)
+ [<span data-ttu-id="c151f-130">Ações nos processos de aprovação do fluxo de trabalho</span><span class="sxs-lookup"><span data-stu-id="c151f-130">Actions in workflow approval processes</span></span>](workflow-actions.md)
+ [<span data-ttu-id="c151f-131">Visão geral de criação de fluxos de trabalho</span><span class="sxs-lookup"><span data-stu-id="c151f-131">Create workflows overview</span></span>](create-workflow.md)
+ [<span data-ttu-id="c151f-132">Configurar propriedades do fluxo de trabalho</span><span class="sxs-lookup"><span data-stu-id="c151f-132">Configure workflow properties</span></span>](configure-workflow-properties.md)
+ [<span data-ttu-id="c151f-133">Configurar tarefas manuais em um fluxo de trabalho</span><span class="sxs-lookup"><span data-stu-id="c151f-133">Configure manual tasks in a workflow</span></span>](configure-manual-task-workflow.md)
+ [<span data-ttu-id="c151f-134">Configurar tarefas automatizadas em um fluxo de trabalho</span><span class="sxs-lookup"><span data-stu-id="c151f-134">Configure automated tasks in a workflow</span></span>](configure-automated-task-workflow.md)
+ [<span data-ttu-id="c151f-135">Configurar processos de aprovação em um fluxo de trabalho</span><span class="sxs-lookup"><span data-stu-id="c151f-135">Configure approval processes in a workflow</span></span>](configure-approval-process-workflow.md)
+ [<span data-ttu-id="c151f-136">Configurar etapas de aprovação em um fluxo de trabalho</span><span class="sxs-lookup"><span data-stu-id="c151f-136">Configure approval steps in a workflow</span></span>](configure-approval-step-workflow.md)
+ [<span data-ttu-id="c151f-137">Configurar decisões manuais em um fluxo de trabalho</span><span class="sxs-lookup"><span data-stu-id="c151f-137">Configure manual decisions in a workflow</span></span>](configure-manual-decision-workflow.md)
+ [<span data-ttu-id="c151f-138">Configurar decisões condicionais em um fluxo de trabalho</span><span class="sxs-lookup"><span data-stu-id="c151f-138">Configure conditional decisions in a workflow</span></span>](configure-conditional-decision-workflow.md)
+ [<span data-ttu-id="c151f-139">Configurar atividades paralelas em um fluxo de trabalho</span><span class="sxs-lookup"><span data-stu-id="c151f-139">Configure parallel activities in a workflow</span></span>](configure-parallel-activity-workflow.md)
+ [<span data-ttu-id="c151f-140">Configurar ramificações paralelas em um fluxo de trabalho</span><span class="sxs-lookup"><span data-stu-id="c151f-140">Configure parallel branches in a workflow</span></span>](configure-parallel-branch-workflow.md)
+ [<span data-ttu-id="c151f-141">Configurar fluxos de trabalho de item de linha</span><span class="sxs-lookup"><span data-stu-id="c151f-141">Configure line-item workflows</span></span>](configure-line-item-workflow.md)
+ [<span data-ttu-id="c151f-142">Perguntas frequentes sobre fluxo de trabalho</span><span class="sxs-lookup"><span data-stu-id="c151f-142">Workflow FAQ</span></span>](workflow-FAQ.md)
