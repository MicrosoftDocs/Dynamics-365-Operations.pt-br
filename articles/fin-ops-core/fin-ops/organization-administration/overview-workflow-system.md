---
title: Visão geral do sistema de fluxo de trabalho
description: Este tópico descreve o sistema de fluxo de trabalho.
author: sericks007
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
ms.author: tjvass
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 6e5e795ca6f7831ecd3fa28be9782f0b287eea6e
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2189996"
---
# <a name="workflow-system-overview"></a><span data-ttu-id="f2afa-103">Visão geral do sistema de fluxo de trabalho</span><span class="sxs-lookup"><span data-stu-id="f2afa-103">Workflow system overview</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="f2afa-104">Este tópico descreve o sistema de fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="f2afa-104">This topic describes the workflow system.</span></span>

## <a name="what-is-workflow"></a><span data-ttu-id="f2afa-105">O que é um fluxo de trabalho?</span><span class="sxs-lookup"><span data-stu-id="f2afa-105">What is workflow?</span></span>

<span data-ttu-id="f2afa-106">O termo *fluxo de trabalho* pode ser definido de duas maneiras: como um sistema e como um processo comercial.</span><span class="sxs-lookup"><span data-stu-id="f2afa-106">The term *workflow* can be defined in two ways: as a system and as a business process.</span></span>

### <a name="workflow-is-a-system"></a><span data-ttu-id="f2afa-107">O fluxo de trabalho é um sistema</span><span class="sxs-lookup"><span data-stu-id="f2afa-107">Workflow is a system</span></span>

<span data-ttu-id="f2afa-108">O fluxo de trabalho é um sistema executado no Microsoft Dynamics AX Application Object Server (AOS).</span><span class="sxs-lookup"><span data-stu-id="f2afa-108">Workflow is a system that runs on the Application Object Server (AOS).</span></span> <span data-ttu-id="f2afa-109">O sistema de fluxo de trabalho fornece uma funcionalidade que você pode usar para criar fluxos de trabalho individuais ou processos comerciais.</span><span class="sxs-lookup"><span data-stu-id="f2afa-109">The workflow system provides functionality that you can use to create individual workflows, or business processes.</span></span>

### <a name="workflow-is-a-business-process"></a><span data-ttu-id="f2afa-110">O fluxo de trabalho é um processo comercial</span><span class="sxs-lookup"><span data-stu-id="f2afa-110">Workflow is a business process</span></span>

<span data-ttu-id="f2afa-111">Um fluxo de trabalho representa um processo comercial.</span><span class="sxs-lookup"><span data-stu-id="f2afa-111">A workflow represents a business process.</span></span> <span data-ttu-id="f2afa-112">Ele define como um documento flui, ou se move, pelo sistema, mostrando quem deve concluir uma tarefa, tomar uma decisão ou aprovar um documento.</span><span class="sxs-lookup"><span data-stu-id="f2afa-112">It defines how a document flows, or moves, through the system by showing who must complete a task, make a decision, or approve a document.</span></span> <span data-ttu-id="f2afa-113">Por exemplo, a ilustração a seguir mostra um fluxo de trabalho para relatórios de despesas.</span><span class="sxs-lookup"><span data-stu-id="f2afa-113">For example, the following illustration shows a workflow for expense reports.</span></span>

![Fluxo de trabalho com elementos que são atribuídos a usuários](./media/workflow_user.gif)

<span data-ttu-id="f2afa-115">Para entender melhor esse fluxo de trabalho, suponha que Samuel envie um relatório de despesas no valor de US$ 7.000.</span><span class="sxs-lookup"><span data-stu-id="f2afa-115">To better understand this workflow, suppose that Sam submits an expense report for USD 7,000.</span></span> <span data-ttu-id="f2afa-116">Nesse cenário, Ivan deve revisar os recibos que Samuel direcionou a ele.</span><span class="sxs-lookup"><span data-stu-id="f2afa-116">In this scenario, Ivan must review the receipts that Sam routes to him.</span></span> <span data-ttu-id="f2afa-117">Depois, Francisco e Suzana devem aprovar o relatório de despesas.</span><span class="sxs-lookup"><span data-stu-id="f2afa-117">Then Frank and Sue must approve the expense report.</span></span> <span data-ttu-id="f2afa-118">Agora suponha que Samuel envie um relatório de despesas no valor de US$ 11.000.</span><span class="sxs-lookup"><span data-stu-id="f2afa-118">Now suppose that Sam submits an expense report for USD 11,000.</span></span> <span data-ttu-id="f2afa-119">Nesse cenário, Ivan deve revisar os recibos e Francisco, Suzana e Ana devem aprovar o relatório de despesas.</span><span class="sxs-lookup"><span data-stu-id="f2afa-119">In this scenario, Ivan must review the receipts, and Frank, Sue, and Ann must approve the expense report.</span></span>

## <a name="benefits-of-using-the-workflow-system"></a><span data-ttu-id="f2afa-120">Benefícios de usar o sistema de fluxo de trabalho</span><span class="sxs-lookup"><span data-stu-id="f2afa-120">Benefits of using the workflow system</span></span>

<span data-ttu-id="f2afa-121">O uso do sistema de fluxo de trabalho em sua organização traz vários benefícios:</span><span class="sxs-lookup"><span data-stu-id="f2afa-121">There are several benefits of using the workflow system in your organization:</span></span>

- <span data-ttu-id="f2afa-122">**Processos consistentes** – você pode definir como documentos específicos, como requisições de compra e relatórios de despesas, são processados.</span><span class="sxs-lookup"><span data-stu-id="f2afa-122">**Consistent processes** – You can define how specific documents, such as purchase requisitions and expense reports, are processed.</span></span> <span data-ttu-id="f2afa-123">Ao usar esse sistema, você garante que os documentos sejam processados e aprovados de maneira consistente e eficiente.</span><span class="sxs-lookup"><span data-stu-id="f2afa-123">By using the workflow system, you ensure that documents are processed and approved in a consistent and efficient manner.</span></span>
- <span data-ttu-id="f2afa-124">**Visibilidade do processo** – você pode rastrear o status, o histórico e as métricas de desempenho de instâncias do fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="f2afa-124">**Process visibility** – You can track the status, history, and performance metrics of workflow instances.</span></span> <span data-ttu-id="f2afa-125">Isso ajuda a determinar se alterações devem ser feitas no fluxo de trabalho para aumentar a eficiência.</span><span class="sxs-lookup"><span data-stu-id="f2afa-125">This helps you determine whether changes should be made to the workflow to improve efficiency.</span></span>
- <span data-ttu-id="f2afa-126">**Lista de trabalho centralizada** – os usuários podem exibir uma lista de trabalho centralizada que exibe as tarefas e aprovações de fluxo de trabalho que são atribuídas a elas.</span><span class="sxs-lookup"><span data-stu-id="f2afa-126">**Centralized work list** – Users can view a centralized work list that displays the workflow tasks and approvals that are assigned to them.</span></span>


## <a name="workflow-content"></a><span data-ttu-id="f2afa-127">Contexto do fluxo de trabalho</span><span class="sxs-lookup"><span data-stu-id="f2afa-127">Workflow content</span></span>

+ [<span data-ttu-id="f2afa-128">Arquitetura do fluxo de trabalho</span><span class="sxs-lookup"><span data-stu-id="f2afa-128">Workflow architecture</span></span>](workflow-system-architecture.md)
+ [<span data-ttu-id="f2afa-129">Elementos do fluxo de trabalho</span><span class="sxs-lookup"><span data-stu-id="f2afa-129">Workflow elements</span></span>](workflow-elements.md)
+ [<span data-ttu-id="f2afa-130">Ações de fluxo de trabalho</span><span class="sxs-lookup"><span data-stu-id="f2afa-130">Workflow actions</span></span>](workflow-actions.md)
+ [<span data-ttu-id="f2afa-131">Criar um fluxo de trabalho</span><span class="sxs-lookup"><span data-stu-id="f2afa-131">Create a workflow</span></span>](create-workflow.md)
+ [<span data-ttu-id="f2afa-132">Configurar propriedades do fluxo de trabalho</span><span class="sxs-lookup"><span data-stu-id="f2afa-132">Configure workflow properties</span></span>](configure-workflow-properties.md)
+ [<span data-ttu-id="f2afa-133">Configurar uma tarefa manual em um fluxo de trabalho</span><span class="sxs-lookup"><span data-stu-id="f2afa-133">Configure a manual task in a workflow</span></span>](configure-manual-task-workflow.md)
+ [<span data-ttu-id="f2afa-134">Configurar uma tarefa automatizada em um fluxo de trabalho</span><span class="sxs-lookup"><span data-stu-id="f2afa-134">Configure an automated task in a workflow</span></span>](configure-automated-task-workflow.md)
+ [<span data-ttu-id="f2afa-135">Configurar um processo de aprovação em um fluxo de trabalho</span><span class="sxs-lookup"><span data-stu-id="f2afa-135">Configure an approval process in a workflow</span></span>](configure-approval-process-workflow.md)
+ [<span data-ttu-id="f2afa-136">Configurar uma etapa de aprovação em um fluxo de trabalho</span><span class="sxs-lookup"><span data-stu-id="f2afa-136">Configure an approval step in a workflow</span></span>](configure-approval-step-workflow.md)
+ [<span data-ttu-id="f2afa-137">Configurar uma decisão manual em um fluxo de trabalho</span><span class="sxs-lookup"><span data-stu-id="f2afa-137">Configure a manual decision in a workflow</span></span>](configure-manual-decision-workflow.md)
+ [<span data-ttu-id="f2afa-138">Configurar uma decisão condicional em um fluxo de trabalho</span><span class="sxs-lookup"><span data-stu-id="f2afa-138">Configure a conditional decision in a workflow</span></span>](configure-conditional-decision-workflow.md)
+ [<span data-ttu-id="f2afa-139">Configurar uma atividade paralela em um fluxo de trabalho</span><span class="sxs-lookup"><span data-stu-id="f2afa-139">Configure a parallel activity in a workflow</span></span>](configure-parallel-activity-workflow.md)
+ [<span data-ttu-id="f2afa-140">Configurar uma ramificação paralela em um fluxo de trabalho</span><span class="sxs-lookup"><span data-stu-id="f2afa-140">Configure a parallel branch in a workflow</span></span>](configure-parallel-branch-workflow.md)
+ [<span data-ttu-id="f2afa-141">Configurar um fluxo de trabalho de item de linha</span><span class="sxs-lookup"><span data-stu-id="f2afa-141">Configure a line-item workflow</span></span>](configure-line-item-workflow.md)
+ [<span data-ttu-id="f2afa-142">Perguntas frequentes sobre fluxo de trabalho</span><span class="sxs-lookup"><span data-stu-id="f2afa-142">Workflow FAQ</span></span>](workflow-FAQ.md)
