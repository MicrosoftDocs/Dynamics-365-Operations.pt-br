---
title: Conteúdo de análise de gastos em compras do Power BI
description: Este tópico descreve o que está incluído no conteúdo do Power BI de análise de gastos da compra.
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
ms.custom: 265434
ms.assetid: 3cd9dfce-2687-4303-bc78-349e7cb5ea75
ms.search.region: global
ms.author: fdahl
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 5914abaafab509e278d7a85441928feddb0b5164
ms.sourcegitcommit: 5192cfaedfd861faea63d8954d7bcc500608a225
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/30/2021
ms.locfileid: "5093433"
---
# <a name="purchase-spend-analysis-power-bi-content"></a><span data-ttu-id="167fb-103">Conteúdo de análise de gastos em compras do Power BI</span><span class="sxs-lookup"><span data-stu-id="167fb-103">Purchase spend analysis Power BI content</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="167fb-104">Este tópico descreve o que está incluído no conteúdo do Microsoft Power BI de **análise de gastos da compra**.</span><span class="sxs-lookup"><span data-stu-id="167fb-104">This topic describes what is included in the **Purchase spend analysis** Microsoft Power BI content.</span></span> <span data-ttu-id="167fb-105">Ele explica como acessar os relatórios do Power BI e fornece informações sobre o modelo de dados e entidades que são usados para criar o conteúdo.</span><span class="sxs-lookup"><span data-stu-id="167fb-105">It explains how to access the Power BI reports, and provides information about the data model and entities that are used to build the content.</span></span>

## <a name="overview"></a><span data-ttu-id="167fb-106">Visão Geral</span><span class="sxs-lookup"><span data-stu-id="167fb-106">Overview</span></span>

<span data-ttu-id="167fb-107">O conteúdo do Power BI de **Análise de gastos da compra** foi desenvolvido para ajudar os gerentes de compras e os gerentes responsáveis por orçamentos a acompanhar os gastos de compra.</span><span class="sxs-lookup"><span data-stu-id="167fb-107">The **Purchase spend analysis** Power BI content was designed to help purchasing managers and managers who are responsible for budgets keep track of purchase spending.</span></span> <span data-ttu-id="167fb-108">Os gerentes podem analisar os gastos de compra das seguintes maneiras:</span><span class="sxs-lookup"><span data-stu-id="167fb-108">Managers can analyze purchase spending in the following ways:</span></span>

- <span data-ttu-id="167fb-109">Compra de um ano atrás até agora (por grupo de fornecedor e fornecedores individuais, categoria de compras e produtos individuais e local de fornecedor)</span><span class="sxs-lookup"><span data-stu-id="167fb-109">Year-to-date purchase (by vendor group and individual vendors, procurement category and individual products, and vendor location)</span></span>
- <span data-ttu-id="167fb-110">Alteração de compra de um ano atrás até agora (por grupo de fornecedor e categoria de compras)</span><span class="sxs-lookup"><span data-stu-id="167fb-110">Year-over-year purchase change (by vendor group and procurement category)</span></span>

<span data-ttu-id="167fb-111">O conteúdo usa dados transacionais de compra e fornece uma visão agregada dos números de compra da empresa e uma repartição dos gastos de compra por fornecedor e produto.</span><span class="sxs-lookup"><span data-stu-id="167fb-111">The content uses purchase transactional data, and provides both an aggregate view of the company-wide purchase figures and a breakdown of purchase spending by vendor and product.</span></span> <span data-ttu-id="167fb-112">Os relatórios destacam as alterações no gasto em compras ao longo do tempo.</span><span class="sxs-lookup"><span data-stu-id="167fb-112">Reports highlight changes in purchase spending over time.</span></span> <span data-ttu-id="167fb-113">Portanto, os relatórios podem ser usados para alertar gerentes sobre tendências positivas e negativas de gastos para fornecedores individuais e produtos.</span><span class="sxs-lookup"><span data-stu-id="167fb-113">Therefore, the reports can be used to alert managers about positive and negative spending trends for individual vendors and products.</span></span> <span data-ttu-id="167fb-114">Além disso, gráficos mostram gasto em compras para categorias de compras diferentes e grupos de fornecedores.</span><span class="sxs-lookup"><span data-stu-id="167fb-114">Additionally, charts show purchase spending for different procurement categories and vendor groups.</span></span> <span data-ttu-id="167fb-115">Portanto, a categoria e os gerentes regionais podem usar os gráficos para ajudar a identificar mudanças nos comportamentos de gastos.</span><span class="sxs-lookup"><span data-stu-id="167fb-115">Therefore, category and regional managers can use the charts to help identify changes in spending behavior.</span></span>

## <a name="accessing-the-power-bi-content"></a><span data-ttu-id="167fb-116">Acessando o conteúdo do Power BI</span><span class="sxs-lookup"><span data-stu-id="167fb-116">Accessing the Power BI content</span></span>
<span data-ttu-id="167fb-117">O conteúdo do Power BI de **Análise de gasto em compras** é exibido na página **Análise de compra e de gastos** (**Compras e fornecimento** \> **Consultas e relatórios** \> **Análise de desempenho de compra** \> **Análise de compra e de gastos**).</span><span class="sxs-lookup"><span data-stu-id="167fb-117">The **Purchase spend analysis** Power BI content is shown on the **Purchase and spend analysis** page (**Procurement and sourcing** \> **Inquiries and reports** \> **Purchase performance analysis** \> **Purchase and spend analysis**).</span></span>

## <a name="metrics-that-are-included-in-the-power-bi-content"></a><span data-ttu-id="167fb-118">Métricas incluídas no conteúdo do Power BI</span><span class="sxs-lookup"><span data-stu-id="167fb-118">Metrics that are included in the Power BI content</span></span>
<span data-ttu-id="167fb-119">O conteúdo de Power BI de **Análise de gastos da compra** inclui um relatório que consiste em um grupo de métricas.</span><span class="sxs-lookup"><span data-stu-id="167fb-119">The **Purchase spend analysis** Power BI content includes a report that consists of a set of metrics.</span></span> <span data-ttu-id="167fb-120">Estas métricas são visualizadas como gráficos, blocos e tabelas.</span><span class="sxs-lookup"><span data-stu-id="167fb-120">These metrics are visualized as charts, tiles, and tables.</span></span> 

<span data-ttu-id="167fb-121">As seções a seguir fornecem uma visão geral das visualizações.</span><span class="sxs-lookup"><span data-stu-id="167fb-121">The following sections provide an overview of the visualizations.</span></span>

### <a name="purchase-by-vendor-report-page"></a><span data-ttu-id="167fb-122">Compra por página de relatórios de fornecedor</span><span class="sxs-lookup"><span data-stu-id="167fb-122">Purchase by vendor report page</span></span>
<span data-ttu-id="167fb-123">**Gráficos**</span><span class="sxs-lookup"><span data-stu-id="167fb-123">**Charts**</span></span>
- <span data-ttu-id="167fb-124">10 principais fornecedores por compra (gráfico de barra empilhada)</span><span class="sxs-lookup"><span data-stu-id="167fb-124">Top 10 vendors by purchase (stacked bar chart)</span></span>
- <span data-ttu-id="167fb-125">Compra total por grupo de fornecedor/país/nome (gráfico de pizza)</span><span class="sxs-lookup"><span data-stu-id="167fb-125">Total purchase by vendor group / country / name (pie chart)</span></span>
- <span data-ttu-id="167fb-126">Compra por grupo de fornecedor/país/nome (gráfico de coluna)</span><span class="sxs-lookup"><span data-stu-id="167fb-126">Purchase by vendor group / country / name (column chart)</span></span>
- <span data-ttu-id="167fb-127">Compra média por grupo de fornecedor/país/nome (gráfico de coluna)</span><span class="sxs-lookup"><span data-stu-id="167fb-127">Average purchase by vendor group / country / name (column chart)</span></span>

<span data-ttu-id="167fb-128">**Blocos**</span><span class="sxs-lookup"><span data-stu-id="167fb-128">**Tiles**</span></span>
- <span data-ttu-id="167fb-129">Total da Compra</span><span class="sxs-lookup"><span data-stu-id="167fb-129">Total purchase</span></span>
- <span data-ttu-id="167fb-130">Crescimento de compra de YOY</span><span class="sxs-lookup"><span data-stu-id="167fb-130">YOY purchase growth</span></span>
- <span data-ttu-id="167fb-131">Número total de fornecedores</span><span class="sxs-lookup"><span data-stu-id="167fb-131">Total # vendors</span></span>
- <span data-ttu-id="167fb-132">Número total de fornecedores ativos</span><span class="sxs-lookup"><span data-stu-id="167fb-132">Total # of active vendors</span></span>

<span data-ttu-id="167fb-133">**Exemplo**</span><span class="sxs-lookup"><span data-stu-id="167fb-133">**Example**</span></span>
<img src="media/spend1.png" alt="Purchase by vendor">

### <a name="purchase-by-product-report-page"></a><span data-ttu-id="167fb-134">Compra por página de relatórios de produto</span><span class="sxs-lookup"><span data-stu-id="167fb-134">Purchase by product report page</span></span>

<span data-ttu-id="167fb-135">**Gráficos**</span><span class="sxs-lookup"><span data-stu-id="167fb-135">**Charts**</span></span>
- <span data-ttu-id="167fb-136">Compra por categoria de itens/nome do produto (gráfico de coluna)</span><span class="sxs-lookup"><span data-stu-id="167fb-136">Purchase by procurement category / product name (column chart)</span></span>
- <span data-ttu-id="167fb-137">Compra total por categoria de itens/nome do produto (gráfico de pizza)</span><span class="sxs-lookup"><span data-stu-id="167fb-137">Total purchase by procurement category / product name (pie chart)</span></span>
- <span data-ttu-id="167fb-138">10 principais produtos por compra (gráfico de barra empilhada)</span><span class="sxs-lookup"><span data-stu-id="167fb-138">Top 10 products by purchase (stacked bar chart)</span></span>

<span data-ttu-id="167fb-139">**Blocos**</span><span class="sxs-lookup"><span data-stu-id="167fb-139">**Tiles**</span></span>
- <span data-ttu-id="167fb-140">Número total de produtos</span><span class="sxs-lookup"><span data-stu-id="167fb-140">Total # of products</span></span></li>
- <span data-ttu-id="167fb-141">Porcentagem de produtos ativos total do número total de produtos</span><span class="sxs-lookup"><span data-stu-id="167fb-141">Total active products percentage of total # of products</span></span>
- <span data-ttu-id="167fb-142">Número da contabilidade de produtos para compra de 80%</span><span class="sxs-lookup"><span data-stu-id="167fb-142">Number of products accounting for 80% purchase</span></span>

<span data-ttu-id="167fb-143">**Exemplo**</span><span class="sxs-lookup"><span data-stu-id="167fb-143">**Example**</span></span>


<img src="media/purchaseByProduct.png" alt="Purchase by Product">

### <a name="purchase-by-period-report-page"></a><span data-ttu-id="167fb-144">Compra por página de relatórios de período</span><span class="sxs-lookup"><span data-stu-id="167fb-144">Purchase by period report page</span></span>
<span data-ttu-id="167fb-145">Essa página exibe compras este ano e no ano passado e crescimento por categoria de compra.</span><span class="sxs-lookup"><span data-stu-id="167fb-145">This page shows purchases this year and last year, and growth by procurement category.</span></span>

<span data-ttu-id="167fb-146">**Gráficos**</span><span class="sxs-lookup"><span data-stu-id="167fb-146">**Charts**</span></span> 
- <span data-ttu-id="167fb-147">Compra por mês/dia (gráfico de coluna)</span><span class="sxs-lookup"><span data-stu-id="167fb-147">Purchase by month / day (column chart)</span></span>
- <span data-ttu-id="167fb-148">Variação de YOY de compra cumulativa (gráfico de cascata)</span><span class="sxs-lookup"><span data-stu-id="167fb-148">Cumulative purchase YOY variance (waterfall chart)</span></span>
- <span data-ttu-id="167fb-149">Crescimento de YOY total da compra (gráfico de coluna)</span><span class="sxs-lookup"><span data-stu-id="167fb-149">Total purchase YOY growth (column chart)</span></span>
- <span data-ttu-id="167fb-150">Demonstrativo de compras (matriz)</span><span class="sxs-lookup"><span data-stu-id="167fb-150">Procurement statement (matrix)</span></span>

<span data-ttu-id="167fb-151">**Blocos**</span><span class="sxs-lookup"><span data-stu-id="167fb-151">**Tiles**</span></span>
- <span data-ttu-id="167fb-152">Crescimento de compra de YOY</span><span class="sxs-lookup"><span data-stu-id="167fb-152">YOY purchase growth</span></span>
- <span data-ttu-id="167fb-153">Porcentagem de crescimento de compra de YOY</span><span class="sxs-lookup"><span data-stu-id="167fb-153">YOY purchase growth %</span></span>

<span data-ttu-id="167fb-154">**Exemplo**</span><span class="sxs-lookup"><span data-stu-id="167fb-154">**Example**</span></span>
<img src="media/purchaseByPeriod.png" alt="Purchase by Period">

### <a name="purchase-by-vendor-location-report-page"></a><span data-ttu-id="167fb-155">Compra por página de relatórios locais de fornecedor</span><span class="sxs-lookup"><span data-stu-id="167fb-155">Purchase by vendor location report page</span></span>

<span data-ttu-id="167fb-156">**Gráficos**</span><span class="sxs-lookup"><span data-stu-id="167fb-156">**Charts**</span></span>
- <span data-ttu-id="167fb-157">Compra por cidade</span><span class="sxs-lookup"><span data-stu-id="167fb-157">Purchase by city</span></span>
- <span data-ttu-id="167fb-158">Porcentagem de crescimento de YOY de compra</span><span class="sxs-lookup"><span data-stu-id="167fb-158">Purchase YOY growth %</span></span>
- <span data-ttu-id="167fb-159">Compra por país</span><span class="sxs-lookup"><span data-stu-id="167fb-159">Purchase by country</span></span>

<span data-ttu-id="167fb-160">**Exemplo**</span><span class="sxs-lookup"><span data-stu-id="167fb-160">**Example**</span></span>
<img src="media/purchByVendorLocation.png" alt="Purchase by Vendor Location">

### <a name="purchase-spend-analysis-by-time-report-page"></a><span data-ttu-id="167fb-161">Análise de gastos de compra por página de relatório de hora</span><span class="sxs-lookup"><span data-stu-id="167fb-161">Purchase spend analysis by time report page</span></span>

<span data-ttu-id="167fb-162">**Gráficos**</span><span class="sxs-lookup"><span data-stu-id="167fb-162">**Charts**</span></span> 
- <span data-ttu-id="167fb-163">Ano atual de compra em mês/dia (gráfico de linha)</span><span class="sxs-lookup"><span data-stu-id="167fb-163">Purchase current year by month / day (line chart)</span></span>
- <span data-ttu-id="167fb-164">Compra atual e do último ano (gráfico de linha e coluna)</span><span class="sxs-lookup"><span data-stu-id="167fb-164">Purchase current and last year (line and column chart)</span></span>

<span data-ttu-id="167fb-165">**Exemplo**</span><span class="sxs-lookup"><span data-stu-id="167fb-165">**Example**</span></span>
<img src="media/PurchByTIme.png" alt="Purchase by Time">

### <a name="purchase-spend-analysis-by-vendor-report-page"></a><span data-ttu-id="167fb-166">Análise de gastos de compra por página de relatório de fornecedor</span><span class="sxs-lookup"><span data-stu-id="167fb-166">Purchase spend analysis by vendor report page</span></span>

<span data-ttu-id="167fb-167">**Gráficos**</span><span class="sxs-lookup"><span data-stu-id="167fb-167">**Charts**</span></span> 
- <span data-ttu-id="167fb-168">10 principais porcentagens de compra de fornecedor (funil)</span><span class="sxs-lookup"><span data-stu-id="167fb-168">Top 10 vendor purchase % of purchase (funnel)</span></span>
- <span data-ttu-id="167fb-169">10 principais fornecedores com gasto elevado de YOY</span><span class="sxs-lookup"><span data-stu-id="167fb-169">Top 10 vendors with increased spending YOY</span></span>
- <span data-ttu-id="167fb-170">10 principais fornecedores com gasto diminuído de YOY</span><span class="sxs-lookup"><span data-stu-id="167fb-170">Top 10 vendors with decreased spending YOY</span></span>

<span data-ttu-id="167fb-171">**Exemplo** 
</span><span class="sxs-lookup"><span data-stu-id="167fb-171">**Example** 
</span></span><img src="media/PurchSpendAnalysisByVendor.png" alt="Purchase spend by vendor">


## <a name="data-model-and-entities"></a><span data-ttu-id="167fb-172">Modelo de dados e entidades</span><span class="sxs-lookup"><span data-stu-id="167fb-172">Data model and entities</span></span>
<span data-ttu-id="167fb-173">Os seguintes dados são usados para preencher as páginas de relatório no conteúdo do Power BI **Análise de gastos da compra**.</span><span class="sxs-lookup"><span data-stu-id="167fb-173">The following data is used to fill the report pages in the **Purchase spend analysis** Power BI content.</span></span> <span data-ttu-id="167fb-174">Esses dados são representadas como medições agregadas que foram preparadas no Repositório de entidades.</span><span class="sxs-lookup"><span data-stu-id="167fb-174">This data is represented as aggregate measurements that are staged in the Entity store.</span></span> <span data-ttu-id="167fb-175">O Repositório de entidades é um banco de dados do Microsoft SQL Server otimizado para análise.</span><span class="sxs-lookup"><span data-stu-id="167fb-175">The Entity store is a Microsoft SQL Server database that is optimized for analytics.</span></span> <span data-ttu-id="167fb-176">Para obter mais informações, consulte [Integração do Power BI com o repositório Entidade](power-bi-integration-entity-store.md).</span><span class="sxs-lookup"><span data-stu-id="167fb-176">For more information, see [Power BI integration with Entity store](power-bi-integration-entity-store.md).</span></span>

<span data-ttu-id="167fb-177">As medidas agregadas neste conteúdo são o subconjunto de medidas agregadas que estavam disponíveis no Cubo de Compras no Microsoft Dynamics AX 2012 e no Microsoft Dynamics AX 2012 R3.</span><span class="sxs-lookup"><span data-stu-id="167fb-177">The aggregate measurements in this content are the subset of aggregate measurements that were available in the Purchase Cube in Microsoft Dynamics AX 2012 and Microsoft Dynamics AX 2012 R3.</span></span> <span data-ttu-id="167fb-178">Para preparar as medidas agregadas do cubo na loja Entidade, você deve torná-las implementáveis.</span><span class="sxs-lookup"><span data-stu-id="167fb-178">To stage the cube's aggregate measurements in the Entity store, you must make them deployable.</span></span> <span data-ttu-id="167fb-179">Para obter mais informações, consulte o procedimento sobre como preparar medidas agregadas no repositório Entidade em [Integração do Power BI com o repositório Entidade](power-bi-integration-entity-store.md).</span><span class="sxs-lookup"><span data-stu-id="167fb-179">For more information, see the procedure for staging aggregate measurements in the Entity store in [Power BI integration with Entity store](power-bi-integration-entity-store.md).</span></span> <span data-ttu-id="167fb-180">As principais medidas agregadas a seguir estão disponíveis diretamente nas entidade de linhas de fatura e são usadas como base do conteúdo.</span><span class="sxs-lookup"><span data-stu-id="167fb-180">The following key aggregate measurements are available directly from the Invoice lines entity and are used as the basis of the content.</span></span>

| <span data-ttu-id="167fb-181">Entidade</span><span class="sxs-lookup"><span data-stu-id="167fb-181">Entity</span></span>        | <span data-ttu-id="167fb-182">Principais medidas agregadas</span><span class="sxs-lookup"><span data-stu-id="167fb-182">Key aggregate measurements</span></span> | <span data-ttu-id="167fb-183">Fonte de dados</span><span class="sxs-lookup"><span data-stu-id="167fb-183">Data source</span></span>                                 | <span data-ttu-id="167fb-184">Campo</span><span class="sxs-lookup"><span data-stu-id="167fb-184">Field</span></span>              | <span data-ttu-id="167fb-185">descrição</span><span class="sxs-lookup"><span data-stu-id="167fb-185">Description</span></span>                            |
|---------------|----------------------------|---------------------------------------------|--------------------|----------------------------------------|
| <span data-ttu-id="167fb-186">Linhas da fatura</span><span class="sxs-lookup"><span data-stu-id="167fb-186">Invoice lines</span></span> | <span data-ttu-id="167fb-187">Compra</span><span class="sxs-lookup"><span data-stu-id="167fb-187">Purchase</span></span>                   | <span data-ttu-id="167fb-188">VendInvoiceTrans</span><span class="sxs-lookup"><span data-stu-id="167fb-188">VendInvoiceTrans</span></span>                            | <span data-ttu-id="167fb-189">SUM(LineAmountMST)</span><span class="sxs-lookup"><span data-stu-id="167fb-189">SUM(LineAmountMST)</span></span> | <span data-ttu-id="167fb-190">O valor na moeda contábil.</span><span class="sxs-lookup"><span data-stu-id="167fb-190">The amount in the accounting currency.</span></span> |

<span data-ttu-id="167fb-191">A tabela a seguir mostra as principais medidas no conteúdo que são calculadas a partir da entidade de linhas da fatura.</span><span class="sxs-lookup"><span data-stu-id="167fb-191">The following table shows the key measurements in the content that are calculated from the Invoice lines entity.</span></span>

| <span data-ttu-id="167fb-192">Medição</span><span class="sxs-lookup"><span data-stu-id="167fb-192">Measure</span></span>               | <span data-ttu-id="167fb-193">Cálculo</span><span class="sxs-lookup"><span data-stu-id="167fb-193">Calculation</span></span>                                                                                         |
|-----------------------|-----------------------------------------------------------------------------------------------------|
| <span data-ttu-id="167fb-194">Ano atual de compra</span><span class="sxs-lookup"><span data-stu-id="167fb-194">Purchase current year</span></span> | <span data-ttu-id="167fb-195">Ano atual de compra = SUM('Invoice lines'\[Purchase\])</span><span class="sxs-lookup"><span data-stu-id="167fb-195">Purchase current year = SUM('Invoice lines'\[Purchase\])</span></span>                                            |
| <span data-ttu-id="167fb-196">Compras do ano passado</span><span class="sxs-lookup"><span data-stu-id="167fb-196">Purchase last year</span></span>    | <span data-ttu-id="167fb-197">Compras do último ano = CALCULATE(SUM('Invoice lines'\[Purchase\]), SAMEPERIODLASTYEAR(Dates\[Date\]))</span><span class="sxs-lookup"><span data-stu-id="167fb-197">Purchase last year = CALCULATE(SUM('Invoice lines'\[Purchase\]), SAMEPERIODLASTYEAR(Dates\[Date\]))</span></span> |
| <span data-ttu-id="167fb-198">Crescimento de compra de YOY</span><span class="sxs-lookup"><span data-stu-id="167fb-198">YOY purchase growth</span></span>   | <span data-ttu-id="167fb-199">Crescimento de compra de YOY = \[Purchase current year\] – \[Purchase last year\]</span><span class="sxs-lookup"><span data-stu-id="167fb-199">YOY purchase growth = \[Purchase current year\] – \[Purchase last year\]</span></span>                            |

<span data-ttu-id="167fb-200">As principais dimensões a seguir no conteúdo são usadas como filtros para cortar as medidas agregadas, para que você possa alcançar mais granularidade e uma introspecção analítica mais profunda.</span><span class="sxs-lookup"><span data-stu-id="167fb-200">The following key dimensions in the content are used as filters to slice the aggregate measurements, so that you can achieve more granularity and gain deeper analytical insights.</span></span>

| <span data-ttu-id="167fb-201">Entidade</span><span class="sxs-lookup"><span data-stu-id="167fb-201">Entity</span></span>                 | <span data-ttu-id="167fb-202">Exemplos de atributos</span><span class="sxs-lookup"><span data-stu-id="167fb-202">Examples of attributes</span></span>                                |
|------------------------|-------------------------------------------------------|
| <span data-ttu-id="167fb-203">Fornecedores</span><span class="sxs-lookup"><span data-stu-id="167fb-203">Vendors</span></span>                | <span data-ttu-id="167fb-204">Grupos de fornecedores, país ou regiões do fornecedor, nome do fornecedor</span><span class="sxs-lookup"><span data-stu-id="167fb-204">Vendor groups, Vendor country or regions, Vendor name</span></span> |
| <span data-ttu-id="167fb-205">Produtos</span><span class="sxs-lookup"><span data-stu-id="167fb-205">Products</span></span>               | <span data-ttu-id="167fb-206">Número do produto, nome do produto, nome do grupo de item</span><span class="sxs-lookup"><span data-stu-id="167fb-206">Product number, Product name, Item groups name</span></span>        |
| <span data-ttu-id="167fb-207">Categorias de compras</span><span class="sxs-lookup"><span data-stu-id="167fb-207">Procurement categories</span></span> | <span data-ttu-id="167fb-208">Categoria de compras, nomes da categoria de compras</span><span class="sxs-lookup"><span data-stu-id="167fb-208">Procurement category, Procurement category names</span></span>      |
| <span data-ttu-id="167fb-209">Entidades legais</span><span class="sxs-lookup"><span data-stu-id="167fb-209">Legal entities</span></span>         | <span data-ttu-id="167fb-210">Nome da entidade legal</span><span class="sxs-lookup"><span data-stu-id="167fb-210">Legal entity name</span></span>                                     |
| <span data-ttu-id="167fb-211">Datas</span><span class="sxs-lookup"><span data-stu-id="167fb-211">Dates</span></span>                  | <span data-ttu-id="167fb-212">Datas, Compensação anual</span><span class="sxs-lookup"><span data-stu-id="167fb-212">Dates, Year offset</span></span>                                    |

<span data-ttu-id="167fb-213">Por padrão, o conteúdo exibe dados do ano atual.</span><span class="sxs-lookup"><span data-stu-id="167fb-213">By default, the content shows data for the current calendar year.</span></span> <span data-ttu-id="167fb-214">Entretanto, poderá modificar o filtro de data na seção filtros de relatório.</span><span class="sxs-lookup"><span data-stu-id="167fb-214">However, you can change the date filter in the report filters section.</span></span> <span data-ttu-id="167fb-215">Você também pode alterar o filtro da empresa.</span><span class="sxs-lookup"><span data-stu-id="167fb-215">You can also change the company filter.</span></span>
