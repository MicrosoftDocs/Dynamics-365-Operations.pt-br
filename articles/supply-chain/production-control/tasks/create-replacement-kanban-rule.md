--- 
title: "Criar uma regra kanban de substituição"
description: "Esse procedimento se concentra em substituir uma regra kanban existente por uma nova regra kanban em uma data específica."
author: ChristianRytt
manager: AnnBe
ms.date: 06/20/2016
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
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 12df41f14973628063b11f20f7368f47b2ad3488
ms.contentlocale: pt-br
ms.lasthandoff: 05/08/2018

---
# <a name="create-a-replacement-kanban-rule"></a><span data-ttu-id="79b81-103">Criar uma regra kanban de substituição</span><span class="sxs-lookup"><span data-stu-id="79b81-103">Create a replacement kanban rule</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="79b81-104">Esse procedimento se concentra em substituir uma regra kanban existente por uma nova regra kanban em uma data específica.</span><span class="sxs-lookup"><span data-stu-id="79b81-104">This procedure focuses on replacing an existing kanban rule with a new kanban rule on a specific date.</span></span> <span data-ttu-id="79b81-105">Isso é útil quando as alterações no fluxo de produção ou as regras de reabastecimento precisam ser coordenadas e programadas.</span><span class="sxs-lookup"><span data-stu-id="79b81-105">This is useful when changes in the production flow or replenishment rules need to be coordinated and scheduled.</span></span> <span data-ttu-id="79b81-106">A empresa de dados de demonstração usada para criar o procedimento é USMF.</span><span class="sxs-lookup"><span data-stu-id="79b81-106">The demo data company used to create procedure is USMF.</span></span> <span data-ttu-id="79b81-107">Este procedimento destina-se ao engenheiro do processo ou gerente de fluxo de valor, pois eles preparam a produção para uma produção de fluxo ou um produto novo ou modificado.</span><span class="sxs-lookup"><span data-stu-id="79b81-107">This procedure is intended for the process engineer or the value stream manager when they prepare production for a changed production flow or a new replenishment rule.</span></span> <span data-ttu-id="79b81-108">Essa tarefa substitui a regra kanban 000022 com uma nova regra e aumenta a quantidade máxima de 48 para 100 da nova regra.</span><span class="sxs-lookup"><span data-stu-id="79b81-108">This task replaces kanban rule 000022 with a new rule and increases the maximum quantity from 48 to 100 for the new rule.</span></span>


## <a name="select-a-kanban-rule-to-replace"></a><span data-ttu-id="79b81-109">Selecionar uma regra kanban para substituir</span><span class="sxs-lookup"><span data-stu-id="79b81-109">Select a kanban rule to replace</span></span>
1. <span data-ttu-id="79b81-110">Vá para Regras kanban.</span><span class="sxs-lookup"><span data-stu-id="79b81-110">Go to Kanban rules.</span></span>
2. <span data-ttu-id="79b81-111">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="79b81-111">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="79b81-112">Selecionar regra kanban 000022.</span><span class="sxs-lookup"><span data-stu-id="79b81-112">Select kanban rule 000022.</span></span>  

## <a name="create-a-replacement-kanban-rule"></a><span data-ttu-id="79b81-113">Criar uma regra kanban de substituição</span><span class="sxs-lookup"><span data-stu-id="79b81-113">Create a replacement kanban rule</span></span>
1. <span data-ttu-id="79b81-114">Clique em Substituir regra kanban.</span><span class="sxs-lookup"><span data-stu-id="79b81-114">Click Replace kanban rule.</span></span>
2. <span data-ttu-id="79b81-115">No campo de data efetiva, insira uma data e hora.</span><span class="sxs-lookup"><span data-stu-id="79b81-115">In the Effective date field, enter a date and time.</span></span>
    * <span data-ttu-id="79b81-116">Selecione uma data futura, como uma semana a partir de agora.</span><span class="sxs-lookup"><span data-stu-id="79b81-116">Select a date in the future, such as one week from now.</span></span> <span data-ttu-id="79b81-117">Esta é a data e a hora em que a nova regra kanban se torna ativa e substitui a regra kanban antiga.</span><span class="sxs-lookup"><span data-stu-id="79b81-117">This is the date and time when the new kanban rule becomes active and replaces the old kanban rule.</span></span>  
    * <span data-ttu-id="79b81-118">Se a regra kanban alterar o caminho no fluxo de produção, outra atividade pode ser marcada.</span><span class="sxs-lookup"><span data-stu-id="79b81-118">If the kanban rule changes the path in the production flow,  another activity can be selected.</span></span>  <span data-ttu-id="79b81-119">Nesse procedimento, manteremos a atividade intocada.</span><span class="sxs-lookup"><span data-stu-id="79b81-119">In this procedure, we will keep the activity untouched.</span></span>  
3. <span data-ttu-id="79b81-120">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="79b81-120">Click OK.</span></span>
    * <span data-ttu-id="79b81-121">Observe que uma nova regra kanban será criada para substituir a regra kanban 000022.</span><span class="sxs-lookup"><span data-stu-id="79b81-121">Notice that a new kanban rule is created to replace kanban rule 000022.</span></span>  
    * <span data-ttu-id="79b81-122">A data efetiva será definida como a data separada quando você substituir a regra kanban.</span><span class="sxs-lookup"><span data-stu-id="79b81-122">The effective date is set according to the date chosen when you replace the kanban rule.</span></span>  
4. <span data-ttu-id="79b81-123">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="79b81-123">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="79b81-124">Selecionar a regra kanban substituída 000022.</span><span class="sxs-lookup"><span data-stu-id="79b81-124">Select the replaced kanban rule 000022.</span></span>  
    * <span data-ttu-id="79b81-125">Observe que a regra kanban substituída tem a mesma data que a data de vencimento porque essa é a data na qual ela vai expirar.</span><span class="sxs-lookup"><span data-stu-id="79b81-125">Notice that the replaced kanban rule has the same date as the Expiration date because this is the date when it will expire.</span></span>  
5. <span data-ttu-id="79b81-126">Na lista, selecione a linha 1.</span><span class="sxs-lookup"><span data-stu-id="79b81-126">In the list, select row 1.</span></span>
    * <span data-ttu-id="79b81-127">Selecionar a nova regra kanban no topo da lista.</span><span class="sxs-lookup"><span data-stu-id="79b81-127">Select the new kanban rule on top of the list.</span></span> <span data-ttu-id="79b81-128">Esta é a regra kanban com o número mais alto.</span><span class="sxs-lookup"><span data-stu-id="79b81-128">This is the kanban rule with the highest kanban rule number.</span></span>  
6. <span data-ttu-id="79b81-129">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="79b81-129">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="79b81-130">Clique no número da regra kanban para abrir a regra kanban.</span><span class="sxs-lookup"><span data-stu-id="79b81-130">Click the kanban rule number to open the kanban rule.</span></span>  

## <a name="modify-maximum-quantity-for-the-replacement-kanban-rule"></a><span data-ttu-id="79b81-131">Modifique a quantidade máxima para a regra kanban de substituição</span><span class="sxs-lookup"><span data-stu-id="79b81-131">Modify maximum quantity for the replacement kanban rule</span></span>
1. <span data-ttu-id="79b81-132">Defina Quantidade máxima como '100'.</span><span class="sxs-lookup"><span data-stu-id="79b81-132">Set Maximum quantity to '100'.</span></span>
    * <span data-ttu-id="79b81-133">Expanda as quantidades FastTab para ver o campo Quantidade máxima.</span><span class="sxs-lookup"><span data-stu-id="79b81-133">Expand the Quantities FastTab to see the Maximum quantity field.</span></span> <span data-ttu-id="79b81-134">Alterar a quantidade máxima para 100 permitirá que até 100 kanbans sejam processados.</span><span class="sxs-lookup"><span data-stu-id="79b81-134">Changing the maximum quantity to 100 will allow up to 100 kanbans to be processed.</span></span>    <span data-ttu-id="79b81-135">Esta é a última etapa da tarefa.</span><span class="sxs-lookup"><span data-stu-id="79b81-135">This is the last step in this task.</span></span>  


