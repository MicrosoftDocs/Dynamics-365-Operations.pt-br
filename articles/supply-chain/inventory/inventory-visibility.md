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
ms.openlocfilehash: 84f5e949f0c81f840c8a9086d05bbcfc576e42aa
ms.sourcegitcommit: b67665ed689c55df1a67d1a7840947c3977d600c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2021
ms.locfileid: "6016997"
---
# <a name="inventory-visibility-add-in"></a><span data-ttu-id="c3a23-103">Suplemento Visibilidade de Estoque</span><span class="sxs-lookup"><span data-stu-id="c3a23-103">Inventory Visibility Add-in</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]
[!INCLUDE [cc-data-platform-banner](../../includes/cc-data-platform-banner.md)]

<span data-ttu-id="c3a23-104">O Suplemento Visibilidade de Estoque é um microsserviço independente e altamente escalonável que permite o rastreamento de estoque disponível em tempo real, oferecendo, assim, uma visão global da visibilidade de estoque.</span><span class="sxs-lookup"><span data-stu-id="c3a23-104">The Inventory Visibility Add-in is an independent and highly scalable microservice that enables real-time on-hand inventory tracking, thus providing a global view of inventory visibility.</span></span>

<span data-ttu-id="c3a23-105">Todas as informações relacionadas ao estoque disponível são exportadas para o serviço quase em tempo real por meio de uma integração SQL de nível baixo.</span><span class="sxs-lookup"><span data-stu-id="c3a23-105">All information that relates to on-hand inventory is exported to the service in near real-time through low-level SQL integration.</span></span> <span data-ttu-id="c3a23-106">Os sistemas externos acessam o serviço por meio de APIs RESTful para consultar informações disponíveis sobre determinados conjuntos de dimensões, recuperando, dessa forma, uma lista de posições disponíveis.</span><span class="sxs-lookup"><span data-stu-id="c3a23-106">External systems access the service through RESTful APIs to query on-hand information on given sets of dimensions, thus retrieving a list of available on-hand positions.</span></span>

<span data-ttu-id="c3a23-107">A Visibilidade de Estoque é um microsserviço criado no Microsoft Dataverse, o que significa que você pode estendê-lo criando Power Apps e aplicando o Power BI para fornecer funcionalidade personalizada para atender aos seus requisitos de negócios.</span><span class="sxs-lookup"><span data-stu-id="c3a23-107">Inventory Visibility is a microservice built on Microsoft Dataverse, which means you can extend it by building Power Apps and applying Power BI to provide customized functionality to meet your business requirements.</span></span> <span data-ttu-id="c3a23-108">Também é possível atualizar o índice para fazer consultas de estoque.</span><span class="sxs-lookup"><span data-stu-id="c3a23-108">It is also possible to upgrade the index to do inventory queries.</span></span>

<span data-ttu-id="c3a23-109">A Visibilidade de Estoque fornece opções de configuração que permitem a integração com vários sistemas de terceiros.</span><span class="sxs-lookup"><span data-stu-id="c3a23-109">Inventory Visibility provides configuration options that let it integrate with multiple third-party systems.</span></span> <span data-ttu-id="c3a23-110">Ela oferece suporte à dimensão de estoque padronizada, à extensibilidade personalizada e a quantidades calculadas padronizadas e configuráveis.</span><span class="sxs-lookup"><span data-stu-id="c3a23-110">It supports the standardized inventory dimension, customized extensibility, and standardized, configurable calculated quantities.</span></span>

<span data-ttu-id="c3a23-111">Este tópico descreve como instalar e configurar o Suplemento Visibilidade de Estoque para Dynamics 365 Supply Chain Management e como usar sua interface de programação de aplicativo (API).</span><span class="sxs-lookup"><span data-stu-id="c3a23-111">This topic describes how to install and configure the Inventory Visibility Add-in for Dynamics 365 Supply Chain Management, and how to use its application programming interface (API).</span></span>

## <a name="install-the-inventory-visibility-add-in"></a><span data-ttu-id="c3a23-112">Instalar o Suplemento Visibilidade de Estoque</span><span class="sxs-lookup"><span data-stu-id="c3a23-112">Install the Inventory Visibility Add-in</span></span>

<span data-ttu-id="c3a23-113">É necessário instalar o Suplemento Visibilidade de Estoque usando o Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="c3a23-113">You need to install the Inventory Visibility Add-in using Microsoft Dynamics Lifecycle Services (LCS).</span></span> <span data-ttu-id="c3a23-114">O LCS é um portal de colaboração que fornece um ambiente e um conjunto de serviços regularmente atualizados que ajudam a gerenciar o ciclo de vida dos seus aplicativos do Dynamics 365 Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="c3a23-114">LCS is a collaboration portal that provides an environment and a set of regularly updated services that help you manage the application lifecycle of your Dynamics 365 Finance and Operations apps.</span></span>

<span data-ttu-id="c3a23-115">Para obter mais informações, consulte [Recursos do Lifecycle Services](../../fin-ops-core/dev-itpro/lifecycle-services/lcs.md).</span><span class="sxs-lookup"><span data-stu-id="c3a23-115">For more information, see [Lifecycle Services resources](../../fin-ops-core/dev-itpro/lifecycle-services/lcs.md).</span></span>

### <a name="inventory-visibility-add-in-prerequisites"></a><span data-ttu-id="c3a23-116">Pré-requisitos do complemento Visibilidade do inventário</span><span class="sxs-lookup"><span data-stu-id="c3a23-116">Inventory Visibility Add-in prerequisites</span></span>

<span data-ttu-id="c3a23-117">Antes de instalar o Suplemento Visibilidade de Estoque, você deve fazer o seguinte:</span><span class="sxs-lookup"><span data-stu-id="c3a23-117">Before you install the Inventory Visibility Add-in, you must do the following:</span></span>

- <span data-ttu-id="c3a23-118">Obter um projeto de implementação do LCS com, pelo menos, um ambiente implantado.</span><span class="sxs-lookup"><span data-stu-id="c3a23-118">Obtain an LCS implementation project with at least one environment deployed.</span></span>
- <span data-ttu-id="c3a23-119">Verifique se os pré-requisitos para a configuração de suplementos fornecidos na [Visão geral dos suplementos](../../fin-ops-core/dev-itpro/power-platform/add-ins-overview.md) foram concluídos.</span><span class="sxs-lookup"><span data-stu-id="c3a23-119">Make sure that the prerequisites for setting up add-ins provided in the [Add-ins overview](../../fin-ops-core/dev-itpro/power-platform/add-ins-overview.md) have been completed.</span></span> <span data-ttu-id="c3a23-120">A visibilidade de estoque não exige link de gravação dupla.</span><span class="sxs-lookup"><span data-stu-id="c3a23-120">Inventory Visibility doesn't require dual-write linking.</span></span>
- <span data-ttu-id="c3a23-121">Entre em contato com a equipe de visibilidade de estoque em [inventvisibilitysupp@microsoft.com](mailto:inventvisibilitysupp@microsoft.com) para obter os três seguintes arquivos necessários:</span><span class="sxs-lookup"><span data-stu-id="c3a23-121">Contact the Inventory Visibility Team at [inventvisibilitysupp@microsoft.com](mailto:inventvisibilitysupp@microsoft.com) to get the following three required files:</span></span>
  - `Inventory Visibility Dataverse Solution.zip`
  - `Inventory Visibility Configuration Trigger.zip`
  - <span data-ttu-id="c3a23-122">`Inventory Visibility Integration.zip` (se a versão do Supply Chain Management que você está executando for anterior à versão 10.0.18)</span><span class="sxs-lookup"><span data-stu-id="c3a23-122">`Inventory Visibility Integration.zip` (if the version of Supply Chain Management that you're running is earlier than version 10.0.18)</span></span>
- <span data-ttu-id="c3a23-123">Outra opção é entrar em contato com a Equipe do Visibilidade do inventário em [inventvisibilitysupp@microsoft.com](mailto:inventvisibilitysupp@microsoft.com) para obter os pacotes do Package Deployer.</span><span class="sxs-lookup"><span data-stu-id="c3a23-123">Alternatively, contact the Inventory Visibility Team at [inventvisibilitysupp@microsoft.com](mailto:inventvisibilitysupp@microsoft.com) to get the package deployer packages.</span></span> <span data-ttu-id="c3a23-124">Esses pacotes podem ser usados por uma ferramenta oficial do Package Deployer.</span><span class="sxs-lookup"><span data-stu-id="c3a23-124">These packages can be used by an official package deployer tool.</span></span>
  - `InventoryServiceBase.PackageDeployer.zip`
  - <span data-ttu-id="c3a23-125">`InventoryServiceApplication.PackageDeployer.zip` (este pacote contém todas as alterações do pacote `InventoryServiceBase`, além de componentes de UI adicionais do aplicativo)</span><span class="sxs-lookup"><span data-stu-id="c3a23-125">`InventoryServiceApplication.PackageDeployer.zip` (this package contains all of the changes in the `InventoryServiceBase` package, plus additional UI application components)</span></span>
- <span data-ttu-id="c3a23-126">Siga as instruções descritas em [Início rápido: registre um aplicativo com a plataforma de identidade da Microsoft](/azure/active-directory/develop/quickstart-register-app) para registrar um aplicativo e adicionar um segredo do cliente ao AAD com sua assinatura do Azure.</span><span class="sxs-lookup"><span data-stu-id="c3a23-126">Follow the instructions given in [Quickstart: Register an application with the Microsoft identity platform](/azure/active-directory/develop/quickstart-register-app) to register an application and add a client secret to AAD under your azure subscription.</span></span>
  - [<span data-ttu-id="c3a23-127">Registrar um aplicativo</span><span class="sxs-lookup"><span data-stu-id="c3a23-127">Register an application</span></span>](/azure/active-directory/develop/quickstart-register-app)
  - [<span data-ttu-id="c3a23-128">Adicionar um segredo do cliente</span><span class="sxs-lookup"><span data-stu-id="c3a23-128">Add a client secret</span></span>](/azure/active-directory/develop/quickstart-register-app#add-a-certificate)
  - <span data-ttu-id="c3a23-129">O **ID do aplicativo (Client)**, **Segredo do cliente** e **ID do locatário** serão usados nas etapas a seguir.</span><span class="sxs-lookup"><span data-stu-id="c3a23-129">The **Application(Client) Id**, **Client Secret**, and **Tenant ID** will be used in the following steps.</span></span>

> [!NOTE]
> <span data-ttu-id="c3a23-130">Os países e regiões com suporte no momento incluem o Canadá, os Estados Unidos e a União Europeia (UE).</span><span class="sxs-lookup"><span data-stu-id="c3a23-130">The currently supported countries and regions include Canada, the United States, and the European Union (EU).</span></span>

<span data-ttu-id="c3a23-131">Caso tenha alguma dúvida sobre esses pré-requisitos, entre em contato com a equipe do produto Visibilidade de Estoque.</span><span class="sxs-lookup"><span data-stu-id="c3a23-131">If you have any questions about these prerequisites, please contact the Inventory Visibility product team.</span></span>

### <a name="set-up-dataverse"></a><a name="setup-microsoft-dataverse"></a><span data-ttu-id="c3a23-132">Configurar Dataverse</span><span class="sxs-lookup"><span data-stu-id="c3a23-132">Set up Dataverse</span></span>

<span data-ttu-id="c3a23-133">Para configurar o Dataverse para uso com o Visibilidade do Inventário, primeiro você preparar os pré-requisitos e então decidir se quer configurar o Dataverse usando a ferramenta do Package Deployer ou importando manualmente as soluções (não é necessário fazer os dois).</span><span class="sxs-lookup"><span data-stu-id="c3a23-133">To set up Dataverse for use with Inventory Visibility, you must first prepare the prerequisites and then decide whether to set up Dataverse using either the package deployer tool or by manually importing the solutions (you don't have to do both).</span></span> <span data-ttu-id="c3a23-134">Em seguida, instale o complemento Visibilidade do inventário.</span><span class="sxs-lookup"><span data-stu-id="c3a23-134">Then install the Inventory Visibility Add-in.</span></span> <span data-ttu-id="c3a23-135">As subseções a seguir descrevem como concluir cada uma dessas ações.</span><span class="sxs-lookup"><span data-stu-id="c3a23-135">The following subsections describe how to complete each of these tasks.</span></span>

#### <a name="prepare-dataverse-prerequisites"></a><span data-ttu-id="c3a23-136">Preparar pré-requisitos do Dataverse</span><span class="sxs-lookup"><span data-stu-id="c3a23-136">Prepare Dataverse prerequisites</span></span>

<span data-ttu-id="c3a23-137">Antes de começar a configurar o Dataverse, adicione um princípio de serviço ao seu locatário fazendo o seguinte:</span><span class="sxs-lookup"><span data-stu-id="c3a23-137">Before you start to set up Dataverse, add a service principle to your tenant by doing the following:</span></span>

1. <span data-ttu-id="c3a23-138">Instale o módulo Azure AD PowerShell v2, conforme descrito em [Instalar o Azure Active Directory PowerShell para o Graph](/powershell/azure/active-directory/install-adv2).</span><span class="sxs-lookup"><span data-stu-id="c3a23-138">Install Azure AD PowerShell Module v2 as described in [Install Azure Active Directory PowerShell for Graph](/powershell/azure/active-directory/install-adv2).</span></span>

1. <span data-ttu-id="c3a23-139">Execute o seguinte comando do PowerShell:</span><span class="sxs-lookup"><span data-stu-id="c3a23-139">Run the following PowerShell command:</span></span>

    ```powershell
    Connect-AzureAD # (open a sign in window and sign in as a tenant user)
    
    New-AzureADServicePrincipal -AppId "3022308a-b9bd-4a18-b8ac-2ddedb2075e1" -DisplayName "d365-scm-inventoryservice"
    ```

#### <a name="set-up-dataverse-using-the-package-deployer-tool"></a><span data-ttu-id="c3a23-140">Configurar o Dataverse usando a ferramenta Package Deployer</span><span class="sxs-lookup"><span data-stu-id="c3a23-140">Set up Dataverse using the package deployer tool</span></span>

<span data-ttu-id="c3a23-141">Após preparar os pré-requisitos, use o seguinte procedimento se preferir configurar o Dataverse usando a ferramenta Package Deployer.</span><span class="sxs-lookup"><span data-stu-id="c3a23-141">After you have the prerequisites in place, use the following procedure if you prefer to set up Dataverse using the package deployer tool.</span></span> <span data-ttu-id="c3a23-142">Consulte a próxima seção para ver detalhes sobre como importar as soluções manualmente (não use os dois procedimentos).</span><span class="sxs-lookup"><span data-stu-id="c3a23-142">See the next section for details about how to import the solutions manually instead (don't do both).</span></span>

1. <span data-ttu-id="c3a23-143">Instale as ferramentas para desenvolvedores conforme descrito em [Baixar ferramentas do NuGet](/dynamics365/customerengagement/on-premises/developer/download-tools-nuget).</span><span class="sxs-lookup"><span data-stu-id="c3a23-143">Install developer tools as described in [Download tools from NuGet](/dynamics365/customerengagement/on-premises/developer/download-tools-nuget).</span></span>

1. <span data-ttu-id="c3a23-144">Com base em suas necessidades de negócios, escolha o pacote `InventoryServiceBase` ou `InventoryServiceApplication`.</span><span class="sxs-lookup"><span data-stu-id="c3a23-144">Based on your business requirements, choose the `InventoryServiceBase` or `InventoryServiceApplication` package.</span></span>

1. <span data-ttu-id="c3a23-145">Importe as soluções:</span><span class="sxs-lookup"><span data-stu-id="c3a23-145">Import the solutions:</span></span>
    1. <span data-ttu-id="c3a23-146">Para o pacote `InventoryServiceBase`:</span><span class="sxs-lookup"><span data-stu-id="c3a23-146">For the `InventoryServiceBase` package:</span></span>
        - <span data-ttu-id="c3a23-147">Descompacte `InventoryServiceBase.PackageDeployer.zip`</span><span class="sxs-lookup"><span data-stu-id="c3a23-147">Unzip `InventoryServiceBase.PackageDeployer.zip`</span></span>
        - <span data-ttu-id="c3a23-148">Encontre a pasta `InventoryServiceBase`, arquivo `[Content_Types].xml`, arquivo `Microsoft.Dynamics.InventoryServiceBase.PackageExtension.dll`, arquivo `Microsoft.Dynamics.InventoryServiceBase.PackageExtension.dll.config` e arquivo `Microsoft.Dynamics.InventoryServiceBase.PackageExtension.dll.config`.</span><span class="sxs-lookup"><span data-stu-id="c3a23-148">Find folder `InventoryServiceBase`, file `[Content_Types].xml`, file `Microsoft.Dynamics.InventoryServiceBase.PackageExtension.dll`, file `Microsoft.Dynamics.InventoryServiceBase.PackageExtension.dll.config`, and file `Microsoft.Dynamics.InventoryServiceBase.PackageExtension.dll.config`.</span></span> 
        - <span data-ttu-id="c3a23-149">Copie cada uma dessas pastas e arquivos para o diretório `.\Tools\PackageDeployment`, que foi criado quando você instalou as ferramentas para desenvolvedores.</span><span class="sxs-lookup"><span data-stu-id="c3a23-149">Copy each of these folders and files to the `.\Tools\PackageDeployment` directory, which was created when you installed the developer tools.</span></span>
    1. <span data-ttu-id="c3a23-150">Para o pacote `InventoryServiceApplication`:</span><span class="sxs-lookup"><span data-stu-id="c3a23-150">For the `InventoryServiceApplication` package:</span></span>
        - <span data-ttu-id="c3a23-151">Descompacte `InventoryServiceApplication.PackageDeployer.zip`</span><span class="sxs-lookup"><span data-stu-id="c3a23-151">Unzip `InventoryServiceApplication.PackageDeployer.zip`</span></span>
        - <span data-ttu-id="c3a23-152">Encontre a pasta `InventoryServiceApplication`, arquivo `[Content_Types].xml`, arquivo `Microsoft.Dynamics.InventoryServiceApplication.PackageExtension.dll`, arquivo `Microsoft.Dynamics.InventoryServiceApplication.PackageExtension.dll.config` e arquivo `Microsoft.Dynamics.InventoryServiceApplication.PackageExtension.dll.config`.</span><span class="sxs-lookup"><span data-stu-id="c3a23-152">Find folder `InventoryServiceApplication`, file `[Content_Types].xml`, file `Microsoft.Dynamics.InventoryServiceApplication.PackageExtension.dll`, file `Microsoft.Dynamics.InventoryServiceApplication.PackageExtension.dll.config`, and file `Microsoft.Dynamics.InventoryServiceApplication.PackageExtension.dll.config`.</span></span>
        - <span data-ttu-id="c3a23-153">Copie cada uma dessas pastas e arquivos para o diretório `.\Tools\PackageDeployment`, que foi criado quando você instalou as ferramentas para desenvolvedores.</span><span class="sxs-lookup"><span data-stu-id="c3a23-153">Copy each of these folders and files to the `.\Tools\PackageDeployment` directory, which was created when you installed the developer tools.</span></span>
    1. <span data-ttu-id="c3a23-154">Execute `.\Tools\PackageDeployment\PackageDeployer.exe`.</span><span class="sxs-lookup"><span data-stu-id="c3a23-154">Execute `.\Tools\PackageDeployment\PackageDeployer.exe`.</span></span> <span data-ttu-id="c3a23-155">Siga as instruções na sua tela para importar as soluções.</span><span class="sxs-lookup"><span data-stu-id="c3a23-155">Follow the instructions on your screen to import the solutions.</span></span>

1. <span data-ttu-id="c3a23-156">Atribua direitos de acesso ao usuário do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="c3a23-156">Assign security roles to the application user.</span></span>
    1. <span data-ttu-id="c3a23-157">Abra a URL do ambiente do Dataverse.</span><span class="sxs-lookup"><span data-stu-id="c3a23-157">Open the URL of your Dataverse environment.</span></span>
    1. <span data-ttu-id="c3a23-158">Vá para **Configurações avançadas \> Sistema \> Segurança \> Usuários** e encontre o usuário chamado **# InventoryVisibility**.</span><span class="sxs-lookup"><span data-stu-id="c3a23-158">Go to **Advanced Setting \> System \> Security \> Users**, and find user the named **# InventoryVisibility**.</span></span>
    1. <span data-ttu-id="c3a23-159">Selecione **Atribuir Função** e, depois, selecione **Administrador do Sistema**.</span><span class="sxs-lookup"><span data-stu-id="c3a23-159">Select **Assign Role**, and then select **System Administrator**.</span></span> <span data-ttu-id="c3a23-160">Se houver uma função chamada **Usuário do Common Data Service**, selecione-a também.</span><span class="sxs-lookup"><span data-stu-id="c3a23-160">If there is a role that is named **Common Data Service User**, select it as well.</span></span>

#### <a name="set-up-dataverse-manually-by-importing-solutions"></a><span data-ttu-id="c3a23-161">Configurar o Dataverse manualmente importando soluções</span><span class="sxs-lookup"><span data-stu-id="c3a23-161">Set up Dataverse manually by importing solutions</span></span>

<span data-ttu-id="c3a23-162">Após preparar os pré-requisitos, use o seguinte procedimento se preferir configurar o Dataverse importando soluções manualmente.</span><span class="sxs-lookup"><span data-stu-id="c3a23-162">After you have the prerequisites in place, use the following procedure if you prefer to set up Dataverse by manually importing solutions.</span></span> <span data-ttu-id="c3a23-163">Consulte a seção anterior para ver detalhes sobre como usar a ferramenta Package Deployer (não use os dois procedimentos).</span><span class="sxs-lookup"><span data-stu-id="c3a23-163">See the previous section for details about how to use the package deployer tool instead (don't do both).</span></span>

1. <span data-ttu-id="c3a23-164">Crie um usuário de aplicativo para a visibilidade de estoque no Dataverse:</span><span class="sxs-lookup"><span data-stu-id="c3a23-164">Create an application user for Inventory Visibility in Dataverse:</span></span>

    1. <span data-ttu-id="c3a23-165">Abra a URL do ambiente do Dataverse.</span><span class="sxs-lookup"><span data-stu-id="c3a23-165">Open the URL of your Dataverse environment.</span></span>
    1. <span data-ttu-id="c3a23-166">Acesse **Configuração Avançada \> Sistema \> Segurança \> Usuários** e crie um usuário de aplicativo.</span><span class="sxs-lookup"><span data-stu-id="c3a23-166">Go to **Advanced Setting \> System \> Security \> Users**, and create an application user.</span></span> <span data-ttu-id="c3a23-167">Use o menu de exibição para alterar a exibição de página para **Usuários do Aplicativo**.</span><span class="sxs-lookup"><span data-stu-id="c3a23-167">Use the view menu to change the page view to **Application Users**.</span></span>
    1. <span data-ttu-id="c3a23-168">Selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="c3a23-168">Select **New**.</span></span> <span data-ttu-id="c3a23-169">Defina a ID do aplicativo como *3022308a-b9bd-4a18-b8ac-2ddedb2075e1*.</span><span class="sxs-lookup"><span data-stu-id="c3a23-169">Set the application ID to *3022308a-b9bd-4a18-b8ac-2ddedb2075e1*.</span></span> <span data-ttu-id="c3a23-170">(A ID do objeto será carregada automaticamente quando você salvar as alterações.) Você pode personalizar o nome.</span><span class="sxs-lookup"><span data-stu-id="c3a23-170">(The object ID will automatically be loaded when you save your changes.) You can customize the name.</span></span> <span data-ttu-id="c3a23-171">Por exemplo, você pode alterá-lo para *Visibilidade do Estoque*.</span><span class="sxs-lookup"><span data-stu-id="c3a23-171">For example, you can change it to *Inventory Visibility*.</span></span> <span data-ttu-id="c3a23-172">Quando terminar, selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="c3a23-172">When you've finished, select **Save**.</span></span>
    1. <span data-ttu-id="c3a23-173">Selecione **Atribuir Função** e, depois, selecione **Administrador do Sistema**.</span><span class="sxs-lookup"><span data-stu-id="c3a23-173">Select **Assign Role**, and then select **System Administrator**.</span></span> <span data-ttu-id="c3a23-174">Se houver uma função denominada **Usuário do Common Data Service**, selecione-a.</span><span class="sxs-lookup"><span data-stu-id="c3a23-174">If there is a role that is named **Common Data Service User**, select it too.</span></span>

    <span data-ttu-id="c3a23-175">Para obter mais informações, consulte [Criar um usuário de aplicativo](/power-platform/admin/create-users-assign-online-security-roles#create-an-application-user).</span><span class="sxs-lookup"><span data-stu-id="c3a23-175">For more information, see [Create an application user](/power-platform/admin/create-users-assign-online-security-roles#create-an-application-user).</span></span>

1. <span data-ttu-id="c3a23-176">Se o idioma padrão de seu Dataverse não estiver definido como **Inglês**:</span><span class="sxs-lookup"><span data-stu-id="c3a23-176">If the default language of your Dataverse is not **English**:</span></span>

    1. <span data-ttu-id="c3a23-177">Acesse **Configurações avançadas \> Administração \> Idiomas**,</span><span class="sxs-lookup"><span data-stu-id="c3a23-177">Go to **Advanced Setting \> Administration \> Languages**,</span></span>
    1. <span data-ttu-id="c3a23-178">Selecione **Inglês (LanguageCode = 1033)** e selecione **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="c3a23-178">Select **English (LanguageCode=1033)** and select **Apply**.</span></span>

1. <span data-ttu-id="c3a23-179">Importe o arquivo `Inventory Visibility Dataverse Solution.zip`, que inclui entidades relacionadas à configuração do Dataverse e o Power Apps:</span><span class="sxs-lookup"><span data-stu-id="c3a23-179">Import the `Inventory Visibility Dataverse Solution.zip` file, which includes Dataverse configuration related entities and Power Apps:</span></span>

    1. <span data-ttu-id="c3a23-180">Acesse a página **Soluções**.</span><span class="sxs-lookup"><span data-stu-id="c3a23-180">Go to the **Solutions** page.</span></span>
    1. <span data-ttu-id="c3a23-181">Selecione **Importar**.</span><span class="sxs-lookup"><span data-stu-id="c3a23-181">Select **Import**.</span></span>

1. <span data-ttu-id="c3a23-182">Importe o fluxo do disparador da atualização de configuração:</span><span class="sxs-lookup"><span data-stu-id="c3a23-182">Import the configuration upgrade trigger flow:</span></span>

    1. <span data-ttu-id="c3a23-183">Acesse a página Microsoft Flow.</span><span class="sxs-lookup"><span data-stu-id="c3a23-183">Go to the Microsoft Flow page.</span></span>
    1. <span data-ttu-id="c3a23-184">Verifique se existe a conexão denominada *Dataverse (herdado)*.</span><span class="sxs-lookup"><span data-stu-id="c3a23-184">Make sure that the connection that is named *Dataverse (legacy)* exists.</span></span> <span data-ttu-id="c3a23-185">(Se ela não existir, crie-a.)</span><span class="sxs-lookup"><span data-stu-id="c3a23-185">(If it doesn't exist, create it.)</span></span>
    1. <span data-ttu-id="c3a23-186">Importe o arquivo `Inventory Visibility Configuration Trigger.zip`.</span><span class="sxs-lookup"><span data-stu-id="c3a23-186">Import the `Inventory Visibility Configuration Trigger.zip` file.</span></span> <span data-ttu-id="c3a23-187">Após ele ser importado, o disparador aparecerá em **Meus fluxos**.</span><span class="sxs-lookup"><span data-stu-id="c3a23-187">After it's imported, the trigger will appear under **My flows**.</span></span>
    1. <span data-ttu-id="c3a23-188">Inicialize as seguintes quatro variáveis, com base nas informações de ambiente:</span><span class="sxs-lookup"><span data-stu-id="c3a23-188">Initialize the following four variables, based on the environment information:</span></span>

        - <span data-ttu-id="c3a23-189">ID de Locatário do Azure</span><span class="sxs-lookup"><span data-stu-id="c3a23-189">Azure Tenant ID</span></span>
        - <span data-ttu-id="c3a23-190">ID do Cliente do Aplicativo Azure</span><span class="sxs-lookup"><span data-stu-id="c3a23-190">Azure Application Client ID</span></span>
        - <span data-ttu-id="c3a23-191">Segredo do Cliente do Aplicativo Azure</span><span class="sxs-lookup"><span data-stu-id="c3a23-191">Azure Application Client Secret</span></span>
        - <span data-ttu-id="c3a23-192">Ponto de extremidade da Visibilidade de Estoque</span><span class="sxs-lookup"><span data-stu-id="c3a23-192">Inventory Visibility Endpoint</span></span>

            <span data-ttu-id="c3a23-193">Para obter mais informações sobre essa variável, consulte a seção [Configurar integração da visibilidade de estoque](#setup-inventory-visibility-integration) mais adiante neste tópico.</span><span class="sxs-lookup"><span data-stu-id="c3a23-193">For more information about this variable, see the [Set up Inventory Visibility integration](#setup-inventory-visibility-integration) section later in this topic.</span></span>

        <span data-ttu-id="c3a23-194">![Gatilho de configurações](media/configuration-trigger.png "Gatilho de configurações")</span><span class="sxs-lookup"><span data-stu-id="c3a23-194">![Configuration trigger](media/configuration-trigger.png "Configuration trigger")</span></span>

    1. <span data-ttu-id="c3a23-195">Selecione **Ativar**.</span><span class="sxs-lookup"><span data-stu-id="c3a23-195">Select **Turn on**.</span></span>

### <a name="install-the-add-in"></a><a name="install-add-in"></a><span data-ttu-id="c3a23-196">Instalar o suplemento</span><span class="sxs-lookup"><span data-stu-id="c3a23-196">Install the add-in</span></span>

<span data-ttu-id="c3a23-197">Para instalar o Suplemento Visibilidade de Estoque, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="c3a23-197">To install the Inventory Visibility Add-in, do the following:</span></span>

1. <span data-ttu-id="c3a23-198">Entre no portal [Lifecycle Services (LCS)](https://lcs.dynamics.com/Logon/Index).</span><span class="sxs-lookup"><span data-stu-id="c3a23-198">Sign in to the [Lifecycle Services (LCS)](https://lcs.dynamics.com/Logon/Index) portal.</span></span>
1. <span data-ttu-id="c3a23-199">Na home page, selecione o projeto no qual seu ambiente foi implantado.</span><span class="sxs-lookup"><span data-stu-id="c3a23-199">On the home page, select the project where your environment is deployed.</span></span>
1. <span data-ttu-id="c3a23-200">Na página do projeto, selecione o ambiente no qual você deseja instalar o suplemento.</span><span class="sxs-lookup"><span data-stu-id="c3a23-200">On the project page, select the environment where you want to install the add-in.</span></span>
1. <span data-ttu-id="c3a23-201">Na página ambiente, role para baixo até ver a seção **Suplementos do ambiente** na seção **Integração do Power Platform**, em que você pode encontrar o nome do ambiente do Dataverse.</span><span class="sxs-lookup"><span data-stu-id="c3a23-201">On the environment page, scroll down until you see the **Environment add-ins** section in the **Power Platform integration** section, where you can find the Dataverse environment name.</span></span>
1. <span data-ttu-id="c3a23-202">Na seção **Suplementos de ambiente**, selecione **Instalar um novo suplemento**.</span><span class="sxs-lookup"><span data-stu-id="c3a23-202">In the **Environment add-ins** section, select **Install a new add-in**.</span></span>

    <span data-ttu-id="c3a23-203">![A página do ambiente no LCS](media/inventory-visibility-environment.png "A página do ambiente no LCS")</span><span class="sxs-lookup"><span data-stu-id="c3a23-203">![The environment page in LCS](media/inventory-visibility-environment.png "The environment page in LCS")</span></span>

1. <span data-ttu-id="c3a23-204">Selecione o link **Instalar um novo suplemento**.</span><span class="sxs-lookup"><span data-stu-id="c3a23-204">Select the **Install a new add-in** link.</span></span> <span data-ttu-id="c3a23-205">Uma lista dos suplementos disponíveis será aberta.</span><span class="sxs-lookup"><span data-stu-id="c3a23-205">A list of available add-ins opens.</span></span>
1. <span data-ttu-id="c3a23-206">Selecione **Visibilidade de Estoque** na lista.</span><span class="sxs-lookup"><span data-stu-id="c3a23-206">Select **Inventory Visibility** in the list.</span></span>
1. <span data-ttu-id="c3a23-207">Insira valores para os seguintes campos no seu ambiente:</span><span class="sxs-lookup"><span data-stu-id="c3a23-207">Enter values for the following fields for your environment:</span></span>

    - <span data-ttu-id="c3a23-208">**ID de aplicativo AAD (cliente)**</span><span class="sxs-lookup"><span data-stu-id="c3a23-208">**AAD application (client) ID**</span></span>
    - <span data-ttu-id="c3a23-209">**ID de locatário do AAD**</span><span class="sxs-lookup"><span data-stu-id="c3a23-209">**AAD tenant ID**</span></span>

    <span data-ttu-id="c3a23-210">![Página de configuração do suplemento](media/inventory-visibility-setup.png "Página de configuração do suplemento")</span><span class="sxs-lookup"><span data-stu-id="c3a23-210">![Add in setup page](media/inventory-visibility-setup.png "Add-in setup page")</span></span>

1. <span data-ttu-id="c3a23-211">Concorde com os termos e condições, marcando a caixa de seleção **Termos e condições**.</span><span class="sxs-lookup"><span data-stu-id="c3a23-211">Agree to the terms and condition by selecting the **Terms and conditions** check box.</span></span>
1. <span data-ttu-id="c3a23-212">Selecione **Instalar**.</span><span class="sxs-lookup"><span data-stu-id="c3a23-212">Select **Install**.</span></span> <span data-ttu-id="c3a23-213">O status do suplemento será mostrado como **Instalando**.</span><span class="sxs-lookup"><span data-stu-id="c3a23-213">The status of the add-in will show as **Installing**.</span></span> <span data-ttu-id="c3a23-214">Após a conclusão, atualize a página para ver a alteração do status para **Instalado**.</span><span class="sxs-lookup"><span data-stu-id="c3a23-214">When it's done, refresh the page to see the status change to **Installed**.</span></span>

### <a name="uninstall-the-add-in"></a><a name="uninstall-add-in"></a><span data-ttu-id="c3a23-215">Desinstalar o suplemento</span><span class="sxs-lookup"><span data-stu-id="c3a23-215">Uninstall the add-in</span></span>

<span data-ttu-id="c3a23-216">Para desinstalar o suplemento, selecione **Desinstalar**.</span><span class="sxs-lookup"><span data-stu-id="c3a23-216">To uninstall the add-in, select **Uninstall**.</span></span> <span data-ttu-id="c3a23-217">Quando você atualizar o LCS, o Suplemento de Visibilidade de Estoque será removido.</span><span class="sxs-lookup"><span data-stu-id="c3a23-217">When you refresh LCS, the Inventory Visibility Add-in will be removed.</span></span> <span data-ttu-id="c3a23-218">O processo de desinstalação remove o registro do suplemento e também inicia um trabalho para limpar todos os dados comerciais armazenados no serviço.</span><span class="sxs-lookup"><span data-stu-id="c3a23-218">The uninstall process removes the add-in registration and also starts a job to clean up all the business data that is stored in the service.</span></span>

## <a name="consume-on-hand-inventory-data-from-supply-chain-management"></a><span data-ttu-id="c3a23-219">Consumir dados de estoque disponível do Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="c3a23-219">Consume on-hand inventory data from Supply Chain Management</span></span>

### <a name="deploy-the-inventory-visibility-integration-package"></a><a name="deploy-inventory-visibility-package"></a><span data-ttu-id="c3a23-220">Implantar o pacote de integração de Visibilidade de Estoque</span><span class="sxs-lookup"><span data-stu-id="c3a23-220">Deploy the Inventory Visibility integration package</span></span>

<span data-ttu-id="c3a23-221">Se você estiver executando o Supply Chain Management versão 10.0.17 ou anterior, contate a equipe de suporte de integração da Visibilidade de Estoque em [inventvisibilitysupp@microsoft.com](mailto:inventvisibilitysupp@microsoft.com) para obter o arquivo de pacote.</span><span class="sxs-lookup"><span data-stu-id="c3a23-221">If you're running Supply Chain Management version 10.0.17 or earlier, contact the Inventory Visibility on-board support team at [inventvisibilitysupp@microsoft.com](mailto:inventvisibilitysupp@microsoft.com) to get the package file.</span></span> <span data-ttu-id="c3a23-222">Em seguida, implante o pacote no LCS.</span><span class="sxs-lookup"><span data-stu-id="c3a23-222">Then deploy the package in LCS.</span></span>

> [!NOTE]
> <span data-ttu-id="c3a23-223">Se ocorrer um erro de incompatibilidade de versão durante a implantação, você deverá importar manualmente o projeto X++ no ambiente de desenvolvimento.</span><span class="sxs-lookup"><span data-stu-id="c3a23-223">If a version mismatch error occurs during deployment, you must manually import the X++ project into your development environment.</span></span> <span data-ttu-id="c3a23-224">Em seguida, crie o pacote implantável no ambiente de desenvolvimento e implante-o no ambiente de produção.</span><span class="sxs-lookup"><span data-stu-id="c3a23-224">Then create the deployable package in your development environment, and deploy it in your production environment.</span></span>
> 
> <span data-ttu-id="c3a23-225">O código está incluído no Supply Chain Management versão 10.0.18.</span><span class="sxs-lookup"><span data-stu-id="c3a23-225">The code is included with Supply Chain Management version 10.0.18.</span></span> <span data-ttu-id="c3a23-226">Se você estiver executando essa versão ou posterior, a implantação não será necessária.</span><span class="sxs-lookup"><span data-stu-id="c3a23-226">If you're running that version or later, deployment isn't required.</span></span>

<span data-ttu-id="c3a23-227">Verifique se os recursos a seguir estão ativados no ambiente do Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="c3a23-227">Make sure that the following features are turned on in your Supply Chain Management environment.</span></span> <span data-ttu-id="c3a23-228">(Por padrão, eles são ativados.)</span><span class="sxs-lookup"><span data-stu-id="c3a23-228">(By default, they are turned on.)</span></span>

| <span data-ttu-id="c3a23-229">Descrição do recurso</span><span class="sxs-lookup"><span data-stu-id="c3a23-229">Feature description</span></span> | <span data-ttu-id="c3a23-230">Versão de código</span><span class="sxs-lookup"><span data-stu-id="c3a23-230">Code version</span></span> | <span data-ttu-id="c3a23-231">Alternar classe</span><span class="sxs-lookup"><span data-stu-id="c3a23-231">Toggle class</span></span> |
|---|---|---|
| <span data-ttu-id="c3a23-232">Habilitar ou desabilitar o uso de dimensões de estoque na tabela InventSum</span><span class="sxs-lookup"><span data-stu-id="c3a23-232">Enable or disable using inventory dimensions on InventSum table</span></span> | <span data-ttu-id="c3a23-233">10.0.11</span><span class="sxs-lookup"><span data-stu-id="c3a23-233">10.0.11</span></span> | <span data-ttu-id="c3a23-234">InventUseDimOfInventSumToggle</span><span class="sxs-lookup"><span data-stu-id="c3a23-234">InventUseDimOfInventSumToggle</span></span> |
| <span data-ttu-id="c3a23-235">Habilitar ou desabilitar o uso de dimensões de estoque na tabela InventSumDelta</span><span class="sxs-lookup"><span data-stu-id="c3a23-235">Enable or disable using inventory dimensions on InventSumDelta table</span></span> | <span data-ttu-id="c3a23-236">10.0.12</span><span class="sxs-lookup"><span data-stu-id="c3a23-236">10.0.12</span></span> | <span data-ttu-id="c3a23-237">InventUseDimOfInventSumDeltaToggle</span><span class="sxs-lookup"><span data-stu-id="c3a23-237">InventUseDimOfInventSumDeltaToggle</span></span> |

### <a name="set-up-inventory-visibility-integration"></a><a name="setup-inventory-visibility-integration"></a><span data-ttu-id="c3a23-238">Configurar a integração da Visibilidade de Estoque</span><span class="sxs-lookup"><span data-stu-id="c3a23-238">Set up Inventory Visibility integration</span></span>

1. <span data-ttu-id="c3a23-239">No Supply Chain Management, abra o espaço de trabalho **[Gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)** e ative o recurso **Integração da Visibilidade de Estoque**.</span><span class="sxs-lookup"><span data-stu-id="c3a23-239">In Supply Chain Management, open the **[Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)** workspace, and turn on the **Inventory Visibility Integration** feature.</span></span>
1. <span data-ttu-id="c3a23-240">Acesse **Gerenciamento de Estoque \> Configuração \> Parâmetros de Integração da Visibilidade de Estoque** e insira a URL do ambiente em que você está executando a Visibilidade de Estoque.</span><span class="sxs-lookup"><span data-stu-id="c3a23-240">Go to **Inventory Management \> Set up \> Inventory Visibility Integration parameters**, and enter the URL of the environment where you're running Inventory Visibility.</span></span>

    <span data-ttu-id="c3a23-241">Localize a região do Azure do ambiente do LCS e insira a URL.</span><span class="sxs-lookup"><span data-stu-id="c3a23-241">Find your LCS environment's Azure region, and then enter the URL.</span></span> <span data-ttu-id="c3a23-242">A URL tem o seguinte formato:</span><span class="sxs-lookup"><span data-stu-id="c3a23-242">The URL has the following form:</span></span>

    `https://inventoryservice.<RegionShortName>-il301.gateway.prod.island.powerapps.com`

    <span data-ttu-id="c3a23-243">Por exemplo, se você estiver na Europa, o ambiente terá uma das seguintes URLs:</span><span class="sxs-lookup"><span data-stu-id="c3a23-243">For example, if you're in Europe, your environment will have one of the following URLs:</span></span>

    - `https://inventoryservice.neu-il301.gateway.prod.island.powerapps.com`
    - `https://inventoryservice.weu-il301.gateway.prod.island.powerapps.com`

    <span data-ttu-id="c3a23-244">As regiões a seguir estão disponíveis no momento.</span><span class="sxs-lookup"><span data-stu-id="c3a23-244">The following regions are currently available.</span></span>

    | <span data-ttu-id="c3a23-245">Região do Azure</span><span class="sxs-lookup"><span data-stu-id="c3a23-245">Azure region</span></span> | <span data-ttu-id="c3a23-246">Nome curto da região</span><span class="sxs-lookup"><span data-stu-id="c3a23-246">Region short name</span></span> |
    |---|---|
    | <span data-ttu-id="c3a23-247">Leste da Austrália</span><span class="sxs-lookup"><span data-stu-id="c3a23-247">Australia east</span></span> | <span data-ttu-id="c3a23-248">eau</span><span class="sxs-lookup"><span data-stu-id="c3a23-248">eau</span></span> |
    | <span data-ttu-id="c3a23-249">Sudeste da Austrália</span><span class="sxs-lookup"><span data-stu-id="c3a23-249">Australia southeast</span></span> | <span data-ttu-id="c3a23-250">seau</span><span class="sxs-lookup"><span data-stu-id="c3a23-250">seau</span></span> |
    | <span data-ttu-id="c3a23-251">Canadá Central</span><span class="sxs-lookup"><span data-stu-id="c3a23-251">Canada central</span></span> | <span data-ttu-id="c3a23-252">cca</span><span class="sxs-lookup"><span data-stu-id="c3a23-252">cca</span></span> |
    | <span data-ttu-id="c3a23-253">Leste do Canadá</span><span class="sxs-lookup"><span data-stu-id="c3a23-253">Canada east</span></span> | <span data-ttu-id="c3a23-254">eca</span><span class="sxs-lookup"><span data-stu-id="c3a23-254">eca</span></span> |
    | <span data-ttu-id="c3a23-255">Norte da Europa</span><span class="sxs-lookup"><span data-stu-id="c3a23-255">North Europe</span></span> | <span data-ttu-id="c3a23-256">neu</span><span class="sxs-lookup"><span data-stu-id="c3a23-256">neu</span></span> |
    | <span data-ttu-id="c3a23-257">Oeste da Europa</span><span class="sxs-lookup"><span data-stu-id="c3a23-257">West Europe</span></span> | <span data-ttu-id="c3a23-258">weu</span><span class="sxs-lookup"><span data-stu-id="c3a23-258">weu</span></span> |
    | <span data-ttu-id="c3a23-259">Leste dos EUA</span><span class="sxs-lookup"><span data-stu-id="c3a23-259">East US</span></span> | <span data-ttu-id="c3a23-260">eus</span><span class="sxs-lookup"><span data-stu-id="c3a23-260">eus</span></span> |
    | <span data-ttu-id="c3a23-261">Oeste dos EUA</span><span class="sxs-lookup"><span data-stu-id="c3a23-261">West US</span></span> | <span data-ttu-id="c3a23-262">wus</span><span class="sxs-lookup"><span data-stu-id="c3a23-262">wus</span></span> |

1. <span data-ttu-id="c3a23-263">Acesse **Gerenciamento de Estoque \> Periódico \> Integração de Visibilidade de Estoque** e habilite o trabalho.</span><span class="sxs-lookup"><span data-stu-id="c3a23-263">Go to **Inventory Management \> Periodic \> Inventory Visibility Integration**, and enable the job.</span></span> <span data-ttu-id="c3a23-264">Todos os eventos de alteração de inventário do Supply Chain Management serão lançados na Visibilidade de Estoque.</span><span class="sxs-lookup"><span data-stu-id="c3a23-264">All inventory change events from Supply Chain Management will now be posted to Inventory Visibility.</span></span>

## <a name="the-inventory-visibility-add-in-public-api"></a><a name="inventory-visibility-public-api"></a><span data-ttu-id="c3a23-265">A API pública do Suplemento Visibilidade de Estoque</span><span class="sxs-lookup"><span data-stu-id="c3a23-265">The Inventory Visibility Add-in public API</span></span>

<span data-ttu-id="c3a23-266">A API REST pública do Suplemento Visibilidade de Estoque apresenta vários pontos de extremidade específicos para integração.</span><span class="sxs-lookup"><span data-stu-id="c3a23-266">The public REST API of the Inventory Visibility Add-in presents several specific endpoints for integration.</span></span> <span data-ttu-id="c3a23-267">Ela oferece suporte a três tipos de interação principais:</span><span class="sxs-lookup"><span data-stu-id="c3a23-267">It supports three main interaction types:</span></span>

- <span data-ttu-id="c3a23-268">Lançar alterações de estoque disponíveis no suplemento a partir de um sistema externo</span><span class="sxs-lookup"><span data-stu-id="c3a23-268">Posting on-hand inventory changes to the add-in from an external system</span></span>
- <span data-ttu-id="c3a23-269">Consultar as quantidades disponíveis no momento a partir de um sistema externo</span><span class="sxs-lookup"><span data-stu-id="c3a23-269">Querying current on-hand quantities from an external system</span></span>
- <span data-ttu-id="c3a23-270">Sincronização automática com o estoque disponível do Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="c3a23-270">Automatic synchronization with Supply Chain Management on-hand inventory</span></span>

<span data-ttu-id="c3a23-271">A sincronização automática não faz parte da API pública.</span><span class="sxs-lookup"><span data-stu-id="c3a23-271">Automatic synchronization isn't part of the public API.</span></span> <span data-ttu-id="c3a23-272">Ela é tratada em segundo plano para ambientes em que o suplemento Visibilidade de Estoque está habilitado.</span><span class="sxs-lookup"><span data-stu-id="c3a23-272">Instead, it's handled in the background for environments where the Inventory Visibility Add-in is enabled.</span></span>

### <a name="authentication"></a><a name="inventory-visibility-authentication"></a><span data-ttu-id="c3a23-273">Autenticação</span><span class="sxs-lookup"><span data-stu-id="c3a23-273">Authentication</span></span>

<span data-ttu-id="c3a23-274">O token de segurança da plataforma é usado para chamar o suplemento Visibilidade de Estoque.</span><span class="sxs-lookup"><span data-stu-id="c3a23-274">The platform security token is used to call the Inventory Visibility Add-in.</span></span> <span data-ttu-id="c3a23-275">Portanto, você deve gerar um token *Azure Active Directory (Azure AD)* usando o aplicativo Azure AD.</span><span class="sxs-lookup"><span data-stu-id="c3a23-275">Therefore, you must generate an *Azure Active Directory (Azure AD) token* by using your Azure AD application.</span></span> <span data-ttu-id="c3a23-276">Você deve usar o token Azure AD para obter o *token de acesso* do serviço de segurança.</span><span class="sxs-lookup"><span data-stu-id="c3a23-276">You must then use the Azure AD token to get the *access token* from the security service.</span></span>

<span data-ttu-id="c3a23-277">Obtenha um token de serviço de segurança da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="c3a23-277">Get a security service token by doing the following:</span></span>

1. <span data-ttu-id="c3a23-278">Entre no portal do Azure e use-o para localizar `clientId` e `clientSecret` para o aplicativo Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="c3a23-278">Sign in to Azure portal and use it to find the `clientId` and `clientSecret` for your Supply Chain Management application.</span></span>
1. <span data-ttu-id="c3a23-279">Busque um token do Azure Active Directory (`aadToken`) enviando uma solicitação HTTP com as seguintes propriedades:</span><span class="sxs-lookup"><span data-stu-id="c3a23-279">Fetch an Azure Active Directory token (`aadToken`) by submitting an HTTP request with the following properties:</span></span>
    - <span data-ttu-id="c3a23-280">**URL** - `https://login.microsoftonline.com/${aadTenantId}/oauth2/token`</span><span class="sxs-lookup"><span data-stu-id="c3a23-280">**URL** - `https://login.microsoftonline.com/${aadTenantId}/oauth2/token`</span></span>
    - <span data-ttu-id="c3a23-281">**Método** - `GET`</span><span class="sxs-lookup"><span data-stu-id="c3a23-281">**Method** - `GET`</span></span>
    - <span data-ttu-id="c3a23-282">**Conteúdo do corpo (dados de formulário)**:</span><span class="sxs-lookup"><span data-stu-id="c3a23-282">**Body content (form data)**:</span></span>

        | <span data-ttu-id="c3a23-283">key</span><span class="sxs-lookup"><span data-stu-id="c3a23-283">key</span></span> | <span data-ttu-id="c3a23-284">valor</span><span class="sxs-lookup"><span data-stu-id="c3a23-284">value</span></span> |
        | --- | --- |
        | <span data-ttu-id="c3a23-285">client_id</span><span class="sxs-lookup"><span data-stu-id="c3a23-285">client_id</span></span> | <span data-ttu-id="c3a23-286">${aadAppId}</span><span class="sxs-lookup"><span data-stu-id="c3a23-286">${aadAppId}</span></span> |
        | <span data-ttu-id="c3a23-287">client_secret</span><span class="sxs-lookup"><span data-stu-id="c3a23-287">client_secret</span></span> | <span data-ttu-id="c3a23-288">${aadAppSecret}</span><span class="sxs-lookup"><span data-stu-id="c3a23-288">${aadAppSecret}</span></span> |
        | <span data-ttu-id="c3a23-289">grant_type</span><span class="sxs-lookup"><span data-stu-id="c3a23-289">grant_type</span></span> | <span data-ttu-id="c3a23-290">client_credentials</span><span class="sxs-lookup"><span data-stu-id="c3a23-290">client_credentials</span></span> |
        | <span data-ttu-id="c3a23-291">resource</span><span class="sxs-lookup"><span data-stu-id="c3a23-291">resource</span></span> | <span data-ttu-id="c3a23-292">0cdb527f-a8d1-4bf8-9436-b352c68682b2</span><span class="sxs-lookup"><span data-stu-id="c3a23-292">0cdb527f-a8d1-4bf8-9436-b352c68682b2</span></span> |
1. <span data-ttu-id="c3a23-293">Você receberá um `aadToken` em resposta, que se parece com o seguinte exemplo.</span><span class="sxs-lookup"><span data-stu-id="c3a23-293">You should receive an `aadToken` in response, which resembles the following example.</span></span>

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

1. <span data-ttu-id="c3a23-294">Formule uma solicitação JSON que se parece com a seguinte:</span><span class="sxs-lookup"><span data-stu-id="c3a23-294">Formulate a JSON request that resembles the following:</span></span>

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

    <span data-ttu-id="c3a23-295">Onde:</span><span class="sxs-lookup"><span data-stu-id="c3a23-295">Where:</span></span>
    - <span data-ttu-id="c3a23-296">O valor `client_assertion` deve ser o `aadToken` que recebeu na etapa anterior.</span><span class="sxs-lookup"><span data-stu-id="c3a23-296">The `client_assertion` value must be the `aadToken` you received in the previous step.</span></span>
    - <span data-ttu-id="c3a23-297">O valor de `context` deve ser a ID do ambiente em que deseja implantar o suplemento.</span><span class="sxs-lookup"><span data-stu-id="c3a23-297">The `context` value must be the environment ID where you want to deploy the add-in.</span></span>
    - <span data-ttu-id="c3a23-298">Defina todos os demais valores conforme exibido no exemplo.</span><span class="sxs-lookup"><span data-stu-id="c3a23-298">Set all of other values as shown in the example.</span></span>

1. <span data-ttu-id="c3a23-299">Envie uma solicitação HTTP com as seguintes propriedades:</span><span class="sxs-lookup"><span data-stu-id="c3a23-299">Submit an HTTP request with the following properties:</span></span>
    - <span data-ttu-id="c3a23-300">**URL** - `https://securityservice.operations365.dynamics.com/token`</span><span class="sxs-lookup"><span data-stu-id="c3a23-300">**URL** - `https://securityservice.operations365.dynamics.com/token`</span></span>
    - <span data-ttu-id="c3a23-301">**Método** - `POST`</span><span class="sxs-lookup"><span data-stu-id="c3a23-301">**Method** - `POST`</span></span>
    - <span data-ttu-id="c3a23-302">**Cabeçalho HTTP** – inclua a versão da API (a chave é `Api-Version` e o valor é `1.0`)</span><span class="sxs-lookup"><span data-stu-id="c3a23-302">**HTTP header** - Include the API version (key is `Api-Version` and value is `1.0`)</span></span>
    - <span data-ttu-id="c3a23-303">**Conteúdo do corpo** – inclua a solicitação JSON criada na etapa anterior.</span><span class="sxs-lookup"><span data-stu-id="c3a23-303">**Body content** - Include the JSON request that you created in the previous step.</span></span>

1. <span data-ttu-id="c3a23-304">Você receberá um `access_token` em resposta.</span><span class="sxs-lookup"><span data-stu-id="c3a23-304">You will get an `access_token` in response.</span></span> <span data-ttu-id="c3a23-305">É disso que você precisará como um token de portador para chamar a API da Visibilidade de Estoque.</span><span class="sxs-lookup"><span data-stu-id="c3a23-305">This is what you need as a bearer token to call the Inventory Visibility API.</span></span> <span data-ttu-id="c3a23-306">Veja aqui um exemplo.</span><span class="sxs-lookup"><span data-stu-id="c3a23-306">Here is an example.</span></span>

    ```json
    {
        "access_token": "{Returned_Token}",
        "token_type": "bearer",
        "expires_in": 1200
    }
    ```

### <a name="sample-request"></a><a name="inventory-visibility-sample-request"></a><span data-ttu-id="c3a23-307">Solicitação de exemplo</span><span class="sxs-lookup"><span data-stu-id="c3a23-307">Sample Request</span></span>

<span data-ttu-id="c3a23-308">Para sua referência, veja aqui um exemplo de solicitação de HTTP. Você pode usar qualquer ferramenta ou linguagem de programação para enviar essa solicitação, como ``Postman``.</span><span class="sxs-lookup"><span data-stu-id="c3a23-308">For your reference, here is a sample http request, you can use any tools or coding language to send this request, such as  ``Postman``.</span></span>

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

### <a name="configure-the-inventory-visibility-api"></a><a name="inventory-visibility-configuration"></a><span data-ttu-id="c3a23-309">Configurar a API da Visibilidade de Estoque</span><span class="sxs-lookup"><span data-stu-id="c3a23-309">Configure the Inventory Visibility API</span></span>

<span data-ttu-id="c3a23-310">Antes de usar o serviço, você deve concluir as configurações descritas nas subseções a seguir.</span><span class="sxs-lookup"><span data-stu-id="c3a23-310">Before using the service, you must complete the configurations described in the following subsections.</span></span> <span data-ttu-id="c3a23-311">A configuração pode variar com base nos detalhes do seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="c3a23-311">The configuration may vary based on the details of your environment.</span></span> <span data-ttu-id="c3a23-312">Ela inclui principalmente quatro partes:</span><span class="sxs-lookup"><span data-stu-id="c3a23-312">It primarily includes four parts:</span></span>

- [<span data-ttu-id="c3a23-313">Particionamento</span><span class="sxs-lookup"><span data-stu-id="c3a23-313">Partitioning</span></span>](#partitioning)
- [<span data-ttu-id="c3a23-314">Configurações de dimensões</span><span class="sxs-lookup"><span data-stu-id="c3a23-314">Dimension configurations</span></span>](#dimension-configurations)
- [<span data-ttu-id="c3a23-315">Indexando</span><span class="sxs-lookup"><span data-stu-id="c3a23-315">Indexing</span></span>](#indexing)
- [<span data-ttu-id="c3a23-316">Medida personalizada</span><span class="sxs-lookup"><span data-stu-id="c3a23-316">Custom measurement</span></span>](#custom-measurement)

#### <a name="partitioning"></a><span data-ttu-id="c3a23-317">Particionamento</span><span class="sxs-lookup"><span data-stu-id="c3a23-317">Partitioning</span></span>

<span data-ttu-id="c3a23-318">O particionamento pode influenciar significativamente o desempenho da API da Visibilidade de Estoque.</span><span class="sxs-lookup"><span data-stu-id="c3a23-318">Partitioning can significantly influence the performance of the Inventory Visibility API.</span></span> <span data-ttu-id="c3a23-319">É uma boa ideia definir um esquema que permita pequenos agrupamentos de dados e, ao mesmo tempo, permita consultas de dados significativas.</span><span class="sxs-lookup"><span data-stu-id="c3a23-319">It's a good idea to define a scheme that allows for small groupings of data while still allowing for meaningful data queries.</span></span>

<span data-ttu-id="c3a23-320">A `organizationId` (`dataAreaId` no Supply Chain Management) sempre fará parte do particionamento e, por padrão, a Visibilidade de Estoque é configurada para particionar por dimensões como *Local + Localização*.</span><span class="sxs-lookup"><span data-stu-id="c3a23-320">The `organizationId` (`dataAreaId` in Supply Chain Management) will always be part of the partitioning, and by default Inventory Visibility is set to partition by dimensions as *Site + Location*.</span></span> <span data-ttu-id="c3a23-321">Isso significa que o serviço sempre deve ser consultado com essas dimensões definidas nos filtros.</span><span class="sxs-lookup"><span data-stu-id="c3a23-321">This means that the service must always be queried with these dimensions defined on the filters.</span></span>

> [!NOTE]
> <span data-ttu-id="c3a23-322">*Local* e *Localização* são duas dimensões padrão gerais na Visibilidade de Estoque.</span><span class="sxs-lookup"><span data-stu-id="c3a23-322">*Site* and *Location* are two general default dimensions in Inventory Visibility.</span></span> <span data-ttu-id="c3a23-323">No Supply Chain Management, essas dimensões são chamadas de *Local* (`InventSiteId`) e *Depósito* (`InventLocationId`)</span><span class="sxs-lookup"><span data-stu-id="c3a23-323">In Supply Chain Management, those dimensions are called *Site* (`InventSiteId`) and *Warehouse* (`InventLocationId`)</span></span>

### <a name="dimension-configurations"></a><span data-ttu-id="c3a23-324">Configurações de dimensões</span><span class="sxs-lookup"><span data-stu-id="c3a23-324">Dimension configurations</span></span>

<span data-ttu-id="c3a23-325">A Visibilidade de Estoque fornecerá uma lista de dimensões padrão gerais para habilitar a integração de sistemas de várias fontes.</span><span class="sxs-lookup"><span data-stu-id="c3a23-325">Inventory Visibility will provide a list of general default dimensions to enable the multiple source system integration.</span></span>

<span data-ttu-id="c3a23-326">A tabela a seguir lista as dimensões de estoque que serão os nomes de dimensão padrão na Visibilidade de Estoque.</span><span class="sxs-lookup"><span data-stu-id="c3a23-326">The following table lists the inventory dimensions that will be the default dimension names in Inventory Visibility.</span></span>

| <span data-ttu-id="c3a23-327">Tipo de dimensão</span><span class="sxs-lookup"><span data-stu-id="c3a23-327">Dimension type</span></span> | <span data-ttu-id="c3a23-328">Nome da dimensão</span><span class="sxs-lookup"><span data-stu-id="c3a23-328">Dimension name</span></span> |
|---|---|
| <span data-ttu-id="c3a23-329">Produto</span><span class="sxs-lookup"><span data-stu-id="c3a23-329">Product</span></span> | `ColorId` |
| <span data-ttu-id="c3a23-330">Produto</span><span class="sxs-lookup"><span data-stu-id="c3a23-330">Product</span></span> | `SizeId` |
| <span data-ttu-id="c3a23-331">Produto</span><span class="sxs-lookup"><span data-stu-id="c3a23-331">Product</span></span> | `StyleId` |
| <span data-ttu-id="c3a23-332">Produto</span><span class="sxs-lookup"><span data-stu-id="c3a23-332">Product</span></span> | `ConfigId` |
| <span data-ttu-id="c3a23-333">Rastreamento</span><span class="sxs-lookup"><span data-stu-id="c3a23-333">Tracking</span></span> | `BatchId` |
| <span data-ttu-id="c3a23-334">Rastreamento</span><span class="sxs-lookup"><span data-stu-id="c3a23-334">Tracking</span></span> | `SerialId` |
| <span data-ttu-id="c3a23-335">Localização</span><span class="sxs-lookup"><span data-stu-id="c3a23-335">Location</span></span> | `LocationId` |
| <span data-ttu-id="c3a23-336">Localização</span><span class="sxs-lookup"><span data-stu-id="c3a23-336">Location</span></span> | `SiteId` |
| <span data-ttu-id="c3a23-337">Status do Estoque</span><span class="sxs-lookup"><span data-stu-id="c3a23-337">Inventory Status</span></span> | `StatusId` |
| <span data-ttu-id="c3a23-338">Específico do Depósito</span><span class="sxs-lookup"><span data-stu-id="c3a23-338">Warehouse Specific</span></span> | `WMSLocationId` |
| <span data-ttu-id="c3a23-339">Específico do Depósito</span><span class="sxs-lookup"><span data-stu-id="c3a23-339">Warehouse Specific</span></span> | `WMSPalletId` |
| <span data-ttu-id="c3a23-340">Específico do Depósito</span><span class="sxs-lookup"><span data-stu-id="c3a23-340">Warehouse Specific</span></span> | `LicensePlateId` |

> [!NOTE]
> <span data-ttu-id="c3a23-341">O tipo de dimensão listado na tabela anterior é somente para referência.</span><span class="sxs-lookup"><span data-stu-id="c3a23-341">The dimension type listed in the previous table is for reference only.</span></span> <span data-ttu-id="c3a23-342">Não é necessário definir o tipo de dimensão na Visibilidade de Estoque.</span><span class="sxs-lookup"><span data-stu-id="c3a23-342">You don't need to define the dimension type in Inventory Visibility.</span></span>

<span data-ttu-id="c3a23-343">Se uma dimensão personalizada existir e precisar fluir para um valor padrão quando consumida pela Visibilidade de Estoque, você poderá configurar o nome **Dimensão personalizada** na Visibilidade de Estoque.</span><span class="sxs-lookup"><span data-stu-id="c3a23-343">If a custom dimension exists and needs to flow to a default value when consumed by Inventory Visibility, you can configure the **Custom dimension** name in Inventory Visibility.</span></span>

<span data-ttu-id="c3a23-344">Os sistemas externos acessam a Visibilidade de Estoque por meio de APIs RESTful que habilitam informações de disponibilidade sobre determinados conjuntos de dimensões a serem consultadas.</span><span class="sxs-lookup"><span data-stu-id="c3a23-344">External systems access Inventory Visibility through RESTful APIs that enable on-hand information on given sets of dimensions to be queried.</span></span> <span data-ttu-id="c3a23-345">Para a integração, a Visibilidade de Estoque permite configurar a *fonte de dados do canal externo* e a dimensão de origem para as *dimensões de destino* na Visibilidade de Estoque.</span><span class="sxs-lookup"><span data-stu-id="c3a23-345">For the integration, Inventory Visibility enables you to configure the *external channel data source* and the source dimension to the *target dimensions* in Inventory Visibility.</span></span>

<span data-ttu-id="c3a23-346">As dimensões de destino devem ser uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="c3a23-346">The target dimensions should be one of the following:</span></span>

- <span data-ttu-id="c3a23-347">Dimensões padrão na Visibilidade de Estoque</span><span class="sxs-lookup"><span data-stu-id="c3a23-347">Default dimensions in Inventory Visibility</span></span>
- <span data-ttu-id="c3a23-348">Dimensões personalizadas</span><span class="sxs-lookup"><span data-stu-id="c3a23-348">Custom dimensions</span></span>

<span data-ttu-id="c3a23-349">A finalidade da configuração de dimensões é padronizar a integração de vários sistemas para a consulta em dimensões e o evento de lançamento com dimensões.</span><span class="sxs-lookup"><span data-stu-id="c3a23-349">The purpose of dimension configuration is to standardize the multi-system integration for the query on dimensions and the posting event with dimensions.</span></span>

#### <a name="indexing"></a><span data-ttu-id="c3a23-350">Indexando</span><span class="sxs-lookup"><span data-stu-id="c3a23-350">Indexing</span></span>

<span data-ttu-id="c3a23-351">Na maioria das vezes, a consulta de estoque disponível não só estará no nível "total" mais alto, mas talvez você queira ver resultados agregados com base nas dimensões de estoque.</span><span class="sxs-lookup"><span data-stu-id="c3a23-351">Most of the time, the inventory on-hand query will not only be on the highest "total" level, but you may want to see results aggregated based on the inventory dimensions.</span></span>

<span data-ttu-id="c3a23-352">A Visibilidade de Estoque fornece flexibilidade, permitindo que você configure os índices, que se baseiam na dimensão ou na combinação das dimensões.</span><span class="sxs-lookup"><span data-stu-id="c3a23-352">Inventory Visibility provides flexibility by allowing you to set up the indexes, which are based on the dimension or the combination of the dimensions.</span></span>

> [!NOTE]
> <span data-ttu-id="c3a23-353">No momento, só é possível configurar índices para, no máximo, cinco.</span><span class="sxs-lookup"><span data-stu-id="c3a23-353">Currently, you can only configure indexes to a maximum of five.</span></span> <span data-ttu-id="c3a23-354">É necessário considerar cuidadosamente qual dimensão ou combinação de dimensões você usará antes da implementação para garantir que ela atenderá às suas necessidades comerciais.</span><span class="sxs-lookup"><span data-stu-id="c3a23-354">You need to carefully consider which dimension or dimension combination you will use before the implementation to ensure that it will meet your business needs.</span></span> <span data-ttu-id="c3a23-355">Por exemplo, se você quiser consultar produtos da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="c3a23-355">For example, if you want to query products as follows:</span></span>

- <span data-ttu-id="c3a23-356">Consultar o produto agregado disponível por meio das dimensões *Cor* e *Tamanho*.</span><span class="sxs-lookup"><span data-stu-id="c3a23-356">Query the aggregated product on-hand by the *Color* and *Size* dimensions.</span></span>
- <span data-ttu-id="c3a23-357">Em alguns casos, você só deseja consultar o produto no total.</span><span class="sxs-lookup"><span data-stu-id="c3a23-357">In some cases, you just want to query on the product in total.</span></span>

<span data-ttu-id="c3a23-358">Você teria dois índices definidos da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="c3a23-358">You would have two indexes defined as the following:</span></span>

- `["ColorId", "SizeId"]`
- `[]`

<span data-ttu-id="c3a23-359">O colchete vazio agregará com base na ID do produto na partição.</span><span class="sxs-lookup"><span data-stu-id="c3a23-359">The empty bracket will aggregate based on the product ID within the partition.</span></span>

<span data-ttu-id="c3a23-360">A indexação define como você pode agrupar os resultados com base na configuração de consulta `groupBy`.</span><span class="sxs-lookup"><span data-stu-id="c3a23-360">The indexing defines how you can group your results based on the `groupBy` query setting.</span></span> <span data-ttu-id="c3a23-361">Nesse caso, se você não definir nenhum valor `groupBy`, obterá totais por `productid`.</span><span class="sxs-lookup"><span data-stu-id="c3a23-361">In this case if you don't define any `groupBy` values, you'll get totals by `productid`.</span></span> <span data-ttu-id="c3a23-362">Caso contrário, se você definir `groupBy` como `groupBy=ColorId&groupBy=SizeId`, obterá várias linhas retornadas, com base nas diferentes combinações de cor e tamanho no sistema.</span><span class="sxs-lookup"><span data-stu-id="c3a23-362">Otherwise, if you define `groupBy` as `groupBy=ColorId&groupBy=SizeId`, you'll get multiple lines returned, based on the different color and size combinations in the system.</span></span>

<span data-ttu-id="c3a23-363">Você pode colocar os critérios de consulta no corpo da solicitação.</span><span class="sxs-lookup"><span data-stu-id="c3a23-363">You can put your query criteria in the request body.</span></span>

<span data-ttu-id="c3a23-364">Veja uma consulta de exemplo no produto com combinação de cor e tamanho.</span><span class="sxs-lookup"><span data-stu-id="c3a23-364">Here is a sample query on the product with color and size combination.</span></span>

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

<span data-ttu-id="c3a23-365">No campo `filters`, somente o `ProductId` permite a inserção de vários valores no momento.</span><span class="sxs-lookup"><span data-stu-id="c3a23-365">For the `filters` field, currently only `ProductId` supports multiple values.</span></span> <span data-ttu-id="c3a23-366">Se o `ProductId` for uma matriz vazia, todos os produtos serão consultados.</span><span class="sxs-lookup"><span data-stu-id="c3a23-366">If the `ProductId` is an empty array, all products will be queried.</span></span>

#### <a name="custom-measurement"></a><span data-ttu-id="c3a23-367">Medida personalizada</span><span class="sxs-lookup"><span data-stu-id="c3a23-367">Custom measurement</span></span>

<span data-ttu-id="c3a23-368">As quantidades de medida padrão estão vinculadas ao Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="c3a23-368">The default measurement quantities are linked to Supply Chain Management.</span></span> <span data-ttu-id="c3a23-369">No entanto, talvez você deseje ter uma quantidade composta de uma combinação das medidas padrão.</span><span class="sxs-lookup"><span data-stu-id="c3a23-369">However, you may want to have a quantity that is made up of a combination of the default measurements.</span></span> <span data-ttu-id="c3a23-370">Para isso, você pode ter uma configuração de quantidades personalizadas, que será adicionada à saída das consultas de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="c3a23-370">To do this, you can have a configuration of custom quantities, which will be added to the output of the on-hand queries.</span></span>

<span data-ttu-id="c3a23-371">A funcionalidade simplesmente permite definir um conjunto de medidas que será adicionado e/ou um conjunto de medidas que será subtraído para formar a medida personalizada.</span><span class="sxs-lookup"><span data-stu-id="c3a23-371">The functionality simply allows you to define a set of measures that will be added, and/or a set of measures that will be subtracted, in order to form the custom measurement.</span></span>

<span data-ttu-id="c3a23-372">Por exemplo, com a seguinte condição de consulta, você configurará a quantidade de medidas personalizadas como `MyCustomAvailableforReservation` para ser consumida pelo sistema de consumo.</span><span class="sxs-lookup"><span data-stu-id="c3a23-372">For example, with the following query condition, you will configure the custom measurement quantity as `MyCustomAvailableforReservation` to be consumed by the consumption system.</span></span>

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



| <span data-ttu-id="c3a23-373">Sistema de consumo</span><span class="sxs-lookup"><span data-stu-id="c3a23-373">Consumption system</span></span> | <span data-ttu-id="c3a23-374">Medidas calculadas</span><span class="sxs-lookup"><span data-stu-id="c3a23-374">Calculated measurers</span></span> | <span data-ttu-id="c3a23-375">Fonte de dados</span><span class="sxs-lookup"><span data-stu-id="c3a23-375">Data source</span></span> | <span data-ttu-id="c3a23-376">Modificador</span><span class="sxs-lookup"><span data-stu-id="c3a23-376">Modifier</span></span> | <span data-ttu-id="c3a23-377">Tipo de cálculo do modificador</span><span class="sxs-lookup"><span data-stu-id="c3a23-377">Modifier calculation type</span></span> |
|---|---|---|---|---|
| `CustomChannel` | `MyCustomAvailableforReservation` | `fno` | `availphysical` | <span data-ttu-id="c3a23-378">Adição</span><span class="sxs-lookup"><span data-stu-id="c3a23-378">Addition</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `fno` | `orderedintotal` | <span data-ttu-id="c3a23-379">Adição</span><span class="sxs-lookup"><span data-stu-id="c3a23-379">Addition</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `fno` | `orderedreserved` | <span data-ttu-id="c3a23-380">Subtração</span><span class="sxs-lookup"><span data-stu-id="c3a23-380">Subtraction</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `mypos` | `inbound` | <span data-ttu-id="c3a23-381">Adição</span><span class="sxs-lookup"><span data-stu-id="c3a23-381">Addition</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `mypos` | `outbound` | <span data-ttu-id="c3a23-382">Subtração</span><span class="sxs-lookup"><span data-stu-id="c3a23-382">Subtraction</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `exterchannel` | `received` | <span data-ttu-id="c3a23-383">Adição</span><span class="sxs-lookup"><span data-stu-id="c3a23-383">Addition</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `exterchannel` | `scheduled` | <span data-ttu-id="c3a23-384">Adição</span><span class="sxs-lookup"><span data-stu-id="c3a23-384">Addition</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `exterchannel` | `issued` | <span data-ttu-id="c3a23-385">Subtração</span><span class="sxs-lookup"><span data-stu-id="c3a23-385">Subtraction</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `exterchannel` | `reserved` | <span data-ttu-id="c3a23-386">Subtração</span><span class="sxs-lookup"><span data-stu-id="c3a23-386">Subtraction</span></span> |

<span data-ttu-id="c3a23-387">Com isso, a consulta na quantidade de medidas personalizadas retornará a seguinte saída.</span><span class="sxs-lookup"><span data-stu-id="c3a23-387">With that, the query on the custom measurement quantity will return the following output.</span></span>

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

<span data-ttu-id="c3a23-388">A saída `MyCustomAvailableforReservation` se baseia na configuração de cálculo nas medidas personalizadas como:</span><span class="sxs-lookup"><span data-stu-id="c3a23-388">The `MyCustomAvailableforReservation` output is based on the calculation setting in the custom measurements as:</span></span>  
 <span data-ttu-id="c3a23-389">*100 + 50 + 80 + 90 + 30 &ndash; 10 &ndash; 20 &ndash; 60 &ndash; 40 = 220*</span><span class="sxs-lookup"><span data-stu-id="c3a23-389">*100 + 50 + 80 + 90 + 30 &ndash; 10 &ndash; 20 &ndash; 60 &ndash; 40 = 220*</span></span>

### <a name="posting-on-hand-changes"></a><span data-ttu-id="c3a23-390">Lançar alterações de disponibilidade</span><span class="sxs-lookup"><span data-stu-id="c3a23-390">Posting on-hand changes</span></span>

<span data-ttu-id="c3a23-391">A URL exata na qual o evento será lançado dependerá da sua região geográfica.</span><span class="sxs-lookup"><span data-stu-id="c3a23-391">The exact URL that the event will be posted to will depend on your geographical region.</span></span> <span data-ttu-id="c3a23-392">Ela terá a forma:</span><span class="sxs-lookup"><span data-stu-id="c3a23-392">It will take the form:</span></span>

`https://{serviceURL}/api/environment/{environmentId}/onhand`

<span data-ttu-id="c3a23-393">Quando autenticada, essa URL pode ser usada junto com o método HTTP `POST` para enviar eventos de alteração de disponibilidade para o serviço.</span><span class="sxs-lookup"><span data-stu-id="c3a23-393">When authenticated, this URL can be used along with the HTTP `POST` method to send on-hand change events to the service.</span></span>

<span data-ttu-id="c3a23-394">Um cabeçalho especial é usado para a comunicação com os serviços do Dynamics 365 por meio de solicitações HTTP, indicando a ID de ambiente da instância do Supply Chain Management à qual os dados estão vinculados.</span><span class="sxs-lookup"><span data-stu-id="c3a23-394">A special header is used for communicating with Dynamics 365 services through HTTP requests, denoting the environment ID of the Supply Chain Management instance the data is linked to.</span></span> <span data-ttu-id="c3a23-395">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="c3a23-395">For example:</span></span>

`x-ms-environment-id: 2db79622-f97a-4d64-9844-d12efed41796`

#### <a name="posting-on-hand-changes-query-example-1"></a><span data-ttu-id="c3a23-396">Exemplo de consulta de lançamento de alterações de disponibilidade 1</span><span class="sxs-lookup"><span data-stu-id="c3a23-396">Posting on-hand changes query example 1</span></span>

<span data-ttu-id="c3a23-397">Este exemplo mostra um cenário no qual você definirá a configuração de dimensões no Power Apps.</span><span class="sxs-lookup"><span data-stu-id="c3a23-397">This example shows a scenario where you will set up the dimension configuration in Power Apps.</span></span>

<span data-ttu-id="c3a23-398">Use a seguinte consulta para configurar o mapeamento de dimensões no Power Apps:</span><span class="sxs-lookup"><span data-stu-id="c3a23-398">Use the following query to configure the dimension mapping in Power Apps:</span></span>

```json
{
    "PosSizeId": "SizeId",
    "PosColorId": "ColorId",
    "PosSiteId": "SiteId",
    "PosLocationId": "LocationId"
}
```

<span data-ttu-id="c3a23-399">Agora, você pode especificar a `dimensionDataSource` e usar dimensões personalizadas nas suas consultas.</span><span class="sxs-lookup"><span data-stu-id="c3a23-399">Now you can specify the `dimensionDataSource` and use custom dimensions in your queries.</span></span> <span data-ttu-id="c3a23-400">O sistema converterá automaticamente as dimensões personalizadas em dimensões base.</span><span class="sxs-lookup"><span data-stu-id="c3a23-400">The system will automatically convert custom dimensions to base dimensions.</span></span>

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

#### <a name="posting-on-hand-changes-query-example-2"></a><span data-ttu-id="c3a23-401">Exemplo de consulta de lançamento de alterações de disponibilidade 2</span><span class="sxs-lookup"><span data-stu-id="c3a23-401">Posting on-hand changes query example 2</span></span>

<span data-ttu-id="c3a23-402">Este exemplo mostra um cenário em que não há mapeamentos definidos para a configuração de dimensões no Power Apps, portanto, o lançamento também deve usar as dimensões base.</span><span class="sxs-lookup"><span data-stu-id="c3a23-402">This example shows a scenario where no mappings are set up for the dimension configuration in Power Apps, so the posting should also use the base dimensions.</span></span> <span data-ttu-id="c3a23-403">Todas as dimensões devem ser dimensões base quando o campo `dimensionDataSource` é nulo, vazio ou um espaço em branco.</span><span class="sxs-lookup"><span data-stu-id="c3a23-403">All dimensions must be base dimensions when the `dimensionDataSource` field is null, empty, or whitespace.</span></span>

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

#### <a name="json-document-field-properties"></a><span data-ttu-id="c3a23-404">Propriedades de campo do documento JSON</span><span class="sxs-lookup"><span data-stu-id="c3a23-404">JSON document field properties</span></span>

<span data-ttu-id="c3a23-405">Os campos dos exemplos de consulta JSON fornecidos anteriormente têm as propriedades listadas na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="c3a23-405">The fields from the JSON query examples provided previously have the properties listed in the following table.</span></span>

| <span data-ttu-id="c3a23-406">ID do campo</span><span class="sxs-lookup"><span data-stu-id="c3a23-406">Field ID</span></span> | <span data-ttu-id="c3a23-407">descrição</span><span class="sxs-lookup"><span data-stu-id="c3a23-407">Description</span></span> |
|---|---|
| `id` | <span data-ttu-id="c3a23-408">Uma ID exclusiva para o evento de alteração específico.</span><span class="sxs-lookup"><span data-stu-id="c3a23-408">A unique ID for the specific change event.</span></span> <span data-ttu-id="c3a23-409">Essa ID é usada para garantir que, se a comunicação com o serviço falhar durante o lançamento, o reenvio do evento não resultará no mesmo evento sendo contado duas vezes no sistema.</span><span class="sxs-lookup"><span data-stu-id="c3a23-409">This ID is used to ensure that if communication with the service fails during posting, resubmitting the event would not result in the same event being counted twice in the system.</span></span> |
| `organizationId` | <span data-ttu-id="c3a23-410">O identificador da organização vinculada ao evento.</span><span class="sxs-lookup"><span data-stu-id="c3a23-410">The identifier of the organization linked to the event.</span></span> <span data-ttu-id="c3a23-411">Isso é mapeado para as IDs de áreas de dados ou organizações do Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="c3a23-411">This maps to Supply Chain Management organizations or data area IDs.</span></span> |
| `productId` | <span data-ttu-id="c3a23-412">O identificador do produto em questão.</span><span class="sxs-lookup"><span data-stu-id="c3a23-412">The identifier of the product in question.</span></span> |
| `quantity` | <span data-ttu-id="c3a23-413">A quantidade pela qual a disponibilidade precisa ser alterada.</span><span class="sxs-lookup"><span data-stu-id="c3a23-413">The quantity by which the on-hand needs to be changed.</span></span> <span data-ttu-id="c3a23-414">Se, por exemplo, 10 novos bagels forem adicionados a uma prateleira, esse valor será 10.</span><span class="sxs-lookup"><span data-stu-id="c3a23-414">If, for instance, 10 new bagels were added to a shelf, this value would be 10.</span></span> <span data-ttu-id="c3a23-415">Se 3 bagels forem removidos da prateleira ou vendidos, esse valor será -3.</span><span class="sxs-lookup"><span data-stu-id="c3a23-415">If 3 bagels were then removed from the shelf or sold, this value would be -3.</span></span> |
| `dimensionDataSource` | <span data-ttu-id="c3a23-416">A fonte de dados das dimensões usadas no evento e na consulta de alteração de lançamento.</span><span class="sxs-lookup"><span data-stu-id="c3a23-416">The data source of the dimensions used in the posting change event and query.</span></span> <span data-ttu-id="c3a23-417">Se você especificar a fonte de dados, poderá usar as dimensões personalizadas da fonte de dados especificada.</span><span class="sxs-lookup"><span data-stu-id="c3a23-417">If you specify the data source, you can use the custom dimensions from the specified data source.</span></span> <span data-ttu-id="c3a23-418">Com a configuração de dimensões, a Visibilidade de Estoque pode mapear as dimensões personalizadas para as dimensões padrão gerais.</span><span class="sxs-lookup"><span data-stu-id="c3a23-418">With the dimension configuration, Inventory Visibility can map the custom dimensions to the general default dimensions.</span></span> <span data-ttu-id="c3a23-419">Se a `dimensionDataSource` não estiver especificada, você só poderá usar as dimensões padrão gerais nas suas consultas.</span><span class="sxs-lookup"><span data-stu-id="c3a23-419">If the `dimensionDataSource` is not specified, you can only use the general default dimensions in your queries.</span></span>   |
| `dimensions` | <span data-ttu-id="c3a23-420">Um recipiente dinâmico de pares de chave/valor.</span><span class="sxs-lookup"><span data-stu-id="c3a23-420">A dynamic bag of key/value pairs.</span></span> <span data-ttu-id="c3a23-421">Eles serão mapeados para algumas das dimensões no Supply Chain Management, mas você também pode adicionar dimensões personalizadas (como *Origem*) que podem indicar se o evento é proveniente do Supply Chain Management ou de um sistema externo.</span><span class="sxs-lookup"><span data-stu-id="c3a23-421">These will map to some of the dimensions in Supply Chain Management, but you could also add custom dimensions (like *Source*) that may denote if the event was coming from Supply Chain Management or an external system.</span></span> |

### <a name="querying-current-on-hand"></a><span data-ttu-id="c3a23-422">Consultar a disponibilidade atual</span><span class="sxs-lookup"><span data-stu-id="c3a23-422">Querying current on-hand</span></span>

<span data-ttu-id="c3a23-423">O ponto de extremidade para consultar a disponibilidade atual terá uma URL semelhante:</span><span class="sxs-lookup"><span data-stu-id="c3a23-423">The endpoint for querying the current on-hand will have a similar URL:</span></span>

`https://{serviceURL}/api/environment/{environmentId}/onhand/indexquery`

<span data-ttu-id="c3a23-424">Ela será consultada com o método HTTP `POST`.</span><span class="sxs-lookup"><span data-stu-id="c3a23-424">It will be queried with the HTTP `POST` method.</span></span>

#### <a name="current-on-hand-query-example-1"></a><span data-ttu-id="c3a23-425">Exemplo de consulta da disponibilidade atual 1</span><span class="sxs-lookup"><span data-stu-id="c3a23-425">Current on-hand query example 1</span></span>

<span data-ttu-id="c3a23-426">Este exemplo mostra um cenário no qual você já concluiu a configuração de dimensões no Power Apps.</span><span class="sxs-lookup"><span data-stu-id="c3a23-426">This example shows a scenario where you have already completed the dimension configuration in Power Apps.</span></span>

<span data-ttu-id="c3a23-427">Use a seguinte consulta para configurar o mapeamento de dimensões no Power Apps:</span><span class="sxs-lookup"><span data-stu-id="c3a23-427">Use the following query to configure the dimension mapping in Power Apps:</span></span>

```json
{
    "PosSizeId": "SizeId",
    "PosColorId": "ColorId",
    "PosSiteId": "SiteId",
    "PosLocationId": "LocationId"
}
```

<span data-ttu-id="c3a23-428">Agora, você pode especificar a `dimensionDataSource` e usar dimensões personalizadas nas suas consultas.</span><span class="sxs-lookup"><span data-stu-id="c3a23-428">Now you can specify the `dimensionDataSource` and use custom dimensions in your queries.</span></span> <span data-ttu-id="c3a23-429">O sistema converterá automaticamente as dimensões personalizadas em dimensões base.</span><span class="sxs-lookup"><span data-stu-id="c3a23-429">The system will automatically convert custom dimensions to base dimensions.</span></span> <span data-ttu-id="c3a23-430">Você pode especificar a `DimensionDataSource` em `filters` e especificar dimensões personalizadas em `filters` e `groupByValues`.</span><span class="sxs-lookup"><span data-stu-id="c3a23-430">You can specify the `DimensionDataSource` in `filters` and specify custom dimensions in both `filters` and `groupByValues`.</span></span> <span data-ttu-id="c3a23-431">O sistema converterá automaticamente as dimensões personalizadas em dimensões base.</span><span class="sxs-lookup"><span data-stu-id="c3a23-431">The system will automatically convert custom dimensions to base dimensions.</span></span>

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

#### <a name="current-on-hand-query-example-2"></a><span data-ttu-id="c3a23-432">Exemplo de consulta da disponibilidade atual 2</span><span class="sxs-lookup"><span data-stu-id="c3a23-432">Current on-hand query example 2</span></span>

<span data-ttu-id="c3a23-433">Este exemplo mostra um cenário em que não há mapeamentos definidos para a configuração de dimensões no Power Apps, portanto, o lançamento também deve usar as dimensões base.</span><span class="sxs-lookup"><span data-stu-id="c3a23-433">This example shows a scenario where no mappings are set up for the dimension configuration in Power Apps, so the posting should also use the base dimensions.</span></span> <span data-ttu-id="c3a23-434">Todas as dimensões devem ser dimensões base quando o campo `dimensionDataSource`, em `filters`, é nulo, vazio ou um espaço em branco.</span><span class="sxs-lookup"><span data-stu-id="c3a23-434">All dimensions must be base dimensions when the `dimensionDataSource` field, under `filters` is null, empty, or whitespace.</span></span>

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

#### <a name="example-return-result"></a><span data-ttu-id="c3a23-435">Exemplo de retorno de resultado</span><span class="sxs-lookup"><span data-stu-id="c3a23-435">Example return result</span></span>

<span data-ttu-id="c3a23-436">As consultas mostradas nos exemplos anteriores poderiam retornar um resultado como este.</span><span class="sxs-lookup"><span data-stu-id="c3a23-436">The queries shown in the previous examples could return a result like this.</span></span>

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

<span data-ttu-id="c3a23-437">Observe que os campos de quantidades estão estruturados como um dicionário de medidas e seus valores associados.</span><span class="sxs-lookup"><span data-stu-id="c3a23-437">Note that the quantities fields are structured as a dictionary of measures and their associated values.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
