---
title: Configurações de campo ausentes quando os grupos de modelos de item são copiados para outra entidade legal
description: Configurações de campo ausentes quando os grupos de modelos de item são copiados para outra entidade legal.
author: niwang
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: InventModelGroup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 6f6fdfef0bc377418ed8a9c8830e74526a0b95eb
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026264"
---
# <a name="missing-field-settings-when-item-model-groups-are-copied-to-another-legal-entity"></a>Configurações de campo ausentes quando os grupos de modelos de item são copiados para outra entidade legal

Número de KB: 4612800

## <a name="symptoms"></a>Sintomas

Ao copiar grupos de modelos de item para outra entidade legal (empresa) usando a entidade *Políticas de estoque do grupo de modelos de Item*, algumas configurações de campo (por exemplo, o modelo de estoque e a descrição) estão faltando no novo grupo de modelos da entidade legal de destino.

## <a name="resolution"></a>Resolução

Para criar uma cópia completa de um grupo de modelos de item para outra entidade legal, você também deve selecionar as políticas de estoque do grupo de modelos de item (`InventInventoryPolicyEntity`) e as diretivas de pressuposição de fluxo de custo (`InventCostFlowAssumptionPolicyEntity`) associadas ao grupo de modelos de item.
