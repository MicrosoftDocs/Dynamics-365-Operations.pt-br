---
title: Solucionar problemas durante a sincronização inicial
description: Este tópico fornece informações sobre como solucionar problemas que podem ajudá-lo a corrigir problemas que podem acontecer durante a sincronização inicial.
author: RamaKrishnamoorthy
ms.date: 03/16/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-03-16
ms.openlocfilehash: c716707140c85b06ad2f084c10c4b2d0ecfea82e
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5754005"
---
# <a name="troubleshoot-issues-during-initial-synchronization"></a><span data-ttu-id="43d81-103">Solucionar problemas durante a sincronização inicial</span><span class="sxs-lookup"><span data-stu-id="43d81-103">Troubleshoot issues during initial synchronization</span></span>

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="43d81-104">Este tópico fornece informações de solução de problemas para integração de gravação dupla entre aplicativos do Finance and Operations e o Dataverse.</span><span class="sxs-lookup"><span data-stu-id="43d81-104">This topic provides troubleshooting information for dual-write integration between Finance and Operations apps and Dataverse.</span></span> <span data-ttu-id="43d81-105">Especificamente, ele fornece informações sobre como solucionar problemas que podem ajudá-lo a corrigir problemas que podem acontecer durante a sincronização inicial.</span><span class="sxs-lookup"><span data-stu-id="43d81-105">Specifically, it provides information that can help you fix issues that might occur during initial synchronization.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="43d81-106">Alguns dos problemas que este tópico aborda podem exigir a função de administrador do sistema ou as credenciais de administrador do locatário Microsoft Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="43d81-106">Some of the issues that this topic addresses might require either the system admin role or Microsoft Azure Active Directory (Azure AD) tenant admin credentials.</span></span> <span data-ttu-id="43d81-107">A seção para cada problema explica se uma função ou credenciais específicas são necessárias.</span><span class="sxs-lookup"><span data-stu-id="43d81-107">The section for each issue explains whether a specific role or credentials are required.</span></span>

## <a name="check-for-initial-synchronization-errors-in-a-finance-and-operations-app"></a><span data-ttu-id="43d81-108">Verificar erros de sincronização inicial em um aplicativo do Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="43d81-108">Check for initial synchronization errors in a Finance and Operations app</span></span>

<span data-ttu-id="43d81-109">Depois de habilitar os modelos de mapeamento, o status dos mapas deve estar em **Execução**.</span><span class="sxs-lookup"><span data-stu-id="43d81-109">After you enable the mapping templates, the status of the maps should be **Running**.</span></span> <span data-ttu-id="43d81-110">Se o status **Não estiver em execução**, ocorrerão erros durante a sincronização inicial.</span><span class="sxs-lookup"><span data-stu-id="43d81-110">If the status is **Not running**, errors occurred during initial synchronization.</span></span> <span data-ttu-id="43d81-111">Para exibir os erros, selecione a guia **Detalhes de sincronização inicial** na página **Gravação dupla**.</span><span class="sxs-lookup"><span data-stu-id="43d81-111">To view the errors, select the **Initial sync details** tab on the **Dual-write** page.</span></span>

![Erro na guia Detalhes da sincronização inicial](media/initial_sync_status.png)

## <a name="you-cant-complete-initial-synchronization-400-bad-request"></a><span data-ttu-id="43d81-113">Não é possível concluir a sincronização inicial: 400 Solicitação incorreta</span><span class="sxs-lookup"><span data-stu-id="43d81-113">You can't complete initial synchronization: 400 Bad Request</span></span>

<span data-ttu-id="43d81-114">**Função necessária para corrigir o problema:** administrador do sistema</span><span class="sxs-lookup"><span data-stu-id="43d81-114">**Required role to fix the issue:** System admin</span></span>

<span data-ttu-id="43d81-115">A seguinte mensagem de erro pode ser exibida ao tentar executar o mapeamento e a sincronização inicial:</span><span class="sxs-lookup"><span data-stu-id="43d81-115">You might receive the following error message when you try to run the mapping and initial synchronization:</span></span>

<span data-ttu-id="43d81-116">*(\[Solicitação Incorreta\], O servidor remoto retornou um erro: (400) Solicitação Incorreta.), a exportação AX encontrou um erro*</span><span class="sxs-lookup"><span data-stu-id="43d81-116">*(\[Bad Request\], The remote server returned an error: (400) Bad Request.), AX export encountered an error*</span></span>

<span data-ttu-id="43d81-117">Veja aqui um exemplo da mensagem de erro completa.</span><span class="sxs-lookup"><span data-stu-id="43d81-117">Here is an example of the full error message.</span></span>

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

<span data-ttu-id="43d81-118">Se esse erro ocorrer consistentemente e você não puder concluir a sincronização inicial, siga estas etapas para corrigir o problema.</span><span class="sxs-lookup"><span data-stu-id="43d81-118">If this error occurs consistently, and you can't complete the initial synchronization, follow these steps to fix the issue.</span></span>

1. <span data-ttu-id="43d81-119">Faça login na máquina virtual (VM) para o aplicativo Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="43d81-119">Sign in to the virtual machine (VM) for the Finance and Operations app.</span></span>
2. <span data-ttu-id="43d81-120">Abra o console de gerenciamento da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="43d81-120">Open Microsoft Management Console.</span></span>
3. <span data-ttu-id="43d81-121">No painel **Serviços**, verifique se o serviço de estrutura de importação/exportação de dados do Microsoft Dynamics 365 está em execução.</span><span class="sxs-lookup"><span data-stu-id="43d81-121">In the **Services** pane, make sure that the Microsoft Dynamics 365 Data import export framework service is running.</span></span> <span data-ttu-id="43d81-122">Reinicie-o se ele tiver sido interrompido, pois a sincronização inicial requer essa ação.</span><span class="sxs-lookup"><span data-stu-id="43d81-122">Restart it if it has been stopped, because the initial synchronization requires it.</span></span>

## <a name="initial-synchronization-error-403-forbidden"></a><span data-ttu-id="43d81-123">Erro de sincronização inicial: 403 Proibido</span><span class="sxs-lookup"><span data-stu-id="43d81-123">Initial synchronization error: 403 Forbidden</span></span>

<span data-ttu-id="43d81-124">A seguinte mensagem de erro pode ser exibida durante sincronização inicial:</span><span class="sxs-lookup"><span data-stu-id="43d81-124">You might receive the following error message during initial synchronization:</span></span>

<span data-ttu-id="43d81-125">*(\[Proibido\], O servidor remoto retornou um erro: (403) Proibido.), a exportação AX encontrou um erro*</span><span class="sxs-lookup"><span data-stu-id="43d81-125">*(\[Forbidden\], The remote server returned an error: (403) Forbidden.), AX export encountered an error*</span></span>

<span data-ttu-id="43d81-126">Para corrigir o problema, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="43d81-126">To fix the issue, follow these steps.</span></span>

1. <span data-ttu-id="43d81-127">Entrar no aplicativo Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="43d81-127">Sign in to the Finance and Operations app.</span></span>
2. <span data-ttu-id="43d81-128">Na página **aplicativo do Azure Active Directory**, exclua o cliente **DtAppID** e, em seguida, adicione-o novamente.</span><span class="sxs-lookup"><span data-stu-id="43d81-128">On the **Azure Active Directory applications** page, delete the **DtAppID** client, and then add it again.</span></span>

![Cliente DtAppID na lista de aplicativos do Azure AD](media/aad_applications.png)

## <a name="self-reference-or-circular-reference-failures-during-initial-synchronization"></a><span data-ttu-id="43d81-130">Falhas de autorreferência ou referência circular durante a sincronização inicial</span><span class="sxs-lookup"><span data-stu-id="43d81-130">Self-reference or circular reference failures during initial synchronization</span></span>

<span data-ttu-id="43d81-131">Você poderá receber mensagens de erro se um dos seus mapeamentos tiver autorreferências ou referências circulares:</span><span class="sxs-lookup"><span data-stu-id="43d81-131">You might receive an error messages if any of your mappings have self-references or circular references.</span></span> <span data-ttu-id="43d81-132">Os erros são classificados nestas categorias:</span><span class="sxs-lookup"><span data-stu-id="43d81-132">The errors fall into these categories:</span></span>

- [<span data-ttu-id="43d81-133">Erros em Fornecedores V2 para mapeamento de tabela msdyn_vendors</span><span class="sxs-lookup"><span data-stu-id="43d81-133">Errors in the Vendors V2–to–msdyn_vendors table mapping</span></span>](#error-vendor-map)
- [<span data-ttu-id="43d81-134">Erros no mapeamento de Clientes V3 para a tabela Contas</span><span class="sxs-lookup"><span data-stu-id="43d81-134">Errors in the Customers V3–to–Accounts table mapping</span></span>](#error-customer-map)

## <a name="resolve-errors-in-the-vendors-v2tomsdyn_vendors-table-mapping"></a><a id="error-vendor-map"></a><span data-ttu-id="43d81-135">Resolver erros em Fornecedores V2 para mapeamento de tabela msdyn_vendors</span><span class="sxs-lookup"><span data-stu-id="43d81-135">Resolve errors in the Vendors V2–to–msdyn_vendors table mapping</span></span>

<span data-ttu-id="43d81-136">Você poderá encontrar erros de sincronização inicial para o mapeamento de **Fornecedores V2** para **msdyn\_vendors** se as tabelas tiverem linhas existentes com valores nas colunas **PrimaryContactPersonId** e **InvoiceVendorAccountNumber**.</span><span class="sxs-lookup"><span data-stu-id="43d81-136">You might encounter initial synchronization errors for the mapping of **Vendors V2** to **msdyn\_vendors** if the tables have existing rows where there are values in the **PrimaryContactPersonId** and **InvoiceVendorAccountNumber** columns.</span></span> <span data-ttu-id="43d81-137">Esses erros ocorrem porque **InvoiceVendorAccountNumber** é uma coluna de auto-referência e **PrimaryContactPersonId** é uma referência circular no mapeamento do fornecedor.</span><span class="sxs-lookup"><span data-stu-id="43d81-137">These errors occur because **InvoiceVendorAccountNumber** is a self-referencing column, and **PrimaryContactPersonId** is a circular reference in the vendor mapping.</span></span>

<span data-ttu-id="43d81-138">As mensagens de erro recebidas terão o seguinte formulário.</span><span class="sxs-lookup"><span data-stu-id="43d81-138">The error messages that you receive will have the following form.</span></span>

<span data-ttu-id="43d81-139">*Não foi possível resolver a GUID do campo: \<field\>. A pesquisa não foi encontrada: \<value\>. Experimente esta(s) URLs para verificar se os dados de referência existem: `https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/<entity>?$select=<field>&$filter=<field> eq <value>`*</span><span class="sxs-lookup"><span data-stu-id="43d81-139">*Couldn't resolve the guid for the field: \<field\>. The lookup was not found: \<value\>. Try this URL(s) to check if the reference data exists: `https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/<entity>?$select=<field>&$filter=<field> eq <value>`*</span></span>

<span data-ttu-id="43d81-140">Eis alguns exemplos:</span><span class="sxs-lookup"><span data-stu-id="43d81-140">Here are some examples:</span></span>

- <span data-ttu-id="43d81-141">*Não foi possível resolver a GUID do campo: msdyn\_vendorprimarycontactperson.msdyn\_contactpersonid. A pesquisa não foi encontrada: 000056. Experimente esta(s) URLs para verificar se os dados de referência existem: `https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/contacts?$select=msdyn_contactpersonid.contactid&$filter=msdyn_contactpersonid eq '000056'`*</span><span class="sxs-lookup"><span data-stu-id="43d81-141">*Couldn't resolve the guid for the field: msdyn\_vendorprimarycontactperson.msdyn\_contactpersonid. The lookup was not found: 000056. Try this URL(s) to check if the reference data exists: `https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/contacts?$select=msdyn_contactpersonid.contactid&$filter=msdyn_contactpersonid eq '000056'`*</span></span>
- <span data-ttu-id="43d81-142">*Não foi possível resolver a GUID do campo: msdyn\_invoicevendoraccountnumber.msdyn\_vendoraccountnumber. A pesquisa não foi encontrada: V24-1. Experimente esta(s) URLs para verificar se os dados de referência existem: `https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/msdn_vendors?$select=msdyn_vendoraccountnumber,msdyn_vendorid&$filter=msdyn_vendoraccountnumber eq 'V24-1'`*</span><span class="sxs-lookup"><span data-stu-id="43d81-142">*Couldn't resolve the guid for the field: msdyn\_invoicevendoraccountnumber.msdyn\_vendoraccountnumber. The lookup was not found: V24-1. Try this URL(s) to check if the reference data exists: `https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/msdn_vendors?$select=msdyn_vendoraccountnumber,msdyn_vendorid&$filter=msdyn_vendoraccountnumber eq 'V24-1'`*</span></span>

<span data-ttu-id="43d81-143">Se alguma linha na tabela do fornecedor tiver valores nas colunas **PrimaryContactPersonId** e **InvoiceVendorAccountNumber**, siga estas etapas para concluir a sincronização inicial.</span><span class="sxs-lookup"><span data-stu-id="43d81-143">If any rows in the vendor table have values in the **PrimaryContactPersonId** and **InvoiceVendorAccountNumber** columns, follow these steps to complete the initial synchronization.</span></span>

1. <span data-ttu-id="43d81-144">No aplicativo Finance and Operations, exclua as colunas **PrimaryContactPersonId** e **InvoiceVendorAccountNumber** do mapeamento e depois salve o mapeamento.</span><span class="sxs-lookup"><span data-stu-id="43d81-144">In the Finance and Operations app, delete the **PrimaryContactPersonId** and **InvoiceVendorAccountNumber** columns from the mapping, and then save the mapping.</span></span>

    1. <span data-ttu-id="43d81-145">Na página de mapeamento de gravação dupla para **Fornecedores V2 (msdyn\_vendors)**, na guia **Mapeamentos de tabela**, no filtro esquerdo, selecione **Finance and Operations apps.Vendors V2**.</span><span class="sxs-lookup"><span data-stu-id="43d81-145">On the dual-write mapping page for **Vendors V2 (msdyn\_vendors)**, on the **Table mappings** tab, in the left filter, select **Finance and Operations apps.Vendors V2**.</span></span> <span data-ttu-id="43d81-146">No filtro direito, selecione **Sales.Vendor**.</span><span class="sxs-lookup"><span data-stu-id="43d81-146">In the right filter, select **Sales.Vendor**.</span></span>
    2. <span data-ttu-id="43d81-147">Procure **primarycontactperson** para encontrar a coluna de origem **PrimaryContactPersonId**.</span><span class="sxs-lookup"><span data-stu-id="43d81-147">Search for **primarycontactperson** to find the **PrimaryContactPersonId** source column.</span></span>
    3. <span data-ttu-id="43d81-148">Selecione **Ações** e depois **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="43d81-148">Select **Actions**, and then select **Delete**.</span></span>

        ![Excluindo a coluna PrimaryContactPersonId](media/vend_selfref3.png)

    4. <span data-ttu-id="43d81-150">Repita essas etapas para excluir a coluna **InvoiceVendorAccountNumber**.</span><span class="sxs-lookup"><span data-stu-id="43d81-150">Repeat these steps to delete the **InvoiceVendorAccountNumber** column.</span></span>

        ![Excluindo a coluna InvoiceVendorAccountNumber](media/vend-selfref4.png)

    5. <span data-ttu-id="43d81-152">Salve as alterações feitas no mapeamento.</span><span class="sxs-lookup"><span data-stu-id="43d81-152">Save your changes to the mapping.</span></span>

2. <span data-ttu-id="43d81-153">Desative o controle de alterações para a tabela **Fornecedor V2**.</span><span class="sxs-lookup"><span data-stu-id="43d81-153">Turn off change tracking for the **Vendors V2** table.</span></span>

    1. <span data-ttu-id="43d81-154">No espaço de trabalho **Gerenciamento de dados**, selecione o bloco **Tabelas de dados**.</span><span class="sxs-lookup"><span data-stu-id="43d81-154">In the **Data management** workspace, select the **Data tables** tile.</span></span>
    2. <span data-ttu-id="43d81-155">Selecione a tabela **Fornecedores V2**.</span><span class="sxs-lookup"><span data-stu-id="43d81-155">Select the **Vendors V2** table.</span></span>
    3. <span data-ttu-id="43d81-156">No Painel de Ações, selecione **Opções** e depois selecione **Controle de Alterações**.</span><span class="sxs-lookup"><span data-stu-id="43d81-156">On the Action Pane, select **Options**, and then select **Change tracking**.</span></span>

        ![Selecionando a opção Controle de Alterações](media/selfref_options.png)

    4. <span data-ttu-id="43d81-158">Selecione **Desabilitar Controle de Alterações**.</span><span class="sxs-lookup"><span data-stu-id="43d81-158">Select **Disable Change Tracking**.</span></span>

        ![Selecionando Desabilitar Controle de Alterações](media/selfref_tracking.png)

3. <span data-ttu-id="43d81-160">Execute a sincronização inicial para mapeamento do **Fornecedor V2 (msdyn\_vendors)**.</span><span class="sxs-lookup"><span data-stu-id="43d81-160">Run initial synchronization for the **Vendors V2 (msdyn\_vendors)** mapping.</span></span> <span data-ttu-id="43d81-161">A sincronização inicial deve ser executada com êxito, sem erros.</span><span class="sxs-lookup"><span data-stu-id="43d81-161">The initial synchronization should run successfully, without any errors.</span></span>
4. <span data-ttu-id="43d81-162">Execute a sincronização inicial para o mapeamento de **Contatos de CDS V2 (contatos)**.</span><span class="sxs-lookup"><span data-stu-id="43d81-162">Run initial synchronization for the **CDS Contacts V2 (contacts)** mapping.</span></span> <span data-ttu-id="43d81-163">Você deverá sincronizar este mapeamento se desejar sincronizar a coluna de contato principal na tabela fornecedores, pois a sincronização inicial também precisa ser feita para as linhas de contatos.</span><span class="sxs-lookup"><span data-stu-id="43d81-163">You must sync this mapping if you want to sync the primary contact column on the vendors table, because initial synchronization must also be done for the contact rows.</span></span>
5. <span data-ttu-id="43d81-164">Adicione as colunas **PrimaryContactPersonId** e **InvoiceVendorAccountNumber** novamente ao mapeamento **Fornecedores V2 (msdyn\_vendors)** e salve o mapeamento.</span><span class="sxs-lookup"><span data-stu-id="43d81-164">Add the **PrimaryContactPersonId** and **InvoiceVendorAccountNumber** columns back to the **Vendors V2 (msdyn\_vendors)** mapping, and then save the mapping.</span></span>
6. <span data-ttu-id="43d81-165">Execute a sincronização inicial novamente para o mapeamento do **Fornecedor V2 (msdyn\_vendors)**.</span><span class="sxs-lookup"><span data-stu-id="43d81-165">Run initial synchronization again for the **Vendors V2 (msdyn\_vendors)** mapping.</span></span> <span data-ttu-id="43d81-166">Como o controle de alterações está desabilitado, todas as linhas serão sincronizadas.</span><span class="sxs-lookup"><span data-stu-id="43d81-166">Because change tracking is turned off, all the rows will be synced.</span></span>
7. <span data-ttu-id="43d81-167">Ative o controle de alterações novamente para a tabela **Fornecedor V2**.</span><span class="sxs-lookup"><span data-stu-id="43d81-167">Turn change tracking back on for the **Vendors V2** table.</span></span>

## <a name="resolve-errors-in-the-customers-v3toaccounts-table-mapping"></a><a id="error-customer-map"></a><span data-ttu-id="43d81-168">Resolver erros no mapeamento de Clientes V3 para a tabela Contas</span><span class="sxs-lookup"><span data-stu-id="43d81-168">Resolve errors in the Customers V3–to–Accounts table mapping</span></span>

<span data-ttu-id="43d81-169">Você poderá encontrar erros de sincronização inicial para o mapeamento de **Clientes V3** para **Contas** se as tabelas tiverem linhas existentes com valores nas colunas **ContactPersonID** e **InvoiceAccount**.</span><span class="sxs-lookup"><span data-stu-id="43d81-169">You might encounter initial synchronization errors for the mapping of **Customers V3** to **Accounts** if the tables have existing rows where there are values in the **ContactPersonID** and **InvoiceAccount** columns.</span></span> <span data-ttu-id="43d81-170">Esses erros ocorrem porque **InvoiceAccount** é uma coluna de autorreferência e **ContactPersonID** é uma referência circular no mapeamento do fornecedor.</span><span class="sxs-lookup"><span data-stu-id="43d81-170">These errors occur because **InvoiceAccount** is a self-referencing column, and **ContactPersonID** is a circular reference in the vendor mapping.</span></span>

<span data-ttu-id="43d81-171">As mensagens de erro recebidas terão o seguinte formulário.</span><span class="sxs-lookup"><span data-stu-id="43d81-171">The error messages that you receive will have the following form.</span></span>

<span data-ttu-id="43d81-172">*Não foi possível resolver a GUID do campo: \<field\>. A pesquisa não foi encontrada: \<value\>. Experimente esta(s) URLs para verificar se os dados de referência existem: `https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/<entity>?$select=<field>&$filter=<field> eq <value>`*</span><span class="sxs-lookup"><span data-stu-id="43d81-172">*Couldn't resolve the guid for the field: \<field\>. The lookup was not found: \<value\>. Try this URL(s) to check if the reference data exists: `https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/<entity>?$select=<field>&$filter=<field> eq <value>`*</span></span>

<span data-ttu-id="43d81-173">Eis alguns exemplos:</span><span class="sxs-lookup"><span data-stu-id="43d81-173">Here are some examples:</span></span>

- <span data-ttu-id="43d81-174">*Não foi possível resolver a GUID do campo: primarycontactid.msdyn\_contactpersonid. A pesquisa não foi encontrada: 000056. Experimente esta(s) URLs para verificar se os dados de referência existem: `https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/contacts?$select=msdyn_contactpersonid.contactid&$filter=msdyn_contactpersonid eq '000056'`*</span><span class="sxs-lookup"><span data-stu-id="43d81-174">*Couldn't resolve the guid for the field: primarycontactid.msdyn\_contactpersonid. The lookup was not found: 000056. Try this URL(s) to check if the reference data exists: `https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/contacts?$select=msdyn_contactpersonid.contactid&$filter=msdyn_contactpersonid eq '000056'`*</span></span>
- <span data-ttu-id="43d81-175">*Não foi possível resolver a GUID do campo: msdyn\_billingaccount.accountnumber. A pesquisa não foi encontrada: 1206-1. Experimente esta(s) URLs para verificar se os dados de referência existem: `https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/accounts?$select=accountnumber.account&$filter=accountnumber eq '1206-1'`*</span><span class="sxs-lookup"><span data-stu-id="43d81-175">*Couldn't resolve the guid for the field: msdyn\_billingaccount.accountnumber. The lookup was not found: 1206-1. Try this URL(s) to check if the reference data exists: `https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/accounts?$select=accountnumber.account&$filter=accountnumber eq '1206-1'`*</span></span>

<span data-ttu-id="43d81-176">Se alguma linha na tabela cliente tiver valores nas colunas **ContactPersonID** e **InvoiceAccount**, siga estas etapas para concluir a sincronização inicial.</span><span class="sxs-lookup"><span data-stu-id="43d81-176">If any rows in the customer table have values in the **ContactPersonID** and **InvoiceAccount** columns, follow these steps to complete the initial synchronization.</span></span> <span data-ttu-id="43d81-177">Você pode usar essa abordagem para qualquer tabela pronta para uso, como **Contas** e **Contatos**.</span><span class="sxs-lookup"><span data-stu-id="43d81-177">You can use this approach for any out-of-box tables, such **Accounts** and **Contacts**.</span></span>

1. <span data-ttu-id="43d81-178">No aplicativo Finance and Operations, exclua as colunas **ContactPersonID** e **InvoiceAccount** do mapeamento **Clientes V3 (contas)** e salve o mapeamento.</span><span class="sxs-lookup"><span data-stu-id="43d81-178">In the Finance and Operations app, delete the **ContactPersonID** and **InvoiceAccount** columns from the **Customers V3 (accounts)** mapping, and then save the mapping.</span></span>

    1. <span data-ttu-id="43d81-179">Na página de mapeamento de gravação dupla para **Clientes V3 (contas)**, na guia **Mapeamentos de tabela**, no filtro esquerdo, selecione **Finance and Operations app.Customers V3**.</span><span class="sxs-lookup"><span data-stu-id="43d81-179">On the dual-write mapping page for **Customers V3 (accounts)**, on the **Table mappings** tab, in the left filter, select **Finance and Operations app.Customers V3**.</span></span> <span data-ttu-id="43d81-180">No filtro direito, selecione **Dataverse.Account**.</span><span class="sxs-lookup"><span data-stu-id="43d81-180">In the right filter, select **Dataverse.Account**.</span></span>
    2. <span data-ttu-id="43d81-181">Pesquise **contactperson** para encontrar a coluna de origem **ContactPersonID**.</span><span class="sxs-lookup"><span data-stu-id="43d81-181">Search for **contactperson** to find the **ContactPersonID** source column.</span></span>
    3. <span data-ttu-id="43d81-182">Selecione **Ações** e depois **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="43d81-182">Select **Actions**, and then select **Delete**.</span></span>

        ![Excluir a coluna ContactPersonID](media/cust_selfref3.png)

    4. <span data-ttu-id="43d81-184">Repita essas etapas para excluir a coluna **InvoiceAccount**.</span><span class="sxs-lookup"><span data-stu-id="43d81-184">Repeat these steps to delete the **InvoiceAccount** column.</span></span>

        ![Excluir a coluna InvoiceAccount](media/cust_selfref4.png)

    5. <span data-ttu-id="43d81-186">Salve as alterações feitas no mapeamento.</span><span class="sxs-lookup"><span data-stu-id="43d81-186">Save your changes to the mapping.</span></span>

2. <span data-ttu-id="43d81-187">Desative o controle de alterações para a tabela **Clientes V3**.</span><span class="sxs-lookup"><span data-stu-id="43d81-187">Turn off change tracking for the **Customers V3** table.</span></span>

    1. <span data-ttu-id="43d81-188">No espaço de trabalho **Gerenciamento de dados**, selecione o bloco **Tabelas de dados**.</span><span class="sxs-lookup"><span data-stu-id="43d81-188">In the **Data management** workspace, select the **Data tables** tile.</span></span>
    2. <span data-ttu-id="43d81-189">Selecione a tabela **Fornecedor V3**.</span><span class="sxs-lookup"><span data-stu-id="43d81-189">Select the **Customers V3** table.</span></span>
    3. <span data-ttu-id="43d81-190">No Painel de Ações, selecione **Opções** e depois selecione **Controle de Alterações**.</span><span class="sxs-lookup"><span data-stu-id="43d81-190">On the Action Pane, select **Options**, and then select **Change tracking**.</span></span>

        ![Selecionando a opção Controle de Alterações](media/selfref_options.png)

    4. <span data-ttu-id="43d81-192">Selecione **Desabilitar Controle de Alterações**.</span><span class="sxs-lookup"><span data-stu-id="43d81-192">Select **Disable Change Tracking**.</span></span>

        ![Selecionando Desabilitar Controle de Alterações](media/selfref_tracking.png)

3. <span data-ttu-id="43d81-194">Execute a sincronização inicial para o mapeamento de **Clientes V3 (contas)**.</span><span class="sxs-lookup"><span data-stu-id="43d81-194">Run initial synchronization for the **Customers V3 (Accounts)** mapping.</span></span> <span data-ttu-id="43d81-195">A sincronização inicial deve ser executada com êxito, sem erros.</span><span class="sxs-lookup"><span data-stu-id="43d81-195">The initial synchronization should run successfully, without any errors.</span></span>
4. <span data-ttu-id="43d81-196">Execute a sincronização inicial para o mapeamento de **Contatos de CDS V2 (contatos)**.</span><span class="sxs-lookup"><span data-stu-id="43d81-196">Run initial synchronization for the **CDS Contacts V2 (contacts)** mapping.</span></span>

    > [!NOTE]
    > <span data-ttu-id="43d81-197">Há dois mapas com o mesmo nome.</span><span class="sxs-lookup"><span data-stu-id="43d81-197">There are two maps that have the same name.</span></span> <span data-ttu-id="43d81-198">Certifique-se de selecionar o mapa que tenha a seguinte descrição na guia **Detalhes**: **Gravação dupla para sincronização entre Contatos FO.CDS do Fornecedor V2 para CDS.Contacts. Exige novo pacote \[Dynamics365SupplyChainExtended\].**</span><span class="sxs-lookup"><span data-stu-id="43d81-198">Be sure to select the map that has the following description on the **Details** tab: **Dual-write template for sync between FO.CDS Vendor Contacts V2 to CDS.Contacts. Requires new package \[Dynamics365SupplyChainExtended\].**</span></span>

5. <span data-ttu-id="43d81-199">Adicione as colunas **InvoiceAccount** e **ContactPersonId** novamente no mapeamento **Clientes V3 (contas)** e depois salve o mapeamento.</span><span class="sxs-lookup"><span data-stu-id="43d81-199">Add the **InvoiceAccount** and **ContactPersonId** columns back to the **Customers V3 (Accounts)** mapping, and then save the mapping.</span></span> <span data-ttu-id="43d81-200">As colunas **InvoiceAccount** e **ContactPersonId** agora fazem parte do modo de sincronização ao vivo novamente.</span><span class="sxs-lookup"><span data-stu-id="43d81-200">Both the **InvoiceAccount** column and the **ContactPersonId** column are now part of live synchronization mode again.</span></span> <span data-ttu-id="43d81-201">Na próxima etapa, você executará a sincronização inicial dessas colunas.</span><span class="sxs-lookup"><span data-stu-id="43d81-201">In the next step, you will do the initial synchronization for these columns.</span></span>
6. <span data-ttu-id="43d81-202">Execute a sincronização inicial novamente para o mapeamento de **Clientes V3 (contas)**.</span><span class="sxs-lookup"><span data-stu-id="43d81-202">Run initial synchronization again for the **Customers V3 (Accounts)** mapping.</span></span> <span data-ttu-id="43d81-203">Como o controle de alterações está desabilitado, os dados de **InvoiceAccount** e **ContactPersonId** serão sincronizados do aplicativo Finance and Operations para o Dataverse.</span><span class="sxs-lookup"><span data-stu-id="43d81-203">Because change tracking is turned off, the data for **InvoiceAccount** and **ContactPersonId** will be synced from the Finance and Operations app to Dataverse.</span></span>
7. <span data-ttu-id="43d81-204">Para sincronizar os dados de **InvoiceAccount** e **ContactPersonId** do Dataverse para o Finance and Operations, você deve usar um projeto de integração de dados.</span><span class="sxs-lookup"><span data-stu-id="43d81-204">To sync the data for **InvoiceAccount** and **ContactPersonId** from Dataverse to the Finance and Operations app, you must use a data integration project.</span></span>

    1. <span data-ttu-id="43d81-205">No Power Apps, crie um projeto de integração de dados entre as tabelas **Sales.Account** e **Finance and Operations apps.Customers V3**.</span><span class="sxs-lookup"><span data-stu-id="43d81-205">In Power Apps, create a data integration project between the **Sales.Account** and **Finance and Operations apps.Customers V3** tables.</span></span> <span data-ttu-id="43d81-206">A direção de dados deve ser do Dataverse para o aplicativo do Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="43d81-206">The data direction must be from Dataverse to the Finance and Operations app.</span></span> <span data-ttu-id="43d81-207">Como **InvoiceAccount** é um novo atributo na gravação dupla, talvez você queira ignorar a sincronização inicial desse atributo.</span><span class="sxs-lookup"><span data-stu-id="43d81-207">Because **InvoiceAccount** is a new attribute in dual-write, you might want to skip initial synchronization for it.</span></span> <span data-ttu-id="43d81-208">Para obter mais informações, consulte [Integrar dados no Dataverse](https://docs.microsoft.com/power-platform/admin/data-integrator).</span><span class="sxs-lookup"><span data-stu-id="43d81-208">For more information, see [Integrate data into Dataverse](https://docs.microsoft.com/power-platform/admin/data-integrator).</span></span>

        <span data-ttu-id="43d81-209">A ilustração a seguir mostra um projeto que atualiza **CustomerAccount** e **ContactPersonId**.</span><span class="sxs-lookup"><span data-stu-id="43d81-209">The following illustration shows a project that updates **CustomerAccount** and **ContactPersonId**.</span></span>

        ![Projeto de integração de dados para atualizar CustomerAccount e ContactPersonId](media/cust_selfref6.png)

    2. <span data-ttu-id="43d81-211">Adicione os critérios da empresa no filtro do Dataverse, para que somente as linhas que correspondem aos critérios do filtro sejam atualizadas no aplicativo do Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="43d81-211">Add the company criteria in the filter on the Dataverse side, so that only rows that match the filter criteria will be updated in the Finance and Operations app.</span></span> <span data-ttu-id="43d81-212">Para adicionar um filtro, selecione o botão de filtro.</span><span class="sxs-lookup"><span data-stu-id="43d81-212">To add a filter, select the filter button.</span></span> <span data-ttu-id="43d81-213">Em seguida, na caixa de diálogo **Editar consulta**, você pode adicionar uma consulta de filtro como **\_msdyn\_company\_value eq '\<guid\>'**.</span><span class="sxs-lookup"><span data-stu-id="43d81-213">Then, in the **Edit query** dialog box, you can add a filter query such as **\_msdyn\_company\_value eq '\<guid\>'**.</span></span> 

        > <span data-ttu-id="43d81-214">[NOTA] Se o botão de filtro não estiver presente, crie um tíquete de suporte para solicitar que a equipe de integração de dados habilite a capacidade de filtro no seu locatário.</span><span class="sxs-lookup"><span data-stu-id="43d81-214">[NOTE] If the filter button isn't present, create a support ticket to ask the data integration team to enable the filter capability on your tenant.</span></span>

        <span data-ttu-id="43d81-215">Se você não inserir uma consulta de filtro para **\_msdyn\_company\_value**, todas os linhas serão sincronizados.</span><span class="sxs-lookup"><span data-stu-id="43d81-215">If you don't enter a filter query for **\_msdyn\_company\_value**, all the rows will be synced.</span></span>

        ![Adicionando uma consulta de filtro](media/cust_selfref7.png)

    <span data-ttu-id="43d81-217">A sincronização inicial das linhas está concluída.</span><span class="sxs-lookup"><span data-stu-id="43d81-217">The initial synchronization of the rows is now completed.</span></span>

8. <span data-ttu-id="43d81-218">No aplicativo do Finance and Operations, habilite o controle de alterações novamente para a tabela **Clientes V3**.</span><span class="sxs-lookup"><span data-stu-id="43d81-218">In the Finance and Operations app, turn change tracking back on for the **Customers V3** table.</span></span>


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]