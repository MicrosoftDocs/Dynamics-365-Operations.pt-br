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
# <a name="late-selection-isnt-respected-when-production-orders-are-reset-via-a-batch-job"></a><span data-ttu-id="33378-103">A seleção em atraso não é respeitada quando os pedidos de produção são redefinidos por meio de um trabalho em lote</span><span class="sxs-lookup"><span data-stu-id="33378-103">Late selection isn't respected when production orders are reset via a batch job</span></span>

<span data-ttu-id="33378-104">Número da base de dados de conhecimento: 4614634</span><span class="sxs-lookup"><span data-stu-id="33378-104">KB number: 4614634</span></span>

## <a name="symptoms"></a><span data-ttu-id="33378-105">Sintomas</span><span class="sxs-lookup"><span data-stu-id="33378-105">Symptoms</span></span>

<span data-ttu-id="33378-106">Quando você usar um trabalho em lote recorrente para redefinir o status de um pedido de produção, as seleções em atraso não são respeitadas.</span><span class="sxs-lookup"><span data-stu-id="33378-106">When you use a recurring batch job to reset the status of a production order, late selections aren't respected.</span></span>

## <a name="resolution"></a><span data-ttu-id="33378-107">Resolução</span><span class="sxs-lookup"><span data-stu-id="33378-107">Resolution</span></span>

<span data-ttu-id="33378-108">O design atual não permite o uso de seleções em atraso para o processo *Redefinir status*.</span><span class="sxs-lookup"><span data-stu-id="33378-108">The current design doesn't support the use of late selections for the *Reset status* process.</span></span>
