---
title: Configurar tarefas automatizadas em um fluxo de trabalho
description: Este tópico explica como configurar as propriedades de uma tarefa automatizada.
author: ChrisGarty
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 192061
ms.assetid: c0aceb57-b5e6-4ef3-91e7-89a21c9f048a
ms.search.region: Global
ms.author: cgarty
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 2ca46e6c69b8e823be15f3e039408017e6463406
ms.sourcegitcommit: e55efd2f62bf60f678108c09ad4701a76b20cc68
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/17/2020
ms.locfileid: "3698258"
---
# <a name="configure-automated-tasks-in-a-workflow"></a><span data-ttu-id="114dd-103">Configurar tarefas automatizadas em um fluxo de trabalho</span><span class="sxs-lookup"><span data-stu-id="114dd-103">Configure automated tasks in a workflow</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="114dd-104">Este tópico explica como configurar as propriedades de uma tarefa automatizada.</span><span class="sxs-lookup"><span data-stu-id="114dd-104">This topic explains how to configure the properties for an automated task.</span></span>

<span data-ttu-id="114dd-105">Para configurar uma tarefa automatizada no editor de fluxo de trabalho, clique com o botão direito do mouse na tarefa e clique em **Propriedades** para abrir a página **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="114dd-105">To configure an automated task in the workflow editor, right-click the task, and then click **Properties** to open the **Properties** page.</span></span> <span data-ttu-id="114dd-106">Em seguida, use os procedimentos a seguir para configurar as propriedades da tarefa automatizada.</span><span class="sxs-lookup"><span data-stu-id="114dd-106">Then use the following procedures to configure the properties for the automated task.</span></span>

## <a name="name-the-task"></a><span data-ttu-id="114dd-107">Nomear a tarefa</span><span class="sxs-lookup"><span data-stu-id="114dd-107">Name the task</span></span>

<span data-ttu-id="114dd-108">Siga estas etapas para inserir um nome para a tarefa automatizada.</span><span class="sxs-lookup"><span data-stu-id="114dd-108">Follow these steps to enter a name for the automated task.</span></span>

1. <span data-ttu-id="114dd-109">No painel esquerdo, clique em **Configurações Básicas**.</span><span class="sxs-lookup"><span data-stu-id="114dd-109">In the left pane, click **Basic Settings**.</span></span>
2. <span data-ttu-id="114dd-110">No campo **Nome**, insira um nome exclusivo para a tarefa.</span><span class="sxs-lookup"><span data-stu-id="114dd-110">In the **Name** field, enter a unique name for the task.</span></span>

## <a name="specify-when-notifications-are-sent"></a><span data-ttu-id="114dd-111">Especificar quando enviar notificações</span><span class="sxs-lookup"><span data-stu-id="114dd-111">Specify when notifications are sent</span></span>

<span data-ttu-id="114dd-112">É possível enviar notificações às pessoas quando uma tarefa automatizada tiver sido executada ou cancelada.</span><span class="sxs-lookup"><span data-stu-id="114dd-112">You can send notifications to people when an automated task has been run or canceled.</span></span> <span data-ttu-id="114dd-113">Siga estas etapas para especificar quando as notificações são enviadas, e a quem são enviadas.</span><span class="sxs-lookup"><span data-stu-id="114dd-113">Follow these steps to specify when notifications are sent, and who they are sent to.</span></span>

1. <span data-ttu-id="114dd-114">No painel esquerdo, clique em **Notificações**.</span><span class="sxs-lookup"><span data-stu-id="114dd-114">In the left pane, click **Notifications**.</span></span>
2. <span data-ttu-id="114dd-115">Marque a caixa de seleção ao lado dos eventos para os quais enviar notificações:</span><span class="sxs-lookup"><span data-stu-id="114dd-115">Select the check box next to the events to send notifications for:</span></span>

    - <span data-ttu-id="114dd-116">**Execução** – as notificações são enviadas quando a tarefa tiver sido executada.</span><span class="sxs-lookup"><span data-stu-id="114dd-116">**Execution** – Notifications are sent when the task has been run.</span></span>
    - <span data-ttu-id="114dd-117">**Cancelada** – as notificações são enviadas quando a tarefa tiver sido cancelada.</span><span class="sxs-lookup"><span data-stu-id="114dd-117">**Canceled** – Notifications are sent when the task has been canceled.</span></span>

3. <span data-ttu-id="114dd-118">Selecione a linha de um evento que você selecionou na etapa 2.</span><span class="sxs-lookup"><span data-stu-id="114dd-118">Select the row for an event that you selected in step 2.</span></span>
4. <span data-ttu-id="114dd-119">Na guia **Texto da notificação**, insira o texto da notificação na caixa de texto.</span><span class="sxs-lookup"><span data-stu-id="114dd-119">On the **Notification text** tab, in the text box, enter the text of the notification.</span></span>
5. <span data-ttu-id="114dd-120">Para personalizar a notificação, você poderá inserir espaços reservados.</span><span class="sxs-lookup"><span data-stu-id="114dd-120">To personalize the notification, you can insert placeholders.</span></span> <span data-ttu-id="114dd-121">Esses espaços reservados são substituídos pelos dados adequados quando a notificação é exibida para os usuários.</span><span class="sxs-lookup"><span data-stu-id="114dd-121">Placeholders are replaced with appropriate data when the notification is shown to users.</span></span> <span data-ttu-id="114dd-122">Siga estas etapas para inserir um espaço reservado:</span><span class="sxs-lookup"><span data-stu-id="114dd-122">Follow these steps to insert a placeholder:</span></span>

    1. <span data-ttu-id="114dd-123">Na caixa de texto, clique no local onde o espaço reservado deve aparecer.</span><span class="sxs-lookup"><span data-stu-id="114dd-123">In the text box, click where the placeholder should appear.</span></span>
    2. <span data-ttu-id="114dd-124">Clique em **Inserir espaço reservado**.</span><span class="sxs-lookup"><span data-stu-id="114dd-124">Click **Insert placeholder**.</span></span>
    3. <span data-ttu-id="114dd-125">Na lista exibida, selecione o espaço reservado a ser inserido.</span><span class="sxs-lookup"><span data-stu-id="114dd-125">In the list that appears, select the placeholder to insert.</span></span>
    4. <span data-ttu-id="114dd-126">Clique em **Inserir**.</span><span class="sxs-lookup"><span data-stu-id="114dd-126">Click **Insert**.</span></span>

6. <span data-ttu-id="114dd-127">Para adicionar traduções da notificação, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="114dd-127">To add translations of the notification, follow these steps:</span></span>

    1. <span data-ttu-id="114dd-128">Clique em **Traduções**.</span><span class="sxs-lookup"><span data-stu-id="114dd-128">Click **Translations**.</span></span>
    2. <span data-ttu-id="114dd-129">Na página exibida, clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="114dd-129">On the page that appears, click **Add**.</span></span>
    3. <span data-ttu-id="114dd-130">Na lista exibida, selecione o idioma do texto que você está inserindo.</span><span class="sxs-lookup"><span data-stu-id="114dd-130">In the list that appears, select the language that you're entering the text in.</span></span>
    4. <span data-ttu-id="114dd-131">No campo **Texto traduzido**, insira o texto.</span><span class="sxs-lookup"><span data-stu-id="114dd-131">In the **Translated text** field, enter the text.</span></span>
    5. <span data-ttu-id="114dd-132">Para personalizar o texto, insira os espaços reservados conforme descrito na etapa 5.</span><span class="sxs-lookup"><span data-stu-id="114dd-132">To personalize the text, you can insert placeholders as described in step 5.</span></span>
    6. <span data-ttu-id="114dd-133">Clique em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="114dd-133">Click **Close**.</span></span>

7. <span data-ttu-id="114dd-134">Na guia **Destinatário**, especifique para quem as notificações serão enviadas.</span><span class="sxs-lookup"><span data-stu-id="114dd-134">On the **Recipient** tab, specify who the notifications are sent to.</span></span> <span data-ttu-id="114dd-135">Selecione uma das opções na tabela a seguir e execute as etapas adicionais dessa opção antes de passar para a etapa 8.</span><span class="sxs-lookup"><span data-stu-id="114dd-135">Select one of the options in the following table, and then follow the additional steps for that option before you go to step 8.</span></span>

    <table>
    <thead>
    <tr>
    <th><span data-ttu-id="114dd-136">Opção</span><span class="sxs-lookup"><span data-stu-id="114dd-136">Option</span></span></th>
    <th><span data-ttu-id="114dd-137">Destinatários da notificação</span><span class="sxs-lookup"><span data-stu-id="114dd-137">Notification recipients</span></span></th>
    <th><span data-ttu-id="114dd-138">Etapas adicionais</span><span class="sxs-lookup"><span data-stu-id="114dd-138">Additional steps</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr>
    <td><span data-ttu-id="114dd-139">Participante</span><span class="sxs-lookup"><span data-stu-id="114dd-139">Participant</span></span></td>
    <td><span data-ttu-id="114dd-140">Usuários que foram atribuídos a uma função ou um grupo específico</span><span class="sxs-lookup"><span data-stu-id="114dd-140">Users who are assigned to a specific group or role</span></span></td>
    <td>
    <ol>
    <li><span data-ttu-id="114dd-141">Depois que você selecionar <strong>Participante</strong>, na guia <strong>Baseado em função</strong>, na lista <strong>Tipo de participante</strong>, selecione o tipo de grupo ou de função ao qual enviar notificações.</span><span class="sxs-lookup"><span data-stu-id="114dd-141">After you select <strong>Participant</strong>, on the <strong>Role based</strong> tab, in the <strong>Type of participant</strong> list, select the type of group or role to send notifications to.</span></span></li>
    <li><span data-ttu-id="114dd-142">Na lista <strong>Participante</strong>, selecione o grupo ou a função ao qual serão enviadas notificações.</span><span class="sxs-lookup"><span data-stu-id="114dd-142">In the <strong>Participant</strong> list, select the group or role to send notifications to.</span></span></li>
    </ol>
    </td>
    </tr>
    <tr>
    <td><span data-ttu-id="114dd-143">Usuário de fluxo de trabalho</span><span class="sxs-lookup"><span data-stu-id="114dd-143">Workflow user</span></span></td>
    <td><span data-ttu-id="114dd-144">Usuários que participam do fluxo de trabalho atual</span><span class="sxs-lookup"><span data-stu-id="114dd-144">Users who participate in the current workflow</span></span></td>
    <td>
    <ul>
    <li><span data-ttu-id="114dd-145">Depois que você selecionar <strong>Usuário de fluxo de trabalho</strong> na guia <strong>Usuário de fluxo de trabalho</strong>, na lista <strong>Usuário de fluxo de trabalho</strong>, selecione um usuário que participa do fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="114dd-145">After you select <strong>Workflow user</strong>, on the <strong>Workflow user</strong> tab, in the <strong>Workflow user</strong> list, select a user who participates in the workflow.</span></span></li>
    </ul>
    </td>
    </tr>
    <tr>
    <td><span data-ttu-id="114dd-146">Usuário</span><span class="sxs-lookup"><span data-stu-id="114dd-146">User</span></span></td>
    <td><span data-ttu-id="114dd-147">Usuários específicos</span><span class="sxs-lookup"><span data-stu-id="114dd-147">Specific users</span></span></td>
    <td>
    <ol>
    <li><span data-ttu-id="114dd-148">Após selecionar <strong>Usuário</strong>, clique na guia <strong>Usuário</strong>.</span><span class="sxs-lookup"><span data-stu-id="114dd-148">After you select <strong>User</strong>, click the <strong>User</strong> tab.</span></span></li>
    <li><span data-ttu-id="114dd-149">A lista <strong>Usuários disponíveis</strong> inclui todos os usuários.</span><span class="sxs-lookup"><span data-stu-id="114dd-149">The <strong>Available users</strong> list includes all users.</span></span> <span data-ttu-id="114dd-150">Selecione os usuários aos quais enviar notificações e mova- os para a lista <strong>Usuários selecionados</strong>.</span><span class="sxs-lookup"><span data-stu-id="114dd-150">Select the users to send notifications to, and then move those users to the <strong>Selected users</strong> list.</span></span></li>
    </ol>
    </td>
    </tr>
    </tbody>
    </table>

8. <span data-ttu-id="114dd-151">Repita as etapas de 3 a 7 para cada evento selecionado na etapa 2.</span><span class="sxs-lookup"><span data-stu-id="114dd-151">Repeat steps 3 through 7 for each event that you selected in step 2.</span></span>
