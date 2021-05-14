---
title: Adicionar suporte para uma rede de entrega de conteúdo (CDN)
description: Este tópico descreve como adicionar uma rede de entrega de conteúdo (CDN) ao ambiente do Microsoft Dynamics 365 Commerce.
author: brianshook
ms.date: 03/17/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 59277323e0995f59d3a451395a038fa3708274eb
ms.sourcegitcommit: 9eadc7ca08e2db3fd208f5fc835551abe9d06dc8
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/22/2021
ms.locfileid: "5936821"
---
# <a name="add-support-for-a-content-delivery-network-cdn"></a><span data-ttu-id="35ba7-103">Adicionar suporte para uma rede de distribuição de conteúdo (CDN)</span><span class="sxs-lookup"><span data-stu-id="35ba7-103">Add support for a content delivery network (CDN)</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="35ba7-104">Este tópico descreve como adicionar uma rede de entrega de conteúdo (CDN) ao ambiente do Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="35ba7-104">This topic describes how to add a content delivery network (CDN) to your Microsoft Dynamics 365 Commerce environment.</span></span>

<span data-ttu-id="35ba7-105">Ao configurar um ambiente de comércio eletrônico no Dynamics 365 Commerce, você pode configurá-lo para funcionar com o serviço de CDN.</span><span class="sxs-lookup"><span data-stu-id="35ba7-105">When you set up an e-commerce environment in Dynamics 365 Commerce, you can configure it to work with your CDN service.</span></span> 

<span data-ttu-id="35ba7-106">Seu domínio personalizado pode ser habilitado durante o processo de provisionamento para o ambiente de comércio eletrônico.</span><span class="sxs-lookup"><span data-stu-id="35ba7-106">Your custom domain can be enabled during the provisioning process for your e-commerce environment.</span></span> <span data-ttu-id="35ba7-107">Como alternativa, você pode usar uma solicitação de serviço para configurá-la após a conclusão do processo de provisionamento.</span><span class="sxs-lookup"><span data-stu-id="35ba7-107">Alternatively, you can use a service request to set it up after the provisioning process is completed.</span></span> <span data-ttu-id="35ba7-108">O processo de provisionamento para o ambiente de comércio eletrônico gera um nome de host associado ao ambiente.</span><span class="sxs-lookup"><span data-stu-id="35ba7-108">The provisioning process for the e-commerce environment generates a host name that is associated with the environment.</span></span> <span data-ttu-id="35ba7-109">Este nome de host tem o seguinte formato, no qual \<*e-commerce-tenant-name*\> é o nome de seu ambiente:</span><span class="sxs-lookup"><span data-stu-id="35ba7-109">This host name has the following format, where \<*e-commerce-tenant-name*\> is the name of your environment:</span></span>

<span data-ttu-id="35ba7-110">&lt;e-commerce-tenant-name&gt;.commerce.dynamics.com</span><span class="sxs-lookup"><span data-stu-id="35ba7-110">&lt;e-commerce-tenant-name&gt;.commerce.dynamics.com</span></span>

<span data-ttu-id="35ba7-111">O nome de host ou ponto de extremidade gerado durante o processo de provisionamento é compatível com um certificado SSL (Secure Sockets Layer) apenas para \*.commerce.dynamics.com.</span><span class="sxs-lookup"><span data-stu-id="35ba7-111">The host name or endpoint that is generated during the provisioning process supports a Secure Sockets Layer (SSL) certificate only for \*.commerce.dynamics.com.</span></span> <span data-ttu-id="35ba7-112">Não é compatível com SSL para domínios personalizados.</span><span class="sxs-lookup"><span data-stu-id="35ba7-112">It doesn't support SSL for custom domains.</span></span> <span data-ttu-id="35ba7-113">Portanto, é precisa encerrar o SSL para domínios personalizados em sua CDN e encaminhar o tráfego da CDN para o nome de host ou ponto de extremidade que o Commerce gerou.</span><span class="sxs-lookup"><span data-stu-id="35ba7-113">Therefore, you must terminate SSL for custom domains in your CDN and forward traffic from the CDN to the host name or endpoint that Commerce generated.</span></span> 

<span data-ttu-id="35ba7-114">Além disso, as *estatísticas* (arquivos JavaScript ou Folhas de Estilos em Cascata \[CSS\]) do Commerce são fornecidas por meio dos pontos de extremidade que o Commerce gerou (\*.commerce.dynamics.com).</span><span class="sxs-lookup"><span data-stu-id="35ba7-114">Additionally, the *statics* (JavaScript or Cascading Style Sheets \[CSS\] files) from Commerce are served from the endpoint that Commerce generated (\*.commerce.dynamics.com).</span></span> <span data-ttu-id="35ba7-115">A estática pode ser armazenada em cache somente se o nome de host ou ponto de extremidade que o Commerce gerou for colocado após a CDN.</span><span class="sxs-lookup"><span data-stu-id="35ba7-115">The statics can be cached only if the host name or endpoint that Commerce generated is put behind the CDN.</span></span>

## <a name="set-up-ssl"></a><span data-ttu-id="35ba7-116">Configurar SSL</span><span class="sxs-lookup"><span data-stu-id="35ba7-116">Set up SSL</span></span>

<span data-ttu-id="35ba7-117">Depois de provisionar o ambiente do Commerce com o domínio personalizado fornecido, ou depois de fornecer o domínio personalizado para o ambiente usando uma solicitação de serviço, é necessário trabalhar com equipe de integração do Commerce para planejar as alterações de DNS.</span><span class="sxs-lookup"><span data-stu-id="35ba7-117">After you provision your Commerce environment with the custom domain that is provided, or after you provide the custom domain for your environment by using a service request, you need to work with the Commerce onboarding team to plan the DNS changes.</span></span>

<span data-ttu-id="35ba7-118">Como mencionado anteriormente, o nome de host ou ponto de extremidade gerado é compatível com um certificado SSL apenas para \*.commerce.dynamics.com.</span><span class="sxs-lookup"><span data-stu-id="35ba7-118">As was previously mentioned, the generated host name or endpoint supports an SSL certificate only for \*.commerce.dynamics.com.</span></span> <span data-ttu-id="35ba7-119">Não é compatível com SSL para domínios personalizados.</span><span class="sxs-lookup"><span data-stu-id="35ba7-119">It doesn't support SSL for custom domains.</span></span>

## <a name="cdn-services"></a><span data-ttu-id="35ba7-120">Serviços CDN</span><span class="sxs-lookup"><span data-stu-id="35ba7-120">CDN services</span></span>

<span data-ttu-id="35ba7-121">Qualquer serviço de CDN pode ser usado com um ambiente do Commerce.</span><span class="sxs-lookup"><span data-stu-id="35ba7-121">Any CDN service can be used with a Commerce environment.</span></span> <span data-ttu-id="35ba7-122">Aqui estão dois exemplos:</span><span class="sxs-lookup"><span data-stu-id="35ba7-122">Here are two examples:</span></span>

- <span data-ttu-id="35ba7-123">**Microsoft Azure Front Door Service** – A solução de CDN do Azure.</span><span class="sxs-lookup"><span data-stu-id="35ba7-123">**Microsoft Azure Front Door Service** – The Azure CDN solution.</span></span> <span data-ttu-id="35ba7-124">Para obter mais informações sobre o Azure Front Door Service, consulte a [Documentação do Azure Front Door Service](/azure/frontdoor/).</span><span class="sxs-lookup"><span data-stu-id="35ba7-124">For more information about Azure Front Door Service, see [Azure Front Door Service Documentation](/azure/frontdoor/).</span></span>
- <span data-ttu-id="35ba7-125">**Dynamic Site Accelerator da Akamai** – Para obter mais informações, consulte [Dynamic Site Accelerator](https://www.akamai.com/us/en/products/performance/dynamic-site-accelerator.jsp).</span><span class="sxs-lookup"><span data-stu-id="35ba7-125">**Akamai Dynamic Site Accelerator** – For more information, see [Dynamic Site Accelerator](https://www.akamai.com/us/en/products/performance/dynamic-site-accelerator.jsp).</span></span>

## <a name="cdn-setup"></a><span data-ttu-id="35ba7-126">Configuração de CDN</span><span class="sxs-lookup"><span data-stu-id="35ba7-126">CDN setup</span></span>

<span data-ttu-id="35ba7-127">O processo de instalação da CDN consiste nas etapas gerais a seguir:</span><span class="sxs-lookup"><span data-stu-id="35ba7-127">The CDN setup process consists of these general steps:</span></span>

1. <span data-ttu-id="35ba7-128">Adicione um host de front-end.</span><span class="sxs-lookup"><span data-stu-id="35ba7-128">Add a front-end host.</span></span>
1. <span data-ttu-id="35ba7-129">Configure um pool de back-end.</span><span class="sxs-lookup"><span data-stu-id="35ba7-129">Configure a backend pool.</span></span>
1. <span data-ttu-id="35ba7-130">Configurar regras de roteamento.</span><span class="sxs-lookup"><span data-stu-id="35ba7-130">Set up rules for routing.</span></span>

### <a name="add-a-front-end-host"></a><span data-ttu-id="35ba7-131">Adicionar um host de front-end</span><span class="sxs-lookup"><span data-stu-id="35ba7-131">Add a front-end host</span></span>

<span data-ttu-id="35ba7-132">Qualquer serviço de CDN pode ser usado, mas, por exemplo, neste tópico, o Azure Front Door Service é usado.</span><span class="sxs-lookup"><span data-stu-id="35ba7-132">Any CDN service can be used, but for the example in this topic, Azure Front Door Service is used.</span></span> 

<span data-ttu-id="35ba7-133">Para obter informações sobre como configurar o Azure Front Door Service, consulte [Início Rápido: Crie um Front Door para um aplicativo Web global altamente disponível](/azure/frontdoor/quickstart-create-front-door).</span><span class="sxs-lookup"><span data-stu-id="35ba7-133">For information about how to set up Azure Front Door Service, see [Quickstart: Create a Front Door for a highly available global web application](/azure/frontdoor/quickstart-create-front-door).</span></span>

### <a name="configure-a-backend-pool-in-azure-front-door-service"></a><span data-ttu-id="35ba7-134">Configurar um pool de back-end no Azure Front Door Service</span><span class="sxs-lookup"><span data-stu-id="35ba7-134">Configure a backend pool in Azure Front Door Service</span></span>

<span data-ttu-id="35ba7-135">Para configurar um pool de back-end no Azure Front Door Service, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="35ba7-135">To configure a backend pool in Azure Front Door Service, follow these steps.</span></span>

1. <span data-ttu-id="35ba7-136">Adicionar **&lt;ecom-Tenant-name&gt;.commerce.dynamics.com** a um grupo de back-end como um host personalizado que tem um cabeçalho de host back-end que é o mesmo que **&lt;ecom-tenant-name&gt;.commerce.dynamics.com**.</span><span class="sxs-lookup"><span data-stu-id="35ba7-136">Add **&lt;ecom-tenant-name&gt;.commerce.dynamics.com** to a backend pool as a custom host that has a backend host header that is the same as **&lt;ecom-tenant-name&gt;.commerce.dynamics.com**.</span></span>
1. <span data-ttu-id="35ba7-137">Em **Balanceamento de carga**, deixe os valores padrão.</span><span class="sxs-lookup"><span data-stu-id="35ba7-137">Under **Load balancing**, leave the default values.</span></span>
1. <span data-ttu-id="35ba7-138">Desabilite as verificações de integridade do pool de back-end.</span><span class="sxs-lookup"><span data-stu-id="35ba7-138">Disable health checks for the backend pool.</span></span>

<span data-ttu-id="35ba7-139">A ilustração a seguir mostra a caixa de diálogo **Adicionar um pool de back-end** no Azure Front Door Service com o nome do host de back-end inserido.</span><span class="sxs-lookup"><span data-stu-id="35ba7-139">The following illustration shows the **Add a backend** dialog box in Azure Front Door Service with the backend host name entered.</span></span>

![Caixa de diálogo Adicionar um pool de back-end](./media/CDN_BackendPool.png)

<span data-ttu-id="35ba7-141">A ilustração a seguir mostra a caixa de diálogo **Adicionar um pool de back-end** no Azure Front Door Service com os valores de balanceamento de carga padrão.</span><span class="sxs-lookup"><span data-stu-id="35ba7-141">The following illustration shows the **Add a backend pool** dialog box in Azure Front Door Service with the default load balancing values.</span></span>

![Adicionar uma caixa de diálogo do pool de back-end continuada](./media/CDN_BackendPool_2.png)

> [!NOTE]
> <span data-ttu-id="35ba7-143">Certifique-se de desabilitar os **Testes de Integridade** ao configurar seu próprio Azure Front Door Service para Commerce.</span><span class="sxs-lookup"><span data-stu-id="35ba7-143">Be sure to disable **Health Probes** when setting up your own Azure Front Door service for Commerce.</span></span>


### <a name="set-up-rules-in-azure-front-door-service"></a><span data-ttu-id="35ba7-144">Configurar regras no Azure Front Door Service</span><span class="sxs-lookup"><span data-stu-id="35ba7-144">Set up rules in Azure Front Door Service</span></span>

<span data-ttu-id="35ba7-145">Para configurar uma regra de roteamento no Azure Front Door Service, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="35ba7-145">To set up a routing rule in Azure Front Door Service, follow these steps.</span></span>

1. <span data-ttu-id="35ba7-146">Adicione uma regra de roteamento.</span><span class="sxs-lookup"><span data-stu-id="35ba7-146">Add a routing rule.</span></span>
1. <span data-ttu-id="35ba7-147">No campo **Nome**, digite **padrão**.</span><span class="sxs-lookup"><span data-stu-id="35ba7-147">In the **Name** field, enter **default**.</span></span>
1. <span data-ttu-id="35ba7-148">No campo **Protocolo aceito**, selecione **HTTP e HTTPS**.</span><span class="sxs-lookup"><span data-stu-id="35ba7-148">In the **Accepted protocol** field, select **HTTP and HTTPS**.</span></span>
1. <span data-ttu-id="35ba7-149">No campo **Hosts de front-end**, insira **dynamics-ecom-tenant-name.azurefd.net**.</span><span class="sxs-lookup"><span data-stu-id="35ba7-149">In the **Frontend hosts** field, enter **dynamics-ecom-tenant-name.azurefd.net**.</span></span>
1. <span data-ttu-id="35ba7-150">Em **Padrões para correspondência**, no campo superior, insira **/\***.</span><span class="sxs-lookup"><span data-stu-id="35ba7-150">Under **Patterns to match**, in the upper field, enter **/\***.</span></span>
1. <span data-ttu-id="35ba7-151">Em **Detalhes do roteiro**, defina a opção **Tipo de roteiro** como **Encaminhar**.</span><span class="sxs-lookup"><span data-stu-id="35ba7-151">Under **Route Details**, set the **Route type** option to **Forward**.</span></span>
1. <span data-ttu-id="35ba7-152">No campo **Pool de back-end**, selecione **ecom-backend**.</span><span class="sxs-lookup"><span data-stu-id="35ba7-152">In the **Backend pool** field, select **ecom-backend**.</span></span>
1. <span data-ttu-id="35ba7-153">No grupo de campos **Protocolo de encaminhamento**, selecione a opção **Solicitação de correspondência**.</span><span class="sxs-lookup"><span data-stu-id="35ba7-153">In the **Forwarding protocol** field group, select the **Match request** option.</span></span> 
1. <span data-ttu-id="35ba7-154">Defina a opção **Reescrita de URL** como **Desabilitada**.</span><span class="sxs-lookup"><span data-stu-id="35ba7-154">Set the **URL rewrite** option to **Disabled**.</span></span>
1. <span data-ttu-id="35ba7-155">Defina a opção **Cache** como **Desabilitada**.</span><span class="sxs-lookup"><span data-stu-id="35ba7-155">Set the **Caching** option to **Disabled**.</span></span>


> [!WARNING]
> <span data-ttu-id="35ba7-156">Se o domínio que você usar já estiver ativo e ao vivo, crie um tíquete de suporte do bloco **Suporte** no [Microsoft Dynamics Lifecycle Services](https://lcs.dynamics.com/) para obter ajuda para as próximas etapas.</span><span class="sxs-lookup"><span data-stu-id="35ba7-156">If the domain that you will use is already active and live, create a support ticket from the **Support** tile in [Microsoft Dynamics Lifecycle Services](https://lcs.dynamics.com/) to get assistance for your next steps.</span></span> <span data-ttu-id="35ba7-157">Para obter mais informações, consulte [Obter suporte para aplicativos do Finance and Operations ou Lifecycle Services (LCs)](../fin-ops-core/dev-itpro/lifecycle-services/lcs-support.md).</span><span class="sxs-lookup"><span data-stu-id="35ba7-157">For more information, see [Get support for Finance and Operations apps or Lifecycle Services (LCS)](../fin-ops-core/dev-itpro/lifecycle-services/lcs-support.md).</span></span>

<span data-ttu-id="35ba7-158">Se o domínio for novo e não for um domínio dinâmico pré-existente, você poderá adicionar seu domínio personalizado à configuração do Azure Front Door Service.</span><span class="sxs-lookup"><span data-stu-id="35ba7-158">If your domain is new and is not a pre-existing live domain, you can add your custom domain to the configuration for Azure Front Door Service.</span></span> <span data-ttu-id="35ba7-159">Isso permitirá que o tráfego da Web direcione ao seu site por meio da instância do Azure Front Door.</span><span class="sxs-lookup"><span data-stu-id="35ba7-159">This will enable web traffic to direct to your site via the Azure Front Door instance.</span></span> <span data-ttu-id="35ba7-160">Para adicionar o domínio personalizado (por exemplo, `www.fabrikam.com`), você deve configurar um nome canônico (CNAME) para o domínio.</span><span class="sxs-lookup"><span data-stu-id="35ba7-160">To add the custom domain (for example, `www.fabrikam.com`), you must configure a Canonical Name (CNAME) for the domain.</span></span>

<span data-ttu-id="35ba7-161">A ilustração a seguir mostra a caixa de diálogo **Configuração de CNAME** no Azure Front Door Service.</span><span class="sxs-lookup"><span data-stu-id="35ba7-161">The following illustration shows the **CNAME configuration** dialog box in Azure Front Door Service.</span></span>

![Caixa de diálogo Configuração de CNAME](./media/CNAME_Configuration.png)

<span data-ttu-id="35ba7-163">É possível usar o Azure Front Door Service para gerenciar o certificado ou usar seu próprio certificado para o domínio personalizado.</span><span class="sxs-lookup"><span data-stu-id="35ba7-163">You can use Azure Front Door Service to manage the certificate, or you can use your own certificate for the custom domain.</span></span>

<span data-ttu-id="35ba7-164">A ilustração a seguir mostra a caixa de diálogo **HTTPS de domínio personalizado** no Azure Front Door Service.</span><span class="sxs-lookup"><span data-stu-id="35ba7-164">The following illustration shows the **Custom Domain HTTPS** dialog box in Azure Front Door Service.</span></span>

![Caixa de diálogo HTTPS de domínio personalizado](./media/Custom_Domain_HTTPS.png)

<span data-ttu-id="35ba7-166">Para obter instruções detalhadas sobre como adicionar um domínio personalizado ao seu Azure Front Door, consulte [Adicionar um domínio personalizado ao seu Front Door](/azure/frontdoor/front-door-custom-domain).</span><span class="sxs-lookup"><span data-stu-id="35ba7-166">For detailed instructions on adding a custom domain to your Azure Front Door, see [Add a custom domain to your Front Door](/azure/frontdoor/front-door-custom-domain).</span></span>

<span data-ttu-id="35ba7-167">Agora sua CDN deve estar configurada corretamente para poder ser usada com o site do Commerce.</span><span class="sxs-lookup"><span data-stu-id="35ba7-167">Your CDN should now be correctly configured so that it can be used with your Commerce site.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="35ba7-168">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="35ba7-168">Additional resources</span></span>

[<span data-ttu-id="35ba7-169">Opções de implementação da rede de distribuição de conteúdo</span><span class="sxs-lookup"><span data-stu-id="35ba7-169">Content delivery network implementation options</span></span>](cdn-options.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]