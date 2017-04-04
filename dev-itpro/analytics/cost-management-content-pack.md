---
title: "Custo o conteúdo de O power BI de gerenciamento"
description: "Este tópico descreve o que está incluído no conteúdo de custo previsto do power BI de gerenciamento. Explica como acessar os relatórios de O power BI, e fornece informações sobre o modelo de dados e as entidades que são usados para construir o conteúdo."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User, IT Pro
ms.search.scope: AX 7.0.0, Operations
ms.custom: 270314
ms.assetid: 9680d977-43c8-47a7-966d-2280ba21402a
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 388b6398488e6f316c1ec07a00182e81c1dc8d08
ms.openlocfilehash: e4de011e6eeac58643b828b65e24b874d981d5e7
ms.lasthandoff: 03/31/2017


---

# <a name="cost-management-power-bi-content"></a>Custo o conteúdo de O power BI de gerenciamento

Este tópico descreve o que está incluído no conteúdo de custo previsto do power BI de gerenciamento. Explica como acessar os relatórios de O power BI, e fornece informações sobre o modelo de dados e as entidades que são usados para construir o conteúdo.

# <a name="overview"></a>Visão Geral

** Gerenciamento de custo previsto ** o conteúdo de O power BI Microsoft é adequado para contadores ou pessoas de estoque na organização que é responsável o estoque. ** Gerenciamento de custo previsto ** o conteúdo de O power BI fornece a introspecção administrativa no estoque e no estoque (WIP) de desenvolvimento, e como os custos são feitas por meio de categoria no tempo. As informações também pode ser usada como um manuais suplementam detalhado ao demonstrativo financeiro.

## <a name="key-measures"></a>Medições da chave

+ Saldo inicial
+ Saldo final
+ Alteração líquida
+ % Alteração líquida em
+ Classificação por vencimento

## <a name="key-performance-indicators"></a>Indicadores chave de desempenho
+ Giro de estoque
+ Precisão do estoque

A fonte de dados principal de CostAggregatedCostStatementEntryEntity é a tabela de CostStatementCache. Esta tabela são gerenciados por estrutura o cache de conjunto de dados. Por padrão, ela é atualizada a cada 24 horas, mas você pode habilitar atualizações manuais na configuração de cache de dados. Você pode então fazer uma atualização manual em gerenciamento ** de custo estimado ou ** ** análise de custo previsto ** o espaço de trabalho. Depois da atualização de CostStatementCache é executada, você deve atualizar a conexão de OData em eficiência consulte BI.com dados atualizados no site. Medições de variação (compra, produção) no conteúdo de O power BI pertencem apenas a itens que valuated por método de estoque de custo padrão. A variação de produção é calculado como a diferença entre os custos ativos e os realizados. A variação de produção é calculado quando a ordem de produção possui um status de concluído. ** ** Para obter mais informações sobre tipos de variação de produção e como cada tipo é calculado, consulte analisar [sobre variações para uma ordem de produção] de conclusão (https://technet.microsoft.com/en-us/library/gg242850.aspx).

## <a name="accessing-the-power-bi-content"></a>Acessando o conteúdo de O power BI
** Gerenciamento de custo previsto ** o conteúdo de O power BI está disponível em PowerBI.com. Para obter mais informações sobre como conectar e cobrar do Microsoft Dynamics 365 de dados, consulte operações [conteúdo de O power BI de acesso de power-bi-home-page.md] (PowerBI.com).

## <a name="metrics-that-are-included-in-the-power-bi-content"></a>Medidor incluído no conteúdo de O power BI
O conteúdo inclui um conjunto de páginas do relatório. Cada página consiste em um conjunto que são métricas de visualizado como gráficos, caixas, e tabelas. A seguinte tabela fornece uma visão geral do management visualizações ** ** de custo previsto põe conteúdo de BI.

| Página de relatório | Gráficos | Títulos |
|---|---|---|
|Estoque total (padrão no período atual) |Precisão |Medições de estoque:<br>Saldo final de estoque<br>Alteração líquido de estoque<br>% Alteração de rede de estoque<br>|
| |Giro de estoque | |
| |Saldo final de estoque por grupo de recursos | |
| |Alteração líquido de estoque 2 por nível do nível 1 nome da categoria e o nome de categoria| |
| |Compre variações o nível 3 por nome de grupo de recursos e categoria | |
|Estoque por site (o padrão no período atual) |Estoque o saldo final por nome e por grupo de recursos do site | |
| |Estoque a volta por nome e por grupo de recursos do site | |
| |Estoque o saldo final por cidade e por grupo de recursos | |
|Estoque por grupo de recursos (o padrão no período atual) |As medições | |
| |Estoque a exatidão por valor por grupo de recursos | |
| |De volta ao valor por grupo de recursos | |
|Estoque (YOY o ano corrente padrão para o ano anterior) |As medições | |
| |KPI de estoque:<br>Giro de estoque<br>Precisão do estoque | |
| |Estoque o saldo final por ano e por grupo de recursos | |
| |Compre variações o nível 3 por nome de ano e categoria | |
|Da classificação por vencimento (o padrão do ano atual) |Da classificação por vencimento por trimestre e por grupo de recursos | |
| |Da classificação por vencimento por trimestre e o site nome | |
|WIP (total padrão no período atual) |Alteração de rede WIP por nível 2 em nível 1 nome da categoria e o nome de categoria |Medidas WIP trabalho em andamento:<br>Saldo final de WIP<br>Alteração líquido de WIP<br>% Alteração líquido de WIP<br> |
| |As variações de produção por grupo de recursos por categoria e nomeiam o nível 3 | |
| |Alteração de rede WIP por grupo de recursos | |
|WIP por site (padrão no período atual) |Medidas WIP trabalho em andamento | |
| |A modificação de rede WIP por nome do site e a categoria nomeiam o nível 2 | |
| |As variações de produção por nome e a categoria do site nomeiam o nível 3 | |

## <a name="understanding-the-data-model-and-entities"></a>Noções básicas sobre o modelo de dados e as entidades
O dynamics 365 para operações que são usados para preencher as páginas de relatório em gerenciamento ** de custo previsto põem ** o conteúdo de BI. Esses dados são representadas como as medições agregadas que forem preparadas na entidade, um base de dados Microsoft SQL que é otimizada para análise. Para obter mais informações, consulte visão geral [de integração do power BI com armazenamento] entidade (power-bi-integration-entity-store.md). Estas medições agregação de chave são usadas como base de conteúdo.

| Entidade            | Medição agregada principal | Fonte de dados para dynamics 365 para operações | Campo             | descrição                       |
|-------------------|---------------------------|---------------------------------------------|-------------------|-----------------------------------|
| Entradas de demonstrativo | Alteração líquida                | CostAggregatedCostStatementEntryEntity      | soma (valor de\[\])   | Valor contábil na moeda |
| Entradas de demonstrativo | Quantidade líquida de modificação       | CostAggregatedCostStatementEntryEntity      | soma (quantidade\]\[) |                                   |

A tabela mostra como as medições agregadas principais são usadas para criar diversas medidas calculadas no conjunto de dados de conteúdo.

| Medição                                 | Como é calculada a medição                                                                                                                                                                                                                                                                                                                                                                                                                                              |
|-----------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Saldo inicial                       | alteração\]a rede\]-\[de saldo final do\[                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| Quantidade inicial de saldo              | quantidade\]altere de rede\]-\[a quantidade de saldo final do\[                                                                                                                                                                                                                                                                                                                                                                                                                        |
| Saldo final                          | CALCULE (valor SUM (\]), FILTRO (ALLEXCEPT calendários fiscais (““, “calendars'entity_PLACEHOLDER \ [fiscal LedgerRecId\]“, ID de entities'entity_PLACEHOLDER \\]“, [nome de entities'entity_PLACEHOLDER\]\ [, “moeda de Ledgers'entity_PLACEHOLDER \\]“, [descrição de Ledgers'entity_PLACEHOLDER\]\ nome “, [\]\[de Ledgers'entity_PLACEHOLDER \ [“), data fiscal = &lt;\] max de calendars'entity_PLACEHOLDER \ [(“\]data fiscal de calendars'entity_PLACEHOLDER \) [))                                                                                                                                                                                           |
| Terminando a quantidade de saldo                 | CALCULE (quantidade SUM (\]), FILTRO (ALLEXCEPT calendários fiscais (““, “calendars'entity_PLACEHOLDER \ [fiscal LedgerRecId\]“, ID de entities'entity_PLACEHOLDER \\]“, [nome de entities'entity_PLACEHOLDER\]\ [, “moeda de Ledgers'entity_PLACEHOLDER \\]“, [descrição de Ledgers'entity_PLACEHOLDER\]\ nome “, [\]\[de Ledgers'entity_PLACEHOLDER \ [“), data fiscal = &lt;\] max de calendars'entity_PLACEHOLDER \ [(“\]data fiscal de calendars'entity_PLACEHOLDER \) [))                                                                                                                                                                                         |
| Do saldo inicial             | \]CALCULE (saldo inicial do\[,\] 'tipo de demonstrativo de entries'entity_PLACEHOLDER \ demonstrativo = [de estoque “”)                                                                                                                                                                                                                                                                                                                                                                                      |
| Saldo final de estoque                | \]CALCULE (saldo final do\[,\] 'tipo de demonstrativo de entries'entity_PLACEHOLDER \ demonstrativo = [de estoque “”)                                                                                                                                                                                                                                                                                                                                                                                         |
| Alteração líquido de estoque                    | CALCULE alteração (\]a rede do\[,\] 'tipo de demonstrativo de entries'entity_PLACEHOLDER \ demonstrativo = [de estoque “”)                                                                                                                                                                                                                                                                                                                                                                                             |
| Alterar quantidade líquido de estoque           | (Quantidade CALCULE\]altere a rede do\[,\] 'tipo de demonstrativo de entries'entity_PLACEHOLDER \ demonstrativo = [de estoque “”)                                                                                                                                                                                                                                                                                                                                                                                    |
| % Alteração de rede de estoque                  | IF\] (saldo final do\[0 = 0,\], saldo final\] / \[altere líquido de estoque do \[)                                                                                                                                                                                                                                                                                                                                                                           |
| Para o valor de estoque                | (se OR (saldo de estoque médio\]\[&lt;= 0, problemas vendidos ou consumidas\] do &gt;\[) = 0, 0, ABS (saídas vendidos ou consumidas\]de estoque do\[)/saldo\[estoque médio\]\[)                                                                                                                                                                                                                                                                                                  |
| Saldo de estoque médio               | (\]de saldo inicial do\] + \[de saldo final\[/2                                                                                                                                                                                                                                                                                                                                                                                                       |
| Problemas vendidos ou consumidas de estoque       | o estoque vendido\[\] + \[\]de custo previsto material consumido estoque                                                                                                                                                                                                                                                                                                                                                                                                                  |
| Custo materiais consumidos estoque        | CALCULE alteração (\]líquido de estoque do\[, 'nome de categoria de entries'entity_PLACEHOLDER \ [de demonstrativo - nível 2 =\_\] ConsumedMaterialsCost “”)                                                                                                                                                                                                                                                                                                                                                            |
| Estoque vendido                          | CALCULE alteração (\]líquido de estoque do\[, 'nome de categoria de entries'entity_PLACEHOLDER \ [de demonstrativo - nível 2 =\_\] “vendido”)                                                                                                                                                                                                                                                                                                                                                                             |
| Precisão do estoque por valor            | IF\] (saldo final do &lt;\[0 = (OR, IF (valor contado estoque\[\]&lt;&gt; 0,\] 0 saldo final de estoque &lt; do \[), 0 1)Max (, 0,\] (saldo final do\[- ABS (valor contado estoque\[\]))\]/saldo final estoque do\[))                                                                                                                                                                                                                              |
| Valor contado estoque                | CALCULE alteração (\]líquido de estoque do\[, 'nome de categoria de entries'entity_PLACEHOLDER \ [de demonstrativo - nível 3 =\_\] “”) contagem                                                                                                                                                                                                                                                                                                                                                                         |
| Classificação por vencimento do estoque                         | (se ISBLANK (máximo ('data fiscal de calendars'entity_PLACEHOLDER\]\ [)), (quadro), max (0, MIN (a classificação por vencimento de estoque do\[de recebimentos quantidade\], classificação por vencimento de estoque\] - \[a quantidade de saldo final de classificação por vencimento de estoque do \[de recebimentos quantidade futuramente\]))) custos unitários do\]avg \* \[                                                                                                                                                                                                                                |
| A classificação por vencimento de recebimentos de estoque de quantidade       | IF (minDate\] = \[\[minDateAllSelected\], CALCULA (quantidade\]altere líquido de estoque “\[,\] 0 quantidade de entries'entity_PLACEHOLDER &gt; \ [de demonstrativo, FILTRO (ALLEXCEPT calendários fiscais (““, “calendars'entity_PLACEHOLDER \ [fiscal LedgerRecId\]“, ID de entities'entity_PLACEHOLDER \\]“, [nome de entities'entity_PLACEHOLDER\]\ [, “moeda de Ledgers'entity_PLACEHOLDER \\]“, [descrição de Ledgers'entity_PLACEHOLDER \\]“, [nome de Ledgers'entity_PLACEHOLDER\]\ [“), data fiscal = &lt;\] max de calendars'entity_PLACEHOLDER \ [('data fiscal de calendars'entity_PLACEHOLDER \\]) [))(Quantidade, CALCULE\]altere líquido de estoque do\[,\] 'quantidade de 0 entries'entity_PLACEHOLDER &gt; \ [do demonstrativo)) |
| Quantidade de saldo final de classificação por vencimento de estoque | \] a quantidade de saldo final\[CALCULA\[+\](quantidade da alteração da rede do\[, FILTRO (ALLEXCEPT calendários fiscais (““, “calendars'entity_PLACEHOLDER \ [fiscal LedgerRecId\]“, ID de entities'entity_PLACEHOLDER \\]“, [nome de entities'entity_PLACEHOLDER\]\ [, “moeda de Ledgers'entity_PLACEHOLDER \\]“, [descrição de Ledgers'entity_PLACEHOLDER \\]“, [nome de Ledgers'entity_PLACEHOLDER\]\ [“), data de calendars'entity_PLACEHOLDER &gt; fiscal\] \ [máximo (“\]data fiscal de calendars'entity_PLACEHOLDER \) [))                                                                                                                                 |
| Recibos de classificação por vencimento de estoque no futuro  | CALCULE alteração (\]líquido de estoque do\[,\] valor “\] 0 de entries'entity_PLACEHOLDER &gt; \ [de demonstrativo, FILTRO (ALLEXCEPT calendários fiscais (““, “calendars'entity_PLACEHOLDER \ [fiscal LedgerRecId\]“, ID de entities'entity_PLACEHOLDER \\]“, [nome de entities'entity_PLACEHOLDER\]\ [, “moeda de Ledgers'entity_PLACEHOLDER \\]“, [descrição de Ledgers'entity_PLACEHOLDER \\]“, [nome de Ledgers'entity_PLACEHOLDER\]\ [), data “\] max &gt; fiscal de calendars'entity_PLACEHOLDER \ [('data fiscal de calendars'entity_PLACEHOLDER \\]) [))                                                                                                                                             |
| Custos unitários do estoque avg                 | (Quantidade CALCULE\]de saldo final\] / \[de saldo final do\[, ALLEXCEPT calendários fiscais (““, “calendars'entity_PLACEHOLDER \ [fiscal LedgerRecId\]“, ID de entities'entity_PLACEHOLDER \\]“, [nome de entities'entity_PLACEHOLDER\]\ [, “moeda de Ledgers'entity_PLACEHOLDER \\]“, [descrição de Ledgers'entity_PLACEHOLDER \\]“, [nome de Ledgers'entity_PLACEHOLDER\]\ [))                                                                                                                                                                                                                 |
| Variações de compra                      | CALCULE (SUM (valor\[\]) “, nome da categoria de entries'entity_PLACEHOLDER \ [de demonstrativo - nível 2 =\_\] “, obtido”\] “tipo de demonstrativo de entries'entity_PLACEHOLDER \ [de demonstrativo variação = “”)                                                                                                                                                                                                                                                                                                                              |
| Saldo inicial WIP                   | \]CALCULE (saldo inicial do\[,\] 'tipo de demonstrativo de entries'entity_PLACEHOLDER \ [do demonstrativo WIP = “”)                                                                                                                                                                                                                                                                                                                                                                                            |
| Saldo final de WIP                      | \]CALCULE (saldo final do\[,\] 'tipo de demonstrativo de entries'entity_PLACEHOLDER \ [do demonstrativo WIP = “”)                                                                                                                                                                                                                                                                                                                                                                                               |
| Alteração líquido de WIP                          | CALCULE alteração (\]a rede do\[,\] 'tipo de demonstrativo de entries'entity_PLACEHOLDER \ [do demonstrativo WIP = “”)                                                                                                                                                                                                                                                                                                                                                                                                   |
| % Alteração líquido de WIP                        | IF\] (saldo final WIP\[= 0, 0,\]saldo final WIP\] / \[altere líquido do \[)                                                                                                                                                                                                                                                                                                                                                                                             |
| Variações de produção                    | CALCULE (SUM (valor\[\]) “, nome da categoria de entries'entity_PLACEHOLDER \ [de demonstrativo - nível 2 =\_\] “ManufacturedCost”\] “, tipo de demonstrativo de entries'entity_PLACEHOLDER \ [de demonstrativo variação = “”)                                                                                                                                                                                                                                                                                                                      |
| Nome de categoria - nível 1                 | alterne (nome da categoria do\[- nível 1,\_\]“sem “, “sem “, ““, “NetSourcing fonte líquida “, “NetUsage” uso líquido, ““, ““, “NetConversionCost custos de conversão líquidos “, ““, “NetCostOfGoodsManufactured custo líquidos fabricação de mercadorias”, de saldo BeginningBalance “”, “” inicial)                                                                                                                                                                                                         |
| Nome de categoria - nível 2                 | alterne (nome da categoria do\[- o nível 2,\_\]“sem “, “sem” “, obtido” “,” “, obtido disposto disposto “, ““, “”, transferido transferido ““, “”, vendido vendido ““, ““, “ConsumedMaterialsCost custo materiais consumidos “, ““, “ConsumedManufacturingCost custo de fabricação consumido “, ““, “ConsumedOutsourcingCost de custos é conhecido como terceirização consumidos “, ““, “ConsumedIndirectCost custos indiretos consumidos “, “ManufacturedCost “, “fabricou custo “, “”, variações variações “”)                            |
| Nome de categoria - nível 3                 | alterne (nome da categoria do\[- nível 3,\_\]nenhum preço ““, “sem” de contagem, “”, as “sem”, “” ProductionPriceVariance de produção, “”, alteração “, “RoundingVariance” de “QuantityVariance”, “a”, “SubstitutionVariance”, “substituído”, “”, ScrapVariance de sucata “”, “LotSizeVariance” “, de tamanho de lote”, “” RevaluationVariance de reavaliação, “”, “PurchasePriceVariance” “, de preço de compra,” “CostChangeVariance”, ““, custos arredondamento a variação”)                                                   |

As seguintes dimensões principais são usadas como os filtros para cortar medições agregadas para obter a granularidade maior e fornecer uma introspecções analíticas mais profundas.

| Entidade           | Exemplos de atributos                       |
|------------------|----------------------------------------------|
| Entidades         | Nome, ID                                     |
| Calendários fiscais | Calendário, período, mês, trimestre, ano       |
| Metas de KPI        | Meta de precisão do estoque, meta de volta de estoque |
| Razões          | Moeda, nome, descrição                  |
| Locais            | ID, nome, país, cidade                      |

## <a name="additional-resources"></a>Recursos adicionais
Estes são alguns links úteis relacionados às entidades e ao desenvolvimento de conteúdo do Power BI:

-   [Entidades de dados](..\data-entities\data-entities.md)
-   [Criando pacotes de conteúdo organizacionais](https://powerbi.microsoft.com/en-us/documentation/powerbi-service-organizational-content-packs-introduction/)
-   [Modelagem de dados por meio do Power BI](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-2-1-intro-modeling-data)
-   [Adicionando blocos do Power BI aos espaços de trabalho](configure-power-bi-integration.md)



