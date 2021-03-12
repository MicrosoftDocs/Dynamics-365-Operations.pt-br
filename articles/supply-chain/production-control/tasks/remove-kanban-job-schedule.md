---
title: Remover um trabalho kanban da agenda
description: Esse procedimento se concentra em remover uns trabalhos kanban planejados do processo de plano revertendo o status do trabalho para Não planejado.
author: ChristianRytt
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KanbanJobSchedulingListPage, SysLookupMultiSelectGrid, KanbanJobStatusUpdate
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: fcd9247e24323ba606377d7e51bd4447ab51c905
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4961606"
---
# <a name="remove-a-kanban-job-from-the-schedule"></a><span data-ttu-id="86564-103">Remover um trabalho kanban da agenda</span><span class="sxs-lookup"><span data-stu-id="86564-103">Remove a kanban job from the schedule</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="86564-104">Esse procedimento se concentra em remover uns trabalhos kanban planejados do processo de plano revertendo o status do trabalho para Não planejado.</span><span class="sxs-lookup"><span data-stu-id="86564-104">This procedure focuses on removing a planned process kanban job from the schedule by reverting the job status to Not planned.</span></span> <span data-ttu-id="86564-105">A empresa de dados demo usada para criar este procedimento é USMF.</span><span class="sxs-lookup"><span data-stu-id="86564-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="86564-106">Este procedimento está direcionada para o supervisor de chão de fábrica ou o planejador de produção.</span><span class="sxs-lookup"><span data-stu-id="86564-106">This procedure is intended for the shop floor supervisor or production planner.</span></span>


## <a name="find-a-planned-kanban-job"></a><span data-ttu-id="86564-107">Escolha um trabalho kanban planejado</span><span class="sxs-lookup"><span data-stu-id="86564-107">Find a planned kanban job</span></span>
1. <span data-ttu-id="86564-108">Vá para Controle de produção > Kanban > Agendamento de trabalho Kanban.</span><span class="sxs-lookup"><span data-stu-id="86564-108">Go to Production control > Kanban > Kanban job scheduling.</span></span>
2. <span data-ttu-id="86564-109">No campo Célula de trabalho, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="86564-109">In the Work cell field, click the drop-down button to open the lookup.</span></span>
3. <span data-ttu-id="86564-110">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="86564-110">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="86564-111">Selecione a célula de trabalho 1250.</span><span class="sxs-lookup"><span data-stu-id="86564-111">Select work cell 1250.</span></span>  
4. <span data-ttu-id="86564-112">Clique em Selecionar.</span><span class="sxs-lookup"><span data-stu-id="86564-112">Click Select.</span></span>
5. <span data-ttu-id="86564-113">No campo Exibir status do trabalho, selecione 'Programado'.</span><span class="sxs-lookup"><span data-stu-id="86564-113">In the Display job status field, select 'Scheduled'.</span></span>

## <a name="remove-the-planned-kanban-job-from-the-schedule"></a><span data-ttu-id="86564-114">Remover o trabalho kanban planejado da agenda</span><span class="sxs-lookup"><span data-stu-id="86564-114">Remove the planned kanban job from the schedule</span></span>
1. <span data-ttu-id="86564-115">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="86564-115">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="86564-116">Selecione um trabalho que tenha o Status planejado, por exemplo, um trabalho de 19 de dezembro de 2012.</span><span class="sxs-lookup"><span data-stu-id="86564-116">Select a job that has the Planned status, for example, a job from December 19, 2012.</span></span>  
2. <span data-ttu-id="86564-117">No Painel de Ação, clique em Plano.</span><span class="sxs-lookup"><span data-stu-id="86564-117">On the Action Pane, click Plan.</span></span>
3. <span data-ttu-id="86564-118">Clique em Reverter status de trabalho.</span><span class="sxs-lookup"><span data-stu-id="86564-118">Click Revert job status.</span></span>
4. <span data-ttu-id="86564-119">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="86564-119">Click OK.</span></span>
    * <span data-ttu-id="86564-120">Isso reverterá o status do trabalho atual 'Planejado' para 'Não planejado' e remove-o da diretoria do processo.</span><span class="sxs-lookup"><span data-stu-id="86564-120">This will revert the current job status from 'Planned' to 'Not planned' and remove it from the process board.</span></span>   

