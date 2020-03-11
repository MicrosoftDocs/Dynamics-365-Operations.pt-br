---
title: Criar listas de tarefas e adicionar tarefas
description: Este tópico descreve como criar listas de tarefas e adicionar tarefas a elas no Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
manager: annbe
ms.date: 02/10/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.search.region: Global
ms.search.industry: ''
ms.author: gmohanv
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Release 10.0.9
ms.openlocfilehash: 1cab31784db9f3242dce20e98762088436a5a8f8
ms.sourcegitcommit: 80cbb7d22267aa6a0ae0568d0063fb95556958a5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/11/2020
ms.locfileid: "3036823"
---
# <a name="create-task-lists-and-add-tasks"></a><span data-ttu-id="48750-103">Criar listas de tarefas e adicionar tarefas</span><span class="sxs-lookup"><span data-stu-id="48750-103">Create task lists and add tasks</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="48750-104">Este tópico descreve como criar listas de tarefas e adicionar tarefas a elas no Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="48750-104">This topic describes how to create task lists and add tasks to them in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="48750-105">Visão geral</span><span class="sxs-lookup"><span data-stu-id="48750-105">Overview</span></span>

<span data-ttu-id="48750-106">Uma *tarefa* define uma parte específica do trabalho ou uma ação que alguém deve concluir em ou antes de uma data de vencimento especificada.</span><span class="sxs-lookup"><span data-stu-id="48750-106">A *task* defines a specific piece of work or an action that someone must complete on or before a specified due date.</span></span> <span data-ttu-id="48750-107">No Dynamics 365 Commerce, uma tarefa pode incluir instruções e informações detalhadas sobre uma pessoa para contato.</span><span class="sxs-lookup"><span data-stu-id="48750-107">In Dynamics 365 Commerce, a task can include detailed instructions and information about a contact person.</span></span> <span data-ttu-id="48750-108">Ele também pode incluir links para operações de Back-Office, operações de ponto de venda (PDV) ou páginas do site para ajudar a melhorar a produtividade e fornecer o contexto que o proprietário da tarefa requer para concluir a tarefa com eficiência.</span><span class="sxs-lookup"><span data-stu-id="48750-108">It can also include links to back-office operations, point of sale (POS) operations, or site pages, to help improve productivity and provide the context that the task owner requires to complete the task efficiently.</span></span>

<span data-ttu-id="48750-109">Uma *lista de tarefas* é um conjunto de tarefas que devem ser concluídas como parte de um processo comercial.</span><span class="sxs-lookup"><span data-stu-id="48750-109">A *task list* is a collection of tasks that must be completed as part of a business process.</span></span> <span data-ttu-id="48750-110">Por exemplo, pode haver uma lista de tarefas que um novo trabalhador deve preencher durante a integração, uma lista de tarefas para caixas que trabalham com turnos à noite ou uma lista de tarefas que deve ser preenchida para preparar o armazenamento para um período de final de ano futuro.</span><span class="sxs-lookup"><span data-stu-id="48750-110">For example, there might be a task list that a new worker must complete during onboarding, a task list for cashiers who work evening shifts, or a task list that must be completed to prepare the store for an upcoming holiday season.</span></span> <span data-ttu-id="48750-111">Em Commerce, todas as listas de tarefas que têm uma data de destino podem ser atribuídas a qualquer quantidade de lojas ou funcionários e podem ser configuradas como recorrentes.</span><span class="sxs-lookup"><span data-stu-id="48750-111">In Commerce, every task list that has a target date can be assigned to any number of stores or employees, and it can be configured to recur.</span></span>

<span data-ttu-id="48750-112">Os gerentes e trabalhadores podem criar listas de tarefas no back-office do Commerce e, depois, atribuí-las a um conjunto de lojas.</span><span class="sxs-lookup"><span data-stu-id="48750-112">Both managers and workers can create task lists in Commerce back office, and then assign them to a set of stores.</span></span>

## <a name="create-a-task-list"></a><span data-ttu-id="48750-113">Criar uma lista de tarefas</span><span class="sxs-lookup"><span data-stu-id="48750-113">Create a task list</span></span>

<span data-ttu-id="48750-114">Para criar uma lista de tarefas, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="48750-114">To create a task list, follow these steps.</span></span>

1. <span data-ttu-id="48750-115">Vá para **Retail e Commerce \> Gerenciamento de tarefas \> Administração de gerenciamento de tarefas**.</span><span class="sxs-lookup"><span data-stu-id="48750-115">Go to **Retail and Commerce \> Task management \> Task management administration**.</span></span>
1. <span data-ttu-id="48750-116">Selecione **Novo**, e depois insira os valores nos campos **Nome**, **Descrição** e **Proprietário**.</span><span class="sxs-lookup"><span data-stu-id="48750-116">Select **New**, and then enter values in the **Name**, **Description**, and **Owner** fields.</span></span>
1. <span data-ttu-id="48750-117">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="48750-117">Select **Save**.</span></span>

## <a name="add-tasks-to-a-task-list"></a><span data-ttu-id="48750-118">Adicionar tarefas a uma lista de tarefas</span><span class="sxs-lookup"><span data-stu-id="48750-118">Add tasks to a task list</span></span>

<span data-ttu-id="48750-119">Para adicionar tarefas a uma lista de tarefas, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="48750-119">To add tasks to a task list, follow these steps.</span></span>
 
1. <span data-ttu-id="48750-120">Na Guia Rápida **Tarefas** de uma lista de tarefas existente, selecione **Novo** para adicionar uma tarefa.</span><span class="sxs-lookup"><span data-stu-id="48750-120">On the **Tasks** FastTab of an existing task list, select **New** to add a task.</span></span>
1. <span data-ttu-id="48750-121">Na caixa de diálogo **Criar uma nova tarefa**, no campo **Nome**, insira um nome para a tarefa.</span><span class="sxs-lookup"><span data-stu-id="48750-121">In the **Create a new task** dialog box, in the **Name** field, enter a name for the task.</span></span>
1. <span data-ttu-id="48750-122">No campo **Deslocamento da data de vencimento a partir da data de destino**, insira um valor inteiro positivo ou negativo.</span><span class="sxs-lookup"><span data-stu-id="48750-122">In the **Due data offset from target date** field, enter a positive or negative integer value.</span></span> <span data-ttu-id="48750-123">Por exemplo, insira **-2** se a tarefa deve ser concluída dois dias antes da data de vencimento da lista de tarefas.</span><span class="sxs-lookup"><span data-stu-id="48750-123">For example, enter **-2** if the task should be completed two days before the task list's due date.</span></span>
1. <span data-ttu-id="48750-124">No campo **Notas**, insira instruções detalhadas.</span><span class="sxs-lookup"><span data-stu-id="48750-124">In the **Notes** field, enter detailed instructions.</span></span>
1. <span data-ttu-id="48750-125">No campo **Pessoa para contato**, insira o nome de um especialista no assunto que o proprietário da tarefa pode contatar se precisar de ajuda.</span><span class="sxs-lookup"><span data-stu-id="48750-125">In the **Contact person** field, enter the name of a subject matter expert that the task owner can contact if he or she needs help.</span></span>
1. <span data-ttu-id="48750-126">No campo **Link de contato**, insira um link, com base na natureza da tarefa.</span><span class="sxs-lookup"><span data-stu-id="48750-126">In the **Task link** field, enter a link, based on the nature of the task.</span></span>

> [!TIP]
> <span data-ttu-id="48750-127">Embora você possa usar o campo **Atribuído a** para atribuir tarefas a alguém enquanto está criando uma lista de tarefas, recomendamos que você evite atribuir tarefas durante a criação da lista de tarefas.</span><span class="sxs-lookup"><span data-stu-id="48750-127">Although you can use the **Assigned to** field to assign tasks to someone while you're creating a task list, we recommend that you avoid assigning tasks during task list creation.</span></span> <span data-ttu-id="48750-128">Em vez disso, atribua as tarefas depois que a lista for instanciada para armazenamentos individuais.</span><span class="sxs-lookup"><span data-stu-id="48750-128">Instead, assign the tasks after the list is instantiated for individual stores.</span></span>

## <a name="use-task-links-to-help-improve-worker-productivity"></a><span data-ttu-id="48750-129">Use links de tarefas para ajudar a melhorar a produtividade do trabalhador</span><span class="sxs-lookup"><span data-stu-id="48750-129">Use task links to help improve worker productivity</span></span>

<span data-ttu-id="48750-130">Commerce permite vincular tarefas a operações específicas do PDV, como a execução de um relatório de vendas, a exibição de um vídeo de treinamento online para a orientação de novos funcionários ou a execução de uma operação de back-office.</span><span class="sxs-lookup"><span data-stu-id="48750-130">Commerce lets you link tasks to specific POS operations, such as running a sales report, viewing an online training video for new employee orientation, or performing a back-office operation.</span></span> <span data-ttu-id="48750-131">Esse recurso ajuda os proprietários da tarefa a obter as informações necessárias para concluir uma tarefa com eficiência.</span><span class="sxs-lookup"><span data-stu-id="48750-131">This feature helps task owners get the information that they need to complete a task efficiently.</span></span>

<span data-ttu-id="48750-132">Para adicionar links de tarefas ao criar uma tarefa, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="48750-132">To add task links while you create a task, follow these steps.</span></span>

1. <span data-ttu-id="48750-133">Na Guia Rápida **Tarefas** de uma lista de tarefas existente, selecione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="48750-133">On the **Tasks** FastTab of an existing task list, select **Edit**.</span></span>
1. <span data-ttu-id="48750-134">Na caixa de diálogo **Editar tarefas**, no campo **Link das tarefas**, selecione uma ou mais das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="48750-134">In the **Edit task** dialog box, in the **Task link** field, select one or more of the following options:</span></span>

    - <span data-ttu-id="48750-135">Selecione o **Item do menu** para configurar uma operação de back-office, como "Kits de produtos".</span><span class="sxs-lookup"><span data-stu-id="48750-135">Select **Menu item** to configure a back-office operation, such as "Product kits."</span></span>
    - <span data-ttu-id="48750-136">Selecione a **Operação de PDV** para configurar uma operação de PDV, como "Relatórios de vendas".</span><span class="sxs-lookup"><span data-stu-id="48750-136">Select **POS Operation** to configure a POS operation, such as "Sales reports."</span></span>
    - <span data-ttu-id="48750-137">Selecione a **URL** para configurar uma URL absoluta.</span><span class="sxs-lookup"><span data-stu-id="48750-137">Select **URL** to configure an absolute URL.</span></span>

<span data-ttu-id="48750-138">A ilustração a seguir mostra a seleção de links de tarefas na caixa de diálogo **Editar tarefa**.</span><span class="sxs-lookup"><span data-stu-id="48750-138">The following illustration shows the selection of task links in the **Edit task** dialog box.</span></span>

![Selecionando links de tarefas na caixa de diálogo Editar tarefa](media/HQ-POS-Tasks-Linking.png)

### <a name="configure-a-pos-operation-so-that-it-can-be-linked-to-a-task"></a><span data-ttu-id="48750-140">Configurar uma operação de PDV para que possa ser vinculada a uma tarefa</span><span class="sxs-lookup"><span data-stu-id="48750-140">Configure a POS operation so that it can be linked to a task</span></span>

<span data-ttu-id="48750-141">Para configurar uma operação de PDV para que possa ser vinculada a uma tarefa, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="48750-141">To configure a POS operation so that it can be linked to a task, follow these steps.</span></span>

1. <span data-ttu-id="48750-142">Vá para **Retail e Commerce \> Configuração de canal \> Configuração do PDV \> PDV \> Operações de PDV**.</span><span class="sxs-lookup"><span data-stu-id="48750-142">Go to **Retail and Commerce \> Channel setup \> POS setup \> POS \> POS operations**.</span></span>
1. <span data-ttu-id="48750-143">Selecione **Editar**, localize a operação de PDV e marque a caixa de seleção **Habilitar gerenciamento de tarefas** para ela.</span><span class="sxs-lookup"><span data-stu-id="48750-143">Select **Edit**, find the POS operation, and then select the **Enable Task Management** check box for it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="48750-144">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="48750-144">Additional resources</span></span>

[<span data-ttu-id="48750-145">Visão geral do gerenciamento de tarefas</span><span class="sxs-lookup"><span data-stu-id="48750-145">Task management overview</span></span>](task-mgmt-overview.md)

[<span data-ttu-id="48750-146">Configurar gerenciamento de tarefas</span><span class="sxs-lookup"><span data-stu-id="48750-146">Configure task management</span></span>](task-mgmt-configure.md)

[<span data-ttu-id="48750-147">Atribuir listas de tarefas a lojas ou funcionários</span><span class="sxs-lookup"><span data-stu-id="48750-147">Assign task lists to stores or employees</span></span>](task-mgmt-assign-lists.md)

[<span data-ttu-id="48750-148">Gerenciamento de tarefas em PDV</span><span class="sxs-lookup"><span data-stu-id="48750-148">Task management in POS</span></span>](task-mgmt-POS.md)
