---
title: Visão geral de criação de fluxos de trabalho
description: Este tópico explica como criar um fluxo de trabalho.
author: sericks007
manager: AnnBe
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WorkflowSelectTemplateRnr, WorkflowTableListPageRnr
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 195583
ms.assetid: 836ddd01-cc34-45c3-a4b0-20647357dbc6
ms.search.region: Global
ms.author: donaldc
ms.search.validFrom: 2016-08-30
ms.dyn365.ops.version: Platform update 2
ms.openlocfilehash: a643be553f3fcdfbe53f2024982a596e498830a8
ms.sourcegitcommit: 57bc7e17682e2edb5e1766496b7a22f4621819dd
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/18/2019
ms.locfileid: "2811279"
---
# <a name="create-workflows-overview"></a><span data-ttu-id="54865-103">Visão geral de criação de fluxos de trabalho</span><span class="sxs-lookup"><span data-stu-id="54865-103">Create workflows overview</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="54865-104">Este tópico explica como criar um fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="54865-104">This topic explains how to create a workflow.</span></span>

## <a name="open-the-workflow-editor"></a><span data-ttu-id="54865-105">Abrir o editor de fluxo de trabalho</span><span class="sxs-lookup"><span data-stu-id="54865-105">Open the workflow editor</span></span>

<span data-ttu-id="54865-106">O módulo em que você está trabalhando determina os tipos de fluxo de trabalho que você pode criar.</span><span class="sxs-lookup"><span data-stu-id="54865-106">The module that you're working in determines the types of workflow that you can create.</span></span> <span data-ttu-id="54865-107">Siga estas etapas para selecionar o tipo de fluxo de trabalho a ser criado e para abrir o editor de fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="54865-107">Follow these steps to select the type of workflow to create and open the workflow editor.</span></span>

1. <span data-ttu-id="54865-108">Vá para o módulo para o qual deseja criar um novo fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="54865-108">Open the module that you want to create a new workflow for.</span></span> <span data-ttu-id="54865-109">Por exemplo, para criar um fluxo de trabalho para requisições de compra, clique em **Compras e fornecimento**.</span><span class="sxs-lookup"><span data-stu-id="54865-109">For example, to create a workflow for purchase requisitions, click **Procurement and sourcing**.</span></span>
2. <span data-ttu-id="54865-110">Clique em **Configuração** &gt; **\[nome do módulo\] fluxos de trabalho**.</span><span class="sxs-lookup"><span data-stu-id="54865-110">Click **Setup** &gt; **\[Module name\] workflows**.</span></span>
3. <span data-ttu-id="54865-111">Na página de listagem que aparece, no Painel de ação, clique em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="54865-111">On the list page that appears, on the Action Pane, click **New**.</span></span>
4. <span data-ttu-id="54865-112">Na página **Criar fluxo de trabalho**, selecione o tipo de fluxo de trabalho para criar, e então clique em **Criar fluxo de trabalho**.</span><span class="sxs-lookup"><span data-stu-id="54865-112">On the **Create workflow** page, select the type of workflow to create, and then click **Create workflow**.</span></span> <span data-ttu-id="54865-113">O editor de fluxo de trabalho aparece.</span><span class="sxs-lookup"><span data-stu-id="54865-113">The workflow editor appears.</span></span> <span data-ttu-id="54865-114">Agora você pode usar os procedimentos a seguir para criar o fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="54865-114">You can now use the following procedures to design the workflow.</span></span>

## <a name="drag-workflow-elements-onto-the-canvas"></a><span data-ttu-id="54865-115">Arrastar os elementos do fluxo de trabalho para a tela</span><span class="sxs-lookup"><span data-stu-id="54865-115">Drag workflow elements onto the canvas</span></span>

<span data-ttu-id="54865-116">Na área **Elementos de fluxo de trabalho** do editor de fluxo de trabalho contém os elementos que você pode adicionar ao fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="54865-116">The **Workflow elements** area of the workflow editor contains the elements that you can add to your workflow.</span></span> <span data-ttu-id="54865-117">Para adicionar elementos ao fluxo de trabalho, arraste-os da área para a tela.</span><span class="sxs-lookup"><span data-stu-id="54865-117">To add elements to the workflow, drag them onto the canvas.</span></span>

## <a name="connect-the-elements"></a><span data-ttu-id="54865-118">Conectar os elementos</span><span class="sxs-lookup"><span data-stu-id="54865-118">Connect the elements</span></span>

<span data-ttu-id="54865-119">Para conectar um elemento do fluxo de trabalho a outro, mantenha o ponteiro sobre um elemento até que os pontos de conexão apareçam.</span><span class="sxs-lookup"><span data-stu-id="54865-119">To connect one workflow element to another, hold the pointer over an element until connection points appear.</span></span> <span data-ttu-id="54865-120">Clique em um ponto de conexão e arraste-o para outro elemento.</span><span class="sxs-lookup"><span data-stu-id="54865-120">Click a connection point, and drag it to another element.</span></span> <span data-ttu-id="54865-121">Conecte todos os elementos.</span><span class="sxs-lookup"><span data-stu-id="54865-121">Be sure to connect all the elements.</span></span>

## <a name="configure-the-properties-of-the-workflow"></a><span data-ttu-id="54865-122">Configurar as propriedades do fluxo de trabalho</span><span class="sxs-lookup"><span data-stu-id="54865-122">Configure the properties of the workflow</span></span>

<span data-ttu-id="54865-123">Execute as etapas abaixo para configurar as propriedades do fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="54865-123">Follow these steps to configure the properties of the workflow.</span></span>

1. <span data-ttu-id="54865-124">Clique na tela para garantir que nenhum elemento do fluxo de trabalho esteja selecionado.</span><span class="sxs-lookup"><span data-stu-id="54865-124">Click the canvas to make sure that no workflow element is selected.</span></span>
2. <span data-ttu-id="54865-125">Clique em **Propriedades** para abrir a página **Propriedades** para o fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="54865-125">Click **Properties** to open the **Properties** page for the workflow.</span></span>
3. <span data-ttu-id="54865-126">Siga os procedimentos no tópico [Configurar propriedades do fluxo de trabalho](configure-workflow-properties.md).</span><span class="sxs-lookup"><span data-stu-id="54865-126">Follow the procedures in the [Configure workflow properties](configure-workflow-properties.md) topic.</span></span>

## <a name="configure-the-elements-of-the-workflow"></a><span data-ttu-id="54865-127">Configurar os elementos do fluxo de trabalho</span><span class="sxs-lookup"><span data-stu-id="54865-127">Configure the elements of the workflow</span></span>

<span data-ttu-id="54865-128">Configure cada elemento que você arrastou para a tela.</span><span class="sxs-lookup"><span data-stu-id="54865-128">Configure each element that you dragged onto the canvas.</span></span> <span data-ttu-id="54865-129">Para obter informações sobre como configurar cada elemento do fluxo de trabalho, consulte os seguintes tópicos.</span><span class="sxs-lookup"><span data-stu-id="54865-129">For information about how to configure each workflow element, see the following topics:</span></span>

- [<span data-ttu-id="54865-130">Configurar tarefas manuais em um fluxo de trabalho</span><span class="sxs-lookup"><span data-stu-id="54865-130">Configure manual tasks in a workflow</span></span>](configure-manual-task-workflow.md)
- [<span data-ttu-id="54865-131">Configurar tarefas automatizadas em um fluxo de trabalho</span><span class="sxs-lookup"><span data-stu-id="54865-131">Configure automated tasks in a workflow</span></span>](configure-automated-task-workflow.md)
- [<span data-ttu-id="54865-132">Configurar processos de aprovação em um fluxo de trabalho</span><span class="sxs-lookup"><span data-stu-id="54865-132">Configure approval processes in a workflow</span></span>](configure-approval-process-workflow.md)
- [<span data-ttu-id="54865-133">Configurar etapas de aprovação em um fluxo de trabalho</span><span class="sxs-lookup"><span data-stu-id="54865-133">Configure approval steps in a workflow</span></span>](configure-approval-step-workflow.md)
- [<span data-ttu-id="54865-134">Configurar decisões manuais em um fluxo de trabalho</span><span class="sxs-lookup"><span data-stu-id="54865-134">Configure manual decisions in a workflow</span></span>](configure-manual-decision-workflow.md)
- [<span data-ttu-id="54865-135">Configurar decisões condicionais em um fluxo de trabalho</span><span class="sxs-lookup"><span data-stu-id="54865-135">Configure conditional decisions in a workflow</span></span>](configure-conditional-decision-workflow.md)
- [<span data-ttu-id="54865-136">Configurar ramificações paralelas em um fluxo de trabalho</span><span class="sxs-lookup"><span data-stu-id="54865-136">Configure parallel branches in a workflow</span></span>](configure-parallel-activity-workflow.md)
- [<span data-ttu-id="54865-137">Configurar uma ramificação paralela</span><span class="sxs-lookup"><span data-stu-id="54865-137">Configure a parallel branch</span></span>](configure-parallel-branch-workflow.md)
- [<span data-ttu-id="54865-138">Configurar fluxos de trabalho de item de linha</span><span class="sxs-lookup"><span data-stu-id="54865-138">Configure line-item workflows</span></span>](configure-line-item-workflow.md)

## <a name="resolve-any-errors-or-warnings"></a><span data-ttu-id="54865-139">Resolver todos os erros ou avisos</span><span class="sxs-lookup"><span data-stu-id="54865-139">Resolve any errors or warnings</span></span>

<span data-ttu-id="54865-140">O painel **Erros e avisos**, localizado na parte inferior do editor de fluxo de trabalho, exibe as mensagens geradas para o fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="54865-140">The **Errors and warnings** pane at the bottom of the workflow editor shows messages that have been generated for the workflow.</span></span> <span data-ttu-id="54865-141">Para localizar o elemento que gerou um erro ou aviso, clique duas vezes no erro ou na mensagem de aviso.</span><span class="sxs-lookup"><span data-stu-id="54865-141">To find the element where an error or warning occurred, double-click the error or warning message.</span></span> <span data-ttu-id="54865-142">Todos os erros e avisos devem ser resolvidos para que você possa ativar o fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="54865-142">You must resolve all errors and warnings before you can make the workflow active.</span></span>

## <a name="save-and-activate-the-workflow"></a><span data-ttu-id="54865-143">Salvar e ativar o fluxo de trabalho</span><span class="sxs-lookup"><span data-stu-id="54865-143">Save and activate the workflow</span></span>

<span data-ttu-id="54865-144">Quando estiver pronto para salvar e ativar o fluxo de trabalho, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="54865-144">When you're ready to save and activate the workflow, follow these steps.</span></span>

1. <span data-ttu-id="54865-145">Clique em **Salvar e fechar** para fechar o editor de fluxo de trabalho e abrir a página **Salvar fluxo de trabalho**.</span><span class="sxs-lookup"><span data-stu-id="54865-145">Click **Save and close** to close the workflow editor and open the **Save workflow** page.</span></span>
2. <span data-ttu-id="54865-146">Digite comentários sobre as alterações feitas no fluxo de trabalho e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="54865-146">Enter comments about the changes that you've made to the workflow, and then click **OK**.</span></span>
3. <span data-ttu-id="54865-147">Se todos os erros e avisos foram resolvidos, a página **Ativar fluxo de trabalho** será exibido.</span><span class="sxs-lookup"><span data-stu-id="54865-147">If all errors and warnings have been resolved, the **Activate workflow** page appears.</span></span> <span data-ttu-id="54865-148">Selecione uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="54865-148">Select one of the following options:</span></span>

    - <span data-ttu-id="54865-149">Para ativar a versão de fluxo de trabalho, clique em **Ativar a nova versão**.</span><span class="sxs-lookup"><span data-stu-id="54865-149">To activate this version of the workflow, click **Activate the new version**.</span></span> <span data-ttu-id="54865-150">Quando um fluxo de trabalho estiver ativo, os usuários poderão enviar documentos a ele para processamento.</span><span class="sxs-lookup"><span data-stu-id="54865-150">When a workflow is active, users can submit documents to it for processing.</span></span>
    - <span data-ttu-id="54865-151">Se não quiser ativar a versão, clique em **Não ativar a nova versão**.</span><span class="sxs-lookup"><span data-stu-id="54865-151">If you don't want to activate this version, click **Do not activate the new version**.</span></span> <span data-ttu-id="54865-152">É possível ativar o fluxo de trabalho posteriormente.</span><span class="sxs-lookup"><span data-stu-id="54865-152">You can activate the workflow later.</span></span>
