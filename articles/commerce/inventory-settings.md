---
title: Aplicar configurações de estoque
description: Este tópico abrange as configurações de estoque e descreve como aplicá-las no Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 06/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: 737e71dc73750bf151629fd904081924ac15b91e
ms.sourcegitcommit: 4a981ee4be6d7e6c0e55541535d386bce2565cba
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/27/2020
ms.locfileid: "3621212"
---
# <a name="apply-inventory-settings"></a><span data-ttu-id="30e09-103">Aplicar configurações de estoque</span><span class="sxs-lookup"><span data-stu-id="30e09-103">Apply inventory settings</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="30e09-104">Este tópico abrange as configurações de estoque e descreve como aplicá-las no Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="30e09-104">This topic covers inventory settings and describes how to apply them in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="30e09-105">Visão Geral</span><span class="sxs-lookup"><span data-stu-id="30e09-105">Overview</span></span>

<span data-ttu-id="30e09-106">As configurações de estoque especificam se o estoque deverá ser verificado antes que os produtos sejam adicionados ao carrinho.</span><span class="sxs-lookup"><span data-stu-id="30e09-106">Inventory settings specify whether inventory should be checked before products are added to the cart.</span></span> <span data-ttu-id="30e09-107">Eles também definem as mensagens de merchandising relacionadas ao estoque, como "Em estoque" e "Apenas alguns restantes".</span><span class="sxs-lookup"><span data-stu-id="30e09-107">They also define inventory-related merchandising messages, such as "In stock" and "Only a few left."</span></span> <span data-ttu-id="30e09-108">Essas configurações garantem que um produto não seja comprado se estiver esgotado.</span><span class="sxs-lookup"><span data-stu-id="30e09-108">These settings ensure that a product can't be purchased if it's out of stock.</span></span>

<span data-ttu-id="30e09-109">O Dynamics 365 Commerce fornece estimativas de disponibilidade em estoque para produtos.</span><span class="sxs-lookup"><span data-stu-id="30e09-109">Dynamics 365 Commerce provides estimates of on-hand availability for products.</span></span> <span data-ttu-id="30e09-110">Para obter informações sobre como é calculada a disponibilidade em estoque estimada, consulte [Calcular a disponibilidade de estoque para canais de varejo](calculated-inventory-retail-channels.md).</span><span class="sxs-lookup"><span data-stu-id="30e09-110">For information about how estimated on-hand availability is calculated, see [Calculate inventory availability for retail channels](calculated-inventory-retail-channels.md).</span></span>

<span data-ttu-id="30e09-111">No construtor de sites do Commerce, os limites de estoque e intervalos podem ser definidos para um produto ou uma categoria.</span><span class="sxs-lookup"><span data-stu-id="30e09-111">In Commerce site builder, inventory thresholds and ranges can be defined for a product or a category.</span></span> <span data-ttu-id="30e09-112">Eles determinam se o estoque pode ser classificado como em estoque, estoque baixo ou esgotado.</span><span class="sxs-lookup"><span data-stu-id="30e09-112">They determine whether inventory can be classified as in stock, low stock, or out of stock.</span></span> <span data-ttu-id="30e09-113">Para obter detalhes, consulte [Configurar buffers de estoque e níveis de estoque](inventory-buffers-levels.md).</span><span class="sxs-lookup"><span data-stu-id="30e09-113">For details, see [Configure inventory buffers and inventory levels](inventory-buffers-levels.md).</span></span>

## <a name="inventory-settings"></a><span data-ttu-id="30e09-114">Configurações de estoque</span><span class="sxs-lookup"><span data-stu-id="30e09-114">Inventory settings</span></span>

<span data-ttu-id="30e09-115">No Commerce, as configurações de estoque são definidas em **Configurações do Site \> Extensões \> Gerenciamento de Estoque** no construtor de sites.</span><span class="sxs-lookup"><span data-stu-id="30e09-115">In Commerce, inventory settings are defined at **Site Settings \> Extensions \> Inventory Management** in site builder.</span></span> <span data-ttu-id="30e09-116">Há quatro configurações de estoque, uma das quais está obsoleta (preterida):</span><span class="sxs-lookup"><span data-stu-id="30e09-116">There are four inventory settings, one of which is obsolete (deprecated):</span></span>

- <span data-ttu-id="30e09-117">**Habilitar verificação de estoque no aplicativo** – essa configuração ativa uma verificação de estoque de produto.</span><span class="sxs-lookup"><span data-stu-id="30e09-117">**Enable inventory check on app** – This setting turns on a product inventory check.</span></span> <span data-ttu-id="30e09-118">Os módulos caixa de compras, carrinho e separação na loja verificarão então o estoque do produto e só permitirão que um produto seja adicionado ao carrinho se o estoque estiver disponível.</span><span class="sxs-lookup"><span data-stu-id="30e09-118">Buy box, cart, and pick up in store modules will then check product inventory, and will allow a product to be added to the cart only if inventory is available.</span></span>
- <span data-ttu-id="30e09-119">**Nível de estoque baseado em** – essa configuração define como os níveis de estoque são calculados.</span><span class="sxs-lookup"><span data-stu-id="30e09-119">**Inventory level based on** – This setting defines how inventory levels are calculated.</span></span> <span data-ttu-id="30e09-120">Os valores disponíveis são **Total Disponível**, **Físico Disponível** e **Limite de esgotado**.</span><span class="sxs-lookup"><span data-stu-id="30e09-120">The available values are **Total Available**, **Physical Available**, and **Out of stock threshold**.</span></span> <span data-ttu-id="30e09-121">No Commerce, o limite e os intervalos de estoque podem ser definidos para cada produto e categoria.</span><span class="sxs-lookup"><span data-stu-id="30e09-121">In Commerce, inventory threshold and ranges can be defined for each product and category.</span></span> <span data-ttu-id="30e09-122">As APIs de estoque retornam informações de estoque de produtos para a propriedade **total Disponível** e a propriedade **Físico Disponível**.</span><span class="sxs-lookup"><span data-stu-id="30e09-122">The inventory APIs return product inventory information for both the **Total Available** property and the **Physical Available** property.</span></span> <span data-ttu-id="30e09-123">O varejista decide se o **Total Disponível** ou **Físico Disponível** deve ser usado para determinar a contagem de estoque e os intervalos correspondentes para os status em estoque e esgotado.</span><span class="sxs-lookup"><span data-stu-id="30e09-123">The retailer decides whether the **Total Available** or **Physical Available** value should be used to determine the inventory count and the corresponding ranges for in-stock and out-of-stock statuses.</span></span>

    <span data-ttu-id="30e09-124">O valor **Limite de esgotado** da configuração **Nível de estoque com base em** é um valor antigo (herdado) e obsoleto.</span><span class="sxs-lookup"><span data-stu-id="30e09-124">The **Out of stock threshold** value of the **Inventory level based on** setting is an old (legacy), obsolete value.</span></span> <span data-ttu-id="30e09-125">Quando ele está selecionado, a contagem de estoque é determinada dos resultados do valor de **Total Disponível**, mas o limite é definido pela configuração numérica **Limite de esgotado**, descrita posteriormente.</span><span class="sxs-lookup"><span data-stu-id="30e09-125">When it's selected, the inventory count is determined from the results of the **Total Available** value, but the threshold is defined by the **Out of stock threshold** numeric setting that is described later.</span></span> <span data-ttu-id="30e09-126">Essa configuração de limite se aplica a todos os produtos em um site de comércio eletrônico.</span><span class="sxs-lookup"><span data-stu-id="30e09-126">This threshold setting applies to all products across an e-Commerce site.</span></span> <span data-ttu-id="30e09-127">Se o estoque estiver abaixo do número limite, um produto será considerado esgotado.</span><span class="sxs-lookup"><span data-stu-id="30e09-127">If inventory is below the threshold number, a product is considered out of stock.</span></span> <span data-ttu-id="30e09-128">Caso contrário, ele será considerada em estoque.</span><span class="sxs-lookup"><span data-stu-id="30e09-128">Otherwise, it's considered in stock.</span></span> <span data-ttu-id="30e09-129">Os recursos do valor **Limite de esgotado** são limitados e não é recomendável usá-lo na versão 10.0.12 e posteriores.</span><span class="sxs-lookup"><span data-stu-id="30e09-129">The capabilities of the **Out of stock threshold** value are limited, and we don't recommend that you use it in version 10.0.12 and later.</span></span>

- <span data-ttu-id="30e09-130">**Intervalos de estoque** – essa configuração define os intervalos de estoque em que a mensagem é mostrada nos módulos de site.</span><span class="sxs-lookup"><span data-stu-id="30e09-130">**Inventory ranges** – This setting defines the inventory ranges that message are shown for on site modules.</span></span> <span data-ttu-id="30e09-131">Isso só se aplicará se o valor **Total Disponível** ou o valor **Físico Disponível** for selecionado para a configuração **Nível de estoque com base em**.</span><span class="sxs-lookup"><span data-stu-id="30e09-131">It's applicable only if either the **Total Available** value or the **Physical Available** value is selected for the **Inventory level based on** setting.</span></span> <span data-ttu-id="30e09-132">Os valores disponíveis são **Todos**, **Baixo e esgotado** e **Esgotado**.</span><span class="sxs-lookup"><span data-stu-id="30e09-132">The available values are **All**, **Low and out of stock**, and **Out of stock**.</span></span>

    - <span data-ttu-id="30e09-133">Quando **Tudo** estiver selecionado, as mensagens de todos os intervalos de estoque, de em estoque (mensagem "Disponível") a esgotado (mensagem "Esgotado"), serão mostradas.</span><span class="sxs-lookup"><span data-stu-id="30e09-133">When **All** is selected, messages for all inventory ranges, from in stock ("Available" message) to out of stock ("Out of stock" message), will be shown.</span></span>
    - <span data-ttu-id="30e09-134">Quando **Baixo e esgotado** estiver selecionado, as mensagens de todos os intervalos de estoque, exceto em estoque (mensagem "Disponível") serão mostradas.</span><span class="sxs-lookup"><span data-stu-id="30e09-134">When **Low and out of stock** is selected, messages for all inventory ranges except in stock ("Available" message) will be shown.</span></span>
    - <span data-ttu-id="30e09-135">Quando **Esgotado** não estiver selecionado, apenas a mensagem "Esgotado" será mostrada.</span><span class="sxs-lookup"><span data-stu-id="30e09-135">When **Out of stock** is selected, only the "Out of stock" message will be shown.</span></span>

- <span data-ttu-id="30e09-136">**Limite de esgotado** – essa configuração numérica antiga só entrará em vigor se o valor **Limite de esgotado** estiver selecionado para a configuração **Nível de estoque com base em**.</span><span class="sxs-lookup"><span data-stu-id="30e09-136">**Out of stock threshold** – This old numeric setting will take effect only if the **Out of stock threshold** value is selected for the **Inventory level based on** setting.</span></span>

## <a name="modules-that-use-inventory-settings"></a><span data-ttu-id="30e09-137">Módulos que usam configurações de estoque</span><span class="sxs-lookup"><span data-stu-id="30e09-137">Modules that use inventory settings</span></span>

<span data-ttu-id="30e09-138">Os módulos caixa de compras, lista de desejos, seletor de loja, carrinho e ícone de carrinho usam configurações de estoque para mostrar os intervalos de estoque e as mensagens.</span><span class="sxs-lookup"><span data-stu-id="30e09-138">Buy box, wishlist, store selector, cart, and cart icon modules use inventory settings to show the inventory ranges and messages.</span></span>

<span data-ttu-id="30e09-139">A imagem a seguir mostra um exemplo de uma página de detalhes do produto (PDP) que está mostrando uma mensagem de em estoque ("Disponível").</span><span class="sxs-lookup"><span data-stu-id="30e09-139">The following image shows an example of a product details page (PDP) that is showing an in-stock ("Available") message.</span></span>

![Exemplo de um módulo PDP com uma mensagem de em estoque](./media/pdp-InStock.png)

<span data-ttu-id="30e09-141">A imagem a seguir mostra um exemplo de uma página de detalhes do produto (PDP) que está mostrando uma mensagem "Esgotado".</span><span class="sxs-lookup"><span data-stu-id="30e09-141">The following image shows an example of a PDP that is showing an "Out of stock" message.</span></span>

![Exemplo de um módulo PDP com uma mensagem de esgotado](./media/pdp-outofstock.png)

<span data-ttu-id="30e09-143">A imagem a seguir mostra um exemplo de um carrinho mostrando uma mensagem de em estoque ("Disponível").</span><span class="sxs-lookup"><span data-stu-id="30e09-143">The following image shows an example of a cart that is showing an in-stock ("Available") message.</span></span>

![Exemplo de um módulo carrinho com uma mensagem de em estoque](./media/cart-instock.png)

## <a name="additional-resources"></a><span data-ttu-id="30e09-145">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="30e09-145">Additional resources</span></span>

[<span data-ttu-id="30e09-146">Visão geral do kit de início</span><span class="sxs-lookup"><span data-stu-id="30e09-146">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="30e09-147">Configurar buffers de estoque e níveis de estoque</span><span class="sxs-lookup"><span data-stu-id="30e09-147">Configure inventory buffers and inventory levels</span></span>](inventory-buffers-levels.md)

[<span data-ttu-id="30e09-148">Módulo de carrinho</span><span class="sxs-lookup"><span data-stu-id="30e09-148">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="30e09-149">Módulo de caixa de compra</span><span class="sxs-lookup"><span data-stu-id="30e09-149">Buy box module</span></span>](add-buy-box.md)

[<span data-ttu-id="30e09-150">Páginas e módulos de gerenciamento de contas</span><span class="sxs-lookup"><span data-stu-id="30e09-150">Account management pages and modules</span></span>](account-management.md)

[<span data-ttu-id="30e09-151">Módulo de seletor de loja</span><span class="sxs-lookup"><span data-stu-id="30e09-151">Store selector module</span></span>](store-selector.md)
