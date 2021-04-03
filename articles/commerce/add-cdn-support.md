---
title: Adicionar suporte para uma rede de entrega de conteúdo (CDN)
description: Este tópico descreve como adicionar uma rede de entrega de conteúdo (CDN) ao ambiente do Microsoft Dynamics 365 Commerce.
author: brianshook
manager: annbe
ms.date: 07/31/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: d653b072eca134c765a5db5659b228648fc13c4a
ms.sourcegitcommit: 3fe4d9a33447aa8a62d704fbbf18aeb9cb667baa
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/12/2021
ms.locfileid: "5582710"
---
# <a name="add-support-for-a-content-delivery-network-cdn"></a><span data-ttu-id="641da-103">Adicionar suporte para uma rede de distribuição de conteúdo (CDN)</span><span class="sxs-lookup"><span data-stu-id="641da-103">Add support for a content delivery network (CDN)</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="641da-104">Este tópico descreve como adicionar uma rede de entrega de conteúdo (CDN) ao ambiente do Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="641da-104">This topic describes how to add a content delivery network (CDN) to your Microsoft Dynamics 365 Commerce environment.</span></span>

<span data-ttu-id="641da-105">Ao configurar um ambiente de comércio eletrônico no Dynamics 365 Commerce, você pode configurá-lo para funcionar com o serviço de CDN.</span><span class="sxs-lookup"><span data-stu-id="641da-105">When you set up an e-commerce environment in Dynamics 365 Commerce, you can configure it to work with your CDN service.</span></span> 

<span data-ttu-id="641da-106">Seu domínio personalizado pode ser habilitado durante o processo de provisionamento para o ambiente de comércio eletrônico.</span><span class="sxs-lookup"><span data-stu-id="641da-106">Your custom domain can be enabled during the provisioning process for your e-commerce environment.</span></span> <span data-ttu-id="641da-107">Como alternativa, você pode usar uma solicitação de serviço para configurá-la após a conclusão do processo de provisionamento.</span><span class="sxs-lookup"><span data-stu-id="641da-107">Alternatively, you can use a service request to set it up after the provisioning process is completed.</span></span> <span data-ttu-id="641da-108">O processo de provisionamento para o ambiente de comércio eletrônico gera um nome de host associado ao ambiente.</span><span class="sxs-lookup"><span data-stu-id="641da-108">The provisioning process for the e-commerce environment generates a host name that is associated with the environment.</span></span> <span data-ttu-id="641da-109">Este nome de host tem o seguinte formato, no qual \<*e-commerce-tenant-name*\> é o nome de seu ambiente:</span><span class="sxs-lookup"><span data-stu-id="641da-109">This host name has the following format, where \<*e-commerce-tenant-name*\> is the name of your environment:</span></span>

<span data-ttu-id="641da-110">&lt;e-commerce-tenant-name&gt;.commerce.dynamics.com</span><span class="sxs-lookup"><span data-stu-id="641da-110">&lt;e-commerce-tenant-name&gt;.commerce.dynamics.com</span></span>

<span data-ttu-id="641da-111">O nome de host ou ponto de extremidade gerado durante o processo de provisionamento é compatível com um certificado SSL (Secure Sockets Layer) apenas para \*.commerce.dynamics.com.</span><span class="sxs-lookup"><span data-stu-id="641da-111">The host name or endpoint that is generated during the provisioning process supports a Secure Sockets Layer (SSL) certificate only for \*.commerce.dynamics.com.</span></span> <span data-ttu-id="641da-112">Não é compatível com SSL para domínios personalizados.</span><span class="sxs-lookup"><span data-stu-id="641da-112">It doesn't support SSL for custom domains.</span></span> <span data-ttu-id="641da-113">Portanto, é precisa encerrar o SSL para domínios personalizados em sua CDN e encaminhar o tráfego da CDN para o nome de host ou ponto de extremidade que o Commerce gerou.</span><span class="sxs-lookup"><span data-stu-id="641da-113">Therefore, you must terminate SSL for custom domains in your CDN and forward traffic from the CDN to the host name or endpoint that Commerce generated.</span></span> 

<span data-ttu-id="641da-114">Além disso, as *estatísticas* (arquivos JavaScript ou Folhas de Estilos em Cascata \[CSS\]) do Commerce são fornecidas por meio dos pontos de extremidade que o Commerce gerou (\*.commerce.dynamics.com).</span><span class="sxs-lookup"><span data-stu-id="641da-114">Additionally, the *statics* (JavaScript or Cascading Style Sheets \[CSS\] files) from Commerce are served from the endpoint that Commerce generated (\*.commerce.dynamics.com).</span></span> <span data-ttu-id="641da-115">A estática pode ser armazenada em cache somente se o nome de host ou ponto de extremidade que o Commerce gerou for colocado após a CDN.</span><span class="sxs-lookup"><span data-stu-id="641da-115">The statics can be cached only if the host name or endpoint that Commerce generated is put behind the CDN.</span></span>

## <a name="set-up-ssl"></a><span data-ttu-id="641da-116">Configurar SSL</span><span class="sxs-lookup"><span data-stu-id="641da-116">Set up SSL</span></span>

<span data-ttu-id="641da-117">Para ajudar a garantir que o SSL esteja configurado e que as estáticas sejam armazenadas em cache, você deve configurar sua CDN para que ela seja associada ao nome de host que o Commerce gerou para o seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="641da-117">To help guarantee that SSL is set up, and that statics are cached, you must configure your CDN so that it is associated with the host name that Commerce generated for your environment.</span></span> <span data-ttu-id="641da-118">Você também deve armazenar em cache o seguinte padrão apenas para estática:</span><span class="sxs-lookup"><span data-stu-id="641da-118">You must also cache the following pattern for statics only:</span></span> 

<span data-ttu-id="641da-119">/\_msdyn365/\_scnr/\*</span><span class="sxs-lookup"><span data-stu-id="641da-119">/\_msdyn365/\_scnr/\*</span></span>

<span data-ttu-id="641da-120">Depois de provisionar o ambiente do Commerce com o domínio personalizado fornecido, ou depois de fornecer o domínio personalizado para o ambiente usando uma solicitação de serviço, aponte o domínio personalizado para o nome de host ou ponto de extremidade que o Commerce gerou.</span><span class="sxs-lookup"><span data-stu-id="641da-120">After you provision your Commerce environment with the custom domain that is provided, or after you provide the custom domain for your environment by using a service request, point your custom domain to the host name or endpoint that Commerce generated.</span></span>

<span data-ttu-id="641da-121">Como mencionado anteriormente, o nome de host ou ponto de extremidade gerado é compatível com um certificado SSL apenas para \*.commerce.dynamics.com.</span><span class="sxs-lookup"><span data-stu-id="641da-121">As was previously mentioned, the generated host name or endpoint supports an SSL certificate only for \*.commerce.dynamics.com.</span></span> <span data-ttu-id="641da-122">Não é compatível com SSL para domínios personalizados.</span><span class="sxs-lookup"><span data-stu-id="641da-122">It doesn't support SSL for custom domains.</span></span>

## <a name="cdn-services"></a><span data-ttu-id="641da-123">Serviços CDN</span><span class="sxs-lookup"><span data-stu-id="641da-123">CDN services</span></span>

<span data-ttu-id="641da-124">Qualquer serviço de CDN pode ser usado com um ambiente do Commerce.</span><span class="sxs-lookup"><span data-stu-id="641da-124">Any CDN service can be used with a Commerce environment.</span></span> <span data-ttu-id="641da-125">Aqui estão dois exemplos:</span><span class="sxs-lookup"><span data-stu-id="641da-125">Here are two examples:</span></span>

- <span data-ttu-id="641da-126">**Microsoft Azure Front Door Service** – A solução de CDN do Azure.</span><span class="sxs-lookup"><span data-stu-id="641da-126">**Microsoft Azure Front Door Service** – The Azure CDN solution.</span></span> <span data-ttu-id="641da-127">Para obter mais informações sobre o Azure Front Door Service, consulte a [Documentação do Azure Front Door Service](https://docs.microsoft.com/azure/frontdoor/).</span><span class="sxs-lookup"><span data-stu-id="641da-127">For more information about Azure Front Door Service, see [Azure Front Door Service Documentation](https://docs.microsoft.com/azure/frontdoor/).</span></span>
- <span data-ttu-id="641da-128">**Dynamic Site Accelerator da Akamai** – Para obter mais informações, consulte [Dynamic Site Accelerator](https://www.akamai.com/us/en/products/performance/dynamic-site-accelerator.jsp).</span><span class="sxs-lookup"><span data-stu-id="641da-128">**Akamai Dynamic Site Accelerator** – For more information, see [Dynamic Site Accelerator](https://www.akamai.com/us/en/products/performance/dynamic-site-accelerator.jsp).</span></span>

## <a name="cdn-setup"></a><span data-ttu-id="641da-129">Configuração de CDN</span><span class="sxs-lookup"><span data-stu-id="641da-129">CDN setup</span></span>

<span data-ttu-id="641da-130">O processo de instalação da CDN consiste nas etapas gerais a seguir:</span><span class="sxs-lookup"><span data-stu-id="641da-130">The CDN setup process consists of these general steps:</span></span>

1. <span data-ttu-id="641da-131">Adicione um host de front-end.</span><span class="sxs-lookup"><span data-stu-id="641da-131">Add a front-end host.</span></span>
1. <span data-ttu-id="641da-132">Configure um pool de back-end.</span><span class="sxs-lookup"><span data-stu-id="641da-132">Configure a backend pool.</span></span>
1. <span data-ttu-id="641da-133">Configure regras para roteamento e cache.</span><span class="sxs-lookup"><span data-stu-id="641da-133">Set up rules for routing and caching.</span></span>

### <a name="add-a-front-end-host"></a><span data-ttu-id="641da-134">Adicionar um host de front-end</span><span class="sxs-lookup"><span data-stu-id="641da-134">Add a front-end host</span></span>

<span data-ttu-id="641da-135">Qualquer serviço de CDN pode ser usado, mas, por exemplo, neste tópico, o Azure Front Door Service é usado.</span><span class="sxs-lookup"><span data-stu-id="641da-135">Any CDN service can be used, but for the example in this topic, Azure Front Door Service is used.</span></span> 

<span data-ttu-id="641da-136">Para obter informações sobre como configurar o Azure Front Door Service, consulte [Início Rápido: Crie um Front Door para um aplicativo Web global altamente disponível](https://docs.microsoft.com/azure/frontdoor/quickstart-create-front-door).</span><span class="sxs-lookup"><span data-stu-id="641da-136">For information about how to set up Azure Front Door Service, see [Quickstart: Create a Front Door for a highly available global web application](https://docs.microsoft.com/azure/frontdoor/quickstart-create-front-door).</span></span>

### <a name="configure-a-backend-pool-in-azure-front-door-service"></a><span data-ttu-id="641da-137">Configurar um pool de back-end no Azure Front Door Service</span><span class="sxs-lookup"><span data-stu-id="641da-137">Configure a backend pool in Azure Front Door Service</span></span>

<span data-ttu-id="641da-138">Para configurar um pool de back-end no Azure Front Door Service, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="641da-138">To configure a backend pool in Azure Front Door Service, follow these steps.</span></span>

1. <span data-ttu-id="641da-139">Adicione **&lt;ecom-tenant-name&gt;.commerce.dynamics.com** a um pool de back-end como um host personalizado que tenha um cabeçalho de host de back-end vazio.</span><span class="sxs-lookup"><span data-stu-id="641da-139">Add **&lt;ecom-tenant-name&gt;.commerce.dynamics.com** to a backend pool as a custom host that has an empty backend host header.</span></span>
1. <span data-ttu-id="641da-140">Em **Balanceamento de carga**, deixe os valores padrão.</span><span class="sxs-lookup"><span data-stu-id="641da-140">Under **Load balancing**, leave the default values.</span></span>

<span data-ttu-id="641da-141">A ilustração a seguir mostra a caixa de diálogo **Adicionar um pool de back-end** no Azure Front Door Service com o nome do host de back-end inserido.</span><span class="sxs-lookup"><span data-stu-id="641da-141">The following illustration shows the **Add a backend** dialog box in Azure Front Door Service with the backend host name entered.</span></span>

![Caixa de diálogo Adicionar um pool de back-end](./media/CDN_BackendPool.png)

<span data-ttu-id="641da-143">A ilustração a seguir mostra a caixa de diálogo **Adicionar um pool de back-end** no Azure Front Door Service com os valores de balanceamento de carga padrão.</span><span class="sxs-lookup"><span data-stu-id="641da-143">The following illustration shows the **Add a backend pool** dialog box in Azure Front Door Service with the default load balancing values.</span></span>

![Adicionar uma caixa de diálogo do pool de back-end continuada](./media/CDN_BackendPool_2.png)

### <a name="set-up-rules-in-azure-front-door-service"></a><span data-ttu-id="641da-145">Configurar regras no Azure Front Door Service</span><span class="sxs-lookup"><span data-stu-id="641da-145">Set up rules in Azure Front Door Service</span></span>

<span data-ttu-id="641da-146">Para configurar uma regra de roteamento no Azure Front Door Service, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="641da-146">To set up a routing rule in Azure Front Door Service, follow these steps.</span></span>

1. <span data-ttu-id="641da-147">Adicione uma regra de roteamento.</span><span class="sxs-lookup"><span data-stu-id="641da-147">Add a routing rule.</span></span>
1. <span data-ttu-id="641da-148">No campo **Nome**, digite **padrão**.</span><span class="sxs-lookup"><span data-stu-id="641da-148">In the **Name** field, enter **default**.</span></span>
1. <span data-ttu-id="641da-149">No campo **Protocolo aceito**, selecione **HTTP e HTTPS**.</span><span class="sxs-lookup"><span data-stu-id="641da-149">In the **Accepted protocol** field, select **HTTP and HTTPS**.</span></span>
1. <span data-ttu-id="641da-150">No campo **Hosts de front-end**, insira **dynamics-ecom-tenant-name.azurefd.net**.</span><span class="sxs-lookup"><span data-stu-id="641da-150">In the **Frontend hosts** field, enter **dynamics-ecom-tenant-name.azurefd.net**.</span></span>
1. <span data-ttu-id="641da-151">Em **Padrões para correspondência**, no campo superior, insira **/\***.</span><span class="sxs-lookup"><span data-stu-id="641da-151">Under **Patterns to match**, in the upper field, enter **/\***.</span></span>
1. <span data-ttu-id="641da-152">Em **Detalhes do roteiro**, defina a opção **Tipo de roteiro** como **Encaminhar**.</span><span class="sxs-lookup"><span data-stu-id="641da-152">Under **Route Details**, set the **Route type** option to **Forward**.</span></span>
1. <span data-ttu-id="641da-153">No campo **Pool de back-end**, selecione **ecom-backend**.</span><span class="sxs-lookup"><span data-stu-id="641da-153">In the **Backend pool** field, select **ecom-backend**.</span></span>
1. <span data-ttu-id="641da-154">No grupo de campos **Protocolo de encaminhamento**, selecione a opção **Solicitação de correspondência**.</span><span class="sxs-lookup"><span data-stu-id="641da-154">In the **Forwarding protocol** field group, select the **Match request** option.</span></span> 
1. <span data-ttu-id="641da-155">Defina a opção **Reescrita de URL** como **Desabilitada**.</span><span class="sxs-lookup"><span data-stu-id="641da-155">Set the **URL rewrite** option to **Disabled**.</span></span>
1. <span data-ttu-id="641da-156">Defina a opção **Cache** como **Desabilitada**.</span><span class="sxs-lookup"><span data-stu-id="641da-156">Set the **Caching** option to **Disabled**.</span></span>

<span data-ttu-id="641da-157">Para configurar uma regra de cache no Azure Front Door Service, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="641da-157">To set up a caching rule in Azure Front Door Service, follow these steps.</span></span>

1. <span data-ttu-id="641da-158">Adicione uma regra de cache.</span><span class="sxs-lookup"><span data-stu-id="641da-158">Add a caching rule.</span></span>
1. <span data-ttu-id="641da-159">No campo **Nome**, digite **estática**.</span><span class="sxs-lookup"><span data-stu-id="641da-159">In the **Name** field, enter **statics**.</span></span>
1. <span data-ttu-id="641da-160">No campo **Protocolo aceito**, selecione **HTTP e HTTPS**.</span><span class="sxs-lookup"><span data-stu-id="641da-160">In the **Accepted protocol** field, select **HTTP and HTTPS**.</span></span>
1. <span data-ttu-id="641da-161">No campo **Hosts de front-end**, insira **dynamics-ecom-tenant-name.azurefd.net**.</span><span class="sxs-lookup"><span data-stu-id="641da-161">In the **Frontend hosts** field, enter **dynamics-ecom-tenant-name.azurefd.net**.</span></span>
1. <span data-ttu-id="641da-162">Em **Padrões para correspondência**, no campo superior, **/\_msdyn365/\_scnr/\***.</span><span class="sxs-lookup"><span data-stu-id="641da-162">Under **Patterns to match**, in the upper field, **/\_msdyn365/\_scnr/\***.</span></span>
1. <span data-ttu-id="641da-163">Em **Detalhes do roteiro**, defina a opção **Tipo de roteiro** como **Encaminhar**.</span><span class="sxs-lookup"><span data-stu-id="641da-163">Under **Route Details**, set the **Route type** option to **Forward**.</span></span>
1. <span data-ttu-id="641da-164">No campo **Pool de back-end**, selecione **ecom-backend**.</span><span class="sxs-lookup"><span data-stu-id="641da-164">In the **Backend pool** field, select **ecom-backend**.</span></span>
1. <span data-ttu-id="641da-165">No grupo de campos **Protocolo de encaminhamento**, selecione a opção **Solicitação de correspondência**.</span><span class="sxs-lookup"><span data-stu-id="641da-165">In the **Forwarding protocol** field group, select the **Match request** option.</span></span>
1. <span data-ttu-id="641da-166">Defina a opção **Reescrita de URL** como **Desabilitada**.</span><span class="sxs-lookup"><span data-stu-id="641da-166">Set the **URL rewrite** option to **Disabled**.</span></span>
1. <span data-ttu-id="641da-167">Defina a opção **Cache** como **Desabilitada**.</span><span class="sxs-lookup"><span data-stu-id="641da-167">Set the **Caching** option to **Disabled**.</span></span>
1. <span data-ttu-id="641da-168">No campo **Comportamento de cache da cadeia de caracteres de consulta**, selecione **Armazenar em cache cada URL exclusiva**.</span><span class="sxs-lookup"><span data-stu-id="641da-168">In the **Query string caching behavior** field, select **Cache every unique URL**.</span></span>
1. <span data-ttu-id="641da-169">No grupo de campos **Compactação dinâmica**, selecione a opção **Habilitada**.</span><span class="sxs-lookup"><span data-stu-id="641da-169">In the **Dynamic compression** field group, select the **Enabled** option.</span></span>

<span data-ttu-id="641da-170">A ilustração a seguir mostra a caixa de diálogo **Adicionar uma regra** no Azure Front Door Service.</span><span class="sxs-lookup"><span data-stu-id="641da-170">The following illustration shows the **Add a rule** dialog box in Azure Front Door Service.</span></span>

![Caixa de diálogo Adicionar uma regra](./media/CDN_CachingRule.png)

> [!WARNING]
> <span data-ttu-id="641da-172">Se o domínio que você usar já estiver ativo e ao vivo, crie um tíquete de suporte do bloco **Suporte** no [Microsoft Dynamics Lifecycle Services](https://lcs.dynamics.com/) para obter ajuda para as próximas etapas.</span><span class="sxs-lookup"><span data-stu-id="641da-172">If the domain that you will use is already active and live, create a support ticket from the **Support** tile in [Microsoft Dynamics Lifecycle Services](https://lcs.dynamics.com/) to get assistance for your next steps.</span></span> <span data-ttu-id="641da-173">Para obter mais informações, consulte [Obter suporte para aplicativos do Finance and Operations ou Lifecycle Services (LCs)](../fin-ops-core/dev-itpro/lifecycle-services/lcs-support.md).</span><span class="sxs-lookup"><span data-stu-id="641da-173">For more information, see [Get support for Finance and Operations apps or Lifecycle Services (LCS)](../fin-ops-core/dev-itpro/lifecycle-services/lcs-support.md).</span></span>

<span data-ttu-id="641da-174">Se o domínio for novo e não for um domínio dinâmico pré-existente, você poderá adicionar seu domínio personalizado à configuração do Azure Front Door Service.</span><span class="sxs-lookup"><span data-stu-id="641da-174">If your domain is new and is not a pre-existing live domain, you can add your custom domain to the configuration for Azure Front Door Service.</span></span> <span data-ttu-id="641da-175">Isso permitirá que o tráfego da Web direcione ao seu site por meio da instância do Azure Front Door.</span><span class="sxs-lookup"><span data-stu-id="641da-175">This will enable web traffic to direct to your site via the Azure Front Door instance.</span></span> <span data-ttu-id="641da-176">Para adicionar o domínio personalizado (por exemplo, `www.fabrikam.com`), você deve configurar um nome canônico (CNAME) para o domínio.</span><span class="sxs-lookup"><span data-stu-id="641da-176">To add the custom domain (for example, `www.fabrikam.com`), you must configure a Canonical Name (CNAME) for the domain.</span></span>

<span data-ttu-id="641da-177">A ilustração a seguir mostra a caixa de diálogo **Configuração de CNAME** no Azure Front Door Service.</span><span class="sxs-lookup"><span data-stu-id="641da-177">The following illustration shows the **CNAME configuration** dialog box in Azure Front Door Service.</span></span>

![Caixa de diálogo Configuração de CNAME](./media/CNAME_Configuration.png)

<span data-ttu-id="641da-179">É possível usar o Azure Front Door Service para gerenciar o certificado ou usar seu próprio certificado para o domínio personalizado.</span><span class="sxs-lookup"><span data-stu-id="641da-179">You can use Azure Front Door Service to manage the certificate, or you can use your own certificate for the custom domain.</span></span>

<span data-ttu-id="641da-180">A ilustração a seguir mostra a caixa de diálogo **HTTPS de domínio personalizado** no Azure Front Door Service.</span><span class="sxs-lookup"><span data-stu-id="641da-180">The following illustration shows the **Custom Domain HTTPS** dialog box in Azure Front Door Service.</span></span>

![Caixa de diálogo HTTPS de domínio personalizado](./media/Custom_Domain_HTTPS.png)

<span data-ttu-id="641da-182">Para obter instruções detalhadas sobre como adicionar um domínio personalizado ao seu Azure Front Door, consulte [Adicionar um domínio personalizado ao seu Front Door](https://docs.microsoft.com/azure/frontdoor/front-door-custom-domain).</span><span class="sxs-lookup"><span data-stu-id="641da-182">For detailed instructions on adding a custom domain to your Azure Front Door, see [Add a custom domain to your Front Door](https://docs.microsoft.com/azure/frontdoor/front-door-custom-domain).</span></span>

<span data-ttu-id="641da-183">Agora sua CDN deve estar configurada corretamente para poder ser usada com o site do Commerce.</span><span class="sxs-lookup"><span data-stu-id="641da-183">Your CDN should now be correctly configured so that it can be used with your Commerce site.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="641da-184">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="641da-184">Additional resources</span></span>

[<span data-ttu-id="641da-185">Opções de implementação da rede de distribuição de conteúdo</span><span class="sxs-lookup"><span data-stu-id="641da-185">Content delivery network implementation options</span></span>](cdn-options.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
