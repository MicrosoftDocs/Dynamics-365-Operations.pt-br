--- 
title: "Criar uma regra kanban para atividades múltiplas"
description: "Este procedimento mostra como criar uma regra kanban que inclua atividades múltiplas de um fluxo da produção."
author: ChristianRytt
manager: AnnBe
ms.date: 08/24/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: d6d0c50da3124553124b65f6ba0e1c5ed35e8613
ms.contentlocale: pt-br
ms.lasthandoff: 08/29/2017

---
# <a name="create-a-kanban-rule-for-multiple-activities"></a><span data-ttu-id="d603b-103">Criar uma regra kanban para atividades múltiplas</span><span class="sxs-lookup"><span data-stu-id="d603b-103">Create a kanban rule for multiple activities</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="d603b-104">Este procedimento mostra como criar uma regra kanban que inclua atividades múltiplas de um fluxo da produção.</span><span class="sxs-lookup"><span data-stu-id="d603b-104">This procedure shows how to create a kanban rule that includes multiple activities from a production flow.</span></span> <span data-ttu-id="d603b-105">A empresa de dados demo usada para criar esta tarefa é USMF.</span><span class="sxs-lookup"><span data-stu-id="d603b-105">The demo data company used to create this task is USMF.</span></span> <span data-ttu-id="d603b-106">Esta tarefa destina-se ao Engenheiro do processo ou Gerente de fluxo de valor, pois eles preparam a produção de um produto novo ou modificado em um ambiente de lean.</span><span class="sxs-lookup"><span data-stu-id="d603b-106">This task is intended for the process engineer or the value stream manager, as they prepare production of a new or modified product in a lean environment.</span></span>


## <a name="create-a-new-kanban-rule"></a><span data-ttu-id="d603b-107">Criar uma nova regra kanban</span><span class="sxs-lookup"><span data-stu-id="d603b-107">Create a new kanban rule</span></span>
1. <span data-ttu-id="d603b-108">Vá para Gerenciamento de informações dos produtos > Lean manufacturing > Regras kanban.</span><span class="sxs-lookup"><span data-stu-id="d603b-108">Go to Product information management > Lean manufacturing > Kanban rules.</span></span>
2. <span data-ttu-id="d603b-109">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="d603b-109">Click New.</span></span>
3. <span data-ttu-id="d603b-110">No campo Estratégia de reabastecimento, selecione 'Programado'.</span><span class="sxs-lookup"><span data-stu-id="d603b-110">In the Replenishment strategy field, select 'Scheduled'.</span></span>
4. <span data-ttu-id="d603b-111">No campo Primeira atividade do plano, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="d603b-111">In the First plan activity field, enter or select a value.</span></span>
    * <span data-ttu-id="d603b-112">Selecione SpeakerAssemblyAndPolish.</span><span class="sxs-lookup"><span data-stu-id="d603b-112">Select SpeakerAssemblyAndPolish.</span></span>  
5. <span data-ttu-id="d603b-113">Selecione a caixa de verificação múltipla das atividades.</span><span class="sxs-lookup"><span data-stu-id="d603b-113">Select the Multiple activities check box.</span></span>
    * <span data-ttu-id="d603b-114">O objetivo é incluir mais que uma atividade na regra kanban.</span><span class="sxs-lookup"><span data-stu-id="d603b-114">The purpose is to include more than one activity in the kanban rule.</span></span> <span data-ttu-id="d603b-115">Você escolhe um trajeto no fluxo da produção quando você seleciona a última atividade do plano.</span><span class="sxs-lookup"><span data-stu-id="d603b-115">You choose a path in the production flow when you select the last plan activity.</span></span>  
6. <span data-ttu-id="d603b-116">No campo Última atividade do plano, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="d603b-116">In the Last plan activity field, enter or select a value.</span></span>
    * <span data-ttu-id="d603b-117">Selecione SpeakerTestAndPackaging.</span><span class="sxs-lookup"><span data-stu-id="d603b-117">Select SpeakerTestAndPackaging.</span></span> <span data-ttu-id="d603b-118">Depois que você seleciona o valor, uma página abre automaticamente.</span><span class="sxs-lookup"><span data-stu-id="d603b-118">After you select the value, a page automatically opens.</span></span> <span data-ttu-id="d603b-119">Selecione o fluxo kanban SpeakerAssemblyAndPolish > SpeakerTestAndPackaging.</span><span class="sxs-lookup"><span data-stu-id="d603b-119">Select the kanban flow SpeakerAssemblyAndPolish > SpeakerTestAndPackaging.</span></span> <span data-ttu-id="d603b-120">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="d603b-120">Click OK.</span></span>  
7. <span data-ttu-id="d603b-121">Expanda a seção Detalhes.</span><span class="sxs-lookup"><span data-stu-id="d603b-121">Expand the Details section.</span></span>
8. <span data-ttu-id="d603b-122">No campo Produto, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="d603b-122">In the Product field, enter or select a value.</span></span>
    * <span data-ttu-id="d603b-123">Selecione o item L0006.</span><span class="sxs-lookup"><span data-stu-id="d603b-123">Select Item L0006.</span></span>  

## <a name="create-kanban-and-view-jobs"></a><span data-ttu-id="d603b-124">Criar um kanban e ver trabalhos</span><span class="sxs-lookup"><span data-stu-id="d603b-124">Create kanban and view jobs</span></span>
1. <span data-ttu-id="d603b-125">Expanda a seção kanbans.</span><span class="sxs-lookup"><span data-stu-id="d603b-125">Expand the Kanbans section.</span></span>
2. <span data-ttu-id="d603b-126">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="d603b-126">Click Add.</span></span>
3. <span data-ttu-id="d603b-127">No campo Número de novos kanbans, insira '1'.</span><span class="sxs-lookup"><span data-stu-id="d603b-127">In the Number of new kanbans field, enter '1'.</span></span>
    * <span data-ttu-id="d603b-128">Isso criará um kanban.</span><span class="sxs-lookup"><span data-stu-id="d603b-128">This will create one kanban.</span></span>  
4. <span data-ttu-id="d603b-129">Defina Quantidade de produto para '3'.</span><span class="sxs-lookup"><span data-stu-id="d603b-129">Set Product quantity to '3'.</span></span>
    * <span data-ttu-id="d603b-130">Kanban processará 3 produtos.</span><span class="sxs-lookup"><span data-stu-id="d603b-130">Kanban will process 3 products.</span></span>  
5. <span data-ttu-id="d603b-131">No campo Data/hora de vencimento, insira uma data e hora.</span><span class="sxs-lookup"><span data-stu-id="d603b-131">In the Due date/time field, enter a date and time.</span></span>
    * <span data-ttu-id="d603b-132">Você pode inserir Hoje.</span><span class="sxs-lookup"><span data-stu-id="d603b-132">You can enter Today.</span></span>  
6. <span data-ttu-id="d603b-133">Clique em Criar.</span><span class="sxs-lookup"><span data-stu-id="d603b-133">Click Create.</span></span>
7. <span data-ttu-id="d603b-134">Clique em Detalhes.</span><span class="sxs-lookup"><span data-stu-id="d603b-134">Click Details.</span></span>
    * <span data-ttu-id="d603b-135">Observe que o kanban tem dois trabalhos do processo do fluxo da produção.</span><span class="sxs-lookup"><span data-stu-id="d603b-135">Notice that the kanban has two process jobs from the production flow.</span></span> <span data-ttu-id="d603b-136">O primeiro é SpeakerAssemblyAndPolish, e o segundo é SpeakerTestAndPackaging.</span><span class="sxs-lookup"><span data-stu-id="d603b-136">The first one is SpeakerAssemblyAndPolish, and the second one is SpeakerTestAndPackaging.</span></span>  
    * <span data-ttu-id="d603b-137">Esta é a última etapa!</span><span class="sxs-lookup"><span data-stu-id="d603b-137">This is the last step!</span></span>  


