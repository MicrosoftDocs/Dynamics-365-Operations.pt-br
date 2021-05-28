---
title: O pedido de compra planejado é criado quando uma compra existe em dias negativos
description: Se o código de cobertura for Mín/Máx, a Otimização de planejamento cria um pedido de compra planejado quando uma compra existe em dias negativos.
author: ChristianRytt
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: ReqTransPo,MpsIntegrationParameters
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: ilebedev
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 826496c2de956ff949dd79ab8aa643053719bf75
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026275"
---
# <a name="planned-purchase-order-is-created-when-a-purchase-exists-within-negative-days"></a><span data-ttu-id="3d281-103">O pedido de compra planejado é criado quando uma compra existe em dias negativos</span><span class="sxs-lookup"><span data-stu-id="3d281-103">Planned purchase order is created when a purchase exists within negative days</span></span>

<span data-ttu-id="3d281-104">Número da base de dados de conhecimento: 4614298</span><span class="sxs-lookup"><span data-stu-id="3d281-104">KB number: 4614298</span></span>

## <a name="symptoms"></a><span data-ttu-id="3d281-105">Sintomas</span><span class="sxs-lookup"><span data-stu-id="3d281-105">Symptoms</span></span>

<span data-ttu-id="3d281-106">Se o código de cobertura for *Mín/Máx*, a Otimização de planejamento cria um pedido de compra planejado quando uma compra existe em dias negativos.</span><span class="sxs-lookup"><span data-stu-id="3d281-106">If the coverage code is *Min/max*, Planning Optimization creates a planned purchase order when a purchase exists within negative days.</span></span>

## <a name="resolution"></a><span data-ttu-id="3d281-107">Resolução</span><span class="sxs-lookup"><span data-stu-id="3d281-107">Resolution</span></span>

<span data-ttu-id="3d281-108">A Otimização de planejamento não dá suporte a dias negativos.</span><span class="sxs-lookup"><span data-stu-id="3d281-108">Planning Optimization doesn't support negative days.</span></span> <span data-ttu-id="3d281-109">Entretanto, isso sempre garante que os pedidos planejados não serão agendados dentro do prazo relacionado à data atual.</span><span class="sxs-lookup"><span data-stu-id="3d281-109">However, it always ensures that planned orders won't be scheduled within the lead time relative to the current date.</span></span> <span data-ttu-id="3d281-110">Por exemplo, o prazo de compra é de 10 dias, e espera-se que um pedido de compra chegue 8 dias a contar de hoje.</span><span class="sxs-lookup"><span data-stu-id="3d281-110">For example, the purchase lead time is 10 days, and a purchase order is expected to arrive eight days from today.</span></span> <span data-ttu-id="3d281-111">Neste caso, o pedido de compra será usado como oferta para a demanda que é 5 dias a contar de hoje.</span><span class="sxs-lookup"><span data-stu-id="3d281-111">In this case, the purchase order will be used as supply for demand that is five days from today.</span></span>

<span data-ttu-id="3d281-112">Portanto, recomendamos que você ajuste seus prazos para cobrir todas (ou quase todas) as suas situações.</span><span class="sxs-lookup"><span data-stu-id="3d281-112">Therefore, we recommend that you adjust your lead times to cover all (or almost all) of your scenarios.</span></span>
