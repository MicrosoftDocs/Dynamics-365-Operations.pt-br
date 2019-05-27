---
title: Agendar uma ordem de produção com operações e agendamento de trabalho
description: Este procedimento se concentra em agendar uma ordem de produção com o agendamento de operações e planejamento de trabalho.
author: ChristianRytt
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProdTableListPage, ProdTableCreate, InventItemIdLookupPurchase, ProdSchedule, ProdTable, ProdRouteJob
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 00698e9cd2ed0481e5fed301c8a8c2e98690a5db
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1562129"
---
# <a name="schedule-a-production-order-with-operations-and-job-scheduling"></a><span data-ttu-id="4ece4-103">Agendar uma ordem de produção com operações e agendamento de trabalho</span><span class="sxs-lookup"><span data-stu-id="4ece4-103">Schedule a production order with operations and job scheduling</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="4ece4-104">Este procedimento se concentra em agendar uma ordem de produção com o agendamento de operações e planejamento de trabalho.</span><span class="sxs-lookup"><span data-stu-id="4ece4-104">This procedure focuses on scheduling a production order with operations scheduling and job scheduling.</span></span> <span data-ttu-id="4ece4-105">Nenhum trabalho é criado com o agendamento de operações, mas sim no planejamento de trabalho.</span><span class="sxs-lookup"><span data-stu-id="4ece4-105">No jobs are created with operations scheduling whereas jobs are created with job scheduling.</span></span> <span data-ttu-id="4ece4-106">A empresa de dados demo usada para criar esta tarefa é USMF.</span><span class="sxs-lookup"><span data-stu-id="4ece4-106">The demo data company used to create this task is USMF.</span></span> <span data-ttu-id="4ece4-107">Este procedimento destina-se ao gerente de produção, ao planejador de produção, ou supervisor de chão de fábrica que trabalha em um ambiente de manufatura discreto.</span><span class="sxs-lookup"><span data-stu-id="4ece4-107">This procedure is intended for the production manager, production planner, or shop floor supervisor working in a discrete manufacturing environment.</span></span>


## <a name="create-a-production-order"></a><span data-ttu-id="4ece4-108">Criar uma ordem de produção</span><span class="sxs-lookup"><span data-stu-id="4ece4-108">Create a production order</span></span>
1. <span data-ttu-id="4ece4-109">Vá para Controle de produção > Ordens de produção > Todas as ordens de produção.</span><span class="sxs-lookup"><span data-stu-id="4ece4-109">Go to Production control > Production orders > All production orders.</span></span>
2. <span data-ttu-id="4ece4-110">Clique em Nova ordem de produção.</span><span class="sxs-lookup"><span data-stu-id="4ece4-110">Click New production order.</span></span>
3. <span data-ttu-id="4ece4-111">No campo Número do item, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="4ece4-111">In the Item number field, enter or select a value.</span></span>
    * <span data-ttu-id="4ece4-112">Selecione o Número de item D0001.</span><span class="sxs-lookup"><span data-stu-id="4ece4-112">Select Item number D0001.</span></span>  
4. <span data-ttu-id="4ece4-113">Clique em Criar.</span><span class="sxs-lookup"><span data-stu-id="4ece4-113">Click Create.</span></span>

## <a name="schedule-operations-for-the-production-order"></a><span data-ttu-id="4ece4-114">Agendar operações para a ordem de produção</span><span class="sxs-lookup"><span data-stu-id="4ece4-114">Schedule operations for the production order</span></span>
1. <span data-ttu-id="4ece4-115">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="4ece4-115">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="4ece4-116">Selecione a ordem de produção que você acabou de criar.</span><span class="sxs-lookup"><span data-stu-id="4ece4-116">Select the production order that you have just created.</span></span> <span data-ttu-id="4ece4-117">Ela deve estar na parte superior da lista.</span><span class="sxs-lookup"><span data-stu-id="4ece4-117">It should be at the top of the list.</span></span>      
2. <span data-ttu-id="4ece4-118">No Painel de Ação, clique em Agenda.</span><span class="sxs-lookup"><span data-stu-id="4ece4-118">On the Action Pane, click Schedule.</span></span>
3. <span data-ttu-id="4ece4-119">Clique em Agendar operações.</span><span class="sxs-lookup"><span data-stu-id="4ece4-119">Click Schedule operations.</span></span>
4. <span data-ttu-id="4ece4-120">No campo Direção do agendamento, selecione 'A partir da data de agendamento'.</span><span class="sxs-lookup"><span data-stu-id="4ece4-120">In the Scheduling direction field, select 'Forward from scheduling date'.</span></span>
5. <span data-ttu-id="4ece4-121">No campo Data de planejamento, insira uma data.</span><span class="sxs-lookup"><span data-stu-id="4ece4-121">In the Scheduling date field, enter a date.</span></span>
    * <span data-ttu-id="4ece4-122">Selecione uma data futura, por exemplo, hoje mais uma semana.</span><span class="sxs-lookup"><span data-stu-id="4ece4-122">Select a future date, for example, today plus one week.</span></span> <span data-ttu-id="4ece4-123">Com a Direção de agendamento selecionada, a ordem de produção será agendada a partir dessa data.</span><span class="sxs-lookup"><span data-stu-id="4ece4-123">With the selected Scheduling direction, the production order will be scheduled forward from this date.</span></span>  
6. <span data-ttu-id="4ece4-124">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="4ece4-124">Click OK.</span></span>
7. <span data-ttu-id="4ece4-125">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="4ece4-125">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="4ece4-126">Observe que o status foi alterado para Agendado.</span><span class="sxs-lookup"><span data-stu-id="4ece4-126">Note that the status is changed to Scheduled.</span></span>  
8. <span data-ttu-id="4ece4-127">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="4ece4-127">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="4ece4-128">Clique em Todos os trabalhos.</span><span class="sxs-lookup"><span data-stu-id="4ece4-128">Click All jobs.</span></span>
    * <span data-ttu-id="4ece4-129">Observe que nenhum trabalho é criado com o agendamento de operações.</span><span class="sxs-lookup"><span data-stu-id="4ece4-129">Note that no jobs are created with operations scheduling.</span></span>  
10. <span data-ttu-id="4ece4-130">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="4ece4-130">Close the page.</span></span>

## <a name="schedule-jobs-for-the-production-order"></a><span data-ttu-id="4ece4-131">Agendar trabalhos para a ordem de produção</span><span class="sxs-lookup"><span data-stu-id="4ece4-131">Schedule jobs for the production order</span></span>
1. <span data-ttu-id="4ece4-132">No Painel de Ação, clique em Agenda.</span><span class="sxs-lookup"><span data-stu-id="4ece4-132">On the Action Pane, click Schedule.</span></span>
2. <span data-ttu-id="4ece4-133">Clique em Agendar trabalhos.</span><span class="sxs-lookup"><span data-stu-id="4ece4-133">Click Schedule jobs.</span></span>
3. <span data-ttu-id="4ece4-134">No campo Direção do agendamento, selecione 'A partir da data de agendamento'.</span><span class="sxs-lookup"><span data-stu-id="4ece4-134">In the Scheduling direction field, select 'Forward from scheduling date'.</span></span>
4. <span data-ttu-id="4ece4-135">No campo Data de planejamento, insira uma data.</span><span class="sxs-lookup"><span data-stu-id="4ece4-135">In the Scheduling date field, enter a date.</span></span>
    * <span data-ttu-id="4ece4-136">Selecione uma data futura, por exemplo, hoje mais uma semana.</span><span class="sxs-lookup"><span data-stu-id="4ece4-136">Select a date in the future, for example, today plus one week.</span></span> <span data-ttu-id="4ece4-137">Com a Direção de agendamento selecionada, a ordem de produção será agendada a partir dessa data.</span><span class="sxs-lookup"><span data-stu-id="4ece4-137">With the selected Scheduling direction, the production order will be scheduled forward from this date.</span></span>  
5. <span data-ttu-id="4ece4-138">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="4ece4-138">Click OK.</span></span>
6. <span data-ttu-id="4ece4-139">No Painel de Ação, clique em Ordem de produção.</span><span class="sxs-lookup"><span data-stu-id="4ece4-139">On the Action Pane, click Production order.</span></span>
7. <span data-ttu-id="4ece4-140">Clique em Todos os trabalhos.</span><span class="sxs-lookup"><span data-stu-id="4ece4-140">Click All jobs.</span></span>
    * <span data-ttu-id="4ece4-141">Observe que, com base no roteiro ativo, 5 trabalhos são criados com o agendamento do trabalho.</span><span class="sxs-lookup"><span data-stu-id="4ece4-141">Note that based on the active route, 5 jobs are created with job scheduling.</span></span>  

