---
title: "Incluir valor físico"
description: "Você usa a caixa de seleção Incluir valor físico na Guia Rápida Modelo de estoque da página Grupos de modelos de item para especificar se as transações atualizadas fisicamente serão consideradas quando o preço de custo médio for calculado para um item."
author: AndersGirke
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: InventModelGroup
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 79033
ms.assetid: 1928c145-bf82-436d-87ca-e7a173e31923
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: mguada
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 28f51524e4818558716b3f7a82ffcb301fee883d
ms.contentlocale: pt-br
ms.lasthandoff: 05/08/2018

---

# <a name="include-physical-value"></a><span data-ttu-id="e7fd8-103">Incluir valor físico</span><span class="sxs-lookup"><span data-stu-id="e7fd8-103">Include physical value</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="e7fd8-104">Você usa a caixa de seleção Incluir valor físico na Guia Rápida Modelo de estoque da página Grupos de modelos de item para especificar se as transações atualizadas fisicamente serão consideradas quando o preço de custo médio for calculado para um item.</span><span class="sxs-lookup"><span data-stu-id="e7fd8-104">You use the Include physical value check box on the Inventory model FastTab of the Item model groups page to specify whether physically updated transactions are considered when the running average cost price is calculated for an item.</span></span>

<span data-ttu-id="e7fd8-105">A caixa de seleção **Incluir valor físico** tem os valores a seguir.</span><span class="sxs-lookup"><span data-stu-id="e7fd8-105">The **Include physical value** check box has the following values.</span></span>

| <span data-ttu-id="e7fd8-106">Valor</span><span class="sxs-lookup"><span data-stu-id="e7fd8-106">Value</span></span>    | <span data-ttu-id="e7fd8-107">Resultado</span><span class="sxs-lookup"><span data-stu-id="e7fd8-107">Result</span></span>                                                                                                                          |
|----------|---------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="e7fd8-108">Selecionados</span><span class="sxs-lookup"><span data-stu-id="e7fd8-108">Selected</span></span> | <span data-ttu-id="e7fd8-109">As transações atualizadas fisicamente como as atualizadas financeiramente são usadas para calcular o preço de custo médio corrente.</span><span class="sxs-lookup"><span data-stu-id="e7fd8-109">Both physically updated transactions and financially updated transactions are used to calculate the running average cost price.</span></span> |
| <span data-ttu-id="e7fd8-110">Desmarcado</span><span class="sxs-lookup"><span data-stu-id="e7fd8-110">Cleared</span></span>  | <span data-ttu-id="e7fd8-111">Somente as transações atualizadas financeiramente serão usadas para calcular o preço de custo médio corrente.</span><span class="sxs-lookup"><span data-stu-id="e7fd8-111">Only financially updated transactions are used to calculate the running average cost price.</span></span>                                     |

<span data-ttu-id="e7fd8-112">A caixa de seleção tem efeitos ligeiramente diferentes, dependendo do modelo de estoque usado.</span><span class="sxs-lookup"><span data-stu-id="e7fd8-112">The check box has slightly different effects, depending on the inventory model that you use.</span></span>

-   <span data-ttu-id="e7fd8-113">Se você marcar a caixa de seleção **Incluir valor físico** ao usar o modelo de estoque FIFO, LIFO ou Data LIFO, o fechamento de estoque também ajustará as transações atualizadas fisicamente.</span><span class="sxs-lookup"><span data-stu-id="e7fd8-113">If you select the **Include physical value** check box when you use the FIFO (First in, first out), LIFO (Last in, first out), or LIFO date inventory model, inventory close also makes adjustments to physically updated transactions.</span></span>
-   <span data-ttu-id="e7fd8-114">Se você não marcar a caixa de seleção **Incluir valor físico** ao usar esses modelos de estoque, o fechamento de estoque liquidará somente para transações atualizadas financeiramente.</span><span class="sxs-lookup"><span data-stu-id="e7fd8-114">If you don't select the **Include physical value** check box when you use these inventory models, inventory close makes settlements only to financially updated transactions.</span></span>
-   <span data-ttu-id="e7fd8-115">Ao usar a média ponderada ou o modelo de estoque de data da média ponderada, o fechamento de estoque liquidará somente transações atualizadas financeiramente, independentemente de você marcar a caixa de seleção **Incluir valor físico**.</span><span class="sxs-lookup"><span data-stu-id="e7fd8-115">When you use the weighted average or weighted average date inventory model, inventory close settles only financially updated transactions, regardless of whether you select the **Include physical value** check box.</span></span>

<span data-ttu-id="e7fd8-116">**Exemplo 1** Você marcou a caixa de seleção**Incluir valor físico** e recebe as seguintes ordens de compra:</span><span class="sxs-lookup"><span data-stu-id="e7fd8-116">**Example 1** You've selected the **Include physical value** check box and receive the following purchase orders:</span></span>

-   <span data-ttu-id="e7fd8-117">Uma ordem de compra para uma quantidade 2 e um preço de custo de BRL 10,00 que foi atualizado na guia de remessa</span><span class="sxs-lookup"><span data-stu-id="e7fd8-117">A purchase order for a quantity of 2 and a cost price of USD 10.00 that has been packing slip–updated</span></span>
-   <span data-ttu-id="e7fd8-118">Uma ordem de compra para uma quantidade 3 e um preço de custo de BRL 12,00 que foi atualizado na fatura</span><span class="sxs-lookup"><span data-stu-id="e7fd8-118">A purchase order for a quantity of 3 and a cost price of USD 12.00 that has been invoice-updated</span></span>

<span data-ttu-id="e7fd8-119">Nesse caso, o preço de custo médio corrente será BRL 11,20 porque tanto as transações atualizadas fisicamente como as atualizadas financeiramente são usadas para calcular o preço de custo.</span><span class="sxs-lookup"><span data-stu-id="e7fd8-119">In this case, the running average cost price will be USD 11.20, because both physically updated transactions and financially updated transactions are used to calculate the cost price.</span></span> <span data-ttu-id="e7fd8-120">**Exemplo 2** Você não marcou a caixa de seleção **Incluir valor físico** e o preço de custo na configuração do item é BRL 10,00.</span><span class="sxs-lookup"><span data-stu-id="e7fd8-120">**Example 2** You haven't selected the **Include physical value** check box, and the cost price on the item setup is USD 10.00.</span></span> <span data-ttu-id="e7fd8-121">Você recebe uma ordem de compra para uma quantidade 20 e um preço de custo de BRL 12,00 que foi atualizado na guia de remessa.</span><span class="sxs-lookup"><span data-stu-id="e7fd8-121">You receive a purchase order for a quantity of 20 and a cost price of USD 12.00 that has been packing slip–updated.</span></span> <span data-ttu-id="e7fd8-122">Quando uma ordem de venda é lançada, o valor de custo lançado é de BRL 10,00, pois o preço de custo médio corrente não incluirá as transações lançadas fisicamente.</span><span class="sxs-lookup"><span data-stu-id="e7fd8-122">When a sales order is posted, the posted cost amount is USD 10.00, because the running average cost price won't include physically posted transactions.</span></span> <span data-ttu-id="e7fd8-123">**Observação:** para comparação, se você marcar a caixa de seleção **Incluir valor físico** para esse item, quando uma ordem de venda for lançada, o valor de custo lançado será BRL 12,00.</span><span class="sxs-lookup"><span data-stu-id="e7fd8-123">**Note:** For comparison, if you select the **Include physical value** check box for this item, when a sales order is posted, the posted cost amount will be USD 12.00.</span></span>




