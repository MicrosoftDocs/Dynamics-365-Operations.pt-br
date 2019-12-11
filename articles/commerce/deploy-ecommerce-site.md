---
title: Implantar um novo locatário de comércio eletrônico
description: Este tópico descreve como implantar um novo locatário de comércio eletrônico usando Microsoft Dynamics Lifecycle Services (LCS).
author: psimolin
manager: annbe
ms.date: 10/31/2019
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
ms.openlocfilehash: c2632632b9b21dd3a88e9a4df0e65cfd28e579d2
ms.sourcegitcommit: 295d940a345879b3dfc5991e387b91c7257019ea
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/01/2019
ms.locfileid: "2697442"
---
# <a name="deploy-a-new-e-commerce-tenant"></a><span data-ttu-id="13352-103">Implantar um novo locatário de comércio eletrônico</span><span class="sxs-lookup"><span data-stu-id="13352-103">Deploy a new e-Commerce tenant</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="13352-104">Este tópico descreve como implantar um novo site de comércio eletrônico usando Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="13352-104">This topic describes how to deploy a new e-Commerce site by using Microsoft Dynamics Lifecycle Services (LCS).</span></span>

## <a name="overview"></a><span data-ttu-id="13352-105">Visão geral</span><span class="sxs-lookup"><span data-stu-id="13352-105">Overview</span></span>
    
<span data-ttu-id="13352-106">Microsoft Dynamics Lifecycle Services (LCS) é um espaço de trabalho colaborativo baseado em nuvem que parceiros e clientes podem usar para gerenciar seus produtos e ambientes, exibir as informações mais recentes de produtos e serviços do Microsoft Dynamics, e criar, rastrear e navegar em incidentes de suporte.</span><span class="sxs-lookup"><span data-stu-id="13352-106">Microsoft Dynamics Lifecycle Services (LCS) is a cloud-based collaborative workspace that partners and customers can use to manage their projects and environments, view the latest information about Microsoft Dynamics products and features, and create, track, and browse support incidents.</span></span> <span data-ttu-id="13352-107">Os recursos de gerenciamento de comércio online são integrados no LCS.</span><span class="sxs-lookup"><span data-stu-id="13352-107">E-Commerce management features are integrated into LCS.</span></span>

<span data-ttu-id="13352-108">Para saber mais sobre LCS, consulte [Guia do usuário do Lifecycle Services](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/lifecycle-services/lcs-user-guide).</span><span class="sxs-lookup"><span data-stu-id="13352-108">To learn more about LCS, see the [Lifecycle Services User Guide](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/lifecycle-services/lcs-user-guide).</span></span>
    
## <a name="get-started"></a><span data-ttu-id="13352-109">Comece a usar</span><span class="sxs-lookup"><span data-stu-id="13352-109">Get started</span></span>

<span data-ttu-id="13352-110">Antes de poder iniciar o comércio online, você deve inicializar um projeto, um ambiente e um Retail Cloud Scale Unit (RCSU).</span><span class="sxs-lookup"><span data-stu-id="13352-110">Before you can initialize e-Commerce, you must initialize a project, an environment, and a Retail Cloud Scale Unit (RCSU).</span></span> <span data-ttu-id="13352-111">Para realizar a inicialização em LCS, você deve ter permissões para a função do gerente Proprietário do Projeto ou de Ambiente.</span><span class="sxs-lookup"><span data-stu-id="13352-111">To do the initialization in LCS, you must have permissions for either the Project Owner or Environment manager role.</span></span> <span data-ttu-id="13352-112">As topologias de produção e do ambiente do sandbox são suportadas.</span><span class="sxs-lookup"><span data-stu-id="13352-112">The production and sandbox environment topologies are supported.</span></span>

<span data-ttu-id="13352-113">Para obter mais informações sobre os ambientes, consulte [Planejamento de ambiente](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/imp-lifecycle/environment-planning).</span><span class="sxs-lookup"><span data-stu-id="13352-113">For more information about environments, see [Environment planning](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/imp-lifecycle/environment-planning).</span></span> <span data-ttu-id="13352-114">Para obter mais informações sobre RCSU, consulte [Inicializar Retail Cloud Scale Unit](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/deployment/initialize-retail-channels).</span><span class="sxs-lookup"><span data-stu-id="13352-114">For more information about RCSU, see [Initialize Retail Cloud Scale Unit](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/deployment/initialize-retail-channels).</span></span>

## <a name="initialize-e-commerce"></a><span data-ttu-id="13352-115">Inicializar comércio eletrônico</span><span class="sxs-lookup"><span data-stu-id="13352-115">Initialize e-Commerce</span></span>

<span data-ttu-id="13352-116">Use este procedimento para inicializar o recurso de comércio online em um ambiente existente.</span><span class="sxs-lookup"><span data-stu-id="13352-116">Use this procedure to initialize the e-Commerce feature in an existing environment.</span></span>

<span data-ttu-id="13352-117">Antes de começar, verifique se você tem as seguintes informações necessárias:</span><span class="sxs-lookup"><span data-stu-id="13352-117">Before you begin, make sure that you have the following required information:</span></span>

- <span data-ttu-id="13352-118">O RCSU que será usado.</span><span class="sxs-lookup"><span data-stu-id="13352-118">The RCSU that will be used.</span></span>
- <span data-ttu-id="13352-119">O grupo de segurança do Microsoft Azure Active Directory que será usado para administradores de sistemas de eletrônicos online.</span><span class="sxs-lookup"><span data-stu-id="13352-119">The Microsoft Azure Active Directory security group that will be used for e-Commerce system admins.</span></span>
- <span data-ttu-id="13352-120">O grupo de segurança do Microsoft Azure Active Directory que será usado para moderadores de avaliações e opiniões.</span><span class="sxs-lookup"><span data-stu-id="13352-120">The Microsoft Azure Active Directory security group that will be used for ratings and reviews moderators.</span></span>
- <span data-ttu-id="13352-121">Os domínios que serão associados com o ambiente.</span><span class="sxs-lookup"><span data-stu-id="13352-121">The domains that will be associated with the environment.</span></span>

<span data-ttu-id="13352-122">Além disso, você pode coletar as seguintes informações opcionais:</span><span class="sxs-lookup"><span data-stu-id="13352-122">In addition, you can collect the following optional information:</span></span>

- <span data-ttu-id="13352-123">Informações de business-to-consumer (B2C) do Azure AD:</span><span class="sxs-lookup"><span data-stu-id="13352-123">Azure AD business-to-consumer (B2C) information:</span></span>

    - <span data-ttu-id="13352-124">Nome do locatário.</span><span class="sxs-lookup"><span data-stu-id="13352-124">Tenant Name.</span></span>
    - <span data-ttu-id="13352-125">ID do Cliente.</span><span class="sxs-lookup"><span data-stu-id="13352-125">Client ID.</span></span>
    - <span data-ttu-id="13352-126">Domínio Personalizado de Logon.</span><span class="sxs-lookup"><span data-stu-id="13352-126">Login Custom Domain.</span></span>
    - <span data-ttu-id="13352-127">Resposta de URL.</span><span class="sxs-lookup"><span data-stu-id="13352-127">Reply URL.</span></span>
    - <span data-ttu-id="13352-128">ID da Política de Entrada da Inscrição.</span><span class="sxs-lookup"><span data-stu-id="13352-128">SignUp SignIn Policy ID.</span></span>
    - <span data-ttu-id="13352-129">ID da política de senha de redefinição.</span><span class="sxs-lookup"><span data-stu-id="13352-129">Reset password Policy ID.</span></span>
    - <span data-ttu-id="13352-130">Editar ID da Política de Perfil.</span><span class="sxs-lookup"><span data-stu-id="13352-130">Edit Profile Policy ID.</span></span>

[!NOTE]
<span data-ttu-id="13352-131">Essas informações podem ser adicionadas posteriormente, com uma solicitação de serviço.</span><span class="sxs-lookup"><span data-stu-id="13352-131">This information can be added later, through a service request.</span></span>

<span data-ttu-id="13352-132">Depois que coletou informações obrigatórias, siga essas etapas para inicializar o comércio online.</span><span class="sxs-lookup"><span data-stu-id="13352-132">After you've collected the required information, follow these steps to initialize e-Commerce.</span></span>

1. <span data-ttu-id="13352-133">Entre no [LCS](https://lcs.dynamics.com).</span><span class="sxs-lookup"><span data-stu-id="13352-133">Sign in to [LCS](https://lcs.dynamics.com).</span></span>
1. <span data-ttu-id="13352-134">Abra o projeto que contém o ambiente onde você deseja inicializar o comércio online.</span><span class="sxs-lookup"><span data-stu-id="13352-134">Open the project that contains the environment where you want to initialize e-Commerce.</span></span>
1. <span data-ttu-id="13352-135">Na seção **Ambientes**, selecione o ambiente.</span><span class="sxs-lookup"><span data-stu-id="13352-135">In the **Environments** section, select the environment.</span></span>
1. <span data-ttu-id="13352-136">Em **Recursos de ambiente**, selecione o link **Gerente de retail**.</span><span class="sxs-lookup"><span data-stu-id="13352-136">Under **Environment features**, select the **Retail manage** link.</span></span>
1. <span data-ttu-id="13352-137">Na guia **Comércio eletrônico**, selecione **Configuração**.</span><span class="sxs-lookup"><span data-stu-id="13352-137">On the **e-Commerce** tab, select **Setup**.</span></span> <span data-ttu-id="13352-138">É exibida uma caixa de diálogo, onde você pode inserir as informações que são necessárias para provisionamento.</span><span class="sxs-lookup"><span data-stu-id="13352-138">A dialog box appears, where you must enter the information that is required for provisioning.</span></span>
1. <span data-ttu-id="13352-139">Preencha as informações necessárias, e vá para a próxima página.</span><span class="sxs-lookup"><span data-stu-id="13352-139">Fill in the required information, and then go to the next page.</span></span>
1. <span data-ttu-id="13352-140">Na página a seguir, preencha as informações necessárias e depois envie o formulário.</span><span class="sxs-lookup"><span data-stu-id="13352-140">On the next page, fill in the required information, and then submit the form.</span></span> <span data-ttu-id="13352-141">Você volta para a guia **Comércio online**, onde você pode ver que a inicialização foi iniciada.</span><span class="sxs-lookup"><span data-stu-id="13352-141">You're returned to the **e-Commerce** tab, where you should see that initialization has been started.</span></span>
1. <span data-ttu-id="13352-142">Para exibir o status de inicialização, **Atualize** ou retorne para a guia **Comércio online** posteriormente.</span><span class="sxs-lookup"><span data-stu-id="13352-142">To view the initialization status, either **Refresh** or return to the **e-Commerce** tab later.</span></span>
    
<span data-ttu-id="13352-143">Quando o comércio online é inicializado do LCS, o sistema provisiona vários componentes necessários para o comércio online para associá-los ao ambiente.</span><span class="sxs-lookup"><span data-stu-id="13352-143">When e-Commerce is initialized from LCS, the system provisions several components that are required for e-Commerce and associates them with the environment.</span></span> <span data-ttu-id="13352-144">Após provisionar ser concluído, a guia **Comércio online** na guia **Gerenciamento de retail** é atualizada para refletir o provisionamento.</span><span class="sxs-lookup"><span data-stu-id="13352-144">After provisioning is completed, the **e-Commerce** tab on the **Retail management** page is updated to reflect the provisioning.</span></span> <span data-ttu-id="13352-145">A página mostra as últimas implantações de personalização e o status de quaisquer outras implantações em andamento.</span><span class="sxs-lookup"><span data-stu-id="13352-145">The page shows the latest customization deployments and the status of any other ongoing deployments.</span></span> <span data-ttu-id="13352-146">Também inclui links para site de comércio eletrônico e a ferramenta de gerenciamento de site de comércio online (a ferramenta de criação).</span><span class="sxs-lookup"><span data-stu-id="13352-146">It also includes links to the e-Commerce site and the e-Commerce site management tool (the authoring tool).</span></span>

## <a name="access-the-authoring-environment"></a><span data-ttu-id="13352-147">Acessar o ambiente de criação</span><span class="sxs-lookup"><span data-stu-id="13352-147">Access the authoring environment</span></span>

<span data-ttu-id="13352-148">Para acessar o ambiente de criação, vá para a guia **Comércio online** na página **Gerenciamento de retail**.</span><span class="sxs-lookup"><span data-stu-id="13352-148">To access the authoring environment, go to the **e-Commerce** tab on the **Retail management** page.</span></span> <span data-ttu-id="13352-149">Nele, você encontrará os links para o site de comércio online e a ferramenta de gerenciamento de site.</span><span class="sxs-lookup"><span data-stu-id="13352-149">There, you will find links to your e-Commerce site and the site management tool.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="13352-150">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="13352-150">Additional resources</span></span>

[<span data-ttu-id="13352-151">Visão geral de loja online</span><span class="sxs-lookup"><span data-stu-id="13352-151">Online store overview</span></span>](online-store-overview.md)

[<span data-ttu-id="13352-152">Criar um site de comércio eletrônico</span><span class="sxs-lookup"><span data-stu-id="13352-152">Create an e-Commerce site</span></span>](create-ecommerce-site.md)

[<span data-ttu-id="13352-153">Associar um site online a um canal</span><span class="sxs-lookup"><span data-stu-id="13352-153">Associate an online site with a channel</span></span>](associate-site-online-store.md)

[<span data-ttu-id="13352-154">Configure seu nome de domínio</span><span class="sxs-lookup"><span data-stu-id="13352-154">Configure your domain name</span></span>](configure-your-domain-name.md)

[<span data-ttu-id="13352-155">Adicionar suporte para uma rede de entrega de conteúdo (CDN)</span><span class="sxs-lookup"><span data-stu-id="13352-155">Add support for a content delivery network (CDN)</span></span>](add-cdn-support.md)

[<span data-ttu-id="13352-156">Habilitar detecção de lojas com base na localização</span><span class="sxs-lookup"><span data-stu-id="13352-156">Enable location-based store detection</span></span>](enable-store-detection.md)

[<span data-ttu-id="13352-157">Configurar páginas personalizadas para logons dos usuários</span><span class="sxs-lookup"><span data-stu-id="13352-157">Set up custom pages for user logins</span></span>](custom-pages-user-logins.md)
