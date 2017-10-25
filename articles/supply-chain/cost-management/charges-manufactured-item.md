---
title: Exibir encargos para um item fabricado
description: "Os custos constantes de um item fabricado refletem os tempos de preparação da operação e os componentes com uma quantidade constante ou um valor de sucata constante."
author: AndersGirke
manager: AnnBe
ms.date: 04/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CostingVersion, InventItemPrice
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 274483
ms.assetid: 6f5b851b-c5a7-43ef-b380-0d316667c1ef
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.dyn365.ops.intro: AX 7.0.0
ms.search.validFrom: 2016-02-28
ms.translationtype: HT
ms.sourcegitcommit: a61761a5c9d98befd67682e1790af5377b7a55e1
ms.openlocfilehash: f0ce01b21f62ee91c861b45e92f87b95be0476de
ms.contentlocale: pt-br
ms.lasthandoff: 10/13/2017

---

# <a name="display-charges-for-a-manufactured-item"></a><span data-ttu-id="098b6-103">Exibir encargos para um item fabricado</span><span class="sxs-lookup"><span data-stu-id="098b6-103">Display charges for a manufactured item</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="098b6-104">Os custos constantes de um item fabricado refletem os tempos de preparação da operação e os componentes com uma quantidade constante ou um valor de sucata constante.</span><span class="sxs-lookup"><span data-stu-id="098b6-104">The constant costs of a manufactured item reflect the operation setup times and the components that have a constant quantity or a constant scrap amount.</span></span>

<span data-ttu-id="098b6-105">O valor calculado dos encargos de um item pode ser exibido com os custos unitários do item.</span><span class="sxs-lookup"><span data-stu-id="098b6-105">The calculated amount of an item's charges can be displayed with the item's unit costs.</span></span> <span data-ttu-id="098b6-106">Entretanto, os encargos são exibidos algumas vezes em campos separados, e não estão incluídos nos custos unitários do item.</span><span class="sxs-lookup"><span data-stu-id="098b6-106">However, the charges are sometimes displayed as separate fields, and they are not included in the item's unit costs.</span></span> <span data-ttu-id="098b6-107">Quando os encargos aparecem como campos separados, um campo mostra o valor total dos encargos e outro campo exibe o tamanho do lote de custos usado para amortizar o valor.</span><span class="sxs-lookup"><span data-stu-id="098b6-107">When the charges appear as separate fields, one field displays the total amount of charges, and another field displays the costing lot size that is used to amortize the amount.</span></span> <span data-ttu-id="098b6-108">A página Preço de item, por exemplo, exibe os encargos como dois campos separados.</span><span class="sxs-lookup"><span data-stu-id="098b6-108">The Item price page, for example, displays the charges as two separate fields.</span></span> <span data-ttu-id="098b6-109">Entretanto, a página Concluído exibe o custo total do item por unidade e os custos amortizados são incluídos nos custos unitários.</span><span class="sxs-lookup"><span data-stu-id="098b6-109">However, the Complete page displays the item's total cost per unit, and the amortized costs are included in the unit costs.</span></span>

<span data-ttu-id="098b6-110">Os encargos de um item fabricado são sempre incluídos no custo unitário do item para fins de custo padrão.</span><span class="sxs-lookup"><span data-stu-id="098b6-110">The charges for a manufactured item are always included in the item's unit cost for standard cost purposes.</span></span> <span data-ttu-id="098b6-111">Opcionalmente, eles podem ser incluídos para custos planejados.</span><span class="sxs-lookup"><span data-stu-id="098b6-111">They can optionally be included for planned cost purposes.</span></span> <span data-ttu-id="098b6-112">Uma política na versão de avaliação de custo impõe a inclusão de encargos no custo de um item fabricado.</span><span class="sxs-lookup"><span data-stu-id="098b6-112">A policy in the costing version enforces the inclusion of charges in the cost of a manufactured item.</span></span> <span data-ttu-id="098b6-113">Ao ativar um registro de custo de um item, você atualiza os encargos das informações de custo base do item, exibidas na página Preço do item.</span><span class="sxs-lookup"><span data-stu-id="098b6-113">When you activate an item's cost record, you update the charges for the item's base cost information, which is displayed in the Item price page.</span></span> <span data-ttu-id="098b6-114">Os encargos são exibidos como dois campos separados e não estão incluídos no custo unitário do item.</span><span class="sxs-lookup"><span data-stu-id="098b6-114">The charges are displayed as two separate fields, and they are not included in the item's unit cost.</span></span> <span data-ttu-id="098b6-115">Cada ativação atualiza as informações de custo base do item, mesmo se a ativação refletir sites diferentes.</span><span class="sxs-lookup"><span data-stu-id="098b6-115">Each activation updates the item's base cost information, even if the activation reflects different sites.</span></span> <span data-ttu-id="098b6-116">Portanto, considere as informações de custo base como informações de referência.</span><span class="sxs-lookup"><span data-stu-id="098b6-116">Therefore, you should view the base cost information as reference information.</span></span>





