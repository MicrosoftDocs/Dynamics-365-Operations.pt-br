---
title: Suplemento Visibilidade de Estoque
description: Este tópico descreve como instalar e configurar o Suplemento Visibilidade de Estoque para Dynamics 365 Supply Chain Management.
author: sherry-zheng
ms.date: 10/26/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2020-10-26
ms.dyn365.ops.version: Release 10.0.15
ms.openlocfilehash: d09c7be5de75511b10d7a69d4b8ac12917b0dbe8
ms.sourcegitcommit: 34b478f175348d99df4f2f0c2f6c0c21b6b2660a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/16/2021
ms.locfileid: "5910416"
---
# <a name="inventory-visibility-add-in"></a><span data-ttu-id="0dd53-103">Suplemento Visibilidade de Estoque</span><span class="sxs-lookup"><span data-stu-id="0dd53-103">Inventory Visibility Add-in</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]
[!INCLUDE [cc-data-platform-banner](../../includes/cc-data-platform-banner.md)]

<span data-ttu-id="0dd53-104">O Suplemento Visibilidade de Estoque é um microsserviço independente e altamente escalonável que permite o rastreamento de estoque disponível em tempo real, oferecendo, assim, uma visão global da visibilidade de estoque.</span><span class="sxs-lookup"><span data-stu-id="0dd53-104">The Inventory Visibility Add-in is an independent and highly scalable microservice that enables real-time on-hand inventory tracking, thus providing a global view of inventory visibility.</span></span>

<span data-ttu-id="0dd53-105">Todas as informações relacionadas ao estoque disponível são exportadas para o serviço quase em tempo real por meio de uma integração SQL de nível baixo.</span><span class="sxs-lookup"><span data-stu-id="0dd53-105">All information that relates to on-hand inventory is exported to the service in near real-time through low-level SQL integration.</span></span> <span data-ttu-id="0dd53-106">Os sistemas externos acessam o serviço por meio de APIs RESTful para consultar informações disponíveis sobre determinados conjuntos de dimensões, recuperando, dessa forma, uma lista de posições disponíveis.</span><span class="sxs-lookup"><span data-stu-id="0dd53-106">External systems access the service through RESTful APIs to query on-hand information on given sets of dimensions, thus retrieving a list of available on-hand positions.</span></span>

<span data-ttu-id="0dd53-107">A Visibilidade de Estoque é um microsserviço criado no Microsoft Dataverse, o que significa que você pode estendê-lo criando Power Apps e aplicando o Power BI para fornecer funcionalidade personalizada para atender aos seus requisitos de negócios.</span><span class="sxs-lookup"><span data-stu-id="0dd53-107">Inventory Visibility is a microservice built on Microsoft Dataverse, which means you can extend it by building Power Apps and applying Power BI to provide customized functionality to meet your business requirements.</span></span> <span data-ttu-id="0dd53-108">Também é possível atualizar o índice para fazer consultas de estoque.</span><span class="sxs-lookup"><span data-stu-id="0dd53-108">It is also possible to upgrade the index to do inventory queries.</span></span>

<span data-ttu-id="0dd53-109">A Visibilidade de Estoque fornece opções de configuração que permitem a integração com vários sistemas de terceiros.</span><span class="sxs-lookup"><span data-stu-id="0dd53-109">Inventory Visibility provides configuration options that let it integrate with multiple third-party systems.</span></span> <span data-ttu-id="0dd53-110">Ela oferece suporte à dimensão de estoque padronizada, à extensibilidade personalizada e a quantidades calculadas padronizadas e configuráveis.</span><span class="sxs-lookup"><span data-stu-id="0dd53-110">It supports the standardized inventory dimension, customized extensibility, and standardized, configurable calculated quantities.</span></span>

<span data-ttu-id="0dd53-111">Este tópico descreve como instalar e configurar o Suplemento Visibilidade de Estoque para Dynamics 365 Supply Chain Management e como usar sua interface de programação de aplicativo (API).</span><span class="sxs-lookup"><span data-stu-id="0dd53-111">This topic describes how to install and configure the Inventory Visibility Add-in for Dynamics 365 Supply Chain Management, and how to use its application programming interface (API).</span></span>

## <a name="install-the-inventory-visibility-add-in"></a><span data-ttu-id="0dd53-112">Instalar o Suplemento Visibilidade de Estoque</span><span class="sxs-lookup"><span data-stu-id="0dd53-112">Install the Inventory Visibility Add-in</span></span>

<span data-ttu-id="0dd53-113">É necessário instalar o Suplemento Visibilidade de Estoque usando o Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="0dd53-113">You need to install the Inventory Visibility Add-in using Microsoft Dynamics Lifecycle Services (LCS).</span></span> <span data-ttu-id="0dd53-114">O LCS é um portal de colaboração que fornece um ambiente e um conjunto de serviços regularmente atualizados que ajudam a gerenciar o ciclo de vida dos seus aplicativos do Dynamics 365 Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="0dd53-114">LCS is a collaboration portal that provides an environment and a set of regularly updated services that help you manage the application lifecycle of your Dynamics 365 Finance and Operations apps.</span></span>

<span data-ttu-id="0dd53-115">Para obter mais informações, consulte [Recursos do Lifecycle Services](../../fin-ops-core/dev-itpro/lifecycle-services/lcs.md).</span><span class="sxs-lookup"><span data-stu-id="0dd53-115">For more information, see [Lifecycle Services resources](../../fin-ops-core/dev-itpro/lifecycle-services/lcs.md).</span></span>

### <a name="prerequisites"></a><span data-ttu-id="0dd53-116">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="0dd53-116">Prerequisites</span></span>

<span data-ttu-id="0dd53-117">Antes de instalar o Suplemento Visibilidade de Estoque, você deve fazer o seguinte:</span><span class="sxs-lookup"><span data-stu-id="0dd53-117">Before you install the Inventory Visibility Add-in, you must do the following:</span></span>

- <span data-ttu-id="0dd53-118">Obter um projeto de implementação do LCS com, pelo menos, um ambiente implantado.</span><span class="sxs-lookup"><span data-stu-id="0dd53-118">Obtain an LCS implementation project with at least one environment deployed.</span></span>
- <span data-ttu-id="0dd53-119">Verifique se os pré-requisitos para a configuração de suplementos fornecidos na [Visão geral dos suplementos](../../fin-ops-core/dev-itpro/power-platform/add-ins-overview.md) foram concluídos.</span><span class="sxs-lookup"><span data-stu-id="0dd53-119">Make sure that the prerequisites for setting up add-ins provided in the [Add-ins overview](../../fin-ops-core/dev-itpro/power-platform/add-ins-overview.md) have been completed.</span></span> <span data-ttu-id="0dd53-120">A visibilidade de estoque não exige link de gravação dupla.</span><span class="sxs-lookup"><span data-stu-id="0dd53-120">Inventory Visibility doesn't require dual-write linking.</span></span>
- <span data-ttu-id="0dd53-121">Entre em contato com a equipe de visibilidade de estoque em [inventvisibilitysupp@microsoft.com](mailto:inventvisibilitysupp@microsoft.com) para obter os três seguintes arquivos necessários:</span><span class="sxs-lookup"><span data-stu-id="0dd53-121">Contact the Inventory Visibility Team at [inventvisibilitysupp@microsoft.com](mailto:inventvisibilitysupp@microsoft.com) to get the following three required files:</span></span>
    - `Inventory Visibility Dataverse Solution.zip`
    - `Inventory Visibility Configuration Trigger.zip`
    - <span data-ttu-id="0dd53-122">`Inventory Visibility Integration.zip` (se a versão do Supply Chain Management que você está executando for anterior à versão 10.0.18)</span><span class="sxs-lookup"><span data-stu-id="0dd53-122">`Inventory Visibility Integration.zip` (if the version of Supply Chain Management that you're running is earlier than version 10.0.18)</span></span>
- <span data-ttu-id="0dd53-123">Siga as instruções descritas em [Início rápido: registre um aplicativo com a plataforma de identidade da Microsoft](/azure/active-directory/develop/quickstart-register-app) para registrar um aplicativo e adicionar um segredo do cliente ao AAD com sua assinatura do Azure.</span><span class="sxs-lookup"><span data-stu-id="0dd53-123">Follow the instructions given in [Quickstart: Register an application with the Microsoft identity platform](/azure/active-directory/develop/quickstart-register-app) to register an application and add a client secret to AAD under your azure subscription.</span></span>
    - [<span data-ttu-id="0dd53-124">Registrar um aplicativo</span><span class="sxs-lookup"><span data-stu-id="0dd53-124">Register an application</span></span>](/azure/active-directory/develop/quickstart-register-app)
    - [<span data-ttu-id="0dd53-125">Adicionar um segredo do cliente</span><span class="sxs-lookup"><span data-stu-id="0dd53-125">Add a client secret</span></span>](/azure/active-directory/develop/quickstart-register-app#add-a-certificate)
    - <span data-ttu-id="0dd53-126">A **ID do aplicativo (cliente)**, o **Segredo do cliente** e a **ID de locatário** serão usados nas próximas etapas.</span><span class="sxs-lookup"><span data-stu-id="0dd53-126">The **Application(Client) Id**, **Client Secret** and **Tenant ID** will be used in the following steps.</span></span>

> [!NOTE]
> <span data-ttu-id="0dd53-127">Os países e regiões com suporte no momento incluem o Canadá, os Estados Unidos e a União Europeia (UE).</span><span class="sxs-lookup"><span data-stu-id="0dd53-127">The currently supported countries and regions include Canada, the United States, and the European Union (EU).</span></span>

<span data-ttu-id="0dd53-128">Caso tenha alguma dúvida sobre esses pré-requisitos, entre em contato com a equipe do produto Visibilidade de Estoque.</span><span class="sxs-lookup"><span data-stu-id="0dd53-128">If you have any questions about these prerequisites, please contact the Inventory Visibility product team.</span></span>

### <a name="set-up-dataverse"></a><a name="setup-microsoft-dataverse"></a><span data-ttu-id="0dd53-129">Configurar Dataverse</span><span class="sxs-lookup"><span data-stu-id="0dd53-129">Set up Dataverse</span></span>

<span data-ttu-id="0dd53-130">Siga estas etapas para configurar o Dataverse.</span><span class="sxs-lookup"><span data-stu-id="0dd53-130">Follow these steps to set up Dataverse.</span></span>

1. <span data-ttu-id="0dd53-131">Adicione um princípio de serviço ao seu locatário:</span><span class="sxs-lookup"><span data-stu-id="0dd53-131">Add a service principle to your tenant:</span></span>

    1. <span data-ttu-id="0dd53-132">Instale o módulo Azure AD PowerShell v2, conforme descrito em [Instalar o Azure Active Directory PowerShell para o Graph](/powershell/azure/active-directory/install-adv2).</span><span class="sxs-lookup"><span data-stu-id="0dd53-132">Install Azure AD PowerShell Module v2 as described in [Install Azure Active Directory PowerShell for Graph](/powershell/azure/active-directory/install-adv2).</span></span>
    1. <span data-ttu-id="0dd53-133">Execute o comando do PowerShell a seguir.</span><span class="sxs-lookup"><span data-stu-id="0dd53-133">Run the following PowerShell command.</span></span>

        ```powershell
        Connect-AzureAD # (open a sign in window and sign in as a tenant user)

        New-AzureADServicePrincipal -AppId "3022308a-b9bd-4a18-b8ac-2ddedb2075e1" -DisplayName "d365-scm-inventoryservice"
        ```

1. <span data-ttu-id="0dd53-134">Crie um usuário de aplicativo para a visibilidade de estoque no Dataverse:</span><span class="sxs-lookup"><span data-stu-id="0dd53-134">Create an application user for Inventory Visibility in Dataverse:</span></span>

    1. <span data-ttu-id="0dd53-135">Abra a URL do ambiente do Dataverse.</span><span class="sxs-lookup"><span data-stu-id="0dd53-135">Open the URL of your Dataverse environment.</span></span>
    1. <span data-ttu-id="0dd53-136">Acesse **Configuração Avançada \> Sistema \> Segurança \> Usuários** e crie um usuário de aplicativo.</span><span class="sxs-lookup"><span data-stu-id="0dd53-136">Go to **Advanced Setting \> System \> Security \> Users**, and create an application user.</span></span> <span data-ttu-id="0dd53-137">Use o menu de exibição para alterar a exibição de página para **Usuários do Aplicativo**.</span><span class="sxs-lookup"><span data-stu-id="0dd53-137">Use the view menu to change the page view to **Application Users**.</span></span>
    1. <span data-ttu-id="0dd53-138">Selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="0dd53-138">Select **New**.</span></span> <span data-ttu-id="0dd53-139">Defina a ID do aplicativo como *3022308a-b9bd-4a18-b8ac-2ddedb2075e1*.</span><span class="sxs-lookup"><span data-stu-id="0dd53-139">Set the application ID to *3022308a-b9bd-4a18-b8ac-2ddedb2075e1*.</span></span> <span data-ttu-id="0dd53-140">(A ID do objeto será carregada automaticamente quando você salvar as alterações.) Você pode personalizar o nome.</span><span class="sxs-lookup"><span data-stu-id="0dd53-140">(The object ID will automatically be loaded when you save your changes.) You can customize the name.</span></span> <span data-ttu-id="0dd53-141">Por exemplo, você pode alterá-lo para *Visibilidade do Estoque*.</span><span class="sxs-lookup"><span data-stu-id="0dd53-141">For example, you can change it to *Inventory Visibility*.</span></span> <span data-ttu-id="0dd53-142">Quando terminar, selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="0dd53-142">When you've finished, select **Save**.</span></span>
    1. <span data-ttu-id="0dd53-143">Selecione **Atribuir Função** e, depois, selecione **Administrador do Sistema**.</span><span class="sxs-lookup"><span data-stu-id="0dd53-143">Select **Assign Role**, and then select **System Administrator**.</span></span> <span data-ttu-id="0dd53-144">Se houver uma função denominada **Usuário do Common Data Service**, selecione-a.</span><span class="sxs-lookup"><span data-stu-id="0dd53-144">If there is a role that is named **Common Data Service User**, select it too.</span></span>

    <span data-ttu-id="0dd53-145">Para obter mais informações, consulte [Criar um usuário de aplicativo](/power-platform/admin/create-users-assign-online-security-roles#create-an-application-user).</span><span class="sxs-lookup"><span data-stu-id="0dd53-145">For more information, see [Create an application user](/power-platform/admin/create-users-assign-online-security-roles#create-an-application-user).</span></span>

1. <span data-ttu-id="0dd53-146">Se o idioma padrão de seu Dataverse não estiver definido como **Inglês**:</span><span class="sxs-lookup"><span data-stu-id="0dd53-146">If the default language of your Dataverse is not **English**:</span></span>

    1. <span data-ttu-id="0dd53-147">Acesse **Configurações avançadas \> Administração \> Idiomas**,</span><span class="sxs-lookup"><span data-stu-id="0dd53-147">Go to **Advanced Setting \> Administration \> Languages**,</span></span>
    1. <span data-ttu-id="0dd53-148">Selecione **Inglês (LanguageCode = 1033)** e selecione **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="0dd53-148">Select **English (LanguageCode=1033)** and select **Apply**.</span></span>

1. <span data-ttu-id="0dd53-149">Importe o arquivo `Inventory Visibility Dataverse Solution.zip`, que inclui entidades relacionadas à configuração do Dataverse e o Power Apps:</span><span class="sxs-lookup"><span data-stu-id="0dd53-149">Import the `Inventory Visibility Dataverse Solution.zip` file, which includes Dataverse configuration related entities and Power Apps:</span></span>

    1. <span data-ttu-id="0dd53-150">Acesse a página **Soluções**.</span><span class="sxs-lookup"><span data-stu-id="0dd53-150">Go to the **Solutions** page.</span></span>
    1. <span data-ttu-id="0dd53-151">Selecione **Importar**.</span><span class="sxs-lookup"><span data-stu-id="0dd53-151">Select **Import**.</span></span>

1. <span data-ttu-id="0dd53-152">Importe o fluxo do disparador da atualização de configuração:</span><span class="sxs-lookup"><span data-stu-id="0dd53-152">Import the configuration upgrade trigger flow:</span></span>

    1. <span data-ttu-id="0dd53-153">Acesse a página Microsoft Flow.</span><span class="sxs-lookup"><span data-stu-id="0dd53-153">Go to the Microsoft Flow page.</span></span>
    1. <span data-ttu-id="0dd53-154">Verifique se existe a conexão denominada *Dataverse (herdado)*.</span><span class="sxs-lookup"><span data-stu-id="0dd53-154">Make sure that the connection that is named *Dataverse (legacy)* exists.</span></span> <span data-ttu-id="0dd53-155">(Se ela não existir, crie-a.)</span><span class="sxs-lookup"><span data-stu-id="0dd53-155">(If it doesn't exist, create it.)</span></span>
    1. <span data-ttu-id="0dd53-156">Importe o arquivo `Inventory Visibility Configuration Trigger.zip`.</span><span class="sxs-lookup"><span data-stu-id="0dd53-156">Import the `Inventory Visibility Configuration Trigger.zip` file.</span></span> <span data-ttu-id="0dd53-157">Após ele ser importado, o disparador aparecerá em **Meus fluxos**.</span><span class="sxs-lookup"><span data-stu-id="0dd53-157">After it's imported, the trigger will appear under **My flows**.</span></span>
    1. <span data-ttu-id="0dd53-158">Inicialize as seguintes quatro variáveis, com base nas informações de ambiente:</span><span class="sxs-lookup"><span data-stu-id="0dd53-158">Initialize the following four variables, based on the environment information:</span></span>

        - <span data-ttu-id="0dd53-159">ID de Locatário do Azure</span><span class="sxs-lookup"><span data-stu-id="0dd53-159">Azure Tenant ID</span></span>
        - <span data-ttu-id="0dd53-160">ID do Cliente do Aplicativo Azure</span><span class="sxs-lookup"><span data-stu-id="0dd53-160">Azure Application Client ID</span></span>
        - <span data-ttu-id="0dd53-161">Segredo do Cliente do Aplicativo Azure</span><span class="sxs-lookup"><span data-stu-id="0dd53-161">Azure Application Client Secret</span></span>
        - <span data-ttu-id="0dd53-162">Ponto de extremidade da Visibilidade de Estoque</span><span class="sxs-lookup"><span data-stu-id="0dd53-162">Inventory Visibility Endpoint</span></span>

            <span data-ttu-id="0dd53-163">Para obter mais informações sobre essa variável, consulte a seção [Configurar integração da visibilidade de estoque](#setup-inventory-visibility-integration) mais adiante neste tópico.</span><span class="sxs-lookup"><span data-stu-id="0dd53-163">For more information about this variable, see the [Set up Inventory Visibility integration](#setup-inventory-visibility-integration) section later in this topic.</span></span>

        <span data-ttu-id="0dd53-164">![Gatilho de configurações](media/configuration-trigger.png "Gatilho de configurações")</span><span class="sxs-lookup"><span data-stu-id="0dd53-164">![Configuration trigger](media/configuration-trigger.png "Configuration trigger")</span></span>

    1. <span data-ttu-id="0dd53-165">Selecione **Ativar**.</span><span class="sxs-lookup"><span data-stu-id="0dd53-165">Select **Turn on**.</span></span>

### <a name="install-the-add-in"></a><a name="install-add-in"></a><span data-ttu-id="0dd53-166">Instalar o suplemento</span><span class="sxs-lookup"><span data-stu-id="0dd53-166">Install the add-in</span></span>

<span data-ttu-id="0dd53-167">Para instalar o Suplemento Visibilidade de Estoque, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="0dd53-167">To install the Inventory Visibility Add-in, do the following:</span></span>

1. <span data-ttu-id="0dd53-168">Entre no portal [Lifecycle Services (LCS)](https://lcs.dynamics.com/Logon/Index).</span><span class="sxs-lookup"><span data-stu-id="0dd53-168">Sign in to the [Lifecycle Services (LCS)](https://lcs.dynamics.com/Logon/Index) portal.</span></span>
1. <span data-ttu-id="0dd53-169">Na home page, selecione o projeto no qual seu ambiente foi implantado.</span><span class="sxs-lookup"><span data-stu-id="0dd53-169">On the home page, select the project where your environment is deployed.</span></span>
1. <span data-ttu-id="0dd53-170">Na página do projeto, selecione o ambiente no qual você deseja instalar o suplemento.</span><span class="sxs-lookup"><span data-stu-id="0dd53-170">On the project page, select the environment where you want to install the add-in.</span></span>
1. <span data-ttu-id="0dd53-171">Na página ambiente, role para baixo até ver a seção **Suplementos do ambiente** na seção **Integração do Power Platform**, em que você pode encontrar o nome do ambiente do Dataverse.</span><span class="sxs-lookup"><span data-stu-id="0dd53-171">On the environment page, scroll down until you see the **Environment add-ins** section in the **Power Platform integration** section, where you can find the Dataverse environment name.</span></span>
1. <span data-ttu-id="0dd53-172">Na seção **Suplementos de ambiente**, selecione **Instalar um novo suplemento**.</span><span class="sxs-lookup"><span data-stu-id="0dd53-172">In the **Environment add-ins** section, select **Install a new add-in**.</span></span>

    <span data-ttu-id="0dd53-173">![A página do ambiente no LCS](media/inventory-visibility-environment.png "A página do ambiente no LCS")</span><span class="sxs-lookup"><span data-stu-id="0dd53-173">![The environment page in LCS](media/inventory-visibility-environment.png "The environment page in LCS")</span></span>

1. <span data-ttu-id="0dd53-174">Selecione o link **Instalar um novo suplemento**.</span><span class="sxs-lookup"><span data-stu-id="0dd53-174">Select the **Install a new add-in** link.</span></span> <span data-ttu-id="0dd53-175">Uma lista dos suplementos disponíveis será aberta.</span><span class="sxs-lookup"><span data-stu-id="0dd53-175">A list of available add-ins opens.</span></span>
1. <span data-ttu-id="0dd53-176">Selecione **Visibilidade de Estoque** na lista.</span><span class="sxs-lookup"><span data-stu-id="0dd53-176">Select **Inventory Visibility** in the list.</span></span>
1. <span data-ttu-id="0dd53-177">Insira valores para os seguintes campos no seu ambiente:</span><span class="sxs-lookup"><span data-stu-id="0dd53-177">Enter values for the following fields for your environment:</span></span>

    - <span data-ttu-id="0dd53-178">**ID de aplicativo AAD (cliente)**</span><span class="sxs-lookup"><span data-stu-id="0dd53-178">**AAD application (client) ID**</span></span>
    - <span data-ttu-id="0dd53-179">**ID de locatário do AAD**</span><span class="sxs-lookup"><span data-stu-id="0dd53-179">**AAD tenant ID**</span></span>

    <span data-ttu-id="0dd53-180">![Página de configuração do suplemento](media/inventory-visibility-setup.png "Página de configuração do suplemento")</span><span class="sxs-lookup"><span data-stu-id="0dd53-180">![Add in setup page](media/inventory-visibility-setup.png "Add-in setup page")</span></span>

1. <span data-ttu-id="0dd53-181">Concorde com os termos e condições, marcando a caixa de seleção **Termos e condições**.</span><span class="sxs-lookup"><span data-stu-id="0dd53-181">Agree to the terms and condition by selecting the **Terms and conditions** check box.</span></span>
1. <span data-ttu-id="0dd53-182">Selecione **Instalar**.</span><span class="sxs-lookup"><span data-stu-id="0dd53-182">Select **Install**.</span></span> <span data-ttu-id="0dd53-183">O status do suplemento será mostrado como **Instalando**.</span><span class="sxs-lookup"><span data-stu-id="0dd53-183">The status of the add-in will show as **Installing**.</span></span> <span data-ttu-id="0dd53-184">Após a conclusão, atualize a página para ver a alteração do status para **Instalado**.</span><span class="sxs-lookup"><span data-stu-id="0dd53-184">When it's done, refresh the page to see the status change to **Installed**.</span></span>

### <a name="uninstall-the-add-in"></a><a name="uninstall-add-in"></a><span data-ttu-id="0dd53-185">Desinstalar o suplemento</span><span class="sxs-lookup"><span data-stu-id="0dd53-185">Uninstall the add-in</span></span>

<span data-ttu-id="0dd53-186">Para desinstalar o suplemento, selecione **Desinstalar**.</span><span class="sxs-lookup"><span data-stu-id="0dd53-186">To uninstall the add-in, select **Uninstall**.</span></span> <span data-ttu-id="0dd53-187">Quando você atualizar o LCS, o Suplemento de Visibilidade de Estoque será removido.</span><span class="sxs-lookup"><span data-stu-id="0dd53-187">When you refresh LCS, the Inventory Visibility Add-in will be removed.</span></span> <span data-ttu-id="0dd53-188">O processo de desinstalação remove o registro do suplemento e também inicia um trabalho para limpar todos os dados comerciais armazenados no serviço.</span><span class="sxs-lookup"><span data-stu-id="0dd53-188">The uninstall process removes the add-in registration and also starts a job to clean up all the business data that is stored in the service.</span></span>

## <a name="consume-on-hand-inventory-data-from-supply-chain-management"></a><span data-ttu-id="0dd53-189">Consumir dados de estoque disponível do Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="0dd53-189">Consume on-hand inventory data from Supply Chain Management</span></span>

### <a name="deploy-the-inventory-visibility-integration-package"></a><a name="deploy-inventory-visibility-package"></a><span data-ttu-id="0dd53-190">Implantar o pacote de integração de Visibilidade de Estoque</span><span class="sxs-lookup"><span data-stu-id="0dd53-190">Deploy the Inventory Visibility integration package</span></span>

<span data-ttu-id="0dd53-191">Se você estiver executando o Supply Chain Management versão 10.0.17 ou anterior, contate a equipe de suporte de integração da Visibilidade de Estoque em [inventvisibilitysupp@microsoft.com](mailto:inventvisibilitysupp@microsoft.com) para obter o arquivo de pacote.</span><span class="sxs-lookup"><span data-stu-id="0dd53-191">If you're running Supply Chain Management version 10.0.17 or earlier, contact the Inventory Visibility on-board support team at [inventvisibilitysupp@microsoft.com](mailto:inventvisibilitysupp@microsoft.com) to get the package file.</span></span> <span data-ttu-id="0dd53-192">Em seguida, implante o pacote no LCS.</span><span class="sxs-lookup"><span data-stu-id="0dd53-192">Then deploy the package in LCS.</span></span>

> [!NOTE]
> <span data-ttu-id="0dd53-193">Se ocorrer um erro de incompatibilidade de versão durante a implantação, você deverá importar manualmente o projeto X++ no ambiente de desenvolvimento.</span><span class="sxs-lookup"><span data-stu-id="0dd53-193">If a version mismatch error occurs during deployment, you must manually import the X++ project into your development environment.</span></span> <span data-ttu-id="0dd53-194">Em seguida, crie o pacote implantável no ambiente de desenvolvimento e implante-o no ambiente de produção.</span><span class="sxs-lookup"><span data-stu-id="0dd53-194">Then create the deployable package in your development environment, and deploy it in your production environment.</span></span>
> 
> <span data-ttu-id="0dd53-195">O código está incluído no Supply Chain Management versão 10.0.18.</span><span class="sxs-lookup"><span data-stu-id="0dd53-195">The code is included with Supply Chain Management version 10.0.18.</span></span> <span data-ttu-id="0dd53-196">Se você estiver executando essa versão ou posterior, a implantação não será necessária.</span><span class="sxs-lookup"><span data-stu-id="0dd53-196">If you're running that version or later, deployment isn't required.</span></span>

<span data-ttu-id="0dd53-197">Verifique se os recursos a seguir estão ativados no ambiente do Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="0dd53-197">Make sure that the following features are turned on in your Supply Chain Management environment.</span></span> <span data-ttu-id="0dd53-198">(Por padrão, eles são ativados.)</span><span class="sxs-lookup"><span data-stu-id="0dd53-198">(By default, they are turned on.)</span></span>

| <span data-ttu-id="0dd53-199">Descrição do recurso</span><span class="sxs-lookup"><span data-stu-id="0dd53-199">Feature description</span></span> | <span data-ttu-id="0dd53-200">Versão de código</span><span class="sxs-lookup"><span data-stu-id="0dd53-200">Code version</span></span> | <span data-ttu-id="0dd53-201">Alternar classe</span><span class="sxs-lookup"><span data-stu-id="0dd53-201">Toggle class</span></span> |
|---|---|---|
| <span data-ttu-id="0dd53-202">Habilitar ou desabilitar o uso de dimensões de estoque na tabela InventSum</span><span class="sxs-lookup"><span data-stu-id="0dd53-202">Enable or disable using inventory dimensions on InventSum table</span></span> | <span data-ttu-id="0dd53-203">10.0.11</span><span class="sxs-lookup"><span data-stu-id="0dd53-203">10.0.11</span></span> | <span data-ttu-id="0dd53-204">InventUseDimOfInventSumToggle</span><span class="sxs-lookup"><span data-stu-id="0dd53-204">InventUseDimOfInventSumToggle</span></span> |
| <span data-ttu-id="0dd53-205">Habilitar ou desabilitar o uso de dimensões de estoque na tabela InventSumDelta</span><span class="sxs-lookup"><span data-stu-id="0dd53-205">Enable or disable using inventory dimensions on InventSumDelta table</span></span> | <span data-ttu-id="0dd53-206">10.0.12</span><span class="sxs-lookup"><span data-stu-id="0dd53-206">10.0.12</span></span> | <span data-ttu-id="0dd53-207">InventUseDimOfInventSumDeltaToggle</span><span class="sxs-lookup"><span data-stu-id="0dd53-207">InventUseDimOfInventSumDeltaToggle</span></span> |

### <a name="set-up-inventory-visibility-integration"></a><a name="setup-inventory-visibility-integration"></a><span data-ttu-id="0dd53-208">Configurar a integração da Visibilidade de Estoque</span><span class="sxs-lookup"><span data-stu-id="0dd53-208">Set up Inventory Visibility integration</span></span>

1. <span data-ttu-id="0dd53-209">No Supply Chain Management, abra o espaço de trabalho **[Gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)** e ative o recurso **Integração da Visibilidade de Estoque**.</span><span class="sxs-lookup"><span data-stu-id="0dd53-209">In Supply Chain Management, open the **[Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)** workspace, and turn on the **Inventory Visibility Integration** feature.</span></span>
1. <span data-ttu-id="0dd53-210">Acesse **Gerenciamento de Estoque \> Configuração \> Parâmetros de Integração da Visibilidade de Estoque** e insira a URL do ambiente em que você está executando a Visibilidade de Estoque.</span><span class="sxs-lookup"><span data-stu-id="0dd53-210">Go to **Inventory Management \> Set up \> Inventory Visibility Integration parameters**, and enter the URL of the environment where you're running Inventory Visibility.</span></span>

    <span data-ttu-id="0dd53-211">Localize a região do Azure do ambiente do LCS e insira a URL.</span><span class="sxs-lookup"><span data-stu-id="0dd53-211">Find your LCS environment's Azure region, and then enter the URL.</span></span> <span data-ttu-id="0dd53-212">A URL tem o seguinte formato:</span><span class="sxs-lookup"><span data-stu-id="0dd53-212">The URL has the following form:</span></span>

    `https://inventoryservice.<RegionShortName>-il301.gateway.prod.island.powerapps.com`

    <span data-ttu-id="0dd53-213">Por exemplo, se você estiver na Europa, o ambiente terá uma das seguintes URLs:</span><span class="sxs-lookup"><span data-stu-id="0dd53-213">For example, if you're in Europe, your environment will have one of the following URLs:</span></span>

    - `https://inventoryservice.neu-il301.gateway.prod.island.powerapps.com`
    - `https://inventoryservice.weu-il301.gateway.prod.island.powerapps.com`

    <span data-ttu-id="0dd53-214">As regiões a seguir estão disponíveis no momento.</span><span class="sxs-lookup"><span data-stu-id="0dd53-214">The following regions are currently available.</span></span>

    | <span data-ttu-id="0dd53-215">Região do Azure</span><span class="sxs-lookup"><span data-stu-id="0dd53-215">Azure region</span></span> | <span data-ttu-id="0dd53-216">Nome curto da região</span><span class="sxs-lookup"><span data-stu-id="0dd53-216">Region short name</span></span> |
    |---|---|
    | <span data-ttu-id="0dd53-217">Leste da Austrália</span><span class="sxs-lookup"><span data-stu-id="0dd53-217">Australia east</span></span> | <span data-ttu-id="0dd53-218">eau</span><span class="sxs-lookup"><span data-stu-id="0dd53-218">eau</span></span> |
    | <span data-ttu-id="0dd53-219">Sudeste da Austrália</span><span class="sxs-lookup"><span data-stu-id="0dd53-219">Australia southeast</span></span> | <span data-ttu-id="0dd53-220">seau</span><span class="sxs-lookup"><span data-stu-id="0dd53-220">seau</span></span> |
    | <span data-ttu-id="0dd53-221">Canadá Central</span><span class="sxs-lookup"><span data-stu-id="0dd53-221">Canada central</span></span> | <span data-ttu-id="0dd53-222">cca</span><span class="sxs-lookup"><span data-stu-id="0dd53-222">cca</span></span> |
    | <span data-ttu-id="0dd53-223">Leste do Canadá</span><span class="sxs-lookup"><span data-stu-id="0dd53-223">Canada east</span></span> | <span data-ttu-id="0dd53-224">eca</span><span class="sxs-lookup"><span data-stu-id="0dd53-224">eca</span></span> |
    | <span data-ttu-id="0dd53-225">Norte da Europa</span><span class="sxs-lookup"><span data-stu-id="0dd53-225">North Europe</span></span> | <span data-ttu-id="0dd53-226">neu</span><span class="sxs-lookup"><span data-stu-id="0dd53-226">neu</span></span> |
    | <span data-ttu-id="0dd53-227">Oeste da Europa</span><span class="sxs-lookup"><span data-stu-id="0dd53-227">West Europe</span></span> | <span data-ttu-id="0dd53-228">weu</span><span class="sxs-lookup"><span data-stu-id="0dd53-228">weu</span></span> |
    | <span data-ttu-id="0dd53-229">Leste dos EUA</span><span class="sxs-lookup"><span data-stu-id="0dd53-229">East US</span></span> | <span data-ttu-id="0dd53-230">eus</span><span class="sxs-lookup"><span data-stu-id="0dd53-230">eus</span></span> |
    | <span data-ttu-id="0dd53-231">Oeste dos EUA</span><span class="sxs-lookup"><span data-stu-id="0dd53-231">West US</span></span> | <span data-ttu-id="0dd53-232">wus</span><span class="sxs-lookup"><span data-stu-id="0dd53-232">wus</span></span> |

1. <span data-ttu-id="0dd53-233">Acesse **Gerenciamento de Estoque \> Periódico \> Integração de Visibilidade de Estoque** e habilite o trabalho.</span><span class="sxs-lookup"><span data-stu-id="0dd53-233">Go to **Inventory Management \> Periodic \> Inventory Visibility Integration**, and enable the job.</span></span> <span data-ttu-id="0dd53-234">Todos os eventos de alteração de inventário do Supply Chain Management serão lançados na Visibilidade de Estoque.</span><span class="sxs-lookup"><span data-stu-id="0dd53-234">All inventory change events from Supply Chain Management will now be posted to Inventory Visibility.</span></span>

## <a name="the-inventory-visibility-add-in-public-api"></a><a name="inventory-visibility-public-api"></a><span data-ttu-id="0dd53-235">A API pública do Suplemento Visibilidade de Estoque</span><span class="sxs-lookup"><span data-stu-id="0dd53-235">The Inventory Visibility Add-in public API</span></span>

<span data-ttu-id="0dd53-236">A API REST pública do Suplemento Visibilidade de Estoque apresenta vários pontos de extremidade específicos para integração.</span><span class="sxs-lookup"><span data-stu-id="0dd53-236">The public REST API of the Inventory Visibility Add-in presents several specific endpoints for integration.</span></span> <span data-ttu-id="0dd53-237">Ela oferece suporte a três tipos de interação principais:</span><span class="sxs-lookup"><span data-stu-id="0dd53-237">It supports three main interaction types:</span></span>

- <span data-ttu-id="0dd53-238">Lançar alterações de estoque disponíveis no suplemento a partir de um sistema externo</span><span class="sxs-lookup"><span data-stu-id="0dd53-238">Posting on-hand inventory changes to the add-in from an external system</span></span>
- <span data-ttu-id="0dd53-239">Consultar as quantidades disponíveis no momento a partir de um sistema externo</span><span class="sxs-lookup"><span data-stu-id="0dd53-239">Querying current on-hand quantities from an external system</span></span>
- <span data-ttu-id="0dd53-240">Sincronização automática com o estoque disponível do Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="0dd53-240">Automatic synchronization with Supply Chain Management on-hand inventory</span></span>

<span data-ttu-id="0dd53-241">A sincronização automática não faz parte da API pública.</span><span class="sxs-lookup"><span data-stu-id="0dd53-241">Automatic synchronization isn't part of the public API.</span></span> <span data-ttu-id="0dd53-242">Ela é tratada em segundo plano para ambientes em que o suplemento Visibilidade de Estoque está habilitado.</span><span class="sxs-lookup"><span data-stu-id="0dd53-242">Instead, it's handled in the background for environments where the Inventory Visibility Add-in is enabled.</span></span>

### <a name="authentication"></a><a name="inventory-visibility-authentication"></a><span data-ttu-id="0dd53-243">Autenticação</span><span class="sxs-lookup"><span data-stu-id="0dd53-243">Authentication</span></span>

<span data-ttu-id="0dd53-244">O token de segurança da plataforma é usado para chamar o suplemento Visibilidade de Estoque.</span><span class="sxs-lookup"><span data-stu-id="0dd53-244">The platform security token is used to call the Inventory Visibility Add-in.</span></span> <span data-ttu-id="0dd53-245">Portanto, você deve gerar um token *Azure Active Directory (Azure AD)* usando o aplicativo Azure AD.</span><span class="sxs-lookup"><span data-stu-id="0dd53-245">Therefore, you must generate an *Azure Active Directory (Azure AD) token* by using your Azure AD application.</span></span> <span data-ttu-id="0dd53-246">Você deve usar o token Azure AD para obter o *token de acesso* do serviço de segurança.</span><span class="sxs-lookup"><span data-stu-id="0dd53-246">You must then use the Azure AD token to get the *access token* from the security service.</span></span>

<span data-ttu-id="0dd53-247">Obtenha um token de serviço de segurança da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="0dd53-247">Get a security service token by doing the following:</span></span>

1. <span data-ttu-id="0dd53-248">Entre no portal do Azure e use-o para localizar `clientId` e `clientSecret` para o aplicativo Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="0dd53-248">Sign in to Azure portal and use it to find the `clientId` and `clientSecret` for your Supply Chain Management application.</span></span>
1. <span data-ttu-id="0dd53-249">Busque um token do Azure Active Directory (`aadToken`) enviando uma solicitação HTTP com as seguintes propriedades:</span><span class="sxs-lookup"><span data-stu-id="0dd53-249">Fetch an Azure Active Directory token (`aadToken`) by submitting an HTTP request with the following properties:</span></span>
    - <span data-ttu-id="0dd53-250">**URL** - `https://login.microsoftonline.com/${aadTenantId}/oauth2/token`</span><span class="sxs-lookup"><span data-stu-id="0dd53-250">**URL** - `https://login.microsoftonline.com/${aadTenantId}/oauth2/token`</span></span>
    - <span data-ttu-id="0dd53-251">**Método** - `GET`</span><span class="sxs-lookup"><span data-stu-id="0dd53-251">**Method** - `GET`</span></span>
    - <span data-ttu-id="0dd53-252">**Conteúdo do corpo (dados de formulário)**:</span><span class="sxs-lookup"><span data-stu-id="0dd53-252">**Body content (form data)**:</span></span>

        | <span data-ttu-id="0dd53-253">key</span><span class="sxs-lookup"><span data-stu-id="0dd53-253">key</span></span> | <span data-ttu-id="0dd53-254">valor</span><span class="sxs-lookup"><span data-stu-id="0dd53-254">value</span></span> |
        | --- | --- |
        | <span data-ttu-id="0dd53-255">client_id</span><span class="sxs-lookup"><span data-stu-id="0dd53-255">client_id</span></span> | <span data-ttu-id="0dd53-256">${aadAppId}</span><span class="sxs-lookup"><span data-stu-id="0dd53-256">${aadAppId}</span></span> |
        | <span data-ttu-id="0dd53-257">client_secret</span><span class="sxs-lookup"><span data-stu-id="0dd53-257">client_secret</span></span> | <span data-ttu-id="0dd53-258">${aadAppSecret}</span><span class="sxs-lookup"><span data-stu-id="0dd53-258">${aadAppSecret}</span></span> |
        | <span data-ttu-id="0dd53-259">grant_type</span><span class="sxs-lookup"><span data-stu-id="0dd53-259">grant_type</span></span> | <span data-ttu-id="0dd53-260">client_credentials</span><span class="sxs-lookup"><span data-stu-id="0dd53-260">client_credentials</span></span> |
        | <span data-ttu-id="0dd53-261">resource</span><span class="sxs-lookup"><span data-stu-id="0dd53-261">resource</span></span> | <span data-ttu-id="0dd53-262">0cdb527f-a8d1-4bf8-9436-b352c68682b2</span><span class="sxs-lookup"><span data-stu-id="0dd53-262">0cdb527f-a8d1-4bf8-9436-b352c68682b2</span></span> |
1. <span data-ttu-id="0dd53-263">Você receberá um `aadToken` em resposta, que se parece com o seguinte exemplo.</span><span class="sxs-lookup"><span data-stu-id="0dd53-263">You should receive an `aadToken` in response, which resembles the following example.</span></span>

    ```json
    {
        "token_type": "Bearer",
        "expires_in": "3599",
        "ext_expires_in": "3599",
        "expires_on": "1610466645",
        "not_before": "1610462745",
        "resource": "0cdb527f-a8d1-4bf8-9436-b352c68682b2",
        "access_token": "eyJ0eX...8WQ"
    }
    ```

1. <span data-ttu-id="0dd53-264">Formule uma solicitação JSON que se parece com a seguinte:</span><span class="sxs-lookup"><span data-stu-id="0dd53-264">Formulate a JSON request that resembles the following:</span></span>

    ```json
    {
        "grant_type": "client_credentials",
        "client_assertion_type":"aad_app",
        "client_assertion": "{Your_AADToken}",
        "scope":"https://inventoryservice.operations365.dynamics.com/.default",
        "context": "5dbf6cc8-255e-4de2-8a25-2101cd5649b4",
        "context_type": "finops-env"
    }
    ```

    <span data-ttu-id="0dd53-265">Onde:</span><span class="sxs-lookup"><span data-stu-id="0dd53-265">Where:</span></span>
    - <span data-ttu-id="0dd53-266">O valor `client_assertion` deve ser o `aadToken` que recebeu na etapa anterior.</span><span class="sxs-lookup"><span data-stu-id="0dd53-266">The `client_assertion` value must be the `aadToken` you received in the previous step.</span></span>
    - <span data-ttu-id="0dd53-267">O valor de `context` deve ser a ID do ambiente em que deseja implantar o suplemento.</span><span class="sxs-lookup"><span data-stu-id="0dd53-267">The `context` value must be the environment ID where you want to deploy the add-in.</span></span>
    - <span data-ttu-id="0dd53-268">Defina todos os demais valores conforme exibido no exemplo.</span><span class="sxs-lookup"><span data-stu-id="0dd53-268">Set all of other values as shown in the example.</span></span>

1. <span data-ttu-id="0dd53-269">Envie uma solicitação HTTP com as seguintes propriedades:</span><span class="sxs-lookup"><span data-stu-id="0dd53-269">Submit an HTTP request with the following properties:</span></span>
    - <span data-ttu-id="0dd53-270">**URL** - `https://securityservice.operations365.dynamics.com/token`</span><span class="sxs-lookup"><span data-stu-id="0dd53-270">**URL** - `https://securityservice.operations365.dynamics.com/token`</span></span>
    - <span data-ttu-id="0dd53-271">**Método** - `POST`</span><span class="sxs-lookup"><span data-stu-id="0dd53-271">**Method** - `POST`</span></span>
    - <span data-ttu-id="0dd53-272">**Cabeçalho HTTP** – inclua a versão da API (a chave é `Api-Version` e o valor é `1.0`)</span><span class="sxs-lookup"><span data-stu-id="0dd53-272">**HTTP header** - Include the API version (key is `Api-Version` and value is `1.0`)</span></span>
    - <span data-ttu-id="0dd53-273">**Conteúdo do corpo** – inclua a solicitação JSON criada na etapa anterior.</span><span class="sxs-lookup"><span data-stu-id="0dd53-273">**Body content** - Include the JSON request that you created in the previous step.</span></span>

1. <span data-ttu-id="0dd53-274">Você receberá um `access_token` em resposta.</span><span class="sxs-lookup"><span data-stu-id="0dd53-274">You will get an `access_token` in response.</span></span> <span data-ttu-id="0dd53-275">É disso que você precisará como um token de portador para chamar a API da Visibilidade de Estoque.</span><span class="sxs-lookup"><span data-stu-id="0dd53-275">This is what you need as a bearer token to call the Inventory Visibility API.</span></span> <span data-ttu-id="0dd53-276">Veja aqui um exemplo.</span><span class="sxs-lookup"><span data-stu-id="0dd53-276">Here is an example.</span></span>

    ```json
    {
        "access_token": "{Returned_Token}",
        "token_type": "bearer",
        "expires_in": 1200
    }
    ```

### <a name="sample-request"></a><a name="inventory-visibility-sample-request"></a><span data-ttu-id="0dd53-277">Solicitação de exemplo</span><span class="sxs-lookup"><span data-stu-id="0dd53-277">Sample Request</span></span>

<span data-ttu-id="0dd53-278">Para sua referência, veja aqui um exemplo de solicitação de HTTP. Você pode usar qualquer ferramenta ou linguagem de programação para enviar essa solicitação, como ``Postman``.</span><span class="sxs-lookup"><span data-stu-id="0dd53-278">For your reference, here is a sample http request, you can use any tools or coding language to send this request, such as  ``Postman``.</span></span>

```json
# Url
# replace {RegionShortName} and {EnvironmentId} with your value
https://inventoryservice.{RegionShortName}-il301.gateway.prod.island.powerapps.com/api/environment/{EnvironmentId}/onhand

# Method
Post

# Header
# replace {access_token} with the one get from security service
Api-version: "1.0"
Content-Type: "application/json"
Authorization: "Bearer {access_token}"

# Body
{
    "id": "id-bike-0001",
    "organizationId": "usmf",
    "productId": "Bike",
    "quantities": {
        "pos": {
            "inbound": 5
        }  
    },
    "dimensions": {
        "SizeId": "Small",
        "ColorId": "Red",
        "SiteId": "1",
        "LocationId": "11"
    }
}
```

### <a name="configure-the-inventory-visibility-api"></a><a name="inventory-visibility-configuration"></a><span data-ttu-id="0dd53-279">Configurar a API da Visibilidade de Estoque</span><span class="sxs-lookup"><span data-stu-id="0dd53-279">Configure the Inventory Visibility API</span></span>

<span data-ttu-id="0dd53-280">Antes de usar o serviço, você deve concluir as configurações descritas nas subseções a seguir.</span><span class="sxs-lookup"><span data-stu-id="0dd53-280">Before using the service, you must complete the configurations described in the following subsections.</span></span> <span data-ttu-id="0dd53-281">A configuração pode variar com base nos detalhes do seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="0dd53-281">The configuration may vary based on the details of your environment.</span></span> <span data-ttu-id="0dd53-282">Ela inclui principalmente quatro partes:</span><span class="sxs-lookup"><span data-stu-id="0dd53-282">It primarily includes four parts:</span></span>

- [<span data-ttu-id="0dd53-283">Particionamento</span><span class="sxs-lookup"><span data-stu-id="0dd53-283">Partitioning</span></span>](#partitioning)
- [<span data-ttu-id="0dd53-284">Configurações de dimensões</span><span class="sxs-lookup"><span data-stu-id="0dd53-284">Dimension configurations</span></span>](#dimension-configurations)
- [<span data-ttu-id="0dd53-285">Indexando</span><span class="sxs-lookup"><span data-stu-id="0dd53-285">Indexing</span></span>](#indexing)
- [<span data-ttu-id="0dd53-286">Medida personalizada</span><span class="sxs-lookup"><span data-stu-id="0dd53-286">Custom measurement</span></span>](#custom-measurement)

#### <a name="partitioning"></a><span data-ttu-id="0dd53-287">Particionamento</span><span class="sxs-lookup"><span data-stu-id="0dd53-287">Partitioning</span></span>

<span data-ttu-id="0dd53-288">O particionamento pode influenciar significativamente o desempenho da API da Visibilidade de Estoque.</span><span class="sxs-lookup"><span data-stu-id="0dd53-288">Partitioning can significantly influence the performance of the Inventory Visibility API.</span></span> <span data-ttu-id="0dd53-289">É uma boa ideia definir um esquema que permita pequenos agrupamentos de dados e, ao mesmo tempo, permita consultas de dados significativas.</span><span class="sxs-lookup"><span data-stu-id="0dd53-289">It's a good idea to define a scheme that allows for small groupings of data while still allowing for meaningful data queries.</span></span>

<span data-ttu-id="0dd53-290">A `organizationId` (`dataAreaId` no Supply Chain Management) sempre fará parte do particionamento e, por padrão, a Visibilidade de Estoque é configurada para particionar por dimensões como *Local + Localização*.</span><span class="sxs-lookup"><span data-stu-id="0dd53-290">The `organizationId` (`dataAreaId` in Supply Chain Management) will always be part of the partitioning, and by default Inventory Visibility is set to partition by dimensions as *Site + Location*.</span></span> <span data-ttu-id="0dd53-291">Isso significa que o serviço sempre deve ser consultado com essas dimensões definidas nos filtros.</span><span class="sxs-lookup"><span data-stu-id="0dd53-291">This means that the service must always be queried with these dimensions defined on the filters.</span></span>

> [!NOTE]
> <span data-ttu-id="0dd53-292">*Local* e *Localização* são duas dimensões padrão gerais na Visibilidade de Estoque.</span><span class="sxs-lookup"><span data-stu-id="0dd53-292">*Site* and *Location* are two general default dimensions in Inventory Visibility.</span></span> <span data-ttu-id="0dd53-293">No Supply Chain Management, essas dimensões são chamadas de *Local* (`InventSiteId`) e *Depósito* (`InventLocationId`)</span><span class="sxs-lookup"><span data-stu-id="0dd53-293">In Supply Chain Management, those dimensions are called *Site* (`InventSiteId`) and *Warehouse* (`InventLocationId`)</span></span>

### <a name="dimension-configurations"></a><span data-ttu-id="0dd53-294">Configurações de dimensões</span><span class="sxs-lookup"><span data-stu-id="0dd53-294">Dimension configurations</span></span>

<span data-ttu-id="0dd53-295">A Visibilidade de Estoque fornecerá uma lista de dimensões padrão gerais para habilitar a integração de sistemas de várias fontes.</span><span class="sxs-lookup"><span data-stu-id="0dd53-295">Inventory Visibility will provide a list of general default dimensions to enable the multiple source system integration.</span></span>

<span data-ttu-id="0dd53-296">A tabela a seguir lista as dimensões de estoque que serão os nomes de dimensão padrão na Visibilidade de Estoque.</span><span class="sxs-lookup"><span data-stu-id="0dd53-296">The following table lists the inventory dimensions that will be the default dimension names in Inventory Visibility.</span></span>

| <span data-ttu-id="0dd53-297">Tipo de dimensão</span><span class="sxs-lookup"><span data-stu-id="0dd53-297">Dimension type</span></span> | <span data-ttu-id="0dd53-298">Nome da dimensão</span><span class="sxs-lookup"><span data-stu-id="0dd53-298">Dimension name</span></span> |
|---|---|
| <span data-ttu-id="0dd53-299">Produto</span><span class="sxs-lookup"><span data-stu-id="0dd53-299">Product</span></span> | `ColorId` |
| <span data-ttu-id="0dd53-300">Produto</span><span class="sxs-lookup"><span data-stu-id="0dd53-300">Product</span></span> | `SizeId` |
| <span data-ttu-id="0dd53-301">Produto</span><span class="sxs-lookup"><span data-stu-id="0dd53-301">Product</span></span> | `StyleId` |
| <span data-ttu-id="0dd53-302">Produto</span><span class="sxs-lookup"><span data-stu-id="0dd53-302">Product</span></span> | `ConfigId` |
| <span data-ttu-id="0dd53-303">Rastreamento</span><span class="sxs-lookup"><span data-stu-id="0dd53-303">Tracking</span></span> | `BatchId` |
| <span data-ttu-id="0dd53-304">Rastreamento</span><span class="sxs-lookup"><span data-stu-id="0dd53-304">Tracking</span></span> | `SerialId` |
| <span data-ttu-id="0dd53-305">Localização</span><span class="sxs-lookup"><span data-stu-id="0dd53-305">Location</span></span> | `LocationId` |
| <span data-ttu-id="0dd53-306">Localização</span><span class="sxs-lookup"><span data-stu-id="0dd53-306">Location</span></span> | `SiteId` |
| <span data-ttu-id="0dd53-307">Status do Estoque</span><span class="sxs-lookup"><span data-stu-id="0dd53-307">Inventory Status</span></span> | `StatusId` |
| <span data-ttu-id="0dd53-308">Específico do Depósito</span><span class="sxs-lookup"><span data-stu-id="0dd53-308">Warehouse Specific</span></span> | `WMSLocationId` |
| <span data-ttu-id="0dd53-309">Específico do Depósito</span><span class="sxs-lookup"><span data-stu-id="0dd53-309">Warehouse Specific</span></span> | `WMSPalletId` |
| <span data-ttu-id="0dd53-310">Específico do Depósito</span><span class="sxs-lookup"><span data-stu-id="0dd53-310">Warehouse Specific</span></span> | `LicensePlateId` |

> [!NOTE]
> <span data-ttu-id="0dd53-311">O tipo de dimensão listado na tabela anterior é somente para referência.</span><span class="sxs-lookup"><span data-stu-id="0dd53-311">The dimension type listed in the previous table is for reference only.</span></span> <span data-ttu-id="0dd53-312">Não é necessário definir o tipo de dimensão na Visibilidade de Estoque.</span><span class="sxs-lookup"><span data-stu-id="0dd53-312">You don't need to define the dimension type in Inventory Visibility.</span></span>

<span data-ttu-id="0dd53-313">Se uma dimensão personalizada existir e precisar fluir para um valor padrão quando consumida pela Visibilidade de Estoque, você poderá configurar o nome **Dimensão personalizada** na Visibilidade de Estoque.</span><span class="sxs-lookup"><span data-stu-id="0dd53-313">If a custom dimension exists and needs to flow to a default value when consumed by Inventory Visibility, you can configure the **Custom dimension** name in Inventory Visibility.</span></span>

<span data-ttu-id="0dd53-314">Os sistemas externos acessam a Visibilidade de Estoque por meio de APIs RESTful que habilitam informações de disponibilidade sobre determinados conjuntos de dimensões a serem consultadas.</span><span class="sxs-lookup"><span data-stu-id="0dd53-314">External systems access Inventory Visibility through RESTful APIs that enable on-hand information on given sets of dimensions to be queried.</span></span> <span data-ttu-id="0dd53-315">Para a integração, a Visibilidade de Estoque permite configurar a *fonte de dados do canal externo* e a dimensão de origem para as *dimensões de destino* na Visibilidade de Estoque.</span><span class="sxs-lookup"><span data-stu-id="0dd53-315">For the integration, Inventory Visibility enables you to configure the *external channel data source* and the source dimension to the *target dimensions* in Inventory Visibility.</span></span>

<span data-ttu-id="0dd53-316">As dimensões de destino devem ser uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="0dd53-316">The target dimensions should be one of the following:</span></span>

- <span data-ttu-id="0dd53-317">Dimensões padrão na Visibilidade de Estoque</span><span class="sxs-lookup"><span data-stu-id="0dd53-317">Default dimensions in Inventory Visibility</span></span>
- <span data-ttu-id="0dd53-318">Dimensões personalizadas</span><span class="sxs-lookup"><span data-stu-id="0dd53-318">Custom dimensions</span></span>

<span data-ttu-id="0dd53-319">A finalidade da configuração de dimensões é padronizar a integração de vários sistemas para a consulta em dimensões e o evento de lançamento com dimensões.</span><span class="sxs-lookup"><span data-stu-id="0dd53-319">The purpose of dimension configuration is to standardize the multi-system integration for the query on dimensions and the posting event with dimensions.</span></span>

#### <a name="indexing"></a><span data-ttu-id="0dd53-320">Indexando</span><span class="sxs-lookup"><span data-stu-id="0dd53-320">Indexing</span></span>

<span data-ttu-id="0dd53-321">Na maioria das vezes, a consulta de estoque disponível não só estará no nível "total" mais alto, mas talvez você queira ver resultados agregados com base nas dimensões de estoque.</span><span class="sxs-lookup"><span data-stu-id="0dd53-321">Most of the time, the inventory on-hand query will not only be on the highest "total" level, but you may want to see results aggregated based on the inventory dimensions.</span></span>

<span data-ttu-id="0dd53-322">A Visibilidade de Estoque fornece flexibilidade, permitindo que você configure os índices, que se baseiam na dimensão ou na combinação das dimensões.</span><span class="sxs-lookup"><span data-stu-id="0dd53-322">Inventory Visibility provides flexibility by allowing you to set up the indexes, which are based on the dimension or the combination of the dimensions.</span></span>

> [!NOTE]
> <span data-ttu-id="0dd53-323">No momento, só é possível configurar índices para, no máximo, cinco.</span><span class="sxs-lookup"><span data-stu-id="0dd53-323">Currently, you can only configure indexes to a maximum of five.</span></span> <span data-ttu-id="0dd53-324">É necessário considerar cuidadosamente qual dimensão ou combinação de dimensões você usará antes da implementação para garantir que ela atenderá às suas necessidades comerciais.</span><span class="sxs-lookup"><span data-stu-id="0dd53-324">You need to carefully consider which dimension or dimension combination you will use before the implementation to ensure that it will meet your business needs.</span></span> <span data-ttu-id="0dd53-325">Por exemplo, se você quiser consultar produtos da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="0dd53-325">For example, if you want to query products as follows:</span></span>

- <span data-ttu-id="0dd53-326">Consultar o produto agregado disponível por meio das dimensões *Cor* e *Tamanho*.</span><span class="sxs-lookup"><span data-stu-id="0dd53-326">Query the aggregated product on-hand by the *Color* and *Size* dimensions.</span></span>
- <span data-ttu-id="0dd53-327">Em alguns casos, você só deseja consultar o produto no total.</span><span class="sxs-lookup"><span data-stu-id="0dd53-327">In some cases, you just want to query on the product in total.</span></span>

<span data-ttu-id="0dd53-328">Você teria dois índices definidos da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="0dd53-328">You would have two indexes defined as the following:</span></span>

- `["ColorId", "SizeId"]`
- `[]`

<span data-ttu-id="0dd53-329">O colchete vazio agregará com base na ID do produto na partição.</span><span class="sxs-lookup"><span data-stu-id="0dd53-329">The empty bracket will aggregate based on the product ID within the partition.</span></span>

<span data-ttu-id="0dd53-330">A indexação define como você pode agrupar os resultados com base na configuração de consulta `groupBy`.</span><span class="sxs-lookup"><span data-stu-id="0dd53-330">The indexing defines how you can group your results based on the `groupBy` query setting.</span></span> <span data-ttu-id="0dd53-331">Nesse caso, se você não definir nenhum valor `groupBy`, obterá totais por `productid`.</span><span class="sxs-lookup"><span data-stu-id="0dd53-331">In this case if you don't define any `groupBy` values, you'll get totals by `productid`.</span></span> <span data-ttu-id="0dd53-332">Caso contrário, se você definir `groupBy` como `groupBy=ColorId&groupBy=SizeId`, obterá várias linhas retornadas, com base nas diferentes combinações de cor e tamanho no sistema.</span><span class="sxs-lookup"><span data-stu-id="0dd53-332">Otherwise, if you define `groupBy` as `groupBy=ColorId&groupBy=SizeId`, you'll get multiple lines returned, based on the different color and size combinations in the system.</span></span>

<span data-ttu-id="0dd53-333">Você pode colocar os critérios de consulta no corpo da solicitação.</span><span class="sxs-lookup"><span data-stu-id="0dd53-333">You can put your query criteria in the request body.</span></span>

<span data-ttu-id="0dd53-334">Veja uma consulta de exemplo no produto com combinação de cor e tamanho.</span><span class="sxs-lookup"><span data-stu-id="0dd53-334">Here is a sample query on the product with color and size combination.</span></span>

```json
{
    "filters": {
        "OrganizationId": ["usmf"],
        "ProductId": ["MyProduct1", "MyProduct2"],
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

<span data-ttu-id="0dd53-335">No campo `filters`, somente o `ProductId` permite a inserção de vários valores no momento.</span><span class="sxs-lookup"><span data-stu-id="0dd53-335">For the `filters` field, currently only `ProductId` supports multiple values.</span></span> <span data-ttu-id="0dd53-336">Se o `ProductId` for uma matriz vazia, todos os produtos serão consultados.</span><span class="sxs-lookup"><span data-stu-id="0dd53-336">If the `ProductId` is an empty array, all products will be queried.</span></span>

#### <a name="custom-measurement"></a><span data-ttu-id="0dd53-337">Medida personalizada</span><span class="sxs-lookup"><span data-stu-id="0dd53-337">Custom measurement</span></span>

<span data-ttu-id="0dd53-338">As quantidades de medida padrão estão vinculadas ao Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="0dd53-338">The default measurement quantities are linked to Supply Chain Management.</span></span> <span data-ttu-id="0dd53-339">No entanto, talvez você deseje ter uma quantidade composta de uma combinação das medidas padrão.</span><span class="sxs-lookup"><span data-stu-id="0dd53-339">However, you may want to have a quantity that is made up of a combination of the default measurements.</span></span> <span data-ttu-id="0dd53-340">Para isso, você pode ter uma configuração de quantidades personalizadas, que será adicionada à saída das consultas de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="0dd53-340">To do this, you can have a configuration of custom quantities, which will be added to the output of the on-hand queries.</span></span>

<span data-ttu-id="0dd53-341">A funcionalidade simplesmente permite definir um conjunto de medidas que será adicionado e/ou um conjunto de medidas que será subtraído para formar a medida personalizada.</span><span class="sxs-lookup"><span data-stu-id="0dd53-341">The functionality simply allows you to define a set of measures that will be added, and/or a set of measures that will be subtracted, in order to form the custom measurement.</span></span>

<span data-ttu-id="0dd53-342">Por exemplo, com a seguinte condição de consulta, você configurará a quantidade de medidas personalizadas como `MyCustomAvailableforReservation` para ser consumida pelo sistema de consumo.</span><span class="sxs-lookup"><span data-stu-id="0dd53-342">For example, with the following query condition, you will configure the custom measurement quantity as `MyCustomAvailableforReservation` to be consumed by the consumption system.</span></span>

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



| <span data-ttu-id="0dd53-343">Sistema de consumo</span><span class="sxs-lookup"><span data-stu-id="0dd53-343">Consumption system</span></span> | <span data-ttu-id="0dd53-344">Medidas calculadas</span><span class="sxs-lookup"><span data-stu-id="0dd53-344">Calculated measurers</span></span> | <span data-ttu-id="0dd53-345">Fonte de dados</span><span class="sxs-lookup"><span data-stu-id="0dd53-345">Data source</span></span> | <span data-ttu-id="0dd53-346">Modificador</span><span class="sxs-lookup"><span data-stu-id="0dd53-346">Modifier</span></span> | <span data-ttu-id="0dd53-347">Tipo de cálculo do modificador</span><span class="sxs-lookup"><span data-stu-id="0dd53-347">Modifier calculation type</span></span> |
|---|---|---|---|---|
| `CustomChannel` | `MyCustomAvailableforReservation` | `fno` | `availphysical` | <span data-ttu-id="0dd53-348">Adição</span><span class="sxs-lookup"><span data-stu-id="0dd53-348">Addition</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `fno` | `orderedintotal` | <span data-ttu-id="0dd53-349">Adição</span><span class="sxs-lookup"><span data-stu-id="0dd53-349">Addition</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `fno` | `orderedreserved` | <span data-ttu-id="0dd53-350">Subtração</span><span class="sxs-lookup"><span data-stu-id="0dd53-350">Subtraction</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `mypos` | `inbound` | <span data-ttu-id="0dd53-351">Adição</span><span class="sxs-lookup"><span data-stu-id="0dd53-351">Addition</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `mypos` | `outbound` | <span data-ttu-id="0dd53-352">Subtração</span><span class="sxs-lookup"><span data-stu-id="0dd53-352">Subtraction</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `exterchannel` | `received` | <span data-ttu-id="0dd53-353">Adição</span><span class="sxs-lookup"><span data-stu-id="0dd53-353">Addition</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `exterchannel` | `scheduled` | <span data-ttu-id="0dd53-354">Adição</span><span class="sxs-lookup"><span data-stu-id="0dd53-354">Addition</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `exterchannel` | `issued` | <span data-ttu-id="0dd53-355">Subtração</span><span class="sxs-lookup"><span data-stu-id="0dd53-355">Subtraction</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `exterchannel` | `reserved` | <span data-ttu-id="0dd53-356">Subtração</span><span class="sxs-lookup"><span data-stu-id="0dd53-356">Subtraction</span></span> |

<span data-ttu-id="0dd53-357">Com isso, a consulta na quantidade de medidas personalizadas retornará a seguinte saída.</span><span class="sxs-lookup"><span data-stu-id="0dd53-357">With that, the query on the custom measurement quantity will return the following output.</span></span>

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

<span data-ttu-id="0dd53-358">A saída `MyCustomAvailableforReservation` se baseia na configuração de cálculo nas medidas personalizadas como:</span><span class="sxs-lookup"><span data-stu-id="0dd53-358">The `MyCustomAvailableforReservation` output is based on the calculation setting in the custom measurements as:</span></span>  
 <span data-ttu-id="0dd53-359">*100 + 50 + 80 + 90 + 30 &ndash; 10 &ndash; 20 &ndash; 60 &ndash; 40 = 220*</span><span class="sxs-lookup"><span data-stu-id="0dd53-359">*100 + 50 + 80 + 90 + 30 &ndash; 10 &ndash; 20 &ndash; 60 &ndash; 40 = 220*</span></span>

### <a name="posting-on-hand-changes"></a><span data-ttu-id="0dd53-360">Lançar alterações de disponibilidade</span><span class="sxs-lookup"><span data-stu-id="0dd53-360">Posting on-hand changes</span></span>

<span data-ttu-id="0dd53-361">A URL exata na qual o evento será lançado dependerá da sua região geográfica.</span><span class="sxs-lookup"><span data-stu-id="0dd53-361">The exact URL that the event will be posted to will depend on your geographical region.</span></span> <span data-ttu-id="0dd53-362">Ela terá a forma:</span><span class="sxs-lookup"><span data-stu-id="0dd53-362">It will take the form:</span></span>

`https://{serviceURL}/api/environment/{environmentId}/onhand`

<span data-ttu-id="0dd53-363">Quando autenticada, essa URL pode ser usada junto com o método HTTP `POST` para enviar eventos de alteração de disponibilidade para o serviço.</span><span class="sxs-lookup"><span data-stu-id="0dd53-363">When authenticated, this URL can be used along with the HTTP `POST` method to send on-hand change events to the service.</span></span>

<span data-ttu-id="0dd53-364">Um cabeçalho especial é usado para a comunicação com os serviços do Dynamics 365 por meio de solicitações HTTP, indicando a ID de ambiente da instância do Supply Chain Management à qual os dados estão vinculados.</span><span class="sxs-lookup"><span data-stu-id="0dd53-364">A special header is used for communicating with Dynamics 365 services through HTTP requests, denoting the environment ID of the Supply Chain Management instance the data is linked to.</span></span> <span data-ttu-id="0dd53-365">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="0dd53-365">For example:</span></span>

`x-ms-environment-id: 2db79622-f97a-4d64-9844-d12efed41796`

#### <a name="posting-on-hand-changes-query-example-1"></a><span data-ttu-id="0dd53-366">Exemplo de consulta de lançamento de alterações de disponibilidade 1</span><span class="sxs-lookup"><span data-stu-id="0dd53-366">Posting on-hand changes query example 1</span></span>

<span data-ttu-id="0dd53-367">Este exemplo mostra um cenário no qual você definirá a configuração de dimensões no Power Apps.</span><span class="sxs-lookup"><span data-stu-id="0dd53-367">This example shows a scenario where you will set up the dimension configuration in Power Apps.</span></span>

<span data-ttu-id="0dd53-368">Use a seguinte consulta para configurar o mapeamento de dimensões no Power Apps:</span><span class="sxs-lookup"><span data-stu-id="0dd53-368">Use the following query to configure the dimension mapping in Power Apps:</span></span>

```json
{
    "PosSizeId": "SizeId",
    "PosColorId": "ColorId",
    "PosSiteId": "SiteId",
    "PosLocationId": "LocationId"
}
```

<span data-ttu-id="0dd53-369">Agora, você pode especificar a `dimensionDataSource` e usar dimensões personalizadas nas suas consultas.</span><span class="sxs-lookup"><span data-stu-id="0dd53-369">Now you can specify the `dimensionDataSource` and use custom dimensions in your queries.</span></span> <span data-ttu-id="0dd53-370">O sistema converterá automaticamente as dimensões personalizadas em dimensões base.</span><span class="sxs-lookup"><span data-stu-id="0dd53-370">The system will automatically convert custom dimensions to base dimensions.</span></span>

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

#### <a name="posting-on-hand-changes-query-example-2"></a><span data-ttu-id="0dd53-371">Exemplo de consulta de lançamento de alterações de disponibilidade 2</span><span class="sxs-lookup"><span data-stu-id="0dd53-371">Posting on-hand changes query example 2</span></span>

<span data-ttu-id="0dd53-372">Este exemplo mostra um cenário em que não há mapeamentos definidos para a configuração de dimensões no Power Apps, portanto, o lançamento também deve usar as dimensões base.</span><span class="sxs-lookup"><span data-stu-id="0dd53-372">This example shows a scenario where no mappings are set up for the dimension configuration in Power Apps, so the posting should also use the base dimensions.</span></span> <span data-ttu-id="0dd53-373">Todas as dimensões devem ser dimensões base quando o campo `dimensionDataSource` é nulo, vazio ou um espaço em branco.</span><span class="sxs-lookup"><span data-stu-id="0dd53-373">All dimensions must be base dimensions when the `dimensionDataSource` field is null, empty, or whitespace.</span></span>

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

#### <a name="json-document-field-properties"></a><span data-ttu-id="0dd53-374">Propriedades de campo do documento JSON</span><span class="sxs-lookup"><span data-stu-id="0dd53-374">JSON document field properties</span></span>

<span data-ttu-id="0dd53-375">Os campos dos exemplos de consulta JSON fornecidos anteriormente têm as propriedades listadas na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="0dd53-375">The fields from the JSON query examples provided previously have the properties listed in the following table.</span></span>

| <span data-ttu-id="0dd53-376">ID do campo</span><span class="sxs-lookup"><span data-stu-id="0dd53-376">Field ID</span></span> | <span data-ttu-id="0dd53-377">descrição</span><span class="sxs-lookup"><span data-stu-id="0dd53-377">Description</span></span> |
|---|---|
| `id` | <span data-ttu-id="0dd53-378">Uma ID exclusiva para o evento de alteração específico.</span><span class="sxs-lookup"><span data-stu-id="0dd53-378">A unique ID for the specific change event.</span></span> <span data-ttu-id="0dd53-379">Essa ID é usada para garantir que, se a comunicação com o serviço falhar durante o lançamento, o reenvio do evento não resultará no mesmo evento sendo contado duas vezes no sistema.</span><span class="sxs-lookup"><span data-stu-id="0dd53-379">This ID is used to ensure that if communication with the service fails during posting, resubmitting the event would not result in the same event being counted twice in the system.</span></span> |
| `organizationId` | <span data-ttu-id="0dd53-380">O identificador da organização vinculada ao evento.</span><span class="sxs-lookup"><span data-stu-id="0dd53-380">The identifier of the organization linked to the event.</span></span> <span data-ttu-id="0dd53-381">Isso é mapeado para as IDs de áreas de dados ou organizações do Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="0dd53-381">This maps to Supply Chain Management organizations or data area IDs.</span></span> |
| `productId` | <span data-ttu-id="0dd53-382">O identificador do produto em questão.</span><span class="sxs-lookup"><span data-stu-id="0dd53-382">The identifier of the product in question.</span></span> |
| `quantity` | <span data-ttu-id="0dd53-383">A quantidade pela qual a disponibilidade precisa ser alterada.</span><span class="sxs-lookup"><span data-stu-id="0dd53-383">The quantity by which the on-hand needs to be changed.</span></span> <span data-ttu-id="0dd53-384">Se, por exemplo, 10 novos bagels forem adicionados a uma prateleira, esse valor será 10.</span><span class="sxs-lookup"><span data-stu-id="0dd53-384">If, for instance, 10 new bagels were added to a shelf, this value would be 10.</span></span> <span data-ttu-id="0dd53-385">Se 3 bagels forem removidos da prateleira ou vendidos, esse valor será -3.</span><span class="sxs-lookup"><span data-stu-id="0dd53-385">If 3 bagels were then removed from the shelf or sold, this value would be -3.</span></span> |
| `dimensionDataSource` | <span data-ttu-id="0dd53-386">A fonte de dados das dimensões usadas no evento e na consulta de alteração de lançamento.</span><span class="sxs-lookup"><span data-stu-id="0dd53-386">The data source of the dimensions used in the posting change event and query.</span></span> <span data-ttu-id="0dd53-387">Se você especificar a fonte de dados, poderá usar as dimensões personalizadas da fonte de dados especificada.</span><span class="sxs-lookup"><span data-stu-id="0dd53-387">If you specify the data source, you can use the custom dimensions from the specified data source.</span></span> <span data-ttu-id="0dd53-388">Com a configuração de dimensões, a Visibilidade de Estoque pode mapear as dimensões personalizadas para as dimensões padrão gerais.</span><span class="sxs-lookup"><span data-stu-id="0dd53-388">With the dimension configuration, Inventory Visibility can map the custom dimensions to the general default dimensions.</span></span> <span data-ttu-id="0dd53-389">Se a `dimensionDataSource` não estiver especificada, você só poderá usar as dimensões padrão gerais nas suas consultas.</span><span class="sxs-lookup"><span data-stu-id="0dd53-389">If the `dimensionDataSource` is not specified, you can only use the general default dimensions in your queries.</span></span>   |
| `dimensions` | <span data-ttu-id="0dd53-390">Um recipiente dinâmico de pares de chave/valor.</span><span class="sxs-lookup"><span data-stu-id="0dd53-390">A dynamic bag of key/value pairs.</span></span> <span data-ttu-id="0dd53-391">Eles serão mapeados para algumas das dimensões no Supply Chain Management, mas você também pode adicionar dimensões personalizadas (como *Origem*) que podem indicar se o evento é proveniente do Supply Chain Management ou de um sistema externo.</span><span class="sxs-lookup"><span data-stu-id="0dd53-391">These will map to some of the dimensions in Supply Chain Management, but you could also add custom dimensions (like *Source*) that may denote if the event was coming from Supply Chain Management or an external system.</span></span> |

### <a name="querying-current-on-hand"></a><span data-ttu-id="0dd53-392">Consultar a disponibilidade atual</span><span class="sxs-lookup"><span data-stu-id="0dd53-392">Querying current on-hand</span></span>

<span data-ttu-id="0dd53-393">O ponto de extremidade para consultar a disponibilidade atual terá uma URL semelhante:</span><span class="sxs-lookup"><span data-stu-id="0dd53-393">The endpoint for querying the current on-hand will have a similar URL:</span></span>

`https://{serviceURL}/api/environment/{environmentId}/onhand/indexquery`

<span data-ttu-id="0dd53-394">Ela será consultada com o método HTTP `POST`.</span><span class="sxs-lookup"><span data-stu-id="0dd53-394">It will be queried with the HTTP `POST` method.</span></span>

#### <a name="current-on-hand-query-example-1"></a><span data-ttu-id="0dd53-395">Exemplo de consulta da disponibilidade atual 1</span><span class="sxs-lookup"><span data-stu-id="0dd53-395">Current on-hand query example 1</span></span>

<span data-ttu-id="0dd53-396">Este exemplo mostra um cenário no qual você já concluiu a configuração de dimensões no Power Apps.</span><span class="sxs-lookup"><span data-stu-id="0dd53-396">This example shows a scenario where you have already completed the dimension configuration in Power Apps.</span></span>

<span data-ttu-id="0dd53-397">Use a seguinte consulta para configurar o mapeamento de dimensões no Power Apps:</span><span class="sxs-lookup"><span data-stu-id="0dd53-397">Use the following query to configure the dimension mapping in Power Apps:</span></span>

```json
{
    "PosSizeId": "SizeId",
    "PosColorId": "ColorId",
    "PosSiteId": "SiteId",
    "PosLocationId": "LocationId"
}
```

<span data-ttu-id="0dd53-398">Agora, você pode especificar a `dimensionDataSource` e usar dimensões personalizadas nas suas consultas.</span><span class="sxs-lookup"><span data-stu-id="0dd53-398">Now you can specify the `dimensionDataSource` and use custom dimensions in your queries.</span></span> <span data-ttu-id="0dd53-399">O sistema converterá automaticamente as dimensões personalizadas em dimensões base.</span><span class="sxs-lookup"><span data-stu-id="0dd53-399">The system will automatically convert custom dimensions to base dimensions.</span></span> <span data-ttu-id="0dd53-400">Você pode especificar a `DimensionDataSource` em `filters` e especificar dimensões personalizadas em `filters` e `groupByValues`.</span><span class="sxs-lookup"><span data-stu-id="0dd53-400">You can specify the `DimensionDataSource` in `filters` and specify custom dimensions in both `filters` and `groupByValues`.</span></span> <span data-ttu-id="0dd53-401">O sistema converterá automaticamente as dimensões personalizadas em dimensões base.</span><span class="sxs-lookup"><span data-stu-id="0dd53-401">The system will automatically convert custom dimensions to base dimensions.</span></span>

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

#### <a name="current-on-hand-query-example-2"></a><span data-ttu-id="0dd53-402">Exemplo de consulta da disponibilidade atual 2</span><span class="sxs-lookup"><span data-stu-id="0dd53-402">Current on-hand query example 2</span></span>

<span data-ttu-id="0dd53-403">Este exemplo mostra um cenário em que não há mapeamentos definidos para a configuração de dimensões no Power Apps, portanto, o lançamento também deve usar as dimensões base.</span><span class="sxs-lookup"><span data-stu-id="0dd53-403">This example shows a scenario where no mappings are set up for the dimension configuration in Power Apps, so the posting should also use the base dimensions.</span></span> <span data-ttu-id="0dd53-404">Todas as dimensões devem ser dimensões base quando o campo `dimensionDataSource`, em `filters`, é nulo, vazio ou um espaço em branco.</span><span class="sxs-lookup"><span data-stu-id="0dd53-404">All dimensions must be base dimensions when the `dimensionDataSource` field, under `filters` is null, empty, or whitespace.</span></span>

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

#### <a name="example-return-result"></a><span data-ttu-id="0dd53-405">Exemplo de retorno de resultado</span><span class="sxs-lookup"><span data-stu-id="0dd53-405">Example return result</span></span>

<span data-ttu-id="0dd53-406">As consultas mostradas nos exemplos anteriores poderiam retornar um resultado como este.</span><span class="sxs-lookup"><span data-stu-id="0dd53-406">The queries shown in the previous examples could return a result like this.</span></span>

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

<span data-ttu-id="0dd53-407">Observe que os campos de quantidades estão estruturados como um dicionário de medidas e seus valores associados.</span><span class="sxs-lookup"><span data-stu-id="0dd53-407">Note that the quantities fields are structured as a dictionary of measures and their associated values.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]