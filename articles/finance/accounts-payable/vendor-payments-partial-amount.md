---
title: Pagamentos de fornecedor de uma quantidade parcial
description: Algumas vezes, você pode fazer um pagamento para um fornecedor que seja menor do que o valor de uma fatura. Este artigo descreve as diversas opções para controlar essa situação.
author: abruer
manager: AnnBe
ms.date: 08/22/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerJournalTransVendPaym, VendOpenTrans
audience: Application User
ms.reviewer: roschlom
ms.custom: 14321
ms.assetid: 9a17075e-5325-4d55-a1e5-1791b8c460a0
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 00a3cc8480b4d171c1f2b3cda4e8707893c6a05b
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4991183"
---
# <a name="vendor-payments-for-a-partial-amount"></a>Pagamentos de fornecedor de um valor parcial

[!include [banner](../includes/banner.md)]

Algumas vezes, você pode fazer um pagamento para um fornecedor que seja menor do que o valor de uma fatura. Este artigo descreve as diversas opções para controlar essa situação. As opções disponíveis dependerão dos seus requisitos empresariais e da sua configuração. 

<a name="cash-discount-amounts"></a>Valores de desconto à vista
---------------------

Um fornecedor poderá oferecer um desconto à vista quando você pagar uma fatura antes da data de vencimento. Por exemplo, você insere uma fatura de 100,00 que especifica um desconto à vista de 2% caso a fatura seja paga em 10 dias. As condições da data de vencimento serão de 30 dias. Se uma proposta de pagamento usa o desconto de caixa como critério para selecionar uma fatura e se a proposta é executada na data de desconto ou antes dela, a fatura é selecionada para pagamento e o pagamento é criado por 98,00. Um desconto de dinheiro também pode ser tomado para um pagamento único que foi criado manualmente.

## <a name="partial-payments-with-cash-discounts"></a>Pagamentos parciais com descontos à vista
Quando você faz um pagamento parcial, talvez planeje fazer um pagamento parcial adicional para liquidar completamente a fatura. Para obter um desconto à vista para um pagamento parcial, você deve definir a opção **Calcular descontos à vista para pagamentos parciais** como **Sim** na página **Parâmetros de contas a pagar**. 

Por exemplo, você recebe um desconto à vista de 2% caso a fatura seja paga em até 10 dias após a emissão. Uma fatura é lançada para 100,00. Se você fizer um pagamento de 49,00 dentro de 10 dias, vai inserir um débito de 49,00 em um diário de pagamento. Quando você liquida o pagamento parcial na página **Liquidar transações abertas**, **1,00** aparecerá no campo **Valor do desconto à vista a ser obtido**. 

> [!NOTE] 
> Se você inserir um pagamento parcial e deixar o valor total da fatura no campo **Valor para liquidar**, o campo **Valor do desconto à vista** a ser obtido será automaticamente recalculado quando as transações forem lançadas.

## <a name="credit-notes-with-cash-discounts"></a>Notas de crédito com descontos à vista
Você poderia devolver alguns dos itens em uma fatura e receberia uma nota de crédito. Se um desconto à vista tiver sido retirado da fatura original, você poderá subtrair o valor do desconto e receber um reembolso do valor correto. Se a opção **Calcular descontos à vista para notas de crédito** estiver definida como **Sim** na página **Parâmetros de contas a pagar**, o desconto será calculado automaticamente para a nota de crédito. 

Por exemplo, você recebe um desconto à vista de 2% caso a fatura seja paga em até 10 dias após a emissão. Uma fatura de 100,00 é lançada. Se você devolver a mercadoria e receber uma nota de crédito, poderá inserir a nota de crédito para o valor total da fatura original, 100,00, juntamente com o desconto de 2% que também é definido na nota de crédito.  Quando você exibe a nota de crédito na página **Liquidar transações**,**98,00** aparece no campo **Valor para liquidar** e **-2,00** aparece no campo **Valor do desconto à vista**. O valor do desconto é lançado em uma conta de desconto à vista.

## <a name="overpaymentunderpayment-amounts"></a>Valores de pagamento a maior/a menor
Você pode fazer um pagamento parcial em que o valor a ser liquidado é muito pequeno. Por exemplo, a fatura de fornecedor é de 1.000,00 e você paga 999,90. Se o valor restante for menor do que o valor especificado para pagamentos a maior ou para pagamentos a menor na página **Parâmetros de contas a pagar**, a diferença será automaticamente lançada em uma conta conta contábil de pagamento a maior/a menor.


Para saber mais, consulte [Visão geral de pagamentos a fornecedores](../cash-bank-management/tasks/vendor-payment-overview.md).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]