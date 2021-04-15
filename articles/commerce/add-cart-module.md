---
title: Módulo de carrinho
description: Este tópico abrange os módulos de carrinho e descreve como adicioná-los às páginas de site no Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 12/15/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 1ec8e89ed82bcdffdc21e62d24ad8c8a7d939cdf
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5797854"
---
# <a name="cart-module"></a><span data-ttu-id="349f9-103">Módulo de carrinho</span><span class="sxs-lookup"><span data-stu-id="349f9-103">Cart module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="349f9-104">Este tópico abrange os módulos de carrinho e descreve como adicioná-los às páginas de site no Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="349f9-104">This topic covers cart modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="349f9-105">Um módulo de carrinho mostra os itens que foram adicionados ao carrinho antes de o cliente prosseguir para finalizar a compra.</span><span class="sxs-lookup"><span data-stu-id="349f9-105">A cart module shows the items that have been added to the cart before the customer proceeds to checkout.</span></span> <span data-ttu-id="349f9-106">O módulo também mostra um resumo da ordem e permite que o cliente aplique ou remova códigos promocionais.</span><span class="sxs-lookup"><span data-stu-id="349f9-106">The module also shows an order summary and lets the customer apply or remove promotional codes.</span></span>

<span data-ttu-id="349f9-107">O módulo do carrinho oferece suporte a finalização de compra em conexão e a finalização de compra de convidado.</span><span class="sxs-lookup"><span data-stu-id="349f9-107">The cart module supports signed-in checkout and guest checkout.</span></span> <span data-ttu-id="349f9-108">Ele também oferece suporte ao link **Voltar para compra**.</span><span class="sxs-lookup"><span data-stu-id="349f9-108">It also supports a **Back to shopping** link.</span></span> <span data-ttu-id="349f9-109">Você pode configurar o roteiro desse link em **Configurações de Site \> Extensões \> Roteiros**.</span><span class="sxs-lookup"><span data-stu-id="349f9-109">You can configure the route for this link at **Site Settings \> Extensions \> Routes**.</span></span>

<span data-ttu-id="349f9-110">O módulo do carrinho processa os dados com base na ID do carrinho, que é um cookie do navegador disponível em todo o site.</span><span class="sxs-lookup"><span data-stu-id="349f9-110">The cart module renders data based on the cart ID, which is a browser cookie available throughout the site.</span></span> 

<span data-ttu-id="349f9-111">A imagem a seguir mostra um exemplo de uma página de carrinho no site da Fabrikam.</span><span class="sxs-lookup"><span data-stu-id="349f9-111">The following image shows an example of a cart page on the Fabrikam site.</span></span>

![Exemplo de um módulo de carrinho no site da Fabrikam](./media/cart2.PNG)

<span data-ttu-id="349f9-113">A imagem a seguir mostra um exemplo de uma página de carrinho no site da Fabrikam.</span><span class="sxs-lookup"><span data-stu-id="349f9-113">The following image shows an example of a cart page on the Fabrikam site.</span></span> <span data-ttu-id="349f9-114">Neste exemplo, há uma taxa de manuseio para um item de linha.</span><span class="sxs-lookup"><span data-stu-id="349f9-114">In this example, there is a handling fee for a line item.</span></span>

![Exemplo de um módulo de carrinho com uma taxa de manuseio para um item de linha](./media/ecommerce-handling-fee.png)

## <a name="cart-module-properties-and-slots"></a><span data-ttu-id="349f9-116">Propriedades e slots do módulo de carrinho</span><span class="sxs-lookup"><span data-stu-id="349f9-116">Cart module properties and slots</span></span>

| <span data-ttu-id="349f9-117">Propriedade</span><span class="sxs-lookup"><span data-stu-id="349f9-117">Property</span></span> | <span data-ttu-id="349f9-118">Valores</span><span class="sxs-lookup"><span data-stu-id="349f9-118">Values</span></span> | <span data-ttu-id="349f9-119">descrição</span><span class="sxs-lookup"><span data-stu-id="349f9-119">Description</span></span> |
|----------------|--------|-------------|
| <span data-ttu-id="349f9-120">Cabeçalho</span><span class="sxs-lookup"><span data-stu-id="349f9-120">Heading</span></span> | <span data-ttu-id="349f9-121">Texto do cabeçalho e uma tag do cabeçalho (**H1**, **H2**, **H3**, **H4**, **H5** ou **H6**)</span><span class="sxs-lookup"><span data-stu-id="349f9-121">Heading text and a heading tag (**H1**, **H2**, **H3**, **H4**, **H5**, or **H6**)</span></span> | <span data-ttu-id="349f9-122">Um título para o carrinho, como "Sacola de compras" ou "Itens em seu carrinho".</span><span class="sxs-lookup"><span data-stu-id="349f9-122">A heading for the cart, such as "Shopping bag" or "Items in your cart."</span></span> |
| <span data-ttu-id="349f9-123">Mostrar erros de estoque insuficiente</span><span class="sxs-lookup"><span data-stu-id="349f9-123">Show out of stock errors</span></span> | <span data-ttu-id="349f9-124">**Verdadeiro** ou **Falso**</span><span class="sxs-lookup"><span data-stu-id="349f9-124">**True** or **False**</span></span> | <span data-ttu-id="349f9-125">Se esta propriedade for definida como **True**, a página do carrinho mostrará erros relacionados ao estoque.</span><span class="sxs-lookup"><span data-stu-id="349f9-125">If this property is set to **True**, the cart page will show stock-related errors.</span></span> <span data-ttu-id="349f9-126">Recomendamos definir esta propriedade como **True** se as verificações de estoque forem aplicadas no site.</span><span class="sxs-lookup"><span data-stu-id="349f9-126">We recommend that you set this property to **True** if inventory checks are applied on the site.</span></span> |
| <span data-ttu-id="349f9-127">Mostrar encargos de remessa para itens de linha</span><span class="sxs-lookup"><span data-stu-id="349f9-127">Show shipping charges for line items</span></span> | <span data-ttu-id="349f9-128">**Verdadeiro** ou **Falso**</span><span class="sxs-lookup"><span data-stu-id="349f9-128">**True** or **False**</span></span> | <span data-ttu-id="349f9-129">Se esta propriedade for definida como **True**, os itens de linha do carrinho mostrarão os encargos de remessa, se essas informações estiverem disponíveis.</span><span class="sxs-lookup"><span data-stu-id="349f9-129">If this property is set to **True**, cart line items will show the shipping charges, if this information is available.</span></span> <span data-ttu-id="349f9-130">Este recurso não é compatível com o tema Fabrikam, pois os usuários selecionam a remessa somente no fluxo de finalização da compra.</span><span class="sxs-lookup"><span data-stu-id="349f9-130">This feature isn't supported in the Fabrikam theme, because users select shipping only in the checkout flow.</span></span> <span data-ttu-id="349f9-131">No entanto, esse recurso pode ser ativado em outros fluxos de trabalho, se aplicável.</span><span class="sxs-lookup"><span data-stu-id="349f9-131">However, this feature can be turned on in other workflows if it's applicable.</span></span> |
| <span data-ttu-id="349f9-132">Mostrar promoções disponíveis</span><span class="sxs-lookup"><span data-stu-id="349f9-132">Show available promotions</span></span>| <span data-ttu-id="349f9-133">**Verdadeiro** ou **Falso**</span><span class="sxs-lookup"><span data-stu-id="349f9-133">**True** or **False**</span></span> | <span data-ttu-id="349f9-134">Se esta propriedade for definida como **Verdadeiro**, o carrinho mostrará promoções disponíveis com base em itens do carrinho.</span><span class="sxs-lookup"><span data-stu-id="349f9-134">If this property is set to **True**, the cart shows available promotions, based on items in the cart.</span></span> <span data-ttu-id="349f9-135">Esse recurso está disponível na versão 10.0.16 do Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="349f9-135">This capability is available in the Dynamics 365 Commerce 10.0.16 release.</span></span> |

## <a name="modules-that-can-be-used-in-a-cart-module"></a><span data-ttu-id="349f9-136">Módulos que podem ser usados em um módulo de carrinho</span><span class="sxs-lookup"><span data-stu-id="349f9-136">Modules that can be used in a cart module</span></span>

- <span data-ttu-id="349f9-137">**Bloco de texto** – Este módulo fornece suporte a mensagens personalizadas no módulo de carrinho.</span><span class="sxs-lookup"><span data-stu-id="349f9-137">**Text block** – This module supports custom messaging in the cart module.</span></span> <span data-ttu-id="349f9-138">As mensagens são direcionadas pelo sistema de gerenciamento de conteúdo (CMS).</span><span class="sxs-lookup"><span data-stu-id="349f9-138">The messages are driven by the content management system (CMS).</span></span> <span data-ttu-id="349f9-139">Qualquer mensagem pode ser adicionada, como "Caso você tenha problemas com o pedido, entre em contato com 1-800-Fabrikam".</span><span class="sxs-lookup"><span data-stu-id="349f9-139">Any message can be added, such as "For issues with your order, contact 1-800-Fabrikam."</span></span>
- <span data-ttu-id="349f9-140">**Seletor de loja** – Este módulo mostra uma lista de lojas próximas, onde um item está disponível para retirada.</span><span class="sxs-lookup"><span data-stu-id="349f9-140">**Store selector** – This module shows a list of nearby stores where an item is available for pickup.</span></span> <span data-ttu-id="349f9-141">Ele permite que os usuários insiram um local para encontrar lojas próximas.</span><span class="sxs-lookup"><span data-stu-id="349f9-141">It lets users enter a location to find stores that are nearby.</span></span> <span data-ttu-id="349f9-142">Para obter mais informações sobre este módulo, consulte [Módulo do seletor de armazenamento](store-selector.md).</span><span class="sxs-lookup"><span data-stu-id="349f9-142">For more information on this module, see [Store selector module](store-selector.md).</span></span>

## <a name="module-properties"></a><span data-ttu-id="349f9-143">Propriedades do módulo</span><span class="sxs-lookup"><span data-stu-id="349f9-143">Module properties</span></span>

<span data-ttu-id="349f9-144">As seguintes configurações de módulo de carrinho podem ser definidas em **Configurações de Site \> Extensões**:</span><span class="sxs-lookup"><span data-stu-id="349f9-144">The following cart module settings can be configured at **Site Settings \> Extensions**:</span></span>

- <span data-ttu-id="349f9-145">**Quantidade máxima** – Esta propriedade é usada para especificar o número máximo de cada item que pode ser adicionado ao carrinho.</span><span class="sxs-lookup"><span data-stu-id="349f9-145">**Maximum quantity** – This property is used to specify the maximum number of each item that can be added to the cart.</span></span> <span data-ttu-id="349f9-146">Por exemplo, um varejista pode decidir que apenas 10 de cada produto podem ser vendidos em uma única transação.</span><span class="sxs-lookup"><span data-stu-id="349f9-146">For example, a retailer might decide that only 10 of each product can be sold in a single transaction.</span></span>
- <span data-ttu-id="349f9-147">**Estoque** – para obter informações sobre como aplicar configurações de estoque, consulte [Aplicar configurações de estoque](inventory-settings.md).</span><span class="sxs-lookup"><span data-stu-id="349f9-147">**Inventory** – For information about how to apply inventory settings, see [Apply inventory settings](inventory-settings.md).</span></span>
- <span data-ttu-id="349f9-148">**Voltar para compra** – Esta propriedade é usada para especificar o roteiro do link **Voltar para compra**.</span><span class="sxs-lookup"><span data-stu-id="349f9-148">**Back to shopping** – This property is used to specify the route for the **Back to shopping** link.</span></span> <span data-ttu-id="349f9-149">O roteiro pode ser configurado no nível do site, permitindo que os varejistas retornem o cliente para a Home Page ou qualquer outra página no site.</span><span class="sxs-lookup"><span data-stu-id="349f9-149">The route can be configured at the site level, allowing retailers to take the customer back to the home page or any other page on the site.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="349f9-150">No Dynamics 365 Commerce versão 10.0.14 e posterior, os itens no carrinho são agregados com base nas configurações definidas no perfil de funcionalidade online da loja online na sede do Commerce.</span><span class="sxs-lookup"><span data-stu-id="349f9-150">In the Dynamics 365 Commerce 10.0.14 release and later, items in the cart are aggregated based on the settings that are defined in the online functionality profile for the online store in Commerce headquarters.</span></span> <span data-ttu-id="349f9-151">Para obter mais informações sobre como criar um perfil de funcionalidade online e definir as propriedades necessárias para agregação, consulte [Criar um perfil de funcionalidade online](online-functionality-profile.md).</span><span class="sxs-lookup"><span data-stu-id="349f9-151">For more information about how to create an online functionality profile and set the properties that are required for aggregation, see [Create an online functionality profile](online-functionality-profile.md).</span></span>

## <a name="commerce-scale-unit-interaction"></a><span data-ttu-id="349f9-152">Interação do Commerce Scale Unit</span><span class="sxs-lookup"><span data-stu-id="349f9-152">Commerce Scale Unit interaction</span></span>

<span data-ttu-id="349f9-153">O módulo de carrinho recupera informações do produto usando as APIs de Commerce Scale Unit.</span><span class="sxs-lookup"><span data-stu-id="349f9-153">The cart module retrieves product information by using Commerce Scale Unit APIs.</span></span> <span data-ttu-id="349f9-154">A ID de carrinho do cookie do navegador é usada para recuperar todas as informações do produto direto do Commerce Scale Unit.</span><span class="sxs-lookup"><span data-stu-id="349f9-154">The cart ID from the browser cookie is used to retrieve all the product information from Commerce Scale Unit.</span></span>

## <a name="add-a-cart-module-to-a-page"></a><span data-ttu-id="349f9-155">Adicionar um módulo de carrinho a uma página</span><span class="sxs-lookup"><span data-stu-id="349f9-155">Add a cart module to a page</span></span>

<span data-ttu-id="349f9-156">Para adicionar um módulo de carrinho a uma nova página e definir as propriedades necessárias, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="349f9-156">To add a cart module to a new page and set the required properties, follow these steps.</span></span>

1. <span data-ttu-id="349f9-157">Vá para **Fragmentos** e selecione **Novo** para criar um novo fragmento.</span><span class="sxs-lookup"><span data-stu-id="349f9-157">Go to **Fragments**, and select **New** to create a new fragment.</span></span>
1. <span data-ttu-id="349f9-158">Na caixa de diálogo **Novo fragmento**, selecione o módulo **Carrinho**.</span><span class="sxs-lookup"><span data-stu-id="349f9-158">In the **New fragment** dialog box, select the **Cart** module.</span></span>
1. <span data-ttu-id="349f9-159">Em **Nome do fragmento**, digite o nome **Fragmento de carrinho** e selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="349f9-159">Under **Fragment name**, enter the name **Cart fragment**, and then select **OK**.</span></span>
1. <span data-ttu-id="349f9-160">Selecione o slot **Carrinho**.</span><span class="sxs-lookup"><span data-stu-id="349f9-160">Select the **Cart** slot.</span></span>
1. <span data-ttu-id="349f9-161">No painel de propriedades à direita, selecione o símbolo de lápis, digite o texto do título no campo e, em seguida, selecione o símbolo de marca de seleção.</span><span class="sxs-lookup"><span data-stu-id="349f9-161">In the properties pane on the right, select the pencil symbol, enter heading text in the field, and then select the check mark symbol.</span></span>
1. <span data-ttu-id="349f9-162">No slot **Carrinho**, selecione as reticências (**...**) e, depois, **Adicionar Módulo**.</span><span class="sxs-lookup"><span data-stu-id="349f9-162">In the **Cart** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="349f9-163">Na caixa de diálogo **Adicionar Módulo**, selecione o módulo **Seletor de loja** e, depois, **OK**.</span><span class="sxs-lookup"><span data-stu-id="349f9-163">In the **Add Module** dialog box, select the **Store selector** module, and then select **OK**.</span></span>
1. <span data-ttu-id="349f9-164">Selecione **Salvar**, **Concluir edição** para fazer check-in do fragmento e depois selecione **Publicar** para publicá-lo.</span><span class="sxs-lookup"><span data-stu-id="349f9-164">Select **Save**, select **Finish editing** to check in the fragment, and then select **Publish** to publish it.</span></span>
1. <span data-ttu-id="349f9-165">Vá para **Modelos** e selecione **Novo** para criar um novo modelo.</span><span class="sxs-lookup"><span data-stu-id="349f9-165">Go to **Templates**, and select **New** to create a new template.</span></span>
1. <span data-ttu-id="349f9-166">Na caixa de diálogo **Novo Modelo**, em **Nome do modelo**, insira um nome para o modelo.</span><span class="sxs-lookup"><span data-stu-id="349f9-166">In the **New Template** dialog box, under **Template name**, enter a name for the template.</span></span>
1. <span data-ttu-id="349f9-167">Na árvore de estrutura de tópicos, selecione o slot **Corpo**, as reticências (**...**) e, em seguida, selecione **Adicionar fragmento**.</span><span class="sxs-lookup"><span data-stu-id="349f9-167">In the outline tree, select the **Body** slot, select the ellipsis (**...**), and then select **Add fragment**.</span></span>
1. <span data-ttu-id="349f9-168">Na caixa de diálogo **Selecionar fragmento**, selecione o fragmento **Fragmento de carrinho** e, em seguida, selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="349f9-168">In the **Select fragment** dialog box, select the **Cart fragment** fragment, and then select **OK**.</span></span>
1. <span data-ttu-id="349f9-169">Selecione **Salvar**, **Concluir edição** para fazer check-in do modelo e depois selecione **Publicar** para publicá-lo.</span><span class="sxs-lookup"><span data-stu-id="349f9-169">Select **Save**, select **Finish editing** to check in the template, and then select **Publish** to publish it.</span></span>
1. <span data-ttu-id="349f9-170">Vá para **Páginas** e selecione **Novo** para criar uma nova página.</span><span class="sxs-lookup"><span data-stu-id="349f9-170">Go to **Pages**, and select **New** to create a new page.</span></span>
1. <span data-ttu-id="349f9-171">Na caixa de diálogo **Escolher um modelo**, selecione o modelo que você criou, insira um nome de página e selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="349f9-171">In the **Choose a template** dialog box, select the template that you created, enter a page name, and then select **OK**.</span></span>
1. <span data-ttu-id="349f9-172">Selecione **Salvar** e depois selecione **Visualizar** para visualizar a página.</span><span class="sxs-lookup"><span data-stu-id="349f9-172">Select **Save**, and then select **Preview** to preview the page.</span></span>
1. <span data-ttu-id="349f9-173">Selecione **Concluir edição** para fazer check-in da página e depois selecione **Publicar** para publicá-lo.</span><span class="sxs-lookup"><span data-stu-id="349f9-173">Select **Finish editing** to check in the page, and then select **Publish** to publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="349f9-174">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="349f9-174">Additional resources</span></span>

[<span data-ttu-id="349f9-175">Módulo de ícone de carrinho</span><span class="sxs-lookup"><span data-stu-id="349f9-175">Cart icon module</span></span>](cart-icon-module.md)

[<span data-ttu-id="349f9-176">Módulo de finalização da compra</span><span class="sxs-lookup"><span data-stu-id="349f9-176">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="349f9-177">Módulo de pagamento</span><span class="sxs-lookup"><span data-stu-id="349f9-177">Payment module</span></span>](payment-module.md)

[<span data-ttu-id="349f9-178">Módulo de endereço de remessa</span><span class="sxs-lookup"><span data-stu-id="349f9-178">Shipping address module</span></span>](ship-address-module.md)

[<span data-ttu-id="349f9-179">Módulo de opções de entrega</span><span class="sxs-lookup"><span data-stu-id="349f9-179">Delivery options module</span></span>](delivery-options-module.md)

[<span data-ttu-id="349f9-180">Módulo de informações sobre retirada</span><span class="sxs-lookup"><span data-stu-id="349f9-180">Pickup information module</span></span>](pickup-info-module.md)

[<span data-ttu-id="349f9-181">Módulo de detalhes da ordem</span><span class="sxs-lookup"><span data-stu-id="349f9-181">Order details module</span></span>](order-confirmation-module.md)

[<span data-ttu-id="349f9-182">Módulo de cartão-presente</span><span class="sxs-lookup"><span data-stu-id="349f9-182">Gift card module</span></span>](add-giftcard.md)

[<span data-ttu-id="349f9-183">Calcular disponibilidade de estoque para canais de varejo</span><span class="sxs-lookup"><span data-stu-id="349f9-183">Calculate inventory availability for retail channels</span></span>](calculated-inventory-retail-channels.md)

[<span data-ttu-id="349f9-184">Criar um perfil de funcionalidade online</span><span class="sxs-lookup"><span data-stu-id="349f9-184">Create an online functionality profile</span></span>](online-functionality-profile.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]