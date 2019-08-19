---
title: Criar uma regra kanban usando um evento de estoque mínimo
description: Este procedimento é centrado sobre a instalação necessária para criar uma regra kanban usando um evento do estoque mínimo para assegurar-se de que um produto específico esteja sempre disponível em um lugar específico.
author: ChristianRytt
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KanbanRules, LeanProductionFlowActivityLookup, InventItemIdLookupSimple, EcoResProductInformationDialog, EcoResProductDetailsExtended, ReqItemTable, InventLocationIdLookup
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 4b578a664e9e3b6496e5665b2eefd9d75f86ecc3
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/01/2019
ms.locfileid: "1837821"
---
# <a name="create-a-kanban-rule-using-a-minimum-stock-event"></a><span data-ttu-id="02ed2-103">Criar uma regra kanban usando um evento de estoque mínimo</span><span class="sxs-lookup"><span data-stu-id="02ed2-103">Create a kanban rule using a minimum stock event</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="02ed2-104">Este procedimento é centrado sobre a instalação necessária para criar uma regra kanban usando um evento do estoque mínimo para assegurar-se de que um produto específico esteja sempre disponível em um lugar específico.</span><span class="sxs-lookup"><span data-stu-id="02ed2-104">This procedure focuses on the setup needed to create a kanban rule using a minimum stock event to ensure that a specific product is always available at a specific location.</span></span> <span data-ttu-id="02ed2-105">Uma regra kanban é criada para transferir o material ao lugar quando o nível de estoque cai abaixo de 200 partes.</span><span class="sxs-lookup"><span data-stu-id="02ed2-105">A kanban rule is created to transfer material to the location when the inventory level drops below 200 pieces.</span></span> <span data-ttu-id="02ed2-106">Ao executar o processamento do evento de vinculação, os kanbans necessários são criados.</span><span class="sxs-lookup"><span data-stu-id="02ed2-106">By running the Pegging event processing, the needed kanbans are created.</span></span> <span data-ttu-id="02ed2-107">A empresa de dados demo usada para criar esta tarefa é USMF.</span><span class="sxs-lookup"><span data-stu-id="02ed2-107">The demo data company used to create this task is USMF.</span></span> <span data-ttu-id="02ed2-108">Esta tarefa destina-se ao Engenheiro do processo ou Gerente de fluxo de valor, pois eles preparam a produção de um produto novo ou modificado em um ambiente de lean.</span><span class="sxs-lookup"><span data-stu-id="02ed2-108">This task is intended for the process engineer or the value stream manager, as they prepare production of a new or modified product in a lean environment.</span></span>


## <a name="create-a-new-kanban-rule"></a><span data-ttu-id="02ed2-109">Criar uma nova regra kanban</span><span class="sxs-lookup"><span data-stu-id="02ed2-109">Create a new kanban rule</span></span>
1. <span data-ttu-id="02ed2-110">Vá para Gerenciamento de informações dos produtos > Lean manufacturing > Regras kanban.</span><span class="sxs-lookup"><span data-stu-id="02ed2-110">Go to Product information management > Lean manufacturing > Kanban rules.</span></span>
2. <span data-ttu-id="02ed2-111">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="02ed2-111">Click New.</span></span>
3. <span data-ttu-id="02ed2-112">No campo Tipo, selecione "Retirada".</span><span class="sxs-lookup"><span data-stu-id="02ed2-112">In the Type field, select 'Withdrawal'.</span></span>
    * <span data-ttu-id="02ed2-113">Este tipo é usado para criar kanbans de transferência.</span><span class="sxs-lookup"><span data-stu-id="02ed2-113">This type is used to create transfer kanbans.</span></span>  
4. <span data-ttu-id="02ed2-114">No campo Estratégia de reabastecimento, selecione 'Evento'.</span><span class="sxs-lookup"><span data-stu-id="02ed2-114">In the Replenishment strategy field, select 'Event'.</span></span>
    * <span data-ttu-id="02ed2-115">A Estratégia de evento é usada para criar a transferência de kanbans com base em um evento.</span><span class="sxs-lookup"><span data-stu-id="02ed2-115">The Event strategy is used to create the transfer kanbans based on an event.</span></span> <span data-ttu-id="02ed2-116">Mais tarde no procedimento, você provocará kanbans de transferência usando o reabastecimento conservado em estoque.</span><span class="sxs-lookup"><span data-stu-id="02ed2-116">Later in the procedure, you will trigger transfer kanbans by using stock replenishment.</span></span>  
5. <span data-ttu-id="02ed2-117">No campo Primeira atividade do plano, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="02ed2-117">In the First plan activity field, enter or select a value.</span></span>
    * <span data-ttu-id="02ed2-118">Insira ou selecione ReplenishSpeakerComponents.</span><span class="sxs-lookup"><span data-stu-id="02ed2-118">Enter or select ReplenishSpeakerComponents.</span></span> <span data-ttu-id="02ed2-119">Essa atividade de transferência tem o depósito de recebimento (saída) e o local 12, o que significa que o material será movido para a localização 12 no depósito 12.</span><span class="sxs-lookup"><span data-stu-id="02ed2-119">This transfer activity has receipt (output) warehouse and location 12, which means that materials will be moved to location 12 in warehouse 12.</span></span>  
6. <span data-ttu-id="02ed2-120">Expanda a seção Detalhes.</span><span class="sxs-lookup"><span data-stu-id="02ed2-120">Expand the Details section.</span></span>
7. <span data-ttu-id="02ed2-121">No campo Produto, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="02ed2-121">In the Product field, enter or select a value.</span></span>
    * <span data-ttu-id="02ed2-122">Selecione M0007.</span><span class="sxs-lookup"><span data-stu-id="02ed2-122">Select M0007.</span></span>  
8. <span data-ttu-id="02ed2-123">Expanda a seção Eventos.</span><span class="sxs-lookup"><span data-stu-id="02ed2-123">Expand the Events section.</span></span>
9. <span data-ttu-id="02ed2-124">No campo Evento de reabastecimento de estoque, selecione "Lote".</span><span class="sxs-lookup"><span data-stu-id="02ed2-124">In the Stock replenishment event field, select 'Batch'.</span></span>
    * <span data-ttu-id="02ed2-125">Isto cria kanbans para cumprir necessidades materiais no lugar relacionado durante o processamento do evento de vinculação.</span><span class="sxs-lookup"><span data-stu-id="02ed2-125">This creates kanbans to fulfill material needs at the related location during Pegging event processing.</span></span>  

## <a name="set-the-minimum-quantity-for-the-item"></a><span data-ttu-id="02ed2-126">Defina a quantidade mínima para o item</span><span class="sxs-lookup"><span data-stu-id="02ed2-126">Set the minimum quantity for the item</span></span>
1. <span data-ttu-id="02ed2-127">Clique para seguir o link no campo Produto.</span><span class="sxs-lookup"><span data-stu-id="02ed2-127">Click to follow the link in the Product field.</span></span>
2. <span data-ttu-id="02ed2-128">Clique para seguir o link no campo Número de item.</span><span class="sxs-lookup"><span data-stu-id="02ed2-128">Click to follow the link in the Item number field.</span></span>
3. <span data-ttu-id="02ed2-129">Expanda a imagem do produto FactBox.</span><span class="sxs-lookup"><span data-stu-id="02ed2-129">Expand the Product image FactBox.</span></span>
4. <span data-ttu-id="02ed2-130">No Painel de Ação, clique em Plano.</span><span class="sxs-lookup"><span data-stu-id="02ed2-130">On the Action Pane, click Plan.</span></span>
5. <span data-ttu-id="02ed2-131">Clique em Cobertura de item.</span><span class="sxs-lookup"><span data-stu-id="02ed2-131">Click Item coverage.</span></span>
6. <span data-ttu-id="02ed2-132">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="02ed2-132">Click New.</span></span>
7. <span data-ttu-id="02ed2-133">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="02ed2-133">In the list, mark the selected row.</span></span>
8. <span data-ttu-id="02ed2-134">No campo Depósito, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="02ed2-134">In the Warehouse field, enter or select a value.</span></span>
    * <span data-ttu-id="02ed2-135">Defina Depósito como 12.</span><span class="sxs-lookup"><span data-stu-id="02ed2-135">Set Warehouse to 12.</span></span>  
9. <span data-ttu-id="02ed2-136">Ajuste o mínimo para “200".</span><span class="sxs-lookup"><span data-stu-id="02ed2-136">Set Minimum to '200'.</span></span>

## <a name="run-the-batch-event-creation-job"></a><span data-ttu-id="02ed2-137">Execute o trabalho de criação de evento em lotes</span><span class="sxs-lookup"><span data-stu-id="02ed2-137">Run the batch event creation job</span></span>
1. <span data-ttu-id="02ed2-138">Vá para Controle de produção > Tarefas periódicas > Processamento em lote de trabalhos kanban > Processamento de evento de vinculação.</span><span class="sxs-lookup"><span data-stu-id="02ed2-138">Go to Production control > Periodic tasks > Kanban job batch processing > Pegging event processing.</span></span>
2. <span data-ttu-id="02ed2-139">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="02ed2-139">Click OK.</span></span>
3. <span data-ttu-id="02ed2-140">Vá para Gerenciamento de informações dos produtos > Lean manufacturing > Regras kanban.</span><span class="sxs-lookup"><span data-stu-id="02ed2-140">Go to Product information management > Lean manufacturing > Kanban rules.</span></span>
4. <span data-ttu-id="02ed2-141">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="02ed2-141">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="02ed2-142">Selecione a regra kanban que você criou anteriormente.</span><span class="sxs-lookup"><span data-stu-id="02ed2-142">Select the kanban rule that you created earlier.</span></span>  
5. <span data-ttu-id="02ed2-143">Expanda a seção kanbans.</span><span class="sxs-lookup"><span data-stu-id="02ed2-143">Expand the Kanbans section.</span></span>
    * <span data-ttu-id="02ed2-144">Observe que um kanban foi criado para transferir o material necessário para o depósito 12.</span><span class="sxs-lookup"><span data-stu-id="02ed2-144">Notice that a kanban was created to transfer the needed material to warehouse 12.</span></span>  

