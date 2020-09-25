---
title: Aplicativo Human Resources no Teams
description: Este tópico apresenta o aplicativo Microsoft Dynamics 365 Human Resources no Microsoft Teams.
author: andreabichsel
manager: AnnBe
ms.date: 09/01/2020
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
ms.openlocfilehash: a022f8297066793080d254baa01410884a3fafd9
ms.sourcegitcommit: 55b729361ea852e38531c51972c6730e3d9c2b45
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/08/2020
ms.locfileid: "3776299"
---
# <a name="human-resources-app-in-teams"></a><span data-ttu-id="ba1c2-103">Aplicativo Human Resources no Teams</span><span class="sxs-lookup"><span data-stu-id="ba1c2-103">Human Resources app in Teams</span></span>

[!include [banner](includes/preview-feature.md)]

<span data-ttu-id="ba1c2-104">O aplicativo Microsoft Dynamics 365 Human Resources no Microsoft Teams permite aos funcionários solicitar folgas rapidamente, além de visualizar suas informações de saldo de folgas no Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="ba1c2-104">The Microsoft Dynamics 365 Human Resources app in Microsoft Teams lets employees quickly request time off and view their time-off balance information in Microsoft Teams.</span></span> <span data-ttu-id="ba1c2-105">Os funcionários podem interagir com um bot para solicitar informações.</span><span class="sxs-lookup"><span data-stu-id="ba1c2-105">Employees can interact with a bot to request information.</span></span> <span data-ttu-id="ba1c2-106">A guia **Folga** fornece informações mais detalhadas.</span><span class="sxs-lookup"><span data-stu-id="ba1c2-106">The **Time off** tab provides more detailed information.</span></span>

![Bot do aplicativo de licenças do Human Resources Teams](./media/hr-admin-teams-leave-app-bot.png)

![Guia Folga do aplicativo de licença do Human Resources Teams](./media/hr-teams-leave-app-timeoff-tab.png)

## <a name="install-and-setup"></a><span data-ttu-id="ba1c2-109">Instalação e configuração</span><span class="sxs-lookup"><span data-stu-id="ba1c2-109">Install and setup</span></span>

<span data-ttu-id="ba1c2-110">Você pode encontrar o aplicativo Human Resources na loja do Teams.</span><span class="sxs-lookup"><span data-stu-id="ba1c2-110">You can find the Human Resources app in the Teams store.</span></span> <span data-ttu-id="ba1c2-111">Para obter informações sobre como instalar o aplicativo do Teams, consulte [Gerenciar solicitações de licença no Teams](hr-teams-leave-app.md).</span><span class="sxs-lookup"><span data-stu-id="ba1c2-111">For information about installing the Teams app, see [Manage leave requests in Teams](hr-teams-leave-app.md).</span></span>

<span data-ttu-id="ba1c2-112">Para obter informações sobre como gerenciar permissões de aplicativo no Teams, consulte [Gerenciar políticas de permissão de aplicativo no Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/teams-app-permission-policies).</span><span class="sxs-lookup"><span data-stu-id="ba1c2-112">For information about managing app permissions in Teams, see [Manage app permission policies in Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/teams-app-permission-policies).</span></span>

## <a name="enable-notifications-for-the-human-resources-app-in-teams"></a><span data-ttu-id="ba1c2-113">Habilitar notificações para o aplicativo de recursos humanos no Teams</span><span class="sxs-lookup"><span data-stu-id="ba1c2-113">Enable notifications for the Human Resources app in Teams</span></span>

<span data-ttu-id="ba1c2-114">Para que os usuários recebam notificações de solicitação de licença no aplicativo Team, você deve habilitar notificações no Human Resources.</span><span class="sxs-lookup"><span data-stu-id="ba1c2-114">If you want users to receive leave request notifications in the Teams app, you must enable notifications in Human Resources.</span></span>

>[!NOTE]
><span data-ttu-id="ba1c2-115">Somente os usuários que estiverem conectados ao Teams e usando o aplicativo Human Resources Teams receberão notificações.</span><span class="sxs-lookup"><span data-stu-id="ba1c2-115">Only users who are signed into Teams and using the Human Resources Teams app will receive notifications.</span></span>

1. <span data-ttu-id="ba1c2-116">No Human Resources, selecione **Administração do sistema**.</span><span class="sxs-lookup"><span data-stu-id="ba1c2-116">In Human Resources, select **System administration**.</span></span>

2. <span data-ttu-id="ba1c2-117">Selecione **Links**.</span><span class="sxs-lookup"><span data-stu-id="ba1c2-117">Select **Links**.</span></span>

3. <span data-ttu-id="ba1c2-118">Em **Configuração** , selecione **Parâmetros do sistema** .</span><span class="sxs-lookup"><span data-stu-id="ba1c2-118">Under **Setup**, select **System parameters**.</span></span>

4. <span data-ttu-id="ba1c2-119">Na guia **Geral**, defina **Habilitar notificações para o aplicativo Teams** como **Sim** .</span><span class="sxs-lookup"><span data-stu-id="ba1c2-119">On the **General** tab, set **Enable notifications for Teams app** to **Yes**.</span></span>

   ![Habilitar notificações do aplicativo Teams nos Parâmetros do Sistema](./media/hr-admin-teams-leave-app-enable-notifications.png)

5. <span data-ttu-id="ba1c2-121">Para ativar notificações do Teams para todos os usuários, selecione **Sim** no prompt.</span><span class="sxs-lookup"><span data-stu-id="ba1c2-121">To turn on Teams notifications for all users, select **Yes** at the prompt.</span></span>

   ![Habilitar notificações do Teams para todos os usuários](./media/hr-admin-teams-leave-app-notifications-all-users.png)

### <a name="turn-teams-notifications-on-or-off-for-individual-users"></a><span data-ttu-id="ba1c2-123">Ativar ou desativar notificações do Teams para usuários individuais</span><span class="sxs-lookup"><span data-stu-id="ba1c2-123">Turn Teams notifications on or off for individual users</span></span>

<span data-ttu-id="ba1c2-124">Depois de habilitar notificações para o aplicativo Human Resources Team, você pode ativar ou desativar notificações para usuários individuais.</span><span class="sxs-lookup"><span data-stu-id="ba1c2-124">After you've enabled notifications for the Human Resources Teams app, you can turn notifications on or off for individual users.</span></span>

1. <span data-ttu-id="ba1c2-125">No Human Resources, selecione **Administração do sistema**.</span><span class="sxs-lookup"><span data-stu-id="ba1c2-125">In Human Resources, select **System administration**.</span></span>

2. <span data-ttu-id="ba1c2-126">Selecione **Links**.</span><span class="sxs-lookup"><span data-stu-id="ba1c2-126">Select **Links**.</span></span>

3. <span data-ttu-id="ba1c2-127">Em **Usuários**, selecione **Opções do usuário** .</span><span class="sxs-lookup"><span data-stu-id="ba1c2-127">Under **Users**, select **User options**.</span></span>

4. <span data-ttu-id="ba1c2-128">Selecione a guia **Fluxo de trabalho**.</span><span class="sxs-lookup"><span data-stu-id="ba1c2-128">Select the **Workflow** tab.</span></span>

5. <span data-ttu-id="ba1c2-129">Defina **Habilitar notificações para o aplicativo Teams** como **Sim** para habilitar notificações para o usuário ou como **Não** para desabilitar notificações para o usuário.</span><span class="sxs-lookup"><span data-stu-id="ba1c2-129">Set **Enable notifications for Teams app** to **Yes** to enable notifications for the user or **No** to disable notifications for the user.</span></span>

   ![Habilitar notificações do aplicativo Teams na guia Fluxo de trabalho de opções do usuário](./media/hr-admin-teams-leave-app-notifications.png)

6. <span data-ttu-id="ba1c2-131">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="ba1c2-131">Select **Save**.</span></span>

## <a name="known-issues"></a><span data-ttu-id="ba1c2-132">Problemas conhecidos</span><span class="sxs-lookup"><span data-stu-id="ba1c2-132">Known issues</span></span>

| <span data-ttu-id="ba1c2-133">Problema</span><span class="sxs-lookup"><span data-stu-id="ba1c2-133">Issue</span></span> | <span data-ttu-id="ba1c2-134">Status</span><span class="sxs-lookup"><span data-stu-id="ba1c2-134">Status</span></span> |
| --- | --- |
| <span data-ttu-id="ba1c2-135">O rolamento horizontal não funciona em telefones Android</span><span class="sxs-lookup"><span data-stu-id="ba1c2-135">Horizontal scrolling doesn't work on Android phones</span></span> | <span data-ttu-id="ba1c2-136">O rolamento horizontal não é um problema em dispositivos iOS ou de desktop.</span><span class="sxs-lookup"><span data-stu-id="ba1c2-136">Horizontal scrolling isn't an issue on iOS or desktop devices.</span></span> <span data-ttu-id="ba1c2-137">Estamos trabalhando em uma correção para o Android.</span><span class="sxs-lookup"><span data-stu-id="ba1c2-137">We're working on a fix for Android.</span></span> |
| <span data-ttu-id="ba1c2-138">Erro: há um problema ao encontrar um ambiente ao qual se conectar.</span><span class="sxs-lookup"><span data-stu-id="ba1c2-138">Error: There is an issue finding an environment to connect to.</span></span> | <span data-ttu-id="ba1c2-139">Você poderá receber esse erro mesmo que tenha verificado que o usuário pode acessar um ou mais ambientes de recursos humanos.</span><span class="sxs-lookup"><span data-stu-id="ba1c2-139">You might receive this error even if you've verified that the user can access one or more Human Resources environments.</span></span> <span data-ttu-id="ba1c2-140">Além disso, talvez você não veja todos os ambientes esperados.</span><span class="sxs-lookup"><span data-stu-id="ba1c2-140">Also, you might not see all the environments you expect.</span></span> <span data-ttu-id="ba1c2-141">Até corrigir esse problema, exclua o usuário e importe-os novamente para resolver o problema.</span><span class="sxs-lookup"><span data-stu-id="ba1c2-141">Until we fix this issue, delete the user and then import them in again to resolve the problem.</span></span> |
| <span data-ttu-id="ba1c2-142">O saldo exibido ao enviar folga para uma data futura está incorreto.</span><span class="sxs-lookup"><span data-stu-id="ba1c2-142">The balance is incorrect when submitting time off for a future date.</span></span> | <span data-ttu-id="ba1c2-143">A previsão ainda não está disponível.</span><span class="sxs-lookup"><span data-stu-id="ba1c2-143">Forecasting isn't yet available.</span></span> <span data-ttu-id="ba1c2-144">O saldo é exibido para a data atual.</span><span class="sxs-lookup"><span data-stu-id="ba1c2-144">The balance displays for the current date.</span></span> |
| <span data-ttu-id="ba1c2-145">Não é possível cancelar uma solicitação **Em revisão**.</span><span class="sxs-lookup"><span data-stu-id="ba1c2-145">Unable to cancel an **In review** request.</span></span> | <span data-ttu-id="ba1c2-146">Atualmente, essa funcionalidade não tem suporte e será adicionada em uma versão futura.</span><span class="sxs-lookup"><span data-stu-id="ba1c2-146">This functionality isn't currently supported and will be added in a future release.</span></span> |
| <span data-ttu-id="ba1c2-147">As informações de saldo são calculadas a partir de hoje.</span><span class="sxs-lookup"><span data-stu-id="ba1c2-147">Balance information is calculated as of today.</span></span> | <span data-ttu-id="ba1c2-148">O sistema atualmente não exibe os saldos a partir do período de acúmulo, mesmo se estiver configurado nos parâmetros de Licença e ausência.</span><span class="sxs-lookup"><span data-stu-id="ba1c2-148">The system currently doesn't display balances as of the accrual period, even if it's configured in Leave and absence parameters.</span></span> |

## <a name="privacy-notice"></a><span data-ttu-id="ba1c2-149">Aviso de privacidade</span><span class="sxs-lookup"><span data-stu-id="ba1c2-149">Privacy notice</span></span>

### <a name="microsoft-language-understanding-intelligent-service-luis"></a><span data-ttu-id="ba1c2-150">Serviço Inteligente de Reconhecimento Vocal (LUIS) da Microsoft</span><span class="sxs-lookup"><span data-stu-id="ba1c2-150">Microsoft Language Understanding Intelligent Service (LUIS)</span></span>

<span data-ttu-id="ba1c2-151">Com o bot do Dynamics 365 Human Resources no Microsoft Teams, as entradas de texto do usuário são analisadas para compreender a consulta/intenção subjacente.</span><span class="sxs-lookup"><span data-stu-id="ba1c2-151">With the Dynamics 365 Human Resources bot in Microsoft Teams, the user’s text inputs are analyzed for understanding the underlying query/intent.</span></span> <span data-ttu-id="ba1c2-152">A entrada do usuário, como "Pesquisar conta Contoso", é encaminhada para um dos Cognitive Services da Microsoft, chamado de Serviço Inteligente de Reconhecimento Vocal (LUIS).</span><span class="sxs-lookup"><span data-stu-id="ba1c2-152">The user’s input such as “Search account Contoso” is routed to one of Microsoft’s Cognitive Service called Language Understanding Intelligent Service (LUIS).</span></span> <span data-ttu-id="ba1c2-153">Leia mais sobre o LUIS  [aqui](https://www.luis.ai/).</span><span class="sxs-lookup"><span data-stu-id="ba1c2-153">Read more about LUIS [here](https://www.luis.ai/).</span></span> <span data-ttu-id="ba1c2-154">O serviço LUIS exclui a ambiguidade ou compreende a intenção da entrada do usuário (nesse caso, a intenção é encontrar informações) e a entidade de destino (nesse caso, a entidade pretendida é uma conta chamada Contoso).</span><span class="sxs-lookup"><span data-stu-id="ba1c2-154">The LUIS service disambiguates or understands the intent of user input (in this case, the intent is to find information) and the target entity (in this case, the intended entity is an account named Contoso).</span></span> <span data-ttu-id="ba1c2-155">Em seguida, essas informações são passadas para o [Azure Bot Framework](https://azure.microsoft.com/services/bot-service/) da Microsoft, que interage com os dados do Dynamics 365 Human Resources e recupera as informações desejadas para a consulta do usuário.</span><span class="sxs-lookup"><span data-stu-id="ba1c2-155">This information is then passed on to Microsoft’s [Azure bot framework](https://azure.microsoft.com/services/bot-service/), which interacts with data from Dynamics 365 Human Resources and retrieves the desired information for the user query.</span></span> 

<span data-ttu-id="ba1c2-156">Ao instalar e permitir o acesso ao uso do bot, você permite que o serviço LUIS e a estrutura de bot do Azure processem a intenção por trás da entrada, o que resulta em uma experiência aprimorada de conversa do usuário.</span><span class="sxs-lookup"><span data-stu-id="ba1c2-156">By installing and allowing access to use of the bot, you agree to allow the LUIS service and Azure bot framework to process the intent behind the input,  which results in an enhanced conversational user experience.</span></span> <span data-ttu-id="ba1c2-157">O serviço LUIS e a estrutura de bot do Azure têm vários níveis de conformidade em comparação com o Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="ba1c2-157">The LUIS service and Azure bot framework may have varying levels of compliance compared to Dynamics 365 Human Resources.</span></span> <span data-ttu-id="ba1c2-158">Embora o serviço LUIS tenha acesso a somente às consultas do usuário e não tenha sido desenvolvido para se conectar aos dados ou à conta do usuário do Dynamics 365 Human Resources, um usuário do bot do Dynamics 365 Human Resources poderia voluntariamente inserir uma consulta contendo Dados do Cliente, Dados Pessoais ou outros dados, e esse conteúdo da consulta poderia ser enviado para o serviço LUIS e para a estrutura de bot do Azure.</span><span class="sxs-lookup"><span data-stu-id="ba1c2-158">While the LUIS service has access to only the user queries and is not designed to be connected to the user’s Dynamics 365 Human Resources data or account, a user of the Dynamics 365 Human Resources bot could voluntarily enter a query containing Customer Data, Personal Data, or other data and such query content could get sent to the LUIS service and the Azure bot framework.</span></span> 

<span data-ttu-id="ba1c2-159">O conteúdo das consultas e das mensagens do usuário é mantido no sistema do LUIS por até 30 dias, criptografado em repouso e não é usado para treinamento ou melhoria de serviço.</span><span class="sxs-lookup"><span data-stu-id="ba1c2-159">The content of user’s queries and messages is retained in LUIS system for a maximum of 30 days, is encrypted at rest, and is not used for training or service improvement.</span></span> <span data-ttu-id="ba1c2-160">Leia mais sobre o Cognitive Services [aqui](https://azure.microsoft.com/services/cognitive-services/language-understanding-intelligent-service/).</span><span class="sxs-lookup"><span data-stu-id="ba1c2-160">Read more about Cognitive Services [here](https://azure.microsoft.com/services/cognitive-services/language-understanding-intelligent-service/).</span></span> 

<span data-ttu-id="ba1c2-161">Para gerenciar as configurações de administração de aplicativos no Microsoft Teams, vá para o [centro de administração do Microsoft Teams](https://admin.teams.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="ba1c2-161">To manage admin settings for apps in Microsoft Teams, go to the [Microsoft Teams admin center](https://admin.teams.microsoft.com/).</span></span>

### <a name="microsoft-azure-event-grid-and-microsoft-teams"></a><span data-ttu-id="ba1c2-162">Grade de Eventos do Microsoft Azure e Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ba1c2-162">Microsoft Azure Event Grid and Microsoft Teams</span></span>

<span data-ttu-id="ba1c2-163">Ao usar o recurso de notificações do aplicativo Dynamics 365 Human Resources no Teams, determinados dados do cliente fluirão fora da região geográfica em que o serviço de Human Resources do locatário é implantado.</span><span class="sxs-lookup"><span data-stu-id="ba1c2-163">When using the notifications feature for the Dynamics 365 Human Resources app in Teams, certain customer data will flow outside of the geographic region where your tenant’s Human Resources service is deployed.</span></span> <span data-ttu-id="ba1c2-164">O Dynamics 365 Human Resources transmite detalhes da solicitação de licença e da tarefa de fluxo de trabalho do funcionário para a Grade de Eventos do Microsoft Azure e o Microsoft Teams .</span><span class="sxs-lookup"><span data-stu-id="ba1c2-164">Dynamics 365 Human Resources transmits the employee’s leave request and workflow task details to Microsoft Azure Event Grid and Microsoft Teams.</span></span> <span data-ttu-id="ba1c2-165">Esses dados podem ser armazenados por até 24 horas e processados nos Estados Unidos, são criptografados em trânsito e em repouso, e não são usados pela Microsoft ou subprocessadores para treinamento ou melhorias de serviço.</span><span class="sxs-lookup"><span data-stu-id="ba1c2-165">This data may be stored for up to 24 hours and processed in the United States, is encrypted in transit and at rest, and is not used by Microsoft or its subprocessors for training or service improvements.</span></span>

## <a name="see-also"></a><span data-ttu-id="ba1c2-166">Consulte também</span><span class="sxs-lookup"><span data-stu-id="ba1c2-166">See also</span></span> 

[<span data-ttu-id="ba1c2-167">Baixar e instalar o Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ba1c2-167">Download and install Microsoft Teams</span></span>](https://support.office.com/article/download-and-install-microsoft-teams-422bf3aa-9ae8-46f1-83a2-e65720e1a34d)</br>
[<span data-ttu-id="ba1c2-168">Central de ajuda do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ba1c2-168">Microsoft Teams help center</span></span>](https://support.office.com/teams)</br>
[<span data-ttu-id="ba1c2-169">Gerenciar solicitações de licença no Teams</span><span class="sxs-lookup"><span data-stu-id="ba1c2-169">Manage leave requests in Teams</span></span>](hr-teams-leave-app.md)

