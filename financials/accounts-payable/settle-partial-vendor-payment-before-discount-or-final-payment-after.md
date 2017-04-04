---
title: "Liquidar um pagamento parcial fornecedor antes da data do desconto com um pagamento final após a data de desconto"
description: "Este artigo mostra um cenário na qual vários pagamentos parciais são feitos, alguns no período de desconto à vista e outro fora do período de desconto à vista."
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
ms.custom: 14411
ms.assetid: 302ad6ae-28ee-4899-9f6b-f74424a5f50c
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 2cb439e871d57f74c296697cfc42705fb0121bb7
ms.openlocfilehash: 33851ff7c9ee2c50544589ade0191798a13706e7
ms.lasthandoff: 03/31/2017


---

# <a name="settle-a-partial-vendor-payment-before-the-discount-date-with-a-final-payment-after-the-discount-date"></a>Liquidar um pagamento parcial fornecedor antes da data do desconto com um pagamento final após a data de desconto

Este artigo mostra um cenário na qual vários pagamentos parciais são feitos, alguns no período de desconto à vista e outro fora do período de desconto à vista.

Fabrikam compra bens de fornecedor 3057. A Fabrikam recebe um desconto à vista de 1 por cento se a fatura é pago em 14 dias. As faturas devem ser pagas em 30 dias. O fornecedor também permite que a Fabrikam obtenha descontos à vista em pagamentos parciais. Parâmetros de pagamento estão localizados ** parâmetros de contas a pagar ** na página.

## <a name="invoice-on-june-25"></a>Fatura em 25 de junho
abril o 25 de junho, insere e lança uma nota fiscal para 1,000.00 para o fornecedor 3057. Alice pode exibir essa transação na página **Transações do fornecedor**.

| Comprovante   | Tipo de transação | Data      | Fatura | Valor em débito na moeda da transação | Valor em crédito na moeda da transação | Saldo   | Moeda |
|-----------|------------------|-----------|---------|--------------------------------------|---------------------------------------|-----------|----------|
| Inv-10020 | Fatura          | 25/6/2015 | 10020   |                                      | 1.000,00                              | -1.000,00 | USD      |

## <a name="partial-payment-on-july-2"></a>Pagamento parcial em 2 de julho
Em 2 de julho, Alice deseja liquidar 300.00 da fatura. O pagamento está qualificado para um desconto, pois a Fabrikam obtém descontos em pagamentos parciais. Consequentemente, April paga 297,00 e tem um desconto de 3,00. Criar um diário de pagamento e insira uma linha para o fornecedor 3057. Então abre ** transações de acordo ** a página, de modo que possa marcar a nota fiscal para pagamento.

| Marcar     | Usar desconto à vista | Comprovante   | Conta | Data      | Data de conclusão  | Fatura | Valor na moeda da transação | Moeda | Valor para liquidar |
|----------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------|----------|------------------|
| Selecionada | Normal            | Inv-10020 | 3057    | 25/6/2015 | 25/7/2015 | 10020   | -1.000,00                      | USD      | -297,00          |

As informações do desconto aparecem na parte inferior da página **Liquidar transações abertas**.

|                              |           |
|------------------------------|-----------|
| Data do desconto à vista           | 09/07/2015 |
| Valor de desconto à vista         | -10,00    |
| Usar desconto à vista            | Normal    |
| Desconto à vista obtido          | 0,00      |
| Valor do desconto à vista a ser obtido | -3,00     |

Então Alice lança o pagamento. Agora a fatura tem um saldo de 700,00. Alice pode exibir essa transação na página **Transações do fornecedor**.

| Comprovante    | Tipo de transação | Data      | Fatura | Valor em débito na moeda da transação | Valor em crédito na moeda da transação | Saldo | Moeda |
|------------|------------------|-----------|---------|--------------------------------------|---------------------------------------|---------|----------|
| Inv-10020  | Fatura          | 25/6/2015 | 10020   |                                      | 1.000,00                              | -700,00 | USD      |
| APP-10020  | Pagamento          | 01/07/2015  |         | 297.00                               |                                       | 0,00    | USD      |
| DISC-10020 | Desconto à vista    | 01/07/2015  |         | 3,00                                 |                                       | 0,00    | USD      |

## <a name="remaining-payment-on-july-15-use-cash-discount--normal"></a>Pagamento restante em 15 de julho, Usar desconto à vista = Normal
Alice paga o restante da fatura em 15 de julho, que ocorre após o período de desconto. Na página **Liquidar transações abertas**, nenhum valor de desconto será exibido no campo **Estimativa de desconto à vista** e o valor no campo **Valor de desconto à vista** é **0,00**. Quando April pagar os 700,00 restantes, nenhum desconto adicional será obtido.

| Marcar     | Usar desconto à vista | Comprovante   | Conta | Data      | Data de conclusão  | Fatura | Valor na moeda da transação | Moeda | Valor para liquidar |
|----------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------|----------|------------------|
| Selecionada | Normal            | Inv-10020 | 3057    | 25/6/2015 | 25/7/2015 | 10020   | -700,00                        | USD      | -700,00          |

As informações do desconto aparecem na parte inferior da página **Liquidar transações**. April pode ver que ela já obteve um desconto de 3,00.

|                              |           |
|------------------------------|-----------|
| Data do desconto à vista           | 09/07/2015 |
| Valor de desconto à vista         | 0,00      |
| Usar desconto à vista            | Normal    |
| Desconto à vista obtido          | -3,00     |
| Valor do desconto à vista a ser obtido | 0,00      |

April lança o pagamento. Quando ela abre a página **Transações do fornecedor**, vê que a fatura tem um saldo 0,00. Ela também vê que há dois pagamentos. Um pagamento é de 297,00 e tem um desconto de 3,00, e o outro pagamento é de 700,00.

| Comprovante    | Tipo de transação | Data      | Fatura | Valor em débito na moeda da transação | Valor em crédito na moeda da transação | Saldo | Moeda |
|------------|------------------|-----------|---------|--------------------------------------|---------------------------------------|---------|----------|
| Inv-10020  | Fatura          | 25/6/2015 | 10020   |                                      | 1.000,00                              | 0,00    | USD      |
| APP-10020  | Pagamento          | 01/07/2015  |         | 297.00                               |                                       | 0,00    | USD      |
| DISC-10020 | Desconto à vista    | 01/07/2015  |         | 3,00                                 |                                       | 0,00    | USD      |
| APP-10021  | Pagamento          | 15/7/2015 |         | 700.00                               |                                       | 0,00    | USD      |

## <a name="remaining-payment-on-july-15-use-cash-discount--always"></a>Pagamento restante em 15 de julho, Usar desconto à vista = Sempre
Se o fornecedor deixa abril executar um desconto está pagando mesmo que após a data de desconto, poderá alterar valor ** desconto à vista ** o uso no campo sempre ** **. ** Calcular descontos à vista para pagamentos parciais ** a configuração é substituída, e o desconto será obtido. O valor do pagamento é de 693,00, e o desconto equivale aos 7,00 restantes.

| Marcar     | Usar desconto à vista | Comprovante   | Conta | Data      | Data de conclusão  | Fatura | Valor em débito na moeda da transação | Valor em crédito na moeda da transação | Moeda | Valor para liquidar |
|----------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------------|---------------------------------------|----------|------------------|
| Selecionada | Sempre            | Inv-10020 | 3057    | 25/6/2015 | 25/7/2015 | 10020   | 700.00                               |                                       | USD      | -693,00          |

As informações do desconto aparecem na parte inferior da página **Liquidar transações**.

|                              |           |
|------------------------------|-----------|
| Data do desconto à vista           | 09/07/2015 |
| Valor de desconto à vista         | 7:00      |
| Usar desconto à vista            | Sempre    |
| Desconto à vista obtido          | -3,00     |
| Valor do desconto à vista a ser obtido | -7,00     |

April lança o pagamento. Quando ela abre a página **Transações do fornecedor**, vê que a fatura tem um saldo 0,00. Ela também vê que há dois pagamentos. Um pagamento é de 297,00 e tem um desconto de 3,00, e o outro pagamento é de 693,00 e tem um desconto de 7,00.

| Comprovante    | Tipo de transação | Data      | Fatura | Valor em débito na moeda da transação | Valor em crédito na moeda da transação | Saldo | Moeda |
|------------|------------------|-----------|---------|--------------------------------------|---------------------------------------|---------|----------|
| Inv-10020  | Fatura          | 25/6/2015 | 10020   |                                      | 1.000,00                              | 0,00    | USD      |
| APP-10020  | Pagamento          | 01/07/2015  |         | 297.00                               |                                       | 0,00    | USD      |
| DISC-10020 | Desconto à vista    | 01/07/2015  |         | 3,00                                 |                                       | 0,00    | USD      |
| APP-10021  | Pagamento          | 15/7/2015 |         | 693.00                               |                                       | 0,00    | USD      |
| DISC-10021 | Desconto à vista    | 15/7/2015 |         | 7:00                                 |                                       | 0,00    | USD      |




