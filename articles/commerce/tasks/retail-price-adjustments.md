---
title: Ajustes de preço de varejo
description: Este procedimento orienta na criação de um ajuste de preço comercial.
author: josaw1
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, RetailDiscountPricingWorkspace, RetailPeriodicDiscount, RetailDiscountPriceGroup
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 7443f69473c0aad478d47f80f284b1156bad9c24
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4962976"
---
# <a name="retail-price-adjustments"></a><span data-ttu-id="27bb1-103">Ajustes de preço de varejo</span><span class="sxs-lookup"><span data-stu-id="27bb1-103">Retail price adjustments</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="27bb1-104">Este procedimento orienta na criação de um ajuste de preço comercial.</span><span class="sxs-lookup"><span data-stu-id="27bb1-104">This procedure will walk through creating a commerce price adjustment.</span></span> <span data-ttu-id="27bb1-105">Um ajuste de preço pode definir o preço de venda de um item diretamente ou modificar o preço base de venda ou o preço de venda do contrato comercial.</span><span class="sxs-lookup"><span data-stu-id="27bb1-105">A price adjustment can set an item's sale price directly, or modify its base sale price or trade agreement sale price.</span></span> <span data-ttu-id="27bb1-106">Este procedimento usa a empresa de dados de demonstração USRT.</span><span class="sxs-lookup"><span data-stu-id="27bb1-106">This procedure uses the USRT demo data company.</span></span>

1. <span data-ttu-id="27bb1-107">Clique em Gerenciamento de preços e descontos.</span><span class="sxs-lookup"><span data-stu-id="27bb1-107">Click Pricing and discount management.</span></span>
2. <span data-ttu-id="27bb1-108">Clique na guia Ajustes de preço.</span><span class="sxs-lookup"><span data-stu-id="27bb1-108">Click the Price adjustments tab.</span></span>
3. <span data-ttu-id="27bb1-109">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="27bb1-109">Click New.</span></span>
    * <span data-ttu-id="27bb1-110">Aqui você pode criar todas as regras de preços e descontos mais comumente usadas, incluindo descontos, ajustes de preço, diários de contratos comerciais e regras de preços de categoria.</span><span class="sxs-lookup"><span data-stu-id="27bb1-110">From here you can create all of the most commonly used price and discount rules, including discounts, price adjustments, trade agreement journals, and category pricing rules.</span></span>  
4. <span data-ttu-id="27bb1-111">Clique em Ajuste de preço.</span><span class="sxs-lookup"><span data-stu-id="27bb1-111">Click Price adjustment.</span></span>
5. <span data-ttu-id="27bb1-112">No campo Nome, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="27bb1-112">In the Name field, type a value.</span></span>
6. <span data-ttu-id="27bb1-113">Expandir a seção Linhas.</span><span class="sxs-lookup"><span data-stu-id="27bb1-113">Expand the Lines section.</span></span>
7. <span data-ttu-id="27bb1-114">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="27bb1-114">Click Add.</span></span>
    * <span data-ttu-id="27bb1-115">Neste exemplo, insira '81126' no campo Produto.</span><span class="sxs-lookup"><span data-stu-id="27bb1-115">For this example, enter '81126' in the Product field.</span></span> <span data-ttu-id="27bb1-116">Em seguida, insira '10,0' no campo Porcentagem de desconto.</span><span class="sxs-lookup"><span data-stu-id="27bb1-116">Then, enter '10.0' in the Discount percentage field.</span></span>  
    * <span data-ttu-id="27bb1-117">Um ajuste de preço do tipo porcentagem de desconto reduzirá um preço base de venda ou um preço de venda do contrato comercial.</span><span class="sxs-lookup"><span data-stu-id="27bb1-117">A discount percentage type price adjustment will reduce a base sales price or trade agreement sales price.</span></span>  
8. <span data-ttu-id="27bb1-118">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="27bb1-118">Click Add.</span></span>
    * <span data-ttu-id="27bb1-119">Para este exemplo, insira '81125' no campo Produto.</span><span class="sxs-lookup"><span data-stu-id="27bb1-119">For this example, enter '81125' in the Product field.</span></span> <span data-ttu-id="27bb1-120">Depois, selecione 'Valor do desconto à vista' no campo Método de desconto.</span><span class="sxs-lookup"><span data-stu-id="27bb1-120">Then, select 'Cash discount amount' in the Discount method field.</span></span>    <span data-ttu-id="27bb1-121">Por último, insira '5,0' no campo Valor do desconto à vista.</span><span class="sxs-lookup"><span data-stu-id="27bb1-121">Finally, enter '5.0' in the Cash discount amount field.</span></span>  
    * <span data-ttu-id="27bb1-122">Um tipo de desconto de valor de desconto à vista é um valor deduzido de um preço base ou de um preço do contrato comercial.</span><span class="sxs-lookup"><span data-stu-id="27bb1-122">A Cash discount amount discount type is an amount taken off from a base price or a trade agreement price.</span></span>  
9. <span data-ttu-id="27bb1-123">Clique em Grupos de preços.</span><span class="sxs-lookup"><span data-stu-id="27bb1-123">Click Price groups.</span></span>
    * <span data-ttu-id="27bb1-124">Selecione 'RP-Houston' no campo Grupo de preços.</span><span class="sxs-lookup"><span data-stu-id="27bb1-124">Select 'RP-Houston' in the Price group field.</span></span>  
    * <span data-ttu-id="27bb1-125">Isso associará o ajuste de preço à loja Houston.</span><span class="sxs-lookup"><span data-stu-id="27bb1-125">This will associate the Price adjustment to the Houston store.</span></span>  
10. <span data-ttu-id="27bb1-126">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="27bb1-126">Click Save.</span></span>
11. <span data-ttu-id="27bb1-127">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="27bb1-127">Close the page.</span></span>
12. <span data-ttu-id="27bb1-128">No campo Status, selecione 'Habilitado'.</span><span class="sxs-lookup"><span data-stu-id="27bb1-128">In the Status field, select 'Enabled'.</span></span>
13. <span data-ttu-id="27bb1-129">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="27bb1-129">Click Save.</span></span>
14. <span data-ttu-id="27bb1-130">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="27bb1-130">Close the page.</span></span>
15. <span data-ttu-id="27bb1-131">Atualize a página.</span><span class="sxs-lookup"><span data-stu-id="27bb1-131">Refresh the page.</span></span>

