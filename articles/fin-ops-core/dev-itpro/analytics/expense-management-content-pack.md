---
title: Conteúdo do Power BI sobre gerenciamento de despesas
description: Este tópico descreve o que está incluído no pacote de conteúdo de Gerenciamento de despesas do Power BI.
author: panolte
manager: AnnBe
ms.date: 03/18/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: TrvExpenseWorkspace, ExpenseWorkspace
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kfend
ms.search.validFrom: 2018-10-31
ms.dyn365.ops.version: 8.0999999999999996
ms.openlocfilehash: be40d56f2468ec9490796aae9ef107b5f22aa9e7
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/09/2021
ms.locfileid: "5568890"
---
# <a name="expense-management-power-bi-content"></a>Conteúdo do Power BI sobre gerenciamento de despesas

[!include [banner](../includes/banner.md)]

Este tópico descreve o que está incluído no conteúdo de Gerenciamento de despesas do Power BI. 

## <a name="overview"></a>Visão Geral
Dois pacotes de conteúdo do Power BI estão disponíveis para uso com o Gerenciamento de despesas na versão 8.1 ou posterior. 
- Há um painel pessoal criado para os funcionários que enviam relatórios de despesas. 

  O painel foi ajustado para fornecer às pessoas informações importantes sobre valores enviados e não enviados, além de um histórico e de insights sobre o histórico de transações de despesa. O painel pessoal é uma única página que contém as informações mais importantes para o usuário.

- Há um painel admin criado para caixeiros e gerentes de contas a pagar. O painel foi ajustado para o controle e o relatório das despesas gerais do funcionário. Ele fornece as principais métricas de despesa, como despesas não enviadas, quilometragem os valores médios dos relatório de despesas. Ele usa dados transacionais e fornece exibições agregadas do gerenciamento de despesas entre todas as empresas. Ele também fornece um detalhamento por funcionário, com a opção de incluir dados de dimensão financeira. O conteúdo da Análise de despesas de administrador inclui: 
  - Uma página de visão geral com as principais métricas sobre os valores das despesas e insights dos relatórios de despesa de rascunho, em andamento e concluídos. 
  - Uma página de estatísticas do funcionário para examinar detalhes individuais sobre um funcionário por tempo, por tipo de custo e por grupo de estatísticas. 
  - Uma página de comparação do funcionário para comparar vários funcionários ao longo do tempo. 

Todos os valores são mostrados na moeda da empresa. Os dados de todas as empresas são mostrados, mas se necessário, é possível adicionar um filtro de empresa. 

## <a name="accessing-the-power-bi-content"></a>Acessando o conteúdo do Power BI
Você pode encontrar o conteúdo Painel de Despesas de Administrador.pbix e Painel de Despesas Pessoais.pbix do Power BI na Biblioteca de ativos compartilhados no Microsoft Dynamics Lifecycle Services (LCS). Para obter mais informações sobre como baixar o pacote de conteúdo e implementá-lo na sua organização, consulte [Conteúdo do Power BI no LCS da Microsoft e de seus parceiros](https://blogs.msdn.microsoft.com/dynamicsaxbi/2016/12/12/power-bi-content-from-microsoft-and-your-partners/).
O conteúdo está disponível no espaço de trabalho de despesas Gerenciamento de Despesas como conteúdo integrado do Power BI. Os proprietários de despesas podem acessar suas próprias despesas pessoais, enquanto somente os funcionários e gerentes de Contas a pagar têm acesso ao conteúdo de administrador para exibir dados de despesas de todos os usuários.

## <a name="refreshing-the-power-bi-content"></a>Atualizando o conteúdo do Power BI
O conteúdo de Gerenciamento de despesas do Power BI requer que as medidas TrvBiExpenseMeasurement e a BudgetActivityMeasure sejam atualizadas no Repositório de Entidades. 

## <a name="metrics-that-are-included-in-the-power-bi-content"></a>Métricas incluídas no conteúdo do Power BI
O conteúdo inclui um conjunto de páginas de relatório. Cada página consiste em um conjunto de métricas visualizadas, como gráficos, blocos e tabelas. A tabela a seguir fornece uma visão geral das visualizações no conteúdo do Power BI.

**Análise de despesas pessoais**

| Página de relatório | Visualização                             |
|-------------|-------------------------------------------|
| Minhas despesas | Valor da quilometragem                         |
|             | Relatórios de despesas em andamento                |
|             | Nº de despesas não enviadas               |
|             | Despesas pessoais a serem pagas              |
|             | Valor não enviado                        |
|             | Valor enviado                          |
|             | Valor aguardando reembolso             |
|             | Relatórios de despesas com valores e status   |
|             | Relatórios de despesas enviados mas não aprovados  |
|             | Despesas por tipo de custo                     |
|             | Despesas por comerciante                      |
|             | Despesas por despesas processadas            |
|             | Despesas por projeto                       |
|             | Valor total das transações ao longo de tempo        |

**Análise de despesas de administrador**

| Página de relatório         | Visualização                           |           
|---------------------|-----------------------------------------|
| Visão geral de despesas    | Valor de despesas de rascunho                   |
|                     | Número de linhas de despesas de rascunho           |
|                     | Linhas de despesas de rascunho                     |
|                     | Violações da política de relatório de despesas        |
|                     | Valor pendente                      |
|                     | Despesas enviadas mas não aprovadas       |
|                     | Despesas aprovadas                       |
|                     | Valor total de despesas                    |
|                     | Resumos dos relatórios de despesas                |
|                     | Despesas por tipo de custo                   |
|                     | Despesas por comerciante                    |
|                     | Despesas por funcionários                   |
|                     | Despesas vs projeto                     |
| Comparação de funcionários | Valores de despesa                         |
|                     | Valores de despesa ao longo do tempo por funcionário   |
| Estatísticas do funcionário | Relatórios de despesas por tipo de custo            |
|                     | Despesas pessoais                       |
|                     | Relatórios de despesas por grupo de estatísticas     |


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]