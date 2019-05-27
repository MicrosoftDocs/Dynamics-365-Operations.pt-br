---
title: Ajustes de preço e descontos
description: Este artigo oferece informações sobre ajustes de preço e descontos no Microsoft Dynamics 365 for Retail.
author: scott-tucker
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailParameters, RetailPeriodicDiscount
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 15891
ms.assetid: bab5adf3-ddf0-4c22-a2eb-b4d25b88de99
ms.search.region: global
ms.search.industry: Retail
ms.author: scotttuc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 61ac8e5fbdc4d91bb5bc5372a7fb96633043473a
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1549443"
---
# <a name="price-adjustments-and-discounts"></a><span data-ttu-id="fe8f5-103">Ajustes de preço e descontos</span><span class="sxs-lookup"><span data-stu-id="fe8f5-103">Price adjustments and discounts</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="fe8f5-104">Este artigo oferece informações sobre ajustes de preço e descontos no Microsoft Dynamics 365 for Retail.</span><span class="sxs-lookup"><span data-stu-id="fe8f5-104">This article provides information about price adjustments and discounts in Microsoft Dynamics 365 for Retail.</span></span>

<span data-ttu-id="fe8f5-105">No Dynamics 365 for Retail, você pode fazer ajustes de preços nos produtos e também configurar descontos para serem aplicados a um item de linha ou uma transação no ponto de venda (PDV), em uma ordem de venda do call center ou em uma ordem online.</span><span class="sxs-lookup"><span data-stu-id="fe8f5-105">In Dynamics 365 for Retail, you can make price adjustments to products, and can also set up discounts that are applied to a line item or a transaction at the point of sale (POS), in a call center sales order, or in an online order.</span></span> <span data-ttu-id="fe8f5-106">Os ajustes de preço e descontos podem ser vinculados a grupos de preços.</span><span class="sxs-lookup"><span data-stu-id="fe8f5-106">Both price adjustments and discounts can be linked to price groups.</span></span> <span data-ttu-id="fe8f5-107">Para ajustes de preço e descontos, você pode especificar uma única data inicial e data final ou um período recorrente, um código do desconto e alguns atributos adicionais.</span><span class="sxs-lookup"><span data-stu-id="fe8f5-107">For both price adjustments and discounts, you can specify a single start date and end date or a reoccurring period, a discount code, and a few additional attributes.</span></span> <span data-ttu-id="fe8f5-108">Os ajustes de preço e os descontos podem ser aplicados a produtos, a variantes ou categorias.</span><span class="sxs-lookup"><span data-stu-id="fe8f5-108">Price adjustments and discounts can be applied to products, variants, or categories.</span></span> <span data-ttu-id="fe8f5-109">Se mais de um desconto for aplicado a um produto, um cliente poderá receber um dos descontos ou um desconto combinado, dependendo da configuração do desconto.</span><span class="sxs-lookup"><span data-stu-id="fe8f5-109">If more than one discount applies to a product, a customer might receive either one of the discounts or a combined discount, depending on the configuration of the discount.</span></span> <span data-ttu-id="fe8f5-110">O Dynamics 365 for Retail aplica automaticamente o desconto ou a combinação de descontos que oferecem o melhor preço ao cliente.</span><span class="sxs-lookup"><span data-stu-id="fe8f5-110">Dynamics 365 for Retail automatically applies the discount or combination of discounts that gives the best price to the customer.</span></span> <span data-ttu-id="fe8f5-111">Quando você configura um ajuste de preço ou um desconto, certifique-se de confirmar que os grupos de preços serão atribuídos aos canais, aos catálogos, às afiliações ou aos programas de fidelidade corretos aos quais você deseja que o desconto seja aplicado.</span><span class="sxs-lookup"><span data-stu-id="fe8f5-111">When you set up a price adjustment or a discount, be sure to confirm that price groups are assigned to the correct channels, catalogs, affiliations, or loyalty programs that you want the discount to apply to.</span></span> <span data-ttu-id="fe8f5-112">Além disso, se quiser gerar automaticamente a ID de desconto, você poderá configurar sequências numéricas na página **Parâmetros de varejo** antes de definir um novo desconto ou ajuste de preço.</span><span class="sxs-lookup"><span data-stu-id="fe8f5-112">Additionally, if you want to automatically generate the discount ID, set up number sequences on the **Retail parameters** page before you define a new price adjustment or discount.</span></span>

> [!NOTE]
> <span data-ttu-id="fe8f5-113">Você pode excluir um ajuste de preço ou um desconto.</span><span class="sxs-lookup"><span data-stu-id="fe8f5-113">You can delete a price adjustment or a discount.</span></span> <span data-ttu-id="fe8f5-114">No entanto, as informações estatísticas serão perdidas.</span><span class="sxs-lookup"><span data-stu-id="fe8f5-114">However, statistical information will be lost.</span></span>

## <a name="types-of-discounts"></a><span data-ttu-id="fe8f5-115">Tipos de descontos</span><span class="sxs-lookup"><span data-stu-id="fe8f5-115">Types of discounts</span></span>

<span data-ttu-id="fe8f5-116">Há quatro tipos de descontos de varejo:</span><span class="sxs-lookup"><span data-stu-id="fe8f5-116">There are four types of retail discounts:</span></span>

- <span data-ttu-id="fe8f5-117">**Desconto simples** – Uma única porcentagem ou valor.</span><span class="sxs-lookup"><span data-stu-id="fe8f5-117">**Simple discount** – A single percentage or amount.</span></span>
- <span data-ttu-id="fe8f5-118">**Desconto por quantidade** – Um desconto que é aplicado quando dois ou mais produtos são comprados.</span><span class="sxs-lookup"><span data-stu-id="fe8f5-118">**Quantity discount** – A discount that is applied when two or more products are purchased.</span></span>
- <span data-ttu-id="fe8f5-119">**Desconto da compra combinada** – Um desconto que é aplicado quando uma combinação específica de produtos é comprada.</span><span class="sxs-lookup"><span data-stu-id="fe8f5-119">**Mix and match discount** – A discount that is applied when a specific combination of products is purchased.</span></span>
- <span data-ttu-id="fe8f5-120">**Desconto de limite** – Um desconto que é aplicado quando o total da transação for maior do que um valor especificado.</span><span class="sxs-lookup"><span data-stu-id="fe8f5-120">**Threshold discount** – A discount that is applied when the transaction total is more than a specified amount.</span></span>

<span data-ttu-id="fe8f5-121">Os ajustes de preço e descontos podem ser associados aos grupos de preços.</span><span class="sxs-lookup"><span data-stu-id="fe8f5-121">Both price adjustments and discounts can be associated with price groups.</span></span> <span data-ttu-id="fe8f5-122">Os grupos de preços podem ser associados aos canais, aos catálogos, às afiliações e aos programas de fidelidade.</span><span class="sxs-lookup"><span data-stu-id="fe8f5-122">Price groups can then be associated with channels, catalogs, affiliations, and loyalty programs.</span></span>
