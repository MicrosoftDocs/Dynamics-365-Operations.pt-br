---
title: Módulo de carrinho
description: Este tópico abrange os módulos de carrinho e descreve como adicioná-los a páginas de site no Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 01/23/2020
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
ms.openlocfilehash: f6dd8fb56f7342eb9c877eda503a92f4a31e5863
ms.sourcegitcommit: 829329220475ed8cff5a5db92a59dd90c22b04fa
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/05/2020
ms.locfileid: "3025427"
---
# <a name="cart-module"></a><span data-ttu-id="ace9b-103">Módulo de carrinho</span><span class="sxs-lookup"><span data-stu-id="ace9b-103">Cart module</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="ace9b-104">Este tópico abrange os módulos de carrinho e descreve como adicioná-los a páginas de site no Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="ace9b-104">This topic covers cart modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="ace9b-105">Visão geral</span><span class="sxs-lookup"><span data-stu-id="ace9b-105">Overview</span></span>

<span data-ttu-id="ace9b-106">Um módulo de carrinho é usado para mostrar os itens que foram adicionados ao carrinho antes de o cliente prosseguir para finalizar a compra.</span><span class="sxs-lookup"><span data-stu-id="ace9b-106">A cart module is used to show the items that have been added to the cart before the customer proceeds to checkout.</span></span> <span data-ttu-id="ace9b-107">Por exemplo, inclui todos os itens que foram adicionados ao carrinho e o resumo do pedido.</span><span class="sxs-lookup"><span data-stu-id="ace9b-107">For example, it includes all the items that have been added to the cart and an order summary.</span></span> <span data-ttu-id="ace9b-108">Ele também permite que o cliente aplique ou remova códigos promocionais.</span><span class="sxs-lookup"><span data-stu-id="ace9b-108">It also lets the customer apply or remove promotional codes.</span></span>

<span data-ttu-id="ace9b-109">O módulo do carrinho oferece suporte a finalização de compra em conexão e a finalização de compra de convidado.</span><span class="sxs-lookup"><span data-stu-id="ace9b-109">The cart module supports signed-in checkout and guest checkout.</span></span> <span data-ttu-id="ace9b-110">Ele também oferece suporte ao link **Voltar para compra**.</span><span class="sxs-lookup"><span data-stu-id="ace9b-110">It also supports a **Back to shopping** link.</span></span> <span data-ttu-id="ace9b-111">Você pode configurar o roteiro desse link em **Configurações de Site \> Extensões \> Roteiros**.</span><span class="sxs-lookup"><span data-stu-id="ace9b-111">You can configure the route for this link at **Site Settings \> Extensions \> Routes**.</span></span>

<span data-ttu-id="ace9b-112">O módulo do carrinho processa dados com base na ID do carrinho.</span><span class="sxs-lookup"><span data-stu-id="ace9b-112">The cart module renders data based on the cart ID.</span></span> <span data-ttu-id="ace9b-113">A ID do carrinho é um cookie do navegador disponível em todo o site.</span><span class="sxs-lookup"><span data-stu-id="ace9b-113">The cart ID is a browser cookie that is available throughout the site.</span></span>

## <a name="cart-module-properties-and-slots"></a><span data-ttu-id="ace9b-114">Propriedades e slots do módulo de carrinho</span><span class="sxs-lookup"><span data-stu-id="ace9b-114">Cart module properties and slots</span></span>

<span data-ttu-id="ace9b-115">O módulo do carrinho tem uma propriedade **Título** que pode ser definida com valores como **Sacola de compras** e **Itens no seu carrinho**.</span><span class="sxs-lookup"><span data-stu-id="ace9b-115">The cart module has a **Heading** property that can be set to values such as **Shopping bag** and **Items in your cart**.</span></span> 

## <a name="modules-that-can-be-used-in-a-cart-module"></a><span data-ttu-id="ace9b-116">Módulos que podem ser usados em um módulo de carrinho</span><span class="sxs-lookup"><span data-stu-id="ace9b-116">Modules that can be used in a cart module</span></span>

- <span data-ttu-id="ace9b-117">**Bloco de texto** – Este módulo fornece suporte a mensagens personalizadas no módulo de carrinho.</span><span class="sxs-lookup"><span data-stu-id="ace9b-117">**Text block** – This module supports custom messaging in the cart module.</span></span> <span data-ttu-id="ace9b-118">As mensagens são direcionadas pelo sistema de gerenciamento de conteúdo (CMS).</span><span class="sxs-lookup"><span data-stu-id="ace9b-118">The messages are driven by the content management system (CMS).</span></span> <span data-ttu-id="ace9b-119">Qualquer mensagem pode ser adicionada, como "Caso você tenha problemas com o pedido, entre em contato com 1-800-Fabrikam".</span><span class="sxs-lookup"><span data-stu-id="ace9b-119">Any message can be added, such as "For issues with your order, contact 1-800-Fabrikam."</span></span>
- <span data-ttu-id="ace9b-120">**Seletor de loja** – Este módulo mostra uma lista de lojas próximas, onde um item está disponível para retirada.</span><span class="sxs-lookup"><span data-stu-id="ace9b-120">**Store selector** – This module shows a list of nearby stores where an item is available for pickup.</span></span> <span data-ttu-id="ace9b-121">Ele permite que os usuários insiram um local para encontrar lojas próximas.</span><span class="sxs-lookup"><span data-stu-id="ace9b-121">It lets users enter a location to find stores that are nearby.</span></span> <span data-ttu-id="ace9b-122">O módulo de seletor de loja é integrado à interface de programação de aplicativos (API) de Geocodificação do Bing Mapas para converter o local em latitude e longitude.</span><span class="sxs-lookup"><span data-stu-id="ace9b-122">The store selector module is integrated with the Bing Maps Geocoding application programming interface (API) to convert the location to a latitude and longitude.</span></span> <span data-ttu-id="ace9b-123">Uma chave de API do Bing Mapas é necessária e deve ser adicionada à página parâmetros compartilhados de Varejo no Dynamics 365 Retail.</span><span class="sxs-lookup"><span data-stu-id="ace9b-123">A Bing Maps API key is required and must be added to the Retail shared parameters page in Dynamics 365 Retail.</span></span> <span data-ttu-id="ace9b-124">Este módulo oferece suporte a duas propriedades **Raio de pesquisa,** e **Link dos Termos de Serviço**.</span><span class="sxs-lookup"><span data-stu-id="ace9b-124">This module supports two properties, **Search radius** and **Terms of service link**.</span></span> <span data-ttu-id="ace9b-125">A propriedade **Raio de pesquisa** define o raio da pesquisa para lojas, em milhas.</span><span class="sxs-lookup"><span data-stu-id="ace9b-125">The **Search radius** property defines the search radius for stores, in miles.</span></span> <span data-ttu-id="ace9b-126">Se nenhum valor for especificado, será usado o raio de pesquisa padrão, 50 milhas.</span><span class="sxs-lookup"><span data-stu-id="ace9b-126">If no value is specified, the default search radius, 50 miles, is used.</span></span> <span data-ttu-id="ace9b-127">Se o Bing Mapas ou qualquer serviço externo for usado, a propriedade **Link dos Termos de Serviço** poderá ser usada para fornecer um link para os termos de serviço.</span><span class="sxs-lookup"><span data-stu-id="ace9b-127">If Bings Maps or any external service is used, the **Terms of service link** property can be used to provide a link to the terms of service.</span></span> <span data-ttu-id="ace9b-128">É necessário um link dos termos de serviço para o serviço Bing Mapas.</span><span class="sxs-lookup"><span data-stu-id="ace9b-128">A terms of service link is required for the Bing Maps service.</span></span> 

## <a name="cart-module-settings"></a><span data-ttu-id="ace9b-129">Configurações do módulo de carrinho</span><span class="sxs-lookup"><span data-stu-id="ace9b-129">Cart module settings</span></span>

<span data-ttu-id="ace9b-130">Os módulos de carrinho têm as seguintes configurações que podem ser definidas em **Configurações de Site \> Extensões**:</span><span class="sxs-lookup"><span data-stu-id="ace9b-130">Cart modules have the following settings that can be configured at **Site Settings \> Extensions**:</span></span>

- <span data-ttu-id="ace9b-131">**Quantidade máxima** – Esta propriedade é usada para especificar o número máximo de cada item que pode ser adicionado ao carrinho.</span><span class="sxs-lookup"><span data-stu-id="ace9b-131">**Maximum quantity** – This property is used to specify the maximum number of each item that can be added to the cart.</span></span> <span data-ttu-id="ace9b-132">Por exemplo, um varejista pode decidir que apenas 10 de cada produto podem ser vendidos em uma única transação.</span><span class="sxs-lookup"><span data-stu-id="ace9b-132">For example, a retailer might decide that only 10 of each product can be sold in a single transaction.</span></span>
- <span data-ttu-id="ace9b-133">**Verificação de estoque** – Quando o valor é definido como **Verdadeiro**, um item é adicionado ao carrinho somente após o módulo da caixa de compra garantir que ele esteja em estoque.</span><span class="sxs-lookup"><span data-stu-id="ace9b-133">**Inventory check** – When the value is set to **True**, an item is added to the cart only after the buy box module makes sure that it's in stock.</span></span> <span data-ttu-id="ace9b-134">Essa verificação de estoque é feita tanto para os cenários em que o item será enviado como para os cenários em que ele será retirado na loja.</span><span class="sxs-lookup"><span data-stu-id="ace9b-134">This inventory check is done both for scenarios where the item will be shipped and for scenarios where it will be picked up in the store.</span></span> <span data-ttu-id="ace9b-135">Se o valor estiver definido como **Falso**, nenhuma verificação de estoque será feita antes que um item seja adicionado ao carrinho e a ordem seja feita.</span><span class="sxs-lookup"><span data-stu-id="ace9b-135">If the value is set to **False**, no inventory check is done before an item is added to the cart and the order is placed.</span></span>
- <span data-ttu-id="ace9b-136">**Buffer de estoque** – Esta propriedade é usada para especificar um número de buffer para o estoque.</span><span class="sxs-lookup"><span data-stu-id="ace9b-136">**Inventory buffer** – This property is used to specify a buffer number for inventory.</span></span> <span data-ttu-id="ace9b-137">O estoque é mantido em tempo real e, quando muitos clientes fazem pedidos, pode ser difícil manter uma contagem precisa do estoque.</span><span class="sxs-lookup"><span data-stu-id="ace9b-137">Inventory is maintained in real time, and when many customers place orders, it can be difficult to maintain an accurate inventory count.</span></span> <span data-ttu-id="ace9b-138">Quando uma verificação de estoque é feita, se o estoque for menor que a quantidade do buffer, o produto é tratado como esgotado no estoque.</span><span class="sxs-lookup"><span data-stu-id="ace9b-138">When an inventory check is done, if the inventory is less than the buffer amount, the product is treated as out of stock.</span></span> <span data-ttu-id="ace9b-139">Sendo assim, quando as vendas ocorrem rapidamente por meio de vários canais, e a contagem do estoque não está totalmente sincronizada, há menos risco de que um item esgotado no estoque seja vendido.</span><span class="sxs-lookup"><span data-stu-id="ace9b-139">Therefore, when sales occur quickly through several channels, and the inventory count isn't fully synced, there is less risk that an item that is out of stock will be sold.</span></span>
- <span data-ttu-id="ace9b-140">**Voltar para compra** – Esta propriedade é usada para especificar o roteiro do link **Voltar para compra**.</span><span class="sxs-lookup"><span data-stu-id="ace9b-140">**Back to shopping** – This property is used to specify the route for the **Back to shopping** link.</span></span> <span data-ttu-id="ace9b-141">Esse roteiro pode ser configurado no nível do site.</span><span class="sxs-lookup"><span data-stu-id="ace9b-141">This route can be configured at the site level.</span></span> <span data-ttu-id="ace9b-142">Essa configuração permite que os varejistas encaminhem os clientes para a home page ou para outra página no site.</span><span class="sxs-lookup"><span data-stu-id="ace9b-142">This configuration lets retailers take the customer back to the home page or any other page on the site.</span></span>

## <a name="commerce-scale-unit-interaction"></a><span data-ttu-id="ace9b-143">Interação do Commerce Scale Unit</span><span class="sxs-lookup"><span data-stu-id="ace9b-143">Commerce Scale Unit interaction</span></span>

<span data-ttu-id="ace9b-144">O módulo de carrinho recupera informações do produto usando as APIs de Commerce Scale Unit.</span><span class="sxs-lookup"><span data-stu-id="ace9b-144">The cart module retrieves product information by using Commerce Scale Unit APIs.</span></span> <span data-ttu-id="ace9b-145">A ID de carrinho do cookie do navegador é usada para recuperar todas as informações do produto direto do Commerce Scale Unit.</span><span class="sxs-lookup"><span data-stu-id="ace9b-145">The cart ID from the browser cookie is used to retrieve all the product information from Commerce Scale Unit.</span></span>

## <a name="add-a-cart-module-to-a-page"></a><span data-ttu-id="ace9b-146">Adicionar um módulo de carrinho a uma página</span><span class="sxs-lookup"><span data-stu-id="ace9b-146">Add a cart module to a page</span></span>

<span data-ttu-id="ace9b-147">Para adicionar um módulo de carrinho a uma nova página e definir as propriedades necessárias, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="ace9b-147">To add a cart module to a new page and set the required properties, follow these steps.</span></span>

1. <span data-ttu-id="ace9b-148">Crie um fragmento chamado **Fragmento do carrinho** e adicione um módulo de carrinho a ele.</span><span class="sxs-lookup"><span data-stu-id="ace9b-148">Create a fragment that is named **Cart fragment**, and add a cart module to it.</span></span>
1. <span data-ttu-id="ace9b-149">Adicione um título ao módulo de carrinho.</span><span class="sxs-lookup"><span data-stu-id="ace9b-149">Add a heading to the cart module.</span></span>
1. <span data-ttu-id="ace9b-150">Adicione um módulo de seletor de loja ao módulo de carrinho.</span><span class="sxs-lookup"><span data-stu-id="ace9b-150">Add a store selector module to the cart module.</span></span>
1. <span data-ttu-id="ace9b-151">Salve o fragmento, termine de editá-lo e publique-o.</span><span class="sxs-lookup"><span data-stu-id="ace9b-151">Save the fragment, finish editing it, and publish it.</span></span>
1. <span data-ttu-id="ace9b-152">Crie um modelo chamado **Modelo de carrinho** e adicione o fragmento do carrinho que você acabou de criar.</span><span class="sxs-lookup"><span data-stu-id="ace9b-152">Create a template that is named **Cart template**, and add the cart fragment that you just created to it.</span></span>
1. <span data-ttu-id="ace9b-153">Salve o modelo, termine de editá-lo e publique-o.</span><span class="sxs-lookup"><span data-stu-id="ace9b-153">Save the template, finish editing it, and publish it.</span></span>
1. <span data-ttu-id="ace9b-154">Crie uma página que use o novo modelo.</span><span class="sxs-lookup"><span data-stu-id="ace9b-154">Create a page that uses the new template.</span></span>
1. <span data-ttu-id="ace9b-155">Salve e exiba a página.</span><span class="sxs-lookup"><span data-stu-id="ace9b-155">Save and preview the page.</span></span>
1. <span data-ttu-id="ace9b-156">Termine de editar a página e publique-a.</span><span class="sxs-lookup"><span data-stu-id="ace9b-156">Finish editing the page, and publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="ace9b-157">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="ace9b-157">Additional resources</span></span>

[<span data-ttu-id="ace9b-158">Visão geral do kit de início</span><span class="sxs-lookup"><span data-stu-id="ace9b-158">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="ace9b-159">Módulo de contêiner</span><span class="sxs-lookup"><span data-stu-id="ace9b-159">Container module</span></span>](add-container-module.md)

[<span data-ttu-id="ace9b-160">Módulo de caixa de compra</span><span class="sxs-lookup"><span data-stu-id="ace9b-160">Buy box module</span></span>](add-buy-box.md)

[<span data-ttu-id="ace9b-161">Módulo de finalização da compra</span><span class="sxs-lookup"><span data-stu-id="ace9b-161">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="ace9b-162">Módulo de confirmação da ordem</span><span class="sxs-lookup"><span data-stu-id="ace9b-162">Order confirmation module</span></span>](order-confirmation-module.md)

[<span data-ttu-id="ace9b-163">Módulo de cabeçalho</span><span class="sxs-lookup"><span data-stu-id="ace9b-163">Header module</span></span>](author-header-module.md)

[<span data-ttu-id="ace9b-164">Módulo de rodapé</span><span class="sxs-lookup"><span data-stu-id="ace9b-164">Footer module</span></span>](author-footer-module.md)
