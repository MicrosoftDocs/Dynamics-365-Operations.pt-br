---
title: Atribuir títulos e ícones de etapa ao aplicativo móvel Warehouse Management
description: Este artigo descreve como atribuir ícones e títulos de etapas para fluxos de tarefas novos ou personalizados para o aplicativo móvel Warehouse Management.
author: Mirzaab
ms.date: 05/17/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2021-05-17
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 361ace454f7125ec86bd99cffefc7d268f81d37f
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8890586"
---
# <a name="assign-step-icons-and-titles-for-the-warehouse-management-mobile-app"></a>Atribuir títulos e ícones de etapa ao aplicativo móvel Warehouse Management

[!include [banner](../includes/banner.md)]

Este artigo descreve como atribuir ícones e títulos de etapas para fluxos de tarefas novos ou personalizados para o aplicativo móvel Warehouse Management.

As ilustrações a seguir mostram como os ícones e títulos de etapas aparecem no aplicativo móvel Warehouse Management.

![Exemplo de um ícone e um título de etapa no aplicativo móvel Warehouse Management.](media/step-icon-example.png "Exemplo de um ícone e um título de etapa no aplicativo móvel Warehouse Management")

## <a name="turn-this-feature-on-or-off"></a>Ativar ou desativar este recurso

Para usar a funcionalidade descrita neste artigo, o recurso *Configurações de usuário, ícones e títulos de etapas para o novo aplicativo de depósito* deve estar ativado para o seu sistema. A partir do Supply Chain Management 10.0.25, este recurso é obrigatório e não pode ser desativado. Se você estiver executando uma versão anterior à 10.0.25, os administradores poderão ativar ou desativar essa funcionalidade procurando o recurso *Configurações de usuário, ícones e títulos de etapas do novo aplicativo de depósito* no espaço de trabalho [Gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

## <a name="standard-step-ids-classes-and-icons"></a>IDs, classes e ícones de etapa padrão

Cada etapa em um fluxo de tarefa é identificada por uma ID de etapa e cada ID de etapa possui uma classe de etapa correspondente. O ícone e o título da etapa são especificados em cada classe da etapa.

### <a name="step-ids-and-step-classes"></a><a name="step-ids-classes"></a>IDs de etapa e classes de etapa

A tabela a seguir lista cada ID de etapa que está disponível atualmente e sua classe de etapa correspondente. O nome de controle do campo de entrada principal é usado como a ID da etapa.

Para ter um exemplo que mostra como essas IDs e classes de etapa são usadas, consulte a implementação do método `WHSMobileAppStepInfoBuilder.stepId()` na seção [Exemplo: Atribuir ícones e títulos de etapa para um fluxo personalizado](#example) a seguir neste artigo.

| ID da etapa | Classe da etapa |
|-|-|
| BatchDisposition | WHSMobileAppStepBatchDisposition |
| Transportadora | WHSMobileAppStepCarrier |
| CatchWeight | WHSMobileAppStepCatchWeight |
| CatchWeightQtyOutboundWeight | WHSMobileAppStepCatchWeight |
| CatchWeightTag | WHSMobileAppStepCatchWeightTag |
| CatchWeightTagWeight | WHSMobileAppStepCatchWeightTagWeight |
| ChangeWarehouseSuccess | WHSMobileAppStepChangeWarehouseSuccess |
| CheckDigit | WHSMobileAppStepCheckDigit |
| ClusterId | WHSMobileAppStepClusterId |
| ClusterPickQtyVerification | WHSMobileAppStepQtyVerification |
| ClusterPosition | WHSMobileAppStepClusterPosition |
| ConfigId | WHSMobileAppStepConfigId |
| Confirmação | WHSMobileAppStepConfirmation |
| ConsolidateFromLicensePlateId | WHSMobileAppStepConsolidateFromLicensePlateId |
| ConsolidateLPConfirmation | WHSMobileAppStepConsolidateLPConfirmation |
| ConsolidateToLicensePlateId | WHSMobileAppStepConsolidateToLicensePlateId |
| ContainerType | WHSMobileAppStepContainerType |
| CountingReasonCode | WHSMobileAppStepCountingReasonCode |
| CycleCountingAddLPOrFinish | WHSMobileAppStepCycleCountingAddLPOrFinish |
| CycleCountQty1 | WHSMobileAppStepCycleCountQty |
| CycleCountQty2 | WHSMobileAppStepCycleCountQty |
| CycleCountQty3 | WHSMobileAppStepCycleCountQty |
| CycleCountQty4 | WHSMobileAppStepCycleCountQty |
| Disposition | WHSMobileAppStepDisposition |
| DriverCheckInConfirmation | WHSMobileAppStepDriverCheckInConfirmation |
| DriverCheckInId | WHSMobileAppStepDriverCheckInId |
| DriverCheckOutConfirmation | WHSMobileAppStepDriverCheckOutConfirmation |
| DriverCheckOutId | WHSMobileAppStepDriverCheckOutId |
| ExpDate | WHSMobileAppStepExpDate |
| FromBatchDisposition | WHSMobileAppStepFromBatchDisposition |
| FromInventoryStatus | WHSMobileAppStepInventoryStatusFrom |
| FullQty | WHSMobileAppStepFullQty |
| InboundPut | WHSMobileAppStepInboundPut |
| InventBatchId | WHSMobileAppStepBatch |
| InventColorId | WHSMobileAppStepInventColorId |
| InventLocation | WHSMobileAppStepInventLocation |
| InventLocationId | WHSMobileAppStepWarehouse |
| InventSerialId | WHSMobileAppStepInventSerialId |
| InventSizeId | WHSMobileAppStepInventSizeId |
| InventStatusId | WHSMobileAppStepInventStatus |
| InventStyleId | WHSMobileAppStepInventStyleId |
| InventVersionId | WHSMobileAppStepInventVersionId |
| ItemId | WHSMobileAppStepItem |
| ITMContainerID | ITMMobileAppStepContainerId |
| ITMShipmentID | ITMMobileAppStepShipmentId |
| KanbanCardId | WHSMobileAppStepKanbanCard |
| KanbanCardToEmpty | WHSMobileAppStepKanbanCardToEmpty |
| KanbanOrCardId | WHSMobileAppStepKanbanCard |
| LicensePlateId | WHSMobileAppStepLicensePlate |
| LoadId | WHSMobileAppStepLoadId |
| LocationLicensePlatePosition | WHSMobileAppStepLocationLicensePlatePosition |
| LocOrLP | WHSMobileAppStepLocOrLP |
| LocOrLP_From | WHSMobileAppStepLocOrLPFrom |
| LocOrLP_To | WHSMobileAppStepLocOrLPTo |
| LocOrLPCheck | WHSMobileAppStepLocOrLPCheck |
| LocVerification | WHSMobileAppStepLocVerification |
| LPAdjustIn | WHSMobileAppStepLPAdjustIn |
| LPBreakChildLP | WHSMobileAppStepLPBreakChildLP |
| LPBreakParentLP | WHSMobileAppStepLPBreakParentLP |
| LPBuildChildLP | WHSMobileAppStepLPBuildChildLP |
| LPBuildParentLP | WHSMobileAppStepLPBuildParentLP |
| LPVerification | WHSMobileAppStepLPVerification |
| MergeContainerId | WHSMobileAppStepMergeContainerId |
| MixedLPLineNum | WHSMobileAppStepMixedLPLineNum |
| MobileDeviceQueueMessageCollectionIdentifierId | WHSMobileAppStepSelectOrder |
| MovementConfirmCancel | WHSMobileAppStepMovementConfirmCancel |
| NewCaptureWeight | WHSMobileAppStepCatchWeight |
| NewQty | WHSMobileAppStepNewQty |
| OutboundCatchWeightTag | WHSMobileAppStepCatchWeightTag |
| OutboundPut | WHSMobileAppStepOutboundPut |
| OutboundWeight | WHSMobileAppStepCatchWeight |
| OverridePutNewLocation | WHSMobileAppStepOverridePutNewLocation |
| PieceByPieceConfirmation | WHSMobileAppStepQtyVerification |
| POLineNum | WHSMobileAppStepPOLineNum |
| Nº da OC | WHSMobileAppStepPONum |
| PositionFull | WHSMobileAppStepPositionFull |
| PositionFullQty | WHSMobileAppStepPositionFullQty |
| Concentração | WHSMobileAppStepPotency |
| PrinterName | WHSMobileAppStepPrinterName |
| ProdId | WHSMobileAppStepProdId |
| ProdLastPalletConfirmation | WHSMobileAppStepProdLastPalletConfirmation |
| ProductConfirmation | WHSMobileAppStepProductConfirmation |
| ProductionScrapConfirmation | WHSMobileAppStepProductionScrapConfirmation |
| Colocar | WHSMobileAppStepPut |
| PutawayClusterId | WHSMobileAppStepPutawayClusterId |
| Qtd. | WHSMobileAppStepQty |
| QtyAdjust | WHSMobileAppStepQtyAdjust |
| QtyShort | WHSMobileAppStepQtyShort |
| QtyToConsume | WHSMobileAppStepQtyToConsume |
| QtyToPick | WHSMobileAppStepQtyToPick |
| QtyToPut | WHSMobileAppStepQtyToPut |
| QtyToScrap | WHSMobileAppStepQtyToScrap |
| QtyVerification | WHSMobileAppStepQtyVerification |
| QtyWithScanningLimit | WHSMobileAppStepQtyAdjust |
| ReasonString | WHSMobileAppStepReasonString |
| RecvLocationId | WHSMobileAppStepRecvLocationId |
| RemoveContainerId | WHSMobileAppStepRemoveContainerId |
| ReprintLabelConfirmation | WHSMobileAppStepReprintLabelConfirmation |
| RMANum | WHSMobileAppStepRMANum |
| ShortPickReason | WHSMobileAppStepShortPickReason |
| SortConOrLP | WHSMobileAppStepSortConOrLP |
| SortLicensePlateId | WHSMobileAppStepSortLicensePlateId |
| SortPositionId | WHSMobileAppStepSortPositionId |
| SortVerification | WHSMobileAppStepSortVerification |
| StartLocationId | WHSMobileAppStepStartLocationId |
| StartProdOrderConfirmation | WHSMobileAppStepStartProdOrderConfirmation |
| TargetLicensePlateId | WHSMobileAppStepTargetLicensePlateId |
| TOLineNum | WHSMobileAppStepTOLineNum |
| ToLocation | WHSMobileAppStepToLocation |
| TONum | WHSMobileAppStepTONum |
| ToWarehouse | WHSMobileAppStepWarehouseTo |
| TransportLoadId | WHSMobileAppStepTransportLoadId |
| WaveLabelId | WHSMobileAppStepWaveLabelId |
| WaveLblQty | WHSMobileAppStepWaveLblQty |
| Peso | WHSMobileAppStepWeight |
| WeightToConsume | WHSMobileAppStepWeightToConsume |
| WHSAdjustmentType | WHSMobileAppStepWHSAdjustmentType |
| WHSReceivingException | WHSMobileAppStepWHSReceivingException |
| WHSWorkException | WHSMobileAppStepWHSWorkException |
| WHSWorkLicensePlateId | WHSMobileAppStepWorkLicensePlateId |
| WMSLocationId | WHSMobileAppStepLocation |
| WorkId | WHSMobileAppStepWorkId |
| WorkIdToCancel | WHSMobileAppStepWorkIdToCancel |
| WorkLPIdPutawayCluster | WHSMobileAppStepWorkLPIdPutawayCluster |
| WorkPoolId | WHSMobileAppStepWorkPoolId |
| ZoneId | WHSMobileAppStepZoneId |

### <a name="available-step-icons"></a><a name="step-icons"></a>Ícones de etapas disponíveis

O sistema inclui uma coleção de ícones de etapas padrão que você também pode usar para suas etapas personalizadas. No momento, não é possível carregar ícones de etapas personalizadas. Portanto, você deve sempre selecionar um dos ícones de etapa padrão.

A tabela a seguir mostra cada ícone de etapa padrão atualmente disponível e seu nome.

<table>
<tbody>
<tr>
<td><img src="media/step-icons-about.png" alt="About step icon" title="Sobre o ícone de etapa"><br>Sobre</td>
<td><img src="media/step-icons-add-lp.png" alt="Add license plate or item step icon" title="Adicionar placa de licença ou ícone de etapa de item"><br>AddLpOrItem</td>
<td><img src="media/step-icons-batch-disposition.png" alt="Batch disposition step icon" title="Ícone de etapa de disposição de lote"><br>BatchDisposition</td>
<td><img src="media/step-icons-carrier.png" alt="Carrier step icon" title="Ícone de etapa da operadora"><br>Transportadora</td>
</tr>
<tr>
<td><img src="media/step-icons-cw-tag.png" alt="Catch weight tag step icon" title="Ícone de etapa do rótulo de peso variável"><br>CatchWeightTag</td>
<td><img src="media/step-icons-cw-tag-weight.png" alt="Catch weight tag weight step icon" title="Ícone de etapa de peso do rótulo de peso variável"><br>CatchWeightTagWeight</td>
<td><img src="media/step-icons-check-digit.png" alt="Check digit step icon" title="Ícone de etapa de dígito de verificação"><br>CheckDigit</td>
<td><img src="media/step-icons-check-in-out.png" alt="Check in or out ID step icon" title="Ícone de etapa de ID de check-in ou check-out"><br>CheckInOutId</td>
</tr>
<tr>
<td><img src="media/step-icons-child-lp.png" alt="Child license plate step icon" title="Ícone de etapa da placa de licença secundária"><br>ChildLP</td>
<td><img src="media/step-icons-cluster-id.png" alt="Cluster ID step icon" title="Ícone de etapa de ID de cluster"><br>ClusterId</td>
<td><img src="media/step-icons-cluster-position.png" alt="Cluster position step icon" title="Ícone de etapa de posição de cluster"><br>ClusterPosition</td>
<td><img src="media/step-icons-config-id.png" alt="Config ID step icon" title="Ícone de etapa de ID de configuração"><br>ConfigId</td>
</tr>
<tr>
<td><img src="media/step-icons-configured-field.png" alt="Configured field step icon" title="Ícone de etapa de campo configurado"><br>ConfiguredField</td>
<td><img src="media/step-icons-con-lp.png" alt="Con or LP step icon" title="Ícone de etapa Con ou LP"><br>ConOrLP</td>
<td><img src="media/step-icons-consolidate-from-LP.png" alt="Consolidate from license plate ID step icon" title="ID de etapa Consolidar a partir da ID de placa de licença"><br>ConsolidateFromLicensePlateID</td>
<td><img src="media/step-icons-consolidate-to-LP.png" alt="Consolidate to license plate ID step icon" title="ID de etapa Consolidar para a ID de placa de licença"><br>ConsolidateToLicensePlateID</td>
</tr>
<tr>
<td><img src="media/step-icons-container-type.png" alt="Container type step icon" title="Ícone de etapa do tipo de contêiner"><br>ContainerType</td>
<td><img src="media/step-icons-counting.png" alt="Counting step icon" title="Ícone de etapa de contagem"><br>Contagem</td>
<td><img src="media/step-icons-counting-reason.png" alt="Counting reason code step icon" title="Ícone de etapa do código do motivo de contagem"><br>CountingReasonCode</td>
<td><img src="media/step-icons-country-origin.png" alt="Country of origin code step icon" title="Ícone de etapa do código do país de origem"><br>CountryOfOrigin</td>
</tr>
<tr>
<td><img src="media/step-icons-disposition.png" alt="Disposition step icon" title="Ícone da etapa de disposição"><br>Disposition</td>
<td><img src="media/step-icons-done.png" alt="Done step icon" title="Ícone de etapa concluída"><br>Concluídos</td>
<td><img src="media/step-icons-driver-check-in-confirmation.png" alt="Driver check in confirmation step icon" title="Ícone da etapa de confirmação de verificação do motorista"><br>DriverCheckInConfirmation</td>
<td><img src="media/step-icons-driver-check-in-id.png" alt="Driver check in ID step icon" title="Ícone de etapa de verificação de identificação do motorista"><br>DriverCheckInId</td>
</tr>
<tr>
<td><img src="media/step-icons-driver-check-out-id.png" alt="Driver check out ID step icon" title="Ícone de etapa de verificação de registro de saída do motorista"><br>DriverCheckOutId</td>
<td><img src="media/step-icons-exp-date.png" alt="Expiration date step icon" title="Ícone de etapa da data de expiração"><br>ExpDate</td>
<td><img src="media/step-icons-field.png" alt="Field step icon" title="Ícone de etapa de campo"><br>Campo</td>
<td><img src="media/step-icons-from-batch.png" alt="From batch disposition step icon" title="Ícone da etapa Da disposição em lote"><br>FromBatchDisposition</td>
</tr>
<tr>
<td><img src="media/step-icons-from-inventory-status.png" alt="From inventory status step icon" title="Ícone de etapa Do status de estoque"><br>FromInventoryStatus</td>
<td><img src="media/step-icons-id-attribute.png" alt="ID attribute step icon" title="Ícone de etapa de atributo de ID"><br>IdAttribute</td>
<td><img src="media/step-icons-invent-batch-id.png" alt="Inventory batch ID step icon" title="Ícone de etapa de ID de lote de estoque"><br>InventBatchID</td>
<td><img src="media/step-icons-invent-color-id.png" alt="Inventory color ID step icon" title="Ícone de etapa de ID da cor de estoque"><br>InventColorID</td>
</tr>
<tr>
<td><img src="media/step-icons-invent-location.png" alt="Inventory location step icon" title="Ícone de etapa de localização de estoque"><br>InventLocation</td>
<td><img src="media/step-icons-invent-serial-id.png" alt="Inventory serial ID step icon" title="Ícone de etapa de ID da série de estoque"><br>InventSerialID</td>
<td><img src="media/step-icons-invent-size-id.png" alt="Inventory size ID step icon" title="Ícone de etapa de ID do tamanho do estoque"><br>InventSizeID</td>
<td><img src="media/step-icons-invent-status-id.png" alt="Inventory status ID step icon" title="Ícone de etapa da ID do status do estoque"><br>InventStatusID</td>
</tr>
<tr>
<td><img src="media/step-icons-invent-style-id.png" alt="Inventory style ID step icon" title="Ícone de etapa de ID do estilo do estoque"><br>InventStyleID</td>
<td><img src="media/step-icons-invent-version-id.png" alt="Inventory version ID step icon" title="Ícone de etapa da ID da versão do estoque"><br>InventVersionID</td>
<td><img src="media/step-icons-item-id.png" alt="Item ID step icon" title="Ícone de etapa de ID de item"><br>ItemID</td>
<td><img src="media/step-icons-itm-contianer-id.png" alt="ITM container ID step icon" title="Ícone de etapa da ID do contêiner ITM"><br>ITMContainerID</td>
</tr>
<tr>
<td><img src="media/step-icons-itm-shipment-id.png" alt="ITM shipment ID step icon" title="Ícone de etapa da ID de remessa ITM"><br>ITMShipmentID</td>
<td><img src="media/step-icons-kanban-card-id.png" alt="Kanban card ID step icon" title="Ícone de etapa de identificação do cartão kanban"><br>KanbanCardID</td>
<td><img src="media/step-icons-kanban-or-card-id.png" alt="Kanban or card ID step icon" title="Ícone de etapa de identificação do cartão ou kanban"><br>KanbanOrCardID</td>
<td><img src="media/step-icons-license-plate-id.png" alt="License plate ID step icon" title="Ícone de etapa da ID da placa de licença"><br>LicensePlateID</td>
</tr>
<tr>
<td><img src="media/step-icons-load-id.png" alt="Load ID step icon" title="Ícone de etapa de ID de carregamento"><br>LoadId</td>
<td><img src="media/step-icons-location-lp-pos.png" alt="Location license plate position step icon" title="Ícone de etapa de posição de placa de licença de localização"><br>LocationLicensePlatePosition</td>
<td><img src="media/step-icons-location-or-lp.png" alt="Location or license plate step icon" title="Ícone da etapa de localização ou placa de licença"><br>LocOrLP</td>
<td><img src="media/step-icons-location-or-lp-check.png" alt="Location or license plate check step icon" title="Ícone da etapa de verificação de localização ou placa de licença"><br>LocOrLPCheck</td>
</tr>
<tr>
<td><img src="media/step-icons-location-or-lp-from.png" alt="Location or license plate from step icon" title="Ícone da etapa de a partir de localização ou placa de licença"><br>LocOrLPFrom</td>
<td><img src="media/step-icons-location-or-lp-to.png" alt="Location or license plate to step icon" title="Ícone da etapa de para localização ou placa de licença"><br>LocOrLPTo</td>
<td><img src="media/step-icons-long-process-complete.png" alt="Long process completed step icon" title="Ícone de etapa de processo longo concluído"><br>LongProcessCompleted</td>
<td><img src="media/step-icons-lp-break-parent.png" alt="LP break parent LP step icon" title="Ícone de etapa de LP principal de interrupção de LP"><br>LPBreakParentLP</td>
</tr>
<tr>
<td><img src="media/step-icons-merge-container.png" alt="Merge container ID step icon" title="Ícone de etapa da ID de mesclagem de contêiner"><br>MergeContainerId</td>
<td><img src="media/step-icons-mixed-lp-line.png" alt="Mixed license plate line number step icon" title="Ícone de etapa do número de linha da placa de licença"><br>MixedLPLineNum</td>
<td><img src="media/step-icons-outbound-weight.png" alt="Outbound weight step icon" title="Ícone de etapa de peso de saída"><br>OutboundWeight</td>
<td><img src="media/step-icons-owner.png" alt="Owner step icon" title="Ícone de etapa de proprietário"><br>Proprietário</td>
</tr>
<tr>
<td><img src="media/step-icons-parent-lp.png" alt="Parent license plate step icon" title="Ícone de etapa da placa de licença principal"><br>ParentLP</td>
<td><img src="media/step-icons-please-confirm.png" alt="Please confirm step icon" title="Ícone de etapa de confirmação"><br>PleaseConfirm</td>
<td><img src="media/step-icons-po-line-num.png" alt="Purchase order line number step icon" title="Ícone de etapa de número de linha da ordem de compra"><br>POLineNum</td>
<td><img src="media/step-icons-po-num.png" alt="Purchase order number step icon" title="Ícone de etapa de número da ordem de compra"><br>Nº da OC</td>
</tr>
<tr>
<td><img src="media/step-icons-position-full.png" alt="Position full step icon" title="Ícone de etapa de posição completa"><br>PositionFull</td>
<td><img src="media/step-icons-potency.png" alt="Potency step icon" title="Ícone de etapa de concentração"><br>Concentração</td>
<td><img src="media/step-icons-printer-name.png" alt="Printer name step icon" title="Ícone de etapa de nome da impressora"><br>PrinterName</td>
<td><img src="media/step-icons-prod-id.png" alt="Prod ID step icon" title="Ícone de etapa de ID de produção"><br>ProdId</td>
</tr>
<tr>
<td><img src="media/step-icons-product-confirm.png" alt="Product confirmation step icon" title="Ícone de etapa de confirmação do produto"><br>ProductConfirmation</td>
<td><img src="media/step-icons-put.png" alt="Put step icon" title="Ícone de etapa de colocação"><br>Colocar</td>
<td><img src="media/step-icons-putaway-cluster-id.png" alt="Putaway cluster ID step icon" title="Ícone de etapa de ID de cluster de armazenamento"><br>PutawayClusterId</td>
<td><img src="media/step-icons-qty.png" alt="Quantity step icon" title="Ícone de etapa de quantidade"><br>Qtd.</td>
</tr>
<tr>
<td><img src="media/step-icons-qty-adjust-in.png" alt="Quantity adjust in step icon" title="Ícone de etapa de ajuste de quantidade em"><br>QtyAdjustIn</td>
<td><img src="media/step-icons-qty-short.png" alt="Quantity short step icon" title="Ícone de etapa de quantidade curta"><br>QtyShort</td>
<td><img src="media/step-icons-qty-to-consume.png" alt="Quantity to consume step icon" title="Ícone de etapa de quantidade para consumo"><br>QtyToConsume</td>
<td><img src="media/step-icons-qty-to-put.png" alt="Quantity to put step icon" title="Ícone de etapa de quantidade para colocação"><br>QtyToPut</td>
</tr>
<tr>
<td><img src="media/step-icons-qty-to-scrap.png" alt="Quantity to scrap step icon" title="Ícone de etapa de quantidade para sucata"><br>QtyToScrap</td>
<td><img src="media/step-icons-qty-confirmation.png" alt="Quantity confirmation step icon" title="Ícone de etapa de confirmação da quantidade"><br>QuantityConfirmation</td>
<td><img src="media/step-icons-raf-end-job.png" alt="Report as finished end job step icon" title="Ícone de etapa de relatório como trabalho final concluído"><br>RAFEndJob</td>
<td><img src="media/step-icons-recv-loc-id.png" alt="Receive location ID step icon" title="Ícone de etapa de ID de recebimento de localização"><br>RecvLocationID</td>
</tr>
<tr>
<td><img src="media/step-icons-remove-container-id.png" alt="Remove container ID step icon" title="Ícone de etapa da ID de remoção de contêiner"><br>RemoveContainerID</td>
<td><img src="media/step-icons-rma-no.png" alt="RMA number step icon" title="Ícone de etapa de número de ADM"><br>RMANum</td>
<td><img src="media/step-icons-select-order.png" alt="Select order step icon" title="Ícone de etapa de seleção de ordem"><br>SelectOrder</td>
<td><img src="media/step-icons-short-pick-reason.png" alt="Short pick reason step icon" title="Ícone de etapa do motivo de separação insuficiente"><br>ShortPickReason</td>
</tr>
<tr>
<td><img src="media/step-icons-sort-position-id.png" alt="Sort position ID step icon" title="Ícone de etapa de ID de posição insuficiente"><br>SortPositionId</td>
<td><img src="media/step-icons-target-lp-id.png" alt="Target license plate ID step icon" title="Ícone de etapa da ID da placa de licença alvo"><br>TargetLicensePlateId</td>
<td><img src="media/step-icons-to-line-no.png" alt="To line number step icon" title="Ícone de etapa de para número de linha"><br>ToLineNum</td>
<td><img src="media/step-icons-to-location.png" alt="To location step icon" title="Ícone de etapa para localização"><br>ToLocation</td>
</tr>
<tr>
<td><img src="media/step-icons-to-number.png" alt="To number step icon" title="Ícone de etapa para número"><br>ToNum</td>
<td><img src="media/step-icons-to-warehouse.png" alt="To warehouse step icon" title="Ícone de etapa para depósito"><br>ToWarehouse</td>
<td><img src="media/step-icons-tranport-load-id.png" alt="Transport load ID step icon" title="Ícone de etapa de ID de carga de transporte"><br>TransportLoadId</td>
<td><img src="media/step-icons-vendor-batch-id.png" alt="Vendor batch ID step icon" title="Ícone de etapa de ID de lote de fornecedor"><br>VendBatchId</td>
</tr>
<tr>
<td><img src="media/step-icons-wave-label-id.png" alt="Wave label ID step icon" title="Ícone de etapa da ID da etiqueta do ciclo"><br>WaveLabelId</td>
<td><img src="media/step-icons-wave-label-qty.png" alt="Wave label quantity step icon" title="Ícone de etapa da quantidade da etiqueta do ciclo"><br>WaveLblQty</td>
<td><img src="media/step-icons-weight.png" alt="Weight step icon" title="Ícone de etapa de peso"><br>Peso</td>
<td><img src="media/step-icons-weight-to-consume.png" alt="Weight to consume step icon" title="Ícone de etapa do peso para consumo"><br>WeightToConsume</td>
</tr>
<tr>
<td><img src="media/step-icons-whs-adjustment-type.png" alt="WHS adjustment type step icon" title="Ícone de etapa do tipo de ajuste WHS"><br>WHSAdjustmentType</td>
<td><img src="media/step-icons-whs-receiving-exception.png" alt="WHS receiving exception step icon" title="Ícone de etapa de exceção de recebimento WHS"><br>WHSReceivingException</td>
<td><img src="media/step-icons-wms-location-id.png" alt="WMS location ID step icon" title="Ícone de etapa de ID de localização WMS"><br>WMSLocationID</td>
<td><img src="media/step-icons-work-id.png" alt="Work ID step icon" title="Ícone de etapa de ID de trabalho"><br>WorkId</td>
</tr>
<tr>
<td><img src="media/step-icons-work-id-to-cancel.png" alt="Work ID to cancel step icon" title="Ícone de etapa de ID de trabalho para cancelamento"><br>WorkIdToCancel</td>
<td><img src="media/step-icons-work-lp-id.png" alt="Work license plate ID step icon" title="Ícone de etapa da ID da placa de licença de trabalho"><br>WorkLicensePlateId</td>
<td><img src="media/step-icons-work-lp-putaway-cluster.png" alt="Work license plate ID putaway cluster step icon" title="Ícone de etapa de cluster de armazenamento da ID da placa de licença de trabalho"><br>WorkLPIDPutawayCluster</td>
<td><img src="media/step-icons-work-pool-id.png" alt="Work pool ID step icon" title="Ícone de etapa de ID de pool de trabalho"><br>WorkPoolID</td>
</tr>
<tr>
<td><img src="media/step-icons-zone-pool-id.png" alt="Zone ID step icon" title="Ícone de etapa de ID de zona"><br>ZoneID</td>
<td></td>
<td></td>
<td></td>
</tr>
</tbody>
</table>

## <a name="example-assign-step-icons-and-titles-for-a-custom-flow"></a><a name="example"></a>Exemplo: Atribuir ícones e títulos de etapa para um fluxo personalizado

Este exemplo explica como configurar ícones e títulos de etapas para um fluxo de tarefa personalizado. O cenário é baseado em um exemplo de fluxo de tarefa personalizada que é apresentado e explorado em mais detalhes na seguinte postagem do blog: [Personalização do aplicativo móvel de depósito](https://cloudblogs.microsoft.com/dynamics365/it/2017/07/06/customizing-the-warehousing-mobile-app). O fluxo de tarefas funciona da seguinte maneira:

1. O aplicativo mostra uma página que solicita que o trabalhador forneça uma ID de contêiner (por exemplo, lendo um código de barras).
1. Se a ID do contêiner for válida, o aplicativo abre uma nova página que solicita ao trabalhador o peso. (Se a ID do contêiner não for válida, o trabalhador será redirecionado à primeira página.)
1. Quando o trabalhador insere um peso válido, o sistema armazena o peso e redireciona o trabalhador à primeira página.

A ilustração a seguir mostra esse fluxo de tarefa.

![Diagrama de fluxo de tarefas.](media/step-icons-example-task-flow.png "Diagrama de fluxo de tarefas")

### <a name="create-a-step-class-for-the-container-input-page"></a>Criar uma classe de etapa para a página de entrada do contêiner

A página de entrada do contêiner permite que o trabalhador faça a digitalização ou insira uma ID de contêiner.

![Página de entrada do contêiner.](media/step-icons-example-container-input.png "Página de entrada do contêiner")

Na página de entrada do contêiner, o nome do controle do campo de entrada é `ContainerId`. Como esse nome de controle não está na [lista de IDs de etapa](#step-ids-classes), você não encontrará uma etapa existente baseada nele. Portanto, você deve criar uma classe de etapa que representa a etapa. Veja aqui um exemplo.

```xpp
[WHSMobileAppStepId('ContainerId')]
final internal class WHSMobileAppStepContainerId extends WHSMobileAppStep
{
    private const WHSMobileAppStepIcon PopulationIcon = 'InventBatchID';
    private const WHSMobileAppStepTitle InputNotFilledTitle = "@WAX:WHSMobileAppStepContainerID_InputNotFilled"; //Scan a container
    protected void initValues()
    {
        defaultStepIcon = PopulationIcon;
        defaultStepTitle = InputNotFilledTitle;
    }
}
```

O identificador do ícone da etapa é armazenado no membro da classe `defaultStepIcon`, e o título da etapa é armazenado no membro da classe `defaultStepTitle`.

Para atribuir um ícone de etapa, defina `defaultStepIcon` para uma das IDs de ícone que estão listadas na seção [Ícones de etapas disponíveis](#step-icons) anteriormente neste artigo.

### <a name="use-a-standard-or-custom-step-icon-and-title-for-the-weight-input"></a>Usar um ícone de etapa padrão ou personalizado e um título para a entrada de peso

A página de entrada de peso permite que o trabalhador insira um peso.

![Página entrada de peso.](media/step-icons-example-weight-input.png "Página entrada de peso")

Na página de entrada de peso, o nome do controle do campo de entrada é `Weight`, que está na [lista de IDs de etapa](#step-ids-classes). Portanto, se o ícone e o título da etapa definidos na classe `WHSMobileAppStepWeight` são aceitáveis para você, não é necessário alterar nada nesta etapa.

No entanto, se você preferir usar um ícone ou título diferente para esta etapa, você pode substituir o método `stepId()` ou o método `stepInfo()` na classe de construtor. Cada fluxo de tarefa tem seu próprio construtor de informações de etapa.

#### <a name="override-the-stepid-method"></a>Substituir o método stepId()

O exemplo a seguir mostra uma maneira de modificar uma classe de construtor substituindo o método `stepId()`.

```xpp
[WHSWorkExecuteMode(WHSWorkExecuteMode:: WeighContainer)]
public class WHSMobileAppStepInfoBuilderWeighContainer extends WHSMobileAppStepInfoBuilder
{
    protected WHSMobileAppStepId stepId()
    {
        WHSMobileAppStepId stepIdLocal = super();
        if (stepIdLocal == 'Weight')
        {
            return 'NewWeight';
        }
        return stepIdLocal;
    }
}
```

Em seguida, você cria uma classe de etapa para a etapa `NewWeight`. O código deve ser semelhante ao código do exemplo `ContainerId` mostrado anteriormente neste artigo.

#### <a name="override-the-stepinfo-method"></a>Substituir o método stepInfo()

O exemplo a seguir mostra uma maneira de modificar uma classe de construtor substituindo o método `stepInfo()`.

```xpp
[WHSWorkExecuteMode(WHSWorkExecuteMode:: WeighContainer)]
public class WHSMobileAppStepInfoBuilderWeighContainer extends WHSMobileAppStepInfoBuilder
{
    protected WHSMobileAppStepInfo stepInfo()
    {
        if (stepId != 'Weight')
        {
            return super();
        }
        WHSMobileAppStepInfo stepInfo = WHSMobileAppStepInfo::construct();
        stepInfo.parmStepIcon('NewIcon');
        stepInfo.parmStepTitle('NewTitle');
        return stepInfo;
    }
}
```

Depois, você constrói um objeto `WHSMobileAppStepInfo` e define o ícone e/ou título diretamente.

## <a name="additional-resources"></a>Recursos adicionais

- [Instalar e conectar o aplicativo móvel Gerenciamento de Depósito](install-configure-warehouse-management-app.md)
- [Configurações do usuário do dispositivo móvel](mobile-device-user-settings.md)
