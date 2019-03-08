---
title: Fontes comuns de variações de produção
description: Este artigo aborda várias fontes típicas de cada tipo de variação de produção.
author: AndersGirke
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventCostTrans
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 79753
ms.assetid: 14ac7db4-fb40-43c1-bb0d-1d51fc91d24f
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: mguada
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 50f8cd7904e1d32175edd321fbd6533e985fb324
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2019
ms.locfileid: "308681"
---
# <a name="common-sources-of-production-variances"></a><span data-ttu-id="d303b-103">Fontes comuns de variações de produção</span><span class="sxs-lookup"><span data-stu-id="d303b-103">Common sources of production variances</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="d303b-104">Este artigo aborda várias fontes típicas de cada tipo de variação de produção.</span><span class="sxs-lookup"><span data-stu-id="d303b-104">This article explains various typical sources of each type of production variance.</span></span> 

<span data-ttu-id="d303b-105">Veja a seguir algumas origens típicas de uma variação **tamanho de lote**:</span><span class="sxs-lookup"><span data-stu-id="d303b-105">Here are some typical sources of a **lot size** variance:</span></span>

-   <span data-ttu-id="d303b-106">A quantidade de bens para uma ordem de produção difere da quantidade de cálculo usada no cálculo do custo padrão.</span><span class="sxs-lookup"><span data-stu-id="d303b-106">The good quantity for a production order differs from the calculation quantity that is used in the standard cost calculation.</span></span> <span data-ttu-id="d303b-107">A quantidade dá a base para amortizar custos constantes.</span><span class="sxs-lookup"><span data-stu-id="d303b-107">The quantity provides the basis for amortizing constant costs.</span></span>
-   <span data-ttu-id="d303b-108">O valor dos custos constantes na ordem de produção difere dos custos constantes usados no cálculo do custo padrão.</span><span class="sxs-lookup"><span data-stu-id="d303b-108">The value of constant costs on the production order differs from the constant costs that are used in the standard cost calculation.</span></span> <span data-ttu-id="d303b-109">Os custos constantes na ordem de produção podem ser diferentes por muitos motivos.</span><span class="sxs-lookup"><span data-stu-id="d303b-109">The constant costs on the production order can differ for several reasons.</span></span> <span data-ttu-id="d303b-110">Por exemplo, eles podem refletir os seguintes fatores:</span><span class="sxs-lookup"><span data-stu-id="d303b-110">For example, the constant costs might reflect the following factors:</span></span>
    -   <span data-ttu-id="d303b-111">Alterações manuais à lista de materiais (BOM) de produção ou roteiro</span><span class="sxs-lookup"><span data-stu-id="d303b-111">Manual changes to the production bill of materials (BOM) or route</span></span>
    -   <span data-ttu-id="d303b-112">A seleção de uma versão da BOM ou do roteiro diferente quando você cria a ordem de produção</span><span class="sxs-lookup"><span data-stu-id="d303b-112">The selection of a different BOM version or route version when you create the production order</span></span>
    -   <span data-ttu-id="d303b-113">Alterações de engenharia planejadas para a versão da BOM ou de roteiro atribuída ao item</span><span class="sxs-lookup"><span data-stu-id="d303b-113">Planned engineering changes to the BOM version or route version that is assigned to the item</span></span>

<span data-ttu-id="d303b-114">Veja a seguir algumas origens típicas de uma variação **preço de produção**:</span><span class="sxs-lookup"><span data-stu-id="d303b-114">Here are some typical sources of a **production price** variance:</span></span>

-   <span data-ttu-id="d303b-115">A categoria de custo (e o preço da categoria de custo) para o consumo informado de uma operação de roteiro é diferente da categoria de custo usada no cálculo do custo padrão.</span><span class="sxs-lookup"><span data-stu-id="d303b-115">The cost category (and cost category price) for the reported consumption of a routing operation differs from the cost category that is used in standard cost calculation.</span></span>
-   <span data-ttu-id="d303b-116">O custo ativo do preço da categoria de custo é diferente do preço da categoria de custo usado no cálculo do custo padrão.</span><span class="sxs-lookup"><span data-stu-id="d303b-116">The active cost for the cost category price differs from the cost category price that is used in standard cost calculation.</span></span>

<span data-ttu-id="d303b-117">Veja a seguir algumas origens típicas de uma variação **quantidade de produção**:</span><span class="sxs-lookup"><span data-stu-id="d303b-117">Here are some typical sources of a **production quantity** variance:</span></span>

-   <span data-ttu-id="d303b-118">Emitir a mais ou a menos um componente de material.</span><span class="sxs-lookup"><span data-stu-id="d303b-118">You over-issue or under-issue a material component.</span></span>
-   <span data-ttu-id="d303b-119">Relatar uma operação de roteiro a mais ou a menos.</span><span class="sxs-lookup"><span data-stu-id="d303b-119">You over-report or under-report the time for a routing operation.</span></span>
-   <span data-ttu-id="d303b-120">Você recebe a mais ou a menos a quantidade de bens do item principal, relativa a quantidade do pedido.</span><span class="sxs-lookup"><span data-stu-id="d303b-120">You over-receive or under-receive the good quantity of the parent item, relative to the order quantity.</span></span> <span data-ttu-id="d303b-121">No entanto, você emite componentes e relata operações completamente, com base na quantidade do pedido para a ordem de produção.</span><span class="sxs-lookup"><span data-stu-id="d303b-121">However, you issue components and report operations completely, based on the order quantity for the production order.</span></span>

<span data-ttu-id="d303b-122">Veja a seguir algumas origens típicas de uma variação **substituição de produção**:</span><span class="sxs-lookup"><span data-stu-id="d303b-122">Here are some typical sources of a **production substitution** variance:</span></span>

-   <span data-ttu-id="d303b-123">Você emite um componente de material que não está na BOM de produção.</span><span class="sxs-lookup"><span data-stu-id="d303b-123">You issue a material component that isn't on the production BOM.</span></span>
-   <span data-ttu-id="d303b-124">Você adiciona manualmente um componente à BOM de produção e relata o componente como consumido.</span><span class="sxs-lookup"><span data-stu-id="d303b-124">You manually add a component to the production BOM and report that component as consumed.</span></span>
-   <span data-ttu-id="d303b-125">Você relatar um item como consumido, mas não o adiciona manualmente à BOM de produção.</span><span class="sxs-lookup"><span data-stu-id="d303b-125">You report an item as consumed but don't manually add it to the production BOM.</span></span>
-   <span data-ttu-id="d303b-126">Você adicionar manualmente uma operação à BOM de roteiro de produção e relata aquela operação como consumida.</span><span class="sxs-lookup"><span data-stu-id="d303b-126">You manually add an operation to the production route and report that operation as consumed.</span></span>
-   <span data-ttu-id="d303b-127">Quando você cria a ordem de produção, você seleciona uma versão da BOM diferente daquela usada no cálculo do custo padrão.</span><span class="sxs-lookup"><span data-stu-id="d303b-127">When you create the production order, you select a BOM version that differs from the BOM version that is used in the standard cost calculation.</span></span>
-   <span data-ttu-id="d303b-128">Quando você cria a ordem de produção, você seleciona a versão de roteiro diferente daquela usada no cálculo do custo padrão.</span><span class="sxs-lookup"><span data-stu-id="d303b-128">When you create the production order, you select a route version that differs from the route version that is used in the standard cost calculation.</span></span>




