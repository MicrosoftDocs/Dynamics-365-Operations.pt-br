---
title: Gravador de tarefa e Ajuda do Retail Modern POS (MPOS) e Cloud POS
description: Este tópico descreve como utilizar o Gravador de tarefas no Retail Modern POS e no Cloud POS.
author: mugunthanm
manager: AnnBe
ms.date: 06/19/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailTerminalTable, SystemParameters
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 1205393
ms.assetid: 2f13e9cf-55b5-458b-8c32-3f8cd98c9ecf
ms.search.region: Global
ms.search.industry: Retail
ms.author: mumani
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 0ab8456d81fbe2dca495b65b932395572242a25c
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/01/2020
ms.locfileid: "3021621"
---
# <a name="task-recorder-and-help-for-retail-modern-pos-mpos-and-cloud-pos"></a><span data-ttu-id="9ff16-103">Gravador de tarefa e Ajuda do Retail Modern POS (MPOS) e Cloud POS</span><span class="sxs-lookup"><span data-stu-id="9ff16-103">Task recorder and Help for Retail Modern POS (MPOS) and Cloud POS</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="9ff16-104">Este tópico descreve como utilizar o Gravador de tarefas no Retail Modern POS e no Cloud POS.</span><span class="sxs-lookup"><span data-stu-id="9ff16-104">This topic describes how to use Task recorder in Retail Modern POS and Cloud POS.</span></span>

## <a name="overview"></a><span data-ttu-id="9ff16-105">Visão Geral</span><span class="sxs-lookup"><span data-stu-id="9ff16-105">Overview</span></span>

<span data-ttu-id="9ff16-106">O Gravador de tarefas do Retail Modern POS ou do PDV em Nuvem é uma nova solução que foi criada com foco na alta capacidade de resposta.</span><span class="sxs-lookup"><span data-stu-id="9ff16-106">Task recorder in Retail Modern POS or Cloud POS is a new solution that was built with a focus on high responsiveness.</span></span> <span data-ttu-id="9ff16-107">Ele oferece uma API (interface de programa aplicativo) flexível para extensibilidade e integração direta com os registros dos consumidores do processo de negócios.</span><span class="sxs-lookup"><span data-stu-id="9ff16-107">It provides a flexible application programming interface (API) for extensibility and seamless integration with consumers of business process recordings.</span></span> <span data-ttu-id="9ff16-108">Além disso, a integração do Gravador de tarefas com a ferramenta BPM (Modelador de processo de negócios) no Microsoft Dynamics Lifecycle Services ([https://bpm.lcs.dynamics.com](https://bpm.lcs.dynamics.com/)) foi apresentada.</span><span class="sxs-lookup"><span data-stu-id="9ff16-108">Additionally, Task recorder integration with the Business process modeler (BPM) tool on Microsoft Dynamics Lifecycle Services ([https://bpm.lcs.dynamics.com](https://bpm.lcs.dynamics.com/)) has been brought forward.</span></span> <span data-ttu-id="9ff16-109">Portanto, os usuários podem continuar a gerar diagramas sofisticados de processo de negócios a partir de gravações para analisar e projetar seus aplicativos.</span><span class="sxs-lookup"><span data-stu-id="9ff16-109">Therefore, users can continue to produce rich business process diagrams from recordings to analyze and design their applications.</span></span>

## <a name="architecture"></a><span data-ttu-id="9ff16-110">Arquitetura</span><span class="sxs-lookup"><span data-stu-id="9ff16-110">Architecture</span></span>

<span data-ttu-id="9ff16-111">O Gravador de tarefas pode registrar ações de usuário no cliente com fidelidade precisa.</span><span class="sxs-lookup"><span data-stu-id="9ff16-111">Task recorder can record user actions in the client with exact fidelity.</span></span> <span data-ttu-id="9ff16-112">Cada controle é instrumentado para notificar o Gravador de tarefas sobre a execução de uma ação de usuário.</span><span class="sxs-lookup"><span data-stu-id="9ff16-112">Each control is instrumented to notify Task recorder about the execution of a user action.</span></span> <span data-ttu-id="9ff16-113">O controle notifica o Gravador de tarefas sobre a ocorrência de um evento e passa adiante todas as informações pertinentes sobre a ação de usuário correspondente em tempo real.</span><span class="sxs-lookup"><span data-stu-id="9ff16-113">The control notifies Task recorder that an event occurred and passes along all pertinent information about the corresponding user action in real time.</span></span> <span data-ttu-id="9ff16-114">Com essas informações, o Gravador de tarefas pode capturar o tipo de ação de usuário (como um clique de botão, uma entrada de valor ou a navegação) e quaisquer dados relacionados à ação de usuário (como o valor e o tipo dos dados de entrada, o contexto de formulário ou o contexto de registro).</span><span class="sxs-lookup"><span data-stu-id="9ff16-114">From this information, Task recorder can capture the type of user action (such as a button click, value entry, or navigation) and any data that is related to the user action (such as the input data value and type, form context, or record context).</span></span> <span data-ttu-id="9ff16-115">O Gravador de tarefas mantém as informações com detalhes suficientes para ajudar a garantir que a reprodução da gravação possa executar as ações gravadas exatamente como o usuário as executaria.</span><span class="sxs-lookup"><span data-stu-id="9ff16-115">Task recorder persists the information with enough detail to help guarantee that a playback of the recording can perform the recorded actions exactly as the user performed them.</span></span> <span data-ttu-id="9ff16-116">(O recurso de reprodução ainda não foi implementado no Retail Modern POS ou no PDV em Nuvem).</span><span class="sxs-lookup"><span data-stu-id="9ff16-116">(The playback feature isn't yet implemented at Retail modern POS or Cloud POS.)</span></span>

## <a name="basic-configuration"></a><span data-ttu-id="9ff16-117">Configuração básica</span><span class="sxs-lookup"><span data-stu-id="9ff16-117">Basic configuration</span></span>

<span data-ttu-id="9ff16-118">Para habilitar a gravação de tarefas no PDV, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="9ff16-118">To enable task recording in POS, follow these steps.</span></span>

1. <span data-ttu-id="9ff16-119">Clique em **Varejo e Comércio** &gt; **Configuração do canal** &gt; **Configuração do PDV** &gt; **Registros**.</span><span class="sxs-lookup"><span data-stu-id="9ff16-119">Click **Retail and Commerce** &gt; **Channel Setup** &gt; **POS Setup** &gt; **Registers**.</span></span>
2. <span data-ttu-id="9ff16-120">Clique em registro em que a gravação de tarefas será habilitada.</span><span class="sxs-lookup"><span data-stu-id="9ff16-120">Click the register to enable task recording on.</span></span>
3. <span data-ttu-id="9ff16-121">Na guia **Registrar**, na Guia Rápida **Geral**, defina a opção **Habilitar gravação de tarefas** como **Sim**.</span><span class="sxs-lookup"><span data-stu-id="9ff16-121">On the **Register** tab, on the **General** FastTab, set the **Enable task recording** option to **Yes**.</span></span>
4. <span data-ttu-id="9ff16-122">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="9ff16-122">Click **Save**.</span></span>
5. <span data-ttu-id="9ff16-123">Vá para **Retail e Commerce** &gt; **TI de Varejo e Comércio** &gt; **Agenda de distribuição**.</span><span class="sxs-lookup"><span data-stu-id="9ff16-123">Go to **Retail and Commerce** &gt; **Retail and Commerce IT** &gt; **Distribution schedule**.</span></span>
6. <span data-ttu-id="9ff16-124">Selecione o trabalho **Registros (1090)** e então clique em **Executar agora**.</span><span class="sxs-lookup"><span data-stu-id="9ff16-124">Select the **Registers (1090)** job, and then click **Run now**.</span></span>

## <a name="create-a-recording"></a><span data-ttu-id="9ff16-125">Criar uma gravação</span><span class="sxs-lookup"><span data-stu-id="9ff16-125">Create a recording</span></span>

<span data-ttu-id="9ff16-126">Siga estas etapas para criar uma nova gravação usando o Gravador de tarefas.</span><span class="sxs-lookup"><span data-stu-id="9ff16-126">Follow these steps to create a new recording using Task recorder.</span></span>

1. <span data-ttu-id="9ff16-127">Inicie o Retail Modern POS ou o Cloud POS e entre.</span><span class="sxs-lookup"><span data-stu-id="9ff16-127">Start Retail Modern POS or Cloud POS, and sign in.</span></span>
2. <span data-ttu-id="9ff16-128">Na página **Configurações**, na seção **Gravador de Tarefas**, clique em **Abrir gravador de tarefas**.</span><span class="sxs-lookup"><span data-stu-id="9ff16-128">On the **Settings** page, in the **Task Recorder** section, click **Open task recorder**.</span></span> <span data-ttu-id="9ff16-129">O painel **Gravador de tarefas** aparecerá.</span><span class="sxs-lookup"><span data-stu-id="9ff16-129">The **Task recorder** pane appears.</span></span> <span data-ttu-id="9ff16-130">Você pode clicar no botão **Fechar** (**X**) no canto superior direito para fechar o painel **Gravador de tarefas** antes de iniciar uma nova gravação.</span><span class="sxs-lookup"><span data-stu-id="9ff16-130">You can click the **Close** button (**X**) in the upper-right corner to close the **Task recorder** pane before you begin a new recording.</span></span> <span data-ttu-id="9ff16-131">Para reabrir o painel, repita a etapa 2.</span><span class="sxs-lookup"><span data-stu-id="9ff16-131">To reopen the pane, repeat step 2.</span></span>

    <span data-ttu-id="9ff16-132">[![Painel do Gravador de tarefas](./media/newrecording-1024x450.jpg)](./media/newrecording.jpg)</span><span class="sxs-lookup"><span data-stu-id="9ff16-132">[![Task recorder pane](./media/newrecording-1024x450.jpg)](./media/newrecording.jpg)</span></span>

3. <span data-ttu-id="9ff16-133">Insira um nome e uma descrição para a gravação e então clique em **Iniciar**.</span><span class="sxs-lookup"><span data-stu-id="9ff16-133">Enter a name and description for the recording, and then click **Start**.</span></span> <span data-ttu-id="9ff16-134">A sessão de gravação começa assim que você clica em **Iniciar**.</span><span class="sxs-lookup"><span data-stu-id="9ff16-134">The recording session begins as soon as you click **Start**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="9ff16-135">Se você clicar no botão **Fechar** (**X**) no canto superior direito enquanto a gravação estiver em andamento, o painel **Gravador de tarefas** será fechado, mas a sessão de gravação não será encerrada.</span><span class="sxs-lookup"><span data-stu-id="9ff16-135">If you click the **Close** button (**X**) in the upper-right corner while recording is in progress, the **Task recorder** pane is closed, but the recording session isn't ended.</span></span> <span data-ttu-id="9ff16-136">Para reabrir o painel do Gravador de tarefas, clique no botão **Ajuda** (ponto de interrogação) na parte superior da tela.</span><span class="sxs-lookup"><span data-stu-id="9ff16-136">To reopen the Task recorder pane, click the **Help** button (question mark) at the top of the screen.</span></span>
    >
    > <span data-ttu-id="9ff16-137">[![Ponto de interrogação](./media/help.jpg)](./media/help.jpg)</span><span class="sxs-lookup"><span data-stu-id="9ff16-137">[![Question mark](./media/help.jpg)](./media/help.jpg)</span></span>

4. <span data-ttu-id="9ff16-138">Depois que você clicar em **Iniciar**, o Gravador de tarefas entrará no modo de gravação.</span><span class="sxs-lookup"><span data-stu-id="9ff16-138">After you click **Start**, Task recorder enters recording mode.</span></span> <span data-ttu-id="9ff16-139">O painel **Gravador de tarefas** mostra as informações e os controles relacionados ao processo de gravação.</span><span class="sxs-lookup"><span data-stu-id="9ff16-139">The **Task recorder** pane shows information and controls that are related to the recording process.</span></span>
5. <span data-ttu-id="9ff16-140">Execute as ações desejadas na IU (interface do usuário) do Retail Modern POS ou do Cloud POS.</span><span class="sxs-lookup"><span data-stu-id="9ff16-140">Perform the actions that you want to perform in the Retail Modern POS or Cloud POS user interface (UI).</span></span>
6. <span data-ttu-id="9ff16-141">Para encerrar a sessão de gravação, clique em **Parar**.</span><span class="sxs-lookup"><span data-stu-id="9ff16-141">To end the recording session, click **Stop**.</span></span>

## <a name="download-options"></a><span data-ttu-id="9ff16-142">Opções de download</span><span class="sxs-lookup"><span data-stu-id="9ff16-142">Download options</span></span>

<span data-ttu-id="9ff16-143">Após o encerramento da sessão de gravação, diversas opções são mostradas para que você possa baixar sua gravação.</span><span class="sxs-lookup"><span data-stu-id="9ff16-143">After you end the recording session, several options are shown, so that you can download your recording.</span></span>

<span data-ttu-id="9ff16-144">[![Opções de download](./media/downlaod-options.jpg)](./media/downlaod-options.jpg)</span><span class="sxs-lookup"><span data-stu-id="9ff16-144">[![Download options](./media/downlaod-options.jpg)](./media/downlaod-options.jpg)</span></span>

### <a name="save-to-this-pc"></a><span data-ttu-id="9ff16-145">Salvar neste computador</span><span class="sxs-lookup"><span data-stu-id="9ff16-145">Save to this PC</span></span>

<span data-ttu-id="9ff16-146">Você pode usar o pacote de gravação para reproduzir um Guia de tarefas, manter a gravação ou editar as anotações na gravação.</span><span class="sxs-lookup"><span data-stu-id="9ff16-146">You can use the recording package to play a Task guide, maintain the recording, or edit the annotations in the recording.</span></span> <span data-ttu-id="9ff16-147">(Esse recurso ainda não foi implementado no Retail Modern POS ou no Cloud POS).</span><span class="sxs-lookup"><span data-stu-id="9ff16-147">(This feature isn't yet implemented in Retail Modern POS and Cloud POS.)</span></span>

### <a name="export-as-word-document"></a><span data-ttu-id="9ff16-148">Exportar como documento do Word</span><span class="sxs-lookup"><span data-stu-id="9ff16-148">Export as Word document</span></span>

<span data-ttu-id="9ff16-149">Você pode salvar a gravação como um documento do Microsoft Word.</span><span class="sxs-lookup"><span data-stu-id="9ff16-149">You can save the recording as a Microsoft Word document.</span></span> <span data-ttu-id="9ff16-150">O documento conterá as etapas gravadas e as capturas de tela que foram feitas.</span><span class="sxs-lookup"><span data-stu-id="9ff16-150">The document will contain the recorded steps and the screenshots that were captured.</span></span>

### <a name="save-as-developer-recording"></a><span data-ttu-id="9ff16-151">Salvar como gravação do desenvolvedor</span><span class="sxs-lookup"><span data-stu-id="9ff16-151">Save as developer recording</span></span>

<span data-ttu-id="9ff16-152">O arquivo bruto de gravação será útil em cenários de desenvolvimento, como a geração de código de teste.</span><span class="sxs-lookup"><span data-stu-id="9ff16-152">The raw recording file will be useful for developer scenarios such as test code generation.</span></span> <span data-ttu-id="9ff16-153">(Esse recurso ainda não foi implementado).</span><span class="sxs-lookup"><span data-stu-id="9ff16-153">(This feature isn't yet implemented.)</span></span>

## <a name="recording-controls"></a><span data-ttu-id="9ff16-154">Controles de gravação</span><span class="sxs-lookup"><span data-stu-id="9ff16-154">Recording controls</span></span>

<span data-ttu-id="9ff16-155">[![Controles de gravação](./media/controls.jpg)](./media/controls.jpg)</span><span class="sxs-lookup"><span data-stu-id="9ff16-155">[![Recording controls](./media/controls.jpg)](./media/controls.jpg)</span></span>

### <a name="stop"></a><span data-ttu-id="9ff16-156">Parar</span><span class="sxs-lookup"><span data-stu-id="9ff16-156">Stop</span></span>

<span data-ttu-id="9ff16-157">Clique em **Parar** para encerrar a sessão de gravação.</span><span class="sxs-lookup"><span data-stu-id="9ff16-157">Click **Stop** to end the recording session.</span></span> <span data-ttu-id="9ff16-158">Observe que não é possível reiniciar uma sessão depois de encerrá-la.</span><span class="sxs-lookup"><span data-stu-id="9ff16-158">Note that you can't restart a session after you end it.</span></span> <span data-ttu-id="9ff16-159">Portanto, certifique-se de que a gravação esteja concluída antes de encerrá-la.</span><span class="sxs-lookup"><span data-stu-id="9ff16-159">Therefore, make sure that the recording is completed before you end it.</span></span>

### <a name="pause"></a><span data-ttu-id="9ff16-160">Pausa</span><span class="sxs-lookup"><span data-stu-id="9ff16-160">Pause</span></span>

<span data-ttu-id="9ff16-161">Clique em **Pausar** para parar temporariamente (pausa) a sessão de gravação e para continuar com a operação.</span><span class="sxs-lookup"><span data-stu-id="9ff16-161">Click **Pause** to temporarily stop (pause) the recording session and continue with the operation.</span></span> <span data-ttu-id="9ff16-162">As etapas realizadas depois que você clicar em **Pausar** não serão registradas.</span><span class="sxs-lookup"><span data-stu-id="9ff16-162">Steps that you perform after you click **Pause** aren't recorded.</span></span>

### <a name="continue"></a><span data-ttu-id="9ff16-163">Continuar</span><span class="sxs-lookup"><span data-stu-id="9ff16-163">Continue</span></span>

<span data-ttu-id="9ff16-164">Para retomar a sessão de gravação depois de pausá-la, clique em **Continuar**.</span><span class="sxs-lookup"><span data-stu-id="9ff16-164">To resume the recording session after you've paused it, click **Continue**.</span></span>

### <a name="capture-screenshots"></a><span data-ttu-id="9ff16-165">Capturar telas</span><span class="sxs-lookup"><span data-stu-id="9ff16-165">Capture screenshots</span></span>

<span data-ttu-id="9ff16-166">O Gravador de tarefas pode capturar telas da interface do usuário do Retail Modern POS à medida que você registra um processo de negócios.</span><span class="sxs-lookup"><span data-stu-id="9ff16-166">Task recorder can capture screenshots of the Retail Modern POS UI as you record a business process.</span></span> <span data-ttu-id="9ff16-167">Para ativar o recurso de captura de tela, defina a opção **Capturar tela** como **Sim** e, em seguida, faça a gravação.</span><span class="sxs-lookup"><span data-stu-id="9ff16-167">To turn on the screenshot capture feature, set the **Capture screenshot** option to **Yes** and then make the recording.</span></span> <span data-ttu-id="9ff16-168">Depois que o registro for concluído, clique em **Interromper** e baixar o documento do Word.</span><span class="sxs-lookup"><span data-stu-id="9ff16-168">Once the recording is completed, click **Stop** and download the Word document.</span></span> <span data-ttu-id="9ff16-169">O documento conterá as etapas a capturas de tela relevantes.</span><span class="sxs-lookup"><span data-stu-id="9ff16-169">The document will contain the steps with relevant screenshots.</span></span>

> [!NOTE]
> <span data-ttu-id="9ff16-170">A funcionalidade Capturar tela não tem suporte no Cloud POS.</span><span class="sxs-lookup"><span data-stu-id="9ff16-170">Capture screenshot functionality is not supported in Cloud POS.</span></span>

### <a name="start-task-and-end-task"></a><span data-ttu-id="9ff16-171">Iniciar tarefa e Finalizar tarefa</span><span class="sxs-lookup"><span data-stu-id="9ff16-171">Start task and End task</span></span>

<span data-ttu-id="9ff16-172">Você pode especificar o início e o final de um conjunto de etapas agrupadas usando os botões **Iniciar tarefa** e **Finalizar** **tarefa**.</span><span class="sxs-lookup"><span data-stu-id="9ff16-172">You can specify the beginning and end of a set of grouped steps by using the **Start task** and **End** **task** buttons.</span></span> <span data-ttu-id="9ff16-173">Clique em **Iniciar tarefa** para adicionar uma etapa "Iniciar Tarefa" e execute as etapas que devem ser incluídas no grupo.</span><span class="sxs-lookup"><span data-stu-id="9ff16-173">Click **Start task** to add a "Start Task" step, and then perform the steps that should be included in the group.</span></span> <span data-ttu-id="9ff16-174">Depois de concluir a execução das etapas para o grupo, clique em **Finalizar tarefa**.</span><span class="sxs-lookup"><span data-stu-id="9ff16-174">After you've finished performing the steps for the group, click **End task**.</span></span> <span data-ttu-id="9ff16-175">As tarefas ajudam você a organizar seus procedimentos.</span><span class="sxs-lookup"><span data-stu-id="9ff16-175">Tasks help you organize your procedures.</span></span> <span data-ttu-id="9ff16-176">As tarefas podem ser aninhadas em outras tarefas.</span><span class="sxs-lookup"><span data-stu-id="9ff16-176">Tasks can be nested within other tasks.</span></span> <span data-ttu-id="9ff16-177">Assim, você pode organizar melhor os processos de negócios muito longos e complexos.</span><span class="sxs-lookup"><span data-stu-id="9ff16-177">In this way, you can better organize very long and complex business processes.</span></span>

## <a name="adding-annotations"></a><span data-ttu-id="9ff16-178">Adição de anotações</span><span class="sxs-lookup"><span data-stu-id="9ff16-178">Adding annotations</span></span>

<span data-ttu-id="9ff16-179">Uma anotação é um outro texto adicionado a uma etapa em uma gravação.</span><span class="sxs-lookup"><span data-stu-id="9ff16-179">An annotation is additional text that you add to a step in a recording.</span></span> <span data-ttu-id="9ff16-180">Por exemplo, você pode usar as anotações para oferecer ao usuário mais contexto ou mais instruções.</span><span class="sxs-lookup"><span data-stu-id="9ff16-180">For example, you can use annotations to give the user more context or instructions.</span></span> <span data-ttu-id="9ff16-181">Você pode adicionar anotações antes ou depois de uma etapa.</span><span class="sxs-lookup"><span data-stu-id="9ff16-181">You can add annotations before or after a step.</span></span> <span data-ttu-id="9ff16-182">Você pode adicionar uma anotação a qualquer etapa clicando no botão **Editar** (símbolo de lápis) à direita de etapa.</span><span class="sxs-lookup"><span data-stu-id="9ff16-182">You can add an annotation to any step by clicking the **Edit** button (pencil symbol) to the right of the step.</span></span>

<span data-ttu-id="9ff16-183">[![Botão Editar de uma etapa](./media/annotate.jpg)](./media/annotate.jpg)</span><span class="sxs-lookup"><span data-stu-id="9ff16-183">[![Edit button for a step](./media/annotate.jpg)](./media/annotate.jpg)</span></span>

### <a name="texts-and-notes"></a><span data-ttu-id="9ff16-184">Textos e notas</span><span class="sxs-lookup"><span data-stu-id="9ff16-184">Texts and notes</span></span>

<span data-ttu-id="9ff16-185">Você pode usar os campos **Textos** e **Notas** para adicionar o texto que deve ser associado a uma etapa em uma Guia de tarefas.</span><span class="sxs-lookup"><span data-stu-id="9ff16-185">You can use the **Texts** and **Notes** fields to add text that should be associated with a step in a Task guide.</span></span>

<span data-ttu-id="9ff16-186">[![Campos Texto e Notas](./media/annotatesteps.jpg)](./media/annotatesteps.jpg)</span><span class="sxs-lookup"><span data-stu-id="9ff16-186">[![Text and Notes fields](./media/annotatesteps.jpg)](./media/annotatesteps.jpg)</span></span>

#### <a name="text"></a><span data-ttu-id="9ff16-187">Texto</span><span class="sxs-lookup"><span data-stu-id="9ff16-187">Text</span></span>

<span data-ttu-id="9ff16-188">O texto inserido no campo **Texto** aparece *acima* do texto da etapa no Guia de tarefas.</span><span class="sxs-lookup"><span data-stu-id="9ff16-188">Text that you enter in the **Text** field appears *above* the step text in the Task guide.</span></span> <span data-ttu-id="9ff16-189">Esta localização é apropriada para o texto que o usuário deve ler antes de concluir a etapa.</span><span class="sxs-lookup"><span data-stu-id="9ff16-189">This location is appropriate for text that you want the user to read before he or she completes the step.</span></span>

#### <a name="notes"></a><span data-ttu-id="9ff16-190">Observação</span><span class="sxs-lookup"><span data-stu-id="9ff16-190">Notes</span></span>

<span data-ttu-id="9ff16-191">O texto inserido no campo **Notas** aparece *abaixo* do texto da etapa no Guia de tarefas.</span><span class="sxs-lookup"><span data-stu-id="9ff16-191">Text that you enter in the **Notes** field appears *below* the step text in the Task guide.</span></span> <span data-ttu-id="9ff16-192">Para ler o texto da nota, o usuário deverá expandir o texto da etapa na janela pop-up.</span><span class="sxs-lookup"><span data-stu-id="9ff16-192">To read the note text, the user must expand the step text in the pop-up window.</span></span> <span data-ttu-id="9ff16-193">Essa localização é apropriada para o material de leitura opcional ou para outras informações que possam ser úteis para o usuário, mas que não são obrigatórias para a conclusão da ação.</span><span class="sxs-lookup"><span data-stu-id="9ff16-193">This location is appropriate for optional reading material or other information that might be useful to the user, but that the user doesn't require in order to complete the action.</span></span>

## <a name="help-in-retail-modern-pos-and-cloud-pos"></a><span data-ttu-id="9ff16-194">Ajuda do Retail Modern POS e do Cloud POS</span><span class="sxs-lookup"><span data-stu-id="9ff16-194">Help in Retail Modern POS and Cloud POS</span></span>

<span data-ttu-id="9ff16-195">Para mostrar suas próprias gravações de tarefas personalizadas no painel da Ajuda do Retail Modern POS e do Cloud BPM para que possam ser executadas novamente como guias de tarefas ou exibidas como texto, você deverá salvar suas gravações de tarefas em sua própria biblioteca do BPM, e então atualizar os parâmetros do seu sistema de ajuda para que ele aponte para sua biblioteca do BPM.</span><span class="sxs-lookup"><span data-stu-id="9ff16-195">To show your own custom task recordings in the Help pane of Retail Modern POS and Cloud POS so that they can be viewed as text, you must save your task recordings to your own BPM library, and then update your Help system parameters to point to your BPM library.</span></span> <span data-ttu-id="9ff16-196">Para obter mais informações, consulte [Conectando o sistema de ajuda.](../fin-and-ops/get-started/help-connect.md)</span><span class="sxs-lookup"><span data-stu-id="9ff16-196">For more information, see [Connecting the Help system](../fin-and-ops/get-started/help-connect.md).</span></span> <span data-ttu-id="9ff16-197">A Ajuda do Retail Modern POS e do Cloud POS pesquisa o LCS em tempo real.</span><span class="sxs-lookup"><span data-stu-id="9ff16-197">Retail Modern POS and Cloud POS Help searches LCS in real time.</span></span> <span data-ttu-id="9ff16-198">Ela pesquisa em todas as bibliotecas BPM selecionadas nos parâmetros do sistema da Ajuda do Commerce e mostra os resultados relevantes.</span><span class="sxs-lookup"><span data-stu-id="9ff16-198">It searches across all the BPM libraries that are selected in the Commerce Help system parameters and shows the relevant results.</span></span> <span data-ttu-id="9ff16-199">Para acessar o menu **Ajuda**, clique no botão **Ajuda** (ponto de interrogação) na parte superior da tela e, na caixa de pesquisa, digite o nome do processo e pressione o botão de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="9ff16-199">To access the **Help** menu, click the **Help** button (question mark) at the top of the screen and then in the search box type your process name and hit the search button.</span></span>

<span data-ttu-id="9ff16-200">[![Botão Ajuda](./media/help.jpg)](./media/help.jpg)</span><span class="sxs-lookup"><span data-stu-id="9ff16-200">[![Help button](./media/help.jpg)](./media/help.jpg)</span></span>

<span data-ttu-id="9ff16-201">Quando você clicar em uma Guia de tarefas nos resultados da pesquisa, poderá exibir as etapas como um tópico da Ajuda ou exportar as etapas para um documento do Word.</span><span class="sxs-lookup"><span data-stu-id="9ff16-201">When you click a Task guide in the search results, you can either view the steps as a Help topic or export the steps to a Word document.</span></span>

> [!NOTE]
> <span data-ttu-id="9ff16-202">A ajuda no Retail Modern POS e Cloud POS não exibirá guias de tarefas de acordo com o formulário em que você está ou a operação que está fazendo.</span><span class="sxs-lookup"><span data-stu-id="9ff16-202">Help in Retail Modern POS and Cloud POS will not bring up task guides according to what form you're on or operation you're doing.</span></span> <span data-ttu-id="9ff16-203">É necessário digitar o nome do processo na caixa de pesquisa e clique em **Pesquisar**.</span><span class="sxs-lookup"><span data-stu-id="9ff16-203">You have to type the process name in the search box and then click **Search**.</span></span>