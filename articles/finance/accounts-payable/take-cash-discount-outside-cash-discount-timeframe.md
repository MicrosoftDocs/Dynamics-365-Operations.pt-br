---
title: Obter um desconto à vista fora do período de desconto à vista
description: Este artigo oferece dois cenários que mostram como um desconto à vista pode ser obtido mesmo se o pagamento for feito fora do período de desconto à vista.
author: angelad116
ms.date: 10/24/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerJournalTransVendPaym, VendOpenTrans
audience: Application User
ms.reviewer: twheeloc
ms.custom: 14301
ms.assetid: bad10b7f-e550-4742-9261-8a094c9c624d
ms.search.region: Global
ms.author: angelading
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 26b1eb5e542acf7496d1a0cf7196716a5de75e4e
ms.sourcegitcommit: cf6b764824bd1cf2c0dde6d37ddd0a7abab87ff0
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/16/2022
ms.locfileid: "9780445"
---
# <a name="take-a-cash-discount-outside-the-cash-discount-period"></a>Obter um desconto à vista fora do período de desconto à vista

[!include [banner](../includes/banner.md)]

Este artigo oferece dois cenários que mostram como um desconto à vista pode ser obtido mesmo se o pagamento for feito fora do período de desconto à vista.

Em 28 de junho, Amanda cria uma fatura de 2.000,00 para o fornecedor 3052. A fatura tem desconto à vista de 1 por cento se a fatura for paga em 14 dias.

## <a name="use-cash-discount-option--always"></a>Opção Usar desconto à vista = Sempre
Amanda cria um pagamento em 1º de julho, que é posterior à data do desconto. Alice abre a página **Liquidar transações** para exibir as transações que podem ser liquidadas. 

Alice marca a fatura para pagamento. Nenhum desconto à vista é obtido, pois o pagamento é feito após a data do desconto. Entretanto, o fornecedor deu a aprovação à Amanda para fazer o desconto em dinheiro de qualquer maneira. Sendo assim, Amanda altera o valor no campo **Usar desconto à vista** para **Sempre**.

| Marcar     | Usar desconto à vista | Comprovante   | Conta | Data do desconto à vista | Data de conclusão  | Fatura | Valor na moeda da transação | Moeda | Valor para liquidar |
|----------|-------------------|-----------|---------|--------------------|-----------|---------|--------------------------------|----------|------------------|
| Selecionados | Sempre            | Inv-10030 | 3052    | 28/6/2020          | 12/7/2020 | 10030   | -2.000,00                      | USD      | -1.980,00        |

As informações do desconto aparecem na parte inferior da página **Liquidar transações**.

| Campo                        | Valor     |
|------------------------------|-----------|
| Data do desconto à vista           | 12/7/2020 |
| Valor de desconto à vista         | -20,00    |
| Usar desconto à vista            | Sempre    |
| Desconto à vista obtido          | 0,00      |
| Valor do desconto à vista a ser obtido | -20,00    |

## <a name="date-to-use-for-calculating-discounts--selected-date"></a>Data a ser usada para calcular descontos = Data selecionada
Se a fatura e o pagamento tiverem sido lançados, o desconto à vista ainda poderá ser obtido quando as transações forem liquidadas na página **Liquidar transações**. Alice altera o valor no campo **Data a ser usada para calcular descontos** como **Data selecionada**. Ela então insere uma data 28 de junho, que está no período de desconto à vista para a fatura. Essa data é usada para calcular um desconto à vista para a transação. Na página **Liquidar transações abertas**, Alice vê que, por padrão, o desconto total de 20,00 aparece. A linha da fatura mostra que o valor a ser liquidado é de 1.980,00.

| Marcar          | Usar desconto à vista | Comprovante   | Conta | Data do desconto à vista | Data de conclusão  | Fatura | Valor na moeda da transação | Moeda | Valor para liquidar |
|--------------|-------------------|-----------|---------|--------------------|-----------|---------|--------------------------------|----------|------------------|
| Selecionado e destacado | Normal    | Inv-10030 | 3052    | 28/6/2020         | 12/7/2020 | 10030   | -2.000,00                      | USD      | -1.980,00        |
| Selecionados                 | Normal    | APP-10030 | 3052    | 15/7/2020          | 15/7/2020 |         | 500.00                         | USD      | 500.00           |

As informações do desconto aparecem na parte inferior da página **Liquidar transações abertas**. O valor do desconto a ser obtido é de 20,00, porque o valor a ser liquidado da fatura é o valor padrão, 1.980,00.

| Campo                        | Valor     |
|------------------------------|-----------|
| Data do desconto à vista           | 12/7/2020 |
| Valor de desconto à vista         | -20,00    |
| Usar desconto à vista            | Normal    |
| Desconto à vista obtido          | 0,00      |
| Valor do desconto à vista a ser obtido | -20,00    |

Alice atualiza o valor no campo **Valor a ser liquidado** para **-500,00**. O valor no campo **Valor do desconto à vista a ser obtido** é calculado como **5,05**.

| Marcar                     | Usar desconto à vista | Comprovante   | Conta | Data      | Data de conclusão  | Fatura | Valor na moeda da transação | Moeda | Valor para liquidar |
|--------------------------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------|----------|------------------|
| Selecionado e destacado | Normal            | Inv-10030 | 3052    | 28/6/2020 | 12/7/2020 | 10030   | 2,000.00                       | USD      | -500,00          |
| Selecionados                 | Normal            | APP-10030 | 3052    | 15/7/2020 | 15/7/2020 |         | 500.00                         | USD      | 500.00           |

As informações do desconto aparecem na parte inferior da página **Liquidar transações abertas**. O valor no campo **Valor do desconto à vista a ser obtida** é **5,05**, porque o valor a ser liquidado para a fatura foi alterado para o valor do pagamento, 500,00.

| Campo                        | Valor     |
|------------------------------|-----------|
| Data do desconto à vista           | 12/7/2020 |
| Valor de desconto à vista         | -20,00    |
| Usar desconto à vista            | Normal    |
| Desconto à vista obtido          | 0,00      |
| Valor do desconto à vista a ser obtido | -5,05     |







[!INCLUDE[footer-include](../../includes/footer-banner.md)]
