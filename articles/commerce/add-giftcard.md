---
title: Módulo do vale-presente
description: Este tópico abrange os módulos de cartão-presente e descreve como adicioná-los a páginas de site no Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 09/15/2020
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
ms.openlocfilehash: fc47d590789c79c08af7555222aa7cc9409da23c
ms.sourcegitcommit: 8028fbc5b9585e87d3331ea02577ff82ede090af
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/16/2020
ms.locfileid: "3817417"
---
# <a name="gift-card-module"></a><span data-ttu-id="3f0f8-103">Módulo do vale-presente</span><span class="sxs-lookup"><span data-stu-id="3f0f8-103">Gift card module</span></span>

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

<span data-ttu-id="3f0f8-104">Este tópico abrange os módulos de cartão-presente e descreve como adicioná-los a páginas de site no Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="3f0f8-104">This topic covers gift card modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="3f0f8-105">Visão Geral</span><span class="sxs-lookup"><span data-stu-id="3f0f8-105">Overview</span></span>

<span data-ttu-id="3f0f8-106">Os módulos de cartão-presente podem ser usados em módulos de finalização de compra para aceitar cartões-presente, uma forma comum de pagamento usada para transações de comércio eletrônico.</span><span class="sxs-lookup"><span data-stu-id="3f0f8-106">Gift card modules can be used in checkout modules to accept gift cards, a common form of payment used for e-Commerce transactions.</span></span> <span data-ttu-id="3f0f8-107">O módulo de cartão-presente oferece suporte a cartões-presente Dynamics 365, SVS e Givex.</span><span class="sxs-lookup"><span data-stu-id="3f0f8-107">The gift card module supports Dynamics 365, SVS, and Givex gift cards.</span></span> <span data-ttu-id="3f0f8-108">Os cartões-presente SVS e Givex são resgatados por meio do provedor de pagamentos Adyen.</span><span class="sxs-lookup"><span data-stu-id="3f0f8-108">SVS and Givex gift cards are redeemed via the Adyen payment provider.</span></span> <span data-ttu-id="3f0f8-109">Para obter mais informações sobre suporte a cartões-presente externos, como SVS e Givex, consulte [Suporte a cartões-presente externos](./dev-itpro/gift-card.md).</span><span class="sxs-lookup"><span data-stu-id="3f0f8-109">For more information about support for external gift cards such as SVS and Givex, see [Support for external gift cards](./dev-itpro/gift-card.md).</span></span>

> [!NOTE]
> <span data-ttu-id="3f0f8-110">O suporte para o resgate de vales-presentes SVS e Givex durante o fluxo de finalização de compra está disponível na versão 10.0.11 do Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="3f0f8-110">Support for redeeming SVS and Givex gift cards during checkout flow is available in the Dynamics 365 Commerce 10.0.11 release.</span></span> 

<span data-ttu-id="3f0f8-111">Há dois módulos de cartão-presente disponíveis:</span><span class="sxs-lookup"><span data-stu-id="3f0f8-111">There are two gift card modules available:</span></span>

- <span data-ttu-id="3f0f8-112">**Cartão-presente** - Este módulo pode ser usado em uma página de finalização de compra para resgatar um cartão-presente como meio de pagamento.</span><span class="sxs-lookup"><span data-stu-id="3f0f8-112">**Gift card** - This module can be used on a checkout page to redeem a gift card as tender.</span></span> 
- <span data-ttu-id="3f0f8-113">**Verificação de saldo do cartão-presente** - Este módulo pode ser usado em qualquer página para verificar o saldo de um cartão-presente.</span><span class="sxs-lookup"><span data-stu-id="3f0f8-113">**Gift card balance check** - This module can be used on any page to check the balance on a gift card.</span></span> <span data-ttu-id="3f0f8-114">Este módulo está disponível nas versões 10.0.14 e posterior do Commerce.</span><span class="sxs-lookup"><span data-stu-id="3f0f8-114">This module is available in Commerce release 10.0.14 and later.</span></span>

> [!NOTE]
> <span data-ttu-id="3f0f8-115">O suporte para o módulo de verificação de saldo de vale-presente está disponível na versão do 10.0.14 do Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="3f0f8-115">Support for the gift card balance check module is available in the Dynamics 365 Commerce 10.0.14 release.</span></span>

<span data-ttu-id="3f0f8-116">A imagem a seguir mostra um exemplo de um módulo de cartão-presente em uma página de finalização de compra.</span><span class="sxs-lookup"><span data-stu-id="3f0f8-116">The following image shows an example of a gift card module on a checkout page.</span></span>

![Exemplo de um módulo de cartão-presente](./media/ecommerce-giftcard.PNG)

## <a name="module-properties"></a><span data-ttu-id="3f0f8-118">Propriedades do módulo</span><span class="sxs-lookup"><span data-stu-id="3f0f8-118">Module properties</span></span>

- <span data-ttu-id="3f0f8-119">**Mostrar campos adicionais**- Essa propriedade define quais campos devem ser exibidos para cartões-presente além do número do cartão-presente, que é sempre exibido por padrão.</span><span class="sxs-lookup"><span data-stu-id="3f0f8-119">**Show additional fields** - This property defines what fields should be displayed for gift cards in addition to the gift card number, which is always displayed by default.</span></span> <span data-ttu-id="3f0f8-120">Por exemplo, alguns cartões-presente suportam a exibição de um PIN (número de identificação pessoal) e outros suportam a exibição de um PIN e uma data de validade.</span><span class="sxs-lookup"><span data-stu-id="3f0f8-120">For example, some gift cards support displaying a personal identification number (PIN), and others support displaying a PIN and expiration date.</span></span> <span data-ttu-id="3f0f8-121">Como alternativa, essa propriedade pode ser definida como "Nenhum", que exibiria somente o número do cartão-presente e nenhum outro campo.</span><span class="sxs-lookup"><span data-stu-id="3f0f8-121">Alternatively, this property could be set to "None", which would only display the gift card number and no additional fields.</span></span>

<span data-ttu-id="3f0f8-122">Valores com suporte:</span><span class="sxs-lookup"><span data-stu-id="3f0f8-122">Supported values:</span></span>
-   <span data-ttu-id="3f0f8-123">PIN</span><span class="sxs-lookup"><span data-stu-id="3f0f8-123">PIN</span></span>
-   <span data-ttu-id="3f0f8-124">Data de validade</span><span class="sxs-lookup"><span data-stu-id="3f0f8-124">Expiration date</span></span>
-   <span data-ttu-id="3f0f8-125">PIN e data de vencimento</span><span class="sxs-lookup"><span data-stu-id="3f0f8-125">PIN and expiration date</span></span> 
-   <span data-ttu-id="3f0f8-126">Nemhum(a)</span><span class="sxs-lookup"><span data-stu-id="3f0f8-126">None</span></span>

## <a name="site-settings-for-gift-card-modules"></a><span data-ttu-id="3f0f8-127">Configurações do site para módulos de cartão-presente</span><span class="sxs-lookup"><span data-stu-id="3f0f8-127">Site settings for gift card modules</span></span>

<span data-ttu-id="3f0f8-128">No construtor de sites do Commerce em **Configurações de site \> Extensões**, há uma configuração de módulo de cartão-presente chamada **Tipo de cartão-presente compatível**.</span><span class="sxs-lookup"><span data-stu-id="3f0f8-128">In Commerce site builder under **Site Settings \> Extensions**, there is a gift card module setting called **Supported gift card type**.</span></span> <span data-ttu-id="3f0f8-129">Esta configuração oferece suporte a três valores:</span><span class="sxs-lookup"><span data-stu-id="3f0f8-129">This setting supports three values:</span></span>
- <span data-ttu-id="3f0f8-130">**Cartão-presente do Dynamics 365** - Quando essa configuração é aplicada, o módulo do cartão-presente só permite o resgate dos cartões-presente do Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="3f0f8-130">**Dynamics 365 gift card** - When this setting is applied, the gift card module only allows the redemption of Dynamics 365 gift cards.</span></span> <span data-ttu-id="3f0f8-131">Essa configuração só tem suporte para usuários conectados no site de comércio eletrônico.</span><span class="sxs-lookup"><span data-stu-id="3f0f8-131">This setting is only supported for signed-in users on the e-Commerce site.</span></span>
- <span data-ttu-id="3f0f8-132">**Cartões-presente SVS e Givex** - Quando essa configuração é aplicada, o módulo do cartão-presente só permite o resgate dos cartões-presente Givex e SVS.</span><span class="sxs-lookup"><span data-stu-id="3f0f8-132">**SVS and Givex gift cards** - When this setting is applied, the gift card module only allows the redemption of Givex and SVS gift cards.</span></span> <span data-ttu-id="3f0f8-133">Essa configuração tem suporte para usuários conectados e anônimos no site de comércio eletrônico.</span><span class="sxs-lookup"><span data-stu-id="3f0f8-133">This setting is supported for signed-in and anonymous users on the e-Commerce site.</span></span>
- <span data-ttu-id="3f0f8-134">**Cartões-presente Dynamics 365, SVS e Givex** - Quando essa configuração é aplicada, o módulo do cartão-presente só permite o resgate dos cartões-presente Dynamics 365, Givex e SVS.</span><span class="sxs-lookup"><span data-stu-id="3f0f8-134">**Dynamics 365, SVS, and Givex gift cards** - When this setting is applied, the gift card module allows the redemption of Dynamics 365, Givex, and SVS gift cards.</span></span> <span data-ttu-id="3f0f8-135">Essa configuração só tem suporte para usuários conectados no site de comércio eletrônico.</span><span class="sxs-lookup"><span data-stu-id="3f0f8-135">This setting is only supported for signed-in users on the e-Commerce site.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3f0f8-136">Essas configurações estão disponíveis na versão 10.0.11 do Dynamics 365 Commerce e são necessárias somente se você precisar de suporte para vales-presente SVS ou Givex.</span><span class="sxs-lookup"><span data-stu-id="3f0f8-136">These settings are available in the Dynamics 365 Commerce 10.0.11 release and are required only if you need support for SVS or Givex gift cards.</span></span> <span data-ttu-id="3f0f8-137">Se estiver atualizando de uma versão mais antiga do Dynamics 365 Commerce, você deverá atualizar manualmente o arquivo appsettings.json.</span><span class="sxs-lookup"><span data-stu-id="3f0f8-137">If you are updating from an older version of Dynamics 365 Commerce, you must manually update the appsettings.json file.</span></span> <span data-ttu-id="3f0f8-138">Para obter instruções sobre como atualizar o arquivo appsettings.json, consulte [SDK e atualizações da biblioteca de módulos](e-commerce-extensibility/sdk-updates.md#update-the-appsettingsjson-file).</span><span class="sxs-lookup"><span data-stu-id="3f0f8-138">For instructions on updating the appsettings.json file, see [SDK and module library updates](e-commerce-extensibility/sdk-updates.md#update-the-appsettingsjson-file).</span></span> 

## <a name="add-a-gift-card-module-to-a-page"></a><span data-ttu-id="3f0f8-139">Adicionar um módulo de cartão-presente a uma página</span><span class="sxs-lookup"><span data-stu-id="3f0f8-139">Add a gift card module to a page</span></span>

<span data-ttu-id="3f0f8-140">Para obter instruções sobre como adicionar um módulo de cartão-presente a uma página de check-in e definir as propriedades necessárias, consulte [Módulo de finalização](add-checkout-module.md).</span><span class="sxs-lookup"><span data-stu-id="3f0f8-140">For instructions on how to add a gift card module to a checkout page and set the required properties, see [Checkout module](add-checkout-module.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="3f0f8-141">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="3f0f8-141">Additional resources</span></span>

[<span data-ttu-id="3f0f8-142">Módulo de carrinho</span><span class="sxs-lookup"><span data-stu-id="3f0f8-142">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="3f0f8-143">Módulo de ícone de carrinho</span><span class="sxs-lookup"><span data-stu-id="3f0f8-143">Cart icon module</span></span>](cart-icon-module.md)

[<span data-ttu-id="3f0f8-144">Módulo de finalização da compra</span><span class="sxs-lookup"><span data-stu-id="3f0f8-144">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="3f0f8-145">Módulo de pagamento</span><span class="sxs-lookup"><span data-stu-id="3f0f8-145">Payment module</span></span>](payment-module.md)

[<span data-ttu-id="3f0f8-146">Módulo do endereço de remessa</span><span class="sxs-lookup"><span data-stu-id="3f0f8-146">Shipping address module</span></span>](ship-address-module.md)

[<span data-ttu-id="3f0f8-147">Módulo de opções de entrega</span><span class="sxs-lookup"><span data-stu-id="3f0f8-147">Delivery options module</span></span>](delivery-options-module.md)

[<span data-ttu-id="3f0f8-148">Módulo de detalhes da ordem</span><span class="sxs-lookup"><span data-stu-id="3f0f8-148">Order details module</span></span>](order-confirmation-module.md)

[<span data-ttu-id="3f0f8-149">Suporte a cartões-presente externos</span><span class="sxs-lookup"><span data-stu-id="3f0f8-149">Support for external gift cards</span></span>](./dev-itpro/gift-card.md)

[<span data-ttu-id="3f0f8-150">SDK e atualizações da biblioteca de módulos</span><span class="sxs-lookup"><span data-stu-id="3f0f8-150">SDK and module library updates</span></span>](e-commerce-extensibility/sdk-updates.md)
