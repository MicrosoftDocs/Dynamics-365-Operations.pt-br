---
title: Impedir descontos em produtos de varejo
description: "Há vários motivos que levam varejistas a impedir que alguns produtos tenham descontos, seja em uma promoção ou durante a venda no PDV."
author: jeffbl
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations, Retail
ms.custom: 85183
ms.assetid: e8c5a24f-7edd-4fd6-af80-5e0ac9f03127
ms.search.region: Global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: c124ecf104bdb3de786c9dd98c2b07a4c9c04041
ms.openlocfilehash: 0debfe984a83295dde145fe4b8c2deb836345cd6
ms.contentlocale: pt-br
ms.lasthandoff: 07/31/2017

---

# <a name="prevent-discounts-for-retail-products"></a><span data-ttu-id="f5366-103">Impedir descontos em produtos de varejo</span><span class="sxs-lookup"><span data-stu-id="f5366-103">Prevent discounts for retail products</span></span>

[!include[banner](includes/banner.md)]

<span data-ttu-id="f5366-104">Há vários motivos que levam varejistas a impedir que alguns produtos tenham descontos, seja em uma promoção ou durante a venda no PDV.</span><span class="sxs-lookup"><span data-stu-id="f5366-104">There are various reasons why retailers may want to prevent some products from being discounted, either from a promotion or during the sale at the POS.</span></span>

<span data-ttu-id="f5366-105">As seguintes opções, que podem ser encontradas na guia **Varejo** de produtos liberados, permitirão que os produtos sejam configurados para evitar todos os descontos ou os descontos manuais.</span><span class="sxs-lookup"><span data-stu-id="f5366-105">The following options, which can be found on the **Retail** tab of released products, will allow the product to be configured to prevent all or manual discounts.</span></span> <span data-ttu-id="f5366-106">As configurações também podem ser especificadas no nível da categoria a partir da hierarquia da categoria de varejo.</span><span class="sxs-lookup"><span data-stu-id="f5366-106">The settings can also be specified at the category level from the retail category hierarchy.</span></span>

<span data-ttu-id="f5366-107">**Impedir todos os descontos**: selecione esta opção para impedir que todos os tipos de descontos sejam aplicados a este produto.</span><span class="sxs-lookup"><span data-stu-id="f5366-107">**Prevent all discounts**: Select this option to prevent all types of discounts from being applied to this product.</span></span> <span data-ttu-id="f5366-108">Isso inclui promoções, como compra combinada, descontos de quantidade e de limite, bem como os descontos manuais de linha e de transação que são aplicados durante uma venda por um usuário do PDV.</span><span class="sxs-lookup"><span data-stu-id="f5366-108">This includes promotions such as mix and match, quantity and threshold discounts, as well as manual line and transaction discounts that are applied during a sale by a POS user.</span></span>

<span data-ttu-id="f5366-109">**Impedir descontos manuais**: selecione esta opção para evitar somente os descontos manuais de linha ou de transação que são aplicados durante uma venda por um usuário do PDV.</span><span class="sxs-lookup"><span data-stu-id="f5366-109">**Prevent manual discounts**: Select this option to only prevent the manual line or transaction discounts that are applied during a sale by a POS user.</span></span> <span data-ttu-id="f5366-110">Produtos com essa opção selecionada ainda estão qualificados para promoções, como descontos de compra combinada e descontos de quantidade e de limite.</span><span class="sxs-lookup"><span data-stu-id="f5366-110">Products with this option selected are still eligible for promotions, such as mix and match and quantity and threshold discounts.</span></span>

<span data-ttu-id="f5366-111">**Observação**: essas configurações não restringem a operação de substituição de preço, pois elas definem o preço base e isso não é tratado como um desconto.</span><span class="sxs-lookup"><span data-stu-id="f5366-111">**Note**: These settings do not restrict the price override operation, because that sets the base price and is not treated as a discount.</span></span>  

![campo impedir descontos](/media/prevent-discounts.png)

