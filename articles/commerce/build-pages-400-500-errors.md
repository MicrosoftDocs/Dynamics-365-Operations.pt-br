---
title: Criar páginas de resposta personalizadas para erros do código de status 4xx/5xx
description: Este tópico descreve como criar páginas de resposta personalizada para erros de código de status 4xx e 5xx usando as ferramentas de criação no Microsoft Dynamics 365 Commerce.
author: v-chgri
manager: annbe
ms.date: 10/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: josaw
ms.search.scope: Operations, Retail, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: bcceeb1bc68c6432442c863ca06b7ba81d0abed8
ms.sourcegitcommit: 295d940a345879b3dfc5991e387b91c7257019ea
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/01/2019
ms.locfileid: "2697097"
---
# <a name="build-custom-response-pages-for-4xx5xx-status-code-errors"></a><span data-ttu-id="e95dc-103">Criar páginas de resposta personalizadas para erros do código de status 4xx/5xx</span><span class="sxs-lookup"><span data-stu-id="e95dc-103">Build custom response pages for 4xx/5xx status code errors</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="e95dc-104">Este tópico descreve como criar páginas de resposta personalizada para erros de código de status 4xx e 5xx usando as ferramentas de criação no Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="e95dc-104">This topic describes how to build custom response pages for 4xx and 5xx status code errors by using the authoring tools in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="e95dc-105">Visão geral</span><span class="sxs-lookup"><span data-stu-id="e95dc-105">Overview</span></span>

<span data-ttu-id="e95dc-106">Se uma solicitação não tiver êxito, o servidor emite respostas de erro do código de status do HTTP.</span><span class="sxs-lookup"><span data-stu-id="e95dc-106">If a request isn't successful, the server issues HTTP status code error responses.</span></span> <span data-ttu-id="e95dc-107">O código de status 404 é capturado e retornado se uma página não for encontrada e o código de status 500 é capturado e retornado se um erro de servidor ocorrer.</span><span class="sxs-lookup"><span data-stu-id="e95dc-107">The 404 status code is captured and returned if a page isn't found, and the 500 status code is captured and returned if a server error occurs.</span></span> <span data-ttu-id="e95dc-108">No Dynamics 365 Commerce, os usuários do aplicativo podem criar as páginas de resposta de erro de código de status personalizado que são exibidas para usuários dessas respostas de erro de código de status.</span><span class="sxs-lookup"><span data-stu-id="e95dc-108">In Dynamics 365 Commerce, application users can build custom status code error response pages that are shown to users for these status code error responses.</span></span>

## <a name="build-a-status-code-error-response-page"></a><span data-ttu-id="e95dc-109">Criar uma página de resposta de erro do código de status</span><span class="sxs-lookup"><span data-stu-id="e95dc-109">Build a status code error response page</span></span>

<span data-ttu-id="e95dc-110">Para começar a criar uma página de resposta de erro do código de status, siga essas etapas.</span><span class="sxs-lookup"><span data-stu-id="e95dc-110">To start to build a status code error response page, follow these steps.</span></span>

1. <span data-ttu-id="e95dc-111">Em seu navegador preferido, conecte-se ao Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="e95dc-111">In your preferred web browser, sign in to Dynamics 365 Commerce.</span></span> 
1. <span data-ttu-id="e95dc-112">Selecione o site no qual você deseja criar uma página de resposta de erro de código do status 4xx/5xx.</span><span class="sxs-lookup"><span data-stu-id="e95dc-112">Select the site that you want to build a 4xx/5xx status code error response page for.</span></span>

### <a name="build-the-template"></a><span data-ttu-id="e95dc-113">Criar o modelo</span><span class="sxs-lookup"><span data-stu-id="e95dc-113">Build the template</span></span>

<span data-ttu-id="e95dc-114">Para criar o modelo para a página de resposta de erro do código de status, siga essas etapas.</span><span class="sxs-lookup"><span data-stu-id="e95dc-114">To build the template for the status code error response page, follow these steps.</span></span>

1. <span data-ttu-id="e95dc-115">Vá para **Modelos \> Novo modelo**.</span><span class="sxs-lookup"><span data-stu-id="e95dc-115">Go to **Templates \> New template**.</span></span>
1. <span data-ttu-id="e95dc-116">Nomeie o novo modelo.</span><span class="sxs-lookup"><span data-stu-id="e95dc-116">Name the new template.</span></span>
1. <span data-ttu-id="e95dc-117">Crie modelo, com base na estrutura que deseja que a página de resposta de erro do código de status apareça.</span><span class="sxs-lookup"><span data-stu-id="e95dc-117">Build the template, based on the structure that you want the status code error response page to have.</span></span>
1. <span data-ttu-id="e95dc-118">Faça check-in do modelo e publique-o.</span><span class="sxs-lookup"><span data-stu-id="e95dc-118">Check the template in, and publish it.</span></span>

### <a name="build-the-status-code-error-response-page"></a><span data-ttu-id="e95dc-119">Crie a página de resposta de erro do código de status</span><span class="sxs-lookup"><span data-stu-id="e95dc-119">Build the status code error response page</span></span>

<span data-ttu-id="e95dc-120">Para criar a página de resposta de erro do código de status, siga essas etapas.</span><span class="sxs-lookup"><span data-stu-id="e95dc-120">To build the status code error response page, follow these steps.</span></span>

1. <span data-ttu-id="e95dc-121">Vá para **Páginas \> Nova página**.</span><span class="sxs-lookup"><span data-stu-id="e95dc-121">Go to **Pages \> New Page**.</span></span>
1. <span data-ttu-id="e95dc-122">Nomeie a página de resposta de erro do código de status, mas **não** defina o campo **URL**.</span><span class="sxs-lookup"><span data-stu-id="e95dc-122">Name the status code error response page, but do **not** set the **URL** field.</span></span>
1. <span data-ttu-id="e95dc-123">Crie a página.</span><span class="sxs-lookup"><span data-stu-id="e95dc-123">Build the page.</span></span>
1. <span data-ttu-id="e95dc-124">Faça check-in da página e publique-a.</span><span class="sxs-lookup"><span data-stu-id="e95dc-124">Check the page in, and publish it.</span></span>

> [!NOTE]
> <span data-ttu-id="e95dc-125">Você pode criar páginas de resposta de erro de código do status separada para erros de código do status 4xx e 5xx.</span><span class="sxs-lookup"><span data-stu-id="e95dc-125">You can create separate status code error response pages for 4xx and 5xx status code errors.</span></span> <span data-ttu-id="e95dc-126">Alternativamente, você pode usar a mesma página geral da resposta de erro do código de status para ambas as categorias de erro.</span><span class="sxs-lookup"><span data-stu-id="e95dc-126">Alternatively, you can use the same general status code error response page for both error categories.</span></span>

### <a name="set-up-a-redirect-for-the-status-code-error-response-page"></a><span data-ttu-id="e95dc-127">Configurar um redirecionamento para a página de resposta de erro do código de status</span><span class="sxs-lookup"><span data-stu-id="e95dc-127">Set up a redirect for the status code error response page</span></span>

<span data-ttu-id="e95dc-128">Para configurar um redirecionamento para a página de resposta de erro do código de status, siga essas etapas.</span><span class="sxs-lookup"><span data-stu-id="e95dc-128">To set up a redirect for the status code error response page, follow these steps.</span></span>

1. <span data-ttu-id="e95dc-129">Vá para **URLs \> Novo \> Novo alias**, e selecione a página de resposta de erro do código de status que você compilou anteriormente.</span><span class="sxs-lookup"><span data-stu-id="e95dc-129">Go to **URLs \> New \> New Alias**, and select the status code error response page that you built earlier.</span></span>
1. <span data-ttu-id="e95dc-130">No campo **Alias**, **default-4xx** ou **default-5xx**, dependendo da página de resposta de erro do código de status para a qual você está configurando o redirecionamento.</span><span class="sxs-lookup"><span data-stu-id="e95dc-130">In the **Alias** field, enter either **default-4xx** or **default-5xx**, depending on the status code error response page that you're setting up a redirect for.</span></span> <span data-ttu-id="e95dc-131">Essas alias devem ser publicados.</span><span class="sxs-lookup"><span data-stu-id="e95dc-131">These aliases must be published.</span></span> <span data-ttu-id="e95dc-132">Caso contrário, o redirecionamento não funcionará.</span><span class="sxs-lookup"><span data-stu-id="e95dc-132">Otherwise, the redirect won't work.</span></span>
1. <span data-ttu-id="e95dc-133">Selecione **OK** para enviar o link.</span><span class="sxs-lookup"><span data-stu-id="e95dc-133">Select **OK** to commit the linking.</span></span>

> [!NOTE]
> <span data-ttu-id="e95dc-134">Se estiver usando uma única página de resposta de erro do código de status para ambas as categorias de erro, repita este procedimento para vincular uma apelido da outra categoria de erro na mesma página.</span><span class="sxs-lookup"><span data-stu-id="e95dc-134">If you're using a single status code error response page for both error categories, repeat this procedure to link an alias for the other error category to the same page.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="e95dc-135">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="e95dc-135">Additional resources</span></span>

[<span data-ttu-id="e95dc-136">Trabalhar com modelos</span><span class="sxs-lookup"><span data-stu-id="e95dc-136">Work with templates</span></span>](work-with-templates.md)

[<span data-ttu-id="e95dc-137">Adicionar uma nova página do site</span><span class="sxs-lookup"><span data-stu-id="e95dc-137">Add a new site page</span></span>](add-new-page.md)

[<span data-ttu-id="e95dc-138">Criar uma URL da página</span><span class="sxs-lookup"><span data-stu-id="e95dc-138">Create a page URL</span></span>](create-page-url.md)
