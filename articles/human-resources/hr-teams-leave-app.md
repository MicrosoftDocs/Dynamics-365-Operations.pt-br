---
title: Gerenciar solicitações de licença no Teams
description: Este tópico mostra como solicitar licenças no aplicativo do Dynamics 365 Human Resources no Microsoft Teams.
author: andreabichsel
ms.date: 02/23/2021
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: 72fa3309b77717d0291b8b6828ed5bc4c65e95ab
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5790563"
---
# <a name="manage-leave-requests-in-teams"></a><span data-ttu-id="b5df7-103">Gerenciar solicitações de licença no Teams</span><span class="sxs-lookup"><span data-stu-id="b5df7-103">Manage leave requests in Teams</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="b5df7-104">O aplicativo Dynamics 365 Human Resources no Microsoft Teams permite solicitar folgas rapidamente e exibir informações de saldo de folgas no Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="b5df7-104">The Dynamics 365 Human Resources app in Microsoft Teams lets you quickly request time off and view your time-off balance information right in Microsoft Teams.</span></span> <span data-ttu-id="b5df7-105">Você pode interagir com um bot para solicitar informações e iniciar uma solicitação de licença.</span><span class="sxs-lookup"><span data-stu-id="b5df7-105">You can interact with a bot to request information and start a leave request.</span></span> <span data-ttu-id="b5df7-106">A guia **Folga** fornece informações mais detalhadas.</span><span class="sxs-lookup"><span data-stu-id="b5df7-106">The **Time off** tab provides more detailed information.</span></span> <span data-ttu-id="b5df7-107">Você também pode enviar às pessoas informações sobre as próximas folgas no Teams e chats fora do aplicativo Human Resources.</span><span class="sxs-lookup"><span data-stu-id="b5df7-107">You can also send people information about your upcoming time off in Teams and chats outside the Human Resources app.</span></span>

## <a name="install-the-app"></a><span data-ttu-id="b5df7-108">Instalar o aplicativo</span><span class="sxs-lookup"><span data-stu-id="b5df7-108">Install the app</span></span>

<span data-ttu-id="b5df7-109">Você pode encontrar o aplicativo Dynamics 365 Human Resources na loja do Teams.</span><span class="sxs-lookup"><span data-stu-id="b5df7-109">You can find the Dynamics 365 Human Resources app in the Teams store.</span></span>

1. <span data-ttu-id="b5df7-110">No Microsoft Teams, selecione as reticências.</span><span class="sxs-lookup"><span data-stu-id="b5df7-110">In Microsoft Teams, select the ellipses.</span></span>

   ![Reticências do aplicativo de licença do Human Resources Teams](./media/hr-teams-leave-app-ellipses.png)
 
2. <span data-ttu-id="b5df7-112">Procure Dynamics 365 Human Resources, e selecione o título **Human Resources**.</span><span class="sxs-lookup"><span data-stu-id="b5df7-112">Search for Dynamics 365 Human Resources, and then select the **Human Resources** tile.</span></span>

   ![Título do HR do aplicativo de licença do Human Resources Teams](./media/hr-teams-leave-app-human-resources-tile.png)

3. <span data-ttu-id="b5df7-114">Selecione o botão **Adicionar** para instalar o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="b5df7-114">Select the **Add** button to install the app.</span></span>

   ![Instalar o aplicativo de licença do Human Resources Teams](./media/hr-teams-leave-app-in-store.png)

<span data-ttu-id="b5df7-116">Se o aplicativo não fizer logon automaticamente, selecione a guia **Configurações** para entrar.</span><span class="sxs-lookup"><span data-stu-id="b5df7-116">If the app doesn't automatically sign you in, select the **Settings** tab to sign in.</span></span>

![Guia Configurações do aplicativo de licença do Human Resources Teams](./media/hr-teams-leave-app-settings-tab.png)

> [!NOTE]
> <span data-ttu-id="b5df7-118">Caso você não veja uma caixa de diálogo de entrada, verifique as configurações do navegador para permitir janelas pop-up.</span><span class="sxs-lookup"><span data-stu-id="b5df7-118">If you don’t see a sign-in dialog box, check your browser settings to allow pop-ups.</span></span> 

<span data-ttu-id="b5df7-119">Se você tiver acesso a mais de uma instância do Human Resources, poderá selecionar a qual ambiente deseja se conectar na guia **Configurações**.</span><span class="sxs-lookup"><span data-stu-id="b5df7-119">If you have access to more than one instance of Human Resources, you can select which environment you want to connect to in the **Settings** tab.</span></span>

> [!NOTE]
> <span data-ttu-id="b5df7-120">O aplicativo agora oferece suporte à função de segurança Administrador do sistema.</span><span class="sxs-lookup"><span data-stu-id="b5df7-120">The app now supports the System Administrator security role.</span></span>
 
## <a name="use-the-bot"></a><span data-ttu-id="b5df7-121">Usar o bot</span><span class="sxs-lookup"><span data-stu-id="b5df7-121">Use the bot</span></span>

<span data-ttu-id="b5df7-122">Depois de instalar o aplicativo, será exibida uma mensagem de boas-vindas, informando os tipos de ações que o bot pode assumir em seu nome.</span><span class="sxs-lookup"><span data-stu-id="b5df7-122">After the app installs, a welcome message appears, letting you know the types of actions the bot can take on your behalf.</span></span>

![Mensagem de boas-vindas do bot do aplicativo de licença do Human Resources Teams](./media/hr-teams-leave-app-bot.png)
 
> [!NOTE]
> <span data-ttu-id="b5df7-124">Talvez você precise entrar na primeira interação com o bot.</span><span class="sxs-lookup"><span data-stu-id="b5df7-124">When first interacting with the bot, you might need to sign in.</span></span> <span data-ttu-id="b5df7-125">Caso você não veja uma caixa de diálogo de entrada, verifique as configurações do navegador para permitir janelas pop-up.</span><span class="sxs-lookup"><span data-stu-id="b5df7-125">If you don’t see a sign-in dialog box, check your browser settings to allow pop-ups.</span></span>

<span data-ttu-id="b5df7-126">Você pode pedir para o bot:</span><span class="sxs-lookup"><span data-stu-id="b5df7-126">You can ask the bot to:</span></span>

- <span data-ttu-id="b5df7-127">Iniciar uma solicitação de licença para você.</span><span class="sxs-lookup"><span data-stu-id="b5df7-127">Start a leave request for you.</span></span>

  ![Iniciar uma solicitação de licença no chat do Teams](./media/hr-teams-leave-app-initiate.png)

- <span data-ttu-id="b5df7-129">O bot do chat preencherá uma solicitação de licença.</span><span class="sxs-lookup"><span data-stu-id="b5df7-129">The chat bot will populate a leave request for you.</span></span> <span data-ttu-id="b5df7-130">Selecione **Solicitar folga** e edite os detalhes para sua solicitação.</span><span class="sxs-lookup"><span data-stu-id="b5df7-130">Select **Request time off** and edit the details for your request.</span></span>

  ![Editar detalhes da solicitação de licença](./media/hr-teams-leave-app-details.png)

- <span data-ttu-id="b5df7-132">Ao terminar de editar detalhes da solicitação de licença, selecione **Enviar** para enviá-la para aprovação.</span><span class="sxs-lookup"><span data-stu-id="b5df7-132">When you're done editing your leave request details, select **Submit** to submit it for approval.</span></span>

  ![Enviar solicitação de licença](./media/hr-teams-leave-app-submit.png)

## <a name="manage-your-leave-in-teams"></a><span data-ttu-id="b5df7-134">Gerenciar a sua licença no Teams</span><span class="sxs-lookup"><span data-stu-id="b5df7-134">Manage your leave in Teams</span></span>

<span data-ttu-id="b5df7-135">A guia **Folga** permite exibir:</span><span class="sxs-lookup"><span data-stu-id="b5df7-135">The **Time off** tab allows you to view:</span></span> 

- <span data-ttu-id="b5df7-136">Informações do saldo para cada tipo de licença na qual você está inscrito</span><span class="sxs-lookup"><span data-stu-id="b5df7-136">Balance information for each leave type you're enrolled in</span></span>

- <span data-ttu-id="b5df7-137">Solicitações de licença futuras</span><span class="sxs-lookup"><span data-stu-id="b5df7-137">Upcoming leave requests</span></span>

- <span data-ttu-id="b5df7-138">Solicitações de folga</span><span class="sxs-lookup"><span data-stu-id="b5df7-138">Time-off requests</span></span>

- <span data-ttu-id="b5df7-139">Rascunho de solicitações de licença</span><span class="sxs-lookup"><span data-stu-id="b5df7-139">Draft leave requests</span></span>

![Guia Folga do aplicativo de licença do Human Resources Teams](./media/hr-teams-leave-app-timeoff-tab.png)
 
### <a name="create-a-new-request"></a><span data-ttu-id="b5df7-141">Criar uma solicitação</span><span class="sxs-lookup"><span data-stu-id="b5df7-141">Create a new request</span></span>

1. <span data-ttu-id="b5df7-142">Para criar uma solicitação de licença, selecione **Nova solicitação**.</span><span class="sxs-lookup"><span data-stu-id="b5df7-142">To create a new leave request, select **New request**.</span></span>

   ![Nova solicitação no aplicativo de licença do Human Resources Teams](./media/hr-teams-leave-app-timeoff-tab-new.png)

2. <span data-ttu-id="b5df7-144">Insira os dias que você deseja solicitar folga e depois selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="b5df7-144">Enter the day or days you want to take off, and then select **Add**.</span></span>

   ![Adicionar folga no aplicativo de licença do Human Resources Teams](./media/hr-teams-leave-app-timeoff-tab-add.png)

3. <span data-ttu-id="b5df7-146">Se aplicável, insira um código de motivo.</span><span class="sxs-lookup"><span data-stu-id="b5df7-146">If applicable, enter a reason code.</span></span> <span data-ttu-id="b5df7-147">Insira também comentários e adicione anexos.</span><span class="sxs-lookup"><span data-stu-id="b5df7-147">Also enter any comments and add any attachments.</span></span>

4. <span data-ttu-id="b5df7-148">Após inserir as informações, digite **Enviar** para enviá-la para aprovação.</span><span class="sxs-lookup"><span data-stu-id="b5df7-148">When you're done entering information, type **Submit** to submit it for approval.</span></span> <span data-ttu-id="b5df7-149">Você também pode digitar **Salvar como rascunho** para continuar depois.</span><span class="sxs-lookup"><span data-stu-id="b5df7-149">You can also type **Save as draft** to come back to it later.</span></span>

### <a name="manage-draft-requests"></a><span data-ttu-id="b5df7-150">Gerenciar solicitações em rascunho</span><span class="sxs-lookup"><span data-stu-id="b5df7-150">Manage draft requests</span></span>

1. <span data-ttu-id="b5df7-151">Selecione a guia **Rascunhos**.</span><span class="sxs-lookup"><span data-stu-id="b5df7-151">Select the **Drafts** tab.</span></span>

   ![Guia Rascunhos do aplicativo de licença do Human Resources Teams](./media/hr-teams-leave-app-drafts-tab.png)

2. <span data-ttu-id="b5df7-153">Selecione o lápis para editar a solicitação, ou selecione a lixeira para excluí-la.</span><span class="sxs-lookup"><span data-stu-id="b5df7-153">Select the pencil to edit the request, or select the trash can to delete the request.</span></span>

3. <span data-ttu-id="b5df7-154">Faça todas as alterações necessárias.</span><span class="sxs-lookup"><span data-stu-id="b5df7-154">Make any necessary changes.</span></span> <span data-ttu-id="b5df7-155">Após inserir as informações, digite **Enviar** para enviá-la para aprovação.</span><span class="sxs-lookup"><span data-stu-id="b5df7-155">When you're done entering information, type **Submit** to submit it for approval.</span></span> <span data-ttu-id="b5df7-156">Você também pode selecionar **Salvar como rascunho** para continuar depois.</span><span class="sxs-lookup"><span data-stu-id="b5df7-156">You can also select **Save as draft** to come back to it later.</span></span>

   ![Editar rascunho no aplicativo de licença do Human Resources Teams](./media/hr-teams-leave-app-drafts-edit.png)
   
### <a name="respond-to-teams-notifications"></a><span data-ttu-id="b5df7-158">Responder a notificações do Teams</span><span class="sxs-lookup"><span data-stu-id="b5df7-158">Respond to Teams notifications</span></span>

<span data-ttu-id="b5df7-159">Quando você ou um trabalhador para o qual você é um aprovador enviar uma solicitação de licença, você receberá uma notificação no aplicativo Human Resources no Teams.</span><span class="sxs-lookup"><span data-stu-id="b5df7-159">When you or a worker you're an approver for submits a leave request, you'll receive a notification in the Human Resources app in Teams.</span></span> <span data-ttu-id="b5df7-160">Você pode selecionar a notificação para exibi-la.</span><span class="sxs-lookup"><span data-stu-id="b5df7-160">You can select the notification to view it.</span></span> <span data-ttu-id="b5df7-161">As notificações também aparecem na área **Chat** .</span><span class="sxs-lookup"><span data-stu-id="b5df7-161">Notifications also appear in the **Chat** area.</span></span>

<span data-ttu-id="b5df7-162">Se você for aprovador, poderá selecionar **Aprovar** ou **Negar** na notificação.</span><span class="sxs-lookup"><span data-stu-id="b5df7-162">If you're an approver, you can select **Approve** or **Deny** in the notification.</span></span> <span data-ttu-id="b5df7-163">Você também pode fornecer uma mensagem opcional.</span><span class="sxs-lookup"><span data-stu-id="b5df7-163">You can also provide an optional message.</span></span>

![Deixar uma notificação de solicitação no aplicativo Human Resources no Teams](./media/hr-teams-leave-app-notification.png)

## <a name="send-upcoming-time-off-information-to-your-coworkers"></a><span data-ttu-id="b5df7-165">Enviar informações sobre as próximas folgas para seus colegas de trabalho</span><span class="sxs-lookup"><span data-stu-id="b5df7-165">Send upcoming time-off information to your coworkers</span></span>

<span data-ttu-id="b5df7-166">Depois de instalar o aplicativo Human Resources para o Teams, você pode enviar facilmente informações sobre sua próxima folga para seus colegas de trabalho em equipes ou bate-papos.</span><span class="sxs-lookup"><span data-stu-id="b5df7-166">After you install the Human Resources app for Teams, you can easily send information about your upcoming time off to your coworkers in teams or chats.</span></span>

1. <span data-ttu-id="b5df7-167">Em uma equipe ou chat no Teams, selecione o botão do Human Resources abaixo da janela de chat.</span><span class="sxs-lookup"><span data-stu-id="b5df7-167">In a team or chat in Teams, select the Human Resources button below the chat window.</span></span>

   ![Botão do Human Resources abaixo da janela de bate-papo](./media/hr-teams-leave-app-chat-button.png)

2. <span data-ttu-id="b5df7-169">Selecione a solicitação de licença que deseja compartilhar.</span><span class="sxs-lookup"><span data-stu-id="b5df7-169">Select the leave request you want to share.</span></span> <span data-ttu-id="b5df7-170">Se você deseja compartilhar um rascunho de solicitação de licença, selecione **Rascunhos** primeiro.</span><span class="sxs-lookup"><span data-stu-id="b5df7-170">If you want to share a draft leave request, select **Drafts** first.</span></span>

   ![Selecionar uma próxima solicitação de licença para compartilhar](./media/hr-teams-leave-app-chat-search.png)

<span data-ttu-id="b5df7-172">Sua solicitação de licença será exibida no chat.</span><span class="sxs-lookup"><span data-stu-id="b5df7-172">Your leave request will display in the chat.</span></span>

![Cartão de solicitação de licença do Human Resources](./media/hr-teams-leave-app-chat-card.png)

<span data-ttu-id="b5df7-174">Se você compartilhou uma solicitação de rascunho, ela será exibida como rascunho:</span><span class="sxs-lookup"><span data-stu-id="b5df7-174">If you shared a draft request, it will display as a draft:</span></span>

![Rascunho do cartão de solicitação de licença do Human Resources](./media/hr-teams-leave-app-chat-draft-card.png)

## <a name="view-your-teams-leave-calendar"></a><span data-ttu-id="b5df7-176">Exibir o calendário de licença da equipe</span><span class="sxs-lookup"><span data-stu-id="b5df7-176">View your team's leave calendar</span></span>

<span data-ttu-id="b5df7-177">Se você for um gerente com subordinados diretos, poderá exibir folgas aprovadas e pendentes da sua equipe.</span><span class="sxs-lookup"><span data-stu-id="b5df7-177">If you're a manager with direct reports, you can view your team's approved and pending time off.</span></span>

1. <span data-ttu-id="b5df7-178">No aplicativo Human Resources no Teams, selecione **Folga** .</span><span class="sxs-lookup"><span data-stu-id="b5df7-178">In the Human Resources app in Teams, select **Time off**.</span></span>

2. <span data-ttu-id="b5df7-179">Selecione **Calendário da equipe** .</span><span class="sxs-lookup"><span data-stu-id="b5df7-179">Select **Team calendar**.</span></span> <span data-ttu-id="b5df7-180">O calendário exibe as folgas aprovadas e pendentes dos subordinados diretos.</span><span class="sxs-lookup"><span data-stu-id="b5df7-180">The calendar displays your direct reports' approved and pending time off.</span></span>

   ![Exibir calendário no aplicativo Human Resources do Teams](./media/hr-teams-leave-app-view-calendar.png)

   > [!NOTE]
   > <span data-ttu-id="b5df7-182">Se você não conseguir ver o calendário da equipe, peça ao administrador para habilitá-lo.</span><span class="sxs-lookup"><span data-stu-id="b5df7-182">If you can't see the team calendar, ask your admin to enable it.</span></span> <span data-ttu-id="b5df7-183">Para obter mais informações, consulte [Instalar e configurar](hr-admin-teams-leave-app.md#install-and-setup).</span><span class="sxs-lookup"><span data-stu-id="b5df7-183">For more information, see [Install and setup](hr-admin-teams-leave-app.md#install-and-setup).</span></span>

## <a name="supported-languages"></a><span data-ttu-id="b5df7-184">Idiomas com suporte</span><span class="sxs-lookup"><span data-stu-id="b5df7-184">Supported languages</span></span>

<span data-ttu-id="b5df7-185">O aplicativo Dynamics 365 Human Resources no Teams oferece suporte aos seguintes idiomas:</span><span class="sxs-lookup"><span data-stu-id="b5df7-185">The Dynamics 365 Human Resources app in Teams supports the following languages:</span></span>

| <span data-ttu-id="b5df7-186">ID da localidade</span><span class="sxs-lookup"><span data-stu-id="b5df7-186">Locale ID</span></span> | <span data-ttu-id="b5df7-187">Idioma</span><span class="sxs-lookup"><span data-stu-id="b5df7-187">Language</span></span> |
| --- | --- |
| <span data-ttu-id="b5df7-188">de-DE</span><span class="sxs-lookup"><span data-stu-id="b5df7-188">de-DE</span></span> | <span data-ttu-id="b5df7-189">Alemão (Alemanha)</span><span class="sxs-lookup"><span data-stu-id="b5df7-189">German (Germany)</span></span> |
| <span data-ttu-id="b5df7-190">es-ES</span><span class="sxs-lookup"><span data-stu-id="b5df7-190">es-ES</span></span> | <span data-ttu-id="b5df7-191">Espanhol (Espanha)</span><span class="sxs-lookup"><span data-stu-id="b5df7-191">Spanish (Spain)</span></span> |
| <span data-ttu-id="b5df7-192">es-MX</span><span class="sxs-lookup"><span data-stu-id="b5df7-192">es-MX</span></span> | <span data-ttu-id="b5df7-193">Espanhol (México)</span><span class="sxs-lookup"><span data-stu-id="b5df7-193">Spanish (Mexico)</span></span> |
| <span data-ttu-id="b5df7-194">fr-CA</span><span class="sxs-lookup"><span data-stu-id="b5df7-194">fr-CA</span></span> | <span data-ttu-id="b5df7-195">Francês (Canadá)</span><span class="sxs-lookup"><span data-stu-id="b5df7-195">French (Canada)</span></span> |
| <span data-ttu-id="b5df7-196">fr-FR</span><span class="sxs-lookup"><span data-stu-id="b5df7-196">fr-FR</span></span> | <span data-ttu-id="b5df7-197">Francês (França)</span><span class="sxs-lookup"><span data-stu-id="b5df7-197">French (France)</span></span> |
| <span data-ttu-id="b5df7-198">it-IT</span><span class="sxs-lookup"><span data-stu-id="b5df7-198">it-IT</span></span> | <span data-ttu-id="b5df7-199">Italiano (Itália)</span><span class="sxs-lookup"><span data-stu-id="b5df7-199">Italian (Italy)</span></span> |
| <span data-ttu-id="b5df7-200">nl-NL</span><span class="sxs-lookup"><span data-stu-id="b5df7-200">nl-NL</span></span> | <span data-ttu-id="b5df7-201">Holandês (Países Baixos)</span><span class="sxs-lookup"><span data-stu-id="b5df7-201">Dutch (Netherlands)</span></span> |
| <span data-ttu-id="b5df7-202">pt-BR</span><span class="sxs-lookup"><span data-stu-id="b5df7-202">pt-BR</span></span> | <span data-ttu-id="b5df7-203">Português (Brasil)</span><span class="sxs-lookup"><span data-stu-id="b5df7-203">Portuguese (Brazil)</span></span> |
| <span data-ttu-id="b5df7-204">tr-TR</span><span class="sxs-lookup"><span data-stu-id="b5df7-204">tr-TR</span></span> | <span data-ttu-id="b5df7-205">Turco (Turquia)</span><span class="sxs-lookup"><span data-stu-id="b5df7-205">Turkish (Turkey)</span></span> |
| <span data-ttu-id="b5df7-206">zh-CN</span><span class="sxs-lookup"><span data-stu-id="b5df7-206">zh-CN</span></span> | <span data-ttu-id="b5df7-207">Chinês (simplificado)</span><span class="sxs-lookup"><span data-stu-id="b5df7-207">Chinese (Simplified)</span></span> |

## <a name="troubleshooting"></a><span data-ttu-id="b5df7-208">Solução de problemas</span><span class="sxs-lookup"><span data-stu-id="b5df7-208">Troubleshooting</span></span>

<span data-ttu-id="b5df7-209">Se você tiver problemas para entrar ou usar o aplicativo do Dynamics 365 Human Resources no Teams, tente seguir estas instruções de solução de problemas.</span><span class="sxs-lookup"><span data-stu-id="b5df7-209">If you're having trouble signing into or using the Dynamics 365 Human Resources Teams app, try following these troubleshooting instructions.</span></span> <span data-ttu-id="b5df7-210">Se você ainda tiver problemas após a solução de problemas, contate o Suporte.</span><span class="sxs-lookup"><span data-stu-id="b5df7-210">If you're still having problems after troubleshooting, contact Support.</span></span> <span data-ttu-id="b5df7-211">Para obter mais informações, consulte [Obter suporte](hr-admin-troubleshooting-support.md).</span><span class="sxs-lookup"><span data-stu-id="b5df7-211">For more information, see [Get support](hr-admin-troubleshooting-support.md).</span></span>

### <a name="cant-sign-into-the-human-resources-app-in-teams"></a><span data-ttu-id="b5df7-212">Não é possível entrar no aplicativo do Human Resources no Teams</span><span class="sxs-lookup"><span data-stu-id="b5df7-212">Can't sign into the Human Resources app in Teams</span></span>

<span data-ttu-id="b5df7-213">Se não conseguir entrar no aplicativo, é possível que a conta que você esteja usando para entrar no Microsoft Teams não esteja associada a um registro de funcionário no Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="b5df7-213">If you can't sign into the app, it's possible that the account you're using to sign into Microsoft Teams isn't associated with an employee record in Dynamics 365 Human Resources.</span></span> <span data-ttu-id="b5df7-214">Entre em contato com o administrador do sistema para verificar se o registro de funcionário está associado corretamente.</span><span class="sxs-lookup"><span data-stu-id="b5df7-214">Contact your system administrator to ensure your employee record is correctly associated.</span></span>

### <a name="translations-dont-display-correctly"></a><span data-ttu-id="b5df7-215">As traduções não são exibidas corretamente</span><span class="sxs-lookup"><span data-stu-id="b5df7-215">Translations don't display correctly</span></span>

<span data-ttu-id="b5df7-216">Se as traduções não forem exibidas conforme o esperado, verifique se o idioma selecionado no Teams corresponde ao idioma selecionado em **Usar opções** no Human Resources.</span><span class="sxs-lookup"><span data-stu-id="b5df7-216">If translations don't display as expected, make sure the language you select in Teams matches the language selected in Human Resources **User options**.</span></span>

<span data-ttu-id="b5df7-217">No Teams, verifique **Idioma do aplicativo** em **Configurações**.</span><span class="sxs-lookup"><span data-stu-id="b5df7-217">In Teams, look at **App language** in **Settings**.</span></span>

![Configurações do Teams](./media/hr-teams-leave-app-settings.png)

<span data-ttu-id="b5df7-219">No Human Resources, selecione **Configurações** e, depois, **Opções de usuário**.</span><span class="sxs-lookup"><span data-stu-id="b5df7-219">In Human Resources, select **Settings** and then select **User options**.</span></span> <span data-ttu-id="b5df7-220">Verifique se o campo **Idioma** corresponde ao campo **Idioma do aplicativo** no Teams.</span><span class="sxs-lookup"><span data-stu-id="b5df7-220">Verify that the **Language** field matches the **App language** field in Teams.</span></span>

![Opções de usuário no Human Resources](./media/hr-teams-leave-app-user-options.png)

<span data-ttu-id="b5df7-222">Se ainda houver problemas de tradução, avise-nos.</span><span class="sxs-lookup"><span data-stu-id="b5df7-222">If you still experience translation issues, let us know.</span></span> <span data-ttu-id="b5df7-223">Para obter informações, consulte [Obter suporte para aplicativos do Finance and Operations ou Lifecycle Services (LCS)](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/lifecycle-services/lcs-support?toc=/dynamics365/human-resources/toc.json).</span><span class="sxs-lookup"><span data-stu-id="b5df7-223">For information, see [Get support for Finance and Operations apps or Lifecycle Services (LCS)](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/lifecycle-services/lcs-support?toc=/dynamics365/human-resources/toc.json).</span></span>

### <a name="error-when-approving-leave-requests-in-the-human-resources-app-in-teams"></a><span data-ttu-id="b5df7-224">Erro ao aprovar solicitações de licença no aplicativo do Human Resources no Teams</span><span class="sxs-lookup"><span data-stu-id="b5df7-224">Error when approving leave requests in the Human Resources app in Teams</span></span>

<span data-ttu-id="b5df7-225">Se você receber um erro ao tentar aprovar solicitações de licença no aplicativo do Teams, siga estas etapas de solução de problemas:</span><span class="sxs-lookup"><span data-stu-id="b5df7-225">If you receive an error when you're trying to approve leave requests in the Teams app, try the following troubleshooting steps:</span></span>

1. <span data-ttu-id="b5df7-226">Verifique se a conta que você está usando para entrar no Microsoft Teams é a mesma que usa para acessar o Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="b5df7-226">Verify that the account you're using to sign into Microsoft Teams is the same one you use for accessing Dynamics 365 Human Resources.</span></span>

2. <span data-ttu-id="b5df7-227">Verifique se você é um aprovador válido para a solicitação ao verificar as configurações do fluxo de trabalho para a aprovação de licenças.</span><span class="sxs-lookup"><span data-stu-id="b5df7-227">Verify that you're a valid approver for the request by checking the workflow settings for leave approval.</span></span> <span data-ttu-id="b5df7-228">Para obter mais informações sobre fluxos de trabalho de solicitações de licença, consulte [Criar um fluxo de trabalho de solicitações de licença](hr-leave-and-absence-workflow.md).</span><span class="sxs-lookup"><span data-stu-id="b5df7-228">For more information about leave request workflows, see [Create a leave request workflow](hr-leave-and-absence-workflow.md).</span></span>

## <a name="known-accessibility-issues"></a><span data-ttu-id="b5df7-229">Problemas de acessibilidade conhecidos</span><span class="sxs-lookup"><span data-stu-id="b5df7-229">Known accessibility issues</span></span>

<span data-ttu-id="b5df7-230">O aplicativo Human Resources no Teams tem as questões de acessibilidade a seguir que estamos trabalhando para corrigir em versões futuras.</span><span class="sxs-lookup"><span data-stu-id="b5df7-230">The Human Resources app in Teams has the following accessibility issues that we're working on fixing in future releases.</span></span>

| <span data-ttu-id="b5df7-231">Problema</span><span class="sxs-lookup"><span data-stu-id="b5df7-231">Issue</span></span> | <span data-ttu-id="b5df7-232">Solução ou explicação</span><span class="sxs-lookup"><span data-stu-id="b5df7-232">Workaround or explanation</span></span> |
| --- | --- |
| <span data-ttu-id="b5df7-233">O zoom para 400% da área de trabalho oculta alguns dos botões de ação da exibição.</span><span class="sxs-lookup"><span data-stu-id="b5df7-233">Zooming to 400% on desktop hides some of the action buttons from view.</span></span> | <span data-ttu-id="b5df7-234">É recomendável usar uma lupa até que possamos dar suporte a esse nível de zoom.</span><span class="sxs-lookup"><span data-stu-id="b5df7-234">We recommend using a magnifier instead until we can support this zoom level.</span></span> |
| <span data-ttu-id="b5df7-235">Na guia **Folga**, o VoiceOver anuncia uma ação de botão enquanto lê o cabeçalho para a grade de folgas.</span><span class="sxs-lookup"><span data-stu-id="b5df7-235">On the **Time off** tab, voiceover announces a button action while reading the header for the time-off grid.</span></span> | <span data-ttu-id="b5df7-236">O cabeçalho e os elementos na grade são agrupados por ano e são recolhíveis.</span><span class="sxs-lookup"><span data-stu-id="b5df7-236">The header and elements within the grid are grouped by year, and they're collapsible.</span></span> <span data-ttu-id="b5df7-237">O VoiceOver interpreta isso como um item acionável, mas não é.</span><span class="sxs-lookup"><span data-stu-id="b5df7-237">Voiceover interprets this as an actionable item, but it isn't.</span></span> |
| <span data-ttu-id="b5df7-238">Na guia **Folga**, há um gesto de passar o dedo adicional ao navegar até o **Código de motivo** em uma nova solicitação.</span><span class="sxs-lookup"><span data-stu-id="b5df7-238">On the **Time off** tab, there's an extra swipe gesture when navigating to **Reason code** in a new request.</span></span> | <span data-ttu-id="b5df7-239">Não há controle oculto para que a navegação de deslizar o dedo esteja tentando acessar.</span><span class="sxs-lookup"><span data-stu-id="b5df7-239">There is no hidden control that the swipe navigation is trying to get to.</span></span> |
| <span data-ttu-id="b5df7-240">Na guia **Folga**, se você passar o dedo enquanto o calendário estiver aberto, terminará fora de controle, e não na parte superior em uma nova solicitação ou ao editar uma solicitação.</span><span class="sxs-lookup"><span data-stu-id="b5df7-240">On the **Time off** tab, if you swipe while the calendar is open, you end up outside the control instead of at the top in a new request or while editing a request.</span></span> | <span data-ttu-id="b5df7-241">Quando você atingir **Acessar hoje**, considere isso como o final do controle e o deslize o dedo na direção inversa para voltar ao início.</span><span class="sxs-lookup"><span data-stu-id="b5df7-241">When you reach **Go to today**, consider that to be the end of the control and swipe in the reverse direction to get back to the top.</span></span> |
| <span data-ttu-id="b5df7-242">Na guia **Chat**, o foco recai sobre a parte superior quando você insere uma data usando a ferramenta de assistência ou a navegação por teclado.</span><span class="sxs-lookup"><span data-stu-id="b5df7-242">On the **Chat** tab, the focus jumps back to the top when you enter a date while using the assistive tool or keyboard navigation.</span></span> | <span data-ttu-id="b5df7-243">Pressione a tecla Tab até acessar a área de entrada novamente.</span><span class="sxs-lookup"><span data-stu-id="b5df7-243">Tab until you reach your input area again.</span></span> |

## <a name="privacy-notice"></a><span data-ttu-id="b5df7-244">Aviso de privacidade</span><span class="sxs-lookup"><span data-stu-id="b5df7-244">Privacy notice</span></span>

### <a name="microsoft-language-understanding-intelligent-service-luis"></a><span data-ttu-id="b5df7-245">Serviço Inteligente de Reconhecimento Vocal (LUIS) da Microsoft</span><span class="sxs-lookup"><span data-stu-id="b5df7-245">Microsoft Language Understanding Intelligent Service (LUIS)</span></span>

<span data-ttu-id="b5df7-246">Com o bot do Dynamics 365 Human Resources no Microsoft Teams, as entradas de texto do usuário são analisadas para compreender a consulta/intenção subjacente.</span><span class="sxs-lookup"><span data-stu-id="b5df7-246">With the Dynamics 365 Human Resources bot in Microsoft Teams, the user’s text inputs are analyzed for understanding the underlying query/intent.</span></span> <span data-ttu-id="b5df7-247">A entrada do usuário, como "Pesquisar conta Contoso", é encaminhada para um dos Cognitive Services da Microsoft, chamado de Serviço Inteligente de Reconhecimento Vocal (LUIS).</span><span class="sxs-lookup"><span data-stu-id="b5df7-247">The user’s input such as “Search account Contoso” is routed to one of Microsoft’s Cognitive Service called Language Understanding Intelligent Service (LUIS).</span></span> <span data-ttu-id="b5df7-248">Leia mais sobre o LUIS  [aqui](https://www.luis.ai/).</span><span class="sxs-lookup"><span data-stu-id="b5df7-248">Read more about LUIS [here](https://www.luis.ai/).</span></span> <span data-ttu-id="b5df7-249">O serviço LUIS exclui a ambiguidade ou compreende a intenção da entrada do usuário (nesse caso, a intenção é encontrar informações) e a entidade de destino (nesse caso, a entidade pretendida é uma conta chamada Contoso).</span><span class="sxs-lookup"><span data-stu-id="b5df7-249">The LUIS service disambiguates or understands the intent of user input (in this case, the intent is to find information) and the target entity (in this case, the intended entity is an account named Contoso).</span></span> <span data-ttu-id="b5df7-250">Em seguida, essas informações são passadas para o [Azure Bot Framework](https://azure.microsoft.com/services/bot-service/) da Microsoft, que interage com os dados do Dynamics 365 Human Resources e recupera as informações desejadas para a consulta do usuário.</span><span class="sxs-lookup"><span data-stu-id="b5df7-250">This information is then passed on to Microsoft’s [Azure bot framework](https://azure.microsoft.com/services/bot-service/), which interacts with data from Dynamics 365 Human Resources and retrieves the desired information for the user query.</span></span> 

<span data-ttu-id="b5df7-251">Ao instalar e permitir o acesso ao uso do bot, você permite que o serviço LUIS e a estrutura de bot do Azure processem a intenção por trás da entrada, o que resulta em uma experiência aprimorada de conversa do usuário.</span><span class="sxs-lookup"><span data-stu-id="b5df7-251">By installing and allowing access to use of the bot, you agree to allow the LUIS service and Azure bot framework to process the intent behind the input,  which results in an enhanced conversational user experience.</span></span> <span data-ttu-id="b5df7-252">O serviço LUIS e a estrutura de bot do Azure têm vários níveis de conformidade em comparação com o Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="b5df7-252">The LUIS service and Azure bot framework may have varying levels of compliance compared to Dynamics 365 Human Resources.</span></span> <span data-ttu-id="b5df7-253">Embora o serviço LUIS tenha acesso a somente às consultas do usuário e não tenha sido desenvolvido para se conectar aos dados ou à conta do usuário do Dynamics 365 Human Resources, um usuário do bot do Dynamics 365 Human Resources poderia voluntariamente inserir uma consulta contendo Dados do Cliente, Dados Pessoais ou outros dados, e esse conteúdo da consulta poderia ser enviado para o serviço LUIS e para a estrutura de bot do Azure.</span><span class="sxs-lookup"><span data-stu-id="b5df7-253">While the LUIS service has access to only the user queries and is not designed to be connected to the user’s Dynamics 365 Human Resources data or account, a user of the Dynamics 365 Human Resources bot could voluntarily enter a query containing Customer Data, Personal Data, or other data and such query content could get sent to the LUIS service and the Azure bot framework.</span></span> 

<span data-ttu-id="b5df7-254">O conteúdo das consultas e das mensagens do usuário é mantido no sistema do LUIS por até 30 dias, criptografado em repouso e não é usado para treinamento ou melhoria de serviço.</span><span class="sxs-lookup"><span data-stu-id="b5df7-254">The content of user’s queries and messages is retained in LUIS system for a maximum of 30 days, is encrypted at rest, and is not used for training or service improvement.</span></span> <span data-ttu-id="b5df7-255">Leia mais sobre o Cognitive Services [aqui](https://azure.microsoft.com/services/cognitive-services/language-understanding-intelligent-service/).</span><span class="sxs-lookup"><span data-stu-id="b5df7-255">Read more about Cognitive Services [here](https://azure.microsoft.com/services/cognitive-services/language-understanding-intelligent-service/).</span></span> 

<span data-ttu-id="b5df7-256">Para gerenciar as configurações de administração de aplicativos no Microsoft Teams, vá para o [centro de administração do Microsoft Teams](https://admin.teams.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="b5df7-256">To manage admin settings for apps in Microsoft Teams, go to the [Microsoft Teams admin center](https://admin.teams.microsoft.com/).</span></span>

### <a name="microsoft-teams-azure-event-grid-and-azure-cosmos-db"></a><span data-ttu-id="b5df7-257">Microsoft Teams, Azure Event Grid e Azure Cosmos DB</span><span class="sxs-lookup"><span data-stu-id="b5df7-257">Microsoft Teams, Azure Event Grid, and Azure Cosmos DB</span></span>

<span data-ttu-id="b5df7-258">Ao usar o aplicativo Dynamics 365 Human Resources no Microsoft Teams, determinados dados do cliente podem fluir fora da região geográfica em que o serviço de Human Resources do locatário é implantado.</span><span class="sxs-lookup"><span data-stu-id="b5df7-258">When using the Dynamics 365 Human Resources app in Microsoft Teams, certain customer data may flow outside of the geographic region where your tenant’s Human Resources service is deployed.</span></span>

<span data-ttu-id="b5df7-259">O Dynamics 365 Human Resources transmite detalhes da solicitação de licença e da tarefa de fluxo de trabalho do funcionário para a Grade de Eventos do Microsoft Azure e o Microsoft Teams .</span><span class="sxs-lookup"><span data-stu-id="b5df7-259">Dynamics 365 Human Resources transmits the employee’s leave request and workflow task details to Microsoft Azure Event Grid and Microsoft Teams.</span></span> <span data-ttu-id="b5df7-260">Esses dados podem ser armazenados na Grade de Eventos do Microsoft Azure por até 24 horas e podem ser processados nos Estados Unidos, são criptografados em trânsito e em repouso, e não são usados pela Microsoft ou subprocessadores para treinamento ou melhorias de serviço.</span><span class="sxs-lookup"><span data-stu-id="b5df7-260">This data may be stored in Microsoft Azure Event Grid for up to 24 hours and will be processed in the United States, is encrypted in transit and at rest, and is not used by Microsoft or its subprocessors for training or service improvements.</span></span> <span data-ttu-id="b5df7-261">Para entender onde seus dados são armazenados no Teams, consulte: [Localização dos dados no Microsoft Teams](https://docs.microsoft.com/microsoftteams/location-of-data-in-teams?view=o365-worldwide&preserve-view=true).</span><span class="sxs-lookup"><span data-stu-id="b5df7-261">To understand where your data is stored in Teams, please see: [Location of data in Microsoft Teams](https://docs.microsoft.com/microsoftteams/location-of-data-in-teams?view=o365-worldwide&preserve-view=true).</span></span>

<span data-ttu-id="b5df7-262">Ao conversar com o bot de bate-papo no aplicativo Human Resources, o conteúdo da conversa pode ser armazenado no Azure Cosmos DB e transmitido ao Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="b5df7-262">While conversing with the chat bot in the Human Resources app, the conversation content may be stored in Azure Cosmos DB and transmitted to Microsoft Teams.</span></span> <span data-ttu-id="b5df7-263">Esses dados podem ser armazenados no Azure Cosmos DB por até 24 horas e podem ser processados fora da região geográfica onde o serviço do Human Resources do seu locatário está implantado, é criptografado em trânsito e em repouso e não é usado pela Microsoft ou seus subprocessadores para treinamento ou melhorias de serviço.</span><span class="sxs-lookup"><span data-stu-id="b5df7-263">This data may be stored in Azure Cosmos DB for up to 24 hours and may be processed outside of the geographic region where your tenant's Human Resources service is deployed, is encrypted in transit and at rest, and is not used by Microsoft or its subprocessors for training or service improvements.</span></span> <span data-ttu-id="b5df7-264">Para entender onde seus dados são armazenados no Teams, consulte: [Localização dos dados no Microsoft Teams](https://docs.microsoft.com/microsoftteams/location-of-data-in-teams?view=o365-worldwide&preserve-view=true).</span><span class="sxs-lookup"><span data-stu-id="b5df7-264">To understand where your data is stored in Teams, please see: [Location of data in Microsoft Teams](https://docs.microsoft.com/microsoftteams/location-of-data-in-teams?view=o365-worldwide&preserve-view=true).</span></span>
 
<span data-ttu-id="b5df7-265">Para restringir o acesso ao aplicativo Human Resources no Microsoft Teams para sua organização ou usuários dentro de sua organização, consulte [Gerenciar políticas de permissão de aplicativo no Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/teams-app-permission-policies).</span><span class="sxs-lookup"><span data-stu-id="b5df7-265">To restrict access to the Human Resources app in Microsoft Teams for your organization or users within your organization, see [Manage app permission policies in Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/teams-app-permission-policies).</span></span>

## <a name="see-also"></a><span data-ttu-id="b5df7-266">Consulte também</span><span class="sxs-lookup"><span data-stu-id="b5df7-266">See also</span></span>

[<span data-ttu-id="b5df7-267">Baixar e instalar o Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b5df7-267">Download and install Microsoft Teams</span></span>](https://support.office.com/article/download-and-install-microsoft-teams-422bf3aa-9ae8-46f1-83a2-e65720e1a34d)</br>
[<span data-ttu-id="b5df7-268">Central de ajuda do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b5df7-268">Microsoft Teams help center</span></span>](https://support.office.com/teams)</br>
[<span data-ttu-id="b5df7-269">Aplicativo Human Resources no Teams</span><span class="sxs-lookup"><span data-stu-id="b5df7-269">Human Resources app in Teams</span></span>](hr-admin-teams-leave-app.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]