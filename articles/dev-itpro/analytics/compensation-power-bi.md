---
title: "Conteúdo de remuneração do Power BI"
description: "Este tópico descreve o conteúdo de remuneração do Power BI. Ele explica como acessar os relatórios e fornece informações sobre o modelo de dados e as entidades usadas para criar o conteúdo."
author: jcart1106
manager: AnnBe
ms.date: 12/19/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Operations, Talent, Core
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: cb43245afe578341251b140383a3b03ba2abd962
ms.openlocfilehash: 01841a2da44bfeebc8f8656229c406bd350cb6e5
ms.contentlocale: pt-br
ms.lasthandoff: 12/19/2017

---

# <a name="compensation-power-bi-content"></a>Conteúdo de remuneração do Power BI

[!include[banner](../includes/banner.md)]

Este tópico descreve o conteúdo de **Remuneração** do Microsoft Power BI. Ele explica como acessar os relatórios e fornece informações sobre o modelo de dados e as entidades usadas para criar o conteúdo.

## <a name="accessing-the-power-bi-content"></a>Acessando o conteúdo do Power BI
O conteúdo de **Remuneração** do Power BI é mostrado no espaço de trabalho **Gerenciamento de remuneração** se você usar um dos seguintes produtos:

- Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition
- Microsoft Dynamics 365 for Talent

## <a name="reports-that-are-included-in-the-power-bi-content"></a>Relatórios incluídos no conteúdo do Power BI
Os relatórios que estão incluídos no conteúdo de **Remuneração** do Power BI têm gráficos e tabelas que contêm informações adicionais. A tabela a seguir descreve os relatórios.

| Relatório                     | Conteúdo |
|----------------------------|----------|
| Visão geral da remuneração      | Resumo de outros relatórios |
| Análise da remuneração      | Funcionários por hora e remunerados pela empresa, totais de funcionários pelo plano de remuneração, funcionários de sexo masculino e feminino pelo plano de remuneração e remuneração de funcionário por departamento |
| Análise de pagamento da posição      | Pagamento de salário e pagamento por hora mais alto e mais baixo, posições com pagamento mais alto e mais baixo e posições de tempo integral e meio período. |
| Análise do plano de remuneração | Inscrição do funcionário por benefício selecionado |

Você pode filtrar os gráficos e blocos nesses relatórios e fixá-los no painel. Para obter mais informações sobre como filtrar e fixar no Power BI, consulte [Criar e configurar um painel](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-4-2-create-configure-dashboards).


## <a name="understanding-the-data-model-and-entities"></a>Noções básicas sobre o modelo de dados e as entidades
Os dados a seguir são utilizados para preencher o conteúdo de **Remuneração** do Power BI. Esta tabela mostra as entidades nas quais o conteúdo foi baseado.

| Entidade                   | Conteúdo                                                                                                   | Relações com outras entidades |
|--------------------------|------------------------------------------------------------------------------------------------------------|-----------------------------------|
| Compensação de calendário          | Compensações de calendário para dividir relatórios                                                                          | Atribuição da última posição, Tendência da posição, Evolução do funcionário, Funcionário demitido |
| Empresa                  | Empresas para filtrar relatórios                                                                             | Remuneração atual, Funcionário atual, Funcionário demitido, Evolução do funcionário |
| Remuneração             | Taxa de pagamento e frequência com o tempo                                                                           | Remuneração atual, Funcionário atual, Funcionário demitido, Evolução do funcionário |
| Remuneração atual     | Taxa de pagamento e frequência a partir da data atual                                                              | Empresa, remuneração, dados demográficos, trabalho, posição |
| Posição atual         | Posições a partir da data atual, equivalente ao horário integral (FTE), posições abertas e posições abertas a preenchidas | Trabalho, Posição |
| Funcionário atual         | Trabalhadores a partir da data atual, idade e número de funcionários                                                         | Empresa, Remuneração, Localização geográfica, Nome do funcionário, Subordinado a, Cargo do funcionário, Dados demográficos, Trabalho, Emprego, Posição, Benefícios |
| Data                     | Dias, semanas, meses e anos                                                                             | Atribuição da última posição, Tendência da posição, Funcionário demitido, Evolução do funcionário |
| Dados demográficos             | Data de nascimento, gênero, origem étnica e estado civil                                                   | Funcionário atual, Funcionário demitido, Evolução do funcionário |
| Emprego               | Data inicial, data final e data de transição                                                                  | Funcionário atual, Funcionário demitido, Evolução do funcionário |
| Localização Geográfica      | Cidade, região, CEP e estado ou província                                                           | Funcionário atual, Funcionário demitido, Evolução do funcionário |
| Trabalho                      | Função, tipo e título                                                                                  | Posição atual, funcionário atual |
| Atribuição da última posição | Motivo da atribuição, data inicial, data final e trabalho                                                           | Compensação de calendário, data, trabalho, posição |
| Cargo                 | Departamento, FTE, posição, tipo de posição e título                                                        | Posição atual, funcionário atual |
| Tendência da Posição           | Posições com o tempo, FTE e trabalho                                                                          | Compensação de calendário, data, trabalho, posição |
| Subordinado a               | Nome, sobrenome e nome completo                                                                       | Trabalhador atual, Funcionário demitido, Evolução do funcionário |
| Funcionário demitido      | Funcionários demitidos, data da demissão, cargo, posição e trabalho                                             | Empresa, Remuneração, Localização geográfica, Nome do funcionário, Subordinado a, Calendário de compensação, Data, Cargo do funcionário, Dados demográficos, Emprego, Trabalho, Posição, Benefícios |
| Benefícios                 | Data de efetivação, opção de benefício, plano de benefício e tipo de benefício                                             | Nome atual, Funcionário demitido, Evolução do funcionário |
| Nome do Funcionário            | Nome, sobrenome e nome completo                                                                       | Funcionário atual, Funcionário demitido, Evolução do funcionário |
| Cargo do funcionário           | Título e data de tempo de serviço                                                                                   | Funcionário atual, Funcionário demitido, Evolução do funcionário |
| Evolução do funcionário           | Trabalhadores com o tempo, número de funcionários, empresa e posição                                                        | Empresa, Remuneração, Localização geográfica, Nome do funcionário, Subordinado a, Calendário de compensação, Data, Cargo do funcionário, Dados demográficos, Emprego, Trabalho, Posição, Benefícios |



