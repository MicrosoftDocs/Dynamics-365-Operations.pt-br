---
title: "Estimativa de custo da ordem de produção"
description: "Este artigo fornece informações sobre a previsão de custo de produção. A estimativa de custo de produção fornece os custos projetados de consumo de capacidade e de material para produzir um item na quantidade da ordem de produção planejada."
author: AndersGirke
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: BOMCalcTrans, InventCostTrans, ProdCalcTrans, ProdTableJour, ProdTableListPage
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 80633
ms.assetid: b4625d10-c852-4fda-b718-79df458de0d4
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: mguada
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a61761a5c9d98befd67682e1790af5377b7a55e1
ms.openlocfilehash: 21656a5d58e9566731c25cb09dbccc975bef5fb0
ms.contentlocale: pt-br
ms.lasthandoff: 10/13/2017

---

# <a name="production-order-cost-estimation"></a><span data-ttu-id="92544-104">Estimativa de custo da ordem de produção</span><span class="sxs-lookup"><span data-stu-id="92544-104">Production order cost estimation</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="92544-105">Este artigo fornece informações sobre a previsão de custo de produção.</span><span class="sxs-lookup"><span data-stu-id="92544-105">This article provides information about production cost estimation.</span></span> <span data-ttu-id="92544-106">A estimativa de custo de produção fornece os custos projetados de consumo de capacidade e de material para produzir um item na quantidade da ordem de produção planejada.</span><span class="sxs-lookup"><span data-stu-id="92544-106">Production cost estimation provides the projected material and capacity consumption costs of producing an item in the planned production order quantity.</span></span> 

<span data-ttu-id="92544-107">Depois de criar uma ordem de produção, você deve estimar o custo de produção.</span><span class="sxs-lookup"><span data-stu-id="92544-107">After you create a production order, you must estimate production costs.</span></span> <span data-ttu-id="92544-108">Sua função é estimar o consumo de item e roteiro para o processo de produção, pois essas estimativas formam a base dos processos de produção e planejamento subsequente.</span><span class="sxs-lookup"><span data-stu-id="92544-108">The purpose is to estimate item and route consumption for the production process, because these estimates are used as the basis for subsequent scheduling and production processes.</span></span>

## <a name="production-cost-estimation"></a><span data-ttu-id="92544-109">Estimativa de custo de produção</span><span class="sxs-lookup"><span data-stu-id="92544-109">Production cost estimation</span></span>
<span data-ttu-id="92544-110">As estimativas dos custos de produção são baseadas nas seguintes informações:</span><span class="sxs-lookup"><span data-stu-id="92544-110">Estimates of production costs are based on the following information:</span></span>

-   <span data-ttu-id="92544-111">A quantidade na ordem de produção</span><span class="sxs-lookup"><span data-stu-id="92544-111">The quantity on the production order</span></span>
-   <span data-ttu-id="92544-112">Os componentes na lista de materiais (BOMs) de produção</span><span class="sxs-lookup"><span data-stu-id="92544-112">The components on the production bills of materials (BOMs)</span></span>
-   <span data-ttu-id="92544-113">As operações de roteiro na rota de produção</span><span class="sxs-lookup"><span data-stu-id="92544-113">The routing operations in the production route</span></span>
-   <span data-ttu-id="92544-114">Os custos indiretos que se aplicam aos componentes e operações</span><span class="sxs-lookup"><span data-stu-id="92544-114">The indirect costs that apply to the components and operations</span></span>
-   <span data-ttu-id="92544-115">Os dados de custo ativos como a data de cálculo</span><span class="sxs-lookup"><span data-stu-id="92544-115">The active cost data as of the calculation date</span></span>

<span data-ttu-id="92544-116">Se houver um item de linha fantasma nas BOMs de produção, os cálculos refletirão os componentes do fantasma e as operações de roteiro.</span><span class="sxs-lookup"><span data-stu-id="92544-116">If there is a phantom line item on the production BOMs, the calculations reflect the phantom’s components and route operations.</span></span> <span data-ttu-id="92544-117">Você pode usar a tarefa de estimativa para recalcular os custos estimados para que eles reflitam a informação atualizada.</span><span class="sxs-lookup"><span data-stu-id="92544-117">You can use the estimation task to recalculate estimated costs so that they reflect updated information.</span></span> <span data-ttu-id="92544-118">Por exemplo, as informações atualizadas podem ser alterações na quantidade da ordem de produção, os componentes nas BOMs de produção, as operações de roteamento no roteiro de produção, os custos indiretos aplicados a esses componentes e operações ou os dados de custo ativos a partir da data do novo cálculo.</span><span class="sxs-lookup"><span data-stu-id="92544-118">For example, the updated information might be changes to the quantity on the production order, the components on the production BOMs, the routing operations in the production route, the indirect costs that apply to these components and operations, or the active cost data as of the recalculation date.</span></span> <span data-ttu-id="92544-119">Os cálculos do custo estimado também sugerem um preço de venda para o item de produção com base em uma abordagem de custo mais marcação.</span><span class="sxs-lookup"><span data-stu-id="92544-119">The calculations of estimated cost also suggest a sales price for the production item, based on a cost-plus-markup approach.</span></span> <span data-ttu-id="92544-120">Os cálculos de custo estimados podem, opcionalmente, ser aplicados para ordens de referência que reflitam ordens de produção que são vinculados a ordem de produção.</span><span class="sxs-lookup"><span data-stu-id="92544-120">The calculations of estimated cost can optionally apply to reference orders that reflect other production orders that are linked to the production order.</span></span>

## <a name="view-the-estimated-costs"></a><span data-ttu-id="92544-121">Exiba os custos previstos</span><span class="sxs-lookup"><span data-stu-id="92544-121">View the estimated costs</span></span>
<span data-ttu-id="92544-122">Depois de executar a estimativa, você poderá ver os resultados na página **Cálculo de preço**.</span><span class="sxs-lookup"><span data-stu-id="92544-122">After you run estimation, you can view the results on the **Price calculation** page.</span></span> <span data-ttu-id="92544-123">A estimativa calcula os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="92544-123">The estimation calculates the following values:</span></span>

-   <span data-ttu-id="92544-124">**Custo de produção** – O custo de produção é a linha superior da estimativa.</span><span class="sxs-lookup"><span data-stu-id="92544-124">**Production cost** – The production cost is the top line of the estimate.</span></span> <span data-ttu-id="92544-125">Ela mostra o custo completo de executar a ordem de produção e o preço de venda total para a produção.</span><span class="sxs-lookup"><span data-stu-id="92544-125">It shows the complete cost of running the production order and the total sales price for the production.</span></span> <span data-ttu-id="92544-126">É a soma de todas as linhas de custo na estimativa.</span><span class="sxs-lookup"><span data-stu-id="92544-126">It's the sum of all the cost lines on the estimate.</span></span>
-   <span data-ttu-id="92544-127">**Custos de roteiro ou do recurso** – Os custos de roteiro ou do recurso são os custos das operações de produção.</span><span class="sxs-lookup"><span data-stu-id="92544-127">**Route or resource costs** – Route or resource costs are the costs for the production operations.</span></span> <span data-ttu-id="92544-128">Incluem os custos dos elementos como o tempo de preparação, o tempo de execução, e custos gerais indiretos.</span><span class="sxs-lookup"><span data-stu-id="92544-128">They include the cost of elements such as setup time, run time, and overhead.</span></span>
-   <span data-ttu-id="92544-129">**Custos de material** – Custos de material são os custos e os preços dos componentes da lista de materiais (BOM) necessários para produzir o item.</span><span class="sxs-lookup"><span data-stu-id="92544-129">**Material costs** – Material costs are the costs and prices of the BOM components that are required in order to produce the item.</span></span> <span data-ttu-id="92544-130">Eles foram estabelecidos e inseridos no sistema previamente.</span><span class="sxs-lookup"><span data-stu-id="92544-130">These costs have previously been established and entered into the system.</span></span>

## <a name="other-uses-of-cost-estimation"></a><span data-ttu-id="92544-131">Outros usos de uma estimativa de custo</span><span class="sxs-lookup"><span data-stu-id="92544-131">Other uses of cost estimation</span></span>
<span data-ttu-id="92544-132">Uma estimativa de custo também fornece as seguintes informações:</span><span class="sxs-lookup"><span data-stu-id="92544-132">A cost estimate also provides the following information:</span></span>

-   <span data-ttu-id="92544-133">Cotações de preço significativas</span><span class="sxs-lookup"><span data-stu-id="92544-133">Meaningful price quotations</span></span>
-   <span data-ttu-id="92544-134">Estimativas da lucratividade da ordem</span><span class="sxs-lookup"><span data-stu-id="92544-134">Estimates of the profitability of the order</span></span>
-   <span data-ttu-id="92544-135">Estimativas do uso de matéria-prima</span><span class="sxs-lookup"><span data-stu-id="92544-135">Estimates of raw material usage</span></span>
-   <span data-ttu-id="92544-136">Comparações das informações de custo de produções anteriores</span><span class="sxs-lookup"><span data-stu-id="92544-136">Comparisons of cost information from previous productions</span></span>
-   <span data-ttu-id="92544-137">Informações sobre orçamento e previsões</span><span class="sxs-lookup"><span data-stu-id="92544-137">Budget and forecasting information</span></span>
-   <span data-ttu-id="92544-138">Estimativas do tamanho de produção necessário para manter um determinado custo</span><span class="sxs-lookup"><span data-stu-id="92544-138">Estimates of the production size that is required in order to maintain a particular cost</span></span>





