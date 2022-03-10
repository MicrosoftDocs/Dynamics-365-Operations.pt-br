---
title: Previsões de pagamento do cliente
description: Este tópico descreve o recurso de previsões de pagamento que pode ajudar a entender melhor as práticas de pagamento típicas de um cliente. Esse recurso também pode ajudar a identificar as circunstâncias que devem causar o início de processos de cobrança antes do que você espera.
author: ShivamPandey-msft
ms.date: 11/03/2021
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom:
- "14151"
- intro-internal
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2019-11-06
ms.dyn365.ops.version: AX 10.0.8
ms.openlocfilehash: 04897e3a7765264ab2e664422caa928c49b9cc61
ms.sourcegitcommit: 3754d916799595eb611ceabe45a52c6280a98992
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2022
ms.locfileid: "7982028"
---
# <a name="customer-payment-predictions"></a>Previsões de pagamento do cliente

[!include [banner](../includes/banner.md)]

Este tópico descreve o recurso de previsões de pagamento que pode ajudar a entender melhor as práticas de pagamento típicas de um cliente. Esse recurso também pode ajudar a identificar as circunstâncias que devem causar o início de processos de cobranças antes do que você espera.

## <a name="overview"></a>Visão Geral

As organizações geralmente acham difícil prever quando os clientes pagarão suas faturas. Essa falta de insight pode causar os seguintes problemas:

- Previsões de fluxo de caixa menos precisas
- Processos de cobranças que iniciam muito tarde
- Ordens liberadas para clientes que podem não cumprir o pagamento

Previsões de pagamento de cliente ajudam as organizações a prever quando uma fatura de cliente será paga. Portanto, eles podem criar estratégias de cobranças que ajudam a aumentar a probabilidade de serem pagas no prazo.

## <a name="predictions"></a>Previsões

As previsões de pagamento permitem que as organizações melhorem seus processos comerciais, ajudando-os a identificar as faturas que provavelmente serão pagas com atraso. A organização pode usar essas informações para realizar ações que melhorem as chances de que elas sejam pagas no prazo.

O recurso Previsões de pagamento de cliente usa um modelo de aprendizado de máquina para prever com mais precisão quando um cliente pagará uma fatura pendente. Esse modelo de aprendizagem de máquina inclui faturas históricas, pagamentos e dados de clientes.

Para cada fatura aberta, o recurso atribui três probabilidades de pagamento:

- A probabilidade de que o pagamento seja feito no prazo
- A probabilidade de que o pagamento seja feito com atraso
- A probabilidade de que o pagamento seja feito com muito atraso

O recurso também fornece uma exibição agregada de pagamentos esperados.

[![Exibição agregada de previsões de pagamento.](./media/graphic-payment-reports.png)](./media/graphic-payment-reports.png)

Cada fatura recebe uma probabilidade de pagamento no prazo. As faturas com uma probabilidade de pagamento no prazo inferior a 50% são marcadas com um círculo vermelho para indicar que elas exigem a atenção de um agente de cobranças.

[![Lista de probabilidades de pagamento.](./media/customer-pymnt-probability-list.png)](./media/customer-pymnt-probability-list.png)

O recurso Previsões de pagamento de cliente também fornece informações contextuais para explicar a previsão. Essas informações incluem os principais fatores que influenciam a previsão, o estado atual de negócios com o cliente e detalhes sobre o comportamento do pagamento histórico do cliente.

Em muitas empresas, o processo de cobranças tem sido uma atividade reativa. Em outras palavras, o processo de cobranças não inicia até que as faturas vençam. As previsões de pagamento de cliente permitem que as organizações sejam mais proativas sobre as cobranças. Elas não precisam mais esperar que uma transação vença para iniciar o processo de cobranças. Em vez disso, elas podem usar o recurso de previsões de pagamento para determinar se as cobranças proativas aumentará a probabilidade de o pagamento ser feito no prazo.

## <a name="methodology"></a>Metodologia

No passado, normalmente era difícil desenvolver e implantar uma solução de IA (inteligência artificial). O processo exigia uma equipe com cientistas de dados, especialistas no assunto (SMEs) e engenheiros trabalhando por um período extenso para formular, desenvolver, implantar e manter uma solução útil de IA. As previsões de pagamento do cliente facilitam a implantação e o uso de uma solução de IA no Microsoft Dynamics 365 Finance. A Microsoft está pré-embalando soluções de IA criadas com base no Microsoft AI Builder. Portanto, os usuários podem implantar a solução de IA em um único clique do mouse para aproveitar as vantagens das previsões inteligentes. Se você não estiver satisfeito com a precisão das previsões, um usuário avançado poderá (novamente, com um único clique do mouse) entrar na experiência de extensão do AI Builder e, depois, marcar ou desmarcar os campos usados para gerar previsões. Quando estiver pronto, você poderá "treinar" o modelo e publicar as alterações. O modelo recentemente treinado será automaticamente retirado para gerar previsões no Dynamics 365 Finance.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
