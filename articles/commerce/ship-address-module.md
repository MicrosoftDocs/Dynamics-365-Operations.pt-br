---
title: módulo de endereço de remessa
description: Este tópico abrange o módulo de endereço de remessa e explica como configurá-lo no Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 02/11/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.13
ms.openlocfilehash: e590c966ca6bd8111df5f91cbac0485afaa45c78
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5234404"
---
# <a name="shipping-address-module"></a><span data-ttu-id="802db-103">Módulo de endereço de remessa</span><span class="sxs-lookup"><span data-stu-id="802db-103">Shipping address module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="802db-104">Este tópico descreve o módulo de endereço de remessa e explica como configurá-lo no Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="802db-104">This topic describes covers the shipping address module and explains how to configure it in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="802db-105">O módulo de endereço de remessa permite que os clientes adicionem ou selecionem o endereço de remessa para uma ordem durante o o fluxo de finalização de compra.</span><span class="sxs-lookup"><span data-stu-id="802db-105">The shipping address module lets customers add or select the shipping address for an order during the checkout flow.</span></span> <span data-ttu-id="802db-106">Se o cliente estiver conectado, quaisquer endereços que foram salvos anteriormente para esse cliente serão exibidos e o cliente poderá selecionar entre eles.</span><span class="sxs-lookup"><span data-stu-id="802db-106">If a customer is signed in, any addresses that were previously saved for that customer are shown, and the customer can select among them.</span></span> <span data-ttu-id="802db-107">O cliente também pode adicionar um novo endereço.</span><span class="sxs-lookup"><span data-stu-id="802db-107">The customer can also add a new address.</span></span> <span data-ttu-id="802db-108">O módulo de endereço de remessa é usado para todos os itens em uma ordem que exija remessa.</span><span class="sxs-lookup"><span data-stu-id="802db-108">The shipping address module is used for all items on an order that require shipping.</span></span>

<span data-ttu-id="802db-109">Os formatos de endereço de remessa podem ser definidos na sede do Commerce para cada país ou região, e o módulo de endereço de remessa reforça as regras específicas do país/região.</span><span class="sxs-lookup"><span data-stu-id="802db-109">Shipping address formats can be defined in Commerce headquarters for each country or region, and the shipping address module then enforces country/region-specific rules.</span></span>

<span data-ttu-id="802db-110">Quando os clientes inserem um endereço de remessa durante o fluxo de finalização de compra, eles têm a opção de salvar o endereço como o endereço principal.</span><span class="sxs-lookup"><span data-stu-id="802db-110">When customers enter a shipping address during the checkout flow, they have the option to save the address as a primary address.</span></span> <span data-ttu-id="802db-111">Esta opção é exibida somente se o cliente estiver conectado.</span><span class="sxs-lookup"><span data-stu-id="802db-111">This option is shown only if a customer is signed in.</span></span>

<span data-ttu-id="802db-112">Embora o módulo de endereço de remessa não forneça validação de endereço, essa funcionalidade pode ser implementada por meio da personalização.</span><span class="sxs-lookup"><span data-stu-id="802db-112">Although the shipping address module doesn't provide address validation, this functionality can be implemented through customization.</span></span>

<span data-ttu-id="802db-113">A ilustração a seguir mostra um exemplo de um novo módulo de endereço de remessa em uma página de finalização de compra.</span><span class="sxs-lookup"><span data-stu-id="802db-113">The following illustration shows an example of a new shipping address module on a checkout page.</span></span>

![Exemplo de um módulo de endereço de remessa em uma página de finalização de compra](./media/ecommerce-shippingaddress.PNG)

## <a name="module-properties"></a><span data-ttu-id="802db-115">Propriedades do módulo</span><span class="sxs-lookup"><span data-stu-id="802db-115">Module properties</span></span>

| <span data-ttu-id="802db-116">Nome da propriedade</span><span class="sxs-lookup"><span data-stu-id="802db-116">Property name</span></span> | <span data-ttu-id="802db-117">Valores</span><span class="sxs-lookup"><span data-stu-id="802db-117">Values</span></span> | <span data-ttu-id="802db-118">descrição</span><span class="sxs-lookup"><span data-stu-id="802db-118">Description</span></span> |
|---------------|--------|-------------|
| <span data-ttu-id="802db-119">Cabeçalho</span><span class="sxs-lookup"><span data-stu-id="802db-119">Heading</span></span> | <span data-ttu-id="802db-120">Texto do cabeçalho e uma tag do cabeçalho (**H1**, **H2**, **H3**, **H4**, **H5** ou **H6**)</span><span class="sxs-lookup"><span data-stu-id="802db-120">Heading text and a heading tag (**H1**, **H2**, **H3**, **H4**, **H5**, or **H6**)</span></span> | <span data-ttu-id="802db-121">Um título opcional para o módulo de endereço de remessa.</span><span class="sxs-lookup"><span data-stu-id="802db-121">An optional heading for the shipping address module.</span></span> |
| <span data-ttu-id="802db-122">Mostrar tipo de endereço</span><span class="sxs-lookup"><span data-stu-id="802db-122">Show address type</span></span> | <span data-ttu-id="802db-123">**Verdadeiro** ou **Falso**</span><span class="sxs-lookup"><span data-stu-id="802db-123">**True** or **False**</span></span> | <span data-ttu-id="802db-124">Se essa propriedade opcional for definida como **Verdadeira**, um tipo de endereço, como **Residencial** ou **Comercial**, será exibido.</span><span class="sxs-lookup"><span data-stu-id="802db-124">If this optional property is set to **True**, an address type, such as **Home** or **Business**, will be shown.</span></span> <span data-ttu-id="802db-125">Se nenhum tipo de endereço for especificado, o endereço será salvo automaticamente como **Tipo**=**Outro**.</span><span class="sxs-lookup"><span data-stu-id="802db-125">If no address type is specified, the address will automatically be saved as **Type**=**Other**.</span></span> |
| <span data-ttu-id="802db-126">Habilitar a sugestão automática</span><span class="sxs-lookup"><span data-stu-id="802db-126">Enable auto suggestion</span></span>| <span data-ttu-id="802db-127">**Verdadeiro** ou **Falso**</span><span class="sxs-lookup"><span data-stu-id="802db-127">**True** or **False**</span></span> | <span data-ttu-id="802db-128">Se essa propriedade opcional for definida como **Verdadeira**, sugestões de endereço automático serão fornecidas.</span><span class="sxs-lookup"><span data-stu-id="802db-128">If this optional property is set to **True**, automatic address suggestions will be provided.</span></span> <span data-ttu-id="802db-129">Essas sugestões são desenvolvidas pelo Bing Maps.</span><span class="sxs-lookup"><span data-stu-id="802db-129">These suggestions are powered by Bing Maps.</span></span> <span data-ttu-id="802db-130">Para obter informações sobre como configurar a integração do Bing Maps para seu site, consulte [Módulo do seletor de armazenamento](store-selector.md).</span><span class="sxs-lookup"><span data-stu-id="802db-130">For information about how to set up Bing Maps integration for your site, see [Store selector module](store-selector.md).</span></span> <span data-ttu-id="802db-131">Este recurso está disponível a partir da versão 10.0.15 do Commerce.</span><span class="sxs-lookup"><span data-stu-id="802db-131">This feature is available as of the Commerce version 10.0.15 release.</span></span>|
|<span data-ttu-id="802db-132">Opções de sugestão automática</span><span class="sxs-lookup"><span data-stu-id="802db-132">Auto suggest options</span></span>| <span data-ttu-id="802db-133">Um número</span><span class="sxs-lookup"><span data-stu-id="802db-133">A number</span></span>| <span data-ttu-id="802db-134">Se as sugestões de endereço automático estiverem habilitadas, você poderá especificar opções adicionais, como o número máximo de sugestões que devem ser fornecidas.</span><span class="sxs-lookup"><span data-stu-id="802db-134">If automatic address suggestions are enabled, you can specify additional options, such as the maximum number of suggestions that should be provided.</span></span>|

## <a name="add-a-shipping-address-module-to-a-checkout-page-and-set-the-required-properties"></a><span data-ttu-id="802db-135">Adicionar um módulo de endereço de remessa a uma página de finalização da compra e definir as propriedades necessárias</span><span class="sxs-lookup"><span data-stu-id="802db-135">Add a shipping address module to a checkout page and set the required properties</span></span>

<span data-ttu-id="802db-136">Um módulo de endereço de remessa pode ser adicionado somente a um módulo de finalização da compra.</span><span class="sxs-lookup"><span data-stu-id="802db-136">A shipping address module can be added only to a checkout module.</span></span> <span data-ttu-id="802db-137">Para obter mais informações sobre como configurar o módulo endereço de remessa e adicioná-lo a uma página de finalização da compra, consulte [Módulo de finalização da compra](add-checkout-module.md).</span><span class="sxs-lookup"><span data-stu-id="802db-137">For more information about how to configure the shipping address module and add it to a checkout page, see [Checkout module](add-checkout-module.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="802db-138">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="802db-138">Additional resources</span></span>

[<span data-ttu-id="802db-139">Módulo de carrinho</span><span class="sxs-lookup"><span data-stu-id="802db-139">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="802db-140">Módulo de ícone de carrinho</span><span class="sxs-lookup"><span data-stu-id="802db-140">Cart icon module</span></span>](cart-icon-module.md)

[<span data-ttu-id="802db-141">Módulo de finalização da compra</span><span class="sxs-lookup"><span data-stu-id="802db-141">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="802db-142">Módulo de pagamento</span><span class="sxs-lookup"><span data-stu-id="802db-142">Payment module</span></span>](payment-module.md)

[<span data-ttu-id="802db-143">Módulo de opções de entrega</span><span class="sxs-lookup"><span data-stu-id="802db-143">Delivery options module</span></span>](delivery-options-module.md)

[<span data-ttu-id="802db-144">Módulo de informações de retirada</span><span class="sxs-lookup"><span data-stu-id="802db-144">Pickup information module</span></span>](pickup-info-module.md)

[<span data-ttu-id="802db-145">Módulo de detalhes da ordem</span><span class="sxs-lookup"><span data-stu-id="802db-145">Order details module</span></span>](order-confirmation-module.md)

[<span data-ttu-id="802db-146">Módulo de cartão-presente</span><span class="sxs-lookup"><span data-stu-id="802db-146">Gift card module</span></span>](add-giftcard.md)

[<span data-ttu-id="802db-147">Módulo de seletor de loja</span><span class="sxs-lookup"><span data-stu-id="802db-147">Store selector module</span></span>](store-selector.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]