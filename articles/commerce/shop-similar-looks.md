---
title: Habilitar recomendações de "comprar looks semelhantes"
description: Este tópico descreve como habilitar recomendações de "comprar looks semelhantes" de produtos no Microsoft Dynamics 365 Commerce.
author: bebeale
manager: AnnBe
ms.date: 08/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: ''
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail, eCommerce
ms.author: bebeale
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: 2e57965a1073982a7b6c34b79dbf6e5b90d7ee30
ms.sourcegitcommit: 15c68822f4d412bfc609be31b3702f18c81ea0bc
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/06/2020
ms.locfileid: "3666299"
---
# <a name="enable-shop-similar-looks-recommendations"></a><span data-ttu-id="e9507-103">Habilitar recomendações de "comprar looks semelhantes"</span><span class="sxs-lookup"><span data-stu-id="e9507-103">Enable "shop similar looks" recommendations</span></span>

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

<span data-ttu-id="e9507-104">Este tópico descreve como habilitar recomendações de "comprar looks semelhantes" de produtos no Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="e9507-104">This topic describes how to enable "shop similar looks" product recommendations in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="e9507-105">Visão Geral</span><span class="sxs-lookup"><span data-stu-id="e9507-105">Overview</span></span>

<span data-ttu-id="e9507-106">O recurso de recomendações de "comprar looks semelhantes" no Dynamics 365 Commerce usa o poder da inteligência artificial e do machine learning (IA-ML) para fornecer recomendações de produtos visualmente semelhantes para os clientes.</span><span class="sxs-lookup"><span data-stu-id="e9507-106">The "shop similar looks" recommendations feature in Dynamics 365 Commerce uses the power of artificial intelligence and machine learning (AI-ML) to deliver recommendations for visually similar products to customers.</span></span> <span data-ttu-id="e9507-107">Ao disponibilizar as recomendações de "comprar looks semelhantes" para todos os canais de varejo no Commerce, os varejistas podem aumentar a satisfação do cliente ajudando-os a encontrar o que desejam com facilidade.</span><span class="sxs-lookup"><span data-stu-id="e9507-107">By making "shop similar looks" recommendations available for all retail channels in Commerce, retailers can increase customer satisfaction by helping customers easily find what they want.</span></span>

<span data-ttu-id="e9507-108">A funcionalidade para as recomendações de "comprar looks semelhantes" usa as imagens dos produtos de grades de produtos de origem para encontrar e recomendar produtos visualmente semelhantes em um catálogo de produtos do varejista.</span><span class="sxs-lookup"><span data-stu-id="e9507-108">The functionality for "shop similar looks" recommendations uses product images of seed product variants to find and recommend visually similar products in a retailer's product catalog.</span></span> 

<span data-ttu-id="e9507-109">As recomendações de "comprar looks semelhante" estão disponíveis nas experiências de PDV (ponto de venda) e comércio eletrônico.</span><span class="sxs-lookup"><span data-stu-id="e9507-109">"Shop similar looks" recommendations are available in both the point of sale (POS) and e-Commerce experiences.</span></span>

### <a name="example-scenarios"></a><span data-ttu-id="e9507-110">Cenários de exemplo</span><span class="sxs-lookup"><span data-stu-id="e9507-110">Example scenarios</span></span>

- <span data-ttu-id="e9507-111">Um cliente vê um suéter preto listrado e recebe uma recomendação para um suéter semelhante em vermelho.</span><span class="sxs-lookup"><span data-stu-id="e9507-111">A customer views a black striped sweater and receives a recommendation for a similar sweater in red.</span></span> <span data-ttu-id="e9507-112">O cliente seleciona o produto recomendado em vez do produto visto originalmente e recebe recomendações para produtos semelhantes em vermelho.</span><span class="sxs-lookup"><span data-stu-id="e9507-112">The customer selects the recommended product instead of the originally viewed product and then receives recommendations for similar products in red.</span></span> 
- <span data-ttu-id="e9507-113">Um cliente usa recomendações de "comprar looks semelhantes" para descobrir brincos que combinem com um anel que o cliente esteja interessado em comprar.</span><span class="sxs-lookup"><span data-stu-id="e9507-113">A customer uses "shop similar looks" recommendations to discover matching earrings for a ring that the customer is interested in buying.</span></span>

## <a name="enable-shop-similar-looks-recommendations-in-commerce-headquarters"></a><span data-ttu-id="e9507-114">Habilitar recomendações de "comprar looks semelhantes" na sede do Commerce</span><span class="sxs-lookup"><span data-stu-id="e9507-114">Enable "shop similar looks" recommendations in Commerce headquarters</span></span>

<span data-ttu-id="e9507-115">As recomendações de produto têm suporte somente para clientes do Commerce que migraram seu armazenamento para usar o Azure Data Lake Gen2.</span><span class="sxs-lookup"><span data-stu-id="e9507-115">Product recommendations are supported only for Commerce users who have migrated their storage to Azure Data Lake Gen2.</span></span>

### <a name="prerequisites"></a><span data-ttu-id="e9507-116">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="e9507-116">Prerequisites</span></span>

<span data-ttu-id="e9507-117">Antes que os varejistas comecem a mostrar recomendações de "comprar looks semelhantes" para os clientes, há duas etapas de pré-requisito:</span><span class="sxs-lookup"><span data-stu-id="e9507-117">Before retailers can begin to show "shop similar looks" recommendations to customers, there are two prerequisite steps:</span></span>

- <span data-ttu-id="e9507-118">[Habilite recomendações de produtos](enable-product-recommendations.md) na sede do Commerce.</span><span class="sxs-lookup"><span data-stu-id="e9507-118">[Enable product recommendations](enable-product-recommendations.md) in Commerce headquarters.</span></span>
- <span data-ttu-id="e9507-119">Confirme se o servidor de mídia oferece suporte a chamadas HTTPS.</span><span class="sxs-lookup"><span data-stu-id="e9507-119">Confirm that the media server supports HTTPS calls.</span></span>

<span data-ttu-id="e9507-120">Para que o mecanismo de recomendações acesse as imagens dos produtos, os varejistas devem gerar as URLs dos produtos.</span><span class="sxs-lookup"><span data-stu-id="e9507-120">For the recommendations engine to access the product images, retailers must generate the product URLs.</span></span> <span data-ttu-id="e9507-121">Para gerar as URLs dos produtos na sede do Commerce, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="e9507-121">To generate product URLs in Commerce headquarters, follow these steps.</span></span>

1. <span data-ttu-id="e9507-122">Acesse **Imagens de produtos**.</span><span class="sxs-lookup"><span data-stu-id="e9507-122">Go to **Product images**.</span></span>
1. <span data-ttu-id="e9507-123">No Painel de Ações, selecione **Definir modelo de mídia**.</span><span class="sxs-lookup"><span data-stu-id="e9507-123">On the Action Pane, select **Define media template**.</span></span>
1. <span data-ttu-id="e9507-124">No painel de propriedades **Definir modelo de mídia**, em **URLs de mídia**, selecione **Gerar URLs**.</span><span class="sxs-lookup"><span data-stu-id="e9507-124">In the **Define media template** properties pane, under **Media URLs**, select **Generate URLs**.</span></span>

> [!NOTE]
> <span data-ttu-id="e9507-125">Ao habilitar o recurso de recomendações "comprar looks semelhantes", o processo de geração de listas de recomendação de produtos será iniciado.</span><span class="sxs-lookup"><span data-stu-id="e9507-125">When you enable the "shop similar looks" recommendations feature, the process of generating product recommendation lists begins.</span></span> <span data-ttu-id="e9507-126">Talvez seja necessário até um dia para que essas listas estejam disponíveis e visíveis online nos terminais de PDV.</span><span class="sxs-lookup"><span data-stu-id="e9507-126">Up to a day might be required before those lists are available and visible online and on POS terminals.</span></span>

<span data-ttu-id="e9507-127">Para habilitar o recurso de recomendações de "comprar looks semelhantes" na sede do Commerce, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="e9507-127">To enable the "shop similar looks" recommendations feature in Commerce headquarters, follow these steps.</span></span>

1. <span data-ttu-id="e9507-128">Acesse **Gerenciamento de recursos**.</span><span class="sxs-lookup"><span data-stu-id="e9507-128">Go to **Feature management**.</span></span>
1. <span data-ttu-id="e9507-129">Na lista de recursos disponíveis, procure e selecione **Comprar looks semelhantes**.</span><span class="sxs-lookup"><span data-stu-id="e9507-129">In the list of available features, search for and select **Shop similar looks**.</span></span>
1. <span data-ttu-id="e9507-130">No painel direito, selecione **Habilitar** para ativar o serviço.</span><span class="sxs-lookup"><span data-stu-id="e9507-130">In the right pane, select **Enable** to turn on the service.</span></span>

<span data-ttu-id="e9507-131">A ilustração a seguir mostra o recurso **Comprar looks semelhantes** na página **Gerenciamento de recursos** na sede do Commerce.</span><span class="sxs-lookup"><span data-stu-id="e9507-131">The following illustration shows the **Shop similar looks** feature on the **Feature management** page in Commerce headquarters.</span></span>

![O recurso "Comprar looks semelhantes" na página "Gerenciamento de recursos" na sede do Commerce](./media/enableshopsimilarlooks.png)

<span data-ttu-id="e9507-133">Depois que as tarefas anteriores forem concluídas, os terminais de PDV serão aprimorados automaticamente com um painel contextual **Comprar looks semelhantes**.</span><span class="sxs-lookup"><span data-stu-id="e9507-133">After the preceding tasks been completed, POS terminals are automatically enhanced with a contextual **Shop similar products** panel.</span></span> <span data-ttu-id="e9507-134">Ao selecionar **Ver mais**, os usuários do terminal de PDV podem ser levados a uma página dedicada de "Comprar looks semelhantes" que pode ser filtrada ainda mais.</span><span class="sxs-lookup"><span data-stu-id="e9507-134">By selecting **See more**, POS terminal users can be taken to a dedicated "shop similar looks" page that can be filtered further.</span></span>

> [!NOTE]
> <span data-ttu-id="e9507-135">Se você desativar o recurso de recomendações de "Comprar looks semelhantes", nenhum outro tipo de recomendação de produtos será afetado.</span><span class="sxs-lookup"><span data-stu-id="e9507-135">If you turn off the "shop similar looks" recommendations feature, no other types of product recommendations are affected.</span></span> <span data-ttu-id="e9507-136">Para obter mais informações sobre recomendações de produtos, consulte [Visão geral de recomendações de produtos](product-recommendations.md).</span><span class="sxs-lookup"><span data-stu-id="e9507-136">For more information about product recommendations, see [Product recommendations overview](product-recommendations.md).</span></span>

## <a name="add-a-shop-similar-looks-button-to-product-details-pages-by-using-commerce-site-builder"></a><span data-ttu-id="e9507-137">Adicionar um botão Comprar looks semelhantes às páginas de detalhes dos produtos usando o construtor de sites do Commerce</span><span class="sxs-lookup"><span data-stu-id="e9507-137">Add a Shop similar looks button to product details pages by using Commerce site builder</span></span>

<span data-ttu-id="e9507-138">Depois que você habilitar o recurso de recomendações de "Comprar looks semelhantes" na sede do Commerce, uma opção no construtor de sites do Commerce permitirá que os varejistas adicionem um botão **Comprar looks semelhantes** à caixa de compra em qualquer página de detalhes do produto (PDP).</span><span class="sxs-lookup"><span data-stu-id="e9507-138">After you enable the "shop similar looks" recommendations feature in Commerce headquarters, an option in Commerce site builder lets retailers to add a **Shop similar looks** button to the buy box on any product details page (PDP).</span></span> <span data-ttu-id="e9507-139">Um cliente que selecionar esse botão será levado a uma página dedicada de "comprar looks semelhantes" que retornará produtos visualmente semelhantes.</span><span class="sxs-lookup"><span data-stu-id="e9507-139">A customer who selects this button is taken to a dedicated "shop similar looks" page that returns visually similar products.</span></span> <span data-ttu-id="e9507-140">Nela, o cliente poderá usar seletores para filtrar ainda mais os produtos.</span><span class="sxs-lookup"><span data-stu-id="e9507-140">There, the customer can use selectors to further filter the products.</span></span>

<span data-ttu-id="e9507-141">Para adicionar um botão **Comprar looks semelhantes** e uma PDP usando o construtor de sites do Commerce, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="e9507-141">To add a **Shop similar looks** button to a PDP by using Commerce site builder, follow these steps.</span></span>

1. <span data-ttu-id="e9507-142">Abra uma página existente do construtor de sites que contenha um módulo de caixa de compra.</span><span class="sxs-lookup"><span data-stu-id="e9507-142">Open an existing site builder page that contains a buy box module.</span></span>
1. <span data-ttu-id="e9507-143">No painel de navegação esquerdo, selecione o módulo de caixa de compra.</span><span class="sxs-lookup"><span data-stu-id="e9507-143">In the left navigation pane, select the buy box module.</span></span>
1. <span data-ttu-id="e9507-144">No painel de navegação direito, marque a caixa de seleção **Habilitar Link para Comprar Looks Semelhantes**.</span><span class="sxs-lookup"><span data-stu-id="e9507-144">In the right navigation pane, select the **Enable Shop Similar Looks Link** check box.</span></span>
1. <span data-ttu-id="e9507-145">Selecione **Salvar**, **Concluir edição** para fazer check-in da página e depois selecione **Publicar** para publicá-lo.</span><span class="sxs-lookup"><span data-stu-id="e9507-145">Select **Save**, select **Finish editing** to check in the page, and then select **Publish** to publish it.</span></span> <span data-ttu-id="e9507-146">Depois que a página for publicada, a PDP incluirá um botão **Comprar looks semelhantes**.</span><span class="sxs-lookup"><span data-stu-id="e9507-146">After the page is published, the PDP will include a **Shop similar looks** button.</span></span>

<span data-ttu-id="e9507-147">A ilustração a seguir mostra a caixa de seleção **Habilitar Link para Comprar Looks Semelhantes** e o botão **Comprar looks semelhantes** em um exemplo de PDP no construtor de sites.</span><span class="sxs-lookup"><span data-stu-id="e9507-147">The following illustration shows the **Enable Shop Similar Looks Link** check box and **Shop similar looks** button on an example PDP in site builder.</span></span>

![Caixa de seleção Habilitar Link para Comprar Looks Semelhantes e o botão Comprar looks semelhantes em uma PDP no construtor de sites](./media/SSLecomtooling.png)

## <a name="additional-resources"></a><span data-ttu-id="e9507-149">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="e9507-149">Additional resources</span></span>

[<span data-ttu-id="e9507-150">Visão geral das recomendações de produtos</span><span class="sxs-lookup"><span data-stu-id="e9507-150">Product recommendations overview</span></span>](product-recommendations.md)

[<span data-ttu-id="e9507-151">Habilitar Azure Data Lake Storage em um ambiente do Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="e9507-151">Enable Azure Data Lake Storage in a Dynamics 365 Commerce environment</span></span>](enable-adls-environment.md)

[<span data-ttu-id="e9507-152">Habilitar recomendações dos produtos</span><span class="sxs-lookup"><span data-stu-id="e9507-152">Enable product recommendations</span></span>](enable-product-recommendations.md)

[<span data-ttu-id="e9507-153">Cancelar recomendações personalizadas</span><span class="sxs-lookup"><span data-stu-id="e9507-153">Opt out of personalized recommendations</span></span>](personalization-gdpr.md)

[<span data-ttu-id="e9507-154">Adicionar recomendações de produtos no PDV</span><span class="sxs-lookup"><span data-stu-id="e9507-154">Add product recommendations on POS</span></span>](product.md)

[<span data-ttu-id="e9507-155">Adicionar recomendações à tela de transação</span><span class="sxs-lookup"><span data-stu-id="e9507-155">Add recommendations to the transaction screen</span></span>](add-recommendations-control-pos-screen.md)

[<span data-ttu-id="e9507-156">Ajustar os resultados das recomendações de AI-ML</span><span class="sxs-lookup"><span data-stu-id="e9507-156">Adjust AI-ML recommendations results</span></span>](modify-product-recommendation-results.md)

[<span data-ttu-id="e9507-157">Criar manualmente recomendações selecionadas</span><span class="sxs-lookup"><span data-stu-id="e9507-157">Manually create curated recommendations</span></span>](create-editorial-recommendation-lists.md)

[<span data-ttu-id="e9507-158">Criar recomendações com dados de demonstração</span><span class="sxs-lookup"><span data-stu-id="e9507-158">Create recommendations with demo data</span></span>](product-recommendations-demo-data.md)

[<span data-ttu-id="e9507-159">Perguntas frequentes sobre recomendações de produtos</span><span class="sxs-lookup"><span data-stu-id="e9507-159">Product recommendations FAQ</span></span>](faq-recommendations.md)
