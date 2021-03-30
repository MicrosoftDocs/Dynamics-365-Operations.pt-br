---
title: Criar páginas de resposta personalizadas para erros do código de status 4xx/5xx
description: Este tópico descreve como criar páginas de resposta personalizadas para erros de código de status 4xx e 5xx usando as ferramentas de criação no Microsoft Dynamics 365 Commerce.
author: v-chgri
manager: annbe
ms.date: 04/14/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: ee2f74581ded6020d075377f931c465d7c89f9e5
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5211096"
---
# <a name="build-custom-response-pages-for-4xx5xx-status-code-errors"></a><span data-ttu-id="0c72c-103">Criar páginas de resposta personalizadas para erros do código de status 4xx/5xx</span><span class="sxs-lookup"><span data-stu-id="0c72c-103">Build custom response pages for 4xx/5xx status code errors</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="0c72c-104">Este tópico descreve como criar páginas de resposta personalizadas para erros de código de status 4xx e 5xx usando as ferramentas de criação no Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="0c72c-104">This topic describes how to build custom response pages for 4xx and 5xx status code errors by using the authoring tools in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="0c72c-105">Visão Geral</span><span class="sxs-lookup"><span data-stu-id="0c72c-105">Overview</span></span>

<span data-ttu-id="0c72c-106">Se uma solicitação não tiver êxito, o servidor emite respostas de erro do código de status do HTTP.</span><span class="sxs-lookup"><span data-stu-id="0c72c-106">If a request isn't successful, the server issues HTTP status code error responses.</span></span> <span data-ttu-id="0c72c-107">O código de status 404 é capturado e retornado se uma página não for encontrada e o código de status 500 é capturado e retornado se um erro de servidor ocorrer.</span><span class="sxs-lookup"><span data-stu-id="0c72c-107">The 404 status code is captured and returned if a page isn't found, and the 500 status code is captured and returned if a server error occurs.</span></span> <span data-ttu-id="0c72c-108">No Dynamics 365 Commerce, os usuários do aplicativo podem criar as páginas de resposta de erro de código de status personalizado que são exibidas para usuários dessas respostas de erro de código de status.</span><span class="sxs-lookup"><span data-stu-id="0c72c-108">In Dynamics 365 Commerce, application users can build custom status code error response pages that are shown to users for these status code error responses.</span></span>

## <a name="build-a-status-code-error-response-page"></a><span data-ttu-id="0c72c-109">Criar uma página de resposta de erro do código de status</span><span class="sxs-lookup"><span data-stu-id="0c72c-109">Build a status code error response page</span></span>

<span data-ttu-id="0c72c-110">Para começar a criar uma página de resposta de erro do código de status, siga essas etapas.</span><span class="sxs-lookup"><span data-stu-id="0c72c-110">To start to build a status code error response page, follow these steps.</span></span>

1. <span data-ttu-id="0c72c-111">Em seu navegador preferido, conecte-se ao Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="0c72c-111">In your preferred web browser, sign in to Dynamics 365 Commerce.</span></span> 
1. <span data-ttu-id="0c72c-112">Selecione o site no qual você deseja criar uma página de resposta de erro de código do status 4xx/5xx.</span><span class="sxs-lookup"><span data-stu-id="0c72c-112">Select the site that you want to build a 4xx/5xx status code error response page for.</span></span>

### <a name="build-the-template"></a><span data-ttu-id="0c72c-113">Criar o modelo</span><span class="sxs-lookup"><span data-stu-id="0c72c-113">Build the template</span></span>

<span data-ttu-id="0c72c-114">Para criar o modelo para a página de resposta de erro do código de status, siga essas etapas.</span><span class="sxs-lookup"><span data-stu-id="0c72c-114">To build the template for the status code error response page, follow these steps.</span></span>

1. <span data-ttu-id="0c72c-115">Vá para **Modelos**.</span><span class="sxs-lookup"><span data-stu-id="0c72c-115">Go to **Templates**.</span></span>
1. <span data-ttu-id="0c72c-116">Selecione **Novo** para criar um modelo de página.</span><span class="sxs-lookup"><span data-stu-id="0c72c-116">Select **New** to create a page template.</span></span>
1. <span data-ttu-id="0c72c-117">Na caixa de diálogo **Novo Modelo**, em **Nome do Modelo**, insira um nome para o novo modelo e selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="0c72c-117">In the **New Template** dialog box, under **Template Name**, enter a name for the new template, and then select **OK**.</span></span>
1. <span data-ttu-id="0c72c-118">Crie modelo, com base na estrutura que deseja que a página de resposta de erro do código de status apareça.</span><span class="sxs-lookup"><span data-stu-id="0c72c-118">Build the template, based on the structure that you want the status code error response page to have.</span></span>
1. <span data-ttu-id="0c72c-119">Selecione **Salvar**, **Concluir edição** para fazer check-in do modelo e depois selecione **Publicar** para publicá-lo.</span><span class="sxs-lookup"><span data-stu-id="0c72c-119">Select **Save**, select **Finish editing** to check in the template, and then select **Publish** to publish it.</span></span> 

### <a name="build-the-status-code-error-response-page"></a><span data-ttu-id="0c72c-120">Crie a página de resposta de erro do código de status</span><span class="sxs-lookup"><span data-stu-id="0c72c-120">Build the status code error response page</span></span>

<span data-ttu-id="0c72c-121">Para criar a página de resposta de erro do código de status, siga essas etapas.</span><span class="sxs-lookup"><span data-stu-id="0c72c-121">To build the status code error response page, follow these steps.</span></span>

1. <span data-ttu-id="0c72c-122">Vá para **Páginas**.</span><span class="sxs-lookup"><span data-stu-id="0c72c-122">Go to **Pages**.</span></span>
1. <span data-ttu-id="0c72c-123">Selecione **Novo** para criar uma página.</span><span class="sxs-lookup"><span data-stu-id="0c72c-123">Select **New** to create a page.</span></span>
1. <span data-ttu-id="0c72c-124">Na caixa de diálogo **Escolha um modelo**, selecione um modelo e, em **Nome da página**, insira um nome para a página da resposta do erro do código de status.</span><span class="sxs-lookup"><span data-stu-id="0c72c-124">In the **Choose a template** dialog box, select a template, and then, under **Page name**, enter a name for the status code error response page.</span></span> <span data-ttu-id="0c72c-125">Deixe o campo **URL da Página** em branco.</span><span class="sxs-lookup"><span data-stu-id="0c72c-125">Leave the **Page URL** field blank.</span></span>
1. <span data-ttu-id="0c72c-126">Crie a página.</span><span class="sxs-lookup"><span data-stu-id="0c72c-126">Build the page.</span></span>
1. <span data-ttu-id="0c72c-127">Selecione **Salvar**, **Concluir edição** para fazer check-in da página e depois selecione **Publicar** para publicá-lo.</span><span class="sxs-lookup"><span data-stu-id="0c72c-127">Select **Save**, select **Finish editing** to check in the page, and then select **Publish** to publish it.</span></span>

> [!NOTE]
> <span data-ttu-id="0c72c-128">Você pode criar páginas de resposta de erro de código do status separada para erros de código do status 4xx e 5xx.</span><span class="sxs-lookup"><span data-stu-id="0c72c-128">You can create separate status code error response pages for 4xx and 5xx status code errors.</span></span> <span data-ttu-id="0c72c-129">Alternativamente, você pode usar a mesma página geral da resposta de erro do código de status para ambas as categorias de erro.</span><span class="sxs-lookup"><span data-stu-id="0c72c-129">Alternatively, you can use the same general status code error response page for both error categories.</span></span>

### <a name="set-up-a-redirect-for-the-status-code-error-response-page"></a><span data-ttu-id="0c72c-130">Configurar um redirecionamento para a página de resposta de erro do código de status</span><span class="sxs-lookup"><span data-stu-id="0c72c-130">Set up a redirect for the status code error response page</span></span>

<span data-ttu-id="0c72c-131">Para configurar um redirecionamento para a página de resposta de erro do código de status, siga essas etapas.</span><span class="sxs-lookup"><span data-stu-id="0c72c-131">To set up a redirect for the status code error response page, follow these steps.</span></span>

1. <span data-ttu-id="0c72c-132">Vá para **URLs \> Novo \> Novo alias**, e selecione a página de resposta de erro do código de status que você compilou anteriormente.</span><span class="sxs-lookup"><span data-stu-id="0c72c-132">Go to **URLs \> New \> New Alias**, and select the status code error response page that you built earlier.</span></span>
1. <span data-ttu-id="0c72c-133">No campo **Alias**, **default-4xx** ou **default-5xx**, dependendo da página de resposta de erro do código de status para a qual você está configurando o redirecionamento.</span><span class="sxs-lookup"><span data-stu-id="0c72c-133">In the **Alias** field, enter either **default-4xx** or **default-5xx**, depending on the status code error response page that you're setting up a redirect for.</span></span> <span data-ttu-id="0c72c-134">Essas alias devem ser publicados.</span><span class="sxs-lookup"><span data-stu-id="0c72c-134">These aliases must be published.</span></span> <span data-ttu-id="0c72c-135">Caso contrário, o redirecionamento não funcionará.</span><span class="sxs-lookup"><span data-stu-id="0c72c-135">Otherwise, the redirect won't work.</span></span>
1. <span data-ttu-id="0c72c-136">Selecione **OK** para enviar o link.</span><span class="sxs-lookup"><span data-stu-id="0c72c-136">Select **OK** to commit the linking.</span></span>

> [!NOTE]
> <span data-ttu-id="0c72c-137">Se estiver usando uma única página de resposta de erro do código de status para ambas as categorias de erro, repita este procedimento para vincular uma apelido da outra categoria de erro na mesma página.</span><span class="sxs-lookup"><span data-stu-id="0c72c-137">If you're using a single status code error response page for both error categories, repeat this procedure to link an alias for the other error category to the same page.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="0c72c-138">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="0c72c-138">Additional resources</span></span>

[<span data-ttu-id="0c72c-139">Trabalhar com modelos</span><span class="sxs-lookup"><span data-stu-id="0c72c-139">Work with templates</span></span>](work-with-templates.md)

[<span data-ttu-id="0c72c-140">Adicionar uma nova página do site</span><span class="sxs-lookup"><span data-stu-id="0c72c-140">Add a new site page</span></span>](add-new-page.md)

[<span data-ttu-id="0c72c-141">Criar uma URL da página</span><span class="sxs-lookup"><span data-stu-id="0c72c-141">Create a page URL</span></span>](create-page-url.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]