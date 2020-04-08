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
ms.openlocfilehash: d51b547093825a6e7730b5fdfcfb1c081776c63c
ms.sourcegitcommit: 68f1485de7d64a6c9eba1088af63bd07992d972d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2020
ms.locfileid: "3172705"
---
# <a name="troubleshoot-issues-during-initial-synchronization"></a><span data-ttu-id="c284a-103">Solucionar problemas durante a sincronização inicial</span><span class="sxs-lookup"><span data-stu-id="c284a-103">Troubleshoot issues during initial synchronization</span></span>

[!include [banner](../../includes/banner.md)]



<span data-ttu-id="c284a-104">Este tópico fornece informações de solução de problemas para integração de gravação dupla entre aplicativos do Finance and Operations e o Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="c284a-104">This topic provides troubleshooting information for dual-write integration between Finance and Operations apps and Common Data Service.</span></span> <span data-ttu-id="c284a-105">Especificamente, ele fornece informações sobre como solucionar problemas que podem ajudá-lo a corrigir problemas que podem acontecer durante a sincronização inicial.</span><span class="sxs-lookup"><span data-stu-id="c284a-105">Specifically, it provides information that can help you fix issues that might occur during initial synchronization.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="c284a-106">Alguns dos problemas que este tópico aborda podem exigir a função de administrador do sistema ou as credenciais de administrador do locatário Microsoft Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="c284a-106">Some of the issues that this topic addresses might require either the system admin role or Microsoft Azure Active Directory (Azure AD) tenant admin credentials.</span></span> <span data-ttu-id="c284a-107">A seção para cada problema explica se uma função ou credenciais específicas são necessárias.</span><span class="sxs-lookup"><span data-stu-id="c284a-107">The section for each issue explains whether a specific role or credentials are required.</span></span>

## <a name="check-for-initial-synchronization-errors-in-a-finance-and-operations-app"></a><span data-ttu-id="c284a-108">Verificar erros de sincronização inicial em um aplicativo do Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="c284a-108">Check for initial synchronization errors in a Finance and Operations app</span></span>

<span data-ttu-id="c284a-109">Depois de habilitar os modelos de mapeamento, o status dos mapas deve estar em **Execução**.</span><span class="sxs-lookup"><span data-stu-id="c284a-109">After you enable the mapping templates, the status of the maps should be **Running**.</span></span> <span data-ttu-id="c284a-110">Se o status **Não estiver em execução**, ocorrerão erros durante a sincronização inicial.</span><span class="sxs-lookup"><span data-stu-id="c284a-110">If the status is **Not running**, errors occurred during initial synchronization.</span></span> <span data-ttu-id="c284a-111">Para exibir os erros, selecione a guia **Detalhes de sincronização inicial** na página **Gravação dupla**.</span><span class="sxs-lookup"><span data-stu-id="c284a-111">To view the errors, select the **Initial sync details** tab on the **Dual-write** page.</span></span>

![Guia detalhes da sincronização inicial](media/initial_sync_status.png)

## <a name="you-cant-complete-initial-synchronization-400-bad-request"></a><span data-ttu-id="c284a-113">Não é possível concluir a sincronização inicial: 400 Solicitação incorreta</span><span class="sxs-lookup"><span data-stu-id="c284a-113">You can't complete initial synchronization: 400 Bad Request</span></span>

<span data-ttu-id="c284a-114">**Função necessária para corrigir o problema:** administrador do sistema</span><span class="sxs-lookup"><span data-stu-id="c284a-114">**Required role to fix the issue:** System admin</span></span>

<span data-ttu-id="c284a-115">A seguinte mensagem de erro pode ser exibida ao tentar executar o mapeamento e a sincronização inicial:</span><span class="sxs-lookup"><span data-stu-id="c284a-115">You might receive the following error message when you try to run the mapping and initial synchronization:</span></span>

<span data-ttu-id="c284a-116">*O servidor remoto retornou um erro: (400) Solicitação incorreta.), a exportação AX encontrou um erro*</span><span class="sxs-lookup"><span data-stu-id="c284a-116">*The remote server returned an error: (400) Bad Request.), AX export encountered an error*</span></span>

<span data-ttu-id="c284a-117">Veja aqui um exemplo da mensagem de erro completa.</span><span class="sxs-lookup"><span data-stu-id="c284a-117">Here is an example of the full error message.</span></span>

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

<span data-ttu-id="c284a-118">Se esse erro ocorrer consistentemente e você não puder concluir a sincronização inicial, siga estas etapas para corrigir o problema.</span><span class="sxs-lookup"><span data-stu-id="c284a-118">If this error occurs consistently, and you can't complete the initial synchronization, follow these steps to fix the issue.</span></span>

1. <span data-ttu-id="c284a-119">Faça login na máquina virtual (VM) para o aplicativo Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="c284a-119">Sign in to the virtual machine (VM) for the Finance and Operations app.</span></span>
2. <span data-ttu-id="c284a-120">Abra o console de gerenciamento da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c284a-120">Open Microsoft Management Console.</span></span> 
3. <span data-ttu-id="c284a-121">No painel **Serviços**, verifique se o serviço de estrutura de importação/exportação de dados do Microsoft Dynamics 365 está em execução.</span><span class="sxs-lookup"><span data-stu-id="c284a-121">In the **Services** pane, make sure that the Microsoft Dynamics 365 Data import export framework service is running.</span></span> <span data-ttu-id="c284a-122">Reinicie-o se ele tiver sido interrompido, pois a sincronização inicial requer essa ação.</span><span class="sxs-lookup"><span data-stu-id="c284a-122">Restart it if it has been stopped, because the initial synchronization requires it.</span></span>

## <a name="initial-synchronization-error-403-forbidden"></a><span data-ttu-id="c284a-123">Erro de sincronização inicial: 403 Proibido</span><span class="sxs-lookup"><span data-stu-id="c284a-123">Initial synchronization error: 403 Forbidden</span></span>

<span data-ttu-id="c284a-124">A seguinte mensagem de erro pode ser exibida durante sincronização inicial:</span><span class="sxs-lookup"><span data-stu-id="c284a-124">You might receive the following error message during initial synchronization:</span></span>

<span data-ttu-id="c284a-125">*(\[Proibido\], O servidor remoto retornou um erro: (403) Proibido.), a exportação AX encontrou um erro*</span><span class="sxs-lookup"><span data-stu-id="c284a-125">*(\[Forbidden\], The remote server returned an error: (403) Forbidden.), AX export encountered an error*</span></span>

<span data-ttu-id="c284a-126">Para corrigir o problema, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="c284a-126">To fix the issue, follow these steps.</span></span>

1. <span data-ttu-id="c284a-127">Entrar no aplicativo Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="c284a-127">Sign in to the Finance and Operations app.</span></span>
2. <span data-ttu-id="c284a-128">Na página **aplicativo do Azure Active Directory**, exclua o cliente **DtAppID** e, em seguida, adicione-o novamente.</span><span class="sxs-lookup"><span data-stu-id="c284a-128">On the **Azure Active Directory applications** page, delete the **DtAppID** client, and then add it again.</span></span>

![Lista de aplicativos do Azure AD](media/aad_applications.png)

## <a name="self-reference-failures-during-initial-synchronization"></a><span data-ttu-id="c284a-130">Falhas de autorreferência durante a sincronização inicial</span><span class="sxs-lookup"><span data-stu-id="c284a-130">Self-reference failures during initial synchronization</span></span>

<span data-ttu-id="c284a-131">Você pode receber uma mensagem de erro semelhante à seguinte, caso algum dos seus mapeamentos tenha as próprias referências:</span><span class="sxs-lookup"><span data-stu-id="c284a-131">You might receive an error message that resembles the following example if any of your mappings have self-references:</span></span>

<span data-ttu-id="c284a-132">*Nos fornecedores V2, o seguinte erro: ID de registro: novo registro, ErrorMessage: não foi possível resolver o GUID do campo: msdyn\_invoicevendoraccountnumber.msdyn\_vendoraccountnumber. O valor de pesquisa não foi encontrado: CN-001. Teste essa URL para verificar se os dados de referência existem: `https://sampleorg.crm.dynamics.com/api/data/v9.0/msdyn_vendors?$select=msdyn_vendoraccountnumber,msdyn_vendorid&$filter=msdyn_vendoraccountnumber` eq 'CN-001'*</span><span class="sxs-lookup"><span data-stu-id="c284a-132">*On the Vendors V2, the following error: Record Id: new record, ErrorMessage: Couldn't resolve the guid for the field: msdyn\_invoicevendoraccountnumber.msdyn\_vendoraccountnumber. The lookup value was not found: CN-001. Try this URL(s) to check if the reference data exists: `https://sampleorg.crm.dynamics.com/api/data/v9.0/msdyn_vendors?$select=msdyn_vendoraccountnumber,msdyn_vendorid&$filter=msdyn_vendoraccountnumber` eq 'CN-001'*</span></span>

<span data-ttu-id="c284a-133">Esse tipo de erro ocorre durante a sincronização inicial de mapeamentos que têm referências próprias.</span><span class="sxs-lookup"><span data-stu-id="c284a-133">This type of error occurs during initial synchronization of mappings that have self-references.</span></span> <span data-ttu-id="c284a-134">No exemplo anterior, a conta de nota fiscal de campo faz referência à entidade de fornecedor.</span><span class="sxs-lookup"><span data-stu-id="c284a-134">In the preceding example, the field invoice account references the vendor entity.</span></span>

<span data-ttu-id="c284a-135">Para corrigir o problema, talvez seja necessário executar o mapeamento duas vezes antes que a sincronização inicial seja bem-sucedida.</span><span class="sxs-lookup"><span data-stu-id="c284a-135">To fix the issue, you might have to run the mapping two times before the initial synchronization is successful.</span></span>

