---
title: Solucionar problemas durante a sincronização inicial
description: Este tópico fornece informações sobre como solucionar problemas que podem ajudá-lo a corrigir problemas que podem acontecer durante a sincronização inicial.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 03/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-03-16
ms.openlocfilehash: 10065039fce441d7f96f700ff826d959e96f2479
ms.sourcegitcommit: cecd97fd74ff7b31f1a677e8fdf3e233aa28ef5a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/28/2020
ms.locfileid: "3410072"
---
# <a name="troubleshoot-issues-during-initial-synchronization"></a><span data-ttu-id="216ac-103">Solucionar problemas durante a sincronização inicial</span><span class="sxs-lookup"><span data-stu-id="216ac-103">Troubleshoot issues during initial synchronization</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="216ac-104">Este tópico fornece informações de solução de problemas para integração de gravação dupla entre aplicativos do Finance and Operations e o Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="216ac-104">This topic provides troubleshooting information for dual-write integration between Finance and Operations apps and Common Data Service.</span></span> <span data-ttu-id="216ac-105">Especificamente, ele fornece informações sobre como solucionar problemas que podem ajudá-lo a corrigir problemas que podem acontecer durante a sincronização inicial.</span><span class="sxs-lookup"><span data-stu-id="216ac-105">Specifically, it provides information that can help you fix issues that might occur during initial synchronization.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="216ac-106">Alguns dos problemas que este tópico aborda podem exigir a função de administrador do sistema ou as credenciais de administrador do locatário Microsoft Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="216ac-106">Some of the issues that this topic addresses might require either the system admin role or Microsoft Azure Active Directory (Azure AD) tenant admin credentials.</span></span> <span data-ttu-id="216ac-107">A seção para cada problema explica se uma função ou credenciais específicas são necessárias.</span><span class="sxs-lookup"><span data-stu-id="216ac-107">The section for each issue explains whether a specific role or credentials are required.</span></span>

## <a name="check-for-initial-synchronization-errors-in-a-finance-and-operations-app"></a><span data-ttu-id="216ac-108">Verificar erros de sincronização inicial em um aplicativo do Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="216ac-108">Check for initial synchronization errors in a Finance and Operations app</span></span>

<span data-ttu-id="216ac-109">Depois de habilitar os modelos de mapeamento, o status dos mapas deve estar em **Execução**.</span><span class="sxs-lookup"><span data-stu-id="216ac-109">After you enable the mapping templates, the status of the maps should be **Running**.</span></span> <span data-ttu-id="216ac-110">Se o status **Não estiver em execução**, ocorrerão erros durante a sincronização inicial.</span><span class="sxs-lookup"><span data-stu-id="216ac-110">If the status is **Not running**, errors occurred during initial synchronization.</span></span> <span data-ttu-id="216ac-111">Para exibir os erros, selecione a guia **Detalhes de sincronização inicial** na página **Gravação dupla**.</span><span class="sxs-lookup"><span data-stu-id="216ac-111">To view the errors, select the **Initial sync details** tab on the **Dual-write** page.</span></span>

![Guia detalhes da sincronização inicial](media/initial_sync_status.png)

## <a name="you-cant-complete-initial-synchronization-400-bad-request"></a><span data-ttu-id="216ac-113">Não é possível concluir a sincronização inicial: 400 Solicitação incorreta</span><span class="sxs-lookup"><span data-stu-id="216ac-113">You can't complete initial synchronization: 400 Bad Request</span></span>

<span data-ttu-id="216ac-114">**Função necessária para corrigir o problema:** administrador do sistema</span><span class="sxs-lookup"><span data-stu-id="216ac-114">**Required role to fix the issue:** System admin</span></span>

<span data-ttu-id="216ac-115">A seguinte mensagem de erro pode ser exibida ao tentar executar o mapeamento e a sincronização inicial:</span><span class="sxs-lookup"><span data-stu-id="216ac-115">You might receive the following error message when you try to run the mapping and initial synchronization:</span></span>

<span data-ttu-id="216ac-116">*O servidor remoto retornou um erro: (400) Solicitação incorreta.), a exportação AX encontrou um erro*</span><span class="sxs-lookup"><span data-stu-id="216ac-116">*The remote server returned an error: (400) Bad Request.), AX export encountered an error*</span></span>

<span data-ttu-id="216ac-117">Veja aqui um exemplo da mensagem de erro completa.</span><span class="sxs-lookup"><span data-stu-id="216ac-117">Here is an example of the full error message.</span></span>

```console
Dual write Initial Sync completed with status: Error. Following are the details:
Executed leg: From AX Financial dimensions to CRM msdyn_dimensionattributes
with exported records count: 0, ImportRecordsErrorCount: 0,
ImportRecordsInsertedCount: 0 and ImportRecordsUpdatedCount: 0
ErrorsDetails:
Dual write Initial sync failed
Message: ([Bad Request], The remote server returned an error: (400) Bad Request.), AX export encountered an error
Stacktrace: at
Microsoft.Dynamics.Integrator.QueryGenerator.AxClient.\<ExportAxPackage\>d__16.MoveNext()
in X:\\bt\\1024532\\repo\\src\\Core\\QueryGenerator\\AxClient.cs:line 265
\--- End of stack trace from previous location where exception was thrown ---
at System.Runtime.ExceptionServices.ExceptionDispatchInfo.Throw()
at System.Runtime.CompilerServices.TaskAwaiter.HandleNonSuccessAndDebuggerNotification(Task task)
at Microsoft.D365.ServicePlatform.Context.ServiceContext.Activity.\<ExecuteAsync\>d__11\`2.MoveNext()
\--- End of stack trace from previous location where exception was thrown ---
```

<span data-ttu-id="216ac-118">Se esse erro ocorrer consistentemente e você não puder concluir a sincronização inicial, siga estas etapas para corrigir o problema.</span><span class="sxs-lookup"><span data-stu-id="216ac-118">If this error occurs consistently, and you can't complete the initial synchronization, follow these steps to fix the issue.</span></span>

1. <span data-ttu-id="216ac-119">Faça login na máquina virtual (VM) para o aplicativo Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="216ac-119">Sign in to the virtual machine (VM) for the Finance and Operations app.</span></span>
2. <span data-ttu-id="216ac-120">Abra o console de gerenciamento da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="216ac-120">Open Microsoft Management Console.</span></span>
3. <span data-ttu-id="216ac-121">No painel **Serviços**, verifique se o serviço de estrutura de importação/exportação de dados do Microsoft Dynamics 365 está em execução.</span><span class="sxs-lookup"><span data-stu-id="216ac-121">In the **Services** pane, make sure that the Microsoft Dynamics 365 Data import export framework service is running.</span></span> <span data-ttu-id="216ac-122">Reinicie-o se ele tiver sido interrompido, pois a sincronização inicial requer essa ação.</span><span class="sxs-lookup"><span data-stu-id="216ac-122">Restart it if it has been stopped, because the initial synchronization requires it.</span></span>

## <a name="initial-synchronization-error-403-forbidden"></a><span data-ttu-id="216ac-123">Erro de sincronização inicial: 403 Proibido</span><span class="sxs-lookup"><span data-stu-id="216ac-123">Initial synchronization error: 403 Forbidden</span></span>

<span data-ttu-id="216ac-124">A seguinte mensagem de erro pode ser exibida durante sincronização inicial:</span><span class="sxs-lookup"><span data-stu-id="216ac-124">You might receive the following error message during initial synchronization:</span></span>

<span data-ttu-id="216ac-125">*(\[Proibido\], O servidor remoto retornou um erro: (403) Proibido.), a exportação AX encontrou um erro*</span><span class="sxs-lookup"><span data-stu-id="216ac-125">*(\[Forbidden\], The remote server returned an error: (403) Forbidden.), AX export encountered an error*</span></span>

<span data-ttu-id="216ac-126">Para corrigir o problema, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="216ac-126">To fix the issue, follow these steps.</span></span>

1. <span data-ttu-id="216ac-127">Entrar no aplicativo Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="216ac-127">Sign in to the Finance and Operations app.</span></span>
2. <span data-ttu-id="216ac-128">Na página **aplicativo do Azure Active Directory**, exclua o cliente **DtAppID** e, em seguida, adicione-o novamente.</span><span class="sxs-lookup"><span data-stu-id="216ac-128">On the **Azure Active Directory applications** page, delete the **DtAppID** client, and then add it again.</span></span>

![Lista de aplicativos do Azure AD](media/aad_applications.png)

## <a name="self-reference-or-circular-reference-failures-during-initial-synchronization"></a><span data-ttu-id="216ac-130">Falhas de autorreferência ou referência circular durante a sincronização inicial</span><span class="sxs-lookup"><span data-stu-id="216ac-130">Self-reference or circular-reference failures during initial synchronization</span></span>

<span data-ttu-id="216ac-131">Você poderá receber mensagens de erro se um dos seus mapeamentos tiver autorreferências ou referências circulares:</span><span class="sxs-lookup"><span data-stu-id="216ac-131">You might receive an error messages if any of your mappings have self-references or circular references.</span></span> <span data-ttu-id="216ac-132">Os erros são classificados nestas categorias:</span><span class="sxs-lookup"><span data-stu-id="216ac-132">The errors fall into these categories:</span></span>

- [<span data-ttu-id="216ac-133">Fornecedores V2 para mapeamento de entidade msdyn_vendors</span><span class="sxs-lookup"><span data-stu-id="216ac-133">Vendors V2 to msdyn_vendors entity mapping</span></span>](#error-vendor-map)
- [<span data-ttu-id="216ac-134">Clientes V3 para mapeamento de entidade Contas</span><span class="sxs-lookup"><span data-stu-id="216ac-134">Customers V3 to Accounts entity mapping</span></span>](#error-customer-map)

## <a name="resolve-an-error-in-vendors-v2-to-msdyn_vendors-entity-mapping"></a><a id="error-vendor-map"></a><span data-ttu-id="216ac-135">Resolver um erro em fornecedores v2 para mapeamento de entidade msdyn_vendors</span><span class="sxs-lookup"><span data-stu-id="216ac-135">Resolve an error in Vendors V2 to msdyn_vendors entity mapping</span></span>

<span data-ttu-id="216ac-136">Você poderá executar os seguintes erros de sincronização iniciais nos **Fornecedores V2** para mapeamento de **msdyn_vendors** se as entidades tiverem registros existentes com valores nos campos **PrimaryContactPersonId** e **InvoiceVendorAccountNumber**.</span><span class="sxs-lookup"><span data-stu-id="216ac-136">You might run into the following initial sync errors on the **Vendors V2** to **msdyn_vendors** mapping if the entities have existing records with values in the **PrimaryContactPersonId** and **InvoiceVendorAccountNumber** fields.</span></span> <span data-ttu-id="216ac-137">Isso ocorre porque **InvoiceVendorAccountNumber** é um campo de auto-referência e **PrimaryContactPersonId** é uma referência circular no mapeamento do fornecedor.</span><span class="sxs-lookup"><span data-stu-id="216ac-137">This because **InvoiceVendorAccountNumber** is a self-referencing field, and **PrimaryContactPersonId** is a circular reference in the vendor mapping.</span></span>

<span data-ttu-id="216ac-138">*Não foi possível resolver a GUID do campo: <field>. A pesquisa não foi encontrada: <value>. Experimente este(s) URLs para verificar se os dados de referência existem: https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/<entity>?$select=<field>&$filter=<field> eq <value>*</span><span class="sxs-lookup"><span data-stu-id="216ac-138">*Couldn't resolve the guid for the field: <field>. The lookup was not found: <value>. Try this URL(s) to check if the reference data exists: https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/<entity>?$select=<field>&$filter=<field> eq <value>*</span></span>

<span data-ttu-id="216ac-139">Veja alguns exemplos:</span><span class="sxs-lookup"><span data-stu-id="216ac-139">Here are a couple of examples:</span></span>

- <span data-ttu-id="216ac-140">*Não foi possível resolver o GUID do campo: msdyn_vendorprimarycontactperson.msdyn_contactpersonid. A pesquisa não foi encontrada: 000056. Experimente este(s) URL(s) para verificar se os dados de referência existem: https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/contacts?$select=msdyn_contactpersonid.contactid&$filter=msdyn_contactpersonid eq '000056'*</span><span class="sxs-lookup"><span data-stu-id="216ac-140">*Couldn't resolve the guid for the field: msdyn_vendorprimarycontactperson.msdyn_contactpersonid. The lookup was not found: 000056. Try this URL(s) to check if the reference data exists: https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/contacts?$select=msdyn_contactpersonid.contactid&$filter=msdyn_contactpersonid eq '000056'*</span></span>
- <span data-ttu-id="216ac-141">*Não foi possível resolver o GUID do campo: msdyn_invoicevendoraccountnumber.msdyn_vendoraccountnumber. A pesquisa não foi encontrada: V24-1. Experimente este(s) URL(s) para verificar se os dados de referência existem: https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/msdn_vendors?$select=msdyn_vendoraccountnumber,msdyn_vendorid&$filter=msdyn_vendoraccountnumber eq 'V24-1'*</span><span class="sxs-lookup"><span data-stu-id="216ac-141">*Couldn't resolve the guid for the field: msdyn_invoicevendoraccountnumber.msdyn_vendoraccountnumber. The lookup was not found: V24-1. Try this URL(s) to check if the reference data exists: https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/msdn_vendors?$select=msdyn_vendoraccountnumber,msdyn_vendorid&$filter=msdyn_vendoraccountnumber eq 'V24-1'*</span></span>

<span data-ttu-id="216ac-142">Se você tiver registros com valores nesses campos na entidade fornecedor, siga as etapas na seção a seguir para concluir a sincronização inicial com êxito.</span><span class="sxs-lookup"><span data-stu-id="216ac-142">If you have records with values in these fields in the vendor entity follow the steps in the below section to complete initial sync successfully.</span></span>

1. <span data-ttu-id="216ac-143">No aplicativo Finance and Operations, exclua os campos **PrimaryContactPersonId** e **InvoiceVendorAccountNumber** do mapeamento e salve as alterações.</span><span class="sxs-lookup"><span data-stu-id="216ac-143">In the Finance and Operations app, delete the **PrimaryContactPersonId** and **InvoiceVendorAccountNumber** fields from the mapping and save the changes.</span></span>

    1. <span data-ttu-id="216ac-144">Navegue até a página de mapeamento de gravação dupla para **Fornecedores V2 (msdyn_vendors)** e selecione a guia **Mapeamentos de entidade**. No filtro esquerdo, selecione **Finance and Operations apps.Vendors V2**.</span><span class="sxs-lookup"><span data-stu-id="216ac-144">Navigate to the dual-write mapping page for **Vendors V2 (msdyn_vendors)**, and select the **Entity mappings** tab. In the left filter, select **Finance and Operations apps.Vendors V2**.</span></span> <span data-ttu-id="216ac-145">No filtro direito, selecione **Sales.Vendor**.</span><span class="sxs-lookup"><span data-stu-id="216ac-145">In the right filter, select **Sales.Vendor**.</span></span>

    2. <span data-ttu-id="216ac-146">Procure **primarycontactperson** para encontrar o campo de origem **PrimaryContactPersonId**.</span><span class="sxs-lookup"><span data-stu-id="216ac-146">Search for **primarycontactperson** to find the source field **PrimaryContactPersonId**.</span></span>
    
    3. <span data-ttu-id="216ac-147">Clique no botão **Ações** e selecione **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="216ac-147">Click the **Actions** button, and select **Delete**.</span></span>
    
        ![Autorreferência ou referência circular 3](media/vend_selfref3.png)
    
    4. <span data-ttu-id="216ac-149">Repita para excluir o campo **InvoiceVendorAccountNumber**.</span><span class="sxs-lookup"><span data-stu-id="216ac-149">Repeat to delete the **InvoiceVendorAccountNumber** field.</span></span>
    
        ![Autorreferência ou referência circular 4](media/vend-selfref4.png)
    
    5. <span data-ttu-id="216ac-151">Salve as alterações de mapeamento.</span><span class="sxs-lookup"><span data-stu-id="216ac-151">Save the mapping changes.</span></span>

2. <span data-ttu-id="216ac-152">Desabilite o controle de alterações para a entidade **Fornecedor V2**.</span><span class="sxs-lookup"><span data-stu-id="216ac-152">Disable the change tracking for the **Vendors V2** entity.</span></span>

    1. <span data-ttu-id="216ac-153">Navegue até **Gerenciamento de dados \> Entidades de Dados**.</span><span class="sxs-lookup"><span data-stu-id="216ac-153">Navigate to **Data management \> Data Entities**.</span></span>
    
    2. <span data-ttu-id="216ac-154">Selecione a entidade **Fornecedores V2**.</span><span class="sxs-lookup"><span data-stu-id="216ac-154">Select the **Vendors V2** entity.</span></span>
    
    3. <span data-ttu-id="216ac-155">Clique em **Opções** na barra de menus e em **Controle de alterações**.</span><span class="sxs-lookup"><span data-stu-id="216ac-155">Click **Options** from the menu bar, and then **Change tracking**.</span></span>
    
        ![Autorreferência ou referência circular 5](media/selfref_options.png)
    
    4. <span data-ttu-id="216ac-157">Clique em **Desabilitar Controle de Alterações**.</span><span class="sxs-lookup"><span data-stu-id="216ac-157">Click **Disable Change Tracking**.</span></span>
    
        ![Autorreferência ou referência circular 6](media/selfref_tracking.png)

3. <span data-ttu-id="216ac-159">Execute o mapeamento de sincronização inicial do **Fornecedor V2 (msdyn_vendors)**.</span><span class="sxs-lookup"><span data-stu-id="216ac-159">Run the initial sync of **Vendors V2 (msdyn_vendors)** mapping.</span></span> <span data-ttu-id="216ac-160">A sincronização inicial deve ser executada com êxito sem erros.</span><span class="sxs-lookup"><span data-stu-id="216ac-160">The initial sync should run successfully without any errors.</span></span>

4. <span data-ttu-id="216ac-161">Execute a sincronização inicial para o mapeamento de **Contatos de CDS V2 (contatos)**.</span><span class="sxs-lookup"><span data-stu-id="216ac-161">Run the initial sync for the **CDS Contacts V2 (contacts)** mapping.</span></span> <span data-ttu-id="216ac-162">Você deverá sincronizar este mapeamento se desejar sincronizar o campo de contato principal na entidade fornecedores, já que os registros de contatos também precisam ser sincronizados.</span><span class="sxs-lookup"><span data-stu-id="216ac-162">You must sync this mapping if you want to sync primary contact field on vendors entity as the contacts records also need to be initial synced.</span></span>

5. <span data-ttu-id="216ac-163">Adicione os campos **PrimaryContactPersonId** e **InvoiceVendorAccountNumber** novamente ao mapeamento **Fornecedores V2 (msdyn_vendors)** e salve o mapeamento.</span><span class="sxs-lookup"><span data-stu-id="216ac-163">Add the fields **PrimaryContactPersonId** and **InvoiceVendorAccountNumber** back to the **Vendors V2 (msdyn_vendors)** mapping and save the mapping.</span></span>

6. <span data-ttu-id="216ac-164">Execute novamente a sincronização inicial para mapeamento do **Fornecedor V2 (msdyn_vendors)**.</span><span class="sxs-lookup"><span data-stu-id="216ac-164">Run the initial sync again for the **Vendors V2 (msdyn_vendors)** mapping.</span></span> <span data-ttu-id="216ac-165">Todos os registros serão sincronizados, pois o controle de alterações está desabilitado.</span><span class="sxs-lookup"><span data-stu-id="216ac-165">All the records will be synced, because change tracking is disabled.</span></span>

7. <span data-ttu-id="216ac-166">Habilite o controle de alterações para a entidade **Fornecedor V2**.</span><span class="sxs-lookup"><span data-stu-id="216ac-166">Enable change tracking for the **Vendors V2** entity.</span></span>

## <a name="resolve-an-error-in-customers-v3-to-accounts-entity-mapping"></a><a id="error-customer-map"></a><span data-ttu-id="216ac-167">Resolver um erro no mapeamento de Clientes V3 para a entidade Contas</span><span class="sxs-lookup"><span data-stu-id="216ac-167">Resolve an error in Customers V3 to Accounts entity mapping</span></span>

<span data-ttu-id="216ac-168">Você poderá executar os seguintes erros de sincronização inicial no mapeamento de **Clientes V3** para **Contas** se as entidades tiverem registros existentes com valores nos campos **ContactPersonID** e **InvoiceAccount**.</span><span class="sxs-lookup"><span data-stu-id="216ac-168">You might run into the following initial sync errors on the **Customers V3** to **Accounts** mapping if the entities have existing records with values in the **ContactPersonID** and **InvoiceAccount** fields.</span></span> <span data-ttu-id="216ac-169">Isso ocorre porque **InvoiceAccount** é um campo de autorreferência e **ContactPersonID** é uma referência circular no mapeamento do fornecedor.</span><span class="sxs-lookup"><span data-stu-id="216ac-169">This because **InvoiceAccount** is a self-referencing field, and **ContactPersonID** is a circular reference in the vendor mapping.</span></span>

<span data-ttu-id="216ac-170">*Não foi possível resolver a GUID do campo: <field>. A pesquisa não foi encontrada: <value>. Experimente este(s) URLs para verificar se os dados de referência existem: https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/<entity>?$select=<field>&$filter=<field> eq <value>*</span><span class="sxs-lookup"><span data-stu-id="216ac-170">*Couldn't resolve the guid for the field: <field>. The lookup was not found: <value>. Try this URL(s) to check if the reference data exists: https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/<entity>?$select=<field>&$filter=<field> eq <value>*</span></span>

- <span data-ttu-id="216ac-171">*Não foi possível resolver o GUID do campo: primarycontactid.msdyn_contactpersonid. A pesquisa não foi encontrada: 000056. Experimente este(s) URL(s) para verificar se os dados de referência existem: https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/contacts?$select=msdyn_contactpersonid.contactid&$filter=msdyn_contactpersonid eq '000056'*</span><span class="sxs-lookup"><span data-stu-id="216ac-171">*Couldn't resolve the guid for the field: primarycontactid.msdyn_contactpersonid. The lookup was not found: 000056. Try this URL(s) to check if the reference data exists: https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/contacts?$select=msdyn_contactpersonid.contactid&$filter=msdyn_contactpersonid eq '000056'*</span></span>
- <span data-ttu-id="216ac-172">*Não foi possível resolver o GUID do campo: msdyn_billingaccount.accountnumber. A pesquisa não foi encontrada: 1206-1. Experimente este(s) URL(s) para verificar se os dados de referência existem: https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/accounts?$select=accountnumber.account&$filter=accountnumber eq '1206-1'*</span><span class="sxs-lookup"><span data-stu-id="216ac-172">*Couldn't resolve the guid for the field: msdyn_billingaccount.accountnumber. The lookup was not found: 1206-1. Try this URL(s) to check if the reference data exists: https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/accounts?$select=accountnumber.account&$filter=accountnumber eq '1206-1'*</span></span>

<span data-ttu-id="216ac-173">Se você tiver registros com valores nesses campos na entidade cliente, siga as etapas na seção a seguir para concluir a sincronização inicial com êxito.</span><span class="sxs-lookup"><span data-stu-id="216ac-173">If you have records with values in these fields in the customer entity follow the steps in the below section to complete initial sync successfully.</span></span> <span data-ttu-id="216ac-174">Você pode usar essa abordagem para qualquer entidade pronta para uso, como Contas e Contatos.</span><span class="sxs-lookup"><span data-stu-id="216ac-174">You can use this approach for any out-of-the-box entities such Accounts and Contacts.</span></span>

1. <span data-ttu-id="216ac-175">No aplicativo Finance and Operations, exclua os campos **ContactPersonID** e **InvoiceAccount** do mapeamento **Clientes V3 (contas)** e salve o mapeamento.</span><span class="sxs-lookup"><span data-stu-id="216ac-175">In the Finance and Operations app, delete the fields **ContactPersonID** and **InvoiceAccount** from the **Customers V3 (accounts)** mapping and save the mapping.</span></span>

    1. <span data-ttu-id="216ac-176">Navegue até a página de mapeamento de gravação dupla para **Clientes V3 (contas)**, selecione a guia **Mapeamentos de entidade**. No filtro esquerdo, selecione **Finance and Operations app.Customers V3**.</span><span class="sxs-lookup"><span data-stu-id="216ac-176">Navigate to the dual-write mapping page for **Customers V3 (accounts)**, select the **Entity mappings** tab. In the left filter, select **Finance and Operations app.Customers V3**.</span></span> <span data-ttu-id="216ac-177">No filtro direito, selecione **Common Data Service.Account**.</span><span class="sxs-lookup"><span data-stu-id="216ac-177">In the right filter, select **Common Data Service.Account**.</span></span>

    2. <span data-ttu-id="216ac-178">Procure **contactperson** para encontrar o campo de origem **ContactPersonID**.</span><span class="sxs-lookup"><span data-stu-id="216ac-178">Search for **contactperson** to find the source field **ContactPersonID**.</span></span>
    
    3. <span data-ttu-id="216ac-179">Clique no botão **Ações** e selecione **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="216ac-179">Click the **Actions** button, and select **Delete**.</span></span>
    
        ![Autorreferência ou referência circular 3](media/cust_selfref3.png)
    
    4. <span data-ttu-id="216ac-181">Repita para excluir o campo **InvoiceAccount**.</span><span class="sxs-lookup"><span data-stu-id="216ac-181">Repeat to delete the **InvoiceAccount** field.</span></span>
    
        ![Autorreferência ou referência circular](media/cust_selfref4.png)
    
    5. <span data-ttu-id="216ac-183">Salve as alterações de mapeamento.</span><span class="sxs-lookup"><span data-stu-id="216ac-183">Save the mapping changes.</span></span>

2. <span data-ttu-id="216ac-184">Desabilite o controle de alterações para a entidade **Clientes V3**.</span><span class="sxs-lookup"><span data-stu-id="216ac-184">Disable the change tracking for the **Customers V3** entity.</span></span>

    1. <span data-ttu-id="216ac-185">Navegue até **Gerenciamento de dados \> Entidades de Dados**.</span><span class="sxs-lookup"><span data-stu-id="216ac-185">Navigate to **Data management \> Data Entities**.</span></span>
    
    2. <span data-ttu-id="216ac-186">Selecione a entidade **Clientes V3**.</span><span class="sxs-lookup"><span data-stu-id="216ac-186">Select the **Customers V3** entity.</span></span>
    
    3. <span data-ttu-id="216ac-187">Clique em **Opções** na barra de menus e em **Controle de alterações**.</span><span class="sxs-lookup"><span data-stu-id="216ac-187">Click **Options** from the menu bar, and then **Change tracking**.</span></span>
    
        ![Autorreferência ou referência circular 5](media/selfref_options.png)
    
    4. <span data-ttu-id="216ac-189">Clique em **Desabilitar Controle de Alterações**.</span><span class="sxs-lookup"><span data-stu-id="216ac-189">Click **Disable Change Tracking**.</span></span>
    
        ![Autorreferência ou referência circular 6](media/selfref_tracking.png)

3. <span data-ttu-id="216ac-191">Execute a sincronização inicial para o mapeamento de **Clientes V3 (contas)**.</span><span class="sxs-lookup"><span data-stu-id="216ac-191">Run the initial sync for the **Customers V3 (Accounts)** mapping.</span></span> <span data-ttu-id="216ac-192">A sincronização inicial deve ser executada com êxito sem erros.</span><span class="sxs-lookup"><span data-stu-id="216ac-192">The initial sync should run successfully without any errors.</span></span>

4. <span data-ttu-id="216ac-193">Execute a sincronização inicial para o mapeamento de **Contatos de CDS V2 (contatos)**.</span><span class="sxs-lookup"><span data-stu-id="216ac-193">Run the initial sync for the **CDS Contacts V2 (contacts)** mapping.</span></span> <span data-ttu-id="216ac-194">Há 2 mapas com o mesmo nome.</span><span class="sxs-lookup"><span data-stu-id="216ac-194">There are 2 maps with the same name.</span></span> <span data-ttu-id="216ac-195">Selecione aquele com o modelo de descrição **Gravação dupla para sincronização entre Contatos FO.CDS do Fornecedor V2 para CDS.Contacts. Exige novo pacote \[Dynamics365SupplyChainExtended\].**</span><span class="sxs-lookup"><span data-stu-id="216ac-195">Select the one with the description **Dual-write template for sync between FO.CDS Vendor Contacts V2 to CDS.Contacts. Requires new package \[Dynamics365SupplyChainExtended\].**</span></span> <span data-ttu-id="216ac-196">Na guia **Detalhes** do mapa.</span><span class="sxs-lookup"><span data-stu-id="216ac-196">on the **Details** tab of the map.</span></span>

5. <span data-ttu-id="216ac-197">Adicione os campos **InvoiceAccount** e **ContactPersonId** novamente no mapeamento **Clientes V3 (contas)** e salve o mapeamento.</span><span class="sxs-lookup"><span data-stu-id="216ac-197">Add the fields **InvoiceAccount** and **ContactPersonId** back to the **Customers V3 (Accounts)** mapping and save the mapping.</span></span> <span data-ttu-id="216ac-198">Agora, os campos **InvoiceAccount** e **ContactPersonId** fazem parte novamente do modo de sincronização ao vivo.</span><span class="sxs-lookup"><span data-stu-id="216ac-198">Now, both the **InvoiceAccount** field and the **ContactPersonId** field are again part of live sync mode.</span></span> <span data-ttu-id="216ac-199">Na próxima etapa, você concluirá a sincronização inicial desses campos.</span><span class="sxs-lookup"><span data-stu-id="216ac-199">In the next step, you complete the initial sync for these fields.</span></span>

6. <span data-ttu-id="216ac-200">Execute a sincronização inicial novamente para o mapeamento de **Clientes V3 (contas)**.</span><span class="sxs-lookup"><span data-stu-id="216ac-200">Run the initial sync again for the **Customers V3 (Accounts)** mapping.</span></span> <span data-ttu-id="216ac-201">Como o controle de alterações está desabilitado, a execução da sincronização sincronizará os dados de **InvoiceAccount** e **ContactPersonId** do aplicativo Finance and Operations para o Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="216ac-201">Because change tracking is disabled, running the sync will sync the data for **InvoiceAccount** and **ContactPersonId** from the Finance and Operations app to Common Data Service.</span></span>

7. <span data-ttu-id="216ac-202">Para sincronizar os dados para **InvoiceAccount** e **ContactPersonId** do Common Data Service para o Finance and Operations, você usa um projeto de integração de dados.</span><span class="sxs-lookup"><span data-stu-id="216ac-202">To sync the data for **InvoiceAccount** and **ContactPersonId** from Common Data Service to the Finance and Operations, you use a data integration project.</span></span>

    1. <span data-ttu-id="216ac-203">No Power Apps, crie um projeto de integração de dados entre as entidades **Sales.Account** e **Finance and Operations apps.Customers V3**.</span><span class="sxs-lookup"><span data-stu-id="216ac-203">In Power Apps, create a data integration project between the **Sales.Account** and **Finance and Operations apps.Customers V3** entities.</span></span> <span data-ttu-id="216ac-204">A direção de dados deve ser do Common Data Service para o aplicativo do Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="216ac-204">The data direction must be from Common Data Service to the Finance and Operations app.</span></span>  <span data-ttu-id="216ac-205">Como **InvoiceAccount** é um novo atributo na gravação dupla, talvez você deseje ignorar a sincronização inicial desse atributo.</span><span class="sxs-lookup"><span data-stu-id="216ac-205">Because **InvoiceAccount** is a new attribute in dual-write, you may want to skip initial sync for this attribute.</span></span> <span data-ttu-id="216ac-206">Para obter mais informações, consulte [Integrar dados no Common Data Service](https://docs.microsoft.com/power-platform/admin/data-integrator).</span><span class="sxs-lookup"><span data-stu-id="216ac-206">For more information, see [Integrate data into Common Data Service](https://docs.microsoft.com/power-platform/admin/data-integrator).</span></span>

        <span data-ttu-id="216ac-207">A imagem a seguir mostra um projeto que atualiza **CustomerAccount** e **ContactPersonId**.</span><span class="sxs-lookup"><span data-stu-id="216ac-207">The following image shows a project that updates **CustomerAccount** and **ContactPersonId**.</span></span>

        ![Autorreferência ou referência circular](media/cust_selfref6.png)

    2. <span data-ttu-id="216ac-209">Adicione os critérios da empresa no filtro do Common Data Service, pois somente os registros que correspondem aos critérios do filtro serão atualizados no aplicativo do Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="216ac-209">Add the company criteria in the filter on Common Data Service side, because only the records that match filter criteria will be updated in the Finance and Operations app.</span></span> <span data-ttu-id="216ac-210">Para adicionar um filtro, clique no ícone de filtro.</span><span class="sxs-lookup"><span data-stu-id="216ac-210">To add a filter, click the filter icon.</span></span> <span data-ttu-id="216ac-211">Na caixa de diálogo **Editar consulta**, você pode adicionar uma consulta de filtro como **_msdyn_company_value eq '\<guid\>'**.</span><span class="sxs-lookup"><span data-stu-id="216ac-211">In the **Edit query** dialog, you can add a filter query like **_msdyn_company_value eq '\<guid\>'**.</span></span> <span data-ttu-id="216ac-212">Se o ícone de filtro não estiver presente, crie um tíquete de suporte para solicitar que a equipe de integração de dados habilite a capacidade de filtro no seu locatário.</span><span class="sxs-lookup"><span data-stu-id="216ac-212">If the filter icon is not present, create a support ticket to ask the data integration team to enable the filter capability on your tenant.</span></span> <span data-ttu-id="216ac-213">Se você não inserir uma consulta de filtro para **msdyn_company_value**, todos os registros serão sincronizados.</span><span class="sxs-lookup"><span data-stu-id="216ac-213">If you do not enter a filter query for **_msdyn_company_value**, then all the records are synced.</span></span>

        ![Autorreferência ou referência circular](media/cust_selfref7.png)

        <span data-ttu-id="216ac-215">Isso conclui a sincronização inicial dos registros.</span><span class="sxs-lookup"><span data-stu-id="216ac-215">This completes the initial sync of the records.</span></span>

8. <span data-ttu-id="216ac-216">Habilite o controle de alterações para a entidade **Clientes V3** no aplicativo do Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="216ac-216">Enable change tracking for the **Customers V3** entity in the Finance and Operations app.</span></span>

