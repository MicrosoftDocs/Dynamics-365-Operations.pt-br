---
title: "Balanced diários da contabilidade interunidade"
description: "Este artigo mostra como um diário é automaticamente balanceado quando uma dimensão financeira de balanceamento estiver marcada na página do razão."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: LedgerParameters
audience: Application User
ms.reviewer: annbe
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 15791
ms.assetid: 301bd80e-f8b1-4f12-8194-e6d7de736084
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: 8b6fda79222905b0df211a0b944aca9e4dc76850
ms.lasthandoff: 03/31/2017


---

# <a name="balanced-journals-for-interunit-accounting"></a>Balanced diários da contabilidade interunidade

Este artigo mostra como um diário é automaticamente balanceado quando uma dimensão financeira de balanceamento estiver marcada na página do razão. 

Se as entradas de conta não estiverem equilibradas no nível dos valores de dimensão financeira, entradas adicionais de conta serão criadas automaticamente para equilibrar a entrada. Essas entradas de conta usam os tipos de contabilidade **Interunidade - débito** e** Interunidade - crédito** na página **Contas para transações automáticas** para determinar a conta principal. Por exemplo, a matriz, que é o segundo segmento da conta contábil, é selecionada como a dimensão financeira de balanceamento, e as seguintes entradas contábeis estão prestes a serem criadas.

|                      |           |
|----------------------|-----------|
| 6100 – MSP – OU o\_256 | 100.00 DR |
| 6100 – NY – OU o\_249  | 100.00 DR |
| 2100 – MSP – OU o\_256 | 200.00 CR |

Neste caso, os seguintes saldos são determinados:

-   Para Ramificação para o MSP = 100.00 CR
-   Para Ramificação para NY = 100.00 DR

No entanto, as seguintes entradas contábeis são criadas automaticamente para conferir a entrada no nível de valores de dimensão financeira.

|                                   |           |
|-----------------------------------|-----------|
| (Débito) de Interunit – MSP – OU o\_256 | 100.00 DR |
| (Crédito) de Interunit – NY – OU o\_249 | 100.00 CR |




