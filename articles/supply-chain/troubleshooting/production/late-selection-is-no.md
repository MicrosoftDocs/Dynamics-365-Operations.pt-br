---
title: A seleção em atraso não é respeitada quando os pedidos de produção são redefinidos por meio de um trabalho em lote
description: Quando você usar um trabalho em lote recorrente para redefinir o status de um pedido de produção, as seleções em atraso não são respeitadas.
author: johanhoffmann
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: ProdTableListPage
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 8800ec411ddd7ae73c5ac159592620a07b50c1e87938f823274ec24062c9a71a
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6741947"
---
# <a name="late-selection-isnt-respected-when-production-orders-are-reset-via-a-batch-job"></a>A seleção em atraso não é respeitada quando os pedidos de produção são redefinidos por meio de um trabalho em lote

Número da base de dados de conhecimento: 4614634

## <a name="symptoms"></a>Sintomas

Quando você usar um trabalho em lote recorrente para redefinir o status de um pedido de produção, as seleções em atraso não são respeitadas.

## <a name="resolution"></a>Resolução

O design atual não permite o uso de seleções em atraso para o processo *Redefinir status*.
