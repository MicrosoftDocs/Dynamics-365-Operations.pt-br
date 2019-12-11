---
title: Configurar páginas personalizadas para entradas dos usuários
description: Este tópico descreve como criar páginas personalizadas no Microsoft Dynamics 365 Commerce que manipula inscrições personalizadas para usuários nos locatários de business-to-consumer (B2C) do Azure Active Directory (Azure AD).
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
ms.openlocfilehash: 644d937ddd3c219ae869f22d977d2846dffc20e1
ms.sourcegitcommit: 295d940a345879b3dfc5991e387b91c7257019ea
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/01/2019
ms.locfileid: "2697534"
---
# <a name="set-up-custom-pages-for-user-logins"></a><span data-ttu-id="c88dc-103">Configurar páginas personalizadas para logons dos usuários</span><span class="sxs-lookup"><span data-stu-id="c88dc-103">Set up custom pages for user logins</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="c88dc-104">Este tópico descreve como criar páginas personalizadas no Microsoft Dynamics 365 Commerce que manipula inscrições personalizadas para usuários nos locatários de business-to-consumer (B2C) do Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="c88dc-104">This topic describes how to build custom pages in Microsoft Dynamics 365 Commerce that handle customized sign-ins for users of Azure Active Directory (Azure AD) business-to-consumer (B2C) tenants.</span></span>

## <a name="overview"></a><span data-ttu-id="c88dc-105">Visão geral</span><span class="sxs-lookup"><span data-stu-id="c88dc-105">Overview</span></span>

<span data-ttu-id="c88dc-106">Para usar as páginas personalizadas criadas no Dynamics 365 Commerce para manipular fluxos de inscrições de usuário, você deve configurar as políticas do Azure AD que serão referenciadas no ambiente de comércio.</span><span class="sxs-lookup"><span data-stu-id="c88dc-106">To use custom pages that are authored in Dynamics 365 Commerce to handle user sign-in flows, you must set up the Azure AD policies that will be referenced in the Commerce environment.</span></span> <span data-ttu-id="c88dc-107">Você pode configurar as políticas B2C "Se inscrever e entrar," "Edição de perfil," e "Redefinição de senha" Azure AD usando o aplicativo B2C do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="c88dc-107">You can configure the "Sign up and sign in," "Profile editing," and "Password reset" Azure AD B2C policies by using the Azure AD B2C application.</span></span> <span data-ttu-id="c88dc-108">O locatário B2C do Azure AD e nomes de política podem ser referenciados durante o processo de provisionamento feito para o ambiente de comércio usando Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="c88dc-108">The Azure AD B2C tenant and policy names can then be referenced during the provisioning process that is done for the Commerce environment by using Microsoft Dynamics Lifecycle Services (LCS).</span></span>

<span data-ttu-id="c88dc-109">As páginas personalizadas Comércio podem ser criadas usando se inscrever, entrar, edição de perfil da conta ou módulo para redefinição de senha.</span><span class="sxs-lookup"><span data-stu-id="c88dc-109">The custom Commerce pages can be built by using the sign in, sign up, account profile edit, or password reset module.</span></span> <span data-ttu-id="c88dc-110">As URLs da página publicadas para essas páginas personalizadas devem ser referenciadas nas configurações de política do Azure AD B2C no portal do Azure.</span><span class="sxs-lookup"><span data-stu-id="c88dc-110">The page URLs that are published for these custom pages should then be referenced in Azure AD B2C policy configurations in the Azure portal.</span></span>

## <a name="set-up-b2c-policies"></a><span data-ttu-id="c88dc-111">Configurar políticas B2C</span><span class="sxs-lookup"><span data-stu-id="c88dc-111">Set up B2C policies</span></span>

<span data-ttu-id="c88dc-112">Depois de ter configurado seu locatário B2C Azure AD e associá-lo com seu ambiente de comércio, vá para a página **Azure AD B2C** no portal do Azure e depois, no menu, em **Políticas**, selecione **Fluxos de usuário (políticas)**.</span><span class="sxs-lookup"><span data-stu-id="c88dc-112">After you set up your Azure AD B2C tenant and associate it with your Commerce environment, go to the **Azure AD B2C** page in the Azure portal, and then, on the menu, under **Policies**, select **User flows (policies)**.</span></span>

![Comando fluxos de usuário (políticas) no menu](./media/B2C_CustomPage_PoliciesMenu.png)

<span data-ttu-id="c88dc-114">Agora você pode configurar fluxos de entrada de usuário de "Se inscrever e entrar," "Edição de perfil," e "Redefinição de senha".</span><span class="sxs-lookup"><span data-stu-id="c88dc-114">You can now configure the "Sign up and sign in," "Profile editing," and "Password reset" user sign-in flows.</span></span>

### <a name="configure-the-sign-up-and-sign-in-policy"></a><span data-ttu-id="c88dc-115">Configurar a política "Se inscrever e entrar"</span><span class="sxs-lookup"><span data-stu-id="c88dc-115">Configure the "Sign up and sign in" policy</span></span>

<span data-ttu-id="c88dc-116">Para configurar a política ""Se inscrever e entrar", siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="c88dc-116">To configure the "Sign up and sign in" policy, follow these steps.</span></span>

1. <span data-ttu-id="c88dc-117">Selecione **Novo fluxo de usuário**, e depois na guia **Recomendado**, selecione a política **"Se inscrever e entrar**.</span><span class="sxs-lookup"><span data-stu-id="c88dc-117">Select **New user flow**, and then, on the **Recommended** tab, select the **Sign up and sign in** policy.</span></span>
1. <span data-ttu-id="c88dc-118">Insira um nome para a política (por exemplo, **B2C\_1\_SignInSignUp**).</span><span class="sxs-lookup"><span data-stu-id="c88dc-118">Enter a name for the policy (for example, **B2C\_1\_SignInSignUp**).</span></span>
1. <span data-ttu-id="c88dc-119">Na seção **Provedores de Identidade**, selecione os provedores de identidade para usar a política.</span><span class="sxs-lookup"><span data-stu-id="c88dc-119">In the **Identity Providers** section, select the identity providers to use for the policy.</span></span> <span data-ttu-id="c88dc-120">Ao mínimo, **Inscrição por e-mail** deve estar selecionado.</span><span class="sxs-lookup"><span data-stu-id="c88dc-120">At a minimum, **Email signup** must be selected.</span></span>
1. <span data-ttu-id="c88dc-121">Na coluna **Coletar atributo**, marque as caixas de seleção **Endereço de e-mail**, **Nome fornecido** e **Sobrenome**.</span><span class="sxs-lookup"><span data-stu-id="c88dc-121">In the **Collect attribute** column, select the check boxes for **Email Address**, **Given Name**, and **Surname**.</span></span>
1. <span data-ttu-id="c88dc-122">Na coluna **Retornar reivindicação**, marque as caixas de seleção **Endereços de e-mail**, **Nome fornecido**, **Provedor de identidade**, **Sobrenome** e **ID do objeto de usuário**.</span><span class="sxs-lookup"><span data-stu-id="c88dc-122">In the **Return claim** column, select the check boxes for **Email Addresses**, **Given Name**, **Identity Provider**, **Surname**, and **User's Object ID**.</span></span>

    ![Atributos e reivindicações selecionados](./media/B2C_SignInSignUp_Attributes.png)

1. <span data-ttu-id="c88dc-124">Selecione **OK** para criar a política.</span><span class="sxs-lookup"><span data-stu-id="c88dc-124">Select **OK** to create the policy.</span></span>
1. <span data-ttu-id="c88dc-125">Clique duas vezes no nome da política, e depois no painel de navegação, selecione **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="c88dc-125">Double-click the new policy name, and then, in the navigation pane, select **Properties**.</span></span>
1. <span data-ttu-id="c88dc-126">Defina a opção **Habilitar layout de página garantindo JavaScript (visualização)** como **Ligado**.</span><span class="sxs-lookup"><span data-stu-id="c88dc-126">Set the **Enable JavaScript enforcing page layout (preview)** option to **On**.</span></span>

    ![As páginas de propriedade da nova política](./media/B2C_SignInSignUp_EnableJavascript.png)

> [!NOTE]
> <span data-ttu-id="c88dc-128">O nome da política será referenciado por completo no ambiente de comércio.</span><span class="sxs-lookup"><span data-stu-id="c88dc-128">The policy name will be fully referenced in the Commerce environment.</span></span> <span data-ttu-id="c88dc-129">(O prefixo **B2C\_1\_** será incluído na referência.) Políticas não podem ser renomeadas após serem criadas.</span><span class="sxs-lookup"><span data-stu-id="c88dc-129">(The **B2C\_1\_** prefix will be included in the reference.) Policies can't be renamed after they are created.</span></span> <span data-ttu-id="c88dc-130">Se você está substituindo uma política existente para seu ambiente de comércio, você pode excluir a política original e criar uma nova política que tem o mesmo nome.</span><span class="sxs-lookup"><span data-stu-id="c88dc-130">If you're replacing an existing policy for your Commerce environment, you can delete the original policy and build a new policy that has the same name.</span></span> <span data-ttu-id="c88dc-131">Alternativamente, se o ambiente já foi provisionado, você pode enviar o novo nome de política por meio de solicitação de serviço.</span><span class="sxs-lookup"><span data-stu-id="c88dc-131">Alternatively, if the environment has already been provisioned, you can submit the new policy name through a service request.</span></span>

<span data-ttu-id="c88dc-132">Você retornará a esta política para concluir a configuração depois de criar páginas personalizadas.</span><span class="sxs-lookup"><span data-stu-id="c88dc-132">You will return to this policy to finish the setup after you've built the custom pages.</span></span> <span data-ttu-id="c88dc-133">Por hora, feche a política para retornar à página **Fluxos de usuário (políticas)** no portal do Azure.</span><span class="sxs-lookup"><span data-stu-id="c88dc-133">For now, close the policy to return to the **User flows (policies)** page in the Azure portal.</span></span>

### <a name="configure-the-profile-editing-policy"></a><span data-ttu-id="c88dc-134">Configurar a política "Edição de perfil"</span><span class="sxs-lookup"><span data-stu-id="c88dc-134">Configure the "Profile editing" policy</span></span>

<span data-ttu-id="c88dc-135">Para configurar a política "Edição de perfil", siga as etapas a seguir.</span><span class="sxs-lookup"><span data-stu-id="c88dc-135">To configure the "Profile editing" policy, follow these steps.</span></span>

1. <span data-ttu-id="c88dc-136">Selecione **Novo fluxo de usuário**, e depois na guia **Recomendado**, selecione a política **Edição de perfil**.</span><span class="sxs-lookup"><span data-stu-id="c88dc-136">Select **New user flow**, and then, on the **Recommended** tab, select the **Profile editing** policy.</span></span>
1. <span data-ttu-id="c88dc-137">Insira um nome para a política (por exemplo, **B2C\_1\_EditProfile**).</span><span class="sxs-lookup"><span data-stu-id="c88dc-137">Enter a name for the policy (for example, **B2C\_1\_EditProfile**).</span></span>
1. <span data-ttu-id="c88dc-138">Na seção **Provedores de Identidade**, selecione os provedores de identidade para usar a política.</span><span class="sxs-lookup"><span data-stu-id="c88dc-138">In the **Identity Providers** section, select the identity providers to use for the policy.</span></span> <span data-ttu-id="c88dc-139">Ao mínimo, **Inscrição de conta local** deve estar selecionado.</span><span class="sxs-lookup"><span data-stu-id="c88dc-139">At a minimum, **Local Account SignIn** must be selected.</span></span>
1. <span data-ttu-id="c88dc-140">Na coluna **Coletar atributo**, marque as caixas de seleção **Endereços de e-mail** e **Sobrenome**.</span><span class="sxs-lookup"><span data-stu-id="c88dc-140">In the **Collect attribute** column, select the check boxes for **Email Addresses** and **Surname**.</span></span>
1. <span data-ttu-id="c88dc-141">Na coluna **Retornar reivindicação**, marque as caixas de seleção **Endereços de e-mail**, **Nome fornecido**, **Provedor de identidade**, **Sobrenome** e **ID do objeto de usuário**.</span><span class="sxs-lookup"><span data-stu-id="c88dc-141">In the **Return claim** column, select the check boxes for **Email Addresses**, **Given Name**, **Identity Provider**, **Surname**, and **User's Object ID**.</span></span>
1. <span data-ttu-id="c88dc-142">Selecione **OK** para criar a política.</span><span class="sxs-lookup"><span data-stu-id="c88dc-142">Select **OK** to create the policy.</span></span>
1. <span data-ttu-id="c88dc-143">Clique duas vezes no nome da política, e depois no painel de navegação, selecione **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="c88dc-143">Double-click the new policy name, and then, in the navigation pane, select **Properties**.</span></span>
1. <span data-ttu-id="c88dc-144">Defina a opção **Habilitar layout de página garantindo JavaScript (visualização)** como **Ligado**.</span><span class="sxs-lookup"><span data-stu-id="c88dc-144">Set the **Enable JavaScript enforcing page layout (preview)** option to **On**.</span></span>

<span data-ttu-id="c88dc-145">Você retornará a esta política para concluir a configuração depois de criar páginas personalizadas.</span><span class="sxs-lookup"><span data-stu-id="c88dc-145">You will return to this policy to finish the setup after you've built the custom pages.</span></span> <span data-ttu-id="c88dc-146">Por hora, feche a política para retornar à página **Fluxos de usuário (políticas)** no portal do Azure.</span><span class="sxs-lookup"><span data-stu-id="c88dc-146">For now, close the policy to return to the **User flows (policies)** page in the Azure portal.</span></span>

### <a name="configure-the-password-reset-policy"></a><span data-ttu-id="c88dc-147">Configurar a política "Redefinir senha"</span><span class="sxs-lookup"><span data-stu-id="c88dc-147">Configure the "Password reset" policy</span></span>

<span data-ttu-id="c88dc-148">Para configurar a política "Redefinir senha", siga as etapas a seguir.</span><span class="sxs-lookup"><span data-stu-id="c88dc-148">To configure the "Password reset" policy, follow these steps.</span></span>

1. <span data-ttu-id="c88dc-149">Selecione **Novo fluxo de usuário**, e depois na guia **Visualização**, selecione a política **Redefinir senha v1.1**.</span><span class="sxs-lookup"><span data-stu-id="c88dc-149">Select **New user flow**, and then, on the **Preview** tab, select the **Password reset v1.1** policy.</span></span>

    ![Política Redefinir senha v1.1 selecionada na guia Visualização](./media/B2C_ForgetPassword_Menu.png)

1. <span data-ttu-id="c88dc-151">Insira um nome para a política (por exemplo, **B2C\_1\_ForgetPassword**).</span><span class="sxs-lookup"><span data-stu-id="c88dc-151">Enter a name for the policy (for example, **B2C\_1\_ForgetPassword**).</span></span>
1. <span data-ttu-id="c88dc-152">Na seção **Provedores de Identidade**, selecione **Redefinir senha usando endereço de e-mail**.</span><span class="sxs-lookup"><span data-stu-id="c88dc-152">In the **Identity Providers** section, select **Reset password using email address**.</span></span>
1. <span data-ttu-id="c88dc-153">Na coluna **Retornar reivindicação**, marque as caixas de seleção **Endereços de e-mail**, **Nome fornecido**, **Sobrenome** e **ID do objeto de usuário**.</span><span class="sxs-lookup"><span data-stu-id="c88dc-153">In the **Return claim** column, select the check boxes for **Email Addresses**, **Given Name**, **Surname**, and **User's Object ID**.</span></span>

    ![Reclamações selecionadas](./media/B2C_ForgetPassword_Attributes.png)

1. <span data-ttu-id="c88dc-155">Selecione **OK** para criar a política.</span><span class="sxs-lookup"><span data-stu-id="c88dc-155">Select **OK** to create the policy.</span></span>
1. <span data-ttu-id="c88dc-156">Clique duas vezes no nome da política, e depois no painel de navegação, selecione **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="c88dc-156">Double-click the new policy name, and then, in the navigation pane, select **Properties**.</span></span>
1. <span data-ttu-id="c88dc-157">Defina a opção **Habilitar layout de página garantindo JavaScript (visualização)** como **Ligado**.</span><span class="sxs-lookup"><span data-stu-id="c88dc-157">Set the **Enable JavaScript enforcing page layout (preview)** option to **On**.</span></span>

<span data-ttu-id="c88dc-158">Você retornará a esta política para concluir a configuração depois de criar páginas personalizadas.</span><span class="sxs-lookup"><span data-stu-id="c88dc-158">You will return to this policy to finish the setup after you've built the custom pages.</span></span> <span data-ttu-id="c88dc-159">Por hora, feche a política para retornar à página **Fluxos de usuário (políticas)** no portal do Azure.</span><span class="sxs-lookup"><span data-stu-id="c88dc-159">For now, close the policy to return to the **User flows (policies)** page in the Azure portal.</span></span>

## <a name="build-the-custom-pages"></a><span data-ttu-id="c88dc-160">Criar as páginas personalizadas</span><span class="sxs-lookup"><span data-stu-id="c88dc-160">Build the custom pages</span></span>

<span data-ttu-id="c88dc-161">Para criar as páginas personalizadas para lidar com inscrições de usuários, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="c88dc-161">To build the custom pages to handle user sign-ins, follow these steps.</span></span>

1. <span data-ttu-id="c88dc-162">Nas ferramentas de comércio, vá para nosso site.</span><span class="sxs-lookup"><span data-stu-id="c88dc-162">In the Commerce authoring tools, go to your site.</span></span>
1. <span data-ttu-id="c88dc-163">Criar os seguintes cinco modelos e cinco páginas:</span><span class="sxs-lookup"><span data-stu-id="c88dc-163">Build the following five templates and five pages:</span></span>

    - <span data-ttu-id="c88dc-164">Um modelo de **Entrada** e página que usa o módulo de entrada.</span><span class="sxs-lookup"><span data-stu-id="c88dc-164">A **Sign In** template and page that use the sign in module.</span></span>
    - <span data-ttu-id="c88dc-165">Um modelo de **Se inscrever** e página que usa o módulo de inscrição.</span><span class="sxs-lookup"><span data-stu-id="c88dc-165">A **Sign Up** template and page that use the sign up module.</span></span>
    - <span data-ttu-id="c88dc-166">Um modelo e a página para **Redefinir senha** que usa o módulo para redefinir senha.</span><span class="sxs-lookup"><span data-stu-id="c88dc-166">A **Password Reset** template and page that use the password reset module.</span></span>
    - <span data-ttu-id="c88dc-167">Um modelo e a página para **Verificação para redefinir senha** que usa o módulo de verificação para redefinir senha.</span><span class="sxs-lookup"><span data-stu-id="c88dc-167">A **Password Reset verification** template and page that use the password reset verification module.</span></span>
    - <span data-ttu-id="c88dc-168">Um modelo e página **Edição de perfil** que usa o módulo de edição do perfil da conta</span><span class="sxs-lookup"><span data-stu-id="c88dc-168">A **Profile Edit** template and page that use the account profile edit module</span></span>

<span data-ttu-id="c88dc-169">Quando você cria páginas, siga estas diretrizes:</span><span class="sxs-lookup"><span data-stu-id="c88dc-169">When you build the pages, follow these guidelines:</span></span>

- <span data-ttu-id="c88dc-170">Para cada página ou módulo, use o layout e estilo que melhor atende aos seus requisitos de empresa.</span><span class="sxs-lookup"><span data-stu-id="c88dc-170">For each page or module, use the layout and style that best suit your business requirements.</span></span>
- <span data-ttu-id="c88dc-171">Publicar todas as páginas e URLs que devem ser usadas na configuração do Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="c88dc-171">Publish all pages and URLs that must be used in the Azure AD B2C setup.</span></span>
- <span data-ttu-id="c88dc-172">Após as páginas e URLs serem publicados, colete os URLs que devem ser usados para configurações da política Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="c88dc-172">After the pages and URLs are published, collect the URLs that must be used for the Azure AD B2C policy configurations.</span></span> <span data-ttu-id="c88dc-173">Um sufixo **?preloadscripts=true** será adicionado a cada URL quando é usado.</span><span class="sxs-lookup"><span data-stu-id="c88dc-173">A **?preloadscripts=true** suffix will be added to every URL when it's used.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c88dc-174">Não reutilize cabeçalhos e rodapés universais com links relacionados.</span><span class="sxs-lookup"><span data-stu-id="c88dc-174">Don't reuse universal headers and footers that have relative links.</span></span> <span data-ttu-id="c88dc-175">Como essas páginas estão hospedadas no domínio Azure AD B2C quando são usadas, apenas URLs absolutas devem ser usadas para todos os links.</span><span class="sxs-lookup"><span data-stu-id="c88dc-175">Because these pages will be hosted in the Azure AD B2C domain when they are used, only absolute URLs should be used for all links.</span></span>

## <a name="configure-azure-ad-b2c-policies-with-custom-page-information"></a><span data-ttu-id="c88dc-176">Configurar políticas Azure AD B2C com informações de página personalizadas</span><span class="sxs-lookup"><span data-stu-id="c88dc-176">Configure Azure AD B2C policies with custom page information</span></span> 

<span data-ttu-id="c88dc-177">No portal do Azure, volte à página do **Azure AD B2C** e depois no menu, em **Políticas**, selecione **Fluxos de usuário (políticas)**.</span><span class="sxs-lookup"><span data-stu-id="c88dc-177">In the Azure portal, return to the **Azure AD B2C** page, and then, on the menu, under **Policies**, select **User flows (policies)**.</span></span>

### <a name="update-the-sign-up-and-sign-in-policy-with-custom-page-information"></a><span data-ttu-id="c88dc-178">Atualizar a política "Se inscrever e entrar" com informações de página personalizadas</span><span class="sxs-lookup"><span data-stu-id="c88dc-178">Update the "Sign up and sign in" policy with custom page information</span></span>

<span data-ttu-id="c88dc-179">Para atualizar a política "Se inscrever e entrar" com informações de página personalizadas, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="c88dc-179">To update the "Sign up and sign in" policy with custom page information, follow these steps.</span></span>

1. <span data-ttu-id="c88dc-180">Na política **Se inscrever e entrar** que você configurou anteriormente, no painel de navegação, selecione **Layouts de página**.</span><span class="sxs-lookup"><span data-stu-id="c88dc-180">In the **Sign in and sign up** policy that you configured earlier, in the navigation pane, select **Page layouts**.</span></span>
1. <span data-ttu-id="c88dc-181">Selecione o layout **Unificar entrada ou inscrição na página**.</span><span class="sxs-lookup"><span data-stu-id="c88dc-181">Select the **Unified sign up or sign in page** layout.</span></span>
1. <span data-ttu-id="c88dc-182">Defina a opção **Usar conteúdo de página personalizado** como **Sim**.</span><span class="sxs-lookup"><span data-stu-id="c88dc-182">Set the **Use custom page content** option to **Yes**.</span></span>
1. <span data-ttu-id="c88dc-183">No campo **URL de página personalizada**, insira a URL de entrada completa.</span><span class="sxs-lookup"><span data-stu-id="c88dc-183">In the **Custom page URI** field, enter the full sign-in URL.</span></span> <span data-ttu-id="c88dc-184">Inclua o sufixo **?preloadscripts=true**.</span><span class="sxs-lookup"><span data-stu-id="c88dc-184">Include the **?preloadscripts=true** suffix.</span></span> <span data-ttu-id="c88dc-185">Por exemplo, insira **www.\<my domain\>.com/sign-in?preloadscripts=true**.</span><span class="sxs-lookup"><span data-stu-id="c88dc-185">For example, enter **www.\<my domain\>.com/sign-in?preloadscripts=true**.</span></span>
1. <span data-ttu-id="c88dc-186">No campo **Versão de layout de página (visualização)**, selecione **1.2.0**.</span><span class="sxs-lookup"><span data-stu-id="c88dc-186">In the **Page Layout Version (Preview)** field, select **1.2.0**.</span></span>
1. <span data-ttu-id="c88dc-187">Selecione o layout **Página de inscrição de conta local**.</span><span class="sxs-lookup"><span data-stu-id="c88dc-187">Select the **Local account sign up page** layout.</span></span>
1. <span data-ttu-id="c88dc-188">Defina a opção **Usar conteúdo de página personalizado** como **Sim**.</span><span class="sxs-lookup"><span data-stu-id="c88dc-188">Set the **Use custom page content** option to **Yes**.</span></span>
1. <span data-ttu-id="c88dc-189">No campo **URL de página personalizada**, insira a URL de entrada completa.</span><span class="sxs-lookup"><span data-stu-id="c88dc-189">In the **Custom page URI** field, enter the full sign-in URL.</span></span> <span data-ttu-id="c88dc-190">Inclua o sufixo **?preloadscripts=true**.</span><span class="sxs-lookup"><span data-stu-id="c88dc-190">Include the **?preloadscripts=true** suffix.</span></span> <span data-ttu-id="c88dc-191">Por exemplo, insira **www.\<my domain\>.com/sign-in?preloadscripts=true**.</span><span class="sxs-lookup"><span data-stu-id="c88dc-191">For example, enter **www.\<my domain\>.com/sign-in?preloadscripts=true**.</span></span>
1. <span data-ttu-id="c88dc-192">No campo **Versão de layout de página (visualização)**, selecione **1.2.0**.</span><span class="sxs-lookup"><span data-stu-id="c88dc-192">In the **Page Layout Version (Preview)** field, select **1.2.0**.</span></span>
1. <span data-ttu-id="c88dc-193">Na seção **Atributos de usuário**, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="c88dc-193">In the **User attributes** section, follow these steps:</span></span>

    1. <span data-ttu-id="c88dc-194">Para os atributos **Endereço de e-mail**, **Nome** e **Sobrenome**, selecione **Não** no campo **Requer verificação**.</span><span class="sxs-lookup"><span data-stu-id="c88dc-194">For the **Email Address**, **Given Name**, and **Surname** attributes, select **No** in the **Requires Verification** field.</span></span>
    1. <span data-ttu-id="c88dc-195">Para os atributos **Nome** e **Sobrenome**, selecione **Não** no campo **Opcional**.</span><span class="sxs-lookup"><span data-stu-id="c88dc-195">For the **Given Name** and **Surname** attributes, select **No** in the **Optional** field.</span></span>

    ![Configuração da política de página de inscrição de conta local](./media/B2C_SignUp_PageURLConfig.png)

### <a name="update-the-profile-editing-policy-with-custom-page-information"></a><span data-ttu-id="c88dc-197">Atualizar a política "Edição de perfil" com informações de página personalizadas</span><span class="sxs-lookup"><span data-stu-id="c88dc-197">Update the "Profile editing" policy with custom page information</span></span>

<span data-ttu-id="c88dc-198">Para atualizar a política "Edição de perfil" com informações de página personalizadas, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="c88dc-198">To update the "Profile editing" policy with custom page information, follow these steps.</span></span>

1. <span data-ttu-id="c88dc-199">Na política **Edição de perfil** que você configurou anteriormente, no painel de navegação, selecione **Layouts de página**.</span><span class="sxs-lookup"><span data-stu-id="c88dc-199">In the **Profile Editing** policy that you configured earlier, in the navigation pane, select **Page layouts**.</span></span>
1. <span data-ttu-id="c88dc-200">Selecione o layout **Página de edição de perfil**.</span><span class="sxs-lookup"><span data-stu-id="c88dc-200">Select the **Profile edit page** layout.</span></span>
1. <span data-ttu-id="c88dc-201">Defina a opção **Usar conteúdo de página personalizado** como **Sim**.</span><span class="sxs-lookup"><span data-stu-id="c88dc-201">Set the **Use custom page content** option to **Yes**.</span></span>
1. <span data-ttu-id="c88dc-202">No campo **URL de página personalizada**, insira a URL de entrada completa.</span><span class="sxs-lookup"><span data-stu-id="c88dc-202">In the **Custom page URI** field, enter the full sign-in URL.</span></span> <span data-ttu-id="c88dc-203">Inclua o sufixo **?preloadscripts=true**.</span><span class="sxs-lookup"><span data-stu-id="c88dc-203">Include the **?preloadscripts=true** suffix.</span></span> <span data-ttu-id="c88dc-204">Por exemplo, insira **www.\<my domain\>.com/sign-in?preloadscripts=true**.</span><span class="sxs-lookup"><span data-stu-id="c88dc-204">For example, enter **www.\<my domain\>.com/sign-in?preloadscripts=true**.</span></span>
1. <span data-ttu-id="c88dc-205">No campo **Versão de layout de página (visualização)**, selecione **1.2.0**.</span><span class="sxs-lookup"><span data-stu-id="c88dc-205">In the **Page Layout Version (Preview)** field, select **1.2.0**.</span></span>
1. <span data-ttu-id="c88dc-206">Na seção **Atributos de usuário**, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="c88dc-206">In the **User attributes** section, follow these steps:</span></span>

    1. <span data-ttu-id="c88dc-207">Para os atributos **Endereço de e-mail**, **Nome**, selecione **Não** no campo **Requer verificação**.</span><span class="sxs-lookup"><span data-stu-id="c88dc-207">For the **Email Address**, **Given Name** attributes, select **No** in the **Requires Verification** field.</span></span>
    1. <span data-ttu-id="c88dc-208">Para os atributos **Nome** e **Sobrenome**, selecione **Não** no campo **Opcional**.</span><span class="sxs-lookup"><span data-stu-id="c88dc-208">For the **Given Name** and **Surname** attributes, select **No** in the **Optional** field.</span></span>

### <a name="update-the-password-reset-policy-with-custom-page-information"></a><span data-ttu-id="c88dc-209">Atualizar a política "Redefinir senha" com informações de página personalizadas</span><span class="sxs-lookup"><span data-stu-id="c88dc-209">Update the "Password reset" policy with custom page information</span></span>

<span data-ttu-id="c88dc-210">Para atualizar a política "Redefinir senha" com informações de página personalizadas, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="c88dc-210">To update the "Password reset" policy with custom page information, follow these steps.</span></span>

1. <span data-ttu-id="c88dc-211">Na política **Redefinir senha** que você configurou anteriormente, no painel de navegação, selecione **Layouts de página**.</span><span class="sxs-lookup"><span data-stu-id="c88dc-211">In the **Password Reset** policy that you configured earlier, in the navigation pane, select **Page layouts**.</span></span>
1. <span data-ttu-id="c88dc-212">Selecione o layout **Nova página de senha**.</span><span class="sxs-lookup"><span data-stu-id="c88dc-212">Select the **New password page** layout.</span></span>
1. <span data-ttu-id="c88dc-213">Defina a opção **Usar conteúdo de página personalizado** como **Sim**.</span><span class="sxs-lookup"><span data-stu-id="c88dc-213">Set the **Use custom page content** option to **Yes**.</span></span>
1. <span data-ttu-id="c88dc-214">No campo **URL de página personalizada**, insira a URL de entrada completa.</span><span class="sxs-lookup"><span data-stu-id="c88dc-214">In the **Custom page URI** field, enter the full sign-in URL.</span></span> <span data-ttu-id="c88dc-215">Inclua o sufixo **?preloadscripts=true**.</span><span class="sxs-lookup"><span data-stu-id="c88dc-215">Include the **?preloadscripts=true** suffix.</span></span> <span data-ttu-id="c88dc-216">Por exemplo, insira **www.\<my domain\>.com/sign-in?preloadscripts=true**.</span><span class="sxs-lookup"><span data-stu-id="c88dc-216">For example, enter **www.\<my domain\>.com/sign-in?preloadscripts=true**.</span></span>
1. <span data-ttu-id="c88dc-217">No campo **Versão de layout de página (visualização)**, selecione **1.2.0**.</span><span class="sxs-lookup"><span data-stu-id="c88dc-217">In the **Page Layout Version (Preview)** field, select **1.2.0**.</span></span>
1. <span data-ttu-id="c88dc-218">Selecione o layout **Página de verificação de conta**.</span><span class="sxs-lookup"><span data-stu-id="c88dc-218">Select the **Account verification page** layout.</span></span>
1. <span data-ttu-id="c88dc-219">Defina a opção **Usar conteúdo de página personalizado** como **Sim**.</span><span class="sxs-lookup"><span data-stu-id="c88dc-219">Set the **Use custom page content** option to **Yes**.</span></span>
1. <span data-ttu-id="c88dc-220">No campo **URL de página personalizada**, insira a URL de entrada completa.</span><span class="sxs-lookup"><span data-stu-id="c88dc-220">In the **Custom page URI** field, enter the full sign-in URL.</span></span> <span data-ttu-id="c88dc-221">Inclua o sufixo **?preloadscripts=true**.</span><span class="sxs-lookup"><span data-stu-id="c88dc-221">Include the **?preloadscripts=true** suffix.</span></span> <span data-ttu-id="c88dc-222">Por exemplo, insira **www.\<my domain\>.com/sign-in?preloadscripts=true**.</span><span class="sxs-lookup"><span data-stu-id="c88dc-222">For example, enter **www.\<my domain\>.com/sign-in?preloadscripts=true**.</span></span>
1. <span data-ttu-id="c88dc-223">No campo **Versão de layout de página (visualização)**, selecione **1.2.0**.</span><span class="sxs-lookup"><span data-stu-id="c88dc-223">In the **Page Layout Version (Preview)** field, select **1.2.0**.</span></span>

## <a name="customize-default-text-strings-for-labels-and-descriptions"></a><span data-ttu-id="c88dc-224">Personalizar caracteres de texto padrão e rótulos para descrições</span><span class="sxs-lookup"><span data-stu-id="c88dc-224">Customize default text strings for labels and descriptions</span></span>

<span data-ttu-id="c88dc-225">No pacote inicial, módulos de inscrição são preenchidos com caracteres de texto padrão para rótulos e descrições.</span><span class="sxs-lookup"><span data-stu-id="c88dc-225">In the starter kit, sign in modules are prefilled with default text strings for the labels and descriptions.</span></span> <span data-ttu-id="c88dc-226">Você pode personalizar esses caracteres no kit de desenvolvimento de software (SDK) atualizando os valores no arquivo global.json para entrar no módulo.</span><span class="sxs-lookup"><span data-stu-id="c88dc-226">You can customize these strings in the software development kit (SDK) by updating the values in the global.json file for the sign in module.</span></span>

<span data-ttu-id="c88dc-227">Por exemplo, o texto padrão para o link de senha esquecida é **Esqueceu a senha?**.</span><span class="sxs-lookup"><span data-stu-id="c88dc-227">For example, the default text for the forgotten password link is **Forgotten password?**.</span></span> <span data-ttu-id="c88dc-228">A seguir veja um texto padrão na página de entrada.</span><span class="sxs-lookup"><span data-stu-id="c88dc-228">The following shows this default text on the sign-in page.</span></span>

![Texto padrão para o link de senha esquecida na página de entrada](./media/B2C_SignUp_ModuleFace.png)

<span data-ttu-id="c88dc-230">No entanto, no arquivo global.json para o módulo de entrada de kit inicial, você pode editar o texto para **Esqueceu a senha?**, como visto na ilustração a seguir.</span><span class="sxs-lookup"><span data-stu-id="c88dc-230">However, in the global.json file for the starter kit sign in module, you can edit the text to **Forgot Password?**, as shown in the following illustration.</span></span>

![Texto de link atualizado no arquivo global.json do módulo de entrada](./media/B2C_CustomizingStringsForModule.png)

<span data-ttu-id="c88dc-232">Depois de atualizar o arquivo global.json e publicar suas alterações, o novo texto de link aparece no módulo de entrada em Comércio e na página de entrada ao vivo.</span><span class="sxs-lookup"><span data-stu-id="c88dc-232">After you update the global.json file and publish your changes, the new link text appears in the sign in module in both Commerce and on the live sign-in page.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="c88dc-233">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="c88dc-233">Additional resources</span></span>

[<span data-ttu-id="c88dc-234">Visão geral de loja online</span><span class="sxs-lookup"><span data-stu-id="c88dc-234">Online store overview</span></span>](online-store-overview.md)

[<span data-ttu-id="c88dc-235">Criar um site de comércio eletrônico</span><span class="sxs-lookup"><span data-stu-id="c88dc-235">Create an e-Commerce site</span></span>](create-ecommerce-site.md)

[<span data-ttu-id="c88dc-236">Implantar um novo site de comércio eletrônico</span><span class="sxs-lookup"><span data-stu-id="c88dc-236">Deploy a new e-Commerce site</span></span>](deploy-ecommerce-site.md)

[<span data-ttu-id="c88dc-237">Associar um site online a um canal</span><span class="sxs-lookup"><span data-stu-id="c88dc-237">Associate an online site with a channel</span></span>](associate-site-online-store.md)

[<span data-ttu-id="c88dc-238">Configure seu nome de domínio</span><span class="sxs-lookup"><span data-stu-id="c88dc-238">Configure your domain name</span></span>](configure-your-domain-name.md)

[<span data-ttu-id="c88dc-239">Adicionar suporte para uma rede de entrega de conteúdo (CDN)</span><span class="sxs-lookup"><span data-stu-id="c88dc-239">Add support for a content delivery network (CDN)</span></span>](add-cdn-support.md)

[<span data-ttu-id="c88dc-240">Habilitar detecção de lojas com base na localização</span><span class="sxs-lookup"><span data-stu-id="c88dc-240">Enable location-based store detection</span></span>](enable-store-detection.md)
