---
title: Remover um trabalho kanban da agenda
description: Esse procedimento se concentra em remover uns trabalhos kanban planejados do processo de plano revertendo o status do trabalho para Não planejado.
author: ChristianRytt
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KanbanJobSchedulingListPage, SysLookupMultiSelectGrid, KanbanJobStatusUpdate
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 4b2137268301beb85906bf7fb26c41f6eb09534c
ms.sourcegitcommit: fcb27d6a46cd544feef34f6ec7607bdd46b0c12b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/18/2020
ms.locfileid: "3148900"
---
# <a name="remove-a-kanban-job-from-the-schedule"></a><span data-ttu-id="a9271-103">Remover um trabalho kanban da agenda</span><span class="sxs-lookup"><span data-stu-id="a9271-103">Remove a kanban job from the schedule</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="a9271-104">Esse procedimento se concentra em remover uns trabalhos kanban planejados do processo de plano revertendo o status do trabalho para Não planejado.</span><span class="sxs-lookup"><span data-stu-id="a9271-104">This procedure focuses on removing a planned process kanban job from the schedule by reverting the job status to Not planned.</span></span> <span data-ttu-id="a9271-105">A empresa de dados demo usada para criar este procedimento é USMF.</span><span class="sxs-lookup"><span data-stu-id="a9271-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="a9271-106">Este procedimento está direcionada para o supervisor de chão de fábrica ou o planejador de produção.</span><span class="sxs-lookup"><span data-stu-id="a9271-106">This procedure is intended for the shop floor supervisor or production planner.</span></span>


## <a name="find-a-planned-kanban-job"></a><span data-ttu-id="a9271-107">Escolha um trabalho kanban planejado</span><span class="sxs-lookup"><span data-stu-id="a9271-107">Find a planned kanban job</span></span>
1. <span data-ttu-id="a9271-108">Vá para Controle de produção > Kanban > Agendamento de trabalho Kanban.</span><span class="sxs-lookup"><span data-stu-id="a9271-108">Go to Production control > Kanban > Kanban job scheduling.</span></span>
2. <span data-ttu-id="a9271-109">No campo Célula de trabalho, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="a9271-109">In the Work cell field, click the drop-down button to open the lookup.</span></span>
3. <span data-ttu-id="a9271-110">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="a9271-110">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="a9271-111">Selecione a célula de trabalho 1250.</span><span class="sxs-lookup"><span data-stu-id="a9271-111">Select work cell 1250.</span></span>  
4. <span data-ttu-id="a9271-112">Clique em Selecionar.</span><span class="sxs-lookup"><span data-stu-id="a9271-112">Click Select.</span></span>
5. <span data-ttu-id="a9271-113">No campo Exibir status do trabalho, selecione 'Programado'.</span><span class="sxs-lookup"><span data-stu-id="a9271-113">In the Display job status field, select 'Scheduled'.</span></span>

## <a name="remove-the-planned-kanban-job-from-the-schedule"></a><span data-ttu-id="a9271-114">Remover o trabalho kanban planejado da agenda</span><span class="sxs-lookup"><span data-stu-id="a9271-114">Remove the planned kanban job from the schedule</span></span>
1. <span data-ttu-id="a9271-115">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="a9271-115">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="a9271-116">Selecione um trabalho que tenha o Status planejado, por exemplo, um trabalho de 19 de dezembro de 2012.</span><span class="sxs-lookup"><span data-stu-id="a9271-116">Select a job that has the Planned status, for example, a job from December 19, 2012.</span></span>  
2. <span data-ttu-id="a9271-117">No Painel de Ação, clique em Plano.</span><span class="sxs-lookup"><span data-stu-id="a9271-117">On the Action Pane, click Plan.</span></span>
3. <span data-ttu-id="a9271-118">Clique em Reverter status de trabalho.</span><span class="sxs-lookup"><span data-stu-id="a9271-118">Click Revert job status.</span></span>
4. <span data-ttu-id="a9271-119">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="a9271-119">Click OK.</span></span>
    * <span data-ttu-id="a9271-120">Isso reverterá o status do trabalho atual 'Planejado' para 'Não planejado' e remove-o da diretoria do processo.</span><span class="sxs-lookup"><span data-stu-id="a9271-120">This will revert the current job status from 'Planned' to 'Not planned' and remove it from the process board.</span></span>   

