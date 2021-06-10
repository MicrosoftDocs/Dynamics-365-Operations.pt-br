---
title: Atualizar para o modelo de catálogo de endereços global e de participantes
description: Este tópico descreve como atualizar dados de gravação dupla para o modelo de catálogo de endereços global e do participante.
author: RamaKrishnamoorthy
ms.date: 03/31/2021
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2021-03-31
ms.openlocfilehash: 90ddbe704ab21d62752b581a813601e8986c2103
ms.sourcegitcommit: 180548e3c10459776cf199989d3753e0c1555912
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/28/2021
ms.locfileid: "6112664"
---
# <a name="upgrade-to-the-party-and-global-address-book-model"></a><span data-ttu-id="e6212-103">Atualizar para o modelo de catálogo de endereços global e de participantes</span><span class="sxs-lookup"><span data-stu-id="e6212-103">Upgrade to the party and global address book model</span></span>

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="e6212-104">O [modelo do Microsoft Azure Data Factory](https://aka.ms/dual-write-gab-adf) ajuda você a atualizar os dados existentes das tabelas **Conta**, **Contato** e **Fornecedor** em uma gravação dupla para o modelo de catálogo de endereços global e do participante.</span><span class="sxs-lookup"><span data-stu-id="e6212-104">The [Microsoft Azure Data Factory template](https://aka.ms/dual-write-gab-adf) helps you upgrade existing **Account**, **Contact**, and **Vendor** table data in dual-write to the party and global address book model.</span></span> <span data-ttu-id="e6212-105">O modelo reconcilia os dados de aplicativos do Finance and Operations e aplicativos do Customer Engagement.</span><span class="sxs-lookup"><span data-stu-id="e6212-105">The template reconciles the data from both finance and operations apps and customer engagement applications.</span></span> <span data-ttu-id="e6212-106">No final do processo, os campos **Participante** e **Contato** para os registros de **Participante** serão criados e associados aos registros de **Conta**, **Contato** e **Fornecedor** nos aplicativos do participação do cliente.</span><span class="sxs-lookup"><span data-stu-id="e6212-106">At the end of the process, **Party** and **Contact** fields for **Party** records will be created and associated with **Account**, **Contact**, and **Vendor** records in customer engagement applications.</span></span> <span data-ttu-id="e6212-107">Um arquivo .csv (`FONewParty.csv`) é gerado para criar novos registros de **Participante** no aplicativo do Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="e6212-107">A .csv file (`FONewParty.csv`) is generated to create new **Party** records inside the finance and operations app.</span></span> <span data-ttu-id="e6212-108">Este tópico fornece instruções sobre como usar o modelo do Data Factory e atualizar seus dados.</span><span class="sxs-lookup"><span data-stu-id="e6212-108">This topic provides instructions about how to use the Data Factory template and upgrade your data.</span></span>

<span data-ttu-id="e6212-109">Se não tiver nenhuma personalização, você poderá usar o modelo no estado em que se encontra.</span><span class="sxs-lookup"><span data-stu-id="e6212-109">If you don’t have any customizations, you can use the template as is.</span></span> <span data-ttu-id="e6212-110">Se tiver personalizações para **Conta**, **Contato** e **Fornecedor**, você deverá modificar o modelo usando as instruções a seguir.</span><span class="sxs-lookup"><span data-stu-id="e6212-110">If you have customizations for **Account**, **Contact**, and **Vendor** then you must modify the template using the following instructions.</span></span>

> [!NOTE]
> <span data-ttu-id="e6212-111">O modelo atualiza somente os dados do **Participante**.</span><span class="sxs-lookup"><span data-stu-id="e6212-111">The template only upgrades the **Party** data.</span></span> <span data-ttu-id="e6212-112">Em uma versão futura, os endereços postais e eletrônicos serão incluídos.</span><span class="sxs-lookup"><span data-stu-id="e6212-112">In a future release, postal and electronic addresses will be included.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="e6212-113">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="e6212-113">Prerequisites</span></span>

<span data-ttu-id="e6212-114">Os seguintes pré-requisitos são necessários para atualizar para o modelo de catálogo de endereços global e de terceiros:</span><span class="sxs-lookup"><span data-stu-id="e6212-114">The following prerequisites are required to upgrade to the party and global address book model:</span></span>

+ [<span data-ttu-id="e6212-115">Assinatura do Azure</span><span class="sxs-lookup"><span data-stu-id="e6212-115">Azure subscription</span></span>](https://portal.azure.com/)
+ [<span data-ttu-id="e6212-116">Acesso ao modelo</span><span class="sxs-lookup"><span data-stu-id="e6212-116">Access to the template</span></span>](https://aka.ms/dual-write-gab-adf)
+ <span data-ttu-id="e6212-117">Você deve ser um cliente de gravação dupla existente.</span><span class="sxs-lookup"><span data-stu-id="e6212-117">You must be an existing dual-write customer.</span></span>

## <a name="prepare-for-the-upgrade"></a><span data-ttu-id="e6212-118">Preparar-se para o upgrade</span><span class="sxs-lookup"><span data-stu-id="e6212-118">Prepare for the upgrade</span></span>
<span data-ttu-id="e6212-119">As seguintes atividades são necessárias para se preparar para a atualização:</span><span class="sxs-lookup"><span data-stu-id="e6212-119">The following activities are needed to prepare for the upgrade:</span></span>

+ <span data-ttu-id="e6212-120">**Totalmente sincronizado**: ambos os ambientes estão em um estado totalmente sincronizado para **Conta (Cliente)**, **Contato** e **Fornecedor**.</span><span class="sxs-lookup"><span data-stu-id="e6212-120">**Fully synced**: Both environments are in a fully synced state for **Account (Customer)**, **Contact**, and **Vendor**.</span></span>
+ <span data-ttu-id="e6212-121">**Chaves de integração**: as tabelas **Conta (Cliente)**, **Contato** e **Fornecedor** nos aplicativos de participação do cliente estão usando as chaves de integração prontas para uso que são enviadas.</span><span class="sxs-lookup"><span data-stu-id="e6212-121">**Integration keys**: **Account (Customer)**, **Contact**, and **Vendor** tables in customer engagement apps are using the integration keys that shipped out-of-the-box.</span></span> <span data-ttu-id="e6212-122">Se personalizou as chaves de integração, você deve personalizar o modelo.</span><span class="sxs-lookup"><span data-stu-id="e6212-122">If you customized the integration keys, you must customize the template.</span></span>
+ <span data-ttu-id="e6212-123">**Número do participante**: todos os registros de **Conta (Cliente)**, **Contato** e **Fornecedor** que serão atualizados têm um número de **Participante**.</span><span class="sxs-lookup"><span data-stu-id="e6212-123">**Party number**: All **Account (Customer)**, **Contact**, and **Vendor** records that will be upgraded have a **Party** number.</span></span> <span data-ttu-id="e6212-124">Registros sem um número de **Participante** serão ignorados.</span><span class="sxs-lookup"><span data-stu-id="e6212-124">Records without a **Party** number will be ignored.</span></span> <span data-ttu-id="e6212-125">Se desejar fazer upgrade desses registros, adicione um número de **Participante** a eles antes de iniciar o processo de upgrade.</span><span class="sxs-lookup"><span data-stu-id="e6212-125">If you want to upgrade those records, add a **Party** number to them before you start the upgrade process.</span></span>
+ <span data-ttu-id="e6212-126">**Interrupção do sistema**: durante o processo de upgrade, você terá de manter os ambientes do Finance and Operations e Customer Engagement offline.</span><span class="sxs-lookup"><span data-stu-id="e6212-126">**System outage**: During the upgrade process, you will have to take both the finance and operations and customer engagement environments offline.</span></span>
+ <span data-ttu-id="e6212-127">**Instantâneo**: tire instantâneos dos aplicativos do Finance and Operations e Customer Engagement.</span><span class="sxs-lookup"><span data-stu-id="e6212-127">**Snapshot**: Take snapshots of both the finance and operations apps and customer engagement apps.</span></span> <span data-ttu-id="e6212-128">Use os instantâneos para restaurar o estado anterior, se necessário.</span><span class="sxs-lookup"><span data-stu-id="e6212-128">Use the snapshots to restore the previous state if you need to.</span></span>

## <a name="deployment"></a><span data-ttu-id="e6212-129">Implantação</span><span class="sxs-lookup"><span data-stu-id="e6212-129">Deployment</span></span>

1. <span data-ttu-id="e6212-130">Baixe o modelo de [Dynamics-365-FastTrack-Implementation-Assets](https://aka.ms/dual-write-gab-adf).</span><span class="sxs-lookup"><span data-stu-id="e6212-130">Download the template from [Dynamics-365-FastTrack-Implementation-Assets](https://aka.ms/dual-write-gab-adf).</span></span>

2. <span data-ttu-id="e6212-131">Entre no [Microsoft Azure](https://portal.azure.com/).</span><span class="sxs-lookup"><span data-stu-id="e6212-131">Sign in to [Microsoft Azure](https://portal.azure.com/).</span></span>

3. <span data-ttu-id="e6212-132">Crie um [grupo de recursos](/azure/azure-resource-manager/management/manage-resource-groups-portal).</span><span class="sxs-lookup"><span data-stu-id="e6212-132">Create a [resource group](/azure/azure-resource-manager/management/manage-resource-groups-portal).</span></span>

4. <span data-ttu-id="e6212-133">Crie uma [conta de armazenamento](/azure/storage/common/storage-account-create?tabs=azure-portal) no grupo de recursos que você criou.</span><span class="sxs-lookup"><span data-stu-id="e6212-133">Create a [storage account](/azure/storage/common/storage-account-create?tabs=azure-portal) in the resource group that you created.</span></span>

5. <span data-ttu-id="e6212-134">Crie uma [data factory](/azure/data-factory/quickstart-create-data-factory-portal) no grupo de recursos que você criou acima.</span><span class="sxs-lookup"><span data-stu-id="e6212-134">Create a [data factory](/azure/data-factory/quickstart-create-data-factory-portal) in above resource group that you created.</span></span>

6. <span data-ttu-id="e6212-135">Abra a data Factory e selecione o bloco **Autoria e Monitoramento**.</span><span class="sxs-lookup"><span data-stu-id="e6212-135">Open the data factory and select the **Author & Monitor** tile.</span></span>

7. <span data-ttu-id="e6212-136">Na guia **Gerenciar**, selecione **Modelo de ARM**.</span><span class="sxs-lookup"><span data-stu-id="e6212-136">On the **Manage** tab, select **ARM template**.</span></span>

8. <span data-ttu-id="e6212-137">Selecione **Importar modelo ARM** para importar o modelo de **Participante**.</span><span class="sxs-lookup"><span data-stu-id="e6212-137">Select the **Import ARM template** to import the **Party** template.</span></span>

9. <span data-ttu-id="e6212-138">Importe o modelo para a data factory.</span><span class="sxs-lookup"><span data-stu-id="e6212-138">Import the template into the data factory.</span></span> <span data-ttu-id="e6212-139">Insira os valores a seguir para **Detalhes do projeto** e **Detalhes da instância**.</span><span class="sxs-lookup"><span data-stu-id="e6212-139">Enter the following values for **Project details** and **Instance details**.</span></span>

    <span data-ttu-id="e6212-140">Campo</span><span class="sxs-lookup"><span data-stu-id="e6212-140">Field</span></span> | <span data-ttu-id="e6212-141">Alíquota</span><span class="sxs-lookup"><span data-stu-id="e6212-141">Value</span></span>
    ---|---
    <span data-ttu-id="e6212-142">Assinatura</span><span class="sxs-lookup"><span data-stu-id="e6212-142">Subscription</span></span> | <span data-ttu-id="e6212-143">Assinatura do Azure</span><span class="sxs-lookup"><span data-stu-id="e6212-143">Azure subscription</span></span>
    <span data-ttu-id="e6212-144">Grupo de recursos</span><span class="sxs-lookup"><span data-stu-id="e6212-144">Resource group</span></span> | <span data-ttu-id="e6212-145">Forneça o mesmo recurso no qual a conta de armazenamento foi criada.</span><span class="sxs-lookup"><span data-stu-id="e6212-145">Provide same resource under which storage account is created.</span></span>
    <span data-ttu-id="e6212-146">Região</span><span class="sxs-lookup"><span data-stu-id="e6212-146">Region</span></span> | <span data-ttu-id="e6212-147">Especifique a região.</span><span class="sxs-lookup"><span data-stu-id="e6212-147">Specify region.</span></span>
    <span data-ttu-id="e6212-148">Nome da fábrica</span><span class="sxs-lookup"><span data-stu-id="e6212-148">Factory Name</span></span> | <span data-ttu-id="e6212-149">Especifique o nome da fábrica.</span><span class="sxs-lookup"><span data-stu-id="e6212-149">Specify factory name.</span></span>
    <span data-ttu-id="e6212-150">Chave principal_da entidade de serviço vinculada ao FO</span><span class="sxs-lookup"><span data-stu-id="e6212-150">FO Linked Service_service Principal Key</span></span> | <span data-ttu-id="e6212-151">Especifique a chave do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="e6212-151">Specify the application's key.</span></span>
    <span data-ttu-id="e6212-152">Cadeia de conexão_Armazenamento de Blobs do Azure</span><span class="sxs-lookup"><span data-stu-id="e6212-152">Azure Blob Storage_connection String</span></span> | <span data-ttu-id="e6212-153">Cadeia de conexão do Armazenamento de Blobs do Azure.</span><span class="sxs-lookup"><span data-stu-id="e6212-153">Azure Blob storage connection string.</span></span>
    <span data-ttu-id="e6212-154">Service_password vinculada ao Dynamics CRM</span><span class="sxs-lookup"><span data-stu-id="e6212-154">Dynamics Crm Linked Service_password</span></span> | <span data-ttu-id="e6212-155">A senha da conta de usuário especificada como nome de usuário.</span><span class="sxs-lookup"><span data-stu-id="e6212-155">The password for the user account you specified as the username.</span></span>
    <span data-ttu-id="e6212-156">Service_properties_type Properties_url vinculada ao FO</span><span class="sxs-lookup"><span data-stu-id="e6212-156">FO Linked Service_properties_type Properties_url</span></span>  | `https://sampledynamics.sandbox-operationsdynamics.com/data`
    <span data-ttu-id="e6212-157">Service_properties_type Properties_tenant vinculado ao FO</span><span class="sxs-lookup"><span data-stu-id="e6212-157">FO Linked Service_properties_type Properties_tenant</span></span> | <span data-ttu-id="e6212-158">Especifique as informações do locatário (nome do domínio ou ID do locatário) em que seu aplicativo reside.</span><span class="sxs-lookup"><span data-stu-id="e6212-158">Specify the tenant information (domain name or tenant ID) under which your application resides.</span></span>
    <span data-ttu-id="e6212-159">Service_properties_type Properties_aad Resource Id vinculado ao FO</span><span class="sxs-lookup"><span data-stu-id="e6212-159">FO Linked Service_properties_type Properties_aad Resource Id</span></span> | `https://sampledynamics.sandboxoperationsdynamics.com`
    <span data-ttu-id="e6212-160">ID Principal do Service_properties_type Properties_service vinculada ao FO</span><span class="sxs-lookup"><span data-stu-id="e6212-160">FO Linked Service_properties_type Properties_service Principal Id</span></span> | <span data-ttu-id="e6212-161">Especifique a ID do cliente do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="e6212-161">Specify the application's client ID.</span></span>
    <span data-ttu-id="e6212-162">Service_properties_type Properties_username vinculado ao Dynamics CRM</span><span class="sxs-lookup"><span data-stu-id="e6212-162">Dynamics Crm Linked Service_properties_type Properties_username</span></span> | <span data-ttu-id="e6212-163">O nome de usuário para conectar-se ao Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="e6212-163">The username to connect to Dynamics 365.</span></span>

    <span data-ttu-id="e6212-164">Para obter mais informações, confira os tópicos a seguir:</span><span class="sxs-lookup"><span data-stu-id="e6212-164">For additional information, refer to the following topics:</span></span> 
    
    - [<span data-ttu-id="e6212-165">Promover manualmente um modelo do Resource Manager para cada ambiente</span><span class="sxs-lookup"><span data-stu-id="e6212-165">Manually promote a Resource Manager template for each environment</span></span>](/azure/data-factory/continuous-integration-deployment#manually-promote-a-resource-manager-template-for-each-environment)
    - [<span data-ttu-id="e6212-166">Propriedades de serviço vinculadas</span><span class="sxs-lookup"><span data-stu-id="e6212-166">Linked service properties</span></span>](/azure/data-factory/connector-dynamics-ax#linked-service-properties)
    - [<span data-ttu-id="e6212-167">Copiar dados usando o Azure Data Factory</span><span class="sxs-lookup"><span data-stu-id="e6212-167">Copy data using Azure Data Factory</span></span>](/azure/data-factory/connector-dynamics-crm-office-365#dynamics-365-and-dynamics-crm-online)

10. <span data-ttu-id="e6212-168">Após a implantação, valide os conjuntos de dados, de fluxo de dados e o serviço vinculado da data factory.</span><span class="sxs-lookup"><span data-stu-id="e6212-168">After deployment, validate the datasets, data flow, and linked service of the data factory.</span></span>

   ![Conjuntos de dados, fluxo de dados e serviço vinculado](media/data-factory-validate.png)

11. <span data-ttu-id="e6212-170">Navegue até **Gerenciar**.</span><span class="sxs-lookup"><span data-stu-id="e6212-170">Navigate to **Manage**.</span></span> <span data-ttu-id="e6212-171">Em **Conexões**, selecione **Serviço vinculado**.</span><span class="sxs-lookup"><span data-stu-id="e6212-171">Under **Connections**, select **Linked Service**.</span></span> <span data-ttu-id="e6212-172">Selecione **DynamicsCrmLinkedService**.</span><span class="sxs-lookup"><span data-stu-id="e6212-172">Select **DynamicsCrmLinkedService**.</span></span> <span data-ttu-id="e6212-173">No formulário **Editar serviço vinculado (Dynamics CRM)**, insira os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="e6212-173">In the **Edit linked service (Dynamics CRM)** form, enter the following values.</span></span>

    <span data-ttu-id="e6212-174">Campo</span><span class="sxs-lookup"><span data-stu-id="e6212-174">Field</span></span> | <span data-ttu-id="e6212-175">Alíquota</span><span class="sxs-lookup"><span data-stu-id="e6212-175">Value</span></span>
    ---|---
    <span data-ttu-id="e6212-176">Organização</span><span class="sxs-lookup"><span data-stu-id="e6212-176">Name</span></span> | <span data-ttu-id="e6212-177">DynamicsCrmLinkedService</span><span class="sxs-lookup"><span data-stu-id="e6212-177">DynamicsCrmLinkedService</span></span>
    <span data-ttu-id="e6212-178">descrição</span><span class="sxs-lookup"><span data-stu-id="e6212-178">Description</span></span> | <span data-ttu-id="e6212-179">Serviços vinculados para conectar com a instância do CRM para obter dados de entidades</span><span class="sxs-lookup"><span data-stu-id="e6212-179">Linked services to connect with CRM instance to fetch entities data</span></span>
    <span data-ttu-id="e6212-180">Conectar via tempo de execução de integração</span><span class="sxs-lookup"><span data-stu-id="e6212-180">Connect via integration runtime</span></span> | <span data-ttu-id="e6212-181">AutoResolvelntegrationRuntime</span><span class="sxs-lookup"><span data-stu-id="e6212-181">AutoResolvelntegrationRuntime</span></span>
    <span data-ttu-id="e6212-182">Tipo de implantação</span><span class="sxs-lookup"><span data-stu-id="e6212-182">Deployment type</span></span> | <span data-ttu-id="e6212-183">Online</span><span class="sxs-lookup"><span data-stu-id="e6212-183">Online</span></span>
    <span data-ttu-id="e6212-184">URI de serviço</span><span class="sxs-lookup"><span data-stu-id="e6212-184">Service Uri</span></span> | `https://<organization-name>.crm[x].dynamics.com`
    <span data-ttu-id="e6212-185">Tipo de autenticação</span><span class="sxs-lookup"><span data-stu-id="e6212-185">Authentication type</span></span> | <span data-ttu-id="e6212-186">Office365</span><span class="sxs-lookup"><span data-stu-id="e6212-186">Office365</span></span>
    <span data-ttu-id="e6212-187">Nome de usuário</span><span class="sxs-lookup"><span data-stu-id="e6212-187">User name</span></span> |
    <span data-ttu-id="e6212-188">Senha ou Azure Key Vault</span><span class="sxs-lookup"><span data-stu-id="e6212-188">Password or Azure Key Vault</span></span> | <span data-ttu-id="e6212-189">Senha</span><span class="sxs-lookup"><span data-stu-id="e6212-189">Password</span></span>
    <span data-ttu-id="e6212-190">Senha</span><span class="sxs-lookup"><span data-stu-id="e6212-190">Password</span></span> |

## <a name="run-the-template"></a><span data-ttu-id="e6212-191">Executar o modelo</span><span class="sxs-lookup"><span data-stu-id="e6212-191">Run the template</span></span>

1. <span data-ttu-id="e6212-192">Interrompa os mapas de gravação dupla de **Conta**, **Contato** e **Fornecedor** usando o aplicativo do Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="e6212-192">Stop the following **Account**, **Contact**, and **Vendor** dual-write maps using the Finance and Operations app.</span></span>

    + <span data-ttu-id="e6212-193">Clientes V3 (contas)</span><span class="sxs-lookup"><span data-stu-id="e6212-193">Customers V3(accounts)</span></span>
    + <span data-ttu-id="e6212-194">Clientes V3 (contatos)</span><span class="sxs-lookup"><span data-stu-id="e6212-194">Customers V3(contacts)</span></span>
    + <span data-ttu-id="e6212-195">Contatos V2 do CDS (contatos)</span><span class="sxs-lookup"><span data-stu-id="e6212-195">CDS Contacts V2(contacts)</span></span>
    + <span data-ttu-id="e6212-196">Contatos V2 do CDS (contatos)</span><span class="sxs-lookup"><span data-stu-id="e6212-196">CDS Contacts V2(contacts)</span></span>
    + <span data-ttu-id="e6212-197">Fornecedores V2 (msdyn_vendor)</span><span class="sxs-lookup"><span data-stu-id="e6212-197">Vendor V2 (msdyn_vendor)</span></span>

2. <span data-ttu-id="e6212-198">Certifique-se de que os mapas sejam removidos da tabela `msdy_dualwriteruntimeconfig` no Dataverse.</span><span class="sxs-lookup"><span data-stu-id="e6212-198">Make sure the maps are removed from the `msdy_dualwriteruntimeconfig` table in Dataverse.</span></span>

3. <span data-ttu-id="e6212-199">Instale [Soluções de gravação dupla de catálogo de endereços global e de participante](https://aka.ms/dual-write-gab) pelo AppSource.</span><span class="sxs-lookup"><span data-stu-id="e6212-199">Install [Dual-write Party and Global Address Book Solutions](https://aka.ms/dual-write-gab) from AppSource.</span></span>

4. <span data-ttu-id="e6212-200">No aplicativo do Finance and Operations, se as tabelas a seguir contiverem dados, execute a **Sincronização Inicial** para elas.</span><span class="sxs-lookup"><span data-stu-id="e6212-200">In the finance and operations app, if the following tables contain data, then run **Initial Sync** for them.</span></span>

    + <span data-ttu-id="e6212-201">Saudações</span><span class="sxs-lookup"><span data-stu-id="e6212-201">Salutations</span></span>
    + <span data-ttu-id="e6212-202">Tipos de caracteres pessoais</span><span class="sxs-lookup"><span data-stu-id="e6212-202">Personal character types</span></span>
    + <span data-ttu-id="e6212-203">Fechamento complementar</span><span class="sxs-lookup"><span data-stu-id="e6212-203">Complimentary closing</span></span>
    + <span data-ttu-id="e6212-204">Títulos da pessoa de contato</span><span class="sxs-lookup"><span data-stu-id="e6212-204">Contact person titles</span></span>
    + <span data-ttu-id="e6212-205">Funções de tomada de decisão</span><span class="sxs-lookup"><span data-stu-id="e6212-205">Decision making roles</span></span>
    + <span data-ttu-id="e6212-206">Níveis de fidelidade</span><span class="sxs-lookup"><span data-stu-id="e6212-206">Loyalty levels</span></span>

5. <span data-ttu-id="e6212-207">No aplicativo de participação do cliente, desabilite as seguintes etapas do plug-in.</span><span class="sxs-lookup"><span data-stu-id="e6212-207">In the customer engagement app, disable the following plug-in steps.</span></span>

    + <span data-ttu-id="e6212-208">Atualização de Conta</span><span class="sxs-lookup"><span data-stu-id="e6212-208">Account Update</span></span>
         + <span data-ttu-id="e6212-209">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromAccountEntity: atualização da conta</span><span class="sxs-lookup"><span data-stu-id="e6212-209">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromAccountEntity: Update of account</span></span>
         + <span data-ttu-id="e6212-210">Microsoft.Dynamics.FinanceExtended.Plugins.TriggerNotesForCustomerTypeCodes: atualização da conta</span><span class="sxs-lookup"><span data-stu-id="e6212-210">Microsoft.Dynamics.FinanceExtended.Plugins.TriggerNotesForCustomerTypeCodes: Update of account</span></span>
    + <span data-ttu-id="e6212-211">Atualização do contato</span><span class="sxs-lookup"><span data-stu-id="e6212-211">Contact Update</span></span>
         + <span data-ttu-id="e6212-212">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromContactEntity: atualização do contato</span><span class="sxs-lookup"><span data-stu-id="e6212-212">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromContactEntity: Update of contact</span></span>
         + <span data-ttu-id="e6212-213">Microsoft.Dynamics.FinanceExtended.Plugins.TriggerNotesForSellableContact: atualização do contato</span><span class="sxs-lookup"><span data-stu-id="e6212-213">Microsoft.Dynamics.FinanceExtended.Plugins.TriggerNotesForSellableContact: Update of contact</span></span>
    + <span data-ttu-id="e6212-214">Atualização de msdyn_party</span><span class="sxs-lookup"><span data-stu-id="e6212-214">msdyn_party Update</span></span>
         + <span data-ttu-id="e6212-215">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromPartyEntity: atualização de msdyn_party</span><span class="sxs-lookup"><span data-stu-id="e6212-215">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromPartyEntity: Update of msdyn_party</span></span>
    + <span data-ttu-id="e6212-216">Atualização de msdyn_vendor</span><span class="sxs-lookup"><span data-stu-id="e6212-216">msdyn_vendor Update</span></span>
         + <span data-ttu-id="e6212-217">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromVendorEntity: atualização de msdyn_vendor</span><span class="sxs-lookup"><span data-stu-id="e6212-217">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromVendorEntity: Update of msdyn_vendor</span></span>

6. <span data-ttu-id="e6212-218">No aplicativo de participação do cliente, desabilite os seguintes fluxos de trabalho:</span><span class="sxs-lookup"><span data-stu-id="e6212-218">In the customer engagement app, disable the following workflows:</span></span>

    + <span data-ttu-id="e6212-219">Criar Fornecedores na Tabela Contas</span><span class="sxs-lookup"><span data-stu-id="e6212-219">Create Vendors in Accounts Table</span></span>
    + <span data-ttu-id="e6212-220">Criar Fornecedores na Tabela Contas</span><span class="sxs-lookup"><span data-stu-id="e6212-220">Create Vendors in Accounts Table</span></span>
    + <span data-ttu-id="e6212-221">Criar Fornecedores do tipo pessoa na Tabela Contatos</span><span class="sxs-lookup"><span data-stu-id="e6212-221">Create Vendors of type person in Contacts Table</span></span>
    + <span data-ttu-id="e6212-222">Criar Fornecedores do tipo Pessoa na Tabela Fornecedores</span><span class="sxs-lookup"><span data-stu-id="e6212-222">Create Vendors of type Person in Vendors Table</span></span>
    + <span data-ttu-id="e6212-223">Atualizar Fornecedores na Tabela Contas</span><span class="sxs-lookup"><span data-stu-id="e6212-223">Update Vendors in Accounts Table</span></span>
    + <span data-ttu-id="e6212-224">Atualizar Fornecedores na Tabela Fornecedores</span><span class="sxs-lookup"><span data-stu-id="e6212-224">Update Vendors in Vendors Table</span></span>
    + <span data-ttu-id="e6212-225">Atualizar Fornecedores do tipo Pessoa na Tabela Contatos</span><span class="sxs-lookup"><span data-stu-id="e6212-225">Update Vendors of type Person in Contacts Table</span></span>
    + <span data-ttu-id="e6212-226">Atualizar Fornecedores do tipo Pessoa na Tabela Fornecedores</span><span class="sxs-lookup"><span data-stu-id="e6212-226">Update Vendors of type Person in Vendors Table</span></span>

7. <span data-ttu-id="e6212-227">Na data Factory, execute o modelo selecionando **Disparar Agora**, conforme mostrado na imagem a seguir.</span><span class="sxs-lookup"><span data-stu-id="e6212-227">In the data factory, run the template by selecting **Trigger now** as shown in the following image.</span></span> <span data-ttu-id="e6212-228">Esse processo pode levar algumas horas para ser concluído com base no volume de dados.</span><span class="sxs-lookup"><span data-stu-id="e6212-228">This process might take a few hours to complete based on the data volume.</span></span>

    ![Disparar execução](media/data-factory-trigger.png)

    > [!NOTE]
    > <span data-ttu-id="e6212-230">Se tiver personalizações para **Conta**, **Contato** e **Fornecedor**, você precisará modificar o modelo.</span><span class="sxs-lookup"><span data-stu-id="e6212-230">If you have customizations for **Account**, **Contact**, and **Vendor**, then you need to modify the template.</span></span>

8. <span data-ttu-id="e6212-231">Importe os novos registros de **Participante** no aplicativo Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="e6212-231">Import the new **Party** records in the Finance and Operations app.</span></span>

    + <span data-ttu-id="e6212-232">Baixe o arquivo `FONewParty.csv` do Armazenamento de Blobs do Azure.</span><span class="sxs-lookup"><span data-stu-id="e6212-232">Download the `FONewParty.csv` file from Azure blob storage.</span></span> <span data-ttu-id="e6212-233">O caminho é `partybootstrapping/output/FONewParty.csv`.</span><span class="sxs-lookup"><span data-stu-id="e6212-233">The path is `partybootstrapping/output/FONewParty.csv`.</span></span>
    + <span data-ttu-id="e6212-234">Converta o arquivo `FONewParty.csv` em um arquivo do Excel e importe-o para o aplicativo do Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="e6212-234">Convert the `FONewParty.csv` file into an Excel file and import the Excel file into the finance and operations app.</span></span> <span data-ttu-id="e6212-235">Se a importação de CSV funcionar para você, você poderá importar o arquivo CSV diretamente.</span><span class="sxs-lookup"><span data-stu-id="e6212-235">If the csv import works for you, you can import the csv file directly.</span></span> <span data-ttu-id="e6212-236">A importação pode levar algumas horas para ser executada, dependendo do volume de dados.</span><span class="sxs-lookup"><span data-stu-id="e6212-236">The import could take a few hours to run, depending on the data volume.</span></span> <span data-ttu-id="e6212-237">Para obter mais informações, consulte [Visão geral de trabalhos de importação e exportação de dados](../data-import-export-job.md).</span><span class="sxs-lookup"><span data-stu-id="e6212-237">For more information, see [Data import and export jobs overview](../data-import-export-job.md).</span></span>

    ![Importar os registros de participante do Dataverse](media/data-factory-import-party.png)

9. <span data-ttu-id="e6212-239">Nos aplicativos de participação do cliente, habilite as seguintes etapas do plug-in:</span><span class="sxs-lookup"><span data-stu-id="e6212-239">In the customer engagement apps, enable the following plug-in steps:</span></span>

    + <span data-ttu-id="e6212-240">Atualização de Conta</span><span class="sxs-lookup"><span data-stu-id="e6212-240">Account Update</span></span>
         + <span data-ttu-id="e6212-241">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromAccountEntity: atualização da conta</span><span class="sxs-lookup"><span data-stu-id="e6212-241">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromAccountEntity: Update of account</span></span>
         + <span data-ttu-id="e6212-242">Microsoft.Dynamics.FinanceExtended.Plugins.TriggerNotesForCustomerTypeCodes: atualização da conta</span><span class="sxs-lookup"><span data-stu-id="e6212-242">Microsoft.Dynamics.FinanceExtended.Plugins.TriggerNotesForCustomerTypeCodes: Update of account</span></span>
    + <span data-ttu-id="e6212-243">Atualização do contato</span><span class="sxs-lookup"><span data-stu-id="e6212-243">Contact Update</span></span>
         + <span data-ttu-id="e6212-244">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromContactEntity: atualização do contato</span><span class="sxs-lookup"><span data-stu-id="e6212-244">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromContactEntity: Update of contact</span></span>
         + <span data-ttu-id="e6212-245">Microsoft.Dynamics.FinanceExtended.Plugins.TriggerNotesForSellableContact: atualização do contato</span><span class="sxs-lookup"><span data-stu-id="e6212-245">Microsoft.Dynamics.FinanceExtended.Plugins.TriggerNotesForSellableContact: Update of contact</span></span>
    + <span data-ttu-id="e6212-246">Atualização de msdyn_party</span><span class="sxs-lookup"><span data-stu-id="e6212-246">msdyn_party Update</span></span>
         + <span data-ttu-id="e6212-247">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromPartyEntity: atualização de msdyn_party</span><span class="sxs-lookup"><span data-stu-id="e6212-247">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromPartyEntity: Update of msdyn_party</span></span>
    + <span data-ttu-id="e6212-248">Atualização de msdyn_vendor</span><span class="sxs-lookup"><span data-stu-id="e6212-248">msdyn_vendor Update</span></span>
         + <span data-ttu-id="e6212-249">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromVendorEntity: atualização de msdyn_vendor</span><span class="sxs-lookup"><span data-stu-id="e6212-249">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromVendorEntity: Update of msdyn_vendor</span></span>

10. <span data-ttu-id="e6212-250">Nos aplicativos de participação do cliente, ative os seguintes fluxos de trabalho se eles foram desativados nas etapas anteriores:</span><span class="sxs-lookup"><span data-stu-id="e6212-250">In the customer engagement apps, activate the following workflows if you deactivated them in previous steps:</span></span>

    + <span data-ttu-id="e6212-251">Criar Fornecedores na Tabela Contas</span><span class="sxs-lookup"><span data-stu-id="e6212-251">Create Vendors in Accounts Table</span></span>
    + <span data-ttu-id="e6212-252">Criar Fornecedores na Tabela Contas</span><span class="sxs-lookup"><span data-stu-id="e6212-252">Create Vendors in Accounts Table</span></span>
    + <span data-ttu-id="e6212-253">Criar Fornecedores do tipo pessoa na Tabela Contatos</span><span class="sxs-lookup"><span data-stu-id="e6212-253">Create Vendors of type person in Contacts Table</span></span>
    + <span data-ttu-id="e6212-254">Criar Fornecedores do tipo Pessoa na Tabela Fornecedores</span><span class="sxs-lookup"><span data-stu-id="e6212-254">Create Vendors of type Person in Vendors Table</span></span>
    + <span data-ttu-id="e6212-255">Atualizar Fornecedores na Tabela Contas</span><span class="sxs-lookup"><span data-stu-id="e6212-255">Update Vendors in Accounts Table</span></span>
    + <span data-ttu-id="e6212-256">Atualizar Fornecedores na Tabela Fornecedores</span><span class="sxs-lookup"><span data-stu-id="e6212-256">Update Vendors in Vendors Table</span></span>
    + <span data-ttu-id="e6212-257">Atualizar Fornecedores do tipo Pessoa na Tabela Contatos</span><span class="sxs-lookup"><span data-stu-id="e6212-257">Update Vendors of type Person in Contacts Table</span></span>
    + <span data-ttu-id="e6212-258">Atualizar Fornecedores do tipo Pessoa na Tabela Fornecedores</span><span class="sxs-lookup"><span data-stu-id="e6212-258">Update Vendors of type Person in Vendors Table</span></span>

11. <span data-ttu-id="e6212-259">Execute os mapas relacionados ao **Participante**, conforme instruído em [Catálogo de endereços global e de participantes](party-gab.md).</span><span class="sxs-lookup"><span data-stu-id="e6212-259">Run the **Party**-related maps as instructed in [Party and global address book](party-gab.md).</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="e6212-260">Solução de problemas</span><span class="sxs-lookup"><span data-stu-id="e6212-260">Troubleshooting</span></span>

1. <span data-ttu-id="e6212-261">Se houve falha no processo, execute novamente a data factory começando pela atividade com falha.</span><span class="sxs-lookup"><span data-stu-id="e6212-261">If the process fails, rerun the data factory starting from the failed activity.</span></span>
2. <span data-ttu-id="e6212-262">Alguns arquivos são gerados pela data Factory que podem ser usados para a finalidade de validação dos dados.</span><span class="sxs-lookup"><span data-stu-id="e6212-262">Some files are generated by the data factory that you can use for data validation purpose.</span></span>
3. <span data-ttu-id="e6212-263">A data Factory é executada com base em arquivos CSV que são delimitados por vírgula.</span><span class="sxs-lookup"><span data-stu-id="e6212-263">The data factory runs based on csv files that are comma-delimited.</span></span> <span data-ttu-id="e6212-264">Se houver um valor de campo com uma vírgula, isso poderá interferir nos resultados.</span><span class="sxs-lookup"><span data-stu-id="e6212-264">If there is a field value that has a comma, it may interfere with the results.</span></span> <span data-ttu-id="e6212-265">Você deve remover as vírgulas.</span><span class="sxs-lookup"><span data-stu-id="e6212-265">You need to remove the commas.</span></span>
4. <span data-ttu-id="e6212-266">A guia **Monitoramento** fornece informações sobre todas as etapas e os dados processados.</span><span class="sxs-lookup"><span data-stu-id="e6212-266">The **Monitoring** tab provides information about all steps and data processed.</span></span> <span data-ttu-id="e6212-267">Selecione uma etapa específica para depurá-la.</span><span class="sxs-lookup"><span data-stu-id="e6212-267">Select a specific step to debug it.</span></span>

    ![Guia Monitoramento](media/data-factory-monitor.png)

## <a name="learn-more-about-the-template"></a><span data-ttu-id="e6212-269">Saiba mais sobre o modelo</span><span class="sxs-lookup"><span data-stu-id="e6212-269">Learn more about the template</span></span>

<span data-ttu-id="e6212-270">Você pode encontrar informações adicionais sobre o modelo em [Comentários para o leiame do modelo do Azure Data Factory](https://github.com/microsoft/Dynamics-365-FastTrack-Implementation-Assets/blob/master/Dual-write/Upgrade%20data%20to%20dual-write%20Party-GAB%20schema/readme.md).</span><span class="sxs-lookup"><span data-stu-id="e6212-270">You can find additional information about the template in [Comments for Azure Data Factory template readme](https://github.com/microsoft/Dynamics-365-FastTrack-Implementation-Assets/blob/master/Dual-write/Upgrade%20data%20to%20dual-write%20Party-GAB%20schema/readme.md).</span></span>
