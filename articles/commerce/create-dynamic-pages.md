---
title: Criar páginas de comércio eletrônico dinâmicas com base nos parâmetros da URL
description: Este tópico descreve como configurar uma página de comércio eletrônico do Microsoft Dynamics 365 Commerce que pode fornecer conteúdo dinâmico, com base em parâmetros de URL.
author: StuHarg
ms.date: 01/28/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ROBOTS: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.author: stuharg
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 8f59b80880e6947e1b45c110df0e78d4bdd57c5d
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5795802"
---
# <a name="create-dynamic-e-commerce-pages-based-on-url-parameters"></a><span data-ttu-id="ccf1d-103">Criar páginas de comércio eletrônico dinâmicas com base nos parâmetros da URL</span><span class="sxs-lookup"><span data-stu-id="ccf1d-103">Create dynamic e-commerce pages based on URL parameters</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="ccf1d-104">Este tópico descreve como configurar uma página de comércio eletrônico do Microsoft Dynamics 365 Commerce que pode fornecer conteúdo dinâmico, com base em parâmetros de URL.</span><span class="sxs-lookup"><span data-stu-id="ccf1d-104">This topic describes how to set up a Microsoft Dynamics 365 Commerce e-commerce page that can serve dynamic content, based on URL parameters.</span></span>

<span data-ttu-id="ccf1d-105">Uma página de comércio eletrônico pode ser configurada para fornecer conteúdo diferente, com base em um segmento no caminho da URL.</span><span class="sxs-lookup"><span data-stu-id="ccf1d-105">An e-commerce page can be configured to serve different content, based on a segment in the URL path.</span></span> <span data-ttu-id="ccf1d-106">Portanto, a página é conhecida como uma página dinâmica.</span><span class="sxs-lookup"><span data-stu-id="ccf1d-106">Therefore, the page is known as a dynamic page.</span></span> <span data-ttu-id="ccf1d-107">O segmento é usado como um parâmetro para recuperar o conteúdo da página.</span><span class="sxs-lookup"><span data-stu-id="ccf1d-107">The segment is used as a parameter to retrieve the page content.</span></span> <span data-ttu-id="ccf1d-108">Por exemplo, uma página denominada **visualizador\_de blog** é criada e associada à URL `https://fabrikam.com/blog`.</span><span class="sxs-lookup"><span data-stu-id="ccf1d-108">For example, a page that is named **blog\_viewer** is created and associated with the URL `https://fabrikam.com/blog`.</span></span> <span data-ttu-id="ccf1d-109">Essa página pode ser usada para mostrar conteúdo diferente, com base no último segmento do caminho da URL.</span><span class="sxs-lookup"><span data-stu-id="ccf1d-109">This page can then be used to show different content, based on the last segment in the URL path.</span></span> <span data-ttu-id="ccf1d-110">Por exemplo, o último segmento na URL `https://fabrikam.com/blog/article-1` é o **artigo-1**.</span><span class="sxs-lookup"><span data-stu-id="ccf1d-110">For example, the last segment in the URL `https://fabrikam.com/blog/article-1` is **article-1**.</span></span>

<span data-ttu-id="ccf1d-111">As páginas personalizadas separadas que substituem a página dinâmica também podem ser associadas a segmentos no caminho da URL.</span><span class="sxs-lookup"><span data-stu-id="ccf1d-111">Separate custom pages that override the dynamic page can also be associated with segments in the URL path.</span></span> <span data-ttu-id="ccf1d-112">Por exemplo, uma página denominada **resumo\_de blog** é criada e associada à URL `https://fabrikam.com/blog/about-this-blog`.</span><span class="sxs-lookup"><span data-stu-id="ccf1d-112">For example, a page that is named **blog\_summary** is created and associated with the URL `https://fabrikam.com/blog/about-this-blog`.</span></span> <span data-ttu-id="ccf1d-113">Quando essa URL é solicitada, a página **resumo\_do blog** que é associada ao parâmetro **/about-this-blog** é retornada, em vez da página **visualizador\_do blog**.</span><span class="sxs-lookup"><span data-stu-id="ccf1d-113">When this URL is requested, the **blog\_summary** page that is associated with the **/about-this-blog** parameter is returned instead of the **blog\_viewer** page.</span></span>

> [!NOTE]
> <span data-ttu-id="ccf1d-114">A funcionalidade para hospedar, recuperar e mostrar o conteúdo da página dinâmica é implementada usando um módulo personalizado.</span><span class="sxs-lookup"><span data-stu-id="ccf1d-114">The functionality for hosting, retrieving, and showing dynamic page content is implemented by using a custom module.</span></span> <span data-ttu-id="ccf1d-115">Para obter mais informações, consulte [Extensibilidade de canal online](e-commerce-extensibility/overview.md).</span><span class="sxs-lookup"><span data-stu-id="ccf1d-115">For more information, see [Online channel extensibility](e-commerce-extensibility/overview.md).</span></span>

## <a name="set-up-a-dynamic-e-commerce-page"></a><span data-ttu-id="ccf1d-116">Configurar uma página dinâmica de comércio eletrônico</span><span class="sxs-lookup"><span data-stu-id="ccf1d-116">Set up a dynamic e-commerce page</span></span>

<span data-ttu-id="ccf1d-117">Para configurar uma página dinâmica de comércio eletrônico, você deve criar a página dinâmica, criar a URL base e configurar o roteiro para a página dinâmica.</span><span class="sxs-lookup"><span data-stu-id="ccf1d-117">To set up a dynamic e-commerce page, you must create the dynamic page, create the base URL, and configure the route to the dynamic page.</span></span>

### <a name="create-the-page-that-will-serve-dynamic-content"></a><span data-ttu-id="ccf1d-118">Criar a página que fornecerá conteúdo dinâmico</span><span class="sxs-lookup"><span data-stu-id="ccf1d-118">Create the page that will serve dynamic content</span></span>

<span data-ttu-id="ccf1d-119">Para criar uma página que fornecerá conteúdo dinâmico, siga as etapas em [Adicionar uma nova página do site](add-new-page.md).</span><span class="sxs-lookup"><span data-stu-id="ccf1d-119">To create a page that will serve dynamic content, follow the steps in [Add a new site page](add-new-page.md).</span></span> <span data-ttu-id="ccf1d-120">A página que você criar exigirá a implementação de um módulo que usa o último segmento no caminho da URL para recuperar conteúdo de uma fonte de dados externa.</span><span class="sxs-lookup"><span data-stu-id="ccf1d-120">The page that you create will require implementation of a module that uses the last segment in the URL path to retrieve content from an external data source.</span></span> <span data-ttu-id="ccf1d-121">Para obter mais informações sobre o desenvolvimento de módulos personalizados, consulte [Extensibilidade de canal online](e-commerce-extensibility/overview.md).</span><span class="sxs-lookup"><span data-stu-id="ccf1d-121">For more information about custom module development, see [Online channel extensibility](e-commerce-extensibility/overview.md).</span></span>

### <a name="create-the-base-url-for-the-dynamic-page"></a><span data-ttu-id="ccf1d-122">Criar a URL base para a página dinâmica</span><span class="sxs-lookup"><span data-stu-id="ccf1d-122">Create the base URL for the dynamic page</span></span>

<span data-ttu-id="ccf1d-123">Para criar a URL base para a página dinâmica no assistente para criação de sites do Commerce, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="ccf1d-123">To create the base URL for the dynamic page in Commerce site builder, follow these steps.</span></span>

1. <span data-ttu-id="ccf1d-124">Acesse **URLs** e selecione **Nova \> Nova URL**.</span><span class="sxs-lookup"><span data-stu-id="ccf1d-124">Go to **URLs**, and select **New \> New URL**.</span></span>
1. <span data-ttu-id="ccf1d-125">Na caixa de diálogo **Criar nova URL**, selecione **Página interna**.</span><span class="sxs-lookup"><span data-stu-id="ccf1d-125">In the **Create new URL** dialog box, select **Internal page**.</span></span> <span data-ttu-id="ccf1d-126">Em **Caminho da URL**, insira o caminho que servirá como a raiz da página dinâmica (neste exemplo, **/blog**).</span><span class="sxs-lookup"><span data-stu-id="ccf1d-126">Under **URL path**, enter the path that will serve as the root for the dynamic page (in this example, **/blog**).</span></span> <span data-ttu-id="ccf1d-127">Selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="ccf1d-127">Then select **Next**.</span></span>
1. <span data-ttu-id="ccf1d-128">Na caixa de diálogo **Selecionar uma página**, selecione a página criada para atuar como a página dinâmica e selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="ccf1d-128">In the **Select a page** dialog box, select the page that you created to serve as the dynamic page, and then select **Save**.</span></span>
1. <span data-ttu-id="ccf1d-129">Selecione **Publicar**.</span><span class="sxs-lookup"><span data-stu-id="ccf1d-129">Select **Publish**.</span></span>

### <a name="configure-the-route-to-the-dynamic-page"></a><span data-ttu-id="ccf1d-130">Configurar o roteiro para a página dinâmica</span><span class="sxs-lookup"><span data-stu-id="ccf1d-130">Configure the route to the dynamic page</span></span>

<span data-ttu-id="ccf1d-131">Para configurar o roteiro para a página dinâmica no assistente para criação de sites do Commerce, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="ccf1d-131">To configure the route to the dynamic page in Commerce site builder, follow these steps.</span></span>

1. <span data-ttu-id="ccf1d-132">Acesse **Configurações do Site \> Extensões**.</span><span class="sxs-lookup"><span data-stu-id="ccf1d-132">Go to **Site Settings \> Extensions**.</span></span>
1. <span data-ttu-id="ccf1d-133">Em **Caminhos de URL parametrizada**, selecione **Adicionar** e insira o caminho da URL inserido ao criar a URL (neste exemplo, **/blog**).</span><span class="sxs-lookup"><span data-stu-id="ccf1d-133">Under **Parameterized URL paths**, select **Add**, and then enter the URL path that you entered when you created the URL (in this example, **/blog**).</span></span>
1. <span data-ttu-id="ccf1d-134">Selecione **Salvar e publicar**.</span><span class="sxs-lookup"><span data-stu-id="ccf1d-134">Select **Save and publish**.</span></span>

<span data-ttu-id="ccf1d-135">Depois que o roteiro for configurado, todas as solicitações ao caminho de URL parametrizada retornarão a página associada a essa URL.</span><span class="sxs-lookup"><span data-stu-id="ccf1d-135">After the route is configured, all requests to the parameterized URL path will return the page that is associated with that URL.</span></span> <span data-ttu-id="ccf1d-136">Se alguma solicitação contiver um segmento adicional, a página associada será devolvida e o conteúdo da página será recuperado usando o segmento como um parâmetro.</span><span class="sxs-lookup"><span data-stu-id="ccf1d-136">If any requests contain an additional segment, the associated page will be returned, and the page content will be retrieved by using the segment as a parameter.</span></span> <span data-ttu-id="ccf1d-137">Por exemplo, `https://fabrikam.com/blog/article-1` retornará a página **resumo de\_blog** e o conteúdo da página será recuperado usando o parâmetro **/article-1**.</span><span class="sxs-lookup"><span data-stu-id="ccf1d-137">For example, `https://fabrikam.com/blog/article-1` will return the **blog\_summary** page, and the page content will be retrieved by using the **/article-1** parameter.</span></span>

## <a name="override-a-parameterized-url-with-a-custom-page"></a><span data-ttu-id="ccf1d-138">Substituir uma URL parametrizada por uma página personalizada</span><span class="sxs-lookup"><span data-stu-id="ccf1d-138">Override a parameterized URL with a custom page</span></span>

<span data-ttu-id="ccf1d-139">Para substituir uma URL parametrizada por uma página personalizada no assistente para criação de sites do Commerce, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="ccf1d-139">To override a parameterized URL with a custom page in Commerce site builder, follow these steps.</span></span>

1. <span data-ttu-id="ccf1d-140">Acesse **URLs** e selecione **Nova \> Nova URL**.</span><span class="sxs-lookup"><span data-stu-id="ccf1d-140">Go to **URLs**, and select **New \> New URL**.</span></span>
1. <span data-ttu-id="ccf1d-141">Na caixa de diálogo **Criar nova URL**, selecione **Página interna**.</span><span class="sxs-lookup"><span data-stu-id="ccf1d-141">In the **Create new URL** dialog box, select **Internal page**.</span></span> <span data-ttu-id="ccf1d-142">Em **Caminho da URL**, insira o caminho que inclui o segmento a ser substituído (neste exemplo, **/blog/about-this-blog**).</span><span class="sxs-lookup"><span data-stu-id="ccf1d-142">Under **URL path**, enter the path that includes the segment to override (in this example, **/blog/about-this-blog**).</span></span> <span data-ttu-id="ccf1d-143">Selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="ccf1d-143">Then select **Next**.</span></span>
1. <span data-ttu-id="ccf1d-144">Na caixa de diálogo **Selecionar uma página**, selecione a página personalizado e, depois, **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="ccf1d-144">In the **Select a page** dialog box, select the custom page, and then select **Save**.</span></span>
1. <span data-ttu-id="ccf1d-145">Selecione **Publicar**.</span><span class="sxs-lookup"><span data-stu-id="ccf1d-145">Select **Publish**.</span></span>
1. <span data-ttu-id="ccf1d-146">Se a página personalizada ainda não tiver sido publicada, acesse **Páginas**, selecione a página personalizada e selecione **Publicar**.</span><span class="sxs-lookup"><span data-stu-id="ccf1d-146">If the custom page hasn't yet been published, go to **Pages**, select the custom page, and then select **Publish**.</span></span>

<span data-ttu-id="ccf1d-147">Depois que a página personalizada for publicada, ela será fornecida em vez da página dinâmica com conteúdo parametrizado.</span><span class="sxs-lookup"><span data-stu-id="ccf1d-147">After the custom page is published, it will be served instead of the dynamic page that has parameterized content.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="ccf1d-148">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="ccf1d-148">Additional resources</span></span>

[<span data-ttu-id="ccf1d-149">Modificar uma página de site existente</span><span class="sxs-lookup"><span data-stu-id="ccf1d-149">Modify an existing site page</span></span>](modify-existing-page.md)

[<span data-ttu-id="ccf1d-150">Adicionar uma nova página do site</span><span class="sxs-lookup"><span data-stu-id="ccf1d-150">Add a new site page</span></span>](add-new-page.md)

[<span data-ttu-id="ccf1d-151">Selecionar layouts de página</span><span class="sxs-lookup"><span data-stu-id="ccf1d-151">Select page layouts</span></span>](select-page-layouts.md)

[<span data-ttu-id="ccf1d-152">Gerenciar metadados de SEO</span><span class="sxs-lookup"><span data-stu-id="ccf1d-152">Manage SEO metadata</span></span>](manage-seo-metadata.md)

[<span data-ttu-id="ccf1d-153">Salvar, visualizar, e publicar uma página</span><span class="sxs-lookup"><span data-stu-id="ccf1d-153">Save, preview, and publish a page</span></span>](save-preview-publish-page.md)

[<span data-ttu-id="ccf1d-154">Enriquecer uma página de produto</span><span class="sxs-lookup"><span data-stu-id="ccf1d-154">Enrich a product page</span></span>](enrich-product-page.md)

[<span data-ttu-id="ccf1d-155">Enriquecer uma página de aterrissagem da categoria</span><span class="sxs-lookup"><span data-stu-id="ccf1d-155">Enrich a category landing page</span></span>](enrich-category-page.md)

[<span data-ttu-id="ccf1d-156">Verificar acessibilidade do conteúdo da página</span><span class="sxs-lookup"><span data-stu-id="ccf1d-156">Verify page content accessibility</span></span>](verify-accessibility.md)

[<span data-ttu-id="ccf1d-157">Extensibilidade do canal online</span><span class="sxs-lookup"><span data-stu-id="ccf1d-157">Online channel extensibility</span></span>](e-commerce-extensibility/overview.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
