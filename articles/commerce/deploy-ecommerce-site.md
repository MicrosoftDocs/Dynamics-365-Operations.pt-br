---
title: Implantar um novo locatário de comércio eletrônico
description: Este tópico descreve como implantar um novo site de comércio eletrônico do Dynamics 365 Commerce usando o Microsoft Dynamics Lifecycle Services (LCS).
author: psimolin
ms.date: 07/02/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 0fff5d47d6eb3e08288d17853fcd94f9eab843c3
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5801940"
---
# <a name="deploy-a-new-e-commerce-tenant"></a><span data-ttu-id="b4cdd-103">Implantar um novo locatário de comércio eletrônico</span><span class="sxs-lookup"><span data-stu-id="b4cdd-103">Deploy a new e-commerce tenant</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="b4cdd-104">Este tópico descreve como implantar um novo site de comércio eletrônico do Dynamics 365 Commerce usando o Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="b4cdd-104">This topic describes how to deploy a new Dynamics 365 Commerce e-commerce site by using Microsoft Dynamics Lifecycle Services (LCS).</span></span>

<span data-ttu-id="b4cdd-105">Microsoft Dynamics Lifecycle Services (LCS) é um espaço de trabalho colaborativo baseado em nuvem que parceiros e clientes podem usar para gerenciar seus produtos e ambientes, exibir as informações mais recentes de produtos e serviços do Microsoft Dynamics, e criar, rastrear e navegar em incidentes de suporte.</span><span class="sxs-lookup"><span data-stu-id="b4cdd-105">Microsoft Dynamics Lifecycle Services (LCS) is a cloud-based collaborative workspace that partners and customers can use to manage their projects and environments, view the latest information about Microsoft Dynamics products and features, and create, track, and browse support incidents.</span></span> <span data-ttu-id="b4cdd-106">Os recursos de gerenciamento de comércio eletrônico são integrados no LCS.</span><span class="sxs-lookup"><span data-stu-id="b4cdd-106">E-commerce management features are integrated into LCS.</span></span>

<span data-ttu-id="b4cdd-107">Para saber mais sobre LCS, consulte [Guia do usuário do Lifecycle Services](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/lifecycle-services/lcs-user-guide).</span><span class="sxs-lookup"><span data-stu-id="b4cdd-107">To learn more about LCS, see the [Lifecycle Services User Guide](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/lifecycle-services/lcs-user-guide).</span></span>
    
## <a name="get-started"></a><span data-ttu-id="b4cdd-108">Iniciado</span><span class="sxs-lookup"><span data-stu-id="b4cdd-108">Get started</span></span>

<span data-ttu-id="b4cdd-109">Antes de iniciar o comércio eletrônico, inicialize um projeto, um ambiente e um Retail Cloud Scale Unit (RCSU).</span><span class="sxs-lookup"><span data-stu-id="b4cdd-109">Before you can initialize e-commerce, you must initialize a project, an environment, and a Retail Cloud Scale Unit (RCSU).</span></span> <span data-ttu-id="b4cdd-110">Para realizar a inicialização em LCS, você deve ter permissões para a função do gerente Proprietário do Projeto ou de Ambiente.</span><span class="sxs-lookup"><span data-stu-id="b4cdd-110">To do the initialization in LCS, you must have permissions for either the Project Owner or Environment manager role.</span></span> <span data-ttu-id="b4cdd-111">As topologias de produção e do ambiente do sandbox são suportadas.</span><span class="sxs-lookup"><span data-stu-id="b4cdd-111">The production and sandbox environment topologies are supported.</span></span>

<span data-ttu-id="b4cdd-112">Para obter mais informações sobre os ambientes, consulte [Planejamento de ambiente](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/imp-lifecycle/environment-planning).</span><span class="sxs-lookup"><span data-stu-id="b4cdd-112">For more information about environments, see [Environment planning](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/imp-lifecycle/environment-planning).</span></span> <span data-ttu-id="b4cdd-113">Para obter mais informações sobre RCSU, consulte [Inicializar Retail Cloud Scale Unit](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/deployment/initialize-retail-channels).</span><span class="sxs-lookup"><span data-stu-id="b4cdd-113">For more information about RCSU, see [Initialize Retail Cloud Scale Unit](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/deployment/initialize-retail-channels).</span></span>

## <a name="initialize-e-commerce"></a><span data-ttu-id="b4cdd-114">Inicializar comércio eletrônico</span><span class="sxs-lookup"><span data-stu-id="b4cdd-114">Initialize e-commerce</span></span>

<span data-ttu-id="b4cdd-115">Use este procedimento para inicializar o recurso de comércio eletrônico em um ambiente existente.</span><span class="sxs-lookup"><span data-stu-id="b4cdd-115">Use this procedure to initialize the e-commerce feature in an existing environment.</span></span>

<span data-ttu-id="b4cdd-116">Antes de começar, verifique se você tem as seguintes informações necessárias:</span><span class="sxs-lookup"><span data-stu-id="b4cdd-116">Before you begin, make sure that you have the following required information:</span></span>

- <span data-ttu-id="b4cdd-117">O RCSU que será usado.</span><span class="sxs-lookup"><span data-stu-id="b4cdd-117">The RCSU that will be used.</span></span>
- <span data-ttu-id="b4cdd-118">O grupo de segurança do Microsoft Azure Active Directory que será usado para administradores de sistemas de comércio eletrônico.</span><span class="sxs-lookup"><span data-stu-id="b4cdd-118">The Microsoft Azure Active Directory security group that will be used for e-commerce system admins.</span></span>
- <span data-ttu-id="b4cdd-119">O grupo de segurança do Microsoft Azure Active Directory que será usado para moderadores de avaliações e opiniões.</span><span class="sxs-lookup"><span data-stu-id="b4cdd-119">The Microsoft Azure Active Directory security group that will be used for ratings and reviews moderators.</span></span>
- <span data-ttu-id="b4cdd-120">Os domínios que serão associados com o ambiente.</span><span class="sxs-lookup"><span data-stu-id="b4cdd-120">The domains that will be associated with the environment.</span></span>

<span data-ttu-id="b4cdd-121">Além disso, você pode coletar as seguintes informações opcionais:</span><span class="sxs-lookup"><span data-stu-id="b4cdd-121">In addition, you can collect the following optional information:</span></span>

- <span data-ttu-id="b4cdd-122">Informações de business-to-consumer (B2C) do Azure AD:</span><span class="sxs-lookup"><span data-stu-id="b4cdd-122">Azure AD business-to-consumer (B2C) information:</span></span>

    - <span data-ttu-id="b4cdd-123">Nome do locatário.</span><span class="sxs-lookup"><span data-stu-id="b4cdd-123">Tenant Name.</span></span>
    - <span data-ttu-id="b4cdd-124">ID do Cliente.</span><span class="sxs-lookup"><span data-stu-id="b4cdd-124">Client ID.</span></span>
    - <span data-ttu-id="b4cdd-125">Domínio Personalizado de Logon.</span><span class="sxs-lookup"><span data-stu-id="b4cdd-125">Login Custom Domain.</span></span>
    - <span data-ttu-id="b4cdd-126">Resposta de URL.</span><span class="sxs-lookup"><span data-stu-id="b4cdd-126">Reply URL.</span></span>
    - <span data-ttu-id="b4cdd-127">ID da Política de Entrada da Inscrição.</span><span class="sxs-lookup"><span data-stu-id="b4cdd-127">SignUp SignIn Policy ID.</span></span>
    - <span data-ttu-id="b4cdd-128">ID da política de senha de redefinição.</span><span class="sxs-lookup"><span data-stu-id="b4cdd-128">Reset password Policy ID.</span></span>
    - <span data-ttu-id="b4cdd-129">Editar ID da Política de Perfil.</span><span class="sxs-lookup"><span data-stu-id="b4cdd-129">Edit Profile Policy ID.</span></span>

> [!NOTE]
> <span data-ttu-id="b4cdd-130">Essas informações podem ser adicionadas posteriormente, com uma solicitação de serviço.</span><span class="sxs-lookup"><span data-stu-id="b4cdd-130">This information can be added later, through a service request.</span></span>

<span data-ttu-id="b4cdd-131">Após coletar as informações obrigatórias, siga estas etapas para inicializar o comércio eletrônico.</span><span class="sxs-lookup"><span data-stu-id="b4cdd-131">After you've collected the required information, follow these steps to initialize e-commerce.</span></span>

1. <span data-ttu-id="b4cdd-132">Entre no [LCS](https://lcs.dynamics.com).</span><span class="sxs-lookup"><span data-stu-id="b4cdd-132">Sign in to [LCS](https://lcs.dynamics.com).</span></span>
1. <span data-ttu-id="b4cdd-133">Abra o projeto que contém o ambiente em que você deseja inicializar o comércio eletrônico.</span><span class="sxs-lookup"><span data-stu-id="b4cdd-133">Open the project that contains the environment where you want to initialize e-commerce.</span></span>
1. <span data-ttu-id="b4cdd-134">Na seção **Ambientes**, selecione o ambiente.</span><span class="sxs-lookup"><span data-stu-id="b4cdd-134">In the **Environments** section, select the environment.</span></span>
1. <span data-ttu-id="b4cdd-135">Em **Recursos de ambiente**, selecione o link **Gerente de retail**.</span><span class="sxs-lookup"><span data-stu-id="b4cdd-135">Under **Environment features**, select the **Retail manage** link.</span></span>
1. <span data-ttu-id="b4cdd-136">Na guia **Comércio eletrônico**, selecione **Configuração**.</span><span class="sxs-lookup"><span data-stu-id="b4cdd-136">On the **e-Commerce** tab, select **Setup**.</span></span> <span data-ttu-id="b4cdd-137">É exibida uma caixa de diálogo, onde você pode inserir as informações que são necessárias para provisionamento.</span><span class="sxs-lookup"><span data-stu-id="b4cdd-137">A dialog box appears, where you must enter the information that is required for provisioning.</span></span>
1. <span data-ttu-id="b4cdd-138">Preencha as informações necessárias, e vá para a próxima página.</span><span class="sxs-lookup"><span data-stu-id="b4cdd-138">Fill in the required information, and then go to the next page.</span></span>
1. <span data-ttu-id="b4cdd-139">Na página a seguir, preencha as informações necessárias e depois envie o formulário.</span><span class="sxs-lookup"><span data-stu-id="b4cdd-139">On the next page, fill in the required information, and then submit the form.</span></span> <span data-ttu-id="b4cdd-140">Você volta para a guia **Comércio online**, onde você pode ver que a inicialização foi iniciada.</span><span class="sxs-lookup"><span data-stu-id="b4cdd-140">You're returned to the **e-Commerce** tab, where you should see that initialization has been started.</span></span>
1. <span data-ttu-id="b4cdd-141">Para exibir o status de inicialização, **Atualize** ou retorne para a guia **Comércio online** posteriormente.</span><span class="sxs-lookup"><span data-stu-id="b4cdd-141">To view the initialization status, either **Refresh** or return to the **e-Commerce** tab later.</span></span>
    
<span data-ttu-id="b4cdd-142">Quando o comércio eletrônico é inicializado do LCS, o sistema provisiona vários componentes necessários para o comércio eletrônico e os associa ao ambiente.</span><span class="sxs-lookup"><span data-stu-id="b4cdd-142">When e-commerce is initialized from LCS, the system provisions several components that are required for e-commerce and associates them with the environment.</span></span> <span data-ttu-id="b4cdd-143">Depois que o provisionamento é concluído, a guia **Comércio eletrônico** na página **Gerenciamento de varejo** é atualizada para refletir o provisionamento.</span><span class="sxs-lookup"><span data-stu-id="b4cdd-143">After provisioning is complete, the **e-Commerce** tab on the **Retail management** page is updated to reflect the provisioning.</span></span> <span data-ttu-id="b4cdd-144">A página mostra as últimas implantações de personalização e o status de quaisquer outras implantações em andamento.</span><span class="sxs-lookup"><span data-stu-id="b4cdd-144">The page shows the latest customization deployments and the status of any other ongoing deployments.</span></span> <span data-ttu-id="b4cdd-145">Ela também inclui links para o site de comércio eletrônico e o assistente para criação de sites de comércio eletrônico, onde os sites são criados.</span><span class="sxs-lookup"><span data-stu-id="b4cdd-145">It also includes links to the e-commerce site and the Commerce site builder where sites are authored.</span></span>

## <a name="access-commerce-site-builder"></a><span data-ttu-id="b4cdd-146">Acessar o assistente para criação de sites do Commerce</span><span class="sxs-lookup"><span data-stu-id="b4cdd-146">Access Commerce site builder</span></span>

<span data-ttu-id="b4cdd-147">Para acessar o assistente para criação de sites do Commerce, vá para a guia **Comércio eletrônico** na página **Gerenciamento de varejo** no LCS e selecione o link **Ferramenta de gerenciamento de site de comércio eletrônico**.</span><span class="sxs-lookup"><span data-stu-id="b4cdd-147">To access Commerce site builder, go to the **e-Commerce** tab on the **Retail management** page in LCS and select the **e-Commerce site management tool** link.</span></span> <span data-ttu-id="b4cdd-148">A página de aterrissagem do assistente para criação de sites mostra uma exibição no nível de locatário.</span><span class="sxs-lookup"><span data-stu-id="b4cdd-148">The site builder landing page displays a tenant-level view.</span></span> <span data-ttu-id="b4cdd-149">Nesta página, você pode:</span><span class="sxs-lookup"><span data-stu-id="b4cdd-149">From this page, you can:</span></span>

- <span data-ttu-id="b4cdd-150">Modifique configurações no nível de locatário.</span><span class="sxs-lookup"><span data-stu-id="b4cdd-150">Modify tenant-level settings.</span></span>
- <span data-ttu-id="b4cdd-151">Navegar para qualquer site que você criou e tem permissão para exibir.</span><span class="sxs-lookup"><span data-stu-id="b4cdd-151">Navigate to any site you have created, and have permission to view.</span></span> 
- <span data-ttu-id="b4cdd-152">Acessar recursos de Revisões, como relatórios e moderação.</span><span class="sxs-lookup"><span data-stu-id="b4cdd-152">Access Reviews features such as moderation and reporting.</span></span>
- <span data-ttu-id="b4cdd-153">Criar um novo site.</span><span class="sxs-lookup"><span data-stu-id="b4cdd-153">Create a new site.</span></span> <span data-ttu-id="b4cdd-154">Para obter mais informações sobre como criar um novo site, consulte [Criar um site de comércio eletrônico](create-ecommerce-site.md).</span><span class="sxs-lookup"><span data-stu-id="b4cdd-154">For more information about how to create a new site, see [Create an e-commerce site](create-ecommerce-site.md) .</span></span> 

## <a name="additional-resources"></a><span data-ttu-id="b4cdd-155">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="b4cdd-155">Additional resources</span></span>

[<span data-ttu-id="b4cdd-156">Configurar seu nome de domínio</span><span class="sxs-lookup"><span data-stu-id="b4cdd-156">Configure your domain name</span></span>](configure-your-domain-name.md)

[<span data-ttu-id="b4cdd-157">Criar um site de comércio eletrônico</span><span class="sxs-lookup"><span data-stu-id="b4cdd-157">Create an e-commerce site</span></span>](create-ecommerce-site.md)

[<span data-ttu-id="b4cdd-158">Associar um site do Dynamics 365 Commerce a um canal online</span><span class="sxs-lookup"><span data-stu-id="b4cdd-158">Associate a Dynamics 365 Commerce site with an online channel</span></span>](associate-site-online-store.md)

[<span data-ttu-id="b4cdd-159">Gerenciar arquivos robots.txt</span><span class="sxs-lookup"><span data-stu-id="b4cdd-159">Manage robots.txt files</span></span>](manage-robots-txt-files.md)

[<span data-ttu-id="b4cdd-160">Carregar redirecionamentos de URL em massa</span><span class="sxs-lookup"><span data-stu-id="b4cdd-160">Upload URL redirects in bulk</span></span>](upload-bulk-redirects.md)

[<span data-ttu-id="b4cdd-161">Configurar um locatário B2C do Commerce</span><span class="sxs-lookup"><span data-stu-id="b4cdd-161">Set up a B2C tenant in Commerce</span></span>](set-up-B2C-tenant.md)

[<span data-ttu-id="b4cdd-162">Configurar páginas personalizadas para logons dos usuários</span><span class="sxs-lookup"><span data-stu-id="b4cdd-162">Set up custom pages for user logins</span></span>](custom-pages-user-logins.md)

[<span data-ttu-id="b4cdd-163">Configurar múltiplos locatários B2C em um ambiente do Commerce</span><span class="sxs-lookup"><span data-stu-id="b4cdd-163">Configure multiple B2C tenants in a Commerce environment</span></span>](configure-multi-B2C-tenants.md)

[<span data-ttu-id="b4cdd-164">Adicionar suporte para uma rede de entrega de conteúdo (CDN)</span><span class="sxs-lookup"><span data-stu-id="b4cdd-164">Add support for a content delivery network (CDN)</span></span>](add-cdn-support.md)

[<span data-ttu-id="b4cdd-165">Habilitar detecção de lojas com base na localização</span><span class="sxs-lookup"><span data-stu-id="b4cdd-165">Enable location-based store detection</span></span>](enable-store-detection.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
