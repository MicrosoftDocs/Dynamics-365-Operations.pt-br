---
title: "Conteúdo de benefícios do Power BI"
description: "Este tópico descreve o conteúdo de benefícios do Power BI. Ele explica como acessar os relatórios incluídos no conteúdo, além de fornecer informações sobre o modelo de dados e as entidades usadas para criar o conteúdo."
author: jcart1106
manager: AnnBe
ms.date: 05/24/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User, IT Pro
ms.search.scope: Operations, UnifiedOperations, Talent, Core
ms.search.region: Global
ms.author: JCart
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.translationtype: Human Translation
ms.sourcegitcommit: 869151f2486b7a481e4694cfb6992d0ee2cfc008
ms.openlocfilehash: 815d8ecfe85c1000667d2d289c05c1e98b8b8c76
ms.contentlocale: pt-br
ms.lasthandoff: 06/13/2017

---

# <a name="benefits-power-bi-content"></a>Conteúdo de benefícios do Power BI

[!include[banner](../includes/banner.md)]

Este tópico descreve o conteúdo de **Benefícios** do Microsoft Power BI. Ele explica como acessar os relatórios incluídos no conteúdo, além de fornecer informações sobre o modelo de dados e as entidades usadas para criar o conteúdo.

## <a name="accessing-the-power-bi-content"></a>Acessando o conteúdo do Power BI
O conteúdo de **Benefícios** do Power BI é mostrado no espaço de trabalho **Gerenciamento de benefícios** se você usar um dos seguintes produtos:

- Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition atualização de julho de 2017
- Microsoft Dynamics 365 for Talent

## <a name="reports-that-are-included-in-the-power-bi-content"></a>Relatórios incluídos no conteúdo do Power BI
Os relatórios incluídos no conteúdo de **Benefícios** do Power BI têm gráficos e tabelas que contêm informações adicionais. A tabela a seguir descreve os relatórios.

| Relatório                       | Conteúdo                                                                                       |
|------------------------------|------------------------------------------------------------------------------------------------|
| Visão geral da inscrição no benefício  | Mais e menos planos inscritos, registro por grupo de funcionários e as opções selecionadas do plano de benefícios |
| Benefícios do funcionário            | Inscrição do funcionário por benefício selecionado                                                        |
                                                                                             
Você pode filtrar os gráficos e blocos nesses relatórios e fixá-los no painel. Para obter mais informações sobre como filtrar e fixar no Power BI, consulte [Criar e configurar um painel](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-4-2-create-configure-dashboards).

## <a name="extending-the-power-bi-content"></a>Aumentando o conteúdo do Power BI
Usando os pacotes de conteúdo disponíveis no Microsoft Dynamics Lifecycle Services (LCS), você pode fornecer grande análise às pessoas que não acessam o Finance and Operations. Você pode modificar esses pacotes de conteúdo para que eles incluam outros relatórios ou imagens e, em seguida, publique os pacotes de conteúdo no locatário do Power BI.com para análise.

Você pode localizar o conteúdo do Power BI **Benefícios** na biblioteca de ativos compartilhados do LCS. Para obter mais informações sobre como baixar o pacote de conteúdo e implementá-lo na sua organização, consulte [Conteúdo do Power BI no LCS da Microsoft e seus parceiros](power-bi-content-microsoft-partners.md). Para ver uma demonstração que mostra como implementar o conteúdo do Power BI, veja o Office Mix [Conteúdo do Power BI da Microsoft e seus parceiros no Dynamics Lifecycle Services](https://mix.office.com/watch/9puyb1b2xs1w).

>[!NOTE]
>Os arquivos .pbix disponíveis no Lifecycle Services aplicam-se somente ao Finance and Operations.

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
| Localização geográfica      | Cidade, região, CEP e estado ou província                                                           | Funcionário atual, Funcionário demitido, Evolução do funcionário |
| Trabalho                      | Função, tipo e título                                                                                  | Posição atual, funcionário atual |
| Atribuição da última posição | Motivo da atribuição, data inicial, data final e trabalho                                                           | Compensação de calendário, data, trabalho, posição |
| Cargo                 | Departamento, FTE, posição, tipo de posição e título                                                        | Posição atual, funcionário atual |
| Tendência da posição           | Posições com o tempo, FTE e trabalho                                                                          | Compensação de calendário, data, trabalho, posição |
| Subordinado a               | Nome, sobrenome e nome completo                                                                       | Trabalhador atual, Funcionário demitido, Evolução do funcionário |
| Funcionário demitido      | Funcionários demitidos, data da demissão, cargo, posição e trabalho                                           | Empresa, Remuneração, Localização geográfica, Nome do funcionário, Subordinado a, Calendário de compensação, Data, Cargo do funcionário, Dados demográficos, Emprego, Trabalho, Posição, Benefícios |
| Benefícios                 | Data de efetivação, opção de benefício, plano de benefício e tipo de benefício                                             | Nome atual, Funcionário demitido, Evolução do funcionário |
| Nome do Funcionário            | Nome, sobrenome e nome completo                                                                       | Funcionário atual, Funcionário demitido, Evolução do funcionário |
| Cargo do funcionário           | Título e data de tempo de serviço                                                                                   | Funcionário atual, Funcionário demitido, Evolução do funcionário |
| Evolução do funcionário           | Trabalhadores com o tempo, número de funcionários, empresa e posição                                                        | Empresa, Remuneração, Localização geográfica, Nome do funcionário, Subordinado a, Calendário de compensação, Data, Cargo do funcionário, Dados demográficos, Emprego, Trabalho, Posição, Benefícios |

Essas entidades foram usadas para criar medidas calculadas no modelo de dados. Essas medidas calculadas são então usadas para calcular os KPIs (indicadores chave de desempenho) e os relatórios usados no conteúdo. Se quiser incluir cálculos adicionais nos seus relatórios e painel, você pode baixar e modificar o arquivo .pbix no LCS. Esse arquivo é o modelo de dados padrão usado para criar o conteúdo. Após a realização de modificações, poderá criar um painel e pacote de conteúdo organizacional contendo as informações adicionadas.
