---
title: Eventos do aplicativo de depósito
description: Este tópico descreve o processamento de eventos de aplicativos de depósito usado para processar mensagens de eventos do aplicativo de depósito como parte de um trabalho em lotes.
author: perlynne
manager: tfehr
ms.date: 09/02/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSMobileDeviceQueueEvent
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-10-09
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 210008c4a1366773f465c59b38eca30f11f0b38c
ms.sourcegitcommit: 286786445f72db20e993d37a63df0b886f8f5e99
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/12/2020
ms.locfileid: "3988362"
---
# <a name="warehouse-app-event-processing"></a><span data-ttu-id="4aed8-103">Processamento de eventos do aplicativo de depósito</span><span class="sxs-lookup"><span data-stu-id="4aed8-103">Warehouse app event processing</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="4aed8-104">Os trabalhos em lotes executados no Supply Chain Management podem usar dados de uma fila para processar eventos emitidos pelo aplicativo de depósito para reagir conforme a necessidade dos eventos sinalizados.</span><span class="sxs-lookup"><span data-stu-id="4aed8-104">Batch jobs running in Supply Chain Management can use data from a queue for processing events issued by the warehouse app to react as needed to the signaled events.</span></span> <span data-ttu-id="4aed8-105">Esse recurso adiciona eventos relevantes à fila em resposta a certos tipos de ações executadas por trabalhadores usando o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="4aed8-105">This feature add relevant events to the queue in response to certain types of actions taken by workers using the app.</span></span> <span data-ttu-id="4aed8-106">Um exemplo é ao usar o recurso **Criar e processar ordens de transferência do aplicativo de depósito**, as linhas e o cabeçalho da ordem de transferência serão criados e atualizados no back-end quando o sistema estiver executando o trabalho em lotes **Processar eventos do aplicativo de depósito**.</span><span class="sxs-lookup"><span data-stu-id="4aed8-106">An example is when using the **Create and process transfer orders from the warehouse app** feature, the transfer order header and lines get created and updated in the back end when the system is running the **Process warehouse app events** batch job.</span></span>

## <a name="enable-the-process-warehouse-app-events-feature"></a><span data-ttu-id="4aed8-107">Habilitar o recurso Processar eventos de aplicativo de depósito</span><span class="sxs-lookup"><span data-stu-id="4aed8-107">Enable the Process warehouse app events feature</span></span>

<span data-ttu-id="4aed8-108">Antes de poder usar esse recurso, ele deverá estar habilitado no seu sistema.</span><span class="sxs-lookup"><span data-stu-id="4aed8-108">Before you can use this feature, it must be enabled on your system.</span></span> <span data-ttu-id="4aed8-109">Os administradores podem usar a página [gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para verificar o status do recurso e ativá-lo, se necessário.</span><span class="sxs-lookup"><span data-stu-id="4aed8-109">Administrators can use the [feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) page to check the feature status and enable it if needed.</span></span> <span data-ttu-id="4aed8-110">O recurso Processar eventos de aplicativo de depósito é listado como:</span><span class="sxs-lookup"><span data-stu-id="4aed8-110">The Process warehouse app events feature is listed as:</span></span>

- <span data-ttu-id="4aed8-111">**Módulo** - gerenciamento de Depósito</span><span class="sxs-lookup"><span data-stu-id="4aed8-111">**Module** - Warehouse management</span></span>
- <span data-ttu-id="4aed8-112">**Nome do recurso** - Processar eventos de aplicativo de depósito</span><span class="sxs-lookup"><span data-stu-id="4aed8-112">**Feature name** - Process warehouse app events</span></span>

## <a name="set-up-a-batch-job-to-process-warehouse-app-events"></a><span data-ttu-id="4aed8-113">Configurar um trabalho em lotes para processar eventos de aplicativo de depósito</span><span class="sxs-lookup"><span data-stu-id="4aed8-113">Set up a batch job to process warehouse app events</span></span>

### <a name="process-warehouse-app-events"></a><span data-ttu-id="4aed8-114">Processar eventos do aplicativo de depósito</span><span class="sxs-lookup"><span data-stu-id="4aed8-114">Process warehouse app events</span></span>

<span data-ttu-id="4aed8-115">Configure um trabalho em lotes agendado para processar os eventos do aplicativo de depósito para a criação da ordem de transferência e as atualizações de linha.</span><span class="sxs-lookup"><span data-stu-id="4aed8-115">Set up a scheduled batch job to process the warehouse app events for the transfer order creation and line updates.</span></span>

1. <span data-ttu-id="4aed8-116">Vá para **Gerenciamento de depósito \> Tarefas periódicas \> Processar remessas de saída**.</span><span class="sxs-lookup"><span data-stu-id="4aed8-116">Go to **Warehouse management \> Periodic tasks \> Process warehouse app events**.</span></span>
1. <span data-ttu-id="4aed8-117">A caixa de diálogo Processar eventos do aplicativo de depósito será aberta.</span><span class="sxs-lookup"><span data-stu-id="4aed8-117">The Process warehouse app events dialog box opens.</span></span> <span data-ttu-id="4aed8-118">Expanda a guia rápida **Executar em segundo plano** e defina **Processamento em lotes** como **Sim**.</span><span class="sxs-lookup"><span data-stu-id="4aed8-118">Expand the **Run in background** FastTab and set **Batch processing** to **Yes**.</span></span>
1. <span data-ttu-id="4aed8-119">Na guia rápida **Executar em segundo plano**, selecione **Recorrência**.</span><span class="sxs-lookup"><span data-stu-id="4aed8-119">On the **Run in the background** FastTab, select **Recurrence**.</span></span>
1. <span data-ttu-id="4aed8-120">A caixa de diálogo **Definir recorrência** será aberta.</span><span class="sxs-lookup"><span data-stu-id="4aed8-120">The **Define recurrence** dialog box opens.</span></span> <span data-ttu-id="4aed8-121">Defina o plano de execução, conforme necessário para a sua empresa.</span><span class="sxs-lookup"><span data-stu-id="4aed8-121">Set the run schedule as needed for your business.</span></span>
1. <span data-ttu-id="4aed8-122">Selecione **OK** para retornar à caixa de diálogo **Processar eventos de aplicativo de depósito**.</span><span class="sxs-lookup"><span data-stu-id="4aed8-122">Select **OK** to return to the **Process warehouse app events** dialog box.</span></span>
1. <span data-ttu-id="4aed8-123">Selecione **OK** na caixa de diálogo **Processar eventos de aplicativo de depósito** para adicionar o trabalho em lotes à fila de lotes.</span><span class="sxs-lookup"><span data-stu-id="4aed8-123">Select **OK** in the **Process warehouse app events** dialog box to add the batch job to the batch queue.</span></span>

## <a name="query-warehouse-app-events"></a><span data-ttu-id="4aed8-124">Consultar eventos do aplicativo de depósito</span><span class="sxs-lookup"><span data-stu-id="4aed8-124">Query warehouse app events</span></span>

<span data-ttu-id="4aed8-125">Você pode exibir a fila de eventos e as mensagens de eventos geradas pelo aplicativo de depósito indo para **Gerenciamento de depósito \> Consultas e relatórios \> Logs do dispositivo móvel \> Eventos do aplicativo de depósito**.</span><span class="sxs-lookup"><span data-stu-id="4aed8-125">You can view the event queue and events messages generated by the warehouse app by going to **Warehouse management \> Inquiries and reports \> Mobile device logs \> Warehouse app events**.</span></span>

## <a name="the-standard-event-queue-process"></a><span data-ttu-id="4aed8-126">O processo da fila de eventos padrão</span><span class="sxs-lookup"><span data-stu-id="4aed8-126">The standard event queue process</span></span>

<span data-ttu-id="4aed8-127">A fila de eventos de aplicativos de depósito normalmente será usada com o seguinte fluxo descrito:</span><span class="sxs-lookup"><span data-stu-id="4aed8-127">The warehouse apps events queue will typically be used with the following described flow:</span></span>

1. <span data-ttu-id="4aed8-128">Um evento é adicionado à fila com uma mensagem de evento.</span><span class="sxs-lookup"><span data-stu-id="4aed8-128">An event gets added to the queue  with an event message.</span></span> <span data-ttu-id="4aed8-129">A nova mensagem inicialmente tem um estado de evento de **Espera**, o que significa que o trabalho em lotes **Processar eventos do aplicativo de depósito** não será coletado e processará essa mensagem.</span><span class="sxs-lookup"><span data-stu-id="4aed8-129">The new message initially has an Event state of **Waiting**, which means that the **Process warehouse app events** batch job will not pick up and process this message.</span></span>
1. <span data-ttu-id="4aed8-130">Assim que o estado da mensagem é atualizado para **Enfileirado**, o trabalho em lotes **Processar aplicativo de depósito** irá coletar e processar o evento.</span><span class="sxs-lookup"><span data-stu-id="4aed8-130">As soon as the message state is updated to **Queued**, the **Process warehouse app** events batch job will pick up and process the event.</span></span>
1. <span data-ttu-id="4aed8-131">O trabalho em lotes atualiza os estados de evento para **Concluído** ou **Com falha**, dependendo do processo solicitado ser possível.</span><span class="sxs-lookup"><span data-stu-id="4aed8-131">The batch job updates the event states to either **Completed** or **Failed**, depending on whether the requested process was possible.</span></span>
1. <span data-ttu-id="4aed8-132">Quando todas as mensagens de evento relacionadas forem **Concluídas**, o evento será excluído da fila.</span><span class="sxs-lookup"><span data-stu-id="4aed8-132">When all the related event messages are **Completed**, the event is deleted from the queue.</span></span>

 <span data-ttu-id="4aed8-133">Para obter um exemplo detalhado, consulte [Criar ordem de transferência do processo de aplicativo de depósito](create-transfer-order-from-warehouse-app.md).</span><span class="sxs-lookup"><span data-stu-id="4aed8-133">For a detailed example, see [Create transfer order from warehouse app process](create-transfer-order-from-warehouse-app.md).</span></span>

## <a name="handle-event-errors"></a><span data-ttu-id="4aed8-134">Tratar erros de eventos</span><span class="sxs-lookup"><span data-stu-id="4aed8-134">Handle event errors</span></span>

<span data-ttu-id="4aed8-135">Como parte do processamento de eventos de depósito, a atividade de mensagem solicitada pode não receber processos do trabalho em lotes.</span><span class="sxs-lookup"><span data-stu-id="4aed8-135">As part of the warehouse event processing, the requested message activity may not receive processes from the batch job.</span></span> <span data-ttu-id="4aed8-136">Nesse caso, a mensagem do evento será alterada para **Com falha**.</span><span class="sxs-lookup"><span data-stu-id="4aed8-136">In this case, the event message will change to **Failed**.</span></span> <span data-ttu-id="4aed8-137">Você pode usar as informações do **Log do lote** para saber o motivo e tomar as medidas necessárias para corrigir qualquer problema.</span><span class="sxs-lookup"><span data-stu-id="4aed8-137">You can use the **Batch log** information to learn why and take needed action to correct any problems.</span></span>

<span data-ttu-id="4aed8-138">Para obter um exemplo detalhado, consulte [Criar ordem de transferência do aplicativo de depósito](create-transfer-order-from-warehouse-app.md).</span><span class="sxs-lookup"><span data-stu-id="4aed8-138">For a detailed example, see [Create transfer order from warehouse app](create-transfer-order-from-warehouse-app.md).</span></span>

<span data-ttu-id="4aed8-139">Para redefinir uma mensagem do evento de aplicativo de depósito com falha:</span><span class="sxs-lookup"><span data-stu-id="4aed8-139">To reset a failed warehouse app event message:</span></span>

1. <span data-ttu-id="4aed8-140">Vá para **Gerenciamento de depósito \> Consultas e relatórios \> Logs do dispositivo móvel \> Eventos do aplicativo de depósito**.</span><span class="sxs-lookup"><span data-stu-id="4aed8-140">Go to **Warehouse management \> Inquiries and reports \> Mobile device logs \> Warehouse app events**.</span></span>
1. <span data-ttu-id="4aed8-141">Na Guia Rápida **Mensagens de eventos do aplicativo de depósito**, localize e selecione um evento relevante que está mostrando **Com Falha** na coluna **Estado do evento**.</span><span class="sxs-lookup"><span data-stu-id="4aed8-141">On the **Warehouse app event messages** FastTab, find and select a relevant event that is showing **Failed** in the **Event state** column.</span></span>
1. <span data-ttu-id="4aed8-142">Selecione **Redefinir** na barra de ferramentas **Mensagens de eventos do aplicativo de depósito**.</span><span class="sxs-lookup"><span data-stu-id="4aed8-142">Select **Reset** from the **Warehouse app event messages** toolbar.</span></span>
1. <span data-ttu-id="4aed8-143">Continue trabalhando até que todas as mensagens relevantes sejam redefinidas.</span><span class="sxs-lookup"><span data-stu-id="4aed8-143">Continue working until all relevant messages are reset.</span></span>

<span data-ttu-id="4aed8-144">Você também pode remover uma mensagem de evento **Com falha** usando a opção **Excluir** na barra de ferramentas **Mensagens de eventos do aplicativo de depósito**.</span><span class="sxs-lookup"><span data-stu-id="4aed8-144">You can also remove a **Failed** event message by using the **Delete** option on the **Warehouse app event messages** toolbar.</span></span>
