---
title: "Conteúdo de O power BI de teste da contabilização de custo previsto"
description: "Este tópico descreve o que está incluído no conteúdo de O power BI de teste da contabilização de custo previsto. Explica como acessar os relatórios de O power BI, e fornece informações sobre o modelo de dados e as entidades usados para construir o conteúdo."
author: YuyuScheller
manager: AnnBe
ms.date: 2017-04-04
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User, IT Pro
ms.search.scope: Operations
ms.custom: 270274
ms.assetid: b74549df-35d5-4f2f-b3c7-405b0d38ea78
ms.search.region: Global
ms.author: yuyus
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: 388b6398488e6f316c1ec07a00182e81c1dc8d08
ms.openlocfilehash: 50e7bd92ee693f59fd013226aee22bd1a54c81e2
ms.lasthandoff: 03/31/2017


---

# <a name="cost-accounting-analysis-power-bi-content"></a>Conteúdo de O power BI de teste da contabilização de custo previsto

Este tópico descreve o que está incluído no conteúdo de O power BI de teste da contabilização de custo previsto. Explica como acessar os relatórios de O power BI, e fornece informações sobre o modelo de dados e as entidades usados para construir o conteúdo.

<a name="overview"></a>Visão Geral
--------

** Análise de contabilização de custo previsto ** o conteúdo de O power BI Microsoft é adequado para controladores de custo estimado ou alguém responsável para executar o controle de custo de uma organização. Inclui métricas principal, como custo, magnitude, e taxa de custo para custos reais, custos de orçamento por, e por custos flexíveis. Usa dados de transações de contabilização de custo estimado no Microsoft Dynamics 365 para operações e uma visão agregada de custo para a organização inteira em uma moeda de relatório. Os gerentes podem filtrar dados por objetos de custo estimado para executar o controle de custo das unidades organizacionais, mesmo que a organização pode ter várias entidades legais. Porque ** análise de contabilização de custo previsto ** o conteúdo de O power BI realça variações entre os custos reais e os custos orçados, gerentes podem ser notificados sobre tendências positivas e negativos para as unidades operacionais. Os gerentes podem fazer busca detalhada em hierarquias de elementos de custo estimado ou aos elementos de custo previsto individuais para obter introspecção detalhada em como as variações de custo, ocorreram e levar a ação em vigor. ** Análise de contabilização de custo previsto ** o conteúdo de O power BI deixar contadores de custo previsto analisar como os custos são feitas nos objetos de custo previsto organizacional inteira. Para saber mais sobre contabilização de custo previsto, consulte [] home page de contabilidade (/dynamics365/operations/financials/cost e contabilização de custo previsto da contabilização de custo previsto home-page.md -). Configurando a segurança em nível de acesso na contabilização de custo previsto e a combinação com a segurança em nível de linha do power BI, você poderá conceder os proprietários de custo previsto da acesso ** análise de contabilização de custo previsto põe conteúdo ** de BI. Todos os dados nas exibições serão filtradas então com o nível de acesso que é controlado na contabilização de custo previsto. Para saber mais sobre segurança em nível de acesso e a segurança em nível de linha, consulte segurança [configurada para o conteúdo da contabilização de custo previsto do power BI] de setup-security-cost-accounting-content-pack.md ().

## <a name="accessing-the-power-bi-content"></a>Acessando o conteúdo de O power BI
Você pode encontrar ** análise de contabilização de custo previsto põe conteúdo ** de BI na biblioteca de ativos compartilhados em serviços (LCS) do Microsoft Dynamics lifecycle. Para obter mais informações sobre como o download conteúdo e à alocação de dados dynamics 365, consulte operações [conteúdo de O power BI em LCS Microsoft e seus parceiros (power-bi-content-microsoft-partners.md]). ** Observação: ** KB4011327 ** ** é um pré-requisito para ** análise de contabilização de custo previsto ** o conteúdo de O power BI.  Após você entra serviços do ciclo de vida, você pode acessar o KB aqui: <https://fix.lcs.dynamics.com/issue/results/?q=kb4011327>.

## <a name="metrics-that-are-included-in-the-power-bi-content"></a>Medidor incluído no conteúdo de O power BI
O conteúdo inclui um conjunto de páginas do relatório. Cada página consiste em um conjunto que são métricas de visualizado como gráficos, caixas, e tabelas. A seguinte tabela fornece uma visão geral do teste visualizações ** de contabilização de custo previsto põe conteúdo ** de BI.

| Página de relatório                      | Gráfico                                                                                                                         | Bloco                                          |
|----------------------------------|-------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------|
| Controle de custo por período fiscal    | Custos reais e de orçamento por nível de hierarquia do elemento de custo previsto                                                                   | Custos reais versus custos de orçamento                    |
|                                  | Variação de orçamento por nível de hierarquia do elemento de custo previsto                                                                               | Taxa de custo real vs a taxa de custo previsto de orçamento          |
|                                  | Variação de orçamento de 10 melhores o percentual por elementos de custo previsto                                                                          | A magnitude real vs magnitude de orçamento          |
| Controle de custo no ano até     | O custo real e o orçamento custaram período no ano civil                                                                           | Custos reais versus custos de orçamento                    |
|                                  | Variação de orçamento por período de ano civil                                                                                       | Taxa de custo real vs a taxa de custo previsto de orçamento          |
|                                  | Variação de orçamento de 10 melhores o percentual por elementos de custo previsto                                                                          | A magnitude real vs magnitude de orçamento          |
| Taxa de custo estimado no ano fiscal         | Taxa de custo real por comportamento de custo previsto                                                                                             | Taxa de custo real vs a taxa de custo previsto de orçamento          |
|                                  | Taxa de custo real, orçamento de taxa de variação de custo previsto, a taxa de percentual orçamento de custo previsto e custos de orçamento taxa por nível de hierarquia do elemento de custo previsto | A magnitude real vs magnitude de orçamento          |
|                                  | Variação de orçamento por nível de hierarquia do elemento de custo previsto                                                                               |                                               |
|                                  | Variação de orçamento de 10 melhores o percentual por elementos de custo previsto                                                                          |                                               |
| Orçamento flexível por período fiscal | Custos reais, custos de orçamento e de orçamento flexível por nível de hierarquia do elemento de custo previsto                                             | A magnitude real vs magnitude de orçamento          |
|                                  | Variação de orçamento e variação de orçamento flexível por nível de hierarquia do elemento de custo previsto                                                  | Custos reais versus custos de orçamento flexíveis           |
|                                  | Custos reais, custos de orçamento flexíveis e o comportamento de custo previsto e por nível de hierarquia do elemento de custo previsto                                  | Taxa de custo real vs a taxa de custo previsto de orçamento flexível |
| Demonstrativo de custo previsto por período fiscal  | Custo real por nome do membro de dimensão do nível de hierarquia do elemento de custo previsto e de custo                                             |                                               |
|                                  | Custos reais do custo previsto do membro de nome do membro de dimensão de objeto e de dimensão do elemento de custo previsto                                       |                                               |

## <a name="understanding-the-data-model-and-entities"></a>Noções básicas sobre o modelo de dados e as entidades
O dynamics 365 para operações que são usados para preencher as páginas de relatório de análise em ** contabilização de custo previsto põem ** o conteúdo de BI. Esses dados são representadas como as medições agregadas que forem preparadas na entidade, um base de dados Microsoft SQL que é otimizada para análise. Para obter mais informações, consulte visão geral [de integração do power BI com armazenamento] entidade (power-bi-integration-entity-store.md). Estas medições agregação de chave são usadas como base de conteúdo.

| Entidade                  | Medição agregada principal | Fonte de dados para dynamics 365 para operações | Campo     | descrição                                   |
|-------------------------|---------------------------|---------------------------------------------|-----------|-----------------------------------------------|
| Escriturações de custo previsto | SUM (valor)               | CAMDATAAggregatedCostEntry                  | Valor    | Valor na moeda do razão da contabilização de custo previsto |
| Entradas de estatísticas     | (SUM magnitude)            | CAMDATAAggregatedStatisctialEntry           | Magnitude |                                               |

A tabela mostra como as medições agregadas principais são usadas para criar diversas medidas calculadas no conjunto de dados de conteúdo.

| Medição                                       | Como é calculada a medição                                                                                          |
|-----------------------------------------------|------------------------------------------------------------------------------------------------------------------------|
| Custo real                                   | CALCULE medida (“\]de entries'entity_PLACEHOLDER \ [de contabilização de custo previsto de versions'entity_PLACEHOLDER “, [ISSOURCEVERSIONBUDGET \\_a transação VALOR\] = 0)            |
| Custo de orçamento                                   | CALCULE medida (“\]de entries'entity_PLACEHOLDER \ [de contabilização de custo previsto de versions'entity_PLACEHOLDER “, [ISSOURCEVERSIONBUDGET \\_a transação VALOR\] = 1)            |
| De orçamento a variação de custo                          | custos reais de custo previsto\]\] - \[de orçamento do\[                                                                                      |
| Percentual de variação do orçamento                    | IF (\] orçamento de custo previsto =\[0, em branco (\]), orçamento de custo previsto\] / \[de variação do \[)                                                |
| Magnitude real                              | CALCULE (“entries'entity_PLACEHOLDER \ [estatístico FullMagnitude\]“, de versions'entity_PLACEHOLDER \ [ISSOURCEVERSIONBUDGET\_a transação VALOR\] = 0)          |
| De orçamento a magnitude                              | CALCULE (\[FullMagnitude\], de versions'entity_PLACEHOLDER '\ [ISSOURCEVERSIONBUDGET\_a transação VALOR\] = 1)                               |
| Variação estatísticas de orçamento                   | magnitude real\]\] - \[a magnitude de orçamento do\[                                                                            |
| Percentual de variação estatístico de orçamento        | IF (magnitude\] de orçamento\[, 0 = em branco (), magnitude estatísticas de orçamento\]\] / \[de variação do \[)                          |
| Taxa de custo real                              | IF magnitude (real =\]\[0, PLACA (real, magnitude\]\] / \[de custo reais do \[)                                          |
| Taxa de custo do orçamento                              | IF (magnitude\] de orçamento\[= 0, PLACA (), custo previsto magnitude do\]de orçamento\] / \[de orçamento do \[)                                          |
| Variação de custo previsto do orçamento                     | taxa de custo previsto de custo reais\]\] - \[do orçamento do\[                                                                            |
| Porcentagem de custo previsto de variação do orçamento          | IF (\] orçamento de custo previsto =\[0, em branco (), orçamento de custo previsto\] / \[de variação do orçamento \[taxa de custo previsto\])                                 |
| Custos fixos de orçamento                             | \]CALCULE (custos de orçamento do\[, entries'entity_PLACEHOLDER '\ [COSTBEHAVIOR\] a contabilização de custo previsto = 1)                                              |
| Custos variáveis de orçamento                          | \]CALCULE (custos de orçamento do\[, entries'entity_PLACEHOLDER '\ [COSTBEHAVIOR\] a contabilização de custo previsto = 2)                                              |
| Custos de orçamento flexíveis fixos                    | \[Custos fixos de orçamento\]                                                                                                  |
| Custos de orçamento flexíveis variáveis                 | IF (magnitude\] de orçamento\[= 0, PLACA (, (magnitude de custo previsto de orçamento\]\] / \[de orçamento variável\[) magnitude real\]\* \[)       |
| Custos de orçamento flexíveis                          | \[do orçamento flexível\]de custo previsto + \[orçamento flexível variável\]de custo previsto                                                     |
| Variação de orçamento flexível                      | custos reais de custo previsto\]\] - \[de orçamento flexível\[                                                                             |
| Flexível porcentagem de variação do orçamento           | Orçamento flexível (SE\] de custo previsto =\[0, PLACA (esse orçamento flexível,\]de custo previsto\] / \[de variação do \[)                     |
| Taxa de custo previsto de orçamento flexível                     | IF magnitude (real =\]\[0, PLACA (orçamento flexível,\]de custo previsto / \[\[magnitude real\])                                 |
| Variação de custo previsto do orçamento flexível            | taxa de custo previsto de custo reais\]\] - \[do orçamento flexível\[                                                                   |
| Porcentagem de custo previsto de variação do orçamento flexível | IF (taxa de custo previsto\] de orçamento flexível\[= 0, PLACA (, variação de custo previsto\] / \[do orçamento flexível \[orçamento flexível taxa de custo previsto\]) |

As seguintes dimensões principais são usadas como os filtros para cortar medições agregadas para obter a granularidade maior e fornecer uma introspecções analíticas mais profundas.

| Entidade                             | Exemplos de atributos                                                                                               |
|------------------------------------|----------------------------------------------------------------------------------------------------------------------|
| Razões de contabilização de custos            | Razão de contabilização de custos                                                                                               |
| Unidades de controle de custo                 | Nome da unidade de controle de custo                                                                                               |
| Dimensões do elemento de custo            | Elementos de custo previsto do nome, nome do membro de dimensão do elemento de custo previsto, o membro descrição de dimensão do elemento de custo previsto          |
| Dimensões de objeto de custo             | Nome do custo previsto de dimensão de objeto, nome do membro de dimensão de objeto de custo, o membro descrição de dimensão de objeto de custo              |
| Dimensões estatísticas             | Nome estatístico de dimensão, nome do membro estatístico de dimensão, o membro estatística descrição de dimensão              |
| Hierarquias de custo previsto do objeto  | Nome do custo previsto da hierarquia de dimensão de objeto, nível de hierarquia de dimensão a OS de custos, hierarquia de hierarquia de dimensão a OS de custo    |
| Hierarquias de elementos de custo previsto | Nome da hierarquia de dimensão do elemento de custo previsto, nível de hierarquia de dimensão do elemento de custo previsto, árvore de hierarquia de dimensão do elemento de custo previsto |
| Hierarquias estatísticas  | Nome estatístico da hierarquia de dimensão, estatístico nível de hierarquia de dimensões, a estatística da hierarquia de dimensão    |
| Versões de transação               | Nome da versão                                                                                                         |
| Calendários fiscais                   | Calendário, descrição do calendário                                                                                       |
| Anos fiscais                       | Ano civil                                                                                                        |
| Períodos fiscais                     | Período do ano civil                                                                                                 |

## <a name="additional-resources"></a>Recursos adicionais
Estes são alguns links úteis relacionados às entidades e ao desenvolvimento de conteúdo do Power BI:

-   [Entidades de dados](..\data-entities\data-entities.md)
-   [Criando pacotes de conteúdo organizacionais](https://powerbi.microsoft.com/en-us/documentation/powerbi-service-organizational-content-packs-introduction/)
-   [Modelagem de dados por meio do Power BI](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-2-1-intro-modeling-data)
-   [Adicionando blocos do Power BI aos espaços de trabalho](configure-power-bi-integration.md)
-   [Segurança configuração para o conteúdo da contabilização de custo previsto do power BI] de (setup-security-cost-accounting-content-pack.md)


