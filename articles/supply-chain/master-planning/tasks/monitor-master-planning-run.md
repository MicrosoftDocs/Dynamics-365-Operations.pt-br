---
title: Monitorar a execução de um planejamento mestre
description: Este tópico explica como o planejador de produção pode ver se a execução de um planejamento mestre está em andamento.
author: josaw1
ms.date: 11/04/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, ReqCreatePlanWorkspace, ReqTransPlanCard, SysQueryForm, InventItemIdLookupSimple, ReqLog, ReqProcessTaskTrace
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: a1733562768b3fe869f326bbfb47b6135a91b5cb
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5829633"
---
# <a name="monitor-a-master-planning-run"></a><span data-ttu-id="6fc85-103">Monitorar a execução de um planejamento mestre</span><span class="sxs-lookup"><span data-stu-id="6fc85-103">Monitor a master planning run</span></span>

[!include [banner](../../includes/banner.md)]

## <a name="use-a-gantt-chart-to-visualize-master-planning-progress"></a><span data-ttu-id="6fc85-104">Use um gráfico de Gantt para visualizar o andamento do planejamento mestre</span><span class="sxs-lookup"><span data-stu-id="6fc85-104">Use a Gantt chart to visualize master planning progress</span></span>

<span data-ttu-id="6fc85-105">Na página **Exibir andamento de planejamento mestre**, você pode exibir detalhes de execuções históricas do planejamento mestre como um gráfico de Gantt.</span><span class="sxs-lookup"><span data-stu-id="6fc85-105">From the **View master planning progress** page, you can view details of historical master planning runs as a Gantt chart.</span></span> <span data-ttu-id="6fc85-106">Esta funcionalidade pode ajudar a entender o tempo decorrido nas várias fases de planejamento mestre.</span><span class="sxs-lookup"><span data-stu-id="6fc85-106">This functionality can help you understand the time that is spent on the various phases of master planning.</span></span> <span data-ttu-id="6fc85-107">Para um trabalho de planejamento ativo atual, a página **Exibir andamento de planejamento mestre** pode ser usada para controlar o andamento e exibir o tempo estimado restante.</span><span class="sxs-lookup"><span data-stu-id="6fc85-107">For a current active planning job, the **View master planning progress** page can be used to track progress and view the estimated remaining time.</span></span>

### <a name="turn-on-and-use-the-master-plan-progress-visualization-feature"></a><span data-ttu-id="6fc85-108">Ativar e usar o recurso de visualização do andamento de Planejamento mestre</span><span class="sxs-lookup"><span data-stu-id="6fc85-108">Turn on and use the Master plan progress visualization feature</span></span>

<span data-ttu-id="6fc85-109">Para usar essa funcionalidade, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="6fc85-109">To use this functionality, follow these steps.</span></span>

1. <span data-ttu-id="6fc85-110">No espaço de trabalho **Gerenciamento de recursos**, na guia **Novo**, selecione **Visualização do andamento de planejamento mestre** na lista.</span><span class="sxs-lookup"><span data-stu-id="6fc85-110">In the **Feature management** workspace, on the **New** tab, select **Master planning progress visualization** in the list.</span></span> <span data-ttu-id="6fc85-111">Se o recurso não aparecer na guia **Novo** , examine as guias **Não habilitado** e **Tudo**.</span><span class="sxs-lookup"><span data-stu-id="6fc85-111">If the feature doesn't appear on the **New** tab, look on the **Not enabled** and **All** tabs.</span></span>
1. <span data-ttu-id="6fc85-112">Selecione **Habilitar agora**.</span><span class="sxs-lookup"><span data-stu-id="6fc85-112">Select **Enable now**.</span></span> <span data-ttu-id="6fc85-113">Como alternativa, selecione **Agenda** e selecione a hora em que você deseja que o recurso seja ativado.</span><span class="sxs-lookup"><span data-stu-id="6fc85-113">Alternatively, select **Schedule**, and then select the time when you want the feature to be turned on.</span></span>

<span data-ttu-id="6fc85-114">A página **Exibir andamento de planejamento mestre** pode exibir trabalhos de planejamento históricos e trabalhos de planejamento ativos.</span><span class="sxs-lookup"><span data-stu-id="6fc85-114">The **View master planning progress** page can display both historical planning jobs and active planning jobs.</span></span> 

<span data-ttu-id="6fc85-115">Para exibir trabalhos históricos de planejamento, há duas opções.</span><span class="sxs-lookup"><span data-stu-id="6fc85-115">To view historical planning jobs, there are two options.</span></span> 

1. <span data-ttu-id="6fc85-116">Acesse **Planejamento mestre \> Configuração \> Planos \> Planos mestres** e, depois, no Painel de Ação, selecione **Histórico**.</span><span class="sxs-lookup"><span data-stu-id="6fc85-116">Go to **Master planning \> Setup \> Plans \> Master plans**, and then, on the Action Pane, select **History**.</span></span> <span data-ttu-id="6fc85-117">Com o trabalho desejado selecionado, selecione **Consultas** e depois selecione **Exibir andamento**</span><span class="sxs-lookup"><span data-stu-id="6fc85-117">With the desired job selected, select **Inquiries**,  and then select **View progress**</span></span>
1. <span data-ttu-id="6fc85-118">Vá para **Planejamento mestre \> Espaços de trabalho \> Planejamento mestre**, no bloco Planejamento mestre, clique em **Histórico**.</span><span class="sxs-lookup"><span data-stu-id="6fc85-118">Go to **Master planning \> Workspaces \> Master planning**, on the Master planning tile click **History**.</span></span> <span data-ttu-id="6fc85-119">Com o trabalho desejado selecionado, selecione **Consultas** e depois selecione **Exibir andamento**</span><span class="sxs-lookup"><span data-stu-id="6fc85-119">With the desired job selected, select **Inquiries**,  and then select **View progress**</span></span>

<span data-ttu-id="6fc85-120">Para exibir trabalhos de planejamento ativos, há duas opções.</span><span class="sxs-lookup"><span data-stu-id="6fc85-120">To view active planning jobs, there are two options.</span></span> 
1. <span data-ttu-id="6fc85-121">Vá para **Planejamento mestre \> Espaços de trabalho \> Planejamento mestre**, no Painel de Ação, selecione **Processo de planejamento inacabado**.</span><span class="sxs-lookup"><span data-stu-id="6fc85-121">Go to **Master planning \> Workspaces \> Master planning**, on the Action Pane, select **Unfinished planning process**.</span></span> <span data-ttu-id="6fc85-122">Com o trabalho desejado selecionado, selecione **Consultas** e depois selecione **Exibir andamento**.</span><span class="sxs-lookup"><span data-stu-id="6fc85-122">With the desired job selected, select **Inquiries**,  and then select **View progress**.</span></span>
1. <span data-ttu-id="6fc85-123">Vá para **Planejamento mestre \> Espaços de trabalho \> Planejamento mestre**, no bloco Planejamento mestre, clique em **Exibir andamento**.</span><span class="sxs-lookup"><span data-stu-id="6fc85-123">Go to **Master planning \> Workspaces \> Master planning**, on the Master planning tile click **View progress**.</span></span> <span data-ttu-id="6fc85-124">Com o trabalho desejado selecionado, selecione **Consultas** e depois selecione **Exibir andamento**</span><span class="sxs-lookup"><span data-stu-id="6fc85-124">With the desired job selected, select **Inquiries**,  and then select **View progress**</span></span>

<span data-ttu-id="6fc85-125">Observe que você só poderá exibir os trabalhos ativos quando um trabalho de planejamento estiver em processamento.</span><span class="sxs-lookup"><span data-stu-id="6fc85-125">Note you can view active jobs only when a planning job is processing.</span></span>

### <a name="analyze-a-master-planning-job"></a><span data-ttu-id="6fc85-126">Analisar um trabalho de planejamento mestre</span><span class="sxs-lookup"><span data-stu-id="6fc85-126">Analyze a master planning job</span></span>

<span data-ttu-id="6fc85-127">No gráfico de Gantt, é possível expandir cada um dos processos de planejamento para exibir detalhes adicionais sobre o tempo gasto:</span><span class="sxs-lookup"><span data-stu-id="6fc85-127">In the Gantt chart, you can expand each of the following planning processes to view additional details about the time that is spent:</span></span>

- <span data-ttu-id="6fc85-128">Inicializando</span><span class="sxs-lookup"><span data-stu-id="6fc85-128">Initializing</span></span>
- <span data-ttu-id="6fc85-129">Excluindo e inserindo dados</span><span class="sxs-lookup"><span data-stu-id="6fc85-129">Deleting and inserting data</span></span>
- <span data-ttu-id="6fc85-130">Planejamento de cobertura</span><span class="sxs-lookup"><span data-stu-id="6fc85-130">Coverage planning</span></span>
- <span data-ttu-id="6fc85-131">Atrasos</span><span class="sxs-lookup"><span data-stu-id="6fc85-131">Delays</span></span>
- <span data-ttu-id="6fc85-132">Mensagens de ação</span><span class="sxs-lookup"><span data-stu-id="6fc85-132">Action messages</span></span>
- <span data-ttu-id="6fc85-133">Finalização</span><span class="sxs-lookup"><span data-stu-id="6fc85-133">Finalization</span></span>
- <span data-ttu-id="6fc85-134">Confirmação automática</span><span class="sxs-lookup"><span data-stu-id="6fc85-134">Auto-firming</span></span>

<span data-ttu-id="6fc85-135">O gráfico de Gantt é uma ferramenta útil se desejar exibir o impacto do uso de mensagens de ação.</span><span class="sxs-lookup"><span data-stu-id="6fc85-135">The Gantt chart is a useful tool if you want to view the impact of using action messages.</span></span>

#### <a name="navigation-in-the-gantt-chart"></a><span data-ttu-id="6fc85-136">Navegação no gráfico de Gantt</span><span class="sxs-lookup"><span data-stu-id="6fc85-136">Navigation in the Gantt chart</span></span>

- <span data-ttu-id="6fc85-137">Para expandir o grupo selecionado e mostrar os detalhes, selecione o sinal de adição (**+**) no modo de exibição de árvore.</span><span class="sxs-lookup"><span data-stu-id="6fc85-137">To expand the selected group and show the details, select the plus sign (**+**) in the tree view.</span></span>
- <span data-ttu-id="6fc85-138">Para recolher o grupo selecionado, selecione o sinal de subtração (**–**) no modo de exibição de árvore.</span><span class="sxs-lookup"><span data-stu-id="6fc85-138">To collapse the selected group, select the minus sign (**–**) in the tree view.</span></span>
- <span data-ttu-id="6fc85-139">Você pode usar o teclado para a navegação.</span><span class="sxs-lookup"><span data-stu-id="6fc85-139">You can use your keyboard for navigation.</span></span> <span data-ttu-id="6fc85-140">Use as teclas **Seta para cima** e **Seta para baixo** para mover-se entre linhas.</span><span class="sxs-lookup"><span data-stu-id="6fc85-140">Use the **Up arrow** and **Down arrow** keys to move between rows.</span></span> <span data-ttu-id="6fc85-141">Use as teclas **Seta para a direita** e **Seta para a esquerda** para expandir e recolher grupos.</span><span class="sxs-lookup"><span data-stu-id="6fc85-141">Use the **Right arrow** and **Left arrow** keys to expand and collapse groups.</span></span>
- <span data-ttu-id="6fc85-142">Para abrir ou fechar todos os níveis no gráfico de Gantt, **Expandir tudo** ou **Recolher tudo**.</span><span class="sxs-lookup"><span data-stu-id="6fc85-142">To open or close all levels in the Gantt chart, select **Expand all** or **Collapse all**.</span></span>
- <span data-ttu-id="6fc85-143">Para exibir o tempo de processamento relacionado, passe o mouse sobre uma tarefa.</span><span class="sxs-lookup"><span data-stu-id="6fc85-143">To view the related processing time, hover over a task.</span></span> <span data-ttu-id="6fc85-144">(As tarefas estão no nível mais baixo no gráfico Gantt).</span><span class="sxs-lookup"><span data-stu-id="6fc85-144">(Tasks are the lowest level in the Gantt chart.)</span></span>

#### <a name="view-an-additional-master-planning-run-to-compare-jobs"></a><span data-ttu-id="6fc85-145">Exibir uma execução do planejamento mestre adicional para comparar trabalhos</span><span class="sxs-lookup"><span data-stu-id="6fc85-145">View an additional master planning run to compare jobs</span></span>

<span data-ttu-id="6fc85-146">Ao selecionar um trabalho de planejamento mestre no campo **Mostrar execução de planejamento mestre adicional**, você poderá exibir uma exibição de planejamento mestre adicional no gráfico de Gantt e comparar os dois trabalhos.</span><span class="sxs-lookup"><span data-stu-id="6fc85-146">By selecting a master planning job on field **Show additional master planning run**, you can view an additional master planning run in the Gantt chart and compare the two jobs.</span></span>

#### <a name="bom-level-display"></a><span data-ttu-id="6fc85-147">Exibição do nível de BOM</span><span class="sxs-lookup"><span data-stu-id="6fc85-147">BOM-level display</span></span>

<span data-ttu-id="6fc85-148">Os níveis de lista de materiais (BOM) são mostrados de forma diferente para planejamento de cobertura, atrasos, ações e confirmação.</span><span class="sxs-lookup"><span data-stu-id="6fc85-148">Bill of materials (BOM) levels are shown differently for coverage planning, delays, actions, and firming.</span></span>

- <span data-ttu-id="6fc85-149">**Planejamento de cobertura** – os níveis de BOM são mostrados conforme esperado.</span><span class="sxs-lookup"><span data-stu-id="6fc85-149">**Coverage planning** – BOM levels are shown as expected.</span></span> <span data-ttu-id="6fc85-150">Eles são calculados de cima para baixo.</span><span class="sxs-lookup"><span data-stu-id="6fc85-150">They are calculated from the top down.</span></span>

    <span data-ttu-id="6fc85-151">**Exemplo:** nível 0, 1, 2 de BOM</span><span class="sxs-lookup"><span data-stu-id="6fc85-151">**Example:** BOM level 0, 1, 2</span></span>

- <span data-ttu-id="6fc85-152">**Atrasos** – os níveis de BOM são mostrados como os níveis de BOM de planejamento de cobertura multiplicados por –1.</span><span class="sxs-lookup"><span data-stu-id="6fc85-152">**Delays** – BOM levels are shown as the coverage planning BOM levels multiplied by –1.</span></span> <span data-ttu-id="6fc85-153">(Ou seja, eles têm um sinal negativo).</span><span class="sxs-lookup"><span data-stu-id="6fc85-153">(In other words, they have a negative sign.)</span></span>

    <span data-ttu-id="6fc85-154">**Exemplo:** nível –2, –1, 0 de BOM</span><span class="sxs-lookup"><span data-stu-id="6fc85-154">**Example:** BOM level –2, –1, 0</span></span>

- <span data-ttu-id="6fc85-155">**Mensagem de ação** – os níveis de BOM são mostrados conforme esperado.</span><span class="sxs-lookup"><span data-stu-id="6fc85-155">**Action message** – BOM levels are shown as expected.</span></span> <span data-ttu-id="6fc85-156">Eles são calculados de cima para baixo.</span><span class="sxs-lookup"><span data-stu-id="6fc85-156">They are calculated from the top down.</span></span>

    <span data-ttu-id="6fc85-157">**Exemplo:** nível 0, 1, 2 de BOM</span><span class="sxs-lookup"><span data-stu-id="6fc85-157">**Example:** BOM level 0, 1, 2</span></span>

- <span data-ttu-id="6fc85-158">**Confirmação automática** – os níveis de BOM são mostrados como 999 menos o nível de BOM de planejamento de cobertura.</span><span class="sxs-lookup"><span data-stu-id="6fc85-158">**Auto-firming** – BOM levels are shown as 999 minus the coverage planning BOM level.</span></span>

    <span data-ttu-id="6fc85-159">**Exemplo:** nível 999, 998, 997 de BOM</span><span class="sxs-lookup"><span data-stu-id="6fc85-159">**Example:** BOM level 999, 998, 997</span></span>

<span data-ttu-id="6fc85-160">A tabela a seguir resume o comportamento.</span><span class="sxs-lookup"><span data-stu-id="6fc85-160">The following table summarizes the behavior.</span></span>

| <span data-ttu-id="6fc85-161">Nível de BOM que é mostrado</span><span class="sxs-lookup"><span data-stu-id="6fc85-161">BOM level that is shown</span></span> | <span data-ttu-id="6fc85-162">Item final</span><span class="sxs-lookup"><span data-stu-id="6fc85-162">End item</span></span> | <span data-ttu-id="6fc85-163">Subcomponente</span><span class="sxs-lookup"><span data-stu-id="6fc85-163">Subcomponent</span></span> | <span data-ttu-id="6fc85-164">Matéria-prima</span><span class="sxs-lookup"><span data-stu-id="6fc85-164">Raw material</span></span> |
|---|---|---|---|
| <span data-ttu-id="6fc85-165">Planejamento de cobertura</span><span class="sxs-lookup"><span data-stu-id="6fc85-165">Coverage planning</span></span> | <span data-ttu-id="6fc85-166">0</span><span class="sxs-lookup"><span data-stu-id="6fc85-166">0</span></span> | <span data-ttu-id="6fc85-167">1</span><span class="sxs-lookup"><span data-stu-id="6fc85-167">1</span></span> | <span data-ttu-id="6fc85-168">2</span><span class="sxs-lookup"><span data-stu-id="6fc85-168">2</span></span> |
| <span data-ttu-id="6fc85-169">Atrasos</span><span class="sxs-lookup"><span data-stu-id="6fc85-169">Delays</span></span> | <span data-ttu-id="6fc85-170">0</span><span class="sxs-lookup"><span data-stu-id="6fc85-170">0</span></span> | <span data-ttu-id="6fc85-171">–1</span><span class="sxs-lookup"><span data-stu-id="6fc85-171">–1</span></span> | <span data-ttu-id="6fc85-172">–2</span><span class="sxs-lookup"><span data-stu-id="6fc85-172">–2</span></span> |
| <span data-ttu-id="6fc85-173">Mensagem de ação</span><span class="sxs-lookup"><span data-stu-id="6fc85-173">Action message</span></span> | <span data-ttu-id="6fc85-174">0</span><span class="sxs-lookup"><span data-stu-id="6fc85-174">0</span></span> | <span data-ttu-id="6fc85-175">1</span><span class="sxs-lookup"><span data-stu-id="6fc85-175">1</span></span> | <span data-ttu-id="6fc85-176">2</span><span class="sxs-lookup"><span data-stu-id="6fc85-176">2</span></span> |
| <span data-ttu-id="6fc85-177">Confirmação automática</span><span class="sxs-lookup"><span data-stu-id="6fc85-177">Auto-firming</span></span> | <span data-ttu-id="6fc85-178">999</span><span class="sxs-lookup"><span data-stu-id="6fc85-178">999</span></span> | <span data-ttu-id="6fc85-179">998</span><span class="sxs-lookup"><span data-stu-id="6fc85-179">998</span></span> | <span data-ttu-id="6fc85-180">997</span><span class="sxs-lookup"><span data-stu-id="6fc85-180">997</span></span> |

#### <a name="visualize-progress"></a><span data-ttu-id="6fc85-181">Visualizar progresso</span><span class="sxs-lookup"><span data-stu-id="6fc85-181">Visualize progress</span></span>

<span data-ttu-id="6fc85-182">Se você exibir um trabalho de planejamento mestre que esteja em execução, o andamento será mostrado por meio de cores no gráfico de Gantt.</span><span class="sxs-lookup"><span data-stu-id="6fc85-182">If you view a master planning job that is currently running, progress is shown through colors in the Gantt chart.</span></span> <span data-ttu-id="6fc85-183">As cores a seguir se aplicam ao tema azul.</span><span class="sxs-lookup"><span data-stu-id="6fc85-183">The following colors apply to the blue theme.</span></span> <span data-ttu-id="6fc85-184">Para outros temas de cor, as cores serão diferentes.</span><span class="sxs-lookup"><span data-stu-id="6fc85-184">For other color themes, the colors will differ.</span></span>

- <span data-ttu-id="6fc85-185">**Azul escuro** – tarefas de planejamento concluídas.</span><span class="sxs-lookup"><span data-stu-id="6fc85-185">**Dark blue** – Completed planning tasks.</span></span>
- <span data-ttu-id="6fc85-186">**Laranja** – a tarefa que está em andamento.</span><span class="sxs-lookup"><span data-stu-id="6fc85-186">**Orange** – The task that is currently in progress.</span></span>
- <span data-ttu-id="6fc85-187">**Azul claro** – a estimativa para as tarefas restantes.</span><span class="sxs-lookup"><span data-stu-id="6fc85-187">**Light blue** – The estimate for remaining tasks.</span></span>

<span data-ttu-id="6fc85-188">A cor é mostrada somente no nível mais baixo no gráfico de Gantt.</span><span class="sxs-lookup"><span data-stu-id="6fc85-188">The color is shown only on the lowest level in the Gantt chart.</span></span> <span data-ttu-id="6fc85-189">Selecione **Expandir tudo** para exibir todas as tarefas no trabalho de planejamento mestre.</span><span class="sxs-lookup"><span data-stu-id="6fc85-189">Select **Expand all** to view all tasks in the master planning job.</span></span> <span data-ttu-id="6fc85-190">A estimativa de tarefas restantes se baseia em trabalhos históricos de planejamento mestre.</span><span class="sxs-lookup"><span data-stu-id="6fc85-190">The estimate of remaining tasks is based on historical master planning jobs.</span></span>

## <a name="run-master-planning-and-track-processing-time"></a><span data-ttu-id="6fc85-191">Executar o planejamento mestre e controlar o tempo de processamento</span><span class="sxs-lookup"><span data-stu-id="6fc85-191">Run master planning and track processing time</span></span>

1. <span data-ttu-id="6fc85-192">No painel padrão, selecione **Planejamento mestre**.</span><span class="sxs-lookup"><span data-stu-id="6fc85-192">On the default dashboard, select **Master planning**.</span></span>
1. <span data-ttu-id="6fc85-193">No campo **Plano**, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="6fc85-193">In the **Plan** field, enter or select a value.</span></span>
1. <span data-ttu-id="6fc85-194">Selecione **Executar**.</span><span class="sxs-lookup"><span data-stu-id="6fc85-194">Select **Run**.</span></span>
1. <span data-ttu-id="6fc85-195">Defina a opção **Controlar tempo de processamento** como **Sim**.</span><span class="sxs-lookup"><span data-stu-id="6fc85-195">Set the **Track processing time** option to **Yes**.</span></span>
1. <span data-ttu-id="6fc85-196">No campo **Número de threads**, insira um número.</span><span class="sxs-lookup"><span data-stu-id="6fc85-196">In the **Number of threads** field, enter a number.</span></span>
1. <span data-ttu-id="6fc85-197">Na Guia Rápida **Registros a incluir**, selecione **Filtro**.</span><span class="sxs-lookup"><span data-stu-id="6fc85-197">On the **Records to include** FastTab, select **Filter**.</span></span>
1. <span data-ttu-id="6fc85-198">Na grade, selecione a linha em que o campo **Campo** é definido como **Número do item**.</span><span class="sxs-lookup"><span data-stu-id="6fc85-198">In the grid, select the row where the **Field** field is set to **Item number**.</span></span>
1. <span data-ttu-id="6fc85-199">No campo **Critérios**, insira um valor.</span><span class="sxs-lookup"><span data-stu-id="6fc85-199">In the **Criteria** field, enter a value.</span></span>
1. <span data-ttu-id="6fc85-200">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="6fc85-200">Select **OK**.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]