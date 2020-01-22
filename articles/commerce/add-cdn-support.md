---
title: Adicionar suporte para uma rede de entrega de conteúdo (CDN)
description: Este tópico descreve como adicionar uma rede de entrega de conteúdo (CDN) ao ambiente do Microsoft Dynamics 365 Commerce.
author: brianshook
manager: annbe
ms.date: 10/01/2019
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
ms.openlocfilehash: d2d64f0de5287a764cb2e40b99a08084494bf53c
ms.sourcegitcommit: ef3a1d7527311d00b69a1072ae5eb021ce68034c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/09/2020
ms.locfileid: "2945619"
---
# <a name="add-support-for-a-content-delivery-network-cdn"></a><span data-ttu-id="55be2-103">Adicionar suporte para uma rede de entrega de conteúdo (CDN)</span><span class="sxs-lookup"><span data-stu-id="55be2-103">Add support for a content delivery network (CDN)</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="55be2-104">Este tópico descreve como adicionar uma rede de entrega de conteúdo (CDN) ao ambiente do Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="55be2-104">This topic describes how to add a content delivery network (CDN) to your Microsoft Dynamics 365 Commerce environment.</span></span>

## <a name="overview"></a><span data-ttu-id="55be2-105">Visão geral</span><span class="sxs-lookup"><span data-stu-id="55be2-105">Overview</span></span>

<span data-ttu-id="55be2-106">Ao configurar um ambiente de comércio eletrônico no Dynamics 365 Commerce, você pode configurá-lo para funcionar com o serviço de CDN.</span><span class="sxs-lookup"><span data-stu-id="55be2-106">When you set up an e-Commerce environment in Dynamics 365 Commerce, you can configure it to work with your CDN service.</span></span> 

<span data-ttu-id="55be2-107">Seu domínio personalizado pode ser habilitado durante o processo de provisionamento para o seu ambiente de comércio eletrônico.</span><span class="sxs-lookup"><span data-stu-id="55be2-107">Your custom domain can be enabled during the provisioning process for your e-Commerce environment.</span></span> <span data-ttu-id="55be2-108">Como alternativa, você pode usar uma solicitação de serviço para configurá-la após a conclusão do processo de provisionamento.</span><span class="sxs-lookup"><span data-stu-id="55be2-108">Alternatively, you can use a service request to set it up after the provisioning process is completed.</span></span> <span data-ttu-id="55be2-109">O processo de provisionamento para o ambiente de comércio eletrônico gera um nome de host associado ao ambiente.</span><span class="sxs-lookup"><span data-stu-id="55be2-109">The provisioning process for the e-Commerce environment generates a host name that is associated with the environment.</span></span> <span data-ttu-id="55be2-110">Este nome de host tem o seguinte formato, em que *e-commerce-tenant-name* é o nome do seu ambiente:</span><span class="sxs-lookup"><span data-stu-id="55be2-110">This host name has the following format, where *e-commerce-tenant-name* is the name of your environment:</span></span>

<span data-ttu-id="55be2-111">&lt;e-commerce-tenant-name&gt;.commerce.dynamics.com</span><span class="sxs-lookup"><span data-stu-id="55be2-111">&lt;e-commerce-tenant-name&gt;.commerce.dynamics.com</span></span>

<span data-ttu-id="55be2-112">O nome de host ou ponto de extremidade gerado durante o processo de provisionamento é compatível com um certificado SSL (Secure Sockets Layer) apenas para \*.commerce.dynamics.com.</span><span class="sxs-lookup"><span data-stu-id="55be2-112">The host name or endpoint that is generated during the provisioning process supports a Secure Sockets Layer (SSL) certificate only for \*.commerce.dynamics.com.</span></span> <span data-ttu-id="55be2-113">Não é compatível com SSL para domínios personalizados.</span><span class="sxs-lookup"><span data-stu-id="55be2-113">It doesn't support SSL for custom domains.</span></span> <span data-ttu-id="55be2-114">Portanto, é precisa encerrar o SSL para domínios personalizados em sua CDN e encaminhar o tráfego da CDN para o nome de host ou ponto de extremidade que o Commerce gerou.</span><span class="sxs-lookup"><span data-stu-id="55be2-114">Therefore, you must terminate SSL for custom domains in your CDN and forward traffic from the CDN to the host name or endpoint that Commerce generated.</span></span> 

<span data-ttu-id="55be2-115">Além disso, as *estatísticas* (arquivos JavaScript ou Folhas de Estilos em Cascata \[CSS\]) do Commerce são fornecidas por meio dos pontos de extremidade que o Commerce gerou (\*.commerce.dynamics.com).</span><span class="sxs-lookup"><span data-stu-id="55be2-115">Additionally, the *statics* (JavaScript or Cascading Style Sheets \[CSS\] files) from Commerce are served from the endpoint that Commerce generated (\*.commerce.dynamics.com).</span></span> <span data-ttu-id="55be2-116">A estática pode ser armazenada em cache somente se o nome de host ou ponto de extremidade que o Commerce gerou for colocado após a CDN.</span><span class="sxs-lookup"><span data-stu-id="55be2-116">The statics can be cached only if the host name or endpoint that Commerce generated is put behind the CDN.</span></span>

## <a name="set-up-ssl"></a><span data-ttu-id="55be2-117">Configurar SSL</span><span class="sxs-lookup"><span data-stu-id="55be2-117">Set up SSL</span></span>

<span data-ttu-id="55be2-118">Para ajudar a garantir que o SSL esteja configurado e que as estáticas sejam armazenadas em cache, você deve configurar sua CDN para que ela seja associada ao nome de host que o Commerce gerou para o seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="55be2-118">To help guarantee that SSL is set up, and that statics are cached, you must configure your CDN so that it is associated with the host name that Commerce generated for your environment.</span></span> <span data-ttu-id="55be2-119">Você também deve armazenar em cache o seguinte padrão apenas para estática:</span><span class="sxs-lookup"><span data-stu-id="55be2-119">You must also cache the following pattern for statics only:</span></span> 

<span data-ttu-id="55be2-120">/\_msdyn365/\_scnr/\*</span><span class="sxs-lookup"><span data-stu-id="55be2-120">/\_msdyn365/\_scnr/\*</span></span>

<span data-ttu-id="55be2-121">Depois de provisionar o ambiente do Commerce com o domínio personalizado fornecido, ou depois de fornecer o domínio personalizado para o ambiente usando uma solicitação de serviço, aponte o domínio personalizado para o nome de host ou ponto de extremidade que o Commerce gerou.</span><span class="sxs-lookup"><span data-stu-id="55be2-121">After you provision your Commerce environment with the custom domain that is provided, or after you provide the custom domain for your environment by using a service request, point your custom domain to the host name or endpoint that Commerce generated.</span></span>

<span data-ttu-id="55be2-122">Como mencionado anteriormente, o nome de host ou ponto de extremidade gerado é compatível com um certificado SSL apenas para \*.commerce.dynamics.com.</span><span class="sxs-lookup"><span data-stu-id="55be2-122">As was previously mentioned, the generated host name or endpoint supports an SSL certificate only for \*.commerce.dynamics.com.</span></span> <span data-ttu-id="55be2-123">Não é compatível com SSL para domínios personalizados.</span><span class="sxs-lookup"><span data-stu-id="55be2-123">It doesn't support SSL for custom domains.</span></span>

## <a name="cdn-services"></a><span data-ttu-id="55be2-124">Serviços CDN</span><span class="sxs-lookup"><span data-stu-id="55be2-124">CDN services</span></span>

<span data-ttu-id="55be2-125">Qualquer serviço de CDN pode ser usado com um ambiente do Commerce.</span><span class="sxs-lookup"><span data-stu-id="55be2-125">Any CDN service can be used with a Commerce environment.</span></span> <span data-ttu-id="55be2-126">Aqui estão dois exemplos:</span><span class="sxs-lookup"><span data-stu-id="55be2-126">Here are two examples:</span></span>

- <span data-ttu-id="55be2-127">**Microsoft Azure Front Door Service** – A solução de CDN do Azure.</span><span class="sxs-lookup"><span data-stu-id="55be2-127">**Microsoft Azure Front Door Service** – The Azure CDN solution.</span></span> <span data-ttu-id="55be2-128">Para obter mais informações sobre o Azure Front Door Service, consulte a [Documentação do Azure Front Door Service](https://docs.microsoft.com/azure/frontdoor/).</span><span class="sxs-lookup"><span data-stu-id="55be2-128">For more information about Azure Front Door Service, see [Azure Front Door Service Documentation](https://docs.microsoft.com/azure/frontdoor/).</span></span>
- <span data-ttu-id="55be2-129">**Dynamic Site Accelerator da Akamai** – Para obter mais informações, consulte [Dynamic Site Accelerator](https://www.akamai.com/us/en/products/performance/dynamic-site-accelerator.jsp).</span><span class="sxs-lookup"><span data-stu-id="55be2-129">**Akamai Dynamic Site Accelerator** – For more information, see [Dynamic Site Accelerator](https://www.akamai.com/us/en/products/performance/dynamic-site-accelerator.jsp).</span></span>

## <a name="cdn-setup"></a><span data-ttu-id="55be2-130">Configuração de CDN</span><span class="sxs-lookup"><span data-stu-id="55be2-130">CDN setup</span></span>

<span data-ttu-id="55be2-131">O processo de instalação da CDN consiste nas etapas gerais a seguir:</span><span class="sxs-lookup"><span data-stu-id="55be2-131">The CDN setup process consists of these general steps:</span></span>

1. <span data-ttu-id="55be2-132">Adicione um host de front-end.</span><span class="sxs-lookup"><span data-stu-id="55be2-132">Add a front-end host.</span></span>
1. <span data-ttu-id="55be2-133">Configure um pool de back-end.</span><span class="sxs-lookup"><span data-stu-id="55be2-133">Configure a back-end pool.</span></span>
1. <span data-ttu-id="55be2-134">Configure regras para roteamento e cache.</span><span class="sxs-lookup"><span data-stu-id="55be2-134">Set up rules for routing and caching.</span></span>

### <a name="add-a-front-end-host"></a><span data-ttu-id="55be2-135">Adicionar um host de front-end</span><span class="sxs-lookup"><span data-stu-id="55be2-135">Add a front-end host</span></span>

<span data-ttu-id="55be2-136">Qualquer serviço de CDN pode ser usado, mas, por exemplo, neste tópico, o Azure Front Door Service é usado.</span><span class="sxs-lookup"><span data-stu-id="55be2-136">Any CDN service can be used, but for the example in this topic, Azure Front Door Service is used.</span></span> 

<span data-ttu-id="55be2-137">Para obter informações sobre como configurar o Azure Front Door Service, consulte [Início Rápido: Crie um Front Door para um aplicativo Web global altamente disponível](https://docs.microsoft.com/azure/frontdoor/quickstart-create-front-door).</span><span class="sxs-lookup"><span data-stu-id="55be2-137">For information about how to set up Azure Front Door Service, see [Quickstart: Create a Front Door for a highly available global web application](https://docs.microsoft.com/azure/frontdoor/quickstart-create-front-door).</span></span>

### <a name="configure-a-back-end-pool-in-azure-front-door-service"></a><span data-ttu-id="55be2-138">Configurar um pool de back-end no Azure Front Door Service</span><span class="sxs-lookup"><span data-stu-id="55be2-138">Configure a back-end pool in Azure Front Door Service</span></span>

<span data-ttu-id="55be2-139">Para configurar um pool de back-end no Azure Front Door Service, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="55be2-139">To configure a back-end pool in Azure Front Door Service, follow these steps.</span></span>

1. <span data-ttu-id="55be2-140">Adicione **&lt;ecom-tenant-name&gt;.commerce.dynamics.com** para um pool de back-end como um host personalizado que tenha um cabeçalho de host de back-end vazio.</span><span class="sxs-lookup"><span data-stu-id="55be2-140">Add **&lt;ecom-tenant-name&gt;.commerce.dynamics.com** to a back-end pool as a custom host that has an empty back-end host header.</span></span>
1. <span data-ttu-id="55be2-141">Em **Sondas de integridade**, no campo **Caminho**, insira **/keepalive**.</span><span class="sxs-lookup"><span data-stu-id="55be2-141">Under **Health probes**, in the **Path** field, enter **/keepalive**.</span></span>
1. <span data-ttu-id="55be2-142">No campo **Intervalos (segundos)**, insira **255**.</span><span class="sxs-lookup"><span data-stu-id="55be2-142">In the **Intervals (seconds)** field, enter **255**.</span></span>
1. <span data-ttu-id="55be2-143">Em **Balanceamento de carga**, deixe os valores padrão.</span><span class="sxs-lookup"><span data-stu-id="55be2-143">Under **Load balancing**, leave the default values.</span></span>

<span data-ttu-id="55be2-144">A ilustração a seguir mostra a caixa de diálogo **Adicionar um pool de back-end** no Azure Front Door Service.</span><span class="sxs-lookup"><span data-stu-id="55be2-144">The following illustration shows the **Add a backend pool** dialog box in Azure Front Door Service.</span></span>

![Caixa de diálogo Adicionar um pool de back-end](./media/CDN_BackendPool.png)

### <a name="set-up-rules-in-azure-front-door-service"></a><span data-ttu-id="55be2-146">Configurar regras no Azure Front Door Service</span><span class="sxs-lookup"><span data-stu-id="55be2-146">Set up rules in Azure Front Door Service</span></span>

<span data-ttu-id="55be2-147">Para configurar uma regra de roteamento no Azure Front Door Service, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="55be2-147">To set up a routing rule in Azure Front Door Service, follow these steps.</span></span>

1. <span data-ttu-id="55be2-148">Adicione uma regra de roteamento.</span><span class="sxs-lookup"><span data-stu-id="55be2-148">Add a routing rule.</span></span>
1. <span data-ttu-id="55be2-149">No campo **Nome**, digite **padrão**.</span><span class="sxs-lookup"><span data-stu-id="55be2-149">In the **Name** field, enter **default**.</span></span>
1. <span data-ttu-id="55be2-150">No campo **Protocolo aceito**, selecione **HTTP e HTTPS**.</span><span class="sxs-lookup"><span data-stu-id="55be2-150">In the **Accepted protocol** field, select **HTTP and HTTPS**.</span></span>
1. <span data-ttu-id="55be2-151">No campo **Hosts de front-end**, insira **dynamics-ecom-tenant-name.azurefd.net**.</span><span class="sxs-lookup"><span data-stu-id="55be2-151">In the **Frontend hosts** field, enter **dynamics-ecom-tenant-name.azurefd.net**.</span></span>
1. <span data-ttu-id="55be2-152">Em **Padrões para correspondência**, no campo superior, insira **/\***.</span><span class="sxs-lookup"><span data-stu-id="55be2-152">Under **Patterns to match**, in the upper field, enter **/\***.</span></span>
1. <span data-ttu-id="55be2-153">Em **Detalhes do roteiro**, defina a opção **Tipo de roteiro** como **Encaminhar**.</span><span class="sxs-lookup"><span data-stu-id="55be2-153">Under **Route Details**, set the **Route type** option to **Forward**.</span></span>
1. <span data-ttu-id="55be2-154">No campo **Pool de back-end**, selecione **ecom-backend**.</span><span class="sxs-lookup"><span data-stu-id="55be2-154">In the **Backend pool** field, select **ecom-backend**.</span></span>
1. <span data-ttu-id="55be2-155">No grupo de campos **Protocolo de encaminhamento**, selecione a opção **Solicitação de correspondência**.</span><span class="sxs-lookup"><span data-stu-id="55be2-155">In the **Forwarding protocol** field group, select the **Match request** option.</span></span> 
1. <span data-ttu-id="55be2-156">Defina a opção **Reescrita de URL** como **Desabilitada**.</span><span class="sxs-lookup"><span data-stu-id="55be2-156">Set the **URL rewrite** option to **Disabled**.</span></span>
1. <span data-ttu-id="55be2-157">Defina a opção **Cache** como **Desabilitada**.</span><span class="sxs-lookup"><span data-stu-id="55be2-157">Set the **Caching** option to **Disabled**.</span></span>

<span data-ttu-id="55be2-158">Para configurar uma regra de cache no Azure Front Door Service, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="55be2-158">To set up a caching rule in Azure Front Door Service, follow these steps.</span></span>

1. <span data-ttu-id="55be2-159">Adicione uma regra de cache.</span><span class="sxs-lookup"><span data-stu-id="55be2-159">Add a caching rule.</span></span>
1. <span data-ttu-id="55be2-160">No campo **Nome**, digite **estática**.</span><span class="sxs-lookup"><span data-stu-id="55be2-160">In the **Name** field, enter **statics**.</span></span>
1. <span data-ttu-id="55be2-161">No campo **Protocolo aceito**, selecione **HTTP e HTTPS**.</span><span class="sxs-lookup"><span data-stu-id="55be2-161">In the **Accepted protocol** field, select **HTTP and HTTPS**.</span></span>
1. <span data-ttu-id="55be2-162">No campo **Hosts de front-end**, insira **dynamics-ecom-tenant-name.azurefd.net**.</span><span class="sxs-lookup"><span data-stu-id="55be2-162">In the **Frontend hosts** field, enter **dynamics-ecom-tenant-name.azurefd.net**.</span></span>
1. <span data-ttu-id="55be2-163">Em **Padrões para correspondência**, no campo superior, **/\_msdyn365/\_scnr/\***.</span><span class="sxs-lookup"><span data-stu-id="55be2-163">Under **Patterns to match**, in the upper field, **/\_msdyn365/\_scnr/\***.</span></span>
1. <span data-ttu-id="55be2-164">Em **Detalhes do roteiro**, defina a opção **Tipo de roteiro** como **Encaminhar**.</span><span class="sxs-lookup"><span data-stu-id="55be2-164">Under **Route Details**, set the **Route type** option to **Forward**.</span></span>
1. <span data-ttu-id="55be2-165">No campo **Pool de back-end**, selecione **ecom-backend**.</span><span class="sxs-lookup"><span data-stu-id="55be2-165">In the **Backend pool** field, select **ecom-backend**.</span></span>
1. <span data-ttu-id="55be2-166">No grupo de campos **Protocolo de encaminhamento**, selecione a opção **Solicitação de correspondência**.</span><span class="sxs-lookup"><span data-stu-id="55be2-166">In the **Forwarding protocol** field group, select the **Match request** option.</span></span>
1. <span data-ttu-id="55be2-167">Defina a opção **Reescrita de URL** como **Desabilitada**.</span><span class="sxs-lookup"><span data-stu-id="55be2-167">Set the **URL rewrite** option to **Disabled**.</span></span>
1. <span data-ttu-id="55be2-168">Defina a opção **Cache** como **Desabilitada**.</span><span class="sxs-lookup"><span data-stu-id="55be2-168">Set the **Caching** option to **Disabled**.</span></span>
1. <span data-ttu-id="55be2-169">No campo **Comportamento de cache da cadeia de caracteres de consulta**, selecione **Armazenar em cache cada URL exclusiva**.</span><span class="sxs-lookup"><span data-stu-id="55be2-169">In the **Query string caching behavior** field, select **Cache every unique URL**.</span></span>
1. <span data-ttu-id="55be2-170">No grupo de campos **Compactação dinâmica**, selecione a opção **Habilitada**.</span><span class="sxs-lookup"><span data-stu-id="55be2-170">In the **Dynamic compression** field group, select the **Enabled** option.</span></span>

<span data-ttu-id="55be2-171">A ilustração a seguir mostra a caixa de diálogo **Adicionar uma regra** no Azure Front Door Service.</span><span class="sxs-lookup"><span data-stu-id="55be2-171">The following illustration shows the **Add a rule** dialog box in Azure Front Door Service.</span></span>

![Caixa de diálogo Adicionar uma regra](./media/CDN_CachingRule.png)

<span data-ttu-id="55be2-173">Depois que essa configuração inicial é implantada, é preciso adicionar seu domínio personalizado à configuração do Azure Front Door Service.</span><span class="sxs-lookup"><span data-stu-id="55be2-173">After this initial configuration is deployed, you must add your custom domain to the configuration for Azure Front Door Service.</span></span> <span data-ttu-id="55be2-174">Para adicionar o domínio personalizado (por exemplo, `www.fabrikam.com`), você deve configurar um nome canônico (CNAME) para o domínio.</span><span class="sxs-lookup"><span data-stu-id="55be2-174">To add the custom domain (for example, `www.fabrikam.com`), you must configure a Canonical Name (CNAME) for the domain.</span></span>

<span data-ttu-id="55be2-175">A ilustração a seguir mostra a caixa de diálogo **Configuração de CNAME** no Azure Front Door Service.</span><span class="sxs-lookup"><span data-stu-id="55be2-175">The following illustration shows the **CNAME configuration** dialog box in Azure Front Door Service.</span></span>

![Caixa de diálogo Configuração de CNAME](./media/CNAME_Configuration.png)

> [!NOTE]
> <span data-ttu-id="55be2-177">Se o domínio que você usará já estiver ativo, entre em contato com o suporte para habilitar esse domínio com o Azure Front Door Service para configurar um teste.</span><span class="sxs-lookup"><span data-stu-id="55be2-177">If the domain that you will use is already active and live, contact support to enable this domain with Azure Front Door Service to set up a test.</span></span>

<span data-ttu-id="55be2-178">É possível usar o Azure Front Door Service para gerenciar o certificado ou usar seu próprio certificado para o domínio personalizado.</span><span class="sxs-lookup"><span data-stu-id="55be2-178">You can use Azure Front Door Service to manage the certificate, or you can use your own certificate for the custom domain.</span></span>

<span data-ttu-id="55be2-179">A ilustração a seguir mostra a caixa de diálogo **HTTPS de domínio personalizado** no Azure Front Door Service.</span><span class="sxs-lookup"><span data-stu-id="55be2-179">The following illustration shows the **Custom Domain HTTPS** dialog box in Azure Front Door Service.</span></span>

![Caixa de diálogo HTTPS de domínio personalizado](./media/Custom_Domain_HTTPS.png)

<span data-ttu-id="55be2-181">Agora sua CDN deve estar configurada corretamente para poder ser usada com o site do Commerce.</span><span class="sxs-lookup"><span data-stu-id="55be2-181">Your CDN should now be correctly configured so that it can be used with your Commerce site.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="55be2-182">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="55be2-182">Additional resources</span></span>

[<span data-ttu-id="55be2-183">Configure seu nome de domínio</span><span class="sxs-lookup"><span data-stu-id="55be2-183">Configure your domain name</span></span>](configure-your-domain-name.md)

[<span data-ttu-id="55be2-184">Implantar um novo site de comércio eletrônico</span><span class="sxs-lookup"><span data-stu-id="55be2-184">Deploy a new e-Commerce site</span></span>](deploy-ecommerce-site.md)

[<span data-ttu-id="55be2-185">Criar um site de comércio eletrônico</span><span class="sxs-lookup"><span data-stu-id="55be2-185">Create an e-Commerce site</span></span>](create-ecommerce-site.md)

[<span data-ttu-id="55be2-186">Associar um site online a um canal</span><span class="sxs-lookup"><span data-stu-id="55be2-186">Associate an online site with a channel</span></span>](associate-site-online-store.md)

[<span data-ttu-id="55be2-187">Gerenciar arquivos robots.txt</span><span class="sxs-lookup"><span data-stu-id="55be2-187">Manage robots.txt files</span></span>](manage-robots-txt-files.md)

[<span data-ttu-id="55be2-188">Configurar páginas personalizadas para logons dos usuários</span><span class="sxs-lookup"><span data-stu-id="55be2-188">Set up custom pages for user logins</span></span>](custom-pages-user-logins.md)

[<span data-ttu-id="55be2-189">Habilitar detecção de lojas com base na localização</span><span class="sxs-lookup"><span data-stu-id="55be2-189">Enable location-based store detection</span></span>](enable-store-detection.md)
