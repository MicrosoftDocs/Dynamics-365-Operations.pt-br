---
title: Provisionar um ambiente de visualização do Commerce
description: Este tópico explica como provisionar um ambiente de visualização do Microsoft Dynamics 365 Commerce.
author: psimolin
manager: annbe
ms.date: 01/06/2020
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
ms.openlocfilehash: b77d2cbbc100aeae5dcd53ddbe69ff2e4435da13
ms.sourcegitcommit: 4d77d06a07ec9e7a3fcbd508afdffaa406fd3dd8
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/06/2020
ms.locfileid: "2934739"
---
# <a name="provision-a-commerce-preview-environment"></a><span data-ttu-id="2998e-103">Provisionar um ambiente de visualização do Commerce</span><span class="sxs-lookup"><span data-stu-id="2998e-103">Provision a Commerce preview environment</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="2998e-104">Este tópico explica como provisionar um ambiente de visualização do Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="2998e-104">This topic explains how to provision a Microsoft Dynamics 365 Commerce preview environment.</span></span>

<span data-ttu-id="2998e-105">Antes de começar, recomendamos que você pelo menos olhe a documentação de todo este tópico para ter uma ideia do que o processo implica e do que este tópico contém.</span><span class="sxs-lookup"><span data-stu-id="2998e-105">Before you begin, we recommend that you at least skim through this whole topic to get an idea of what the process entails and what this topic contains.</span></span>

> [!NOTE]
> <span data-ttu-id="2998e-106">Se ainda não tiver acesso à visualização do Dynamics 365 Commerce, você pode solicitar o acesso de visualização do [site do Commerce](https://aka.ms/Dynamics365CommerceWebsite).</span><span class="sxs-lookup"><span data-stu-id="2998e-106">If you haven't yet been granted access to the Dynamics 365 Commerce preview, you can request preview access from the [Commerce website](https://aka.ms/Dynamics365CommerceWebsite).</span></span>

## <a name="overview"></a><span data-ttu-id="2998e-107">Visão geral</span><span class="sxs-lookup"><span data-stu-id="2998e-107">Overview</span></span>

<span data-ttu-id="2998e-108">Para provisionar com êxito o seu ambiente de visualização do Commerce, você deve criar um projeto com um nome e um tipo de produto específicos.</span><span class="sxs-lookup"><span data-stu-id="2998e-108">To successfully provision your Commerce preview environment, you must create a project that has a specific product name and type.</span></span> <span data-ttu-id="2998e-109">O ambiente e o Retail Cloud Scale Unit (RCSU) também têm alguns parâmetros específicos que você deve usar ao provisionar o comércio eletrônico posteriormente.</span><span class="sxs-lookup"><span data-stu-id="2998e-109">The environment and Retail Cloud Scale Unit (RCSU) also have some specific parameters that you must use when you provision e-Commerce later.</span></span> <span data-ttu-id="2998e-110">As instruções neste tópico descrevem todas as etapas necessárias que devem ser concluídas e os parâmetros que devem ser usados.</span><span class="sxs-lookup"><span data-stu-id="2998e-110">The instructions in this topic describe all the required steps that you must complete and the parameters that you must use.</span></span>

<span data-ttu-id="2998e-111">Após o provisionamento bem-sucedido de seu ambiente de visualização do Commerce, você deve concluir algumas etapas de pós-provisionamento para prepará-lo.</span><span class="sxs-lookup"><span data-stu-id="2998e-111">After you successfully provision your Commerce preview environment, you must complete a few post-provisioning steps to prepare it.</span></span> <span data-ttu-id="2998e-112">Algumas etapas são opcionais, dependendo dos aspectos do sistema você deseja avaliar.</span><span class="sxs-lookup"><span data-stu-id="2998e-112">Some steps are optional, depending on the aspects of the system that you want to evaluate.</span></span> <span data-ttu-id="2998e-113">Você sempre poderá concluir as etapas opcionais posteriormente.</span><span class="sxs-lookup"><span data-stu-id="2998e-113">You can always complete the optional steps later.</span></span>

<span data-ttu-id="2998e-114">Para obter informações sobre como configurar seu ambiente de visualização do Commerce depois de provisioná-lo, consulte [Configurar um ambiente de visualização do Commerce](cpe-post-provisioning.md).</span><span class="sxs-lookup"><span data-stu-id="2998e-114">For information about how to configure your Commerce preview environment after you provision it, see [Configure a Commerce preview environment](cpe-post-provisioning.md).</span></span> <span data-ttu-id="2998e-115">Para obter informações sobre como configurar recursos opcionais de seu ambiente de visualização do Commerce, consulte [Configurar recursos opcionais para um ambiente de visualização do Commerce](cpe-optional-features.md).</span><span class="sxs-lookup"><span data-stu-id="2998e-115">For information about how to configure optional features for your Commerce preview environment, see [Configure optional features for a Commerce preview environment](cpe-optional-features.md).</span></span>

<span data-ttu-id="2998e-116">Se tiver dúvidas sobre as etapas de provisionamento ou detectar problemas, informe à Microsoft em [Visualização do Microsoft Dynamics 365 Commerce - grupo do Yammer](https://aka.ms/Dynamics365CommercePreviewYammer).</span><span class="sxs-lookup"><span data-stu-id="2998e-116">If you have any questions about the provisioning steps, or if you encounter any issues, let Microsoft know in the [Microsoft Dynamics 365 Commerce Preview Yammer group](https://aka.ms/Dynamics365CommercePreviewYammer).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="2998e-117">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="2998e-117">Prerequisites</span></span>

<span data-ttu-id="2998e-118">Os pré-requisitos a seguir devem estar disponíveis para que você possa provisionar o seu ambiente de visualização do Commerce:</span><span class="sxs-lookup"><span data-stu-id="2998e-118">The following prerequisites must be in place before you can provision your Commerce preview environment:</span></span>

- <span data-ttu-id="2998e-119">Você tem acesso ao portal do Lifecycle Services (LCS) do Microsoft Dynamics.</span><span class="sxs-lookup"><span data-stu-id="2998e-119">You have access to the Microsoft Dynamics Lifecycle Services (LCS) portal.</span></span>
- <span data-ttu-id="2998e-120">Você foi aceito no programa de Visualização do Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="2998e-120">You've been accepted into the Dynamics 365 Commerce Preview program.</span></span>
- <span data-ttu-id="2998e-121">Você tem as permissões necessárias para criar um projeto para **Pré-vendas de clientes potenciais** ou **Migrar, criar soluções e conhecer**</span><span class="sxs-lookup"><span data-stu-id="2998e-121">You have the required permissions to create a project for **Prospective presales** or **Migrate, create solutions, and learn**.</span></span>
- <span data-ttu-id="2998e-122">Você é membro da função **Gerente de ambiente** ou **Proprietário do projeto** no projeto no qual você irá provisionar o ambiente.</span><span class="sxs-lookup"><span data-stu-id="2998e-122">You're a member of the **Environment manager** or **Project owner** role in the project where you will provision the environment.</span></span>
- <span data-ttu-id="2998e-123">Você tem acesso de administrador à sua assinatura do Microsoft Azure ou entra em contato com um administrador de assinatura que pode concluir as duas etapas que exigem permissões de administrador em seu nome.</span><span class="sxs-lookup"><span data-stu-id="2998e-123">You have admin access to your Microsoft Azure subscription, or you're in contact with a subscription admin who can complete the two steps that require admin permissions on your behalf.</span></span>
- <span data-ttu-id="2998e-124">Você tem sua ID de locatário do Azure Active Directory (Azure AD) disponível.</span><span class="sxs-lookup"><span data-stu-id="2998e-124">You have your Azure Active Directory (Azure AD) tenant ID available.</span></span>
- <span data-ttu-id="2998e-125">Você criou um grupo de segurança do Azure AD que pode ser usado como um grupo de administradores do sistema do e-Commerce e tem sua ID disponível.</span><span class="sxs-lookup"><span data-stu-id="2998e-125">You've created an Azure AD security group that can be used as an e-Commerce system admin group, and you have its ID available.</span></span>
- <span data-ttu-id="2998e-126">Você criou um grupo de segurança do Azure AD que pode ser usado como um grupo de moderadores de Classificações e Opiniões e sua ID disponível.</span><span class="sxs-lookup"><span data-stu-id="2998e-126">You've created an Azure AD security group that can be used as a Ratings and Reviews moderator group, and you have its ID available.</span></span> <span data-ttu-id="2998e-127">(Esse grupo de segurança pode ser o mesmo que o grupo de administração de sistema de Comércio eletrônico).</span><span class="sxs-lookup"><span data-stu-id="2998e-127">(This security group can be the same as the e-Commerce system admin group.)</span></span>

### <a name="find-your-azure-ad-tenant-id"></a><span data-ttu-id="2998e-128">Como encontrar sua ID do locatário de Azure AD</span><span class="sxs-lookup"><span data-stu-id="2998e-128">Find your Azure AD tenant ID</span></span>

<span data-ttu-id="2998e-129">Sua ID de locatário do Azure AD é um identificador exclusivo globalmente (GUID) que é semelhante a este exemplo: **72f988bf-86f1-41af-91ab-2d7cd011db47**.</span><span class="sxs-lookup"><span data-stu-id="2998e-129">Your Azure AD tenant ID is a globally unique identifier (GUID) that resembles this example: **72f988bf-86f1-41af-91ab-2d7cd011db47**.</span></span>

#### <a name="find-your-azure-ad-tenant-id-by-using-the-azure-portal"></a><span data-ttu-id="2998e-130">Localizar sua ID de locatário do Azure AD usando o portal do Azure</span><span class="sxs-lookup"><span data-stu-id="2998e-130">Find your Azure AD tenant ID by using the Azure portal</span></span>

1. <span data-ttu-id="2998e-131">Entre no [portal do Azure](https://portal.azure.com/).</span><span class="sxs-lookup"><span data-stu-id="2998e-131">Sign in to the [Azure portal](https://portal.azure.com/).</span></span>
1. <span data-ttu-id="2998e-132">Verifique se o diretório correto foi selecionado.</span><span class="sxs-lookup"><span data-stu-id="2998e-132">Make sure that the correct directory is selected.</span></span>
1. <span data-ttu-id="2998e-133">No menu à esquerda, selecione **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="2998e-133">On the menu on the left, select **Azure Active Directory**.</span></span>
1. <span data-ttu-id="2998e-134">Em **Gerenciar**, selecione **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="2998e-134">Under **Manage**, select **Properties**.</span></span> <span data-ttu-id="2998e-135">Sua ID de locatário do Azure AD aparece em **ID do Diretório**.</span><span class="sxs-lookup"><span data-stu-id="2998e-135">Your Azure AD tenant ID appears under **Directory ID**.</span></span>

#### <a name="find-your-azure-ad-tenant-id-by-using-openid-connect-metadata"></a><span data-ttu-id="2998e-136">Encontre sua ID de locatário do Azure AD usando os metadados de Conexão de OpenID</span><span class="sxs-lookup"><span data-stu-id="2998e-136">Find your Azure AD tenant ID by using OpenID Connect metadata</span></span>

<span data-ttu-id="2998e-137">Crie uma URL de OpenID substituindo **\{YOUR\_DOMAIN\}** com seu domínio, como `microsoft.com`.</span><span class="sxs-lookup"><span data-stu-id="2998e-137">Create an OpenID URL by replacing **\{YOUR\_DOMAIN\}** with your domain, such as `microsoft.com`.</span></span> <span data-ttu-id="2998e-138">Por exemplo, `https://login.microsoftonline.com/{YOUR_DOMAIN}/.well-known/openid-configuration` ficará `https://login.microsoftonline.com/microsoft.com/.well-known/openid-configuration`.</span><span class="sxs-lookup"><span data-stu-id="2998e-138">For example, `https://login.microsoftonline.com/{YOUR_DOMAIN}/.well-known/openid-configuration` will become `https://login.microsoftonline.com/microsoft.com/.well-known/openid-configuration`.</span></span>

1. <span data-ttu-id="2998e-139">Vá para o URL do OpenID que contém o seu domínio.</span><span class="sxs-lookup"><span data-stu-id="2998e-139">Go to the OpenID URL that contains your domain.</span></span>

    <span data-ttu-id="2998e-140">Você pode localizar sua ID de locatário do Azure AD em vários valores da propriedade.</span><span class="sxs-lookup"><span data-stu-id="2998e-140">You can find you Azure AD tenant ID in multiple property values.</span></span>

1. <span data-ttu-id="2998e-141">Localize **authorization\_endpoint** e extraia a GUID que aparece imediatamente após `login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="2998e-141">Find **authorization\_endpoint**, and extract the GUID that appears immediately after `login.microsoftonline.com/`.</span></span>

### <a name="find-your-azure-ad-security-group-id"></a><span data-ttu-id="2998e-142">Localizar a ID do grupo de segurança do Azure AD</span><span class="sxs-lookup"><span data-stu-id="2998e-142">Find your Azure AD security group ID</span></span>

<span data-ttu-id="2998e-143">A ID do grupo de segurança do Azure AD é um GUID semelhante a este exemplo: **436ea7f5-ee6c-40c1-9f08-825c5811066a**.</span><span class="sxs-lookup"><span data-stu-id="2998e-143">The ID of your Azure AD security group is a GUID that resembles this example: **436ea7f5-ee6c-40c1-9f08-825c5811066a**.</span></span>

<span data-ttu-id="2998e-144">Este procedimento pressupõe que você seja membro do grupo para o qual você está tentando encontrar a ID.</span><span class="sxs-lookup"><span data-stu-id="2998e-144">This procedure assumes that you're a member of the group that you're trying to find the ID for.</span></span>

1. <span data-ttu-id="2998e-145">Abra o [Gerenciador de Gráficos](https://developer.microsoft.com/graph/graph-explorer#).</span><span class="sxs-lookup"><span data-stu-id="2998e-145">Open the [Graph Explorer](https://developer.microsoft.com/graph/graph-explorer#).</span></span>
1. <span data-ttu-id="2998e-146">Selecione **Entrar com a conta da Microsoft** e entre usando suas credenciais.</span><span class="sxs-lookup"><span data-stu-id="2998e-146">Select **Sign In with Microsoft**, and sign in by using your credentials.</span></span>
1. <span data-ttu-id="2998e-147">À esquerda, selecione **mostrar mais exemplos.**</span><span class="sxs-lookup"><span data-stu-id="2998e-147">On the left, select **show more samples**.</span></span>
1. <span data-ttu-id="2998e-148">No painel à direita, habilite **Grupos**.</span><span class="sxs-lookup"><span data-stu-id="2998e-148">In the right pane, enable **Groups**.</span></span>
1. <span data-ttu-id="2998e-149">Feche o painel direito.</span><span class="sxs-lookup"><span data-stu-id="2998e-149">Close the right pane.</span></span>
1. <span data-ttu-id="2998e-150">Selecione **todos os grupos aos quais eu pertenço**.</span><span class="sxs-lookup"><span data-stu-id="2998e-150">Select **all groups I belong to**.</span></span>
1. <span data-ttu-id="2998e-151">No campo **Visualização de Resposta**, localize seu grupo.</span><span class="sxs-lookup"><span data-stu-id="2998e-151">In the **Response Preview** field, find your group.</span></span> <span data-ttu-id="2998e-152">A ID do grupo de segurança aparece na propriedade **id**.</span><span class="sxs-lookup"><span data-stu-id="2998e-152">The security group ID appears under the **id** property.</span></span>

## <a name="provision-your-commerce-preview-environment"></a><span data-ttu-id="2998e-153">Provisionar seu ambiente de visualização do Commerce</span><span class="sxs-lookup"><span data-stu-id="2998e-153">Provision your Commerce preview environment</span></span>

<span data-ttu-id="2998e-154">Estes procedimentos explicam como provisionar um ambiente de visualização do Commerce.</span><span class="sxs-lookup"><span data-stu-id="2998e-154">These procedures explain how to provision a Commerce preview environment.</span></span> <span data-ttu-id="2998e-155">Depois de concluí-los com êxito, o ambiente de visualização do Commerce estará pronto para a configuração.</span><span class="sxs-lookup"><span data-stu-id="2998e-155">After you successfully complete them, the Commerce preview environment will be ready for configuration.</span></span> <span data-ttu-id="2998e-156">Todas as atividades descritas aqui ocorrem no portal do LCS.</span><span class="sxs-lookup"><span data-stu-id="2998e-156">All the activities that are described here occur in the LCS portal.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2998e-157">O acesso de visualização está vinculado à conta e à organização do LCS que você especificou no aplicativo de visualização.</span><span class="sxs-lookup"><span data-stu-id="2998e-157">Preview access is tied to the LCS account and organization that you specified in your preview application.</span></span> <span data-ttu-id="2998e-158">Você deve usar a mesma conta para provisionar o ambiente de visualização do Commerce.</span><span class="sxs-lookup"><span data-stu-id="2998e-158">You must use the same account to provision the Commerce preview environment.</span></span> <span data-ttu-id="2998e-159">Se for necessário usar uma conta ou um locatário diferentes da LCS para o ambiente de visualização do Commerce, você deverá fornecer esses detalhes à Microsoft.</span><span class="sxs-lookup"><span data-stu-id="2998e-159">If you must use a different LCS account or tenant for the Commerce preview environment, you must provide those details to Microsoft.</span></span> <span data-ttu-id="2998e-160">Para obter informações de contato, consulte a seção [Suporte ao ambiente de visualização do Commerce](#commerce-preview-environment-support) posteriormente neste tópico.</span><span class="sxs-lookup"><span data-stu-id="2998e-160">For contact information, see the [Commerce preview environment support](#commerce-preview-environment-support) section later in this topic.</span></span>

### <a name="grant-access-to-e-commerce-applications"></a><span data-ttu-id="2998e-161">Conceder acesso aos aplicativos de comércio eletrônico</span><span class="sxs-lookup"><span data-stu-id="2998e-161">Grant access to e-Commerce applications</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2998e-162">A pessoa que faz logon deve ser um administrador de locatário do Azure AD que tem a ID do locatário do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="2998e-162">The person who signs in must be an Azure AD tenant admin who has the Azure AD tenant ID.</span></span> <span data-ttu-id="2998e-163">Se essa etapa não for concluída com êxito, as etapas de provisionamento restantes falharão.</span><span class="sxs-lookup"><span data-stu-id="2998e-163">If this step isn't successfully completed, the remaining provisioning steps will fail.</span></span>

<span data-ttu-id="2998e-164">Para autorizar os aplicativos de comércio eletrônico a acessarem sua assinatura do Azure, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="2998e-164">To authorize e-Commerce applications to access your Azure subscription, follow these steps.</span></span>

1. <span data-ttu-id="2998e-165">Monte uma URL no seguinte formato:</span><span class="sxs-lookup"><span data-stu-id="2998e-165">Assemble a URL in the following format:</span></span>

    `https://login.windows.net/{AAD_TENANT_ID}/oauth2/authorize?client_id=fbcbf727-cd18-4422-a723-f8274075331a&response_type=code&redirect_uri=https://sb.manage.commerce.dynamics.com/_commerce/Consent&response_mode=query&prompt=admin_consent&state=12345`

1. <span data-ttu-id="2998e-166">Copie e cole a URL no seu navegador ou editor de texto e substitua **\{AAD\_TENANT\_ID\}** por sua ID de locatário do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="2998e-166">Copy and paste the URL into your browser or text editor, and replace **\{AAD\_TENANT\_ID\}** with your Azure AD tenant ID.</span></span> <span data-ttu-id="2998e-167">Em seguida, abra a URL.</span><span class="sxs-lookup"><span data-stu-id="2998e-167">Then open the URL.</span></span>
1. <span data-ttu-id="2998e-168">Na caixa de diálogo de logon do Azure AD, faça logon e confirme se você deseja conceder acesso ao **Dynamics 365 Commerce (Versão prévia)** à sua assinatura.</span><span class="sxs-lookup"><span data-stu-id="2998e-168">In the Azure AD sign-in dialog box, sign in, and confirm that you want to grant **Dynamics 365 Commerce (Preview)** access to your subscription.</span></span> <span data-ttu-id="2998e-169">Você será redirecionado a uma página que indica se a operação foi bem-sucedida.</span><span class="sxs-lookup"><span data-stu-id="2998e-169">You're redirected to a page that indicates whether the operation was successful.</span></span>

### <a name="confirm-that-preview-features-are-available-and-turned-on-in-lcs"></a><span data-ttu-id="2998e-170">Confirme se os recursos de visualização estão disponíveis e habilitados no LCS</span><span class="sxs-lookup"><span data-stu-id="2998e-170">Confirm that preview features are available and turned on in LCS</span></span>

<span data-ttu-id="2998e-171">Para confirmar se os recursos de visualização estão disponíveis e habilitados no LCS, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="2998e-171">To confirm that preview features are available and turned on in LCS, follow these steps.</span></span>

1. <span data-ttu-id="2998e-172">Entre no [portal do LCS](https://lcs.dynamics.com) usando a mesma conta da LCS que você usou para solicitar acesso à visualização.</span><span class="sxs-lookup"><span data-stu-id="2998e-172">Sign in to the [LCS portal](https://lcs.dynamics.com) by using the same LCS account that you used to request access to the preview.</span></span>
1. <span data-ttu-id="2998e-173">Na página inicial do LCS, role para a direita e selecione o bloco **Gerenciamento de recursos de visualização**.</span><span class="sxs-lookup"><span data-stu-id="2998e-173">On the LCS home page, scroll all the way to the right, and select the **Preview feature management** tile.</span></span>

    ![Bloco de gerenciamento de visualização](./media/preview1.png)

1. <span data-ttu-id="2998e-175">Role para baixo até **Recursos de visualização privada** e confirme se os seguintes recursos estão disponíveis e ativados:</span><span class="sxs-lookup"><span data-stu-id="2998e-175">Scroll down to **Private preview features**, and confirm that the following features are available and turned on:</span></span>

    - <span data-ttu-id="2998e-176">Avaliação de Comércio eletrônico</span><span class="sxs-lookup"><span data-stu-id="2998e-176">e-Commerce Evaluation</span></span>
    - <span data-ttu-id="2998e-177">Ambientes do Programa de Visualização do Comércio</span><span class="sxs-lookup"><span data-stu-id="2998e-177">Commerce Preview Program Environments</span></span>

    ![Recursos de visualização privada](./media/preview2.png)

1. <span data-ttu-id="2998e-179">Se esses recursos não aparecerem na lista, contate a Microsoft e forneça seu endereço de email de trabalho, sua conta LCS e os detalhes do locatário.</span><span class="sxs-lookup"><span data-stu-id="2998e-179">If those features don't appear in the list, contact Microsoft, and provide your work email address, LCS account, and tenant details.</span></span> <span data-ttu-id="2998e-180">Para obter informações de contato, consulte a seção [Suporte ao ambiente de visualização do Commerce](#commerce-preview-environment-support).</span><span class="sxs-lookup"><span data-stu-id="2998e-180">For contact information, see the [Commerce preview environment support](#commerce-preview-environment-support) section.</span></span>

### <a name="create-a-new-project"></a><span data-ttu-id="2998e-181">Criar um novo projeto</span><span class="sxs-lookup"><span data-stu-id="2998e-181">Create a new project</span></span>

<span data-ttu-id="2998e-182">Para criar um novo projeto no LCS, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="2998e-182">To create a new project in LCS, follow these steps.</span></span>

1. <span data-ttu-id="2998e-183">Na home page do LCS, selecione o sinal de mais (**+**) para criar um projeto.</span><span class="sxs-lookup"><span data-stu-id="2998e-183">On the LCS home page, select the plus sign (**+**) to create a project.</span></span>
1. <span data-ttu-id="2998e-184">No painel à direita, siga uma destas etapas:</span><span class="sxs-lookup"><span data-stu-id="2998e-184">In the right pane, follow one of these steps:</span></span>

    - <span data-ttu-id="2998e-185">Se você for um parceiro, selecione **Migrar, criar soluções e conhecer**.</span><span class="sxs-lookup"><span data-stu-id="2998e-185">If you're a partner, select **Migrate, create solutions, and learn**.</span></span>
    - <span data-ttu-id="2998e-186">Se for um cliente, selecione **Pré-vendas de clientes potenciais**.</span><span class="sxs-lookup"><span data-stu-id="2998e-186">If you're a customer, select **Prospective presales**.</span></span>

1. <span data-ttu-id="2998e-187">Inserir um nome, descrição e setor.</span><span class="sxs-lookup"><span data-stu-id="2998e-187">Enter a name, description, and industry.</span></span>
1. <span data-ttu-id="2998e-188">No campo **Nome do produto**, selecione **Dynamics 365 Retail**.</span><span class="sxs-lookup"><span data-stu-id="2998e-188">In the **Product name** field, select **Dynamics 365 Retail**.</span></span>
1. <span data-ttu-id="2998e-189">No campo **Versão do produto**, selecione **Dynamics 365 Retail**.</span><span class="sxs-lookup"><span data-stu-id="2998e-189">In the **Product version** field, select **Dynamics 365 Retail**.</span></span>
1. <span data-ttu-id="2998e-190">No campo **Metodologia**, selecione **Metodologia de implementação do Dynamics Retail**.</span><span class="sxs-lookup"><span data-stu-id="2998e-190">In the **Methodology** field, select **Dynamics Retail implementation methodology**.</span></span>
1. <span data-ttu-id="2998e-191">Opcional: você pode importar funções e usuários de um projeto existente.</span><span class="sxs-lookup"><span data-stu-id="2998e-191">Optional: You can import roles and users from an existing project.</span></span>
1. <span data-ttu-id="2998e-192">Selecione **Criar**.</span><span class="sxs-lookup"><span data-stu-id="2998e-192">Select **Create**.</span></span> <span data-ttu-id="2998e-193">A exibição do projeto é exibida.</span><span class="sxs-lookup"><span data-stu-id="2998e-193">The project view appears.</span></span>

### <a name="add-the-azure-connector"></a><span data-ttu-id="2998e-194">Adicione o Conector do Azure</span><span class="sxs-lookup"><span data-stu-id="2998e-194">Add the Azure Connector</span></span>

<span data-ttu-id="2998e-195">Para adicionar o Conector do Azure ao seu projeto LCS, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="2998e-195">To add the Azure Connector to your LCS project, follow these steps.</span></span>

1. <span data-ttu-id="2998e-196">Siga uma destas etapas:</span><span class="sxs-lookup"><span data-stu-id="2998e-196">Follow one of these steps:</span></span>

    - <span data-ttu-id="2998e-197">Se você for um parceiro, selecione o bloco **Configurações do projeto** na extrema direita.</span><span class="sxs-lookup"><span data-stu-id="2998e-197">If you're a partner, select the **Project settings** tile on the far right.</span></span>
    - <span data-ttu-id="2998e-198">Se for um cliente, selecione **Configurações do projeto** no menu superior.</span><span class="sxs-lookup"><span data-stu-id="2998e-198">If you're a customer, select **Project settings** on the top menu.</span></span>

1. <span data-ttu-id="2998e-199">Selecione **Conectores do Azure**.</span><span class="sxs-lookup"><span data-stu-id="2998e-199">Select **Azure connectors**.</span></span>
1. <span data-ttu-id="2998e-200">Selecione **Adicionar** para adicionar o Conector do Azure.</span><span class="sxs-lookup"><span data-stu-id="2998e-200">Select **Add** to add the Azure Connector.</span></span>
1. <span data-ttu-id="2998e-201">Insira um nome.</span><span class="sxs-lookup"><span data-stu-id="2998e-201">Enter a name.</span></span>
1. <span data-ttu-id="2998e-202">Digite sua ID da Assinatura do Azure.</span><span class="sxs-lookup"><span data-stu-id="2998e-202">Enter your Azure subscription ID.</span></span>
1. <span data-ttu-id="2998e-203">Ativa a opção **Configurar para usar o gerente de recursos do Azure (ARM)**.</span><span class="sxs-lookup"><span data-stu-id="2998e-203">Turn on the **Configure to use Azure Resource Manager (ARM)** option.</span></span>
1. <span data-ttu-id="2998e-204">Verifique se o valor **Domínio (ou ID) de Locatário do AAD de assinatura do Azure** está correto.</span><span class="sxs-lookup"><span data-stu-id="2998e-204">Verify that the **Azure subscription AAD Tenant Domain (or ID)** value is correct.</span></span> <span data-ttu-id="2998e-205">Consulte seu administrador de assinatura do Azure, se necessário.</span><span class="sxs-lookup"><span data-stu-id="2998e-205">Consult your Azure subscription admin as required.</span></span>
1. <span data-ttu-id="2998e-206">Selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="2998e-206">Select **Next**.</span></span>
1. <span data-ttu-id="2998e-207">Siga as instruções na página para conceder aos aplicativos necessários o acesso à sua assinatura.</span><span class="sxs-lookup"><span data-stu-id="2998e-207">Follow the instructions on the page to grant the required applications access to your subscription.</span></span> <span data-ttu-id="2998e-208">Consulte seu administrador de assinatura do Azure, se necessário.</span><span class="sxs-lookup"><span data-stu-id="2998e-208">Consult your Azure subscription admin as required.</span></span>

    1. <span data-ttu-id="2998e-209">Entre no [portal do Azure](https://portal.azure.com/).</span><span class="sxs-lookup"><span data-stu-id="2998e-209">Sign in to the [Azure portal](https://portal.azure.com/).</span></span>
    1. <span data-ttu-id="2998e-210">Verifique se o diretório correto está selecionado e, no menu à esquerda, selecione **Assinaturas**.</span><span class="sxs-lookup"><span data-stu-id="2998e-210">Make sure that the correct directory is selected, and then, on the menu on the left, select **Subscriptions**.</span></span>
    1. <span data-ttu-id="2998e-211">Localize a assinatura correta da lista e selecione-a.</span><span class="sxs-lookup"><span data-stu-id="2998e-211">Find the correct subscription in the list, and select it.</span></span> <span data-ttu-id="2998e-212">Use a funcionalidade de pesquisa, conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="2998e-212">Use the search functionality as required.</span></span>
    1. <span data-ttu-id="2998e-213">No menu, selecione **Controle de acesso (IAM)**.</span><span class="sxs-lookup"><span data-stu-id="2998e-213">On the menu, select **Access control (IAM)**.</span></span>
    1. <span data-ttu-id="2998e-214">À direita, em **Adicionar uma atribuição da função**, selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="2998e-214">On the right, under **Add a role assignment**, select **Add**.</span></span> <span data-ttu-id="2998e-215">O painel **Adicionar atribuição da função** é aberto.</span><span class="sxs-lookup"><span data-stu-id="2998e-215">The **Add role assignment** pane appears.</span></span>
    1. <span data-ttu-id="2998e-216">No campo **Função**, selecione **Colaborador**.</span><span class="sxs-lookup"><span data-stu-id="2998e-216">In the **Role** field, select **Contributor**.</span></span>
    1. <span data-ttu-id="2998e-217">No campo **Atribuir acesso a**, mantenha o valor padrão, **usuário, grupo ou entidade de serviço do Azure AD**.</span><span class="sxs-lookup"><span data-stu-id="2998e-217">In the **Assign access to** field, leave the default value, **Azure AD user, group, or service principal**.</span></span>
    1. <span data-ttu-id="2998e-218">Em **Selecionar**, insira **b96b7e94-b82e-4e71-99a0-cf7fb188acea**.</span><span class="sxs-lookup"><span data-stu-id="2998e-218">Under **Select**, enter **b96b7e94-b82e-4e71-99a0-cf7fb188acea**.</span></span>
    1. <span data-ttu-id="2998e-219">Selecione **Serviços de Implantação do Dynamics \[ativado por wsfed\]** na lista.</span><span class="sxs-lookup"><span data-stu-id="2998e-219">Select **Dynamics Deployment Services \[wsfed-enabled\]** in the list.</span></span>
    1. <span data-ttu-id="2998e-220">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="2998e-220">Select **Save**.</span></span>

1. <span data-ttu-id="2998e-221">Selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="2998e-221">Select **Next**.</span></span>
1. <span data-ttu-id="2998e-222">Siga as instruções na página para conceder aos aplicativos necessários o acesso à sua assinatura.</span><span class="sxs-lookup"><span data-stu-id="2998e-222">Follow the instructions on the page to grant the required applications access to your subscription.</span></span> <span data-ttu-id="2998e-223">Consulte seu administrador de assinatura do Azure, se necessário.</span><span class="sxs-lookup"><span data-stu-id="2998e-223">Consult your Azure subscription admin as required.</span></span>
1. <span data-ttu-id="2998e-224">Selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="2998e-224">Select **Next**.</span></span>
1. <span data-ttu-id="2998e-225">No campo **região do Azure**, selecione **Leste dos EUA**, **Leste dos EUA 2**, **Oeste dos EUA** ou **Oeste dos EUA 2**.</span><span class="sxs-lookup"><span data-stu-id="2998e-225">In the **Azure region** field, select **East US**, **East US 2**, **West US**, or **West US 2**.</span></span>
1. <span data-ttu-id="2998e-226">Selecione **Conectar**.</span><span class="sxs-lookup"><span data-stu-id="2998e-226">Select **Connect**.</span></span> <span data-ttu-id="2998e-227">Seu Conector do Azure deverá aparecer na lista.</span><span class="sxs-lookup"><span data-stu-id="2998e-227">Your Azure Connector should appear in the list.</span></span>

### <a name="import-the-commerce-preview-demo-base-extension"></a><span data-ttu-id="2998e-228">Importar a Extensão da Demonstração da Versão Prévia do Commerce</span><span class="sxs-lookup"><span data-stu-id="2998e-228">Import the Commerce Preview Demo Base Extension</span></span>

<span data-ttu-id="2998e-229">Para importar a extensão da demonstração da versão prévia do Commerce para seu projeto, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="2998e-229">To import the Commerce Preview Demo Base Extension into your project, follow these steps.</span></span>

1. <span data-ttu-id="2998e-230">Abra a home page do seu projeto selecionando o nome do projeto na parte superior.</span><span class="sxs-lookup"><span data-stu-id="2998e-230">Open the home page for your project by selecting the project name at the top.</span></span>
1. <span data-ttu-id="2998e-231">Siga uma destas etapas:</span><span class="sxs-lookup"><span data-stu-id="2998e-231">Follow one of these steps:</span></span>

    - <span data-ttu-id="2998e-232">Se você for um parceiro, selecione o bloco **Biblioteca de ativos** na extrema direita.</span><span class="sxs-lookup"><span data-stu-id="2998e-232">If you're a partner, select the **Asset library** tile on the far right.</span></span>
    - <span data-ttu-id="2998e-233">Se for um cliente, selecione **Biblioteca de ativos** no menu superior.</span><span class="sxs-lookup"><span data-stu-id="2998e-233">If you're a customer, select **Asset library** on the top menu.</span></span>

1. <span data-ttu-id="2998e-234">Na lista à esquerda, selecione **Pacote de software implantável**.</span><span class="sxs-lookup"><span data-stu-id="2998e-234">In the list on the left, select **Software deployable package**.</span></span>
1. <span data-ttu-id="2998e-235">Selecione **Importar**.</span><span class="sxs-lookup"><span data-stu-id="2998e-235">Select **Import**.</span></span>
1. <span data-ttu-id="2998e-236">Em **Biblioteca de ativos compartilhados**, selecione **Extensão da Demonstração da Versão Prévia do Commerce** na lista de ativos.</span><span class="sxs-lookup"><span data-stu-id="2998e-236">Under **Shared asset library**, select **Commerce Preview Demo Base Extension** in the list of assets.</span></span>
1. <span data-ttu-id="2998e-237">Escolha **Separar**.</span><span class="sxs-lookup"><span data-stu-id="2998e-237">Select **Pick**.</span></span> <span data-ttu-id="2998e-238">Você retornará à biblioteca de Ativos e deverá ver a extensão na lista.</span><span class="sxs-lookup"><span data-stu-id="2998e-238">You're returned to the Asset library, and you should see the extension in the list.</span></span>

<span data-ttu-id="2998e-239">A ilustração a seguir mostra as ações que devem ser executadas na página **Biblioteca de ativos** do LCS.</span><span class="sxs-lookup"><span data-stu-id="2998e-239">The following illustration shows the actions that must be taken on the LCS **Asset library** page.</span></span>

![Importando a Extensão Base da Demonstração da Versão Prévia do Commerce](./media/import.png)

### <a name="deploy-the-environment"></a><span data-ttu-id="2998e-241">Implantar o ambiente</span><span class="sxs-lookup"><span data-stu-id="2998e-241">Deploy the environment</span></span>

<span data-ttu-id="2998e-242">Para implantar o ambiente, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="2998e-242">To deploy the environment, follow these steps.</span></span>

> [!NOTE]
> <span data-ttu-id="2998e-243">Talvez não seja necessário concluir as etapas 6, 7 e/ou 8, porque as páginas que têm uma única opção são ignoradas.</span><span class="sxs-lookup"><span data-stu-id="2998e-243">You might not have to complete steps 6, 7, and/or 8, because pages that have a single option are skipped.</span></span> <span data-ttu-id="2998e-244">Quando estiver na exibição de **Parâmetros do ambiente**, confirme se o texto **Dynamics 365 Commerce (Versão prévia) Demonstração (10.0.6 com atualização de plataforma 30**) aparece diretamente acima do campo **Nome do ambiente**.</span><span class="sxs-lookup"><span data-stu-id="2998e-244">When you're in the **Environment parameters** view, confirm that the text **Dynamics 365 Commerce (Preview) - Demo (10.0.6 with Platform update 30)** appears directly above the **Environment name** field.</span></span> <span data-ttu-id="2998e-245">Consulte a ilustração que aparece após a etapa 8.</span><span class="sxs-lookup"><span data-stu-id="2998e-245">See the illustration that appears after step 8.</span></span>

1. <span data-ttu-id="2998e-246">No menu superior, selecione **Ambientes hospedados na nuvem**.</span><span class="sxs-lookup"><span data-stu-id="2998e-246">On the top menu, select **Cloud-hosted environments**.</span></span>
1. <span data-ttu-id="2998e-247">Selecione **Adicionar** para adicionar um ambiente.</span><span class="sxs-lookup"><span data-stu-id="2998e-247">Select **Add** to add an environment.</span></span>
1. <span data-ttu-id="2998e-248">No campo **Versão do aplicativo**, selecione **10.0.6**.</span><span class="sxs-lookup"><span data-stu-id="2998e-248">In the **Application version** field, select **10.0.6**.</span></span>
1. <span data-ttu-id="2998e-249">No campo **Versão da plataforma**, selecione **Atualização da Plataforma 30**.</span><span class="sxs-lookup"><span data-stu-id="2998e-249">In the **Platform version** field, select **Platform Update 30**.</span></span>

    ![Selecionando as versões do aplicativo e da plataforma](./media/project1.png)

1. <span data-ttu-id="2998e-251">Selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="2998e-251">Select **Next**.</span></span>
1. <span data-ttu-id="2998e-252">Selecione **Demonstração** como a topologia do ambiente.</span><span class="sxs-lookup"><span data-stu-id="2998e-252">Select **Demo** as the environment topology.</span></span>

    ![Selecionar a topologia de ambiente 1](./media/project2.png)

1. <span data-ttu-id="2998e-254">Selecione **Dynamics 365 Commerce (Versão prévia) - Demonstrativo** como a topologia do ambiente.</span><span class="sxs-lookup"><span data-stu-id="2998e-254">Select **Dynamics 365 Commerce (Preview) - Demo** as the environment topology.</span></span> <span data-ttu-id="2998e-255">Se você configurou um único Conector do Azure anteriormente, isso será usado para este ambiente.</span><span class="sxs-lookup"><span data-stu-id="2998e-255">If you configured a single Azure Connector earlier, it will be used for this environment.</span></span> <span data-ttu-id="2998e-256">Se você configurou vários Conectores do Azure, é possível selecionar qual conector usar: **Leste dos EUA**, **Leste dos EUA 2,** **Oeste dos EUA**, ou **Oeste dos EUA 2**.</span><span class="sxs-lookup"><span data-stu-id="2998e-256">If you configured multiple Azure Connectors, you can select which connector to use: **East US**, **East US 2**, **West US**, or **West US 2**.</span></span> <span data-ttu-id="2998e-257">(Para obter o melhor desempenho de ponta a ponta, recomendamos que você selecione **Oeste dos EUA 2**.)</span><span class="sxs-lookup"><span data-stu-id="2998e-257">(For the best end-to-end performance, we recommend that you select **West US 2**.)</span></span>

    ![Selecionando a topologia de ambiente 2](./media/project3.png)

1. <span data-ttu-id="2998e-259">Na página **Implantar ambiente**, insira um nome de ambiente.</span><span class="sxs-lookup"><span data-stu-id="2998e-259">On the **Deploy environment** page, enter an environment name.</span></span> <span data-ttu-id="2998e-260">Deixe as configurações avançadas como estão.</span><span class="sxs-lookup"><span data-stu-id="2998e-260">Leave the advanced settings as they are.</span></span>

    ![Implantar página do ambiente](./media/project4.png)

1. <span data-ttu-id="2998e-262">Ajuste o tamanho da VM, conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="2998e-262">Adjust the VM size as required.</span></span> <span data-ttu-id="2998e-263">(Recomendamos a unidade de manutenção de estoque da VM\[SKU\] **D13 v2**.)</span><span class="sxs-lookup"><span data-stu-id="2998e-263">(We recommend VM stock keeping unit \[SKU\] **D13 v2**.)</span></span>
1. <span data-ttu-id="2998e-264">Revise os termos de definição de preços e licenciamento e marque a caixa de seleção para indicar que você concorda com eles.</span><span class="sxs-lookup"><span data-stu-id="2998e-264">Review the pricing and licensing terms, and then select the check box to indicate that you agree to them.</span></span>
1. <span data-ttu-id="2998e-265">Selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="2998e-265">Select **Next**.</span></span>
1. <span data-ttu-id="2998e-266">Na página de confirmação da implantação, verifique se os detalhes estão corretos e selecione **Implantar**.</span><span class="sxs-lookup"><span data-stu-id="2998e-266">On the deployment confirmation page, verify that the details are correct, and then select **Deploy**.</span></span> <span data-ttu-id="2998e-267">Você voltará à visualização **Ambientes hospedados na nuvem** e seu ambiente deverá aparecer na lista.</span><span class="sxs-lookup"><span data-stu-id="2998e-267">You're returned to the **Cloud-hosted environments** view, and your environment should appear in the list.</span></span>

    <span data-ttu-id="2998e-268">Seu ambiente solicitado aparecerá na fila e, em seguida, será implantado.</span><span class="sxs-lookup"><span data-stu-id="2998e-268">Your requested environment will appear as queued and then deploying.</span></span> <span data-ttu-id="2998e-269">Os fluxos de trabalho de ambiente levarão algum tempo para serem concluídos.</span><span class="sxs-lookup"><span data-stu-id="2998e-269">The environment workflows will take some time to be completed.</span></span> <span data-ttu-id="2998e-270">Portanto, verifique novamente depois de aproximadamente seis a nove horas.</span><span class="sxs-lookup"><span data-stu-id="2998e-270">Therefore, check back after approximately six to nine hours.</span></span>

1. <span data-ttu-id="2998e-271">Antes de continuar, verifique se o status de ambiente está **Implantado**.</span><span class="sxs-lookup"><span data-stu-id="2998e-271">Before you continue, make sure that the status of your environment is **Deployed**.</span></span>

### <a name="initialize-rcsu"></a><span data-ttu-id="2998e-272">Inicialize o RCSU</span><span class="sxs-lookup"><span data-stu-id="2998e-272">Initialize RCSU</span></span>

<span data-ttu-id="2998e-273">Para inicializar sua RCSU, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="2998e-273">To initialize RCSU, follow these steps.</span></span>

1. <span data-ttu-id="2998e-274">Na visualização **Ambientes hospedados na nuvem** selecione seu ambiente da lista.</span><span class="sxs-lookup"><span data-stu-id="2998e-274">In the **Cloud-hosted environments** view, select your environment in the list.</span></span>
1. <span data-ttu-id="2998e-275">Nas visualização do ambiente à direita, selecione **Detalhes completos**.</span><span class="sxs-lookup"><span data-stu-id="2998e-275">In the environment view on the right, select **Full details**.</span></span> <span data-ttu-id="2998e-276">A visualização de detalhes do ambiente é exibida.</span><span class="sxs-lookup"><span data-stu-id="2998e-276">The environment details view appears.</span></span>
1. <span data-ttu-id="2998e-277">Em **Recursos do ambiente**, selecione **Gerenciar**.</span><span class="sxs-lookup"><span data-stu-id="2998e-277">Under **Environment features**, select **Manage**.</span></span>
1. <span data-ttu-id="2998e-278">Na guia **Varejo**, selecione **Inicializar**.</span><span class="sxs-lookup"><span data-stu-id="2998e-278">On the **Retail** tab, select **Initialize**.</span></span> <span data-ttu-id="2998e-279">A visualização dos parâmetros de inicialização do RCSU será exibida.</span><span class="sxs-lookup"><span data-stu-id="2998e-279">The RCSU initialization parameters view appears.</span></span>
1. <span data-ttu-id="2998e-280">No campo **Região**, selecione **Leste dos EUA**, **Leste dos EUA 2**, **Oeste dos EUA** ou **Oeste dos EUA 2**.</span><span class="sxs-lookup"><span data-stu-id="2998e-280">In the **Region** field, select **East US**, **East US 2**, **West US**, or **West US 2**.</span></span>
1. <span data-ttu-id="2998e-281">No campo **Versão**, selecione **Especificar uma versão** na lista e, em seguida, especifique **9.16.19262.5** no campo que é exibido.</span><span class="sxs-lookup"><span data-stu-id="2998e-281">In the **Version** field, select **Specify a version** in the list, and then specify **9.16.19262.5** in the field that appears.</span></span> <span data-ttu-id="2998e-282">Certifique-se de especificar a versão exata indicada aqui.</span><span class="sxs-lookup"><span data-stu-id="2998e-282">Be sure to specify the exact version that is indicated here.</span></span> <span data-ttu-id="2998e-283">Caso contrário, será necessário atualizar a RCSU para a versão correta posteriormente.</span><span class="sxs-lookup"><span data-stu-id="2998e-283">Otherwise, you will have to update RCSU to the correct version later.</span></span>
1. <span data-ttu-id="2998e-284">Ative a opção **Aplicar extensão**.</span><span class="sxs-lookup"><span data-stu-id="2998e-284">Turn on the **Apply extension** option.</span></span>
1. <span data-ttu-id="2998e-285">Na lista de extensões, selecione **Extensão da Demonstração da Versão Prévia do Commerce**.</span><span class="sxs-lookup"><span data-stu-id="2998e-285">In the list of extensions, select **Commerce Preview Demo Base Extension**.</span></span>
1. <span data-ttu-id="2998e-286">Selecione **Inicializar**.</span><span class="sxs-lookup"><span data-stu-id="2998e-286">Select **Initialize**.</span></span>
1. <span data-ttu-id="2998e-287">Na página de confirmação da implantação, verifique se os detalhes estão corretos e selecione **Sim**.</span><span class="sxs-lookup"><span data-stu-id="2998e-287">On the deployment confirmation page, verify that the details are correct, and then select **Yes**.</span></span> <span data-ttu-id="2998e-288">Você retornará à visualização **Gerenciamento de varejo** com a guia **Varejo** selecionada.</span><span class="sxs-lookup"><span data-stu-id="2998e-288">You're returned to the **Retail management** view, where the **Retail** tab is selected.</span></span> <span data-ttu-id="2998e-289">Sua RCSU foi enfileirada para provisionamento.</span><span class="sxs-lookup"><span data-stu-id="2998e-289">Your RCSU has been queued for provisioning.</span></span>
1. <span data-ttu-id="2998e-290">Antes de continuar, verifique se o status de RCSU é **Êxito**.</span><span class="sxs-lookup"><span data-stu-id="2998e-290">Before you continue, make sure that the status of your RCSU is **Success**.</span></span> <span data-ttu-id="2998e-291">A inicialização leva cerca de duas a cinco horas.</span><span class="sxs-lookup"><span data-stu-id="2998e-291">Initialization takes approximately two to five hours.</span></span>

### <a name="initialize-e-commerce"></a><span data-ttu-id="2998e-292">Inicializar comércio eletrônico</span><span class="sxs-lookup"><span data-stu-id="2998e-292">Initialize e-Commerce</span></span>

<span data-ttu-id="2998e-293">Para inicializar o comércio eletrônico, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="2998e-293">To initialize e-Commerce, follow these steps.</span></span>

1. <span data-ttu-id="2998e-294">Na guia **Comércio eletrônico (Versão prévia)**, revise o consentimento da visualização e, em seguida, selecione **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="2998e-294">On the **e-Commerce (Preview)** tab, review the preview consent, and then select **Setup**.</span></span>
1. <span data-ttu-id="2998e-295">No campo **Nome do locatário de comércio eletrônico**, informe um nome.</span><span class="sxs-lookup"><span data-stu-id="2998e-295">In the **e-Commerce tenant name** field, enter a name.</span></span> <span data-ttu-id="2998e-296">No entanto, observe que este nome estará visível em algumas das URLs que apontam para sua instância de comércio eletrônico.</span><span class="sxs-lookup"><span data-stu-id="2998e-296">However, be aware that this name will appear in some of the URLs that point to your e-Commerce instance.</span></span>
1. <span data-ttu-id="2998e-297">No campo **Nome da Retail cloud scale unit**, selecione o RCSU na lista.</span><span class="sxs-lookup"><span data-stu-id="2998e-297">In the **Retail cloud scale unit name** field, select your RCSU in the list.</span></span> <span data-ttu-id="2998e-298">(A lista deve ter apenas uma opção).</span><span class="sxs-lookup"><span data-stu-id="2998e-298">(The list should have only one option.)</span></span>

    <span data-ttu-id="2998e-299">O **Geografia de comércio eletrônico** é definido automaticamente, e o valor não pode ser alterado.</span><span class="sxs-lookup"><span data-stu-id="2998e-299">The **e-Commerce geography** field is set automatically, and the value can't be changed.</span></span>

1. <span data-ttu-id="2998e-300">Selecione **Avançar** para continuar.</span><span class="sxs-lookup"><span data-stu-id="2998e-300">Select **Next** to continue.</span></span>
1. <span data-ttu-id="2998e-301">No campo **Nomes de host suportados**, insira qualquer domínio válido, como `www.fabrikam.com`.</span><span class="sxs-lookup"><span data-stu-id="2998e-301">In the **Supported host names** field, enter any valid domain, such as `www.fabrikam.com`.</span></span>
1.  <span data-ttu-id="2998e-302">No campo **Grupo de segurança do AAD para o administrador do sistema**, insira as primeiras letras do nome do grupo de segurança que você deseja usar.</span><span class="sxs-lookup"><span data-stu-id="2998e-302">In the **AAD security group for system admin** field, enter the first few letters of the name of the security group that you want to use.</span></span> <span data-ttu-id="2998e-303">Selecione o ícone de lupa para exibir os resultados da pesquisa.</span><span class="sxs-lookup"><span data-stu-id="2998e-303">Select the magnifying class icon to display the search results.</span></span> <span data-ttu-id="2998e-304">Selecione um grupo de segurança na lista.</span><span class="sxs-lookup"><span data-stu-id="2998e-304">Select a security group from the list.</span></span>
2.  <span data-ttu-id="2998e-305">No campo **Grupo de segurança do AAD para o moderador de revisão e de avaliações**, insira as primeiras letras do nome do grupo de segurança que você deseja usar.</span><span class="sxs-lookup"><span data-stu-id="2998e-305">In the **AAD security group for ratings and review moderator** field, enter the first few letters of the name of the security group that you want to use.</span></span> <span data-ttu-id="2998e-306">Selecione o ícone de lupa para exibir os resultados da pesquisa.</span><span class="sxs-lookup"><span data-stu-id="2998e-306">Select the magnifying class icon to display the search results.</span></span> <span data-ttu-id="2998e-307">Selecione um grupo de segurança na lista.</span><span class="sxs-lookup"><span data-stu-id="2998e-307">Select a security group from the list.</span></span>
1. <span data-ttu-id="2998e-308">Deixe a opção **Habilitar classificações e examinar o serviço** ativada.</span><span class="sxs-lookup"><span data-stu-id="2998e-308">Leave the **Enable ratings and review service** option turned on.</span></span>
1. <span data-ttu-id="2998e-309">Se você já tiver concluído a etapa de consentimento do Microsoft Azure Active Directory (Azure AD), conforme descrito na seção "Conceder acesso a aplicativos de comércio eletrônico", marque a caixa de seleção para confirmar seu consentimento.</span><span class="sxs-lookup"><span data-stu-id="2998e-309">If you have already completed the Microsoft Azure Active Directory (Azure AD) consent step as described in the "Grant access to e-Commerce applications" section, select the check box to confirm your consent.</span></span> <span data-ttu-id="2998e-310">Se ainda não tiver concluído essa etapa, você precisará fazer isso antes de continuar com a inicialização.</span><span class="sxs-lookup"><span data-stu-id="2998e-310">If you have not yet completed this step, you need to do that before proceeding with the initialization.</span></span> <span data-ttu-id="2998e-311">Selecione o link no texto ao lado da caixa de seleção para abrir a caixa de diálogo de consentimento e concluir a etapa.</span><span class="sxs-lookup"><span data-stu-id="2998e-311">Select the link within the text next to the check box to open the consent dialog box and complete the step.</span></span>
1. <span data-ttu-id="2998e-312">Selecione **Inicializar**.</span><span class="sxs-lookup"><span data-stu-id="2998e-312">Select **Initialize**.</span></span> <span data-ttu-id="2998e-313">Você retornará à visualização **Gerenciamento de varejo** na qual a guia **Comércio eletrônico (Versão prévia)** está ativada.</span><span class="sxs-lookup"><span data-stu-id="2998e-313">You're returned to the **Retail management** view, where the **e-Commerce (Preview)** tab is selected.</span></span> <span data-ttu-id="2998e-314">A inicialização de Comércio eletrônico começou.</span><span class="sxs-lookup"><span data-stu-id="2998e-314">E-Commerce initialization has started.</span></span>
1. <span data-ttu-id="2998e-315">Antes de continuar, aguarde até que o status de inicialização do seu comércio eletrônico seja **Inicialização com êxito**.</span><span class="sxs-lookup"><span data-stu-id="2998e-315">Before you continue, wait until the status of e-Commerce initialization is **Initialization successful**.</span></span>
1. <span data-ttu-id="2998e-316">Em **Links** no canto inferior direito, anote as URLs dos seguintes links:</span><span class="sxs-lookup"><span data-stu-id="2998e-316">Under **Links** in the lower right, make a note of the URLs for the following links:</span></span>

    * <span data-ttu-id="2998e-317">**Site de comércio eletrônico** – o link para a raiz do seu site de comércio eletrônico.</span><span class="sxs-lookup"><span data-stu-id="2998e-317">**e-Commerce site** – The link to the root of your e-Commerce site.</span></span>
    * <span data-ttu-id="2998e-318">**Ferramenta de gerenciamento de site de comércio eletrônico** – o link para a ferramenta de gerenciamento de site.</span><span class="sxs-lookup"><span data-stu-id="2998e-318">**e-Commerce site management tool** – The link to the site management tool.</span></span>

## <a name="commerce-preview-environment-support"></a><span data-ttu-id="2998e-319">Suporte ao ambiente de visualização do Commerce</span><span class="sxs-lookup"><span data-stu-id="2998e-319">Commerce preview environment support</span></span>

<span data-ttu-id="2998e-320">Se você tiver problemas ao concluir as etapas de provisionamento, visite [Visualização do Microsoft Dynamics 365 Commerce - grupo Yammer](https://aka.ms/Dynamics365CommercePreviewYammer) para obter ajuda.</span><span class="sxs-lookup"><span data-stu-id="2998e-320">If you experience issues while you're completing the provisioning steps, visit the [Microsoft Dynamics 365 Commerce Preview Yammer group](https://aka.ms/Dynamics365CommercePreviewYammer) for help.</span></span>

<span data-ttu-id="2998e-321">Se tiver problemas ao tentar acessar o grupo Yammer, poderá contatar a Microsoft por email em <Dynamics365Commerce@microsoft.com>.</span><span class="sxs-lookup"><span data-stu-id="2998e-321">If you experience issues when you try to access the Yammer group, you can contact Microsoft by email at <Dynamics365Commerce@microsoft.com>.</span></span> <span data-ttu-id="2998e-322">Esse endereço de email não está ativamente monitorado.</span><span class="sxs-lookup"><span data-stu-id="2998e-322">This email address isn't actively monitored.</span></span> <span data-ttu-id="2998e-323">Portanto, espere um atraso na resposta.</span><span class="sxs-lookup"><span data-stu-id="2998e-323">Therefore, expect a delay in the response.</span></span>

## <a name="next-steps"></a><span data-ttu-id="2998e-324">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="2998e-324">Next steps</span></span>

<span data-ttu-id="2998e-325">Para continuar o processo de provisionamento e configuração de seu ambiente de visualização do Commerce, consulte [Configurar um ambiente de visualização do Commerce](cpe-post-provisioning.md).</span><span class="sxs-lookup"><span data-stu-id="2998e-325">To continue the process of provisioning and configuring your Commerce preview environment, see [Configure a Commerce preview environment](cpe-post-provisioning.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="2998e-326">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="2998e-326">Additional resources</span></span>

[<span data-ttu-id="2998e-327">Visão geral do ambiente de visualização do Commerce</span><span class="sxs-lookup"><span data-stu-id="2998e-327">Commerce preview environment overview</span></span>](cpe-overview.md)

[<span data-ttu-id="2998e-328">Configurar um ambiente de visualização do Commerce</span><span class="sxs-lookup"><span data-stu-id="2998e-328">Configure a Commerce preview environment</span></span>](cpe-post-provisioning.md)

[<span data-ttu-id="2998e-329">Configurar recursos opcionais para um ambiente de visualização do Commerce</span><span class="sxs-lookup"><span data-stu-id="2998e-329">Configure optional features for a Commerce preview environment</span></span>](cpe-optional-features.md)

[<span data-ttu-id="2998e-330">Perguntas frequentes do ambiente de visualização do Commerce</span><span class="sxs-lookup"><span data-stu-id="2998e-330">Commerce preview environment FAQ</span></span>](cpe-faq.md)

[<span data-ttu-id="2998e-331">Microsoft Lifecycle Services (LCS)</span><span class="sxs-lookup"><span data-stu-id="2998e-331">Microsoft Lifecycle Services (LCS)</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/lifecycle-services/lcs-user-guide)

[<span data-ttu-id="2998e-332">Retail Cloud Scale Unit (RCSU)</span><span class="sxs-lookup"><span data-stu-id="2998e-332">Retail Cloud Scale Unit (RCSU)</span></span>](https://docs.microsoft.com/business-applications-release-notes/october18/dynamics365-retail/retail-cloud-scale-unit)

[<span data-ttu-id="2998e-333">Portal do Microsoft Azure</span><span class="sxs-lookup"><span data-stu-id="2998e-333">Microsoft Azure portal</span></span>](https://azure.microsoft.com/features/azure-portal)

[<span data-ttu-id="2998e-334">Site do Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="2998e-334">Dynamics 365 Commerce website</span></span>](https://aka.ms/Dynamics365CommerceWebsite)

[<span data-ttu-id="2998e-335">Recursos de ajuda do Dynamics 365 Retail</span><span class="sxs-lookup"><span data-stu-id="2998e-335">Help resources for Dynamics 365 Retail</span></span>](../retail/index.md)
