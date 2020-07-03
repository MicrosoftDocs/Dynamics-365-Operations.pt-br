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
# <a name="human-resources-app-in-teams"></a>Aplicativo Human Resources no Teams

[!include [banner](includes/preview-feature.md)]

O aplicativo Microsoft Dynamics 365 Human Resources no Microsoft Teams permite aos funcionários solicitar folgas rapidamente, além de visualizar suas informações de saldo de folgas no Microsoft Teams. Os funcionários podem interagir com um bot para solicitar informações. A guia **Folga** fornece informações mais detalhadas.

![Bot do aplicativo de licenças do Human Resources Teams](./media/hr-admin-teams-leave-app-bot.png)

![Guia Folga do aplicativo de licença do Human Resources Teams](./media/hr-teams-leave-app-timeoff-tab.png)

## <a name="install-and-setup"></a>Instalação e configuração

Você pode encontrar o aplicativo Human Resources na loja do Teams. Para obter informações sobre como instalar o aplicativo do Teams, consulte [Gerenciar solicitações de licença no Teams](hr-teams-leave-app.md).

Para obter informações sobre como gerenciar permissões de aplicativo no Teams, consulte [Gerenciar políticas de permissão de aplicativo no Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/teams-app-permission-policies).

## <a name="known-issues"></a>Problemas conhecidos

| Problema | Status |
| --- | --- |
| Erro: há um problema ao encontrar um ambiente ao qual se conectar. | Você poderá receber esse erro mesmo que tenha verificado que o usuário pode acessar um ou mais ambientes de recursos humanos. Além disso, talvez você não veja todos os ambientes esperados. Até corrigir esse problema, exclua o usuário e importe-os novamente para resolver o problema. |
| O saldo exibido ao enviar folga para uma data futura está incorreto. | A previsão ainda não está disponível. O saldo é exibido para a data atual. |
| Ao reduzir o número de horas tiradas em uma solicitação existente, o **Saldo restante** diminui em vez de aumentar. | Abordaremos esse problema conhecido no futuro. A exibição está incorreta, mas os valores corretos são ajustados após o envio. |
| Dois cartões de **Próxima folga** são exibidos para as mesmas datas. | Os cartões representam envios individuais. Continuaremos recebendo feedback e fazendo ajustes. |
| Não é possível cancelar uma solicitação **Em revisão**. | Atualmente, essa funcionalidade não tem suporte e será adicionada em uma versão futura. |
| As informações de saldo são calculadas a partir de hoje. | O sistema atualmente não exibe os saldos a partir do período de acúmulo, mesmo se estiver configurado nos parâmetros de Licença e ausência. |

## <a name="privacy-notice"></a>Aviso de privacidade

Com o bot do Dynamics 365 Human Resources no Microsoft Teams, as entradas de texto do usuário são analisadas para compreender a consulta/intenção subjacente. A entrada do usuário, como "Pesquisar conta Contoso", é encaminhada para um dos Cognitive Services da Microsoft, chamado de Serviço Inteligente de Reconhecimento Vocal (LUIS). Leia mais sobre o LUIS  [aqui](https://www.luis.ai/). O serviço LUIS exclui a ambiguidade ou compreende a intenção da entrada do usuário (nesse caso, a intenção é encontrar informações) e a entidade de destino (nesse caso, a entidade pretendida é uma conta chamada Contoso). Em seguida, essas informações são passadas para a [estrutura de bot do Azure](https://azure.microsoft.com/services/bot-service/) da Microsoft, que interage com os dados do Dynamics 365 Human Resources e recupera as informações desejadas para a consulta do usuário. 

Ao instalar e permitir o acesso ao uso do bot, você permite que o serviço LUIS e a estrutura de bot do Azure processem a intenção por trás da entrada, o que resulta em uma experiência aprimorada de conversa do usuário. O serviço LUIS e a estrutura de bot do Azure têm vários níveis de conformidade em comparação com o Dynamics 365 Human Resources. Embora o serviço LUIS tenha acesso a somente às consultas do usuário e não tenha sido desenvolvido para se conectar aos dados ou à conta do usuário do Dynamics 365 Human Resources, um usuário do bot do Dynamics 365 Human Resources poderia voluntariamente inserir uma consulta contendo Dados do Cliente, Dados Pessoais ou outros dados, e esse conteúdo da consulta poderia ser enviado para o serviço LUIS e para a estrutura de bot do Azure. 

O conteúdo das consultas e das mensagens do usuário é mantido no sistema do LUIS por até 30 dias, criptografado em repouso e não é usado para treinamento ou melhoria de serviço. Leia mais sobre o Cognitive Services [aqui](https://azure.microsoft.com/services/cognitive-services/language-understanding-intelligent-service/). 

Para gerenciar as configurações de administração de aplicativos no Microsoft Teams, vá para o [centro de administração do Microsoft Teams](https://admin.teams.microsoft.com/). 

## <a name="see-also"></a>Consulte também 

[Baixar e instalar o Microsoft Teams](https://support.office.com/article/download-and-install-microsoft-teams-422bf3aa-9ae8-46f1-83a2-e65720e1a34d)</br>
[Central de ajuda do Microsoft Teams](https://support.office.com/teams)</br>
[Gerenciar solicitações de licença no Teams](hr-teams-leave-app.md)

