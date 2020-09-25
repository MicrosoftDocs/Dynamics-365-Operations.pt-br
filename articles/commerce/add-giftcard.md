---
title: Módulo do vale-presente
description: Este tópico abrange os módulos de cartão-presente e descreve como adicioná-los a páginas de site no Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 08/31/2020
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
ms.openlocfilehash: 4cc947b9d6f3cfa51bce2155170c49e9529d0f7d
ms.sourcegitcommit: 420b9e538f706178f8e1f2786e02f4f400bf2336
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/02/2020
ms.locfileid: "3761072"
---
# <a name="gift-card-module"></a><span data-ttu-id="d1248-103">Módulo do vale-presente</span><span class="sxs-lookup"><span data-stu-id="d1248-103">Gift card module</span></span>

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

<span data-ttu-id="d1248-104">Este tópico abrange os módulos de cartão-presente e descreve como adicioná-los a páginas de site no Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="d1248-104">This topic covers gift card modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="d1248-105">Visão Geral</span><span class="sxs-lookup"><span data-stu-id="d1248-105">Overview</span></span>

<span data-ttu-id="d1248-106">Os módulos de cartão-presente podem ser usados em módulos de finalização de compra para aceitar cartões-presente, uma forma comum de pagamento usada para transações de comércio eletrônico.</span><span class="sxs-lookup"><span data-stu-id="d1248-106">Gift card modules can be used in checkout modules to accept gift cards, a common form of payment used for e-Commerce transactions.</span></span> <span data-ttu-id="d1248-107">O módulo de cartão-presente oferece suporte a cartões-presente Dynamics 365, SVS e Givex.</span><span class="sxs-lookup"><span data-stu-id="d1248-107">The gift card module supports Dynamics 365, SVS, and Givex gift cards.</span></span> <span data-ttu-id="d1248-108">Os cartões-presente SVS e Givex são resgatados por meio do provedor de pagamentos Adyen.</span><span class="sxs-lookup"><span data-stu-id="d1248-108">SVS and Givex gift cards are redeemed via the Adyen payment provider.</span></span> <span data-ttu-id="d1248-109">Para obter mais informações sobre suporte a cartões-presente externos, como SVS e Givex, consulte [Suporte a cartões-presente externos](./dev-itpro/gift-card.md).</span><span class="sxs-lookup"><span data-stu-id="d1248-109">For more information about support for external gift cards such as SVS and Givex, see [Support for external gift cards](./dev-itpro/gift-card.md).</span></span>

<span data-ttu-id="d1248-110">Há dois módulos de cartão-presente disponíveis:</span><span class="sxs-lookup"><span data-stu-id="d1248-110">There are two gift card modules available:</span></span>

- <span data-ttu-id="d1248-111">**Cartão-presente** - Este módulo pode ser usado em uma página de finalização de compra para resgatar um cartão-presente como meio de pagamento.</span><span class="sxs-lookup"><span data-stu-id="d1248-111">**Gift card** - This module can be used on a checkout page to redeem a gift card as tender.</span></span> 
- <span data-ttu-id="d1248-112">**Verificação de saldo do cartão-presente** - Este módulo pode ser usado em qualquer página para verificar o saldo de um cartão-presente.</span><span class="sxs-lookup"><span data-stu-id="d1248-112">**Gift card balance check** - This module can be used on any page to check the balance on a gift card.</span></span> <span data-ttu-id="d1248-113">Este módulo está disponível nas versões 10.0.14 e posterior do Commerce.</span><span class="sxs-lookup"><span data-stu-id="d1248-113">This module is available in Commerce release 10.0.14 and later.</span></span>

<span data-ttu-id="d1248-114">A imagem a seguir mostra um exemplo de um módulo de cartão-presente em uma página de finalização de compra.</span><span class="sxs-lookup"><span data-stu-id="d1248-114">The following image shows an example of a gift card module on a checkout page.</span></span>

![Exemplo de um módulo de cartão-presente](./media/ecommerce-giftcard.PNG)

## <a name="module-properties"></a><span data-ttu-id="d1248-116">Propriedades do módulo</span><span class="sxs-lookup"><span data-stu-id="d1248-116">Module properties</span></span>

- <span data-ttu-id="d1248-117">**Mostrar campos adicionais**- Essa propriedade define quais campos devem ser exibidos para cartões-presente além do número do cartão-presente, que é sempre exibido por padrão.</span><span class="sxs-lookup"><span data-stu-id="d1248-117">**Show additional fields** - This property defines what fields should be displayed for gift cards in addition to the gift card number, which is always displayed by default.</span></span> <span data-ttu-id="d1248-118">Por exemplo, alguns cartões-presente suportam a exibição de um PIN (número de identificação pessoal) e outros suportam a exibição de um PIN e uma data de validade.</span><span class="sxs-lookup"><span data-stu-id="d1248-118">For example, some gift cards support displaying a personal identification number (PIN), and others support displaying a PIN and expiration date.</span></span> <span data-ttu-id="d1248-119">Como alternativa, essa propriedade pode ser definida como "Nenhum", que exibiria somente o número do cartão-presente e nenhum outro campo.</span><span class="sxs-lookup"><span data-stu-id="d1248-119">Alternatively, this property could be set to "None", which would only display the gift card number and no additional fields.</span></span>

<span data-ttu-id="d1248-120">Valores com suporte:</span><span class="sxs-lookup"><span data-stu-id="d1248-120">Supported values:</span></span>
-   <span data-ttu-id="d1248-121">PIN</span><span class="sxs-lookup"><span data-stu-id="d1248-121">PIN</span></span>
-   <span data-ttu-id="d1248-122">Data de validade</span><span class="sxs-lookup"><span data-stu-id="d1248-122">Expiration date</span></span>
-   <span data-ttu-id="d1248-123">PIN e data de vencimento</span><span class="sxs-lookup"><span data-stu-id="d1248-123">PIN and expiration date</span></span> 
-   <span data-ttu-id="d1248-124">Nemhum(a)</span><span class="sxs-lookup"><span data-stu-id="d1248-124">None</span></span>

## <a name="site-settings-for-gift-card-modules"></a><span data-ttu-id="d1248-125">Configurações do site para módulos de cartão-presente</span><span class="sxs-lookup"><span data-stu-id="d1248-125">Site settings for gift card modules</span></span>

<span data-ttu-id="d1248-126">No construtor de sites do Commerce em **Configurações de site \> Extensões**, há uma configuração de módulo de cartão-presente chamada **Tipo de cartão-presente compatível**.</span><span class="sxs-lookup"><span data-stu-id="d1248-126">In Commerce site builder under **Site Settings \> Extensions**, there is a gift card module setting called **Supported gift card type**.</span></span> <span data-ttu-id="d1248-127">Esta configuração oferece suporte a três valores:</span><span class="sxs-lookup"><span data-stu-id="d1248-127">This setting supports three values:</span></span>
- <span data-ttu-id="d1248-128">**Cartão-presente do Dynamics 365** - Quando essa configuração é aplicada, o módulo do cartão-presente só permite o resgate dos cartões-presente do Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="d1248-128">**Dynamics 365 gift card** - When this setting is applied, the gift card module only allows the redemption of Dynamics 365 gift cards.</span></span> <span data-ttu-id="d1248-129">Essa configuração só tem suporte para usuários conectados no site de comércio eletrônico.</span><span class="sxs-lookup"><span data-stu-id="d1248-129">This setting is only supported for signed-in users on the e-Commerce site.</span></span>
- <span data-ttu-id="d1248-130">**Cartões-presente SVS e Givex** - Quando essa configuração é aplicada, o módulo do cartão-presente só permite o resgate dos cartões-presente Givex e SVS.</span><span class="sxs-lookup"><span data-stu-id="d1248-130">**SVS and Givex gift cards** - When this setting is applied, the gift card module only allows the redemption of Givex and SVS gift cards.</span></span> <span data-ttu-id="d1248-131">Essa configuração tem suporte para usuários conectados e anônimos no site de comércio eletrônico.</span><span class="sxs-lookup"><span data-stu-id="d1248-131">This setting is supported for signed-in and anonymous users on the e-Commerce site.</span></span>
- <span data-ttu-id="d1248-132">**Cartões-presente Dynamics 365, SVS e Givex** - Quando essa configuração é aplicada, o módulo do cartão-presente só permite o resgate dos cartões-presente Dynamics 365, Givex e SVS.</span><span class="sxs-lookup"><span data-stu-id="d1248-132">**Dynamics 365, SVS, and Givex gift cards** - When this setting is applied, the gift card module allows the redemption of Dynamics 365, Givex, and SVS gift cards.</span></span> <span data-ttu-id="d1248-133">Essa configuração só tem suporte para usuários conectados no site de comércio eletrônico.</span><span class="sxs-lookup"><span data-stu-id="d1248-133">This setting is only supported for signed-in users on the e-Commerce site.</span></span>

## <a name="add-a-gift-card-module-to-a-page"></a><span data-ttu-id="d1248-134">Adicionar um módulo de cartão-presente a uma página</span><span class="sxs-lookup"><span data-stu-id="d1248-134">Add a gift card module to a page</span></span>

<span data-ttu-id="d1248-135">Para obter instruções sobre como adicionar um módulo de cartão-presente a uma página de check-in e definir as propriedades necessárias, consulte [Módulo de finalização](add-checkout-module.md).</span><span class="sxs-lookup"><span data-stu-id="d1248-135">For instructions on how to add a gift card module to a checkout page and set the required properties, see [Checkout module](add-checkout-module.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="d1248-136">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="d1248-136">Additional resources</span></span>

[<span data-ttu-id="d1248-137">Módulo de carrinho</span><span class="sxs-lookup"><span data-stu-id="d1248-137">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="d1248-138">Módulo de ícone de carrinho</span><span class="sxs-lookup"><span data-stu-id="d1248-138">Cart icon module</span></span>](cart-icon-module.md)

[<span data-ttu-id="d1248-139">Módulo de finalização da compra</span><span class="sxs-lookup"><span data-stu-id="d1248-139">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="d1248-140">Módulo de pagamento</span><span class="sxs-lookup"><span data-stu-id="d1248-140">Payment module</span></span>](payment-module.md)

[<span data-ttu-id="d1248-141">Módulo do endereço de remessa</span><span class="sxs-lookup"><span data-stu-id="d1248-141">Shipping address module</span></span>](ship-address-module.md)

[<span data-ttu-id="d1248-142">Módulo de opções de entrega</span><span class="sxs-lookup"><span data-stu-id="d1248-142">Delivery options module</span></span>](delivery-options-module.md)

[<span data-ttu-id="d1248-143">Módulo de detalhes da ordem</span><span class="sxs-lookup"><span data-stu-id="d1248-143">Order details module</span></span>](order-confirmation-module.md)

[<span data-ttu-id="d1248-144">Suporte a cartões-presente externos</span><span class="sxs-lookup"><span data-stu-id="d1248-144">Support for external gift cards</span></span>](./dev-itpro/gift-card.md)
