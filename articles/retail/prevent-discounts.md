---
title: Opções para impedir descontos em produtos de varejo
description: Há vários motivos que levam varejistas a impedir que alguns produtos tenham descontos, seja em uma promoção ou durante a venda no PDV.
author: jblucher
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailPeriodicDiscount
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 85183
ms.assetid: e8c5a24f-7edd-4fd6-af80-5e0ac9f03127
ms.search.region: Global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: c9d3e7af95dffddfddc34059d93a2a5a350d08e5
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1550735"
---
# <a name="options-for-preventing-discounts-for-retail-products"></a><span data-ttu-id="41674-103">Opções para impedir descontos em produtos de varejo</span><span class="sxs-lookup"><span data-stu-id="41674-103">Options for preventing discounts for retail products</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="41674-104">Há vários motivos que levam varejistas a impedir que alguns produtos tenham descontos, seja em uma promoção ou durante a venda no PDV.</span><span class="sxs-lookup"><span data-stu-id="41674-104">There are various reasons why retailers may want to prevent some products from being discounted, either from a promotion or during the sale at the POS.</span></span>

<span data-ttu-id="41674-105">As seguintes opções, que podem ser encontradas na guia **Varejo** de produtos liberados, permitirão que os produtos sejam configurados para evitar todos os descontos ou os descontos manuais.</span><span class="sxs-lookup"><span data-stu-id="41674-105">The following options, which can be found on the **Retail** tab of released products, will allow the product to be configured to prevent all or manual discounts.</span></span> <span data-ttu-id="41674-106">As configurações também podem ser especificadas no nível da categoria a partir da hierarquia da categoria de varejo.</span><span class="sxs-lookup"><span data-stu-id="41674-106">The settings can also be specified at the category level from the retail category hierarchy.</span></span>

- <span data-ttu-id="41674-107">**Impedir todos os descontos** – selecione esta opção para impedir que todos os tipos de descontos sejam aplicados a este produto.</span><span class="sxs-lookup"><span data-stu-id="41674-107">**Prevent all discounts** – Select this option to prevent all types of discounts from being applied to this product.</span></span> <span data-ttu-id="41674-108">Isso inclui promoções, como compra combinada, descontos de quantidade e de limite, bem como os descontos manuais de linha e de transação que são aplicados durante uma venda por um usuário do PDV.</span><span class="sxs-lookup"><span data-stu-id="41674-108">This includes promotions such as mix and match, quantity and threshold discounts, as well as manual line and transaction discounts that are applied during a sale by a POS user.</span></span>
- <span data-ttu-id="41674-109">**Impedir descontos manuais** – selecione esta opção para evitar apenas os descontos de linha manual ou de transação que são aplicados durante uma venda por um usuário do PDV.</span><span class="sxs-lookup"><span data-stu-id="41674-109">**Prevent manual discounts** – Select this option to only prevent the manual line or transaction discounts that are applied during a sale by a POS user.</span></span> <span data-ttu-id="41674-110">Produtos com essa opção selecionada ainda estão qualificados para promoções, como descontos de compra combinada e descontos de quantidade e de limite.</span><span class="sxs-lookup"><span data-stu-id="41674-110">Products with this option selected are still eligible for promotions, such as mix and match and quantity and threshold discounts.</span></span>

> [!NOTE]
> <span data-ttu-id="41674-111">Essas configurações não restringem a operação de substituição de preço, pois elas definem o preço base e não são tratadas como um desconto.</span><span class="sxs-lookup"><span data-stu-id="41674-111">These settings do not restrict the price override operation, because that sets the base price and is not treated as a discount.</span></span>

<span data-ttu-id="41674-112">[![campo impedir descontos](./media/prevent-discounts.png)](./media/prevent-discounts.png)</span><span class="sxs-lookup"><span data-stu-id="41674-112">[![prevent discounts field](./media/prevent-discounts.png)](./media/prevent-discounts.png)</span></span>
