---
title: Módulo de ícone de carrinho
description: Este tópico abrange o módulo de ícone de carrinho e descreve como adicioná-lo às páginas do site no Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 05/28/2020
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
ms.openlocfilehash: 6771a84118504cd5c8e44302380eb970e4658902
ms.sourcegitcommit: b52477b7d0d52102a7ca2fb95f4ebfa30ecd9f54
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/29/2020
ms.locfileid: "3411080"
---
# <a name="cart-icon-module"></a><span data-ttu-id="ebcc9-103">Módulo de ícone de carrinho</span><span class="sxs-lookup"><span data-stu-id="ebcc9-103">Cart icon module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="ebcc9-104">Este tópico abrange o módulo de ícone de carrinho e descreve como adicioná-lo às páginas do site no Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="ebcc9-104">This topic covers the cart icon module and describes how to add it to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="ebcc9-105">Visão Geral</span><span class="sxs-lookup"><span data-stu-id="ebcc9-105">Overview</span></span>

<span data-ttu-id="ebcc9-106">O módulo de ícone de carrinho representa o carrinho no módulo de cabeçalho da página e mostra o número de itens no carrinho.</span><span class="sxs-lookup"><span data-stu-id="ebcc9-106">The cart icon module represents the cart in the header module of the page, and shows the number of items in the cart.</span></span> <span data-ttu-id="ebcc9-107">O módulo do ícone de carrinho também exibe um resumo do carrinho (também conhecido como um mini carrinho) quando mouse é passado pelo ícone de carrinho.</span><span class="sxs-lookup"><span data-stu-id="ebcc9-107">The cart icon module also displays a cart summary (also known as a mini cart) when the cart icon is hovered over.</span></span> <span data-ttu-id="ebcc9-108">O mini carrinho fornece ao usuário um resumo dos itens no carrinho sem ter que navegar até a página do carrinho.</span><span class="sxs-lookup"><span data-stu-id="ebcc9-108">The mini cart provides the user with a summary of the items in the cart without having to navigate to the cart page.</span></span> <span data-ttu-id="ebcc9-109">Além disso, ele também permite que o usuário vá diretamente para a página de check-out se estiver satisfeito com o resumo.</span><span class="sxs-lookup"><span data-stu-id="ebcc9-109">In addition, it also allows the user to directly go to checkout page if they are happy with the summary.</span></span> <span data-ttu-id="ebcc9-110">Isso reduz o número de navegações de página e torna o check-out mais rápido.</span><span class="sxs-lookup"><span data-stu-id="ebcc9-110">This reduces the number of page navigations and makes checkout faster.</span></span> 

<span data-ttu-id="ebcc9-111">A imagem a seguir mostra um exemplo de um módulo de ícone de carrinho que exibe um minicarrinho no cabeçalho Fabrikam.</span><span class="sxs-lookup"><span data-stu-id="ebcc9-111">The following image shows an example of a cart icon module that displays a mini cart in the Fabrikam header.</span></span>

![Exemplo de um módulo de ícone de carrinho](./media/ecommerce-Minicart.PNG)

## <a name="module-properties"></a><span data-ttu-id="ebcc9-113">Propriedades do módulo</span><span class="sxs-lookup"><span data-stu-id="ebcc9-113">Module properties</span></span>

- <span data-ttu-id="ebcc9-114">**Mostrar mini carrinho** – Quando verdadeiro, esta propriedade permite que um resumo do carrinho (mini carrinho) seja exibido quando o ícone do carrinho é focalizado.</span><span class="sxs-lookup"><span data-stu-id="ebcc9-114">**Show mini cart** – When true, this property enables a cart summary (mini cart) to be displayed when the cart icon is hovered over.</span></span> <span data-ttu-id="ebcc9-115">Essa funcionalidade só tem suporte em portas de exibição de desktop.</span><span class="sxs-lookup"><span data-stu-id="ebcc9-115">This functionality is only supported for desktop view ports.</span></span>


## <a name="add-a-cart-icon-module-to-a-page"></a><span data-ttu-id="ebcc9-116">Adicionar um módulo do ícone de carrinho a uma página</span><span class="sxs-lookup"><span data-stu-id="ebcc9-116">Add a cart icon module to a page</span></span>

<span data-ttu-id="ebcc9-117">Para adicionar um módulo de ícone de carrinho, consulte [Módulo de cabeçalho](author-header-module.md).</span><span class="sxs-lookup"><span data-stu-id="ebcc9-117">To add a cart icon module, see [Header module](author-header-module.md).</span></span>


## <a name="additional-resources"></a><span data-ttu-id="ebcc9-118">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="ebcc9-118">Additional resources</span></span>

[<span data-ttu-id="ebcc9-119">Módulo de caixa de compra</span><span class="sxs-lookup"><span data-stu-id="ebcc9-119">Buy box module</span></span>](add-buy-box.md)

[<span data-ttu-id="ebcc9-120">Módulo de carrinho</span><span class="sxs-lookup"><span data-stu-id="ebcc9-120">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="ebcc9-121">Módulo de finalização da compra</span><span class="sxs-lookup"><span data-stu-id="ebcc9-121">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="ebcc9-122">Módulo de confirmação da ordem</span><span class="sxs-lookup"><span data-stu-id="ebcc9-122">Order confirmation module</span></span>](order-confirmation-module.md)

[<span data-ttu-id="ebcc9-123">Módulo de cabeçalho</span><span class="sxs-lookup"><span data-stu-id="ebcc9-123">Header module</span></span>](author-header-module.md)

[<span data-ttu-id="ebcc9-124">Módulo de rodapé</span><span class="sxs-lookup"><span data-stu-id="ebcc9-124">Footer module</span></span>](author-footer-module.md)
