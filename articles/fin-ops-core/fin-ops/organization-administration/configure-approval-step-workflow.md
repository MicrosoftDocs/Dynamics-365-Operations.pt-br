---
title: Configurar etapas de aprovação em um fluxo de trabalho
description: Este tópico explica como configurar as propriedades de uma etapa de aprovação.
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
ms.custom: 192161
ms.assetid: 8b478e3d-d6b4-403b-aae0-f639a71ca36c
ms.search.region: Global
ms.author: donaldc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c5bd5300a061e12ccabdea83c20863c95e15fe19
ms.sourcegitcommit: 1d5a4f70a931e78b06811add97c1962e8d93689b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/13/2020
ms.locfileid: "3124672"
---
# <a name="configure-approval-steps-in-a-workflow"></a><span data-ttu-id="98841-103">Configurar etapas de aprovação em um fluxo de trabalho</span><span class="sxs-lookup"><span data-stu-id="98841-103">Configure approval steps in a workflow</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="98841-104">Este tópico explica como configurar as propriedades de uma etapa de aprovação.</span><span class="sxs-lookup"><span data-stu-id="98841-104">This topic explains how to configure the properties of an approval step.</span></span>

<span data-ttu-id="98841-105">Para configurar uma etapa de aprovação no editor de fluxo de trabalho, clique com o botão direito do mouse na etapa de aprovação e clique em **Propriedades** para abrir a página **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="98841-105">To configure an approval step in the workflow editor, right-click the approval step, and then click **Properties** to open the **Properties** page.</span></span> <span data-ttu-id="98841-106">Depois, use os procedimentos a seguir para configurar as propriedades da etapa de aprovação.</span><span class="sxs-lookup"><span data-stu-id="98841-106">Then use the following procedures to configure the properties of the approval step.</span></span>

## <a name="name-the-step"></a><span data-ttu-id="98841-107">Nomear a etapa</span><span class="sxs-lookup"><span data-stu-id="98841-107">Name the step</span></span>
<span data-ttu-id="98841-108">Siga estas etapas para inserir um nome para a etapa de aprovação.</span><span class="sxs-lookup"><span data-stu-id="98841-108">Follow these steps to enter a name for the approval step.</span></span>

1. <span data-ttu-id="98841-109">No painel esquerdo, clique em **Configurações Básicas**.</span><span class="sxs-lookup"><span data-stu-id="98841-109">In the left pane, click **Basic Settings**.</span></span>
2. <span data-ttu-id="98841-110">No campo **Nome**, insira um nome exclusivo para a etapa de aprovação.</span><span class="sxs-lookup"><span data-stu-id="98841-110">In the **Name** field, enter a unique name for the approval step.</span></span>

## <a name="enter-a-subject-line-and-instructions"></a><span data-ttu-id="98841-111">Inserir uma linha de assunto e instruções</span><span class="sxs-lookup"><span data-stu-id="98841-111">Enter a subject line and instructions</span></span>

<span data-ttu-id="98841-112">Você deve fornecer uma linha de assunto e instruções para os usuários atribuídos à etapa de aprovação.</span><span class="sxs-lookup"><span data-stu-id="98841-112">You must provide a subject line and instructions to users who are assigned to the approval step.</span></span> <span data-ttu-id="98841-113">Por exemplo, se você estiver configurando uma etapa de aprovação para requisições de compra, o usuário que foi atribuído à etapa verá a linha de assunto e as instruções na página **Requisições de compra**.</span><span class="sxs-lookup"><span data-stu-id="98841-113">For example, if you're configuring an approval step for purchase requisitions, the user who is assigned to the step sees the subject line and instructions on the **Purchase requisitions** page.</span></span> <span data-ttu-id="98841-114">A linha de assunto aparece em uma barra de mensagens na página.</span><span class="sxs-lookup"><span data-stu-id="98841-114">The subject line appears in a message bar on the page.</span></span> <span data-ttu-id="98841-115">Em seguida, o usuário pode clicar no ícone na barra de mensagens para ver as instruções.</span><span class="sxs-lookup"><span data-stu-id="98841-115">The user can then click the icon in the message bar to see the instructions.</span></span> <span data-ttu-id="98841-116">Siga estas etapas para inserir uma linha de assunto e instruções.</span><span class="sxs-lookup"><span data-stu-id="98841-116">Follow these steps to enter a subject line and instructions.</span></span>

1. <span data-ttu-id="98841-117">No painel esquerdo, clique em **Configurações Básicas**.</span><span class="sxs-lookup"><span data-stu-id="98841-117">In the left pane, click **Basic Settings**.</span></span>
2. <span data-ttu-id="98841-118">No campo **Assunto do item de trabalho**, insira a linha de assunto.</span><span class="sxs-lookup"><span data-stu-id="98841-118">In the **Work item subject** field, enter the subject line.</span></span>
3. <span data-ttu-id="98841-119">Para personalizar a linha de assunto, você pode inserir espaços reservados.</span><span class="sxs-lookup"><span data-stu-id="98841-119">To personalize the subject line, you can insert placeholders.</span></span> <span data-ttu-id="98841-120">Esses espaços reservados são substituídos pelos dados adequados quando a linha de assunto for exibida para os usuários.</span><span class="sxs-lookup"><span data-stu-id="98841-120">Placeholders are replaced with appropriate data when the subject line is shown to users.</span></span> <span data-ttu-id="98841-121">Siga estas etapas para inserir um espaço reservado:</span><span class="sxs-lookup"><span data-stu-id="98841-121">Follow these steps to insert a placeholder:</span></span>

    1. <span data-ttu-id="98841-122">Na caixa de texto, clique no local onde o espaço reservado deve aparecer.</span><span class="sxs-lookup"><span data-stu-id="98841-122">In the text box, click where the placeholder should appear.</span></span>
    2. <span data-ttu-id="98841-123">Clique em **Inserir espaço reservado**.</span><span class="sxs-lookup"><span data-stu-id="98841-123">Click **Insert placeholder**.</span></span>
    3. <span data-ttu-id="98841-124">Na lista exibida, selecione o espaço reservado a ser inserido.</span><span class="sxs-lookup"><span data-stu-id="98841-124">In the list that appears, select the placeholder to insert.</span></span>
    4. <span data-ttu-id="98841-125">Clique em **Inserir**.</span><span class="sxs-lookup"><span data-stu-id="98841-125">Click **Insert**.</span></span>

4. <span data-ttu-id="98841-126">Para adicionar traduções da linha de assunto, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="98841-126">To add translations of the subject line, follow these steps:</span></span>

    1. <span data-ttu-id="98841-127">Clique em **Traduções**.</span><span class="sxs-lookup"><span data-stu-id="98841-127">Click **Translations**.</span></span>
    2. <span data-ttu-id="98841-128">Na página exibida, clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="98841-128">On the page that appears, click **Add**.</span></span>
    3. <span data-ttu-id="98841-129">Na lista exibida, selecione o idioma do texto que você está inserindo.</span><span class="sxs-lookup"><span data-stu-id="98841-129">In the list that appears, select the language that you're entering the text in.</span></span>
    4. <span data-ttu-id="98841-130">No campo **Texto traduzido**, insira o texto.</span><span class="sxs-lookup"><span data-stu-id="98841-130">In the **Translated text** field, enter the text.</span></span>
    5. <span data-ttu-id="98841-131">Para personalizar o texto, insira os espaços reservados conforme descrito na etapa 3.</span><span class="sxs-lookup"><span data-stu-id="98841-131">To personalize the text, you can insert placeholders as described in step 3.</span></span>
    6. <span data-ttu-id="98841-132">Clique em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="98841-132">Click **Close**.</span></span>

5. <span data-ttu-id="98841-133">No campo **Instruções do item de trabalho**, insira as instruções.</span><span class="sxs-lookup"><span data-stu-id="98841-133">In the **Work item instructions** field, enter the instructions.</span></span>
6. <span data-ttu-id="98841-134">Para personalizar as instruções, você pode inserir espaços reservados.</span><span class="sxs-lookup"><span data-stu-id="98841-134">To personalize the instructions, you can insert placeholders.</span></span> <span data-ttu-id="98841-135">Esses espaços reservados são substituídos pelos dados adequados quando as instruções são exibidas para os usuários.</span><span class="sxs-lookup"><span data-stu-id="98841-135">Placeholders are replaced with appropriate data when the instructions are shown to users.</span></span> <span data-ttu-id="98841-136">Siga estas etapas para inserir um espaço reservado:</span><span class="sxs-lookup"><span data-stu-id="98841-136">Follow these steps to insert a placeholder:</span></span>

    1. <span data-ttu-id="98841-137">Na caixa de texto, clique no local onde o espaço reservado deve aparecer.</span><span class="sxs-lookup"><span data-stu-id="98841-137">In the text box, click where the placeholder should appear.</span></span>
    2. <span data-ttu-id="98841-138">Clique em **Inserir espaço reservado**.</span><span class="sxs-lookup"><span data-stu-id="98841-138">Click **Insert placeholder**.</span></span>
    3. <span data-ttu-id="98841-139">Na lista exibida, selecione o espaço reservado a ser inserido.</span><span class="sxs-lookup"><span data-stu-id="98841-139">In the list that appears, select the placeholder to insert.</span></span>
    4. <span data-ttu-id="98841-140">Clique em **Inserir**.</span><span class="sxs-lookup"><span data-stu-id="98841-140">Click **Insert**.</span></span>

7. <span data-ttu-id="98841-141">Para adicionar traduções das instruções, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="98841-141">To add translations of the instructions, follow these steps:</span></span>

    1. <span data-ttu-id="98841-142">Clique em **Traduções**.</span><span class="sxs-lookup"><span data-stu-id="98841-142">Click **Translations**.</span></span>
    2. <span data-ttu-id="98841-143">Na página exibida, clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="98841-143">On the page that appears, click **Add**.</span></span>
    3. <span data-ttu-id="98841-144">Na lista exibida, selecione o idioma do texto que você está inserindo.</span><span class="sxs-lookup"><span data-stu-id="98841-144">In the list that appears, select the language that you're entering the text in.</span></span>
    4. <span data-ttu-id="98841-145">No campo **Texto traduzido**, insira o texto.</span><span class="sxs-lookup"><span data-stu-id="98841-145">In the **Translated text** field, enter the text.</span></span>
    5. <span data-ttu-id="98841-146">Para personalizar o texto, insira os espaços reservados conforme descrito na etapa 6.</span><span class="sxs-lookup"><span data-stu-id="98841-146">To personalize the text, you can insert placeholders as described in step 6.</span></span>
    6. <span data-ttu-id="98841-147">Clique em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="98841-147">Click **Close**.</span></span>

## <a name="assign-the-approval-step"></a><span data-ttu-id="98841-148">Atribuir a etapa de aprovação</span><span class="sxs-lookup"><span data-stu-id="98841-148">Assign the approval step</span></span>

<span data-ttu-id="98841-149">Siga estas etapas para especificar a quem a etapa de aprovação deve ser atribuída.</span><span class="sxs-lookup"><span data-stu-id="98841-149">Follow these steps to specify who the approval step should be assigned to.</span></span>

1. <span data-ttu-id="98841-150">No painel esquerdo, clique em **Atribuição**.</span><span class="sxs-lookup"><span data-stu-id="98841-150">In the left pane, click **Assignment**.</span></span>
2. <span data-ttu-id="98841-151">Na guia **Tipo de atribuição**, selecione uma das opções na tabela a seguir e execute as etapas adicionais dessa opção antes de passar para a etapa 3.</span><span class="sxs-lookup"><span data-stu-id="98841-151">On the **Assignment type** tab, select one of the options in the following table, and then follow the additional steps for that option before you go to step 3.</span></span>

    <table>
    <thead>
    <tr>
    <th><span data-ttu-id="98841-152">Opção</span><span class="sxs-lookup"><span data-stu-id="98841-152">Option</span></span></th>
    <th><span data-ttu-id="98841-153">Os usuários aos quais a etapa de aprovação foi atribuída</span><span class="sxs-lookup"><span data-stu-id="98841-153">Users that the approval step is assigned to</span></span></th>
    <th><span data-ttu-id="98841-154">Etapas adicionais</span><span class="sxs-lookup"><span data-stu-id="98841-154">Additional steps</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr>
    <td><span data-ttu-id="98841-155">Participante</span><span class="sxs-lookup"><span data-stu-id="98841-155">Participant</span></span></td>
    <td><span data-ttu-id="98841-156">Usuários que foram atribuídos a uma função ou um grupo específico</span><span class="sxs-lookup"><span data-stu-id="98841-156">Users who are assigned to a specific group or role</span></span></td>
    <td>
    <ol>
    <li><span data-ttu-id="98841-157">Depois que você selecionar <strong>Participante</strong>, na guia <strong>Baseado em função</strong>, na lista <strong>Tipo de participante</strong>, selecione o tipo de grupo ou de função ao qual atribuir a etapa.</span><span class="sxs-lookup"><span data-stu-id="98841-157">After you select <strong>Participant</strong>, on the <strong>Role based</strong> tab, in the <strong>Type of participant</strong> list, select the type of group or role to assign the step to.</span></span></li>
    <li><span data-ttu-id="98841-158">Na lista <strong>Participante</strong>, selecione o grupo ou a função ao qual atribuir a etapa.</span><span class="sxs-lookup"><span data-stu-id="98841-158">In the <strong>Participant</strong> list, select the group or role to assign the step to.</span></span></li>
    </ol>
    </td>
    </tr>
    <tr>
    <td><span data-ttu-id="98841-159">Hierarquia</span><span class="sxs-lookup"><span data-stu-id="98841-159">Hierarchy</span></span></td>
    <td><span data-ttu-id="98841-160">Usuários em uma hierarquia organizacional específica</span><span class="sxs-lookup"><span data-stu-id="98841-160">Users in a specific organizational hierarchy</span></span></td>
    <td>
    <ol>
    <li><span data-ttu-id="98841-161">Depois que você selecionar <strong>Hierarquia</strong>, na guia <strong>Seleção de hierarquia</strong>, na lista <strong>Tipo de hierarquia</strong>, selecione o tipo de hierarquia ao qual atribuir a etapa.</span><span class="sxs-lookup"><span data-stu-id="98841-161">After you select <strong>Hierarchy</strong>, on the <strong>Hierarchy selection</strong> tab, in the <strong>Hierarchy type</strong> list, select the type of hierarchy to assign the step to.</span></span></li>
    <li><span data-ttu-id="98841-162">O sistema deve recuperar um intervalo de nomes de usuário da hierarquia.</span><span class="sxs-lookup"><span data-stu-id="98841-162">The system must retrieve a range of user names from the hierarchy.</span></span> <span data-ttu-id="98841-163">Esses nomes representam os usuários aos quais a etapa pode ser atribuída.</span><span class="sxs-lookup"><span data-stu-id="98841-163">These names represent users that the step can be assigned to.</span></span> <span data-ttu-id="98841-164">Siga estas etapas para especificar o ponto inicial e final do intervalo de nomes de usuário que o sistema recupera:</span><span class="sxs-lookup"><span data-stu-id="98841-164">Follow these steps to specify the starting point and ending point of the range of user names that the system retrieves:</span></span> <ol>
    <li><span data-ttu-id="98841-165">Para especificar o ponto de partida, selecione uma pessoa na lista <strong>Iniciar em</strong>.</span><span class="sxs-lookup"><span data-stu-id="98841-165">To specify the starting point, select a person in the <strong>Start from</strong> list.</span></span></li>
    <li><span data-ttu-id="98841-166">Para especificar o ponto final, clique em <strong>Adicionar condição</strong>.</span><span class="sxs-lookup"><span data-stu-id="98841-166">To specify the ending point, click <strong>Add condition</strong>.</span></span> <span data-ttu-id="98841-167">Em seguida, insira uma condição que determine em que ponto da hierarquia o sistema para de recuperar nomes.</span><span class="sxs-lookup"><span data-stu-id="98841-167">Then enter a condition that determines where in the hierarchy the system stops retrieving names.</span></span></li>
    </ol>
    </li>
    <li><span data-ttu-id="98841-168">Na guia <strong>Opções de hierarquia</strong>, especifique a quais usuários no intervalo a etapa deve ser atribuída:</span><span class="sxs-lookup"><span data-stu-id="98841-168">On the <strong>Hierarchy options</strong> tab, specify which users in the range the step should be assigned to:</span></span> <ul>
    <li><span data-ttu-id="98841-169"><strong>Atribuir a todos os usuários recuperados</strong> – A etapa é atribuída a todos os usuários do intervalo.</span><span class="sxs-lookup"><span data-stu-id="98841-169"><strong>Assign to all users retrieved</strong> – The step is assigned to all users in the range.</span></span></li>
    <li><span data-ttu-id="98841-170"><strong>Atribuir somente ao último usuário recuperado</strong> – A etapa é atribuída somente ao último usuário do intervalo.</span><span class="sxs-lookup"><span data-stu-id="98841-170"><strong>Assign only to last user retrieved</strong> – The step is assigned to only the last user in the range.</span></span></li>
    <li><span data-ttu-id="98841-171"><strong>Excluir usuários com a seguinte condição</strong> – A etapa não é atribuído aos usuários do intervalo que atenderem a determinada condição.</span><span class="sxs-lookup"><span data-stu-id="98841-171"><strong>Exclude users with the following condition</strong> – The step isn't assigned to any users in the range who meet a specific condition.</span></span> <span data-ttu-id="98841-172">Clique em <strong>Adicionar condição</strong> para especificar a condição.</span><span class="sxs-lookup"><span data-stu-id="98841-172">Click <strong>Add condition</strong> to specify the condition.</span></span></li>
    </ul>
    </li>
    </ol>
    </td>
    </tr>
    <tr>
    <td><span data-ttu-id="98841-173">Usuário de fluxo de trabalho</span><span class="sxs-lookup"><span data-stu-id="98841-173">Workflow user</span></span></td>
    <td><span data-ttu-id="98841-174">Usuários no fluxo de trabalho atual</span><span class="sxs-lookup"><span data-stu-id="98841-174">Users in the current workflow</span></span></td>
    <td>
    <ul>
    <li><span data-ttu-id="98841-175">Depois que você selecionar <strong>Usuário de fluxo de trabalho</strong> na guia <strong>Usuário de fluxo de trabalho</strong>, na lista <strong>Usuário de fluxo de trabalho</strong>, selecione um usuário que participa do fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="98841-175">After you select <strong>Workflow user</strong>, on the <strong>Workflow user</strong> tab, in the <strong>Workflow user</strong> list, select a user who participates in the workflow.</span></span></li>
    </ul>
    </td>
    </tr>
    <tr>
    <td><span data-ttu-id="98841-176">Usuário</span><span class="sxs-lookup"><span data-stu-id="98841-176">User</span></span></td>
    <td><span data-ttu-id="98841-177">Usuários específicos</span><span class="sxs-lookup"><span data-stu-id="98841-177">Specific users</span></span></td>
    <td>
    <ol>
    <li><span data-ttu-id="98841-178">Após selecionar <strong>Usuário</strong>, clique na guia <strong>Usuário</strong>.</span><span class="sxs-lookup"><span data-stu-id="98841-178">After you select <strong>User</strong>, click the <strong>User</strong> tab.</span></span></li>
    <li><span data-ttu-id="98841-179">A lista <strong>Usuários disponíveis</strong> inclui todos os usuários do sistema.</span><span class="sxs-lookup"><span data-stu-id="98841-179">The <strong>Available users</strong> list includes all system users.</span></span> <span data-ttu-id="98841-180">Selecione os usuários aos quais deseja atribuir a etapa e mova-os para a lista <strong>Usuários selecionados</strong>.</span><span class="sxs-lookup"><span data-stu-id="98841-180">Select the users to assign the step to, and then move those users to the <strong>Selected users</strong> list.</span></span></li>
    </ol>
    </td>
    </tr>
    </tbody>
    </table>

3. <span data-ttu-id="98841-181">Na guia **Limite de tempo**, no campo **Duração**, especifique quanto tempo o usuário tem para executar uma ação nos documentos que atingem a etapa de aprovação ou responder a eles.</span><span class="sxs-lookup"><span data-stu-id="98841-181">On the **Time limit** tab, in the **Duration** field, specify how much time the user has to take action on, or respond to, documents that reach the approval step.</span></span> <span data-ttu-id="98841-182">Selecione uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="98841-182">Select one of the following options:</span></span>

    - <span data-ttu-id="98841-183">**Horas** – Insira o número de horas que o usuário tem para responder.</span><span class="sxs-lookup"><span data-stu-id="98841-183">**Hours** – Enter the number of hours that the user has to respond.</span></span> <span data-ttu-id="98841-184">Selecione o calendário usado pela sua organização e insira informações sobre a semana de trabalho da organização.</span><span class="sxs-lookup"><span data-stu-id="98841-184">Then select the calendar that your organization uses, and enter information about your organization's work week.</span></span>
    - <span data-ttu-id="98841-185">**Dias** – Insira o número de dias que o usuário tem para responder.</span><span class="sxs-lookup"><span data-stu-id="98841-185">**Days** – Enter the number of days that the user has to respond.</span></span> <span data-ttu-id="98841-186">Selecione o calendário usado pela sua organização e insira informações sobre a semana de trabalho da organização.</span><span class="sxs-lookup"><span data-stu-id="98841-186">Then select the calendar that your organization uses, and enter information about your organization's work week.</span></span>
    - <span data-ttu-id="98841-187">**Semanas** – Insira o número de semanas que o usuário tem para responder.</span><span class="sxs-lookup"><span data-stu-id="98841-187">**Weeks** – Enter the number of weeks that the user has to respond.</span></span>
    - <span data-ttu-id="98841-188">**Meses** – Selecione até que dia e semana o usuário deve responder.</span><span class="sxs-lookup"><span data-stu-id="98841-188">**Months** – Select the day and week that the user must respond by.</span></span> <span data-ttu-id="98841-189">Por exemplo, talvez você queira que o usuário responda até sexta-feira da terceira semana do mês.</span><span class="sxs-lookup"><span data-stu-id="98841-189">For example, you might want the user to respond by Friday of the third week of the month.</span></span>
    - <span data-ttu-id="98841-190">**Anos** – Selecione até que dia, semana e mês o usuário deve responder.</span><span class="sxs-lookup"><span data-stu-id="98841-190">**Years** – Select the day, week, and month that the user must respond by.</span></span> <span data-ttu-id="98841-191">Por exemplo, talvez você queira que o usuário responda até sexta-feira da terceira semana de dezembro.</span><span class="sxs-lookup"><span data-stu-id="98841-191">For example, you might want the user to respond by Friday of the third week of December.</span></span>

    <span data-ttu-id="98841-192">Se o usuário não executar nenhuma ação no documento no tempo alocado, o documento vencerá.</span><span class="sxs-lookup"><span data-stu-id="98841-192">If the user doesn't take action on the document in the allotted time, the document is overdue.</span></span> <span data-ttu-id="98841-193">Um documento vencido será escalonado, com base nas opções selecionadas na área **Escalonamento** da página.</span><span class="sxs-lookup"><span data-stu-id="98841-193">A document that is overdue is escalated, based on the options that you select in the **Escalation** area of the page.</span></span>

4. <span data-ttu-id="98841-194">Se você tiver atribuído a etapa de aprovação a vários usuários ou a um grupo de usuários, na guia **Política de conclusão**, selecione uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="98841-194">If you assigned the approval step to multiple users or a group of users, on the **Completion policy** tab, select one of the following options:</span></span>

    - <span data-ttu-id="98841-195">**Aprovador único** – a ação que é aplicada ao documento é determinada pela primeira pessoa que responde.</span><span class="sxs-lookup"><span data-stu-id="98841-195">**Single approver** – The action that is applied to the document is determined by the first person who responds.</span></span> <span data-ttu-id="98841-196">Por exemplo, suponha que Samuel tenha enviado um relatório de despesas de US$ 15.000.</span><span class="sxs-lookup"><span data-stu-id="98841-196">For example, Sam has submitted an expense report for USD 15,000.</span></span> <span data-ttu-id="98841-197">O relatório de despesas está atribuído no momento à Suzana, à Joana e a Guilherme.</span><span class="sxs-lookup"><span data-stu-id="98841-197">The expense report is currently assigned to Sue, Jo, and Bill.</span></span> <span data-ttu-id="98841-198">Se Suzana for a primeira pessoa a responder ao documento, a ação tomada por ela será aplicada.</span><span class="sxs-lookup"><span data-stu-id="98841-198">If Sue is the first person who responds to the document, the action that she takes is applied to the document.</span></span> <span data-ttu-id="98841-199">Se Suzana rejeitar o documento, ele será rejeitado e enviado novamente para Samuel.</span><span class="sxs-lookup"><span data-stu-id="98841-199">If Sue rejects the document, it's rejected and sent back to Sam.</span></span> <span data-ttu-id="98841-200">Se Suzana aprovar o documento, ele será enviado a Ana para aprovação.</span><span class="sxs-lookup"><span data-stu-id="98841-200">If Sue approves the document, it's sent to Ann for approval.</span></span>

        ![Fluxo de trabalho que tem um processo de aprovação](./media/workflow_multipleusersinstep.gif)

    - <span data-ttu-id="98841-202">**Maioria dos aprovadores** – a ação que é aplicada ao documento é determinada quando a maioria dos aprovadores responde.</span><span class="sxs-lookup"><span data-stu-id="98841-202">**Majority of approvers** – The action that is applied to the document is determined when most of the approvers respond.</span></span> <span data-ttu-id="98841-203">Por exemplo, suponha que Samuel tenha enviado um relatório de despesas de US$ 15.000.</span><span class="sxs-lookup"><span data-stu-id="98841-203">For example, Sam has submitted an expense report for USD 15,000.</span></span> <span data-ttu-id="98841-204">O relatório de despesas está atribuído no momento à Suzana, à Joana e a Guilherme.</span><span class="sxs-lookup"><span data-stu-id="98841-204">The expense report is currently assigned to Sue, Jo, and Bill.</span></span> <span data-ttu-id="98841-205">Se Suzana e Joana forem os dois primeiros aprovadores a responder, a ação tomada por ambas será aplicada ao documento.</span><span class="sxs-lookup"><span data-stu-id="98841-205">If Sue and Jo are the first two approvers who respond, the action that they take is applied to the document.</span></span>

        - <span data-ttu-id="98841-206">Se Suzana aprovar o documento, mas Joana o rejeitar, o documento será rejeitado e enviado novamente para Samuel.</span><span class="sxs-lookup"><span data-stu-id="98841-206">If Sue approves the document, but Jo rejects it, the document is rejected and sent back to Sam.</span></span>
        - <span data-ttu-id="98841-207">Se Suzana e Joana aprovarem o documento, ele será enviado a Ana para aprovação.</span><span class="sxs-lookup"><span data-stu-id="98841-207">If both Sue and Jo approve the document, it's sent to Ann for approval.</span></span>

    - <span data-ttu-id="98841-208">**Porcentagem de aprovadores** – a ação que é aplicada ao documento é determinada quando uma porcentagem específica dos aprovadores responde.</span><span class="sxs-lookup"><span data-stu-id="98841-208">**Percentage of approvers** – The action that is applied to the document is determined when a specific percentage of the approvers respond.</span></span> <span data-ttu-id="98841-209">Por exemplo, suponha que Samuel tenha enviado um relatório de despesas de US$ 15.000.</span><span class="sxs-lookup"><span data-stu-id="98841-209">For example, Sam has submitted an expense report for USD 15,000.</span></span> <span data-ttu-id="98841-210">O relatório de despesas está atribuído no momento à Suzana, à Joana e ao Guilherme, e você inseriu **50** como porcentagem.</span><span class="sxs-lookup"><span data-stu-id="98841-210">The expense report is currently assigned to Sue, Jo, and Bill, and you entered **50** as the percentage.</span></span> <span data-ttu-id="98841-211">Se Suzana e Joana forem os dois primeiros aprovadores a responderem, a ação que elas executarem será aplicada ao documento, pois o requisito de 50% dos aprovadores foi atendido.</span><span class="sxs-lookup"><span data-stu-id="98841-211">If Sue and Jo are the first two approvers who respond, the action that they take is applied to the document, because they meet the requirement for 50 percent of approvers.</span></span>

        - <span data-ttu-id="98841-212">Se Suzana aprovar o documento, mas Joana o rejeitar, o documento será rejeitado e enviado novamente para Samuel.</span><span class="sxs-lookup"><span data-stu-id="98841-212">If Sue approves the document, but Jo rejects it, the document is rejected and sent back to Sam.</span></span>
        - <span data-ttu-id="98841-213">Se Suzana e Joana aprovarem o documento, ele será enviado a Ana para aprovação.</span><span class="sxs-lookup"><span data-stu-id="98841-213">If both Sue and Jo approve the document, it's sent to Ann for approval.</span></span>

    - <span data-ttu-id="98841-214">**Todos os aprovadores** – todos os aprovadores deverão aprovar o documento.</span><span class="sxs-lookup"><span data-stu-id="98841-214">**All approvers** – All the approvers must approve the document.</span></span> <span data-ttu-id="98841-215">Caso contrário, o fluxo de trabalho não poderá continuar.</span><span class="sxs-lookup"><span data-stu-id="98841-215">Otherwise, the workflow can't continue.</span></span> <span data-ttu-id="98841-216">Por exemplo, suponha que Samuel tenha enviado um relatório de despesas de US$ 15.000.</span><span class="sxs-lookup"><span data-stu-id="98841-216">For example, Sam has submitted an expense report for USD 15,000.</span></span> <span data-ttu-id="98841-217">O relatório de despesas está atribuído no momento à Suzana, à Joana e a Guilherme.</span><span class="sxs-lookup"><span data-stu-id="98841-217">The expense report is currently assigned to Sue, Jo, and Bill.</span></span> <span data-ttu-id="98841-218">Se Suzana e Joana aprovarem o documento, mas Guilherme o rejeitar, o documento será rejeitado e enviado novamente para Samuel.</span><span class="sxs-lookup"><span data-stu-id="98841-218">If Sue and Joe approve the document, but Bill rejects it, the document is rejected and sent back to Sam.</span></span> <span data-ttu-id="98841-219">Se Suzana, Joana e Guilherme aprovarem o documento, ele será enviado a Ana para aprovação.</span><span class="sxs-lookup"><span data-stu-id="98841-219">If Sue, Jo, and Bill all approve the document, it's sent to Ann for approval.</span></span>

## <a name="specify-when-the-approval-step-is-required"></a><span data-ttu-id="98841-220">Especificar quando a etapa de aprovação é necessária</span><span class="sxs-lookup"><span data-stu-id="98841-220">Specify when the approval step is required</span></span>

<span data-ttu-id="98841-221">Você pode especificar quando a etapa de aprovação é necessária.</span><span class="sxs-lookup"><span data-stu-id="98841-221">You can specify when the approval step is required.</span></span> <span data-ttu-id="98841-222">Possivelmente, ela sempre será necessária ou será necessária apenas se condições específicas forem atendidas.</span><span class="sxs-lookup"><span data-stu-id="98841-222">The approval step can always be required, or it can be required only if specific conditions are met.</span></span>

### <a name="the-approval-step-is-always-required"></a><span data-ttu-id="98841-223">A etapa de aprovação é sempre necessária</span><span class="sxs-lookup"><span data-stu-id="98841-223">The approval step is always required</span></span>

<span data-ttu-id="98841-224">Siga estas etapas caso a etapa de aprovação seja sempre necessária.</span><span class="sxs-lookup"><span data-stu-id="98841-224">Follow these steps if the approval step is always required.</span></span>

1. <span data-ttu-id="98841-225">No painel esquerdo, clique em **Condição**.</span><span class="sxs-lookup"><span data-stu-id="98841-225">In the left pane, click **Condition**.</span></span>
2. <span data-ttu-id="98841-226">Selecione a opção **Executar sempre esta etapa**.</span><span class="sxs-lookup"><span data-stu-id="98841-226">Select the **Always run this step** option.</span></span>

### <a name="the-approval-step-is-required-in-specific-conditions"></a><span data-ttu-id="98841-227">A etapa de aprovação é necessária em condições específicas</span><span class="sxs-lookup"><span data-stu-id="98841-227">The approval step is required in specific conditions</span></span>

<span data-ttu-id="98841-228">A etapa de aprovação que você está configurando poderá ser necessária apenas se condições específicas forem atendidas.</span><span class="sxs-lookup"><span data-stu-id="98841-228">The approval step that you're configuring might be required only if specific conditions are met.</span></span> <span data-ttu-id="98841-229">Por exemplo, se você estiver configurando uma etapa de aprovação para um fluxo de trabalho de requisição de compra, talvez seja conveniente que a etapa de aprovação ocorra somente se o valor da requisição de compra for superior a US$ 10.000.</span><span class="sxs-lookup"><span data-stu-id="98841-229">For example, if you're configuring an approval step for a purchase requisition workflow, you might want the approval step to occur only if the amount of the purchase requisition is more than USD 10,000.</span></span> <span data-ttu-id="98841-230">Siga estas etapas para especificar quando a etapa de aprovação é necessária.</span><span class="sxs-lookup"><span data-stu-id="98841-230">Follow these steps to specify when the approval step is required.</span></span>

1. <span data-ttu-id="98841-231">No painel esquerdo, clique em **Condição**.</span><span class="sxs-lookup"><span data-stu-id="98841-231">In the left pane, click **Condition**.</span></span>
2. <span data-ttu-id="98841-232">Selecione a opção **Executar esta etapa somente quando a seguinte condição for atendida**.</span><span class="sxs-lookup"><span data-stu-id="98841-232">Select the **Run this step only when the following condition is met** option.</span></span>
3. <span data-ttu-id="98841-233">Insira uma condição.</span><span class="sxs-lookup"><span data-stu-id="98841-233">Enter a condition.</span></span>
4. <span data-ttu-id="98841-234">Insira quaisquer condições adicionais necessárias.</span><span class="sxs-lookup"><span data-stu-id="98841-234">Enter any additional conditions that are required.</span></span>
5. <span data-ttu-id="98841-235">Para verificar se as condições inseridas foram configuradas corretamente, execute estas etapas:</span><span class="sxs-lookup"><span data-stu-id="98841-235">To verify that the conditions that you entered are configured correctly, follow these steps:</span></span>

    1. <span data-ttu-id="98841-236">Clique em **Teste**.</span><span class="sxs-lookup"><span data-stu-id="98841-236">Click **Test**.</span></span>
    2. <span data-ttu-id="98841-237">Na página **Testar condição de fluxo de trabalho**, na área **Validar condição**, selecione um registro.</span><span class="sxs-lookup"><span data-stu-id="98841-237">On the **Test workflow condition** page, in the **Validate condition** area, select a record.</span></span>
    3. <span data-ttu-id="98841-238">Clique em **Teste**.</span><span class="sxs-lookup"><span data-stu-id="98841-238">Click **Test**.</span></span> <span data-ttu-id="98841-239">O sistema avaliará o registro para determinar se ele atende às condições definidas.</span><span class="sxs-lookup"><span data-stu-id="98841-239">The system evaluates the record to determine whether it meets the conditions that you defined.</span></span>
    4. <span data-ttu-id="98841-240">Clique em **OK** ou **Cancelar** para retornar à página **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="98841-240">Click **OK** or **Cancel** to return to the **Properties** page.</span></span>

## <a name="specify-what-happens-when-the-document-is-overdue"></a><span data-ttu-id="98841-241">Especificar o que acontece quando o documento está vencido</span><span class="sxs-lookup"><span data-stu-id="98841-241">Specify what happens when the document is overdue</span></span>

<span data-ttu-id="98841-242">Se um usuário não executar nenhuma ação em um documento no tempo alocado, o documento vencerá.</span><span class="sxs-lookup"><span data-stu-id="98841-242">If a user doesn't take action on a document in the allotted time, the document is overdue.</span></span> <span data-ttu-id="98841-243">Um documento vencido pode ser escalonado ou atribuído automaticamente a outro usuário para aprovação.</span><span class="sxs-lookup"><span data-stu-id="98841-243">A document that is overdue can be escalated, or automatically assigned to another user for approval.</span></span> <span data-ttu-id="98841-244">Siga estas etapas para escalonar o documento se ele estiver vencido.</span><span class="sxs-lookup"><span data-stu-id="98841-244">Follow these steps to escalate the document if it's overdue.</span></span>

1. <span data-ttu-id="98841-245">No painel esquerdo, clique em **Escalonamento**.</span><span class="sxs-lookup"><span data-stu-id="98841-245">In the left pane, click **Escalation**.</span></span>
2. <span data-ttu-id="98841-246">Marque a caixa de seleção **Usar caminho de escalonamento** para criar um caminho de escalonamento.</span><span class="sxs-lookup"><span data-stu-id="98841-246">Select the **Use escalation path** check box to create an escalation path.</span></span> <span data-ttu-id="98841-247">O sistema atribuirá automaticamente o documento aos usuários listados nesse caminho.</span><span class="sxs-lookup"><span data-stu-id="98841-247">The system automatically assigns the document to the users who are listed in the escalation path.</span></span> <span data-ttu-id="98841-248">Por exemplo, a tabela a seguir representa um caminho de escalonamento.</span><span class="sxs-lookup"><span data-stu-id="98841-248">For example, the following table represents an escalation path.</span></span>

    | <span data-ttu-id="98841-249">Sequência</span><span class="sxs-lookup"><span data-stu-id="98841-249">Sequence</span></span> | <span data-ttu-id="98841-250">Caminho de escalonamento</span><span class="sxs-lookup"><span data-stu-id="98841-250">Escalation path</span></span>      |
    |----------|----------------------|
    | <span data-ttu-id="98841-251">1</span><span class="sxs-lookup"><span data-stu-id="98841-251">1</span></span>        | <span data-ttu-id="98841-252">Atribuir a: Denise</span><span class="sxs-lookup"><span data-stu-id="98841-252">Assign to: Donna</span></span>     |
    | <span data-ttu-id="98841-253">2</span><span class="sxs-lookup"><span data-stu-id="98841-253">2</span></span>        | <span data-ttu-id="98841-254">Atribuir a: Eduardo</span><span class="sxs-lookup"><span data-stu-id="98841-254">Assign to: Erin</span></span>      |
    | <span data-ttu-id="98841-255">3</span><span class="sxs-lookup"><span data-stu-id="98841-255">3</span></span>        | <span data-ttu-id="98841-256">Ação final: Rejeitar</span><span class="sxs-lookup"><span data-stu-id="98841-256">Final action: Reject</span></span> |

    <span data-ttu-id="98841-257">Nesse exemplo, o sistema atribui o documento vencido à Denise.</span><span class="sxs-lookup"><span data-stu-id="98841-257">In this example, the system assigns the overdue document to Donna.</span></span> <span data-ttu-id="98841-258">Se Denise não responder no tempo alocado, o sistema atribuirá o documento a Eduardo.</span><span class="sxs-lookup"><span data-stu-id="98841-258">If Donna doesn't respond in the allotted time, the system assigns the document to Erin.</span></span> <span data-ttu-id="98841-259">Se Eduardo não responder no tempo alocado, o sistema rejeitará o documento.</span><span class="sxs-lookup"><span data-stu-id="98841-259">If Erin doesn't respond in the allotted time, the system rejects the document.</span></span>

3. <span data-ttu-id="98841-260">Para adicionar um usuário ao caminho de escalonamento, clique em **Adicionar escalonamento**.</span><span class="sxs-lookup"><span data-stu-id="98841-260">To add a user to the escalation path, click **Add escalation**.</span></span> <span data-ttu-id="98841-261">Na guia **Tipo de atribuição**, selecione uma das opções na tabela a seguir e execute as etapas adicionais dessa opção antes de passar para a etapa 4.</span><span class="sxs-lookup"><span data-stu-id="98841-261">On the **Assignment type** tab, select one of the options in the following table, and then follow the additional steps for that option before you go to step 4.</span></span>

    <table>
    <thead>
    <tr>
    <th><span data-ttu-id="98841-262">Opção</span><span class="sxs-lookup"><span data-stu-id="98841-262">Option</span></span></th>
    <th><span data-ttu-id="98841-263">Usuários aos quais o documento será escalonado</span><span class="sxs-lookup"><span data-stu-id="98841-263">Users that the document is escalated to</span></span></th>
    <th><span data-ttu-id="98841-264">Etapas adicionais</span><span class="sxs-lookup"><span data-stu-id="98841-264">Additional steps</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr>
    <td><span data-ttu-id="98841-265">Hierarquia</span><span class="sxs-lookup"><span data-stu-id="98841-265">Hierarchy</span></span></td>
    <td><span data-ttu-id="98841-266">Usuários em uma hierarquia organizacional específica</span><span class="sxs-lookup"><span data-stu-id="98841-266">Users in a specific organizational hierarchy</span></span></td>
    <td>
    <ol>
    <li><span data-ttu-id="98841-267">Depois que você selecionar <strong>Hierarquia</strong>, na guia <strong>Seleção de hierarquia</strong>, na lista <strong>Tipo de hierarquia</strong>, selecione o tipo de hierarquia ao qual o documento será escalonado.</span><span class="sxs-lookup"><span data-stu-id="98841-267">After you select <strong>Hierarchy</strong>, on the <strong>Hierarchy selection</strong> tab, in the <strong>Hierarchy type</strong> list, select the type of hierarchy to escalate the document to.</span></span></li>
    <li><span data-ttu-id="98841-268">O sistema deve recuperar um intervalo de nomes de usuário da hierarquia.</span><span class="sxs-lookup"><span data-stu-id="98841-268">The system must retrieve a range of user names from the hierarchy.</span></span> <span data-ttu-id="98841-269">Esses nomes representam usuários para os quais o documento pode ser escalonado.</span><span class="sxs-lookup"><span data-stu-id="98841-269">These names represent users that the document can be escalated to.</span></span> <span data-ttu-id="98841-270">Siga estas etapas para especificar o ponto inicial e final do intervalo de nomes de usuário que o sistema recupera:</span><span class="sxs-lookup"><span data-stu-id="98841-270">Follow these steps to specify the starting point and ending point of the range of user names that the system retrieves:</span></span> <ol>
    <li><span data-ttu-id="98841-271">Para especificar o ponto de partida, selecione uma pessoa na lista <strong>Iniciar em</strong>.</span><span class="sxs-lookup"><span data-stu-id="98841-271">To specify the starting point, select a person in the <strong>Start from</strong> list.</span></span></li>
    <li><span data-ttu-id="98841-272">Para especificar o ponto final, clique em <strong>Adicionar condição</strong>.</span><span class="sxs-lookup"><span data-stu-id="98841-272">To specify the ending point, click <strong>Add condition</strong>.</span></span> <span data-ttu-id="98841-273">Em seguida, insira uma condição que determine em que ponto da hierarquia o sistema para de recuperar nomes.</span><span class="sxs-lookup"><span data-stu-id="98841-273">Then enter a condition that determines where in the hierarchy the system stops retrieving names.</span></span></li>
    </ol>
    </li>
    <li><span data-ttu-id="98841-274">Na guia <strong>Opções de hierarquia</strong>, especifique a quais usuários no intervalo o documento deve ser escalonado:</span><span class="sxs-lookup"><span data-stu-id="98841-274">On the <strong>Hierarchy options</strong> tab, specify which users in the range the document should be escalated to:</span></span> <ul>
    <li><span data-ttu-id="98841-275"><strong>Atribuir a todos os usuários recuperados</strong> – O documento é escalonado para todos os usuários do intervalo.</span><span class="sxs-lookup"><span data-stu-id="98841-275"><strong>Assign to all users retrieved</strong> – The document is escalated to all users in the range.</span></span></li>
    <li><span data-ttu-id="98841-276"><strong>Atribuir somente ao último usuário recuperado</strong> – O documento é escalonado somente ao último usuário do intervalo.</span><span class="sxs-lookup"><span data-stu-id="98841-276"><strong>Assign only to last user retrieved</strong> – The document is escalated to only the last user in the range.</span></span></li>
    <li><span data-ttu-id="98841-277"><strong>Excluir usuários com a seguinte condição</strong> – O documento não é escalonado aos usuários do intervalo que atenderem a determinada condição.</span><span class="sxs-lookup"><span data-stu-id="98841-277"><strong>Exclude users with the following condition</strong> – The document isn't escalated to any users in the range who meet a specific condition.</span></span> <span data-ttu-id="98841-278">Clique em <strong>Adicionar condição</strong> para especificar a condição.</span><span class="sxs-lookup"><span data-stu-id="98841-278">Click <strong>Add condition</strong> to specify the condition.</span></span></li>
    </ul>
    </li>
    </ol>
    </td>
    </tr>
    <tr>
    <td><span data-ttu-id="98841-279">Usuário de fluxo de trabalho</span><span class="sxs-lookup"><span data-stu-id="98841-279">Workflow user</span></span></td>
    <td><span data-ttu-id="98841-280">Usuários no fluxo de trabalho atual</span><span class="sxs-lookup"><span data-stu-id="98841-280">Users in the current workflow</span></span></td>
    <td>
    <ul>
    <li><span data-ttu-id="98841-281">Depois que você selecionar <strong>Usuário de fluxo de trabalho</strong> na guia <strong>Usuário de fluxo de trabalho</strong>, na lista <strong>Usuário de fluxo de trabalho</strong>, selecione um usuário que participa do fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="98841-281">After you select <strong>Workflow user</strong>, on the <strong>Workflow user</strong> tab, in the <strong>Workflow user</strong> list, select a user who participates in the workflow.</span></span></li>
    </ul>
    </td>
    </tr>
    <tr>
    <td><span data-ttu-id="98841-282">Usuário</span><span class="sxs-lookup"><span data-stu-id="98841-282">User</span></span></td>
    <td><span data-ttu-id="98841-283">Usuários específicos</span><span class="sxs-lookup"><span data-stu-id="98841-283">Specific users</span></span></td>
    <td>
    <ol>
    <li><span data-ttu-id="98841-284">Após selecionar <strong>Usuário</strong>, clique na guia <strong>Usuário</strong>.</span><span class="sxs-lookup"><span data-stu-id="98841-284">After you select <strong>User</strong>, click the <strong>User</strong> tab.</span></span></li>
    <li><span data-ttu-id="98841-285">A lista <strong>Usuários disponíveis</strong> inclui todos os usuários.</span><span class="sxs-lookup"><span data-stu-id="98841-285">The <strong>Available users</strong> list includes all users.</span></span> <span data-ttu-id="98841-286">Selecione os usuários aos quais o documento será escalonado e mova-os para a lista <strong>Usuários selecionados</strong>.</span><span class="sxs-lookup"><span data-stu-id="98841-286">Select the users to escalate the document to, and then move those users to the <strong>Selected users</strong> list.</span></span></li>
    </ol>
    </td>
    </tr>
    </tbody>
    </table>

4. <span data-ttu-id="98841-287">Na guia **Limite de tempo**, no campo **Duração**, especifique quanto tempo o usuário tem para executar uma ação nos documentos que atingem a etapa de aprovação ou responder a eles.</span><span class="sxs-lookup"><span data-stu-id="98841-287">On the **Time limit** tab, in the **Duration** field, specify how much time the user has to take action on, or respond to, documents.</span></span> <span data-ttu-id="98841-288">Selecione uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="98841-288">Select one of the following options:</span></span>

    - <span data-ttu-id="98841-289">**Horas** – Insira o número de horas que o usuário tem para responder.</span><span class="sxs-lookup"><span data-stu-id="98841-289">**Hours** – Enter the number of hours that the user has to respond.</span></span> <span data-ttu-id="98841-290">Selecione o calendário usado pela sua organização e insira informações sobre a semana de trabalho da organização.</span><span class="sxs-lookup"><span data-stu-id="98841-290">Then select the calendar that your organization uses, and enter information about your organization's work week.</span></span>
    - <span data-ttu-id="98841-291">**Dias** – Insira o número de dias que o usuário tem para responder.</span><span class="sxs-lookup"><span data-stu-id="98841-291">**Days** – Enter the number of days that the user has to respond.</span></span> <span data-ttu-id="98841-292">Selecione o calendário usado pela sua organização e insira informações sobre a semana de trabalho da organização.</span><span class="sxs-lookup"><span data-stu-id="98841-292">Then select the calendar that your organization uses, and enter information about your organization's work week.</span></span>
    - <span data-ttu-id="98841-293">**Semanas** – Insira o número de semanas que o usuário tem para responder.</span><span class="sxs-lookup"><span data-stu-id="98841-293">**Weeks** – Enter the number of weeks that the user has to respond.</span></span>
    - <span data-ttu-id="98841-294">**Meses** – Selecione até que dia e semana o usuário deve responder.</span><span class="sxs-lookup"><span data-stu-id="98841-294">**Months** – Select the day and week that the user must respond by.</span></span> <span data-ttu-id="98841-295">Por exemplo, talvez você queira que o usuário responda até sexta-feira da terceira semana do mês.</span><span class="sxs-lookup"><span data-stu-id="98841-295">For example, you might want the user to respond by Friday of the third week of the month.</span></span>
    - <span data-ttu-id="98841-296">**Anos** – Selecione até que dia, semana e mês o usuário deve responder.</span><span class="sxs-lookup"><span data-stu-id="98841-296">**Years** – Select the day, week, and month that the user must respond by.</span></span> <span data-ttu-id="98841-297">Por exemplo, talvez você queira que o usuário responda até sexta-feira da terceira semana de dezembro.</span><span class="sxs-lookup"><span data-stu-id="98841-297">For example, you might want the user to respond by Friday of the third week of December.</span></span>

5. <span data-ttu-id="98841-298">Repita as etapas de 3 a 4 para cada usuário que deve ser adicionado ao caminho de escalonamento.</span><span class="sxs-lookup"><span data-stu-id="98841-298">Repeat steps 3 through 4 for each user that should be added to the escalation path.</span></span> <span data-ttu-id="98841-299">Você pode alterar a ordem dos usuários.</span><span class="sxs-lookup"><span data-stu-id="98841-299">You can change the order of the users.</span></span>
6. <span data-ttu-id="98841-300">Se os usuários no caminho de escalonamento não responderem no tempo alocado, o sistema executará uma ação no documento automaticamente.</span><span class="sxs-lookup"><span data-stu-id="98841-300">If the users in the escalation path don't respond in the allotted time, the system automatically take action on the document.</span></span> <span data-ttu-id="98841-301">Para especificar a ação que o sistema executará, selecione a linha **Ação** e, na guia **Encerrar ação**, selecione uma ação.</span><span class="sxs-lookup"><span data-stu-id="98841-301">To specify the action that the system takes, select the **Action** row, and then, on the **End action** tab, select an action.</span></span>
