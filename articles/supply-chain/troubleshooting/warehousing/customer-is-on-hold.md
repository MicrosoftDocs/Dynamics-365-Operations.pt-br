---
title: Não é possível confirmar uma remessa porque o cliente está em espera
description: Não é possível confirmar uma remessa porque o cliente está em espera.
author: GalynaFedorova
ms.date: 07/30/2021
ms.topic: troubleshooting
ms.search.form: WHSLoadTable_WHSShipConfirm,WHSLoadPlanningListPage_WHSShipConfirm,WHSLoadPlanningWorkbench_WHSShipConfirm,WHSTransportLoad_WHSShipConfirm,WHSShipPlanningListPage_WHSShipConfirm,WHSShipmentDetails_WHSShipConfirm,WHSWorkTable_WHSShipConfirm,WHSWorkTableListPage_WHSShipConfirm,Dialog_WHSOutboundShipConfirmController_WHSOutboundShipConfirm
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: v-gfedorova
ms.search.validFrom: 2021-07-30
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: 82b28e7cfd8c88e453cdd09398f5a92f605eab15a17d33defa0b9729a53c05b6
ms.sourcegitcommit: fa5ff2a0822aac16b518a2aea0d3389f79793390
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/07/2021
ms.locfileid: "7012137"
---
# <a name="you-cant-confirm-a-shipment-because-the-customer-is-on-hold"></a>Não é possível confirmar uma remessa porque o cliente está em espera

Código de erro: WAX:CustomerOnHoldShipmentCannotBeConfirmed

## <a name="symptoms"></a>Sintomas

Ao tentar confirmar uma remessa, o sistema mostra a seguinte mensagem de erro:

> A remessa %1 não pode ser confirmada porque o cliente está em espera para %2.

Portanto, não é possível confirmar a remessa da carga.

## <a name="cause"></a>Causa

A conta do cliente da carga ou remessa está em espera. Portanto, o status do cliente impede a confirmação de remessa.

## <a name="resolution"></a>Resolução

Use o procedimento a seguir para desbloquear a conta do cliente.

1. Ir para **Contas recebíveis \> Clientes \> Todos os clientes**.
1. Abra a conta de cliente para a qual a remessa não pode ser confirmada.
1. Na FastTab **Crédito e cobranças**, defina o campo **Faturamento e entrega em espera** como *Não*.
1. Repita este procedimento para todos os clientes bloqueados para a carga.
