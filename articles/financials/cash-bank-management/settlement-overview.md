---
title: Visão geral da liquidação
description: Este artigo oferece informações gerais sobre o processo de liquidação. Ele descreve os tipos de transações que podem ser liquidadas, quando e como as transações podem ser liquidadas e os resultados do processo de liquidação.
author: kweekley
manager: AnnBe
ms.date: 12/06/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustOpenTrans, LedgerJournalTransCustPaym, LedgerJournalTransVendPaym, VendOpenTrans
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 14551
ms.assetid: 0968fa71-5984-415b-8689-759a0136d5d1
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2018-10-31
ms.dyn365.ops.version: 8.0999999999999996
ms.openlocfilehash: 9b82c6afa2812344ff8200e227ee8c5f2451584f
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2019
ms.locfileid: "338282"
---
# <a name="settlement-overview"></a>Visão geral da liquidação

[!include [banner](../includes/banner.md)]

Este artigo oferece informações gerais sobre o processo de liquidação. Ele descreve os tipos de transações que podem ser liquidadas, quando e como as transações podem ser liquidadas e os resultados do processo de liquidação.

Durante a liquidação, as transações de um documento são aplicadas a transações em outro documento para aumentar ou diminuir o saldo de cada documento. Por exemplo, um pagamento pode ser aplicado a uma fatura. Vários tipos de transação podem ser resolvidos, em momentos diferentes e através de vários métodos. A liquidação também pode fazer com que novas transações sejam geradas.

## <a name="what-transactions-can-be-settled"></a>Quais transações podem ser liquidadas
A liquidação dentro do Contas a pagar e do Contas a receber pode ocorrer entre quaisquer tipo de transação que afetarem o saldo do fornecedor ou o saldo do cliente, como faturas, pagamentos, memorandos de crédito e taxas. Qualquer tipo de transação pode ser liquidado com relação a qualquer outro tipo de transação. Por exemplo, você pode liquidar um pagamento de uma fatura, um memorando de crédito para uma fatura, uma fatura para uma fatura e um pagamento para um pagamento. Você pode liquidar pagamentos para uma transação na mesma entidade legal ou em uma entidade legal diferente. Em organizações que usam um módulo de pagamento centralizado, as [pagamentos centralizados](set-up-centralized-payments.md) podem ajudar a simplificar o processo de pagamento.

## <a name="when-to-settle-transactions"></a>Quando liquidar transações
As transações podem ser liquidadas no momento da entrada de pagamento. Por exemplo, quando você faz um pagamento para um fornecedor, normalmente você seleciona as faturas a serem pagas. Ao selecionar faturas, você as marca para liquidação contra o pagamento. Quando os auxiliares de pagamento do Contas a Receber registram um pagamento de cliente, eles podem marcar as faturas apropriadas para liquidação, com base nas informações incluídas no pagamento do cliente. A página **Transações de liquidação** é usada para marcar transações para liquidação. Esta página pode ser aberta a partir de qualquer fatura ou pagamento não lançado. Quando a transação é lançada, a liquidação também é lançada. As transações também podem ser liquidadas depois de serem lançadas. Você pode inserir e lançar um pagamento de cliente sem liquidá-lo em todas as faturas. No entanto, você pode ter que fazer primeiro a pesquisa, para garantir que o pagamento é liquidado na fatura correta. A página **Liquidar transações** pode ser aberta na página **Todos os clientes** ou **Todos os fornecedores** ou na página **Transações** de qualquer cliente ou fornecedor. Você também pode reservar pagamentos antecipados lançados para uma fatura marcando o pagamento de uma liquidação contra uma ordem de compra ou de venda. Neste caso, o pagamento ainda terá um saldo em aberto, mas não pode ser liquidado contra outra fatura. O pagamento será automaticamente compensado com a fatura criada a partir da ordem de compra ou da ordem do cliente.

## <a name="how-to-settle-transactions"></a>Como liquidar transações
As transações podem ser liquidadas manualmente, automaticamente, ou usando uma combinação dos métodos. A opção de um método de liquidação depende dos processos comerciais, que podem então ser implementado através da configuração da liquidação nos parâmetros de Contas a pagar e de Contas a receber. Você pode criar pagamentos de fornecedor e pagamentos de débito direto do cliente usando uma proposta de pagamento, que pode ser usada para selecionar faturas a serem pagas. A proposta de pagamento é iniciada manualmente, mas, em seguida, o Microsoft Dynamics 365 for Finance and Operations marca automaticamente as faturas selecionadas para liquidação quando os pagamentos são criados. Se os pagamentos forem criados manualmente, você pode usar a página **Transações de liquidação** para selecionar faturas para liquidação. Também é possível selecionar manualmente as faturas ou você pode usar a opção **Marcar por prioridade** para que as faturas sejam marcadas automaticamente para liquidação. A opção **Marcar por prioridade** fica disponível somente para Contas a receber. Para habilitar esta opção, use **Prioridade de liquidação** nos Parâmetros de contas a receber. Se um auxiliar de pagamento inserir um pagamento, mas não liquidar esse pagamento antes de lançá-lo, o pagamento poderá ser liquidado automaticamente. Você pode ativar a liquidação automática em Parâmetros de contas a receber e Parâmetros de contas a pagar. Quando você utiliza a liquidação automática, pode utilizar a ordem de liquidação predefinida ou pode definir a sua própria ordem de prioridade de liquidação em Parâmetros de contas a receber. Essa funcionalidade só estará disponível para Contas a receber.

## <a name="results-of-settlement"></a>Os resultados da liquidação
Quando as transações são liquidadas, o saldo pendente de cada transação é aumentado ou diminuído, conforme apropriado. Em um cenário típico, no qual uma fatura e um pagamento são liquidados, o status e um saldo de cada transação será atualizado de acordo com as regras a seguir:

-   Se o valor do pagamento for maior do que o valor da fatura, o saldo da fatura será reduzido a 0,00 e a fatura será fechada. O pagamento permanece aberto e o saldo é o valor pelo qual o pagamento excede o valor da fatura.
-   Se o valor do pagamento for menor do que o valor da fatura, o saldo do pagamento será reduzido a 0,00 e o pagamento será fechado. A fatura permanece aberta e o saldo é o valor pelo qual o pagamento fica a menor em relação à fatura.
-   Se o valor do pagamento for igual ao valor da fatura, o pagamento e a fatura serão fechados e o saldo dos dois será 0,00.

Se um pagamento [for menor do que o valor da fatura](../accounts-payable/vendor-payments-partial-amount.md) devido a um desconto à vista, baixa ou pagamento a menor, a fatura e o pagamento podem ainda ser fechados, dependendo da configuração dos parâmetros de Contas a pagar e dos parâmetros de Contas a receber. A liquidação também pode gerar transações. Por exemplo, a liquidação de uma fatura e de um pagamento pode gerar um desconto à vista, um ganho ou perda realizado, ajustes de impostos, baixas contábeis ou diferenças mínimas.


## <a name="additional-resources"></a>Recursos adicionais
- [Liquidar pendências](settle-remainder.md)

