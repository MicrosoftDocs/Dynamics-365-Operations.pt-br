---
title: Suplemento Visibilidade de Estoque
description: Este tópico descreve como instalar e configurar o Suplemento Visibilidade de Estoque para Dynamics 365 Supply Chain Management.
author: chuzheng
manager: tfehr
ms.date: 10/26/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2020-10-26
ms.dyn365.ops.version: Release 10.0.15
ms.openlocfilehash: 2976153a6a7e4b4130e8f7673ed128945aeabf65
ms.sourcegitcommit: 03c2e1717b31e4c17ee7bb9004d2ba8cf379a036
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "4625056"
---
# <a name="inventory-visibility-add-in"></a><span data-ttu-id="7abe6-103">Suplemento Visibilidade de Estoque</span><span class="sxs-lookup"><span data-stu-id="7abe6-103">Inventory Visibility Add-in</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

<span data-ttu-id="7abe6-104">O Suplemento Visibilidade de Estoque é um microsserviço independente e altamente escalonável que permite o rastreamento de estoque disponível em tempo real, oferecendo, assim, uma visão global da visibilidade de estoque.</span><span class="sxs-lookup"><span data-stu-id="7abe6-104">The Inventory Visibility Add-in is an independent and highly scalable microservice that enables real-time on-hand inventory tracking, thus providing a global view of inventory visibility.</span></span>

<span data-ttu-id="7abe6-105">Todas as informações relacionadas ao estoque disponível são exportadas para o serviço quase em tempo real por meio de uma integração SQL de nível baixo.</span><span class="sxs-lookup"><span data-stu-id="7abe6-105">All information that relates to on-hand inventory is exported to the service in near real-time through low-level SQL integration.</span></span> <span data-ttu-id="7abe6-106">Os sistemas externos acessam o serviço por meio de APIs RESTful para consultar informações disponíveis sobre determinados conjuntos de dimensões, recuperando, dessa forma, uma lista de posições disponíveis.</span><span class="sxs-lookup"><span data-stu-id="7abe6-106">External systems access the service through RESTful APIs to query on-hand information on given sets of dimensions, thus retrieving a list of available on-hand positions.</span></span>

<span data-ttu-id="7abe6-107">A Visibilidade de Estoque é um microsserviço criado no Common Data Service, o que significa que você pode estendê-lo criando Power Apps e aplicando o Power BI para fornecer funcionalidade personalizada para atender aos seus requisitos de negócios.</span><span class="sxs-lookup"><span data-stu-id="7abe6-107">Inventory Visibility is a microservice built on the Common Data Service, which means you can extend it by building Power Apps and applying Power BI to provide customized functionality to meet your business requirements.</span></span> <span data-ttu-id="7abe6-108">Também é possível atualizar o índice para fazer consultas de estoque.</span><span class="sxs-lookup"><span data-stu-id="7abe6-108">It is also possible to upgrade the index to do inventory queries.</span></span>

<span data-ttu-id="7abe6-109">A Visibilidade de Estoque fornece opções de configuração que permitem a integração com vários sistemas de terceiros.</span><span class="sxs-lookup"><span data-stu-id="7abe6-109">Inventory Visibility provides configuration options that let it integrate with multiple third-party systems.</span></span> <span data-ttu-id="7abe6-110">Ela oferece suporte à dimensão de estoque padronizada, à extensibilidade personalizada e a quantidades calculadas padronizadas e configuráveis.</span><span class="sxs-lookup"><span data-stu-id="7abe6-110">It supports the standardized inventory dimension, customized extensibility, and standardized, configurable calculated quantities.</span></span>

<span data-ttu-id="7abe6-111">Este tópico descreve como instalar e configurar o Suplemento Visibilidade de Estoque para Dynamics 365 Supply Chain Management e como usar sua interface de programação de aplicativo (API).</span><span class="sxs-lookup"><span data-stu-id="7abe6-111">This topic describes how to install and configure the Inventory Visibility Add-in for Dynamics 365 Supply Chain Management, and how to use its application programming interface (API).</span></span>

## <a name="install-the-inventory-visibility-add-in"></a><span data-ttu-id="7abe6-112">Instalar o Suplemento Visibilidade de Estoque</span><span class="sxs-lookup"><span data-stu-id="7abe6-112">Install the Inventory Visibility Add-in</span></span>

<span data-ttu-id="7abe6-113">É necessário instalar o Suplemento Visibilidade de Estoque usando o Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="7abe6-113">You need to install the Inventory Visibility Add-in using Microsoft Dynamics Lifecycle Services (LCS).</span></span> <span data-ttu-id="7abe6-114">O LCS é um portal de colaboração que fornece um ambiente e um conjunto de serviços regularmente atualizados que ajudam a gerenciar o ciclo de vida dos seus aplicativos do Dynamics 365 Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="7abe6-114">LCS is a collaboration portal that provides an environment and a set of regularly updated services that help you manage the application lifecycle of your Dynamics 365 Finance and Operations apps.</span></span>

<span data-ttu-id="7abe6-115">Para obter mais informações, consulte [Recursos do Lifecycle Services](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/lifecycle-services/lcs).</span><span class="sxs-lookup"><span data-stu-id="7abe6-115">For more information, see [Lifecycle Services resources](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/lifecycle-services/lcs).</span></span>

### <a name="prerequisites"></a><span data-ttu-id="7abe6-116">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="7abe6-116">Prerequisites</span></span>

<span data-ttu-id="7abe6-117">Antes de instalar o Suplemento Visibilidade de Estoque, você deve fazer o seguinte:</span><span class="sxs-lookup"><span data-stu-id="7abe6-117">Before you install the Inventory Visibility Add-in, you must do the following:</span></span>

- <span data-ttu-id="7abe6-118">Obter um projeto de implementação do LCS com, pelo menos, um ambiente implantado.</span><span class="sxs-lookup"><span data-stu-id="7abe6-118">Obtain an LCS implementation project with at least one environment deployed.</span></span>
- <span data-ttu-id="7abe6-119">Gerar as chaves beta da sua oferta no LCS.</span><span class="sxs-lookup"><span data-stu-id="7abe6-119">Generate the beta keys for your offering in LCS.</span></span>
- <span data-ttu-id="7abe6-120">Habilitar as chaves beta da sua oferta para seu usuário no LCS.</span><span class="sxs-lookup"><span data-stu-id="7abe6-120">Enable the beta keys for your offering for your user in LCS.</span></span>
- <span data-ttu-id="7abe6-121">Entrar em contato com a equipe do produto Visibilidade de Estoque da Microsoft e fornecer uma ID de ambiente onde você deseja implantar o Suplemento Visibilidade de Estoque.</span><span class="sxs-lookup"><span data-stu-id="7abe6-121">Contact the Microsoft Inventory Visibility product team and provide an environment ID where you want to deploy the Inventory Visibility Add-in.</span></span>

<span data-ttu-id="7abe6-122">Caso tenha alguma dúvida sobre esses pré-requisitos, entre em contato com a equipe do produto Visibilidade de Estoque.</span><span class="sxs-lookup"><span data-stu-id="7abe6-122">If you have any questions about these prerequisites, please contact the Inventory Visibility product team.</span></span>

### <a name="install-the-add-in"></a><a name="install-add-in"></a><span data-ttu-id="7abe6-123">Instalar o suplemento</span><span class="sxs-lookup"><span data-stu-id="7abe6-123">Install the add-in</span></span>

<span data-ttu-id="7abe6-124">Para instalar o Suplemento Visibilidade de Estoque, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="7abe6-124">To install the Inventory Visibility Add-in, do the following:</span></span>

1. <span data-ttu-id="7abe6-125">Entre no portal [Lifecycle Services (LCS)](https://lcs.dynamics.com/Logon/Index).</span><span class="sxs-lookup"><span data-stu-id="7abe6-125">Sign in to the [Lifecycle Services (LCS)](https://lcs.dynamics.com/Logon/Index) portal.</span></span>
1. <span data-ttu-id="7abe6-126">Na home page, selecione o projeto no qual seu ambiente foi implantado.</span><span class="sxs-lookup"><span data-stu-id="7abe6-126">On the home page, select the project where your environment is deployed.</span></span>
1. <span data-ttu-id="7abe6-127">Na página do projeto, selecione o ambiente no qual você deseja instalar o suplemento.</span><span class="sxs-lookup"><span data-stu-id="7abe6-127">On the project page, select the environment where you want to install the add-in.</span></span>
1. <span data-ttu-id="7abe6-128">Na página do ambiente, role para baixo até ver a seção **Suplementos de ambiente**.</span><span class="sxs-lookup"><span data-stu-id="7abe6-128">On the environment page, scroll down until you see the **Environment add-ins** section.</span></span> <span data-ttu-id="7abe6-129">Se a seção não estiver visível, verifique se as chaves beta dos pré-requisitos foram totalmente processadas.</span><span class="sxs-lookup"><span data-stu-id="7abe6-129">If the section isn't visible, make sure the prerequisite beta keys have been fully processed.</span></span>
1. <span data-ttu-id="7abe6-130">Na seção **Suplementos de ambiente**, selecione **Instalar um novo suplemento**.</span><span class="sxs-lookup"><span data-stu-id="7abe6-130">In the **Environment add-ins** section, select **Install a new add-in**.</span></span>
    <span data-ttu-id="7abe6-131">![A página do ambiente no LCS](media/inventory-visibility-environment.png "A página do ambiente no LCS")</span><span class="sxs-lookup"><span data-stu-id="7abe6-131">![The environment page in LCS](media/inventory-visibility-environment.png "The environment page in LCS")</span></span>
1. <span data-ttu-id="7abe6-132">Selecione o link **Instalar um novo suplemento**.</span><span class="sxs-lookup"><span data-stu-id="7abe6-132">Select the **Install a new add-in** link.</span></span> <span data-ttu-id="7abe6-133">Uma lista dos suplementos disponíveis será aberta.</span><span class="sxs-lookup"><span data-stu-id="7abe6-133">A list of available add-ins opens.</span></span>
1. <span data-ttu-id="7abe6-134">Selecione **Serviço de estoque** na lista.</span><span class="sxs-lookup"><span data-stu-id="7abe6-134">Select **Inventory service** from the list.</span></span> <span data-ttu-id="7abe6-135">(Observe que agora isso pode estar listado como **Suplemento Visibilidade de Estoque para Dynamics 365 Supply Chain Management**.)</span><span class="sxs-lookup"><span data-stu-id="7abe6-135">(Note, this may now be listed as **Inventory Visibility Add-in for Dynamics 365 Supply Chain Management**.)</span></span>
1. <span data-ttu-id="7abe6-136">Insira valores para os seguintes campos no seu ambiente:</span><span class="sxs-lookup"><span data-stu-id="7abe6-136">Enter values for the following fields for your environment:</span></span>

    - <span data-ttu-id="7abe6-137">**ID de aplicativo do AAD**</span><span class="sxs-lookup"><span data-stu-id="7abe6-137">**AAD application ID**</span></span>
    - <span data-ttu-id="7abe6-138">**ID de locatário do AAD**</span><span class="sxs-lookup"><span data-stu-id="7abe6-138">**AAD tenant ID**</span></span>

    <span data-ttu-id="7abe6-139">![Página de configuração do suplemento](media/inventory-visibility-setup.png "Página de configuração do suplemento")</span><span class="sxs-lookup"><span data-stu-id="7abe6-139">![Add in setup page](media/inventory-visibility-setup.png "Add-in setup page")</span></span>

1. <span data-ttu-id="7abe6-140">Concorde com os termos e condições, marcando a caixa de seleção **Termos e condições**.</span><span class="sxs-lookup"><span data-stu-id="7abe6-140">Agree to the terms and condition by selecting the **Terms and conditions** check box.</span></span>
1. <span data-ttu-id="7abe6-141">Selecione **Instalar**.</span><span class="sxs-lookup"><span data-stu-id="7abe6-141">Select **Install**.</span></span> <span data-ttu-id="7abe6-142">O status do suplemento será mostrado como **Instalando**.</span><span class="sxs-lookup"><span data-stu-id="7abe6-142">The status of the add-in will show as **Installing**.</span></span> <span data-ttu-id="7abe6-143">Após a conclusão, atualize a página para ver a alteração do status para **Instalado**.</span><span class="sxs-lookup"><span data-stu-id="7abe6-143">When it's done, refresh the page to see the status change to **Installed**.</span></span>

### <a name="get-a-security-service-token"></a><span data-ttu-id="7abe6-144">Obter um token de serviço de segurança</span><span class="sxs-lookup"><span data-stu-id="7abe6-144">Get a security service token</span></span>

<span data-ttu-id="7abe6-145">Para obter um token de serviço de segurança, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="7abe6-145">To get a security service token, do the following:</span></span>

1. <span data-ttu-id="7abe6-146">Obtenha seu `aadToken` e chame o ponto de extremidade: https://securityservice.operations365.dynamics.com/token.</span><span class="sxs-lookup"><span data-stu-id="7abe6-146">Get your `aadToken` and call the endpoint: https://securityservice.operations365.dynamics.com/token.</span></span>
1. <span data-ttu-id="7abe6-147">Substitua a `client_assertion` no corpo pelo seu `aadToken`.</span><span class="sxs-lookup"><span data-stu-id="7abe6-147">Replace the `client_assertion` in the body with your `aadToken`.</span></span>
1. <span data-ttu-id="7abe6-148">Substitua o contexto no corpo pelo ambiente em que você deseja implantar o suplemento.</span><span class="sxs-lookup"><span data-stu-id="7abe6-148">Replace the context in the body with the environment where you want to deploy the add-in.</span></span>
1. <span data-ttu-id="7abe6-149">Substitua o escopo no corpo pelo seguinte:</span><span class="sxs-lookup"><span data-stu-id="7abe6-149">Replace the scope in the body with the following:</span></span>

    - <span data-ttu-id="7abe6-150">Escopo para MCK - "https://inventoryservice.operations365.dynamics.cn/.default"</span><span class="sxs-lookup"><span data-stu-id="7abe6-150">Scope for MCK - "https://inventoryservice.operations365.dynamics.cn/.default"</span></span>  
    <span data-ttu-id="7abe6-151">(Você pode encontrar a ID de aplicativo e a ID de locatário do Azure Active Directory para MCK em `appsettings.mck.json`.)</span><span class="sxs-lookup"><span data-stu-id="7abe6-151">(You can find the Azure Active Directory application ID and tenant ID for MCK in `appsettings.mck.json`.)</span></span>
    - <span data-ttu-id="7abe6-152">Escopo para PROD - "https://inventoryservice.operations365.dynamics.com/.default"</span><span class="sxs-lookup"><span data-stu-id="7abe6-152">Scope for PROD - "https://inventoryservice.operations365.dynamics.com/.default"</span></span>  
    <span data-ttu-id="7abe6-153">(Você pode encontrar a ID de aplicativo e a ID de locatário do Azure Active Directory para PROD em `appsettings.prod.json`.)</span><span class="sxs-lookup"><span data-stu-id="7abe6-153">(You can find the Azure Active Directory application ID and tenant ID for PROD in `appsettings.prod.json`.)</span></span>

    <span data-ttu-id="7abe6-154">O resultado deve se assemelhar ao seguinte exemplo.</span><span class="sxs-lookup"><span data-stu-id="7abe6-154">The result should resemble the following example.</span></span>

    ```json
    {
        "grant_type": "client_credentials",
        "client_assertion_type":"aad_app",
        "client_assertion": "{**Your_AADToken**}",
        "scope":"**https://inventoryservice.operations365.dynamics.com/.default**",
        "context": "**5dbf6cc8-255e-4de2-8a25-2101cd5649b4**",
        "context_type": "finops-env"
    }
    ```

1. <span data-ttu-id="7abe6-155">Você receberá um `access_token` em resposta.</span><span class="sxs-lookup"><span data-stu-id="7abe6-155">You will get an `access_token` in response.</span></span> <span data-ttu-id="7abe6-156">É disso que você precisará como um token de portador para chamar a API da Visibilidade de Estoque.</span><span class="sxs-lookup"><span data-stu-id="7abe6-156">This is what you need as a bearer token to call the Inventory Visibility API.</span></span> <span data-ttu-id="7abe6-157">Veja aqui um exemplo.</span><span class="sxs-lookup"><span data-stu-id="7abe6-157">Here is an example.</span></span>

    ```json
    {
        "access_token": "{Returned_Token}",
        "token_type": "bearer",
        "expires_in": 1200
    }
    ```

### <a name="uninstall-the-add-in"></a><span data-ttu-id="7abe6-158">Desinstalar o suplemento</span><span class="sxs-lookup"><span data-stu-id="7abe6-158">Uninstall the add-in</span></span>

<span data-ttu-id="7abe6-159">Para desinstalar o suplemento, selecione **Desinstalar**.</span><span class="sxs-lookup"><span data-stu-id="7abe6-159">To uninstall the add-in, select **Uninstall**.</span></span> <span data-ttu-id="7abe6-160">Atualize o LCS e o Suplemento Visibilidade de Estoque será removido.</span><span class="sxs-lookup"><span data-stu-id="7abe6-160">Refresh LCS and the Inventory Visibility Add-in will be removed.</span></span> <span data-ttu-id="7abe6-161">O processo de desinstalação removerá o registro do suplemento e também iniciará um trabalho para limpar todos os dados comerciais armazenados no serviço.</span><span class="sxs-lookup"><span data-stu-id="7abe6-161">The uninstall process will remove the add-in registration and also start a job to clean up all of the business data stored in the service.</span></span>

## <a name="inventory-visibility-add-in-public-api"></a><span data-ttu-id="7abe6-162">API pública do Suplemento Visibilidade de Estoque</span><span class="sxs-lookup"><span data-stu-id="7abe6-162">Inventory Visibility Add-in public API</span></span>

<span data-ttu-id="7abe6-163">A API REST pública do Suplemento Visibilidade de Estoque apresenta vários pontos de extremidade de integração específicos.</span><span class="sxs-lookup"><span data-stu-id="7abe6-163">The public REST API of the of the Inventory Visibility Add-in presents several specific endpoints of integration.</span></span> <span data-ttu-id="7abe6-164">Ela oferece suporte a três tipos de interação principais:</span><span class="sxs-lookup"><span data-stu-id="7abe6-164">It supports three main interaction types:</span></span>

- <span data-ttu-id="7abe6-165">Lançar alterações de disponibilidade no suplemento a partir de um sistema externo.</span><span class="sxs-lookup"><span data-stu-id="7abe6-165">Posting on-hand changes to the add-in from an external system.</span></span>
- <span data-ttu-id="7abe6-166">Consultar as quantidades disponíveis no momento a partir de um sistema externo.</span><span class="sxs-lookup"><span data-stu-id="7abe6-166">Querying current on-hand quantities from an external system.</span></span>
- <span data-ttu-id="7abe6-167">Sincronização automática com a disponibilidade do Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="7abe6-167">Automatic synchronization with Supply Chain Management on-hand.</span></span>

<span data-ttu-id="7abe6-168">A sincronização automática não faz parte da API pública, mas é tratada em segundo plano para ambientes que habilitaram o Suplemento Visibilidade de Estoque.</span><span class="sxs-lookup"><span data-stu-id="7abe6-168">The automatic synchronization isn't part of the public API but is instead handled in the background for environments that have enabled the Inventory Visibility Add-in.</span></span>

### <a name="authentication"></a><span data-ttu-id="7abe6-169">Autenticação</span><span class="sxs-lookup"><span data-stu-id="7abe6-169">Authentication</span></span>

<span data-ttu-id="7abe6-170">O token de segurança da plataforma é usado para chamar o Suplemento Visibilidade de Estoque, portanto, você deve gerar um token do Azure Active Directory usando seu aplicativo do Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="7abe6-170">The platform security token is used to call the Inventory Visibility Add-in, so you must generate an Azure Active Directory token using your Azure Active Directory application.</span></span>

<span data-ttu-id="7abe6-171">Para obter mais informações sobre como receber o token de segurança, consulte [Instalar o Suplemento Visibilidade de Estoque](#install-add-in).</span><span class="sxs-lookup"><span data-stu-id="7abe6-171">For more information about how to get the security token, see [Install the Inventory Visibility Add-in](#install-add-in).</span></span>

### <a name="configure-the-inventory-visibility-api"></a><span data-ttu-id="7abe6-172">Configurar a API da Visibilidade de Estoque</span><span class="sxs-lookup"><span data-stu-id="7abe6-172">Configure the Inventory Visibility API</span></span>

<span data-ttu-id="7abe6-173">Antes de usar o serviço, você deve concluir as configurações descritas nas subseções a seguir.</span><span class="sxs-lookup"><span data-stu-id="7abe6-173">Before using the service, you must complete the configurations described in the following subsections.</span></span> <span data-ttu-id="7abe6-174">A configuração pode variar com base nos detalhes do seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="7abe6-174">The configuration may vary based on the details of your environment.</span></span> <span data-ttu-id="7abe6-175">Ela inclui principalmente quatro partes:</span><span class="sxs-lookup"><span data-stu-id="7abe6-175">It primarily includes four parts:</span></span>

- [<span data-ttu-id="7abe6-176">Particionamento</span><span class="sxs-lookup"><span data-stu-id="7abe6-176">Partitioning</span></span>](#partitioning)
- [<span data-ttu-id="7abe6-177">Configurações de dimensões</span><span class="sxs-lookup"><span data-stu-id="7abe6-177">Dimension configurations</span></span>](#dimension-configurations)
- [<span data-ttu-id="7abe6-178">Indexando</span><span class="sxs-lookup"><span data-stu-id="7abe6-178">Indexing</span></span>](#indexing)
- [<span data-ttu-id="7abe6-179">Medida personalizada</span><span class="sxs-lookup"><span data-stu-id="7abe6-179">Custom measurement</span></span>](#custom-measurement)

#### <a name="partitioning"></a><span data-ttu-id="7abe6-180">Particionamento</span><span class="sxs-lookup"><span data-stu-id="7abe6-180">Partitioning</span></span>

<span data-ttu-id="7abe6-181">O particionamento pode influenciar significativamente o desempenho da API da Visibilidade de Estoque.</span><span class="sxs-lookup"><span data-stu-id="7abe6-181">Partitioning can significantly influence the performance of the Inventory Visibility API.</span></span> <span data-ttu-id="7abe6-182">É uma boa ideia definir um esquema que permita pequenos agrupamentos de dados e, ao mesmo tempo, permita consultas de dados significativas.</span><span class="sxs-lookup"><span data-stu-id="7abe6-182">It's a good idea to define a scheme that allows for small groupings of data while still allowing for meaningful data queries.</span></span>

<span data-ttu-id="7abe6-183">A `organizationId` (`dataAreaId` no Supply Chain Management) sempre fará parte do particionamento e, por padrão, a Visibilidade de Estoque é configurada para particionar por dimensões como *Local + Localização*.</span><span class="sxs-lookup"><span data-stu-id="7abe6-183">The `organizationId` (`dataAreaId` in Supply Chain Management) will always be part of the partitioning, and by default Inventory Visibility is set to partition by dimensions as *Site + Location*.</span></span> <span data-ttu-id="7abe6-184">Isso significa que o serviço sempre deve ser consultado com essas dimensões definidas nos filtros.</span><span class="sxs-lookup"><span data-stu-id="7abe6-184">This means that the service must always be queried with these dimensions defined on the filters.</span></span>

> [!NOTE]
> <span data-ttu-id="7abe6-185">*Local* e *Localização* são duas dimensões padrão gerais na Visibilidade de Estoque.</span><span class="sxs-lookup"><span data-stu-id="7abe6-185">*Site* and *Location* are two general default dimensions in Inventory Visibility.</span></span> <span data-ttu-id="7abe6-186">No Supply Chain Management, essas dimensões são chamadas de *Local* (`InventSiteId`) e *Depósito* (`InventLocationId`)</span><span class="sxs-lookup"><span data-stu-id="7abe6-186">In Supply Chain Management, those dimensions are called *Site* (`InventSiteId`) and *Warehouse* (`InventLocationId`)</span></span>

### <a name="dimension-configurations"></a><span data-ttu-id="7abe6-187">Configurações de dimensões</span><span class="sxs-lookup"><span data-stu-id="7abe6-187">Dimension configurations</span></span>

<span data-ttu-id="7abe6-188">A Visibilidade de Estoque fornecerá uma lista de dimensões padrão gerais para habilitar a integração de sistemas de várias fontes.</span><span class="sxs-lookup"><span data-stu-id="7abe6-188">Inventory Visibility will provide a list of general default dimensions to enable the multiple source system integration.</span></span>

<span data-ttu-id="7abe6-189">A tabela a seguir lista as dimensões de estoque que serão os nomes de dimensão padrão na Visibilidade de Estoque.</span><span class="sxs-lookup"><span data-stu-id="7abe6-189">The following table lists the inventory dimensions that will be the default dimension names in Inventory Visibility.</span></span>

| <span data-ttu-id="7abe6-190">Tipo de dimensão</span><span class="sxs-lookup"><span data-stu-id="7abe6-190">Dimension type</span></span> | <span data-ttu-id="7abe6-191">Nome da dimensão</span><span class="sxs-lookup"><span data-stu-id="7abe6-191">Dimension name</span></span> |
|---|---|
| <span data-ttu-id="7abe6-192">Produto</span><span class="sxs-lookup"><span data-stu-id="7abe6-192">Product</span></span> | `ColorId` |
| <span data-ttu-id="7abe6-193">Produto</span><span class="sxs-lookup"><span data-stu-id="7abe6-193">Product</span></span> | `SizeId` |
| <span data-ttu-id="7abe6-194">Produto</span><span class="sxs-lookup"><span data-stu-id="7abe6-194">Product</span></span> | `StyleId` |
| <span data-ttu-id="7abe6-195">Produto</span><span class="sxs-lookup"><span data-stu-id="7abe6-195">Product</span></span> | `ConfigId` |
| <span data-ttu-id="7abe6-196">Rastreamento</span><span class="sxs-lookup"><span data-stu-id="7abe6-196">Tracking</span></span> | `BatchId` |
| <span data-ttu-id="7abe6-197">Rastreamento</span><span class="sxs-lookup"><span data-stu-id="7abe6-197">Tracking</span></span> | `SerialId` |
| <span data-ttu-id="7abe6-198">Localização</span><span class="sxs-lookup"><span data-stu-id="7abe6-198">Location</span></span> | `LocationId` |
| <span data-ttu-id="7abe6-199">Localização</span><span class="sxs-lookup"><span data-stu-id="7abe6-199">Location</span></span> | `SiteId` |
| <span data-ttu-id="7abe6-200">Status do Estoque</span><span class="sxs-lookup"><span data-stu-id="7abe6-200">Inventory Status</span></span> | `StatusId` |
| <span data-ttu-id="7abe6-201">Específico do Depósito</span><span class="sxs-lookup"><span data-stu-id="7abe6-201">Warehouse Specific</span></span> | `WMSLocationId` |
| <span data-ttu-id="7abe6-202">Específico do Depósito</span><span class="sxs-lookup"><span data-stu-id="7abe6-202">Warehouse Specific</span></span> | `WMSPalletId` |
| <span data-ttu-id="7abe6-203">Específico do Depósito</span><span class="sxs-lookup"><span data-stu-id="7abe6-203">Warehouse Specific</span></span> | `LicensePlateId` |

> [!NOTE]
> <span data-ttu-id="7abe6-204">O tipo de dimensão listado na tabela anterior é somente para referência.</span><span class="sxs-lookup"><span data-stu-id="7abe6-204">The dimension type listed in the previous table is for reference only.</span></span> <span data-ttu-id="7abe6-205">Não é necessário definir o tipo de dimensão na Visibilidade de Estoque.</span><span class="sxs-lookup"><span data-stu-id="7abe6-205">You don't need to define the dimension type in Inventory Visibility.</span></span>

<span data-ttu-id="7abe6-206">Se uma dimensão personalizada existir e precisar fluir para um valor padrão quando consumida pela Visibilidade de Estoque, você poderá configurar o nome **Dimensão personalizada** na Visibilidade de Estoque.</span><span class="sxs-lookup"><span data-stu-id="7abe6-206">If a custom dimension exists and needs to flow to a default value when consumed by Inventory Visibility, you can configure the **Custom dimension** name in Inventory Visibility.</span></span>

<span data-ttu-id="7abe6-207">Os sistemas externos acessam a Visibilidade de Estoque por meio de APIs RESTful que habilitam informações de disponibilidade sobre determinados conjuntos de dimensões a serem consultadas.</span><span class="sxs-lookup"><span data-stu-id="7abe6-207">External systems access Inventory Visibility through RESTful APIs that enable on-hand information on given sets of dimensions to be queried.</span></span> <span data-ttu-id="7abe6-208">Para a integração, a Visibilidade de Estoque permite configurar a *fonte de dados do canal externo* e a dimensão de origem para as *dimensões de destino* na Visibilidade de Estoque.</span><span class="sxs-lookup"><span data-stu-id="7abe6-208">For the integration, Inventory Visibility enables you to configure the *external channel data source* and the source dimension to the *target dimensions* in Inventory Visibility.</span></span>

<span data-ttu-id="7abe6-209">As dimensões de destino devem ser uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="7abe6-209">The target dimensions should be one of the following:</span></span>

- <span data-ttu-id="7abe6-210">Dimensões padrão na Visibilidade de Estoque</span><span class="sxs-lookup"><span data-stu-id="7abe6-210">Default dimensions in Inventory Visibility</span></span>
- <span data-ttu-id="7abe6-211">Dimensões personalizadas</span><span class="sxs-lookup"><span data-stu-id="7abe6-211">Custom dimensions</span></span>

<span data-ttu-id="7abe6-212">A finalidade da configuração de dimensões é padronizar a integração de vários sistemas para a consulta em dimensões e o evento de lançamento com dimensões.</span><span class="sxs-lookup"><span data-stu-id="7abe6-212">The purpose of dimension configuration is to standardize the multi-system integration for the query on dimensions and the posting event with dimensions.</span></span>

#### <a name="indexing"></a><span data-ttu-id="7abe6-213">Indexando</span><span class="sxs-lookup"><span data-stu-id="7abe6-213">Indexing</span></span>

<span data-ttu-id="7abe6-214">Na maioria das vezes, a consulta de estoque disponível não só estará no nível "total" mais alto, mas talvez você queira ver resultados agregados com base nas dimensões de estoque.</span><span class="sxs-lookup"><span data-stu-id="7abe6-214">Most of the time, the inventory on-hand query will not only be on the highest "total" level, but you may want to see results aggregated based on the inventory dimensions.</span></span>

<span data-ttu-id="7abe6-215">A Visibilidade de Estoque fornece flexibilidade, permitindo que você configure os índices, que se baseiam na dimensão ou na combinação das dimensões.</span><span class="sxs-lookup"><span data-stu-id="7abe6-215">Inventory Visibility provides flexibility by allowing you to set up the indexes, which are based on the dimension or the combination of the dimensions.</span></span>

> [!NOTE]
> <span data-ttu-id="7abe6-216">No momento, só é possível configurar índices para, no máximo, cinco.</span><span class="sxs-lookup"><span data-stu-id="7abe6-216">Currently, you can only configure indexes to a maximum of five.</span></span> <span data-ttu-id="7abe6-217">É necessário considerar cuidadosamente qual dimensão ou combinação de dimensões você usará antes da implementação para garantir que ela atenderá às suas necessidades comerciais.</span><span class="sxs-lookup"><span data-stu-id="7abe6-217">You need to carefully consider which dimension or dimension combination you will use before the implementation to ensure that it will meet your business needs.</span></span> <span data-ttu-id="7abe6-218">Por exemplo, se você quiser consultar produtos da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="7abe6-218">For example, if you want to query products as follows:</span></span>

- <span data-ttu-id="7abe6-219">Consultar o produto agregado disponível por meio das dimensões *Cor* e *Tamanho*.</span><span class="sxs-lookup"><span data-stu-id="7abe6-219">Query the aggregated product on-hand by the *Color* and *Size* dimensions.</span></span>
- <span data-ttu-id="7abe6-220">Em alguns casos, você só deseja consultar o produto no total.</span><span class="sxs-lookup"><span data-stu-id="7abe6-220">In some cases, you just want to query on the product in total.</span></span>

<span data-ttu-id="7abe6-221">Você teria dois índices definidos da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="7abe6-221">You would have two indexes defined as the following:</span></span>

- `["ColorId", "SizeId"]`
- `[]`

<span data-ttu-id="7abe6-222">O colchete vazio agregará com base na ID do produto na partição.</span><span class="sxs-lookup"><span data-stu-id="7abe6-222">The empty bracket will aggregate based on the product ID within the partition.</span></span>

<span data-ttu-id="7abe6-223">A indexação define como você pode agrupar os resultados com base na configuração de consulta `groupBy`.</span><span class="sxs-lookup"><span data-stu-id="7abe6-223">The indexing defines how you can group your results based on the `groupBy` query setting.</span></span> <span data-ttu-id="7abe6-224">Nesse caso, se você não definir nenhum valor `groupBy`, obterá totais por `productid`.</span><span class="sxs-lookup"><span data-stu-id="7abe6-224">In this case if you don't define any `groupBy` values, you'll get totals by `productid`.</span></span> <span data-ttu-id="7abe6-225">Caso contrário, se você definir `groupBy` como `groupBy=ColorId&groupBy=SizeId`, receberá várias linhas retornadas, com base nas diferentes combinações de cor e tamanho no sistema.</span><span class="sxs-lookup"><span data-stu-id="7abe6-225">Otherwise if you define `groupBy` as `groupBy=ColorId&groupBy=SizeId`, you'll get multiple lines returned, based on the different color and size combinations in the system.</span></span>

<span data-ttu-id="7abe6-226">Você pode colocar os critérios de consulta no corpo da solicitação.</span><span class="sxs-lookup"><span data-stu-id="7abe6-226">You can put your query criteria in the request body.</span></span>

<span data-ttu-id="7abe6-227">Veja uma consulta de exemplo no produto com combinação de cor e tamanho.</span><span class="sxs-lookup"><span data-stu-id="7abe6-227">Here is a sample query on the product with color and size combination.</span></span>

```json
{
    "filters": {
        "OrganizationId": ["usmf"],
        "ProductId": ["MyProduct"],
        "LocationId": ["21"],
        "SiteId": ["2"],
        "ColorId": ["Red"]
    },
    "groupByValues": [
        "SizeId",
        "ColorId"
    ],
    "returnNegative": true
}
```

#### <a name="custom-measurement"></a><span data-ttu-id="7abe6-228">Medida personalizada</span><span class="sxs-lookup"><span data-stu-id="7abe6-228">Custom measurement</span></span>

<span data-ttu-id="7abe6-229">As quantidades de medidas padrão estão vinculadas ao Supply Chain Management, mas talvez você queira ter uma quantidade que seja composta por uma combinação das medidas padrão.</span><span class="sxs-lookup"><span data-stu-id="7abe6-229">The default measurement quantities are linked to Supply Chain Management, however you may want to have a quantity that is made up of a combination of the default measurements.</span></span> <span data-ttu-id="7abe6-230">Para isso, você pode ter uma configuração de quantidades personalizadas, que será adicionada à saída das consultas de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="7abe6-230">To do this, you can have a configuration of custom quantities, which will be added to the output of the on-hand queries.</span></span>

<span data-ttu-id="7abe6-231">A funcionalidade simplesmente permite definir um conjunto de medidas que será adicionado e/ou um conjunto de medidas que será subtraído para formar a medida personalizada.</span><span class="sxs-lookup"><span data-stu-id="7abe6-231">The functionality simply allows you to define a set of measures that will be added, and/or a set of measures that will be subtracted, in order to form the custom measurement.</span></span>

<span data-ttu-id="7abe6-232">Por exemplo, com a seguinte condição de consulta, você configurará a quantidade de medidas personalizadas como `MyCustomAvailableforReservation` para ser consumida pelo sistema de consumo.</span><span class="sxs-lookup"><span data-stu-id="7abe6-232">For example, with the following query condition, you will configure the custom measurement quantity as `MyCustomAvailableforReservation` to be consumed by the consumption system.</span></span>

```json
[
    {
        "productId": "MyProduct",
        "dimensions": {
            "colorid": "Red"
        },
        "quantities": {
            "mypos": {
                "outbound": 20.0,
                "inbound": 80.0
            },
            "fno": {
                "availphysical": 100.0,
                "orderedintotal": 50.0,
                "orderedreserved": 10.0
            },
            "exterchannel": {
                "received": 90.0,
                "scheduled": 30.0,
                "issued": 60.0,
                "reserved": 40.0
            }
        }
    }
]

```



| <span data-ttu-id="7abe6-233">Sistema de consumo</span><span class="sxs-lookup"><span data-stu-id="7abe6-233">Consumption system</span></span> | <span data-ttu-id="7abe6-234">Medidas calculadas</span><span class="sxs-lookup"><span data-stu-id="7abe6-234">Calculated measurers</span></span> | <span data-ttu-id="7abe6-235">Fonte de dados</span><span class="sxs-lookup"><span data-stu-id="7abe6-235">Data source</span></span> | <span data-ttu-id="7abe6-236">Modificador</span><span class="sxs-lookup"><span data-stu-id="7abe6-236">Modifier</span></span> | <span data-ttu-id="7abe6-237">Tipo de cálculo do modificador</span><span class="sxs-lookup"><span data-stu-id="7abe6-237">Modifier calculation type</span></span> |
|---|---|---|---|---|
| `CustomChannel` | `MyCustomAvailableforReservation` | `fno` | `availphysical` | <span data-ttu-id="7abe6-238">Adição</span><span class="sxs-lookup"><span data-stu-id="7abe6-238">Addition</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `fno` | `orderedintotal` | <span data-ttu-id="7abe6-239">Adição</span><span class="sxs-lookup"><span data-stu-id="7abe6-239">Addition</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `fno` | `orderedreserved` | <span data-ttu-id="7abe6-240">Subtração</span><span class="sxs-lookup"><span data-stu-id="7abe6-240">Subtraction</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `mypos` | `inbound` | <span data-ttu-id="7abe6-241">Adição</span><span class="sxs-lookup"><span data-stu-id="7abe6-241">Addition</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `mypos` | `outbound` | <span data-ttu-id="7abe6-242">Subtração</span><span class="sxs-lookup"><span data-stu-id="7abe6-242">Subtraction</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `exterchannel` | `received` | <span data-ttu-id="7abe6-243">Adição</span><span class="sxs-lookup"><span data-stu-id="7abe6-243">Addition</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `exterchannel` | `scheduled` | <span data-ttu-id="7abe6-244">Adição</span><span class="sxs-lookup"><span data-stu-id="7abe6-244">Addition</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `exterchannel` | `issued` | <span data-ttu-id="7abe6-245">Subtração</span><span class="sxs-lookup"><span data-stu-id="7abe6-245">Subtraction</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `exterchannel` | `reserved` | <span data-ttu-id="7abe6-246">Subtração</span><span class="sxs-lookup"><span data-stu-id="7abe6-246">Subtraction</span></span> |

<span data-ttu-id="7abe6-247">Com isso, a consulta na quantidade de medidas personalizadas retornará a seguinte saída.</span><span class="sxs-lookup"><span data-stu-id="7abe6-247">With that, the query on the custom measurement quantity will return the following output.</span></span>

```json
[
    {
        "productId": "MyProduct",
        "dimensions": {
            "colorid": "Red"
        },
        "quantities": {
            "mypos": {
                "outbound": 20.0,
                "inbound": 80.0
            },
            "fno": {
                "availphysical": 100.0,
                "orderedintotal": 50.0,
                "orderedreserved": 10.0
            },
            "exterchannel": {
                "received": 90.0,
                "scheduled": 30.0,
                "issued": 60.0,
                "reserved": 40.0
            },
            "CustomChannel": {
                "MyCustomAvailableforReservation": 220.0
            }
        }
    }
]
```

<span data-ttu-id="7abe6-248">A saída `MyCustomAvailableforReservation` se baseia na configuração de cálculo nas medidas personalizadas como:</span><span class="sxs-lookup"><span data-stu-id="7abe6-248">The `MyCustomAvailableforReservation` output is based on the calculation setting in the custom measurements as:</span></span>  
 <span data-ttu-id="7abe6-249">*100 + 50 + 80 + 90 + 30 &ndash; 10 &ndash; 20 &ndash; 60 &ndash; 40 = 220*</span><span class="sxs-lookup"><span data-stu-id="7abe6-249">*100 + 50 + 80 + 90 + 30 &ndash; 10 &ndash; 20 &ndash; 60 &ndash; 40 = 220*</span></span>

### <a name="posting-on-hand-changes"></a><span data-ttu-id="7abe6-250">Lançar alterações de disponibilidade</span><span class="sxs-lookup"><span data-stu-id="7abe6-250">Posting on-hand changes</span></span>

<span data-ttu-id="7abe6-251">A URL exata na qual o evento será lançado dependerá da sua região geográfica.</span><span class="sxs-lookup"><span data-stu-id="7abe6-251">The exact URL that the event will be posted to will depend on your geographical region.</span></span> <span data-ttu-id="7abe6-252">Ela terá a forma:</span><span class="sxs-lookup"><span data-stu-id="7abe6-252">It will take the form:</span></span>

`https://{serviceURL}/api/environment/{environmentId}/onhand`

<span data-ttu-id="7abe6-253">Quando autenticada, essa URL pode ser usada junto com o método HTTP `POST` para enviar eventos de alteração de disponibilidade para o serviço.</span><span class="sxs-lookup"><span data-stu-id="7abe6-253">When authenticated, this URL can be used along with the HTTP `POST` method to send on-hand change events to the service.</span></span>

<span data-ttu-id="7abe6-254">Um cabeçalho especial é usado para a comunicação com os serviços do Dynamics 365 por meio de solicitações HTTP, indicando a ID de ambiente da instância do Supply Chain Management à qual os dados estão vinculados.</span><span class="sxs-lookup"><span data-stu-id="7abe6-254">A special header is used for communicating with Dynamics 365 services through HTTP requests, denoting the environment ID of the Supply Chain Management instance the data is linked to.</span></span> <span data-ttu-id="7abe6-255">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="7abe6-255">For example:</span></span>

`x-ms-environment-id: 2db79622-f97a-4d64-9844-d12efed41796`

#### <a name="posting-on-hand-changes-query-example-1"></a><span data-ttu-id="7abe6-256">Exemplo de consulta de lançamento de alterações de disponibilidade 1</span><span class="sxs-lookup"><span data-stu-id="7abe6-256">Posting on-hand changes query example 1</span></span>

<span data-ttu-id="7abe6-257">Este exemplo mostra um cenário no qual você definirá a configuração de dimensões no Power Apps.</span><span class="sxs-lookup"><span data-stu-id="7abe6-257">This example shows a scenario where you will set up the dimension configuration in Power Apps.</span></span>

<span data-ttu-id="7abe6-258">Use a seguinte consulta para configurar o mapeamento de dimensões no Power Apps:</span><span class="sxs-lookup"><span data-stu-id="7abe6-258">Use the following query to configure the dimension mapping in Power Apps:</span></span>

```json
{
    "PosSizeId": "SizeId",
    "PosColorId": "ColorId",
    "PosSiteId": "SiteId",
    "PosLocationId": "LocationId"
}
```

<span data-ttu-id="7abe6-259">Agora, você pode especificar a `dimensionDataSource` e usar dimensões personalizadas nas suas consultas.</span><span class="sxs-lookup"><span data-stu-id="7abe6-259">Now you can specify the `dimensionDataSource` and use custom dimensions in your queries.</span></span> <span data-ttu-id="7abe6-260">O sistema converterá automaticamente as dimensões personalizadas em dimensões base.</span><span class="sxs-lookup"><span data-stu-id="7abe6-260">The system will automatically convert custom dimensions to base dimensions.</span></span>

```json
{
    "id": "demo-test-00007",
    "organizationId": "usmf",
    "productId": "MyProduct",
    "quantities": {
        "pos": {
            "Outbound": 1
        }
    },
    "dimensionDataSource": "pos",
    "dimensions": {
        "PosSizeId": "Large",
        "PosColorId": "Red",
        "PosSiteId": "2",
        "PosLocationId": "21"
    }
}
```

#### <a name="posting-on-hand-changes-query-example-2"></a><span data-ttu-id="7abe6-261">Exemplo de consulta de lançamento de alterações de disponibilidade 2</span><span class="sxs-lookup"><span data-stu-id="7abe6-261">Posting on-hand changes query example 2</span></span>

<span data-ttu-id="7abe6-262">Este exemplo mostra um cenário em que não há mapeamentos definidos para a configuração de dimensões no Power Apps, portanto, o lançamento também deve usar as dimensões base.</span><span class="sxs-lookup"><span data-stu-id="7abe6-262">This example shows a scenario where no mappings are set up for the dimension configuration in Power Apps, so the posting should also use the base dimensions.</span></span> <span data-ttu-id="7abe6-263">Todas as dimensões devem ser dimensões base quando o campo `dimensionDataSource` é nulo, vazio ou um espaço em branco.</span><span class="sxs-lookup"><span data-stu-id="7abe6-263">All dimensions must be base dimensions when the `dimensionDataSource` field is null, empty, or whitespace.</span></span>

```json
{
    "id": "demo-test-00007",
    "organizationId": "usmf",
    "productId": "MyProduct",
    "quantities": {
        "pos": {
            "Outbound": 1
        }
    },
    "dimensions": {
        "SizeId": "Large",
        "ColorId": "Red",
        "SiteId": "2",
        "LocationId": "21"
    }
}
```

#### <a name="json-document-field-properties"></a><span data-ttu-id="7abe6-264">Propriedades de campo do documento JSON</span><span class="sxs-lookup"><span data-stu-id="7abe6-264">JSON document field properties</span></span>

<span data-ttu-id="7abe6-265">Os campos dos exemplos de consulta JSON fornecidos anteriormente têm as propriedades listadas na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="7abe6-265">The fields from the JSON query examples provided previously have the properties listed in the following table.</span></span>

| <span data-ttu-id="7abe6-266">ID do campo</span><span class="sxs-lookup"><span data-stu-id="7abe6-266">Field ID</span></span> | <span data-ttu-id="7abe6-267">descrição</span><span class="sxs-lookup"><span data-stu-id="7abe6-267">Description</span></span> |
|---|---|
| `id` | <span data-ttu-id="7abe6-268">Uma ID exclusiva para o evento de alteração específico.</span><span class="sxs-lookup"><span data-stu-id="7abe6-268">A unique ID for the specific change event.</span></span> <span data-ttu-id="7abe6-269">Essa ID é usada para garantir que, se a comunicação com o serviço falhar durante o lançamento, o reenvio do evento não resultará no mesmo evento sendo contado duas vezes no sistema.</span><span class="sxs-lookup"><span data-stu-id="7abe6-269">This ID is used to ensure that if communication with the service fails during posting, resubmitting the event would not result in the same event being counted twice in the system.</span></span> |
| `organizationId` | <span data-ttu-id="7abe6-270">O identificador da organização vinculada ao evento.</span><span class="sxs-lookup"><span data-stu-id="7abe6-270">The identifier of the organization linked to the event.</span></span> <span data-ttu-id="7abe6-271">Isso é mapeado para as IDs de áreas de dados ou organizações do Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="7abe6-271">This maps to Supply Chain Management organizations or data area IDs.</span></span> |
| `productId` | <span data-ttu-id="7abe6-272">O identificador do produto em questão.</span><span class="sxs-lookup"><span data-stu-id="7abe6-272">The identifier of the product in question.</span></span> |
| `quantity` | <span data-ttu-id="7abe6-273">A quantidade pela qual a disponibilidade precisa ser alterada.</span><span class="sxs-lookup"><span data-stu-id="7abe6-273">The quantity by which the on-hand needs to be changed.</span></span> <span data-ttu-id="7abe6-274">Se, por exemplo, 10 novos bagels forem adicionados a uma prateleira, esse valor será 10.</span><span class="sxs-lookup"><span data-stu-id="7abe6-274">If, for instance, 10 new bagels were added to a shelf, this value would be 10.</span></span> <span data-ttu-id="7abe6-275">Se 3 bagels forem removidos da prateleira ou vendidos, esse valor será -3.</span><span class="sxs-lookup"><span data-stu-id="7abe6-275">If 3 bagels were then removed from the shelf or sold, this value would be -3.</span></span> |
| `dimensionDataSource` | <span data-ttu-id="7abe6-276">A fonte de dados das dimensões usadas no evento e na consulta de alteração de lançamento.</span><span class="sxs-lookup"><span data-stu-id="7abe6-276">The data source of the dimensions used in the posting change event and query.</span></span> <span data-ttu-id="7abe6-277">Se você especificar a fonte de dados, poderá usar as dimensões personalizadas da fonte de dados especificada.</span><span class="sxs-lookup"><span data-stu-id="7abe6-277">If you specify the data source, you can use the custom dimensions from the specified data source.</span></span> <span data-ttu-id="7abe6-278">Com a configuração de dimensões, a Visibilidade de Estoque pode mapear as dimensões personalizadas para as dimensões padrão gerais.</span><span class="sxs-lookup"><span data-stu-id="7abe6-278">With the dimension configuration, Inventory Visibility can map the custom dimensions to the general default dimensions.</span></span> <span data-ttu-id="7abe6-279">Se a `dimensionDataSource` não estiver especificada, você só poderá usar as dimensões padrão gerais nas suas consultas.</span><span class="sxs-lookup"><span data-stu-id="7abe6-279">If the `dimensionDataSource` is not specified, you can only use the general default dimensions in your queries.</span></span>   |
| `dimensions` | <span data-ttu-id="7abe6-280">Um recipiente dinâmico de pares de chave/valor.</span><span class="sxs-lookup"><span data-stu-id="7abe6-280">A dynamic bag of key/value pairs.</span></span> <span data-ttu-id="7abe6-281">Eles serão mapeados para algumas das dimensões no Supply Chain Management, mas você também pode adicionar dimensões personalizadas (como *Origem*) que podem indicar se o evento é proveniente do Supply Chain Management ou de um sistema externo.</span><span class="sxs-lookup"><span data-stu-id="7abe6-281">These will map to some of the dimensions in Supply Chain Management, but you could also add custom dimensions (like *Source*) that may denote if the event was coming from Supply Chain Management or an external system.</span></span> |

### <a name="querying-current-on-hand"></a><span data-ttu-id="7abe6-282">Consultar a disponibilidade atual</span><span class="sxs-lookup"><span data-stu-id="7abe6-282">Querying current on-hand</span></span>

<span data-ttu-id="7abe6-283">O ponto de extremidade para consultar a disponibilidade atual terá uma URL semelhante:</span><span class="sxs-lookup"><span data-stu-id="7abe6-283">The endpoint for querying the current on-hand will have a similar URL:</span></span>

`https://{serviceURL}/api/environment/{environmentId}/onhand/indexquery`

<span data-ttu-id="7abe6-284">Ela será consultada com o método HTTP `POST`.</span><span class="sxs-lookup"><span data-stu-id="7abe6-284">It will be queried with the HTTP `POST` method.</span></span>

#### <a name="current-on-hand-query-example-1"></a><span data-ttu-id="7abe6-285">Exemplo de consulta da disponibilidade atual 1</span><span class="sxs-lookup"><span data-stu-id="7abe6-285">Current on-hand query example 1</span></span>

<span data-ttu-id="7abe6-286">Este exemplo mostra um cenário no qual você já concluiu a configuração de dimensões no Power Apps.</span><span class="sxs-lookup"><span data-stu-id="7abe6-286">This example shows a scenario where you have already completed the dimension configuration in Power Apps.</span></span>

<span data-ttu-id="7abe6-287">Use a seguinte consulta para configurar o mapeamento de dimensões no Power Apps:</span><span class="sxs-lookup"><span data-stu-id="7abe6-287">Use the following query to configure the dimension mapping in Power Apps:</span></span>

```json
{
    "PosSizeId": "SizeId",
    "PosColorId": "ColorId",
    "PosSiteId": "SiteId",
    "PosLocationId": "LocationId"
}
```

<span data-ttu-id="7abe6-288">Agora, você pode especificar a `dimensionDataSource` e usar dimensões personalizadas nas suas consultas.</span><span class="sxs-lookup"><span data-stu-id="7abe6-288">Now you can specify the `dimensionDataSource` and use custom dimensions in your queries.</span></span> <span data-ttu-id="7abe6-289">O sistema converterá automaticamente as dimensões personalizadas em dimensões base.</span><span class="sxs-lookup"><span data-stu-id="7abe6-289">The system will automatically convert custom dimensions to base dimensions.</span></span> <span data-ttu-id="7abe6-290">Você pode especificar a `DimensionDataSource` em `filters` e especificar dimensões personalizadas em `filters` e `groupByValues`.</span><span class="sxs-lookup"><span data-stu-id="7abe6-290">You can specify the `DimensionDataSource` in `filters` and specify custom dimensions in both `filters` and `groupByValues`.</span></span> <span data-ttu-id="7abe6-291">O sistema converterá automaticamente as dimensões personalizadas em dimensões base.</span><span class="sxs-lookup"><span data-stu-id="7abe6-291">The system will automatically convert custom dimensions to base dimensions.</span></span>

```json
{
    "filters": {
        "OrganizationId": ["usmf"],
        "ProductId": ["MyProduct"],
        "DimensionDataSource": ["Pos"],
        "PosLocationId": ["21"],
        "PosSiteId": ["2"],
        "PosColorId": ["Red"]
    },
    "groupByValues": [
        "PosSizeId",
        "PosColorId"
    ],
    "returnNegative": true
}
```

#### <a name="current-on-hand-query-example-2"></a><span data-ttu-id="7abe6-292">Exemplo de consulta da disponibilidade atual 2</span><span class="sxs-lookup"><span data-stu-id="7abe6-292">Current on-hand query example 2</span></span>

<span data-ttu-id="7abe6-293">Este exemplo mostra um cenário em que não há mapeamentos definidos para a configuração de dimensões no Power Apps, portanto, o lançamento também deve usar as dimensões base.</span><span class="sxs-lookup"><span data-stu-id="7abe6-293">This example shows a scenario where no mappings are set up for the dimension configuration in Power Apps, so the posting should also use the base dimensions.</span></span> <span data-ttu-id="7abe6-294">Todas as dimensões devem ser dimensões base quando o campo `dimensionDataSource`, em `filters`, é nulo, vazio ou um espaço em branco.</span><span class="sxs-lookup"><span data-stu-id="7abe6-294">All dimensions must be base dimensions when the `dimensionDataSource` field, under `filters` is null, empty, or whitespace.</span></span>

```json
{
    "filters": {
        "OrganizationId": ["usmf"],
        "ProductId": ["MyProduct"],
        "LocationId": ["21"],
        "SiteId": ["2"],
        "ColorId": ["Red"]
    },
    "groupByValues": [
        "SizeId",
        "ColorId"
    ],
    "returnNegative": true
}
```

#### <a name="example-return-result"></a><span data-ttu-id="7abe6-295">Exemplo de retorno de resultado</span><span class="sxs-lookup"><span data-stu-id="7abe6-295">Example return result</span></span>

<span data-ttu-id="7abe6-296">As consultas mostradas nos exemplos anteriores poderiam retornar um resultado como este.</span><span class="sxs-lookup"><span data-stu-id="7abe6-296">The queries shown in the previous examples could return a result like this.</span></span>

```json
[
    {
        "productId": "MyProduct",
        "dimensions": {
            "colorid": "Red"
        },
        "quantities": {
            "mypos": {
                "outbound": 20.0,
                "inbound": 80.0
            },
            "fno": {
                "availphysical": 100.0,
                "orderedintotal": 50.0,
                "orderedreserved": 10.0
            },
            "exterchannel": {
                "received": 90.0,
                "scheduled": 30.0,
                "issued": 60.0,
                "reserved": 40.0
            },
            "CustomChannel": {
                "MyCustomAvailableforReservation": 220.0
            }
        }
    }
]
```

<span data-ttu-id="7abe6-297">Observe que os campos de quantidades estão estruturados como um dicionário de medidas e seus valores associados.</span><span class="sxs-lookup"><span data-stu-id="7abe6-297">Note that the quantities fields are structured as a dictionary of measures and their associated values.</span></span>
