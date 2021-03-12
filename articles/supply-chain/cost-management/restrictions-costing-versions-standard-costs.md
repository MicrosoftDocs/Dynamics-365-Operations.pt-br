---
title: Restrições em versões de avaliação de custo para custos padrão
description: Este tópico descreve as restrições que se aplicam a uma versão de avaliação de custo para custos padrão.
author: AndersGirke
manager: tfehr
ms.date: 01/17/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CostingVersion
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.industry: Manufacturing
ms.author: aevengir
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5339c3c4a62b94a06cbffc200ed1e9b227d6b6af
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4963779"
---
#  <a name="restrictions-on-costing-versions-for-standard-costs"></a><span data-ttu-id="af31a-103">Restrições em versões de avaliação de custo para custos padrão</span><span class="sxs-lookup"><span data-stu-id="af31a-103">Restrictions on costing versions for standard costs</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="af31a-104">Este tópico descreve as restrições que se aplicam a uma versão de avaliação de custo para custos padrão.</span><span class="sxs-lookup"><span data-stu-id="af31a-104">This topic describes the restrictions that apply to a costing version for standard costs.</span></span> 

<span data-ttu-id="af31a-105">As restrições a seguir ajudam a garantir a aderência aos princípios de avaliação de custo padrão:</span><span class="sxs-lookup"><span data-stu-id="af31a-105">The following restrictions help guarantee adherence to standard costing principles:</span></span>

-  <span data-ttu-id="af31a-106">Os encargos devem ser incluídos no custo de um item.</span><span class="sxs-lookup"><span data-stu-id="af31a-106">Charges must be included in an item's cost.</span></span> <span data-ttu-id="af31a-107">Os encargos para um item fabricado representam os custos constantes amortizados na lista de materiais (BOM) e nas informações de roteiro.</span><span class="sxs-lookup"><span data-stu-id="af31a-107">The charges for a manufactured item represent the amortized constant costs in the bill of materials (BOM) and route information.</span></span> <span data-ttu-id="af31a-108">Portanto, os encargos devem ser incluídos no custo unitário.</span><span class="sxs-lookup"><span data-stu-id="af31a-108">Therefore, the charges must be included in the unit cost.</span></span> <span data-ttu-id="af31a-109">Os encargos para um item comprado também estão incluídos no custo unitário do item.</span><span class="sxs-lookup"><span data-stu-id="af31a-109">The charges for a purchased item are also included in the item's unit cost.</span></span>

-  <span data-ttu-id="af31a-110">O cálculo de custos padrão de itens fabricados deve ser baseado nos registros de custo em uma versão do custo para custos padrão.</span><span class="sxs-lookup"><span data-stu-id="af31a-110">Calculation of standard costs for manufactured items must be based on the cost records in a costing version for standard costs.</span></span> <span data-ttu-id="af31a-111">Fontes alternativas de dados de custo só podem ser usadas com uma versão de avaliação de custo para custos planejados, como contratos comerciais de preço de compra para itens comprados.</span><span class="sxs-lookup"><span data-stu-id="af31a-111">Alternative sources of cost data can be used only with a costing version for planned costs, such as purchase price trade agreements for purchased items.</span></span> <span data-ttu-id="af31a-112">Fontes alternativas de dados de custo são definidas pelo grupo de cálculo de BOM.</span><span class="sxs-lookup"><span data-stu-id="af31a-112">Alternative sources of cost data are defined by the BOM calculation group.</span></span>

-  <span data-ttu-id="af31a-113">Os cálculos de BOM devem ser feitos em um modo de detalhamento de nível único.</span><span class="sxs-lookup"><span data-stu-id="af31a-113">BOM calculations must be performed in a single-level explosion mode.</span></span>

<span data-ttu-id="af31a-114">Os dados de custo de item para custos padrão podem ser copiados em outra versão do custo que contenha os custos padrão ou planejados.</span><span class="sxs-lookup"><span data-stu-id="af31a-114">The item cost data for standard costs can be copied to another costing version that contains standard costs or planned costs.</span></span> <span data-ttu-id="af31a-115">Porém, os dados de custo de item para os custos planejados não podem ser copiados para uma versão de custo que contenha custos padrão porque as restrições listadas anteriormente neste tópico não se aplicam aos custos planejados.</span><span class="sxs-lookup"><span data-stu-id="af31a-115">However, the item cost data for planned costs can't be copied to a cost version that contains standard costs, because the restrictions that are listed earlier in this topic don't apply to planned costs.</span></span>

<a name="related-topics"></a><span data-ttu-id="af31a-116">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="af31a-116">Related topics</span></span>
--------

[<span data-ttu-id="af31a-117">Visão geral de versões de avaliação de custo</span><span class="sxs-lookup"><span data-stu-id="af31a-117">Costing versions overview</span></span>](costing-versions.md)

[<span data-ttu-id="af31a-118">Atualizar custos padrão em um ambiente de não fabricação</span><span class="sxs-lookup"><span data-stu-id="af31a-118">Update standard costs in a non-manufacturing environment</span></span>](update-standard-costs-non-manufacturing-environment.md)

[<span data-ttu-id="af31a-119">Preparar para manter custos padrão para itens fabricados</span><span class="sxs-lookup"><span data-stu-id="af31a-119">Prepare to maintain standard costs for manufactured items</span></span>](update-standard-costs-manufacturing-environment.md)

