---
title: "Preparar para manter custos padrão para itens fabricados"
description: "Este tópico descreve as estapas de preparação para manter custos para itens fabricados."
author: AndersGirke
manager: AnnBe
ms.date: 01/17/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: InventStdCostConv
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.industry: Manufacturing
ms.author: aevengir
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 72d4ff5e1311005d3bf43a13e28208cd9b3d1457
ms.openlocfilehash: c1942d1f2c8eeb05a6cbaddd2d7911a93b7e05a1
ms.contentlocale: pt-br
ms.lasthandoff: 03/08/2018

---


# <a name="prepare-to-maintain-standard-costs-for-manufactured-items"></a><span data-ttu-id="9a98c-103">Preparar para manter custos padrão para itens fabricados</span><span class="sxs-lookup"><span data-stu-id="9a98c-103">Prepare to maintain standard costs for manufactured items</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="9a98c-104">Este tópico descreve as estapas de preparação para manter custos para itens fabricados.</span><span class="sxs-lookup"><span data-stu-id="9a98c-104">This topic describes the steps for preparing to maintain costs for manufactured items.</span></span> <span data-ttu-id="9a98c-105">As etapas para itens fabricados diferem levemente das etapas para itens comprados.</span><span class="sxs-lookup"><span data-stu-id="9a98c-105">The steps for manufactured items differ slightly from the steps for purchased items.</span></span>

<span data-ttu-id="9a98c-106">As diretivas atribuídas aos itens fabricados podem afetar os cálculos de custo para os itens pai fabricados.</span><span class="sxs-lookup"><span data-stu-id="9a98c-106">Policies that are assigned to manufactured items can affect the cost calculations for the parent manufactured items.</span></span> <span data-ttu-id="9a98c-107">Para se preparar para manter custos para itens fabricados, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="9a98c-107">To prepare to maintain costs for manufactured items, follow these steps.</span></span>

1. <span data-ttu-id="9a98c-108">Atribua um grupo de modelo de item ao item fabricado.</span><span class="sxs-lookup"><span data-stu-id="9a98c-108">Assign an item model group to the manufactured item.</span></span> 

   <span data-ttu-id="9a98c-109">O grupo de modelo de item identifica que custos padrão serão usados.</span><span class="sxs-lookup"><span data-stu-id="9a98c-109">The item model group identifies that standard costs will be used.</span></span>

2. <span data-ttu-id="9a98c-110">Atribua um grupo de itens ao item fabricado.</span><span class="sxs-lookup"><span data-stu-id="9a98c-110">Assign an item group to the manufactured item.</span></span> 

   <span data-ttu-id="9a98c-111">O grupo de itens contém contas contábeis que se aplicam ao item fabricado.</span><span class="sxs-lookup"><span data-stu-id="9a98c-111">The item group contains ledger accounts that apply to the manufactured item.</span></span> <span data-ttu-id="9a98c-112">As contas contábeis para um item fabricado que tem um modelo de estoque de custo padrão incluem diversas variações de produção, a variação de alteração de custo e a reavaliação de custo de estoque.</span><span class="sxs-lookup"><span data-stu-id="9a98c-112">The ledger accounts for a manufactured item that has a standard cost inventory model include several production variances, the cost change variance, and the inventory cost revaluation.</span></span>

3. <span data-ttu-id="9a98c-113">Atribua a unidade de medida do item para o item.</span><span class="sxs-lookup"><span data-stu-id="9a98c-113">Assign the inventory unit of measure to the item.</span></span> 

   <span data-ttu-id="9a98c-114">Os custos do item são sempre expressos na unidade de medida de estoque do item.</span><span class="sxs-lookup"><span data-stu-id="9a98c-114">The item's costs are always expressed in the item's inventory unit of measure.</span></span>

4. <span data-ttu-id="9a98c-115">Não atribua um grupo de custos ao item fabricado, a não ser que ele seja tratado como um item comprado.</span><span class="sxs-lookup"><span data-stu-id="9a98c-115">Don't assign a cost group to the manufactured item unless the item will be treated as a purchased item.</span></span>

5. <span data-ttu-id="9a98c-116">Atribua um grupo de cálculo de BOM (lista de materiais) ao item fabricado.</span><span class="sxs-lookup"><span data-stu-id="9a98c-116">Assign a bill of materials (BOM) calculation group to the manufactured item.</span></span> 

   <span data-ttu-id="9a98c-117">O grupo de cálculo de BOM do item define as condições de aviso aplicáveis.</span><span class="sxs-lookup"><span data-stu-id="9a98c-117">The item's BOM calculation group defines warning conditions that apply.</span></span> <span data-ttu-id="9a98c-118">Dessa maneira, quando um cálculo de BOM for feito, mensagens de aviso sobre possíveis fontes de erros de cálculo poderão ser geradas.</span><span class="sxs-lookup"><span data-stu-id="9a98c-118">In that way, when a BOM calculation is done, warning messages can be generated about possible sources of calculation errors.</span></span> <span data-ttu-id="9a98c-119">Por exemplo, uma mensagem de aviso pode identificar quando uma BOM ativa ou um roteiro não existe.</span><span class="sxs-lookup"><span data-stu-id="9a98c-119">For example, a warning message can identify when an active BOM or route doesn't exist.</span></span> <span data-ttu-id="9a98c-120">O grupo de cálculo de BOM contém uma diretiva para interromper o detalhamento que indica quando um item fabricado deve ser tratado como um item comprado.</span><span class="sxs-lookup"><span data-stu-id="9a98c-120">The BOM calculation group contains a stop explosion policy that indicates when a manufactured item should be treated as a purchased item.</span></span>

6. <span data-ttu-id="9a98c-121">Se o item fabricado tiver custos constantes, atribua uma quantidade de ordem padrão a ele.</span><span class="sxs-lookup"><span data-stu-id="9a98c-121">If the manufactured item has constant costs, assign a standard order quantity to it.</span></span> 

   <span data-ttu-id="9a98c-122">A quantidade de ordem padrão é um tamanho de lote contábil para amortização dos custos constantes.</span><span class="sxs-lookup"><span data-stu-id="9a98c-122">The standard order quantity is an accounting lot size for amortizing constant costs.</span></span> <span data-ttu-id="9a98c-123">Exemplos de custos constantes incluem os tempos de configuração em operações bancárias e uma quantidade constante de componentes na BOM.</span><span class="sxs-lookup"><span data-stu-id="9a98c-123">Examples of constant costs include setup times in routing operations and a constant component quantity in the BOM.</span></span>

7. <span data-ttu-id="9a98c-124">Defina o BOM para o item fabricado.</span><span class="sxs-lookup"><span data-stu-id="9a98c-124">Define the BOM for the manufactured item.</span></span> 

   <span data-ttu-id="9a98c-125">Uma ou mais versões de BOM podem ser definidas para o item fabricado.</span><span class="sxs-lookup"><span data-stu-id="9a98c-125">One or more BOM versions can be defined for the manufactured item.</span></span> <span data-ttu-id="9a98c-126">Verifique se as versões desejadas foram marcadas como aprovadas e ativas, além de terem as datas efetivas que você deseja.</span><span class="sxs-lookup"><span data-stu-id="9a98c-126">Verify that the versions that you want have been marked as approved and active, and that they have the effective dates that you want.</span></span> <span data-ttu-id="9a98c-127">A versão de BOM pode abranger empresas ou ser específica para sites.</span><span class="sxs-lookup"><span data-stu-id="9a98c-127">The BOM version can be company-wide or site-specific.</span></span>

8. <span data-ttu-id="9a98c-128">Defina o roteiro para o item fabricado.</span><span class="sxs-lookup"><span data-stu-id="9a98c-128">Define the routing for the manufactured item.</span></span> 

   <span data-ttu-id="9a98c-129">Uma ou mais versões de roteiro podem ser definidas para o item fabricado.</span><span class="sxs-lookup"><span data-stu-id="9a98c-129">One or more route versions can be defined for the manufactured item.</span></span> <span data-ttu-id="9a98c-130">Verifique se as versões desejadas foram marcadas como aprovadas e ativas, além de terem as datas efetivas que você deseja.</span><span class="sxs-lookup"><span data-stu-id="9a98c-130">Verify that the versions that you want have been marked as approved and active, and that they have the effective dates that you want.</span></span> <span data-ttu-id="9a98c-131">A versão de roteiro deve ser específica para sites.</span><span class="sxs-lookup"><span data-stu-id="9a98c-131">The route version must be site-specific.</span></span>

<span data-ttu-id="9a98c-132">Se desejar usar informações de roteiro para avaliação de custo, etapas de preparação adicionais serão necessárias.</span><span class="sxs-lookup"><span data-stu-id="9a98c-132">If you want to use routing information for costing purposes, additional preparation steps are required.</span></span> <span data-ttu-id="9a98c-133">Por exemplo, as categorias de custo que são atribuídas às operações de roteiro devem estar corretas e completas.</span><span class="sxs-lookup"><span data-stu-id="9a98c-133">For example, the cost categories that are assigned to routing operations must be correct and completed.</span></span>

<a name="related-topics"></a><span data-ttu-id="9a98c-134">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="9a98c-134">Related topics</span></span>
--------

[<span data-ttu-id="9a98c-135">Amortizar custos constantes para um item fabricado</span><span class="sxs-lookup"><span data-stu-id="9a98c-135">Amortize constant costs for a manufactured item</span></span>](amortize-constant-costs-manufactured-item.md)

[<span data-ttu-id="9a98c-136">Configurar produtos que podem ser produzidos ou obtidos</span><span class="sxs-lookup"><span data-stu-id="9a98c-136">Set up products that can be produced or procured</span></span>](manufactured-items-treated-as-purchased-items.md)


