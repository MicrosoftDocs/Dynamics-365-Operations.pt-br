---
title: Mensagens do processador de mensagens
description: Este tópico fornece informações sobre o recurso Mensagens do processador de mensagens para cargas de trabalho da unidade de escala.
author: perlynne
ms.date: 04/22/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SysMessageProcessorMessage, BusinessEventsWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: SCM
ms.author: perlynne
ms.search.validFrom: 2021-04-21
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 03d8cad743ac2b2b1e7b2832b8272ca3dbf5a163
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2021
ms.locfileid: "6021046"
---
# <a name="message-processor-messages"></a><span data-ttu-id="09aa6-103">Mensagens do processador de mensagens</span><span class="sxs-lookup"><span data-stu-id="09aa6-103">Message processor messages</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

<span data-ttu-id="09aa6-104">As mensagens do processador de mensagens são usadas na execução de unidades de escala de nuvem e de borda para [cargas de trabalho de fabricação](cloud-edge-workload-manufacturing.md) e [cargas de trabalho de gerenciamento de depósito](cloud-edge-workload-warehousing.md).</span><span class="sxs-lookup"><span data-stu-id="09aa6-104">Message processor messages are used when running cloud and edge scale units for [manufacturing workloads](cloud-edge-workload-manufacturing.md) and [warehouse management workloads](cloud-edge-workload-warehousing.md).</span></span>

<span data-ttu-id="09aa6-105">Uma grande quantidade de dados é trocada entre os ambientes de implantação de unidade de escala e de hub para mantê-los em sincronia, mas somente algumas dessas trocas de dados serão processadas pelo *processador de mensagens*.</span><span class="sxs-lookup"><span data-stu-id="09aa6-105">A large amount of data is exchanged between the hub and scale unit deployment environments to keep them in sync, but only a few of these data exchanges will be processed by the *message processor*.</span></span> <span data-ttu-id="09aa6-106">Você pode exibir as mensagens processadas pelo processador de mensagens indo para **Administração do sistema > Processador de mensagens > Mensagens do processador de mensagens**.</span><span class="sxs-lookup"><span data-stu-id="09aa6-106">You can view the messages processed by the message processor by going to **System administration > Message processor > Message processor messages**.</span></span>

## <a name="message-grid-columns-and-filters"></a><span data-ttu-id="09aa6-107">Colunas e filtros da grade de mensagens</span><span class="sxs-lookup"><span data-stu-id="09aa6-107">Message grid columns and filters</span></span>

<span data-ttu-id="09aa6-108">Você pode usar os campos na parte superior da página **Mensagens do processador de mensagens** para ajudar a encontrar mensagens específicas que você está procurando.</span><span class="sxs-lookup"><span data-stu-id="09aa6-108">You can use the fields at the top of the **Message processor messages** page to help find any particular messages you are looking for.</span></span> <span data-ttu-id="09aa6-109">A maioria desses filtros corresponde aos cabeçalhos de coluna na grade de mensagens.</span><span class="sxs-lookup"><span data-stu-id="09aa6-109">Most of these filters match the column headings in the message grid.</span></span> <span data-ttu-id="09aa6-110">Os seguintes filtros e cabeçalhos de coluna estão disponíveis:</span><span class="sxs-lookup"><span data-stu-id="09aa6-110">The following filters and column headings are available:</span></span>

- <span data-ttu-id="09aa6-111">**Tipo de mensagem** – Especifica o tipo de mensagem.</span><span class="sxs-lookup"><span data-stu-id="09aa6-111">**Message type** – Specifies the type of message.</span></span>
- <span data-ttu-id="09aa6-112">**Fila de mensagens** – especifica o nome da fila na qual a mensagem será processada.</span><span class="sxs-lookup"><span data-stu-id="09aa6-112">**Message queue** – Specifies the name of the queue in which the message is to be processed.</span></span> <span data-ttu-id="09aa6-113">As seguintes filas são fornecidas:</span><span class="sxs-lookup"><span data-stu-id="09aa6-113">The following queues are provided:</span></span>
  - <span data-ttu-id="09aa6-114">*Unidade de escala para hub*</span><span class="sxs-lookup"><span data-stu-id="09aa6-114">*Scale unit to hub*</span></span>
  - <span data-ttu-id="09aa6-115">*Hub para unidade de escala da execução de depósito*</span><span class="sxs-lookup"><span data-stu-id="09aa6-115">*Hub to warehouse execution scale unit*</span></span>
  - <span data-ttu-id="09aa6-116">*Hub para unidade de escala da execução de fabricação*</span><span class="sxs-lookup"><span data-stu-id="09aa6-116">*Hub to manufacturing execution scale unit*</span></span>
- <span data-ttu-id="09aa6-117">**Estado da mensagem** – especifica o estado da mensagem.</span><span class="sxs-lookup"><span data-stu-id="09aa6-117">**Message state** – Specifies the state of the message.</span></span> <span data-ttu-id="09aa6-118">Há os seguintes status:</span><span class="sxs-lookup"><span data-stu-id="09aa6-118">The following states exists:</span></span>
  - <span data-ttu-id="09aa6-119">*Enfileirado* – a mensagem está pronta para ser processada pelo processador de mensagens.</span><span class="sxs-lookup"><span data-stu-id="09aa6-119">*Queued* – The message is ready to be processed by the message processor.</span></span>
  - <span data-ttu-id="09aa6-120">*Processado* – a mensagem foi processada com sucesso pelo processador de mensagens.</span><span class="sxs-lookup"><span data-stu-id="09aa6-120">*Processed* – The message was successfully processed by the message processor.</span></span>
  - <span data-ttu-id="09aa6-121">*Cancelado* – a mensagem foi processada, mas o processamento falhou.</span><span class="sxs-lookup"><span data-stu-id="09aa6-121">*Canceled* – The message was processed, but processing failed.</span></span>
- <span data-ttu-id="09aa6-122">**Conteúdo da mensagem** – este filtro faz uma pesquisa de texto completo do conteúdo da mensagem.</span><span class="sxs-lookup"><span data-stu-id="09aa6-122">**Message content** – This filter does a full-text search of message content.</span></span> <span data-ttu-id="09aa6-123">(O conteúdo da mensagem não é mostrado na grade). O filtro trata a maioria dos símbolos especiais (como "-") como espaços e trata todos os caracteres de espaço como operadores booliano OU.</span><span class="sxs-lookup"><span data-stu-id="09aa6-123">(Message content is not shown in the grid.) The filter treats most special symbols (such as "-") as spaces, and treats all space characters as Boolean OR operators.</span></span> <span data-ttu-id="09aa6-124">T = por exemplo, isso significa que, se você procurar um valor `journalid` específico igual a "USMF-123456", o sistema encontrará todas as mensagens que contêm "USMF" ou "123456", que provavelmente será uma lista longa.</span><span class="sxs-lookup"><span data-stu-id="09aa6-124">T=For example, this means if you search for a specific `journalid` value equal "USMF-123456", the system will find all messages that contain "USMF" or "123456", which is likely to be a long list.</span></span> <span data-ttu-id="09aa6-125">Portanto, seria melhor inserir apenas "123456", pois isso retornará resultados mais específicos.</span><span class="sxs-lookup"><span data-stu-id="09aa6-125">Therefore, it would be better to enter just "123456" alone because that will return more specific results.</span></span>

## <a name="example-message-type-request-inventory-adjustment-financial-update"></a><span data-ttu-id="09aa6-126">Exemplo de tipo de mensagem: solicitação de atualização financeira de ajuste de estoque</span><span class="sxs-lookup"><span data-stu-id="09aa6-126">Example message type: Request inventory adjustment financial update</span></span>

<span data-ttu-id="09aa6-127">Por exemplo, a *Atualização financeira de ajuste de estoque de solicitação* do **Tipo de mensagem** é usada para criar e lançar um diário de contagem no Hub quando um trabalhador usa o aplicativo de depósito para [registrar um ajuste de estoque](cloud-edge-warehouse-inventory-adjustment.md) em uma carga de trabalho de gerenciamento de depósito da unidade de escala.</span><span class="sxs-lookup"><span data-stu-id="09aa6-127">For example, the **Message type** *Request inventory adjustment financial update* is used to create and post a counting journal on the hub when a worker uses the warehouse app to [register an inventory adjustment](cloud-edge-warehouse-inventory-adjustment.md) on a scale unit warehouse management workload.</span></span> <span data-ttu-id="09aa6-128">Como esse processo específico se origina de uma unidade de escala, o campo **Fila de mensagens** mostrará o valor *Unidade de escala ao Hub*.</span><span class="sxs-lookup"><span data-stu-id="09aa6-128">Because this specific process originates from a scale unit, the **Message queue** field will show the value *Scale unit to hub*.</span></span>

<span data-ttu-id="09aa6-129">Para esse tipo de mensagem, uma carga de trabalho da unidade de escala registra a mensagem como parte de uma operação de ajuste de estoque do aplicativo de depósito.</span><span class="sxs-lookup"><span data-stu-id="09aa6-129">For this message type, a scale unit workload records the message as part of a warehouse app inventory adjustment operation.</span></span> <span data-ttu-id="09aa6-130">Os dados da mensagem são então transferidos para o hub como parte do mesmo processo usado para a [Arquitetura do Commerce Data Exchange](../../commerce/commerce-architecture.md).</span><span class="sxs-lookup"><span data-stu-id="09aa6-130">The message data is then transferred to the hub as part of the same process used for the [Commerce data exchange architecture](../../commerce/commerce-architecture.md).</span></span> <span data-ttu-id="09aa6-131">A mensagem será atualizada para mostrar o **Estado da mensagem** como *Enfileirado*.</span><span class="sxs-lookup"><span data-stu-id="09aa6-131">The message will be updated to show **Message state** as *Queued*.</span></span> <span data-ttu-id="09aa6-132">Em seguida, o processador de mensagens tenta processar a mensagem e atualiza o **Estado da mensagem** para que seja *Processado* com êxito ou *Cancelado* em caso de falha.</span><span class="sxs-lookup"><span data-stu-id="09aa6-132">The message processor then attempts to process the message and updates the **Message state** to *Processed* on success, or *Canceled* on failure.</span></span>

## <a name="view-the-message-log-message-content-and-details"></a><span data-ttu-id="09aa6-133">Exibir o log de mensagens, o conteúdo da mensagem e os detalhes</span><span class="sxs-lookup"><span data-stu-id="09aa6-133">View the message log, message content, and details</span></span>

<span data-ttu-id="09aa6-134">Você pode encontrar informações detalhadas sobre uma mensagem, selecionando-a na grade e, em seguida, abrindo as guias **Log** ou **Conteúdo da mensagem** na grade da mensagem, na qual cada evento de processamento é mostrado.</span><span class="sxs-lookup"><span data-stu-id="09aa6-134">You can find detailed information about a message by selecting it in the grid and then opening the **Log** or **Message content** tabs under the message grid, where each processing event is shown.</span></span>

<span data-ttu-id="09aa6-135">O **Conteúdo da mensagem** depende do **Tipo de mensagem** e, portanto, terá um tamanho de texto diferente.</span><span class="sxs-lookup"><span data-stu-id="09aa6-135">The **Message content** depends on the **Message type** and will therefore have different text length.</span></span> <span data-ttu-id="09aa6-136">Um texto de conteúdo de mensagem típico começa com um **{** e termina com um **}** e entre os nomes de campo, como `journalId` seguidos por um **:** e um valor como *USMF-123456*.</span><span class="sxs-lookup"><span data-stu-id="09aa6-136">A typical message content text will start with a **{** and end with a **}** and in between have field names such as `journalId` followed by a **:** and a value such as *USMF-123456*.</span></span>

<span data-ttu-id="09aa6-137">A barra de ferramentas na guia **Log** tem os seguintes botões:</span><span class="sxs-lookup"><span data-stu-id="09aa6-137">The toolbar on the **Log** tab includes the following buttons:</span></span>

- <span data-ttu-id="09aa6-138">**Log** – exibe os resultados do processamento.</span><span class="sxs-lookup"><span data-stu-id="09aa6-138">**Log** – Displays the processing results.</span></span> <span data-ttu-id="09aa6-139">Isso é especialmente útil para compreender os motivos de uma falha de processamento para as mensagens terem um **Resultado de processamento** *Com falha*.</span><span class="sxs-lookup"><span data-stu-id="09aa6-139">This is especially helpful for understanding the reasons for a processing failure for messages having a **Processing result** of *Failed*.</span></span>
- <span data-ttu-id="09aa6-140">**Pacote** – as operações de processamento de várias mensagens podem ser executadas como parte do mesmo processo em lote.</span><span class="sxs-lookup"><span data-stu-id="09aa6-140">**Bundle** – Multiple message processing operations can run as part of the same batch process.</span></span> <span data-ttu-id="09aa6-141">Selecione este botão para exibir os dados detalhados.</span><span class="sxs-lookup"><span data-stu-id="09aa6-141">Select this button to view this detailed data.</span></span> <span data-ttu-id="09aa6-142">Por exemplo, você pode ver se existem dependências que exigem que o sistema processe certas mensagens em uma sequência específica.</span><span class="sxs-lookup"><span data-stu-id="09aa6-142">For example, you can see whether dependencies exist that require the system to process certain messages in a specific sequence.</span></span>

## <a name="message-processor-batch-job"></a><span data-ttu-id="09aa6-143">Trabalho em lotes do processador de mensagens</span><span class="sxs-lookup"><span data-stu-id="09aa6-143">Message processor batch job</span></span>

<span data-ttu-id="09aa6-144">Ao executar uma implantação de nuvem e de borda, o trabalho em lotes *Processador de mensagens* será automaticamente revogado quando uma nova mensagem for criada para processamento, de forma que você não precisará agendar esse trabalho manualmente.</span><span class="sxs-lookup"><span data-stu-id="09aa6-144">When running a cloud and edge deployment, the *Message processor* batch job will automatically be evoked when a new message is created for processing, so you should not need to schedule this job manually.</span></span>

<span data-ttu-id="09aa6-145">Se necessário, você pode acessar o trabalho em lotes indo para **Administração do sistema > Processador de mensagens > Processador de mensagens**.</span><span class="sxs-lookup"><span data-stu-id="09aa6-145">If necessary, you can access the batch job by going to **System administration > Message  processor > Message processor**.</span></span>

## <a name="manually-process-or-cancel-a-message"></a><span data-ttu-id="09aa6-146">Processar ou cancelar manualmente uma mensagem</span><span class="sxs-lookup"><span data-stu-id="09aa6-146">Manually process or cancel a message</span></span>

<span data-ttu-id="09aa6-147">Se necessário, você pode processar ou cancelar manualmente uma mensagem, dependendo do seu estado atual.</span><span class="sxs-lookup"><span data-stu-id="09aa6-147">If needed, you can manually process or cancel a message, depending on its current state.</span></span> <span data-ttu-id="09aa6-148">Para fazer isso, selecione a mensagem na grade e, em seguida, selecione **Processar** ou **Cancelar** no Painel de Ações</span><span class="sxs-lookup"><span data-stu-id="09aa6-148">To do so, select the message in the grid and then select **Process** or **Cancel** on the Action Pane</span></span>

## <a name="set-up-business-events-to-deliver-alerts-for-failed-processing-results"></a><span data-ttu-id="09aa6-149">Configurar eventos de negócios para enviar alertas para resultados de processamento com falha</span><span class="sxs-lookup"><span data-stu-id="09aa6-149">Set up business events to deliver alerts for failed processing results</span></span>

<span data-ttu-id="09aa6-150">Além de filtrar no valor do **Estado da mensagem** *Cancelado* para pesquisar mensagens com falha, você pode configurar [Eventos de negócios](../../fin-ops-core/dev-itpro/business-events/home-page.md) no hub para alertá-lo sobre resultados de processamento com falha.</span><span class="sxs-lookup"><span data-stu-id="09aa6-150">In addition to filtering on the **Message state** value *Canceled* to inquire for failed messages, you can set up [Business events](../../fin-ops-core/dev-itpro/business-events/home-page.md) on the hub to alert you to failed processing results.</span></span> <span data-ttu-id="09aa6-151">Para fazer isso, ative o evento de negócios chamado *Mensagem do processador de mensagens processada*  na página **Catálogo dos eventos de negócios** (**Administração do sistema > Configuração > Eventos de negócios > Catálogo de eventos de negócios**).</span><span class="sxs-lookup"><span data-stu-id="09aa6-151">To do so, activate the business event named *Message processor message processed*  on the **Business events catalog** page (**System administration > Setup > Business events > Business events catalog**).</span></span>

<span data-ttu-id="09aa6-152">Como parte do processo de ativação, você será guiado para especificar se o evento é específico a uma ou todas as entidades legais e fornecer um **Nome de ponto de extremidade**, que deve ser definido primeiro.</span><span class="sxs-lookup"><span data-stu-id="09aa6-152">As part of the activation process, you will be guided to specify whether the event is specific to one or all legal entities and provide an **Endpoint name**, which must be defined first.</span></span>

>[!NOTE]
> <span data-ttu-id="09aa6-153">Se **Quando um evento de negócios ocorre** for definido como *Microsoft Power Automate* (em vez de *HTTPS*, por exemplo), o **Nome do ponto de extremidade** será criado automaticamente no Supply Chain Management com base na configuração do *Microsoft Power Automate*.</span><span class="sxs-lookup"><span data-stu-id="09aa6-153">If **When a Business Event occurs** is set to *Microsoft Power Automate* (rather than *HTTPS*, for example), the **Endpoint name** will automatically be created in Supply Chain Management based on the *Microsoft Power Automate* setup.</span></span>

### <a name="microsoft-power-automate-example"></a><span data-ttu-id="09aa6-154">Exemplo do Microsoft Power Automate</span><span class="sxs-lookup"><span data-stu-id="09aa6-154">Microsoft Power Automate example</span></span>

<span data-ttu-id="09aa6-155">Neste exemplo, usar **Quando um evento de negócios ocorre** com *Microsoft Power Automate* envia emails contendo mensagens InfoLog e hiperlinks para abrir a página **Mensagens do processador de mensagens** para uma mensagem de falha específica na implantação do hub.</span><span class="sxs-lookup"><span data-stu-id="09aa6-155">In this example, use **When a Business Event occurs** with *Microsoft Power Automate* sends emails containing InfoLog messages and hyperlinks to open the **Message processor messages** page for a specific failed message on the hub deployment.</span></span> <span data-ttu-id="09aa6-156">Se necessário, você pode adicionar lógica extra para enviar as notificações em paralelo usando diferentes canais e controlar os destinatários com base nos dados do evento.</span><span class="sxs-lookup"><span data-stu-id="09aa6-156">If needed, you can add extra logic to send the notifications in parallel using different channels and control the recipients based on the event data.</span></span>

1. <span data-ttu-id="09aa6-157">No [Power Automate](https://preview.flow.microsoft.com), crie um novo fluxo de nuvem automatizado para o gatilho de fluxo **Quando um evento de negócios ocorre - Aplicativo Finance and Operations (Dynamics 365)** seguido pelas etapas **Analisar JSON** e **Enviar um email**, conforme mostrado na ilustração a seguir.</span><span class="sxs-lookup"><span data-stu-id="09aa6-157">In [Power Automate](https://preview.flow.microsoft.com), create a new automated cloud flow for the flow trigger **When a Business Event occurs - Fin & Ops App (Dynamics 365)** followed by the **Parse JSON** and **Send an email** steps, as shown in the following illustration.</span></span>

    :::image type="content" source="./media/cloud-edge-power-automate-example1.png" alt-text="Fluxo de nuvem automatizado do Power Automate":::

1. <span data-ttu-id="09aa6-159">Na etapa **Quando um Evento de Negócios ocorre**, você pode pesquisar ou inserir a **Instância** do hub após a **Categoria** e, em seguida, o **Evento de negócios** *Mensagem do processador de mensagens processada*, conforme mostrado na seguinte ilustração.</span><span class="sxs-lookup"><span data-stu-id="09aa6-159">In the **When a Business Event occurs** step, you can look up or enter the hub **Instance** following the **Category** and then the **Business event** *Message processor message processed*, as shown in the following illustration.</span></span>

    :::image type="content" source="./media/cloud-edge-power-automate-example2.png" alt-text="Power Automate Etapa Quando um Evento de Negócios ocorre":::

1. <span data-ttu-id="09aa6-161">Para a etapa **Analisar JSON**, insira um **Esquema** que define os campos estendidos.</span><span class="sxs-lookup"><span data-stu-id="09aa6-161">For the **Parse JSON** step, enter a **Schema** that defines the extended fields.</span></span> <span data-ttu-id="09aa6-162">Você pode usar a opção *Baixar esquema* na página **Catálogo de eventos de negócios** no Supply Chain Management ou começar colando o texto do esquema de exemplo.</span><span class="sxs-lookup"><span data-stu-id="09aa6-162">You can use the *Download schema* option on the **Business events catalog** page in Supply Chain Management or start by pasting in the example schema text.</span></span> <span data-ttu-id="09aa6-163">Este texto de exemplo é fornecido após a ilustração a seguir.</span><span class="sxs-lookup"><span data-stu-id="09aa6-163">This example text is provided after the following illustration.</span></span>

    :::image type="content" source="./media/cloud-edge-power-automate-example3.png" alt-text="Power Automate Analisar etapa JSON":::

    ```json
    {
        "properties": {
            "BusinessEventId": {
                "type": "string"
            },
            "ControlNumber": {
                "type": "integer"
            },
            "EventId": {
                "type": "string"
            },
            "EventTime": {
                "type": "string"
            },
            "MajorVersion": {
                "type": "integer"
            },
            "MessageContent": {
                "type": "string"
            },
            "MessageDestinationCompanyId": {
                "type": "string"
            },
            "MessageDestinationOperationalSiteId": {
                "type": "string"
            },
            "MessageDestinationWarehouseId": {
                "type": "string"
            },
            "MessageDestinationWorkloadName": {
                "type": "string"
            },
            "MessageInfolog": {
                "type": "string"
            },
            "MessageProcessingResult": {
                "type": "string"
            },
            "MessageProcessingResultLabel": {
                "type": "string"
            },
            "MessageProcessorMessagePageUrl": {
                "type": "string"
            },
            "MessageQueue": {
                "type": "string"
            },
            "MessageQueueLabel": {
                "type": "string"
            },
            "MessageSourceCompanyId": {
                "type": "string"
            },
            "MessageSourceOperationalSiteId": {
                "type": "string"
            },
            "MessageSourceWarehouseId": {
                "type": "string"
            },
            "MessageSourceWorkloadName": {
                "type": "string"
            },
            "MessageState": {
                "type": "string"
            },
            "MessageStateLabel": {
                "type": "string"
            },
            "MessageType": {
                "type": "string"
            },
            "MessageTypeLabel": {
                "type": "string"
            },
            "MinorVersion": {
                "type": "integer"
            }
        },
        "type": "object"
    }
    ```

1. <span data-ttu-id="09aa6-165">Na etapa **Enviar um email** você pode selecionar os campos individuais ou começar colando o exemplo de corpo de email no campo **Corpo**.</span><span class="sxs-lookup"><span data-stu-id="09aa6-165">In the **Send an email** step, you can select the individual fields or start by pasting the email body example into the **Body** field.</span></span> <span data-ttu-id="09aa6-166">Este exemplo é fornecido após a ilustração a seguir.</span><span class="sxs-lookup"><span data-stu-id="09aa6-166">This example is provided after the following illustration.</span></span>

    :::image type="content" source="./media/cloud-edge-power-automate-example4.png" alt-text="Power Automate Enviar uma mensagem de email":::

    ```plaintext
    Message queue: @{body('Parse_JSON')?['MessageQueue']}
    Message queue label: @{body('Parse_JSON')?['MessageQueueLabel']}
    Message type: @{body('Parse_JSON')?['MessageQueueType']}
    Message type label: @{body('Parse_JSON')?['MessageQueueTypeLabel']}
    Message content: @{body('Parse_JSON')?['MessageContent']}
    Message state: @{body('Parse_JSON')?['MessageState']}
    Message state label: @{body('Parse_JSON')?['MessageStateLabel']}
    Message processing result: @{body('Parse_JSON')?['MessageProcessingResult']}
    Message processing result label: @{body('Parse_JSON')?['MessageProcessingResultLabel']}
    Message infolog: @{body('Parse_JSON')?['MessageInfolog']}
    Message source company ID: @{body('Parse_JSON')?['MessageSourceCompanyId']}
    Message source workload name: @{body('Parse_JSON')?['MessageSourceWorkloadName']}
    Message source site ID: @{body('Parse_JSON')?['MessageSourceOperationalSiteId']}
    Message source warehouse ID: @{body('Parse_JSON')?['MessageSourceWarehouseId']}
    Message destination company ID: @{body('Parse_JSON')?['MessageDestinationCompanyId']}
    Message destination workload name: @{body('Parse_JSON')?['MessageDestinationWorkloadName']}
    Message destination site ID: @{body('Parse_JSON')?['MessageDestinationOperationalSiteId']}
    Message destination warehouse ID: @{body('Parse_JSON')?['MessageDestinationWarehouseId']}
    Message processor message page URL: @{body('Parse_JSON')?['MessageProcessorMessagePageUrl']}
    ```

1. <span data-ttu-id="09aa6-168">Quando você salvar o evento de negócios, ele será automaticamente ativado e pronto para ser usado como parte do Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="09aa6-168">When you save the business event, it will automatically be activated and ready to use as part of Supply Chain Management.</span></span>
