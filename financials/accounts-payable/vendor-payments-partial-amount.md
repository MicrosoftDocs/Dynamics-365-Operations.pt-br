---
title: Pagamentos de fornecedor de uma quantidade parcial
description: "Algumas vezes, você pode fazer um pagamento para um fornecedor que seja menor do que o valor de uma fatura. Este artigo descreve as diversas opções para controlar essa situação. As opções disponíveis dependerão dos seus requisitos empresariais e da sua configuração."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: LedgerJournalTransVendPaym, VendOpenTrans
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 14321
ms.assetid: 9a17075e-5325-4d55-a1e5-1791b8c460a0
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 2cb439e871d57f74c296697cfc42705fb0121bb7
ms.openlocfilehash: 4d243e6a9a68b69a6b32748344fc606ff3f2d965
ms.lasthandoff: 03/31/2017


---

# <a name="vendor-payments-for-a-partial-amount"></a>Pagamentos de fornecedor de uma quantidade parcial

Algumas vezes, você pode fazer um pagamento para um fornecedor que seja menor do que o valor de uma fatura. Este artigo descreve as diversas opções para controlar essa situação. As opções disponíveis dependerão dos seus requisitos empresariais e da sua configuração. 

<a name="cash-discount-amounts"></a>Valores de desconto à vista
---------------------

Um fornecedor poderá oferecer um desconto à vista quando você pagar uma fatura antes da data de vencimento. Por exemplo, você insere uma fatura de 100,00 que especifica um desconto à vista de 2% caso a fatura seja paga em 10 dias. As condições da data de vencimento serão de 30 dias. Se uma proposta de pagamento usa o desconto à vista como um critério quando uma nota fiscal, e se a proposta foi executada até a data de desconto à vista, a nota é selecionada para o pagamento, o pagamento é criada para 98.00. Um desconto à vista pode ser obtido para um único pagamento criada manualmente.

## <a name="partial-payments-with-cash-discounts"></a>Pagamentos parciais com descontos à vista
Quando você faz um pagamento parcial, talvez planeje fazer um pagamento parcial adicional para liquidar completamente a fatura. Para obter um desconto à vista para um pagamento parcial, você deve definir Sim ** calcular descontos à vista para pagamentos parciais ** padrão ** ** ** parâmetros de contas a pagar ** na página. 

Por exemplo, você recebe um desconto à vista de 2% caso a fatura seja paga em até 10 dias após a emissão. Uma fatura é lançada para 100,00. Se você fizer um pagamento de 49.00 em 10 dias, você insere um débito de 49.00 em um diário de pagamento. Quando você liquida pagamento parcial ** transações abertas de acordo ** na página, será exibido 1.00 ** ** ** valor de desconto à vista levar ** no campo. 

> [!NOTE] 
> Se você inserir o pagamento parcial e deixar o valor da nota fiscal total ** valor no acordo, ** ** campo valor do desconto à vista levar ** o campo é recalculado automaticamente quando você lança as transações.

## <a name="credit-notes-with-cash-discounts"></a>Notas de crédito com descontos à vista
Você poderia devolver alguns dos itens em uma fatura e receberia uma nota de crédito. Se um desconto à vista tiver sido retirado da fatura original, você poderá subtrair o valor do desconto e receber um reembolso do valor correto. Se ** calcular descontos à vista para notas de crédito ** a opção estiver definida ** Sim ** ** parâmetros de contas a pagar ** na página, o desconto é calculado automaticamente a nota de crédito. 

Por exemplo, você recebe um desconto à vista de 2% caso a fatura seja paga em até 10 dias após a emissão. Uma fatura de 100,00 é lançada. Se você devolver mercadorias e recebe uma nota de crédito, insira a nota de crédito para o valor total da nota fiscal original, 100.00, com o desconto à vista de 2 por cento definido também em memorando de crédito.  Quando você exibe a nota de crédito ** transações de acordo ** na página, ** 98.00 ** o valor aparece ** o comprometimento ** campo, e ** - 2.00 ** ** aparece em valores com desconto à vista ** campo. O valor do desconto é lançado em uma conta de desconto à vista.

## <a name="overpaymentunderpayment-amounts"></a>Valores de pagamento a maior/a menor
Você pode fazer um pagamento parcial em que o valor a ser liquidado é muito pequeno. Por exemplo, a fatura de fornecedor é de 1.000,00 e você paga 999,90. Se o valor restante for menor do que o valor especificado para pagamentos a maior ou para pagamentos a menor na página **Parâmetros de contas a pagar**, a diferença será automaticamente lançada em uma conta conta contábil de pagamento a maior/a menor.


