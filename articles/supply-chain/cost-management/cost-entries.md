---
title: Entradas de custo
description: "Este artigo fornece informações sobre entradas de custo previsto e quando foram criadas. Uma entrada de custo estimada é um registro que marca a quantidade e os custos de um determinado evento."
author: AndersGirke
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: InventCostOnhandItem
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 19131
ms.assetid: dd2663d8-bcc0-47b1-b36d-57433143487c
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 39e31b7290668ae6d84b699a45fcd999c558e841
ms.contentlocale: pt-br
ms.lasthandoff: 04/13/2018

---

# <a name="cost-entries"></a><span data-ttu-id="e2be3-104">Entradas de custo</span><span class="sxs-lookup"><span data-stu-id="e2be3-104">Cost entries</span></span>

[!INCLUDE [banner](../includes/banner.md)]

<span data-ttu-id="e2be3-105">Este artigo fornece informações sobre entradas de custo previsto e quando foram criadas.</span><span class="sxs-lookup"><span data-stu-id="e2be3-105">This article provides information about cost entries and when they are created.</span></span> <span data-ttu-id="e2be3-106">Uma entrada de custo estimada é um registro que marca a quantidade e os custos de um determinado evento.</span><span class="sxs-lookup"><span data-stu-id="e2be3-106">A cost entry is a record that registers the quantity and cost of a given event.</span></span>

<span data-ttu-id="e2be3-107">As entradas de custo são agregações de transações de estoque que são registradas nas dimensões de estoque financeiras ativas.</span><span class="sxs-lookup"><span data-stu-id="e2be3-107">Cost entries are aggregations of inventory transactions that are recorded on active financial inventory dimensions.</span></span>

## <a name="examples"></a><span data-ttu-id="e2be3-108">Exemplos</span><span class="sxs-lookup"><span data-stu-id="e2be3-108">Examples</span></span>
### <a name="example-1-no-cost-entries-are-created"></a><span data-ttu-id="e2be3-109">Exemplo 1: Nenhuma entrada de custo é criada</span><span class="sxs-lookup"><span data-stu-id="e2be3-109">Example 1: No cost entries are created</span></span>

<span data-ttu-id="e2be3-110">Um evento do diário de transferência é registrado.</span><span class="sxs-lookup"><span data-stu-id="e2be3-110">A transfer journal event is registered.</span></span> <span data-ttu-id="e2be3-111">O evento transfere uma parte do item A da localização A para a localização B. A dimensão de estoque do local não será considerada parte do objeto de custo.</span><span class="sxs-lookup"><span data-stu-id="e2be3-111">The event transfers one piece of item A from location A to location B. The Location inventory dimension isn't considered part of the cost object.</span></span> <span data-ttu-id="e2be3-112">Sendo assim, o evento cria duas transações de estoque e nenhuma entrada de custo.</span><span class="sxs-lookup"><span data-stu-id="e2be3-112">Therefore, the event creates two inventory transactions and no cost entries.</span></span>

### <a name="example-2-cost-entries-are-created"></a><span data-ttu-id="e2be3-113">Exemplo 2: Entradas de custo são criadas</span><span class="sxs-lookup"><span data-stu-id="e2be3-113">Example 2: Cost entries are created</span></span>

<span data-ttu-id="e2be3-114">Um evento do diário de transferência é registrado.</span><span class="sxs-lookup"><span data-stu-id="e2be3-114">A transfer journal event is registered.</span></span> <span data-ttu-id="e2be3-115">O evento transfere uma parte do item A da localização 1 para a localização 2</span><span class="sxs-lookup"><span data-stu-id="e2be3-115">The event transfers one piece of item A from site 1 to site 2.</span></span> <span data-ttu-id="e2be3-116">A dimensão de estoque do local é considerada parte do objeto de custo.</span><span class="sxs-lookup"><span data-stu-id="e2be3-116">The Site inventory dimension is considered part of the cost object.</span></span> <span data-ttu-id="e2be3-117">Sendo assim, o evento cria duas transações de estoque e duas entradas de custo.</span><span class="sxs-lookup"><span data-stu-id="e2be3-117">Therefore, the event creates two inventory transactions and two cost entries.</span></span>

### <a name="example-3-one-cost-entry-is-created"></a><span data-ttu-id="e2be3-118">Exemplo 3: Uma entrada de custo é criada</span><span class="sxs-lookup"><span data-stu-id="e2be3-118">Example 3: One cost entry is created</span></span>

<span data-ttu-id="e2be3-119">Um evento de recebimento de produto é registrado para uma ordem de compra.</span><span class="sxs-lookup"><span data-stu-id="e2be3-119">A product receipt event is registered for a purchase order.</span></span> <span data-ttu-id="e2be3-120">O evento registra 100 peças do item A a um custo unitário de 10,00 reais (BRL).</span><span class="sxs-lookup"><span data-stu-id="e2be3-120">The event registers 100 pieces of item A at a unit cost of 10.00 U.S. dollars (USD).</span></span> <span data-ttu-id="e2be3-121">Como o item A usa um número de série para rastrear a finalidade do gerenciamento de estoque, um número de série exclusivo é criado para cada item recebido.</span><span class="sxs-lookup"><span data-stu-id="e2be3-121">Because item A uses a serial number to track the purpose of inventory management, a unique serial number is created for each item that is received.</span></span> <span data-ttu-id="e2be3-122">Sendo assim, o evento cria 100 transações de estoque e uma entrada de custo.</span><span class="sxs-lookup"><span data-stu-id="e2be3-122">Therefore, the event creates 100 inventory transactions and one cost entry.</span></span>

## <a name="cost-entries-page"></a><span data-ttu-id="e2be3-123">Página de entradas de custo</span><span class="sxs-lookup"><span data-stu-id="e2be3-123">Cost entries page</span></span>
<span data-ttu-id="e2be3-124">A nova página de **Entradas de custo** permite exibir e controlar os registros de custos e de quantidades.</span><span class="sxs-lookup"><span data-stu-id="e2be3-124">The new **Cost entries** page lets you view and control registrations of quantities and costs.</span></span> <span data-ttu-id="e2be3-125">Essa página complementa as páginas **Transação de estoque** e **Liquidações de estoque**.</span><span class="sxs-lookup"><span data-stu-id="e2be3-125">This page complements the **Inventory transaction** and **Inventory settlement** pages.</span></span> <span data-ttu-id="e2be3-126">Os registros são registrados em ordem cronológica para um evento.</span><span class="sxs-lookup"><span data-stu-id="e2be3-126">Records are registered in chronological order for an event.</span></span> <span data-ttu-id="e2be3-127">Consequentemente, você pode encontrar e controlar rapidamente os custos acumulados de um evento específico ou todos os eventos relacionados a um documento.</span><span class="sxs-lookup"><span data-stu-id="e2be3-127">Therefore, you can quickly find and control the accumulated costs of a specific event or all events that are related to a document.</span></span> <span data-ttu-id="e2be3-128">Veja a seguir um exemplo:</span><span class="sxs-lookup"><span data-stu-id="e2be3-128">Here is an example:</span></span>

-   <span data-ttu-id="e2be3-129">Um evento de recebimento de produto é registrado para o item A. Cem peças são recebidas a um custo unitário de BRL 10,00.</span><span class="sxs-lookup"><span data-stu-id="e2be3-129">A product receipt event is registered for item A. One hundred pieces are received at a unit cost of 10.00 USD.</span></span>
-   <span data-ttu-id="e2be3-130">Alguns dias após o evento de fatura ser registrado, o custo aumenta para BRL 11,00.</span><span class="sxs-lookup"><span data-stu-id="e2be3-130">A few days after the invoice event is registered, the cost increases to 11.00 USD.</span></span> <span data-ttu-id="e2be3-131">Portanto, o valor total é de BRL 1.100,00.</span><span class="sxs-lookup"><span data-stu-id="e2be3-131">Therefore, the total amount is 1,100 USD.</span></span> <span data-ttu-id="e2be3-132">Um segundo comprovante é criado para esclarecer a diferença de 100 reais.</span><span class="sxs-lookup"><span data-stu-id="e2be3-132">A second voucher is created to account for the difference of 100 USD.</span></span>
-   <span data-ttu-id="e2be3-133">Alguns dias depois, um encargo diverso de 15,00 reais para cobrir o custo de transporte é registrado na ordem de compra.</span><span class="sxs-lookup"><span data-stu-id="e2be3-133">A few days later, a miscellaneous charge of 15.00 USD to cover the transportation cost is registered on the purchase order.</span></span>

| <span data-ttu-id="e2be3-134">Comprovante</span><span class="sxs-lookup"><span data-stu-id="e2be3-134">Voucher</span></span> | <span data-ttu-id="e2be3-135">Data</span><span class="sxs-lookup"><span data-stu-id="e2be3-135">Date</span></span>       | <span data-ttu-id="e2be3-136">Demonstrativo</span><span class="sxs-lookup"><span data-stu-id="e2be3-136">Reference</span></span>      | <span data-ttu-id="e2be3-137">Número</span><span class="sxs-lookup"><span data-stu-id="e2be3-137">Number</span></span> | <span data-ttu-id="e2be3-138">ID do lote</span><span class="sxs-lookup"><span data-stu-id="e2be3-138">Lot ID</span></span>  | <span data-ttu-id="e2be3-139">Quantidade</span><span class="sxs-lookup"><span data-stu-id="e2be3-139">Quantity</span></span> | <span data-ttu-id="e2be3-140">Valor</span><span class="sxs-lookup"><span data-stu-id="e2be3-140">Amount</span></span>  |
|---------|------------|----------------|--------|---------|---------------|----|
| <span data-ttu-id="e2be3-141">00001</span><span class="sxs-lookup"><span data-stu-id="e2be3-141">00001</span></span>   | <span data-ttu-id="e2be3-142">01/01/2015</span><span class="sxs-lookup"><span data-stu-id="e2be3-142">01-01-2015</span></span> | <span data-ttu-id="e2be3-143">Ordem de Compra</span><span class="sxs-lookup"><span data-stu-id="e2be3-143">Purchase order</span></span> | <span data-ttu-id="e2be3-144">100001</span><span class="sxs-lookup"><span data-stu-id="e2be3-144">100001</span></span> | <span data-ttu-id="e2be3-145">0000101</span><span class="sxs-lookup"><span data-stu-id="e2be3-145">0000101</span></span> | <span data-ttu-id="e2be3-146">100,00</span><span class="sxs-lookup"><span data-stu-id="e2be3-146">100.00</span></span>   | <span data-ttu-id="e2be3-147">1.000,00</span><span class="sxs-lookup"><span data-stu-id="e2be3-147">1000.00</span></span> |
| <span data-ttu-id="e2be3-148">00002</span><span class="sxs-lookup"><span data-stu-id="e2be3-148">00002</span></span>   | <span data-ttu-id="e2be3-149">20/01/2015</span><span class="sxs-lookup"><span data-stu-id="e2be3-149">20-01-2015</span></span> | <span data-ttu-id="e2be3-150">Ordem de Compra</span><span class="sxs-lookup"><span data-stu-id="e2be3-150">Purchase order</span></span> | <span data-ttu-id="e2be3-151">100001</span><span class="sxs-lookup"><span data-stu-id="e2be3-151">100001</span></span> | <span data-ttu-id="e2be3-152">0000101</span><span class="sxs-lookup"><span data-stu-id="e2be3-152">0000101</span></span> |          | <span data-ttu-id="e2be3-153">100,00</span><span class="sxs-lookup"><span data-stu-id="e2be3-153">100.00</span></span>  |
| <span data-ttu-id="e2be3-154">00003</span><span class="sxs-lookup"><span data-stu-id="e2be3-154">00003</span></span>   | <span data-ttu-id="e2be3-155">31/01/2015</span><span class="sxs-lookup"><span data-stu-id="e2be3-155">31-01-2015</span></span> | <span data-ttu-id="e2be3-156">Ajuste</span><span class="sxs-lookup"><span data-stu-id="e2be3-156">Adjustment</span></span>     | <span data-ttu-id="e2be3-157">100001</span><span class="sxs-lookup"><span data-stu-id="e2be3-157">100001</span></span> | <span data-ttu-id="e2be3-158">0000101</span><span class="sxs-lookup"><span data-stu-id="e2be3-158">0000101</span></span> |          | <span data-ttu-id="e2be3-159">15,00</span><span class="sxs-lookup"><span data-stu-id="e2be3-159">15.00</span></span>   |

<span data-ttu-id="e2be3-160">A página **Entradas de custo** permite a filtragem por ID de documento e data de documento.</span><span class="sxs-lookup"><span data-stu-id="e2be3-160">The **Cost entries** page enables filtering by document ID and document date.</span></span> 

> [!NOTE]
> <span data-ttu-id="e2be3-161">As entradas de custo estão disponíveis somente para [objetos de custo](cost-object.md) ou produtos liberados.</span><span class="sxs-lookup"><span data-stu-id="e2be3-161">Cost entries are available only for [cost objects](cost-object.md) or released products.</span></span>

<a name="see-also"></a><span data-ttu-id="e2be3-162">Consulte também</span><span class="sxs-lookup"><span data-stu-id="e2be3-162">See also</span></span>
--------

[<span data-ttu-id="e2be3-163">Objetos de custo</span><span class="sxs-lookup"><span data-stu-id="e2be3-163">Cost objects</span></span>](cost-object.md)




