---
title: Previsões de pagamento do cliente (versão preliminar)
description: Este tópico descreve o recurso de previsões de pagamento que pode ajudar a entender melhor as práticas de pagamento típicas de um cliente. Esse recurso também pode ajudar a identificar as circunstâncias que devem causar o início de processos de cobrança antes do que você espera.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 05/26/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 14151
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2019-11-06
ms.dyn365.ops.version: AX 10.0.8
ms.openlocfilehash: f306f9437b78005d8b8aa11f0b6f210ebdd4fd2a
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4995056"
---
# <a name="customer-payment-predictions-preview"></a>Previsões de pagamento do cliente (versão preliminar)

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Este tópico descreve o recurso de previsões de pagamento que pode ajudar a entender melhor as práticas de pagamento típicas de um cliente. Esse recurso também pode ajudar a identificar as circunstâncias que devem causar o início de processos de cobranças antes do que você espera.

## <a name="overview"></a>Visão Geral

As organizações geralmente acham difícil prever quando os clientes pagarão suas faturas. Essa falta de insight pode causar os seguintes problemas:

- Previsões de fluxo de caixa menos precisas
- Processos de cobranças que iniciam muito tarde
- Ordens liberadas para clientes que podem não cumprir o pagamento

Previsões de pagamento de cliente (versão preliminar) ajudam as organizações a prever quando uma fatura de cliente será paga. Portanto, eles podem criar estratégias de cobranças que ajudam a aumentar a probabilidade de serem pagas no prazo.

## <a name="predictions"></a>Previsões

As previsões de pagamento permitem que as organizações melhorem seus processos comerciais, ajudando-os a identificar as faturas que provavelmente serão pagas com atraso. A organização pode usar essas informações para realizar ações que melhorem as chances de que elas sejam pagas no prazo.

O recurso Previsões de pagamento de cliente usa um modelo de aprendizado de máquina para prever com mais precisão quando um cliente pagará uma fatura pendente. Esse modelo de aprendizagem de máquina inclui faturas históricas, pagamentos e dados de clientes.

Para cada fatura aberta, o recurso atribui três probabilidades de pagamento:

- A probabilidade de que o pagamento seja feito no prazo
- A probabilidade de que o pagamento seja feito com atraso
- A probabilidade de que o pagamento seja feito com muito atraso

O recurso também fornece uma exibição agregada de pagamentos esperados.

[![Exibição agregada de previsões de pagamento](./media/graphic-payment-reports.png)](./media/graphic-payment-reports.png)

Cada fatura recebe uma probabilidade de pagamento no prazo. As faturas com uma probabilidade de pagamento no prazo inferior a 50% são marcadas com um círculo vermelho para indicar que elas exigem a atenção de um agente de cobranças.

[![Lista de probabilidades de pagamento](./media/customer-pymnt-probability-list.png)](./media/customer-pymnt-probability-list.png)

O recurso Previsões de pagamento de cliente também fornece informações contextuais para explicar a previsão. Essas informações incluem os principais fatores que influenciam a previsão, o estado atual de negócios com o cliente e detalhes sobre o comportamento do pagamento histórico do cliente.

Em muitas empresas, o processo de cobranças tem sido uma atividade reativa. Em outras palavras, o processo de cobranças não inicia até que as faturas vençam. As previsões de pagamento de cliente permitem que as organizações sejam mais proativas sobre as cobranças. Elas não precisam mais esperar que uma transação vença para iniciar o processo de cobranças. Em vez disso, elas podem usar o recurso de previsões de pagamento para determinar se as cobranças proativas aumentará a probabilidade de o pagamento ser feito no prazo.

## <a name="methodology"></a>Metodologia

No passado, normalmente era difícil desenvolver e implantar uma solução de IA (inteligência artificial). O processo exigia uma equipe com cientistas de dados, especialistas no assunto (SMEs) e engenheiros trabalhando por um período extenso para formular, desenvolver, implantar e manter uma solução útil de IA. As previsões de pagamento do cliente facilitam a implantação e o uso de uma solução de IA no Microsoft Dynamics 365 Finance. A Microsoft está pré-embalando soluções de IA criadas com base no Microsoft AI Builder. Portanto, os usuários podem implantar a solução de IA em um único clique do mouse para aproveitar as vantagens das previsões inteligentes. Se você não estiver satisfeito com a precisão das previsões, um usuário avançado poderá (novamente, com um único clique do mouse) entrar na experiência de extensão do AI builder e então marcar ou desmarcar os campos usados para gerar previsões. Quando estiver pronto, você poderá "treinar" o modelo e publicar as alterações. O modelo recentemente treinado será automaticamente retirado para gerar previsões no Dynamics 365 Finance.

## <a name="release-details"></a>Detalhes da liberação

A versão preliminar pública do Finance Insights está disponível para implantações de avaliação nos Estados Unidos da América, na Europa e no Reino Unido. A Microsoft está adicionando suporte para outras regiões de forma incremental.

Os recursos de versão preliminar pública devem ser ativados somente em ambientes de área restrita de Camada 2. A Configuração e os Modelos de IA criados em um ambiente de área restrita podem não ser migrados para o ambiente de produção. Para obter mais informações, consulte [Termos de uso suplementares para versões preliminares do Microsoft Dynamics 365](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/public-preview-terms).

## <a name="privacy-notice"></a>Aviso de privacidade

As versões prévias (1) podem utilizar menos medidas de privacidade e segurança que o serviço do Dynamics 365 Finance and Operations, (2) não estão incluídas no contrato de nível de serviço (SLA) desse serviço, (3) não devem ser usadas para processar dados pessoais ou outros dados sujeitos a requisitos de conformidade legais ou regulatórios e (4) têm suporte limitado.
