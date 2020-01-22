---
title: Configurar um ambiente de visualização de comércio
description: Este tópico explica como configurar um ambiente de visualização do Microsoft Dynamics 365 Commerce após ter sido provisionado.
author: psimolin
manager: annbe
ms.date: 12/10/2019
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
ms.author: psimolin
ms.search.validFrom: 2019-12-10
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: f19d03f3f2f5a9f6f7ba08b682277e4e3b764d10
ms.sourcegitcommit: 610d5c3efadbaf11752b46f24680af619bcd70a6
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2019
ms.locfileid: "2906130"
---
# <a name="configure-a-commerce-preview-environment"></a><span data-ttu-id="684d1-103">Configurar um ambiente de visualização de comércio</span><span class="sxs-lookup"><span data-stu-id="684d1-103">Configure a Commerce preview environment</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="684d1-104">Este tópico explica como configurar um ambiente de visualização do Microsoft Dynamics 365 Commerce após ter sido provisionado.</span><span class="sxs-lookup"><span data-stu-id="684d1-104">This topic explains how to configure a Microsoft Dynamics 365 Commerce preview environment after it's provisioned.</span></span>

## <a name="overview"></a><span data-ttu-id="684d1-105">Visão geral</span><span class="sxs-lookup"><span data-stu-id="684d1-105">Overview</span></span>

<span data-ttu-id="684d1-106">Conclua os procedimentos neste tópico somente após o provisionamento do seu ambiente de visualização comercial.</span><span class="sxs-lookup"><span data-stu-id="684d1-106">Complete the procedures in this topic only after your Commerce preview environment has been provisioned.</span></span> <span data-ttu-id="684d1-107">Para obter informações sobre como provisionar seu ambiente de visualização do Commerce depois, consulte [Provisionar um ambiente de visualização do Commerce](provisioning-guide.md).</span><span class="sxs-lookup"><span data-stu-id="684d1-107">For information about how to provision your Commerce preview environment, see [Provision a Commerce preview environment](provisioning-guide.md).</span></span>

<span data-ttu-id="684d1-108">Depois que o ambiente de visualização comercial é provisionado de ponta a ponta, as etapas adicionais de configuração posteriores ao provisionamento devem ser concluídas para que você possa começar a avaliar o ambiente.</span><span class="sxs-lookup"><span data-stu-id="684d1-108">After your Commerce preview environment has been provisioned end to end, additional post-provisioning configuration steps must be completed before you can start to evaluate the environment.</span></span> <span data-ttu-id="684d1-109">Para concluir essas etapas, você deve usar Microsoft Dynamics Lifecycle Services (LCS), Dynamics 365 Commerce e Dynamics 365 Retail.</span><span class="sxs-lookup"><span data-stu-id="684d1-109">To complete these steps, you must use Microsoft Dynamics Lifecycle Services (LCS), Dynamics 365 Commerce, and Dynamics 365 Retail.</span></span>

## <a name="before-you-start"></a><span data-ttu-id="684d1-110">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="684d1-110">Before you start</span></span>

1. <span data-ttu-id="684d1-111">Entre no [Portal de LCS](https://lcs.dynamics.com).</span><span class="sxs-lookup"><span data-stu-id="684d1-111">Sign in to the [LCS portal](https://lcs.dynamics.com).</span></span>
1. <span data-ttu-id="684d1-112">Vá para seu projeto.</span><span class="sxs-lookup"><span data-stu-id="684d1-112">Go to your project.</span></span>
1. <span data-ttu-id="684d1-113">No menu superior, selecione **Ambientes hospedados na nuvem**.</span><span class="sxs-lookup"><span data-stu-id="684d1-113">On the top menu, select **Cloud-hosted environments**.</span></span>
1. <span data-ttu-id="684d1-114">Selecione seu ambiente na lista.</span><span class="sxs-lookup"><span data-stu-id="684d1-114">Select your environment in the list.</span></span>
1. <span data-ttu-id="684d1-115">Nas informações sobre o ambiente à direita, clique em **Detalhes completos**.</span><span class="sxs-lookup"><span data-stu-id="684d1-115">In the environment information on the right, select **Full details**.</span></span>
1. <span data-ttu-id="684d1-116">Selecione **Logon** para abrir um menu e depois selecione **Fazer logon no ambiente**.</span><span class="sxs-lookup"><span data-stu-id="684d1-116">Select **Login** to open a menu, and then select **Log on to environment**.</span></span>
1. <span data-ttu-id="684d1-117">Verifique se a entidade legal **USRT** está selecionada no canto superior direito.</span><span class="sxs-lookup"><span data-stu-id="684d1-117">Make sure that the **USRT** legal entity is selected in the upper-right corner.</span></span>

## <a name="configure-the-point-of-sale-in-lcs"></a><span data-ttu-id="684d1-118">Configurar o ponto de venda no LCS</span><span class="sxs-lookup"><span data-stu-id="684d1-118">Configure the point of sale in LCS</span></span>

### <a name="associate-a-worker-with-your-identity"></a><span data-ttu-id="684d1-119">Associar um trabalhador com sua identidade</span><span class="sxs-lookup"><span data-stu-id="684d1-119">Associate a worker with your identity</span></span>

<span data-ttu-id="684d1-120">Para associar um trabalhador à sua identidade no LCS, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="684d1-120">To associate a worker with your identity in LCS, follow these steps.</span></span>

1. <span data-ttu-id="684d1-121">Use o menu à esquerda, vá para **Módulos \> Varejo \> Funcionários \> Trabalhadores**.</span><span class="sxs-lookup"><span data-stu-id="684d1-121">Use the menu on the left to go to **Modules \> Retail \> Employees \> Workers**.</span></span>
1. <span data-ttu-id="684d1-122">Na lista, encontre e selecione o registro a seguir: **000713 - Andrew Collette**.</span><span class="sxs-lookup"><span data-stu-id="684d1-122">In the list, find and select the following record: **000713 - Andrew Collette**.</span></span>
1. <span data-ttu-id="684d1-123">No Painel de Ação, selecione **Varejo**.</span><span class="sxs-lookup"><span data-stu-id="684d1-123">On the Action Pane, select **Retail**.</span></span>
1. <span data-ttu-id="684d1-124">Selecione **Associar identidade existente**.</span><span class="sxs-lookup"><span data-stu-id="684d1-124">Select **Associate existing identity**.</span></span>
1. <span data-ttu-id="684d1-125">No campo **Email** à direita de **Pesquisar usando email**, insira seu endereço de email.</span><span class="sxs-lookup"><span data-stu-id="684d1-125">In the **Email** field to the right of **Search using email**, enter your email address.</span></span>
1. <span data-ttu-id="684d1-126">Selecione **Pesquisar**.</span><span class="sxs-lookup"><span data-stu-id="684d1-126">Select **Search**.</span></span>
1. <span data-ttu-id="684d1-127">Selecione o registro com seu nome.</span><span class="sxs-lookup"><span data-stu-id="684d1-127">Select the record that has your name.</span></span>
1. <span data-ttu-id="684d1-128">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="684d1-128">Select **OK**.</span></span>
1. <span data-ttu-id="684d1-129">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="684d1-129">Select **Save**.</span></span>

### <a name="activate-cloud-pos"></a><span data-ttu-id="684d1-130">Ativar PDV em nuvem</span><span class="sxs-lookup"><span data-stu-id="684d1-130">Activate Cloud POS</span></span>

<span data-ttu-id="684d1-131">Para ativar a nuvem POS no LCS, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="684d1-131">To activate Cloud POS in LCS, follow these steps.</span></span>

1. <span data-ttu-id="684d1-132">No menu superior, selecione **Ambientes hospedados na nuvem**.</span><span class="sxs-lookup"><span data-stu-id="684d1-132">On the top menu, select **Cloud-hosted environments**.</span></span>
1. <span data-ttu-id="684d1-133">Selecione seu ambiente na lista.</span><span class="sxs-lookup"><span data-stu-id="684d1-133">Select your environment in the list.</span></span>
1. <span data-ttu-id="684d1-134">Nas informações sobre o ambiente à direita, clique em **Detalhes completos**.</span><span class="sxs-lookup"><span data-stu-id="684d1-134">In the environment information on the right, select **Full details**.</span></span>
1. <span data-ttu-id="684d1-135">Selecione **Logon** para abrir um menu e selecione **Fazer logon no ponto de venda da nuvem** para abrir o ponto de venda (POS).</span><span class="sxs-lookup"><span data-stu-id="684d1-135">Select **Login** to open a menu, and then select **Log on to Cloud Point of Sale** to open the point of sale (POS).</span></span>
1. <span data-ttu-id="684d1-136">Selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="684d1-136">Select **Next**.</span></span>
1. <span data-ttu-id="684d1-137">Entre usando sua conta do Microsoft Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="684d1-137">Sign in by using your Microsoft Azure Active Directory (Azure AD) account.</span></span>
1. <span data-ttu-id="684d1-138">Em **Nome da loja**, selecione **São Francisco**.</span><span class="sxs-lookup"><span data-stu-id="684d1-138">Under **Store name**, select **San Francisco**.</span></span>
1. <span data-ttu-id="684d1-139">Selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="684d1-139">Select **Next**.</span></span>
1. <span data-ttu-id="684d1-140">Em **Registro e dispositivo**, selecione **SANFRAN-1**.</span><span class="sxs-lookup"><span data-stu-id="684d1-140">Under **Register and device**, select **SANFRAN-1**.</span></span>
1. <span data-ttu-id="684d1-141">Selecione **Ativar**.</span><span class="sxs-lookup"><span data-stu-id="684d1-141">Select **Activate**.</span></span> <span data-ttu-id="684d1-142">Você está desconectado e será levado para a página de entrada do POS.</span><span class="sxs-lookup"><span data-stu-id="684d1-142">You're signed out and taken to the POS sign-in page.</span></span>
1. <span data-ttu-id="684d1-143">Agora você pode fazer logon na experiência do Cloud POS usando o ID do operador **000713** e a senha **123**.</span><span class="sxs-lookup"><span data-stu-id="684d1-143">You can now sign in to the Cloud POS experience by using operator ID **000713** and password **123**.</span></span>

## <a name="set-up-your-site-in-commerce"></a><span data-ttu-id="684d1-144">Configurar seu site no Commerce</span><span class="sxs-lookup"><span data-stu-id="684d1-144">Set up your site in Commerce</span></span>

<span data-ttu-id="684d1-145">Para iniciar a configuração do seu site de visualização no Commerce, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="684d1-145">To start to set up your preview site in Commerce, follow these steps.</span></span>

1. <span data-ttu-id="684d1-146">Efetue login na ferramenta de gerenciamento de site usando a URL que você fez uma observação ao inicializar o comércio eletrônico durante o provisionamento (consulte [Inicializar comércio eletrônico](provisioning-guide.md#initialize-e-commerce)).</span><span class="sxs-lookup"><span data-stu-id="684d1-146">Sign in to the site management tool by using the URL that you made a note of when you initialized e-Commerce during provisioning (see [Initialize e-Commerce](provisioning-guide.md#initialize-e-commerce)).</span></span>
1. <span data-ttu-id="684d1-147">Selecione o site **Fabrikam** para abrir a caixa de diálogo de configuração do site.</span><span class="sxs-lookup"><span data-stu-id="684d1-147">Select the **Fabrikam** site to open the site setup dialog box.</span></span>
1. <span data-ttu-id="684d1-148">Selecione o domínio que você inseriu ao inicializar o comércio eletrônico.</span><span class="sxs-lookup"><span data-stu-id="684d1-148">Select the domain that you entered when you initialized e-Commerce.</span></span>
1. <span data-ttu-id="684d1-149">Selecione **Loja online estendida Fabrikam** como o canal padrão.</span><span class="sxs-lookup"><span data-stu-id="684d1-149">Select **Fabrikam extended online store** as the default channel.</span></span> <span data-ttu-id="684d1-150">(Certifique-se de selecionar a loja online **estendida**.)</span><span class="sxs-lookup"><span data-stu-id="684d1-150">(Make sure that you select the **extended** online store.)</span></span>
1. <span data-ttu-id="684d1-151">Selecione **en-us** como o idioma padrão.</span><span class="sxs-lookup"><span data-stu-id="684d1-151">Select **en-us** as the default language.</span></span>
1. <span data-ttu-id="684d1-152">Deixe o valor do campo **Caminho** como está.</span><span class="sxs-lookup"><span data-stu-id="684d1-152">Leave the value of the **Path** field as it is.</span></span>
1. <span data-ttu-id="684d1-153">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="684d1-153">Select **OK**.</span></span> <span data-ttu-id="684d1-154">A lista de páginas do site é exibida.</span><span class="sxs-lookup"><span data-stu-id="684d1-154">The list of pages on the site appears.</span></span>

## <a name="enable-jobs-in-retail"></a><span data-ttu-id="684d1-155">Habilitar trabalhos no Varejo</span><span class="sxs-lookup"><span data-stu-id="684d1-155">Enable jobs in Retail</span></span>

<span data-ttu-id="684d1-156">Para habilitar trabalhos em Varejo, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="684d1-156">To enable jobs in Retail, follow these steps.</span></span>

1. <span data-ttu-id="684d1-157">Entre no ambiente (Matriz).</span><span class="sxs-lookup"><span data-stu-id="684d1-157">Sign in to the environment (HQ).</span></span>
1. <span data-ttu-id="684d1-158">Use o menu à esquerda, vá para **Varejo \> Consultas e relatórios \> Trabalhos em lotes**.</span><span class="sxs-lookup"><span data-stu-id="684d1-158">Use the menu on the left to go to **Retail \> Inquiries and reports \> Batch jobs**.</span></span>

    <span data-ttu-id="684d1-159">As etapas restantes deste procedimento devem ser concluídas para cada um dos seguintes trabalhos:</span><span class="sxs-lookup"><span data-stu-id="684d1-159">The remaining steps of this procedure must be completed for each of the following jobs:</span></span>

    * <span data-ttu-id="684d1-160">Processar notificação por email da ordem de varejo</span><span class="sxs-lookup"><span data-stu-id="684d1-160">Process retail order email notification</span></span>
    * <span data-ttu-id="684d1-161">Disponibilidade do produto</span><span class="sxs-lookup"><span data-stu-id="684d1-161">Product availability</span></span>
    * <span data-ttu-id="684d1-162">P-0001</span><span class="sxs-lookup"><span data-stu-id="684d1-162">P-0001</span></span>
    * <span data-ttu-id="684d1-163">Sincronizar trabalho de ordens</span><span class="sxs-lookup"><span data-stu-id="684d1-163">Synchronize orders job</span></span>

1. <span data-ttu-id="684d1-164">Use o Filtro Rápido para procurar o trabalho pelo nome.</span><span class="sxs-lookup"><span data-stu-id="684d1-164">Use the Quick Filter to search for the job by name.</span></span>
1. <span data-ttu-id="684d1-165">Se o status do trabalho for **Retido**, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="684d1-165">If the status of the job is **Withhold**, follow these steps:</span></span>

    1. <span data-ttu-id="684d1-166">Selecione o registro.</span><span class="sxs-lookup"><span data-stu-id="684d1-166">Select the record.</span></span>
    1. <span data-ttu-id="684d1-167">No Painel de Ação, na guia **Trabalho em lotes**, selecione **Alterar status**.</span><span class="sxs-lookup"><span data-stu-id="684d1-167">On the Action Pane, on **Batch job** tab, select **Change status**.</span></span>
    1. <span data-ttu-id="684d1-168">Selecione **Aguardando** e, depois, **OK**.</span><span class="sxs-lookup"><span data-stu-id="684d1-168">Select **Waiting**, and then select **OK**.</span></span>

### <a name="run-full-data-synchronization-in-retail"></a><span data-ttu-id="684d1-169">Executar sincronização completa de dados no varejo</span><span class="sxs-lookup"><span data-stu-id="684d1-169">Run full data synchronization in Retail</span></span>

<span data-ttu-id="684d1-170">Para executar a sincronização completa dos dados no Varejo, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="684d1-170">To run full data synchronization in Retail, follow these steps.</span></span>

1. <span data-ttu-id="684d1-171">Use o menu à esquerda para ir para **Módulos \> Varejo \> configuração da Sede \> agendador do Retail \> Banco de dados do canal**.</span><span class="sxs-lookup"><span data-stu-id="684d1-171">Use the menu on the left to go to **Modules \> Retail \> Headquarters setup \> Retail scheduler \> Channel database**.</span></span>
1. <span data-ttu-id="684d1-172">Na lista à esquerda, o canal **Padrão** é selecionado.</span><span class="sxs-lookup"><span data-stu-id="684d1-172">In the list on the left, the **Default** channel is selected.</span></span> <span data-ttu-id="684d1-173">Selecione o outro canal disponível.</span><span class="sxs-lookup"><span data-stu-id="684d1-173">Select the other available channel.</span></span> <span data-ttu-id="684d1-174">Esse canal é nomeado **scXXXXXXXXX**.</span><span class="sxs-lookup"><span data-stu-id="684d1-174">This channel is named **scXXXXXXXXX**.</span></span>
1. <span data-ttu-id="684d1-175">No Painel de Ação, selecione **Sincronização de dados completa**.</span><span class="sxs-lookup"><span data-stu-id="684d1-175">On the Action Pane, select **Full data sync**.</span></span>
1. <span data-ttu-id="684d1-176">Digite **9999** como a agenda de distribuição.</span><span class="sxs-lookup"><span data-stu-id="684d1-176">Enter **9999** as the distribution schedule.</span></span>
1. <span data-ttu-id="684d1-177">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="684d1-177">Select **OK**.</span></span>
1. <span data-ttu-id="684d1-178">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="684d1-178">Select **OK**.</span></span>

### <a name="test-credit-card-information-to-do-test-purchases"></a><span data-ttu-id="684d1-179">Testar informações do cartão de crédito para testar compras</span><span class="sxs-lookup"><span data-stu-id="684d1-179">Test credit card information to do test purchases</span></span>

<span data-ttu-id="684d1-180">Para realizar transações de teste no site, você pode usar as informações do cartão de crédito de teste a seguir:</span><span class="sxs-lookup"><span data-stu-id="684d1-180">To perform test transactions on the site, you can use the following test credit card information:</span></span>

- <span data-ttu-id="684d1-181">**Número do cartão:** 4111-1111-1111-1111</span><span class="sxs-lookup"><span data-stu-id="684d1-181">**Card number:** 4111-1111-1111-1111</span></span>
- <span data-ttu-id="684d1-182">**Data de vencimento:** 20/10</span><span class="sxs-lookup"><span data-stu-id="684d1-182">**Expiration date:** 10/20</span></span>
- <span data-ttu-id="684d1-183">**Código do valor de verificação do cartão (CVV):** 737</span><span class="sxs-lookup"><span data-stu-id="684d1-183">**Card verification value (CVV) code:** 737</span></span>

> [!IMPORTANT]
> <span data-ttu-id="684d1-184">Nunca, em qualquer circunstância, tente usar as informações reais do cartão de crédito no local do teste.</span><span class="sxs-lookup"><span data-stu-id="684d1-184">Never, under any circumstances, try to use actual credit card information on the test site.</span></span>

## <a name="next-steps"></a><span data-ttu-id="684d1-185">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="684d1-185">Next steps</span></span>

<span data-ttu-id="684d1-186">Depois que as etapas de provisionamento e configuração forem concluídas, você estará pronto para avaliar seu ambiente de visualização.</span><span class="sxs-lookup"><span data-stu-id="684d1-186">After the provisioning and configuration steps are completed, you're ready to evaluate your preview environment.</span></span> <span data-ttu-id="684d1-187">Use a URL da ferramenta de gerenciamento de site do Commerce para ir para a experiência de criação de páginas.</span><span class="sxs-lookup"><span data-stu-id="684d1-187">Use the URL of the Commerce site management tool to go to the authoring experience.</span></span> <span data-ttu-id="684d1-188">Use a URL da ferramenta de gerenciamento de site do Commerce para ir para a experiência de site do cliente de varejo.</span><span class="sxs-lookup"><span data-stu-id="684d1-188">Use the URL of the Commerce site to go to the retail customer site experience.</span></span>

<span data-ttu-id="684d1-189">Para configurar recursos opcionais de seu ambiente de visualização do Commerce, consulte [Configurar recursos opcionais para um ambiente de visualização do Commerce](cpe-optional-features.md).</span><span class="sxs-lookup"><span data-stu-id="684d1-189">To configure optional features for your Commerce preview environment, see [Configure optional features for a Commerce preview environment](cpe-optional-features.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="684d1-190">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="684d1-190">Additional resources</span></span>

[<span data-ttu-id="684d1-191">Visão geral do ambiente de visualização do Commerce</span><span class="sxs-lookup"><span data-stu-id="684d1-191">Commerce preview environment overview</span></span>](cpe-overview.md)

[<span data-ttu-id="684d1-192">Provisionar um ambiente de visualização do Commerce</span><span class="sxs-lookup"><span data-stu-id="684d1-192">Provision a Commerce preview environment</span></span>](provisioning-guide.md)

[<span data-ttu-id="684d1-193">Configurar recursos opcionais para um ambiente de visualização do Commerce</span><span class="sxs-lookup"><span data-stu-id="684d1-193">Configure optional features for a Commerce preview environment</span></span>](cpe-optional-features.md)

[<span data-ttu-id="684d1-194">Perguntas frequentes do ambiente de visualização do Commerce</span><span class="sxs-lookup"><span data-stu-id="684d1-194">Commerce preview environment FAQ</span></span>](cpe-faq.md)

[<span data-ttu-id="684d1-195">Microsoft Lifecycle Services (LCS)</span><span class="sxs-lookup"><span data-stu-id="684d1-195">Microsoft Lifecycle Services (LCS)</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/lifecycle-services/lcs-user-guide)

[<span data-ttu-id="684d1-196">Retail Cloud Scale Unit (RCSU)</span><span class="sxs-lookup"><span data-stu-id="684d1-196">Retail Cloud Scale Unit (RCSU)</span></span>](https://docs.microsoft.com/business-applications-release-notes/october18/dynamics365-retail/retail-cloud-scale-unit)

[<span data-ttu-id="684d1-197">Portal do Microsoft Azure</span><span class="sxs-lookup"><span data-stu-id="684d1-197">Microsoft Azure portal</span></span>](https://azure.microsoft.com/features/azure-portal)

[<span data-ttu-id="684d1-198">Site do Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="684d1-198">Dynamics 365 Commerce website</span></span>](https://aka.ms/Dynamics365CommerceWebsite)

[<span data-ttu-id="684d1-199">Recursos de ajuda do Dynamics 365 Retail</span><span class="sxs-lookup"><span data-stu-id="684d1-199">Help resources for Dynamics 365 Retail</span></span>](../retail/index.md)
