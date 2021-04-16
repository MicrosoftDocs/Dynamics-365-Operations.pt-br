---
title: Habilitar recomendações de "comprar looks semelhantes"
description: Este tópico descreve como habilitar recomendações de "comprar looks semelhantes" de produtos no Microsoft Dynamics 365 Commerce.
author: bebeale
ms.date: 08/06/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail, eCommerce
ms.author: bebeale
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: 06b5721c423330b8840bb546bdb144c3189c25bb
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5795372"
---
# <a name="enable-shop-similar-looks-recommendations"></a><span data-ttu-id="6a709-103">Habilitar recomendações de "comprar itens semelhantes"</span><span class="sxs-lookup"><span data-stu-id="6a709-103">Enable "shop similar looks" recommendations</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="6a709-104">Este tópico descreve como habilitar recomendações de "comprar looks semelhantes" de produtos no Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="6a709-104">This topic describes how to enable "shop similar looks" product recommendations in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="6a709-105">O recurso de recomendações de "comprar looks semelhantes" no Dynamics 365 Commerce usa o poder da inteligência artificial e do machine learning (IA-ML) para fornecer recomendações de produtos visualmente semelhantes para os clientes.</span><span class="sxs-lookup"><span data-stu-id="6a709-105">The "shop similar looks" recommendations feature in Dynamics 365 Commerce uses the power of artificial intelligence and machine learning (AI-ML) to deliver recommendations for visually similar products to customers.</span></span> <span data-ttu-id="6a709-106">Ao disponibilizar as recomendações de "comprar looks semelhantes" para todos os canais de varejo no Commerce, os varejistas podem aumentar a satisfação do cliente ajudando-os a encontrar o que desejam com facilidade.</span><span class="sxs-lookup"><span data-stu-id="6a709-106">By making "shop similar looks" recommendations available for all retail channels in Commerce, retailers can increase customer satisfaction by helping customers easily find what they want.</span></span>

<span data-ttu-id="6a709-107">A funcionalidade para as recomendações de "comprar looks semelhantes" usa as imagens dos produtos de grades de produtos de origem para encontrar e recomendar produtos visualmente semelhantes em um catálogo de produtos do varejista.</span><span class="sxs-lookup"><span data-stu-id="6a709-107">The functionality for "shop similar looks" recommendations uses product images of seed product variants to find and recommend visually similar products in a retailer's product catalog.</span></span> 

<span data-ttu-id="6a709-108">As recomendações de "comprar looks semelhante" estão disponíveis nas experiências de PDV (ponto de venda) e comércio eletrônico.</span><span class="sxs-lookup"><span data-stu-id="6a709-108">"Shop similar looks" recommendations are available in both the point of sale (POS) and e-Commerce experiences.</span></span>

### <a name="example-scenarios"></a><span data-ttu-id="6a709-109">Cenários de exemplo</span><span class="sxs-lookup"><span data-stu-id="6a709-109">Example scenarios</span></span>

- <span data-ttu-id="6a709-110">Um cliente vê um suéter preto listrado e recebe uma recomendação para um suéter semelhante em vermelho.</span><span class="sxs-lookup"><span data-stu-id="6a709-110">A customer views a black striped sweater and receives a recommendation for a similar sweater in red.</span></span> <span data-ttu-id="6a709-111">O cliente seleciona o produto recomendado em vez do produto visto originalmente e recebe recomendações para produtos semelhantes em vermelho.</span><span class="sxs-lookup"><span data-stu-id="6a709-111">The customer selects the recommended product instead of the originally viewed product and then receives recommendations for similar products in red.</span></span> 
- <span data-ttu-id="6a709-112">Um cliente usa recomendações de "comprar looks semelhantes" para descobrir brincos que combinem com um anel que o cliente esteja interessado em comprar.</span><span class="sxs-lookup"><span data-stu-id="6a709-112">A customer uses "shop similar looks" recommendations to discover matching earrings for a ring that the customer is interested in buying.</span></span>

## <a name="enable-shop-similar-looks-recommendations-in-commerce-headquarters"></a><span data-ttu-id="6a709-113">Habilitar recomendações de "comprar looks semelhantes" na sede do Commerce</span><span class="sxs-lookup"><span data-stu-id="6a709-113">Enable "shop similar looks" recommendations in Commerce headquarters</span></span>

<span data-ttu-id="6a709-114">As recomendações de produto têm suporte somente para clientes do Commerce que migraram seu armazenamento para usar o Azure Data Lake Gen2.</span><span class="sxs-lookup"><span data-stu-id="6a709-114">Product recommendations are supported only for Commerce users who have migrated their storage to Azure Data Lake Gen2.</span></span>

### <a name="prerequisites"></a><span data-ttu-id="6a709-115">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="6a709-115">Prerequisites</span></span>

<span data-ttu-id="6a709-116">Antes que os varejistas comecem a mostrar recomendações de "comprar looks semelhantes" para os clientes, há duas etapas de pré-requisito:</span><span class="sxs-lookup"><span data-stu-id="6a709-116">Before retailers can begin to show "shop similar looks" recommendations to customers, there are two prerequisite steps:</span></span>

- <span data-ttu-id="6a709-117">[Habilite recomendações de produtos](enable-product-recommendations.md) na sede do Commerce.</span><span class="sxs-lookup"><span data-stu-id="6a709-117">[Enable product recommendations](enable-product-recommendations.md) in Commerce headquarters.</span></span>
- <span data-ttu-id="6a709-118">Confirme se o servidor de mídia oferece suporte a chamadas HTTPS.</span><span class="sxs-lookup"><span data-stu-id="6a709-118">Confirm that the media server supports HTTPS calls.</span></span>

<span data-ttu-id="6a709-119">Para que o mecanismo de recomendações acesse as imagens dos produtos, os varejistas devem gerar as URLs dos produtos.</span><span class="sxs-lookup"><span data-stu-id="6a709-119">For the recommendations engine to access the product images, retailers must generate the product URLs.</span></span> <span data-ttu-id="6a709-120">Para gerar as URLs dos produtos na sede do Commerce, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="6a709-120">To generate product URLs in Commerce headquarters, follow these steps.</span></span>

1. <span data-ttu-id="6a709-121">Acesse **Imagens de produtos**.</span><span class="sxs-lookup"><span data-stu-id="6a709-121">Go to **Product images**.</span></span>
1. <span data-ttu-id="6a709-122">No Painel de Ações, selecione **Definir modelo de mídia**.</span><span class="sxs-lookup"><span data-stu-id="6a709-122">On the Action Pane, select **Define media template**.</span></span>
1. <span data-ttu-id="6a709-123">No painel de propriedades **Definir modelo de mídia**, em **URLs de mídia**, selecione **Gerar URLs**.</span><span class="sxs-lookup"><span data-stu-id="6a709-123">In the **Define media template** properties pane, under **Media URLs**, select **Generate URLs**.</span></span>

> [!NOTE]
> <span data-ttu-id="6a709-124">Ao habilitar o recurso de recomendações "comprar looks semelhantes", o processo de geração de listas de recomendação de produtos será iniciado.</span><span class="sxs-lookup"><span data-stu-id="6a709-124">When you enable the "shop similar looks" recommendations feature, the process of generating product recommendation lists begins.</span></span> <span data-ttu-id="6a709-125">Talvez seja necessário até um dia para que essas listas estejam disponíveis e visíveis online nos terminais de PDV.</span><span class="sxs-lookup"><span data-stu-id="6a709-125">Up to a day might be required before those lists are available and visible online and on POS terminals.</span></span>

<span data-ttu-id="6a709-126">Para habilitar o recurso de recomendações de "comprar looks semelhantes" na sede do Commerce, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="6a709-126">To enable the "shop similar looks" recommendations feature in Commerce headquarters, follow these steps.</span></span>

1. <span data-ttu-id="6a709-127">Acesse **Gerenciamento de recursos**.</span><span class="sxs-lookup"><span data-stu-id="6a709-127">Go to **Feature management**.</span></span>
1. <span data-ttu-id="6a709-128">Na lista de recursos disponíveis, procure e selecione **Comprar looks semelhantes**.</span><span class="sxs-lookup"><span data-stu-id="6a709-128">In the list of available features, search for and select **Shop similar looks**.</span></span>
1. <span data-ttu-id="6a709-129">No painel direito, selecione **Habilitar** para ativar o serviço.</span><span class="sxs-lookup"><span data-stu-id="6a709-129">In the right pane, select **Enable** to turn on the service.</span></span>

<span data-ttu-id="6a709-130">A ilustração a seguir mostra o recurso **Comprar looks semelhantes** na página **Gerenciamento de recursos** na sede do Commerce.</span><span class="sxs-lookup"><span data-stu-id="6a709-130">The following illustration shows the **Shop similar looks** feature on the **Feature management** page in Commerce headquarters.</span></span>

![O recurso "Comprar looks semelhantes" na página "Gerenciamento de recursos" na sede do Commerce](./media/enableshopsimilarlooks.png)

<span data-ttu-id="6a709-132">Depois que as tarefas anteriores forem concluídas, os terminais de PDV serão aprimorados automaticamente com um painel contextual **Comprar looks semelhantes**.</span><span class="sxs-lookup"><span data-stu-id="6a709-132">After the preceding tasks been completed, POS terminals are automatically enhanced with a contextual **Shop similar products** panel.</span></span> <span data-ttu-id="6a709-133">Ao selecionar **Ver mais**, os usuários do terminal de PDV podem ser levados a uma página dedicada de "Comprar looks semelhantes" que pode ser filtrada ainda mais.</span><span class="sxs-lookup"><span data-stu-id="6a709-133">By selecting **See more**, POS terminal users can be taken to a dedicated "shop similar looks" page that can be filtered further.</span></span>

> [!NOTE]
> <span data-ttu-id="6a709-134">Se você desativar o recurso de recomendações de "Comprar looks semelhantes", nenhum outro tipo de recomendação de produtos será afetado.</span><span class="sxs-lookup"><span data-stu-id="6a709-134">If you turn off the "shop similar looks" recommendations feature, no other types of product recommendations are affected.</span></span> <span data-ttu-id="6a709-135">Para obter mais informações sobre recomendações de produtos, consulte [Visão geral de recomendações de produtos](product-recommendations.md).</span><span class="sxs-lookup"><span data-stu-id="6a709-135">For more information about product recommendations, see [Product recommendations overview](product-recommendations.md).</span></span>

## <a name="add-a-shop-similar-looks-button-to-product-details-pages-by-using-commerce-site-builder"></a><span data-ttu-id="6a709-136">Adicionar um botão Comprar looks semelhantes às páginas de detalhes dos produtos usando o construtor de sites do Commerce</span><span class="sxs-lookup"><span data-stu-id="6a709-136">Add a Shop similar looks button to product details pages by using Commerce site builder</span></span>

<span data-ttu-id="6a709-137">Depois que você habilitar o recurso de recomendações de "Comprar looks semelhantes" na sede do Commerce, uma opção no construtor de sites do Commerce permitirá que os varejistas adicionem um botão **Comprar looks semelhantes** à caixa de compra em qualquer página de detalhes do produto (PDP).</span><span class="sxs-lookup"><span data-stu-id="6a709-137">After you enable the "shop similar looks" recommendations feature in Commerce headquarters, an option in Commerce site builder lets retailers to add a **Shop similar looks** button to the buy box on any product details page (PDP).</span></span> <span data-ttu-id="6a709-138">Um cliente que selecionar esse botão será levado a uma página dedicada de "comprar looks semelhantes" que retornará produtos visualmente semelhantes.</span><span class="sxs-lookup"><span data-stu-id="6a709-138">A customer who selects this button is taken to a dedicated "shop similar looks" page that returns visually similar products.</span></span> <span data-ttu-id="6a709-139">Nela, o cliente poderá usar seletores para filtrar ainda mais os produtos.</span><span class="sxs-lookup"><span data-stu-id="6a709-139">There, the customer can use selectors to further filter the products.</span></span>

<span data-ttu-id="6a709-140">Para adicionar um botão **Comprar looks semelhantes** e uma PDP usando o construtor de sites do Commerce, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="6a709-140">To add a **Shop similar looks** button to a PDP by using Commerce site builder, follow these steps.</span></span>

1. <span data-ttu-id="6a709-141">Abra uma página existente do construtor de sites que contenha um módulo de caixa de compra.</span><span class="sxs-lookup"><span data-stu-id="6a709-141">Open an existing site builder page that contains a buy box module.</span></span>
1. <span data-ttu-id="6a709-142">No painel de navegação esquerdo, selecione o módulo de caixa de compra.</span><span class="sxs-lookup"><span data-stu-id="6a709-142">In the left navigation pane, select the buy box module.</span></span>
1. <span data-ttu-id="6a709-143">No painel de navegação direito, marque a caixa de seleção **Habilitar Link para Comprar Looks Semelhantes**.</span><span class="sxs-lookup"><span data-stu-id="6a709-143">In the right navigation pane, select the **Enable Shop Similar Looks Link** check box.</span></span>
1. <span data-ttu-id="6a709-144">Selecione **Salvar**, **Concluir edição** para fazer check-in da página e depois selecione **Publicar** para publicá-lo.</span><span class="sxs-lookup"><span data-stu-id="6a709-144">Select **Save**, select **Finish editing** to check in the page, and then select **Publish** to publish it.</span></span> <span data-ttu-id="6a709-145">Depois que a página for publicada, a PDP incluirá um botão **Comprar looks semelhantes**.</span><span class="sxs-lookup"><span data-stu-id="6a709-145">After the page is published, the PDP will include a **Shop similar looks** button.</span></span>

<span data-ttu-id="6a709-146">A ilustração a seguir mostra a caixa de seleção **Habilitar Link para Comprar Looks Semelhantes** e o botão **Comprar looks semelhantes** em um exemplo de PDP no construtor de sites.</span><span class="sxs-lookup"><span data-stu-id="6a709-146">The following illustration shows the **Enable Shop Similar Looks Link** check box and **Shop similar looks** button on an example PDP in site builder.</span></span>

![Caixa de seleção Habilitar Link para Comprar Looks Semelhantes e o botão Comprar looks semelhantes em uma PDP no construtor de sites](./media/SSLecomtooling.png)

## <a name="additional-resources"></a><span data-ttu-id="6a709-148">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="6a709-148">Additional resources</span></span>

[<span data-ttu-id="6a709-149">Visão geral das recomendações de produtos</span><span class="sxs-lookup"><span data-stu-id="6a709-149">Product recommendations overview</span></span>](product-recommendations.md)

[<span data-ttu-id="6a709-150">Habilitar Azure Data Lake Storage em um ambiente do Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="6a709-150">Enable Azure Data Lake Storage in a Dynamics 365 Commerce environment</span></span>](enable-adls-environment.md)

[<span data-ttu-id="6a709-151">Habilitar recomendações dos produtos</span><span class="sxs-lookup"><span data-stu-id="6a709-151">Enable product recommendations</span></span>](enable-product-recommendations.md)

[<span data-ttu-id="6a709-152">Cancelar recomendações personalizadas</span><span class="sxs-lookup"><span data-stu-id="6a709-152">Opt out of personalized recommendations</span></span>](personalization-gdpr.md)

[<span data-ttu-id="6a709-153">Adicionar recomendações de produtos no PDV</span><span class="sxs-lookup"><span data-stu-id="6a709-153">Add product recommendations on POS</span></span>](product.md)

[<span data-ttu-id="6a709-154">Adicionar recomendações à tela de transação</span><span class="sxs-lookup"><span data-stu-id="6a709-154">Add recommendations to the transaction screen</span></span>](add-recommendations-control-pos-screen.md)

[<span data-ttu-id="6a709-155">Ajustar os resultados das recomendações de AI-ML</span><span class="sxs-lookup"><span data-stu-id="6a709-155">Adjust AI-ML recommendations results</span></span>](modify-product-recommendation-results.md)

[<span data-ttu-id="6a709-156">Criar manualmente recomendações selecionadas</span><span class="sxs-lookup"><span data-stu-id="6a709-156">Manually create curated recommendations</span></span>](create-editorial-recommendation-lists.md)

[<span data-ttu-id="6a709-157">Criar recomendações com dados de demonstração</span><span class="sxs-lookup"><span data-stu-id="6a709-157">Create recommendations with demo data</span></span>](product-recommendations-demo-data.md)

[<span data-ttu-id="6a709-158">Perguntas frequentes sobre recomendações de produtos</span><span class="sxs-lookup"><span data-stu-id="6a709-158">Product recommendations FAQ</span></span>](faq-recommendations.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
