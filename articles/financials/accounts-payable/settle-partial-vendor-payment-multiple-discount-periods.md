---
title: Liquidar um pagamento parcial de fornecedor com vários períodos de desconto
description: Este artigo mostra um cenário em que vários pagamentos parciais são feitos para um fornecedor que oferece vários descontos à vista.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/22/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerJournalTransVendPaym, VendOpenTrans
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 14262
ms.assetid: af95c48a-afd1-476c-978d-e34995100be4
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c697d20bcbe6ab8f2bc38c03b181104db1f36838
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2019
ms.locfileid: "357947"
---
# <a name="settle-a-partial-vendor-payment-that-has-multiple-discount-periods"></a>Liquidar um pagamento parcial de fornecedor com vários períodos de desconto

[!include [banner](../includes/banner.md)]

Este artigo mostra um cenário em que vários pagamentos parciais são feitos para um fornecedor que oferece vários descontos à vista. 

O fornecedor 3054 oferece à Fabrikam um desconto à vista de 2 por cento se uma fatura for paga em cinco dias e um desconto à vista de 1 por cento se uma fatura for paga em 14 dias.

## <a name="invoice"></a>Fatura
Em 28 de junho, Amanda cria uma fatura de 1.000,00 para o fornecedor 3054. Alice pode exibir essa transação na página **Transações do fornecedor**.

| Comprovante   | Data      | Fatura | Valor em débito na moeda da transação | Valor em crédito na moeda da transação | Saldo   | Moeda |
|-----------|-----------|---------|--------------------------------------|---------------------------------------|-----------|----------|
| Inv-10060 | 28/6/2015 | 10060   |                                      | 1.000,00                              | -1.000,00 | USD      |

As datas e valores de desconto à vista a seguir estão disponíveis para esta fatura.

| Data do desconto à vista | Valor de desconto à vista | Valor na moeda da transação |
|--------------------|----------------------|--------------------------------|
| 3/7/2015           | 20,00                | 980,00                         |
| 12/7/2015          | 10.00                | 990,00                         |
| 25/7/2015          | 0,00                 | 1.000,00                       |

## <a name="payment-on-july-2"></a>Pagamento em 2 de julho
Em 2 de julho, Alice deseja pagar 300,00 da fatura. Ela cria um pagamento único usando a página **Diário de pagamento** em Contas a pagar. Ela adiciona uma linha para o fornecedor 3054 e insere um valor de pagamento de **300,00**. April então abre a página **Liquidar transações**, dessa forma, ela pode marcar a fatura que será liquidada. Ela atualiza o valor no campo **Valor para liquidar** para **300,00** e observa que o valor do campo **Valor do desconto à vista a ser obtido** foi alterado para **6,12**. Como este pagamento é feito no primeiro período de desconto, um desconto de 2 por cento é obtido.

| Marcar | Usar desconto à vista | Comprovante   | Conta | Data      | Data de conclusão  | Fatura | Valor na moeda da transação | Moeda | Valor para liquidar |
|------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------|----------|------------------|
|      | Normal            | Inv-10060 | 3054    | 28/6/2015 | 28/7/2015 | 10060   | 1.000,00                       | USD      | 300,00           |

As informações do desconto aparecem na parte inferior da página **Liquidar transações abertas**.

|                              |           |
|------------------------------|-----------|
| Data do desconto à vista           | 02/07/2015 |
| Valor de desconto à vista         | -20,00    |
| Usar desconto à vista            | Normal    |
| Desconto à vista obtido          | 0,00      |
| Valor do desconto à vista a ser obtido | -6,12     |

Como um desconto à vista está disponível, April quer alterar o valor do pagamento, de forma que o valor total liquidado seja 300,00 para o pagamento e o desconto à vista. Ela altera o valor no campo **Valor para liquidar** para **294,00** e observa que o valor do campo **Valor do desconto à vista a ser obtido** foi alterado para **6,00**.

| Marcar | Usar desconto à vista | Comprovante   | Conta | Data      | Data de conclusão  | Fatura | Valor na moeda da transação | Moeda | Valor para liquidar |
|------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------|----------|------------------|
|      | Normal            | Inv-10060 | 3054    | 28/6/2015 | 28/7/2015 | 10060   | 1.000,00                       | USD      | 294,00           |

As informações do desconto aparecem na parte inferior da página **Liquidar transações abertas**.

|                              |           |
|------------------------------|-----------|
| Data do desconto à vista           | 02/07/2015 |
| Valor de desconto à vista         | -20,00    |
| Usar desconto à vista            | Normal    |
| Desconto à vista obtido          | 0,00      |
| Valor do desconto à vista a ser obtido | -6,00     |

April lança o pagamento. Na página **Transações do fornecedor**, ela pode exibir as transações. Ela vê que 300,00 foram aplicados à fatura. O valor inclui um desconto de 6,00. Consequentemente, o saldo restante é 700,00.

| Comprovante    | Data      | Fatura | Valor em débito na moeda da transação | Valor em crédito na moeda da transação | Saldo | Moeda |
|------------|-----------|---------|--------------------------------------|---------------------------------------|---------|----------|
| Inv-10060  | 28/6/2015 | 10060   |                                      | 1.000,00                              | -700,00 | USD      |
| APP-10060  | 2/7/2015  |         | 294,00                               |                                       | 0,00    | USD      |
| DISC-10060 | 2/7/2015  |         | 6,00                                 |                                       | 0,00    | USD      |

## <a name="payment-on-july-8"></a>Pagamento em 8 de julho
Em 8 de julho, Abril faz um pagamento adicional da fatura. Para inserir o valor, ela abre a página **Liquidar transações** e clica na guia **Desconto à vista**. Ela vê as datas e os valores dos dois descontos à vista que estão disponíveis. Como este pagamento é feito no segundo período de desconto, um desconto de 1 por cento ou 5,00 fica disponível. Esse valor é calculado como a metade do desconto de 1 por cento em 1.000,00, ou a metade de 10,00.

| Data do desconto à vista | Valor de desconto à vista | Valor na moeda da transação |
|--------------------|----------------------|--------------------------------|
| 3/7/2015           | 20,00                | 680,00                         |
| 12/7/2015          | 10.00                | 690,00                         |
| 25/7/2015          | 0,00                 | 700.00                         |

April decide pagar 495,00 e obtém o desconto à vista de 5,00. Consequentemente, o valor total que é liquidado é de 500,00.

| Marcar | Usar desconto à vista | Comprovante   | Conta | Data      | Data de conclusão  | Fatura | Valor na moeda da transação | Moeda | Valor para liquidar |
|------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------|----------|------------------|
|      | Normal            | Inv-10060 | 3054    | 28/6/2015 | 28/7/2015 | 10060   | 1.000,00                       | USD      | 495.00           |

As informações do desconto aparecem na parte inferior da página **Liquidar transações abertas**.

|                              |           |
|------------------------------|-----------|
| Data do desconto à vista           | 12/7/2015 |
| Valor de desconto à vista         | -10,00    |
| Usar desconto à vista            | Normal    |
| Desconto à vista obtido          | -6,00     |
| Valor do desconto à vista a ser obtido | -5,00     |

Na página **Transações do fornecedor**, April considera que o novo saldo é 200,00.

| Comprovante    | Data      | Fatura | Valor em débito na moeda da transação | Valor em crédito na moeda da transação | Saldo | Moeda |
|------------|-----------|---------|--------------------------------------|---------------------------------------|---------|----------|
| Inv-10060  | 28/6/2015 | 10060   |                                      | 1.000,00                              | -200,00 | USD      |
| APP-10060  | 2/7/2015  |         | 294,00                               |                                       | 0,00    | USD      |
| DISC-10060 | 2/7/2015  |         | 6,00                                 |                                       | 0,00    | USD      |
| APP-10061  | 12/7/2015 |         | 495.00                               |                                       | 0,00    | USD      |
| DISC-10061 | 12/7/2015 |         | 5,00                                 |                                       | 0,00    | USD      |

## <a name="payment-on-july-20"></a>Pagamento em 20 de julho
Em 20 de julho, April cria um pagamento final de 200,00. Nenhum desconto é obtido porque o pagamento é feito depois dos períodos de desconto. O saldo da fatura é 0,00.

| Comprovante    | Data      | Fatura | Valor em débito na moeda da transação | Valor em crédito na moeda da transação | Saldo | Moeda |
|------------|-----------|---------|--------------------------------------|---------------------------------------|---------|----------|
| Inv-10060  | 28/6/2015 | 10060   |                                      | 1.000,00                              | -200,00 | USD      |
| APP-10060  | 2/7/2015  |         | 294,00                               |                                       | 0,00    | USD      |
| DISC-10060 | 2/7/2015  |         | 6,00                                 |                                       | 0,00    | USD      |
| APP-10061  | 12/7/2015 |         | 495.00                               |                                       | 0,00    | USD      |
| DISC-10061 | 12/7/2015 |         | 5,00                                 |                                       | 0,00    | USD      |
| APP-10062  | 20/07/2015 |         | 200,00                               |                                       | 0,00    | USD      |





