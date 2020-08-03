---
title: Configurar um ambiente de avaliação do Dynamics 365 Commerce
description: Este tópico explica como configurar um ambiente de avaliação do Microsoft Dynamics 365 Commerce após ter sido provisionado.
author: psimolin
manager: annbe
ms.date: 07/16/2020
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
ms.openlocfilehash: 6a1ae960f0f530104af7bdea9a8fcb78b01571f5
ms.sourcegitcommit: 5175e3fae432016246244cf70fe05465f43de88c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/17/2020
ms.locfileid: "3599715"
---
# <a name="configure-a-dynamics-365-commerce-evaluation-environment"></a><span data-ttu-id="e7430-103">Configurar um ambiente de avaliação do Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="e7430-103">Configure a Dynamics 365 Commerce evaluation environment</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="e7430-104">Este tópico explica como configurar um ambiente de avaliação do Microsoft Dynamics 365 Commerce após ter sido provisionado.</span><span class="sxs-lookup"><span data-stu-id="e7430-104">This topic explains how to configure a Microsoft Dynamics 365 Commerce evaluation environment after it's provisioned.</span></span>

## <a name="overview"></a><span data-ttu-id="e7430-105">Visão Geral</span><span class="sxs-lookup"><span data-stu-id="e7430-105">Overview</span></span>

<span data-ttu-id="e7430-106">Conclua os procedimentos neste tópico somente após o provisionamento do seu ambiente de avaliação do Commerce.</span><span class="sxs-lookup"><span data-stu-id="e7430-106">Complete the procedures in this topic only after your Commerce evaluation environment has been provisioned.</span></span> <span data-ttu-id="e7430-107">Para obter informações sobre como provisionar seu ambiente de avaliação do Commerce, consulte [Provisionar um ambiente de avaliação do Commerce](provisioning-guide.md).</span><span class="sxs-lookup"><span data-stu-id="e7430-107">For information about how to provision your Commerce evaluation environment, see [Provision a Commerce evaluation environment](provisioning-guide.md).</span></span>

<span data-ttu-id="e7430-108">Depois que o ambiente de avaliação do Commerce for provisionado de ponta a ponta, as etapas adicionais de configuração de pós-provisionamento deverão ser concluídas para que você possa começar a avaliar o ambiente.</span><span class="sxs-lookup"><span data-stu-id="e7430-108">After your Commerce evaluation environment has been provisioned end to end, additional post-provisioning configuration steps must be completed before you can start to evaluate the environment.</span></span> <span data-ttu-id="e7430-109">Para concluir essas etapas, você deve usar Microsoft Dynamics Lifecycle Services (LCS) e Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="e7430-109">To complete these steps, you must use Microsoft Dynamics Lifecycle Services (LCS) and Dynamics 365 Commerce.</span></span>

## <a name="before-you-start"></a><span data-ttu-id="e7430-110">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="e7430-110">Before you start</span></span>

1. <span data-ttu-id="e7430-111">Entre no [Portal de LCS](https://lcs.dynamics.com).</span><span class="sxs-lookup"><span data-stu-id="e7430-111">Sign in to the [LCS portal](https://lcs.dynamics.com).</span></span>
1. <span data-ttu-id="e7430-112">Vá para seu projeto.</span><span class="sxs-lookup"><span data-stu-id="e7430-112">Go to your project.</span></span>
1. <span data-ttu-id="e7430-113">No menu superior, selecione **Ambientes hospedados na nuvem**.</span><span class="sxs-lookup"><span data-stu-id="e7430-113">On the top menu, select **Cloud-hosted environments**.</span></span>
1. <span data-ttu-id="e7430-114">Selecione seu ambiente na lista.</span><span class="sxs-lookup"><span data-stu-id="e7430-114">Select your environment in the list.</span></span>
1. <span data-ttu-id="e7430-115">Nas informações sobre o ambiente à direita, selecione **Fazer logon no ambiente**.</span><span class="sxs-lookup"><span data-stu-id="e7430-115">In the environment information on the right, select **Log on to environment**.</span></span> <span data-ttu-id="e7430-116">Você será direcionado para a sede do Commerce.</span><span class="sxs-lookup"><span data-stu-id="e7430-116">You will be sent to Commerce headquarters.</span></span>
1. <span data-ttu-id="e7430-117">Verifique se a entidade legal **USRT** está selecionada no canto superior direito.</span><span class="sxs-lookup"><span data-stu-id="e7430-117">Make sure that the **USRT** legal entity is selected in the upper-right corner.</span></span>

<span data-ttu-id="e7430-118">Durante as atividades de pós-provisionamento na sede do Commerce, garanta que a entidade legal **USRT** esteja sempre selecionada.</span><span class="sxs-lookup"><span data-stu-id="e7430-118">During post-provisioning activities in Commerce headquarters, make sure that the **USRT** legal entity is always selected.</span></span>

## <a name="configure-the-point-of-sale"></a><span data-ttu-id="e7430-119">Configurar o ponto de venda</span><span class="sxs-lookup"><span data-stu-id="e7430-119">Configure the point of sale</span></span>

### <a name="associate-a-worker-with-your-identity"></a><span data-ttu-id="e7430-120">Associar um trabalhador com sua identidade</span><span class="sxs-lookup"><span data-stu-id="e7430-120">Associate a worker with your identity</span></span>

<span data-ttu-id="e7430-121">Para associar um trabalhador à sua identidade, siga estas etapas na sede do Commerce.</span><span class="sxs-lookup"><span data-stu-id="e7430-121">To associate a worker with your identity, follow these steps in Commerce headquarters.</span></span>

1. <span data-ttu-id="e7430-122">Use o menu à esquerda, vá para **Módulos \> Varejo e comércio \> Funcionários \> Trabalhadores**.</span><span class="sxs-lookup"><span data-stu-id="e7430-122">Use the menu on the left to go to **Modules \> Retail and commerce \> Employees \> Workers**.</span></span>
1. <span data-ttu-id="e7430-123">Na lista, encontre e selecione o registro a seguir: **000713 - Andrew Collette**.</span><span class="sxs-lookup"><span data-stu-id="e7430-123">In the list, find and select the following record: **000713 - Andrew Collette**.</span></span>
1. <span data-ttu-id="e7430-124">No Painel de Ação, selecione **Commerce**.</span><span class="sxs-lookup"><span data-stu-id="e7430-124">On the Action Pane, select **Commerce**.</span></span>
1. <span data-ttu-id="e7430-125">Selecione **Associar identidade existente**.</span><span class="sxs-lookup"><span data-stu-id="e7430-125">Select **Associate existing identity**.</span></span>
1. <span data-ttu-id="e7430-126">No campo **Email** à direita de **Pesquisar usando email**, insira seu endereço de email.</span><span class="sxs-lookup"><span data-stu-id="e7430-126">In the **Email** field to the right of **Search using email**, enter your email address.</span></span>
1. <span data-ttu-id="e7430-127">Selecione **Pesquisar**.</span><span class="sxs-lookup"><span data-stu-id="e7430-127">Select **Search**.</span></span>
1. <span data-ttu-id="e7430-128">Selecione o registro com seu nome.</span><span class="sxs-lookup"><span data-stu-id="e7430-128">Select the record that has your name.</span></span>
1. <span data-ttu-id="e7430-129">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="e7430-129">Select **OK**.</span></span>
1. <span data-ttu-id="e7430-130">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="e7430-130">Select **Save**.</span></span>

### <a name="activate-cloud-pos"></a><span data-ttu-id="e7430-131">Ativar PDV em nuvem</span><span class="sxs-lookup"><span data-stu-id="e7430-131">Activate Cloud POS</span></span>

<span data-ttu-id="e7430-132">Para ativar o PDV em Nuvem, siga estas etapas no LCS.</span><span class="sxs-lookup"><span data-stu-id="e7430-132">To activate Cloud POS, follow these steps in LCS.</span></span>

1. <span data-ttu-id="e7430-133">No menu superior, selecione **Ambientes hospedados na nuvem**.</span><span class="sxs-lookup"><span data-stu-id="e7430-133">On the top menu, select **Cloud-hosted environments**.</span></span>
1. <span data-ttu-id="e7430-134">Selecione seu ambiente na lista.</span><span class="sxs-lookup"><span data-stu-id="e7430-134">Select your environment in the list.</span></span>
1. <span data-ttu-id="e7430-135">Nas informações sobre o ambiente à direita, selecione **Fazer logon no Ponto de Venda em Nuvem**.</span><span class="sxs-lookup"><span data-stu-id="e7430-135">In the environment information on the right, select **Log on to Cloud Point of Sale**.</span></span>
1. <span data-ttu-id="e7430-136">Selecione **Avançar** para abrir a caixa de diálogo **Antes de começar**.</span><span class="sxs-lookup"><span data-stu-id="e7430-136">Select **Next** to open the **Before you start** dialog box.</span></span>
1. <span data-ttu-id="e7430-137">Deixe o campo **URL do Servidor** como está.</span><span class="sxs-lookup"><span data-stu-id="e7430-137">Leave the **Server URL** field as it is.</span></span> <span data-ttu-id="e7430-138">Selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="e7430-138">Select **Next**.</span></span>
1. <span data-ttu-id="e7430-139">Entre usando sua conta do Microsoft Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="e7430-139">Sign in by using your Microsoft Azure Active Directory (Azure AD) account.</span></span>
1. <span data-ttu-id="e7430-140">Em **Nome da loja**, selecione **São Francisco** e, em seguida, selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="e7430-140">Under **Store name**, select **San Francisco**, and then select **Next**.</span></span>
1. <span data-ttu-id="e7430-141">Em **Registro e dispositivo**, selecione **SANFRAN-1**.</span><span class="sxs-lookup"><span data-stu-id="e7430-141">Under **Register and device**, select **SANFRAN-1**.</span></span>
1. <span data-ttu-id="e7430-142">Selecione **Ativar**.</span><span class="sxs-lookup"><span data-stu-id="e7430-142">Select **Activate**.</span></span> <span data-ttu-id="e7430-143">Você está desconectado e será levado para a página de entrada do POS.</span><span class="sxs-lookup"><span data-stu-id="e7430-143">You're signed out and taken to the POS sign-in page.</span></span>
1. <span data-ttu-id="e7430-144">Agora você pode fazer logon na experiência do Cloud POS usando o ID do operador **000713** e a senha **123**.</span><span class="sxs-lookup"><span data-stu-id="e7430-144">You can now sign in to the Cloud POS experience by using operator ID **000713** and password **123**.</span></span>

## <a name="set-up-your-site-in-commerce"></a><span data-ttu-id="e7430-145">Configurar seu site no Commerce</span><span class="sxs-lookup"><span data-stu-id="e7430-145">Set up your site in Commerce</span></span>

<span data-ttu-id="e7430-146">Para iniciar a configuração do seu site de avaliação no Commerce, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="e7430-146">To start to set up your evaluation site in Commerce, follow these steps.</span></span>

1. <span data-ttu-id="e7430-147">Entre no construtor de sites usando a URL que você anotou ao inicializar o e-Commerce durante o provisionamento (consulte [Inicializar o e-Commerce](provisioning-guide.md#initialize-e-commerce)).</span><span class="sxs-lookup"><span data-stu-id="e7430-147">Sign in to site builder by using the URL that you made a note of when you initialized e-Commerce during provisioning (see [Initialize e-Commerce](provisioning-guide.md#initialize-e-commerce)).</span></span>
1. <span data-ttu-id="e7430-148">Selecione o site **Fabrikam** para abrir a caixa de diálogo de configuração do site.</span><span class="sxs-lookup"><span data-stu-id="e7430-148">Select the **Fabrikam** site to open the site setup dialog box.</span></span>
1. <span data-ttu-id="e7430-149">Selecione o domínio que você inseriu ao inicializar o comércio eletrônico.</span><span class="sxs-lookup"><span data-stu-id="e7430-149">Select the domain that you entered when you initialized e-Commerce.</span></span>
1. <span data-ttu-id="e7430-150">Selecione **Loja online estendida Fabrikam** como o canal padrão.</span><span class="sxs-lookup"><span data-stu-id="e7430-150">Select **Fabrikam extended online store** as the default channel.</span></span> <span data-ttu-id="e7430-151">(Certifique-se de selecionar a loja online **estendida**.)</span><span class="sxs-lookup"><span data-stu-id="e7430-151">(Make sure that you select the **extended** online store.)</span></span>
1. <span data-ttu-id="e7430-152">Selecione **en-us** como o idioma padrão.</span><span class="sxs-lookup"><span data-stu-id="e7430-152">Select **en-us** as the default language.</span></span>
1. <span data-ttu-id="e7430-153">Deixe o valor do campo **Caminho** como está.</span><span class="sxs-lookup"><span data-stu-id="e7430-153">Leave the value of the **Path** field as it is.</span></span>
1. <span data-ttu-id="e7430-154">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="e7430-154">Select **OK**.</span></span> <span data-ttu-id="e7430-155">A lista de páginas do site é exibida.</span><span class="sxs-lookup"><span data-stu-id="e7430-155">The list of pages on the site appears.</span></span>

## <a name="enable-jobs"></a><span data-ttu-id="e7430-156">Habilitar trabalhos</span><span class="sxs-lookup"><span data-stu-id="e7430-156">Enable jobs</span></span>

<span data-ttu-id="e7430-157">Para habilitar trabalhos no Commerce, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="e7430-157">To enable jobs in Commerce, follow these steps.</span></span>

1. <span data-ttu-id="e7430-158">Entre no ambiente (Matriz).</span><span class="sxs-lookup"><span data-stu-id="e7430-158">Sign in to the environment (HQ).</span></span>
1. <span data-ttu-id="e7430-159">Use o menu à esquerda, vá para **Varejo e comércio \> Consultas e relatórios \> Trabalhos em lotes**.</span><span class="sxs-lookup"><span data-stu-id="e7430-159">Use the menu on the left to go to **Retail and commerce \> Inquiries and reports \> Batch jobs**.</span></span>

    <span data-ttu-id="e7430-160">As etapas restantes deste procedimento devem ser concluídas para cada um dos seguintes trabalhos:</span><span class="sxs-lookup"><span data-stu-id="e7430-160">The remaining steps of this procedure must be completed for each of the following jobs:</span></span>

    * <span data-ttu-id="e7430-161">Processar notificação por email da ordem de varejo</span><span class="sxs-lookup"><span data-stu-id="e7430-161">Process retail order email notification</span></span>
    * <span data-ttu-id="e7430-162">Disponibilidade do produto</span><span class="sxs-lookup"><span data-stu-id="e7430-162">Product availability</span></span>
    * <span data-ttu-id="e7430-163">P-0001</span><span class="sxs-lookup"><span data-stu-id="e7430-163">P-0001</span></span>
    * <span data-ttu-id="e7430-164">Sincronizar trabalho de ordens</span><span class="sxs-lookup"><span data-stu-id="e7430-164">Synchronize orders job</span></span>

1. <span data-ttu-id="e7430-165">Use o Filtro Rápido para procurar o trabalho pelo nome.</span><span class="sxs-lookup"><span data-stu-id="e7430-165">Use the Quick Filter to search for the job by name.</span></span>
1. <span data-ttu-id="e7430-166">Se o status do trabalho for **Em execução**, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="e7430-166">If the status of the job is **Executing**, follow these steps:</span></span>

    1. <span data-ttu-id="e7430-167">Selecione o registro.</span><span class="sxs-lookup"><span data-stu-id="e7430-167">Select the record.</span></span>
    1. <span data-ttu-id="e7430-168">No Painel de Ação, na guia **Trabalho em lotes**, selecione **Alterar status**.</span><span class="sxs-lookup"><span data-stu-id="e7430-168">On the Action Pane, on **Batch job** tab, select **Change status**.</span></span>
    1. <span data-ttu-id="e7430-169">Selecione **Cancelar** e, em seguida, selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="e7430-169">Select **Canceling**, and then select **OK**.</span></span>

<span data-ttu-id="e7430-170">Opcionalmente, você também pode definir o intervalo de recorrência como um (1) minuto para os seguintes trabalhos:</span><span class="sxs-lookup"><span data-stu-id="e7430-170">Optionally, you can also set the recurrence interval to one (1) minute for the following jobs:</span></span>

* <span data-ttu-id="e7430-171">Trabalho Processar notificação por email da ordem de varejo</span><span class="sxs-lookup"><span data-stu-id="e7430-171">Process retail order email notification job</span></span>
* <span data-ttu-id="e7430-172">Trabalho P-0001</span><span class="sxs-lookup"><span data-stu-id="e7430-172">P-0001 job</span></span>
* <span data-ttu-id="e7430-173">Sincronizar trabalho de ordens</span><span class="sxs-lookup"><span data-stu-id="e7430-173">Synchronize orders job</span></span>

### <a name="run-full-data-synchronization"></a><span data-ttu-id="e7430-174">Executar sincronização de dados completa</span><span class="sxs-lookup"><span data-stu-id="e7430-174">Run full data synchronization</span></span>

<span data-ttu-id="e7430-175">Para executar a sincronização completa dos dados no Commerce, siga estas etapas na sede do Commerce.</span><span class="sxs-lookup"><span data-stu-id="e7430-175">To run full data synchronization in Commerce, follow these steps in Commerce headquarters.</span></span>

1. <span data-ttu-id="e7430-176">Use o menu à esquerda para ir para **Módulos \> Varejo e comércio \> Configuração da sede \> Agendador do Commerce \> Banco de dados do canal**.</span><span class="sxs-lookup"><span data-stu-id="e7430-176">Use the menu on the left to go to **Modules \> Retail and commerce \> Headquarters setup \> Commerce scheduler \> Channel database**.</span></span>
1. <span data-ttu-id="e7430-177">Selecione o canal chamado **scXXXXXXXXX**.</span><span class="sxs-lookup"><span data-stu-id="e7430-177">Select the channel that is named **scXXXXXXXXX**.</span></span>
1. <span data-ttu-id="e7430-178">No Painel de Ação, selecione **Sincronização de dados completa**.</span><span class="sxs-lookup"><span data-stu-id="e7430-178">On the Action Pane, select **Full data sync**.</span></span>
1. <span data-ttu-id="e7430-179">Digite **9999** como a agenda de distribuição.</span><span class="sxs-lookup"><span data-stu-id="e7430-179">Enter **9999** as the distribution schedule.</span></span>
1. <span data-ttu-id="e7430-180">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="e7430-180">Select **OK**.</span></span>
1. <span data-ttu-id="e7430-181">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="e7430-181">Select **OK**.</span></span>

### <a name="test-credit-card-information-to-do-test-purchases"></a><span data-ttu-id="e7430-182">Testar informações do cartão de crédito para testar compras</span><span class="sxs-lookup"><span data-stu-id="e7430-182">Test credit card information to do test purchases</span></span>

<span data-ttu-id="e7430-183">Para realizar transações de teste no site, você pode usar as informações do cartão de crédito de teste a seguir:</span><span class="sxs-lookup"><span data-stu-id="e7430-183">To perform test transactions on the site, you can use the following test credit card information:</span></span>

- <span data-ttu-id="e7430-184">**Número do cartão:** 4111-1111-1111-1111</span><span class="sxs-lookup"><span data-stu-id="e7430-184">**Card number:** 4111-1111-1111-1111</span></span>
- <span data-ttu-id="e7430-185">**Data de vencimento:** 20/10</span><span class="sxs-lookup"><span data-stu-id="e7430-185">**Expiration date:** 10/20</span></span>
- <span data-ttu-id="e7430-186">**Código do valor de verificação do cartão (CVV):** 737</span><span class="sxs-lookup"><span data-stu-id="e7430-186">**Card verification value (CVV) code:** 737</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e7430-187">Nunca, em qualquer circunstância, tente usar as informações reais do cartão de crédito no local do teste.</span><span class="sxs-lookup"><span data-stu-id="e7430-187">Never, under any circumstances, try to use actual credit card information on the test site.</span></span>

## <a name="next-steps"></a><span data-ttu-id="e7430-188">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="e7430-188">Next steps</span></span>

<span data-ttu-id="e7430-189">Depois que as etapas de provisionamento e configuração forem concluídas, você poderá começar a usar seu ambiente de avaliação.</span><span class="sxs-lookup"><span data-stu-id="e7430-189">After the provisioning and configuration steps are completed, you can start to use your evaluation environment.</span></span> <span data-ttu-id="e7430-190">Use a URL do construtor de sites do Commerce para acessar a experiência de criação.</span><span class="sxs-lookup"><span data-stu-id="e7430-190">Use the Commerce site builder URL to go to the authoring experience.</span></span> <span data-ttu-id="e7430-191">Use a URL do site do Commerce para acessar a experiência de site do cliente de varejo.</span><span class="sxs-lookup"><span data-stu-id="e7430-191">Use the Commerce site URL to go to the retail customer site experience.</span></span>

<span data-ttu-id="e7430-192">Para configurar recursos opcionais para seu ambiente de avaliação do Commerce, consulte [Configurar recursos opcionais para um ambiente de avaliação do Commerce](cpe-optional-features.md).</span><span class="sxs-lookup"><span data-stu-id="e7430-192">To configure optional features for your Commerce evaluation environment, see [Configure optional features for a Commerce evaluation environment](cpe-optional-features.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="e7430-193">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="e7430-193">Additional resources</span></span>

[<span data-ttu-id="e7430-194">Visão geral do ambiente de avaliação do Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="e7430-194">Dynamics 365 Commerce evaluation environment overview</span></span>](cpe-overview.md)

[<span data-ttu-id="e7430-195">Provisionar um ambiente de avaliação do Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="e7430-195">Provision a Dynamics 365 Commerce evaluation environment</span></span>](provisioning-guide.md)

[<span data-ttu-id="e7430-196">Configurar recursos opcionais para um ambiente de avaliação do Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="e7430-196">Configure optional features for a Dynamics 365 Commerce evaluation environment</span></span>](cpe-optional-features.md)

[<span data-ttu-id="e7430-197">Configurar BOPIS em um ambiente de avaliação do Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="e7430-197">Configure BOPIS in a Dynamics 365 Commerce evaluation environment</span></span>](cpe-bopis.md)

[<span data-ttu-id="e7430-198">Perguntas frequentes sobre o ambiente de avaliação do Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="e7430-198">Dynamics 365 Commerce evaluation environment FAQ</span></span>](cpe-faq.md)

[<span data-ttu-id="e7430-199">Microsoft Lifecycle Services (LCS)</span><span class="sxs-lookup"><span data-stu-id="e7430-199">Microsoft Lifecycle Services (LCS)</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/lifecycle-services/lcs-user-guide)

[<span data-ttu-id="e7430-200">Retail Cloud Scale Unit (RCSU)</span><span class="sxs-lookup"><span data-stu-id="e7430-200">Retail Cloud Scale Unit (RCSU)</span></span>](https://docs.microsoft.com/business-applications-release-notes/october18/dynamics365-retail/retail-cloud-scale-unit)

[<span data-ttu-id="e7430-201">Portal do Microsoft Azure</span><span class="sxs-lookup"><span data-stu-id="e7430-201">Microsoft Azure portal</span></span>](https://azure.microsoft.com/features/azure-portal)

[<span data-ttu-id="e7430-202">Site do Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="e7430-202">Dynamics 365 Commerce website</span></span>](https://aka.ms/Dynamics365CommerceWebsite)
