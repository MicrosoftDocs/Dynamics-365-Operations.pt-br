---
title: Valores de objeto de estoque
description: Este artigo fornece informações sobre como os valores de um objeto do estoque são calculados.
author: AndersGirke
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventCostOnhandItem
audience: Application User
ms.reviewer: kamaybac
ms.custom: 19111
ms.assetid: 56a7c8ba-bf4a-4b1d-918d-56bb96926c4f
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 543253714b3cf318ad5f6092b190e777772f956f
ms.sourcegitcommit: 34b478f175348d99df4f2f0c2f6c0c21b6b2660a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/16/2021
ms.locfileid: "5910128"
---
# <a name="inventory-object-values"></a><span data-ttu-id="b5e02-103">Valores de objeto de estoque</span><span class="sxs-lookup"><span data-stu-id="b5e02-103">Inventory object values</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b5e02-104">Este artigo fornece informações sobre como os valores de um objeto do estoque são calculados.</span><span class="sxs-lookup"><span data-stu-id="b5e02-104">This article provides information about how the values of an inventory object are calculated.</span></span> 

<span data-ttu-id="b5e02-105">Uma nova funcionalidade chamada de **quantidade física** permite visualizar os valores de um objeto de estoque específico.</span><span class="sxs-lookup"><span data-stu-id="b5e02-105">A new functionality that is named **physical quantity** lets you see the values of a specific inventory object.</span></span> 

<span data-ttu-id="b5e02-106">Um objeto de custo representa o nível da entidade onde a contabilidade de estoque é executada.</span><span class="sxs-lookup"><span data-stu-id="b5e02-106">A cost object represents the entity level where inventory accounting is performed.</span></span> <span data-ttu-id="b5e02-107">Para obter mais informações sobre os objetos de custo, consulte [Objetos de custo](cost-object.md).</span><span class="sxs-lookup"><span data-stu-id="b5e02-107">For more information about cost objects, see [Cost objects](cost-object.md).</span></span> 

<span data-ttu-id="b5e02-108">Para visualizar os valores de um objeto de estoque específico, clique em **Quantidade física** na página **Objeto de custo**.</span><span class="sxs-lookup"><span data-stu-id="b5e02-108">To see the values of a specific inventory object, click **Physical quantity** on the **Cost object** page.</span></span> <span data-ttu-id="b5e02-109">Veja aqui como o valor de um objeto de estoque é calculado:</span><span class="sxs-lookup"><span data-stu-id="b5e02-109">Here is how the value of an inventory object is calculated:</span></span> 

<span data-ttu-id="b5e02-110">Objeto de estoque. Valor = Objeto de custo. Custo unitário médio x Objeto de estoque.Quantidade</span><span class="sxs-lookup"><span data-stu-id="b5e02-110">Inventory object.Value = Cost object.Average unit cost × Inventory object.Quantity</span></span> 

<span data-ttu-id="b5e02-111">Os exemplos a seguir mostram como os valores de um objeto de estoque e de um objeto de custo são calculados.</span><span class="sxs-lookup"><span data-stu-id="b5e02-111">The following example shows how the values of an inventory object and a cost object are calculated.</span></span> <span data-ttu-id="b5e02-112">Dois eventos de recebimento de produtos são registrados para o item A:</span><span class="sxs-lookup"><span data-stu-id="b5e02-112">Two product receipt events are registered on item A:</span></span>

-   <span data-ttu-id="b5e02-113">Recebimento de produtos 1: Quantidade = 100 pcs., Valor = $1.000,00, Local = 1, Depósito = 11, Nº do lote</span><span class="sxs-lookup"><span data-stu-id="b5e02-113">Product receipt 1: Quantity = 100 pcs., Amount = $1,000.00, Site = 1, Warehouse =11, Batch No.</span></span> <span data-ttu-id="b5e02-114">= B1</span><span class="sxs-lookup"><span data-stu-id="b5e02-114">= B1</span></span>
-   <span data-ttu-id="b5e02-115">Recebimento de produtos 2 = Quantidade = 50 pcs., Valor = $800,00, Local = 1, Depósito = 11, Nº do lote</span><span class="sxs-lookup"><span data-stu-id="b5e02-115">Product receipt 2: Quantity = 50 pcs., Amount = $800.00, Site = 1, Warehouse =11, Batch No.</span></span> <span data-ttu-id="b5e02-116">= B2</span><span class="sxs-lookup"><span data-stu-id="b5e02-116">= B2</span></span>

<span data-ttu-id="b5e02-117">A tabela a seguir mostra o resultado do cálculo para um objeto de custo.</span><span class="sxs-lookup"><span data-stu-id="b5e02-117">The following table shows the calculation result for a cost object.</span></span> <span data-ttu-id="b5e02-118">Você pode exibir o resultado na página **Objeto de custo**.</span><span class="sxs-lookup"><span data-stu-id="b5e02-118">You can view the result on the **Cost object** page.</span></span>

<table style="width:100%;">
<colgroup>
<col width="14%" />
<col width="14%" />
<col width="14%" />
<col width="14%" />
<col width="14%" />
<col width="14%" />
<col width="14%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b5e02-119">Tipo de Objeto</span><span class="sxs-lookup"><span data-stu-id="b5e02-119">Object type</span></span></th>
<th><span data-ttu-id="b5e02-120">Nº do item</span><span class="sxs-lookup"><span data-stu-id="b5e02-120">Item number</span></span></th>
<th><span data-ttu-id="b5e02-121">Local</span><span class="sxs-lookup"><span data-stu-id="b5e02-121">Site</span></span></th>
<th><span data-ttu-id="b5e02-122">Quantidade</span><span class="sxs-lookup"><span data-stu-id="b5e02-122">Quantity</span></span></th>
<th><span data-ttu-id="b5e02-123">Unidade de estoque</span><span class="sxs-lookup"><span data-stu-id="b5e02-123">Inventory unit</span></span></th>
<th><span data-ttu-id="b5e02-124">Valor</span><span class="sxs-lookup"><span data-stu-id="b5e02-124">Value</span></span></th>
<th><span data-ttu-id="b5e02-125">Custo unitário médio</span><span class="sxs-lookup"><span data-stu-id="b5e02-125">Average unit cost</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="b5e02-126">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="b5e02-126">Cost object</span></span></td>
<td><span data-ttu-id="b5e02-127">S</span><span class="sxs-lookup"><span data-stu-id="b5e02-127">A</span></span></td>
<td><span data-ttu-id="b5e02-128">1</span><span class="sxs-lookup"><span data-stu-id="b5e02-128">1</span></span></td>
<td><span data-ttu-id="b5e02-129">150</span><span class="sxs-lookup"><span data-stu-id="b5e02-129">150</span></span></td>
<td><span data-ttu-id="b5e02-130">Pçs.</span><span class="sxs-lookup"><span data-stu-id="b5e02-130">Pcs.</span></span></td>
<td><p><span data-ttu-id="b5e02-131">$1.800,00</span><span class="sxs-lookup"><span data-stu-id="b5e02-131">$1800.00</span></span></p></td>
<td><p><span data-ttu-id="b5e02-132">$12,00</span><span class="sxs-lookup"><span data-stu-id="b5e02-132">$12.00</span></span></p></td>
</tr>
</tbody>
</table>

<span data-ttu-id="b5e02-133">A tabela a seguir mostra o resultado do cálculo para um objeto de estoque.</span><span class="sxs-lookup"><span data-stu-id="b5e02-133">The following table shows the calculation result for an inventory object.</span></span> <span data-ttu-id="b5e02-134">Você pode exibir o resultado clicando em **Quantidade física** na página **Objeto de custo**.</span><span class="sxs-lookup"><span data-stu-id="b5e02-134">You can view the result by clicking **Physical quantity** on the **Cost object** page.</span></span>

<table style="width:100%;">
<colgroup>
<col width="11%" />
<col width="11%" />
<col width="11%" />
<col width="11%" />
<col width="11%" />
<col width="11%" />
<col width="11%" />
<col width="11%" />
<col width="11%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b5e02-135">Tipo de Objeto</span><span class="sxs-lookup"><span data-stu-id="b5e02-135">Object type</span></span></th>
<th><span data-ttu-id="b5e02-136">Nº do item</span><span class="sxs-lookup"><span data-stu-id="b5e02-136">Item number</span></span></th>
<th><span data-ttu-id="b5e02-137">Local</span><span class="sxs-lookup"><span data-stu-id="b5e02-137">Site</span></span></th>
<th><span data-ttu-id="b5e02-138">Depósito</span><span class="sxs-lookup"><span data-stu-id="b5e02-138">Warehouse</span></span></th>
<th><span data-ttu-id="b5e02-139">Nº do lote</span><span class="sxs-lookup"><span data-stu-id="b5e02-139">Batch No.</span></span></th>
<th><span data-ttu-id="b5e02-140">Quantidade</span><span class="sxs-lookup"><span data-stu-id="b5e02-140">Quantity</span></span></th>
<th><span data-ttu-id="b5e02-141">Unidade de estoque</span><span class="sxs-lookup"><span data-stu-id="b5e02-141">Inventory unit</span></span></th>
<th><span data-ttu-id="b5e02-142">Valor</span><span class="sxs-lookup"><span data-stu-id="b5e02-142">Value</span></span></th>
<th><span data-ttu-id="b5e02-143">Custo unitário médio</span><span class="sxs-lookup"><span data-stu-id="b5e02-143">Average unit cost</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="b5e02-144">Objeto de estoque</span><span class="sxs-lookup"><span data-stu-id="b5e02-144">Inventory object</span></span></td>
<td><span data-ttu-id="b5e02-145">S</span><span class="sxs-lookup"><span data-stu-id="b5e02-145">A</span></span></td>
<td><span data-ttu-id="b5e02-146">1</span><span class="sxs-lookup"><span data-stu-id="b5e02-146">1</span></span></td>
<td><span data-ttu-id="b5e02-147">11</span><span class="sxs-lookup"><span data-stu-id="b5e02-147">11</span></span></td>
<td><span data-ttu-id="b5e02-148">B1</span><span class="sxs-lookup"><span data-stu-id="b5e02-148">B1</span></span></td>
<td><span data-ttu-id="b5e02-149">100</span><span class="sxs-lookup"><span data-stu-id="b5e02-149">100</span></span></td>
<td><span data-ttu-id="b5e02-150">Pçs.</span><span class="sxs-lookup"><span data-stu-id="b5e02-150">Pcs.</span></span></td>
<td><p><span data-ttu-id="b5e02-151">$1.200,00</span><span class="sxs-lookup"><span data-stu-id="b5e02-151">$1200.00</span></span></p></td>
<td><p><span data-ttu-id="b5e02-152">$12,00</span><span class="sxs-lookup"><span data-stu-id="b5e02-152">$12.00</span></span></p></td>
</tr>
<tr class="even">
<td><span data-ttu-id="b5e02-153">Objeto de estoque</span><span class="sxs-lookup"><span data-stu-id="b5e02-153">Inventory object</span></span></td>
<td><span data-ttu-id="b5e02-154">A</span><span class="sxs-lookup"><span data-stu-id="b5e02-154">A</span></span></td>
<td><span data-ttu-id="b5e02-155">1</span><span class="sxs-lookup"><span data-stu-id="b5e02-155">1</span></span></td>
<td><span data-ttu-id="b5e02-156">11</span><span class="sxs-lookup"><span data-stu-id="b5e02-156">11</span></span></td>
<td><span data-ttu-id="b5e02-157">B2</span><span class="sxs-lookup"><span data-stu-id="b5e02-157">B2</span></span></td>
<td><span data-ttu-id="b5e02-158">50</span><span class="sxs-lookup"><span data-stu-id="b5e02-158">50</span></span></td>
<td><span data-ttu-id="b5e02-159">Pçs.</span><span class="sxs-lookup"><span data-stu-id="b5e02-159">Pcs.</span></span></td>
<td><p><span data-ttu-id="b5e02-160">$600,00</span><span class="sxs-lookup"><span data-stu-id="b5e02-160">$600.00</span></span></p></td>
<td><p><span data-ttu-id="b5e02-161">$12,00</span><span class="sxs-lookup"><span data-stu-id="b5e02-161">$12.00</span></span></p></td>
</tr>
</tbody>
</table>



<a name="additional-resources"></a><span data-ttu-id="b5e02-162">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="b5e02-162">Additional resources</span></span>
--------

[<span data-ttu-id="b5e02-163">Objetos de custo</span><span class="sxs-lookup"><span data-stu-id="b5e02-163">Cost objects</span></span>](cost-object.md)

[<span data-ttu-id="b5e02-164">Entradas de custo</span><span class="sxs-lookup"><span data-stu-id="b5e02-164">Cost entries</span></span>](cost-entries.md)

[<span data-ttu-id="b5e02-165">Novidades e alterações</span><span class="sxs-lookup"><span data-stu-id="b5e02-165">What's new and changed</span></span>](../../fin-ops-core/fin-ops/get-started/whats-new-changed.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]