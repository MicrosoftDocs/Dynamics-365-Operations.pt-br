---
title: Configurar um locatário B2C do Commerce
description: Este tópico descreve como configurar os locatários business-to-consumer (B2C) do Azure Active Directory (Azure AD) para a autenticação do site de usuário no Dynamics 365 Commerce.
author: BrianShook
manager: annbe
ms.date: 03/02/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: ''
ms.search.region: Global
ms.search.industry: retail
ms.author: BriShoo
ms.search.validFrom: 2020-02-13
ms.dyn365.ops.version: ''
ms.openlocfilehash: a5fca37fb89c723273ef753b102092e2cfb26563
ms.sourcegitcommit: 236672932ffd0a758012ebb7b2df9bc51249c126
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/03/2020
ms.locfileid: "3096489"
---
# <a name="set-up-a-b2c-tenant-in-commerce"></a><span data-ttu-id="df0ce-103">Configurar um locatário B2C do Commerce</span><span class="sxs-lookup"><span data-stu-id="df0ce-103">Set up a B2C tenant in Commerce</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="df0ce-104">Este tópico descreve como configurar os locatários business-to-consumer (B2C) do Azure Active Directory (Azure AD) para a autenticação do site de usuário no Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="df0ce-104">This topic describes how to set up your Azure Active Directory (Azure AD) business-to-consumer (B2C) tenants for user site authentication in Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="df0ce-105">Visão Geral</span><span class="sxs-lookup"><span data-stu-id="df0ce-105">Overview</span></span>

<span data-ttu-id="df0ce-106">O Dynamics 365 Commerce usa o B2C do Azure AD para oferecer suporte aos fluxos de credenciais e autenticação de usuário.</span><span class="sxs-lookup"><span data-stu-id="df0ce-106">Dynamics 365 Commerce uses Azure AD B2C to support user credential and authentication flows.</span></span> <span data-ttu-id="df0ce-107">Um usuário pode se inscrever, acessar e redefinir a senha por meio desses fluxos.</span><span class="sxs-lookup"><span data-stu-id="df0ce-107">A user can sign up, sign in, and reset their password through these flows.</span></span> <span data-ttu-id="df0ce-108">O B2C do Azure AD armazena informações confidenciais de autenticação do usuário, como nome de usuário e senha.</span><span class="sxs-lookup"><span data-stu-id="df0ce-108">Azure AD B2C stores sensitive user authentication information, such as username and password.</span></span> <span data-ttu-id="df0ce-109">O registro de usuário no locatário B2C armazenará um registro de conta local B2C ou um registro de provedor de identidade social B2C.</span><span class="sxs-lookup"><span data-stu-id="df0ce-109">The user record in the B2C tenant will store either a B2C local account record or a B2C social identity provider record.</span></span> <span data-ttu-id="df0ce-110">Esses registros de B2C serão vinculados ao registro do cliente no ambiente do Commerce.</span><span class="sxs-lookup"><span data-stu-id="df0ce-110">These B2C records will link back to the customer record in the Commerce environment.</span></span>

## <a name="create-or-link-to-an-existing-aad-b2c-tenant-in-the-azure-portal"></a><span data-ttu-id="df0ce-111">Criar ou vincular a um locatário B2C do AAD no portal do Azure</span><span class="sxs-lookup"><span data-stu-id="df0ce-111">Create or link to an existing AAD B2C tenant in the Azure portal</span></span>

1. <span data-ttu-id="df0ce-112">Entre no [portal do Azure](https://portal.azure.com/).</span><span class="sxs-lookup"><span data-stu-id="df0ce-112">Sign in to the [Azure portal](https://portal.azure.com/).</span></span>
1. <span data-ttu-id="df0ce-113">No menu do portal do Azure, selecione **Criar um recurso**.</span><span class="sxs-lookup"><span data-stu-id="df0ce-113">From the Azure portal menu, select **Create a resource**.</span></span> <span data-ttu-id="df0ce-114">Certifique-se de usar a assinatura e o diretório que será conectado ao ambiente do Commerce.</span><span class="sxs-lookup"><span data-stu-id="df0ce-114">Be sure to use the subscription and directory that will be connected with your Commerce environment.</span></span>

    ![Criar um Recurso no Portal do Azure](./media/B2CImage_1.png)

1. <span data-ttu-id="df0ce-116">Vá para **Identidade \> B2C do Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="df0ce-116">Go to **Identity \> Azure Active Directory B2C**.</span></span>
1. <span data-ttu-id="df0ce-117">Na página **Criar Locatário B2C ou Vincular a um Locatário existente**, use uma das opções abaixo que melhor atende às necessidades da sua empresa:</span><span class="sxs-lookup"><span data-stu-id="df0ce-117">Once on the **Create New B2C Tenant or Link to existing Tenant** page, use one of the options below that best suits your company's needs:</span></span>

    - <span data-ttu-id="df0ce-118">**Criar Locatário B2C do Azure AD**: Use esta opção para criar um locatário B2C do AAD.</span><span class="sxs-lookup"><span data-stu-id="df0ce-118">**Create a new Azure AD B2C Tenant**: Use this option to create a new AAD B2C tenant.</span></span>
        1. <span data-ttu-id="df0ce-119">Selecione **Criar Locatário B2C do Azure AD**.</span><span class="sxs-lookup"><span data-stu-id="df0ce-119">Select **Create a new Azure AD B2C Tenant**.</span></span>
        1. <span data-ttu-id="df0ce-120">Em **Nome da organização**, insira o nome da organização.</span><span class="sxs-lookup"><span data-stu-id="df0ce-120">Under **Organization name**, enter the organization name.</span></span>
        1. <span data-ttu-id="df0ce-121">Em **Nome do domínio inicial**, insira o nome do domínio inicial.</span><span class="sxs-lookup"><span data-stu-id="df0ce-121">Under **Initial domain name**, enter the initial domain name.</span></span>
        1. <span data-ttu-id="df0ce-122">Em **País ou região**, selecione o país ou a região.</span><span class="sxs-lookup"><span data-stu-id="df0ce-122">For **Country or region**, select the country or region.</span></span>
        1. <span data-ttu-id="df0ce-123">Selecione **Criar** para criar o locatário.</span><span class="sxs-lookup"><span data-stu-id="df0ce-123">Select **Create** to create the tenant.</span></span>

     ![Criar um Locatário do Azure AD](./media/B2CImage_2.png)

     - <span data-ttu-id="df0ce-125">**Vincular um Locatário B2C do Azure AD à minha assinatura do Azure**: Use esta opção se já tiver um locatário B2C do Azure AD ao qual deseja vincular.</span><span class="sxs-lookup"><span data-stu-id="df0ce-125">**Link an existing Azure AD B2C Tenant to my Azure subscription**: Use this option if you already have an Azure AD B2C tenant you want to link to.</span></span>
        1. <span data-ttu-id="df0ce-126">Selecione **Vincular um Locatário B2C do Azure AD existente à minha assinatura do Azure**.</span><span class="sxs-lookup"><span data-stu-id="df0ce-126">Select **Link an existing Azure AD B2C Tenant to my Azure subscription**.</span></span>
        1. <span data-ttu-id="df0ce-127">Em **Locatário B2C do Azure AD**, selecione o locatário B2C apropriado.</span><span class="sxs-lookup"><span data-stu-id="df0ce-127">For **Azure AD B2C Tenant**, select the appropriate B2C tenant.</span></span> <span data-ttu-id="df0ce-128">Se a mensagem "Nenhum locatário B2C elegível encontrado" aparecer na caixa de seleção, você não tem um locatário B2C elegível existente e precisará criar um.</span><span class="sxs-lookup"><span data-stu-id="df0ce-128">If the message "No eligible B2C Tenants found" appears in the selection box, you do not have an existing eligible B2C tenant and will need to create a new one.</span></span>
        1. <span data-ttu-id="df0ce-129">Em **Grupo de recursos**, selecione **Criar**.</span><span class="sxs-lookup"><span data-stu-id="df0ce-129">For **Resource group**, select **Create new**.</span></span> <span data-ttu-id="df0ce-130">Insira um **Nome** para o grupo de recursos que conterá o locatário, selecione **Local o grupo de recursos** e selecione **Criar**.</span><span class="sxs-lookup"><span data-stu-id="df0ce-130">Enter a **Name** for the resource group that will contain the tenant, select the **Resource group location**, and then select **Create**.</span></span>

    ![Vincule um Locatário B2C do Azure AD existente à Assinatura do Azure](./media/B2CImage_3.png)

1. <span data-ttu-id="df0ce-132">Após criar diretório B2C do Azure AD (pode demorar alguns instantes), será exibido um link para o novo diretório no painel.</span><span class="sxs-lookup"><span data-stu-id="df0ce-132">Once the new Azure AD B2C directory is created (this may take a few moments), a link to the new directory will appear on the dashboard.</span></span> <span data-ttu-id="df0ce-133">Este link direcionará você para a página "Bem-vinco ao B2C do Azure Active Directory".</span><span class="sxs-lookup"><span data-stu-id="df0ce-133">This link will direct you to the "Welcome to Azure Active Directory B2C" page.</span></span>

    ![Link para o novo Diretório do AAD](./media/B2CImage_4.png)

> [!NOTE]
> <span data-ttu-id="df0ce-135">Se você tiver várias assinaturas na conta do Azure ou tiver configurado o locatário B2C sem vincular a uma assinatura ativa, um banner de **Solução de problemas** orientará você a vincular o locatário a uma assinatura.</span><span class="sxs-lookup"><span data-stu-id="df0ce-135">If you have multiple subscriptions within your Azure account or have set up the B2C tenant without linking to an active subscription, a **Troubleshoot** banner will direct you to link the tenant to a subscription.</span></span> <span data-ttu-id="df0ce-136">Selecione a mensagem de solução de problemas e siga as instruções para resolver o problema da assinatura.</span><span class="sxs-lookup"><span data-stu-id="df0ce-136">Select the troubleshooting message and follow the instructions to resolve the subscription issue.</span></span>

<span data-ttu-id="df0ce-137">A imagem a seguir mostra um exemplo de um banner de **Solução de problemas** do B2C do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="df0ce-137">The following image shows an example of an Azure AD B2C **Troubleshoot** banner.</span></span>

![Aviso mostrando que o diretório não tem uma Assinatura Ativa](./media/B2CImage_5.png)

## <a name="create-the-b2c-application"></a><span data-ttu-id="df0ce-139">Criar o aplicativo B2C</span><span class="sxs-lookup"><span data-stu-id="df0ce-139">Create the B2C application</span></span>

<span data-ttu-id="df0ce-140">Após o locatário B2C ter sido criado, você criará um aplicativo B2C dentro do locatário para interagir com as ações do Commerce.</span><span class="sxs-lookup"><span data-stu-id="df0ce-140">Once the B2C tenant has been created, you will create a B2C application within the tenant to interact with the Commerce actions.</span></span>

<span data-ttu-id="df0ce-141">Para criar o aplicativo B2C, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="df0ce-141">To create the B2C application, follow these steps.</span></span>

1. <span data-ttu-id="df0ce-142">No portal do Azure, selecione **Aplicativos** e selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="df0ce-142">In the Azure portal, select **Applications** and then select **Add**.</span></span>
1. <span data-ttu-id="df0ce-143">Em **Nome**, insira o nome do aplicativo B2C do AAD desejado.</span><span class="sxs-lookup"><span data-stu-id="df0ce-143">Under **Name**, enter the name of the desired AAD B2C application.</span></span>
1. <span data-ttu-id="df0ce-144">Em **Aplicativo Web/API Web**, para **Incluir aplicativo web/ API web**, selecione **Sim**.</span><span class="sxs-lookup"><span data-stu-id="df0ce-144">Under **Web App/Web API**, for **Include web app / web API**, select **Yes**.</span></span>
1. <span data-ttu-id="df0ce-145">Em **Permitir fluxo implícito**, selecione **Sim** (o valor padrão).</span><span class="sxs-lookup"><span data-stu-id="df0ce-145">For **Allow implicit flow**, select **Yes** (the default value).</span></span>
1. <span data-ttu-id="df0ce-146">Em **URL de resposta**, insira as URLs de resposta dedicadas.</span><span class="sxs-lookup"><span data-stu-id="df0ce-146">Under **Reply URL**, enter your dedicated reply URLs.</span></span> <span data-ttu-id="df0ce-147">Consulte [URLs de resposta](#reply-urls) abaixo para obter informações sobre URLs de resposta e como formatá-las aqui.</span><span class="sxs-lookup"><span data-stu-id="df0ce-147">See [Reply URLs](#reply-urls) below for information on reply URLs and how to format them here.</span></span>
1. <span data-ttu-id="df0ce-148">Para **Incluir cliente nativo**, selecione **Não** (o valor padrão).</span><span class="sxs-lookup"><span data-stu-id="df0ce-148">For **Include native client**, select **No** (the default value).</span></span>
1. <span data-ttu-id="df0ce-149">Selecione **Criar**.</span><span class="sxs-lookup"><span data-stu-id="df0ce-149">Select **Create**.</span></span>

### <a name="reply-urls"></a><span data-ttu-id="df0ce-150">URLs de resposta</span><span class="sxs-lookup"><span data-stu-id="df0ce-150">Reply URLs</span></span>

<span data-ttu-id="df0ce-151">As URLs de resposta são importantes, pois permitem uma lista de permissões dos domínios de retorno quando o seu site chamar o B2C do Azure AD para autenticar um usuário.</span><span class="sxs-lookup"><span data-stu-id="df0ce-151">Reply URLs are important as they allow a whitelist of the return domains when your site calls Azure AD B2C to authenticate a user.</span></span> <span data-ttu-id="df0ce-152">Isto permite o retorno do usuário autenticado para o domínio a partir do qual estão tentando fazer o logon (domínio do seu site).</span><span class="sxs-lookup"><span data-stu-id="df0ce-152">This allows the return of the authenticated user back to the domain from which they are signing into (your site domain).</span></span> 

<span data-ttu-id="df0ce-153">Na caixa **URL de resposta** na tela **B2C do Azure AD – Aplicativos \> Novo aplicativo**, será necessário adicionar linhas separadas ao domínio do site e (após o ambiente ser provisionado) à URL gerada pelo Commerce.</span><span class="sxs-lookup"><span data-stu-id="df0ce-153">In the **Reply URL** box on the **Azure AD B2c - Applications \> New application** screen, you need to add separate lines for both your site domain and (once your environment is provisioned) the Commerce-generated URL.</span></span> <span data-ttu-id="df0ce-154">Essas URLs devem sempre usar um formato de URL válido e devem ser somente URLs base (sem barras ou caminhos à direita).</span><span class="sxs-lookup"><span data-stu-id="df0ce-154">These URLs must always use a valid URL format and must be base URLs only (no trailing forward slashes or paths).</span></span> <span data-ttu-id="df0ce-155">A string ``/_msdyn365/authresp`` precisará ser inserida às URLs base, como nos seguintes exemplos.</span><span class="sxs-lookup"><span data-stu-id="df0ce-155">The string ``/_msdyn365/authresp`` then needs to be appended to the base URLs, as in the following examples.</span></span>

- ``https://fabrikam.com/_msdyn365/authresp``
- ``https://fabrikam-prod.commerce.dynamics.com/_msdyn365/authresp``

## <a name="create-user-flow-policies"></a><span data-ttu-id="df0ce-156">Criar políticas de fluxo de usuário</span><span class="sxs-lookup"><span data-stu-id="df0ce-156">Create user flow policies</span></span>

<span data-ttu-id="df0ce-157">Os fluxos de usuário são as políticas que o B2C do Azure AD usa para fornecer experiências seguras de logon, inscrição, edição de perfil e esquecer senha.</span><span class="sxs-lookup"><span data-stu-id="df0ce-157">User flows are the policies Azure AD B2C uses to provide secure sign in, sign up, edit profile, and forget password user experiences.</span></span> <span data-ttu-id="df0ce-158">O Dynamics 365 Commerce usa esses fluxos para realizar ações de políticas para interagir com o locatário B2C do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="df0ce-158">Dynamics 365 Commerce uses these flows to perform the policy actions to interact with the Azure AD B2C tenant.</span></span> <span data-ttu-id="df0ce-159">Quando um usuário interage com essas políticas, ele é redirecionado para o locatário do B2C do Azure AD para realizar as ações.</span><span class="sxs-lookup"><span data-stu-id="df0ce-159">When a user interacts with these policies, they are redirected to the Azure AD B2C tenant to perform the actions.</span></span>

<span data-ttu-id="df0ce-160">O B2C do Azure AD fornece três tipos de fluxo de usuário básicos:</span><span class="sxs-lookup"><span data-stu-id="df0ce-160">Azure AD B2C provides three basic user flow types:</span></span>
- <span data-ttu-id="df0ce-161">Inscrever-se e fazer logon</span><span class="sxs-lookup"><span data-stu-id="df0ce-161">Sign up and sign in</span></span>
- <span data-ttu-id="df0ce-162">Edição de perfil</span><span class="sxs-lookup"><span data-stu-id="df0ce-162">Profile editing</span></span>
- <span data-ttu-id="df0ce-163">Senha redefinida</span><span class="sxs-lookup"><span data-stu-id="df0ce-163">Password reset</span></span>

<span data-ttu-id="df0ce-164">Você pode optar por usar os fluxos de usuário padrão fornecidos pelo Azure AD, que exibirão uma página hospedada pelo B2C do AAD.</span><span class="sxs-lookup"><span data-stu-id="df0ce-164">You can choose to use the default user flows provided by Azure AD, which will display a page hosted by AAD B2C.</span></span> <span data-ttu-id="df0ce-165">Como alternativa, é possível criar uma página HTML para controlar a aparência e a experiência desses fluxos de usuário.</span><span class="sxs-lookup"><span data-stu-id="df0ce-165">Alternately, you can create an HTML page to control the look and feel of these user flow experiences.</span></span> 

<span data-ttu-id="df0ce-166">Para personalizar as páginas de política de usuário do Dynamics 365 Commerce, consulte [Configurar páginas personalizadas para logons de usuário](custom-pages-user-logins.md).</span><span class="sxs-lookup"><span data-stu-id="df0ce-166">To customize the user policy pages for Dynamics 365 Commerce, see [Set up custom pages for user logins](custom-pages-user-logins.md).</span></span> <span data-ttu-id="df0ce-167">Para obter informações adicionais, consulte [Personalizar a interface de experiências de usuário no B2C do Azure Active Directory](https://docs.microsoft.com/azure/active-directory-b2c/tutorial-customize-ui).</span><span class="sxs-lookup"><span data-stu-id="df0ce-167">For additional information, see [Customize the interface of user experiences in Azure Active Directory B2C](https://docs.microsoft.com/azure/active-directory-b2c/tutorial-customize-ui).</span></span>

### <a name="create-a-sign-up-and-sign-in-user-flow-policy"></a><span data-ttu-id="df0ce-168">Criar uma política fluxo de usuário de inscrição e logon</span><span class="sxs-lookup"><span data-stu-id="df0ce-168">Create a sign up and sign in user flow policy</span></span>

<span data-ttu-id="df0ce-169">Para criar uma política de fluxo de usuário de inscrição e logon, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="df0ce-169">To create a sign up and sign in user flow policy, follow these steps.</span></span>

1. <span data-ttu-id="df0ce-170">No portal do Azure, selecione **Fluxos de usuário (políticas)** no painel de navegação esquerdo.</span><span class="sxs-lookup"><span data-stu-id="df0ce-170">In the Azure portal, select **User flows (policies)** in the left navigation pane.</span></span>
1. <span data-ttu-id="df0ce-171">Na página do **B2C do Azure AD – Fluxos de usuário (políticas)**, selecione **Novo Fluxo de Usuário**.</span><span class="sxs-lookup"><span data-stu-id="df0ce-171">On the **Azure AD B2C – User flows (policies)** page, select **New User Flow**.</span></span>
1. <span data-ttu-id="df0ce-172">Na guia **Recomendado**, selecione **Inscrever-se e fazer logon**.</span><span class="sxs-lookup"><span data-stu-id="df0ce-172">On the **Recommended** tab, select **Sign up and sign in**.</span></span>
1. <span data-ttu-id="df0ce-173">Em **Nome**, insira um nome da política.</span><span class="sxs-lookup"><span data-stu-id="df0ce-173">Under **Name**, enter a policy name.</span></span> <span data-ttu-id="df0ce-174">Esse nome será exibido após um prefixo atribuído pelo portal (por exemplo, "B2C_1_").</span><span class="sxs-lookup"><span data-stu-id="df0ce-174">This name will display afterwards with a prefix the portal assigns (for example, "B2C_1_").</span></span>
1. <span data-ttu-id="df0ce-175">Em **Provedores de identidade**, marque a caixa de seleção apropriada.</span><span class="sxs-lookup"><span data-stu-id="df0ce-175">Under **Identity providers**, select the appropriate check box.</span></span>
1. <span data-ttu-id="df0ce-176">Em **Autenticação Multifator**, selecione a escolha apropriada para a sua empresa.</span><span class="sxs-lookup"><span data-stu-id="df0ce-176">Under **Multifactor Authentication**, select the appropriate choice for your company.</span></span> 
1. <span data-ttu-id="df0ce-177">Em **Atributos e declarações de usuário**, selecione as opções para coletar atributos ou retornar reivindicações, conforme apropriado.</span><span class="sxs-lookup"><span data-stu-id="df0ce-177">Under **User attributes and claims**, select options to collect attributes or return claims as appropriate.</span></span> <span data-ttu-id="df0ce-178">O Commerce requer as seguintes opções padrão:</span><span class="sxs-lookup"><span data-stu-id="df0ce-178">Commerce requires the following default options:</span></span>

    | <span data-ttu-id="df0ce-179">**Coletar atributo**</span><span class="sxs-lookup"><span data-stu-id="df0ce-179">**Collect  attribute**</span></span> | <span data-ttu-id="df0ce-180">**Retornar reivindicação**</span><span class="sxs-lookup"><span data-stu-id="df0ce-180">**Return  claim**</span></span> |
    | ---------------------- | ----------------- |
    |                        | <span data-ttu-id="df0ce-181">Endereços de Email</span><span class="sxs-lookup"><span data-stu-id="df0ce-181">Email Addresses</span></span>   |
    | <span data-ttu-id="df0ce-182">Nome Fornecido</span><span class="sxs-lookup"><span data-stu-id="df0ce-182">Given Name</span></span>             | <span data-ttu-id="df0ce-183">Nome Fornecido</span><span class="sxs-lookup"><span data-stu-id="df0ce-183">Given Name</span></span>        |
    |                        | <span data-ttu-id="df0ce-184">Provedor de Identidade</span><span class="sxs-lookup"><span data-stu-id="df0ce-184">Identity Provider</span></span> |
    | <span data-ttu-id="df0ce-185">Sobrenome</span><span class="sxs-lookup"><span data-stu-id="df0ce-185">Surname</span></span>                | <span data-ttu-id="df0ce-186">Sobrenome</span><span class="sxs-lookup"><span data-stu-id="df0ce-186">Surname</span></span>           |
    |                        | <span data-ttu-id="df0ce-187">ID do Objeto do Usuário</span><span class="sxs-lookup"><span data-stu-id="df0ce-187">User’s Object ID</span></span>  |

1. <span data-ttu-id="df0ce-188">Selecione **Criar**.</span><span class="sxs-lookup"><span data-stu-id="df0ce-188">Select **Create**.</span></span>

<span data-ttu-id="df0ce-189">A imagem a seguir é um exemplo do fluxo de usuário de inscrição e logon do B2C do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="df0ce-189">The following image is an example of the Azure AD B2C sign up and sign in user flow.</span></span>

![Configurações da política de Inscrição e Logon](./media/B2CImage_11.png)

<span data-ttu-id="df0ce-191">A imagem a seguir mostra a opção **Executar fluxo de usuário** no fluxo de usuário de inscrição e logon do B2C do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="df0ce-191">The following image shows the **Run user flow** option in the Azure AD B2C sign up and sign in user flow.</span></span>

![Executar a opção do fluxo de usuário no fluxo da política](./media/B2CImage_23.png)
   
### <a name="create-a-profile-editing-user-flow-policy"></a><span data-ttu-id="df0ce-193">Criar uma política de fluxo de usuário de edição de perfil</span><span class="sxs-lookup"><span data-stu-id="df0ce-193">Create a profile editing user flow policy</span></span>

<span data-ttu-id="df0ce-194">Para criar uma política de fluxo de usuário de edição de perfil, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="df0ce-194">To create a profile editing user flow policy, follow these steps.</span></span>

1. <span data-ttu-id="df0ce-195">No portal do Azure, selecione **Fluxos de usuário (políticas)** no painel de navegação esquerdo.</span><span class="sxs-lookup"><span data-stu-id="df0ce-195">In the Azure portal, select **User flows (policies)** in the left navigation pane.</span></span>
1. <span data-ttu-id="df0ce-196">Na página do **B2C do Azure AD – Fluxos de usuário (políticas)**, selecione **Novo Fluxo de Usuário**.</span><span class="sxs-lookup"><span data-stu-id="df0ce-196">On the **Azure AD B2C – User flows (policies)** page, select **New User Flow**.</span></span>
1. <span data-ttu-id="df0ce-197">Na guia **Recomendado**, selecione **Edição de perfil**.</span><span class="sxs-lookup"><span data-stu-id="df0ce-197">On the **Recommended** tab, select **Profile editing**.</span></span>
1. <span data-ttu-id="df0ce-198">Em **Nome**, insira o fluxo de usuário de edição de perfil.</span><span class="sxs-lookup"><span data-stu-id="df0ce-198">Under **Name**, enter the profile editing user flow.</span></span> <span data-ttu-id="df0ce-199">Esse nome será exibido após um prefixo atribuído pelo portal (por exemplo, "B2C_1_").</span><span class="sxs-lookup"><span data-stu-id="df0ce-199">This name will display afterwards with a prefix the portal assigns (for example, "B2C_1_").</span></span>
1. <span data-ttu-id="df0ce-200">Em **Provedores de identidade**, selecione **Logon da Conta Local**.</span><span class="sxs-lookup"><span data-stu-id="df0ce-200">Under **Identity providers**, select **Local Account SignIn**.</span></span>
1. <span data-ttu-id="df0ce-201">Em **Atributos do usuário**, marque as seguintes caixas de seleção:</span><span class="sxs-lookup"><span data-stu-id="df0ce-201">Under **User attributes**, select the following check boxes:</span></span>
    - <span data-ttu-id="df0ce-202">**Endereços de Email** (somente **Retornar reivindicação**)</span><span class="sxs-lookup"><span data-stu-id="df0ce-202">**Email Addresses** (**Return claim** only)</span></span>
    - <span data-ttu-id="df0ce-203">**Nome Fornecido** (**Coletar atributo** e **Retornar reivindicação**)</span><span class="sxs-lookup"><span data-stu-id="df0ce-203">**Given Name** (**Collect attribute** and **Return claim**)</span></span>
    - <span data-ttu-id="df0ce-204">**Provedor de Identidade** (somente **Retornar reivindicação**)</span><span class="sxs-lookup"><span data-stu-id="df0ce-204">**Identity Provider** (**Return claim** only)</span></span>
    - <span data-ttu-id="df0ce-205">**Sobrenome** (**Coletar atributo** e **Retornar reivindicação**)</span><span class="sxs-lookup"><span data-stu-id="df0ce-205">**Surname** (**Collect attribute** and **Return claim**)</span></span>
    - <span data-ttu-id="df0ce-206">**ID de Objeto do Usuário** (somente **Retornar reivindicação**)</span><span class="sxs-lookup"><span data-stu-id="df0ce-206">**User's Object ID** (**Return claim** only)</span></span>
1. <span data-ttu-id="df0ce-207">Selecione **Criar**.</span><span class="sxs-lookup"><span data-stu-id="df0ce-207">Select **Create**.</span></span>

<span data-ttu-id="df0ce-208">A imagem a seguir mostra um exemplo do fluxo de usuário de edição do perfil do B2C do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="df0ce-208">The following image shows an example of the Azure AD B2C profile editing user flow.</span></span>

![Criar o fluxo de usuário de Edição de Perfil](./media/B2CImage_12.png)

### <a name="create-a-password-reset-user-flow-policy"></a><span data-ttu-id="df0ce-210">Criar uma política de fluxo de usuário de redefinição de senha</span><span class="sxs-lookup"><span data-stu-id="df0ce-210">Create a password reset user flow policy</span></span>

<span data-ttu-id="df0ce-211">Para criar uma política de fluxo de usuário de redefinição de senha, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="df0ce-211">To create a password reset user flow policy, follow these steps.</span></span>

1. <span data-ttu-id="df0ce-212">No portal do Azure, selecione **Fluxos de usuário (políticas)** no painel de navegação esquerdo.</span><span class="sxs-lookup"><span data-stu-id="df0ce-212">In the Azure portal, select **User flows (policies)** in the left navigation pane.</span></span>
1. <span data-ttu-id="df0ce-213">Na página do **B2C do Azure AD – Fluxos de usuário (políticas)**, selecione **Novo Fluxo de Usuário**.</span><span class="sxs-lookup"><span data-stu-id="df0ce-213">On the **Azure AD B2C – User flows (policies)** page, select **New User Flow**.</span></span>
1. <span data-ttu-id="df0ce-214">Na guia **Recomendado**, selecione **Redefinição de Senha**.</span><span class="sxs-lookup"><span data-stu-id="df0ce-214">On the **Recommended** tab, select **Password Reset**.</span></span>
1. <span data-ttu-id="df0ce-215">Em **Nome**, insira um nome para o fluxo de usuário de redefinição de senha.</span><span class="sxs-lookup"><span data-stu-id="df0ce-215">Under **Name**, enter a name for the password reset user flow.</span></span>
1. <span data-ttu-id="df0ce-216">Em **Provedores de identidade**, selecione **Redefinir senha usando endereço de email**.</span><span class="sxs-lookup"><span data-stu-id="df0ce-216">Under **Identity providers**, select **Reset password using email address**.</span></span>
1. <span data-ttu-id="df0ce-217">Selecione **Criar**.</span><span class="sxs-lookup"><span data-stu-id="df0ce-217">Select **Create**.</span></span>
1. <span data-ttu-id="df0ce-218">Em **Declarações do aplicativo**, marque as seguintes caixas de seleção:</span><span class="sxs-lookup"><span data-stu-id="df0ce-218">Under **Application claims**, select the following check boxes:</span></span>
    - <span data-ttu-id="df0ce-219">**Email**</span><span class="sxs-lookup"><span data-stu-id="df0ce-219">**Email**</span></span>
    - <span data-ttu-id="df0ce-220">**Endereços**</span><span class="sxs-lookup"><span data-stu-id="df0ce-220">**Addresses**</span></span>
    - <span data-ttu-id="df0ce-221">**Nome Fornecido**</span><span class="sxs-lookup"><span data-stu-id="df0ce-221">**Given Name**</span></span>
    - <span data-ttu-id="df0ce-222">**Sobrenome**</span><span class="sxs-lookup"><span data-stu-id="df0ce-222">**Surname**</span></span>
    - <span data-ttu-id="df0ce-223">**ID do Objeto do Usuário**</span><span class="sxs-lookup"><span data-stu-id="df0ce-223">**User's Object ID**</span></span>
1. <span data-ttu-id="df0ce-224">Selecione **Criar**.</span><span class="sxs-lookup"><span data-stu-id="df0ce-224">Select **Create**.</span></span>

<span data-ttu-id="df0ce-225">A imagem a seguir mostra onde definir **Redefinir Senha usando endereço de email** no fluxo de usuário de redefinição de senha do B2C do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="df0ce-225">The following image shows where to set **Reset Password using mail address** in the Azure AD B2C password reset user flow.</span></span>

![Configure "Redefinir Senha usando endereço de email" na política de Redefinição de Senha](./media/B2CImage_13.png)

## <a name="add-social-identity-providers-optional"></a><span data-ttu-id="df0ce-227">Adicionar provedores de identidade social (Opcional)</span><span class="sxs-lookup"><span data-stu-id="df0ce-227">Add social identity providers (Optional)</span></span>

<span data-ttu-id="df0ce-228">Os provedores de identidade social permitem que os usuários usem suas contas sociais para autenticação.</span><span class="sxs-lookup"><span data-stu-id="df0ce-228">Social identity providers allow users to use their social accounts for authentication.</span></span> <span data-ttu-id="df0ce-229">Incluir a autenticação de provedor de identidade social é opcional no Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="df0ce-229">Adding social identity provider authentication is optional in Dynamics 365 Commerce.</span></span> 

<span data-ttu-id="df0ce-230">Se a autenticação de provedor de identidade social não for adicionada, os perfis padrão do B2C do Azure AD serão os perfis principais da sua base de usuários.</span><span class="sxs-lookup"><span data-stu-id="df0ce-230">If social identity provider authentication is not added, the default Azure AD B2C profiles will be the main profiles for your user base.</span></span> <span data-ttu-id="df0ce-231">Os usuários selecionarão o próprio nome de usuário (endereço de email preferencial) e definirão uma senha.</span><span class="sxs-lookup"><span data-stu-id="df0ce-231">Users will select their own username (their preferred email address) and set a password.</span></span> <span data-ttu-id="df0ce-232">O B2C do Azure AD autenticará os usuários diretamente.</span><span class="sxs-lookup"><span data-stu-id="df0ce-232">Azure AD B2C will authenticate users directly.</span></span> 

<span data-ttu-id="df0ce-233">Se a autenticação do provedor de identidade social for adicionada e um usuário escolher um dos provedores de identidade social fornecidos, uma entidade ainda será criada no locatário B2C do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="df0ce-233">If social identity provider authentication is added and a user chooses one of the social identity providers offered, an entity is still created in the Azure AD B2C tenant.</span></span> <span data-ttu-id="df0ce-234">O B2C do Azure AD autenticará as credenciais do usuário com o provedor de identidade social.</span><span class="sxs-lookup"><span data-stu-id="df0ce-234">Azure AD B2C will then authenticate the user's credentials with the social identity provider.</span></span>

> [!NOTE]
> <span data-ttu-id="df0ce-235">O logon do provedor de identidade cria um registro no locatário do B2C, mas em um formato diferente das contas locais, pois chamará a referência externa do provedor de identidade social para a autenticação.</span><span class="sxs-lookup"><span data-stu-id="df0ce-235">The identity provider sign in creates a record in the B2C tenant, but in a different format than local accounts since it will call the external social identity provider reference for authentication.</span></span> <span data-ttu-id="df0ce-236">O usuário pode usar o mesmo endereço de email em todos os provedores de identidade social, indicando que o nome de usuário do email usado para a autenticação pode não ser exclusivo para o locatário.</span><span class="sxs-lookup"><span data-stu-id="df0ce-236">The user can use the same email address across social identity providers, meaning that the email username used for authentication may not be unique to the tenant.</span></span> <span data-ttu-id="df0ce-237">O B2C do Azure AD apenas irá impor que os usuários tenham um endereço de email exclusivo nas contas locais do B2C.</span><span class="sxs-lookup"><span data-stu-id="df0ce-237">Azure AD B2C will only enforce that users have a unique email address on local B2C accounts.</span></span>

<span data-ttu-id="df0ce-238">Antes de adicionar um provedor de identidade social para autenticação, vá para o portal do provedor de identidade e configure um aplicativo de provedor de identidade conforme as orientações na documentação do B2C do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="df0ce-238">Before you can add a social identity provider for authentication, you must go to the identity provider's portal and set up an identity provider application as instructed in the Azure AD B2C documentation.</span></span> <span data-ttu-id="df0ce-239">Uma lista de links para a documentação é fornecida a seguir.</span><span class="sxs-lookup"><span data-stu-id="df0ce-239">A list of links to the documentation is provided below.</span></span>

- [<span data-ttu-id="df0ce-240">Amazon</span><span class="sxs-lookup"><span data-stu-id="df0ce-240">Amazon</span></span>](https://docs.microsoft.com/azure/active-directory-b2c/active-directory-b2c-setup-amzn-app)
- [<span data-ttu-id="df0ce-241">Azure AD (Único Locatário)</span><span class="sxs-lookup"><span data-stu-id="df0ce-241">Azure AD (Single Tenant)</span></span>](https://docs.microsoft.com/azure/active-directory-b2c/active-directory-b2c-setup-oidc-azure-active-directory)
- [<span data-ttu-id="df0ce-242">Conta da Microsoft</span><span class="sxs-lookup"><span data-stu-id="df0ce-242">Microsoft Account</span></span>](https://docs.microsoft.com/azure/active-directory-b2c/active-directory-b2c-setup-msa-app)
- [<span data-ttu-id="df0ce-243">Facebook</span><span class="sxs-lookup"><span data-stu-id="df0ce-243">Facebook</span></span>](https://docs.microsoft.com/azure/active-directory-b2c/active-directory-b2c-setup-fb-app)
- [<span data-ttu-id="df0ce-244">GitHub</span><span class="sxs-lookup"><span data-stu-id="df0ce-244">GitHub</span></span>](https://docs.microsoft.com/azure/active-directory-b2c/active-directory-b2c-setup-github-app)
- [<span data-ttu-id="df0ce-245">Google</span><span class="sxs-lookup"><span data-stu-id="df0ce-245">Google</span></span>](https://docs.microsoft.com/azure/active-directory-b2c/active-directory-b2c-setup-goog-app)
- [<span data-ttu-id="df0ce-246">LinkedIn</span><span class="sxs-lookup"><span data-stu-id="df0ce-246">LinkedIn</span></span>](https://docs.microsoft.com/azure/active-directory-b2c/active-directory-b2c-setup-li-app)
- [<span data-ttu-id="df0ce-247">OpenID Connect</span><span class="sxs-lookup"><span data-stu-id="df0ce-247">OpenID Connect</span></span>](https://docs.microsoft.com/azure/active-directory-b2c/active-directory-b2c-setup-oidc-idp)
- [<span data-ttu-id="df0ce-248">Twitter</span><span class="sxs-lookup"><span data-stu-id="df0ce-248">Twitter</span></span>](https://docs.microsoft.com/azure/active-directory-b2c/active-directory-b2c-setup-twitter-app)

### <a name="add-and-set-up-a-social-identity-provider"></a><span data-ttu-id="df0ce-249">Adicionar e configurar um provedor de identidade social</span><span class="sxs-lookup"><span data-stu-id="df0ce-249">Add and set up a social identity provider</span></span>

<span data-ttu-id="df0ce-250">Para adicionar e configurar um provedor de identidade social, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="df0ce-250">To add and set up a social identity provider, follow these steps.</span></span>  

1. <span data-ttu-id="df0ce-251">No portal do Azure, navegue até **Provedores de Identidade**.</span><span class="sxs-lookup"><span data-stu-id="df0ce-251">In the Azure portal, navigate to **Identity Providers**.</span></span>
1. <span data-ttu-id="df0ce-252">Selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="df0ce-252">Select **Add**.</span></span> <span data-ttu-id="df0ce-253">A tela **Adicionar provedor de identidade** será exibida.</span><span class="sxs-lookup"><span data-stu-id="df0ce-253">The **Add identity provider** screen appears.</span></span>
1. <span data-ttu-id="df0ce-254">Em **Nome**, insira o nome a ser exibido para os usuários na tela de logon.</span><span class="sxs-lookup"><span data-stu-id="df0ce-254">Under **Name**, enter the name to be displayed to users on your sign in screen.</span></span>
1. <span data-ttu-id="df0ce-255">Em **Tipo de provedor de identidade**, selecione um provedor de identidade na lista.</span><span class="sxs-lookup"><span data-stu-id="df0ce-255">Under **Identity provider type**, select an identity provider from the list.</span></span>
1. <span data-ttu-id="df0ce-256">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="df0ce-256">Select **OK**.</span></span>
1. <span data-ttu-id="df0ce-257">Selecione **Configurar este provedor de identidade** para acessar a tela **Configurar provedor de identidade social**.</span><span class="sxs-lookup"><span data-stu-id="df0ce-257">Select **Set up this identity provider** to access the **Set up the social identity provider** screen.</span></span>
1. <span data-ttu-id="df0ce-258">Em **ID do Cliente**, insira o ID do cliente obtido na configuração do aplicativo do provedor de identidade.</span><span class="sxs-lookup"><span data-stu-id="df0ce-258">Under **Client ID**, enter the client ID as obtained from the identity provider application setup.</span></span>
1. <span data-ttu-id="df0ce-259">Em **Segredo do cliente**, insira o segredo do cliente obtido na configuração do aplicativo do provedor de identidade.</span><span class="sxs-lookup"><span data-stu-id="df0ce-259">Under **Client secret**, enter the client secret as obtained from the identity provider application setup.</span></span>
1. <span data-ttu-id="df0ce-260">Anexe o fluxo de usuário para as políticas de inscrição e logon:</span><span class="sxs-lookup"><span data-stu-id="df0ce-260">Attach user flow for sign in sign up policies:</span></span>
1. <span data-ttu-id="df0ce-261">Vá para **B2C do Azure AD – Fluxos de usuário (políticas) \> {sua política de inscrição e logon} \> Provedores de identidade**.</span><span class="sxs-lookup"><span data-stu-id="df0ce-261">Go to **Azure AD B2C – User flows (policies) \> {your sign-in sign-up policy} \> Identity providers**.</span></span>
1. <span data-ttu-id="df0ce-262">Para anexar a política de fluxo de usuário de inscrição/logon, selecione os provedores de identidade configurados para a sua conta.</span><span class="sxs-lookup"><span data-stu-id="df0ce-262">To attach the sign in/sign up user flow policy, select each identity provider you have set up for your account.</span></span> <span data-ttu-id="df0ce-263">Para testá-los, selecione **Executar fluxo de usuário** para cada provedor de identidade.</span><span class="sxs-lookup"><span data-stu-id="df0ce-263">To test these, select **Run user flow** for each identity provider.</span></span> <span data-ttu-id="df0ce-264">Uma nova guia será exibida na página de logon mostrando a caixa de seleção do novo provedor de identidade.</span><span class="sxs-lookup"><span data-stu-id="df0ce-264">A new tab will display the sign-in page displaying the new identity provider selection box.</span></span>

<span data-ttu-id="df0ce-265">A imagem a seguir mostra exemplos das telas **Adicionar provedor de identidade** e **Configurar o provedor de identidade social** no B2C do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="df0ce-265">The following image shows examples of the **Add identity provider** and **Set up the social identity provider** screens in Azure AD B2C.</span></span>

![Adicionar um Provedor de Identidade Social ao aplicativo](./media/B2CImage_14.png)

<span data-ttu-id="df0ce-267">A imagem a seguir mostra um exemplo de como selecionar provedores de identidade na página **Provedores de Identidade** do B2C do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="df0ce-267">The following image shows an example of how to select identity providers on the Azure AD B2C **Identity Providers** page.</span></span>

![Selecione cada Provedor de Identidade Social que será habilitado para a sua política](./media/B2CImage_16.png)

<span data-ttu-id="df0ce-269">A imagem a seguir mostra um exemplo de uma tela de logon padrão com um botão de logon do provedor de identidade social exibido.</span><span class="sxs-lookup"><span data-stu-id="df0ce-269">The following image shows an example of a default sign-in screen with a social identity provider sign-in button displayed.</span></span>

![Exemplo de tela de logon padrão com o botão de logon do Provedor de Identidade Social exibido](./media/B2CImage_17.png)

## <a name="update-commerce-headquarters-with-the-new-azure-ad-b2c-information"></a><span data-ttu-id="df0ce-271">Atualizar o Commerce headquarters com as novas informações do B2C do Azure AD</span><span class="sxs-lookup"><span data-stu-id="df0ce-271">Update Commerce headquarters with the new Azure AD B2C information</span></span>

<span data-ttu-id="df0ce-272">Depois que as etapas de provisionamento do B2C do Azure AD estiverem concluídas, o aplicativo B2C do Azure AD devem ser registrados no ambiente do Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="df0ce-272">Once the Azure AD B2C provisioning steps above are completed, the Azure AD B2C application must be registered in your Dynamics 365 Commerce environment.</span></span>

<span data-ttu-id="df0ce-273">Para atualizar o headquarters com as novas informações do B2C do Azure AD, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="df0ce-273">To update headquarters with the new Azure AD B2C information, follow these steps.</span></span>

1. <span data-ttu-id="df0ce-274">No Commerce, vá para **Parâmetros Compartilhados do Commerce** e selecione **Provedores de Identidade** no menu esquerdo.</span><span class="sxs-lookup"><span data-stu-id="df0ce-274">In Commerce, go to **Commerce Shared Parameters** and select **Identity Providers** in the left menu.</span></span>
1. <span data-ttu-id="df0ce-275">Em **Provedores de Identidade**, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="df0ce-275">Under **Identity Providers**, do the following:</span></span>
    1. <span data-ttu-id="df0ce-276">Na caixa **Emissor**, insira o URL do emissor do provedor de identidade.</span><span class="sxs-lookup"><span data-stu-id="df0ce-276">In the **Issuer** box, enter the identity provider issuer URL.</span></span> <span data-ttu-id="df0ce-277">Para encontrar o URL do emissor, consulte [Obter URL do emissor](#obtain-issuer-url) abaixo.</span><span class="sxs-lookup"><span data-stu-id="df0ce-277">To find your issuer URL, see [Obtain issuer URL](#obtain-issuer-url) below.</span></span>
    1. <span data-ttu-id="df0ce-278">Na caixa **Nome**, insira um nome para o registro do emissor.</span><span class="sxs-lookup"><span data-stu-id="df0ce-278">In the **Name** box, enter a name for your issuer record.</span></span>
    1. <span data-ttu-id="df0ce-279">Na caixa **Tipo**, insira **B2C do Azure AD (id_token)**.</span><span class="sxs-lookup"><span data-stu-id="df0ce-279">In the **Type** box, enter **Azure AD B2C (id_token)**.</span></span>
1. <span data-ttu-id="df0ce-280">Em **Partes Confiáveis**, com o item do provedor de identidade do B2C acima selecionado, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="df0ce-280">Under **Relying Parties**, with the above B2C identity provider item selected, do the following:</span></span>
    1. <span data-ttu-id="df0ce-281">Na caixa **ClientID**, insira a ID do aplicativo B2C.</span><span class="sxs-lookup"><span data-stu-id="df0ce-281">In the **ClientID** box, enter your B2C application ID.</span></span> <span data-ttu-id="df0ce-282">Isso pode ser encontrado na caixa **ID do Aplicativo** na página de propriedades do aplicativo B2C.</span><span class="sxs-lookup"><span data-stu-id="df0ce-282">You can find this in the **Application ID** box of your B2C application's properties page.</span></span>
    1. <span data-ttu-id="df0ce-283">Na caixa **Tipo**, insira **Público**.</span><span class="sxs-lookup"><span data-stu-id="df0ce-283">In the **Type** box, enter **Public**.</span></span>
    1. <span data-ttu-id="df0ce-284">Na caixa **Tipo de Usuário**, insira **Cliente**.</span><span class="sxs-lookup"><span data-stu-id="df0ce-284">In the **User Type** box, enter **Customer**.</span></span>
1. <span data-ttu-id="df0ce-285">No painel de ação, selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="df0ce-285">On the action pane, select **Save**.</span></span>
1. <span data-ttu-id="df0ce-286">Na caixa de pesquisa do Commerce, procure **Sequências numéricas** (Administração da organização > Sequências numéricas).</span><span class="sxs-lookup"><span data-stu-id="df0ce-286">In the Commerce search box, search for **Number sequences** (Organization administration > Number sequences).</span></span>
1. <span data-ttu-id="df0ce-287">No painel de ação, selecione **Editar** em **Manter**.</span><span class="sxs-lookup"><span data-stu-id="df0ce-287">Under the action pane, select **Edit** under **Maintain**.</span></span>
1. <span data-ttu-id="df0ce-288">Na guia rápida **Geral**, selecione **Não** para **Manual**.</span><span class="sxs-lookup"><span data-stu-id="df0ce-288">On the **General** fast tab, select **No** for **Manual**.</span></span>
1. <span data-ttu-id="df0ce-289">No painel de ação, selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="df0ce-289">On the action pane, select **Save**.</span></span> 
1. <span data-ttu-id="df0ce-290">Na caixa de pesquisa do Commerce, procure **Agenda de distribuição**</span><span class="sxs-lookup"><span data-stu-id="df0ce-290">In the Commerce search box, search for **Distribution schedule**</span></span>
1. <span data-ttu-id="df0ce-291">No menu de navegação à esquerda da página **Agendas de distribuição**, selecione o trabalho **1110 Configuração global**.</span><span class="sxs-lookup"><span data-stu-id="df0ce-291">In the left navigation menu of the **Distribution schedules** page, select job **1110 Global configuration**.</span></span>
1. <span data-ttu-id="df0ce-292">No painel de ação, selecione **Executar Agora**.</span><span class="sxs-lookup"><span data-stu-id="df0ce-292">On the action pane, select **Run Now**.</span></span>

### <a name="obtain-issuer-url"></a><span data-ttu-id="df0ce-293">Obter URL do emissor</span><span class="sxs-lookup"><span data-stu-id="df0ce-293">Obtain issuer URL</span></span>

<span data-ttu-id="df0ce-294">Para obter o URL do emissor do provedor de identidade, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="df0ce-294">To obtain your identity provider issuer URL, follow these steps.</span></span>

1. <span data-ttu-id="df0ce-295">Crie um URL do endereço de metadados no seguinte formato usando o locatário e a política B2C: ``https://<B2CTENANTNAME>.b2clogin.com/<B2CTENANTNAME>.onmicrosoft.com/v2.0/.well-known/openid-configuration?p=<B2CSIGN-INPOLICY>``</span><span class="sxs-lookup"><span data-stu-id="df0ce-295">Create a metadata address URL in the following format using your B2C tenant and policy: ``https://<B2CTENANTNAME>.b2clogin.com/<B2CTENANTNAME>.onmicrosoft.com/v2.0/.well-known/openid-configuration?p=<B2CSIGN-INPOLICY>``</span></span>
    - <span data-ttu-id="df0ce-296">Exemplo: ``https://d365plc.b2clogin.com/d365plc.onmicrosoft.com/v2.0/.well-known/openid-configuration?p=B2C_1_signinup``.</span><span class="sxs-lookup"><span data-stu-id="df0ce-296">Example: ``https://d365plc.b2clogin.com/d365plc.onmicrosoft.com/v2.0/.well-known/openid-configuration?p=B2C_1_signinup``.</span></span>
1. <span data-ttu-id="df0ce-297">Insira o URL do endereço de metadados na barra de endereço no navegador.</span><span class="sxs-lookup"><span data-stu-id="df0ce-297">Enter the metadata address URL into a browser address bar.</span></span>
1. <span data-ttu-id="df0ce-298">Nos metadados, copie o URL do emissor do provedor de identidade (valor para **"emissor"**).</span><span class="sxs-lookup"><span data-stu-id="df0ce-298">In the metadata, copy the identity provider issuer URL (the value for **"issuer"**).</span></span>
    - <span data-ttu-id="df0ce-299">Exemplo: ``https://login.fabrikam.com/073405c3-0113-4f43-b5e2-df01266e24ae/v2.0/``.</span><span class="sxs-lookup"><span data-stu-id="df0ce-299">Example: ``https://login.fabrikam.com/073405c3-0113-4f43-b5e2-df01266e24ae/v2.0/``.</span></span>

## <a name="configure-your-b2c-tenant-in-commerce-site-builder"></a><span data-ttu-id="df0ce-300">Configurar o locatário B2C no construtor de sites do Commerce</span><span class="sxs-lookup"><span data-stu-id="df0ce-300">Configure your B2C tenant in Commerce site builder</span></span>

<span data-ttu-id="df0ce-301">Após configurar o locatário B2C do Azure AD, será necessário configurar o locatário B2C no construtor de sites do Commerce.</span><span class="sxs-lookup"><span data-stu-id="df0ce-301">Once setup of your Azure AD B2C tenant is completed, you must configure the B2C tenant in Commerce site builder.</span></span> <span data-ttu-id="df0ce-302">As etapas de configuração incluem coletar informações do aplicativo B2C do portal do Azure, inserir as informações do aplicativo B2C no construtor de sites e associar o aplicativo B2C ao site e ao canal.</span><span class="sxs-lookup"><span data-stu-id="df0ce-302">Configuration steps include collecting B2C application information from the Azure portal, entering that B2C application information into site builder, and then associating the B2C application with your site and channel.</span></span>

### <a name="collect-the-required-application-information"></a><span data-ttu-id="df0ce-303">Coletar as informações necessárias do aplicativo</span><span class="sxs-lookup"><span data-stu-id="df0ce-303">Collect the required application information</span></span>

<span data-ttu-id="df0ce-304">Para coletar as informações necessárias do aplicativo, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="df0ce-304">To collect the required application information, follow these steps.</span></span>

1. <span data-ttu-id="df0ce-305">No portal do Azure, vá para **Página Inicial \> B2C do Azure AD – Aplicativos**,</span><span class="sxs-lookup"><span data-stu-id="df0ce-305">In the Azure portal, go to **Home \> Azure AD B2C - Applications**.</span></span>
1. <span data-ttu-id="df0ce-306">Selecione o aplicativo e, no painel de navegação à esquerda, selecione **Propriedades** para obter os detalhes do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="df0ce-306">Select your application, and then in the left navigation pane select **Properties** to obtain the application details.</span></span>
1. <span data-ttu-id="df0ce-307">Na caixa **ID do Aplicativo**, colete a ID do aplicativo B2C criado no seu locatário B2C.</span><span class="sxs-lookup"><span data-stu-id="df0ce-307">From the **Application ID** box, collect the application ID of the B2C application created in your B2C tenant.</span></span> <span data-ttu-id="df0ce-308">Posteriormente, ela será inserida como **GUID do Cliente** no construtor de sites.</span><span class="sxs-lookup"><span data-stu-id="df0ce-308">This will later be entered as the **Client GUID** in site builder.</span></span>
1. <span data-ttu-id="df0ce-309">Em **URL de resposta**, colete o URL de resposta.</span><span class="sxs-lookup"><span data-stu-id="df0ce-309">Under **Reply URL**, collect the reply URL.</span></span>
1. <span data-ttu-id="df0ce-310">Vá para **Página Inicial \> B2C do Azure AD – Fluxos de usuário (políticas)** e colete os nomes de cada política de fluxo de usuário.</span><span class="sxs-lookup"><span data-stu-id="df0ce-310">Go to **Home \> Azure AD B2C – User flows (policies)**, and then collect the names of each user flow policy.</span></span>

<span data-ttu-id="df0ce-311">A imagem a seguir mostra um exemplo da página **B2C do Azure AD – Aplicativos**.</span><span class="sxs-lookup"><span data-stu-id="df0ce-311">The following image shows an example of the **Azure AD B2C - Applications** page.</span></span>

![Navegue até o Aplicativo B2C no locatário](./media/B2CImage_19.png)

<span data-ttu-id="df0ce-313">A imagem a seguir mostra um exemplo da página **Propriedades** de um aplicativo no B2C do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="df0ce-313">The following image shows an example of an application **Properties** page in Azure AD B2C.</span></span> 

![Copiar a ID do Aplicativo nas Propriedades do Aplicativo B2C](./media/B2CImage_21.png)

<span data-ttu-id="df0ce-315">A imagem a seguir mostra um exemplo de políticas de fluxo de usuário na página **B2C do Azure AD – Fluxos de usuário (políticas)**.</span><span class="sxs-lookup"><span data-stu-id="df0ce-315">The following image shows an example of user flow policies on the **Azure AD B2C – User flows (policies)** page.</span></span>

![Coletar os nomes de cada fluxo de política de B2C](./media/B2CImage_22.png)

### <a name="enter-your-aad-b2c-tenant-application-information-into-commerce"></a><span data-ttu-id="df0ce-317">Insira as informações do aplicativo locatário B2C do AAD no Commerce</span><span class="sxs-lookup"><span data-stu-id="df0ce-317">Enter your AAD B2C tenant application information into Commerce</span></span>

<span data-ttu-id="df0ce-318">Insira os detalhes do locatário B2C do Azure AD no construtor de sites do Commerce antes de associar o locatário B2C aos sites.</span><span class="sxs-lookup"><span data-stu-id="df0ce-318">You must enter details of the Azure AD B2C tenant into Commerce site builder before associating the B2C tenant with your site(s).</span></span>

<span data-ttu-id="df0ce-319">Para adicionar as informações do aplicativo locatário B2C do AAD ao Commerce, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="df0ce-319">To add your AAD B2C tenant application information to Commerce, follow these steps.</span></span>

1. <span data-ttu-id="df0ce-320">Faça login como administrador no construtor de sites do Commerce no seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="df0ce-320">Sign in as an administrator to Commerce site builder for your environment.</span></span>
1. <span data-ttu-id="df0ce-321">No painel de navegação esquerdo, selecione **Configurações de Locatário** para expandi-lo.</span><span class="sxs-lookup"><span data-stu-id="df0ce-321">In the left navigation pane, select **Tenant Settings**  to expand it.</span></span>
1. <span data-ttu-id="df0ce-322">Em **Configurações do Locatário**, selecione **Configurações do B2C**.</span><span class="sxs-lookup"><span data-stu-id="df0ce-322">Under **Tenant Settings**, select **B2C Settings**.</span></span> 
1. <span data-ttu-id="df0ce-323">Na janela principal ao lado de **Aplicativos B2C**, selecione **Gerenciar**.</span><span class="sxs-lookup"><span data-stu-id="df0ce-323">In the main window next **B2C Applications**, select **Manage**.</span></span> <span data-ttu-id="df0ce-324">(Se o locatário aparecer na lista de Aplicativos B2C, ele já foi adicionado por um administrador.</span><span class="sxs-lookup"><span data-stu-id="df0ce-324">(If your tenant appears in the B2C Applications list, then it was already added by an administrator.</span></span> <span data-ttu-id="df0ce-325">Verifique se os itens na etapa 6 abaixo correspondem ao Aplicativo B2C.)</span><span class="sxs-lookup"><span data-stu-id="df0ce-325">Verify that the items in step 6 below match your B2C Application.)</span></span>
1. <span data-ttu-id="df0ce-326">Selecione **Adicionar Aplicativo B2C**.</span><span class="sxs-lookup"><span data-stu-id="df0ce-326">Select **Add B2C Application**.</span></span>
1. <span data-ttu-id="df0ce-327">Insira os seguintes itens obrigatórios no formulário exibido usando valores do locatário e aplicativo B2C.</span><span class="sxs-lookup"><span data-stu-id="df0ce-327">Enter the following required items in the form displayed, using values from your B2C tenant and application.</span></span> <span data-ttu-id="df0ce-328">Os campos que não são obrigatórios (sem um asterisco) podem ser deixados em branco.</span><span class="sxs-lookup"><span data-stu-id="df0ce-328">Fields that are not required (those without an asterisk) may be left blank.</span></span>

    - <span data-ttu-id="df0ce-329">**Nome do Aplicativo**: O nome do Aplicativo B2C, por exemplo, "Fabrikam B2C".</span><span class="sxs-lookup"><span data-stu-id="df0ce-329">**Application Name**: The name for your B2C Application, for example "Fabrikam B2C".</span></span>
    - <span data-ttu-id="df0ce-330">**Nome do Locatário**: O nome do Locatário B2C, por exemplo, "Fabrikam".</span><span class="sxs-lookup"><span data-stu-id="df0ce-330">**Tenant Name**: The name of your B2C Tenant, for example "Fabrikam".</span></span>
    - <span data-ttu-id="df0ce-331">**ID da Política de Esquecer Senha**: A ID da política de fluxo de usuário de esquecer senha, por exemplo, "B2C_1_PasswordReset".</span><span class="sxs-lookup"><span data-stu-id="df0ce-331">**Forget Password Policy ID**: The forget password user flow policy ID, for example "B2C_1_PasswordReset".</span></span>
    - <span data-ttu-id="df0ce-332">**ID da Política de Inscrição e Logon**: A ID da política do fluxo de usuário de inscrição e logon, por exemplo "B2C_1_signup_signin".</span><span class="sxs-lookup"><span data-stu-id="df0ce-332">**Signup Signin Policy ID**: The sign up and sign in user flow policy ID, for example "B2C_1_signup_signin".</span></span>
    - <span data-ttu-id="df0ce-333">**GUID do Cliente**: A ID do aplicativo B2C, por exemplo "22290eb2-c52e-42e9-8b35-a2b0a3bcb9e6".</span><span class="sxs-lookup"><span data-stu-id="df0ce-333">**Client GUID**: The B2C application ID, for example "22290eb2-c52e-42e9-8b35-a2b0a3bcb9e6".</span></span>
    - <span data-ttu-id="df0ce-334">**ID da Política de Editar Perfil**: A ID da política do fluxo de usuário de edição de perfil, por exemplo "B2C_1A_ProfileEdit".</span><span class="sxs-lookup"><span data-stu-id="df0ce-334">**Edit Profile Policy ID**: The profile editing user flow policy ID, for example "B2C_1A_ProfileEdit".</span></span>

1. <span data-ttu-id="df0ce-335">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="df0ce-335">Select **OK**.</span></span> <span data-ttu-id="df0ce-336">Agora você verá o nome do aplicativo B2C aparecer na lista.</span><span class="sxs-lookup"><span data-stu-id="df0ce-336">You should now see the name of your B2C application appear in the list.</span></span>

### <a name="associate-the-b2c-application-to-your-site-and-channel"></a><span data-ttu-id="df0ce-337">Associar o aplicativo B2C ao site e ao canal</span><span class="sxs-lookup"><span data-stu-id="df0ce-337">Associate the B2C application to your site and channel</span></span>

> [!WARNING]
> <span data-ttu-id="df0ce-338">Se o site já estiver associado a um aplicativo B2C, alterar para outro aplicativo B2C removerá as referências atuais estabelecidas para usuários já inscritos neste ambiente.</span><span class="sxs-lookup"><span data-stu-id="df0ce-338">If your site is already associated with a B2C application, changing to a different B2C application will remove the current references established for users already signed up in this environment.</span></span> <span data-ttu-id="df0ce-339">Se for alterado, todas as credenciais associadas ao aplicativo B2C atualmente atribuído não estarão disponíveis para os usuários.</span><span class="sxs-lookup"><span data-stu-id="df0ce-339">If changed, any credentials associated with the currently-assigned B2C application will not be available to users.</span></span> 
> 
> <span data-ttu-id="df0ce-340">Somente atualize o aplicativo B2C se estiver configurando o aplicativo B2C do canal pela primeira vez ou se quiser que os usuários se inscrevam novamente com novas credenciais neste canal com o novo aplicativo do B2C.</span><span class="sxs-lookup"><span data-stu-id="df0ce-340">Only update the B2C application if you are setting up the channel's B2C application for the first time or if you intend to have users re-sign up with new credentials to this channel with the new B2C application.</span></span> <span data-ttu-id="df0ce-341">Tenha cautela ao associar canais aos aplicativos B2C e nomeie os aplicativos de forma clara.</span><span class="sxs-lookup"><span data-stu-id="df0ce-341">Take caution when associating channels to B2C applications, and name applications clearly.</span></span> <span data-ttu-id="df0ce-342">Se um canal não estiver associado a um aplicativo B2C nas etapas abaixo, os usuários que fizerem logon nesse canal para o seu site serão inseridos no aplicativo B2C exibido como **padrão** na lista **Configurações do Locatário \> Configurações do B2C** de aplicativos B2C.</span><span class="sxs-lookup"><span data-stu-id="df0ce-342">If a channel is not associated to a B2C application in the steps below, users signing into that channel for your site will be entered into the B2C application showing as **default** in the **Tenant Settings \> B2C Settings** list of B2C applications.</span></span>

<span data-ttu-id="df0ce-343">Para associar o aplicativo B2C ao site e ao canal, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="df0ce-343">To associate the B2C application to your site and channel, follow these steps.</span></span>

1. <span data-ttu-id="df0ce-344">Navegue até o seu site no construtor de sites do Commerce.</span><span class="sxs-lookup"><span data-stu-id="df0ce-344">Navigate to your site in Commerce site builder.</span></span>
1. <span data-ttu-id="df0ce-345">No painel de navegação esquerdo, selecione **Configurações de Site** para expandi-lo.</span><span class="sxs-lookup"><span data-stu-id="df0ce-345">In the left navigation pane, select **Site Settings** to expand it.</span></span>
1. <span data-ttu-id="df0ce-346">Abaixo de **Configurações do Site**, selecione **Canais**.</span><span class="sxs-lookup"><span data-stu-id="df0ce-346">Below **Site Settings**, select **Channels**.</span></span>
1. <span data-ttu-id="df0ce-347">Na janela principal em **Canais**, selecione o seu canal.</span><span class="sxs-lookup"><span data-stu-id="df0ce-347">In the main window under **Channels**, select your channel.</span></span>
1. <span data-ttu-id="df0ce-348">No painel de propriedades do canal à direita, selecione o nome do aplicativo B2C no menu suspenso **Selecionar Aplicativo B2C**.</span><span class="sxs-lookup"><span data-stu-id="df0ce-348">In the channel properties pane on the right, select your B2C application name from the **Select B2C Application** drop down menu.</span></span>
1. <span data-ttu-id="df0ce-349">Selecione **Fechar** e, depois, selecione **Salvar e Publicar**.</span><span class="sxs-lookup"><span data-stu-id="df0ce-349">Select **Close**, and then select **Save and Publish**.</span></span>

## <a name="additional-b2c-information"></a><span data-ttu-id="df0ce-350">Informações adicionais do B2C</span><span class="sxs-lookup"><span data-stu-id="df0ce-350">Additional B2C information</span></span>

### <a name="customer-migration"></a><span data-ttu-id="df0ce-351">Migração de clientes</span><span class="sxs-lookup"><span data-stu-id="df0ce-351">Customer migration</span></span>

<span data-ttu-id="df0ce-352">Se você estiver considerando migrar registros de clientes de uma plataforma de provedor de identidade anterior, trabalhe em conjunto com a equipe do Dynamics 365 Commerce para revisar as suas necessidades de migração de clientes.</span><span class="sxs-lookup"><span data-stu-id="df0ce-352">If you are considering migrating customer records from a previous identity provider platform, please work with the Dynamics 365 Commerce team to review your customer migration needs.</span></span>

<span data-ttu-id="df0ce-353">Para obter documentação adicional do B2C do Azure AD sobre migração de clientes, consulte [Migrar usuários para o B2C do Azure Active Directory](https://docs.microsoft.com/azure/active-directory-b2c/active-directory-b2c-user-migration).</span><span class="sxs-lookup"><span data-stu-id="df0ce-353">For additional Azure AD B2C documentation on customer migration, see [Migrate users to Azure Active Directory B2C](https://docs.microsoft.com/azure/active-directory-b2c/active-directory-b2c-user-migration).</span></span>

### <a name="custom-policies"></a><span data-ttu-id="df0ce-354">Políticas personalizadas</span><span class="sxs-lookup"><span data-stu-id="df0ce-354">Custom policies</span></span>

<span data-ttu-id="df0ce-355">Para obter informações adicionais sobre como personalizar fluxos de interações e políticas do B2C do Azure AD fora do escopo oferecido por políticas padrão do B2C, consulte [Políticas personalizadas no B2C do Azure Active Directory](https://docs.microsoft.com/azure/active-directory-b2c/active-directory-b2c-overview-custom).</span><span class="sxs-lookup"><span data-stu-id="df0ce-355">For additional information regarding customizing Azure AD B2C interactions and policy flows beyond what is offered by B2C standard policies, see [Custom policies in Azure Active Directory B2C](https://docs.microsoft.com/azure/active-directory-b2c/active-directory-b2c-overview-custom).</span></span> 

### <a name="secondary-admin"></a><span data-ttu-id="df0ce-356">Administrador secundário</span><span class="sxs-lookup"><span data-stu-id="df0ce-356">Secondary admin</span></span>

<span data-ttu-id="df0ce-357">Uma conta de administrador ideal secundária pode ser adicionada à seção **Usuários** do locatário B2C.</span><span class="sxs-lookup"><span data-stu-id="df0ce-357">An optional, secondary administrator account can be added in the **Users** section of your B2C tenant.</span></span> <span data-ttu-id="df0ce-358">Pode ser uma conta direta ou uma conta geral.</span><span class="sxs-lookup"><span data-stu-id="df0ce-358">This can be a direct account or a general account.</span></span> <span data-ttu-id="df0ce-359">Caso precise compartilhar uma conta entre os recursos da equipe, uma conta comum também poderá ser criada.</span><span class="sxs-lookup"><span data-stu-id="df0ce-359">If you need to share an account across team resources, a common account can also be created.</span></span> <span data-ttu-id="df0ce-360">Devido à confidencialidade dos dados armazenados no B2C do Azure AD, uma conta comum deverá ser monitorada rigorosamente de acordo com as práticas de segurança da empresa.</span><span class="sxs-lookup"><span data-stu-id="df0ce-360">Due to the sensitivity of the data stored in Azure AD B2C, a common account should be monitored closely per your company's security practices.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="df0ce-361">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="df0ce-361">Additional resources</span></span>

[<span data-ttu-id="df0ce-362">Configurar seu nome de domínio</span><span class="sxs-lookup"><span data-stu-id="df0ce-362">Configure your domain name</span></span>](configure-your-domain-name.md)

[<span data-ttu-id="df0ce-363">Implantar um novo site de comércio eletrônico</span><span class="sxs-lookup"><span data-stu-id="df0ce-363">Deploy a new e-Commerce site</span></span>](deploy-ecommerce-site.md)

[<span data-ttu-id="df0ce-364">Criar um site de comércio eletrônico</span><span class="sxs-lookup"><span data-stu-id="df0ce-364">Create an e-Commerce site</span></span>](create-ecommerce-site.md)

[<span data-ttu-id="df0ce-365">Associar um site online a um canal</span><span class="sxs-lookup"><span data-stu-id="df0ce-365">Associate an online site with a channel</span></span>](associate-site-online-store.md)

[<span data-ttu-id="df0ce-366">Gerenciar arquivos robots.txt</span><span class="sxs-lookup"><span data-stu-id="df0ce-366">Manage robots.txt files</span></span>](manage-robots-txt-files.md)

[<span data-ttu-id="df0ce-367">Carregar redirecionamentos de URL em massa</span><span class="sxs-lookup"><span data-stu-id="df0ce-367">Upload URL redirects in bulk</span></span>](upload-bulk-redirects.md)

[<span data-ttu-id="df0ce-368">Configurar páginas personalizadas para logons dos usuários</span><span class="sxs-lookup"><span data-stu-id="df0ce-368">Set up custom pages for user logins</span></span>](custom-pages-user-logins.md)

[<span data-ttu-id="df0ce-369">Configurar múltiplos locatários B2C em um ambiente do Commerce</span><span class="sxs-lookup"><span data-stu-id="df0ce-369">Configure multiple B2C tenants in a Commerce environment</span></span>](configure-multi-B2C-tenants.md)

[<span data-ttu-id="df0ce-370">Adicionar suporte para uma rede de entrega de conteúdo (CDN)</span><span class="sxs-lookup"><span data-stu-id="df0ce-370">Add support for a content delivery network (CDN)</span></span>](add-cdn-support.md)

[<span data-ttu-id="df0ce-371">Habilitar detecção de lojas com base na localização</span><span class="sxs-lookup"><span data-stu-id="df0ce-371">Enable location-based store detection</span></span>](enable-store-detection.md)
