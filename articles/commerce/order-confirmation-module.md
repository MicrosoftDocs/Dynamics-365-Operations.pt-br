---
title: Módulo de confirmação da ordem
description: Este tópico abrange os módulos de confirmação da ordem e descreve como usá-los no Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 11/06/2020
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
ms.openlocfilehash: bf33ebf9c0c5136f40fcd7e1012988d186c4169b
ms.sourcegitcommit: 12d271bb26c7490e7525d9b4bbf125cdc39fef43
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/07/2020
ms.locfileid: "4410352"
---
# <a name="order-confirmation-module"></a><span data-ttu-id="c907e-103">Módulo de confirmação da ordem</span><span class="sxs-lookup"><span data-stu-id="c907e-103">Order confirmation module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="c907e-104">Este tópico abrange os módulos de confirmação da ordem e descreve como usá-los no Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="c907e-104">This topic covers order confirmation modules and describes how to use them in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="c907e-105">Visão Geral</span><span class="sxs-lookup"><span data-stu-id="c907e-105">Overview</span></span>

<span data-ttu-id="c907e-106">O módulo de confirmação da ordem é usado para mostrar detalhes da confirmação da ordem após ela ser realizada.</span><span class="sxs-lookup"><span data-stu-id="c907e-106">The order confirmation module is used to show order confirmation details after an order has been placed.</span></span> <span data-ttu-id="c907e-107">Ele mostra a ID de confirmação, as informações de contato e outros detalhes da ordem, como os itens que foram comprados, as informações de pagamento, as opções de retirada e o método de remessa.</span><span class="sxs-lookup"><span data-stu-id="c907e-107">It shows the order confirmation ID, order contact information, and other order details, such as the items that were purchased, payment information, pickup options, and the shipping method.</span></span>

## <a name="order-confirmation-module-properties"></a><span data-ttu-id="c907e-108">Propriedades do módulo de confirmação da ordem</span><span class="sxs-lookup"><span data-stu-id="c907e-108">Order confirmation module properties</span></span>

| <span data-ttu-id="c907e-109">Nome da propriedade</span><span class="sxs-lookup"><span data-stu-id="c907e-109">Property name</span></span>  | <span data-ttu-id="c907e-110">Valores</span><span class="sxs-lookup"><span data-stu-id="c907e-110">Values</span></span> | <span data-ttu-id="c907e-111">Descrição</span><span class="sxs-lookup"><span data-stu-id="c907e-111">Description</span></span> |
|----------------|--------|-------------|
| <span data-ttu-id="c907e-112">Cabeçalho</span><span class="sxs-lookup"><span data-stu-id="c907e-112">Heading</span></span>        | <span data-ttu-id="c907e-113">Texto do cabeçalho e tag do cabeçalho (**H1**, **H2**, **H3**, **H4**, **H5** ou **H6**)</span><span class="sxs-lookup"><span data-stu-id="c907e-113">Heading text and heading tag (**H1**, **H2**, **H3**, **H4**, **H5**, or **H6**)</span></span> | <span data-ttu-id="c907e-114">O módulo de confirmação da ordem pode ter um título.</span><span class="sxs-lookup"><span data-stu-id="c907e-114">The order confirmation module can have a heading.</span></span> <span data-ttu-id="c907e-115">Por padrão, a tag de cabeçalho **H2** é usada para o cabeçalho.</span><span class="sxs-lookup"><span data-stu-id="c907e-115">By default, the **H2** heading tag is used for the heading.</span></span> <span data-ttu-id="c907e-116">No entanto, a tag pode ser alterada para atender aos requisitos de acessibilidade.</span><span class="sxs-lookup"><span data-stu-id="c907e-116">However, the tag can be changed to meet accessibility requirements.</span></span> |
| <span data-ttu-id="c907e-117">Número do contato</span><span class="sxs-lookup"><span data-stu-id="c907e-117">Contact number</span></span> | <span data-ttu-id="c907e-118">Text</span><span class="sxs-lookup"><span data-stu-id="c907e-118">Text</span></span> | <span data-ttu-id="c907e-119">Um número de contato pode ser fornecido para perguntas relativas a ordens.</span><span class="sxs-lookup"><span data-stu-id="c907e-119">A contact number can be provided for order-related questions.</span></span> |
| <span data-ttu-id="c907e-120">Mostrar informações do intervalo de tempo de retirada</span><span class="sxs-lookup"><span data-stu-id="c907e-120">Show pickup timeslot information</span></span> | <span data-ttu-id="c907e-121">Verdadeiro ou Falso</span><span class="sxs-lookup"><span data-stu-id="c907e-121">True or False</span></span> | <span data-ttu-id="c907e-122">Esta propriedade está disponível no Dynamics 365 Commerce 10.0.15 e superiores.</span><span class="sxs-lookup"><span data-stu-id="c907e-122">This property is available in Dynamics 365 Commerce 10.0.15 and higher.</span></span> <span data-ttu-id="c907e-123">Quando verdadeira, ela exibe as informações do intervalo de tempo de retirada, se forem fornecidas, de um item de retirada</span><span class="sxs-lookup"><span data-stu-id="c907e-123">When true, it displays the pickup timeslot information if provided for a pickup item</span></span>|

## <a name="modules-that-can-be-used-on-an-order-confirmation-page"></a><span data-ttu-id="c907e-124">Módulos que podem ser usados em uma página de confirmação da ordem</span><span class="sxs-lookup"><span data-stu-id="c907e-124">Modules that can be used on an order confirmation page</span></span>

<span data-ttu-id="c907e-125">Ao criar uma página de confirmação da ordem, você pode adicionar outros módulos relevantes além do módulo de confirmação da ordem.</span><span class="sxs-lookup"><span data-stu-id="c907e-125">When you create an order confirmation page, you can add other relevant modules in addition to the order confirmation module.</span></span> <span data-ttu-id="c907e-126">Eis alguns exemplos:</span><span class="sxs-lookup"><span data-stu-id="c907e-126">Here are some examples:</span></span>

- <span data-ttu-id="c907e-127">**Módulo de recomendações** – O módulo de recomendações pode ser adicionado à página de confirmação da ordem para sugerir outros produtos para o cliente.</span><span class="sxs-lookup"><span data-stu-id="c907e-127">**Recommendations module** – The recommendations module can be added to the order confirmation page to suggest other products to the customer.</span></span>
- <span data-ttu-id="c907e-128">**Módulos de marketing** – Qualquer módulo de marketing pode ser adicionado à página de confirmação da ordem para mostrar conteúdo de marketing.</span><span class="sxs-lookup"><span data-stu-id="c907e-128">**Marketing modules** – Any marketing module can be added to the order confirmation page to show marketing content.</span></span>

## <a name="add-an-order-confirmation-module-to-a-page"></a><span data-ttu-id="c907e-129">Adicionar um módulo de confirmação da ordem a uma página</span><span class="sxs-lookup"><span data-stu-id="c907e-129">Add an order confirmation module to a page</span></span>

<span data-ttu-id="c907e-130">Para adicionar um módulo de confirmação da ordem a uma nova página e definir as propriedades necessárias, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="c907e-130">To add an order confirmation module to a new page and set the required properties, follow these steps.</span></span>

1. <span data-ttu-id="c907e-131">Vá para **Modelos** e selecione **Novo** para criar um novo modelo.</span><span class="sxs-lookup"><span data-stu-id="c907e-131">Go to **Templates**, and select **New** to create a new template.</span></span>
1. <span data-ttu-id="c907e-132">Na caixa de diálogo **Novo Modelo**, em **Nome do modelo**, insira o nome **Modelo de confirmação da ordem** e selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="c907e-132">In the **New Template** dialog box, under **Template name**, enter the name **Order confirmation template**, and then select **OK**.</span></span>
1. <span data-ttu-id="c907e-133">No slot **Corpo**, selecione as reticências (**...**) e, depois, **Adicionar Módulo**.</span><span class="sxs-lookup"><span data-stu-id="c907e-133">In the **Body** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="c907e-134">Na caixa de diálogo **Adicionar Módulo**, selecione o módulo **Página padrão** e, depois, **OK**.</span><span class="sxs-lookup"><span data-stu-id="c907e-134">In the **Add Module** dialog box, select the **Default page** module, and then select **OK**.</span></span>
1. <span data-ttu-id="c907e-135">No slot **Principal** do módulo **Página Padrão**, selecione as reticências (**...**) e, em seguida, **Adicionar Módulo**.</span><span class="sxs-lookup"><span data-stu-id="c907e-135">In the **Main** slot of the **Default Page** module, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="c907e-136">Na caixa de diálogo **Adicionar Módulo**, selecione o módulo **Confirmação da ordem** e, em seguida, **OK**.</span><span class="sxs-lookup"><span data-stu-id="c907e-136">In the **Add Module** dialog box, select the **Order confirmation** module, and then select **OK**.</span></span>
1. <span data-ttu-id="c907e-137">Selecione **Salvar** e, em seguida, **Visualizar** para visualizar o modelo.</span><span class="sxs-lookup"><span data-stu-id="c907e-137">Select **Save**, and then select **Preview** to preview the template.</span></span> <span data-ttu-id="c907e-138">O módulo de confirmação da ordem não será renderizado porque exige o contexto do número de confirmação da ordem.</span><span class="sxs-lookup"><span data-stu-id="c907e-138">The order confirmation module won't be rendered, because it requires the context of the order confirmation number.</span></span>
1. <span data-ttu-id="c907e-139">Selecione **Concluir edição** para fazer check-in do modelo e depois selecione **Publicar** para publicá-lo.</span><span class="sxs-lookup"><span data-stu-id="c907e-139">Select **Finish editing** to check in the template, and then select **Publish** to publish it.</span></span>
1. <span data-ttu-id="c907e-140">Vá para **Páginas** e selecione **Novo** para criar uma nova página.</span><span class="sxs-lookup"><span data-stu-id="c907e-140">Go to **Pages**, and select **New** to create a new page.</span></span>
1. <span data-ttu-id="c907e-141">Na caixa de diálogo **Escolher um modelo**, selecione **Modelo de confirmação da ordem**.</span><span class="sxs-lookup"><span data-stu-id="c907e-141">In the **Choose a template** dialog box, select **Order confirmation template**.</span></span> <span data-ttu-id="c907e-142">Em **Nome da página**, insira **Página de confirmação da ordem** e selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="c907e-142">Under **Page name**, enter **Order confirmation page**, and then select **OK**.</span></span>
1. <span data-ttu-id="c907e-143">No slot **Principal** do módulo **Página Padrão**, selecione as reticências (**...**) e, em seguida, **Adicionar Módulo**.</span><span class="sxs-lookup"><span data-stu-id="c907e-143">In the **Main** slot of the **Default Page** module, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="c907e-144">Na caixa de diálogo **Adicionar Módulo**, selecione o módulo **Confirmação da ordem** e, em seguida, **OK**.</span><span class="sxs-lookup"><span data-stu-id="c907e-144">In the **Add Module** dialog box, select the **Order confirmation** module, and then select **OK**.</span></span>
1. <span data-ttu-id="c907e-145">No painel de propriedades do módulo de confirmação da ordem, selecione **Título** ao lado do símbolo de lápis.</span><span class="sxs-lookup"><span data-stu-id="c907e-145">In the properties pane for the order confirmation module, select **Heading** next to the pencil symbol.</span></span>
1. <span data-ttu-id="c907e-146">No campo **Texto do Título** da caixa de diálogo **Título**, insira o texto do título **Confirmação da ordem** e, em seguida, selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="c907e-146">In the **Heading Text** field of the **Heading** dialog box, enter the heading text **Order confirmation**, and then select **OK**.</span></span>
1. <span data-ttu-id="c907e-147">Selecione **Salvar** e depois selecione **Visualizar** para visualizar a página.</span><span class="sxs-lookup"><span data-stu-id="c907e-147">Select **Save**, and then select **Preview** to preview the page.</span></span>
1. <span data-ttu-id="c907e-148">Selecione **Concluir edição** para fazer check-in da página e depois selecione **Publicar** para publicá-lo.</span><span class="sxs-lookup"><span data-stu-id="c907e-148">Select **Finish editing** to check in the page, and then select **Publish** to publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="c907e-149">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="c907e-149">Additional resources</span></span>

[<span data-ttu-id="c907e-150">Módulo de carrinho</span><span class="sxs-lookup"><span data-stu-id="c907e-150">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="c907e-151">Módulo de ícone de carrinho</span><span class="sxs-lookup"><span data-stu-id="c907e-151">Cart icon module</span></span>](cart-icon-module.md)

[<span data-ttu-id="c907e-152">Módulo de finalização da compra</span><span class="sxs-lookup"><span data-stu-id="c907e-152">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="c907e-153">Módulo de pagamento</span><span class="sxs-lookup"><span data-stu-id="c907e-153">Payment module</span></span>](payment-module.md)

[<span data-ttu-id="c907e-154">Módulo de endereço de remessa</span><span class="sxs-lookup"><span data-stu-id="c907e-154">Shipping address module</span></span>](ship-address-module.md)

[<span data-ttu-id="c907e-155">Módulo de opções de entrega</span><span class="sxs-lookup"><span data-stu-id="c907e-155">Delivery options module</span></span>](delivery-options-module.md)

[<span data-ttu-id="c907e-156">Módulo de informações sobre retirada</span><span class="sxs-lookup"><span data-stu-id="c907e-156">Pickup information module</span></span>](pickup-info-module.md)

[<span data-ttu-id="c907e-157">Módulo de cartão-presente</span><span class="sxs-lookup"><span data-stu-id="c907e-157">Gift card module</span></span>](add-giftcard.md)
