---
title: "Liquidar um pagamento parcial de fornecedor com descontos em notas de crédito de fornecedor"
description: "Este artigo aborda um cenário onde um memorando de crédito é liquidado com relação a uma nota fiscal."
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
ms.custom: 14222
ms.assetid: 2b19f7fd-9ff9-4ee4-bddf-f582946d008e
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: 849cffa64eaf777f9f4c9243dab41b00fa59ad79
ms.lasthandoff: 03/31/2017


---

# <a name="settle-a-partial-vendor-payment-that-has-discounts-on-vendor-credit-notes"></a>Liquidar um pagamento parcial de fornecedor com descontos em notas de crédito de fornecedor

[!include[banner](../includes/banner.md)]


Este artigo aborda um cenário onde um memorando de crédito é liquidado com relação a uma nota fiscal.

Os fornecedores da Fabrikam fornecem descontos à vista em notas de crédito. O fornecedor 3050 permite que a Fabrikam obtenha um desconto à vista de 1% se uma fatura for paga em 14 dias.

## <a name="invoice-and-credit-memo"></a>Fatura e nota de crédito
Em 29 de junho, Amanda cria uma fatura de 1.000,00 para o fornecedor 3050. Em 2 de julho, ela cria uma nota de crédito de 200,00. Na página **Fornecedores**, Alice abre a página **Liquidar transações**. Ela pode usar a página **Liquidar transações** para marcar a nota de crédito e a fatura para liquidação. Um desconto de 2,00 é calculado na nota de crédito. Portanto, o valor total da nota de crédito é reduzido para 198,00.

| Marcar                     | Usar desconto à vista | Comprovante   | Conta | Data      | Data de conclusão  | Fatura | Valor na moeda da transação | Moeda | Valor para liquidar |
|--------------------------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------|----------|------------------|
| Selecionada                 | Normal            | Inv-10070 | 3050    | 29/6/2015 | 29/7/2015 | 10070   | -1.000,00                      | USD      | -990,00          |
| Selecionado e destacado | Normal            | CR-10070  | 3050    | 2/7/2015  | 29/7/2015 |         | 200,00                         | USD      | 198,00           |

As informações do desconto para a nota de crédito aparecem na parte inferior da página **Liquidar transações abertas**.

|                              |           |
|------------------------------|-----------|
| Data do desconto à vista           | 13/7/2015 |
| Valor de desconto à vista         | 2,00      |
| Usar desconto à vista            | Normal    |
| Desconto à vista obtido          | 0,00      |
| Valor do desconto à vista a ser obtido | 2,00      |

Alice clica em **Lançar**. Ela então analisa a liquidação concluída. Alice vê que 198,00 da nota de crédito foram aplicados e um desconto de 2,00 foi obtido. Portanto, o total é de 200,00.

| Marcar                     | Usar desconto à vista | Comprovante   | Conta | Data      | Data de conclusão  | Fatura  | Valor na moeda da transação | Moeda | Valor para liquidar |
|--------------------------|-------------------|-----------|---------|-----------|-----------|----------|--------------------------------|----------|------------------|
| Selecionado e destacado | Normal            | Inv-10070 | 3050    | 29/6/2015 | 29/7/2015 | 10070    | -1.000,00                      | USD      | -200,00          |
| Selecionado                 | Normal            | CR-10070  | 3050    | 2/7/2015  | 29/7/2015 | CR-10070 | 200,00                         | USD      | 198,00           |

Alice pode examinar as transações de fornecedor na página **Transações de fornecedor** ao selecionar um fornecedor na página **Todos os fornecedores **e, no Painel de Ação, clique em **Transações**. Nessa página, Alice vê que a fatura tem um saldo de -800,00. Ela também vê uma nota de crédito de 198,00 e um desconto de 2,00.

| Comprovante    | Tipo de transação | Data      | Fatura | Valor em débito na moeda da transação | Valor em crédito na moeda da transação | Saldo | Moeda |
|------------|------------------|-----------|---------|--------------------------------------|---------------------------------------|---------|----------|
| Inv-10070  | Fatura          | 29/6/2015 | 10070   |                                      | 1.000,00                              | -800,00 | USD      |
| Inv-10071  |                  | 2/7/2015  | CR10071 | 200,00                               |                                       | 0,00    | USD      |
| DISC-10071 |  Desconto à vista   | 2/7/2015  |         | 2,00                                 |                                       | 0,00    | USD      |
| DISC-10071 |  Desconto à vista   | 2/7/2015  |         |                                      | 2,00                                  | 0,00    | USD      |





