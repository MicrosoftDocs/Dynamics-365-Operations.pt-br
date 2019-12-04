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
# <a name="purchase-spend-analysis-power-bi-content"></a>Conteúdo de análise de gastos em compras do Power BI

[!include [banner](../includes/banner.md)]

Este tópico descreve o que está incluído no conteúdo do Microsoft Power BI de **análise de gastos da compra**. Ele explica como acessar os relatórios do Power BI e fornece informações sobre o modelo de dados e entidades que são usados para criar o conteúdo.

## <a name="overview"></a>Visão Geral

O conteúdo do Power BI de **Análise de gastos da compra** foi desenvolvido para ajudar os gerentes de compras e os gerentes responsáveis por orçamentos a acompanhar os gastos de compra. Os gerentes podem analisar os gastos de compra das seguintes maneiras:

- Compra de um ano atrás até agora (por grupo de fornecedor e fornecedores individuais, categoria de compras e produtos individuais e local de fornecedor)
- Alteração de compra de um ano atrás até agora (por grupo de fornecedor e categoria de compras)

O conteúdo usa dados transacionais de compra e fornece uma visão agregada dos números de compra da empresa e uma repartição dos gastos de compra por fornecedor e produto. Os relatórios destacam as alterações no gasto em compras ao longo do tempo. Portanto, os relatórios podem ser usados para alertar gerentes sobre tendências positivas e negativas de gastos para fornecedores individuais e produtos. Além disso, gráficos mostram gasto em compras para categorias de compras diferentes e grupos de fornecedores. Portanto, a categoria e os gerentes regionais podem usar os gráficos para ajudar a identificar mudanças nos comportamentos de gastos.

## <a name="accessing-the-power-bi-content"></a>Acessando o conteúdo do Power BI
O conteúdo do Power BI de **Análise de gasto em compras** é exibido na página **Análise de compra e de gastos** (**Compras e fornecimento** \> **Consultas e relatórios** \> **Análise de desempenho de compra** \> **Análise de compra e de gastos**).

## <a name="metrics-that-are-included-in-the-power-bi-content"></a>Métricas incluídas no conteúdo do Power BI
O conteúdo de Power BI de **Análise de gastos da compra** inclui um relatório que consiste em um grupo de métricas. Estas métricas são visualizadas como gráficos, blocos e tabelas. 

As seções a seguir fornecem uma visão geral das visualizações.

### <a name="purchase-by-vendor-report-page"></a>Compra por página de relatórios de fornecedor
**Gráficos**
- 10 principais fornecedores por compra (gráfico de barra empilhada)
- Compra total por grupo de fornecedor/país/nome (gráfico de pizza)
- Compra por grupo de fornecedor/país/nome (gráfico de coluna)
- Compra média por grupo de fornecedor/país/nome (gráfico de coluna)

**Blocos**
- Total da Compra
- Crescimento de compra de YOY
- Número total de fornecedores
- Número total de fornecedores ativos

**Exemplo**
<img src="media/spend1.png" alt="Purchase by vendor">

### <a name="purchase-by-product-report-page"></a>Compra por página de relatórios de produto

**Gráficos**
- Compra por categoria de itens/nome do produto (gráfico de coluna)
- Compra total por categoria de itens/nome do produto (gráfico de pizza)
- 10 principais produtos por compra (gráfico de barra empilhada)

**Blocos**
- Número total de produtos</li>
- Porcentagem de produtos ativos total do número total de produtos
- Número da contabilidade de produtos para compra de 80%

**Exemplo**


<img src="media/purchaseByProduct.png" alt="Purchase by Product">

### <a name="purchase-by-period-report-page"></a>Compra por página de relatórios de período
Essa página exibe compras este ano e no ano passado e crescimento por categoria de compra.

**Gráficos** 
- Compra por mês/dia (gráfico de coluna)
- Variação de YOY de compra cumulativa (gráfico de cascata)
- Crescimento de YOY total da compra (gráfico de coluna)
- Demonstrativo de compras (matriz)

**Blocos**
- Crescimento de compra de YOY
- Porcentagem de crescimento de compra de YOY

**Exemplo**
<img src="media/purchaseByPeriod.png" alt="Purchase by Period">

### <a name="purchase-by-vendor-location-report-page"></a>Compra por página de relatórios locais de fornecedor

**Gráficos**
- Compra por cidade
- Porcentagem de crescimento de YOY de compra
- Compra por país

**Exemplo**
<img src="media/purchByVendorLocation.png" alt="Purchase by Vendor Location">

### <a name="purchase-spend-analysis-by-time-report-page"></a>Análise de gastos de compra por página de relatório de hora

**Gráficos** 
- Ano atual de compra em mês/dia (gráfico de linha)
- Compra atual e do último ano (gráfico de linha e coluna)

**Exemplo**
<img src="media/PurchByTIme.png" alt="Purchase by Time">

### <a name="purchase-spend-analysis-by-vendor-report-page"></a>Análise de gastos de compra por página de relatório de fornecedor

**Gráficos** 
- 10 principais porcentagens de compra de fornecedor (funil)
- 10 principais fornecedores com gasto elevado de YOY
- 10 principais fornecedores com gasto diminuído de YOY

**Exemplo** 
<img src="media/PurchSpendAnalysisByVendor.png" alt="Purchase spend by vendor">


## <a name="data-model-and-entities"></a>Modelo de dados e entidades
Os seguintes dados são usados para preencher as páginas de relatório no conteúdo do Power BI **Análise de gastos da compra**. Esses dados são representadas como medições agregadas que foram preparadas no Repositório de entidades. O Repositório de entidades é um banco de dados do Microsoft SQL Server otimizado para análise. Para obter mais informações, consulte [Integração do Power BI com o repositório Entidade](power-bi-integration-entity-store.md).

As medidas agregadas neste conteúdo são o subconjunto de medidas agregadas que estavam disponíveis no Cubo de Compras no Microsoft Dynamics AX 2012 e no Microsoft Dynamics AX 2012 R3. Para preparar as medidas agregadas do cubo na loja Entidade, você deve torná-las implementáveis. Para obter mais informações, consulte o procedimento sobre como preparar medidas agregadas no repositório Entidade em [Integração do Power BI com o repositório Entidade](power-bi-integration-entity-store.md). As principais medidas agregadas a seguir estão disponíveis diretamente nas entidade de linhas de fatura e são usadas como base do conteúdo.

| Entidade        | Principais medidas agregadas | Fonte de dados                                 | Campo              | descrição                            |
|---------------|----------------------------|---------------------------------------------|--------------------|----------------------------------------|
| Linhas da fatura | Compra                   | VendInvoiceTrans                            | SUM(LineAmountMST) | O valor na moeda contábil. |

A tabela a seguir mostra as principais medidas no conteúdo que são calculadas a partir da entidade de linhas da fatura.

| Medição               | Cálculo                                                                                         |
|-----------------------|-----------------------------------------------------------------------------------------------------|
| Ano atual de compra | Ano atual de compra = SUM('Invoice lines'\[Purchase\])                                            |
| Compras do ano passado    | Compras do último ano = CALCULATE(SUM('Invoice lines'\[Purchase\]), SAMEPERIODLASTYEAR(Dates\[Date\])) |
| Crescimento de compra de YOY   | Crescimento de compra de YOY = \[Purchase current year\] – \[Purchase last year\]                            |

As principais dimensões a seguir no conteúdo são usadas como filtros para cortar as medidas agregadas, para que você possa alcançar mais granularidade e uma introspecção analítica mais profunda.

| Entidade                 | Exemplos de atributos                                |
|------------------------|-------------------------------------------------------|
| Fornecedores                | Grupos de fornecedores, país ou regiões do fornecedor, nome do fornecedor |
| Produtos               | Número do produto, nome do produto, nome do grupo de item        |
| Categorias de compras | Categoria de compras, nomes da categoria de compras      |
| Entidades legais         | Nome da entidade legal                                     |
| Datas                  | Datas, Compensação anual                                    |

Por padrão, o conteúdo exibe dados do ano atual. Entretanto, poderá modificar o filtro de data na seção filtros de relatório. Você também pode alterar o filtro da empresa.
