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
ms.openlocfilehash: e4ee3bf07a1df445875197f38f655464cc9b44d3
ms.sourcegitcommit: cf709f1421a0bf66ecea493088ecb4eb08004187
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/12/2020
ms.locfileid: "3443840"
---
# <a name="troubleshoot-issues-during-initial-synchronization"></a><span data-ttu-id="0e2d4-103">Solucionar problemas durante a sincronização inicial</span><span class="sxs-lookup"><span data-stu-id="0e2d4-103">Troubleshoot issues during initial synchronization</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="0e2d4-104">Este tópico fornece informações de solução de problemas para integração de gravação dupla entre aplicativos do Finance and Operations e o Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="0e2d4-104">This topic provides troubleshooting information for dual-write integration between Finance and Operations apps and Common Data Service.</span></span> <span data-ttu-id="0e2d4-105">Especificamente, ele fornece informações sobre como solucionar problemas que podem ajudá-lo a corrigir problemas que podem acontecer durante a sincronização inicial.</span><span class="sxs-lookup"><span data-stu-id="0e2d4-105">Specifically, it provides information that can help you fix issues that might occur during initial synchronization.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0e2d4-106">Alguns dos problemas que este tópico aborda podem exigir a função de administrador do sistema ou as credenciais de administrador do locatário Microsoft Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="0e2d4-106">Some of the issues that this topic addresses might require either the system admin role or Microsoft Azure Active Directory (Azure AD) tenant admin credentials.</span></span> <span data-ttu-id="0e2d4-107">A seção para cada problema explica se uma função ou credenciais específicas são necessárias.</span><span class="sxs-lookup"><span data-stu-id="0e2d4-107">The section for each issue explains whether a specific role or credentials are required.</span></span>

## <a name="check-for-initial-synchronization-errors-in-a-finance-and-operations-app"></a><span data-ttu-id="0e2d4-108">Verificar erros de sincronização inicial em um aplicativo do Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="0e2d4-108">Check for initial synchronization errors in a Finance and Operations app</span></span>

<span data-ttu-id="0e2d4-109">Depois de habilitar os modelos de mapeamento, o status dos mapas deve estar em **Execução**.</span><span class="sxs-lookup"><span data-stu-id="0e2d4-109">After you enable the mapping templates, the status of the maps should be **Running**.</span></span> <span data-ttu-id="0e2d4-110">Se o status **Não estiver em execução**, ocorrerão erros durante a sincronização inicial.</span><span class="sxs-lookup"><span data-stu-id="0e2d4-110">If the status is **Not running**, errors occurred during initial synchronization.</span></span> <span data-ttu-id="0e2d4-111">Para exibir os erros, selecione a guia **Detalhes de sincronização inicial** na página **Gravação dupla**.</span><span class="sxs-lookup"><span data-stu-id="0e2d4-111">To view the errors, select the **Initial sync details** tab on the **Dual-write** page.</span></span>

![Erro na guia Detalhes da sincronização inicial](media/initial_sync_status.png)

## <a name="you-cant-complete-initial-synchronization-400-bad-request"></a><span data-ttu-id="0e2d4-113">Não é possível concluir a sincronização inicial: 400 Solicitação incorreta</span><span class="sxs-lookup"><span data-stu-id="0e2d4-113">You can't complete initial synchronization: 400 Bad Request</span></span>

<span data-ttu-id="0e2d4-114">**Função necessária para corrigir o problema:** administrador do sistema</span><span class="sxs-lookup"><span data-stu-id="0e2d4-114">**Required role to fix the issue:** System admin</span></span>

<span data-ttu-id="0e2d4-115">A seguinte mensagem de erro pode ser exibida ao tentar executar o mapeamento e a sincronização inicial:</span><span class="sxs-lookup"><span data-stu-id="0e2d4-115">You might receive the following error message when you try to run the mapping and initial synchronization:</span></span>

<span data-ttu-id="0e2d4-116">*(\[Solicitação Incorreta\], O servidor remoto retornou um erro: (400) Solicitação Incorreta.), a exportação AX encontrou um erro*</span><span class="sxs-lookup"><span data-stu-id="0e2d4-116">*(\[Bad Request\], The remote server returned an error: (400) Bad Request.), AX export encountered an error*</span></span>

<span data-ttu-id="0e2d4-117">Veja aqui um exemplo da mensagem de erro completa.</span><span class="sxs-lookup"><span data-stu-id="0e2d4-117">Here is an example of the full error message.</span></span>

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

<span data-ttu-id="0e2d4-118">Se esse erro ocorrer consistentemente e você não puder concluir a sincronização inicial, siga estas etapas para corrigir o problema.</span><span class="sxs-lookup"><span data-stu-id="0e2d4-118">If this error occurs consistently, and you can't complete the initial synchronization, follow these steps to fix the issue.</span></span>

1. <span data-ttu-id="0e2d4-119">Faça login na máquina virtual (VM) para o aplicativo Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="0e2d4-119">Sign in to the virtual machine (VM) for the Finance and Operations app.</span></span>
2. <span data-ttu-id="0e2d4-120">Abra o console de gerenciamento da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="0e2d4-120">Open Microsoft Management Console.</span></span>
3. <span data-ttu-id="0e2d4-121">No painel **Serviços**, verifique se o serviço de estrutura de importação/exportação de dados do Microsoft Dynamics 365 está em execução.</span><span class="sxs-lookup"><span data-stu-id="0e2d4-121">In the **Services** pane, make sure that the Microsoft Dynamics 365 Data import export framework service is running.</span></span> <span data-ttu-id="0e2d4-122">Reinicie-o se ele tiver sido interrompido, pois a sincronização inicial requer essa ação.</span><span class="sxs-lookup"><span data-stu-id="0e2d4-122">Restart it if it has been stopped, because the initial synchronization requires it.</span></span>

## <a name="initial-synchronization-error-403-forbidden"></a><span data-ttu-id="0e2d4-123">Erro de sincronização inicial: 403 Proibido</span><span class="sxs-lookup"><span data-stu-id="0e2d4-123">Initial synchronization error: 403 Forbidden</span></span>

<span data-ttu-id="0e2d4-124">A seguinte mensagem de erro pode ser exibida durante sincronização inicial:</span><span class="sxs-lookup"><span data-stu-id="0e2d4-124">You might receive the following error message during initial synchronization:</span></span>

<span data-ttu-id="0e2d4-125">*(\[Proibido\], O servidor remoto retornou um erro: (403) Proibido.), a exportação AX encontrou um erro*</span><span class="sxs-lookup"><span data-stu-id="0e2d4-125">*(\[Forbidden\], The remote server returned an error: (403) Forbidden.), AX export encountered an error*</span></span>

<span data-ttu-id="0e2d4-126">Para corrigir o problema, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="0e2d4-126">To fix the issue, follow these steps.</span></span>

1. <span data-ttu-id="0e2d4-127">Entrar no aplicativo Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="0e2d4-127">Sign in to the Finance and Operations app.</span></span>
2. <span data-ttu-id="0e2d4-128">Na página **aplicativo do Azure Active Directory**, exclua o cliente **DtAppID** e, em seguida, adicione-o novamente.</span><span class="sxs-lookup"><span data-stu-id="0e2d4-128">On the **Azure Active Directory applications** page, delete the **DtAppID** client, and then add it again.</span></span>

![Cliente DtAppID na lista de aplicativos do Azure AD](media/aad_applications.png)

## <a name="self-reference-or-circular-reference-failures-during-initial-synchronization"></a><span data-ttu-id="0e2d4-130">Falhas de autorreferência ou referência circular durante a sincronização inicial</span><span class="sxs-lookup"><span data-stu-id="0e2d4-130">Self-reference or circular reference failures during initial synchronization</span></span>

<span data-ttu-id="0e2d4-131">Você poderá receber mensagens de erro se um dos seus mapeamentos tiver autorreferências ou referências circulares:</span><span class="sxs-lookup"><span data-stu-id="0e2d4-131">You might receive an error messages if any of your mappings have self-references or circular references.</span></span> <span data-ttu-id="0e2d4-132">Os erros são classificados nestas categorias:</span><span class="sxs-lookup"><span data-stu-id="0e2d4-132">The errors fall into these categories:</span></span>

- [<span data-ttu-id="0e2d4-133">Erros em Fornecedores V2 para mapeamento de entidade msdyn_vendors</span><span class="sxs-lookup"><span data-stu-id="0e2d4-133">Errors in the Vendors V2–to–msdyn_vendors entity mapping</span></span>](#error-vendor-map)
- [<span data-ttu-id="0e2d4-134">Erros no mapeamento de Clientes V3 para a entidade Contas</span><span class="sxs-lookup"><span data-stu-id="0e2d4-134">Errors in the Customers V3–to–Accounts entity mapping</span></span>](#error-customer-map)

## <a name="resolve-errors-in-the-vendors-v2tomsdyn_vendors-entity-mapping"></a><a id="error-vendor-map"></a><span data-ttu-id="0e2d4-135">Resolver erros em Fornecedores V2 para mapeamento de entidade msdyn_vendors</span><span class="sxs-lookup"><span data-stu-id="0e2d4-135">Resolve errors in the Vendors V2–to–msdyn_vendors entity mapping</span></span>

<span data-ttu-id="0e2d4-136">Você poderá encontrar erros de sincronização inicial para p mapeamento de **Fornecedores V2** para **msdyn\_vendors** se as entidades tiverem registros existentes com valores nos campos **PrimaryContactPersonId** e **InvoiceVendorAccountNumber**.</span><span class="sxs-lookup"><span data-stu-id="0e2d4-136">You might encounter initial synchronization errors for the mapping of **Vendors V2** to **msdyn\_vendors** if the entities have existing records where there are values in the **PrimaryContactPersonId** and **InvoiceVendorAccountNumber** fields.</span></span> <span data-ttu-id="0e2d4-137">Esses erros ocorrem porque **InvoiceVendorAccountNumber** é um campo de auto-referência e **PrimaryContactPersonId** é uma referência circular no mapeamento do fornecedor.</span><span class="sxs-lookup"><span data-stu-id="0e2d4-137">These errors occur because **InvoiceVendorAccountNumber** is a self-referencing field, and **PrimaryContactPersonId** is a circular reference in the vendor mapping.</span></span>

<span data-ttu-id="0e2d4-138">As mensagens de erro recebidas terão o seguinte formulário.</span><span class="sxs-lookup"><span data-stu-id="0e2d4-138">The error messages that you receive will have the following form.</span></span>

<span data-ttu-id="0e2d4-139">*Não foi possível resolver a GUID do campo: \<field\>. A pesquisa não foi encontrada: \<value\>. Experimente esta(s) URLs para verificar se os dados de referência existem: `https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/<entity>?$select=<field>&$filter=<field> eq <value>`*</span><span class="sxs-lookup"><span data-stu-id="0e2d4-139">*Couldn't resolve the guid for the field: \<field\>. The lookup was not found: \<value\>. Try this URL(s) to check if the reference data exists: `https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/<entity>?$select=<field>&$filter=<field> eq <value>`*</span></span>

<span data-ttu-id="0e2d4-140">Eis alguns exemplos:</span><span class="sxs-lookup"><span data-stu-id="0e2d4-140">Here are some examples:</span></span>

- <span data-ttu-id="0e2d4-141">*Não foi possível resolver a GUID do campo: msdyn\_vendorprimarycontactperson.msdyn\_contactpersonid. A pesquisa não foi encontrada: 000056. Experimente esta(s) URLs para verificar se os dados de referência existem: `https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/contacts?$select=msdyn_contactpersonid.contactid&$filter=msdyn_contactpersonid eq '000056'`*</span><span class="sxs-lookup"><span data-stu-id="0e2d4-141">*Couldn't resolve the guid for the field: msdyn\_vendorprimarycontactperson.msdyn\_contactpersonid. The lookup was not found: 000056. Try this URL(s) to check if the reference data exists: `https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/contacts?$select=msdyn_contactpersonid.contactid&$filter=msdyn_contactpersonid eq '000056'`*</span></span>
- <span data-ttu-id="0e2d4-142">*Não foi possível resolver a GUID do campo: msdyn\_invoicevendoraccountnumber.msdyn\_vendoraccountnumber. A pesquisa não foi encontrada: V24-1. Experimente esta(s) URLs para verificar se os dados de referência existem: `https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/msdn_vendors?$select=msdyn_vendoraccountnumber,msdyn_vendorid&$filter=msdyn_vendoraccountnumber eq 'V24-1'`*</span><span class="sxs-lookup"><span data-stu-id="0e2d4-142">*Couldn't resolve the guid for the field: msdyn\_invoicevendoraccountnumber.msdyn\_vendoraccountnumber. The lookup was not found: V24-1. Try this URL(s) to check if the reference data exists: `https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/msdn_vendors?$select=msdyn_vendoraccountnumber,msdyn_vendorid&$filter=msdyn_vendoraccountnumber eq 'V24-1'`*</span></span>

<span data-ttu-id="0e2d4-143">Se algum registro na entidade fornecedor tiver valores nos campos **PrimaryContactPersonId** e **InvoiceVendorAccountNumber**, siga estas etapas para concluir a sincronização inicial.</span><span class="sxs-lookup"><span data-stu-id="0e2d4-143">If any records in the vendor entity have values in the **PrimaryContactPersonId** and **InvoiceVendorAccountNumber** fields, follow these steps to complete the initial synchronization.</span></span>

1. <span data-ttu-id="0e2d4-144">No aplicativo Finance and Operations, exclua os campos **PrimaryContactPersonId** e **InvoiceVendorAccountNumber** do mapeamento e depois salve o mapeamento.</span><span class="sxs-lookup"><span data-stu-id="0e2d4-144">In the Finance and Operations app, delete the **PrimaryContactPersonId** and **InvoiceVendorAccountNumber** fields from the mapping, and then save the mapping.</span></span>

    1. <span data-ttu-id="0e2d4-145">Na página de mapeamento de gravação dupla para **Fornecedores V2 (msdyn\_vendors)**, na guia **Mapeamentos de entidade**, no filtro esquerdo, selecione **Finance and Operations apps.Vendors V2**.</span><span class="sxs-lookup"><span data-stu-id="0e2d4-145">On the dual-write mapping page for **Vendors V2 (msdyn\_vendors)**, on the **Entity mappings** tab, in the left filter, select **Finance and Operations apps.Vendors V2**.</span></span> <span data-ttu-id="0e2d4-146">No filtro direito, selecione **Sales.Vendor**.</span><span class="sxs-lookup"><span data-stu-id="0e2d4-146">In the right filter, select **Sales.Vendor**.</span></span>
    2. <span data-ttu-id="0e2d4-147">Procure **primarycontactperson** para encontrar o campo de origem **PrimaryContactPersonId**.</span><span class="sxs-lookup"><span data-stu-id="0e2d4-147">Search for **primarycontactperson** to find the **PrimaryContactPersonId** source field.</span></span>
    3. <span data-ttu-id="0e2d4-148">Selecione **Ações** e depois **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="0e2d4-148">Select **Actions**, and then select **Delete**.</span></span>

        ![Excluindo o campo PrimaryContactPersonId](media/vend_selfref3.png)

    4. <span data-ttu-id="0e2d4-150">Repita essas etapas para excluir o campo **InvoiceVendorAccountNumber**.</span><span class="sxs-lookup"><span data-stu-id="0e2d4-150">Repeat these steps to delete the **InvoiceVendorAccountNumber** field.</span></span>

        ![Excluindo o campo InvoiceVendorAccountNumber](media/vend-selfref4.png)

    5. <span data-ttu-id="0e2d4-152">Salve as alterações feitas no mapeamento.</span><span class="sxs-lookup"><span data-stu-id="0e2d4-152">Save your changes to the mapping.</span></span>

2. <span data-ttu-id="0e2d4-153">Desative o controle de alterações para a entidade **Fornecedor V2**.</span><span class="sxs-lookup"><span data-stu-id="0e2d4-153">Turn off change tracking for the **Vendors V2** entity.</span></span>

    1. <span data-ttu-id="0e2d4-154">No espaço de trabalho **Gerenciamento de dados**, selecione o bloco **Entidades de dados**.</span><span class="sxs-lookup"><span data-stu-id="0e2d4-154">In the **Data management** workspace, select the **Data entities** tile.</span></span>
    2. <span data-ttu-id="0e2d4-155">Selecione a entidade **Fornecedores V2**.</span><span class="sxs-lookup"><span data-stu-id="0e2d4-155">Select the **Vendors V2** entity.</span></span>
    3. <span data-ttu-id="0e2d4-156">No Painel de Ações, selecione **Opções** e depois selecione **Controle de Alterações**.</span><span class="sxs-lookup"><span data-stu-id="0e2d4-156">On the Action Pane, select **Options**, and then select **Change tracking**.</span></span>

        ![Selecionando a opção Controle de Alterações](media/selfref_options.png)

    4. <span data-ttu-id="0e2d4-158">Selecione **Desabilitar Controle de Alterações**.</span><span class="sxs-lookup"><span data-stu-id="0e2d4-158">Select **Disable Change Tracking**.</span></span>

        ![Selecionando Desabilitar Controle de Alterações](media/selfref_tracking.png)

3. <span data-ttu-id="0e2d4-160">Execute a sincronização inicial para mapeamento do **Fornecedor V2 (msdyn\_vendors)**.</span><span class="sxs-lookup"><span data-stu-id="0e2d4-160">Run initial synchronization for the **Vendors V2 (msdyn\_vendors)** mapping.</span></span> <span data-ttu-id="0e2d4-161">A sincronização inicial deve ser executada com êxito, sem erros.</span><span class="sxs-lookup"><span data-stu-id="0e2d4-161">The initial synchronization should run successfully, without any errors.</span></span>
4. <span data-ttu-id="0e2d4-162">Execute a sincronização inicial para o mapeamento de **Contatos de CDS V2 (contatos)**.</span><span class="sxs-lookup"><span data-stu-id="0e2d4-162">Run initial synchronization for the **CDS Contacts V2 (contacts)** mapping.</span></span> <span data-ttu-id="0e2d4-163">Você deverá sincronizar este mapeamento se desejar sincronizar o campo de contato principal na entidade fornecedores, pois a sincronização inicial também precisa ser feita para os registros de contatos.</span><span class="sxs-lookup"><span data-stu-id="0e2d4-163">You must sync this mapping if you want to sync the primary contact field on the vendors entity, because initial synchronization must also be done for the contact records.</span></span>
5. <span data-ttu-id="0e2d4-164">Adicione os campos **PrimaryContactPersonId** e **InvoiceVendorAccountNumber** novamente ao mapeamento **Fornecedores V2 (msdyn\_vendors)** e salve o mapeamento.</span><span class="sxs-lookup"><span data-stu-id="0e2d4-164">Add the **PrimaryContactPersonId** and **InvoiceVendorAccountNumber** fields back to the **Vendors V2 (msdyn\_vendors)** mapping, and then save the mapping.</span></span>
6. <span data-ttu-id="0e2d4-165">Execute a sincronização inicial novamente para o mapeamento do **Fornecedor V2 (msdyn\_vendors)**.</span><span class="sxs-lookup"><span data-stu-id="0e2d4-165">Run initial synchronization again for the **Vendors V2 (msdyn\_vendors)** mapping.</span></span> <span data-ttu-id="0e2d4-166">Como o controle de alterações está desabilitado, todos os registros serão sincronizados.</span><span class="sxs-lookup"><span data-stu-id="0e2d4-166">Because change tracking is turned off, all the records will be synced.</span></span>
7. <span data-ttu-id="0e2d4-167">Ative o controle de alterações novamente para a entidade **Fornecedor V2**.</span><span class="sxs-lookup"><span data-stu-id="0e2d4-167">Turn change tracking back on for the **Vendors V2** entity.</span></span>

## <a name="resolve-errors-in-the-customers-v3toaccounts-entity-mapping"></a><a id="error-customer-map"></a><span data-ttu-id="0e2d4-168">Resolver erros no mapeamento de Clientes V3 para a entidade Contas</span><span class="sxs-lookup"><span data-stu-id="0e2d4-168">Resolve errors in the Customers V3–to–Accounts entity mapping</span></span>

<span data-ttu-id="0e2d4-169">Você poderá encontrar erros de sincronização inicial para o mapeamento de **Clientes V3** para **Contas** se as entidades tiverem registros existentes com valores nos campos **ContactPersonID** e **InvoiceAccount**.</span><span class="sxs-lookup"><span data-stu-id="0e2d4-169">You might encounter initial synchronization errors for the mapping of **Customers V3** to **Accounts** if the entities have existing records where there are values in the **ContactPersonID** and **InvoiceAccount** fields.</span></span> <span data-ttu-id="0e2d4-170">Esses erros ocorrem porque **InvoiceAccount** é um campo de autorreferência e **ContactPersonID** é uma referência circular no mapeamento do fornecedor.</span><span class="sxs-lookup"><span data-stu-id="0e2d4-170">These errors occur because **InvoiceAccount** is a self-referencing field, and **ContactPersonID** is a circular reference in the vendor mapping.</span></span>

<span data-ttu-id="0e2d4-171">As mensagens de erro recebidas terão o seguinte formulário.</span><span class="sxs-lookup"><span data-stu-id="0e2d4-171">The error messages that you receive will have the following form.</span></span>

<span data-ttu-id="0e2d4-172">*Não foi possível resolver a GUID do campo: \<field\>. A pesquisa não foi encontrada: \<value\>. Experimente esta(s) URLs para verificar se os dados de referência existem: `https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/<entity>?$select=<field>&$filter=<field> eq <value>`*</span><span class="sxs-lookup"><span data-stu-id="0e2d4-172">*Couldn't resolve the guid for the field: \<field\>. The lookup was not found: \<value\>. Try this URL(s) to check if the reference data exists: `https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/<entity>?$select=<field>&$filter=<field> eq <value>`*</span></span>

<span data-ttu-id="0e2d4-173">Eis alguns exemplos:</span><span class="sxs-lookup"><span data-stu-id="0e2d4-173">Here are some examples:</span></span>

- <span data-ttu-id="0e2d4-174">*Não foi possível resolver a GUID do campo: primarycontactid.msdyn\_contactpersonid. A pesquisa não foi encontrada: 000056. Experimente esta(s) URLs para verificar se os dados de referência existem: `https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/contacts?$select=msdyn_contactpersonid.contactid&$filter=msdyn_contactpersonid eq '000056'`*</span><span class="sxs-lookup"><span data-stu-id="0e2d4-174">*Couldn't resolve the guid for the field: primarycontactid.msdyn\_contactpersonid. The lookup was not found: 000056. Try this URL(s) to check if the reference data exists: `https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/contacts?$select=msdyn_contactpersonid.contactid&$filter=msdyn_contactpersonid eq '000056'`*</span></span>
- <span data-ttu-id="0e2d4-175">*Não foi possível resolver a GUID do campo: msdyn\_billingaccount.accountnumber. A pesquisa não foi encontrada: 1206-1. Experimente esta(s) URLs para verificar se os dados de referência existem: `https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/accounts?$select=accountnumber.account&$filter=accountnumber eq '1206-1'`*</span><span class="sxs-lookup"><span data-stu-id="0e2d4-175">*Couldn't resolve the guid for the field: msdyn\_billingaccount.accountnumber. The lookup was not found: 1206-1. Try this URL(s) to check if the reference data exists: `https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/accounts?$select=accountnumber.account&$filter=accountnumber eq '1206-1'`*</span></span>

<span data-ttu-id="0e2d4-176">Se algum registro na entidade cliente tiver valores nos campos **ContactPersonID** e **InvoiceAccount**, siga estas etapas para concluir a sincronização inicial.</span><span class="sxs-lookup"><span data-stu-id="0e2d4-176">If any records in the customer entity have values in the **ContactPersonID** and **InvoiceAccount** fields, follow these steps to complete the initial synchronization.</span></span> <span data-ttu-id="0e2d4-177">Você pode usar essa abordagem para qualquer entidade pronta para uso, como **Contas** e **Contatos**.</span><span class="sxs-lookup"><span data-stu-id="0e2d4-177">You can use this approach for any out-of-box entities, such **Accounts** and **Contacts**.</span></span>

1. <span data-ttu-id="0e2d4-178">No aplicativo Finance and Operations, exclua os campos **ContactPersonID** e **InvoiceAccount** do mapeamento **Clientes V3 (contas)** e salve o mapeamento.</span><span class="sxs-lookup"><span data-stu-id="0e2d4-178">In the Finance and Operations app, delete the **ContactPersonID** and **InvoiceAccount** fields from the **Customers V3 (accounts)** mapping, and then save the mapping.</span></span>

    1. <span data-ttu-id="0e2d4-179">Na página de mapeamento de gravação dupla para **Clientes V3 (contas)**, na guia **Mapeamentos de entidade**, no filtro esquerdo, selecione **Finance and Operations app.Customers V3**.</span><span class="sxs-lookup"><span data-stu-id="0e2d4-179">On the dual-write mapping page for **Customers V3 (accounts)**, on the **Entity mappings** tab, in the left filter, select **Finance and Operations app.Customers V3**.</span></span> <span data-ttu-id="0e2d4-180">No filtro direito, selecione **Common Data Service.Account**.</span><span class="sxs-lookup"><span data-stu-id="0e2d4-180">In the right filter, select **Common Data Service.Account**.</span></span>
    2. <span data-ttu-id="0e2d4-181">Procure **contactperson** para encontrar o campo de origem **ContactPersonID**.</span><span class="sxs-lookup"><span data-stu-id="0e2d4-181">Search for **contactperson** to find the **ContactPersonID** source field.</span></span>
    3. <span data-ttu-id="0e2d4-182">Selecione **Ações** e depois **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="0e2d4-182">Select **Actions**, and then select **Delete**.</span></span>

        ![Excluindo o campo ContactPersonID](media/cust_selfref3.png)

    4. <span data-ttu-id="0e2d4-184">Repita essas etapas para excluir o campo **InvoiceAccount**.</span><span class="sxs-lookup"><span data-stu-id="0e2d4-184">Repeat these steps to delete the **InvoiceAccount** field.</span></span>

        ![Excluindo o campo InvoiceAccount](media/cust_selfref4.png)

    5. <span data-ttu-id="0e2d4-186">Salve as alterações feitas no mapeamento.</span><span class="sxs-lookup"><span data-stu-id="0e2d4-186">Save your changes to the mapping.</span></span>

2. <span data-ttu-id="0e2d4-187">Desative o controle de alterações para a entidade **Clientes V3**.</span><span class="sxs-lookup"><span data-stu-id="0e2d4-187">Turn off change tracking for the **Customers V3** entity.</span></span>

    1. <span data-ttu-id="0e2d4-188">No espaço de trabalho **Gerenciamento de dados**, selecione o bloco **Entidades de dados**.</span><span class="sxs-lookup"><span data-stu-id="0e2d4-188">In the **Data management** workspace, select the **Data entities** tile.</span></span>
    2. <span data-ttu-id="0e2d4-189">Selecione a entidade **Clientes V3**.</span><span class="sxs-lookup"><span data-stu-id="0e2d4-189">Select the **Customers V3** entity.</span></span>
    3. <span data-ttu-id="0e2d4-190">No Painel de Ações, selecione **Opções** e depois selecione **Controle de Alterações**.</span><span class="sxs-lookup"><span data-stu-id="0e2d4-190">On the Action Pane, select **Options**, and then select **Change tracking**.</span></span>

        ![Selecionando a opção Controle de Alterações](media/selfref_options.png)

    4. <span data-ttu-id="0e2d4-192">Selecione **Desabilitar Controle de Alterações**.</span><span class="sxs-lookup"><span data-stu-id="0e2d4-192">Select **Disable Change Tracking**.</span></span>

        ![Selecionando Desabilitar Controle de Alterações](media/selfref_tracking.png)

3. <span data-ttu-id="0e2d4-194">Execute a sincronização inicial para o mapeamento de **Clientes V3 (contas)**.</span><span class="sxs-lookup"><span data-stu-id="0e2d4-194">Run initial synchronization for the **Customers V3 (Accounts)** mapping.</span></span> <span data-ttu-id="0e2d4-195">A sincronização inicial deve ser executada com êxito, sem erros.</span><span class="sxs-lookup"><span data-stu-id="0e2d4-195">The initial synchronization should run successfully, without any errors.</span></span>
4. <span data-ttu-id="0e2d4-196">Execute a sincronização inicial para o mapeamento de **Contatos de CDS V2 (contatos)**.</span><span class="sxs-lookup"><span data-stu-id="0e2d4-196">Run initial synchronization for the **CDS Contacts V2 (contacts)** mapping.</span></span>

    > [!NOTE]
    > <span data-ttu-id="0e2d4-197">Há dois mapas com o mesmo nome.</span><span class="sxs-lookup"><span data-stu-id="0e2d4-197">There are two maps that have the same name.</span></span> <span data-ttu-id="0e2d4-198">Certifique-se de selecionar o mapa que tenha a seguinte descrição na guia **Detalhes**: **Gravação dupla para sincronização entre Contatos FO.CDS do Fornecedor V2 para CDS.Contacts. Exige novo pacote \[Dynamics365SupplyChainExtended\].**</span><span class="sxs-lookup"><span data-stu-id="0e2d4-198">Be sure to select the map that has the following description on the **Details** tab: **Dual-write template for sync between FO.CDS Vendor Contacts V2 to CDS.Contacts. Requires new package \[Dynamics365SupplyChainExtended\].**</span></span>

5. <span data-ttu-id="0e2d4-199">Adicione os campos **InvoiceAccount** e **ContactPersonId** novamente no mapeamento **Clientes V3 (contas)** e depois salve o mapeamento.</span><span class="sxs-lookup"><span data-stu-id="0e2d4-199">Add the **InvoiceAccount** and **ContactPersonId** fields back to the **Customers V3 (Accounts)** mapping, and then save the mapping.</span></span> <span data-ttu-id="0e2d4-200">Os campos **InvoiceAccount** e **ContactPersonId** agora fazem parte do modo de sincronização ao vivo novamente.</span><span class="sxs-lookup"><span data-stu-id="0e2d4-200">Both the **InvoiceAccount** field and the **ContactPersonId** field are now part of live synchronization mode again.</span></span> <span data-ttu-id="0e2d4-201">Na próxima etapa, você executará a sincronização inicial desses campos.</span><span class="sxs-lookup"><span data-stu-id="0e2d4-201">In the next step, you will do the initial synchronization for these fields.</span></span>
6. <span data-ttu-id="0e2d4-202">Execute a sincronização inicial novamente para o mapeamento de **Clientes V3 (contas)**.</span><span class="sxs-lookup"><span data-stu-id="0e2d4-202">Run initial synchronization again for the **Customers V3 (Accounts)** mapping.</span></span> <span data-ttu-id="0e2d4-203">Como o controle de alterações está desabilitado, os dados de **InvoiceAccount** e **ContactPersonId** serão sincronizados do aplicativo Finance and Operations para o Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="0e2d4-203">Because change tracking is turned off, the data for **InvoiceAccount** and **ContactPersonId** will be synced from the Finance and Operations app to Common Data Service.</span></span>
7. <span data-ttu-id="0e2d4-204">Para sincronizar os dados de **InvoiceAccount** e **ContactPersonId** do Common Data Service para o Finance and Operations, você deve usar um projeto de integração de dados.</span><span class="sxs-lookup"><span data-stu-id="0e2d4-204">To sync the data for **InvoiceAccount** and **ContactPersonId** from Common Data Service to the Finance and Operations app, you must use a data integration project.</span></span>

    1. <span data-ttu-id="0e2d4-205">No Power Apps, crie um projeto de integração de dados entre as entidades **Sales.Account** e **Finance and Operations apps.Customers V3**.</span><span class="sxs-lookup"><span data-stu-id="0e2d4-205">In Power Apps, create a data integration project between the **Sales.Account** and **Finance and Operations apps.Customers V3** entities.</span></span> <span data-ttu-id="0e2d4-206">A direção de dados deve ser do Common Data Service para o aplicativo do Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="0e2d4-206">The data direction must be from Common Data Service to the Finance and Operations app.</span></span> <span data-ttu-id="0e2d4-207">Como **InvoiceAccount** é um novo atributo na gravação dupla, talvez você queira ignorar a sincronização inicial desse atributo.</span><span class="sxs-lookup"><span data-stu-id="0e2d4-207">Because **InvoiceAccount** is a new attribute in dual-write, you might want to skip initial synchronization for it.</span></span> <span data-ttu-id="0e2d4-208">Para obter mais informações, consulte [Integrar dados no Common Data Service](https://docs.microsoft.com/power-platform/admin/data-integrator).</span><span class="sxs-lookup"><span data-stu-id="0e2d4-208">For more information, see [Integrate data into Common Data Service](https://docs.microsoft.com/power-platform/admin/data-integrator).</span></span>

        <span data-ttu-id="0e2d4-209">A ilustração a seguir mostra um projeto que atualiza **CustomerAccount** e **ContactPersonId**.</span><span class="sxs-lookup"><span data-stu-id="0e2d4-209">The following illustration shows a project that updates **CustomerAccount** and **ContactPersonId**.</span></span>

        ![Projeto de integração de dados para atualizar CustomerAccount e ContactPersonId](media/cust_selfref6.png)

    2. <span data-ttu-id="0e2d4-211">Adicione os critérios da empresa no filtro do Common Data Service, para que somente os registros que correspondem aos critérios do filtro sejam atualizados no aplicativo do Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="0e2d4-211">Add the company criteria in the filter on the Common Data Service side, so that only records that match the filter criteria will be updated in the Finance and Operations app.</span></span> <span data-ttu-id="0e2d4-212">Para adicionar um filtro, selecione o botão de filtro.</span><span class="sxs-lookup"><span data-stu-id="0e2d4-212">To add a filter, select the filter button.</span></span> <span data-ttu-id="0e2d4-213">Em seguida, na caixa de diálogo **Editar consulta**, você pode adicionar uma consulta de filtro como **\_msdyn\_company\_value eq '\<guid\>'**.</span><span class="sxs-lookup"><span data-stu-id="0e2d4-213">Then, in the **Edit query** dialog box, you can add a filter query such as **\_msdyn\_company\_value eq '\<guid\>'**.</span></span> 

        > <span data-ttu-id="0e2d4-214">[NOTA] Se o botão de filtro não estiver presente, crie um tíquete de suporte para solicitar que a equipe de integração de dados habilite a capacidade de filtro no seu locatário.</span><span class="sxs-lookup"><span data-stu-id="0e2d4-214">[NOTE] If the filter button isn't present, create a support ticket to ask the data integration team to enable the filter capability on your tenant.</span></span>

        <span data-ttu-id="0e2d4-215">Se você não inserir uma consulta de filtro para **\_msdyn\_company\_value**, todos os registros serão sincronizados.</span><span class="sxs-lookup"><span data-stu-id="0e2d4-215">If you don't enter a filter query for **\_msdyn\_company\_value**, all the records will be synced.</span></span>

        ![Adicionando uma consulta de filtro](media/cust_selfref7.png)

    <span data-ttu-id="0e2d4-217">A sincronização inicial dos registros está concluída.</span><span class="sxs-lookup"><span data-stu-id="0e2d4-217">The initial synchronization of the records is now completed.</span></span>

8. <span data-ttu-id="0e2d4-218">No aplicativo do Finance and Operations, habilite o controle de alterações novamente para a entidade **Clientes V3**.</span><span class="sxs-lookup"><span data-stu-id="0e2d4-218">In the Finance and Operations app, turn change tracking back on for the **Customers V3** entity.</span></span>
