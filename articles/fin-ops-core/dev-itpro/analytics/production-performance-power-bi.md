---
title: Conteúdo de desempenho da produção do Power BI
description: Este tópico descreve o que está incluído no conteúdo do Power BI Desempenho de produção. Ele explica como acessar os relatórios do Power BI e fornece informações sobre o modelo de dados e entidades que foram usados para criar o conteúdo.
author: AndersGirke
manager: AnnBe
ms.date: 12/19/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ProductionPerformancePowerBI
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: aevengir
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 0dc71f819f132b91fe153f83089eab24fa33173a
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/06/2019
ms.locfileid: "2772479"
---
# <a name="production-performance-power-bi-content"></a>Conteúdo de desempenho da produção do Power BI

[!include [banner](../includes/banner.md)]

Este tópico descreve o que está incluído no conteúdo do Microsoft Power BI **Desempenho de produção**. Ele explica como acessar os relatórios do Power BI e fornece informações sobre o modelo de dados e entidades que foram usados para criar o conteúdo.

## <a name="overview"></a>Visão Geral

O conteúdo do Power BI **Desempenho de produção** destina-se a gerentes de produção ou indivíduos na organização responsáveis ​​pelo controle de produção.

Os relatórios que estão incluídos permitem que você use o Power BI para monitorar o desempenho das operações de fabricação em relação a execução, qualidade e custo. Os relatórios usam dados transacionais de ordens de produção e ordens por lotes e fornecem uma visão agregada das métricas de produção de toda a empresa e uma quebra de métricas por produto e recurso.

O conteúdo do Power BI destaca a capacidade da organização de completar a produção a tempo e na íntegra. O desempenho futuro é projetado com base nos planos de produção. Relatórios abrangentes fornecem informações detalhadas sobre os defeitos do produto causados ​​pela produção e também as taxas de defeito para recursos e operações.

O conteúdo do Power BI também permite analisar as variações de produção. A variação de produção é calculada como a diferença entre os custos ativos e os realizados. As variações de produção são calculadas quando as ordens de produção ou ordens de lote atingem o status **Finalizado**.

O conteúdo do Power BI **Desempenho de produção** contém dados que se originam de ordens de produção e de ordens de lotes. Os relatórios não incluem dados relacionados às produções de Kanban.

## <a name="accessing-the-power-bi-content"></a>Acessando o conteúdo do Power BI
O conteúdo do Power BI de **Desempenho da produção** é exibido na página **Desempenho da produção** (**Controle de produção** \> **Consultas e relatórios** \> **Análise do desempenho da produção** \> **Desempenho da produção**). 

## <a name="metrics-that-are-included-in-the-power-bi-content"></a>Métricas incluídas no conteúdo do Power BI

O conteúdo do Power BI **Desempenho de produção** inclui um conjunto de páginas do relatório. Cada página consiste em um conjunto de métricas visualizadas, como gráficos, blocos e tabelas.

A tabela a seguir fornece uma visão geral das visualizações incluídas.

| Página de relatório                                | Gráficos | Blocos |
|--------------------------------------------|--------|-------|
| Desempenho da produção                     | <ul><li>Número de produção por data</li><li>Número de produções por produto e grupo de itens</li><li>Número de produções planejadas por data</li><li>10 piores produtos por prazo e totalidade</li></ul> | <ul><li>Total de ordens</li><li>No prazo e na totalidade</li><li>Incompleto %</li><li>Antecipada %</li><li>Atrasado %</li></ul> |
| Defeitos por produto                         | <ul><li>Taxa defeituosa (ppm) por data</li><li>Taxa defeituosa (ppm) por produto e grupo de itens</li><li>Quantidade produzida por data</li><li>10 melhores produtos por taxa efetiva</li></ul> | <ul><li>Taxa defeituosa (ppm)</li><li>Quantidade com defeito</li><li>Quantidade total</li></ul> |
| Tendência de defeitos por produto                   | Taxa de defeito (ppm) por quantidade produzida | Taxa de defeito (ppm) |
| Defeitos por recurso                        | <ul><li>Taxa de defeito (ppm) por data</li><li>Taxa de defeito (ppm) por recurso e site</li><li>Taxa de defeito (ppm) por operação</li><li>10 principais recursos por taxa de defeito</li></ul> | Quantidade com defeito |
| Tendência de defeitos por recurso                  | Taxa de defeito (ppm) por quantidade processada | |
| Variações de produção para os custos de ordem de produção | <ul><li>Variação de produção por data e tipo de grupo de custo</li><li>Variação de produção por site e tipo de grupo de custo</li><li>Os 10 melhores produtos com variação de produção desfavorável</li><li>As 10 principais variações de produção desfavoráveis por recurso</li></ul> | <ul><li>Custo realizado</li><li>Variação de produção</li><li>Variação de produção %</li></ul> |


## <a name="understanding-the-data-model-and-entities"></a>Noções básicas sobre o modelo de dados e as entidades

Os seguintes dados são usados para as páginas de relatório no conteúdo do Power BI **Desempenho de produção**. Esses dados são representadas como medições agregadas que foram preparadas no Repositório de entidades. O Repositório de entidades é um banco de dados do Microsoft SQL Server otimizado para análise. Para saber mais sobre o repositório de entidades, consulte [Integração do Power BI com o repositório Entidade](power-bi-integration-entity-store.md).

A tabela a seguir mostra as principais medidas agregadas que são usadas como base do conteúdo do Power BI.

| Entidade                   | Principais medidas agregadas  | Fonte de dados para os aplicativos do Finance and Operations | Campo              |
|--------------------------|-----------------------------|----------------------------------------|--------------------|
| CostCalculation          | CostAmount                  | ProdCalcTransExpanded                  | CostAmount         |
| CostCalculation          | CostMarkup                  | ProdCalcTransExpanded                  | CostMarkup         |
| CostCalculation          | ActualCostAmount            | ProdCalcTransExpanded                  | RealCostAmount     |
| CostCalculation          | RealCostAdjustment          | ProdCalcTransExpanded                  | RealCostAdjustment |
| RouteTransactions        | ErrorQuantity               | ProdRouteTransExpanded                 | QtyError           |
| RouteTransactions        | GoodQuantity                | ProdRouteTransExpanded                 | QtyGood            |
| ProductionOrder          | DaysDelayed                 | ProdTableExpanded                      | DaysDelayed        |
| ProductionOrder          | LeadTime                    | ProdTableExpanded                      | LeadTime           |
| ProductionOrder          | PlannedLeadTime             | ProdTableExpanded                      | PlannedLeadTime    |
| ProductionOrder          | ProductionOrderCount        | ProdTableExpanded                      |                    |
| CoproductCostCalculation | CoproductCostAmount         | PmfCoByProdCalcTransExpanded           | CostAmount         |
| CoproductCostCalculation | CoproductCostMarkup         | PmfCoByProdCalcTransExpanded           | CostMarkup         |
| CoproductCostCalculation | CoproductRealCostAdjustment | PmfCoByProdCalcTransExpanded           | RealCostAdjustment |
| CoproductCostCalculation | CoproductActualCostAmount   | PmfCoByProdCalcTransExpanded           | RealCostAmount     |

A tabela a seguir mostra como as principais medidas agregadas são usadas para criar diversas medidas calculadas no conjunto de dados do conteúdo.

| Medição                  | Como a medida é calculada |
|--------------------------|-------------------------------|
| Variação de produção %   | SUM('Variação de produção'\[Variação de produção\]) / SUM('Variação de produção'\[Custo estimado\]) |
| Todas as ordens planejadas       | COUNTROWS('Ordem de produção planejada') |
| Antecipada                    | COUNTROWS(FILTRO('Ordem de produção planejada', 'Ordem de produção planejada'\[Data de término planejada\] \< 'Ordem de produção planejada'\[Data do requisito\])) |
| Em atraso                     | COUNTROWS(FILTRO('Ordem de produção planejada', 'Ordem de produção planejada'\[Data de término planejada\] \> 'Ordem de produção planejada'\[Data do requisito\])) |
| No prazo                  | COUNTROWS(FILTER('Ordem de produção planejada', 'Ordem de produção planejada'\[Data de término planejada\] = 'Ordem de produção planejada'\[Data do requisito\])) |
| No prazo %                | IF ( 'Ordem de produção planejada'\[No prazo\] \<\> 0, 'Ordem de produção planejada'\[No prazo\], IF ('Ordem de produção planejada'\[Todas as ordens planejadas\] \<\> 0, 0, BLANK()) ) / 'Ordem de produção planejada'\[Todas as ordens planejadas\] |
| Concluída                | COUNTROWS(FILTRO('Ordem de produção', 'Ordem de produção'\[Is RAF'ed\] = TRUE)) |
| Taxa defeituosa (ppm)     | IF( 'Ordem de produção'\[Quantidade total\] = 0, BLANK(), (SUM('Ordem de produção'\[Quantidade com defeito\]) / 'Ordem de produção'\[Quantidade total\]) \* 1000000) |
| Taxa de produção em atraso  | 'Ordem de produção'\[Atrasada \#\] / 'Ordem de produção'\[Concluída\] |
| Antecipadamente e na totalidade          | COUNTROWS(FILTRO('Ordem de produção', 'Ordem de produção'\[Is in full\] = TRUE && 'Ordem de produção'\[Está antecipada\] = TRUE)) |
| Antecipada \#                 | COUNTROWS(FILTRO('Ordem de produção', 'Ordem de produção'\[Está antecipada\] = TRUE)) |
| Antecipada %                  | IFERROR( IF('Ordem de produção'\[Antecipada \#\] \<\> 0, 'Ordem de produção'\[Antecipada \#\], IF('Ordem de produção'\[Total de ordens\] = 0, BLANK(), 0)) / 'Ordem de produção'\[Total de ordens\], BLANK()) |
| Incompleto               | COUNTROWS(FILTRO('Ordem de produção', 'Ordem de produção'\[Está na totalidade\] = FALSE && 'Ordem de produção'\[Is RAF'ed\] = TRUE)) |
| Incompleto %             | IFERROR( IF('Ordem de produção'\[Incompleta\] \<\> 0, 'Ordem de produção'\[Incompleta\], IF('Ordem de produção'\[Total de ordens\] = 0, BLANK(), 0)) / 'Ordem de produção'\[Total de ordens\], BLANK()) |
| Está atrasada               | 'Ordem de produção'\[Is RAF'ed\] = TRUE && 'Ordem de produção'\[Valor atrasado\] = 1 |
| Está antecipado                 | 'Ordem de produção'\[Is RAF'ed\] = TRUE && 'Ordem de produção'\[Dias de atraso\] \< 0 |
| Está na totalidade               | 'Ordem de produção'\[Boa quantidade\] \>= 'Ordem de produção'\[Quantidade programada\] |
| É RAF'ed                | 'Ordem de produção'\[Valor de status de produção\] = 5 \|\| 'Ordem de produção'\[Valor de status de produção\] = 7 |
| Atrasado e na totalidade           | COUNTROWS(FILTER('Ordem de produção', 'Ordem de produção'\[Está na totalidade\] = TRUE && 'Ordem de produção'\[Está atrasada\] = TRUE)) |
| Atrasado \#                  | COUNTROWS(FILTRO('Ordem de produção', 'Ordem de produção'\[Está atrasada\] = TRUE)) |
| Atrasado %                   | IFERROR( IF('Ordem de produção'\[Atrasada \#\] \<\> 0, 'Ordem de produção'\[Atrasada \#\], IF('Ordem de produção'\[Total de ordens\] = 0, BLANK(), 0)) / 'Ordem de produção'\[Total de ordens\], BLANK()) |
| No prazo e na totalidade        | COUNTROWS(FILTRO('Ordem de produção', 'Ordem de produção'\[Está na totalidade\] = TRUE && 'Ordem de produção'\[Is delayed\] = FALSE && 'Ordem de produção'\[Está antecipada\] = FALSE)) |
| No prazo e na totalidade      | IFERROR( IF('Ordem de produção'\[No prazo e na totalidade\] \<\> 0, 'Ordem de produção'\[No prazo e na totalidade\], IF('Ordem de produção'\[Concluída\] = 0, BLANK(), 0)) / 'Ordem de produção'\[Concluída\], BLANK()) |
| Total de ordens             | COUNTROWS('Ordem de produção') |
| Quantidade total           | SUM('Ordem de produção'\[Boa quantidade\]) + SUM('Ordem de produção'\[Quantidade com defeito\]) |
| Taxa de defeito (ppm)        | IF( 'Transações de roteiro'\[Quantidade processada\] = 0, BLANK(), (SUM('Transações de roteiro'\[Quantidade com defeito\]) / 'Route transactions'\[Quantidade processada\]) \* 1000000) |
| Taxa mista de defeitos (ppm) | IF( 'Transações de roteiro'\[Quantidade total mista\] = 0, BLANK(), (SUM('Transações de roteiro'\[Quantidade com defeito\]) / 'Transações de roteiro'\[Quantidade total mista\]) \* 1000000) |
| Quantidade processada       | SUM('Transações de roteiro'\[Boa quantidade\]) + SUM('Transações de roteiro'\[Quantidade com defeito\]) |
| Quantidade mista total     | SUM('Ordem de produção'\[Boa quantidade\]) + SUM('Transações de roteiro'\[Quantidade com defeito\]) |

A tabela a seguir mostra as dimensões-chave que são usadas como filtros para cortar as medidas agregadas, para que você possa obter maior granularidade e obter informações analíticas mais profundas.

| Entidade                    | Exemplos de atributos                                        |
|---------------------------|---------------------------------------------------------------|
| Data do relatório de conclusão | Data de conclusão (RAF), mês e compensação de ano                 |
| Data de término                | Compensação e mês do mês encerrado                                  |
| Data da necessidade          | Compensação e data de requisito do mês da data de requisito            |
| Data de transação de roteiro    | Compensação e data do mês da transação de roteiro                       |
| Locais                     | ID de sites, nome do site, estado e cidade                          |
| Entidades                  | Id e nome                                                   |
| Recursos                 | ID do recurso, nome do recurso, tipo de recurso e grupo de recursos |
| Produtos                  | Número do produto, nome do produto, identificação do item e grupo de itens         |
