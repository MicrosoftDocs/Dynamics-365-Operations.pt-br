---
title: Módulo de opções de entrega
description: Este tópico abrange os módulos de opções de entrega e explica como configurá-los no Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 08/05/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.13
ms.openlocfilehash: f97dcd42e22e319d9af7cbf57fce7c10d8565d04
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5801974"
---
# <a name="delivery-options-module"></a><span data-ttu-id="23102-103">Módulo de opções de entrega</span><span class="sxs-lookup"><span data-stu-id="23102-103">Delivery options module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="23102-104">Este tópico abrange os módulos de opções de entrega e explica como configurá-los no Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="23102-104">This topic covers delivery options modules and explains how to configure them in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="23102-105">Os módulos de opções de entrega permitem que os clientes selecionem um modo de entrega, como remessa ou retirada do pedido online.</span><span class="sxs-lookup"><span data-stu-id="23102-105">Delivery options modules let customers select a mode of delivery such as shipping or pickup for their online order.</span></span> <span data-ttu-id="23102-106">É necessário um endereço de remessa para determinar o modo de entrega.</span><span class="sxs-lookup"><span data-stu-id="23102-106">A shipping address is required to determine the mode of delivery.</span></span> <span data-ttu-id="23102-107">Se o endereço de remessa for alterado, as opções de entrega deverão ser recuperadas novamente.</span><span class="sxs-lookup"><span data-stu-id="23102-107">If the shipping address changes, the delivery options must be retrieved again.</span></span> <span data-ttu-id="23102-108">Se uma ordem incluir somente itens que serão retirados em uma loja, esse módulo ficará oculto automaticamente.</span><span class="sxs-lookup"><span data-stu-id="23102-108">If an order includes only items that will be picked up in a store, this module is automatically hidden.</span></span>

<span data-ttu-id="23102-109">Para obter mais informações sobre como configurar os modos de entrega, consulte [Configuração de canal online](channel-setup-online.md) e [Configurar os modos de entrega](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/set-up-modes-of-delivery).</span><span class="sxs-lookup"><span data-stu-id="23102-109">For information about how to configure modes of delivery, see [Online channel setup](channel-setup-online.md) and [Set up modes of delivery](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/set-up-modes-of-delivery).</span></span>

<span data-ttu-id="23102-110">Cada modo de entrega pode ter um encargo associado.</span><span class="sxs-lookup"><span data-stu-id="23102-110">Each delivery mode can have an associated charge.</span></span> <span data-ttu-id="23102-111">Para obter mais informações sobre como configurar encargos de uma loja online, consulte [Encargos automáticos avançados do Omnicanal](omni-auto-charges.md).</span><span class="sxs-lookup"><span data-stu-id="23102-111">For more information about how to configure charges for an online store, see [Omni-channel Advanced auto-charges](omni-auto-charges.md).</span></span>

<span data-ttu-id="23102-112">No Commerce versão 10.0.13, o módulo de opções de entrega foi atualizado para oferecer suporte aos recursos **Encargos de cabeçalho sem rateio** e **Remessa como encargo de linha**.</span><span class="sxs-lookup"><span data-stu-id="23102-112">In Commerce version 10.0.13, the delivery options module has been updated to support the **Header charges without proration** and **Shipping as a line charge** features.</span></span> <span data-ttu-id="23102-113">Se o rateio for desativado, a expectativa é que o fluxo de trabalho do comércio eletrônico não permita um modo misto de entrega para os itens no carrinho (ou seja, alguns itens são selecionados para remessa, mas outros são selecionados para retirada).</span><span class="sxs-lookup"><span data-stu-id="23102-113">If proration is turned off, the expectation is that the e-Commerce workflow won't allow a mixed mode of delivery for the items in the cart (that is, some items are selected for shipment, but others are selected for pickup).</span></span> <span data-ttu-id="23102-114">O recurso **Encargos de cabeçalho sem rateio** requer que o sinalizador **Habilitar manuseio de modo de entrega consistente no canal** será ativado no Commerce Headquarters.</span><span class="sxs-lookup"><span data-stu-id="23102-114">The **Header charges without proration** feature requires that the **Enable consistent delivery mode handling in channel** flag be turned on in Commerce headquarters.</span></span> <span data-ttu-id="23102-115">Quando esse sinalizador for ativado, as cobranças de remessa serão aplicadas no nível do cabeçalho ou no nível da linha, dependendo da configuração no Commerce Headquarters.</span><span class="sxs-lookup"><span data-stu-id="23102-115">When that flag is turned on, shipping charges will be applied at either the header level or the line level, depending on the configuration in Commerce headquarters.</span></span>

<span data-ttu-id="23102-116">O tema Fabrikam oferece suporte a um modo misto de entrega em que alguns itens são selecionados para remessa, mas outros são selecionados para retirada.</span><span class="sxs-lookup"><span data-stu-id="23102-116">The Fabrikam theme supports a mixed mode of delivery, where some items are selected for shipment but others are selected for pickup.</span></span> <span data-ttu-id="23102-117">Nesse modo, os encargos de remessa serão rateados para todos os itens selecionados no modo de remessa da entrega.</span><span class="sxs-lookup"><span data-stu-id="23102-117">In this mode, shipping charges will be prorated for all items that are selected for the shipping mode of delivery.</span></span> <span data-ttu-id="23102-118">Para que um modo misto de entrega funcione, é necessário configurar o recurso **Encargos de cabeçalho com rateio** no Commerce Headquarters.</span><span class="sxs-lookup"><span data-stu-id="23102-118">For a mixed mode of delivery to work, you must first configure the **Header charges with proration** feature in Commerce headquarters.</span></span> <span data-ttu-id="23102-119">Para obter mais informações sobre essa configuração, consulte [Ratear encargos de cabeçalho para coincidir com linhas de vendas](pro-rate-charges-matching-lines.md).</span><span class="sxs-lookup"><span data-stu-id="23102-119">For more information about this configuration, see [Prorate header charges to match sales lines](pro-rate-charges-matching-lines.md).</span></span>

<span data-ttu-id="23102-120">Se os encargos de remessa forem aplicáveis aos itens de linha, eles poderão ser exibidos para cada item na linha do carrinho.</span><span class="sxs-lookup"><span data-stu-id="23102-120">If shipping charges apply to line items, they can be shown on the cart line for each item.</span></span> <span data-ttu-id="23102-121">Esta funcionalidade requer que a propriedade **Mostrar encargos de remessa no item da linha** seja ativada para o módulo do carrinho e o módulo de finalização da compra.</span><span class="sxs-lookup"><span data-stu-id="23102-121">This functionality requires that the **Show shipping charges on line item** property be turned on for both the cart module and the checkout module.</span></span> <span data-ttu-id="23102-122">Para obter mais informações, consulte [Módulo de carrinho](add-cart-module.md) e [Módulo de finalização da compra](add-checkout-module.md).</span><span class="sxs-lookup"><span data-stu-id="23102-122">For more information, see [Cart module](add-cart-module.md) and [Checkout module](add-checkout-module.md).</span></span>

<span data-ttu-id="23102-123">A ilustração a seguir mostra um exemplo de um módulo de opções de entrega em uma página de finalização da compra.</span><span class="sxs-lookup"><span data-stu-id="23102-123">The following illustration shows an example of a delivery options module on a checkout page.</span></span>

![Exemplo de um módulo de opções de entrega em uma página de finalização de compra](./media/ecommerce-deliveryoptions.PNG)

## <a name="delivery-options-module-properties"></a><span data-ttu-id="23102-125">Propriedades do módulo de opções de entrega</span><span class="sxs-lookup"><span data-stu-id="23102-125">Delivery options module properties</span></span>

| <span data-ttu-id="23102-126">Propriedade</span><span class="sxs-lookup"><span data-stu-id="23102-126">Property</span></span> | <span data-ttu-id="23102-127">Valores</span><span class="sxs-lookup"><span data-stu-id="23102-127">Values</span></span> | <span data-ttu-id="23102-128">descrição</span><span class="sxs-lookup"><span data-stu-id="23102-128">Description</span></span> |
|----------|--------|-------------|
| <span data-ttu-id="23102-129">Cabeçalho</span><span class="sxs-lookup"><span data-stu-id="23102-129">Heading</span></span> | <span data-ttu-id="23102-130">Texto do cabeçalho e uma tag do cabeçalho (**H1**, **H2**, **H3**, **H4**, **H5** ou **H6**)</span><span class="sxs-lookup"><span data-stu-id="23102-130">Heading text and a heading tag (**H1**, **H2**, **H3**, **H4**, **H5**, or **H6**)</span></span> | <span data-ttu-id="23102-131">Um título opcional para o módulo de opções de entrega.</span><span class="sxs-lookup"><span data-stu-id="23102-131">An optional heading for the delivery options module.</span></span> |
| <span data-ttu-id="23102-132">Nome da classe CSS personalizada</span><span class="sxs-lookup"><span data-stu-id="23102-132">Custom CSS class name</span></span> | <span data-ttu-id="23102-133">Texto</span><span class="sxs-lookup"><span data-stu-id="23102-133">Text</span></span> | <span data-ttu-id="23102-134">Um nome de classe de Folhas de Estilo em Cascata (CSS) que será usado para renderizar esse módulo, se aplicável.</span><span class="sxs-lookup"><span data-stu-id="23102-134">A custom Cascading Style Sheets (CSS) class name that will be used to render this module, if applicable.</span></span> |
| <span data-ttu-id="23102-135">Opção de Modo de Entrega do Filtro</span><span class="sxs-lookup"><span data-stu-id="23102-135">Filter Delivery Mode Option</span></span> | <span data-ttu-id="23102-136">**Não filtrar** ou **Modos não remessa**</span><span class="sxs-lookup"><span data-stu-id="23102-136">**Do not filter** or **Non-shipping modes**</span></span> | <span data-ttu-id="23102-137">Um valor que especifica se o módulo de opções de entrega devem filtrar todos os modos de entrega não remessa.</span><span class="sxs-lookup"><span data-stu-id="23102-137">A value that specifies whether the delivery options module should filter out all non-shipping delivery modes.</span></span> |

## <a name="add-a-delivery-options-module-to-a-checkout-page-and-set-the-required-properties"></a><span data-ttu-id="23102-138">Adicionar um módulo de opções de entrega a uma página de finalização da compra e definir as propriedades necessárias</span><span class="sxs-lookup"><span data-stu-id="23102-138">Add a delivery options module to a checkout page and set the required properties</span></span>

<span data-ttu-id="23102-139">Um módulo de opções de entrega pode ser adicionado somente a um módulo de finalização da compra.</span><span class="sxs-lookup"><span data-stu-id="23102-139">A delivery options module can be added only to a checkout module.</span></span> <span data-ttu-id="23102-140">Para obter mais informações sobre como configurar o módulo de opções de entrega e adicioná-lo a uma página de finalização da compra, consulte [Módulo de finalização da compra](add-checkout-module.md).</span><span class="sxs-lookup"><span data-stu-id="23102-140">For more information about how to configure the delivery options module and add it to a checkout page, see [Checkout module](add-checkout-module.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="23102-141">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="23102-141">Additional resources</span></span>

[<span data-ttu-id="23102-142">Módulo de carrinho</span><span class="sxs-lookup"><span data-stu-id="23102-142">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="23102-143">Módulo de finalização da compra</span><span class="sxs-lookup"><span data-stu-id="23102-143">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="23102-144">Módulo de pagamento</span><span class="sxs-lookup"><span data-stu-id="23102-144">Payment module</span></span>](payment-module.md)

[<span data-ttu-id="23102-145">Módulo de endereço de remessa</span><span class="sxs-lookup"><span data-stu-id="23102-145">Shipping address module</span></span>](ship-address-module.md)

[<span data-ttu-id="23102-146">Módulo de informações sobre retirada</span><span class="sxs-lookup"><span data-stu-id="23102-146">Pickup information module</span></span>](pickup-info-module.md)

[<span data-ttu-id="23102-147">Módulo de detalhes da ordem</span><span class="sxs-lookup"><span data-stu-id="23102-147">Order details module</span></span>](order-confirmation-module.md)

[<span data-ttu-id="23102-148">Módulo de cartão-presente</span><span class="sxs-lookup"><span data-stu-id="23102-148">Gift card module</span></span>](add-giftcard.md)

[<span data-ttu-id="23102-149">Configuração de canal online</span><span class="sxs-lookup"><span data-stu-id="23102-149">Online channel setup</span></span>](channel-setup-online.md)

[<span data-ttu-id="23102-150">Encargos automáticos Avançados de Omnicanal</span><span class="sxs-lookup"><span data-stu-id="23102-150">Omni-channel Advanced auto-charges</span></span>](omni-auto-charges.md)

[<span data-ttu-id="23102-151">Ratear encargos do cabeçalho para coincidir com linhas de vendas</span><span class="sxs-lookup"><span data-stu-id="23102-151">Prorate header charges to match sales lines</span></span>](pro-rate-charges-matching-lines.md)

[<span data-ttu-id="23102-152">Configurar os modos de entrega</span><span class="sxs-lookup"><span data-stu-id="23102-152">Set up modes of delivery</span></span>](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/set-up-modes-of-delivery)


[!INCLUDE[footer-include](../includes/footer-banner.md)]