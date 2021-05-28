---
title: A quantidade em um pedido de quarentena iniciado não é atualizado quando o pedido é dividido
description: Quando você cria um pedido de quarentena e tenta dividi-lo, a quantidade do pedido não é atualizada para a quantidade dividida restante.
author: niwang
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: InventQuarantineOrder
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: shawan
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: a8af535257ce217629d5ba92e624623c3ea39345
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026282"
---
# <a name="quantity-on-a-started-quarantine-order-isnt-updated-when-the-order-is-split"></a><span data-ttu-id="053dd-103">A quantidade em um pedido de quarentena iniciado não é atualizado quando o pedido é dividido</span><span class="sxs-lookup"><span data-stu-id="053dd-103">Quantity on a started quarantine order isn't updated when the order is split</span></span>

<span data-ttu-id="053dd-104">Número da base de dados de conhecimento: 4613113</span><span class="sxs-lookup"><span data-stu-id="053dd-104">KB number: 4613113</span></span>

## <a name="symptoms"></a><span data-ttu-id="053dd-105">Sintomas</span><span class="sxs-lookup"><span data-stu-id="053dd-105">Symptoms</span></span>

<span data-ttu-id="053dd-106">Quando você cria um pedido de quarentena e tenta dividi-lo, a quantidade do pedido não é atualizada para a quantidade restante após a divisão.</span><span class="sxs-lookup"><span data-stu-id="053dd-106">When you create a quarantine order and try to split it, the order quantity isn't updated to the remaining quantity after the split.</span></span>

## <a name="resolution"></a><span data-ttu-id="053dd-107">Resolução</span><span class="sxs-lookup"><span data-stu-id="053dd-107">Resolution</span></span>

<span data-ttu-id="053dd-108">O sistema não altera a quantidade original de um pedido de quarentena para garantir que você possa acompanhar a quantidade original que foi criada para esse pedido de quarentena.</span><span class="sxs-lookup"><span data-stu-id="053dd-108">The system doesn't change the original quantity from a quarantine order to ensure that you can track the original quantity that was created for that quarantine order.</span></span> <span data-ttu-id="053dd-109">No entanto, o sistema acompanha a quantidade que foi dividida de um pedido de quarentena.</span><span class="sxs-lookup"><span data-stu-id="053dd-109">However, the system does track the quantity that is split from a quarantine order.</span></span> <span data-ttu-id="053dd-110">Para fazer esse acompanhamento, ele usa um campo do banco de dados chamado `QuantityThatHasSplitIntoOtherQuarantineOrders`.</span><span class="sxs-lookup"><span data-stu-id="053dd-110">To do this tracking, it uses a database field that is named `QuantityThatHasSplitIntoOtherQuarantineOrders`.</span></span> <span data-ttu-id="053dd-111">No entanto, este campo não está visível na interface de usuário (UI).</span><span class="sxs-lookup"><span data-stu-id="053dd-111">However, this field isn't visible in the user interface (UI).</span></span>
