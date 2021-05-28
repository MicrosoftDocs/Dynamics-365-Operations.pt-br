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
ms.openlocfilehash: e53198f427f4060421a4f0078277682c43db1320
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026263"
---
# <a name="late-selection-isnt-respected-when-production-orders-are-reset-via-a-batch-job"></a>A seleção em atraso não é respeitada quando os pedidos de produção são redefinidos por meio de um trabalho em lote

Número da base de dados de conhecimento: 4614634

## <a name="symptoms"></a>Sintomas

Quando você usar um trabalho em lote recorrente para redefinir o status de um pedido de produção, as seleções em atraso não são respeitadas.

## <a name="resolution"></a>Resolução

O design atual não permite o uso de seleções em atraso para o processo *Redefinir status*.
