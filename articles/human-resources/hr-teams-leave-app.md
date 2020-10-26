---
title: Gerenciar solicitações de licença no Teams
description: Este tópico mostra como solicitar licenças no aplicativo do Dynamics 365 Human Resources no Microsoft Teams.
author: andreabichsel
manager: AnnBe
ms.date: 09/30/2020
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
ms.openlocfilehash: c6856e417ee47f8f582f797c5bcedcff23a1432f
ms.sourcegitcommit: b6ab46f6e5ce60e2c3d70a348827eaf60c84cae2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/01/2020
ms.locfileid: "3929984"
---
# <a name="manage-leave-requests-in-teams"></a>Gerenciar solicitações de licença no Teams

[!include [banner](includes/preview-feature.md)]

O aplicativo Microsoft Dynamics 365 Human Resources no Microsoft Teams permite solicitar folgas rapidamente, além de visualizar as informações de saldo de folgas no Microsoft Teams. Você pode interagir com um bot para solicitar informações e iniciar uma solicitação de licença. A guia **Folga** fornece informações mais detalhadas. Além disso, você pode enviar às pessoas informações sobre suas próximas folgas em equipes e bate-papos fora do aplicativo Human Resources.

## <a name="install-the-app"></a>Instalar o aplicativo

Você pode encontrar o aplicativo Human Resources na loja do Teams.

1. No Microsoft Teams, selecione as reticências.

   ![Reticências do aplicativo de licença do Human Resources Teams](./media/hr-teams-leave-app-ellipses.png)
 
2. Procure Dynamics 365 Human Resources, e selecione o título **Human Resources**.

   ![Título do HR do aplicativo de licença do Human Resources Teams](./media/hr-teams-leave-app-human-resources-tile.png)

3. Selecione o botão **Adicionar** para instalar o aplicativo.

   ![Instalar o aplicativo de licença do Human Resources Teams](./media/hr-teams-leave-app-in-store.png)

Se o aplicativo não fizer logon automaticamente, selecione a guia **Configurações** para entrar.

![Guia Configurações do aplicativo de licença do Human Resources Teams](./media/hr-teams-leave-app-settings-tab.png)

> [!NOTE]
> Caso você não veja uma caixa de diálogo de entrada, verifique as configurações do navegador para permitir janelas pop-up. 

Se você tiver acesso a mais de uma instância do Human Resources, poderá selecionar a qual ambiente deseja se conectar na guia **Configurações**.

> [!NOTE]
> O aplicativo agora oferece suporte à função de segurança Administrador do sistema.
 
## <a name="use-the-bot"></a>Usar o bot

Depois de instalar o aplicativo, será exibida uma mensagem de boas-vindas, informando os tipos de ações que o bot pode assumir em seu nome.

![Mensagem de boas-vindas do bot do aplicativo de licença do Human Resources Teams](./media/hr-teams-leave-app-bot.png)
 
> [!NOTE]
> Talvez você precise entrar na primeira interação com o bot. Caso você não veja uma caixa de diálogo de entrada, verifique as configurações do navegador para permitir janelas pop-up.

Você pode pedir para o bot:

- Mostrar informações do saldo de folgas para cada tipo de licença na qual você está inscrito.

   ![Mostrar saldos do aplicativo de licença do Human Resources Teams](./media/hr-teams-leave-app-bot-balances.png)
 
- Mostrar detalhes adicionais sobre um tipo de licença específico.

   ![Mostrar detalhes do aplicativo de licença do Human Resources Teams](./media/hr-teams-leave-app-bot-details.png)

- Iniciar uma solicitação de licença para você.

   ![Solicitar licença no aplicativo de licença do Human Resources Teams](./media/hr-teams-leave-app-bot-request.png)
 
Depois de iniciar uma solicitação de licença, você pode ajustar os dias diretamente no cartão.

![Editar solicitação no aplicativo de licença do Human Resources Teams](./media/hr-teams-leave-app-bot-edit.png)
 
Após inserir as informações, selecione **Enviar** para enviá-las para aprovação. Você também pode selecionar **Salvar como rascunho** para continuar depois.

![Enviar solicitação no aplicativo de licença do Human Resources Teams](./media/hr-teams-leave-app-bot-submit.png)

## <a name="manage-your-leave-in-teams"></a>Gerenciar a sua licença no Teams

A guia **Folga** permite exibir:

- Informações do saldo para cada tipo de licença na qual você está inscrito

- Solicitações de licença futuras

- Solicitações de folga

- Rascunho de solicitações de licença

![Guia Folga do aplicativo de licença do Human Resources Teams](./media/hr-teams-leave-app-timeoff-tab.png)
 
### <a name="create-a-new-request"></a>Criar uma solicitação

1. Para criar uma solicitação de licença, selecione **Nova solicitação**.

   ![Nova solicitação no aplicativo de licença do Human Resources Teams](./media/hr-teams-leave-app-timeoff-tab-new.png)

2. Insira os dias que você deseja solicitar folga e depois selecione **Adicionar**.

   ![Adicionar folga no aplicativo de licença do Human Resources Teams](./media/hr-teams-leave-app-timeoff-tab-add.png)

3. Se aplicável, insira um código de motivo. Insira também comentários e adicione anexos.

4. Após inserir as informações, digite **Enviar** para enviá-la para aprovação. Você também pode digitar **Salvar como rascunho** para continuar depois.

### <a name="manage-draft-requests"></a>Gerenciar solicitações em rascunho

1. Selecione a guia **Rascunhos**.

   ![Guia Rascunhos do aplicativo de licença do Human Resources Teams](./media/hr-teams-leave-app-drafts-tab.png)

2. Selecione o lápis para editar a solicitação, ou selecione a lixeira para excluí-la.

3. Faça todas as alterações necessárias. Após inserir as informações, digite **Enviar** para enviá-la para aprovação. Você também pode selecionar **Salvar como rascunho** para continuar depois.

   ![Editar rascunho no aplicativo de licença do Human Resources Teams](./media/hr-teams-leave-app-drafts-edit.png)
   
### <a name="respond-to-teams-notifications"></a>Responder a notificações do Teams

Quando você ou um trabalhador para o qual você é um aprovador enviar uma solicitação de licença, você receberá uma notificação no aplicativo Human Resources no Teams. Você pode selecionar a notificação para exibi-la. As notificações também aparecem na área **Chat** .

Se você for aprovador, poderá selecionar **Aprovar** ou **Negar** na notificação. Você também pode fornecer uma mensagem opcional.

![Deixar uma notificação de solicitação no aplicativo Human Resources no Teams](./media/hr-teams-leave-app-notification.png)

## <a name="send-upcoming-time-off-information-to-your-coworkers"></a>Enviar informações sobre as próximas folgas para seus colegas de trabalho

Depois de instalar o aplicativo Human Resources para o Teams, você pode enviar facilmente informações sobre sua próxima folga para seus colegas de trabalho em equipes ou bate-papos.

1. Em uma equipe ou chat no Teams, selecione o botão do Human Resources abaixo da janela de chat.

   ![Botão do Human Resources abaixo da janela de bate-papo](./media/hr-teams-leave-app-chat-button.png)

2. Selecione a solicitação de licença que deseja compartilhar. Se você deseja compartilhar um rascunho de solicitação de licença, selecione **Rascunhos** primeiro.

   ![Selecionar uma próxima solicitação de licença para compartilhar](./media/hr-teams-leave-app-chat-search.png)

Sua solicitação de licença será exibida no chat.

![Cartão de solicitação de licença do Human Resources](./media/hr-teams-leave-app-chat-card.png)

Se você compartilhou uma solicitação de rascunho, ela será exibida como rascunho:

![Rascunho do cartão de solicitação de licença do Human Resources](./media/hr-teams-leave-app-chat-draft-card.png)

## <a name="view-your-teams-leave-calendar"></a>Exibir o calendário de licença da equipe

Se você for um gerente com subordinados diretos, poderá exibir folgas aprovadas e pendentes da sua equipe.

1. No aplicativo Human Resources no Teams, selecione **Folga** .

2. Selecione **Calendário da equipe** .

   ![Exibir calendário no aplicativo Human Resources do Teams](./media/hr-teams-leave-app-view-calendar.png)

O calendário exibe as folgas aprovadas e pendentes dos subordinados diretos.

![Calendário de folgas no aplicativo Human Resources do Teams](./media/hr-teams-leave-app-calendar.png)

## <a name="troubleshooting"></a>Solução de problemas

Se você tiver problemas para entrar ou ao usar o aplicativo do Human Resources no Teams, tente seguir estas instruções de solução de problemas. Se você ainda tiver problemas após a solução de problemas, contate o Suporte. Para obter mais informações, consulte [Obter suporte](hr-admin-troubleshooting-support.md).

### <a name="cant-sign-into-the-human-resources-app-in-teams"></a>Não é possível entrar no aplicativo do Human Resources no Teams

Se não conseguir entrar no aplicativo, é possível que a conta que você esteja usando para entrar no Microsoft Teams não esteja associada a um registro de funcionário no Dynamics 365 Human Resources. Entre em contato com o administrador do sistema para verificar se o registro de funcionário está associado corretamente.

### <a name="error-when-approving-leave-requests-in-the-human-resources-app-in-teams"></a>Erro ao aprovar solicitações de licença no aplicativo do Human Resources no Teams

Se você receber um erro ao tentar aprovar solicitações de licença no aplicativo do Teams, execute as seguintes etapas de solução de problemas:

1. Verifique se a conta que você está usando para entrar no Microsoft Teams é a mesma que usa para acessar o Dynamics 365 Human Resources.

2. Verifique se você é um aprovador válido para a solicitação ao verificar as configurações do fluxo de trabalho para a aprovação de licenças. Para obter mais informações sobre fluxos de trabalho de solicitações de licença, consulte [Criar um fluxo de trabalho de solicitações de licença](hr-leave-and-absence-workflow.md).

## <a name="privacy-notice"></a>Aviso de privacidade

### <a name="microsoft-language-understanding-intelligent-service-luis"></a>Serviço Inteligente de Reconhecimento Vocal (LUIS) da Microsoft

Com o bot do Dynamics 365 Human Resources no Microsoft Teams, as entradas de texto do usuário são analisadas para compreender a consulta/intenção subjacente. A entrada do usuário, como "Pesquisar conta Contoso", é encaminhada para um dos Cognitive Services da Microsoft, chamado de Serviço Inteligente de Reconhecimento Vocal (LUIS). Leia mais sobre o LUIS  [aqui](https://www.luis.ai/). O serviço LUIS exclui a ambiguidade ou compreende a intenção da entrada do usuário (nesse caso, a intenção é encontrar informações) e a entidade de destino (nesse caso, a entidade pretendida é uma conta chamada Contoso). Em seguida, essas informações são passadas para o [Azure Bot Framework](https://azure.microsoft.com/services/bot-service/) da Microsoft, que interage com os dados do Dynamics 365 Human Resources e recupera as informações desejadas para a consulta do usuário. 

Ao instalar e permitir o acesso ao uso do bot, você permite que o serviço LUIS e a estrutura de bot do Azure processem a intenção por trás da entrada, o que resulta em uma experiência aprimorada de conversa do usuário. O serviço LUIS e a estrutura de bot do Azure têm vários níveis de conformidade em comparação com o Dynamics 365 Human Resources. Embora o serviço LUIS tenha acesso a somente às consultas do usuário e não tenha sido desenvolvido para se conectar aos dados ou à conta do usuário do Dynamics 365 Human Resources, um usuário do bot do Dynamics 365 Human Resources poderia voluntariamente inserir uma consulta contendo Dados do Cliente, Dados Pessoais ou outros dados, e esse conteúdo da consulta poderia ser enviado para o serviço LUIS e para a estrutura de bot do Azure. 

O conteúdo das consultas e das mensagens do usuário é mantido no sistema do LUIS por até 30 dias, criptografado em repouso e não é usado para treinamento ou melhoria de serviço. Leia mais sobre o Cognitive Services [aqui](https://azure.microsoft.com/services/cognitive-services/language-understanding-intelligent-service/). 

Para gerenciar as configurações de administração de aplicativos no Microsoft Teams, vá para o [centro de administração do Microsoft Teams](https://admin.teams.microsoft.com/).

### <a name="microsoft-teams-azure-event-grid-and-azure-cosmos-db"></a>Microsoft Teams, Azure Event Grid e Azure Cosmos DB

Ao usar o aplicativo Dynamics 365 Human Resources no Microsoft Teams, determinados dados do cliente podem fluir fora da região geográfica em que o serviço de Human Resources do locatário é implantado.

O Dynamics 365 Human Resources transmite detalhes da solicitação de licença e da tarefa de fluxo de trabalho do funcionário para a Grade de Eventos do Microsoft Azure e o Microsoft Teams . Esses dados podem ser armazenados na Grade de Eventos do Microsoft Azure por até 24 horas e podem ser processados nos Estados Unidos, são criptografados em trânsito e em repouso, e não são usados pela Microsoft ou subprocessadores para treinamento ou melhorias de serviço. Para entender onde seus dados são armazenados no Teams, consulte: [Localização dos dados no Microsoft Teams](https://docs.microsoft.com/microsoftteams/location-of-data-in-teams?view=o365-worldwide&preserve-view=true).

Ao conversar com o bot de bate-papo no aplicativo Human Resources, o conteúdo da conversa pode ser armazenado no Azure Cosmos DB e transmitido ao Microsoft Teams. Esses dados podem ser armazenados no Azure Cosmos DB por até 24 horas e podem ser processados fora da região geográfica onde o serviço do Human Resources do seu locatário está implantado, é criptografado em trânsito e em repouso e não é usado pela Microsoft ou seus subprocessadores para treinamento ou melhorias de serviço. Para entender onde seus dados são armazenados no Teams, consulte: [Localização dos dados no Microsoft Teams](https://docs.microsoft.com/microsoftteams/location-of-data-in-teams?view=o365-worldwide&preserve-view=true).
 
Para restringir o acesso ao aplicativo Human Resources no Microsoft Teams para sua organização ou usuários dentro de sua organização, consulte [Gerenciar políticas de permissão de aplicativo no Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/teams-app-permission-policies).

## <a name="see-also"></a>Consulte também

[Baixar e instalar o Microsoft Teams](https://support.office.com/article/download-and-install-microsoft-teams-422bf3aa-9ae8-46f1-83a2-e65720e1a34d)</br>
[Central de ajuda do Microsoft Teams](https://support.office.com/teams)</br>
[Aplicativo Human Resources no Teams](hr-admin-teams-leave-app.md)
