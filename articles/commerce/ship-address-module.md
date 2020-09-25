---
title: módulo de endereço de remessa
description: Este tópico abrange o módulo de endereço de remessa e explica como configurá-lo no Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 08/05/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Operations, Retail, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.13
ms.openlocfilehash: 380d268ec0ba64367f090c31408eac1c54d0ff17
ms.sourcegitcommit: ae0843763a8b6b232bb71db326fab28605ac6c53
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "3661432"
---
# <a name="shipping-address-module"></a><span data-ttu-id="5ed03-103">módulo de endereço de remessa</span><span class="sxs-lookup"><span data-stu-id="5ed03-103">Shipping address module</span></span>

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

<span data-ttu-id="5ed03-104">Este tópico descreve o módulo de endereço de remessa e explica como configurá-lo no Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="5ed03-104">This topic describes covers the shipping address module and explains how to configure it in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="5ed03-105">Visão Geral</span><span class="sxs-lookup"><span data-stu-id="5ed03-105">Overview</span></span>

<span data-ttu-id="5ed03-106">O módulo de endereço de remessa permite que os clientes adicionem ou selecionem o endereço de remessa para uma ordem durante o o fluxo de finalização de compra.</span><span class="sxs-lookup"><span data-stu-id="5ed03-106">The shipping address module lets customers add or select the shipping address for an order during the checkout flow.</span></span> <span data-ttu-id="5ed03-107">Se o cliente estiver conectado, quaisquer endereços que foram salvos anteriormente para esse cliente serão exibidos e o cliente poderá selecionar entre eles.</span><span class="sxs-lookup"><span data-stu-id="5ed03-107">If a customer is signed in, any addresses that were previously saved for that customer are shown, and the customer can select among them.</span></span> <span data-ttu-id="5ed03-108">O cliente também pode adicionar um novo endereço.</span><span class="sxs-lookup"><span data-stu-id="5ed03-108">The customer can also add a new address.</span></span> <span data-ttu-id="5ed03-109">O módulo de endereço de remessa é usado para todos os itens em uma ordem que exija remessa.</span><span class="sxs-lookup"><span data-stu-id="5ed03-109">The shipping address module is used for all items on an order that require shipping.</span></span>

<span data-ttu-id="5ed03-110">Os formatos de endereço de remessa podem ser definidos na sede do Commerce para cada país ou região, e o módulo de endereço de remessa reforça as regras específicas do país/região.</span><span class="sxs-lookup"><span data-stu-id="5ed03-110">Shipping address formats can be defined in Commerce headquarters for each country or region, and the shipping address module then enforces country/region-specific rules.</span></span>

<span data-ttu-id="5ed03-111">Quando os clientes inserem um endereço de remessa durante o fluxo de finalização de compra, eles têm a opção de salvar o endereço como o endereço principal.</span><span class="sxs-lookup"><span data-stu-id="5ed03-111">When customers enter a shipping address during the checkout flow, they have the option to save the address as a primary address.</span></span> <span data-ttu-id="5ed03-112">Esta opção é exibida somente se o cliente estiver conectado.</span><span class="sxs-lookup"><span data-stu-id="5ed03-112">This option is shown only if a customer is signed in.</span></span>

<span data-ttu-id="5ed03-113">Embora o módulo de endereço de remessa não forneça validação de endereço, essa funcionalidade pode ser implementada por meio da personalização.</span><span class="sxs-lookup"><span data-stu-id="5ed03-113">Although the shipping address module doesn't provide address validation, this functionality can be implemented through customization.</span></span>

<span data-ttu-id="5ed03-114">A ilustração a seguir mostra um exemplo de um novo módulo de endereço de remessa em uma página de finalização de compra.</span><span class="sxs-lookup"><span data-stu-id="5ed03-114">The following illustration shows an example of a new shipping address module on a checkout page.</span></span>

![Exemplo de um módulo de endereço de remessa em uma página de finalização de compra](./media/ecommerce-shippingaddress.PNG)

## <a name="module-properties"></a><span data-ttu-id="5ed03-116">Propriedades do módulo</span><span class="sxs-lookup"><span data-stu-id="5ed03-116">Module properties</span></span>

| <span data-ttu-id="5ed03-117">Nome da propriedade</span><span class="sxs-lookup"><span data-stu-id="5ed03-117">Property name</span></span> | <span data-ttu-id="5ed03-118">Valores</span><span class="sxs-lookup"><span data-stu-id="5ed03-118">Values</span></span> | <span data-ttu-id="5ed03-119">descrição</span><span class="sxs-lookup"><span data-stu-id="5ed03-119">Description</span></span> |
|---------------|--------|-------------|
| <span data-ttu-id="5ed03-120">Cabeçalho</span><span class="sxs-lookup"><span data-stu-id="5ed03-120">Heading</span></span> | <span data-ttu-id="5ed03-121">Texto do cabeçalho e uma tag do cabeçalho (**H1**, **H2**, **H3**, **H4**, **H5** ou **H6**)</span><span class="sxs-lookup"><span data-stu-id="5ed03-121">Heading text and a heading tag (**H1**, **H2**, **H3**, **H4**, **H5**, or **H6**)</span></span> | <span data-ttu-id="5ed03-122">Um título opcional para o módulo de endereço de remessa.</span><span class="sxs-lookup"><span data-stu-id="5ed03-122">An optional heading for the shipping address module.</span></span> |
| <span data-ttu-id="5ed03-123">Mostrar tipo de endereço</span><span class="sxs-lookup"><span data-stu-id="5ed03-123">Show address type</span></span> | <span data-ttu-id="5ed03-124">**Verdadeiro** ou **Falso**</span><span class="sxs-lookup"><span data-stu-id="5ed03-124">**True** or **False**</span></span> | <span data-ttu-id="5ed03-125">Se essa propriedade opcional for definida como **Verdadeira**, um tipo de endereço, como **Residencial** ou **Comercial**, será exibido.</span><span class="sxs-lookup"><span data-stu-id="5ed03-125">If this optional property is set to **True**, an address type, such as **Home** or **Business**, will be shown.</span></span> <span data-ttu-id="5ed03-126">Se nenhum tipo de endereço for especificado, o endereço será salvo automaticamente como **Tipo**=**Outro**.</span><span class="sxs-lookup"><span data-stu-id="5ed03-126">If no address type is specified, the address will automatically be saved as **Type**=**Other**.</span></span> |

## <a name="add-a-shipping-address-module-to-a-checkout-page-and-set-the-required-properties"></a><span data-ttu-id="5ed03-127">Adicionar um módulo de endereço de remessa a uma página de finalização da compra e definir as propriedades necessárias</span><span class="sxs-lookup"><span data-stu-id="5ed03-127">Add a shipping address module to a checkout page and set the required properties</span></span>

<span data-ttu-id="5ed03-128">Um módulo de endereço de remessa pode ser adicionado somente a um módulo de finalização da compra.</span><span class="sxs-lookup"><span data-stu-id="5ed03-128">A shipping address module can be added only to a checkout module.</span></span> <span data-ttu-id="5ed03-129">Para obter mais informações sobre como configurar o módulo endereço de remessa e adicioná-lo a uma página de finalização da compra, consulte [Módulo de finalização da compra](add-checkout-module.md).</span><span class="sxs-lookup"><span data-stu-id="5ed03-129">For more information about how to configure the shipping address module and add it to a checkout page, see [Checkout module](add-checkout-module.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="5ed03-130">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="5ed03-130">Additional resources</span></span>

[<span data-ttu-id="5ed03-131">Módulo de carrinho</span><span class="sxs-lookup"><span data-stu-id="5ed03-131">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="5ed03-132">Módulo de ícone de carrinho</span><span class="sxs-lookup"><span data-stu-id="5ed03-132">Cart icon module</span></span>](cart-icon-module.md)

[<span data-ttu-id="5ed03-133">Módulo de finalização da compra</span><span class="sxs-lookup"><span data-stu-id="5ed03-133">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="5ed03-134">Módulo de pagamento</span><span class="sxs-lookup"><span data-stu-id="5ed03-134">Payment module</span></span>](payment-module.md)

[<span data-ttu-id="5ed03-135">Módulo de opções de entrega</span><span class="sxs-lookup"><span data-stu-id="5ed03-135">Delivery options module</span></span>](delivery-options-module.md)

[<span data-ttu-id="5ed03-136">Módulo de detalhes da ordem</span><span class="sxs-lookup"><span data-stu-id="5ed03-136">Order details module</span></span>](order-confirmation-module.md)

[<span data-ttu-id="5ed03-137">Módulo de vale-presente</span><span class="sxs-lookup"><span data-stu-id="5ed03-137">Gift card module</span></span>](add-giftcard.md)