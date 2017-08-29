---
title: "Liquidar um pagamento parcial de cliente antes da data do desconto com um pagamento final posterior à data do desconto"
description: "Este artigo discute o efeito de liquidar pagamentos de faturas de clientes. O cenário se concentra nos efeitos no sub-razão, e não na Contabilidade."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/22/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CustOpenTrans, LedgerJournalTransCustPaym
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 14584
ms.assetid: e54936f5-053b-4ed3-b778-42c7e9aeb7cf
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 4399cf66e423d2e6436c664e6485a77d9ad75d69
ms.contentlocale: pt-br
ms.lasthandoff: 05/25/2017

---

# <a name="settle-a-partial-customer-payment-before-the-discount-date-with-a-final-payment-after-the-discount-date"></a>Liquidar um pagamento parcial de cliente antes da data do desconto com um pagamento final posterior à data do desconto

[!include[banner](../includes/banner.md)]


Este artigo discute o efeito de liquidar pagamentos de faturas de clientes. O cenário se concentra nos efeitos no sub-razão, e não na Contabilidade.

A Fabrikam vende produtos para o cliente 4027. Oferece um desconto à vista de 1 por cento se a fatura for paga em 14 dias. As faturas devem ser pagas em 30 dias. A Fabrikam também oferece descontos à vista para pagamentos parciais. Os parâmetros de pagamento estão localizados na página **Parâmetros de contas a receber**.

## <a name="invoice"></a>Fatura
Em 25 de junho, Amanda insere e lança uma fatura de 1.000,00 para o cliente 4027. Arnie pode exibir estas fatura usando o botão **Transações** na página **Clientes**.

| Comprovante   | Tipo de transação | Data      | Fatura | Valor em débito na moeda da transação | Valor em crédito na moeda da transação | Saldo  | Moeda |
|-----------|------------------|-----------|---------|--------------------------------------|---------------------------------------|----------|----------|
| FTI-10020 | Fatura          | 25/6/2015 | 10020   | 1.000,00                             |                                       | 1.000,00 | USD      |

## <a name="partial-payment-before-the-cash-discount-date"></a>Pagamento parcial antes da data de desconto à vista
Em 2 de julho, o cliente 4027 faz um pagamento parcial de 297,00 para a fatura. O pagamento é qualificado para um desconto à vista porque a Fabrikam oferece descontos à vista em pagamentos parciais e o pagamento parcial é feito antes da data de desconto à vista. Consequentemente, o cliente 4027 tem um desconto de 3,00. Arnie registra o pagamento para o cliente 4027 usando o diário de pagamentos. Arnie então abre a página **Liquidar transações**, dessa forma, ele pode marcar a fatura para liquidação.

| Marcar     | Usar desconto à vista | Comprovante   | Conta | Data      | Data de conclusão  | Fatura | Valor em débito na moeda da transação | Moeda | Valor para liquidar |
|----------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------------|----------|------------------|
| Selecionada | Normal            | FTI-10020 | 4027    | 25/6/2015 | 25/7/2015 | 10020   | 1.000,00                             | USD      | 297.00           |

As informações do desconto aparecem na parte inferior da página **Liquidar transações abertas**. Se você não alterar o valor da opção **Valor para liquidar** para 297,00, os valores da opção **Valor de desconto à vista** que aparecem serão diferentes. No entanto, 3,00 serão obtidos como o desconto à vista quando o pagamento for lançado, pois a liquidação é ajustada automaticamente ao Valor a ser liquidado para você.

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

Arnie altera o valor no campo**Usar desconto à vista** novamente para **Normal**, porque não permitirá que o cliente obtenha o desconto restante de 7,00. Então, Arnie lança o pagamento. Quando Arnie abre a página**Transações do cliente**, ele vê que a fatura tem um saldo de 0,00. Ele também vê que há dois pagamentos. Um pagamento é de 297,00 e tem um desconto à vista de 3,00, e o outro pagamento é de 700,00.

| Comprovante    | Tipo de transação | Data      | Fatura | Valor em débito na moeda da transação | Valor em crédito na moeda da transação | Saldo | Moeda |
|------------|------------------|-----------|---------|--------------------------------------|---------------------------------------|---------|----------|
| FTI-10020  | Fatura          | 25/6/2015 | 10020   | 1.000,00                             |                                       | 0,00    | USD      |
| ARP-10020  |                  | 01/07/2015  |         |                                      | 297.00                                | 0,00    | USD      |
| DISC-10020 |                  | 01/07/2015  |         |                                      | 3,00                                  | 0,00    | USD      |
| ARP-10021  |                  | 11/07/2015 |         |                                      | 700.00                                | 0,00    | USD      |






