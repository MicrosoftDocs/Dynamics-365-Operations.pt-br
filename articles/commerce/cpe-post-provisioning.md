---
title: Configurar um ambiente de visualização do Dynamics 365 Commerce
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
ms.openlocfilehash: d72caee25c03e8167b94dd387c7861f98bd0f4cb
ms.sourcegitcommit: 12b9d6f2dd24e52e46487748c848864909af6967
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/14/2020
ms.locfileid: "3057708"
---
# <a name="configure-a-dynamics-365-commerce-preview-environment"></a><span data-ttu-id="a41af-103">Configurar um ambiente de visualização do Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="a41af-103">Configure a Dynamics 365 Commerce preview environment</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="a41af-104">Este tópico explica como configurar um ambiente de visualização do Microsoft Dynamics 365 Commerce após ter sido provisionado.</span><span class="sxs-lookup"><span data-stu-id="a41af-104">This topic explains how to configure a Microsoft Dynamics 365 Commerce preview environment after it's provisioned.</span></span>

## <a name="overview"></a><span data-ttu-id="a41af-105">Visão geral</span><span class="sxs-lookup"><span data-stu-id="a41af-105">Overview</span></span>

<span data-ttu-id="a41af-106">Conclua os procedimentos neste tópico somente após o provisionamento do seu ambiente de visualização comercial.</span><span class="sxs-lookup"><span data-stu-id="a41af-106">Complete the procedures in this topic only after your Commerce preview environment has been provisioned.</span></span> <span data-ttu-id="a41af-107">Para obter informações sobre como provisionar seu ambiente de visualização do Commerce depois, consulte [Provisionar um ambiente de visualização do Commerce](provisioning-guide.md).</span><span class="sxs-lookup"><span data-stu-id="a41af-107">For information about how to provision your Commerce preview environment, see [Provision a Commerce preview environment](provisioning-guide.md).</span></span>

<span data-ttu-id="a41af-108">Depois que o ambiente de visualização comercial é provisionado de ponta a ponta, as etapas adicionais de configuração posteriores ao provisionamento devem ser concluídas para que você possa começar a avaliar o ambiente.</span><span class="sxs-lookup"><span data-stu-id="a41af-108">After your Commerce preview environment has been provisioned end to end, additional post-provisioning configuration steps must be completed before you can start to evaluate the environment.</span></span> <span data-ttu-id="a41af-109">Para concluir essas etapas, você deve usar Microsoft Dynamics Lifecycle Services (LCS) e Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="a41af-109">To complete these steps, you must use Microsoft Dynamics Lifecycle Services (LCS) and Dynamics 365 Commerce.</span></span>

## <a name="before-you-start"></a><span data-ttu-id="a41af-110">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="a41af-110">Before you start</span></span>

1. <span data-ttu-id="a41af-111">Entre no [Portal de LCS](https://lcs.dynamics.com).</span><span class="sxs-lookup"><span data-stu-id="a41af-111">Sign in to the [LCS portal](https://lcs.dynamics.com).</span></span>
1. <span data-ttu-id="a41af-112">Vá para seu projeto.</span><span class="sxs-lookup"><span data-stu-id="a41af-112">Go to your project.</span></span>
1. <span data-ttu-id="a41af-113">No menu superior, selecione **Ambientes hospedados na nuvem**.</span><span class="sxs-lookup"><span data-stu-id="a41af-113">On the top menu, select **Cloud-hosted environments**.</span></span>
1. <span data-ttu-id="a41af-114">Selecione seu ambiente na lista.</span><span class="sxs-lookup"><span data-stu-id="a41af-114">Select your environment in the list.</span></span>
1. <span data-ttu-id="a41af-115">Nas informações sobre o ambiente à direita, clique em **Detalhes completos**.</span><span class="sxs-lookup"><span data-stu-id="a41af-115">In the environment information on the right, select **Full details**.</span></span>
1. <span data-ttu-id="a41af-116">Selecione **Logon** para abrir um menu e depois selecione **Fazer logon no ambiente**.</span><span class="sxs-lookup"><span data-stu-id="a41af-116">Select **Login** to open a menu, and then select **Log on to environment**.</span></span>
1. <span data-ttu-id="a41af-117">Verifique se a entidade legal **USRT** está selecionada no canto superior direito.</span><span class="sxs-lookup"><span data-stu-id="a41af-117">Make sure that the **USRT** legal entity is selected in the upper-right corner.</span></span>

## <a name="configure-the-point-of-sale-in-lcs"></a><span data-ttu-id="a41af-118">Configurar o ponto de venda no LCS</span><span class="sxs-lookup"><span data-stu-id="a41af-118">Configure the point of sale in LCS</span></span>

### <a name="associate-a-worker-with-your-identity"></a><span data-ttu-id="a41af-119">Associar um trabalhador com sua identidade</span><span class="sxs-lookup"><span data-stu-id="a41af-119">Associate a worker with your identity</span></span>

<span data-ttu-id="a41af-120">Para associar um trabalhador à sua identidade no LCS, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="a41af-120">To associate a worker with your identity in LCS, follow these steps.</span></span>

1. <span data-ttu-id="a41af-121">Use o menu à esquerda, vá para **Módulos \> Varejo e comércio \> Funcionários \> Trabalhadores**.</span><span class="sxs-lookup"><span data-stu-id="a41af-121">Use the menu on the left to go to **Modules \> Retail and commerce \> Employees \> Workers**.</span></span>
1. <span data-ttu-id="a41af-122">Na lista, encontre e selecione o registro a seguir: **000713 - Andrew Collette**.</span><span class="sxs-lookup"><span data-stu-id="a41af-122">In the list, find and select the following record: **000713 - Andrew Collette**.</span></span>
1. <span data-ttu-id="a41af-123">No Painel de Ação, selecione **Varejo**.</span><span class="sxs-lookup"><span data-stu-id="a41af-123">On the Action Pane, select **Retail**.</span></span>
1. <span data-ttu-id="a41af-124">Selecione **Associar identidade existente**.</span><span class="sxs-lookup"><span data-stu-id="a41af-124">Select **Associate existing identity**.</span></span>
1. <span data-ttu-id="a41af-125">No campo **Email** à direita de **Pesquisar usando email**, insira seu endereço de email.</span><span class="sxs-lookup"><span data-stu-id="a41af-125">In the **Email** field to the right of **Search using email**, enter your email address.</span></span>
1. <span data-ttu-id="a41af-126">Selecione **Pesquisar**.</span><span class="sxs-lookup"><span data-stu-id="a41af-126">Select **Search**.</span></span>
1. <span data-ttu-id="a41af-127">Selecione o registro com seu nome.</span><span class="sxs-lookup"><span data-stu-id="a41af-127">Select the record that has your name.</span></span>
1. <span data-ttu-id="a41af-128">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="a41af-128">Select **OK**.</span></span>
1. <span data-ttu-id="a41af-129">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="a41af-129">Select **Save**.</span></span>

### <a name="activate-cloud-pos"></a><span data-ttu-id="a41af-130">Ativar PDV em nuvem</span><span class="sxs-lookup"><span data-stu-id="a41af-130">Activate Cloud POS</span></span>

<span data-ttu-id="a41af-131">Para ativar a nuvem POS no LCS, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="a41af-131">To activate Cloud POS in LCS, follow these steps.</span></span>

1. <span data-ttu-id="a41af-132">No menu superior, selecione **Ambientes hospedados na nuvem**.</span><span class="sxs-lookup"><span data-stu-id="a41af-132">On the top menu, select **Cloud-hosted environments**.</span></span>
1. <span data-ttu-id="a41af-133">Selecione seu ambiente na lista.</span><span class="sxs-lookup"><span data-stu-id="a41af-133">Select your environment in the list.</span></span>
1. <span data-ttu-id="a41af-134">Nas informações sobre o ambiente à direita, clique em **Detalhes completos**.</span><span class="sxs-lookup"><span data-stu-id="a41af-134">In the environment information on the right, select **Full details**.</span></span>
1. <span data-ttu-id="a41af-135">Selecione **Logon** para abrir um menu e selecione **Fazer logon no ponto de venda da nuvem** para abrir o ponto de venda (POS).</span><span class="sxs-lookup"><span data-stu-id="a41af-135">Select **Login** to open a menu, and then select **Log on to Cloud Point of Sale** to open the point of sale (POS).</span></span>
1. <span data-ttu-id="a41af-136">Selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="a41af-136">Select **Next**.</span></span>
1. <span data-ttu-id="a41af-137">Entre usando sua conta do Microsoft Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="a41af-137">Sign in by using your Microsoft Azure Active Directory (Azure AD) account.</span></span>
1. <span data-ttu-id="a41af-138">Em **Nome da loja**, selecione **São Francisco**.</span><span class="sxs-lookup"><span data-stu-id="a41af-138">Under **Store name**, select **San Francisco**.</span></span>
1. <span data-ttu-id="a41af-139">Selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="a41af-139">Select **Next**.</span></span>
1. <span data-ttu-id="a41af-140">Em **Registro e dispositivo**, selecione **SANFRAN-1**.</span><span class="sxs-lookup"><span data-stu-id="a41af-140">Under **Register and device**, select **SANFRAN-1**.</span></span>
1. <span data-ttu-id="a41af-141">Selecione **Ativar**.</span><span class="sxs-lookup"><span data-stu-id="a41af-141">Select **Activate**.</span></span> <span data-ttu-id="a41af-142">Você está desconectado e será levado para a página de entrada do POS.</span><span class="sxs-lookup"><span data-stu-id="a41af-142">You're signed out and taken to the POS sign-in page.</span></span>
1. <span data-ttu-id="a41af-143">Agora você pode fazer logon na experiência do Cloud POS usando o ID do operador **000713** e a senha **123**.</span><span class="sxs-lookup"><span data-stu-id="a41af-143">You can now sign in to the Cloud POS experience by using operator ID **000713** and password **123**.</span></span>

## <a name="set-up-your-site-in-commerce"></a><span data-ttu-id="a41af-144">Configurar seu site no Commerce</span><span class="sxs-lookup"><span data-stu-id="a41af-144">Set up your site in Commerce</span></span>

<span data-ttu-id="a41af-145">Para iniciar a configuração do seu site de visualização no Commerce, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="a41af-145">To start to set up your preview site in Commerce, follow these steps.</span></span>

1. <span data-ttu-id="a41af-146">Efetue login na ferramenta de gerenciamento de site usando a URL que você fez uma observação ao inicializar o comércio eletrônico durante o provisionamento (consulte [Inicializar comércio eletrônico](provisioning-guide.md#initialize-e-commerce)).</span><span class="sxs-lookup"><span data-stu-id="a41af-146">Sign in to the site management tool by using the URL that you made a note of when you initialized e-Commerce during provisioning (see [Initialize e-Commerce](provisioning-guide.md#initialize-e-commerce)).</span></span>
1. <span data-ttu-id="a41af-147">Selecione o site **Fabrikam** para abrir a caixa de diálogo de configuração do site.</span><span class="sxs-lookup"><span data-stu-id="a41af-147">Select the **Fabrikam** site to open the site setup dialog box.</span></span>
1. <span data-ttu-id="a41af-148">Selecione o domínio que você inseriu ao inicializar o comércio eletrônico.</span><span class="sxs-lookup"><span data-stu-id="a41af-148">Select the domain that you entered when you initialized e-Commerce.</span></span>
1. <span data-ttu-id="a41af-149">Selecione **Loja online estendida Fabrikam** como o canal padrão.</span><span class="sxs-lookup"><span data-stu-id="a41af-149">Select **Fabrikam extended online store** as the default channel.</span></span> <span data-ttu-id="a41af-150">(Certifique-se de selecionar a loja online **estendida**.)</span><span class="sxs-lookup"><span data-stu-id="a41af-150">(Make sure that you select the **extended** online store.)</span></span>
1. <span data-ttu-id="a41af-151">Selecione **en-us** como o idioma padrão.</span><span class="sxs-lookup"><span data-stu-id="a41af-151">Select **en-us** as the default language.</span></span>
1. <span data-ttu-id="a41af-152">Deixe o valor do campo **Caminho** como está.</span><span class="sxs-lookup"><span data-stu-id="a41af-152">Leave the value of the **Path** field as it is.</span></span>
1. <span data-ttu-id="a41af-153">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="a41af-153">Select **OK**.</span></span> <span data-ttu-id="a41af-154">A lista de páginas do site é exibida.</span><span class="sxs-lookup"><span data-stu-id="a41af-154">The list of pages on the site appears.</span></span>

## <a name="enable-jobs"></a><span data-ttu-id="a41af-155">Habilitar trabalhos</span><span class="sxs-lookup"><span data-stu-id="a41af-155">Enable jobs</span></span>

<span data-ttu-id="a41af-156">Para habilitar trabalhos no Commerce, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="a41af-156">To enable jobs in Commerce, follow these steps.</span></span>

1. <span data-ttu-id="a41af-157">Entre no ambiente (Matriz).</span><span class="sxs-lookup"><span data-stu-id="a41af-157">Sign in to the environment (HQ).</span></span>
1. <span data-ttu-id="a41af-158">Use o menu à esquerda, vá para **Varejo e comércio \> Consultas e relatórios \> Trabalhos em lotes**.</span><span class="sxs-lookup"><span data-stu-id="a41af-158">Use the menu on the left to go to **Retail and commerce \> Inquiries and reports \> Batch jobs**.</span></span>

    <span data-ttu-id="a41af-159">As etapas restantes deste procedimento devem ser concluídas para cada um dos seguintes trabalhos:</span><span class="sxs-lookup"><span data-stu-id="a41af-159">The remaining steps of this procedure must be completed for each of the following jobs:</span></span>

    * <span data-ttu-id="a41af-160">Processar notificação por email da ordem de varejo</span><span class="sxs-lookup"><span data-stu-id="a41af-160">Process retail order email notification</span></span>
    * <span data-ttu-id="a41af-161">Disponibilidade do produto</span><span class="sxs-lookup"><span data-stu-id="a41af-161">Product availability</span></span>
    * <span data-ttu-id="a41af-162">P-0001</span><span class="sxs-lookup"><span data-stu-id="a41af-162">P-0001</span></span>
    * <span data-ttu-id="a41af-163">Sincronizar trabalho de ordens</span><span class="sxs-lookup"><span data-stu-id="a41af-163">Synchronize orders job</span></span>

1. <span data-ttu-id="a41af-164">Use o Filtro Rápido para procurar o trabalho pelo nome.</span><span class="sxs-lookup"><span data-stu-id="a41af-164">Use the Quick Filter to search for the job by name.</span></span>
1. <span data-ttu-id="a41af-165">Se o status do trabalho for **Retido**, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="a41af-165">If the status of the job is **Withhold**, follow these steps:</span></span>

    1. <span data-ttu-id="a41af-166">Selecione o registro.</span><span class="sxs-lookup"><span data-stu-id="a41af-166">Select the record.</span></span>
    1. <span data-ttu-id="a41af-167">No Painel de Ação, na guia **Trabalho em lotes**, selecione **Alterar status**.</span><span class="sxs-lookup"><span data-stu-id="a41af-167">On the Action Pane, on **Batch job** tab, select **Change status**.</span></span>
    1. <span data-ttu-id="a41af-168">Selecione **Aguardando** e, depois, **OK**.</span><span class="sxs-lookup"><span data-stu-id="a41af-168">Select **Waiting**, and then select **OK**.</span></span>

### <a name="run-full-data-synchronization"></a><span data-ttu-id="a41af-169">Executar sincronização de dados completa</span><span class="sxs-lookup"><span data-stu-id="a41af-169">Run full data synchronization</span></span>

<span data-ttu-id="a41af-170">Para executar a sincronização completa dos dados no Commerce, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="a41af-170">To run full data synchronization in Commerce, follow these steps.</span></span>

1. <span data-ttu-id="a41af-171">Use o menu à esquerda para ir para **Módulos \> Varejo e comércio \> configuração da Sede \> Agendador do Retail \> Banco de dados do canal**.</span><span class="sxs-lookup"><span data-stu-id="a41af-171">Use the menu on the left to go to **Modules \> Retail and commerce \> Headquarters setup \> Retail scheduler \> Channel database**.</span></span>
1. <span data-ttu-id="a41af-172">Na lista à esquerda, o canal **Padrão** é selecionado.</span><span class="sxs-lookup"><span data-stu-id="a41af-172">In the list on the left, the **Default** channel is selected.</span></span> <span data-ttu-id="a41af-173">Selecione o outro canal disponível.</span><span class="sxs-lookup"><span data-stu-id="a41af-173">Select the other available channel.</span></span> <span data-ttu-id="a41af-174">Esse canal é nomeado **scXXXXXXXXX**.</span><span class="sxs-lookup"><span data-stu-id="a41af-174">This channel is named **scXXXXXXXXX**.</span></span>
1. <span data-ttu-id="a41af-175">No Painel de Ação, selecione **Sincronização de dados completa**.</span><span class="sxs-lookup"><span data-stu-id="a41af-175">On the Action Pane, select **Full data sync**.</span></span>
1. <span data-ttu-id="a41af-176">Digite **9999** como a agenda de distribuição.</span><span class="sxs-lookup"><span data-stu-id="a41af-176">Enter **9999** as the distribution schedule.</span></span>
1. <span data-ttu-id="a41af-177">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="a41af-177">Select **OK**.</span></span>
1. <span data-ttu-id="a41af-178">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="a41af-178">Select **OK**.</span></span>

### <a name="test-credit-card-information-to-do-test-purchases"></a><span data-ttu-id="a41af-179">Testar informações do cartão de crédito para testar compras</span><span class="sxs-lookup"><span data-stu-id="a41af-179">Test credit card information to do test purchases</span></span>

<span data-ttu-id="a41af-180">Para realizar transações de teste no site, você pode usar as informações do cartão de crédito de teste a seguir:</span><span class="sxs-lookup"><span data-stu-id="a41af-180">To perform test transactions on the site, you can use the following test credit card information:</span></span>

- <span data-ttu-id="a41af-181">**Número do cartão:** 4111-1111-1111-1111</span><span class="sxs-lookup"><span data-stu-id="a41af-181">**Card number:** 4111-1111-1111-1111</span></span>
- <span data-ttu-id="a41af-182">**Data de vencimento:** 20/10</span><span class="sxs-lookup"><span data-stu-id="a41af-182">**Expiration date:** 10/20</span></span>
- <span data-ttu-id="a41af-183">**Código do valor de verificação do cartão (CVV):** 737</span><span class="sxs-lookup"><span data-stu-id="a41af-183">**Card verification value (CVV) code:** 737</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a41af-184">Nunca, em qualquer circunstância, tente usar as informações reais do cartão de crédito no local do teste.</span><span class="sxs-lookup"><span data-stu-id="a41af-184">Never, under any circumstances, try to use actual credit card information on the test site.</span></span>

## <a name="next-steps"></a><span data-ttu-id="a41af-185">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="a41af-185">Next steps</span></span>

<span data-ttu-id="a41af-186">Depois que as etapas de provisionamento e configuração forem concluídas, você estará pronto para avaliar seu ambiente de visualização.</span><span class="sxs-lookup"><span data-stu-id="a41af-186">After the provisioning and configuration steps are completed, you're ready to evaluate your preview environment.</span></span> <span data-ttu-id="a41af-187">Use a URL da ferramenta de gerenciamento de site do Commerce para ir para a experiência de criação de páginas.</span><span class="sxs-lookup"><span data-stu-id="a41af-187">Use the URL of the Commerce site management tool to go to the authoring experience.</span></span> <span data-ttu-id="a41af-188">Use a URL da ferramenta de gerenciamento de site do Commerce para ir para a experiência de site do cliente de varejo.</span><span class="sxs-lookup"><span data-stu-id="a41af-188">Use the URL of the Commerce site to go to the retail customer site experience.</span></span>

<span data-ttu-id="a41af-189">Para configurar recursos opcionais de seu ambiente de visualização do Commerce, consulte [Configurar recursos opcionais para um ambiente de visualização do Commerce](cpe-optional-features.md).</span><span class="sxs-lookup"><span data-stu-id="a41af-189">To configure optional features for your Commerce preview environment, see [Configure optional features for a Commerce preview environment](cpe-optional-features.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="a41af-190">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="a41af-190">Additional resources</span></span>

[<span data-ttu-id="a41af-191">Visão geral do ambiente de visualização do Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="a41af-191">Dynamics 365 Commerce preview environment overview</span></span>](cpe-overview.md)

[<span data-ttu-id="a41af-192">Provisionar um ambiente de visualização do Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="a41af-192">Provision a Dynamics 365 Commerce preview environment</span></span>](provisioning-guide.md)

[<span data-ttu-id="a41af-193">Configurar recursos opcionais para um ambiente de visualização do Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="a41af-193">Configure optional features for a Dynamics 365 Commerce preview environment</span></span>](cpe-optional-features.md)

[<span data-ttu-id="a41af-194">Perguntas frequentes do ambiente de visualização do Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="a41af-194">Dynamics 365 Commerce preview environment FAQ</span></span>](cpe-faq.md)

[<span data-ttu-id="a41af-195">Microsoft Lifecycle Services (LCS)</span><span class="sxs-lookup"><span data-stu-id="a41af-195">Microsoft Lifecycle Services (LCS)</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/lifecycle-services/lcs-user-guide)

[<span data-ttu-id="a41af-196">Retail Cloud Scale Unit (RCSU)</span><span class="sxs-lookup"><span data-stu-id="a41af-196">Retail Cloud Scale Unit (RCSU)</span></span>](https://docs.microsoft.com/business-applications-release-notes/october18/dynamics365-retail/retail-cloud-scale-unit)

[<span data-ttu-id="a41af-197">Portal do Microsoft Azure</span><span class="sxs-lookup"><span data-stu-id="a41af-197">Microsoft Azure portal</span></span>](https://azure.microsoft.com/features/azure-portal)

[<span data-ttu-id="a41af-198">Site do Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="a41af-198">Dynamics 365 Commerce website</span></span>](https://aka.ms/Dynamics365CommerceWebsite)
