---
title: Liquidar um pagamento parcial de cliente com descontos em notas de crédito
description: Este artigo mostra um cenário onde um desconto à vista é aplicado a uma nota de crédito quando a fatura original também tinha um desconto à vista.
author: ShivamPandey-msft
ms.date: 08/22/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CustOpenTrans, LedgerJournalTransCustPaym
audience: Application User
ms.reviewer: twheeloc
ms.custom: 14564
ms.assetid: d9984cef-ddcf-46bd-816d-c01b8cc5cf48
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 44f64b9b9cd4fa65d17ba30fb87a688411becd5a
ms.sourcegitcommit: cf6b764824bd1cf2c0dde6d37ddd0a7abab87ff0
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/16/2022
ms.locfileid: "9780428"
---
# <a name="settle-a-partial-customer-payment-that-has-discounts-on-credit-notes"></a>Liquidar um pagamento parcial de cliente com descontos em notas de crédito

[!include [banner](../includes/banner.md)]

Este artigo mostra um cenário onde um desconto à vista é aplicado a uma nota de crédito quando a fatura original também tinha um desconto à vista. 

A Fabrikam permite que os clientes tenham descontos à vista em pagamentos parciais e também em notas de crédito (memorandos de crédito). Um desconto à vista pode ser obtido em uma nota de crédito quando a nota de crédito for emitida para uma fatura que o cliente obteve em um desconto à vista. Em vez de fornecer um crédito para o valor total, você pode creditar o saldo do cliente para um valor que exclui a porcentagem de desconto à vista que o cliente obteve. Os parâmetros de pagamento estão localizados na página **Parâmetros de contas a receber**.

## <a name="invoice-and-credit-note"></a>Fatura e nota de crédito
O cliente 4035 possui uma fatura de 1.000,00 e uma nota de crédito de 100,00. Cada documento terá um desconto de 1%, se for pago em 14 dias. Arnie pode exibir as informações na página **Transações do cliente**.

| Comprovante    | Tipo de transação | Data      | Fatura  | Valor em débito na moeda da transação | Valor em crédito na moeda da transação | Saldo  | Moeda |
|------------|------------------|-----------|----------|--------------------------------------|---------------------------------------|----------|----------|
| FTI-10050  | Fatura          | 28/6/2020 | 10050    | 1.000.00                             |                                       | 1.000.00 | USD      |
| CCRN-10050 | Nota de crédito      | 28/6/2020 | CR-10050 |                                      | 100.00                                | -100,00  | USD      |

## <a name="settle-a-credit-note-with-an-invoice"></a>Liquidar uma nota de crédito com uma fatura
Na página **Transações do cliente**, Arnie abre a página **Liquidar transações**. Arnie pode usar a página **Liquidar transações** para liquidar a fatura e a nota de crédito. Como parte do processo de liquidação, Arnie visualiza as datas e os valores de desconto em dinheiro. Arnie marca os dois documentos e clica em **Postar** para liquidar as transações. Há um desconto de -1,00 na nota de crédito, pois a Fabrikam permite descontos em notas de crédito.

| Marcar     | Usar desconto à vista | Comprovante    | Conta | Data      | Data de conclusão  | Fatura  | Valor na moeda da transação | Moeda | Valor para liquidar |
|----------|-------------------|------------|---------|-----------|-----------|----------|--------------------------------|----------|------------------|
| Selecionados | Normal            | FTI-10050  | 4035    | 28/6/2020 | 28/7/2020 | 10050    | 1.000.00                       | USD      | 990.00           |
| Selecionados | Normal            | CCRN-10050 | 4035    | 28/6/2020 | 28/7/2020 | CR-10050 | -100,00                        | USD      | -99,00           |

As informações do desconto aparecem na parte inferior da página **Liquidar transações**.

- **Data do desconto à vista**: 12/07/2020 
- **Valor de desconto à vista**: -1,00     
- **Usar desconto à vista**: Normal    
- **Desconto à vista obtido**: 0,00      
- **Valor do desconto à vista a ser obtido**: -1,00     

A liquidação será de 100,00 e incluirá um pagamento de 99,00 e um desconto de 1,00.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]
