---
title: "Conteúdo do Power BI de análise de gasto em compras"
description: "Este tópico descreve o que está incluído no conteúdo do Power BI de análise de gastos da compra. Ele explica como acessar os relatórios incluídos no conteúdo, além de fornecer informações sobre o modelo de dados e as entidades usadas para criar o conteúdo."
author: FrankDahl
manager: AnnBe
ms.date: 12/18/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
ms.search.form: PurchaseSpendAnalysisPowerBI
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 265434
ms.assetid: 3cd9dfce-2687-4303-bc78-349e7cb5ea75
ms.search.region: global
ms.author: fdahl
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 821d8927211d7ac3e479848c7e7bef9f650d4340
ms.openlocfilehash: 069c4dc21959ab603ba6ca3da0ac68ef20325265
ms.contentlocale: pt-br
ms.lasthandoff: 08/13/2018

---

# <a name="purchase-spend-analysis-power-bi-content"></a><span data-ttu-id="555e3-104">Conteúdo do Power BI de análise de gasto em compras</span><span class="sxs-lookup"><span data-stu-id="555e3-104">Purchase spend analysis Power BI content</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="555e3-105">Este tópico descreve o que está incluído no conteúdo do Microsoft Power BI de **Análise de gastos da compra**.</span><span class="sxs-lookup"><span data-stu-id="555e3-105">This topic describes what is included in the **Purchase spend analysis** Microsoft Power BI content.</span></span> <span data-ttu-id="555e3-106">Ele explica como acessar os relatórios do Power BI, além de fornecer informações sobre o modelo de dados e as entidades usados para criar o pacote de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="555e3-106">It explains how to access the Power BI reports, and provides information about the data model and entities that are used to build the content.</span></span>

## <a name="overview"></a><span data-ttu-id="555e3-107">Visão Geral</span><span class="sxs-lookup"><span data-stu-id="555e3-107">Overview</span></span>

<span data-ttu-id="555e3-108">O conteúdo do Power BI de **Análise de gastos da compra** foi desenvolvido para ajudar os gerentes de compras e os gerentes responsáveis por orçamentos a ficar de olho nos gastos de compra.</span><span class="sxs-lookup"><span data-stu-id="555e3-108">The **Purchase spend analysis** Power BI content was designed to help purchasing managers and managers who are responsible for budgets keep an eye on purchase spending.</span></span> <span data-ttu-id="555e3-109">Os gerentes podem analisar os gastos de compra das seguintes maneiras:</span><span class="sxs-lookup"><span data-stu-id="555e3-109">Managers can analyze purchase spending in the following ways:</span></span>

- <span data-ttu-id="555e3-110">Compra de um ano atrás até agora (por grupo de fornecedor e fornecedores individuais, categoria de compras e produtos individuais e local de fornecedor)</span><span class="sxs-lookup"><span data-stu-id="555e3-110">Year-to-date purchase (by vendor group and individual vendors, procurement category and individual products, and vendor location)</span></span>
- <span data-ttu-id="555e3-111">Alteração de compra de um ano atrás até agora (por grupo de fornecedor e categoria de compras)</span><span class="sxs-lookup"><span data-stu-id="555e3-111">Year-over-year purchase change (by vendor group and procurement category)</span></span>

<span data-ttu-id="555e3-112">O conteúdo usa dados transacionais de compra e fornece uma visão agregada dos números de compra da empresa e uma repartição dos gastos de compra por fornecedor e produto.</span><span class="sxs-lookup"><span data-stu-id="555e3-112">The content uses purchase transactional data, and provides both an aggregate view of the company-wide purchase figures and a breakdown of purchase spending by vendor and product.</span></span> <span data-ttu-id="555e3-113">Os relatórios destacam as alterações no gasto em compras ao longo do tempo.</span><span class="sxs-lookup"><span data-stu-id="555e3-113">Reports highlight changes in purchase spending over time.</span></span> <span data-ttu-id="555e3-114">Portanto, os relatórios podem ser usados para alertar gerentes sobre tendências positivas e negativas de gastos para fornecedores individuais e produtos.</span><span class="sxs-lookup"><span data-stu-id="555e3-114">Therefore, the reports can be used to alert managers about positive and negative spending trends for individual vendors and products.</span></span> <span data-ttu-id="555e3-115">Além disso, gráficos mostram gasto em compras para categorias de compras diferentes e grupos de fornecedores.</span><span class="sxs-lookup"><span data-stu-id="555e3-115">Additionally, charts show purchase spending for different procurement categories and vendor groups.</span></span> <span data-ttu-id="555e3-116">Portanto, a categoria e os gerentes regionais podem usar os gráficos para ajudar a identificar mudanças nos comportamentos de gastos.</span><span class="sxs-lookup"><span data-stu-id="555e3-116">Therefore, category and regional managers can use the charts to help identify changes in spending behavior.</span></span>

## <a name="accessing-the-power-bi-content"></a><span data-ttu-id="555e3-117">Acessando o conteúdo do Power BI</span><span class="sxs-lookup"><span data-stu-id="555e3-117">Accessing the Power BI content</span></span>
<span data-ttu-id="555e3-118">O conteúdo do Power BI de **Análise de gasto em compras** é exibido na página **Análise de compra e de gastos** (**Compras** \> **Consultas e relatórios** \> **Teste de desempenho de compra** \> **Análise de compra e de gastos**).</span><span class="sxs-lookup"><span data-stu-id="555e3-118">The **Purchase spend analysis** Power BI content is shown on the **Purchase and spend analysis** page (**Procurement and sourcing** \> **Inquiries and reports** \> **Purchase performance analysis** \> **Purchase and spend analysis**).</span></span>

## <a name="metrics-that-are-included-in-the-power-bi-content"></a><span data-ttu-id="555e3-119">Métricas incluídas no conteúdo do Power BI</span><span class="sxs-lookup"><span data-stu-id="555e3-119">Metrics that are included in the Power BI content</span></span>
<span data-ttu-id="555e3-120">O conteúdo de Power BI de **Análise de gastos da compra** inclui um relatório que consiste em um grupo de métricas.</span><span class="sxs-lookup"><span data-stu-id="555e3-120">The **Purchase spend analysis** Power BI content includes a report that consists of a set of metrics.</span></span> <span data-ttu-id="555e3-121">Estas métricas são visualizadas como gráficos, blocos e tabelas.</span><span class="sxs-lookup"><span data-stu-id="555e3-121">These metrics are visualized as charts, tiles, and tables.</span></span> <span data-ttu-id="555e3-122">A tabela a seguir fornece uma visão geral das visualizações.</span><span class="sxs-lookup"><span data-stu-id="555e3-122">The following table provides an overview of the visualizations.</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="555e3-123">Página de relatório</span><span class="sxs-lookup"><span data-stu-id="555e3-123">Report page</span></span></th>
<th><span data-ttu-id="555e3-124">Gráficos</span><span class="sxs-lookup"><span data-stu-id="555e3-124">Charts</span></span></th>
<th><span data-ttu-id="555e3-125">Blocos</span><span class="sxs-lookup"><span data-stu-id="555e3-125">Tiles</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="555e3-126">Venda por fornecedor</span><span class="sxs-lookup"><span data-stu-id="555e3-126">Purchase by vendor</span></span></td>
<td><ul>
<li><span data-ttu-id="555e3-127">10 principais fornecedores por compra (gráfico de barra empilhada)</span><span class="sxs-lookup"><span data-stu-id="555e3-127">Top 10 vendors by purchase (stacked bar chart)</span></span></li>
<li><span data-ttu-id="555e3-128">Compra total por grupo de fornecedor/país/nome (gráfico de pizza)</span><span class="sxs-lookup"><span data-stu-id="555e3-128">Total purchase by vendor group / country / name (pie chart)</span></span></li>
<li><span data-ttu-id="555e3-129">Compra por grupo de fornecedor/país/nome (gráfico de coluna)</span><span class="sxs-lookup"><span data-stu-id="555e3-129">Purchase by vendor group / country / name (column chart)</span></span></li>
<li><span data-ttu-id="555e3-130">Compra média por grupo de fornecedor/país/nome (gráfico de coluna)</span><span class="sxs-lookup"><span data-stu-id="555e3-130">Average purchase by vendor group / country / name (column chart)</span></span></li>
</ul></td>
<td><ul>
<li><span data-ttu-id="555e3-131">Total da Compra</span><span class="sxs-lookup"><span data-stu-id="555e3-131">Total purchase</span></span></li>
<li><span data-ttu-id="555e3-132">Crescimento de compra de YOY</span><span class="sxs-lookup"><span data-stu-id="555e3-132">YOY purchase growth</span></span></li>
<li><span data-ttu-id="555e3-133">Número total de fornecedores</span><span class="sxs-lookup"><span data-stu-id="555e3-133">Total # vendors</span></span></li>
<li><span data-ttu-id="555e3-134">Número total de fornecedores ativos</span><span class="sxs-lookup"><span data-stu-id="555e3-134">Total # of active vendors</span></span></li>
</ul></td>
</tr>
<tr>
<td><span data-ttu-id="555e3-135">Compra por produto</span><span class="sxs-lookup"><span data-stu-id="555e3-135">Purchase by product</span></span></td>
<td><ul>
<li><span data-ttu-id="555e3-136">Compra por categoria de itens/nome do produto (gráfico de coluna)</span><span class="sxs-lookup"><span data-stu-id="555e3-136">Purchase by procurement category / product name (column chart)</span></span></li>
<li><span data-ttu-id="555e3-137">Compra total por categoria de itens/nome do produto (gráfico de pizza)</span><span class="sxs-lookup"><span data-stu-id="555e3-137">Total purchase by procurement category / product name (pie chart)</span></span></li>
<li><span data-ttu-id="555e3-138">10 principais produtos por compra (gráfico de barra empilhada)</span><span class="sxs-lookup"><span data-stu-id="555e3-138">Top 10 products by purchase (stacked bar chart)</span></span></li>
</ul></td>
<td><ul>
<li><span data-ttu-id="555e3-139">Número total de produtos</span><span class="sxs-lookup"><span data-stu-id="555e3-139">Total # of products</span></span></li>
<li><span data-ttu-id="555e3-140">Porcentagem de produtos ativos total do número total de produtos</span><span class="sxs-lookup"><span data-stu-id="555e3-140">Total active products percentage of total # of products</span></span></li>
<li><span data-ttu-id="555e3-141">Número da contabilidade de produtos para compra de 80%</span><span class="sxs-lookup"><span data-stu-id="555e3-141">Number of products accounting for 80% purchase</span></span></li>
</ul></td>
</tr>
<tr>
<td><span data-ttu-id="555e3-142">Compra por período\*</span><span class="sxs-lookup"><span data-stu-id="555e3-142">Purchase by period\*</span></span></td>
<td><ul>
<li><span data-ttu-id="555e3-143">Compra por mês/dia (gráfico de coluna)</span><span class="sxs-lookup"><span data-stu-id="555e3-143">Purchase by month / day (column chart)</span></span></li>
<li><span data-ttu-id="555e3-144">Variação de YOY de compra cumulativa (gráfico de cascata)</span><span class="sxs-lookup"><span data-stu-id="555e3-144">Cumulative purchase YOY variance (waterfall chart)</span></span></li>
<li><span data-ttu-id="555e3-145">Crescimento de YOY total da compra (gráfico de coluna)</span><span class="sxs-lookup"><span data-stu-id="555e3-145">Total purchase YOY growth (column chart)</span></span></li>
<li><span data-ttu-id="555e3-146">Demonstrativo de compras (matriz)</span><span class="sxs-lookup"><span data-stu-id="555e3-146">Procurement statement (matrix)</span></span></li>
</ul></td>
<td><ul>
<li><span data-ttu-id="555e3-147">Crescimento de compra de YOY</span><span class="sxs-lookup"><span data-stu-id="555e3-147">YOY purchase growth</span></span></li>
<li><span data-ttu-id="555e3-148">Porcentagem de crescimento de compra de YOY</span><span class="sxs-lookup"><span data-stu-id="555e3-148">YOY purchase growth %</span></span></li>
</ul></td>
</tr>
<tr>
<td><span data-ttu-id="555e3-149">Compra por local de fornecedor</span><span class="sxs-lookup"><span data-stu-id="555e3-149">Purchase by vendor location</span></span></td>
<td><ul>
<li><span data-ttu-id="555e3-150">Compra por cidade</span><span class="sxs-lookup"><span data-stu-id="555e3-150">Purchase by city</span></span></li>
<li><span data-ttu-id="555e3-151">Porcentagem de crescimento de YOY de compra</span><span class="sxs-lookup"><span data-stu-id="555e3-151">Purchase YOY growth %</span></span></li>
<li><span data-ttu-id="555e3-152">Compra por país</span><span class="sxs-lookup"><span data-stu-id="555e3-152">Purchase by country</span></span></li>
</ul></td>
<td></td>
</tr>
<tr>
<td><span data-ttu-id="555e3-153">Análise de gastos de compra por hora</span><span class="sxs-lookup"><span data-stu-id="555e3-153">Purchase spend analysis by time</span></span></td>
<td><ul>
<li><span data-ttu-id="555e3-154">Ano atual de compra em mês/dia (gráfico de linha)</span><span class="sxs-lookup"><span data-stu-id="555e3-154">Purchase current year by month / day (line chart)</span></span></li>
<li><span data-ttu-id="555e3-155">Compra atual e do último ano (gráfico de linha e coluna)</span><span class="sxs-lookup"><span data-stu-id="555e3-155">Purchase current and last year (line and column chart)</span></span></li>
</ul></td>
<td></td>
</tr>
<tr>
<td><span data-ttu-id="555e3-156">Análise de gastos de compra por fornecedor</span><span class="sxs-lookup"><span data-stu-id="555e3-156">Purchase spend analysis by vendor</span></span></td>
<td><ul>
<li><span data-ttu-id="555e3-157">10 principais porcentagens de compra de fornecedor (funil)</span><span class="sxs-lookup"><span data-stu-id="555e3-157">Top 10 vendor purchase % of purchase (funnel)</span></span></li>
<li><span data-ttu-id="555e3-158">10 principais fornecedores com gasto elevado de YOY</span><span class="sxs-lookup"><span data-stu-id="555e3-158">Top 10 vendors with increased spending YOY</span></span></li>
<li><span data-ttu-id="555e3-159">10 principais fornecedores com gasto diminuído de YOY</span><span class="sxs-lookup"><span data-stu-id="555e3-159">Top 10 vendors with decreased spending YOY</span></span></li>
</ul></td>
<td></td>
</tr>
</tbody>
</table>

<span data-ttu-id="555e3-160">\* Compras este ano e no ano passado e crescimento por categoria de compra</span><span class="sxs-lookup"><span data-stu-id="555e3-160">\* Purchase this year and last year, and growth by procurement category</span></span>

## <a name="data-model-and-entities"></a><span data-ttu-id="555e3-161">Modelo de dados e entidades</span><span class="sxs-lookup"><span data-stu-id="555e3-161">Data model and entities</span></span>
<span data-ttu-id="555e3-162">Os seguintes dados são usados para preencher as páginas de relatório no conteúdo do Power BI **Análise de gastos da compra**.</span><span class="sxs-lookup"><span data-stu-id="555e3-162">The following data is used to fill the report pages in the **Purchase spend analysis** Power BI content.</span></span> <span data-ttu-id="555e3-163">Esses dados são representadas como medições agregadas que foram preparadas no Repositório de entidades.</span><span class="sxs-lookup"><span data-stu-id="555e3-163">This data is represented as aggregate measurements that are staged in the Entity store.</span></span> <span data-ttu-id="555e3-164">O Repositório de entidades é um banco de dados do Microsoft SQL Server otimizado para análise.</span><span class="sxs-lookup"><span data-stu-id="555e3-164">The Entity store is a Microsoft SQL Server database that is optimized for analytics.</span></span> <span data-ttu-id="555e3-165">Para obter mais informações, consulte [Visão geral da integração do Power BI com a loja Entidade](power-bi-integration-entity-store.md).</span><span class="sxs-lookup"><span data-stu-id="555e3-165">For more information, see [Overview of Power BI integration with Entity store](power-bi-integration-entity-store.md).</span></span>

<span data-ttu-id="555e3-166">As medidas agregadas neste conteúdo são o subconjunto de medidas agregadas que estavam disponíveis no Cubo de Compras no Microsoft Dynamics AX 2012 e no Microsoft Dynamics AX 2012 R3.</span><span class="sxs-lookup"><span data-stu-id="555e3-166">The aggregate measurements in this content are the subset of aggregate measurements that were available in the Purchase Cube in Microsoft Dynamics AX 2012 and Microsoft Dynamics AX 2012 R3.</span></span> <span data-ttu-id="555e3-167">Para preparar as medidas agregadas do cubo na loja Entidade, você deve torná-las implementáveis.</span><span class="sxs-lookup"><span data-stu-id="555e3-167">To stage the cube's aggregate measurements in the Entity store, you must make them deployable.</span></span> <span data-ttu-id="555e3-168">Para obter mais informações, consulte o procedimento sobre como preparar medidas agregadas na loja Entidade em [Visão geral da integração do Power BI com a loja Entidade](power-bi-integration-entity-store.md).</span><span class="sxs-lookup"><span data-stu-id="555e3-168">For more information, see the procedure for staging aggregate measurements in the Entity store in [Overview of Power BI integration with Entity store](power-bi-integration-entity-store.md).</span></span> <span data-ttu-id="555e3-169">As principais medidas agregadas a seguir estão disponíveis diretamente nas entidade de linhas de fatura e são usadas como base do conteúdo.</span><span class="sxs-lookup"><span data-stu-id="555e3-169">The following key aggregate measurements are available directly from the Invoice lines entity and are used as the basis of the content.</span></span>

| <span data-ttu-id="555e3-170">Entidade</span><span class="sxs-lookup"><span data-stu-id="555e3-170">Entity</span></span>        | <span data-ttu-id="555e3-171">Principais medidas agregadas</span><span class="sxs-lookup"><span data-stu-id="555e3-171">Key aggregate measurements</span></span> | <span data-ttu-id="555e3-172">Fonte de dados</span><span class="sxs-lookup"><span data-stu-id="555e3-172">Data source</span></span>                                 | <span data-ttu-id="555e3-173">Campo</span><span class="sxs-lookup"><span data-stu-id="555e3-173">Field</span></span>              | <span data-ttu-id="555e3-174">descrição</span><span class="sxs-lookup"><span data-stu-id="555e3-174">Description</span></span>                            |
|---------------|----------------------------|---------------------------------------------|--------------------|----------------------------------------|
| <span data-ttu-id="555e3-175">Linhas da fatura</span><span class="sxs-lookup"><span data-stu-id="555e3-175">Invoice lines</span></span> | <span data-ttu-id="555e3-176">Compra</span><span class="sxs-lookup"><span data-stu-id="555e3-176">Purchase</span></span>                   | <span data-ttu-id="555e3-177">VendInvoiceTrans</span><span class="sxs-lookup"><span data-stu-id="555e3-177">VendInvoiceTrans</span></span>                            | <span data-ttu-id="555e3-178">SUM(LineAmountMST)</span><span class="sxs-lookup"><span data-stu-id="555e3-178">SUM(LineAmountMST)</span></span> | <span data-ttu-id="555e3-179">O valor na moeda contábil.</span><span class="sxs-lookup"><span data-stu-id="555e3-179">The amount in the accounting currency.</span></span> |

<span data-ttu-id="555e3-180">A tabela a seguir mostra as principais medidas no conteúdo que são calculadas a partir da entidade de linhas da fatura.</span><span class="sxs-lookup"><span data-stu-id="555e3-180">The following table shows the key measurements in the content that are calculated from the Invoice lines entity.</span></span>

| <span data-ttu-id="555e3-181">Medição</span><span class="sxs-lookup"><span data-stu-id="555e3-181">Measure</span></span>               | <span data-ttu-id="555e3-182">Cálculo</span><span class="sxs-lookup"><span data-stu-id="555e3-182">Calculation</span></span>                                                                                         |
|-----------------------|-----------------------------------------------------------------------------------------------------|
| <span data-ttu-id="555e3-183">Ano atual de compra</span><span class="sxs-lookup"><span data-stu-id="555e3-183">Purchase current year</span></span> | <span data-ttu-id="555e3-184">Ano atual de compra = SUM('Invoice lines'\[Purchase\])</span><span class="sxs-lookup"><span data-stu-id="555e3-184">Purchase current year = SUM('Invoice lines'\[Purchase\])</span></span>                                            |
| <span data-ttu-id="555e3-185">Compras do ano passado</span><span class="sxs-lookup"><span data-stu-id="555e3-185">Purchase last year</span></span>    | <span data-ttu-id="555e3-186">Compras do último ano = CALCULATE(SUM('Invoice lines'\[Purchase\]), SAMEPERIODLASTYEAR(Dates\[Date\]))</span><span class="sxs-lookup"><span data-stu-id="555e3-186">Purchase last year = CALCULATE(SUM('Invoice lines'\[Purchase\]), SAMEPERIODLASTYEAR(Dates\[Date\]))</span></span> |
| <span data-ttu-id="555e3-187">Crescimento de compra de YOY</span><span class="sxs-lookup"><span data-stu-id="555e3-187">YOY purchase growth</span></span>   | <span data-ttu-id="555e3-188">Crescimento de compra de YOY = \[Purchase current year\] – \[Purchase last year\]</span><span class="sxs-lookup"><span data-stu-id="555e3-188">YOY purchase growth = \[Purchase current year\] – \[Purchase last year\]</span></span>                            |

<span data-ttu-id="555e3-189">As principais dimensões a seguir no conteúdo são usadas como filtros para cortar as medidas agregadas, para que você possa alcançar mais granularidade e uma introspecção analítica mais profunda.</span><span class="sxs-lookup"><span data-stu-id="555e3-189">The following key dimensions in the content are used as filters to slice the aggregate measurements, so that you can achieve more granularity and gain deeper analytical insights.</span></span>

| <span data-ttu-id="555e3-190">Entidade</span><span class="sxs-lookup"><span data-stu-id="555e3-190">Entity</span></span>                 | <span data-ttu-id="555e3-191">Exemplos de atributos</span><span class="sxs-lookup"><span data-stu-id="555e3-191">Examples of attributes</span></span>                                |
|------------------------|-------------------------------------------------------|
| <span data-ttu-id="555e3-192">Fornecedores</span><span class="sxs-lookup"><span data-stu-id="555e3-192">Vendors</span></span>                | <span data-ttu-id="555e3-193">Grupos de fornecedores, país ou regiões do fornecedor, nome do fornecedor</span><span class="sxs-lookup"><span data-stu-id="555e3-193">Vendor groups, Vendor country or regions, Vendor name</span></span> |
| <span data-ttu-id="555e3-194">Produtos</span><span class="sxs-lookup"><span data-stu-id="555e3-194">Products</span></span>               | <span data-ttu-id="555e3-195">Número do produto, nome do produto, nome do grupo de item</span><span class="sxs-lookup"><span data-stu-id="555e3-195">Product number, Product name, Item groups name</span></span>        |
| <span data-ttu-id="555e3-196">Categorias de compras</span><span class="sxs-lookup"><span data-stu-id="555e3-196">Procurement categories</span></span> | <span data-ttu-id="555e3-197">Categoria de compras, nomes da categoria de compras</span><span class="sxs-lookup"><span data-stu-id="555e3-197">Procurement category, Procurement category names</span></span>      |
| <span data-ttu-id="555e3-198">Entidades legais</span><span class="sxs-lookup"><span data-stu-id="555e3-198">Legal entities</span></span>         | <span data-ttu-id="555e3-199">Nome da entidade legal</span><span class="sxs-lookup"><span data-stu-id="555e3-199">Legal entity name</span></span>                                     |
| <span data-ttu-id="555e3-200">Datas</span><span class="sxs-lookup"><span data-stu-id="555e3-200">Dates</span></span>                  | <span data-ttu-id="555e3-201">Datas, Compensação anual</span><span class="sxs-lookup"><span data-stu-id="555e3-201">Dates, Year offset</span></span>                                    |

<span data-ttu-id="555e3-202">Por padrão, o conteúdo exibe dados do ano atual.</span><span class="sxs-lookup"><span data-stu-id="555e3-202">By default, the content shows data for the current calendar year.</span></span> <span data-ttu-id="555e3-203">Entretanto, poderá modificar o filtro de data na seção filtros de relatório.</span><span class="sxs-lookup"><span data-stu-id="555e3-203">However, you can change the date filter in the report filters section.</span></span> <span data-ttu-id="555e3-204">Você também pode alterar o filtro da empresa.</span><span class="sxs-lookup"><span data-stu-id="555e3-204">You can also change the company filter.</span></span>

