---
title: Reservar o mesmo lote para uma ordem de venda
description: "Este artigo explica como configurar um produto para permitir a reserva de estoque em relação a um único lote de estoque."
author: YuyuScheller
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: EcoResProductDetailsExtended, EcoResStorageDimensionGroup, EcoResTrackingDimensionGroup, InventBatch, InventModelGroup, PdsAskSameLotForm, PdsCustSellableDays
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 28911
ms.assetid: 5823d75e-f839-46dd-beb3-e09b79fc8aa4
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: aef3a52f4cb2d5af47a8c25a67e6c2076fa1ff03
ms.contentlocale: pt-br
ms.lasthandoff: 11/03/2017

---

# <a name="reserve-the-same-batch-for-a-sales-order"></a><span data-ttu-id="a524e-103">Reservar o mesmo lote para uma ordem de venda</span><span class="sxs-lookup"><span data-stu-id="a524e-103">Reserve the same batch for a sales order</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="a524e-104">Este artigo explica como configurar um produto para permitir a reserva de estoque em relação a um único lote de estoque.</span><span class="sxs-lookup"><span data-stu-id="a524e-104">This article explains how to set up a product to allow reservation of inventory against a single batch of inventory.</span></span>

<span data-ttu-id="a524e-105">A reserva de mesmo lote permite reservar estoque para uma linha de ordem de venda para um único lote de estoque.</span><span class="sxs-lookup"><span data-stu-id="a524e-105">Same batch reservation lets you reserve inventory for a sales order line against a single batch of inventory.</span></span> <span data-ttu-id="a524e-106">Por exemplo, um cliente que encomende papel de parede pode solicitar que a ordem inteira seja atendida pelo mesmo lote a fim de evitar diferenças entre os rolos.</span><span class="sxs-lookup"><span data-stu-id="a524e-106">For example, a customer who orders wallpaper can request that the whole order be filled from the same batch or lot, to avoid inconsistencies among the rolls.</span></span> <span data-ttu-id="a524e-107">Para configurar um produto para usar a mesma reserva de lote, as configurações a seguir devem estar ativas no grupo de modelos de item, no grupo de dimensões de rastreamento e no grupo de dimensões de armazenamento atribuídos ao produto:</span><span class="sxs-lookup"><span data-stu-id="a524e-107">To set up a product to use same batch reservation, the following settings must be active in the item model group, tracking dimension group, and storage dimension group that you assign to the product:</span></span>

-   <span data-ttu-id="a524e-108">**Grupos de modelos de itens** – o grupo de modelos de itens deve ter os campos **Seleção de mesmo lote** e **Consolidar necessidade** selecionados no grupo de campos **Reserva** para políticas de estoque.</span><span class="sxs-lookup"><span data-stu-id="a524e-108">**Item model groups** – The item model group must have the **Same batch selection** and **Consolidate requirement** fields selected in the **Reservation** field group for inventory policies.</span></span>
-   <span data-ttu-id="a524e-109">**Grupos de dimensões de rastreamento** – o grupo de dimensões de rastreamento deve ter o campo **Plano de cobertura por dimensão** selecionado para o número do lote.</span><span class="sxs-lookup"><span data-stu-id="a524e-109">**Tracking dimensions groups** – The tracking dimension group must have the **Coverage plan by dimension** field selected for the batch number.</span></span>
-   <span data-ttu-id="a524e-110">**Grupos de dimensões de armazenamento** – o grupo de dimensões de armazenamento deve ter o campo **Plano de cobertura por dimensão** selecionado para **Local** e **Depósito**.</span><span class="sxs-lookup"><span data-stu-id="a524e-110">**Storage dimensions groups** – The storage dimension group must have the **Coverage plan by dimension** field selected for **Site** and **Warehouse**.</span></span>

<span data-ttu-id="a524e-111">Ao reservar estoque para um produto em uma linha da ordem de venda configurada para a seleção de mesmo lote, o Microsoft Dynamics 365 for Finance and Operations tenta reservar a quantidade encomendada de um único lote de estoque.</span><span class="sxs-lookup"><span data-stu-id="a524e-111">When you reserve inventory for a product on a sales order line that is set up for same batch selection, Microsoft Dynamics 365 for Finance and Operations tries to reserve the ordered quantity from a single inventory batch.</span></span> <span data-ttu-id="a524e-112">Qualquer requisito específico do atributo de lote também será considerado.</span><span class="sxs-lookup"><span data-stu-id="a524e-112">Any specific batch attribute requirements are also considered.</span></span> <span data-ttu-id="a524e-113">Se a quantidade não puder ser preenchida de um único lote, a página **Conflito de reserva de mesmo lote** será exibida.</span><span class="sxs-lookup"><span data-stu-id="a524e-113">If the quantity can't be filled from a single batch, the **Same batch reservation conflict** page appears.</span></span> <span data-ttu-id="a524e-114">Essa página descreve os problemas e também as ações que você pode executar para proceder com a reserva.</span><span class="sxs-lookup"><span data-stu-id="a524e-114">This page describes the issues and also the actions that you can take to continue with the reservation.</span></span> <span data-ttu-id="a524e-115">As seguintes condições podem impedir que o lote seja reservado:</span><span class="sxs-lookup"><span data-stu-id="a524e-115">The following conditions might prevent the batch from being reserved:</span></span>

-   <span data-ttu-id="a524e-116">O código de disposição do lote tem **Bloquear reserva** da venda sinalizado como **Bloqueado**.</span><span class="sxs-lookup"><span data-stu-id="a524e-116">The batch disposition code has **Block reservation** for sales flagged as **Blocked**.</span></span>
-   <span data-ttu-id="a524e-117">O lote expirou com base na data de vencimento e nos dias comercializáveis aplicáveis do cliente.</span><span class="sxs-lookup"><span data-stu-id="a524e-117">The batch has expired, based on the expiration date and any applicable customer sellable days.</span></span> <span data-ttu-id="a524e-118">O item ainda poderá ser considerado para reserva se o grupo de modelos de item for controlado pela data FEFO (primeiro a vencer, primeiro a sair) e se a data de validade for selecionada como critério de separação.</span><span class="sxs-lookup"><span data-stu-id="a524e-118">The item can still be considered for reservation if the item model group for the item is First Expiry First Out (FEFO) date–controlled, and if the best-before date is selected as the pick criterion.</span></span>
-   <span data-ttu-id="a524e-119">O lote não tem dias restantes de validade suficientes com base na data de vencimento e na data de validade, mais os dias comercializáveis do cliente.</span><span class="sxs-lookup"><span data-stu-id="a524e-119">The batch doesn't have enough shelf-life days remaining, based on the expiration date and best-before date, plus any customer sellable days.</span></span>





