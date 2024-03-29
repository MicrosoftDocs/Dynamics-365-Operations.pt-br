---
title: Conteúdo do Power BI real vs orçamento
description: Este artigo descreve o conteúdo do Power BI real versus orçamento. Ele explica como acessar os relatórios e fornece informações sobre o modelo de dados.
author: panolte
ms.date: 12/18/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BudgetTrackingWorkspace
audience: Application user, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: panolte
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.openlocfilehash: ff57d052b66103ad716ad8d55afb4fcb095d2c02
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8847272"
---
# <a name="actual-vs-budget-power-bi-content"></a>Conteúdo do Power BI real vs orçamento

[!include [banner](../includes/banner.md)]

Este artigo descreve o conteúdo do Microsoft Power BI **real versus orçamento**. Ele explica como acessar os relatórios do Power BI e fornece informações sobre o modelo de dados e entidades que foram usados para criar o conteúdo.

## <a name="overview"></a>Visão Geral

O conteúdo do **Real vs orçamento** do Power BI foi criado para indivíduos responsáveis por monitorar o desempenho real versus orçamento da organização. O conteúdo **Real vs orçamento** do Power BI fornece visibilidade em suas variações de orçamento. Você pode analisar o orçamento do ano atual por categoria de conta, código de orçamento, conta principal, descrições de conta principal ou período fiscal para obter um melhor entendimento sobre a causa das variações.

## <a name="accessing-the-power-bi-content"></a>Acessando o conteúdo do Power BI
Os relatórios de conteúdo **Real vs orçamento** do Power BI são mostrados nos espaços de trabalho **Orçamentos e previsão do razão** e **CFO**.

## <a name="reports-that-are-included-in-the-power-bi-content"></a>Relatórios incluídos no conteúdo do Power BI
A tabela a seguir fornece detalhes sobre as métricas encontradas em cada página de relatório no conteúdo **Real vs orçamento** do Power BI.

| Relatório                      | Métrica                                                                             |
|-----------------------------|-------------------------------------------------------------------------------------|
| Despesas - Real vs de orçamento | <ul><li>Despesas totais deste ano</li><li>Total de despesas de orçamento deste ano</li></ul>  |
| Receita - Real vs de Orçamento  | <ul><li>Receita total deste ano</li><li>Receita total de orçamento deste ano</li><ul>     |
| Despesa                     | <ul><li>Despesas totais deste ano</li><li>Meta de despesas com base no orçamento</li><ul> |
| Receita                     | <ul><li>Receita total deste ano</li><li>Meta de receita com base no orçamento</li><ul>   |
| Renda líquida                  | <ul><li>Rendimento líquido deste ano</li><li>Meta de rendimento líquido com base no orçamento</li><ul>   |

## <a name="understanding-the-data-model-and-entities"></a>Noções básicas sobre o modelo de dados e as entidades

| Entidade                    | Conteúdo                                                                         |
|---------------------------|----------------------------------------------------------------------------------|
| Atividades de contabilidade | Valores de transação referente à contabilidade                                       |
| Atividades de orçamento         | Valores de transação para o registro de orçamento                                      |
| Contas Principais             | Contas principais para filtrar relatórios                                               |
| Calendários fiscais          | Calendários fiscais para filtrar relatórios                                            |
| Razões                   | Razões que podem ser usados para filtrar relatório para o razão atual              |
| Códigos de orçamento              | Códigos de orçamento para filtrar relatórios                                                |
| Entidades legais            | Entidades legais que podem ser usadas para filtrar relatório para a entidade legal atual |


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]