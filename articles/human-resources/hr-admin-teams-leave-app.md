---
title: Aplicativo Human Resources no Teams
description: Este tópico apresenta o aplicativo Microsoft Dynamics 365 Human Resources no Microsoft Teams.
author: andreabichsel
manager: AnnBe
ms.date: 05/18/2020
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
ms.openlocfilehash: 36684710e39c27840cc4aaa259a85579104fd8d6
ms.sourcegitcommit: ba340f836e472f13f263dec46a49847c788fca44
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/04/2020
ms.locfileid: "3431121"
---
# <a name="human-resources-app-in-teams"></a><span data-ttu-id="e2746-103">Aplicativo Human Resources no Teams</span><span class="sxs-lookup"><span data-stu-id="e2746-103">Human Resources app in Teams</span></span>

[!include [banner](includes/preview-feature.md)]

<span data-ttu-id="e2746-104">O aplicativo Microsoft Dynamics 365 Human Resources no Microsoft Teams permite aos funcionários solicitar folgas rapidamente, além de visualizar suas informações de saldo de folgas no Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="e2746-104">The Microsoft Dynamics 365 Human Resources app in Microsoft Teams lets employees quickly request time off and view their time-off balance information in Microsoft Teams.</span></span> <span data-ttu-id="e2746-105">Os funcionários podem interagir com um bot para solicitar informações.</span><span class="sxs-lookup"><span data-stu-id="e2746-105">Employees can interact with a bot to request information.</span></span> <span data-ttu-id="e2746-106">A guia **Folga** fornece informações mais detalhadas.</span><span class="sxs-lookup"><span data-stu-id="e2746-106">The **Time off** tab provides more detailed information.</span></span>

![Bot do aplicativo de licenças do Human Resources Teams](./media/hr-admin-teams-leave-app-bot.png)

![Guia Folga do aplicativo de licença do Human Resources Teams](./media/hr-teams-leave-app-timeoff-tab.png)

## <a name="install-and-setup"></a><span data-ttu-id="e2746-109">Instalação e configuração</span><span class="sxs-lookup"><span data-stu-id="e2746-109">Install and setup</span></span>

<span data-ttu-id="e2746-110">Você pode encontrar o aplicativo Human Resources na loja do Teams.</span><span class="sxs-lookup"><span data-stu-id="e2746-110">You can find the Human Resources app in the Teams store.</span></span> <span data-ttu-id="e2746-111">Para obter informações sobre como instalar o aplicativo do Teams, consulte [Gerenciar solicitações de licença no Teams](hr-teams-leave-app.md).</span><span class="sxs-lookup"><span data-stu-id="e2746-111">For information about installing the Teams app, see [Manage leave requests in Teams](hr-teams-leave-app.md).</span></span>

<span data-ttu-id="e2746-112">Para obter informações sobre como gerenciar permissões de aplicativo no Teams, consulte [Gerenciar políticas de permissão de aplicativo no Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/teams-app-permission-policies).</span><span class="sxs-lookup"><span data-stu-id="e2746-112">For information about managing app permissions in Teams, see [Manage app permission policies in Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/teams-app-permission-policies).</span></span>

## <a name="known-issues"></a><span data-ttu-id="e2746-113">Problemas conhecidos</span><span class="sxs-lookup"><span data-stu-id="e2746-113">Known issues</span></span>

| <span data-ttu-id="e2746-114">Problema</span><span class="sxs-lookup"><span data-stu-id="e2746-114">Issue</span></span> | <span data-ttu-id="e2746-115">Status</span><span class="sxs-lookup"><span data-stu-id="e2746-115">Status</span></span> |
| --- | --- |
| <span data-ttu-id="e2746-116">Erro: há um problema ao encontrar um ambiente ao qual se conectar.</span><span class="sxs-lookup"><span data-stu-id="e2746-116">Error: There is an issue finding an environment to connect to.</span></span> | <span data-ttu-id="e2746-117">Você poderá receber esse erro mesmo que tenha verificado que o usuário pode acessar um ou mais ambientes de recursos humanos.</span><span class="sxs-lookup"><span data-stu-id="e2746-117">You might receive this error even if you've verified that the user can access one or more Human Resources environments.</span></span> <span data-ttu-id="e2746-118">Além disso, talvez você não veja todos os ambientes esperados.</span><span class="sxs-lookup"><span data-stu-id="e2746-118">In addtion, you might not see all the environments you expect.</span></span> <span data-ttu-id="e2746-119">Até corrigir esse problema, exclua o usuário e importe-os novamente para resolver o problema.</span><span class="sxs-lookup"><span data-stu-id="e2746-119">Until we fix this issue, delete the user and then import them in again to resolve the problem.</span></span> |
| <span data-ttu-id="e2746-120">O saldo exibido ao enviar folga para uma data futura está incorreto.</span><span class="sxs-lookup"><span data-stu-id="e2746-120">The balance is incorrect when submitting time off for a future date.</span></span> | <span data-ttu-id="e2746-121">A previsão ainda não está disponível.</span><span class="sxs-lookup"><span data-stu-id="e2746-121">Forecasting isn't yet available.</span></span> <span data-ttu-id="e2746-122">O saldo é exibido para a data atual.</span><span class="sxs-lookup"><span data-stu-id="e2746-122">The balance displays for the current date.</span></span> |
| <span data-ttu-id="e2746-123">Ao reduzir o número de horas tiradas em uma solicitação existente, o **Saldo restante** diminui em vez de aumentar.</span><span class="sxs-lookup"><span data-stu-id="e2746-123">When reducing the number of hours taken in an existing request, the **Remaining balance** goes down instead of up.</span></span> | <span data-ttu-id="e2746-124">Abordaremos esse problema conhecido no futuro.</span><span class="sxs-lookup"><span data-stu-id="e2746-124">We'll address this known issue in the future.</span></span> <span data-ttu-id="e2746-125">A exibição está incorreta, mas os valores corretos são ajustados após o envio.</span><span class="sxs-lookup"><span data-stu-id="e2746-125">The display is incorrect, but the correct amounts are adjusted upon submission.</span></span> |
| <span data-ttu-id="e2746-126">Dois cartões de **Próxima folga** são exibidos para as mesmas datas.</span><span class="sxs-lookup"><span data-stu-id="e2746-126">Two **Upcoming time off** cards display for the same dates.</span></span> | <span data-ttu-id="e2746-127">Os cartões representam envios individuais.</span><span class="sxs-lookup"><span data-stu-id="e2746-127">The cards represent individual submissions.</span></span> <span data-ttu-id="e2746-128">Continuaremos recebendo feedback e fazendo ajustes.</span><span class="sxs-lookup"><span data-stu-id="e2746-128">We'll continue to take feedback and make adjustments.</span></span> |
| <span data-ttu-id="e2746-129">Não é possível cancelar uma solicitação **Em revisão**.</span><span class="sxs-lookup"><span data-stu-id="e2746-129">Unable to cancel an **In review** request.</span></span> | <span data-ttu-id="e2746-130">Atualmente, essa funcionalidade não tem suporte e será adicionada em uma versão futura.</span><span class="sxs-lookup"><span data-stu-id="e2746-130">This functionality isn't currently supported and will be added in a future release.</span></span> |
| <span data-ttu-id="e2746-131">As informações de saldo são calculadas a partir de hoje.</span><span class="sxs-lookup"><span data-stu-id="e2746-131">Balance information is calculated as of today.</span></span> | <span data-ttu-id="e2746-132">O sistema atualmente não exibe os saldos a partir do período de acúmulo, mesmo se estiver configurado nos parâmetros de Licença e ausência.</span><span class="sxs-lookup"><span data-stu-id="e2746-132">The system currently doesn't display balances as of the accrual period, even if it's configured in Leave and absence parameters.</span></span> |

## <a name="privacy-notice"></a><span data-ttu-id="e2746-133">Aviso de privacidade</span><span class="sxs-lookup"><span data-stu-id="e2746-133">Privacy notice</span></span>

<span data-ttu-id="e2746-134">Com o bot do Dynamics 365 Human Resources no Microsoft Teams, as entradas de texto do usuário são analisadas para compreender a consulta/intenção subjacente.</span><span class="sxs-lookup"><span data-stu-id="e2746-134">With the Dynamics 365 Human Resources bot in Microsoft Teams, the user’s text inputs are analyzed for understanding the underlying query/intent.</span></span> <span data-ttu-id="e2746-135">A entrada do usuário, como "Pesquisar conta Contoso", é encaminhada para um dos Cognitive Services da Microsoft, chamado de Serviço Inteligente de Reconhecimento Vocal (LUIS).</span><span class="sxs-lookup"><span data-stu-id="e2746-135">The user’s input such as “Search account Contoso” is routed to one of Microsoft’s Cognitive Service called Language Understanding Intelligent Service (LUIS).</span></span> <span data-ttu-id="e2746-136">Leia mais sobre o LUIS  [aqui](https://www.luis.ai/).</span><span class="sxs-lookup"><span data-stu-id="e2746-136">Read more about LUIS [here](https://www.luis.ai/).</span></span> <span data-ttu-id="e2746-137">O serviço LUIS exclui a ambiguidade ou compreende a intenção da entrada do usuário (nesse caso, a intenção é encontrar informações) e a entidade de destino (nesse caso, a entidade pretendida é uma conta chamada Contoso).</span><span class="sxs-lookup"><span data-stu-id="e2746-137">The LUIS service disambiguates or understands the intent of user input (in this case, the intent is to find information) and the target entity (in this case, the intended entity is an account named Contoso).</span></span> <span data-ttu-id="e2746-138">Em seguida, essas informações são passadas para a [estrutura de bot do Azure](https://azure.microsoft.com/services/bot-service/) da Microsoft, que interage com os dados do Dynamics 365 Human Resources e recupera as informações desejadas para a consulta do usuário.</span><span class="sxs-lookup"><span data-stu-id="e2746-138">This information is then passed on to Microsoft’s [Azure bot framework](https://azure.microsoft.com/services/bot-service/) which interacts with data from Dynamics 365 Human Resources and retrieves the desired information for the user query.</span></span> 

<span data-ttu-id="e2746-139">Ao instalar e permitir o acesso ao uso do bot, você permite que o serviço LUIS e a estrutura de bot do Azure processem a intenção por trás da entrada, o que resulta em uma experiência aprimorada de conversa do usuário.</span><span class="sxs-lookup"><span data-stu-id="e2746-139">By installing and allowing access to use of the bot, you agree to allow the LUIS service and Azure bot framework to process the intent behind the input,  which results in an enhanced conversational user experience.</span></span> <span data-ttu-id="e2746-140">O serviço LUIS e a estrutura de bot do Azure têm vários níveis de conformidade em comparação com o Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="e2746-140">The LUIS service and Azure bot framework may have varying levels of compliance compared to Dynamics 365 Human Resources.</span></span> <span data-ttu-id="e2746-141">Embora o serviço LUIS tenha acesso a somente às consultas do usuário e não tenha sido desenvolvido para se conectar aos dados ou à conta do usuário do Dynamics 365 Human Resources, um usuário do bot do Dynamics 365 Human Resources poderia voluntariamente inserir uma consulta contendo Dados do Cliente, Dados Pessoais ou outros dados, e esse conteúdo da consulta poderia ser enviado para o serviço LUIS e para a estrutura de bot do Azure.</span><span class="sxs-lookup"><span data-stu-id="e2746-141">While the LUIS service has access to only the user queries and is not designed to be connected to the user’s Dynamics 365 Human Resources data or account, a user of the Dynamics 365 Human Resources bot could voluntarily enter a query containing Customer Data, Personal Data, or other data and such query content could get sent to the LUIS service and the Azure bot framework.</span></span> 

<span data-ttu-id="e2746-142">O conteúdo das consultas e das mensagens do usuário é mantido no sistema do LUIS por até 30 dias, criptografado em repouso e não é usado para treinamento ou melhoria de serviço.</span><span class="sxs-lookup"><span data-stu-id="e2746-142">The content of user’s queries and messages is retained in LUIS system for a maximum of 30 days, is encrypted at rest, and is not used for training or service improvement.</span></span> <span data-ttu-id="e2746-143">Leia mais sobre o Cognitive Services [aqui](https://azure.microsoft.com/services/cognitive-services/language-understanding-intelligent-service/).</span><span class="sxs-lookup"><span data-stu-id="e2746-143">Read more about Cognitive Services [here](https://azure.microsoft.com/services/cognitive-services/language-understanding-intelligent-service/).</span></span> 

<span data-ttu-id="e2746-144">Para gerenciar as configurações de administração de aplicativos no Microsoft Teams, vá para o [centro de administração do Microsoft Teams](https://admin.teams.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="e2746-144">To manage admin settings for apps in Microsoft Teams, go to the [Microsoft Teams admin center](https://admin.teams.microsoft.com/).</span></span> 

## <a name="see-also"></a><span data-ttu-id="e2746-145">Consulte também</span><span class="sxs-lookup"><span data-stu-id="e2746-145">See also</span></span> 

[<span data-ttu-id="e2746-146">Baixar e instalar o Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="e2746-146">Download and install Microsoft Teams</span></span>](https://support.office.com/article/download-and-install-microsoft-teams-422bf3aa-9ae8-46f1-83a2-e65720e1a34d)</br>
[<span data-ttu-id="e2746-147">Central de ajuda do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="e2746-147">Microsoft Teams help center</span></span>](https://support.office.com/teams)</br>
[<span data-ttu-id="e2746-148">Gerenciar solicitações de licença no Teams</span><span class="sxs-lookup"><span data-stu-id="e2746-148">Manage leave requests in Teams</span></span>](hr-teams-leave-app.md)
