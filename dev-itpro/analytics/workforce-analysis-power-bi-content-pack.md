---
title: "Conteúdo do Power BI de métricas de força de trabalho"
description: "Este tópico descreve o Conteúdo do Power BI Métricas de força de trabalho. Ele explica como acessar os relatórios e fornece informações sobre o modelo de dados e as entidades usadas para criar o conteúdo."
author: jcart1106
manager: AnnBe
ms.date: 06/16/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User, IT Pro
ms.search.scope: Operations, UnifiedOperations, Talent, Core
ms.custom: 264084
ms.assetid: 8e700583-3a7d-4f5f-9ac8-58c4feed1a02
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: Human Translation
ms.sourcegitcommit: 869151f2486b7a481e4694cfb6992d0ee2cfc008
ms.openlocfilehash: 1f732a53eee17317417058b92706a9228d783cb5
ms.contentlocale: pt-br
ms.lasthandoff: 06/13/2017


---

# <a name="workforce-metrics-power-bi-content"></a>Conteúdo do Power BI de métricas de força de trabalho

[!include[banner](../includes/banner.md)]

Este tópico descreve o Conteúdo do Microsoft Power BI **Métricas de força de trabalho**. Ele explica como acessar os relatórios do Power BI, além de fornecer informações sobre o modelo de dados e as entidades usados para criar o pacote de conteúdo.

## <a name="accessing-the-power-bi-content"></a>Acessando o conteúdo do Power BI
O conteúdo do Power BI **Métricas de força de trabalho** aparece no espaço de trabalho **Gerenciamento de pessoal** se você usar um destes produtos:

- Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition atualização de julho de 2017
- Microsoft Dynamics 365 for Talent

## <a name="metrics-that-are-included-in-the-power-bi-content"></a>Métricas incluídas no conteúdo do Power BI
A tabela a seguir lista as métricas mostradas em cada relatório.

| Relatório                                           | Métrica                                                                                                                                                                                                            |
|--------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Métricas de pessoas                                   | Resumo de outros relatórios                                                                                                                           |
| Companhia de Análise de Pessoal, Departamento, Localização | Número de funcionários por empresa, número de funcionários por departamento, número de funcionários por local e número total de funcionários                                                                                                                           |
| Trabalho de Análise de Headcount, Etapa, Gerente            | Número de funcionários por cargo, número de funcionários por etapa, número de funcionários por gerente e número total de funcionários                                                                                                                                      |
| Análise de tendência de funcionários                         | O número de funcionários deste ano em relação ao ano passado pela empresa e pelo número de funcionários nos últimos 12 meses                                                                                                                        |
| Análise FTE                                     | Equivalente ao horário integral (FTE) total, FTE atribuído total, FTE por departamento, FTE dos últimos 12 meses e FTE por trabalho |
| Demografia da força de trabalho                           | Número de funcionários por idade e sexo, número de funcionários por origem étnica, número de funcionários por estado de veterano, número de funcionários por estado civil, número de estudantes em período integral, tempo médio de permanência, idade média, proporção de empregados do sexo feminino e idiomas falados pelos funcionários |
| Análise de posição                                | Posições abertas por departamento, posições abertas a preenchidas, posições ativas a inativas, e posições por departamento                                                                                                   |
| Análise de atrito                               | Atrito deste ano em comparação ao do ano passado, atrito, funcionários existentes por idade e gênero, tempo médio de licença dos funcionários, funcionários existentes deste mês e licença dos funcionários por razão                                                                   |
| Pessoas por departamento                             | Funcionários com um número pessoal por departamento, posição e datas de início e término da atribuição                                                                                                                       |
| Análise de antiguidade                               | Tempo médio, média de anos de serviço por empresa e lista de antiguidade                                                                                                                                                              |
| Aniversários de funcionários                           | Aniversários deste mês, aniversários do mês que vem, funcionários por anos de serviço e aniversários, anos de serviço por departamento                                                                                                                                                                    |
| Aniversários de funcionários                               | Aniversários deste mês, aniversários do mês que vem, aniversários de funcionários e aniversários por mês e departamento                                                                                                                                                                    |
| Projetos de contratação em massa                               | Total de projetos de contratação em massa, projetos de contratação em massa por status, projetos de contratação em massa por departamento e proprietário, projetos de contratação em massa por trabalho e projetos de contratação em massa                                                                                                                                                                    |

Você pode filtrar os gráficos e blocos nesses relatórios e fixá-los no painel. Para saber mais sobre como filtrar e fixar no Power BI, veja [Criar e configurar um painel](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-4-2-create-configure-dashboards).

## <a name="extending-the-power-bi-content"></a>Aumentando o conteúdo do Power BI
Usando os pacotes de conteúdo disponíveis no Microsoft Dynamics Lifecycle Services (LCS), você pode fornecer grande análise às pessoas que não acessam o Finance and Operations. Você pode modificar esses pacotes de conteúdo para que eles incluam outros relatórios ou imagens e, em seguida, publique os pacotes de conteúdo no locatário do Power BI.com para análise.

Você pode localizar o conteúdo do Power BI **Métricas de força de trabalho** na biblioteca de ativos compartilhados do LCS. Para obter mais informações sobre como baixar o pacote de conteúdo e implementá-lo na sua organização, consulte [Conteúdo do Power BI no LCS da Microsoft e seus parceiros](power-bi-content-microsoft-partners.md). Para ver uma demonstração que mostra como implementar o conteúdo do Power BI, veja o Office Mix [Conteúdo do Power BI da Microsoft e seus parceiros no Dynamics Lifecycle Services](https://mix.office.com/watch/9puyb1b2xs1w).

Certifique-se de baixar o conteúdo do Power BI **Métricas de força de trabalho** que se aplica à versão do Microsoft Dynamics 365 que você está usando.

>[!NOTE]
>Os arquivos .pbix disponíveis no Lifecycle Services aplicam-se somente ao Finance and Operations.

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

Essas entidades foram usadas para criar medidas calculadas no modelo de dados. Essas medidas calculadas são então usadas para calcular os KPIs (indicadores chave de desempenho) e os relatórios usados no conteúdo do Power BI. Se quiser incluir cálculos adicionais nos seus relatórios e painel, você pode baixar e modificar o arquivo .pbix no LCS. Esse arquivo é o modelo de dados padrão usado para criar o conteúdo do Power BI. Após a realização de modificações, poderá criar um painel e pacote de conteúdo organizacional contendo as informações adicionadas.

