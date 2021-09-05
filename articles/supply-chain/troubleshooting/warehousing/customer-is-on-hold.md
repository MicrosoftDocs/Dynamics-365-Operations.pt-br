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
ms.openlocfilehash: 801778fc8f04b106bf168a3dcd5a89767a837740
ms.sourcegitcommit: b9c2798aa994e1526d1c50726f807e6335885e1a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/13/2021
ms.locfileid: "7344255"
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
