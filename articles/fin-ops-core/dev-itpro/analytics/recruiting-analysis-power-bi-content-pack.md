---
title: Conteúdo de recrutamento do Power BI
description: Este tópico descreve o conteúdo de recrutamento do Power BI.
author: jcart1106
ms.date: 12/19/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: HcmRecruitmentWorkspace
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: 263934
ms.assetid: 38e6827b-0819-473c-bc47-821a1ec482b8
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 36ea9f204b50b3d7a6c8e33e69a9c3fd7d82cd79d466e2b9547c6733aa294aea
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6765113"
---
# <a name="recruiting-power-bi-content"></a>Conteúdo de recrutamento do Power BI

[!include [banner](../includes/banner.md)]

Este tópico descreve o conteúdo de **Recrutamento** do Microsoft Power BI. Ele explica como acessar os relatórios do Power BI e fornece informações sobre o modelo de dados e entidades que foram usados para criar o conteúdo.

## <a name="accessing-the-power-bi-content"></a>Acessando o conteúdo do Power BI
O **Recrutamento** de conteúdo do Power BI é exibido no espaço de trabalho **Gerenciamento de recrutamento**.

## <a name="reports-and-visuals-in-the-recruitment-management-workspace"></a>Relatórios e visuais na área de trabalho de gerenciamento de recrutamento
O espaço de trabalho **Gerenciamento de recrutamento** contém uma guia **Análise**. Esta guia contém o conteúdo embutido do Power BI para recrutamento. O conteúdo consiste em uma guia visão geral e guias adicionais que contém detalhes. A tabela a seguir descreve os relatórios em cada guia.

| Relatório               | Conteúdo |
|----------------------|----------|
| Visão geral do recrutamento | Resume outros relatórios |
| Análise do candidato   | Número total de candidatos, candidatos à vaga, origens de candidatos, candidatos do sexo feminino e masculino, e candidatos por local |
| Status do candidato     | Candidatos por tipo, por status e status do candidato |
| Análise de recrutamento  | Taxa de aluguel líquido, dias médios de contratação, porcentagem de contratações ruins, custos de recrutamento, número de projetos de recrutamento, contratações de candidatos e candidatos versus aberturas por projeto de recrutamento |

## <a name="understanding-the-data-model-and-entities"></a>Noções básicas sobre o modelo de dados e as entidades
Você pode filtrar os gráficos e blocos nesses relatórios e fixá-los no painel. Para obter mais informações sobre como filtrar e fixar no Power BI, consulte [Criar e Configurar um Painel](https://powerbi.microsoft.com/guided-learning/powerbi-learning-4-2-create-configure-dashboards).

A seguinte tabela mostra as entidades nas quais o conteúdo do Power BI de **Recrutamento** foi baseado.

| Entidade               | Conteúdo                                                         | Relações com outras entidades |
|----------------------|------------------------------------------------------------------|-----------------------------------|
| Candidato            | Candidatos, candidatos contratados, taxa de contratação de redes e custos          | Nome do candidato, empresa, deslocamento do calendário, data, localização geográfica, demografia, trabalho, mídia, projeto de recrutamento |
| Nome do candidato       | Primeiro nome do candidato, sobrenome e nome completo                   | Candidato, candidato empregado, candidato demitido |
| Compensação de calendário      | Compensações de calendário para dividir relatórios                                | Candidato, candidato empregado, candidato demitido |
| Empresa              | Empresas para filtrar relatórios                                   | Candidato, candidato empregado, candidato demitido |
| Data                 | Dias, semanas, meses e anos                                   | Candidato, candidato empregado, candidato demitido |
| Dados demográficos         | Data de nascimento, gênero, origem étnica e estado civil         | Candidato, candidato empregado, candidato demitido |
| Candidato empregado   | Candidato, desempenho, data inicial e tipo de candidato           | Companhia, compensação de calendário, data, localização geográfica, nome do candidato, emprego, desempenho, trabalho, mídia, projeto de recrutamento |
| Emprego           | Data inicial, data final e data de transição                        | Candidato, candidato empregado, candidato demitido |
| Localização Geográfica  | Cidade, região, CEP e estado ou província                 | Candidato, candidato empregado, candidato demitido |
| Trabalho                  | Função, tipo e título                                        | Candidato, candidato empregado, candidato demitido |
| Mídia                | Fonte de candidatos                                             | Candidato, candidato empregado, candidato demitido |
| Desempenho          | Classificação, descrição e modelo de classificação                            | Candidato, candidato empregado, candidato demitido |
| Projeto de recrutamento  | Descrição do projeto, status do projeto e aberturas                | Candidato, candidato empregado, candidato demitido |
| Candidato demitido | Candidatos finalizados, desempenho e data de demissão | Companhia, compensação de calendário, data, localização geográfica, desempenho, demografia, emprego, mídia, projeto de recrutamento, nome do candidato |


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]