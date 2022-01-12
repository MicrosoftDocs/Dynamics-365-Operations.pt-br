---
title: Gerenciar solicitações de licença no Teams
description: Este tópico mostra como solicitar licenças no aplicativo do Dynamics 365 Human Resources no Microsoft Teams.
author: twheeloc
ms.date: 12/15/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LeaveAbsenceWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-05-18
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: d004e33d01dbd171626d7e23f93df081bc0210a9
ms.sourcegitcommit: 70ac76be31bab7ed5e93f92f4683e65031fbdf85
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/16/2021
ms.locfileid: "7924738"
---
# <a name="manage-leave-requests-in-teams"></a>Gerenciar solicitações de licença no Teams

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

O aplicativo Dynamics 365 Human Resources no Microsoft Teams permite solicitar folgas rapidamente e exibir informações de saldo de folgas no Microsoft Teams. Você pode interagir com um bot para solicitar informações e iniciar uma solicitação de licença. A guia **Folga** fornece informações mais detalhadas. Você também pode enviar às pessoas informações sobre as próximas folgas no Teams e chats fora do aplicativo Human Resources.

## <a name="install-the-app"></a>Instalar o aplicativo

Você pode encontrar o aplicativo Dynamics 365 Human Resources na loja do Teams.

1. No Microsoft Teams, navegue até a lista de aplicativos.
 
2. Procure Dynamics 365 Human Resources, e selecione o título **Human Resources**.

> [!NOTE]
> A partir de 20 de dezembro de 2021, os serviços de bot do aplicativo Human Resources (versão 1.1.4) hospedados no locatário da Microsoft serão desativados. A extensão mais atualizada (versão 1.1.5) está disponível para instalação. Para obter mais informações, consulte [Gerenciar solicitações de licença no Teams](hr-admin-teams-leave-app.md#update-app).

3. Selecione o botão **Adicionar** para instalar o aplicativo.

Se o aplicativo não fizer logon automaticamente, selecione a guia **Configurações** para entrar.

> [!NOTE]
> Caso você não veja uma caixa de diálogo de entrada, atualize as configurações do navegador para permitir janelas pop-up. 

Se você tiver acesso a mais de uma instância do Human Resources, poderá selecionar a qual ambiente deseja se conectar na guia **Configurações**.

> [!NOTE]
> O aplicativo agora oferece suporte à função de segurança Administrador do sistema.
 
## <a name="use-the-bot"></a>Usar o bot

Depois de instalar o aplicativo, será exibida uma mensagem de boas-vindas, informando os tipos de ações que o bot pode assumir em seu nome.

> [!NOTE]
> Talvez você precise entrar na primeira interação com o bot. Caso você não veja uma caixa de diálogo de entrada, atualize as configurações do navegador para permitir janelas pop-up.

Você pode pedir para o bot:

- Exiba os saldos de licenças atuais. Por exemplo, envie uma mensagem que diga, "Exibir os saldos da licença".

- Iniciar uma solicitação de licença para você. Por exemplo, envie uma mensagem informando que "Tirar folga" ou "Eu quero tirar férias na próxima quinta e sexta-feira" para ser mais específico para solicitar licença para o tipo de licença de férias. 

  ![Iniciar uma solicitação de licença no chat do Teams.](./media/hr-teams-leave-app-initiate.png)

- O bot do chat preencherá uma solicitação de licença. Selecione **Solicitar folga** e edite os detalhes para sua solicitação.

   Se você deseja enviar solicitações de licença para vários tipos de licença para a mesma data, selecione a opção **Dividir dia com** no menu **Mais opções**. 

   Se você selecionar uma licença de meio-dia quando a unidade de pedido de licença for em dias, você pode especificar se deseja solicitar uma folga na primeira metade do dia ou na segunda metade do dia selecionando a opção **Definição de meio dia** do menu **Mais opções**.
   
   ![Definições de meio dia.](./media/HalfDayDefinitions.png)

- Ao terminar de editar detalhes da solicitação de licença, selecione **Enviar** para enviá-la para aprovação.

  ![Enviar solicitação de licença.](./media/hr-teams-leave-app-submit.png)

## <a name="manage-your-leave-in-teams"></a>Gerenciar a sua licença no Teams

A guia **Folga** permite exibir: 

- Informações do saldo para cada tipo de licença na qual você está inscrito

- Solicitações de licença futuras

- Solicitações de folga

- Rascunho de solicitações de licença
 
### <a name="create-a-new-request"></a>Criar uma solicitação

1. Para criar uma solicitação de licença, selecione **Nova solicitação**.

2. Insira os dias que você deseja solicitar folga e depois selecione **Adicionar**.

   ![Adicionar folga no aplicativo de licença do Human Resources Teams.](./media/TimeOffHours.png)

3. Se aplicável, insira um código de motivo. Insira também comentários e adicione anexos.

4. Selecione a opção **Dividir dia com** do menu **Mais opções** se quiser enviar várias entradas de solicitação de licença para a mesma data para diferentes tipos de licença.

5. Selecione a opção **Definição de meio dia** para especificar se deseja solicitar a primeira metade do dia ou a segunda metade do dia. Esta opção está disponível quando a unidade de solicitação de licença é em dias e o valor solicitado é de 0,5 dias.

6. Após inserir as informações, digite **Enviar** para enviá-las para aprovação. Você também pode digitar **Salvar como rascunho** para continuar depois.

### <a name="manage-draft-requests"></a>Gerenciar solicitações em rascunho

1. Selecione a guia **Rascunhos**.

2. Selecione o lápis para editar a solicitação, ou selecione a lixeira para excluí-la.

3. Faça todas as alterações necessárias. Após inserir as informações, digite **Enviar** para enviá-la para aprovação. Você também pode selecionar **Salvar como rascunho** para continuar depois.
   
### <a name="respond-to-teams-notifications"></a>Responder a notificações do Teams

Quando você ou um trabalhador para o qual você é um aprovador enviar uma solicitação de licença, você receberá uma notificação no aplicativo Human Resources no Teams. Você pode selecionar a notificação para exibir a solicitação de licença. As notificações também aparecem na área **Chat** .

Se você for aprovador, poderá selecionar **Aprovar** ou **Negar** na notificação. Você também pode fornecer uma mensagem opcional.

## <a name="send-upcoming-time-off-information-to-your-coworkers"></a>Enviar informações sobre as próximas folgas para seus colegas de trabalho

Depois de instalar o aplicativo Human Resources para o Teams, você pode enviar facilmente informações sobre sua próxima folga para seus colegas de trabalho em equipes ou bate-papos.

1. Em uma equipe ou chat no Teams, selecione o botão do Human Resources abaixo da janela de chat.

   ![Botão do Human Resources abaixo da janela de bate-papo.](./media/hr-teams-leave-app-chat-button.png)

2. Selecione a solicitação de licença que deseja compartilhar. Se você deseja compartilhar um rascunho de solicitação de licença, selecione **Rascunhos** primeiro.

Sua solicitação de licença será exibida no chat.

Se você compartilhou uma solicitação de rascunho, ela será exibida como rascunho.

## <a name="view-your-teams-leave-calendar"></a>Exibir o calendário de licença da equipe

Se você for um gerente com subordinados diretos, poderá exibir folgas aprovadas e pendentes da sua equipe.

1. No aplicativo Human Resources no Teams, selecione **Folga** .

2. Selecione **Calendário da equipe** . O calendário exibe as folgas aprovadas e pendentes dos subordinados diretos.

   > [!NOTE]
   > Se você não conseguir ver o calendário da equipe, peça ao administrador para habilitá-lo. Para obter mais informações, consulte [Instalar e configurar](hr-admin-teams-leave-app.md#install-and-setup).

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

## <a name="troubleshooting"></a>Solução de problemas

Se você tiver problemas para entrar ou usar o aplicativo do Dynamics 365 Human Resources no Teams, tente seguir estas instruções de solução de problemas. Se você ainda tiver problemas após a solução de problemas, contate o Suporte. Para obter mais informações, consulte [Obter suporte](../fin-ops-core/dev-itpro/lifecycle-services/lcs-support.md).

### <a name="cant-sign-into-the-human-resources-app-in-teams"></a>Não é possível entrar no aplicativo do Human Resources no Teams

Se não conseguir entrar no aplicativo, é possível que a conta que você esteja usando para entrar no Microsoft Teams não esteja associada a um registro de funcionário no Dynamics 365 Human Resources. Entre em contato com o administrador do sistema para verificar se o registro de funcionário está associado corretamente.

### <a name="cant-find-the-dynamics-365-human-resources-environment-in-settings"></a>Não é possível encontrar o ambiente do Dynamics 365 Human Resources nas configurações

Se você não conseguir selecionar o ambiente correto do Dynamics 365, é possível que o registro do usuário não tenha sido sincronizado corretamente. Entre em contato com o administrador do sistema para recriar o registro de usuário e associá-lo às credenciais do usuário. Tente entrar no aplicativo Human Resources pelo Microsoft Teams em alguns minutos.

### <a name="translations-dont-display-correctly"></a>As traduções não são exibidas corretamente

Se as traduções não forem exibidas conforme o esperado, verifique se o idioma selecionado no Teams corresponde ao idioma selecionado em **Usar opções** no Human Resources.

No Teams, verifique **Idioma do aplicativo** em **Configurações**.

![Configurações do Teams.](./media/hr-teams-leave-app-settings.png)

No Human Resources, selecione **Configurações** e, depois, **Opções de usuário**. Verifique se o campo **Idioma** corresponde ao campo **Idioma do aplicativo** no Teams.

![Opções de usuário no Human Resources.](./media/hr-teams-leave-app-user-options.png)

Se ainda houver problemas de tradução, avise-nos. Para obter informações, consulte [Obter suporte para aplicativos do Finance and Operations ou Lifecycle Services (LCS)](../fin-ops-core/dev-itpro/lifecycle-services/lcs-support.md?toc=%2fdynamics365%2fhuman-resources%2ftoc.json).

### <a name="error-when-approving-leave-requests-in-the-human-resources-app-in-teams"></a>Erro ao aprovar solicitações de licença no aplicativo do Human Resources no Teams

Se você receber um erro ao tentar aprovar solicitações de licença no aplicativo do Teams, siga estas etapas de solução de problemas:

1. Verifique se a conta que você está usando para entrar no Microsoft Teams é a mesma que usa para acessar o Dynamics 365 Human Resources.

2. Verifique se você é um aprovador válido para a solicitação ao verificar as configurações do fluxo de trabalho para a aprovação de licenças. Para obter mais informações sobre fluxos de trabalho de solicitações de licença, consulte [Criar um fluxo de trabalho de solicitações de licença](hr-leave-and-absence-workflow.md).

### <a name="leave-approvers-dont-receive-teams-chat-messages-to-approve-leave-requests"></a>Aprovadores de licenças não recebem mensagens de chat do Teams para aprovar solicitações de licença

1. Verifique se as notificações estão habilitadas para o ambiente e o usuário. Para obter mais informações, consulte [Habilitar notificações para o aplicativo Human Resources](hr-admin-teams-leave-app.md#enable-notifications-for-the-human-resources-app-in-teams) no Teams e [Ativar ou desativar notificações do Teams para usuários individuais](hr-admin-teams-leave-app.md#turn-teams-notifications-on-or-off-for-individual-users).

2. Verifique se os usuários estão conectados na guia **Chats** com as mesmas credenciais usadas para aprovar solicitações de licença. Use as mensagens "sair" e "entrar" para conectar-se com as credenciais corretas.

3. Se o problema persistir, verifique o status do trabalho em lote **Sistema de Eventos Comerciais** como um administrador do sistema. Se estiver em um estágio **Aguardando** ou **Executando**, verifique novamente em alguns minutos. Se o status permanecer inalterado, registre um tíquete de suporte para que nossa equipe possa ajudar a corrigir o problema.

## <a name="known-accessibility-issues"></a>Problemas de acessibilidade conhecidos

O aplicativo Human Resources no Teams tem as questões de acessibilidade a seguir que estamos trabalhando para corrigir em versões futuras.

| Problema | Solução ou explicação |
| --- | --- |
| O zoom para 400% da área de trabalho oculta alguns dos botões de ação da exibição. | É recomendável usar uma lupa até que possamos dar suporte a esse nível de zoom. |
| Na guia **Folga**, o VoiceOver anuncia uma ação de botão enquanto lê o cabeçalho para a grade de folgas. | O cabeçalho e os elementos na grade são agrupados por ano e são recolhíveis. O VoiceOver interpreta essa apresentação como um item acionável, mas ela não é. |
| Na guia **Folga**, há um gesto de passar o dedo adicional ao navegar até o **Código de motivo** em uma nova solicitação. | Não há controle oculto para que a navegação de deslizar o dedo esteja tentando acessar. |
| Na guia **Folga**, se você passar o dedo enquanto o calendário estiver aberto, terminará fora de controle, e não na parte superior em uma nova solicitação ou ao editar uma solicitação. | Quando você atingir **Acessar hoje**, considere isso como o final do controle e o deslize o dedo na direção inversa para voltar ao início. |
| Na guia **Chat**, o foco recai sobre a parte superior quando você insere uma data usando a ferramenta de assistência ou a navegação por teclado. | Pressione a tecla Tab até acessar a área de entrada novamente. |

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
[Aplicativo Human Resources no Teams](hr-admin-teams-leave-app.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
