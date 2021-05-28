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
# <a name="cumulation-of-customer-rebates-fails-when-item-rebate-groups-are-used"></a><span data-ttu-id="29602-103">O acúmulo de descontos de clientes falha quando grupos de descontos de itens são usados</span><span class="sxs-lookup"><span data-stu-id="29602-103">Cumulation of customer rebates fails when item rebate groups are used</span></span>

<span data-ttu-id="29602-104">Número de KB: 4611372</span><span class="sxs-lookup"><span data-stu-id="29602-104">KB number: 4611372</span></span>

## <a name="symptoms"></a><span data-ttu-id="29602-105">Sintomas</span><span class="sxs-lookup"><span data-stu-id="29602-105">Symptoms</span></span>

<span data-ttu-id="29602-106">Quando você usa os contratos de reembolso do cliente (do tipo *valor*) em combinação com os grupos de reembolso do item, os reembolsos são calculados, mas o acúmulo falha.</span><span class="sxs-lookup"><span data-stu-id="29602-106">When you use customer rebate agreements (of the *amount* type) in combination with item rebate groups, rebates are calculated, but cumulation fails.</span></span>

## <a name="resolution"></a><span data-ttu-id="29602-107">Resolução</span><span class="sxs-lookup"><span data-stu-id="29602-107">Resolution</span></span>

<span data-ttu-id="29602-108">O sistema está agindo como esperado.</span><span class="sxs-lookup"><span data-stu-id="29602-108">The system is behaving as designed.</span></span> <span data-ttu-id="29602-109">Grupos de itens agrupar somente itens que tenham a mesma condição de limite.</span><span class="sxs-lookup"><span data-stu-id="29602-109">Item groups group only items that have the same threshold condition.</span></span> <span data-ttu-id="29602-110">A condição de reembolso (limite) é definida em relação ao valor de cada item, e não ao valor acumulado para qualquer item no grupo de itens.</span><span class="sxs-lookup"><span data-stu-id="29602-110">The rebate condition (threshold) is set against the amount for each item, not against the cumulated amount for any item in the item group.</span></span>
