---
title: Exemplos e lógica de relatório de classificação por vencimento de estoque
description: Este tópico apresenta alguns exemplos que mostram como interpretar os resultados de um relatório de classificação por vencimento de estoque.
author: RichardLuan
manager: tfehr
ms.date: 5/29/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventAgingStorage, InventAgingStorageChart, InventAgingStorageDetails
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: riluan
ms.search.validFrom: 2020-5-29
ms.dyn365.ops.version: ''
ms.openlocfilehash: a6e708e4dc818f20fc8d835053da75c2fe9c98f6
ms.sourcegitcommit: cd339f48066b1d0fc740b513cb72ea19015acd16
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/02/2020
ms.locfileid: "3759535"
---
# <a name="inventory-aging-report-examples-and-logic"></a><span data-ttu-id="651e2-103">Exemplos e lógica de relatório de classificação por vencimento de estoque</span><span class="sxs-lookup"><span data-stu-id="651e2-103">Inventory aging report examples and logic</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="651e2-104">Este tópico apresenta alguns exemplos que mostram como interpretar os resultados de um relatório de **classificação por vencimento de estoque**.</span><span class="sxs-lookup"><span data-stu-id="651e2-104">This topic presents some examples that show how to interpret the results of an **Inventory aging** report.</span></span> <span data-ttu-id="651e2-105">Este relatório categoriza os valores de estoque e quantidade disponíveis para um item ou grupo de itens selecionado em vários buckets de período.</span><span class="sxs-lookup"><span data-stu-id="651e2-105">This report categorizes on-hand quantity and inventory values for a selected item or item group into several period buckets.</span></span> <span data-ttu-id="651e2-106">Este tópico também mostra a lógica interna do relatório.</span><span class="sxs-lookup"><span data-stu-id="651e2-106">This topic also shows the internal logic of the report.</span></span>

<span data-ttu-id="651e2-107">Os exemplos neste tópico mostram resultados que são apresentados em um relatório **Classificação por vencimento de estoque** padrão.</span><span class="sxs-lookup"><span data-stu-id="651e2-107">The examples in this topic show results that are presented on a standard **Inventory aging** report.</span></span> <span data-ttu-id="651e2-108">No entanto, em geral, recomendamos que você use a versão de [Armazenamento do relatório de classificação por vencimento de estoque](inventory-aging-report-storage.md) desse relatório, especialmente quando houver vários itens e depósitos que devem ser processados.</span><span class="sxs-lookup"><span data-stu-id="651e2-108">However, in general, we recommend that you use the [Inventory aging report storage](inventory-aging-report-storage.md) version of this report, especially when you have many items and warehouses that must be processed.</span></span> <span data-ttu-id="651e2-109">A classificação por vencimento de estoque salva cada relatório gerado, mostra os resultados como uma página interativa e um gráfico e permite exportar qualquer relatório salvo.</span><span class="sxs-lookup"><span data-stu-id="651e2-109">Inventory aging report storage saves each report that you generate, shows the results as an interactive page and a chart, and lets you export any saved report.</span></span>

## <a name="sample-data-that-is-used-in-these-examples"></a><span data-ttu-id="651e2-110">Dados de exemplo usados nestes exemplos</span><span class="sxs-lookup"><span data-stu-id="651e2-110">Sample data that is used in these examples</span></span>

<span data-ttu-id="651e2-111">Os exemplos neste tópico se baseiam nos dados de exemplo de transação de estoque descritos nesta seção.</span><span class="sxs-lookup"><span data-stu-id="651e2-111">The examples in this topic are based on the sample inventory transaction data that is described in this section.</span></span>

### <a name="storage-dimension-setup"></a><span data-ttu-id="651e2-112">Configuração de dimensão de armazenamento</span><span class="sxs-lookup"><span data-stu-id="651e2-112">Storage dimension setup</span></span>

<span data-ttu-id="651e2-113">O sistema de exemplo contém a seguinte configuração de dimensões de armazenamento.</span><span class="sxs-lookup"><span data-stu-id="651e2-113">The example system contains the following setup of storage dimensions.</span></span>

| <span data-ttu-id="651e2-114">Nome</span><span class="sxs-lookup"><span data-stu-id="651e2-114">Name</span></span>      | <span data-ttu-id="651e2-115">Ativos</span><span class="sxs-lookup"><span data-stu-id="651e2-115">Active</span></span> | <span data-ttu-id="651e2-116">Estoque físico</span><span class="sxs-lookup"><span data-stu-id="651e2-116">Physical inventory</span></span> | <span data-ttu-id="651e2-117">Estoque financeiro</span><span class="sxs-lookup"><span data-stu-id="651e2-117">Financial inventory</span></span> |
|-----------|--------|--------------------|---------------------|
| <span data-ttu-id="651e2-118">Site</span><span class="sxs-lookup"><span data-stu-id="651e2-118">Site</span></span>      | <span data-ttu-id="651e2-119">Sim</span><span class="sxs-lookup"><span data-stu-id="651e2-119">Yes</span></span>    | <span data-ttu-id="651e2-120">Sim</span><span class="sxs-lookup"><span data-stu-id="651e2-120">Yes</span></span>                | <span data-ttu-id="651e2-121">Sim</span><span class="sxs-lookup"><span data-stu-id="651e2-121">Yes</span></span>                 |
| <span data-ttu-id="651e2-122">Depósito</span><span class="sxs-lookup"><span data-stu-id="651e2-122">Warehouse</span></span> | <span data-ttu-id="651e2-123">Sim</span><span class="sxs-lookup"><span data-stu-id="651e2-123">Yes</span></span>    | <span data-ttu-id="651e2-124">Sim</span><span class="sxs-lookup"><span data-stu-id="651e2-124">Yes</span></span>                | <span data-ttu-id="651e2-125">Não</span><span class="sxs-lookup"><span data-stu-id="651e2-125">No</span></span>                  |

### <a name="inventory-model"></a><span data-ttu-id="651e2-126">Modelo de estoque</span><span class="sxs-lookup"><span data-stu-id="651e2-126">Inventory model</span></span>

<span data-ttu-id="651e2-127">Para o sistema de exemplo, o modelo de estoque para os produtos liberados é *PEPS*, e a configuração **Preço de custo** para o modelo de estoque é *Incluir valor físico*.</span><span class="sxs-lookup"><span data-stu-id="651e2-127">For the example system, the inventory model for the released products is *FIFO*, and the **Cost price** setting for the inventory model is *Include physical value*.</span></span>

### <a name="inventory-transactions"></a><span data-ttu-id="651e2-128">Transações de estoque</span><span class="sxs-lookup"><span data-stu-id="651e2-128">Inventory transactions</span></span>

<span data-ttu-id="651e2-129">O sistema de exemplo contém as seguintes transações de estoque para um produto liberado que tem o número de item *1.000*.</span><span class="sxs-lookup"><span data-stu-id="651e2-129">The example system contains the following inventory transactions for a released product that has the item number *1000*.</span></span>

| <span data-ttu-id="651e2-130">Demonstrativo</span><span class="sxs-lookup"><span data-stu-id="651e2-130">Reference</span></span>      | <span data-ttu-id="651e2-131">Site</span><span class="sxs-lookup"><span data-stu-id="651e2-131">Site</span></span> | <span data-ttu-id="651e2-132">Depósito</span><span class="sxs-lookup"><span data-stu-id="651e2-132">Warehouse</span></span> | <span data-ttu-id="651e2-133">Recebimento</span><span class="sxs-lookup"><span data-stu-id="651e2-133">Receipt</span></span>   | <span data-ttu-id="651e2-134">Problema</span><span class="sxs-lookup"><span data-stu-id="651e2-134">Issue</span></span> | <span data-ttu-id="651e2-135">Data física</span><span class="sxs-lookup"><span data-stu-id="651e2-135">Physical date</span></span> | <span data-ttu-id="651e2-136">Data financeira</span><span class="sxs-lookup"><span data-stu-id="651e2-136">Financial date</span></span> | <span data-ttu-id="651e2-137">Quantidade</span><span class="sxs-lookup"><span data-stu-id="651e2-137">Quantity</span></span> | <span data-ttu-id="651e2-138">Valor de custo</span><span class="sxs-lookup"><span data-stu-id="651e2-138">Cost amount</span></span> | <span data-ttu-id="651e2-139">Valor de custo físico</span><span class="sxs-lookup"><span data-stu-id="651e2-139">Physical cost amount</span></span> |
|----------------|------|-----------|-----------|-------|---------------|----------------|----------|-------------|----------------------|
| <span data-ttu-id="651e2-140">Ordem de Compra</span><span class="sxs-lookup"><span data-stu-id="651e2-140">Purchase order</span></span> | <span data-ttu-id="651e2-141">1</span><span class="sxs-lookup"><span data-stu-id="651e2-141">1</span></span>    | <span data-ttu-id="651e2-142">11</span><span class="sxs-lookup"><span data-stu-id="651e2-142">11</span></span>        | <span data-ttu-id="651e2-143">Comprado</span><span class="sxs-lookup"><span data-stu-id="651e2-143">Purchased</span></span> |       | <span data-ttu-id="651e2-144">15 de março</span><span class="sxs-lookup"><span data-stu-id="651e2-144">March 15</span></span>      | <span data-ttu-id="651e2-145">15 de março</span><span class="sxs-lookup"><span data-stu-id="651e2-145">March 15</span></span>       | <span data-ttu-id="651e2-146">10</span><span class="sxs-lookup"><span data-stu-id="651e2-146">10</span></span>       | <span data-ttu-id="651e2-147">1.000</span><span class="sxs-lookup"><span data-stu-id="651e2-147">1,000</span></span>       | <span data-ttu-id="651e2-148">1.000</span><span class="sxs-lookup"><span data-stu-id="651e2-148">1,000</span></span>                |
| <span data-ttu-id="651e2-149">Ordem de Compra</span><span class="sxs-lookup"><span data-stu-id="651e2-149">Purchase order</span></span> | <span data-ttu-id="651e2-150">2</span><span class="sxs-lookup"><span data-stu-id="651e2-150">2</span></span>    | <span data-ttu-id="651e2-151">21</span><span class="sxs-lookup"><span data-stu-id="651e2-151">21</span></span>        | <span data-ttu-id="651e2-152">Comprado</span><span class="sxs-lookup"><span data-stu-id="651e2-152">Purchased</span></span> |       | <span data-ttu-id="651e2-153">15 de março</span><span class="sxs-lookup"><span data-stu-id="651e2-153">March 15</span></span>      | <span data-ttu-id="651e2-154">15 de março</span><span class="sxs-lookup"><span data-stu-id="651e2-154">March 15</span></span>       | <span data-ttu-id="651e2-155">10</span><span class="sxs-lookup"><span data-stu-id="651e2-155">10</span></span>       | <span data-ttu-id="651e2-156">2,000</span><span class="sxs-lookup"><span data-stu-id="651e2-156">2,000</span></span>       | <span data-ttu-id="651e2-157">2,000</span><span class="sxs-lookup"><span data-stu-id="651e2-157">2,000</span></span>                |
| <span data-ttu-id="651e2-158">Ordem de Compra</span><span class="sxs-lookup"><span data-stu-id="651e2-158">Purchase order</span></span> | <span data-ttu-id="651e2-159">1</span><span class="sxs-lookup"><span data-stu-id="651e2-159">1</span></span>    | <span data-ttu-id="651e2-160">11</span><span class="sxs-lookup"><span data-stu-id="651e2-160">11</span></span>        | <span data-ttu-id="651e2-161">Recebida</span><span class="sxs-lookup"><span data-stu-id="651e2-161">Received</span></span>  |       | <span data-ttu-id="651e2-162">15 de abril</span><span class="sxs-lookup"><span data-stu-id="651e2-162">April 15</span></span>      |                | <span data-ttu-id="651e2-163">5</span><span class="sxs-lookup"><span data-stu-id="651e2-163">5</span></span>        |             | <span data-ttu-id="651e2-164">375</span><span class="sxs-lookup"><span data-stu-id="651e2-164">375</span></span>                  |
| <span data-ttu-id="651e2-165">Ordem de transferência</span><span class="sxs-lookup"><span data-stu-id="651e2-165">Transfer order</span></span> | <span data-ttu-id="651e2-166">1</span><span class="sxs-lookup"><span data-stu-id="651e2-166">1</span></span>    | <span data-ttu-id="651e2-167">11</span><span class="sxs-lookup"><span data-stu-id="651e2-167">11</span></span>        |           | <span data-ttu-id="651e2-168">Vendido</span><span class="sxs-lookup"><span data-stu-id="651e2-168">Sold</span></span>  | <span data-ttu-id="651e2-169">Maio de 2</span><span class="sxs-lookup"><span data-stu-id="651e2-169">May 2</span></span>         | <span data-ttu-id="651e2-170">Maio de 2</span><span class="sxs-lookup"><span data-stu-id="651e2-170">May 2</span></span>          | <span data-ttu-id="651e2-171">-5</span><span class="sxs-lookup"><span data-stu-id="651e2-171">-5</span></span>       | <span data-ttu-id="651e2-172">-458,33</span><span class="sxs-lookup"><span data-stu-id="651e2-172">-458.33</span></span>     | <span data-ttu-id="651e2-173">-458,33</span><span class="sxs-lookup"><span data-stu-id="651e2-173">-458.33</span></span>              |
| <span data-ttu-id="651e2-174">Ordem de transferência</span><span class="sxs-lookup"><span data-stu-id="651e2-174">Transfer order</span></span> | <span data-ttu-id="651e2-175">1</span><span class="sxs-lookup"><span data-stu-id="651e2-175">1</span></span>    | <span data-ttu-id="651e2-176">12</span><span class="sxs-lookup"><span data-stu-id="651e2-176">12</span></span>        | <span data-ttu-id="651e2-177">Comprado</span><span class="sxs-lookup"><span data-stu-id="651e2-177">Purchased</span></span> |       | <span data-ttu-id="651e2-178">Maio de 2</span><span class="sxs-lookup"><span data-stu-id="651e2-178">May 2</span></span>         | <span data-ttu-id="651e2-179">Maio de 2</span><span class="sxs-lookup"><span data-stu-id="651e2-179">May 2</span></span>          | <span data-ttu-id="651e2-180">5</span><span class="sxs-lookup"><span data-stu-id="651e2-180">5</span></span>        | <span data-ttu-id="651e2-181">458.33</span><span class="sxs-lookup"><span data-stu-id="651e2-181">458.33</span></span>      | <span data-ttu-id="651e2-182">458.33</span><span class="sxs-lookup"><span data-stu-id="651e2-182">458.33</span></span>               |
| <span data-ttu-id="651e2-183">Ordem de Venda</span><span class="sxs-lookup"><span data-stu-id="651e2-183">Sales order</span></span>    | <span data-ttu-id="651e2-184">1</span><span class="sxs-lookup"><span data-stu-id="651e2-184">1</span></span>    | <span data-ttu-id="651e2-185">12</span><span class="sxs-lookup"><span data-stu-id="651e2-185">12</span></span>        |           | <span data-ttu-id="651e2-186">Vendido</span><span class="sxs-lookup"><span data-stu-id="651e2-186">Sold</span></span>  | <span data-ttu-id="651e2-187">Maio de 3</span><span class="sxs-lookup"><span data-stu-id="651e2-187">May 3</span></span>         | <span data-ttu-id="651e2-188">Maio de 3</span><span class="sxs-lookup"><span data-stu-id="651e2-188">May 3</span></span>          | <span data-ttu-id="651e2-189">-1</span><span class="sxs-lookup"><span data-stu-id="651e2-189">-1</span></span>       | <span data-ttu-id="651e2-190">-91,67</span><span class="sxs-lookup"><span data-stu-id="651e2-190">-91.67</span></span>      | <span data-ttu-id="651e2-191">-91,67</span><span class="sxs-lookup"><span data-stu-id="651e2-191">-91.67</span></span>               |

## <a name="how-quantities-and-amounts-in-each-period-bucket-are-calculated"></a><span data-ttu-id="651e2-192">Como as quantidades e os valores em cada bucket de período são calculados</span><span class="sxs-lookup"><span data-stu-id="651e2-192">How quantities and amounts in each period bucket are calculated</span></span>

<span data-ttu-id="651e2-193">Usando os dados de exemplo descritos nas seções anteriores, você pode executar um relatório **Classificação por vencimento de estoque** com as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="651e2-193">By using the sample data that is described in the previous sections, you can run an **Inventory aging** report that has the following settings:</span></span>

- <span data-ttu-id="651e2-194">**A partir da data:** *9 de maio de 2020*</span><span class="sxs-lookup"><span data-stu-id="651e2-194">**As of date:** *May 9, 2020*</span></span>
- <span data-ttu-id="651e2-195">**Site:** *Exibir*</span><span class="sxs-lookup"><span data-stu-id="651e2-195">**Site:** *View*</span></span>
- <span data-ttu-id="651e2-196">**Depósito:** *Não*</span><span class="sxs-lookup"><span data-stu-id="651e2-196">**Warehouse:** *No*</span></span>
- <span data-ttu-id="651e2-197">**Número do item:** *Total*</span><span class="sxs-lookup"><span data-stu-id="651e2-197">**Item number:** *Total*</span></span>
- <span data-ttu-id="651e2-198">**Período de classificação por vencimento:** defina esse campo para gerar buckets mensais.</span><span class="sxs-lookup"><span data-stu-id="651e2-198">**Aging period:** Set this field to generate monthly buckets.</span></span>

<span data-ttu-id="651e2-199">Nesse caso, o conteúdo do relatório gerado será semelhante ao exemplo a seguir.</span><span class="sxs-lookup"><span data-stu-id="651e2-199">In this case, the content of the report that is generated will resemble the following example.</span></span>

<table>
<thead>
<tr>
    <th rowspan="2"><span data-ttu-id="651e2-200">Nº de itens</span><span class="sxs-lookup"><span data-stu-id="651e2-200">Item number</span></span></th>
    <th rowspan="2"><span data-ttu-id="651e2-201">Site</span><span class="sxs-lookup"><span data-stu-id="651e2-201">Site</span></span></th>
    <th rowspan="2"><span data-ttu-id="651e2-202">Quantidade disponível</span><span class="sxs-lookup"><span data-stu-id="651e2-202">On-hand quantity</span></span></th>
    <th rowspan="2"><span data-ttu-id="651e2-203">Valor disponível</span><span class="sxs-lookup"><span data-stu-id="651e2-203">On-hand value</span></span></th>
    <th rowspan="2"><span data-ttu-id="651e2-204">Quantidade do valor do estoque</span><span class="sxs-lookup"><span data-stu-id="651e2-204">Inventory value quantity</span></span></th>
    <th rowspan="2"><span data-ttu-id="651e2-205">Valor do estoque</span><span class="sxs-lookup"><span data-stu-id="651e2-205">Inventory value</span></span></th>
    <th rowspan="2"><span data-ttu-id="651e2-206">Custo unitário médio</span><span class="sxs-lookup"><span data-stu-id="651e2-206">Average unit cost</span></span></th>
    <th colspan="2"><span data-ttu-id="651e2-207">8/5/2020 - 1/5/2020</span><span class="sxs-lookup"><span data-stu-id="651e2-207">5/8/2020 - 5/1/2020</span></span></th>
    <th colspan="2"><span data-ttu-id="651e2-208">30/4/2020 - 1/4/2020</span><span class="sxs-lookup"><span data-stu-id="651e2-208">4/30/2020 - 4/1/2020</span></span></th>
    <th colspan="2"><span data-ttu-id="651e2-209">31/3/2020 - 1/3/2020</span><span class="sxs-lookup"><span data-stu-id="651e2-209">3/31/2020 - 3/1/2020</span></span></th>
</tr>
<tr>
    <th><span data-ttu-id="651e2-210">P1:Quantidade</span><span class="sxs-lookup"><span data-stu-id="651e2-210">P1:Quantity</span></span></th>
    <th><span data-ttu-id="651e2-211">P1:Valor</span><span class="sxs-lookup"><span data-stu-id="651e2-211">P1:Amount</span></span></th>
    <th><span data-ttu-id="651e2-212">P2:Quantidade</span><span class="sxs-lookup"><span data-stu-id="651e2-212">P2:Quantity</span></span></th>
    <th><span data-ttu-id="651e2-213">P2:Valor</span><span class="sxs-lookup"><span data-stu-id="651e2-213">P2:Amount</span></span></th>
    <th><span data-ttu-id="651e2-214">P3:Quantidade</span><span class="sxs-lookup"><span data-stu-id="651e2-214">P3:Quantity</span></span></th>
    <th><span data-ttu-id="651e2-215">P3:Valor</span><span class="sxs-lookup"><span data-stu-id="651e2-215">P3:Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
    <td><span data-ttu-id="651e2-216">1000</span><span class="sxs-lookup"><span data-stu-id="651e2-216">1000</span></span></td>
    <td><span data-ttu-id="651e2-217">1</span><span class="sxs-lookup"><span data-stu-id="651e2-217">1</span></span></td>
    <td><span data-ttu-id="651e2-218">14</span><span class="sxs-lookup"><span data-stu-id="651e2-218">14</span></span></td>
    <td><span data-ttu-id="651e2-219">1,283.33</span><span class="sxs-lookup"><span data-stu-id="651e2-219">1,283.33</span></span></td>
    <td><span data-ttu-id="651e2-220">14</span><span class="sxs-lookup"><span data-stu-id="651e2-220">14</span></span></td>
    <td><span data-ttu-id="651e2-221">1,283.33</span><span class="sxs-lookup"><span data-stu-id="651e2-221">1,283.33</span></span></td>
    <td><span data-ttu-id="651e2-222">91.67</span><span class="sxs-lookup"><span data-stu-id="651e2-222">91.67</span></span></td>
    <td></td>
    <td></td>
    <td><span data-ttu-id="651e2-223">5.00</span><span class="sxs-lookup"><span data-stu-id="651e2-223">5.00</span></span></td>
    <td><span data-ttu-id="651e2-224">458.33</span><span class="sxs-lookup"><span data-stu-id="651e2-224">458.33</span></span></td>
    <td><span data-ttu-id="651e2-225">9.00</span><span class="sxs-lookup"><span data-stu-id="651e2-225">9.00</span></span></td>
    <td><span data-ttu-id="651e2-226">825.00</span><span class="sxs-lookup"><span data-stu-id="651e2-226">825.00</span></span></td>
</tr>
<tr>
    <td><span data-ttu-id="651e2-227">1000</span><span class="sxs-lookup"><span data-stu-id="651e2-227">1000</span></span></td>
    <td><span data-ttu-id="651e2-228">2</span><span class="sxs-lookup"><span data-stu-id="651e2-228">2</span></span></td>
    <td><span data-ttu-id="651e2-229">10</span><span class="sxs-lookup"><span data-stu-id="651e2-229">10</span></span></td>
    <td><span data-ttu-id="651e2-230">2,000.00</span><span class="sxs-lookup"><span data-stu-id="651e2-230">2,000.00</span></span></td>
    <td><span data-ttu-id="651e2-231">10</span><span class="sxs-lookup"><span data-stu-id="651e2-231">10</span></span></td>
    <td><span data-ttu-id="651e2-232">2,000.00</span><span class="sxs-lookup"><span data-stu-id="651e2-232">2,000.00</span></span></td>
    <td><span data-ttu-id="651e2-233">200.00</span><span class="sxs-lookup"><span data-stu-id="651e2-233">200.00</span></span></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td><span data-ttu-id="651e2-234">10,00</span><span class="sxs-lookup"><span data-stu-id="651e2-234">10.00</span></span></td>
    <td><span data-ttu-id="651e2-235">2,000.00</span><span class="sxs-lookup"><span data-stu-id="651e2-235">2,000.00</span></span></td>
</tr>
</tbody>
<tfoot>
<tr>
    <td><span data-ttu-id="651e2-236"><strong>Totais de 1.000</strong></span><span class="sxs-lookup"><span data-stu-id="651e2-236"><strong>1000 Totals</strong></span></span></td>
    <td></td>
    <td><span data-ttu-id="651e2-237"><strong>24.00</strong></span><span class="sxs-lookup"><span data-stu-id="651e2-237"><strong>24.00</strong></span></span></td>
    <td><span data-ttu-id="651e2-238"><strong>3,283.33</strong></span><span class="sxs-lookup"><span data-stu-id="651e2-238"><strong>3,283.33</strong></span></span></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td><span data-ttu-id="651e2-239"><strong>5.00</strong></span><span class="sxs-lookup"><span data-stu-id="651e2-239"><strong>5.00</strong></span></span></td>
    <td><span data-ttu-id="651e2-240"><strong>458.33</strong></span><span class="sxs-lookup"><span data-stu-id="651e2-240"><strong>458.33</strong></span></span></td>
    <td><span data-ttu-id="651e2-241"><strong>19</strong></span><span class="sxs-lookup"><span data-stu-id="651e2-241"><strong>19</strong></span></span></td>
    <td><span data-ttu-id="651e2-242"><strong>2,825.00</strong></span><span class="sxs-lookup"><span data-stu-id="651e2-242"><strong>2,825.00</strong></span></span></td>
</tr>
</tfoot>
</table>

<span data-ttu-id="651e2-243">Observe os seguintes detalhes neste exemplo de relatório:</span><span class="sxs-lookup"><span data-stu-id="651e2-243">Note the following details in this example report:</span></span>

- <span data-ttu-id="651e2-244">Os valores de **Quantidade de valor de estoque**, **Valor de estoque** e **Custo unitário médio** exibidos no relatório são valores para a dimensão de estoque financeira (**Site**, neste caso).</span><span class="sxs-lookup"><span data-stu-id="651e2-244">The **Inventory value quantity**, **Inventory value**, and **Average unit cost** values that are shown on the report are values for the financial inventory dimension (**Site**, in this case).</span></span>

    <span data-ttu-id="651e2-245">Por exemplo, para o site 1, o relatório mostra as seguintes informações:</span><span class="sxs-lookup"><span data-stu-id="651e2-245">For example, for site 1, the report shows the following information:</span></span>

    - <span data-ttu-id="651e2-246">O valor de **Quantidade de valor em estoque** é *14* (= 10 + 5 – 5 + 5 – 1).</span><span class="sxs-lookup"><span data-stu-id="651e2-246">The **Inventory value quantity** value is *14* (= 10 + 5 – 5 + 5 – 1).</span></span>
    - <span data-ttu-id="651e2-247">O valor de **Valor em estoque** é *1.283,33* (= 1.000 + 375 – 458,33 + 458,33 – 91,67).</span><span class="sxs-lookup"><span data-stu-id="651e2-247">The **Inventory value** value is *1,283.33* (= 1,000 + 375 – 458.33 + 458.33 – 91.67).</span></span>
    - <span data-ttu-id="651e2-248">O valor de **Custo unitário médio** é *91,67*.</span><span class="sxs-lookup"><span data-stu-id="651e2-248">The **Average unit cost** value is *91.67*.</span></span>
    - <span data-ttu-id="651e2-249">O valor de **Valor disponível** e o valor de **Valor** em cada bucket de período são calculados usando-se o valor de **Custo unitário médio**.</span><span class="sxs-lookup"><span data-stu-id="651e2-249">The **On-hand value** value and the **Amount** value in each period bucket are calculated by using the **Average unit cost** value.</span></span>

- <span data-ttu-id="651e2-250">O relatório determina a quantidade disponível para cada bucket de período resumindo a quantidade de estoque total recebida para cada bucket de período.</span><span class="sxs-lookup"><span data-stu-id="651e2-250">The report determines the on-hand quantity for each period bucket by summarizing the total received inventory quantity for each period bucket.</span></span> <span data-ttu-id="651e2-251">Em seguida, ele aplica o princípio PEPS (primeiro a entrar, primeiro a sair) para deduzir a quantidade emitida total, independentemente do modelo de estoque usado pelos itens.</span><span class="sxs-lookup"><span data-stu-id="651e2-251">It then applies the first in, first out (FIFO) principle to deduct the total issued quantity, regardless of the inventory model that the items use.</span></span>

<span data-ttu-id="651e2-252">Se você executar o mesmo relatório novamente, mas, desta vez, definir os campos **Site** e **Depósito** como *Exibir*, o novo relatório será semelhante ao exemplo a seguir.</span><span class="sxs-lookup"><span data-stu-id="651e2-252">If you run the same report again, but this time you set both the **Site** and **Warehouse** fields to *View*, the new report will resemble the following example.</span></span>

<table>
<thead>
<tr>
    <th rowspan="2"><span data-ttu-id="651e2-253">Nº de itens</span><span class="sxs-lookup"><span data-stu-id="651e2-253">Item number</span></span></th>
    <th rowspan="2"><span data-ttu-id="651e2-254">Site</span><span class="sxs-lookup"><span data-stu-id="651e2-254">Site</span></span></th>
    <th rowspan="2"><span data-ttu-id="651e2-255">Depósito</span><span class="sxs-lookup"><span data-stu-id="651e2-255">Warehouse</span></span></th>
    <th rowspan="2"><span data-ttu-id="651e2-256">Quantidade disponível</span><span class="sxs-lookup"><span data-stu-id="651e2-256">On-hand quantity</span></span></th>
    <th rowspan="2"><span data-ttu-id="651e2-257">Valor disponível</span><span class="sxs-lookup"><span data-stu-id="651e2-257">On-hand value</span></span></th>
    <th rowspan="2"><span data-ttu-id="651e2-258">Quantidade do valor do estoque</span><span class="sxs-lookup"><span data-stu-id="651e2-258">Inventory value quantity</span></span></th>
    <th rowspan="2"><span data-ttu-id="651e2-259">Valor do estoque</span><span class="sxs-lookup"><span data-stu-id="651e2-259">Inventory value</span></span></th>
    <th rowspan="2"><span data-ttu-id="651e2-260">Custo unitário médio</span><span class="sxs-lookup"><span data-stu-id="651e2-260">Average unit cost</span></span></th>
    <th colspan="2"><span data-ttu-id="651e2-261">8/5/2020 - 1/5/2020</span><span class="sxs-lookup"><span data-stu-id="651e2-261">5/8/2020 - 5/1/2020</span></span></th>
    <th colspan="2"><span data-ttu-id="651e2-262">30/4/2020 - 1/4/2020</span><span class="sxs-lookup"><span data-stu-id="651e2-262">4/30/2020 - 4/1/2020</span></span></th>
    <th colspan="2"><span data-ttu-id="651e2-263">31/3/2020 - 1/3/2020</span><span class="sxs-lookup"><span data-stu-id="651e2-263">3/31/2020 - 3/1/2020</span></span></th>
</tr>
<tr>
    <th><span data-ttu-id="651e2-264">P1:Quantidade</span><span class="sxs-lookup"><span data-stu-id="651e2-264">P1:Quantity</span></span></th>
    <th><span data-ttu-id="651e2-265">P1:Valor</span><span class="sxs-lookup"><span data-stu-id="651e2-265">P1:Amount</span></span></th>
    <th><span data-ttu-id="651e2-266">P2:Quantidade</span><span class="sxs-lookup"><span data-stu-id="651e2-266">P2:Quantity</span></span></th>
    <th><span data-ttu-id="651e2-267">P2:Valor</span><span class="sxs-lookup"><span data-stu-id="651e2-267">P2:Amount</span></span></th>
    <th><span data-ttu-id="651e2-268">P3:Quantidade</span><span class="sxs-lookup"><span data-stu-id="651e2-268">P3:Quantity</span></span></th>
    <th><span data-ttu-id="651e2-269">P3:Valor</span><span class="sxs-lookup"><span data-stu-id="651e2-269">P3:Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
    <td><span data-ttu-id="651e2-270">1000</span><span class="sxs-lookup"><span data-stu-id="651e2-270">1000</span></span></td>
    <td><span data-ttu-id="651e2-271">1</span><span class="sxs-lookup"><span data-stu-id="651e2-271">1</span></span></td>
    <td><span data-ttu-id="651e2-272">11</span><span class="sxs-lookup"><span data-stu-id="651e2-272">11</span></span></td>
    <td><span data-ttu-id="651e2-273">10</span><span class="sxs-lookup"><span data-stu-id="651e2-273">10</span></span></td>
    <td><span data-ttu-id="651e2-274">916.67</span><span class="sxs-lookup"><span data-stu-id="651e2-274">916.67</span></span></td>
    <td><span data-ttu-id="651e2-275">14</span><span class="sxs-lookup"><span data-stu-id="651e2-275">14</span></span></td>
    <td><span data-ttu-id="651e2-276">1,283.33</span><span class="sxs-lookup"><span data-stu-id="651e2-276">1,283.33</span></span></td>
    <td><span data-ttu-id="651e2-277">91.67</span><span class="sxs-lookup"><span data-stu-id="651e2-277">91.67</span></span></td>
    <td></td>
    <td></td>
    <td><span data-ttu-id="651e2-278">5.00</span><span class="sxs-lookup"><span data-stu-id="651e2-278">5.00</span></span></td>
    <td><span data-ttu-id="651e2-279">458.33</span><span class="sxs-lookup"><span data-stu-id="651e2-279">458.33</span></span></td>
    <td><span data-ttu-id="651e2-280">5.00</span><span class="sxs-lookup"><span data-stu-id="651e2-280">5.00</span></span></td>
    <td><span data-ttu-id="651e2-281">458.33</span><span class="sxs-lookup"><span data-stu-id="651e2-281">458.33</span></span></td>
</tr>
<tr>
    <td><span data-ttu-id="651e2-282">1000</span><span class="sxs-lookup"><span data-stu-id="651e2-282">1000</span></span></td>
    <td><span data-ttu-id="651e2-283">1</span><span class="sxs-lookup"><span data-stu-id="651e2-283">1</span></span></td>
    <td><span data-ttu-id="651e2-284">12</span><span class="sxs-lookup"><span data-stu-id="651e2-284">12</span></span></td>
    <td><span data-ttu-id="651e2-285">4</span><span class="sxs-lookup"><span data-stu-id="651e2-285">4</span></span></td>
    <td><span data-ttu-id="651e2-286">366.67</span><span class="sxs-lookup"><span data-stu-id="651e2-286">366.67</span></span></td>
    <td><span data-ttu-id="651e2-287">14</span><span class="sxs-lookup"><span data-stu-id="651e2-287">14</span></span></td>
    <td><span data-ttu-id="651e2-288">1,283.33</span><span class="sxs-lookup"><span data-stu-id="651e2-288">1,283.33</span></span></td>
    <td><span data-ttu-id="651e2-289">91.67</span><span class="sxs-lookup"><span data-stu-id="651e2-289">91.67</span></span></td>
    <td><span data-ttu-id="651e2-290">4.00</span><span class="sxs-lookup"><span data-stu-id="651e2-290">4.00</span></span></td>
    <td><span data-ttu-id="651e2-291">366.67</span><span class="sxs-lookup"><span data-stu-id="651e2-291">366.67</span></span></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
</tr>
<tr>
    <td><span data-ttu-id="651e2-292">1000</span><span class="sxs-lookup"><span data-stu-id="651e2-292">1000</span></span></td>
    <td><span data-ttu-id="651e2-293">2</span><span class="sxs-lookup"><span data-stu-id="651e2-293">2</span></span></td>
    <td></td>
    <td><span data-ttu-id="651e2-294">10</span><span class="sxs-lookup"><span data-stu-id="651e2-294">10</span></span></td>
    <td><span data-ttu-id="651e2-295">2,000.00</span><span class="sxs-lookup"><span data-stu-id="651e2-295">2,000.00</span></span></td>
    <td><span data-ttu-id="651e2-296">10</span><span class="sxs-lookup"><span data-stu-id="651e2-296">10</span></span></td>
    <td><span data-ttu-id="651e2-297">2,000.00</span><span class="sxs-lookup"><span data-stu-id="651e2-297">2,000.00</span></span></td>
    <td><span data-ttu-id="651e2-298">200.00</span><span class="sxs-lookup"><span data-stu-id="651e2-298">200.00</span></span></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td><span data-ttu-id="651e2-299">10,00</span><span class="sxs-lookup"><span data-stu-id="651e2-299">10.00</span></span></td>
    <td><span data-ttu-id="651e2-300">2,000.00</span><span class="sxs-lookup"><span data-stu-id="651e2-300">2,000.00</span></span></td>
</tr>
</tbody>
<tfoot>
<tr>
    <td><span data-ttu-id="651e2-301"><strong>Totais de 1.000</strong></span><span class="sxs-lookup"><span data-stu-id="651e2-301"><strong>1000 Totals</strong></span></span></td>
    <td></td>
    <td></td>
    <td><span data-ttu-id="651e2-302"><strong>24.00</strong></span><span class="sxs-lookup"><span data-stu-id="651e2-302"><strong>24.00</strong></span></span></td>
    <td><span data-ttu-id="651e2-303"><strong>3,283.33</strong></span><span class="sxs-lookup"><span data-stu-id="651e2-303"><strong>3,283.33</strong></span></span></td>
    <td></td>
    <td></td>
    <td></td>
    <td><span data-ttu-id="651e2-304"><strong>4.00</strong></span><span class="sxs-lookup"><span data-stu-id="651e2-304"><strong>4.00</strong></span></span></td>
    <td><span data-ttu-id="651e2-305"><strong>366.67</strong></span><span class="sxs-lookup"><span data-stu-id="651e2-305"><strong>366.67</strong></span></span></td>
    <td><span data-ttu-id="651e2-306"><strong>5.00</strong></span><span class="sxs-lookup"><span data-stu-id="651e2-306"><strong>5.00</strong></span></span></td>
    <td><span data-ttu-id="651e2-307"><strong>458.33</strong></span><span class="sxs-lookup"><span data-stu-id="651e2-307"><strong>458.33</strong></span></span></td>
    <td><span data-ttu-id="651e2-308"><strong>15</strong></span><span class="sxs-lookup"><span data-stu-id="651e2-308"><strong>15</strong></span></span></td>
    <td><span data-ttu-id="651e2-309"><strong>2,458.33</strong></span><span class="sxs-lookup"><span data-stu-id="651e2-309"><strong>2,458.33</strong></span></span></td>
</tr>
</tfoot>
</table>

<span data-ttu-id="651e2-310">Desta vez, o site 1 é dividido em duas linhas, uma para o depósito 11 e outra para o depósito 12.</span><span class="sxs-lookup"><span data-stu-id="651e2-310">This time, site 1 is split into two rows, one for warehouse 11 and one for warehouse 12.</span></span> <span data-ttu-id="651e2-311">No entanto, os valores de **Quantidade de valor de estoque**, **Valor de estoque** e **Custo unitário médio** são iguais, já que **Depósito** não é uma dimensão de estoque financeira.</span><span class="sxs-lookup"><span data-stu-id="651e2-311">However, the **Inventory value quantity**, **Inventory value**, and **Average unit cost** values are the same, because **Warehouse** isn't a financial inventory dimension.</span></span>

<span data-ttu-id="651e2-312">Além disso, observe que a distribuição de quantidade do site 1 é diferente.</span><span class="sxs-lookup"><span data-stu-id="651e2-312">Additionally, notice that the quantity distribution of site 1 is different.</span></span> <span data-ttu-id="651e2-313">No primeiro relatório que você executou, o sistema ignorou a ordem de transferência ocorrida no mesmo site e deduziu a quantidade da fatura de venda do bucket de período **31/3/2020-1/3/2020** no site 1.</span><span class="sxs-lookup"><span data-stu-id="651e2-313">In the first report that you ran, the system ignored the transfer order that occurred in the same site and deducted the quantity of the sales invoice from the **3/31/2020 - 3/1/2020** period bucket in site 1.</span></span> <span data-ttu-id="651e2-314">No entanto, no novo relatório, o sistema deduz a quantidade da fatura de venda do bucket de período **8/5/2020-1/5/2020** no depósito 12.</span><span class="sxs-lookup"><span data-stu-id="651e2-314">However, in the new report, the system deducts the quantity of the sales invoice from the **5/8/2020 - 5/1/2020** period bucket in warehouse 12.</span></span>

## <a name="effects-of-inventory-closing"></a><span data-ttu-id="651e2-315">Efeitos do fechamento de estoque</span><span class="sxs-lookup"><span data-stu-id="651e2-315">Effects of inventory closing</span></span>

<span data-ttu-id="651e2-316">Se você executar o fechamento de estoque para maio e executar o relatório anterior novamente, mas definir o campo **A partir da data** como *31 de maio de 2020*, os seguintes resultados serão observados:</span><span class="sxs-lookup"><span data-stu-id="651e2-316">If you run the inventory closing for May and then run the previous report again, but you set the **As of date** field to *May 31, 2020*, you will notice the following results:</span></span>

- <span data-ttu-id="651e2-317">Os valores **Valor de estoque** e **Custo unitário médio** são atualizados.</span><span class="sxs-lookup"><span data-stu-id="651e2-317">The **Inventory value** and **Average unit cost** values are updated.</span></span>
- <span data-ttu-id="651e2-318">O valor de **Valor disponível** e todos os valores de **Valor** em cada bucket de período são atualizados adequadamente.</span><span class="sxs-lookup"><span data-stu-id="651e2-318">The **On-hand value** value and all the **Amount** values in every period bucket are updated accordingly.</span></span>

<span data-ttu-id="651e2-319">O novo relatório se assemelhará ao seguinte exemplo.</span><span class="sxs-lookup"><span data-stu-id="651e2-319">The new report will resemble the following example.</span></span>

<table>
<thead>
<tr>
    <th rowspan="2"><span data-ttu-id="651e2-320">Nº de itens</span><span class="sxs-lookup"><span data-stu-id="651e2-320">Item number</span></span></th>
    <th rowspan="2"><span data-ttu-id="651e2-321">Site</span><span class="sxs-lookup"><span data-stu-id="651e2-321">Site</span></span></th>
    <th rowspan="2"><span data-ttu-id="651e2-322">Depósito</span><span class="sxs-lookup"><span data-stu-id="651e2-322">Warehouse</span></span></th>
    <th rowspan="2"><span data-ttu-id="651e2-323">Quantidade disponível</span><span class="sxs-lookup"><span data-stu-id="651e2-323">On-hand quantity</span></span></th>
    <th rowspan="2"><span data-ttu-id="651e2-324">Valor disponível</span><span class="sxs-lookup"><span data-stu-id="651e2-324">On-hand value</span></span></th>
    <th rowspan="2"><span data-ttu-id="651e2-325">Quantidade do valor do estoque</span><span class="sxs-lookup"><span data-stu-id="651e2-325">Inventory value quantity</span></span></th>
    <th rowspan="2"><span data-ttu-id="651e2-326">Valor do estoque</span><span class="sxs-lookup"><span data-stu-id="651e2-326">Inventory value</span></span></th>
    <th rowspan="2"><span data-ttu-id="651e2-327">Custo unitário médio</span><span class="sxs-lookup"><span data-stu-id="651e2-327">Average unit cost</span></span></th>
    <th colspan="2"><span data-ttu-id="651e2-328">31/5/2020 - 1/5/2020</span><span class="sxs-lookup"><span data-stu-id="651e2-328">5/31/2020 - 5/1/2020</span></span></th>
    <th colspan="2"><span data-ttu-id="651e2-329">30/4/2020 - 1/4/2020</span><span class="sxs-lookup"><span data-stu-id="651e2-329">4/30/2020 - 4/1/2020</span></span></th>
    <th colspan="2"><span data-ttu-id="651e2-330">31/3/2020 - 1/3/2020</span><span class="sxs-lookup"><span data-stu-id="651e2-330">3/31/2020 - 3/1/2020</span></span></th>
</tr>
<tr>
    <th><span data-ttu-id="651e2-331">P1:Quantidade</span><span class="sxs-lookup"><span data-stu-id="651e2-331">P1:Quantity</span></span></th>
    <th><span data-ttu-id="651e2-332">P1:Valor</span><span class="sxs-lookup"><span data-stu-id="651e2-332">P1:Amount</span></span></th>
    <th><span data-ttu-id="651e2-333">P2:Quantidade</span><span class="sxs-lookup"><span data-stu-id="651e2-333">P2:Quantity</span></span></th>
    <th><span data-ttu-id="651e2-334">P2:Valor</span><span class="sxs-lookup"><span data-stu-id="651e2-334">P2:Amount</span></span></th>
    <th><span data-ttu-id="651e2-335">P3:Quantidade</span><span class="sxs-lookup"><span data-stu-id="651e2-335">P3:Quantity</span></span></th>
    <th><span data-ttu-id="651e2-336">P3:Valor</span><span class="sxs-lookup"><span data-stu-id="651e2-336">P3:Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
    <td><span data-ttu-id="651e2-337">1000</span><span class="sxs-lookup"><span data-stu-id="651e2-337">1000</span></span></td>
    <td><span data-ttu-id="651e2-338">1</span><span class="sxs-lookup"><span data-stu-id="651e2-338">1</span></span></td>
    <td><span data-ttu-id="651e2-339">11</span><span class="sxs-lookup"><span data-stu-id="651e2-339">11</span></span></td>
    <td><span data-ttu-id="651e2-340">10</span><span class="sxs-lookup"><span data-stu-id="651e2-340">10</span></span></td>
    <td><span data-ttu-id="651e2-341">910.70</span><span class="sxs-lookup"><span data-stu-id="651e2-341">910.70</span></span></td>
    <td><span data-ttu-id="651e2-342">14</span><span class="sxs-lookup"><span data-stu-id="651e2-342">14</span></span></td>
    <td><span data-ttu-id="651e2-343">1,275.00</span><span class="sxs-lookup"><span data-stu-id="651e2-343">1,275.00</span></span></td>
    <td><span data-ttu-id="651e2-344">91.07</span><span class="sxs-lookup"><span data-stu-id="651e2-344">91.07</span></span></td>
    <td><span data-ttu-id="651e2-345">0,00</span><span class="sxs-lookup"><span data-stu-id="651e2-345">0.00</span></span></td>
    <td></td>
    <td><span data-ttu-id="651e2-346">5.00</span><span class="sxs-lookup"><span data-stu-id="651e2-346">5.00</span></span></td>
    <td><span data-ttu-id="651e2-347">455.36</span><span class="sxs-lookup"><span data-stu-id="651e2-347">455.36</span></span></td>
    <td><span data-ttu-id="651e2-348">5.00</span><span class="sxs-lookup"><span data-stu-id="651e2-348">5.00</span></span></td>
    <td><span data-ttu-id="651e2-349">455.36</span><span class="sxs-lookup"><span data-stu-id="651e2-349">455.36</span></span></td>
</tr>
<tr>
    <td><span data-ttu-id="651e2-350">1000</span><span class="sxs-lookup"><span data-stu-id="651e2-350">1000</span></span></td>
    <td><span data-ttu-id="651e2-351">1</span><span class="sxs-lookup"><span data-stu-id="651e2-351">1</span></span></td>
    <td><span data-ttu-id="651e2-352">12</span><span class="sxs-lookup"><span data-stu-id="651e2-352">12</span></span></td>
    <td><span data-ttu-id="651e2-353">4</span><span class="sxs-lookup"><span data-stu-id="651e2-353">4</span></span></td>
    <td><span data-ttu-id="651e2-354">364.29</span><span class="sxs-lookup"><span data-stu-id="651e2-354">364.29</span></span></td>
    <td><span data-ttu-id="651e2-355">14</span><span class="sxs-lookup"><span data-stu-id="651e2-355">14</span></span></td>
    <td><span data-ttu-id="651e2-356">1,275.00</span><span class="sxs-lookup"><span data-stu-id="651e2-356">1,275.00</span></span></td>
    <td><span data-ttu-id="651e2-357">91.07</span><span class="sxs-lookup"><span data-stu-id="651e2-357">91.07</span></span></td>
    <td><span data-ttu-id="651e2-358">4.00</span><span class="sxs-lookup"><span data-stu-id="651e2-358">4.00</span></span></td>
    <td><span data-ttu-id="651e2-359">364.29</span><span class="sxs-lookup"><span data-stu-id="651e2-359">364.29</span></span></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
</tr>
<tr>
    <td><span data-ttu-id="651e2-360">1000</span><span class="sxs-lookup"><span data-stu-id="651e2-360">1000</span></span></td>
    <td><span data-ttu-id="651e2-361">2</span><span class="sxs-lookup"><span data-stu-id="651e2-361">2</span></span></td>
    <td></td>
    <td><span data-ttu-id="651e2-362">10</span><span class="sxs-lookup"><span data-stu-id="651e2-362">10</span></span></td>
    <td><span data-ttu-id="651e2-363">2,000.00</span><span class="sxs-lookup"><span data-stu-id="651e2-363">2,000.00</span></span></td>
    <td><span data-ttu-id="651e2-364">10</span><span class="sxs-lookup"><span data-stu-id="651e2-364">10</span></span></td>
    <td><span data-ttu-id="651e2-365">2,000.00</span><span class="sxs-lookup"><span data-stu-id="651e2-365">2,000.00</span></span></td>
    <td><span data-ttu-id="651e2-366">200.00</span><span class="sxs-lookup"><span data-stu-id="651e2-366">200.00</span></span></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td><span data-ttu-id="651e2-367">10,00</span><span class="sxs-lookup"><span data-stu-id="651e2-367">10.00</span></span></td>
    <td><span data-ttu-id="651e2-368">2,000.00</span><span class="sxs-lookup"><span data-stu-id="651e2-368">2,000.00</span></span></td>
</tr>
</tbody>
<tfoot>
<tr>
    <td><span data-ttu-id="651e2-369"><strong>Totais de 1.000</strong></span><span class="sxs-lookup"><span data-stu-id="651e2-369"><strong>1000 Totals</strong></span></span></td>
    <td></td>
    <td></td>
    <td><span data-ttu-id="651e2-370"><strong>24.00</strong></span><span class="sxs-lookup"><span data-stu-id="651e2-370"><strong>24.00</strong></span></span></td>
    <td><span data-ttu-id="651e2-371"><strong>3,275.00</strong></span><span class="sxs-lookup"><span data-stu-id="651e2-371"><strong>3,275.00</strong></span></span></td>
    <td></td>
    <td></td>
    <td></td>
    <td><span data-ttu-id="651e2-372"><strong>4.00</strong></span><span class="sxs-lookup"><span data-stu-id="651e2-372"><strong>4.00</strong></span></span></td>
    <td><span data-ttu-id="651e2-373"><strong>364.29</strong></span><span class="sxs-lookup"><span data-stu-id="651e2-373"><strong>364.29</strong></span></span></td>
    <td><span data-ttu-id="651e2-374"><strong>5.00</strong></span><span class="sxs-lookup"><span data-stu-id="651e2-374"><strong>5.00</strong></span></span></td>
    <td><span data-ttu-id="651e2-375"><strong>455.36</strong></span><span class="sxs-lookup"><span data-stu-id="651e2-375"><strong>455.36</strong></span></span></td>
    <td><span data-ttu-id="651e2-376"><strong>15</strong></span><span class="sxs-lookup"><span data-stu-id="651e2-376"><strong>15</strong></span></span></td>
    <td><span data-ttu-id="651e2-377"><strong>2,455.36</strong></span><span class="sxs-lookup"><span data-stu-id="651e2-377"><strong>2,455.36</strong></span></span></td>
</tr>
</tfoot>
</table>
