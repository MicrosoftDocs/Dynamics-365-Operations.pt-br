---
title: Módulo de exibição rápida
description: Este tópico abrange os módulos de exibição rápida e descreve como adicioná-los a páginas de site no Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 01/28/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2020-01-08
ms.dyn365.ops.version: Release 10.0.17
ms.openlocfilehash: d7e88163fd9b8dc4f5636ed29e2c4248aece52bf
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5792162"
---
# <a name="quick-view-module"></a><span data-ttu-id="0c636-103">Módulo de exibição rápida</span><span class="sxs-lookup"><span data-stu-id="0c636-103">Quick view module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="0c636-104">Este tópico abrange os módulos de exibição rápida e descreve como adicioná-los a páginas de site no Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="0c636-104">This topic covers quick view modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="0c636-105">O módulo de exibição rápida permite que os usuários visualizem rapidamente as informações do produto quando pesquisam produtos em uma página de lista e adicionem um ou mais produtos ao carrinho da página da lista, sem precisarem ir à página de detalhes do produto (PDP).</span><span class="sxs-lookup"><span data-stu-id="0c636-105">The quick view module lets users quickly view product information when they browse products on a list page, and add one or more products to the cart from the list page, without having to go to the product details page (PDP).</span></span> <span data-ttu-id="0c636-106">O módulo de exibição rápida fornece uma visão geral das informações sobre o produto de que os usuários precisam para criar uma decisão de "adicionar ao carrinho".</span><span class="sxs-lookup"><span data-stu-id="0c636-106">The quick view module provides an overview of the product information that users require to make an "add to cart" decision.</span></span> <span data-ttu-id="0c636-107">Ele também fornece um link para a PDP, de forma que os usuários possam ver mais detalhes e opções de compra dos produtos.</span><span class="sxs-lookup"><span data-stu-id="0c636-107">It also provides a link to the PDP, so that users can view additional product details and purchase options.</span></span>

<span data-ttu-id="0c636-108">O módulo de exibição rápida é compatível com os módulos [coleção de produtos](product-collection-module-overview.md) e [resultados de pesquisa](search-result-module.md).</span><span class="sxs-lookup"><span data-stu-id="0c636-108">The quick view module is supported by the [product collection](product-collection-module-overview.md) and [search results](search-result-module.md) modules.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0c636-109">O módulo de exibição rápida está disponível a partir do Commerce versão 10.0.17.</span><span class="sxs-lookup"><span data-stu-id="0c636-109">The quick view module is available as of the Commerce version 10.0.17 release.</span></span>

<span data-ttu-id="0c636-110">A ilustração a seguir mostra um exemplo de um módulo de exibição rápida em uma página de lista de produtos.</span><span class="sxs-lookup"><span data-stu-id="0c636-110">The following illustration shows an example of a quick view module on a product list page.</span></span>

![Exemplo de um módulo de exibição rápida em uma página de lista de produtos](./media/ecommerce-quickview.PNG)

## <a name="module-properties"></a><span data-ttu-id="0c636-112">Propriedades do módulo</span><span class="sxs-lookup"><span data-stu-id="0c636-112">Module properties</span></span>

<span data-ttu-id="0c636-113">O módulo de exibição rápida oferece suporte a algumas das mesmas funções que o módulo de caixa de compra.</span><span class="sxs-lookup"><span data-stu-id="0c636-113">The quick view module supports some of the same functions as the buy box module.</span></span> <span data-ttu-id="0c636-114">Portanto, as propriedades de um módulo de exibição rápida são parecidas com as propriedades de um módulo de caixa de compra.</span><span class="sxs-lookup"><span data-stu-id="0c636-114">Therefore, the properties of a quick view module resemble the properties of a buy box module.</span></span>

| <span data-ttu-id="0c636-115">Propriedade</span><span class="sxs-lookup"><span data-stu-id="0c636-115">Property</span></span> | <span data-ttu-id="0c636-116">Valores</span><span class="sxs-lookup"><span data-stu-id="0c636-116">Values</span></span> | <span data-ttu-id="0c636-117">descrição</span><span class="sxs-lookup"><span data-stu-id="0c636-117">Description</span></span> |
|----------------|--------|-------------|
| <span data-ttu-id="0c636-118">Marca do título</span><span class="sxs-lookup"><span data-stu-id="0c636-118">Heading tag</span></span> | <span data-ttu-id="0c636-119">**H1**, **H2**, **H3**, **H4**, **H5** ou **H6**</span><span class="sxs-lookup"><span data-stu-id="0c636-119">**H1**, **H2**, **H3**, **H4**, **H5**, or **H6**</span></span> | <span data-ttu-id="0c636-120">Esta propriedade define a marca do título para o título do produto.</span><span class="sxs-lookup"><span data-stu-id="0c636-120">This property defines the heading tag for the product title.</span></span> <span data-ttu-id="0c636-121">Se o módulo de exibição rápida estiver na parte superior da página, essa propriedade deverá ser definida como **H1** para atender aos padrões de acessibilidade.</span><span class="sxs-lookup"><span data-stu-id="0c636-121">If the quick view module is at the top of the page, this property should be set to **H1** to meet accessibility standards.</span></span> |
| <span data-ttu-id="0c636-122">Permitir preço personalizado</span><span class="sxs-lookup"><span data-stu-id="0c636-122">Allow custom price</span></span> | <span data-ttu-id="0c636-123">**Verdadeiro** ou **Falso**</span><span class="sxs-lookup"><span data-stu-id="0c636-123">**True** or **False**</span></span> | <span data-ttu-id="0c636-124">Se esta propriedade for definida como **Verdadeiro**, o usuário poderá inserir um preço personalizado.</span><span class="sxs-lookup"><span data-stu-id="0c636-124">If this property is set to **True**, the user can enter a custom price.</span></span> |
| <span data-ttu-id="0c636-125">Preço mínimo</span><span class="sxs-lookup"><span data-stu-id="0c636-125">Minimum price</span></span> | <span data-ttu-id="0c636-126">Inteiro</span><span class="sxs-lookup"><span data-stu-id="0c636-126">Integer</span></span> | <span data-ttu-id="0c636-127">Esta propriedade será aplicável somente se a propriedade **Permitir preço personalizado** estiver definida como **Verdadeiro**.</span><span class="sxs-lookup"><span data-stu-id="0c636-127">This property is applicable only if the **Allow custom price** property is set to **True**.</span></span> <span data-ttu-id="0c636-128">Ela define o preço mínimo que o usuário pode inserir (por exemplo, US$ 1).</span><span class="sxs-lookup"><span data-stu-id="0c636-128">It defines the minimum price that the user can enter (for example, $1).</span></span> |
| <span data-ttu-id="0c636-129">Preço máximo</span><span class="sxs-lookup"><span data-stu-id="0c636-129">Maximum price</span></span> | <span data-ttu-id="0c636-130">Inteiro</span><span class="sxs-lookup"><span data-stu-id="0c636-130">Integer</span></span> | <span data-ttu-id="0c636-131">Esta propriedade será aplicável somente se a propriedade **Permitir preço personalizado** estiver definida como **Verdadeiro**.</span><span class="sxs-lookup"><span data-stu-id="0c636-131">This property is applicable only if the **Allow custom price** property is set to **True**.</span></span> <span data-ttu-id="0c636-132">Ela define o preço máximo que o usuário pode inserir (por exemplo, US$ 1.000).</span><span class="sxs-lookup"><span data-stu-id="0c636-132">It defines the maximum price that the user can enter (for example, $1,000).</span></span> |

## <a name="commerce-site-builder-settings"></a><span data-ttu-id="0c636-133">Configurações do construtor de sites do Commerce</span><span class="sxs-lookup"><span data-stu-id="0c636-133">Commerce site builder settings</span></span>

<span data-ttu-id="0c636-134">Assim como o módulo de caixa de compra, o módulo de exibição rápida respeita as configurações em **Configurações do site \> Extensões \> Adicionar produto ao carrinho**.</span><span class="sxs-lookup"><span data-stu-id="0c636-134">Like the buy box module, the quick view module respects the settings at **Site Settings \> Extensions \> Add product to cart**.</span></span> <span data-ttu-id="0c636-135">No entanto, a configuração **Navegar para a página do carrinho** é ignorada, pois ela é inconsistente com a finalidade do módulo de exibição rápida, que permite que os usuários pesquisem vários produtos em uma página de lista e os adicionem ao carrinho sem sair da página de lista.</span><span class="sxs-lookup"><span data-stu-id="0c636-135">However, the **Navigate to cart page** setting is ignored, because it's inconsistent with the purpose of the quick view module, which is to enable users to browse multiple products on a list page and add them to the cart without moving away from the list page.</span></span>

## <a name="add-a-quick-view-module-to-a-product-collection-module"></a><span data-ttu-id="0c636-136">Adicionar um módulo de exibição rápida a um módulo de coleção de produtos</span><span class="sxs-lookup"><span data-stu-id="0c636-136">Add a quick view module to a product collection module</span></span>

<span data-ttu-id="0c636-137">É possível adicionar um módulo de exibição rápida aos módulos coleção de produtos e resultados de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="0c636-137">A quick view module can be added to the product collection and search results modules.</span></span>

<span data-ttu-id="0c636-138">Para adicionar um módulo de exibição rápida a um módulo de coleção de produtos no construtor de sites do Commerce, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="0c636-138">To add a quick view module to a product collection module in Commerce site builder, follow these steps.</span></span>

1. <span data-ttu-id="0c636-139">Vá para **Páginas** e selecione a página inicial do site da Fabrikam.</span><span class="sxs-lookup"><span data-stu-id="0c636-139">Go to **Pages**, and then select the home page for the Fabrikam site.</span></span>
1. <span data-ttu-id="0c636-140">Vá para qualquer módulo de **Coleção de produtos** na página inicial, selecione as reticências (**...**) e depois **Adicionar módulo**.</span><span class="sxs-lookup"><span data-stu-id="0c636-140">Go to any **Product Collection** module on the homepage, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="0c636-141">Na caixa de diálogo **Adicionar Módulo**, selecione o módulo **Exibição rápida** e depois **OK**.</span><span class="sxs-lookup"><span data-stu-id="0c636-141">In the **Add Module** dialog box, select the **Quick View** module, and then select **OK**.</span></span>
1. <span data-ttu-id="0c636-142">No painel propriedades do módulo **Exibição rápida**, selecione **Título**.</span><span class="sxs-lookup"><span data-stu-id="0c636-142">In the properties pane of the **Quick View** module, select **Heading**.</span></span> <span data-ttu-id="0c636-143">Na caixa de diálogo **Título**, defina o campo **Nível do título** como **H2** e então selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="0c636-143">In the **Heading** dialog box, set the **Heading Level** field to **H2**, and then select **OK**.</span></span>
1. <span data-ttu-id="0c636-144">Selecione **Salvar**, **Concluir edição** para fazer check-in da página e depois selecione **Publicar** para publicá-lo.</span><span class="sxs-lookup"><span data-stu-id="0c636-144">Select **Save**, select **Finish editing** to check in the page, and then select **Publish** to publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="0c636-145">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="0c636-145">Additional resources</span></span>

[<span data-ttu-id="0c636-146">Visão geral da biblioteca de módulos</span><span class="sxs-lookup"><span data-stu-id="0c636-146">Module library overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="0c636-147">Módulo de caixa de compra</span><span class="sxs-lookup"><span data-stu-id="0c636-147">Buy box module</span></span>](add-buy-box.md)

[<span data-ttu-id="0c636-148">Módulos de coleta de produtos</span><span class="sxs-lookup"><span data-stu-id="0c636-148">Product collection module</span></span>](product-collection-module-overview.md)

[<span data-ttu-id="0c636-149">Módulo de resultados de pesquisa</span><span class="sxs-lookup"><span data-stu-id="0c636-149">Search results module</span></span>](search-result-module.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
