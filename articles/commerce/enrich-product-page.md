---
title: Enriquecer uma página de produto
description: Este tópico descreve como enriquecer uma página de produto no Microsoft Dynamics 365 Commerce.
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
ms.openlocfilehash: 12508a80c440894ec6e2073b5e550846480e6c45
ms.sourcegitcommit: 7a1d01122790b904e2d96a7ea9f1d003392358a6
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/17/2020
ms.locfileid: "3269811"
---
# <a name="enrich-a-product-page"></a><span data-ttu-id="4ffb4-103">Enriquecer uma página de produto</span><span class="sxs-lookup"><span data-stu-id="4ffb4-103">Enrich a product page</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="4ffb4-104">Este tópico descreve como enriquecer uma página de produto no Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="4ffb4-104">This topic describes how to enrich a product page in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="4ffb4-105">Visão geral</span><span class="sxs-lookup"><span data-stu-id="4ffb4-105">Overview</span></span>

<span data-ttu-id="4ffb4-106">Por padrão, seu site usa uma página genérica para exibir dados de produto.</span><span class="sxs-lookup"><span data-stu-id="4ffb4-106">By default, your site uses a generic page to show product data.</span></span> <span data-ttu-id="4ffb4-107">Essa página inclui informações básicas sobre o produto e controles necessários para vendê-lo.</span><span class="sxs-lookup"><span data-stu-id="4ffb4-107">This page includes the basic information about the product and the controls that are required to sell it.</span></span> <span data-ttu-id="4ffb4-108">Entretanto, você pode complementar as informações provenientes da Unidade de Escala do Commerce com imagens adicionais ou texto para um produto específico.</span><span class="sxs-lookup"><span data-stu-id="4ffb4-108">However, you can supplement the information that comes from the Commerce Scale Unit with additional images or text for a specific product.</span></span> <span data-ttu-id="4ffb4-109">Esse processo é conhecido como enriquecimento da página de produto.</span><span class="sxs-lookup"><span data-stu-id="4ffb4-109">This process is known as enriching the product page.</span></span>

<span data-ttu-id="4ffb4-110">Em muitos casos, você desejará usar conteúdo adicional específico de seus produtos.</span><span class="sxs-lookup"><span data-stu-id="4ffb4-110">In many cases, you will want to use specific additional content for your products.</span></span> <span data-ttu-id="4ffb4-111">Ao acessar **Retail e Commerce** na ferramenta de criação, você verá uma lista de produtos do canal atribuído ao site.</span><span class="sxs-lookup"><span data-stu-id="4ffb4-111">When you go to **Retail and Commerce** in the authoring tool, you will see a list of products from the channel that is assigned to the site.</span></span> <span data-ttu-id="4ffb4-112">Na lista, a coluna **Enriquecido** indica se a página do produto de um produto foi enriquecida.</span><span class="sxs-lookup"><span data-stu-id="4ffb4-112">In this list, the **Enriched** column indicates whether the product page for a product has been enriched.</span></span> <span data-ttu-id="4ffb4-113">Se uma marca de seleção é exibida na coluna, uma página enriquecida de produto existe para o produto.</span><span class="sxs-lookup"><span data-stu-id="4ffb4-113">If a check mark appears in the column, an enriched product page exists for the product.</span></span> <span data-ttu-id="4ffb4-114">Se nenhuma marca de seleção for exibida, a página de produto padrão e o conteúdo são usados para o produto.</span><span class="sxs-lookup"><span data-stu-id="4ffb4-114">If no check mark appears, the default product page and content are used for the product.</span></span> <span data-ttu-id="4ffb4-115">Você pode visualizar as páginas de produto enriquecida e não enriquecida selecionando um nome de produto na lista.</span><span class="sxs-lookup"><span data-stu-id="4ffb4-115">You can preview both enriched and non-enriched product pages by selecting a product name in the list.</span></span>

## <a name="enrich-a-product-page"></a><span data-ttu-id="4ffb4-116">Enriquecer uma página de produto</span><span class="sxs-lookup"><span data-stu-id="4ffb4-116">Enrich a product page</span></span>

<span data-ttu-id="4ffb4-117">Para enriquecer uma página de produto, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="4ffb4-117">To enrich a product page, follow these steps.</span></span>

1. <span data-ttu-id="4ffb4-118">Em **Sites**, selecione **Fabrikam** (ou o nome do seu site).</span><span class="sxs-lookup"><span data-stu-id="4ffb4-118">Under **Sites**, select **Fabrikam** (or the name of your site).</span></span>
1. <span data-ttu-id="4ffb4-119">No painel de navegação à esquerda, selecione **Produtos**.</span><span class="sxs-lookup"><span data-stu-id="4ffb4-119">In the navigation pane on the left, select **Products**.</span></span>
1. <span data-ttu-id="4ffb4-120">Selecione todos os produtos que não têm uma página de produto enriquecida.</span><span class="sxs-lookup"><span data-stu-id="4ffb4-120">Select any product that doesn't have an enriched product page.</span></span>
1. <span data-ttu-id="4ffb4-121">No Painel de Ação, selecione **Enriquecer página de produto**.</span><span class="sxs-lookup"><span data-stu-id="4ffb4-121">On the Action Pane, select **Enrich product page**.</span></span>
1. <span data-ttu-id="4ffb4-122">Selecione **Modelo PDP** e, depois, **OK**.</span><span class="sxs-lookup"><span data-stu-id="4ffb4-122">Select **PDP-template**, and then select **OK**.</span></span>
1. <span data-ttu-id="4ffb4-123">Na árvore em destaque da página à esquerda, expanda o slot **Principal**.</span><span class="sxs-lookup"><span data-stu-id="4ffb4-123">In the page outline tree on the left, expand the **Main** slot.</span></span>
1. <span data-ttu-id="4ffb4-124">Selecione o botão de reticências (**...**) para o slot **Principal** e depois selecione **Adicionar módulo**.</span><span class="sxs-lookup"><span data-stu-id="4ffb4-124">Select the ellipsis button (**...**) for the **Main** slot, and then select **Add Module**.</span></span>
1. <span data-ttu-id="4ffb4-125">Selecione **Contêiner 2** e, depois, **OK**.</span><span class="sxs-lookup"><span data-stu-id="4ffb4-125">Select **Container 2**, and then select **OK**.</span></span>
1. <span data-ttu-id="4ffb4-126">Selecione o botão de reticências para **Contêiner 2** e depois selecione **Adicionar módulo**.</span><span class="sxs-lookup"><span data-stu-id="4ffb4-126">Select the ellipsis button for **Container 2**, and then select **Add Module**.</span></span>
1. <span data-ttu-id="4ffb4-127">Selecione **Recurso** e, depois, **OK**.</span><span class="sxs-lookup"><span data-stu-id="4ffb4-127">Select **Feature**, and then select **OK**.</span></span>
1. <span data-ttu-id="4ffb4-128">No painel de propriedades à direita, no campo **Texto rico**, digite a descrição atualizada do produto.</span><span class="sxs-lookup"><span data-stu-id="4ffb4-128">In the properties pane on the right, in the **Rich Text** field, enter the updated description of the product.</span></span>
1. <span data-ttu-id="4ffb4-129">No campo **Cabeçalho**, insira texto de cabeçalho e depois selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="4ffb4-129">In the **Heading** field, enter heading text, and then select **OK**.</span></span>
1. <span data-ttu-id="4ffb4-130">Selecione **Salvar** e **Finalizar edição**.</span><span class="sxs-lookup"><span data-stu-id="4ffb4-130">Select **Save**, and then select **Finish editing**.</span></span>
1. <span data-ttu-id="4ffb4-131">No campo **Comentários**, insira **Enriqueceu um produto** e depois selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="4ffb4-131">In the **Comments** field, enter **Enriched a product**, and then select **OK**.</span></span>
1. <span data-ttu-id="4ffb4-132">Selecione **Visualizar** para visualizar a página de produto enriquecida.</span><span class="sxs-lookup"><span data-stu-id="4ffb4-132">Select **Preview** to preview the enriched product page.</span></span> <span data-ttu-id="4ffb4-133">Quando terminar, feche a guia de visualização para retornar à ferramenta de criação.</span><span class="sxs-lookup"><span data-stu-id="4ffb4-133">When you've finished, close the preview tab to return to the authoring tool.</span></span>
1. <span data-ttu-id="4ffb4-134">Selecione **Publicar**.</span><span class="sxs-lookup"><span data-stu-id="4ffb4-134">Select **Publish**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="4ffb4-135">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="4ffb4-135">Additional resources</span></span>

[<span data-ttu-id="4ffb4-136">Modificar uma página de site existente</span><span class="sxs-lookup"><span data-stu-id="4ffb4-136">Modify an existing site page</span></span>](modify-existing-page.md)

[<span data-ttu-id="4ffb4-137">Adicionar uma nova página do site</span><span class="sxs-lookup"><span data-stu-id="4ffb4-137">Add a new site page</span></span>](add-new-page.md)

[<span data-ttu-id="4ffb4-138">Selecionar layouts de página</span><span class="sxs-lookup"><span data-stu-id="4ffb4-138">Select page layouts</span></span>](select-page-layouts.md)

[<span data-ttu-id="4ffb4-139">Gerenciar metadados de SEO</span><span class="sxs-lookup"><span data-stu-id="4ffb4-139">Manage SEO metadata</span></span>](manage-seo-metadata.md)

[<span data-ttu-id="4ffb4-140">Salvar, visualizar, e publicar uma página</span><span class="sxs-lookup"><span data-stu-id="4ffb4-140">Save, preview, and publish a page</span></span>](save-preview-publish-page.md)

[<span data-ttu-id="4ffb4-141">Enriquecer uma página de aterrissagem da categoria</span><span class="sxs-lookup"><span data-stu-id="4ffb4-141">Enrich a category landing page</span></span>](enrich-category-page.md)

[<span data-ttu-id="4ffb4-142">Verificar acessibilidade de conteúdo da página</span><span class="sxs-lookup"><span data-stu-id="4ffb4-142">Verify page content accessibility</span></span>](verify-accessibility.md)
