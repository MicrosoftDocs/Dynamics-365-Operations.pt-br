---
title: Módulo de opções de entrega
description: Este tópico abrange os módulos de opções de entrega e explica como configurá-los no Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 04/23/2021
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
ms.openlocfilehash: 8342afefa6eeda3a53decb39caddb62d1e4e1963
ms.sourcegitcommit: dc4898aa32f381620c517bf89c7856e693563ace
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/17/2021
ms.locfileid: "6270852"
---
# <a name="delivery-options-module"></a><span data-ttu-id="dae7b-103">Módulo de opções de entrega</span><span class="sxs-lookup"><span data-stu-id="dae7b-103">Delivery options module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="dae7b-104">Este tópico abrange os módulos de opções de entrega e explica como configurá-los no Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="dae7b-104">This topic covers delivery options modules and explains how to configure them in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="dae7b-105">Os módulos de opções de entrega permitem que os clientes selecionem um modo de entrega, como remessa ou retirada do pedido online.</span><span class="sxs-lookup"><span data-stu-id="dae7b-105">Delivery options modules let customers select a mode of delivery such as shipping or pickup for their online order.</span></span> <span data-ttu-id="dae7b-106">É necessário um endereço de remessa para determinar o modo de entrega.</span><span class="sxs-lookup"><span data-stu-id="dae7b-106">A shipping address is required to determine the mode of delivery.</span></span> <span data-ttu-id="dae7b-107">Se o endereço de remessa for alterado, as opções de entrega deverão ser recuperadas novamente.</span><span class="sxs-lookup"><span data-stu-id="dae7b-107">If the shipping address changes, the delivery options must be retrieved again.</span></span> <span data-ttu-id="dae7b-108">Se uma ordem incluir somente itens que serão retirados em uma loja, esse módulo ficará oculto automaticamente.</span><span class="sxs-lookup"><span data-stu-id="dae7b-108">If an order includes only items that will be picked up in a store, this module is automatically hidden.</span></span>

<span data-ttu-id="dae7b-109">Para obter mais informações sobre como configurar os modos de entrega, consulte [Configuração de canal online](channel-setup-online.md) e [Configurar os modos de entrega](/dynamicsax-2012/appuser-itpro/set-up-modes-of-delivery).</span><span class="sxs-lookup"><span data-stu-id="dae7b-109">For information about how to configure modes of delivery, see [Online channel setup](channel-setup-online.md) and [Set up modes of delivery](/dynamicsax-2012/appuser-itpro/set-up-modes-of-delivery).</span></span>

<span data-ttu-id="dae7b-110">Cada modo de entrega pode ter um encargo associado.</span><span class="sxs-lookup"><span data-stu-id="dae7b-110">Each delivery mode can have an associated charge.</span></span> <span data-ttu-id="dae7b-111">Para obter mais informações sobre como configurar encargos de uma loja online, consulte [Encargos automáticos avançados do Omnicanal](omni-auto-charges.md).</span><span class="sxs-lookup"><span data-stu-id="dae7b-111">For more information about how to configure charges for an online store, see [Omni-channel Advanced auto-charges](omni-auto-charges.md).</span></span>

<span data-ttu-id="dae7b-112">No Commerce versão 10.0.13, o módulo de opções de entrega foi atualizado para oferecer suporte aos recursos **Encargos de cabeçalho sem rateio** e **Remessa como encargo de linha**.</span><span class="sxs-lookup"><span data-stu-id="dae7b-112">In Commerce version 10.0.13, the delivery options module has been updated to support the **Header charges without proration** and **Shipping as a line charge** features.</span></span> <span data-ttu-id="dae7b-113">Se o rateio for desativado, a expectativa é que o fluxo de trabalho do comércio eletrônico não permita um modo misto de entrega para os itens no carrinho (ou seja, alguns itens são selecionados para remessa, mas outros são selecionados para retirada).</span><span class="sxs-lookup"><span data-stu-id="dae7b-113">If proration is turned off, the expectation is that the e-Commerce workflow won't allow a mixed mode of delivery for the items in the cart (that is, some items are selected for shipment, but others are selected for pickup).</span></span> <span data-ttu-id="dae7b-114">O recurso **Encargos de cabeçalho sem rateio** requer que o sinalizador **Habilitar manuseio de modo de entrega consistente no canal** seja ativado no Commerce Headquarters.</span><span class="sxs-lookup"><span data-stu-id="dae7b-114">The **Header charges without proration** feature requires that the **Enable consistent delivery mode handling in channel** flag is turned on in Commerce headquarters.</span></span> <span data-ttu-id="dae7b-115">Quando o sinalizador do recurso for ativado, as cobranças de remessa serão aplicadas no nível do cabeçalho ou no nível da linha, dependendo da configuração no Commerce Headquarters.</span><span class="sxs-lookup"><span data-stu-id="dae7b-115">When the feature flag is turned on, shipping charges will be applied at either the header level or the line level, depending on the configuration in Commerce headquarters.</span></span>

<span data-ttu-id="dae7b-116">O tema Fabrikam oferece suporte a um modo misto de entrega em que alguns itens são selecionados para remessa, mas outros são selecionados para retirada.</span><span class="sxs-lookup"><span data-stu-id="dae7b-116">The Fabrikam theme supports a mixed mode of delivery, where some items are selected for shipment but others are selected for pickup.</span></span> <span data-ttu-id="dae7b-117">Nesse modo, os encargos de remessa serão rateados para todos os itens selecionados no modo de remessa da entrega.</span><span class="sxs-lookup"><span data-stu-id="dae7b-117">In this mode, shipping charges will be prorated for all items that are selected for the shipping mode of delivery.</span></span> <span data-ttu-id="dae7b-118">Para que um modo misto de entrega funcione, é necessário configurar o recurso **Encargos de cabeçalho com rateio** no Commerce Headquarters.</span><span class="sxs-lookup"><span data-stu-id="dae7b-118">For a mixed mode of delivery to work, you must first configure the **Header charges with proration** feature in Commerce headquarters.</span></span> <span data-ttu-id="dae7b-119">Para obter mais informações sobre essa configuração, consulte [Ratear encargos de cabeçalho para coincidir com linhas de vendas](pro-rate-charges-matching-lines.md).</span><span class="sxs-lookup"><span data-stu-id="dae7b-119">For more information about this configuration, see [Prorate header charges to match sales lines](pro-rate-charges-matching-lines.md).</span></span>

<span data-ttu-id="dae7b-120">Se os encargos de remessa forem aplicáveis aos itens de linha, eles poderão ser exibidos para cada item na linha do carrinho.</span><span class="sxs-lookup"><span data-stu-id="dae7b-120">If shipping charges apply to line items, they can be shown on the cart line for each item.</span></span> <span data-ttu-id="dae7b-121">Esta funcionalidade requer que a propriedade **Mostrar encargos de remessa no item da linha** seja ativada para o módulo do carrinho e o módulo de finalização da compra.</span><span class="sxs-lookup"><span data-stu-id="dae7b-121">This functionality requires that the **Show shipping charges on line item** property be turned on for both the cart module and the checkout module.</span></span> <span data-ttu-id="dae7b-122">Para obter mais informações, consulte [Módulo de carrinho](add-cart-module.md) e [Módulo de finalização da compra](add-checkout-module.md).</span><span class="sxs-lookup"><span data-stu-id="dae7b-122">For more information, see [Cart module](add-cart-module.md) and [Checkout module](add-checkout-module.md).</span></span>

<span data-ttu-id="dae7b-123">A ilustração a seguir mostra um exemplo de um módulo de opções de entrega em uma página de finalização da compra.</span><span class="sxs-lookup"><span data-stu-id="dae7b-123">The following illustration shows an example of a delivery options module on a checkout page.</span></span>

![Exemplo de um módulo de opções de entrega em uma página de finalização de compra](./media/ecommerce-deliveryoptions.PNG)

## <a name="delivery-options-module-properties"></a><span data-ttu-id="dae7b-125">Propriedades do módulo de opções de entrega</span><span class="sxs-lookup"><span data-stu-id="dae7b-125">Delivery options module properties</span></span>

| <span data-ttu-id="dae7b-126">Propriedade</span><span class="sxs-lookup"><span data-stu-id="dae7b-126">Property</span></span> | <span data-ttu-id="dae7b-127">Valores</span><span class="sxs-lookup"><span data-stu-id="dae7b-127">Values</span></span> | <span data-ttu-id="dae7b-128">descrição</span><span class="sxs-lookup"><span data-stu-id="dae7b-128">Description</span></span> |
|----------|--------|-------------|
| <span data-ttu-id="dae7b-129">Cabeçalho</span><span class="sxs-lookup"><span data-stu-id="dae7b-129">Heading</span></span> | <span data-ttu-id="dae7b-130">Texto do cabeçalho e uma tag do cabeçalho (**H1**, **H2**, **H3**, **H4**, **H5** ou **H6**)</span><span class="sxs-lookup"><span data-stu-id="dae7b-130">Heading text and a heading tag (**H1**, **H2**, **H3**, **H4**, **H5**, or **H6**)</span></span> | <span data-ttu-id="dae7b-131">Um título opcional para o módulo de opções de entrega.</span><span class="sxs-lookup"><span data-stu-id="dae7b-131">An optional heading for the delivery options module.</span></span> |
| <span data-ttu-id="dae7b-132">Nome da classe CSS personalizada</span><span class="sxs-lookup"><span data-stu-id="dae7b-132">Custom CSS class name</span></span> | <span data-ttu-id="dae7b-133">Texto</span><span class="sxs-lookup"><span data-stu-id="dae7b-133">Text</span></span> | <span data-ttu-id="dae7b-134">Um nome de classe de Folhas de Estilo em Cascata (CSS) que será usado para renderizar esse módulo, se aplicável.</span><span class="sxs-lookup"><span data-stu-id="dae7b-134">A custom Cascading Style Sheets (CSS) class name that will be used to render this module, if applicable.</span></span> |
| <span data-ttu-id="dae7b-135">Opção de Modo de Entrega do Filtro</span><span class="sxs-lookup"><span data-stu-id="dae7b-135">Filter Delivery Mode Option</span></span> | <span data-ttu-id="dae7b-136">**Não filtrar** ou **Modos não remessa**</span><span class="sxs-lookup"><span data-stu-id="dae7b-136">**Do not filter** or **Non-shipping modes**</span></span> | <span data-ttu-id="dae7b-137">Um valor que especifica se o módulo de opções de entrega devem filtrar todos os modos de entrega não remessa.</span><span class="sxs-lookup"><span data-stu-id="dae7b-137">A value that specifies whether the delivery options module should filter out all non-shipping delivery modes.</span></span> |
| <span data-ttu-id="dae7b-138">Seleção automática de uma opção de entrega</span><span class="sxs-lookup"><span data-stu-id="dae7b-138">Auto select a delivery option</span></span> | <span data-ttu-id="dae7b-139">**Não filtrar**, **Seleção automática de uma opção de entrega e mostrar resumo** ou **Seleção automática de uma opção de entrega e não mostrar resumo**</span><span class="sxs-lookup"><span data-stu-id="dae7b-139">**Do not filter**, **Auto select delivery option and show summary**, or **Auto select delivery option and don't show summary**</span></span> | <span data-ttu-id="dae7b-140">Esta propriedade aplica automaticamente a primeira opção de entrega disponível para finalizar a compra, sem exigir que o usuário a selecione.</span><span class="sxs-lookup"><span data-stu-id="dae7b-140">This property automatically applies the first available delivery option to checkout without requiring the user to select it.</span></span> <span data-ttu-id="dae7b-141">Deve ser usada somente se houver uma opção de entrega disponível.</span><span class="sxs-lookup"><span data-stu-id="dae7b-141">It should be used only if there is one available delivery option.</span></span> <span data-ttu-id="dae7b-142">Essa propriedade é suportada a partir da versão 10.0.19 do Commerce.</span><span class="sxs-lookup"><span data-stu-id="dae7b-142">This property is supported as of the Commerce version 10.0.19 release.</span></span> |

## <a name="add-a-delivery-options-module-to-a-checkout-page-and-set-the-required-properties"></a><span data-ttu-id="dae7b-143">Adicionar um módulo de opções de entrega a uma página de finalização da compra e definir as propriedades necessárias</span><span class="sxs-lookup"><span data-stu-id="dae7b-143">Add a delivery options module to a checkout page and set the required properties</span></span>

<span data-ttu-id="dae7b-144">Um módulo de opções de entrega pode ser adicionado somente a um módulo de finalização da compra.</span><span class="sxs-lookup"><span data-stu-id="dae7b-144">A delivery options module can be added only to a checkout module.</span></span> <span data-ttu-id="dae7b-145">Para obter mais informações sobre como configurar o módulo de opções de entrega e adicioná-lo a uma página de finalização da compra, consulte [Módulo de finalização da compra](add-checkout-module.md).</span><span class="sxs-lookup"><span data-stu-id="dae7b-145">For more information about how to configure the delivery options module and add it to a checkout page, see [Checkout module](add-checkout-module.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="dae7b-146">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="dae7b-146">Additional resources</span></span>

[<span data-ttu-id="dae7b-147">Módulo de carrinho</span><span class="sxs-lookup"><span data-stu-id="dae7b-147">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="dae7b-148">Módulo de finalização da compra</span><span class="sxs-lookup"><span data-stu-id="dae7b-148">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="dae7b-149">Módulo de pagamento</span><span class="sxs-lookup"><span data-stu-id="dae7b-149">Payment module</span></span>](payment-module.md)

[<span data-ttu-id="dae7b-150">Módulo de endereço de remessa</span><span class="sxs-lookup"><span data-stu-id="dae7b-150">Shipping address module</span></span>](ship-address-module.md)

[<span data-ttu-id="dae7b-151">Módulo de informações sobre retirada</span><span class="sxs-lookup"><span data-stu-id="dae7b-151">Pickup information module</span></span>](pickup-info-module.md)

[<span data-ttu-id="dae7b-152">Módulo de detalhes da ordem</span><span class="sxs-lookup"><span data-stu-id="dae7b-152">Order details module</span></span>](order-confirmation-module.md)

[<span data-ttu-id="dae7b-153">Módulo de cartão-presente</span><span class="sxs-lookup"><span data-stu-id="dae7b-153">Gift card module</span></span>](add-giftcard.md)

[<span data-ttu-id="dae7b-154">Configuração de canal online</span><span class="sxs-lookup"><span data-stu-id="dae7b-154">Online channel setup</span></span>](channel-setup-online.md)

[<span data-ttu-id="dae7b-155">Encargos automáticos Avançados de Omnicanal</span><span class="sxs-lookup"><span data-stu-id="dae7b-155">Omni-channel Advanced auto-charges</span></span>](omni-auto-charges.md)

[<span data-ttu-id="dae7b-156">Ratear encargos do cabeçalho para coincidir com linhas de vendas</span><span class="sxs-lookup"><span data-stu-id="dae7b-156">Prorate header charges to match sales lines</span></span>](pro-rate-charges-matching-lines.md)

[<span data-ttu-id="dae7b-157">Configurar os modos de entrega</span><span class="sxs-lookup"><span data-stu-id="dae7b-157">Set up modes of delivery</span></span>](/dynamicsax-2012/appuser-itpro/set-up-modes-of-delivery)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
