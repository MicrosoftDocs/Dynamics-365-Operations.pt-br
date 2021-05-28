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
ms.openlocfilehash: 95472a00d34ba939ac89b4e2484f34d50bee3088
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2021
ms.locfileid: "6018303"
---
# <a name="upgrade-to-the-party-and-global-address-book-model"></a><span data-ttu-id="f98f4-103">Atualizar para o modelo de catálogo de endereços global e de participantes</span><span class="sxs-lookup"><span data-stu-id="f98f4-103">Upgrade to the party and global address book model</span></span>

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="f98f4-104">O [modelo do Azure Data Factory](https://aka.ms/dual-write-gab-adf) ajuda você a atualizar os dados existentes das tabelas **Conta**, **Contato** e **Fornecedor** em uma gravação dupla para o modelo de catálogo de endereços global e do participante.</span><span class="sxs-lookup"><span data-stu-id="f98f4-104">The [Azure Data Factory template](https://aka.ms/dual-write-gab-adf) helps you upgrade existing **Account**, **Contact**, and **Vendor** table data in dual-write to the party and global address book model.</span></span> <span data-ttu-id="f98f4-105">O modelo reconcilia os dados dos aplicativos do Finance and Operations e dos aplicativos de participação do cliente.</span><span class="sxs-lookup"><span data-stu-id="f98f4-105">The template reconciles the data from both Finance and Operations apps and customer engagement applications.</span></span> <span data-ttu-id="f98f4-106">No final do processo, os campos **Participante** e **Contato** para os registros de **Participante** serão criados e associados aos registros de **Conta**, **Contato** e **Fornecedor** nos aplicativos do participação do cliente.</span><span class="sxs-lookup"><span data-stu-id="f98f4-106">At the end of the process, **Party** and **Contact** fields for **Party** records will be created and associated with **Account**, **Contact**, and **Vendor** records in customer engagement applications.</span></span> <span data-ttu-id="f98f4-107">Um arquivo .csv (`FONewParty.csv`) é gerado para criar novos registros de **Participante** no aplicativo Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="f98f4-107">A .csv file (`FONewParty.csv`) is generated to create new **Party** records inside the Finance and Operations app.</span></span> <span data-ttu-id="f98f4-108">Este tópico fornece as instruções para usar o modelo do Data Factory e atualizar seus dados.</span><span class="sxs-lookup"><span data-stu-id="f98f4-108">This topic provides the instructions to use the Data Factory template and upgrade your data.</span></span>

<span data-ttu-id="f98f4-109">Se não tiver nenhuma personalização, você poderá usar o modelo no estado em que se encontra.</span><span class="sxs-lookup"><span data-stu-id="f98f4-109">If you don’t have any customizations, you can use the template as-is.</span></span> <span data-ttu-id="f98f4-110">Se tiver personalizações para **Conta**, **Contato** e **Fornecedor**, você deverá modificar o modelo usando as instruções a seguir.</span><span class="sxs-lookup"><span data-stu-id="f98f4-110">If you have customizations for **Account**, **Contact**, and **Vendor** then you must modify the template using the following instructions.</span></span>

> [!Note]
> <span data-ttu-id="f98f4-111">O modelo ajuda a atualizar somente os dados do **Participante**.</span><span class="sxs-lookup"><span data-stu-id="f98f4-111">The template helps to upgrade only the **Party** data.</span></span> <span data-ttu-id="f98f4-112">Em uma versão futura, os endereços postais e eletrônicos serão incluídos.</span><span class="sxs-lookup"><span data-stu-id="f98f4-112">In a future release, postal and electronic addresses will be included.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="f98f4-113">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="f98f4-113">Prerequisites</span></span>

<span data-ttu-id="f98f4-114">Estes pré-requisitos são obrigatórios:</span><span class="sxs-lookup"><span data-stu-id="f98f4-114">These prerequisites are required:</span></span>

+ [<span data-ttu-id="f98f4-115">Assinatura do Azure</span><span class="sxs-lookup"><span data-stu-id="f98f4-115">Azure subscription</span></span>](https://portal.azure.com/)
+ [<span data-ttu-id="f98f4-116">Acesso ao modelo</span><span class="sxs-lookup"><span data-stu-id="f98f4-116">Access to the template</span></span>](https://aka.ms/dual-write-gab-adf)
+ <span data-ttu-id="f98f4-117">Você ser um cliente de gravação dupla existente.</span><span class="sxs-lookup"><span data-stu-id="f98f4-117">You are an existing dual-write customer.</span></span>

## <a name="prepare-for-the-upgrade"></a><span data-ttu-id="f98f4-118">Preparar-se para o upgrade</span><span class="sxs-lookup"><span data-stu-id="f98f4-118">Prepare for the upgrade</span></span>

+ <span data-ttu-id="f98f4-119">**Totalmente sincronizado**: ambos os ambientes estão em um estado totalmente sincronizado para **Conta (Cliente)**, **Contato** e **Fornecedor**.</span><span class="sxs-lookup"><span data-stu-id="f98f4-119">**Fully synched**: Both environments are fully synched state for **Account (Customer)**, **Contact**, and **Vendor**.</span></span>
+ <span data-ttu-id="f98f4-120">**Chaves de integração**: as tabelas **Conta (Cliente)**, **Contato** e **Fornecedor** nos aplicativos de participação do cliente estão usando as chaves de integração prontas para uso que são enviadas.</span><span class="sxs-lookup"><span data-stu-id="f98f4-120">**Integration keys**: **Account (Customer)**, **Contact**, and **Vendor** tables in customer engagement apps are using the integration keys that shipped out-of-the-box.</span></span> <span data-ttu-id="f98f4-121">Se personalizou as chaves de integração, você deve personalizar o modelo.</span><span class="sxs-lookup"><span data-stu-id="f98f4-121">If you customized the integration keys, you must customize the template.</span></span>
+ <span data-ttu-id="f98f4-122">**Número do participante**: todos os registros de **Conta (Cliente)**, **Contato** e **Fornecedor** que serão atualizados têm um número de **Participante**.</span><span class="sxs-lookup"><span data-stu-id="f98f4-122">**Party number**: All **Account (Customer)**, **Contact**, and **Vendor** records that will be upgraded have a **Party** number.</span></span> <span data-ttu-id="f98f4-123">Registros sem um número de **Participante** serão ignorados.</span><span class="sxs-lookup"><span data-stu-id="f98f4-123">Records without a **Party** number will be ignored.</span></span> <span data-ttu-id="f98f4-124">Se desejar fazer upgrade desses registros, adicione um número de **Participante** a eles antes de iniciar o processo de upgrade.</span><span class="sxs-lookup"><span data-stu-id="f98f4-124">If you want to upgrade those records, add a **Party** number to them before you start the upgrade process.</span></span>
+ <span data-ttu-id="f98f4-125">**Interrupção do sistema**: durante o processo de upgrade, você terá de manter os ambientes do Finance and Operations e de participação do cliente offline.</span><span class="sxs-lookup"><span data-stu-id="f98f4-125">**System outage**: During the upgrade process, you will have to take both the Finance and Operations and customer engagement environments offline.</span></span>
+ <span data-ttu-id="f98f4-126">**Instantâneo**: tire instantâneos dos aplicativos Finance and Operations e de participação do cliente.</span><span class="sxs-lookup"><span data-stu-id="f98f4-126">**Snapshot**: Take snapshots of both the Finance and Operations and customer engagement apps.</span></span> <span data-ttu-id="f98f4-127">Use os instantâneos para restaurar o estado anterior, se necessário.</span><span class="sxs-lookup"><span data-stu-id="f98f4-127">Use the snapshots to restore the previous state if you need to.</span></span>

## <a name="deployment"></a><span data-ttu-id="f98f4-128">Implantação</span><span class="sxs-lookup"><span data-stu-id="f98f4-128">Deployment</span></span>

1. <span data-ttu-id="f98f4-129">Baixe o modelo de [Dynamics-365-FastTrack-Implementation-Assets](https://aka.ms/dual-write-gab-adf).</span><span class="sxs-lookup"><span data-stu-id="f98f4-129">Download the template from [Dynamics-365-FastTrack-Implementation-Assets](https://aka.ms/dual-write-gab-adf).</span></span>

2. <span data-ttu-id="f98f4-130">Entre no [Microsoft Azure](https://portal.azure.com/).</span><span class="sxs-lookup"><span data-stu-id="f98f4-130">Sign in to [Microsoft Azure](https://portal.azure.com/).</span></span>

3. <span data-ttu-id="f98f4-131">Crie um [grupo de recursos](/azure/azure-resource-manager/management/manage-resource-groups-portal).</span><span class="sxs-lookup"><span data-stu-id="f98f4-131">Create a [resource group](/azure/azure-resource-manager/management/manage-resource-groups-portal).</span></span>

4. <span data-ttu-id="f98f4-132">Crie uma [conta de armazenamento](/azure/storage/common/storage-account-create?tabs=azure-portal) no grupo de recursos que você criou.</span><span class="sxs-lookup"><span data-stu-id="f98f4-132">Create a [storage account](/azure/storage/common/storage-account-create?tabs=azure-portal) in the resource group that you created.</span></span>

5. <span data-ttu-id="f98f4-133">Crie uma [data factory](/azure/data-factory/quickstart-create-data-factory-portal) no grupo de recursos que você criou acima.</span><span class="sxs-lookup"><span data-stu-id="f98f4-133">Create a [data factory](/azure/data-factory/quickstart-create-data-factory-portal) in above resource group that you created.</span></span>

6. <span data-ttu-id="f98f4-134">Abra a data Factory e selecione o bloco **Autoria e Monitoramento**.</span><span class="sxs-lookup"><span data-stu-id="f98f4-134">Open the data factory and select the **Author & Monitor** tile.</span></span>

7. <span data-ttu-id="f98f4-135">Na guia **Gerenciar**, selecione **Modelo de ARM**.</span><span class="sxs-lookup"><span data-stu-id="f98f4-135">On the **Manage** tab, select **ARM template**.</span></span>

8. <span data-ttu-id="f98f4-136">Selecione **Importar modelo ARM** para importar o modelo de **Participante**.</span><span class="sxs-lookup"><span data-stu-id="f98f4-136">Select the **Import ARM template** to import the **Party** template.</span></span>

9. <span data-ttu-id="f98f4-137">Importe o modelo para a data factory.</span><span class="sxs-lookup"><span data-stu-id="f98f4-137">Import the template into the data factory.</span></span> <span data-ttu-id="f98f4-138">Insira os valores a seguir para **Detalhes do projeto** e **Detalhes da instância**.</span><span class="sxs-lookup"><span data-stu-id="f98f4-138">Enter the following values for **Project details** and **Instance details**.</span></span>

    <span data-ttu-id="f98f4-139">Campo</span><span class="sxs-lookup"><span data-stu-id="f98f4-139">Field</span></span> | <span data-ttu-id="f98f4-140">Alíquota</span><span class="sxs-lookup"><span data-stu-id="f98f4-140">Value</span></span>
    ---|---
    <span data-ttu-id="f98f4-141">Assinatura</span><span class="sxs-lookup"><span data-stu-id="f98f4-141">Subscription</span></span> | <span data-ttu-id="f98f4-142">Assinatura do Azure</span><span class="sxs-lookup"><span data-stu-id="f98f4-142">Azure subscription</span></span>
    <span data-ttu-id="f98f4-143">Grupo de recursos</span><span class="sxs-lookup"><span data-stu-id="f98f4-143">Resource group</span></span> | <span data-ttu-id="f98f4-144">Forneça o mesmo recurso no qual a conta de armazenamento foi criada.</span><span class="sxs-lookup"><span data-stu-id="f98f4-144">Provide same resource under which storage account is created.</span></span>
    <span data-ttu-id="f98f4-145">Região</span><span class="sxs-lookup"><span data-stu-id="f98f4-145">Region</span></span> | <span data-ttu-id="f98f4-146">Especifique a região.</span><span class="sxs-lookup"><span data-stu-id="f98f4-146">Specify region.</span></span>
    <span data-ttu-id="f98f4-147">Nome da fábrica</span><span class="sxs-lookup"><span data-stu-id="f98f4-147">Factory Name</span></span> | <span data-ttu-id="f98f4-148">Especifique o nome da fábrica.</span><span class="sxs-lookup"><span data-stu-id="f98f4-148">Specify factory name.</span></span>
    <span data-ttu-id="f98f4-149">Chave principal_da entidade de serviço vinculada ao FO</span><span class="sxs-lookup"><span data-stu-id="f98f4-149">FO Linked Service_service Principal Key</span></span> | <span data-ttu-id="f98f4-150">Especifique a chave do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="f98f4-150">Specify the application's key.</span></span>
    <span data-ttu-id="f98f4-151">Cadeia de conexão_Armazenamento de Blobs do Azure</span><span class="sxs-lookup"><span data-stu-id="f98f4-151">Azure Blob Storage_connection String</span></span> | <span data-ttu-id="f98f4-152">Cadeia de conexão do Armazenamento de Blobs do Azure.</span><span class="sxs-lookup"><span data-stu-id="f98f4-152">Azure Blob storage connection string.</span></span>
    <span data-ttu-id="f98f4-153">Service_password vinculada ao Dynamics CRM</span><span class="sxs-lookup"><span data-stu-id="f98f4-153">Dynamics Crm Linked Service_password</span></span> | <span data-ttu-id="f98f4-154">A senha da conta de usuário especificada como nome de usuário.</span><span class="sxs-lookup"><span data-stu-id="f98f4-154">The password for the user account you specified as the username.</span></span>
    <span data-ttu-id="f98f4-155">Service_properties_type Properties_url vinculada ao FO</span><span class="sxs-lookup"><span data-stu-id="f98f4-155">FO Linked Service_properties_type Properties_url</span></span>  | `https://sampledynamics.sandbox-operationsdynamics.com/data`
    <span data-ttu-id="f98f4-156">Service_properties_type Properties_tenant vinculado ao FO</span><span class="sxs-lookup"><span data-stu-id="f98f4-156">FO Linked Service_properties_type Properties_tenant</span></span> | <span data-ttu-id="f98f4-157">Especifique as informações do locatário (nome do domínio ou ID do locatário) em que seu aplicativo reside.</span><span class="sxs-lookup"><span data-stu-id="f98f4-157">Specify the tenant information (domain name or tenant ID) under which your application resides.</span></span>
    <span data-ttu-id="f98f4-158">Service_properties_type Properties_aad Resource Id vinculado ao FO</span><span class="sxs-lookup"><span data-stu-id="f98f4-158">FO Linked Service_properties_type Properties_aad Resource Id</span></span> | `https://sampledynamics.sandboxoperationsdynamics.com`
    <span data-ttu-id="f98f4-159">ID Principal do Service_properties_type Properties_service vinculada ao FO</span><span class="sxs-lookup"><span data-stu-id="f98f4-159">FO Linked Service_properties_type Properties_service Principal Id</span></span> | <span data-ttu-id="f98f4-160">Especifique a ID do cliente do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="f98f4-160">Specify the application's client ID.</span></span>
    <span data-ttu-id="f98f4-161">Service_properties_type Properties_username vinculado ao Dynamics CRM</span><span class="sxs-lookup"><span data-stu-id="f98f4-161">Dynamics Crm Linked Service_properties_type Properties_username</span></span> | <span data-ttu-id="f98f4-162">O nome de usuário para conectar-se ao Dynamics.</span><span class="sxs-lookup"><span data-stu-id="f98f4-162">The username to connect to Dynamics.</span></span>

    <span data-ttu-id="f98f4-163">Para obter mais informações, consulte [Promover manualmente um modelo do Resource Manager para cada ambiente](/azure/data-factory/continuous-integration-deployment#manually-promote-a-resource-manager-template-for-each-environment), [Propriedades do serviço vinculado](/azure/data-factory/connector-dynamics-ax#linked-service-properties) e [Copiar dados usando o Azure Data Factory](/azure/data-factory/connector-dynamics-crm-office-365#dynamics-365-and-dynamics-crm-online)</span><span class="sxs-lookup"><span data-stu-id="f98f4-163">For more information, see [Manually promote a Resource Manager template for each environment](/azure/data-factory/continuous-integration-deployment#manually-promote-a-resource-manager-template-for-each-environment), [Linked service properties](/azure/data-factory/connector-dynamics-ax#linked-service-properties), and [Copy data using Azure Data Factory](/azure/data-factory/connector-dynamics-crm-office-365#dynamics-365-and-dynamics-crm-online)</span></span>

10. <span data-ttu-id="f98f4-164">Após a implantação, valide os conjuntos de dados, de fluxo de dados e o serviço vinculado da data factory.</span><span class="sxs-lookup"><span data-stu-id="f98f4-164">After deployment, validate the datasets, data flow, and linked service of the data factory.</span></span>

   ![Conjuntos de dados, fluxo de dados e serviço vinculado](media/data-factory-validate.png)

11. <span data-ttu-id="f98f4-166">Navegue até **Gerenciar**.</span><span class="sxs-lookup"><span data-stu-id="f98f4-166">Navigate to **Manage**.</span></span> <span data-ttu-id="f98f4-167">Em **Conexões**, selecione **Serviço vinculado**.</span><span class="sxs-lookup"><span data-stu-id="f98f4-167">Under **Connections**, select **Linked Service**.</span></span> <span data-ttu-id="f98f4-168">Selecione **DynamicsCrmLinkedService**.</span><span class="sxs-lookup"><span data-stu-id="f98f4-168">Select **DynamicsCrmLinkedService**.</span></span> <span data-ttu-id="f98f4-169">No formulário **Editar serviço vinculado (Dynamics CRM)**, insira os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="f98f4-169">In the **Edit linked service (Dynamics CRM)** form, enter the following values:</span></span>

    <span data-ttu-id="f98f4-170">Campo</span><span class="sxs-lookup"><span data-stu-id="f98f4-170">Field</span></span> | <span data-ttu-id="f98f4-171">Alíquota</span><span class="sxs-lookup"><span data-stu-id="f98f4-171">Value</span></span>
    ---|---
    <span data-ttu-id="f98f4-172">Organização</span><span class="sxs-lookup"><span data-stu-id="f98f4-172">Name</span></span> | <span data-ttu-id="f98f4-173">DynamicsCrmLinkedService</span><span class="sxs-lookup"><span data-stu-id="f98f4-173">DynamicsCrmLinkedService</span></span>
    <span data-ttu-id="f98f4-174">descrição</span><span class="sxs-lookup"><span data-stu-id="f98f4-174">Description</span></span> | <span data-ttu-id="f98f4-175">Serviços vinculados para conectar com a instância do CRM para obter dados de entidades</span><span class="sxs-lookup"><span data-stu-id="f98f4-175">Linked services to connect with CRM instance to fetch entities data</span></span>
    <span data-ttu-id="f98f4-176">Conectar via tempo de execução de integração</span><span class="sxs-lookup"><span data-stu-id="f98f4-176">Connect via integration runtime</span></span> | <span data-ttu-id="f98f4-177">AutoResolvelntegrationRuntime</span><span class="sxs-lookup"><span data-stu-id="f98f4-177">AutoResolvelntegrationRuntime</span></span>
    <span data-ttu-id="f98f4-178">Tipo de implantação</span><span class="sxs-lookup"><span data-stu-id="f98f4-178">Deployment type</span></span> | <span data-ttu-id="f98f4-179">Online</span><span class="sxs-lookup"><span data-stu-id="f98f4-179">Online</span></span>
    <span data-ttu-id="f98f4-180">URI de serviço</span><span class="sxs-lookup"><span data-stu-id="f98f4-180">Service Uri</span></span> | `https://<organization-name>.crm[x].dynamics.com`
    <span data-ttu-id="f98f4-181">Tipo de autenticação</span><span class="sxs-lookup"><span data-stu-id="f98f4-181">Authentication type</span></span> | <span data-ttu-id="f98f4-182">Office365</span><span class="sxs-lookup"><span data-stu-id="f98f4-182">Office365</span></span>
    <span data-ttu-id="f98f4-183">Nome de usuário</span><span class="sxs-lookup"><span data-stu-id="f98f4-183">User name</span></span> |
    <span data-ttu-id="f98f4-184">Senha ou Azure Key Vault</span><span class="sxs-lookup"><span data-stu-id="f98f4-184">Password or Azure Key Vault</span></span> | <span data-ttu-id="f98f4-185">Senha</span><span class="sxs-lookup"><span data-stu-id="f98f4-185">Password</span></span>
    <span data-ttu-id="f98f4-186">Senha</span><span class="sxs-lookup"><span data-stu-id="f98f4-186">Password</span></span> |

## <a name="run-the-template"></a><span data-ttu-id="f98f4-187">Executar o modelo</span><span class="sxs-lookup"><span data-stu-id="f98f4-187">Run the template</span></span>

1. <span data-ttu-id="f98f4-188">Interrompa a seguinte gravação dupla de **Conta**, **Contato** e **Fornecedor** usando o aplicativo do Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="f98f4-188">Stop the following **Account**, **Contact**, and **Vendor** dual-write using the Finance and Operations app.</span></span>

    + <span data-ttu-id="f98f4-189">Clientes V3 (contas)</span><span class="sxs-lookup"><span data-stu-id="f98f4-189">Customers V3(accounts)</span></span>
    + <span data-ttu-id="f98f4-190">Clientes V3 (contatos)</span><span class="sxs-lookup"><span data-stu-id="f98f4-190">Customers V3(contacts)</span></span>
    + <span data-ttu-id="f98f4-191">Contatos V2 do CDS (contatos)</span><span class="sxs-lookup"><span data-stu-id="f98f4-191">CDS Contacts V2(contacts)</span></span>
    + <span data-ttu-id="f98f4-192">Contatos V2 do CDS (contatos)</span><span class="sxs-lookup"><span data-stu-id="f98f4-192">CDS Contacts V2(contacts)</span></span>
    + <span data-ttu-id="f98f4-193">Fornecedores V2 (msdyn_vendor)</span><span class="sxs-lookup"><span data-stu-id="f98f4-193">Vendor V2 (msdyn_vendor)</span></span>

2. <span data-ttu-id="f98f4-194">Certifique-se de que os mapas sejam removidos da tabela `msdy_dualwriteruntimeconfig` no Dataverse.</span><span class="sxs-lookup"><span data-stu-id="f98f4-194">Make sure the maps are removed from the `msdy_dualwriteruntimeconfig` table in Dataverse.</span></span>

3. <span data-ttu-id="f98f4-195">Instale [Soluções de gravação dupla de catálogo de endereços global e de participante](https://aka.ms/dual-write-gab) pelo AppSource.</span><span class="sxs-lookup"><span data-stu-id="f98f4-195">Install [Dual-write Party and Global Address Book Solutions](https://aka.ms/dual-write-gab) from AppSource.</span></span>

4. <span data-ttu-id="f98f4-196">No aplicativo Finance and Operations, se as tabelas a seguir contiverem dados, execute a **Sincronização Inicial** para elas.</span><span class="sxs-lookup"><span data-stu-id="f98f4-196">In the Finance and Operations app, if the following tables contain data, then run **Initial Sync** for them.</span></span>

    + <span data-ttu-id="f98f4-197">Saudações</span><span class="sxs-lookup"><span data-stu-id="f98f4-197">Salutations</span></span>
    + <span data-ttu-id="f98f4-198">Tipos de caracteres pessoais</span><span class="sxs-lookup"><span data-stu-id="f98f4-198">Personal character types</span></span>
    + <span data-ttu-id="f98f4-199">Fechamento complementar</span><span class="sxs-lookup"><span data-stu-id="f98f4-199">Complimentary closing</span></span>
    + <span data-ttu-id="f98f4-200">Títulos da pessoa de contato</span><span class="sxs-lookup"><span data-stu-id="f98f4-200">Contact person titles</span></span>
    + <span data-ttu-id="f98f4-201">Funções de tomada de decisão</span><span class="sxs-lookup"><span data-stu-id="f98f4-201">Decision making roles</span></span>
    + <span data-ttu-id="f98f4-202">Níveis de fidelidade</span><span class="sxs-lookup"><span data-stu-id="f98f4-202">Loyalty levels</span></span>

5. <span data-ttu-id="f98f4-203">No aplicativo de participação do cliente, desabilite as seguintes etapas do plug-in.</span><span class="sxs-lookup"><span data-stu-id="f98f4-203">In the customer engagement app, disable the following plugin steps.</span></span>

    + <span data-ttu-id="f98f4-204">Atualização da conta</span><span class="sxs-lookup"><span data-stu-id="f98f4-204">Account Update</span></span>
         + <span data-ttu-id="f98f4-205">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromAccountEntity: atualização da conta</span><span class="sxs-lookup"><span data-stu-id="f98f4-205">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromAccountEntity: Update of account</span></span>
         + <span data-ttu-id="f98f4-206">Microsoft.Dynamics.FinanceExtended.Plugins.TriggerNotesForCustomerTypeCodes: atualização da conta</span><span class="sxs-lookup"><span data-stu-id="f98f4-206">Microsoft.Dynamics.FinanceExtended.Plugins.TriggerNotesForCustomerTypeCodes: Update of account</span></span>
    + <span data-ttu-id="f98f4-207">Atualização do contato</span><span class="sxs-lookup"><span data-stu-id="f98f4-207">Contact Update</span></span>
         + <span data-ttu-id="f98f4-208">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromContactEntity: atualização do contato</span><span class="sxs-lookup"><span data-stu-id="f98f4-208">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromContactEntity: Update of contact</span></span>
         + <span data-ttu-id="f98f4-209">Microsoft.Dynamics.FinanceExtended.Plugins.TriggerNotesForSellableContact: atualização do contato</span><span class="sxs-lookup"><span data-stu-id="f98f4-209">Microsoft.Dynamics.FinanceExtended.Plugins.TriggerNotesForSellableContact: Update of contact</span></span>
    + <span data-ttu-id="f98f4-210">Atualização de msdyn_party</span><span class="sxs-lookup"><span data-stu-id="f98f4-210">msdyn_party Update</span></span>
         + <span data-ttu-id="f98f4-211">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromPartyEntity: atualização de msdyn_party</span><span class="sxs-lookup"><span data-stu-id="f98f4-211">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromPartyEntity: Update of msdyn_party</span></span>
    + <span data-ttu-id="f98f4-212">Atualização de msdyn_vendor</span><span class="sxs-lookup"><span data-stu-id="f98f4-212">msdyn_vendor Update</span></span>
         + <span data-ttu-id="f98f4-213">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromVendorEntity: atualização de msdyn_vendor</span><span class="sxs-lookup"><span data-stu-id="f98f4-213">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromVendorEntity: Update of msdyn_vendor</span></span>

6. <span data-ttu-id="f98f4-214">No aplicativo de participação do cliente, desabilite os seguintes fluxos de trabalho:</span><span class="sxs-lookup"><span data-stu-id="f98f4-214">In the customer engagement app, disable the following workflows:</span></span>

    + <span data-ttu-id="f98f4-215">Criar Fornecedores na Tabela Contas</span><span class="sxs-lookup"><span data-stu-id="f98f4-215">Create Vendors in Accounts Table</span></span>
    + <span data-ttu-id="f98f4-216">Criar Fornecedores na Tabela Contas</span><span class="sxs-lookup"><span data-stu-id="f98f4-216">Create Vendors in Accounts Table</span></span>
    + <span data-ttu-id="f98f4-217">Criar Fornecedores do tipo pessoa na Tabela Contatos</span><span class="sxs-lookup"><span data-stu-id="f98f4-217">Create Vendors of type person in Contacts Table</span></span>
    + <span data-ttu-id="f98f4-218">Criar Fornecedores do tipo Pessoa na Tabela Fornecedores</span><span class="sxs-lookup"><span data-stu-id="f98f4-218">Create Vendors of type Person in Vendors Table</span></span>
    + <span data-ttu-id="f98f4-219">Atualizar Fornecedores na Tabela Contas</span><span class="sxs-lookup"><span data-stu-id="f98f4-219">Update Vendors in Accounts Table</span></span>
    + <span data-ttu-id="f98f4-220">Atualizar Fornecedores na Tabela Fornecedores</span><span class="sxs-lookup"><span data-stu-id="f98f4-220">Update Vendors in Vendors Table</span></span>
    + <span data-ttu-id="f98f4-221">Atualizar Fornecedores do tipo Pessoa na Tabela Contatos</span><span class="sxs-lookup"><span data-stu-id="f98f4-221">Update Vendors of type Person in Contacts Table</span></span>
    + <span data-ttu-id="f98f4-222">Atualizar Fornecedores do tipo Pessoa na Tabela Fornecedores</span><span class="sxs-lookup"><span data-stu-id="f98f4-222">Update Vendors of type Person in Vendors Table</span></span>

7. <span data-ttu-id="f98f4-223">Na data Factory, execute o modelo selecionando **Disparar Agora**, conforme mostrado na imagem a seguir.</span><span class="sxs-lookup"><span data-stu-id="f98f4-223">In the data factory, run the template by selecting **Trigger now** as shown in the following image.</span></span> <span data-ttu-id="f98f4-224">Esse processo pode levar algumas horas para ser concluído com base no volume de dados.</span><span class="sxs-lookup"><span data-stu-id="f98f4-224">This process might take a few hours to complete based on the data volume.</span></span>

    ![Disparar execução](media/data-factory-trigger.png)

    > [!NOTE]
    > <span data-ttu-id="f98f4-226">Se tiver personalizações para **Conta**, **Contato** e **Fornecedor**, você deverá modificar o modelo.</span><span class="sxs-lookup"><span data-stu-id="f98f4-226">If you have customizations for **Account**, **Contact**, and **Vendor** then you must modify the template.</span></span>

8. <span data-ttu-id="f98f4-227">Importe os novos registros de **Participante** no aplicativo Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="f98f4-227">Import the new **Party** records in the Finance and Operations app.</span></span>

    + <span data-ttu-id="f98f4-228">Baixe o arquivo `FONewParty.csv` do Armazenamento de Blobs do Azure.</span><span class="sxs-lookup"><span data-stu-id="f98f4-228">Download the `FONewParty.csv` file from Azure blob storage.</span></span> <span data-ttu-id="f98f4-229">O caminho é `partybootstrapping/output/FONewParty.csv`.</span><span class="sxs-lookup"><span data-stu-id="f98f4-229">The path is `partybootstrapping/output/FONewParty.csv`.</span></span>
    + <span data-ttu-id="f98f4-230">Converta o arquivo `FONewParty.csv` em um arquivo do Excel e importe-o para o aplicativo Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="f98f4-230">Convert the `FONewParty.csv` file into an Excel file and import the Excel file into the Finance and Operations app.</span></span>  <span data-ttu-id="f98f4-231">Se a importação de CSV funcionar para você, você poderá importar o arquivo CSV diretamente.</span><span class="sxs-lookup"><span data-stu-id="f98f4-231">If the csv import works for you, you can import csv file directly.</span></span> <span data-ttu-id="f98f4-232">A importação pode levar algumas horas para ser executada, dependendo do volume de dados.</span><span class="sxs-lookup"><span data-stu-id="f98f4-232">The import could take a few hours to run, depending on the data volume.</span></span> <span data-ttu-id="f98f4-233">Para obter mais informações, consulte [Visão geral de trabalhos de importação e exportação de dados](../data-import-export-job.md).</span><span class="sxs-lookup"><span data-stu-id="f98f4-233">For more information, see [Data import and export jobs overview](../data-import-export-job.md).</span></span>

    ![Importar os registros de participante do Dataverse](media/data-factory-import-party.png)

9. <span data-ttu-id="f98f4-235">Nos aplicativos de participação do cliente, habilite as seguintes etapas do plug-in:</span><span class="sxs-lookup"><span data-stu-id="f98f4-235">In the customer engagement apps, enable the following plugin steps:</span></span>

    + <span data-ttu-id="f98f4-236">Atualização da conta</span><span class="sxs-lookup"><span data-stu-id="f98f4-236">Account Update</span></span>
         + <span data-ttu-id="f98f4-237">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromAccountEntity: atualização da conta</span><span class="sxs-lookup"><span data-stu-id="f98f4-237">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromAccountEntity: Update of account</span></span>
         + <span data-ttu-id="f98f4-238">Microsoft.Dynamics.FinanceExtended.Plugins.TriggerNotesForCustomerTypeCodes: atualização da conta</span><span class="sxs-lookup"><span data-stu-id="f98f4-238">Microsoft.Dynamics.FinanceExtended.Plugins.TriggerNotesForCustomerTypeCodes: Update of account</span></span>
    + <span data-ttu-id="f98f4-239">Atualização do contato</span><span class="sxs-lookup"><span data-stu-id="f98f4-239">Contact Update</span></span>
         + <span data-ttu-id="f98f4-240">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromContactEntity: atualização do contato</span><span class="sxs-lookup"><span data-stu-id="f98f4-240">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromContactEntity: Update of contact</span></span>
         + <span data-ttu-id="f98f4-241">Microsoft.Dynamics.FinanceExtended.Plugins.TriggerNotesForSellableContact: atualização do contato</span><span class="sxs-lookup"><span data-stu-id="f98f4-241">Microsoft.Dynamics.FinanceExtended.Plugins.TriggerNotesForSellableContact: Update of contact</span></span>
    + <span data-ttu-id="f98f4-242">Atualização de msdyn_party</span><span class="sxs-lookup"><span data-stu-id="f98f4-242">msdyn_party Update</span></span>
         + <span data-ttu-id="f98f4-243">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromPartyEntity: atualização de msdyn_party</span><span class="sxs-lookup"><span data-stu-id="f98f4-243">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromPartyEntity: Update of msdyn_party</span></span>
    + <span data-ttu-id="f98f4-244">Atualização de msdyn_vendor</span><span class="sxs-lookup"><span data-stu-id="f98f4-244">msdyn_vendor Update</span></span>
         + <span data-ttu-id="f98f4-245">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromVendorEntity: atualização de msdyn_vendor</span><span class="sxs-lookup"><span data-stu-id="f98f4-245">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromVendorEntity: Update of msdyn_vendor</span></span>

10. <span data-ttu-id="f98f4-246">Nos aplicativos de participação do cliente, ative os seguintes fluxos de trabalho se eles foram desativados nas etapas anteriores:</span><span class="sxs-lookup"><span data-stu-id="f98f4-246">In the customer engagement apps, activate the following workflows if you deactivated them in previous steps:</span></span>

    + <span data-ttu-id="f98f4-247">Criar Fornecedores na Tabela Contas</span><span class="sxs-lookup"><span data-stu-id="f98f4-247">Create Vendors in Accounts Table</span></span>
    + <span data-ttu-id="f98f4-248">Criar Fornecedores na Tabela Contas</span><span class="sxs-lookup"><span data-stu-id="f98f4-248">Create Vendors in Accounts Table</span></span>
    + <span data-ttu-id="f98f4-249">Criar Fornecedores do tipo pessoa na Tabela Contatos</span><span class="sxs-lookup"><span data-stu-id="f98f4-249">Create Vendors of type person in Contacts Table</span></span>
    + <span data-ttu-id="f98f4-250">Criar Fornecedores do tipo Pessoa na Tabela Fornecedores</span><span class="sxs-lookup"><span data-stu-id="f98f4-250">Create Vendors of type Person in Vendors Table</span></span>
    + <span data-ttu-id="f98f4-251">Atualizar Fornecedores na Tabela Contas</span><span class="sxs-lookup"><span data-stu-id="f98f4-251">Update Vendors in Accounts Table</span></span>
    + <span data-ttu-id="f98f4-252">Atualizar Fornecedores na Tabela Fornecedores</span><span class="sxs-lookup"><span data-stu-id="f98f4-252">Update Vendors in Vendors Table</span></span>
    + <span data-ttu-id="f98f4-253">Atualizar Fornecedores do tipo Pessoa na Tabela Contatos</span><span class="sxs-lookup"><span data-stu-id="f98f4-253">Update Vendors of type Person in Contacts Table</span></span>
    + <span data-ttu-id="f98f4-254">Atualizar Fornecedores do tipo Pessoa na Tabela Fornecedores</span><span class="sxs-lookup"><span data-stu-id="f98f4-254">Update Vendors of type Person in Vendors Table</span></span>

11. <span data-ttu-id="f98f4-255">Execute os mapas relacionados ao **Participante**, conforme instruído em [Catálogo de endereços global e de participantes](party-gab.md).</span><span class="sxs-lookup"><span data-stu-id="f98f4-255">Run the **Party**-related maps as instructed in [Party and global address book](party-gab.md).</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="f98f4-256">Solução de problemas</span><span class="sxs-lookup"><span data-stu-id="f98f4-256">Troubleshooting</span></span>

1. <span data-ttu-id="f98f4-257">Se houve falha no processo, execute novamente a data factory começando pela atividade com falha.</span><span class="sxs-lookup"><span data-stu-id="f98f4-257">In the process fails, rerun the data factory starting from the failed activity.</span></span>
2. <span data-ttu-id="f98f4-258">Alguns arquivos são gerados pela data Factory que podem ser usados para a finalidade de validação dos dados.</span><span class="sxs-lookup"><span data-stu-id="f98f4-258">Some files are generated by the data factory that you can use for data validation purpose.</span></span>
3. <span data-ttu-id="f98f4-259">A data Factory é executada com base em arquivos CSV que são delimitados por vírgula.</span><span class="sxs-lookup"><span data-stu-id="f98f4-259">The data factory runs based on csv files that are comma-delimited.</span></span> <span data-ttu-id="f98f4-260">Se houver um valor de campo com uma vírgula, isso poderá interferir nos resultados.</span><span class="sxs-lookup"><span data-stu-id="f98f4-260">If there is a field value that has a comma, it may interfere with the results.</span></span> <span data-ttu-id="f98f4-261">Você deve remover as vírgulas.</span><span class="sxs-lookup"><span data-stu-id="f98f4-261">You need to remove the commas.</span></span>
4. <span data-ttu-id="f98f4-262">A guia **Monitoramento** fornece informações sobre todas as etapas e os dados processados.</span><span class="sxs-lookup"><span data-stu-id="f98f4-262">The **Monitoring** tab provides information about all steps and data processed.</span></span> <span data-ttu-id="f98f4-263">Selecione uma etapa específica para depurá-la.</span><span class="sxs-lookup"><span data-stu-id="f98f4-263">Select a specific step to debug it.</span></span>

    ![Guia Monitoramento](media/data-factory-monitor.png)

## <a name="learn-more-about-the-template"></a><span data-ttu-id="f98f4-265">Saiba mais sobre o modelo</span><span class="sxs-lookup"><span data-stu-id="f98f4-265">Learn more about the template</span></span>

<span data-ttu-id="f98f4-266">Você pode encontrar comentários sobre o modelo no arquivo [readme.md](https://github.com/microsoft/Dynamics-365-FastTrack-Implementation-Assets/blob/master/Dual-write/Upgrade%20data%20to%20dual-write%20Party-GAB%20schema/readme.md).</span><span class="sxs-lookup"><span data-stu-id="f98f4-266">You can find comments for the template the [readme.md](https://github.com/microsoft/Dynamics-365-FastTrack-Implementation-Assets/blob/master/Dual-write/Upgrade%20data%20to%20dual-write%20Party-GAB%20schema/readme.md) file.</span></span>