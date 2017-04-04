---
title: Liquidar um pagamento parcial de cliente e do pagamento final antes da data do desconto
description: "Este artigo oferece os cenários que mostram como registrar pagamentos parciais para um cliente e executar descontos à vista no período de desconto à vista."
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
ms.custom: 14491
ms.assetid: 0f07d3ce-a439-43ed-a22e-957ccd36a37b
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: f707d45290682e79ee439ba0d504852429defa90
ms.openlocfilehash: ac2c569666b97bc430d3d677366a88446ab76091
ms.lasthandoff: 03/31/2017


---

# <a name="settle-a-partial-customer-payment-and-the-final-payment-in-full-before-the-discount-date"></a>Liquidar um pagamento parcial de cliente e do pagamento final antes da data do desconto

Este artigo oferece os cenários que mostram como registrar pagamentos parciais para um cliente e executar descontos à vista no período de desconto à vista.

Fabrikam vende mercadorias para o cliente 4028. Fabrikam oferece um desconto à vista de 1 por cento se a fatura é pago em 14 dias. As faturas devem ser pagas em 30 dias. A Fabrikam também oferece descontos à vista para pagamentos parciais. Parâmetros de pagamento estão localizados ** parâmetros de contas a receber ** na página.

## <a name="customer-invoice"></a>Fatura de cliente
O 25 de junho, Arnie insere e lança uma nota fiscal para 1,000.00 para o cliente 4028. Alberto pode exibir esta transação na página** Transações do cliente**.

| Comprovante   | Tipo de transação | Data      | Fatura | Valor em débito na moeda da transação | Valor em crédito na moeda da transação | Saldo  | Moeda |
|-----------|------------------|-----------|---------|--------------------------------------|---------------------------------------|----------|----------|
| FTI-10010 | Fatura          | 25/6/2015 | 10010   | 1.000,00                             |                                       | 1.000,00 | USD      |

Na página **Cliente** ou **Transações de cliente**, Alberto pode abrir a página **Liquidar transações** para exibir as datas e os valores dos descontos à vista disponíveis para a fatura. A data de vencimento é 25 de julho, e um desconto à vista de 10,00 está disponível caso a fatura seja paga até 9 de julho.

| Marcar     | Usar desconto à vista | Comprovante   | Conta | Data      | Data de conclusão  | Fatura | Valor na moeda da transação | Moeda | Valor para liquidar |
|----------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------|----------|------------------|
| Selecionada | Normal            | FTI-10010 | 4028    | 25/6/2015 | 25/7/2015 | 10010   | 1.000,00                       | USD      | 990,00           |

As informações do desconto aparecem na parte inferior da página **Liquidar transações** da fatura marcada.

|                              |           |
|------------------------------|-----------|
| Data do desconto à vista           | 09/07/2015 |
| Valor de desconto à vista         | 10.00     |
| Usar desconto à vista            | Normal    |
| Desconto à vista obtido          | 0,00      |
| Valor do desconto à vista a ser obtido | 10.00     |

Alberto clica na guia **Desconto à vista** para exibir o valor do desconto.

| Data do desconto à vista | Valor de desconto à vista | Valor na moeda da transação |
|--------------------|----------------------|--------------------------------|
| 9/7/2015           | 10.00                | 990,00                         |
| 25/7/2015          | 0,00                 | 1.000,00                       |

## <a name="partial-payment-by-using-the-enter-customer-payments-page"></a>Pagamento parcial usando a página Inserir pagamentos do cliente
O cliente 4028 enviar um pagamento de 500.00 o 1º de julho. Para inserir o pagamento, Arnie não clica ** ** linhas. Em vez disso, ele registra o pagamento criando um novo diário de pagamentos e depois abre a página **Inserir pagamentos de clientes**. Ele insere as informações de pagamento e marca a fatura inserida. Quando Alberto insere **500,00** como o valor, também insere **500,00** no campo **Valor a ser pago** na grade. Como a Fabrikam permite um desconto à vista em pagamentos parciais, ele vê que um desconto à vista parcial de 5,.05 também será obtido. O cálculo desse desconto é 500,00 ÷ 0,99 × 0,01 = 5,05. (Nesse cálculo, 500,00 é dividido por 0,99, porque há um desconto de 1%. Consequentemente, o cliente paga 99% da fatura. O resultado é então multiplicado pela porcentagem de desconto, que é de 1%, ou 0,01. Se o cliente assume o desconto total de 10.00, o valor que deve ser liquidado será 990.00.) Informações de desconto exibida na grade na parte inferior ** inserir pagamentos de clientes ** de página.

| Valor do desconto à vista a ser obtido | Desconto à vista obtido | Valor a ser pago |
|------------------------------|---------------------|---------------|
| 5,05                         | 0,00                | 500,00        |

## <a name="partial-payment-by-using-the-journal-lines"></a>Pagamento parcial usando as linhas do diário
Em vez de abrir a página **Inserir pagamentos de clientes** no diário de pagamento, Alberto poderá clicar em **Linhas** para inserir um pagamento. O diário de pagamento é exibida, em Arnie pode inserir uma linha para o cliente 4028. Arnie então abre a página **Liquidar transações**, dessa forma, ele pode marcar a fatura para liquidação. Alberto marca a fatura e altera o valor do campo **Valor a ser liquidado** para **500,00**. Novamente, ele vê que o valor do campo **Valor do desconto à vista** é **10,00** para a fatura total e que o valor do campo **Valor do desconto a vista a ser obtido** é **5,05**. Consequentemente, Arnie está liquidando 505,05 desta fatura.

| Marcar     | Usar desconto à vista | Comprovante   | Conta | Data      | Data de conclusão  | Fatura | Valor na moeda da transação | Moeda | Valor para liquidar |
|----------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------|----------|------------------|
| Selecionada | Normal            | FTI-10010 | 4028    | 25/6/2015 | 25/7/2015 | 10010   | 1.000,00                       | USD      | 500,00           |

As informações do desconto aparecem na parte inferior da página **Liquidar transações abertas**.

|                              |           |
|------------------------------|-----------|
| Data do desconto à vista           | 09/07/2015 |
| Valor de desconto à vista         | 10.00     |
| Usar desconto à vista            | Normal    |
| Desconto à vista obtido          | 0,00      |
| Valor do desconto à vista a ser obtido | 5,05      |

Se o cliente quiser liquidar exatamente a metade da fatura, ele enviará um pagamento de 495,00. Nesse caso, Alberto insere **495,00** no campo **Valor a ser liquidado**. O desconto à vista de 5,00, também será obtido, de forma que o valor liquidado total será de 500,00.

| Marcar     | Usar desconto à vista | Comprovante   | Conta | Data      | Data de conclusão  | Fatura | Valor na moeda da transação | Moeda | Valor para liquidar |
|----------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------|----------|------------------|
| Selecionada | Normal            | FTI-10010 | 4028    | 25/6/2015 | 25/7/2015 | 10010   | 1.000,00                       | USD      | 495.00           |

As informações do desconto aparecem na parte inferior da página **Liquidar transações abertas**.

|                              |           |
|------------------------------|-----------|
| Data do desconto à vista           | 09/07/2015 |
| Valor de desconto à vista         | 10.00     |
| Usar desconto à vista            | Normal    |
| Desconto à vista obtido          | 0,00      |
| Valor do desconto à vista a ser obtido | 5,00      |

Alberto fecha a página **Liquidar transações**. Uma linha de pagamento para 495,00 é criada no diário, e Arnie lança o diário. Ele pode examinar as transações do cliente na página **Transações do cliente**. Nessa página, Alberto vê que a fatura tem um saldo de 500,00. Também vê um pagamento de 495,00 e um desconto de 5,00.

| Comprovante    | Tipo de transação | Data      | Fatura | Valor em débito na moeda da transação | Valor em crédito na moeda da transação | Saldo | Moeda |
|------------|------------------|-----------|---------|--------------------------------------|---------------------------------------|---------|----------|
| FTI-10010  | Fatura          | 25/6/2015 | 10010   | 1.000,00                             |                                       | 500,00  | USD      |
| ARP-10010  |  Pagamento         | 01/07/2015  |         |                                      | 495.00                                | 0,00    | USD      |
| DISC-10010 |  Desconto à vista   | 01/07/2015  |         |                                      | 5,00                                  | 0,00    | USD      |

## <a name="payment-for-the-remaining-amount"></a>Pagamento do valor restante
O cliente 4028 paga o valor restante de 495,00 em 8 de julho, que está no período de desconto à vista. Arnie cria o diário de pagamentos em 8 de julho e marca a transação para liquidação. Ele vê que o valor que deve ser liquidado é de 495,00. O valor do campo **Desconto à vista estimado** é **5,00**, já que o desconto de 5,00 foi obtido anteriormente.

|                         |        |
|-------------------------|--------|
| Total marcado            | 495.00 |
| Estimativa de desconto em dinheiro | 5,00   |

As informações sobre a transação marcada aparecem na grade da página **Liquidar transações abertas**.

| Marcar     | Usar desconto à vista | Comprovante   | Conta | Data      | Data de conclusão  | Fatura | Valor na moeda da transação | Moeda | Valor para liquidar |
|----------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------|----------|------------------|
| Selecionada | Normal            | FTI-10010 | 4028    | 25/6/2015 | 25/7/2015 | 10010   | 1.000,00                       | USD      | 495.00           |

As informações do desconto aparecem na parte inferior da página **Liquidar transações abertas**.

|                              |           |
|------------------------------|-----------|
| Data do desconto à vista           | 09/07/2015 |
| Valor de desconto à vista         | 10.00     |
| Usar desconto à vista            | Normal    |
| Desconto à vista obtido          | 5,00      |
| Valor do desconto à vista a ser obtido | 5,00      |

Alberto lança esse diário e analisa e as transações do cliente na página **Transações do cliente**. O saldo da fatura agora é 0,00, e Arnie vê os dois pagamentos e os dois descontos à vista.

| Comprovante    | Tipo de transação | Data      | Fatura | Valor em débito na moeda da transação | Valor em crédito na moeda da transação | Saldo | Moeda |
|------------|------------------|-----------|---------|--------------------------------------|---------------------------------------|---------|----------|
| FTI-10010  | Fatura          | 25/6/2015 | 10010   | 1.000,00                             |                                       | 0,00    | USD      |
| ARP-10010  | Pagamento          | 01/07/2015  |         |                                      | 495,00                                | 0,00    | USD      |
| DISC-10010 | Desconto à vista    | 01/07/2015  |         |                                      | 5,00                                  | 0,00    | USD      |
| ARP-10011  | Pagamento          | 8/7/2015  |         |                                      | 495,00                                | 0,00    | USD      |
| DISC-10011 | Desconto à vista    | 8/7/2015  |         |                                      | 5,00                                  | 0,00    | USD      |




