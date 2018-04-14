---
title: "Amortização de custos constantes para um item fabricado"
description: "Os custos constantes de um item fabricado refletem os tempos de preparação da operação e os componentes com uma quantidade constante ou um valor de sucata constante."
author: AndersGirke
manager: AnnBe
ms.date: 04/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: BOMCalcDialog, BOMCalcTable, BOMCalcTrans
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 274503
ms.assetid: 535ab25d-a031-4e8c-84ec-478f2987a1ad
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: aevengir
ms.dyn365.ops.version: AX 7.0.0
ms.search.validFrom: 2016-02-28
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 2e9d15e35661d37036af48d4d1183e4f25012e57
ms.contentlocale: pt-br
ms.lasthandoff: 04/13/2018

---

# <a name="amortize-constant-costs-for-a-manufactured-item"></a><span data-ttu-id="9b3dc-103">Amortização de custos constantes para um item fabricado</span><span class="sxs-lookup"><span data-stu-id="9b3dc-103">Amortize constant costs for a manufactured item</span></span>

[!INCLUDE [banner](../includes/banner.md)]

<span data-ttu-id="9b3dc-104">Os custos constantes de um item fabricado refletem os tempos de preparação da operação e os componentes com uma quantidade constante ou um valor de sucata constante.</span><span class="sxs-lookup"><span data-stu-id="9b3dc-104">A manufactured item’s constant costs reflect the operation setup times and the components that have a constant quantity or a constant scrap amount.</span></span> 

<span data-ttu-id="9b3dc-105">O conceito do tamanho de um lote de custos é usado para amortizar esses custos constantes no custo calculado de um item fabricado.</span><span class="sxs-lookup"><span data-stu-id="9b3dc-105">The concept of a costing lot size is used to amortize these constant costs in the calculated cost of a manufactured item.</span></span> <span data-ttu-id="9b3dc-106">Esse conceito tem vários sinônimos, um dos quais é tamanho de lote contabilidade.</span><span class="sxs-lookup"><span data-stu-id="9b3dc-106">This concept has several synonyms, one of which is accounting lot size.</span></span> <span data-ttu-id="9b3dc-107">O conceito de amortizar custos constantes também tem vários sinônimos, um dos quais é custos constantes proporcionais.</span><span class="sxs-lookup"><span data-stu-id="9b3dc-107">The concept of amortizing constant costs also has several synonyms, one of which is proportional constant costs.</span></span>

<span data-ttu-id="9b3dc-108">A quantidade de um tamanho de lote de avaliação de custo para um item fabricado é usada em um cálculo de lista de materiais (BOM).</span><span class="sxs-lookup"><span data-stu-id="9b3dc-108">The quantity of a costing lot size for a manufactured item is used in a bill of material (BOM) calculation.</span></span> <span data-ttu-id="9b3dc-109">A quantidade depende de como você inicia e executa o cálculo de BOM, como explicado a seguir:</span><span class="sxs-lookup"><span data-stu-id="9b3dc-109">The quantity depends on how you initiate and perform the BOM calculation, as illustrated by the following:</span></span>

-   <span data-ttu-id="9b3dc-110">Quantidade de cálculo padrão no cálculo de BOM de um item: a quantidade de ordem padrão do item para estoque atua como o tamanho de lote de avaliação de custos, mas o valor padrão pode ser uma quantidade maior para refletir o múltiplo da quantidade da ordem do item.</span><span class="sxs-lookup"><span data-stu-id="9b3dc-110">Default calculation quantity in an item’s BOM calculation − The item’s standard order quantity for inventory acts as the costing lot size, but the default value might be a greater quantity to reflect the item’s order quantity multiple.</span></span> <span data-ttu-id="9b3dc-111">O múltiplo e a quantidade de ordem padrão do item podem ser definidos nas configurações de ordem padrão ou de ordem específica ao site.</span><span class="sxs-lookup"><span data-stu-id="9b3dc-111">The item’s standard order quantity and multiple can be defined within its default order settings or site-specific order settings.</span></span>
-   <span data-ttu-id="9b3dc-112">A quantidade de cálculo especificada no cálculo de BOM de um item − a quantidade de cálculo especificada atua como o tamanho de lote de custos do item.</span><span class="sxs-lookup"><span data-stu-id="9b3dc-112">Specified calculation quantity in an item’s BOM calculation − The specified calculation quantity acts as the costing lot size for the item.</span></span> <span data-ttu-id="9b3dc-113">A quantidade de cálculo inicialmente usa a quantidade de ordem padrão do item, mas o valor padrão pode ser substituído manualmente.</span><span class="sxs-lookup"><span data-stu-id="9b3dc-113">The calculation quantity initially uses the item’s standard order quantity, but the default value can be manually overridden.</span></span> <span data-ttu-id="9b3dc-114">A quantidade de cálculo especificada representa o tamanho do lote de avaliação de custo para o item especificado e para os componentes fabricados com um tipo de linha de BOM de produção.</span><span class="sxs-lookup"><span data-stu-id="9b3dc-114">The specified calculation quantity represents the costing lot size for the specified item, and for manufactured components that have a BOM line type of production.</span></span> <span data-ttu-id="9b3dc-115">Isso é porque supõe-se que o componente será produzido na quantidade exata.</span><span class="sxs-lookup"><span data-stu-id="9b3dc-115">This is because it is assumed that the component will be produced to the exact quantity.</span></span> <span data-ttu-id="9b3dc-116">O tamanho de lote de avaliação de custo para outros componentes fabricados com um tipo de linha de BOM igual a item refletirá a quantidade de ordem padrão.</span><span class="sxs-lookup"><span data-stu-id="9b3dc-116">The costing lot size for other manufactured components that have a BOM line type of item will reflect their standard order quantity.</span></span>
-   <span data-ttu-id="9b3dc-117">A quantidade especificada de marca a ser solicitada no calculo de BOM de um item − a quantidade de cálculo especificada atua como o tamanho de lote de custos para o item e seus componentes fabricados quando os cálculos de BOM usam um modo de detalhamento de marca a ser solicitada.</span><span class="sxs-lookup"><span data-stu-id="9b3dc-117">Specified make-to-order calculation quantity in an item’s BOM calculation − The specified calculation quantity acts as the costing lot size for the item and its manufactured components when BOM calculations use a make-to-order explosion mode.</span></span> <span data-ttu-id="9b3dc-118">Supõe-se que os componentes fabricados serão produzidos na quantidade exata, assim como um componente fabricado com um tipo de linha de BOM igual a produção.</span><span class="sxs-lookup"><span data-stu-id="9b3dc-118">It is assumed that the manufactured components will be produced to the exact quantity, just like a manufactured component that has a BOM line type of production.</span></span>
-   <span data-ttu-id="9b3dc-119">A quantidade de cálculo especificada em um cálculo de BOM específico a uma ordem − um cálculo de BOM específico a uma ordem pode ser realizado para um item de linha em uma ordem de venda, cotação de venda ou ordem de serviço.</span><span class="sxs-lookup"><span data-stu-id="9b3dc-119">Specified calculation quantity in an order-specific BOM calculation − An order-specific BOM calculation can be performed for a line item on a sales order, sales quotation, or service order.</span></span> <span data-ttu-id="9b3dc-120">A quantidade de cálculo especificada usa como padrão a quantidade no item de linha de origem, mas a quantidade padrão pode ser substituída.</span><span class="sxs-lookup"><span data-stu-id="9b3dc-120">The specified calculation quantity uses the quantity on the originating line item, but the default quantity can be overridden.</span></span> <span data-ttu-id="9b3dc-121">Você pode selecionar se deseja que o cálculo de BOM específico a uma ordem use um modo de detalhamento de marca a ser solicitada ou de vários níveis.</span><span class="sxs-lookup"><span data-stu-id="9b3dc-121">You can select whether the order-specific BOM calculation uses a make-to-order or multilevel explosion mode.</span></span>

<span data-ttu-id="9b3dc-122">O valor calculado dos custos constantes amortizados de um item fabricado é denominado encargos.</span><span class="sxs-lookup"><span data-stu-id="9b3dc-122">The calculated amount of a manufactured item’s amortized constant costs is termed charges.</span></span>






