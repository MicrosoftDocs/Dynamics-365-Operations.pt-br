---
title: Configurar tarefas manuais em um fluxo de trabalho
description: Este tópico explica como configurar as propriedades de uma tarefa manual.
author: sericks007
manager: AnnBe
ms.date: 08/23/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 192191
ms.assetid: 27f1afde-ff26-4b6f-8c11-27ec49130bbb
ms.search.region: Global
ms.author: donaldc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 492c49b1a3e8334bca401770c4c2db04e8892691
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2190157"
---
# <a name="configure-manual-tasks-in-a-workflow"></a><span data-ttu-id="37e79-103">Configurar tarefas manuais em um fluxo de trabalho</span><span class="sxs-lookup"><span data-stu-id="37e79-103">Configure manual tasks in a workflow</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="37e79-104">Este tópico explica como configurar as propriedades de uma tarefa manual.</span><span class="sxs-lookup"><span data-stu-id="37e79-104">This topic explains how to configure the properties for a manual task.</span></span>

<span data-ttu-id="37e79-105">Para configurar uma tarefa manual no editor de fluxo de trabalho, clique com o botão direito do mouse na tarefa e clique em **Propriedades** para abrir a página **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="37e79-105">To configure a manual task in the workflow editor, right-click the task, and then click **Properties** to open the **Properties** page.</span></span> <span data-ttu-id="37e79-106">Em seguida, use os procedimentos a seguir para configurar as propriedades da tarefa manual.</span><span class="sxs-lookup"><span data-stu-id="37e79-106">Then use the following procedures to configure the properties for the manual task.</span></span>

## <a name="name-the-task"></a><span data-ttu-id="37e79-107">Nomear a tarefa</span><span class="sxs-lookup"><span data-stu-id="37e79-107">Name the task</span></span>

<span data-ttu-id="37e79-108">Siga estas etapas para inserir um nome para a tarefa manual.</span><span class="sxs-lookup"><span data-stu-id="37e79-108">Follow these steps to enter a name for the manual task.</span></span>

1. <span data-ttu-id="37e79-109">No painel esquerdo, clique em **Configurações Básicas**.</span><span class="sxs-lookup"><span data-stu-id="37e79-109">In the left pane, click **Basic Settings**.</span></span>
2. <span data-ttu-id="37e79-110">No campo **Nome**, insira um nome exclusivo para a tarefa.</span><span class="sxs-lookup"><span data-stu-id="37e79-110">In the **Name** field, enter a unique name for the task.</span></span>

## <a name="enter-a-subject-line-and-instructions"></a><span data-ttu-id="37e79-111">Inserir uma linha de assunto e instruções</span><span class="sxs-lookup"><span data-stu-id="37e79-111">Enter a subject line and instructions</span></span>

<span data-ttu-id="37e79-112">Você deve fornecer uma linha de assunto e instruções para os usuários atribuídos à tarefa.</span><span class="sxs-lookup"><span data-stu-id="37e79-112">You must provide a subject line and instructions to users who are assigned to the task.</span></span> <span data-ttu-id="37e79-113">Por exemplo, se você estiver configurando uma tarefa de requisições de compra, o usuário que foi atribuído à tarefa verá a linha de assunto e as instruções na página **Requisições de compra**.</span><span class="sxs-lookup"><span data-stu-id="37e79-113">For example, if you're configuring a task for purchase requisitions, the user who is assigned to the task sees the subject line and instructions on the **Purchase requisitions** page.</span></span> <span data-ttu-id="37e79-114">A linha de assunto aparece em uma barra de mensagens na página.</span><span class="sxs-lookup"><span data-stu-id="37e79-114">The subject line appears in a message bar on the page.</span></span> <span data-ttu-id="37e79-115">O usuário poderá clicar no ícone na barra de mensagens para exibir as instruções.</span><span class="sxs-lookup"><span data-stu-id="37e79-115">The user can then click the icon in the message bar to view the instructions.</span></span> <span data-ttu-id="37e79-116">Siga estas etapas para inserir uma linha de assunto e instruções.</span><span class="sxs-lookup"><span data-stu-id="37e79-116">Follow these steps to enter a subject line and instructions.</span></span>

1. <span data-ttu-id="37e79-117">No painel esquerdo, clique em **Configurações Básicas**.</span><span class="sxs-lookup"><span data-stu-id="37e79-117">In the left pane, click **Basic Settings**.</span></span>
2. <span data-ttu-id="37e79-118">No campo **Assunto do item de trabalho**, insira a linha de assunto.</span><span class="sxs-lookup"><span data-stu-id="37e79-118">In the **Work item subject** field, enter the subject line.</span></span>
3. <span data-ttu-id="37e79-119">Para personalizar a linha de assunto, você pode inserir espaços reservados.</span><span class="sxs-lookup"><span data-stu-id="37e79-119">To personalize the subject line, you can insert placeholders.</span></span> <span data-ttu-id="37e79-120">Esses espaços reservados são substituídos pelos dados adequados quando a linha de assunto for exibida para os usuários.</span><span class="sxs-lookup"><span data-stu-id="37e79-120">Placeholders are replaced with appropriate data when the subject line is shown to users.</span></span> <span data-ttu-id="37e79-121">Siga estas etapas para inserir um espaço reservado:</span><span class="sxs-lookup"><span data-stu-id="37e79-121">Follow these steps to insert a placeholder:</span></span>

    1. <span data-ttu-id="37e79-122">Na caixa de texto, clique no local onde o espaço reservado deve aparecer.</span><span class="sxs-lookup"><span data-stu-id="37e79-122">In the text box, click where the placeholder should appear.</span></span>
    2. <span data-ttu-id="37e79-123">Clique em **Inserir espaço reservado**.</span><span class="sxs-lookup"><span data-stu-id="37e79-123">Click **Insert placeholder**.</span></span>
    3. <span data-ttu-id="37e79-124">Na lista exibida, selecione o espaço reservado a ser inserido.</span><span class="sxs-lookup"><span data-stu-id="37e79-124">In the list that appears, select the placeholder to insert.</span></span>
    4. <span data-ttu-id="37e79-125">Clique em **Inserir**.</span><span class="sxs-lookup"><span data-stu-id="37e79-125">Click **Insert**.</span></span>

4. <span data-ttu-id="37e79-126">Para adicionar traduções da linha de assunto, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="37e79-126">To add translations of the subject line, follow these steps:</span></span>

    1. <span data-ttu-id="37e79-127">Clique em **Traduções**.</span><span class="sxs-lookup"><span data-stu-id="37e79-127">Click **Translations**.</span></span>
    2. <span data-ttu-id="37e79-128">Na página exibida, clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="37e79-128">On the page that appears, click **Add**.</span></span>
    3. <span data-ttu-id="37e79-129">Na lista exibida, selecione o idioma do texto que você está inserindo.</span><span class="sxs-lookup"><span data-stu-id="37e79-129">In the list that appears, select the language that you're entering the text in.</span></span>
    4. <span data-ttu-id="37e79-130">No campo **Texto traduzido**, insira o texto.</span><span class="sxs-lookup"><span data-stu-id="37e79-130">In the **Translated text** field, enter the text.</span></span>
    5. <span data-ttu-id="37e79-131">Para personalizar o texto, insira os espaços reservados conforme descrito na etapa 3.</span><span class="sxs-lookup"><span data-stu-id="37e79-131">To personalize the text, you can insert placeholders as described in step 3.</span></span>
    6. <span data-ttu-id="37e79-132">Clique em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="37e79-132">Click **Close**.</span></span>

5. <span data-ttu-id="37e79-133">No campo **Instruções do item de trabalho**, insira as instruções.</span><span class="sxs-lookup"><span data-stu-id="37e79-133">In the **Work item instructions** field, enter the instructions.</span></span>
6. <span data-ttu-id="37e79-134">Para personalizar as instruções, você pode inserir espaços reservados.</span><span class="sxs-lookup"><span data-stu-id="37e79-134">To personalize the instructions, you can insert placeholders.</span></span> <span data-ttu-id="37e79-135">Esses espaços reservados são substituídos pelos dados adequados quando as instruções são exibidas para os usuários.</span><span class="sxs-lookup"><span data-stu-id="37e79-135">Placeholders are replaced with appropriate data when the instructions are shown to users.</span></span> <span data-ttu-id="37e79-136">Siga estas etapas para inserir um espaço reservado:</span><span class="sxs-lookup"><span data-stu-id="37e79-136">Follow these steps to insert a placeholder:</span></span>

    1. <span data-ttu-id="37e79-137">Na caixa de texto, clique no local onde o espaço reservado deve aparecer.</span><span class="sxs-lookup"><span data-stu-id="37e79-137">In the text box, click where the placeholder should appear.</span></span>
    2. <span data-ttu-id="37e79-138">Clique em **Inserir espaço reservado**.</span><span class="sxs-lookup"><span data-stu-id="37e79-138">Click **Insert placeholder**.</span></span>
    3. <span data-ttu-id="37e79-139">Na lista exibida, selecione o espaço reservado a ser inserido.</span><span class="sxs-lookup"><span data-stu-id="37e79-139">In the list that appears, select the placeholder to insert.</span></span>
    4. <span data-ttu-id="37e79-140">Clique em **Inserir**.</span><span class="sxs-lookup"><span data-stu-id="37e79-140">Click **Insert**.</span></span>

7. <span data-ttu-id="37e79-141">Para adicionar traduções das instruções, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="37e79-141">To add translations of the instructions, follow these steps:</span></span>

    1. <span data-ttu-id="37e79-142">Clique em **Traduções**.</span><span class="sxs-lookup"><span data-stu-id="37e79-142">Click **Translations**.</span></span>
    2. <span data-ttu-id="37e79-143">Na página exibida, clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="37e79-143">On the page that appears, click **Add**.</span></span>
    3. <span data-ttu-id="37e79-144">Na lista exibida, selecione o idioma do texto que você está inserindo.</span><span class="sxs-lookup"><span data-stu-id="37e79-144">In the list that appears, select the language that you're entering the text in.</span></span>
    4. <span data-ttu-id="37e79-145">No campo **Texto traduzido**, insira o texto.</span><span class="sxs-lookup"><span data-stu-id="37e79-145">In the **Translated text** field, enter the text.</span></span>
    5. <span data-ttu-id="37e79-146">Para personalizar o texto, insira os espaços reservados conforme descrito na etapa 6.</span><span class="sxs-lookup"><span data-stu-id="37e79-146">To personalize the text, you can insert placeholders as described in step 6.</span></span>
    6. <span data-ttu-id="37e79-147">Clique em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="37e79-147">Click **Close**.</span></span>

## <a name="assign-the-task"></a><span data-ttu-id="37e79-148">Atribuir a tarefa</span><span class="sxs-lookup"><span data-stu-id="37e79-148">Assign the task</span></span>

<span data-ttu-id="37e79-149">Siga estas etapas para especificar a quem a tarefa manual deve ser atribuída.</span><span class="sxs-lookup"><span data-stu-id="37e79-149">Follow these steps to specify who the manual task should be assigned to.</span></span>

1. <span data-ttu-id="37e79-150">No painel esquerdo, clique em **Atribuição**.</span><span class="sxs-lookup"><span data-stu-id="37e79-150">In the left pane, click **Assignment**.</span></span>
2. <span data-ttu-id="37e79-151">Na guia **Tipo de atribuição**, selecione uma das opções na tabela a seguir e execute as etapas adicionais dessa opção antes de passar para a etapa 3.</span><span class="sxs-lookup"><span data-stu-id="37e79-151">On the **Assignment type** tab, select one of the options in the following table, and then follow the additional steps for that option before you go to step 3.</span></span>

    <table>
    <thead>
    <tr>
    <th><span data-ttu-id="37e79-152">Opção</span><span class="sxs-lookup"><span data-stu-id="37e79-152">Option</span></span></th>
    <th><span data-ttu-id="37e79-153">Usuários aos quais a tarefa será atribuída</span><span class="sxs-lookup"><span data-stu-id="37e79-153">Users that the task is assigned to</span></span></th>
    <th><span data-ttu-id="37e79-154">Etapas adicionais</span><span class="sxs-lookup"><span data-stu-id="37e79-154">Additional steps</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr>
    <td><span data-ttu-id="37e79-155">Participante</span><span class="sxs-lookup"><span data-stu-id="37e79-155">Participant</span></span></td>
    <td><span data-ttu-id="37e79-156">Usuários que foram atribuídos a uma função ou um grupo específico</span><span class="sxs-lookup"><span data-stu-id="37e79-156">Users who are assigned to a specific group or role</span></span></td>
    <td>
    <ol>
    <li><span data-ttu-id="37e79-157">Depois que você selecionar <strong>Participante</strong>, na guia <strong>Baseado em função</strong>, na lista <strong>Tipo de participante</strong>, selecione o tipo de grupo ou de função ao qual atribuir a tarefa.</span><span class="sxs-lookup"><span data-stu-id="37e79-157">After you select <strong>Participant</strong>, on the <strong>Role based</strong> tab, in the <strong>Type of participant</strong> list, select the type of group or role to assign the task to.</span></span></li>
    <li><span data-ttu-id="37e79-158">Na lista <strong>Participante</strong>, selecione o grupo ou a função ao qual atribuir a tarefa.</span><span class="sxs-lookup"><span data-stu-id="37e79-158">In the <strong>Participant</strong> list, select the group or role to assign the task to.</span></span></li>
    </ol>
    </td>
    </tr>
    <tr>
    <td><span data-ttu-id="37e79-159">Hierarquia</span><span class="sxs-lookup"><span data-stu-id="37e79-159">Hierarchy</span></span></td>
    <td><span data-ttu-id="37e79-160">Usuários em uma hierarquia organizacional específica</span><span class="sxs-lookup"><span data-stu-id="37e79-160">Users in a specific organizational hierarchy</span></span></td>
    <td>
    <ol>
    <li><span data-ttu-id="37e79-161">Depois que você selecionar <strong>Hierarquia</strong>, na guia <strong>Seleção de hierarquia</strong>, na lista <strong>Tipo de hierarquia</strong>, selecione o tipo de hierarquia ao qual atribuir a tarefa.</span><span class="sxs-lookup"><span data-stu-id="37e79-161">After you select <strong>Hierarchy</strong>, on the <strong>Hierarchy selection</strong> tab, in the <strong>Hierarchy type</strong> list, select the type of hierarchy to assign the task to.</span></span></li>
    <li><span data-ttu-id="37e79-162">O sistema deve recuperar um intervalo de nomes de usuário da hierarquia.</span><span class="sxs-lookup"><span data-stu-id="37e79-162">The system must retrieve a range of user names from the hierarchy.</span></span> <span data-ttu-id="37e79-163">Esses nomes representam os usuários aos quais a tarefa pode ser atribuída.</span><span class="sxs-lookup"><span data-stu-id="37e79-163">These names represent users that the task can be assigned to.</span></span> <span data-ttu-id="37e79-164">Siga estas etapas para especificar o ponto inicial e final do intervalo de nomes de usuário que o sistema recupera:</span><span class="sxs-lookup"><span data-stu-id="37e79-164">Follow these steps to specify the starting point and ending point of the range of user names that the system retrieves:</span></span> <ol>
    <li><span data-ttu-id="37e79-165">Para especificar o ponto de partida, selecione uma pessoa na lista <strong>Iniciar em</strong>.</span><span class="sxs-lookup"><span data-stu-id="37e79-165">To specify the starting point, select a person in the <strong>Start from</strong> list.</span></span></li>
    <li><span data-ttu-id="37e79-166">Para especificar o ponto final, clique em <strong>Adicionar condição</strong>.</span><span class="sxs-lookup"><span data-stu-id="37e79-166">To specify the ending point, click <strong>Add condition</strong>.</span></span> <span data-ttu-id="37e79-167">Em seguida, insira uma condição que determine em que ponto da hierarquia o sistema para de recuperar nomes.</span><span class="sxs-lookup"><span data-stu-id="37e79-167">Then enter a condition that determines where in the hierarchy the system stops retrieving names.</span></span></li>
    </ol>
    </li>
    <li><span data-ttu-id="37e79-168">Na guia <strong>Opções de hierarquia</strong>, especifique a quais usuários no intervalo a tarefa deve ser atribuída:</span><span class="sxs-lookup"><span data-stu-id="37e79-168">On the <strong>Hierarchy options</strong> tab, specify which users in the range the task should be assigned to:</span></span> <ul>
    <li><span data-ttu-id="37e79-169"><strong>Atribuir a todos os usuários recuperados</strong> – A tarefa é atribuída a todos os usuários do intervalo.</span><span class="sxs-lookup"><span data-stu-id="37e79-169"><strong>Assign to all users retrieved</strong> – The task is assigned to all users in the range.</span></span></li>
    <li><span data-ttu-id="37e79-170"><strong>Atribuir somente ao último usuário recuperado</strong> – A tarefa é atribuída somente ao último usuário do intervalo.</span><span class="sxs-lookup"><span data-stu-id="37e79-170"><strong>Assign only to last user retrieved</strong> – The task is assigned to only the last user in the range.</span></span></li>
    <li><span data-ttu-id="37e79-171"><strong>Excluir usuários com a seguinte condição</strong> – A tarefa não é atribuída aos usuários do intervalo que atenderem a determinada condição.</span><span class="sxs-lookup"><span data-stu-id="37e79-171"><strong>Exclude users with the following condition</strong> – The task isn't assigned to users in the range who meet a specific condition.</span></span> <span data-ttu-id="37e79-172">Clique em <strong>Adicionar condição</strong> para especificar a condição.</span><span class="sxs-lookup"><span data-stu-id="37e79-172">Click <strong>Add condition</strong> to specify the condition.</span></span></li>
    </ul>
    </li>
    </ol>
    </td>
    </tr>
    <tr>
    <td><span data-ttu-id="37e79-173">Usuário de fluxo de trabalho</span><span class="sxs-lookup"><span data-stu-id="37e79-173">Workflow user</span></span></td>
    <td><span data-ttu-id="37e79-174">Usuários no fluxo de trabalho atual</span><span class="sxs-lookup"><span data-stu-id="37e79-174">Users in the current workflow</span></span></td>
    <td>
    <ul>
    <li><span data-ttu-id="37e79-175">Depois que você selecionar <strong>Usuário de fluxo de trabalho</strong> na guia <strong>Usuário de fluxo de trabalho</strong>, na lista <strong>Usuário de fluxo de trabalho</strong>, selecione um usuário que participa do fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="37e79-175">After you select <strong>Workflow user</strong>, on the <strong>Workflow user</strong> tab, in the <strong>Workflow user</strong> list, select a user who participates in the workflow.</span></span></li>
    </ul>
    </td>
    </tr>
    <tr>
    <td><span data-ttu-id="37e79-176">Usuário</span><span class="sxs-lookup"><span data-stu-id="37e79-176">User</span></span></td>
    <td><span data-ttu-id="37e79-177">Usuários específicos</span><span class="sxs-lookup"><span data-stu-id="37e79-177">Specific users</span></span></td>
    <td>
    <ol>
    <li><span data-ttu-id="37e79-178">Após selecionar <strong>Usuário</strong>, clique na guia <strong>Usuário</strong>.</span><span class="sxs-lookup"><span data-stu-id="37e79-178">After you select <strong>User</strong>, click the <strong>User</strong> tab.</span></span></li>
    <li><span data-ttu-id="37e79-179">A lista <strong>Usuários disponíveis</strong> inclui todos os usuários.</span><span class="sxs-lookup"><span data-stu-id="37e79-179">The <strong>Available users</strong> list includes all users.</span></span> <span data-ttu-id="37e79-180">Selecione os usuários aos quais deseja atribuir a tarefa e mova-os para a lista <strong>Usuários selecionados</strong>.</span><span class="sxs-lookup"><span data-stu-id="37e79-180">Select the users to assign the task to, and then move those users to the <strong>Selected users</strong> list.</span></span></li>
    </ol>
    </td>
    </tr>
    <tr>
    <td><span data-ttu-id="37e79-181">Fila</span><span class="sxs-lookup"><span data-stu-id="37e79-181">Queue</span></span></td>
    <td><span data-ttu-id="37e79-182">Uma fila de itens de trabalho</span><span class="sxs-lookup"><span data-stu-id="37e79-182">A work item queue</span></span></td>
    <td>
    <ol>
    <li><span data-ttu-id="37e79-183">Após selecionar <strong>Fila</strong>, clique na guia <strong>Fila baseada</strong>.</span><span class="sxs-lookup"><span data-stu-id="37e79-183">After you select <strong>Queue</strong>, click the <strong>Queue based</strong> tab.</span></span></li>
    <li><span data-ttu-id="37e79-184">Para atribuir a tarefa a uma fila específica, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="37e79-184">To assign the task to a specific queue, follow these steps:</span></span> <ol>
    <li><span data-ttu-id="37e79-185">Na lista <strong>Tipo de fila</strong>, selecione <strong>Fila de itens de trabalho</strong>.</span><span class="sxs-lookup"><span data-stu-id="37e79-185">In the <strong>Queue type</strong> list, select <strong>Work item queues</strong>.</span></span></li>
    <li><span data-ttu-id="37e79-186">Na lista <strong>Nome da fila</strong>, selecione a fila.</span><span class="sxs-lookup"><span data-stu-id="37e79-186">In the <strong>Queue name</strong> list, select the queue.</span></span></li>
    </ol>
    </li>
    <li><span data-ttu-id="37e79-187">Se uma condição específica tiver que determinar a qual fila atribuir a tarefa, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="37e79-187">If a specific condition should determine which queue the task is assigned to, follow these steps:</span></span> <ol>
    <li><span data-ttu-id="37e79-188">Na lista <strong>Tipo de fila</strong>, selecione <strong>Filas de itens de trabalho condicionais</strong>.</span><span class="sxs-lookup"><span data-stu-id="37e79-188">In the <strong>Queue type</strong> list, select <strong>Conditional work item queues</strong>.</span></span></li>
    <li><span data-ttu-id="37e79-189">Na lista <strong>Nome da fila</strong>, selecione <strong>Fila condicional</strong>.</span><span class="sxs-lookup"><span data-stu-id="37e79-189">In the <strong>Queue name</strong> list, select <strong>Conditional queue</strong>.</span></span></li>
    </ol>
    </li>
    </ol>
    <blockquote>[!NOTE] <span data-ttu-id="37e79-190">Esta opção é usada apenas para alguns fluxos de trabalho, como Gerenciamento de casos.</span><span class="sxs-lookup"><span data-stu-id="37e79-190">This option is used for only a few workflows, such as Case management.</span></span></blockquote>
    </td>
    </tr>
    </tbody>
    </table>

3. <span data-ttu-id="37e79-191">Na guia **Limite de tempo**, no campo **Duração**, especifique quanto tempo o usuário tem para concluir a tarefa.</span><span class="sxs-lookup"><span data-stu-id="37e79-191">On the **Time limit** tab, in the **Duration** field, specify how much time the user has to complete the task.</span></span> <span data-ttu-id="37e79-192">Selecione uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="37e79-192">Select one of the following options:</span></span>

    - <span data-ttu-id="37e79-193">**Horas** – Insira o número de horas que o usuário tem para concluir a tarefa.</span><span class="sxs-lookup"><span data-stu-id="37e79-193">**Hours** – Enter the number of hours that the user has to complete the task.</span></span> <span data-ttu-id="37e79-194">Selecione o calendário usado pela sua organização e insira informações sobre a semana de trabalho da organização.</span><span class="sxs-lookup"><span data-stu-id="37e79-194">Then select the calendar that your organization uses, and enter information about your organization's work week.</span></span>
    - <span data-ttu-id="37e79-195">**Dias** – Insira o número de dias que o usuário tem para concluir a tarefa.</span><span class="sxs-lookup"><span data-stu-id="37e79-195">**Days** – Enter the number of days that the user has to complete the task.</span></span> <span data-ttu-id="37e79-196">Selecione o calendário usado pela sua organização e insira informações sobre a semana de trabalho da organização.</span><span class="sxs-lookup"><span data-stu-id="37e79-196">Then select the calendar that your organization uses, and enter information about your organization's work week.</span></span>
    - <span data-ttu-id="37e79-197">**Semanas** – Insira o número de semanas que o usuário tem para concluir a tarefa.</span><span class="sxs-lookup"><span data-stu-id="37e79-197">**Weeks** – Enter the number of weeks that the user has to complete the task.</span></span>
    - <span data-ttu-id="37e79-198">**Meses** – Selecione o dia e a semana até quando o usuário deve concluir a tarefa.</span><span class="sxs-lookup"><span data-stu-id="37e79-198">**Months** – Select the day and week that the user must complete the task by.</span></span> <span data-ttu-id="37e79-199">Por exemplo, você talvez você queira que o usuário conclua a tarefa até a sexta-feira da terceira semana do mês.</span><span class="sxs-lookup"><span data-stu-id="37e79-199">For example, you might want the user to complete the task by Friday of the third week of the month.</span></span>
    - <span data-ttu-id="37e79-200">**Anos** – Selecione o dia, a semana e o mês até quando o usuário deve concluir a tarefa.</span><span class="sxs-lookup"><span data-stu-id="37e79-200">**Years** – Select the day, week, and month that the user must complete the task by.</span></span> <span data-ttu-id="37e79-201">Por exemplo, talvez você queira que o usuário conclua a tarefa até a sexta-feira da terceira semana de dezembro.</span><span class="sxs-lookup"><span data-stu-id="37e79-201">For example, you might want the user to complete the task by Friday of the third week of December.</span></span>

    <span data-ttu-id="37e79-202">Se o usuário não concluir a tarefa no tempo alocado, a tarefa vencerá.</span><span class="sxs-lookup"><span data-stu-id="37e79-202">If the user doesn't complete the task in the allotted time, the task is overdue.</span></span> <span data-ttu-id="37e79-203">Uma tarefa vencida poderá ser escalonada, com base nas opções selecionadas na área **Escalonamento** da página.</span><span class="sxs-lookup"><span data-stu-id="37e79-203">A task that is overdue can be escalated, based on the options that you select in the **Escalation** area of the page.</span></span>

## <a name="specify-what-happens-when-the-task-is-overdue"></a><span data-ttu-id="37e79-204">Especificar o que acontece quando a tarefa está vencida</span><span class="sxs-lookup"><span data-stu-id="37e79-204">Specify what happens when the task is overdue</span></span>

<span data-ttu-id="37e79-205">Se um usuário não concluir a tarefa manual no tempo alocado, a tarefa vencerá.</span><span class="sxs-lookup"><span data-stu-id="37e79-205">If a user doesn't complete the manual task in the allotted time, the task is overdue.</span></span> <span data-ttu-id="37e79-206">Uma tarefa vencida pode ser escalonada ou atribuída automaticamente a outro usuário.</span><span class="sxs-lookup"><span data-stu-id="37e79-206">A task that is overdue can be escalated, or automatically assigned to another user.</span></span> <span data-ttu-id="37e79-207">Siga estas etapas para escalonar a tarefa se ela estiver vencida.</span><span class="sxs-lookup"><span data-stu-id="37e79-207">Follow these steps to escalate the task if it's overdue.</span></span>

1. <span data-ttu-id="37e79-208">No painel esquerdo, clique em **Escalonamento**.</span><span class="sxs-lookup"><span data-stu-id="37e79-208">In the left pane, click **Escalation**.</span></span>
2. <span data-ttu-id="37e79-209">Marque a caixa de seleção **Usar caminho de escalonamento** para criar um caminho de escalonamento.</span><span class="sxs-lookup"><span data-stu-id="37e79-209">Select the **Use escalation path** check box to create an escalation path.</span></span> <span data-ttu-id="37e79-210">O sistema atribuirá automaticamente a tarefa aos usuários listados no caminho de escalonamento.</span><span class="sxs-lookup"><span data-stu-id="37e79-210">The system automatically assigns the task to the users who are listed in the escalation path.</span></span> <span data-ttu-id="37e79-211">Por exemplo, a tabela a seguir representa um caminho de escalonamento.</span><span class="sxs-lookup"><span data-stu-id="37e79-211">For example, the following table represents an escalation path.</span></span>

    | <span data-ttu-id="37e79-212">Sequência</span><span class="sxs-lookup"><span data-stu-id="37e79-212">Sequence</span></span> | <span data-ttu-id="37e79-213">Caminho de escalonamento</span><span class="sxs-lookup"><span data-stu-id="37e79-213">Escalation path</span></span>      |
    |----------|----------------------|
    | <span data-ttu-id="37e79-214">1</span><span class="sxs-lookup"><span data-stu-id="37e79-214">1</span></span>        | <span data-ttu-id="37e79-215">Atribuir a: Denise</span><span class="sxs-lookup"><span data-stu-id="37e79-215">Assign to: Donna</span></span>     |
    | <span data-ttu-id="37e79-216">2</span><span class="sxs-lookup"><span data-stu-id="37e79-216">2</span></span>        | <span data-ttu-id="37e79-217">Atribuir a: Eduardo</span><span class="sxs-lookup"><span data-stu-id="37e79-217">Assign to: Erin</span></span>      |
    | <span data-ttu-id="37e79-218">3</span><span class="sxs-lookup"><span data-stu-id="37e79-218">3</span></span>        | <span data-ttu-id="37e79-219">Ação final: Rejeitar</span><span class="sxs-lookup"><span data-stu-id="37e79-219">Final action: Reject</span></span> |

    <span data-ttu-id="37e79-220">Nesse exemplo, o sistema atribui a tarefa vencida à Denise.</span><span class="sxs-lookup"><span data-stu-id="37e79-220">In this example, the system assigns the overdue task to Donna.</span></span> <span data-ttu-id="37e79-221">Se a Denise não concluir a tarefa no tempo alocado, o sistema a atribuirá a Eduardo.</span><span class="sxs-lookup"><span data-stu-id="37e79-221">If Donna doesn't complete the task in the allotted time, the system assigns the task to Erin.</span></span> <span data-ttu-id="37e79-222">Se Eduardo não concluir a tarefa no tempo alocado, o sistema rejeitará o documento enviado para processamento.</span><span class="sxs-lookup"><span data-stu-id="37e79-222">If Erin doesn't complete the task in the allotted time, the system rejects the document that was submitted for processing.</span></span>

3. <span data-ttu-id="37e79-223">Para adicionar um usuário ao caminho de escalonamento, clique em **Adicionar escalonamento**.</span><span class="sxs-lookup"><span data-stu-id="37e79-223">To add a user to the escalation path, click **Add escalation**.</span></span> <span data-ttu-id="37e79-224">Na guia **Tipo de atribuição**, selecione uma das opções na tabela a seguir e execute as etapas adicionais dessa opção antes de passar para a etapa 4.</span><span class="sxs-lookup"><span data-stu-id="37e79-224">On the **Assignment type** tab, select one of the options in the following table, and then follow the additional steps for that option before you go to step 4.</span></span>

    <table>
    <thead>
    <tr>
    <th><span data-ttu-id="37e79-225">Opção</span><span class="sxs-lookup"><span data-stu-id="37e79-225">Option</span></span></th>
    <th><span data-ttu-id="37e79-226">Usuários aos quais a tarefa será escalonada</span><span class="sxs-lookup"><span data-stu-id="37e79-226">Users that the task is escalated to</span></span></th>
    <th><span data-ttu-id="37e79-227">Etapas adicionais</span><span class="sxs-lookup"><span data-stu-id="37e79-227">Additional steps</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr>
    <td><span data-ttu-id="37e79-228">Hierarquia</span><span class="sxs-lookup"><span data-stu-id="37e79-228">Hierarchy</span></span></td>
    <td><span data-ttu-id="37e79-229">Usuários em uma hierarquia organizacional específica</span><span class="sxs-lookup"><span data-stu-id="37e79-229">Users in a specific organizational hierarchy</span></span></td>
    <td>
    <ol>
    <li><span data-ttu-id="37e79-230">Depois que você selecionar <strong>Hierarquia</strong>, na guia <strong>Seleção de hierarquia</strong>, na lista <strong>Tipo de hierarquia</strong>, selecione o tipo de hierarquia ao qual a tarefa será escalonada.</span><span class="sxs-lookup"><span data-stu-id="37e79-230">After you select <strong>Hierarchy</strong>, on the <strong>Hierarchy selection</strong> tab, in the <strong>Hierarchy type</strong> list, select the type of hierarchy to escalate the task to.</span></span></li>
    <li><span data-ttu-id="37e79-231">O sistema deve recuperar um intervalo de nomes de usuário da hierarquia.</span><span class="sxs-lookup"><span data-stu-id="37e79-231">The system must retrieve a range of user names from the hierarchy.</span></span> <span data-ttu-id="37e79-232">Esses nomes representam os usuários aos quais a tarefa pode ser escalonada.</span><span class="sxs-lookup"><span data-stu-id="37e79-232">These names represent users that the task can be escalated to.</span></span> <span data-ttu-id="37e79-233">Siga estas etapas para especificar o ponto inicial e final do intervalo de nomes de usuário que o sistema recupera:</span><span class="sxs-lookup"><span data-stu-id="37e79-233">Follow these steps to specify the starting point and ending point of the range of user names that the system retrieves:</span></span> <ol>
    <li><span data-ttu-id="37e79-234">Para especificar o ponto de partida, selecione uma pessoa na lista <strong>Iniciar em</strong>.</span><span class="sxs-lookup"><span data-stu-id="37e79-234">To specify the starting point, select a person in the <strong>Start from</strong> list.</span></span></li>
    <li><span data-ttu-id="37e79-235">Para especificar o ponto final, clique em <strong>Adicionar condição</strong>.</span><span class="sxs-lookup"><span data-stu-id="37e79-235">To specify the ending point, click <strong>Add condition</strong>.</span></span> <span data-ttu-id="37e79-236">Em seguida, insira uma condição que determine em que ponto da hierarquia o sistema para de recuperar nomes.</span><span class="sxs-lookup"><span data-stu-id="37e79-236">Then enter a condition that determines where in the hierarchy the system stops retrieving names.</span></span></li>
    </ol>
    </li>
    <li><span data-ttu-id="37e79-237">Na guia <strong>Opções de hierarquia</strong>, especifique a quais usuários no intervalo a tarefa deve ser escalonada:</span><span class="sxs-lookup"><span data-stu-id="37e79-237">On the <strong>Hierarchy options</strong> tab, specify which users in the range the task should be escalated to:</span></span> <ul>
    <li><span data-ttu-id="37e79-238"><strong>Atribuir a todos os usuários recuperados</strong> – A tarefa é escalonada a todos os usuários do intervalo.</span><span class="sxs-lookup"><span data-stu-id="37e79-238"><strong>Assign to all users retrieved</strong> – The task is escalated to all users in the range.</span></span></li>
    <li><span data-ttu-id="37e79-239"><strong>Atribuir somente ao último usuário recuperado</strong> – A tarefa é escalonada somente ao último usuário do intervalo.</span><span class="sxs-lookup"><span data-stu-id="37e79-239"><strong>Assign only to last user retrieved</strong> – The task is escalated to only the last user in the range.</span></span></li>
    <li><span data-ttu-id="37e79-240"><strong>Excluir usuários com a seguinte condição</strong> – Esta tarefa não é escalonada aos usuários do intervalo que atenderem a determinada condição.</span><span class="sxs-lookup"><span data-stu-id="37e79-240"><strong>Exclude users with the following condition</strong> – This task isn't escalated to users in the range who meet a specific condition.</span></span> <span data-ttu-id="37e79-241">Clique em <strong>Adicionar condição</strong> para especificar a condição.</span><span class="sxs-lookup"><span data-stu-id="37e79-241">Click <strong>Add condition</strong> to specify the condition.</span></span></li>
    </ul>
    </li>
    </ol>
    </td>
    </tr>
    <tr>
    <td><span data-ttu-id="37e79-242">Usuário de fluxo de trabalho</span><span class="sxs-lookup"><span data-stu-id="37e79-242">Workflow user</span></span></td>
    <td><span data-ttu-id="37e79-243">Usuários no fluxo de trabalho atual</span><span class="sxs-lookup"><span data-stu-id="37e79-243">Users in the current workflow</span></span></td>
    <td>
    <ul>
    <li><span data-ttu-id="37e79-244">Depois que você selecionar <strong>Usuário de fluxo de trabalho</strong> na guia <strong>Usuário de fluxo de trabalho</strong>, na lista <strong>Usuário de fluxo de trabalho</strong>, selecione um usuário que participa do fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="37e79-244">After you select <strong>Workflow user</strong>, on the <strong>Workflow user</strong> tab, in the <strong>Workflow user</strong> list, select a user who participates in the workflow.</span></span></li>
    </ul>
    </td>
    </tr>
    <tr>
    <td><span data-ttu-id="37e79-245">Usuário</span><span class="sxs-lookup"><span data-stu-id="37e79-245">User</span></span></td>
    <td><span data-ttu-id="37e79-246">Usuários específicos</span><span class="sxs-lookup"><span data-stu-id="37e79-246">Specific users</span></span></td>
    <td>
    <ol>
    <li><span data-ttu-id="37e79-247">Após selecionar <strong>Usuário</strong>, clique na guia <strong>Usuário</strong>.</span><span class="sxs-lookup"><span data-stu-id="37e79-247">After you select <strong>User</strong>, click the <strong>User</strong> tab.</span></span></li>
    <li><span data-ttu-id="37e79-248">A lista <strong>Usuários disponíveis</strong> inclui todos os usuários.</span><span class="sxs-lookup"><span data-stu-id="37e79-248">The <strong>Available users</strong> list includes all users.</span></span> <span data-ttu-id="37e79-249">Selecione os usuários aos quais escalonar a tarefa e mova-os para a lista <strong>Usuários selecionados</strong>.</span><span class="sxs-lookup"><span data-stu-id="37e79-249">Select the users to escalate the task to, and then move those users to the <strong>Selected users</strong> list.</span></span></li>
    </ol>
    </td>
    </tr>
    </tbody>
    </table>

4. <span data-ttu-id="37e79-250">Na guia **Limite de tempo**, no campo **Duração**, especifique quanto tempo o usuário tem para concluir a tarefa.</span><span class="sxs-lookup"><span data-stu-id="37e79-250">On the **Time limit** tab, in the **Duration** field, specify how much time the user has to complete the task.</span></span> <span data-ttu-id="37e79-251">Selecione uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="37e79-251">Select one of the following options:</span></span>

    - <span data-ttu-id="37e79-252">**Horas** – Insira o número de horas que o usuário tem para concluir a tarefa.</span><span class="sxs-lookup"><span data-stu-id="37e79-252">**Hours** – Enter the number of hours that the user has to complete the task.</span></span> <span data-ttu-id="37e79-253">Selecione o calendário usado pela sua organização e insira informações sobre a semana de trabalho da organização.</span><span class="sxs-lookup"><span data-stu-id="37e79-253">Then select the calendar that your organization uses, and enter information about your organization's work week.</span></span>
    - <span data-ttu-id="37e79-254">**Dias** – Insira o número de dias que o usuário tem para concluir a tarefa.</span><span class="sxs-lookup"><span data-stu-id="37e79-254">**Days** – Enter the number of days that the user has to complete the task.</span></span> <span data-ttu-id="37e79-255">Selecione o calendário usado pela sua organização e insira informações sobre a semana de trabalho da organização.</span><span class="sxs-lookup"><span data-stu-id="37e79-255">Then select the calendar that your organization uses, and enter information about your organization's work week.</span></span>
    - <span data-ttu-id="37e79-256">**Semanas** – Insira o número de semanas que o usuário tem para concluir a tarefa.</span><span class="sxs-lookup"><span data-stu-id="37e79-256">**Weeks** – Enter the number of weeks that the user has to complete the task.</span></span>
    - <span data-ttu-id="37e79-257">**Meses** – Selecione o dia e a semana até quando o usuário deve concluir a tarefa.</span><span class="sxs-lookup"><span data-stu-id="37e79-257">**Months** – Select the day and week that the user must complete the task by.</span></span> <span data-ttu-id="37e79-258">Por exemplo, você talvez você queira que o usuário conclua a tarefa até a sexta-feira da terceira semana do mês.</span><span class="sxs-lookup"><span data-stu-id="37e79-258">For example, you might want the user to complete the task by Friday of the third week of the month.</span></span>
    - <span data-ttu-id="37e79-259">**Anos** – Selecione o dia, a semana e o mês até quando o usuário deve concluir a tarefa.</span><span class="sxs-lookup"><span data-stu-id="37e79-259">**Years** – Select the day, week, and month that the user must complete the task by.</span></span> <span data-ttu-id="37e79-260">Por exemplo, talvez você queira que o usuário conclua a tarefa até a sexta-feira da terceira semana de dezembro.</span><span class="sxs-lookup"><span data-stu-id="37e79-260">For example, you might want the user to complete the task by Friday of the third week of December.</span></span>

5. <span data-ttu-id="37e79-261">Repita as etapas de 3 a 4 para cada usuário que deve ser adicionado ao caminho de escalonamento.</span><span class="sxs-lookup"><span data-stu-id="37e79-261">Repeat steps 3 through 4 for each user that should be added to the escalation path.</span></span> <span data-ttu-id="37e79-262">Você pode alterar a ordem dos usuários.</span><span class="sxs-lookup"><span data-stu-id="37e79-262">You can change the order of the users.</span></span>
6. <span data-ttu-id="37e79-263">Se os usuários no caminho de escalonamento não concluírem a tarefa no tempo alocado, o sistema executará uma ação na tarefa.</span><span class="sxs-lookup"><span data-stu-id="37e79-263">If the users in the escalation path don't complete the task in the allotted time, the system takes action on the task.</span></span> <span data-ttu-id="37e79-264">Para especificar a ação que o sistema executará, selecione a linha **Ação** e, na guia **Encerrar ação**, selecione uma ação.</span><span class="sxs-lookup"><span data-stu-id="37e79-264">To specify the action that the system takes, select the **Action** row, and then, on the **End action** tab, select an action.</span></span>

## <a name="specify-when-the-system-automatically-acts-on-the-task"></a><span data-ttu-id="37e79-265">Especificar quando o sistema deve executar automaticamente uma ação na tarefa</span><span class="sxs-lookup"><span data-stu-id="37e79-265">Specify when the system automatically acts on the task</span></span>

<span data-ttu-id="37e79-266">Você pode configurar o sistema para executar uma ação na tarefa manual se condições específicas forem atendidas.</span><span class="sxs-lookup"><span data-stu-id="37e79-266">You can configure the system to take action on the manual task if specific conditions are met.</span></span> <span data-ttu-id="37e79-267">Por exemplo, uma tarefa requer que um membro do departamento de relatórios de despesas revise os recibos que são enviados com um relatório de despesas.</span><span class="sxs-lookup"><span data-stu-id="37e79-267">For example, a task requires that a member of the Expense reports department review the receipts that are submitted together with an expense report.</span></span> <span data-ttu-id="37e79-268">De acordo com a política da empresa, essa tarefa deverá ser executada se o valor total do relatório de despesas for superior a US$ 100.</span><span class="sxs-lookup"><span data-stu-id="37e79-268">According to company policy, this task must be performed if the total amount of the expense report is more than USD 100.</span></span> <span data-ttu-id="37e79-269">Nesse cenário, você pode configurar o sistema para marcar automaticamente a tarefa como **Concluída** quando o valor total for inferior a 100.</span><span class="sxs-lookup"><span data-stu-id="37e79-269">In this scenario, you can configure the system to automatically mark the task as **Complete** when the total amount is less than 100.</span></span> <span data-ttu-id="37e79-270">Siga estas etapas para especificar quando o sistema executará uma ação na tarefa manual.</span><span class="sxs-lookup"><span data-stu-id="37e79-270">Follow these steps to specify when the system takes action on the manual task.</span></span>

1. <span data-ttu-id="37e79-271">No painel esquerdo, clique em **Ações automáticas**.</span><span class="sxs-lookup"><span data-stu-id="37e79-271">In the left pane, click **Automatic actions**.</span></span>
2. <span data-ttu-id="37e79-272">Marque a caixa de seleção **Habilitar ações automáticas**.</span><span class="sxs-lookup"><span data-stu-id="37e79-272">Select the **Enable automatic actions** check box.</span></span>
3. <span data-ttu-id="37e79-273">Clique em **Adicionar condição**.</span><span class="sxs-lookup"><span data-stu-id="37e79-273">Click **Add condition**.</span></span>
4. <span data-ttu-id="37e79-274">Insira uma condição.</span><span class="sxs-lookup"><span data-stu-id="37e79-274">Enter a condition.</span></span>
5. <span data-ttu-id="37e79-275">Insira quaisquer condições adicionais necessárias.</span><span class="sxs-lookup"><span data-stu-id="37e79-275">Enter any additional conditions that are required.</span></span>
6. <span data-ttu-id="37e79-276">Para verificar se as condições inseridas foram configuradas corretamente, execute estas etapas:</span><span class="sxs-lookup"><span data-stu-id="37e79-276">To verify that the conditions that you entered are configured correctly, follow these steps:</span></span>

    1. <span data-ttu-id="37e79-277">Clique em **Teste**.</span><span class="sxs-lookup"><span data-stu-id="37e79-277">Click **Test**.</span></span>
    2. <span data-ttu-id="37e79-278">Na página **Testar condição de fluxo de trabalho**, na área **Validar condição**, selecione um registro.</span><span class="sxs-lookup"><span data-stu-id="37e79-278">On the **Test workflow condition** page, in the **Validate condition** area, select a record.</span></span>
    3. <span data-ttu-id="37e79-279">Clique em **Teste**.</span><span class="sxs-lookup"><span data-stu-id="37e79-279">Click **Test**.</span></span> <span data-ttu-id="37e79-280">O sistema avaliará o registro para determinar se ele atende às condições definidas.</span><span class="sxs-lookup"><span data-stu-id="37e79-280">The system evaluates the record to determine whether it meets the conditions that you defined.</span></span>
    4. <span data-ttu-id="37e79-281">Clique em **OK** ou **Cancelar** para retornar à página **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="37e79-281">Click **OK** or **Cancel** to return to the **Properties** page.</span></span>

7. <span data-ttu-id="37e79-282">Na lista **Ação de autocompletar**, selecione a ação que o sistema deve executar na tarefa.</span><span class="sxs-lookup"><span data-stu-id="37e79-282">In the **Auto complete action** list, select the action that the system should take on the task.</span></span>

## <a name="specify-when-notifications-are-sent"></a><span data-ttu-id="37e79-283">Especificar quando enviar notificações</span><span class="sxs-lookup"><span data-stu-id="37e79-283">Specify when notifications are sent</span></span>

<span data-ttu-id="37e79-284">Você poderá enviar notificações às pessoas quando uma tarefa manual for delegada, escalonada, concluída ou rejeitada, ou quando uma alteração for solicitada.</span><span class="sxs-lookup"><span data-stu-id="37e79-284">You can send notifications to people when a manual task has been delegated, escalated, completed, or rejected, or when a change has been requested.</span></span> <span data-ttu-id="37e79-285">Siga estas etapas para especificar quando enviar notificações e a quem elas devem ser enviadas.</span><span class="sxs-lookup"><span data-stu-id="37e79-285">Follow these steps to specify when notifications are sent, and who the notifications are sent to.</span></span>

1. <span data-ttu-id="37e79-286">No painel esquerdo, clique em **Notificações**.</span><span class="sxs-lookup"><span data-stu-id="37e79-286">In the left pane, click **Notifications**.</span></span>
2. <span data-ttu-id="37e79-287">Marque a caixa de seleção ao lado dos eventos para os quais as notificações devem ser enviadas:</span><span class="sxs-lookup"><span data-stu-id="37e79-287">Select the check box next to the events that notifications should be sent for:</span></span>

    - <span data-ttu-id="37e79-288">**Delegar** – A tarefa foi atribuída a outro usuário.</span><span class="sxs-lookup"><span data-stu-id="37e79-288">**Delegate** – The task has been assigned to another user.</span></span>
    - <span data-ttu-id="37e79-289">**Escalonar** – O usuário atribuído não concluiu a tarefa no tempo alocado.</span><span class="sxs-lookup"><span data-stu-id="37e79-289">**Escalate** – The assigned user hasn't completed the task in the allotted time.</span></span>
    - <span data-ttu-id="37e79-290">**Concluída** – O usuário atribuído concluiu a tarefa.</span><span class="sxs-lookup"><span data-stu-id="37e79-290">**Complete** – The assigned user has completed the task.</span></span>
    - <span data-ttu-id="37e79-291">**Rejeitar** – O usuário atribuído rejeitou o documento enviado.</span><span class="sxs-lookup"><span data-stu-id="37e79-291">**Reject** – The assigned user has rejected the document that was submitted.</span></span>
    - <span data-ttu-id="37e79-292">**Solicitar alteração** – O usuário atribuído solicitou uma alteração no documento enviado.</span><span class="sxs-lookup"><span data-stu-id="37e79-292">**Request change** – The assigned user has requested a change to the document that was submitted.</span></span>

3. <span data-ttu-id="37e79-293">Selecione a linha de um evento que você selecionou na etapa 2.</span><span class="sxs-lookup"><span data-stu-id="37e79-293">Select the row for an event that you selected in step 2.</span></span>
4. <span data-ttu-id="37e79-294">Na guia **Texto da notificação**, insira o texto da notificação na caixa de texto.</span><span class="sxs-lookup"><span data-stu-id="37e79-294">On the **Notification text** tab, in the text box, enter the text of the notification.</span></span>
5. <span data-ttu-id="37e79-295">Para personalizar a notificação, você poderá inserir espaços reservados.</span><span class="sxs-lookup"><span data-stu-id="37e79-295">To personalize the notification, you can insert placeholders.</span></span> <span data-ttu-id="37e79-296">Os espaços reservados são substituídos pelas informações adequadas quando a notificação é exibida para os usuários.</span><span class="sxs-lookup"><span data-stu-id="37e79-296">Placeholders are replaced with appropriate information when the notification is shown to users.</span></span> <span data-ttu-id="37e79-297">Siga estas etapas para inserir um espaço reservado:</span><span class="sxs-lookup"><span data-stu-id="37e79-297">Follow these steps to insert a placeholder:</span></span>

    1. <span data-ttu-id="37e79-298">Na caixa de texto, clique no local onde o espaço reservado deve aparecer.</span><span class="sxs-lookup"><span data-stu-id="37e79-298">In the text box, click where the placeholder should appear.</span></span>
    2. <span data-ttu-id="37e79-299">Clique em **Inserir espaço reservado**.</span><span class="sxs-lookup"><span data-stu-id="37e79-299">Click **Insert placeholder**.</span></span>
    3. <span data-ttu-id="37e79-300">Na lista exibida, selecione o espaço reservado a ser inserido.</span><span class="sxs-lookup"><span data-stu-id="37e79-300">In the list that appears, select the placeholder to insert.</span></span>
    4. <span data-ttu-id="37e79-301">Clique em **Inserir**.</span><span class="sxs-lookup"><span data-stu-id="37e79-301">Click **Insert**.</span></span>

6. <span data-ttu-id="37e79-302">Para adicionar traduções da notificação, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="37e79-302">To add translations of the notification, follow these steps:</span></span>

    1. <span data-ttu-id="37e79-303">Clique em **Traduções**.</span><span class="sxs-lookup"><span data-stu-id="37e79-303">Click **Translations**.</span></span>
    2. <span data-ttu-id="37e79-304">Na página exibida, clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="37e79-304">On the page that appears, click **Add**.</span></span>
    3. <span data-ttu-id="37e79-305">Na lista exibida, selecione o idioma do texto que você está inserindo.</span><span class="sxs-lookup"><span data-stu-id="37e79-305">In the list that appears, select the language that you're entering the text in.</span></span>
    4. <span data-ttu-id="37e79-306">No campo **Texto traduzido**, insira o texto.</span><span class="sxs-lookup"><span data-stu-id="37e79-306">In the **Translated text** field, enter the text.</span></span>
    5. <span data-ttu-id="37e79-307">Para personalizar o texto, insira os espaços reservados conforme descrito na etapa 5.</span><span class="sxs-lookup"><span data-stu-id="37e79-307">To personalize the text, you can insert placeholders as described in step 5.</span></span>
    6. <span data-ttu-id="37e79-308">Clique em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="37e79-308">Click **Close**.</span></span>

7. <span data-ttu-id="37e79-309">Na guia **Destinatário**, especifique para quem as notificações serão enviadas.</span><span class="sxs-lookup"><span data-stu-id="37e79-309">On the **Recipient** tab, specify who the notifications are sent to.</span></span> <span data-ttu-id="37e79-310">Selecione uma das opções na tabela a seguir e execute as etapas adicionais dessa opção antes de passar para a etapa 8.</span><span class="sxs-lookup"><span data-stu-id="37e79-310">Select one of the options in the following table, and then follow the additional steps for that option before you go to step 8.</span></span>

    <table>
    <thead>
    <tr>
    <th><span data-ttu-id="37e79-311">Opção</span><span class="sxs-lookup"><span data-stu-id="37e79-311">Option</span></span></th>
    <th><span data-ttu-id="37e79-312">Destinatários da notificação</span><span class="sxs-lookup"><span data-stu-id="37e79-312">Notification recipients</span></span></th>
    <th><span data-ttu-id="37e79-313">Etapas adicionais</span><span class="sxs-lookup"><span data-stu-id="37e79-313">Additional steps</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr>
    <td><span data-ttu-id="37e79-314">Participante</span><span class="sxs-lookup"><span data-stu-id="37e79-314">Participant</span></span></td>
    <td><span data-ttu-id="37e79-315">Usuários que foram atribuídos a uma função ou um grupo específico</span><span class="sxs-lookup"><span data-stu-id="37e79-315">Users who are assigned to a specific group or role</span></span></td>
    <td>
    <ol>
    <li><span data-ttu-id="37e79-316">Depois que você selecionar <strong>Participante</strong>, na guia <strong>Baseado em função</strong>, na lista <strong>Tipo de participante</strong>, selecione o tipo de grupo ou de função ao qual enviar notificações.</span><span class="sxs-lookup"><span data-stu-id="37e79-316">After you select <strong>Participant</strong>, on the <strong>Role based</strong> tab, in the <strong>Type of participant</strong> list, select the type of group or role to send notifications to.</span></span></li>
    <li><span data-ttu-id="37e79-317">Na lista <strong>Participante</strong>, selecione o grupo ou a função ao qual serão enviadas notificações.</span><span class="sxs-lookup"><span data-stu-id="37e79-317">In the <strong>Participant</strong> list, select the group or role to send notifications to.</span></span></li>
    </ol>
    </td>
    </tr>
    <tr>
    <td><span data-ttu-id="37e79-318">Usuário de fluxo de trabalho</span><span class="sxs-lookup"><span data-stu-id="37e79-318">Workflow user</span></span></td>
    <td><span data-ttu-id="37e79-319">Usuários no fluxo de trabalho atual</span><span class="sxs-lookup"><span data-stu-id="37e79-319">Users in the current workflow</span></span></td>
    <td>
    <ul>
    <li><span data-ttu-id="37e79-320">Depois que você selecionar <strong>Usuário de fluxo de trabalho</strong> na guia <strong>Usuário de fluxo de trabalho</strong>, na lista <strong>Usuário de fluxo de trabalho</strong>, selecione um usuário que participa do fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="37e79-320">After you select <strong>Workflow user</strong>, on the <strong>Workflow user</strong> tab, in the <strong>Workflow user</strong> list, select a user who participates in the workflow.</span></span></li>
    </ul>
    </td>
    </tr>
    <tr>
    <td><span data-ttu-id="37e79-321">Usuário</span><span class="sxs-lookup"><span data-stu-id="37e79-321">User</span></span></td>
    <td><span data-ttu-id="37e79-322">Usuários específicos</span><span class="sxs-lookup"><span data-stu-id="37e79-322">Specific users</span></span></td>
    <td>
    <ol>
    <li><span data-ttu-id="37e79-323">Após selecionar <strong>Usuário</strong>, clique na guia <strong>Usuário</strong>.</span><span class="sxs-lookup"><span data-stu-id="37e79-323">After you select <strong>User</strong>, click the <strong>User</strong> tab.</span></span></li>
    <li><span data-ttu-id="37e79-324">A lista <strong>Usuários disponíveis</strong> inclui todos os usuários.</span><span class="sxs-lookup"><span data-stu-id="37e79-324">The <strong>Available users</strong> list includes all users.</span></span> <span data-ttu-id="37e79-325">Selecione os usuários aos quais enviar notificações e mova- os para a lista <strong>Usuários selecionados</strong>.</span><span class="sxs-lookup"><span data-stu-id="37e79-325">Select the users to send notifications to, and then move those users to the <strong>Selected users</strong> list.</span></span></li>
    </ol>
    </td>
    </tr>
    </tbody>
    </table>

8. <span data-ttu-id="37e79-326">Repita as etapas de 3 a 7 para cada evento selecionado na etapa 2.</span><span class="sxs-lookup"><span data-stu-id="37e79-326">Repeat steps 3 through 7 for each event that you selected in step 2.</span></span>

## <a name="set-a-time-limit"></a><span data-ttu-id="37e79-327">Definir um limite de tempo</span><span class="sxs-lookup"><span data-stu-id="37e79-327">Set a time limit</span></span>

<span data-ttu-id="37e79-328">Siga estas etapas se a tarefa manual tiver que ser concluída em um horário específico.</span><span class="sxs-lookup"><span data-stu-id="37e79-328">Follow these steps if the manual task must be completed in a specific time.</span></span>

> [!NOTE]
> <span data-ttu-id="37e79-329">As opções selecionadas neste procedimento substituirão as que você selecionou nas áreas **Atribuição** e **Escalonamento** da página.</span><span class="sxs-lookup"><span data-stu-id="37e79-329">The options that you select in this procedure override the options that you selected in the **Assignment** and **Escalation** areas of the page.</span></span>

1. <span data-ttu-id="37e79-330">No painel esquerdo, clique em **Configurações avançadas**.</span><span class="sxs-lookup"><span data-stu-id="37e79-330">In the left pane, click **Advanced settings**.</span></span>
2. <span data-ttu-id="37e79-331">Marque a caixa de seleção **Definir um limite de tempo para o elemento de fluxo de trabalho**.</span><span class="sxs-lookup"><span data-stu-id="37e79-331">Select the **Set a time limit for the workflow element** check box.</span></span>
3. <span data-ttu-id="37e79-332">No campo **Duração**, especifique quando a tarefa deve ser concluída.</span><span class="sxs-lookup"><span data-stu-id="37e79-332">In the **Duration** field, specify when the task must be completed.</span></span> <span data-ttu-id="37e79-333">Selecione uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="37e79-333">Select one of the following options:</span></span>

    - <span data-ttu-id="37e79-334">**Horas** – Insira o número de Horas em que a tarefa deve ser concluída.</span><span class="sxs-lookup"><span data-stu-id="37e79-334">**Hours** – Enter the number of hours that the task must be completed in.</span></span> <span data-ttu-id="37e79-335">Selecione o calendário usado pela sua organização e insira informações sobre a semana de trabalho da organização.</span><span class="sxs-lookup"><span data-stu-id="37e79-335">Then select the calendar that your organization uses, and enter information about your organization's work week.</span></span>
    - <span data-ttu-id="37e79-336">**Dias** – Insira o número de dias em que a tarefa deve ser concluída.</span><span class="sxs-lookup"><span data-stu-id="37e79-336">**Days** – Enter the number of days that the task must be completed in.</span></span> <span data-ttu-id="37e79-337">Selecione o calendário usado pela sua organização e insira informações sobre a semana de trabalho da organização.</span><span class="sxs-lookup"><span data-stu-id="37e79-337">Then select the calendar that your organization uses, and enter information about your organization's work week.</span></span>
    - <span data-ttu-id="37e79-338">**Semanas** – Insira o número de semanas em que a tarefa deve ser concluída.</span><span class="sxs-lookup"><span data-stu-id="37e79-338">**Weeks** – Enter the number of weeks that the task must be completed in.</span></span>
    - <span data-ttu-id="37e79-339">**Meses** – Selecione o dia e a semana até quando a tarefa deve ser concluída.</span><span class="sxs-lookup"><span data-stu-id="37e79-339">**Months** – Select the day and week that the task must be completed by.</span></span> <span data-ttu-id="37e79-340">Por exemplo, você talvez queira que a tarefa seja concluída até a sexta-feira da terceira semana do mês.</span><span class="sxs-lookup"><span data-stu-id="37e79-340">For example, you might want the task to be completed by Friday of the third week of the month.</span></span>
    - <span data-ttu-id="37e79-341">**Anos** – Selecione o dia, a semana e o mês até quando a tarefa deve ser concluída.</span><span class="sxs-lookup"><span data-stu-id="37e79-341">**Years** – Select the day, week, and month that the task must be completed by.</span></span> <span data-ttu-id="37e79-342">Por exemplo, talvez você queira que a tarefa seja concluída até a sexta-feira da terceira semana de dezembro.</span><span class="sxs-lookup"><span data-stu-id="37e79-342">For example, you might want the task to be completed by Friday of the third week of December.</span></span>

4. <span data-ttu-id="37e79-343">Se o limite de tempo for excedido, o sistema executará uma ação na tarefa.</span><span class="sxs-lookup"><span data-stu-id="37e79-343">If the time limit is exceeded, the system takes action on the task.</span></span> <span data-ttu-id="37e79-344">Na lista **Ação**, selecione a ação que o sistema deve executar.</span><span class="sxs-lookup"><span data-stu-id="37e79-344">In the **Action** list, select the action that the system should take.</span></span>

## <a name="specify-which-actions-are-available-to-the-user"></a><span data-ttu-id="37e79-345">Especificar quais ações estarão disponíveis para o usuário</span><span class="sxs-lookup"><span data-stu-id="37e79-345">Specify which actions are available to the user</span></span>

<span data-ttu-id="37e79-346">Quando a tarefa manual for atribuída a um usuário, este deverá executar uma ação nessa tarefa.</span><span class="sxs-lookup"><span data-stu-id="37e79-346">When the manual task is assigned to a user, the user must take action on the task.</span></span> <span data-ttu-id="37e79-347">Siga estas etapas para especificar quais ações o usuário pode executar na tarefa</span><span class="sxs-lookup"><span data-stu-id="37e79-347">Follow these steps to specify which actions the user can take on the task.</span></span>

> [!NOTE]
> <span data-ttu-id="37e79-348">As ações disponíveis variam de acordo com o design da tarefa.</span><span class="sxs-lookup"><span data-stu-id="37e79-348">The actions that are available vary, depending on the design of the task.</span></span>

1. <span data-ttu-id="37e79-349">No painel esquerdo, clique em **Configurações avançadas**.</span><span class="sxs-lookup"><span data-stu-id="37e79-349">In the left pane, click **Advanced settings**.</span></span>
2. <span data-ttu-id="37e79-350">Marque a caixa de seleção **Concluída** se o usuário puder marcar a tarefa como **Concluída**.</span><span class="sxs-lookup"><span data-stu-id="37e79-350">Select the **Complete** check box if the user should be able to mark the task as **Complete**.</span></span>
3. <span data-ttu-id="37e79-351">Marque a caixa de seleção **Rejeitar** se o usuário puder rejeitar o documento enviado.</span><span class="sxs-lookup"><span data-stu-id="37e79-351">Select the **Reject** check box if the user should be able to reject the document that was submitted.</span></span>
4. <span data-ttu-id="37e79-352">Marque a caixa de seleção **Solicitar alteração** se o usuário puder solicitar alterações no documento que foi enviado.</span><span class="sxs-lookup"><span data-stu-id="37e79-352">Select the **Request change** check box if the user should be able to request changes to the document that was submitted.</span></span>
5. <span data-ttu-id="37e79-353">Marque a caixa de seleção **Delegar** se o usuário puder atribuir a tarefa a outro usuário.</span><span class="sxs-lookup"><span data-stu-id="37e79-353">Select the **Delegate** check box if the user should be able to assign the task to another user.</span></span>
6. <span data-ttu-id="37e79-354">Marque a caixa de seleção **Reatribuir** se o usuário puder reatribuir a tarefa a outro usuário na fila de itens de trabalho.</span><span class="sxs-lookup"><span data-stu-id="37e79-354">Select the **Reassign** check box if the user should be able to reassign the task to another user in the work item queue.</span></span>
7. <span data-ttu-id="37e79-355">Marque a caixa de seleção **Liberar** se o usuário puder reatribuir a tarefa na fila de itens de trabalho.</span><span class="sxs-lookup"><span data-stu-id="37e79-355">Select the **Release** check box if the user should be able to reassign the task to the work item queue.</span></span> <span data-ttu-id="37e79-356">Assim, outro usuário poderá concluir a tarefa.</span><span class="sxs-lookup"><span data-stu-id="37e79-356">Another user can then complete the task.</span></span>
