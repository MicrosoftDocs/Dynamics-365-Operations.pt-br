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
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: psimolin
ms.search.validFrom: 2019-12-10
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 9b11ab600bb2aa17cf330947304f5b22dd522081
ms.sourcegitcommit: c88b54ba13a4dfe39b844ffaced4dc435560c47d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2021
ms.locfileid: "5477964"
---
# <a name="configure-a-dynamics-365-commerce-evaluation-environment"></a><span data-ttu-id="f51df-103">Configurar um ambiente de avaliação do Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="f51df-103">Configure a Dynamics 365 Commerce evaluation environment</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="f51df-104">Este tópico explica como configurar um ambiente de avaliação do Microsoft Dynamics 365 Commerce após ter sido provisionado.</span><span class="sxs-lookup"><span data-stu-id="f51df-104">This topic explains how to configure a Microsoft Dynamics 365 Commerce evaluation environment after it's provisioned.</span></span>

<span data-ttu-id="f51df-105">Conclua os procedimentos neste tópico somente após o provisionamento do seu ambiente de avaliação do Commerce.</span><span class="sxs-lookup"><span data-stu-id="f51df-105">Complete the procedures in this topic only after your Commerce evaluation environment has been provisioned.</span></span> <span data-ttu-id="f51df-106">Para obter informações sobre como provisionar seu ambiente de avaliação do Commerce, consulte [Provisionar um ambiente de avaliação do Commerce](provisioning-guide.md).</span><span class="sxs-lookup"><span data-stu-id="f51df-106">For information about how to provision your Commerce evaluation environment, see [Provision a Commerce evaluation environment](provisioning-guide.md).</span></span>

<span data-ttu-id="f51df-107">Depois que o ambiente de avaliação do Commerce for provisionado de ponta a ponta, as etapas adicionais de configuração de pós-provisionamento deverão ser concluídas para que você possa começar a avaliar o ambiente.</span><span class="sxs-lookup"><span data-stu-id="f51df-107">After your Commerce evaluation environment has been provisioned end to end, additional post-provisioning configuration steps must be completed before you can start to evaluate the environment.</span></span> <span data-ttu-id="f51df-108">Para concluir essas etapas, você deve usar Microsoft Dynamics Lifecycle Services (LCS) e Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="f51df-108">To complete these steps, you must use Microsoft Dynamics Lifecycle Services (LCS) and Dynamics 365 Commerce.</span></span>

## <a name="before-you-start"></a><span data-ttu-id="f51df-109">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="f51df-109">Before you start</span></span>

1. <span data-ttu-id="f51df-110">Entre no [Portal de LCS](https://lcs.dynamics.com).</span><span class="sxs-lookup"><span data-stu-id="f51df-110">Sign in to the [LCS portal](https://lcs.dynamics.com).</span></span>
1. <span data-ttu-id="f51df-111">Vá para seu projeto.</span><span class="sxs-lookup"><span data-stu-id="f51df-111">Go to your project.</span></span>
1. <span data-ttu-id="f51df-112">No menu superior, selecione **Ambientes hospedados na nuvem**.</span><span class="sxs-lookup"><span data-stu-id="f51df-112">On the top menu, select **Cloud-hosted environments**.</span></span>
1. <span data-ttu-id="f51df-113">Selecione seu ambiente na lista.</span><span class="sxs-lookup"><span data-stu-id="f51df-113">Select your environment in the list.</span></span>
1. <span data-ttu-id="f51df-114">Nas informações sobre o ambiente à direita, selecione **Fazer logon no ambiente**.</span><span class="sxs-lookup"><span data-stu-id="f51df-114">In the environment information on the right, select **Log on to environment**.</span></span> <span data-ttu-id="f51df-115">Você será direcionado para a sede do Commerce.</span><span class="sxs-lookup"><span data-stu-id="f51df-115">You will be sent to Commerce headquarters.</span></span>
1. <span data-ttu-id="f51df-116">Verifique se a entidade legal **USRT** está selecionada no canto superior direito.</span><span class="sxs-lookup"><span data-stu-id="f51df-116">Make sure that the **USRT** legal entity is selected in the upper-right corner.</span></span>

<span data-ttu-id="f51df-117">Durante as atividades de pós-provisionamento na sede do Commerce, garanta que a entidade legal **USRT** esteja sempre selecionada.</span><span class="sxs-lookup"><span data-stu-id="f51df-117">During post-provisioning activities in Commerce headquarters, make sure that the **USRT** legal entity is always selected.</span></span>

## <a name="configure-the-point-of-sale"></a><span data-ttu-id="f51df-118">Configurar o ponto de venda</span><span class="sxs-lookup"><span data-stu-id="f51df-118">Configure the point of sale</span></span>

### <a name="associate-a-worker-with-your-identity"></a><span data-ttu-id="f51df-119">Associar um trabalhador com sua identidade</span><span class="sxs-lookup"><span data-stu-id="f51df-119">Associate a worker with your identity</span></span>

<span data-ttu-id="f51df-120">Para associar um trabalhador à sua identidade, siga estas etapas na sede do Commerce.</span><span class="sxs-lookup"><span data-stu-id="f51df-120">To associate a worker with your identity, follow these steps in Commerce headquarters.</span></span>

1. <span data-ttu-id="f51df-121">Use o menu à esquerda, vá para **Módulos \> Varejo e comércio \> Funcionários \> Trabalhadores**.</span><span class="sxs-lookup"><span data-stu-id="f51df-121">Use the menu on the left to go to **Modules \> Retail and commerce \> Employees \> Workers**.</span></span>
1. <span data-ttu-id="f51df-122">Na lista, encontre e selecione o registro a seguir: **000713 - Andrew Collette**.</span><span class="sxs-lookup"><span data-stu-id="f51df-122">In the list, find and select the following record: **000713 - Andrew Collette**.</span></span>
1. <span data-ttu-id="f51df-123">No Painel de Ação, selecione **Commerce**.</span><span class="sxs-lookup"><span data-stu-id="f51df-123">On the Action Pane, select **Commerce**.</span></span>
1. <span data-ttu-id="f51df-124">Selecione **Associar identidade existente**.</span><span class="sxs-lookup"><span data-stu-id="f51df-124">Select **Associate existing identity**.</span></span>
1. <span data-ttu-id="f51df-125">No campo **Email** à direita de **Pesquisar usando email**, insira seu endereço de email.</span><span class="sxs-lookup"><span data-stu-id="f51df-125">In the **Email** field to the right of **Search using email**, enter your email address.</span></span>
1. <span data-ttu-id="f51df-126">Selecione **Pesquisar**.</span><span class="sxs-lookup"><span data-stu-id="f51df-126">Select **Search**.</span></span>
1. <span data-ttu-id="f51df-127">Selecione o registro com seu nome.</span><span class="sxs-lookup"><span data-stu-id="f51df-127">Select the record that has your name.</span></span>
1. <span data-ttu-id="f51df-128">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="f51df-128">Select **OK**.</span></span>
1. <span data-ttu-id="f51df-129">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="f51df-129">Select **Save**.</span></span>

### <a name="activate-cloud-pos"></a><span data-ttu-id="f51df-130">Ativar PDV em nuvem</span><span class="sxs-lookup"><span data-stu-id="f51df-130">Activate Cloud POS</span></span>

<span data-ttu-id="f51df-131">Para ativar o PDV em Nuvem, siga estas etapas no LCS.</span><span class="sxs-lookup"><span data-stu-id="f51df-131">To activate Cloud POS, follow these steps in LCS.</span></span>

1. <span data-ttu-id="f51df-132">No menu superior, selecione **Ambientes hospedados na nuvem**.</span><span class="sxs-lookup"><span data-stu-id="f51df-132">On the top menu, select **Cloud-hosted environments**.</span></span>
1. <span data-ttu-id="f51df-133">Selecione seu ambiente na lista.</span><span class="sxs-lookup"><span data-stu-id="f51df-133">Select your environment in the list.</span></span>
1. <span data-ttu-id="f51df-134">Nas informações sobre o ambiente à direita, selecione **Fazer logon no Ponto de Venda em Nuvem**.</span><span class="sxs-lookup"><span data-stu-id="f51df-134">In the environment information on the right, select **Log on to Cloud Point of Sale**.</span></span>
1. <span data-ttu-id="f51df-135">Selecione **Avançar** para abrir a caixa de diálogo **Antes de começar**.</span><span class="sxs-lookup"><span data-stu-id="f51df-135">Select **Next** to open the **Before you start** dialog box.</span></span>
1. <span data-ttu-id="f51df-136">Deixe o campo **URL do Servidor** como está.</span><span class="sxs-lookup"><span data-stu-id="f51df-136">Leave the **Server URL** field as it is.</span></span> <span data-ttu-id="f51df-137">Selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="f51df-137">Select **Next**.</span></span>
1. <span data-ttu-id="f51df-138">Entre usando sua conta do Microsoft Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="f51df-138">Sign in by using your Microsoft Azure Active Directory (Azure AD) account.</span></span>
1. <span data-ttu-id="f51df-139">Em **Nome da loja**, selecione **São Francisco** e, em seguida, selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="f51df-139">Under **Store name**, select **San Francisco**, and then select **Next**.</span></span>
1. <span data-ttu-id="f51df-140">Em **Registro e dispositivo**, selecione **SANFRAN-1**.</span><span class="sxs-lookup"><span data-stu-id="f51df-140">Under **Register and device**, select **SANFRAN-1**.</span></span>
1. <span data-ttu-id="f51df-141">Selecione **Ativar**.</span><span class="sxs-lookup"><span data-stu-id="f51df-141">Select **Activate**.</span></span> <span data-ttu-id="f51df-142">Você está desconectado e será levado para a página de entrada do POS.</span><span class="sxs-lookup"><span data-stu-id="f51df-142">You're signed out and taken to the POS sign-in page.</span></span>
1. <span data-ttu-id="f51df-143">Agora você pode fazer logon na experiência do Cloud POS usando o ID do operador **000713** e a senha **123**.</span><span class="sxs-lookup"><span data-stu-id="f51df-143">You can now sign in to the Cloud POS experience by using operator ID **000713** and password **123**.</span></span>

## <a name="set-up-your-site-in-commerce"></a><span data-ttu-id="f51df-144">Configurar seu site no Commerce</span><span class="sxs-lookup"><span data-stu-id="f51df-144">Set up your site in Commerce</span></span>

<span data-ttu-id="f51df-145">Para iniciar a configuração do seu site de avaliação no Commerce, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="f51df-145">To start to set up your evaluation site in Commerce, follow these steps.</span></span>

1. <span data-ttu-id="f51df-146">Entre no construtor de sites usando a URL que você anotou ao inicializar o e-Commerce durante o provisionamento (consulte [Inicializar o e-Commerce](provisioning-guide.md#initialize-e-commerce)).</span><span class="sxs-lookup"><span data-stu-id="f51df-146">Sign in to site builder by using the URL that you made a note of when you initialized e-Commerce during provisioning (see [Initialize e-Commerce](provisioning-guide.md#initialize-e-commerce)).</span></span>
1. <span data-ttu-id="f51df-147">Selecione o site **Fabrikam** para abrir a caixa de diálogo de configuração do site.</span><span class="sxs-lookup"><span data-stu-id="f51df-147">Select the **Fabrikam** site to open the site setup dialog box.</span></span>
1. <span data-ttu-id="f51df-148">Selecione o domínio que você inseriu ao inicializar o comércio eletrônico.</span><span class="sxs-lookup"><span data-stu-id="f51df-148">Select the domain that you entered when you initialized e-Commerce.</span></span>
1. <span data-ttu-id="f51df-149">Selecione **Loja online estendida Fabrikam** como o canal padrão.</span><span class="sxs-lookup"><span data-stu-id="f51df-149">Select **Fabrikam extended online store** as the default channel.</span></span> <span data-ttu-id="f51df-150">(Certifique-se de selecionar a loja online **estendida**.)</span><span class="sxs-lookup"><span data-stu-id="f51df-150">(Make sure that you select the **extended** online store.)</span></span>
1. <span data-ttu-id="f51df-151">Selecione **en-us** como o idioma padrão.</span><span class="sxs-lookup"><span data-stu-id="f51df-151">Select **en-us** as the default language.</span></span>
1. <span data-ttu-id="f51df-152">Deixe o valor do campo **Caminho** como está.</span><span class="sxs-lookup"><span data-stu-id="f51df-152">Leave the value of the **Path** field as it is.</span></span>
1. <span data-ttu-id="f51df-153">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="f51df-153">Select **OK**.</span></span> <span data-ttu-id="f51df-154">A lista de páginas do site é exibida.</span><span class="sxs-lookup"><span data-stu-id="f51df-154">The list of pages on the site appears.</span></span>

## <a name="enable-jobs"></a><span data-ttu-id="f51df-155">Habilitar trabalhos</span><span class="sxs-lookup"><span data-stu-id="f51df-155">Enable jobs</span></span>

<span data-ttu-id="f51df-156">Para habilitar trabalhos no Commerce, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="f51df-156">To enable jobs in Commerce, follow these steps.</span></span>

1. <span data-ttu-id="f51df-157">Entre no ambiente (Matriz).</span><span class="sxs-lookup"><span data-stu-id="f51df-157">Sign in to the environment (HQ).</span></span>
1. <span data-ttu-id="f51df-158">Use o menu à esquerda, vá para **Varejo e comércio \> Consultas e relatórios \> Trabalhos em lotes**.</span><span class="sxs-lookup"><span data-stu-id="f51df-158">Use the menu on the left to go to **Retail and commerce \> Inquiries and reports \> Batch jobs**.</span></span>

    <span data-ttu-id="f51df-159">As etapas restantes deste procedimento devem ser concluídas para cada um dos seguintes trabalhos:</span><span class="sxs-lookup"><span data-stu-id="f51df-159">The remaining steps of this procedure must be completed for each of the following jobs:</span></span>

    * <span data-ttu-id="f51df-160">Processar notificação por email da ordem de varejo</span><span class="sxs-lookup"><span data-stu-id="f51df-160">Process retail order email notification</span></span>
    * <span data-ttu-id="f51df-161">Disponibilidade do produto</span><span class="sxs-lookup"><span data-stu-id="f51df-161">Product availability</span></span>
    * <span data-ttu-id="f51df-162">P-0001</span><span class="sxs-lookup"><span data-stu-id="f51df-162">P-0001</span></span>
    * <span data-ttu-id="f51df-163">Sincronizar trabalho de ordens</span><span class="sxs-lookup"><span data-stu-id="f51df-163">Synchronize orders job</span></span>

1. <span data-ttu-id="f51df-164">Use o Filtro Rápido para procurar o trabalho pelo nome.</span><span class="sxs-lookup"><span data-stu-id="f51df-164">Use the Quick Filter to search for the job by name.</span></span>
1. <span data-ttu-id="f51df-165">Se o status do trabalho for **Em execução**, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="f51df-165">If the status of the job is **Executing**, follow these steps:</span></span>

    1. <span data-ttu-id="f51df-166">Selecione o registro.</span><span class="sxs-lookup"><span data-stu-id="f51df-166">Select the record.</span></span>
    1. <span data-ttu-id="f51df-167">No Painel de Ação, na guia **Trabalho em lotes**, selecione **Alterar status**.</span><span class="sxs-lookup"><span data-stu-id="f51df-167">On the Action Pane, on **Batch job** tab, select **Change status**.</span></span>
    1. <span data-ttu-id="f51df-168">Selecione **Cancelar** e, em seguida, selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="f51df-168">Select **Canceling**, and then select **OK**.</span></span>

<span data-ttu-id="f51df-169">Opcionalmente, você também pode definir o intervalo de recorrência como um (1) minuto para os seguintes trabalhos:</span><span class="sxs-lookup"><span data-stu-id="f51df-169">Optionally, you can also set the recurrence interval to one (1) minute for the following jobs:</span></span>

* <span data-ttu-id="f51df-170">Trabalho Processar notificação por email da ordem de varejo</span><span class="sxs-lookup"><span data-stu-id="f51df-170">Process retail order email notification job</span></span>
* <span data-ttu-id="f51df-171">Trabalho P-0001</span><span class="sxs-lookup"><span data-stu-id="f51df-171">P-0001 job</span></span>
* <span data-ttu-id="f51df-172">Sincronizar trabalho de ordens</span><span class="sxs-lookup"><span data-stu-id="f51df-172">Synchronize orders job</span></span>

### <a name="run-full-data-synchronization"></a><span data-ttu-id="f51df-173">Executar sincronização de dados completa</span><span class="sxs-lookup"><span data-stu-id="f51df-173">Run full data synchronization</span></span>

<span data-ttu-id="f51df-174">Para executar a sincronização completa dos dados no Commerce, siga estas etapas na sede do Commerce.</span><span class="sxs-lookup"><span data-stu-id="f51df-174">To run full data synchronization in Commerce, follow these steps in Commerce headquarters.</span></span>

1. <span data-ttu-id="f51df-175">Use o menu à esquerda para ir para **Módulos \> Varejo e comércio \> Configuração da sede \> Agendador do Commerce \> Banco de dados do canal**.</span><span class="sxs-lookup"><span data-stu-id="f51df-175">Use the menu on the left to go to **Modules \> Retail and commerce \> Headquarters setup \> Commerce scheduler \> Channel database**.</span></span>
1. <span data-ttu-id="f51df-176">Selecione o canal chamado **scXXXXXXXXX**.</span><span class="sxs-lookup"><span data-stu-id="f51df-176">Select the channel that is named **scXXXXXXXXX**.</span></span>
1. <span data-ttu-id="f51df-177">No Painel de Ação, selecione **Sincronização de dados completa**.</span><span class="sxs-lookup"><span data-stu-id="f51df-177">On the Action Pane, select **Full data sync**.</span></span>
1. <span data-ttu-id="f51df-178">Digite **9999** como a agenda de distribuição.</span><span class="sxs-lookup"><span data-stu-id="f51df-178">Enter **9999** as the distribution schedule.</span></span>
1. <span data-ttu-id="f51df-179">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="f51df-179">Select **OK**.</span></span>
1. <span data-ttu-id="f51df-180">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="f51df-180">Select **OK**.</span></span>

### <a name="test-credit-card-information-to-do-test-purchases"></a><span data-ttu-id="f51df-181">Testar informações do cartão de crédito para testar compras</span><span class="sxs-lookup"><span data-stu-id="f51df-181">Test credit card information to do test purchases</span></span>

<span data-ttu-id="f51df-182">Para realizar transações de teste no site, você pode usar as informações do cartão de crédito de teste a seguir:</span><span class="sxs-lookup"><span data-stu-id="f51df-182">To perform test transactions on the site, you can use the following test credit card information:</span></span>

- <span data-ttu-id="f51df-183">**Número do cartão:** 4111-1111-1111-1111</span><span class="sxs-lookup"><span data-stu-id="f51df-183">**Card number:** 4111-1111-1111-1111</span></span>
- <span data-ttu-id="f51df-184">**Data de vencimento:** 20/10</span><span class="sxs-lookup"><span data-stu-id="f51df-184">**Expiration date:** 10/20</span></span>
- <span data-ttu-id="f51df-185">**Código do valor de verificação do cartão (CVV):** 737</span><span class="sxs-lookup"><span data-stu-id="f51df-185">**Card verification value (CVV) code:** 737</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f51df-186">Nunca, em qualquer circunstância, tente usar as informações reais do cartão de crédito no local do teste.</span><span class="sxs-lookup"><span data-stu-id="f51df-186">Never, under any circumstances, try to use actual credit card information on the test site.</span></span>

## <a name="next-steps"></a><span data-ttu-id="f51df-187">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="f51df-187">Next steps</span></span>

<span data-ttu-id="f51df-188">Depois que as etapas de provisionamento e configuração forem concluídas, você poderá começar a usar seu ambiente de avaliação.</span><span class="sxs-lookup"><span data-stu-id="f51df-188">After the provisioning and configuration steps are completed, you can start to use your evaluation environment.</span></span> <span data-ttu-id="f51df-189">Use a URL do construtor de sites do Commerce para acessar a experiência de criação.</span><span class="sxs-lookup"><span data-stu-id="f51df-189">Use the Commerce site builder URL to go to the authoring experience.</span></span> <span data-ttu-id="f51df-190">Use a URL do site do Commerce para acessar a experiência de site do cliente de varejo.</span><span class="sxs-lookup"><span data-stu-id="f51df-190">Use the Commerce site URL to go to the retail customer site experience.</span></span>

<span data-ttu-id="f51df-191">Para configurar recursos opcionais para seu ambiente de avaliação do Commerce, consulte [Configurar recursos opcionais para um ambiente de avaliação do Commerce](cpe-optional-features.md).</span><span class="sxs-lookup"><span data-stu-id="f51df-191">To configure optional features for your Commerce evaluation environment, see [Configure optional features for a Commerce evaluation environment](cpe-optional-features.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="f51df-192">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="f51df-192">Additional resources</span></span>

[<span data-ttu-id="f51df-193">Visão geral do ambiente de avaliação do Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="f51df-193">Dynamics 365 Commerce evaluation environment overview</span></span>](cpe-overview.md)

[<span data-ttu-id="f51df-194">Provisionar um ambiente de avaliação do Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="f51df-194">Provision a Dynamics 365 Commerce evaluation environment</span></span>](provisioning-guide.md)

[<span data-ttu-id="f51df-195">Configurar recursos opcionais para um ambiente de avaliação do Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="f51df-195">Configure optional features for a Dynamics 365 Commerce evaluation environment</span></span>](cpe-optional-features.md)

[<span data-ttu-id="f51df-196">Configurar BOPIS em um ambiente de avaliação do Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="f51df-196">Configure BOPIS in a Dynamics 365 Commerce evaluation environment</span></span>](cpe-bopis.md)

[<span data-ttu-id="f51df-197">Perguntas frequentes sobre o ambiente de avaliação do Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="f51df-197">Dynamics 365 Commerce evaluation environment FAQ</span></span>](cpe-faq.md)

[<span data-ttu-id="f51df-198">Microsoft Lifecycle Services (LCS)</span><span class="sxs-lookup"><span data-stu-id="f51df-198">Microsoft Lifecycle Services (LCS)</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/lifecycle-services/lcs-user-guide)

[<span data-ttu-id="f51df-199">Retail Cloud Scale Unit (RCSU)</span><span class="sxs-lookup"><span data-stu-id="f51df-199">Retail Cloud Scale Unit (RCSU)</span></span>](https://docs.microsoft.com/business-applications-release-notes/october18/dynamics365-retail/retail-cloud-scale-unit)

[<span data-ttu-id="f51df-200">Portal do Microsoft Azure</span><span class="sxs-lookup"><span data-stu-id="f51df-200">Microsoft Azure portal</span></span>](https://azure.microsoft.com/features/azure-portal)

[<span data-ttu-id="f51df-201">Site do Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="f51df-201">Dynamics 365 Commerce website</span></span>](https://aka.ms/Dynamics365CommerceWebsite)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
