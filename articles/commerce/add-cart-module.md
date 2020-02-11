---
title: Módulo de carrinho
description: Este tópico abrange os módulos de carrinho e descreve como adicioná-los a páginas de site no Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 10/31/2019
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
ms.openlocfilehash: 1c910f08e5999ec586b5cb656d5769e9d4abd069
ms.sourcegitcommit: 295d940a345879b3dfc5991e387b91c7257019ea
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/01/2019
ms.locfileid: "2696752"
---
# <a name="cart-module"></a><span data-ttu-id="8d494-103">Módulo de carrinho</span><span class="sxs-lookup"><span data-stu-id="8d494-103">Cart module</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="8d494-104">Este tópico abrange os módulos de carrinho e descreve como adicioná-los a páginas de site no Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="8d494-104">This topic covers cart modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="8d494-105">Visão geral</span><span class="sxs-lookup"><span data-stu-id="8d494-105">Overview</span></span>

<span data-ttu-id="8d494-106">Um módulo de carrinho é um contêiner usado para hospedar todos os módulos necessários para mostrar itens que estão no carrinho.</span><span class="sxs-lookup"><span data-stu-id="8d494-106">A cart module is container that is used to host all the modules that are required to showcase items that are in the cart.</span></span> <span data-ttu-id="8d494-107">Por exemplo, inclui todos os itens que foram adicionados ao carrinho, o resumo do pedido e os códigos promocionais.</span><span class="sxs-lookup"><span data-stu-id="8d494-107">For example, it includes all the items that have been added to the cart, the order summary, and promotional codes.</span></span>

<span data-ttu-id="8d494-108">O módulo do carrinho processa dados com base na ID do carrinho.</span><span class="sxs-lookup"><span data-stu-id="8d494-108">The cart module renders data based on the cart ID.</span></span> <span data-ttu-id="8d494-109">A ID do carrinho é um cookie do navegador disponível em todo o site.</span><span class="sxs-lookup"><span data-stu-id="8d494-109">The cart ID is a browser cookie that is available throughout the site.</span></span>

## <a name="cart-module-properties-and-slots"></a><span data-ttu-id="8d494-110">Propriedades e slots do módulo de carrinho</span><span class="sxs-lookup"><span data-stu-id="8d494-110">Cart module properties and slots</span></span>

<span data-ttu-id="8d494-111">Como um contêiner, um módulo de carrinho controla algumas propriedades básicas, como o cabeçalho e a largura.</span><span class="sxs-lookup"><span data-stu-id="8d494-111">As a container, a cart module controls some basic properties, such as the heading and the width.</span></span> <span data-ttu-id="8d494-112">O cabeçalho é tipicamente texto como **Bolsa de compras**, **Seu carrinho** ou **Itens em seu carrinho**.</span><span class="sxs-lookup"><span data-stu-id="8d494-112">The heading is typically text such as **Shopping bag**, **Your cart**, or **Items in your cart**.</span></span> <span data-ttu-id="8d494-113">A configuração de largura determina se os módulos dentro do contêiner devem se ajustar a esse contêiner ou se podem preencher a tela.</span><span class="sxs-lookup"><span data-stu-id="8d494-113">The width setting determines whether the modules inside the container must fit within that container, or whether they can fill the screen.</span></span>

<span data-ttu-id="8d494-114">A página do carrinho é dividida em várias regiões: itens de linha do carrinho, resumo da ordem e finalização de compra e a funcionalidade "localização na loja".</span><span class="sxs-lookup"><span data-stu-id="8d494-114">The cart page is divided into multiple regions: cart line items, order summary and checkout, and "find in store" functionality.</span></span> <span data-ttu-id="8d494-115">Cada região é mapeada para um slot no módulo de carrinho e cada slot aceita um conjunto predefinido de módulos.</span><span class="sxs-lookup"><span data-stu-id="8d494-115">Each region is mapped to a slot in the cart module, and every slot accepts a predefined set of modules.</span></span>

## <a name="modules-that-can-be-used-in-a-cart-module"></a><span data-ttu-id="8d494-116">Módulos que podem ser usados em um módulo de carrinho</span><span class="sxs-lookup"><span data-stu-id="8d494-116">Modules that can be used in a cart module</span></span>

- <span data-ttu-id="8d494-117">**Linha do carrinho de compras** – Este módulo mostra um resumo de cada item que foi adicionado ao carrinho.</span><span class="sxs-lookup"><span data-stu-id="8d494-117">**Cart line items** – This module shows a summary of every item that has been added to the cart.</span></span> <span data-ttu-id="8d494-118">As informações incluem o título do produto, dimensões selecionadas, preço, quantidade e descontos.</span><span class="sxs-lookup"><span data-stu-id="8d494-118">The information includes the product title, selected dimensions, price, quantity, and discounts.</span></span> <span data-ttu-id="8d494-119">Este módulo também permite ações como "remover do carrinho" e "adicionar à lista de desejos".</span><span class="sxs-lookup"><span data-stu-id="8d494-119">This module also supports actions such as "remove from cart" and "add to wish list."</span></span> <span data-ttu-id="8d494-120">Para cada item de linha, há uma opção para enviar o item ou retirá-lo na loja.</span><span class="sxs-lookup"><span data-stu-id="8d494-120">For each line item, there is an option to ship the item or pick it up from the store.</span></span> <span data-ttu-id="8d494-121">Esta opção deve ser configurada separadamente no módulo de retirada na loja.</span><span class="sxs-lookup"><span data-stu-id="8d494-121">This option must be configured separately in the pick up in store module.</span></span>
- <span data-ttu-id="8d494-122">**Resumo da ordem** – Este módulo mostra um resumo da ordem.</span><span class="sxs-lookup"><span data-stu-id="8d494-122">**Order summary** – This module shows an order summary.</span></span> <span data-ttu-id="8d494-123">As informações incluem subtotal, remessa, impostos e economia.</span><span class="sxs-lookup"><span data-stu-id="8d494-123">The information includes the subtotal, shipping, taxes, and savings.</span></span> <span data-ttu-id="8d494-124">Um cabeçalho pode ser configurado para esse módulo.</span><span class="sxs-lookup"><span data-stu-id="8d494-124">A heading can be configured for this module.</span></span>
- <span data-ttu-id="8d494-125">**Código promocional** – Este módulo permite ao cliente resgatar códigos promocionais.</span><span class="sxs-lookup"><span data-stu-id="8d494-125">**Promo code** – This module lets the customer redeem promotional codes.</span></span> <span data-ttu-id="8d494-126">Um código promocional pode ser aplicado ou removido.</span><span class="sxs-lookup"><span data-stu-id="8d494-126">A promotional code can be applied or removed.</span></span>
- <span data-ttu-id="8d494-127">**Finalização da compra** – Este módulo inicia a ação de finalização de compra e redireciona o usuário para a página de finalização de compra.</span><span class="sxs-lookup"><span data-stu-id="8d494-127">**Checkout** – This module initiates the checkout action and redirects the user to the checkout page.</span></span> <span data-ttu-id="8d494-128">Três links devem ser configurados para esse módulo:</span><span class="sxs-lookup"><span data-stu-id="8d494-128">Three links must be configured for this module:</span></span>

    - <span data-ttu-id="8d494-129">**Finalização da compra** – Esse link força os clientes a entrar se ainda não estiverem conectados.</span><span class="sxs-lookup"><span data-stu-id="8d494-129">**Checkout** – This link forces customers to sign in if they aren't already signed in.</span></span>
    - <span data-ttu-id="8d494-130">**Finalização de compra do convidado** – Esse link permite que clientes anônimos coloquem ordens.</span><span class="sxs-lookup"><span data-stu-id="8d494-130">**Guest checkout** – This link lets anonymous customers place orders.</span></span> <span data-ttu-id="8d494-131">É mostrado apenas quando os clientes não estão conectados.</span><span class="sxs-lookup"><span data-stu-id="8d494-131">It's shown only when customers aren't signed in.</span></span>
    - <span data-ttu-id="8d494-132">**Voltar para compra** – Este link permite que os clientes acessem a home page ou qualquer outra página, para que possam continuar comprando.</span><span class="sxs-lookup"><span data-stu-id="8d494-132">**Back to shopping** – This link lets customers go to the home page or any other page, so that they can continue to shop.</span></span>

- <span data-ttu-id="8d494-133">**Bloco de conteúdo sofisticado** – Este módulo permite mensagens personalizadas no módulo de carrinho.</span><span class="sxs-lookup"><span data-stu-id="8d494-133">**Content rich block** – This module supports custom messaging in the cart module.</span></span> <span data-ttu-id="8d494-134">As mensagens são direcionadas pelo sistema de gerenciamento de conteúdo (CMS).</span><span class="sxs-lookup"><span data-stu-id="8d494-134">The messages are driven by the content management system (CMS).</span></span> <span data-ttu-id="8d494-135">Qualquer mensagem pode ser adicionada, como "For issues with the order, contact 1-800-Fabrikam" (Caso você tenha problemas com a ordem, entre em contato com 1-800-Fabrikam).</span><span class="sxs-lookup"><span data-stu-id="8d494-135">Any message can be added, such as "For issues with the order, contact 1-800-Fabrikam."</span></span>
- <span data-ttu-id="8d494-136">**Retirar na loja** – Este módulo mostra uma lista de lojas próximas, onde um item está disponível para retirada.</span><span class="sxs-lookup"><span data-stu-id="8d494-136">**Pick up in store** – This module shows a list of nearby stores where an item is available for pickup.</span></span> <span data-ttu-id="8d494-137">Por padrão, esse módulo mostra lojas que estão dentro de um raio de 80 quilômetros da localização do cliente.</span><span class="sxs-lookup"><span data-stu-id="8d494-137">By default, this module shows stores that are within a 50-mile radius of the customer's location.</span></span> <span data-ttu-id="8d494-138">Contudo, o raio de pesquisa pode ser personalizado no módulo.</span><span class="sxs-lookup"><span data-stu-id="8d494-138">However, the search radius can be customized in the module.</span></span> <span data-ttu-id="8d494-139">Para cada loja, é feita uma verificação de estoque, se a funcionalidade de verificação de estoque estiver ativada e uma mensagem apropriada informando o que está no estoque ou esgotado do estoque for exibida.</span><span class="sxs-lookup"><span data-stu-id="8d494-139">For each store, an inventory check is done, if the inventory check functionality is turned on, and an appropriate in-stock or out-of-stock message is shown.</span></span>
- <span data-ttu-id="8d494-140">**Pesquisa na loja pelo Bing Maps** – Este módulo pode ser usado no módulo de retirada na loja.</span><span class="sxs-lookup"><span data-stu-id="8d494-140">**Store search by Bing Maps** – This module can be used inside the pick up in store module.</span></span> <span data-ttu-id="8d494-141">Permite que os clientes pesquisem lojas inserindo um local.</span><span class="sxs-lookup"><span data-stu-id="8d494-141">It lets customers search for stores by entering a location.</span></span> <span data-ttu-id="8d494-142">A interface de programação de aplicativos (API) de geocodificação do Bing Maps é usada para converter o local inserido pelo cliente em latitude e longitude.</span><span class="sxs-lookup"><span data-stu-id="8d494-142">The Bing Maps geocoding application programming interface (API) is used to convert the location that the customer entered to a latitude and a longitude.</span></span> <span data-ttu-id="8d494-143">Se esse módulo não for usado, apenas as lojas próximas à localização atual do cliente serão exibidas e o cliente não poderá procurar um local diferente.</span><span class="sxs-lookup"><span data-stu-id="8d494-143">If this module isn't used, only stores that are near the customer's current location are shown, and the customer can't search for a different location.</span></span>

## <a name="cart-module-settings"></a><span data-ttu-id="8d494-144">Configurações do módulo de carrinho</span><span class="sxs-lookup"><span data-stu-id="8d494-144">Cart module settings</span></span>

<span data-ttu-id="8d494-145">Os módulos de carrinho têm três configurações que podem ser configuradas:</span><span class="sxs-lookup"><span data-stu-id="8d494-145">Cart modules have three settings that can be configured:</span></span>

- <span data-ttu-id="8d494-146">**Quantidade máxima** – O número máximo de cada item que pode ser adicionado ao carrinho.</span><span class="sxs-lookup"><span data-stu-id="8d494-146">**Maximum quantity** – The maximum number of each item that can be added to the cart.</span></span> <span data-ttu-id="8d494-147">Por exemplo, um varejista pode decidir que apenas 10 de cada produto podem ser vendidos em uma única transação.</span><span class="sxs-lookup"><span data-stu-id="8d494-147">For example, a retailer might decide that only 10 of each product can be sold in a single transaction.</span></span>
- <span data-ttu-id="8d494-148">**Verificação de estoque** – Quando o valor é definido como **Verdadeiro**, um item é adicionado ao carrinho somente após o módulo da caixa de compra garantir que ele esteja em estoque.</span><span class="sxs-lookup"><span data-stu-id="8d494-148">**Inventory check** – When the value is set to **True**, an item is added to the cart only after the buy box module makes sure that it's in stock.</span></span> <span data-ttu-id="8d494-149">Essa verificação de estoque é feita tanto para os cenários em que o item será enviado como para os cenários em que ele será retirado na loja.</span><span class="sxs-lookup"><span data-stu-id="8d494-149">This inventory check is done both for scenarios where the item will be shipped and for scenarios where it will be picked up in the store.</span></span> <span data-ttu-id="8d494-150">Se o valor estiver definido como **Falso**, nenhuma verificação de estoque será feita antes que um item seja adicionado ao carrinho e a ordem seja feita.</span><span class="sxs-lookup"><span data-stu-id="8d494-150">If the value is set to **False**, no inventory check is done before an item is added to the cart and the order is placed.</span></span>
- <span data-ttu-id="8d494-151">**Buffer de estoque** – O estoque é mantido em tempo real e, quando muitos clientes colocam ordens, pode ser difícil manter uma contagem precisa do estoque.</span><span class="sxs-lookup"><span data-stu-id="8d494-151">**Inventory buffer** – Inventory is maintained in real time, and when many customers place orders, it can be difficult to maintain an accurate inventory count.</span></span> <span data-ttu-id="8d494-152">Portanto, um buffer pode ser definido para o estoque.</span><span class="sxs-lookup"><span data-stu-id="8d494-152">Therefore, a buffer can be defined for inventory.</span></span> <span data-ttu-id="8d494-153">Quando uma verificação de estoque é feita, se o estoque for menor que a quantidade do buffer, o produto é tratado como esgotado no estoque.</span><span class="sxs-lookup"><span data-stu-id="8d494-153">When an inventory check is done, if the inventory is less than the buffer amount, the product is treated as out of stock.</span></span> <span data-ttu-id="8d494-154">Sendo assim, quando as vendas ocorrem rapidamente por meio de vários canais, para que a contagem do estoque não seja totalmente sincronizada, há menos risco de que um item esgotado no estoque seja vendido.</span><span class="sxs-lookup"><span data-stu-id="8d494-154">Therefore, when sales occur quickly through several channels, so that the inventory count isn't fully synced, there is less risk that an item that is out of stock will be sold.</span></span>

## <a name="retail-server-interaction"></a><span data-ttu-id="8d494-155">Interação do Retail Server</span><span class="sxs-lookup"><span data-stu-id="8d494-155">Retail Server interaction</span></span>

<span data-ttu-id="8d494-156">O módulo de carrinho recupera informações do produto usando as APIs do Retail Server.</span><span class="sxs-lookup"><span data-stu-id="8d494-156">The cart module retrieves product information by using Retail Server APIs.</span></span> <span data-ttu-id="8d494-157">A ID de carrinho do cookie do navegador é usada para recuperar todas as informações do produto do Retail Server.</span><span class="sxs-lookup"><span data-stu-id="8d494-157">The cart ID from the browser cookie is used to retrieve all the product information from Retail Server.</span></span>

## <a name="add-a-cart-module-to-a-page"></a><span data-ttu-id="8d494-158">Adicionar um módulo de carrinho a uma página</span><span class="sxs-lookup"><span data-stu-id="8d494-158">Add a cart module to a page</span></span>

<span data-ttu-id="8d494-159">Para adicionar um módulo de carrinho a uma nova página e definir as propriedades necessárias, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="8d494-159">To add a cart module to a new page and set the required properties, follow these steps.</span></span>

1. <span data-ttu-id="8d494-160">Crie um fragmento denominado **fragmento do carrinho** e adicione um módulo de carrinho a ele.</span><span class="sxs-lookup"><span data-stu-id="8d494-160">Create a fragment that is named **cart fragment**, and add a cart module to it.</span></span>
1. <span data-ttu-id="8d494-161">No slot **Linha do carrinho de compras** do módulo do carrinho, adicione um módulo de itens de linha do carrinho.</span><span class="sxs-lookup"><span data-stu-id="8d494-161">In the **Cart line items** slot of the cart module, add a cart line items module.</span></span>
1. <span data-ttu-id="8d494-162">No slot **Resumo da ordem**, adicione um módulo de resumo da ordem.</span><span class="sxs-lookup"><span data-stu-id="8d494-162">In the **Order summary** slot, add an order summary module.</span></span>
1. <span data-ttu-id="8d494-163">No slot **Código promocional**, adicione um módulo de código promocional.</span><span class="sxs-lookup"><span data-stu-id="8d494-163">In the **Promo code** slot, add a promo code module.</span></span>
1. <span data-ttu-id="8d494-164">No slot **Finalização da compra**, adicione um módulo de finalização da compra.</span><span class="sxs-lookup"><span data-stu-id="8d494-164">In the **Checkout** slot, add a checkout module.</span></span>
1. <span data-ttu-id="8d494-165">No slot **Localizar na loja**, adicione um módulo de retirada na loja.</span><span class="sxs-lookup"><span data-stu-id="8d494-165">In the **Find in Store** slot, add a pick up in store module.</span></span>
1. <span data-ttu-id="8d494-166">No módulo de retirada na loja, selecione o slot **Pesquisa na loja** e adicione um módulo de pesquisa na loja pelo Bing Maps.</span><span class="sxs-lookup"><span data-stu-id="8d494-166">In the pick up in store module, select the **Store search** slot, and add a store search by Bing Maps module.</span></span>
1. <span data-ttu-id="8d494-167">Insira o fragmento e publique-o.</span><span class="sxs-lookup"><span data-stu-id="8d494-167">Check in the fragment, and publish it.</span></span>
1. <span data-ttu-id="8d494-168">Crie um modelo chamado **modelo de carrinho** e adicione o fragmento do carrinho que você acabou de criar.</span><span class="sxs-lookup"><span data-stu-id="8d494-168">Create a template that is named **cart template**, and add the cart fragment that you just created to it.</span></span>
1. <span data-ttu-id="8d494-169">Salve o modelo, insira-o e publique-o.</span><span class="sxs-lookup"><span data-stu-id="8d494-169">Save the template, check it in, and publish it.</span></span>
1. <span data-ttu-id="8d494-170">Crie uma página que use o novo modelo.</span><span class="sxs-lookup"><span data-stu-id="8d494-170">Create a page that uses the new template.</span></span>
1. <span data-ttu-id="8d494-171">Salve e exiba a página.</span><span class="sxs-lookup"><span data-stu-id="8d494-171">Save and preview the page.</span></span>
1. <span data-ttu-id="8d494-172">Insira a página e publique-a.</span><span class="sxs-lookup"><span data-stu-id="8d494-172">Check in the page, and publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="8d494-173">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="8d494-173">Additional resources</span></span>

[<span data-ttu-id="8d494-174">Visão geral do kit de início</span><span class="sxs-lookup"><span data-stu-id="8d494-174">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="8d494-175">Módulo de contêiner</span><span class="sxs-lookup"><span data-stu-id="8d494-175">Container module</span></span>](add-container-module.md)

[<span data-ttu-id="8d494-176">Módulo de caixa de compra</span><span class="sxs-lookup"><span data-stu-id="8d494-176">Buy box module</span></span>](add-buy-box.md)

[<span data-ttu-id="8d494-177">Módulo de finalização da compra</span><span class="sxs-lookup"><span data-stu-id="8d494-177">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="8d494-178">Módulo de confirmação da ordem</span><span class="sxs-lookup"><span data-stu-id="8d494-178">Order confirmation module</span></span>](order-confirmation-module.md)

[<span data-ttu-id="8d494-179">Módulo de cabeçalho</span><span class="sxs-lookup"><span data-stu-id="8d494-179">Header module</span></span>](author-header-module.md)

[<span data-ttu-id="8d494-180">Módulo de rodapé</span><span class="sxs-lookup"><span data-stu-id="8d494-180">Footer module</span></span>](author-footer-module.md)