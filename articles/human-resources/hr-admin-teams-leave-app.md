---
title: Aplicativo Human Resources no Teams
description: Este artigo apresenta o aplicativo Microsoft Dynamics 365 Human Resources no Microsoft Teams.
author: twheeloc
ms.date: 12/15/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: FeatureManagementWorkspace
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-05-18
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: d29802bdf3411c93f20d710e1f26e541e5022d57
ms.sourcegitcommit: 3aa3dedc3123cb079614762e2718841c2f7d7d35
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/30/2022
ms.locfileid: "9812177"
---
# <a name="human-resources-app-in-teams"></a>Aplicativo Human Resources no Teams


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

O aplicativo Microsoft Dynamics 365 Human Resources no Microsoft Teams permite aos funcionários solicitar folgas rapidamente, além de exibir suas informações de saldo de folgas no Microsoft Teams. Os funcionários podem interagir com um bot para solicitar informações. A guia **Folga** fornece informações mais detalhadas. Além disso, eles podem enviar às pessoas informações sobre suas próximas folgas em equipes e bate-papos fora do aplicativo do Human Resources.

![Bot do aplicativo de licenças do Human Resources Teams.](./media/hr-teams-leave-app-bot.png)

![Guia Folga do aplicativo de licença do Human Resources Teams.](./media/hr-teams-leave-app-timeoff-tab.png)

![Cartão de solicitação de licença do Human Resources.](./media/hr-teams-leave-app-chat-card.png)

## <a name="install-and-setup"></a>Instalação e configuração

Você pode encontrar o aplicativo Dynamics 365 Human Resources na loja do Teams. Para obter informações sobre como instalar o aplicativo do Teams, consulte [Gerenciar solicitações de licença no Teams](hr-teams-leave-app.md).

Para obter informações sobre como gerenciar permissões de aplicativo no Teams, consulte [Gerenciar políticas de permissão de aplicativo no Microsoft Teams](/MicrosoftTeams/teams-app-permission-policies).

Se desejar que os usuários exibam o Calendário de licenças e ausências no aplicativo, habilite o **Calendário de licenças e ausências no Teams** no Gerenciamento de recursos. Para obter mais informações sobre como habilitar recursos, consulte [Gerenciar recursos](hr-admin-manage-features.md).

## <a name="update-app"></a>Atualizar aplicativo
>[!NOTE]
> A partir de 20 de dezembro de 2021, os serviços de bot do aplicativo Human Resources hospedados no locatário da Microsoft serão desativados. Não haverá nenhum impacto para uma extensão atualizada (versão 1.1.5) que está disponível para instalação. O impacto principal será na extensão desatualizada (versão 1.1.4). O bot de chat desta versão deixará de funcionar. A guia **Folga** continuará funcionando em ambas as extensões.

Para a versão 1.1.4, o bot de chat deixa de responder a todas as mensagens. Por exemplo, **Entrar**, **Exibir saldos** e **Ver folga**. O aplicativo deve ser atualizado manualmente para a versão mais recente. Para obter mais informações, consulte [Atualizar aplicativos no Microsoft Teams](/MicrosoftTeams/apps-update-experience).

Para atualizar para a versão 1.1.5, siga estas etapas:
1. No Microsoft Teams, vá para **Aplicativos**.
2. Encontre o aplicativo **Human Resources**.
3. Selecione **Atualizar**.

Para verificar a versão do aplicativo Human Resources, acesse a guia **Sobre** ou a seção **Aplicativo pessoal**. 

![Guia **Sobre** do Human Resources.](./media/HR-teams-about.png)

## <a name="enable-notifications-for-the-human-resources-app-in-teams"></a>Habilitar notificações para o aplicativo de recursos humanos no Teams

Para que os usuários recebam notificações de solicitação de licença no aplicativo Teams, habilite notificações no Dynamics 365 Human Resources.

>[!NOTE]
>Somente usuários conectados ao Teams e que utilizem o aplicativo Dynamics 365 Human Resources no Teams receberão notificações.

1. No Human Resources, selecione **Administração do sistema**.

2. Selecione **Links**.

3. Em **Configuração** , selecione **Parâmetros do sistema** .

4. Na guia **Geral**, defina **Habilitar notificações para o aplicativo Teams** como **Sim** .

   ![Habilitar notificações do aplicativo Teams nos Parâmetros do Sistema.](./media/hr-admin-teams-leave-app-enable-notifications.png)

5. Para ativar notificações do Teams para todos os usuários, selecione **Sim** no prompt.

   ![Habilitar notificações do Teams para todos os usuários.](./media/hr-admin-teams-leave-app-notifications-all-users.png)

### <a name="turn-teams-notifications-on-or-off-for-individual-users"></a>Ativar ou desativar notificações do Teams para usuários individuais

Após habilitar notificações para o aplicativo Dynamics 365 Human Resources no Teams, você poderá ativar ou desativar notificações para usuários individuais.

1. No Human Resources, selecione **Administração do sistema**.

2. Selecione **Links**.

3. Em **Usuários**, selecione **Opções do usuário** .

4. Selecione a guia **Fluxo de trabalho**.

5. Defina **Habilitar notificações para o aplicativo Teams** como **Sim** para habilitar notificações para o usuário ou como **Não** para desabilitar notificações para o usuário.

   ![Habilitar notificações do aplicativo Teams na guia Fluxo de trabalho de opções do usuário.](./media/hr-admin-teams-leave-app-notifications.png)

6. Selecione **Salvar**.

## <a name="supported-languages"></a>Idiomas com suporte

O aplicativo Dynamics 365 Human Resources no Teams oferece suporte aos seguintes idiomas:

| ID da localidade | Idioma |
| --- | --- |
| de-DE | Alemão (Alemanha) |
| es-ES | Espanhol (Espanha) |
| es-MX | Espanhol (México) |
| fr-CA | Francês (Canadá) |
| fr-FR | Francês (França) |
| it-IT | Italiano (Itália) |
| nl-NL | Holandês (Países Baixos) |
| pt-BR | Português (Brasil) |
| tr-TR | Turco (Turquia) |
| zh-CN | Chinês (simplificado) |

## <a name="notes"></a>Notas

Os seguintes itens de trabalho foram lançados para versões futuras:

| Item de trabalho | Status |
| --- | --- |
| O saldo exibido ao enviar folga para uma data futura está incorreto. | A previsão ainda não está disponível. O saldo é exibido para a data atual. |
| Não é possível cancelar uma solicitação **Em revisão**. | Atualmente, essa funcionalidade não tem suporte e será adicionada em uma versão futura. |
| As informações de saldo são calculadas a partir de hoje. | No momento, o sistema não mostra os saldos a partir do período de acúmulo, mesmo se estiver configurado na página **Parâmetros de licença e ausência**. |

## <a name="troubleshooting"></a>Solução de problemas

Se um usuário tiver problemas para entrar ou ao usar o aplicativo do Human Resources no Teams, tente seguir estas instruções de solução de problemas. Se você ainda tiver problemas após a solução de problemas, contate o Suporte. Para obter mais informações, consulte [Obter suporte](../fin-ops-core/dev-itpro/lifecycle-services/lcs-support.md).

### <a name="ensure-the-teams-human-resources-application-is-up-to-date"></a>Verifique se o aplicativo Human Resources no Teams está atualizado
Se você encontrar problemas com o aplicativo Human Resources no Teams, precisará confirmar que está executando a versão mais recente. A versão mínima compatível é 1.1.5. Para obter instruções sobre como atualizar um aplicativo do Teams, consulte a [documentação do Teams](/MicrosoftTeams/apps-update-experience).

### <a name="cant-sign-into-the-human-resources-app-in-teams"></a>Não é possível entrar no aplicativo do Human Resources no Teams

Se um usuário entrar em contato com você porque não consegue entrar no aplicativo, verifique se ele tem um registro de funcionário associado no Human Resources.

### <a name="error-when-approving-leave-requests-in-the-human-resources-app-in-teams"></a>Erro ao aprovar solicitações de licença no aplicativo do Human Resources no Teams

Se um usuário receber um erro ao tentar aprovar solicitações de licença no aplicativo do Teams, experimente as seguintes etapas de solução de problemas:

1. Verifique se a sua conta do Teams é a mesma usada para acessar o Human Resources.

2. Verifique se ele é um aprovador válido para a solicitação ao verificar as configurações do fluxo de trabalho para a aprovação de licenças. Para obter mais informações sobre fluxos de trabalho de solicitações de licença, consulte [Criar um fluxo de trabalho de solicitações de licença](hr-leave-and-absence-workflow.md).

### <a name="leave-approvers-dont-receive-teams-chat-messages-to-approve-leave-requests"></a>Aprovadores de licenças não recebem mensagens de chat do Teams para aprovar solicitações de licença

1. Verifique se as notificações estão habilitadas para o ambiente e o usuário. Para obter mais informações, consulte [Habilitar notificações para o aplicativo Human Resources](hr-admin-teams-leave-app.md#enable-notifications-for-the-human-resources-app-in-teams) no Teams e [Ativar ou desativar notificações do Teams para usuários individuais](hr-admin-teams-leave-app.md#turn-teams-notifications-on-or-off-for-individual-users).

2. Verifique se os usuários estão conectados na guia **Chats** com as mesmas credenciais usadas para aprovar solicitações de licença. Use as mensagens "sair" e "entrar" para conectar-se com as credenciais corretas.

3. Se o problema persistir, verifique o status do trabalho em lote **Sistema de Eventos Comerciais** como um administrador do sistema. Se estiver em um estágio **Aguardando** ou **Executando**, verifique novamente em alguns minutos. Se o status permanecer inalterado, registre um tíquete de suporte para que nossa equipe possa ajudar a corrigir o problema.

## <a name="privacy-notice"></a>Aviso de privacidade

### <a name="microsoft-language-understanding-intelligent-service-luis"></a>Serviço Inteligente de Reconhecimento Vocal (LUIS) da Microsoft

Com o bot do Dynamics 365 Human Resources no Microsoft Teams, as entradas de texto do usuário são analisadas para compreender a consulta/intenção subjacente. A entrada do usuário, como "Pesquisar conta Contoso", é encaminhada para um Serviço Cognitivo da Microsoft chamado LUIS (Serviço Inteligente de Reconhecimento Vocal). Leia mais sobre o LUIS  [aqui](https://www.luis.ai/). O serviço LUIS exclui a ambiguidade ou compreende a intenção da entrada do usuário (nesse caso, a intenção é encontrar informações) e a entidade de destino (nesse caso, a entidade pretendida é uma conta chamada Contoso). Em seguida, essas informações são passadas para o [Azure Bot Framework](https://azure.microsoft.com/services/bot-service/) da Microsoft, que interage com os dados do Dynamics 365 Human Resources e recupera as informações desejadas para a consulta do usuário.

Ao instalar e permitir o acesso ao uso do bot, você permite que o serviço LUIS e a estrutura de bot do Azure processem a intenção por trás da entrada, o que resulta em uma experiência aprimorada de conversa do usuário. O serviço LUIS e a estrutura de bot do Azure têm vários níveis de conformidade em comparação com o Dynamics 365 Human Resources. Embora o serviço LUIS tenha acesso a somente às consultas do usuário e não tenha sido desenvolvido para se conectar aos dados ou à conta do usuário do Dynamics 365 Human Resources, um usuário do bot do Dynamics 365 Human Resources poderia voluntariamente inserir uma consulta contendo Dados do Cliente, Dados Pessoais ou outros dados, e esse conteúdo da consulta poderia ser enviado para o serviço LUIS e para o Azure Bot Framework. 

O conteúdo das consultas e das mensagens do usuário é mantido no sistema do LUIS por até 30 dias, criptografado em repouso e não é usado para treinamento ou melhoria de serviço. Leia mais sobre o Cognitive Services [aqui](https://azure.microsoft.com/services/cognitive-services/language-understanding-intelligent-service/). 

Para gerenciar as configurações de administração de aplicativos no Microsoft Teams, Acesse o [centro de administração do Microsoft Teams](https://admin.teams.microsoft.com/).

### <a name="microsoft-teams-azure-event-grid-and-azure-cosmos-db"></a>Microsoft Teams, Azure Event Grid e Azure Cosmos DB

Ao usar o aplicativo Dynamics 365 Human Resources no Microsoft Teams, determinados dados do cliente podem fluir fora da região geográfica em que o serviço de Human Resources do locatário é implantado.

O Dynamics 365 Human Resources transmite detalhes da solicitação de licença e da tarefa de fluxo de trabalho do funcionário para a Grade de Eventos do Microsoft Azure e o Microsoft Teams . Esses dados podem ser armazenados na Grade de Eventos do Microsoft Azure por até 24 horas e podem ser processados nos Estados Unidos, são criptografados em trânsito e em repouso, e não são usados pela Microsoft ou subprocessadores para treinamento ou melhorias de serviço. Para entender onde seus dados são armazenados no Teams, consulte: [Localização dos dados no Microsoft Teams](/microsoftteams/location-of-data-in-teams?preserve-view=true&view=o365-worldwide).

Ao conversar com o bot de bate-papo no aplicativo Human Resources, o conteúdo da conversa pode ser armazenado no Azure Cosmos DB e transmitido ao Microsoft Teams. Esses dados podem ser armazenados no Azure Cosmos DB por até 24 horas e podem ser processados fora da região geográfica onde o serviço do Human Resources do seu locatário está implantado, é criptografado em trânsito e em repouso e não é usado pela Microsoft ou seus subprocessadores para treinamento ou melhorias de serviço. Para entender onde seus dados são armazenados no Teams, consulte: [Localização dos dados no Microsoft Teams](/microsoftteams/location-of-data-in-teams?preserve-view=true&view=o365-worldwide).
 
Para restringir o acesso ao aplicativo Human Resources no Microsoft Teams para sua organização ou usuários dentro de sua organização, consulte [Gerenciar políticas de permissão de aplicativo no Microsoft Teams](/MicrosoftTeams/teams-app-permission-policies).

## <a name="see-also"></a>Consulte também 

[Baixar e instalar o Microsoft Teams](https://support.office.com/article/download-and-install-microsoft-teams-422bf3aa-9ae8-46f1-83a2-e65720e1a34d)</br>
[Central de ajuda do Microsoft Teams](https://support.office.com/teams)</br>
[Gerenciar solicitações de licença no Teams](hr-teams-leave-app.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
