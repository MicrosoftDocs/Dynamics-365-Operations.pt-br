---
title: Enriquecer uma página de aterrissagem da categoria
description: Este tópico cobre o enriquecimento de páginas de categoria no Dynamics 365 Commerce.
author: v-chgri
manager: annbe
ms.date: 04/14/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: asharchw
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: fbcf6ec60723b726e022b4e17bbde4c903e5cb57
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5238765"
---
# <a name="enrich-a-category-landing-page"></a><span data-ttu-id="c7724-103">Enriquecer uma página de aterrissagem da categoria</span><span class="sxs-lookup"><span data-stu-id="c7724-103">Enrich a category landing page</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="c7724-104">Este tópico cobre o enriquecimento de páginas de categoria no Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="c7724-104">This topic covers the enrichment of category pages in Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="c7724-105">Visão geral</span><span class="sxs-lookup"><span data-stu-id="c7724-105">Overview</span></span>

<span data-ttu-id="c7724-106">Comércio fornece uma página de aterrissagem de categoria padrão usada quando dados de categoria são mostrados.</span><span class="sxs-lookup"><span data-stu-id="c7724-106">Commerce provides a default category landing page that is used when category data is shown.</span></span> <span data-ttu-id="c7724-107">Uma página da categoria padrão contém elementos necessários, como os refinadores, posicionamento de produto categorizado, classificação de opções, um resumo de escolhas e controles de paginação.</span><span class="sxs-lookup"><span data-stu-id="c7724-107">A default category page contains required elements, such as refiners, categorized product placement, sorting options, a choice summary, and pagination controls.</span></span> 

<span data-ttu-id="c7724-108">Entretanto, em vez de usar a página da categoria padrão, você poderá usar uma página de aterrissagem de categoria "enriquecida" que tem mais conteúdo e mais elementos específicos.</span><span class="sxs-lookup"><span data-stu-id="c7724-108">However, instead of using the default category page, you might want to use an "enriched" category landing page that has more content and more specific elements.</span></span> <span data-ttu-id="c7724-109">Um enriquecimento típico pode envolver adicionar conteúdo de marketing específico do conteúdo à página de categoria.</span><span class="sxs-lookup"><span data-stu-id="c7724-109">A typical enrichment might involve adding category-specific marketing content to the category page.</span></span> <span data-ttu-id="c7724-110">O conteúdo deve incluir o posicionamento de produtos entre categoria para fins de venda, listas de editorial, imagens, vídeos e outro texto.</span><span class="sxs-lookup"><span data-stu-id="c7724-110">This content might include cross-category product placement for cross-sell purposes, editorial lists, images, videos, and other text.</span></span> <span data-ttu-id="c7724-111">Você também pode modificar a página da categoria padrão ou definir uma página diferente de categoria para uma categoria específica.</span><span class="sxs-lookup"><span data-stu-id="c7724-111">You can either modify the default category page or define a different category page for a specific category.</span></span>

![Página de aterrissagem da categoria enriquecida](./media/CategoryLandingPages.png)

<span data-ttu-id="c7724-113">Na construtor de sites do Commerce, a página **Produtos** inclui uma lista de categorias do canal que são atribuídas ao site.</span><span class="sxs-lookup"><span data-stu-id="c7724-113">In Commerce site builder, the **Products** page includes a list of categories from the channel that are assigned to the site.</span></span> <span data-ttu-id="c7724-114">Se o status **Enriquecido** é selecionado para uma página de categoria, essa página de categoria foi enriquecida.</span><span class="sxs-lookup"><span data-stu-id="c7724-114">If the **Enriched** status is selected for a category page, that category page has been enriched.</span></span> <span data-ttu-id="c7724-115">Se não, a página da categoria padrão e o conteúdo são usados para a categoria.</span><span class="sxs-lookup"><span data-stu-id="c7724-115">Otherwise, the default category page and content are used for the category.</span></span> <span data-ttu-id="c7724-116">Você pode visualizar as páginas de categoria de produto enriquecida para a categoria selecionando o nome da categoria.</span><span class="sxs-lookup"><span data-stu-id="c7724-116">You can preview both the enriched and non-enriched category pages for a category by selecting the category name.</span></span>

<span data-ttu-id="c7724-117">Para enriquecer uma pagina de categoria, siga este procedimento.</span><span class="sxs-lookup"><span data-stu-id="c7724-117">To enrich a category page, do the following.</span></span>

1. <span data-ttu-id="c7724-118">Na página **Produtos**, selecione o nome da categoria para a qual deseja enriquecer a página da categoria.</span><span class="sxs-lookup"><span data-stu-id="c7724-118">On the **Products** page, select the name of the category for which you want to enrich the category page.</span></span> <span data-ttu-id="c7724-119">A página da categoria padrão para a categoria selecionada é aberta no editor de páginas.</span><span class="sxs-lookup"><span data-stu-id="c7724-119">The default category page for the selected category is opened in the page editor.</span></span>
2. <span data-ttu-id="c7724-120">Selecione **Enriquecer página de categoria**.</span><span class="sxs-lookup"><span data-stu-id="c7724-120">Select **Enrich category page**.</span></span>
3. <span data-ttu-id="c7724-121">Selecione um modelo para a página de categoria enriquecida.</span><span class="sxs-lookup"><span data-stu-id="c7724-121">Select a template for the enriched category page.</span></span> <span data-ttu-id="c7724-122">Se estiver fazendo apenas alterações menores, selecione a página da categoria padrão.</span><span class="sxs-lookup"><span data-stu-id="c7724-122">If you're making only minor changes, you can select the default category page.</span></span> <span data-ttu-id="c7724-123">Alternativamente, você pode selecionar um modelo específico de página de categoria.</span><span class="sxs-lookup"><span data-stu-id="c7724-123">Alternatively, you can select a specific category page template.</span></span> <span data-ttu-id="c7724-124">Quando você seleciona o modelo, o editor de páginas é aberto e o modelo selecionado é usado para criar uma nova página de categoria para a categoria selecionada.</span><span class="sxs-lookup"><span data-stu-id="c7724-124">When you select the template, the page editor is opened, and the selected template is used to create a new category page for the selected category.</span></span> <span data-ttu-id="c7724-125">A página realizará check-out, e agora você pode fazer as alterações.</span><span class="sxs-lookup"><span data-stu-id="c7724-125">The page is checked out to you, and you can now make your changes.</span></span>

> [!NOTE]
> <span data-ttu-id="c7724-126">Módulos que usam dados de especificação de categoria usam os dados da categoria selecionada.</span><span class="sxs-lookup"><span data-stu-id="c7724-126">Modules that use category specification data use the data from your selected category.</span></span> <span data-ttu-id="c7724-127">As configurações do modelo selecionado determinam as alterações que você pode fazer.</span><span class="sxs-lookup"><span data-stu-id="c7724-127">The settings of the template that you select determine the changes that you can make.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="c7724-128">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="c7724-128">Additional resources</span></span>

[<span data-ttu-id="c7724-129">Modificar uma página de site existente</span><span class="sxs-lookup"><span data-stu-id="c7724-129">Modify an existing site page</span></span>](modify-existing-page.md)

[<span data-ttu-id="c7724-130">Adicionar uma nova página do site</span><span class="sxs-lookup"><span data-stu-id="c7724-130">Add a new site page</span></span>](add-new-page.md)

[<span data-ttu-id="c7724-131">Selecionar layouts de página</span><span class="sxs-lookup"><span data-stu-id="c7724-131">Select page layouts</span></span>](select-page-layouts.md)

[<span data-ttu-id="c7724-132">Gerenciar metadados de SEO</span><span class="sxs-lookup"><span data-stu-id="c7724-132">Manage SEO metadata</span></span>](manage-seo-metadata.md)

[<span data-ttu-id="c7724-133">Salvar, visualizar, e publicar uma página</span><span class="sxs-lookup"><span data-stu-id="c7724-133">Save, preview, and publish a page</span></span>](save-preview-publish-page.md)

[<span data-ttu-id="c7724-134">Enriquecer uma página de produto</span><span class="sxs-lookup"><span data-stu-id="c7724-134">Enrich a product page</span></span>](enrich-product-page.md)

[<span data-ttu-id="c7724-135">Verificar acessibilidade do conteúdo da página</span><span class="sxs-lookup"><span data-stu-id="c7724-135">Verify page content accessibility</span></span>](verify-accessibility.md)

[<span data-ttu-id="c7724-136">Criar páginas dinâmicas de comércio eletrônico com base nos parâmetros da URL</span><span class="sxs-lookup"><span data-stu-id="c7724-136">Create dynamic e-commerce pages based on URL parameters</span></span>](create-dynamic-pages.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]