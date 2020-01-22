---
title: Salvar, visualizar, e publicar uma página
description: Este tópico descreve como salvar, visualizar e publicar uma página no Microsoft Dynamics 365 Commerce.
author: psimolin
manager: annbe
ms.date: 10/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 3fff8299ecc6833890b14fa421501236830b2c61
ms.sourcegitcommit: ef3a1d7527311d00b69a1072ae5eb021ce68034c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/09/2020
ms.locfileid: "2945665"
---
# <a name="save-preview-and-publish-a-page"></a><span data-ttu-id="ed118-103">Salvar, visualizar, e publicar uma página</span><span class="sxs-lookup"><span data-stu-id="ed118-103">Save, preview, and publish a page</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="ed118-104">Este tópico descreve como salvar, visualizar e publicar uma página no Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="ed118-104">This topic describes how to save, preview, and publish a page in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="save-a-page"></a><span data-ttu-id="ed118-105">Salvar uma página</span><span class="sxs-lookup"><span data-stu-id="ed118-105">Save a page</span></span>

<span data-ttu-id="ed118-106">Para salvar uma página, você deve fazer check-out e abri-la no editor de páginas.</span><span class="sxs-lookup"><span data-stu-id="ed118-106">To save a page, you must have it checked out to yourself and open in the page editor.</span></span> <span data-ttu-id="ed118-107">Você deve salvar uma página imediatamente após modificá-la, para ajudar a garantir que suas alterações serão armazenadas.</span><span class="sxs-lookup"><span data-stu-id="ed118-107">You should save a page immediately after you modify it, to help guarantee that your changes are stored.</span></span>

<span data-ttu-id="ed118-108">Ao salvar uma página, as alterações ficarão visível apenas para você.</span><span class="sxs-lookup"><span data-stu-id="ed118-108">When you save a page, the changes are visible only to you.</span></span> <span data-ttu-id="ed118-109">A operação de salvar destina-se principalmente a armazenar alterações enquanto a página ainda não está pronta para o check-in.</span><span class="sxs-lookup"><span data-stu-id="ed118-109">The save operation is intended primarily to store changes while the page isn't yet ready to be checked in.</span></span> <span data-ttu-id="ed118-110">Quando você terminar de modificar a página, recomendamos que faça o check-in, para que as alterações fiquem visíveis para outras pessoas.</span><span class="sxs-lookup"><span data-stu-id="ed118-110">When you've finished modifying the page, we recommend that you check it in, so that the changes become visible to others.</span></span> <span data-ttu-id="ed118-111">Nesse ponto, também pode ser feito check-out da página por outros usuários que precisam modificá-la.</span><span class="sxs-lookup"><span data-stu-id="ed118-111">At that point, the page can also be checked out by other users who must modify it.</span></span>

## <a name="preview-a-page"></a><span data-ttu-id="ed118-112">Visualizar uma página</span><span class="sxs-lookup"><span data-stu-id="ed118-112">Preview a page</span></span>

<span data-ttu-id="ed118-113">A ferramenta de criação oferece dois tipos de recursos de visualização: um painel de visualização "você vê como vai aparecer" (WYSIWYG) no editor de páginas e uma janela de visualização separada.</span><span class="sxs-lookup"><span data-stu-id="ed118-113">The authoring tool offers two kinds of preview features: a "what you see is what you get" (WYSIWYG) preview pane in the page editor and a separate preview window.</span></span>

<span data-ttu-id="ed118-114">Ao usar o editor de páginas, uma visualização "você vê como vai aparecer" (WYSIWYG) aparece no painel central.</span><span class="sxs-lookup"><span data-stu-id="ed118-114">While you're using the page editor, a "what you see is what you get" (WYSIWYG) preview appears in the center pane.</span></span> <span data-ttu-id="ed118-115">Essa visualização é automaticamente atualizada sempre que você salvar a página.</span><span class="sxs-lookup"><span data-stu-id="ed118-115">This preview is automatically updated whenever you save the page.</span></span> <span data-ttu-id="ed118-116">Você também pode atualizá-la manualmente, selecionando **Atualizar** na barra de comandos.</span><span class="sxs-lookup"><span data-stu-id="ed118-116">You can also manually update it by selecting **Refresh** on the command bar.</span></span> <span data-ttu-id="ed118-117">A visualização WYSIWYG renderiza a página exatamente como os usuários do site a verão, mas os auxiliares de criação são renderizados em cima dela.</span><span class="sxs-lookup"><span data-stu-id="ed118-117">The WYSIWYG preview renders the page just as the site's users will see it, but authoring helpers are rendered on top of it.</span></span>

<span data-ttu-id="ed118-118">Quando você terminar de modificar a página, convém visualizá-la para ver o que os clientes verão.</span><span class="sxs-lookup"><span data-stu-id="ed118-118">When you've finished modifying the page, you might want to preview it to see what customers will see.</span></span> <span data-ttu-id="ed118-119">Para visualizar uma página, selecione **Visualizar** na barra de comandos.</span><span class="sxs-lookup"><span data-stu-id="ed118-119">To preview a page, select **Preview** on the command bar.</span></span> <span data-ttu-id="ed118-120">A visualização aparecerá em uma janela separada do navegador.</span><span class="sxs-lookup"><span data-stu-id="ed118-120">The preview will appear in a separate browser window.</span></span> <span data-ttu-id="ed118-121">A página na janela de visualização é renderizada exatamente como o usuário do site a vê.</span><span class="sxs-lookup"><span data-stu-id="ed118-121">The page in the preview window is rendered just as the site's user will see it.</span></span> <span data-ttu-id="ed118-122">Você pode redimensionar a janela para garantir que os módulos responsivos sejam renderizados corretamente em todas as portas de exibição.</span><span class="sxs-lookup"><span data-stu-id="ed118-122">You can resize the window to make sure that responsive modules are correctly rendered in all view ports.</span></span>

> [!NOTE]
> <span data-ttu-id="ed118-123">É necessária autenticação e permissões corretas para visualizar o conteúdo não publicado.</span><span class="sxs-lookup"><span data-stu-id="ed118-123">Authentication and correct permissions are required to preview unpublished content.</span></span> <span data-ttu-id="ed118-124">Portanto, se você compartilhar a URL da visualização com alguém, essa pessoa deverá ter as permissões corretas para acessar o conteúdo.</span><span class="sxs-lookup"><span data-stu-id="ed118-124">Therefore, if you share the URL of the preview with someone, that person must have the correct permissions to access the content.</span></span>

## <a name="publish-a-page"></a><span data-ttu-id="ed118-125">Publicar uma página</span><span class="sxs-lookup"><span data-stu-id="ed118-125">Publish a page</span></span>

<span data-ttu-id="ed118-126">Quando sua página estiver pronta, a próxima etapa será publicá-la, para que usuários externos possam visualizar o conteúdo.</span><span class="sxs-lookup"><span data-stu-id="ed118-126">When your page is ready, the next step is to publish it, so that external users can view the content.</span></span> <span data-ttu-id="ed118-127">Antes de poder publicar uma página, você deve fazer check-in dela.</span><span class="sxs-lookup"><span data-stu-id="ed118-127">Before you can publish a page, you must check it in.</span></span>

<span data-ttu-id="ed118-128">Você pode publicar e cancelar a publicação de páginas do inspetor ou do editor de páginas.</span><span class="sxs-lookup"><span data-stu-id="ed118-128">You can publish and unpublish pages from either the page inspector or the page editor.</span></span> <span data-ttu-id="ed118-129">O inspetor de páginas mostra uma lista de páginas e permite operações em massa.</span><span class="sxs-lookup"><span data-stu-id="ed118-129">The page inspector shows a list of pages and allows for bulk operations.</span></span> <span data-ttu-id="ed118-130">O editor de páginas pode ser usado para publicar ou cancelar a publicação apenas da única página aberta nela.</span><span class="sxs-lookup"><span data-stu-id="ed118-130">The page editor can be used to publish or unpublish only the single page that is open in it.</span></span>

<span data-ttu-id="ed118-131">Para publicar uma ou mais páginas do inspetor de páginas, selecione as páginas, verifique se elas foram submetidas a check-in e, em seguida, selecione **Publicar** na barra de comandos.</span><span class="sxs-lookup"><span data-stu-id="ed118-131">To publish one or more pages from the page inspector, select the pages, make sure that they are checked in, and then select **Publish** on the command bar.</span></span> <span data-ttu-id="ed118-132">As páginas serão publicadas e você receberá uma notificação sobre a operação na ferramenta de criação.</span><span class="sxs-lookup"><span data-stu-id="ed118-132">The pages are published, and you receive a notification about the operation in the authoring tool.</span></span>

<span data-ttu-id="ed118-133">Para publicar uma única página no editor de páginas, o procedimento é semelhante.</span><span class="sxs-lookup"><span data-stu-id="ed118-133">To publish a single page from the page editor, the procedure is similar.</span></span> <span data-ttu-id="ed118-134">Enquanto a página estiver aberta no editor de páginas, verifique se ela foi submetida a check-in e, em seguida, selecione **Publicar** na barra de comandos.</span><span class="sxs-lookup"><span data-stu-id="ed118-134">While the page is open in the page editor, make sure that it has been checked in, and then select **Publish** on the command bar.</span></span> <span data-ttu-id="ed118-135">A página será publicada e você receberá uma notificação sobre a operação.</span><span class="sxs-lookup"><span data-stu-id="ed118-135">The page is published, and you receive a notification about the operation.</span></span>

<span data-ttu-id="ed118-136">Quando você publica uma página, apenas o conteúdo da página é publicado.</span><span class="sxs-lookup"><span data-stu-id="ed118-136">When you publish a page, just the page content is published.</span></span> <span data-ttu-id="ed118-137">Você e outros usuários podem acessar a página e visualizá-la somente depois que uma URL estiver associada a ela.</span><span class="sxs-lookup"><span data-stu-id="ed118-137">You and other users can go to the page and view it only after a URL is associated with it.</span></span> <span data-ttu-id="ed118-138">A URL deverá ser publicada separadamente.</span><span class="sxs-lookup"><span data-stu-id="ed118-138">The URL must be published separately.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ed118-139">Antes de poder publicar uma página, todas as imagens ou fragmentos mencionados pela página já devem ser publicados.</span><span class="sxs-lookup"><span data-stu-id="ed118-139">Before you can publish a page, any images or fragments that the page references must already be published.</span></span>

## <a name="save-preview-and-publish-a-home-page"></a><span data-ttu-id="ed118-140">Salvar, visualizar e publicar uma home page</span><span class="sxs-lookup"><span data-stu-id="ed118-140">Save, preview, and publish a home page</span></span>

<span data-ttu-id="ed118-141">Para salvar, visualizar e publicar uma home page, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="ed118-141">To save, preview, and publish a home page, follow these steps.</span></span>

1. <span data-ttu-id="ed118-142">Em **Sites**, selecione **Fabrikam** (ou o nome do seu site).</span><span class="sxs-lookup"><span data-stu-id="ed118-142">Under **Sites**, select **Fabrikam** (or the name of your site).</span></span>
1. <span data-ttu-id="ed118-143">No painel de navegação à esquerda, selecione **Páginas**.</span><span class="sxs-lookup"><span data-stu-id="ed118-143">In the navigation pane on the left, select **Pages**.</span></span>
1. <span data-ttu-id="ed118-144">Localize e selecione a home page para abri-la no editor de páginas.</span><span class="sxs-lookup"><span data-stu-id="ed118-144">Find and select the home page to open it in the page editor.</span></span>
1. <span data-ttu-id="ed118-145">Selecione **Fazer Check-Out**.</span><span class="sxs-lookup"><span data-stu-id="ed118-145">Select **Check Out**.</span></span>
1. <span data-ttu-id="ed118-146">Modifique a página, como necessário.</span><span class="sxs-lookup"><span data-stu-id="ed118-146">Modify the page as you require.</span></span>
1. <span data-ttu-id="ed118-147">Selecione **Salvar** e **Fazer Check-in**.</span><span class="sxs-lookup"><span data-stu-id="ed118-147">Select **Save**, and then select **Check In**.</span></span>
1. <span data-ttu-id="ed118-148">No campo **Comentários** , insira uma observação sobre as alterações feitas e selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="ed118-148">In the **Comments** field, enter a note about the changes that you made, and then select **OK**.</span></span>
1. <span data-ttu-id="ed118-149">Selecione **Visualizar** para exibir a página.</span><span class="sxs-lookup"><span data-stu-id="ed118-149">Select **Preview** to preview your page.</span></span> <span data-ttu-id="ed118-150">Quando terminar, feche a guia de visualização para retornar à ferramenta de criação.</span><span class="sxs-lookup"><span data-stu-id="ed118-150">When you've finished, close the preview tab to return to the authoring tool.</span></span>
1. <span data-ttu-id="ed118-151">Selecione **Publicar**.</span><span class="sxs-lookup"><span data-stu-id="ed118-151">Select **Publish**.</span></span>

## <a name="publish-a-url"></a><span data-ttu-id="ed118-152">Publicar uma URL</span><span class="sxs-lookup"><span data-stu-id="ed118-152">Publish a URL</span></span>

<span data-ttu-id="ed118-153">Para publicar uma URL, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="ed118-153">To publish a URL, follow these steps.</span></span>

1. <span data-ttu-id="ed118-154">Em **Sites**, selecione **Fabrikam** (ou o nome do seu site).</span><span class="sxs-lookup"><span data-stu-id="ed118-154">Under **Sites**, select **Fabrikam** (or the name of your site).</span></span>
1. <span data-ttu-id="ed118-155">No painel de navegação à esquerda, selecione **URLs**.</span><span class="sxs-lookup"><span data-stu-id="ed118-155">In the navigation pane on the left, select **URLs**.</span></span>
1. <span data-ttu-id="ed118-156">Encontre e selecione a URL para publicar.</span><span class="sxs-lookup"><span data-stu-id="ed118-156">Find and select the URL to publish.</span></span>
1. <span data-ttu-id="ed118-157">Na barra de comandos, selecione **Publicar**.</span><span class="sxs-lookup"><span data-stu-id="ed118-157">On the command bar, select **Publish**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="ed118-158">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="ed118-158">Additional resources</span></span>

[<span data-ttu-id="ed118-159">Modificar uma página de site existente</span><span class="sxs-lookup"><span data-stu-id="ed118-159">Modify an existing site page</span></span>](modify-existing-page.md)

[<span data-ttu-id="ed118-160">Adicionar uma nova página do site</span><span class="sxs-lookup"><span data-stu-id="ed118-160">Add a new site page</span></span>](add-new-page.md)

[<span data-ttu-id="ed118-161">Selecionar layouts de página</span><span class="sxs-lookup"><span data-stu-id="ed118-161">Select page layouts</span></span>](select-page-layouts.md)

[<span data-ttu-id="ed118-162">Gerenciar metadados de SEO</span><span class="sxs-lookup"><span data-stu-id="ed118-162">Manage SEO metadata</span></span>](manage-seo-metadata.md)

[<span data-ttu-id="ed118-163">Enriquecer uma página de produto</span><span class="sxs-lookup"><span data-stu-id="ed118-163">Enrich a product page</span></span>](enrich-product-page.md)

[<span data-ttu-id="ed118-164">Enriquecer uma página de aterrissagem da categoria</span><span class="sxs-lookup"><span data-stu-id="ed118-164">Enrich a category landing page</span></span>](enrich-category-page.md)

[<span data-ttu-id="ed118-165">Verificar acessibilidade de conteúdo da página</span><span class="sxs-lookup"><span data-stu-id="ed118-165">Verify page content accessibility</span></span>](verify-accessibility.md)
