---
title: Enriquecer uma página de produto
description: Este tópico descreve como enriquecer uma página de produto no Microsoft Dynamics 365 Commerce.
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
ms.openlocfilehash: d9c0f329d21cdda5c36a39a8c602d5925b720f52
ms.sourcegitcommit: ef3a1d7527311d00b69a1072ae5eb021ce68034c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/09/2020
ms.locfileid: "2945734"
---
# <a name="enrich-a-product-page"></a><span data-ttu-id="e7d6b-103">Enriquecer uma página de produto</span><span class="sxs-lookup"><span data-stu-id="e7d6b-103">Enrich a product page</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="e7d6b-104">Este tópico descreve como enriquecer uma página de produto no Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="e7d6b-104">This topic describes how to enrich a product page in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="e7d6b-105">Visão geral</span><span class="sxs-lookup"><span data-stu-id="e7d6b-105">Overview</span></span>

<span data-ttu-id="e7d6b-106">Por padrão, seu site usa uma página genérica para exibir dados de produto.</span><span class="sxs-lookup"><span data-stu-id="e7d6b-106">By default, your site uses a generic page to show product data.</span></span> <span data-ttu-id="e7d6b-107">Essa página inclui informações básicas sobre o produto e controles necessários para vendê-lo.</span><span class="sxs-lookup"><span data-stu-id="e7d6b-107">This page includes the basic information about the product and the controls that are required to sell it.</span></span> <span data-ttu-id="e7d6b-108">Entretanto, você pode adicionar as informações que vem do servidor de varejo com imagens adicionais ou texto para um produto específico.</span><span class="sxs-lookup"><span data-stu-id="e7d6b-108">However, you can supplement the information that comes from the Retail Server with additional images or text for a specific product.</span></span> <span data-ttu-id="e7d6b-109">Esse processo é conhecido como enriquecimento da página de produto.</span><span class="sxs-lookup"><span data-stu-id="e7d6b-109">This process is known as enriching the product page.</span></span>

<span data-ttu-id="e7d6b-110">Em muitos casos, você desejará usar conteúdo adicional específico de seus produtos.</span><span class="sxs-lookup"><span data-stu-id="e7d6b-110">In many cases, you will want to use specific additional content for your products.</span></span> <span data-ttu-id="e7d6b-111">Quando você vai para **Varejo** na ferramenta de criação, você verá uma lista de produtos no canal atribuído ao site.</span><span class="sxs-lookup"><span data-stu-id="e7d6b-111">When you go to **Retail** in the authoring tool, you will see a list of products from the channel that is assigned to the site.</span></span> <span data-ttu-id="e7d6b-112">Na lista, a coluna **Enriquecido** indica se a página do produto de um produto foi enriquecida.</span><span class="sxs-lookup"><span data-stu-id="e7d6b-112">In this list, the **Enriched** column indicates whether the product page for a product has been enriched.</span></span> <span data-ttu-id="e7d6b-113">Se uma marca de seleção é exibida na coluna, uma página enriquecida de produto existe para o produto.</span><span class="sxs-lookup"><span data-stu-id="e7d6b-113">If a check mark appears in the column, an enriched product page exists for the product.</span></span> <span data-ttu-id="e7d6b-114">Se nenhuma marca de seleção for exibida, a página de produto padrão e o conteúdo são usados para o produto.</span><span class="sxs-lookup"><span data-stu-id="e7d6b-114">If no check mark appears, the default product page and content are used for the product.</span></span> <span data-ttu-id="e7d6b-115">Você pode visualizar as páginas de produto enriquecida e não enriquecida selecionando um nome de produto na lista.</span><span class="sxs-lookup"><span data-stu-id="e7d6b-115">You can preview both enriched and non-enriched product pages by selecting a product name in the list.</span></span>

## <a name="enrich-a-product-page"></a><span data-ttu-id="e7d6b-116">Enriquecer uma página de produto</span><span class="sxs-lookup"><span data-stu-id="e7d6b-116">Enrich a product page</span></span>

<span data-ttu-id="e7d6b-117">Para enriquecer uma página de produto, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="e7d6b-117">To enrich a product page, follow these steps.</span></span>

1. <span data-ttu-id="e7d6b-118">Em **Sites**, selecione **Fabrikam** (ou o nome do seu site).</span><span class="sxs-lookup"><span data-stu-id="e7d6b-118">Under **Sites**, select **Fabrikam** (or the name of your site).</span></span>
1. <span data-ttu-id="e7d6b-119">No painel de navegação à esquerda, selecione **Produtos**.</span><span class="sxs-lookup"><span data-stu-id="e7d6b-119">In the navigation pane on the left, select **Products**.</span></span>
1. <span data-ttu-id="e7d6b-120">Selecione todos os produtos que não têm uma página de produto enriquecida.</span><span class="sxs-lookup"><span data-stu-id="e7d6b-120">Select any product that doesn't have an enriched product page.</span></span>
1. <span data-ttu-id="e7d6b-121">No Painel de Ação, selecione **Enriquecer página de produto**.</span><span class="sxs-lookup"><span data-stu-id="e7d6b-121">On the Action Pane, select **Enrich product page**.</span></span>
1. <span data-ttu-id="e7d6b-122">Selecione **Modelo PDP** e, depois, **OK**.</span><span class="sxs-lookup"><span data-stu-id="e7d6b-122">Select **PDP-template**, and then select **OK**.</span></span>
1. <span data-ttu-id="e7d6b-123">Na árvore em destaque da página à esquerda, expanda o slot **Principal**.</span><span class="sxs-lookup"><span data-stu-id="e7d6b-123">In the page outline tree on the left, expand the **Main** slot.</span></span>
1. <span data-ttu-id="e7d6b-124">Selecione o botão de reticências (**...**) para o slot **Principal** e depois selecione **Adicionar módulo**.</span><span class="sxs-lookup"><span data-stu-id="e7d6b-124">Select the ellipsis button (**...**) for the **Main** slot, and then select **Add Module**.</span></span>
1. <span data-ttu-id="e7d6b-125">Selecione **Contêiner 2** e, depois, **OK**.</span><span class="sxs-lookup"><span data-stu-id="e7d6b-125">Select **Container 2**, and then select **OK**.</span></span>
1. <span data-ttu-id="e7d6b-126">Selecione o botão de reticências para **Contêiner 2** e depois selecione **Adicionar módulo**.</span><span class="sxs-lookup"><span data-stu-id="e7d6b-126">Select the ellipsis button for **Container 2**, and then select **Add Module**.</span></span>
1. <span data-ttu-id="e7d6b-127">Selecione **Recurso** e, depois, **OK**.</span><span class="sxs-lookup"><span data-stu-id="e7d6b-127">Select **Feature**, and then select **OK**.</span></span>
1. <span data-ttu-id="e7d6b-128">No painel de propriedades à direita, no campo **Texto rico**, digite a descrição atualizada do produto.</span><span class="sxs-lookup"><span data-stu-id="e7d6b-128">In the properties pane on the right, in the **Rich Text** field, enter the updated description of the product.</span></span>
1. <span data-ttu-id="e7d6b-129">No campo **Cabeçalho**, insira texto de cabeçalho e depois selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="e7d6b-129">In the **Heading** field, enter heading text, and then select **OK**.</span></span>
1. <span data-ttu-id="e7d6b-130">Selecione **Salvar** e **Fazer Check-in**.</span><span class="sxs-lookup"><span data-stu-id="e7d6b-130">Select **Save**, and then select **Check In**.</span></span>
1. <span data-ttu-id="e7d6b-131">No campo **Comentários**, insira **Enriqueceu um produto** e depois selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="e7d6b-131">In the **Comments** field, enter **Enriched a product**, and then select **OK**.</span></span>
1. <span data-ttu-id="e7d6b-132">Selecione **Visualizar** para visualizar a página de produto enriquecida.</span><span class="sxs-lookup"><span data-stu-id="e7d6b-132">Select **Preview** to preview the enriched product page.</span></span> <span data-ttu-id="e7d6b-133">Quando terminar, feche a guia de visualização para retornar à ferramenta de criação.</span><span class="sxs-lookup"><span data-stu-id="e7d6b-133">When you've finished, close the preview tab to return to the authoring tool.</span></span>
1. <span data-ttu-id="e7d6b-134">Selecione **Publicar**.</span><span class="sxs-lookup"><span data-stu-id="e7d6b-134">Select **Publish**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="e7d6b-135">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="e7d6b-135">Additional resources</span></span>

[<span data-ttu-id="e7d6b-136">Modificar uma página de site existente</span><span class="sxs-lookup"><span data-stu-id="e7d6b-136">Modify an existing site page</span></span>](modify-existing-page.md)

[<span data-ttu-id="e7d6b-137">Adicionar uma nova página do site</span><span class="sxs-lookup"><span data-stu-id="e7d6b-137">Add a new site page</span></span>](add-new-page.md)

[<span data-ttu-id="e7d6b-138">Selecionar layouts de página</span><span class="sxs-lookup"><span data-stu-id="e7d6b-138">Select page layouts</span></span>](select-page-layouts.md)

[<span data-ttu-id="e7d6b-139">Gerenciar metadados de SEO</span><span class="sxs-lookup"><span data-stu-id="e7d6b-139">Manage SEO metadata</span></span>](manage-seo-metadata.md)

[<span data-ttu-id="e7d6b-140">Salvar, visualizar, e publicar uma página</span><span class="sxs-lookup"><span data-stu-id="e7d6b-140">Save, preview, and publish a page</span></span>](save-preview-publish-page.md)

[<span data-ttu-id="e7d6b-141">Enriquecer uma página de aterrissagem da categoria</span><span class="sxs-lookup"><span data-stu-id="e7d6b-141">Enrich a category landing page</span></span>](enrich-category-page.md)

[<span data-ttu-id="e7d6b-142">Verificar acessibilidade de conteúdo da página</span><span class="sxs-lookup"><span data-stu-id="e7d6b-142">Verify page content accessibility</span></span>](verify-accessibility.md)
