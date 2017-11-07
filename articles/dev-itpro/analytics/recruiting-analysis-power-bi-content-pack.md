---
title: "Recrutamento de conteúdo do Power BI"
description: "Este tópico descreve o conteúdo de recrutamento do Power BI. Ele explica como acessar os relatórios e fornece informações sobre o modelo de dados e as entidades usadas para criar o conteúdo."
author: jcart1106
manager: AnnBe
ms.date: 06/16/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 263934
ms.assetid: 38e6827b-0819-473c-bc47-821a1ec482b8
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: a02dab349da0709b8d9250dba0a2ca1e03b6a527
ms.contentlocale: pt-br
ms.lasthandoff: 09/29/2017

---

# <a name="recruiting-power-bi-content"></a>Recrutamento de conteúdo do Power BI

[!include[banner](../includes/banner.md)]

Este tópico descreve o conteúdo de **Recrutamento** do Microsoft Power BI. Ele explica como acessar os relatórios do Power BI, além de fornecer informações sobre o modelo de dados e as entidades usados para criar o pacote de conteúdo.

## <a name="accessing-the-power-bi-content"></a>Acessando o conteúdo do Power BI
Se estiver usando o Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition (julho de 2017), o conteúdo do Power BI de **Recrutamento** é mostrado no espaço de trabalho **Gerenciamento de recrutamento**. 

## <a name="reports-and-visuals-in-the-recruitment-management-workspace"></a>Relatórios e visuais na área de trabalho de gerenciamento de recrutamento
O espaço de trabalho **Gerenciamento de recrutamento** contém uma guia **Análise** . Esta guia contém o conteúdo embutido do Power BI para recrutamento. O conteúdo consiste em uma guia visão geral e guias adicionais que contém detalhes. A tabela a seguir descreve os relatórios em cada guia.

| Relatório               | Conteúdo |
|----------------------|----------|
| Visão geral do recrutamento | Resume outros relatórios |
| Análise do candidato   | Número total de candidatos, candidatos à vaga, origens de candidatos, candidatos do sexo feminino e masculino, e candidatos por local |
| Status do candidato     | Candidatos por tipo, por status e status do candidato |
| Análise de recrutamento  | Taxa de aluguel líquido, dias médios de contratação, porcentagem de contratações ruins, custos de recrutamento, número de projetos de recrutamento, contratações de candidatos e candidatos versus aberturas por projeto de recrutamento |

## <a name="understanding-the-data-model-and-entities"></a>Noções básicas sobre o modelo de dados e as entidades
Você pode filtrar os gráficos e blocos nesses relatórios e fixá-los no painel. Para obter mais informações sobre como filtrar e fixar no Power BI, consulte [Criar e configurar um painel](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-4-2-create-configure-dashboards).

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

Essas entidades foram usadas para criar medidas calculadas. Essas medidas calculadas são então usadas para calcular os KPIs (indicadores chave de desempenho) e os relatórios usados no conteúdo. Para incluir cálculos adicionais nos seus relatórios e painel, você pode baixar e modificar o arquivo Recruiting.pbix do Microsoft Dynamics Lifecycle Services (LCS). Esse arquivo é o modelo de dados padrão usado para criar o conteúdo. Após a realização de modificações, poderá criar um painel e pacote de conteúdo organizacional contendo as informações adicionadas.

