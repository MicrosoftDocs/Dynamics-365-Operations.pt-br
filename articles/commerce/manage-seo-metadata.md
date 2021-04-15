---
title: Gerenciar metadados de SEO
description: Este tópico descreve como gerenciar metadados da otimização do mecanismo de pesquisa (SEO) no Microsoft Dynamics 365 Commerce.
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
ms.openlocfilehash: 1e03ef346df92a94b0a403f241d0f7d1f64fd210
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5794202"
---
# <a name="manage-seo-metadata"></a><span data-ttu-id="181f7-103">Gerenciar metadados de SEO</span><span class="sxs-lookup"><span data-stu-id="181f7-103">Manage SEO metadata</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="181f7-104">Este tópico descreve como gerenciar metadados da otimização do mecanismo de pesquisa (SEO) no Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="181f7-104">This topic describes how to manage search engine optimization (SEO) metadata in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="181f7-105">Os metadados de SEO para um site podem ser gerenciados usando mapas do site e metadados da página.</span><span class="sxs-lookup"><span data-stu-id="181f7-105">SEO metadata for a site can be managed by using site maps and page metadata.</span></span>
    
## <a name="site-maps"></a><span data-ttu-id="181f7-106">Mapas do site</span><span class="sxs-lookup"><span data-stu-id="181f7-106">Site maps</span></span>

<span data-ttu-id="181f7-107">Um mapa do site é uma lista legível por máquina, no formato XML, das páginas do seu site.</span><span class="sxs-lookup"><span data-stu-id="181f7-107">A site map is a machine-readable list, in XML format, of the pages on your website.</span></span> <span data-ttu-id="181f7-108">Ele deve ser consumido pelos mecanismos de pesquisa, para que eles possam fornecer melhores resultados de pesquisa em seu site.</span><span class="sxs-lookup"><span data-stu-id="181f7-108">It's intended to be consumed by search engines, so that they can provide better search results from your site.</span></span> <span data-ttu-id="181f7-109">Os mapas do site podem ser incorporados manualmente pelos mecanismos de pesquisa ou publicados em um arquivo robots.txt.</span><span class="sxs-lookup"><span data-stu-id="181f7-109">Site maps can be manually ingested by search engines or published in a robots.txt file.</span></span>

<span data-ttu-id="181f7-110">O Dynamics 365 Commerce oferece suporte à geração automática de mapas de site.</span><span class="sxs-lookup"><span data-stu-id="181f7-110">Dynamics 365 Commerce supports automatic generation of site maps.</span></span> <span data-ttu-id="181f7-111">Os mapas de site são atualizados automaticamente quando as páginas são publicadas e as publicações canceladas.</span><span class="sxs-lookup"><span data-stu-id="181f7-111">Site maps are automatically updated when pages are published and unpublished.</span></span>

### <a name="turn-on-site-map-generation"></a><span data-ttu-id="181f7-112">Ative a geração do mapa do site</span><span class="sxs-lookup"><span data-stu-id="181f7-112">Turn on site map generation</span></span>

1. <span data-ttu-id="181f7-113">Conectar-se à ferramenta de criação.</span><span class="sxs-lookup"><span data-stu-id="181f7-113">Sign in to the authoring tool.</span></span>
1. <span data-ttu-id="181f7-114">Em **Sites**, selecione **Fabrikam** (ou o nome do seu site).</span><span class="sxs-lookup"><span data-stu-id="181f7-114">Under **Sites**, select **Fabrikam** (or the name of your site).</span></span>
1. <span data-ttu-id="181f7-115">No painel de navegação à esquerda, selecione **Gerenciamento de sites**.</span><span class="sxs-lookup"><span data-stu-id="181f7-115">In the navigation pane on the left, select **Site Management**.</span></span>
1. <span data-ttu-id="181f7-116">Verifique se a opção **Mapas de site habilitados** está ativada.</span><span class="sxs-lookup"><span data-stu-id="181f7-116">Make sure that the **Site maps enabled** option is turned on.</span></span>

## <a name="page-metadata"></a><span data-ttu-id="181f7-117">Metadados da página</span><span class="sxs-lookup"><span data-stu-id="181f7-117">Page metadata</span></span>

<span data-ttu-id="181f7-118">O Dynamics 365 Commerce permite gerenciar metadados de SEO para páginas individuais.</span><span class="sxs-lookup"><span data-stu-id="181f7-118">Dynamics 365 Commerce lets you manage SEO metadata for individual pages.</span></span> <span data-ttu-id="181f7-119">É possível exibir e modificar estas informações na seção **Propriedades de SEO** de um contêiner de página.</span><span class="sxs-lookup"><span data-stu-id="181f7-119">You can view and modify this information in the **SEO Properties** section of a page container.</span></span> <span data-ttu-id="181f7-120">As seguintes propriedades de metadados de SEO são suportadas:</span><span class="sxs-lookup"><span data-stu-id="181f7-120">The following SEO metadata properties are supported:</span></span>

- <span data-ttu-id="181f7-121">Cargo</span><span class="sxs-lookup"><span data-stu-id="181f7-121">Title</span></span>
- <span data-ttu-id="181f7-122">Descrição</span><span class="sxs-lookup"><span data-stu-id="181f7-122">Description</span></span>
- <span data-ttu-id="181f7-123">Palavras-chave de SEO</span><span class="sxs-lookup"><span data-stu-id="181f7-123">SEO keywords</span></span>
- <span data-ttu-id="181f7-124">Etiquetas Aria</span><span class="sxs-lookup"><span data-stu-id="181f7-124">Aria labels</span></span>
- <span data-ttu-id="181f7-125">noindex</span><span class="sxs-lookup"><span data-stu-id="181f7-125">noindex</span></span>
- <span data-ttu-id="181f7-126">nofollow</span><span class="sxs-lookup"><span data-stu-id="181f7-126">nofollow</span></span>
- <span data-ttu-id="181f7-127">noarchive</span><span class="sxs-lookup"><span data-stu-id="181f7-127">noarchive</span></span>
- <span data-ttu-id="181f7-128">nocache</span><span class="sxs-lookup"><span data-stu-id="181f7-128">nocache</span></span>
- <span data-ttu-id="181f7-129">noOpenDirectoryProject</span><span class="sxs-lookup"><span data-stu-id="181f7-129">noOpenDirectoryProject</span></span>
- <span data-ttu-id="181f7-130">nosnippet</span><span class="sxs-lookup"><span data-stu-id="181f7-130">nosnippet</span></span>
- <span data-ttu-id="181f7-131">noImageIndex</span><span class="sxs-lookup"><span data-stu-id="181f7-131">noImageIndex</span></span>
- <span data-ttu-id="181f7-132">unavailableAfter</span><span class="sxs-lookup"><span data-stu-id="181f7-132">unavailableAfter</span></span>

### <a name="modify-page-metadata"></a><span data-ttu-id="181f7-133">Modificar metadados da página</span><span class="sxs-lookup"><span data-stu-id="181f7-133">Modify page metadata</span></span>

<span data-ttu-id="181f7-134">Para modificar os metadados da página, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="181f7-134">To modify page metadata, follow these steps.</span></span>

1. <span data-ttu-id="181f7-135">Em **Sites**, selecione o **Fabrikam** (ou o nome do seu site).</span><span class="sxs-lookup"><span data-stu-id="181f7-135">Under **Sites**, select the **Fabrikam** (or the name of your site).</span></span>
1. <span data-ttu-id="181f7-136">No painel de navegação à esquerda, selecione **Páginas**.</span><span class="sxs-lookup"><span data-stu-id="181f7-136">In the navigation pane on the left, select **Pages**.</span></span>
1. <span data-ttu-id="181f7-137">Selecione a home page para abri-la no editor de páginas.</span><span class="sxs-lookup"><span data-stu-id="181f7-137">Select the home page to open it in the page editor.</span></span>
1. <span data-ttu-id="181f7-138">Na barra de comandos, selecione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="181f7-138">On the command bar, select **Edit**.</span></span>
1. <span data-ttu-id="181f7-139">No painel de propriedades à direita, expanda **Marcas meta padrão**.</span><span class="sxs-lookup"><span data-stu-id="181f7-139">In the properties pane on the right, expand **Default metatags**.</span></span>
1. <span data-ttu-id="181f7-140">Para adicionar uma nova marca meta, selecione **Adicionar** e informe a marca no campo.</span><span class="sxs-lookup"><span data-stu-id="181f7-140">To add a new metatag, select **Add**, and then enter the tag in the field.</span></span> <span data-ttu-id="181f7-141">Para remover uma marca meta existente, selecione o símbolo da lata de lixo à direita dela.</span><span class="sxs-lookup"><span data-stu-id="181f7-141">To remove an existing metatag, select the trash can symbol to the right of it.</span></span>
1. <span data-ttu-id="181f7-142">Selecione **Salvar** e **Finalizar edição**.</span><span class="sxs-lookup"><span data-stu-id="181f7-142">Select **Save**, and then select **Finish editing**.</span></span>
1. <span data-ttu-id="181f7-143">No campo **Comentários**, insira **Marcas meta atualizadas** e depois selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="181f7-143">In the **Comments** field, enter **Updated metatags**, and then select **OK**.</span></span>
1. <span data-ttu-id="181f7-144">Selecione **Visualizar** para exibir a página.</span><span class="sxs-lookup"><span data-stu-id="181f7-144">Select **Preview** to preview your page.</span></span> <span data-ttu-id="181f7-145">Quando terminar, feche a guia de visualização para retornar à ferramenta de criação.</span><span class="sxs-lookup"><span data-stu-id="181f7-145">When you've finished, close the preview tab to return to the authoring tool.</span></span>
1. <span data-ttu-id="181f7-146">Selecione **Publicar**.</span><span class="sxs-lookup"><span data-stu-id="181f7-146">Select **Publish**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="181f7-147">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="181f7-147">Additional resources</span></span>

[<span data-ttu-id="181f7-148">Modificar uma página de site existente</span><span class="sxs-lookup"><span data-stu-id="181f7-148">Modify an existing site page</span></span>](modify-existing-page.md)

[<span data-ttu-id="181f7-149">Adicionar uma nova página do site</span><span class="sxs-lookup"><span data-stu-id="181f7-149">Add a new site page</span></span>](add-new-page.md)

[<span data-ttu-id="181f7-150">Selecionar layouts de página</span><span class="sxs-lookup"><span data-stu-id="181f7-150">Select page layouts</span></span>](select-page-layouts.md)

[<span data-ttu-id="181f7-151">Salvar, visualizar, e publicar uma página</span><span class="sxs-lookup"><span data-stu-id="181f7-151">Save, preview, and publish a page</span></span>](save-preview-publish-page.md)

[<span data-ttu-id="181f7-152">Enriquecer uma página de produto</span><span class="sxs-lookup"><span data-stu-id="181f7-152">Enrich a product page</span></span>](enrich-product-page.md)

[<span data-ttu-id="181f7-153">Enriquecer uma página de aterrissagem da categoria</span><span class="sxs-lookup"><span data-stu-id="181f7-153">Enrich a category landing page</span></span>](enrich-category-page.md)

[<span data-ttu-id="181f7-154">Verificar acessibilidade do conteúdo da página</span><span class="sxs-lookup"><span data-stu-id="181f7-154">Verify page content accessibility</span></span>](verify-accessibility.md)

[<span data-ttu-id="181f7-155">Criar páginas dinâmicas de comércio eletrônico com base nos parâmetros da URL</span><span class="sxs-lookup"><span data-stu-id="181f7-155">Create dynamic e-commerce pages based on URL parameters</span></span>](create-dynamic-pages.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
