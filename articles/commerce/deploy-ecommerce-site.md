---
title: Implantar um novo locatário de comércio eletrônico
description: Este tópico descreve como implantar um novo locatário de comércio eletrônico usando Microsoft Dynamics Lifecycle Services (LCS).
author: psimolin
manager: annbe
ms.date: 03/02/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: d5cf2804c44e81ad135a3248d38c228148b530cc
ms.sourcegitcommit: 567132f4e4f7a1d76dccf762068209a42c788b52
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/03/2020
ms.locfileid: "3096669"
---
# <a name="deploy-a-new-e-commerce-tenant"></a><span data-ttu-id="e2d82-103">Implantar um novo locatário de comércio eletrônico</span><span class="sxs-lookup"><span data-stu-id="e2d82-103">Deploy a new e-Commerce tenant</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="e2d82-104">Este tópico descreve como implantar um novo site de comércio eletrônico usando Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="e2d82-104">This topic describes how to deploy a new e-Commerce site by using Microsoft Dynamics Lifecycle Services (LCS).</span></span>

## <a name="overview"></a><span data-ttu-id="e2d82-105">Visão geral</span><span class="sxs-lookup"><span data-stu-id="e2d82-105">Overview</span></span>

<span data-ttu-id="e2d82-106">Microsoft Dynamics Lifecycle Services (LCS) é um espaço de trabalho colaborativo baseado em nuvem que parceiros e clientes podem usar para gerenciar seus produtos e ambientes, exibir as informações mais recentes de produtos e serviços do Microsoft Dynamics, e criar, rastrear e navegar em incidentes de suporte.</span><span class="sxs-lookup"><span data-stu-id="e2d82-106">Microsoft Dynamics Lifecycle Services (LCS) is a cloud-based collaborative workspace that partners and customers can use to manage their projects and environments, view the latest information about Microsoft Dynamics products and features, and create, track, and browse support incidents.</span></span> <span data-ttu-id="e2d82-107">Os recursos de gerenciamento de comércio online são integrados no LCS.</span><span class="sxs-lookup"><span data-stu-id="e2d82-107">E-Commerce management features are integrated into LCS.</span></span>

<span data-ttu-id="e2d82-108">Para saber mais sobre LCS, consulte [Guia do usuário do Lifecycle Services](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/lifecycle-services/lcs-user-guide).</span><span class="sxs-lookup"><span data-stu-id="e2d82-108">To learn more about LCS, see the [Lifecycle Services User Guide](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/lifecycle-services/lcs-user-guide).</span></span>
    
## <a name="get-started"></a><span data-ttu-id="e2d82-109">Comece a usar</span><span class="sxs-lookup"><span data-stu-id="e2d82-109">Get started</span></span>

<span data-ttu-id="e2d82-110">Antes de poder iniciar o comércio online, você deve inicializar um projeto, um ambiente e um Retail Cloud Scale Unit (RCSU).</span><span class="sxs-lookup"><span data-stu-id="e2d82-110">Before you can initialize e-Commerce, you must initialize a project, an environment, and a Retail Cloud Scale Unit (RCSU).</span></span> <span data-ttu-id="e2d82-111">Para realizar a inicialização em LCS, você deve ter permissões para a função do gerente Proprietário do Projeto ou de Ambiente.</span><span class="sxs-lookup"><span data-stu-id="e2d82-111">To do the initialization in LCS, you must have permissions for either the Project Owner or Environment manager role.</span></span> <span data-ttu-id="e2d82-112">As topologias de produção e do ambiente do sandbox são suportadas.</span><span class="sxs-lookup"><span data-stu-id="e2d82-112">The production and sandbox environment topologies are supported.</span></span>

<span data-ttu-id="e2d82-113">Para obter mais informações sobre os ambientes, consulte [Planejamento de ambiente](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/imp-lifecycle/environment-planning).</span><span class="sxs-lookup"><span data-stu-id="e2d82-113">For more information about environments, see [Environment planning](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/imp-lifecycle/environment-planning).</span></span> <span data-ttu-id="e2d82-114">Para obter mais informações sobre RCSU, consulte [Inicializar Retail Cloud Scale Unit](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/deployment/initialize-retail-channels).</span><span class="sxs-lookup"><span data-stu-id="e2d82-114">For more information about RCSU, see [Initialize Retail Cloud Scale Unit](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/deployment/initialize-retail-channels).</span></span>

## <a name="initialize-e-commerce"></a><span data-ttu-id="e2d82-115">Inicializar comércio eletrônico</span><span class="sxs-lookup"><span data-stu-id="e2d82-115">Initialize e-Commerce</span></span>

<span data-ttu-id="e2d82-116">Use este procedimento para inicializar o recurso de comércio online em um ambiente existente.</span><span class="sxs-lookup"><span data-stu-id="e2d82-116">Use this procedure to initialize the e-Commerce feature in an existing environment.</span></span>

<span data-ttu-id="e2d82-117">Antes de começar, verifique se você tem as seguintes informações necessárias:</span><span class="sxs-lookup"><span data-stu-id="e2d82-117">Before you begin, make sure that you have the following required information:</span></span>

- <span data-ttu-id="e2d82-118">O RCSU que será usado.</span><span class="sxs-lookup"><span data-stu-id="e2d82-118">The RCSU that will be used.</span></span>
- <span data-ttu-id="e2d82-119">O grupo de segurança do Microsoft Azure Active Directory que será usado para administradores de sistemas de eletrônicos online.</span><span class="sxs-lookup"><span data-stu-id="e2d82-119">The Microsoft Azure Active Directory security group that will be used for e-Commerce system admins.</span></span>
- <span data-ttu-id="e2d82-120">O grupo de segurança do Microsoft Azure Active Directory que será usado para moderadores de avaliações e opiniões.</span><span class="sxs-lookup"><span data-stu-id="e2d82-120">The Microsoft Azure Active Directory security group that will be used for ratings and reviews moderators.</span></span>
- <span data-ttu-id="e2d82-121">Os domínios que serão associados com o ambiente.</span><span class="sxs-lookup"><span data-stu-id="e2d82-121">The domains that will be associated with the environment.</span></span>

<span data-ttu-id="e2d82-122">Além disso, você pode coletar as seguintes informações opcionais:</span><span class="sxs-lookup"><span data-stu-id="e2d82-122">In addition, you can collect the following optional information:</span></span>

- <span data-ttu-id="e2d82-123">Informações de business-to-consumer (B2C) do Azure AD:</span><span class="sxs-lookup"><span data-stu-id="e2d82-123">Azure AD business-to-consumer (B2C) information:</span></span>

    - <span data-ttu-id="e2d82-124">Nome do locatário.</span><span class="sxs-lookup"><span data-stu-id="e2d82-124">Tenant Name.</span></span>
    - <span data-ttu-id="e2d82-125">ID do Cliente.</span><span class="sxs-lookup"><span data-stu-id="e2d82-125">Client ID.</span></span>
    - <span data-ttu-id="e2d82-126">Domínio Personalizado de Logon.</span><span class="sxs-lookup"><span data-stu-id="e2d82-126">Login Custom Domain.</span></span>
    - <span data-ttu-id="e2d82-127">Resposta de URL.</span><span class="sxs-lookup"><span data-stu-id="e2d82-127">Reply URL.</span></span>
    - <span data-ttu-id="e2d82-128">ID da Política de Entrada da Inscrição.</span><span class="sxs-lookup"><span data-stu-id="e2d82-128">SignUp SignIn Policy ID.</span></span>
    - <span data-ttu-id="e2d82-129">ID da política de senha de redefinição.</span><span class="sxs-lookup"><span data-stu-id="e2d82-129">Reset password Policy ID.</span></span>
    - <span data-ttu-id="e2d82-130">Editar ID da Política de Perfil.</span><span class="sxs-lookup"><span data-stu-id="e2d82-130">Edit Profile Policy ID.</span></span>

[!NOTE]
<span data-ttu-id="e2d82-131">Essas informações podem ser adicionadas posteriormente, com uma solicitação de serviço.</span><span class="sxs-lookup"><span data-stu-id="e2d82-131">This information can be added later, through a service request.</span></span>

<span data-ttu-id="e2d82-132">Depois que coletou informações obrigatórias, siga essas etapas para inicializar o comércio online.</span><span class="sxs-lookup"><span data-stu-id="e2d82-132">After you've collected the required information, follow these steps to initialize e-Commerce.</span></span>

1. <span data-ttu-id="e2d82-133">Entre no [LCS](https://lcs.dynamics.com).</span><span class="sxs-lookup"><span data-stu-id="e2d82-133">Sign in to [LCS](https://lcs.dynamics.com).</span></span>
1. <span data-ttu-id="e2d82-134">Abra o projeto que contém o ambiente onde você deseja inicializar o comércio online.</span><span class="sxs-lookup"><span data-stu-id="e2d82-134">Open the project that contains the environment where you want to initialize e-Commerce.</span></span>
1. <span data-ttu-id="e2d82-135">Na seção **Ambientes**, selecione o ambiente.</span><span class="sxs-lookup"><span data-stu-id="e2d82-135">In the **Environments** section, select the environment.</span></span>
1. <span data-ttu-id="e2d82-136">Em **Recursos de ambiente**, selecione o link **Gerente de retail**.</span><span class="sxs-lookup"><span data-stu-id="e2d82-136">Under **Environment features**, select the **Retail manage** link.</span></span>
1. <span data-ttu-id="e2d82-137">Na guia **Comércio eletrônico**, selecione **Configuração**.</span><span class="sxs-lookup"><span data-stu-id="e2d82-137">On the **e-Commerce** tab, select **Setup**.</span></span> <span data-ttu-id="e2d82-138">É exibida uma caixa de diálogo, onde você pode inserir as informações que são necessárias para provisionamento.</span><span class="sxs-lookup"><span data-stu-id="e2d82-138">A dialog box appears, where you must enter the information that is required for provisioning.</span></span>
1. <span data-ttu-id="e2d82-139">Preencha as informações necessárias, e vá para a próxima página.</span><span class="sxs-lookup"><span data-stu-id="e2d82-139">Fill in the required information, and then go to the next page.</span></span>
1. <span data-ttu-id="e2d82-140">Na página a seguir, preencha as informações necessárias e depois envie o formulário.</span><span class="sxs-lookup"><span data-stu-id="e2d82-140">On the next page, fill in the required information, and then submit the form.</span></span> <span data-ttu-id="e2d82-141">Você volta para a guia **Comércio online**, onde você pode ver que a inicialização foi iniciada.</span><span class="sxs-lookup"><span data-stu-id="e2d82-141">You're returned to the **e-Commerce** tab, where you should see that initialization has been started.</span></span>
1. <span data-ttu-id="e2d82-142">Para exibir o status de inicialização, **Atualize** ou retorne para a guia **Comércio online** posteriormente.</span><span class="sxs-lookup"><span data-stu-id="e2d82-142">To view the initialization status, either **Refresh** or return to the **e-Commerce** tab later.</span></span>
    
<span data-ttu-id="e2d82-143">Quando o comércio online é inicializado do LCS, o sistema provisiona vários componentes necessários para o comércio online para associá-los ao ambiente.</span><span class="sxs-lookup"><span data-stu-id="e2d82-143">When e-Commerce is initialized from LCS, the system provisions several components that are required for e-Commerce and associates them with the environment.</span></span> <span data-ttu-id="e2d82-144">Depois que o provisionamento é concluído, a guia **Comércio eletrônico** na página **Gerenciamento de varejo** é atualizada para refletir o provisionamento.</span><span class="sxs-lookup"><span data-stu-id="e2d82-144">After provisioning is complete, the **e-Commerce** tab on the **Retail management** page is updated to reflect the provisioning.</span></span> <span data-ttu-id="e2d82-145">A página mostra as últimas implantações de personalização e o status de quaisquer outras implantações em andamento.</span><span class="sxs-lookup"><span data-stu-id="e2d82-145">The page shows the latest customization deployments and the status of any other ongoing deployments.</span></span> <span data-ttu-id="e2d82-146">Ela também inclui links para o site de comércio eletrônico e o assistente para criação de sites de comércio eletrônico, onde os sites são criados.</span><span class="sxs-lookup"><span data-stu-id="e2d82-146">It also includes links to the e-Commerce site and the e-Commerce site builder where sites are authored.</span></span>

## <a name="access-site-builder"></a><span data-ttu-id="e2d82-147">Acessar o assistente para criação de sites</span><span class="sxs-lookup"><span data-stu-id="e2d82-147">Access site builder</span></span>

<span data-ttu-id="e2d82-148">Para acessar o assistente para criação de sites, vá para a guia **Comércio eletrônico** na página **Gerenciamento de varejo** no LCS e selecione o link **Ferramenta de gerenciamento de site de comércio eletrônico**.</span><span class="sxs-lookup"><span data-stu-id="e2d82-148">To access site builder, go to the **e-Commerce** tab on the **Retail management** page in LCS and select the **e-Commerce site management tool** link.</span></span> <span data-ttu-id="e2d82-149">A página de aterrissagem do assistente para criação de sites mostra uma exibição no nível de locatário.</span><span class="sxs-lookup"><span data-stu-id="e2d82-149">The site builder landing page displays a tenant-level view.</span></span> <span data-ttu-id="e2d82-150">Nesta página, você pode:</span><span class="sxs-lookup"><span data-stu-id="e2d82-150">From this page, you can:</span></span>

- <span data-ttu-id="e2d82-151">Modifique configurações no nível de locatário.</span><span class="sxs-lookup"><span data-stu-id="e2d82-151">Modify tenant-level settings.</span></span>
- <span data-ttu-id="e2d82-152">Navegar para qualquer site que você criou e tem permissão para exibir.</span><span class="sxs-lookup"><span data-stu-id="e2d82-152">Navigate to any site you have created, and have permission to view.</span></span> 
- <span data-ttu-id="e2d82-153">Acessar recursos de Revisões, como relatórios e moderação.</span><span class="sxs-lookup"><span data-stu-id="e2d82-153">Access Reviews features such as moderation and reporting.</span></span>
- <span data-ttu-id="e2d82-154">Criar um novo site.</span><span class="sxs-lookup"><span data-stu-id="e2d82-154">Create a new site.</span></span> <span data-ttu-id="e2d82-155">Para obter mais informações sobre como criar um novo site, consulte [Criar um site de comércio eletrônico](create-ecommerce-site.md).</span><span class="sxs-lookup"><span data-stu-id="e2d82-155">For more information about how to create a new site, see [Create an e-Commerce site](create-ecommerce-site.md) .</span></span> 

## <a name="additional-resources"></a><span data-ttu-id="e2d82-156">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="e2d82-156">Additional resources</span></span>

[<span data-ttu-id="e2d82-157">Configurar seu nome de domínio</span><span class="sxs-lookup"><span data-stu-id="e2d82-157">Configure your domain name</span></span>](configure-your-domain-name.md)

[<span data-ttu-id="e2d82-158">Criar um site de comércio eletrônico</span><span class="sxs-lookup"><span data-stu-id="e2d82-158">Create an e-Commerce site</span></span>](create-ecommerce-site.md)

[<span data-ttu-id="e2d82-159">Configurar um canal da loja online</span><span class="sxs-lookup"><span data-stu-id="e2d82-159">Set up an online store channel</span></span>](online-stores.md)

[<span data-ttu-id="e2d82-160">Associar um site online a um canal</span><span class="sxs-lookup"><span data-stu-id="e2d82-160">Associate an online site with a channel</span></span>](associate-site-online-store.md)

[<span data-ttu-id="e2d82-161">Gerenciar arquivos robots.txt</span><span class="sxs-lookup"><span data-stu-id="e2d82-161">Manage robots.txt files</span></span>](manage-robots-txt-files.md)

[<span data-ttu-id="e2d82-162">Carregar redirecionamentos de URL em massa</span><span class="sxs-lookup"><span data-stu-id="e2d82-162">Upload URL redirects in bulk</span></span>](upload-bulk-redirects.md)

[<span data-ttu-id="e2d82-163">Configurar um locatário B2C do Commerce</span><span class="sxs-lookup"><span data-stu-id="e2d82-163">Set up a B2C tenant in Commerce</span></span>](set-up-B2C-tenant.md)

[<span data-ttu-id="e2d82-164">Configurar páginas personalizadas para logons dos usuários</span><span class="sxs-lookup"><span data-stu-id="e2d82-164">Set up custom pages for user logins</span></span>](custom-pages-user-logins.md)

[<span data-ttu-id="e2d82-165">Configurar múltiplos locatários B2C em um ambiente do Commerce</span><span class="sxs-lookup"><span data-stu-id="e2d82-165">Configure multiple B2C tenants in a Commerce environment</span></span>](configure-multi-B2C-tenants.md)

[<span data-ttu-id="e2d82-166">Adicionar suporte para uma rede de entrega de conteúdo (CDN)</span><span class="sxs-lookup"><span data-stu-id="e2d82-166">Add support for a content delivery network (CDN)</span></span>](add-cdn-support.md)

[<span data-ttu-id="e2d82-167">Habilitar detecção de lojas com base na localização</span><span class="sxs-lookup"><span data-stu-id="e2d82-167">Enable location-based store detection</span></span>](enable-store-detection.md)
