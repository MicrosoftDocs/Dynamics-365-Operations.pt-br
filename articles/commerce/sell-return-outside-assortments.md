---
title: Vender e retornar produtos que não fazem parte do sortimento de uma loja
description: Com o Dynamics 365 Commerce, você pode vender e devolver produtos fora das variedades.
author: pdp1207
ms.date: 05/24/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: RetailAssortmentDetails
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.search.region: Global
ms.search.industry: retail
ms.author: prabhup
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.openlocfilehash: b6bae9f0d3a236c69ee3ee47226c19c1e1dcaf42
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5794034"
---
# <a name="sell-and-return-products-that-arent-part-of-a-stores-assortment"></a><span data-ttu-id="01f7f-103">Vender e retornar produtos que não fazem parte do sortimento de uma loja</span><span class="sxs-lookup"><span data-stu-id="01f7f-103">Sell and return products that aren't part of a store's assortment</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="01f7f-104">Um cenário comum para qualquer varejista é vender produtos para seus clientes ou aceitar devoluções de seus clientes, mesmo que eles não tenham os produtos específicos em sua loja (ou seja, os produtos não são sortidos para a loja)</span><span class="sxs-lookup"><span data-stu-id="01f7f-104">A common scenario for any retailer is to sell products to their customers or accept returns from their customers even if they don't carry the specific products in their store (in other words, the products are not assorted to the store).</span></span>

<span data-ttu-id="01f7f-105">Estes são alguns dos cenários típicos:</span><span class="sxs-lookup"><span data-stu-id="01f7f-105">Here are some typical scenarios:</span></span>

+ <span data-ttu-id="01f7f-106">Um revendedor não tem todos os seus produtos em uma loja específica.</span><span class="sxs-lookup"><span data-stu-id="01f7f-106">A retailer doesn't carry all its products in a specific store.</span></span> <span data-ttu-id="01f7f-107">Os produtos restantes são armazenados no depósito.</span><span class="sxs-lookup"><span data-stu-id="01f7f-107">The remaining products are stored in the warehouse.</span></span> <span data-ttu-id="01f7f-108">O associado da loja pode ajudar o cliente pesquisando ou navegando pelos produtos no depósito, adicionando-os ao carrinho e concluindo o check-out selecionando um método de entrega, como envio para um endereço do depósito ou deixando o cliente pegar o produto na loja atual ou em outra loja.</span><span class="sxs-lookup"><span data-stu-id="01f7f-108">The store associate can assist the customer by searching or browsing for the products in the warehouse, add them to the cart, and complete the checkout by selecting a delivery method, such as shipping to an address from the warehouse or letting the customer pick up the product from the current store or from another store.</span></span>
+ <span data-ttu-id="01f7f-109">Um varejista não tem produtos específicos na loja ou não os possui em estoque na loja visitada pelo cliente, mas os produtos estão disponíveis em outras lojas.</span><span class="sxs-lookup"><span data-stu-id="01f7f-109">A retailer doesn't carry specific products in the store or doesn't have them in stock at the store the customer visited, but the products are available in other stores.</span></span> <span data-ttu-id="01f7f-110">O associado da loja pode ajudar o cliente pesquisando ou navegando nos produtos na outra loja, adicione-os ao carrinho e complete o check-out selecionando um método de entrega.</span><span class="sxs-lookup"><span data-stu-id="01f7f-110">The store associate can assist the customer by searching or browsing the products in the other store, add them to the cart, and complete the checkout by selecting a delivery method.</span></span>
+ <span data-ttu-id="01f7f-111">Um varejista tem muitas lojas em uma cidade ou CEP e ao redor dela. Ele não quer forçar os clientes a devolver produtos à mesma loja em que fizeram a compra.</span><span class="sxs-lookup"><span data-stu-id="01f7f-111">A retailer has many stores in and around a specific city or zip code and doesn't want to force the customers to return products to the same store they were purchased in.</span></span> <span data-ttu-id="01f7f-112">Em vez disso, os clientes podem devolver o produto para qualquer loja.</span><span class="sxs-lookup"><span data-stu-id="01f7f-112">Instead, customers can return products to any store.</span></span>

<span data-ttu-id="01f7f-113">Esses cenários comuns estão disponíveis para varejistas que usam o Commerce.</span><span class="sxs-lookup"><span data-stu-id="01f7f-113">Those common scenarios are available for retailers using Commerce.</span></span> <span data-ttu-id="01f7f-114">Com o Commerce, você pode:</span><span class="sxs-lookup"><span data-stu-id="01f7f-114">With Commerce, you can:</span></span>

+ <span data-ttu-id="01f7f-115">Pesquisar ou procurar produtos em outras lojas.</span><span class="sxs-lookup"><span data-stu-id="01f7f-115">Search or browse products at other stores.</span></span>
+ <span data-ttu-id="01f7f-116">Procure ou procure todos os produtos lançados.</span><span class="sxs-lookup"><span data-stu-id="01f7f-116">Search or browse all released products.</span></span>
+ <span data-ttu-id="01f7f-117">Crie transações de caixa e transporte ou ordens de clientes.</span><span class="sxs-lookup"><span data-stu-id="01f7f-117">Create cash-and-carry transactions or customer orders.</span></span>
+ <span data-ttu-id="01f7f-118">Selecione as opções de entrega para pedidos de clientes.</span><span class="sxs-lookup"><span data-stu-id="01f7f-118">Select delivery options for customer orders.</span></span>
+ <span data-ttu-id="01f7f-119">Pegue produtos na loja atual ou em outra loja.</span><span class="sxs-lookup"><span data-stu-id="01f7f-119">Pick up products at the current store or another store.</span></span>
+ <span data-ttu-id="01f7f-120">Cancelar um pedido na loja atual ou em outra loja.</span><span class="sxs-lookup"><span data-stu-id="01f7f-120">Cancel an order at the current store or another store.</span></span>
+ <span data-ttu-id="01f7f-121">Devolver um pedido com ou sem o recibo na loja atual ou em outra loja.</span><span class="sxs-lookup"><span data-stu-id="01f7f-121">Return an order with or without the receipt at the current store or another store.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]