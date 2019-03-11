---
title: Conteúdo de aprendizagem do Power BI
description: Este tópico descreve o conteúdo de Aprendizagem do Power BI.
author: jcart1106
manager: AnnBe
ms.date: 12/19/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations, Talent
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.openlocfilehash: a4ea4606f9987bc08565d43a1f05243acf88883c
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2019
ms.locfileid: "321446"
---
# <a name="learning-power-bi-content"></a>Conteúdo de aprendizagem do Power BI

[!include [banner](../includes/banner.md)]

Este tópico descreve o conteúdo de **Aprendizagem** do Microsoft Power BI.

## <a name="reports-that-are-included-in-the-power-bi-content"></a>Relatórios incluídos no conteúdo do Power BI

Os relatórios incluídos no conteúdo de **Aprendizagem** do Power BI têm gráficos e tabelas com informações adicionais. A tabela a seguir descreve os relatórios.

| Relatório                | Conteúdo |
|-----------------------|----------|
| Visão geral de Aprendizagem     | Resumo de outros relatórios |
| Análise de curso       | Registro por localização, participante por status, cursos por tipo de empresa e participação no curso por trabalho |
| Análise de registro | Lista de registro |
| Tipos de cursos          | Tipos de cursos por habilidade |
| Análise de instrutor   | Relação de cursos para instrutores, número de instrutores, cursos de instrutor, cursos por instrutor, e programação do curso por instrutor |
| Cursos oferecidos       | Lista de cursos |
| Design de cursos        | Agenda do curso |

Você pode filtrar os gráficos e blocos nesses relatórios e fixá-los no painel. Para obter mais informações sobre como filtrar e fixar no Power BI, consulte [Criar e Configurar um Painel](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-4-2-create-configure-dashboards).

## <a name="understanding-the-data-model-and-entities"></a>Noções básicas sobre o modelo de dados e as entidades

Os dados a seguir são utilizados para preencher os relatórios no conteúdo de **Aprendizagem** do Power BI. Esta tabela mostra as entidades nas quais o conteúdo foi baseado.

| Entidade           | Conteúdo                                                         | Relações com outras entidades |
|------------------|------------------------------------------------------------------|-----------------------------------|
| Compensação do calendário  | Compensações de calendário para dividir relatórios                                | Agenda do curso, participantes do curso |
| Empresa          | Empresas para filtrar relatórios                                   | Agenda do curso, participantes do curso |
| Curso           | Curso, descrição, nome do instrutor, local, sala e status | Agenda do curso, participantes do curso, competência do curso |
| Agenda do curso    | Agenda, curso e períodos de início e término                          | Empresa, compensação do calendário, data, curso |
| Participantes do curso | Nome, status, trabalho e data de registro                         | Empresa, compensação do calendário, data, curso, dados demográficos, emprego, curso, nome do funcionário, cargo do funcionário, trabalho, posição |
| Competência do curso     | Habilidade, tipo de habilidade e classificação                                     | Curso |
| Data             | Dias, semanas, meses e anos                                   | Agenda do curso, participantes do curso |
| Dados demográficos     | Data de nascimento, gênero, origem étnica e estado civil         | Agenda do curso, participantes do curso |
| Emprego       | Data inicial, data final e data de transição                        | Agenda do curso, participantes do curso |
| Trabalho              | Função, tipo e título                                        | Agenda do curso, participantes do curso |
| Cargo         | Posição, título e tempo completo equivalente (FTE)                  | Agenda do curso, participantes do curso |
| Nome do Funcionário    | Nome, sobrenome e nome completo                             | Participantes do curso |
| Cargo do funcionário   | Título e data de tempo de serviço                                         | Participantes do curso |
