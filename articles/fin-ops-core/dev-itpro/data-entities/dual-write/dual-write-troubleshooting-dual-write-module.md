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
ms.openlocfilehash: 34c10e38400a72a670a93f2a72d0aa7a4aed561a
ms.sourcegitcommit: 68f1485de7d64a6c9eba1088af63bd07992d972d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2020
ms.locfileid: "3172751"
---
# <a name="troubleshoot-issues-with-the-dual-write-module-in-finance-and-operations-apps"></a><span data-ttu-id="d8f47-103">Solucionar problemas com o módulo de gravação dupla em aplicativos do Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="d8f47-103">Troubleshoot issues with the Dual-write module in Finance and Operations apps</span></span>

[!include [banner](../../includes/banner.md)]



<span data-ttu-id="d8f47-104">Este tópico fornece informações de solução de problemas para integração de gravação dupla entre aplicativos do Finance and Operations e o Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="d8f47-104">This topic provides troubleshooting information for dual-write integration between Finance and Operations apps and Common Data Service.</span></span> <span data-ttu-id="d8f47-105">Especificamente, ele fornece informações sobre como solucionar problemas que podem ajudá-lo a corrigir problemas no módulo de **dupla gravação** nos aplicativos Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="d8f47-105">Specifically, it provides information that can help you fix issues with the **Dual-write** module in Finance and Operations apps.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d8f47-106">Alguns dos problemas que este tópico aborda podem exigir a função de administrador do sistema ou as credenciais de administrador do locatário Microsoft Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="d8f47-106">Some of the issues that this topic addresses might require either the system admin role or Microsoft Azure Active Directory (Azure AD) tenant admin credentials.</span></span> <span data-ttu-id="d8f47-107">A seção para cada problema explica se uma função ou credenciais específicas são necessárias.</span><span class="sxs-lookup"><span data-stu-id="d8f47-107">The section for each issue explains whether a specific role or credentials are required.</span></span>

## <a name="you-cant-load-the-dual-write-module-in-a-finance-and-operations-app"></a><span data-ttu-id="d8f47-108">Não é possível carregar o módulo de gravação dupla em um aplicativo do Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="d8f47-108">You can't load the Dual-write module in a Finance and Operations app</span></span>

<span data-ttu-id="d8f47-109">Se você não conseguir abrir a página **Gravação dupla** selecionando o bloco **Gravação dupla** no espaço de trabalho **Gerenciamento de dados**, o serviço de integração de dados está provavelmente desligado.</span><span class="sxs-lookup"><span data-stu-id="d8f47-109">If you can't open the **Dual-write** page by selecting the **Dual Write** tile in the **Data management** workspace, the data integration service is probably down.</span></span> <span data-ttu-id="d8f47-110">Crie um tíquete de suporte para solicitar uma reinicialização do serviço de integração de dados.</span><span class="sxs-lookup"><span data-stu-id="d8f47-110">Create a support ticket to request a restart of the data integration service.</span></span>

## <a name="error-when-you-try-to-create-a-new-entity-mapping"></a><span data-ttu-id="d8f47-111">Erro ao tentar criar um novo mapeamento de entidade</span><span class="sxs-lookup"><span data-stu-id="d8f47-111">Error when you try to create a new entity mapping</span></span>

<span data-ttu-id="d8f47-112">**Credenciais necessárias para corrigir o problema:** administrador de locatário do Azure AD</span><span class="sxs-lookup"><span data-stu-id="d8f47-112">**Required credentials to fix the issue:** Azure AD tenant admin</span></span>

<span data-ttu-id="d8f47-113">A seguinte mensagem de erro pode ser exibida ao tentar configurar uma nova entidade para gravação dupla:</span><span class="sxs-lookup"><span data-stu-id="d8f47-113">You might receive the following error message when you try to configure a new entity for dual-write:</span></span>

<span data-ttu-id="d8f47-114">*O código de status de resposta não indica êxito: 401 (Não autorizado)*</span><span class="sxs-lookup"><span data-stu-id="d8f47-114">*Response status code does not indicate success: 401 (Unauthorized)*</span></span>

<span data-ttu-id="d8f47-115">Este erro ocorre porque somente um administrador de locatário do Azure AD pode adicionar um novo mapeamento de entidade.</span><span class="sxs-lookup"><span data-stu-id="d8f47-115">This error occurs because only an Azure AD tenant admin can add a new entity mapping.</span></span>

<span data-ttu-id="d8f47-116">Para corrigir o problema, faça login no aplicativo Finance and Operations como um locatário de administração do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="d8f47-116">To fix the issue, sign in to the Finance and Operations app as an Azure AD admin tenant.</span></span> <span data-ttu-id="d8f47-117">Você também deve ir para a web.PowerApps.com e revalidar a conexão.</span><span class="sxs-lookup"><span data-stu-id="d8f47-117">You must also go to web.PowerApps.com and revalidate your connection.</span></span>

## <a name="error-when-you-open-the-dual-write-user-interface"></a><span data-ttu-id="d8f47-118">Erro ao abrir a interface do usuário de gravação dupla</span><span class="sxs-lookup"><span data-stu-id="d8f47-118">Error when you open the dual-write user interface</span></span>

<span data-ttu-id="d8f47-119">A seguinte mensagem de erro pode ser exibida ao tentar acessar a gravação dupla no espaço de trabalho do **Gerenciamento de dados**:</span><span class="sxs-lookup"><span data-stu-id="d8f47-119">You might receive the following error message when you try to access dual-write from the **Data management** workspace:</span></span>

<span data-ttu-id="d8f47-120">*login.microsoftonline.com recusou a conexão.*</span><span class="sxs-lookup"><span data-stu-id="d8f47-120">*login.microsoftonline.com refused to connect.*</span></span>

<span data-ttu-id="d8f47-121">Para corrigir o problema, faça login usando uma janela InPrivate no Microsoft Edge, uma janela Incognito no Chromium ou uma janela Incognito no Google Chrome.</span><span class="sxs-lookup"><span data-stu-id="d8f47-121">To fix the issue, sign in by using an InPrivate window in Microsoft Edge, an incognito window in Chromium, or an incognito window in Google Chrome.</span></span> <span data-ttu-id="d8f47-122">Você também deve desbloquear ou limpar cookies de terceiros.</span><span class="sxs-lookup"><span data-stu-id="d8f47-122">You must also unblock or clear third-party cookies.</span></span>

## <a name="error-when-you-link-the-environment-for-dual-write-or-add-a-new-entity-mapping"></a><span data-ttu-id="d8f47-123">Erro ao vincular o ambiente para dupla gravação ou adicionar um novo mapeamento de entidade</span><span class="sxs-lookup"><span data-stu-id="d8f47-123">Error when you link the environment for dual-write or add a new entity mapping</span></span>

<span data-ttu-id="d8f47-124">**Credenciais necessárias para corrigir o problema:** administrador de locatário do Azure AD</span><span class="sxs-lookup"><span data-stu-id="d8f47-124">**Required credentials to fix the issue:** Azure AD tenant admin</span></span>

<span data-ttu-id="d8f47-125">Você pode encontrar o seguinte erro ao vincular ou criar mapas:</span><span class="sxs-lookup"><span data-stu-id="d8f47-125">You might encounter the following error when linking or creating maps:</span></span>

<span data-ttu-id="d8f47-126">*O código de status de resposta não indica sucesso: 403 (tokenexchange).<br> ID da sessão: \<seu ID da sessão\><br> ID da atividade raiz: \<seu ID de atividade raiz\>*</span><span class="sxs-lookup"><span data-stu-id="d8f47-126">*Response status code does not indicate success: 403 (tokenexchange).<br> Session ID: \<your session id\><br> Root activity ID: \<your root activity id\>*</span></span>

<span data-ttu-id="d8f47-127">Este erro poderá ocorrer se você não tiver permissões suficientes para vincular duas gravações ou criar mapas.</span><span class="sxs-lookup"><span data-stu-id="d8f47-127">This error can occur if you don't have sufficient permissions to link dual-write or create maps.</span></span> <span data-ttu-id="d8f47-128">Você deve usar uma conta de administrador de locatário do Azure AD para vincular ambientes e adicionar novos mapeamentos de entidade.</span><span class="sxs-lookup"><span data-stu-id="d8f47-128">You must use an Azure AD tenant admin account to link environments and add new entity mappings.</span></span> <span data-ttu-id="d8f47-129">No entanto, após a configuração, você pode usar uma conta de não-administrador para monitorar o status e editar os mapeamentos.</span><span class="sxs-lookup"><span data-stu-id="d8f47-129">However, after setup, you can use a non-admin account to monitor status and edit the mappings.</span></span>

## <a name="error-when-you-stop-the-entity-mapping"></a><span data-ttu-id="d8f47-130">Erro ao interromper o mapeamento de entidade</span><span class="sxs-lookup"><span data-stu-id="d8f47-130">Error when you stop the entity mapping</span></span>

<span data-ttu-id="d8f47-131">A seguinte mensagem de erro pode ser exibida ao tentar interromper os mapeamentos de entidade:</span><span class="sxs-lookup"><span data-stu-id="d8f47-131">You might receive the following error message when you try to stop the entity mappings:</span></span>

<span data-ttu-id="d8f47-132">*\[Proibido\], \[{"status":403,"origem":"","mensagem":"Erro da troca de token: O usuário não tem acesso à conexão dynamicscrmonline/xxxxxx-xxxx-xxxx-xxxxxxxx"}\], O servidor remoto retornou um erro: (403) Proibido.*</span><span class="sxs-lookup"><span data-stu-id="d8f47-132">*\[Forbidden\], \[{"status":403,"source":"","message":"Error from token exchange: User is not allowed to access connection dynamicscrmonline/xxxxxx-xxxx-xxxx-xxxxxxxx"}\], The remote server returned an error: (403) Forbidden.*</span></span>

<span data-ttu-id="d8f47-133">Este erro ocorre quando o ambiente Common Data Service vinculado não está disponível.</span><span class="sxs-lookup"><span data-stu-id="d8f47-133">This error occurs when the linked Common Data Service environment isn't available.</span></span>

<span data-ttu-id="d8f47-134">Para corrigir o problema, crie um tíquete para a equipe de integração de dados.</span><span class="sxs-lookup"><span data-stu-id="d8f47-134">To fix the issue, create a ticket for the Data Integration team.</span></span> <span data-ttu-id="d8f47-135">Anexe o rastreamento de rede para que a equipe de integração de dados possa marcar os mapas como **Não executados** no back-end.</span><span class="sxs-lookup"><span data-stu-id="d8f47-135">Attach the network trace so that the Data Integration team can mark the maps as **Not running** in the back end.</span></span>
