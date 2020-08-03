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
ms.search.form: CostAdminWorkspace, CostAnalysisWorkspace
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
ms.openlocfilehash: cb7b7a055c26b53ee3acc3b872acf04fcf089eca
ms.sourcegitcommit: f64fce03ec52f844b05a9e8cac286cb201385002
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/16/2020
ms.locfileid: "3597231"
---
# <a name="inventory-aging-report-examples-and-logic"></a><span data-ttu-id="5f37f-103">Exemplos e lógica de relatório de classificação por vencimento de estoque</span><span class="sxs-lookup"><span data-stu-id="5f37f-103">Inventory aging report examples and logic</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="5f37f-104">Este tópico apresenta alguns exemplos que mostram como interpretar os resultados de um relatório de **classificação por vencimento de estoque**.</span><span class="sxs-lookup"><span data-stu-id="5f37f-104">This topic presents some examples that show how to interpret the results of an **Inventory aging** report.</span></span> <span data-ttu-id="5f37f-105">Este relatório categoriza os valores de estoque e quantidade disponíveis para um item ou grupo de itens selecionado em vários buckets de período.</span><span class="sxs-lookup"><span data-stu-id="5f37f-105">This report categorizes on-hand quantity and inventory values for a selected item or item group into several period buckets.</span></span> <span data-ttu-id="5f37f-106">Este tópico também mostra a lógica interna do relatório.</span><span class="sxs-lookup"><span data-stu-id="5f37f-106">This topic also shows the internal logic of the report.</span></span>

<span data-ttu-id="5f37f-107">Os exemplos neste tópico mostram resultados que são apresentados em um relatório **Classificação por vencimento de estoque** padrão.</span><span class="sxs-lookup"><span data-stu-id="5f37f-107">The examples in this topic show results that are presented on a standard **Inventory aging** report.</span></span> <span data-ttu-id="5f37f-108">No entanto, em geral, recomendamos que você use a versão de [Armazenamento do relatório de classificação por vencimento de estoque](inventory-aging-report-storage.md) desse relatório, especialmente quando houver vários itens e depósitos que devem ser processados.</span><span class="sxs-lookup"><span data-stu-id="5f37f-108">However, in general, we recommend that you use the [Inventory aging report storage](inventory-aging-report-storage.md) version of this report, especially when you have many items and warehouses that must be processed.</span></span> <span data-ttu-id="5f37f-109">A classificação por vencimento de estoque salva cada relatório gerado, mostra os resultados como uma página interativa e um gráfico e permite exportar qualquer relatório salvo.</span><span class="sxs-lookup"><span data-stu-id="5f37f-109">Inventory aging report storage saves each report that you generate, shows the results as an interactive page and a chart, and lets you export any saved report.</span></span>

## <a name="sample-data-that-is-used-in-these-examples"></a><span data-ttu-id="5f37f-110">Dados de exemplo usados nestes exemplos</span><span class="sxs-lookup"><span data-stu-id="5f37f-110">Sample data that is used in these examples</span></span>

<span data-ttu-id="5f37f-111">Os exemplos neste tópico se baseiam nos dados de exemplo de transação de estoque descritos nesta seção.</span><span class="sxs-lookup"><span data-stu-id="5f37f-111">The examples in this topic are based on the sample inventory transaction data that is described in this section.</span></span>

### <a name="storage-dimension-setup"></a><span data-ttu-id="5f37f-112">Configuração de dimensão de armazenamento</span><span class="sxs-lookup"><span data-stu-id="5f37f-112">Storage dimension setup</span></span>

<span data-ttu-id="5f37f-113">O sistema de exemplo contém a seguinte configuração de dimensões de armazenamento.</span><span class="sxs-lookup"><span data-stu-id="5f37f-113">The example system contains the following setup of storage dimensions.</span></span>

| <span data-ttu-id="5f37f-114">Nome</span><span class="sxs-lookup"><span data-stu-id="5f37f-114">Name</span></span>      | <span data-ttu-id="5f37f-115">Ativos</span><span class="sxs-lookup"><span data-stu-id="5f37f-115">Active</span></span> | <span data-ttu-id="5f37f-116">Estoque físico</span><span class="sxs-lookup"><span data-stu-id="5f37f-116">Physical inventory</span></span> | <span data-ttu-id="5f37f-117">Estoque financeiro</span><span class="sxs-lookup"><span data-stu-id="5f37f-117">Financial inventory</span></span> |
|-----------|--------|--------------------|---------------------|
| <span data-ttu-id="5f37f-118">Site</span><span class="sxs-lookup"><span data-stu-id="5f37f-118">Site</span></span>      | <span data-ttu-id="5f37f-119">Sim</span><span class="sxs-lookup"><span data-stu-id="5f37f-119">Yes</span></span>    | <span data-ttu-id="5f37f-120">Sim</span><span class="sxs-lookup"><span data-stu-id="5f37f-120">Yes</span></span>                | <span data-ttu-id="5f37f-121">Sim</span><span class="sxs-lookup"><span data-stu-id="5f37f-121">Yes</span></span>                 |
| <span data-ttu-id="5f37f-122">Depósito</span><span class="sxs-lookup"><span data-stu-id="5f37f-122">Warehouse</span></span> | <span data-ttu-id="5f37f-123">Sim</span><span class="sxs-lookup"><span data-stu-id="5f37f-123">Yes</span></span>    | <span data-ttu-id="5f37f-124">Sim</span><span class="sxs-lookup"><span data-stu-id="5f37f-124">Yes</span></span>                | <span data-ttu-id="5f37f-125">Não</span><span class="sxs-lookup"><span data-stu-id="5f37f-125">No</span></span>                  |

### <a name="inventory-model"></a><span data-ttu-id="5f37f-126">Modelo de estoque</span><span class="sxs-lookup"><span data-stu-id="5f37f-126">Inventory model</span></span>

<span data-ttu-id="5f37f-127">Para o sistema de exemplo, o modelo de estoque para os produtos liberados é *PEPS*, e a configuração **Preço de custo** para o modelo de estoque é *Incluir valor físico*.</span><span class="sxs-lookup"><span data-stu-id="5f37f-127">For the example system, the inventory model for the released products is *FIFO*, and the **Cost price** setting for the inventory model is *Include physical value*.</span></span>

### <a name="inventory-transactions"></a><span data-ttu-id="5f37f-128">Transações de estoque</span><span class="sxs-lookup"><span data-stu-id="5f37f-128">Inventory transactions</span></span>

<span data-ttu-id="5f37f-129">O sistema de exemplo contém as seguintes transações de estoque para um produto liberado que tem o número de item *1.000*.</span><span class="sxs-lookup"><span data-stu-id="5f37f-129">The example system contains the following inventory transactions for a released product that has the item number *1000*.</span></span>

| <span data-ttu-id="5f37f-130">Demonstrativo</span><span class="sxs-lookup"><span data-stu-id="5f37f-130">Reference</span></span>      | <span data-ttu-id="5f37f-131">Site</span><span class="sxs-lookup"><span data-stu-id="5f37f-131">Site</span></span> | <span data-ttu-id="5f37f-132">Depósito</span><span class="sxs-lookup"><span data-stu-id="5f37f-132">Warehouse</span></span> | <span data-ttu-id="5f37f-133">Recebimento</span><span class="sxs-lookup"><span data-stu-id="5f37f-133">Receipt</span></span>   | <span data-ttu-id="5f37f-134">Problema</span><span class="sxs-lookup"><span data-stu-id="5f37f-134">Issue</span></span> | <span data-ttu-id="5f37f-135">Data física</span><span class="sxs-lookup"><span data-stu-id="5f37f-135">Physical date</span></span> | <span data-ttu-id="5f37f-136">Data financeira</span><span class="sxs-lookup"><span data-stu-id="5f37f-136">Financial date</span></span> | <span data-ttu-id="5f37f-137">Quantidade</span><span class="sxs-lookup"><span data-stu-id="5f37f-137">Quantity</span></span> | <span data-ttu-id="5f37f-138">Valor de custo</span><span class="sxs-lookup"><span data-stu-id="5f37f-138">Cost amount</span></span> | <span data-ttu-id="5f37f-139">Valor de custo físico</span><span class="sxs-lookup"><span data-stu-id="5f37f-139">Physical cost amount</span></span> |
|----------------|------|-----------|-----------|-------|---------------|----------------|----------|-------------|----------------------|
| <span data-ttu-id="5f37f-140">Ordem de Compra</span><span class="sxs-lookup"><span data-stu-id="5f37f-140">Purchase order</span></span> | <span data-ttu-id="5f37f-141">1</span><span class="sxs-lookup"><span data-stu-id="5f37f-141">1</span></span>    | <span data-ttu-id="5f37f-142">11</span><span class="sxs-lookup"><span data-stu-id="5f37f-142">11</span></span>        | <span data-ttu-id="5f37f-143">Comprado</span><span class="sxs-lookup"><span data-stu-id="5f37f-143">Purchased</span></span> |       | <span data-ttu-id="5f37f-144">15 de março</span><span class="sxs-lookup"><span data-stu-id="5f37f-144">March 15</span></span>      | <span data-ttu-id="5f37f-145">15 de março</span><span class="sxs-lookup"><span data-stu-id="5f37f-145">March 15</span></span>       | <span data-ttu-id="5f37f-146">10</span><span class="sxs-lookup"><span data-stu-id="5f37f-146">10</span></span>       | <span data-ttu-id="5f37f-147">1.000</span><span class="sxs-lookup"><span data-stu-id="5f37f-147">1,000</span></span>       | <span data-ttu-id="5f37f-148">1.000</span><span class="sxs-lookup"><span data-stu-id="5f37f-148">1,000</span></span>                |
| <span data-ttu-id="5f37f-149">Ordem de Compra</span><span class="sxs-lookup"><span data-stu-id="5f37f-149">Purchase order</span></span> | <span data-ttu-id="5f37f-150">2</span><span class="sxs-lookup"><span data-stu-id="5f37f-150">2</span></span>    | <span data-ttu-id="5f37f-151">21</span><span class="sxs-lookup"><span data-stu-id="5f37f-151">21</span></span>        | <span data-ttu-id="5f37f-152">Comprado</span><span class="sxs-lookup"><span data-stu-id="5f37f-152">Purchased</span></span> |       | <span data-ttu-id="5f37f-153">15 de março</span><span class="sxs-lookup"><span data-stu-id="5f37f-153">March 15</span></span>      | <span data-ttu-id="5f37f-154">15 de março</span><span class="sxs-lookup"><span data-stu-id="5f37f-154">March 15</span></span>       | <span data-ttu-id="5f37f-155">10</span><span class="sxs-lookup"><span data-stu-id="5f37f-155">10</span></span>       | <span data-ttu-id="5f37f-156">2,000</span><span class="sxs-lookup"><span data-stu-id="5f37f-156">2,000</span></span>       | <span data-ttu-id="5f37f-157">2,000</span><span class="sxs-lookup"><span data-stu-id="5f37f-157">2,000</span></span>                |
| <span data-ttu-id="5f37f-158">Ordem de Compra</span><span class="sxs-lookup"><span data-stu-id="5f37f-158">Purchase order</span></span> | <span data-ttu-id="5f37f-159">1</span><span class="sxs-lookup"><span data-stu-id="5f37f-159">1</span></span>    | <span data-ttu-id="5f37f-160">11</span><span class="sxs-lookup"><span data-stu-id="5f37f-160">11</span></span>        | <span data-ttu-id="5f37f-161">Recebida</span><span class="sxs-lookup"><span data-stu-id="5f37f-161">Received</span></span>  |       | <span data-ttu-id="5f37f-162">15 de abril</span><span class="sxs-lookup"><span data-stu-id="5f37f-162">April 15</span></span>      |                | <span data-ttu-id="5f37f-163">5</span><span class="sxs-lookup"><span data-stu-id="5f37f-163">5</span></span>        |             | <span data-ttu-id="5f37f-164">375</span><span class="sxs-lookup"><span data-stu-id="5f37f-164">375</span></span>                  |
| <span data-ttu-id="5f37f-165">Ordem de transferência</span><span class="sxs-lookup"><span data-stu-id="5f37f-165">Transfer order</span></span> | <span data-ttu-id="5f37f-166">1</span><span class="sxs-lookup"><span data-stu-id="5f37f-166">1</span></span>    | <span data-ttu-id="5f37f-167">11</span><span class="sxs-lookup"><span data-stu-id="5f37f-167">11</span></span>        |           | <span data-ttu-id="5f37f-168">Vendido</span><span class="sxs-lookup"><span data-stu-id="5f37f-168">Sold</span></span>  | <span data-ttu-id="5f37f-169">Maio de 2</span><span class="sxs-lookup"><span data-stu-id="5f37f-169">May 2</span></span>         | <span data-ttu-id="5f37f-170">Maio de 2</span><span class="sxs-lookup"><span data-stu-id="5f37f-170">May 2</span></span>          | <span data-ttu-id="5f37f-171">-5</span><span class="sxs-lookup"><span data-stu-id="5f37f-171">-5</span></span>       | <span data-ttu-id="5f37f-172">-458,33</span><span class="sxs-lookup"><span data-stu-id="5f37f-172">-458.33</span></span>     | <span data-ttu-id="5f37f-173">-458,33</span><span class="sxs-lookup"><span data-stu-id="5f37f-173">-458.33</span></span>              |
| <span data-ttu-id="5f37f-174">Ordem de transferência</span><span class="sxs-lookup"><span data-stu-id="5f37f-174">Transfer order</span></span> | <span data-ttu-id="5f37f-175">1</span><span class="sxs-lookup"><span data-stu-id="5f37f-175">1</span></span>    | <span data-ttu-id="5f37f-176">12</span><span class="sxs-lookup"><span data-stu-id="5f37f-176">12</span></span>        | <span data-ttu-id="5f37f-177">Comprado</span><span class="sxs-lookup"><span data-stu-id="5f37f-177">Purchased</span></span> |       | <span data-ttu-id="5f37f-178">Maio de 2</span><span class="sxs-lookup"><span data-stu-id="5f37f-178">May 2</span></span>         | <span data-ttu-id="5f37f-179">Maio de 2</span><span class="sxs-lookup"><span data-stu-id="5f37f-179">May 2</span></span>          | <span data-ttu-id="5f37f-180">5</span><span class="sxs-lookup"><span data-stu-id="5f37f-180">5</span></span>        | <span data-ttu-id="5f37f-181">458.33</span><span class="sxs-lookup"><span data-stu-id="5f37f-181">458.33</span></span>      | <span data-ttu-id="5f37f-182">458.33</span><span class="sxs-lookup"><span data-stu-id="5f37f-182">458.33</span></span>               |
| <span data-ttu-id="5f37f-183">Ordem de Venda</span><span class="sxs-lookup"><span data-stu-id="5f37f-183">Sales order</span></span>    | <span data-ttu-id="5f37f-184">1</span><span class="sxs-lookup"><span data-stu-id="5f37f-184">1</span></span>    | <span data-ttu-id="5f37f-185">12</span><span class="sxs-lookup"><span data-stu-id="5f37f-185">12</span></span>        |           | <span data-ttu-id="5f37f-186">Vendido</span><span class="sxs-lookup"><span data-stu-id="5f37f-186">Sold</span></span>  | <span data-ttu-id="5f37f-187">Maio de 3</span><span class="sxs-lookup"><span data-stu-id="5f37f-187">May 3</span></span>         | <span data-ttu-id="5f37f-188">Maio de 3</span><span class="sxs-lookup"><span data-stu-id="5f37f-188">May 3</span></span>          | <span data-ttu-id="5f37f-189">-1</span><span class="sxs-lookup"><span data-stu-id="5f37f-189">-1</span></span>       | <span data-ttu-id="5f37f-190">-91,67</span><span class="sxs-lookup"><span data-stu-id="5f37f-190">-91.67</span></span>      | <span data-ttu-id="5f37f-191">-91,67</span><span class="sxs-lookup"><span data-stu-id="5f37f-191">-91.67</span></span>               |

## <a name="how-quantities-and-amounts-in-each-period-bucket-are-calculated"></a><span data-ttu-id="5f37f-192">Como as quantidades e os valores em cada bucket de período são calculados</span><span class="sxs-lookup"><span data-stu-id="5f37f-192">How quantities and amounts in each period bucket are calculated</span></span>

<span data-ttu-id="5f37f-193">Usando os dados de exemplo descritos nas seções anteriores, você pode executar um relatório **Classificação por vencimento de estoque** com as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="5f37f-193">By using the sample data that is described in the previous sections, you can run an **Inventory aging** report that has the following settings:</span></span>

- <span data-ttu-id="5f37f-194">**A partir da data:** *9 de maio de 2020*</span><span class="sxs-lookup"><span data-stu-id="5f37f-194">**As of date:** *May 9, 2020*</span></span>
- <span data-ttu-id="5f37f-195">**Site:** *Exibir*</span><span class="sxs-lookup"><span data-stu-id="5f37f-195">**Site:** *View*</span></span>
- <span data-ttu-id="5f37f-196">**Depósito:** *Não*</span><span class="sxs-lookup"><span data-stu-id="5f37f-196">**Warehouse:** *No*</span></span>
- <span data-ttu-id="5f37f-197">**Número do item:** *Total*</span><span class="sxs-lookup"><span data-stu-id="5f37f-197">**Item number:** *Total*</span></span>
- <span data-ttu-id="5f37f-198">**Período de classificação por vencimento:** defina esse campo para gerar buckets mensais.</span><span class="sxs-lookup"><span data-stu-id="5f37f-198">**Aging period:** Set this field to generate monthly buckets.</span></span>

<span data-ttu-id="5f37f-199">Nesse caso, o conteúdo do relatório gerado será semelhante ao exemplo a seguir.</span><span class="sxs-lookup"><span data-stu-id="5f37f-199">In this case, the content of the report that is generated will resemble the following example.</span></span>

<table>
<thead>
<tr>
    <th rowspan="2"><span data-ttu-id="5f37f-200">Nº de itens</span><span class="sxs-lookup"><span data-stu-id="5f37f-200">Item number</span></span></th>
    <th rowspan="2"><span data-ttu-id="5f37f-201">Site</span><span class="sxs-lookup"><span data-stu-id="5f37f-201">Site</span></span></th>
    <th rowspan="2"><span data-ttu-id="5f37f-202">Quantidade disponível</span><span class="sxs-lookup"><span data-stu-id="5f37f-202">On-hand quantity</span></span></th>
    <th rowspan="2"><span data-ttu-id="5f37f-203">Valor disponível</span><span class="sxs-lookup"><span data-stu-id="5f37f-203">On-hand value</span></span></th>
    <th rowspan="2"><span data-ttu-id="5f37f-204">Quantidade do valor do estoque</span><span class="sxs-lookup"><span data-stu-id="5f37f-204">Inventory value quantity</span></span></th>
    <th rowspan="2"><span data-ttu-id="5f37f-205">Valor do estoque</span><span class="sxs-lookup"><span data-stu-id="5f37f-205">Inventory value</span></span></th>
    <th rowspan="2"><span data-ttu-id="5f37f-206">Custo unitário médio</span><span class="sxs-lookup"><span data-stu-id="5f37f-206">Average unit cost</span></span></th>
    <th colspan="2"><span data-ttu-id="5f37f-207">8/5/2020 - 1/5/2020</span><span class="sxs-lookup"><span data-stu-id="5f37f-207">5/8/2020 - 5/1/2020</span></span></th>
    <th colspan="2"><span data-ttu-id="5f37f-208">30/4/2020 - 1/4/2020</span><span class="sxs-lookup"><span data-stu-id="5f37f-208">4/30/2020 - 4/1/2020</span></span></th>
    <th colspan="2"><span data-ttu-id="5f37f-209">31/3/2020 - 1/3/2020</span><span class="sxs-lookup"><span data-stu-id="5f37f-209">3/31/2020 - 3/1/2020</span></span></th>
</tr>
<tr>
    <th><span data-ttu-id="5f37f-210">P1:Quantidade</span><span class="sxs-lookup"><span data-stu-id="5f37f-210">P1:Quantity</span></span></th>
    <th><span data-ttu-id="5f37f-211">P1:Valor</span><span class="sxs-lookup"><span data-stu-id="5f37f-211">P1:Amount</span></span></th>
    <th><span data-ttu-id="5f37f-212">P2:Quantidade</span><span class="sxs-lookup"><span data-stu-id="5f37f-212">P2:Quantity</span></span></th>
    <th><span data-ttu-id="5f37f-213">P2:Valor</span><span class="sxs-lookup"><span data-stu-id="5f37f-213">P2:Amount</span></span></th>
    <th><span data-ttu-id="5f37f-214">P3:Quantidade</span><span class="sxs-lookup"><span data-stu-id="5f37f-214">P3:Quantity</span></span></th>
    <th><span data-ttu-id="5f37f-215">P3:Valor</span><span class="sxs-lookup"><span data-stu-id="5f37f-215">P3:Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
    <td><span data-ttu-id="5f37f-216">1000</span><span class="sxs-lookup"><span data-stu-id="5f37f-216">1000</span></span></td>
    <td><span data-ttu-id="5f37f-217">1</span><span class="sxs-lookup"><span data-stu-id="5f37f-217">1</span></span></td>
    <td><span data-ttu-id="5f37f-218">14</span><span class="sxs-lookup"><span data-stu-id="5f37f-218">14</span></span></td>
    <td><span data-ttu-id="5f37f-219">1,283.33</span><span class="sxs-lookup"><span data-stu-id="5f37f-219">1,283.33</span></span></td>
    <td><span data-ttu-id="5f37f-220">14</span><span class="sxs-lookup"><span data-stu-id="5f37f-220">14</span></span></td>
    <td><span data-ttu-id="5f37f-221">1,283.33</span><span class="sxs-lookup"><span data-stu-id="5f37f-221">1,283.33</span></span></td>
    <td><span data-ttu-id="5f37f-222">91.67</span><span class="sxs-lookup"><span data-stu-id="5f37f-222">91.67</span></span></td>
    <td></td>
    <td></td>
    <td><span data-ttu-id="5f37f-223">5.00</span><span class="sxs-lookup"><span data-stu-id="5f37f-223">5.00</span></span></td>
    <td><span data-ttu-id="5f37f-224">458.33</span><span class="sxs-lookup"><span data-stu-id="5f37f-224">458.33</span></span></td>
    <td><span data-ttu-id="5f37f-225">9.00</span><span class="sxs-lookup"><span data-stu-id="5f37f-225">9.00</span></span></td>
    <td><span data-ttu-id="5f37f-226">825.00</span><span class="sxs-lookup"><span data-stu-id="5f37f-226">825.00</span></span></td>
</tr>
<tr>
    <td><span data-ttu-id="5f37f-227">1000</span><span class="sxs-lookup"><span data-stu-id="5f37f-227">1000</span></span></td>
    <td><span data-ttu-id="5f37f-228">2</span><span class="sxs-lookup"><span data-stu-id="5f37f-228">2</span></span></td>
    <td><span data-ttu-id="5f37f-229">10</span><span class="sxs-lookup"><span data-stu-id="5f37f-229">10</span></span></td>
    <td><span data-ttu-id="5f37f-230">2,000.00</span><span class="sxs-lookup"><span data-stu-id="5f37f-230">2,000.00</span></span></td>
    <td><span data-ttu-id="5f37f-231">10</span><span class="sxs-lookup"><span data-stu-id="5f37f-231">10</span></span></td>
    <td><span data-ttu-id="5f37f-232">2,000.00</span><span class="sxs-lookup"><span data-stu-id="5f37f-232">2,000.00</span></span></td>
    <td><span data-ttu-id="5f37f-233">200.00</span><span class="sxs-lookup"><span data-stu-id="5f37f-233">200.00</span></span></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td><span data-ttu-id="5f37f-234">10,00</span><span class="sxs-lookup"><span data-stu-id="5f37f-234">10.00</span></span></td>
    <td><span data-ttu-id="5f37f-235">2,000.00</span><span class="sxs-lookup"><span data-stu-id="5f37f-235">2,000.00</span></span></td>
</tr>
</tbody>
<tfoot>
<tr>
    <td><span data-ttu-id="5f37f-236"><strong>Totais de 1.000</strong></span><span class="sxs-lookup"><span data-stu-id="5f37f-236"><strong>1000 Totals</strong></span></span></td>
    <td></td>
    <td><span data-ttu-id="5f37f-237"><strong>24.00</strong></span><span class="sxs-lookup"><span data-stu-id="5f37f-237"><strong>24.00</strong></span></span></td>
    <td><span data-ttu-id="5f37f-238"><strong>3,283.33</strong></span><span class="sxs-lookup"><span data-stu-id="5f37f-238"><strong>3,283.33</strong></span></span></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td><span data-ttu-id="5f37f-239"><strong>5.00</strong></span><span class="sxs-lookup"><span data-stu-id="5f37f-239"><strong>5.00</strong></span></span></td>
    <td><span data-ttu-id="5f37f-240"><strong>458.33</strong></span><span class="sxs-lookup"><span data-stu-id="5f37f-240"><strong>458.33</strong></span></span></td>
    <td><span data-ttu-id="5f37f-241"><strong>19</strong></span><span class="sxs-lookup"><span data-stu-id="5f37f-241"><strong>19</strong></span></span></td>
    <td><span data-ttu-id="5f37f-242"><strong>2,825.00</strong></span><span class="sxs-lookup"><span data-stu-id="5f37f-242"><strong>2,825.00</strong></span></span></td>
</tr>
</tfoot>
</table>

<span data-ttu-id="5f37f-243">Observe os seguintes detalhes neste exemplo de relatório:</span><span class="sxs-lookup"><span data-stu-id="5f37f-243">Note the following details in this example report:</span></span>

- <span data-ttu-id="5f37f-244">Os valores de **Quantidade de valor de estoque**, **Valor de estoque** e **Custo unitário médio** exibidos no relatório são valores para a dimensão de estoque financeira (**Site**, neste caso).</span><span class="sxs-lookup"><span data-stu-id="5f37f-244">The **Inventory value quantity**, **Inventory value**, and **Average unit cost** values that are shown on the report are values for the financial inventory dimension (**Site**, in this case).</span></span>

    <span data-ttu-id="5f37f-245">Por exemplo, para o site 1, o relatório mostra as seguintes informações:</span><span class="sxs-lookup"><span data-stu-id="5f37f-245">For example, for site 1, the report shows the following information:</span></span>

    - <span data-ttu-id="5f37f-246">O valor de **Quantidade de valor em estoque** é *14* (= 10 + 5 – 5 + 5 – 1).</span><span class="sxs-lookup"><span data-stu-id="5f37f-246">The **Inventory value quantity** value is *14* (= 10 + 5 – 5 + 5 – 1).</span></span>
    - <span data-ttu-id="5f37f-247">O valor de **Valor em estoque** é *1.283,33* (= 1.000 + 375 – 458,33 + 458,33 – 91,67).</span><span class="sxs-lookup"><span data-stu-id="5f37f-247">The **Inventory value** value is *1,283.33* (= 1,000 + 375 – 458.33 + 458.33 – 91.67).</span></span>
    - <span data-ttu-id="5f37f-248">O valor de **Custo unitário médio** é *91,67*.</span><span class="sxs-lookup"><span data-stu-id="5f37f-248">The **Average unit cost** value is *91.67*.</span></span>
    - <span data-ttu-id="5f37f-249">O valor de **Valor disponível** e o valor de **Valor** em cada bucket de período são calculados usando-se o valor de **Custo unitário médio**.</span><span class="sxs-lookup"><span data-stu-id="5f37f-249">The **On-hand value** value and the **Amount** value in each period bucket are calculated by using the **Average unit cost** value.</span></span>

- <span data-ttu-id="5f37f-250">O relatório determina a quantidade disponível para cada bucket de período resumindo a quantidade de estoque total recebida para cada bucket de período.</span><span class="sxs-lookup"><span data-stu-id="5f37f-250">The report determines the on-hand quantity for each period bucket by summarizing the total received inventory quantity for each period bucket.</span></span> <span data-ttu-id="5f37f-251">Em seguida, ele aplica o princípio PEPS (primeiro a entrar, primeiro a sair) para deduzir a quantidade emitida total, independentemente do modelo de estoque usado pelos itens.</span><span class="sxs-lookup"><span data-stu-id="5f37f-251">It then applies the first in, first out (FIFO) principle to deduct the total issued quantity, regardless of the inventory model that the items use.</span></span>

<span data-ttu-id="5f37f-252">Se você executar o mesmo relatório novamente, mas, desta vez, definir os campos **Site** e **Depósito** como *Exibir*, o novo relatório será semelhante ao exemplo a seguir.</span><span class="sxs-lookup"><span data-stu-id="5f37f-252">If you run the same report again, but this time you set both the **Site** and **Warehouse** fields to *View*, the new report will resemble the following example.</span></span>

<table>
<thead>
<tr>
    <th rowspan="2"><span data-ttu-id="5f37f-253">Nº de itens</span><span class="sxs-lookup"><span data-stu-id="5f37f-253">Item number</span></span></th>
    <th rowspan="2"><span data-ttu-id="5f37f-254">Site</span><span class="sxs-lookup"><span data-stu-id="5f37f-254">Site</span></span></th>
    <th rowspan="2"><span data-ttu-id="5f37f-255">Depósito</span><span class="sxs-lookup"><span data-stu-id="5f37f-255">Warehouse</span></span></th>
    <th rowspan="2"><span data-ttu-id="5f37f-256">Quantidade disponível</span><span class="sxs-lookup"><span data-stu-id="5f37f-256">On-hand quantity</span></span></th>
    <th rowspan="2"><span data-ttu-id="5f37f-257">Valor disponível</span><span class="sxs-lookup"><span data-stu-id="5f37f-257">On-hand value</span></span></th>
    <th rowspan="2"><span data-ttu-id="5f37f-258">Quantidade do valor do estoque</span><span class="sxs-lookup"><span data-stu-id="5f37f-258">Inventory value quantity</span></span></th>
    <th rowspan="2"><span data-ttu-id="5f37f-259">Valor do estoque</span><span class="sxs-lookup"><span data-stu-id="5f37f-259">Inventory value</span></span></th>
    <th rowspan="2"><span data-ttu-id="5f37f-260">Custo unitário médio</span><span class="sxs-lookup"><span data-stu-id="5f37f-260">Average unit cost</span></span></th>
    <th colspan="2"><span data-ttu-id="5f37f-261">8/5/2020 - 1/5/2020</span><span class="sxs-lookup"><span data-stu-id="5f37f-261">5/8/2020 - 5/1/2020</span></span></th>
    <th colspan="2"><span data-ttu-id="5f37f-262">30/4/2020 - 1/4/2020</span><span class="sxs-lookup"><span data-stu-id="5f37f-262">4/30/2020 - 4/1/2020</span></span></th>
    <th colspan="2"><span data-ttu-id="5f37f-263">31/3/2020 - 1/3/2020</span><span class="sxs-lookup"><span data-stu-id="5f37f-263">3/31/2020 - 3/1/2020</span></span></th>
</tr>
<tr>
    <th><span data-ttu-id="5f37f-264">P1:Quantidade</span><span class="sxs-lookup"><span data-stu-id="5f37f-264">P1:Quantity</span></span></th>
    <th><span data-ttu-id="5f37f-265">P1:Valor</span><span class="sxs-lookup"><span data-stu-id="5f37f-265">P1:Amount</span></span></th>
    <th><span data-ttu-id="5f37f-266">P2:Quantidade</span><span class="sxs-lookup"><span data-stu-id="5f37f-266">P2:Quantity</span></span></th>
    <th><span data-ttu-id="5f37f-267">P2:Valor</span><span class="sxs-lookup"><span data-stu-id="5f37f-267">P2:Amount</span></span></th>
    <th><span data-ttu-id="5f37f-268">P3:Quantidade</span><span class="sxs-lookup"><span data-stu-id="5f37f-268">P3:Quantity</span></span></th>
    <th><span data-ttu-id="5f37f-269">P3:Valor</span><span class="sxs-lookup"><span data-stu-id="5f37f-269">P3:Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
    <td><span data-ttu-id="5f37f-270">1000</span><span class="sxs-lookup"><span data-stu-id="5f37f-270">1000</span></span></td>
    <td><span data-ttu-id="5f37f-271">1</span><span class="sxs-lookup"><span data-stu-id="5f37f-271">1</span></span></td>
    <td><span data-ttu-id="5f37f-272">11</span><span class="sxs-lookup"><span data-stu-id="5f37f-272">11</span></span></td>
    <td><span data-ttu-id="5f37f-273">10</span><span class="sxs-lookup"><span data-stu-id="5f37f-273">10</span></span></td>
    <td><span data-ttu-id="5f37f-274">916.67</span><span class="sxs-lookup"><span data-stu-id="5f37f-274">916.67</span></span></td>
    <td><span data-ttu-id="5f37f-275">14</span><span class="sxs-lookup"><span data-stu-id="5f37f-275">14</span></span></td>
    <td><span data-ttu-id="5f37f-276">1,283.33</span><span class="sxs-lookup"><span data-stu-id="5f37f-276">1,283.33</span></span></td>
    <td><span data-ttu-id="5f37f-277">91.67</span><span class="sxs-lookup"><span data-stu-id="5f37f-277">91.67</span></span></td>
    <td></td>
    <td></td>
    <td><span data-ttu-id="5f37f-278">5.00</span><span class="sxs-lookup"><span data-stu-id="5f37f-278">5.00</span></span></td>
    <td><span data-ttu-id="5f37f-279">458.33</span><span class="sxs-lookup"><span data-stu-id="5f37f-279">458.33</span></span></td>
    <td><span data-ttu-id="5f37f-280">5.00</span><span class="sxs-lookup"><span data-stu-id="5f37f-280">5.00</span></span></td>
    <td><span data-ttu-id="5f37f-281">458.33</span><span class="sxs-lookup"><span data-stu-id="5f37f-281">458.33</span></span></td>
</tr>
<tr>
    <td><span data-ttu-id="5f37f-282">1000</span><span class="sxs-lookup"><span data-stu-id="5f37f-282">1000</span></span></td>
    <td><span data-ttu-id="5f37f-283">1</span><span class="sxs-lookup"><span data-stu-id="5f37f-283">1</span></span></td>
    <td><span data-ttu-id="5f37f-284">12</span><span class="sxs-lookup"><span data-stu-id="5f37f-284">12</span></span></td>
    <td><span data-ttu-id="5f37f-285">4</span><span class="sxs-lookup"><span data-stu-id="5f37f-285">4</span></span></td>
    <td><span data-ttu-id="5f37f-286">366.67</span><span class="sxs-lookup"><span data-stu-id="5f37f-286">366.67</span></span></td>
    <td><span data-ttu-id="5f37f-287">14</span><span class="sxs-lookup"><span data-stu-id="5f37f-287">14</span></span></td>
    <td><span data-ttu-id="5f37f-288">1,283.33</span><span class="sxs-lookup"><span data-stu-id="5f37f-288">1,283.33</span></span></td>
    <td><span data-ttu-id="5f37f-289">91.67</span><span class="sxs-lookup"><span data-stu-id="5f37f-289">91.67</span></span></td>
    <td><span data-ttu-id="5f37f-290">4.00</span><span class="sxs-lookup"><span data-stu-id="5f37f-290">4.00</span></span></td>
    <td><span data-ttu-id="5f37f-291">366.67</span><span class="sxs-lookup"><span data-stu-id="5f37f-291">366.67</span></span></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
</tr>
<tr>
    <td><span data-ttu-id="5f37f-292">1000</span><span class="sxs-lookup"><span data-stu-id="5f37f-292">1000</span></span></td>
    <td><span data-ttu-id="5f37f-293">2</span><span class="sxs-lookup"><span data-stu-id="5f37f-293">2</span></span></td>
    <td></td>
    <td><span data-ttu-id="5f37f-294">10</span><span class="sxs-lookup"><span data-stu-id="5f37f-294">10</span></span></td>
    <td><span data-ttu-id="5f37f-295">2,000.00</span><span class="sxs-lookup"><span data-stu-id="5f37f-295">2,000.00</span></span></td>
    <td><span data-ttu-id="5f37f-296">10</span><span class="sxs-lookup"><span data-stu-id="5f37f-296">10</span></span></td>
    <td><span data-ttu-id="5f37f-297">2,000.00</span><span class="sxs-lookup"><span data-stu-id="5f37f-297">2,000.00</span></span></td>
    <td><span data-ttu-id="5f37f-298">200.00</span><span class="sxs-lookup"><span data-stu-id="5f37f-298">200.00</span></span></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td><span data-ttu-id="5f37f-299">10,00</span><span class="sxs-lookup"><span data-stu-id="5f37f-299">10.00</span></span></td>
    <td><span data-ttu-id="5f37f-300">2,000.00</span><span class="sxs-lookup"><span data-stu-id="5f37f-300">2,000.00</span></span></td>
</tr>
</tbody>
<tfoot>
<tr>
    <td><span data-ttu-id="5f37f-301"><strong>Totais de 1.000</strong></span><span class="sxs-lookup"><span data-stu-id="5f37f-301"><strong>1000 Totals</strong></span></span></td>
    <td></td>
    <td></td>
    <td><span data-ttu-id="5f37f-302"><strong>24.00</strong></span><span class="sxs-lookup"><span data-stu-id="5f37f-302"><strong>24.00</strong></span></span></td>
    <td><span data-ttu-id="5f37f-303"><strong>3,283.33</strong></span><span class="sxs-lookup"><span data-stu-id="5f37f-303"><strong>3,283.33</strong></span></span></td>
    <td></td>
    <td></td>
    <td></td>
    <td><span data-ttu-id="5f37f-304"><strong>4.00</strong></span><span class="sxs-lookup"><span data-stu-id="5f37f-304"><strong>4.00</strong></span></span></td>
    <td><span data-ttu-id="5f37f-305"><strong>366.67</strong></span><span class="sxs-lookup"><span data-stu-id="5f37f-305"><strong>366.67</strong></span></span></td>
    <td><span data-ttu-id="5f37f-306"><strong>5.00</strong></span><span class="sxs-lookup"><span data-stu-id="5f37f-306"><strong>5.00</strong></span></span></td>
    <td><span data-ttu-id="5f37f-307"><strong>458.33</strong></span><span class="sxs-lookup"><span data-stu-id="5f37f-307"><strong>458.33</strong></span></span></td>
    <td><span data-ttu-id="5f37f-308"><strong>15</strong></span><span class="sxs-lookup"><span data-stu-id="5f37f-308"><strong>15</strong></span></span></td>
    <td><span data-ttu-id="5f37f-309"><strong>2,458.33</strong></span><span class="sxs-lookup"><span data-stu-id="5f37f-309"><strong>2,458.33</strong></span></span></td>
</tr>
</tfoot>
</table>

<span data-ttu-id="5f37f-310">Desta vez, o site 1 é dividido em duas linhas, uma para o depósito 11 e outra para o depósito 12.</span><span class="sxs-lookup"><span data-stu-id="5f37f-310">This time, site 1 is split into two rows, one for warehouse 11 and one for warehouse 12.</span></span> <span data-ttu-id="5f37f-311">No entanto, os valores de **Quantidade de valor de estoque**, **Valor de estoque** e **Custo unitário médio** são iguais, já que **Depósito** não é uma dimensão de estoque financeira.</span><span class="sxs-lookup"><span data-stu-id="5f37f-311">However, the **Inventory value quantity**, **Inventory value**, and **Average unit cost** values are the same, because **Warehouse** isn't a financial inventory dimension.</span></span>

<span data-ttu-id="5f37f-312">Além disso, observe que a distribuição de quantidade do site 1 é diferente.</span><span class="sxs-lookup"><span data-stu-id="5f37f-312">Additionally, notice that the quantity distribution of site 1 is different.</span></span> <span data-ttu-id="5f37f-313">No primeiro relatório que você executou, o sistema ignorou a ordem de transferência ocorrida no mesmo site e deduziu a quantidade da fatura de venda do bucket de período **31/3/2020-1/3/2020** no site 1.</span><span class="sxs-lookup"><span data-stu-id="5f37f-313">In the first report that you ran, the system ignored the transfer order that occurred in the same site and deducted the quantity of the sales invoice from the **3/31/2020 - 3/1/2020** period bucket in site 1.</span></span> <span data-ttu-id="5f37f-314">No entanto, no novo relatório, o sistema deduz a quantidade da fatura de venda do bucket de período **8/5/2020-1/5/2020** no depósito 12.</span><span class="sxs-lookup"><span data-stu-id="5f37f-314">However, in the new report, the system deducts the quantity of the sales invoice from the **5/8/2020 - 5/1/2020** period bucket in warehouse 12.</span></span>

## <a name="effects-of-inventory-closing"></a><span data-ttu-id="5f37f-315">Efeitos do fechamento de estoque</span><span class="sxs-lookup"><span data-stu-id="5f37f-315">Effects of inventory closing</span></span>

<span data-ttu-id="5f37f-316">Se você executar o fechamento de estoque para maio e executar o relatório anterior novamente, mas definir o campo **A partir da data** como *31 de maio de 2020*, os seguintes resultados serão observados:</span><span class="sxs-lookup"><span data-stu-id="5f37f-316">If you run the inventory closing for May and then run the previous report again, but you set the **As of date** field to *May 31, 2020*, you will notice the following results:</span></span>

- <span data-ttu-id="5f37f-317">Os valores **Valor de estoque** e **Custo unitário médio** são atualizados.</span><span class="sxs-lookup"><span data-stu-id="5f37f-317">The **Inventory value** and **Average unit cost** values are updated.</span></span>
- <span data-ttu-id="5f37f-318">O valor de **Valor disponível** e todos os valores de **Valor** em cada bucket de período são atualizados adequadamente.</span><span class="sxs-lookup"><span data-stu-id="5f37f-318">The **On-hand value** value and all the **Amount** values in every period bucket are updated accordingly.</span></span>

<span data-ttu-id="5f37f-319">O novo relatório se assemelhará ao seguinte exemplo.</span><span class="sxs-lookup"><span data-stu-id="5f37f-319">The new report will resemble the following example.</span></span>

<table>
<thead>
<tr>
    <th rowspan="2"><span data-ttu-id="5f37f-320">Nº de itens</span><span class="sxs-lookup"><span data-stu-id="5f37f-320">Item number</span></span></th>
    <th rowspan="2"><span data-ttu-id="5f37f-321">Site</span><span class="sxs-lookup"><span data-stu-id="5f37f-321">Site</span></span></th>
    <th rowspan="2"><span data-ttu-id="5f37f-322">Depósito</span><span class="sxs-lookup"><span data-stu-id="5f37f-322">Warehouse</span></span></th>
    <th rowspan="2"><span data-ttu-id="5f37f-323">Quantidade disponível</span><span class="sxs-lookup"><span data-stu-id="5f37f-323">On-hand quantity</span></span></th>
    <th rowspan="2"><span data-ttu-id="5f37f-324">Valor disponível</span><span class="sxs-lookup"><span data-stu-id="5f37f-324">On-hand value</span></span></th>
    <th rowspan="2"><span data-ttu-id="5f37f-325">Quantidade do valor do estoque</span><span class="sxs-lookup"><span data-stu-id="5f37f-325">Inventory value quantity</span></span></th>
    <th rowspan="2"><span data-ttu-id="5f37f-326">Valor do estoque</span><span class="sxs-lookup"><span data-stu-id="5f37f-326">Inventory value</span></span></th>
    <th rowspan="2"><span data-ttu-id="5f37f-327">Custo unitário médio</span><span class="sxs-lookup"><span data-stu-id="5f37f-327">Average unit cost</span></span></th>
    <th colspan="2"><span data-ttu-id="5f37f-328">31/5/2020 - 1/5/2020</span><span class="sxs-lookup"><span data-stu-id="5f37f-328">5/31/2020 - 5/1/2020</span></span></th>
    <th colspan="2"><span data-ttu-id="5f37f-329">30/4/2020 - 1/4/2020</span><span class="sxs-lookup"><span data-stu-id="5f37f-329">4/30/2020 - 4/1/2020</span></span></th>
    <th colspan="2"><span data-ttu-id="5f37f-330">31/3/2020 - 1/3/2020</span><span class="sxs-lookup"><span data-stu-id="5f37f-330">3/31/2020 - 3/1/2020</span></span></th>
</tr>
<tr>
    <th><span data-ttu-id="5f37f-331">P1:Quantidade</span><span class="sxs-lookup"><span data-stu-id="5f37f-331">P1:Quantity</span></span></th>
    <th><span data-ttu-id="5f37f-332">P1:Valor</span><span class="sxs-lookup"><span data-stu-id="5f37f-332">P1:Amount</span></span></th>
    <th><span data-ttu-id="5f37f-333">P2:Quantidade</span><span class="sxs-lookup"><span data-stu-id="5f37f-333">P2:Quantity</span></span></th>
    <th><span data-ttu-id="5f37f-334">P2:Valor</span><span class="sxs-lookup"><span data-stu-id="5f37f-334">P2:Amount</span></span></th>
    <th><span data-ttu-id="5f37f-335">P3:Quantidade</span><span class="sxs-lookup"><span data-stu-id="5f37f-335">P3:Quantity</span></span></th>
    <th><span data-ttu-id="5f37f-336">P3:Valor</span><span class="sxs-lookup"><span data-stu-id="5f37f-336">P3:Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
    <td><span data-ttu-id="5f37f-337">1000</span><span class="sxs-lookup"><span data-stu-id="5f37f-337">1000</span></span></td>
    <td><span data-ttu-id="5f37f-338">1</span><span class="sxs-lookup"><span data-stu-id="5f37f-338">1</span></span></td>
    <td><span data-ttu-id="5f37f-339">11</span><span class="sxs-lookup"><span data-stu-id="5f37f-339">11</span></span></td>
    <td><span data-ttu-id="5f37f-340">10</span><span class="sxs-lookup"><span data-stu-id="5f37f-340">10</span></span></td>
    <td><span data-ttu-id="5f37f-341">910.70</span><span class="sxs-lookup"><span data-stu-id="5f37f-341">910.70</span></span></td>
    <td><span data-ttu-id="5f37f-342">14</span><span class="sxs-lookup"><span data-stu-id="5f37f-342">14</span></span></td>
    <td><span data-ttu-id="5f37f-343">1,275.00</span><span class="sxs-lookup"><span data-stu-id="5f37f-343">1,275.00</span></span></td>
    <td><span data-ttu-id="5f37f-344">91.07</span><span class="sxs-lookup"><span data-stu-id="5f37f-344">91.07</span></span></td>
    <td><span data-ttu-id="5f37f-345">0,00</span><span class="sxs-lookup"><span data-stu-id="5f37f-345">0.00</span></span></td>
    <td></td>
    <td><span data-ttu-id="5f37f-346">5.00</span><span class="sxs-lookup"><span data-stu-id="5f37f-346">5.00</span></span></td>
    <td><span data-ttu-id="5f37f-347">455.36</span><span class="sxs-lookup"><span data-stu-id="5f37f-347">455.36</span></span></td>
    <td><span data-ttu-id="5f37f-348">5.00</span><span class="sxs-lookup"><span data-stu-id="5f37f-348">5.00</span></span></td>
    <td><span data-ttu-id="5f37f-349">455.36</span><span class="sxs-lookup"><span data-stu-id="5f37f-349">455.36</span></span></td>
</tr>
<tr>
    <td><span data-ttu-id="5f37f-350">1000</span><span class="sxs-lookup"><span data-stu-id="5f37f-350">1000</span></span></td>
    <td><span data-ttu-id="5f37f-351">1</span><span class="sxs-lookup"><span data-stu-id="5f37f-351">1</span></span></td>
    <td><span data-ttu-id="5f37f-352">12</span><span class="sxs-lookup"><span data-stu-id="5f37f-352">12</span></span></td>
    <td><span data-ttu-id="5f37f-353">4</span><span class="sxs-lookup"><span data-stu-id="5f37f-353">4</span></span></td>
    <td><span data-ttu-id="5f37f-354">364.29</span><span class="sxs-lookup"><span data-stu-id="5f37f-354">364.29</span></span></td>
    <td><span data-ttu-id="5f37f-355">14</span><span class="sxs-lookup"><span data-stu-id="5f37f-355">14</span></span></td>
    <td><span data-ttu-id="5f37f-356">1,275.00</span><span class="sxs-lookup"><span data-stu-id="5f37f-356">1,275.00</span></span></td>
    <td><span data-ttu-id="5f37f-357">91.07</span><span class="sxs-lookup"><span data-stu-id="5f37f-357">91.07</span></span></td>
    <td><span data-ttu-id="5f37f-358">4.00</span><span class="sxs-lookup"><span data-stu-id="5f37f-358">4.00</span></span></td>
    <td><span data-ttu-id="5f37f-359">364.29</span><span class="sxs-lookup"><span data-stu-id="5f37f-359">364.29</span></span></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
</tr>
<tr>
    <td><span data-ttu-id="5f37f-360">1000</span><span class="sxs-lookup"><span data-stu-id="5f37f-360">1000</span></span></td>
    <td><span data-ttu-id="5f37f-361">2</span><span class="sxs-lookup"><span data-stu-id="5f37f-361">2</span></span></td>
    <td></td>
    <td><span data-ttu-id="5f37f-362">10</span><span class="sxs-lookup"><span data-stu-id="5f37f-362">10</span></span></td>
    <td><span data-ttu-id="5f37f-363">2,000.00</span><span class="sxs-lookup"><span data-stu-id="5f37f-363">2,000.00</span></span></td>
    <td><span data-ttu-id="5f37f-364">10</span><span class="sxs-lookup"><span data-stu-id="5f37f-364">10</span></span></td>
    <td><span data-ttu-id="5f37f-365">2,000.00</span><span class="sxs-lookup"><span data-stu-id="5f37f-365">2,000.00</span></span></td>
    <td><span data-ttu-id="5f37f-366">200.00</span><span class="sxs-lookup"><span data-stu-id="5f37f-366">200.00</span></span></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td><span data-ttu-id="5f37f-367">10,00</span><span class="sxs-lookup"><span data-stu-id="5f37f-367">10.00</span></span></td>
    <td><span data-ttu-id="5f37f-368">2,000.00</span><span class="sxs-lookup"><span data-stu-id="5f37f-368">2,000.00</span></span></td>
</tr>
</tbody>
<tfoot>
<tr>
    <td><span data-ttu-id="5f37f-369"><strong>Totais de 1.000</strong></span><span class="sxs-lookup"><span data-stu-id="5f37f-369"><strong>1000 Totals</strong></span></span></td>
    <td></td>
    <td></td>
    <td><span data-ttu-id="5f37f-370"><strong>24.00</strong></span><span class="sxs-lookup"><span data-stu-id="5f37f-370"><strong>24.00</strong></span></span></td>
    <td><span data-ttu-id="5f37f-371"><strong>3,275.00</strong></span><span class="sxs-lookup"><span data-stu-id="5f37f-371"><strong>3,275.00</strong></span></span></td>
    <td></td>
    <td></td>
    <td></td>
    <td><span data-ttu-id="5f37f-372"><strong>4.00</strong></span><span class="sxs-lookup"><span data-stu-id="5f37f-372"><strong>4.00</strong></span></span></td>
    <td><span data-ttu-id="5f37f-373"><strong>364.29</strong></span><span class="sxs-lookup"><span data-stu-id="5f37f-373"><strong>364.29</strong></span></span></td>
    <td><span data-ttu-id="5f37f-374"><strong>5.00</strong></span><span class="sxs-lookup"><span data-stu-id="5f37f-374"><strong>5.00</strong></span></span></td>
    <td><span data-ttu-id="5f37f-375"><strong>455.36</strong></span><span class="sxs-lookup"><span data-stu-id="5f37f-375"><strong>455.36</strong></span></span></td>
    <td><span data-ttu-id="5f37f-376"><strong>15</strong></span><span class="sxs-lookup"><span data-stu-id="5f37f-376"><strong>15</strong></span></span></td>
    <td><span data-ttu-id="5f37f-377"><strong>2,455.36</strong></span><span class="sxs-lookup"><span data-stu-id="5f37f-377"><strong>2,455.36</strong></span></span></td>
</tr>
</tfoot>
</table>
