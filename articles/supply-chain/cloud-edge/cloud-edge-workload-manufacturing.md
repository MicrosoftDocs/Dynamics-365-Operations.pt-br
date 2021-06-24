---
title: Cargas de trabalho de execução de fabricação para unidades de escala de nuvem e de borda
description: Este tópico descreve como cargas de trabalho de execução de fabricação funcionam com unidades de escala de nuvem e de borda.
author: cabeln
ms.date: 10/06/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: SCM
ms.author: cabeln
ms.search.validFrom: 2020-10-06
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 9cd7dd8b9241171bdfdb3cc1379211a2fe99bbe1
ms.sourcegitcommit: 8d50c905a0c9d4347519549b587bdebab8ffc628
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2021
ms.locfileid: "6183987"
---
# <a name="manufacturing-execution-workloads-for-cloud-and-edge-scale-units"></a><span data-ttu-id="b0677-103">Cargas de trabalho de execução de fabricação para unidades de escala de nuvem e borda</span><span class="sxs-lookup"><span data-stu-id="b0677-103">Manufacturing execution workloads for cloud and edge scale units</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

> [!WARNING]
> <span data-ttu-id="b0677-104">A carga de trabalho de execução de fabricação está disponível na versão preliminar neste momento.</span><span class="sxs-lookup"><span data-stu-id="b0677-104">The manufacturing execution workload is available in preview at this point in time.</span></span>
> <span data-ttu-id="b0677-105">Algumas funcionalidades comerciais não têm suporte total na versão preliminar pública quando unidades de escala de carga de trabalho são usadas.</span><span class="sxs-lookup"><span data-stu-id="b0677-105">Some business functionality isn't fully supported in the public preview when workload scale units are used.</span></span>

<span data-ttu-id="b0677-106">Na execução de fabricação, as unidades de escala fornecem os seguintes recursos:</span><span class="sxs-lookup"><span data-stu-id="b0677-106">In manufacturing execution, scale units deliver the following capabilities:</span></span>

- <span data-ttu-id="b0677-107">Os operadores de máquina e os supervisores de chão de fábrica podem acessar o plano de produção operacional.</span><span class="sxs-lookup"><span data-stu-id="b0677-107">Machine operators and shop floor supervisors can access the operational production plan.</span></span>
- <span data-ttu-id="b0677-108">Os operadores de máquina podem manter o plano atualizado ao executar trabalhos de fabricação discretos e de processo.</span><span class="sxs-lookup"><span data-stu-id="b0677-108">Machine operators can keep the plan up to date by running discrete and process manufacturing jobs.</span></span>
- <span data-ttu-id="b0677-109">O supervisor de chão de fábrica pode ajustar o plano operacional.</span><span class="sxs-lookup"><span data-stu-id="b0677-109">The shop floor supervisor can adjust the operational plan.</span></span>
- <span data-ttu-id="b0677-110">Os trabalhadores podem acessar o tempo e a presença de entrada e de saída na borda para garantir o cálculo correto do pagamento do trabalhador.</span><span class="sxs-lookup"><span data-stu-id="b0677-110">Workers can access time and attendance for clock-in and clock-out on the edge, to ensure correct worker pay calculation.</span></span>

<span data-ttu-id="b0677-111">Este tópico descreve como cargas de trabalho de execução de fabricação funcionam com unidades de escala de nuvem e de borda.</span><span class="sxs-lookup"><span data-stu-id="b0677-111">This topic describes how manufacturing execution workloads work with cloud and edge scale units.</span></span>

## <a name="the-manufacturing-lifecycle"></a><span data-ttu-id="b0677-112">O ciclo de vida de fabricação</span><span class="sxs-lookup"><span data-stu-id="b0677-112">The manufacturing lifecycle</span></span>

<span data-ttu-id="b0677-113">A ilustração a seguir mostra que o ciclo de vida da fabricação é dividido em três fases: *Planejar*, *Executar* e *Finalizar*.</span><span class="sxs-lookup"><span data-stu-id="b0677-113">As the following illustration shows, the manufacturing lifecycle is divided into three phases: *Plan*, *Execute*, and *Finalize*.</span></span>

<span data-ttu-id="b0677-114">[![Fases de execução de fabricação quando um único ambiente é usado](media/mes-phases.png "Fases de execução de fabricação quando um único ambiente é usado")](media/mes-phases-large.png)</span><span class="sxs-lookup"><span data-stu-id="b0677-114">[![Manufacturing execution phases when a single environment is used](media/mes-phases.png "Manufacturing execution phases when a single environment is used")](media/mes-phases-large.png)</span></span>

<span data-ttu-id="b0677-115">A fase _Planejar_ inclui definição de produtos, planejamento, criação e agendamento de ordens e liberação.</span><span class="sxs-lookup"><span data-stu-id="b0677-115">The _Plan_ phase includes product definition, planning, order creation and scheduling, and release.</span></span> <span data-ttu-id="b0677-116">A etapa de liberação indica a transição da fase _Planejar_ para a fase _Executar_.</span><span class="sxs-lookup"><span data-stu-id="b0677-116">The release step indicates the transition from the _Plan_ phase to the _Execute_ phase.</span></span> <span data-ttu-id="b0677-117">Quando uma ordem de produção é liberada, os trabalhos de ordem de produção ficam visíveis no piso de produção e prontos para execução.</span><span class="sxs-lookup"><span data-stu-id="b0677-117">When a production order is released, the production order jobs will be visible on the production floor and ready for execution.</span></span>

<span data-ttu-id="b0677-118">Quando um trabalho de produção é marcado como concluído, ele passa da fase _Executar_ para a fase _Finalizar_.</span><span class="sxs-lookup"><span data-stu-id="b0677-118">When a production job is marked as completed, it moves from the _Execute_ phase to the _Finalize_ phase.</span></span> <span data-ttu-id="b0677-119">Na fase _Finalizar_, os registros da fase *Executar* passam por um fluxo de trabalho de aprovação, em que são calculados, aprovados e transferidos.</span><span class="sxs-lookup"><span data-stu-id="b0677-119">In the _Finalize_ phase, the registrations from the *Execute* phase go through an approval workflow, where they are calculated, approved, and transferred.</span></span> <span data-ttu-id="b0677-120">Nesse ponto, a ordem de produção é concluída.</span><span class="sxs-lookup"><span data-stu-id="b0677-120">At that point, the production order is completed.</span></span> <span data-ttu-id="b0677-121">Portanto, é gerada a base do pagamento dos trabalhadores.</span><span class="sxs-lookup"><span data-stu-id="b0677-121">Therefore, the basis for the workers' pay is generated.</span></span>

## <a name="splitting-the-execute-phase-into-a-separate-workload"></a><span data-ttu-id="b0677-122">Dividir a fase Executar em uma carga de trabalho separada</span><span class="sxs-lookup"><span data-stu-id="b0677-122">Splitting the Execute phase into a separate workload</span></span>

<span data-ttu-id="b0677-123">Conforme ilustrado a seguir, quando as unidades de escala são usadas, a fase _Executar_ é dividida como uma carga de trabalho separada.</span><span class="sxs-lookup"><span data-stu-id="b0677-123">As the following illustration shows, when scale units are used, the _Execute_ phase is split out as a separate workload.</span></span>

<span data-ttu-id="b0677-124">[![Fases de execução de fabricação quando unidades de escala são usadas](media/mes-phases-workloads.png "Fases de execução de fabricação quando unidades de escala são usadas")](media/mes-phases-workloads-large.png)</span><span class="sxs-lookup"><span data-stu-id="b0677-124">[![Manufacturing execution phases when scale units are used](media/mes-phases-workloads.png "Manufacturing execution phases when scale units are used")](media/mes-phases-workloads-large.png)</span></span>

<span data-ttu-id="b0677-125">O modelo passa de uma instalação de única instância para um modelo baseado no hub e em unidades de escala.</span><span class="sxs-lookup"><span data-stu-id="b0677-125">The model now goes from a single-instance installation to a model that is based on the hub and scale units.</span></span> <span data-ttu-id="b0677-126">As fases _Planejar_ e _Finalizar_ são executadas como operações back office no hub; a carga de trabalho de execução de fabricação é executada nas unidades de escala.</span><span class="sxs-lookup"><span data-stu-id="b0677-126">The _Plan_ and _Finalize_ phases run as back-office operations on the hub, and the manufacturing execution workload runs on the scale units.</span></span> <span data-ttu-id="b0677-127">Os dados são transferidos de forma assíncrona entre o hub e as unidades de escala.</span><span class="sxs-lookup"><span data-stu-id="b0677-127">Data is transferred asynchronously between the hub and scale units.</span></span>

<span data-ttu-id="b0677-128">Quando uma ordem de produção é liberada no hub, todos os dados necessários para processar os trabalhos de produção são transferidos para a unidade de escala.</span><span class="sxs-lookup"><span data-stu-id="b0677-128">When a production order is released on the hub, all data that is required to process production jobs is transferred to the scale unit.</span></span> <span data-ttu-id="b0677-129">Esses dados incluem ordens de produção, roteiros de produção, listas de materiais e produtos.</span><span class="sxs-lookup"><span data-stu-id="b0677-129">This data includes production orders, production routes, bills of materials, and products.</span></span> <span data-ttu-id="b0677-130">Os dados que não estão relacionados a uma ordem de produção (como atividades indiretas, códigos de ausência e parâmetros de produção) também são transferidos do hub para a unidade de escala.</span><span class="sxs-lookup"><span data-stu-id="b0677-130">Data that isn't related to a production order (such as indirect activities, absence codes, and production parameters) is also transferred from the hub to the scale unit.</span></span> <span data-ttu-id="b0677-131">Como regra, os dados obtidos no hub e que são transferidos para a unidade de escala só podem ser criados ou atualizados no hub.</span><span class="sxs-lookup"><span data-stu-id="b0677-131">As a rule, data that originates from the hub and that is transferred to the scale unit can be created or updated only on the hub.</span></span> <span data-ttu-id="b0677-132">Por exemplo, não é possível criar um novo código de ausência ou uma atividade indireta na unidade de escala &mdash; eles só podem ser usados para registro.</span><span class="sxs-lookup"><span data-stu-id="b0677-132">For example, a new absence code or indirect activity can't be created on the scale unit&mdash;they can be used only for registration.</span></span> <span data-ttu-id="b0677-133">Os registros feitos na unidade de escala durante a execução são transferidos para o hub, no qual a aprovação de tempo e presença, o estoque e as atualizações financeiras são processados.</span><span class="sxs-lookup"><span data-stu-id="b0677-133">The registrations that are made on the scale unit during execution are then transferred to the hub, where time and attendance approval, inventory, and financial updates are processed.</span></span>

## <a name="manufacturing-execution-tasks-that-can-be-run-on-workloads"></a><span data-ttu-id="b0677-134">Tarefas de execução de fabricação que podem ser executadas em cargas de trabalho</span><span class="sxs-lookup"><span data-stu-id="b0677-134">Manufacturing execution tasks that can be run on workloads</span></span>

<span data-ttu-id="b0677-135">As seguintes tarefas de execução de fabricação podem ser executadas no momento em cargas de trabalho quando as unidades de escala são usadas:</span><span class="sxs-lookup"><span data-stu-id="b0677-135">The following manufacturing execution tasks can currently be run on workloads when scale units are used:</span></span>

- <span data-ttu-id="b0677-136">Registro de entrada, login, registro de saída e ausência</span><span class="sxs-lookup"><span data-stu-id="b0677-136">Clock-in, log-in, clock-out, and absence</span></span>
- <span data-ttu-id="b0677-137">Iniciar trabalho</span><span class="sxs-lookup"><span data-stu-id="b0677-137">Start job</span></span>
- <span data-ttu-id="b0677-138">Agrupar trabalhos</span><span class="sxs-lookup"><span data-stu-id="b0677-138">Bundle jobs</span></span>
- <span data-ttu-id="b0677-139">Progresso do relatório</span><span class="sxs-lookup"><span data-stu-id="b0677-139">Report progress</span></span>
- <span data-ttu-id="b0677-140">Relatório de sucata</span><span class="sxs-lookup"><span data-stu-id="b0677-140">Report scrap</span></span>
- <span data-ttu-id="b0677-141">Atividade indireta</span><span class="sxs-lookup"><span data-stu-id="b0677-141">Indirect activity</span></span>
- <span data-ttu-id="b0677-142">Interrupção</span><span class="sxs-lookup"><span data-stu-id="b0677-142">Break</span></span>
- <span data-ttu-id="b0677-143">Relatar como finalizado e guardar (exige que você também execute a carga de trabalho de execução do armazém na sua unidade de escala, consulte também [Relatar como finalizado e guardar em uma unidade de escala](#RAF))</span><span class="sxs-lookup"><span data-stu-id="b0677-143">Report as finished and putaway (requires that you also run the warehouse execution workload on your scale unit, see also [Report as finished and putaway on a scale unit](#RAF))</span></span>

## <a name="working-with-manufacturing-execution-workloads-on-the-hub"></a><span data-ttu-id="b0677-144">Trabalhar com cargas de trabalho de execução de fabricação no hub</span><span class="sxs-lookup"><span data-stu-id="b0677-144">Working with manufacturing execution workloads on the hub</span></span>

<span data-ttu-id="b0677-145">Normalmente, os processos necessários para executar cargas de trabalho de execução de fabricação são executados automaticamente para manter o hub e todas as unidades de escala em sincronia, conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="b0677-145">Usually, the processes that are required to run manufacturing execution workloads run automatically to keep the hub and all the scale units in sync, as needed.</span></span> <span data-ttu-id="b0677-146">No entanto, se tiver problemas, você poderá disparar manualmente o processamento de registros brutos que são recebidos de cargas de trabalho e/ou verificar o log de processamento de registros.</span><span class="sxs-lookup"><span data-stu-id="b0677-146">However, if you're having trouble, you can manually trigger the processing of raw registrations that are received from workloads and/or check the registration processing log.</span></span>

### <a name="manually-process-raw-registrations"></a><span data-ttu-id="b0677-147">Processar manualmente registros brutos</span><span class="sxs-lookup"><span data-stu-id="b0677-147">Manually process raw registrations</span></span>

<span data-ttu-id="b0677-148">Um trabalho em lotes no Supply Chain Management é executado automaticamente para processar todos os registros que foram recebidos das cargas de trabalho.</span><span class="sxs-lookup"><span data-stu-id="b0677-148">A batch job in Supply Chain Management runs automatically to process all the registrations that have been received from the workloads.</span></span> <span data-ttu-id="b0677-149">Esse trabalho cria os diários de produção e as entradas do livro de registro necessários quando um registro é processado para um trabalho concluído na carga de trabalho.</span><span class="sxs-lookup"><span data-stu-id="b0677-149">This job creates the required production journals and logbook entries when a registration is processed for a completed job on the workload.</span></span>

<span data-ttu-id="b0677-150">Embora o trabalho em geral seja executado automaticamente, você pode executá-lo manualmente a qualquer momento, entrando no hub e acessando **Controle de produção \> Tarefas periódicas \> Gerenciamento de carga de trabalho back office \> Processar registros brutos**.</span><span class="sxs-lookup"><span data-stu-id="b0677-150">Although the job usually runs automatically, you can run it manually at any time by signing in to the hub and going to **Production control \> Periodic tasks \> Backoffice workload management \> Process raw registrations**.</span></span>

### <a name="check-the-raw-registration-processing-log"></a><span data-ttu-id="b0677-151">Verificar o log de processamento do registro bruto</span><span class="sxs-lookup"><span data-stu-id="b0677-151">Check the raw registration processing log</span></span>

<span data-ttu-id="b0677-152">Para revisar o log de processamento do registro, entre no hub e acesse **Controle de produção \> Tarefas periódicas \> Gerenciamento de carga de trabalho back office \> Log de processamento de registro bruto**.</span><span class="sxs-lookup"><span data-stu-id="b0677-152">To review the registration processing log, sign in to the hub, and go to **Production control \> Periodic tasks \> Backoffice workload management \> Raw registration processing log**.</span></span> <span data-ttu-id="b0677-153">A página **Log de processamento de registro bruto** mostra uma lista de registros brutos processados e o status de cada registro.</span><span class="sxs-lookup"><span data-stu-id="b0677-153">The **Raw registration processing log** page shows a list of processed raw registrations and the status of each registration.</span></span>

<span data-ttu-id="b0677-154">![Página Log de processamento de registro bruto](media/mes-processing-log.png "Página Log de processamento de registro bruto")</span><span class="sxs-lookup"><span data-stu-id="b0677-154">![Raw registration processing log page](media/mes-processing-log.png "Raw registration processing log page")</span></span>

<span data-ttu-id="b0677-155">Você pode trabalhar em qualquer registro na lista selecionando ele e um dos seguintes botões no Painel de Ações:</span><span class="sxs-lookup"><span data-stu-id="b0677-155">You can work on any registration in the list by selecting it and then selecting one of the following buttons on the Action Pane:</span></span>

- <span data-ttu-id="b0677-156">**Processar** – processe manualmente o registro selecionado.</span><span class="sxs-lookup"><span data-stu-id="b0677-156">**Process** – Manually process the selected registration.</span></span> <span data-ttu-id="b0677-157">Essa ação poderá ser útil se o trabalho _Processar registros brutos_ não for executado ou se ele falhar.</span><span class="sxs-lookup"><span data-stu-id="b0677-157">This action can be useful if the _Process raw registrations_ job hasn't run, or if it failed.</span></span>
- <span data-ttu-id="b0677-158">**Cancelar** – cancele o registro selecionado.</span><span class="sxs-lookup"><span data-stu-id="b0677-158">**Cancel** – Cancel the selected registration.</span></span>

## <a name="working-with-manufacturing-execution-workloads-on-a-scale-unit"></a><span data-ttu-id="b0677-159">Trabalhar com cargas de trabalho de execução de fabricação em uma unidade de escala</span><span class="sxs-lookup"><span data-stu-id="b0677-159">Working with manufacturing execution workloads on a scale unit</span></span>

<span data-ttu-id="b0677-160">Normalmente, os processos necessários para executar cargas de trabalho de execução de fabricação são executados automaticamente para manter o hub e todas as unidades de escala em sincronia, conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="b0677-160">Usually, the processes that are required to run manufacturing execution workloads run automatically to keep the hub and all the scale units in sync, as needed.</span></span> <span data-ttu-id="b0677-161">No entanto, se tiver problemas, você poderá verificar o histórico de ordens que foram processadas em uma unidade de escala ou executar manualmente o trabalho _Hub de fabricação para processador de mensagens da unidade de escala_.</span><span class="sxs-lookup"><span data-stu-id="b0677-161">However, if you're having trouble, you can check the history of orders that have been processed on a scale unit or manually run the _Manufacturing hub to scale unit message processor_ job.</span></span>

### <a name="view-the-history-of-manufacturing-jobs-that-have-been-processed-on-a-scale-unit"></a><span data-ttu-id="b0677-162">Exibir o histórico de trabalhos de fabricação que foram processados em uma unidade de escala</span><span class="sxs-lookup"><span data-stu-id="b0677-162">View the history of manufacturing jobs that have been processed on a scale unit</span></span>

<span data-ttu-id="b0677-163">Para revisar o histórico de trabalhos de fabricação que foram processados em uma unidade de escala, entre na máquina da unidade de escala e acesse **Controle de produção \> Tarefas periódicas \> Gerenciamento de carga de trabalho back office \> Histórico de processamento de trabalhos de fabricação**.</span><span class="sxs-lookup"><span data-stu-id="b0677-163">To review the history of manufacturing jobs that have been processed on a scale unit, sign in to the scale unit machine, and go to **Production control \> Periodic tasks \> Backoffice workload management \> Manufacturing jobs processing history**.</span></span> <span data-ttu-id="b0677-164">A página **Histórico de processamento de trabalhos de fabricação** mostra o histórico de processamento das ordens de produção na unidade de escala.</span><span class="sxs-lookup"><span data-stu-id="b0677-164">The **Manufacturing jobs processing history** page shows the processing history of the production orders on the scale unit.</span></span> <span data-ttu-id="b0677-165">Você pode trabalhar em qualquer ordem de produção selecionando ela e um dos seguintes botões no Painel de Ações:</span><span class="sxs-lookup"><span data-stu-id="b0677-165">You can work on any production order in the list by selecting it and then selecting one of the following buttons on the Action Pane:</span></span>

- <span data-ttu-id="b0677-166">**Processar** – processe manualmente a ordem de produção selecionada.</span><span class="sxs-lookup"><span data-stu-id="b0677-166">**Process** – Manually process the selected production order.</span></span>
- <span data-ttu-id="b0677-167">**Cancelar** – cancele a ordem de produção selecionada.</span><span class="sxs-lookup"><span data-stu-id="b0677-167">**Cancel** – Cancel the selected production order.</span></span>

### <a name="manufacturing-hub-to-scale-unit-message-processor-job"></a><span data-ttu-id="b0677-168">Trabalho Hub de fabricação para processador de mensagens da unidade de escala</span><span class="sxs-lookup"><span data-stu-id="b0677-168">Manufacturing hub to scale unit message processor job</span></span>

<span data-ttu-id="b0677-169">O trabalho _Hub de fabricação para processador de mensagens da unidade de escala_ processa dados do hub para a unidade de escala.</span><span class="sxs-lookup"><span data-stu-id="b0677-169">The _Manufacturing hub to scale unit message processor_ job processes data from the hub to the scale unit.</span></span> <span data-ttu-id="b0677-170">Esse trabalho é iniciado automaticamente quando a carga de trabalho de execução de fabricação é implantada.</span><span class="sxs-lookup"><span data-stu-id="b0677-170">This job is automatically started when the manufacturing execution workload is deployed.</span></span> <span data-ttu-id="b0677-171">No entanto, você pode executá-lo manualmente a qualquer momento, acessando **Controle de produção \> Tarefas periódicas \> Gerenciamento de carga de trabalho back office \> Hub de fabricação para processador de mensagens da unidade de escala**.</span><span class="sxs-lookup"><span data-stu-id="b0677-171">However, you can run it manually at any time by going to **Production control \> Periodic tasks \> Backoffice workload management \> Manufacturing hub to scale unit message processor**.</span></span>

<a name="RAF"></a>

## <a name="report-as-finished-and-putaway-on-a-scale-unit"></a><span data-ttu-id="b0677-172">Relatar como finalizado e guardar em uma unidade de escala</span><span class="sxs-lookup"><span data-stu-id="b0677-172">Report as finished and putaway on a scale unit</span></span>

<!-- KFM: 
This section describes how to enable the abilities to report as finished and then putaway finished items when you are using to a scale unit.

### Enable and use report as finished and putaway on a scale unit -->

<span data-ttu-id="b0677-173">Na versão atual, as operações de relatar como finalizado e guardar (para produtos acabados, coprodutos e subprodutos) são compatíveis pela [carga de trabalho de execução do armazém](cloud-edge-workload-warehousing.md) (e não a carga de trabalho de execução de fabricação).</span><span class="sxs-lookup"><span data-stu-id="b0677-173">In the current release, report as finished and putaway operations (for finished products, co-products, and by-products) are supported by the [warehouse execution workload](cloud-edge-workload-warehousing.md) (not the manufacturing execution workload).</span></span> <span data-ttu-id="b0677-174">Portanto, para usar esta funcionalidade quando conectado a uma unidade de escala, você deve fazer o seguinte:</span><span class="sxs-lookup"><span data-stu-id="b0677-174">Therefore, to use this functionality when connected to a scale unit, you must do the following:</span></span>

- <span data-ttu-id="b0677-175">Instale a carga de trabalho de execução do armazém e a carga de trabalho de execução de fabricação na sua unidade de escala.</span><span class="sxs-lookup"><span data-stu-id="b0677-175">Install both the warehouse execution workload and the manufacturing execution workload on your scale unit.</span></span>
- <span data-ttu-id="b0677-176">Use o aplicativo móvel Warehouse Management para relatar como finalizado e processar o trabalho de guardar.</span><span class="sxs-lookup"><span data-stu-id="b0677-176">Use the Warehouse Management mobile app to report as finished and process the putaway work.</span></span> <span data-ttu-id="b0677-177">No momento, a interface de execução do chão de fábrica não dão suporte a esses processos.</span><span class="sxs-lookup"><span data-stu-id="b0677-177">The production floor execution interface does not currently support these processes.</span></span>

<!-- KFM: API details needed

### Customize report as finished and putaway functionality

 -->

[!INCLUDE [cloud-edge-privacy-notice](../../includes/cloud-edge-privacy-notice.md)]

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
