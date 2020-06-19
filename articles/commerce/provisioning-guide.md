---
title: Provisionar um ambiente de visualização do Dynamics 365 Commerce
description: Este tópico explica como provisionar um ambiente de visualização do Microsoft Dynamics 365 Commerce.
author: psimolin
manager: annbe
ms.date: 06/02/2020
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
ms.openlocfilehash: c109c2326cf01739255b49587c15aa34ad884f6a
ms.sourcegitcommit: be7e4378c8122c6e7cfc4e7991efbdffee45e006
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2020
ms.locfileid: "3426456"
---
# <a name="provision-a-dynamics-365-commerce-preview-environment"></a><span data-ttu-id="72066-103">Provisionar um ambiente de visualização do Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="72066-103">Provision a Dynamics 365 Commerce preview environment</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="72066-104">Este tópico explica como provisionar um ambiente de visualização do Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="72066-104">This topic explains how to provision a Dynamics 365 Commerce preview environment.</span></span>

<span data-ttu-id="72066-105">Antes de começar, recomendamos que você faça uma verificação rápida deste tópico para ter uma ideia do que o processo requer.</span><span class="sxs-lookup"><span data-stu-id="72066-105">Before you begin, we recommend that you take a quick scan through this topic to get an idea of what the process requires.</span></span>

> [!NOTE]
> <span data-ttu-id="72066-106">Se ainda não tiver acesso à visualização do Dynamics 365 Commerce, você poderá solicitar o acesso de visualização do [site do Dynamics 365 Commerce](https://aka.ms/Dynamics365CommerceWebsite).</span><span class="sxs-lookup"><span data-stu-id="72066-106">If you haven't yet been granted access to the Dynamics 365 Commerce preview, you can request preview access from the [Dynamics 365 Commerce website](https://aka.ms/Dynamics365CommerceWebsite).</span></span>

## <a name="overview"></a><span data-ttu-id="72066-107">Visão geral</span><span class="sxs-lookup"><span data-stu-id="72066-107">Overview</span></span>

<span data-ttu-id="72066-108">Para provisionar com êxito o seu ambiente de visualização do Commerce, você deve criar um projeto com um nome e um tipo de produto específicos.</span><span class="sxs-lookup"><span data-stu-id="72066-108">To successfully provision your Commerce preview environment, you must create a project that has a specific product name and type.</span></span> <span data-ttu-id="72066-109">O ambiente e o Commerce Scale Unit (CSU) também têm alguns parâmetros específicos que você deve usar ao provisionar o comércio eletrônico posteriormente.</span><span class="sxs-lookup"><span data-stu-id="72066-109">The environment and Commerce Scale Unit (CSU) also have some specific parameters that you must use when you provision e-Commerce later.</span></span> <span data-ttu-id="72066-110">As instruções neste tópico descrevem todas as etapas necessárias para concluir o provisionamento e os parâmetros que devem ser usados.</span><span class="sxs-lookup"><span data-stu-id="72066-110">The instructions in this topic describe all the steps required to complete provisioning and the parameters that you must use.</span></span>

<span data-ttu-id="72066-111">Após o provisionamento bem-sucedido de seu ambiente de visualização do Commerce, você deve concluir algumas etapas de pós-provisionamento para prepará-lo.</span><span class="sxs-lookup"><span data-stu-id="72066-111">After you successfully provision your Commerce preview environment, you must complete a few post-provisioning steps to prepare it.</span></span> <span data-ttu-id="72066-112">Algumas etapas são opcionais, dependendo dos aspectos do sistema você deseja avaliar.</span><span class="sxs-lookup"><span data-stu-id="72066-112">Some steps are optional, depending on the aspects of the system that you want to evaluate.</span></span> <span data-ttu-id="72066-113">Você sempre poderá concluir as etapas opcionais posteriormente.</span><span class="sxs-lookup"><span data-stu-id="72066-113">You can always complete the optional steps later.</span></span>

<span data-ttu-id="72066-114">Para obter informações sobre como configurar seu ambiente de visualização do Commerce depois de provisioná-lo, consulte [Configurar um ambiente de visualização do Commerce](cpe-post-provisioning.md).</span><span class="sxs-lookup"><span data-stu-id="72066-114">For information about how to configure your Commerce preview environment after you provision it, see [Configure a Commerce preview environment](cpe-post-provisioning.md).</span></span> <span data-ttu-id="72066-115">Para obter informações sobre como configurar recursos opcionais de seu ambiente de visualização do Commerce, consulte [Configurar recursos opcionais para um ambiente de visualização do Commerce](cpe-optional-features.md).</span><span class="sxs-lookup"><span data-stu-id="72066-115">For information about how to configure optional features for your Commerce preview environment, see [Configure optional features for a Commerce preview environment](cpe-optional-features.md).</span></span>

<span data-ttu-id="72066-116">Se tiver dúvidas sobre as etapas de provisionamento ou detectar problemas, informe à Microsoft em [Visualização do Microsoft Dynamics 365 Commerce - grupo do Yammer](https://aka.ms/Dynamics365CommercePreviewYammer).</span><span class="sxs-lookup"><span data-stu-id="72066-116">If you have any questions about the provisioning steps, or if you encounter any issues, let Microsoft know in the [Microsoft Dynamics 365 Commerce Preview Yammer group](https://aka.ms/Dynamics365CommercePreviewYammer).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="72066-117">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="72066-117">Prerequisites</span></span>

<span data-ttu-id="72066-118">Os pré-requisitos a seguir devem estar disponíveis para que você possa provisionar o seu ambiente de visualização do Commerce:</span><span class="sxs-lookup"><span data-stu-id="72066-118">The following prerequisites must be in place before you can provision your Commerce preview environment:</span></span>

- <span data-ttu-id="72066-119">Você tem acesso ao portal do Lifecycle Services (LCS) do Microsoft Dynamics.</span><span class="sxs-lookup"><span data-stu-id="72066-119">You have access to the Microsoft Dynamics Lifecycle Services (LCS) portal.</span></span>
- <span data-ttu-id="72066-120">Você é um parceiro ou cliente do Microsoft Dynamics 365 existente e consegue criar um projeto do Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="72066-120">You are an existing Microsoft Dynamics 365 partner or customer and are able to create a Dynamics 365 Commerce project.</span></span>
- <span data-ttu-id="72066-121">Você foi aceito no programa de Visualização do Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="72066-121">You've been accepted into the Dynamics 365 Commerce Preview program.</span></span>
- <span data-ttu-id="72066-122">Você tem as permissões necessárias para criar um projeto para **Migrar, criar soluções e conhecer**.</span><span class="sxs-lookup"><span data-stu-id="72066-122">You have the required permissions to create a project for **Migrate, create solutions, and learn**.</span></span>
- <span data-ttu-id="72066-123">Você é membro da função **Gerente de ambiente** ou **Proprietário do projeto** no projeto no qual você irá provisionar o ambiente.</span><span class="sxs-lookup"><span data-stu-id="72066-123">You're a member of the **Environment manager** or **Project owner** role in the project where you will provision the environment.</span></span>
- <span data-ttu-id="72066-124">Você tem acesso de administrador à sua assinatura do Microsoft Azure ou entra em contato com um administrador de assinatura que pode concluir as duas etapas que exigem permissões de administrador em seu nome.</span><span class="sxs-lookup"><span data-stu-id="72066-124">You have admin access to your Microsoft Azure subscription, or you're in contact with a subscription admin who can complete the two steps that require admin permissions on your behalf.</span></span>
- <span data-ttu-id="72066-125">Você tem sua ID de locatário do Azure Active Directory (Azure AD) disponível.</span><span class="sxs-lookup"><span data-stu-id="72066-125">You have your Azure Active Directory (Azure AD) tenant ID available.</span></span>
- <span data-ttu-id="72066-126">Você criou um grupo de segurança do Azure AD que pode ser usado como um grupo de administradores do sistema do e-Commerce e tem sua ID disponível.</span><span class="sxs-lookup"><span data-stu-id="72066-126">You've created an Azure AD security group that can be used as an e-Commerce system admin group, and you have its ID available.</span></span>
- <span data-ttu-id="72066-127">Você criou um grupo de segurança do Azure AD que pode ser usado como um grupo de moderadores de Classificações e Opiniões e sua ID disponível.</span><span class="sxs-lookup"><span data-stu-id="72066-127">You've created an Azure AD security group that can be used as a Ratings and Reviews moderator group, and you have its ID available.</span></span> <span data-ttu-id="72066-128">(Esse grupo de segurança pode ser o mesmo que o grupo de administração de sistema de Comércio eletrônico).</span><span class="sxs-lookup"><span data-stu-id="72066-128">(This security group can be the same as the e-Commerce system admin group.)</span></span>

## <a name="provision-your-commerce-preview-environment"></a><span data-ttu-id="72066-129">Provisionar seu ambiente de visualização do Commerce</span><span class="sxs-lookup"><span data-stu-id="72066-129">Provision your Commerce preview environment</span></span>

<span data-ttu-id="72066-130">Estes procedimentos explicam como provisionar um ambiente de visualização do Commerce.</span><span class="sxs-lookup"><span data-stu-id="72066-130">These procedures explain how to provision a Commerce preview environment.</span></span> <span data-ttu-id="72066-131">Depois de concluí-los com êxito, o ambiente de visualização do Commerce estará pronto para a configuração.</span><span class="sxs-lookup"><span data-stu-id="72066-131">After you successfully complete them, the Commerce preview environment will be ready for configuration.</span></span> <span data-ttu-id="72066-132">Todas as atividades descritas aqui ocorrem no portal do LCS.</span><span class="sxs-lookup"><span data-stu-id="72066-132">All the activities that are described here occur in the LCS portal.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="72066-133">O acesso de visualização está vinculado à conta e à organização do LCS que você especificou no aplicativo de visualização do Commerce.</span><span class="sxs-lookup"><span data-stu-id="72066-133">Preview access is tied to the LCS account and organization that you specified in your Commerce preview application.</span></span> <span data-ttu-id="72066-134">Você deve usar a mesma conta para provisionar o ambiente de visualização do Commerce.</span><span class="sxs-lookup"><span data-stu-id="72066-134">You must use the same account to provision the Commerce preview environment.</span></span> <span data-ttu-id="72066-135">Se for necessário usar uma conta ou um locatário diferentes da LCS para o ambiente de visualização do Commerce, forneça esses detalhes à Microsoft.</span><span class="sxs-lookup"><span data-stu-id="72066-135">If you need to use a different LCS account or tenant for the Commerce preview environment, you must provide those details to Microsoft.</span></span> <span data-ttu-id="72066-136">Para obter informações de contato, consulte a seção [Suporte ao ambiente de visualização do Commerce](#commerce-preview-environment-support) posteriormente neste tópico.</span><span class="sxs-lookup"><span data-stu-id="72066-136">For contact information, see the [Commerce preview environment support](#commerce-preview-environment-support) section later in this topic.</span></span>

### <a name="confirm-that-preview-features-are-available-and-turned-on-in-lcs"></a><span data-ttu-id="72066-137">Confirme se os recursos de visualização estão disponíveis e habilitados no LCS</span><span class="sxs-lookup"><span data-stu-id="72066-137">Confirm that preview features are available and turned on in LCS</span></span>

<span data-ttu-id="72066-138">Para confirmar se os recursos de visualização estão disponíveis e habilitados no LCS, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="72066-138">To confirm that preview features are available and turned on in LCS, follow these steps.</span></span>

1. <span data-ttu-id="72066-139">Entre no [portal do LCS](https://lcs.dynamics.com) usando a mesma conta da LCS que você usou para solicitar acesso à visualização.</span><span class="sxs-lookup"><span data-stu-id="72066-139">Sign in to the [LCS portal](https://lcs.dynamics.com) by using the same LCS account that you used to request access to the preview.</span></span>
1. <span data-ttu-id="72066-140">Na página inicial do LCS, role para a direita e selecione o bloco **Gerenciamento de recursos de visualização**.</span><span class="sxs-lookup"><span data-stu-id="72066-140">On the LCS home page, scroll all the way to the right, and select the **Preview feature management** tile.</span></span>

    ![Bloco de gerenciamento de visualização](./media/preview1.png)

1. <span data-ttu-id="72066-142">Role para baixo até **Recursos de visualização privada** e confirme se os seguintes recursos estão disponíveis e ativados:</span><span class="sxs-lookup"><span data-stu-id="72066-142">Scroll down to **Private preview features**, and confirm that the following features are available and turned on:</span></span>

    - <span data-ttu-id="72066-143">Avaliação de Comércio eletrônico</span><span class="sxs-lookup"><span data-stu-id="72066-143">e-Commerce Evaluation</span></span>
    - <span data-ttu-id="72066-144">Ambientes do Programa de Visualização do Comércio</span><span class="sxs-lookup"><span data-stu-id="72066-144">Commerce Preview Program Environments</span></span>

    ![Recursos de visualização privada](./media/preview2.png)

1. <span data-ttu-id="72066-146">Se esses recursos não aparecerem na lista, contate a Microsoft e forneça seu endereço de email de trabalho, sua conta LCS e os detalhes do locatário.</span><span class="sxs-lookup"><span data-stu-id="72066-146">If those features don't appear in the list, contact Microsoft, and provide your work email address, LCS account, and tenant details.</span></span> <span data-ttu-id="72066-147">Para obter informações de contato, consulte a seção [Suporte ao ambiente de visualização do Commerce](#commerce-preview-environment-support).</span><span class="sxs-lookup"><span data-stu-id="72066-147">For contact information, see the [Commerce preview environment support](#commerce-preview-environment-support) section.</span></span>

### <a name="create-a-new-project"></a><span data-ttu-id="72066-148">Criar um novo projeto</span><span class="sxs-lookup"><span data-stu-id="72066-148">Create a new project</span></span>

<span data-ttu-id="72066-149">Para criar um novo projeto no LCS, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="72066-149">To create a new project in LCS, follow these steps.</span></span>

1. <span data-ttu-id="72066-150">Na home page do LCS, selecione o sinal de mais (**+**) para criar um projeto.</span><span class="sxs-lookup"><span data-stu-id="72066-150">On the LCS home page, select the plus sign (**+**) to create a project.</span></span>
1. <span data-ttu-id="72066-151">No painel à direita, siga uma destas etapas:</span><span class="sxs-lookup"><span data-stu-id="72066-151">In the right pane, follow one of these steps:</span></span>

    - <span data-ttu-id="72066-152">Se você for um parceiro, selecione **Migrar, criar soluções e conhecer**.</span><span class="sxs-lookup"><span data-stu-id="72066-152">If you're a partner, select **Migrate, create solutions, and learn**.</span></span>
    - <span data-ttu-id="72066-153">Se for um cliente, selecione **Pré-vendas de clientes potenciais**.</span><span class="sxs-lookup"><span data-stu-id="72066-153">If you're a customer, select **Prospective presales**.</span></span>

1. <span data-ttu-id="72066-154">Inserir um nome, descrição e setor.</span><span class="sxs-lookup"><span data-stu-id="72066-154">Enter a name, description, and industry.</span></span>
1. <span data-ttu-id="72066-155">No campo **Nome do produto**, selecione **Dynamics 365 Retail**.</span><span class="sxs-lookup"><span data-stu-id="72066-155">In the **Product name** field, select **Dynamics 365 Retail**.</span></span>
1. <span data-ttu-id="72066-156">No campo **Versão do produto**, selecione **Dynamics 365 Retail**.</span><span class="sxs-lookup"><span data-stu-id="72066-156">In the **Product version** field, select **Dynamics 365 Retail**.</span></span>
1. <span data-ttu-id="72066-157">No campo **Metodologia**, selecione **Metodologia de implementação do Dynamics Retail**.</span><span class="sxs-lookup"><span data-stu-id="72066-157">In the **Methodology** field, select **Dynamics Retail implementation methodology**.</span></span>
1. <span data-ttu-id="72066-158">Opcional: você pode importar funções e usuários de um projeto existente.</span><span class="sxs-lookup"><span data-stu-id="72066-158">Optional: You can import roles and users from an existing project.</span></span>
1. <span data-ttu-id="72066-159">Selecione **Criar**.</span><span class="sxs-lookup"><span data-stu-id="72066-159">Select **Create**.</span></span> <span data-ttu-id="72066-160">A exibição do projeto é exibida.</span><span class="sxs-lookup"><span data-stu-id="72066-160">The project view appears.</span></span>

### <a name="add-the-azure-connector"></a><span data-ttu-id="72066-161">Adicione o Conector do Azure</span><span class="sxs-lookup"><span data-stu-id="72066-161">Add the Azure Connector</span></span>

<span data-ttu-id="72066-162">Para adicionar o Conector do Azure ao seu projeto LCS, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="72066-162">To add the Azure Connector to your LCS project, follow these steps.</span></span>

1. <span data-ttu-id="72066-163">Siga uma destas etapas:</span><span class="sxs-lookup"><span data-stu-id="72066-163">Follow one of these steps:</span></span>

    - <span data-ttu-id="72066-164">Se você for um parceiro, selecione o bloco **Configurações do projeto** na extrema direita.</span><span class="sxs-lookup"><span data-stu-id="72066-164">If you're a partner, select the **Project settings** tile on the far right.</span></span>
    - <span data-ttu-id="72066-165">Se for um cliente, selecione **Configurações do projeto** no menu superior.</span><span class="sxs-lookup"><span data-stu-id="72066-165">If you're a customer, select **Project settings** on the top menu.</span></span>

1. <span data-ttu-id="72066-166">Selecione **Conectores do Azure**.</span><span class="sxs-lookup"><span data-stu-id="72066-166">Select **Azure connectors**.</span></span>
1. <span data-ttu-id="72066-167">Selecione **Adicionar** para adicionar o Conector do Azure.</span><span class="sxs-lookup"><span data-stu-id="72066-167">Select **Add** to add the Azure Connector.</span></span>
1. <span data-ttu-id="72066-168">Insira um nome.</span><span class="sxs-lookup"><span data-stu-id="72066-168">Enter a name.</span></span>
1. <span data-ttu-id="72066-169">Digite sua ID da Assinatura do Azure.</span><span class="sxs-lookup"><span data-stu-id="72066-169">Enter your Azure subscription ID.</span></span>
1. <span data-ttu-id="72066-170">Ativa a opção **Configurar para usar o gerente de recursos do Azure (ARM)**.</span><span class="sxs-lookup"><span data-stu-id="72066-170">Turn on the **Configure to use Azure Resource Manager (ARM)** option.</span></span>
1. <span data-ttu-id="72066-171">Verifique se o valor **Domínio (ou ID) de Locatário do AAD de assinatura do Azure** está correto.</span><span class="sxs-lookup"><span data-stu-id="72066-171">Verify that the **Azure subscription AAD Tenant Domain (or ID)** value is correct.</span></span> <span data-ttu-id="72066-172">Consulte seu administrador de assinatura do Azure, se necessário.</span><span class="sxs-lookup"><span data-stu-id="72066-172">Consult your Azure subscription admin as required.</span></span>
1. <span data-ttu-id="72066-173">Selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="72066-173">Select **Next**.</span></span>
1. <span data-ttu-id="72066-174">Siga as instruções na página para conceder aos aplicativos necessários o acesso à sua assinatura.</span><span class="sxs-lookup"><span data-stu-id="72066-174">Follow the instructions on the page to grant the required applications access to your subscription.</span></span> <span data-ttu-id="72066-175">Consulte seu administrador de assinatura do Azure, se necessário.</span><span class="sxs-lookup"><span data-stu-id="72066-175">Consult your Azure subscription admin as required.</span></span>

    1. <span data-ttu-id="72066-176">Entre no [portal do Azure](https://portal.azure.com/).</span><span class="sxs-lookup"><span data-stu-id="72066-176">Sign in to the [Azure portal](https://portal.azure.com/).</span></span>
    1. <span data-ttu-id="72066-177">Verifique se o diretório correto está selecionado e, no menu à esquerda, selecione **Assinaturas**.</span><span class="sxs-lookup"><span data-stu-id="72066-177">Make sure that the correct directory is selected, and then, on the menu on the left, select **Subscriptions**.</span></span>
    1. <span data-ttu-id="72066-178">Localize a assinatura correta da lista e selecione-a.</span><span class="sxs-lookup"><span data-stu-id="72066-178">Find the correct subscription in the list, and select it.</span></span> <span data-ttu-id="72066-179">Use a funcionalidade de pesquisa, conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="72066-179">Use the search functionality as required.</span></span>
    1. <span data-ttu-id="72066-180">No menu, selecione **Controle de acesso (IAM)**.</span><span class="sxs-lookup"><span data-stu-id="72066-180">On the menu, select **Access control (IAM)**.</span></span>
    1. <span data-ttu-id="72066-181">À direita, em **Adicionar uma atribuição da função**, selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="72066-181">On the right, under **Add a role assignment**, select **Add**.</span></span> <span data-ttu-id="72066-182">O painel **Adicionar atribuição da função** é aberto.</span><span class="sxs-lookup"><span data-stu-id="72066-182">The **Add role assignment** pane appears.</span></span>
    1. <span data-ttu-id="72066-183">No campo **Função**, selecione **Colaborador**.</span><span class="sxs-lookup"><span data-stu-id="72066-183">In the **Role** field, select **Contributor**.</span></span>
    1. <span data-ttu-id="72066-184">No campo **Atribuir acesso a**, mantenha o valor padrão, **usuário, grupo ou entidade de serviço do Azure AD**.</span><span class="sxs-lookup"><span data-stu-id="72066-184">In the **Assign access to** field, leave the default value, **Azure AD user, group, or service principal**.</span></span>
    1. <span data-ttu-id="72066-185">Em **Selecionar**, insira **b96b7e94-b82e-4e71-99a0-cf7fb188acea**.</span><span class="sxs-lookup"><span data-stu-id="72066-185">Under **Select**, enter **b96b7e94-b82e-4e71-99a0-cf7fb188acea**.</span></span>
    1. <span data-ttu-id="72066-186">Selecione **Serviços de Implantação do Dynamics \[ativado por wsfed\]** na lista.</span><span class="sxs-lookup"><span data-stu-id="72066-186">Select **Dynamics Deployment Services \[wsfed-enabled\]** in the list.</span></span>
    1. <span data-ttu-id="72066-187">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="72066-187">Select **Save**.</span></span>

1. <span data-ttu-id="72066-188">Selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="72066-188">Select **Next**.</span></span>
1. <span data-ttu-id="72066-189">Siga as instruções na página para conceder aos aplicativos necessários o acesso à sua assinatura.</span><span class="sxs-lookup"><span data-stu-id="72066-189">Follow the instructions on the page to grant the required applications access to your subscription.</span></span> <span data-ttu-id="72066-190">Consulte seu administrador de assinatura do Azure, se necessário.</span><span class="sxs-lookup"><span data-stu-id="72066-190">Consult your Azure subscription admin as required.</span></span>
1. <span data-ttu-id="72066-191">Selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="72066-191">Select **Next**.</span></span>
1. <span data-ttu-id="72066-192">No campo **região do Azure**, selecione **Leste dos EUA**, **Leste dos EUA 2**, **Oeste dos EUA** ou **Oeste dos EUA 2**.</span><span class="sxs-lookup"><span data-stu-id="72066-192">In the **Azure region** field, select **East US**, **East US 2**, **West US**, or **West US 2**.</span></span>
1. <span data-ttu-id="72066-193">Selecione **Conectar**.</span><span class="sxs-lookup"><span data-stu-id="72066-193">Select **Connect**.</span></span> <span data-ttu-id="72066-194">Seu Conector do Azure deverá aparecer na lista.</span><span class="sxs-lookup"><span data-stu-id="72066-194">Your Azure Connector should appear in the list.</span></span>

### <a name="import-the-commerce-preview-demo-base-extension"></a><span data-ttu-id="72066-195">Importar a Extensão da Demonstração da Versão Prévia do Commerce</span><span class="sxs-lookup"><span data-stu-id="72066-195">Import the Commerce Preview Demo Base Extension</span></span>

<span data-ttu-id="72066-196">Para importar a extensão da demonstração da versão prévia do Commerce para seu projeto, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="72066-196">To import the Commerce Preview Demo Base Extension into your project, follow these steps.</span></span>

1. <span data-ttu-id="72066-197">Abra a home page do seu projeto selecionando o nome do projeto na parte superior.</span><span class="sxs-lookup"><span data-stu-id="72066-197">Open the home page for your project by selecting the project name at the top.</span></span>
1. <span data-ttu-id="72066-198">Siga uma destas etapas:</span><span class="sxs-lookup"><span data-stu-id="72066-198">Follow one of these steps:</span></span>

    - <span data-ttu-id="72066-199">Se você for um parceiro, selecione o bloco **Biblioteca de ativos** na extrema direita.</span><span class="sxs-lookup"><span data-stu-id="72066-199">If you're a partner, select the **Asset library** tile on the far right.</span></span>
    - <span data-ttu-id="72066-200">Se for um cliente, selecione **Biblioteca de ativos** no menu superior.</span><span class="sxs-lookup"><span data-stu-id="72066-200">If you're a customer, select **Asset library** on the top menu.</span></span>

1. <span data-ttu-id="72066-201">Na lista à esquerda, selecione **Pacote de software implantável**.</span><span class="sxs-lookup"><span data-stu-id="72066-201">In the list on the left, select **Software deployable package**.</span></span>
1. <span data-ttu-id="72066-202">Selecione **Importar**.</span><span class="sxs-lookup"><span data-stu-id="72066-202">Select **Import**.</span></span>
1. <span data-ttu-id="72066-203">Em **Biblioteca de ativos compartilhados**, selecione **Extensão da Demonstração da Versão Prévia do Commerce** na lista de ativos.</span><span class="sxs-lookup"><span data-stu-id="72066-203">Under **Shared asset library**, select **Commerce Preview Demo Base Extension** in the list of assets.</span></span>
1. <span data-ttu-id="72066-204">Escolha **Separar**.</span><span class="sxs-lookup"><span data-stu-id="72066-204">Select **Pick**.</span></span> <span data-ttu-id="72066-205">Você retornará à biblioteca de Ativos e deverá ver a extensão na lista.</span><span class="sxs-lookup"><span data-stu-id="72066-205">You're returned to the Asset library, and you should see the extension in the list.</span></span>

<span data-ttu-id="72066-206">A ilustração a seguir mostra as ações que devem ser executadas na página **Biblioteca de ativos** do LCS.</span><span class="sxs-lookup"><span data-stu-id="72066-206">The following illustration shows the actions that must be taken on the LCS **Asset library** page.</span></span>

![Importando a Extensão Base da Demonstração da Versão Prévia do Commerce](./media/import.png)

### <a name="deploy-the-environment"></a><span data-ttu-id="72066-208">Implantar o ambiente</span><span class="sxs-lookup"><span data-stu-id="72066-208">Deploy the environment</span></span>

<span data-ttu-id="72066-209">Para implantar o ambiente, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="72066-209">To deploy the environment, follow these steps.</span></span>

> [!NOTE]
> <span data-ttu-id="72066-210">Talvez não seja necessário concluir as etapas 6, 7 e/ou 8, porque as páginas que têm uma única opção são ignoradas.</span><span class="sxs-lookup"><span data-stu-id="72066-210">You might not have to complete steps 6, 7, and/or 8, because pages that have a single option are skipped.</span></span> <span data-ttu-id="72066-211">Quando estiver na exibição de **Parâmetros do ambiente**, confirme se o texto **Dynamics 365 Commerce - Demonstração (10.0.* x* com atualização de plataforma *xx*)\*\* aparece diretamente acima do campo **Nome do ambiente**.</span><span class="sxs-lookup"><span data-stu-id="72066-211">When you're in the **Environment parameters** view, confirm that the text **Dynamics 365 Commerce - Demo (10.0.* x* with Platform update *xx*)\*\* appears directly above the **Environment name** field.</span></span> <span data-ttu-id="72066-212">Para obter detalhes, consulte a ilustração que aparece após a etapa 8.</span><span class="sxs-lookup"><span data-stu-id="72066-212">For details, see the illustration that appears after step 8.</span></span>

1. <span data-ttu-id="72066-213">No menu superior, selecione **Ambientes hospedados na nuvem**.</span><span class="sxs-lookup"><span data-stu-id="72066-213">On the top menu, select **Cloud-hosted environments**.</span></span>
1. <span data-ttu-id="72066-214">Selecione **Adicionar** para adicionar um ambiente.</span><span class="sxs-lookup"><span data-stu-id="72066-214">Select **Add** to add an environment.</span></span>
1. <span data-ttu-id="72066-215">No campo **Versão do aplicativo**, selecione a versão mais recente.</span><span class="sxs-lookup"><span data-stu-id="72066-215">In the **Application version** field, select the most current version.</span></span> <span data-ttu-id="72066-216">Se você tiver uma necessidade específica de selecionar uma versão de aplicativo diferente da versão mais atual, não selecione uma versão antes de **10.0.8.**</span><span class="sxs-lookup"><span data-stu-id="72066-216">If you have a specific need to select an application version other than the most current version, do not select a version prior to **10.0.8**.</span></span>
1. <span data-ttu-id="72066-217">No campo **Versão da plataforma**, use a versão da plataforma que é escolhida automaticamente para a versão do aplicativo selecionada.</span><span class="sxs-lookup"><span data-stu-id="72066-217">In the **Platform version** field, use the platform version that is automatically chosen for the application version you selected.</span></span> 

    ![Seleção das versões do aplicativo e da plataforma](./media/project1.png)

1. <span data-ttu-id="72066-219">Selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="72066-219">Select **Next**.</span></span>
1. <span data-ttu-id="72066-220">Selecione **Demonstração** como a topologia do ambiente.</span><span class="sxs-lookup"><span data-stu-id="72066-220">Select **Demo** as the environment topology.</span></span>

    ![Selecionar a topologia de ambiente 1](./media/project2.png)

1. <span data-ttu-id="72066-222">Selecione **Dynamics 365 Commerce - Demonstração** como a topologia do ambiente.</span><span class="sxs-lookup"><span data-stu-id="72066-222">Select **Dynamics 365 Commerce - Demo** as the environment topology.</span></span> <span data-ttu-id="72066-223">Se você configurou um único Conector do Azure anteriormente, isso será usado para este ambiente.</span><span class="sxs-lookup"><span data-stu-id="72066-223">If you configured a single Azure Connector earlier, it will be used for this environment.</span></span> <span data-ttu-id="72066-224">Se você configurou vários Conectores do Azure, é possível selecionar qual conector usar: **Leste dos EUA**, **Leste dos EUA 2,** **Oeste dos EUA**, ou **Oeste dos EUA 2**.</span><span class="sxs-lookup"><span data-stu-id="72066-224">If you configured multiple Azure Connectors, you can select which connector to use: **East US**, **East US 2**, **West US**, or **West US 2**.</span></span> <span data-ttu-id="72066-225">(Para obter o melhor desempenho de ponta a ponta, recomendamos que você selecione **Oeste dos EUA 2**.)</span><span class="sxs-lookup"><span data-stu-id="72066-225">(For the best end-to-end performance, we recommend that you select **West US 2**.)</span></span>

    ![Selecionando a topologia de ambiente 2](./media/project3.png)

1. <span data-ttu-id="72066-227">Na página **Implantar ambiente**, insira um nome de ambiente.</span><span class="sxs-lookup"><span data-stu-id="72066-227">On the **Deploy environment** page, enter an environment name.</span></span> <span data-ttu-id="72066-228">Deixe as configurações avançadas como estão.</span><span class="sxs-lookup"><span data-stu-id="72066-228">Leave the advanced settings as they are.</span></span>

    ![Implantar página do ambiente](./media/project4.png)

1. <span data-ttu-id="72066-230">Ajuste o tamanho da VM, conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="72066-230">Adjust the VM size as required.</span></span> <span data-ttu-id="72066-231">(Recomendamos a unidade de manutenção de estoque da VM\[SKU\] **D13 v2**.)</span><span class="sxs-lookup"><span data-stu-id="72066-231">(We recommend VM stock keeping unit \[SKU\] **D13 v2**.)</span></span>
1. <span data-ttu-id="72066-232">Revise os termos de definição de preços e licenciamento e marque a caixa de seleção para indicar que você concorda com eles.</span><span class="sxs-lookup"><span data-stu-id="72066-232">Review the pricing and licensing terms, and then select the check box to indicate that you agree to them.</span></span>
1. <span data-ttu-id="72066-233">Selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="72066-233">Select **Next**.</span></span>
1. <span data-ttu-id="72066-234">Na página de confirmação da implantação, verifique se os detalhes estão corretos e selecione **Implantar**.</span><span class="sxs-lookup"><span data-stu-id="72066-234">On the deployment confirmation page, verify that the details are correct, and then select **Deploy**.</span></span> <span data-ttu-id="72066-235">Você voltará à visualização **Ambientes hospedados na nuvem** e seu ambiente deverá aparecer na lista.</span><span class="sxs-lookup"><span data-stu-id="72066-235">You're returned to the **Cloud-hosted environments** view, and your environment should appear in the list.</span></span>

    <span data-ttu-id="72066-236">Seu ambiente solicitado aparecerá na fila e, em seguida, será implantado.</span><span class="sxs-lookup"><span data-stu-id="72066-236">Your requested environment will appear as queued and then deploying.</span></span> <span data-ttu-id="72066-237">Os fluxos de trabalho de ambiente levarão algum tempo para serem concluídos.</span><span class="sxs-lookup"><span data-stu-id="72066-237">The environment workflows will take some time to be completed.</span></span> <span data-ttu-id="72066-238">Portanto, verifique novamente depois de aproximadamente seis a nove horas.</span><span class="sxs-lookup"><span data-stu-id="72066-238">Therefore, check back after approximately six to nine hours.</span></span>

1. <span data-ttu-id="72066-239">Antes de continuar, verifique se o status de ambiente está **Implantado**.</span><span class="sxs-lookup"><span data-stu-id="72066-239">Before you continue, make sure that the status of your environment is **Deployed**.</span></span>

### <a name="initialize-the-commerce-scale-unit-cloud"></a><span data-ttu-id="72066-240">Inicializar o Commerce Scale Unit (nuvem)</span><span class="sxs-lookup"><span data-stu-id="72066-240">Initialize the Commerce Scale Unit (cloud)</span></span>

<span data-ttu-id="72066-241">Para inicializar sua CSU, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="72066-241">To initialize CSU, follow these steps.</span></span>

1. <span data-ttu-id="72066-242">Na visualização **Ambientes hospedados na nuvem** selecione seu ambiente da lista.</span><span class="sxs-lookup"><span data-stu-id="72066-242">In the **Cloud-hosted environments** view, select your environment in the list.</span></span>
1. <span data-ttu-id="72066-243">Nas visualização do ambiente à direita, selecione **Detalhes completos**.</span><span class="sxs-lookup"><span data-stu-id="72066-243">In the environment view on the right, select **Full details**.</span></span> <span data-ttu-id="72066-244">A visualização de detalhes do ambiente é exibida.</span><span class="sxs-lookup"><span data-stu-id="72066-244">The environment details view appears.</span></span>
1. <span data-ttu-id="72066-245">Em **Recursos do ambiente**, selecione **Gerenciar**.</span><span class="sxs-lookup"><span data-stu-id="72066-245">Under **Environment features**, select **Manage**.</span></span>
1. <span data-ttu-id="72066-246">Na guia **Commerce**, selecione **Inicializar**.</span><span class="sxs-lookup"><span data-stu-id="72066-246">On the **Commerce** tab, select **Initialize**.</span></span> <span data-ttu-id="72066-247">A visualização dos parâmetros de inicialização do CSU será exibida.</span><span class="sxs-lookup"><span data-stu-id="72066-247">The CSU initialization parameters view appears.</span></span>
1. <span data-ttu-id="72066-248">No campo **Região**, selecione **Leste dos EUA**, **Leste dos EUA 2**, **Oeste dos EUA** ou **Oeste dos EUA 2**.</span><span class="sxs-lookup"><span data-stu-id="72066-248">In the **Region** field, select **East US**, **East US 2**, **West US**, or **West US 2**.</span></span>
1. <span data-ttu-id="72066-249">No campo **Versão**, selecione **Especificar uma versão** na lista e, em seguida, especifique **9.18.20014.4** no campo que é exibido.</span><span class="sxs-lookup"><span data-stu-id="72066-249">In the **Version** field, select **Specify a version** in the list, and then specify **9.18.20014.4** in the field that appears.</span></span> <span data-ttu-id="72066-250">Certifique-se de especificar a versão exata indicada aqui.</span><span class="sxs-lookup"><span data-stu-id="72066-250">Be sure to specify the exact version that is indicated here.</span></span> <span data-ttu-id="72066-251">Caso contrário, será necessário atualizar a RCSU para a versão correta posteriormente.</span><span class="sxs-lookup"><span data-stu-id="72066-251">Otherwise, you will have to update RCSU to the correct version later.</span></span>
1. <span data-ttu-id="72066-252">Ative a opção **Aplicar extensão**.</span><span class="sxs-lookup"><span data-stu-id="72066-252">Turn on the **Apply extension** option.</span></span>
1. <span data-ttu-id="72066-253">Na lista de extensões, selecione **Extensão da Demonstração da Versão Prévia do Commerce**.</span><span class="sxs-lookup"><span data-stu-id="72066-253">In the list of extensions, select **Commerce Preview Demo Base Extension**.</span></span>
1. <span data-ttu-id="72066-254">Selecione **Inicializar**.</span><span class="sxs-lookup"><span data-stu-id="72066-254">Select **Initialize**.</span></span>
1. <span data-ttu-id="72066-255">Na página de confirmação da implantação, verifique se os detalhes estão corretos e selecione **Sim**.</span><span class="sxs-lookup"><span data-stu-id="72066-255">On the deployment confirmation page, verify that the details are correct, and then select **Yes**.</span></span> <span data-ttu-id="72066-256">O modo **Gerenciamento do Commerce** é reexibido e a guia **Comércio** é selecionada.</span><span class="sxs-lookup"><span data-stu-id="72066-256">The **Commerce management** view displays again, where the **Commerce** tab is selected.</span></span> <span data-ttu-id="72066-257">Sua CSU foi enfileirada para provisionamento.</span><span class="sxs-lookup"><span data-stu-id="72066-257">Your CSU has been queued for provisioning.</span></span>
1. <span data-ttu-id="72066-258">Antes de continuar, verifique se o status de CSU é **Êxito**.</span><span class="sxs-lookup"><span data-stu-id="72066-258">Before you continue, make sure that the status of your CSU is **Success**.</span></span> <span data-ttu-id="72066-259">A inicialização leva cerca de duas a cinco horas.</span><span class="sxs-lookup"><span data-stu-id="72066-259">Initialization takes approximately two to five hours.</span></span>

### <a name="initialize-e-commerce"></a><span data-ttu-id="72066-260">Inicializar comércio eletrônico</span><span class="sxs-lookup"><span data-stu-id="72066-260">Initialize e-Commerce</span></span>

<span data-ttu-id="72066-261">Para inicializar o comércio eletrônico, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="72066-261">To initialize e-Commerce, follow these steps.</span></span>

1. <span data-ttu-id="72066-262">Na guia **Comércio eletrônico**, revise o consentimento da visualização e, depois, selecione **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="72066-262">On the **e-Commerce** tab, review the preview consent, and then select **Setup**.</span></span>
1. <span data-ttu-id="72066-263">No campo **Nome do locatário de comércio eletrônico**, informe um nome.</span><span class="sxs-lookup"><span data-stu-id="72066-263">In the **e-Commerce tenant name** field, enter a name.</span></span> <span data-ttu-id="72066-264">No entanto, observe que este nome estará visível em algumas das URLs que apontam para sua instância de comércio eletrônico.</span><span class="sxs-lookup"><span data-stu-id="72066-264">However, be aware that this name will appear in some of the URLs that point to your e-Commerce instance.</span></span>
1. <span data-ttu-id="72066-265">No campo **Nome do Commerce Scale Unit**, selecione o seu CSU na lista.</span><span class="sxs-lookup"><span data-stu-id="72066-265">In the **Commerce Scale Unit name** field, select your CSU in the list.</span></span> <span data-ttu-id="72066-266">(A lista deve ter apenas uma opção).</span><span class="sxs-lookup"><span data-stu-id="72066-266">(The list should have only one option.)</span></span>

    <span data-ttu-id="72066-267">O **Geografia de comércio eletrônico** é definido automaticamente, e o valor não pode ser alterado.</span><span class="sxs-lookup"><span data-stu-id="72066-267">The **e-Commerce geography** field is set automatically, and the value can't be changed.</span></span>

1. <span data-ttu-id="72066-268">Selecione **Avançar** para continuar.</span><span class="sxs-lookup"><span data-stu-id="72066-268">Select **Next** to continue.</span></span>
1. <span data-ttu-id="72066-269">No campo **Nomes de host suportados**, insira qualquer domínio válido, como `www.fabrikam.com`.</span><span class="sxs-lookup"><span data-stu-id="72066-269">In the **Supported host names** field, enter any valid domain, such as `www.fabrikam.com`.</span></span>
1.  <span data-ttu-id="72066-270">No campo **Grupo de segurança do AAD para o administrador do sistema**, insira as primeiras letras do nome do grupo de segurança que você deseja usar.</span><span class="sxs-lookup"><span data-stu-id="72066-270">In the **AAD security group for system admin** field, enter the first few letters of the name of the security group that you want to use.</span></span> <span data-ttu-id="72066-271">Selecione o ícone de lupa para exibir os resultados da pesquisa.</span><span class="sxs-lookup"><span data-stu-id="72066-271">Select the magnifying class icon to display the search results.</span></span> <span data-ttu-id="72066-272">Selecione o grupo de segurança correto na lista.</span><span class="sxs-lookup"><span data-stu-id="72066-272">Select the correct security group from the list.</span></span>
2.  <span data-ttu-id="72066-273">No campo **Grupo de segurança do AAD para o moderador de revisão e de avaliações**, insira as primeiras letras do nome do grupo de segurança que você deseja usar.</span><span class="sxs-lookup"><span data-stu-id="72066-273">In the **AAD security group for ratings and review moderator** field, enter the first few letters of the name of the security group that you want to use.</span></span> <span data-ttu-id="72066-274">Selecione o ícone de lupa para exibir os resultados da pesquisa.</span><span class="sxs-lookup"><span data-stu-id="72066-274">Select the magnifying class icon to display the search results.</span></span> <span data-ttu-id="72066-275">Selecione o grupo de segurança correto na lista.</span><span class="sxs-lookup"><span data-stu-id="72066-275">Select the correct security group from the list.</span></span>
1. <span data-ttu-id="72066-276">Deixe a opção **Habilitar classificações e examinar o serviço** ativada.</span><span class="sxs-lookup"><span data-stu-id="72066-276">Leave the **Enable ratings and review service** option turned on.</span></span>
1. <span data-ttu-id="72066-277">Selecione **Inicializar**.</span><span class="sxs-lookup"><span data-stu-id="72066-277">Select **Initialize**.</span></span> <span data-ttu-id="72066-278">O modo **Gerenciamento do Commerce** é reexibido e a guia **Comércio eletrônico** é selecionada.</span><span class="sxs-lookup"><span data-stu-id="72066-278">The **Commerce management** view displays again, where the **e-Commerce** tab is selected.</span></span> <span data-ttu-id="72066-279">A inicialização de Comércio eletrônico começou.</span><span class="sxs-lookup"><span data-stu-id="72066-279">E-Commerce initialization has started.</span></span>
1. <span data-ttu-id="72066-280">Antes de continuar, aguarde até que o status de inicialização do seu comércio eletrônico seja **Inicialização com êxito**.</span><span class="sxs-lookup"><span data-stu-id="72066-280">Before you continue, wait until the status of e-Commerce initialization is **Initialization successful**.</span></span>
1. <span data-ttu-id="72066-281">Em **Links** no canto inferior direito, anote as URLs dos seguintes links:</span><span class="sxs-lookup"><span data-stu-id="72066-281">Under **Links** in the lower right, make a note of the URLs for the following links:</span></span>

    * <span data-ttu-id="72066-282">**Site de comércio eletrônico** – o link para a raiz do seu site de comércio eletrônico.</span><span class="sxs-lookup"><span data-stu-id="72066-282">**e-Commerce site** – The link to the root of your e-Commerce site.</span></span>
    * <span data-ttu-id="72066-283">**Ferramenta de gerenciamento de site de comércio eletrônico** – o link para a ferramenta de gerenciamento de site.</span><span class="sxs-lookup"><span data-stu-id="72066-283">**e-Commerce site management tool** – The link to the site management tool.</span></span>

## <a name="commerce-preview-environment-support"></a><span data-ttu-id="72066-284">Suporte ao ambiente de visualização do Commerce</span><span class="sxs-lookup"><span data-stu-id="72066-284">Commerce preview environment support</span></span>

<span data-ttu-id="72066-285">Se você tiver problemas ao concluir as etapas de provisionamento, visite [Visualização do Microsoft Dynamics 365 Commerce - grupo Yammer](https://aka.ms/Dynamics365CommercePreviewYammer) para obter ajuda.</span><span class="sxs-lookup"><span data-stu-id="72066-285">If you experience issues while you're completing the provisioning steps, visit the [Microsoft Dynamics 365 Commerce Preview Yammer group](https://aka.ms/Dynamics365CommercePreviewYammer) for help.</span></span>

## <a name="next-steps"></a><span data-ttu-id="72066-286">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="72066-286">Next steps</span></span>

<span data-ttu-id="72066-287">Para continuar o processo de provisionamento e configuração de seu ambiente de visualização do Commerce, consulte [Configurar um ambiente de visualização do Commerce](cpe-post-provisioning.md).</span><span class="sxs-lookup"><span data-stu-id="72066-287">To continue the process of provisioning and configuring your Commerce preview environment, see [Configure a Commerce preview environment](cpe-post-provisioning.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="72066-288">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="72066-288">Additional resources</span></span>

[<span data-ttu-id="72066-289">Visão geral do ambiente de visualização do Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="72066-289">Dynamics 365 Commerce preview environment overview</span></span>](cpe-overview.md)

[<span data-ttu-id="72066-290">Configurar um ambiente de visualização do Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="72066-290">Configure a Dynamics 365 Commerce preview environment</span></span>](cpe-post-provisioning.md)

[<span data-ttu-id="72066-291">Configurar recursos opcionais para um ambiente de visualização do Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="72066-291">Configure optional features for a Dynamics 365 Commerce preview environment</span></span>](cpe-optional-features.md)

[<span data-ttu-id="72066-292">Perguntas frequentes do ambiente de visualização do Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="72066-292">Dynamics 365 Commerce preview environment FAQ</span></span>](cpe-faq.md)

[<span data-ttu-id="72066-293">Microsoft Lifecycle Services (LCS)</span><span class="sxs-lookup"><span data-stu-id="72066-293">Microsoft Lifecycle Services (LCS)</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/lifecycle-services/lcs-user-guide)

[<span data-ttu-id="72066-294">Commerce Scale Unit (nuvem)</span><span class="sxs-lookup"><span data-stu-id="72066-294">Commerce Scale Unit (cloud)</span></span>](https://docs.microsoft.com/business-applications-release-notes/october18/dynamics365-retail/retail-cloud-scale-unit)

[<span data-ttu-id="72066-295">Portal do Microsoft Azure</span><span class="sxs-lookup"><span data-stu-id="72066-295">Microsoft Azure portal</span></span>](https://azure.microsoft.com/features/azure-portal)

[<span data-ttu-id="72066-296">Site do Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="72066-296">Dynamics 365 Commerce website</span></span>](https://aka.ms/Dynamics365CommerceWebsite)

