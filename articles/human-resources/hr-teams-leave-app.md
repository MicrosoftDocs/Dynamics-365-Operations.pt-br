---
title: Gerenciar solicitações de licença no Teams
description: Este tópico mostra como solicitar licenças no aplicativo do Dynamics 365 Human Resources no Microsoft Teams.
author: andreabichsel
manager: tfehr
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: LeaveAbsenceWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-05-18
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 342106ad09db3a5d9c2dec8ab18e824d70e0f6bf
ms.sourcegitcommit: f8bac7ca2803913fd236adbc3806259a17a110f4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2021
ms.locfileid: "5128152"
---
# <a name="manage-leave-requests-in-teams"></a><span data-ttu-id="ed1e2-103">Gerenciar solicitações de licença no Teams</span><span class="sxs-lookup"><span data-stu-id="ed1e2-103">Manage leave requests in Teams</span></span>

[!include [banner](includes/preview-feature.md)]

<span data-ttu-id="ed1e2-104">O aplicativo Microsoft Dynamics 365 Human Resources no Microsoft Teams permite solicitar folgas rapidamente, além de visualizar as informações de saldo de folgas no Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="ed1e2-104">The Microsoft Dynamics 365 Human Resources app in Microsoft Teams lets you quickly request time off and view your time-off balance information right in Microsoft Teams.</span></span> <span data-ttu-id="ed1e2-105">Você pode interagir com um bot para solicitar informações e iniciar uma solicitação de licença.</span><span class="sxs-lookup"><span data-stu-id="ed1e2-105">You can interact with a bot to request information and start a leave request.</span></span> <span data-ttu-id="ed1e2-106">A guia **Folga** fornece informações mais detalhadas.</span><span class="sxs-lookup"><span data-stu-id="ed1e2-106">The **Time off** tab provides more detailed information.</span></span> <span data-ttu-id="ed1e2-107">Você também pode enviar às pessoas informações sobre as próximas folgas em equipes e chats fora do aplicativo Human Resources.</span><span class="sxs-lookup"><span data-stu-id="ed1e2-107">You can also send people information about your upcoming time off in teams and chats outside the Human Resources app.</span></span>

## <a name="install-the-app"></a><span data-ttu-id="ed1e2-108">Instalar o aplicativo</span><span class="sxs-lookup"><span data-stu-id="ed1e2-108">Install the app</span></span>

<span data-ttu-id="ed1e2-109">Você pode encontrar o aplicativo Human Resources na loja do Teams.</span><span class="sxs-lookup"><span data-stu-id="ed1e2-109">You can find the Human Resources app in the Teams store.</span></span>

1. <span data-ttu-id="ed1e2-110">No Microsoft Teams, selecione as reticências.</span><span class="sxs-lookup"><span data-stu-id="ed1e2-110">In Microsoft Teams, select the ellipses.</span></span>

   ![Reticências do aplicativo de licença do Human Resources Teams](./media/hr-teams-leave-app-ellipses.png)
 
2. <span data-ttu-id="ed1e2-112">Procure Dynamics 365 Human Resources, e selecione o título **Human Resources**.</span><span class="sxs-lookup"><span data-stu-id="ed1e2-112">Search for Dynamics 365 Human Resources, and then select the **Human Resources** tile.</span></span>

   ![Título do HR do aplicativo de licença do Human Resources Teams](./media/hr-teams-leave-app-human-resources-tile.png)

3. <span data-ttu-id="ed1e2-114">Selecione o botão **Adicionar** para instalar o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="ed1e2-114">Select the **Add** button to install the app.</span></span>

   ![Instalar o aplicativo de licença do Human Resources Teams](./media/hr-teams-leave-app-in-store.png)

<span data-ttu-id="ed1e2-116">Se o aplicativo não fizer logon automaticamente, selecione a guia **Configurações** para entrar.</span><span class="sxs-lookup"><span data-stu-id="ed1e2-116">If the app doesn't automatically sign you in, select the **Settings** tab to sign in.</span></span>

![Guia Configurações do aplicativo de licença do Human Resources Teams](./media/hr-teams-leave-app-settings-tab.png)

> [!NOTE]
> <span data-ttu-id="ed1e2-118">Caso você não veja uma caixa de diálogo de entrada, verifique as configurações do navegador para permitir janelas pop-up.</span><span class="sxs-lookup"><span data-stu-id="ed1e2-118">If you don’t see a sign-in dialog box, check your browser settings to allow pop-ups.</span></span> 

<span data-ttu-id="ed1e2-119">Se você tiver acesso a mais de uma instância do Human Resources, poderá selecionar a qual ambiente deseja se conectar na guia **Configurações**.</span><span class="sxs-lookup"><span data-stu-id="ed1e2-119">If you have access to more than one instance of Human Resources, you can select which environment you want to connect to in the **Settings** tab.</span></span>

> [!NOTE]
> <span data-ttu-id="ed1e2-120">O aplicativo agora oferece suporte à função de segurança Administrador do sistema.</span><span class="sxs-lookup"><span data-stu-id="ed1e2-120">The app now supports the System Administrator security role.</span></span>
 
## <a name="use-the-bot"></a><span data-ttu-id="ed1e2-121">Usar o bot</span><span class="sxs-lookup"><span data-stu-id="ed1e2-121">Use the bot</span></span>

<span data-ttu-id="ed1e2-122">Depois de instalar o aplicativo, será exibida uma mensagem de boas-vindas, informando os tipos de ações que o bot pode assumir em seu nome.</span><span class="sxs-lookup"><span data-stu-id="ed1e2-122">After the app installs, a welcome message appears, letting you know the types of actions the bot can take on your behalf.</span></span>

![Mensagem de boas-vindas do bot do aplicativo de licença do Human Resources Teams](./media/hr-teams-leave-app-bot.png)
 
> [!NOTE]
> <span data-ttu-id="ed1e2-124">Talvez você precise entrar na primeira interação com o bot.</span><span class="sxs-lookup"><span data-stu-id="ed1e2-124">When first interacting with the bot, you might need to sign in.</span></span> <span data-ttu-id="ed1e2-125">Caso você não veja uma caixa de diálogo de entrada, verifique as configurações do navegador para permitir janelas pop-up.</span><span class="sxs-lookup"><span data-stu-id="ed1e2-125">If you don’t see a sign-in dialog box, check your browser settings to allow pop-ups.</span></span>

<span data-ttu-id="ed1e2-126">Você pode pedir para o bot:</span><span class="sxs-lookup"><span data-stu-id="ed1e2-126">You can ask the bot to:</span></span>

- <span data-ttu-id="ed1e2-127">Mostrar informações do saldo de folgas para cada tipo de licença na qual você está inscrito.</span><span class="sxs-lookup"><span data-stu-id="ed1e2-127">Show time-off balance information for each leave type you're enrolled in.</span></span>

   ![Mostrar saldos do aplicativo de licença do Human Resources Teams](./media/hr-teams-leave-app-bot-balances.png)
 
- <span data-ttu-id="ed1e2-129">Mostrar detalhes adicionais sobre um tipo de licença específico.</span><span class="sxs-lookup"><span data-stu-id="ed1e2-129">Show additional details about a specific leave type.</span></span>

   ![Mostrar detalhes do aplicativo de licença do Human Resources Teams](./media/hr-teams-leave-app-bot-details.png)

- <span data-ttu-id="ed1e2-131">Iniciar uma solicitação de licença para você.</span><span class="sxs-lookup"><span data-stu-id="ed1e2-131">Start a leave request for you.</span></span>

   ![Solicitar licença no aplicativo de licença do Human Resources Teams](./media/hr-teams-leave-app-bot-request.png)
 
<span data-ttu-id="ed1e2-133">Depois de iniciar uma solicitação de licença, você pode ajustar os dias diretamente no cartão.</span><span class="sxs-lookup"><span data-stu-id="ed1e2-133">After you start a leave request, you can adjust the days right within the card.</span></span>

![Editar solicitação no aplicativo de licença do Human Resources Teams](./media/hr-teams-leave-app-bot-edit.png)
 
<span data-ttu-id="ed1e2-135">Após inserir as informações, selecione **Enviar** para enviá-las para aprovação.</span><span class="sxs-lookup"><span data-stu-id="ed1e2-135">When you're done entering information, select **Submit** to submit it for approval.</span></span> <span data-ttu-id="ed1e2-136">Você também pode selecionar **Salvar como rascunho** para continuar depois.</span><span class="sxs-lookup"><span data-stu-id="ed1e2-136">You can also select **Save as draft** to come back to it later.</span></span>

![Enviar solicitação no aplicativo de licença do Human Resources Teams](./media/hr-teams-leave-app-bot-submit.png)

## <a name="manage-your-leave-in-teams"></a><span data-ttu-id="ed1e2-138">Gerenciar a sua licença no Teams</span><span class="sxs-lookup"><span data-stu-id="ed1e2-138">Manage your leave in Teams</span></span>

<span data-ttu-id="ed1e2-139">A guia **Folga** permite exibir:</span><span class="sxs-lookup"><span data-stu-id="ed1e2-139">The **Time off** tab allows you to view:</span></span>

- <span data-ttu-id="ed1e2-140">Informações do saldo para cada tipo de licença na qual você está inscrito</span><span class="sxs-lookup"><span data-stu-id="ed1e2-140">Balance information for each leave type you're enrolled in</span></span>

- <span data-ttu-id="ed1e2-141">Solicitações de licença futuras</span><span class="sxs-lookup"><span data-stu-id="ed1e2-141">Upcoming leave requests</span></span>

- <span data-ttu-id="ed1e2-142">Solicitações de folga</span><span class="sxs-lookup"><span data-stu-id="ed1e2-142">Time-off requests</span></span>

- <span data-ttu-id="ed1e2-143">Rascunho de solicitações de licença</span><span class="sxs-lookup"><span data-stu-id="ed1e2-143">Draft leave requests</span></span>

![Guia Folga do aplicativo de licença do Human Resources Teams](./media/hr-teams-leave-app-timeoff-tab.png)
 
### <a name="create-a-new-request"></a><span data-ttu-id="ed1e2-145">Criar uma solicitação</span><span class="sxs-lookup"><span data-stu-id="ed1e2-145">Create a new request</span></span>

1. <span data-ttu-id="ed1e2-146">Para criar uma solicitação de licença, selecione **Nova solicitação**.</span><span class="sxs-lookup"><span data-stu-id="ed1e2-146">To create a new leave request, select **New request**.</span></span>

   ![Nova solicitação no aplicativo de licença do Human Resources Teams](./media/hr-teams-leave-app-timeoff-tab-new.png)

2. <span data-ttu-id="ed1e2-148">Insira os dias que você deseja solicitar folga e depois selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="ed1e2-148">Enter the day or days you want to take off, and then select **Add**.</span></span>

   ![Adicionar folga no aplicativo de licença do Human Resources Teams](./media/hr-teams-leave-app-timeoff-tab-add.png)

3. <span data-ttu-id="ed1e2-150">Se aplicável, insira um código de motivo.</span><span class="sxs-lookup"><span data-stu-id="ed1e2-150">If applicable, enter a reason code.</span></span> <span data-ttu-id="ed1e2-151">Insira também comentários e adicione anexos.</span><span class="sxs-lookup"><span data-stu-id="ed1e2-151">Also enter any comments and add any attachments.</span></span>

4. <span data-ttu-id="ed1e2-152">Após inserir as informações, digite **Enviar** para enviá-la para aprovação.</span><span class="sxs-lookup"><span data-stu-id="ed1e2-152">When you're done entering information, type **Submit** to submit it for approval.</span></span> <span data-ttu-id="ed1e2-153">Você também pode digitar **Salvar como rascunho** para continuar depois.</span><span class="sxs-lookup"><span data-stu-id="ed1e2-153">You can also type **Save as draft** to come back to it later.</span></span>

### <a name="manage-draft-requests"></a><span data-ttu-id="ed1e2-154">Gerenciar solicitações em rascunho</span><span class="sxs-lookup"><span data-stu-id="ed1e2-154">Manage draft requests</span></span>

1. <span data-ttu-id="ed1e2-155">Selecione a guia **Rascunhos**.</span><span class="sxs-lookup"><span data-stu-id="ed1e2-155">Select the **Drafts** tab.</span></span>

   ![Guia Rascunhos do aplicativo de licença do Human Resources Teams](./media/hr-teams-leave-app-drafts-tab.png)

2. <span data-ttu-id="ed1e2-157">Selecione o lápis para editar a solicitação, ou selecione a lixeira para excluí-la.</span><span class="sxs-lookup"><span data-stu-id="ed1e2-157">Select the pencil to edit the request, or select the trash can to delete the request.</span></span>

3. <span data-ttu-id="ed1e2-158">Faça todas as alterações necessárias.</span><span class="sxs-lookup"><span data-stu-id="ed1e2-158">Make any necessary changes.</span></span> <span data-ttu-id="ed1e2-159">Após inserir as informações, digite **Enviar** para enviá-la para aprovação.</span><span class="sxs-lookup"><span data-stu-id="ed1e2-159">When you're done entering information, type **Submit** to submit it for approval.</span></span> <span data-ttu-id="ed1e2-160">Você também pode selecionar **Salvar como rascunho** para continuar depois.</span><span class="sxs-lookup"><span data-stu-id="ed1e2-160">You can also select **Save as draft** to come back to it later.</span></span>

   ![Editar rascunho no aplicativo de licença do Human Resources Teams](./media/hr-teams-leave-app-drafts-edit.png)
   
### <a name="respond-to-teams-notifications"></a><span data-ttu-id="ed1e2-162">Responder a notificações do Teams</span><span class="sxs-lookup"><span data-stu-id="ed1e2-162">Respond to Teams notifications</span></span>

<span data-ttu-id="ed1e2-163">Quando você ou um trabalhador para o qual você é um aprovador enviar uma solicitação de licença, você receberá uma notificação no aplicativo Human Resources no Teams.</span><span class="sxs-lookup"><span data-stu-id="ed1e2-163">When you or a worker you're an approver for submits a leave request, you'll receive a notification in the Human Resources app in Teams.</span></span> <span data-ttu-id="ed1e2-164">Você pode selecionar a notificação para exibi-la.</span><span class="sxs-lookup"><span data-stu-id="ed1e2-164">You can select the notification to view it.</span></span> <span data-ttu-id="ed1e2-165">As notificações também aparecem na área **Chat** .</span><span class="sxs-lookup"><span data-stu-id="ed1e2-165">Notifications also appear in the **Chat** area.</span></span>

<span data-ttu-id="ed1e2-166">Se você for aprovador, poderá selecionar **Aprovar** ou **Negar** na notificação.</span><span class="sxs-lookup"><span data-stu-id="ed1e2-166">If you're an approver, you can select **Approve** or **Deny** in the notification.</span></span> <span data-ttu-id="ed1e2-167">Você também pode fornecer uma mensagem opcional.</span><span class="sxs-lookup"><span data-stu-id="ed1e2-167">You can also provide an optional message.</span></span>

![Deixar uma notificação de solicitação no aplicativo Human Resources no Teams](./media/hr-teams-leave-app-notification.png)

## <a name="send-upcoming-time-off-information-to-your-coworkers"></a><span data-ttu-id="ed1e2-169">Enviar informações sobre as próximas folgas para seus colegas de trabalho</span><span class="sxs-lookup"><span data-stu-id="ed1e2-169">Send upcoming time-off information to your coworkers</span></span>

<span data-ttu-id="ed1e2-170">Depois de instalar o aplicativo Human Resources para o Teams, você pode enviar facilmente informações sobre sua próxima folga para seus colegas de trabalho em equipes ou bate-papos.</span><span class="sxs-lookup"><span data-stu-id="ed1e2-170">After you install the Human Resources app for Teams, you can easily send information about your upcoming time off to your coworkers in teams or chats.</span></span>

1. <span data-ttu-id="ed1e2-171">Em uma equipe ou chat no Teams, selecione o botão do Human Resources abaixo da janela de chat.</span><span class="sxs-lookup"><span data-stu-id="ed1e2-171">In a team or chat in Teams, select the Human Resources button below the chat window.</span></span>

   ![Botão do Human Resources abaixo da janela de bate-papo](./media/hr-teams-leave-app-chat-button.png)

2. <span data-ttu-id="ed1e2-173">Selecione a solicitação de licença que deseja compartilhar.</span><span class="sxs-lookup"><span data-stu-id="ed1e2-173">Select the leave request you want to share.</span></span> <span data-ttu-id="ed1e2-174">Se você deseja compartilhar um rascunho de solicitação de licença, selecione **Rascunhos** primeiro.</span><span class="sxs-lookup"><span data-stu-id="ed1e2-174">If you want to share a draft leave request, select **Drafts** first.</span></span>

   ![Selecionar uma próxima solicitação de licença para compartilhar](./media/hr-teams-leave-app-chat-search.png)

<span data-ttu-id="ed1e2-176">Sua solicitação de licença será exibida no chat.</span><span class="sxs-lookup"><span data-stu-id="ed1e2-176">Your leave request will display in the chat.</span></span>

![Cartão de solicitação de licença do Human Resources](./media/hr-teams-leave-app-chat-card.png)

<span data-ttu-id="ed1e2-178">Se você compartilhou uma solicitação de rascunho, ela será exibida como rascunho:</span><span class="sxs-lookup"><span data-stu-id="ed1e2-178">If you shared a draft request, it will display as a draft:</span></span>

![Rascunho do cartão de solicitação de licença do Human Resources](./media/hr-teams-leave-app-chat-draft-card.png)

## <a name="view-your-teams-leave-calendar"></a><span data-ttu-id="ed1e2-180">Exibir o calendário de licença da equipe</span><span class="sxs-lookup"><span data-stu-id="ed1e2-180">View your team's leave calendar</span></span>

<span data-ttu-id="ed1e2-181">Se você for um gerente com subordinados diretos, poderá exibir folgas aprovadas e pendentes da sua equipe.</span><span class="sxs-lookup"><span data-stu-id="ed1e2-181">If you're a manager with direct reports, you can view your team's approved and pending time off.</span></span>

1. <span data-ttu-id="ed1e2-182">No aplicativo Human Resources no Teams, selecione **Folga** .</span><span class="sxs-lookup"><span data-stu-id="ed1e2-182">In the Human Resources app in Teams, select **Time off**.</span></span>

2. <span data-ttu-id="ed1e2-183">Selecione **Calendário da equipe** .</span><span class="sxs-lookup"><span data-stu-id="ed1e2-183">Select **Team calendar**.</span></span>

   ![Exibir calendário no aplicativo Human Resources do Teams](./media/hr-teams-leave-app-view-calendar.png)

<span data-ttu-id="ed1e2-185">O calendário exibe as folgas aprovadas e pendentes dos subordinados diretos.</span><span class="sxs-lookup"><span data-stu-id="ed1e2-185">The calendar displays your direct reports' approved and pending time off.</span></span>

![Calendário de folgas no aplicativo Human Resources do Teams](./media/hr-teams-leave-app-calendar.png)

## <a name="troubleshooting"></a><span data-ttu-id="ed1e2-187">Solução de problemas</span><span class="sxs-lookup"><span data-stu-id="ed1e2-187">Troubleshooting</span></span>

<span data-ttu-id="ed1e2-188">Se você tiver problemas para entrar ou ao usar o aplicativo do Human Resources no Teams, tente seguir estas instruções de solução de problemas.</span><span class="sxs-lookup"><span data-stu-id="ed1e2-188">If you're having trouble signing into or using the Human Resources Teams app, try following these troubleshooting instructions.</span></span> <span data-ttu-id="ed1e2-189">Se você ainda tiver problemas após a solução de problemas, contate o Suporte.</span><span class="sxs-lookup"><span data-stu-id="ed1e2-189">If you're still having problems after troubleshooting, contact Support.</span></span> <span data-ttu-id="ed1e2-190">Para obter mais informações, consulte [Obter suporte](hr-admin-troubleshooting-support.md).</span><span class="sxs-lookup"><span data-stu-id="ed1e2-190">For more information, see [Get support](hr-admin-troubleshooting-support.md).</span></span>

### <a name="cant-sign-into-the-human-resources-app-in-teams"></a><span data-ttu-id="ed1e2-191">Não é possível entrar no aplicativo do Human Resources no Teams</span><span class="sxs-lookup"><span data-stu-id="ed1e2-191">Can't sign into the Human Resources app in Teams</span></span>

<span data-ttu-id="ed1e2-192">Se não conseguir entrar no aplicativo, é possível que a conta que você esteja usando para entrar no Microsoft Teams não esteja associada a um registro de funcionário no Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="ed1e2-192">If you can't sign into the app, it's possible that the account you're using to sign into Microsoft Teams isn't associated with an employee record in Dynamics 365 Human Resources.</span></span> <span data-ttu-id="ed1e2-193">Entre em contato com o administrador do sistema para verificar se o registro de funcionário está associado corretamente.</span><span class="sxs-lookup"><span data-stu-id="ed1e2-193">Contact your system administrator to ensure your employee record is correctly associated.</span></span>

### <a name="error-when-approving-leave-requests-in-the-human-resources-app-in-teams"></a><span data-ttu-id="ed1e2-194">Erro ao aprovar solicitações de licença no aplicativo do Human Resources no Teams</span><span class="sxs-lookup"><span data-stu-id="ed1e2-194">Error when approving leave requests in the Human Resources app in Teams</span></span>

<span data-ttu-id="ed1e2-195">Se você receber um erro ao tentar aprovar solicitações de licença no aplicativo do Teams, siga estas etapas de solução de problemas:</span><span class="sxs-lookup"><span data-stu-id="ed1e2-195">If you receive an error when you're trying to approve leave requests in the Teams app, try the following troubleshooting steps:</span></span>

1. <span data-ttu-id="ed1e2-196">Verifique se a conta que você está usando para entrar no Microsoft Teams é a mesma que usa para acessar o Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="ed1e2-196">Verify that the account you're using to sign into Microsoft Teams is the same one you use for accessing Dynamics 365 Human Resources.</span></span>

2. <span data-ttu-id="ed1e2-197">Verifique se você é um aprovador válido para a solicitação ao verificar as configurações do fluxo de trabalho para a aprovação de licenças.</span><span class="sxs-lookup"><span data-stu-id="ed1e2-197">Verify that you're a valid approver for the request by checking the workflow settings for leave approval.</span></span> <span data-ttu-id="ed1e2-198">Para obter mais informações sobre fluxos de trabalho de solicitações de licença, consulte [Criar um fluxo de trabalho de solicitações de licença](hr-leave-and-absence-workflow.md).</span><span class="sxs-lookup"><span data-stu-id="ed1e2-198">For more information about leave request workflows, see [Create a leave request workflow](hr-leave-and-absence-workflow.md).</span></span>

## <a name="known-accessibility-issues"></a><span data-ttu-id="ed1e2-199">Problemas de acessibilidade conhecidos</span><span class="sxs-lookup"><span data-stu-id="ed1e2-199">Known accessibility issues</span></span>

<span data-ttu-id="ed1e2-200">O aplicativo Human Resources no Teams tem as questões de acessibilidade a seguir que estamos trabalhando para corrigir em versões futuras.</span><span class="sxs-lookup"><span data-stu-id="ed1e2-200">The Human Resources app in Teams has the following accessibility issues that we're working on fixing in future releases.</span></span>

| <span data-ttu-id="ed1e2-201">Problema</span><span class="sxs-lookup"><span data-stu-id="ed1e2-201">Issue</span></span> | <span data-ttu-id="ed1e2-202">Solução ou explicação</span><span class="sxs-lookup"><span data-stu-id="ed1e2-202">Workaround or explanation</span></span> |
| --- | --- |
| <span data-ttu-id="ed1e2-203">O zoom para 400% da área de trabalho oculta alguns dos botões de ação da exibição.</span><span class="sxs-lookup"><span data-stu-id="ed1e2-203">Zooming to 400% on desktop hides some of the action buttons from view.</span></span> | <span data-ttu-id="ed1e2-204">É recomendável usar uma lupa até que possamos dar suporte a esse nível de zoom.</span><span class="sxs-lookup"><span data-stu-id="ed1e2-204">We recommend using a magnifier instead until we can support this zoom level.</span></span> |
| <span data-ttu-id="ed1e2-205">Na guia **Folga**, o VoiceOver anuncia uma ação de botão enquanto lê o cabeçalho para a grade de folgas.</span><span class="sxs-lookup"><span data-stu-id="ed1e2-205">On the **Time off** tab, voiceover announces a button action while reading the header for the time-off grid.</span></span> | <span data-ttu-id="ed1e2-206">O cabeçalho e os elementos na grade são agrupados por ano e são recolhíveis.</span><span class="sxs-lookup"><span data-stu-id="ed1e2-206">The header and elements within the grid are grouped by year, and they're collapsible.</span></span> <span data-ttu-id="ed1e2-207">O VoiceOver interpreta isso como um item acionável, mas não é.</span><span class="sxs-lookup"><span data-stu-id="ed1e2-207">Voiceover interprets this as an actionable item, but it isn't.</span></span> |
| <span data-ttu-id="ed1e2-208">Na guia **Folga**, há um gesto de passar o dedo adicional ao navegar até o **Código de motivo** em uma nova solicitação.</span><span class="sxs-lookup"><span data-stu-id="ed1e2-208">On the **Time off** tab, there's an extra swipe gesture when navigating to **Reason code** in a new request.</span></span> | <span data-ttu-id="ed1e2-209">Não há controle oculto para que a navegação de deslizar o dedo esteja tentando acessar.</span><span class="sxs-lookup"><span data-stu-id="ed1e2-209">There is no hidden control that the swipe navigation is trying to get to.</span></span> |
| <span data-ttu-id="ed1e2-210">Na guia **Folga**, se você passar o dedo enquanto o calendário estiver aberto, terminará fora de controle, e não na parte superior em uma nova solicitação ou ao editar uma solicitação.</span><span class="sxs-lookup"><span data-stu-id="ed1e2-210">On the **Time off** tab, if you swipe while the calendar is open, you end up outside the control instead of at the top in a new request or while editing a request.</span></span> | <span data-ttu-id="ed1e2-211">Quando você atingir **Acessar hoje**, considere isso como o final do controle e o deslize o dedo na direção inversa para voltar ao início.</span><span class="sxs-lookup"><span data-stu-id="ed1e2-211">When you reach **Go to today**, consider that to be the end of the control and swipe in the reverse direction to get back to the top.</span></span> |
| <span data-ttu-id="ed1e2-212">O VoiceOver não lê os rótulos para datas.</span><span class="sxs-lookup"><span data-stu-id="ed1e2-212">Voiceover doesn't read the labels for dates.</span></span> | <span data-ttu-id="ed1e2-213">As datas encontradas em pares são sempre **Data de início** e **Data de término**.</span><span class="sxs-lookup"><span data-stu-id="ed1e2-213">The dates encountered in pairs are always **Start date** and **End date**.</span></span> |
| <span data-ttu-id="ed1e2-214">Na guia **Chat**, o foco recai sobre a parte superior quando você insere uma data usando a ferramenta de assistência ou a navegação por teclado.</span><span class="sxs-lookup"><span data-stu-id="ed1e2-214">On the **Chat** tab, the focus jumps back to the top when you enter a date while using the assistive tool or keyboard navigation.</span></span> | <span data-ttu-id="ed1e2-215">Pressione a tecla Tab até acessar a área de entrada novamente.</span><span class="sxs-lookup"><span data-stu-id="ed1e2-215">Tab until you reach your input area again.</span></span> |

## <a name="privacy-notice"></a><span data-ttu-id="ed1e2-216">Aviso de privacidade</span><span class="sxs-lookup"><span data-stu-id="ed1e2-216">Privacy notice</span></span>

### <a name="microsoft-language-understanding-intelligent-service-luis"></a><span data-ttu-id="ed1e2-217">Serviço Inteligente de Reconhecimento Vocal (LUIS) da Microsoft</span><span class="sxs-lookup"><span data-stu-id="ed1e2-217">Microsoft Language Understanding Intelligent Service (LUIS)</span></span>

<span data-ttu-id="ed1e2-218">Com o bot do Dynamics 365 Human Resources no Microsoft Teams, as entradas de texto do usuário são analisadas para compreender a consulta/intenção subjacente.</span><span class="sxs-lookup"><span data-stu-id="ed1e2-218">With the Dynamics 365 Human Resources bot in Microsoft Teams, the user’s text inputs are analyzed for understanding the underlying query/intent.</span></span> <span data-ttu-id="ed1e2-219">A entrada do usuário, como "Pesquisar conta Contoso", é encaminhada para um dos Cognitive Services da Microsoft, chamado de Serviço Inteligente de Reconhecimento Vocal (LUIS).</span><span class="sxs-lookup"><span data-stu-id="ed1e2-219">The user’s input such as “Search account Contoso” is routed to one of Microsoft’s Cognitive Service called Language Understanding Intelligent Service (LUIS).</span></span> <span data-ttu-id="ed1e2-220">Leia mais sobre o LUIS  [aqui](https://www.luis.ai/).</span><span class="sxs-lookup"><span data-stu-id="ed1e2-220">Read more about LUIS [here](https://www.luis.ai/).</span></span> <span data-ttu-id="ed1e2-221">O serviço LUIS exclui a ambiguidade ou compreende a intenção da entrada do usuário (nesse caso, a intenção é encontrar informações) e a entidade de destino (nesse caso, a entidade pretendida é uma conta chamada Contoso).</span><span class="sxs-lookup"><span data-stu-id="ed1e2-221">The LUIS service disambiguates or understands the intent of user input (in this case, the intent is to find information) and the target entity (in this case, the intended entity is an account named Contoso).</span></span> <span data-ttu-id="ed1e2-222">Em seguida, essas informações são passadas para o [Azure Bot Framework](https://azure.microsoft.com/services/bot-service/) da Microsoft, que interage com os dados do Dynamics 365 Human Resources e recupera as informações desejadas para a consulta do usuário.</span><span class="sxs-lookup"><span data-stu-id="ed1e2-222">This information is then passed on to Microsoft’s [Azure bot framework](https://azure.microsoft.com/services/bot-service/), which interacts with data from Dynamics 365 Human Resources and retrieves the desired information for the user query.</span></span> 

<span data-ttu-id="ed1e2-223">Ao instalar e permitir o acesso ao uso do bot, você permite que o serviço LUIS e a estrutura de bot do Azure processem a intenção por trás da entrada, o que resulta em uma experiência aprimorada de conversa do usuário.</span><span class="sxs-lookup"><span data-stu-id="ed1e2-223">By installing and allowing access to use of the bot, you agree to allow the LUIS service and Azure bot framework to process the intent behind the input,  which results in an enhanced conversational user experience.</span></span> <span data-ttu-id="ed1e2-224">O serviço LUIS e a estrutura de bot do Azure têm vários níveis de conformidade em comparação com o Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="ed1e2-224">The LUIS service and Azure bot framework may have varying levels of compliance compared to Dynamics 365 Human Resources.</span></span> <span data-ttu-id="ed1e2-225">Embora o serviço LUIS tenha acesso a somente às consultas do usuário e não tenha sido desenvolvido para se conectar aos dados ou à conta do usuário do Dynamics 365 Human Resources, um usuário do bot do Dynamics 365 Human Resources poderia voluntariamente inserir uma consulta contendo Dados do Cliente, Dados Pessoais ou outros dados, e esse conteúdo da consulta poderia ser enviado para o serviço LUIS e para a estrutura de bot do Azure.</span><span class="sxs-lookup"><span data-stu-id="ed1e2-225">While the LUIS service has access to only the user queries and is not designed to be connected to the user’s Dynamics 365 Human Resources data or account, a user of the Dynamics 365 Human Resources bot could voluntarily enter a query containing Customer Data, Personal Data, or other data and such query content could get sent to the LUIS service and the Azure bot framework.</span></span> 

<span data-ttu-id="ed1e2-226">O conteúdo das consultas e das mensagens do usuário é mantido no sistema do LUIS por até 30 dias, criptografado em repouso e não é usado para treinamento ou melhoria de serviço.</span><span class="sxs-lookup"><span data-stu-id="ed1e2-226">The content of user’s queries and messages is retained in LUIS system for a maximum of 30 days, is encrypted at rest, and is not used for training or service improvement.</span></span> <span data-ttu-id="ed1e2-227">Leia mais sobre o Cognitive Services [aqui](https://azure.microsoft.com/services/cognitive-services/language-understanding-intelligent-service/).</span><span class="sxs-lookup"><span data-stu-id="ed1e2-227">Read more about Cognitive Services [here](https://azure.microsoft.com/services/cognitive-services/language-understanding-intelligent-service/).</span></span> 

<span data-ttu-id="ed1e2-228">Para gerenciar as configurações de administração de aplicativos no Microsoft Teams, vá para o [centro de administração do Microsoft Teams](https://admin.teams.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="ed1e2-228">To manage admin settings for apps in Microsoft Teams, go to the [Microsoft Teams admin center](https://admin.teams.microsoft.com/).</span></span>

### <a name="microsoft-teams-azure-event-grid-and-azure-cosmos-db"></a><span data-ttu-id="ed1e2-229">Microsoft Teams, Azure Event Grid e Azure Cosmos DB</span><span class="sxs-lookup"><span data-stu-id="ed1e2-229">Microsoft Teams, Azure Event Grid, and Azure Cosmos DB</span></span>

<span data-ttu-id="ed1e2-230">Ao usar o aplicativo Dynamics 365 Human Resources no Microsoft Teams, determinados dados do cliente podem fluir fora da região geográfica em que o serviço de Human Resources do locatário é implantado.</span><span class="sxs-lookup"><span data-stu-id="ed1e2-230">When using the Dynamics 365 Human Resources app in Microsoft Teams, certain customer data may flow outside of the geographic region where your tenant’s Human Resources service is deployed.</span></span>

<span data-ttu-id="ed1e2-231">O Dynamics 365 Human Resources transmite detalhes da solicitação de licença e da tarefa de fluxo de trabalho do funcionário para a Grade de Eventos do Microsoft Azure e o Microsoft Teams .</span><span class="sxs-lookup"><span data-stu-id="ed1e2-231">Dynamics 365 Human Resources transmits the employee’s leave request and workflow task details to Microsoft Azure Event Grid and Microsoft Teams.</span></span> <span data-ttu-id="ed1e2-232">Esses dados podem ser armazenados na Grade de Eventos do Microsoft Azure por até 24 horas e podem ser processados nos Estados Unidos, são criptografados em trânsito e em repouso, e não são usados pela Microsoft ou subprocessadores para treinamento ou melhorias de serviço.</span><span class="sxs-lookup"><span data-stu-id="ed1e2-232">This data may be stored in Microsoft Azure Event Grid for up to 24 hours and will be processed in the United States, is encrypted in transit and at rest, and is not used by Microsoft or its subprocessors for training or service improvements.</span></span> <span data-ttu-id="ed1e2-233">Para entender onde seus dados são armazenados no Teams, consulte: [Localização dos dados no Microsoft Teams](https://docs.microsoft.com/microsoftteams/location-of-data-in-teams?view=o365-worldwide&preserve-view=true).</span><span class="sxs-lookup"><span data-stu-id="ed1e2-233">To understand where your data is stored in Teams, please see: [Location of data in Microsoft Teams](https://docs.microsoft.com/microsoftteams/location-of-data-in-teams?view=o365-worldwide&preserve-view=true).</span></span>

<span data-ttu-id="ed1e2-234">Ao conversar com o bot de bate-papo no aplicativo Human Resources, o conteúdo da conversa pode ser armazenado no Azure Cosmos DB e transmitido ao Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="ed1e2-234">While conversing with the chat bot in the Human Resources app, the conversation content may be stored in Azure Cosmos DB and transmitted to Microsoft Teams.</span></span> <span data-ttu-id="ed1e2-235">Esses dados podem ser armazenados no Azure Cosmos DB por até 24 horas e podem ser processados fora da região geográfica onde o serviço do Human Resources do seu locatário está implantado, é criptografado em trânsito e em repouso e não é usado pela Microsoft ou seus subprocessadores para treinamento ou melhorias de serviço.</span><span class="sxs-lookup"><span data-stu-id="ed1e2-235">This data may be stored in Azure Cosmos DB for up to 24 hours and may be processed outside of the geographic region where your tenant's Human Resources service is deployed, is encrypted in transit and at rest, and is not used by Microsoft or its subprocessors for training or service improvements.</span></span> <span data-ttu-id="ed1e2-236">Para entender onde seus dados são armazenados no Teams, consulte: [Localização dos dados no Microsoft Teams](https://docs.microsoft.com/microsoftteams/location-of-data-in-teams?view=o365-worldwide&preserve-view=true).</span><span class="sxs-lookup"><span data-stu-id="ed1e2-236">To understand where your data is stored in Teams, please see: [Location of data in Microsoft Teams](https://docs.microsoft.com/microsoftteams/location-of-data-in-teams?view=o365-worldwide&preserve-view=true).</span></span>
 
<span data-ttu-id="ed1e2-237">Para restringir o acesso ao aplicativo Human Resources no Microsoft Teams para sua organização ou usuários dentro de sua organização, consulte [Gerenciar políticas de permissão de aplicativo no Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/teams-app-permission-policies).</span><span class="sxs-lookup"><span data-stu-id="ed1e2-237">To restrict access to the Human Resources app in Microsoft Teams for your organization or users within your organization, see [Manage app permission policies in Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/teams-app-permission-policies).</span></span>

## <a name="see-also"></a><span data-ttu-id="ed1e2-238">Consulte também</span><span class="sxs-lookup"><span data-stu-id="ed1e2-238">See also</span></span>

[<span data-ttu-id="ed1e2-239">Baixar e instalar o Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ed1e2-239">Download and install Microsoft Teams</span></span>](https://support.office.com/article/download-and-install-microsoft-teams-422bf3aa-9ae8-46f1-83a2-e65720e1a34d)</br>
[<span data-ttu-id="ed1e2-240">Central de ajuda do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ed1e2-240">Microsoft Teams help center</span></span>](https://support.office.com/teams)</br>
[<span data-ttu-id="ed1e2-241">Aplicativo Human Resources no Teams</span><span class="sxs-lookup"><span data-stu-id="ed1e2-241">Human Resources app in Teams</span></span>](hr-admin-teams-leave-app.md)
