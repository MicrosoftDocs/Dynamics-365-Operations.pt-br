---
title: Criar listas de tarefas e adicionar tarefas
description: Este tópico descreve como criar listas de tarefas e adicionar tarefas a elas no Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
ms.date: 02/10/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: ''
ms.author: gmohanv
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Release 10.0.9
ms.openlocfilehash: a0e49d1eced3bb62e78c630b137a5b86121682f3
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5795228"
---
# <a name="create-task-lists-and-add-tasks"></a><span data-ttu-id="7ec62-103">Criar listas de tarefas e adicionar tarefas</span><span class="sxs-lookup"><span data-stu-id="7ec62-103">Create task lists and add tasks</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="7ec62-104">Este tópico descreve como criar listas de tarefas e adicionar tarefas a elas no Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="7ec62-104">This topic describes how to create task lists and add tasks to them in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="7ec62-105">Uma *tarefa* define uma parte específica do trabalho ou uma ação que alguém deve concluir em ou antes de uma data de vencimento especificada.</span><span class="sxs-lookup"><span data-stu-id="7ec62-105">A *task* defines a specific piece of work or an action that someone must complete on or before a specified due date.</span></span> <span data-ttu-id="7ec62-106">No Dynamics 365 Commerce, uma tarefa pode incluir instruções e informações detalhadas sobre uma pessoa para contato.</span><span class="sxs-lookup"><span data-stu-id="7ec62-106">In Dynamics 365 Commerce, a task can include detailed instructions and information about a contact person.</span></span> <span data-ttu-id="7ec62-107">Ele também pode incluir links para operações de Back-Office, operações de ponto de venda (PDV) ou páginas do site para ajudar a melhorar a produtividade e fornecer o contexto que o proprietário da tarefa requer para concluir a tarefa com eficiência.</span><span class="sxs-lookup"><span data-stu-id="7ec62-107">It can also include links to back-office operations, point of sale (POS) operations, or site pages, to help improve productivity and provide the context that the task owner requires to complete the task efficiently.</span></span>

<span data-ttu-id="7ec62-108">Uma *lista de tarefas* é um conjunto de tarefas que devem ser concluídas como parte de um processo comercial.</span><span class="sxs-lookup"><span data-stu-id="7ec62-108">A *task list* is a collection of tasks that must be completed as part of a business process.</span></span> <span data-ttu-id="7ec62-109">Por exemplo, pode haver uma lista de tarefas que um novo trabalhador deve preencher durante a integração, uma lista de tarefas para caixas que trabalham com turnos à noite ou uma lista de tarefas que deve ser preenchida para preparar o armazenamento para um período de final de ano futuro.</span><span class="sxs-lookup"><span data-stu-id="7ec62-109">For example, there might be a task list that a new worker must complete during onboarding, a task list for cashiers who work evening shifts, or a task list that must be completed to prepare the store for an upcoming holiday season.</span></span> <span data-ttu-id="7ec62-110">Em Commerce, todas as listas de tarefas que têm uma data de destino podem ser atribuídas a qualquer quantidade de lojas ou funcionários e podem ser configuradas como recorrentes.</span><span class="sxs-lookup"><span data-stu-id="7ec62-110">In Commerce, every task list that has a target date can be assigned to any number of stores or employees, and it can be configured to recur.</span></span>

<span data-ttu-id="7ec62-111">Os gerentes e trabalhadores podem criar listas de tarefas no back-office do Commerce e, depois, atribuí-las a um conjunto de lojas.</span><span class="sxs-lookup"><span data-stu-id="7ec62-111">Both managers and workers can create task lists in Commerce back office, and then assign them to a set of stores.</span></span>

## <a name="create-a-task-list"></a><span data-ttu-id="7ec62-112">Criar uma lista de tarefas</span><span class="sxs-lookup"><span data-stu-id="7ec62-112">Create a task list</span></span>

<span data-ttu-id="7ec62-113">Para criar uma lista de tarefas, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="7ec62-113">To create a task list, follow these steps.</span></span>

1. <span data-ttu-id="7ec62-114">Vá para **Retail e Commerce \> Gerenciamento de tarefas \> Administração de gerenciamento de tarefas**.</span><span class="sxs-lookup"><span data-stu-id="7ec62-114">Go to **Retail and Commerce \> Task management \> Task management administration**.</span></span>
1. <span data-ttu-id="7ec62-115">Selecione **Novo**, e depois insira os valores nos campos **Nome**, **Descrição** e **Proprietário**.</span><span class="sxs-lookup"><span data-stu-id="7ec62-115">Select **New**, and then enter values in the **Name**, **Description**, and **Owner** fields.</span></span>
1. <span data-ttu-id="7ec62-116">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="7ec62-116">Select **Save**.</span></span>

## <a name="add-tasks-to-a-task-list"></a><span data-ttu-id="7ec62-117">Adicionar tarefas a uma lista de tarefas</span><span class="sxs-lookup"><span data-stu-id="7ec62-117">Add tasks to a task list</span></span>

<span data-ttu-id="7ec62-118">Para adicionar tarefas a uma lista de tarefas, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="7ec62-118">To add tasks to a task list, follow these steps.</span></span>
 
1. <span data-ttu-id="7ec62-119">Na Guia Rápida **Tarefas** de uma lista de tarefas existente, selecione **Novo** para adicionar uma tarefa.</span><span class="sxs-lookup"><span data-stu-id="7ec62-119">On the **Tasks** FastTab of an existing task list, select **New** to add a task.</span></span>
1. <span data-ttu-id="7ec62-120">Na caixa de diálogo **Criar uma nova tarefa**, no campo **Nome**, insira um nome para a tarefa.</span><span class="sxs-lookup"><span data-stu-id="7ec62-120">In the **Create a new task** dialog box, in the **Name** field, enter a name for the task.</span></span>
1. <span data-ttu-id="7ec62-121">No campo **Deslocamento da data de vencimento a partir da data de destino**, insira um valor inteiro positivo ou negativo.</span><span class="sxs-lookup"><span data-stu-id="7ec62-121">In the **Due data offset from target date** field, enter a positive or negative integer value.</span></span> <span data-ttu-id="7ec62-122">Por exemplo, insira **-2** se a tarefa deve ser concluída dois dias antes da data de vencimento da lista de tarefas.</span><span class="sxs-lookup"><span data-stu-id="7ec62-122">For example, enter **-2** if the task should be completed two days before the task list's due date.</span></span>
1. <span data-ttu-id="7ec62-123">No campo **Notas**, insira instruções detalhadas.</span><span class="sxs-lookup"><span data-stu-id="7ec62-123">In the **Notes** field, enter detailed instructions.</span></span>
1. <span data-ttu-id="7ec62-124">No campo **Pessoa para contato**, insira o nome de um especialista no assunto que o proprietário da tarefa pode contatar se precisar de ajuda.</span><span class="sxs-lookup"><span data-stu-id="7ec62-124">In the **Contact person** field, enter the name of a subject matter expert that the task owner can contact if he or she needs help.</span></span>
1. <span data-ttu-id="7ec62-125">No campo **Link de contato**, insira um link, com base na natureza da tarefa.</span><span class="sxs-lookup"><span data-stu-id="7ec62-125">In the **Task link** field, enter a link, based on the nature of the task.</span></span>

> [!TIP]
> <span data-ttu-id="7ec62-126">Embora você possa usar o campo **Atribuído a** para atribuir tarefas a alguém enquanto está criando uma lista de tarefas, recomendamos que você evite atribuir tarefas durante a criação da lista de tarefas.</span><span class="sxs-lookup"><span data-stu-id="7ec62-126">Although you can use the **Assigned to** field to assign tasks to someone while you're creating a task list, we recommend that you avoid assigning tasks during task list creation.</span></span> <span data-ttu-id="7ec62-127">Em vez disso, atribua as tarefas depois que a lista for instanciada para armazenamentos individuais.</span><span class="sxs-lookup"><span data-stu-id="7ec62-127">Instead, assign the tasks after the list is instantiated for individual stores.</span></span>

## <a name="use-task-links-to-help-improve-worker-productivity"></a><span data-ttu-id="7ec62-128">Use links de tarefas para ajudar a melhorar a produtividade do trabalhador</span><span class="sxs-lookup"><span data-stu-id="7ec62-128">Use task links to help improve worker productivity</span></span>

<span data-ttu-id="7ec62-129">Commerce permite vincular tarefas a operações específicas do PDV, como a execução de um relatório de vendas, a exibição de um vídeo de treinamento online para a orientação de novos funcionários ou a execução de uma operação de back-office.</span><span class="sxs-lookup"><span data-stu-id="7ec62-129">Commerce lets you link tasks to specific POS operations, such as running a sales report, viewing an online training video for new employee orientation, or performing a back-office operation.</span></span> <span data-ttu-id="7ec62-130">Esse recurso ajuda os proprietários da tarefa a obter as informações necessárias para concluir uma tarefa com eficiência.</span><span class="sxs-lookup"><span data-stu-id="7ec62-130">This feature helps task owners get the information that they need to complete a task efficiently.</span></span>

<span data-ttu-id="7ec62-131">Para adicionar links de tarefas ao criar uma tarefa, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="7ec62-131">To add task links while you create a task, follow these steps.</span></span>

1. <span data-ttu-id="7ec62-132">Na Guia Rápida **Tarefas** de uma lista de tarefas existente, selecione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="7ec62-132">On the **Tasks** FastTab of an existing task list, select **Edit**.</span></span>
1. <span data-ttu-id="7ec62-133">Na caixa de diálogo **Editar tarefas**, no campo **Link das tarefas**, selecione uma ou mais das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="7ec62-133">In the **Edit task** dialog box, in the **Task link** field, select one or more of the following options:</span></span>

    - <span data-ttu-id="7ec62-134">Selecione o **Item do menu** para configurar uma operação de back-office, como "Kits de produtos".</span><span class="sxs-lookup"><span data-stu-id="7ec62-134">Select **Menu item** to configure a back-office operation, such as "Product kits."</span></span>
    - <span data-ttu-id="7ec62-135">Selecione a **Operação de PDV** para configurar uma operação de PDV, como "Relatórios de vendas".</span><span class="sxs-lookup"><span data-stu-id="7ec62-135">Select **POS Operation** to configure a POS operation, such as "Sales reports."</span></span>
    - <span data-ttu-id="7ec62-136">Selecione a **URL** para configurar uma URL absoluta.</span><span class="sxs-lookup"><span data-stu-id="7ec62-136">Select **URL** to configure an absolute URL.</span></span>

<span data-ttu-id="7ec62-137">A ilustração a seguir mostra a seleção de links de tarefas na caixa de diálogo **Editar tarefa**.</span><span class="sxs-lookup"><span data-stu-id="7ec62-137">The following illustration shows the selection of task links in the **Edit task** dialog box.</span></span>

![Selecionando links de tarefas na caixa de diálogo Editar tarefa](media/HQ-POS-Tasks-Linking.png)

### <a name="configure-a-pos-operation-so-that-it-can-be-linked-to-a-task"></a><span data-ttu-id="7ec62-139">Configurar uma operação de PDV para que possa ser vinculada a uma tarefa</span><span class="sxs-lookup"><span data-stu-id="7ec62-139">Configure a POS operation so that it can be linked to a task</span></span>

<span data-ttu-id="7ec62-140">Para configurar uma operação de PDV para que possa ser vinculada a uma tarefa, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="7ec62-140">To configure a POS operation so that it can be linked to a task, follow these steps.</span></span>

1. <span data-ttu-id="7ec62-141">Vá para **Retail e Commerce \> Configuração de canal \> Configuração do PDV \> PDV \> Operações de PDV**.</span><span class="sxs-lookup"><span data-stu-id="7ec62-141">Go to **Retail and Commerce \> Channel setup \> POS setup \> POS \> POS operations**.</span></span>
1. <span data-ttu-id="7ec62-142">Selecione **Editar**, localize a operação de PDV e marque a caixa de seleção **Habilitar gerenciamento de tarefas** para ela.</span><span class="sxs-lookup"><span data-stu-id="7ec62-142">Select **Edit**, find the POS operation, and then select the **Enable Task Management** check box for it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="7ec62-143">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="7ec62-143">Additional resources</span></span>

[<span data-ttu-id="7ec62-144">Visão geral do gerenciamento de tarefas</span><span class="sxs-lookup"><span data-stu-id="7ec62-144">Task management overview</span></span>](task-mgmt-overview.md)

[<span data-ttu-id="7ec62-145">Configurar gerenciamento de tarefas</span><span class="sxs-lookup"><span data-stu-id="7ec62-145">Configure task management</span></span>](task-mgmt-configure.md)

[<span data-ttu-id="7ec62-146">Atribuir listas de tarefas a lojas ou funcionários</span><span class="sxs-lookup"><span data-stu-id="7ec62-146">Assign task lists to stores or employees</span></span>](task-mgmt-assign-lists.md)

[<span data-ttu-id="7ec62-147">Gerenciamento de tarefas em PDV</span><span class="sxs-lookup"><span data-stu-id="7ec62-147">Task management in POS</span></span>](task-mgmt-POS.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
