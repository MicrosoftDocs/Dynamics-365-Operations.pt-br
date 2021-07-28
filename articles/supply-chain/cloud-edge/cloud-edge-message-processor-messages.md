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
ms.openlocfilehash: 35fd48ef300d46d00c07f3231d780d1ba431d8ef
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/06/2021
ms.locfileid: "6350561"
---
# <a name="message-processor-messages"></a>Mensagens do processador de mensagens

[!include [banner](../includes/banner.md)]

As mensagens do processador de mensagens são usadas na execução de unidades de escala de nuvem e de borda para [cargas de trabalho de fabricação](cloud-edge-workload-manufacturing.md) e [cargas de trabalho de gerenciamento de depósito](cloud-edge-workload-warehousing.md).

Uma grande quantidade de dados é trocada entre os ambientes de implantação de unidade de escala e de hub para mantê-los em sincronia, mas somente algumas dessas trocas de dados serão processadas pelo *processador de mensagens*. Você pode exibir as mensagens processadas pelo processador de mensagens indo para **Administração do sistema > Processador de mensagens > Mensagens do processador de mensagens**.

## <a name="message-grid-columns-and-filters"></a>Colunas e filtros da grade de mensagens

Você pode usar os campos na parte superior da página **Mensagens do processador de mensagens** para ajudar a encontrar mensagens específicas que você está procurando. A maioria desses filtros corresponde aos cabeçalhos de coluna na grade de mensagens. Os seguintes filtros e cabeçalhos de coluna estão disponíveis:

- **Tipo de mensagem** – Especifica o tipo de mensagem.
- **Fila de mensagens** – especifica o nome da fila na qual a mensagem será processada. As seguintes filas são fornecidas:
  - *Unidade de escala para hub*
  - *Hub para unidade de escala da execução de depósito*
  - *Hub para unidade de escala da execução de fabricação*
- **Estado da mensagem** – especifica o estado da mensagem. Há os seguintes status:
  - *Enfileirado* – a mensagem está pronta para ser processada pelo processador de mensagens.
  - *Processado* – a mensagem foi processada com sucesso pelo processador de mensagens.
  - *Cancelado* – a mensagem foi processada, mas o processamento falhou.
- **Conteúdo da mensagem** – este filtro faz uma pesquisa de texto completo do conteúdo da mensagem. (O conteúdo da mensagem não é mostrado na grade). O filtro trata a maioria dos símbolos especiais (como "-") como espaços e trata todos os caracteres de espaço como operadores booliano OU. T = por exemplo, isso significa que, se você procurar um valor `journalid` específico igual a "USMF-123456", o sistema encontrará todas as mensagens que contêm "USMF" ou "123456", que provavelmente será uma lista longa. Portanto, seria melhor inserir apenas "123456", pois isso retornará resultados mais específicos.

## <a name="example-message-type-request-inventory-adjustment-financial-update"></a>Exemplo de tipo de mensagem: solicitação de atualização financeira de ajuste de estoque

Por exemplo, a *Atualização financeira de ajuste de estoque de solicitação* do **Tipo de mensagem** é usada para criar e lançar um diário de contagem no Hub quando um trabalhador usa o aplicativo de depósito para [registrar um ajuste de estoque](cloud-edge-warehouse-inventory-adjustment.md) em uma carga de trabalho de gerenciamento de depósito da unidade de escala. Como esse processo específico se origina de uma unidade de escala, o campo **Fila de mensagens** mostrará o valor *Unidade de escala ao Hub*.

Para esse tipo de mensagem, uma carga de trabalho da unidade de escala registra a mensagem como parte de uma operação de ajuste de estoque do aplicativo de depósito. Os dados da mensagem são então transferidos para o hub como parte do mesmo processo usado para a [Arquitetura do Commerce Data Exchange](../../commerce/commerce-architecture.md). A mensagem será atualizada para mostrar o **Estado da mensagem** como *Enfileirado*. Em seguida, o processador de mensagens tenta processar a mensagem e atualiza o **Estado da mensagem** para que seja *Processado* com êxito ou *Cancelado* em caso de falha.

## <a name="view-the-message-log-message-content-and-details"></a>Exibir o log de mensagens, o conteúdo da mensagem e os detalhes

Você pode encontrar informações detalhadas sobre uma mensagem, selecionando-a na grade e, em seguida, abrindo as guias **Log** ou **Conteúdo da mensagem** na grade da mensagem, na qual cada evento de processamento é mostrado.

O **Conteúdo da mensagem** depende do **Tipo de mensagem** e, portanto, terá um tamanho de texto diferente. Um texto de conteúdo de mensagem típico começa com um **{** e termina com um **}** e entre os nomes de campo, como `journalId` seguidos por um **:** e um valor como *USMF-123456*.

A barra de ferramentas na guia **Log** tem os seguintes botões:

- **Log** – exibe os resultados do processamento. Isso é especialmente útil para compreender os motivos de uma falha de processamento para as mensagens terem um **Resultado de processamento** *Com falha*.
- **Pacote** – as operações de processamento de várias mensagens podem ser executadas como parte do mesmo processo em lote. Selecione este botão para exibir os dados detalhados. Por exemplo, você pode ver se existem dependências que exigem que o sistema processe certas mensagens em uma sequência específica.

## <a name="message-processor-batch-job"></a>Trabalho em lotes do processador de mensagens

Ao executar uma implantação de nuvem e de borda, o trabalho em lotes *Processador de mensagens* será automaticamente revogado quando uma nova mensagem for criada para processamento, de forma que você não precisará agendar esse trabalho manualmente.

Se necessário, você pode acessar o trabalho em lotes indo para **Administração do sistema > Processador de mensagens > Processador de mensagens**.

## <a name="manually-process-or-cancel-a-message"></a>Processar ou cancelar manualmente uma mensagem

Se necessário, você pode processar ou cancelar manualmente uma mensagem, dependendo do seu estado atual. Para fazer isso, selecione a mensagem na grade e, em seguida, selecione **Processar** ou **Cancelar** no Painel de Ações

## <a name="set-up-business-events-to-deliver-alerts-for-failed-processing-results"></a>Configurar eventos de negócios para enviar alertas para resultados de processamento com falha

Além de filtrar no valor do **Estado da mensagem** *Cancelado* para pesquisar mensagens com falha, você pode configurar [Eventos de negócios](../../fin-ops-core/dev-itpro/business-events/home-page.md) no hub para alertá-lo sobre resultados de processamento com falha. Para fazer isso, ative o evento de negócios chamado *Mensagem do processador de mensagens processada*  na página **Catálogo dos eventos de negócios** (**Administração do sistema > Configuração > Eventos de negócios > Catálogo de eventos de negócios**).

Como parte do processo de ativação, você será guiado para especificar se o evento é específico a uma ou todas as entidades legais e fornecer um **Nome de ponto de extremidade**, que deve ser definido primeiro.

>[!NOTE]
> Se **Quando um evento de negócios ocorre** for definido como *Microsoft Power Automate* (em vez de *HTTPS*, por exemplo), o **Nome do ponto de extremidade** será criado automaticamente no Supply Chain Management com base na configuração do *Microsoft Power Automate*.

### <a name="microsoft-power-automate-example"></a>Exemplo do Microsoft Power Automate

Neste exemplo, usar **Quando um evento de negócios ocorre** com *Microsoft Power Automate* envia emails contendo mensagens InfoLog e hiperlinks para abrir a página **Mensagens do processador de mensagens** para uma mensagem de falha específica na implantação do hub. Se necessário, você pode adicionar lógica extra para enviar as notificações em paralelo usando diferentes canais e controlar os destinatários com base nos dados do evento.

1. No [Power Automate](https://preview.flow.microsoft.com), crie um novo fluxo de nuvem automatizado para o gatilho de fluxo **Quando um evento de negócios ocorre - Aplicativo Finance and Operations (Dynamics 365)** seguido pelas etapas **Analisar JSON** e **Enviar um email**, conforme mostrado na ilustração a seguir.

    :::image type="content" source="./media/cloud-edge-power-automate-example1.png" alt-text="Fluxo de nuvem automatizado do Power Automate.":::

1. Na etapa **Quando um Evento de Negócios ocorre**, você pode pesquisar ou inserir a **Instância** do hub após a **Categoria** e, em seguida, o **Evento de negócios** *Mensagem do processador de mensagens processada*, conforme mostrado na seguinte ilustração.

    :::image type="content" source="./media/cloud-edge-power-automate-example2.png" alt-text="Power Automate Etapa Quando um Evento de Negócios ocorre.":::

1. Para a etapa **Analisar JSON**, insira um **Esquema** que define os campos estendidos. Você pode usar a opção *Baixar esquema* na página **Catálogo de eventos de negócios** no Supply Chain Management ou começar colando o texto do esquema de exemplo. Este texto de exemplo é fornecido após a ilustração a seguir.

    :::image type="content" source="./media/cloud-edge-power-automate-example3.png" alt-text="Power Automate Analisar etapa JSON.":::

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

1. Na etapa **Enviar um email** você pode selecionar os campos individuais ou começar colando o exemplo de corpo de email no campo **Corpo**. Este exemplo é fornecido após a ilustração a seguir.

    :::image type="content" source="./media/cloud-edge-power-automate-example4.png" alt-text="Power Automate Enviar uma mensagem de email.":::

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

1. Quando você salvar o evento de negócios, ele será automaticamente ativado e pronto para ser usado como parte do Supply Chain Management.
