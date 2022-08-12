---
title: Conteúdo de gerente de prática do Power BI
description: Este artigo descreve o que está incluído no conteúdo Gerente de prática do Power BI.
author: sericks007
ms.date: 12/18/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.region: Global
ms.author: kfend
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.assetid: ''
ms.search.form: ProjManagementWorkspace
ms.openlocfilehash: 92c2881c89da0b23e3a66c0f8bbcafd91c38c6e3
ms.sourcegitcommit: 3c4dd125ed321af8a983e89bcb5bd6e5ed04a762
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/28/2022
ms.locfileid: "9206494"
---
# <a name="practice-manager-power-bi-content"></a>Conteúdo de gerente de prática do Power BI

[!include [banner](../includes/banner.md)]

Este artigo descreve o que está incluído no conteúdo **Gerente de prática** do Microsoft Power BI. Ele explica como acessar os relatórios do Power BI e fornece informações sobre o modelo de dados e entidades que são usados para criar o conteúdo.

## <a name="overview"></a>Visão Geral

O conteúdo **Gerente de prática** do Power BI foi criado para gerentes de prática e para gerentes de projeto. Ele oferece métricas chave relacionadas aos projetos em que a organização estiver trabalhando. O painel apresenta uma visão geral dos projetos e de clientes relacionados. Um filtro no nível de relatório pode ser usado para relatar entidades legais específicas. Este conteúdo do Power BI extrai dados das medições agregadas contábeis do projeto.

O conteúdo **Gerente de prática** do Power BI contém cinco páginas de relatório: uma página de visão geral e quatro páginas que fornecem detalhes sobre custos e receitas do projeto, do gerenciamento do valor obtido e as métricas de hora divididas entre diversas dimensões.

Todos os valores no conteúdo são mostrados na moeda do sistema. Você pode definir a moeda do sistema na página **Parâmetros do sistema**.

## <a name="accessing-the-power-bi-content"></a>Acessando o conteúdo do Power BI

O conteúdo do **Gerente de prática** do Power BI é exibido no espaço de trabalho **Gerenciamento de projetos**.

## <a name="reports-that-are-included-in-the-power-bi-content"></a>Relatórios incluídos no conteúdo do Power BI

A tabela a seguir fornece detalhes sobre as métricas encontradas em cada página de relatório no conteúdo **Gerente de prática** do Power BI.

| Página de relatório       | Métrica |
|-------------------|---------|
| Visão geral de projetos | <ul><li>Projetos criados</li><li>Projetos previstos</li><li>Projetos em andamento</li><li>Receita real por cliente</li><li>Margem bruta de orçamento por projeto</li><li>Visão geral do gerenciamento de valores obtidos</li></ul> |
| Custo              | <ul><li>Custo real versus orçamento por mês</li><li>Custo real versus orçamento por ano</li><li>Custo real versus orçamento por categoria</li><li>Custo real por tipo de transação</li></ul> |
| Receita           | <ul><li>Receita real por mês</li><li>Receita real por CEP</li><li>Receita real versus orçamento por categoria</li><li>Receita real por setor do cliente</li></ul> |
| EVM               | Índice de custo e de desempenho de agenda por projeto |
| Horas             | <ul><li>Horas utilizadas faturáveis reais versus horas de custo indireto faturáveis reais versus horas do orçamento</li><li>Horas utilizadas faturáveis reais versus horas de custo indireto faturáveis reais por projeto</li><li>Horas utilizadas faturáveis reais versus horas de custo indireto faturáveis reais por recurso</li><li>Taxa de horas faturáveis reais por projeto</li><li>Taxa de horas faturáveis reais por recurso</li></ul> |

Os gráficos e os blocos em todos esses relatórios podem ser filtrados e fixados no painel. Para obter mais informações sobre como filtrar e fixar no Power BI, consulte [Criar e configurar um painel](https://powerbi.microsoft.com/guided-learning/powerbi-learning-4-2-create-configure-dashboards/). Você também pode usar a funcionalidade Exportar dados subjacentes para exportar os dados subjacentes resumidos em uma visualização.

## <a name="understanding-the-data-model-and-entities"></a>Noções básicas sobre o modelo de dados e as entidades

Os seguintes dados são usados para preencher as páginas de relatório no conteúdo do Power BI **Gerente de práticas**. Esses dados são representadas como medições agregadas que foram preparadas no Repositório de entidades. O Repositório de entidades é um banco de dados do Microsoft SQL Server otimizado para análise. Para obter mais informações, consulte [Integração do Power BI com o repositório Entidade](power-bi-integration-entity-store.md).

As seções a seguir descrevem as medidas agregadas usadas em cada entidade.

### <a name="entity-projectaccountingcube_actualhourutilization"></a>Entidade: ProjectAccountingCube\_ActualHourUtilization
**Fonte de dados:** ProjEmplTrans

| Principal medida agregada      | Campo                              | descrição |
|--------------------------------|------------------------------------|-------------|
| Horas utilizadas faturáveis reais | Sum(ActualUtilizationBillableRate) | Total de horas utilizadas faturáveis reais. |
| Horas de custo Indireto real faturável   | Sum(ActualBurdenBillableRate)      | Total de taxa de custo indireto real. |

### <a name="entity-projectaccountingcube_actuals"></a>Entidade: ProjectAccountingCube\_Actuals
**Fonte de dados:** ProjTransPosting

| Principal medida agregada | Campo              | descrição |
|---------------------------|--------------------|-------------|
| Receita real            | Sum(ActualRevenue) | Total da receita lançada para todas as transações. |
| Custo real               | Sum(ActualCost)    | Total de custo lançado para todos os tipos de transação. |

### <a name="entity-projectaccountingcube_customer"></a>Entidade: ProjectAccountingCube\_Customer
**Fonte de dados:** CustTable

| Principal medida agregada | Campo                                             | descrição |
|---------------------------|---------------------------------------------------|-------------|
| Número de projetos        | COUNTA(ProjectAccountingCube\_Projects\[PROJETOS\]) | Contagem de projetos disponíveis. |

### <a name="entity-projectaccountingcube_forecasts"></a>Entidade: ProjectAccountingCube\_Forecasts
**Fonte de dados:** ProjTransBudget

| Principal medida agregada | Campo                  | descrição |
|---------------------------|------------------------|-------------|
| Custo de orçamento               | Sum(BudgetCost)        | Total de custo previsto para todos os tipos de transação. |
| Receita de orçamento            | Sum(BudgetRevenue)     | O total de receita acumulada/faturada prevista. |
| Margem bruta de orçamento       | Sum(BudgetGrossMargin) | A diferença entre a soma do total de receita prevista e a soma do total de custo previsto. |

### <a name="entity-projectaccountingcube_projectplancostsview"></a>Entidade: ProjectAccountingCube\_ProjectPlanCostsView
**Fonte de dados:** Projeto

| Principal medida agregada | Campo                    | descrição |
|---------------------------|--------------------------|-------------|
| Custo planejado              | Sum(SumOfTotalCostPrice) | Total de preço de custo em estimativas para todos os tipos de transação de projeto com tarefas planejadas. |

### <a name="entity-projectaccountingcube_projects"></a>Entidade: ProjectAccountingCube\_Projects
**Fonte de dados:** Projeto

| Principal medida agregada    | Campo | descrição |
|------------------------------|-------|-------------|
| Índice de desempenho de custo       | ProjectAccountingCube\_Projects\[Valor ganho\] ÷ ProjectAccountingCube\_Projects\[Total do custo real de tarefas concluídas\] | Cálculo do total do valor ganho dividido pelo total do custo real. |
| Índice de desempenho da agenda   | ProjectAccountingCube\_Projects\[Valor ganho\] ÷ ProjectAccountingCube\_Projects\[Total do custo planejado de tarefas concluídas\] | Cálculo do total do valor ganho dividido pelo total do custo planejado. |
| Porcentagem de trabalho concluído | Porcentagem de trabalho concluído = ProjectAccountingCube\_Projects\[Total do custo real de tarefas concluídas\] ÷ (ProjectAccountingCube\_Projects\[Total do custo real de tarefas concluídas\] + ProjectAccountingCube\_Projects\[Total do custo planejado do projeto\] – ProjectAccountingCube\_Projects\[Total do custo planejado de tarefas concluídas\]) | O percentual total de trabalho concluído com base no total do custo real das tarefas concluídas e no custo planejado do projeto. |
| Relação real de horas faturáveis  | ProjectAccountingCube\_Projects\[Total de horas do projeto faturáveis reais utilizadas\] ÷ (ProjectAccountingCube\_Projects\[Total de horas do projeto faturáveis reais utilizadas\] + ProjectAccountingCube\_Projects\[Total de horas do projeto faturáveis reais de custo indireto\]) | O total real de horas faturáveis, com base nas horas utilizadas e nas horas de custo indireto. |
| Valor obtido                 | ProjectAccountingCube\_Projects\[Total do custo planejado do projeto\] × ProjectAccountingCube\_Projects\[Porcentagem de trabalho concluído\] | Total do custo planejado multiplicado pelo percentual do trabalho concluído. |

### <a name="entity-projectaccountingcube_totalestimatedcosts"></a>Entidade: ProjectAccountingCube\_TotalEstimatedCosts 
**Fonte de dados:** ProjTable

| Principal medida agregada       | Campo               | descrição |
|---------------------------------|---------------------|-------------|
| Custo planejado de atividade concluído | Sum(TotalCostPrice) | Total de preço de custo em estimativas para todos os tipos de transação de projeto com tarefas concluídas. |


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
