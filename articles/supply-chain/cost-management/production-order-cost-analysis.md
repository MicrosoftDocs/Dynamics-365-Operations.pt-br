---
title: Análise de custo da ordem de produção
description: Este artigo oferece informações sobre a análise de custo que você pode fazer para as ordens de produção concluídas e atuais. Você pode analisar os custos estimados e os custos reais usando a página Cálculo de preço ou o relatório Estimativas de custo e avaliações de custo. É possível visualizar as informações sobre os custos estimados e reais (incluindo a quantidade) para cada item de componente, operação de roteiro e custo indireto.
author: AndersGirke
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventCostTrans, ProdCalcTrans, ProdTableJour, ProdTableListPage, ProdSetupHistoricalCost
audience: Application User
ms.reviewer: kamaybac
ms.custom: 79634
ms.assetid: ded5da04-f787-49f7-b5e5-75c2a2b92930
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: mguada
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 50df2a63584d3db0d3b91fabd224e12dffa809d4
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5809629"
---
# <a name="production-order-cost-analysis"></a>Análise de custo da ordem de produção

[!include [banner](../includes/banner.md)]

Este artigo oferece informações sobre a análise de custo que você pode fazer para as ordens de produção concluídas e atuais. Você pode analisar os custos estimados e os custos reais usando a página Cálculo de preço ou o relatório Estimativas de custo e avaliações de custo. É possível visualizar as informações sobre os custos estimados e reais (incluindo a quantidade) para cada item de componente, operação de roteiro e custo indireto.

Os custos reais para uma ordem de produção são feitos com base no consumo de material e operações de banco informados. Você pode acessar transações detalhadas sobre o consumo de material, operações de banco e custos indiretos informados na página **Lançamento de produção**.

## <a name="variance-analysis-for-a-completed-production-order"></a>Análise de variação para uma ordem de produção concluída
As variações refletem uma comparação das atividades de produção relatadas e o cálculo de custos padrão para o item de produção. As variações não refletem uma comparação para os custos previstos da ordem de produção. As atividades de produção relatadas incluem o consumo de material e operações de roteiro, juntamente com os custos indiretos associados e a quantidade relatada como concluída. Os quatro tipos de variação a seguir são calculados:

-   Variação de tamanho do lote
-   Variação de quantidade de produção
-   Variação do preço de produção
-   Variação de substituição de produção

O diagrama a seguir mostra as quatro variações consideradas para a diferença entre os custos reais de uma ordem de produção e os custos calculados na registro de custo do item quando a ordem de produção é finalizada. 

![Variações que são consideradas diferenças em uma ordem de produção concluída](./media/control.jpg) 

Você poderá analisar as variações de produção usando a página **Variação** ou o relatório **Variação de produção**. Use as opções de exibição para exibir as variações detalhadas por item e por recurso de operações ou por grupo de custos. A política de divisão de custos nos parâmetros de estoque determina se as variações serão monitoradas por grupo de custos. Você também pode usar as opções de exibição **única**, **multi** e **total** para exibir variações resumidas. As informações sobre as variações detalhadas podem ajudar a compreender a origem de cada variação. Para prever as variações antes de finalizar uma ordem de produção, analise as informações detalhadas fornecidas no relatório **Estimativas de custo e avaliações de custo**.

## <a name="cost-analysis-for-current-production-orders"></a>Análise de custo para ordens de produção atuais
Relatórios separados fornecem informações sobre cada tipo de transação. Use esses relatórios para analisar custos para atividades de produção relatadas. As informações são exibidas somente para ordens de produção atuais com o status **Iniciada** ou **Relatada como concluída**.

-   **Materiais em andamento**− esse relatório lista as transações de lista de separação relatadas contra as ordens de produção atuais a partir da data de transação especificada. O relatório indica a quantidade de um componente emitida e o valor de custo para cada transação. Use os critérios de seleção de um único item do componente. Por exemplo, você pode imprimir informações sobre a quantidade emitida do componente contra as ordens de produção aplicáveis. A quantidade emitida não é atualizada pelas quantidades relatadas como concluídas para o item principal. Portanto, a quantidade real de matérias-primas em processamento poderá ser exagerada.
-   **Trabalho em andamento**− esse relatório lista as transações de roteiro (ou transações de trabalho) relatadas contra as ordens de produção atuais a partir da data de transação especificada. O relatório indica as horas, o valor e a quantidade (quantidade sem erros e quantidade com erros) relatados para cada transação. Também inclui informações como o número da operação, a ID da operação e o recurso de operações. Adicionalmente, esse relatório mostra o valor e o tempo totais de todas as transações em relação à ordem de produção e a quantidade relatada como concluída.
-   **Custos indiretos em andamento**− esse relatório lista os custos indiretos que foram incorridos conta ordens de produção. Esses dados são feitos com base no consumo de operações de roteiro e de componentes a partir de uma data de transação especificada. Esse relatório indica o tipo de custo indireto (sobretaxa ou taxa), o código da folha de custos para o custo indireto e o valor do custo para cada transação. Esse relatório não fornece informações sobre o cartão de roteiro ou a transação da lista de separação que gerou o custo indireto.
-   **Avaliação de custo de produção em andamento**− o relatório lista o consumo combinado de materiais, operações de roteiro e custo indireto contra as ordens de produção a partir de uma data de transação específica.
-   **Itens concluídos em andamento**− o relatório lista ordens de produção atuais e as transações relatadas como concluídas a partir da data de transação especificada.


<a name="additional-resources"></a>Recursos adicionais
--------

[Fontes comuns de variações de produção](common-sources-of-production-variances.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]