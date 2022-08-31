---
title: Módulo Chat do Commerce com Omnicanal para Customer Service
description: Este artigo descreve o módulo Chat do Commerce com Omnicanal para Customer Service no Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
ms.date: 08/23/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2022-07-20
ms.openlocfilehash: e4a004b929138f0a04c19d6a94278cfad6e83303
ms.sourcegitcommit: 1dbff0b5fa1f4722a1720fac35cce94606fa4320
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/24/2022
ms.locfileid: "9346375"
---
# <a name="commerce-chat-with-omnichannel-for-customer-service-module"></a>Módulo Chat do Commerce com Omnicanal para Customer Service

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

Este artigo descreve o módulo *Chat do Commerce com Omnicanal para Customer Service* no Microsoft Dynamics 365 Commerce.

No Commerce versão 10.0.29, um novo módulo de Chat do Commerce com Omnicanal para Customer Service foi adicionado à biblioteca de módulos do Commerce. O recurso de chat do Commerce fornece aos clientes de comércio eletrônico os recursos de chat do Omnicanal para Customer Service do Dynamics 365, que inclui suporte ao cliente via chat ao vivo para ajudar a tirar dúvidas de clientes, fornecer atendimento ao cliente e facilitar vendas para clientes do Commerce.

O recurso de chat do Commerce permite que os varejistas atinjam estas metas:

- Aumente a participação personalizada com clientes para ajudar a melhorar a retenção de clientes.
- Melhore o atendimento ao cliente por meio da integração do agente humano e de chatbots de autoatendimento.
- Ajude agentes a obter experiência por meio de perfis de clientes, ordens e dados de compra em tempo real que promovam melhorias operacionais e maior participação.
- Aumente a satisfação geral do cliente para ajudar a aumentar as vendas.

Os seguintes recursos estão disponíveis como parte do recurso de chat do Commerce:

- Módulo Chat do Commerce com Omnicanal para Customer Service
- A inclusão de **Call Center do Commerce** como uma guia de aplicativo na experiência do agente no Omnicanal para Customer Service do Dynamics 365

## <a name="prerequisites-for-omnichannel-for-customer-service"></a>Pré-requisitos do Omnicanal para Customer Service

Como pré-requisito, você deve configurar o chat no widget de administração do Omnicanal para Customer Service e obter alguns dos parâmetros para configurar a experiência de chat do Commerce. Para obter instruções, consulte [Configurar um canal de chat](/dynamics365/customer-service/set-up-chat-widget).

Depois de configurar o chat no widget de administração do Omnicanal para Customer Service, você receberá um script semelhante ao exemplo a seguir.

`<script id="Microsoft_Omnichannel_LCWidget" src="https://oc-cdn-ocprod.azureedge.net/livechatwidget/scripts/LiveChatBootstrapper.js" data-app-id="xxxx-xxx-4be7-bcd5-1d118ecffe1f" data-org-id="5a0e73c0-xxxx-xxxxx-xxx- 76df135f375d" data-org-url="https://xxsxxxxssdb348f-crm.omnichannelengagementhub.com"></script>`

Copie esse script, pois você precisará dos valores dele para configurar o módulo de chat.

### <a name="commerce-chat-with-omnichannel-for-customer-service-mandatory-fields"></a>Campos obrigatórios do Chat do Commerce com Omnicanal para Customer Service

A tabela a seguir mostra os valores de script do widget Omnicanal para Customer Service que são necessários para configurar o módulo Chat do Commerce com Omnicanal para Customer Service.

| Propriedade widget | Descrição |
| ------------- |--------------|
| Origem do script | O valor de **src** no script do widget de chat. |
| ID do aplicativo de dados | O valor de **data-app-id** no script do widget de chat. |
| ID da organização de dados | O valor de **data-org-id** no script do widget de chat. |
| URL da organização de dados | O valor de **data-org-url** no script do widget de chat. |

## <a name="configure-the-commerce-chat-experience-for-your-e-commerce-site"></a>Configurar a experiência de chat do Commerce para seu site de comércio eletrônico

Uma maneira recomendada de implementar a experiência de chat para o seu site de comércio eletrônico é adicionar o módulo Chat do Commerce com Omnicanal para Customer Service ao fragmento de cabeçalho compartilhado usado nas páginas do site de comércio eletrônico.

Para adicionar o módulo de chat ao fragmento do cabeçalho do seu site no construtor de sites do Commerce, siga estas etapas.

1. No construtor de sites do seu site, acesse **Fragmentos**.
1. Selecione **Novo**.
1. Na caixa de diálogo **Selecionar um fragmento**, selecione o módulo **Chat do Commerce com Omnicanal para Customer Service**, insira um nome para o fragmento e, depois, selecione **OK**.
1. No modo de estrutura de tópicos, selecione o slot **Msdyn365 cs chat connector**.
1. No painel **Propriedades do chat** à direita, siga estas etapas:

    1. No campo **Origem do script**, insira o valor **src** obtido do script Omnicanal para Customer Service.
    1. No campo **ID do aplicativo de dados**, insira o valor **data-app-id** obtido do script Omnicanal para Customer Service.
    1. No campo **ID da organização de dados**, insira o valor **data-org-id** obtido do script Omnicanal para Customer Service.
    1. No campo **URL da organização de dados**, insira o valor **data-org-url** obtido do script Omnicanal para Customer Service.

    ![Criar um fragmento de módulo de Chat do Commerce no construtor de sites do Commerce.](media/Commerce-chat-creating-new-fragment.png)

1. Selecione **Salvar**, **Concluir edição** para fazer check-in do fragmento e depois selecione **Publicar** para publicá-lo.
1. Vá para **Fragmentos** e abra o fragmento de cabeçalho do site.
1. No slot **Contêiner padrão**, selecione as reticências (**...**) e, depois, **Adicionar fragmento**.
1. Na caixa de diálogo **Selecionar módulos**, selecione o fragmento de chat criado anteriormente e, depois, selecione **OK**.
1. Selecione **Salvar**, **Concluir edição** para fazer check-in do fragmento e depois selecione **Publicar** para publicá-lo.

## <a name="add-commerce-headquarters-as-an-application-tab-for-omnichannel-for-customer-service"></a>Adicionar o Commerce headquarters como uma guia de aplicativo para Omnicanal para Customer Service

Você pode adicionar a guia de aplicativo para o Commerce headquarters no Omnicanal para Customer Service. Os agentes humanos podem usar a interface de usuário da experiência de agente do Omnicanal para Customer Service para acessar facilmente o módulo de atendimento ao cliente do Dynamics 365 Commerce que contém informações contextuais para o cliente junto com informações de ordens de venda. Além disso, os agentes do atendimento ao cliente podem fazer novas ordens, iniciar devoluções e verificar informações de status da ordem.

### <a name="create-a-new-application-tab-that-loads-commerce-headquarters-in-an-iframe-module"></a>Criar uma nova guia do aplicativo que carrega o Commerce headquarters em um módulo do iFrame 

Para criar uma nova guia do aplicativo que carrega o Commerce headquarters em um módulo do iFrame, siga estas etapas.

1. Abra o [Power Apps Maker Portal](https://make.powerapps.com).
1. No painel de navegação à esquerda, selecione **Aplicativos**.
1. Selecione **Centro de administração do Customer Service**.
1. Vá para **Experiência do agente**.
1. Para **Modelos da guia do aplicativo**, selecione **Gerenciar**.
1. Crie uma nova guia do aplicativo do tipo **Site de terceiros**. Para obter instruções, consulte [Gerenciar modelos da guia do aplicativo](/dynamics365/app-profile-manager/application-tab-templates?tabs=customerserviceadmincenter).
1. Em **Parâmetros**, no campo **Valor** do parâmetro **url**, insira a URL a seguir, em que `<YourOrganizationHeadquartersURL>` e `<LegalEntityname>` são substituídos pelos valores apropriados. O Omnicanal para Customer Service lê **{AccountNumber}** do contexto do chat. Portanto, deixe **{AccountNumber}** como está.

    `https://<YourOrganizationHeadquartersURL>/?mi=MCRCustomerService&cmp=<LegalEntityName>&embedded=true&customerId={AccountNumber}`

1. Deixe o campo **Valor** do parâmetro **data** em branco.

![Crie uma guia do aplicativo no Omnicanal para Customer Service do Dynamics 365.](media/OC-CS-Admin-Application-Tab-Parameters.png)

## <a name="enable-a-new-application-tab-for-customer-agents-in-dynamics-365-omnichannel-for-customer-service"></a>Habilitar uma nova guia do aplicativo para agentes de cliente no Omnicanal para Customer Service do Dynamics 365

Para habilitar uma nova guia do aplicativo para agentes de cliente no Omnicanal para Customer Service do Dynamics 365, siga estas etapas.
    
1. Abra o [Power Apps Maker Portal](https://make.powerapps.com).
1. No painel de navegação à esquerda, selecione **Aplicativos**.
1. Selecione **Centro de administração do Customer Service**.
1. Vá para **Atendimento ao cliente \> Fluxos de trabalho**.
1. Abra o fluxo de trabalho que você criou para seus agentes e, depois, em **Configurações avançadas**, selecione **Sessões padrão**.
1. Em **Guias do Aplicativo**, selecione **Adicionar Guia do Aplicativo Existente** e, depois, adicione a nova guia de aplicativo criada anteriormente. Esta etapa garante que uma guia do aplicativo que carrega o Commerce headquarters em um módulo do iFrame será exibida quando um agente receber uma chamada de chat de entrada do site de comércio eletrônico.

## <a name="add-context-variables-in-dynamics-365-omnichannel-for-customer-service"></a>Adicionar variáveis de contexto no Omnicanal para Customer Service do Dynamics 365

Para adicionar variáveis de contexto no Omnicanal para Customer Service do Dynamics 365, siga estas etapas.

1. Abra o [Power Apps Maker Portal](https://make.powerapps.com).
1. No painel de navegação à esquerda, selecione **Aplicativos**.
1. Selecione **Centro de administração do Customer Service**.
1. Vá para **Atendimento ao cliente \> Fluxos de trabalho**.
1. Abra o fluxo de trabalho que você criou para seus agentes e, depois, em **Configurações avançadas**, vá para a sessão **Variável de contexto**.
1. Selecione **Editar** e, depois, adicione **AccountNumber** como uma variável de contexto do tipo **texto**. Essa variável ajudará o Commerce headquarters a carregar informações do cliente com números de conta correspondentes.

> [!NOTE]
> Se desejar ler os endereços de email e nomes de usuários conectados de um canal de comércio eletrônico, você poderá adicionar **Email** e **Nome** como variáveis de contexto do tipo **texto**, além da variável de contexto **AccountNumber**.
