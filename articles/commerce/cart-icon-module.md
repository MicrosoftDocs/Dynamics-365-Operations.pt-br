---
title: Módulo de ícone de carrinho
description: Este tópico abrange o módulo de ícone de carrinho e descreve como adicioná-lo às páginas do site no Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 10/20/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 43bc274548de016f24569001bac94aff324bea12
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5213225"
---
# <a name="cart-icon-module"></a><span data-ttu-id="5a50e-103">Módulo de ícone de carrinho</span><span class="sxs-lookup"><span data-stu-id="5a50e-103">Cart icon module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="5a50e-104">Este tópico abrange o módulo de ícone de carrinho e descreve como adicioná-lo às páginas do site no Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="5a50e-104">This topic covers the cart icon module and describes how to add it to site pages in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="5a50e-105">O módulo de ícone de carrinho representa o carrinho no módulo de cabeçalho da página e mostra o número de itens no carrinho.</span><span class="sxs-lookup"><span data-stu-id="5a50e-105">The cart icon module represents the cart in the header module of the page, and shows the number of items in the cart.</span></span> <span data-ttu-id="5a50e-106">O módulo do ícone de carrinho também exibe um resumo do carrinho (também conhecido como um mini carrinho) quando mouse é passado pelo ícone de carrinho.</span><span class="sxs-lookup"><span data-stu-id="5a50e-106">The cart icon module also displays a cart summary (also known as a mini cart) when the cart icon is hovered over.</span></span> <span data-ttu-id="5a50e-107">O mini carrinho fornece ao usuário um resumo dos itens no carrinho sem ter que navegar até a página do carrinho.</span><span class="sxs-lookup"><span data-stu-id="5a50e-107">The mini cart provides the user with a summary of the items in the cart without having to navigate to the cart page.</span></span> <span data-ttu-id="5a50e-108">Além disso, ele também permite que o usuário vá diretamente para a página de check-out se estiver satisfeito com o resumo.</span><span class="sxs-lookup"><span data-stu-id="5a50e-108">In addition, it also allows the user to directly go to checkout page if they are happy with the summary.</span></span> <span data-ttu-id="5a50e-109">Isso reduz o número de navegações de página e torna o check-out mais rápido.</span><span class="sxs-lookup"><span data-stu-id="5a50e-109">This reduces the number of page navigations and makes checkout faster.</span></span> 

> [!NOTE]
> <span data-ttu-id="5a50e-110">O suporte ao módulo de ícone de carrinho está disponível no Dynamics 365 Commerce versão 10.0.11.</span><span class="sxs-lookup"><span data-stu-id="5a50e-110">Support for the cart icon module is available in the Dynamics 365 Commerce 10.0.11 release.</span></span>

<span data-ttu-id="5a50e-111">A imagem a seguir mostra um exemplo de um módulo de ícone de carrinho que exibe um minicarrinho no cabeçalho Fabrikam.</span><span class="sxs-lookup"><span data-stu-id="5a50e-111">The following image shows an example of a cart icon module that displays a mini cart in the Fabrikam header.</span></span>

![Exemplo de um módulo de ícone de carrinho](./media/ecommerce-Minicart.PNG)

## <a name="module-properties"></a><span data-ttu-id="5a50e-113">Propriedades do módulo</span><span class="sxs-lookup"><span data-stu-id="5a50e-113">Module properties</span></span>

- <span data-ttu-id="5a50e-114">**Mostrar mini carrinho** – Quando verdadeiro, esta propriedade permite que um resumo do carrinho (mini carrinho) seja exibido quando o ícone do carrinho é focalizado.</span><span class="sxs-lookup"><span data-stu-id="5a50e-114">**Show mini cart** – When true, this property enables a cart summary (mini cart) to be displayed when the cart icon is hovered over.</span></span> <span data-ttu-id="5a50e-115">Essa funcionalidade só tem suporte em portas de exibição de desktop.</span><span class="sxs-lookup"><span data-stu-id="5a50e-115">This functionality is only supported for desktop view ports.</span></span>

## <a name="add-a-cart-icon-module-to-a-page"></a><span data-ttu-id="5a50e-116">Adicionar um módulo do ícone de carrinho a uma página</span><span class="sxs-lookup"><span data-stu-id="5a50e-116">Add a cart icon module to a page</span></span>

<span data-ttu-id="5a50e-117">Para adicionar um módulo de ícone de carrinho, consulte [Módulo de cabeçalho](author-header-module.md).</span><span class="sxs-lookup"><span data-stu-id="5a50e-117">To add a cart icon module, see [Header module](author-header-module.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="5a50e-118">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="5a50e-118">Additional resources</span></span>

[<span data-ttu-id="5a50e-119">Módulo de carrinho</span><span class="sxs-lookup"><span data-stu-id="5a50e-119">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="5a50e-120">Módulo de finalização da compra</span><span class="sxs-lookup"><span data-stu-id="5a50e-120">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="5a50e-121">Módulo de pagamento</span><span class="sxs-lookup"><span data-stu-id="5a50e-121">Payment module</span></span>](payment-module.md)

[<span data-ttu-id="5a50e-122">Módulo de endereço de remessa</span><span class="sxs-lookup"><span data-stu-id="5a50e-122">Shipping address module</span></span>](ship-address-module.md)

[<span data-ttu-id="5a50e-123">Módulo de opções de entrega</span><span class="sxs-lookup"><span data-stu-id="5a50e-123">Delivery options module</span></span>](delivery-options-module.md)

[<span data-ttu-id="5a50e-124">Módulo de informações sobre retirada</span><span class="sxs-lookup"><span data-stu-id="5a50e-124">Pickup information module</span></span>](pickup-info-module.md)

[<span data-ttu-id="5a50e-125">Módulo de detalhes da ordem</span><span class="sxs-lookup"><span data-stu-id="5a50e-125">Order details module</span></span>](order-confirmation-module.md)

[<span data-ttu-id="5a50e-126">Módulo de cartão-presente</span><span class="sxs-lookup"><span data-stu-id="5a50e-126">Gift card module</span></span>](add-giftcard.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]