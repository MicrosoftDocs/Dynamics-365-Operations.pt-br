---
title: Usar fluxos de trabalho para gerenciar informações de funcionários
description: Este artigo explica como você pode usar o recurso de fluxo de trabalho para recursos humanos para gerenciar informações de funcionários. Por exemplo, você pode associar um fluxo de trabalho a uma posição e configurar um fluxo de trabalho de aprovação que é iniciado quando os funcionários alteram seu registro.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations, Human Resources
ms.custom: 269074
ms.assetid: 426c6127-42ee-4163-8dd0-b2867f95581d
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 539f4c77244d2e5590e3994dedc0725e5a80093b
ms.sourcegitcommit: ba340f836e472f13f263dec46a49847c788fca44
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/04/2020
ms.locfileid: "3429165"
---
# <a name="use-workflows-to-manage-employee-information"></a><span data-ttu-id="9bc6b-104">Usar fluxos de trabalho para gerenciar informações de funcionários</span><span class="sxs-lookup"><span data-stu-id="9bc6b-104">Use workflows to manage employee information</span></span>

<span data-ttu-id="9bc6b-105">Este artigo explica como você pode usar o recurso de fluxo de trabalho para recursos humanos para gerenciar informações de funcionários.</span><span class="sxs-lookup"><span data-stu-id="9bc6b-105">This article explains how you can use the workflow capability for Human resources to manage employee information.</span></span> <span data-ttu-id="9bc6b-106">Por exemplo, você pode associar um fluxo de trabalho a uma posição e configurar um fluxo de trabalho de aprovação que é iniciado quando os funcionários alteram seu registro.</span><span class="sxs-lookup"><span data-stu-id="9bc6b-106">For example, you can associate a workflow with a position and configure an approval workflow that is started when employees change their record.</span></span>

<span data-ttu-id="9bc6b-107">A capacidade de fluxo de trabalho para Recursos Humanos fornece vários fluxos de trabalho para gerenciar atividades de recursos humanos.</span><span class="sxs-lookup"><span data-stu-id="9bc6b-107">The workflow capability for Human resources provides numerous workflows for managing human resources activities.</span></span> <span data-ttu-id="9bc6b-108">Além disso, várias opções estão disponíveis para que você possa modificar fluxos de trabalho específicos e associá-los a uma hierarquia de relatórios.</span><span class="sxs-lookup"><span data-stu-id="9bc6b-108">Additionally, numerous options are available so that you can modify specific workflows and associate them with a reporting hierarchy.</span></span> <span data-ttu-id="9bc6b-109">Fluxos de trabalho estão disponíveis para ajudar a gerenciar alterações a vários tipos padrão de informações de funcionários.</span><span class="sxs-lookup"><span data-stu-id="9bc6b-109">Workflows are available to help manage changes to several standard types of employee information.</span></span> <span data-ttu-id="9bc6b-110">Você pode associar um fluxo de trabalho a uma posição.</span><span class="sxs-lookup"><span data-stu-id="9bc6b-110">You can associate a workflow with a position.</span></span> <span data-ttu-id="9bc6b-111">Em seguida, se os funcionários alterarem o registro do funcionário, será iniciado um fluxo de trabalho que requer aprovação antes que as novas informações sejam salvas.</span><span class="sxs-lookup"><span data-stu-id="9bc6b-111">Then, if employees change their employee record, a workflow is started that requires approval before the new information is saved.</span></span> <span data-ttu-id="9bc6b-112">Os fluxos de trabalho são predefinidos para os seguintes tipos de informações para ajudá-lo a gerenciar com eficiência as alterações e manter os dados dos funcionários precisos:</span><span class="sxs-lookup"><span data-stu-id="9bc6b-112">Workflows are predefined for the following types of information to help you efficiently manage changes and keep your employees’ data accurate:</span></span>

-   <span data-ttu-id="9bc6b-113">Números de identificação</span><span class="sxs-lookup"><span data-stu-id="9bc6b-113">Identification numbers</span></span>
-   <span data-ttu-id="9bc6b-114">Cursos</span><span class="sxs-lookup"><span data-stu-id="9bc6b-114">Courses</span></span>
-   <span data-ttu-id="9bc6b-115">Formação educacional</span><span class="sxs-lookup"><span data-stu-id="9bc6b-115">Education</span></span>
-   <span data-ttu-id="9bc6b-116">Imagem</span><span class="sxs-lookup"><span data-stu-id="9bc6b-116">Image</span></span>
-   <span data-ttu-id="9bc6b-117">Itens emprestados</span><span class="sxs-lookup"><span data-stu-id="9bc6b-117">Loaned items</span></span>
-   <span data-ttu-id="9bc6b-118">Experiência profissional</span><span class="sxs-lookup"><span data-stu-id="9bc6b-118">Professional experience</span></span>
-   <span data-ttu-id="9bc6b-119">Experiência em projetos</span><span class="sxs-lookup"><span data-stu-id="9bc6b-119">Project experience</span></span>
-   <span data-ttu-id="9bc6b-120">Habilidades</span><span class="sxs-lookup"><span data-stu-id="9bc6b-120">Skills</span></span>
-   <span data-ttu-id="9bc6b-121">Posições de confiança</span><span class="sxs-lookup"><span data-stu-id="9bc6b-121">Positions of trust</span></span>
-   <span data-ttu-id="9bc6b-122">Ações de recursos humanos</span><span class="sxs-lookup"><span data-stu-id="9bc6b-122">Human resources actions</span></span>
-   <span data-ttu-id="9bc6b-123">Registro do curso</span><span class="sxs-lookup"><span data-stu-id="9bc6b-123">Course registration</span></span>

<span data-ttu-id="9bc6b-124">Quando os funcionários são contratados, transferidos ou encerrados, o fluxo de trabalho pode incluir um processo de revisão.</span><span class="sxs-lookup"><span data-stu-id="9bc6b-124">When employees are hired, transferred, or terminated, the workflow can include a review process.</span></span> <span data-ttu-id="9bc6b-125">Desta forma, um documento pode ser revisto ou os termos de uma ação podem ser definidos como parte do fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="9bc6b-125">In this way, a document can be revised or the terms of an action can be defined as part of the workflow.</span></span> <span data-ttu-id="9bc6b-126">Quando o processo de revisão é concluído, o documento ou ação é concluído e o fluxo de trabalho passa para uma etapa de aprovação final.</span><span class="sxs-lookup"><span data-stu-id="9bc6b-126">When the review process is completed, the document or action is completed, and the workflow moves to a final approval step.</span></span>

## <a name="associate-a-workflow-with-a-position-hierarchy"></a><span data-ttu-id="9bc6b-127">Associar um fluxo de trabalho a uma hierarquia de posições</span><span class="sxs-lookup"><span data-stu-id="9bc6b-127">Associate a workflow with a position hierarchy</span></span>
<span data-ttu-id="9bc6b-128">Você pode associar um fluxo de trabalho com qualquer hierarquia que você configurar.</span><span class="sxs-lookup"><span data-stu-id="9bc6b-128">You can associate a workflow with any hierarchy that you configure.</span></span> <span data-ttu-id="9bc6b-129">Por exemplo, se uma posição estiver associada a uma hierarquia de relatórios de matriz, você pode configurar um fluxo de trabalho que encaminha despesas para um projeto específico, para a liderança do projeto em vez do gerente do funcionário que está associado a essa posição.</span><span class="sxs-lookup"><span data-stu-id="9bc6b-129">For example, if a position is associated with a matrix reporting hierarchy, you might configure a workflow that routes expenses for a specific project to the project lead instead of the manager of the employee who is associated with that position.</span></span> <span data-ttu-id="9bc6b-130">Para criar um novo fluxo de trabalho ou modificar um fluxo de trabalho, na página **Fluxo de trabalho de recursos humanos**, clique em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="9bc6b-130">To create a new workflow or modify an existing workflow, on the **Human resources workflow** page, click **New**.</span></span> <span data-ttu-id="9bc6b-131">Selecione um fluxo de trabalho na lista para iniciar o designer de fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="9bc6b-131">Select a workflow in the list to start the Workflow designer.</span></span> <span data-ttu-id="9bc6b-132">Você pode usar o designer para criar um novo fluxo de trabalho ou alterar as etapas em um fluxo de trabalho existente.</span><span class="sxs-lookup"><span data-stu-id="9bc6b-132">You can use the designer to create a new workflow or change the steps in an existing workflow.</span></span> <span data-ttu-id="9bc6b-133">Quando você altera um fluxo de trabalho existente, suas alterações são salvas como uma nova versão.</span><span class="sxs-lookup"><span data-stu-id="9bc6b-133">When you change an existing workflow, your changes are saved as a new version.</span></span> <span data-ttu-id="9bc6b-134">Portanto, você pode sempre voltar a uma versão anterior, se for necessário.</span><span class="sxs-lookup"><span data-stu-id="9bc6b-134">Therefore, you can always go back to a previous version if you have to.</span></span>

## <a name="configure-a-human-resources-workflow"></a><span data-ttu-id="9bc6b-135">Configurar um fluxo de trabalho de recursos humanos</span><span class="sxs-lookup"><span data-stu-id="9bc6b-135">Configure a Human resources workflow</span></span>
<span data-ttu-id="9bc6b-136">Para configurar um fluxo de trabalho básico que é iniciado quando os funcionários solicitam alterações à sua identificação pessoal, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="9bc6b-136">To configure a basic workflow that is started when employees request changes to their personal identification, follow these steps.</span></span>

1.  <span data-ttu-id="9bc6b-137">Na página **Fluxos de trabalho de recursos humanos**, clique em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="9bc6b-137">On the **Human resources workflows** page, click **New**.</span></span>
2.  <span data-ttu-id="9bc6b-138">Na lista de fluxos de trabalho disponíveis, selecione **Números de identificação**.</span><span class="sxs-lookup"><span data-stu-id="9bc6b-138">In the list of available workflows, select **Identification numbers**.</span></span>
3.  <span data-ttu-id="9bc6b-139">Clique em **Executar** para o designer de fluxo de trabalho, e insira o nome de usuário e senha quando for solicitado.</span><span class="sxs-lookup"><span data-stu-id="9bc6b-139">Click **Run** to start the Workflow designer, and then enter your user name and password when you're prompted.</span></span>
4.  <span data-ttu-id="9bc6b-140">Arraste o elemento **Aprovar número de identificação** da lista de elementos de fluxo de trabalho para a tela do designer.</span><span class="sxs-lookup"><span data-stu-id="9bc6b-140">Drag the **Approve identification number** element from the list of workflow elements to the designer canvas.</span></span>
5.  <span data-ttu-id="9bc6b-141">Conecte o elemento de aprovação com **Início** e **Término**.</span><span class="sxs-lookup"><span data-stu-id="9bc6b-141">Connect the approval element to **Start** and **Finish**.</span></span>
6.  <span data-ttu-id="9bc6b-142">Clique duas vezes em **Aprovar elemento** e, em seguida, clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="9bc6b-142">Double-click **Approve element**, and then right-click, and select **Properties**.</span></span>
7.  <span data-ttu-id="9bc6b-143">Siga essas etapas para adicionar instruções de item de trabalho:</span><span class="sxs-lookup"><span data-stu-id="9bc6b-143">Follow these steps to add work item instructions:</span></span>
    1.  <span data-ttu-id="9bc6b-144">Selecione **Atribuição** e, em seguida, selecione **Hierarquia** no tipo de atribuição.</span><span class="sxs-lookup"><span data-stu-id="9bc6b-144">Select **Assignment**, and then select **Hierarchy** under the assignment type.</span></span>
    2.  <span data-ttu-id="9bc6b-145">Na seleção de **Hierarquia**, selecione **Hierarquia configurável**.</span><span class="sxs-lookup"><span data-stu-id="9bc6b-145">Under the **Hierarchy** selection, select **Configurable hierarchy**.</span></span>
    3.  <span data-ttu-id="9bc6b-146">Adicione uma condição de parada, e feche a página.</span><span class="sxs-lookup"><span data-stu-id="9bc6b-146">Add a stop condition, and close the page.</span></span>

8.  <span data-ttu-id="9bc6b-147">Complete todas as instruções adicionais (não devem existir avisos adicionais).</span><span class="sxs-lookup"><span data-stu-id="9bc6b-147">Complete any additional instructions (no additional warnings should exist).</span></span>
9.  <span data-ttu-id="9bc6b-148">Clique em **Salvar e fechar**.</span><span class="sxs-lookup"><span data-stu-id="9bc6b-148">Click **Save and close**.</span></span> <span data-ttu-id="9bc6b-149">Ative o novo fluxo de trabalho quando a caixa de diálogo abrir e selecione **Ativar**.</span><span class="sxs-lookup"><span data-stu-id="9bc6b-149">Activate the new workflow when the dialog box opens, and select **Make active**.</span></span>
10. <span data-ttu-id="9bc6b-150">Vá para **Recursos humanos** &gt; **Posições** &gt; **Tipos de hierarquia de posição**.</span><span class="sxs-lookup"><span data-stu-id="9bc6b-150">Go to **Human Resources** &gt; **Positions** &gt; **Position hierarchy types**.</span></span>
11. <span data-ttu-id="9bc6b-151">Selecione **Matriz**.</span><span class="sxs-lookup"><span data-stu-id="9bc6b-151">Select **Matrix**.</span></span>
12. <span data-ttu-id="9bc6b-152">Adicione o fluxo de trabalho **Número de identificação do trabalhador** à lista.</span><span class="sxs-lookup"><span data-stu-id="9bc6b-152">Add the **Worker identification number** workflow to the list.</span></span>




