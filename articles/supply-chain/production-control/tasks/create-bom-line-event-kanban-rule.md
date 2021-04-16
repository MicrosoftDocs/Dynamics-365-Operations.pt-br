---
title: Criar uma regra kanban de evento da linha BOM
description: Essa tarefa se concentra na configuração necessária para criar uma regra kanban de evento e garantir a fonte para linhas BOM de produção em um ambiente de produção lean e clássico misturado.
author: ChristianRytt
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: KanbanRules, LeanProductionFlowActivityLookup, InventItemIdLookupSimple, ProdTableListPage, ProdTableCreate, InventItemIdLookupPurchase, ProdTable, ProdBOM, ProdParmCostEstimation
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 27d415e146f33224bcbbfb73498040d584e07f10
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5829201"
---
# <a name="create-a-bom-line-event-kanban-rule"></a><span data-ttu-id="c9fa2-103">Criar uma regra kanban de evento da linha BOM</span><span class="sxs-lookup"><span data-stu-id="c9fa2-103">Create a BOM line event kanban rule</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="c9fa2-104">Essa tarefa se concentra na configuração necessária para criar uma regra kanban de evento e garantir a fonte para linhas BOM de produção em um ambiente de produção lean e clássico misturado.</span><span class="sxs-lookup"><span data-stu-id="c9fa2-104">This task focuses on the setup needed to create an event kanban rule to ensure supply for production BOM lines in a mixed lean and classic production environment.</span></span> <span data-ttu-id="c9fa2-105">A empresa de dados demo usada para criar esta tarefa é USMF.</span><span class="sxs-lookup"><span data-stu-id="c9fa2-105">The demo data company used to create this task is USMF.</span></span> <span data-ttu-id="c9fa2-106">Esta tarefa destina-se ao Engenheiro do processo ou Gerente de fluxo de valor, pois eles preparam a produção de um produto novo ou modificado.</span><span class="sxs-lookup"><span data-stu-id="c9fa2-106">This task is intended for the process engineer or the value stream manager, as they prepare production of a new or modified product.</span></span>


## <a name="create-a-new-kanban-rule"></a><span data-ttu-id="c9fa2-107">Criar uma nova regra kanban</span><span class="sxs-lookup"><span data-stu-id="c9fa2-107">Create a new kanban rule</span></span>
1. <span data-ttu-id="c9fa2-108">Vá para Controle de produção > Tarefas periódicas > Cálculo da quantidade kanban > Regras kanban.</span><span class="sxs-lookup"><span data-stu-id="c9fa2-108">Go to Production control > Periodic tasks > Kanban quantity calculation > Kanban rules.</span></span>
2. <span data-ttu-id="c9fa2-109">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="c9fa2-109">Click New.</span></span>
3. <span data-ttu-id="c9fa2-110">No campo Tipo, selecione "Retirada".</span><span class="sxs-lookup"><span data-stu-id="c9fa2-110">In the Type field, select 'Withdrawal'.</span></span>
    * <span data-ttu-id="c9fa2-111">O tipo de retirada é usado para criar kanbans de transferência.</span><span class="sxs-lookup"><span data-stu-id="c9fa2-111">The Withdrawal type is used to create transfer kanbans.</span></span>  
4. <span data-ttu-id="c9fa2-112">No campo Estratégia de reabastecimento, selecione 'Evento'.</span><span class="sxs-lookup"><span data-stu-id="c9fa2-112">In the Replenishment strategy field, select 'Event'.</span></span>
    * <span data-ttu-id="c9fa2-113">A Estratégia de evento está selecionada para criar a transferência de kanbans com base em um evento.</span><span class="sxs-lookup"><span data-stu-id="c9fa2-113">The Event strategy is selected to create the transfer of kanbans based on an event.</span></span> <span data-ttu-id="c9fa2-114">Posteriormente na guia da tarefa, o dispararemos estimando uma ordem de produção.</span><span class="sxs-lookup"><span data-stu-id="c9fa2-114">Later in the task guide, we will trigger it by estimating a production order.</span></span>  
5. <span data-ttu-id="c9fa2-115">No campo Primeira atividade do plano, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="c9fa2-115">In the First plan activity field, enter or select a value.</span></span>
    * <span data-ttu-id="c9fa2-116">Insira ou selecione ReplenishSpeakerComponents.</span><span class="sxs-lookup"><span data-stu-id="c9fa2-116">Enter or select ReplenishSpeakerComponents.</span></span> <span data-ttu-id="c9fa2-117">Essa atividade de transferência tem o depósito de recebimento (saída) e o local 12, o que significa que o material será movido para a localização 12 no depósito 12.</span><span class="sxs-lookup"><span data-stu-id="c9fa2-117">This transfer activity has receipt (output) warehouse and location 12, which means that material will be moved to location 12 in warehouse 12.</span></span>  
6. <span data-ttu-id="c9fa2-118">Expanda a seção Detalhes.</span><span class="sxs-lookup"><span data-stu-id="c9fa2-118">Expand the Details section.</span></span>
7. <span data-ttu-id="c9fa2-119">No campo Produto, insira ou selecione M0001.</span><span class="sxs-lookup"><span data-stu-id="c9fa2-119">In the Product field, enter or select M0001.</span></span>
8. <span data-ttu-id="c9fa2-120">Expanda a seção Eventos.</span><span class="sxs-lookup"><span data-stu-id="c9fa2-120">Expand the Events section.</span></span>
9. <span data-ttu-id="c9fa2-121">No campo Evento de linha BOM, selecione 'Automático'.</span><span class="sxs-lookup"><span data-stu-id="c9fa2-121">In the BOM line event field, select 'Automatic'.</span></span>
    * <span data-ttu-id="c9fa2-122">No campo do evento da linha BOM definido como automático, o kanban será criado para atender às necessidades de material de embalagem para linhas BOM da ordem de produção.</span><span class="sxs-lookup"><span data-stu-id="c9fa2-122">With the BOM line event field set to Automatic, kanban will be created to fulfill material needs for production order BOM lines.</span></span>  
10. <span data-ttu-id="c9fa2-123">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="c9fa2-123">Close the page.</span></span>

## <a name="create-and-modify-a-new-production-order"></a><span data-ttu-id="c9fa2-124">Criar e modificar uma nova ordem de produção</span><span class="sxs-lookup"><span data-stu-id="c9fa2-124">Create and modify a new production order</span></span>
1. <span data-ttu-id="c9fa2-125">Vá para Controle de produção > Ordens de produção > Todas as ordens de produção.</span><span class="sxs-lookup"><span data-stu-id="c9fa2-125">Go to Production control > Production orders > All production orders.</span></span>
2. <span data-ttu-id="c9fa2-126">Clique em Nova ordem de produção.</span><span class="sxs-lookup"><span data-stu-id="c9fa2-126">Click New production order.</span></span>
3. <span data-ttu-id="c9fa2-127">No campo Número do item, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="c9fa2-127">In the Item number field, enter or select a value.</span></span>
    * <span data-ttu-id="c9fa2-128">Insira ou selecione 'L0001'.</span><span class="sxs-lookup"><span data-stu-id="c9fa2-128">Enter or select 'L0001'.</span></span> <span data-ttu-id="c9fa2-129">Nós usamos o item L0001 porque o item M0001 é incluído na BOM para o item L0001.</span><span class="sxs-lookup"><span data-stu-id="c9fa2-129">We use item L0001 because item M0001 is included in the BOM for item L0001.</span></span>  
4. <span data-ttu-id="c9fa2-130">Clique em Criar.</span><span class="sxs-lookup"><span data-stu-id="c9fa2-130">Click Create.</span></span>
5. <span data-ttu-id="c9fa2-131">Na lista, clique no link na linha de L0001.</span><span class="sxs-lookup"><span data-stu-id="c9fa2-131">In the list, click the link in the row for L0001</span></span>
6. <span data-ttu-id="c9fa2-132">Clicar em BOM.</span><span class="sxs-lookup"><span data-stu-id="c9fa2-132">Click BOM.</span></span>
7. <span data-ttu-id="c9fa2-133">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="c9fa2-133">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="c9fa2-134">Clique em Editar.</span><span class="sxs-lookup"><span data-stu-id="c9fa2-134">Click Edit.</span></span>
9. <span data-ttu-id="c9fa2-135">No campo Tipo de linha, selecione "Fornecimento vinculado".</span><span class="sxs-lookup"><span data-stu-id="c9fa2-135">In the Line type field, select 'Pegged supply'.</span></span>
    * <span data-ttu-id="c9fa2-136">O Fornecimento vinculado está selecionado para disparar a criação de fornecimento de um kanban.</span><span class="sxs-lookup"><span data-stu-id="c9fa2-136">Pegged supply is selected to trigger the supply creation of a kanban.</span></span>  
10. <span data-ttu-id="c9fa2-137">Selecione Não no campo Consumo de recurso.</span><span class="sxs-lookup"><span data-stu-id="c9fa2-137">Select No in the Resource consumption field.</span></span>
    * <span data-ttu-id="c9fa2-138">Desmarcar a caixa de seleção de consumo de recurso permite trocar o depósito.</span><span class="sxs-lookup"><span data-stu-id="c9fa2-138">Clearing the check box of Resource consumption lets us change the warehouse.</span></span>  
11. <span data-ttu-id="c9fa2-139">Expanda a seção Dimensões de estoque.</span><span class="sxs-lookup"><span data-stu-id="c9fa2-139">Expand the Inventory dimensions section.</span></span>
12. <span data-ttu-id="c9fa2-140">No campo Depósito, digite '12'.</span><span class="sxs-lookup"><span data-stu-id="c9fa2-140">In the Warehouse field, type '12'.</span></span>
    * <span data-ttu-id="c9fa2-141">O depósito é definido como 12 porque esse é o depósito de saída para a atividade de saída.</span><span class="sxs-lookup"><span data-stu-id="c9fa2-141">Warehouse is set to 12 because this is the output warehouse for the withdrawal activity.</span></span>  
13. <span data-ttu-id="c9fa2-142">No campo Local, digite '12'.</span><span class="sxs-lookup"><span data-stu-id="c9fa2-142">In the Location field, type '12'.</span></span>
    * <span data-ttu-id="c9fa2-143">O local é definido como 12 porque esse é o local de saída para a atividade de saída.</span><span class="sxs-lookup"><span data-stu-id="c9fa2-143">Location is set to 12 because this is the output location of the withdrawal activity.</span></span>  
14. <span data-ttu-id="c9fa2-144">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="c9fa2-144">Close the page.</span></span>
15. <span data-ttu-id="c9fa2-145">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="c9fa2-145">Close the page.</span></span>

## <a name="estimate-the-production-order-and-view-the-kanban-created"></a><span data-ttu-id="c9fa2-146">Estimar a ordem de produção e exibir o kanban criado</span><span class="sxs-lookup"><span data-stu-id="c9fa2-146">Estimate the production order and view the kanban created</span></span>
1. <span data-ttu-id="c9fa2-147">Clique em Estimar.</span><span class="sxs-lookup"><span data-stu-id="c9fa2-147">Click Estimate.</span></span>
    * <span data-ttu-id="c9fa2-148">Para estimar a ordem de produção dispararemos a criação do kanban associada para fornecer o item M0001.</span><span class="sxs-lookup"><span data-stu-id="c9fa2-148">Estimating the production order will trigger the creation of the associated kanban to supply item M0001.</span></span>  
2. <span data-ttu-id="c9fa2-149">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="c9fa2-149">Click OK.</span></span>
3. <span data-ttu-id="c9fa2-150">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="c9fa2-150">Close the page.</span></span>
4. <span data-ttu-id="c9fa2-151">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="c9fa2-151">Close the page.</span></span>
5. <span data-ttu-id="c9fa2-152">Vá para Gerenciamento de informações dos produtos > Lean manufacturing > Regras kanban.</span><span class="sxs-lookup"><span data-stu-id="c9fa2-152">Go to Product information management > Lean manufacturing > Kanban rules.</span></span>
6. <span data-ttu-id="c9fa2-153">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="c9fa2-153">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="c9fa2-154">Selecione a regra kanban de evento criada para o item M0001.</span><span class="sxs-lookup"><span data-stu-id="c9fa2-154">Select the event kanban rule created for item M0001.</span></span>  
7. <span data-ttu-id="c9fa2-155">Expanda a seção kanbans.</span><span class="sxs-lookup"><span data-stu-id="c9fa2-155">Expand the Kanbans section.</span></span>
8. <span data-ttu-id="c9fa2-156">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="c9fa2-156">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="c9fa2-157">Observe o kanban criado para fornecer M0001 para a ordem de produção prevista.</span><span class="sxs-lookup"><span data-stu-id="c9fa2-157">Notice the kanban created to supply M0001 for the estimated production order.</span></span>  
    * <span data-ttu-id="c9fa2-158">Esta é a última etapa!</span><span class="sxs-lookup"><span data-stu-id="c9fa2-158">This is the last step!</span></span>  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]