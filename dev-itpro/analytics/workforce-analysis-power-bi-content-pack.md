---
title: "Conteúdo do Power BI de métricas de força de trabalho"
description: "Este tópico descreve o Microsoft Dynamics 365 for Operations - Conteúdo do Power BI de métricas de força de trabalho Ele explica como acessar os relatórios incluídos no pacote de conteúdo, além de fornecer informações sobre o modelo de dados e as entidades usados para criar o pacote de conteúdo."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User, IT Pro
ms.search.scope: Operations
ms.custom: 264084
ms.assetid: 8e700583-3a7d-4f5f-9ac8-58c4feed1a02
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: 388b6398488e6f316c1ec07a00182e81c1dc8d08
ms.openlocfilehash: d03692e39c51cc4eb0fe23ba263e52de2bf3c3da
ms.lasthandoff: 03/31/2017


---

# <a name="workforce-metrics-power-bi-content"></a>Conteúdo do Power BI de métricas de força de trabalho

[!include[banner](../includes/banner.md)]


Este tópico descreve o Microsoft Dynamics 365 for Operations - Conteúdo do Power BI de métricas de força de trabalho Ele explica como acessar os relatórios incluídos no pacote de conteúdo, além de fornecer informações sobre o modelo de dados e as entidades usados para criar o pacote de conteúdo.

<a name="accessing-the-content-pack"></a>Acessando o pacote de conteúdo
--------------------------

Você pode encontrar o pacote de conteúdo de métricas de força de trabalho na biblioteca de ativos compartilhados no Microsoft Dynamics Lifecycle Services (LCS). Para obter mais informações sobre como baixar o pacote de conteúdo e conectá-lo a seus dados do Microsoft Dynamics 365 for Operations, consulte [Conteúdo do Power BI no LCS da Microsoft e seus parceiros](power-bi-content-microsoft-partners.md).

## <a name="reports-that-are-included-in-the-content-pack"></a>Relatórios incluídos no pacote de conteúdo
Após a conexão do pacote de conteúdo aos dados do Dynamics 365 for Operations, os relatórios mostrarão os dados da sua organização. Se você nunca usou o Microsoft Power BI antes, você pode saber mais sobre ele na página [Aprendizado guiado para Power BI](https://powerbi.microsoft.com/en-us/guided-learning/?WT.mc_id=PBIService_GetData). Os relatórios incluídos no pacote de conteúdo têm gráficos e tabelas que contêm informações adicionais. A tabela a seguir descreve os relatórios.

| Relatório                                           | Conteúdo                                                                                                                                                                                                            |
|--------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Companhia de Análise de Pessoal, Departamento, Localização | Número de funcionários por empresa, número de funcionários por departamento, número de funcionários por local e número total de funcionários                                                                                                                           |
| Trabalho de Análise de Headcount, Etapa, Gerente            | Número de funcionários por cargo, número de funcionários por etapa, número de funcionários por gerente e número total de funcionários                                                                                                                                      |
| Análise de tendência de funcionários                         | O número de funcionários deste ano em relação ao ano passado pela empresa e pelo número de funcionários nos últimos 12 meses                                                                                                                        |
| Demografia da força de trabalho                           | Número de funcionários por idade e sexo, número de funcionários por origem étnica, número de funcionários por estado de veterano, número de funcionários por estado civil, número de estudantes em período integral, tempo médio de permanência, idade média e proporção de empregados do sexo feminino |
| Análise de posição                                | Posições abertas por departamento, posições abertas a preenchidas, posições ativas a inativas, e posições por departamento                                                                                                   |
| Análise de atrito                               | Atrito este ano versus ano passado, atrito, tempo médio de saída das pessoas, idade média das pessoas que saem e funcionários que deixam a empresa por motivo                                                                   |
| Pessoas por departamento                             | Funcionários com um número pessoal por departamento, posição e datas de início e término da atribuição                                                                                                                       |
| Análise de antiguidade                               | Média de anos de serviço por empresa e lista de antiguidade                                                                                                                                                              |
| Aniversários e anos de serviço               | Funcionários por anos de serviço e aniversários                                                                                                                                                                    |

Você pode filtrar os gráficos e blocos nesses relatórios e fixá-los no painel. Para obter mais informações sobre como filtrar e fixar no Power BI, consulte [Criar e configurar um painel](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-4-2-create-configure-dashboards).

## <a name="understanding-the-data-model-and-entities"></a>Noções básicas sobre o modelo de dados e as entidades
Os dados do Microsoft Dynamics 365 for Operations são usados para preencher os relatórios no pacote de conteúdo de métricas de força de trabalho. A seguinte tabela mostra as entidades nas quais o pacote de conteúdo foi baseado.

| Entidade                            | Conteúdo                                                                                                   | Relações com outras entidades                                                                                                                                                                                                                                                                                                |
|-----------------------------------|------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Workforce\_CalendarOffset         | Compensações de calendário para dividir relatórios                                                                          | Workforce\_PastPositionAssignment Workforce\_PositionTrend Workorce\_WorkerTrend Workforce\_TerminatedWorker                                                                                                                                                                                                                     |
| Workforce\_Company                | Empresas para filtrar relatórios                                                                             | Workforce\_CurrentCompensation Workforce\_CurrentWorker Workforce\_TerminatedWorker Workorce\_WorkerTrend                                                                                                                                                                                                                        |
| Workforce\_Compensation           | Taxa de pagamento e frequência com o tempo                                                                           | Workforce\_CurrentCompensation Workforce\_CurrentWorker Workforce\_TerminatedWorker Workorce\_WorkerTrend                                                                                                                                                                                                                        |
| Workforce\_CurrentCompensation    | Taxa de pagamento e frequência a partir da data atual                                                              | Workforce\_Company Workforce\_Compensation Workforce\_Demographics Workforce\_Job Workforce\_Position                                                                                                                                                                                                                            |
| Workforce\_CurrentPosition        | Posições a partir da data atual, equivalente ao horário integral (FTE), posições abertas e posições abertas a preenchidas | Workforce\_Job Workforce\_Position                                                                                                                                                                                                                                                                                               |
| Workforce\_CurrentWorker          | Trabalhadores a partir da data atual, idade e número de funcionários                                                         | Workforce\_Company Workforce\_Compensation Workforce\_GeographicLocation Workforce\_Performance Workforce\_WorkerName Workforce\_ReportsToWorkerName Workforce\_WorkerTitle Workforce\_Demographics Workforce\_Job Workforce\_Employment Workforce\_Position Workforce\_WorkerBenefit                                            |
| Workforce\_Date                   | Dias, semanas, meses e anos                                                                             | Workforce\_PastPositionAssignment Workforce\_PositionTrend Workforce\_TerminatedWorker Workorce\_WorkerTrend                                                                                                                                                                                                                     |
| Workforce\_Demographics           | Data de nascimento, gênero, origem étnica e estado civil                                                   | Workforce\_CurrentWorker Workforce\_TerminatedWorker Workorce\_WorkerTrend                                                                                                                                                                                                                                                       |
| Workforce\_Employment             | Data inicial, data final e data de transição                                                                  | Workforce\_CurrentWorker Workforce\_TerminatedWorker Workorce\_WorkerTrend                                                                                                                                                                                                                                                       |
| Workforce\_GeographicLocation     | Cidade, região, CEP e estado ou província                                                           | Workforce\_CurrentWorker Workforce\_TerminatedWorker Workorce\_WorkerTrend                                                                                                                                                                                                                                                       |
| Workforce\_Job                    | Função, tipo e título                                                                                  | Workforce\_CurrentPosition Workforce\_CurrentWorker                                                                                                                                                                                                                                                                              |
| Workforce\_JobPreferredSkill      |                                                                                                            |                                                                                                                                                                                                                                                                                                                                  |
| Workforce\_PastPositionAssignment | Motivo da atribuição, data inicial, data final e trabalho                                                           | Workforce\_CalendarOffset Workforce\_Date Workforce\_Job Workforce\_Position                                                                                                                                                                                                                                                     |
| Workforce\_Performance            | Classificação, descrição e modelo de classificação                                                                      | Workforce\_CurrentWorker Workforce\_TerminatedWorker Workorce\_WorkerTrend                                                                                                                                                                                                                                                       |
| Workforce\_PersonSkill            | Nível e habilidade                                                                                            | Workforce\_Skill                                                                                                                                                                                                                                                                                                                 |
| Workforce\_PersonSkillAnalysis    | Certificado, nível e habilidade                                                                                | Workforce\_Skill Workforce\_WorkerName                                                                                                                                                                                                                                                                                           |
| Workforce\_Position               | Departamento, FTE, posição, tipo de posição e título                                                        | Workforce\_CurrentPosition Workforce\_CurrentWorker                                                                                                                                                                                                                                                                              |
| Workforce\_PositionTrend          | Posições com o tempo, FTE e trabalho                                                                          | Workforce\_CalendarOffset Workforce\_Date Workforce\_Job Workforce\_Position                                                                                                                                                                                                                                                     |
| Workforce\_ReportsToWorkerName    | Nome, sobrenome e nome completo                                                                       | Workforce\_CurrentWorker Workforce\_TerminatedWorker Workorce\_WorkerTrend                                                                                                                                                                                                                                                       |
| Workforce\_Skill                  | Habilidade, tipo de habilidade e classificação                                                                              | Workforce\_PersonSkill Workforce\_PersonSkillAnalysis                                                                                                                                                                                                                                                                            |
| Workforce\_TerminatedWorker       | Trabalhadores demitidos, data da demissão, título, posição e trabalho                                             | Workforce\_Company Workforce\_Compensation Workforce\_GeographicLocation Workforce\_Performance Workforce\_WorkerName Workforce\_ReportsToWorkerName Workforce\_CalendarOffset Workforces\_Date Workforce\_WorkerTitle Workforce\_Demographics Workforce\_Employment Workforce\_Job Workforce\_Position Workforce\_WorkerBenefit |
| Workforce\_WorkerBenefit          | Data de efetivação, opção de benefício, plano de benefício e tipo de benefício                                             | Workforce\_CurrentWorker Workforce\_TerminatedWorker Workorce\_WorkerTrend                                                                                                                                                                                                                                                       |
| Workforce\_WorkerName             | Nome, sobrenome e nome completo                                                                       | Workforce\_CurrentWorker Workforce\_TerminatedWorker Workorce\_WorkerTrend Workforce\_PersonSkillAnalysis                                                                                                                                                                                                                        |
| Workforce\_WorkerTitle            | Título e data de tempo de serviço                                                                                   | Workforce\_CurrentWorker Workforce\_TerminatedWorker Workorce\_WorkerTrend                                                                                                                                                                                                                                                       |
| Workorce\_WorkerTrend             | Trabalhadores com o tempo, número de funcionários, empresa e posição                                                        | Workforce\_Company Workforce\_Compensation Workforce\_GeographicLocation Workforce\_Performance Workforce\_WorkerName Workforce\_ReportsToWorkerName Workforce\_CalendarOffset Workforces\_Date Workforce\_WorkerTitle Workforce\_Demographics Workforce\_Employment Workforce\_Job Workforce\_WorkerBenefit                     |

Essas entidades foram usadas para criar medidas calculadas no modelo de dados. Essas medidas calculadas são então usadas para calcular os KPIs (indicadores chave de desempenho) e os relatórios usados no pacote de conteúdo. Para incluir cálculos adicionais nos seus relatórios e painel, você pode baixar e modificar o arquivo CompensationandBenefits.pbix no LCS. Esse arquivo de trabalho é o modelo de dados padrão usado para criar o pacote de conteúdo. Após a realização de modificações, poderá criar um painel e pacote de conteúdo organizacional contendo as informações adicionadas.

## <a name="additional-resources"></a>Recursos adicionais
Estes são alguns links úteis relacionados às entidades e ao desenvolvimento de conteúdo do Power BI:

-   [Entidades de dados](https://blogs.msdn.microsoft.com/dynamicsaxbi/2016/06/09/power-bi-integration-with-entity-store-in-dynamics-ax-7-may-update/)
-   [Criando pacotes de conteúdo organizacionais](https://powerbi.microsoft.com/en-us/documentation/powerbi-service-organizational-content-packs-introduction/)
-   [Modelagem de dados por meio do Power BI](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-2-1-intro-modeling-data)
-   [Adicionando blocos do Power BI aos espaços de trabalho](https://blogs.msdn.microsoft.com/dynamicsaxbi/2016/07/06/pinning-power-bi-reports-to-dynamics-ax-client/)




