---
title: Integração com sistemas de execução de fabricação de terceiros
description: Este artigo explica como você pode integrar o Microsoft Dynamics 365 Supply Chain Management com um sistema de execução de fabricação de terceiros (MES).
author: johanhoffmann
ms.date: 10/01/2021
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2021-10-01
ms.dyn365.ops.version: 10.0.23
ms.openlocfilehash: 208ed2d6c8b411d12888966d9c175730e828eb44
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8860628"
---
# <a name="integrate-with-third-party-manufacturing-execution-systems"></a>Integração com sistemas de execução de fabricação de terceiros

[!include [banner](../includes/banner.md)]

Algumas organizações de fabricação que usam o Microsoft Dynamics 365 Supply Chain Management usam a funcionalidade nativa no Dynamics 365 para controlar atividades de fabricação para máquinas, equipamentos e funcionários. No entanto, outras organizações de fabricação, especialmente com requisitos avançados de fabricação, usam um MES (sistema de execução de fabricação de terceiros). As organizações podem escolher uma solução MES de terceiros porque, por exemplo, ela é especificamente ajustada ao setor vertical.

Na solução integrada, a troca de dados é totalmente automatizada e ocorre em tempo quase real. Portanto, os dados são mantidos atuais nos dois sistemas e não é necessária a entrada de dados manual. Por exemplo, quando o consumo de material é registrado no MES, a integração garante que o mesmo consumo também esteja registrado no Dynamics 365. Portanto, os registros de estoque atualizados estão disponíveis para outros processos importantes, como planejamento e vendas.

A solução torna a integração de usuários do Supply Chain Management com MESs terceirizados mais rápida, fácil e barata. Ela oferece os seguintes recursos:

- Eventos e interfaces de negócios compatíveis com os [principais processos de execução de fabricação](#processes-available-for-mes-integration)
- Um painel centralizado em que é possível rastrear o histórico de processamento de eventos e solucionar e corrigir processos com falha

A ilustração a seguir mostra uma coleção típica de eventos de negócios, processos e mensagens trocadas em uma solução integrada.

![Cenário de integração típico.](media/3p-mes-scenario.png "Cenário de integração típico.")

## <a name="turn-on-the-mes-integration-feature"></a>Ativar o recurso de integração MES

Para que você possa usar esse recurso, um administrador deve ativá-lo no sistema, conforme descrito no procedimento a seguir.

1. Acesse **Administração de sistema \> Configurar \> Configuração de licença**.
1. Verifique se a chave de licença **Horário e presença** está habilitada (exibe uma marca de seleção). Essa chave de licença é necessária porque ela controla a funcionalidade e os dados do sistema de execução de fabricação. Se ela não estiver habilitada, siga estas etapas:
    1. Coloque seu sistema em modo de manutenção, conforme descrito em [Modo de manutenção](../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md).
    1. Na página **Configuração de licença**, marque a caixa de seleção **Horário e presença**.
    1. Desative o modo de manutenção, conforme descrito no [Modo de manutenção](../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md)
1. Acesse **Administrador do sistema \> Espaços de trabalho \> Gerenciamento de recursos**.
1. Habilite o recurso listado da seguinte forma (consulte também [Visão geral do gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)):
    - **Módulo:** *Controle de produção*
    - **Nome do recurso:** *Integração do sistema de execução de fabricação*

## <a name="processes-available-for-mes-integration"></a>Processos disponíveis para integração MES

Você pode habilitar qualquer ou todos os processos a seguir para integração.

| Nome do processo | Descrição |
|---|---|
| Liberar ordens de produção e status de ordem de produção para alterar eventos de negócios | Esse processo fornece um evento de negócios que o MES pode ouvir, para obter informações sobre as ordens de produção que devem ser produzidas. Espera-se que os dados de referência relacionados à ordem de produção sejam compartilhados do Supply Chain Management para o MES por meio do Protocolo Open Data (OData) ou de entidades de dados. |
| Começar ordem de produção | Este processo fornece ao Supply Chain Management informações sobre ordens de produção iniciadas com o MES. Ele garante que os dois sistemas tenham uma exibição atualizada de todas as atividades de fabricação. |
| Relatório produzido ou quantidade sucateada | Este processo fornece ao Supply Chain Management informações sobre quantidades de mercadoria e de erro que são relatadas em um trabalho de produção com o MES. Ele garante que os supervisores de chão de fábrica tenham uma exibição atualizada do andamento do plano de produção. |
| Relatar consumo de materiais | Esse processo fornece ao Supply Chain Management informações do MES sobre as quantidades de materiais consumidos. Ele disponibiliza registros de estoque atualizados para outros processos importantes, como planejamento e vendas. |
| Relatar tempo consumido para a operação | Esse processo fornece ao Supply Chain Management informações sobre o tempo usado para uma operação específica. |
| Ordem de produção final | Esse processo informa ao Supply Chain Management que o MES atualizou uma ordem de produção para o status final *Concluído*. Esse status indica que nenhuma quantidade maior será produzida na ordem de produção. |

## <a name="monitor-incoming-messages"></a>Monitorar mensagens de entrada

Para monitorar as mensagens de entrada no sistema, abra a página **Integração de sistemas de execução de fabricação**. Lá você pode exibir, processar e solucionar problemas.

Todas as mensagens para uma ordem de produção específica são processadas na sequência em que são recebidas. No entanto, as mensagens para ordens de produção diferentes não podem ser processadas na sequência de recebimentos porque os trabalhos em lotes são processados em paralelo. No caso de falha, o trabalho em lotes tentará processar cada mensagem três vezes antes de defini-la como status de *Falha*.

## <a name="call-the-api"></a>Chamar a API

Para chamar a API de integração de MES, envie uma solicitação `POST` para a seguinte URL de ponto de extremidade:

`/api/services/SysMessageServices/SysMessageService/SendMessage`

O corpo da solicitação enviada deve ser semelhante ao exemplo a seguir. Substitua os valores de `_companyId`, `_messageType` e `_messageContent` conforme necessário. Para obter informações sobre os vários tipos de mensagem com suporte da API e como criar seu conteúdo, consulte a próxima seção.

```json
{
    "_companyId": "USMF",
    "_messageQueue": "JmgMES3P",
    "_messageType": "ProdProductionOrderReportFinished",
    "_messageContent":
    "{\"ProductionOrderNumber\": \"P000123\", \"ReportFinishedLines\": [{\"ItemNumber\": \"A0001\", \"ReportedGoodQuantity\": 10, \"ReportAsFinishedDate\": \"2021-01-01\"}]}"
}
```

## <a name="api-message-types-and-content"></a>Tipos e conteúdo de mensagens de API

Esta seção descreve cada tipo de mensagem que pode ser trocada por meio da API de integração MES.

### <a name="start-production-order-message"></a>Mensagem iniciar ordem de produção

Para a mensagem *iniciar ordem de produção*, o valor `_messageType` é `ProdProductionOrderStart`. A tabela a seguir mostra os campos com suporte desta mensagem.

| Nome do campo | Status | Tipo |
|---|---|---|
| `ProductionOrderNumber` | Obrigatório | Sequência de caracteres |
| `StartedQuantity` | Opcional | Real |
| `StartedDate` | Opcional | Data |
| `AutomaticBOMConsumptionRule` | Opcional | Enum (FlushingPrincip \| Always \| Never) |

### <a name="report-as-finished-message"></a>Mensagem Relatar como concluído

Para a mensagem *relatar como concluído*, o valor `_messageType` é `ProdProductionOrderReportFinished`. A tabela a seguir mostra os campos com suporte desta mensagem.

| Nome do campo | Status | Tipo |
|---|---|---|
| `ProductionOrderNumber` | Obrigatório | Sequência de caracteres |
| `ReportFinishedLines` | Obrigatório | Uma lista de linhas (pelo menos uma), cada uma contendo o payload descrito na próxima tabela |

A tabela a seguir mostra os campos compatíveis com cada linha na seção `ReportFinishedLines` da mensagem `ProdProductionOrderReportFinished`.

| Nome do campo | Status | Tipo |
|---|---|---|
| `LineNumber` | Opcional | Real |
| `ItemNumber` | Opcional | Sequência de caracteres|
| `ProductionType` | Opcional | Enum (MainItem \| Formula \| BOM \| Co_Product \| By_Product \| None), extensível |
| `ReportedErrorQuantity` | Opcional | Real|
| `ReportedGoodQuantity` | Opcional | Real|
| `ReportedErrorCatchWeightQuantity` | Opcional | Real |
| `ReportedGoodCatchWeightQuantity` | Opcional | Real |
| `AcceptError` | Opcional | Enum (Sim\|Não) |
| `ErrorCause` | Opcional | Enum (None \| Material \| Machine \| OperatingStaff), extensível |
| `ExecutedDateTime` | Opcional | Data e Hora |
| `ReportAsFinishedDate` | Opcional | Data |
| `AutomaticBOMConsumptionRule` | Opcional | Enum (FlushingPrincip \| Always \| Never) |
| `AutomaticRouteConsumptionRule` | Opcional |Enum (RouteDependent \| Always \| Never) |
| `RespectFlushingPrincipleDuringOverproduction` | Opcional | Enum (Sim\|Não) |
| `ProductionJournalNameId` | Opcional | Cadeia de caracteres |
| `PickingListProductionJournalNameId` | Opcional | Cadeia de caracteres|
| `RouteCardProductionJournalNameId` | Opcional | Cadeia de caracteres |
| `FromOperationNumber` | Opcional | Inteiro|
| `ToOperationNumber` | Opcional | Inteiro|
| `InventoryLotId` | Opcional | Cadeia de caracteres |
| `BaseValue` | Opcional | Cadeia de caracteres |
| `EndJob` | Opcional | Enum (Sim\|Não) |
| `EndPickingList` | Opcional | Enum (Sim\|Não) |
| `EndRouteCard` | Opcional | Enum (Sim\|Não) |
| `PostNow` | Opcional | Enum (Sim\|Não) |
| `AutoUpdate` | Opcional | Enum (Sim\|Não) |
| `ProductColorId` | Opcional | Cadeia de caracteres|
| `ProductConfigurationId` | Opcional | Cadeia de caracteres |
| `ProductSizeId` | Opcional | Cadeia de caracteres |
| `ProductStyleId` | Opcional | Sequência de caracteres |
| `ProductVersionId` | Opcional | Sequência de caracteres |
| `ItemBatchNumber` | Opcional | Sequência de caracteres |
| `ProductSerialNumber` | Opcional | Sequência de caracteres |
| `LicensePlateNumber` | Opcional | Sequência de caracteres |
| `InventoryStatusId` | Opcional | Sequência de caracteres |
| `ProductionWarehouseId` | Opcional | Sequência de caracteres |
| `ProductionSiteId` | Opcional | Sequência de caracteres |
| `ProductionWarehouseLocationId` | Opcional | Sequência de caracteres |
| `InventoryDimension1` a `InventoryDimension12` | Opcional | Sequência de caracteres |

As 12 dimensões extensíveis (`InventoryDimension1` a `InventoryDimension12`) exigem personalização e nem sempre são usadas. Para obter mais informações sobre elas, consulte [Adicionar novas dimensões de estoque por meio da extensão](../../fin-ops-core/dev-itpro/extensibility/inventory-dimensions.md).

### <a name="material-consumption-picking-list-message"></a>Mensagem de consumo de material (lista de separação)

Para a mensagem *consumo de material (lista de separação)*, o valor `_messageType` é `ProdProductionOrderPickingList`. A tabela a seguir mostra os campos com suporte desta mensagem.

| Nome do campo | Status | Tipo |
|---|---|---|
| `ProductionOrderNumber` | Obrigatório | Sequência de caracteres |
| `JournalNameId` | Opcional | Sequência de caracteres |
| `PickingListLines` | Obrigatório | Uma lista de linhas (pelo menos uma), cada uma contendo o payload descrito na próxima tabela |

A tabela a seguir mostra os campos compatíveis com cada linha na seção `PickingListLines` da mensagem `ProdProductionOrderPickingList`.

| Nome do campo | Status | Tipo |
|---|---|---|
| `ItemNumber` | Obrigatório | Sequência de caracteres |
| `ConsumptionBOMQuantity` | Opcional | Real |
| `ProposalBOMQuantity` | Opcional | Real |
| `ScrapBOMQuantity` | Opcional | Real |
| `BOMUnitSymbol` | Opcional | Sequência de caracteres |
| `ConsumptionInventoryQuantity` | Opcional | Real |
| `ProposalInventoryQuantity` | Opcional | Real |
| `ConsumptionCatchWeightQuantity` | Opcional | Real |
| `ProposalCatchWeightQuantity` | Opcional | Real |
| `ConsumptionDate` | Opcional | Data |
| `OperationNumber` | Opcional | Inteiro |
| `LineNumber` | Opcional | Real |
| `PositionNumber` | Opcional | Cadeia de caracteres |
| `IsConsumptionEnded` | Opcional | Enum (Sim\|Não) |
| `ErrorCause` | Opcional | Enum (None \| Material \| Machine \| OperatingStaff), extensível |
| `InventoryLotId` | Opcional | Cadeia de caracteres |

### <a name="time-used-for-operation-route-card-message"></a>Tempo usado para a mensagem da operação (cartão de roteiro)

Para a mensagem *tempo usado para a operação (cartão de roteiro)*, o valor `_messageType` é `ProdProductionOrderRouteCard`. A tabela a seguir mostra os campos com suporte desta mensagem.

| Nome do campo | Status | Tipo |
|---|---|---|
| `ProductionOrderNumber` | Obrigatório | Sequência de caracteres |
| `JournalNameId` | Opcional | Sequência de caracteres |
| `RouteCardLines` | Obrigatório | Uma lista de linhas (pelo menos uma), cada uma contendo o payload descrito na próxima tabela |

A tabela a seguir mostra os campos compatíveis com cada linha na seção `RouteCardLines` da mensagem `ProdProductionOrderRouteCard`.

| Nome do campo | Status | Tipo |
|---|---|---|
| `OperationNumber` | Obrigatório | Inteiro |
| `OperationPriority` | Opcional | Enum (Primary \| Secondary1 \| Secondary2 \| ... \| Secondary20) |
| `OperationId` | Opcional | Sequência de caracteres |
| `OperationsResourceId` | Opcional | Sequência de caracteres |
| `Worker` | Opcional | Sequência de caracteres |
| `HoursRouteCostCategoryId` | Opcional | Sequência de caracteres |
| `QuantityRouteCostCategoryId` | Opcional | Sequência de caracteres |
| `HourlyRate` | Opcional | Real |
| `Hours` | Opcional | Real |
| `GoodQuantity` | Opcional | Real |
| `ErrorQuantity` | Opcional | Real |
| `CatchWeightGoodQuantity` | Opcional | Real |
| `CatchWeightErrorQuantity` | Opcional | Real |
| `QuantityPrice` | Opcional | Real |
| `ProcessingPercentage` | Opcional | Real |
| `ConsumptionDate` | Opcional | Data |
| `TaskType` | Opcional | Enum (QueueBefore \| Setup \| Process \| Overlap \| Transport \| QueueAfter \| Burden) |
| `ErrorCause` | Opcional | Enum (None \| Material \| Machine \| OperatingStaff), extensível |
| `OperationCompleted` | Opcional | Enum (Sim\|Não) |
| `BOMConsumption` | Opcional | Enum (Sim\|Não) |
| `ReportAsFinished` | Opcional | Enum (Sim\|Não) |

### <a name="end-production-order-message"></a>Mensagem Finalizar ordem de produção

Para a mensagem *finalizar ordem de produção*, o valor `_messageType` é `ProdProductionOrderEnd`. A tabela a seguir mostra os campos com suporte desta mensagem.

| Nome do campo | Status | Tipo |
|---|---|---|
| `ProductionOrderNumber` | Obrigatório | Cadeia de caracteres |
| `ExecutedDateTime` | Opcional | Data e Hora |
| `EndedDate` | Opcional | Data |
| `UseTimeAndAttendanceCost` | Opcional | Enum (Sim\|Não) |
| `AutoReportAsFinished` | Opcional | Enum (Sim\|Não) |
| `AutoUpdate` | Opcional | Enum (Sim\|Não) |

## <a name="other-production-information"></a>Outras informações de produção

As mensagens suportam ações ou eventos que ocorrem no chão de fábrica. Elas são processadas usando a estrutura de integração MES descrita neste artigo. O design supõe que outras informações de referência a serem compartilhadas com o MES (como informações relacionadas ao produto ou a lista de materiais ou o roteiro (com os horários de configuração e configuração específicos) usados em uma ordem de produção específica) serão recuperadas do sistema usando [entidades de dados](../../fin-ops-core/dev-itpro/data-entities/data-entities-data-packages.md#data-entities) via transferência de arquivo ou OData.

## <a name="receive-feedback-about-the-state-of-a-message"></a>Receber comentários sobre o estado de uma mensagem

Após o MES enviar uma mensagem para o Supply Chain Management, talvez seja relevante para o Supply Chain Management retornar comentários sobre o estado da mensagem. Veja alguns exemplos de casos em que esse comportamento pode ser relevante:

- Não há pessoa responsável por supervisionar constantemente a integração de MES.
- A pessoa responsável por supervisionar a integração de MES deseja ser notificada por email quando uma mensagem falha, para que saiba que precisa agir.
- O MES deve mostrar uma mensagem de erro para informar o operador de chão de fábrica ou alguém do departamento de TI que deve tomar medidas.
- O MES deve recalcular o agendamento da ordem após receber uma mensagem de falha (por exemplo, porque uma ordem de produção falhou ao iniciar).

Nesses casos, você pode aproveitar o recurso de alerta padrão no Supply Chain Management. Para obter informações sobre como alertas padrão funcionam, consulte os seguintes recursos:

- Artigo da ajuda: [Visão geral de alertas](../../fin-ops-core/fin-ops/get-started/alerts-overview.md)
- Vídeo: [Opções de regras de alerta no Dynamics 365 for Finance and Operations](https://www.youtube.com/watch?v=cpzimwOjicM&ab_channel=MicrosoftDynamics365)

Por exemplo, você pode configurar os seguintes alertas para fornecer comentários sobre o estado de uma mensagem:

- Crie um evento de negócios ("Enviar externamente") que é usado quando uma mensagem *Falha*.
- Envie uma notificação e um email para o administrador de TI ou o gerente de piso de produção.
