---
title: Aplicar configurações de estoque
description: Este tópico abrange as configurações de estoque e descreve como aplicá-las no Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: 77a3bde12fd047e15d7730903416cdb5263a8cd9
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4972800"
---
# <a name="apply-inventory-settings"></a><span data-ttu-id="6c246-103">Aplicar configurações de estoque</span><span class="sxs-lookup"><span data-stu-id="6c246-103">Apply inventory settings</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="6c246-104">Este tópico abrange as configurações de estoque e descreve como aplicá-las no Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="6c246-104">This topic covers inventory settings and describes how to apply them in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="6c246-105">Visão Geral</span><span class="sxs-lookup"><span data-stu-id="6c246-105">Overview</span></span>

<span data-ttu-id="6c246-106">As configurações de estoque especificam se o estoque deverá ser verificado antes que os produtos sejam adicionados ao carrinho.</span><span class="sxs-lookup"><span data-stu-id="6c246-106">Inventory settings specify whether inventory should be checked before products are added to the cart.</span></span> <span data-ttu-id="6c246-107">Eles também definem as mensagens de merchandising relacionadas ao estoque, como "Em estoque" e "Apenas alguns restantes".</span><span class="sxs-lookup"><span data-stu-id="6c246-107">They also define inventory-related merchandising messages, such as "In stock" and "Only a few left."</span></span> <span data-ttu-id="6c246-108">Essas configurações garantem que um produto não seja comprado se estiver esgotado.</span><span class="sxs-lookup"><span data-stu-id="6c246-108">These settings ensure that a product can't be purchased if it's out of stock.</span></span>

<span data-ttu-id="6c246-109">O Dynamics 365 Commerce fornece estimativas de disponibilidade em estoque para produtos.</span><span class="sxs-lookup"><span data-stu-id="6c246-109">Dynamics 365 Commerce provides estimates of on-hand availability for products.</span></span> <span data-ttu-id="6c246-110">Para obter informações sobre como é calculada a disponibilidade em estoque estimada, consulte [Calcular a disponibilidade de estoque para canais de varejo](calculated-inventory-retail-channels.md).</span><span class="sxs-lookup"><span data-stu-id="6c246-110">For information about how estimated on-hand availability is calculated, see [Calculate inventory availability for retail channels](calculated-inventory-retail-channels.md).</span></span>

<span data-ttu-id="6c246-111">No construtor de sites do Commerce, os limites de estoque e intervalos podem ser definidos para um produto ou uma categoria.</span><span class="sxs-lookup"><span data-stu-id="6c246-111">In Commerce site builder, inventory thresholds and ranges can be defined for a product or a category.</span></span> <span data-ttu-id="6c246-112">Eles determinam se o estoque pode ser classificado como em estoque, estoque baixo ou esgotado.</span><span class="sxs-lookup"><span data-stu-id="6c246-112">They determine whether inventory can be classified as in stock, low stock, or out of stock.</span></span> <span data-ttu-id="6c246-113">Para obter detalhes, consulte [Configurar buffers de estoque e níveis de estoque](inventory-buffers-levels.md).</span><span class="sxs-lookup"><span data-stu-id="6c246-113">For details, see [Configure inventory buffers and inventory levels](inventory-buffers-levels.md).</span></span>

> [!NOTE]
> <span data-ttu-id="6c246-114">O suporte para limites e intervalos de estoque está disponível na versão 10.0.12 do Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="6c246-114">Support for inventory thresholds and ranges is available in the Dynamics 365 Commerce 10.0.12 release.</span></span>

## <a name="inventory-settings"></a><span data-ttu-id="6c246-115">Configurações de estoque</span><span class="sxs-lookup"><span data-stu-id="6c246-115">Inventory settings</span></span>

<span data-ttu-id="6c246-116">No Commerce, as configurações de estoque são definidas em **Configurações do Site \> Extensões \> Gerenciamento de Estoque** no construtor de sites.</span><span class="sxs-lookup"><span data-stu-id="6c246-116">In Commerce, inventory settings are defined at **Site Settings \> Extensions \> Inventory Management** in site builder.</span></span> <span data-ttu-id="6c246-117">Há quatro configurações de estoque, uma das quais está obsoleta (preterida):</span><span class="sxs-lookup"><span data-stu-id="6c246-117">There are four inventory settings, one of which is obsolete (deprecated):</span></span>

- <span data-ttu-id="6c246-118">**Habilitar verificação de estoque no aplicativo** – essa configuração ativa uma verificação de estoque de produto.</span><span class="sxs-lookup"><span data-stu-id="6c246-118">**Enable stock check in app** – This setting turns on a product inventory check.</span></span> <span data-ttu-id="6c246-119">Os módulos caixa de compras, carrinho e separação na loja verificarão então o estoque do produto e só permitirão que um produto seja adicionado ao carrinho se o estoque estiver disponível.</span><span class="sxs-lookup"><span data-stu-id="6c246-119">Buy box, cart, and pick up in store modules will then check product inventory, and will allow a product to be added to the cart only if inventory is available.</span></span>
- <span data-ttu-id="6c246-120">**Nível de estoque baseado em** – essa configuração define como os níveis de estoque são calculados.</span><span class="sxs-lookup"><span data-stu-id="6c246-120">**Inventory level based on** – This setting defines how inventory levels are calculated.</span></span> <span data-ttu-id="6c246-121">Os valores disponíveis são **Total Disponível**, **Físico Disponível** e **Limite de esgotado**.</span><span class="sxs-lookup"><span data-stu-id="6c246-121">The available values are **Total Available**, **Physical Available**, and **Out of stock threshold**.</span></span> <span data-ttu-id="6c246-122">No Commerce, o limite e os intervalos de estoque podem ser definidos para cada produto e categoria.</span><span class="sxs-lookup"><span data-stu-id="6c246-122">In Commerce, inventory threshold and ranges can be defined for each product and category.</span></span> <span data-ttu-id="6c246-123">As APIs de estoque retornam informações de estoque de produtos para a propriedade **total Disponível** e a propriedade **Físico Disponível**.</span><span class="sxs-lookup"><span data-stu-id="6c246-123">The inventory APIs return product inventory information for both the **Total Available** property and the **Physical Available** property.</span></span> <span data-ttu-id="6c246-124">O varejista decide se o **Total Disponível** ou **Físico Disponível** deve ser usado para determinar a contagem de estoque e os intervalos correspondentes para os status em estoque e esgotado.</span><span class="sxs-lookup"><span data-stu-id="6c246-124">The retailer decides whether the **Total Available** or **Physical Available** value should be used to determine the inventory count and the corresponding ranges for in-stock and out-of-stock statuses.</span></span>

    <span data-ttu-id="6c246-125">O valor **Limite de esgotado** da configuração **Nível de estoque com base em** é um valor antigo (herdado) e obsoleto.</span><span class="sxs-lookup"><span data-stu-id="6c246-125">The **Out of stock threshold** value of the **Inventory level based on** setting is an old (legacy), obsolete value.</span></span> <span data-ttu-id="6c246-126">Quando ele está selecionado, a contagem de estoque é determinada dos resultados do valor de **Total Disponível**, mas o limite é definido pela configuração numérica **Limite de esgotado**, descrita posteriormente.</span><span class="sxs-lookup"><span data-stu-id="6c246-126">When it's selected, the inventory count is determined from the results of the **Total Available** value, but the threshold is defined by the **Out of stock threshold** numeric setting that is described later.</span></span> <span data-ttu-id="6c246-127">Essa configuração de limite se aplica a todos os produtos em um site de comércio eletrônico.</span><span class="sxs-lookup"><span data-stu-id="6c246-127">This threshold setting applies to all products across an e-commerce site.</span></span> <span data-ttu-id="6c246-128">Se o estoque estiver abaixo do número limite, um produto será considerado esgotado.</span><span class="sxs-lookup"><span data-stu-id="6c246-128">If inventory is below the threshold number, a product is considered out of stock.</span></span> <span data-ttu-id="6c246-129">Caso contrário, ele será considerada em estoque.</span><span class="sxs-lookup"><span data-stu-id="6c246-129">Otherwise, it's considered in stock.</span></span> <span data-ttu-id="6c246-130">Os recursos do valor **Limite de esgotado** são limitados e não é recomendável usá-lo na versão 10.0.12 e posteriores.</span><span class="sxs-lookup"><span data-stu-id="6c246-130">The capabilities of the **Out of stock threshold** value are limited, and we don't recommend that you use it in version 10.0.12 and later.</span></span>

- <span data-ttu-id="6c246-131">**Intervalos de estoque** – essa configuração define os intervalos de estoque em que a mensagem é mostrada nos módulos de site.</span><span class="sxs-lookup"><span data-stu-id="6c246-131">**Inventory ranges** – This setting defines the inventory ranges that message are shown for on site modules.</span></span> <span data-ttu-id="6c246-132">Isso só se aplicará se o valor **Total Disponível** ou o valor **Físico Disponível** for selecionado para a configuração **Nível de estoque com base em**.</span><span class="sxs-lookup"><span data-stu-id="6c246-132">It's applicable only if either the **Total Available** value or the **Physical Available** value is selected for the **Inventory level based on** setting.</span></span> <span data-ttu-id="6c246-133">Os valores disponíveis são **Todos**, **Baixo e esgotado** e **Esgotado**.</span><span class="sxs-lookup"><span data-stu-id="6c246-133">The available values are **All**, **Low and out of stock**, and **Out of stock**.</span></span>

    - <span data-ttu-id="6c246-134">Quando **Tudo** estiver selecionado, as mensagens de todos os intervalos de estoque, de em estoque (mensagem "Disponível") a esgotado (mensagem "Esgotado"), serão mostradas.</span><span class="sxs-lookup"><span data-stu-id="6c246-134">When **All** is selected, messages for all inventory ranges, from in stock ("Available" message) to out of stock ("Out of stock" message), will be shown.</span></span>
    - <span data-ttu-id="6c246-135">Quando **Baixo e esgotado** estiver selecionado, as mensagens de todos os intervalos de estoque, exceto em estoque (mensagem "Disponível") serão mostradas.</span><span class="sxs-lookup"><span data-stu-id="6c246-135">When **Low and out of stock** is selected, messages for all inventory ranges except in stock ("Available" message) will be shown.</span></span>
    - <span data-ttu-id="6c246-136">Quando **Esgotado** não estiver selecionado, apenas a mensagem "Esgotado" será mostrada.</span><span class="sxs-lookup"><span data-stu-id="6c246-136">When **Out of stock** is selected, only the "Out of stock" message will be shown.</span></span>

- <span data-ttu-id="6c246-137">**Limite de esgotado** – essa configuração numérica antiga só entrará em vigor se o valor **Limite de esgotado** estiver selecionado para a configuração **Nível de estoque com base em**.</span><span class="sxs-lookup"><span data-stu-id="6c246-137">**Out of stock threshold** – This old numeric setting will take effect only if the **Out of stock threshold** value is selected for the **Inventory level based on** setting.</span></span>

> [!IMPORTANT] 
> <span data-ttu-id="6c246-138">Essas configurações estão disponíveis na versão 10.0.12 do Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="6c246-138">These settings are available in the Dynamics 365 Commerce 10.0.12 release.</span></span> <span data-ttu-id="6c246-139">Se estiver atualizando de uma versão mais antiga do Dynamics 365 Commerce, você deverá atualizar manualmente o arquivo appsettings.json.</span><span class="sxs-lookup"><span data-stu-id="6c246-139">If you are updating from an older version of Dynamics 365 Commerce, you must manually update the appsettings.json file.</span></span> <span data-ttu-id="6c246-140">Para obter instruções sobre como atualizar o arquivo appsettings.json, consulte [SDK e atualizações da biblioteca de módulos](e-commerce-extensibility/sdk-updates.md#update-the-appsettingsjson-file).</span><span class="sxs-lookup"><span data-stu-id="6c246-140">For instructions on updating the appsettings.json file, see [SDK and module library updates](e-commerce-extensibility/sdk-updates.md#update-the-appsettingsjson-file).</span></span>

## <a name="modules-that-use-inventory-settings"></a><span data-ttu-id="6c246-141">Módulos que usam configurações de estoque</span><span class="sxs-lookup"><span data-stu-id="6c246-141">Modules that use inventory settings</span></span>

<span data-ttu-id="6c246-142">Os módulos caixa de compras, lista de desejos, seletor de loja, carrinho e ícone de carrinho usam configurações de estoque para mostrar os intervalos de estoque e as mensagens.</span><span class="sxs-lookup"><span data-stu-id="6c246-142">Buy box, wishlist, store selector, cart, and cart icon modules use inventory settings to show the inventory ranges and messages.</span></span>

<span data-ttu-id="6c246-143">A imagem a seguir mostra um exemplo de uma página de detalhes do produto (PDP) que está mostrando uma mensagem de em estoque ("Disponível").</span><span class="sxs-lookup"><span data-stu-id="6c246-143">The following image shows an example of a product details page (PDP) that is showing an in-stock ("Available") message.</span></span>

![Exemplo de um módulo PDP com uma mensagem de em estoque](./media/pdp-InStock.png)

<span data-ttu-id="6c246-145">A imagem a seguir mostra um exemplo de uma página de detalhes do produto (PDP) que está mostrando uma mensagem "Esgotado".</span><span class="sxs-lookup"><span data-stu-id="6c246-145">The following image shows an example of a PDP that is showing an "Out of stock" message.</span></span>

![Exemplo de um módulo PDP com uma mensagem de esgotado](./media/pdp-outofstock.png)

<span data-ttu-id="6c246-147">A imagem a seguir mostra um exemplo de um carrinho mostrando uma mensagem de em estoque ("Disponível").</span><span class="sxs-lookup"><span data-stu-id="6c246-147">The following image shows an example of a cart that is showing an in-stock ("Available") message.</span></span>

![Exemplo de um módulo carrinho com uma mensagem de em estoque](./media/cart-instock.png)

## <a name="additional-resources"></a><span data-ttu-id="6c246-149">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="6c246-149">Additional resources</span></span>

[<span data-ttu-id="6c246-150">Visão geral da biblioteca de módulos</span><span class="sxs-lookup"><span data-stu-id="6c246-150">Module library overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="6c246-151">Configurar buffers de estoque e níveis de estoque</span><span class="sxs-lookup"><span data-stu-id="6c246-151">Configure inventory buffers and inventory levels</span></span>](inventory-buffers-levels.md)

[<span data-ttu-id="6c246-152">Módulo de carrinho</span><span class="sxs-lookup"><span data-stu-id="6c246-152">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="6c246-153">Módulo de caixa de compra</span><span class="sxs-lookup"><span data-stu-id="6c246-153">Buy box module</span></span>](add-buy-box.md)

[<span data-ttu-id="6c246-154">Páginas e módulos de gerenciamento de contas</span><span class="sxs-lookup"><span data-stu-id="6c246-154">Account management pages and modules</span></span>](account-management.md)

[<span data-ttu-id="6c246-155">Módulo de seletor de loja</span><span class="sxs-lookup"><span data-stu-id="6c246-155">Store selector module</span></span>](store-selector.md)

[<span data-ttu-id="6c246-156">SDK e atualizações da biblioteca de módulos</span><span class="sxs-lookup"><span data-stu-id="6c246-156">SDK and module library updates</span></span>](e-commerce-extensibility/sdk-updates.md)
