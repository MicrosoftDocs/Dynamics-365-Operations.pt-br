---
title: Criar uma regra kanban para atividades múltiplas
description: Este procedimento mostra como criar uma regra kanban que inclua atividades múltiplas de um fluxo da produção.
author: ChristianRytt
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KanbanRules, LeanProductionFlowActivityLookup, KanbanFlowSelection, InventItemIdLookupSimple, KanbanCreateScheduled, Kanban
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b52e33c34a2fd151765833c68eab9091b22405cc
ms.sourcegitcommit: fcb27d6a46cd544feef34f6ec7607bdd46b0c12b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/18/2020
ms.locfileid: "3147011"
---
# <a name="create-a-kanban-rule-for-multiple-activities"></a><span data-ttu-id="09e33-103">Criar uma regra kanban para atividades múltiplas</span><span class="sxs-lookup"><span data-stu-id="09e33-103">Create a kanban rule for multiple activities</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="09e33-104">Este procedimento mostra como criar uma regra kanban que inclua atividades múltiplas de um fluxo da produção.</span><span class="sxs-lookup"><span data-stu-id="09e33-104">This procedure shows how to create a kanban rule that includes multiple activities from a production flow.</span></span> <span data-ttu-id="09e33-105">A empresa de dados demo usada para criar esta tarefa é USMF.</span><span class="sxs-lookup"><span data-stu-id="09e33-105">The demo data company used to create this task is USMF.</span></span> <span data-ttu-id="09e33-106">Esta tarefa destina-se ao Engenheiro do processo ou Gerente de fluxo de valor, pois eles preparam a produção de um produto novo ou modificado em um ambiente de lean.</span><span class="sxs-lookup"><span data-stu-id="09e33-106">This task is intended for the process engineer or the value stream manager, as they prepare production of a new or modified product in a lean environment.</span></span>


## <a name="create-a-new-kanban-rule"></a><span data-ttu-id="09e33-107">Criar uma nova regra kanban</span><span class="sxs-lookup"><span data-stu-id="09e33-107">Create a new kanban rule</span></span>
1. <span data-ttu-id="09e33-108">Vá para Gerenciamento de informações dos produtos > Lean manufacturing > Regras kanban.</span><span class="sxs-lookup"><span data-stu-id="09e33-108">Go to Product information management > Lean manufacturing > Kanban rules.</span></span>
2. <span data-ttu-id="09e33-109">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="09e33-109">Click New.</span></span>
3. <span data-ttu-id="09e33-110">No campo Estratégia de reabastecimento, selecione 'Programado'.</span><span class="sxs-lookup"><span data-stu-id="09e33-110">In the Replenishment strategy field, select 'Scheduled'.</span></span>
4. <span data-ttu-id="09e33-111">No campo Primeira atividade do plano, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="09e33-111">In the First plan activity field, enter or select a value.</span></span>
    * <span data-ttu-id="09e33-112">Selecione SpeakerAssemblyAndPolish.</span><span class="sxs-lookup"><span data-stu-id="09e33-112">Select SpeakerAssemblyAndPolish.</span></span>  
5. <span data-ttu-id="09e33-113">Selecione a caixa de verificação múltipla das atividades.</span><span class="sxs-lookup"><span data-stu-id="09e33-113">Select the Multiple activities check box.</span></span>
    * <span data-ttu-id="09e33-114">O objetivo é incluir mais que uma atividade na regra kanban.</span><span class="sxs-lookup"><span data-stu-id="09e33-114">The purpose is to include more than one activity in the kanban rule.</span></span> <span data-ttu-id="09e33-115">Você escolhe um trajeto no fluxo da produção quando você seleciona a última atividade do plano.</span><span class="sxs-lookup"><span data-stu-id="09e33-115">You choose a path in the production flow when you select the last plan activity.</span></span>  
6. <span data-ttu-id="09e33-116">No campo Última atividade do plano, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="09e33-116">In the Last plan activity field, enter or select a value.</span></span>
    * <span data-ttu-id="09e33-117">Selecione SpeakerTestAndPackaging.</span><span class="sxs-lookup"><span data-stu-id="09e33-117">Select SpeakerTestAndPackaging.</span></span> <span data-ttu-id="09e33-118">Depois que você seleciona o valor, uma página abre automaticamente.</span><span class="sxs-lookup"><span data-stu-id="09e33-118">After you select the value, a page automatically opens.</span></span> <span data-ttu-id="09e33-119">Selecione o fluxo kanban SpeakerAssemblyAndPolish > SpeakerTestAndPackaging.</span><span class="sxs-lookup"><span data-stu-id="09e33-119">Select the kanban flow SpeakerAssemblyAndPolish > SpeakerTestAndPackaging.</span></span> <span data-ttu-id="09e33-120">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="09e33-120">Click OK.</span></span>  
7. <span data-ttu-id="09e33-121">Expanda a seção Detalhes.</span><span class="sxs-lookup"><span data-stu-id="09e33-121">Expand the Details section.</span></span>
8. <span data-ttu-id="09e33-122">No campo Produto, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="09e33-122">In the Product field, enter or select a value.</span></span>
    * <span data-ttu-id="09e33-123">Selecione o item L0006.</span><span class="sxs-lookup"><span data-stu-id="09e33-123">Select Item L0006.</span></span>  

## <a name="create-kanban-and-view-jobs"></a><span data-ttu-id="09e33-124">Criar um kanban e ver trabalhos</span><span class="sxs-lookup"><span data-stu-id="09e33-124">Create kanban and view jobs</span></span>
1. <span data-ttu-id="09e33-125">Expanda a seção kanbans.</span><span class="sxs-lookup"><span data-stu-id="09e33-125">Expand the Kanbans section.</span></span>
2. <span data-ttu-id="09e33-126">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="09e33-126">Click Add.</span></span>
3. <span data-ttu-id="09e33-127">No campo Número de novos kanbans, insira '1'.</span><span class="sxs-lookup"><span data-stu-id="09e33-127">In the Number of new kanbans field, enter '1'.</span></span>
    * <span data-ttu-id="09e33-128">Isso criará um kanban.</span><span class="sxs-lookup"><span data-stu-id="09e33-128">This will create one kanban.</span></span>  
4. <span data-ttu-id="09e33-129">Defina Quantidade de produto para '3'.</span><span class="sxs-lookup"><span data-stu-id="09e33-129">Set Product quantity to '3'.</span></span>
    * <span data-ttu-id="09e33-130">Kanban processará 3 produtos.</span><span class="sxs-lookup"><span data-stu-id="09e33-130">Kanban will process 3 products.</span></span>  
5. <span data-ttu-id="09e33-131">No campo Data/hora de vencimento, insira uma data e hora.</span><span class="sxs-lookup"><span data-stu-id="09e33-131">In the Due date/time field, enter a date and time.</span></span>
    * <span data-ttu-id="09e33-132">Você pode inserir Hoje.</span><span class="sxs-lookup"><span data-stu-id="09e33-132">You can enter Today.</span></span>  
6. <span data-ttu-id="09e33-133">Clique em Criar.</span><span class="sxs-lookup"><span data-stu-id="09e33-133">Click Create.</span></span>
7. <span data-ttu-id="09e33-134">Clique em Detalhes.</span><span class="sxs-lookup"><span data-stu-id="09e33-134">Click Details.</span></span>
    * <span data-ttu-id="09e33-135">Observe que o kanban tem dois trabalhos do processo do fluxo da produção.</span><span class="sxs-lookup"><span data-stu-id="09e33-135">Notice that the kanban has two process jobs from the production flow.</span></span> <span data-ttu-id="09e33-136">O primeiro é SpeakerAssemblyAndPolish, e o segundo é SpeakerTestAndPackaging.</span><span class="sxs-lookup"><span data-stu-id="09e33-136">The first one is SpeakerAssemblyAndPolish, and the second one is SpeakerTestAndPackaging.</span></span>  
    * <span data-ttu-id="09e33-137">Esta é a última etapa!</span><span class="sxs-lookup"><span data-stu-id="09e33-137">This is the last step!</span></span>  

