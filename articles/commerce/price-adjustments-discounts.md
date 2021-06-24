---
title: Ajustes de preço e descontos
description: Este artigo oferece informações sobre ajustes de preço e descontos no Dynamics 365 Commerce.
author: scott-tucker
ms.date: 06/11/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: RetailParameters, RetailPeriodicDiscount
audience: Application User
ms.reviewer: josaw
ms.custom: 15891
ms.assetid: bab5adf3-ddf0-4c22-a2eb-b4d25b88de99
ms.search.region: global
ms.search.industry: Retail
ms.author: scotttuc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 44c03ae0a04d648e788a72d8f6dcc3671c5736c7
ms.sourcegitcommit: 7c9d6be464db058511df9cb6ba162d21dc0554e8
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/11/2021
ms.locfileid: "6240933"
---
# <a name="price-adjustments-and-discounts"></a><span data-ttu-id="66075-103">Ajustes de preço e descontos</span><span class="sxs-lookup"><span data-stu-id="66075-103">Price adjustments and discounts</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="66075-104">Este artigo oferece informações sobre ajustes de preço e descontos no Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="66075-104">This article provides information about price adjustments and discounts in Dynamics 365 Commerce.</span></span>

<span data-ttu-id="66075-105">No Commerce, você pode fazer ajustes de preços nos produtos e também configurar descontos para serem aplicados a um item de linha ou uma transação no ponto de venda (PDV), em uma ordem de venda do call center ou em uma ordem online.</span><span class="sxs-lookup"><span data-stu-id="66075-105">In Commerce, you can make price adjustments to products, and can also set up discounts that are applied to a line item or a transaction at the point of sale (POS), in a call center sales order, or in an online order.</span></span> <span data-ttu-id="66075-106">Os ajustes de preço e descontos podem ser vinculados a grupos de preços.</span><span class="sxs-lookup"><span data-stu-id="66075-106">Both price adjustments and discounts can be linked to price groups.</span></span> <span data-ttu-id="66075-107">Para ajustes de preço e descontos, você pode especificar uma única data inicial e data final ou um período recorrente, um código do desconto e alguns atributos adicionais.</span><span class="sxs-lookup"><span data-stu-id="66075-107">For both price adjustments and discounts, you can specify a single start date and end date or a reoccurring period, a discount code, and a few additional attributes.</span></span> 

<span data-ttu-id="66075-108">Os ajustes de preço e os descontos podem ser aplicados a produtos, a variantes ou categorias.</span><span class="sxs-lookup"><span data-stu-id="66075-108">Price adjustments and discounts can be applied to products, variants, or categories.</span></span> <span data-ttu-id="66075-109">Se mais de um desconto for aplicado a um produto, um cliente poderá receber um dos descontos ou um desconto combinado, dependendo da configuração do desconto.</span><span class="sxs-lookup"><span data-stu-id="66075-109">If more than one discount applies to a product, a customer might receive either one of the discounts or a combined discount, depending on the configuration of the discount.</span></span> <span data-ttu-id="66075-110">O Commerce aplica automaticamente o desconto ou a combinação de descontos que oferecem o melhor preço ao cliente.</span><span class="sxs-lookup"><span data-stu-id="66075-110">Commerce automatically applies the discount or combination of discounts that gives the best price to the customer.</span></span> <span data-ttu-id="66075-111">Quando você configura um ajuste de preço ou um desconto, certifique-se de confirmar que os grupos de preços serão atribuídos aos canais, aos catálogos, às afiliações ou aos programas de fidelidade corretos aos quais você deseja que o desconto seja aplicado.</span><span class="sxs-lookup"><span data-stu-id="66075-111">When you set up a price adjustment or a discount, be sure to confirm that price groups are assigned to the correct channels, catalogs, affiliations, or loyalty programs that you want the discount to apply to.</span></span> <span data-ttu-id="66075-112">Além disso, se quiser gerar automaticamente a ID de desconto, você poderá configurar sequências numéricas na página **Parâmetros do Commerce** antes de definir um novo desconto ou ajuste de preço.</span><span class="sxs-lookup"><span data-stu-id="66075-112">Additionally, if you want to automatically generate the discount ID, set up number sequences on the **Commerce parameters** page before you define a new price adjustment or discount.</span></span>

> [!NOTE]
> <span data-ttu-id="66075-113">Você pode excluir um ajuste de preço ou um desconto.</span><span class="sxs-lookup"><span data-stu-id="66075-113">You can delete a price adjustment or a discount.</span></span> <span data-ttu-id="66075-114">No entanto, as informações estatísticas serão perdidas.</span><span class="sxs-lookup"><span data-stu-id="66075-114">However, statistical information will be lost.</span></span>

## <a name="types-of-discounts"></a><span data-ttu-id="66075-115">Tipos de descontos</span><span class="sxs-lookup"><span data-stu-id="66075-115">Types of discounts</span></span>

<span data-ttu-id="66075-116">Há muitos tipos de descontos:</span><span class="sxs-lookup"><span data-stu-id="66075-116">There are many types of discounts:</span></span>

- <span data-ttu-id="66075-117">**Desconto simples** – Uma única porcentagem ou valor.</span><span class="sxs-lookup"><span data-stu-id="66075-117">**Simple discount** – A single percentage or amount.</span></span>
- <span data-ttu-id="66075-118">**Desconto por quantidade** – Um desconto que é aplicado quando dois ou mais produtos são comprados.</span><span class="sxs-lookup"><span data-stu-id="66075-118">**Quantity discount** – A discount that is applied when two or more products are purchased.</span></span>
- <span data-ttu-id="66075-119">**Desconto da compra combinada** – Um desconto que é aplicado quando uma combinação específica de produtos é comprada.</span><span class="sxs-lookup"><span data-stu-id="66075-119">**Mix and match discount** – A discount that is applied when a specific combination of products is purchased.</span></span>
- <span data-ttu-id="66075-120">**Desconto de limite** – Um desconto que é aplicado quando o total da transação for maior do que um valor especificado.</span><span class="sxs-lookup"><span data-stu-id="66075-120">**Threshold discount** – A discount that is applied when the transaction total is more than a specified amount.</span></span>
- <span data-ttu-id="66075-121">**Desconto com base no meio de pagamento** – Um desconto aplicado quando o total da transação é maior do que um valor especificado e um tipo de pagamento específico (por exemplo, dinheiro, cartão de crédito ou de débito) é usado para o pagamento.</span><span class="sxs-lookup"><span data-stu-id="66075-121">**Tender-based discount** – A discount that is applied when the transaction total is more than a specified amount and a specific payment type (for example, cash, credit, or debit card) is used for payment.</span></span>
- <span data-ttu-id="66075-122">**Desconto de remessa** – Um desconto aplicado quando o total da transação é maior do que um valor especificado e um modo de entrega específico (por exemplo, remessa em dois dias ou remessa em 24h) é usado na ordem.</span><span class="sxs-lookup"><span data-stu-id="66075-122">**Shipping discount** – A discount that is applied when the transaction total is more than a specified amount and a specific mode of delivery (for example, two day shipping or overnight shipping) is used on the order.</span></span>

<span data-ttu-id="66075-123">Os ajustes de preço e descontos podem ser associados aos grupos de preços.</span><span class="sxs-lookup"><span data-stu-id="66075-123">Both price adjustments and discounts can be associated with price groups.</span></span> <span data-ttu-id="66075-124">Os grupos de preços podem ser associados aos canais, aos catálogos, às afiliações e aos programas de fidelidade.</span><span class="sxs-lookup"><span data-stu-id="66075-124">Price groups can then be associated with channels, catalogs, affiliations, and loyalty programs.</span></span>

> [!NOTE]
> <span data-ttu-id="66075-125">O desconto mixo e o desconto limite têm propriedades chamadas "Contar produtos não passíveis de desconto" e "Contar produtos não passíveis de desconto em relação ao limite", respectivamente.</span><span class="sxs-lookup"><span data-stu-id="66075-125">The mix and match discount and the threshold discount have properties named "Count non-discountable products" and "Count non-discountable products towards threshold", respectively.</span></span> <span data-ttu-id="66075-126">Se essas propriedades forem habilitadas, um item que não está qualificado para qualquer outro desconto ainda pode ajudar a qualificar uma transação do desconto, mas o item não qualificado não obterá o desconto.</span><span class="sxs-lookup"><span data-stu-id="66075-126">If these properties are enabled, an item that is not eligible for any discount can still help qualify a transaction for the discount, but the ineligible item will not get the discount.</span></span> 
> 
> <span data-ttu-id="66075-127">Por exemplo, se você criar um desconto misto com duas linhas, A e B, em que um cliente deva obter 10% de desconto em ambos os itens, mas o item A tem uma configuração "Impedir todos os descontos" marcada, isso normalmente impediria que o item A fosse incluso no desconto.</span><span class="sxs-lookup"><span data-stu-id="66075-127">For example, if you create a mix and match discount with two lines, A and B, where a customer should get 10% off on both items, but item A has the configuration "Prevent all discounts" checked, then this would typically stop item A from being included in the discount.</span></span> <span data-ttu-id="66075-128">No entanto, se a propriedade "Contar produtos não passíveis de desconto" for habilitada, o item A pode ser usado para qualificar para o desconto misto, mas o desconto de 10% será aplicado somente ao item B. Uma lógica semelhante aplica-se ao desconto limite.</span><span class="sxs-lookup"><span data-stu-id="66075-128">However, if the "Count non-discountable products" property is enabled, then item A can be used to qualify for the mix and match discount, but the 10% discount will only be applied to item B. Similar logic applies to the threshold discount.</span></span> 
>
> <span data-ttu-id="66075-129">No entanto, a propriedade "Contar produtos não passíveis de desconto em relação ao limite" tem uma funcionalidade adicional quando comparada com a propriedade "Contar produtos não passíveis de desconto" dos descontos mixos.</span><span class="sxs-lookup"><span data-stu-id="66075-129">However, the property "Count non-discountable products towards threshold" has an additional capability when compared to the "Count non-discountable products" property of the mix and match discounts.</span></span> <span data-ttu-id="66075-130">Se o desconto limite estiver habilitado e não houver um item que tem um desconto existente que impediria qualquer outro desconto ao item, o preço pago para este item será qualificado para o limite, mas o item não obterá o desconto adicional.</span><span class="sxs-lookup"><span data-stu-id="66075-130">If the threshold discount is enabled, and if there is an item that has an existing discount which would prevent the item from any other discounts, then  the price paid for this item would qualify towards meeting the threshold, but this item will not get the additional discount.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
