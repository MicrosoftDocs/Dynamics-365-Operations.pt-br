---
title: Entidades de criação de viagem
description: Este artigo fornece informações sobre entidades de dados de criação de viagem, que agrupam as entidades de dados necessárias para criar uma viagem de trabalho.
author: yufeihuang
ms.date: 05/27/2022
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yufeihuang
ms.search.validFrom: 2022-05-27
ms.dyn365.ops.version: 10.0.28
ms.openlocfilehash: 6234dfa61a5859e2ecaca75594c69c49ba326629
ms.sourcegitcommit: 5b34b41ae74269ba639e2876bc5862ef468da1cc
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/15/2022
ms.locfileid: "9167661"
---
# <a name="voyage-creation-entities"></a>Entidades de criação de viagem

[!include [banner](../includes/banner.md)]

As entidades de dados de criação de viagem agrupam as entidades de dados que são necessárias para criar uma viagem de trabalho. Você ou seu controlador de frete podem usar essas entidades de dados para criar registros de viagem, contêiner de remessa, fólio e linha de viagem que fazem referência a pedidos de comprador existentes ou linhas de pedidos de transferência.

## <a name="voyages-itmtableentity"></a>Viagens (ITMTableEntity)

A viagem representa a jornada de entrada de mercadorias e serve como a área de custo de nível mais alto no custo de entrega. Ela contém informações de nível de cabeçalho relacionadas à embarcação, ao porto de origem e ao porto de destino. Esta funcionalidade é compatível com a entidade `ITMTableEntity`. A tabela a seguir lista os campos e mapeamentos que compõem essa entidade.

| Nome | Mapeamento | Tipo de dados | Chave | Obrigatório |
|---|---|---|---|---|
| Modo de entrega | ITMTable.DlvModeId | Nvarchar(10) | Número | Número |
| Agente aconselhado | ITMTable.ITMBrokerAdvised | Datetime | Número | Número |
| Compromisso do cliente | ITMTable.ITMCustomerAppointment | Datetime | Número | Número |
| Entrega no depósito | ITMTable.ITMDelAtWarehouse | Datetime | Número | Número |
| Instruções de entrega | ITMTable.ITMDeliveryInstructions | Datetime | Número | Número |
| Data da partida | ITMTable.ITMDepartureDate | Datetime | Número | Número |
| Mercadorias lançadas | ITMTable.ITMGoodsReleased | Datetime | Número | Número |
| Data de transporte local | ITMTable.ITMLocalTransportDate | Datetime | Número | Número |
| Hora de transporte local | ITMTable.ITMLocalTransportTime | Int | Número | Número |
| Conhecimento de embarque original enviado | ITMTable.ITMOriginalBOLSebt | Datetime | Número | Número |
| Documentos originais recebidos | ITMTable.ITMOriginalDocsReceived | Datetime | Número | Número |
| Status da ordem de compra | ITMTable.ITMPurchStatus | Int | Número | Número |
| Data de verificação | ITMTable.ITMVerificationDate | Datetime | Número | Número |
| Identificador de entrada alfandegária | ITMTable.ShipCustomsEntryId | Nvarchar(20) | Número | Número |
| Data de remessa | ITMTable.ShipDate | Datetime | Número | Número |
| Descrição | ITMTable.ShipDescription | Nvarchar(60) | Número | Número |
| Documentos recebidos | ITMTable.ShipDocReceived | Int | Número | Número |
| Data de entrega estimada | ITMTable.ShipEstDlvDate | Datetime | Número | Número |
| ETA na porta de remessa | ITMTable.ShipEstPortDate | Datetime | Número | Número |
| Porta de origem | ITMTable.ShipFromPort | Nvarchar(20) | Número | Número |
| Conhecimento aéreo/conhecimento de embarque doméstico | ITMTable.ShipHAWB | Nvarchar(20) | Número | Número |
| Viagem | ITMTable.ShipId | Nvarchar(20) | **Sim** | **Sim** |
| Referência de reserva | ITMTable.ShipIdExternal | Nvarchar(20) | Número | Número |
| Modelo de diário | ITMTable.ShipJourneyId | Nvarchar(20) | Número | Número |
| Encaminhador local | ITMTable.ShipLocalForwarder | Nvarchar(20) | Número | Número |
| Conta mestre de porte aéreo/conhecimento de embarque | ITMTable.ShipMAWB | Nvarchar(20) | Número | Número |
| Medição | ITMTable.ShipMeasurement | Numeric(32, 6) | Número | Número |
| Unidade de medida | ITMTable.ShipMeasurementUnit | Int | Número | Número |
| Número de paletes | ITMTable.ShipNoOfPallets | Int | Número | Número |
| Viagem pendente | ITMTable.ShipPending | Int | Número | Número |
| Comentários | ITMTable.ShipRemarks | Nvarchar(MAX) | Número | Número |
| Locação | ITMTable.ShipRental | Int | Número | Número |
| Status da viagem | ITMTable.ShipStatusId | Nvarchar(20) | Número | Número |
| Correspondente em número | ITMTable.ShipTallyInNumber | Nvarchar(20) | Número | Número |
| Porta de destino | ITMTable.ShipToPort | Nvarchar(20) | Número | Número |
| Data de avaliação | ITMTable.ShipValuationDate | Datetime | Número | Número |
| Transportadora | ITMTable.ShipVendAccount | Nvarchar(20) | Número | Número |
| Embarcação | ITMTable.ShipVesselId | Nvarchar(20) | Número | **Sim** |
| ID de viagem externa | ITMTable.ShipVoyage | Nvarchar(20) | Número | Número |

### <a name="number-sequences-for-voyages"></a>Sequências numéricas para viagens

A sequência numérica compartilhada para viagens controla a alocação de IDs de viagem.

O valor que é passado para a entidade de dados como o valor **ID de viagem** (`ShipId`) é usado para identificar um registro existente para atualização. Se esse registro não existir, o comportamento dependerá se a sequência numérica atribuída está configurada para permitir a entrada manual:

- Se a entrada manual estiver habilitada, é criado um registro que usa o valor passado.
- Se a entrada manual não estiver habilitada, o próximo número na sequência numérica atribuída será usado em vez do valor passado.

Durante a sessão de importação, o valor do espaço reservado importado como a ID da viagem é retido. Esse comportamento garante que o contêiner de remessa e as linhas de viagem que fazem referência ao espaço reservado sejam incluídos na viagem e que sejam atualizados para refletir o valor atribuído na sequência numérica.

### <a name="automatic-cost-transactions"></a>Transações automáticas de custos

Os custos automáticos podem ser adicionados a uma viagem na página **Custos automáticos** no Microsoft Dynamics 365 Supply Chain Management (**Custo de entrega \> Configuração de avaliação de custo \> Custos automáticos**). Os registros de custos automáticos também podem ser criados usando entidades de dados de transação de custo para cada área de custo com a qual o custo de entrega é compatível.

Os custos automáticos configurados no Supply Chain Management são aplicados à viagem quando uma linha de viagem é criada. Nenhum custo será visível no registro até que o registro do cabeçalho seja associado às informações da linha.

## <a name="shipping-containers-itmcontainersentity"></a>Contêineres de envio (ITMContainersEntity)

Um contêiner de envio representa um contêiner físico no qual as mercadorias são transportadas. Esse contêiner físico pode ser um contêiner de frete para frete marítimo ou um único palete para frete aéreo. O contêiner de envio inclui informações de nível de cabeçalho relacionadas à ID do contêiner de envio, número do selo e tipo de contêiner de remessa. (O tipo de contêiner de envio fornece informações de dimensão.) Essa funcionalidade é compatível com a entidade `ITMContainersEntity`. A tabela a seguir lista os campos e mapeamentos que compõem essa entidade.

| Nome | Mapeamento | Tipo de dados | Chave | Obrigatório |
|---|---|---|---|---|
| Data da partida | ITMContainers.ITMDepartureDate | Datetime | Número | Número |
| Data de transporte local | ITMContainers.ITMLocalTransportDate | Datetime | Número | Número |
| Hora de transporte local | ITMContainers.ITMLocalTransportTime | Int | Número | Número |
| Viagem original | ITMContainers.OrigShipId | Nvarchar(20) | Número | Número |
| Peso real | ITMContainers.ShipActualWeight | Numeric(32, 6) | Número | Número |
| Agente aconselhado | ITMContainers.ShipBrokerAdvised | Datetime | Número | Número |
| Contêiner de remessa | ITMContainers.ShipContainerId | Nvarchar(20) | **Sim** | **Sim** |
| Tipo de contêiner de remessa | ITMContainers.ShipContainerTypeId | Nvarchar(20) | Número | Número |
| Tipo de Unidade | ITMContainers.ShipContainerUnitTypeId | Nvarchar(10) | Número | Número |
| Convertido em aluguel | ITMContainers.ShipConvertedToRental | Int | Número | Número |
| Compromisso do cliente | ITMContainers.ShipCustomerAppointment | Datetime | Número | Número |
| Data de remessa | ITMContainers.ShipDate | Datetime | Número | Número |
| Entrega no depósito | ITMContainers.ShipDelAtWarehouse | Datetime | Número | Número |
| Instruções de entrega | ITMContainers.ShipDeliveryInstructions | Datetime | Número | Número |
| Data de aplicação do certificado de exame | ITMContainers.ShipECAppliedDate | Datetime | Número | Número |
| Data de validade do certificado de exame | ITMContainers.ShipECExpiryDate | Datetime | Número | Número |
| Número do certificado de exame | ITMContainers.ShipECNum | Nvarchar(20) | Número | Número |
| Data de recebimento do certificado de exame | ITMContainers.ShipECReceivedDate | Datetime | Número | Número |
| Data de entrega estimada | ITMContainers.ShipEstDlvDate | Datetime | Número | Número |
| ETA na porta de remessa | ITMContainers.ShipEstPortDate | Datetime | Número | Número |
| Data de carregamento esperada | ITMContainers.ShipExpectedLoadingDate | Datetime | Número | Número |
| Porta de origem | ITMContainers.ShipFromPort | Nvarchar(20) | Número | Número |
| Descrição das mercadorias | ITMContainers.ShipGoodsDesc | Nvarchar(60) | Número | Número |
| Mercadorias lançadas | ITMContainers.ShipGoodsReleased | Datetime | Número | Número |
| Unidade do rastreador GPS | ITMContainers.ShipGPSUnit | Nvarchar(30) | Número | Número |
| Conhecimento aéreo/conhecimento de embarque doméstico | ITMContainers.ShipHAWB | Nvarchar(20) | Número | Número |
| Viagem | ITMContainers.ShipId | Nvarchar(20) | **Sim** | **Sim** |
| Modelo de diário | ITMContainers.ShipJourneyId | Nvarchar(20) | Número | Número |
| Encaminhador local | ITMContainers.ShipLocalForwarder | Nvarchar(20) | Número | Número |
| Medição | ITMContainers.ShipMeasurement | Numeric(32, 6) | Número | Número |
| Unidade de medida | ITMContainers.ShipMeasurementUnit | Int | Número | Número |
| Número de caixas | ITMContainers.ShipNoOfCartons | Numeric(32, 6) | Número | Número |
| Conhecimento de embarque original enviado | ITMContainers.ShipOriginalBOLSebt | Datetime | Número | Número |
| Documentos originais recebidos | ITMContainers.ShipOriginalDocsReceived | Datetime | Número | Número |
| Nosso número de lacre | ITMContainers.ShipOurSealNum | Nvarchar(20) | Número | Número |
| Usado | ITMContainers.ShipPendingUsed | Int | Número | Número |
| Status da ordem de compra | ITMContainers.ShipPurchStatus | Int | Número | Número |
| Tipo de refrigeração | ITMContainers.ShipRefrigerationTypeId | Nvarchar(10) | Número | Número |
| Comentários | ITMContainers.ShipRemarks | Nvarchar(MAX) | Número | Número |
| Locação | ITMContainers.ShipRental | Int | Número | Número |
| Retornável | ITMContainers.ShipReturnable | Int | Número | Número |
| Status da viagem | ITMContainers.ShipStatusId | Nvarchar(20) | Número | Número |
| Número de lacre da empresa transportadora | ITMContainers.ShipTheirSealNum | Nvarchar(20) | Número | Número |
| Porta de destino | ITMContainers.ShipToPort | Nvarchar(20) | Número | Número |
| Data de verificação | ITMContainers.ShipVerificationDate | Datetime | Número | Número |
| Embarcação | ITMContainers.ShipVesselId | Nvarchar(20) | Número | **Sim** |

### <a name="voyage-id-validation"></a>Validação de ID de viagem

A ID do contêiner de envio não é controlado por uma sequência numérica. É único apenas no contexto da viagem em que é usado.

Se a entidade de contêiner de envio (`ITMContainersEntity`) for usada independentemente da entidade de viagem (`ITMTableEntity`), o valor **ID de viagem** (`ShipId`) deverá corresponder a um registro existente na tabela de viagem. Caso contrário, a importação falhará.

Se a entidade de contêiner de envio (`ITMContainersEntity`) e a entidade de viagem (`ITMTableEntity`) forem usadas como parte da mesma sessão de importação, a entidade de viagem deve preceder a criação de um contêiner de envio. Caso contrário, o valor **ID de viagem** (`ShipId`) não poderá ser validado com sucesso. Se um valor de espaço reservado for usado para o valor **ID de viagem** (`ShipId`), a associação poderá ser criada somente se o mesmo espaço reservado for usado como o valor **ID de viagem** (`ShipId`) na entidade de contêiner.

### <a name="other-field-validations"></a>Outras validações de campo

A tabela a seguir mostra os campos na tabela de contêineres de envio (`ITMContainers`) que são validados em relação às tabelas de configuração de custo de entrega. Ela também mostra as entidades de dados de custo de entrega que um controlador de frete pode usar para ler os valores existentes e garantir que os valores válidos sejam recebidos em seu ambiente.

| Campo na tabela ITMContainers | Entidade de dados de custo de entrega |
|---|---|
| Tipo de contêiner de remessa | ITMShippingContainerTypeEntity |
| Descrição das mercadorias | ITMGoodsDescriptionEntity |
| Tipo de refrigeração | ITMShippingContainerRefrigerationTypeEntity |

## <a name="folios-itmfolioentity"></a>Fólios (ITMFolioEntity)

Um fólio representa um agrupamento de itens em um contêiner de envio para fins de declarações alfandegárias. O fólio inclui informações no nível do cabeçalho relacionadas ao agente alfandegário e uma descrição das mercadorias. Esta funcionalidade é compatível com a entidade `ITMFolioEntity`. A tabela a seguir lista os campos e mapeamentos que compõem essa entidade.

| Nome | Mapeamento | Tipo de dados | Chave | Obrigatório |
|---|---|---|---|---|
| Agente aconselhado | ITMFolioTable.ShipBrokerAdvised | Datetime | Número | Número |
| Número de controle de carga | ITMFolioTable.ShipCargoControlNumber | Nvarchar(20) | Número | Número |
| Compromisso do cliente | ITMFolioTable.ShipCustomerAppointment | Datetime | Número | Número |
| Agente alfandegário | ITMFolioTable.ShipCustomsBroker | Nvarchar(20) | Número | Número |
| ID da Alfândega | ITMFolioTable.ShipCustomsId | Nvarchar(60) | Número | Número |
| Empresa | ITMFolioTable.ShipDataArea | Nvarchar(4) | Número | **Sim** |
| Entrega no depósito | ITMFolioTable.ShipDelAtWarehouse | Datetime | Número | Número |
| Instruções de entrega | ITMFolioTable.ShipDeliveryInstructions | Datetime | Número | Número |
| Documentos recebidos | ITMFolioTable.ShipDocReceived | Int | Número | Número |
| Data de entrega estimada | ITMFolioTable.ShipEstDlvDate | Datetime | Número | Número |
| ETA na porta de remessa | ITMFolioTable.ShipEstPortDate | Datetime | Número | Número |
| Exportador | ITMFolioTable.ShipExporterId | Nvarchar(20) | Número | Número |
| Nome | ITMFolioTable.ShipExporterName | Nvarchar(60) | Número | Número |
| Data do fólio | ITMFolioTable.ShipFolioDate | Datetime | Número | Número |
| Fólio | ITMFolioTable.ShipFolioId | Nvarchar(20) | **Sim** | **Sim** |
| Porta de origem | ITMFolioTable.ShipFromPort | Nvarchar(20) | Número | Número |
| Descrição das mercadorias | ITMFolioTable.ShipGoodsDesc | Nvarchar(60) | Número | Número |
| Mercadorias lançadas | ITMFolioTable.ShipGoodsReleased | Datetime | Número | Número |
| Conhecimento aéreo/conhecimento de embarque doméstico | ITMFolioTable.ShipHAWB | Nvarchar(20) | Número | Número |
| Viagem | ITMFolioTable.ShipId | Nvarchar(20) | Número | **Sim** |
| Medição | ITMFolioTable.ShipMeasurement | Numeric(32, 6) | Número | Número |
| Unidade de medida | ITMFolioTable.ShipMeasurementUnit | Int | Número | Número |
| Número de caixas | ITMFolioTable.ShipNoOfCartons | Numeric(32, 6) | Número | Número |
| Conhecimento de embarque original enviado | ITMFolioTable.ShipOriginalBOLSebt | Datetime | Número | Número |
| Documentos originais recebidos | ITMFolioTable.ShipOriginalDocsReceived | Datetime | Número | Número |
| Status da ordem de compra | ITMFolioTable.ShipPurchStatus | Int | Número | Número |
| Comentários | ITMFolioTable.ShipRemarks | Nvarchar(MAX) | Número | Número |
| Status da viagem | ITMFolioTable.ShipStatusId | Nvarchar(20) | Número | Número |
| Código de tarifa | ITMFolioTable.ShipTariffCode | Nvarchar(10) | Número | Número |
| Porta de destino | ITMFolioTable.ShipToPort | Nvarchar(20) | Número | Número |
| Data de avaliação | ITMFolioTable.ShipValuationDate | Datetime | Número | Número |
| Data de verificação | ITMFolioTable.ShipVerificationDate | Datetime | Número | Número |
| Conta de Fornecedor | ITMFolioTable.VendAccount | Nvarchar(20) | Número | Número |

### <a name="number-sequences-for-folios"></a>Sequências numéricas para fólios

A sequência numérica para fólios controla a alocação de IDs de fólio.

O valor que é passado para a entidade de dados como o valor **ID de fólio** (`FolioId`) é usado para identificar um registro existente para atualização. Se esse registro não existir, o comportamento dependerá se a sequência numérica atribuída está configurada para permitir a entrada manual:

- Se a entrada manual estiver habilitada, é criado um registro que usa o valor passado.
- Se a entrada manual não estiver habilitada, o próximo número na sequência numérica atribuída será usado em vez do valor passado.

Durante a sessão de importação, o valor do espaço reservado importado como a ID da fólio é retido. Esse comportamento garante que as linhas de viagem que fazem referência ao espaço reservado sejam associadas corretamente e que sejam atualizadas para refletir o valor atribuído na sequência numérica.

### <a name="field-validations"></a>Validações de campo

O campo **Descrição das mercadorias** na tabela de fólio (`ITMFolioTable`) é validado em relação à tabela de configuração de custo de importação com o mesmo nome. Um controlador de frete pode usar a entidade de dados de custo de entrega `ITMGoodsDescriptionEntity` para ler os valores existentes e garantir que valores válidos sejam recebidos em seu ambiente.

## <a name="voyage-lines-for-purchase-orders-itmpurchaselineentity"></a>Linhas de viagem para pedidos de compra (ITMPurchaseLineEntity)

A linha de viagem representa uma única linha de pedido de compra incluída na viagem. Essa relação é estabelecida por meio dos campos **Número da ordem de compra** e **Número da linha de compra**. A linha de viagem faz referência a cada registro anterior que foi criado para a viagem, contêiner de transporte e fólio. Esta funcionalidade é compatível com a entidade `ITMPurchaseLineEntity`. A tabela a seguir lista os campos e mapeamentos que compõem essa entidade.

| Nome | Mapeamento | Tipo de dados | Chave | Obrigatório |
|---|---|---|---|---|
| Moeda | ITMLine.CurrencyCode | Nvarchar(3) | Número | Número |
| Valor líquido | ITMLine.LineAmountMST | Numeric(32, 6) | Número | Número |
| Número da linha de compra | ITMLine.RefRecId | Numeric(32, 6) | **Sim** | Número |
| Contêiner de remessa | ITMLine.ShipContainerId | Int | Número | Número |
| Empresa | ITMLine.ShipDataArea | Nvarchar(20) | **Sim** | Número |
| Quantidade declarada | ITMLine.ShipDeclaredQty | Nvarchar(4) | Número | Número |
| Fólio | ITMLine.ShipFolioId | Numeric(32, 6) | Número | Número |
| Viagem | ITMLine.ShipId | Nvarchar(20) | **Sim** | Número |
| Número do item | ITMLine.ShipItemId | Nvarchar(20) | Número | Número |
| Medição | ITMLine.ShipMeasurement | Nvarchar(20) | Número | Número |
| Unidade de medida | ITMLine.ShipMeasurementUnit | Numeric(32, 6) | Número | Número |
| Número de caixas | ITMLine.ShipNoOfCartons | Int | Número | Número |
| Cargo | ITMLine.ShipPosition | Numeric(32, 6) | Número | Número |
| Quantidade | ITMLine.ShipQty | Int | Número | Número |
| Número da ordem de compra | ITMLine.TransRefId | Numeric(32, 6) | **Sim** | Número |
| Unidade | ITMLine.UnitId | Int | Número | Número |
| Volume | ITMLine.Volume | Nvarchar(10) | Número | Número |
| Peso | ITMLine.Weight | Numeric(32, 6) | Número | Número |

## <a name="voyage-lines-for-transfer-orders-itmtransferlineentity"></a>Linhas de viagem para pedidos de transferência (ITMTransferLineEntity)

A linha de viagem representa uma única linha de pedido de transferência incluída na viagem. Essa relação é estabelecida por meio dos campos **Número da ordem de transferência** e **Número da linha de transferência**. A linha de viagem faz referência a cada registro anterior que foi criado para a viagem, contêiner de transporte e fólio. Esta funcionalidade é compatível com a entidade `ITMTransferLineEntity`. A tabela a seguir lista os campos e mapeamentos que compõem essa entidade.

| Nome | Mapeamento | Tipo de dados | Chave | Obrigatório |
|---|---|---|---|---|
| Moeda | ITMLine.CurrencyCode | Nvarchar(3) | Número | Número |
| Valor líquido | ITMLine.LineAmountMST | Numeric(32, 6) | Número | Número |
| Contêiner de remessa | ITMLine.ShipContainerId | Int | Número | Número |
| Empresa | ITMLine.ShipDataArea | Nvarchar(20) | **Sim** | Número |
| Quantidade declarada | ITMLine.ShipDeclaredQty | Nvarchar(4) | Número | Número |
| Fólio | ITMLine.ShipFolioId | Numeric(32, 6) | Número | Número |
| Viagem | ITMLine.ShipId | Nvarchar(20) | **Sim** | Número |
| Número do item | ITMLine.ShipItemId | Nvarchar(20) | Número | Número |
| Medição | ITMLine.ShipMeasurement | Nvarchar(20) | Número | Número |
| Unidade de medida | ITMLine.ShipMeasurementUnit | Numeric(32, 6) | Número | Número |
| Número de caixas | ITMLine.ShipNoOfCartons | Int | Número | Número |
| Cargo | ITMLine.ShipPosition | Numeric(32, 6) | Número | Número |
| Quantidade | ITMLine.ShipQty | Int | Número | Número |
| Número da linha de transferência | ITMLine.TransferLineNumber | Numeric(32, 6) | **Sim** | Número |
| Número da ordem de transferência | ITMLine.TransRefId | Numeric(32, 6) | **Sim** | Número |
| Unidade | ITMLine.UnitId | Int | Número | Número |
| Volume | ITMLine.Volume | Nvarchar(10) | Número | Número |
| Peso | ITMLine.Weight | Numeric(32, 6) | Número | Número |

### <a name="reference-table"></a>Tabela de referência

As linhas de viagem são criadas por meio de uma associação com uma linha de pedido de entrada aberta. Essa linha pode estar em um pedido de compra ou pode ser a transação de recebimento em um pedido de transferência. O campo `RefTableId` na tabela de linhas de viagem (`ITMLine`) especifica a qual tipo de pedido a linha está relacionada, referenciando o número da tabela. Se números de tabela específicos forem referenciados na tabela em que os dados estão sendo criados, as entidades serão divididas com base nesses valores.

Os valores da tabela de referência (`RefTableId`) e o tipo de transação (`TransType`) estão implícitos na seleção da entidade de linha de compra de custo de entrega ou da entidade de linha de transferência de custo de entrega.

### <a name="validation"></a>Validação

Uma linha de viagem faz referência direta a um registro de viagem, um registro de contêiner e um registro de fólio. Se a entidade de linha de compra (`ITMPurchaseLinesEntity`) ou a entidade de linha de transferência (`ITMPurchaseLinesEntity`) for usada independentemente das entidades usadas para criar esses registros de referência, os valores **ID de viagem** (`ShipId`), **Contêiner de remessa** (`ShipContainerId`) e **Fólio** (`ShipFolioId`) devem corresponder a um registro existente nas tabelas correspondentes. Caso contrário, a importação falhará.

Se qualquer entidade de linha for usada como parte da mesma sessão de importação, essas outras entidades devem preceder a criação de uma linha de viagem. Caso contrário, os valores não podem ser validados com sucesso. Se um valor de espaço reservado for usado para a viagem ou número de fólio, a associação poderá ser criada somente se o mesmo espaço reservado for usado para a viagem ou número de fólio na entidade de linha de viagem.

Se a linha de pedido de compra ou pedido de transferência já estiver atribuída a uma linha de viagem existente, a nova linha de viagem não será criada. Antes que a linha de pedido possa ser atribuída a uma nova viagem, ela deve ser removida de sua viagem atual.

### <a name="order-line-identification"></a>Identificação da linha do pedido

As linhas de viagem fazem referência direta aos valores de referência **ID do registro** (`RefRecId`), **ID de dimensão de estoque** (`InventDimId`) e **ID de transação de estoque** (`InventTransId`) Esses valores não precisam mais ser incluídos quando a entidade de dados é usada. Em vez disso, o número da linha do pedido agora deve ser incluído. Juntos, o número da linha do pedido e o número do pedido permitem que cada um desses valores de referência seja identificado.

### <a name="voyage-line-quantity"></a>Quantidade da linha de viagem

Como uma linha de viagem está diretamente associada a uma linha de pedido, o valor **Quantidade** (`ShipQty`) inserido usando a entidade exige que os valores correspondam. A validação é executada em relação à quantidade na linha do pedido de compra ou no pedido de transferência. Se a validação falhar, o registro não será processado.

### <a name="calculated-fields"></a>Campos calculados

Os campos calculados **Peso** e **Volume** aceitam os valores recebidos por meio da entidade de dados. Se nenhum valor for fornecido, os valores do sistema serão usados para atualizar esses campos, se os valores do sistema estiverem disponíveis. Para Custo no entrega, os valores são calculados da seguinte forma:

- *Peso* = *Quantidade* × *Peso bruto do item*
- *Volume* = *Quantidade* × (*Profundidade bruta do item* × *Altura bruta do item* × *Largura bruta do item*)

## <a name="sequencing"></a>Sequenciamento

Devido às dependências entre as tabelas, o registro de viagem deve ser criado primeiro. A linha de viagem pode ser criada somente após a criação da viagem, do contêiner de remessa e dos fólios.

Para criar uma viagem sem avisos de validação, o sistema deve processar as entidades na seguinte ordem:

1. Viagens (`ITMTableEntity`)
1. Contêineres de remessa (`ITMContainersEntity`)
1. Fólios (`ITMFolioTableEntity`)
1. Linhas de viagem (`ITMPurchaseLinesEntity` ou `ITMTransferLinesEntity`)
