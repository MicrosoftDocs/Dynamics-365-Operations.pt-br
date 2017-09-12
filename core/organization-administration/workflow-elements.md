---
title: Elementos do fluxo de trabalho
description: "Este artigo descreve os diversos elementos que compõem um fluxo de trabalho."
author: sericks007
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 56441
ms.assetid: de740262-6ffd-42b9-a325-540eae5cec94
ms.search.region: Global
ms.author: tjvass
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 08c38aada355583c5a6872f75b57db95d9b81786
ms.openlocfilehash: 5620a91ff9f300bed782170307a295ab79fc5b2e
ms.contentlocale: pt-br
ms.lasthandoff: 07/18/2017

---

# <a name="workflow-elements"></a><span data-ttu-id="c8090-103">Elementos do fluxo de trabalho</span><span class="sxs-lookup"><span data-stu-id="c8090-103">Workflow elements</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="c8090-104">Este artigo descreve os diversos elementos que compõem um fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="c8090-104">This article describes the various elements that make up a workflow.</span></span>

<span data-ttu-id="c8090-105">Um fluxo de trabalho consiste em elementos.</span><span class="sxs-lookup"><span data-stu-id="c8090-105">A workflow consists of elements.</span></span> <span data-ttu-id="c8090-106">As seções a seguir descrevem cada tipo de elemento.</span><span class="sxs-lookup"><span data-stu-id="c8090-106">The sections that follow describe each type of element.</span></span>

## <a name="tasks"></a><span data-ttu-id="c8090-107">Tarefas</span><span class="sxs-lookup"><span data-stu-id="c8090-107">Tasks</span></span>
<span data-ttu-id="c8090-108">Uma *tarefa* é uma unidade de trabalho que deve ser executada.</span><span class="sxs-lookup"><span data-stu-id="c8090-108">A *task* is a unit of work that must be performed.</span></span> <span data-ttu-id="c8090-109">Dois tipos de tarefas podem ser adicionados a um fluxo de trabalho: tarefas manuais e tarefas automatizadas.</span><span class="sxs-lookup"><span data-stu-id="c8090-109">Two types of tasks can be added to a workflow: manual tasks and automated tasks.</span></span>

### <a name="manual-task"></a><span data-ttu-id="c8090-110">Tarefa manual</span><span class="sxs-lookup"><span data-stu-id="c8090-110">Manual task</span></span>

<span data-ttu-id="c8090-111">Uma *tarefa manual* é uma unidade de trabalho que deve ser executada por um usuário.</span><span class="sxs-lookup"><span data-stu-id="c8090-111">A *manual task* is a unit of work that must be performed by a user.</span></span> <span data-ttu-id="c8090-112">Por exemplo, um fluxo de trabalho de relatório de despesas pode ter tarefas manuais que exijam que os usuários atribuídos concluam as seguintes ações:</span><span class="sxs-lookup"><span data-stu-id="c8090-112">For example, an expense report workflow can have manual tasks that require the assigned users to complete the following actions:</span></span>

-   <span data-ttu-id="c8090-113">Revisem os recibos que são enviados junto com um relatório de despesas.</span><span class="sxs-lookup"><span data-stu-id="c8090-113">Review the receipts that are submitted together with an expense report.</span></span>
-   <span data-ttu-id="c8090-114">Liguem para o gerente de um funcionário.</span><span class="sxs-lookup"><span data-stu-id="c8090-114">Call an employee's manager.</span></span>

### <a name="automated-task"></a><span data-ttu-id="c8090-115">Tarefa automatizada</span><span class="sxs-lookup"><span data-stu-id="c8090-115">Automated task</span></span>

<span data-ttu-id="c8090-116">Uma *tarefa automatizada* é uma unidade de trabalho que deve ser executada pelo sistema.</span><span class="sxs-lookup"><span data-stu-id="c8090-116">An *automated task* is a unit of work that must be performed by the system.</span></span> <span data-ttu-id="c8090-117">Não exige interação humana.</span><span class="sxs-lookup"><span data-stu-id="c8090-117">No human interaction is required.</span></span> <span data-ttu-id="c8090-118">Por exemplo, um fluxo de trabalho da ordem de venda pode ter tarefas automatizadas que exijam que o sistema conclua as seguintes ações:</span><span class="sxs-lookup"><span data-stu-id="c8090-118">For example, a sales order workflow can have automated tasks that require the system to complete the following actions:</span></span>

-   <span data-ttu-id="c8090-119">Execute uma verificação de crédito.</span><span class="sxs-lookup"><span data-stu-id="c8090-119">Perform a credit check.</span></span>
-   <span data-ttu-id="c8090-120">Crie um registro para o cliente, caso não exista um ainda.</span><span class="sxs-lookup"><span data-stu-id="c8090-120">Create a customer record for the customer, if a record doesn't already exist.</span></span>

## <a name="approval-processes"></a><span data-ttu-id="c8090-121">Processos de aprovação</span><span class="sxs-lookup"><span data-stu-id="c8090-121">Approval processes</span></span>
<span data-ttu-id="c8090-122">Um *processo de aprovação* consiste em etapas isoladas.</span><span class="sxs-lookup"><span data-stu-id="c8090-122">An *approval process* is a process that consists of separate steps.</span></span> <span data-ttu-id="c8090-123">Em cada etapa de aprovação, o usuário pode executar as seguintes ações:</span><span class="sxs-lookup"><span data-stu-id="c8090-123">At each approval step, the user can perform the following actions:</span></span>

-   <span data-ttu-id="c8090-124">Aprovar o documento.</span><span class="sxs-lookup"><span data-stu-id="c8090-124">Approve the document.</span></span>
-   <span data-ttu-id="c8090-125">Rejeitar o documento.</span><span class="sxs-lookup"><span data-stu-id="c8090-125">Reject the document.</span></span>
-   <span data-ttu-id="c8090-126">Solicitar uma alteração no documento.</span><span class="sxs-lookup"><span data-stu-id="c8090-126">Request a change to the document.</span></span>
-   <span data-ttu-id="c8090-127">Atribuir o documento a outro usuário para aprovação.</span><span class="sxs-lookup"><span data-stu-id="c8090-127">Assign the document to another user for approval.</span></span>

## <a name="lineitem-workflow-elements"></a><span data-ttu-id="c8090-128">Elementos de fluxo de trabalho de item de linha</span><span class="sxs-lookup"><span data-stu-id="c8090-128">Lineitem workflow elements</span></span>
<span data-ttu-id="c8090-129">Um fluxo de trabalho pode ser criado para processar documentos ou os itens de linha em um documento.</span><span class="sxs-lookup"><span data-stu-id="c8090-129">A workflow can be created to process either documents or the line items on a document.</span></span> <span data-ttu-id="c8090-130">Por exemplo, você criou um fluxo de trabalho de aprovação para folhas de ponto.</span><span class="sxs-lookup"><span data-stu-id="c8090-130">For example, you've created an approval workflow for timesheets.</span></span> <span data-ttu-id="c8090-131">(Faremos referência a esse fluxo de trabalho como *fluxo de trabalho de documento*.) Você pode adicionar um elemento de *fluxo de trabalho de item de linha* a esse fluxo de trabalho de documento.</span><span class="sxs-lookup"><span data-stu-id="c8090-131">(We will refer to this workflow as the *document workflow*.) You can add a *line-item workflow* element to that document workflow.</span></span> <span data-ttu-id="c8090-132">Quando o elemento de item de linha é executado, cada item de linha do documento é enviado para processamento.</span><span class="sxs-lookup"><span data-stu-id="c8090-132">When the line-item element is run, each line item on the document is submitted for processing.</span></span> <span data-ttu-id="c8090-133">Talvez seja conveniente que todos os itens de linha sejam processados pelo mesmo fluxo de trabalho de item de linha ou que cada item de linha seja processado por um fluxo de trabalho de item de linha diferente.</span><span class="sxs-lookup"><span data-stu-id="c8090-133">You might want all the line items to be processed by the same line-item workflow, or you might want each line item to be processed by a different line-item workflow.</span></span> <span data-ttu-id="c8090-134">Suponha que um funcionário tenha enviado uma folha de ponto que se assemelhe à figura a seguir.</span><span class="sxs-lookup"><span data-stu-id="c8090-134">Imagine that an employee has submitted a timesheet that resembles the following figure.</span></span> <span data-ttu-id="c8090-135">![Fluxo de trabalho com itens de linha](./media/workflow_lineitemworkflow.gif) Nesse cenário, você pode optar por criar os seguintes fluxos de trabalho de item de linha:</span><span class="sxs-lookup"><span data-stu-id="c8090-135">![Workflow with line items](./media/workflow_lineitemworkflow.gif) In this scenario, you might want to create the following line-item workflows:</span></span>

-   <span data-ttu-id="c8090-136">**Fluxo de trabalho de item de linha 1** – Esse fluxo de trabalho é usado para processar itens de linha onde a ID de projeto é 1111.</span><span class="sxs-lookup"><span data-stu-id="c8090-136">**Line-item workflow 1** – This workflow is used to process line items where the project ID is 1111.</span></span>
-   <span data-ttu-id="c8090-137">**Fluxo de trabalho de item de linha 2** – Esse fluxo de trabalho é usado para processar itens de linha onde a ID de projeto é 2222.</span><span class="sxs-lookup"><span data-stu-id="c8090-137">**Line-item workflow 2** – This workflow is used to process line items where the project ID is 2222.</span></span>
-   <span data-ttu-id="c8090-138">**Fluxo de trabalho de item de linha 3** – esse fluxo de trabalho é usado para processar itens de linha onde a ID de projeto é 3333.</span><span class="sxs-lookup"><span data-stu-id="c8090-138">**Line-item workflow 3** – This workflow is used to process line items where the project ID is 3333.</span></span>

## <a name="flowcontrol-elements"></a><span data-ttu-id="c8090-139">Elementos de controle de fluxo</span><span class="sxs-lookup"><span data-stu-id="c8090-139">Flowcontrol elements</span></span>
<span data-ttu-id="c8090-140">Os elementos a seguir permitem projetar os fluxos de trabalho com ramificações alternativas ou ramificações executadas ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="c8090-140">The following elements let you design workflows that have alternate branches or branches that run at the same time.</span></span>

### <a name="manual-decision"></a><span data-ttu-id="c8090-141">Decisão manual</span><span class="sxs-lookup"><span data-stu-id="c8090-141">Manual decision</span></span>

<span data-ttu-id="c8090-142">Uma *decisão manual* é um ponto em que um fluxo de trabalho se divide em duas ramificações.</span><span class="sxs-lookup"><span data-stu-id="c8090-142">A *manual decision* is a point where a workflow divides into two branches.</span></span> <span data-ttu-id="c8090-143">Um usuário deve tomar uma decisão, e essa decisão determina qual ramificação é usada para processar o documento que foi enviado.</span><span class="sxs-lookup"><span data-stu-id="c8090-143">A user must make a decision, and this decision determines which branch is used to process the document that was submitted.</span></span>

### <a name="conditional-decision"></a><span data-ttu-id="c8090-144">Decisão condicional</span><span class="sxs-lookup"><span data-stu-id="c8090-144">Conditional decision</span></span>

<span data-ttu-id="c8090-145">Uma *decisão condicional* também é um ponto em que um fluxo de trabalho se divide em duas ramificações.</span><span class="sxs-lookup"><span data-stu-id="c8090-145">A *conditional decision* is also a point where a workflow divides into two branches.</span></span> <span data-ttu-id="c8090-146">No entanto, o sistema decide qual ramificação é usada para processar o documento que foi enviado.</span><span class="sxs-lookup"><span data-stu-id="c8090-146">However, the system decides which branch is used to process the document that was submitted.</span></span> <span data-ttu-id="c8090-147">Para tomar esta decisão, o sistema avaliará o documento para determinar se ele atende às condições especificadas.</span><span class="sxs-lookup"><span data-stu-id="c8090-147">To make this decision, the system evaluates the document to determine whether it meets specified conditions.</span></span>

### <a name="parallel-activity"></a><span data-ttu-id="c8090-148">Atividade paralela</span><span class="sxs-lookup"><span data-stu-id="c8090-148">Parallel activity</span></span>

<span data-ttu-id="c8090-149">Uma *atividade paralela* é um elemento de fluxo de trabalho que inclui duas ou mais ramificações de fluxo de trabalho executadas ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="c8090-149">A *parallel activity* is a workflow element that includes two or more workflow branches that run at the same time.</span></span>

### <a name="subworkflow"></a><span data-ttu-id="c8090-150">Subfluxo de trabalho</span><span class="sxs-lookup"><span data-stu-id="c8090-150">Subworkflow</span></span>

<span data-ttu-id="c8090-151">Um *subfluxo de trabalho* é um fluxo de trabalho executado no contexto de outro fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="c8090-151">A *subworkflow* is a workflow that runs in the context of another workflow.</span></span>




