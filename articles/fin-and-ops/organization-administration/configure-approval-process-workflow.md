---
title: "Configurar um processo de aprovação em um fluxo de trabalho"
description: "Use os procedimentos a seguir para configurar as propriedades do processo de aprovação."
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
ms.custom: 195643
ms.assetid: f853f57b-83ae-4fb0-a9fa-06ea3fc34fa1
ms.search.region: Global
ms.author: donaldc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: eedadfcbfac9d792a5ab80c1dcd8f3abfaddca08
ms.contentlocale: pt-br
ms.lasthandoff: 09/29/2017

---

# <a name="configure-an-approval-process-in-a-workflow"></a><span data-ttu-id="ca2d5-103">Configurar um processo de aprovação em um fluxo de trabalho</span><span class="sxs-lookup"><span data-stu-id="ca2d5-103">Configure an approval process in a workflow</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="ca2d5-104">Use os procedimentos a seguir para configurar as propriedades do processo de aprovação.</span><span class="sxs-lookup"><span data-stu-id="ca2d5-104">Use the following procedure to configure the properties of the approval process.</span></span>

<span data-ttu-id="ca2d5-105">Para configurar um processo de aprovação, no editor de fluxo de trabalho, clique com o botão direito do mouse no elemento de aprovação e depois clique em **Propriedades** para abrir o formulário **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="ca2d5-105">To configure an approval process, in the workflow editor, right-click the approval element, and then click **Properties** to open the **Properties** form.</span></span>
<span data-ttu-id="ca2d5-106">Nomear o processo de aprovação</span><span class="sxs-lookup"><span data-stu-id="ca2d5-106">Name the approval process</span></span>
-------------------------

<span data-ttu-id="ca2d5-107">Siga estas etapas para inserir um nome para o processo de aprovação.</span><span class="sxs-lookup"><span data-stu-id="ca2d5-107">Follow these steps to enter a name for the approval process.</span></span>
1.  <span data-ttu-id="ca2d5-108">No painel esquerdo, clique em **Configurações Básicas**.</span><span class="sxs-lookup"><span data-stu-id="ca2d5-108">In the left pane, click **Basic Settings**.</span></span>
2.  <span data-ttu-id="ca2d5-109">No campo **Nome**, insira um nome exclusivo para o processo de aprovação.</span><span class="sxs-lookup"><span data-stu-id="ca2d5-109">In the **Name** field, enter a unique name for the approval process.</span></span>

## <a name="specify-when-the-system-automatically-acts-on-the-document"></a><span data-ttu-id="ca2d5-110">Especificar quando o sistema deve executar automaticamente uma ação no documento</span><span class="sxs-lookup"><span data-stu-id="ca2d5-110">Specify when the system automatically acts on the document</span></span>
<span data-ttu-id="ca2d5-111">Você pode configurar o sistema para executar automaticamente uma ação no documento se condições específicas forem atendidas.</span><span class="sxs-lookup"><span data-stu-id="ca2d5-111">You can configure the system to automatically act on the document if specific conditions are met.</span></span> <span data-ttu-id="ca2d5-112">Por exemplo, o sistema pode aprovar os relatórios de despesas que tenham valores totais inferiores a USD 100.</span><span class="sxs-lookup"><span data-stu-id="ca2d5-112">For example, the system can approve expense reports that have total amounts that are less than USD 100.</span></span> <span data-ttu-id="ca2d5-113">Siga estas etapas para especificar quando o sistema deve executar uma ação no documento.</span><span class="sxs-lookup"><span data-stu-id="ca2d5-113">Follow these steps to specify when the system acts on the document.</span></span>
1.  <span data-ttu-id="ca2d5-114">No painel esquerdo, clique em **Ações automáticas**.</span><span class="sxs-lookup"><span data-stu-id="ca2d5-114">In the left pane, click **Automatic actions**.</span></span>
2.  <span data-ttu-id="ca2d5-115">Marque a caixa de seleção **Habilitar ações automáticas**.</span><span class="sxs-lookup"><span data-stu-id="ca2d5-115">Select the **Enable automatic actions** check box.</span></span>
3.  <span data-ttu-id="ca2d5-116">Clique em **Adicionar condição**.</span><span class="sxs-lookup"><span data-stu-id="ca2d5-116">Click **Add condition**.</span></span>
4.  <span data-ttu-id="ca2d5-117">Insira uma condição.</span><span class="sxs-lookup"><span data-stu-id="ca2d5-117">Enter a condition.</span></span>
5.  <span data-ttu-id="ca2d5-118">Insira outras condições, se necessário.</span><span class="sxs-lookup"><span data-stu-id="ca2d5-118">Enter additional conditions, if necessary.</span></span>
6.  <span data-ttu-id="ca2d5-119">Para verificar se as condições inseridas foram configuradas corretamente, execute as etapas a seguir:</span><span class="sxs-lookup"><span data-stu-id="ca2d5-119">To verify that the conditions that you entered are configured correctly, complete the following steps:</span></span>
    1.  <span data-ttu-id="ca2d5-120">Clique em **Teste** para abrir o formulário **Condição de fluxo de trabalho de teste**.</span><span class="sxs-lookup"><span data-stu-id="ca2d5-120">Click **Test** to open the **Test workflow condition** form.</span></span>
    2.  <span data-ttu-id="ca2d5-121">Selecione um registro na área **Validar condição** do formulário.</span><span class="sxs-lookup"><span data-stu-id="ca2d5-121">Select a record in the **Validate condition** area of the form.</span></span>
    3.  <span data-ttu-id="ca2d5-122">Clique em **Teste**.</span><span class="sxs-lookup"><span data-stu-id="ca2d5-122">Click **Test**.</span></span> <span data-ttu-id="ca2d5-123">O sistema avaliará o registro para determinar se ele atende às condições definidas.</span><span class="sxs-lookup"><span data-stu-id="ca2d5-123">The system evaluates the record to determine whether it meets the conditions that you defined.</span></span>
    4.  <span data-ttu-id="ca2d5-124">Clique em **OK** ou em **Cancelar** para retornar ao formulário **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="ca2d5-124">Click **OK** or **Cancel** to return to the **Properties** form.</span></span>

7.  <span data-ttu-id="ca2d5-125">Na lista **Ação de autocompletar**, selecione a ação que o sistema deve executar no documento.</span><span class="sxs-lookup"><span data-stu-id="ca2d5-125">In the **Auto complete action** list, select the action that the system should take on the document.</span></span>

## <a name="specify-when-notifications-are-sent"></a><span data-ttu-id="ca2d5-126">Especificar quando enviar notificações</span><span class="sxs-lookup"><span data-stu-id="ca2d5-126">Specify when notifications are sent</span></span>
<span data-ttu-id="ca2d5-127">Você poderá enviar notificações às pessoas quando um documento tiver sido aprovado, rejeitado, delegado ou escalonada ou quando uma alteração tiver sido solicitada.</span><span class="sxs-lookup"><span data-stu-id="ca2d5-127">You can send notifications to people when a document has been approved, rejected, delegated, or escalated, or when a change has been requested.</span></span> <span data-ttu-id="ca2d5-128">Siga estas etapas para especificar quando enviar notificações e a quem elas devem ser enviadas.</span><span class="sxs-lookup"><span data-stu-id="ca2d5-128">Follow these steps to specify when notifications are sent, and who the notifications are sent to.</span></span>
1.  <span data-ttu-id="ca2d5-129">No painel esquerdo, clique em **Notificações**.</span><span class="sxs-lookup"><span data-stu-id="ca2d5-129">In the left pane, click **Notifications**.</span></span>
2.  <span data-ttu-id="ca2d5-130">Marque a caixa de seleção ao lado dos eventos para os quais enviar notificações:</span><span class="sxs-lookup"><span data-stu-id="ca2d5-130">Select the check box next to the events to send notifications for:</span></span>
    -   <span data-ttu-id="ca2d5-131">**Delegar** – quando um documento tiver sido atribuído a outro usuário para aprovação.</span><span class="sxs-lookup"><span data-stu-id="ca2d5-131">**Delegate** – When a document has been assigned to another user for approval.</span></span>
    -   <span data-ttu-id="ca2d5-132">**Escalonar** – quando o usuário atribuído não executar uma ação em um documento no tempo alocado.</span><span class="sxs-lookup"><span data-stu-id="ca2d5-132">**Escalate** – When the assigned user has not acted on a document in the allotted time.</span></span>
    -   <span data-ttu-id="ca2d5-133">**Aprovar** – quando um documento tiver sido aprovado.</span><span class="sxs-lookup"><span data-stu-id="ca2d5-133">**Approve** – When a document has been approved.</span></span>
    -   <span data-ttu-id="ca2d5-134">**Rejeitar** – quando um documento tiver sido rejeitado.</span><span class="sxs-lookup"><span data-stu-id="ca2d5-134">**Reject** – When a document has been rejected.</span></span>
    -   <span data-ttu-id="ca2d5-135">**Solicitar alteração** – quando o usuário atribuído tiver solicitado uma alteração em um documento enviado.</span><span class="sxs-lookup"><span data-stu-id="ca2d5-135">**Request change** – When the assigned user has requested a change to a document that was submitted.</span></span>

3.  <span data-ttu-id="ca2d5-136">Selecione a linha de um evento que você selecionou na etapa 2.</span><span class="sxs-lookup"><span data-stu-id="ca2d5-136">Select the row for an event that you selected in step 2.</span></span>
4.  <span data-ttu-id="ca2d5-137">Clique na guia **Texto de Notificação**.</span><span class="sxs-lookup"><span data-stu-id="ca2d5-137">Click the **Notification text** tab.</span></span>
5.  <span data-ttu-id="ca2d5-138">Na caixa de texto, insira o texto da notificação.</span><span class="sxs-lookup"><span data-stu-id="ca2d5-138">In the text box, enter the text for the notification.</span></span>
6.  <span data-ttu-id="ca2d5-139">Para personalizar o texto, insira espaços reservados, que serão substituídos pelos dados adequados quando forem exibidos aos usuários.</span><span class="sxs-lookup"><span data-stu-id="ca2d5-139">To personalize the text, you can insert placeholders, which are replaced with the appropriate data when they are displayed to users.</span></span> <span data-ttu-id="ca2d5-140">Para inserir um espaço reservado, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="ca2d5-140">To insert a placeholder, follow these steps:</span></span>
    1.  <span data-ttu-id="ca2d5-141">Clique na caixa de texto, no local onde o espaço reservado deve aparecer.</span><span class="sxs-lookup"><span data-stu-id="ca2d5-141">Click in the text box at the location where the placeholder should appear.</span></span>
    2.  <span data-ttu-id="ca2d5-142">Clique em **Inserir espaço reservado**.</span><span class="sxs-lookup"><span data-stu-id="ca2d5-142">Click **Insert placeholder**.</span></span>
    3.  <span data-ttu-id="ca2d5-143">Na lista exibida, selecione o espaço reservado a ser inserido.</span><span class="sxs-lookup"><span data-stu-id="ca2d5-143">In the list that is displayed, select the placeholder to insert.</span></span>
    4.  <span data-ttu-id="ca2d5-144">Clique em **Inserir**.</span><span class="sxs-lookup"><span data-stu-id="ca2d5-144">Click **Insert**.</span></span>

7.  <span data-ttu-id="ca2d5-145">Para adicionar traduções da notificação, clique em **Traduções**.</span><span class="sxs-lookup"><span data-stu-id="ca2d5-145">To add translations of the notification, click **Translations**.</span></span> <span data-ttu-id="ca2d5-146">No formulário que é exibido, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="ca2d5-146">In the form that is displayed, follow these steps:</span></span>
    1.  <span data-ttu-id="ca2d5-147">Clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="ca2d5-147">Click **Add**.</span></span>
    2.  <span data-ttu-id="ca2d5-148">Na lista exibida, selecione o idioma no qual o texto será inserido.</span><span class="sxs-lookup"><span data-stu-id="ca2d5-148">In the list that is displayed, select the language in which you will enter the text.</span></span>
    3.  <span data-ttu-id="ca2d5-149">Na caixa de texto **Texto traduzido**, insira o texto.</span><span class="sxs-lookup"><span data-stu-id="ca2d5-149">In the **Translated text** text box, enter the text.</span></span>
    4.  <span data-ttu-id="ca2d5-150">Para personalizar o texto, insira espaços reservados.</span><span class="sxs-lookup"><span data-stu-id="ca2d5-150">To personalize the text, insert placeholders.</span></span>
    5.  <span data-ttu-id="ca2d5-151">Clique em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="ca2d5-151">Click **Close**.</span></span>

8.  <span data-ttu-id="ca2d5-152">Clique na guia **Destinatário**.</span><span class="sxs-lookup"><span data-stu-id="ca2d5-152">Click the **Recipient** tab.</span></span>
9.  <span data-ttu-id="ca2d5-153">Especifique a quem as notificações serão enviadas.</span><span class="sxs-lookup"><span data-stu-id="ca2d5-153">Specify who the notifications are sent to.</span></span> <span data-ttu-id="ca2d5-154">Selecione uma das opções na tabela a seguir e execute as etapas adicionais para a opção antes de ir para a etapa 10.</span><span class="sxs-lookup"><span data-stu-id="ca2d5-154">Select one of the options in the following table, and then follow the additional steps for the option before you go to step 10.</span></span>

    <table>
    <colgroup>
    <col width="33%" />
    <col width="33%" />
    <col width="33%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="ca2d5-155">Opção</span><span class="sxs-lookup"><span data-stu-id="ca2d5-155">Option</span></span></th>
    <th><span data-ttu-id="ca2d5-156">Destinatários da notificação</span><span class="sxs-lookup"><span data-stu-id="ca2d5-156">Notification recipients</span></span></th>
    <th><span data-ttu-id="ca2d5-157">Etapas adicionais</span><span class="sxs-lookup"><span data-stu-id="ca2d5-157">Additional steps</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><span data-ttu-id="ca2d5-158"><strong>Participante</strong></span><span class="sxs-lookup"><span data-stu-id="ca2d5-158"><strong>Participant</strong></span></span></td>
    <td><span data-ttu-id="ca2d5-159">Usuários que foram atribuídos a uma função ou um grupo específico</span><span class="sxs-lookup"><span data-stu-id="ca2d5-159">Users who are assigned to a specific group or role</span></span></td>
    <td><ol>
    <li><span data-ttu-id="ca2d5-160">Após selecionar <strong>Participante</strong>, clique na guia <strong>Função baseada</strong>.</span><span class="sxs-lookup"><span data-stu-id="ca2d5-160">After you select <strong>Participant</strong>, click the <strong>Role based</strong> tab.</span></span></li>
    <li><span data-ttu-id="ca2d5-161">Na lista <strong>Tipo de Participante</strong>, selecione o tipo de grupo ou a função ao qual serão enviadas notificações.</span><span class="sxs-lookup"><span data-stu-id="ca2d5-161">In the <strong>Type of participant</strong> list, select the type of group or role to send notifications to.</span></span></li>
    <li><span data-ttu-id="ca2d5-162">Na lista <strong>Participante</strong>, selecione o grupo ou a função ao qual serão enviadas notificações.</span><span class="sxs-lookup"><span data-stu-id="ca2d5-162">In the <strong>Participant</strong> list, select the group or role to send notifications to.</span></span></li>
    </ol></td>
    </tr>
    <tr class="even">
    <td><span data-ttu-id="ca2d5-163"><strong>Usuário de fluxo de trabalho</strong></span><span class="sxs-lookup"><span data-stu-id="ca2d5-163"><strong>Workflow user</strong></span></span></td>
    <td><span data-ttu-id="ca2d5-164">Usuários que participam do fluxo de trabalho atual</span><span class="sxs-lookup"><span data-stu-id="ca2d5-164">Users who participate in the current workflow</span></span></td>
    <td><ol>
    <li><span data-ttu-id="ca2d5-165">Após selecionar <strong>Usuário de fluxo de trabalho</strong>, clique na guia <strong>Usuário de fluxo de trabalho</strong>.</span><span class="sxs-lookup"><span data-stu-id="ca2d5-165">After you select <strong>Workflow user</strong>, click the <strong>Workflow user</strong> tab.</span></span></li>
    <li><span data-ttu-id="ca2d5-166">Na lista <strong>Usuário de fluxo de trabalho</strong>, selecione um usuário que participa do fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="ca2d5-166">In the <strong>Workflow user</strong> list, select a user who participates in the workflow.</span></span></li>
    </ol></td>
    </tr>
    <tr class="odd">
    <td><span data-ttu-id="ca2d5-167"><strong>Usuário</strong></span><span class="sxs-lookup"><span data-stu-id="ca2d5-167"><strong>User</strong></span></span></td>
    <td><span data-ttu-id="ca2d5-168">Especificar usuários do Microsoft Dynamics 365 for Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="ca2d5-168">Specific Microsoft Dynamics 365 for Finance and Operations users</span></span></td>
    <td><ol>
    <li><span data-ttu-id="ca2d5-169">Após selecionar <strong>Usuário</strong>, clique na guia <strong>Usuário</strong>.</span><span class="sxs-lookup"><span data-stu-id="ca2d5-169">After you select <strong>User</strong>, click the <strong>User</strong> tab.</span></span></li>
    <li><span data-ttu-id="ca2d5-170">A lista <strong>Usuários disponíveis</strong>: inclui todos os usuários do Microsoft Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="ca2d5-170">The <strong>Available users</strong>: list includes all Microsoft Dynamics 365 for Finance and Operations users.</span></span> <span data-ttu-id="ca2d5-171">Selecione os usuários aos quais enviar notificações e mova- os para a lista: <strong>Usuários selecionados</strong>.</span><span class="sxs-lookup"><span data-stu-id="ca2d5-171">Select the users to send notifications to, and then move these users to the <strong>Selected users</strong>: list.</span></span></li>
    </ol></td>
    </tr>
    </tbody>
    </table>

10. <span data-ttu-id="ca2d5-172">Repita as etapas de 3 a 9 para cada evento selecionado na etapa 2.</span><span class="sxs-lookup"><span data-stu-id="ca2d5-172">Repeat steps 3 through 9 for each event that you selected in step 2.</span></span>

## <a name="specify-a-final-approver"></a><span data-ttu-id="ca2d5-173">Especificar um aprovador final</span><span class="sxs-lookup"><span data-stu-id="ca2d5-173">Specify a final approver</span></span>
<span data-ttu-id="ca2d5-174">Você pode designar um aprovador final para cenários nos quais o aprovador for a pessoa que enviou o documento para aprovação.</span><span class="sxs-lookup"><span data-stu-id="ca2d5-174">You may want to designate a final approver for scenarios where the approver is the person who submitted the document for approval.</span></span> <span data-ttu-id="ca2d5-175">Siga estas etapas para especificar um aprovador final.</span><span class="sxs-lookup"><span data-stu-id="ca2d5-175">Follow these steps to specify a final approver.</span></span>
1.  <span data-ttu-id="ca2d5-176">No painel esquerdo, clique em **Configurações avançadas**.</span><span class="sxs-lookup"><span data-stu-id="ca2d5-176">In the left pane, click **Advanced settings**.</span></span>
2.  <span data-ttu-id="ca2d5-177">Marque a caixa de seleção **Usar aprovador final**.</span><span class="sxs-lookup"><span data-stu-id="ca2d5-177">Select the **Use final approver** check box.</span></span>
3.  <span data-ttu-id="ca2d5-178">Na lista, selecione o usuário que será o aprovador final.</span><span class="sxs-lookup"><span data-stu-id="ca2d5-178">In the list, select the user to be the final approver.</span></span>

## <a name="set-a-time-limit"></a><span data-ttu-id="ca2d5-179">Definir um limite de tempo</span><span class="sxs-lookup"><span data-stu-id="ca2d5-179">Set a time limit</span></span>
<span data-ttu-id="ca2d5-180">Siga estas etapas se o processo de aprovação tiver que ser concluído em um horário específico.</span><span class="sxs-lookup"><span data-stu-id="ca2d5-180">Follow these steps if the approval process must be completed in a specific time.</span></span>
| <span data-ttu-id="ca2d5-181">**Nota**</span><span class="sxs-lookup"><span data-stu-id="ca2d5-181">**Note**</span></span>                                                                                                                                                |
|---------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="ca2d5-182">As opções selecionadas aqui substituirão as que você selecionar nas guias **Atribuição** e **Escalonamento** de cada etapa de aprovação.</span><span class="sxs-lookup"><span data-stu-id="ca2d5-182">The options that you select in these steps override the options that you selected in the **Assignment** and **Escalation** areas of each approval step.</span></span> |

1.  <span data-ttu-id="ca2d5-183">No painel esquerdo, clique em **Configurações avançadas**.</span><span class="sxs-lookup"><span data-stu-id="ca2d5-183">In the left pane, click **Advanced settings**.</span></span>
2.  <span data-ttu-id="ca2d5-184">Marque a caixa de seleção **Definir um limite de tempo para o** **elemento de fluxo de trabalho**.</span><span class="sxs-lookup"><span data-stu-id="ca2d5-184">Select the **Set a time limit for the workflow** **element** check box.</span></span>
3.  <span data-ttu-id="ca2d5-185">No campo **Duração**, especifique quando o processo de aprovação deve ser concluído.</span><span class="sxs-lookup"><span data-stu-id="ca2d5-185">In the **Duration** field, specify when the approval process must be completed.</span></span> <span data-ttu-id="ca2d5-186">Selecione uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="ca2d5-186">Select one of the following options:</span></span>
    -   <span data-ttu-id="ca2d5-187">**Horas** – insira o número de horas em que o processo de aprovação deve ser concluído.</span><span class="sxs-lookup"><span data-stu-id="ca2d5-187">**Hours** – Enter the number of hours in which the approval process must be completed.</span></span> <span data-ttu-id="ca2d5-188">Selecione o calendário usado pela sua organização e insira informações sobre a semana de trabalho da organização.</span><span class="sxs-lookup"><span data-stu-id="ca2d5-188">Then select the calendar that your organization uses, and enter information about your organization's work week.</span></span>
    -   <span data-ttu-id="ca2d5-189">**Dias** – insira o número de dias em que o processo de aprovação deve ser concluído.</span><span class="sxs-lookup"><span data-stu-id="ca2d5-189">**Days** – Enter the number of days in which the approval process must be completed.</span></span> <span data-ttu-id="ca2d5-190">Selecione o calendário usado pela sua organização e insira informações sobre a semana de trabalho da organização.</span><span class="sxs-lookup"><span data-stu-id="ca2d5-190">Then select the calendar that your organization uses, and enter information about your organization's work week.</span></span>
    -   <span data-ttu-id="ca2d5-191">**Semanas** – insira o número de semanas em que o processo de aprovação deve ser concluído.</span><span class="sxs-lookup"><span data-stu-id="ca2d5-191">**Weeks** – Enter the number of weeks in which the approval process must be completed.</span></span>
    -   <span data-ttu-id="ca2d5-192">**Meses** – selecione o dia, a semana e o mês de limite para a conclusão do processo de aprovação.</span><span class="sxs-lookup"><span data-stu-id="ca2d5-192">**Months** – Select the day and week by which the approval process must be completed.</span></span> <span data-ttu-id="ca2d5-193">Por exemplo, você pode querer que o processo seja concluído até sexta-feira da terceira semana do mês.</span><span class="sxs-lookup"><span data-stu-id="ca2d5-193">For example, you may want the approval process to be completed by Friday of the third week of the month.</span></span>
    -   <span data-ttu-id="ca2d5-194">**Anos** – selecione o dia, a semana e o mês de limite para a conclusão do processo de aprovação.</span><span class="sxs-lookup"><span data-stu-id="ca2d5-194">**Years** – Select the day, week, and month by which the approval process must be completed.</span></span> <span data-ttu-id="ca2d5-195">Por exemplo, você pode querer que o processo seja concluído até a sexta-feira da terceira semana de dezembro.</span><span class="sxs-lookup"><span data-stu-id="ca2d5-195">For example, you may want the approval process to be completed by Friday of the third week of December.</span></span>

4.  <span data-ttu-id="ca2d5-196">Se o limite de tempo for excedido, o sistema executará uma ação no documento.</span><span class="sxs-lookup"><span data-stu-id="ca2d5-196">If the time limit is exceeded, the system acts on the document.</span></span> <span data-ttu-id="ca2d5-197">Na lista **Ação**, selecione a ação que o sistema deve executar.</span><span class="sxs-lookup"><span data-stu-id="ca2d5-197">In the **Action** list, select the action that the system should take.</span></span>

## <a name="specify-which-actions-are-available-to-the-user"></a><span data-ttu-id="ca2d5-198">Especificar quais ações estarão disponíveis para o usuário</span><span class="sxs-lookup"><span data-stu-id="ca2d5-198">Specify which actions are available to the user</span></span>
<span data-ttu-id="ca2d5-199">Quando um documento for atribuído a um usuário para aprovação, o usuário deverá executar uma ação no documento.</span><span class="sxs-lookup"><span data-stu-id="ca2d5-199">When a document is assigned to a user for approval, the user must act on the document.</span></span> <span data-ttu-id="ca2d5-200">Siga estas etapas para especificar quais as ações o usuário poderá executar no documento enviado.</span><span class="sxs-lookup"><span data-stu-id="ca2d5-200">Follows these steps to specify which actions the user can take on the document that was submitted.</span></span>
1.  <span data-ttu-id="ca2d5-201">No painel esquerdo, clique em **Configurações avançadas**.</span><span class="sxs-lookup"><span data-stu-id="ca2d5-201">In the left pane, click **Advanced settings**.</span></span>
2.  <span data-ttu-id="ca2d5-202">Marque a caixa de seleção **Aprovar** se o usuário puder aprovar o documento.</span><span class="sxs-lookup"><span data-stu-id="ca2d5-202">Select the **Approve** check box if the user can approve the document.</span></span>
3.  <span data-ttu-id="ca2d5-203">Marque a caixa de seleção **Rejeitar** se o usuário puder rejeitar o documento.</span><span class="sxs-lookup"><span data-stu-id="ca2d5-203">Select the **Reject** check box the user can reject the document.</span></span>
4.  <span data-ttu-id="ca2d5-204">Marque a caixa de seleção **Solicitar alteração** se o usuário puder solicitar alterações no documento.</span><span class="sxs-lookup"><span data-stu-id="ca2d5-204">Select the **Request change** check box the user can request changes to the document.</span></span>
5.  <span data-ttu-id="ca2d5-205">Marque a caixa de seleção **Delegar** se o usuário puder atribuir o documento a outro usuário para aprovação.</span><span class="sxs-lookup"><span data-stu-id="ca2d5-205">Select the **Delegate** check box if the user can assign the document to another user for approval.</span></span>

<span data-ttu-id="ca2d5-206">**Nota**: **Habilitar ações de lista de trabalho no portal empresarial** A caixa de seleção foi substituído.</span><span class="sxs-lookup"><span data-stu-id="ca2d5-206">**Note**: The **Enable actions from the work list in Enterprise Portal** check box has been deprecated.</span></span>

## <a name="configure-the-approval-steps"></a><span data-ttu-id="ca2d5-207">Configurar as etapas de aprovação</span><span class="sxs-lookup"><span data-stu-id="ca2d5-207">Configure the approval steps</span></span>
<span data-ttu-id="ca2d5-208">Um processo de aprovação consiste em etapas de aprovação.</span><span class="sxs-lookup"><span data-stu-id="ca2d5-208">An approval process consists of approval steps.</span></span> <span data-ttu-id="ca2d5-209">Conclua o procedimento a seguir para adicionar etapas ao processo de aprovação e configurar as etapas.</span><span class="sxs-lookup"><span data-stu-id="ca2d5-209">Complete the following procedure to add steps the approval process and configure the steps.</span></span>
1.  <span data-ttu-id="ca2d5-210">No editor de fluxo de trabalho, clique duas vezes no processo de aprovação.</span><span class="sxs-lookup"><span data-stu-id="ca2d5-210">In the workflow editor, double-click the approval process.</span></span> <span data-ttu-id="ca2d5-211">O editor de fluxo de trabalho exibe as etapas do processo de aprovação.</span><span class="sxs-lookup"><span data-stu-id="ca2d5-211">The workflow editor displays the steps of the approval process.</span></span>
2.  <span data-ttu-id="ca2d5-212">Para adicionar uma etapa de aprovação, arraste-a da área **Elementos de fluxo de trabalho** para a tela.</span><span class="sxs-lookup"><span data-stu-id="ca2d5-212">To add an approval step, drag the step from the **Workflow elements** area to the canvas.</span></span>
3.  <span data-ttu-id="ca2d5-213">Para configurar uma etapa de aprovação, consulte [Configurar uma etapa de aprovação](configure-approval-step-workflow.md).</span><span class="sxs-lookup"><span data-stu-id="ca2d5-213">To configure an approval step, see [Configure an approval step](configure-approval-step-workflow.md).</span></span>






