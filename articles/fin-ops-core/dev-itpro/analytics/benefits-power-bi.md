---
title: Conteúdo de benefícios do Power BI
description: Este tópico descreve o conteúdo de benefícios do Power BI.
author: jcart1106
manager: AnnBe
ms.date: 12/19/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: HcmBenefitWorkspace
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.openlocfilehash: 5a894ebfb79eab4888178c930b9e7d55cf735c91
ms.sourcegitcommit: 5192cfaedfd861faea63d8954d7bcc500608a225
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/30/2021
ms.locfileid: "5093072"
---
# <a name="benefits-power-bi-content"></a>Conteúdo de benefícios do Power BI

[!include [banner](../includes/banner.md)]

Este tópico descreve o conteúdo de **Benefícios** do Microsoft Power BI. Ele explica como acessar os relatórios incluídos no conteúdo, além de fornecer informações sobre o modelo de dados e as entidades usadas para criar o conteúdo.

## <a name="accessing-the-power-bi-content"></a>Acessando o conteúdo do Power BI
O conteúdo de **Benefícios** do Power BI é mostrado no espaço de trabalho **Gerenciamento de benefícios** se você usa um dos seguintes produtos:

- Microsoft Dynamics 365 Finance
- Microsoft Dynamics 365 Human Resources

## <a name="reports-that-are-included-in-the-power-bi-content"></a>Relatórios incluídos no conteúdo do Power BI
Os relatórios incluídos no conteúdo de **Benefícios** do Power BI têm gráficos e tabelas com informações adicionais. A tabela a seguir descreve os relatórios.

| Relatório                      | Conteúdo                                                                                       |
|-----------------------------|------------------------------------------------------------------------------------------------|
| Visão geral da inscrição no benefício | Mais e menos planos inscritos, registro por grupo de funcionários e as opções selecionadas do plano de benefícios |
| Benefícios do funcionário           | Inscrição do funcionário por benefício selecionado                                                        |

Você pode filtrar os gráficos e blocos nesses relatórios e fixá-los no painel. Para obter mais informações sobre como filtrar e fixar no Power BI, consulte [Criar e Configurar um Painel](https://powerbi.microsoft.com/guided-learning/powerbi-learning-4-2-create-configure-dashboards).

## <a name="understanding-the-data-model-and-entities"></a>Noções básicas sobre o modelo de dados e as entidades
Os dados a seguir são utilizados para preencher os relatórios no conteúdo de **Benefícios** do Power BI. Esta tabela mostra as entidades nas quais o conteúdo foi baseado.

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
| Funcionário demitido      | Funcionários demitidos, data da demissão, cargo, posição e trabalho                                           | Empresa, Remuneração, Localização geográfica, Nome do funcionário, Subordinado a, Calendário de compensação, Data, Cargo do funcionário, Dados demográficos, Emprego, Trabalho, Posição, Benefícios |
| Benefícios                 | Data de efetivação, opção de benefício, plano de benefício e tipo de benefício                                             | Nome atual, Funcionário demitido, Evolução do funcionário |
| Nome do Funcionário            | Nome, sobrenome e nome completo                                                                       | Funcionário atual, Funcionário demitido, Evolução do funcionário |
| Cargo do funcionário           | Título e data de tempo de serviço                                                                                   | Funcionário atual, Funcionário demitido, Evolução do funcionário |
| Evolução do funcionário           | Trabalhadores com o tempo, número de funcionários, empresa e posição                                                        | Empresa, Remuneração, Localização geográfica, Nome do funcionário, Subordinado a, Calendário de compensação, Data, Cargo do funcionário, Dados demográficos, Emprego, Trabalho, Posição, Benefícios |


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]