---
title: "Conteúdo Gerente de prática do Power BI"
description: "Este tópico descreve o que está incluído no conteúdo Gerente de prática do Power BI. Ele explica como acessar os relatórios incluídos no pacote de conteúdo, além de fornecer informações sobre o modelo de dados e as entidades usadas para criar o pacote de conteúdo."
author: knelson
manager: AnnBe
ms.date: 04/28/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Developer/IT Pro
ms.assetid: 
ms.search.region: Global
ms.author: knelson
ms.dyn365.intro: 2017/04/27
ms.dyn365.version: 
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 0f2a1a9df8e5036c60b74b8a710e606b0b1e312a
ms.contentlocale: pt-br
ms.lasthandoff: 05/25/2017


---

# <a name="practice-manager-power-bi-content"></a>Conteúdo Gerente de prática do Power BI

[!include[banner](../includes/banner.md)]


Este tópico descreve o que está incluído no conteúdo **Gerente de prática** do Microsoft Power BI. Ele explica como acessar os relatórios do Power BI, além de fornecer informações sobre o modelo de dados e as entidades usados para criar o pacote de conteúdo.

## <a name="overview"></a>Visão Geral

O conteúdo **Gerente de prática** do Power BI foi criado para gerentes de prática e para gerentes de projeto. Ele oferece métricas chave relacionadas aos projetos em que a organização estiver trabalhando. O painel apresenta uma visão geral dos projetos e de clientes relacionados. Um filtro no nível de relatório pode ser usado para relatar entidades legais específicas. Esse conteúdo do Power BI obtém os dados das medidas agregadas da contabilidade de projeto para o Microsoft Dynamics 365 for Operations.

O conteúdo **Gerente de prática** do Power BI contém cinco páginas de relatório: uma página de visão geral e quatro páginas que fornecem detalhes de custos e receitas do projeto, do gerenciamento do valor obtido e as métricas de hora divididas entre diversas dimensões.

Todos os valores no conteúdo são mostrados na moeda do sistema. Você pode definir a moeda do sistema na página **Parâmetros do sistema**.

## <a name="accessing-the-power-bi-content"></a>Acessando o conteúdo do Power BI

Você pode encontrar o conteúdo do Power BI **Gerente de prática** na biblioteca Ativos compartilhados, no Microsoft Dynamics Lifecycle Services (LCS). Para obter mais informações sobre como baixar o pacote de conteúdo e conectá-lo a seus dados do Dynamics 365 for Operations, consulte [Conteúdo do Power BI no LCS da Microsoft e seus parceiros](power-bi-content-microsoft-partners.md).

Para indicar uma demonstração que mostre como implementar o conteúdo do Power BI, veja o Office Mix [Conteúdo do Power BI da Microsoft e seus parceiros no Dynamics Lifecycle Services](https://mix.office.com/watch/9puyb1b2xs1w).

## <a name="reports-that-are-included-in-the-power-bi-content"></a>Relatórios incluídos no conteúdo do Power BI

A tabela a seguir fornece detalhes sobre as métricas encontradas em cada página de relatório no conteúdo **Gerente de prática** do Power BI.

| Página de relatório                                          | Métrica               |
|------------------------------------------------------|-----------------------------------------------|
| Painel  | Projetos criados<br>Projetos previstos<br>Projetos em andamento<br>Número de projetos por estágio<br>Número de projetos por cidade<br>Receita real por cliente<br>Margem bruta de orçamento por projeto<br>Visão geral do gerenciamento de valores obtidos |
| Custo                                                 | Custo real versus orçamento por mês<br>Custo real versus orçamento por ano<br>Custo real versus orçamento por categoria<br>Custo real por tipo de transação       |
| Receita                                              | Receita real por mês<br>Receita real por CEP<br>Receita real versus orçamento por categoria<br>Receita real por setor do cliente        |
| EVM                                                  | Índice de custo e de desempenho de agenda por projeto                 |
| Horas                                                | Horas utilizadas faturáveis reais versus horas de custo indireto faturáveis reais versus horas do orçamento<br>Horas utilizadas faturáveis reais versus horas de custo indireto faturáveis reais por projeto<br>Horas utilizadas faturáveis reais versus horas de custo indireto faturáveis reais por recurso<br>Taxa de horas faturáveis reais por projeto<br>Taxa de horas faturáveis reais por recurso |

Os gráficos e os blocos em todos esses relatórios podem ser filtrados e fixados no painel. Para saber mais sobre como filtrar e fixar no Power BI, veja [Criar e configurar um painel](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-4-2-create-configure-dashboards/). Você também pode usar a funcionalidade Exportar dados subjacentes para exportar os dados subjacentes resumidos em uma visualização.

## <a name="understanding-the-data-model-and-entities"></a>Noções básicas sobre o modelo de dados e as entidades

Os dados do Dynamics 365 for Operations são usados para preencher as páginas do relatório no conteúdo do Power BI **Gerente de prática**. Esses dados são representados como medições agregadas que são preparadas na loja Entidade, que é um banco de dados Microsoft SQL otimizado para análise. Para obter mais informações, consulte [Visão geral da integração do Power BI com a loja Entidade](power-bi-integration-entity-store.md).

As seções a seguir explicam as medidas agregadas usadas em cada entidade.

### <a name="entity-projectaccountingcubeactualhourutilization"></a>Entidade: ProjectAccountingCube_ActualHourUtilization
**Fonte de dados**: ProjEmplTrans

| Principal medida agregada                | Campo                                | descrição                            | 
|------------------------------------------|--------------------------------------|----------------------------------------|
| ActualBillableUtilizedHours              | Sum(ActualUtilizationBillableRate)   | Total de horas utilizadas faturáveis reais |
| ActualBillableBurdenHours                | Sum(ActualBurdenBillableRate)        | Total de taxa de custo indireto real             |

### <a name="entity-projectaccountingcubeactuals"></a>Entidade: ProjectAccountingCube_Actuals
**Fonte de dados**: ProjTransPosting

| Principal medida agregada                | Campo                                | descrição                            | 
|------------------------------------------|--------------------------------------|----------------------------------------|
| ActualRevenue                            |     Sum(ActualRevenue)               |  Total da receita lançada para uma transação |   
| ActualCost   |                             Sum(ActualCost)           |    Total de custo lançado para todos os tipos de transação    |

### <a name="entity-projectaccountingcubecustomer"></a>Entidade: ProjectAccountingCube_Customer
**Fonte de dados**: CustTable

| Principal medida agregada                | Campo                                | descrição                            | 
|------------------------------------------|--------------------------------------|----------------------------------------|
|    Número de projetos        |   COUNTA(ProjectAccountingCube_Projects[PROJECTS])       |         Contagem de Projetos disponíveis    |


### <a name="entity-projectaccountingcubeforecasts"></a>Entidade: ProjectAccountingCube_Forecasts
**Fonte de dados**: ProjTransBudget

| Principal medida agregada                | Campo                                | descrição                            | 
|------------------------------------------|--------------------------------------|----------------------------------------|
|    BudgetCost    |       Sum(BudgetCost)  |       Total de custo previsto para todos os tipos de transação     |
|     BudgetRevenue    |         Sum(BudgetRevenue)    |    O total de receita acumulada/faturada prevista         |
|BudgetGrossMargin | Sum(BudgetGrossMargin) |A diferença entre a soma do total de receita prevista e a soma do total de custo previsto

### <a name="entity-projectaccountingcubeprojectplancostsview"></a>Entidade: ProjectAccountingCube_ProjectPlanCostsView
**Fonte de dados**: Project

| Principal medida agregada                | Campo                                | descrição                            | 
|------------------------------------------|--------------------------------------|----------------------------------------|
|      PlannedCost      |        Sum(SumOfTotalCostPrice)   | Total de preço de custo em estimativas para todos os tipos de transação de projeto com tarefas planejadas |

### <a name="entity-projectaccountingcubeprojects"></a>Entidade: ProjectAccountingCube_Projects
**Fonte de dados**: Project

| Principal medida agregada                | Campo                                | descrição                            | 
|------------------------------------------|--------------------------------------|----------------------------------------|
|   Índice de desempenho de custo  |ProjectAccountingCube_Projects[Valor ganho]/ProjectAccountingCube_Projects[Total de custo real de tarefas concluídas] |     Cálculo do total do valor ganho dividido pelo total do custo real|
|  Índice de desempenho da agenda |ProjectAccountingCube_Projects[Valor ganho]/ProjectAccountingCube_Projects[Total de custo planejado de tarefas concluídas]|Cálculo do total do valor ganho dividido pelo total do custo planejado |
|Porcentagem de trabalho concluído |Percentual de trabalho concluído = ProjectAccountingCube_Projects[Total do custo real de tarefas concluídas]/(ProjectAccountingCube_Projects[Total do custo real de tarefas concluídas] + ProjectAccountingCube_Projects[Total do custo planejado do projeto] - ProjectAccountingCube_Projects[Total do custo planejado de tarefas concluídas])|O percentual total de trabalho concluído com base no total do custo real de tarefa concluída e no custo planejado do projeto|
|Taxa de Horas faturáveis reais do projeto|ProjectAccountingCube_Projects[Total de horas do projeto faturáveis reais utilizadas]/(ProjectAccountingCube_Projects[Total de horas do projeto faturáveis reais utilizadas] + ProjectAccountingCube_Projects[Total de horas do projeto faturáveis reais de custo indireto])|Total de horas faturáveis reais com base em utilizadas + custo indireto|
|Valor obtido|ProjectAccountingCube_Projects[Total do custo planejado do projeto] * ProjectAccountingCube_Projects[Percentual do trabalho concluído]|Total do custo planejado multiplicado pelo percentual do trabalho concluído|

### <a name="entity-projectaccountingcubetotalestimatedcosts"></a>Entidade: ProjectAccountingCube_TotalEstimatedCosts 
**Fonte de dados**: ProjTable

| Principal medida agregada                | Campo                                | descrição                            | 
|------------------------------------------|--------------------------------------|----------------------------------------|
| CompletedActivityPlannedCost  |  Sum(TotalCostPrice)  |   Total de preço de custo em estimativas para todos os tipos de transação de projeto com tarefas concluídas|

## <a name="additional-resources"></a>Recursos adicionais

Estes são alguns links úteis relacionados às entidades e ao desenvolvimento de conteúdo do Power BI:

- [Entidades de dados](/dynamics365/operations/dev-itpro/data-entities/data-entities)
- [Criando pacotes de conteúdo organizacionais](https://powerbi.microsoft.com/en-us/documentation/powerbi-service-organizational-content-packs-introduction/)
- [Modelagem de dados por meio do Power BI](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-2-1-intro-modeling-data)
- [Configurar a integração do Power BI para espaços de trabalho](configure-power-bi-integration.md)

