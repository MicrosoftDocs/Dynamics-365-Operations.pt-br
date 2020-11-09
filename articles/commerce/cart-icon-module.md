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
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 4ab1609d332b96c0588b06aa086dd4fee944e5d9
ms.sourcegitcommit: 765056b5dc1d0a8c27e56ff2cbd310ad3349ff09
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/20/2020
ms.locfileid: "4055751"
---
# <a name="cart-icon-module"></a><span data-ttu-id="43e19-103">Módulo de ícone de carrinho</span><span class="sxs-lookup"><span data-stu-id="43e19-103">Cart icon module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="43e19-104">Este tópico abrange o módulo de ícone de carrinho e descreve como adicioná-lo às páginas do site no Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="43e19-104">This topic covers the cart icon module and describes how to add it to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="43e19-105">Visão Geral</span><span class="sxs-lookup"><span data-stu-id="43e19-105">Overview</span></span>

<span data-ttu-id="43e19-106">O módulo de ícone de carrinho representa o carrinho no módulo de cabeçalho da página e mostra o número de itens no carrinho.</span><span class="sxs-lookup"><span data-stu-id="43e19-106">The cart icon module represents the cart in the header module of the page, and shows the number of items in the cart.</span></span> <span data-ttu-id="43e19-107">O módulo do ícone de carrinho também exibe um resumo do carrinho (também conhecido como um mini carrinho) quando mouse é passado pelo ícone de carrinho.</span><span class="sxs-lookup"><span data-stu-id="43e19-107">The cart icon module also displays a cart summary (also known as a mini cart) when the cart icon is hovered over.</span></span> <span data-ttu-id="43e19-108">O mini carrinho fornece ao usuário um resumo dos itens no carrinho sem ter que navegar até a página do carrinho.</span><span class="sxs-lookup"><span data-stu-id="43e19-108">The mini cart provides the user with a summary of the items in the cart without having to navigate to the cart page.</span></span> <span data-ttu-id="43e19-109">Além disso, ele também permite que o usuário vá diretamente para a página de check-out se estiver satisfeito com o resumo.</span><span class="sxs-lookup"><span data-stu-id="43e19-109">In addition, it also allows the user to directly go to checkout page if they are happy with the summary.</span></span> <span data-ttu-id="43e19-110">Isso reduz o número de navegações de página e torna o check-out mais rápido.</span><span class="sxs-lookup"><span data-stu-id="43e19-110">This reduces the number of page navigations and makes checkout faster.</span></span> 

> [!NOTE]
> <span data-ttu-id="43e19-111">O suporte ao módulo de ícone de carrinho está disponível no Dynamics 365 Commerce versão 10.0.11.</span><span class="sxs-lookup"><span data-stu-id="43e19-111">Support for the cart icon module is available in the Dynamics 365 Commerce 10.0.11 release.</span></span>

<span data-ttu-id="43e19-112">A imagem a seguir mostra um exemplo de um módulo de ícone de carrinho que exibe um minicarrinho no cabeçalho Fabrikam.</span><span class="sxs-lookup"><span data-stu-id="43e19-112">The following image shows an example of a cart icon module that displays a mini cart in the Fabrikam header.</span></span>

![Exemplo de um módulo de ícone de carrinho](./media/ecommerce-Minicart.PNG)

## <a name="module-properties"></a><span data-ttu-id="43e19-114">Propriedades do módulo</span><span class="sxs-lookup"><span data-stu-id="43e19-114">Module properties</span></span>

- <span data-ttu-id="43e19-115">**Mostrar mini carrinho** – Quando verdadeiro, esta propriedade permite que um resumo do carrinho (mini carrinho) seja exibido quando o ícone do carrinho é focalizado.</span><span class="sxs-lookup"><span data-stu-id="43e19-115">**Show mini cart** – When true, this property enables a cart summary (mini cart) to be displayed when the cart icon is hovered over.</span></span> <span data-ttu-id="43e19-116">Essa funcionalidade só tem suporte em portas de exibição de desktop.</span><span class="sxs-lookup"><span data-stu-id="43e19-116">This functionality is only supported for desktop view ports.</span></span>

## <a name="add-a-cart-icon-module-to-a-page"></a><span data-ttu-id="43e19-117">Adicionar um módulo do ícone de carrinho a uma página</span><span class="sxs-lookup"><span data-stu-id="43e19-117">Add a cart icon module to a page</span></span>

<span data-ttu-id="43e19-118">Para adicionar um módulo de ícone de carrinho, consulte [Módulo de cabeçalho](author-header-module.md).</span><span class="sxs-lookup"><span data-stu-id="43e19-118">To add a cart icon module, see [Header module](author-header-module.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="43e19-119">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="43e19-119">Additional resources</span></span>

[<span data-ttu-id="43e19-120">Módulo de carrinho</span><span class="sxs-lookup"><span data-stu-id="43e19-120">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="43e19-121">Módulo de finalização da compra</span><span class="sxs-lookup"><span data-stu-id="43e19-121">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="43e19-122">Módulo de pagamento</span><span class="sxs-lookup"><span data-stu-id="43e19-122">Payment module</span></span>](payment-module.md)

[<span data-ttu-id="43e19-123">Módulo do endereço de remessa</span><span class="sxs-lookup"><span data-stu-id="43e19-123">Shipping address module</span></span>](ship-address-module.md)

[<span data-ttu-id="43e19-124">Módulo de opções de entrega</span><span class="sxs-lookup"><span data-stu-id="43e19-124">Delivery options module</span></span>](delivery-options-module.md)

[<span data-ttu-id="43e19-125">Módulo de detalhes da ordem</span><span class="sxs-lookup"><span data-stu-id="43e19-125">Order details module</span></span>](order-confirmation-module.md)

[<span data-ttu-id="43e19-126">Módulo de vale-presente</span><span class="sxs-lookup"><span data-stu-id="43e19-126">Gift card module</span></span>](add-giftcard.md)
