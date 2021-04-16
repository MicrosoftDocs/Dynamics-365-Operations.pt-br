---
title: Conteúdo do Power BI Métricas de força de trabalho
description: Este tópico descreve o conteúdo do Power BI Métricas de força de trabalho.
author: jcart1106
ms.date: 12/19/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: HcmWorkforceWorkspace
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: 264084
ms.assetid: 8e700583-3a7d-4f5f-9ac8-58c4feed1a02
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 244fe5afe822c9ff7b9921d8e4e7b6904c96ad01
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5754183"
---
# <a name="workforce-metrics-power-bi-content"></a>Conteúdo do Power BI Métricas de força de trabalho

[!include [banner](../includes/banner.md)]

Este tópico descreve o conteúdo das **Métricas de força de trabalho** do Microsoft Power BI. Ele explica como acessar os relatórios do Power BI e fornece informações sobre o modelo de dados e entidades que foram usados para criar o conteúdo.

## <a name="accessing-the-power-bi-content"></a>Acessando o conteúdo do Power BI
O conteúdo **Métricas de força de trabalho** do Power BI aparece no espaço de trabalho **Gerenciamento de pessoal** se você usar um destes produtos:

- Microsoft Dynamics 365 Finance
- Microsoft Dynamics 365 Human Resources

## <a name="metrics-that-are-included-in-the-power-bi-content"></a>Métricas incluídas no conteúdo do Power BI
A tabela a seguir lista as métricas mostradas em cada relatório.

| Relatório                                           | Métrica |
|--------------------------------------------------|---------|
| Métricas de pessoas                                   | Resumo de outros relatórios |
| Companhia de Análise de Pessoal, Departamento, Localização | Número de funcionários por empresa, número de funcionários por departamento, número de funcionários por local e número total de funcionários |
| Trabalho de Análise de Headcount, Etapa, Gerente            | Número de funcionários por cargo, número de funcionários por etapa, número de funcionários por gerente e número total de funcionários |
| Análise de tendência de funcionários                         | O número de funcionários deste ano em relação ao ano passado pela empresa e pelo número de funcionários nos últimos 12 meses |
| Análise FTE                                     | Equivalente ao horário integral (FTE) total, FTE atribuído total, FTE por departamento, FTE dos últimos 12 meses e FTE por trabalho |
| Demografia da força de trabalho                           | Número de funcionários por idade e sexo, número de funcionários por origem étnica, número de funcionários por estado de veterano, número de funcionários por estado civil, número de estudantes em período integral, tempo médio de permanência, idade média, proporção de empregados do sexo feminino e idiomas falados pelos funcionários |
| Análise de posição                                | Posições abertas por departamento, posições abertas a preenchidas, posições ativas a inativas, e posições por departamento |
| Análise de atrito                               | Atrito deste ano em comparação ao do ano passado, atrito, funcionários existentes por idade e gênero, tempo médio de licença dos funcionários, funcionários existentes deste mês e licença dos funcionários por razão |
| Pessoas por departamento                             | Funcionários com um número pessoal por departamento, posição e datas de início e término da atribuição |
| Análise de antiguidade                               | Tempo médio, média de anos de serviço por empresa e lista de antiguidade |
| Aniversários de funcionários                           | Aniversários deste mês, aniversários do mês que vem, funcionários por anos de serviço e aniversários, anos de serviço por departamento |
| Aniversários de funcionários                               | Aniversários deste mês, aniversários do mês que vem, aniversários de funcionários e aniversários por mês e departamento |
| Projetos de contratação em massa                               | Total de projetos de contratação em massa, projetos de contratação em massa por status, projetos de contratação em massa por departamento e proprietário, projetos de contratação em massa por trabalho e projetos de contratação em massa |

Você pode filtrar os gráficos e blocos nesses relatórios e fixá-los no painel. Para obter mais informações sobre como filtrar e fixar no Power BI, consulte [Criar e configurar um painel](https://powerbi.microsoft.com/guided-learning/powerbi-learning-4-2-create-configure-dashboards).

Certifique-se de baixar o conteúdo do Power BI **Métricas da força de trabalho** que se aplica à versão do Microsoft Dynamics 365 que você está usando.

> [!NOTE]
> Os arquivos .pbix disponíveis no Lifecycle Services aplicam-se somente aos aplicativos do Finance and Operations.

## <a name="understanding-the-data-model-and-entities"></a>Noções básicas sobre o modelo de dados e as entidades
A seguinte tabela mostra as entidades nas quais o conteúdo foi baseado.

| Entidade                   | Conteúdo                                                                            | Relações com outras entidades |
|--------------------------|-------------------------------------------------------------------------------------|-----------------------------------|
| Compensação de calendário          | Compensações de calendário para dividir relatórios                                                   | Atribuição da última posição, Tendência da posição, Evolução do funcionário, Funcionário demitido |
| Empresa                  | Empresas para filtrar relatórios                                                      | Funcionário atual, Funcionário demitido, Evolução do funcionário |
| Posição atual         | Posições a partir da data atual, FTE, posições abertas e posições abertas a preenchidas | Trabalho, Posição |
| Funcionário atual         | Trabalhadores a partir da data atual, idade e número de funcionários                                  | Empresa, Localização geográfica, Nome do funcionário, Subordinado a, Cargo do funcionário, Dados demográficos, Trabalho, Emprego, Posição |
| Data                     | Dias, semanas, meses e anos                                                      | Atribuição da última posição, Tendência da posição, Funcionário demitido, Evolução do funcionário |
| Dados demográficos             | Data de nascimento, gênero, origem étnica e estado civil                            | Funcionário atual, Funcionário demitido, Evolução do funcionário |
| Emprego               | Data inicial, data final e data de transição                                           | Funcionário atual, Funcionário demitido, Evolução do funcionário |
| Localização Geográfica      | Cidade, região, CEP e estado ou província                                    | Funcionário atual, Funcionário demitido, Evolução do funcionário |
| Trabalho                      | Função, tipo e título                                                           | Posição atual, funcionário atual |
| Atribuição da última posição | Motivo da atribuição, data inicial, data final e trabalho                                    | Compensação de calendário, data, trabalho, posição |
| Cargo                 | Departamento, FTE, posição, tipo de posição e título                                 | Posição atual, funcionário atual |
| Tendência da Posição           | Posições com o tempo, FTE e trabalho                                                   | Compensação de calendário, data, trabalho, posição |
| Subordinado a               | Nome, sobrenome e nome completo                                                | Funcionário atual, Funcionário demitido, Evolução do funcionário |
| Funcionário demitido      | Trabalhadores demitidos, data da demissão, cargo, posição e trabalho                      | Empresa, Localização geográfica, Nome do funcionário, Subordinado a, Calendário de compensação, Data, Cargo do funcionário, Dados demográficos, Emprego, Trabalho, Posição |
| Nome do Funcionário            | Nome, sobrenome e nome completo                                                | Trabalhador atual, Funcionário demitido, Evolução do funcionário |
| Cargo do funcionário           | Título e data de tempo de serviço                                                            | Funcionário atual, Funcionário demitido, Evolução do funcionário |
| Evolução do funcionário           | Trabalhadores com o tempo, número de funcionários, empresa e posição                                 | Empresa, Localização geográfica, Nome do funcionário, Subordinado a, Calendário de compensação, Data, Cargo do funcionário, Dados demográficos, Emprego, Trabalho |
| Projeto de contratação em massa        | Número de projetos de contratação em massa, proprietário de projeto e status de projeto                     | Empresa, linha de contratação em massa |
| Linhas de contratação em massa           | Departamento, tipo de emprego e posição                                           | Data, trabalho, projeto de contratação em massa |


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]