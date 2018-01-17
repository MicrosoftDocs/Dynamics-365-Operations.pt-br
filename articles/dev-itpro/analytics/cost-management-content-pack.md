---
title: "Conteúdo do BI Gerenciamento de custo"
description: "Este tópico descreve o que está incluído no conteúdo do Power BI Gerenciamento de custo."
author: YuyuScheller
manager: AnnBe
ms.date: 12/19/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Operations
ms.custom: 270314
ms.assetid: 9680d977-43c8-47a7-966d-2280ba21402a
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: cb43245afe578341251b140383a3b03ba2abd962
ms.openlocfilehash: e0f9042b2647a484a70670d1d29e8036401b39f1
ms.contentlocale: pt-br
ms.lasthandoff: 12/19/2017

---

# <a name="cost-management-power-bi-content"></a>Conteúdo do BI Gerenciamento de custo

[!include[banner](../includes/banner.md)]


Este tópico descreve o que está incluído no conteúdo do Power BI Gerenciamento de custo. 

# <a name="overview"></a>Visão Geral

O conteúdo do Microsoft Power BI **Gerenciamento de custo** destina-se a contadores de estoque ou indivíduos na organização que são responsáveis pelo estoque. O conteúdo do Power BI **Gerenciamento de custo** fornece uma visão administrativa sobre o estoque e estoque WIP (work-in-progress, trabalho em progresso) e como o custo flui por meio deles por categoria com o passar do tempo. As informações também podem ser usadas como um suplemento detalhado para o demonstrativo financeiro.

## <a name="key-measures"></a>Principais medidas

+ Saldo inicial
+ Saldo final
+ Alteração líquida
+ Alteração líquida em %
+ Classificação por vencimento

## <a name="key-performance-indicators"></a>Indicadores chave de desempenho
+ Giro de estoque
+ Precisão do estoque

A fonte de dados primária para CostAggregatedCostStatementEntryEntity é a tabela CostStatementCache. Essa tabela é gerenciada pela estrutura de cache de conjunto de dados. Por padrão, ela é atualizada a cada 24 horas, mas você pode habilitar atualizações manuais na configuração de cache de dados. Depois você pode fazer uma atualização manual no espaço de trabalho **Gerenciamento de custo** ou **Análise de custo**. Depois que a atualização de CostStatementCache é executada, você deve atualizar a conexão OData em PowerBI.com para ver os dados atualizados no site. As medições de variação (compra, produção) no conteúdo do Power BI pertencem apenas a itens avaliados pelo método de estoque de custo padrão. A variação de produção é calculada como a diferença entre os custos ativos e os realizados. A variação de produção é calculada quando a ordem de produção possui um status de **Concluída**. Para obter mais informações sobre tipos de variação de produção e como cada tipo é calculado, consulte [Sobre a análise de variações para uma ordem de produção concluída](https://technet.microsoft.com/en-us/library/gg242850.aspx).


## <a name="metrics-that-are-included-in-the-power-bi-content"></a>Métricas incluídas no conteúdo do Power BI
O conteúdo inclui um conjunto de páginas de relatório. Cada página consiste em um conjunto de métricas visualizadas, como gráficos, blocos e tabelas. A seguinte tabela fornece uma visão geral das visualizações no conteúdo do Power BI **Gerenciamento de custo**.

| Página de relatório | Gráficos | Títulos |
|---|---|---|
|Estoque geral (padrão por período atual) |Precisão |Medidas de estoque:<br>Saldo final de estoque<br>Alteração líquida de estoque<br>Alteração líquida de estoque em %<br>|
| |Giro de estoque | |
| |Saldo final de estoque por grupo de recursos | |
| |Alteração líquida de estoque por nome de categoria de nível 1 e nome de categoria de nível 2| |
| |Variações de compra por grupo de recursos e nome de categoria de nível 3 | |
|Estoque por site (padrão por período atual) |Saldo final de estoque por nome de site e grupo de recursos | |
| |Giro de estoque por nome de site e grupo de recursos | |
| |Saldo final de estoque por cidade e grupo de recursos | |
|Estoque por grupo de recursos (padrão por período atual) |Medidas de estoque | |
| |Precisão do estoque por valor por grupo de recursos | |
| |Giro de estoque por valor por grupo de recursos | |
|YOY de estoque (ano atual padrão vs. ano anterior) |Medidas de estoque | |
| |KPIs de estoque:<br>Giro de estoque<br>Precisão do estoque | |
| |Saldo final de estoque por ano e grupo de recursos | |
| |Variações de compra por ano e nome de categoria de nível 3 | |
|Classificação por vencimento do estoque (padrão por ano atual) |Classificação por vencimento do estoque por trimestre e grupo de recursos | |
| |Classificação por vencimento do estoque por trimestre e nome de site | |
|WIP geral (padrão por período atual) |Alteração líquida WIP por nome de categoria de nível 1 e nome de categoria de nível 2 |Medidas WIP (trabalho em progresso):<br>Saldo final WIP<br>Alteração líquida WIP<br>Alteração líquida WIP em %<br> |
| |Variações de produção por grupo de recursos e nome de categoria de nível 3 | |
| |Alteração líquida WIP por grupo de recursos | |
|WIP por site (padrão por período atual) |Medidas WIP (trabalho em progresso) | |
| |Alteração líquida WIP por nome de site e nome de categoria de nível 2 | |
| |Variações de produção por nome do site e nome de categoria de nível 3 | |

## <a name="understanding-the-data-model-and-entities"></a>Noções básicas sobre o modelo de dados e as entidades
Os dados do Finance and Operations são usados para preencher as páginas do relatório no conteúdo do Power BI **Gerenciamento de custo**. Esses dados são representados como medições agregadas que são preparadas na loja Entidade, que é um banco de dados Microsoft SQL otimizado para análise. Para obter mais informações, consulte [Visão geral da integração do Power BI com a loja Entidade](power-bi-integration-entity-store.md). As principais medidas agregadas a seguir são usadas como base do conteúdo.

| Entidade            | Principal medida agregada | A fonte de dados para o Finance and Operations | Campo             | descrição                       |
|-------------------|---------------------------|---------------------------------------------|-------------------|-----------------------------------|
| Entradas de demonstrativo | Alteração líquida                | CostAggregatedCostStatementEntryEntity      | sum(\[Valor\])   | Valor na moeda contábil |
| Entradas de demonstrativo | Valor de alteração líquida       | CostAggregatedCostStatementEntryEntity      | sum(\[Quantidade\]) |                                   |

A tabela a seguir mostra como as principais medidas agregadas são usadas para criar diversas medidas calculadas no conjunto de dados do conteúdo.

| Medição                                 | Como a medida é calculada                                                                                                                                                                                                                                                                                                                                                                                                                                              |
|-----------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Saldo inicial                       | \[Saldo final\]-\[Alteração líquida\]                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| Valor do saldo inicial              | \[Valor do saldo inicial\]-\[Valor de alteração líquida\]                                                                                                                                                                                                                                                                                                                                                                                                                        |
| Saldo final                          | CALCULATE(SUM(\[Valor\]), FILTER(ALLEXCEPT('Calendários fiscais', 'Calendários fiscais'\[LedgerRecId\], 'entidades'\[ID\], 'entidades'\[Nome\], 'Razões'\[Moeda\], 'Razões'\[Descrição\], 'Razões'\[Nome\]), 'Calendários fiscais'\[Data\] &lt;= MAX('Calendários fiscais'\[Data\])))                                                                                                                                                                                           |
| Quantidade do saldo final                 | CALCULATE(SUM(\[Quantidade\]), FILTER(ALLEXCEPT('Calendários fiscais', 'Calendários fiscais'\[LedgerRecId\], 'entidades'\[ID\], 'entidades'\[Nome\], 'Razões'\[Moeda\], 'Razões'\[Descrição\], 'Razões'\[Nome\]), 'Calendários fiscais'\[Data\] &lt;= MAX('Calendários fiscais'\[Data\])))                                                                                                                                                                                         |
| Saldo inicial de estoque             | CALCULATE(\[Saldo inicial\], 'Entradas de demonstrativo'\[Tipo de instrução\] = "Estoque")                                                                                                                                                                                                                                                                                                                                                                                      |
| Saldo final de estoque                | CALCULATE(\[Saldo final\], 'Entradas de demonstrativo'\[Tipo de instrução\] = "Estoque")                                                                                                                                                                                                                                                                                                                                                                                         |
| Alteração líquida de estoque                    | CALCULATE(\[Alteração líquida\], 'Entradas de demonstrativo'\[Tipo de demonstrativo\] = "Estoque")                                                                                                                                                                                                                                                                                                                                                                                             |
| Quantidade de alteração líquida de estoque           | CALCULATE(\[Quantidade de alteração líquida\], 'Entradas de demonstrativo'\[Tipo de demonstrativo\] = "Estoque")                                                                                                                                                                                                                                                                                                                                                                                    |
| Alteração líquida de estoque em %                  | IF(\[Saldo final de estoque\] = 0, 0, \[Alteração líquida de estoque\] / \[Saldo final de estoque\])                                                                                                                                                                                                                                                                                                                                                                           |
| Giro de estoque por valor                | if(OR(\[Saldo médio de estoque\] &lt;= 0, \[Problemas de estoque vendido ou consumido\] &gt;= 0), 0, ABS(\[Problemas de estoque vendido ou consumido\])/\[Saldo médio de estoque\])                                                                                                                                                                                                                                                                                                  |
| Saldo médio de estoque               | (\[Saldo final de estoque\] + \[Saldo inicial de estoque\]) / 2                                                                                                                                                                                                                                                                                                                                                                                                       |
| Problemas de estoque vendido ou consumido       | \[Estoque vendido\] + \[Custo material de estoque consumido\]                                                                                                                                                                                                                                                                                                                                                                                                                  |
| Custo material de estoque consumido        | CALCULATE(\[Alteração líquida de estoque\], 'Entradas de demonstrativo'\[Nome de categoria - nível 2\_\] = "ConsumedMaterialsCost")                                                                                                                                                                                                                                                                                                                                                            |
| Estoque vendido                          | CALCULATE(\[Alteração líquida de estoque\], 'Entradas de demonstrativo'\[Nome de categoria - nível 2\_\] = "Vendido")                                                                                                                                                                                                                                                                                                                                                                             |
| Precisão do estoque por valor            | IF(\[Saldo final de estoque\] &lt;= 0, IF(OR(\[Valor contado de estoque\] &lt;&gt; 0, \[Saldo final de estoque\] &lt; 0), 0, 1), MAX(0, (\[Saldo final de estoque\] - ABS(\[Valor contado de estoque\]))/\[Saldo final de estoque\]))                                                                                                                                                                                                                              |
| Valor contado de estoque                | CALCULATE(\[Alteração líquida de estoque\], 'Entradas de demonstrativo'\[Nome de categoria - nível 3\_\] = "Contagem")                                                                                                                                                                                                                                                                                                                                                                         |
| Classificação por vencimento do estoque                         | if(ISBLANK(max('Calendários fiscais'\[Data\])), blank(), MAX(0, MIN(\[Valor de recibos de classificação por vencimento do estoque\], \[Valor de saldo de classificação por vencimento do estoque\] - \[Valor de recibos de classificação por vencimento do estoque no futuro\]))) \* \[Custo de unidade de classificação por vencimento do estoque\]                                                                                                                                                                                                                                |
| Valor de recibos de classificação por vencimento do estoque       | IF(\[minDate\] = \[minDateAllSelected\], CALCULATE(\[Quantidade de alteração líquida de estoque\], 'Entradas de demonstrativo'\[Quantidade\] &gt; 0, FILTER(ALLEXCEPT('Calendários fiscais', 'Calendários fiscais'\[LedgerRecId\], 'entidades'\[ID\], 'entidades'\[Nome\], 'Razões'\[Moeda\], 'Razões'\[Descrição\], 'Razões'\[Nome\]), 'Calendários fiscais'\[Data\] &lt;= MAX('Calendários fiscais'\[Data\]))), CALCULATE(\[Inventory net change quantity\], 'Entradas de demonstrativo'\[Quantidade\] &gt; 0)) |
| Valor de saldo final de classificação por vencimento do estoque | \[Valor de saldo final de estoque\] + CALCULATE(\[Quantidade de alteração líquida de estoque\], FILTER(ALLEXCEPT('Calendários fiscais', 'Calendários fiscais'\[LedgerRecId\], 'entidades'\[ID\], 'entidades'\[Nome\], 'Razões'\[Moeda\], 'Razões'\[Descrição\], 'Razões'\[Nome\]), 'Calendários fiscais'\[Data\] &gt; max('Calendários fiscais'\[Data\]) ))                                                                                                                                 |
| Recibos de classificação por vencimento do estoque no futuro  | CALCULATE(\[Alteração líquida de estoque\], 'Entradas de demonstrativo'\[Valor\] &gt; 0, FILTER(ALLEXCEPT('Calendários fiscais', 'Calendários fiscais'\[LedgerRecId\], 'entidades'\[ID\], 'entidades'\[Nome\], 'Razões'\[Moeda\], 'Razões'\[Descrição\], 'Razões'\[Nome\]), 'Calendários fiscais'\[Data\] &gt; MAX('Calendários fiscais'\[Data\])))                                                                                                                                             |
| Custo de unidade de classificação por vencimento do estoque                 | CALCULATE(\[Saldo final de estoque\] / \[Valor de saldo final de estoque\],ALLEXCEPT('Calendários fiscais', 'Calendários fiscais'\[LedgerRecId\], 'entidades'\[ID\], 'entidades'\[Nome\], 'Razões'\[Moeda\], 'Razões'\[Descrição\], 'Razões'\[Nome\]))                                                                                                                                                                                                                 |
| Variações de compra                      | CALCULATE(SUM(\[Valor\]), 'Entradas de demonstrativo'\[Categoria de nome - nível 2\_\] = "Adquirido", 'Entradas de demonstrativo'\[Tipo de demonstrativo\] = "Variação")                                                                                                                                                                                                                                                                                                                              |
| Saldo inicial WIP                   | CALCULAR(\[Saldo inicial\], 'Entradas de demonstrativo'\[Tipo de instrução\] = "WIP")                                                                                                                                                                                                                                                                                                                                                                                            |
| Saldo final WIP                      | CALCULATE(\[Saldo final\], 'Entradas de demonstrativo'\[Tipo de instrução\] = "WIP")                                                                                                                                                                                                                                                                                                                                                                                               |
| Alteração líquida WIP                          | CALCULATE(\[Alteração líquida\], 'Entradas de demonstrativo'\[Tipo de demonstrativo\] = "WIP")                                                                                                                                                                                                                                                                                                                                                                                                   |
| Alteração líquida WIP em %                        | IF(\[Saldo final WIP\] = 0, 0, \[Alteração líquida WIP\] / \[Saldo final WIP\])                                                                                                                                                                                                                                                                                                                                                                                             |
| Variações de produção                    | CALCULATE(SUM(\[Valor\]), 'Entradas de demonstrativo'\[Categoria de nome - nível 2\_\] = "ManufacturedCost", 'Entradas de demonstrativo'\[Tipo de demonstrativo\] = "Variação")                                                                                                                                                                                                                                                                                                                      |
| Nome de categoria - nível 1                 | switch(\[Nome de categoria - nível 1\_\], "Nenhum(a)", "Nenhum(a)", "NetSourcing", "Fornecimento líquido", "NetUsage", "Uso líquido", "NetConversionCost", "Custo líquido da conversão", "NetCostOfGoodsManufactured", "Custo líquido dos produtos manufaturados", "BeginningBalance", "Saldo inicial")                                                                                                                                                                                                         |
| Nome de categoria - nível 2                 | switch(\[Nome de categoria - nível 2\_\], "Nenhum(a)", "Nenhum(a)", "Adquirido", "Adquirido", "Alienado", "Alienado", "Transferido", "Transferido", "Vendido", "Vendido", "ConsumedMaterialsCost", "Custo material consumido", "ConsumedManufacturingCost", "Custo de fabricação consumido", "ConsumedOutsourcingCost", "Custo de terceirização consumido", "ConsumedIndirectCost", "Custo indireto consumido", "ManufacturedCost", "Custo de fabricação", "Variações", "Variações")                            |
| Nome de categoria - nível 3                 | switch(\[Nome de categoria - nível 3\_\], "Nenhum(a)", "Nenhum(a)", "Contagem", "Nenhum(a)", "ProductionPriceVariance", "Preço de produção", "QuantityVariance", "Quantidade", "SubstitutionVariance", "Substituição", "ScrapVariance", "Sucata", "LotSizeVariance", "Tamanho do lote", "RevaluationVariance", "Reavaliação", "PurchasePriceVariance", "Preço de compra", "CostChangeVariance", "Alteração de custo", "RoundingVariance", "Variação de arredondamento")                                                   |

As principais dimensões a seguir são usadas como filtros para cortar as medidas agregadas para obter uma granularidade maior e fornecer uma introspecção analítica mais profunda.

| Entidade           | Exemplos de atributos                       |
|------------------|----------------------------------------------|
| Entidades         | ID, nome                                     |
| Calendários fiscais | Calendário, mês, período, trimestre, ano       |
| Metas de KPI        | Meta de precisão de estoque, meta de giro de estoque |
| Razões          | Moeda, nome, descrição                  |
| Locais            | ID, nome, país, cidade                      |






