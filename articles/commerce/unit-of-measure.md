---
title: Aplicar configurações de unidade de medida
description: Este tópico abrange as configurações de unidade de medida e descreve como aplicá-las no Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 04/23/2021
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: 7d338ba207c9a101f5e224ca66555b16a457bcbc
ms.sourcegitcommit: dc4898aa32f381620c517bf89c7856e693563ace
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/17/2021
ms.locfileid: "6271392"
---
# <a name="apply-unit-of-measure-settings"></a><span data-ttu-id="2fa4a-103">Aplicar configurações de unidade de medida</span><span class="sxs-lookup"><span data-stu-id="2fa4a-103">Apply unit of measure settings</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="2fa4a-104">Este tópico abrange as configurações de unidade de medida e descreve como aplicá-las no Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="2fa4a-104">This topic covers unit of measure settings and describes how to apply them in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="2fa4a-105">Um produto pode ser vendido em unidades diferentes, como "cada", "par" e "dúzia".</span><span class="sxs-lookup"><span data-stu-id="2fa4a-105">A product can be sold in different units, such as "each," "pair," and "dozen."</span></span> <span data-ttu-id="2fa4a-106">Na matriz do Commerce, a unidade de medida de venda pode ser definida para um produto e mostrada em um site de comércio eletrônico.</span><span class="sxs-lookup"><span data-stu-id="2fa4a-106">In Commerce headquarters, the sell-by unit of measure can be defined for a product and shown on an e-commerce site.</span></span> <span data-ttu-id="2fa4a-107">Por exemplo, se um varejista vender um produto individualmente e em dúzias, as unidades de medida disponíveis poderão ser mostradas junto com outras informações do produto.</span><span class="sxs-lookup"><span data-stu-id="2fa4a-107">For example, if a retailer sells a product both individually and in dozens, the available units of measure can be shown together with other product information.</span></span>

<span data-ttu-id="2fa4a-108">No exemplo da ilustração a seguir, uma unidade de medida de venda de **ea** (cada) foi configurada para um produto na matriz do Commerce.</span><span class="sxs-lookup"><span data-stu-id="2fa4a-108">In the example in the following illustration, a sell-by unit of measure of **ea** (each) has been configured for a product in Commerce headquarters.</span></span>

![Exemplo de um produto configurado com uma unidade de medida na matriz do Commerce](./media/Productunit-headquarters.PNG)

> [!NOTE]
> <span data-ttu-id="2fa4a-110">O suporte para a aplicação e a exibição da unidade de medida está disponível a partir do Commerce versão 10.0.19.</span><span class="sxs-lookup"><span data-stu-id="2fa4a-110">Support for applying and showing the unit of measure is available as of the Commerce version 10.0.19 release.</span></span>

## <a name="unit-of-measure-settings"></a><span data-ttu-id="2fa4a-111">Configurações de unidade de medida</span><span class="sxs-lookup"><span data-stu-id="2fa4a-111">Unit of measure settings</span></span>

<span data-ttu-id="2fa4a-112">As configurações de exibição de unidade de medida são definidas no construtor de sites do Commerce, em **Configurações do site \> Extensões \> Exibir unidade de medida de produtos**.</span><span class="sxs-lookup"><span data-stu-id="2fa4a-112">Unit of measure display settings are defined in Commerce site builder, at **Site settings \> Extensions \> Display unit of measure for products**.</span></span> <span data-ttu-id="2fa4a-113">Há três configurações com suporte:</span><span class="sxs-lookup"><span data-stu-id="2fa4a-113">There are three supported settings:</span></span>

- <span data-ttu-id="2fa4a-114">**Não exibir** – Quando esta configuração for selecionada, o site de comércio eletrônico não mostrará a unidade de medida do produto.</span><span class="sxs-lookup"><span data-stu-id="2fa4a-114">**Do not display** – When this setting is selected, the e-commerce site won't show the unit of measure for the product.</span></span> <span data-ttu-id="2fa4a-115">Esse é o comportamento padrão.</span><span class="sxs-lookup"><span data-stu-id="2fa4a-115">This behavior is the default behavior.</span></span>
- <span data-ttu-id="2fa4a-116">**Exibir na experiência de compra do produto** – Quando esta configuração for selecionada, a unidade de medida será mostrada nas páginas de detalhes do produto, carrinho, finalização da compra, histórico de ordens e detalhes da ordem.</span><span class="sxs-lookup"><span data-stu-id="2fa4a-116">**Display in the product buying experience** – When this setting is selected, the unit of measure is shown on product details, cart, checkout, order history, and order details pages.</span></span>
- <span data-ttu-id="2fa4a-117">**Exibir na experiência de navegação e compra do produto** – Quando esta configuração for selecionada, a unidade de medida será mostrada nas páginas de experiência de compra do produto e também durante a experiência de navegação do produto.</span><span class="sxs-lookup"><span data-stu-id="2fa4a-117">**Display in the product browsing and buying experience** – When this setting is selected, the unit of measure is shown on the product buying experience pages and also during the product browsing experience.</span></span> <span data-ttu-id="2fa4a-118">Como parte desse comportamento, as unidades de medida são mostradas nos resultados da pesquisa e nos módulos de coleção de produtos.</span><span class="sxs-lookup"><span data-stu-id="2fa4a-118">As part of this behavior, units of measure are shown in search results and product collection modules.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2fa4a-119">As configurações de exibição de unidade de medida estão disponíveis a partir do Commerce versão 10.0.19.</span><span class="sxs-lookup"><span data-stu-id="2fa4a-119">Unit of measure display settings are available as of the Commerce version 10.0.19 release.</span></span> <span data-ttu-id="2fa4a-120">Se estiver atualizando de uma versão mais antiga do Commerce, você deverá atualizar manualmente o arquivo appsettings.json.</span><span class="sxs-lookup"><span data-stu-id="2fa4a-120">If you're updating from an older version of Commerce, you must manually update the appsettings.json file.</span></span> <span data-ttu-id="2fa4a-121">Para obter instruções, consulte [SDK e atualizações da biblioteca de módulos](e-commerce-extensibility/sdk-updates.md#update-the-appsettingsjson-file).</span><span class="sxs-lookup"><span data-stu-id="2fa4a-121">For instructions, see [SDK and module library updates](e-commerce-extensibility/sdk-updates.md#update-the-appsettingsjson-file).</span></span>

## <a name="modules-that-use-unit-of-measure-settings"></a><span data-ttu-id="2fa4a-122">Módulos que usam configurações de unidade de medida</span><span class="sxs-lookup"><span data-stu-id="2fa4a-122">Modules that use unit of measure settings</span></span>

<span data-ttu-id="2fa4a-123">Os módulos que usam as configurações de unidade de medida incluem os módulos de caixa de compra, lista de desejos, carrinho, ícone de carrinho, contêiner de resultados da pesquisa, coleção de produtos, finalização da compra e detalhes da ordem.</span><span class="sxs-lookup"><span data-stu-id="2fa4a-123">Modules that use the unit of measure settings include the buy box, wishlist, cart, cart icon, search results container, product collection, checkout, and order details modules.</span></span>

<span data-ttu-id="2fa4a-124">No exemplo da ilustração a seguir, uma página de detalhes do produto (PDP) mostra a unidade de medida (**ea**) de um produto.</span><span class="sxs-lookup"><span data-stu-id="2fa4a-124">In the example in the following illustration, a product details page (PDP) shows the unit of measure (**ea**) for a product.</span></span>

![Exemplo de uma PDP que mostra a unidade de medida](./media/Productunit-PDP.png)

<span data-ttu-id="2fa4a-126">No exemplo da ilustração a seguir, um módulo de coleção de produtos mostra a unidade de medida (**ea**) de um produto.</span><span class="sxs-lookup"><span data-stu-id="2fa4a-126">In the example in the following illustration, a product collection module shows the unit of measure (**ea**) for a product.</span></span>

![Exemplo de um módulo de coleção de produtos que mostra a unidade de medida](./media/Productunit-productcollection.png)

## <a name="additional-resources"></a><span data-ttu-id="2fa4a-128">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="2fa4a-128">Additional resources</span></span>

[<span data-ttu-id="2fa4a-129">Visão geral da biblioteca de módulos</span><span class="sxs-lookup"><span data-stu-id="2fa4a-129">Module library overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="2fa4a-130">Módulo de carrinho</span><span class="sxs-lookup"><span data-stu-id="2fa4a-130">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="2fa4a-131">Módulo de caixa de compra</span><span class="sxs-lookup"><span data-stu-id="2fa4a-131">Buy box module</span></span>](add-buy-box.md)

[<span data-ttu-id="2fa4a-132">Páginas e módulos de gerenciamento de contas</span><span class="sxs-lookup"><span data-stu-id="2fa4a-132">Account management pages and modules</span></span>](account-management.md)

[<span data-ttu-id="2fa4a-133">SDK e atualizações da biblioteca de módulos</span><span class="sxs-lookup"><span data-stu-id="2fa4a-133">SDK and module library updates</span></span>](e-commerce-extensibility/sdk-updates.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
