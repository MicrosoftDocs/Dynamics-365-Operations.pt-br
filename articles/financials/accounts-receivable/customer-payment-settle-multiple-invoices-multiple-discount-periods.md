---
title: Usar um pagamento de cliente para liquidar várias faturas que abrangem vários períodos de desconto
description: Este tópico mostra como várias faturas são pagas quando cada fatura se qualifica para um desconto à vista. Os cenários neste artigo realçam como os descontos à vista efetuados podem variar, dependendo de quando o pagamento é efetuado.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 10/26/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustOpenTrans, LedgerJournalTransCustPaym
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 14511
ms.assetid: 3e42ccb5-b9d7-4a70-8db9-4206d10fd433
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c592034ca9c777bbc600c040c61937ad71b4e36d
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/01/2019
ms.locfileid: "1835085"
---
# <a name="use-a-customer-payment-to-settle-multiple-invoices-that-span-multiple-discount-periods"></a>Usar um pagamento de cliente para liquidar várias faturas que abrangem vários períodos de desconto

[!include [banner](../includes/banner.md)]

Este tópico mostra como várias faturas são pagas quando cada fatura se qualifica para um desconto à vista. Os cenários neste artigo realçam como os descontos à vista efetuados podem variar, dependendo de quando o pagamento é efetuado.

A Fabrikam vende produtos para o cliente 4032. Oferece um desconto à vista de 1 por cento se a fatura for paga em 14 dias. A Fabrikam também oferece descontos à vista para pagamentos parciais. Os parâmetros de pagamento estão localizados na página **Parâmetros de contas a receber**.

## <a name="invoices"></a>Faturas
O cliente 4032 possui três faturas que totalizam 3.000,00:

-   A fatura FTI-10040, de 1.000,00, foi inserida em 15 de maio. Essa fatura estará qualificada para um desconto à vista de 1% se for paga em 14 dias.
-   A fatura FTI-10041, de 1.000,00, foi inserida em 25 de junho. Essa fatura estará qualificada para um desconto à vista de 1% se for paga em 14 dias.
-   A fatura FTI-10042, de 1.000,00, foi inserida em 25 de junho. Essa fatura estará qualificada para um desconto à vista de 2% se for paga em cinco dias e um desconto de 1% se for paga em 14 dias.

## <a name="settle-all-invoices-on-june-29"></a>Liquidar todas as faturas em 29 de junho
Se Arnie criasse um diário de pagamento para liquidar totalmente essas faturas em 29 de junho, o pagamento seria de 2.970,00. O total de todos os valores de desconto seria de 30,00. Arnie cria um pagamento para o cliente 4032 e então abre a página **Liquidar transações**. Na página **Liquidar transações** Arnie marca as três linhas da fatura para o pagamento:

-   O pagamento da fatura FTI-10040 é de 1.000,00. Sem desconto à vista.
-   O pagamento da fatura FTI-10041 é de 990,00. Um desconto à vista de 1 por cento ou de 10,00 é obtido.
-   O pagamento da fatura FTI-10042 é de 980,00. Um desconto à vista de 2 por cento ou de 20,00 é obtido.

| Marcar                     | Usar desconto à vista | Comprovante   | Conta | Data      | Data de conclusão  | Fatura | Valor em débito na moeda da transação | Valor em crédito na moeda da transação | Moeda | Valor para liquidar |
|--------------------------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------------|---------------------------------------|----------|------------------|
| Selecionada                 | Normal            | FTI-10040 | 4032    | 15/5/2015 | 15/6/2015 | 10040   | 1.000,00                             |                                       | USD      | 1.000,00         |
| Selecionado                 | Normal            | FTI-10041 | 4032    | 25/6/2015 | 25/7/2015 | 10041   | 1.000,00                             |                                       | USD      | 990,00           |
| Selecionado e destacado | Normal            | FTI-10042 | 4032    | 25/6/2015 | 25/7/2015 | 10042   | 1.000,00                             |                                       | USD      | 980,00           |

Depois que o pagamento é lançado, o saldo do cliente é 0,00.

## <a name="settle-all-invoices-on-july-1"></a>Liquidar todas as faturas em 1 de julho
Se Arnie criasse um diário de pagamento para liquidar totalmente essas faturas em 1 de julho, o pagamento seria de 2.980,00. Arnie cria um pagamento para o cliente 4032 e então abre a página **Liquidar transações**. Na página **Liquidar transações** Arnie marca as três linhas da fatura para o pagamento:

-   O pagamento da fatura FTI-10040 é de 1.000,00. Sem desconto à vista.
-   O pagamento da fatura FTI-10041 é de 990,00. Um desconto à vista de 1 por cento ou de 10,00 é obtido.
-   O pagamento da fatura FTI-10042 é de 990,00. Um desconto à vista de 1 por cento ou de 10,00 é obtido. Embora 1º de julho seja depois do período qualificado para o desconto de 2%, a data ainda está no período qualificado para o desconto de 1%.

| Marcar                     | Usar desconto à vista | Comprovante   | Conta | Data      | Data de conclusão  | Fatura | Valor em débito na moeda da transação | Valor em crédito na moeda da transação | Moeda | Valor para liquidar |
|--------------------------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------------|---------------------------------------|----------|------------------|
| Selecionada                 | Normal            | FTI-10040 | 4032    | 15/5/2015 | 15/6/2015 | 10040   | 1.000,00                             |                                       | USD      | 1.000,00         |
| Selecionado                 | Normal            | FTI-10041 | 4032    | 25/6/2015 | 25/7/2015 | 10041   | 1.000,00                             |                                       | USD      | 990,00           |
| Selecionado e destacado | Normal            | FTI-10042 | 4032    | 25/6/2015 | 25/7/2015 | 10042   | 1.000,00                             |                                       | USD      | 990,00           |

## <a name="partial-settlement-on-june-29"></a>Liquidação parcial em 29 de junho
O cliente 4032 pode pagar um valor parcial, como a metade de cada fatura. Arnie cria um pagamento para o cliente 4032 e então abre a página **Liquidar transações**. Na página **Liquidar transações** Arnie marca as três linhas da fatura para o pagamento. Em cada linha, ele insere o valor a ser liquidado, com base nas instruções que o cliente forneceu. Quando Arnie seleciona uma linha, ele vê o valor do desconto dessa linha e o valor do desconto à vista que é obtido. Como o cliente está pagando a metade da fatura, Arnie vê que o valor do campo **Valor de desconto à vista** para FTI-10042 é **20,00**, mas o valor no campo **Desconto à vista obtido** é **10,00**. O valor do pagamento é 1.485,00.

| Marcar                     | Usar desconto à vista | Comprovante   | Conta | Data      | Data de conclusão  | Fatura | Valor em débito na moeda da transação | Valor em crédito na moeda da transação | Moeda | Valor para liquidar |
|--------------------------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------------|---------------------------------------|----------|------------------|
| Selecionada                 | Normal            | FTI-10040 | 4032    | 15/5/2015 | 15/6/2015 | 10040   | 1.000,00                             |                                       | USD      | 500,00           |
| Selecionado                 | Normal            | FTI-10041 | 4032    | 25/6/2015 | 25/7/2015 | 10041   | 1.000,00                             |                                       | USD      | 495.00           |
| Selecionado e destacado | Normal            | FTI-10042 | 4032    | 25/6/2015 | 25/7/2015 | 10042   | 1.000,00                             |                                       | USD      | 490,00           |

Arnie também pode inserir manualmente o valor do pagamento de 1.485,00 antes de abrir a página **Transações de liquidação**. Se Arnie inserir manualmente o valor do pagamento e, em seguida, marcar todas as três transações, mas não ajustar o valor no campo **Valor a ser liquidado** para cada transação, ele receberá a seguinte mensagem quando fechar a página:

> O valor total de transações marcadas é diferente do valor do diário. Alterar o valor do diário?

Se Arnie quiser que o valor do pagamento seja apenas de 1.485,00, ele clicará em **Não** e lançará o diário. As transações são liquidadas como se segue:

1.  O valor de 1.000,00 da fatura FTI-10040 é totalmente liquidado, pois a fatura foi inserida em 15 de maio e é a fatura mais antiga. Sem desconto à vista. O valor restante na transação de pagamento é de 485,00.
2.  A fatura FTI-10041 não será liquidada. As faturas FTI-10041 e FTI-10042 foram inseridas na mesma data. No entanto, um desconto de 1% está disponível para a fatura FTI-10041 e um desconto de 2% está disponível para a fatura FTI-10042. Como um desconto melhor está disponível para a fatura FTI-10042, os 485,00 restantes são liquidados com a fatura FTI-10042.
3.  A fatura FTI-10042 é liquidada com os 485,00 restantes. A Fabrikam oferece descontos parciais. Nesse caso, o desconto é 9,90 (= 485,00 × 0,02 ÷ de 0,98). O valor (485,00) é dividido por 0,98, porque há um desconto de 2% (portanto, o cliente paga 98% da fatura). O resultado é então multiplicado pela porcentagem de desconto, ou 2%. O pagamento de 485,00 mais o desconto de 9,90 é igual a 494,90. O valor da fatura original era de 1.000,00. Portanto, a transação tem um saldo de 505,10 (= 1.000,00 - 494,90).

Alberto exibe as informações na página **Transações do cliente**.

| Comprovante    | Tipo de transação | Data      | Fatura | Valor em débito na moeda da transação | Valor em crédito na moeda da transação | Saldo  | Moeda |
|------------|------------------|-----------|---------|--------------------------------------|---------------------------------------|----------|----------|
| FTI-10040  | Fatura          | 15/5/2015 | 10040   | 1.000,00                             |                                       | 0,00     | USD      |
| FTI-10041  | Fatura          | 25/6/2015 | 10041   | 1.000,00                             |                                       | 1.000,00 | USD      |
| FTI-10042  | Fatura          | 25/6/2015 | 10042   | 1.000,00                             |                                       | 505,10   | USD      |
| ARP-10040  | Pagamento          | 29/6/2015 |         |                                      | 1.485,00                              | 0,00     | USD      |
| DISC-10040 | Desconto à vista    | 29/6/2015 |         |                                      | 9.90                                  | 0,00     | USD      |





