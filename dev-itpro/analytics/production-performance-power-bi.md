---
title: "Conteúdo do Power BI Desempenho de produção"
description: "Este tópico descreve o que está incluído no conteúdo do Power BI Desempenho de produção. Ele explica como acessar os relatórios do Power BI, além de fornecer informações sobre o modelo de dados e as entidades usados para criar o pacote de conteúdo."
author: sericks
manager: AnnBe
ms.date: 06/16/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User, IT Pro
ms.search.scope: Core, Operations, UnifiedOperations
ms.search.region: Global
ms.author: aevengir
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: Human Translation
ms.sourcegitcommit: 298ac47e2253f8add1aa3938dda15afe186afbeb
ms.openlocfilehash: 915ff93edff0f68f52a536ad169c8f0f917ac9b2
ms.contentlocale: pt-br
ms.lasthandoff: 06/20/2017

---

# <a name="production-performance-power-bi-content"></a>Conteúdo do Power BI Desempenho de produção

[!include[banner](../includes/banner.md)]

Este tópico descreve o que está incluído no conteúdo do Microsoft Power BI **Desempenho de produção**. Ele explica como acessar os relatórios do Power BI, além de fornecer informações sobre o modelo de dados e as entidades usados para criar o pacote de conteúdo.

## <a name="overview"></a>Visão Geral

O conteúdo do Power BI **Desempenho de produção** destina-se a gerentes de produção ou indivíduos na organização responsáveis ​​pelo controle de produção.

Os relatórios que estão incluídos permitem que você use o Power BI para monitorar o desempenho das operações de fabricação em relação à execução, qualidade e custo atempados. Os relatórios usam dados transacionais de ordens de produção e ordens por lotes e fornecem uma visão agregada das métricas de produção de toda a empresa e uma quebra de métricas por produto e recurso.

O conteúdo do Power BI destaca a capacidade da organização de completar a produção a tempo e na íntegra. O desempenho futuro é projetado com base nos planos de produção. Relatórios abrangentes fornecem informações detalhadas sobre os defeitos do produto causados ​​pela produção e também as taxas de defeito para recursos e operações.

As variações de produção são calculadas como a diferença entre o custo estimado e o custo realizado. A variação de produção é calculada como a diferença entre os custos ativos e os realizados. As variações de produção são calculadas quando as ordens de produção ou ordens de lote atingem o status **Finalizado**.

O conteúdo do Power BI **Desempenho de produção** contém dados que se originam de ordens de produção e de ordens de lotes. Os relatórios não incluem dados relacionados às produções de Kanban.

## <a name="accessing-the-power-bi-content"></a>Acessando o conteúdo do Power BI
Se você estiver usando o Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition de julho de 2017, o conteúdo do Power BI **Desempenho de produção** é mostrado na página **Desempenho de produção** (**Controle de produção** > **Consultas e relatórios** > **Análise de desempenho de produção** > **Desempenho de produção**). 

## <a name="metrics-that-are-included-in-the-power-bi-content"></a>Métricas incluídas no conteúdo do Power BI

O conteúdo do Power BI **Desempenho de produção** inclui um conjunto de páginas do relatório. Cada página consiste em um conjunto de métricas visualizadas, como gráficos, blocos e tabelas.

A tabela a seguir fornece uma visão geral das visualizações incluídas.

| Página de relatório                                | Gráficos                                               | Blocos |
|--------------------------------------------|------------------------------------------------------|-------|
| Desempenho da produção                     | <ul><li>Número de produção por data</li><li>Número de produções por produto e grupo de itens</li><li>Número de produções planejadas por data</li><li>10 piores produtos por prazo & totalidade</li></ul> | <ul><li>Total de ordens</li><li>No prazo e na totalidade</li><li>Incompleto %</li><li>Antecipada %</li><li>Atrasado %</li></ul> |
| Defeitos por produto                         | <ul><li>Taxa defeituosa (ppm) por data</li><li>Taxa defeituosa (ppm) por produto e grupo de itens</li><li>Quantidade produzida por data</li><li>10 melhores produtos por taxa efetiva</li></ul> | <ul><li>Taxa defeituosa (ppm)</li><li>Quantidade com defeito</li><li>Quantidade total</li></ul> |
| Tendência de defeitos por produto                   | Taxa de defeito (ppm) por quantidade produzida | Taxa de defeito (ppm) |
| Defeitos por recurso                        | <ul><li>Taxa de defeito (ppm) por data</li><li>Taxa de defeito (ppm) por recurso e site</li><li>Taxa de defeito (ppm) por operação</li><li>10 principais recursos por taxa de defeito</li></ul> | Quantidade com defeito |
| Tendência de defeitos por recurso                  | Taxa de defeito (ppm) por quantidade processada | |
| Variações de produção para os custos de ordem de produção | <ul><li>Variação de produção por data e tipo de grupo de custo</li><li>Variação de produção por site e tipo de grupo de custo</li><li>Os 10 melhores produtos com variação de produção desfavorável</li><li>As 10 principais variações de produção desfavoráveis por recurso</li></ul> | <ul><li>Custo realizado</li><li>Variação de produção</li><li>Variação de produção %</li></ul> |

## <a name="extending-the-power-bi-content"></a>Aumentando o conteúdo do Power BI
Usando os pacotes de conteúdo disponíveis no Microsoft Dynamics Lifecycle Services (LCS), você pode fornecer grande análise às pessoas que não acessam o Microsoft Dynamics 365. Você pode modificar esses pacotes de conteúdo para que eles incluam outros relatórios ou imagens e, em seguida, publique os pacotes de conteúdo no locatário do Power BI.com para análise.

Você pode encontrar o conteúdo do Power BI **Desempenho de produção** na biblioteca de ativos compartilhados no LCS. Para obter mais informações sobre como baixar o pacote de conteúdo e implementá-lo na sua organização, consulte [Conteúdo do Power BI no LCS da Microsoft e seus parceiros](power-bi-content-microsoft-partners.md). Para ver uma demonstração que mostra como implementar o conteúdo do Power BI, veja o Office Mix [Conteúdo do Power BI da Microsoft e seus parceiros no Dynamics Lifecycle Services](https://mix.office.com/watch/9puyb1b2xs1w).

Certifique-se de baixar o conteúdo de **Desempenho de produção** que se aplica à versão do Dynamics 365 que você está usando.

> [!NOTE]
> Se você estiver usando o Microsoft Dynamics 365 for Operations versão 1611, o KB 4011327 é um pré-requisito para este conteúdo de Power BI. Depois de iniciar sessão no LCS, você pode acessar o KB em https://fix.lcs.dynamics.com/issue/results/?q=kb4011327.

## <a name="understanding-the-data-model-and-entities"></a>Noções básicas sobre o modelo de dados e as entidades

Os seguintes dados são usados para as páginas de relatório no conteúdo do Power BI **Desempenho de produção**. Esses dados são representadas como medições agregadas que foram preparadas no Repositório de entidades. O Repositório de entidades é um banco de dados do Microsoft SQL Server otimizado para análise. Para saber mais sobre a loja da entidade, consulte [Integração do Power BI com o armazenamento de entidade](power-bi-integration-entity-store.md).

A tabela a seguir mostra as principais medidas agregadas que são usadas como base do conteúdo do Power BI.

| Entidade                   | Principais medidas agregadas  | A fonte de dados para o Finance and Operations | Campo              |
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
| Variação de produção %   | SUM('Variação de produção'[Variação de produção]) / SUM('Variação de produção'[Custo estimado]) |
| Todas as ordens planejadas       | COUNTROWS('Ordem de produção planejada') |
| Antecipada                    | COUNTROWS(FILTRO('Ordem de produção planejada', Ordem de produção planejada'[Data de término planejada] \< 'Ordem de produção planejada'[Data do requisito])) |
| Atrasada                     | COUNTROWS(FILTRO('Ordem de produção planejada', Ordem de produção planejada'[Data de término planejada] \> 'Ordem de produção planejada'[Data do requisito])) |
| No prazo                  | COUNTROWS(FILTRO('Ordem de produção planejada', Ordem de produção planejada'[Data de término planejada] = 'Ordem de produção planejada'[Data do requisito])) |
| No prazo %                | IF ( 'Ordem de produção planejada'[No prazo] \<\> 0, 'Ordem de produção planejada'[No prazo], IF ('Ordem de produção planejada'[Todas as ordens planejadas] \<\> 0, 0, BLANK()) ) / 'Ordem de produção planejada'[Todas as ordens planejadas] |
| Concluídos                | COUNTROWS(FILTRO('Ordem de produção', 'Ordem de produção'[Is RAF'ed] = TRUE)) |
| Taxa defeituosa (ppm)     | IF( 'Ordem de produção'[Quantidade total] = 0, BLANK(), (SUM('Ordem de produção'[Quantidade defeituosa]) / 'Ordem de produção'[Quantidade total]) \* 1000000) |
| Taxa de produção em atraso  | 'Ordem de produção'[Atrasada \#] / 'Ordem de produção'[Concluída] |
| Antecipadamente e na totalidade          | COUNTROWS(FILTRO('Ordem de produção', 'Ordem de produção'[Está na totalidade] = TRUE && 'Ordem de produção'[Está antecipada] = TRUE)) |
| Antecipada \#                 | COUNTROWS(FILTRO('Ordem de produção', 'Ordem de produção'[Está antecipada] = TRUE)) |
| Antecipada %                  | IFERROR( IF('Ordem de produção'[Antecipada \#] \<\> 0, 'Ordem de produção'[Antecipada \#], IF('Ordem de produção'[Total de ordens] = 0, BLANK(), 0)) / 'Ordem de produção'[Total de ordens], BLANK()) |
| Incompleto               | COUNTROWS(FILTRO('Ordem de produção', 'Ordem de produção'[Está na totalidade] = FALSE && 'Ordem de produção'[Is RAF'ed] = TRUE)) |
| Incompleto %             | IFERROR( IF('Ordem de produção'[Incompleta] \<\> 0, 'Ordem de produção'[Incompleta], IF('Ordem de produção'[Total de ordens] = 0, BLANK(), 0)) / 'Ordem de produção'[Total de ordens], BLANK()) |
| Está atrasada               | 'Ordem de produção'[Is RAF'ed] = TRUE && 'Ordem de produção'[Valor atrasado] = 1 |
| Está antecipado                 | 'Ordem de produção'[Is RAF'ed] = TRUE && 'Ordem de produção'[Dias de atraso] \< 0 |
| Está na totalidade               | 'Ordem de produção'[Boa quantidade] \>= 'Ordem de produção'[Quantidade programada] |
| É RAF'ed                | 'Ordem de produção'[Valor de status de produção] = 5 \|\| 'Ordem de produção'[Valor de status de produção] = 7 |
| Atrasado e na totalidade           | COUNTROWS(FILTRO('Ordem de produção', 'Ordem de produção'[Está na totalidade] = TRUE && 'Ordem de produção'[Está atrasada] = TRUE)) |
| Atrasado \#                  | COUNTROWS(FILTRO('Ordem de produção', 'Ordem de produção'[Está atrasada] = TRUE)) |
| Atrasado %                   | IFERROR( IF('Ordem de produção'[Atrasada \#] \<\> 0, 'Ordem de produção'[Atrasada \#], IF('Ordem de produção'[Total de ordens] = 0, BLANK(), 0)) / 'Ordem de produção'[Total de ordens], BLANK()) |
| No prazo e na totalidade        | COUNTROWS(FILTRO('Ordem de produção', 'Ordem de produção'[Está na totalidade] = TRUE && 'Ordem de produção'[Está atrasada] = FALSE && 'Ordem de produção'[Está antecipada] = FALSE)) |
| No prazo e na totalidade      | IFERROR( IF('Ordem de produção'[No prazo e na totalidade] \<\> 0, 'Ordem de produção'[No prazo e na totalidade], IF('Ordem de produção'[Concluída] = 0, BLANK(), 0)) / 'Ordem de produção'[Concluída], BLANK()) |
| Total de ordens             | COUNTROWS('Ordem de produção') |
| Quantidade total           | SUM('Ordem de produção'[Boa quantidade]) + SUM('Ordem de produção'[Quantidade com defeito]) |
| Taxa de defeito (ppm)        | IF( 'Transações de roteiro'[Quantidade processada] = 0, BLANK(), (SUM('Transações de roteiro'[Quantidade com defeito]) / 'Transações de roteiro'[Quantidade processada]) \* 1000000) |
| Taxa mista de defeitos (ppm) | IF( 'Transações de roteiro'[Quantidade total mista] = 0, BLANK(), (SUM('Transações de roteiro'[Quantidade com defeito]) / 'Transações de roteiro'[Quantidade total mista]) \* 1000000) |
| Quantidade processada       | SUM('Transações de roteiro'[Boa quantidade]) + SUM('Transações de roteiro'[Quantidade com defeito]) |
| Quantidade mista total     | SUM('Ordem de produção'[Boa quantidade]) + SUM('Transações de roteiro'[Quantidade com defeito]) |

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

## <a name="additional-resources"></a>Recursos adicionais

Estes são alguns links úteis relacionados às entidades e ao desenvolvimento de conteúdo do Power BI:

- [Entidades de dados](https://ax.help.dynamics.com/en/wiki/data-entities/)
- [Criando pacotes de conteúdo organizacionais](https://powerbi.microsoft.com/en-us/documentation/powerbi-service-organizational-content-packs-introduction/)
- [Modelagem de dados por meio do Power BI](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-2-1-intro-modeling-data)
- [Adicionando blocos do Power BI aos espaços de trabalho](http://ax.help.dynamics.com/en/wiki/configuring-powerbi-integration/)

