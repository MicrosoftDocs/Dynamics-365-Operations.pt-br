---
title: Visão geral das páginas de detalhes do produto
description: Este tópico fornece uma visão geral das páginas de detalhes do produto (PDPs) no Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 01/23/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: c53e74204fad2960dfba972a38c511df7d6672d8
ms.sourcegitcommit: ce397c2759f642c595e30fef58a770b50360b2bd
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2020
ms.locfileid: "3527530"
---
# <a name="product-details-pages-overview"></a><span data-ttu-id="48349-103">Visão geral das páginas de detalhes do produto</span><span class="sxs-lookup"><span data-stu-id="48349-103">Product details pages overview</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="48349-104">Este tópico fornece uma visão geral das páginas de detalhes do produto (PDPs) no Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="48349-104">This topic provides an overview of product details pages (PDPs) in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="48349-105">Visão geral</span><span class="sxs-lookup"><span data-stu-id="48349-105">Overview</span></span>

<span data-ttu-id="48349-106">Uma PDP fornece informações detalhadas sobre um produto e permite que os clientes selecionem opções de produtos, como tamanho, estilo e cor.</span><span class="sxs-lookup"><span data-stu-id="48349-106">A PDP provides detailed information about a product, and lets customers select product options such as a size, style, and color.</span></span> <span data-ttu-id="48349-107">Uma PDP deve mostrar todas as informações do produto que um cliente precisa para tomar uma decisão de compra.</span><span class="sxs-lookup"><span data-stu-id="48349-107">A PDP should showcase all the product information that a customer requires to make a purchase decision.</span></span>

<span data-ttu-id="48349-108">A ilustração a seguir mostra um exemplo de uma PDP.</span><span class="sxs-lookup"><span data-stu-id="48349-108">The following illustration shows an example of a PDP.</span></span>

![Exemplo de uma página de detalhes do produto](./media/pdp.PNG)

## <a name="header-and-footer-modules"></a><span data-ttu-id="48349-110">Módulos de cabeçalho e rodapé</span><span class="sxs-lookup"><span data-stu-id="48349-110">Header and footer modules</span></span>

<span data-ttu-id="48349-111">A parte superior de uma PDP possui um cabeçalho que mostra todas as categorias de produtos e outras páginas pelas quais o varejista deseja que os clientes naveguem.</span><span class="sxs-lookup"><span data-stu-id="48349-111">The top of a PDP has a header that shows all the product categories and other pages that the retailer wants customers to browse.</span></span> <span data-ttu-id="48349-112">A parte inferior da página possui um rodapé que contém links rápidos para vários tópicos que podem interessar aos clientes.</span><span class="sxs-lookup"><span data-stu-id="48349-112">The bottom of the page has a footer that contains quick links to various topics that might interest customers.</span></span>

## <a name="buy-box-module"></a><span data-ttu-id="48349-113">Módulo de caixa de compra</span><span class="sxs-lookup"><span data-stu-id="48349-113">Buy box module</span></span>

<span data-ttu-id="48349-114">O módulo mais importante em um PDP é o módulo de caixa de compra, que aparece como o primeiro item na seção principal da página.</span><span class="sxs-lookup"><span data-stu-id="48349-114">The most important module on a PDP is the buy box module, which appears as the first item in the main section of the page.</span></span> <span data-ttu-id="48349-115">Um módulo de caixa de compra mostra informações importantes sobre os produtos, como o nome do produto, a descrição do produto, o preço do produto, imagens do produto e classificações de produtos.</span><span class="sxs-lookup"><span data-stu-id="48349-115">A buy box module shows important product information, such as the product name, the product description, the product price, product images, and product ratings.</span></span>

<span data-ttu-id="48349-116">O módulo da caixa de compra permite que o cliente selecione as opções do produto (por exemplo, tamanho, estilo e cor) e adicione o produto ao carrinho.</span><span class="sxs-lookup"><span data-stu-id="48349-116">The buy box module lets the customer select product options (for example, a size, style, and color) and add the product to the cart.</span></span> <span data-ttu-id="48349-117">Ele também permite que o cliente compre o produto on-line e o retire em uma loja.</span><span class="sxs-lookup"><span data-stu-id="48349-117">It also lets the customer buy the product online and pick it up in a store.</span></span> <span data-ttu-id="48349-118">O módulo de compra on-line e retirada na loja usa a integração com as APIs (interfaces de programação de aplicativos) do Bing Maps para encontrar lojas próximas em outro local que o cliente especificar.</span><span class="sxs-lookup"><span data-stu-id="48349-118">The buy online and pick up in store module uses integration with Bing Maps application programming interfaces (APIs) to find nearby stores or stores in another location that the customer specifies.</span></span>

<span data-ttu-id="48349-119">Um módulo da caixa de compra requer uma ID de produto.</span><span class="sxs-lookup"><span data-stu-id="48349-119">A buy box module requires a product ID.</span></span> <span data-ttu-id="48349-120">Essa ID é derivada do contexto de página.</span><span class="sxs-lookup"><span data-stu-id="48349-120">This ID is derived from the page context.</span></span> <span data-ttu-id="48349-121">Se um módulo de caixa de compra for adicionado a uma página em que o contexto da página não inclua um ID do produto, ele não renderizará as informações corretamente.</span><span class="sxs-lookup"><span data-stu-id="48349-121">If a buy box module is added to a page where the page context doesn't include a product ID, it won't render the information correctly.</span></span>

## <a name="product-specifications-module"></a><span data-ttu-id="48349-122">Módulo de especificações do produto</span><span class="sxs-lookup"><span data-stu-id="48349-122">Product specifications module</span></span>

<span data-ttu-id="48349-123">O módulo de especificações de produto pode ser usado para apresentar detalhes adicionais sobre o produto.</span><span class="sxs-lookup"><span data-stu-id="48349-123">The product specifications module can be used to showcase additional details about the product.</span></span> <span data-ttu-id="48349-124">Esses detalhes são obtidos dos atributos do produto no Commerce.</span><span class="sxs-lookup"><span data-stu-id="48349-124">These details are taken from product attributes in Commerce.</span></span> <span data-ttu-id="48349-125">O módulo de especificações do produto mostra cada atributo onde a propriedade **visível** é definida como **verdadeiro**.</span><span class="sxs-lookup"><span data-stu-id="48349-125">The product specifications module shows every attribute where the **visible** property is set to **true**.</span></span> <span data-ttu-id="48349-126">Requer uma ID de produto para recuperar os atributos do produto.</span><span class="sxs-lookup"><span data-stu-id="48349-126">It requires a product ID to retrieve the product attributes.</span></span>

## <a name="recommendations-module"></a><span data-ttu-id="48349-127">Módulo de recomendações</span><span class="sxs-lookup"><span data-stu-id="48349-127">Recommendations module</span></span>

<span data-ttu-id="48349-128">O módulo de recomendações é um módulo importante em uma PDP.</span><span class="sxs-lookup"><span data-stu-id="48349-128">The recommendations module is an important module on a PDP.</span></span> <span data-ttu-id="48349-129">Enquanto os clientes procuram produtos, mais opções de produtos devem ser apresentadas a eles, para que eles possam encontrar o produto correto e fazer uma compra.</span><span class="sxs-lookup"><span data-stu-id="48349-129">While customers browse for products, more product options should be presented to them, so that they can find the correct product and make a purchase.</span></span> <span data-ttu-id="48349-130">As recomendações ajudam os clientes a descobrir facilmente o conteúdo relacionado e continuar comprando.</span><span class="sxs-lookup"><span data-stu-id="48349-130">Recommendations help customers easily discover related content and continue to shop.</span></span>

<span data-ttu-id="48349-131">Diferentes tipos de listas de recomendações estão disponíveis:</span><span class="sxs-lookup"><span data-stu-id="48349-131">Different types of recommendation lists are available:</span></span>

- <span data-ttu-id="48349-132">A lista **As pessoas também gostam de** é baseada no aprendizado de máquina.</span><span class="sxs-lookup"><span data-stu-id="48349-132">The **People also like** list is based on machine learning.</span></span> <span data-ttu-id="48349-133">Ela usa o histórico de transações de outros clientes para fornecer recomendações.</span><span class="sxs-lookup"><span data-stu-id="48349-133">It uses the transaction history of other customers to provide recommendations.</span></span> <span data-ttu-id="48349-134">Essa lista é gerada pelo serviço de recomendações e se parece com as listas "Clientes que compraram isso também compraram ...".</span><span class="sxs-lookup"><span data-stu-id="48349-134">This list is generated by the recommendations service and resembles "Customers who bought this also bought..." lists.</span></span> <span data-ttu-id="48349-135">Uma ID de produtos é necessária para gerar esta lista.</span><span class="sxs-lookup"><span data-stu-id="48349-135">A product ID is required to generate this list.</span></span>
- <span data-ttu-id="48349-136">Uma lista **Relacionada** pode ser configurada para um produto no Commerce.</span><span class="sxs-lookup"><span data-stu-id="48349-136">A **Related** list can be configured for a product in Commerce.</span></span> <span data-ttu-id="48349-137">Por exemplo, para uma bolsa de viagem de couro marrom, mais bolsas de couro ou projetadas para viagem podem ser configuradas para a lista relacionada.</span><span class="sxs-lookup"><span data-stu-id="48349-137">For example, for a brown leather travel handbag, more handbags that are leather-based or designed for travel purposes can be configured for the related list.</span></span> <span data-ttu-id="48349-138">Outros tipos de listas relacionadas, como **Acessórios** e **Mais deste tipo**, também podem ser configurados no Commerce.</span><span class="sxs-lookup"><span data-stu-id="48349-138">Other types of related lists, such as **Accessories** and **More like this**, can also be configured in Commerce.</span></span> <span data-ttu-id="48349-139">Uma ID de produtos é necessária para gerar esta lista.</span><span class="sxs-lookup"><span data-stu-id="48349-139">A product ID is required to generate this list.</span></span> <span data-ttu-id="48349-140">Portanto, se ele for adicionado a uma página inicial, em que o contexto da página não inclua uma ID do produto, a lista ficará vazia.</span><span class="sxs-lookup"><span data-stu-id="48349-140">Therefore, if it's added to a home page, where the page context doesn't include a product ID, the list will be empty.</span></span>
- <span data-ttu-id="48349-141">Listas de recomendações geradas algoritmicamente, como **Mais Populares**, **Mais Vendidos** e **Novo** podem ser usadas em PDPs.</span><span class="sxs-lookup"><span data-stu-id="48349-141">Algorithmically generated recommendation lists, such as **Trending**, **Best Selling**, and **New**, can be used on PDPs.</span></span> <span data-ttu-id="48349-142">Embora essas listas possam não estar diretamente relacionadas ao produto na PDP, elas são outra maneira de ajudar os clientes a encontrar produtos que possam interessá-los.</span><span class="sxs-lookup"><span data-stu-id="48349-142">Although these lists might not be directly related to the product on the PDP, they are another way to help customers find products that might interest them.</span></span> <span data-ttu-id="48349-143">Esses tipos de listas não exigem uma ID de produto.</span><span class="sxs-lookup"><span data-stu-id="48349-143">These types of lists don't require a product ID.</span></span> <span data-ttu-id="48349-144">São listas genéricas que são geradas com base nos padrões de compras no site.</span><span class="sxs-lookup"><span data-stu-id="48349-144">They are generic lists that are generated based on shopping patterns across the site.</span></span>
- <span data-ttu-id="48349-145">As listas editoriais são listas selecionadas manualmente.</span><span class="sxs-lookup"><span data-stu-id="48349-145">Editorial lists are manually curated lists.</span></span> <span data-ttu-id="48349-146">Por exemplo, um fornecedor pode decidir selecionar as listas de produtos manualmente que ele deseja mostrar.</span><span class="sxs-lookup"><span data-stu-id="48349-146">For example, a retailer might decide to manually curate lists of products that it wants to showcase.</span></span>

## <a name="ratings-and-reviews-modules"></a><span data-ttu-id="48349-147">Módulos de classificações e revisões</span><span class="sxs-lookup"><span data-stu-id="48349-147">Ratings and reviews modules</span></span>

<span data-ttu-id="48349-148">Três módulos podem ser usados para mostrar e adicionar revisões:</span><span class="sxs-lookup"><span data-stu-id="48349-148">Three modules can be used to show and add reviews:</span></span>

- <span data-ttu-id="48349-149">**Revisões** – este módulo lista classificações e revisões fornecidas por outros clientes.</span><span class="sxs-lookup"><span data-stu-id="48349-149">**Reviews** – This module lists ratings and reviews that have been provided by other customers.</span></span> <span data-ttu-id="48349-150">Os clientes podem classificar e filtrar as revisões.</span><span class="sxs-lookup"><span data-stu-id="48349-150">Customers can sort and filter the reviews.</span></span> <span data-ttu-id="48349-151">Este módulo também permite que os clientes gostem ou não das revisões e relatem problemas.</span><span class="sxs-lookup"><span data-stu-id="48349-151">This module also lets customers like or dislike reviews, and report issues.</span></span>
- <span data-ttu-id="48349-152">**Escrever revisão** – este módulo permite que os clientes escrevam suas próprias revisões de um produto.</span><span class="sxs-lookup"><span data-stu-id="48349-152">**Write review** – This module lets customers write their own reviews of a product.</span></span>
- <span data-ttu-id="48349-153">**Histograma de classificações** – este módulo inclui um histograma que mostra a tendência de classificações de um produto.</span><span class="sxs-lookup"><span data-stu-id="48349-153">**Ratings histogram** – This module includes a histogram that shows the ratings trend for a product.</span></span>

<span data-ttu-id="48349-154">Para obter mais detalhes, consulte [Visão geral de classificações e opiniões](ratings-reviews-overview.md).</span><span class="sxs-lookup"><span data-stu-id="48349-154">For more details, see [Ratings and reviews overview](ratings-reviews-overview.md).</span></span>

## <a name="marketing-modules"></a><span data-ttu-id="48349-155">Módulos de marketing</span><span class="sxs-lookup"><span data-stu-id="48349-155">Marketing modules</span></span>

<span data-ttu-id="48349-156">Se o conteúdo de marketing for exclusivo de um produto específico, qualquer módulo de marketing poderá ser adicionado à PDP.</span><span class="sxs-lookup"><span data-stu-id="48349-156">If marketing content is unique to a specific product, any marketing module can be added to the PDP.</span></span> <span data-ttu-id="48349-157">Você pode adicionar os módulos de marketing para uma PDP "enriquecendo" a página.</span><span class="sxs-lookup"><span data-stu-id="48349-157">You can add marketing modules to a PDP by "enriching" the page.</span></span> <span data-ttu-id="48349-158">Para obter mais detalhes, consulte [Enriquecer uma página de produto](enrich-product-page.md).</span><span class="sxs-lookup"><span data-stu-id="48349-158">For more details, see [Enrich a product page](enrich-product-page.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="48349-159">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="48349-159">Additional resources</span></span>

[<span data-ttu-id="48349-160">Visão geral da home page</span><span class="sxs-lookup"><span data-stu-id="48349-160">Home page overview</span></span>](quick-tour-home-page.md)

[<span data-ttu-id="48349-161">Visão geral das páginas de carrinho e de finalização da compra</span><span class="sxs-lookup"><span data-stu-id="48349-161">Cart and checkout pages overview</span></span>](quick-tour-cart-checkout.md)

[<span data-ttu-id="48349-162">Visão geral das páginas de gerenciamento da conta</span><span class="sxs-lookup"><span data-stu-id="48349-162">Account management pages overview</span></span>](quick-tour-account-management.md)

[<span data-ttu-id="48349-163">Enriquecer uma página de detalhes de produto</span><span class="sxs-lookup"><span data-stu-id="48349-163">Enrich a product details page</span></span>](enrich-product-page.md)
