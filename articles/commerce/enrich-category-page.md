---
title: Enriquecer uma página de aterrissagem da categoria
description: Este tópico cobre o enriquecimento de páginas de categoria no Dynamics 365 Commerce.
author: v-chgri
ms.date: 04/14/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: asharchw
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 5e18439fc0e91619cade33b83b87be0d5c4d1040
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5799002"
---
# <a name="enrich-a-category-landing-page"></a><span data-ttu-id="63c54-103">Enriquecer uma página de aterrissagem da categoria</span><span class="sxs-lookup"><span data-stu-id="63c54-103">Enrich a category landing page</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="63c54-104">Este tópico cobre o enriquecimento de páginas de categoria no Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="63c54-104">This topic covers the enrichment of category pages in Dynamics 365 Commerce.</span></span>

<span data-ttu-id="63c54-105">Comércio fornece uma página de aterrissagem de categoria padrão usada quando dados de categoria são mostrados.</span><span class="sxs-lookup"><span data-stu-id="63c54-105">Commerce provides a default category landing page that is used when category data is shown.</span></span> <span data-ttu-id="63c54-106">Uma página da categoria padrão contém elementos necessários, como os refinadores, posicionamento de produto categorizado, classificação de opções, um resumo de escolhas e controles de paginação.</span><span class="sxs-lookup"><span data-stu-id="63c54-106">A default category page contains required elements, such as refiners, categorized product placement, sorting options, a choice summary, and pagination controls.</span></span> 

<span data-ttu-id="63c54-107">Entretanto, em vez de usar a página da categoria padrão, você poderá usar uma página de aterrissagem de categoria "enriquecida" que tem mais conteúdo e mais elementos específicos.</span><span class="sxs-lookup"><span data-stu-id="63c54-107">However, instead of using the default category page, you might want to use an "enriched" category landing page that has more content and more specific elements.</span></span> <span data-ttu-id="63c54-108">Um enriquecimento típico pode envolver adicionar conteúdo de marketing específico do conteúdo à página de categoria.</span><span class="sxs-lookup"><span data-stu-id="63c54-108">A typical enrichment might involve adding category-specific marketing content to the category page.</span></span> <span data-ttu-id="63c54-109">O conteúdo deve incluir o posicionamento de produtos entre categoria para fins de venda, listas de editorial, imagens, vídeos e outro texto.</span><span class="sxs-lookup"><span data-stu-id="63c54-109">This content might include cross-category product placement for cross-sell purposes, editorial lists, images, videos, and other text.</span></span> <span data-ttu-id="63c54-110">Você também pode modificar a página da categoria padrão ou definir uma página diferente de categoria para uma categoria específica.</span><span class="sxs-lookup"><span data-stu-id="63c54-110">You can either modify the default category page or define a different category page for a specific category.</span></span>

![Página de aterrissagem da categoria enriquecida](./media/CategoryLandingPages.png)

<span data-ttu-id="63c54-112">Na construtor de sites do Commerce, a página **Produtos** inclui uma lista de categorias do canal que são atribuídas ao site.</span><span class="sxs-lookup"><span data-stu-id="63c54-112">In Commerce site builder, the **Products** page includes a list of categories from the channel that are assigned to the site.</span></span> <span data-ttu-id="63c54-113">Se o status **Enriquecido** é selecionado para uma página de categoria, essa página de categoria foi enriquecida.</span><span class="sxs-lookup"><span data-stu-id="63c54-113">If the **Enriched** status is selected for a category page, that category page has been enriched.</span></span> <span data-ttu-id="63c54-114">Se não, a página da categoria padrão e o conteúdo são usados para a categoria.</span><span class="sxs-lookup"><span data-stu-id="63c54-114">Otherwise, the default category page and content are used for the category.</span></span> <span data-ttu-id="63c54-115">Você pode visualizar as páginas de categoria de produto enriquecida para a categoria selecionando o nome da categoria.</span><span class="sxs-lookup"><span data-stu-id="63c54-115">You can preview both the enriched and non-enriched category pages for a category by selecting the category name.</span></span>

<span data-ttu-id="63c54-116">Para enriquecer uma pagina de categoria, siga este procedimento.</span><span class="sxs-lookup"><span data-stu-id="63c54-116">To enrich a category page, do the following.</span></span>

1. <span data-ttu-id="63c54-117">Na página **Produtos**, selecione o nome da categoria para a qual deseja enriquecer a página da categoria.</span><span class="sxs-lookup"><span data-stu-id="63c54-117">On the **Products** page, select the name of the category for which you want to enrich the category page.</span></span> <span data-ttu-id="63c54-118">A página da categoria padrão para a categoria selecionada é aberta no editor de páginas.</span><span class="sxs-lookup"><span data-stu-id="63c54-118">The default category page for the selected category is opened in the page editor.</span></span>
2. <span data-ttu-id="63c54-119">Selecione **Enriquecer página de categoria**.</span><span class="sxs-lookup"><span data-stu-id="63c54-119">Select **Enrich category page**.</span></span>
3. <span data-ttu-id="63c54-120">Selecione um modelo para a página de categoria enriquecida.</span><span class="sxs-lookup"><span data-stu-id="63c54-120">Select a template for the enriched category page.</span></span> <span data-ttu-id="63c54-121">Se estiver fazendo apenas alterações menores, selecione a página da categoria padrão.</span><span class="sxs-lookup"><span data-stu-id="63c54-121">If you're making only minor changes, you can select the default category page.</span></span> <span data-ttu-id="63c54-122">Alternativamente, você pode selecionar um modelo específico de página de categoria.</span><span class="sxs-lookup"><span data-stu-id="63c54-122">Alternatively, you can select a specific category page template.</span></span> <span data-ttu-id="63c54-123">Quando você seleciona o modelo, o editor de páginas é aberto e o modelo selecionado é usado para criar uma nova página de categoria para a categoria selecionada.</span><span class="sxs-lookup"><span data-stu-id="63c54-123">When you select the template, the page editor is opened, and the selected template is used to create a new category page for the selected category.</span></span> <span data-ttu-id="63c54-124">A página realizará check-out, e agora você pode fazer as alterações.</span><span class="sxs-lookup"><span data-stu-id="63c54-124">The page is checked out to you, and you can now make your changes.</span></span>

> [!NOTE]
> <span data-ttu-id="63c54-125">Módulos que usam dados de especificação de categoria usam os dados da categoria selecionada.</span><span class="sxs-lookup"><span data-stu-id="63c54-125">Modules that use category specification data use the data from your selected category.</span></span> <span data-ttu-id="63c54-126">As configurações do modelo selecionado determinam as alterações que você pode fazer.</span><span class="sxs-lookup"><span data-stu-id="63c54-126">The settings of the template that you select determine the changes that you can make.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="63c54-127">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="63c54-127">Additional resources</span></span>

[<span data-ttu-id="63c54-128">Modificar uma página de site existente</span><span class="sxs-lookup"><span data-stu-id="63c54-128">Modify an existing site page</span></span>](modify-existing-page.md)

[<span data-ttu-id="63c54-129">Adicionar uma nova página do site</span><span class="sxs-lookup"><span data-stu-id="63c54-129">Add a new site page</span></span>](add-new-page.md)

[<span data-ttu-id="63c54-130">Selecionar layouts de página</span><span class="sxs-lookup"><span data-stu-id="63c54-130">Select page layouts</span></span>](select-page-layouts.md)

[<span data-ttu-id="63c54-131">Gerenciar metadados de SEO</span><span class="sxs-lookup"><span data-stu-id="63c54-131">Manage SEO metadata</span></span>](manage-seo-metadata.md)

[<span data-ttu-id="63c54-132">Salvar, visualizar, e publicar uma página</span><span class="sxs-lookup"><span data-stu-id="63c54-132">Save, preview, and publish a page</span></span>](save-preview-publish-page.md)

[<span data-ttu-id="63c54-133">Enriquecer uma página de produto</span><span class="sxs-lookup"><span data-stu-id="63c54-133">Enrich a product page</span></span>](enrich-product-page.md)

[<span data-ttu-id="63c54-134">Verificar acessibilidade do conteúdo da página</span><span class="sxs-lookup"><span data-stu-id="63c54-134">Verify page content accessibility</span></span>](verify-accessibility.md)

[<span data-ttu-id="63c54-135">Criar páginas dinâmicas de comércio eletrônico com base nos parâmetros da URL</span><span class="sxs-lookup"><span data-stu-id="63c54-135">Create dynamic e-commerce pages based on URL parameters</span></span>](create-dynamic-pages.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
