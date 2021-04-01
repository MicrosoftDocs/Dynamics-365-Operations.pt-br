---
title: Habilitar recomendações de "descrição de comprar itens semelhantes"
description: Este tópico descreve como habilitar recomendações de produto "descrição de comprar itens semelhantes" no Microsoft Dynamics 365 Commerce.
author: bsokolov
manager: AnnBe
ms.date: 01/13/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail, eCommerce
ms.author: bebeale
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.16
ms.openlocfilehash: b6b397b1f21e3dfcdb4a2b7fe67ddb541d090a97
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5234380"
---
# <a name="enable-shop-similar-description-recommendations"></a><span data-ttu-id="e7379-103">Habilitar recomendações de "comprar por descrição semelhante"</span><span class="sxs-lookup"><span data-stu-id="e7379-103">Enable "shop similar description" recommendations</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="e7379-104">Este tópico descreve como habilitar recomendações de produto "descrição de comprar itens semelhantes" no Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="e7379-104">This topic describes how to enable "shop similar description" product recommendations in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="e7379-105">O recurso de recomendações de "descrição de comprar itens semelhantes" no Dynamics 365 Commerce usa inteligência artificial e machine learning (IA-ML) para fornecer recomendações de produtos que tenham descrições semelhantes ao que o cliente está pesquisando.</span><span class="sxs-lookup"><span data-stu-id="e7379-105">The "shop similar description" recommendations feature in Dynamics 365 Commerce uses artificial intelligence and machine learning (AI-ML) to deliver recommendations for products that have descriptions that are similar to what the customer is looking for.</span></span> <span data-ttu-id="e7379-106">Ao disponibilizar as recomendações de "descrição de comprar itens semelhantes" para todos os canais de varejo no Commerce, os varejistas podem ajudar os clientes a encontrar o que desejam com facilidade.</span><span class="sxs-lookup"><span data-stu-id="e7379-106">By making "shop similar description" recommendations available for all retail channels in Commerce, retailers can help customers easily find what they want.</span></span>

<span data-ttu-id="e7379-107">A funcionalidade para as recomendações de "descrição de comprar itens semelhantes" usa o nome e descrição dos produtos de origem para encontrar e recomendar produtos visualmente semelhantes em um catálogo de produtos do varejista.</span><span class="sxs-lookup"><span data-stu-id="e7379-107">The functionality for "shop similar description" recommendations uses the product name and description of seed products to find and recommend similar products in a retailer's product catalog.</span></span>

<span data-ttu-id="e7379-108">As recomendações de "descrição de comprar itens semelhante" estão disponíveis nas experiências de PDV (ponto de venda) e comércio eletrônico.</span><span class="sxs-lookup"><span data-stu-id="e7379-108">"Shop similar description" recommendations are available in both the point of sale (POS) and e-commerce experiences.</span></span>

## <a name="example-scenarios"></a><span data-ttu-id="e7379-109">Cenários de exemplo</span><span class="sxs-lookup"><span data-stu-id="e7379-109">Example scenarios</span></span>

<span data-ttu-id="e7379-110">Os cenários de exemplo a seguir mostram os tipos de recomendações que a funcionalidade "descrição de comprar itens semelhantes" pode fornecer:</span><span class="sxs-lookup"><span data-stu-id="e7379-110">The following example scenarios show the types of recommendations that the "shop similar description" functionality can provide:</span></span>

- <span data-ttu-id="e7379-111">Um cliente vê um par de óculos de hastes estilo retrô e recebe um conjunto de recomendações para outros óculos que têm um design semelhante, no contexto do setor do varejista.</span><span class="sxs-lookup"><span data-stu-id="e7379-111">A customer views a pair of retro-style horn-rimmed glasses and receives a set of recommendations for other glasses that have a similar design, in the context of the retailer's industry.</span></span>
- <span data-ttu-id="e7379-112">Um cliente usa recomendações "descrição de comprar itens semelhantes" para descobrir sabores café que sejam semelhantes a um sabor já comprado do varejista.</span><span class="sxs-lookup"><span data-stu-id="e7379-112">A customer uses "shop similar description" recommendations to discover coffee flavors that are similar to a flavor that they previously purchased from the retailer.</span></span>

## <a name="set-up-shop-similar-description-recommendations"></a><span data-ttu-id="e7379-113">Configurar recomendações de "descrição de comprar itens semelhantes"</span><span class="sxs-lookup"><span data-stu-id="e7379-113">Set up "shop similar description" recommendations</span></span>

<span data-ttu-id="e7379-114">As recomendações de produto têm suporte somente para clientes do Commerce que migraram seu armazenamento para usar o Azure Data Lake Storage Gen2.</span><span class="sxs-lookup"><span data-stu-id="e7379-114">Product recommendations are supported only for Commerce users who have migrated their storage to Azure Data Lake Storage Gen2.</span></span>

### <a name="prerequisites"></a><span data-ttu-id="e7379-115">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="e7379-115">Prerequisites</span></span>

<span data-ttu-id="e7379-116">Antes que as recomendações de "descrição de comprar itens semelhantes" possam ser exibidas para os clientes, você deve atender aos seguintes pré-requisitos:</span><span class="sxs-lookup"><span data-stu-id="e7379-116">Before "shop similar description" recommendations can be shown to customers, you must complete the following prerequisites:</span></span>

- <span data-ttu-id="e7379-117">[Habilite recomendações de produtos](enable-product-recommendations.md) na sede do Commerce.</span><span class="sxs-lookup"><span data-stu-id="e7379-117">[Enable product recommendations](enable-product-recommendations.md) in Commerce headquarters.</span></span>
- <span data-ttu-id="e7379-118">Confirme se o servidor de mídia oferece suporte a chamadas HTTPS.</span><span class="sxs-lookup"><span data-stu-id="e7379-118">Confirm that the media server supports HTTPS calls.</span></span>

### <a name="turn-on-the-shop-similar-description-recommendations-feature"></a><span data-ttu-id="e7379-119">Ativar o recurso "descrição de comprar itens semelhantes"</span><span class="sxs-lookup"><span data-stu-id="e7379-119">Turn on the "shop similar description" recommendations feature</span></span>

<span data-ttu-id="e7379-120">Para ativar o recurso de recomendações de "descrição de comprar itens semelhantes" na sede do Commerce, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="e7379-120">To turn on the "shop similar description" recommendations feature in Commerce headquarters, follow these steps.</span></span>

1. <span data-ttu-id="e7379-121">No espaço de trabalho **Gerenciamento de recursos**, na lista de recursos disponíveis, procure e selecione a **Descrição de comprar itens semelhantes**.</span><span class="sxs-lookup"><span data-stu-id="e7379-121">In the **Feature management** workspace, in the list of available features, search for and select **Shop similar description**.</span></span>
1. <span data-ttu-id="e7379-122">No painel à direita, selecione **Habilitar**.</span><span class="sxs-lookup"><span data-stu-id="e7379-122">In the right pane, select **Enable**.</span></span>

> [!NOTE]
> <span data-ttu-id="e7379-123">Quando você ativar o recurso, o sistema começará a gerar listas de recomendação de produtos.</span><span class="sxs-lookup"><span data-stu-id="e7379-123">When you turn on the feature, the system starts to generate product recommendation lists.</span></span> <span data-ttu-id="e7379-124">Pode ser necessário até um dia para que essas listas fiquem disponíveis e visíveis online nos terminais de PDV.</span><span class="sxs-lookup"><span data-stu-id="e7379-124">It might take up to a day for those lists to become available and visible online and on POS terminals.</span></span>
>
> <span data-ttu-id="e7379-125">Se você desativar o recurso, outros tipos de recomendações de produtos não serão afetados.</span><span class="sxs-lookup"><span data-stu-id="e7379-125">If you turn off the feature, other types of product recommendations aren't affected.</span></span> <span data-ttu-id="e7379-126">Para obter mais informações sobre recomendações de produtos, consulte [Visão geral de recomendações de produtos](product-recommendations.md).</span><span class="sxs-lookup"><span data-stu-id="e7379-126">For more information about product recommendations, see [Product recommendations overview](product-recommendations.md).</span></span>

## <a name="add-a-shop-similar-description-button-to-product-details-pages"></a><span data-ttu-id="e7379-127">Adicionar um botão Descrição de comprar itens semelhantes a páginas de detalhes do produto</span><span class="sxs-lookup"><span data-stu-id="e7379-127">Add a Shop similar description button to product details pages</span></span>

<span data-ttu-id="e7379-128">Depois que você ativar o recurso de recomendações de "Descrição de comprar itens semelhantes" na matriz do Commerce, você pode adicionar um botão **Descrição de comprar itens semelhantes** à caixa de compra em qualquer página de detalhes do produto (PDP).</span><span class="sxs-lookup"><span data-stu-id="e7379-128">After you turn on the "shop similar description" recommendations feature in Commerce headquarters, you can add a **Shop similar description** button to the buy box on any product details page (PDP).</span></span> <span data-ttu-id="e7379-129">Um cliente que selecionar esse botão será levado a uma página dedicada de **Descrição de comprar itens semelhantes** que mostra produtos visualmente semelhantes.</span><span class="sxs-lookup"><span data-stu-id="e7379-129">A customer who selects this button is taken to a dedicated **Shop similar description** page that shows visually similar products.</span></span> <span data-ttu-id="e7379-130">O cliente poderá usar seletores para filtrar ainda mais os produtos.</span><span class="sxs-lookup"><span data-stu-id="e7379-130">The customer can then use selectors to further filter the products.</span></span>

<span data-ttu-id="e7379-131">Para adicionar um botão **Descrição de comprar itens semelhantes** a uma PDP usando o construtor de sites do Commerce, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="e7379-131">To add a **Shop similar description** button to a PDP by using Commerce site builder, follow these steps.</span></span>

1. <span data-ttu-id="e7379-132">Abra uma página existente do construtor de sites que contenha um módulo de caixa de compra.</span><span class="sxs-lookup"><span data-stu-id="e7379-132">Open an existing site builder page that contains a buy box module.</span></span>
1. <span data-ttu-id="e7379-133">No painel de navegação esquerdo, selecione o módulo de caixa de compra.</span><span class="sxs-lookup"><span data-stu-id="e7379-133">In the left navigation pane, select the buy box module.</span></span>
1. <span data-ttu-id="e7379-134">No painel direito, marque a caixa de seleção **Habilitar link para Descrição de comprar itens semelhantes**.</span><span class="sxs-lookup"><span data-stu-id="e7379-134">In the right pane, select the **Enable Shop Similar description Link** check box.</span></span>
1. <span data-ttu-id="e7379-135">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="e7379-135">Select **Save**.</span></span>
1. <span data-ttu-id="e7379-136">Selecione **Concluir edição** para fazer check-in da página e depois selecione **Publicar** para publicá-lo.</span><span class="sxs-lookup"><span data-stu-id="e7379-136">Select **Finish editing** to check in the page, and then select **Publish** to publish it.</span></span> <span data-ttu-id="e7379-137">Depois que a página for publicada, a PDP incluirá um botão **Descrição de comprar itens semelhantes**.</span><span class="sxs-lookup"><span data-stu-id="e7379-137">After the page is published, the PDP will include a **Shop similar description** button.</span></span>

<span data-ttu-id="e7379-138">A ilustração a seguir mostra a caixa de seleção **Habilitar link para Descrição de comprar itens semelhantes** e o botão **Descrição de comprar itens semelhantes** em um exemplo de PDP no construtor de sites.</span><span class="sxs-lookup"><span data-stu-id="e7379-138">The following illustration shows the **Enable shop similar description Link** check box and the **Shop similar description** button on an example PDP in site builder.</span></span>

![Habilitar caixa de seleção para link de Descrição de comprar itens semelhantes e botão Descrição de comprar itens semelhantes em uma PDP no construtor de sites](./media/ter_site_builder_buybox_button.png)

## <a name="additional-resources"></a><span data-ttu-id="e7379-140">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="e7379-140">Additional resources</span></span>

[<span data-ttu-id="e7379-141">Visão geral das recomendações de produtos</span><span class="sxs-lookup"><span data-stu-id="e7379-141">Product recommendations overview</span></span>](product-recommendations.md)

[<span data-ttu-id="e7379-142">Habilitar Azure Data Lake Storage em um ambiente do Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="e7379-142">Enable Azure Data Lake Storage in a Dynamics 365 Commerce environment</span></span>](enable-adls-environment.md)

[<span data-ttu-id="e7379-143">Habilitar recomendações de produtos</span><span class="sxs-lookup"><span data-stu-id="e7379-143">Enable product recommendations</span></span>](enable-product-recommendations.md)

[<span data-ttu-id="e7379-144">Habilitar recomendações de "comprar itens semelhantes"</span><span class="sxs-lookup"><span data-stu-id="e7379-144">Enable "shop similar looks" recommendations</span></span>](shop-similar-looks.md)

[<span data-ttu-id="e7379-145">Ajustar os resultados das recomendações de AI-ML</span><span class="sxs-lookup"><span data-stu-id="e7379-145">Adjust AI-ML recommendations results</span></span>](modify-product-recommendation-results.md)

[<span data-ttu-id="e7379-146">Criar manualmente recomendações selecionadas</span><span class="sxs-lookup"><span data-stu-id="e7379-146">Manually create curated recommendations</span></span>](create-editorial-recommendation-lists.md)

[<span data-ttu-id="e7379-147">Perguntas frequentes sobre recomendações de produtos</span><span class="sxs-lookup"><span data-stu-id="e7379-147">Product recommendations FAQ</span></span>](faq-recommendations.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]