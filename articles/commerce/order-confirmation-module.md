---
title: Módulo de confirmação da ordem
description: Este tópico abrange os módulos de confirmação da ordem e descreve como criá-los no Microsoft Dynamics 365 Commerce.
author: anupamar
manager: annbe
ms.date: 10/31/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anupamar-ms
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: e339ce02bb646d0d9a68c22b24fde9b72071de6f
ms.sourcegitcommit: 295d940a345879b3dfc5991e387b91c7257019ea
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/01/2019
ms.locfileid: "2698317"
---
# <a name="order-confirmation-module"></a><span data-ttu-id="7f4fb-103">Módulo de confirmação da ordem</span><span class="sxs-lookup"><span data-stu-id="7f4fb-103">Order confirmation module</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="7f4fb-104">Este tópico abrange os módulos de confirmação da ordem e descreve como criá-los no Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="7f4fb-104">This topic covers order confirmation modules and describes how to create them in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="7f4fb-105">Visão geral</span><span class="sxs-lookup"><span data-stu-id="7f4fb-105">Overview</span></span>

<span data-ttu-id="7f4fb-106">Um módulo de confirmação de ordem será usado para mostrar a mensagem de confirmação em uma página de confirmação da ordem, depois que uma ordem é efetuada.</span><span class="sxs-lookup"><span data-stu-id="7f4fb-106">An order confirmation module is used to show a confirmation message on an order confirmation page after an order is placed.</span></span> <span data-ttu-id="7f4fb-107">O módulo de confirmação da ordem mostra o número de confirmação da ordem e o endereço de email do cliente fornecido durante a finalização da compra.</span><span class="sxs-lookup"><span data-stu-id="7f4fb-107">The order confirmation module shows the order confirmation number and the customer email address that was provided during checkout.</span></span>

<span data-ttu-id="7f4fb-108">Quando uma ordem é efetuada durante a finalização da compra, o número de confirmação da ordem e o endereço de email do cliente são passados para a página de confirmação da ordem como uma cadeia de caracteres de consulta na URL da página.</span><span class="sxs-lookup"><span data-stu-id="7f4fb-108">When an order is placed during checkout, the order confirmation number and customer email address are passed to the order confirmation page as a query string in the page's URL.</span></span> <span data-ttu-id="7f4fb-109">O módulo de confirmação da ordem recebe estas informações e renderiza o status da ordem na página de confirmação da ordem.</span><span class="sxs-lookup"><span data-stu-id="7f4fb-109">The order confirmation module receives this information and renders the order status on the order confirmation page.</span></span> <span data-ttu-id="7f4fb-110">O módulo de confirmação da ordem exige que este contexto da página forneça o status da ordem.</span><span class="sxs-lookup"><span data-stu-id="7f4fb-110">The order confirmation module requires this page context to provide the status of the order.</span></span>

## <a name="order-confirmation-module-properties"></a><span data-ttu-id="7f4fb-111">Propriedades do módulo de confirmação da ordem</span><span class="sxs-lookup"><span data-stu-id="7f4fb-111">Order confirmation module properties</span></span>

| <span data-ttu-id="7f4fb-112">Nome da propriedade</span><span class="sxs-lookup"><span data-stu-id="7f4fb-112">Property name</span></span> | <span data-ttu-id="7f4fb-113">Valores</span><span class="sxs-lookup"><span data-stu-id="7f4fb-113">Values</span></span> | <span data-ttu-id="7f4fb-114">Descrição</span><span class="sxs-lookup"><span data-stu-id="7f4fb-114">Description</span></span> |
|---------------|--------|-------------|
| <span data-ttu-id="7f4fb-115">Cabeçalho</span><span class="sxs-lookup"><span data-stu-id="7f4fb-115">Heading</span></span>       | <span data-ttu-id="7f4fb-116">Texto do cabeçalho e tag do cabeçalho (**H1**, **H2**, **H3**, **H4**, **H5** ou **H6**)</span><span class="sxs-lookup"><span data-stu-id="7f4fb-116">Heading text and heading tag (**H1**, **H2**, **H3**, **H4**, **H5**, or **H6**)</span></span> | <span data-ttu-id="7f4fb-117">O módulo de confirmação da ordem pode ter um título.</span><span class="sxs-lookup"><span data-stu-id="7f4fb-117">The order confirmation module can have a heading.</span></span> <span data-ttu-id="7f4fb-118">Por padrão, a tag de cabeçalho **H2** é usada para o cabeçalho.</span><span class="sxs-lookup"><span data-stu-id="7f4fb-118">By default, the **H2** heading tag is used for the heading.</span></span> <span data-ttu-id="7f4fb-119">No entanto, a tag pode ser alterada para atender aos requisitos de acessibilidade.</span><span class="sxs-lookup"><span data-stu-id="7f4fb-119">However, the tag can be changed to meet accessibility requirements.</span></span> |

## <a name="modules-that-can-be-used-in-an-order-confirmation-page-module"></a><span data-ttu-id="7f4fb-120">Os módulos que podem ser usados em um módulo da página de confirmação da ordem</span><span class="sxs-lookup"><span data-stu-id="7f4fb-120">Modules that can be used in an order confirmation page module</span></span> 

- <span data-ttu-id="7f4fb-121">**Recomendações** – O módulo de recomendações pode ser colocado na página de confirmação da ordem para sugerir outros produtos para o cliente.</span><span class="sxs-lookup"><span data-stu-id="7f4fb-121">**Recommendations** – The recommendations module can be put on the order confirmation page to suggest other products to the customer.</span></span>
- <span data-ttu-id="7f4fb-122">**Marketing** – O módulo de marketing pode adicionar o conteúdo de marketing à página de confirmação da ordem.</span><span class="sxs-lookup"><span data-stu-id="7f4fb-122">**Marketing** – The marketing module can add marketing content to the order confirmation page.</span></span>

## <a name="create-an-order-confirmation-page-module"></a><span data-ttu-id="7f4fb-123">Criar um módulo da página de confirmação da ordem</span><span class="sxs-lookup"><span data-stu-id="7f4fb-123">Create an order confirmation page module</span></span>

1. <span data-ttu-id="7f4fb-124">Criar um modelo da página chamado **modelo de confirmação da ordem**.</span><span class="sxs-lookup"><span data-stu-id="7f4fb-124">Create a page template that is named **order confirmation template**.</span></span>
1. <span data-ttu-id="7f4fb-125">No slot **Principal** da página padrão, adicione um módulo de confirmação da ordem.</span><span class="sxs-lookup"><span data-stu-id="7f4fb-125">In the **Main** slot of the default page, add an order confirmation module.</span></span>
1. <span data-ttu-id="7f4fb-126">No módulo de confirmação da ordem, adicione um módulo de recomendações.</span><span class="sxs-lookup"><span data-stu-id="7f4fb-126">In the order confirmation module, add a recommendations module.</span></span>
1. <span data-ttu-id="7f4fb-127">Salve e exiba o modelo.</span><span class="sxs-lookup"><span data-stu-id="7f4fb-127">Save and preview the template.</span></span> <span data-ttu-id="7f4fb-128">O módulo de confirmação da ordem não deve ser processado porque exige o contexto do número de confirmação da ordem.</span><span class="sxs-lookup"><span data-stu-id="7f4fb-128">The order confirmation module should not be rendered, because it requires the context of the order confirmation number.</span></span>
1. <span data-ttu-id="7f4fb-129">Faça check-in do modelo e publique-o.</span><span class="sxs-lookup"><span data-stu-id="7f4fb-129">Check in the template, and publish it.</span></span>
1. <span data-ttu-id="7f4fb-130">Use o modelo de confirmação da ordem que você acabou de criar para criar uma página chamada **página de confirmação da ordem**.</span><span class="sxs-lookup"><span data-stu-id="7f4fb-130">Use the order confirmation template that you just created to create a page that is named **order confirmation page**.</span></span>
1. <span data-ttu-id="7f4fb-131">Adicione a página padrão à descrição da página.</span><span class="sxs-lookup"><span data-stu-id="7f4fb-131">Add the default page to the page outline.</span></span>
1. <span data-ttu-id="7f4fb-132">No slot **Cabeçalho** , adicione um fragmento do cabeçalho.</span><span class="sxs-lookup"><span data-stu-id="7f4fb-132">In the **Header** slot, add a header fragment.</span></span>
1. <span data-ttu-id="7f4fb-133">No slot **Rodapé** , adicione um fragmento do rodapé.</span><span class="sxs-lookup"><span data-stu-id="7f4fb-133">In the **Footer** slot, add a footer fragment.</span></span>
1. <span data-ttu-id="7f4fb-134">No slot **Principal**, adicione um módulo de confirmação da ordem.</span><span class="sxs-lookup"><span data-stu-id="7f4fb-134">In the **Main** slot, add an order confirmation module.</span></span>
1. <span data-ttu-id="7f4fb-135">No painel de propriedade do módulo de confirmação da ordem, adicione o título **Confirmação da ordem**.</span><span class="sxs-lookup"><span data-stu-id="7f4fb-135">In the property pane of the order confirmation module, add the heading **Order confirmation**.</span></span>
1. <span data-ttu-id="7f4fb-136">Abaixo do módulo de confirmação da ordem, adicione um módulo de recomendações e configure-o de forma que ele use as configurações **Novo** e **Mais Vendidos**.</span><span class="sxs-lookup"><span data-stu-id="7f4fb-136">Below the order confirmation module, add a recommendations module, and configure it so that it uses the **New** and **Best Selling** settings.</span></span>
1. <span data-ttu-id="7f4fb-137">Salve e visualize a página, faça check-in e publique-a.</span><span class="sxs-lookup"><span data-stu-id="7f4fb-137">Save and preview the page, check it in, and publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="7f4fb-138">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="7f4fb-138">Additional resources</span></span>

[<span data-ttu-id="7f4fb-139">Visão geral do kit de início</span><span class="sxs-lookup"><span data-stu-id="7f4fb-139">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="7f4fb-140">Módulo de contêiner</span><span class="sxs-lookup"><span data-stu-id="7f4fb-140">Container module</span></span>](add-container-module.md)

[<span data-ttu-id="7f4fb-141">Módulo de caixa de compra</span><span class="sxs-lookup"><span data-stu-id="7f4fb-141">Buy box module</span></span>](add-buy-box.md)

[<span data-ttu-id="7f4fb-142">Módulo de carrinho</span><span class="sxs-lookup"><span data-stu-id="7f4fb-142">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="7f4fb-143">Módulo de finalização da compra</span><span class="sxs-lookup"><span data-stu-id="7f4fb-143">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="7f4fb-144">Módulo de cabeçalho</span><span class="sxs-lookup"><span data-stu-id="7f4fb-144">Header module</span></span>](author-header-module.md)

[<span data-ttu-id="7f4fb-145">Módulo de rodapé</span><span class="sxs-lookup"><span data-stu-id="7f4fb-145">Footer module</span></span>](author-footer-module.md)
