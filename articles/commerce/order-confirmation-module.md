---
title: Módulo de detalhes da ordem
description: Este tópico abrange os módulos de detalhes da ordem e descreve como usá-los no Microsoft Dynamics 365 Commerce.
author: anupamar
manager: annbe
ms.date: 01/23/2020
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
ms.openlocfilehash: cb09a0b6ce1e48707f96021e9fad0006d9c1c55c
ms.sourcegitcommit: 829329220475ed8cff5a5db92a59dd90c22b04fa
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/05/2020
ms.locfileid: "3026008"
---
# <a name="order-details-module"></a><span data-ttu-id="b170d-103">Módulo de detalhes da ordem</span><span class="sxs-lookup"><span data-stu-id="b170d-103">Order details module</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="b170d-104">Este tópico abrange os módulos de detalhes da ordem e descreve como usá-los no Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="b170d-104">This topic covers order details modules and describes how to use them in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="b170d-105">Visão geral</span><span class="sxs-lookup"><span data-stu-id="b170d-105">Overview</span></span>

<span data-ttu-id="b170d-106">O módulo de detalhes de ordem é usado para mostrar detalhes da confirmação da ordem após ela ser colocada.</span><span class="sxs-lookup"><span data-stu-id="b170d-106">The order details module is used to show order confirmation details after an order has been placed.</span></span> <span data-ttu-id="b170d-107">Ele mostra a ID de confirmação da ordem, as informações de contato da ordem e outros detalhes da ordem, como os itens que foram comprados, as informações de pagamento e o método de remessa.</span><span class="sxs-lookup"><span data-stu-id="b170d-107">It shows the order confirmation ID, order contact information, and other order details, such as the items that were purchased, payment information, and the shipping method.</span></span>

## <a name="order-confirmation-module-properties"></a><span data-ttu-id="b170d-108">Propriedades do módulo de confirmação da ordem</span><span class="sxs-lookup"><span data-stu-id="b170d-108">Order confirmation module properties</span></span>

| <span data-ttu-id="b170d-109">Nome da propriedade</span><span class="sxs-lookup"><span data-stu-id="b170d-109">Property name</span></span>  | <span data-ttu-id="b170d-110">Valores</span><span class="sxs-lookup"><span data-stu-id="b170d-110">Values</span></span> | <span data-ttu-id="b170d-111">Descrição</span><span class="sxs-lookup"><span data-stu-id="b170d-111">Description</span></span> |
|----------------|--------|-------------|
| <span data-ttu-id="b170d-112">Cabeçalho</span><span class="sxs-lookup"><span data-stu-id="b170d-112">Heading</span></span>        | <span data-ttu-id="b170d-113">Texto do cabeçalho e tag do cabeçalho (**H1**, **H2**, **H3**, **H4**, **H5** ou **H6**)</span><span class="sxs-lookup"><span data-stu-id="b170d-113">Heading text and heading tag (**H1**, **H2**, **H3**, **H4**, **H5**, or **H6**)</span></span> | <span data-ttu-id="b170d-114">O módulo de confirmação da ordem pode ter um título.</span><span class="sxs-lookup"><span data-stu-id="b170d-114">The order confirmation module can have a heading.</span></span> <span data-ttu-id="b170d-115">Por padrão, a tag de cabeçalho **H2** é usada para o cabeçalho.</span><span class="sxs-lookup"><span data-stu-id="b170d-115">By default, the **H2** heading tag is used for the heading.</span></span> <span data-ttu-id="b170d-116">No entanto, a tag pode ser alterada para atender aos requisitos de acessibilidade.</span><span class="sxs-lookup"><span data-stu-id="b170d-116">However, the tag can be changed to meet accessibility requirements.</span></span> |
| <span data-ttu-id="b170d-117">Número do contato</span><span class="sxs-lookup"><span data-stu-id="b170d-117">Contact number</span></span> | <span data-ttu-id="b170d-118">Text</span><span class="sxs-lookup"><span data-stu-id="b170d-118">Text</span></span> | <span data-ttu-id="b170d-119">Um número de contato pode ser fornecido para perguntas relativas a ordens.</span><span class="sxs-lookup"><span data-stu-id="b170d-119">A contact number can be provided for order-related questions.</span></span> |

## <a name="modules-that-can-be-used-on-an-order-details-page"></a><span data-ttu-id="b170d-120">Os módulos que podem ser usados em uma página de detalhes da ordem</span><span class="sxs-lookup"><span data-stu-id="b170d-120">Modules that can be used on an order details page</span></span>

<span data-ttu-id="b170d-121">Ao criar uma página de detalhes da ordem, você pode adicionar outros módulos relevantes além do módulo de detalhes da ordem.</span><span class="sxs-lookup"><span data-stu-id="b170d-121">When you create an order details page, you can add other relevant modules in addition to the order details module.</span></span> <span data-ttu-id="b170d-122">Eis alguns exemplos:</span><span class="sxs-lookup"><span data-stu-id="b170d-122">Here are some examples:</span></span>

- <span data-ttu-id="b170d-123">**Módulo de recomendações** – O módulo de recomendações pode ser adicionado à página de detalhes da ordem para sugerir outros produtos para o cliente.</span><span class="sxs-lookup"><span data-stu-id="b170d-123">**Recommendations module** – The recommendations module can be added to the order details page to suggest other products to the customer.</span></span>
- <span data-ttu-id="b170d-124">**Módulos de marketing** – qualquer módulo de marketing pode ser adicionado à página de detalhes da ordem para mostrar o conteúdo de marketing.</span><span class="sxs-lookup"><span data-stu-id="b170d-124">**Marketing modules** – Any marketing module can be added to the order details page to show marketing content.</span></span>

## <a name="create-an-order-details-page-module"></a><span data-ttu-id="b170d-125">Criar um módulo da página de detalhes da ordem</span><span class="sxs-lookup"><span data-stu-id="b170d-125">Create an order details page module</span></span>

1. <span data-ttu-id="b170d-126">Criar um modelo da página chamado **Modelo de detalhes da ordem**.</span><span class="sxs-lookup"><span data-stu-id="b170d-126">Create a page template that is named **Order details template**.</span></span>
1. <span data-ttu-id="b170d-127">No slot **Principal** da página padrão, adicione um módulo de detalhes da ordem.</span><span class="sxs-lookup"><span data-stu-id="b170d-127">In the **Main** slot of the default page, add an order details module.</span></span>
1. <span data-ttu-id="b170d-128">No módulo de detalhes da ordem, adicione um módulo de recomendações.</span><span class="sxs-lookup"><span data-stu-id="b170d-128">In the order details module, add a recommendations module.</span></span>
1. <span data-ttu-id="b170d-129">Salve e exiba o modelo.</span><span class="sxs-lookup"><span data-stu-id="b170d-129">Save and preview the template.</span></span> <span data-ttu-id="b170d-130">O módulo de detalhes da ordem não será processado porque ele exige o contexto do número de confirmação da ordem.</span><span class="sxs-lookup"><span data-stu-id="b170d-130">The order details module won't be rendered, because it requires the context of the order confirmation number.</span></span>
1. <span data-ttu-id="b170d-131">Termine de editar o modelo e publique-o.</span><span class="sxs-lookup"><span data-stu-id="b170d-131">Finish editing the template, and publish it.</span></span>
1. <span data-ttu-id="b170d-132">Use o modelo de detalhes da ordem recém-criado para criar uma página chamada **página de detalhes da ordem**.</span><span class="sxs-lookup"><span data-stu-id="b170d-132">Use the order details template that you just created to create a page that is named **order details page**.</span></span>
1. <span data-ttu-id="b170d-133">Adicione a página padrão à descrição da página.</span><span class="sxs-lookup"><span data-stu-id="b170d-133">Add the default page to the page outline.</span></span>
1. <span data-ttu-id="b170d-134">No slot **Cabeçalho** , adicione um fragmento do cabeçalho.</span><span class="sxs-lookup"><span data-stu-id="b170d-134">In the **Header** slot, add a header fragment.</span></span>
1. <span data-ttu-id="b170d-135">No slot **Rodapé** , adicione um fragmento do rodapé.</span><span class="sxs-lookup"><span data-stu-id="b170d-135">In the **Footer** slot, add a footer fragment.</span></span>
1. <span data-ttu-id="b170d-136">No slot **Principal**, adicione um módulo de detalhes da ordem.</span><span class="sxs-lookup"><span data-stu-id="b170d-136">In the **Main** slot, add an order details module.</span></span>
1. <span data-ttu-id="b170d-137">No painel de propriedade do módulo de detalhes da ordem, adicione o título **Detalhes da ordem**.</span><span class="sxs-lookup"><span data-stu-id="b170d-137">In the property pane for the order details module, add the heading **Order details**.</span></span>
1. <span data-ttu-id="b170d-138">Abaixo do módulo de detalhes da ordem, adicione um módulo de recomendações e configure-o de forma que ele use as configurações **Novo** e **Mais Vendidos**.</span><span class="sxs-lookup"><span data-stu-id="b170d-138">Below the order details module, add a recommendations module, and configure it so that it uses the **New** and **Best Selling** settings.</span></span>
1. <span data-ttu-id="b170d-139">Salve e exiba a página.</span><span class="sxs-lookup"><span data-stu-id="b170d-139">Save and preview the page.</span></span>
1. <span data-ttu-id="b170d-140">Termine de editar a página e publique-a.</span><span class="sxs-lookup"><span data-stu-id="b170d-140">Finish editing the page, and publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="b170d-141">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="b170d-141">Additional resources</span></span>

[<span data-ttu-id="b170d-142">Visão geral do kit de início</span><span class="sxs-lookup"><span data-stu-id="b170d-142">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="b170d-143">Módulo de contêiner</span><span class="sxs-lookup"><span data-stu-id="b170d-143">Container module</span></span>](add-container-module.md)

[<span data-ttu-id="b170d-144">Módulo de caixa de compra</span><span class="sxs-lookup"><span data-stu-id="b170d-144">Buy box module</span></span>](add-buy-box.md)

[<span data-ttu-id="b170d-145">Módulo de carrinho</span><span class="sxs-lookup"><span data-stu-id="b170d-145">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="b170d-146">Módulo de finalização da compra</span><span class="sxs-lookup"><span data-stu-id="b170d-146">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="b170d-147">Módulo de cabeçalho</span><span class="sxs-lookup"><span data-stu-id="b170d-147">Header module</span></span>](author-header-module.md)

[<span data-ttu-id="b170d-148">Módulo de rodapé</span><span class="sxs-lookup"><span data-stu-id="b170d-148">Footer module</span></span>](author-footer-module.md)
