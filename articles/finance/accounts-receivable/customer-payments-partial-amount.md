---
title: Pagamentos de cliente de uma quantidade parcial
description: Às vezes, os clientes fazem um pagamento inferior ao valor de uma fatura. Este artigo descreve as diversas opções para controlar essa situação. As opções disponíveis dependerão dos seus requisitos empresariais e da sua configuração.
author: ShivamPandey-msft
ms.date: 01/08/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CustPaymEntry
audience: Application User
ms.reviewer: roschlom
ms.custom: 13011
ms.assetid: 20423a2d-6997-4e1c-a596-a77016600071
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4f89b3d94fd16aa9cf27931d11fd8fff22048d40
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5824019"
---
# <a name="customer-payments-for-a-partial-amount"></a>Pagamentos de cliente de uma quantidade parcial

[!include [banner](../includes/banner.md)]

Às vezes, os clientes fazem um pagamento inferior ao valor de uma fatura. Este artigo descreve as diversas opções para controlar essa situação. As opções disponíveis dependerão dos seus requisitos empresariais e da sua configuração.

<a name="partial-payment-with-no-discount"></a>Pagamento parcial sem desconto
--------------------------------

Os clientes podem fazer um pagamento parcial porque eles simplesmente não têm o dinheiro suficiente para pagar o total da fatura ou porque há uma contestação sobre um item na fatura. Nessa situação, a fatura pode ser parcialmente liquidada com o pagamento. A fatura permanecerá aberta e mostrará um saldo.

## <a name="discount-amounts"></a>Valores do desconto
Você pode oferecer aos clientes um desconto à vista por pagarem uma fatura antes da data de vencimento. Por exemplo, você insere uma fatura de 100,00 que especifica um desconto à vista de 2% caso a fatura seja paga em 10 dias. As condições da data de vencimento serão de 30 dias. Se você recebe um pagamento de 98,00 em 10 dias, insere o pagamento de 98,00. Em seguida, quando a fatura for marcada para liquidação, o desconto à vista será automaticamente obtido.

## <a name="partial-payments-with-cash-discounts"></a>Pagamentos parciais com descontos à vista
Quando os clientes fazem um pagamento parcial, talvez planejem fazer um pagamento parcial adicional para liquidar completamente a fatura. Para obter um desconto à vista para um pagamento parcial, você deve definir a opção **Calcular descontos à vista para pagamentos parciais** como **Sim** na página **Parâmetros de contas a receber**. 

Por exemplo, você oferece um desconto à vista de 2% caso a fatura seja paga em até 10 dias após a emissão. Uma fatura é lançada para 100,00. Se você receber um pagamento de 49,00 dentro de 10 dias, insere um crédito de 49,00 em um diário de pagamento. Quando você liquida o pagamento parcial na página **Liquidar transações**, **1,00** aparecerá no campo **Valor do desconto à vista a ser obtido**. O valor do desconto é lançado em uma conta de desconto à vista. 

> [!NOTE] 
> Se você inserir um pagamento parcial e deixar o valor total da fatura no campo **Valor para liquidar**, o campo **Valor do desconto à vista** a ser obtido será automaticamente recalculado quando as transações forem lançadas.

## <a name="credit-notes-with-discounts"></a>Notas de crédito com descontos
Se os clientes devolverem alguns dos itens em uma fatura, você poderá emitir uma nota de crédito. Se um desconto à vista tiver sido obtido na fatura original, a nota de crédito para o cliente deverá ser líquida do desconto à vista obtido pelo cliente. Se a opção **Calcular descontos à vista para notas de crédito** estiver definida como **Sim** na página **Parâmetros de contas a receber**, o desconto será calculado automaticamente para a nota de crédito. 

Por exemplo, você ofereceu condições de pagamento que especificam um desconto à vista de 2% se a fatura for paga dentro de 10 dias desde a sua emissão. Uma fatura de 100,00 foi lançada e o cliente obteve o desconto à vista. Se o cliente devolver as mercadorias e você emitir uma nota de crédito, você pode inserir a nota de crédito para -100,00. Quando você exibe a nota de crédito na página **Liquidar transações abertas**, **98,00** aparece no campo **Valor para liquidar** e **-2,00** aparece no campo **Valor do desconto à vista**. O valor do desconto é lançado em uma conta de desconto à vista.

## <a name="overpaymentunderpayment-amounts"></a>Valores de pagamento a maior/a menor
Quando os clientes fizerem um pagamento, poderá haver um valor muito pequeno que ainda deverá ser liquidado. Por exemplo, você emite a fatura do cliente no valor de 1.000,00 e ele paga 999,90. Se o valor restante for menor do que o valor especificado para pagamentos a maior ou para pagamentos a menor na página **Parâmetros de contas a receber**, a diferença será automaticamente lançada em uma conta conta contábil de pagamento a maior/a menor.

## <a name="full-settlement"></a>Liquidação completa
Os clientes podem fazer um pagamento parcial onde o valor restante não será pago, mas é maior do que o valor de pagamento a menor especificado na página **Parâmetros de contas a pagar**. Se você quiser marcar a fatura como totalmente liquidada, poderá usar a opção **Liquidação total** na página **Liquidar transação**. (Você pode habilitar a funcionalidade completa de liquidação usando uma chave de configuração). Por exemplo, uma fatura é lançada para 1.000,00 e o cliente faz um pagamento de 990,00. Você concordou que o cliente não precisa pagar os 10,00 restantes. Depois de marcar a fatura para liquidação, você também poderá marcar **Liquidação total**. A fatura será considerada totalmente liquidada. A diferença de 10,00 é lançada em uma conta de desconto à vista, como um valor de desconto à vista adicional.


Para obter mais informações, consulte [Depositar pagamentos de cliente](tasks/deposit-customer-payments.md).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]