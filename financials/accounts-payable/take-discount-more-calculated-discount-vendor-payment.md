---
title: Obtenha um desconto maior do que o desconto calculado para um pagamento de fornecedor
description: "Este artigo percorre um cenário onde um desconto à vista é dado para um valor maior do que o desconto originalmente disponível na fatura. Esse cenário que pode ocorrer se uma organização firmar um contrato com o fornecedor para pagar um valor menor na fatura."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: LedgerJournalTransVendPaym, VendOpenTrans
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 14281
ms.assetid: 7f0a4197-95dd-4969-ade9-154815cf659e
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 08d7c4981aba7e7c092a6f21d3b63635e76437bf
ms.contentlocale: pt-br
ms.lasthandoff: 05/25/2017


---

# <a name="take-a-discount-that-is-more-than-the-calculated-discount-for-a-vendor-payment"></a>Obtenha um desconto maior do que o desconto calculado para um pagamento de fornecedor

[!include[banner](../includes/banner.md)]


Este artigo percorre um cenário onde um desconto à vista é dado para um valor maior do que o desconto originalmente disponível na fatura. Esse cenário que pode ocorrer se uma organização firmar um contrato com o fornecedor para pagar um valor menor na fatura. 

O fornecedor 3051 oferece à Fabrikam um desconto à vista de 4% se uma fatura for paga em sete dias. Em 29 de junho, Amanda insere uma fatura de 1.000,00. O fornecedor deixa Amanda obter um desconto de 60,00 em vez de o desconto padrão de 40,00 disponível para a fatura. Amanda registra um pagamento único usando o diário de pagamentos Contas a pagar. Ela entra no fornecedor para o pagamento e abre a página **Liquidar transações**. Ela marca a fatura e altera o valor no campo **Valor do desconto à vista** para **60,00**.
| Marcar     | Usar desconto à vista | Comprovante   | Conta | Data      | Data de conclusão  | Fatura | Valor na moeda da transação | Moeda | Valor para liquidar |
|----------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------|----------|------------------|
| Selecionada | Normal            | Inv-10040 | 3051    | 29/6/2015 | 29/7/2015 | 10040   | 1.000,00                       | USD      | 940,00           |

As informações do desconto aparecem na parte inferior da página **Liquidar transações**.
|                              |           |
|------------------------------|-----------|
| Data do desconto à vista           | 12/7/2015 |
| Valor de desconto à vista         | 60,00     |
| Usar desconto à vista            | Normal    |
| Desconto à vista obtido          | 0,00      |
| Valor do desconto à vista a ser obtido | 60,00     |

Amanda lança o diário de pagamentos. A fatura é totalmente liquidada usando um pagamento de 940,00 e um desconto de 60,00.




