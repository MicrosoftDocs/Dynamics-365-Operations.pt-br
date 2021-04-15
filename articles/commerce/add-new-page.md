---
title: Adicionar uma nova página do site
description: Este tópico descreve como adicionar uma nova página de site no Microsoft Dynamics 365 Commerce.
author: psimolin
ms.date: 04/14/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 4a2ecc3ef3ff3f708cec50e42777b50ec4576e25
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5797542"
---
# <a name="add-a-new-site-page"></a><span data-ttu-id="ec13c-103">Adicionar uma nova página do site</span><span class="sxs-lookup"><span data-stu-id="ec13c-103">Add a new site page</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="ec13c-104">Este tópico descreve como adicionar uma nova página de site no Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="ec13c-104">This topic describes how to add a new site page in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="ec13c-105">Após a criação de modelos e fragmentos para o seu site, a próxima etapa é começar a criar páginas que os utilizam.</span><span class="sxs-lookup"><span data-stu-id="ec13c-105">After you've created templates and fragments for your site, the next step is to start to create pages that use them.</span></span> <span data-ttu-id="ec13c-106">Para começar, você deve selecionar um modelo ou layout, um nome de página e uma URL de página.</span><span class="sxs-lookup"><span data-stu-id="ec13c-106">To get started, you must select a template or layout, a page name, and a page URL.</span></span>

## <a name="template-or-layout"></a><span data-ttu-id="ec13c-107">Modelo ou layout</span><span class="sxs-lookup"><span data-stu-id="ec13c-107">Template or layout</span></span>

<span data-ttu-id="ec13c-108">Você pode usar um modelo ou um layout para sua nova página.</span><span class="sxs-lookup"><span data-stu-id="ec13c-108">You can use either a template or a layout for your new page.</span></span> <span data-ttu-id="ec13c-109">Para obter mais informações, consulte [Visão geral de modelos e layouts](templates-layouts-overview.md).</span><span class="sxs-lookup"><span data-stu-id="ec13c-109">For more information, see [Templates and layouts overview](templates-layouts-overview.md).</span></span>

## <a name="page-name"></a><span data-ttu-id="ec13c-110">Nome da página</span><span class="sxs-lookup"><span data-stu-id="ec13c-110">Page name</span></span>

<span data-ttu-id="ec13c-111">O nome da página deve ser exclusivo para sua página.</span><span class="sxs-lookup"><span data-stu-id="ec13c-111">The page name must be unique to your page.</span></span> <span data-ttu-id="ec13c-112">Deve ser descritivo, para que você possa encontrá-lo facilmente e outras pessoas saibam para que serve a página.</span><span class="sxs-lookup"><span data-stu-id="ec13c-112">It should be descriptive, so that you can easily find it and other people know what the page is intended for.</span></span> <span data-ttu-id="ec13c-113">Escolha o nome da página com cuidado, porque não pode ser alterado posteriormente.</span><span class="sxs-lookup"><span data-stu-id="ec13c-113">Choose the page name carefully, because it can't be changed later.</span></span>

## <a name="page-url"></a><span data-ttu-id="ec13c-114">URL da página</span><span class="sxs-lookup"><span data-stu-id="ec13c-114">Page URL</span></span>

<span data-ttu-id="ec13c-115">Você pode ter a opção de inserir uma URL para sua nova página.</span><span class="sxs-lookup"><span data-stu-id="ec13c-115">You can have the option to enter a URL for your new page.</span></span> <span data-ttu-id="ec13c-116">Ao criar uma página, você poderá inserir uma sequência de caracteres que será usada para formar uma URL completa.</span><span class="sxs-lookup"><span data-stu-id="ec13c-116">When you create a page, you can enter a string that will be used to form a complete URL.</span></span> <span data-ttu-id="ec13c-117">Essa sequência de caracteres é conhecida como URL relativa ou campo de dados dinâmico de URL.</span><span class="sxs-lookup"><span data-stu-id="ec13c-117">This string is known as a relative URL or a URL slug.</span></span> <span data-ttu-id="ec13c-118">Uma URL completa é então gerada com base no campo de dados dinâmico da URL e a nova página é atribuída a ele.</span><span class="sxs-lookup"><span data-stu-id="ec13c-118">A complete URL is then generated based on the URL slug, and the new page is assigned to it.</span></span> <span data-ttu-id="ec13c-119">Você poderá alterar o campo de dados dinâmico da URL posteriormente, antes de publicar a página.</span><span class="sxs-lookup"><span data-stu-id="ec13c-119">You can change the URL slug later, before you publish the page.</span></span> <span data-ttu-id="ec13c-120">Para obter mais informações, consulte [Criar uma URL da página](create-page-URL.md).</span><span class="sxs-lookup"><span data-stu-id="ec13c-120">For more information, see [Create a page URL](create-page-URL.md).</span></span>

> [!NOTE]
> <span data-ttu-id="ec13c-121">O Dynamics 365 Commerce dissocia URLs e conteúdo.</span><span class="sxs-lookup"><span data-stu-id="ec13c-121">Dynamics 365 Commerce decouples URLs and content.</span></span> <span data-ttu-id="ec13c-122">Em outras palavras, é possível criar uma página que não esteja associada a uma URL e criar uma URL que não esteja associado a uma página.</span><span class="sxs-lookup"><span data-stu-id="ec13c-122">In other words, a page can be created that isn't associated with an URL, and a URL can be created that isn't associated with a page.</span></span> <span data-ttu-id="ec13c-123">Portanto, a troca de conteúdo pode ser feita para uma URL e não requer tempo de inatividade, e os redirecionamentos são mais fáceis de gerenciar.</span><span class="sxs-lookup"><span data-stu-id="ec13c-123">Therefore, content swapping can be done for a URL and doesn't require downtime, and redirects are easier to manage.</span></span>

## <a name="add-a-new-page"></a><span data-ttu-id="ec13c-124">Adicionar uma nova página</span><span class="sxs-lookup"><span data-stu-id="ec13c-124">Add a new page</span></span>

<span data-ttu-id="ec13c-125">Para adicionar uma nova página ao site, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="ec13c-125">To add a new site page to your site, follow these steps.</span></span>

1. <span data-ttu-id="ec13c-126">Em **Sites**, selecione **Fabrikam** (ou o nome do seu site).</span><span class="sxs-lookup"><span data-stu-id="ec13c-126">Under **Sites**, select **Fabrikam** (or the name of your site).</span></span>
1. <span data-ttu-id="ec13c-127">Selecione **Nova página**.</span><span class="sxs-lookup"><span data-stu-id="ec13c-127">Select **New Page**.</span></span>
1. <span data-ttu-id="ec13c-128">Na caixa de diálogo **Nova página**, selecione um modelo e depois **OK**.</span><span class="sxs-lookup"><span data-stu-id="ec13c-128">In the **New Page** dialog box, select a template, and then select **OK**.</span></span>
1. <span data-ttu-id="ec13c-129">No campo **Nome da página**, insira um nome de página (por exemplo, **Minha nova página**).</span><span class="sxs-lookup"><span data-stu-id="ec13c-129">In the **Page Name** field, enter a page name (for example, **My New Page**).</span></span>
1. <span data-ttu-id="ec13c-130">No campo **URL**, insira uma sequência de caracteres (campo de dados dinâmico da URL) para concluir a URL (por exemplo, **mynewpage**).</span><span class="sxs-lookup"><span data-stu-id="ec13c-130">In the **URL** field, enter a string (URL slug) to complete the URL (for example, **mynewpage**).</span></span>
1. <span data-ttu-id="ec13c-131">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="ec13c-131">Select **OK**.</span></span> <span data-ttu-id="ec13c-132">O editor de páginas é exibido.</span><span class="sxs-lookup"><span data-stu-id="ec13c-132">The page editor appears.</span></span> <span data-ttu-id="ec13c-133">Observe que um cabeçalho e um rodapé são adicionados automaticamente à página, com base no modelo que você selecionou.</span><span class="sxs-lookup"><span data-stu-id="ec13c-133">Notice that a header and a footer are automatically added to the page, based on the template that you selected.</span></span>
1. <span data-ttu-id="ec13c-134">Na descrição da página, selecione o slot **Principal**, selecione o botão de reticências (**...**) e selecione **Adicionar módulo**.</span><span class="sxs-lookup"><span data-stu-id="ec13c-134">In the page outline, select the **Main** slot, select the ellipsis button (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="ec13c-135">Selecione **Contêiner** e, depois, **OK**.</span><span class="sxs-lookup"><span data-stu-id="ec13c-135">Select **Container**, and then select **OK**</span></span>
1. <span data-ttu-id="ec13c-136">Selecione **Contêiner fluido**, selecione o botão de reticências e selecione **Adicionar módulo**.</span><span class="sxs-lookup"><span data-stu-id="ec13c-136">Select **Fluid Container**, select the ellipsis button, and then select **Add Module**.</span></span>
1. <span data-ttu-id="ec13c-137">Selecione **Bloco de conteúdo sofisticado** e selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="ec13c-137">Select **Content Rich block**, and then select **OK**.</span></span>
1. <span data-ttu-id="ec13c-138">Selecione **Bloco de conteúdo sofisticado**, selecione o botão de reticências e selecione **Adicionar módulo**.</span><span class="sxs-lookup"><span data-stu-id="ec13c-138">Select **Content Rich Block**, select the ellipsis button, and then select **Add Module**.</span></span>
1. <span data-ttu-id="ec13c-139">Selecione **Item de bloco de conteúdo sofisticado** e selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="ec13c-139">Select **Content rich block item**, and then select **OK**.</span></span>
1. <span data-ttu-id="ec13c-140">No painel de propriedades à direita, selecione **Parágrafo** e, no campo, digite **Meu texto de teste**.</span><span class="sxs-lookup"><span data-stu-id="ec13c-140">In the properties pane on the right, select **Paragraph**, and then, in the field, enter **My test text**.</span></span>
1. <span data-ttu-id="ec13c-141">Selecione **Salvar** e **Finalizar edição**.</span><span class="sxs-lookup"><span data-stu-id="ec13c-141">Select **Save**, and then select **Finish editing**.</span></span>
1. <span data-ttu-id="ec13c-142">No campo **Comentários**, insira **Adicionou nova página** e depois selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="ec13c-142">In the **Comments** field, enter **Added new page**, and then select **OK**.</span></span>
1. <span data-ttu-id="ec13c-143">Selecione **Visualizar** para exibir a página.</span><span class="sxs-lookup"><span data-stu-id="ec13c-143">Select **Preview** to preview your page.</span></span> <span data-ttu-id="ec13c-144">Quando terminar, feche a guia de visualização para retornar à ferramenta de criação.</span><span class="sxs-lookup"><span data-stu-id="ec13c-144">When you've finished, close the preview tab to return to the authoring tool.</span></span>
1. <span data-ttu-id="ec13c-145">Selecione **Publicar**.</span><span class="sxs-lookup"><span data-stu-id="ec13c-145">Select **Publish**.</span></span>
1. <span data-ttu-id="ec13c-146">No caminho de navegação (trilha de navegação), selecione **Fabrikam** (ou o nome do seu site).</span><span class="sxs-lookup"><span data-stu-id="ec13c-146">In the navigation path (breadcrumbs), select **Fabrikam** (or the name of your site).</span></span>
1. <span data-ttu-id="ec13c-147">No painel de navegação à esquerda, selecione **URLs**.</span><span class="sxs-lookup"><span data-stu-id="ec13c-147">In the navigation pane on the left, select **URLs**.</span></span>
1. <span data-ttu-id="ec13c-148">Encontre e selecione sua URL (**mynewpage**) na lista.</span><span class="sxs-lookup"><span data-stu-id="ec13c-148">Find and select your URL (**mynewpage**) in the list.</span></span>
1. <span data-ttu-id="ec13c-149">Selecione **Publicar**.</span><span class="sxs-lookup"><span data-stu-id="ec13c-149">Select **Publish**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="ec13c-150">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="ec13c-150">Additional resources</span></span>

[<span data-ttu-id="ec13c-151">Modificar uma página de site existente</span><span class="sxs-lookup"><span data-stu-id="ec13c-151">Modify an existing site page</span></span>](modify-existing-page.md)

[<span data-ttu-id="ec13c-152">Selecionar layouts de página</span><span class="sxs-lookup"><span data-stu-id="ec13c-152">Select page layouts</span></span>](select-page-layouts.md)

[<span data-ttu-id="ec13c-153">Gerenciar metadados de SEO</span><span class="sxs-lookup"><span data-stu-id="ec13c-153">Manage SEO metadata</span></span>](manage-seo-metadata.md)

[<span data-ttu-id="ec13c-154">Salvar, visualizar, e publicar uma página</span><span class="sxs-lookup"><span data-stu-id="ec13c-154">Save, preview, and publish a page</span></span>](save-preview-publish-page.md)

[<span data-ttu-id="ec13c-155">Enriquecer uma página de produto</span><span class="sxs-lookup"><span data-stu-id="ec13c-155">Enrich a product page</span></span>](enrich-product-page.md)

[<span data-ttu-id="ec13c-156">Enriquecer uma página de aterrissagem da categoria</span><span class="sxs-lookup"><span data-stu-id="ec13c-156">Enrich a category landing page</span></span>](enrich-category-page.md)

[<span data-ttu-id="ec13c-157">Verificar acessibilidade do conteúdo da página</span><span class="sxs-lookup"><span data-stu-id="ec13c-157">Verify page content accessibility</span></span>](verify-accessibility.md)

[<span data-ttu-id="ec13c-158">Criar páginas dinâmicas de comércio eletrônico com base nos parâmetros da URL</span><span class="sxs-lookup"><span data-stu-id="ec13c-158">Create dynamic e-commerce pages based on URL parameters</span></span>](create-dynamic-pages.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
