---
title: Mover trabalhos kanban agendados
description: Esse procedimento se concentra nesses trabalhos kanban de processo planejados para um período diferente.
author: ChristianRytt
manager: AnnBe
ms.date: 11/07/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KanbanJobSchedulingListPage
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f791c9048ef6efe1585c991f998099cd1fc12df7
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2019
ms.locfileid: "310843"
---
# <a name="move-scheduled-kanban-jobs"></a><span data-ttu-id="c40e0-103">Mover trabalhos kanban agendados</span><span class="sxs-lookup"><span data-stu-id="c40e0-103">Move scheduled kanban jobs</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="c40e0-104">Esse procedimento se concentra nesses trabalhos kanban de processo planejados para um período diferente.</span><span class="sxs-lookup"><span data-stu-id="c40e0-104">This procedure focuses on moving planned process kanban jobs to a different period.</span></span> <span data-ttu-id="c40e0-105">A empresa de dados demo usada para criar este procedimento é USMF.</span><span class="sxs-lookup"><span data-stu-id="c40e0-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="c40e0-106">Este procedimento está direcionada para o supervisor de chão de fábrica ou o planejador de produção que estão trabalhando com kanbans.</span><span class="sxs-lookup"><span data-stu-id="c40e0-106">This procedure is intended for the shop floor supervisor or production planner working with kanbans.</span></span>

## <a name="select-scheduled-kanban-jobs"></a><span data-ttu-id="c40e0-107">Selecionar trabalhos kanban agendados.</span><span class="sxs-lookup"><span data-stu-id="c40e0-107">Select scheduled kanban jobs.</span></span> 

1. <span data-ttu-id="c40e0-108">Vá para **Controle de produção > Kanban > Agendamento de trabalho Kanban**.</span><span class="sxs-lookup"><span data-stu-id="c40e0-108">Go to **Production control > Kanban > Kanban job scheduling**.</span></span> 

2. <span data-ttu-id="c40e0-109">No campo **Célula de trabalho**, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="c40e0-109">In the **Work cell** field, click the drop-down button to open the lookup.</span></span> 

3. <span data-ttu-id="c40e0-110">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="c40e0-110">In the list, mark the selected row.</span></span> 
   - <span data-ttu-id="c40e0-111">Selecione a célula de trabalho 1250.</span><span class="sxs-lookup"><span data-stu-id="c40e0-111">Select work cell 1250.</span></span> 
4. <span data-ttu-id="c40e0-112">Clique em **Selecionar**.</span><span class="sxs-lookup"><span data-stu-id="c40e0-112">Click **Select**.</span></span> 

5. <span data-ttu-id="c40e0-113">No campo **Exibir status do trabalho**, selecione **Programado**.</span><span class="sxs-lookup"><span data-stu-id="c40e0-113">In the **Display job status** field, select **Scheduled**.</span></span> <span data-ttu-id="c40e0-114">Isso filtra a lista de trabalho para exibir somente os trabalhos kanban programados.</span><span class="sxs-lookup"><span data-stu-id="c40e0-114">This filters the job list to display only the scheduled kanban jobs.</span></span> 

## <a name="move-kanban-jobs-to-a-different-period"></a><span data-ttu-id="c40e0-115">Mover trabalhos kanban a um período diferente.</span><span class="sxs-lookup"><span data-stu-id="c40e0-115">Move kanban jobs to a different period.</span></span> 

1. <span data-ttu-id="c40e0-116">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="c40e0-116">In the list, find and select the desired record.</span></span> <span data-ttu-id="c40e0-117">Selecione um trabalho que tenha o status de **Trabalho planejado**, por exemplo, um trabalho programado em 20 de dezembro de 2012 no campo **Período planejado**.</span><span class="sxs-lookup"><span data-stu-id="c40e0-117">Select a job that has the **Planned job** status, for example, a job scheduled on December 20, 2012 in the **Planned period** field.</span></span> <span data-ttu-id="c40e0-118">Então mova o trabalho para o período anterior.</span><span class="sxs-lookup"><span data-stu-id="c40e0-118">Then move the job to the previous period.</span></span> 

2. <span data-ttu-id="c40e0-119">Clique em **Período anterior**.</span><span class="sxs-lookup"><span data-stu-id="c40e0-119">Click **Previous period**.</span></span> 

3. <span data-ttu-id="c40e0-120">Clique em **Finalizar** para mover o trabalho para o final da lista de trabalho como o último trabalho no período anterior.</span><span class="sxs-lookup"><span data-stu-id="c40e0-120">Click **End** to move the job to the end of the job list as the last job in the previous period.</span></span> 

4. <span data-ttu-id="c40e0-121">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="c40e0-121">In the list, find and select the desired record.</span></span> <span data-ttu-id="c40e0-122">Selecione um trabalho que tenha o status de **Trabalho planejado**, por exemplo, um trabalho programado em 18 de dezembro de 2012 no campo **Período planejado**.</span><span class="sxs-lookup"><span data-stu-id="c40e0-122">Select a job that has the **Planned job** status, for example, a job scheduled on December 18, 2012 in the **Planned period** field.</span></span> <span data-ttu-id="c40e0-123">Então mova o trabalho para o próximo período.</span><span class="sxs-lookup"><span data-stu-id="c40e0-123">Then move the job to the next period.</span></span> 

5. <span data-ttu-id="c40e0-124">Clique em **Próximo período**.</span><span class="sxs-lookup"><span data-stu-id="c40e0-124">Click **Next period**.</span></span> 

6. <span data-ttu-id="c40e0-125">Clique em **Iniciar** para mover o trabalho para o início da lista de trabalho como o primeiro trabalho no período anterior.</span><span class="sxs-lookup"><span data-stu-id="c40e0-125">Click **Start** to move the job to the start of the job list as the first job in the previous period.</span></span> 

## <a name="move-a-job-within-a-period"></a><span data-ttu-id="c40e0-126">Mover um trabalho em um período.</span><span class="sxs-lookup"><span data-stu-id="c40e0-126">Move a job within a period.</span></span> 

1. <span data-ttu-id="c40e0-127">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="c40e0-127">In the list, find and select the desired record.</span></span> <span data-ttu-id="c40e0-128">Selecione um trabalho que tenha o status de Trabalho planejado, por exemplo, o segundo trabalho programado em 19 de dezembro de 2012 no campo **Período planejado**.</span><span class="sxs-lookup"><span data-stu-id="c40e0-128">Select a job that has the Planned job status, for example, the second job scheduled on December 19, 2012 in the **Planned period** field.</span></span> <span data-ttu-id="c40e0-129">Então mova o trabalho para o período planejado.</span><span class="sxs-lookup"><span data-stu-id="c40e0-129">Then move the job within the planned period.</span></span> 

2. <span data-ttu-id="c40e0-130">Clique em **Encaminhar**.</span><span class="sxs-lookup"><span data-stu-id="c40e0-130">Click **Forward**.</span></span> <span data-ttu-id="c40e0-131">Observe que os trabalhos são movidos para uma linha abaixo na lista.</span><span class="sxs-lookup"><span data-stu-id="c40e0-131">Notice that the job is moved one line down on the list.</span></span> 

3. <span data-ttu-id="c40e0-132">Clique em **Recuar**.</span><span class="sxs-lookup"><span data-stu-id="c40e0-132">Click **Backward**.</span></span> <span data-ttu-id="c40e0-133">Observe que os trabalhos são movidos para uma linha acima na lista.</span><span class="sxs-lookup"><span data-stu-id="c40e0-133">Notice that the job is moved one line up on the list.</span></span>
