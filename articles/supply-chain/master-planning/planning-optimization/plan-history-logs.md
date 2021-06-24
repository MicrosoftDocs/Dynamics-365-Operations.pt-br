---
title: Exibir logs de histórico de plano e de planejamento
description: Este tópico explica como exibir o histórico de trabalhos de planejamento disparados pela funcionalidade Otimização de Planejamento.
author: ChristianRytt
ms.date: 10/30/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: MPSPlanRegenerationJobList, MPSPlanRegenerationJobLogs
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: AX 10.0.5
ms.openlocfilehash: d7bba084b03f8698c8bf31d171d5e4e486ed06ad
ms.sourcegitcommit: a7649b361ec54b49c0e9ee1c1c63a8815f320225
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/04/2021
ms.locfileid: "6187238"
---
# <a name="view-plan-history-and-planning-logs"></a><span data-ttu-id="035d1-103">Exibir logs de histórico de plano e de planejamento</span><span class="sxs-lookup"><span data-stu-id="035d1-103">View plan history and planning logs</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="035d1-104">Este tópico explica como exibir o histórico de trabalhos de planejamento disparados pela funcionalidade Otimização de Planejamento no Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="035d1-104">This topic explains how to view the history of planning jobs that are triggered by the Planning Optimization functionality in Microsoft Dynamics 365 Supply Chain Management.</span></span>

<span data-ttu-id="035d1-105">Para exibir o histórico de um plano, abra o plano em **Planejamento mestre** \> **Configuração** \> **Planos** \> **Planos mestres** e selecione **Histórico**.</span><span class="sxs-lookup"><span data-stu-id="035d1-105">To view the history for a plan, open the plan by going to **Master planning** \> **Setup** \> **Plans** \> **Master plans** and selecting **History**.</span></span> <span data-ttu-id="035d1-106">O histórico lista todos os trabalhos do plano selecionado.</span><span class="sxs-lookup"><span data-stu-id="035d1-106">The history lists all the jobs for the selected plan.</span></span> <span data-ttu-id="035d1-107">A lista inclui os trabalhos concluídos e ativos.</span><span class="sxs-lookup"><span data-stu-id="035d1-107">The list includes completed and active jobs.</span></span>

<span data-ttu-id="035d1-108">O histórico dos trabalhos para execuções de planejamento mestre da Otimização de Planejamento mantém apenas até 60 registros por plano mestre.</span><span class="sxs-lookup"><span data-stu-id="035d1-108">The history of jobs for Planning Optimization master planning runs keeps only up to 60 records per master plan.</span></span> <span data-ttu-id="035d1-109">Sempre que você executa um novo cálculo de planejamento mestre, o registro histórico mais antigo desse plano é excluído.</span><span class="sxs-lookup"><span data-stu-id="035d1-109">Whenever you run a new master planning calculation, that plan's earliest history record is deleted.</span></span>

<span data-ttu-id="035d1-110">Além de verificar a hora inicial e o status de trabalhos, você pode exibir o log para um determinado trabalho.</span><span class="sxs-lookup"><span data-stu-id="035d1-110">In addition to seeing the start time and status of jobs, you can view the log for a specific job.</span></span> <span data-ttu-id="035d1-111">O log inclui informações e avisos adicionais.</span><span class="sxs-lookup"><span data-stu-id="035d1-111">The log includes additional information and warnings.</span></span> <span data-ttu-id="035d1-112">Nem todos os trabalhos têm um log.</span><span class="sxs-lookup"><span data-stu-id="035d1-112">Not all jobs have a log.</span></span> <span data-ttu-id="035d1-113">Para exibir o log para um trabalho, selecione **Log**.</span><span class="sxs-lookup"><span data-stu-id="035d1-113">To view the log for a job, select **Log**.</span></span> <span data-ttu-id="035d1-114">As entradas de registro só são armazenadas por 30 dias após a data de término do trabalho, depois disso, são automaticamente excluídas.</span><span class="sxs-lookup"><span data-stu-id="035d1-114">Log entries are only stored for 30 days after the date the job finished, after that they are automatically deleted.</span></span>

## <a name="related-resources"></a><span data-ttu-id="035d1-115">Recursos relacionados</span><span class="sxs-lookup"><span data-stu-id="035d1-115">Related resources</span></span>

- [<span data-ttu-id="035d1-116">Visão geral da Otimização do Planejamento</span><span class="sxs-lookup"><span data-stu-id="035d1-116">Planning Optimization overview</span></span>](planning-optimization-overview.md)
- [<span data-ttu-id="035d1-117">Introdução à Otimização do Planejamento</span><span class="sxs-lookup"><span data-stu-id="035d1-117">Get started with Planning Optimization</span></span>](get-started.md)
- [<span data-ttu-id="035d1-118">Análise de ajuste da Otimização de Planejamento</span><span class="sxs-lookup"><span data-stu-id="035d1-118">Planning Optimization fit analysis</span></span>](planning-optimization-fit-analysis.md)
- [<span data-ttu-id="035d1-119">Aplicar filtros a um plano</span><span class="sxs-lookup"><span data-stu-id="035d1-119">Apply filters to a plan</span></span>](plan-filters.md)
- [<span data-ttu-id="035d1-120">Cancelar um trabalho de planejamento</span><span class="sxs-lookup"><span data-stu-id="035d1-120">Cancel a planning job</span></span>](cancel-planning-job.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]