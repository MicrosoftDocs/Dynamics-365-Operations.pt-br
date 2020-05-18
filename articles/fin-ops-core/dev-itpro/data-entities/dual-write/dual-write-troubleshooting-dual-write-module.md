---
title: Solucionar problemas com o módulo de gravação dupla em aplicativos do Finance and Operations
description: Este tópico fornece informações sobre como solucionar problemas que podem ajudá-lo a corrigir problemas no módulo de dupla gravação nos aplicativos Finance and Operations.
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
ms.openlocfilehash: 853791d5ffc1d92b9fbafa2acc13cd5543c38196
ms.sourcegitcommit: e06da171b9cba8163893e30244c52a9ce0901146
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2020
ms.locfileid: "3275524"
---
# <a name="troubleshoot-issues-with-the-dual-write-module-in-finance-and-operations-apps"></a><span data-ttu-id="a23e5-103">Solucionar problemas com o módulo de gravação dupla em aplicativos do Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="a23e5-103">Troubleshoot issues with the dual-write module in Finance and Operations apps</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="a23e5-104">Este tópico fornece informações de solução de problemas para integração de gravação dupla entre aplicativos do Finance and Operations e o Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="a23e5-104">This topic provides troubleshooting information for dual-write integration between Finance and Operations apps and Common Data Service.</span></span> <span data-ttu-id="a23e5-105">Especificamente, ele fornece informações sobre como solucionar problemas que podem ajudá-lo a corrigir problemas no módulo de **dupla gravação** nos aplicativos Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="a23e5-105">Specifically, it provides information that can help you fix issues with the **Dual-write** module in Finance and Operations apps.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a23e5-106">Alguns dos problemas que este tópico aborda podem exigir a função de administrador do sistema ou as credenciais de administrador do locatário Microsoft Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="a23e5-106">Some of the issues that this topic addresses might require either the system admin role or Microsoft Azure Active Directory (Azure AD) tenant admin credentials.</span></span> <span data-ttu-id="a23e5-107">A seção para cada problema explica se uma função ou credenciais específicas são necessárias.</span><span class="sxs-lookup"><span data-stu-id="a23e5-107">The section for each issue explains whether a specific role or credentials are required.</span></span>

## <a name="you-cant-load-the-dual-write-module-in-a-finance-and-operations-app"></a><span data-ttu-id="a23e5-108">Não é possível carregar o módulo de gravação dupla em um aplicativo do Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="a23e5-108">You can't load the dual-write module in a Finance and Operations app</span></span>

<span data-ttu-id="a23e5-109">Se você não conseguir abrir a página **Gravação dupla** selecionando o bloco **Gravação dupla** no espaço de trabalho **Gerenciamento de dados**, o serviço de integração de dados está provavelmente desligado.</span><span class="sxs-lookup"><span data-stu-id="a23e5-109">If you can't open the **Dual-write** page by selecting the **Dual Write** tile in the **Data management** workspace, the data integration service is probably down.</span></span> <span data-ttu-id="a23e5-110">Crie um tíquete de suporte para solicitar uma reinicialização do serviço de integração de dados.</span><span class="sxs-lookup"><span data-stu-id="a23e5-110">Create a support ticket to request a restart of the data integration service.</span></span>

## <a name="error-when-you-try-to-create-a-new-entity-map"></a><span data-ttu-id="a23e5-111">Erro ao tentar criar um novo mapa de entidade</span><span class="sxs-lookup"><span data-stu-id="a23e5-111">Error when you try to create a new entity map</span></span>

<span data-ttu-id="a23e5-112">**Credenciais necessárias para corrigir o problema:** o mesmo usuário que configura a gravação dupla.</span><span class="sxs-lookup"><span data-stu-id="a23e5-112">**Required credentials to fix the issue:** The same user that setup dual-write.</span></span>

<span data-ttu-id="a23e5-113">A seguinte mensagem de erro poderá ser exibida quando você tentar configurar uma nova entidade para gravação dupla:</span><span class="sxs-lookup"><span data-stu-id="a23e5-113">You might receive the following error message when you try to configure a new entity for dual-write.</span></span> <span data-ttu-id="a23e5-114">O único usuário que poderá criar um mapa é o usuário que configurou a conexão de gravação dupla.</span><span class="sxs-lookup"><span data-stu-id="a23e5-114">The only user that can create a map is the user who setup the dual-write connection.</span></span>

<span data-ttu-id="a23e5-115">*O código de status de resposta não indica êxito: 401 (Não autorizado)*</span><span class="sxs-lookup"><span data-stu-id="a23e5-115">*Response status code does not indicate success: 401 (Unauthorized)*</span></span>


## <a name="error-when-you-open-the-dual-write-user-interface"></a><span data-ttu-id="a23e5-116">Erro ao abrir a interface do usuário de gravação dupla</span><span class="sxs-lookup"><span data-stu-id="a23e5-116">Error when you open the dual-write user interface</span></span>

<span data-ttu-id="a23e5-117">A seguinte mensagem de erro pode ser exibida ao tentar acessar a gravação dupla no espaço de trabalho do **Gerenciamento de dados**:</span><span class="sxs-lookup"><span data-stu-id="a23e5-117">You might receive the following error message when you try to access dual-write from the **Data management** workspace:</span></span>

<span data-ttu-id="a23e5-118">*login.microsoftonline.com recusou a conexão.*</span><span class="sxs-lookup"><span data-stu-id="a23e5-118">*login.microsoftonline.com refused to connect.*</span></span>

<span data-ttu-id="a23e5-119">Para corrigir o problema, faça login usando uma janela InPrivate no Microsoft Edge, uma janela Incognito no Chromium ou uma janela Incognito no Google Chrome.</span><span class="sxs-lookup"><span data-stu-id="a23e5-119">To fix the issue, sign in by using an InPrivate window in Microsoft Edge, an incognito window in Chromium, or an incognito window in Google Chrome.</span></span> <span data-ttu-id="a23e5-120">Você também deve desbloquear ou limpar cookies de terceiros.</span><span class="sxs-lookup"><span data-stu-id="a23e5-120">You must also unblock or clear third-party cookies.</span></span>

## <a name="error-when-you-link-the-environment-for-dual-write-or-add-a-new-entity-mapping"></a><span data-ttu-id="a23e5-121">Erro ao vincular o ambiente para dupla gravação ou adicionar um novo mapeamento de entidade</span><span class="sxs-lookup"><span data-stu-id="a23e5-121">Error when you link the environment for dual-write or add a new entity mapping</span></span>

<span data-ttu-id="a23e5-122">**Função necessária para corrigir o problema:** administrador do sistema nos aplicativos Finance and Operations e Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="a23e5-122">**Required role to fix the issue:** System administrator in both Finance and Operations apps and Common Data Service.</span></span>

<span data-ttu-id="a23e5-123">Você pode encontrar o seguinte erro ao vincular ou criar mapas:</span><span class="sxs-lookup"><span data-stu-id="a23e5-123">You might encounter the following error when linking or creating maps:</span></span>

<span data-ttu-id="a23e5-124">*O código de status de resposta não indica sucesso: 403 (tokenexchange).<br> ID da sessão: \<seu ID da sessão\><br> ID da atividade raiz: \<seu ID de atividade raiz\>*</span><span class="sxs-lookup"><span data-stu-id="a23e5-124">*Response status code does not indicate success: 403 (tokenexchange).<br> Session ID: \<your session id\><br> Root activity ID: \<your root activity id\>*</span></span>

<span data-ttu-id="a23e5-125">Este erro poderá ocorrer se você não tiver permissões suficientes para vincular duas gravações ou criar mapas.</span><span class="sxs-lookup"><span data-stu-id="a23e5-125">This error can occur if you don't have sufficient permissions to link dual-write or create maps.</span></span> <span data-ttu-id="a23e5-126">Esse erro também pode ocorrer se o ambiente do Common Data Service foi redefinido sem desvincular a gravação dupla.</span><span class="sxs-lookup"><span data-stu-id="a23e5-126">This error can also occur if the Common Data Service environment was reset without unlinking dual-write.</span></span> <span data-ttu-id="a23e5-127">Qualquer usuário com a função de administrador do sistema nos aplicativos Finance and Operations e Common Data Service pode vincular os ambientes.</span><span class="sxs-lookup"><span data-stu-id="a23e5-127">Any user with system administrator role in both Finance and Operations apps and Common Data Service can link the environments.</span></span> <span data-ttu-id="a23e5-128">Somente o usuário que configurou a conexão de gravação dupla poderá adicionar novos mapas de entidade.</span><span class="sxs-lookup"><span data-stu-id="a23e5-128">Only the user who setup the dual-write connection can add new entity maps.</span></span> <span data-ttu-id="a23e5-129">Após a configuração, qualquer usuário com a função de administrador do sistema poderá monitorar o status e editar os mapeamentos.</span><span class="sxs-lookup"><span data-stu-id="a23e5-129">After setup, any user with system administrator role can monitor the status and edit the mappings.</span></span>

## <a name="error-when-you-stop-the-entity-mapping"></a><span data-ttu-id="a23e5-130">Erro ao interromper o mapeamento de entidade</span><span class="sxs-lookup"><span data-stu-id="a23e5-130">Error when you stop the entity mapping</span></span>

<span data-ttu-id="a23e5-131">A seguinte mensagem de erro pode ser exibida ao tentar interromper os mapeamentos de entidade:</span><span class="sxs-lookup"><span data-stu-id="a23e5-131">You might receive the following error message when you try to stop the entity mappings:</span></span>

<span data-ttu-id="a23e5-132">*\[Proibido\], \[{"status":403,"origem":"","mensagem":"Erro da troca de token: O usuário não tem acesso à conexão dynamicscrmonline/xxxxxx-xxxx-xxxx-xxxxxxxx"}\], O servidor remoto retornou um erro: (403) Proibido.*</span><span class="sxs-lookup"><span data-stu-id="a23e5-132">*\[Forbidden\], \[{"status":403,"source":"","message":"Error from token exchange: User is not allowed to access connection dynamicscrmonline/xxxxxx-xxxx-xxxx-xxxxxxxx"}\], The remote server returned an error: (403) Forbidden.*</span></span>

<span data-ttu-id="a23e5-133">Este erro ocorre quando o ambiente Common Data Service vinculado não está disponível.</span><span class="sxs-lookup"><span data-stu-id="a23e5-133">This error occurs when the linked Common Data Service environment isn't available.</span></span>

<span data-ttu-id="a23e5-134">Para corrigir o problema, crie um tíquete para a equipe de integração de dados.</span><span class="sxs-lookup"><span data-stu-id="a23e5-134">To fix the issue, create a ticket for the Data Integration team.</span></span> <span data-ttu-id="a23e5-135">Anexe o rastreamento de rede para que a equipe de integração de dados possa marcar os mapas como **Não executados** no back-end.</span><span class="sxs-lookup"><span data-stu-id="a23e5-135">Attach the network trace so that the Data Integration team can mark the maps as **Not running** in the back end.</span></span>

## <a name="error-while-trying-to-start-an-entity-mapping"></a><span data-ttu-id="a23e5-136">Erro ao tentar iniciar um mapeamento de entidade</span><span class="sxs-lookup"><span data-stu-id="a23e5-136">Error while trying to start an entity mapping</span></span>

<span data-ttu-id="a23e5-137">A seguinte mensagem de erro pode ser exibida ao tentar definir esse estado de um mapeamento como **Em execução**:</span><span class="sxs-lookup"><span data-stu-id="a23e5-137">You might receive an error like the following when you try to set that state of a mapping to **Running**:</span></span>

<span data-ttu-id="a23e5-138">*Não é possível concluir a sincronização de dados inicial. Erro: falha de gravação dupla — falha no registro do plug-in: não é possível criar metadados de pesquisa da gravação dupla. A referência do objeto do erro não está definida como uma instância de objeto.*</span><span class="sxs-lookup"><span data-stu-id="a23e5-138">*Unable to complete initial data sync. Error: dual-write failure - plugin registration failed: Unable to build dual-write lookup metadata. Error object reference not set to an instance of an object.*</span></span>

<span data-ttu-id="a23e5-139">A correção desse erro depende da causa do erro:</span><span class="sxs-lookup"><span data-stu-id="a23e5-139">The fix for this error depends on the cause of the error:</span></span>

+ <span data-ttu-id="a23e5-140">Se o mapeamento tiver mapeamentos dependentes, certifique-se de habilitar os mapeamentos dependentes deste mapeamento de entidade.</span><span class="sxs-lookup"><span data-stu-id="a23e5-140">If the mapping has dependent mappings, then make sure to enable the dependent mappings of this entity mapping.</span></span>
+ <span data-ttu-id="a23e5-141">O mapeamento pode estar ter campos de origem ou de destino ausentes.</span><span class="sxs-lookup"><span data-stu-id="a23e5-141">The mapping might be missing source or destination fields.</span></span> <span data-ttu-id="a23e5-142">Se um campo no aplicativo Finance and Operations estiver ausente, siga as etapas na seção [Problemas de campos de entidade ausentes nos mapas](dual-write-troubleshooting-finops-upgrades.md#missing-entity-fields-issue-on-maps).</span><span class="sxs-lookup"><span data-stu-id="a23e5-142">If a field in the Finance and Operations app is missing, then follow the steps in the section [Missing entity fields issue on maps](dual-write-troubleshooting-finops-upgrades.md#missing-entity-fields-issue-on-maps).</span></span> <span data-ttu-id="a23e5-143">Se um campo no Common Data Service estiver ausente, clique no botão **Atualizar entidades** no mapeamento para que os campos sejam automaticamente preenchidos no mapeamento.</span><span class="sxs-lookup"><span data-stu-id="a23e5-143">If a field in Common Data Service is missing, then click **Refresh entities** button on the mapping so that the fields are automatically populated back into the mapping.</span></span>