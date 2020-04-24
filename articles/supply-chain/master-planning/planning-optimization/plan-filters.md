---
title: Aplicar filtros a um plano
description: Este tópico explica como usar filtros em um plano quando a funcionalidade Otimização de Planejamento for usada.
author: ChristianRytt
manager: tfehr
ms.date: 01/08/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: AX 10.0.5
ms.openlocfilehash: 73e4a045ff5a9912b898a7115d3d8f530846ebdd
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/02/2020
ms.locfileid: "3209780"
---
# <a name="apply-filters-to-a-plan"></a><span data-ttu-id="c04a4-103">Aplicar filtros a um plano</span><span class="sxs-lookup"><span data-stu-id="c04a4-103">Apply filters to a plan</span></span>

[!include [banner](../../includes/preview-banner.md)]
[!include [banner](../../includes/banner.md)]

<span data-ttu-id="c04a4-104">Quando a funcionalidade Otimização de Planejamento for usada, você poderá aplicar um filtro a um plano.</span><span class="sxs-lookup"><span data-stu-id="c04a4-104">When the Planning Optimization functionality is used, you can apply a filter to a plan.</span></span> <span data-ttu-id="c04a4-105">O **Filtro do plano** sempre será aplicado durante uma execução de planejamento mestre.</span><span class="sxs-lookup"><span data-stu-id="c04a4-105">The **Plan filter** will always be applied during a master planning run.</span></span> <span data-ttu-id="c04a4-106">Um **Filtro do plano** é útil quando você deseja limitar um plano a um grupo de itens específico e garantir que nenhum outro item seja incluído como parte do planejamento mestre resultante.</span><span class="sxs-lookup"><span data-stu-id="c04a4-106">A **Plan filter** is useful when you want to limit a plan to a specific group of items and make sure that no other items are included as part of the resulting master planning.</span></span>

<span data-ttu-id="c04a4-107">Se um **Filtro do plano** for aplicado, e um filtro de runtime também for aplicado durante a execução do planejamento mestre, somente a interseção dos dois filtros será incluída na execução do planejamento.</span><span class="sxs-lookup"><span data-stu-id="c04a4-107">If a **Plan filter** is applied, and a runtime filter is also applied during the master planning run, only the intersection of the two filters is included in the planning run.</span></span>

<span data-ttu-id="c04a4-108">O **Filtro do plano** pode ser acessado dos **Planos mestre** quando a Otimização de Planejamento for usada.</span><span class="sxs-lookup"><span data-stu-id="c04a4-108">The **Plan filter** can be accessed from **Master plans** when Planning Optimization is used.</span></span>

## <a name="example-scenario"></a><span data-ttu-id="c04a4-109">Cenário de exemplo</span><span class="sxs-lookup"><span data-stu-id="c04a4-109">Example scenario</span></span>

<span data-ttu-id="c04a4-110">Um filtro de plano é configurado para incluir os itens A, B e C. Em seguida, são feitas execuções do planejamento mestre para o mesmo plano, mas filtros de runtime diferentes são aplicados:</span><span class="sxs-lookup"><span data-stu-id="c04a4-110">A plan filter is set up that includes items A, B, and C. Master planning runs are then run for the same plan, but different runtime filters are applied:</span></span>

- <span data-ttu-id="c04a4-111">**Filtro de runtime que inclui o item D:** nenhum item é planejado, já que não há interseção entre o filtro de plano e filtro de runtime.</span><span class="sxs-lookup"><span data-stu-id="c04a4-111">**Runtime filter that includes item D:** No items are planned, because there is no intersection between the plan filter and the runtime filter.</span></span>
- <span data-ttu-id="c04a4-112">**Filtro de runtime que inclui os itens A e D:** somente o item A é incluído na execução do planejamento, já que o item D não faz parte do filtro de plano.</span><span class="sxs-lookup"><span data-stu-id="c04a4-112">**Runtime filter that includes item A and D:** Only item A is included in the planning run, because item D isn't part of the plan filter.</span></span>
- <span data-ttu-id="c04a4-113">**Filtro de runtime que inclui o item B:** somente o item B é incluído na execução do planejamento, e a saída de planejamento anterior para o item A é mantida.</span><span class="sxs-lookup"><span data-stu-id="c04a4-113">**Runtime filter that includes item B:** Only item B is included in the planning run, and the previous planning output for item A is kept.</span></span>
- <span data-ttu-id="c04a4-114">**Filtro de runtime que inclui todos os itens (filtros em branco):** os itens A, B e C são incluídos na execução do planejamento, e a saída do planejamento anterior para os itens A e B é substituída.</span><span class="sxs-lookup"><span data-stu-id="c04a4-114">**Runtime filter that includes all items (blank filter):** Items A, B, and C are included in the planning run, and the previous planning output for items A and B is overwritten.</span></span>

> [!NOTE]
> <span data-ttu-id="c04a4-115">Você deve evitar definir um filtro de plano no plano selecionado como **Plano mestre dinâmico atual** na página **Parâmetros de planejamento mestre**.</span><span class="sxs-lookup"><span data-stu-id="c04a4-115">You should avoid setting a plan filter on the plan that is selected as **Current dynamic master plan** on the **Master planning parameters** page.</span></span> <span data-ttu-id="c04a4-116">Caso contrário, a funcionalidade de plano mestre dinâmico ficará limitada aos itens filtrados.</span><span class="sxs-lookup"><span data-stu-id="c04a4-116">Otherwise, the dynamic master plan functionality will be limited to the filtered items.</span></span> <span data-ttu-id="c04a4-117">Por exemplo, se os requisitos líquidos forem atualizados para um item e não fizerem parte do filtro de plano, nenhum resultado será gerado.</span><span class="sxs-lookup"><span data-stu-id="c04a4-117">For example, if the net requirements are updated for an item that isn't part of the plan filter, no result will be generated.</span></span>

## <a name="related-resources"></a><span data-ttu-id="c04a4-118">Recursos relacionados</span><span class="sxs-lookup"><span data-stu-id="c04a4-118">Related resources</span></span>

[<span data-ttu-id="c04a4-119">Visão geral da Otimização de Planejamento</span><span class="sxs-lookup"><span data-stu-id="c04a4-119">Planning Optimization overview</span></span>](planning-optimization-overview.md)

[<span data-ttu-id="c04a4-120">Introdução à Otimização de Planejamento</span><span class="sxs-lookup"><span data-stu-id="c04a4-120">Get started with Planning Optimization</span></span>](get-started.md)

[<span data-ttu-id="c04a4-121">Análise de ajuste da Otimização de Planejamento</span><span class="sxs-lookup"><span data-stu-id="c04a4-121">Planning Optimization fit analysis</span></span>](planning-optimization-fit-analysis.md)

[<span data-ttu-id="c04a4-122">Exibir logs de histórico de plano e de planejamento</span><span class="sxs-lookup"><span data-stu-id="c04a4-122">View plan history and planning logs</span></span>](plan-history-logs.md)

[<span data-ttu-id="c04a4-123">Cancelar um trabalho de planejamento</span><span class="sxs-lookup"><span data-stu-id="c04a4-123">Cancel a planning job</span></span>](cancel-planning-job.md)
