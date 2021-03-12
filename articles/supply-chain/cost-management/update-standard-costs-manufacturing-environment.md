---
title: Atualizar custos padrão em um ambiente de fabricação
description: Este artigo fornece a orientação sobre como atualizar custos padrão em um ambiente de fabricação.
author: AndersGirke
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CostingVersion, InventStdCostConv
audience: Application User
ms.reviewer: kamaybac
ms.custom: 79663
ms.assetid: 3a7c3d13-8dbc-442d-a281-ac0ebe99ec83
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: mguada
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7bc203176967fbe6c20f4f687fe36fdcf3157b20
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4983816"
---
# <a name="update-standard-costs-in-a-manufacturing-environment"></a><span data-ttu-id="b54a3-103">Atualizar custos padrão em um ambiente de fabricação</span><span class="sxs-lookup"><span data-stu-id="b54a3-103">Update standard costs in a manufacturing environment</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b54a3-104">Este artigo fornece a orientação sobre como atualizar custos padrão em um ambiente de fabricação.</span><span class="sxs-lookup"><span data-stu-id="b54a3-104">This article provides guidance about how to update standard costs in a manufacturing environment.</span></span> 

<span data-ttu-id="b54a3-105">As atualização podem refletir novos itens, categorias de custo ou fórmulas de cálculo de custo indireto.</span><span class="sxs-lookup"><span data-stu-id="b54a3-105">Updates can reflect new items, cost categories, or indirect cost calculation formulas.</span></span> <span data-ttu-id="b54a3-106">Também podem refletir correções e alterações de custo.</span><span class="sxs-lookup"><span data-stu-id="b54a3-106">They can also reflect corrections and cost changes.</span></span> <span data-ttu-id="b54a3-107">O tipo de atualização afeta as etapas que você deve completar para atualizar os custos padrão, como ilustrado nos seguintes casos:</span><span class="sxs-lookup"><span data-stu-id="b54a3-107">The type of update affects the steps that you must complete to update standard costs, as illustrated in the following cases:</span></span>

-   <span data-ttu-id="b54a3-108">Insira alterações de custo padrão antecipadas para itens comprados e em seguida altere o status dos registros de custo de item para **Ativo** na data apropriada.</span><span class="sxs-lookup"><span data-stu-id="b54a3-108">Enter expected standard cost changes for purchased items, and then change the status of the item cost records to **Active** on the appropriate date.</span></span> <span data-ttu-id="b54a3-109">No entanto, não calcule novamente os custos dos itens fabricados que usam os itens comprados.</span><span class="sxs-lookup"><span data-stu-id="b54a3-109">However, don't recalculate the costs of manufactured items that use the purchased items.</span></span>
-   <span data-ttu-id="b54a3-110">Insira custos padrão para um novo item comprado, mas não calcule novamente os custos de itens fabricados que têm uma versão de lista de materiais (BOM) que contém o novo item comprado como um componente.</span><span class="sxs-lookup"><span data-stu-id="b54a3-110">Enter standard costs for a new purchased item, but don't recalculate the costs of manufactured items that have a bill of materials (BOM) version that contains the new purchased item as a component.</span></span>
-   <span data-ttu-id="b54a3-111">Corrija ou altere o custo do item comprado ou altere o grupo de custo atribuído a um item comprado e calcule o custo para todos os itens fabricados que têm uma versão de BOM que contém o item comprado como um componente.</span><span class="sxs-lookup"><span data-stu-id="b54a3-111">Correct or change the cost of a purchased item, or change the cost group that is assigned to a purchased item, and calculate the cost for all manufactured items that have a BOM version that contains the purchased item as a component.</span></span>
-   <span data-ttu-id="b54a3-112">Altere o custo para uma categoria de custo e calcule o custo para todos os itens fabricados que têm uma versão de roteiro que contém operações de roteiro as quais usam a categoria de custo.</span><span class="sxs-lookup"><span data-stu-id="b54a3-112">Change the cost for a cost category, and calculate the cost for all manufactured items that have a route version that contains routing operations that use the cost category.</span></span>
-   <span data-ttu-id="b54a3-113">Altere as categorias de custo atribuídas a operações de roteiro ou o grupo de custos atribuído a categorias de custo.</span><span class="sxs-lookup"><span data-stu-id="b54a3-113">Change the cost categories that are assigned to routing operations or the cost group that is assigned to cost categories.</span></span> <span data-ttu-id="b54a3-114">Altere o custo para uma categoria de custo e calcule o custo para todos os itens fabricados que têm uma versão de roteiro que contém operações de roteiro as quais usam a categoria de custo.</span><span class="sxs-lookup"><span data-stu-id="b54a3-114">Then calculate the cost for all manufactured items that have a route version that contains routing operations that use the cost category.</span></span>
-   <span data-ttu-id="b54a3-115">Altere uma fórmula de cálculo de custo indireto e calcule o custo para todos os itens fabricados afetados pela alteração.</span><span class="sxs-lookup"><span data-stu-id="b54a3-115">Change an indirect cost calculation formula, and calculate the cost for all manufactured items that are affected by the change.</span></span>
-   <span data-ttu-id="b54a3-116">Altere ou adicione um site de fabricação para um item fabricado e calcule o custo de fabricação do item para o site.</span><span class="sxs-lookup"><span data-stu-id="b54a3-116">Change or add a manufacturing site for a manufactured item, and calculate the item's manufactured cost for the site.</span></span>
-   <span data-ttu-id="b54a3-117">Calcule ou recalcular o custo para um item fabricado e calcule novamente o custo para todos os itens fabricados que têm uma versão de BOM que contém o item fabricado como um componente.</span><span class="sxs-lookup"><span data-stu-id="b54a3-117">Calculate, or recalculate, the cost for a manufactured item, and recalculate the cost for all manufactured items that have a BOM version that contains the manufactured item as a component.</span></span>
-   <span data-ttu-id="b54a3-118">Calcule os custos para um novo item fabricado com base na BOM aprovada e ativa, assim como nas informações de roteiro.</span><span class="sxs-lookup"><span data-stu-id="b54a3-118">Calculate costs for a new manufactured item, based on its defined, approved, and active BOM and route information.</span></span>

<span data-ttu-id="b54a3-119">Cada caso requer considerações sobre como atualizar custos padrão.</span><span class="sxs-lookup"><span data-stu-id="b54a3-119">Each case requires careful consideration about how to update standard costs.</span></span>



