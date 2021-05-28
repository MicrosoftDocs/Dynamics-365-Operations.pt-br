---
title: Liquidar um pagamento parcial de cliente com vários períodos de desconto
description: Este artigo mostra como os pagamentos parciais de cliente são liquidados quando há vários períodos de desconto.
author: ShivamPandey-msft
ms.date: 08/22/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CustOpenTrans, LedgerJournalTransCustPaym
audience: Application User
ms.reviewer: roschlom
ms.custom: 14471
ms.assetid: b633a7c4-c18d-42e7-91cc-adcdc8a3ba98
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 21600c0815da99314dcbb8f123449c2ae93a3c1a
ms.sourcegitcommit: cabd991fda2bfcabb55db84c225b24a7bb061631
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/12/2021
ms.locfileid: "6027471"
---
# <a name="settle-a-partial-customer-payment-that-has-multiple-discount-periods"></a>Liquidar um pagamento parcial de cliente com vários períodos de desconto

[!include [banner](../includes/banner.md)]

Este artigo mostra como os pagamentos parciais de cliente são liquidados quando há vários períodos de desconto.

A Fabrikam oferece ao cliente 4031 dois períodos de desconto para pagamento à vista. O cliente receberá um desconto à vista de 2% se a fatura for paga em cinco dias, e um desconto à vista de 1% se a fatura for paga em 14 dias. A Fabrikam também oferece descontos à vista para pagamentos parciais. Os parâmetros de pagamento estão localizados na página **Parâmetros de contas a receber**.

## <a name="invoice"></a>Fatura
Em 25 de junho, Amanda insere e lança uma fatura de 1.000,00 para o cliente 4031. Quando Arnie revisa os descontos em dinheiro para esta fatura, vê que o cliente 4031 receberá um desconto de 20,00 se a fatura for paga até 30 de junho. Se a fatura for paga até 9 de julho, o cliente recebe um desconto de 10,00.

| Data do desconto à vista | Valor de desconto à vista | Valor na moeda da transação |
|--------------------|----------------------|--------------------------------|
| 30/6/2015          | 20,00                | 980,00                         |
| 9/7/2015           | 10.00                | 990,00                         |
| 25/7/2015          | 0,00                 | 1.000,00                       |

Alberto pode exibir esta transação na página **Transações do cliente**.

| Comprovante   | Tipo de transação | Data      | Fatura | Valor em débito na moeda da transação | Valor em crédito na moeda da transação | Saldo  | Moeda |
|-----------|------------------|-----------|---------|--------------------------------------|---------------------------------------|----------|----------|
| FTI-10030 | Fatura          | 25/6/2015 | 10030   | 1.000,00                             |                                       | 1.000,00 | USD      |

## <a name="partial-payment-before-the-cash-discount-date"></a>Pagamento parcial antes da data de desconto à vista
Em 28 de junho, o Cliente 4031 faz um pagamento parcial de 294,00. Como 28 de junho está no período de desconto à vista, o cliente obtém um desconto de 6,00. Na página **Liquidar**, o valor de **Valor do desconto à vista** é 20,00 e o valor de **Valor do desconto a ser obtido** é 6,00.

| Marcar     | Usar desconto à vista | Comprovante   | Conta | Data      | Data de conclusão  | Fatura | Valor na moeda da transação | Moeda | Valor para liquidar |
|----------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------|----------|------------------|
| Selecionada | Normal            | FTI-10030 | 4031    | 25/6/2015 | 25/7/2015 | 10030   | 1.000,00                       | USD      | 294,00           |

As informações do desconto aparecem na parte inferior da página **Liquidar transações abertas**. Se você não alterar o valor da opção **Valor para liquidar** para **294,00**, os valores da opção **Valor de desconto à vista** que aparecem serão diferentes. No entanto, 6,00 serão obtidos como o desconto à vista quando o pagamento for lançado, pois a liquidação é ajustada automaticamente ao **Valor para liquidar** para você.

| &nbsp;                       | &nbsp;    |
|------------------------------|-----------|
| Data do desconto à vista           | 30/6/2015 |
| Valor de desconto à vista         | 20,00     |
| Usar desconto à vista            | Normal    |
| Desconto à vista obtido          | 0,00      |
| Valor do desconto à vista a ser obtido | 6,00      |

Após Arnie lançar o pagamento, o saldo da fatura será de 700,00.

## <a name="partial-payment-before-the-second-cash-discount-date"></a>Pagamento parcial antes da segunda data do desconto à vista
Em 8 de julho, o cliente paga o restante do valor da fatura. Um desconto de 7,00 (1%) é obtido, pois o pagamento foi realizado no segundo período de desconto à vista.

| Marcar     | Usar desconto à vista | Comprovante   | Conta | Data      | Data de conclusão  | Fatura | Valor em débito na moeda da transação | Valor em crédito na moeda da transação | Moeda | Valor para liquidar |
|----------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------------|---------------------------------------|----------|------------------|
| Selecionada | Normal            | FTI-10030 | 4031    | 25/6/2015 | 25/7/2015 | 10030   | 700.00                               |                                       | USD      | 693.00           |

As informações do desconto aparecem na parte inferior da página **Liquidar transações abertas**.

| &nbsp;                       | &nbsp;    |
|------------------------------|-----------|
| Data do desconto à vista           | 09/07/2015 |
| Valor de desconto à vista         | 30,00     |
| Usar desconto à vista            | Normal    |
| Desconto à vista obtido          | 6,00      |
| Valor do desconto à vista a ser obtido | 7:00      |

O saldo da fatura agora é de 0,00. Alberto exibe as informações na página **Transações do cliente**.

| Comprovante    | Tipo de transação | Data      | Fatura | Valor em débito na moeda da transação | Valor em crédito na moeda da transação | Saldo | Moeda |
|------------|------------------|-----------|---------|--------------------------------------|---------------------------------------|---------|----------|
| FTI-10030  | Fatura          | 25/6/2015 | 10030   | 1.000,00                             |                                       | 0,00    | USD      |
| ARP-10030  |  Pagamento         | 28/6/2015 |         |                                      | 294,00                                | 0,00    | USD      |
| DISC-10030 |  Desconto à vista   | 28/6/2015 |         |                                      | 6,00                                  | 0,00    | USD      |
| ARP-10031  |  Pagamento         | 8/7/2015  |         |                                      | 693.00                                | 0,00    | USD      |
| DISC-1031  |  Desconto à vista   | 8/7/2015  |         |                                      | 7:00                                  | 0,00    | USD      |







[!INCLUDE[footer-include](../../includes/footer-banner.md)]