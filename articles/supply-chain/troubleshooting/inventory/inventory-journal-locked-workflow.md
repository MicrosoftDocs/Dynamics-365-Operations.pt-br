---
title: O diário de estoque está bloqueado, e o trabalho em lote do fluxo de trabalho não funciona
description: Um dos diários de estoque está bloqueado por alguma operação e não está sendo liberado
author: sherry-zheng
ms.date: 05/31/2021
ms.topic: troubleshooting
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.16
ms.openlocfilehash: 8b21ec2e2b3b8546dcb138422c5540053392c179
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2021
ms.locfileid: "7475553"
---
# <a name="your-inventory-journal-is-locked-and-the-workflow-batch-job-doesnt-work"></a>O diário de estoque está bloqueado, e o trabalho em lote do fluxo de trabalho não funciona

## <a name="symptoms"></a>Sintomas

Um dos diários de estoque está bloqueado por alguma operação e não está sendo liberado. Por exemplo, se um erro desconhecido ocorrer durante o lançamento (que é uma operação de bloqueio do sistema), o diário poderá permanecer no status bloqueado pelo sistema. Nesse caso, o manipulador de itens de trabalho do fluxo de trabalho lançará um erro enquanto realiza a validação do bloqueio.

## <a name="resolution"></a>Resolução

Entre na instância do SQL Server para Supply Chain Management e verifique se **InventJournalTable.SystemBlocked** está definido como *1*. Se estiver, verifique se o diário não deve estar no status bloqueado e redefina **InventJournalTable.SystemBlocked** como *0*.
