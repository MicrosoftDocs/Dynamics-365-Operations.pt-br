---
title: "Conteúdo Gerente de prática do Power BI"
description: "Este tópico descreve o que está incluído no conteúdo Gerente de prática do Power BI. Ele explica como acessar os relatórios incluídos no conteúdo, além de fornecer informações sobre o modelo de dados e as entidades usadas para criar o conteúdo."
author: KimANelson
manager: AnnBe
ms.date: 06/16/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations, UnifiedOperations
ms.assetid: 
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2017-06-30T00:00:00.000Z
ms.dyn365.version: Enterprise edition, July 2017 update
ms.translationtype: Human Translation
ms.sourcegitcommit: 993e88703f19dbeec435d07a4599cbbfcda563bc
ms.openlocfilehash: b63e31f3e4993c1fda229a54b4e5ef2fed824355
ms.contentlocale: pt-br
ms.lasthandoff: 06/20/2017

---

# <a name="practice-manager-power-bi-content"></a>Conteúdo Gerente de prática do Power BI

[!include[banner](../includes/banner.md)]

Este tópico descreve o que está incluído no conteúdo **Gerente de prática** do Microsoft Power BI. Ele explica como acessar os relatórios do Power BI, além de fornecer informações sobre o modelo de dados e as entidades usados para criar o pacote de conteúdo.

## <a name="overview"></a>Visão Geral

O conteúdo **Gerente de prática** do Power BI foi criado para gerentes de prática e para gerentes de projeto. Ele oferece métricas chave relacionadas aos projetos em que a organização estiver trabalhando. O painel apresenta uma visão geral dos projetos e de clientes relacionados. Um filtro no nível de relatório pode ser usado para relatar entidades legais específicas. Este conteúdo do Power BI extrai dados das medições agregadas contábeis do projeto.

O conteúdo **Gerente de prática** do Power BI contém cinco páginas de relatório: uma página de visão geral e quatro páginas que fornecem detalhes sobre custos e receitas do projeto, do gerenciamento do valor obtido e as métricas de hora divididas entre diversas dimensões.

Todos os valores no conteúdo são mostrados na moeda do sistema. Você pode definir a moeda do sistema na página **Parâmetros do sistema**.

## <a name="accessing-the-power-bi-content"></a>Acessando o conteúdo do Power BI
Se estiver usando o Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition com atualização de julho de 2017, o conteúdo do Power BI **Gerente de práticas** é mostrado na área de trabalho **Gerenciamento de projetos**.

## <a name="reports-that-are-included-in-the-power-bi-content"></a>Relatórios incluídos no conteúdo do Power BI

A tabela a seguir fornece detalhes sobre as métricas encontradas em cada página de relatório no conteúdo **Gerente de prática** do Power BI.

| Página de relatório       | Métrica |
|-------------------|---------|
| Visão geral de projetos | <ul><li>Projetos criados</li><li>Projetos previstos</li><li>Projetos em andamento</li><li>Número de projetos por estágio</li><li>Número de projetos por cidade</li><li>Receita real por cliente</li><li>Margem bruta de orçamento por projeto</li><li>Visão geral do gerenciamento de valores obtidos</li></ul> |
| Custo              | <ul><li>Custo real versus orçamento por mês</li><li>Custo real versus orçamento por ano</li><li>Custo real versus orçamento por categoria</li><li>Custo real por tipo de transação</li></ul> |
| Receita           | <ul><li>Receita real por mês</li><li>Receita real por CEP</li><li>Receita real versus orçamento por categoria</li><li>Receita real por setor do cliente</li></ul> |
| EVM               | Índice de custo e de desempenho de agenda por projeto |
| Horas             | <ul><li>Horas utilizadas faturáveis reais versus horas de custo indireto faturáveis reais versus horas do orçamento</li><li>Horas utilizadas faturáveis reais versus horas de custo indireto faturáveis reais por projeto</li><li>Horas utilizadas faturáveis reais versus horas de custo indireto faturáveis reais por recurso</li><li>Taxa de horas faturáveis reais por projeto</li><li>Taxa de horas faturáveis reais por recurso</li></ul> |

Os gráficos e os blocos em todos esses relatórios podem ser filtrados e fixados no painel. Para saber mais sobre como filtrar e fixar no Power BI, veja [Criar e configurar um painel](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-4-2-create-configure-dashboards/). Você também pode usar a funcionalidade Exportar dados subjacentes para exportar os dados subjacentes resumidos em uma visualização.

## <a name="extending-the-power-bi-content"></a>Aumentando o conteúdo do Power BI
Usando os pacotes de conteúdo disponíveis no Microsoft Dynamics Lifecycle Services (LCS), você pode fornecer grande análise às pessoas que não acessam o Microsoft Dynamics 365. Você pode modificar esses pacotes de conteúdo para que eles incluam outros relatórios ou imagens e, em seguida, publicá-los no locatário do Power BI.com para análise. 

Você pode localizar o conteúdo do Power BI **Gerente de práticas** na biblioteca de ativos compartilhados do LCS. Para obter mais informações sobre como baixar o pacote de conteúdo e implementá-lo na sua organização, consulte [Conteúdo do Power BI no LCS da Microsoft e seus parceiros](power-bi-content-microsoft-partners.md). Para ver uma demonstração que mostra como implementar o conteúdo do Power BI, veja o Office Mix [Conteúdo do Power BI da Microsoft e seus parceiros no Dynamics Lifecycle Services](https://mix.office.com/watch/9puyb1b2xs1w).

Certifique-se de baixar o conteúdo de **Gerente de práticas** que se aplica à versão do Dynamics 365 que você está usando.

## <a name="understanding-the-data-model-and-entities"></a>Noções básicas sobre o modelo de dados e as entidades

Os seguintes dados são usados para preencher as páginas de relatório no conteúdo do Power BI **Gerente de práticas**. Esses dados são representadas como medições agregadas que foram preparadas no Repositório de entidades. O Repositório de entidades é um banco de dados do Microsoft SQL Server otimizado para análise. Para obter mais informações, consulte [Visão geral da integração do Power BI com a loja Entidade](power-bi-integration-entity-store.md).

As seções a seguir descrevem as medidas agregadas usadas em cada entidade.

### <a name="entity-projectaccountingcubeactualhourutilization"></a>Entidade: ProjectAccountingCube_ActualHourUtilization
**Fonte de dados:** ProjEmplTrans

| Principal medida agregada      | Campo                              | descrição | 
|--------------------------------|------------------------------------|-------------|
| Horas utilizadas faturáveis reais | Sum(ActualUtilizationBillableRate) | Total de horas utilizadas faturáveis reais. |
| Horas de custo Indireto real faturável   | Sum(ActualBurdenBillableRate)      | Total de taxa de custo indireto real. |

### <a name="entity-projectaccountingcubeactuals"></a>Entidade: ProjectAccountingCube_Actuals
**Fonte de dados:** ProjTransPosting

| Principal medida agregada | Campo              | descrição | 
|---------------------------|--------------------|-------------|
| Receita real            | Sum(ActualRevenue) | Total da receita lançada para todas as transações. |   
| Custo real               | Sum(ActualCost)    | Total de custo lançado para todos os tipos de transação. |

### <a name="entity-projectaccountingcubecustomer"></a>Entidade: ProjectAccountingCube_Customer
**Fonte de dados:** CustTable

| Principal medida agregada | Campo                                            | descrição | 
|---------------------------|--------------------------------------------------|-------------|
| Número de projetos        | COUNTA(ProjectAccountingCube_Projects[PROJECTS]) | Contagem de projetos disponíveis. |


### <a name="entity-projectaccountingcubeforecasts"></a>Entidade: ProjectAccountingCube_Forecasts
**Fonte de dados:** ProjTransBudget

| Principal medida agregada | Campo                  | descrição | 
|---------------------------|------------------------|-------------|
| Custo de orçamento               | Sum(BudgetCost)        | Total de custo previsto para todos os tipos de transação. |
| Receita de orçamento            | Sum(BudgetRevenue)     | O total de receita acumulada/faturada prevista.  |
| Margem bruta de orçamento       | Sum(BudgetGrossMargin) | A diferença entre a soma do total de receita prevista e a soma do total de custo previsto. |

### <a name="entity-projectaccountingcubeprojectplancostsview"></a>Entidade: ProjectAccountingCube_ProjectPlanCostsView
**Fonte de dados:** Projeto

| Principal medida agregada | Campo                    | descrição | 
|---------------------------|--------------------------|-------------|
| Custo planejado              | Sum(SumOfTotalCostPrice) | Total de preço de custo em estimativas para todos os tipos de transação de projeto com tarefas planejadas. |

### <a name="entity-projectaccountingcubeprojects"></a>Entidade: ProjectAccountingCube_Projects
**Fonte de dados:** Projeto

| Principal medida agregada    | Campo | descrição | 
|------------------------------|-------|-------------|
| Índice de desempenho de custo       | ProjectAccountingCube_Projects[Valor ganho]/ProjectAccountingCube_Projects[Total de custo real de tarefas concluídas] | Cálculo do total do valor ganho dividido pelo total do custo real. |
| Índice de desempenho da agenda   | ProjectAccountingCube_Projects[Valor ganho]/ProjectAccountingCube_Projects[Total de custo planejado de tarefas concluídas] | Cálculo do total do valor ganho dividido pelo total do custo planejado. |
| Porcentagem de trabalho concluído | Percentual de trabalho concluído = ProjectAccountingCube_Projects[Total do custo real de tarefas concluídas]/(ProjectAccountingCube_Projects[Total do custo real de tarefas concluídas] + ProjectAccountingCube_Projects[Total do custo planejado do projeto] - ProjectAccountingCube_Projects[Total do custo planejado de tarefas concluídas]) | O percentual total de trabalho concluído com base no total do custo real das tarefas concluídas e no custo planejado do projeto. |
| Relação real de horas faturáveis  | ProjectAccountingCube_Projects[Total de horas do projeto faturáveis reais utilizadas]/(ProjectAccountingCube_Projects[Total de horas do projeto faturáveis reais utilizadas] + ProjectAccountingCube_Projects[Total de horas do projeto faturáveis reais de custo indireto]) | O total real de horas faturáveis, com base nas horas utilizadas e nas horas de custo indireto. |
| Valor obtido                 | ProjectAccountingCube_Projects[Total do custo planejado do projeto] * ProjectAccountingCube_Projects[Percentual do trabalho concluído] | Total do custo planejado multiplicado pelo percentual do trabalho concluído. |

### <a name="entity-projectaccountingcubetotalestimatedcosts"></a>Entidade: ProjectAccountingCube_TotalEstimatedCosts 
**Fonte de dados:** ProjTable

| Principal medida agregada       | Campo               | descrição | 
|---------------------------------|---------------------|-------------|
| Custo planejado de atividade concluído | Sum(TotalCostPrice) | Total de preço de custo em estimativas para todos os tipos de transação de projeto com tarefas concluídas. |

