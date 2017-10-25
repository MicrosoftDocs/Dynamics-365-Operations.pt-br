---
title: Agendamento visual para lean manufacturing
description: "Este tópico fornece informações sobre o quadro de programação kanban, que o planejador de produção pode usar para controlar e otimizar o plano da produção de trabalhos kanban."
author: johanhoffmann
manager: AnnBe
ms.date: 06/16/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: KanbanBoard, KanbanJobSchedulingListPage, LeanProductionFlowVisualization
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: 6218f54364e096bdd718ea35edb0b3666e65f2c1
ms.contentlocale: pt-br
ms.lasthandoff: 09/29/2017

---

# <a name="visual-scheduling-for-lean-manufacturing"></a><span data-ttu-id="cfe3e-103">Agendamento visual para lean manufacturing</span><span class="sxs-lookup"><span data-stu-id="cfe3e-103">Visual scheduling for lean manufacturing</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="cfe3e-104">Este tópico fornece informações sobre o quadro de programação kanban, que o planejador de produção pode usar para controlar e otimizar o plano da produção de trabalhos kanban.</span><span class="sxs-lookup"><span data-stu-id="cfe3e-104">This topic provides information about the Kanban schedule board, which the production planner can use to control and optimize the production plan for kanban jobs.</span></span>

<span data-ttu-id="cfe3e-105">Este tópico fornece informações sobre o quadro de programação kanban, que o planejador de produção pode usar para controlar e otimizar o plano da produção de trabalhos kanban.</span><span class="sxs-lookup"><span data-stu-id="cfe3e-105">This topic provides information about the Kanban schedule board, which the production planner can use to control and optimize the production plan for kanban jobs.</span></span>

<span data-ttu-id="cfe3e-106">O quadro de programação kanban permite que o planejador de produção controle e otimize o plano da produção de trabalhos kanban.</span><span class="sxs-lookup"><span data-stu-id="cfe3e-106">The Kanban schedule board lets the production planner control and optimize the production plan for kanban jobs.</span></span> <span data-ttu-id="cfe3e-107">Ele torna o fluxo de trabalhos kanban transparente e fornece ao planejador de produção uma ferramenta que otimiza e ajusta o plano da produção da célula de trabalho de lean manufacturing.</span><span class="sxs-lookup"><span data-stu-id="cfe3e-107">It makes the flow of kanban jobs transparent, and gives the production planner a tool that optimizes and adjusts the production plan for the lean manufacturing work cell.</span></span>

## <a name="visual-scheduling-of-kanban-jobs"></a><span data-ttu-id="cfe3e-108">Agendamento visual de trabalhos kanban</span><span class="sxs-lookup"><span data-stu-id="cfe3e-108">Visual scheduling of kanban jobs</span></span>
<span data-ttu-id="cfe3e-109">Um trabalho kanban pode consistir em um ou mais trabalhos kanban.</span><span class="sxs-lookup"><span data-stu-id="cfe3e-109">A kanban job can consist of one or many kanban jobs.</span></span> <span data-ttu-id="cfe3e-110">Há dois tipos de trabalhos kanban:</span><span class="sxs-lookup"><span data-stu-id="cfe3e-110">There are two types of kanban jobs:</span></span>

-   <span data-ttu-id="cfe3e-111">Processar</span><span class="sxs-lookup"><span data-stu-id="cfe3e-111">Process</span></span>
-   <span data-ttu-id="cfe3e-112">Transferência</span><span class="sxs-lookup"><span data-stu-id="cfe3e-112">Transfer</span></span>

<span data-ttu-id="cfe3e-113">Só é possível agendar os trabalhos do tipo **Processo**.</span><span class="sxs-lookup"><span data-stu-id="cfe3e-113">You can schedule only jobs of the **Process** type.</span></span> <span data-ttu-id="cfe3e-114">O trabalho kanban e suas propriedades, como o tempo de atividade, são definidos no fluxo kanban de produção.</span><span class="sxs-lookup"><span data-stu-id="cfe3e-114">The kanban job and its properties, such as the activity time, are defined in the production kanban flow.</span></span> <span data-ttu-id="cfe3e-115">No fluxo kanban de produção, o trabalho kanban também é atribuído a uma célula de trabalho.</span><span class="sxs-lookup"><span data-stu-id="cfe3e-115">In the production kanban flow, the kanban job is also assigned to a work cell.</span></span> <span data-ttu-id="cfe3e-116">A capacidade diária da célula de trabalho é calculada com base na capacidade da célula de trabalho definida no grupo de recursos.</span><span class="sxs-lookup"><span data-stu-id="cfe3e-116">The work cell's daily capacity is calculated based on the work cell capacity that is set on the resource group.</span></span> <span data-ttu-id="cfe3e-117">É ajustado pelo tempo de trabalho diário no calendário relacionado.</span><span class="sxs-lookup"><span data-stu-id="cfe3e-117">It's adjusted by the daily working time in the related calendar.</span></span> <span data-ttu-id="cfe3e-118">Quando um trabalho kanban é agendado, o trabalho carrega a capacidade da célula de trabalho.</span><span class="sxs-lookup"><span data-stu-id="cfe3e-118">When a kanban job is scheduled, the job loads the capacity of the work cell.</span></span> <span data-ttu-id="cfe3e-119">O quadro de programação kanban fornece os seguintes principais recursos:</span><span class="sxs-lookup"><span data-stu-id="cfe3e-119">The Kanban schedule board provides the following main features:</span></span>

-   <span data-ttu-id="cfe3e-120">Uma visão geral gráfica do plano da produção em uma célula de trabalho de lean manufacturing.</span><span class="sxs-lookup"><span data-stu-id="cfe3e-120">A graphical overview of the production plan in a lean work cell.</span></span> <span data-ttu-id="cfe3e-121">Essa visão geral mostra os trabalhos do processo kanban nos períodos definidos.</span><span class="sxs-lookup"><span data-stu-id="cfe3e-121">This overview shows the planned kanban process jobs in the defined periods.</span></span>
-   <span data-ttu-id="cfe3e-122">Uma ferramenta que permite agendar trabalhos kanban não planejados e reagendar trabalhos programados anteriormente.</span><span class="sxs-lookup"><span data-stu-id="cfe3e-122">A tool that lets you schedule unplanned kanban jobs and reschedule previously scheduled jobs.</span></span>

## <a name="kanban-schedule-board"></a><span data-ttu-id="cfe3e-123">Quadro de programação kanban</span><span class="sxs-lookup"><span data-stu-id="cfe3e-123">Kanban schedule board</span></span>
<span data-ttu-id="cfe3e-124">A página **Quadro de programação kanban** contém sete elementos principais, conforme mostrado na seguinte ilustração.</span><span class="sxs-lookup"><span data-stu-id="cfe3e-124">The **Kanban schedule board** page contains seven main elements, as shown in the following illustration.</span></span> 

![Quadro de programação kanban](./media/kanban-schedule-board-1024x554.png)
1.  <span data-ttu-id="cfe3e-126">Painel de Ação</span><span class="sxs-lookup"><span data-stu-id="cfe3e-126">Action Pane</span></span>
2.  <span data-ttu-id="cfe3e-127">Filtrar campos</span><span class="sxs-lookup"><span data-stu-id="cfe3e-127">Filter fields</span></span>
3.  <span data-ttu-id="cfe3e-128">Botão de trabalho não planejados</span><span class="sxs-lookup"><span data-stu-id="cfe3e-128">Button for unplanned jobs</span></span>
4.  <span data-ttu-id="cfe3e-129">Nó de período</span><span class="sxs-lookup"><span data-stu-id="cfe3e-129">Period node</span></span>
5.  <span data-ttu-id="cfe3e-130">Trabalho kanban</span><span class="sxs-lookup"><span data-stu-id="cfe3e-130">Kanban job</span></span>
6.  <span data-ttu-id="cfe3e-131">Barra de capacidade</span><span class="sxs-lookup"><span data-stu-id="cfe3e-131">Capacity bar</span></span>
7.  <span data-ttu-id="cfe3e-132">Escala de tempo</span><span class="sxs-lookup"><span data-stu-id="cfe3e-132">Time scale</span></span>

### <a name="view-the-time-scale"></a><span data-ttu-id="cfe3e-133">Exibir a escala de tempo</span><span class="sxs-lookup"><span data-stu-id="cfe3e-133">View the time scale</span></span>

<span data-ttu-id="cfe3e-134">O quadro é dividido em períodos, cada um sendo representado como um nó (4).</span><span class="sxs-lookup"><span data-stu-id="cfe3e-134">The board is divided into periods, each of which is represented as a node (4).</span></span> <span data-ttu-id="cfe3e-135">Os nós de período são listados no eixo vertical, e o acesso horizontal representa uma escala de tempo (7) que mostra a duração do período.</span><span class="sxs-lookup"><span data-stu-id="cfe3e-135">The period nodes are listed on the vertical axis, and the horizontal access represents a time scale (7) that shows the length of the period.</span></span> <span data-ttu-id="cfe3e-136">Um período tem duração de um dia ou uma semana.</span><span class="sxs-lookup"><span data-stu-id="cfe3e-136">A period has a length of either one day or one week.</span></span> <span data-ttu-id="cfe3e-137">A duração do período é determinada pela configuração da célula de trabalho selecionada para o quadro de programação kanban (2).</span><span class="sxs-lookup"><span data-stu-id="cfe3e-137">The period length is determined by the configuration of the work cell that is selected for the Kanban schedule board (2).</span></span> <span data-ttu-id="cfe3e-138">Para cada nó de período, o quadro de programação kanban indica quanto os trabalhos kanban agendados estão carregando em relação ao período.</span><span class="sxs-lookup"><span data-stu-id="cfe3e-138">For each period node, the Kanban schedule board indicates how much the scheduled kanban jobs are loading the period.</span></span> <span data-ttu-id="cfe3e-139">Há também uma indicação da produtividade máxima referente ao período.</span><span class="sxs-lookup"><span data-stu-id="cfe3e-139">There is also an indication of the maximum throughput for the period.</span></span> <span data-ttu-id="cfe3e-140">Se a produtividade planejada exceder a produtividade máxima, o período será considerado como sobrecarregado, e aparecerá um símbolo de aviso vermelho.</span><span class="sxs-lookup"><span data-stu-id="cfe3e-140">If the scheduled throughput exceeds the maximum throughput, the period is considered as overloaded, and a red warning symbol appears.</span></span> <span data-ttu-id="cfe3e-141">Um trabalho Kanban agendado será mostrado em um período com hora inicial e hora final programadas (5).</span><span class="sxs-lookup"><span data-stu-id="cfe3e-141">A scheduled kanban job appears in a period that has scheduled start and end times (5).</span></span> <span data-ttu-id="cfe3e-142">A duração do trabalho é igual ao tempo de atividade.</span><span class="sxs-lookup"><span data-stu-id="cfe3e-142">The length of the job is equal to the activity time.</span></span> <span data-ttu-id="cfe3e-143">Os trabalhos kanban aparecerão como sobreposição em um período se seu tempo de atividade exceder o takt time da célula de trabalho.</span><span class="sxs-lookup"><span data-stu-id="cfe3e-143">Kanban jobs appear as overlapping in a period if their activity times exceed the takt time of the work cell.</span></span>

### <a name="view-job-status"></a><span data-ttu-id="cfe3e-144">Exibir status do trabalho</span><span class="sxs-lookup"><span data-stu-id="cfe3e-144">View job status</span></span>

<span data-ttu-id="cfe3e-145">Mais informações sobre um trabalho kanban estarão disponíveis na dica de ferramenta que aparece quando você coloca o ponteiro sobre o trabalho.</span><span class="sxs-lookup"><span data-stu-id="cfe3e-145">More information about a kanban job is available in the tooltip that appears when you hover the pointer over the job.</span></span> <span data-ttu-id="cfe3e-146">Um símbolo fornece informações sobre o status do trabalho.</span><span class="sxs-lookup"><span data-stu-id="cfe3e-146">A symbol provides information about the status of the job.</span></span> <span data-ttu-id="cfe3e-147">Por exemplo, um símbolo de relógio indica que o trabalho kanban está vencido.</span><span class="sxs-lookup"><span data-stu-id="cfe3e-147">For example, a clock symbol indicates that the kanban job is overdue.</span></span>

### <a name="use-colors-to-view-the-kanban-schedule-board"></a><span data-ttu-id="cfe3e-148">Usar cores para exibir o quadro de programação kanban</span><span class="sxs-lookup"><span data-stu-id="cfe3e-148">Use colors to view the Kanban schedule board</span></span>

<span data-ttu-id="cfe3e-149">Para melhorar a visão geral que o quadro de programação kanban fornece, é possível usar cores para distinguir trabalhos kanban.</span><span class="sxs-lookup"><span data-stu-id="cfe3e-149">To enhance the overview that the Kanban schedule board provides, you can use colors to distinguish kanban jobs.</span></span> <span data-ttu-id="cfe3e-150">A cor de um trabalho kanban é configurada no grupo de agendamento de lean manufacturing, no qual é possível agregar os produtos que devem ser produzidos na mesma sequência.</span><span class="sxs-lookup"><span data-stu-id="cfe3e-150">The color of a kanban job is configured in the lean schedule group, where you can aggregate the products that should be produced in the same sequence.</span></span> <span data-ttu-id="cfe3e-151">O botão **Usar cores do tema** na guia **Quadro** do Painel de Ação permite que você alterne entre as cores do tema do aplicativo e as cores que são configuradas no grupo de agendamento de lean manufacturing.</span><span class="sxs-lookup"><span data-stu-id="cfe3e-151">The **Use theme colors** button on the **Board** tab of the Action Pane lets you switch between the application theme colors and the colors that are configured in the lean schedule group.</span></span> <span data-ttu-id="cfe3e-152">Para cada período, uma barra de capacidade (6) indica quantas horas disponíveis referentes ao período foram carregadas com trabalhos kanban.</span><span class="sxs-lookup"><span data-stu-id="cfe3e-152">For each period, a capacity bar (6) indicates how many of the available hours for the period have been loaded with kanban jobs.</span></span> <span data-ttu-id="cfe3e-153">Se o período estiver sobrecarregado, a barra de capacidade aparecerá mais espessa e em vermelho.</span><span class="sxs-lookup"><span data-stu-id="cfe3e-153">If the period is overloaded, the capacity bar appears thicker and in red.</span></span> <span data-ttu-id="cfe3e-154">Todas essas funções estarão disponíveis na guia **Quadro** do Painel de Ação (1) na parte superior da página **Quadro de programação kanban**.</span><span class="sxs-lookup"><span data-stu-id="cfe3e-154">All these functions are available on the **Board** tab of the Action Pane (1) at the top of the **Kanban schedule board** page.</span></span>

## <a name="plan-unplanned-jobs"></a><span data-ttu-id="cfe3e-155">Planejar trabalhos não planejados</span><span class="sxs-lookup"><span data-stu-id="cfe3e-155">Plan unplanned jobs</span></span>
<span data-ttu-id="cfe3e-156">É possível agendar trabalhos kanban não planejados na caixa de diálogo **Planejar trabalhos não planejados**.</span><span class="sxs-lookup"><span data-stu-id="cfe3e-156">You can schedule unplanned kanban jobs from the **Plan unplanned jobs** dialog box.</span></span> <span data-ttu-id="cfe3e-157">Para abrir essa caixa de diálogo, clique no botão **Trabalhos não planejados** que mostra o número atual de trabalhos não planejados.</span><span class="sxs-lookup"><span data-stu-id="cfe3e-157">To open this dialog box, click the **Unplanned jobs** button that shows the current number of unplanned jobs.</span></span> <span data-ttu-id="cfe3e-158">Como alternativa, clique em **Planejar trabalhos não planejados** na guia **Quadro** do Painel de Ação.</span><span class="sxs-lookup"><span data-stu-id="cfe3e-158">Alternatively, click **Plan unplanned jobs** on the **Board** tab of the Action Pane.</span></span> <span data-ttu-id="cfe3e-159">A caixa de diálogo mostra uma lista dos trabalhos kanban não planejados da célula de trabalho.</span><span class="sxs-lookup"><span data-stu-id="cfe3e-159">The dialog box shows a list of the unplanned kanban jobs for the work cell.</span></span> <span data-ttu-id="cfe3e-160">É possível usar o campo **Filtrar** para filtrar todos os campos na grade.</span><span class="sxs-lookup"><span data-stu-id="cfe3e-160">You can use the **Filter** field to filter on all fields in the grid.</span></span> <span data-ttu-id="cfe3e-161">Por exemplo, você pode filtrar trabalhos kanban de um produto específico.</span><span class="sxs-lookup"><span data-stu-id="cfe3e-161">For example, you can filter on kanban jobs for a specific product.</span></span> <span data-ttu-id="cfe3e-162">Após ter uma lista filtrada dos trabalhos que deseja agendar, selecione-os na lista e depois clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="cfe3e-162">After you have a filtered list of the jobs that you want to schedule, select them in the list, and then click **OK**.</span></span> <span data-ttu-id="cfe3e-163">Para usar o planejamento automático para agendar os trabalhos, defina a opção **Planejamento automático** como **Sim**.</span><span class="sxs-lookup"><span data-stu-id="cfe3e-163">To use automatic planning to schedule the jobs, set the **Automatic planning** option to **Yes**.</span></span> <span data-ttu-id="cfe3e-164">Nesse caso, os trabalhos são agendados em um período de acordo com sua data de vencimento.</span><span class="sxs-lookup"><span data-stu-id="cfe3e-164">In this case, the jobs are scheduled into a period according to their due date.</span></span> <span data-ttu-id="cfe3e-165">Também é possível agendar os trabalhos por período.</span><span class="sxs-lookup"><span data-stu-id="cfe3e-165">You can also schedule the jobs by period.</span></span> <span data-ttu-id="cfe3e-166">Basta selecionar um período no campo **Período**.</span><span class="sxs-lookup"><span data-stu-id="cfe3e-166">Just select a period in the **Period** field.</span></span> <span data-ttu-id="cfe3e-167">A seguinte ilustração mostra um exemplo da caixa de diálogo **Planejar trabalhos não planejados**.</span><span class="sxs-lookup"><span data-stu-id="cfe3e-167">The following illustration shows an example of the **Plan unplanned jobs** dialog box.</span></span> 

![Caixa de diálogo Planejar trabalhos não planejados](./media/plan-unplanned-jobs-1024x564.png)

## <a name="sequence-kanban-jobs-within-the-same-period"></a><span data-ttu-id="cfe3e-169">Sequenciar trabalhos kanban no mesmo período</span><span class="sxs-lookup"><span data-stu-id="cfe3e-169">Sequence kanban jobs within the same period</span></span>
<span data-ttu-id="cfe3e-170">É possível alterar a sequência de um ou mais trabalhos selecionados em um período.</span><span class="sxs-lookup"><span data-stu-id="cfe3e-170">You can change the sequence of one or more selected jobs within a period.</span></span> <span data-ttu-id="cfe3e-171">Essa capacidade pode ser útil para priorizar alguns trabalhos no período.</span><span class="sxs-lookup"><span data-stu-id="cfe3e-171">This capability can be useful if you want to prioritize some jobs within the period.</span></span> <span data-ttu-id="cfe3e-172">Como alternativa, pode ser que você queira sequenciar trabalhos com os mesmos atributos de produto, para otimizar a execução do trabalho.</span><span class="sxs-lookup"><span data-stu-id="cfe3e-172">Alternatively, you might want to sequence jobs that have the same product attributes, to optimize job execution.</span></span> <span data-ttu-id="cfe3e-173">Você pode alterar a sequência usando uma operação arrastar e soltar ou usando os itens de menu **Recuar** e **Avançar** na guia **Quadro** do Painel de Ação.</span><span class="sxs-lookup"><span data-stu-id="cfe3e-173">You can change the sequence through a drag-and-drop operation, or by using the **Backward** and **Forward** menu items on the **Board** tab of the Action Pane.</span></span>

## <a name="reassign-kanban-jobs-across-periods"></a><span data-ttu-id="cfe3e-174">Reatribuir trabalhos kanban em períodos</span><span class="sxs-lookup"><span data-stu-id="cfe3e-174">Reassign kanban jobs across periods</span></span>
<span data-ttu-id="cfe3e-175">Trabalhos podem ser reatribuídos de um período a outro.</span><span class="sxs-lookup"><span data-stu-id="cfe3e-175">Jobs can be reassigned from one period to another.</span></span> <span data-ttu-id="cfe3e-176">Esse recurso pode ser útil se um período estiver sobrecarregado e você quiser nivelar a carga para períodos com capacidade sobressalente.</span><span class="sxs-lookup"><span data-stu-id="cfe3e-176">This capability can be useful if a period is overloaded and you want to level the load to periods that have spare capacity.</span></span> <span data-ttu-id="cfe3e-177">Você pode reatribuir trabalhos usando uma operação arrastar e soltar ou usando os itens de menu **Próximo período** e **Período anterior** na guia **Quadro** do Painel de Ação.</span><span class="sxs-lookup"><span data-stu-id="cfe3e-177">You can reassign jobs through a drag-and-drop operation, or by using the **Next period** and **Previous period** menu items on the **Board** tab of the Action Pane.</span></span>

## <a name="open-the-kanban-schedule-board"></a><span data-ttu-id="cfe3e-178">Abrir o quadro de agenda kanban</span><span class="sxs-lookup"><span data-stu-id="cfe3e-178">Open the Kanban schedule board</span></span>
<span data-ttu-id="cfe3e-179">É possível abrir o quadro de agenda kanban usando o item de menu nas seguintes páginas:</span><span class="sxs-lookup"><span data-stu-id="cfe3e-179">You can open the Kanban schedule board by using the menu item on the following pages:</span></span>

-   <span data-ttu-id="cfe3e-180">Página **Área de produção**</span><span class="sxs-lookup"><span data-stu-id="cfe3e-180">**Production area** page</span></span>
-   <span data-ttu-id="cfe3e-181">Página **Agendamento de trabalhos kanban**</span><span class="sxs-lookup"><span data-stu-id="cfe3e-181">**Kanban jobs scheduling** page</span></span>
-   <span data-ttu-id="cfe3e-182">Página **Visualização do fluxo de produção**</span><span class="sxs-lookup"><span data-stu-id="cfe3e-182">**Production flow visualization** page</span></span>


<a name="see-also"></a><span data-ttu-id="cfe3e-183">Consulte também</span><span class="sxs-lookup"><span data-stu-id="cfe3e-183">See also</span></span>
--------

[<span data-ttu-id="cfe3e-184">Lean manufacturing – agendamento de trabalhos kanban</span><span class="sxs-lookup"><span data-stu-id="cfe3e-184">Lean manufacturing – Kanban job scheduling</span></span>](lean-manufacturing-kanban-job-scheduling.md)

