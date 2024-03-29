---
title: Conteúdo de desenvolvimento de funcionários do Power BI
description: Este artigo descreve o conteúdo de desenvolvimento de funcionários do Power BI.
author: jcart1106
ms.date: 12/19/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.openlocfilehash: 307a7ba2b885ba1437d5ef54c2f9d70ef00e2b14
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9284168"
---
# <a name="employee-development-power-bi-content"></a>Conteúdo de desenvolvimento de funcionários do Power BI

[!include [banner](../includes/banner.md)]

Este artigo descreve o conteúdo de **desenvolvimento de funcionários** do Microsoft Power BI.

## <a name="reports-that-are-included-in-the-power-bi-content"></a>Relatórios incluídos no conteúdo do Power BI
Os relatórios incluídos no conteúdo de **Desenvolvimento de funcionários** do Power BI têm gráficos e tabelas que contêm informações adicionais. A tabela a seguir descreve os relatórios.

| Relatório                        | Conteúdo |
|-------------------------------|----------|
| Visão geral de desenvolvimento do funcionário | Resumo de outros relatórios |
| Análise de habilidades do funcionário       | Tipos de habilidades dos funcionários e habilidades dos funcionários por tipo |
| Análise de nível de habilidade do funcionário | Níveis de habilidade do funcionário por departamento, funcionários por nível de habilidade e tipo de habilidade, e níveis superiores ou inferiores por habilidade |
| Perfil de habilidades                 | O perfil de habilidades do funcionário selecionado |
| Análise de habilidade                | Habilidades por tipo e classificação |
| Análise de avaliação de desempenho   | Funcionários por classificação mais alta ou mais baixa por trabalho, classificação do funcionário por departamento, funcionários por tipo de posição e classificação, e mais alta ou mais baixa classificação por cargo |
| Análise de desempenho do funcionário | Classificações do funcionário sobre classificação selecionada pelo gerente |

Você pode filtrar os gráficos e blocos nesses relatórios e fixá-los no painel. Para obter mais informações sobre como filtrar e fixar no Power BI, consulte [Criar e Configurar um Painel](https://powerbi.microsoft.com/guided-learning/powerbi-learning-4-2-create-configure-dashboards).

## <a name="understanding-the-data-model-and-entities"></a>Noções básicas sobre o modelo de dados e as entidades

| Entidade                   | Conteúdo                                                                                                   | Relações com outras entidades |
|--------------------------|------------------------------------------------------------------------------------------------------------|-----------------------------------|
| Calendário de compensação          | Compensações de calendário para dividir relatórios                                                                          | Atribuição da última posição, Tendência da posição, Evolução do funcionário, Funcionário demitido |
| Empresa                  | Empresas para filtrar relatórios                                                                             | Funcionário atual, Funcionário demitido, Evolução do funcionário |
| Posição atual         | Posições a partir da data atual, equivalente ao horário integral (FTE), posições abertas e posições abertas a preenchidas | Trabalho, Posição |
| Funcionário atual         | Trabalhadores a partir da data atual, idade e número de funcionários                                                         | Empresa, Localização geográfica, Nome do funcionário, Subordinado a, Cargo do funcionário, Dados demográficos, Trabalho, Emprego, Posição |
| Data                     | Dias, semanas, meses e anos                                                                             | Atribuição da última posição, Tendência da posição, Funcionário demitido, Evolução do funcionário |
| Dados demográficos             | Data de nascimento, gênero, origem étnica e estado civil                                                   | Funcionário atual, Demitidos, Funcionário, Evolução do funcionário |
| Emprego               | Data inicial, data final e data de transição                                                                  | Funcionário atual, Funcionário demitido, Evolução do funcionário |
| Localização Geográfica      | Cidade, região, CEP e estado ou província                                                           | Funcionário atual, Funcionário demitido, Evolução do funcionário |
| Trabalho                      | Função, tipo e título                                                                                  | Posição atual, funcionário atual |
| Atribuição da última posição | Motivo da atribuição, data inicial, data final e trabalho                                                           | Compensação de calendário, data, trabalho, posição |
| Cargo                 | Departamento, FTE, posição, tipo de posição e título                                                        | Posição atual, funcionário atual |
| Tendência da Posição           | Posições com o tempo, FTE e trabalho                                                                          | Compensação de calendário, data, trabalho, posição |
| Subordinado a               | Nome, sobrenome e nome completo                                                                       | Funcionário atual, Funcionário demitido, Evolução do funcionário |
| Funcionário demitido      | Trabalhadores demitidos, data da demissão, cargo, posição e trabalho                                             | Empresa, Localização geográfica, Nome do funcionário, Subordinado a, Calendário de compensação, Data, Cargo do funcionário, Dados demográficos, Emprego, Trabalho, Posição |
| Nome do Funcionário            | Nome, sobrenome e nome completo                                                                       | Trabalhador atual, Funcionário demitido, Evolução do funcionário |
| Cargo do funcionário           | Título e data de tempo de serviço                                                                                   | Funcionário atual, Funcionário demitido, Evolução do funcionário |
| Evolução do funcionário           | Trabalhadores com o tempo, número de funcionários, empresa e posição                                                        | Empresa, Localização geográfica, Nome do funcionário, Subordinado a, Calendário de compensação, Data, Cargo do funcionário, Dados demográficos, Emprego, Trabalho |
| Trabalho                      | Função, tipo e título                                                                                  | Funcionário atual, Posição atual, Evolução do funcionário, Habilidade preferencial no trabalho, Atribuição da última posição, Tendência da posição, Funcionário demitido |
| Habilidade preferencial no trabalho      | Importância, classificação, habilidade e nível de habilidade                                                                 | Trabalho |
| Análise de habilidades do funcionário  | Certificado, nível, data do nível e habilidade                                                                    | Nome do funcionário, Habilidade |
| Desempenho              | Classificação, descrição e modelo de classificação                                                                      | Funcionário atual, Posição atual, Evolução do funcionário, Habilidade preferencial no trabalho, Atribuição da última posição, Tendência da posição, Funcionário demitido |
| Habilidade                    | Habilidade, tipo de habilidade e classificação                                                                              | Análise de habilidades do funcionário, Habilidade preferencial no trabalho |


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
