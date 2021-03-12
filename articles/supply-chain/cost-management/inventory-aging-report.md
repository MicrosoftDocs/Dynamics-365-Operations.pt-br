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
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: riluan
ms.search.validFrom: 2020-5-29
ms.dyn365.ops.version: ''
ms.openlocfilehash: b3822cf4c26d7ef9cd0d062d57fa909140d7e258
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4983916"
---
# <a name="inventory-aging-report-examples-and-logic"></a><span data-ttu-id="7ff07-103">Exemplos e lógica de relatório de classificação por vencimento de estoque</span><span class="sxs-lookup"><span data-stu-id="7ff07-103">Inventory aging report examples and logic</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="7ff07-104">Este tópico apresenta alguns exemplos que mostram como interpretar os resultados de um relatório de **classificação por vencimento de estoque**.</span><span class="sxs-lookup"><span data-stu-id="7ff07-104">This topic presents some examples that show how to interpret the results of an **Inventory aging** report.</span></span> <span data-ttu-id="7ff07-105">Este relatório categoriza os valores de estoque e quantidade disponíveis para um item ou grupo de itens selecionado em vários buckets de período.</span><span class="sxs-lookup"><span data-stu-id="7ff07-105">This report categorizes on-hand quantity and inventory values for a selected item or item group into several period buckets.</span></span> <span data-ttu-id="7ff07-106">Este tópico também mostra a lógica interna do relatório.</span><span class="sxs-lookup"><span data-stu-id="7ff07-106">This topic also shows the internal logic of the report.</span></span>

<span data-ttu-id="7ff07-107">Os exemplos neste tópico mostram resultados que são apresentados em um relatório **Classificação por vencimento de estoque** padrão.</span><span class="sxs-lookup"><span data-stu-id="7ff07-107">The examples in this topic show results that are presented on a standard **Inventory aging** report.</span></span> <span data-ttu-id="7ff07-108">No entanto, em geral, recomendamos que você use a versão de [Armazenamento do relatório de classificação por vencimento de estoque](inventory-aging-report-storage.md) desse relatório, especialmente quando houver vários itens e depósitos que devem ser processados.</span><span class="sxs-lookup"><span data-stu-id="7ff07-108">However, in general, we recommend that you use the [Inventory aging report storage](inventory-aging-report-storage.md) version of this report, especially when you have many items and warehouses that must be processed.</span></span> <span data-ttu-id="7ff07-109">A classificação por vencimento de estoque salva cada relatório gerado, mostra os resultados como uma página interativa e um gráfico e permite exportar qualquer relatório salvo.</span><span class="sxs-lookup"><span data-stu-id="7ff07-109">Inventory aging report storage saves each report that you generate, shows the results as an interactive page and a chart, and lets you export any saved report.</span></span>

## <a name="sample-data-that-is-used-in-these-examples"></a><span data-ttu-id="7ff07-110">Dados de exemplo usados nestes exemplos</span><span class="sxs-lookup"><span data-stu-id="7ff07-110">Sample data that is used in these examples</span></span>

<span data-ttu-id="7ff07-111">Os exemplos neste tópico se baseiam nos dados de exemplo de transação de estoque descritos nesta seção.</span><span class="sxs-lookup"><span data-stu-id="7ff07-111">The examples in this topic are based on the sample inventory transaction data that is described in this section.</span></span>

### <a name="storage-dimension-setup"></a><span data-ttu-id="7ff07-112">Configuração de dimensão de armazenamento</span><span class="sxs-lookup"><span data-stu-id="7ff07-112">Storage dimension setup</span></span>

<span data-ttu-id="7ff07-113">O sistema de exemplo contém a seguinte configuração de dimensões de armazenamento.</span><span class="sxs-lookup"><span data-stu-id="7ff07-113">The example system contains the following setup of storage dimensions.</span></span>

| <span data-ttu-id="7ff07-114">Nome</span><span class="sxs-lookup"><span data-stu-id="7ff07-114">Name</span></span>      | <span data-ttu-id="7ff07-115">Ativos</span><span class="sxs-lookup"><span data-stu-id="7ff07-115">Active</span></span> | <span data-ttu-id="7ff07-116">Estoque físico</span><span class="sxs-lookup"><span data-stu-id="7ff07-116">Physical inventory</span></span> | <span data-ttu-id="7ff07-117">Estoque financeiro</span><span class="sxs-lookup"><span data-stu-id="7ff07-117">Financial inventory</span></span> |
|-----------|--------|--------------------|---------------------|
| <span data-ttu-id="7ff07-118">Site</span><span class="sxs-lookup"><span data-stu-id="7ff07-118">Site</span></span>      | <span data-ttu-id="7ff07-119">Sim</span><span class="sxs-lookup"><span data-stu-id="7ff07-119">Yes</span></span>    | <span data-ttu-id="7ff07-120">Sim</span><span class="sxs-lookup"><span data-stu-id="7ff07-120">Yes</span></span>                | <span data-ttu-id="7ff07-121">Sim</span><span class="sxs-lookup"><span data-stu-id="7ff07-121">Yes</span></span>                 |
| <span data-ttu-id="7ff07-122">Depósito</span><span class="sxs-lookup"><span data-stu-id="7ff07-122">Warehouse</span></span> | <span data-ttu-id="7ff07-123">Sim</span><span class="sxs-lookup"><span data-stu-id="7ff07-123">Yes</span></span>    | <span data-ttu-id="7ff07-124">Sim</span><span class="sxs-lookup"><span data-stu-id="7ff07-124">Yes</span></span>                | <span data-ttu-id="7ff07-125">Não</span><span class="sxs-lookup"><span data-stu-id="7ff07-125">No</span></span>                  |

### <a name="inventory-model"></a><span data-ttu-id="7ff07-126">Modelo de estoque</span><span class="sxs-lookup"><span data-stu-id="7ff07-126">Inventory model</span></span>

<span data-ttu-id="7ff07-127">Para o sistema de exemplo, o modelo de estoque para os produtos liberados é *PEPS*, e a configuração **Preço de custo** para o modelo de estoque é *Incluir valor físico*.</span><span class="sxs-lookup"><span data-stu-id="7ff07-127">For the example system, the inventory model for the released products is *FIFO*, and the **Cost price** setting for the inventory model is *Include physical value*.</span></span>

### <a name="inventory-transactions"></a><span data-ttu-id="7ff07-128">Transações de estoque</span><span class="sxs-lookup"><span data-stu-id="7ff07-128">Inventory transactions</span></span>

<span data-ttu-id="7ff07-129">O sistema de exemplo contém as seguintes transações de estoque para um produto liberado que tem o número de item *1.000*.</span><span class="sxs-lookup"><span data-stu-id="7ff07-129">The example system contains the following inventory transactions for a released product that has the item number *1000*.</span></span>

| <span data-ttu-id="7ff07-130">Demonstrativo</span><span class="sxs-lookup"><span data-stu-id="7ff07-130">Reference</span></span>      | <span data-ttu-id="7ff07-131">Site</span><span class="sxs-lookup"><span data-stu-id="7ff07-131">Site</span></span> | <span data-ttu-id="7ff07-132">Depósito</span><span class="sxs-lookup"><span data-stu-id="7ff07-132">Warehouse</span></span> | <span data-ttu-id="7ff07-133">Recebimento</span><span class="sxs-lookup"><span data-stu-id="7ff07-133">Receipt</span></span>   | <span data-ttu-id="7ff07-134">Problema</span><span class="sxs-lookup"><span data-stu-id="7ff07-134">Issue</span></span> | <span data-ttu-id="7ff07-135">Data física</span><span class="sxs-lookup"><span data-stu-id="7ff07-135">Physical date</span></span> | <span data-ttu-id="7ff07-136">Data financeira</span><span class="sxs-lookup"><span data-stu-id="7ff07-136">Financial date</span></span> | <span data-ttu-id="7ff07-137">Quantidade</span><span class="sxs-lookup"><span data-stu-id="7ff07-137">Quantity</span></span> | <span data-ttu-id="7ff07-138">Valor de custo</span><span class="sxs-lookup"><span data-stu-id="7ff07-138">Cost amount</span></span> | <span data-ttu-id="7ff07-139">Valor de custo físico</span><span class="sxs-lookup"><span data-stu-id="7ff07-139">Physical cost amount</span></span> |
|----------------|------|-----------|-----------|-------|---------------|----------------|----------|-------------|----------------------|
| <span data-ttu-id="7ff07-140">Ordem de Compra</span><span class="sxs-lookup"><span data-stu-id="7ff07-140">Purchase order</span></span> | <span data-ttu-id="7ff07-141">1</span><span class="sxs-lookup"><span data-stu-id="7ff07-141">1</span></span>    | <span data-ttu-id="7ff07-142">11</span><span class="sxs-lookup"><span data-stu-id="7ff07-142">11</span></span>        | <span data-ttu-id="7ff07-143">Comprado</span><span class="sxs-lookup"><span data-stu-id="7ff07-143">Purchased</span></span> |       | <span data-ttu-id="7ff07-144">15 de março</span><span class="sxs-lookup"><span data-stu-id="7ff07-144">March 15</span></span>      | <span data-ttu-id="7ff07-145">15 de março</span><span class="sxs-lookup"><span data-stu-id="7ff07-145">March 15</span></span>       | <span data-ttu-id="7ff07-146">10</span><span class="sxs-lookup"><span data-stu-id="7ff07-146">10</span></span>       | <span data-ttu-id="7ff07-147">1.000</span><span class="sxs-lookup"><span data-stu-id="7ff07-147">1,000</span></span>       | <span data-ttu-id="7ff07-148">1.000</span><span class="sxs-lookup"><span data-stu-id="7ff07-148">1,000</span></span>                |
| <span data-ttu-id="7ff07-149">Ordem de Compra</span><span class="sxs-lookup"><span data-stu-id="7ff07-149">Purchase order</span></span> | <span data-ttu-id="7ff07-150">2</span><span class="sxs-lookup"><span data-stu-id="7ff07-150">2</span></span>    | <span data-ttu-id="7ff07-151">21</span><span class="sxs-lookup"><span data-stu-id="7ff07-151">21</span></span>        | <span data-ttu-id="7ff07-152">Comprado</span><span class="sxs-lookup"><span data-stu-id="7ff07-152">Purchased</span></span> |       | <span data-ttu-id="7ff07-153">15 de março</span><span class="sxs-lookup"><span data-stu-id="7ff07-153">March 15</span></span>      | <span data-ttu-id="7ff07-154">15 de março</span><span class="sxs-lookup"><span data-stu-id="7ff07-154">March 15</span></span>       | <span data-ttu-id="7ff07-155">10</span><span class="sxs-lookup"><span data-stu-id="7ff07-155">10</span></span>       | <span data-ttu-id="7ff07-156">2,000</span><span class="sxs-lookup"><span data-stu-id="7ff07-156">2,000</span></span>       | <span data-ttu-id="7ff07-157">2,000</span><span class="sxs-lookup"><span data-stu-id="7ff07-157">2,000</span></span>                |
| <span data-ttu-id="7ff07-158">Ordem de Compra</span><span class="sxs-lookup"><span data-stu-id="7ff07-158">Purchase order</span></span> | <span data-ttu-id="7ff07-159">1</span><span class="sxs-lookup"><span data-stu-id="7ff07-159">1</span></span>    | <span data-ttu-id="7ff07-160">11</span><span class="sxs-lookup"><span data-stu-id="7ff07-160">11</span></span>        | <span data-ttu-id="7ff07-161">Recebida</span><span class="sxs-lookup"><span data-stu-id="7ff07-161">Received</span></span>  |       | <span data-ttu-id="7ff07-162">15 de abril</span><span class="sxs-lookup"><span data-stu-id="7ff07-162">April 15</span></span>      |                | <span data-ttu-id="7ff07-163">5</span><span class="sxs-lookup"><span data-stu-id="7ff07-163">5</span></span>        |             | <span data-ttu-id="7ff07-164">375</span><span class="sxs-lookup"><span data-stu-id="7ff07-164">375</span></span>                  |
| <span data-ttu-id="7ff07-165">Ordem de transferência</span><span class="sxs-lookup"><span data-stu-id="7ff07-165">Transfer order</span></span> | <span data-ttu-id="7ff07-166">1</span><span class="sxs-lookup"><span data-stu-id="7ff07-166">1</span></span>    | <span data-ttu-id="7ff07-167">11</span><span class="sxs-lookup"><span data-stu-id="7ff07-167">11</span></span>        |           | <span data-ttu-id="7ff07-168">Vendido</span><span class="sxs-lookup"><span data-stu-id="7ff07-168">Sold</span></span>  | <span data-ttu-id="7ff07-169">Maio de 2</span><span class="sxs-lookup"><span data-stu-id="7ff07-169">May 2</span></span>         | <span data-ttu-id="7ff07-170">Maio de 2</span><span class="sxs-lookup"><span data-stu-id="7ff07-170">May 2</span></span>          | <span data-ttu-id="7ff07-171">-5</span><span class="sxs-lookup"><span data-stu-id="7ff07-171">-5</span></span>       | <span data-ttu-id="7ff07-172">-458,33</span><span class="sxs-lookup"><span data-stu-id="7ff07-172">-458.33</span></span>     | <span data-ttu-id="7ff07-173">-458,33</span><span class="sxs-lookup"><span data-stu-id="7ff07-173">-458.33</span></span>              |
| <span data-ttu-id="7ff07-174">Ordem de transferência</span><span class="sxs-lookup"><span data-stu-id="7ff07-174">Transfer order</span></span> | <span data-ttu-id="7ff07-175">1</span><span class="sxs-lookup"><span data-stu-id="7ff07-175">1</span></span>    | <span data-ttu-id="7ff07-176">12</span><span class="sxs-lookup"><span data-stu-id="7ff07-176">12</span></span>        | <span data-ttu-id="7ff07-177">Comprado</span><span class="sxs-lookup"><span data-stu-id="7ff07-177">Purchased</span></span> |       | <span data-ttu-id="7ff07-178">Maio de 2</span><span class="sxs-lookup"><span data-stu-id="7ff07-178">May 2</span></span>         | <span data-ttu-id="7ff07-179">Maio de 2</span><span class="sxs-lookup"><span data-stu-id="7ff07-179">May 2</span></span>          | <span data-ttu-id="7ff07-180">5</span><span class="sxs-lookup"><span data-stu-id="7ff07-180">5</span></span>        | <span data-ttu-id="7ff07-181">458.33</span><span class="sxs-lookup"><span data-stu-id="7ff07-181">458.33</span></span>      | <span data-ttu-id="7ff07-182">458.33</span><span class="sxs-lookup"><span data-stu-id="7ff07-182">458.33</span></span>               |
| <span data-ttu-id="7ff07-183">Ordem de Venda</span><span class="sxs-lookup"><span data-stu-id="7ff07-183">Sales order</span></span>    | <span data-ttu-id="7ff07-184">1</span><span class="sxs-lookup"><span data-stu-id="7ff07-184">1</span></span>    | <span data-ttu-id="7ff07-185">12</span><span class="sxs-lookup"><span data-stu-id="7ff07-185">12</span></span>        |           | <span data-ttu-id="7ff07-186">Vendido</span><span class="sxs-lookup"><span data-stu-id="7ff07-186">Sold</span></span>  | <span data-ttu-id="7ff07-187">Maio de 3</span><span class="sxs-lookup"><span data-stu-id="7ff07-187">May 3</span></span>         | <span data-ttu-id="7ff07-188">Maio de 3</span><span class="sxs-lookup"><span data-stu-id="7ff07-188">May 3</span></span>          | <span data-ttu-id="7ff07-189">-1</span><span class="sxs-lookup"><span data-stu-id="7ff07-189">-1</span></span>       | <span data-ttu-id="7ff07-190">-91,67</span><span class="sxs-lookup"><span data-stu-id="7ff07-190">-91.67</span></span>      | <span data-ttu-id="7ff07-191">-91,67</span><span class="sxs-lookup"><span data-stu-id="7ff07-191">-91.67</span></span>               |

## <a name="how-quantities-and-amounts-in-each-period-bucket-are-calculated"></a><span data-ttu-id="7ff07-192">Como as quantidades e os valores em cada bucket de período são calculados</span><span class="sxs-lookup"><span data-stu-id="7ff07-192">How quantities and amounts in each period bucket are calculated</span></span>

<span data-ttu-id="7ff07-193">Usando os dados de exemplo descritos nas seções anteriores, você pode executar um relatório **Classificação por vencimento de estoque** com as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="7ff07-193">By using the sample data that is described in the previous sections, you can run an **Inventory aging** report that has the following settings:</span></span>

- <span data-ttu-id="7ff07-194">**A partir da data:** *9 de maio de 2020*</span><span class="sxs-lookup"><span data-stu-id="7ff07-194">**As of date:** *May 9, 2020*</span></span>
- <span data-ttu-id="7ff07-195">**Site:** *Exibir*</span><span class="sxs-lookup"><span data-stu-id="7ff07-195">**Site:** *View*</span></span>
- <span data-ttu-id="7ff07-196">**Depósito:** *Não*</span><span class="sxs-lookup"><span data-stu-id="7ff07-196">**Warehouse:** *No*</span></span>
- <span data-ttu-id="7ff07-197">**Número do item:** *Total*</span><span class="sxs-lookup"><span data-stu-id="7ff07-197">**Item number:** *Total*</span></span>
- <span data-ttu-id="7ff07-198">**Período de classificação por vencimento:** defina esse campo para gerar buckets mensais.</span><span class="sxs-lookup"><span data-stu-id="7ff07-198">**Aging period:** Set this field to generate monthly buckets.</span></span>

<span data-ttu-id="7ff07-199">Nesse caso, o conteúdo do relatório gerado será semelhante ao exemplo a seguir.</span><span class="sxs-lookup"><span data-stu-id="7ff07-199">In this case, the content of the report that is generated will resemble the following example.</span></span>

<table>
<thead>
<tr>
    <th rowspan="2"><span data-ttu-id="7ff07-200">Nº de itens</span><span class="sxs-lookup"><span data-stu-id="7ff07-200">Item number</span></span></th>
    <th rowspan="2"><span data-ttu-id="7ff07-201">Site</span><span class="sxs-lookup"><span data-stu-id="7ff07-201">Site</span></span></th>
    <th rowspan="2"><span data-ttu-id="7ff07-202">Quantidade disponível</span><span class="sxs-lookup"><span data-stu-id="7ff07-202">On-hand quantity</span></span></th>
    <th rowspan="2"><span data-ttu-id="7ff07-203">Valor disponível</span><span class="sxs-lookup"><span data-stu-id="7ff07-203">On-hand value</span></span></th>
    <th rowspan="2"><span data-ttu-id="7ff07-204">Quantidade do valor do estoque</span><span class="sxs-lookup"><span data-stu-id="7ff07-204">Inventory value quantity</span></span></th>
    <th rowspan="2"><span data-ttu-id="7ff07-205">Valor do estoque</span><span class="sxs-lookup"><span data-stu-id="7ff07-205">Inventory value</span></span></th>
    <th rowspan="2"><span data-ttu-id="7ff07-206">Custo unitário médio</span><span class="sxs-lookup"><span data-stu-id="7ff07-206">Average unit cost</span></span></th>
    <th colspan="2"><span data-ttu-id="7ff07-207">8/5/2020 - 1/5/2020</span><span class="sxs-lookup"><span data-stu-id="7ff07-207">5/8/2020 - 5/1/2020</span></span></th>
    <th colspan="2"><span data-ttu-id="7ff07-208">30/4/2020 - 1/4/2020</span><span class="sxs-lookup"><span data-stu-id="7ff07-208">4/30/2020 - 4/1/2020</span></span></th>
    <th colspan="2"><span data-ttu-id="7ff07-209">31/3/2020 - 1/3/2020</span><span class="sxs-lookup"><span data-stu-id="7ff07-209">3/31/2020 - 3/1/2020</span></span></th>
</tr>
<tr>
    <th><span data-ttu-id="7ff07-210">P1:Quantidade</span><span class="sxs-lookup"><span data-stu-id="7ff07-210">P1:Quantity</span></span></th>
    <th><span data-ttu-id="7ff07-211">P1:Valor</span><span class="sxs-lookup"><span data-stu-id="7ff07-211">P1:Amount</span></span></th>
    <th><span data-ttu-id="7ff07-212">P2:Quantidade</span><span class="sxs-lookup"><span data-stu-id="7ff07-212">P2:Quantity</span></span></th>
    <th><span data-ttu-id="7ff07-213">P2:Valor</span><span class="sxs-lookup"><span data-stu-id="7ff07-213">P2:Amount</span></span></th>
    <th><span data-ttu-id="7ff07-214">P3:Quantidade</span><span class="sxs-lookup"><span data-stu-id="7ff07-214">P3:Quantity</span></span></th>
    <th><span data-ttu-id="7ff07-215">P3:Valor</span><span class="sxs-lookup"><span data-stu-id="7ff07-215">P3:Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
    <td><span data-ttu-id="7ff07-216">1000</span><span class="sxs-lookup"><span data-stu-id="7ff07-216">1000</span></span></td>
    <td><span data-ttu-id="7ff07-217">1</span><span class="sxs-lookup"><span data-stu-id="7ff07-217">1</span></span></td>
    <td><span data-ttu-id="7ff07-218">14</span><span class="sxs-lookup"><span data-stu-id="7ff07-218">14</span></span></td>
    <td><span data-ttu-id="7ff07-219">1,283.33</span><span class="sxs-lookup"><span data-stu-id="7ff07-219">1,283.33</span></span></td>
    <td><span data-ttu-id="7ff07-220">14</span><span class="sxs-lookup"><span data-stu-id="7ff07-220">14</span></span></td>
    <td><span data-ttu-id="7ff07-221">1,283.33</span><span class="sxs-lookup"><span data-stu-id="7ff07-221">1,283.33</span></span></td>
    <td><span data-ttu-id="7ff07-222">91.67</span><span class="sxs-lookup"><span data-stu-id="7ff07-222">91.67</span></span></td>
    <td></td>
    <td></td>
    <td><span data-ttu-id="7ff07-223">5.00</span><span class="sxs-lookup"><span data-stu-id="7ff07-223">5.00</span></span></td>
    <td><span data-ttu-id="7ff07-224">458.33</span><span class="sxs-lookup"><span data-stu-id="7ff07-224">458.33</span></span></td>
    <td><span data-ttu-id="7ff07-225">9.00</span><span class="sxs-lookup"><span data-stu-id="7ff07-225">9.00</span></span></td>
    <td><span data-ttu-id="7ff07-226">825.00</span><span class="sxs-lookup"><span data-stu-id="7ff07-226">825.00</span></span></td>
</tr>
<tr>
    <td><span data-ttu-id="7ff07-227">1000</span><span class="sxs-lookup"><span data-stu-id="7ff07-227">1000</span></span></td>
    <td><span data-ttu-id="7ff07-228">2</span><span class="sxs-lookup"><span data-stu-id="7ff07-228">2</span></span></td>
    <td><span data-ttu-id="7ff07-229">10</span><span class="sxs-lookup"><span data-stu-id="7ff07-229">10</span></span></td>
    <td><span data-ttu-id="7ff07-230">2,000.00</span><span class="sxs-lookup"><span data-stu-id="7ff07-230">2,000.00</span></span></td>
    <td><span data-ttu-id="7ff07-231">10</span><span class="sxs-lookup"><span data-stu-id="7ff07-231">10</span></span></td>
    <td><span data-ttu-id="7ff07-232">2,000.00</span><span class="sxs-lookup"><span data-stu-id="7ff07-232">2,000.00</span></span></td>
    <td><span data-ttu-id="7ff07-233">200.00</span><span class="sxs-lookup"><span data-stu-id="7ff07-233">200.00</span></span></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td><span data-ttu-id="7ff07-234">10,00</span><span class="sxs-lookup"><span data-stu-id="7ff07-234">10.00</span></span></td>
    <td><span data-ttu-id="7ff07-235">2,000.00</span><span class="sxs-lookup"><span data-stu-id="7ff07-235">2,000.00</span></span></td>
</tr>
</tbody>
<tfoot>
<tr>
    <td><span data-ttu-id="7ff07-236"><strong>Totais de 1.000</strong></span><span class="sxs-lookup"><span data-stu-id="7ff07-236"><strong>1000 Totals</strong></span></span></td>
    <td></td>
    <td><span data-ttu-id="7ff07-237"><strong>24.00</strong></span><span class="sxs-lookup"><span data-stu-id="7ff07-237"><strong>24.00</strong></span></span></td>
    <td><span data-ttu-id="7ff07-238"><strong>3,283.33</strong></span><span class="sxs-lookup"><span data-stu-id="7ff07-238"><strong>3,283.33</strong></span></span></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td><span data-ttu-id="7ff07-239"><strong>5.00</strong></span><span class="sxs-lookup"><span data-stu-id="7ff07-239"><strong>5.00</strong></span></span></td>
    <td><span data-ttu-id="7ff07-240"><strong>458.33</strong></span><span class="sxs-lookup"><span data-stu-id="7ff07-240"><strong>458.33</strong></span></span></td>
    <td><span data-ttu-id="7ff07-241"><strong>19</strong></span><span class="sxs-lookup"><span data-stu-id="7ff07-241"><strong>19</strong></span></span></td>
    <td><span data-ttu-id="7ff07-242"><strong>2,825.00</strong></span><span class="sxs-lookup"><span data-stu-id="7ff07-242"><strong>2,825.00</strong></span></span></td>
</tr>
</tfoot>
</table>

<span data-ttu-id="7ff07-243">Observe os seguintes detalhes neste exemplo de relatório:</span><span class="sxs-lookup"><span data-stu-id="7ff07-243">Note the following details in this example report:</span></span>

- <span data-ttu-id="7ff07-244">Os valores de **Quantidade de valor de estoque**, **Valor de estoque** e **Custo unitário médio** exibidos no relatório são valores para a dimensão de estoque financeira (**Site**, neste caso).</span><span class="sxs-lookup"><span data-stu-id="7ff07-244">The **Inventory value quantity**, **Inventory value**, and **Average unit cost** values that are shown on the report are values for the financial inventory dimension (**Site**, in this case).</span></span>

    <span data-ttu-id="7ff07-245">Por exemplo, para o site 1, o relatório mostra as seguintes informações:</span><span class="sxs-lookup"><span data-stu-id="7ff07-245">For example, for site 1, the report shows the following information:</span></span>

    - <span data-ttu-id="7ff07-246">O valor de **Quantidade de valor em estoque** é *14* (= 10 + 5 – 5 + 5 – 1).</span><span class="sxs-lookup"><span data-stu-id="7ff07-246">The **Inventory value quantity** value is *14* (= 10 + 5 – 5 + 5 – 1).</span></span>
    - <span data-ttu-id="7ff07-247">O valor de **Valor em estoque** é *1.283,33* (= 1.000 + 375 – 458,33 + 458,33 – 91,67).</span><span class="sxs-lookup"><span data-stu-id="7ff07-247">The **Inventory value** value is *1,283.33* (= 1,000 + 375 – 458.33 + 458.33 – 91.67).</span></span>
    - <span data-ttu-id="7ff07-248">O valor de **Custo unitário médio** é *91,67*.</span><span class="sxs-lookup"><span data-stu-id="7ff07-248">The **Average unit cost** value is *91.67*.</span></span>
    - <span data-ttu-id="7ff07-249">O valor de **Valor disponível** e o valor de **Valor** em cada bucket de período são calculados usando-se o valor de **Custo unitário médio**.</span><span class="sxs-lookup"><span data-stu-id="7ff07-249">The **On-hand value** value and the **Amount** value in each period bucket are calculated by using the **Average unit cost** value.</span></span>

- <span data-ttu-id="7ff07-250">O relatório determina a quantidade disponível para cada bucket de período resumindo a quantidade de estoque total recebida para cada bucket de período.</span><span class="sxs-lookup"><span data-stu-id="7ff07-250">The report determines the on-hand quantity for each period bucket by summarizing the total received inventory quantity for each period bucket.</span></span> <span data-ttu-id="7ff07-251">Em seguida, ele aplica o princípio PEPS (primeiro a entrar, primeiro a sair) para deduzir a quantidade emitida total, independentemente do modelo de estoque usado pelos itens.</span><span class="sxs-lookup"><span data-stu-id="7ff07-251">It then applies the first in, first out (FIFO) principle to deduct the total issued quantity, regardless of the inventory model that the items use.</span></span>

<span data-ttu-id="7ff07-252">Se você executar o mesmo relatório novamente, mas, desta vez, definir os campos **Site** e **Depósito** como *Exibir*, o novo relatório será semelhante ao exemplo a seguir.</span><span class="sxs-lookup"><span data-stu-id="7ff07-252">If you run the same report again, but this time you set both the **Site** and **Warehouse** fields to *View*, the new report will resemble the following example.</span></span>

<table>
<thead>
<tr>
    <th rowspan="2"><span data-ttu-id="7ff07-253">Nº de itens</span><span class="sxs-lookup"><span data-stu-id="7ff07-253">Item number</span></span></th>
    <th rowspan="2"><span data-ttu-id="7ff07-254">Site</span><span class="sxs-lookup"><span data-stu-id="7ff07-254">Site</span></span></th>
    <th rowspan="2"><span data-ttu-id="7ff07-255">Depósito</span><span class="sxs-lookup"><span data-stu-id="7ff07-255">Warehouse</span></span></th>
    <th rowspan="2"><span data-ttu-id="7ff07-256">Quantidade disponível</span><span class="sxs-lookup"><span data-stu-id="7ff07-256">On-hand quantity</span></span></th>
    <th rowspan="2"><span data-ttu-id="7ff07-257">Valor disponível</span><span class="sxs-lookup"><span data-stu-id="7ff07-257">On-hand value</span></span></th>
    <th rowspan="2"><span data-ttu-id="7ff07-258">Quantidade do valor do estoque</span><span class="sxs-lookup"><span data-stu-id="7ff07-258">Inventory value quantity</span></span></th>
    <th rowspan="2"><span data-ttu-id="7ff07-259">Valor do estoque</span><span class="sxs-lookup"><span data-stu-id="7ff07-259">Inventory value</span></span></th>
    <th rowspan="2"><span data-ttu-id="7ff07-260">Custo unitário médio</span><span class="sxs-lookup"><span data-stu-id="7ff07-260">Average unit cost</span></span></th>
    <th colspan="2"><span data-ttu-id="7ff07-261">8/5/2020 - 1/5/2020</span><span class="sxs-lookup"><span data-stu-id="7ff07-261">5/8/2020 - 5/1/2020</span></span></th>
    <th colspan="2"><span data-ttu-id="7ff07-262">30/4/2020 - 1/4/2020</span><span class="sxs-lookup"><span data-stu-id="7ff07-262">4/30/2020 - 4/1/2020</span></span></th>
    <th colspan="2"><span data-ttu-id="7ff07-263">31/3/2020 - 1/3/2020</span><span class="sxs-lookup"><span data-stu-id="7ff07-263">3/31/2020 - 3/1/2020</span></span></th>
</tr>
<tr>
    <th><span data-ttu-id="7ff07-264">P1:Quantidade</span><span class="sxs-lookup"><span data-stu-id="7ff07-264">P1:Quantity</span></span></th>
    <th><span data-ttu-id="7ff07-265">P1:Valor</span><span class="sxs-lookup"><span data-stu-id="7ff07-265">P1:Amount</span></span></th>
    <th><span data-ttu-id="7ff07-266">P2:Quantidade</span><span class="sxs-lookup"><span data-stu-id="7ff07-266">P2:Quantity</span></span></th>
    <th><span data-ttu-id="7ff07-267">P2:Valor</span><span class="sxs-lookup"><span data-stu-id="7ff07-267">P2:Amount</span></span></th>
    <th><span data-ttu-id="7ff07-268">P3:Quantidade</span><span class="sxs-lookup"><span data-stu-id="7ff07-268">P3:Quantity</span></span></th>
    <th><span data-ttu-id="7ff07-269">P3:Valor</span><span class="sxs-lookup"><span data-stu-id="7ff07-269">P3:Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
    <td><span data-ttu-id="7ff07-270">1000</span><span class="sxs-lookup"><span data-stu-id="7ff07-270">1000</span></span></td>
    <td><span data-ttu-id="7ff07-271">1</span><span class="sxs-lookup"><span data-stu-id="7ff07-271">1</span></span></td>
    <td><span data-ttu-id="7ff07-272">11</span><span class="sxs-lookup"><span data-stu-id="7ff07-272">11</span></span></td>
    <td><span data-ttu-id="7ff07-273">10</span><span class="sxs-lookup"><span data-stu-id="7ff07-273">10</span></span></td>
    <td><span data-ttu-id="7ff07-274">916.67</span><span class="sxs-lookup"><span data-stu-id="7ff07-274">916.67</span></span></td>
    <td><span data-ttu-id="7ff07-275">14</span><span class="sxs-lookup"><span data-stu-id="7ff07-275">14</span></span></td>
    <td><span data-ttu-id="7ff07-276">1,283.33</span><span class="sxs-lookup"><span data-stu-id="7ff07-276">1,283.33</span></span></td>
    <td><span data-ttu-id="7ff07-277">91.67</span><span class="sxs-lookup"><span data-stu-id="7ff07-277">91.67</span></span></td>
    <td></td>
    <td></td>
    <td><span data-ttu-id="7ff07-278">5.00</span><span class="sxs-lookup"><span data-stu-id="7ff07-278">5.00</span></span></td>
    <td><span data-ttu-id="7ff07-279">458.33</span><span class="sxs-lookup"><span data-stu-id="7ff07-279">458.33</span></span></td>
    <td><span data-ttu-id="7ff07-280">5.00</span><span class="sxs-lookup"><span data-stu-id="7ff07-280">5.00</span></span></td>
    <td><span data-ttu-id="7ff07-281">458.33</span><span class="sxs-lookup"><span data-stu-id="7ff07-281">458.33</span></span></td>
</tr>
<tr>
    <td><span data-ttu-id="7ff07-282">1000</span><span class="sxs-lookup"><span data-stu-id="7ff07-282">1000</span></span></td>
    <td><span data-ttu-id="7ff07-283">1</span><span class="sxs-lookup"><span data-stu-id="7ff07-283">1</span></span></td>
    <td><span data-ttu-id="7ff07-284">12</span><span class="sxs-lookup"><span data-stu-id="7ff07-284">12</span></span></td>
    <td><span data-ttu-id="7ff07-285">4</span><span class="sxs-lookup"><span data-stu-id="7ff07-285">4</span></span></td>
    <td><span data-ttu-id="7ff07-286">366.67</span><span class="sxs-lookup"><span data-stu-id="7ff07-286">366.67</span></span></td>
    <td><span data-ttu-id="7ff07-287">14</span><span class="sxs-lookup"><span data-stu-id="7ff07-287">14</span></span></td>
    <td><span data-ttu-id="7ff07-288">1,283.33</span><span class="sxs-lookup"><span data-stu-id="7ff07-288">1,283.33</span></span></td>
    <td><span data-ttu-id="7ff07-289">91.67</span><span class="sxs-lookup"><span data-stu-id="7ff07-289">91.67</span></span></td>
    <td><span data-ttu-id="7ff07-290">4.00</span><span class="sxs-lookup"><span data-stu-id="7ff07-290">4.00</span></span></td>
    <td><span data-ttu-id="7ff07-291">366.67</span><span class="sxs-lookup"><span data-stu-id="7ff07-291">366.67</span></span></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
</tr>
<tr>
    <td><span data-ttu-id="7ff07-292">1000</span><span class="sxs-lookup"><span data-stu-id="7ff07-292">1000</span></span></td>
    <td><span data-ttu-id="7ff07-293">2</span><span class="sxs-lookup"><span data-stu-id="7ff07-293">2</span></span></td>
    <td></td>
    <td><span data-ttu-id="7ff07-294">10</span><span class="sxs-lookup"><span data-stu-id="7ff07-294">10</span></span></td>
    <td><span data-ttu-id="7ff07-295">2,000.00</span><span class="sxs-lookup"><span data-stu-id="7ff07-295">2,000.00</span></span></td>
    <td><span data-ttu-id="7ff07-296">10</span><span class="sxs-lookup"><span data-stu-id="7ff07-296">10</span></span></td>
    <td><span data-ttu-id="7ff07-297">2,000.00</span><span class="sxs-lookup"><span data-stu-id="7ff07-297">2,000.00</span></span></td>
    <td><span data-ttu-id="7ff07-298">200.00</span><span class="sxs-lookup"><span data-stu-id="7ff07-298">200.00</span></span></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td><span data-ttu-id="7ff07-299">10,00</span><span class="sxs-lookup"><span data-stu-id="7ff07-299">10.00</span></span></td>
    <td><span data-ttu-id="7ff07-300">2,000.00</span><span class="sxs-lookup"><span data-stu-id="7ff07-300">2,000.00</span></span></td>
</tr>
</tbody>
<tfoot>
<tr>
    <td><span data-ttu-id="7ff07-301"><strong>Totais de 1.000</strong></span><span class="sxs-lookup"><span data-stu-id="7ff07-301"><strong>1000 Totals</strong></span></span></td>
    <td></td>
    <td></td>
    <td><span data-ttu-id="7ff07-302"><strong>24.00</strong></span><span class="sxs-lookup"><span data-stu-id="7ff07-302"><strong>24.00</strong></span></span></td>
    <td><span data-ttu-id="7ff07-303"><strong>3,283.33</strong></span><span class="sxs-lookup"><span data-stu-id="7ff07-303"><strong>3,283.33</strong></span></span></td>
    <td></td>
    <td></td>
    <td></td>
    <td><span data-ttu-id="7ff07-304"><strong>4.00</strong></span><span class="sxs-lookup"><span data-stu-id="7ff07-304"><strong>4.00</strong></span></span></td>
    <td><span data-ttu-id="7ff07-305"><strong>366.67</strong></span><span class="sxs-lookup"><span data-stu-id="7ff07-305"><strong>366.67</strong></span></span></td>
    <td><span data-ttu-id="7ff07-306"><strong>5.00</strong></span><span class="sxs-lookup"><span data-stu-id="7ff07-306"><strong>5.00</strong></span></span></td>
    <td><span data-ttu-id="7ff07-307"><strong>458.33</strong></span><span class="sxs-lookup"><span data-stu-id="7ff07-307"><strong>458.33</strong></span></span></td>
    <td><span data-ttu-id="7ff07-308"><strong>15</strong></span><span class="sxs-lookup"><span data-stu-id="7ff07-308"><strong>15</strong></span></span></td>
    <td><span data-ttu-id="7ff07-309"><strong>2,458.33</strong></span><span class="sxs-lookup"><span data-stu-id="7ff07-309"><strong>2,458.33</strong></span></span></td>
</tr>
</tfoot>
</table>

<span data-ttu-id="7ff07-310">Desta vez, o site 1 é dividido em duas linhas, uma para o depósito 11 e outra para o depósito 12.</span><span class="sxs-lookup"><span data-stu-id="7ff07-310">This time, site 1 is split into two rows, one for warehouse 11 and one for warehouse 12.</span></span> <span data-ttu-id="7ff07-311">No entanto, os valores de **Quantidade de valor de estoque**, **Valor de estoque** e **Custo unitário médio** são iguais, já que **Depósito** não é uma dimensão de estoque financeira.</span><span class="sxs-lookup"><span data-stu-id="7ff07-311">However, the **Inventory value quantity**, **Inventory value**, and **Average unit cost** values are the same, because **Warehouse** isn't a financial inventory dimension.</span></span>

<span data-ttu-id="7ff07-312">Além disso, observe que a distribuição de quantidade do site 1 é diferente.</span><span class="sxs-lookup"><span data-stu-id="7ff07-312">Additionally, notice that the quantity distribution of site 1 is different.</span></span> <span data-ttu-id="7ff07-313">No primeiro relatório que você executou, o sistema ignorou a ordem de transferência ocorrida no mesmo site e deduziu a quantidade da fatura de venda do bucket de período **31/3/2020-1/3/2020** no site 1.</span><span class="sxs-lookup"><span data-stu-id="7ff07-313">In the first report that you ran, the system ignored the transfer order that occurred in the same site and deducted the quantity of the sales invoice from the **3/31/2020 - 3/1/2020** period bucket in site 1.</span></span> <span data-ttu-id="7ff07-314">No entanto, no novo relatório, o sistema deduz a quantidade da fatura de venda do bucket de período **8/5/2020-1/5/2020** no depósito 12.</span><span class="sxs-lookup"><span data-stu-id="7ff07-314">However, in the new report, the system deducts the quantity of the sales invoice from the **5/8/2020 - 5/1/2020** period bucket in warehouse 12.</span></span>

## <a name="effects-of-inventory-closing"></a><span data-ttu-id="7ff07-315">Efeitos do fechamento de estoque</span><span class="sxs-lookup"><span data-stu-id="7ff07-315">Effects of inventory closing</span></span>

<span data-ttu-id="7ff07-316">Se você executar o fechamento de estoque para maio e executar o relatório anterior novamente, mas definir o campo **A partir da data** como *31 de maio de 2020*, os seguintes resultados serão observados:</span><span class="sxs-lookup"><span data-stu-id="7ff07-316">If you run the inventory closing for May and then run the previous report again, but you set the **As of date** field to *May 31, 2020*, you will notice the following results:</span></span>

- <span data-ttu-id="7ff07-317">Os valores **Valor de estoque** e **Custo unitário médio** são atualizados.</span><span class="sxs-lookup"><span data-stu-id="7ff07-317">The **Inventory value** and **Average unit cost** values are updated.</span></span>
- <span data-ttu-id="7ff07-318">O valor de **Valor disponível** e todos os valores de **Valor** em cada bucket de período são atualizados adequadamente.</span><span class="sxs-lookup"><span data-stu-id="7ff07-318">The **On-hand value** value and all the **Amount** values in every period bucket are updated accordingly.</span></span>

<span data-ttu-id="7ff07-319">O novo relatório se assemelhará ao seguinte exemplo.</span><span class="sxs-lookup"><span data-stu-id="7ff07-319">The new report will resemble the following example.</span></span>

<table>
<thead>
<tr>
    <th rowspan="2"><span data-ttu-id="7ff07-320">Nº de itens</span><span class="sxs-lookup"><span data-stu-id="7ff07-320">Item number</span></span></th>
    <th rowspan="2"><span data-ttu-id="7ff07-321">Site</span><span class="sxs-lookup"><span data-stu-id="7ff07-321">Site</span></span></th>
    <th rowspan="2"><span data-ttu-id="7ff07-322">Depósito</span><span class="sxs-lookup"><span data-stu-id="7ff07-322">Warehouse</span></span></th>
    <th rowspan="2"><span data-ttu-id="7ff07-323">Quantidade disponível</span><span class="sxs-lookup"><span data-stu-id="7ff07-323">On-hand quantity</span></span></th>
    <th rowspan="2"><span data-ttu-id="7ff07-324">Valor disponível</span><span class="sxs-lookup"><span data-stu-id="7ff07-324">On-hand value</span></span></th>
    <th rowspan="2"><span data-ttu-id="7ff07-325">Quantidade do valor do estoque</span><span class="sxs-lookup"><span data-stu-id="7ff07-325">Inventory value quantity</span></span></th>
    <th rowspan="2"><span data-ttu-id="7ff07-326">Valor do estoque</span><span class="sxs-lookup"><span data-stu-id="7ff07-326">Inventory value</span></span></th>
    <th rowspan="2"><span data-ttu-id="7ff07-327">Custo unitário médio</span><span class="sxs-lookup"><span data-stu-id="7ff07-327">Average unit cost</span></span></th>
    <th colspan="2"><span data-ttu-id="7ff07-328">31/5/2020 - 1/5/2020</span><span class="sxs-lookup"><span data-stu-id="7ff07-328">5/31/2020 - 5/1/2020</span></span></th>
    <th colspan="2"><span data-ttu-id="7ff07-329">30/4/2020 - 1/4/2020</span><span class="sxs-lookup"><span data-stu-id="7ff07-329">4/30/2020 - 4/1/2020</span></span></th>
    <th colspan="2"><span data-ttu-id="7ff07-330">31/3/2020 - 1/3/2020</span><span class="sxs-lookup"><span data-stu-id="7ff07-330">3/31/2020 - 3/1/2020</span></span></th>
</tr>
<tr>
    <th><span data-ttu-id="7ff07-331">P1:Quantidade</span><span class="sxs-lookup"><span data-stu-id="7ff07-331">P1:Quantity</span></span></th>
    <th><span data-ttu-id="7ff07-332">P1:Valor</span><span class="sxs-lookup"><span data-stu-id="7ff07-332">P1:Amount</span></span></th>
    <th><span data-ttu-id="7ff07-333">P2:Quantidade</span><span class="sxs-lookup"><span data-stu-id="7ff07-333">P2:Quantity</span></span></th>
    <th><span data-ttu-id="7ff07-334">P2:Valor</span><span class="sxs-lookup"><span data-stu-id="7ff07-334">P2:Amount</span></span></th>
    <th><span data-ttu-id="7ff07-335">P3:Quantidade</span><span class="sxs-lookup"><span data-stu-id="7ff07-335">P3:Quantity</span></span></th>
    <th><span data-ttu-id="7ff07-336">P3:Valor</span><span class="sxs-lookup"><span data-stu-id="7ff07-336">P3:Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
    <td><span data-ttu-id="7ff07-337">1000</span><span class="sxs-lookup"><span data-stu-id="7ff07-337">1000</span></span></td>
    <td><span data-ttu-id="7ff07-338">1</span><span class="sxs-lookup"><span data-stu-id="7ff07-338">1</span></span></td>
    <td><span data-ttu-id="7ff07-339">11</span><span class="sxs-lookup"><span data-stu-id="7ff07-339">11</span></span></td>
    <td><span data-ttu-id="7ff07-340">10</span><span class="sxs-lookup"><span data-stu-id="7ff07-340">10</span></span></td>
    <td><span data-ttu-id="7ff07-341">910.70</span><span class="sxs-lookup"><span data-stu-id="7ff07-341">910.70</span></span></td>
    <td><span data-ttu-id="7ff07-342">14</span><span class="sxs-lookup"><span data-stu-id="7ff07-342">14</span></span></td>
    <td><span data-ttu-id="7ff07-343">1,275.00</span><span class="sxs-lookup"><span data-stu-id="7ff07-343">1,275.00</span></span></td>
    <td><span data-ttu-id="7ff07-344">91.07</span><span class="sxs-lookup"><span data-stu-id="7ff07-344">91.07</span></span></td>
    <td><span data-ttu-id="7ff07-345">0,00</span><span class="sxs-lookup"><span data-stu-id="7ff07-345">0.00</span></span></td>
    <td></td>
    <td><span data-ttu-id="7ff07-346">5.00</span><span class="sxs-lookup"><span data-stu-id="7ff07-346">5.00</span></span></td>
    <td><span data-ttu-id="7ff07-347">455.36</span><span class="sxs-lookup"><span data-stu-id="7ff07-347">455.36</span></span></td>
    <td><span data-ttu-id="7ff07-348">5.00</span><span class="sxs-lookup"><span data-stu-id="7ff07-348">5.00</span></span></td>
    <td><span data-ttu-id="7ff07-349">455.36</span><span class="sxs-lookup"><span data-stu-id="7ff07-349">455.36</span></span></td>
</tr>
<tr>
    <td><span data-ttu-id="7ff07-350">1000</span><span class="sxs-lookup"><span data-stu-id="7ff07-350">1000</span></span></td>
    <td><span data-ttu-id="7ff07-351">1</span><span class="sxs-lookup"><span data-stu-id="7ff07-351">1</span></span></td>
    <td><span data-ttu-id="7ff07-352">12</span><span class="sxs-lookup"><span data-stu-id="7ff07-352">12</span></span></td>
    <td><span data-ttu-id="7ff07-353">4</span><span class="sxs-lookup"><span data-stu-id="7ff07-353">4</span></span></td>
    <td><span data-ttu-id="7ff07-354">364.29</span><span class="sxs-lookup"><span data-stu-id="7ff07-354">364.29</span></span></td>
    <td><span data-ttu-id="7ff07-355">14</span><span class="sxs-lookup"><span data-stu-id="7ff07-355">14</span></span></td>
    <td><span data-ttu-id="7ff07-356">1,275.00</span><span class="sxs-lookup"><span data-stu-id="7ff07-356">1,275.00</span></span></td>
    <td><span data-ttu-id="7ff07-357">91.07</span><span class="sxs-lookup"><span data-stu-id="7ff07-357">91.07</span></span></td>
    <td><span data-ttu-id="7ff07-358">4.00</span><span class="sxs-lookup"><span data-stu-id="7ff07-358">4.00</span></span></td>
    <td><span data-ttu-id="7ff07-359">364.29</span><span class="sxs-lookup"><span data-stu-id="7ff07-359">364.29</span></span></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
</tr>
<tr>
    <td><span data-ttu-id="7ff07-360">1000</span><span class="sxs-lookup"><span data-stu-id="7ff07-360">1000</span></span></td>
    <td><span data-ttu-id="7ff07-361">2</span><span class="sxs-lookup"><span data-stu-id="7ff07-361">2</span></span></td>
    <td></td>
    <td><span data-ttu-id="7ff07-362">10</span><span class="sxs-lookup"><span data-stu-id="7ff07-362">10</span></span></td>
    <td><span data-ttu-id="7ff07-363">2,000.00</span><span class="sxs-lookup"><span data-stu-id="7ff07-363">2,000.00</span></span></td>
    <td><span data-ttu-id="7ff07-364">10</span><span class="sxs-lookup"><span data-stu-id="7ff07-364">10</span></span></td>
    <td><span data-ttu-id="7ff07-365">2,000.00</span><span class="sxs-lookup"><span data-stu-id="7ff07-365">2,000.00</span></span></td>
    <td><span data-ttu-id="7ff07-366">200.00</span><span class="sxs-lookup"><span data-stu-id="7ff07-366">200.00</span></span></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td><span data-ttu-id="7ff07-367">10,00</span><span class="sxs-lookup"><span data-stu-id="7ff07-367">10.00</span></span></td>
    <td><span data-ttu-id="7ff07-368">2,000.00</span><span class="sxs-lookup"><span data-stu-id="7ff07-368">2,000.00</span></span></td>
</tr>
</tbody>
<tfoot>
<tr>
    <td><span data-ttu-id="7ff07-369"><strong>Totais de 1.000</strong></span><span class="sxs-lookup"><span data-stu-id="7ff07-369"><strong>1000 Totals</strong></span></span></td>
    <td></td>
    <td></td>
    <td><span data-ttu-id="7ff07-370"><strong>24.00</strong></span><span class="sxs-lookup"><span data-stu-id="7ff07-370"><strong>24.00</strong></span></span></td>
    <td><span data-ttu-id="7ff07-371"><strong>3,275.00</strong></span><span class="sxs-lookup"><span data-stu-id="7ff07-371"><strong>3,275.00</strong></span></span></td>
    <td></td>
    <td></td>
    <td></td>
    <td><span data-ttu-id="7ff07-372"><strong>4.00</strong></span><span class="sxs-lookup"><span data-stu-id="7ff07-372"><strong>4.00</strong></span></span></td>
    <td><span data-ttu-id="7ff07-373"><strong>364.29</strong></span><span class="sxs-lookup"><span data-stu-id="7ff07-373"><strong>364.29</strong></span></span></td>
    <td><span data-ttu-id="7ff07-374"><strong>5.00</strong></span><span class="sxs-lookup"><span data-stu-id="7ff07-374"><strong>5.00</strong></span></span></td>
    <td><span data-ttu-id="7ff07-375"><strong>455.36</strong></span><span class="sxs-lookup"><span data-stu-id="7ff07-375"><strong>455.36</strong></span></span></td>
    <td><span data-ttu-id="7ff07-376"><strong>15</strong></span><span class="sxs-lookup"><span data-stu-id="7ff07-376"><strong>15</strong></span></span></td>
    <td><span data-ttu-id="7ff07-377"><strong>2,455.36</strong></span><span class="sxs-lookup"><span data-stu-id="7ff07-377"><strong>2,455.36</strong></span></span></td>
</tr>
</tfoot>
</table>
