---
title: Entradas de custo
description: Este artigo fornece informações sobre entradas de custo previsto e quando foram criadas. Uma entrada de custo estimada é um registro que marca a quantidade e os custos de um determinado evento.
author: AndersGirke
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventCostOnhandItem
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 19131
ms.assetid: dd2663d8-bcc0-47b1-b36d-57433143487c
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: shylaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c8dc87ed64c888078f606a2b4d2e35c7c81e78b0
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/02/2020
ms.locfileid: "3201851"
---
# <a name="cost-entries"></a><span data-ttu-id="7f36d-104">Entradas de custo</span><span class="sxs-lookup"><span data-stu-id="7f36d-104">Cost entries</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="7f36d-105">Este artigo fornece informações sobre entradas de custo previsto e quando foram criadas.</span><span class="sxs-lookup"><span data-stu-id="7f36d-105">This article provides information about cost entries and when they are created.</span></span> <span data-ttu-id="7f36d-106">Uma entrada de custo estimada é um registro que marca a quantidade e os custos de um determinado evento.</span><span class="sxs-lookup"><span data-stu-id="7f36d-106">A cost entry is a record that registers the quantity and cost of a given event.</span></span>

<span data-ttu-id="7f36d-107">As entradas de custo são agregações de transações de estoque que são registradas nas dimensões de estoque financeiras ativas.</span><span class="sxs-lookup"><span data-stu-id="7f36d-107">Cost entries are aggregations of inventory transactions that are recorded on active financial inventory dimensions.</span></span>

## <a name="examples"></a><span data-ttu-id="7f36d-108">Exemplos</span><span class="sxs-lookup"><span data-stu-id="7f36d-108">Examples</span></span>
### <a name="example-1-no-cost-entries-are-created"></a><span data-ttu-id="7f36d-109">Exemplo 1: Nenhuma entrada de custo é criada</span><span class="sxs-lookup"><span data-stu-id="7f36d-109">Example 1: No cost entries are created</span></span>

<span data-ttu-id="7f36d-110">Um evento do diário de transferência é registrado.</span><span class="sxs-lookup"><span data-stu-id="7f36d-110">A transfer journal event is registered.</span></span> <span data-ttu-id="7f36d-111">O evento transfere uma parte do item A da localização A para a localização B. A dimensão de estoque do local não será considerada parte do objeto de custo.</span><span class="sxs-lookup"><span data-stu-id="7f36d-111">The event transfers one piece of item A from location A to location B. The Location inventory dimension isn't considered part of the cost object.</span></span> <span data-ttu-id="7f36d-112">Sendo assim, o evento cria duas transações de estoque e nenhuma entrada de custo.</span><span class="sxs-lookup"><span data-stu-id="7f36d-112">Therefore, the event creates two inventory transactions and no cost entries.</span></span>

### <a name="example-2-cost-entries-are-created"></a><span data-ttu-id="7f36d-113">Exemplo 2: Entradas de custo são criadas</span><span class="sxs-lookup"><span data-stu-id="7f36d-113">Example 2: Cost entries are created</span></span>

<span data-ttu-id="7f36d-114">Um evento do diário de transferência é registrado.</span><span class="sxs-lookup"><span data-stu-id="7f36d-114">A transfer journal event is registered.</span></span> <span data-ttu-id="7f36d-115">O evento transfere uma parte do item A da localização 1 para a localização 2</span><span class="sxs-lookup"><span data-stu-id="7f36d-115">The event transfers one piece of item A from site 1 to site 2.</span></span> <span data-ttu-id="7f36d-116">A dimensão de estoque do local é considerada parte do objeto de custo.</span><span class="sxs-lookup"><span data-stu-id="7f36d-116">The Site inventory dimension is considered part of the cost object.</span></span> <span data-ttu-id="7f36d-117">Sendo assim, o evento cria duas transações de estoque e duas entradas de custo.</span><span class="sxs-lookup"><span data-stu-id="7f36d-117">Therefore, the event creates two inventory transactions and two cost entries.</span></span>

### <a name="example-3-one-cost-entry-is-created"></a><span data-ttu-id="7f36d-118">Exemplo 3: Uma entrada de custo é criada</span><span class="sxs-lookup"><span data-stu-id="7f36d-118">Example 3: One cost entry is created</span></span>

<span data-ttu-id="7f36d-119">Um evento de recebimento de produto é registrado para uma ordem de compra.</span><span class="sxs-lookup"><span data-stu-id="7f36d-119">A product receipt event is registered for a purchase order.</span></span> <span data-ttu-id="7f36d-120">O evento registra 100 peças do item A a um custo unitário de 10,00 reais (BRL).</span><span class="sxs-lookup"><span data-stu-id="7f36d-120">The event registers 100 pieces of item A at a unit cost of 10.00 U.S. dollars (USD).</span></span> <span data-ttu-id="7f36d-121">Como o item A usa um número de série para rastrear a finalidade do gerenciamento de estoque, um número de série exclusivo é criado para cada item recebido.</span><span class="sxs-lookup"><span data-stu-id="7f36d-121">Because item A uses a serial number to track the purpose of inventory management, a unique serial number is created for each item that is received.</span></span> <span data-ttu-id="7f36d-122">Sendo assim, o evento cria 100 transações de estoque e uma entrada de custo.</span><span class="sxs-lookup"><span data-stu-id="7f36d-122">Therefore, the event creates 100 inventory transactions and one cost entry.</span></span>

## <a name="cost-entries-page"></a><span data-ttu-id="7f36d-123">Página de entradas de custo</span><span class="sxs-lookup"><span data-stu-id="7f36d-123">Cost entries page</span></span>
<span data-ttu-id="7f36d-124">A nova página de **Entradas de custo** permite exibir e controlar os registros de custos e de quantidades.</span><span class="sxs-lookup"><span data-stu-id="7f36d-124">The new **Cost entries** page lets you view and control registrations of quantities and costs.</span></span> <span data-ttu-id="7f36d-125">Essa página complementa as páginas **Transação de estoque** e **Liquidações de estoque**.</span><span class="sxs-lookup"><span data-stu-id="7f36d-125">This page complements the **Inventory transaction** and **Inventory settlement** pages.</span></span> <span data-ttu-id="7f36d-126">Os registros são registrados em ordem cronológica para um evento.</span><span class="sxs-lookup"><span data-stu-id="7f36d-126">Records are registered in chronological order for an event.</span></span> <span data-ttu-id="7f36d-127">Consequentemente, você pode encontrar e controlar rapidamente os custos acumulados de um evento específico ou todos os eventos relacionados a um documento.</span><span class="sxs-lookup"><span data-stu-id="7f36d-127">Therefore, you can quickly find and control the accumulated costs of a specific event or all events that are related to a document.</span></span> <span data-ttu-id="7f36d-128">Veja a seguir um exemplo:</span><span class="sxs-lookup"><span data-stu-id="7f36d-128">Here is an example:</span></span>

-   <span data-ttu-id="7f36d-129">Um evento de recebimento de produto é registrado para o item A. Cem peças são recebidas a um custo unitário de BRL 10,00.</span><span class="sxs-lookup"><span data-stu-id="7f36d-129">A product receipt event is registered for item A. One hundred pieces are received at a unit cost of 10.00 USD.</span></span>
-   <span data-ttu-id="7f36d-130">Alguns dias após o evento de fatura ser registrado, o custo aumenta para BRL 11,00.</span><span class="sxs-lookup"><span data-stu-id="7f36d-130">A few days after the invoice event is registered, the cost increases to 11.00 USD.</span></span> <span data-ttu-id="7f36d-131">Portanto, o valor total é de BRL 1.100,00.</span><span class="sxs-lookup"><span data-stu-id="7f36d-131">Therefore, the total amount is 1,100 USD.</span></span> <span data-ttu-id="7f36d-132">Um segundo comprovante é criado para esclarecer a diferença de 100 reais.</span><span class="sxs-lookup"><span data-stu-id="7f36d-132">A second voucher is created to account for the difference of 100 USD.</span></span>
-   <span data-ttu-id="7f36d-133">Alguns dias depois, um encargo diverso de 15,00 reais para cobrir o custo de transporte é registrado na ordem de compra.</span><span class="sxs-lookup"><span data-stu-id="7f36d-133">A few days later, a miscellaneous charge of 15.00 USD to cover the transportation cost is registered on the purchase order.</span></span>

| <span data-ttu-id="7f36d-134">Comprovante</span><span class="sxs-lookup"><span data-stu-id="7f36d-134">Voucher</span></span> | <span data-ttu-id="7f36d-135">Data</span><span class="sxs-lookup"><span data-stu-id="7f36d-135">Date</span></span>       | <span data-ttu-id="7f36d-136">Demonstrativo</span><span class="sxs-lookup"><span data-stu-id="7f36d-136">Reference</span></span>      | <span data-ttu-id="7f36d-137">Número</span><span class="sxs-lookup"><span data-stu-id="7f36d-137">Number</span></span> | <span data-ttu-id="7f36d-138">ID do lote</span><span class="sxs-lookup"><span data-stu-id="7f36d-138">Lot ID</span></span>  | <span data-ttu-id="7f36d-139">Quantidade</span><span class="sxs-lookup"><span data-stu-id="7f36d-139">Quantity</span></span> | <span data-ttu-id="7f36d-140">Valor</span><span class="sxs-lookup"><span data-stu-id="7f36d-140">Amount</span></span>  |
|---------|------------|----------------|--------|---------|---------------|----|
| <span data-ttu-id="7f36d-141">00001</span><span class="sxs-lookup"><span data-stu-id="7f36d-141">00001</span></span>   | <span data-ttu-id="7f36d-142">01/01/2015</span><span class="sxs-lookup"><span data-stu-id="7f36d-142">01-01-2015</span></span> | <span data-ttu-id="7f36d-143">Ordem de Compra</span><span class="sxs-lookup"><span data-stu-id="7f36d-143">Purchase order</span></span> | <span data-ttu-id="7f36d-144">100001</span><span class="sxs-lookup"><span data-stu-id="7f36d-144">100001</span></span> | <span data-ttu-id="7f36d-145">0000101</span><span class="sxs-lookup"><span data-stu-id="7f36d-145">0000101</span></span> | <span data-ttu-id="7f36d-146">100,00</span><span class="sxs-lookup"><span data-stu-id="7f36d-146">100.00</span></span>   | <span data-ttu-id="7f36d-147">1.000,00</span><span class="sxs-lookup"><span data-stu-id="7f36d-147">1000.00</span></span> |
| <span data-ttu-id="7f36d-148">00002</span><span class="sxs-lookup"><span data-stu-id="7f36d-148">00002</span></span>   | <span data-ttu-id="7f36d-149">20/01/2015</span><span class="sxs-lookup"><span data-stu-id="7f36d-149">20-01-2015</span></span> | <span data-ttu-id="7f36d-150">Ordem de Compra</span><span class="sxs-lookup"><span data-stu-id="7f36d-150">Purchase order</span></span> | <span data-ttu-id="7f36d-151">100001</span><span class="sxs-lookup"><span data-stu-id="7f36d-151">100001</span></span> | <span data-ttu-id="7f36d-152">0000101</span><span class="sxs-lookup"><span data-stu-id="7f36d-152">0000101</span></span> |          | <span data-ttu-id="7f36d-153">100,00</span><span class="sxs-lookup"><span data-stu-id="7f36d-153">100.00</span></span>  |
| <span data-ttu-id="7f36d-154">00003</span><span class="sxs-lookup"><span data-stu-id="7f36d-154">00003</span></span>   | <span data-ttu-id="7f36d-155">31/01/2015</span><span class="sxs-lookup"><span data-stu-id="7f36d-155">31-01-2015</span></span> | <span data-ttu-id="7f36d-156">Ajuste</span><span class="sxs-lookup"><span data-stu-id="7f36d-156">Adjustment</span></span>     | <span data-ttu-id="7f36d-157">100001</span><span class="sxs-lookup"><span data-stu-id="7f36d-157">100001</span></span> | <span data-ttu-id="7f36d-158">0000101</span><span class="sxs-lookup"><span data-stu-id="7f36d-158">0000101</span></span> |          | <span data-ttu-id="7f36d-159">15,00</span><span class="sxs-lookup"><span data-stu-id="7f36d-159">15.00</span></span>   |

<span data-ttu-id="7f36d-160">A página **Entradas de custo** permite a filtragem por ID de documento e data de documento.</span><span class="sxs-lookup"><span data-stu-id="7f36d-160">The **Cost entries** page enables filtering by document ID and document date.</span></span> 

> [!NOTE]
> <span data-ttu-id="7f36d-161">As entradas de custo estão disponíveis somente para [objetos de custo](cost-object.md) ou produtos liberados.</span><span class="sxs-lookup"><span data-stu-id="7f36d-161">Cost entries are available only for [cost objects](cost-object.md) or released products.</span></span>

<a name="additional-resources"></a><span data-ttu-id="7f36d-162">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="7f36d-162">Additional resources</span></span>
--------

[<span data-ttu-id="7f36d-163">Objetos de custo</span><span class="sxs-lookup"><span data-stu-id="7f36d-163">Cost objects</span></span>](cost-object.md)



