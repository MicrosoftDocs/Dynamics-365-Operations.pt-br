---
title: Cancelar um trabalho de planejamento
description: Este tópico explica como cancelar um trabalho de planejamento ativo que usa a funcionalidade de otimização do planejamento.
author: ChristianRytt
manager: AnnBe
ms.date: 10/26/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: AX 10.0.5
ms.openlocfilehash: a2d90f04985fdd66ca83582ee676100fffb26981
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/06/2019
ms.locfileid: "2773904"
---
[!include [banner](../../includes/banner.md)]
[!include [banner](../../includes/preview-banner.md)]

# <a name="cancel-a-planning-job"></a><span data-ttu-id="8dbc9-103">Cancelar um trabalho de planejamento</span><span class="sxs-lookup"><span data-stu-id="8dbc9-103">Cancel a planning job</span></span>

<span data-ttu-id="8dbc9-104">No Microsoft Dynamics 365 Supply Chain Management, você cancela um trabalho de planejamento ativo que usa a funcionalidade de otimização do planejamento.</span><span class="sxs-lookup"><span data-stu-id="8dbc9-104">In Microsoft Dynamics 365 Supply Chain Management, you can cancel an active planning job that uses the Planning Optimization functionality.</span></span>

<span data-ttu-id="8dbc9-105">Para cancelar um trabalho de planejamento ativo, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="8dbc9-105">To cancel an active planning job, follow these steps.</span></span>

> [!NOTE]
> <span data-ttu-id="8dbc9-106">Somente é possível cancelar trabalhos ativos.</span><span class="sxs-lookup"><span data-stu-id="8dbc9-106">Only active jobs can be canceled.</span></span>

1. <span data-ttu-id="8dbc9-107">Vá para **Planejamento mestre \> Configuração \> Planos**.</span><span class="sxs-lookup"><span data-stu-id="8dbc9-107">Go to **Master planning \> Setup \> Plans**.</span></span>
2. <span data-ttu-id="8dbc9-108">Selecione um plano apropriado para a execução do planejamento.</span><span class="sxs-lookup"><span data-stu-id="8dbc9-108">Select an appropriate plan for the planning run.</span></span>
3. <span data-ttu-id="8dbc9-109">Selecione **Histórico**.</span><span class="sxs-lookup"><span data-stu-id="8dbc9-109">Select **History**.</span></span>
4. <span data-ttu-id="8dbc9-110">Selecione o trabalho de planejamento a ser cancelado.</span><span class="sxs-lookup"><span data-stu-id="8dbc9-110">Select the planning job to cancel.</span></span>
5. <span data-ttu-id="8dbc9-111">Selecione **Cancelar**.</span><span class="sxs-lookup"><span data-stu-id="8dbc9-111">Select **Cancel**.</span></span>

<span data-ttu-id="8dbc9-112">O status do trabalho será **Cancelando** até o serviço de otimização do planejamento confirmar que o trabalho foi cancelado.</span><span class="sxs-lookup"><span data-stu-id="8dbc9-112">The job status will be **Canceling** until the Planning Optimization service confirms that the job has been canceled.</span></span> <span data-ttu-id="8dbc9-113">O status mudará para **Cancelado**.</span><span class="sxs-lookup"><span data-stu-id="8dbc9-113">The status will then be changed to **Canceled**.</span></span>

> [!NOTE]
> <span data-ttu-id="8dbc9-114">Para ver as alterações de status, atualize a página selecionando o botão **Atualizar**.</span><span class="sxs-lookup"><span data-stu-id="8dbc9-114">To see status changes, you must refresh the page by selecting the **Refresh** button.</span></span>

## <a name="related-resources"></a><span data-ttu-id="8dbc9-115">Recursos relacionados</span><span class="sxs-lookup"><span data-stu-id="8dbc9-115">Related resources</span></span>

[<span data-ttu-id="8dbc9-116">Visão geral da otimização do planejamento</span><span class="sxs-lookup"><span data-stu-id="8dbc9-116">Planning Optimization overview</span></span>](planning-optimization-overview.md)

[<span data-ttu-id="8dbc9-117">Introdução à Otimização de Planejamento</span><span class="sxs-lookup"><span data-stu-id="8dbc9-117">Get started with Planning Optimization</span></span>](get-started.md)

[<span data-ttu-id="8dbc9-118">Análise de ajuste da Otimização de Planejamento</span><span class="sxs-lookup"><span data-stu-id="8dbc9-118">Planning Optimization fit analysis</span></span>](planning-optimization-fit-analysis.md)

[<span data-ttu-id="8dbc9-119">Exibir logs de histórico de plano e de planejamento</span><span class="sxs-lookup"><span data-stu-id="8dbc9-119">View plan history and planning logs</span></span>](plan-history-logs.md)

[<span data-ttu-id="8dbc9-120">Aplicar filtros a um plano</span><span class="sxs-lookup"><span data-stu-id="8dbc9-120">Apply filters to a plan</span></span>](plan-filters.md)
