---
title: Módulo de detalhes da ordem
description: Este tópico abrange os módulos de detalhes da ordem e descreve como usá-los no Microsoft Dynamics 365 Commerce.
author: anupamar
manager: annbe
ms.date: 06/18/2020
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
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 6610d2abe0a1b03ddd763f9a65fc1dab42f1da1b
ms.sourcegitcommit: 49f3011b8a6d8cdd038e153d8cb3cf773be25ae4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "4015171"
---
# <a name="order-details-module"></a><span data-ttu-id="beaef-103">Módulo de detalhes da ordem</span><span class="sxs-lookup"><span data-stu-id="beaef-103">Order details module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="beaef-104">Este tópico abrange os módulos de detalhes da ordem e descreve como usá-los no Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="beaef-104">This topic covers order details modules and describes how to use them in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="beaef-105">Visão geral</span><span class="sxs-lookup"><span data-stu-id="beaef-105">Overview</span></span>

<span data-ttu-id="beaef-106">O módulo de detalhes de ordem é usado para mostrar detalhes da confirmação da ordem após ela ser colocada.</span><span class="sxs-lookup"><span data-stu-id="beaef-106">The order details module is used to show order confirmation details after an order has been placed.</span></span> <span data-ttu-id="beaef-107">Ele mostra a ID de confirmação da ordem, as informações de contato da ordem e outros detalhes da ordem, como os itens que foram comprados, as informações de pagamento e o método de remessa.</span><span class="sxs-lookup"><span data-stu-id="beaef-107">It shows the order confirmation ID, order contact information, and other order details, such as the items that were purchased, payment information, and the shipping method.</span></span>

## <a name="order-details-module-properties"></a><span data-ttu-id="beaef-108">Propriedades do módulo de detalhes da ordem</span><span class="sxs-lookup"><span data-stu-id="beaef-108">Order details module properties</span></span>

| <span data-ttu-id="beaef-109">Nome da propriedade</span><span class="sxs-lookup"><span data-stu-id="beaef-109">Property name</span></span>  | <span data-ttu-id="beaef-110">Valores</span><span class="sxs-lookup"><span data-stu-id="beaef-110">Values</span></span> | <span data-ttu-id="beaef-111">descrição</span><span class="sxs-lookup"><span data-stu-id="beaef-111">Description</span></span> |
|----------------|--------|-------------|
| <span data-ttu-id="beaef-112">Título</span><span class="sxs-lookup"><span data-stu-id="beaef-112">Heading</span></span>        | <span data-ttu-id="beaef-113">Texto do cabeçalho e tag do cabeçalho ( **H1** , **H2** , **H3** , **H4** , **H5** ou **H6** )</span><span class="sxs-lookup"><span data-stu-id="beaef-113">Heading text and heading tag ( **H1** , **H2** , **H3** , **H4** , **H5** , or **H6** )</span></span> | <span data-ttu-id="beaef-114">O módulo de detalhes da ordem pode ter um título.</span><span class="sxs-lookup"><span data-stu-id="beaef-114">The order details module can have a heading.</span></span> <span data-ttu-id="beaef-115">Por padrão, a tag de cabeçalho **H2** é usada para o cabeçalho.</span><span class="sxs-lookup"><span data-stu-id="beaef-115">By default, the **H2** heading tag is used for the heading.</span></span> <span data-ttu-id="beaef-116">No entanto, a tag pode ser alterada para atender aos requisitos de acessibilidade.</span><span class="sxs-lookup"><span data-stu-id="beaef-116">However, the tag can be changed to meet accessibility requirements.</span></span> |
| <span data-ttu-id="beaef-117">Número do contato</span><span class="sxs-lookup"><span data-stu-id="beaef-117">Contact number</span></span> | <span data-ttu-id="beaef-118">Text</span><span class="sxs-lookup"><span data-stu-id="beaef-118">Text</span></span> | <span data-ttu-id="beaef-119">Um número de contato pode ser fornecido para perguntas relativas a ordens.</span><span class="sxs-lookup"><span data-stu-id="beaef-119">A contact number can be provided for order-related questions.</span></span> |

## <a name="modules-that-can-be-used-on-an-order-details-page"></a><span data-ttu-id="beaef-120">Os módulos que podem ser usados em uma página de detalhes da ordem</span><span class="sxs-lookup"><span data-stu-id="beaef-120">Modules that can be used on an order details page</span></span>

<span data-ttu-id="beaef-121">Ao criar uma página de detalhes da ordem, você pode adicionar outros módulos relevantes além do módulo de detalhes da ordem.</span><span class="sxs-lookup"><span data-stu-id="beaef-121">When you create an order details page, you can add other relevant modules in addition to the order details module.</span></span> <span data-ttu-id="beaef-122">Eis alguns exemplos:</span><span class="sxs-lookup"><span data-stu-id="beaef-122">Here are some examples:</span></span>

- <span data-ttu-id="beaef-123">**Módulo de recomendações** – O módulo de recomendações pode ser adicionado à página de detalhes da ordem para sugerir outros produtos para o cliente.</span><span class="sxs-lookup"><span data-stu-id="beaef-123">**Recommendations module** – The recommendations module can be added to the order details page to suggest other products to the customer.</span></span>
- <span data-ttu-id="beaef-124">**Módulos de marketing** – qualquer módulo de marketing pode ser adicionado à página de detalhes da ordem para mostrar o conteúdo de marketing.</span><span class="sxs-lookup"><span data-stu-id="beaef-124">**Marketing modules** – Any marketing module can be added to the order details page to show marketing content.</span></span>

## <a name="add-an-order-details-module-to-a-page"></a><span data-ttu-id="beaef-125">Adicionar um módulo de detalhes da ordem a uma página</span><span class="sxs-lookup"><span data-stu-id="beaef-125">Add an order details module to a page</span></span>

<span data-ttu-id="beaef-126">Para adicionar um módulo de detalhes da ordem a uma nova página e definir as propriedades necessárias, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="beaef-126">To add an order details module to a new page and set the required properties, follow these steps.</span></span>

1. <span data-ttu-id="beaef-127">Vá para **Modelos** e selecione **Novo** para criar um novo modelo.</span><span class="sxs-lookup"><span data-stu-id="beaef-127">Go to **Templates** , and select **New** to create a new template.</span></span>
1. <span data-ttu-id="beaef-128">Na caixa de diálogo **Novo Modelo** , em **Nome do modelo** , insira o nome **Modelo de detalhes da ordem** e selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="beaef-128">In the **New Template** dialog box, under **Template name** , enter the name **Order details template** , and then select **OK**.</span></span>
1. <span data-ttu-id="beaef-129">No slot **Corpo** , selecione as reticências ( **...** ) e, depois, **Adicionar Módulo**.</span><span class="sxs-lookup"><span data-stu-id="beaef-129">In the **Body** slot, select the ellipsis ( **...** ), and then select **Add Module**.</span></span>
1. <span data-ttu-id="beaef-130">Na caixa de diálogo **Adicionar Módulo** , selecione o módulo **Página padrão** e, depois, **OK**.</span><span class="sxs-lookup"><span data-stu-id="beaef-130">In the **Add Module** dialog box, select the **Default page** module, and then select **OK**.</span></span>
1. <span data-ttu-id="beaef-131">No slot **Principal** do módulo **Página Padrão** , selecione as reticências ( **...** ) e, em seguida, **Adicionar Módulo**.</span><span class="sxs-lookup"><span data-stu-id="beaef-131">In the **Main** slot of the **Default Page** module, select the ellipsis ( **...** ), and then select **Add Module**.</span></span>
1. <span data-ttu-id="beaef-132">Na caixa de diálogo **Adicionar Módulo** , selecione o módulo **Detalhes da ordem** e, em seguida, **OK**.</span><span class="sxs-lookup"><span data-stu-id="beaef-132">In the **Add Module** dialog box, select the **Order details** module, and then select **OK**.</span></span>
1. <span data-ttu-id="beaef-133">Selecione **Salvar** e, em seguida, **Visualizar** para visualizar o modelo.</span><span class="sxs-lookup"><span data-stu-id="beaef-133">Select **Save** , and then select **Preview** to preview the template.</span></span> <span data-ttu-id="beaef-134">O módulo de detalhes da ordem não será processado porque ele exige o contexto do número de confirmação da ordem.</span><span class="sxs-lookup"><span data-stu-id="beaef-134">The order details module won't be rendered, because it requires the context of the order confirmation number.</span></span>
1. <span data-ttu-id="beaef-135">Selecione **Concluir edição** para fazer check-in do modelo e depois selecione **Publicar** para publicá-lo.</span><span class="sxs-lookup"><span data-stu-id="beaef-135">Select **Finish editing** to check in the template, and then select **Publish** to publish it.</span></span>
1. <span data-ttu-id="beaef-136">Vá para **Páginas** e selecione **Novo** para criar uma nova página.</span><span class="sxs-lookup"><span data-stu-id="beaef-136">Go to **Pages** , and select **New** to create a new page.</span></span>
1. <span data-ttu-id="beaef-137">Na caixa de diálogo **Escolher um modelo** , selecione o **modelo Detalhes da ordem**.</span><span class="sxs-lookup"><span data-stu-id="beaef-137">In the **Choose a template** dialog box, select **Order details template**.</span></span> <span data-ttu-id="beaef-138">Em **Nome da página** , insira **página Detalhes da ordem** e selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="beaef-138">Under **Page name** , enter **Order details page** , and then select **OK**.</span></span>
1. <span data-ttu-id="beaef-139">No slot **Principal** do módulo **Página Padrão** , selecione as reticências ( **...** ) e, em seguida, **Adicionar Módulo**.</span><span class="sxs-lookup"><span data-stu-id="beaef-139">In the **Main** slot of the **Default Page** module, select the ellipsis ( **...** ), and then select **Add Module**.</span></span>
1. <span data-ttu-id="beaef-140">Na caixa de diálogo **Adicionar Módulo** , selecione o módulo **Detalhes da ordem** e, em seguida, **OK**.</span><span class="sxs-lookup"><span data-stu-id="beaef-140">In the **Add Module** dialog box, select the **Order details** module, and then select **OK**.</span></span>
1. <span data-ttu-id="beaef-141">No painel de propriedades do módulo de detalhes da ordem, selecione **Título** ao lado do símbolo de lápis.</span><span class="sxs-lookup"><span data-stu-id="beaef-141">In the properties pane for the order details module, select **Heading** next to the pencil symbol.</span></span>
1. <span data-ttu-id="beaef-142">No campo **Texto do Título** da caixa de diálogo **Título** , insira o texto do título **Detalhes da ordem** e, em seguida, selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="beaef-142">In the **Heading Text** field of the **Heading** dialog box, enter the heading text **Order details** , and then select **OK**.</span></span>
1. <span data-ttu-id="beaef-143">Selecione **Salvar** e depois selecione **Visualizar** para visualizar a página.</span><span class="sxs-lookup"><span data-stu-id="beaef-143">Select **Save** , and then select **Preview** to preview the page.</span></span>
1. <span data-ttu-id="beaef-144">Selecione **Concluir edição** para fazer check-in da página e depois selecione **Publicar** para publicá-lo.</span><span class="sxs-lookup"><span data-stu-id="beaef-144">Select **Finish editing** to check in the page, and then select **Publish** to publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="beaef-145">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="beaef-145">Additional resources</span></span>

[<span data-ttu-id="beaef-146">Módulo de carrinho</span><span class="sxs-lookup"><span data-stu-id="beaef-146">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="beaef-147">Módulo de ícone de carrinho</span><span class="sxs-lookup"><span data-stu-id="beaef-147">Cart icon module</span></span>](cart-icon-module.md)

[<span data-ttu-id="beaef-148">Módulo de finalização da compra</span><span class="sxs-lookup"><span data-stu-id="beaef-148">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="beaef-149">Módulo de pagamento</span><span class="sxs-lookup"><span data-stu-id="beaef-149">Payment module</span></span>](payment-module.md)

[<span data-ttu-id="beaef-150">Módulo do endereço de remessa</span><span class="sxs-lookup"><span data-stu-id="beaef-150">Shipping address module</span></span>](ship-address-module.md)

[<span data-ttu-id="beaef-151">Módulo de opções de entrega</span><span class="sxs-lookup"><span data-stu-id="beaef-151">Delivery options module</span></span>](delivery-options-module.md)

[<span data-ttu-id="beaef-152">Módulo de vale-presente</span><span class="sxs-lookup"><span data-stu-id="beaef-152">Gift card module</span></span>](add-giftcard.md)
