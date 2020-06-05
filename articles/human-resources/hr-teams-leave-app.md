---
title: Gerenciar solicitações de licença no Teams
description: Este tópico mostra como solicitar licenças no aplicativo do Dynamics 365 Human Resources no Microsoft Teams.
author: andreabichsel
manager: AnnBe
ms.date: 05/18/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-05-18
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 67501a1fa65493a1a23eb6176ece5be98d6e4659
ms.sourcegitcommit: 7fc0726c0a93ce6f4dafaad3232b4687f61cdc88
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/21/2020
ms.locfileid: "3392999"
---
# <a name="manage-leave-requests-in-teams"></a><span data-ttu-id="1faca-103">Gerenciar solicitações de licença no Teams</span><span class="sxs-lookup"><span data-stu-id="1faca-103">Manage leave requests in Teams</span></span>

[!include [banner](includes/preview-feature.md)]

<span data-ttu-id="1faca-104">O aplicativo Microsoft Dynamics 365 Human Resources no Microsoft Teams permite solicitar folgas rapidamente, além de visualizar as informações de saldo de folgas no Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="1faca-104">The Microsoft Dynamics 365 Human Resources app in Microsoft Teams lets you quickly request time off and view your time-off balance information right in Microsoft Teams.</span></span> <span data-ttu-id="1faca-105">Você pode interagir com um bot para solicitar informações.</span><span class="sxs-lookup"><span data-stu-id="1faca-105">You can interact with a bot to request information.</span></span> <span data-ttu-id="1faca-106">A guia **Folga** fornece informações mais detalhadas.</span><span class="sxs-lookup"><span data-stu-id="1faca-106">The **Time off** tab provides more detailed information.</span></span>

## <a name="install-the-app"></a><span data-ttu-id="1faca-107">Instalar o aplicativo</span><span class="sxs-lookup"><span data-stu-id="1faca-107">Install the app</span></span>

<span data-ttu-id="1faca-108">Você pode encontrar o aplicativo Human Resources na loja do Teams.</span><span class="sxs-lookup"><span data-stu-id="1faca-108">You can find the Human Resources app in the Teams store.</span></span>

1. <span data-ttu-id="1faca-109">No Microsoft Teams, selecione as reticências.</span><span class="sxs-lookup"><span data-stu-id="1faca-109">In Microsoft Teams, select the ellipses.</span></span>

   ![Reticências do aplicativo de licença do Human Resources Teams](./media/hr-teams-leave-app-ellipses.png)
 
2. <span data-ttu-id="1faca-111">Procure Dynamics 365 Human Resources, e selecione o título **Human Resources**.</span><span class="sxs-lookup"><span data-stu-id="1faca-111">Search for Dynamics 365 Human Resources, and then select the **Human Resources** tile.</span></span>

   ![Título do HR do aplicativo de licença do Human Resources Teams](./media/hr-teams-leave-app-human-resources-tile.png)

3. <span data-ttu-id="1faca-113">Selecione o botão **Adicionar** para instalar o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="1faca-113">Select the **Add** button to install the app.</span></span>

   ![Instalar o aplicativo de licença do Human Resources Teams](./media/hr-teams-leave-app-in-store.png)

<span data-ttu-id="1faca-115">Se o aplicativo não fizer logon automaticamente, selecione a guia **Configurações** para entrar.</span><span class="sxs-lookup"><span data-stu-id="1faca-115">If the app doesn't automatically sign you in, select the **Settings** tab to sign in.</span></span>

![Guia Configurações do aplicativo de licença do Human Resources Teams](./media/hr-teams-leave-app-settings-tab.png)

> [!NOTE]
> <span data-ttu-id="1faca-117">Caso você não veja uma caixa de diálogo de entrada, verifique as configurações do navegador para permitir janelas pop-up.</span><span class="sxs-lookup"><span data-stu-id="1faca-117">If you don’t see a sign-in dialog box, check your browser settings to allow pop-ups.</span></span> 

<span data-ttu-id="1faca-118">Se você tiver acesso a mais de uma instância do Human Resources, poderá selecionar a qual ambiente deseja se conectar na guia **Configurações**.</span><span class="sxs-lookup"><span data-stu-id="1faca-118">If you have access to more than one instance of Human Resources, you can select which environment you want to connect to in the **Settings** tab.</span></span>

> [!WARNING]
> <span data-ttu-id="1faca-119">Atualmente o aplicativo não oferece suporte à função de segurança do Administrador do Sistema e exibirá uma mensagem de erro caso você entre com uma conta de Administrador do Sistema.</span><span class="sxs-lookup"><span data-stu-id="1faca-119">The app doesn't currently support the System Administrator security role, and will display an error message if you sign in with a System Administrator account.</span></span> <span data-ttu-id="1faca-120">Para entrar com uma conta diferente, na guia **Configurações**, selecione o botão **Alternar contas** e entre com uma conta de usuário sem os privilégios de Administrador do Sistema.</span><span class="sxs-lookup"><span data-stu-id="1faca-120">To sign in with a different account, on the **Settings** tab, select the **Switch accounts** button, and then sign in with a user account that doesn’t have System Administrator privileges.</span></span>
 
## <a name="use-the-bot"></a><span data-ttu-id="1faca-121">Usar o bot</span><span class="sxs-lookup"><span data-stu-id="1faca-121">Use the bot</span></span>

<span data-ttu-id="1faca-122">Depois de instalar o aplicativo, será exibida uma mensagem de boas-vindas, informando os tipos de ações que o bot pode assumir em seu nome.</span><span class="sxs-lookup"><span data-stu-id="1faca-122">After the app installs, a welcome message appears, letting you know the types of actions the bot can take on your behalf.</span></span>

![Mensagem de boas-vindas do bot do aplicativo de licença do Human Resources Teams](./media/hr-teams-leave-app-bot.png)
 
> [!NOTE]
> <span data-ttu-id="1faca-124">Talvez você precise entrar na primeira interação com o bot.</span><span class="sxs-lookup"><span data-stu-id="1faca-124">When first interacting with the bot, you might need to sign in.</span></span> <span data-ttu-id="1faca-125">Caso você não veja uma caixa de diálogo de entrada, verifique as configurações do navegador para permitir janelas pop-up.</span><span class="sxs-lookup"><span data-stu-id="1faca-125">If you don’t see a sign-in dialog box, check your browser settings to allow pop-ups.</span></span>

<span data-ttu-id="1faca-126">Você pode pedir para o bot:</span><span class="sxs-lookup"><span data-stu-id="1faca-126">You can ask the bot to:</span></span>

- <span data-ttu-id="1faca-127">Mostrar informações do saldo de folgas para cada tipo de licença na qual você está inscrito.</span><span class="sxs-lookup"><span data-stu-id="1faca-127">Show time-off balance information for each leave type you're enrolled in.</span></span>

   ![Mostrar saldos do aplicativo de licença do Human Resources Teams](./media/hr-teams-leave-app-bot-balances.png)
 
- <span data-ttu-id="1faca-129">Mostrar detalhes adicionais sobre um tipo de licença específico.</span><span class="sxs-lookup"><span data-stu-id="1faca-129">Show additional details about a specific leave type.</span></span>

   ![Mostrar detalhes do aplicativo de licença do Human Resources Teams](./media/hr-teams-leave-app-bot-details.png)

- <span data-ttu-id="1faca-131">Iniciar uma solicitação de licença para você.</span><span class="sxs-lookup"><span data-stu-id="1faca-131">Start a leave request for you.</span></span>

   ![Solicitar licença no aplicativo de licença do Human Resources Teams](./media/hr-teams-leave-app-bot-request.png)
 
<span data-ttu-id="1faca-133">Depois de iniciar uma solicitação de licença, você pode ajustar os dias no próprio cartão, ou selecionar **Editar detalhes** para incluir informações adicionais à sua solicitação.</span><span class="sxs-lookup"><span data-stu-id="1faca-133">After you start a leave request, you can adjust the days right within the card, or you can select **Edit details** to add additional information to your request.</span></span>

![Editar solicitação no aplicativo de licença do Human Resources Teams](./media/hr-teams-leave-app-bot-edit.png)
 
<span data-ttu-id="1faca-135">Após inserir as informações, digite **Enviar** para enviá-la para aprovação.</span><span class="sxs-lookup"><span data-stu-id="1faca-135">When you're done entering information, type **Submit** to submit it for approval.</span></span> <span data-ttu-id="1faca-136">Você também pode digitar **Salvar como rascunho** para continuar depois.</span><span class="sxs-lookup"><span data-stu-id="1faca-136">You can also type **Save as draft** to come back to it later.</span></span>

![Enviar solicitação no aplicativo de licença do Human Resources Teams](./media/hr-teams-leave-app-bot-submit.png)

## <a name="manage-your-leave-in-teams"></a><span data-ttu-id="1faca-138">Gerenciar a sua licença no Teams</span><span class="sxs-lookup"><span data-stu-id="1faca-138">Manage your leave in Teams</span></span>

<span data-ttu-id="1faca-139">A guia **Folga** permite exibir:</span><span class="sxs-lookup"><span data-stu-id="1faca-139">The **Time off** tab allows you to view:</span></span>

- <span data-ttu-id="1faca-140">Informações do saldo para cada tipo de licença na qual você está inscrito</span><span class="sxs-lookup"><span data-stu-id="1faca-140">Balance information for each leave type you're enrolled in</span></span>

- <span data-ttu-id="1faca-141">Solicitações de licença futuras</span><span class="sxs-lookup"><span data-stu-id="1faca-141">Upcoming leave requests</span></span>

- <span data-ttu-id="1faca-142">Solicitações de folga</span><span class="sxs-lookup"><span data-stu-id="1faca-142">Time-off requests</span></span>

- <span data-ttu-id="1faca-143">Rascunho de solicitações de licença</span><span class="sxs-lookup"><span data-stu-id="1faca-143">Draft leave requests</span></span>

![Guia Folga do aplicativo de licença do Human Resources Teams](./media/hr-teams-leave-app-timeoff-tab.png)
 
### <a name="create-a-new-request"></a><span data-ttu-id="1faca-145">Criar uma solicitação</span><span class="sxs-lookup"><span data-stu-id="1faca-145">Create a new request</span></span>

1. <span data-ttu-id="1faca-146">Para criar uma solicitação de licença, selecione **Nova solicitação**.</span><span class="sxs-lookup"><span data-stu-id="1faca-146">To create a new leave request, select **New request**.</span></span>

   ![Nova solicitação no aplicativo de licença do Human Resources Teams](./media/hr-teams-leave-app-timeoff-tab-new.png)

2. <span data-ttu-id="1faca-148">Insira os dias que você deseja solicitar folga e depois selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="1faca-148">Enter the day or days you want to take off, and then select **Add**.</span></span>

   ![Adicionar folga no aplicativo de licença do Human Resources Teams](./media/hr-teams-leave-app-timeoff-tab-add.png)

3. <span data-ttu-id="1faca-150">Se aplicável, insira um código de motivo.</span><span class="sxs-lookup"><span data-stu-id="1faca-150">If applicable, enter a reason code.</span></span> <span data-ttu-id="1faca-151">Insira também comentários e adicione anexos.</span><span class="sxs-lookup"><span data-stu-id="1faca-151">Also enter any comments and add any attachments.</span></span>

4. <span data-ttu-id="1faca-152">Após inserir as informações, digite **Enviar** para enviá-la para aprovação.</span><span class="sxs-lookup"><span data-stu-id="1faca-152">When you're done entering information, type **Submit** to submit it for approval.</span></span> <span data-ttu-id="1faca-153">Você também pode digitar **Salvar como rascunho** para continuar depois.</span><span class="sxs-lookup"><span data-stu-id="1faca-153">You can also type **Save as draft** to come back to it later.</span></span>

### <a name="manage-draft-requests"></a><span data-ttu-id="1faca-154">Gerenciar solicitações em rascunho</span><span class="sxs-lookup"><span data-stu-id="1faca-154">Manage draft requests</span></span>

1. <span data-ttu-id="1faca-155">Selecione a guia **Rascunhos**.</span><span class="sxs-lookup"><span data-stu-id="1faca-155">Select the **Drafts** tab.</span></span>

   ![Guia Rascunhos do aplicativo de licença do Human Resources Teams](./media/hr-teams-leave-app-drafts-tab.png)

2. <span data-ttu-id="1faca-157">Selecione o lápis para editar a solicitação, ou selecione a lixeira para excluí-la.</span><span class="sxs-lookup"><span data-stu-id="1faca-157">Select the pencil to edit the request, or select the trash can to delete the request.</span></span>

3. <span data-ttu-id="1faca-158">Faça todas as alterações necessárias.</span><span class="sxs-lookup"><span data-stu-id="1faca-158">Make any necessary changes.</span></span> <span data-ttu-id="1faca-159">Após inserir as informações, digite **Enviar** para enviá-la para aprovação.</span><span class="sxs-lookup"><span data-stu-id="1faca-159">When you're done entering information, type **Submit** to submit it for approval.</span></span> <span data-ttu-id="1faca-160">Você também pode selecionar **Salvar como rascunho** para continuar depois.</span><span class="sxs-lookup"><span data-stu-id="1faca-160">You can also select **Save as draft** to come back to it later.</span></span>

   ![Editar rascunho no aplicativo de licença do Human Resources Teams](./media/hr-teams-leave-app-drafts-edit.png)
   
## <a name="privacy-notice"></a><span data-ttu-id="1faca-162">Aviso de privacidade</span><span class="sxs-lookup"><span data-stu-id="1faca-162">Privacy notice</span></span>

<span data-ttu-id="1faca-163">Com o bot do Dynamics 365 Human Resources no Microsoft Teams, as entradas de texto do usuário são analisadas para compreender a consulta/intenção subjacente.</span><span class="sxs-lookup"><span data-stu-id="1faca-163">With the Dynamics 365 Human Resources bot in Microsoft Teams, the user’s text inputs are analyzed for understanding the underlying query/intent.</span></span> <span data-ttu-id="1faca-164">A entrada do usuário, como "Pesquisar conta Contoso", é encaminhada para um dos Cognitive Services da Microsoft, chamado de Serviço Inteligente de Reconhecimento Vocal (LUIS).</span><span class="sxs-lookup"><span data-stu-id="1faca-164">The user’s input such as “Search account Contoso” is routed to one of Microsoft’s Cognitive Service called Language Understanding Intelligent Service (LUIS).</span></span> <span data-ttu-id="1faca-165">Leia mais sobre o LUIS  [aqui](https://www.luis.ai/).</span><span class="sxs-lookup"><span data-stu-id="1faca-165">Read more about LUIS [here](https://www.luis.ai/).</span></span> <span data-ttu-id="1faca-166">O serviço LUIS exclui a ambiguidade ou compreende a intenção da entrada do usuário (nesse caso, a intenção é encontrar informações) e a entidade de destino (nesse caso, a entidade pretendida é uma conta chamada Contoso).</span><span class="sxs-lookup"><span data-stu-id="1faca-166">The LUIS service disambiguates or understands the intent of user input (in this case, the intent is to find information) and the target entity (in this case, the intended entity is an account named Contoso).</span></span> <span data-ttu-id="1faca-167">Em seguida, essas informações são passadas para a [estrutura de bot do Azure](https://azure.microsoft.com/services/bot-service/) da Microsoft, que interage com os dados do Dynamics 365 Human Resources e recupera as informações desejadas para a consulta do usuário.</span><span class="sxs-lookup"><span data-stu-id="1faca-167">This information is then passed on to Microsoft’s [Azure bot framework](https://azure.microsoft.com/services/bot-service/) which interacts with data from Dynamics 365 Human Resources and retrieves the desired information for the user query.</span></span> 

<span data-ttu-id="1faca-168">Ao instalar e permitir o acesso ao uso do bot, você permite que o serviço LUIS e a estrutura de bot do Azure processem a intenção por trás da entrada, o que resulta em uma experiência aprimorada de conversa do usuário.</span><span class="sxs-lookup"><span data-stu-id="1faca-168">By installing and allowing access to use of the bot, you agree to allow the LUIS service and Azure bot framework to process the intent behind the input,  which results in an enhanced conversational user experience.</span></span> <span data-ttu-id="1faca-169">O serviço LUIS e a estrutura de bot do Azure têm vários níveis de conformidade em comparação com o Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="1faca-169">The LUIS service and Azure bot framework may have varying levels of compliance compared to Dynamics 365 Human Resources.</span></span> <span data-ttu-id="1faca-170">Embora o serviço LUIS tenha acesso a somente às consultas do usuário e não tenha sido desenvolvido para se conectar aos dados ou à conta do usuário do Dynamics 365 Human Resources, um usuário do bot do Dynamics 365 Human Resources poderia voluntariamente inserir uma consulta contendo Dados do Cliente, Dados Pessoais ou outros dados, e esse conteúdo da consulta poderia ser enviado para o serviço LUIS e para a estrutura de bot do Azure.</span><span class="sxs-lookup"><span data-stu-id="1faca-170">While the LUIS service has access to only the user queries and is not designed to be connected to the user’s Dynamics 365 Human Resources data or account, a user of the Dynamics 365 Human Resources bot could voluntarily enter a query containing Customer Data, Personal Data, or other data and such query content could get sent to the LUIS service and the Azure bot framework.</span></span> 

<span data-ttu-id="1faca-171">O conteúdo das consultas e das mensagens do usuário é mantido no sistema do LUIS por até 30 dias, criptografado em repouso e não é usado para treinamento ou melhoria de serviço.</span><span class="sxs-lookup"><span data-stu-id="1faca-171">The content of user’s queries and messages is retained in LUIS system for a maximum of 30 days, is encrypted at rest, and is not used for training or service improvement.</span></span> <span data-ttu-id="1faca-172">Leia mais sobre o Cognitive Services [aqui](https://azure.microsoft.com/services/cognitive-services/language-understanding-intelligent-service/).</span><span class="sxs-lookup"><span data-stu-id="1faca-172">Read more about Cognitive Services [here](https://azure.microsoft.com/services/cognitive-services/language-understanding-intelligent-service/).</span></span> 

<span data-ttu-id="1faca-173">Para gerenciar as configurações de administração de aplicativos no Microsoft Teams, vá para o [centro de administração do Microsoft Teams](https://admin.teams.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="1faca-173">To manage admin settings for apps in Microsoft Teams, go to the [Microsoft Teams admin center](https://admin.teams.microsoft.com/).</span></span> 

## <a name="see-also"></a><span data-ttu-id="1faca-174">Consulte também</span><span class="sxs-lookup"><span data-stu-id="1faca-174">See also</span></span>

[<span data-ttu-id="1faca-175">Baixar e instalar o Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="1faca-175">Download and install Microsoft Teams</span></span>](https://support.office.com/article/download-and-install-microsoft-teams-422bf3aa-9ae8-46f1-83a2-e65720e1a34d)</br>
[<span data-ttu-id="1faca-176">Central de ajuda do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="1faca-176">Microsoft Teams help center</span></span>](https://support.office.com/teams)</br>
[<span data-ttu-id="1faca-177">Aplicativo Human Resources no Teams</span><span class="sxs-lookup"><span data-stu-id="1faca-177">Human Resources app in Teams</span></span>](hr-admin-teams-leave-app.md)
