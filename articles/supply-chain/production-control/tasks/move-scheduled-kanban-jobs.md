--- 
title: Mover trabalhos kanban agendados
description: "Esse procedimento se concentra nesses trabalhos kanban de processo planejados para um período diferente."
author: ChristianRytt
manager: AnnBe
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 2a12a6859a3a436706822873bc6fdd781e0ef032
ms.contentlocale: pt-br
ms.lasthandoff: 08/29/2017

---
# <a name="move-scheduled-kanban-jobs"></a><span data-ttu-id="6320b-103">Mover trabalhos kanban agendados</span><span class="sxs-lookup"><span data-stu-id="6320b-103">Move scheduled kanban jobs</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="6320b-104">Esse procedimento se concentra nesses trabalhos kanban de processo planejados para um período diferente.</span><span class="sxs-lookup"><span data-stu-id="6320b-104">This procedure focuses on moving planned process kanban jobs to a different period.</span></span> <span data-ttu-id="6320b-105">A empresa de dados demo usada para criar este procedimento é USMF.</span><span class="sxs-lookup"><span data-stu-id="6320b-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="6320b-106">Este procedimento está direcionada para o supervisor de chão de fábrica ou o planejador de produção que estão trabalhando com kanbans.</span><span class="sxs-lookup"><span data-stu-id="6320b-106">This procedure is intended for the shop floor supervisor or production planner working with kanbans.</span></span>


## <a name="select-scheduled-kanban-jobs"></a><span data-ttu-id="6320b-107">Selecionar trabalhos kanban agendados</span><span class="sxs-lookup"><span data-stu-id="6320b-107">Select scheduled kanban jobs</span></span>
1. <span data-ttu-id="6320b-108">Gå til Produktionsstyring > Kanban > Tidsplanlægning af kanban-job.</span><span class="sxs-lookup"><span data-stu-id="6320b-108">Gå til Produktionsstyring > Kanban > Tidsplanlægning af kanban-job.</span></span>
2. <span data-ttu-id="6320b-109">!MtCMR!No campo Célula de trabalho, clique no botão suspenso para abrir a busca.</span><span class="sxs-lookup"><span data-stu-id="6320b-109">!MtCMR!In the Work cell field, click the drop-down button to open the lookup.</span></span> <span data-ttu-id="6320b-110">áçêìõý!</span><span class="sxs-lookup"><span data-stu-id="6320b-110">áçêìõý !</span></span>
3. <span data-ttu-id="6320b-111">Markér den valgte række på listen.</span><span class="sxs-lookup"><span data-stu-id="6320b-111">Markér den valgte række på listen.</span></span>
    * <span data-ttu-id="6320b-112">Selecione a célula de trabalho 1250.</span><span class="sxs-lookup"><span data-stu-id="6320b-112">Select work cell 1250.</span></span>  
4. <span data-ttu-id="6320b-113">Klik på Select.</span><span class="sxs-lookup"><span data-stu-id="6320b-113">Klik på Select.</span></span>
5. <span data-ttu-id="6320b-114">Vælg 'Planlagt' i feltet Display job status.</span><span class="sxs-lookup"><span data-stu-id="6320b-114">Vælg 'Planlagt' i feltet Display job status.</span></span>
    * <span data-ttu-id="6320b-115">Isso filtra a lista de trabalho para exibir somente os trabalhos kanban programados.</span><span class="sxs-lookup"><span data-stu-id="6320b-115">This filters the job list to display only the scheduled kanban jobs.</span></span>  

## <a name="move-kanban-jobs-to-a-different-period"></a><span data-ttu-id="6320b-116">Mover trabalhos kanban a um período diferente</span><span class="sxs-lookup"><span data-stu-id="6320b-116">Move kanban jobs to a different period</span></span>
1. <span data-ttu-id="6320b-117">Find og vælg den ønskede post på listen.</span><span class="sxs-lookup"><span data-stu-id="6320b-117">Find og vælg den ønskede post på listen.</span></span>
    * <span data-ttu-id="6320b-118">Selecione um trabalho que tenha o status de Trabalho planejado, por exemplo, um trabalho programado em 20 de dezembro de 2012 no campo Período planejado.</span><span class="sxs-lookup"><span data-stu-id="6320b-118">Select a job that has the Planned job status, for example, a job scheduled on December 20, 2012  in the Planned period field.</span></span> <span data-ttu-id="6320b-119">Então mova o trabalho para o período anterior.</span><span class="sxs-lookup"><span data-stu-id="6320b-119">Then move the job to the previous period.</span></span>  
2. <span data-ttu-id="6320b-120">Klik på Previous period.</span><span class="sxs-lookup"><span data-stu-id="6320b-120">Klik på Previous period.</span></span>
3. <span data-ttu-id="6320b-121">Klik på End.</span><span class="sxs-lookup"><span data-stu-id="6320b-121">Klik på End.</span></span>
    * <span data-ttu-id="6320b-122">Isso moverá o trabalho para o final da lista de trabalho como o último trabalho no período anterior.</span><span class="sxs-lookup"><span data-stu-id="6320b-122">This will move the job to the end of the job list as the last job in the previous period.</span></span>  
4. <span data-ttu-id="6320b-123">Find og vælg den ønskede post på listen.</span><span class="sxs-lookup"><span data-stu-id="6320b-123">Find og vælg den ønskede post på listen.</span></span>
    * <span data-ttu-id="6320b-124">Selecione um trabalho que tenha o status de Trabalho planejado, por exemplo, um trabalho programado em 18 de dezembro de 2012 no campo Período planejado.</span><span class="sxs-lookup"><span data-stu-id="6320b-124">Select a job that has the Planned job status, for example, a job scheduled on December 18, 2012 in the Planned period field.</span></span> <span data-ttu-id="6320b-125">Então mova o trabalho para o próximo período.</span><span class="sxs-lookup"><span data-stu-id="6320b-125">Then move the job to the next period.</span></span>  
5. <span data-ttu-id="6320b-126">Klik på Next period.</span><span class="sxs-lookup"><span data-stu-id="6320b-126">Klik på Next period.</span></span>
6. <span data-ttu-id="6320b-127">Klik på Start.</span><span class="sxs-lookup"><span data-stu-id="6320b-127">Klik på Start.</span></span>
    * <span data-ttu-id="6320b-128">Isso moverá o trabalho para o início da lista de trabalho como o primeiro trabalho no período anterior.</span><span class="sxs-lookup"><span data-stu-id="6320b-128">This will move the job to the start of the job list as the first job in the previous period.</span></span>  

## <a name="task-move-a-job-within-a-period"></a><span data-ttu-id="6320b-129">Tarefas: Mover um trabalho em um período</span><span class="sxs-lookup"><span data-stu-id="6320b-129">Task: Move a job within a period</span></span>
1. <span data-ttu-id="6320b-130">Find og vælg den ønskede post på listen.</span><span class="sxs-lookup"><span data-stu-id="6320b-130">Find og vælg den ønskede post på listen.</span></span>
    * <span data-ttu-id="6320b-131">Selecione um trabalho que tenha o status de Trabalho planejado, por exemplo, o segundo trabalho programado em 19 de dezembro de 2012 no campo Período planejado.</span><span class="sxs-lookup"><span data-stu-id="6320b-131">Select a job that has the Planned job status, for example, the second job scheduled on December 19, 2012 in the Planned period field.</span></span> <span data-ttu-id="6320b-132">Então mova o trabalho para o período planejado.</span><span class="sxs-lookup"><span data-stu-id="6320b-132">Then move the job within the planned period.</span></span>  
2. <span data-ttu-id="6320b-133">Klik på Forward.</span><span class="sxs-lookup"><span data-stu-id="6320b-133">Klik på Forward.</span></span>
    * <span data-ttu-id="6320b-134">Observe que os trabalhos são movidos para uma linha abaixo na lista.</span><span class="sxs-lookup"><span data-stu-id="6320b-134">Notice that the job is moved one line down on the list.</span></span>  
3. <span data-ttu-id="6320b-135">Klik på Backward.</span><span class="sxs-lookup"><span data-stu-id="6320b-135">Klik på Backward.</span></span>
    * <span data-ttu-id="6320b-136">Observe que os trabalhos são movidos para uma linha acima na lista.</span><span class="sxs-lookup"><span data-stu-id="6320b-136">Notice that the job is moved one line up on the list.</span></span>  


