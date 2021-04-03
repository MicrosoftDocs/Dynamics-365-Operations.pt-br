---
title: Aplicativo Human Resources no Teams
description: Este tópico apresenta o aplicativo Microsoft Dynamics 365 Human Resources no Microsoft Teams.
author: andreabichsel
manager: tfehr
ms.date: 02/23/2021
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
ms.openlocfilehash: 86abe32f76f2cc21c773727be07a44be49cdbac7
ms.sourcegitcommit: 105f65468b45799761c26e5d0ad9df4ff162c38d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/04/2021
ms.locfileid: "5487864"
---
# <a name="human-resources-app-in-teams"></a><span data-ttu-id="90c4f-103">Aplicativo Human Resources no Teams</span><span class="sxs-lookup"><span data-stu-id="90c4f-103">Human Resources app in Teams</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="90c4f-104">O aplicativo Microsoft Dynamics 365 Human Resources no Microsoft Teams permite aos funcionários solicitar folgas rapidamente, além de visualizar suas informações de saldo de folgas no Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="90c4f-104">The Microsoft Dynamics 365 Human Resources app in Microsoft Teams lets employees quickly request time off and view their time-off balance information in Microsoft Teams.</span></span> <span data-ttu-id="90c4f-105">Os funcionários podem interagir com um bot para solicitar informações.</span><span class="sxs-lookup"><span data-stu-id="90c4f-105">Employees can interact with a bot to request information.</span></span> <span data-ttu-id="90c4f-106">A guia **Folga** fornece informações mais detalhadas.</span><span class="sxs-lookup"><span data-stu-id="90c4f-106">The **Time off** tab provides more detailed information.</span></span> <span data-ttu-id="90c4f-107">Além disso, eles podem enviar às pessoas informações sobre suas próximas folgas em equipes e bate-papos fora do aplicativo do Human Resources.</span><span class="sxs-lookup"><span data-stu-id="90c4f-107">In addition, they can send people information about upcoming time off in teams and chats outside the Human Resources app.</span></span>

![Bot do aplicativo de licenças do Human Resources Teams](./media/hr-teams-leave-app-bot.png)

![Guia Folga do aplicativo de licença do Human Resources Teams](./media/hr-teams-leave-app-timeoff-tab.png)

![Cartão de solicitação de licença do Human Resources](./media/hr-teams-leave-app-chat-card.png)

## <a name="install-and-setup"></a><span data-ttu-id="90c4f-111">Instalação e configuração</span><span class="sxs-lookup"><span data-stu-id="90c4f-111">Install and setup</span></span>

<span data-ttu-id="90c4f-112">Você pode encontrar o aplicativo Dynamics 365 Human Resources na loja do Teams.</span><span class="sxs-lookup"><span data-stu-id="90c4f-112">You can find the Dynamics 365 Human Resources app in the Teams store.</span></span> <span data-ttu-id="90c4f-113">Para obter informações sobre como instalar o aplicativo do Teams, consulte [Gerenciar solicitações de licença no Teams](hr-teams-leave-app.md).</span><span class="sxs-lookup"><span data-stu-id="90c4f-113">For information about installing the Teams app, see [Manage leave requests in Teams](hr-teams-leave-app.md).</span></span>

<span data-ttu-id="90c4f-114">Para obter informações sobre como gerenciar permissões de aplicativo no Teams, consulte [Gerenciar políticas de permissão de aplicativo no Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/teams-app-permission-policies).</span><span class="sxs-lookup"><span data-stu-id="90c4f-114">For information about managing app permissions in Teams, see [Manage app permission policies in Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/teams-app-permission-policies).</span></span>

<span data-ttu-id="90c4f-115">Se desejar que os usuários exibam o Calendário de licenças e ausências no aplicativo, habilite o **Calendário de licenças e ausências no Teams** no Gerenciamento de recursos.</span><span class="sxs-lookup"><span data-stu-id="90c4f-115">If you want your users to view the Leave and absence calendar in the app, you'll need to enable the **Leave and absence calendar in Teams** in Feature management.</span></span> <span data-ttu-id="90c4f-116">Para obter mais informações sobre como habilitar recursos, consulte [Gerenciar recursos](hr-admin-manage-features.md).</span><span class="sxs-lookup"><span data-stu-id="90c4f-116">For more information about enabling features, see [Manage features](hr-admin-manage-features.md).</span></span>

## <a name="enable-notifications-for-the-human-resources-app-in-teams"></a><span data-ttu-id="90c4f-117">Habilitar notificações para o aplicativo de recursos humanos no Teams</span><span class="sxs-lookup"><span data-stu-id="90c4f-117">Enable notifications for the Human Resources app in Teams</span></span>

<span data-ttu-id="90c4f-118">Para que os usuários recebam notificações de solicitação de licença no aplicativo Teams, habilite notificações no Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="90c4f-118">If you want users to receive leave request notifications in the Teams app, you must enable notifications in Dynamics 365 Human Resources.</span></span>

>[!NOTE]
><span data-ttu-id="90c4f-119">Somente usuários conectados ao Teams e que utilizem o aplicativo Dynamics 365 Human Resources no Teams receberão notificações.</span><span class="sxs-lookup"><span data-stu-id="90c4f-119">Only users who are signed into Teams and using the Dynamics 365 Human Resources Teams app will receive notifications.</span></span>

1. <span data-ttu-id="90c4f-120">No Human Resources, selecione **Administração do sistema**.</span><span class="sxs-lookup"><span data-stu-id="90c4f-120">In Human Resources, select **System administration**.</span></span>

2. <span data-ttu-id="90c4f-121">Selecione **Links**.</span><span class="sxs-lookup"><span data-stu-id="90c4f-121">Select **Links**.</span></span>

3. <span data-ttu-id="90c4f-122">Em **Configuração** , selecione **Parâmetros do sistema** .</span><span class="sxs-lookup"><span data-stu-id="90c4f-122">Under **Setup**, select **System parameters**.</span></span>

4. <span data-ttu-id="90c4f-123">Na guia **Geral**, defina **Habilitar notificações para o aplicativo Teams** como **Sim** .</span><span class="sxs-lookup"><span data-stu-id="90c4f-123">On the **General** tab, set **Enable notifications for Teams app** to **Yes**.</span></span>

   ![Habilitar notificações do aplicativo Teams nos Parâmetros do Sistema](./media/hr-admin-teams-leave-app-enable-notifications.png)

5. <span data-ttu-id="90c4f-125">Para ativar notificações do Teams para todos os usuários, selecione **Sim** no prompt.</span><span class="sxs-lookup"><span data-stu-id="90c4f-125">To turn on Teams notifications for all users, select **Yes** at the prompt.</span></span>

   ![Habilitar notificações do Teams para todos os usuários](./media/hr-admin-teams-leave-app-notifications-all-users.png)

### <a name="turn-teams-notifications-on-or-off-for-individual-users"></a><span data-ttu-id="90c4f-127">Ativar ou desativar notificações do Teams para usuários individuais</span><span class="sxs-lookup"><span data-stu-id="90c4f-127">Turn Teams notifications on or off for individual users</span></span>

<span data-ttu-id="90c4f-128">Após habilitar notificações para o aplicativo Dynamics 365 Human Resources no Teams, você poderá ativar ou desativar notificações para usuários individuais.</span><span class="sxs-lookup"><span data-stu-id="90c4f-128">After you've enabled notifications for the Dynamics 365 Human Resources Teams app, you can turn notifications on or off for individual users.</span></span>

1. <span data-ttu-id="90c4f-129">No Human Resources, selecione **Administração do sistema**.</span><span class="sxs-lookup"><span data-stu-id="90c4f-129">In Human Resources, select **System administration**.</span></span>

2. <span data-ttu-id="90c4f-130">Selecione **Links**.</span><span class="sxs-lookup"><span data-stu-id="90c4f-130">Select **Links**.</span></span>

3. <span data-ttu-id="90c4f-131">Em **Usuários**, selecione **Opções do usuário** .</span><span class="sxs-lookup"><span data-stu-id="90c4f-131">Under **Users**, select **User options**.</span></span>

4. <span data-ttu-id="90c4f-132">Selecione a guia **Fluxo de trabalho**.</span><span class="sxs-lookup"><span data-stu-id="90c4f-132">Select the **Workflow** tab.</span></span>

5. <span data-ttu-id="90c4f-133">Defina **Habilitar notificações para o aplicativo Teams** como **Sim** para habilitar notificações para o usuário ou como **Não** para desabilitar notificações para o usuário.</span><span class="sxs-lookup"><span data-stu-id="90c4f-133">Set **Enable notifications for Teams app** to **Yes** to enable notifications for the user or **No** to disable notifications for the user.</span></span>

   ![Habilitar notificações do aplicativo Teams na guia Fluxo de trabalho de opções do usuário](./media/hr-admin-teams-leave-app-notifications.png)

6. <span data-ttu-id="90c4f-135">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="90c4f-135">Select **Save**.</span></span>

## <a name="supported-languages"></a><span data-ttu-id="90c4f-136">Idiomas com suporte</span><span class="sxs-lookup"><span data-stu-id="90c4f-136">Supported languages</span></span>

<span data-ttu-id="90c4f-137">O aplicativo Dynamics 365 Human Resources no Teams oferece suporte aos seguintes idiomas:</span><span class="sxs-lookup"><span data-stu-id="90c4f-137">The Dynamics 365 Human Resources app in Teams supports the following languages:</span></span>

| <span data-ttu-id="90c4f-138">ID da localidade</span><span class="sxs-lookup"><span data-stu-id="90c4f-138">Locale ID</span></span> | <span data-ttu-id="90c4f-139">Idioma</span><span class="sxs-lookup"><span data-stu-id="90c4f-139">Language</span></span> |
| --- | --- |
| <span data-ttu-id="90c4f-140">de-DE</span><span class="sxs-lookup"><span data-stu-id="90c4f-140">de-DE</span></span> | <span data-ttu-id="90c4f-141">Alemão (Alemanha)</span><span class="sxs-lookup"><span data-stu-id="90c4f-141">German (Germany)</span></span> |
| <span data-ttu-id="90c4f-142">es-ES</span><span class="sxs-lookup"><span data-stu-id="90c4f-142">es-ES</span></span> | <span data-ttu-id="90c4f-143">Espanhol (Espanha)</span><span class="sxs-lookup"><span data-stu-id="90c4f-143">Spanish (Spain)</span></span> |
| <span data-ttu-id="90c4f-144">es-MX</span><span class="sxs-lookup"><span data-stu-id="90c4f-144">es-MX</span></span> | <span data-ttu-id="90c4f-145">Espanhol (México)</span><span class="sxs-lookup"><span data-stu-id="90c4f-145">Spanish (Mexico)</span></span> |
| <span data-ttu-id="90c4f-146">fr-CA</span><span class="sxs-lookup"><span data-stu-id="90c4f-146">fr-CA</span></span> | <span data-ttu-id="90c4f-147">Francês (Canadá)</span><span class="sxs-lookup"><span data-stu-id="90c4f-147">French (Canada)</span></span> |
| <span data-ttu-id="90c4f-148">fr-FR</span><span class="sxs-lookup"><span data-stu-id="90c4f-148">fr-FR</span></span> | <span data-ttu-id="90c4f-149">Francês (França)</span><span class="sxs-lookup"><span data-stu-id="90c4f-149">French (France)</span></span> |
| <span data-ttu-id="90c4f-150">it-IT</span><span class="sxs-lookup"><span data-stu-id="90c4f-150">it-IT</span></span> | <span data-ttu-id="90c4f-151">Italiano (Itália)</span><span class="sxs-lookup"><span data-stu-id="90c4f-151">Italian (Italy)</span></span> |
| <span data-ttu-id="90c4f-152">nl-NL</span><span class="sxs-lookup"><span data-stu-id="90c4f-152">nl-NL</span></span> | <span data-ttu-id="90c4f-153">Holandês (Países Baixos)</span><span class="sxs-lookup"><span data-stu-id="90c4f-153">Dutch (Netherlands)</span></span> |
| <span data-ttu-id="90c4f-154">pt-BR</span><span class="sxs-lookup"><span data-stu-id="90c4f-154">pt-BR</span></span> | <span data-ttu-id="90c4f-155">Português (Brasil)</span><span class="sxs-lookup"><span data-stu-id="90c4f-155">Portuguese (Brazil)</span></span> |
| <span data-ttu-id="90c4f-156">tr-TR</span><span class="sxs-lookup"><span data-stu-id="90c4f-156">tr-TR</span></span> | <span data-ttu-id="90c4f-157">Turco (Turquia)</span><span class="sxs-lookup"><span data-stu-id="90c4f-157">Turkish (Turkey)</span></span> |
| <span data-ttu-id="90c4f-158">zh-CN</span><span class="sxs-lookup"><span data-stu-id="90c4f-158">zh-CN</span></span> | <span data-ttu-id="90c4f-159">Chinês (simplificado)</span><span class="sxs-lookup"><span data-stu-id="90c4f-159">Chinese (Simplified)</span></span> |

## <a name="notes"></a><span data-ttu-id="90c4f-160">Observação</span><span class="sxs-lookup"><span data-stu-id="90c4f-160">Notes</span></span>

<span data-ttu-id="90c4f-161">Os seguintes itens de trabalho foram lançados para versões futuras:</span><span class="sxs-lookup"><span data-stu-id="90c4f-161">The following work items are slated for future releases:</span></span>

| <span data-ttu-id="90c4f-162">Item de trabalho</span><span class="sxs-lookup"><span data-stu-id="90c4f-162">Work item</span></span> | <span data-ttu-id="90c4f-163">Status</span><span class="sxs-lookup"><span data-stu-id="90c4f-163">Status</span></span> |
| --- | --- |
| <span data-ttu-id="90c4f-164">O saldo exibido ao enviar folga para uma data futura está incorreto.</span><span class="sxs-lookup"><span data-stu-id="90c4f-164">The balance is incorrect when submitting time off for a future date.</span></span> | <span data-ttu-id="90c4f-165">A previsão ainda não está disponível.</span><span class="sxs-lookup"><span data-stu-id="90c4f-165">Forecasting isn't yet available.</span></span> <span data-ttu-id="90c4f-166">O saldo é exibido para a data atual.</span><span class="sxs-lookup"><span data-stu-id="90c4f-166">The balance displays for the current date.</span></span> |
| <span data-ttu-id="90c4f-167">Não é possível cancelar uma solicitação **Em revisão**.</span><span class="sxs-lookup"><span data-stu-id="90c4f-167">Unable to cancel an **In review** request.</span></span> | <span data-ttu-id="90c4f-168">Atualmente, essa funcionalidade não tem suporte e será adicionada em uma versão futura.</span><span class="sxs-lookup"><span data-stu-id="90c4f-168">This functionality isn't currently supported and will be added in a future release.</span></span> |
| <span data-ttu-id="90c4f-169">As informações de saldo são calculadas a partir de hoje.</span><span class="sxs-lookup"><span data-stu-id="90c4f-169">Balance information is calculated as of today.</span></span> | <span data-ttu-id="90c4f-170">O sistema atualmente não exibe os saldos a partir do período de acúmulo, mesmo se estiver configurado nos parâmetros de Licença e ausência.</span><span class="sxs-lookup"><span data-stu-id="90c4f-170">The system currently doesn't display balances as of the accrual period, even if it's configured in Leave and absence parameters.</span></span> |

## <a name="troubleshooting"></a><span data-ttu-id="90c4f-171">Solução de problemas</span><span class="sxs-lookup"><span data-stu-id="90c4f-171">Troubleshooting</span></span>

<span data-ttu-id="90c4f-172">Se um usuário tiver problemas para entrar ou ao usar o aplicativo do Human Resources no Teams, tente seguir estas instruções de solução de problemas.</span><span class="sxs-lookup"><span data-stu-id="90c4f-172">If a user is having trouble signing into or using the Human Resources Teams app, try following these troubleshooting instructions.</span></span> <span data-ttu-id="90c4f-173">Se você ainda tiver problemas após a solução de problemas, contate o Suporte.</span><span class="sxs-lookup"><span data-stu-id="90c4f-173">If you're still having problems after troubleshooting, contact Support.</span></span> <span data-ttu-id="90c4f-174">Para obter mais informações, consulte [Obter suporte](hr-admin-troubleshooting-support.md).</span><span class="sxs-lookup"><span data-stu-id="90c4f-174">For more information, see [Get support](hr-admin-troubleshooting-support.md).</span></span>

### <a name="cant-sign-into-the-human-resources-app-in-teams"></a><span data-ttu-id="90c4f-175">Não é possível entrar no aplicativo do Human Resources no Teams</span><span class="sxs-lookup"><span data-stu-id="90c4f-175">Can't sign into the Human Resources app in Teams</span></span>

<span data-ttu-id="90c4f-176">Se um usuário entrar em contato com você porque não consegue entrar no aplicativo, verifique se ele tem um registro de funcionário associado no Human Resources.</span><span class="sxs-lookup"><span data-stu-id="90c4f-176">If a user contacts you because they can't sign into the app, verify that they have an associated employee record in Human Resources.</span></span>

### <a name="error-when-approving-leave-requests-in-the-human-resources-app-in-teams"></a><span data-ttu-id="90c4f-177">Erro ao aprovar solicitações de licença no aplicativo do Human Resources no Teams</span><span class="sxs-lookup"><span data-stu-id="90c4f-177">Error when approving leave requests in the Human Resources app in Teams</span></span>

<span data-ttu-id="90c4f-178">Se um usuário receber um erro ao tentar aprovar solicitações de licença no aplicativo do Teams, teste as seguintes etapas de solução de problemas:</span><span class="sxs-lookup"><span data-stu-id="90c4f-178">If a user receives an error while trying to approve,  leave requests in the Teams app, try the following troubleshooting steps:</span></span>

1. <span data-ttu-id="90c4f-179">Verifique se a sua conta do Teams é a mesma usada para acessar o Human Resources.</span><span class="sxs-lookup"><span data-stu-id="90c4f-179">Verify that their Teams account is the same one they use for accessing Human Resources.</span></span>

2. <span data-ttu-id="90c4f-180">Verifique se ele é um aprovador válido para a solicitação ao verificar as configurações do fluxo de trabalho para a aprovação de licenças.</span><span class="sxs-lookup"><span data-stu-id="90c4f-180">Verify that they're a valid approver for the request by checking the workflow settings for leave approval.</span></span> <span data-ttu-id="90c4f-181">Para obter mais informações sobre fluxos de trabalho de solicitações de licença, consulte [Criar um fluxo de trabalho de solicitações de licença](hr-leave-and-absence-workflow.md).</span><span class="sxs-lookup"><span data-stu-id="90c4f-181">For more information about leave request workflows, see [Create a leave request workflow](hr-leave-and-absence-workflow.md).</span></span>

## <a name="privacy-notice"></a><span data-ttu-id="90c4f-182">Aviso de privacidade</span><span class="sxs-lookup"><span data-stu-id="90c4f-182">Privacy notice</span></span>

### <a name="microsoft-language-understanding-intelligent-service-luis"></a><span data-ttu-id="90c4f-183">Serviço Inteligente de Reconhecimento Vocal (LUIS) da Microsoft</span><span class="sxs-lookup"><span data-stu-id="90c4f-183">Microsoft Language Understanding Intelligent Service (LUIS)</span></span>

<span data-ttu-id="90c4f-184">Com o bot do Dynamics 365 Human Resources no Microsoft Teams, as entradas de texto do usuário são analisadas para compreender a consulta/intenção subjacente.</span><span class="sxs-lookup"><span data-stu-id="90c4f-184">With the Dynamics 365 Human Resources bot in Microsoft Teams, the user’s text inputs are analyzed for understanding the underlying query/intent.</span></span> <span data-ttu-id="90c4f-185">A entrada do usuário, como "Pesquisar conta Contoso", é encaminhada para um dos Cognitive Services da Microsoft, chamado de Serviço Inteligente de Reconhecimento Vocal (LUIS).</span><span class="sxs-lookup"><span data-stu-id="90c4f-185">The user’s input such as “Search account Contoso” is routed to one of Microsoft’s Cognitive Service called Language Understanding Intelligent Service (LUIS).</span></span> <span data-ttu-id="90c4f-186">Leia mais sobre o LUIS  [aqui](https://www.luis.ai/).</span><span class="sxs-lookup"><span data-stu-id="90c4f-186">Read more about LUIS [here](https://www.luis.ai/).</span></span> <span data-ttu-id="90c4f-187">O serviço LUIS exclui a ambiguidade ou compreende a intenção da entrada do usuário (nesse caso, a intenção é encontrar informações) e a entidade de destino (nesse caso, a entidade pretendida é uma conta chamada Contoso).</span><span class="sxs-lookup"><span data-stu-id="90c4f-187">The LUIS service disambiguates or understands the intent of user input (in this case, the intent is to find information) and the target entity (in this case, the intended entity is an account named Contoso).</span></span> <span data-ttu-id="90c4f-188">Em seguida, essas informações são passadas para o [Azure Bot Framework](https://azure.microsoft.com/services/bot-service/) da Microsoft, que interage com os dados do Dynamics 365 Human Resources e recupera as informações desejadas para a consulta do usuário.</span><span class="sxs-lookup"><span data-stu-id="90c4f-188">This information is then passed on to Microsoft’s [Azure bot framework](https://azure.microsoft.com/services/bot-service/), which interacts with data from Dynamics 365 Human Resources and retrieves the desired information for the user query.</span></span> 

<span data-ttu-id="90c4f-189">Ao instalar e permitir o acesso ao uso do bot, você permite que o serviço LUIS e a estrutura de bot do Azure processem a intenção por trás da entrada, o que resulta em uma experiência aprimorada de conversa do usuário.</span><span class="sxs-lookup"><span data-stu-id="90c4f-189">By installing and allowing access to use of the bot, you agree to allow the LUIS service and Azure bot framework to process the intent behind the input,  which results in an enhanced conversational user experience.</span></span> <span data-ttu-id="90c4f-190">O serviço LUIS e a estrutura de bot do Azure têm vários níveis de conformidade em comparação com o Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="90c4f-190">The LUIS service and Azure bot framework may have varying levels of compliance compared to Dynamics 365 Human Resources.</span></span> <span data-ttu-id="90c4f-191">Embora o serviço LUIS tenha acesso a somente às consultas do usuário e não tenha sido desenvolvido para se conectar aos dados ou à conta do usuário do Dynamics 365 Human Resources, um usuário do bot do Dynamics 365 Human Resources poderia voluntariamente inserir uma consulta contendo Dados do Cliente, Dados Pessoais ou outros dados, e esse conteúdo da consulta poderia ser enviado para o serviço LUIS e para a estrutura de bot do Azure.</span><span class="sxs-lookup"><span data-stu-id="90c4f-191">While the LUIS service has access to only the user queries and is not designed to be connected to the user’s Dynamics 365 Human Resources data or account, a user of the Dynamics 365 Human Resources bot could voluntarily enter a query containing Customer Data, Personal Data, or other data and such query content could get sent to the LUIS service and the Azure bot framework.</span></span> 

<span data-ttu-id="90c4f-192">O conteúdo das consultas e das mensagens do usuário é mantido no sistema do LUIS por até 30 dias, criptografado em repouso e não é usado para treinamento ou melhoria de serviço.</span><span class="sxs-lookup"><span data-stu-id="90c4f-192">The content of user’s queries and messages is retained in LUIS system for a maximum of 30 days, is encrypted at rest, and is not used for training or service improvement.</span></span> <span data-ttu-id="90c4f-193">Leia mais sobre o Cognitive Services [aqui](https://azure.microsoft.com/services/cognitive-services/language-understanding-intelligent-service/).</span><span class="sxs-lookup"><span data-stu-id="90c4f-193">Read more about Cognitive Services [here](https://azure.microsoft.com/services/cognitive-services/language-understanding-intelligent-service/).</span></span> 

<span data-ttu-id="90c4f-194">Para gerenciar as configurações de administração de aplicativos no Microsoft Teams, vá para o [centro de administração do Microsoft Teams](https://admin.teams.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="90c4f-194">To manage admin settings for apps in Microsoft Teams, go to the [Microsoft Teams admin center](https://admin.teams.microsoft.com/).</span></span>

### <a name="microsoft-teams-azure-event-grid-and-azure-cosmos-db"></a><span data-ttu-id="90c4f-195">Microsoft Teams, Azure Event Grid e Azure Cosmos DB</span><span class="sxs-lookup"><span data-stu-id="90c4f-195">Microsoft Teams, Azure Event Grid, and Azure Cosmos DB</span></span>

<span data-ttu-id="90c4f-196">Ao usar o aplicativo Dynamics 365 Human Resources no Microsoft Teams, determinados dados do cliente podem fluir fora da região geográfica em que o serviço de Human Resources do locatário é implantado.</span><span class="sxs-lookup"><span data-stu-id="90c4f-196">When using the Dynamics 365 Human Resources app in Microsoft Teams, certain customer data may flow outside of the geographic region where your tenant’s Human Resources service is deployed.</span></span>

<span data-ttu-id="90c4f-197">O Dynamics 365 Human Resources transmite detalhes da solicitação de licença e da tarefa de fluxo de trabalho do funcionário para a Grade de Eventos do Microsoft Azure e o Microsoft Teams .</span><span class="sxs-lookup"><span data-stu-id="90c4f-197">Dynamics 365 Human Resources transmits the employee’s leave request and workflow task details to Microsoft Azure Event Grid and Microsoft Teams.</span></span> <span data-ttu-id="90c4f-198">Esses dados podem ser armazenados na Grade de Eventos do Microsoft Azure por até 24 horas e podem ser processados nos Estados Unidos, são criptografados em trânsito e em repouso, e não são usados pela Microsoft ou subprocessadores para treinamento ou melhorias de serviço.</span><span class="sxs-lookup"><span data-stu-id="90c4f-198">This data may be stored in Microsoft Azure Event Grid for up to 24 hours and will be processed in the United States, is encrypted in transit and at rest, and is not used by Microsoft or its subprocessors for training or service improvements.</span></span> <span data-ttu-id="90c4f-199">Para entender onde seus dados são armazenados no Teams, consulte: [Localização dos dados no Microsoft Teams](https://docs.microsoft.com/microsoftteams/location-of-data-in-teams?view=o365-worldwide&preserve-view=true).</span><span class="sxs-lookup"><span data-stu-id="90c4f-199">To understand where your data is stored in Teams, please see: [Location of data in Microsoft Teams](https://docs.microsoft.com/microsoftteams/location-of-data-in-teams?view=o365-worldwide&preserve-view=true).</span></span>

<span data-ttu-id="90c4f-200">Ao conversar com o bot de bate-papo no aplicativo Human Resources, o conteúdo da conversa pode ser armazenado no Azure Cosmos DB e transmitido ao Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="90c4f-200">While conversing with the chat bot in the Human Resources app, the conversation content may be stored in Azure Cosmos DB and transmitted to Microsoft Teams.</span></span> <span data-ttu-id="90c4f-201">Esses dados podem ser armazenados no Azure Cosmos DB por até 24 horas e podem ser processados fora da região geográfica onde o serviço do Human Resources do seu locatário está implantado, é criptografado em trânsito e em repouso e não é usado pela Microsoft ou seus subprocessadores para treinamento ou melhorias de serviço.</span><span class="sxs-lookup"><span data-stu-id="90c4f-201">This data may be stored in Azure Cosmos DB for up to 24 hours and may be processed outside of the geographic region where your tenant's Human Resources service is deployed, is encrypted in transit and at rest, and is not used by Microsoft or its subprocessors for training or service improvements.</span></span> <span data-ttu-id="90c4f-202">Para entender onde seus dados são armazenados no Teams, consulte: [Localização dos dados no Microsoft Teams](https://docs.microsoft.com/microsoftteams/location-of-data-in-teams?view=o365-worldwide&preserve-view=true).</span><span class="sxs-lookup"><span data-stu-id="90c4f-202">To understand where your data is stored in Teams, please see: [Location of data in Microsoft Teams](https://docs.microsoft.com/microsoftteams/location-of-data-in-teams?view=o365-worldwide&preserve-view=true).</span></span>
 
<span data-ttu-id="90c4f-203">Para restringir o acesso ao aplicativo Human Resources no Microsoft Teams para sua organização ou usuários dentro de sua organização, consulte [Gerenciar políticas de permissão de aplicativo no Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/teams-app-permission-policies).</span><span class="sxs-lookup"><span data-stu-id="90c4f-203">To restrict access to the Human Resources app in Microsoft Teams for your organization or users within your organization, see [Manage app permission policies in Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/teams-app-permission-policies).</span></span>

## <a name="see-also"></a><span data-ttu-id="90c4f-204">Consulte também</span><span class="sxs-lookup"><span data-stu-id="90c4f-204">See also</span></span> 

[<span data-ttu-id="90c4f-205">Baixar e instalar o Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="90c4f-205">Download and install Microsoft Teams</span></span>](https://support.office.com/article/download-and-install-microsoft-teams-422bf3aa-9ae8-46f1-83a2-e65720e1a34d)</br>
[<span data-ttu-id="90c4f-206">Central de ajuda do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="90c4f-206">Microsoft Teams help center</span></span>](https://support.office.com/teams)</br>
[<span data-ttu-id="90c4f-207">Gerenciar solicitações de licença no Teams</span><span class="sxs-lookup"><span data-stu-id="90c4f-207">Manage leave requests in Teams</span></span>](hr-teams-leave-app.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]