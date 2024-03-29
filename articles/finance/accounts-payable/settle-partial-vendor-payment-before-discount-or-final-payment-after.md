---
title: Liquidar um pagamento parcial antes da data do desconto e um pagamento final após a data do desconto
description: Este artigo mostra um cenário na qual vários pagamentos parciais são feitos, alguns no período de desconto à vista e outro fora do período de desconto à vista.
author: angelad116
ms.date: 10/24/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerJournalTransVendPaym, VendOpenTrans
audience: Application User
ms.reviewer: twheeloc
ms.custom: 14411
ms.assetid: 302ad6ae-28ee-4899-9f6b-f74424a5f50c
ms.search.region: Global
ms.author: angelading
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 828c82d88bef1d942af1219505af591d27043fa5
ms.sourcegitcommit: cf6b764824bd1cf2c0dde6d37ddd0a7abab87ff0
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/16/2022
ms.locfileid: "9780448"
---
# <a name="settle-partial-payment-before-discount-date-and-final-payment-after-discount-date"></a>Liquidar um pagamento parcial antes da data do desconto e um pagamento final após a data do desconto

[!include [banner](../includes/banner.md)]

Este artigo mostra um cenário na qual vários pagamentos parciais são feitos, alguns no período de desconto à vista e outro fora do período de desconto à vista.

A Fabrikam compra produtos do fornecedor 3057. A Fabrikam recebe um desconto à vista de 1 por cento se a fatura for paga em 14 dias. As faturas devem ser pagas em 30 dias. O fornecedor também permite que a Fabrikam obtenha descontos à vista em pagamentos parciais. Os parâmetros de pagamento estão localizados na página **Parâmetros de contas a pagar**.

## <a name="invoice-on-june-25"></a>Fatura em 25 de junho
Em 25 de junho, Amanda insere e lança uma fatura de 1.000,00 para o fornecedor 3057. Alice pode exibir essa transação na página **Transações do fornecedor**.

| Comprovante   | Tipo de transação | Data      | Fatura | Valor em débito na moeda da transação | Valor em crédito na moeda da transação | Saldo   | Moeda |
|-----------|------------------|-----------|---------|--------------------------------------|---------------------------------------|-----------|----------|
| Inv-10020 | Fatura          | 25/6/2020 | 10020   |                                      | 1.000.00                              | -1.000,00 | USD      |

## <a name="partial-payment-on-july-2"></a>Pagamento parcial em 2 de julho
Em 2 de julho, Alice deseja liquidar 300.00 da fatura. O pagamento está qualificado para um desconto, pois a Fabrikam obtém descontos em pagamentos parciais. Consequentemente, April paga 297,00 e tem um desconto de 3,00. Ela cria um diário de pagamento e insere uma linha para o fornecedor 3057. Ela então abre a página **Liquidar transações**, dessa forma, ela pode marcar a fatura para liquidação.

| Marcar     | Usar desconto à vista | Comprovante   | Conta | Data      | Data de conclusão  | Fatura | Valor na moeda da transação | Moeda | Valor para liquidar |
|----------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------|----------|------------------|
| Selecionados | Normal            | Inv-10020 | 3057    | 25/6/2020 | 25/7/2020 | 10020   | -1.000,00                      | USD      | -297,00          |

As informações do desconto aparecem na parte inferior da página **Liquidar transações abertas**.

| Campo                        | Valor     |
|------------------------------|-----------|
| Data do desconto à vista           | 09/7/2020 |
| Valor de desconto à vista         | -10,00    |
| Usar desconto à vista            | Normal    |
| Desconto à vista obtido          | 0,00      |
| Valor do desconto à vista a ser obtido | -3,00     |

Então Alice lança o pagamento. Agora a fatura tem um saldo de 700,00. Alice pode exibir essa transação na página **Transações do fornecedor**.

| Comprovante    | Tipo de transação | Data      | Fatura | Valor em débito na moeda da transação | Valor em crédito na moeda da transação | Saldo | Moeda |
|------------|------------------|-----------|---------|--------------------------------------|---------------------------------------|---------|----------|
| Inv-10020  | Fatura          | 25/6/2020 | 10020   |                                      | 1.000.00                              | -700,00 | USD      |
| APP-10020  | Pagamento          | 01/07/2020  |         | 297.00                               |                                       | 0,00    | USD      |
| DISC-10020 | Desconto à vista    | 01/07/2020  |         | 3.00                                 |                                       | 0,00    | USD      |

## <a name="remaining-payment-on-july-15-use-cash-discount--normal"></a>Pagamento restante em 15 de julho, Usar desconto à vista = Normal
Alice paga o restante da fatura em 15 de julho, que ocorre após o período de desconto. Na página **Liquidar transações abertas**, nenhum valor de desconto será exibido no campo **Estimativa de desconto à vista** e o valor no campo **Valor de desconto à vista** é **0,00**. Quando April pagar os 700,00 restantes, nenhum desconto adicional será obtido.

| Marcar     | Usar desconto à vista | Comprovante   | Conta | Data      | Data de conclusão  | Fatura | Valor na moeda da transação | Moeda | Valor para liquidar |
|----------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------|----------|------------------|
| Selecionados | Normal            | Inv-10020 | 3057    | 25/6/2020 | 25/7/2020 | 10020   | -700,00                        | USD      | -700,00          |

As informações do desconto aparecem na parte inferior da página **Liquidar transações**. April pode ver que ela já obteve um desconto de 3,00.

| Campo                        | Valor     |
|------------------------------|-----------|
| Data do desconto à vista           | 09/7/2020 |
| Valor de desconto à vista         | 0,00      |
| Usar desconto à vista            | Normal    |
| Desconto à vista obtido          | -3,00     |
| Valor do desconto à vista a ser obtido | 0,00      |

April lança o pagamento. Quando ela abre a página **Transações do fornecedor**, vê que a fatura tem um saldo 0,00. Ela também vê que há dois pagamentos. Um pagamento é de 297,00 e tem um desconto de 3,00, e o outro pagamento é de 700,00.

| Comprovante    | Tipo de transação | Data      | Fatura | Valor em débito na moeda da transação | Valor em crédito na moeda da transação | Saldo | Moeda |
|------------|------------------|-----------|---------|--------------------------------------|---------------------------------------|---------|----------|
| Inv-10020  | Fatura          | 25/6/2020 | 10020   |                                      | 1.000.00                              | 0,00    | USD      |
| APP-10020  | Pagamento          | 01/07/2020  |         | 297.00                               |                                       | 0,00    | USD      |
| DISC-10020 | Desconto à vista    | 01/07/2020  |         | 3.00                                 |                                       | 0,00    | USD      |
| APP-10021  | Pagamento          | 15/7/2020 |         | 700,00                               |                                       | 0,00    | USD      |

## <a name="remaining-payment-on-july-15-use-cash-discount--always"></a>Pagamento restante em 15 de julho, Usar desconto à vista = Sempre
Se o fornecedor permitir que April obtenha um desconto, mesmo que ela esteja pagando após a data de desconto, ela poderá alterar o valor no campo **Usar desconto à vista** para **Sempre**. A configuração **Calcular descontos em dinheiro para pagamentos parciais** é substituída, e o desconto é tomado. O valor do pagamento é de 693,00, e o desconto equivale aos 7,00 restantes.

| Marcar     | Usar desconto à vista | Comprovante   | Conta | Data      | Data de conclusão  | Fatura | Valor em débito na moeda da transação | Valor em crédito na moeda da transação | Moeda | Valor para liquidar |
|----------|----------|------|------|-----------|-----------|---------|-----------------------|---------------------------------------|----------|------------------|
| Selecionados | Sempre            | Inv-10020 | 3057    | 25/6/2020 | 25/7/2020 | 10020   | 700,00                   |                   | USD      | -693,00          |

As informações do desconto aparecem na parte inferior da página **Liquidar transações**.

| Campo                        | Valor     |
|------------------------------|-----------|
| Data do desconto à vista           | 09/7/2020 |
| Valor de desconto à vista         | 7.00      |
| Usar desconto à vista            | Sempre    |
| Desconto à vista obtido          | -3,00     |
| Valor do desconto à vista a ser obtido | -7,00     |

April lança o pagamento. Quando ela abre a página **Transações do fornecedor**, vê que a fatura tem um saldo 0,00. Ela também vê que há dois pagamentos. Um pagamento é de 297,00 e tem um desconto de 3,00, e o outro pagamento é de 693,00 e tem um desconto de 7,00.

| Comprovante    | Tipo de transação | Data      | Fatura | Valor em débito na moeda da transação | Valor em crédito na moeda da transação | Saldo | Moeda |
|------------|------------------|-----------|---------|--------------------------------------|---------------------------------------|---------|----------|
| Inv-10020  | Fatura          | 25/6/2020 | 10020   |                                      | 1.000.00                              | 0,00    | USD      |
| APP-10020  | Pagamento          | 01/07/2020  |         | 297.00                               |                                       | 0,00    | USD      |
| DISC-10020 | Desconto à vista    | 01/07/2020  |         | 3.00                                 |                                       | 0,00    | USD      |
| APP-10021  | Pagamento          | 15/7/2020 |         | 693.00                               |                                       | 0,00    | USD      |
| DISC-10021 | Desconto à vista    | 15/7/2020 |         | 7.00                                 |                                       | 0,00    | USD      |







[!INCLUDE[footer-include](../../includes/footer-banner.md)]
