---
title: Adicionar suporte para uma rede de entrega de conteúdo (CDN)
description: Este tópico descreve como adicionar uma rede de entrega de conteúdo (CDN) ao ambiente do Microsoft Dynamics 365 Commerce.
author: brianshook
manager: annbe
ms.date: 07/02/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Operations, Retail, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: febef3bcc06dc1b5868a0decebee33d76110c505
ms.sourcegitcommit: adf196c51e2b6f532d99c177b4c6778cea8a2efc
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/02/2020
ms.locfileid: "3533335"
---
# <a name="add-support-for-a-content-delivery-network-cdn"></a>Adicionar suporte para uma rede de entrega de conteúdo (CDN)


[!include [banner](includes/banner.md)]

Este tópico descreve como adicionar uma rede de entrega de conteúdo (CDN) ao ambiente do Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Visão geral

Ao configurar um ambiente de comércio eletrônico no Dynamics 365 Commerce, você pode configurá-lo para funcionar com o serviço de CDN. 

Seu domínio personalizado pode ser habilitado durante o processo de provisionamento para o seu ambiente de comércio eletrônico. Como alternativa, você pode usar uma solicitação de serviço para configurá-la após a conclusão do processo de provisionamento. O processo de provisionamento para o ambiente de comércio eletrônico gera um nome de host associado ao ambiente. Este nome de host tem o seguinte formato, em que *e-commerce-tenant-name* é o nome do seu ambiente:

&lt;e-commerce-tenant-name&gt;.commerce.dynamics.com

O nome de host ou ponto de extremidade gerado durante o processo de provisionamento é compatível com um certificado SSL (Secure Sockets Layer) apenas para \*.commerce.dynamics.com. Não é compatível com SSL para domínios personalizados. Portanto, é precisa encerrar o SSL para domínios personalizados em sua CDN e encaminhar o tráfego da CDN para o nome de host ou ponto de extremidade que o Commerce gerou. 

Além disso, as *estatísticas* (arquivos JavaScript ou Folhas de Estilos em Cascata \[CSS\]) do Commerce são fornecidas por meio dos pontos de extremidade que o Commerce gerou (\*.commerce.dynamics.com). A estática pode ser armazenada em cache somente se o nome de host ou ponto de extremidade que o Commerce gerou for colocado após a CDN.

## <a name="set-up-ssl"></a>Configurar SSL

Para ajudar a garantir que o SSL esteja configurado e que as estáticas sejam armazenadas em cache, você deve configurar sua CDN para que ela seja associada ao nome de host que o Commerce gerou para o seu ambiente. Você também deve armazenar em cache o seguinte padrão apenas para estática: 

/\_msdyn365/\_scnr/\*

Depois de provisionar o ambiente do Commerce com o domínio personalizado fornecido, ou depois de fornecer o domínio personalizado para o ambiente usando uma solicitação de serviço, aponte o domínio personalizado para o nome de host ou ponto de extremidade que o Commerce gerou.

Como mencionado anteriormente, o nome de host ou ponto de extremidade gerado é compatível com um certificado SSL apenas para \*.commerce.dynamics.com. Não é compatível com SSL para domínios personalizados.

## <a name="cdn-services"></a>Serviços CDN

Qualquer serviço de CDN pode ser usado com um ambiente do Commerce. Aqui estão dois exemplos:

- **Microsoft Azure Front Door Service** – A solução de CDN do Azure. Para obter mais informações sobre o Azure Front Door Service, consulte a [Documentação do Azure Front Door Service](https://docs.microsoft.com/azure/frontdoor/).
- **Dynamic Site Accelerator da Akamai** – Para obter mais informações, consulte [Dynamic Site Accelerator](https://www.akamai.com/us/en/products/performance/dynamic-site-accelerator.jsp).

## <a name="cdn-setup"></a>Configuração de CDN

O processo de instalação da CDN consiste nas etapas gerais a seguir:

1. Adicione um host de front-end.
1. Configure um pool de back-end.
1. Configure regras para roteamento e cache.

### <a name="add-a-front-end-host"></a>Adicionar um host de front-end

Qualquer serviço de CDN pode ser usado, mas, por exemplo, neste tópico, o Azure Front Door Service é usado. 

Para obter informações sobre como configurar o Azure Front Door Service, consulte [Início Rápido: Crie um Front Door para um aplicativo Web global altamente disponível](https://docs.microsoft.com/azure/frontdoor/quickstart-create-front-door).

### <a name="configure-a-back-end-pool-in-azure-front-door-service"></a>Configurar um pool de back-end no Azure Front Door Service

Para configurar um pool de back-end no Azure Front Door Service, siga estas etapas.

1. Adicione **&lt;ecom-tenant-name&gt;.commerce.dynamics.com** para um pool de back-end como um host personalizado que tenha um cabeçalho de host de back-end vazio.
1. Em **Sondas de integridade**, no campo **Caminho**, insira **/keepalive**.
1. No campo **Intervalos (segundos)**, insira **255**.
1. Em **Balanceamento de carga**, deixe os valores padrão.

A ilustração a seguir mostra a caixa de diálogo **Adicionar um pool de back-end** no Azure Front Door Service.

![Caixa de diálogo Adicionar um pool de back-end](./media/CDN_BackendPool.png)

### <a name="set-up-rules-in-azure-front-door-service"></a>Configurar regras no Azure Front Door Service

Para configurar uma regra de roteamento no Azure Front Door Service, siga estas etapas.

1. Adicione uma regra de roteamento.
1. No campo **Nome**, digite **padrão**.
1. No campo **Protocolo aceito**, selecione **HTTP e HTTPS**.
1. No campo **Hosts de front-end**, insira **dynamics-ecom-tenant-name.azurefd.net**.
1. Em **Padrões para correspondência**, no campo superior, insira **/\***.
1. Em **Detalhes do roteiro**, defina a opção **Tipo de roteiro** como **Encaminhar**.
1. No campo **Pool de back-end**, selecione **ecom-backend**.
1. No grupo de campos **Protocolo de encaminhamento**, selecione a opção **Solicitação de correspondência**. 
1. Defina a opção **Reescrita de URL** como **Desabilitada**.
1. Defina a opção **Cache** como **Desabilitada**.

Para configurar uma regra de cache no Azure Front Door Service, siga estas etapas.

1. Adicione uma regra de cache.
1. No campo **Nome**, digite **estática**.
1. No campo **Protocolo aceito**, selecione **HTTP e HTTPS**.
1. No campo **Hosts de front-end**, insira **dynamics-ecom-tenant-name.azurefd.net**.
1. Em **Padrões para correspondência**, no campo superior, **/\_msdyn365/\_scnr/\***.
1. Em **Detalhes do roteiro**, defina a opção **Tipo de roteiro** como **Encaminhar**.
1. No campo **Pool de back-end**, selecione **ecom-backend**.
1. No grupo de campos **Protocolo de encaminhamento**, selecione a opção **Solicitação de correspondência**.
1. Defina a opção **Reescrita de URL** como **Desabilitada**.
1. Defina a opção **Cache** como **Desabilitada**.
1. No campo **Comportamento de cache da cadeia de caracteres de consulta**, selecione **Armazenar em cache cada URL exclusiva**.
1. No grupo de campos **Compactação dinâmica**, selecione a opção **Habilitada**.

A ilustração a seguir mostra a caixa de diálogo **Adicionar uma regra** no Azure Front Door Service.

![Caixa de diálogo Adicionar uma regra](./media/CDN_CachingRule.png)

Depois que essa configuração inicial é implantada, é preciso adicionar seu domínio personalizado à configuração do Azure Front Door Service. Para adicionar o domínio personalizado (por exemplo, `www.fabrikam.com`), você deve configurar um nome canônico (CNAME) para o domínio.

A ilustração a seguir mostra a caixa de diálogo **Configuração de CNAME** no Azure Front Door Service.

![Caixa de diálogo Configuração de CNAME](./media/CNAME_Configuration.png)

> [!NOTE]
> Se o domínio que você usará já estiver ativo, entre em contato com o suporte para habilitar esse domínio com o Azure Front Door Service para configurar um teste.

É possível usar o Azure Front Door Service para gerenciar o certificado ou usar seu próprio certificado para o domínio personalizado.

A ilustração a seguir mostra a caixa de diálogo **HTTPS de domínio personalizado** no Azure Front Door Service.

![Caixa de diálogo HTTPS de domínio personalizado](./media/Custom_Domain_HTTPS.png)

Agora sua CDN deve estar configurada corretamente para poder ser usada com o site do Commerce.

## <a name="additional-resources"></a>Recursos adicionais

[Configure seu nome de domínio](configure-your-domain-name.md)

[Implantar um novo site de comércio eletrônico](deploy-ecommerce-site.md)

[Criar um site de comércio eletrônico](create-ecommerce-site.md)

[Associar um site online a um canal](associate-site-online-store.md)

[Gerenciar arquivos robots.txt](manage-robots-txt-files.md)

[Carregar redirecionamentos de URL em massa](upload-bulk-redirects.md)

[Configurar um locatário B2C do Commerce](set-up-B2C-tenant.md)

[Configurar páginas personalizadas para logons dos usuários](custom-pages-user-logins.md)

[Configurar múltiplos locatários B2C em um ambiente do Commerce](configure-multi-B2C-tenants.md)

[Habilitar detecção de lojas com base na localização](enable-store-detection.md)
