---
title: Agendar a criação de trabalho durante o ciclo
description: Este tópico descreve como configurar e usar o método de processamento Agendar ciclo de criação de trabalho.
author: perlynne
manager: mirzaab
ms.date: 01/14/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSPostMethod, WHSWavePostMethodTaskConfig, WHSWaveTemplateTable, WHSParameters, WHSWaveTableListPage, WHSWorkTableListPage, WHSWorkTable, BatchJobEnhanced, WHSPlannedWorkOrder
audience: Application User
ms.reviewer: ''
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2021-01-14
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 36a450f78695f617056875f8d236fe46bc66aaaf
ms.sourcegitcommit: 2b4809e60974e72df9476ffd62706b1bfc8da4a7
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/04/2021
ms.locfileid: "5501213"
---
# <a name="schedule-work-creation-during-wave"></a><span data-ttu-id="9c8c7-103">Agendar a criação de trabalho durante o ciclo</span><span class="sxs-lookup"><span data-stu-id="9c8c7-103">Schedule work creation during wave</span></span>

[!include [banner](../../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

<span data-ttu-id="9c8c7-104">Use o recurso *Agendar criação de trabalho* como parte do seu processo cíclico para ajudar a aumentar o resultado do processamento em ciclos, fazendo com que o sistema crie o trabalho usando o processamento paralelo.</span><span class="sxs-lookup"><span data-stu-id="9c8c7-104">Use the *Schedule work creation* feature as part of your waving process to help increase wave processing throughput by having the system create work using parallel processing.</span></span>

<span data-ttu-id="9c8c7-105">Quando a funcionalidade estiver habilitada, o trabalho planejado será criado automaticamente, e o sistema eventualmente irá processá-lo para criar o trabalho real.</span><span class="sxs-lookup"><span data-stu-id="9c8c7-105">When the functionality is enabled, planned work will automatically get created, which the system will eventually process to create actual work.</span></span> <span data-ttu-id="9c8c7-106">Se o número de linhas de carga de ciclos atingir um limite predeterminado, o sistema criará o trabalho real mais rapidamente, aplicando o processamento paralelo assíncrono.</span><span class="sxs-lookup"><span data-stu-id="9c8c7-106">If the number of wave load lines reaches a predetermined threshold, the system will create actual work more quickly by applying parallel, asynchronous processing.</span></span>

## <a name="enable-the-schedule-work-creation-feature"></a><span data-ttu-id="9c8c7-107">Habilitar o recurso Agendar criação de trabalho</span><span class="sxs-lookup"><span data-stu-id="9c8c7-107">Enable the Schedule work creation feature</span></span>

### <a name="enable-the-feature-in-feature-management"></a><span data-ttu-id="9c8c7-108">Habilitar o recurso no gerenciamento de recursos</span><span class="sxs-lookup"><span data-stu-id="9c8c7-108">Enable the feature in feature management</span></span>

<span data-ttu-id="9c8c7-109">Para que você possa usar o recurso *Agendar criação de trabalho*, ele deve estar ativado no sistema.</span><span class="sxs-lookup"><span data-stu-id="9c8c7-109">Before you can use the *Schedule work creation* feature, it must be turned on in your system.</span></span> <span data-ttu-id="9c8c7-110">Os administradores podem usar o espaço de trabalho [Gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para verificar o status do recurso e ativá-lo, se necessário.</span><span class="sxs-lookup"><span data-stu-id="9c8c7-110">Admins can use the [Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) workspace to check the status of the feature and turn it on if it's required.</span></span> <span data-ttu-id="9c8c7-111">Nesse caso, o recurso é listado da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="9c8c7-111">There, the feature is listed in the following way:</span></span>

- <span data-ttu-id="9c8c7-112">**Módulo:** *Gerenciamento de Depósito*</span><span class="sxs-lookup"><span data-stu-id="9c8c7-112">**Module:** *Warehouse management*</span></span>
- <span data-ttu-id="9c8c7-113">**Nome do recurso:** *Agendar criação de trabalho*</span><span class="sxs-lookup"><span data-stu-id="9c8c7-113">**Feature name:** *Schedule work creation*</span></span>

> [!NOTE]
> <span data-ttu-id="9c8c7-114">O recurso *Bloquear trabalho em toda a organização* deve estar habilitado para que você possa habilitar o recurso *Agendar criação de trabalho*.</span><span class="sxs-lookup"><span data-stu-id="9c8c7-114">The *Organization-wide work blocking* feature must be enabled before you can enable *Schedule work creation*.</span></span>

### <a name="manually-enable-batch-processing-of-waves"></a><span data-ttu-id="9c8c7-115">Habilitar o processamento manualmente em lotes de ciclos</span><span class="sxs-lookup"><span data-stu-id="9c8c7-115">Manually enable batch processing of waves</span></span>

<span data-ttu-id="9c8c7-116">Para aproveitar um método assíncrono paralelo para criar trabalho de depósito, o processo de ciclos deve estar sendo executado em lotes.</span><span class="sxs-lookup"><span data-stu-id="9c8c7-116">To take advantage of a parallel asynchronous method to create warehouse work, your wave process must be running in batch.</span></span> <span data-ttu-id="9c8c7-117">Para fazer essa configuração:</span><span class="sxs-lookup"><span data-stu-id="9c8c7-117">To set this up:</span></span>

1. <span data-ttu-id="9c8c7-118">Vá para **Gerenciamento de depósito \> Configuração \> Parâmetros de gerenciamento de depósito**.</span><span class="sxs-lookup"><span data-stu-id="9c8c7-118">Go to **Warehouse management \> Setup \> Warehouse management parameters**.</span></span>

1. <span data-ttu-id="9c8c7-119">Na guia **Geral**, defina a opção **Processar ciclos em lote** como *Sim*.</span><span class="sxs-lookup"><span data-stu-id="9c8c7-119">On the **General** tab, set **Process waves in batch** to *Yes*.</span></span> <span data-ttu-id="9c8c7-120">Se preferir, você também pode selecionar um **Grupo de lotes de processamento em ciclos** dedicado para impedir que o processamento de fila em lotes seja executado ao mesmo tempo que outros processos.</span><span class="sxs-lookup"><span data-stu-id="9c8c7-120">Optionally, you can also select a dedicated **Wave processing batch group** to prevent your batch queue processing from running at the same time as other processes.</span></span>

1. <span data-ttu-id="9c8c7-121">Defina o **Tempo de espera para o bloqueio (ms)**, que se aplica quando o sistema está processando vários ciclos ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="9c8c7-121">Set the **Wait for lock (ms) time**, which applies when the system is processing several waves at the same time.</span></span> <span data-ttu-id="9c8c7-122">Para a maioria dos processos em ciclos maiores, recomendamos um valor de *60.000*.</span><span class="sxs-lookup"><span data-stu-id="9c8c7-122">For most larger waving processes, we recommend a value of *60000*.</span></span>

### <a name="manually-enable-the-new-wave-step-method-for-existing-wave-templates"></a><span data-ttu-id="9c8c7-123">Habilitar manualmente o novo método de etapa de ciclo para modelos de ciclo existentes</span><span class="sxs-lookup"><span data-stu-id="9c8c7-123">Manually enable the new wave step method for existing wave templates</span></span>

<span data-ttu-id="9c8c7-124">Comece criando o novo método de etapa de ciclo e habilite-o para o processamento de tarefas assíncronas paralelas.</span><span class="sxs-lookup"><span data-stu-id="9c8c7-124">Start by creating the new wave step method and enabling it for parallel asynchronous task processing.</span></span>

1. <span data-ttu-id="9c8c7-125">Vá para **Gerenciamento de depósito \> Configuração \> Ondas \> Métodos de processo de onda**.</span><span class="sxs-lookup"><span data-stu-id="9c8c7-125">Go to **Warehouse management \> Setup \> Waves \> Wave process methods**.</span></span>

1. <span data-ttu-id="9c8c7-126">Selecione  **Gerar método novamente** e observe que *WHSScheduleWorkCreationWaveStepMethod* foi adicionado à lista de métodos de processo de ciclo que podem ser usados nos modelos de ciclo de remessa.</span><span class="sxs-lookup"><span data-stu-id="9c8c7-126">Select  **Regenerate method** and note that *WHSScheduleWorkCreationWaveStepMethod* has been added to the list of wave process methods you can use in your shipping wave templates.</span></span>

1. <span data-ttu-id="9c8c7-127">Selecione o registro com o **Nome do método** *WHSScheduleWorkCreationWaveStepMethod* e selecione **Configuração de tarefas**.</span><span class="sxs-lookup"><span data-stu-id="9c8c7-127">Select the record with the **Method name** *WHSScheduleWorkCreationWaveStepMethod* and select **Task configuration**.</span></span>

1. <span data-ttu-id="9c8c7-128">Para adicionar uma nova linha à grade, selecione **Novo** no Painel de Ações e use as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="9c8c7-128">To add a new row to the grid, select **New** on the Action Pane and use the following settings:</span></span>

    - <span data-ttu-id="9c8c7-129">**Depósito** - Selecione o depósito que será usado para agendar o processamento de criação de trabalho.</span><span class="sxs-lookup"><span data-stu-id="9c8c7-129">**Warehouse** - Select the warehouse you will use to schedule work creation processing.</span></span>

    - <span data-ttu-id="9c8c7-130">**Número máximo de tarefas em lotes** - Especifique um número máximo de tarefas em lotes.</span><span class="sxs-lookup"><span data-stu-id="9c8c7-130">**Maximum number of batch tasks** - Specify a maximum number of batch tasks.</span></span> <span data-ttu-id="9c8c7-131">Na maioria dos casos, esse valor deve estar no intervalo de 8-16, mas recomendamos que você experimente a configuração ideal com base nos seus cenários.</span><span class="sxs-lookup"><span data-stu-id="9c8c7-131">In most cases, this value should be in the range from 8-16, however we recommend that you experiment with the optimal setting based on your scenarios.</span></span>

    - <span data-ttu-id="9c8c7-132">**Grupo de lotes de processamento em ciclos** - Selecione um grupo de lotes de processamento em ciclos dedicados para otimizar o processamento da fila de lotes.</span><span class="sxs-lookup"><span data-stu-id="9c8c7-132">**Wave processing batch group** - Select a dedicated wave processing batch group to optimize your batch queue processing.</span></span>

<span data-ttu-id="9c8c7-133">Agora, você está pronto para atualizar um modelo de ciclo existente (ou criar um novo) para usar o método de processamento em ciclos *Agendar criação de trabalho*.</span><span class="sxs-lookup"><span data-stu-id="9c8c7-133">Now you are ready to update an existing wave template (or create a new one) to use the *Schedule work creation* wave processing method.</span></span>

1. <span data-ttu-id="9c8c7-134">Vá para **Gerenciamento de depósito \> Configuração \> Ciclos \> Modelos de ciclo**.</span><span class="sxs-lookup"><span data-stu-id="9c8c7-134">Go to **Warehouse management \> Setup \> Waves \> Wave templates**.</span></span>

1. <span data-ttu-id="9c8c7-135">Selecione **Editar** no Painel de Ações.</span><span class="sxs-lookup"><span data-stu-id="9c8c7-135">Select **Edit** on the Action Pane.</span></span>

1. <span data-ttu-id="9c8c7-136">No painel de lista, selecione o modelo de ciclo que deseja atualizar (se você estiver testando com dados de demonstração, poderá usar *24 Padrão de remessa*).</span><span class="sxs-lookup"><span data-stu-id="9c8c7-136">In the list pane, select the wave template you would like to update (if you are testing using demo data, then you could use *24 Shipping default*).</span></span>

1. <span data-ttu-id="9c8c7-137">Expanda a guia rápida **Métodos** e selecione a linha com o **Nome** *Agendar criação de trabalho* na grade **Métodos restantes**.</span><span class="sxs-lookup"><span data-stu-id="9c8c7-137">Expand the **Methods** FastTab and select the row with the **Name** *Schedule work creation* in the **Remaining methods** grid.</span></span>

1. <span data-ttu-id="9c8c7-138">Selecione a seta apontando para a coluna **Métodos selecionados** para mover a linha selecionada para essa coluna.</span><span class="sxs-lookup"><span data-stu-id="9c8c7-138">Select the arrow pointing to the **Selected methods** column to move the selected row to that column.</span></span> <span data-ttu-id="9c8c7-139">(Você só pode ter um método selecionado de cada vez que use o *WHSScheduleWorkCreationWaveStepMethod* ou *createWork*, portanto, a linha existente com o **Nome do método** *createWork* será automaticamente movida para a grade **Métodos restantes**.)</span><span class="sxs-lookup"><span data-stu-id="9c8c7-139">(You can only have one selected method at a time that uses either *WHSScheduleWorkCreationWaveStepMethod* or *createWork*, so the existing row with **Method name** *createWork* is automatically moved to the **Remaining methods** grid.)</span></span>

## <a name="set-wave-task-processing-threshold-data"></a><span data-ttu-id="9c8c7-140">Definir dados do limite de processamento de tarefa de ciclo</span><span class="sxs-lookup"><span data-stu-id="9c8c7-140">Set wave task processing threshold data</span></span>

<span data-ttu-id="9c8c7-141">O sistema criará dados padrão de limite de processamento de tarefa de ciclo na primeira vez que um processo de ciclo for executado usando qualquer processamento baseado em tarefa.</span><span class="sxs-lookup"><span data-stu-id="9c8c7-141">The system will create default wave task processing threshold data the first time a wave process runs using any task-based processing.</span></span> <span data-ttu-id="9c8c7-142">Os dados são usados para controlar quando o processamento de ciclo será executado assincronamente e será baseado em tarefas, o que permite processar e criar trabalhos em paralelo.</span><span class="sxs-lookup"><span data-stu-id="9c8c7-142">The data is used to control when wave processing will run asynchronously and be task-based, which enables it to process and create work in parallel.</span></span>

<span data-ttu-id="9c8c7-143">Os dados padrão usarão inicialmente um valor limite de 15 para o número mínimo de linhas de carregamento (MINIMUMWAVELOADLINES).</span><span class="sxs-lookup"><span data-stu-id="9c8c7-143">The default data will initially use a threshold value of 15 for the minimum number of load lines (MINIMUMWAVELOADLINES).</span></span> <span data-ttu-id="9c8c7-144">Isso significa que, quando o sistema processa um ciclo com mais de 15 linhas de cargas , ele usará o processamento de tarefa assíncrona.</span><span class="sxs-lookup"><span data-stu-id="9c8c7-144">This means that when the system processes a wave with more than 15 loads lines, it will use asynchronous task processing.</span></span> <span data-ttu-id="9c8c7-145">Você pode inserir ou atualizar manualmente esses dados na tabela **WHSWaveTaskProcessingThresholdParameters** em seus ambientes de teste, mas se precisar alterar essa configuração em um ambiente de produção, precisará contatar o Suporte da Microsoft para solicitar a atualização.</span><span class="sxs-lookup"><span data-stu-id="9c8c7-145">You can manually insert/update this data in the **WHSWaveTaskProcessingThresholdParameters** table in your test environments, but if you need to change this setting in a production environment, you must contact Microsoft Support to request the update.</span></span>

## <a name="work-with-the-feature"></a><span data-ttu-id="9c8c7-146">Trabalhar com o recurso</span><span class="sxs-lookup"><span data-stu-id="9c8c7-146">Work with the feature</span></span>

<span data-ttu-id="9c8c7-147">Quando a funcionalidade *Agendar criação de trabalho* for habilitada, o processamento em ciclos criará um trabalho planejado, que acabará sendo usado pelo novo processo de criação de trabalho.</span><span class="sxs-lookup"><span data-stu-id="9c8c7-147">When the *Schedule work creation* functionality is enabled, wave processing will create planned work, which will eventually be used by the new work creation process.</span></span> <span data-ttu-id="9c8c7-148">Durante a criação do trabalho, o trabalho será bloqueado usando o recurso *Bloquear trabalho em toda a organização*.</span><span class="sxs-lookup"><span data-stu-id="9c8c7-148">During work creation, the work will be blocked using the *Organization-wide work blocking* feature.</span></span>

<span data-ttu-id="9c8c7-149">O fluxograma a seguir mostra como o trabalho planejado é criado durante o processamento em ciclos.</span><span class="sxs-lookup"><span data-stu-id="9c8c7-149">The following flowchart shows how planned work is created during wave processing.</span></span>

![Agendar criação de trabalho](media/schedule-work-creation-process.png)

### <a name="planned-work"></a><span data-ttu-id="9c8c7-151">Trabalho planejado</span><span class="sxs-lookup"><span data-stu-id="9c8c7-151">Planned work</span></span>

<span data-ttu-id="9c8c7-152">A página **Detalhes do trabalho planejado** (**Gerenciamento de depósito \> Trabalho \> Detalhes do trabalho planejado**) mostra informações sobre o trabalho planejado, que é inicialmente criado durante o processamento em ciclos.</span><span class="sxs-lookup"><span data-stu-id="9c8c7-152">The **Planned work details** page (**Warehouse management \> Work \> Planned work details**) shows information about the planned work, which is initially created during wave processing.</span></span> <span data-ttu-id="9c8c7-153">Estes são os **Status de progresso** disponíveis:</span><span class="sxs-lookup"><span data-stu-id="9c8c7-153">The following **Process status** values are available:</span></span>

- <span data-ttu-id="9c8c7-154">**Em fila** - O trabalho planejado está aguardando para ser usado para criar trabalho.</span><span class="sxs-lookup"><span data-stu-id="9c8c7-154">**Queued** - The planned work is waiting to be used to create work.</span></span>
- <span data-ttu-id="9c8c7-155">**Concluído** - O trabalho planejado foi usado para criar trabalho.</span><span class="sxs-lookup"><span data-stu-id="9c8c7-155">**Completed** - The planned work has been used to create work.</span></span>
- <span data-ttu-id="9c8c7-156">**Falha** - O processamento em ciclos falhou.</span><span class="sxs-lookup"><span data-stu-id="9c8c7-156">**Failed** – The wave processing has failed.</span></span> <span data-ttu-id="9c8c7-157">Observe que o trabalho planejado pode estar em um estado de **Falha** com ou sem trabalho real relacionado.</span><span class="sxs-lookup"><span data-stu-id="9c8c7-157">Note that the planned work can be in a **Failed** state with or without related actual work.</span></span> <span data-ttu-id="9c8c7-158">Quando o processo de criação do trabalho real falha, o trabalho real permanece no status *Cancelado*.</span><span class="sxs-lookup"><span data-stu-id="9c8c7-158">When the actual work creation process fails, the actual work remains in status *Cancelled*.</span></span>

### <a name="batch-job-for-the-work-creation-process"></a><span data-ttu-id="9c8c7-159">Trabalho em lotes para o processo de criação de trabalho</span><span class="sxs-lookup"><span data-stu-id="9c8c7-159">Batch job for the work creation process</span></span>

<span data-ttu-id="9c8c7-160">Para exibir os trabalhos em lotes para o processamento em ciclos, selecione **Trabalhos em lotes** no painel de ações na página **Todas as ondas**.</span><span class="sxs-lookup"><span data-stu-id="9c8c7-160">To view the batch jobs for processing waves, select **Batch jobs** on the Action Pane on the **All waves** page.</span></span>

<span data-ttu-id="9c8c7-161">Aqui, você pode exibir todos os detalhes da tarefa em lotes para cada um dos IDs do trabalho em lotes.</span><span class="sxs-lookup"><span data-stu-id="9c8c7-161">From here, you can view all the batch task details for each of the batch job IDs.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]