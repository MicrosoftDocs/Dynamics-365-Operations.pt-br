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
ms.openlocfilehash: fc3381dab77cf80c0fd65f3bc27c11b814e72368631bd0e2145aac0be4f4fba4
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6760361"
---
# <a name="cumulation-of-customer-rebates-fails-when-item-rebate-groups-are-used"></a>O acúmulo de descontos de clientes falha quando grupos de descontos de itens são usados

Número de KB: 4611372

## <a name="symptoms"></a>Sintomas

Quando você usa os contratos de reembolso do cliente (do tipo *valor*) em combinação com os grupos de reembolso do item, os reembolsos são calculados, mas o acúmulo falha.

## <a name="resolution"></a>Resolução

O sistema está agindo como esperado. Grupos de itens agrupar somente itens que tenham a mesma condição de limite. A condição de reembolso (limite) é definida em relação ao valor de cada item, e não ao valor acumulado para qualquer item no grupo de itens.
