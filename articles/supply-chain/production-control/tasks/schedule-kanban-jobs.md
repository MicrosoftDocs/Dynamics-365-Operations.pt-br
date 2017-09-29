--- 
title: Agendar trabalhos kanban
description: "Esse procedimento se concentra em trabalhos kanban do processo de agendamento para uma célula de trabalho específica."
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
ms.openlocfilehash: f36544993a9280ae10489a19252bc105abd40ac9
ms.contentlocale: pt-br
ms.lasthandoff: 08/29/2017

---
# <a name="schedule-kanban-jobs"></a><span data-ttu-id="e499f-103">Agendar trabalhos kanban</span><span class="sxs-lookup"><span data-stu-id="e499f-103">Schedule kanban jobs</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="e499f-104">Esse procedimento se concentra em trabalhos kanban do processo de agendamento para uma célula de trabalho específica.</span><span class="sxs-lookup"><span data-stu-id="e499f-104">This procedure focuses on scheduling process kanban jobs for a specific work cell.</span></span> <span data-ttu-id="e499f-105">O procedimento “Preparar uns trabalhos kanban de processo quando os materiais não estiverem disponíveis” é um pré-requisito para a criação deste procedimento.</span><span class="sxs-lookup"><span data-stu-id="e499f-105">The procedure "Prepare a process kanban job when materials are not available" is a prerequisite for creating this procedure.</span></span> <span data-ttu-id="e499f-106">A empresa de dados demo usada para criar este procedimento é USMF.</span><span class="sxs-lookup"><span data-stu-id="e499f-106">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="e499f-107">Esta tarefa está direcionada para o supervisor de chão de fábrica e o planejador de produção que estão trabalhando com kanbans.</span><span class="sxs-lookup"><span data-stu-id="e499f-107">This task is intended for the shop floor supervisor and production planner working with kanbans.</span></span>


## <a name="select-kanban-jobs-for-a-work-cell"></a><span data-ttu-id="e499f-108">Selecione trabalhos kanban para uma célula de trabalho</span><span class="sxs-lookup"><span data-stu-id="e499f-108">Select kanban jobs for a work cell</span></span>
1. <span data-ttu-id="e499f-109">Vá para Controle de produção > Kanban > Agendamento de trabalho Kanban.</span><span class="sxs-lookup"><span data-stu-id="e499f-109">Go to Production control > Kanban > Kanban job scheduling.</span></span>
2. <span data-ttu-id="e499f-110">Expandir o quadro de fatos Capacidade de período</span><span class="sxs-lookup"><span data-stu-id="e499f-110">Expand the Period capacity fact box</span></span>
    * <span data-ttu-id="e499f-111">Expandir o Quadro de Fatos Kanban.</span><span class="sxs-lookup"><span data-stu-id="e499f-111">Expand the Kanban FactBox.</span></span>  
3. <span data-ttu-id="e499f-112">No campo Célula de trabalho, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="e499f-112">In the Work cell field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="e499f-113">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="e499f-113">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="e499f-114">Selecione a célula de trabalho 1250.</span><span class="sxs-lookup"><span data-stu-id="e499f-114">Select work cell 1250.</span></span> <span data-ttu-id="e499f-115">Isso filtrará a exibição para exibir somente os trabalhos para a célula de trabalho 1250.</span><span class="sxs-lookup"><span data-stu-id="e499f-115">This will filter the view to display only the jobs for work cell 1250.</span></span>  
5. <span data-ttu-id="e499f-116">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="e499f-116">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="e499f-117">Clique em Selecionar.</span><span class="sxs-lookup"><span data-stu-id="e499f-117">Click Select.</span></span>

## <a name="schedule-a-kanban-job-in-the-first-available-period"></a><span data-ttu-id="e499f-118">Agendar um trabalho kanban no primeiro período disponível</span><span class="sxs-lookup"><span data-stu-id="e499f-118">Schedule a kanban job in the first available period</span></span>
1. <span data-ttu-id="e499f-119">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="e499f-119">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="e499f-120">Selecione a primeira linha na lista que tem o Status não planejado.</span><span class="sxs-lookup"><span data-stu-id="e499f-120">Select the first row in the list that has the Not planned status.</span></span> <span data-ttu-id="e499f-121">O ícone pontilhado no campo status do trabalho indica Não planejado.</span><span class="sxs-lookup"><span data-stu-id="e499f-121">The dotted icon in the Job status field indicates not planned.</span></span>  
2. <span data-ttu-id="e499f-122">Clique em Agendar.</span><span class="sxs-lookup"><span data-stu-id="e499f-122">Click Schedule.</span></span>
    * <span data-ttu-id="e499f-123">Isso agendará os trabalhos kanban no primeiro período disponível.</span><span class="sxs-lookup"><span data-stu-id="e499f-123">This will schedule the kanban job in the first available period.</span></span>  
    * <span data-ttu-id="e499f-124">Observe que os trabalhos kanban são movidos para o final da lista porque foram adicionados ao período que parte de hoje.</span><span class="sxs-lookup"><span data-stu-id="e499f-124">Notice that the kanban job is moved to the end of the list because it has been added to the period starting from today.</span></span>  
    * <span data-ttu-id="e499f-125">Se o período que parte de hoje for registrado totalmente, os trabalhos serão movidos para o primeiro período disponível.</span><span class="sxs-lookup"><span data-stu-id="e499f-125">If the period starting from today is fully booked, the job will be moved to the first available period.</span></span>  

## <a name="schedule-two-kanban-jobs-for-a-specific-day"></a><span data-ttu-id="e499f-126">Agende os dois trabalhos kanban para um determinado dia</span><span class="sxs-lookup"><span data-stu-id="e499f-126">Schedule two kanban jobs for a specific day</span></span>
1. <span data-ttu-id="e499f-127">Na lista, selecione a linha 1.</span><span class="sxs-lookup"><span data-stu-id="e499f-127">In the list, select row 1.</span></span>
    * <span data-ttu-id="e499f-128">Você deverá ver que a primeira linha que tiver o status não planejado no campo status do trabalho.</span><span class="sxs-lookup"><span data-stu-id="e499f-128">You should see that the first row has the Not planned status in the Job status field.</span></span>  
2. <span data-ttu-id="e499f-129">Na lista, selecione a linha 2.</span><span class="sxs-lookup"><span data-stu-id="e499f-129">In the list, select row 2.</span></span>
    * <span data-ttu-id="e499f-130">Você deverá ver que a segunda linha que tiver o status não planejado no campo status do trabalho.</span><span class="sxs-lookup"><span data-stu-id="e499f-130">You should see that the second row has the Not planned status in the Job status field.</span></span> <span data-ttu-id="e499f-131">Agora você tem os dois primeiros trabalhos selecionados.</span><span class="sxs-lookup"><span data-stu-id="e499f-131">Now you have the first two jobs selected.</span></span>  
3. <span data-ttu-id="e499f-132">Clique em Agendar da data para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="e499f-132">Click Schedule from date to open the drop dialog.</span></span>
4. <span data-ttu-id="e499f-133">Marque ou desmarque a caixa de seleção Substituir reação de escassez de capacidade.</span><span class="sxs-lookup"><span data-stu-id="e499f-133">Check or uncheck the Override capacity shortage reaction box.</span></span>
    * <span data-ttu-id="e499f-134">Esta opção permite que você substitua a reação padrão de escassez de capacidade.</span><span class="sxs-lookup"><span data-stu-id="e499f-134">This option allows you to override the default capacity shortage reaction.</span></span>  
5. <span data-ttu-id="e499f-135">No campo Reação de escassez de capacidade, selecione 'Adicionar ao período solicitado'.</span><span class="sxs-lookup"><span data-stu-id="e499f-135">In the Capacity shortage reaction field, select 'Add to the requested period'.</span></span>
    * <span data-ttu-id="e499f-136">Esta opção assegurará que os trabalhos sejam adicionados à ordem, período de qualquer modo se a célula de trabalho pode ser sobrecarregada.</span><span class="sxs-lookup"><span data-stu-id="e499f-136">This option will ensure that the job is added to the requested period, regardless if the work cell might be overloaded.</span></span>  
6. <span data-ttu-id="e499f-137">Clique em Agendar.</span><span class="sxs-lookup"><span data-stu-id="e499f-137">Click Schedule.</span></span>
    * <span data-ttu-id="e499f-138">Observe que os trabalhos são adicionados ao período desejado.</span><span class="sxs-lookup"><span data-stu-id="e499f-138">Notice that both jobs are added to the desired period.</span></span>  
    * <span data-ttu-id="e499f-139">Na seção Capacidade do período, você pode ver o carregamento para cada período.</span><span class="sxs-lookup"><span data-stu-id="e499f-139">In the Period capacity section, you can see the load for each period.</span></span> <span data-ttu-id="e499f-140">O campo Consumo mostra o consumo programado neste período.</span><span class="sxs-lookup"><span data-stu-id="e499f-140">The Consumption field shows the scheduled consumption in this period.</span></span> <span data-ttu-id="e499f-141">Se o consumo agendado for maior que a capacidade disponível neste período, o consumo selecionado será sobrecarregado.</span><span class="sxs-lookup"><span data-stu-id="e499f-141">If the scheduled consumption is higher than the available capacity in this period, the overloaded consumption will be selected.</span></span>  


