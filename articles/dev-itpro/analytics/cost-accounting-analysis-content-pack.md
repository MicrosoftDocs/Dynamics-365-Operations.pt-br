---
title: "Conteúdo do Power BI Análise de contabilização de custos"
description: "Este tópico descreve o que está incluído no conteúdo do Power BI Análise de contabilização de custos. Ele explica como acessar os relatórios do Power BI, além de fornecer informações sobre o modelo de dados e as entidades usados para criar o pacote de conteúdo."
author: AndersGirke
manager: AnnBe
ms.date: 06/16/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 270274
ms.assetid: b74549df-35d5-4f2f-b3c7-405b0d38ea78
ms.search.region: Global
ms.author: aevengir
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: b49cfe39732a450e4723419c50d8bcc3d64b7ec9
ms.openlocfilehash: f596f84463f46fc37b14b77bd335b9ed8a62eea9
ms.contentlocale: pt-br
ms.lasthandoff: 09/29/2017

---

# <a name="cost-accounting-analysis-power-bi-content"></a>Conteúdo do Power BI Análise de contabilização de custos

[!include[banner](../includes/banner.md)]

Este tópico descreve o que está incluído no conteúdo do Microsoft Power BI **Análise de contabilização de custos**. Ele explica como acessar os relatórios do Power BI, além de fornecer informações sobre o modelo de dados e as entidades usados para criar o pacote de conteúdo.

## <a name="overview"></a>Visão Geral

O conteúdo do Power BI **Análise de contabilização de custos** destina-se a controladores de custo ou qualquer pessoa responsável por realizar o controle de custos de uma organização. Ele inclui as principais métricas, como custo, magnitude e taxa de custo por custo real, custo de orçamento e custo de orçamento flexível. Ele usa dados de transação do módulo **Contabilização de custos** e fornece uma visão agregada dos custos de toda a organização em uma moeda de relatório. Os gerentes podem filtrar os dados por objetos de custo para realizar o controle de custos de suas unidades organizacionais, mesmo que a organização possa ter várias entidades legais. 

Como o conteúdo **Análise de contabilização de custos** destaca variações entre os custos reais e os custos orçados, os gerentes podem ser notificados sobre as tendências positivas e negativas de suas unidades operacionais. Os gerentes podem fazer busca detalhada em hierarquias de elementos de custo ou em elementos de custo individual. Assim, os gerentes podem ter uma ideia aprofundada de como as variações de custo ocorreram e adotar medidas eficazes. 

O conteúdo **Análise de contabilização de custos** permite que os contadores analisem como o custo flui por meio dos objetos de custo de toda a organização. 

Para saber mais sobre contabilização de custos, consulte [Pagina inicial de contabilização de custos](../../financials/cost-accounting/cost-accounting-home-page.md). 

Definindo a segurança de nível de acesso em Contabilização de custos e combinando-a com a segurança de nível de linha no Power BI, você pode conceder a todos os proprietários de objetos de custo acesso ao conteúdo do Power BI **Análise de contabilização de custos**. Todos os dados nas visualizações serão então filtrados no nível de acesso que é controlado em Contabilização de custos. Para saber mais sobre a segurança de nível de acesso e linha, consulte [Definição de segurança do conteúdo Contabilização de custos para o Power BI](setup-security-cost-accounting-content-pack.md).

## <a name="accessing-the-power-bi-content"></a>Acessando o conteúdo do Power BI
Você pode encontrar o conteúdo do Power BI **Análise de contabilização de custos** na biblioteca de ativos compartilhados em Microsoft Dynamics Lifecycle Services (LCS). Para obter mais informações sobre como baixar o pacote de conteúdo e implementá-lo na sua organização, consulte [Conteúdo do Power BI no LCS da Microsoft e seus parceiros](power-bi-content-microsoft-partners.md). Para ver uma demonstração que mostra como implementar o conteúdo do Power BI, veja o Office Mix [Conteúdo do Power BI da Microsoft e seus parceiros no Dynamics Lifecycle Services](https://mix.office.com/watch/9puyb1b2xs1w).

Certifique-se de baixar o conteúdo de **Análise de contabilidade de custo** que se aplica à versão do Microsoft Dynamics 365 que você está usando.

> [!NOTE]
> KB 4011327 é um pré-requisito para esse conteúdo do Power BI. Depois de iniciar sessão no LCS, você pode acessar o KB aqui em <https://fix.lcs.dynamics.com/issue/results/?q=kb4011327>.

## <a name="metrics-that-are-included-in-the-power-bi-content"></a>Métricas incluídas no conteúdo do Power BI
O conteúdo inclui um conjunto de páginas de relatório. Cada página consiste em um conjunto de métricas visualizadas, como gráficos, blocos e tabelas. A seguinte tabela fornece uma visão geral das visualizações no conteúdo do Power BI **Análise de contabilização de custos**.

| Página de relatório                      | Gráfico                                                                                                                         | Bloco                                          |
|----------------------------------|-------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------|
| Controle de custos por período fiscal    | Custo real e custo de orçamento por nível hierárquico de elemento de custo                                                                   | Custo real vs. custo de orçamento                    |
|                                  | Variação de orçamento por nível hierárquico de elemento de custo                                                                               | Taxa de custo real vs. taxa de custo de orçamento          |
|                                  | Variação dos 10 principais orçamentos em porcentagem por elemento de custo                                                                          | Magnitude real vs. magnitude de orçamento          |
| Controle de custo por ano até a data     | Custo real e custo de orçamento por período de ano civil                                                                           | Custo real vs. custo de orçamento                    |
|                                  | Variação de orçamento por período de ano civil                                                                                       | Taxa de custo real vs. taxa de custo de orçamento          |
|                                  | Variação dos 10 principais orçamentos em porcentagem por elemento de custo                                                                          | Magnitude real vs. magnitude de orçamento          |
| Taxa de custo por ano fiscal         | Taxa de custo real por comportamento de custo                                                                                             | Taxa de custo real vs. taxa de custo de orçamento          |
|                                  | Taxa de custo real, variação de taxa de custo de orçamento, porcentagem de taxa de custo de orçamento e taxa de custo de orçamento por nível hierárquico de elemento de custo | Magnitude real vs. magnitude de orçamento          |
|                                  | Variação de orçamento por nível hierárquico de elemento de custo                                                                               |                                               |
|                                  | Variação dos 10 principais orçamentos em porcentagem por elemento de custo                                                                          |                                               |
| Orçamento flexível por período fiscal | Custo real, custo de orçamento e custo de orçamento flexível por nível hierárquico de elemento de custo                                             | Magnitude real vs. magnitude de orçamento          |
|                                  | Variação de orçamento e variação de orçamento flexível por nível hierárquico de elemento de custo                                                  | Custo real vs. custo de orçamento flexível           |
|                                  | Custo real, custo de orçamento e custo flexível por comportamento de custo e nível hierárquico de elemento de custo                                  | Taxa de custo real vs. taxa de custo de orçamento flexível |
| Demonstrativo de custos por período fiscal  | Custo real por nível hierárquico de elemento de custo e nome do membro de dimensão de objeto de custo                                             |                                               |
|                                  | Custo real por nome do membro de dimensão de objeto de custo e nome do membro de dimensão de elemento de custo                                       |                                               |

## <a name="understanding-the-data-model-and-entities"></a>Noções básicas sobre o modelo de dados e as entidades
Os seguintes dados são usados para preencher as páginas de relatório no conteúdo do Power BI **Análise de contabilidade de custo**. Esses dados são representadas como medições agregadas que foram preparadas no Repositório de entidades. O Repositório de entidades é um banco de dados do Microsoft SQL Server otimizado para análise. Para obter mais informações, consulte [Visão geral da integração do Power BI com a loja Entidade](power-bi-integration-entity-store.md). 

As principais medidas agregadas a seguir são usadas como base do conteúdo.

| Entidade                  | Principal medida agregada | Fonte de dados para Dynamics 365      | Campo     | descrição                                        |
|-------------------------|---------------------------|-----------------------------------|-----------|----------------------------------------------------|
| Entradas de contabilização de custos | SUM(Valor)               | CAMDATAAggregatedCostEntry        | Valor    | O valor na moeda contábil de contabilização de custos. |
| Entradas de estatísticas     | SUM(Magnitude)            | CAMDATAAggregatedStatisctialEntry | Magnitude |                                                    |

A tabela a seguir mostra como as principais medidas agregadas são usadas para criar diversas medidas calculadas no conjunto de dados do conteúdo.

| Medição                                       | Como a medida é calculada                                                                                          |
|-----------------------------------------------|------------------------------------------------------------------------------------------------------------------------|
| Custo real                                   | CALCULATE('Entradas de contabilização de custos'\[Medida\], 'Versões de transação'\[ISSOURCEVERSIONBUDGET\_VALOR\] = 0)            |
| Custo de orçamento                                   | CALCULATE('Entradas de contabilização de custos'\[Medida\], 'Versões de transação'\[ISSOURCEVERSIONBUDGET\_VALOR\] = 1)            |
| Variação de custo de orçamento                          | \[Custo de orçamento\] - \[Custo real\]                                                                                      |
| Porcentagem de variação de orçamento                    | IF(\[Custo de orçamento\] = 0, blank(), \[Variação de orçamento\] / \[Custo de orçamento\])                                                |
| Magnitude real                              | CALCULATE('Entradas de estatísticas'\[FullMagnitude\], 'Versões de transação'\[ISSOURCEVERSIONBUDGET\_VALOR\] = 0)          |
| Magnitude de orçamento                              | CALCULATE(\[FullMagnitude\], 'Versões de transação'\[ISSOURCEVERSIONBUDGET\_VALOR\] = 1)                               |
| Variação estatística de orçamento                   | \[Magnitude de orçamento\] - \[Magnitude real\]                                                                            |
| Porcentagem de variação estatística de orçamento        | IF(\[Magnitude de orçamento\] = 0, blank(), \[Variação estatística de orçamento\] / \[Magnitude de orçamento\])                          |
| Taxa de custo real                              | IF(\[Magnitude real\] = 0, BLANK(), \[Custo real\] / \[Magnitude real\])                                          |
| Taxa de custo do orçamento                              | IF(\[Magnitude de orçamento\] = 0, BLANK(), \[Custo de orçamento\] / \[Magnitude de orçamento\])                                          |
| Variação de taxa de custo de orçamento                     | \[Taxa de custo do orçamento\] - \[Taxa de custo real\]                                                                            |
| Porcentagem de variação de taxa de custo de orçamento          | IF(\[Custo de orçamento\] = 0, blank(), \[Variação taxa de custo de orçamento\] / \[Taxa de custo de orçamento\])                                 |
| Custo de orçamento fixo                             | CALCULATE(\[Custo de orçamento\], 'Entradas de contabilização de custos'\[COSTBEHAVIOR\] = 1)                                              |
| Custo de orçamento variável                          | CALCULATE(\[Custo de orçamento\], 'Entradas de contabilização de custos'\[COSTBEHAVIOR\] = 2)                                              |
| Custo de orçamento flexível fixo                    | \[Custo de orçamento fixo\]                                                                                                  |
| Custo de orçamento flexível variável                 | IF(\[Magnitude de orçamento\] = 0, BLANK(), (\[Custo de orçamento variável\] / \[Magnitude de orçamento\]) \* \[Magnitude real\])       |
| Custo de orçamento flexível                          | \[Custo de orçamento flexível fixo\] + \[Custo de orçamento flexível variável\]                                                     |
| Variação de orçamento flexível                      | \[Custo de orçamento flexível\] - \[Custo real\]                                                                             |
| Porcentagem de variação de orçamento flexível           | IF(\[Custo de orçamento flexível\] = 0, BLANK(), \[Variação de orçamento flexível\] / \[Custo de orçamento flexível\])                     |
| Taxa de custo de orçamento flexível                     | IF(\[Magnitude real\] = 0, BLANK(), \[Custo de orçamento flexível\] / \[Magnitude real\])                                 |
| Variação de taxa de custo de orçamento flexível            | \[Taxa de custo de orçamento flexível\] - \[Taxa de custo real\]                                                                   |
| Porcentagem de variação de taxa de custo de orçamento flexível | IF(\[Taxa de custo de orçamento flexível\] = 0, BLANK(), \[Variação de taxa de custo de orçamento flexível\] / \[Taxa de custo de orçamento flexível\]) |

As principais dimensões a seguir são usadas como filtros para cortar as medidas agregadas para obter uma granularidade maior e fornecer uma introspecção analítica mais profunda.

| Entidade                             | Exemplos de atributos                                                                                               |
|------------------------------------|----------------------------------------------------------------------------------------------------------------------|
| Razões de contabilização de custos            | Razão de contabilização de custos                                                                                               |
| Unidades de controle de custo                 | Nome da unidade de controle de custo                                                                                               |
| Dimensões do elemento de custo            | Nome da dimensão dos elementos de custo, nome de membro de dimensão do elemento de custo e descrição de membro de dimensão do elemento de custo          |
| Dimensões de objeto de custo             | Nome da dimensão do objeto de custo, nome de membro de dimensão do objeto de custo e descrição de membro de dimensão do objeto de custo              |
| Dimensões estatísticas             | Nome da dimensão estatística, nome de membro de dimensão estatística e descrição de membro de dimensão estatística              |
| Hierarquias da dimensão de objeto de custo  | Nome da hierarquia de dimensão de objeto de custo, nível da hierarquia de dimensão de objeto de custo e árvore da hierarquia de dimensão de objeto de custo    |
| Hierarquias da dimensão de elemento de custo | Nome da hierarquia de dimensão de elemento de custo, nível da hierarquia de dimensão de elemento de custo e árvore da hierarquia de dimensão de elemento de custo |
| Hierarquias da dimensão estatística  | Nome da hierarquia de dimensão estatística, nível da hierarquia de dimensão estatística e árvore da hierarquia de dimensão estatística    |
| Versões de transação               | Nome da versão                                                                                                         |
| Calendários fiscais                   | Calendário, descrição do calendário                                                                                       |
| Anos fiscais                       | Ano civil                                                                                                        |
| Períodos fiscais                     | Período de ano civil                                                                                                 |

