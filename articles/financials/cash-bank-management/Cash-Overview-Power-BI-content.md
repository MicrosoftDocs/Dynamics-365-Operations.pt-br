---
title: "Visão geral do conteúdo de caixa do Power BI"
description: "Este tópico descreve a visão geral do conteúdo de caixa do Power BI. Ele explica como acessar os relatórios incluídos no conteúdo, além de fornecer informações sobre o modelo de dados e as entidades usadas para criar o conteúdo."
author: saraschi2
manager: AnnBe
ms.date: 06/22/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: sericks
ms.search.scope: Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: fdcd3083f475967ec2e5f94dad850a1bf98c864a
ms.contentlocale: pt-br
ms.lasthandoff: 11/03/2017

---

# <a name="cash-overview-power-bi-content"></a>Visão geral do conteúdo de caixa do Power BI

[!include[banner](../includes/banner.md)]

Este tópico descreve o conteúdo da **Visão geral de caixa** do Microsoft Power BI. Ele explica como acessar os relatórios incluídos no conteúdo, além de fornecer informações sobre o modelo de dados e as entidades usadas para criar o conteúdo.

## <a name="overview"></a>Visão Geral

O conteúdo **Visão geral do caixa** do Power BI foi criado para pessoas que são responsáveis por dinheiro em sua organização. O conteúdo **Visão geral do caixa** do Power BI fornece visibilidade para seu fluxo de caixa. Também fornece as previsões que podem ajudá-lo a tomar as melhores decisões e melhorar a integridade de seu fluxo de caixa. Você pode analisar o caixa por entidade legal, por moeda e por conta bancária para obter melhor o conhecimento de pontos fracos ou deficiências.

## <a name="accessing-the-power-bi-content"></a>Acessando o conteúdo do Power BI

Se estiver usando o Dynamics 365 for Finance and Operations, Enterprise Edition (julho de 2017), os relatórios do conteúdo da **Visão geral de caixa** do Power BI serão exibidos nos espaços de trabalho **Visão geral de caixa** e **Gerenciamento bancário**.

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

## <a name="extending-the-power-bi-content"></a>Aumentando o conteúdo do Power BI
Você pode fornecer grandes análises àqueles que não entram no Dynamics 365 usando os pacotes de conteúdo disponíveis no Lifecycle Services (LCS). Estes pacotes de conteúdo podem ser modificados para incluir outros relatórios ou visuais, em seguida, publicados em seu locatário do Power BI.com para análise. 

Você pode localizar o conteúdo **Visão geral do Caixa** do Power BI na biblioteca de ativos compartilhados do LCS. Para obter mais informações sobre como baixar o pacote de conteúdo e implementá-lo na sua organização, consulte [Conteúdo do Power BI no LCS da Microsoft e seus parceiros](../../dev-itpro/analytics/power-bi-content-microsoft-partners.md). Para ver uma demonstração que mostra como implementar o conteúdo do Power BI, veja o Office Mix [Conteúdo do Power BI da Microsoft e seus parceiros no Dynamics Lifecycle Services](https://mix.office.com/watch/9puyb1b2xs1w).

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

Essas entidades foram usadas para criar medidas calculadas no modelo de dados. Essas medidas calculadas são então usadas para calcular os gráficos e relatórios usados no conteúdo **Visão geral de caixa** do Power BI. Para incluir cálculos adicionais nos seus relatórios e painel, você pode baixar e modificar o arquivo do Power BI do LCS. Esse arquivo é o modelo de dados padrão usado para criar o conteúdo. Após a realização de modificações, poderá criar painéis e pacote de conteúdo organizacional contendo as informações adicionadas.


