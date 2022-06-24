---
title: Insights de pagamento de cliente (versão preliminar)
description: Este artigo descreve o recurso de insights de pagamento que ajuda a melhorar a compreensão das práticas de pagamento típicas de clientes individuais. O recurso pode ajudá-lo a identificar as circunstâncias que justificam o início de processos de cobrança antes que você tenha feito o contrário.
author: ShivamPandey-msft
ms.date: 11/06/2019
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom:
- "14151"
- intro-internal
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2019-11-06
ms.dyn365.ops.version: AX 10.0.8
ms.openlocfilehash: 54655d2b1cfb4b11f32842d4c3cff2f4d8e97ef5
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8856789"
---
# <a name="customer-payment-insights-preview"></a>Insights de pagamento de cliente (versão preliminar)

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Este artigo descreve o recurso de insights de pagamento que ajuda a melhorar a compreensão das práticas de pagamento típicas de clientes individuais. O recurso pode ajudá-lo a identificar as circunstâncias que justificam o início de processos de cobrança antes que você tenha feito o contrário. 

## <a name="overview"></a>Visão Geral

Pode ser difícil prever quando os clientes pagarão suas faturas. A falta de insight resulta em previsões de fluxo de caixa menos precisas, processos de cobrança que começam muito tarde e ordens liberadas para clientes que podem não cumprir seus pagamentos. Insights de pagamento de cliente (versão preliminar) ajudam as organizações a prever quando uma fatura de cliente será paga. Essas informações podem ajudar as organizações a criar estratégias de cobranças que aumentem a probabilidade de serem pagas no prazo. 

## <a name="predictions"></a>Previsões

As previsões de pagamento permitirão que as organizações melhorem seus processos empresariais ajudando-as a identificar facilmente as faturas que provavelmente serão pagas com atraso e a tomar as medidas apropriadas que aumentem suas chances de serem pagas no prazo.

Usando um modelo de aprendizado de máquina, que aproveita as faturas históricas, os pagamentos e os dados do cliente, o Insights de pagamento de cliente (versão prévia) prevê com maior precisão quando um cliente pagará uma fatura pendente.

Para cada fatura em aberto, o Insights de pagamento de cliente (versão preliminar) pode prever três probabilidades de pagamento:

-   Probabilidade de o pagamento ser feito no prazo 
-   Probabilidade de o pagamento ser feito com atraso
-   Probabilidade de o pagamento ser feito com muito atraso

Insights de pagamento de cliente (versão preliminar) também fornece uma exibição agregada dos pagamentos esperados, o que pode ajudar as organizações a compreender o valor total do pagamento que podem esperar de um cliente em um dos três buckets, No prazo, Atrasado e Muito atrasado.

[![Exibição agregada de previsões de pagamento.](./media/graphic-payment-reports.png)](./media/graphic-payment-reports.png)

Além disso, cada fatura obtém uma probabilidade de pagamento no prazo. Se a probabilidade de pagamento no prazo for inferior a 50%, as faturas serão marcadas com um círculo vermelho para indicar que essas faturas podem exigir atenção da cobrança. 

[![Lista de probabilidades de pagamento.](./media/customer-pymnt-probability-list.png)](./media/customer-pymnt-probability-list.png)

O Insights de pagamento de cliente (versão prévia) também oferece informações contextuais para explicar a previsão, como os principais fatores que influenciaram as previsões, o estado atual dos negócios com o cliente e os detalhes sobre o comportamento histórico de pagamento do cliente. Em muitas empresas, o processo de cobrança tem sido uma atividade reativa; o processo de cobrança não começa até a fatura ficar vencida. 

Com o Insights de pagamento de cliente (versão prévia), as organizações podem ser mais proativas sobre as cobranças. Elas não precisam mais esperar que as transações fiquem vencidas para iniciar o processo de cobrança. Em vez disso, podem usar o recurso de previsão de pagamento para determinar se a cobrança proativa aumentará a probabilidade de o pagamento ser feito no prazo. A previsão de pagamento também oferece às empresas as informações necessárias para justificar o início antecipado do processo de cobrança.

## <a name="methodology"></a>Metodologia

O desenvolvimento e a implantação de uma solução de IA são difíceis. É necessário ter uma equipe de cientistas de dados, especialistas no assunto e engenheiros trabalhando por um período extenso para formular, desenvolver, implantar e manter uma solução útil de IA. Estamos facilitando a implantação e o uso de soluções de IA no Finance. Estamos pré-embalando soluções de IA no Finance criadas com base no Microsoft AI Builder. Um usuário final, com um único clique de botão, pode implantar a solução de IA e começar a aproveitar os benefícios das previsões inteligentes. Se uma organização não estiver satisfeita com a precisão das previsões, um usuário avançado, novamente com um único clique, pode entrar na experiência de extensão do AI builder e então marcar ou desmarcar os campos usados para gerar previsões. Quando prontas, elas poderão treinar e publicar as alterações, e o modelo recém-treinado será automaticamente escolhido para previsões no Finance.

## <a name="how-to-get-customer-payment-insights-preview"></a>Como obter o Insights de pagamento de cliente (versão prévia)

Envie um email para [Insights de pagamento de cliente (versão preliminar)](mailto:fiap@microsoft.com) se estiver interessado em experimentar o Insights de pagamento de cliente (versão preliminar).

## <a name="privacy-notice"></a>Aviso de Privacidade

Versões preliminares (1) podem utilizar menos medidas de privacidade e segurança que o serviço do Dynamics 365 Finance e de Operations, (2) não estão incluídas no contrato de nível de serviço desse serviço, (3) não devem ser usadas para processar dados pessoais ou outros dados sujeitos a requisitos de conformidade legais ou regulatórios e (4) têm suporte limitado.




[!INCLUDE[footer-include](../../includes/footer-banner.md)]
