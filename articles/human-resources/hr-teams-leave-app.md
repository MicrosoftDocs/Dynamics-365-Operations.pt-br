---
title: Gerenciar solicitações de licença no Teams
description: Este tópico mostra como solicitar licenças no aplicativo do Dynamics 365 Human Resources no Microsoft Teams.
author: andreabichsel
manager: AnnBe
ms.date: 09/03/2020
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
ms.openlocfilehash: 0fbf44fe35af3147fd5fb478b6cbfc5a5d0b109d
ms.sourcegitcommit: 5b620f670ac0f403a0fdcdeb9c3f970b163191ee
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/04/2020
ms.locfileid: "3766751"
---
# <a name="manage-leave-requests-in-teams"></a><span data-ttu-id="1228e-103">Gerenciar solicitações de licença no Teams</span><span class="sxs-lookup"><span data-stu-id="1228e-103">Manage leave requests in Teams</span></span>

[!include [banner](includes/preview-feature.md)]

<span data-ttu-id="1228e-104">O aplicativo Microsoft Dynamics 365 Human Resources no Microsoft Teams permite solicitar folgas rapidamente, além de visualizar as informações de saldo de folgas no Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="1228e-104">The Microsoft Dynamics 365 Human Resources app in Microsoft Teams lets you quickly request time off and view your time-off balance information right in Microsoft Teams.</span></span> <span data-ttu-id="1228e-105">Você pode interagir com um bot para solicitar informações.</span><span class="sxs-lookup"><span data-stu-id="1228e-105">You can interact with a bot to request information.</span></span> <span data-ttu-id="1228e-106">A guia **Folga** fornece informações mais detalhadas.</span><span class="sxs-lookup"><span data-stu-id="1228e-106">The **Time off** tab provides more detailed information.</span></span>

## <a name="install-the-app"></a><span data-ttu-id="1228e-107">Instalar o aplicativo</span><span class="sxs-lookup"><span data-stu-id="1228e-107">Install the app</span></span>

<span data-ttu-id="1228e-108">Você pode encontrar o aplicativo Human Resources na loja do Teams.</span><span class="sxs-lookup"><span data-stu-id="1228e-108">You can find the Human Resources app in the Teams store.</span></span>

1. <span data-ttu-id="1228e-109">No Microsoft Teams, selecione as reticências.</span><span class="sxs-lookup"><span data-stu-id="1228e-109">In Microsoft Teams, select the ellipses.</span></span>

   ![Reticências do aplicativo de licença do Human Resources Teams](./media/hr-teams-leave-app-ellipses.png)
 
2. <span data-ttu-id="1228e-111">Procure Dynamics 365 Human Resources, e selecione o título **Human Resources**.</span><span class="sxs-lookup"><span data-stu-id="1228e-111">Search for Dynamics 365 Human Resources, and then select the **Human Resources** tile.</span></span>

   ![Título do HR do aplicativo de licença do Human Resources Teams](./media/hr-teams-leave-app-human-resources-tile.png)

3. <span data-ttu-id="1228e-113">Selecione o botão **Adicionar** para instalar o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="1228e-113">Select the **Add** button to install the app.</span></span>

   ![Instalar o aplicativo de licença do Human Resources Teams](./media/hr-teams-leave-app-in-store.png)

<span data-ttu-id="1228e-115">Se o aplicativo não fizer logon automaticamente, selecione a guia **Configurações** para entrar.</span><span class="sxs-lookup"><span data-stu-id="1228e-115">If the app doesn't automatically sign you in, select the **Settings** tab to sign in.</span></span>

![Guia Configurações do aplicativo de licença do Human Resources Teams](./media/hr-teams-leave-app-settings-tab.png)

> [!NOTE]
> <span data-ttu-id="1228e-117">Caso você não veja uma caixa de diálogo de entrada, verifique as configurações do navegador para permitir janelas pop-up.</span><span class="sxs-lookup"><span data-stu-id="1228e-117">If you don’t see a sign-in dialog box, check your browser settings to allow pop-ups.</span></span> 

<span data-ttu-id="1228e-118">Se você tiver acesso a mais de uma instância do Human Resources, poderá selecionar a qual ambiente deseja se conectar na guia **Configurações**.</span><span class="sxs-lookup"><span data-stu-id="1228e-118">If you have access to more than one instance of Human Resources, you can select which environment you want to connect to in the **Settings** tab.</span></span>

> [!WARNING]
> <span data-ttu-id="1228e-119">Atualmente o aplicativo não oferece suporte à função de segurança do Administrador do Sistema e exibirá uma mensagem de erro caso você entre com uma conta de Administrador do Sistema.</span><span class="sxs-lookup"><span data-stu-id="1228e-119">The app doesn't currently support the System Administrator security role, and will display an error message if you sign in with a System Administrator account.</span></span> <span data-ttu-id="1228e-120">Para entrar com uma conta diferente, na guia **Configurações**, selecione o botão **Alternar contas** e entre com uma conta de usuário sem os privilégios de Administrador do Sistema.</span><span class="sxs-lookup"><span data-stu-id="1228e-120">To sign in with a different account, on the **Settings** tab, select the **Switch accounts** button, and then sign in with a user account that doesn’t have System Administrator privileges.</span></span>
 
## <a name="use-the-bot"></a><span data-ttu-id="1228e-121">Usar o bot</span><span class="sxs-lookup"><span data-stu-id="1228e-121">Use the bot</span></span>

<span data-ttu-id="1228e-122">Depois de instalar o aplicativo, será exibida uma mensagem de boas-vindas, informando os tipos de ações que o bot pode assumir em seu nome.</span><span class="sxs-lookup"><span data-stu-id="1228e-122">After the app installs, a welcome message appears, letting you know the types of actions the bot can take on your behalf.</span></span>

![Mensagem de boas-vindas do bot do aplicativo de licença do Human Resources Teams](./media/hr-teams-leave-app-bot.png)
 
> [!NOTE]
> <span data-ttu-id="1228e-124">Talvez você precise entrar na primeira interação com o bot.</span><span class="sxs-lookup"><span data-stu-id="1228e-124">When first interacting with the bot, you might need to sign in.</span></span> <span data-ttu-id="1228e-125">Caso você não veja uma caixa de diálogo de entrada, verifique as configurações do navegador para permitir janelas pop-up.</span><span class="sxs-lookup"><span data-stu-id="1228e-125">If you don’t see a sign-in dialog box, check your browser settings to allow pop-ups.</span></span>

<span data-ttu-id="1228e-126">Você pode pedir para o bot:</span><span class="sxs-lookup"><span data-stu-id="1228e-126">You can ask the bot to:</span></span>

- <span data-ttu-id="1228e-127">Mostrar informações do saldo de folgas para cada tipo de licença na qual você está inscrito.</span><span class="sxs-lookup"><span data-stu-id="1228e-127">Show time-off balance information for each leave type you're enrolled in.</span></span>

   ![Mostrar saldos do aplicativo de licença do Human Resources Teams](./media/hr-teams-leave-app-bot-balances.png)
 
- <span data-ttu-id="1228e-129">Mostrar detalhes adicionais sobre um tipo de licença específico.</span><span class="sxs-lookup"><span data-stu-id="1228e-129">Show additional details about a specific leave type.</span></span>

   ![Mostrar detalhes do aplicativo de licença do Human Resources Teams](./media/hr-teams-leave-app-bot-details.png)

- <span data-ttu-id="1228e-131">Iniciar uma solicitação de licença para você.</span><span class="sxs-lookup"><span data-stu-id="1228e-131">Start a leave request for you.</span></span>

   ![Solicitar licença no aplicativo de licença do Human Resources Teams](./media/hr-teams-leave-app-bot-request.png)
 
<span data-ttu-id="1228e-133">Depois de iniciar uma solicitação de licença, você pode ajustar os dias diretamente no cartão.</span><span class="sxs-lookup"><span data-stu-id="1228e-133">After you start a leave request, you can adjust the days right within the card.</span></span>

![Editar solicitação no aplicativo de licença do Human Resources Teams](./media/hr-teams-leave-app-bot-edit.png)
 
<span data-ttu-id="1228e-135">Após inserir as informações, selecione **Enviar** para enviá-las para aprovação.</span><span class="sxs-lookup"><span data-stu-id="1228e-135">When you're done entering information, select **Submit** to submit it for approval.</span></span> <span data-ttu-id="1228e-136">Você também pode selecionar **Salvar como rascunho** para continuar depois.</span><span class="sxs-lookup"><span data-stu-id="1228e-136">You can also select **Save as draft** to come back to it later.</span></span>

![Enviar solicitação no aplicativo de licença do Human Resources Teams](./media/hr-teams-leave-app-bot-submit.png)

## <a name="manage-your-leave-in-teams"></a><span data-ttu-id="1228e-138">Gerenciar a sua licença no Teams</span><span class="sxs-lookup"><span data-stu-id="1228e-138">Manage your leave in Teams</span></span>

<span data-ttu-id="1228e-139">A guia **Folga** permite exibir:</span><span class="sxs-lookup"><span data-stu-id="1228e-139">The **Time off** tab allows you to view:</span></span>

- <span data-ttu-id="1228e-140">Informações do saldo para cada tipo de licença na qual você está inscrito</span><span class="sxs-lookup"><span data-stu-id="1228e-140">Balance information for each leave type you're enrolled in</span></span>

- <span data-ttu-id="1228e-141">Solicitações de licença futuras</span><span class="sxs-lookup"><span data-stu-id="1228e-141">Upcoming leave requests</span></span>

- <span data-ttu-id="1228e-142">Solicitações de folga</span><span class="sxs-lookup"><span data-stu-id="1228e-142">Time-off requests</span></span>

- <span data-ttu-id="1228e-143">Rascunho de solicitações de licença</span><span class="sxs-lookup"><span data-stu-id="1228e-143">Draft leave requests</span></span>

![Guia Folga do aplicativo de licença do Human Resources Teams](./media/hr-teams-leave-app-timeoff-tab.png)
 
### <a name="create-a-new-request"></a><span data-ttu-id="1228e-145">Criar uma solicitação</span><span class="sxs-lookup"><span data-stu-id="1228e-145">Create a new request</span></span>

1. <span data-ttu-id="1228e-146">Para criar uma solicitação de licença, selecione **Nova solicitação**.</span><span class="sxs-lookup"><span data-stu-id="1228e-146">To create a new leave request, select **New request**.</span></span>

   ![Nova solicitação no aplicativo de licença do Human Resources Teams](./media/hr-teams-leave-app-timeoff-tab-new.png)

2. <span data-ttu-id="1228e-148">Insira os dias que você deseja solicitar folga e depois selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="1228e-148">Enter the day or days you want to take off, and then select **Add**.</span></span>

   ![Adicionar folga no aplicativo de licença do Human Resources Teams](./media/hr-teams-leave-app-timeoff-tab-add.png)

3. <span data-ttu-id="1228e-150">Se aplicável, insira um código de motivo.</span><span class="sxs-lookup"><span data-stu-id="1228e-150">If applicable, enter a reason code.</span></span> <span data-ttu-id="1228e-151">Insira também comentários e adicione anexos.</span><span class="sxs-lookup"><span data-stu-id="1228e-151">Also enter any comments and add any attachments.</span></span>

4. <span data-ttu-id="1228e-152">Após inserir as informações, digite **Enviar** para enviá-la para aprovação.</span><span class="sxs-lookup"><span data-stu-id="1228e-152">When you're done entering information, type **Submit** to submit it for approval.</span></span> <span data-ttu-id="1228e-153">Você também pode digitar **Salvar como rascunho** para continuar depois.</span><span class="sxs-lookup"><span data-stu-id="1228e-153">You can also type **Save as draft** to come back to it later.</span></span>

### <a name="manage-draft-requests"></a><span data-ttu-id="1228e-154">Gerenciar solicitações em rascunho</span><span class="sxs-lookup"><span data-stu-id="1228e-154">Manage draft requests</span></span>

1. <span data-ttu-id="1228e-155">Selecione a guia **Rascunhos**.</span><span class="sxs-lookup"><span data-stu-id="1228e-155">Select the **Drafts** tab.</span></span>

   ![Guia Rascunhos do aplicativo de licença do Human Resources Teams](./media/hr-teams-leave-app-drafts-tab.png)

2. <span data-ttu-id="1228e-157">Selecione o lápis para editar a solicitação, ou selecione a lixeira para excluí-la.</span><span class="sxs-lookup"><span data-stu-id="1228e-157">Select the pencil to edit the request, or select the trash can to delete the request.</span></span>

3. <span data-ttu-id="1228e-158">Faça todas as alterações necessárias.</span><span class="sxs-lookup"><span data-stu-id="1228e-158">Make any necessary changes.</span></span> <span data-ttu-id="1228e-159">Após inserir as informações, digite **Enviar** para enviá-la para aprovação.</span><span class="sxs-lookup"><span data-stu-id="1228e-159">When you're done entering information, type **Submit** to submit it for approval.</span></span> <span data-ttu-id="1228e-160">Você também pode selecionar **Salvar como rascunho** para continuar depois.</span><span class="sxs-lookup"><span data-stu-id="1228e-160">You can also select **Save as draft** to come back to it later.</span></span>

   ![Editar rascunho no aplicativo de licença do Human Resources Teams](./media/hr-teams-leave-app-drafts-edit.png)
   
### <a name="teams-notifications"></a><span data-ttu-id="1228e-162">Notificações do Teams</span><span class="sxs-lookup"><span data-stu-id="1228e-162">Teams notifications</span></span>

<span data-ttu-id="1228e-163">Quando você ou um trabalhador para o qual você é um aprovador enviar uma solicitação de licença, você receberá uma notificação no aplicativo Human Resources no Teams.</span><span class="sxs-lookup"><span data-stu-id="1228e-163">When you or a worker you're an approver for submits a leave request, you'll receive a notification in the Human Resources app in Teams.</span></span> <span data-ttu-id="1228e-164">Você pode selecionar a notificação para exibi-la.</span><span class="sxs-lookup"><span data-stu-id="1228e-164">You can select the notification to view it.</span></span> <span data-ttu-id="1228e-165">As notificações também aparecem na área **Chat** .</span><span class="sxs-lookup"><span data-stu-id="1228e-165">Notifications also appear in the **Chat** area.</span></span>

<span data-ttu-id="1228e-166">Se você for aprovador, poderá selecionar **Aprovar** ou **Negar** na notificação.</span><span class="sxs-lookup"><span data-stu-id="1228e-166">If you're an approver, you can select **Approve** or **Deny** in the notification.</span></span> <span data-ttu-id="1228e-167">Você também pode fornecer uma mensagem opcional.</span><span class="sxs-lookup"><span data-stu-id="1228e-167">You can also provide an optional message.</span></span>

![Deixar uma notificação de solicitação no aplicativo Human Resources no Teams](./media/hr-teams-leave-app-notification.png)

## <a name="view-your-teams-leave-calendar"></a><span data-ttu-id="1228e-169">Exibir o calendário de licença da equipe</span><span class="sxs-lookup"><span data-stu-id="1228e-169">View your team's leave calendar</span></span>

<span data-ttu-id="1228e-170">Se você for um gerente com subordinados diretos, poderá exibir folgas aprovadas e pendentes da sua equipe.</span><span class="sxs-lookup"><span data-stu-id="1228e-170">If you're a manager with direct reports, you can view your team's approved and pending time off.</span></span>

1. <span data-ttu-id="1228e-171">No aplicativo Human Resources no Teams, selecione **Folga** .</span><span class="sxs-lookup"><span data-stu-id="1228e-171">In the Human Resources app in Teams, select **Time off**.</span></span>

2. <span data-ttu-id="1228e-172">Selecione **Calendário da equipe** .</span><span class="sxs-lookup"><span data-stu-id="1228e-172">Select **Team calendar**.</span></span>

   ![Exibir calendário no aplicativo Human Resources do Teams](./media/hr-teams-leave-app-view-calendar.png)

<span data-ttu-id="1228e-174">O calendário exibe as folgas aprovadas e pendentes dos subordinados diretos.</span><span class="sxs-lookup"><span data-stu-id="1228e-174">The calendar displays your direct reports' approved and pending time off.</span></span>

![Calendário de folgas no aplicativo Human Resources do Teams](./media/hr-teams-leave-app-calendar.png)

## <a name="privacy-notice"></a><span data-ttu-id="1228e-176">Aviso de privacidade</span><span class="sxs-lookup"><span data-stu-id="1228e-176">Privacy notice</span></span>

### <a name="microsoft-language-understanding-intelligent-service-luis"></a><span data-ttu-id="1228e-177">Serviço Inteligente de Reconhecimento Vocal (LUIS) da Microsoft</span><span class="sxs-lookup"><span data-stu-id="1228e-177">Microsoft Language Understanding Intelligent Service (LUIS)</span></span>

<span data-ttu-id="1228e-178">Com o bot do Dynamics 365 Human Resources no Microsoft Teams, as entradas de texto do usuário são analisadas para compreender a consulta/intenção subjacente.</span><span class="sxs-lookup"><span data-stu-id="1228e-178">With the Dynamics 365 Human Resources bot in Microsoft Teams, the user’s text inputs are analyzed for understanding the underlying query/intent.</span></span> <span data-ttu-id="1228e-179">A entrada do usuário, como "Pesquisar conta Contoso", é encaminhada para um dos Cognitive Services da Microsoft, chamado de Serviço Inteligente de Reconhecimento Vocal (LUIS).</span><span class="sxs-lookup"><span data-stu-id="1228e-179">The user’s input such as “Search account Contoso” is routed to one of Microsoft’s Cognitive Service called Language Understanding Intelligent Service (LUIS).</span></span> <span data-ttu-id="1228e-180">Leia mais sobre o LUIS  [aqui](https://www.luis.ai/).</span><span class="sxs-lookup"><span data-stu-id="1228e-180">Read more about LUIS [here](https://www.luis.ai/).</span></span> <span data-ttu-id="1228e-181">O serviço LUIS exclui a ambiguidade ou compreende a intenção da entrada do usuário (nesse caso, a intenção é encontrar informações) e a entidade de destino (nesse caso, a entidade pretendida é uma conta chamada Contoso).</span><span class="sxs-lookup"><span data-stu-id="1228e-181">The LUIS service disambiguates or understands the intent of user input (in this case, the intent is to find information) and the target entity (in this case, the intended entity is an account named Contoso).</span></span> <span data-ttu-id="1228e-182">Em seguida, essas informações são passadas para o [Azure Bot Framework](https://azure.microsoft.com/services/bot-service/) da Microsoft, que interage com os dados do Dynamics 365 Human Resources e recupera as informações desejadas para a consulta do usuário.</span><span class="sxs-lookup"><span data-stu-id="1228e-182">This information is then passed on to Microsoft’s [Azure bot framework](https://azure.microsoft.com/services/bot-service/), which interacts with data from Dynamics 365 Human Resources and retrieves the desired information for the user query.</span></span> 

<span data-ttu-id="1228e-183">Ao instalar e permitir o acesso ao uso do bot, você permite que o serviço LUIS e a estrutura de bot do Azure processem a intenção por trás da entrada, o que resulta em uma experiência aprimorada de conversa do usuário.</span><span class="sxs-lookup"><span data-stu-id="1228e-183">By installing and allowing access to use of the bot, you agree to allow the LUIS service and Azure bot framework to process the intent behind the input,  which results in an enhanced conversational user experience.</span></span> <span data-ttu-id="1228e-184">O serviço LUIS e a estrutura de bot do Azure têm vários níveis de conformidade em comparação com o Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="1228e-184">The LUIS service and Azure bot framework may have varying levels of compliance compared to Dynamics 365 Human Resources.</span></span> <span data-ttu-id="1228e-185">Embora o serviço LUIS tenha acesso a somente às consultas do usuário e não tenha sido desenvolvido para se conectar aos dados ou à conta do usuário do Dynamics 365 Human Resources, um usuário do bot do Dynamics 365 Human Resources poderia voluntariamente inserir uma consulta contendo Dados do Cliente, Dados Pessoais ou outros dados, e esse conteúdo da consulta poderia ser enviado para o serviço LUIS e para a estrutura de bot do Azure.</span><span class="sxs-lookup"><span data-stu-id="1228e-185">While the LUIS service has access to only the user queries and is not designed to be connected to the user’s Dynamics 365 Human Resources data or account, a user of the Dynamics 365 Human Resources bot could voluntarily enter a query containing Customer Data, Personal Data, or other data and such query content could get sent to the LUIS service and the Azure bot framework.</span></span> 

<span data-ttu-id="1228e-186">O conteúdo das consultas e das mensagens do usuário é mantido no sistema do LUIS por até 30 dias, criptografado em repouso e não é usado para treinamento ou melhoria de serviço.</span><span class="sxs-lookup"><span data-stu-id="1228e-186">The content of user’s queries and messages is retained in LUIS system for a maximum of 30 days, is encrypted at rest, and is not used for training or service improvement.</span></span> <span data-ttu-id="1228e-187">Leia mais sobre o Cognitive Services [aqui](https://azure.microsoft.com/services/cognitive-services/language-understanding-intelligent-service/).</span><span class="sxs-lookup"><span data-stu-id="1228e-187">Read more about Cognitive Services [here](https://azure.microsoft.com/services/cognitive-services/language-understanding-intelligent-service/).</span></span> 

<span data-ttu-id="1228e-188">Para gerenciar as configurações de administração de aplicativos no Microsoft Teams, vá para o [centro de administração do Microsoft Teams](https://admin.teams.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="1228e-188">To manage admin settings for apps in Microsoft Teams, go to the [Microsoft Teams admin center](https://admin.teams.microsoft.com/).</span></span>

### <a name="microsoft-azure-event-grid-and-microsoft-teams"></a><span data-ttu-id="1228e-189">Grade de Eventos do Microsoft Azure e Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="1228e-189">Microsoft Azure Event Grid and Microsoft Teams</span></span>

<span data-ttu-id="1228e-190">Ao usar o recurso de notificações do aplicativo Dynamics 365 Human Resources no Teams, determinados dados do cliente fluirão fora da região geográfica em que o serviço de Human Resources do locatário é implantado.</span><span class="sxs-lookup"><span data-stu-id="1228e-190">When using the notifications feature for the Dynamics 365 Human Resources app in Teams, certain customer data will flow outside of the geographic region where your tenant’s Human Resources service is deployed.</span></span> <span data-ttu-id="1228e-191">O Dynamics 365 Human Resources transmite detalhes da solicitação de licença e da tarefa de fluxo de trabalho do funcionário para a Grade de Eventos do Microsoft Azure e o Microsoft Teams .</span><span class="sxs-lookup"><span data-stu-id="1228e-191">Dynamics 365 Human Resources transmits the employee’s leave request and workflow task details to Microsoft Azure Event Grid and Microsoft Teams.</span></span> <span data-ttu-id="1228e-192">Esses dados podem ser armazenados por até 24 horas e processados nos Estados Unidos, são criptografados em trânsito e em repouso, e não são usados pela Microsoft ou subprocessadores para treinamento ou melhorias de serviço.</span><span class="sxs-lookup"><span data-stu-id="1228e-192">This data may be stored for up to 24 hours and processed in the United States, is encrypted in transit and at rest, and is not used by Microsoft or its subprocessors for training or service improvements.</span></span>

## <a name="see-also"></a><span data-ttu-id="1228e-193">Consulte também</span><span class="sxs-lookup"><span data-stu-id="1228e-193">See also</span></span>

[<span data-ttu-id="1228e-194">Baixar e instalar o Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="1228e-194">Download and install Microsoft Teams</span></span>](https://support.office.com/article/download-and-install-microsoft-teams-422bf3aa-9ae8-46f1-83a2-e65720e1a34d)</br>
[<span data-ttu-id="1228e-195">Central de ajuda do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="1228e-195">Microsoft Teams help center</span></span>](https://support.office.com/teams)</br>
[<span data-ttu-id="1228e-196">Aplicativo Human Resources no Teams</span><span class="sxs-lookup"><span data-stu-id="1228e-196">Human Resources app in Teams</span></span>](hr-admin-teams-leave-app.md)
