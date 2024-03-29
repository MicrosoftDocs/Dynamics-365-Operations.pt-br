---
title: Conteúdo de treinamento organizacional do Power BI
description: Este artigo descreve o conteúdo de treinamento organizacional de finanças e operações do Power BI.
author: jcart1106
ms.date: 12/19/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.custom: 263874
ms.assetid: 45dbba14-aba6-4571-be0d-5d1aba3515d9
ms.openlocfilehash: 2e80810dbeb536dccf6e13b5fca6a85f4858d8da
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9267232"
---
# <a name="organizational-training-power-bi-content"></a>Conteúdo de treinamento organizacional do Power BI

[!include [banner](../includes/banner.md)]

Este artigo descreve o conteúdo de treinamento organizacional de finanças e operações do Power BI.

## <a name="reports-that-are-included-in-the-content-pack"></a>Relatórios incluídos no pacote de conteúdo
Após a conexão do pacote de conteúdo aos dados, os relatórios mostram os dados de sua organização. Se você nunca usou o Microsoft Power BI antes, pode saber mais sobre ele na [página Aprendizado guiado para Power BI](https://powerbi.microsoft.com/guided-learning/?WT.mc_id=PBIService_GetData). Os relatórios incluídos no pacote de conteúdo têm gráficos e tabelas que contêm informações adicionais. A tabela a seguir descreve os relatórios.

| Relatório          | Conteúdo                                                                    |
|-----------------|-----------------------------------------------------------------------------|
| Análise de curso | Registro por local, participantes de cursos por status e lista de registro |
| Tipos de cursos    | Tipos de cursos por habilidade                                                       |

Você pode filtrar os gráficos e blocos nesses relatórios e fixá-los no painel. Para obter mais informações sobre como filtrar e fixar no Power BI, consulte [Criar e Configurar um Painel](https://powerbi.microsoft.com/guided-learning/powerbi-learning-4-2-create-configure-dashboards).

## <a name="understanding-the-data-model-and-entities"></a>Noções básicas sobre o modelo de dados e as entidades
Os dados de aplicativos são usados para preencher os relatórios no pacote de conteúdo do treinamento organizacional. A seguinte tabela mostra as entidades nas quais o pacote de conteúdo foi baseado.

| Entidade                    | Conteúdo                                                         | Relações com outras entidades |
|---------------------------|------------------------------------------------------------------|-----------------------------------|
| Training\_CalendarOffset  | Compensações de calendário para dividir relatórios                                | Training\_CourseAgenda, Training\_CourseAttendees |
| Training\_Company         | Empresas para filtrar relatórios                                   | Training\_CourseAgenda, Training\_CourseAttendees |
| Training\_Course          | Curso, descrição, nome do instrutor, local, sala e status | Training\_CourseAgenda, Training\_CourseAttendees, Training\_CourseSkill |
| Training\_CourseAgenda    | Agenda, curso e períodos de início e término                          | Training\_Company, Training\_CalendarOffset, Training\_Date, Training\_Course |
| Training\_CourseAttendees | Nome, status, trabalho e data de registro                         | Training\_Company, Training\_CalendarOffset, Training\_Date, Training\_Demographics, Training\_Employment, Training\_Course, Training\_WorkerName, Training\_WorkerTitle, Training\_Job, Training\_Position |
| Training\_CourseSkill     | Habilidade, tipo de habilidade e classificação                                     | Training\_Course |
| Training\_Date            | Dias, semanas, meses e anos                                   | Training\_CourseAgenda, Training\_CourseAttendees |
| Training\_Demographics    | Data de nascimento, gênero, origem étnica e estado civil         | Training\_CourseAgenda, Training\_CourseAttendees |
| Training\_Employment      | Data inicial, data final e data de transição                        | Training\_CourseAgenda, Training\_CourseAttendees |
| Training\_Job             | Função, tipo e título                                        | Training\_CourseAgenda, Training\_CourseAttendees |
| Training\_Position        | Posição, título e tempo completo equivalente (FTE)                  | Training\_CourseAgenda, Training\_CourseAttendees |
| Training\_WorkerName      | Nome, sobrenome e nome completo                             | Training\_CourseAttendees |
| Training\_WorkerTitle     | Título e data de tempo de serviço                                         | Training\_CourseAttendees |


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
