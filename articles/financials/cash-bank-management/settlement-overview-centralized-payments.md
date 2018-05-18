---
title: "Visão geral da liquidação para pagamentos centralizados"
description: "As organizações que incluem várias entidades legais podem criar e gerenciar pagamentos usando uma entidade legal que trate todos os pagamentos. Isso elimina a necessidade de inserir a mesma transação em várias entidades legais e poupa tempo ao simplificar o processo de proposta de pagamento, o processo de liquidação, a edição de transações abertas e a edição de transações fechadas para pagamentos centralizados."
author: abruer
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CustOpenTrans
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 222414
ms.assetid: 610f6858-0f37-4d0f-8c68-bab5a971ef4a
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: b76b141531acfc2d1d7553a3e7a13f165373921b
ms.contentlocale: pt-br
ms.lasthandoff: 11/03/2017

---

# <a name="settlement-overview-for-centralized-payments"></a>Visão geral da liquidação para pagamentos centralizados

[!include [banner](../includes/banner.md)]

As organizações que incluem várias entidades legais podem criar e gerenciar pagamentos usando uma entidade legal que trate todos os pagamentos. Isso elimina a necessidade de inserir a mesma transação em várias entidades legais e poupa tempo ao simplificar o processo de proposta de pagamento, o processo de liquidação, a edição de transações abertas e a edição de transações fechadas para pagamentos centralizados. 

Quando o pagamento de um cliente ou fornecedor é inserido em uma entidade legal e liquidado com uma fatura inserida em outra entidade legal, as transações aplicáveis de liquidação, a vencer e vencidas são geradas automaticamente para cada entidade legal. Um registro de liquidação é criado para cada combinação de nota fiscal e pagamento na transação. Cada registro de liquidação é atribuído um novo número de comprovante, que é baseado na série de sequência numérica do comprovante de pagamento especificado na página **Parâmetros de contas a receber** para clientes e na página **Parâmetros de contas a pagar** para fornecedores. 

Se outros registros adicionais de liquidação forem gerados para descontos à vista, reavaliações de moedas estrangeiras, diferenças mínimas, pagamentos a maior e a menor, eles receberão a data mais recente da transação de pagamento ou fatura. Se a liquidação ocorrer após o lançamento do pagamento, os registros de liquidação usarão a data de lançamento da liquidação especificada na página **Liquidar transações abertas**.
Tipos de lançamento, tipos de transação e descrições padrão
----------------------------------------------------------

Transações de comprovante de liquidação intercompanhia usam o tipo de postagem intercompanhia de pagamento, o pagamento intercompanhia de cliente, e os tipos de transação de pagamento de fornecedor intercompanhia. Você pode configurar informações para o tipo de transação na página **Descrições padrão**. 

Os tipos de transação a seguir estão disponíveis para uso em liquidações de uma única empresa e entre empresas:

-   Liquidação
-   Desconto à vista
-   Reavaliações da moeda estrangeira (incluem reavaliações de moeda estrangeira realizadas e não realizadas)
-   Diferença mínima
-   Pagamento a maior/a menor

Também é possível definir as descrições padrão para comprovantes de liquidação intercompanhia.

<a name="currency-exchange-gains-or-losses"></a>Lucros ou perdas de câmbio
---------------------------------

A taxa de câmbio usada para transações de cliente ou de fornecedor é armazenada com a transação. Os lucros ou as perdas realizados para taxas de câmbio são lançadas para a entidade legal da fatura ou entidade legal de pagamento, dependendo da opção selecionada para o campo **Lançar ganho ou perda de câmbio de moeda** na página **Contabilidade intercompanhia** da entidade legal de pagamento. Os exemplos a seguir usam estas moedas:
-   Moeda contábil do pagamento: EUR
-   Moeda contábil da fatura: USD
-   Moeda da transação de pagamento: DKK
-   Moeda da transação de fatura: CAD

#### <a name="currency-calculations"></a>Cálculos de moeda

Ao liquidar uma fatura inserida em uma entidade legal com um pagamento inserido em outra, a moeda da transação do pagamento (DKK) é convertida em três etapas:
1.  Convertida na moeda contábil do pagamento (EUR), usando as taxas de câmbio da entidade legal do pagamento.
2.  Convertida à moeda contábil da fatura (USD).
3.  Convertida na moeda da transação da fatura (CAD), usando as taxas de câmbio da entidade legal da fatura.

O processo de conversão usa as taxas de câmbio em vigor na data do pagamento. Se o valor do pagamento resultante na moeda da transação da nota fiscal (CAD) for igual ao valor da nota fiscal (CAD), a nota será  considerada paga por completo. 

Quando a página **Liquidar transações abertas** é aberta de um diário de pagamentos no qual o valor do pagamento não foi inserido, o valor a ser liquidado será calculado com base nas notas fiscais selecionadas para liquidação na página **Liquidar transações abertas**. O valor a liquidar é convertido em três etapas:
1.  Convertida para a moeda contábil da fatura (USD), usando as taxas de câmbio da entidade legal da fatura para a data de pagamento.
2.  Convertida para a moeda contábil do pagamento (EUR), usando as taxas de câmbio da entidade legal da fatura para a data de pagamento.
3.  Convertido na moeda da transação do pagamento (DKK).

O valor do pagamento resultante será transferido para a linha do diário de pagamentos quando você fechar a página **Liquidar transações abertas**.

#### <a name="posting-for-gain-or-loss-because-of-different-accounting-currencies"></a>Lançando para lucro ou perda devido a moedas contábeis diferentes

Se houver lucro ou perda cambial, o lucro ou a perda será lançada na entidade legal especificada para o campo **Ganho ou perda de câmbio de lançamentos** na página **Contabilização intercompanhia** para a entidade legal de pagamento. O valor de lucro ou perda é convertido para a moeda contábil da entidade legal onde os ganhos ou perdas serão lançados, usando a taxa de câmbio definida para essa entidade legal.

<a name="cash-discounts"></a>Descontos à vista
--------------

Os descontos à vista gerados durante o processo de liquidação entre empresas são lançados na entidade legal da fatura ou do pagamento, dependendo da opção selecionada no campo **Lançar desconto à vista**, na página **Contabilidade intercompanhia**, para a entidade legal do pagamento. Uma transação de liquidação correspondente é gerada na entidade legal da fatura.

<a name="overpayments-and-underpayments"></a>Pagamentos a maior e a menor
------------------------------

As tolerâncias de pagamento a maior, a menor e de diferença mínima são determinadas com base na entidade legal do pagamento para pagamentos a maior e na entidade legal de faturas para pagamentos a menor. A conta de lançamento usada é determinada pela configuração no campo **Administração do desconto à vista** na página **Parâmetros de contas a receber** para clientes, e no campo **Administração do desconto à vista** na página **Parâmetros de contas a pagar** para fornecedores.

-   Se a configuração de administração do desconto à vista for Específica, ou se a configuração é Inespecífica e o desconto à vista aplicável é postado em uma entidade legal diferente do pagamento extra, a conta automática para desconto à vista de cliente, desconto à vista de fornecedor, ou diferença mínima em moeda da contabilidade é usado. Você pode especificar essas contas na página **Para transações automáticas**.
-   Se a configuração de administração do desconto à vista for Inespecífico e o desconto for lançado na mesma entidade legal do pagamento a maior (a entidade legal do pagamento e da fatura são a mesma), a conta de desconto à vista será ajustada. Por exemplo, se uma nota fiscal para 100,00 com um desconto à vista de 3,00 for liquidada com um pagamento de 98,00, a conta de desconto à vista será ajustada em 1,00. O valor do desconto líquido é de 2,00.
-   Se a configuração de administração do desconto à vista for Inespecífico, o desconto à vista for lançado na mesma entidade legal do pagamento a maior e o pagamento a maior ou a menor for liquidado com várias notas fiscais com descontos à vista, a conta de desconto à vista para a última nota fiscal será ajustada.

Se a seleção de administração do desconto à vista for Inespecífico, as regras de liquidação de pagamento não específicas só serão aplicadas nestas situações:
-   Há um pagamento a maior.
-   O pagamento a maior é liquidado com uma ou mais notas fiscais que têm um desconto à vista.
-   O desconto à vista é lançado na mesma entidade legal que o pagamento a maior.

Em todas as outras situações, os pagamentos a maior ou a menor serão lançados a automática para o desconto à vista do cliente, o desconto à vista do fornecedor, a diferença de centavos contábil na moeda.

## <a name="sales-tax"></a>Imposto
Transações de imposto na entidade legal onde elas foram lançadas originalmente. 

Se o imposto foi lançado para um pagamento antecipado, a liquidação entre empresas estorna o imposto que incidem sobre o pagamento antecipado na entidade legal do pagamento antecipado. Os impostos sobre a entidade legal da fatura continuam incidindo sobre a entidade legal da fatura.

## <a name="financial-dimensions"></a>Dimensões financeiras
Para pagamentos de cliente, as transações a vencer e vencidas na entidade legal do pagamento usam as dimensões financeiras que são especificadas para a conta resumo de contas a receber do pagamento que está sendo liquidado. Na entidade legal da fatura, as transações a vencer e vencidas usam as dimensões financeiras especificadas para a conta resumo de Contas a receber da fatura que estiver sendo liquidada. 

Para pagamentos de fornecedores, as transações a vencer e vencidas na entidade legal do pagamento usam as dimensões financeiras que são especificadas para a conta resumo de contas a pagar do pagamento que está sendo liquidado. Na entidade legal da fatura, as transações a vencer e vencidas usam as dimensões financeiras especificadas para a conta resumo de Contas a pagar da fatura que estiver sendo liquidada.

## <a name="withholding-tax"></a>Imposto retido na fonte
A conta de fornecedor associada à fatura é usada para determinar se o imposto retido na fonte deve ser calculado. Se ele se aplicar, será calculado na entidade legal que associada à fatura. Se a entidade legal usa moedas diferentes, a taxa de câmbio da entidade legal associadas à fatura é usada.






