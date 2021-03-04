---
title: Conteúdo de competências e desenvolvimento de funcionários do Power BI
description: Este tópico descreve o conteúdo de desenvolvimento e competências de Funcionários do Power BI.
author: jcart1106
manager: AnnBe
ms.date: 12/19/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: 263894
ms.assetid: 7d375d8a-b2de-4bec-b575-93d1d4521b79
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: bed461677cbdfa57b0a198b7179eccb9828dc944
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2020
ms.locfileid: "4687117"
---
# <a name="employee-competencies-and-development-power-bi-content"></a>Conteúdo de competências e desenvolvimento de funcionários do Power BI

[!include [banner](../includes/banner.md)]

Este tópico descreve o conteúdo de desenvolvimento e competências de Funcionários do Power BI. 

## <a name="reports-that-are-included-in-the-content-pack"></a>Relatórios incluídos no pacote de conteúdo
Após a conexão do pacote de conteúdo aos dados, os relatórios mostram os dados de sua organização. Se você nunca usou o Microsoft Power BI antes, pode saber mais sobre ele na [página Aprendizado guiado para Power BI](https://powerbi.microsoft.com/guided-learning/?WT.mc_id=PBIService_GetData). Os relatórios incluídos no pacote de conteúdo têm gráficos e tabelas que contêm informações adicionais. A tabela a seguir descreve os relatórios.

| Relatório                            | Conteúdo                                               |
|-----------------------------------|--------------------------------------------------------|
| Análise de competências e desenvolvimento | Tipos de habilidade do membro da equipe e habilidades do membro da equipe por tipo |
| Perfil de habilidades                     | O perfil de habilidades do funcionário selecionado                |
| Análise de habilidade                    | Habilidades por tipo e classificação                              |

Você pode filtrar os gráficos e blocos nesses relatórios e fixá-los no painel. Para obter mais informações sobre como filtrar e fixar no Power BI, consulte [Criar e Configurar um Painel](https://powerbi.microsoft.com/guided-learning/powerbi-learning-4-2-create-configure-dashboards).

## <a name="understanding-the-data-model-and-entities"></a>Noções básicas sobre o modelo de dados e as entidades
Os dados do aplicativo são usados para preencher os relatórios no pacote de conteúdo desenvolvimento e competências de Funcionários. A seguinte tabela mostra as entidades nas quais o pacote de conteúdo foi baseado.

| Entidade                            | Conteúdo                                                                                                   | Relações com outras entidades |
|-----------------------------------|------------------------------------------------------------------------------------------------------------|-----------------------------------|
| Workforce\_CalendarOffset         | Compensações de calendário para dividir relatórios                                                                          | |
| Workforce\_Company                | Empresas para filtrar relatórios                                                                             | |
| Workforce\_Compensation           | Taxa de pagamento e frequência com o tempo                                                                           | |
| Workforce\_CurrentCompensation    | Taxa de pagamento e frequência a partir da data atual                                                              | Workforce\_Company, Workforce\_CurrentCompensation, Workforce\_Demographics, Workforce\_Job, Workforce\_Position |
| Workforce\_CurrentPosition        | Posições a partir da data atual, equivalente ao horário integral (FTE), posições abertas e posições abertas a preenchidas | Workforce\_Job Workforce\_Position |
| Workforce\_CurrentWorker          | Trabalhadores a partir da data atual, idade e número de funcionários                                                         | Workforce\_Company Workforce\_Compensation, Workforce\_GeographicLocation, Workforce\_Performance, Workforce\_PersonSkill, Workforce\_WorkerName, Workforce\_ReportsToWorkerName, Workforce\_WorkerTitle, Workforce\_Demographics, Workforce\_Job, Workforce\_Employment, Workforce\_Position |
| Workforce\_Date                   | Dias, semanas, meses e anos                                                                             | |
| Workforce\_Demographics           | Data de nascimento, gênero, origem étnica e estado civil                                                   | |
| Workforce\_Employment             | Data inicial, data final e data de transição                                                                  | |
| Workforce\_GeographicLocation     | Cidade, região, CEP e estado ou província                                                           | |
| Workforce\_Job                    | Função, tipo e título                                                                                  | |
| Workforce\_JobPreferredSkill      | Importância, classificação, habilidade e nível de habilidade                                                                 | Workforce\_Skill, Workforce\_Job |
| Workforce\_PastPositionAssignment | Motivo da atribuição, data inicial, data final e trabalho                                                           | Workforce\_CalendarOffset, Workforce\_Date, Workforce\_Job, Workforce\_Position |
| Workforce\_Performance            | Classificação, descrição e modelo de classificação                                                                      | |
| Workforce\_PersonSkill            | Nível, data do nível e habilidade                                                                               | Workforce\_Skill |
| Workforce\_PersonSkillAnalysis    | Certificado, nível, data do nível e habilidade                                                                    | Workforce\_WorkerName, Workforce\_Skill |
| Workforce\_Position               | Departamento, FTE, posição, tipo de posição e título                                                        | |
| Workforce\_PositionTrend          | Posições com o tempo, FTE e trabalho                                                                          | Workforce\_CalendarOffset, Workforce\_Date, Workforce\_Job, Workforce\_Position |
| Workforce\_ReportsToWorkerName    | Nome, sobrenome e nome completo                                                                       | |
| Workforce\_Skill                  | Habilidade, tipo de habilidade e classificação                                                                              | |
| Workforce\_TerminatedWorker       | Trabalhadores demitidos, data da demissão, cargo, posição e trabalho                                             | Workforce\_Company, Workforce\_Compensation, Workforce\_GeographicLocation, Workforce\_Performance, Workforce\_WorkerName, Workforce\_ReportsToWorkerName, Workforce\_CalendarOffset, Workforces\_Date, Workforce\_WorkerTitle, Workforce\_Demographics, Workforce\_Employment, Workforce\_Job, Workforce\_Position |
| Workforce\_WorkerName             | Nome, sobrenome e nome completo                                                                       | |
| Workforce\_WorkerTitle            | Título e data de tempo de serviço                                                                                   | |
| Workorce\_WorkerTrend             | Trabalhadores com o tempo, número de funcionários, empresa e posição                                                        | Workforce\_Company, Workforce\_Compensation, Workforce\_GeographicLocation, Workforce\_Performance, Workforce\_WorkerName, Workforce\_ReportsToWorkerName, Workforce\_CalendarOffset, Workforces\_Date, Workforce\_WorkerTitle, Workforce\_Demographics, Workforce\_Employment, Workforce\_Job |


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]