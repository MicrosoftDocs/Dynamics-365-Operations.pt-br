---
title: Gerenciar metadados de SEO
description: Este tópico descreve como gerenciar metadados da otimização do mecanismo de pesquisa (SEO) no Microsoft Dynamics 365 Commerce.
author: psimolin
manager: annbe
ms.date: 04/14/2020
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
ms.openlocfilehash: 74229628e48ffb8ac974acd868e325eeca77d91e
ms.sourcegitcommit: 7a1d01122790b904e2d96a7ea9f1d003392358a6
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/17/2020
ms.locfileid: "3270038"
---
# <a name="manage-seo-metadata"></a><span data-ttu-id="c2ccf-103">Gerenciar metadados de SEO</span><span class="sxs-lookup"><span data-stu-id="c2ccf-103">Manage SEO metadata</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="c2ccf-104">Este tópico descreve como gerenciar metadados da otimização do mecanismo de pesquisa (SEO) no Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="c2ccf-104">This topic describes how to manage search engine optimization (SEO) metadata in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="c2ccf-105">Visão geral</span><span class="sxs-lookup"><span data-stu-id="c2ccf-105">Overview</span></span>

<span data-ttu-id="c2ccf-106">Os metadados de SEO para um site podem ser gerenciados usando mapas do site e metadados da página.</span><span class="sxs-lookup"><span data-stu-id="c2ccf-106">SEO metadata for a site can be managed by using site maps and page metadata.</span></span>
    
## <a name="site-maps"></a><span data-ttu-id="c2ccf-107">Mapas do site</span><span class="sxs-lookup"><span data-stu-id="c2ccf-107">Site maps</span></span>

<span data-ttu-id="c2ccf-108">Um mapa do site é uma lista legível por máquina, no formato XML, das páginas do seu site.</span><span class="sxs-lookup"><span data-stu-id="c2ccf-108">A site map is a machine-readable list, in XML format, of the pages on your website.</span></span> <span data-ttu-id="c2ccf-109">Ele deve ser consumido pelos mecanismos de pesquisa, para que eles possam fornecer melhores resultados de pesquisa em seu site.</span><span class="sxs-lookup"><span data-stu-id="c2ccf-109">It's intended to be consumed by search engines, so that they can provide better search results from your site.</span></span> <span data-ttu-id="c2ccf-110">Os mapas do site podem ser incorporados manualmente pelos mecanismos de pesquisa ou publicados em um arquivo robots.txt.</span><span class="sxs-lookup"><span data-stu-id="c2ccf-110">Site maps can be manually ingested by search engines or published in a robots.txt file.</span></span>

<span data-ttu-id="c2ccf-111">O Dynamics 365 Commerce oferece suporte à geração automática de mapas de site.</span><span class="sxs-lookup"><span data-stu-id="c2ccf-111">Dynamics 365 Commerce supports automatic generation of site maps.</span></span> <span data-ttu-id="c2ccf-112">Os mapas de site são atualizados automaticamente quando as páginas são publicadas e as publicações canceladas.</span><span class="sxs-lookup"><span data-stu-id="c2ccf-112">Site maps are automatically updated when pages are published and unpublished.</span></span>

### <a name="turn-on-site-map-generation"></a><span data-ttu-id="c2ccf-113">Ative a geração do mapa do site</span><span class="sxs-lookup"><span data-stu-id="c2ccf-113">Turn on site map generation</span></span>

1. <span data-ttu-id="c2ccf-114">Conectar-se à ferramenta de criação.</span><span class="sxs-lookup"><span data-stu-id="c2ccf-114">Sign in to the authoring tool.</span></span>
1. <span data-ttu-id="c2ccf-115">Em **Sites**, selecione **Fabrikam** (ou o nome do seu site).</span><span class="sxs-lookup"><span data-stu-id="c2ccf-115">Under **Sites**, select **Fabrikam** (or the name of your site).</span></span>
1. <span data-ttu-id="c2ccf-116">No painel de navegação à esquerda, selecione **Gerenciamento de sites**.</span><span class="sxs-lookup"><span data-stu-id="c2ccf-116">In the navigation pane on the left, select **Site Management**.</span></span>
1. <span data-ttu-id="c2ccf-117">Verifique se a opção **Mapas de site habilitados** está ativada.</span><span class="sxs-lookup"><span data-stu-id="c2ccf-117">Make sure that the **Site maps enabled** option is turned on.</span></span>

## <a name="page-metadata"></a><span data-ttu-id="c2ccf-118">Metadados da página</span><span class="sxs-lookup"><span data-stu-id="c2ccf-118">Page metadata</span></span>

<span data-ttu-id="c2ccf-119">O Dynamics 365 Commerce permite gerenciar metadados de SEO para páginas individuais.</span><span class="sxs-lookup"><span data-stu-id="c2ccf-119">Dynamics 365 Commerce lets you manage SEO metadata for individual pages.</span></span> <span data-ttu-id="c2ccf-120">É possível exibir e modificar estas informações na seção **Propriedades de SEO** de um contêiner de página.</span><span class="sxs-lookup"><span data-stu-id="c2ccf-120">You can view and modify this information in the **SEO Properties** section of a page container.</span></span> <span data-ttu-id="c2ccf-121">As seguintes propriedades de metadados de SEO são suportadas:</span><span class="sxs-lookup"><span data-stu-id="c2ccf-121">The following SEO metadata properties are supported:</span></span>

- <span data-ttu-id="c2ccf-122">Cargo</span><span class="sxs-lookup"><span data-stu-id="c2ccf-122">Title</span></span>
- <span data-ttu-id="c2ccf-123">Descrição</span><span class="sxs-lookup"><span data-stu-id="c2ccf-123">Description</span></span>
- <span data-ttu-id="c2ccf-124">Palavras-chave de SEO</span><span class="sxs-lookup"><span data-stu-id="c2ccf-124">SEO keywords</span></span>
- <span data-ttu-id="c2ccf-125">Etiquetas Aria</span><span class="sxs-lookup"><span data-stu-id="c2ccf-125">Aria labels</span></span>
- <span data-ttu-id="c2ccf-126">noindex</span><span class="sxs-lookup"><span data-stu-id="c2ccf-126">noindex</span></span>
- <span data-ttu-id="c2ccf-127">nofollow</span><span class="sxs-lookup"><span data-stu-id="c2ccf-127">nofollow</span></span>
- <span data-ttu-id="c2ccf-128">noarchive</span><span class="sxs-lookup"><span data-stu-id="c2ccf-128">noarchive</span></span>
- <span data-ttu-id="c2ccf-129">nocache</span><span class="sxs-lookup"><span data-stu-id="c2ccf-129">nocache</span></span>
- <span data-ttu-id="c2ccf-130">noOpenDirectoryProject</span><span class="sxs-lookup"><span data-stu-id="c2ccf-130">noOpenDirectoryProject</span></span>
- <span data-ttu-id="c2ccf-131">nosnippet</span><span class="sxs-lookup"><span data-stu-id="c2ccf-131">nosnippet</span></span>
- <span data-ttu-id="c2ccf-132">noImageIndex</span><span class="sxs-lookup"><span data-stu-id="c2ccf-132">noImageIndex</span></span>
- <span data-ttu-id="c2ccf-133">unavailableAfter</span><span class="sxs-lookup"><span data-stu-id="c2ccf-133">unavailableAfter</span></span>

### <a name="modify-page-metadata"></a><span data-ttu-id="c2ccf-134">Modificar metadados da página</span><span class="sxs-lookup"><span data-stu-id="c2ccf-134">Modify page metadata</span></span>

<span data-ttu-id="c2ccf-135">Para modificar os metadados da página, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="c2ccf-135">To modify page metadata, follow these steps.</span></span>

1. <span data-ttu-id="c2ccf-136">Em **Sites**, selecione o **Fabrikam** (ou o nome do seu site).</span><span class="sxs-lookup"><span data-stu-id="c2ccf-136">Under **Sites**, select the **Fabrikam** (or the name of your site).</span></span>
1. <span data-ttu-id="c2ccf-137">No painel de navegação à esquerda, selecione **Páginas**.</span><span class="sxs-lookup"><span data-stu-id="c2ccf-137">In the navigation pane on the left, select **Pages**.</span></span>
1. <span data-ttu-id="c2ccf-138">Selecione a home page para abri-la no editor de páginas.</span><span class="sxs-lookup"><span data-stu-id="c2ccf-138">Select the home page to open it in the page editor.</span></span>
1. <span data-ttu-id="c2ccf-139">Na barra de comandos, selecione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="c2ccf-139">On the command bar, select **Edit**.</span></span>
1. <span data-ttu-id="c2ccf-140">No painel de propriedades à direita, expanda **Marcas meta padrão**.</span><span class="sxs-lookup"><span data-stu-id="c2ccf-140">In the properties pane on the right, expand **Default metatags**.</span></span>
1. <span data-ttu-id="c2ccf-141">Para adicionar uma nova marca meta, selecione **Adicionar** e informe a marca no campo.</span><span class="sxs-lookup"><span data-stu-id="c2ccf-141">To add a new metatag, select **Add**, and then enter the tag in the field.</span></span> <span data-ttu-id="c2ccf-142">Para remover uma marca meta existente, selecione o símbolo da lata de lixo à direita dela.</span><span class="sxs-lookup"><span data-stu-id="c2ccf-142">To remove an existing metatag, select the trash can symbol to the right of it.</span></span>
1. <span data-ttu-id="c2ccf-143">Selecione **Salvar** e **Finalizar edição**.</span><span class="sxs-lookup"><span data-stu-id="c2ccf-143">Select **Save**, and then select **Finish editing**.</span></span>
1. <span data-ttu-id="c2ccf-144">No campo **Comentários**, insira **Marcas meta atualizadas** e depois selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="c2ccf-144">In the **Comments** field, enter **Updated metatags**, and then select **OK**.</span></span>
1. <span data-ttu-id="c2ccf-145">Selecione **Visualizar** para exibir a página.</span><span class="sxs-lookup"><span data-stu-id="c2ccf-145">Select **Preview** to preview your page.</span></span> <span data-ttu-id="c2ccf-146">Quando terminar, feche a guia de visualização para retornar à ferramenta de criação.</span><span class="sxs-lookup"><span data-stu-id="c2ccf-146">When you've finished, close the preview tab to return to the authoring tool.</span></span>
1. <span data-ttu-id="c2ccf-147">Selecione **Publicar**.</span><span class="sxs-lookup"><span data-stu-id="c2ccf-147">Select **Publish**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="c2ccf-148">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="c2ccf-148">Additional resources</span></span>

[<span data-ttu-id="c2ccf-149">Modificar uma página de site existente</span><span class="sxs-lookup"><span data-stu-id="c2ccf-149">Modify an existing site page</span></span>](modify-existing-page.md)

[<span data-ttu-id="c2ccf-150">Adicionar uma nova página do site</span><span class="sxs-lookup"><span data-stu-id="c2ccf-150">Add a new site page</span></span>](add-new-page.md)

[<span data-ttu-id="c2ccf-151">Selecionar layouts de página</span><span class="sxs-lookup"><span data-stu-id="c2ccf-151">Select page layouts</span></span>](select-page-layouts.md)

[<span data-ttu-id="c2ccf-152">Salvar, visualizar, e publicar uma página</span><span class="sxs-lookup"><span data-stu-id="c2ccf-152">Save, preview, and publish a page</span></span>](save-preview-publish-page.md)

[<span data-ttu-id="c2ccf-153">Enriquecer uma página de produto</span><span class="sxs-lookup"><span data-stu-id="c2ccf-153">Enrich a product page</span></span>](enrich-product-page.md)

[<span data-ttu-id="c2ccf-154">Enriquecer uma página de aterrissagem da categoria</span><span class="sxs-lookup"><span data-stu-id="c2ccf-154">Enrich a category landing page</span></span>](enrich-category-page.md)

[<span data-ttu-id="c2ccf-155">Verificar acessibilidade de conteúdo da página</span><span class="sxs-lookup"><span data-stu-id="c2ccf-155">Verify page content accessibility</span></span>](verify-accessibility.md)
