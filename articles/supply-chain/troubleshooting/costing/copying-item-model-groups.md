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
# <a name="missing-field-settings-when-item-model-groups-are-copied-to-another-legal-entity"></a><span data-ttu-id="cbc1e-103">Configurações de campo ausentes quando os grupos de modelos de item são copiados para outra entidade legal</span><span class="sxs-lookup"><span data-stu-id="cbc1e-103">Missing field settings when item model groups are copied to another legal entity</span></span>

<span data-ttu-id="cbc1e-104">Número de KB: 4612800</span><span class="sxs-lookup"><span data-stu-id="cbc1e-104">KB number: 4612800</span></span>

## <a name="symptoms"></a><span data-ttu-id="cbc1e-105">Sintomas</span><span class="sxs-lookup"><span data-stu-id="cbc1e-105">Symptoms</span></span>

<span data-ttu-id="cbc1e-106">Ao copiar grupos de modelos de item para outra entidade legal (empresa) usando a entidade *Políticas de estoque do grupo de modelos de Item*, algumas configurações de campo (por exemplo, o modelo de estoque e a descrição) estão faltando no novo grupo de modelos da entidade legal de destino.</span><span class="sxs-lookup"><span data-stu-id="cbc1e-106">When you copy item model groups to another legal entity (company) by using the *Item model group inventory policies* entity, some field settings (for example, the inventory model and description) are missing in the new model group in the destination legal entity.</span></span>

## <a name="resolution"></a><span data-ttu-id="cbc1e-107">Resolução</span><span class="sxs-lookup"><span data-stu-id="cbc1e-107">Resolution</span></span>

<span data-ttu-id="cbc1e-108">Para criar uma cópia completa de um grupo de modelos de item para outra entidade legal, você também deve selecionar as políticas de estoque do grupo de modelos de item (`InventInventoryPolicyEntity`) e as diretivas de pressuposição de fluxo de custo (`InventCostFlowAssumptionPolicyEntity`) associadas ao grupo de modelos de item.</span><span class="sxs-lookup"><span data-stu-id="cbc1e-108">To create a complete copy of an item model group to another legal entity, you must also select both the item model group inventory policies (`InventInventoryPolicyEntity`) and the cost flow assumption policies (`InventCostFlowAssumptionPolicyEntity`) that are associated with the item model group.</span></span>
