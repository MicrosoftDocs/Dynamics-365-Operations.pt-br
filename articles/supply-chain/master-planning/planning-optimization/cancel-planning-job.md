---
title: Cancelar um trabalho de planejamento
description: Este tópico explica como cancelar um trabalho de planejamento ativo que usa a funcionalidade de otimização do planejamento.
author: ChristianRytt
ms.date: 02/18/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: AX 10.0.5
ms.openlocfilehash: e9cf4902251c3c2b93af12a8ad9bd571930ef769
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5833320"
---
# <a name="cancel-a-planning-job"></a><span data-ttu-id="7df6d-103">Cancelar um trabalho de planejamento</span><span class="sxs-lookup"><span data-stu-id="7df6d-103">Cancel a planning job</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="7df6d-104">No Microsoft Dynamics 365 Supply Chain Management, você cancela um trabalho de planejamento ativo que usa a funcionalidade de otimização do planejamento.</span><span class="sxs-lookup"><span data-stu-id="7df6d-104">In Microsoft Dynamics 365 Supply Chain Management, you can cancel an active planning job that uses the Planning optimization functionality.</span></span> <span data-ttu-id="7df6d-105">Ao selecionar **Cancelar** na caixa de diálogo quando um trabalho de otimização de planejamento é acionado diretamente da interface do usuário (não em segundo plano), isso não cancelará o trabalho de otimização de planejamento.</span><span class="sxs-lookup"><span data-stu-id="7df6d-105">When you select **Cancel** in the dialog box when a Planning optimization job is triggered directly from the user interface (not in the background), this will not cancel the Planning optimization job.</span></span> <span data-ttu-id="7df6d-106">Mesmo se você receber um aviso como “Operação cancelada”, ainda será necessário seguir as etapas abaixo para cancelar um trabalho de planejamento com a otimização de planejamento.</span><span class="sxs-lookup"><span data-stu-id="7df6d-106">Even if you receive a warning such as “Operation canceled”, you will still need to use the following steps to cancel a planning job with Planning optimization.</span></span>


<span data-ttu-id="7df6d-107">Para cancelar um trabalho de planejamento ativo, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="7df6d-107">To cancel an active planning job, follow these steps.</span></span> 

> [!NOTE]
> <span data-ttu-id="7df6d-108">Somente é possível cancelar trabalhos ativos.</span><span class="sxs-lookup"><span data-stu-id="7df6d-108">Only active jobs can be canceled.</span></span>

1. <span data-ttu-id="7df6d-109">Vá para **Planejamento mestre \> Configuração \> Planos**.</span><span class="sxs-lookup"><span data-stu-id="7df6d-109">Go to **Master planning \> Setup \> Plans**.</span></span>
2. <span data-ttu-id="7df6d-110">Selecione um plano apropriado para a execução do planejamento.</span><span class="sxs-lookup"><span data-stu-id="7df6d-110">Select an appropriate plan for the planning run.</span></span>
3. <span data-ttu-id="7df6d-111">Selecione **Histórico**.</span><span class="sxs-lookup"><span data-stu-id="7df6d-111">Select **History**.</span></span>
4. <span data-ttu-id="7df6d-112">Selecione o trabalho de planejamento a ser cancelado.</span><span class="sxs-lookup"><span data-stu-id="7df6d-112">Select the planning job to cancel.</span></span>
5. <span data-ttu-id="7df6d-113">Selecione **Cancelar**.</span><span class="sxs-lookup"><span data-stu-id="7df6d-113">Select **Cancel**.</span></span>

<span data-ttu-id="7df6d-114">O status do trabalho será **Cancelando** até o serviço de otimização do planejamento confirmar que o trabalho foi cancelado.</span><span class="sxs-lookup"><span data-stu-id="7df6d-114">The job status will be **Canceling** until the Planning Optimization service confirms that the job has been canceled.</span></span> <span data-ttu-id="7df6d-115">O status mudará para **Cancelado**.</span><span class="sxs-lookup"><span data-stu-id="7df6d-115">The status will then be changed to **Canceled**.</span></span>

> [!NOTE]
> <span data-ttu-id="7df6d-116">Para ver as alterações de status, atualize a página selecionando o botão **Atualizar**.</span><span class="sxs-lookup"><span data-stu-id="7df6d-116">To see status changes, you must refresh the page by selecting the **Refresh** button.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="7df6d-117">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="7df6d-117">Additional resources</span></span>

[<span data-ttu-id="7df6d-118">Visão geral de Otimização do Planejamento</span><span class="sxs-lookup"><span data-stu-id="7df6d-118">Planning Optimization overview</span></span>](planning-optimization-overview.md)

[<span data-ttu-id="7df6d-119">Introdução à Otimização de Planejamento</span><span class="sxs-lookup"><span data-stu-id="7df6d-119">Get started with Planning Optimization</span></span>](get-started.md)

[<span data-ttu-id="7df6d-120">Análise de ajuste da Otimização de Planejamento</span><span class="sxs-lookup"><span data-stu-id="7df6d-120">Planning Optimization fit analysis</span></span>](planning-optimization-fit-analysis.md)

[<span data-ttu-id="7df6d-121">Exibir logs de histórico de plano e de planejamento</span><span class="sxs-lookup"><span data-stu-id="7df6d-121">View plan history and planning logs</span></span>](plan-history-logs.md)

[<span data-ttu-id="7df6d-122">Aplicar filtros a um plano</span><span class="sxs-lookup"><span data-stu-id="7df6d-122">Apply filters to a plan</span></span>](plan-filters.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]