---
title: Módulo de carrinho
description: Este tópico abrange os módulos de carrinho e descreve como adicioná-los a páginas de site no Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 03/19/2020
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
ms.openlocfilehash: 598b35b1bd365e761d8d4c5ef214935e60b971f4
ms.sourcegitcommit: de5af1912201dd70aa85fdcad0b184c42405802e
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/21/2020
ms.locfileid: "3154008"
---
# <a name="cart-module"></a><span data-ttu-id="d6faa-103">Módulo de carrinho</span><span class="sxs-lookup"><span data-stu-id="d6faa-103">Cart module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="d6faa-104">Este tópico abrange os módulos de carrinho e descreve como adicioná-los a páginas de site no Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="d6faa-104">This topic covers cart modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="d6faa-105">Visão Geral</span><span class="sxs-lookup"><span data-stu-id="d6faa-105">Overview</span></span>

<span data-ttu-id="d6faa-106">Um módulo de carrinho mostra os itens que foram adicionados ao carrinho antes de o cliente prosseguir para finalizar a compra.</span><span class="sxs-lookup"><span data-stu-id="d6faa-106">A cart module shows the items that have been added to the cart before the customer proceeds to checkout.</span></span> <span data-ttu-id="d6faa-107">O módulo também mostra um resumo da ordem e permite que o cliente aplique ou remova códigos promocionais.</span><span class="sxs-lookup"><span data-stu-id="d6faa-107">The module also shows an order summary and lets the customer apply or remove promotional codes.</span></span>

<span data-ttu-id="d6faa-108">O módulo do carrinho oferece suporte a finalização de compra em conexão e a finalização de compra de convidado.</span><span class="sxs-lookup"><span data-stu-id="d6faa-108">The cart module supports signed-in checkout and guest checkout.</span></span> <span data-ttu-id="d6faa-109">Ele também oferece suporte ao link **Voltar para compra**.</span><span class="sxs-lookup"><span data-stu-id="d6faa-109">It also supports a **Back to shopping** link.</span></span> <span data-ttu-id="d6faa-110">Você pode configurar o roteiro desse link em **Configurações de Site \> Extensões \> Roteiros**.</span><span class="sxs-lookup"><span data-stu-id="d6faa-110">You can configure the route for this link at **Site Settings \> Extensions \> Routes**.</span></span>

<span data-ttu-id="d6faa-111">O módulo do carrinho processa os dados com base na ID do carrinho, que é um cookie do navegador disponível em todo o site.</span><span class="sxs-lookup"><span data-stu-id="d6faa-111">The cart module renders data based on the cart ID, which is a browser cookie available throughout the site.</span></span>

## <a name="cart-module-properties-and-slots"></a><span data-ttu-id="d6faa-112">Propriedades e slots do módulo de carrinho</span><span class="sxs-lookup"><span data-stu-id="d6faa-112">Cart module properties and slots</span></span>

<span data-ttu-id="d6faa-113">O módulo do carrinho tem uma propriedade **Título** que pode ser definida com valores como **Sacola de compras** e **Itens no seu carrinho**.</span><span class="sxs-lookup"><span data-stu-id="d6faa-113">The cart module has a **Heading** property that can be set to values such as **Shopping bag** and **Items in your cart**.</span></span> 

## <a name="modules-that-can-be-used-in-a-cart-module"></a><span data-ttu-id="d6faa-114">Módulos que podem ser usados em um módulo de carrinho</span><span class="sxs-lookup"><span data-stu-id="d6faa-114">Modules that can be used in a cart module</span></span>

- <span data-ttu-id="d6faa-115">**Bloco de texto** – Este módulo fornece suporte a mensagens personalizadas no módulo de carrinho.</span><span class="sxs-lookup"><span data-stu-id="d6faa-115">**Text block** – This module supports custom messaging in the cart module.</span></span> <span data-ttu-id="d6faa-116">As mensagens são direcionadas pelo sistema de gerenciamento de conteúdo (CMS).</span><span class="sxs-lookup"><span data-stu-id="d6faa-116">The messages are driven by the content management system (CMS).</span></span> <span data-ttu-id="d6faa-117">Qualquer mensagem pode ser adicionada, como "Caso você tenha problemas com o pedido, entre em contato com 1-800-Fabrikam".</span><span class="sxs-lookup"><span data-stu-id="d6faa-117">Any message can be added, such as "For issues with your order, contact 1-800-Fabrikam."</span></span>
- <span data-ttu-id="d6faa-118">**Seletor de loja** – Este módulo mostra uma lista de lojas próximas, onde um item está disponível para retirada.</span><span class="sxs-lookup"><span data-stu-id="d6faa-118">**Store selector** – This module shows a list of nearby stores where an item is available for pickup.</span></span> <span data-ttu-id="d6faa-119">Ele permite que os usuários insiram um local para encontrar lojas próximas.</span><span class="sxs-lookup"><span data-stu-id="d6faa-119">It lets users enter a location to find stores that are nearby.</span></span> <span data-ttu-id="d6faa-120">Para obter mais informações sobre este módulo, consulte [Módulo do seletor de armazenamento](store-selector.md).</span><span class="sxs-lookup"><span data-stu-id="d6faa-120">For more information on this module, see [Store Selector module](store-selector.md).</span></span>

## <a name="cart-module-settings"></a><span data-ttu-id="d6faa-121">Configurações do módulo de carrinho</span><span class="sxs-lookup"><span data-stu-id="d6faa-121">Cart module settings</span></span>

<span data-ttu-id="d6faa-122">Os módulos de carrinho têm as seguintes configurações que podem ser definidas em **Configurações de Site \> Extensões**:</span><span class="sxs-lookup"><span data-stu-id="d6faa-122">Cart modules have the following settings that can be configured at **Site Settings \> Extensions**:</span></span>

- <span data-ttu-id="d6faa-123">**Quantidade máxima** – Esta propriedade é usada para especificar o número máximo de cada item que pode ser adicionado ao carrinho.</span><span class="sxs-lookup"><span data-stu-id="d6faa-123">**Maximum quantity** – This property is used to specify the maximum number of each item that can be added to the cart.</span></span> <span data-ttu-id="d6faa-124">Por exemplo, um varejista pode decidir que apenas 10 de cada produto podem ser vendidos em uma única transação.</span><span class="sxs-lookup"><span data-stu-id="d6faa-124">For example, a retailer might decide that only 10 of each product can be sold in a single transaction.</span></span>
- <span data-ttu-id="d6faa-125">**Verificação de estoque** – Quando o valor é definido como **Verdadeiro**, um item é adicionado ao carrinho somente após o módulo da caixa de compra garantir que ele esteja em estoque.</span><span class="sxs-lookup"><span data-stu-id="d6faa-125">**Inventory check** – When the value is set to **True**, an item is added to the cart only after the buy box module makes sure that it's in stock.</span></span> <span data-ttu-id="d6faa-126">Essa verificação de estoque é feita tanto para os cenários em que o item será enviado como para os cenários em que ele será retirado na loja.</span><span class="sxs-lookup"><span data-stu-id="d6faa-126">This inventory check is done for scenarios where the item will be shipped and for scenarios where it will be picked up in the store.</span></span> <span data-ttu-id="d6faa-127">Se o valor estiver definido como **Falso**, nenhuma verificação de estoque será feita antes que um item seja adicionado ao carrinho e a ordem seja feita.</span><span class="sxs-lookup"><span data-stu-id="d6faa-127">If the value is set to **False**, no inventory check is done before an item is added to the cart and the order is placed.</span></span>
- <span data-ttu-id="d6faa-128">**Buffer de estoque** – Esta propriedade é usada para especificar um número de buffer para o estoque.</span><span class="sxs-lookup"><span data-stu-id="d6faa-128">**Inventory buffer** – This property is used to specify a buffer number for inventory.</span></span> <span data-ttu-id="d6faa-129">O estoque é mantido em tempo real e, quando muitos clientes fazem pedidos, pode ser difícil manter uma contagem precisa do estoque.</span><span class="sxs-lookup"><span data-stu-id="d6faa-129">Inventory is maintained in real time, and when many customers place orders, it can be difficult to maintain an accurate inventory count.</span></span> <span data-ttu-id="d6faa-130">Quando uma verificação de estoque é feita, se o estoque for menor que a quantidade do buffer, o produto é tratado como esgotado no estoque.</span><span class="sxs-lookup"><span data-stu-id="d6faa-130">When an inventory check is done, if the inventory is less than the buffer amount, the product is treated as out of stock.</span></span> <span data-ttu-id="d6faa-131">Sendo assim, quando as vendas ocorrem rapidamente por meio de vários canais, e a contagem do estoque não está totalmente sincronizada, há menos risco de que um item esgotado no estoque seja vendido.</span><span class="sxs-lookup"><span data-stu-id="d6faa-131">Therefore, when sales occur quickly through several channels, and the inventory count isn't fully synced, there is less risk that an item that is out of stock will be sold.</span></span>
- <span data-ttu-id="d6faa-132">**Voltar para compra** – Esta propriedade é usada para especificar o roteiro do link **Voltar para compra**.</span><span class="sxs-lookup"><span data-stu-id="d6faa-132">**Back to shopping** – This property is used to specify the route for the **Back to shopping** link.</span></span> <span data-ttu-id="d6faa-133">O roteiro pode ser configurado no nível do site, permitindo que os varejistas retornem o cliente para a Home Page ou qualquer outra página no site.</span><span class="sxs-lookup"><span data-stu-id="d6faa-133">The route can be configured at the site level, allowing retailers to take the customer back to the home page or any other page on the site.</span></span>

## <a name="commerce-scale-unit-interaction"></a><span data-ttu-id="d6faa-134">Interação do Commerce Scale Unit</span><span class="sxs-lookup"><span data-stu-id="d6faa-134">Commerce Scale Unit interaction</span></span>

<span data-ttu-id="d6faa-135">O módulo de carrinho recupera informações do produto usando as APIs de Commerce Scale Unit.</span><span class="sxs-lookup"><span data-stu-id="d6faa-135">The cart module retrieves product information by using Commerce Scale Unit APIs.</span></span> <span data-ttu-id="d6faa-136">A ID de carrinho do cookie do navegador é usada para recuperar todas as informações do produto direto do Commerce Scale Unit.</span><span class="sxs-lookup"><span data-stu-id="d6faa-136">The cart ID from the browser cookie is used to retrieve all the product information from Commerce Scale Unit.</span></span>

## <a name="add-a-cart-module-to-a-page"></a><span data-ttu-id="d6faa-137">Adicionar um módulo de carrinho a uma página</span><span class="sxs-lookup"><span data-stu-id="d6faa-137">Add a cart module to a page</span></span>

<span data-ttu-id="d6faa-138">Para adicionar um módulo de carrinho a uma nova página e definir as propriedades necessárias, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="d6faa-138">To add a cart module to a new page and set the required properties, follow these steps.</span></span>

1. <span data-ttu-id="d6faa-139">Crie um fragmento chamado **Fragmento do carrinho** e adicione um módulo ao novo fragmento.</span><span class="sxs-lookup"><span data-stu-id="d6faa-139">Create a fragment named **Cart fragment**, and add a cart module to the new fragment.</span></span>
1. <span data-ttu-id="d6faa-140">Adicione um título ao módulo de carrinho.</span><span class="sxs-lookup"><span data-stu-id="d6faa-140">Add a heading to the cart module.</span></span>
1. <span data-ttu-id="d6faa-141">Adicione um módulo de seletor de loja ao módulo de carrinho.</span><span class="sxs-lookup"><span data-stu-id="d6faa-141">Add a store selector module to the cart module.</span></span>
1. <span data-ttu-id="d6faa-142">Salve o fragmento, termine de editá-lo e publique o fragmento.</span><span class="sxs-lookup"><span data-stu-id="d6faa-142">Save the fragment, finish editing, and then publish the fragment.</span></span>
1. <span data-ttu-id="d6faa-143">Crie um modelo chamado **Modelo de carrinho** e adicione o fragmento do carrinho que você acabou de criar.</span><span class="sxs-lookup"><span data-stu-id="d6faa-143">Create a template named **Cart template**, and add the cart fragment that you just created.</span></span>
1. <span data-ttu-id="d6faa-144">Salve o modelo, termine de editá-lo e publique o modelo.</span><span class="sxs-lookup"><span data-stu-id="d6faa-144">Save the template, finish editing, and then publish the template.</span></span>
1. <span data-ttu-id="d6faa-145">Crie uma página que use o novo modelo.</span><span class="sxs-lookup"><span data-stu-id="d6faa-145">Create a page that uses the new template.</span></span>
1. <span data-ttu-id="d6faa-146">Salve e exiba a página.</span><span class="sxs-lookup"><span data-stu-id="d6faa-146">Save and preview the page.</span></span>
1. <span data-ttu-id="d6faa-147">Termine a edição da página e publique-a.</span><span class="sxs-lookup"><span data-stu-id="d6faa-147">Finish editing the page, and then publish the page.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="d6faa-148">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="d6faa-148">Additional resources</span></span>

[<span data-ttu-id="d6faa-149">Visão geral do kit de início</span><span class="sxs-lookup"><span data-stu-id="d6faa-149">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="d6faa-150">Módulo de contêiner</span><span class="sxs-lookup"><span data-stu-id="d6faa-150">Container module</span></span>](add-container-module.md)

[<span data-ttu-id="d6faa-151">Módulo seletor de armazenamento</span><span class="sxs-lookup"><span data-stu-id="d6faa-151">Store selector module</span></span>](store-selector.md)

[<span data-ttu-id="d6faa-152">Módulo de caixa de compra</span><span class="sxs-lookup"><span data-stu-id="d6faa-152">Buy box module</span></span>](add-buy-box.md)

[<span data-ttu-id="d6faa-153">Módulo de finalização da compra</span><span class="sxs-lookup"><span data-stu-id="d6faa-153">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="d6faa-154">Módulo de confirmação da ordem</span><span class="sxs-lookup"><span data-stu-id="d6faa-154">Order confirmation module</span></span>](order-confirmation-module.md)

[<span data-ttu-id="d6faa-155">Módulo de cabeçalho</span><span class="sxs-lookup"><span data-stu-id="d6faa-155">Header module</span></span>](author-header-module.md)

[<span data-ttu-id="d6faa-156">Módulo de rodapé</span><span class="sxs-lookup"><span data-stu-id="d6faa-156">Footer module</span></span>](author-footer-module.md)
