---
title: Liquidar um pagamento parcial de fornecedor e liquidar o pagamento final em sua totalidade antes da data do desconto
description: Este artigo mostra um cenário no qual os pagamentos parciais são feitos para uma nota fiscal de fornecedor, e um desconto à vista será obtido.
author: angelad116
ms.date: 10/24/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerJournalTransVendPaym, VendOpenTrans
audience: Application User
ms.reviewer: angelading
ms.custom: 14431
ms.assetid: 6b8e3420-b4c9-4e02-9588-598fe6d3df0d
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5af6b47c816686a31015f07c8c81544481fc4433
ms.sourcegitcommit: 0d5c07ba91a9ceb2eeb11db032fd28037216789d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/25/2022
ms.locfileid: "9715901"
---
# <a name="settle-a-partial-vendor-payment-and-the-final-payment-in-full-before-the-discount-date"></a>Liquidar um pagamento parcial de fornecedor e liquidar o pagamento final em sua totalidade antes da data do desconto

[!include [banner](../includes/banner.md)]

Este artigo mostra um cenário no qual os pagamentos parciais são feitos para uma nota fiscal de fornecedor, e um desconto à vista será obtido.

A Fabrikam compra produtos do fornecedor 3064. O fornecedor oferece à Fabrikam um desconto à vista de 1% se uma fatura for paga em 14 dias. As faturas devem ser pagas em 30 dias. O fornecedor também permite que a Fabrikam obtenha descontos à vista em pagamentos parciais. Os parâmetros de pagamento estão localizados na página **Parâmetros de contas a pagar**. Em 25 de junho, Amanda insere uma fatura de 1.000,00 para o fornecedor 3064.

## <a name="vendor-invoice-on-june-25"></a>Fatura de fornecedor em 25 de junho
Em 25 de junho, Amanda insere e lança uma fatura de 1.000,00 para o fornecedor 3064. Alice pode exibir essa transação na página **Transações do fornecedor**.

| Comprovante   | Data      | Fatura | Valor em débito na moeda da transação | Valor em crédito na moeda da transação | Saldo   | Moeda |
|-----------|-----------|---------|--------------------------------------|---------------------------------------|-----------|----------|
| Inv-10010 | 25/6/2015 | 10010   |                                      | 1.000,00                              | -1.000,00 | USD      |

Na página **Fornecedores**, Alice abre a página **Liquidar transações**. Ela pode usar a página **Liquidar transações** para exibir as datas e os valores de descontos à vista. A data de vencimento é 25 de julho, e um desconto à vista de -10,00 está disponível caso a fatura seja paga até 9 de julho.

| Marcar | Usar desconto à vista | Comprovante   | Conta | Data      | Data de conclusão  | Fatura | Valor na moeda da transação | Moeda | Valor para liquidar |
|------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------|----------|------------------|
|      | Normal            | Inv-10010 | 3064    | 25/6/2015 | 25/7/2015 | 10010   | 1.000,00                       | USD      | 990,00           |

As informações do desconto aparecem na parte inferior da página **Liquidar transações abertas**.

|       &nbsp;                 | &nbsp;    |
|------------------------------|-----------|
| Data do desconto à vista           | 09/07/2015 |
| Valor de desconto à vista         | -10,00    |
| Usar desconto à vista            | Normal    |
| Desconto à vista obtido          | 0,00      |
| Valor do desconto à vista a ser obtido | -10,00    |

Alice clica na guia **Desconto à vista** para exibir o valor do desconto.

| Data do desconto à vista | Valor de desconto à vista | Valor na moeda da transação |
|--------------------|----------------------|--------------------------------|
| 9/7/2015           | 10.00                | 990,00                         |
| 25/7/2015          | 0,00                 | 1.000,00                       |

## <a name="partial-payment-on-july-1-by-using-the-settle-transactions-page"></a>Pagamento parcial em 1º de julho usando a página Liquidar transações
Alice pode criar um diário de pagamento para esse pagamento abrindo a página **Diário de pagamento** em Contas a pagar. Ela cria um novo diário e insere uma linha para o fornecedor 3064. Ela então abre a página **Liquidar transações**, dessa forma, ela pode marcar a fatura para liquidação. Alice marca a fatura e altera o valor do campo **Valor a ser liquidado** para **-500,00**. Ela vê que o valor do campo **Valor do desconto à vista** é **-10,00** para a fatura total e que o valor do campo **Valor do desconto a vista a ser obtido** é **-5,05**. Consequentemente, Amanda está liquidando -505,05 desta fatura.

| Marcar     | Usar desconto à vista | Comprovante   | Conta | Data      | Data de conclusão  | Fatura | Valor na moeda da transação | Moeda | Valor para liquidar |
|----------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------|----------|------------------|
| Selecionada | Normal            | FTI-10010 | 4028    | 25/6/2015 | 25/7/2015 | 10010   | 1.000,00                       | USD      | -500,00          |

As informações do desconto aparecem na parte inferior da página **Liquidar transações abertas**.

|  &nbsp;                      |  &nbsp;   |
|------------------------------|-----------|
| Data do desconto à vista           | 09/07/2015 |
| Valor de desconto à vista         | -10,00    |
| Usar desconto à vista            | Normal    |
| Desconto à vista obtido          | 0,00      |
| Valor do desconto à vista a ser obtido | -5,05     |

Alice deseja liquidar exatamente a metade da fatura. Portanto, ela altera o valor do campo **Valor a ser liquidado** para **-495,00**. O valor total liquidado agora é de 500,00. O valor inclui um desconto à vista de 5,00.

| Marcar     | Usar desconto à vista | Comprovante   | Conta | Data      | Data de conclusão  | Fatura | Valor na moeda da transação | Moeda | Valor para liquidar |
|----------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------|----------|------------------|
| Selecionada | Normal            | FTI-10010 | 4028    | 25/6/2015 | 25/7/2015 | 10010   | 1.000,00                       | USD      | -495,00          |

As informações do desconto aparecem na parte inferior da página **Liquidar transações abertas**.

|  &nbsp;                      |  &nbsp;   |
|------------------------------|-----------|
| Data do desconto à vista           | 09/07/2015 |
| Valor de desconto à vista         | -10,00    |
| Usar desconto à vista            | Normal    |
| Desconto à vista obtido          | 0,00      |
| Valor do desconto à vista a ser obtido | -5,00     |

Alice fecha a página **Liquidar transações**. Uma linha de pagamento para 495,00 é criada no diário, e Amanda lança o diário. Amanda pode rever as transações do fornecedor na página **Transações do fornecedor**. Ela vê que a fatura tem um saldo de -500,00. Ela também vê um pagamento de 495,00 e um desconto à vista de 5,00.

| Comprovante    | Tipo de transação | Data      | Fatura | Valor em débito na moeda da transação | Valor em crédito na moeda da transação | Saldo | Moeda |
|------------|------------------|-----------|---------|--------------------------------------|---------------------------------------|---------|----------|
| Inv-10010  | Fatura          | 25/6/2015 | 10010   |                                      | 1.000,00                              | -500,00 | USD      |
| APP-10010  | Pagamento          | 01/07/2015  |         | 495.00                               |                                       | 0,00    | USD      |
| DISC-10010 | Desconto à vista    | 01/07/2015  |         | 5,00                                 |                                       | 0,00    | USD      |

## <a name="remaining-amount-paid-on-july-8"></a>O valor restante é pago em 8 de julho
Amanda paga o restante da fatura para o fornecedor 3064 em 8 de julho, que está no período de desconto à vista. Amanda cria o diário de pagamentos em 8 de julho e marca a transação para liquidação. Ela vê que o valor que deve ser liquidado é de 495,00. O valor do campo **Desconto à vista estimado** é **-5,00**, já que o desconto de 5,00 foi obtido anteriormente.

|  &nbsp;                 |  &nbsp; |
|-------------------------|--------|
| Total marcado            | 495.00 |
| Estimativa de desconto em dinheiro | -5,00  |

As informações sobre a transação marcada aparecem na grade da página **Liquidar transações abertas**.

| Marcar     | Usar desconto à vista | Comprovante   | Conta | Data      | Data de conclusão  | Fatura | Valor na moeda da transação | Moeda | Valor para liquidar |
|----------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------|----------|------------------|
| Selecionada | Normal            | FTI-10010 | 4028    | 25/6/2015 | 25/7/2015 | 10010   | 1.000,00                       | USD      | 495.00           |

As informações do desconto aparecem na parte inferior da página **Liquidar transações abertas**.

|  &nbsp;                      | &nbsp;    |
|------------------------------|-----------|
| Data do desconto à vista           | 09/07/2015 |
| Valor de desconto à vista         | 10.00     |
| Usar desconto à vista            | Normal    |
| Desconto à vista obtido          | 5,00      |
| Valor do desconto à vista a ser obtido | 5,00      |

Alice lança o diário de pagamento e analisa e as transações do fornecedor na página **Transações do fornecedor**. O saldo da fatura agora é 0,00, e Amanda vê os dois pagamentos e os dois descontos à vista.

| Comprovante    | Tipo de transação | Data      | Fatura | Valor em débito na moeda da transação | Valor em crédito na moeda da transação | Saldo | Moeda |
|------------|------------------|-----------|---------|--------------------------------------|---------------------------------------|---------|----------|
| Inv-10010  | Fatura          | 25/6/2015 | 10010   |                                      | 1.000,00                              | 0,00    | USD      |
| APP-10010  |  Pagamento         | 01/07/2015  |         | 495.00                               |                                       | 0,00    | USD      |
| DISC-10010 | Desconto à vista    | 01/07/2015  |         | 5,00                                 |                                       | 0,00    | USD      |
| APP-10011  | Pagamento          | 8/7/2015  |         | 495.00                               |                                       | 0,00    | USD      |
| DISC-10011 | Desconto à vista    | 8/7/2015  |         | 5,00                                 |                                       | 0,00    | USD      |







[!INCLUDE[footer-include](../../includes/footer-banner.md)]
