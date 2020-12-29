---
title: Provisionar um ambiente de avaliação do Dynamics 365 Commerce
description: Este tópico explica como provisionar um ambiente de avaliação do Microsoft Dynamics 365 Commerce.
author: psimolin
manager: annbe
ms.date: 11/05/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: b54216a565c264dfcfe821581fee9df7b5e22323
ms.sourcegitcommit: 715508547f9a71a89a138190e8540686556c753d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/05/2020
ms.locfileid: "4410344"
---
# <a name="provision-a-dynamics-365-commerce-evaluation-environment"></a><span data-ttu-id="26a38-103">Provisionar um ambiente de avaliação do Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="26a38-103">Provision a Dynamics 365 Commerce evaluation environment</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="26a38-104">Este tópico explica como provisionar um ambiente de avaliação do Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="26a38-104">This topic explains how to provision a Microsoft Dynamics 365 Commerce evaluation environment.</span></span>

<span data-ttu-id="26a38-105">Antes de começar, recomendamos que você faça uma verificação rápida deste tópico para ter uma ideia do que o processo requer.</span><span class="sxs-lookup"><span data-stu-id="26a38-105">Before you begin, we recommend that you take a quick scan through this topic to get an idea of what the process requires.</span></span>

> [!NOTE]
> <span data-ttu-id="26a38-106">Os ambientes de avaliação do Commerce não estão disponíveis para o público geral e são concedidos a parceiros e clientes por solicitação.</span><span class="sxs-lookup"><span data-stu-id="26a38-106">Commerce evaluation environments aren't generally available, and are granted to partners and customers on a per-request basis.</span></span> <span data-ttu-id="26a38-107">Para obter mais informações, fale com o contato do seu parceiro Microsoft.</span><span class="sxs-lookup"><span data-stu-id="26a38-107">For more information, reach out to your Microsoft partner contact.</span></span>

## <a name="overview"></a><span data-ttu-id="26a38-108">Visão Geral</span><span class="sxs-lookup"><span data-stu-id="26a38-108">Overview</span></span>

<span data-ttu-id="26a38-109">Para provisionar um ambiente de avaliação do Commerce com êxito, você deve criar um projeto que tenha um nome e um tipo de produto específicos.</span><span class="sxs-lookup"><span data-stu-id="26a38-109">To successfully provision a Commerce evaluation environment, you must create a project that has a specific product name and type.</span></span> <span data-ttu-id="26a38-110">O ambiente e o Commerce Scale Unit (CSU) também têm alguns parâmetros específicos que você deve usar quando espera provisionar o comércio eletrônico posteriormente.</span><span class="sxs-lookup"><span data-stu-id="26a38-110">The environment and Commerce Scale Unit (CSU) also have some specific parameters that you must use when you expect to provision e-Commerce later.</span></span> <span data-ttu-id="26a38-111">As instruções neste tópico descrevem todas as etapas que são necessárias para concluir o provisionamento e os parâmetros que devem ser usados.</span><span class="sxs-lookup"><span data-stu-id="26a38-111">The instructions in this topic describe all the steps that are required to complete provisioning and the parameters that you must use.</span></span>

<span data-ttu-id="26a38-112">Após o provisionamento bem-sucedido do ambiente de avaliação do Commerce, você deve concluir algumas etapas de pós-provisionamento para prepará-lo para uso.</span><span class="sxs-lookup"><span data-stu-id="26a38-112">After you successfully provision your Commerce evaluation environment, you must complete a few post-provisioning steps to prepare it for use.</span></span> <span data-ttu-id="26a38-113">Algumas etapas são opcionais, dependendo dos aspectos do sistema você deseja avaliar.</span><span class="sxs-lookup"><span data-stu-id="26a38-113">Some steps are optional, depending on the aspects of the system that you want to evaluate.</span></span> <span data-ttu-id="26a38-114">Você sempre poderá concluir as etapas opcionais posteriormente.</span><span class="sxs-lookup"><span data-stu-id="26a38-114">You can always complete the optional steps later.</span></span>

<span data-ttu-id="26a38-115">Para obter informações sobre como configurar seu ambiente de avaliação do Commerce depois de provisioná-lo, consulte [Configurar um ambiente de avaliação do Commerce](cpe-post-provisioning.md).</span><span class="sxs-lookup"><span data-stu-id="26a38-115">For information about how to configure your Commerce evaluation environment after you provision it, see [Configure a Commerce evaluation environment](cpe-post-provisioning.md).</span></span> <span data-ttu-id="26a38-116">Para obter informações sobre como configurar recursos opcionais para o ambiente de avaliação do Commerce, consulte [Configurar recursos opcionais para um ambiente de avaliação do Commerce](cpe-optional-features.md).</span><span class="sxs-lookup"><span data-stu-id="26a38-116">For information about how to configure optional features for your Commerce evaluation environment, see [Configure optional features for a Commerce evaluation environment](cpe-optional-features.md).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="26a38-117">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="26a38-117">Prerequisites</span></span>

<span data-ttu-id="26a38-118">Os pré-requisitos a seguir devem estar em vigor para que você possa provisionar seu ambiente de avaliação do Commerce:</span><span class="sxs-lookup"><span data-stu-id="26a38-118">The following prerequisites must be in place before you can provision your Commerce evaluation environment:</span></span>

- <span data-ttu-id="26a38-119">Você foi integrado ao programa de avaliação e recebeu capacidade para um ambiente de avaliação.</span><span class="sxs-lookup"><span data-stu-id="26a38-119">You have been onboarded into the evaluation program and granted capacity for an evaluation environment.</span></span>
- <span data-ttu-id="26a38-120">Você tem acesso ao portal do Lifecycle Services (LCS) do Microsoft Dynamics.</span><span class="sxs-lookup"><span data-stu-id="26a38-120">You have access to the Microsoft Dynamics Lifecycle Services (LCS) portal.</span></span>
- <span data-ttu-id="26a38-121">Você é um parceiro ou cliente do Microsoft Dynamics 365 existente e consegue criar um projeto do Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="26a38-121">You are an existing Microsoft Dynamics 365 partner or customer and are able to create a Dynamics 365 Commerce project.</span></span>
- <span data-ttu-id="26a38-122">Você tem acesso de administrador à assinatura do Microsoft Azure ou está em contato com um administrador de assinaturas que poderá ajudar se for necessário.</span><span class="sxs-lookup"><span data-stu-id="26a38-122">You have administrator access to your Microsoft Azure subscription, or you're in contact with a subscription administrator who can assist you if required.</span></span>
- <span data-ttu-id="26a38-123">Você tem sua ID de locatário do Azure Active Directory (Azure AD) disponível.</span><span class="sxs-lookup"><span data-stu-id="26a38-123">You have your Azure Active Directory (Azure AD) tenant ID available.</span></span>
- <span data-ttu-id="26a38-124">Você criou um grupo de segurança do Azure AD que pode ser usado como um grupo de administradores do sistema do e-Commerce e tem sua ID disponível.</span><span class="sxs-lookup"><span data-stu-id="26a38-124">You've created an Azure AD security group that can be used as an e-Commerce system admin group, and you have its ID available.</span></span>
- <span data-ttu-id="26a38-125">Você criou um grupo de segurança do Azure AD que pode ser usado como um grupo de moderadores de Classificações e Opiniões e sua ID disponível.</span><span class="sxs-lookup"><span data-stu-id="26a38-125">You've created an Azure AD security group that can be used as a Ratings and Reviews moderator group, and you have its ID available.</span></span> <span data-ttu-id="26a38-126">(Esse grupo de segurança pode ser o mesmo que o grupo de administração de sistema de Comércio eletrônico).</span><span class="sxs-lookup"><span data-stu-id="26a38-126">(This security group can be the same as the e-Commerce system admin group.)</span></span>

<span data-ttu-id="26a38-127">Esta lista não é exaustiva.</span><span class="sxs-lookup"><span data-stu-id="26a38-127">Note that this list isn't exhaustive.</span></span> <span data-ttu-id="26a38-128">Se tiver problemas, fale com o contato do seu parceiro Microsoft para obter ajuda.</span><span class="sxs-lookup"><span data-stu-id="26a38-128">If you experience any issues, reach out to your Microsoft partner contact for assistance.</span></span>

## <a name="provision-your-commerce-evaluation-environment"></a><span data-ttu-id="26a38-129">Provisionar seu ambiente de avaliação do Commerce</span><span class="sxs-lookup"><span data-stu-id="26a38-129">Provision your Commerce evaluation environment</span></span>

<span data-ttu-id="26a38-130">Estes procedimentos explicam como provisionar um ambiente de avaliação do Commerce.</span><span class="sxs-lookup"><span data-stu-id="26a38-130">These procedures explain how to provision a Commerce evaluation environment.</span></span> <span data-ttu-id="26a38-131">Depois que você concluí-los com êxito, o ambiente de avaliação do Commerce estará pronto para a configuração.</span><span class="sxs-lookup"><span data-stu-id="26a38-131">After you successfully complete them, the Commerce evaluation environment will be ready for configuration.</span></span> <span data-ttu-id="26a38-132">Todas as atividades descritas aqui ocorrem no portal do LCS.</span><span class="sxs-lookup"><span data-stu-id="26a38-132">All the activities that are described here occur in the LCS portal.</span></span>

### <a name="create-a-new-project"></a><span data-ttu-id="26a38-133">Criar um novo projeto</span><span class="sxs-lookup"><span data-stu-id="26a38-133">Create a new project</span></span>

<span data-ttu-id="26a38-134">Para criar um novo projeto no LCS, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="26a38-134">To create a new project in LCS, follow these steps.</span></span>

1. <span data-ttu-id="26a38-135">Na home page do LCS, selecione o sinal de mais (**+**) para criar um projeto.</span><span class="sxs-lookup"><span data-stu-id="26a38-135">On the LCS home page, select the plus sign (**+**) to create a project.</span></span>
1. <span data-ttu-id="26a38-136">No painel à direita, siga uma destas etapas:</span><span class="sxs-lookup"><span data-stu-id="26a38-136">In the right pane, follow one of these steps:</span></span>

    - <span data-ttu-id="26a38-137">Se você for um parceiro, selecione **Migrar, criar soluções e conhecer**.</span><span class="sxs-lookup"><span data-stu-id="26a38-137">If you're a partner, select **Migrate, create solutions, and learn**.</span></span>
    - <span data-ttu-id="26a38-138">Se for um cliente, selecione **Pré-vendas de clientes potenciais**.</span><span class="sxs-lookup"><span data-stu-id="26a38-138">If you're a customer, select **Prospective presales**.</span></span>

1. <span data-ttu-id="26a38-139">Inserir um nome, descrição e setor.</span><span class="sxs-lookup"><span data-stu-id="26a38-139">Enter a name, description, and industry.</span></span>
1. <span data-ttu-id="26a38-140">No campo **Nome do produto**, selecione **Dynamics 365 Commerce**.</span><span class="sxs-lookup"><span data-stu-id="26a38-140">In the **Product name** field, select **Dynamics 365 Commerce**.</span></span>
1. <span data-ttu-id="26a38-141">No campo **Versão do produto**, selecione **Dynamics 365 Commerce**.</span><span class="sxs-lookup"><span data-stu-id="26a38-141">In the **Product version** field, select **Dynamics 365 Commerce**.</span></span>
1. <span data-ttu-id="26a38-142">No campo **Metodologia**, selecione **Metodologia de implementação do Dynamics Retail**.</span><span class="sxs-lookup"><span data-stu-id="26a38-142">In the **Methodology** field, select **Dynamics Retail implementation methodology**.</span></span>
1. <span data-ttu-id="26a38-143">Opcional: você pode importar funções e usuários de um projeto existente.</span><span class="sxs-lookup"><span data-stu-id="26a38-143">Optional: You can import roles and users from an existing project.</span></span>
1. <span data-ttu-id="26a38-144">Selecione **Criar**.</span><span class="sxs-lookup"><span data-stu-id="26a38-144">Select **Create**.</span></span> <span data-ttu-id="26a38-145">A exibição do projeto é exibida.</span><span class="sxs-lookup"><span data-stu-id="26a38-145">The project view appears.</span></span>

### <a name="add-the-azure-connector"></a><span data-ttu-id="26a38-146">Adicione o Conector do Azure</span><span class="sxs-lookup"><span data-stu-id="26a38-146">Add the Azure Connector</span></span>

<span data-ttu-id="26a38-147">Para adicionar o Conector do Azure ao projeto do LCS, siga as etapas em [Concluir o processo de integração do Azure Resource Manager (ARM)](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/deployment/arm-onboarding).</span><span class="sxs-lookup"><span data-stu-id="26a38-147">To add the Azure Connector to your LCS project, follow the steps in [Complete the Azure Resource Manager (ARM) onboarding process](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/deployment/arm-onboarding).</span></span>

### <a name="deploy-the-environment"></a><span data-ttu-id="26a38-148">Implantar o ambiente</span><span class="sxs-lookup"><span data-stu-id="26a38-148">Deploy the environment</span></span>

<span data-ttu-id="26a38-149">Para implantar o ambiente, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="26a38-149">To deploy the environment, follow these steps.</span></span>

> [!NOTE]
> <span data-ttu-id="26a38-150">Talvez não seja necessário concluir as etapas 6, 7 e/ou 8, porque as páginas que têm uma única opção são ignoradas.</span><span class="sxs-lookup"><span data-stu-id="26a38-150">You might not have to complete steps 6, 7, and/or 8, because pages that have a single option are skipped.</span></span> <span data-ttu-id="26a38-151">Quando estiver na exibição de **Parâmetros do ambiente**, confirme se o texto **Dynamics 365 Commerce - Demonstração (10.0.* x* com atualização de plataforma *xx*)\*\* aparece diretamente acima do campo **Nome do ambiente**.</span><span class="sxs-lookup"><span data-stu-id="26a38-151">When you're in the **Environment parameters** view, confirm that the text **Dynamics 365 Commerce - Demo (10.0.* x* with Platform update *xx*)\*\* appears directly above the **Environment name** field.</span></span> <span data-ttu-id="26a38-152">Para obter detalhes, consulte a ilustração que aparece após a etapa 8.</span><span class="sxs-lookup"><span data-stu-id="26a38-152">For details, see the illustration that appears after step 8.</span></span>

1. <span data-ttu-id="26a38-153">No menu superior, selecione **Ambientes hospedados na nuvem**.</span><span class="sxs-lookup"><span data-stu-id="26a38-153">On the top menu, select **Cloud-hosted environments**.</span></span>
1. <span data-ttu-id="26a38-154">Selecione **Adicionar** para adicionar um ambiente.</span><span class="sxs-lookup"><span data-stu-id="26a38-154">Select **Add** to add an environment.</span></span>
1. <span data-ttu-id="26a38-155">No campo **Versão do aplicativo**, selecione a versão mais recente.</span><span class="sxs-lookup"><span data-stu-id="26a38-155">In the **Application version** field, select the most current version.</span></span> <span data-ttu-id="26a38-156">Se você tiver uma necessidade específica de selecionar uma versão de aplicativo diferente da versão mais atual, não selecione uma versão antes de **10.0.14.**</span><span class="sxs-lookup"><span data-stu-id="26a38-156">If you have a specific need to select an application version other than the most current version, do not select a version prior to **10.0.14**.</span></span>
1. <span data-ttu-id="26a38-157">No campo **Versão da plataforma**, use a versão da plataforma que é escolhida automaticamente para a versão do aplicativo selecionada.</span><span class="sxs-lookup"><span data-stu-id="26a38-157">In the **Platform version** field, use the platform version that is automatically chosen for the application version you selected.</span></span> 

    ![Seleção das versões do aplicativo e da plataforma](./media/project1.png)

1. <span data-ttu-id="26a38-159">Selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="26a38-159">Select **Next**.</span></span>
1. <span data-ttu-id="26a38-160">Selecione **Demonstração** como a topologia do ambiente.</span><span class="sxs-lookup"><span data-stu-id="26a38-160">Select **Demo** as the environment topology.</span></span>

    ![Selecionar a topologia de ambiente 1](./media/project2.png)

1. <span data-ttu-id="26a38-162">Na página **Implantar ambiente**, insira um nome de ambiente.</span><span class="sxs-lookup"><span data-stu-id="26a38-162">On the **Deploy environment** page, enter an environment name.</span></span> <span data-ttu-id="26a38-163">Deixe as configurações avançadas como estão.</span><span class="sxs-lookup"><span data-stu-id="26a38-163">Leave the advanced settings as they are.</span></span>

    ![Implantar página do ambiente](./media/project4.png)

1. <span data-ttu-id="26a38-165">Ajuste o tamanho da VM, conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="26a38-165">Adjust the VM size as required.</span></span> <span data-ttu-id="26a38-166">(Recomendamos a unidade de manutenção de estoque da VM\[SKU\] **D13 v2**.)</span><span class="sxs-lookup"><span data-stu-id="26a38-166">(We recommend VM stock keeping unit \[SKU\] **D13 v2**.)</span></span>
1. <span data-ttu-id="26a38-167">Revise os termos de definição de preços e licenciamento e marque a caixa de seleção para indicar que você concorda com eles.</span><span class="sxs-lookup"><span data-stu-id="26a38-167">Review the pricing and licensing terms, and then select the check box to indicate that you agree to them.</span></span>
1. <span data-ttu-id="26a38-168">Selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="26a38-168">Select **Next**.</span></span>
1. <span data-ttu-id="26a38-169">Na página de confirmação da implantação, verifique se os detalhes estão corretos e selecione **Implantar**.</span><span class="sxs-lookup"><span data-stu-id="26a38-169">On the deployment confirmation page, verify that the details are correct, and then select **Deploy**.</span></span> <span data-ttu-id="26a38-170">Você voltará à visualização **Ambientes hospedados na nuvem** e seu ambiente deverá aparecer na lista.</span><span class="sxs-lookup"><span data-stu-id="26a38-170">You're returned to the **Cloud-hosted environments** view, and your environment should appear in the list.</span></span>

    <span data-ttu-id="26a38-171">Seu ambiente solicitado aparecerá na fila e, em seguida, será implantado.</span><span class="sxs-lookup"><span data-stu-id="26a38-171">Your requested environment will appear as queued and then deploying.</span></span> <span data-ttu-id="26a38-172">Os fluxos de trabalho de ambiente levarão algum tempo para serem concluídos.</span><span class="sxs-lookup"><span data-stu-id="26a38-172">The environment workflows will take some time to be completed.</span></span> <span data-ttu-id="26a38-173">Portanto, verifique novamente depois de aproximadamente seis a nove horas.</span><span class="sxs-lookup"><span data-stu-id="26a38-173">Therefore, check back after approximately six to nine hours.</span></span>

1. <span data-ttu-id="26a38-174">Antes de continuar, verifique se o status de ambiente está **Implantado**.</span><span class="sxs-lookup"><span data-stu-id="26a38-174">Before you continue, make sure that the status of your environment is **Deployed**.</span></span>

### <a name="initialize-the-commerce-scale-unit-cloud"></a><span data-ttu-id="26a38-175">Inicializar o Commerce Scale Unit (nuvem)</span><span class="sxs-lookup"><span data-stu-id="26a38-175">Initialize the Commerce Scale Unit (cloud)</span></span>

<span data-ttu-id="26a38-176">Para inicializar sua CSU, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="26a38-176">To initialize CSU, follow these steps.</span></span>

1. <span data-ttu-id="26a38-177">Na visualização **Ambientes hospedados na nuvem** selecione seu ambiente da lista.</span><span class="sxs-lookup"><span data-stu-id="26a38-177">In the **Cloud-hosted environments** view, select your environment in the list.</span></span>
1. <span data-ttu-id="26a38-178">Nas visualização do ambiente à direita, selecione **Detalhes completos**.</span><span class="sxs-lookup"><span data-stu-id="26a38-178">In the environment view on the right, select **Full details**.</span></span> <span data-ttu-id="26a38-179">A visualização de detalhes do ambiente é exibida.</span><span class="sxs-lookup"><span data-stu-id="26a38-179">The environment details view appears.</span></span>
1. <span data-ttu-id="26a38-180">Em **Recursos do ambiente**, selecione **Gerenciar**.</span><span class="sxs-lookup"><span data-stu-id="26a38-180">Under **Environment features**, select **Manage**.</span></span>
1. <span data-ttu-id="26a38-181">Na guia **Commerce**, selecione **Inicializar**.</span><span class="sxs-lookup"><span data-stu-id="26a38-181">On the **Commerce** tab, select **Initialize**.</span></span> <span data-ttu-id="26a38-182">A visualização dos parâmetros de inicialização do CSU será exibida.</span><span class="sxs-lookup"><span data-stu-id="26a38-182">The CSU initialization parameters view appears.</span></span>
1. <span data-ttu-id="26a38-183">No campo **Região**, selecione a região que é igual ou próxima à região na qual você implantou o ambiente.</span><span class="sxs-lookup"><span data-stu-id="26a38-183">In the **Region** field, select the region that is the same or close to the region that you deployed the environment to.</span></span>
1. <span data-ttu-id="26a38-184">Deixe o campo **Versão** como está.</span><span class="sxs-lookup"><span data-stu-id="26a38-184">Leave the **Version** field as it is.</span></span>
1. <span data-ttu-id="26a38-185">Selecione **Inicializar**.</span><span class="sxs-lookup"><span data-stu-id="26a38-185">Select **Initialize**.</span></span>
1. <span data-ttu-id="26a38-186">Na página de confirmação da implantação, verifique se os detalhes estão corretos e selecione **Sim**.</span><span class="sxs-lookup"><span data-stu-id="26a38-186">On the deployment confirmation page, verify that the details are correct, and then select **Yes**.</span></span> <span data-ttu-id="26a38-187">O modo **Gerenciamento do Commerce** é reexibido e a guia **Comércio** é selecionada.</span><span class="sxs-lookup"><span data-stu-id="26a38-187">The **Commerce management** view displays again, where the **Commerce** tab is selected.</span></span> <span data-ttu-id="26a38-188">Sua CSU foi enfileirada para provisionamento.</span><span class="sxs-lookup"><span data-stu-id="26a38-188">Your CSU has been queued for provisioning.</span></span>
1. <span data-ttu-id="26a38-189">Antes de continuar, verifique se o status de CSU é **Êxito**.</span><span class="sxs-lookup"><span data-stu-id="26a38-189">Before you continue, make sure that the status of your CSU is **Success**.</span></span> <span data-ttu-id="26a38-190">A inicialização leva cerca de duas a cinco horas.</span><span class="sxs-lookup"><span data-stu-id="26a38-190">Initialization takes approximately two to five hours.</span></span>

<span data-ttu-id="26a38-191">Se não conseguir encontrar o link **Gerenciar** na exibição de detalhes do ambiente, fale com seu contato da Microsoft para obter ajuda.</span><span class="sxs-lookup"><span data-stu-id="26a38-191">If you can't find the **Manage** link in the environment details view, reach out to your Microsoft contact for assistance.</span></span>

### <a name="initialize-e-commerce"></a><span data-ttu-id="26a38-192">Inicializar comércio eletrônico</span><span class="sxs-lookup"><span data-stu-id="26a38-192">Initialize e-Commerce</span></span>

<span data-ttu-id="26a38-193">Para inicializar o comércio eletrônico, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="26a38-193">To initialize e-Commerce, follow these steps.</span></span>

1. <span data-ttu-id="26a38-194">Na guia **Comércio eletrônico**, revise o consentimento da avaliação e selecione **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="26a38-194">On the **e-Commerce** tab, review the evaluation consent, and then select **Setup**.</span></span>
1. <span data-ttu-id="26a38-195">No campo **Nome do ambiente de comércio eletrônico**, insira um nome.</span><span class="sxs-lookup"><span data-stu-id="26a38-195">In the **e-Commerce environment name** field, enter a name.</span></span> <span data-ttu-id="26a38-196">Observe que esse nome estará visível em algumas das URLs que apontam para sua instância de comércio eletrônico.</span><span class="sxs-lookup"><span data-stu-id="26a38-196">Be aware that this name will appear in some of the URLs that point to your e-Commerce instance.</span></span>
1. <span data-ttu-id="26a38-197">No campo **Nome do Commerce Scale Unit**, selecione o seu CSU na lista.</span><span class="sxs-lookup"><span data-stu-id="26a38-197">In the **Commerce Scale Unit name** field, select your CSU in the list.</span></span> <span data-ttu-id="26a38-198">(A lista deve ter apenas uma opção).</span><span class="sxs-lookup"><span data-stu-id="26a38-198">(The list should have only one option.)</span></span>

    <span data-ttu-id="26a38-199">O campo **Geografia de comércio eletrônico** é definido automaticamente.</span><span class="sxs-lookup"><span data-stu-id="26a38-199">The **e-Commerce geography** field is set automatically.</span></span>

1. <span data-ttu-id="26a38-200">Selecione **Avançar** para continuar.</span><span class="sxs-lookup"><span data-stu-id="26a38-200">Select **Next** to continue.</span></span>
1. <span data-ttu-id="26a38-201">No campo **Nomes de host suportados**, insira qualquer domínio válido, como `www.fabrikam.com`.</span><span class="sxs-lookup"><span data-stu-id="26a38-201">In the **Supported host names** field, enter any valid domain, such as `www.fabrikam.com`.</span></span>
1. <span data-ttu-id="26a38-202">No campo **Grupo de segurança do AAD para o administrador do sistema**, insira as primeiras letras do nome do grupo de segurança que você quer usar e selecione o símbolo de lupa para ver os resultados da pesquisa.</span><span class="sxs-lookup"><span data-stu-id="26a38-202">In the **AAD security group for system admin** field, enter the first few letters of the name of the security group that you want to use, and then select the magnifying glass symbol to view the search results.</span></span> <span data-ttu-id="26a38-203">Selecione o grupo de segurança correto na lista.</span><span class="sxs-lookup"><span data-stu-id="26a38-203">Select the correct security group in the list.</span></span>
1.  <span data-ttu-id="26a38-204">No campo **Grupo de segurança do AAD para o moderador de revisão e de avaliações**, insira as primeiras letras do nome do grupo de segurança que você quer usar e selecione o símbolo de lupa para ver os resultados da pesquisa.</span><span class="sxs-lookup"><span data-stu-id="26a38-204">In the **AAD security group for ratings and review moderator** field, enter the first few letters of the name of the security group that you want to use, and then select the magnifying glass symbol to view the search results.</span></span> <span data-ttu-id="26a38-205">Selecione o grupo de segurança correto na lista.</span><span class="sxs-lookup"><span data-stu-id="26a38-205">Select the correct security group in the list.</span></span>
1. <span data-ttu-id="26a38-206">Deixe a opção **Habilitar serviço de classificações e opiniões** como **Sim**.</span><span class="sxs-lookup"><span data-stu-id="26a38-206">Leave the **Enable ratings and review service** option set to **Yes**.</span></span>
1. <span data-ttu-id="26a38-207">Selecione **Inicializar**.</span><span class="sxs-lookup"><span data-stu-id="26a38-207">Select **Initialize**.</span></span> <span data-ttu-id="26a38-208">O modo **Gerenciamento do Commerce** é reexibido e a guia **Comércio eletrônico** é selecionada.</span><span class="sxs-lookup"><span data-stu-id="26a38-208">The **Commerce management** view displays again, where the **e-Commerce** tab is selected.</span></span> <span data-ttu-id="26a38-209">A inicialização de Comércio eletrônico começou.</span><span class="sxs-lookup"><span data-stu-id="26a38-209">E-Commerce initialization has started.</span></span>
1. <span data-ttu-id="26a38-210">Antes de continuar, aguarde até que o status de inicialização do seu comércio eletrônico seja **Inicialização com êxito**.</span><span class="sxs-lookup"><span data-stu-id="26a38-210">Before you continue, wait until the status of e-Commerce initialization is **Initialization successful**.</span></span>
1. <span data-ttu-id="26a38-211">Em **Links** no canto inferior direito, anote as URLs dos seguintes links:</span><span class="sxs-lookup"><span data-stu-id="26a38-211">Under **Links** in the lower right, make a note of the URLs for the following links:</span></span>

    * <span data-ttu-id="26a38-212">**Site de comércio eletrônico** – o link para a raiz do seu site de comércio eletrônico.</span><span class="sxs-lookup"><span data-stu-id="26a38-212">**e-Commerce site** – The link to the root of your e-Commerce site.</span></span>
    * <span data-ttu-id="26a38-213">**Construtor de sites do Commerce** – O link para a ferramenta de gerenciamento de sites.</span><span class="sxs-lookup"><span data-stu-id="26a38-213">**Commerce site builder** – The link to the site management tool.</span></span>

## <a name="next-steps"></a><span data-ttu-id="26a38-214">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="26a38-214">Next steps</span></span>

<span data-ttu-id="26a38-215">Para continuar o processo de provisionamento e configuração de seu ambiente de avaliação do Commerce, consulte [Configurar um ambiente de avaliação do Commerce](cpe-post-provisioning.md).</span><span class="sxs-lookup"><span data-stu-id="26a38-215">To continue the process of provisioning and configuring your Commerce evaluation environment, see [Configure a Commerce evaluation environment](cpe-post-provisioning.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="26a38-216">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="26a38-216">Additional resources</span></span>

[<span data-ttu-id="26a38-217">Visão geral do ambiente de avaliação do Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="26a38-217">Dynamics 365 Commerce evaluation environment overview</span></span>](cpe-overview.md)

[<span data-ttu-id="26a38-218">Configurar um ambiente de avaliação do Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="26a38-218">Configure a Dynamics 365 Commerce evaluation environment</span></span>](cpe-post-provisioning.md)

[<span data-ttu-id="26a38-219">Configurar BOPIS em um ambiente de avaliação do Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="26a38-219">Configure BOPIS in a Dynamics 365 Commerce evaluation environment</span></span>](cpe-bopis.md)

[<span data-ttu-id="26a38-220">Configurar recursos opcionais para um ambiente de avaliação do Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="26a38-220">Configure optional features for a Dynamics 365 Commerce evaluation environment</span></span>](cpe-optional-features.md)

[<span data-ttu-id="26a38-221">Perguntas frequentes sobre o ambiente de avaliação do Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="26a38-221">Dynamics 365 Commerce evaluation environment FAQ</span></span>](cpe-faq.md)

[<span data-ttu-id="26a38-222">Microsoft Lifecycle Services (LCS)</span><span class="sxs-lookup"><span data-stu-id="26a38-222">Microsoft Lifecycle Services (LCS)</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/lifecycle-services/lcs-user-guide)

[<span data-ttu-id="26a38-223">Commerce Scale Unit (nuvem)</span><span class="sxs-lookup"><span data-stu-id="26a38-223">Commerce Scale Unit (cloud)</span></span>](https://docs.microsoft.com/business-applications-release-notes/october18/dynamics365-retail/retail-cloud-scale-unit)

[<span data-ttu-id="26a38-224">Portal do Microsoft Azure</span><span class="sxs-lookup"><span data-stu-id="26a38-224">Microsoft Azure portal</span></span>](https://azure.microsoft.com/features/azure-portal)

[<span data-ttu-id="26a38-225">Site do Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="26a38-225">Dynamics 365 Commerce website</span></span>](https://aka.ms/Dynamics365CommerceWebsite)
