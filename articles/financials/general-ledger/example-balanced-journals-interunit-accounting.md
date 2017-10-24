---
title: Entradas balanceadas para a contabilidade interunidade
description: "Este artigo mostra como um diário é automaticamente balanceado quando uma dimensão financeira de balanceamento estiver marcada na página do razão."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: LedgerParameters
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 15791
ms.assetid: 301bd80e-f8b1-4f12-8194-e6d7de736084
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: f45d180dc8dcafb0579e76b890dd5d516df5b8c0
ms.contentlocale: pt-br
ms.lasthandoff: 09/29/2017

---

# <a name="balanced-journals-for-interunit-accounting"></a>Entradas balanceadas para a contabilidade interunidade

[!include[banner](../includes/banner.md)]


Este artigo mostra como um diário é automaticamente balanceado quando uma dimensão financeira de balanceamento estiver marcada na página do razão. 

Se as entradas de conta não estiverem equilibradas no nível dos valores de dimensão financeira, entradas adicionais de conta serão criadas automaticamente para equilibrar a entrada. Essas entradas de conta usam os tipos de contabilidade **Interunidade - débito** e**Interunidade - crédito** na página **Contas para transações automáticas** para determinar a conta principal. Por exemplo, a matriz, que é o segundo segmento da conta contábil, é selecionada como a dimensão financeira de balanceamento, e as seguintes entradas contábeis estão prestes a serem criadas.

|                      |           |
|----------------------|-----------|
| 6100 – MSP – OU\_256 | 100.00 DR |
| 6100 – NY – OU\_249  | 100.00 DR |
| 2100 – MSP – OU\_256 | 200.00 CR |

Neste caso, os seguintes saldos são determinados:

-   Para Ramificação para o MSP = 100.00 CR
-   Para Ramificação para NY = 100.00 DR

No entanto, as seguintes entradas contábeis são criadas automaticamente para conferir a entrada no nível de valores de dimensão financeira.

|                                   |           |
|-----------------------------------|-----------|
| (Interunidade - débito) – OU\_256 | 100.00 DR |
| (Interunidade - Crédito) – NY – OU\_249 | 100.00 CR |






