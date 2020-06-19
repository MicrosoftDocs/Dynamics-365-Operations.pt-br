---
title: Módulo do vale-presente
description: Este tópico abrange os módulos de cartão-presente e descreve como adicioná-los a páginas de site no Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 05/28/2020
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
ms.openlocfilehash: a8428963e105e422dcd048863c17df0926a409ac
ms.sourcegitcommit: b52477b7d0d52102a7ca2fb95f4ebfa30ecd9f54
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/29/2020
ms.locfileid: "3411103"
---
# <a name="gift-card-module"></a><span data-ttu-id="005e3-103">Módulo do vale-presente</span><span class="sxs-lookup"><span data-stu-id="005e3-103">Gift card module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="005e3-104">Este tópico abrange os módulos de cartão-presente e descreve como adicioná-los a páginas de site no Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="005e3-104">This topic covers gift card modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="005e3-105">Visão Geral</span><span class="sxs-lookup"><span data-stu-id="005e3-105">Overview</span></span>

<span data-ttu-id="005e3-106">Os cartões-presente são uma forma comum de pagamento, e o módulo de cartão-presente pode ser usado em um módulo de check-out para aceitar cartões-presente.</span><span class="sxs-lookup"><span data-stu-id="005e3-106">Gift cards are a common form of payment, and the gift card module can be used in a checkout module to accept gift cards.</span></span> <span data-ttu-id="005e3-107">O módulo de cartão-presente oferece suporte a cartões-presente Dynamics 365, SVS e Givex.</span><span class="sxs-lookup"><span data-stu-id="005e3-107">The gift card module supports Dynamics 365, SVS, and Givex gift cards.</span></span> <span data-ttu-id="005e3-108">Os cartões-presente SVS e Givex são resgatados por meio do provedor de pagamentos Adyen.</span><span class="sxs-lookup"><span data-stu-id="005e3-108">SVS and Givex gift cards are redeemed via the Adyen payment provider.</span></span>

<span data-ttu-id="005e3-109">Para obter mais informações sobre suporte a cartões-presente externos, como SVS e Givex, consulte [Suporte a cartões-presente externos](./dev-itpro/gift-card.md)</span><span class="sxs-lookup"><span data-stu-id="005e3-109">For more information on support for external gift cards such as SVS and Givex, see [Support for external gift cards](./dev-itpro/gift-card.md)</span></span>

<span data-ttu-id="005e3-110">A imagem a seguir mostra um exemplo de um módulo de cartão-presente em uma página de finalização de compra.</span><span class="sxs-lookup"><span data-stu-id="005e3-110">The following image shows an example of a gift card module on a checkout page.</span></span>

![Exemplo de um módulo de cartão-presente](./media/ecommerce-giftcard.PNG)

## <a name="module-properties"></a><span data-ttu-id="005e3-112">Propriedades do módulo</span><span class="sxs-lookup"><span data-stu-id="005e3-112">Module properties</span></span>

- <span data-ttu-id="005e3-113">**Mostrar campos adicionais**- Essa propriedade define quais campos devem ser exibidos para cartões-presente além do número do cartão-presente, que é sempre exibido por padrão.</span><span class="sxs-lookup"><span data-stu-id="005e3-113">**Show additional fields** - This property defines what fields should be displayed for gift cards in addition to the gift card number, which is always displayed by default.</span></span> <span data-ttu-id="005e3-114">Por exemplo, alguns cartões-presente suportam a exibição de um PIN (número de identificação pessoal) e outros suportam a exibição de um PIN e uma data de validade.</span><span class="sxs-lookup"><span data-stu-id="005e3-114">For example, some gift cards support displaying a personal identification number (PIN), and others support displaying a PIN and expiration date.</span></span> <span data-ttu-id="005e3-115">Como alternativa, essa propriedade pode ser definida como "Nenhum", que exibiria somente o número do cartão-presente e nenhum outro campo.</span><span class="sxs-lookup"><span data-stu-id="005e3-115">Alternatively, this property could be set to "None", which would only display the gift card number and no additional fields.</span></span>

<span data-ttu-id="005e3-116">Valores com suporte:</span><span class="sxs-lookup"><span data-stu-id="005e3-116">Supported values:</span></span>
-   <span data-ttu-id="005e3-117">PIN</span><span class="sxs-lookup"><span data-stu-id="005e3-117">PIN</span></span>
-   <span data-ttu-id="005e3-118">Data de validade</span><span class="sxs-lookup"><span data-stu-id="005e3-118">Expiration date</span></span>
-   <span data-ttu-id="005e3-119">PIN e data de vencimento</span><span class="sxs-lookup"><span data-stu-id="005e3-119">PIN and expiration date</span></span> 
-   <span data-ttu-id="005e3-120">Nemhum(a)</span><span class="sxs-lookup"><span data-stu-id="005e3-120">None</span></span>

## <a name="site-settings-for-gift-card-modules"></a><span data-ttu-id="005e3-121">Configurações do site para módulos de cartão-presente</span><span class="sxs-lookup"><span data-stu-id="005e3-121">Site settings for gift card modules</span></span>

<span data-ttu-id="005e3-122">No construtor de sites do Commerce em **Configurações de site \> Extensões**, há uma configuração de módulo de cartão-presente chamada **Tipo de cartão-presente compatível**.</span><span class="sxs-lookup"><span data-stu-id="005e3-122">In Commerce site builder under **Site Settings \> Extensions**, there is a gift card module setting called **Supported gift card type**.</span></span> <span data-ttu-id="005e3-123">Esta configuração oferece suporte a três valores:</span><span class="sxs-lookup"><span data-stu-id="005e3-123">This setting supports three values:</span></span>
- <span data-ttu-id="005e3-124">**Cartão-presente do Dynamics 365** - Quando essa configuração é aplicada, o módulo do cartão-presente só permite o resgate dos cartões-presente do Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="005e3-124">**Dynamics 365 gift card** - When this setting is applied, the gift card module only allows the redemption of Dynamics 365 gift cards.</span></span> <span data-ttu-id="005e3-125">Essa configuração só tem suporte para usuários conectados no site de comércio eletrônico.</span><span class="sxs-lookup"><span data-stu-id="005e3-125">This setting is only supported for signed-in users on the e-Commerce site.</span></span>
- <span data-ttu-id="005e3-126">**Cartões-presente SVS e Givex** - Quando essa configuração é aplicada, o módulo do cartão-presente só permite o resgate dos cartões-presente Givex e SVS.</span><span class="sxs-lookup"><span data-stu-id="005e3-126">**SVS and Givex gift cards** - When this setting is applied, the gift card module only allows the redemption of Givex and SVS gift cards.</span></span> <span data-ttu-id="005e3-127">Essa configuração tem suporte para usuários conectados e anônimos no site de comércio eletrônico.</span><span class="sxs-lookup"><span data-stu-id="005e3-127">This setting is supported for signed-in and anonymous users on the e-Commerce site.</span></span>
- <span data-ttu-id="005e3-128">**Cartões-presente Dynamics 365, SVS e Givex** - Quando essa configuração é aplicada, o módulo do cartão-presente só permite o resgate dos cartões-presente Dynamics 365, Givex e SVS.</span><span class="sxs-lookup"><span data-stu-id="005e3-128">**Dynamics 365, SVS, and Givex gift cards** - When this setting is applied, the gift card module allows the redemption of Dynamics 365, Givex, and SVS gift cards.</span></span> <span data-ttu-id="005e3-129">Essa configuração só tem suporte para usuários conectados no site de comércio eletrônico.</span><span class="sxs-lookup"><span data-stu-id="005e3-129">This setting is only supported for signed-in users on the e-Commerce site.</span></span>

## <a name="add-a-gift-card-module-to-a-page"></a><span data-ttu-id="005e3-130">Adicionar um módulo de cartão-presente a uma página</span><span class="sxs-lookup"><span data-stu-id="005e3-130">Add a gift card module to a page</span></span>

<span data-ttu-id="005e3-131">Para obter instruções sobre como adicionar um módulo de cartão-presente a uma página de check-in e definir as propriedades necessárias, consulte [Módulo de finalização](add-checkout-module.md).</span><span class="sxs-lookup"><span data-stu-id="005e3-131">For instructions on how to add a gift card module to a checkout page and set the required properties, see [Checkout module](add-checkout-module.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="005e3-132">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="005e3-132">Additional resources</span></span>

[<span data-ttu-id="005e3-133">Visão geral do kit de início</span><span class="sxs-lookup"><span data-stu-id="005e3-133">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="005e3-134">Módulo de finalização da compra</span><span class="sxs-lookup"><span data-stu-id="005e3-134">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="005e3-135">Suporte a cartões-presente externos</span><span class="sxs-lookup"><span data-stu-id="005e3-135">Support for external gift cards</span></span>](./dev-itpro/gift-card.md)
