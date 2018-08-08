---
title: "Tarefas de serviço"
description: "Use tarefas de serviço para descrever a tarefa a ser concluída durante uma ordem de serviço. Os técnicos e clientes podem consultar essas informações."
author: ShylaThompson
manager: AnnBe
ms.date: 02/21/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SMAServiceTask
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: ShylaThompson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 1d98cbff30620256c9d13e7b4a90314db150e33e
ms.openlocfilehash: f2538a7b4a4c13a299afb37dd336f2f5d6f36a23
ms.contentlocale: pt-br
ms.lasthandoff: 08/07/2018

---

# <a name="service-tasks"></a><span data-ttu-id="96ffd-104">Tarefas de serviço</span><span class="sxs-lookup"><span data-stu-id="96ffd-104">Service tasks</span></span>  

[!include [banner](../includes/banner.md)]

<span data-ttu-id="96ffd-105">Use tarefas de serviço para descrever a tarefa a ser concluída durante uma ordem de serviço.</span><span class="sxs-lookup"><span data-stu-id="96ffd-105">Use service tasks to describe the task to be completed during a service order.</span></span>
<span data-ttu-id="96ffd-106">Os técnicos e clientes podem consultar essas informações.</span><span class="sxs-lookup"><span data-stu-id="96ffd-106">Both technicians and customers can see this information.</span></span>

<span data-ttu-id="96ffd-107">Crie tarefas de serviço na página **Tarefas de serviço** e associe tarefas de serviço a uma ordem de serviço ou a um contrato de serviço específico por meio da criação de relações de tarefa de serviço.</span><span class="sxs-lookup"><span data-stu-id="96ffd-107">You create service tasks in the **Service tasks** page, and you associate service tasks with a specific service agreement or service order by creating service task relations.</span></span> <span data-ttu-id="96ffd-108">Sempre que criar uma relação de tarefas de serviço, você poderá criar o seguinte:</span><span class="sxs-lookup"><span data-stu-id="96ffd-108">Every time that you create a service task relation, you can create the following:</span></span>

-  <span data-ttu-id="96ffd-109">Notas internas da tarefa, como solicitações técnicas detalhadas da tarefa que devem ser de conhecimento do técnico.</span><span class="sxs-lookup"><span data-stu-id="96ffd-109">Internal notes for the task, such as detailed technical requests for the task that are important for the technician to know.</span></span>

-  <span data-ttu-id="96ffd-110">Notas externas que o cliente pode ver.</span><span class="sxs-lookup"><span data-stu-id="96ffd-110">External notes that the customer can see.</span></span> <span data-ttu-id="96ffd-111">Essas podem oferecer uma explicação menos técnica da tarefa que está sendo executada, de acordo com o contrato entre o cliente e a empresa de serviço.</span><span class="sxs-lookup"><span data-stu-id="96ffd-111">These might provide a less technical explanation of the task that is being completed, according to the agreement between the customer and the service company.</span></span>

<span data-ttu-id="96ffd-112">Quando tiver configurado uma relação de tarefas de serviço entre uma tarefa de serviço e uma ordem de serviço ou um contrato de serviço, você poderá especificar essa tarefa de serviço quando criar linhas de ordem de serviço ou linhas de contrato de serviço para a ordem de serviço ou o contrato de serviço atual.</span><span class="sxs-lookup"><span data-stu-id="96ffd-112">When you have set up a service task relation between a service task and a service order or service agreement, you can specify this service task when you create service order lines or service agreement lines for the current service order or service agreement.</span></span>

<span data-ttu-id="96ffd-113">Ao gerar ordens de serviço de um contrato de serviço, você poderá usar as tarefas de serviço atribuídas a cada linha do contrato de serviço nas linhas da ordem de serviço em ordens de serviço.</span><span class="sxs-lookup"><span data-stu-id="96ffd-113">When you generate service orders from a service agreement, you can use the service tasks that are assigned to each service agreement line to group service order lines into service orders.</span></span>

## <a name="create-a-service-task"></a><span data-ttu-id="96ffd-114">Criar uma tarefa de serviço</span><span class="sxs-lookup"><span data-stu-id="96ffd-114">Create a service task</span></span>

1. <span data-ttu-id="96ffd-115">Clique em **Gerenciamento de serviços** \> **Configuração** \> **Tarefas de serviços**.</span><span class="sxs-lookup"><span data-stu-id="96ffd-115">Click **Service management** \> **Setup** \> **Service tasks**.</span></span>
2. <span data-ttu-id="96ffd-116">Crie uma nova linha.</span><span class="sxs-lookup"><span data-stu-id="96ffd-116">Create a new line.</span></span>
3. <span data-ttu-id="96ffd-117">Insira a ID e a descrição do serviço.</span><span class="sxs-lookup"><span data-stu-id="96ffd-117">Enter the service ID and description.</span></span>

## <a name="example"></a><span data-ttu-id="96ffd-118">Exemplo</span><span class="sxs-lookup"><span data-stu-id="96ffd-118">Example</span></span>

<span data-ttu-id="96ffd-119">Um técnico deve executar dois trabalhos em uma caixa de embreagens (objeto de serviço GB-1234) no site de um cliente.</span><span class="sxs-lookup"><span data-stu-id="96ffd-119">A technician must complete two jobs on a gearbox (service object GB-1234) at a customer site.</span></span> <span data-ttu-id="96ffd-120">Um contrato de serviço é criado para o cliente, e várias transações são associadas aos trabalhos.</span><span class="sxs-lookup"><span data-stu-id="96ffd-120">A service agreement is created for the customer, and several transactions are associated with the jobs.</span></span> <span data-ttu-id="96ffd-121">O contrato de serviço e as linhas de contrato de serviço para os dois trabalhos são as seguintes:</span><span class="sxs-lookup"><span data-stu-id="96ffd-121">The service agreement and service agreement lines for the two jobs are as follows:</span></span>

### <a name="service-agreement"></a><span data-ttu-id="96ffd-122">Contrato de serviço</span><span class="sxs-lookup"><span data-stu-id="96ffd-122">Service agreement</span></span>

| <span data-ttu-id="96ffd-123">Project</span><span class="sxs-lookup"><span data-stu-id="96ffd-123">Project</span></span> | <span data-ttu-id="96ffd-124">Contrato de serviço</span><span class="sxs-lookup"><span data-stu-id="96ffd-124">Service agreement</span></span> | <span data-ttu-id="96ffd-125">descrição</span><span class="sxs-lookup"><span data-stu-id="96ffd-125">Description</span></span>                                  | <span data-ttu-id="96ffd-126">Agrupar</span><span class="sxs-lookup"><span data-stu-id="96ffd-126">Group</span></span>   |
|---------|-------------------|----------------------------------------------|---------|
| <span data-ttu-id="96ffd-127">9012</span><span class="sxs-lookup"><span data-stu-id="96ffd-127">9012</span></span>    | <span data-ttu-id="96ffd-128">000008\_001</span><span class="sxs-lookup"><span data-stu-id="96ffd-128">000008\_001</span></span>       | <span data-ttu-id="96ffd-129">Inspeção e substituição de rotina - GB-1234</span><span class="sxs-lookup"><span data-stu-id="96ffd-129">Inspection and routine replacement – GB-1234</span></span> | <span data-ttu-id="96ffd-130">Gratificação</span><span class="sxs-lookup"><span data-stu-id="96ffd-130">Premium</span></span> |

### <a name="service-agreement-lines"></a><span data-ttu-id="96ffd-131">Linhas do contrato de serviço</span><span class="sxs-lookup"><span data-stu-id="96ffd-131">Service agreement lines</span></span>

| <span data-ttu-id="96ffd-132">Descrição</span><span class="sxs-lookup"><span data-stu-id="96ffd-132">Description</span></span>             | <span data-ttu-id="96ffd-133">Tipo de transação</span><span class="sxs-lookup"><span data-stu-id="96ffd-133">Transaction type</span></span> | <span data-ttu-id="96ffd-134">Objeto de serviço</span><span class="sxs-lookup"><span data-stu-id="96ffd-134">Service object</span></span> | <span data-ttu-id="96ffd-135">Tarefa de serviço</span><span class="sxs-lookup"><span data-stu-id="96ffd-135">Service task</span></span> |
|-------------------------|------------------|----------------|--------------|
| <span data-ttu-id="96ffd-136">inspeção e limpeza</span><span class="sxs-lookup"><span data-stu-id="96ffd-136">Inspection and cleaning</span></span> | <span data-ttu-id="96ffd-137">Hora</span><span class="sxs-lookup"><span data-stu-id="96ffd-137">Hour</span></span>             | <span data-ttu-id="96ffd-138">GB-1234</span><span class="sxs-lookup"><span data-stu-id="96ffd-138">GB-1234</span></span>        | <span data-ttu-id="96ffd-139">I/C - GB1234</span><span class="sxs-lookup"><span data-stu-id="96ffd-139">I/C - GB1234</span></span> |
| <span data-ttu-id="96ffd-140">Viagem</span><span class="sxs-lookup"><span data-stu-id="96ffd-140">Travel</span></span>                  | <span data-ttu-id="96ffd-141">Expense</span><span class="sxs-lookup"><span data-stu-id="96ffd-141">Expense</span></span>          | <span data-ttu-id="96ffd-142">GB-1234</span><span class="sxs-lookup"><span data-stu-id="96ffd-142">GB-1234</span></span>        | <span data-ttu-id="96ffd-143">I/C - GB1234</span><span class="sxs-lookup"><span data-stu-id="96ffd-143">I/C - GB1234</span></span> |
| <span data-ttu-id="96ffd-144">Materiais</span><span class="sxs-lookup"><span data-stu-id="96ffd-144">Materials</span></span>               | <span data-ttu-id="96ffd-145">Item</span><span class="sxs-lookup"><span data-stu-id="96ffd-145">Item</span></span>             | <span data-ttu-id="96ffd-146">GB-1234</span><span class="sxs-lookup"><span data-stu-id="96ffd-146">GB-1234</span></span>        | <span data-ttu-id="96ffd-147">I/C - GB1234</span><span class="sxs-lookup"><span data-stu-id="96ffd-147">I/C - GB1234</span></span> |
| <span data-ttu-id="96ffd-148">Substituição de rotina</span><span class="sxs-lookup"><span data-stu-id="96ffd-148">Routine replacement</span></span>     | <span data-ttu-id="96ffd-149">Hora</span><span class="sxs-lookup"><span data-stu-id="96ffd-149">Hour</span></span>             | <span data-ttu-id="96ffd-150">GB-1234</span><span class="sxs-lookup"><span data-stu-id="96ffd-150">GB-1234</span></span>        | <span data-ttu-id="96ffd-151">RR - GB1234</span><span class="sxs-lookup"><span data-stu-id="96ffd-151">RR - GB1234</span></span>  |
| <span data-ttu-id="96ffd-152">GR-1</span><span class="sxs-lookup"><span data-stu-id="96ffd-152">GR-1</span></span>                    | <span data-ttu-id="96ffd-153">Item</span><span class="sxs-lookup"><span data-stu-id="96ffd-153">Item</span></span>             | <span data-ttu-id="96ffd-154">GB-1234</span><span class="sxs-lookup"><span data-stu-id="96ffd-154">GB-1234</span></span>        | <span data-ttu-id="96ffd-155">RR - GB1234</span><span class="sxs-lookup"><span data-stu-id="96ffd-155">RR - GB1234</span></span>  |
| <span data-ttu-id="96ffd-156">GR-5</span><span class="sxs-lookup"><span data-stu-id="96ffd-156">GR-5</span></span>                    | <span data-ttu-id="96ffd-157">Item</span><span class="sxs-lookup"><span data-stu-id="96ffd-157">Item</span></span>             | <span data-ttu-id="96ffd-158">GB-1234</span><span class="sxs-lookup"><span data-stu-id="96ffd-158">GB-1234</span></span>        | <span data-ttu-id="96ffd-159">RR - GB1234</span><span class="sxs-lookup"><span data-stu-id="96ffd-159">RR - GB1234</span></span>  |

<span data-ttu-id="96ffd-160">As linhas de contrato de serviço dos dois trabalhos têm duas tarefas de serviço anexadas a elas.</span><span class="sxs-lookup"><span data-stu-id="96ffd-160">The service agreement lines for the two jobs have two service tasks attached to them.</span></span> <span data-ttu-id="96ffd-161">As tarefas de serviço determinam as transações que pertencem a cada trabalho.</span><span class="sxs-lookup"><span data-stu-id="96ffd-161">The service tasks determine the transactions that belong to each job.</span></span> <span data-ttu-id="96ffd-162">No primeiro caso, tarefa de serviço I/C - GB1234 identifica todas as linhas de contrato de serviço envolvidas na inspeção e limpeza do objeto GB-1234.</span><span class="sxs-lookup"><span data-stu-id="96ffd-162">In the first case, service task I/C - GB1234 identifies all the service agreement lines that are involved in the inspection and cleaning of object GB-1234.</span></span> <span data-ttu-id="96ffd-163">No segundo caso, a tarefa de serviço RR - GB1234 identifica todas as linhas de contrato de serviço envolvidas na realização de um trabalho de substituição de rotina.</span><span class="sxs-lookup"><span data-stu-id="96ffd-163">In the second case, service task RR - GB1234 identifies all the service agreement lines that are involved in completing a routine replacement job.</span></span>

<span data-ttu-id="96ffd-164">As relações de tarefas de serviço que conectam as tarefas de serviço ao contrato específico são as seguintes:</span><span class="sxs-lookup"><span data-stu-id="96ffd-164">The service task relations that connect the service tasks to the specific agreement are as follows:</span></span>

### <a name="service-tasks"></a><span data-ttu-id="96ffd-165">Tarefas de serviço</span><span class="sxs-lookup"><span data-stu-id="96ffd-165">Service tasks</span></span>

| <span data-ttu-id="96ffd-166">Tarefa de serviço</span><span class="sxs-lookup"><span data-stu-id="96ffd-166">Service task</span></span> | <span data-ttu-id="96ffd-167">Descrição</span><span class="sxs-lookup"><span data-stu-id="96ffd-167">Description</span></span>                             | <span data-ttu-id="96ffd-168">Nota interna</span><span class="sxs-lookup"><span data-stu-id="96ffd-168">Internal note</span></span>                                                                                                                 | <span data-ttu-id="96ffd-169">Nota externa</span><span class="sxs-lookup"><span data-stu-id="96ffd-169">External note</span></span>                 |
|--------------|-----------------------------------------|-------------------------------------------------------------------------------------------------------------------------------|-------------------------------|
| <span data-ttu-id="96ffd-170">I/C - GB1234</span><span class="sxs-lookup"><span data-stu-id="96ffd-170">I/C - GB1234</span></span> | <span data-ttu-id="96ffd-171">Inspeção da caixa de embreagens GB-1234</span><span class="sxs-lookup"><span data-stu-id="96ffd-171">Inspection of gearbox GB-1234</span></span>           | <span data-ttu-id="96ffd-172">Inspeção visual e mecânica da caixa de embreagens GB-1234</span><span class="sxs-lookup"><span data-stu-id="96ffd-172">Visual and mechanical inspection and cleaning of gearbox GB-1234</span></span>                                                              | <span data-ttu-id="96ffd-173">Inspeção de rotina da caixa de embreagens</span><span class="sxs-lookup"><span data-stu-id="96ffd-173">Routine inspection of gearbox</span></span> |
| <span data-ttu-id="96ffd-174">RR - GB1234</span><span class="sxs-lookup"><span data-stu-id="96ffd-174">RR - GB1234</span></span>  | <span data-ttu-id="96ffd-175">Substituição de peças de rotina do GB-1234</span><span class="sxs-lookup"><span data-stu-id="96ffd-175">Routine replacement of parts in GB-1234</span></span> | <span data-ttu-id="96ffd-176">Substituição de serviço de rotina dos componentes GR-1 e GR-5 (para caixas de embreagens fabricadas antes de 2002, substituir também o componente GR-2)</span><span class="sxs-lookup"><span data-stu-id="96ffd-176">Routine service replacement of GR-1 and GR-5 components (for gearboxes manufactured before 2002, also replace GR-2 component)</span></span> | <span data-ttu-id="96ffd-177">Substituição de peças de rotina</span><span class="sxs-lookup"><span data-stu-id="96ffd-177">Routine replacement of parts</span></span>  |

## <a name="group-service-orders"></a><span data-ttu-id="96ffd-178">Agrupar ordens de serviço</span><span class="sxs-lookup"><span data-stu-id="96ffd-178">Group service orders</span></span>

<span data-ttu-id="96ffd-179">Quando você cria ordens de serviço automaticamente, pode usar tarefas de serviço como critérios de agrupamento.</span><span class="sxs-lookup"><span data-stu-id="96ffd-179">When you create service orders automatically, you can use service tasks as grouping criteria.</span></span> <span data-ttu-id="96ffd-180">Para agrupar ordens de serviço por tarefas de serviço, defina no contrato de serviço que as ordens de serviço com base no contrato de serviço devem ser agrupadas por ID da tarefa de serviço como os critérios de agrupamento inicial.</span><span class="sxs-lookup"><span data-stu-id="96ffd-180">To group service orders by service tasks, define on the service agreement that service orders that are based on the service agreement should be grouped by service task ID as their initial grouping criteria.</span></span>

<span data-ttu-id="96ffd-181">**Agrupar por tarefa de serviço**</span><span class="sxs-lookup"><span data-stu-id="96ffd-181">**Group by service task**</span></span>

1. <span data-ttu-id="96ffd-182">Clique em **Gerenciamento de serviços** \> **Comum** \> **Contratos de serviço** \> **Contratos de serviço**.</span><span class="sxs-lookup"><span data-stu-id="96ffd-182">Click **Service management** \> **Common** \> **Service agreements** \> **Service agreements**.</span></span>
2. <span data-ttu-id="96ffd-183">Na guia **Configuração**, selecione **Por tarefa de serviço** no campo **Combinar ordens de serviço**.</span><span class="sxs-lookup"><span data-stu-id="96ffd-183">On the **Setup** tab, select **By service task** in the **Combine service orders** field.</span></span>



