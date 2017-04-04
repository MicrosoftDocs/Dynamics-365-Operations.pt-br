---
title: "Liquidar um pagamento parcial de cliente antes da data do desconto com um pagamento final após a data de desconto"
description: "Este artigo discute o efeito de liquidar pagamentos de faturas de clientes. O cenário se concentra nos efeitos no sub-razão, e não na Contabilidade."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: CustOpenTrans, LedgerJournalTransCustPaym
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 14584
ms.assetid: e54936f5-053b-4ed3-b778-42c7e9aeb7cf
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 2cb439e871d57f74c296697cfc42705fb0121bb7
ms.openlocfilehash: f3234bf607ef9ce1643226894716b975a2c2a7b9
ms.lasthandoff: 03/31/2017


---

# <a name="settle-a-partial-customer-payment-before-the-discount-date-with-a-final-payment-after-the-discount-date"></a>Liquidar um pagamento parcial de cliente antes da data do desconto com um pagamento final após a data de desconto

Este artigo discute o efeito de liquidar pagamentos de faturas de clientes. O cenário se concentra nos efeitos no sub-razão, e não na Contabilidade.

Fabrikam vende mercadorias para o cliente 4027. Fabrikam oferece um desconto à vista de 1 por cento se a fatura é pago em 14 dias. As faturas devem ser pagas em 30 dias. A Fabrikam também oferece descontos à vista para pagamentos parciais. Parâmetros de pagamento estão localizados ** parâmetros de contas a receber ** na página.

## <a name="invoice"></a>Fatura
O 25 de junho, Arnie insere e lança uma nota fiscal para 1,000.00 para o cliente 4027. Arnie pode exibir estas fatura usando ** transações ** o botão ** clientes ** na página.

| Comprovante   | Tipo de transação | Data      | Fatura | Valor em débito na moeda da transação | Valor em crédito na moeda da transação | Saldo  | Moeda |
|-----------|------------------|-----------|---------|--------------------------------------|---------------------------------------|----------|----------|
| FTI-10020 | Fatura          | 25/6/2015 | 10020   | 1.000,00                             |                                       | 1.000,00 | USD      |

## <a name="partial-payment-before-the-cash-discount-date"></a>Pagamento parcial antes da data de desconto à vista
Em 2 de julho, o cliente 4027 faz um pagamento parcial de 297,00 para a fatura. O pagamento é qualificado para um desconto à vista porque a Fabrikam oferece descontos à vista em pagamentos parciais e o pagamento parcial é feito antes da data de desconto à vista. Consequentemente, o cliente 4027 tem um desconto de 3,00. Arnie registra o pagamento para o cliente 4027 usando o diário de pagamentos. Arnie então abre a página **Liquidar transações**, dessa forma, ele pode marcar a fatura para liquidação.

| Marcar     | Usar desconto à vista | Comprovante   | Conta | Data      | Data de conclusão  | Fatura | Valor em débito na moeda da transação | Moeda | Valor para liquidar |
|----------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------------|----------|------------------|
| Selecionada | Normal            | FTI-10020 | 4027    | 25/6/2015 | 25/7/2015 | 10020   | 1.000,00                             | USD      | 297.00           |

As informações do desconto aparecem na parte inferior da página **Liquidar transações abertas**. Se você não alterar o valor da opção **Valor para liquidar** para 297,00, os valores da opção **Valor de desconto à vista** que aparecem serão diferentes. Entretanto, 3.00 serão tiradas como o desconto à vista quando o pagamento for lançado, como o pagamento automaticamente ajusta ** valor o comprometimento ** valor para você.

|                              |           |
|------------------------------|-----------|
| Data do desconto à vista           | 09/07/2015 |
| Valor de desconto à vista         | 10.00     |
| Usar desconto à vista            | Normal    |
| Desconto à vista obtido          | 0,00      |
| Valor do desconto à vista a ser obtido | 3,00      |

Arnie lança o pagamento. Agora a fatura tem um saldo de 700,00. As transações a seguir podem ser vistas para o cliente.

| Comprovante    | Tipo de transação | Data      | Fatura | Valor em débito na moeda da transação | Valor em crédito na moeda da transação | Saldo | Moeda |
|------------|------------------|-----------|---------|--------------------------------------|---------------------------------------|---------|----------|
| FTI-10020  | Fatura          | 25/6/2015 | 10020   | 1.000,00                             |                                       | 700.00  | USD      |
| ARP-10020  |  Pagamento         | 01/07/2015  |         |                                      | 297.00                                | 0,00    | USD      |
| DISC-10020 |  Desconto à vista   | 01/07/2015  |         |                                      | 3,00                                  | 0,00    | USD      |

## <a name="remaining-payment-after-the-cash-discount-date"></a>Pagamento restante após a data de desconto à vista
Em 11 de julho, após o período do desconto, o cliente 4027 paga o restante desta fatura. Na página **Liquidar transações**, um valor de desconto não aparece no campo **Estimativa de desconto em dinheiro** e o valor no campo **Valor de desconto à vista** é **0,00**. Quando o cliente 4027 paga os 700,00 restantes, nenhum desconto adicional será usado.

| Marcar     | Usar desconto à vista | Comprovante   | Conta | Data      | Data de conclusão  | Fatura | Valor em débito na moeda da transação | Moeda | Valor para liquidar |
|----------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------------|----------|------------------|
| Selecionada | Normal            | FTI-10020 | 4027    | 25/6/2015 | 25/7/2015 | 10020   | 700.00                               | USD      | 700.00           |

As informações do desconto aparecem na parte inferior da página **Liquidar transações abertas**.

|                              |           |
|------------------------------|-----------|
| Data do desconto à vista           | 09/07/2015 |
| Valor de desconto à vista         | 0,00      |
| Usar desconto à vista            | Normal    |
| Desconto à vista obtido          | 3,00      |
| Valor do desconto à vista a ser obtido | 0,00      |

Se Arnie alterar o valor no campo **Usar desconto à vista** para **Sempre**, a configuração **Calcular descontos à vista para pagamentos parciais** será substituída, e o desconto à vista será obtido. O valor do pagamento é alterado para 693,00, e o desconto à vista equivale aos 7,00 restantes.

| Marcar     | Usar desconto à vista | Comprovante   | Conta | Data      | Data de conclusão  | Fatura | Valor em débito na moeda da transação | Valor em crédito na moeda da transação | Moeda | Valor para liquidar |
|----------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------------|---------------------------------------|----------|------------------|
| Selecionada | Sempre            | FTI-10020 | 4027    | 25/6/2015 | 25/7/2015 | 10020   | 700.00                               |                                       | USD      | 693.00           |

As informações do desconto aparecem na parte inferior da página **Liquidar transações abertas**.

|                              |           |
|------------------------------|-----------|
| Data do desconto à vista           | 09/07/2015 |
| Valor de desconto à vista         | 7:00      |
| Usar desconto à vista            | Sempre    |
| Desconto à vista obtido          | 3,00      |
| Valor do desconto à vista a ser obtido | 7:00      |

Arnie altera o valor no campo**Usar desconto à vista** novamente para **Normal**, porque não permitirá que o cliente obtenha o desconto restante de 7,00. Então, Arnie lança o pagamento. Quando Arnie abre a página** Transações do cliente**, ele vê que a fatura tem um saldo de 0,00. Ele também vê que há dois pagamentos. Um pagamento é de 297,00 e tem um desconto à vista de 3,00, e o outro pagamento é de 700,00.

| Comprovante    | Tipo de transação | Data      | Fatura | Valor em débito na moeda da transação | Valor em crédito na moeda da transação | Saldo | Moeda |
|------------|------------------|-----------|---------|--------------------------------------|---------------------------------------|---------|----------|
| FTI-10020  | Fatura          | 25/6/2015 | 10020   | 1.000,00                             |                                       | 0,00    | USD      |
| ARP-10020  |                  | 01/07/2015  |         |                                      | 297.00                                | 0,00    | USD      |
| DISC-10020 |                  | 01/07/2015  |         |                                      | 3,00                                  | 0,00    | USD      |
| ARP-10021  |                  | 11/07/2015 |         |                                      | 700.00                                | 0,00    | USD      |




