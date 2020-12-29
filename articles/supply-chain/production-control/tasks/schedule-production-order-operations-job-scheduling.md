---
title: Agendar uma ordem de produção com operações e agendamento de trabalho
description: Este tópico se concentra em agendar uma ordem de produção com o agendamento de operações e planejamento de trabalho.
author: ChristianRytt
manager: tfehr
ms.date: 08/19/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProdTableListPage, ProdTableCreate, InventItemIdLookupPurchase, ProdSchedule, ProdTable, ProdRouteJob
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 7a69339bc678de8343dbf2646a4d6fe0ace9964c
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4422142"
---
# <a name="schedule-a-production-order-with-operations-and-job-scheduling"></a><span data-ttu-id="0b1a4-103">Agendar uma ordem de produção com operações e agendamento de trabalho</span><span class="sxs-lookup"><span data-stu-id="0b1a4-103">Schedule a production order with operations and job scheduling</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="0b1a4-104">Este tópico se concentra em agendar uma ordem de produção com o agendamento de operações e planejamento de trabalho.</span><span class="sxs-lookup"><span data-stu-id="0b1a4-104">This topic focuses on scheduling a production order with operations scheduling and job scheduling.</span></span> <span data-ttu-id="0b1a4-105">Nenhum trabalho é criado com o agendamento de operações, mas sim no planejamento de trabalho.</span><span class="sxs-lookup"><span data-stu-id="0b1a4-105">No jobs are created with operations scheduling whereas jobs are created with job scheduling.</span></span> <span data-ttu-id="0b1a4-106">A empresa de dados demo usada para criar esta tarefa é USMF.</span><span class="sxs-lookup"><span data-stu-id="0b1a4-106">The demo data company used to create this task is USMF.</span></span> <span data-ttu-id="0b1a4-107">Este procedimento destina-se ao gerente de produção, ao planejador de produção, ou supervisor de chão de fábrica que trabalha em um ambiente de manufatura discreto.</span><span class="sxs-lookup"><span data-stu-id="0b1a4-107">This procedure is intended for the production manager, production planner, or shop floor supervisor working in a discrete manufacturing environment.</span></span>


## <a name="create-a-production-order"></a><span data-ttu-id="0b1a4-108">Criar uma ordem de produção</span><span class="sxs-lookup"><span data-stu-id="0b1a4-108">Create a production order</span></span>
1. <span data-ttu-id="0b1a4-109">No painel de navegação, acesse **Módulos > Controle de produção > Ordens de produção > Todas as ordens de produção**.</span><span class="sxs-lookup"><span data-stu-id="0b1a4-109">In the navigation pane, go to **Modules > Production control > Production orders > All production orders**.</span></span>
2. <span data-ttu-id="0b1a4-110">Selecione **Nova ordem de produção**.</span><span class="sxs-lookup"><span data-stu-id="0b1a4-110">Select **New production order**.</span></span>
3. <span data-ttu-id="0b1a4-111">No campo **Número do item**, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="0b1a4-111">In the **Item number** field, enter or select a value.</span></span> <span data-ttu-id="0b1a4-112">Selecione o Número de item **D0001**.</span><span class="sxs-lookup"><span data-stu-id="0b1a4-112">Select Item number **D0001**.</span></span>  
4. <span data-ttu-id="0b1a4-113">Selecione **Criar**.</span><span class="sxs-lookup"><span data-stu-id="0b1a4-113">Select **Create**.</span></span>

## <a name="schedule-operations-for-the-production-order"></a><span data-ttu-id="0b1a4-114">Agendar operações para a ordem de produção</span><span class="sxs-lookup"><span data-stu-id="0b1a4-114">Schedule operations for the production order</span></span>
1. <span data-ttu-id="0b1a4-115">Marque a linha que acabou de ser criada.</span><span class="sxs-lookup"><span data-stu-id="0b1a4-115">Mark the newly created row.</span></span>      
2. <span data-ttu-id="0b1a4-116">No Painel de Ação, selecione **Agendar**.</span><span class="sxs-lookup"><span data-stu-id="0b1a4-116">On the Action Pane, select **Schedule**.</span></span>
3. <span data-ttu-id="0b1a4-117">Selecione **Agendar operações**.</span><span class="sxs-lookup"><span data-stu-id="0b1a4-117">Select **Schedule operations**.</span></span>
4. <span data-ttu-id="0b1a4-118">No campo **Direção do agendamento**, selecione **A partir da data de agendamento**.</span><span class="sxs-lookup"><span data-stu-id="0b1a4-118">In the **Scheduling direction** field, select **Forward from scheduling date**.</span></span>
5. <span data-ttu-id="0b1a4-119">No campo **Data de planejamento**, insira uma data.</span><span class="sxs-lookup"><span data-stu-id="0b1a4-119">In the **Scheduling date** field, enter a date.</span></span> <span data-ttu-id="0b1a4-120">Selecione uma data futura, por exemplo, hoje mais uma semana.</span><span class="sxs-lookup"><span data-stu-id="0b1a4-120">Select a future date, for example, today plus one week.</span></span> <span data-ttu-id="0b1a4-121">Com a Direção de agendamento selecionada, a ordem de produção será agendada a partir dessa data.</span><span class="sxs-lookup"><span data-stu-id="0b1a4-121">With the selected Scheduling direction, the production order will be scheduled forward from this date.</span></span>  
6. <span data-ttu-id="0b1a4-122">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="0b1a4-122">Select **OK**.</span></span>
7. <span data-ttu-id="0b1a4-123">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="0b1a4-123">In the list, mark the selected row.</span></span> <span data-ttu-id="0b1a4-124">Observe que o status foi alterado para **Agendado**.</span><span class="sxs-lookup"><span data-stu-id="0b1a4-124">Note that the status is changed to **Scheduled**.</span></span> 
8. <span data-ttu-id="0b1a4-125">Selecione **Todos os trabalhos**.</span><span class="sxs-lookup"><span data-stu-id="0b1a4-125">Select **All jobs**.</span></span> <span data-ttu-id="0b1a4-126">Observe que nenhum trabalho é criado com o agendamento de operações.</span><span class="sxs-lookup"><span data-stu-id="0b1a4-126">Note that no jobs are created with operations scheduling.</span></span>  
9. <span data-ttu-id="0b1a4-127">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="0b1a4-127">Close the page.</span></span>

## <a name="schedule-jobs-for-the-production-order"></a><span data-ttu-id="0b1a4-128">Agendar trabalhos para a ordem de produção</span><span class="sxs-lookup"><span data-stu-id="0b1a4-128">Schedule jobs for the production order</span></span>
1. <span data-ttu-id="0b1a4-129">No Painel de Ação, selecione **Agendar**.</span><span class="sxs-lookup"><span data-stu-id="0b1a4-129">On the Action Pane, select **Schedule**.</span></span>
2. <span data-ttu-id="0b1a4-130">Selecione **Agendar trabalhos**.</span><span class="sxs-lookup"><span data-stu-id="0b1a4-130">Select **Schedule jobs**.</span></span>
3. <span data-ttu-id="0b1a4-131">No campo **Direção do agendamento**, selecione **A partir da data de agendamento**.</span><span class="sxs-lookup"><span data-stu-id="0b1a4-131">In the **Scheduling direction** field, select **Forward from scheduling date**.</span></span>
4. <span data-ttu-id="0b1a4-132">No campo **Data de planejamento**, insira uma data.</span><span class="sxs-lookup"><span data-stu-id="0b1a4-132">In the **Scheduling date** field, enter a date.</span></span> <span data-ttu-id="0b1a4-133">Selecione uma data futura, por exemplo, hoje mais uma semana.</span><span class="sxs-lookup"><span data-stu-id="0b1a4-133">Select a date in the future, for example, today plus one week.</span></span> <span data-ttu-id="0b1a4-134">Com a Direção de agendamento selecionada, a ordem de produção será agendada a partir dessa data.</span><span class="sxs-lookup"><span data-stu-id="0b1a4-134">With the selected Scheduling direction, the production order will be scheduled forward from this date.</span></span>  
5. <span data-ttu-id="0b1a4-135">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="0b1a4-135">Select **OK**.</span></span>
6. <span data-ttu-id="0b1a4-136">No Painel de Ação, selecione **Ordem de produção**.</span><span class="sxs-lookup"><span data-stu-id="0b1a4-136">On the Action Pane, select **Production order**.</span></span>
7. <span data-ttu-id="0b1a4-137">Selecione **Todos os trabalhos**.</span><span class="sxs-lookup"><span data-stu-id="0b1a4-137">Select **All jobs**.</span></span> <span data-ttu-id="0b1a4-138">Observe que, com base no roteiro ativo, 5 trabalhos são criados com o agendamento do trabalho.</span><span class="sxs-lookup"><span data-stu-id="0b1a4-138">Note that based on the active route, 5 jobs are created with job scheduling.</span></span>  

