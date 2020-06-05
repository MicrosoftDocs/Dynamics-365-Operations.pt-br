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
ms.openlocfilehash: 460d05ca29d5b8da70a971a649d9edd786f7260d
ms.sourcegitcommit: 15c5ec742d648c5f3506d031a2ab6150dcbae348
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/15/2020
ms.locfileid: "3378199"
---
# <a name="store-selector-module"></a><span data-ttu-id="602d3-103">Módulo de seletor de loja</span><span class="sxs-lookup"><span data-stu-id="602d3-103">Store selector module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="602d3-104">Este tópico abrange o módulo de seletor de loja e descreve como adicioná-lo às páginas do site no Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="602d3-104">This topic covers the store selector module and describes how to add it to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="602d3-105">Visão Geral</span><span class="sxs-lookup"><span data-stu-id="602d3-105">Overview</span></span>

<span data-ttu-id="602d3-106">Um módulo de seletor de loja é usado para o cenário de cliente "compre online, retire na loja" (buy online, pick up in store - BOPIS).</span><span class="sxs-lookup"><span data-stu-id="602d3-106">A store selector module is used for the "buy online, pick up in store"" (BOPIS) customer scenario.</span></span> <span data-ttu-id="602d3-107">Ele exibe uma lista de lojas onde um produto está disponível para retirada, além de horários e estoque de produtos de cada loja.</span><span class="sxs-lookup"><span data-stu-id="602d3-107">It displays a list of stores where a product is available for pickup, as well as store hours and product inventory for each store.</span></span>

<span data-ttu-id="602d3-108">O módulo de seletor de loja requer o contexto de um produto e um local de pesquisa para encontrar lojas.</span><span class="sxs-lookup"><span data-stu-id="602d3-108">The store selector module requires the context of a product and a search location to find stores.</span></span> <span data-ttu-id="602d3-109">Na ausência de um local de pesquisa, o padrão é o local do navegador do cliente, desde que o cliente dê consentimento.</span><span class="sxs-lookup"><span data-stu-id="602d3-109">In the absence of a search location, it defaults to the customer's browser location, provided that the customer gives consent.</span></span> <span data-ttu-id="602d3-110">O módulo tem uma caixa de entrada que permite ao cliente inserir um local (CEP ou cidade e estado) para encontrar lojas próximas.</span><span class="sxs-lookup"><span data-stu-id="602d3-110">The module has an input box which allows the customer to enter a location (zipcode, or city and state) to find stores that are nearby.</span></span>

<span data-ttu-id="602d3-111">O módulo de seletor de loja é integrado à interface de programação de aplicativos (API) de Geocodificação do Bing Mapas para converter o local em latitude e longitude.</span><span class="sxs-lookup"><span data-stu-id="602d3-111">The store selector module is integrated with the Bing Maps Geocoding application programming interface (API) to convert the location to a latitude and longitude.</span></span> <span data-ttu-id="602d3-112">Uma chave de API do Bing Mapas é necessária e deve ser adicionada à página parâmetros compartilhados de comércio no Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="602d3-112">A Bing Maps API key is required and must be added to the Commerce shared parameters page in Dynamics 365 Commerce.</span></span>

<span data-ttu-id="602d3-113">O módulo de seletor de loja pode ser adicionado a um módulo de caixa de compra na página de detalhes do produto (PDP) para exibir as lojas onde um produto está disponível para retirada.</span><span class="sxs-lookup"><span data-stu-id="602d3-113">The store selector module can be added to a buy box module on the product details page (PDP) to display stores where a product is available for pickup.</span></span> <span data-ttu-id="602d3-114">Também pode ser adicionado a um módulo de carrinho.</span><span class="sxs-lookup"><span data-stu-id="602d3-114">It can also be added to a cart module.</span></span> <span data-ttu-id="602d3-115">Quando adicionado a um módulo de carrinho, o módulo de seletor de loja exibe opções de retirada para cada item de linha do carrinho.</span><span class="sxs-lookup"><span data-stu-id="602d3-115">When added to a cart module, the store selector module displays pickup options for each cart line item.</span></span> <span data-ttu-id="602d3-116">Além disso, com a codificação personalizada, esse módulo pode ser adicionado a outras páginas ou módulos por meio de extensões e personalizações.</span><span class="sxs-lookup"><span data-stu-id="602d3-116">In addition, with custom coding this module can be added to other pages or modules via extensions and customizations.</span></span>

<span data-ttu-id="602d3-117">Para que o cenário BOPIS funcione, os produtos devem ser configurados com o modo de entrega "retirada do cliente".</span><span class="sxs-lookup"><span data-stu-id="602d3-117">For the BOPIS scenario to work, products should be configured with the "customer pickup" delivery mode.</span></span> <span data-ttu-id="602d3-118">Caso contrário, o módulo não será mostrado nas respectivas páginas.</span><span class="sxs-lookup"><span data-stu-id="602d3-118">Otherwise, the module will not be shown on the respective pages.</span></span> <span data-ttu-id="602d3-119">Para detalhes sobre como configurar o modo de entrega, consulte [Configurar os modos de entrega](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/set-up-modes-of-delivery).</span><span class="sxs-lookup"><span data-stu-id="602d3-119">For details on how to configure the delivery mode, see [Set up modes of delivery](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/set-up-modes-of-delivery).</span></span>

<span data-ttu-id="602d3-120">A imagem a seguir mostra um exemplo de um módulo de seletor de loja usado em uma PDP.</span><span class="sxs-lookup"><span data-stu-id="602d3-120">The following image shows an example of a store selector module used on a PDP.</span></span>

![Exemplo de um módulo de seletor de loja](./media/BOPIS.PNG)

## <a name="store-selector-module-usage-in-e-commerce"></a><span data-ttu-id="602d3-122">Uso do módulo de seletor de loja no comércio eletrônico</span><span class="sxs-lookup"><span data-stu-id="602d3-122">Store selector module usage in e-Commerce</span></span>

- <span data-ttu-id="602d3-123">Um módulo de seletor de loja pode ser usado em uma página de detalhes do produto (PDP) na pesquisa de lojas próximas onde um produto está disponível para retirada.</span><span class="sxs-lookup"><span data-stu-id="602d3-123">A store selector module can be used on a product details page (PDP) to find nearby stores where a product is available for pickup.</span></span>
- <span data-ttu-id="602d3-124">Um módulo de seletor de loja pode ser usado em uma página do carrinho na pesquisa de lojas próximas onde um produto no carrinho está disponível para retirada.</span><span class="sxs-lookup"><span data-stu-id="602d3-124">A store selector module can be used on a cart page to find nearby stores where a product in the cart is available for pickup.</span></span>

## <a name="store-selector-module-properties"></a><span data-ttu-id="602d3-125">Propriedades do módulo de seletor de loja</span><span class="sxs-lookup"><span data-stu-id="602d3-125">Store selector module properties</span></span>

| <span data-ttu-id="602d3-126">Nome da propriedade</span><span class="sxs-lookup"><span data-stu-id="602d3-126">Property name</span></span>             | <span data-ttu-id="602d3-127">Alíquota</span><span class="sxs-lookup"><span data-stu-id="602d3-127">Value</span></span>                 | <span data-ttu-id="602d3-128">descrição</span><span class="sxs-lookup"><span data-stu-id="602d3-128">Description</span></span> |
|---------------------------|-----------------------|-------------|
| <span data-ttu-id="602d3-129">Pesquisar raio</span><span class="sxs-lookup"><span data-stu-id="602d3-129">Search radius</span></span> | <span data-ttu-id="602d3-130">Número</span><span class="sxs-lookup"><span data-stu-id="602d3-130">Number</span></span> | <span data-ttu-id="602d3-131">Define o raio de pesquisa para lojas, em milhas.</span><span class="sxs-lookup"><span data-stu-id="602d3-131">Defines the search radius for stores, in miles.</span></span> <span data-ttu-id="602d3-132">Se nenhum valor for especificado, o raio de pesquisa padrão de 50 milhas será usado.</span><span class="sxs-lookup"><span data-stu-id="602d3-132">If no value is specified, the default search radius of 50 miles is used.</span></span>|
|<span data-ttu-id="602d3-133">Termos de Serviço</span><span class="sxs-lookup"><span data-stu-id="602d3-133">Terms of Service</span></span> | <span data-ttu-id="602d3-134">URL</span><span class="sxs-lookup"><span data-stu-id="602d3-134">URL</span></span>    |  <span data-ttu-id="602d3-135">A URL dos termos de serviço necessária para o serviço Bing Mapas.</span><span class="sxs-lookup"><span data-stu-id="602d3-135">The terms of service URL that is required for the Bing Maps service.</span></span> |

## <a name="add-a-store-selector-module-to-a-page"></a><span data-ttu-id="602d3-136">Adicionar um módulo de seletor de loja a uma página</span><span class="sxs-lookup"><span data-stu-id="602d3-136">Add a store selector module to a page</span></span>

<span data-ttu-id="602d3-137">Um módulo de seletor de loja precisa do contexto de um produto, para que ele possa ser usado apenas nos módulos de caixa de compra e carrinho.</span><span class="sxs-lookup"><span data-stu-id="602d3-137">A store selector module needs the context of a product, so it can only be used within buy box and cart modules.</span></span> <span data-ttu-id="602d3-138">Os módulos de seletor de loja não funcionam fora desses módulos.</span><span class="sxs-lookup"><span data-stu-id="602d3-138">Store selector modules do not function outside these modules.</span></span>

- <span data-ttu-id="602d3-139">Para obter informações sobre como adicionar um módulo de seletor de loja a um módulo de caixa de compra, consulte [Módulo de caixa de compra](add-buy-box.md).</span><span class="sxs-lookup"><span data-stu-id="602d3-139">For information on how to add a store selector module to a buy box module, see [Buy box module](add-buy-box.md).</span></span> 
- <span data-ttu-id="602d3-140">Para obter informações sobre como adicionar um módulo de seletor de loja a um módulo de carrinho, consulte [Módulo de carrinho](add-cart-module.md)</span><span class="sxs-lookup"><span data-stu-id="602d3-140">For information on how to add a store selector module to a cart module, see [Cart module](add-cart-module.md)</span></span>

## <a name="additional-resources"></a><span data-ttu-id="602d3-141">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="602d3-141">Additional resources</span></span>

[<span data-ttu-id="602d3-142">Visão geral do kit de início</span><span class="sxs-lookup"><span data-stu-id="602d3-142">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="602d3-143">Módulo de caixa de compra</span><span class="sxs-lookup"><span data-stu-id="602d3-143">Buy box module</span></span>](add-buy-box.md)

[<span data-ttu-id="602d3-144">Módulo de carrinho</span><span class="sxs-lookup"><span data-stu-id="602d3-144">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="602d3-145">Tour rápido da PDP</span><span class="sxs-lookup"><span data-stu-id="602d3-145">Quick tour of PDP</span></span>](quick-tour-pdp.md)

[<span data-ttu-id="602d3-146">Tour rápido do carrinho e do check-out</span><span class="sxs-lookup"><span data-stu-id="602d3-146">Quick tour of Cart and checkout</span></span>](quick-tour-cart-checkout.md)

[<span data-ttu-id="602d3-147">Configurar os modos de entrega</span><span class="sxs-lookup"><span data-stu-id="602d3-147">Set up modes of delivery</span></span>](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/set-up-modes-of-delivery)

[<span data-ttu-id="602d3-148">Gerenciar o Bing Maps da sua organização</span><span class="sxs-lookup"><span data-stu-id="602d3-148">Manage Bing Maps for your organization</span></span>](dev-itpro/manage-bing-maps.md)
