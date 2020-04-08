---
title: Módulo de seletor de loja
description: Este tópico abrange o módulo de seletor de loja e descreve como adicioná-lo às páginas do site no Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 03/19/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2020-02-10
ms.dyn365.ops.version: ''
ms.openlocfilehash: 8efc2345ded52bfaee2d400815795906f326f4fd
ms.sourcegitcommit: de5af1912201dd70aa85fdcad0b184c42405802e
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/21/2020
ms.locfileid: "3157331"
---
# <a name="store-selector-module"></a><span data-ttu-id="b3fd8-103">Módulo de seletor de loja</span><span class="sxs-lookup"><span data-stu-id="b3fd8-103">Store selector module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="b3fd8-104">Este tópico abrange o módulo de seletor de loja e descreve como adicioná-lo às páginas do site no Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="b3fd8-104">This topic covers the store selector module and describes how to add it to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="b3fd8-105">Visão Geral</span><span class="sxs-lookup"><span data-stu-id="b3fd8-105">Overview</span></span>

<span data-ttu-id="b3fd8-106">Um módulo de seletor de loja é usado para o cenário de cliente "compre online, retire na loja" (buy online, pick up in store - BOPIS).</span><span class="sxs-lookup"><span data-stu-id="b3fd8-106">A store selector module is used for the "buy online, pick up in store"" (BOPIS) customer scenario.</span></span> <span data-ttu-id="b3fd8-107">Ele exibe uma lista de lojas onde um produto está disponível para retirada, além de horários e estoque de produtos de cada loja.</span><span class="sxs-lookup"><span data-stu-id="b3fd8-107">It displays a list of stores where a product is available for pickup, as well as store hours and product inventory for each store.</span></span>

<span data-ttu-id="b3fd8-108">O módulo de seletor de loja requer o contexto de um produto e um local de pesquisa para encontrar lojas.</span><span class="sxs-lookup"><span data-stu-id="b3fd8-108">The store selector module requires the context of a product and a search location to find stores.</span></span> <span data-ttu-id="b3fd8-109">Na ausência de um local de pesquisa, o padrão é o local do navegador do cliente, desde que o cliente dê consentimento.</span><span class="sxs-lookup"><span data-stu-id="b3fd8-109">In the absence of a search location, it defaults to the customer's browser location, provided that the customer gives consent.</span></span> <span data-ttu-id="b3fd8-110">O módulo tem uma caixa de entrada que permite ao cliente inserir um local (CEP ou cidade e estado) para encontrar lojas próximas.</span><span class="sxs-lookup"><span data-stu-id="b3fd8-110">The module has an input box which allows the customer to enter a location (zipcode, or city and state) to find stores that are nearby.</span></span>

<span data-ttu-id="b3fd8-111">O módulo de seletor de loja é integrado à interface de programação de aplicativos (API) de Geocodificação do Bing Mapas para converter o local em latitude e longitude.</span><span class="sxs-lookup"><span data-stu-id="b3fd8-111">The store selector module is integrated with the Bing Maps Geocoding application programming interface (API) to convert the location to a latitude and longitude.</span></span> <span data-ttu-id="b3fd8-112">Uma chave de API do Bing Mapas é necessária e deve ser adicionada à página parâmetros compartilhados de comércio no Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="b3fd8-112">A Bing Maps API key is required and must be added to the Commerce shared parameters page in Dynamics 365 Commerce.</span></span>

<span data-ttu-id="b3fd8-113">O módulo de seletor de loja pode ser adicionado a um módulo de caixa de compra na página de detalhes do produto (PDP) para exibir as lojas onde um produto está disponível para retirada.</span><span class="sxs-lookup"><span data-stu-id="b3fd8-113">The store selector module can be added to a buy box module on the product details page (PDP) to display stores where a product is available for pickup.</span></span> <span data-ttu-id="b3fd8-114">Também pode ser adicionado a um módulo de carrinho.</span><span class="sxs-lookup"><span data-stu-id="b3fd8-114">It can also be added to a cart module.</span></span> <span data-ttu-id="b3fd8-115">Quando adicionado a um módulo de carrinho, o módulo de seletor de loja exibe opções de retirada para cada item de linha do carrinho.</span><span class="sxs-lookup"><span data-stu-id="b3fd8-115">When added to a cart module, the store selector module displays pickup options for each cart line item.</span></span> <span data-ttu-id="b3fd8-116">Além disso, com a codificação personalizada, esse módulo pode ser adicionado a outras páginas ou módulos por meio de extensões e personalizações.</span><span class="sxs-lookup"><span data-stu-id="b3fd8-116">In addition, with custom coding this module can be added to other pages or modules via extensions and customizations.</span></span>

<span data-ttu-id="b3fd8-117">Para que o cenário BOPIS funcione, os produtos devem ser configurados com o modo de entrega "retirada do cliente".</span><span class="sxs-lookup"><span data-stu-id="b3fd8-117">For the BOPIS scenario to work, products should be configured with the "customer pickup" delivery mode.</span></span> <span data-ttu-id="b3fd8-118">Caso contrário, o módulo não será mostrado nas respectivas páginas.</span><span class="sxs-lookup"><span data-stu-id="b3fd8-118">Otherwise, the module will not be shown on the respective pages.</span></span> <span data-ttu-id="b3fd8-119">Para detalhes sobre como configurar o modo de entrega, consulte [Configurar os modos de entrega](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/set-up-modes-of-delivery).</span><span class="sxs-lookup"><span data-stu-id="b3fd8-119">For details on how to configure the delivery mode, see [Set up modes of delivery](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/set-up-modes-of-delivery).</span></span>

<span data-ttu-id="b3fd8-120">A imagem a seguir mostra um exemplo de um módulo de seletor de loja usado em uma PDP.</span><span class="sxs-lookup"><span data-stu-id="b3fd8-120">The following image shows an example of a store selector module used on a PDP.</span></span>

![Exemplo de um módulo de seletor de loja](./media/BOPIS.PNG)

## <a name="store-selector-module-usage-in-e-commerce"></a><span data-ttu-id="b3fd8-122">Uso do módulo de seletor de loja no comércio eletrônico</span><span class="sxs-lookup"><span data-stu-id="b3fd8-122">Store selector module usage in e-Commerce</span></span>

- <span data-ttu-id="b3fd8-123">Um módulo de seletor de loja pode ser usado em uma página de detalhes do produto (PDP) na pesquisa de lojas próximas onde um produto está disponível para retirada.</span><span class="sxs-lookup"><span data-stu-id="b3fd8-123">A store selector module can be used on a product details page (PDP) to find nearby stores where a product is available for pickup.</span></span>
- <span data-ttu-id="b3fd8-124">Um módulo de seletor de loja pode ser usado em uma página do carrinho na pesquisa de lojas próximas onde um produto no carrinho está disponível para retirada.</span><span class="sxs-lookup"><span data-stu-id="b3fd8-124">A store selector module can be used on a cart page to find nearby stores where a product in the cart is available for pickup.</span></span>

## <a name="store-selector-module-properties"></a><span data-ttu-id="b3fd8-125">Propriedades do módulo de seletor de loja</span><span class="sxs-lookup"><span data-stu-id="b3fd8-125">Store selector module properties</span></span>

| <span data-ttu-id="b3fd8-126">Nome da propriedade</span><span class="sxs-lookup"><span data-stu-id="b3fd8-126">Property name</span></span>             | <span data-ttu-id="b3fd8-127">Alíquota</span><span class="sxs-lookup"><span data-stu-id="b3fd8-127">Value</span></span>                 | <span data-ttu-id="b3fd8-128">descrição</span><span class="sxs-lookup"><span data-stu-id="b3fd8-128">Description</span></span> |
|---------------------------|-----------------------|-------------|
| <span data-ttu-id="b3fd8-129">Pesquisar raio</span><span class="sxs-lookup"><span data-stu-id="b3fd8-129">Search radius</span></span> | <span data-ttu-id="b3fd8-130">Número</span><span class="sxs-lookup"><span data-stu-id="b3fd8-130">Number</span></span> | <span data-ttu-id="b3fd8-131">Define o raio de pesquisa para lojas, em milhas.</span><span class="sxs-lookup"><span data-stu-id="b3fd8-131">Defines the search radius for stores, in miles.</span></span> <span data-ttu-id="b3fd8-132">Se nenhum valor for especificado, o raio de pesquisa padrão de 50 milhas será usado.</span><span class="sxs-lookup"><span data-stu-id="b3fd8-132">If no value is specified, the default search radius of 50 miles is used.</span></span>|
|<span data-ttu-id="b3fd8-133">Termos de Serviço</span><span class="sxs-lookup"><span data-stu-id="b3fd8-133">Terms of Service</span></span> | <span data-ttu-id="b3fd8-134">URL</span><span class="sxs-lookup"><span data-stu-id="b3fd8-134">URL</span></span>    |  <span data-ttu-id="b3fd8-135">A URL dos termos de serviço necessária para o serviço Bing Mapas.</span><span class="sxs-lookup"><span data-stu-id="b3fd8-135">The terms of service URL that is required for the Bing Maps service.</span></span> |

## <a name="add-a-store-selector-module-to-a-page"></a><span data-ttu-id="b3fd8-136">Adicionar um módulo de seletor de loja a uma página</span><span class="sxs-lookup"><span data-stu-id="b3fd8-136">Add a store selector module to a page</span></span>

<span data-ttu-id="b3fd8-137">Um módulo de seletor de loja precisa do contexto de um produto, para que ele possa ser usado apenas nos módulos de caixa de compra e carrinho.</span><span class="sxs-lookup"><span data-stu-id="b3fd8-137">A store selector module needs the context of a product, so it can only be used within buy box and cart modules.</span></span> <span data-ttu-id="b3fd8-138">Os módulos de seletor de loja não funcionam fora desses módulos.</span><span class="sxs-lookup"><span data-stu-id="b3fd8-138">Store selector modules do not function outside these modules.</span></span>

- <span data-ttu-id="b3fd8-139">Para obter informações sobre como adicionar um módulo de seletor de loja a um módulo de caixa de compra, consulte [Módulo de caixa de compra](add-buy-box.md).</span><span class="sxs-lookup"><span data-stu-id="b3fd8-139">For information on how to add a store selector module to a buy box module, see [Buy box module](add-buy-box.md).</span></span> 
- <span data-ttu-id="b3fd8-140">Para obter informações sobre como adicionar um módulo de seletor de loja a um módulo de carrinho, consulte [Módulo de carrinho](add-cart-module.md)</span><span class="sxs-lookup"><span data-stu-id="b3fd8-140">For information on how to add a store selector module to a cart module, see [Cart module](add-cart-module.md)</span></span>

## <a name="additional-resources"></a><span data-ttu-id="b3fd8-141">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="b3fd8-141">Additional resources</span></span>

[<span data-ttu-id="b3fd8-142">Visão geral do kit de início</span><span class="sxs-lookup"><span data-stu-id="b3fd8-142">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="b3fd8-143">Módulo de caixa de compra</span><span class="sxs-lookup"><span data-stu-id="b3fd8-143">Buy box module</span></span>](add-buy-box.md)

[<span data-ttu-id="b3fd8-144">Módulo de carrinho</span><span class="sxs-lookup"><span data-stu-id="b3fd8-144">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="b3fd8-145">Tour rápido da PDP</span><span class="sxs-lookup"><span data-stu-id="b3fd8-145">Quick tour of PDP</span></span>](quick-tour-pdp.md)

[<span data-ttu-id="b3fd8-146">Tour rápido do carrinho e do check-out</span><span class="sxs-lookup"><span data-stu-id="b3fd8-146">Quick tour of Cart and checkout</span></span>](quick-tour-cart-checkout.md)

[<span data-ttu-id="b3fd8-147">Configurar os modos de entrega</span><span class="sxs-lookup"><span data-stu-id="b3fd8-147">Set up modes of delivery</span></span>](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/set-up-modes-of-delivery)
