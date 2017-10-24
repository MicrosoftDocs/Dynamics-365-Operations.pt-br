---
title: "Venda e devolução de produtos fora de um sortimento"
description: "Com o Dynamics 365 para Varejo, você pode vender e devolver produtos fora das variedades."
author: pdp1207
manager: AnnBe
ms.date: 05/24/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: 
ms.custom: 
ms.search.region: Global
ms.search.industry: retail
ms.author: prabhup
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 7fa5b240bc9c9f96ae5483be316eff62df915570
ms.contentlocale: pt-br
ms.lasthandoff: 09/29/2017

---

# <a name="sell-and-return-products-outside-of-an-assortment"></a><span data-ttu-id="44eff-103">Venda e devolução de produtos fora de um sortimento</span><span class="sxs-lookup"><span data-stu-id="44eff-103">Sell and return products outside of an assortment</span></span>
<span data-ttu-id="44eff-104">Um cenário comum para qualquer revendedor é vender produtos para seus clientes ou aceitar devoluções de seus clientes, mesmo que eles não transportem os produtos específicos em sua loja (em outras palavras, os produtos não são distribuídos na loja)</span><span class="sxs-lookup"><span data-stu-id="44eff-104">A common scenario for any retailer is to sell products to their customers or accept returns from their customers even if they don’t carry the specific products in their store (in other words, the products are not assorted to the store).</span></span>
<span data-ttu-id="44eff-105">Estes são alguns dos cenários típicos:</span><span class="sxs-lookup"><span data-stu-id="44eff-105">Here are some typical scenarios:</span></span>

+ <span data-ttu-id="44eff-106">Um revendedor não possui todos os seus produtos em uma loja específica.</span><span class="sxs-lookup"><span data-stu-id="44eff-106">A retailer doesn’t carry all its products in a specific store.</span></span> <span data-ttu-id="44eff-107">Os produtos restantes são armazenados no depósito.</span><span class="sxs-lookup"><span data-stu-id="44eff-107">The remaining products are stored in the warehouse.</span></span> <span data-ttu-id="44eff-108">O associado da loja pode ajudar o cliente pesquisando ou navegando pelos produtos no depósito, adicionando-os ao carrinho e concluindo o check-out selecionando um método de entrega, como envio para um endereço do depósito ou deixando o cliente pegar o produto na loja atual ou em outra loja.</span><span class="sxs-lookup"><span data-stu-id="44eff-108">The store associate can assist the customer by searching or browsing for the products in the warehouse, add them to the cart, and complete the checkout by selecting a delivery method, such as shipping to an address from the warehouse or letting the customer pick up the product from the current store or from another store.</span></span>
+ <span data-ttu-id="44eff-109">Um revendedor não possui produtos específicos na loja ou não os possui em estoque na loja visitada pelo cliente, mas os produtos estão disponíveis em outras lojas.</span><span class="sxs-lookup"><span data-stu-id="44eff-109">A retailer doesn’t carry specific products in the store or doesn’t have them in stock at the store the customer visited, but the products are available in other stores.</span></span> <span data-ttu-id="44eff-110">O associado da loja pode ajudar o cliente pesquisando ou navegando nos produtos na outra loja, adicione-os ao carrinho e complete o check-out selecionando um método de entrega.</span><span class="sxs-lookup"><span data-stu-id="44eff-110">The store associate can assist the customer by searching or browsing the products in the other store, add them to the cart, and complete the checkout by selecting a delivery method.</span></span>
+ <span data-ttu-id="44eff-111">Um revendedor tem muitas lojas em e ao redor de uma cidade ou código postal específico e não quer forçar os clientes a devolver produtos à mesma loja em que foram comprados.</span><span class="sxs-lookup"><span data-stu-id="44eff-111">A retailer has many stores in and around a specific city or zip code and doesn’t want to force the customers to return products to the same store they were purchased in.</span></span> <span data-ttu-id="44eff-112">Em vez disso, os clientes podem devolver o produto para qualquer loja.</span><span class="sxs-lookup"><span data-stu-id="44eff-112">Instead, customers can return products to any store.</span></span>


<span data-ttu-id="44eff-113">Esses cenários comuns estão disponíveis para varejistas usando o Dynamics 365 para Varejo.</span><span class="sxs-lookup"><span data-stu-id="44eff-113">Those common scenarios are available for retailers using Dynamics 365 for Retail.</span></span> <span data-ttu-id="44eff-114">Com Varejo, você pode:</span><span class="sxs-lookup"><span data-stu-id="44eff-114">With Retail, you can:</span></span>
+ <span data-ttu-id="44eff-115">Pesquisar ou procurar produtos em outras lojas.</span><span class="sxs-lookup"><span data-stu-id="44eff-115">Search or browse products at other stores.</span></span>
+ <span data-ttu-id="44eff-116">Procure ou procure todos os produtos lançados.</span><span class="sxs-lookup"><span data-stu-id="44eff-116">Search or browse all released products.</span></span>
+ <span data-ttu-id="44eff-117">Crie transações de caixa e transporte ou ordens de clientes.</span><span class="sxs-lookup"><span data-stu-id="44eff-117">Create cash-and-carry transactions or customer orders.</span></span>
+ <span data-ttu-id="44eff-118">Selecione as opções de entrega para pedidos de clientes.</span><span class="sxs-lookup"><span data-stu-id="44eff-118">Select delivery options for customer orders.</span></span>
+ <span data-ttu-id="44eff-119">Pegue produtos na loja atual ou em outra loja.</span><span class="sxs-lookup"><span data-stu-id="44eff-119">Pick up products at the current store or another store.</span></span>
+ <span data-ttu-id="44eff-120">Cancelar um pedido na loja atual ou em outra loja.</span><span class="sxs-lookup"><span data-stu-id="44eff-120">Cancel an order at the current store or another store.</span></span>
+ <span data-ttu-id="44eff-121">Devolver um pedido com ou sem o recibo na loja atual ou em outra loja.</span><span class="sxs-lookup"><span data-stu-id="44eff-121">Return an order with or without the receipt at the current store or another store.</span></span>

