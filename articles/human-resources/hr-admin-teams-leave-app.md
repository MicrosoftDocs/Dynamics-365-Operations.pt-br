---
title: Aplicativo Human Resources no Teams
description: Este tópico apresenta o aplicativo Microsoft Dynamics 365 Human Resources no Microsoft Teams.
author: andreabichsel
manager: AnnBe
ms.date: 09/30/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: FeatureManagementWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-05-18
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 51f04e553da822c4e09d31bcd72c71b674ad1f1b
ms.sourcegitcommit: b6ab46f6e5ce60e2c3d70a348827eaf60c84cae2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/01/2020
ms.locfileid: "3930008"
---
# <a name="human-resources-app-in-teams"></a><span data-ttu-id="73a5f-103">Aplicativo Human Resources no Teams</span><span class="sxs-lookup"><span data-stu-id="73a5f-103">Human Resources app in Teams</span></span>

[!include [banner](includes/preview-feature.md)]

<span data-ttu-id="73a5f-104">O aplicativo Microsoft Dynamics 365 Human Resources no Microsoft Teams permite aos funcionários solicitar folgas rapidamente, além de visualizar suas informações de saldo de folgas no Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="73a5f-104">The Microsoft Dynamics 365 Human Resources app in Microsoft Teams lets employees quickly request time off and view their time-off balance information in Microsoft Teams.</span></span> <span data-ttu-id="73a5f-105">Os funcionários podem interagir com um bot para solicitar informações.</span><span class="sxs-lookup"><span data-stu-id="73a5f-105">Employees can interact with a bot to request information.</span></span> <span data-ttu-id="73a5f-106">A guia **Folga** fornece informações mais detalhadas.</span><span class="sxs-lookup"><span data-stu-id="73a5f-106">The **Time off** tab provides more detailed information.</span></span> <span data-ttu-id="73a5f-107">Além disso, eles podem enviar às pessoas informações sobre suas próximas folgas em equipes e bate-papos fora do aplicativo do Human Resources.</span><span class="sxs-lookup"><span data-stu-id="73a5f-107">In addition, they can send people information about upcoming time off in teams and chats outside the Human Resources app.</span></span>

![Bot do aplicativo de licenças do Human Resources Teams](./media/hr-admin-teams-leave-app-bot.png)

![Guia Folga do aplicativo de licença do Human Resources Teams](./media/hr-teams-leave-app-timeoff-tab.png)

![Cartão de solicitação de licença do Human Resources](./media/hr-teams-leave-app-chat-card.png)

## <a name="install-and-setup"></a><span data-ttu-id="73a5f-111">Instalação e configuração</span><span class="sxs-lookup"><span data-stu-id="73a5f-111">Install and setup</span></span>

<span data-ttu-id="73a5f-112">Você pode encontrar o aplicativo Human Resources na loja do Teams.</span><span class="sxs-lookup"><span data-stu-id="73a5f-112">You can find the Human Resources app in the Teams store.</span></span> <span data-ttu-id="73a5f-113">Para obter informações sobre como instalar o aplicativo do Teams, consulte [Gerenciar solicitações de licença no Teams](hr-teams-leave-app.md).</span><span class="sxs-lookup"><span data-stu-id="73a5f-113">For information about installing the Teams app, see [Manage leave requests in Teams](hr-teams-leave-app.md).</span></span>

<span data-ttu-id="73a5f-114">Para obter informações sobre como gerenciar permissões de aplicativo no Teams, consulte [Gerenciar políticas de permissão de aplicativo no Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/teams-app-permission-policies).</span><span class="sxs-lookup"><span data-stu-id="73a5f-114">For information about managing app permissions in Teams, see [Manage app permission policies in Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/teams-app-permission-policies).</span></span>

## <a name="enable-notifications-for-the-human-resources-app-in-teams"></a><span data-ttu-id="73a5f-115">Habilitar notificações para o aplicativo de recursos humanos no Teams</span><span class="sxs-lookup"><span data-stu-id="73a5f-115">Enable notifications for the Human Resources app in Teams</span></span>

<span data-ttu-id="73a5f-116">Para que os usuários recebam notificações de solicitação de licença no aplicativo Team, você deve habilitar notificações no Human Resources.</span><span class="sxs-lookup"><span data-stu-id="73a5f-116">If you want users to receive leave request notifications in the Teams app, you must enable notifications in Human Resources.</span></span>

>[!NOTE]
><span data-ttu-id="73a5f-117">Somente os usuários que estiverem conectados ao Teams e usando o aplicativo Human Resources Teams receberão notificações.</span><span class="sxs-lookup"><span data-stu-id="73a5f-117">Only users who are signed into Teams and using the Human Resources Teams app will receive notifications.</span></span>

1. <span data-ttu-id="73a5f-118">No Human Resources, selecione **Administração do sistema**.</span><span class="sxs-lookup"><span data-stu-id="73a5f-118">In Human Resources, select **System administration**.</span></span>

2. <span data-ttu-id="73a5f-119">Selecione **Links**.</span><span class="sxs-lookup"><span data-stu-id="73a5f-119">Select **Links**.</span></span>

3. <span data-ttu-id="73a5f-120">Em **Configuração** , selecione **Parâmetros do sistema** .</span><span class="sxs-lookup"><span data-stu-id="73a5f-120">Under **Setup**, select **System parameters**.</span></span>

4. <span data-ttu-id="73a5f-121">Na guia **Geral**, defina **Habilitar notificações para o aplicativo Teams** como **Sim** .</span><span class="sxs-lookup"><span data-stu-id="73a5f-121">On the **General** tab, set **Enable notifications for Teams app** to **Yes**.</span></span>

   ![Habilitar notificações do aplicativo Teams nos Parâmetros do Sistema](./media/hr-admin-teams-leave-app-enable-notifications.png)

5. <span data-ttu-id="73a5f-123">Para ativar notificações do Teams para todos os usuários, selecione **Sim** no prompt.</span><span class="sxs-lookup"><span data-stu-id="73a5f-123">To turn on Teams notifications for all users, select **Yes** at the prompt.</span></span>

   ![Habilitar notificações do Teams para todos os usuários](./media/hr-admin-teams-leave-app-notifications-all-users.png)

### <a name="turn-teams-notifications-on-or-off-for-individual-users"></a><span data-ttu-id="73a5f-125">Ativar ou desativar notificações do Teams para usuários individuais</span><span class="sxs-lookup"><span data-stu-id="73a5f-125">Turn Teams notifications on or off for individual users</span></span>

<span data-ttu-id="73a5f-126">Depois de habilitar notificações para o aplicativo Human Resources Team, você pode ativar ou desativar notificações para usuários individuais.</span><span class="sxs-lookup"><span data-stu-id="73a5f-126">After you've enabled notifications for the Human Resources Teams app, you can turn notifications on or off for individual users.</span></span>

1. <span data-ttu-id="73a5f-127">No Human Resources, selecione **Administração do sistema**.</span><span class="sxs-lookup"><span data-stu-id="73a5f-127">In Human Resources, select **System administration**.</span></span>

2. <span data-ttu-id="73a5f-128">Selecione **Links**.</span><span class="sxs-lookup"><span data-stu-id="73a5f-128">Select **Links**.</span></span>

3. <span data-ttu-id="73a5f-129">Em **Usuários**, selecione **Opções do usuário** .</span><span class="sxs-lookup"><span data-stu-id="73a5f-129">Under **Users**, select **User options**.</span></span>

4. <span data-ttu-id="73a5f-130">Selecione a guia **Fluxo de trabalho**.</span><span class="sxs-lookup"><span data-stu-id="73a5f-130">Select the **Workflow** tab.</span></span>

5. <span data-ttu-id="73a5f-131">Defina **Habilitar notificações para o aplicativo Teams** como **Sim** para habilitar notificações para o usuário ou como **Não** para desabilitar notificações para o usuário.</span><span class="sxs-lookup"><span data-stu-id="73a5f-131">Set **Enable notifications for Teams app** to **Yes** to enable notifications for the user or **No** to disable notifications for the user.</span></span>

   ![Habilitar notificações do aplicativo Teams na guia Fluxo de trabalho de opções do usuário](./media/hr-admin-teams-leave-app-notifications.png)

6. <span data-ttu-id="73a5f-133">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="73a5f-133">Select **Save**.</span></span>

## <a name="known-issues"></a><span data-ttu-id="73a5f-134">Problemas conhecidos</span><span class="sxs-lookup"><span data-stu-id="73a5f-134">Known issues</span></span>

| <span data-ttu-id="73a5f-135">Problema</span><span class="sxs-lookup"><span data-stu-id="73a5f-135">Issue</span></span> | <span data-ttu-id="73a5f-136">Status</span><span class="sxs-lookup"><span data-stu-id="73a5f-136">Status</span></span> |
| --- | --- |
| <span data-ttu-id="73a5f-137">O rolamento horizontal não funciona em telefones Android</span><span class="sxs-lookup"><span data-stu-id="73a5f-137">Horizontal scrolling doesn't work on Android phones</span></span> | <span data-ttu-id="73a5f-138">O rolamento horizontal não é um problema em dispositivos iOS ou de desktop.</span><span class="sxs-lookup"><span data-stu-id="73a5f-138">Horizontal scrolling isn't an issue on iOS or desktop devices.</span></span> <span data-ttu-id="73a5f-139">Estamos trabalhando em uma correção para o Android.</span><span class="sxs-lookup"><span data-stu-id="73a5f-139">We're working on a fix for Android.</span></span> |
| <span data-ttu-id="73a5f-140">O saldo exibido ao enviar folga para uma data futura está incorreto.</span><span class="sxs-lookup"><span data-stu-id="73a5f-140">The balance is incorrect when submitting time off for a future date.</span></span> | <span data-ttu-id="73a5f-141">A previsão ainda não está disponível.</span><span class="sxs-lookup"><span data-stu-id="73a5f-141">Forecasting isn't yet available.</span></span> <span data-ttu-id="73a5f-142">O saldo é exibido para a data atual.</span><span class="sxs-lookup"><span data-stu-id="73a5f-142">The balance displays for the current date.</span></span> |
| <span data-ttu-id="73a5f-143">Não é possível cancelar uma solicitação **Em revisão**.</span><span class="sxs-lookup"><span data-stu-id="73a5f-143">Unable to cancel an **In review** request.</span></span> | <span data-ttu-id="73a5f-144">Atualmente, essa funcionalidade não tem suporte e será adicionada em uma versão futura.</span><span class="sxs-lookup"><span data-stu-id="73a5f-144">This functionality isn't currently supported and will be added in a future release.</span></span> |
| <span data-ttu-id="73a5f-145">As informações de saldo são calculadas a partir de hoje.</span><span class="sxs-lookup"><span data-stu-id="73a5f-145">Balance information is calculated as of today.</span></span> | <span data-ttu-id="73a5f-146">O sistema atualmente não exibe os saldos a partir do período de acúmulo, mesmo se estiver configurado nos parâmetros de Licença e ausência.</span><span class="sxs-lookup"><span data-stu-id="73a5f-146">The system currently doesn't display balances as of the accrual period, even if it's configured in Leave and absence parameters.</span></span> |

## <a name="troubleshooting"></a><span data-ttu-id="73a5f-147">Solução de problemas</span><span class="sxs-lookup"><span data-stu-id="73a5f-147">Troubleshooting</span></span>

<span data-ttu-id="73a5f-148">Se um usuário tiver problemas para entrar ou ao usar o aplicativo do Human Resources no Teams, tente seguir estas instruções de solução de problemas.</span><span class="sxs-lookup"><span data-stu-id="73a5f-148">If a user is having trouble signing into or using the Human Resources Teams app, try following these troubleshooting instructions.</span></span> <span data-ttu-id="73a5f-149">Se você ainda tiver problemas após a solução de problemas, contate o Suporte.</span><span class="sxs-lookup"><span data-stu-id="73a5f-149">If you're still having problems after troubleshooting, contact Support.</span></span> <span data-ttu-id="73a5f-150">Para obter mais informações, consulte [Obter suporte](hr-admin-troubleshooting-support.md).</span><span class="sxs-lookup"><span data-stu-id="73a5f-150">For more information, see [Get support](hr-admin-troubleshooting-support.md).</span></span>

### <a name="cant-sign-into-the-human-resources-app-in-teams"></a><span data-ttu-id="73a5f-151">Não é possível entrar no aplicativo do Human Resources no Teams</span><span class="sxs-lookup"><span data-stu-id="73a5f-151">Can't sign into the Human Resources app in Teams</span></span>

<span data-ttu-id="73a5f-152">Se um usuário entrar em contato com você porque não consegue entrar no aplicativo, verifique se ele tem um registro de funcionário associado no Human Resources.</span><span class="sxs-lookup"><span data-stu-id="73a5f-152">If a user contacts you because they can't sign into the app, verify that the user has an associated employee record in Human Resources.</span></span>

### <a name="error-when-approving-leave-requests-in-the-human-resources-app-in-teams"></a><span data-ttu-id="73a5f-153">Erro ao aprovar solicitações de licença no aplicativo do Human Resources no Teams</span><span class="sxs-lookup"><span data-stu-id="73a5f-153">Error when approving leave requests in the Human Resources app in Teams</span></span>

<span data-ttu-id="73a5f-154">Se um usuário receber um erro ao tentar aprovar solicitações de licença no aplicativo do Teams, execute as seguintes etapas de solução de problemas:</span><span class="sxs-lookup"><span data-stu-id="73a5f-154">If a user receives an error while trying to approve leave requests in the Teams app, perform the following troubleshooting steps:</span></span>

1. <span data-ttu-id="73a5f-155">Verifique se a sua conta do Teams é a mesma usada para acessar o Human Resources.</span><span class="sxs-lookup"><span data-stu-id="73a5f-155">Verify that their Teams account is the same one they use for accessing Human Resources.</span></span>

2. <span data-ttu-id="73a5f-156">Verifique se ele é um aprovador válido para a solicitação ao verificar as configurações do fluxo de trabalho para a aprovação de licenças.</span><span class="sxs-lookup"><span data-stu-id="73a5f-156">Verify that they're a valid approver for the request by checking the workflow settings for leave approval.</span></span> <span data-ttu-id="73a5f-157">Para obter mais informações sobre fluxos de trabalho de solicitações de licença, consulte [Criar um fluxo de trabalho de solicitações de licença](hr-leave-and-absence-workflow.md).</span><span class="sxs-lookup"><span data-stu-id="73a5f-157">For more information about leave request workflows, see [Create a leave request workflow](hr-leave-and-absence-workflow.md).</span></span>

## <a name="privacy-notice"></a><span data-ttu-id="73a5f-158">Aviso de privacidade</span><span class="sxs-lookup"><span data-stu-id="73a5f-158">Privacy notice</span></span>

### <a name="microsoft-language-understanding-intelligent-service-luis"></a><span data-ttu-id="73a5f-159">Serviço Inteligente de Reconhecimento Vocal (LUIS) da Microsoft</span><span class="sxs-lookup"><span data-stu-id="73a5f-159">Microsoft Language Understanding Intelligent Service (LUIS)</span></span>

<span data-ttu-id="73a5f-160">Com o bot do Dynamics 365 Human Resources no Microsoft Teams, as entradas de texto do usuário são analisadas para compreender a consulta/intenção subjacente.</span><span class="sxs-lookup"><span data-stu-id="73a5f-160">With the Dynamics 365 Human Resources bot in Microsoft Teams, the user’s text inputs are analyzed for understanding the underlying query/intent.</span></span> <span data-ttu-id="73a5f-161">A entrada do usuário, como "Pesquisar conta Contoso", é encaminhada para um dos Cognitive Services da Microsoft, chamado de Serviço Inteligente de Reconhecimento Vocal (LUIS).</span><span class="sxs-lookup"><span data-stu-id="73a5f-161">The user’s input such as “Search account Contoso” is routed to one of Microsoft’s Cognitive Service called Language Understanding Intelligent Service (LUIS).</span></span> <span data-ttu-id="73a5f-162">Leia mais sobre o LUIS  [aqui](https://www.luis.ai/).</span><span class="sxs-lookup"><span data-stu-id="73a5f-162">Read more about LUIS [here](https://www.luis.ai/).</span></span> <span data-ttu-id="73a5f-163">O serviço LUIS exclui a ambiguidade ou compreende a intenção da entrada do usuário (nesse caso, a intenção é encontrar informações) e a entidade de destino (nesse caso, a entidade pretendida é uma conta chamada Contoso).</span><span class="sxs-lookup"><span data-stu-id="73a5f-163">The LUIS service disambiguates or understands the intent of user input (in this case, the intent is to find information) and the target entity (in this case, the intended entity is an account named Contoso).</span></span> <span data-ttu-id="73a5f-164">Em seguida, essas informações são passadas para o [Azure Bot Framework](https://azure.microsoft.com/services/bot-service/) da Microsoft, que interage com os dados do Dynamics 365 Human Resources e recupera as informações desejadas para a consulta do usuário.</span><span class="sxs-lookup"><span data-stu-id="73a5f-164">This information is then passed on to Microsoft’s [Azure bot framework](https://azure.microsoft.com/services/bot-service/), which interacts with data from Dynamics 365 Human Resources and retrieves the desired information for the user query.</span></span> 

<span data-ttu-id="73a5f-165">Ao instalar e permitir o acesso ao uso do bot, você permite que o serviço LUIS e a estrutura de bot do Azure processem a intenção por trás da entrada, o que resulta em uma experiência aprimorada de conversa do usuário.</span><span class="sxs-lookup"><span data-stu-id="73a5f-165">By installing and allowing access to use of the bot, you agree to allow the LUIS service and Azure bot framework to process the intent behind the input,  which results in an enhanced conversational user experience.</span></span> <span data-ttu-id="73a5f-166">O serviço LUIS e a estrutura de bot do Azure têm vários níveis de conformidade em comparação com o Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="73a5f-166">The LUIS service and Azure bot framework may have varying levels of compliance compared to Dynamics 365 Human Resources.</span></span> <span data-ttu-id="73a5f-167">Embora o serviço LUIS tenha acesso a somente às consultas do usuário e não tenha sido desenvolvido para se conectar aos dados ou à conta do usuário do Dynamics 365 Human Resources, um usuário do bot do Dynamics 365 Human Resources poderia voluntariamente inserir uma consulta contendo Dados do Cliente, Dados Pessoais ou outros dados, e esse conteúdo da consulta poderia ser enviado para o serviço LUIS e para a estrutura de bot do Azure.</span><span class="sxs-lookup"><span data-stu-id="73a5f-167">While the LUIS service has access to only the user queries and is not designed to be connected to the user’s Dynamics 365 Human Resources data or account, a user of the Dynamics 365 Human Resources bot could voluntarily enter a query containing Customer Data, Personal Data, or other data and such query content could get sent to the LUIS service and the Azure bot framework.</span></span> 

<span data-ttu-id="73a5f-168">O conteúdo das consultas e das mensagens do usuário é mantido no sistema do LUIS por até 30 dias, criptografado em repouso e não é usado para treinamento ou melhoria de serviço.</span><span class="sxs-lookup"><span data-stu-id="73a5f-168">The content of user’s queries and messages is retained in LUIS system for a maximum of 30 days, is encrypted at rest, and is not used for training or service improvement.</span></span> <span data-ttu-id="73a5f-169">Leia mais sobre o Cognitive Services [aqui](https://azure.microsoft.com/services/cognitive-services/language-understanding-intelligent-service/).</span><span class="sxs-lookup"><span data-stu-id="73a5f-169">Read more about Cognitive Services [here](https://azure.microsoft.com/services/cognitive-services/language-understanding-intelligent-service/).</span></span> 

<span data-ttu-id="73a5f-170">Para gerenciar as configurações de administração de aplicativos no Microsoft Teams, vá para o [centro de administração do Microsoft Teams](https://admin.teams.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="73a5f-170">To manage admin settings for apps in Microsoft Teams, go to the [Microsoft Teams admin center](https://admin.teams.microsoft.com/).</span></span>

### <a name="microsoft-teams-azure-event-grid-and-azure-cosmos-db"></a><span data-ttu-id="73a5f-171">Microsoft Teams, Azure Event Grid e Azure Cosmos DB</span><span class="sxs-lookup"><span data-stu-id="73a5f-171">Microsoft Teams, Azure Event Grid, and Azure Cosmos DB</span></span>

<span data-ttu-id="73a5f-172">Ao usar o aplicativo Dynamics 365 Human Resources no Microsoft Teams, determinados dados do cliente podem fluir fora da região geográfica em que o serviço de Human Resources do locatário é implantado.</span><span class="sxs-lookup"><span data-stu-id="73a5f-172">When using the Dynamics 365 Human Resources app in Microsoft Teams, certain customer data may flow outside of the geographic region where your tenant’s Human Resources service is deployed.</span></span>

<span data-ttu-id="73a5f-173">O Dynamics 365 Human Resources transmite detalhes da solicitação de licença e da tarefa de fluxo de trabalho do funcionário para a Grade de Eventos do Microsoft Azure e o Microsoft Teams .</span><span class="sxs-lookup"><span data-stu-id="73a5f-173">Dynamics 365 Human Resources transmits the employee’s leave request and workflow task details to Microsoft Azure Event Grid and Microsoft Teams.</span></span> <span data-ttu-id="73a5f-174">Esses dados podem ser armazenados na Grade de Eventos do Microsoft Azure por até 24 horas e podem ser processados nos Estados Unidos, são criptografados em trânsito e em repouso, e não são usados pela Microsoft ou subprocessadores para treinamento ou melhorias de serviço.</span><span class="sxs-lookup"><span data-stu-id="73a5f-174">This data may be stored in Microsoft Azure Event Grid for up to 24 hours and will be processed in the United States, is encrypted in transit and at rest, and is not used by Microsoft or its subprocessors for training or service improvements.</span></span> <span data-ttu-id="73a5f-175">Para entender onde seus dados são armazenados no Teams, consulte: [Localização dos dados no Microsoft Teams](https://docs.microsoft.com/microsoftteams/location-of-data-in-teams?view=o365-worldwide&preserve-view=true).</span><span class="sxs-lookup"><span data-stu-id="73a5f-175">To understand where your data is stored in Teams, please see: [Location of data in Microsoft Teams](https://docs.microsoft.com/microsoftteams/location-of-data-in-teams?view=o365-worldwide&preserve-view=true).</span></span>

<span data-ttu-id="73a5f-176">Ao conversar com o bot de bate-papo no aplicativo Human Resources, o conteúdo da conversa pode ser armazenado no Azure Cosmos DB e transmitido ao Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="73a5f-176">While conversing with the chat bot in the Human Resources app, the conversation content may be stored in Azure Cosmos DB and transmitted to Microsoft Teams.</span></span> <span data-ttu-id="73a5f-177">Esses dados podem ser armazenados no Azure Cosmos DB por até 24 horas e podem ser processados fora da região geográfica onde o serviço do Human Resources do seu locatário está implantado, é criptografado em trânsito e em repouso e não é usado pela Microsoft ou seus subprocessadores para treinamento ou melhorias de serviço.</span><span class="sxs-lookup"><span data-stu-id="73a5f-177">This data may be stored in Azure Cosmos DB for up to 24 hours and may be processed outside of the geographic region where your tenant's Human Resources service is deployed, is encrypted in transit and at rest, and is not used by Microsoft or its subprocessors for training or service improvements.</span></span> <span data-ttu-id="73a5f-178">Para entender onde seus dados são armazenados no Teams, consulte: [Localização dos dados no Microsoft Teams](https://docs.microsoft.com/microsoftteams/location-of-data-in-teams?view=o365-worldwide&preserve-view=true).</span><span class="sxs-lookup"><span data-stu-id="73a5f-178">To understand where your data is stored in Teams, please see: [Location of data in Microsoft Teams](https://docs.microsoft.com/microsoftteams/location-of-data-in-teams?view=o365-worldwide&preserve-view=true).</span></span>
 
<span data-ttu-id="73a5f-179">Para restringir o acesso ao aplicativo Human Resources no Microsoft Teams para sua organização ou usuários dentro de sua organização, consulte [Gerenciar políticas de permissão de aplicativo no Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/teams-app-permission-policies).</span><span class="sxs-lookup"><span data-stu-id="73a5f-179">To restrict access to the Human Resources app in Microsoft Teams for your organization or users within your organization, see [Manage app permission policies in Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/teams-app-permission-policies).</span></span>

## <a name="see-also"></a><span data-ttu-id="73a5f-180">Consulte também</span><span class="sxs-lookup"><span data-stu-id="73a5f-180">See also</span></span> 

[<span data-ttu-id="73a5f-181">Baixar e instalar o Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="73a5f-181">Download and install Microsoft Teams</span></span>](https://support.office.com/article/download-and-install-microsoft-teams-422bf3aa-9ae8-46f1-83a2-e65720e1a34d)</br>
[<span data-ttu-id="73a5f-182">Central de ajuda do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="73a5f-182">Microsoft Teams help center</span></span>](https://support.office.com/teams)</br>
[<span data-ttu-id="73a5f-183">Gerenciar solicitações de licença no Teams</span><span class="sxs-lookup"><span data-stu-id="73a5f-183">Manage leave requests in Teams</span></span>](hr-teams-leave-app.md)

