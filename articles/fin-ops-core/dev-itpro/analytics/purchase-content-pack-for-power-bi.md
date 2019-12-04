---
title: Conteúdo de análise de gastos em compras do Power BI
description: Este tópico descreve o que está incluído no conteúdo do Power BI de análise de gastos da compra. Ele explica como acessar os relatórios incluídos no conteúdo, além de fornecer informações sobre o modelo de dados e as entidades usadas para criar o conteúdo.
author: FrankDahl
manager: AnnBe
ms.date: 04/24/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: PurchaseSpendAnalysisPowerBI
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 265434
ms.assetid: 3cd9dfce-2687-4303-bc78-349e7cb5ea75
ms.search.region: global
ms.author: fdahl
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 2d31aaf14f6399baca8531707864c48cd2d56ac2
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/06/2019
ms.locfileid: "2769962"
---
# <a name="purchase-spend-analysis-power-bi-content"></a><span data-ttu-id="5d1c9-104">Conteúdo de análise de gastos em compras do Power BI</span><span class="sxs-lookup"><span data-stu-id="5d1c9-104">Purchase spend analysis Power BI content</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="5d1c9-105">Este tópico descreve o que está incluído no conteúdo do Microsoft Power BI de **análise de gastos da compra**.</span><span class="sxs-lookup"><span data-stu-id="5d1c9-105">This topic describes what is included in the **Purchase spend analysis** Microsoft Power BI content.</span></span> <span data-ttu-id="5d1c9-106">Ele explica como acessar os relatórios do Power BI e fornece informações sobre o modelo de dados e entidades que são usados para criar o conteúdo.</span><span class="sxs-lookup"><span data-stu-id="5d1c9-106">It explains how to access the Power BI reports, and provides information about the data model and entities that are used to build the content.</span></span>

## <a name="overview"></a><span data-ttu-id="5d1c9-107">Visão Geral</span><span class="sxs-lookup"><span data-stu-id="5d1c9-107">Overview</span></span>

<span data-ttu-id="5d1c9-108">O conteúdo do Power BI de **Análise de gastos da compra** foi desenvolvido para ajudar os gerentes de compras e os gerentes responsáveis por orçamentos a acompanhar os gastos de compra.</span><span class="sxs-lookup"><span data-stu-id="5d1c9-108">The **Purchase spend analysis** Power BI content was designed to help purchasing managers and managers who are responsible for budgets keep track of purchase spending.</span></span> <span data-ttu-id="5d1c9-109">Os gerentes podem analisar os gastos de compra das seguintes maneiras:</span><span class="sxs-lookup"><span data-stu-id="5d1c9-109">Managers can analyze purchase spending in the following ways:</span></span>

- <span data-ttu-id="5d1c9-110">Compra de um ano atrás até agora (por grupo de fornecedor e fornecedores individuais, categoria de compras e produtos individuais e local de fornecedor)</span><span class="sxs-lookup"><span data-stu-id="5d1c9-110">Year-to-date purchase (by vendor group and individual vendors, procurement category and individual products, and vendor location)</span></span>
- <span data-ttu-id="5d1c9-111">Alteração de compra de um ano atrás até agora (por grupo de fornecedor e categoria de compras)</span><span class="sxs-lookup"><span data-stu-id="5d1c9-111">Year-over-year purchase change (by vendor group and procurement category)</span></span>

<span data-ttu-id="5d1c9-112">O conteúdo usa dados transacionais de compra e fornece uma visão agregada dos números de compra da empresa e uma repartição dos gastos de compra por fornecedor e produto.</span><span class="sxs-lookup"><span data-stu-id="5d1c9-112">The content uses purchase transactional data, and provides both an aggregate view of the company-wide purchase figures and a breakdown of purchase spending by vendor and product.</span></span> <span data-ttu-id="5d1c9-113">Os relatórios destacam as alterações no gasto em compras ao longo do tempo.</span><span class="sxs-lookup"><span data-stu-id="5d1c9-113">Reports highlight changes in purchase spending over time.</span></span> <span data-ttu-id="5d1c9-114">Portanto, os relatórios podem ser usados para alertar gerentes sobre tendências positivas e negativas de gastos para fornecedores individuais e produtos.</span><span class="sxs-lookup"><span data-stu-id="5d1c9-114">Therefore, the reports can be used to alert managers about positive and negative spending trends for individual vendors and products.</span></span> <span data-ttu-id="5d1c9-115">Além disso, gráficos mostram gasto em compras para categorias de compras diferentes e grupos de fornecedores.</span><span class="sxs-lookup"><span data-stu-id="5d1c9-115">Additionally, charts show purchase spending for different procurement categories and vendor groups.</span></span> <span data-ttu-id="5d1c9-116">Portanto, a categoria e os gerentes regionais podem usar os gráficos para ajudar a identificar mudanças nos comportamentos de gastos.</span><span class="sxs-lookup"><span data-stu-id="5d1c9-116">Therefore, category and regional managers can use the charts to help identify changes in spending behavior.</span></span>

## <a name="accessing-the-power-bi-content"></a><span data-ttu-id="5d1c9-117">Acessando o conteúdo do Power BI</span><span class="sxs-lookup"><span data-stu-id="5d1c9-117">Accessing the Power BI content</span></span>
<span data-ttu-id="5d1c9-118">O conteúdo do Power BI de **Análise de gasto em compras** é exibido na página **Análise de compra e de gastos** (**Compras e fornecimento** \> **Consultas e relatórios** \> **Análise de desempenho de compra** \> **Análise de compra e de gastos**).</span><span class="sxs-lookup"><span data-stu-id="5d1c9-118">The **Purchase spend analysis** Power BI content is shown on the **Purchase and spend analysis** page (**Procurement and sourcing** \> **Inquiries and reports** \> **Purchase performance analysis** \> **Purchase and spend analysis**).</span></span>

## <a name="metrics-that-are-included-in-the-power-bi-content"></a><span data-ttu-id="5d1c9-119">Métricas incluídas no conteúdo do Power BI</span><span class="sxs-lookup"><span data-stu-id="5d1c9-119">Metrics that are included in the Power BI content</span></span>
<span data-ttu-id="5d1c9-120">O conteúdo de Power BI de **Análise de gastos da compra** inclui um relatório que consiste em um grupo de métricas.</span><span class="sxs-lookup"><span data-stu-id="5d1c9-120">The **Purchase spend analysis** Power BI content includes a report that consists of a set of metrics.</span></span> <span data-ttu-id="5d1c9-121">Estas métricas são visualizadas como gráficos, blocos e tabelas.</span><span class="sxs-lookup"><span data-stu-id="5d1c9-121">These metrics are visualized as charts, tiles, and tables.</span></span> 

<span data-ttu-id="5d1c9-122">As seções a seguir fornecem uma visão geral das visualizações.</span><span class="sxs-lookup"><span data-stu-id="5d1c9-122">The following sections provide an overview of the visualizations.</span></span>

### <a name="purchase-by-vendor-report-page"></a><span data-ttu-id="5d1c9-123">Compra por página de relatórios de fornecedor</span><span class="sxs-lookup"><span data-stu-id="5d1c9-123">Purchase by vendor report page</span></span>
<span data-ttu-id="5d1c9-124">**Gráficos**</span><span class="sxs-lookup"><span data-stu-id="5d1c9-124">**Charts**</span></span>
- <span data-ttu-id="5d1c9-125">10 principais fornecedores por compra (gráfico de barra empilhada)</span><span class="sxs-lookup"><span data-stu-id="5d1c9-125">Top 10 vendors by purchase (stacked bar chart)</span></span>
- <span data-ttu-id="5d1c9-126">Compra total por grupo de fornecedor/país/nome (gráfico de pizza)</span><span class="sxs-lookup"><span data-stu-id="5d1c9-126">Total purchase by vendor group / country / name (pie chart)</span></span>
- <span data-ttu-id="5d1c9-127">Compra por grupo de fornecedor/país/nome (gráfico de coluna)</span><span class="sxs-lookup"><span data-stu-id="5d1c9-127">Purchase by vendor group / country / name (column chart)</span></span>
- <span data-ttu-id="5d1c9-128">Compra média por grupo de fornecedor/país/nome (gráfico de coluna)</span><span class="sxs-lookup"><span data-stu-id="5d1c9-128">Average purchase by vendor group / country / name (column chart)</span></span>

<span data-ttu-id="5d1c9-129">**Blocos**</span><span class="sxs-lookup"><span data-stu-id="5d1c9-129">**Tiles**</span></span>
- <span data-ttu-id="5d1c9-130">Total da Compra</span><span class="sxs-lookup"><span data-stu-id="5d1c9-130">Total purchase</span></span>
- <span data-ttu-id="5d1c9-131">Crescimento de compra de YOY</span><span class="sxs-lookup"><span data-stu-id="5d1c9-131">YOY purchase growth</span></span>
- <span data-ttu-id="5d1c9-132">Número total de fornecedores</span><span class="sxs-lookup"><span data-stu-id="5d1c9-132">Total # vendors</span></span>
- <span data-ttu-id="5d1c9-133">Número total de fornecedores ativos</span><span class="sxs-lookup"><span data-stu-id="5d1c9-133">Total # of active vendors</span></span>

<span data-ttu-id="5d1c9-134">**Exemplo**</span><span class="sxs-lookup"><span data-stu-id="5d1c9-134">**Example**</span></span>
<img src="media/spend1.png" alt="Purchase by vendor">

### <a name="purchase-by-product-report-page"></a><span data-ttu-id="5d1c9-135">Compra por página de relatórios de produto</span><span class="sxs-lookup"><span data-stu-id="5d1c9-135">Purchase by product report page</span></span>

<span data-ttu-id="5d1c9-136">**Gráficos**</span><span class="sxs-lookup"><span data-stu-id="5d1c9-136">**Charts**</span></span>
- <span data-ttu-id="5d1c9-137">Compra por categoria de itens/nome do produto (gráfico de coluna)</span><span class="sxs-lookup"><span data-stu-id="5d1c9-137">Purchase by procurement category / product name (column chart)</span></span>
- <span data-ttu-id="5d1c9-138">Compra total por categoria de itens/nome do produto (gráfico de pizza)</span><span class="sxs-lookup"><span data-stu-id="5d1c9-138">Total purchase by procurement category / product name (pie chart)</span></span>
- <span data-ttu-id="5d1c9-139">10 principais produtos por compra (gráfico de barra empilhada)</span><span class="sxs-lookup"><span data-stu-id="5d1c9-139">Top 10 products by purchase (stacked bar chart)</span></span>

<span data-ttu-id="5d1c9-140">**Blocos**</span><span class="sxs-lookup"><span data-stu-id="5d1c9-140">**Tiles**</span></span>
- <span data-ttu-id="5d1c9-141">Número total de produtos</span><span class="sxs-lookup"><span data-stu-id="5d1c9-141">Total # of products</span></span></li>
- <span data-ttu-id="5d1c9-142">Porcentagem de produtos ativos total do número total de produtos</span><span class="sxs-lookup"><span data-stu-id="5d1c9-142">Total active products percentage of total # of products</span></span>
- <span data-ttu-id="5d1c9-143">Número da contabilidade de produtos para compra de 80%</span><span class="sxs-lookup"><span data-stu-id="5d1c9-143">Number of products accounting for 80% purchase</span></span>

<span data-ttu-id="5d1c9-144">**Exemplo**</span><span class="sxs-lookup"><span data-stu-id="5d1c9-144">**Example**</span></span>


<img src="media/purchaseByProduct.png" alt="Purchase by Product">

### <a name="purchase-by-period-report-page"></a><span data-ttu-id="5d1c9-145">Compra por página de relatórios de período</span><span class="sxs-lookup"><span data-stu-id="5d1c9-145">Purchase by period report page</span></span>
<span data-ttu-id="5d1c9-146">Essa página exibe compras este ano e no ano passado e crescimento por categoria de compra.</span><span class="sxs-lookup"><span data-stu-id="5d1c9-146">This page shows purchases this year and last year, and growth by procurement category.</span></span>

<span data-ttu-id="5d1c9-147">**Gráficos**</span><span class="sxs-lookup"><span data-stu-id="5d1c9-147">**Charts**</span></span> 
- <span data-ttu-id="5d1c9-148">Compra por mês/dia (gráfico de coluna)</span><span class="sxs-lookup"><span data-stu-id="5d1c9-148">Purchase by month / day (column chart)</span></span>
- <span data-ttu-id="5d1c9-149">Variação de YOY de compra cumulativa (gráfico de cascata)</span><span class="sxs-lookup"><span data-stu-id="5d1c9-149">Cumulative purchase YOY variance (waterfall chart)</span></span>
- <span data-ttu-id="5d1c9-150">Crescimento de YOY total da compra (gráfico de coluna)</span><span class="sxs-lookup"><span data-stu-id="5d1c9-150">Total purchase YOY growth (column chart)</span></span>
- <span data-ttu-id="5d1c9-151">Demonstrativo de compras (matriz)</span><span class="sxs-lookup"><span data-stu-id="5d1c9-151">Procurement statement (matrix)</span></span>

<span data-ttu-id="5d1c9-152">**Blocos**</span><span class="sxs-lookup"><span data-stu-id="5d1c9-152">**Tiles**</span></span>
- <span data-ttu-id="5d1c9-153">Crescimento de compra de YOY</span><span class="sxs-lookup"><span data-stu-id="5d1c9-153">YOY purchase growth</span></span>
- <span data-ttu-id="5d1c9-154">Porcentagem de crescimento de compra de YOY</span><span class="sxs-lookup"><span data-stu-id="5d1c9-154">YOY purchase growth %</span></span>

<span data-ttu-id="5d1c9-155">**Exemplo**</span><span class="sxs-lookup"><span data-stu-id="5d1c9-155">**Example**</span></span>
<img src="media/purchaseByPeriod.png" alt="Purchase by Period">

### <a name="purchase-by-vendor-location-report-page"></a><span data-ttu-id="5d1c9-156">Compra por página de relatórios locais de fornecedor</span><span class="sxs-lookup"><span data-stu-id="5d1c9-156">Purchase by vendor location report page</span></span>

<span data-ttu-id="5d1c9-157">**Gráficos**</span><span class="sxs-lookup"><span data-stu-id="5d1c9-157">**Charts**</span></span>
- <span data-ttu-id="5d1c9-158">Compra por cidade</span><span class="sxs-lookup"><span data-stu-id="5d1c9-158">Purchase by city</span></span>
- <span data-ttu-id="5d1c9-159">Porcentagem de crescimento de YOY de compra</span><span class="sxs-lookup"><span data-stu-id="5d1c9-159">Purchase YOY growth %</span></span>
- <span data-ttu-id="5d1c9-160">Compra por país</span><span class="sxs-lookup"><span data-stu-id="5d1c9-160">Purchase by country</span></span>

<span data-ttu-id="5d1c9-161">**Exemplo**</span><span class="sxs-lookup"><span data-stu-id="5d1c9-161">**Example**</span></span>
<img src="media/purchByVendorLocation.png" alt="Purchase by Vendor Location">

### <a name="purchase-spend-analysis-by-time-report-page"></a><span data-ttu-id="5d1c9-162">Análise de gastos de compra por página de relatório de hora</span><span class="sxs-lookup"><span data-stu-id="5d1c9-162">Purchase spend analysis by time report page</span></span>

<span data-ttu-id="5d1c9-163">**Gráficos**</span><span class="sxs-lookup"><span data-stu-id="5d1c9-163">**Charts**</span></span> 
- <span data-ttu-id="5d1c9-164">Ano atual de compra em mês/dia (gráfico de linha)</span><span class="sxs-lookup"><span data-stu-id="5d1c9-164">Purchase current year by month / day (line chart)</span></span>
- <span data-ttu-id="5d1c9-165">Compra atual e do último ano (gráfico de linha e coluna)</span><span class="sxs-lookup"><span data-stu-id="5d1c9-165">Purchase current and last year (line and column chart)</span></span>

<span data-ttu-id="5d1c9-166">**Exemplo**</span><span class="sxs-lookup"><span data-stu-id="5d1c9-166">**Example**</span></span>
<img src="media/PurchByTIme.png" alt="Purchase by Time">

### <a name="purchase-spend-analysis-by-vendor-report-page"></a><span data-ttu-id="5d1c9-167">Análise de gastos de compra por página de relatório de fornecedor</span><span class="sxs-lookup"><span data-stu-id="5d1c9-167">Purchase spend analysis by vendor report page</span></span>

<span data-ttu-id="5d1c9-168">**Gráficos**</span><span class="sxs-lookup"><span data-stu-id="5d1c9-168">**Charts**</span></span> 
- <span data-ttu-id="5d1c9-169">10 principais porcentagens de compra de fornecedor (funil)</span><span class="sxs-lookup"><span data-stu-id="5d1c9-169">Top 10 vendor purchase % of purchase (funnel)</span></span>
- <span data-ttu-id="5d1c9-170">10 principais fornecedores com gasto elevado de YOY</span><span class="sxs-lookup"><span data-stu-id="5d1c9-170">Top 10 vendors with increased spending YOY</span></span>
- <span data-ttu-id="5d1c9-171">10 principais fornecedores com gasto diminuído de YOY</span><span class="sxs-lookup"><span data-stu-id="5d1c9-171">Top 10 vendors with decreased spending YOY</span></span>

<span data-ttu-id="5d1c9-172">**Exemplo** 
</span><span class="sxs-lookup"><span data-stu-id="5d1c9-172">**Example** 
</span></span><img src="media/PurchSpendAnalysisByVendor.png" alt="Purchase spend by vendor">


## <a name="data-model-and-entities"></a><span data-ttu-id="5d1c9-173">Modelo de dados e entidades</span><span class="sxs-lookup"><span data-stu-id="5d1c9-173">Data model and entities</span></span>
<span data-ttu-id="5d1c9-174">Os seguintes dados são usados para preencher as páginas de relatório no conteúdo do Power BI **Análise de gastos da compra**.</span><span class="sxs-lookup"><span data-stu-id="5d1c9-174">The following data is used to fill the report pages in the **Purchase spend analysis** Power BI content.</span></span> <span data-ttu-id="5d1c9-175">Esses dados são representadas como medições agregadas que foram preparadas no Repositório de entidades.</span><span class="sxs-lookup"><span data-stu-id="5d1c9-175">This data is represented as aggregate measurements that are staged in the Entity store.</span></span> <span data-ttu-id="5d1c9-176">O Repositório de entidades é um banco de dados do Microsoft SQL Server otimizado para análise.</span><span class="sxs-lookup"><span data-stu-id="5d1c9-176">The Entity store is a Microsoft SQL Server database that is optimized for analytics.</span></span> <span data-ttu-id="5d1c9-177">Para obter mais informações, consulte [Integração do Power BI com o repositório Entidade](power-bi-integration-entity-store.md).</span><span class="sxs-lookup"><span data-stu-id="5d1c9-177">For more information, see [Power BI integration with Entity store](power-bi-integration-entity-store.md).</span></span>

<span data-ttu-id="5d1c9-178">As medidas agregadas neste conteúdo são o subconjunto de medidas agregadas que estavam disponíveis no Cubo de Compras no Microsoft Dynamics AX 2012 e no Microsoft Dynamics AX 2012 R3.</span><span class="sxs-lookup"><span data-stu-id="5d1c9-178">The aggregate measurements in this content are the subset of aggregate measurements that were available in the Purchase Cube in Microsoft Dynamics AX 2012 and Microsoft Dynamics AX 2012 R3.</span></span> <span data-ttu-id="5d1c9-179">Para preparar as medidas agregadas do cubo na loja Entidade, você deve torná-las implementáveis.</span><span class="sxs-lookup"><span data-stu-id="5d1c9-179">To stage the cube's aggregate measurements in the Entity store, you must make them deployable.</span></span> <span data-ttu-id="5d1c9-180">Para obter mais informações, consulte o procedimento sobre como preparar medidas agregadas no repositório Entidade em [Integração do Power BI com o repositório Entidade](power-bi-integration-entity-store.md).</span><span class="sxs-lookup"><span data-stu-id="5d1c9-180">For more information, see the procedure for staging aggregate measurements in the Entity store in [Power BI integration with Entity store](power-bi-integration-entity-store.md).</span></span> <span data-ttu-id="5d1c9-181">As principais medidas agregadas a seguir estão disponíveis diretamente nas entidade de linhas de fatura e são usadas como base do conteúdo.</span><span class="sxs-lookup"><span data-stu-id="5d1c9-181">The following key aggregate measurements are available directly from the Invoice lines entity and are used as the basis of the content.</span></span>

| <span data-ttu-id="5d1c9-182">Entidade</span><span class="sxs-lookup"><span data-stu-id="5d1c9-182">Entity</span></span>        | <span data-ttu-id="5d1c9-183">Principais medidas agregadas</span><span class="sxs-lookup"><span data-stu-id="5d1c9-183">Key aggregate measurements</span></span> | <span data-ttu-id="5d1c9-184">Fonte de dados</span><span class="sxs-lookup"><span data-stu-id="5d1c9-184">Data source</span></span>                                 | <span data-ttu-id="5d1c9-185">Campo</span><span class="sxs-lookup"><span data-stu-id="5d1c9-185">Field</span></span>              | <span data-ttu-id="5d1c9-186">descrição</span><span class="sxs-lookup"><span data-stu-id="5d1c9-186">Description</span></span>                            |
|---------------|----------------------------|---------------------------------------------|--------------------|----------------------------------------|
| <span data-ttu-id="5d1c9-187">Linhas da fatura</span><span class="sxs-lookup"><span data-stu-id="5d1c9-187">Invoice lines</span></span> | <span data-ttu-id="5d1c9-188">Compra</span><span class="sxs-lookup"><span data-stu-id="5d1c9-188">Purchase</span></span>                   | <span data-ttu-id="5d1c9-189">VendInvoiceTrans</span><span class="sxs-lookup"><span data-stu-id="5d1c9-189">VendInvoiceTrans</span></span>                            | <span data-ttu-id="5d1c9-190">SUM(LineAmountMST)</span><span class="sxs-lookup"><span data-stu-id="5d1c9-190">SUM(LineAmountMST)</span></span> | <span data-ttu-id="5d1c9-191">O valor na moeda contábil.</span><span class="sxs-lookup"><span data-stu-id="5d1c9-191">The amount in the accounting currency.</span></span> |

<span data-ttu-id="5d1c9-192">A tabela a seguir mostra as principais medidas no conteúdo que são calculadas a partir da entidade de linhas da fatura.</span><span class="sxs-lookup"><span data-stu-id="5d1c9-192">The following table shows the key measurements in the content that are calculated from the Invoice lines entity.</span></span>

| <span data-ttu-id="5d1c9-193">Medição</span><span class="sxs-lookup"><span data-stu-id="5d1c9-193">Measure</span></span>               | <span data-ttu-id="5d1c9-194">Cálculo</span><span class="sxs-lookup"><span data-stu-id="5d1c9-194">Calculation</span></span>                                                                                         |
|-----------------------|-----------------------------------------------------------------------------------------------------|
| <span data-ttu-id="5d1c9-195">Ano atual de compra</span><span class="sxs-lookup"><span data-stu-id="5d1c9-195">Purchase current year</span></span> | <span data-ttu-id="5d1c9-196">Ano atual de compra = SUM('Invoice lines'\[Purchase\])</span><span class="sxs-lookup"><span data-stu-id="5d1c9-196">Purchase current year = SUM('Invoice lines'\[Purchase\])</span></span>                                            |
| <span data-ttu-id="5d1c9-197">Compras do ano passado</span><span class="sxs-lookup"><span data-stu-id="5d1c9-197">Purchase last year</span></span>    | <span data-ttu-id="5d1c9-198">Compras do último ano = CALCULATE(SUM('Invoice lines'\[Purchase\]), SAMEPERIODLASTYEAR(Dates\[Date\]))</span><span class="sxs-lookup"><span data-stu-id="5d1c9-198">Purchase last year = CALCULATE(SUM('Invoice lines'\[Purchase\]), SAMEPERIODLASTYEAR(Dates\[Date\]))</span></span> |
| <span data-ttu-id="5d1c9-199">Crescimento de compra de YOY</span><span class="sxs-lookup"><span data-stu-id="5d1c9-199">YOY purchase growth</span></span>   | <span data-ttu-id="5d1c9-200">Crescimento de compra de YOY = \[Purchase current year\] – \[Purchase last year\]</span><span class="sxs-lookup"><span data-stu-id="5d1c9-200">YOY purchase growth = \[Purchase current year\] – \[Purchase last year\]</span></span>                            |

<span data-ttu-id="5d1c9-201">As principais dimensões a seguir no conteúdo são usadas como filtros para cortar as medidas agregadas, para que você possa alcançar mais granularidade e uma introspecção analítica mais profunda.</span><span class="sxs-lookup"><span data-stu-id="5d1c9-201">The following key dimensions in the content are used as filters to slice the aggregate measurements, so that you can achieve more granularity and gain deeper analytical insights.</span></span>

| <span data-ttu-id="5d1c9-202">Entidade</span><span class="sxs-lookup"><span data-stu-id="5d1c9-202">Entity</span></span>                 | <span data-ttu-id="5d1c9-203">Exemplos de atributos</span><span class="sxs-lookup"><span data-stu-id="5d1c9-203">Examples of attributes</span></span>                                |
|------------------------|-------------------------------------------------------|
| <span data-ttu-id="5d1c9-204">Fornecedores</span><span class="sxs-lookup"><span data-stu-id="5d1c9-204">Vendors</span></span>                | <span data-ttu-id="5d1c9-205">Grupos de fornecedores, país ou regiões do fornecedor, nome do fornecedor</span><span class="sxs-lookup"><span data-stu-id="5d1c9-205">Vendor groups, Vendor country or regions, Vendor name</span></span> |
| <span data-ttu-id="5d1c9-206">Produtos</span><span class="sxs-lookup"><span data-stu-id="5d1c9-206">Products</span></span>               | <span data-ttu-id="5d1c9-207">Número do produto, nome do produto, nome do grupo de item</span><span class="sxs-lookup"><span data-stu-id="5d1c9-207">Product number, Product name, Item groups name</span></span>        |
| <span data-ttu-id="5d1c9-208">Categorias de compras</span><span class="sxs-lookup"><span data-stu-id="5d1c9-208">Procurement categories</span></span> | <span data-ttu-id="5d1c9-209">Categoria de compras, nomes da categoria de compras</span><span class="sxs-lookup"><span data-stu-id="5d1c9-209">Procurement category, Procurement category names</span></span>      |
| <span data-ttu-id="5d1c9-210">Entidades legais</span><span class="sxs-lookup"><span data-stu-id="5d1c9-210">Legal entities</span></span>         | <span data-ttu-id="5d1c9-211">Nome da entidade legal</span><span class="sxs-lookup"><span data-stu-id="5d1c9-211">Legal entity name</span></span>                                     |
| <span data-ttu-id="5d1c9-212">Datas</span><span class="sxs-lookup"><span data-stu-id="5d1c9-212">Dates</span></span>                  | <span data-ttu-id="5d1c9-213">Datas, Compensação anual</span><span class="sxs-lookup"><span data-stu-id="5d1c9-213">Dates, Year offset</span></span>                                    |

<span data-ttu-id="5d1c9-214">Por padrão, o conteúdo exibe dados do ano atual.</span><span class="sxs-lookup"><span data-stu-id="5d1c9-214">By default, the content shows data for the current calendar year.</span></span> <span data-ttu-id="5d1c9-215">Entretanto, poderá modificar o filtro de data na seção filtros de relatório.</span><span class="sxs-lookup"><span data-stu-id="5d1c9-215">However, you can change the date filter in the report filters section.</span></span> <span data-ttu-id="5d1c9-216">Você também pode alterar o filtro da empresa.</span><span class="sxs-lookup"><span data-stu-id="5d1c9-216">You can also change the company filter.</span></span>
