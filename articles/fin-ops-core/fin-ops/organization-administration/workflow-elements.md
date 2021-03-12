---
title: Elementos do fluxo de trabalho
description: Este tópico descreve os diversos elementos que compõem um fluxo de trabalho.
author: ChrisGarty
manager: AnnBe
ms.date: 11/03/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: sericks
ms.custom: 56441
ms.assetid: de740262-6ffd-42b9-a325-540eae5cec94
ms.search.region: Global
ms.author: cgarty
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b259d733076193cda793a227bd0bb71c232339d1
ms.sourcegitcommit: b112925c389a460a98c3401cc2c67df7091b066f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/19/2020
ms.locfileid: "4797567"
---
# <a name="workflow-elements"></a><span data-ttu-id="d760b-103">Elementos do fluxo de trabalho</span><span class="sxs-lookup"><span data-stu-id="d760b-103">Workflow elements</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="d760b-104">Este tópico descreve os diversos elementos que compõem um fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="d760b-104">This topic describes the various elements that make up a workflow.</span></span>

<span data-ttu-id="d760b-105">Um fluxo de trabalho consiste em elementos.</span><span class="sxs-lookup"><span data-stu-id="d760b-105">A workflow consists of elements.</span></span> <span data-ttu-id="d760b-106">As seções a seguir descrevem cada tipo de elemento.</span><span class="sxs-lookup"><span data-stu-id="d760b-106">The sections that follow describe each type of element.</span></span>

## <a name="tasks"></a><span data-ttu-id="d760b-107">Tarefas</span><span class="sxs-lookup"><span data-stu-id="d760b-107">Tasks</span></span>

<span data-ttu-id="d760b-108">Uma *tarefa* é uma unidade de trabalho que deve ser executada.</span><span class="sxs-lookup"><span data-stu-id="d760b-108">A *task* is a unit of work that must be performed.</span></span> <span data-ttu-id="d760b-109">Dois tipos de tarefas podem ser adicionados a um fluxo de trabalho: tarefas manuais e tarefas automatizadas.</span><span class="sxs-lookup"><span data-stu-id="d760b-109">Two types of tasks can be added to a workflow: manual tasks and automated tasks.</span></span>

### <a name="manual-task"></a><span data-ttu-id="d760b-110">Tarefa manual</span><span class="sxs-lookup"><span data-stu-id="d760b-110">Manual task</span></span>

<span data-ttu-id="d760b-111">Uma *tarefa manual* é uma unidade de trabalho que deve ser executada por um usuário.</span><span class="sxs-lookup"><span data-stu-id="d760b-111">A *manual task* is a unit of work that must be performed by a user.</span></span> <span data-ttu-id="d760b-112">Por exemplo, um fluxo de trabalho de relatório de despesas pode ter tarefas manuais que exijam que os usuários atribuídos concluam as seguintes ações:</span><span class="sxs-lookup"><span data-stu-id="d760b-112">For example, an expense report workflow can have manual tasks that require the assigned users to complete the following actions:</span></span>

- <span data-ttu-id="d760b-113">Revisem os recibos que são enviados junto com um relatório de despesas.</span><span class="sxs-lookup"><span data-stu-id="d760b-113">Review the receipts that are submitted together with an expense report.</span></span>
- <span data-ttu-id="d760b-114">Liguem para o gerente de um funcionário.</span><span class="sxs-lookup"><span data-stu-id="d760b-114">Call an employee's manager.</span></span>

### <a name="automated-task"></a><span data-ttu-id="d760b-115">Tarefa automatizada</span><span class="sxs-lookup"><span data-stu-id="d760b-115">Automated task</span></span>

<span data-ttu-id="d760b-116">Uma *tarefa automatizada* é uma unidade de trabalho que deve ser executada pelo sistema.</span><span class="sxs-lookup"><span data-stu-id="d760b-116">An *automated task* is a unit of work that must be performed by the system.</span></span> <span data-ttu-id="d760b-117">Não exige interação humana.</span><span class="sxs-lookup"><span data-stu-id="d760b-117">No human interaction is required.</span></span> <span data-ttu-id="d760b-118">Por exemplo, um fluxo de trabalho da ordem de venda pode ter tarefas automatizadas que exijam que o sistema conclua as seguintes ações:</span><span class="sxs-lookup"><span data-stu-id="d760b-118">For example, a sales order workflow can have automated tasks that require the system to complete the following actions:</span></span>

- <span data-ttu-id="d760b-119">Execute uma verificação de crédito.</span><span class="sxs-lookup"><span data-stu-id="d760b-119">Perform a credit check.</span></span>
- <span data-ttu-id="d760b-120">Crie um registro para o cliente, caso não exista um ainda.</span><span class="sxs-lookup"><span data-stu-id="d760b-120">Create a customer record for the customer, if a record doesn't already exist.</span></span>

## <a name="approval-processes"></a><span data-ttu-id="d760b-121">Processos de aprovação</span><span class="sxs-lookup"><span data-stu-id="d760b-121">Approval processes</span></span>

<span data-ttu-id="d760b-122">Um *processo de aprovação* consiste em etapas isoladas.</span><span class="sxs-lookup"><span data-stu-id="d760b-122">An *approval process* is a process that consists of separate steps.</span></span> <span data-ttu-id="d760b-123">Em cada etapa de aprovação, o usuário pode executar as seguintes ações:</span><span class="sxs-lookup"><span data-stu-id="d760b-123">At each approval step, the user can perform the following actions:</span></span>

- <span data-ttu-id="d760b-124">Aprovar o documento.</span><span class="sxs-lookup"><span data-stu-id="d760b-124">Approve the document.</span></span>
- <span data-ttu-id="d760b-125">Rejeitar o documento.</span><span class="sxs-lookup"><span data-stu-id="d760b-125">Reject the document.</span></span>
- <span data-ttu-id="d760b-126">Solicitar uma alteração no documento.</span><span class="sxs-lookup"><span data-stu-id="d760b-126">Request a change to the document.</span></span>
- <span data-ttu-id="d760b-127">Atribuir o documento a outro usuário para aprovação.</span><span class="sxs-lookup"><span data-stu-id="d760b-127">Assign the document to another user for approval.</span></span>

## <a name="line-item-workflow-elements"></a><span data-ttu-id="d760b-128">Elementos de fluxo de trabalho de item de linha</span><span class="sxs-lookup"><span data-stu-id="d760b-128">Line-item workflow elements</span></span>

<span data-ttu-id="d760b-129">Um fluxo de trabalho pode ser criado para processar documentos ou os itens de linha em um documento.</span><span class="sxs-lookup"><span data-stu-id="d760b-129">A workflow can be created to process either documents or the line items on a document.</span></span> <span data-ttu-id="d760b-130">Por exemplo, você criou um fluxo de trabalho de aprovação para folhas de ponto.</span><span class="sxs-lookup"><span data-stu-id="d760b-130">For example, you've created an approval workflow for timesheets.</span></span> <span data-ttu-id="d760b-131">(Faremos referência a esse fluxo de trabalho como *fluxo de trabalho de documento*.) Você pode adicionar um elemento de *fluxo de trabalho de item de linha* a esse fluxo de trabalho de documento.</span><span class="sxs-lookup"><span data-stu-id="d760b-131">(We will refer to this workflow as the *document workflow*.) You can add a *line-item workflow* element to that document workflow.</span></span> <span data-ttu-id="d760b-132">Quando o elemento de item de linha é executado, cada item de linha do documento é enviado para processamento.</span><span class="sxs-lookup"><span data-stu-id="d760b-132">When the line-item element is run, each line item on the document is submitted for processing.</span></span> <span data-ttu-id="d760b-133">Talvez seja conveniente que todos os itens de linha sejam processados pelo mesmo fluxo de trabalho de item de linha ou que cada item de linha seja processado por um fluxo de trabalho de item de linha diferente.</span><span class="sxs-lookup"><span data-stu-id="d760b-133">You might want all the line items to be processed by the same line-item workflow, or you might want each line item to be processed by a different line-item workflow.</span></span> <span data-ttu-id="d760b-134">Suponha que um funcionário tenha enviado uma folha de ponto que se assemelhe à figura a seguir.</span><span class="sxs-lookup"><span data-stu-id="d760b-134">Imagine that an employee has submitted a timesheet that resembles the following figure.</span></span>

![Fluxo de trabalho com itens de linha](./media/workflow_lineitemworkflow.gif)

<span data-ttu-id="d760b-136">Nesse cenário, talvez seja conveniente criar os seguintes fluxos de trabalho de item de linha:</span><span class="sxs-lookup"><span data-stu-id="d760b-136">In this scenario, you might want to create the following line-item workflows:</span></span>

- <span data-ttu-id="d760b-137">**Fluxo de trabalho de item de linha 1** – Esse fluxo de trabalho é usado para processar itens de linha onde a ID de projeto é 1111.</span><span class="sxs-lookup"><span data-stu-id="d760b-137">**Line-item workflow 1** – This workflow is used to process line items where the project ID is 1111.</span></span>
- <span data-ttu-id="d760b-138">**Fluxo de trabalho de item de linha 2** – Esse fluxo de trabalho é usado para processar itens de linha onde a ID de projeto é 2222.</span><span class="sxs-lookup"><span data-stu-id="d760b-138">**Line-item workflow 2** – This workflow is used to process line items where the project ID is 2222.</span></span>
- <span data-ttu-id="d760b-139">**Fluxo de trabalho de item de linha 3** – esse fluxo de trabalho é usado para processar itens de linha onde a ID de projeto é 3333.</span><span class="sxs-lookup"><span data-stu-id="d760b-139">**Line-item workflow 3** – This workflow is used to process line items where the project ID is 3333.</span></span>

## <a name="flow-control-elements"></a><span data-ttu-id="d760b-140">Elementos de controle de fluxo</span><span class="sxs-lookup"><span data-stu-id="d760b-140">Flow-control elements</span></span>

<span data-ttu-id="d760b-141">Os elementos a seguir permitem projetar os fluxos de trabalho com ramificações alternativas ou ramificações executadas ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="d760b-141">The following elements let you design workflows that have alternate branches or branches that run at the same time.</span></span>

### <a name="manual-decision"></a><span data-ttu-id="d760b-142">Decisão manual</span><span class="sxs-lookup"><span data-stu-id="d760b-142">Manual decision</span></span>

<span data-ttu-id="d760b-143">Uma *decisão manual* é um ponto em que um fluxo de trabalho se divide em duas ramificações.</span><span class="sxs-lookup"><span data-stu-id="d760b-143">A *manual decision* is a point where a workflow divides into two branches.</span></span> <span data-ttu-id="d760b-144">Um usuário deve tomar uma decisão, e essa decisão determina qual ramificação é usada para processar o documento que foi enviado.</span><span class="sxs-lookup"><span data-stu-id="d760b-144">A user must make a decision, and this decision determines which branch is used to process the document that was submitted.</span></span>

### <a name="conditional-decision"></a><span data-ttu-id="d760b-145">Decisão condicional</span><span class="sxs-lookup"><span data-stu-id="d760b-145">Conditional decision</span></span>

<span data-ttu-id="d760b-146">Uma *decisão condicional* também é um ponto em que um fluxo de trabalho se divide em duas ramificações.</span><span class="sxs-lookup"><span data-stu-id="d760b-146">A *conditional decision* is also a point where a workflow divides into two branches.</span></span> <span data-ttu-id="d760b-147">No entanto, o sistema decide qual ramificação é usada para processar o documento que foi enviado.</span><span class="sxs-lookup"><span data-stu-id="d760b-147">However, the system decides which branch is used to process the document that was submitted.</span></span> <span data-ttu-id="d760b-148">Para tomar esta decisão, o sistema avaliará o documento para determinar se ele atende às condições especificadas.</span><span class="sxs-lookup"><span data-stu-id="d760b-148">To make this decision, the system evaluates the document to determine whether it meets specified conditions.</span></span>

### <a name="parallel-activity"></a><span data-ttu-id="d760b-149">Atividade paralela</span><span class="sxs-lookup"><span data-stu-id="d760b-149">Parallel activity</span></span>

<span data-ttu-id="d760b-150">Uma *atividade paralela* é um elemento de fluxo de trabalho que inclui duas ou mais ramificações de fluxo de trabalho executadas ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="d760b-150">A *parallel activity* is a workflow element that includes two or more workflow branches that run at the same time.</span></span>

### <a name="subworkflow"></a><span data-ttu-id="d760b-151">Subfluxo de trabalho</span><span class="sxs-lookup"><span data-stu-id="d760b-151">Subworkflow</span></span>

<span data-ttu-id="d760b-152">Um *subfluxo de trabalho* é um fluxo de trabalho executado no contexto de outro fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="d760b-152">A *subworkflow* is a workflow that runs in the context of another workflow.</span></span>
