---
title: Informações de pagamento do cliente (visualização)
description: Este tópico descreve como as informações de pagamento do cliente podem ajudar a prever quando uma fatura será paga e ajudar as organizações a criar estratégias de otimização que melhorem a probabilidade de serem pagas no prazo.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 07/17/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: shylaw
ms.search.scope: ''
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2018-04-02
ms.dyn365.ops.version: AX 8.0.0
ms.openlocfilehash: 9e722db6302d7ef51c01601cde245d4f4a333eba
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1566225"
---
# <a name="customer-payment-insights-preview"></a>Informações de pagamento do cliente (visualização)

[!include[banner](../includes/banner.md)]

> [!IMPORTANT]
> Esse recurso faz parte de uma versão direcionada e está disponível somente para os usuários que optaram pela visualização privada. Esse recurso estará incluído em uma futura versão de disponibilidade geral.

# <a name="overview"></a>Visão Geral

As organizações geralmente acham difícil prever quando um cliente pagará suas faturas. Essa falta de informações pode resultar em previsões de fluxo de caixa imprecisas, em processos de cobrança ineficientes e na possibilidade de liberação de ordens para clientes que podem representar um risco de crédito. As informações de pagamento do cliente (visualização) usam o aprendizado de máquina para prever quando uma fatura será paga. Também fornecem estratégias de otimização que podem ser adaptadas para maximizar a probabilidade de os clientes pagarem no prazo.

## <a name="predictions"></a>Previsões

As previsões de pagamento permitem que as organizações aperfeiçoem seus processos de negócios, ajudando a:

-   Identificar facilmente as faturas com previsão de pagamento atrasado.
-   Tomar medidas apropriadas para melhorar as chances de ser pago no prazo.

As informações de pagamento do cliente (visualização) usam o aprendizado de máquina para prever quando uma fatura será paga. Usam dados históricos de faturas, pagamentos e clientes para criar um modelo de aprendizado de máquina que é usado para prever quando uma fatura será paga.

Para cada fatura em aberto, as informações de pagamento do cliente (visualização) preveem três probabilidades de pagamento:

-  Probabilidade de o pagamento ser feito no prazo (dentro da data de vencimento da fatura).
-  Probabilidade de o pagamento ser feito em até 30 dias após a data de vencimento da fatura.
-  Probabilidade de o pagamento ser feito além dos 30 dias após a data de vencimento da fatura.

A probabilidade de pagamentos pode ser visualizada na seção de previsão.

[![Previsões de pagamento](./media/Predictions-sm2.png)](./media/Predictions-sm2.png)

Também se atribui a cada fatura uma probabilidade de pagamento vencedora usando um dos três cenários de probabilidade de pagamento previstos que foram definidos acima. O cenário com maior probabilidade de pagamento é o cenário vencedor.


Por exemplo, vamos supor que a previsão mostre uma probabilidade de 71% de que uma determinada fatura seja paga no prazo, 13% de probabilidade de que ela seja paga em até 30 dias após a data de vencimento e 16% de probabilidade de que ela seja paga além dos 30 dias após a data de vencimento. Como a maior probabilidade mostra que a fatura estará no cenário em que o prazo é respeitado, a fatura será marcada com a probabilidade de ser paga a tempo.

[![Previsões de pagamento](./media/payment-predict.png)](./media/payment-predict.png)

## <a name="optimization-strategies"></a>Estratégias de otimização

Além das previsões de pagamento, as informações de pagamento do cliente (visualização) podem usar estratégias de otimização para aperfeiçoar as chances de receber pagamentos no prazo. Com isso, as organizações podem fazer a análise "E se", permitindo que os usuários ajustem os parâmetros da fatura e do cliente e depois comparem o efeito correspondente sobre a probabilidade de receber o pagamento das faturas no prazo.

Por exemplo, uma organização pode querer avaliar o efeito da atualização do desconto à vista nas faturas sobre a probabilidade de receber o pagamento no prazo. Quando as faturas são otimizadas para usar o novo desconto, os usuários podem rever o efeito da aplicação do desconto sobre a probabilidade de receber pagamentos para essas faturas a tempo. Se o custo de aplicar o desconto for mínimo em comparação ao benefício de cobrar o pagamento no prazo, a organização pode optar por aplicar o desconto selecionado a todas as futuras ordens em aberto.

> [!NOTE] 
> Atualmente, apenas o desconto está disponível como estratégia de otimização para informações de pagamento do cliente (visualização).

[![Previsões otimizadas](./media/optimized-pay.png)](./media/optimized-pay.png)

## <a name="how-to-get-customer-payment-insights-preview"></a>Como obter informações de pagamento do cliente (visualização)

Se estiver interessado em experimentar informações de pagamento do cliente (visualização), envie um e-mail [Equipe de visualização de informações financeiras](mailto:fiap@microsoft.com). 

## <a name="privacy-statement"></a>Política de Privacidade

As visualizações armazenam dados de clientes nos Estados Unidos. Além disso, as visualizações (1) podem utilizar menos medidas de privacidade e segurança que o serviço do Dynamics 365 for Finance and Operations, (2) não estão incluídas no contrato de nível de serviço desse serviço, (3) não devem ser usadas para processar dados pessoais ou outros dados sujeitos a requisitos de conformidade legais ou regulatórios e (4) têm suporte limitado.
