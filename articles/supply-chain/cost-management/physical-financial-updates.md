---
title: "Atualizações físicas e financeiras"
description: "Este tópico fornece uma visão geral dos tipos de transação que aumentam ou diminuem quantidades em estoque."
author: AndersGirke
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: InventTrans, InventTransVoucher
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 75023
ms.assetid: 128340e1-c573-48e6-b835-6c350d8dd0fb
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: mguada
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 1d98cbff30620256c9d13e7b4a90314db150e33e
ms.openlocfilehash: 9ba628dbf63d3b124583e6b873530f1459b07562
ms.contentlocale: pt-br
ms.lasthandoff: 08/07/2018

---

# <a name="physical-and-financial-updates"></a><span data-ttu-id="aa096-103">Atualizações físicas e financeiras</span><span class="sxs-lookup"><span data-stu-id="aa096-103">Physical and financial updates</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="aa096-104">Este tópico fornece uma visão geral dos tipos de transação que aumentam ou diminuem quantidades em estoque.</span><span class="sxs-lookup"><span data-stu-id="aa096-104">This topic provides an overview of which types of transactions increase or decrease inventory quantities.</span></span> 

<span data-ttu-id="aa096-105">As transações de estoque podem ser atualizadas de forma física e financeira no Microsoft Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="aa096-105">Inventory transactions can be physically updated and financially updated in Microsoft Dynamics 365 for Finance and Operations.</span></span> <span data-ttu-id="aa096-106">Alguns dos tipos de transações físicas e financeiras aumentam as quantidades em estoque, enquanto outras diminuem a quantidade.</span><span class="sxs-lookup"><span data-stu-id="aa096-106">Some types of physical and financial transactions increase inventory quantities, whereas others decrease the quantity.</span></span>

## <a name="physical-increases"></a><span data-ttu-id="aa096-107">Aumentos físicos</span><span class="sxs-lookup"><span data-stu-id="aa096-107">Physical increases</span></span>
<span data-ttu-id="aa096-108">Quando uma transação física é lançada, o status do registro da transação é **Recebido**.</span><span class="sxs-lookup"><span data-stu-id="aa096-108">When a physical transaction is posted, the status of the transaction record is **Received**.</span></span> <span data-ttu-id="aa096-109">As transações a seguir são consideradas aumentos físicos:</span><span class="sxs-lookup"><span data-stu-id="aa096-109">The following transactions are considered physical increases:</span></span>

-   <span data-ttu-id="aa096-110">Recebimento de ordem de compra</span><span class="sxs-lookup"><span data-stu-id="aa096-110">Purchase order receipt</span></span>
-   <span data-ttu-id="aa096-111">Devolução de guia de remessa de ordem de venda</span><span class="sxs-lookup"><span data-stu-id="aa096-111">Sales order packing slip return</span></span>
-   <span data-ttu-id="aa096-112">Relate uma ordem de produção como concluída.</span><span class="sxs-lookup"><span data-stu-id="aa096-112">Reporting a production order as finished</span></span>
-   <span data-ttu-id="aa096-113">Subproduto em uma lista de separação de ordem de produção</span><span class="sxs-lookup"><span data-stu-id="aa096-113">By-product on a production order picking list</span></span>

## <a name="financial-increases"></a><span data-ttu-id="aa096-114">Aumentos físicos</span><span class="sxs-lookup"><span data-stu-id="aa096-114">Financial increases</span></span>
<span data-ttu-id="aa096-115">Quando uma transação de recebimento financeiro é lançada, o status do registro da transação que aumenta a quantidade é **Comprado**.</span><span class="sxs-lookup"><span data-stu-id="aa096-115">When a financial receipt transaction is posted, the status of the transaction record that increases the quantity is **Purchased**.</span></span> <span data-ttu-id="aa096-116">As transações a seguir são consideradas aumentos físicos:</span><span class="sxs-lookup"><span data-stu-id="aa096-116">The following transactions are considered financial increases:</span></span>

-   <span data-ttu-id="aa096-117">Fatura de fornecedor</span><span class="sxs-lookup"><span data-stu-id="aa096-117">Vendor invoice</span></span>
-   <span data-ttu-id="aa096-118">Fatura de ordem de venda para uma devolução</span><span class="sxs-lookup"><span data-stu-id="aa096-118">Sales order invoice for a return</span></span>
-   <span data-ttu-id="aa096-119">Custos de ordem de produção</span><span class="sxs-lookup"><span data-stu-id="aa096-119">Production order costing</span></span>
-   <span data-ttu-id="aa096-120">Diários de estoque de quantidade positiva, como movimento, lucros e perdas, contagem, lista de materiais e transferência</span><span class="sxs-lookup"><span data-stu-id="aa096-120">Positive quantity inventory journals, such as movement, profit and loss, counting, bill of materials, and transfer</span></span>

## <a name="transactions-that-increase-quantity"></a><span data-ttu-id="aa096-121">Transações que aumentam a quantidade</span><span class="sxs-lookup"><span data-stu-id="aa096-121">Transactions that increase quantity</span></span>
<span data-ttu-id="aa096-122">As transações que aumentam a quantidade são lançadas ao preço de custo médio.</span><span class="sxs-lookup"><span data-stu-id="aa096-122">Transactions that increase quantity are posted at the running average cost price.</span></span> <span data-ttu-id="aa096-123">O Finance and Operations calcula um preço de custo médio baseado no custo de cada uma dessas transações para cada dimensão de estoque rastreada financeiramente.</span><span class="sxs-lookup"><span data-stu-id="aa096-123">Finance and Operations calculates a running average cost price that is based on the cost of each of these transactions for each inventory dimension that is being tracked financially.</span></span> <span data-ttu-id="aa096-124">Para obter informações sobre os preços de custo médio, consulte [Preço de custo médio](running-average-cost-price.md).</span><span class="sxs-lookup"><span data-stu-id="aa096-124">For information about running average cost prices, see [Running average cost price](running-average-cost-price.md).</span></span>

## <a name="transactions-that-decrease-quantity"></a><span data-ttu-id="aa096-125">Transações que diminuem a quantidade</span><span class="sxs-lookup"><span data-stu-id="aa096-125">Transactions that decrease quantity</span></span>
<span data-ttu-id="aa096-126">O Finance and Operations usa o preço de custo médio calculado quando uma transação que diminui a quantidade é lançada, independentemente do modelo de estoque associado a esse estoque.</span><span class="sxs-lookup"><span data-stu-id="aa096-126">Finance and Operations uses the calculated running average cost price when a transaction that decreases quantity is posted, regardless of the inventory model that is associated with that inventory.</span></span> <span data-ttu-id="aa096-127">A transação que diminui a quantidade não deve ter sido marcada anteriormente para outra transação antes do lançamento.</span><span class="sxs-lookup"><span data-stu-id="aa096-127">The transaction that decreases quantity must not have been marked to another transaction before it was posted.</span></span> <span data-ttu-id="aa096-128">Se o estoque disponível físico ficar negativo, o Finance and Operations usará o custo de estoque definido para o item na página **Item**.</span><span class="sxs-lookup"><span data-stu-id="aa096-128">If the physical on-hand inventory becomes negative, Finance and Operations uses the inventory cost that is defined for the item on the **Item** page.</span></span> <span data-ttu-id="aa096-129">**Observação:** se a funcionalidade multissite estiver habilitada, esse custo será o custo de estoque definido para um site na página **Configurações da ordem padrão**.</span><span class="sxs-lookup"><span data-stu-id="aa096-129">**Note:** If multisite functionality is enabled, this cost will instead be the inventory cost that is defined for a site on the **Default order settings** page.</span></span>

## <a name="physical-issues-vs-financial-issues"></a><span data-ttu-id="aa096-130">Saídas físicas versus saídas financeiras</span><span class="sxs-lookup"><span data-stu-id="aa096-130">Physical issues vs. financial issues</span></span>
<span data-ttu-id="aa096-131">Quando uma transação física de saída é lançada, o status do registro da transação é **Deduzido**.</span><span class="sxs-lookup"><span data-stu-id="aa096-131">When a physical issue transaction is posted, the status of the transaction record is **Deducted**.</span></span> <span data-ttu-id="aa096-132">As transações a seguir são consideradas saídas físicas:</span><span class="sxs-lookup"><span data-stu-id="aa096-132">The following transactions are considered physical issues:</span></span>

-   <span data-ttu-id="aa096-133">Diário de lista de separação de ordem de produção</span><span class="sxs-lookup"><span data-stu-id="aa096-133">Production order picking list journal</span></span>
-   <span data-ttu-id="aa096-134">Guia de remessa de ordem de venda</span><span class="sxs-lookup"><span data-stu-id="aa096-134">Sales order packing slip</span></span>
-   <span data-ttu-id="aa096-135">Devolução de guia de remessa de ordem de compra</span><span class="sxs-lookup"><span data-stu-id="aa096-135">Purchase order packing slip return</span></span>

<span data-ttu-id="aa096-136">Quando uma transação financeira é lançada, o status do registro da transação é **Vendido**.</span><span class="sxs-lookup"><span data-stu-id="aa096-136">When a financial transaction is posted, the status of the transaction record is **Sold**.</span></span> <span data-ttu-id="aa096-137">As transações a seguir são consideradas saídas financeiras:</span><span class="sxs-lookup"><span data-stu-id="aa096-137">The following transactions are considered financial issues:</span></span>

-   <span data-ttu-id="aa096-138">Terminar uma ordem de produção</span><span class="sxs-lookup"><span data-stu-id="aa096-138">Ending a production order</span></span>
-   <span data-ttu-id="aa096-139">Fatura de ordem de venda</span><span class="sxs-lookup"><span data-stu-id="aa096-139">Sales order invoice</span></span>
-   <span data-ttu-id="aa096-140">Devolução de fatura de fornecedor</span><span class="sxs-lookup"><span data-stu-id="aa096-140">Vendor invoice return</span></span>
-   <span data-ttu-id="aa096-141">Diários de estoque de quantidade negativa, como movimento, lucros e perdas, contagem, lista de materiais e transferência</span><span class="sxs-lookup"><span data-stu-id="aa096-141">Negative quantity inventory journals, such as movement, profit and loss, counting, bill of materials, and transfer</span></span>

<span data-ttu-id="aa096-142">As transações que diminuem a quantidade são lançadas ao preço de custo médio.</span><span class="sxs-lookup"><span data-stu-id="aa096-142">Transactions that decrease quantity are posted at the running average cost price.</span></span> <span data-ttu-id="aa096-143">Portanto, o procedimento de fechamento de estoque é necessário para liquidar transações de saída para transações de recebimento com base no modelo de estoque atribuído a cada item.</span><span class="sxs-lookup"><span data-stu-id="aa096-143">Therefore, the inventory close procedure is required in order to settle issue transactions to receipt transactions, based on the inventory model that is assigned to each item.</span></span>




