---
title: Configurar o imposto para ordens online
description: Este tópico fornece uma visão geral da seleção do grupo de impostos para diferentes tipos de ordens online no Dynamics 365 Commerce.
author: gvrmohanreddy
ms.date: 11/16/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: gmohanv
ms.search.validFrom: 2020-11-01
ms.dyn365.ops.version: 10.0.16
ms.openlocfilehash: 68b7e59a1e1ea18bdcd4e7a9117e4892407f40ff
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5791838"
---
# <a name="configure-sales-tax-for-online-orders"></a><span data-ttu-id="aa505-103">Configurar o imposto para ordens online</span><span class="sxs-lookup"><span data-stu-id="aa505-103">Configure sales tax for online orders</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="aa505-104">Este tópico fornece uma visão geral da seleção do grupo de impostos para diferentes tipos de ordens online.</span><span class="sxs-lookup"><span data-stu-id="aa505-104">This topic provides an overview of sales tax group selection for different online order types.</span></span> 

<span data-ttu-id="aa505-105">Seu canal de comércio eletrônico pode oferecer suporte a opções como entrega ou retirada para ordens online.</span><span class="sxs-lookup"><span data-stu-id="aa505-105">Your e-commerce channel may want to support options like delivery or pickup for online orders.</span></span> <span data-ttu-id="aa505-106">A aplicabilidade do imposto é baseada na opção selecionada por seus usuários online.</span><span class="sxs-lookup"><span data-stu-id="aa505-106">The sales tax applicability is based on the option selected by your online users.</span></span> <span data-ttu-id="aa505-107">Quando um cliente do site opta por comprar um item online e o envia para um endereço, o imposto é determinado com base na configuração do grupo de impostos do endereço de remessa do cliente.</span><span class="sxs-lookup"><span data-stu-id="aa505-107">When a site customer chooses to buy an item online and gets it shipped to an address, the sales tax is determined based on the customer's shipping address tax group setting.</span></span> <span data-ttu-id="aa505-108">Quando um cliente opta por retirar um item comprado em uma loja, o imposto é determinado com base na configuração do grupo de impostos da loja.</span><span class="sxs-lookup"><span data-stu-id="aa505-108">When a customer opts to pick up a purchased item at a store, the sales tax is determined based on the pickup store's tax group setting.</span></span> 

## <a name="orders-shipped-to-a-customer-address"></a><span data-ttu-id="aa505-109">Ordens enviadas para o endereço de um cliente</span><span class="sxs-lookup"><span data-stu-id="aa505-109">Orders shipped to a customer address</span></span> 

<span data-ttu-id="aa505-110">Em geral, os impostos para ordens online que enviam para endereços de clientes são definidos pelo destino.</span><span class="sxs-lookup"><span data-stu-id="aa505-110">In general, taxes for online orders that ship to customer addresses are defined by the destination.</span></span> <span data-ttu-id="aa505-111">Cada grupo de imposto tem uma configuração de imposto com base no destino de varejo na qual sua empresa pode definir detalhes de destino, como região, estado e cidade de forma hierárquica.</span><span class="sxs-lookup"><span data-stu-id="aa505-111">Every sales tax group has a retail destination-based tax configuration in which your business can define destination details such as county/region, state, county, and city in a hierarchical form.</span></span> <span data-ttu-id="aa505-112">Quando uma ordem online é feita, o mecanismo de imposto do Commerce usa o endereço de entrega de cada item de linha na ordem e encontra grupos de impostos com critérios de imposto baseados no destino correspondentes.</span><span class="sxs-lookup"><span data-stu-id="aa505-112">When an online order is placed, the Commerce tax engine uses the delivery address of every line item in the order, and finds sales tax groups with matching destination-based tax criteria.</span></span> <span data-ttu-id="aa505-113">Por exemplo, em uma ordem online com um endereço de entrega de item de linha para São Francisco (Califórnia), o mecanismo de cálculo de impostos encontrará o grupo de impostos e o código do imposto para a Califórnia e calculará o imposto para cada item de linha apropriadamente.</span><span class="sxs-lookup"><span data-stu-id="aa505-113">For example, for an online order with a line item delivery address to San Francisco, California, the tax engine will find the sales tax group and sales tax code for California and then calculate tax for each line item accordingly.</span></span>  

## <a name="customer-based-tax-groups"></a><span data-ttu-id="aa505-114">Grupos de imposto baseados no cliente</span><span class="sxs-lookup"><span data-stu-id="aa505-114">Customer-based tax groups</span></span>

<span data-ttu-id="aa505-115">Na sede do Comércio, existem dois locais onde os grupos de imposto do cliente são configurados:</span><span class="sxs-lookup"><span data-stu-id="aa505-115">In Commerce headquarters, there are two places where customer tax groups are configured:</span></span>

- <span data-ttu-id="aa505-116">**Perfil do cliente**</span><span class="sxs-lookup"><span data-stu-id="aa505-116">**Customer's profile**</span></span>
- <span data-ttu-id="aa505-117">**Endereço de remessa do cliente**</span><span class="sxs-lookup"><span data-stu-id="aa505-117">**Customer's shipping address**</span></span>

### <a name="if-a-customers-profile-has-a-tax-group-configured"></a><span data-ttu-id="aa505-118">Se o perfil de um cliente tiver um grupo de imposto configurado</span><span class="sxs-lookup"><span data-stu-id="aa505-118">If a customer's profile has a tax group configured</span></span>

<span data-ttu-id="aa505-119">O registro do perfil de um cliente na sede pode ter um grupo de imposto configurado; porém, para ordens online, o grupo de imposto configurado no perfil de um cliente não será usado pelo mecanismo de cálculo de impostos.</span><span class="sxs-lookup"><span data-stu-id="aa505-119">A customer's profile record in headquarters may have a sales tax group configured, however for online orders the sales tax group configured in a customer's profile will not be used by the tax engine.</span></span> 

### <a name="if-a-customers-shipping-address-has-a-tax-group-configured"></a><span data-ttu-id="aa505-120">Se o endereço de remessa de um cliente tiver um grupo de imposto configurado</span><span class="sxs-lookup"><span data-stu-id="aa505-120">If a customer's shipping address has a tax group configured</span></span>

<span data-ttu-id="aa505-121">Se o registro de endereço de remessa de um cliente tiver um grupo de imposto configurado e uma ordem online (ou item de linha) for enviado ao endereço de remessa do cliente, o grupo de imposto configurado no registro de endereço do cliente será usado pelo mecanismo de cálculo de impostos.</span><span class="sxs-lookup"><span data-stu-id="aa505-121">If a customer's shipping address record has a tax group configured and an online order (or line item) is shipped to the customer's shipping address, the tax group configured in the customer's address record will be used by the tax engine for tax calculations.</span></span>

#### <a name="configure-a-tax-group-for-a-customers-shipping-address-record"></a><span data-ttu-id="aa505-122">Configurar um grupo de imposto para o registro do endereço de remessa de um cliente</span><span class="sxs-lookup"><span data-stu-id="aa505-122">Configure a tax group for a customer's shipping address record</span></span>

<span data-ttu-id="aa505-123">Para configurar um grupo de impostos para o registro do endereço de remessa de um cliente na sede do Commerce, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="aa505-123">To configure a tax group for a customer's shipping address record in Commerce headquarters, follow these steps.</span></span>

1. <span data-ttu-id="aa505-124">Acesse **Todos os clientes** e selecione o cliente desejado.</span><span class="sxs-lookup"><span data-stu-id="aa505-124">Go to **All customers**, and then select the desired customer.</span></span> 
1. <span data-ttu-id="aa505-125">Na FastTab **Endereços**, selecione o endereço desejado e depois escolha **Mais opções \> Avançado**.</span><span class="sxs-lookup"><span data-stu-id="aa505-125">On the **Addresses** FastTab, select the desired address, and then select **More options \> Advanced**.</span></span> 
1. <span data-ttu-id="aa505-126">Na guia **Geral** da página **Gerenciar endereços**, defina o valor do imposto conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="aa505-126">Under the **General** tab on the **Manage addresses** page, set the sales tax value as needed.</span></span>

> [!NOTE]
> <span data-ttu-id="aa505-127">O grupo de imposto é definido usando o endereço de entrega da linha de ordem e os impostos com base no destino são configurados no próprio grupo de imposto.</span><span class="sxs-lookup"><span data-stu-id="aa505-127">The tax group is defined using the delivery address of the order line and the destination-based taxes are configured at the tax group itself.</span></span> <span data-ttu-id="aa505-128">Para obter mais informações, consulte [Configurar os impostos para as lojas online com base no destino](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/set-up-taxes-for-online-stores-based-on-destination).</span><span class="sxs-lookup"><span data-stu-id="aa505-128">For more information, see [Set up taxes for online stores based on destination](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/set-up-taxes-for-online-stores-based-on-destination).</span></span>

## <a name="order-pickup-in-store"></a><span data-ttu-id="aa505-129">Retirada de ordens na loja</span><span class="sxs-lookup"><span data-stu-id="aa505-129">Order pickup in store</span></span>

<span data-ttu-id="aa505-130">Para linhas de ordem com retirada na loja ou retirada em frente à loja especificada, o grupo de imposto da loja de retirada selecionada será aplicado.</span><span class="sxs-lookup"><span data-stu-id="aa505-130">For order lines with pickup in store or curbside pickup specified, the tax group from the selected pickup store will be applied.</span></span> <span data-ttu-id="aa505-131">Para obter detalhes sobre como configurar o grupo de imposto para determinada loja, consulte [Definir outras opções de imposto para lojas](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/set-other-tax-options-for-stores).</span><span class="sxs-lookup"><span data-stu-id="aa505-131">For details about how to configure the tax group for a given store, see [Set other tax options for stores](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/set-other-tax-options-for-stores).</span></span>

> [!NOTE]
> <span data-ttu-id="aa505-132">Quando uma linha de ordem é retirada em uma loja, as configurações de impostos do endereço do cliente (se configuradas) serão ignoradas pelo mecanismo de cálculo de impostos e a configuração de impostos da loja de coleta será aplicada.</span><span class="sxs-lookup"><span data-stu-id="aa505-132">When an order line is picked up at a store, a customer's address tax settings (if set up) will be ignored by the tax engine and the pickup store's tax configuration will be applied.</span></span> 

## <a name="additional-resources"></a><span data-ttu-id="aa505-133">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="aa505-133">Additional resources</span></span>

[<span data-ttu-id="aa505-134">Visão geral de imposto</span><span class="sxs-lookup"><span data-stu-id="aa505-134">Sales tax overview</span></span>](https://docs.microsoft.com/dynamics365/finance/general-ledger/indirect-taxes-overview?toc=/dynamics365/commerce/toc.json) 

[<span data-ttu-id="aa505-135">Métodos de cálculo de impostos no campo de Origem</span><span class="sxs-lookup"><span data-stu-id="aa505-135">Sales tax calculation methods in the Origin field</span></span>](https://docs.microsoft.com/dynamics365/finance/general-ledger/sales-tax-calculation-methods-origin-field?toc=/dynamics365/commerce/toc.json) 

[<span data-ttu-id="aa505-136"> Substituições e atribuições de impostos</span><span class="sxs-lookup"><span data-stu-id="aa505-136">Sales tax assignment and overrides</span></span>](https://docs.microsoft.com/dynamics365/supply-chain/procurement/tasks/sales-tax-assignment-overrides?toc=/dynamics365/commerce/toc.json) 

[<span data-ttu-id="aa505-137">Opções de cálculo do valor total e do intervalo para códigos de impostos</span><span class="sxs-lookup"><span data-stu-id="aa505-137">Whole amount and Interval calculation options for sales tax codes</span></span>](https://docs.microsoft.com/dynamics365/finance/general-ledger/whole-amount-interval-options-sales-tax-codes?toc=/dynamics365/commerce/toc.json) 

[<span data-ttu-id="aa505-138">Cálculo da isenção de imposto</span><span class="sxs-lookup"><span data-stu-id="aa505-138">Calculation of tax exemption</span></span>](tax-exempt-price-inclusive.md) 



[!INCLUDE[footer-include](../includes/footer-banner.md)]