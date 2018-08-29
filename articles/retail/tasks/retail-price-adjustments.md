--- 
title: "Criar ajustes de preço de varejo"
description: "Este procedimento orienta na criação de um ajuste de preço de varejo."
author: josaw1
manager: AnnBe
ms.date: 06/07/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations, Retail
ms.search.region: Global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 5098fb3339403b6f2779dfe3bb7ef5c4ca78051f
ms.openlocfilehash: 6dd4e12008838460c0bb0ade907ea78d06c80fed
ms.contentlocale: pt-br
ms.lasthandoff: 08/09/2018

---
# <a name="create-retail-price-adjustments"></a><span data-ttu-id="a9963-103">Criar ajustes de preço de varejo</span><span class="sxs-lookup"><span data-stu-id="a9963-103">Create retail price adjustments</span></span>

[!include [task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="a9963-104">Este procedimento orienta na criação de um ajuste de preço de varejo.</span><span class="sxs-lookup"><span data-stu-id="a9963-104">This procedure will walk through creating a retail price adjustment.</span></span> <span data-ttu-id="a9963-105">Um ajuste de preço de varejo pode definir o preço de venda de um item diretamente ou modificar o preço base de venda ou o preço de venda do contrato comercial.</span><span class="sxs-lookup"><span data-stu-id="a9963-105">A retail price adjustment can set an item's sale price directly, or modify its base sale price or trade agreement sale price.</span></span> <span data-ttu-id="a9963-106">Este procedimento usa a empresa de dados de demonstração USRT.</span><span class="sxs-lookup"><span data-stu-id="a9963-106">This procedure uses the USRT demo data company.</span></span>

1. <span data-ttu-id="a9963-107">Clique em Gerenciamento de preços e descontos.</span><span class="sxs-lookup"><span data-stu-id="a9963-107">Click Pricing and discount management.</span></span>
2. <span data-ttu-id="a9963-108">Clique na guia Ajustes de preço.</span><span class="sxs-lookup"><span data-stu-id="a9963-108">Click the Price adjustments tab.</span></span>
3. <span data-ttu-id="a9963-109">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="a9963-109">Click New.</span></span>
    * <span data-ttu-id="a9963-110">Aqui você pode criar todas as regras de preços e descontos mais comumente usadas, incluindo descontos de varejo, ajustes de preço, diários de contratos comerciais e regras de preços de categoria.</span><span class="sxs-lookup"><span data-stu-id="a9963-110">From here you can create all of the most commonly used price and discount rules, including retail discounts, price adjustments, trade agreement journals, and category pricing rules.</span></span>  
4. <span data-ttu-id="a9963-111">Clique em Ajuste de preço.</span><span class="sxs-lookup"><span data-stu-id="a9963-111">Click Price adjustment.</span></span>
5. <span data-ttu-id="a9963-112">No campo Nome, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="a9963-112">In the Name field, type a value.</span></span>
6. <span data-ttu-id="a9963-113">Expandir a seção Linhas.</span><span class="sxs-lookup"><span data-stu-id="a9963-113">Expand the Lines section.</span></span>
7. <span data-ttu-id="a9963-114">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="a9963-114">Click Add.</span></span>
    * <span data-ttu-id="a9963-115">Neste exemplo, insira '81126' no campo Produto.</span><span class="sxs-lookup"><span data-stu-id="a9963-115">For this example, enter '81126' in the Product field.</span></span>    <span data-ttu-id="a9963-116">Em seguida, insira '10,0' no campo Porcentagem de desconto.</span><span class="sxs-lookup"><span data-stu-id="a9963-116">Then, enter '10.0' in the Discount percentage field.</span></span>  
    * <span data-ttu-id="a9963-117">Um ajuste de preço do tipo porcentagem de desconto reduzirá um preço base de venda ou um preço de venda do contrato comercial.</span><span class="sxs-lookup"><span data-stu-id="a9963-117">A discount percentage type price adjustment will reduce a base sales price or trade agreement sales price.</span></span>  
8. <span data-ttu-id="a9963-118">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="a9963-118">Click Add.</span></span>
    * <span data-ttu-id="a9963-119">Para este exemplo, insira '81125' no campo Produto.</span><span class="sxs-lookup"><span data-stu-id="a9963-119">For this example, enter '81125' in the Product field.</span></span>    <span data-ttu-id="a9963-120">Depois, selecione 'Valor do desconto à vista' no campo Método de desconto.</span><span class="sxs-lookup"><span data-stu-id="a9963-120">Then, select 'Cash discount amount' in the Discount method field.</span></span>    <span data-ttu-id="a9963-121">Por último, insira '5,0' no campo Valor do desconto à vista.</span><span class="sxs-lookup"><span data-stu-id="a9963-121">Finally, enter '5.0' in the Cash discount amount field.</span></span>  
    * <span data-ttu-id="a9963-122">Um tipo de desconto de valor de desconto à vista é um valor deduzido de um preço base ou de um preço do contrato comercial.</span><span class="sxs-lookup"><span data-stu-id="a9963-122">A Cash discount amount discount type is an amount taken off from a base price or a trade agreement price.</span></span>  
9. <span data-ttu-id="a9963-123">Clique em Grupos de preços.</span><span class="sxs-lookup"><span data-stu-id="a9963-123">Click Price groups.</span></span>
    * <span data-ttu-id="a9963-124">Selecione 'RP-Houston' no campo Grupo de preços.</span><span class="sxs-lookup"><span data-stu-id="a9963-124">Select 'RP-Houston' in the Price group field.</span></span>  
    * <span data-ttu-id="a9963-125">Isso associará o ajuste de preço à loja Houston.</span><span class="sxs-lookup"><span data-stu-id="a9963-125">This will associate the Price adjustment to the Houston store.</span></span>  
10. <span data-ttu-id="a9963-126">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="a9963-126">Click Save.</span></span>
11. <span data-ttu-id="a9963-127">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="a9963-127">Close the page.</span></span>
12. <span data-ttu-id="a9963-128">No campo Status, selecione 'Habilitado'.</span><span class="sxs-lookup"><span data-stu-id="a9963-128">In the Status field, select 'Enabled'.</span></span>
13. <span data-ttu-id="a9963-129">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="a9963-129">Click Save.</span></span>
14. <span data-ttu-id="a9963-130">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="a9963-130">Close the page.</span></span>
15. <span data-ttu-id="a9963-131">Atualize a página.</span><span class="sxs-lookup"><span data-stu-id="a9963-131">Refresh the page.</span></span>


