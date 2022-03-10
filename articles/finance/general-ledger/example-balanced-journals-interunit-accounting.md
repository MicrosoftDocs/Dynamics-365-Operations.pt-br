---
title: Entradas balanceadas para a contabilidade interunidade
description: Este artigo mostra como um diário é automaticamente balanceado quando uma dimensão financeira de balanceamento estiver marcada na página do razão.
author: kweekley
ms.date: 10/30/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerParameters
audience: Application User
ms.reviewer: roschlom
ms.custom: 15791
ms.assetid: 301bd80e-f8b1-4f12-8194-e6d7de736084
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7f6ffccb2ee504f182250dbf6d316823efafddf5
ms.sourcegitcommit: 4f8465729d7ae0bf5150a2785a6140c984c7030e
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/31/2021
ms.locfileid: "7726885"
---
# <a name="balanced-journals-for-interunit-accounting"></a>Entradas balanceadas para a contabilidade interunidade

[!include [banner](../includes/banner.md)]

Este artigo mostra como um diário é automaticamente balanceado quando uma dimensão financeira de balanceamento estiver marcada na página do razão. 

Se as entradas de conta não estiverem equilibradas no nível dos valores de dimensão financeira, entradas adicionais de conta serão criadas automaticamente para equilibrar a entrada. Essas entradas de conta usam os tipos de contabilidade **Interunidade - débito** e **Interunidade - crédito** na página **Contas para transações automáticas** para determinar a conta principal. Por exemplo, a unidade de negócios, que é o segundo segmento da conta contábil, é selecionada como a dimensão financeira de balanço, e as entradas contábeis a seguir estão prestes a serem criadas.

| &nbsp;               | &nbsp;    |
|----------------------|-----------|
| 6100 – MSP – OU\_256 | 100.00 DR |
| 6100 – NY – OU\_249  | 100.00 DR |
| 2100 – MSP – OU\_256 | 200.00 CR |

Neste caso, os seguintes saldos são determinados:

-   Para unidade de negócios, MSP = 100.00 CR
-   Para unidade de negócios, NY = 100.00 DR

No entanto, as seguintes entradas contábeis são criadas automaticamente para conferir a entrada no nível de valores de dimensão financeira.

| &nbsp;                            | &nbsp;    |
|-----------------------------------|-----------|
| (Interunidade - débito) – OU\_256 | 100.00 DR |
| (Interunidade - Crédito) – NY – OU\_249 | 100.00 CR |







[!INCLUDE[footer-include](../../includes/footer-banner.md)]
