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
# <a name="manage-leave-requests-in-teams"></a>Gerenciar solicitações de licença no Teams

[!include [banner](includes/preview-feature.md)]

O aplicativo Microsoft Dynamics 365 Human Resources no Microsoft Teams permite solicitar folgas rapidamente, além de visualizar as informações de saldo de folgas no Microsoft Teams. Você pode interagir com um bot para solicitar informações. A guia **Folga** fornece informações mais detalhadas.

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

> [!WARNING]
> Atualmente o aplicativo não oferece suporte à função de segurança do Administrador do Sistema e exibirá uma mensagem de erro caso você entre com uma conta de Administrador do Sistema. Para entrar com uma conta diferente, na guia **Configurações**, selecione o botão **Alternar contas** e entre com uma conta de usuário sem os privilégios de Administrador do Sistema.
 
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
 
Depois de iniciar uma solicitação de licença, você pode ajustar os dias no próprio cartão, ou selecionar **Editar detalhes** para incluir informações adicionais à sua solicitação.

![Editar solicitação no aplicativo de licença do Human Resources Teams](./media/hr-teams-leave-app-bot-edit.png)
 
Após inserir as informações, digite **Enviar** para enviá-la para aprovação. Você também pode digitar **Salvar como rascunho** para continuar depois.

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
   
## <a name="privacy-notice"></a>Aviso de privacidade

Com o bot do Dynamics 365 Human Resources no Microsoft Teams, as entradas de texto do usuário são analisadas para compreender a consulta/intenção subjacente. A entrada do usuário, como "Pesquisar conta Contoso", é encaminhada para um dos Cognitive Services da Microsoft, chamado de Serviço Inteligente de Reconhecimento Vocal (LUIS). Leia mais sobre o LUIS  [aqui](https://www.luis.ai/). O serviço LUIS exclui a ambiguidade ou compreende a intenção da entrada do usuário (nesse caso, a intenção é encontrar informações) e a entidade de destino (nesse caso, a entidade pretendida é uma conta chamada Contoso). Em seguida, essas informações são passadas para a [estrutura de bot do Azure](https://azure.microsoft.com/services/bot-service/) da Microsoft, que interage com os dados do Dynamics 365 Human Resources e recupera as informações desejadas para a consulta do usuário. 

Ao instalar e permitir o acesso ao uso do bot, você permite que o serviço LUIS e a estrutura de bot do Azure processem a intenção por trás da entrada, o que resulta em uma experiência aprimorada de conversa do usuário. O serviço LUIS e a estrutura de bot do Azure têm vários níveis de conformidade em comparação com o Dynamics 365 Human Resources. Embora o serviço LUIS tenha acesso a somente às consultas do usuário e não tenha sido desenvolvido para se conectar aos dados ou à conta do usuário do Dynamics 365 Human Resources, um usuário do bot do Dynamics 365 Human Resources poderia voluntariamente inserir uma consulta contendo Dados do Cliente, Dados Pessoais ou outros dados, e esse conteúdo da consulta poderia ser enviado para o serviço LUIS e para a estrutura de bot do Azure. 

O conteúdo das consultas e das mensagens do usuário é mantido no sistema do LUIS por até 30 dias, criptografado em repouso e não é usado para treinamento ou melhoria de serviço. Leia mais sobre o Cognitive Services [aqui](https://azure.microsoft.com/services/cognitive-services/language-understanding-intelligent-service/). 

Para gerenciar as configurações de administração de aplicativos no Microsoft Teams, vá para o [centro de administração do Microsoft Teams](https://admin.teams.microsoft.com/). 

## <a name="see-also"></a>Consulte também

[Baixar e instalar o Microsoft Teams](https://support.office.com/article/download-and-install-microsoft-teams-422bf3aa-9ae8-46f1-83a2-e65720e1a34d)</br>
[Central de ajuda do Microsoft Teams](https://support.office.com/teams)</br>
[Aplicativo Human Resources no Teams](hr-admin-teams-leave-app.md)
