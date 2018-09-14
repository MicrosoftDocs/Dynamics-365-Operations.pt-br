--- 
title: Criar uma regra kanban usando um evento de linha de kanban
description: "Este procedimento cria uma regra kanban usando a linha kanban de evento que ajusta-se para provocar a tração de uma atividade do processo."
author: ChristianRytt
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: KanbanRules, LeanProductionFlowActivityLookup, SalesTableListPage, SalesCreateOrder, SalesTable
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0312b8cfadd45f8e59225e9daba78b9e216cff51
ms.openlocfilehash: bff5f16c1911739a29d50c546c3c2a9ab85c2371
ms.contentlocale: pt-br
ms.lasthandoff: 09/14/2018

---
# <a name="create-a-kanban-rule-using-a-kanban-line-event"></a><span data-ttu-id="cbbdc-103">Criar uma regra kanban usando um evento de linha de kanban</span><span class="sxs-lookup"><span data-stu-id="cbbdc-103">Create a kanban rule using a kanban line event</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="cbbdc-104">Este procedimento cria uma regra kanban usando a linha kanban de evento que ajusta-se para provocar a tração de uma atividade do processo.</span><span class="sxs-lookup"><span data-stu-id="cbbdc-104">This procedure creates a kanban rule by using the kanban line event setting to trigger pull from a process activity.</span></span> <span data-ttu-id="cbbdc-105">A regra kanban é provocada por uma atividade kanban do processo, com uma quantidade igual ou maior que 25 cada.</span><span class="sxs-lookup"><span data-stu-id="cbbdc-105">The kanban rule is triggered by a kanban process activity, with a quantity equal to or greater than 25 each.</span></span> <span data-ttu-id="cbbdc-106">A empresa de dados demo usada para criar esta tarefa é USMF.</span><span class="sxs-lookup"><span data-stu-id="cbbdc-106">The demo data company used to create this task is USMF.</span></span> <span data-ttu-id="cbbdc-107">Esta tarefa destina-se ao Engenheiro do processo ou Gerente de fluxo de valor, pois eles preparam a produção de um produto novo ou modificado em um ambiente de lean.</span><span class="sxs-lookup"><span data-stu-id="cbbdc-107">This task is intended for the process engineer or the value stream manager, as they prepare production of a new or modified product in a lean environment.</span></span>


## <a name="create-a-kanban-rule"></a><span data-ttu-id="cbbdc-108">Criar uma regra kanban</span><span class="sxs-lookup"><span data-stu-id="cbbdc-108">Create a kanban rule</span></span>
1. <span data-ttu-id="cbbdc-109">Vá para Gerenciamento de informações dos produtos > Lean manufacturing > Regras kanban.</span><span class="sxs-lookup"><span data-stu-id="cbbdc-109">Go to Product information management > Lean manufacturing > Kanban rules.</span></span>
2. <span data-ttu-id="cbbdc-110">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="cbbdc-110">Click New.</span></span>
3. <span data-ttu-id="cbbdc-111">No campo Estratégia de reabastecimento, selecione 'Evento'.</span><span class="sxs-lookup"><span data-stu-id="cbbdc-111">In the Replenishment strategy field, select 'Event'.</span></span>
    * <span data-ttu-id="cbbdc-112">Isto gera kanbans diretamente na procura.</span><span class="sxs-lookup"><span data-stu-id="cbbdc-112">This generates kanbans directly from demand.</span></span> <span data-ttu-id="cbbdc-113">É usado para estabelecer as regras que definem uma encenação por encomenda.</span><span class="sxs-lookup"><span data-stu-id="cbbdc-113">It is used to set up rules that define a make-to-order scenario.</span></span>  
4. <span data-ttu-id="cbbdc-114">No campo Primeira atividade do plano, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="cbbdc-114">In the First plan activity field, enter or select a value.</span></span>
    * <span data-ttu-id="cbbdc-115">Insira ou selecione SpeakerAssemblyAndPolish.</span><span class="sxs-lookup"><span data-stu-id="cbbdc-115">Enter or select SpeakerAssemblyAndPolish.</span></span> <span data-ttu-id="cbbdc-116">A primeira atividade de uma regra kanban de fabricação é uma atividade de processo no fluxo de produto.</span><span class="sxs-lookup"><span data-stu-id="cbbdc-116">The first activity of a manufacturing kanban rule is a process activity in the production flow.</span></span> <span data-ttu-id="cbbdc-117">Quando você seleciona a atividade, as datas de validade da atividade são copiadas para as datas de validade da regra kanban.</span><span class="sxs-lookup"><span data-stu-id="cbbdc-117">When you select the activity, the validity dates of the activity are copied to the validity dates of the kanban rule.</span></span>  
5. <span data-ttu-id="cbbdc-118">Expanda a seção Detalhes.</span><span class="sxs-lookup"><span data-stu-id="cbbdc-118">Expand the Details section.</span></span>
6. <span data-ttu-id="cbbdc-119">No campo Produto, digite 'L0001'.</span><span class="sxs-lookup"><span data-stu-id="cbbdc-119">In the Product field, type 'L0001'.</span></span>
7. <span data-ttu-id="cbbdc-120">Expanda a seção Eventos.</span><span class="sxs-lookup"><span data-stu-id="cbbdc-120">Expand the Events section.</span></span>
8. <span data-ttu-id="cbbdc-121">No campo Evento de linha Kanban, selecione 'Automático'.</span><span class="sxs-lookup"><span data-stu-id="cbbdc-121">In the Kanban line event field, select 'Automatic'.</span></span>
    * <span data-ttu-id="cbbdc-122">Isto gera os kanbans do evento por encomenda.</span><span class="sxs-lookup"><span data-stu-id="cbbdc-122">This generates event kanbans on demand.</span></span>  <span data-ttu-id="cbbdc-123">Este campo é usado para definir regras kanban que reabastecem o material necessário para uma atividade de processo downstream.</span><span class="sxs-lookup"><span data-stu-id="cbbdc-123">The field is used to configure kanban rules that replenish material that is required for a downstream process activity.</span></span> <span data-ttu-id="cbbdc-124">Quando você seleciona automático, os kanbans do evento são criados com a procura.</span><span class="sxs-lookup"><span data-stu-id="cbbdc-124">When you select Automatic, the event kanbans are created with the demand.</span></span> <span data-ttu-id="cbbdc-125">Este ajuste é recomendado se você espera executar no mesmo dia a produção.</span><span class="sxs-lookup"><span data-stu-id="cbbdc-125">This setting is recommended if you expect to execute production on the same day.</span></span>  
9. <span data-ttu-id="cbbdc-126">Defina Quantidade mínima de eventos como '25'.</span><span class="sxs-lookup"><span data-stu-id="cbbdc-126">Set Minimum event quantity to '25'.</span></span>
    * <span data-ttu-id="cbbdc-127">Os kanbans de evento são gerados quando a quantidade da demanda é igual ou maior do que este campo.</span><span class="sxs-lookup"><span data-stu-id="cbbdc-127">Event kanbans are generated when the demand quantity is equal to or more than this field.</span></span> <span data-ttu-id="cbbdc-128">Isto é útil se você quer produzir uma quantidade da ordem menor do que este campo em uma máquina e maior do que este campo em uma outra máquina.</span><span class="sxs-lookup"><span data-stu-id="cbbdc-128">This is useful if you want to produce an order quantity less than this field on one machine and more than this field on another machine.</span></span>  
10. <span data-ttu-id="cbbdc-129">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="cbbdc-129">Click Save.</span></span>

## <a name="create-sales-order-and-trigger-kanban-chain"></a><span data-ttu-id="cbbdc-130">Crie a corrente kanban da ordem e do disparador de vendas</span><span class="sxs-lookup"><span data-stu-id="cbbdc-130">Create sales order and trigger kanban chain</span></span>
1. <span data-ttu-id="cbbdc-131">Vá para Vendas e marketing > Ordens de venda > Todas as ordens de venda.</span><span class="sxs-lookup"><span data-stu-id="cbbdc-131">Go to Sales and marketing > Sales orders > All sales orders.</span></span>
2. <span data-ttu-id="cbbdc-132">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="cbbdc-132">Click New.</span></span>
3. <span data-ttu-id="cbbdc-133">No campo Conta de cliente, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="cbbdc-133">In the Customer account field, enter or select a value.</span></span>
    * <span data-ttu-id="cbbdc-134">Selecione a conta de Cliente US-003, Forest Wholesales.</span><span class="sxs-lookup"><span data-stu-id="cbbdc-134">Select Customer account US-003, Forest Wholesales.</span></span>  
4. <span data-ttu-id="cbbdc-135">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="cbbdc-135">Click OK.</span></span>
5. <span data-ttu-id="cbbdc-136">No campo Número do item, digite 'L0001'.</span><span class="sxs-lookup"><span data-stu-id="cbbdc-136">In the Item number field, type 'L0001'.</span></span>
    * <span data-ttu-id="cbbdc-137">L0001 é o item para o qual você criou a regra kanban.</span><span class="sxs-lookup"><span data-stu-id="cbbdc-137">L0001 is the item for which you created the kanban rule.</span></span>  
6. <span data-ttu-id="cbbdc-138">Defina a quantidade como '27'.</span><span class="sxs-lookup"><span data-stu-id="cbbdc-138">Set Quantity to '27'.</span></span>
    * <span data-ttu-id="cbbdc-139">Como 27 é mais alto do que a quantidade mínima de 25 na regra kanban, este provocará um evento kanban.</span><span class="sxs-lookup"><span data-stu-id="cbbdc-139">Because 27 is higher than the minimum quantity of 25 on the kanban rule, this will trigger an event kanban.</span></span>  
7. <span data-ttu-id="cbbdc-140">No campo Site, digite '1'.</span><span class="sxs-lookup"><span data-stu-id="cbbdc-140">In the Site field, type '1'.</span></span>
8. <span data-ttu-id="cbbdc-141">No campo Depósito, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="cbbdc-141">In the Warehouse field, enter or select a value.</span></span>
    * <span data-ttu-id="cbbdc-142">Selecione depósito 13.</span><span class="sxs-lookup"><span data-stu-id="cbbdc-142">Select warehouse 13.</span></span>  
9. <span data-ttu-id="cbbdc-143">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="cbbdc-143">Click Save.</span></span>

## <a name="view-the-kanban-generated-by-the-kanban-rule"></a><span data-ttu-id="cbbdc-144">Veja o kanban gerado pela regra kanban</span><span class="sxs-lookup"><span data-stu-id="cbbdc-144">View the kanban generated by the kanban rule</span></span>
1. <span data-ttu-id="cbbdc-145">Vá para Gerenciamento de informações dos produtos > Lean manufacturing > Regras kanban.</span><span class="sxs-lookup"><span data-stu-id="cbbdc-145">Go to Product information management > Lean manufacturing > Kanban rules.</span></span>
2. <span data-ttu-id="cbbdc-146">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="cbbdc-146">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="cbbdc-147">Expanda a seção kanbans.</span><span class="sxs-lookup"><span data-stu-id="cbbdc-147">Expand the Kanbans section.</span></span>
    * <span data-ttu-id="cbbdc-148">Observe que um kanban de 27 foi criado para processar a atividade baseada na regra kanban criada.</span><span class="sxs-lookup"><span data-stu-id="cbbdc-148">Notice that a kanban for 27 was created to process the  activity based on the created kanban rule.</span></span>  
    * <span data-ttu-id="cbbdc-149">Esta é a última etapa.</span><span class="sxs-lookup"><span data-stu-id="cbbdc-149">This is the last step.</span></span>  


