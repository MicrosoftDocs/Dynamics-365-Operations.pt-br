---
title: "Visão geral do conteúdo de caixa do Power BI"
description: "Este tópico descreve a visão geral do conteúdo de caixa do Power BI. Ele explica como acessar os relatórios incluídos no conteúdo, além de fornecer informações sobre o modelo de dados e as entidades usadas para criar o conteúdo."
author: saraschi2
manager: AnnBe
ms.date: 12/19/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: BankTreasurerWorkspace
audience: Application User
ms.reviewer: sericks
ms.search.scope: Operations, Core
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: cb43245afe578341251b140383a3b03ba2abd962
ms.openlocfilehash: 5d02a009ca988f91a212e467d4f9784248bbae76
ms.contentlocale: pt-br
ms.lasthandoff: 12/19/2017

---

# <a name="cash-overview-power-bi-content"></a>Visão geral do conteúdo de caixa do Power BI

[!include[banner](../includes/banner.md)]

Este tópico descreve o conteúdo da **Visão geral de caixa** do Microsoft Power BI. Ele explica como acessar os relatórios incluídos no conteúdo, além de fornecer informações sobre o modelo de dados e as entidades usadas para criar o conteúdo.

## <a name="overview"></a>Visão Geral

O conteúdo **Visão geral do caixa** do Power BI foi criado para pessoas que são responsáveis por dinheiro em sua organização. O conteúdo **Visão geral do caixa** do Power BI fornece visibilidade para seu fluxo de caixa. Também fornece as previsões que podem ajudá-lo a tomar as melhores decisões e melhorar a integridade de seu fluxo de caixa. Você pode analisar o caixa por entidade legal, por moeda e por conta bancária para obter melhor o conhecimento de pontos fracos ou deficiências.

## <a name="accessing-the-power-bi-content"></a>Acessando o conteúdo do Power BI

Relatórios do conteúdo do Power BI para **Visão geral do caixa** são exibidos nos espaços de trabalho **Visão geral do caixa** e **Gerenciamento bancário**.

Para exibir os relatórios de previsão de fluxo de caixa com dados, primeiro é preciso executar o processo de cálculo de previsão usando a função **Calcular previsões de fluxo de caixa** na área Gerenciamento de caixa e bancos.  Isso precisa ser concluído para cada empresa incluída na previsão.  Depois, é preciso atualizar a medida agregada LedgerCovLiquidityMeasurement na página **Repositório de Entidades**.  

Para fins de demonstração, você pode adicionar os dados de demonstração de previsão de fluxo de caixa usando a página **Gerar dados** no módulo Dados de demonstração.  Este script inserirá os dados nas tabelas de previsão de fluxo de caixa para que as informações necessárias aos relatórios sejam preenchidas rapidamente.  Este módulo só estará disponível se você tiver o modelo de conjunto Dados de demonstração implantado no ambiente. 

## <a name="reports-that-are-included-in-the-power-bi-content"></a>Relatórios incluídos no conteúdo do Power BI
A tabela a seguir fornece detalhes sobre as métricas encontradas em cada página de relatório no conteúdo **Visão geral de caixa** do Power BI.

| Relatório                                | Conteúdo |
|---------------------------------------|----------|
| Visão geral de caixa - todas as empresas         | <ul><li>Entradas e saídas na moeda do sistema</li><li>Saldos da moeda previstos</li><li>Saldo bancário total na moeda do sistema</li><li>Saldo por entidade legal</li><li>Saldo real de hoje vs previsto na moeda da conta bancária</li></ul> |
| Visão geral de caixa - empresa atual       | <ul><li>Entradas e saídas na moeda contábil</li><li>Saldos da moeda previstos</li><li>Saldo bancário total na moeda contábil</li><li>Saldo real de hoje vs previsto na moeda da conta bancária</li></ul> |
| Previsão de fluxo de caixa – todas as empresas    | <ul><li>Entradas e saídas na moeda do sistema</li><li>Resumo diário de previsão</li><li>Detalhes de previsão</li></ul> |
| Moeda de fluxo de caixa - moeda da empresa | <ul><li>Entradas e saídas na moeda contábil</li><li>Resumo diário de previsão</li><li>Detalhes de previsão</li></ul> |
| Previsão atual                     | <ul><li>Saldos da moeda previstos</li><li>Resumo diário de moeda</li><li>Detalhes de previsão</li></ul> |
| Saldos bancários                         | <ul><li>Saldo bancário total na moeda do sistema</li><li>Saldo por entidade legal</li><li>Saldo real de hoje vs previsto na moeda da conta bancária</li><li>Saldo por conta bancária</li><li>Saldo por moeda</li></ul> |


## <a name="understanding-the-data-model-and-entities"></a>Noções básicas sobre o modelo de dados e as entidades

A seguinte tabela mostra as entidades nas quais o conteúdo **Visão geral de caixa** do Power BI foi baseado.

| Entidade                                                                          | Conteúdo |
|---------------------------------------------------------------------------------|----------|
| LedgerCovLiquidityMeasurement\_Company                                          | Empresas para filtrar relatórios |
| LedgerCovLiquidityMeasurement\_Date                                             | Datas para filtrar relatórios por |
| LedgerCovLiquidityMeasurement\_LedgerCovForecastActual                          | O saldo bancário real vs o último saldo bancário previsto |
| LedgerCovLiquidityMeasurement\_LedgerCovLiquidity                               | Detalhes de transação prevista |
| LedgerCovLiquidityMeasurement\_LedgerCovLiquidityInflowOutflowBalanceCompany    | Entradas, saídas e saldo resumido usando cada moeda contábil da empresa |
| LedgerCovLiquidityMeasurement\_LedgerCovLiquidityInflowOutflowBalanceEnterprise | Entradas, saídas e saldo resumido usando a moeda do sistema de todas as empresas |
| LedgerCovLiquidityMeasurement\_LedgerCovLiquidityTransactionCurrency            | Valor da transação e saldo de moeda líquida resumidos usando a moeda da transação |



