---
title: O acúmulo de descontos de clientes falha quando grupos de descontos de itens são usados
description: Quando você usa os contratos de reembolso de clientes em combinação com grupos de reembolso de itens, os descontos são calculados, mas o acúmulo falha.
author: sherry-zheng
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: PdsRebateTableListPage
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 5222d5a52a34ecfa4a1eac96a2cb561f257f17ea
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026259"
---
# <a name="cumulation-of-customer-rebates-fails-when-item-rebate-groups-are-used"></a>O acúmulo de descontos de clientes falha quando grupos de descontos de itens são usados

Número de KB: 4611372

## <a name="symptoms"></a>Sintomas

Quando você usa os contratos de reembolso do cliente (do tipo *valor*) em combinação com os grupos de reembolso do item, os reembolsos são calculados, mas o acúmulo falha.

## <a name="resolution"></a>Resolução

O sistema está agindo como esperado. Grupos de itens agrupar somente itens que tenham a mesma condição de limite. A condição de reembolso (limite) é definida em relação ao valor de cada item, e não ao valor acumulado para qualquer item no grupo de itens.
