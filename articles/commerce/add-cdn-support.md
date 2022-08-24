---
title: Adicionar suporte para uma rede de distribuição de conteúdo (CDN)
description: Este artigo descreve como adicionar uma rede de distribuição de conteúdo (CDN) ao ambiente do Microsoft Dynamics 365 Commerce.
author: brianshook
ms.date: 03/17/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.custom: ''
ms.assetid: ''
ms.openlocfilehash: 84839c1e370dccd19462de5c4a3dc120df15df09
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9275803"
---
# <a name="add-support-for-a-content-delivery-network-cdn"></a>Adicionar suporte para uma rede de distribuição de conteúdo (CDN)

[!include [banner](includes/banner.md)]

Este artigo descreve como adicionar uma rede de distribuição de conteúdo (CDN) ao ambiente do Microsoft Dynamics 365 Commerce.

Ao configurar um ambiente de comércio eletrônico no Dynamics 365 Commerce, você pode configurá-lo para funcionar com o serviço de CDN. 

Seu domínio personalizado pode ser habilitado durante o processo de provisionamento para o ambiente de comércio eletrônico. Como alternativa, você pode usar uma solicitação de serviço para configurá-la após a conclusão do processo de provisionamento. O processo de provisionamento para o ambiente de comércio eletrônico gera um nome de host associado ao ambiente. Este nome de host tem o seguinte formato, no qual \<*e-commerce-tenant-name*\> é o nome de seu ambiente:

&lt;e-commerce-tenant-name&gt;.commerce.dynamics.com

O nome de host ou ponto de extremidade gerado durante o processo de provisionamento é compatível com um certificado SSL (Secure Sockets Layer) apenas para \*.commerce.dynamics.com. Não é compatível com SSL para domínios personalizados. Portanto, é precisa encerrar o SSL para domínios personalizados em sua CDN e encaminhar o tráfego da CDN para o nome de host ou ponto de extremidade que o Commerce gerou. 

Além disso, as *estatísticas* (arquivos JavaScript ou Folhas de Estilos em Cascata \[CSS\]) do Commerce são fornecidas por meio dos pontos de extremidade que o Commerce gerou (\*.commerce.dynamics.com). A estática pode ser armazenada em cache somente se o nome de host ou ponto de extremidade que o Commerce gerou for colocado após a CDN.

## <a name="set-up-ssl"></a>Configurar SSL

Depois de provisionar o ambiente do Commerce com o domínio personalizado fornecido, ou depois de fornecer o domínio personalizado para o ambiente usando uma solicitação de serviço, é necessário trabalhar com equipe de integração do Commerce para planejar as alterações de DNS.

Como mencionado anteriormente, o nome de host ou ponto de extremidade gerado é compatível com um certificado SSL apenas para \*.commerce.dynamics.com. Não é compatível com SSL para domínios personalizados.

## <a name="cdn-services"></a>Serviços CDN

Qualquer serviço de CDN pode ser usado com um ambiente do Commerce. Aqui estão dois exemplos:

- **Microsoft Azure Front Door Service** – A solução de CDN do Azure. Para obter mais informações sobre o Azure Front Door Service, consulte a [Documentação do Azure Front Door Service](/azure/frontdoor/).
- **Dynamic Site Accelerator da Akamai** – Para obter mais informações, consulte [Dynamic Site Accelerator](https://www.akamai.com/us/en/products/performance/dynamic-site-accelerator.jsp).

## <a name="cdn-setup"></a>Configuração de CDN

O processo de instalação da CDN consiste nas etapas gerais a seguir:

1. Adicione um host de front-end.
1. Configure um pool de back-end.
1. Configurar regras de roteamento.

### <a name="add-a-front-end-host"></a>Adicionar um host de front-end

Qualquer serviço de CDN pode ser usado, mas, por exemplo, neste artigo, o Azure Front Door Service é usado. 

Para obter informações sobre como configurar o Azure Front Door Service, consulte [Início Rápido: Crie um Front Door para um aplicativo Web global altamente disponível](/azure/frontdoor/quickstart-create-front-door).

### <a name="configure-a-backend-pool-in-azure-front-door-service"></a>Configurar um pool de back-end no Azure Front Door Service

Para configurar um pool de back-end no Azure Front Door Service, siga estas etapas.

1. Adicionar **&lt;ecom-Tenant-name&gt;.commerce.dynamics.com** a um grupo de back-end como um host personalizado que tem um cabeçalho de host back-end que é o mesmo que **&lt;ecom-tenant-name&gt;.commerce.dynamics.com**.
1. Em **Balanceamento de carga**, deixe os valores padrão.
1. Desabilite as verificações de integridade do pool de back-end.

A ilustração a seguir mostra a caixa de diálogo **Adicionar um pool de back-end** no Azure Front Door Service com o nome do host de back-end inserido.

![Caixa de diálogo Adicionar um pool de back-end.](./media/CDN_BackendPool.png)

A ilustração a seguir mostra a caixa de diálogo **Adicionar um pool de back-end** no Azure Front Door Service com os valores de balanceamento de carga padrão.

![Adicionar uma caixa de diálogo do pool de back-end continuada.](./media/CDN_BackendPool_2.png)

> [!NOTE]
> Certifique-se de desabilitar os **Testes de Integridade** ao configurar seu próprio Azure Front Door Service para Commerce.


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


> [!WARNING]
> Se o domínio que você usar já estiver ativo e ao vivo, crie um tíquete de suporte do bloco **Suporte** no [Microsoft Dynamics Lifecycle Services](https://lcs.dynamics.com/) para obter ajuda para as próximas etapas. Para obter mais informações, consulte [Obter suporte para os aplicativos de finanças e operações ou o Lifecycle Services (LCS)](../fin-ops-core/dev-itpro/lifecycle-services/lcs-support.md).

Se o domínio for novo e não for um domínio dinâmico pré-existente, você poderá adicionar seu domínio personalizado à configuração do Azure Front Door Service. Isso permitirá que o tráfego da Web direcione ao seu site por meio da instância do Azure Front Door. Para adicionar o domínio personalizado (por exemplo, `www.fabrikam.com`), você deve configurar um nome canônico (CNAME) para o domínio.

A ilustração a seguir mostra a caixa de diálogo **Configuração de CNAME** no Azure Front Door Service.

![Caixa de diálogo Configuração de CNAME.](./media/CNAME_Configuration.png)

É possível usar o Azure Front Door Service para gerenciar o certificado ou usar seu próprio certificado para o domínio personalizado.

A ilustração a seguir mostra a caixa de diálogo **HTTPS de domínio personalizado** no Azure Front Door Service.

![Caixa de diálogo HTTPS de domínio personalizado.](./media/Custom_Domain_HTTPS.png)

Para obter instruções detalhadas sobre como adicionar um domínio personalizado ao seu Azure Front Door, consulte [Adicionar um domínio personalizado ao seu Front Door](/azure/frontdoor/front-door-custom-domain).

Agora sua CDN deve estar configurada corretamente para poder ser usada com o site do Commerce.

## <a name="additional-resources"></a>Recursos adicionais

[Opções de implementação da rede de distribuição de conteúdo](cdn-options.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
