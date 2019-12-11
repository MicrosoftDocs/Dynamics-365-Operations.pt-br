---
title: Adicionar uma nova página do site
description: Este tópico descreve como adicionar uma nova página de site no Microsoft Dynamics 365 Commerce.
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
ms.openlocfilehash: d5ab90343220e427a80cc4dde17c628ba64ac69e
ms.sourcegitcommit: 295d940a345879b3dfc5991e387b91c7257019ea
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/01/2019
ms.locfileid: "2696729"
---
# <a name="add-a-new-site-page"></a><span data-ttu-id="e1457-103">Adicionar uma nova página do site</span><span class="sxs-lookup"><span data-stu-id="e1457-103">Add a new site page</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="e1457-104">Este tópico descreve como adicionar uma nova página de site no Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="e1457-104">This topic describes how to add a new site page in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="e1457-105">Visão geral</span><span class="sxs-lookup"><span data-stu-id="e1457-105">Overview</span></span>

<span data-ttu-id="e1457-106">Após a criação de modelos e fragmentos para o seu site, a próxima etapa é começar a criar páginas que os utilizam.</span><span class="sxs-lookup"><span data-stu-id="e1457-106">After you've created templates and fragments for your site, the next step is to start to create pages that use them.</span></span> <span data-ttu-id="e1457-107">Para começar, você deve selecionar um modelo ou layout, um nome de página e uma URL de página.</span><span class="sxs-lookup"><span data-stu-id="e1457-107">To get started, you must select a template or layout, a page name, and a page URL.</span></span>

## <a name="template-or-layout"></a><span data-ttu-id="e1457-108">Modelo ou layout</span><span class="sxs-lookup"><span data-stu-id="e1457-108">Template or layout</span></span>

<span data-ttu-id="e1457-109">Você pode usar um modelo ou um layout para sua nova página.</span><span class="sxs-lookup"><span data-stu-id="e1457-109">You can use either a template or a layout for your new page.</span></span> <span data-ttu-id="e1457-110">Para obter mais informações, consulte [Visão geral de modelos e layouts](templates-layouts-overview.md).</span><span class="sxs-lookup"><span data-stu-id="e1457-110">For more information, see [Templates and layouts overview](templates-layouts-overview.md).</span></span>

## <a name="page-name"></a><span data-ttu-id="e1457-111">Nome da página</span><span class="sxs-lookup"><span data-stu-id="e1457-111">Page name</span></span>

<span data-ttu-id="e1457-112">O nome da página deve ser exclusivo para sua página.</span><span class="sxs-lookup"><span data-stu-id="e1457-112">The page name must be unique to your page.</span></span> <span data-ttu-id="e1457-113">Deve ser descritivo, para que você possa encontrá-lo facilmente e outras pessoas saibam para que serve a página.</span><span class="sxs-lookup"><span data-stu-id="e1457-113">It should be descriptive, so that you can easily find it and other people know what the page is intended for.</span></span> <span data-ttu-id="e1457-114">Escolha o nome da página com cuidado, porque não pode ser alterado posteriormente.</span><span class="sxs-lookup"><span data-stu-id="e1457-114">Choose the page name carefully, because it can't be changed later.</span></span>

## <a name="page-url"></a><span data-ttu-id="e1457-115">URL da página</span><span class="sxs-lookup"><span data-stu-id="e1457-115">Page URL</span></span>

<span data-ttu-id="e1457-116">Você pode ter a opção de inserir uma URL para sua nova página.</span><span class="sxs-lookup"><span data-stu-id="e1457-116">You can have the option to enter a URL for your new page.</span></span> <span data-ttu-id="e1457-117">Ao criar uma página, você poderá inserir uma sequência de caracteres que será usada para formar uma URL completa.</span><span class="sxs-lookup"><span data-stu-id="e1457-117">When you create a page, you can enter a string that will be used to form a complete URL.</span></span> <span data-ttu-id="e1457-118">Essa sequência de caracteres é conhecida como URL relativa ou campo de dados dinâmico de URL.</span><span class="sxs-lookup"><span data-stu-id="e1457-118">This string is known as a relative URL or a URL slug.</span></span> <span data-ttu-id="e1457-119">Uma URL completa é então gerada com base no campo de dados dinâmico da URL e a nova página é atribuída a ele.</span><span class="sxs-lookup"><span data-stu-id="e1457-119">A complete URL is then generated based on the URL slug, and the new page is assigned to it.</span></span> <span data-ttu-id="e1457-120">Você poderá alterar o campo de dados dinâmico da URL posteriormente, antes de publicar a página.</span><span class="sxs-lookup"><span data-stu-id="e1457-120">You can change the URL slug later, before you publish the page.</span></span> <span data-ttu-id="e1457-121">Para obter mais informações, consulte [Criar uma URL da página](create-page-URL.md).</span><span class="sxs-lookup"><span data-stu-id="e1457-121">For more information, see [Create a page URL](create-page-URL.md).</span></span>

> [!NOTE]
> <span data-ttu-id="e1457-122">O Dynamics 365 Commerce dissocia URLs e conteúdo.</span><span class="sxs-lookup"><span data-stu-id="e1457-122">Dynamics 365 Commerce decouples URLs and content.</span></span> <span data-ttu-id="e1457-123">Em outras palavras, é possível criar uma página que não esteja associada a uma URL e criar uma URL que não esteja associado a uma página.</span><span class="sxs-lookup"><span data-stu-id="e1457-123">In other words, a page can be created that isn't associated with an URL, and a URL can be created that isn't associated with a page.</span></span> <span data-ttu-id="e1457-124">Portanto, a troca de conteúdo pode ser feita para uma URL e não requer tempo de inatividade, e os redirecionamentos são mais fáceis de gerenciar.</span><span class="sxs-lookup"><span data-stu-id="e1457-124">Therefore, content swapping can be done for a URL and doesn't require downtime, and redirects are easier to manage.</span></span>

## <a name="add-a-new-page"></a><span data-ttu-id="e1457-125">Adicionar uma nova página</span><span class="sxs-lookup"><span data-stu-id="e1457-125">Add a new page</span></span>

<span data-ttu-id="e1457-126">Para adicionar uma nova página ao site, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="e1457-126">To add a new site page to your site, follow these steps.</span></span>

1. <span data-ttu-id="e1457-127">Em **Sites**, selecione **Fabrikam** (ou o nome do seu site).</span><span class="sxs-lookup"><span data-stu-id="e1457-127">Under **Sites**, select **Fabrikam** (or the name of your site).</span></span>
1. <span data-ttu-id="e1457-128">Selecione **Nova página**.</span><span class="sxs-lookup"><span data-stu-id="e1457-128">Select **New Page**.</span></span>
1. <span data-ttu-id="e1457-129">Na caixa de diálogo **Nova página**, selecione um modelo e depois **OK**.</span><span class="sxs-lookup"><span data-stu-id="e1457-129">In the **New Page** dialog box, select a template, and then select **OK**.</span></span>
1. <span data-ttu-id="e1457-130">No campo **Nome da página**, insira um nome de página (por exemplo, **Minha nova página**).</span><span class="sxs-lookup"><span data-stu-id="e1457-130">In the **Page Name** field, enter a page name (for example, **My New Page**).</span></span>
1. <span data-ttu-id="e1457-131">No campo **URL**, insira uma sequência de caracteres (campo de dados dinâmico da URL) para concluir a URL (por exemplo, **mynewpage**).</span><span class="sxs-lookup"><span data-stu-id="e1457-131">In the **URL** field, enter a string (URL slug) to complete the URL (for example, **mynewpage**).</span></span>
1. <span data-ttu-id="e1457-132">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="e1457-132">Select **OK**.</span></span> <span data-ttu-id="e1457-133">O editor de páginas é exibido.</span><span class="sxs-lookup"><span data-stu-id="e1457-133">The page editor appears.</span></span> <span data-ttu-id="e1457-134">Observe que um cabeçalho e um rodapé são adicionados automaticamente à página, com base no modelo que você selecionou.</span><span class="sxs-lookup"><span data-stu-id="e1457-134">Notice that a header and a footer are automatically added to the page, based on the template that you selected.</span></span>
1. <span data-ttu-id="e1457-135">Na descrição da página, selecione o slot **Principal**, selecione o botão de reticências (**...**) e selecione **Adicionar módulo**.</span><span class="sxs-lookup"><span data-stu-id="e1457-135">In the page outline, select the **Main** slot, select the ellipsis button (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="e1457-136">Selecione **Contêiner** e, depois, **OK**.</span><span class="sxs-lookup"><span data-stu-id="e1457-136">Select **Container**, and then select **OK**</span></span>
1. <span data-ttu-id="e1457-137">Selecione **Contêiner fluido**, selecione o botão de reticências e selecione **Adicionar módulo**.</span><span class="sxs-lookup"><span data-stu-id="e1457-137">Select **Fluid Container**, select the ellipsis button, and then select **Add Module**.</span></span>
1. <span data-ttu-id="e1457-138">Selecione **Bloco de conteúdo sofisticado** e selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="e1457-138">Select **Content Rich block**, and then select **OK**.</span></span>
1. <span data-ttu-id="e1457-139">Selecione **Bloco de conteúdo sofisticado**, selecione o botão de reticências e selecione **Adicionar módulo**.</span><span class="sxs-lookup"><span data-stu-id="e1457-139">Select **Content Rich Block**, select the ellipsis button, and then select **Add Module**.</span></span>
1. <span data-ttu-id="e1457-140">Selecione **Item de bloco de conteúdo sofisticado** e selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="e1457-140">Select **Content rich block item**, and then select **OK**.</span></span>
1. <span data-ttu-id="e1457-141">No painel de propriedades à direita, selecione **Parágrafo** e, no campo, digite **Meu texto de teste**.</span><span class="sxs-lookup"><span data-stu-id="e1457-141">In the properties pane on the right, select **Paragraph**, and then, in the field, enter **My test text**.</span></span>
1. <span data-ttu-id="e1457-142">Selecione **Salvar** e **Fazer Check-in**.</span><span class="sxs-lookup"><span data-stu-id="e1457-142">Select **Save**, and then select **Check In**.</span></span>
1. <span data-ttu-id="e1457-143">No campo **Comentários**, insira **Adicionou nova página** e depois selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="e1457-143">In the **Comments** field, enter **Added new page**, and then select **OK**.</span></span>
1. <span data-ttu-id="e1457-144">Selecione **Visualizar** para exibir a página.</span><span class="sxs-lookup"><span data-stu-id="e1457-144">Select **Preview** to preview your page.</span></span> <span data-ttu-id="e1457-145">Quando terminar, feche a guia de visualização para retornar à ferramenta de criação.</span><span class="sxs-lookup"><span data-stu-id="e1457-145">When you've finished, close the preview tab to return to the authoring tool.</span></span>
1. <span data-ttu-id="e1457-146">Selecione **Publicar**.</span><span class="sxs-lookup"><span data-stu-id="e1457-146">Select **Publish**.</span></span>
1. <span data-ttu-id="e1457-147">No caminho de navegação (trilha de navegação), selecione **Fabrikam** (ou o nome do seu site).</span><span class="sxs-lookup"><span data-stu-id="e1457-147">In the navigation path (breadcrumbs), select **Fabrikam** (or the name of your site).</span></span>
1. <span data-ttu-id="e1457-148">No painel de navegação à esquerda, selecione **URLs**.</span><span class="sxs-lookup"><span data-stu-id="e1457-148">In the navigation pane on the left, select **URLs**.</span></span>
1. <span data-ttu-id="e1457-149">Encontre e selecione sua URL (**mynewpage**) na lista.</span><span class="sxs-lookup"><span data-stu-id="e1457-149">Find and select your URL (**mynewpage**) in the list.</span></span>
1. <span data-ttu-id="e1457-150">Selecione **Publicar**.</span><span class="sxs-lookup"><span data-stu-id="e1457-150">Select **Publish**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="e1457-151">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="e1457-151">Additional resources</span></span>

[<span data-ttu-id="e1457-152">Modificar uma página de site existente</span><span class="sxs-lookup"><span data-stu-id="e1457-152">Modify an existing site page</span></span>](modify-existing-page.md)

[<span data-ttu-id="e1457-153">Selecionar layouts de página</span><span class="sxs-lookup"><span data-stu-id="e1457-153">Select page layouts</span></span>](select-page-layouts.md)

[<span data-ttu-id="e1457-154">Gerenciar metadados de SEO</span><span class="sxs-lookup"><span data-stu-id="e1457-154">Manage SEO metadata</span></span>](manage-seo-metadata.md)

[<span data-ttu-id="e1457-155">Salvar, visualizar, e publicar uma página</span><span class="sxs-lookup"><span data-stu-id="e1457-155">Save, preview, and publish a page</span></span>](save-preview-publish-page.md)

[<span data-ttu-id="e1457-156">Enriquecer uma página de produto</span><span class="sxs-lookup"><span data-stu-id="e1457-156">Enrich a product page</span></span>](enrich-product-page.md)

[<span data-ttu-id="e1457-157">Enriquecer uma página de aterrissagem da categoria</span><span class="sxs-lookup"><span data-stu-id="e1457-157">Enrich a category landing page</span></span>](enrich-category-page.md)

