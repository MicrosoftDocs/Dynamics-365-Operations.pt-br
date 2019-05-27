---
title: Criar uma regra kanban de evento de vendas
description: Este procedimento tem como foco a configuração necessária para criar uma regra kanban que é necessária durante a criação da ordem de vendas.
author: ChristianRytt
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KanbanRules, LeanProductionFlowActivityLookup, InventItemIdLookupSimple, SalesTableListPage, SalesCreateOrder, SalesTable, LeanPeggingTree
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d2bee6e81acd029406c95237f0b4ba4ab2565ea1
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1573058"
---
# <a name="create-a-sales-event-kanban-rule"></a><span data-ttu-id="7b9fa-103">Criar uma regra kanban de evento de vendas</span><span class="sxs-lookup"><span data-stu-id="7b9fa-103">Create a sales event kanban rule</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="7b9fa-104">Este procedimento tem como foco a configuração necessária para criar uma regra kanban que é necessária durante a criação da ordem de vendas.</span><span class="sxs-lookup"><span data-stu-id="7b9fa-104">This procedure focuses on the setup needed to create a kanban rule that is triggered during sales order creation.</span></span> <span data-ttu-id="7b9fa-105">A regra kanban de evento reabastece requisitos que têm origem nas linhas de ordem de vendas.</span><span class="sxs-lookup"><span data-stu-id="7b9fa-105">The event kanban rule replenishes requirements that originate from sales order lines.</span></span> <span data-ttu-id="7b9fa-106">A empresa de dados demo usada para criar este procedimento é USMF.</span><span class="sxs-lookup"><span data-stu-id="7b9fa-106">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="7b9fa-107">Destina-se ao engenheiro do processo ou gerente de fluxo de valor, pois eles preparam a produção de um produto novo ou modificado.</span><span class="sxs-lookup"><span data-stu-id="7b9fa-107">It is intended for the process engineer or the value stream manager as they prepare production of a new or modified product.</span></span>




## <a name="create-a-new-kanban-rule"></a><span data-ttu-id="7b9fa-108">Criar uma nova regra kanban</span><span class="sxs-lookup"><span data-stu-id="7b9fa-108">Create a new kanban rule</span></span>
1. <span data-ttu-id="7b9fa-109">Vá para Regras kanban.</span><span class="sxs-lookup"><span data-stu-id="7b9fa-109">Go to Kanban rules.</span></span>
2. <span data-ttu-id="7b9fa-110">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="7b9fa-110">Click New.</span></span>
3. <span data-ttu-id="7b9fa-111">No campo Estratégia de reabastecimento, selecione 'Evento'.</span><span class="sxs-lookup"><span data-stu-id="7b9fa-111">In the Replenishment strategy field, select 'Event'.</span></span>
    * <span data-ttu-id="7b9fa-112">Selecionar Evento significa que a regra kanban é ativada por um evento, como a criação de uma linha da ordem de venda.</span><span class="sxs-lookup"><span data-stu-id="7b9fa-112">Selecting Event means that the kanban rule is triggered by an event, for example, creation of a sales order line.</span></span>   <span data-ttu-id="7b9fa-113">Isso é aplicado a áreas nas quais cada kanban deve cobrir uma demanda específica.</span><span class="sxs-lookup"><span data-stu-id="7b9fa-113">This is applied to areas where each kanban should cover a specific demand.</span></span>  
4. <span data-ttu-id="7b9fa-114">No campo Primeira atividade do plano, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="7b9fa-114">In the First plan activity field, enter or select a value.</span></span>
    * <span data-ttu-id="7b9fa-115">Selecione Montagem final.</span><span class="sxs-lookup"><span data-stu-id="7b9fa-115">Select Final assembly.</span></span>  
5. <span data-ttu-id="7b9fa-116">Expanda a seção Detalhes.</span><span class="sxs-lookup"><span data-stu-id="7b9fa-116">Expand the Details section.</span></span>
6. <span data-ttu-id="7b9fa-117">No campo Produto, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="7b9fa-117">In the Product field, enter or select a value.</span></span>
    * <span data-ttu-id="7b9fa-118">Selecione L0050.</span><span class="sxs-lookup"><span data-stu-id="7b9fa-118">Select L0050.</span></span>  

## <a name="define-an-event"></a><span data-ttu-id="7b9fa-119">Definir um evento</span><span class="sxs-lookup"><span data-stu-id="7b9fa-119">Define an event</span></span>
1. <span data-ttu-id="7b9fa-120">Expanda a seção Eventos.</span><span class="sxs-lookup"><span data-stu-id="7b9fa-120">Expand the Events section.</span></span>
2. <span data-ttu-id="7b9fa-121">No campo Evento de vendas, selecione 'Automático'.</span><span class="sxs-lookup"><span data-stu-id="7b9fa-121">In the Sales event field, select 'Automatic'.</span></span>
    * <span data-ttu-id="7b9fa-122">Selecionando o evento de vendas Automático, a regra kanban será acionada automaticamente quando uma linha de vendas corresponder ao produto e local de recebimento.</span><span class="sxs-lookup"><span data-stu-id="7b9fa-122">By selecting the sales event Automatic, this kanban rule will be triggered automatically when a sales line matches the product and receipt location.</span></span> <span data-ttu-id="7b9fa-123">Neste procedimento, é o produto L0050 no depósito 13.</span><span class="sxs-lookup"><span data-stu-id="7b9fa-123">In this procedure, it is product L0050 on warehouse 13.</span></span>  
3. <span data-ttu-id="7b9fa-124">Defina Quantidade mínima de eventos como '50'.</span><span class="sxs-lookup"><span data-stu-id="7b9fa-124">Set Minimum event quantity to '50'.</span></span>
    * <span data-ttu-id="7b9fa-125">Com uma quantidade mínima de eventos de 50, a regra kanban será acionada somente por eventos com uma quantidade de 50 ou mais.</span><span class="sxs-lookup"><span data-stu-id="7b9fa-125">With a minimum event quantity of 50, the kanban rule will only be triggered by events with a quantity of 50 or more.</span></span>  
4. <span data-ttu-id="7b9fa-126">Expanda a seção Fluxo de produção.</span><span class="sxs-lookup"><span data-stu-id="7b9fa-126">Expand the Production flow section.</span></span>
    * <span data-ttu-id="7b9fa-127">Observe que o local de recebimento é o depósito 13.</span><span class="sxs-lookup"><span data-stu-id="7b9fa-127">Notice that the Receipt location is warehouse 13.</span></span> <span data-ttu-id="7b9fa-128">Isso significa que essa regra kanban será acionada quanto a esse local.</span><span class="sxs-lookup"><span data-stu-id="7b9fa-128">This means that this kanban rule will be triggered for this location.</span></span>  
    * <span data-ttu-id="7b9fa-129">Neste exemplo, uma linha de vendas do produto L0050, com uma quantidade de 50 ou mais, no depósito 13, acionará a regra kanban.</span><span class="sxs-lookup"><span data-stu-id="7b9fa-129">In this example, a sales line for product L0050, with a quantity of 50 or more, on warehouse 13, will trigger this kanban rule.</span></span>  

## <a name="create-sales-line-to-trigger-event-kanban-rule"></a><span data-ttu-id="7b9fa-130">Criar linha de vendas para acionar regra kanban de evento</span><span class="sxs-lookup"><span data-stu-id="7b9fa-130">Create sales line to trigger event kanban rule</span></span>
1. <span data-ttu-id="7b9fa-131">Ir para Todas as ordens de venda.</span><span class="sxs-lookup"><span data-stu-id="7b9fa-131">Go to All sales orders.</span></span>
    * <span data-ttu-id="7b9fa-132">Um aviso é exibido quando a regra kanban é salva, o que significa que kanbans serão criados em tempo real durante a produção de ordens de vendas.</span><span class="sxs-lookup"><span data-stu-id="7b9fa-132">A warning is shown when the kanban rule is saved, which means that kanbans will be created in real-time during sales order creation.</span></span>  
2. <span data-ttu-id="7b9fa-133">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="7b9fa-133">Click New.</span></span>
3. <span data-ttu-id="7b9fa-134">No campo Conta de cliente, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="7b9fa-134">In the Customer account field, enter or select a value.</span></span>
    * <span data-ttu-id="7b9fa-135">Por exemplo, selecione US-003.</span><span class="sxs-lookup"><span data-stu-id="7b9fa-135">For example, select US-003.</span></span>  
4. <span data-ttu-id="7b9fa-136">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="7b9fa-136">Click OK.</span></span>
5. <span data-ttu-id="7b9fa-137">No campo Número do item, digite 'L0050'.</span><span class="sxs-lookup"><span data-stu-id="7b9fa-137">In the Item number field, type 'L0050'.</span></span>
6. <span data-ttu-id="7b9fa-138">No campo Site, digite '1'.</span><span class="sxs-lookup"><span data-stu-id="7b9fa-138">In the Site field, type '1'.</span></span>
    * <span data-ttu-id="7b9fa-139">Selecione Site 1, pois o depósito 13 está no site 1.</span><span class="sxs-lookup"><span data-stu-id="7b9fa-139">Select Site 1 because Warehouse 13 is on Site 1.</span></span>  
7. <span data-ttu-id="7b9fa-140">No campo Depósito, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="7b9fa-140">In the Warehouse field, enter or select a value.</span></span>
    * <span data-ttu-id="7b9fa-141">Defina Depósito como 13.</span><span class="sxs-lookup"><span data-stu-id="7b9fa-141">Set Warehouse to 13.</span></span>  
8. <span data-ttu-id="7b9fa-142">Defina a quantidade como '75'.</span><span class="sxs-lookup"><span data-stu-id="7b9fa-142">Set Quantity to '75'.</span></span>
    * <span data-ttu-id="7b9fa-143">Insira uma quantidade de 50 ou mais, para acionar a regra kanban criada.</span><span class="sxs-lookup"><span data-stu-id="7b9fa-143">Enter a quantity of 50 or greater, to trigger the created kanban rule.</span></span>  

## <a name="verify-that-kanban-is-created"></a><span data-ttu-id="7b9fa-144">Verifique se o kanban foi criado.</span><span class="sxs-lookup"><span data-stu-id="7b9fa-144">Verify that kanban is created</span></span>
1. <span data-ttu-id="7b9fa-145">Clique em Produtos e fornecimento.</span><span class="sxs-lookup"><span data-stu-id="7b9fa-145">Click Product and supply.</span></span>
2. <span data-ttu-id="7b9fa-146">Clique em Exibir árvore de vinculação.</span><span class="sxs-lookup"><span data-stu-id="7b9fa-146">Click View pegging tree.</span></span>
    * <span data-ttu-id="7b9fa-147">Note que um kanban com a mesma quantidade como a linha de vendas é criado.</span><span class="sxs-lookup"><span data-stu-id="7b9fa-147">Notice that a kanban with the same quantity as the sales line is created.</span></span> <span data-ttu-id="7b9fa-148">Você também pode ver as questões materiais necessárias para produzir L0050.</span><span class="sxs-lookup"><span data-stu-id="7b9fa-148">You can also see the material issues needed to produce L0050.</span></span> <span data-ttu-id="7b9fa-149">Esta é a última etapa do procedimento.</span><span class="sxs-lookup"><span data-stu-id="7b9fa-149">This is the last step in this procedure.</span></span>  

