---
title: Conteúdo de gerenciamento de custos do Power BI
description: Este tópico descreve o que está incluído no conteúdo de gerenciamento de custos do Power BI.
author: ShylaThompson
ms.date: 03/16/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CostAdminWorkspace, CostAnalysisWorkspace, CostObjectWithLowestAccuracy, CostVarianceChart, CostObjectWithLowestTurn
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: 270314
ms.assetid: 9680d977-43c8-47a7-966d-2280ba21402a
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kfend
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 9fbdc6addc820aadc1f5469cb059a62724cfe905
ms.sourcegitcommit: 03fa7556840aa59f825697f6f9edeb58ea673fca
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2021
ms.locfileid: "7752631"
---
# <a name="cost-management-power-bi-content"></a>Conteúdo de gerenciamento de custos do Power BI

[!include [banner](../includes/banner.md)]

## <a name="overview"></a>Visão Geral

O conteúdo de **Gerenciamento de custos** do Microsoft Power BI destina-se a contadores de estoque ou às pessoas da organização responsáveis ou interessadas pelo status do estoque ou do WIP (trabalho em andamento) ou ainda a pessoas que sejam responsáveis ou tenham interesse na análise de variações de custo padrão.

Este conteúdo do Power BI fornece um formato categorizado que ajuda a monitorar o desempenho dos estoques e visualizar o fluxo de custos. Você pode ganhar insights gerenciais, como o índice de giro, o número de dias que o estoque está disponível, a precisão, e a "classificação ABC" ao nível agregado preferido (empresa, item, grupo de itens, ou o site). As informações disponibilizadas também podem ser usadas como um suplemento detalhado para o demonstrativo financeiro.

O conteúdo do Power BI é criado com base na medida agregada **CostObjectStatementCacheMonthly**, que tem a tabela **CostObjectStatementCache** como principal fonte de dados. Essa tabela é gerenciada pela estrutura de cache de conjunto de dados. Por padrão, ela é atualizada a cada 24 horas, mas você pode alterar a frequência ou habilitar atualizações manuais na configuração do cache de conjunto de dados. Atualizações manuais podem ser feitas no espaço trabalho **Administração de custo** ou no espaço de trabalho **Análise de custo** .

Após cada atualização da tabela **CostObjectStatementCache**, a medida agregada **CostObjectStatementCacheMonthly** deve ser atualizada antes da atualização dos dados nas visualizações do Power BI.

## <a name="accessing-the-power-bi-content"></a>Acessando o conteúdo do Power BI

O conteúdo de **Gerenciamento de custos** do Power BI é mostrado nos espaços trabalho **Administração de custos** e **Análise de custos**.

O espaço de trabalho **Administração de custo** contém as seguintes guias:

- **Visão geral** – esta guia mostra os dados do aplicativo.
- **Status da contabilidade de estoque** – esta guia mostra o conteúdo do Power BI.
- **Status da contabilidade de fabricação** – esta guia mostra o conteúdo do Power BI.

O espaço de trabalho **Análise de custo** contém as seguintes guias:

- **Visão geral** – esta guia mostra os dados do aplicativo.
- **Análise da contabilidade de estoque** – esta guia mostra o conteúdo do Power BI.
- **Análise da contabilidade de fabricação** – esta guia mostra o conteúdo do Power BI.
- **Análise da variação de custos padrão** – esta guia mostra o conteúdo do Power BI.

## <a name="report-pages-that-are-included-in-the-power-bi-content"></a>Páginas de relatório incluídas no conteúdo do Power BI

O conteúdo de **Gerenciamento de custos** do Power BI inclui um conjunto de páginas de relatório formadas por um conjunto de métricas. Estas métricas são visualizadas como gráficos, blocos e tabelas. 

As tabelas a seguir mostram uma visão geral das visualizações no conteúdo de **Gerenciamento de custos** do Power BI.

### <a name="inventory-accounting-status"></a>Status da contabilidade de estoque

| Página de relatório                               | Visualização                                   |
|-------------------------------------------|-------------------------------------------------|
| Visão geral do estoque                        | Saldo inicial                               |
|                                           | Alteração líquida                                      |
|                                           | % da alteração líquida                                    |
|                                           | Saldo final                                  |
|                                           | Precisão do estoque                              |
|                                           | Índice de giro de estoque                        |
|                                           | Dias de estoque disponível                          |
|                                           | Produto ativo no período                        |
|                                           | Objetos de custo ativos no período                   |
|                                           | Saldo por grupo de itens                           |
|                                           | Saldo por site                                 |
|                                           | Demonstrativo por categoria                           |
|                                           | Alteração líquida por trimestre                           |
| Visão geral do estoque por site e grupo de itens | Precisão do estoque por site                      |
|                                           | Índice de giro de estoque por site                |
|                                           | Saldo final do estoque por site                |
|                                           | Precisão do estoque por grupo de itens                |
|                                           | Índice de giro de estoque por grupo de itens          |
|                                           | Saldo final do estoque por site de site e grupo de itens |
| Demonstrativo de estoque                       | Demonstrativo de estoque                             |
| Demonstrativo de estoque por site               | Demonstrativo de estoque por site                     |
| Demonstrativo de estoque por hierarquia de produtos  | Demonstrativo de estoque                             |
| Demonstrativo de estoque por hierarquia de produtos  | Demonstrativo de estoque por site                     |

### <a name="manufacturing-accounting-status"></a>Status da contabilidade de fabricação

| Página de relatório                | Visualização                       |
|----------------------------|-------------------------------------|
| Visão geral de WIP até a presente data           | Saldo inicial                   |
|                            | Alteração líquida                          |
|                            | % da alteração líquida                        |
|                            | Saldo final                      |
|                            | Índice de giro de WIP                  |
|                            | Dias de WIP disponíveis                    |
|                            | Objeto de custo ativo no período        |
|                            | Alteração líquida por grupo de recursos        |
|                            | Saldo por site                     |
|                            | Demonstrativo por categoria               |
|                            | Alteração líquida por trimestre               |
| demonstrativo WIP              | Saldo inicial                   |
|                            | Saldo final                      |
|                            | Demonstrativo de WIP por categoria           |
| Demonstrativo de WIP por site      | Saldo inicial                   |
|                            | Saldo final                      |
|                            | Demonstrativo de WIP por categoria e site  |
| Demonstrativo de WIP por hierarquia | Saldo inicial                   |
|                            | Saldo final                      |
|                            | Demonstrativo de WIP por hierarquia de categoria |

### <a name="inventory-accounting-analysis"></a>Análise da contabilidade de estoque

| Página de relatório        | Visualização                                                                |
|--------------------|------------------------------------------------------------------------------|
| Detalhes do estoque  | Os 10 melhores recursos por saldo final                                           |
|                    | Os 10 melhores recursos por aumento de alteração líquida                                      |
|                    | Os 10 melhores recursos por redução de alteração líquida                                      |
|                    | Os 10 melhores recursos por índice de giro de estoque                                 |
|                    | Recursos por baixo índice de giro de estoque e saldo final acima do limite |
|                    | Os 10 melhores recursos por baixa precisão                                             |
| Classificação ABC | Saldo final de estoque                                                     |
|                    | Material consumido                                                            |
|                    | Vendido (COGS)                                                                  |
| Tendências de estoque   | Saldo final de estoque                                                     |
|                    | Alteração líquida de estoque                                                         |
|                    | Índice de giro de estoque                                                     |
|                    | Precisão do estoque                                                           |

### <a name="manufacturing-accounting-analysis"></a>Análise da contabilidade de fabricação

| Página de relatório | Visualização      |
|-------------|--------------------|
| Tendências de WIP  | Saldo final WIP |
|             | Alteração líquida WIP     |
|             | Índice de giro de WIP |

### <a name="std-cost-variance-analysis"></a>Análise da variação de custo padrão

| Página de relatório                             | Visualização                                        |
|-----------------------------------------|------------------------------------------------------|
| Variação do preço de compra (cusot padrão) até a presente data | Saldo adquirido                                     |
|                                         | Variação do preço de compra                              |
|                                         | Índice de variação do preço de compra                        |
|                                         | Variação por grupo de itens                               |
|                                         | Variação por site                                     |
|                                         | Preço de compra por trimestre                            |
|                                         | Preço de compra por trimestre e por grupo de itens             |
|                                         | Os 10 melhores recursos por índice de preço de compra desfavorável |
|                                         | Os 10 melhores recursos por índice de preço de compra favorável   |
| Variação de produção (cusot padrão) até a presente data     | Custo de fabricação                                    |
|                                         | Variação de produção                                  |
|                                         | Índice de variação de produção                            |
|                                         | Variação por grupo de itens                               |
|                                         | Variação por site                                     |
|                                         | Variação de produção por trimestre                       |
|                                         | Variação de produção por trimestre e tipo de variação     |
|                                         | Os 10 melhores recursos por variação de produção desfavorável  |
|                                         | Os 10 melhores recursos por variação de produção favorável    |

## <a name="understanding-the-data-model-and-entities"></a>Noções básicas sobre o modelo de dados e as entidades

Os dados do aplicativo são usados para preencher as páginas do relatório no conteúdo de **Gerenciamento de custos** do Power BI. Esses dados são representados como medidas agregadas que são preparadas no repositório de entidades, que é um banco de dados do Microsoft SQL Server otimizado para análise. Para obter mais informações, consulte [Integração do Power BI com o repositório Entidade](power-bi-integration-entity-store.md).

As principais medidas agregadas dos objetos a seguir são usadas como base do conteúdo do Power BI.

| Objeto                          | Principais medidas agregadas | Fonte de dados para o Finance and Operations | Campo               |
|---------------------------------|----------------------------|----------------------------------------|---------------------|
| CostObjectStatementCacheMonthly | Valor                     | CostObjectStatementCache               | Valor              |
| CostObjectStatementCacheMonthly | Quantidade                   | CostObjectStatementCache               | Qtd.                 |
| CostInventoryAccountingKPIGoal  | AnnualInventoryTurn        | CostInventoryAccountingKPIGoal         | AnnualInventoryTurn |
| CostInventoryAccountingKPIGoal  | InventoryAccuracy          | CostInventoryAccountingKPIGoal         | InventoryAccuracy   |

A tabela a seguir mostra a principais medidas calculadas no conteúdo do Power BI.

| Medição                            | Cálculo |
|------------------------------------|-------------|
| Saldo inicial                  | Saldo inicial = \[Saldo final\]-\[Alteração líquida\] |
| Quantidade do saldo inicial             | Quantidade do saldo inicial = \[Quantidade do saldo final\]-\[Quantidade da alteração líquida\] |
| Saldo final                     | Saldo final = (CALCULATE(SUM(\[Amount\]), FILTER(ALL(FiscalCalendar) ,FiscalCalendar\[MONTHSTARTDATE\] \<= MAX(FiscalCalendar\[MONTHSTARTDATE\])))) |
| Quantidade do saldo final                | Quantidade do saldo final = CALCULATE(SUM(\[QTY\]), FILTER(ALL(FiscalCalendar),FiscalCalendar\[MONTHSTARTDATE\] \<= MAX(FiscalCalendar\[MONTHSTARTDATE\]))) |
| Alteração líquida                         | Alteração líquida = SUM(\[AMOUNT\]) |
| Quantidade da alteração líquida                    | Quantidade da alteração líquida = SUM(\[QTY\]) |
| Índice de giro de estoque por valor | Índice de giro de estoque por valor = if(OR(\[Saldo médio de estoque\] \<= 0, \[Inventory sold or consumed issues\] \>= 0), 0, ABS(\[Problemas de estoque vendido ou consumido\])/\[Saldo médio de estoque\]) |
| Saldo médio de estoque          | Saldo médio de estoque = ((\[Saldo final\] + \[Saldo inicial\]) / 2) |
| Dias de estoque disponível             | Dias de estoque disponível = 365 / CostObjectStatementEntries\[Índice de giro de estoque por valor\] |
| Precisão do estoque                 | Precisão do estoque por valor = IF(\[Saldo final\] \<= 0, IF(OR(\[Inventory counted amount\] \<\> 0, \[Saldo final\] \< 0), 0, 1), MAX(0, (\[Saldo final\] - ABS(\[Valor contado de estoque\]))/\[Saldo final\])) |

As principais dimensões a seguir são usadas como filtros para dividir as medidas agregadas, para que você possa obter maior granularidade e obter insights analíticos mais profundos.


| Entidade                                                  | Exemplos de atributos                          |
|---------------------------------------------------------|-------------------------------------------------|
| Produtos                                                | Número do produto, Nome do produto, Unidade, Grupos de itens |
| Hierarquias de categoria (atribuídas à função Gerenciamento de custo) | Hierarquia de categoria, Nível da categoria              |
| Entidades legais                                          | Nomes de entidade legal                              |
| Calendários fiscais                                        | Calendário fiscal, Ano, Trimestre, Período, Mês   |
| Site                                                    | ID, Nome, Endereço, Estado, País               |


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
