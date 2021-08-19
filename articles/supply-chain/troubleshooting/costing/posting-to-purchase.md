---
title: O acúmulo da compra que tem quantidade de valor zero é postado para um recibo de produto de valor zero
description: Quando um recibo de produto que tem valor zero é postado, o sistema cria uma postagem para o acúmulo de compra em que o valor é 0 (zero).
author: niwang
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: LedgerTransVoucher
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 304609e065389d4f56913ae3f2f7fc562de2eadc9f0885ddbe2c8f4747081c66
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6722166"
---
# <a name="purchase-accrual-that-has-a-zero-amount-is-posted-for-a-zero-value-product-receipt"></a>O acúmulo da compra que tem quantidade de valor zero é postado para um recibo de produto de valor zero

Número da base de dados de conhecimento: 4612588

## <a name="symptoms"></a>Sintomas

Quando um recibo de produto que tem valor zero é postado, o sistema cria uma postagem para o acúmulo de compra em que o valor é 0 (zero).

## <a name="resolution"></a>Resolução

Por padrão, para postagens do razão do tipo *Compra, acúmulo*, o campo `IsTransferredIndetail` sempre é definido como *Resumo* nas transações do razão auxiliar. Portanto, o sistema cria uma entrada de comprovante relacionada mesmo que o valor seja 0 (zero).

Para ignorar este tipo de postagem quando o valor for 0 (zero), estenda o método `subledgerJournalizer.markDoNotTransferEntries` para que ele inclua `ledgerPostingType = PurchPckSlpPurchaseOffsetAccount`, conforme mostrado no seguinte exemplo.

```xpp
update_recordset existingSubledgerJournalAccountEntry
setting
    IsTransferredInDetail = TransferPolicy::DoNotTransfer
where existingSubledgerJournalAccountEntry.SubledgerJournalEntry == _subledgerJournalEntryRecId
    && (existingSubledgerJournalAccountEntry.AccountingCurrencyAmount == 0 && existingSubledgerJournalAccountEntry.ReportingCurrencyAmount == 0)
    && existingSubledgerJournalAccountEntry.PostingType == LedgerPostingType::PurchPckSlpPurchaseOffsetAccount;
```
