---
title: Chat do Commerce com o módulo do Power Virtual Agents
description: Este artigo descreve o Chat do Commerce com o módulo do Power Virtual Agents que integra o Microsoft Power Virtual Agents aos sites do Dynamics 365 Commerce.
author: gvrmohanreddy
ms.date: 10/18/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2022-09-07
ms.openlocfilehash: 838990cb638479c9c90ba0e38794ecedd55e95b3
ms.sourcegitcommit: 40c80a617b903c2b26e44b41147e0021c5cb680d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/18/2022
ms.locfileid: "9691044"
---
# <a name="commerce-chat-with-power-virtual-agents-module"></a>Chat do Commerce com o módulo do Power Virtual Agents

[!include [banner](includes/banner.md)]

Este artigo descreve o Chat do Commerce com o módulo do Power Virtual Agents que integra o Microsoft Power Virtual Agents aos sites do Dynamics 365 Commerce.

O recurso Chat do Commerce com Power Virtual Agents permite que os clientes de comércio eletrônico do Dynamics 365 usem os recursos do Power Virtual Agents para processar suas consultas. A partir da versão 10.0.30 do Dynamics 365 Commerce, este recurso pode ser incorporado a sites de comércio eletrônico usando o Chat do Commerce com o módulo do Power Virtual Agents que faz parte da biblioteca de módulos do Commerce.

O recurso Chat do Commerce com Power Virtual Agents ajuda as empresas a atingirem os seguintes objetivos:

- Aumentar a participação personalizada com seus clientes e melhorar a retenção.
- Melhorar o atendimento ao cliente por meio de integração de chatbots de autoatendimento.
- Aumentar a satisfação geral do cliente e, portanto, aumentar as vendas.

> [!NOTE]
> Para saber mais sobre as diferenças entre os aplicativos Dynamics 365 Omnichannel for Customer Service e Power Virtual Agents, consulte [Visão geral dos módulos de chat do Commerce](/commerce-chat-modules-overview.md).

## <a name="prerequisites-for-using-power-virtual-agents"></a><a id="prereq"></a>Pré-requisitos para usar o Power Virtual Agents

Para usar o recurso Chat do Commerce com o Power Virtual Agents, primeiro crie um chatbot do Power Virtual Agents para seu site de comércio eletrônico. Para obter instruções, consulte [Criar um bot do Power Virtual Agent](/power-virtual-agents/authoring-first-bot).

Depois de configurar o chatbot, você deve copiar os valores de **ID de Bot** e **ID do Locatário** para configurar a experiência de bate-papo do Commerce. Para obter informações sobre como copiar esses valores, consulte [Recuperar seus parâmetros de bot do Power Virtual Agents](/power-virtual-agents/publication-connect-bot-to-custom-application#retrieve-your-power-virtual-agents-bot-parameters).

## <a name="configure-your-e-commerce-site"></a>Configure seu site de comércio eletrônico 

Uma maneira recomendada de implementar a experiência de chat para o seu site de comércio eletrônico é adicionar o módulo Chat do Commerce com Power Virtual Agents ao fragmento de cabeçalho compartilhado usado nas páginas do seu site.

Para adicionar o módulo de chat ao fragmento do cabeçalho do seu site no construtor de sites do Commerce, siga estas etapas.

1. No construtor de sites do Commerce, acesse **Fragmentos**.
1. Selecione **Novo**.
1. Na caixa de diálogo **Selecionar um fragmento**, selecione o módulo **Chat do Commerce com Power Virtual Agents**, digite um nome para o fragmento e, em seguida, selecione **OK**.
1. No modo de estrutura de tópicos, selecione o slot **Msdyn365 pva chat connector**.
1. No painel Propriedades do chat à direita, siga estas etapas:

    1. Em **Parâmetros de Bot**, no campo **URL de CDN de Chat do Webchat do Bot Framework**, deixe o valor padrão (por exemplo, `https://cdn.botframework.com/botframework-webchat/latest/webchat.js`).
    1. No campo **URL de Autenticação do Bot Framework Direct Line**, deixe o valor padrão (por exemplo, `https://powerva.microsoft.com/api/botmanagement/v1/directline/directlinetoken`).
    1. No campo **ID do Bot**, digite o valor do **ID do Bot** do Power Virtual Agents que você copiou na seção [Pré-requisitos para usar o Power Virtual Agents](#prereq).
    1. No campo **ID do Locatário**, digite o valor do **ID do Locatário** copiado.

1. Selecione **Salvar**, **Concluir edição** para fazer check-in do fragmento e depois selecione **Publicar** para publicá-lo.
1. Vá para **Fragmentos** e abra o fragmento de cabeçalho do site.
1. No slot **Contêiner padrão**, selecione as reticências (**...**) e, depois, **Adicionar fragmento**.
1. Na caixa de diálogo **Selecionar módulos**, selecione o fragmento de chat criado anteriormente e, depois, selecione **OK**.
1. Selecione **Salvar**, **Concluir edição** para fazer check-in do fragmento e depois selecione **Publicar** para publicá-lo.

## <a name="proactive-chat-parameters"></a>Parâmetros de chat proativos

Para obter uma lista completa dos parâmetros de configuração de chat proativos, consulte [Parâmetros de chat proativos do módulo de chat do Commerce](chat-proactive-chat-parameters.md).

> [!NOTE]
> Atualmente, o Power Virtual Agents não suporta autenticação do Azure Active Directory B2C (Azure AD B2C). Ele oferece suporte somente a chamadas anônimas do Retail Cloud Scale Unit (RCSU) para obter disponibilidade do produto ou interagir com outras APIs anônimas. As chamadas a APIs autenticadas via chatbots do Power Virtual Agents exigem uma entrada de cliente explícita.

## <a name="additional-resources"></a>Recursos adicionais

[Visão geral dos recursos do chat comercial](commerce-chat-overview.md)

[Módulo Chat do Commerce com Omnicanal para Customer Service](commerce-chat-module.md)

[Parâmetros de chat proativo do módulo de chat do Commerce](chat-proactive-chat-parameters.md)
