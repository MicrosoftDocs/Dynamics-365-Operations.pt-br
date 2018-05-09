--- 
title: Remover um trabalho kanban da agenda
description: "Esse procedimento se concentra em remover uns trabalhos kanban planejados do processo de plano revertendo o status do trabalho para Não planejado."
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
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 7bd492f3c4dc1057ac97bd8078b76041639004ef
ms.contentlocale: pt-br
ms.lasthandoff: 05/08/2018

---
# <a name="remove-a-kanban-job-from-the-schedule"></a><span data-ttu-id="aa140-103">Remover um trabalho kanban da agenda</span><span class="sxs-lookup"><span data-stu-id="aa140-103">Remove a kanban job from the schedule</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="aa140-104">Esse procedimento se concentra em remover uns trabalhos kanban planejados do processo de plano revertendo o status do trabalho para Não planejado.</span><span class="sxs-lookup"><span data-stu-id="aa140-104">This procedure focuses on removing a planned process kanban job from the schedule by reverting the job status to Not planned.</span></span> <span data-ttu-id="aa140-105">A empresa de dados demo usada para criar este procedimento é USMF.</span><span class="sxs-lookup"><span data-stu-id="aa140-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="aa140-106">Este procedimento está direcionada para o supervisor de chão de fábrica ou o planejador de produção.</span><span class="sxs-lookup"><span data-stu-id="aa140-106">This procedure is intended for the shop floor supervisor or production planner.</span></span>


## <a name="find-a-planned-kanban-job"></a><span data-ttu-id="aa140-107">Escolha um trabalho kanban planejado</span><span class="sxs-lookup"><span data-stu-id="aa140-107">Find a planned kanban job</span></span>
1. <span data-ttu-id="aa140-108">Vá para Controle de produção > Kanban > Agendamento de trabalho Kanban.</span><span class="sxs-lookup"><span data-stu-id="aa140-108">Go to Production control > Kanban > Kanban job scheduling.</span></span>
2. <span data-ttu-id="aa140-109">No campo Célula de trabalho, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="aa140-109">In the Work cell field, click the drop-down button to open the lookup.</span></span>
3. <span data-ttu-id="aa140-110">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="aa140-110">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="aa140-111">Selecione a célula de trabalho 1250.</span><span class="sxs-lookup"><span data-stu-id="aa140-111">Select work cell 1250.</span></span>  
4. <span data-ttu-id="aa140-112">Clique em Selecionar.</span><span class="sxs-lookup"><span data-stu-id="aa140-112">Click Select.</span></span>
5. <span data-ttu-id="aa140-113">No campo Exibir status do trabalho, selecione 'Programado'.</span><span class="sxs-lookup"><span data-stu-id="aa140-113">In the Display job status field, select 'Scheduled'.</span></span>

## <a name="remove-the-planned-kanban-job-from-the-schedule"></a><span data-ttu-id="aa140-114">Remover o trabalho kanban planejado da agenda</span><span class="sxs-lookup"><span data-stu-id="aa140-114">Remove the planned kanban job from the schedule</span></span>
1. <span data-ttu-id="aa140-115">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="aa140-115">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="aa140-116">Selecione um trabalho que tenha o Status planejado, por exemplo, um trabalho de 19 de dezembro de 2012.</span><span class="sxs-lookup"><span data-stu-id="aa140-116">Select a job that has the Planned status, for example, a job from December 19, 2012.</span></span>  
2. <span data-ttu-id="aa140-117">No Painel de Ação, clique em Plano.</span><span class="sxs-lookup"><span data-stu-id="aa140-117">On the Action Pane, click Plan.</span></span>
3. <span data-ttu-id="aa140-118">Clique em Reverter status de trabalho.</span><span class="sxs-lookup"><span data-stu-id="aa140-118">Click Revert job status.</span></span>
4. <span data-ttu-id="aa140-119">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="aa140-119">Click OK.</span></span>
    * <span data-ttu-id="aa140-120">Isso reverterá o status do trabalho atual 'Planejado' para 'Não planejado' e remove-o da diretoria do processo.</span><span class="sxs-lookup"><span data-stu-id="aa140-120">This will revert the current job status from 'Planned' to 'Not planned' and remove it from the process board.</span></span>   


