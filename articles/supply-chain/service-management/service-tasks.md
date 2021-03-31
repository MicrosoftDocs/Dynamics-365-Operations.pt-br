---
title: Visão geral de tarefas de serviço
description: Use tarefas de serviço para descrever a tarefa a ser concluída durante uma ordem de serviço. Os técnicos e clientes podem consultar essas informações.
author: ShylaThompson
manager: tfehr
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMAServiceTask
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 9dfeddcf754ccaf1f5fb5d3f20ca771145c5f2a1
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5223305"
---
# <a name="service-tasks-overview"></a><span data-ttu-id="15095-104">Visão geral de tarefas de serviço</span><span class="sxs-lookup"><span data-stu-id="15095-104">Service tasks overview</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="15095-105">Use tarefas de serviço para descrever a tarefa a ser concluída durante uma ordem de serviço.</span><span class="sxs-lookup"><span data-stu-id="15095-105">Use service tasks to describe the task to be completed during a service order.</span></span>
<span data-ttu-id="15095-106">Os técnicos e clientes podem consultar essas informações.</span><span class="sxs-lookup"><span data-stu-id="15095-106">Both technicians and customers can see this information.</span></span>

<span data-ttu-id="15095-107">Crie tarefas de serviço na página **Tarefas de serviço** e associe tarefas de serviço a uma ordem de serviço ou a um contrato de serviço específico por meio da criação de relações de tarefa de serviço.</span><span class="sxs-lookup"><span data-stu-id="15095-107">You create service tasks in the **Service tasks** page, and you associate service tasks with a specific service agreement or service order by creating service task relations.</span></span> <span data-ttu-id="15095-108">Sempre que criar uma relação de tarefas de serviço, você poderá criar o seguinte:</span><span class="sxs-lookup"><span data-stu-id="15095-108">Every time that you create a service task relation, you can create the following:</span></span>

-  <span data-ttu-id="15095-109">Notas internas da tarefa, como solicitações técnicas detalhadas da tarefa que devem ser de conhecimento do técnico.</span><span class="sxs-lookup"><span data-stu-id="15095-109">Internal notes for the task, such as detailed technical requests for the task that are important for the technician to know.</span></span>

-  <span data-ttu-id="15095-110">Notas externas que o cliente pode ver.</span><span class="sxs-lookup"><span data-stu-id="15095-110">External notes that the customer can see.</span></span> <span data-ttu-id="15095-111">Essas podem oferecer uma explicação menos técnica da tarefa que está sendo executada, de acordo com o contrato entre o cliente e a empresa de serviço.</span><span class="sxs-lookup"><span data-stu-id="15095-111">These might provide a less technical explanation of the task that is being completed, according to the agreement between the customer and the service company.</span></span>

<span data-ttu-id="15095-112">Quando tiver configurado uma relação de tarefas de serviço entre uma tarefa de serviço e uma ordem de serviço ou um contrato de serviço, você poderá especificar essa tarefa de serviço quando criar linhas de ordem de serviço ou linhas de contrato de serviço para a ordem de serviço ou o contrato de serviço atual.</span><span class="sxs-lookup"><span data-stu-id="15095-112">When you have set up a service task relation between a service task and a service order or service agreement, you can specify this service task when you create service order lines or service agreement lines for the current service order or service agreement.</span></span>

<span data-ttu-id="15095-113">Ao gerar ordens de serviço de um contrato de serviço, você poderá usar as tarefas de serviço atribuídas a cada linha do contrato de serviço nas linhas da ordem de serviço em ordens de serviço.</span><span class="sxs-lookup"><span data-stu-id="15095-113">When you generate service orders from a service agreement, you can use the service tasks that are assigned to each service agreement line to group service order lines into service orders.</span></span>

## <a name="create-a-service-task"></a><span data-ttu-id="15095-114">Criar uma tarefa de serviço</span><span class="sxs-lookup"><span data-stu-id="15095-114">Create a service task</span></span>

1. <span data-ttu-id="15095-115">Clique em **Gerenciamento de serviços** \> **Configuração** \> **Tarefas de serviços**.</span><span class="sxs-lookup"><span data-stu-id="15095-115">Click **Service management** \> **Setup** \> **Service tasks**.</span></span>
2. <span data-ttu-id="15095-116">Crie uma nova linha.</span><span class="sxs-lookup"><span data-stu-id="15095-116">Create a new line.</span></span>
3. <span data-ttu-id="15095-117">Insira a ID e a descrição do serviço.</span><span class="sxs-lookup"><span data-stu-id="15095-117">Enter the service ID and description.</span></span>

## <a name="example"></a><span data-ttu-id="15095-118">Exemplo</span><span class="sxs-lookup"><span data-stu-id="15095-118">Example</span></span>

<span data-ttu-id="15095-119">Um técnico deve executar dois trabalhos em uma caixa de embreagens (objeto de serviço GB-1234) no site de um cliente.</span><span class="sxs-lookup"><span data-stu-id="15095-119">A technician must complete two jobs on a gearbox (service object GB-1234) at a customer site.</span></span> <span data-ttu-id="15095-120">Um contrato de serviço é criado para o cliente, e várias transações são associadas aos trabalhos.</span><span class="sxs-lookup"><span data-stu-id="15095-120">A service agreement is created for the customer, and several transactions are associated with the jobs.</span></span> <span data-ttu-id="15095-121">O contrato de serviço e as linhas de contrato de serviço para os dois trabalhos são as seguintes:</span><span class="sxs-lookup"><span data-stu-id="15095-121">The service agreement and service agreement lines for the two jobs are as follows:</span></span>

### <a name="service-agreement"></a><span data-ttu-id="15095-122">Contrato de serviço</span><span class="sxs-lookup"><span data-stu-id="15095-122">Service agreement</span></span>

| <span data-ttu-id="15095-123">Project</span><span class="sxs-lookup"><span data-stu-id="15095-123">Project</span></span> | <span data-ttu-id="15095-124">Contrato de serviço</span><span class="sxs-lookup"><span data-stu-id="15095-124">Service agreement</span></span> | <span data-ttu-id="15095-125">descrição</span><span class="sxs-lookup"><span data-stu-id="15095-125">Description</span></span>                                  | <span data-ttu-id="15095-126">Agrupar</span><span class="sxs-lookup"><span data-stu-id="15095-126">Group</span></span>   |
|---------|-------------------|----------------------------------------------|---------|
| <span data-ttu-id="15095-127">9012</span><span class="sxs-lookup"><span data-stu-id="15095-127">9012</span></span>    | <span data-ttu-id="15095-128">000008\_001</span><span class="sxs-lookup"><span data-stu-id="15095-128">000008\_001</span></span>       | <span data-ttu-id="15095-129">Inspeção e substituição de rotina - GB-1234</span><span class="sxs-lookup"><span data-stu-id="15095-129">Inspection and routine replacement – GB-1234</span></span> | <span data-ttu-id="15095-130">Gratificação</span><span class="sxs-lookup"><span data-stu-id="15095-130">Premium</span></span> |

### <a name="service-agreement-lines"></a><span data-ttu-id="15095-131">Linhas do contrato de serviço</span><span class="sxs-lookup"><span data-stu-id="15095-131">Service agreement lines</span></span>

| <span data-ttu-id="15095-132">Descrição</span><span class="sxs-lookup"><span data-stu-id="15095-132">Description</span></span>             | <span data-ttu-id="15095-133">Tipo de transação</span><span class="sxs-lookup"><span data-stu-id="15095-133">Transaction type</span></span> | <span data-ttu-id="15095-134">Objeto de serviço</span><span class="sxs-lookup"><span data-stu-id="15095-134">Service object</span></span> | <span data-ttu-id="15095-135">Tarefa de serviço</span><span class="sxs-lookup"><span data-stu-id="15095-135">Service task</span></span> |
|-------------------------|------------------|----------------|--------------|
| <span data-ttu-id="15095-136">inspeção e limpeza</span><span class="sxs-lookup"><span data-stu-id="15095-136">Inspection and cleaning</span></span> | <span data-ttu-id="15095-137">Hora</span><span class="sxs-lookup"><span data-stu-id="15095-137">Hour</span></span>             | <span data-ttu-id="15095-138">GB-1234</span><span class="sxs-lookup"><span data-stu-id="15095-138">GB-1234</span></span>        | <span data-ttu-id="15095-139">I/C - GB1234</span><span class="sxs-lookup"><span data-stu-id="15095-139">I/C - GB1234</span></span> |
| <span data-ttu-id="15095-140">Viagem</span><span class="sxs-lookup"><span data-stu-id="15095-140">Travel</span></span>                  | <span data-ttu-id="15095-141">Expense</span><span class="sxs-lookup"><span data-stu-id="15095-141">Expense</span></span>          | <span data-ttu-id="15095-142">GB-1234</span><span class="sxs-lookup"><span data-stu-id="15095-142">GB-1234</span></span>        | <span data-ttu-id="15095-143">I/C - GB1234</span><span class="sxs-lookup"><span data-stu-id="15095-143">I/C - GB1234</span></span> |
| <span data-ttu-id="15095-144">Materiais</span><span class="sxs-lookup"><span data-stu-id="15095-144">Materials</span></span>               | <span data-ttu-id="15095-145">Item</span><span class="sxs-lookup"><span data-stu-id="15095-145">Item</span></span>             | <span data-ttu-id="15095-146">GB-1234</span><span class="sxs-lookup"><span data-stu-id="15095-146">GB-1234</span></span>        | <span data-ttu-id="15095-147">I/C - GB1234</span><span class="sxs-lookup"><span data-stu-id="15095-147">I/C - GB1234</span></span> |
| <span data-ttu-id="15095-148">Substituição de rotina</span><span class="sxs-lookup"><span data-stu-id="15095-148">Routine replacement</span></span>     | <span data-ttu-id="15095-149">Hora</span><span class="sxs-lookup"><span data-stu-id="15095-149">Hour</span></span>             | <span data-ttu-id="15095-150">GB-1234</span><span class="sxs-lookup"><span data-stu-id="15095-150">GB-1234</span></span>        | <span data-ttu-id="15095-151">RR - GB1234</span><span class="sxs-lookup"><span data-stu-id="15095-151">RR - GB1234</span></span>  |
| <span data-ttu-id="15095-152">GR-1</span><span class="sxs-lookup"><span data-stu-id="15095-152">GR-1</span></span>                    | <span data-ttu-id="15095-153">Item</span><span class="sxs-lookup"><span data-stu-id="15095-153">Item</span></span>             | <span data-ttu-id="15095-154">GB-1234</span><span class="sxs-lookup"><span data-stu-id="15095-154">GB-1234</span></span>        | <span data-ttu-id="15095-155">RR - GB1234</span><span class="sxs-lookup"><span data-stu-id="15095-155">RR - GB1234</span></span>  |
| <span data-ttu-id="15095-156">GR-5</span><span class="sxs-lookup"><span data-stu-id="15095-156">GR-5</span></span>                    | <span data-ttu-id="15095-157">Item</span><span class="sxs-lookup"><span data-stu-id="15095-157">Item</span></span>             | <span data-ttu-id="15095-158">GB-1234</span><span class="sxs-lookup"><span data-stu-id="15095-158">GB-1234</span></span>        | <span data-ttu-id="15095-159">RR - GB1234</span><span class="sxs-lookup"><span data-stu-id="15095-159">RR - GB1234</span></span>  |

<span data-ttu-id="15095-160">As linhas de contrato de serviço dos dois trabalhos têm duas tarefas de serviço anexadas a elas.</span><span class="sxs-lookup"><span data-stu-id="15095-160">The service agreement lines for the two jobs have two service tasks attached to them.</span></span> <span data-ttu-id="15095-161">As tarefas de serviço determinam as transações que pertencem a cada trabalho.</span><span class="sxs-lookup"><span data-stu-id="15095-161">The service tasks determine the transactions that belong to each job.</span></span> <span data-ttu-id="15095-162">No primeiro caso, tarefa de serviço I/C - GB1234 identifica todas as linhas de contrato de serviço envolvidas na inspeção e limpeza do objeto GB-1234.</span><span class="sxs-lookup"><span data-stu-id="15095-162">In the first case, service task I/C - GB1234 identifies all the service agreement lines that are involved in the inspection and cleaning of object GB-1234.</span></span> <span data-ttu-id="15095-163">No segundo caso, a tarefa de serviço RR - GB1234 identifica todas as linhas de contrato de serviço envolvidas na realização de um trabalho de substituição de rotina.</span><span class="sxs-lookup"><span data-stu-id="15095-163">In the second case, service task RR - GB1234 identifies all the service agreement lines that are involved in completing a routine replacement job.</span></span>

<span data-ttu-id="15095-164">As relações de tarefas de serviço que conectam as tarefas de serviço ao contrato específico são as seguintes:</span><span class="sxs-lookup"><span data-stu-id="15095-164">The service task relations that connect the service tasks to the specific agreement are as follows:</span></span>

### <a name="service-tasks"></a><span data-ttu-id="15095-165">Tarefas de serviço</span><span class="sxs-lookup"><span data-stu-id="15095-165">Service tasks</span></span>

| <span data-ttu-id="15095-166">Tarefa de serviço</span><span class="sxs-lookup"><span data-stu-id="15095-166">Service task</span></span> | <span data-ttu-id="15095-167">Descrição</span><span class="sxs-lookup"><span data-stu-id="15095-167">Description</span></span>                             | <span data-ttu-id="15095-168">Nota interna</span><span class="sxs-lookup"><span data-stu-id="15095-168">Internal note</span></span>                                                                                                                 | <span data-ttu-id="15095-169">Nota externa</span><span class="sxs-lookup"><span data-stu-id="15095-169">External note</span></span>                 |
|--------------|-----------------------------------------|-------------------------------------------------------------------------------------------------------------------------------|-------------------------------|
| <span data-ttu-id="15095-170">I/C - GB1234</span><span class="sxs-lookup"><span data-stu-id="15095-170">I/C - GB1234</span></span> | <span data-ttu-id="15095-171">Inspeção da caixa de embreagens GB-1234</span><span class="sxs-lookup"><span data-stu-id="15095-171">Inspection of gearbox GB-1234</span></span>           | <span data-ttu-id="15095-172">Inspeção visual e mecânica da caixa de embreagens GB-1234</span><span class="sxs-lookup"><span data-stu-id="15095-172">Visual and mechanical inspection and cleaning of gearbox GB-1234</span></span>                                                              | <span data-ttu-id="15095-173">Inspeção de rotina da caixa de embreagens</span><span class="sxs-lookup"><span data-stu-id="15095-173">Routine inspection of gearbox</span></span> |
| <span data-ttu-id="15095-174">RR - GB1234</span><span class="sxs-lookup"><span data-stu-id="15095-174">RR - GB1234</span></span>  | <span data-ttu-id="15095-175">Substituição de peças de rotina do GB-1234</span><span class="sxs-lookup"><span data-stu-id="15095-175">Routine replacement of parts in GB-1234</span></span> | <span data-ttu-id="15095-176">Substituição de serviço de rotina dos componentes GR-1 e GR-5 (para caixas de embreagens fabricadas antes de 2002, substituir também o componente GR-2)</span><span class="sxs-lookup"><span data-stu-id="15095-176">Routine service replacement of GR-1 and GR-5 components (for gearboxes manufactured before 2002, also replace GR-2 component)</span></span> | <span data-ttu-id="15095-177">Substituição de peças de rotina</span><span class="sxs-lookup"><span data-stu-id="15095-177">Routine replacement of parts</span></span>  |

## <a name="group-service-orders"></a><span data-ttu-id="15095-178">Agrupar ordens de serviço</span><span class="sxs-lookup"><span data-stu-id="15095-178">Group service orders</span></span>

<span data-ttu-id="15095-179">Quando você cria ordens de serviço automaticamente, pode usar tarefas de serviço como critérios de agrupamento.</span><span class="sxs-lookup"><span data-stu-id="15095-179">When you create service orders automatically, you can use service tasks as grouping criteria.</span></span> <span data-ttu-id="15095-180">Para agrupar ordens de serviço por tarefas de serviço, defina no contrato de serviço que as ordens de serviço com base no contrato de serviço devem ser agrupadas por ID da tarefa de serviço como os critérios de agrupamento inicial.</span><span class="sxs-lookup"><span data-stu-id="15095-180">To group service orders by service tasks, define on the service agreement that service orders that are based on the service agreement should be grouped by service task ID as their initial grouping criteria.</span></span>

<span data-ttu-id="15095-181">**Agrupar por tarefa de serviço**</span><span class="sxs-lookup"><span data-stu-id="15095-181">**Group by service task**</span></span>

1. <span data-ttu-id="15095-182">Clique em **Gerenciamento de serviços** \> **Comum** \> **Contratos de serviço** \> **Contratos de serviço**.</span><span class="sxs-lookup"><span data-stu-id="15095-182">Click **Service management** \> **Common** \> **Service agreements** \> **Service agreements**.</span></span>
2. <span data-ttu-id="15095-183">Na guia **Configuração**, selecione **Por tarefa de serviço** no campo **Combinar ordens de serviço**.</span><span class="sxs-lookup"><span data-stu-id="15095-183">On the **Setup** tab, select **By service task** in the **Combine service orders** field.</span></span>




[!INCLUDE[footer-include](../../includes/footer-banner.md)]