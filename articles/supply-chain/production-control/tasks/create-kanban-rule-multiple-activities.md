---
title: Criar uma regra kanban para atividades múltiplas
description: Este procedimento mostra como criar uma regra kanban que inclua atividades múltiplas de um fluxo da produção.
author: ChristianRytt
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: KanbanRules, LeanProductionFlowActivityLookup, KanbanFlowSelection, InventItemIdLookupSimple, KanbanCreateScheduled, Kanban
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 828b01fbb3b94b1fcb9fe8a565b1191a4f4bf630
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5829105"
---
# <a name="create-a-kanban-rule-for-multiple-activities"></a><span data-ttu-id="92146-103">Criar uma regra kanban para atividades múltiplas</span><span class="sxs-lookup"><span data-stu-id="92146-103">Create a kanban rule for multiple activities</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="92146-104">Este procedimento mostra como criar uma regra kanban que inclua atividades múltiplas de um fluxo da produção.</span><span class="sxs-lookup"><span data-stu-id="92146-104">This procedure shows how to create a kanban rule that includes multiple activities from a production flow.</span></span> <span data-ttu-id="92146-105">A empresa de dados demo usada para criar esta tarefa é USMF.</span><span class="sxs-lookup"><span data-stu-id="92146-105">The demo data company used to create this task is USMF.</span></span> <span data-ttu-id="92146-106">Esta tarefa destina-se ao Engenheiro do processo ou Gerente de fluxo de valor, pois eles preparam a produção de um produto novo ou modificado em um ambiente de lean.</span><span class="sxs-lookup"><span data-stu-id="92146-106">This task is intended for the process engineer or the value stream manager, as they prepare production of a new or modified product in a lean environment.</span></span>


## <a name="create-a-new-kanban-rule"></a><span data-ttu-id="92146-107">Criar uma nova regra kanban</span><span class="sxs-lookup"><span data-stu-id="92146-107">Create a new kanban rule</span></span>
1. <span data-ttu-id="92146-108">Vá para Gerenciamento de informações dos produtos > Lean manufacturing > Regras kanban.</span><span class="sxs-lookup"><span data-stu-id="92146-108">Go to Product information management > Lean manufacturing > Kanban rules.</span></span>
2. <span data-ttu-id="92146-109">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="92146-109">Click New.</span></span>
3. <span data-ttu-id="92146-110">No campo Estratégia de reabastecimento, selecione 'Programado'.</span><span class="sxs-lookup"><span data-stu-id="92146-110">In the Replenishment strategy field, select 'Scheduled'.</span></span>
4. <span data-ttu-id="92146-111">No campo Primeira atividade do plano, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="92146-111">In the First plan activity field, enter or select a value.</span></span>
    * <span data-ttu-id="92146-112">Selecione SpeakerAssemblyAndPolish.</span><span class="sxs-lookup"><span data-stu-id="92146-112">Select SpeakerAssemblyAndPolish.</span></span>  
5. <span data-ttu-id="92146-113">Selecione a caixa de verificação múltipla das atividades.</span><span class="sxs-lookup"><span data-stu-id="92146-113">Select the Multiple activities check box.</span></span>
    * <span data-ttu-id="92146-114">O objetivo é incluir mais que uma atividade na regra kanban.</span><span class="sxs-lookup"><span data-stu-id="92146-114">The purpose is to include more than one activity in the kanban rule.</span></span> <span data-ttu-id="92146-115">Você escolhe um trajeto no fluxo da produção quando você seleciona a última atividade do plano.</span><span class="sxs-lookup"><span data-stu-id="92146-115">You choose a path in the production flow when you select the last plan activity.</span></span>  
6. <span data-ttu-id="92146-116">No campo Última atividade do plano, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="92146-116">In the Last plan activity field, enter or select a value.</span></span>
    * <span data-ttu-id="92146-117">Selecione SpeakerTestAndPackaging.</span><span class="sxs-lookup"><span data-stu-id="92146-117">Select SpeakerTestAndPackaging.</span></span> <span data-ttu-id="92146-118">Depois que você seleciona o valor, uma página abre automaticamente.</span><span class="sxs-lookup"><span data-stu-id="92146-118">After you select the value, a page automatically opens.</span></span> <span data-ttu-id="92146-119">Selecione o fluxo kanban SpeakerAssemblyAndPolish > SpeakerTestAndPackaging.</span><span class="sxs-lookup"><span data-stu-id="92146-119">Select the kanban flow SpeakerAssemblyAndPolish > SpeakerTestAndPackaging.</span></span> <span data-ttu-id="92146-120">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="92146-120">Click OK.</span></span>  
7. <span data-ttu-id="92146-121">Expanda a seção Detalhes.</span><span class="sxs-lookup"><span data-stu-id="92146-121">Expand the Details section.</span></span>
8. <span data-ttu-id="92146-122">No campo Produto, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="92146-122">In the Product field, enter or select a value.</span></span>
    * <span data-ttu-id="92146-123">Selecione o item L0006.</span><span class="sxs-lookup"><span data-stu-id="92146-123">Select Item L0006.</span></span>  

## <a name="create-kanban-and-view-jobs"></a><span data-ttu-id="92146-124">Criar um kanban e ver trabalhos</span><span class="sxs-lookup"><span data-stu-id="92146-124">Create kanban and view jobs</span></span>
1. <span data-ttu-id="92146-125">Expanda a seção kanbans.</span><span class="sxs-lookup"><span data-stu-id="92146-125">Expand the Kanbans section.</span></span>
2. <span data-ttu-id="92146-126">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="92146-126">Click Add.</span></span>
3. <span data-ttu-id="92146-127">No campo Número de novos kanbans, insira '1'.</span><span class="sxs-lookup"><span data-stu-id="92146-127">In the Number of new kanbans field, enter '1'.</span></span>
    * <span data-ttu-id="92146-128">Isso criará um kanban.</span><span class="sxs-lookup"><span data-stu-id="92146-128">This will create one kanban.</span></span>  
4. <span data-ttu-id="92146-129">Defina Quantidade de produto para '3'.</span><span class="sxs-lookup"><span data-stu-id="92146-129">Set Product quantity to '3'.</span></span>
    * <span data-ttu-id="92146-130">Kanban processará 3 produtos.</span><span class="sxs-lookup"><span data-stu-id="92146-130">Kanban will process 3 products.</span></span>  
5. <span data-ttu-id="92146-131">No campo Data/hora de vencimento, insira uma data e hora.</span><span class="sxs-lookup"><span data-stu-id="92146-131">In the Due date/time field, enter a date and time.</span></span>
    * <span data-ttu-id="92146-132">Você pode inserir Hoje.</span><span class="sxs-lookup"><span data-stu-id="92146-132">You can enter Today.</span></span>  
6. <span data-ttu-id="92146-133">Clique em Criar.</span><span class="sxs-lookup"><span data-stu-id="92146-133">Click Create.</span></span>
7. <span data-ttu-id="92146-134">Clique em Detalhes.</span><span class="sxs-lookup"><span data-stu-id="92146-134">Click Details.</span></span>
    * <span data-ttu-id="92146-135">Observe que o kanban tem dois trabalhos do processo do fluxo da produção.</span><span class="sxs-lookup"><span data-stu-id="92146-135">Notice that the kanban has two process jobs from the production flow.</span></span> <span data-ttu-id="92146-136">O primeiro é SpeakerAssemblyAndPolish, e o segundo é SpeakerTestAndPackaging.</span><span class="sxs-lookup"><span data-stu-id="92146-136">The first one is SpeakerAssemblyAndPolish, and the second one is SpeakerTestAndPackaging.</span></span>  
    * <span data-ttu-id="92146-137">Esta é a última etapa!</span><span class="sxs-lookup"><span data-stu-id="92146-137">This is the last step!</span></span>  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]