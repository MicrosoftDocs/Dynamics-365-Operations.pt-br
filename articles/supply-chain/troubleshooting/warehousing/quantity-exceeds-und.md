---
title: Não é possível confirmar uma remessa porque a quantidade excede a porcentagem de entrega insuficiente
description: Não é possível confirmar uma remessa porque a quantidade excede a porcentagem de entrega insuficiente
author: perlynne
ms.date: 04/21/2021
ms.topic: troubleshooting
ms.search.form: WHSLoadTable_WHSShipConfirm,WHSLoadPlanningListPage_WHSShipConfirm,WHSLoadPlanningWorkbench_WHSShipConfirm,WHSTransportLoad_WHSShipConfirm,WHSShipPlanningListPage_WHSShipConfirm,WHSShipmentDetails_WHSShipConfirm,WHSWorkTable_WHSShipConfirm,WHSWorkTableListPage_WHSShipConfirm,Dialog_WHSOutboundShipConfirmController_WHSOutboundShipConfirm,WHSContainerCloseDiag_WHSShipConfirm
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: lbc
ms.search.validFrom: 2021-04-21
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 625003731485329b93f5f9454ccece580c889613
ms.sourcegitcommit: c2c6d687a89bc1534c029109315c23e92865b63b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/31/2021
ms.locfileid: "6123810"
---
# <a name="you-cant-confirm-a-shipment-because-the-quantity-exceeds-the-underdelivery-percentage"></a>Não é possível confirmar uma remessa porque a quantidade excede a porcentagem de entrega insuficiente

Código de erro: WAX1686

## <a name="symptoms"></a>Sintomas

Ao tentar confirmar uma remessa, o sistema mostra a seguinte mensagem de erro:

> Não foi possível confirmar a remessa da carga %1 porque a quantidade do item %2 excede a porcentagem definida de entrega insuficiente.

Portanto, não é possível confirmar a remessa da carga.

## <a name="cause"></a>Causa

A quantidade da carga ou remessa foi apenas parcialmente separada. A quantidade é atualmente inferior à quantidade separada por uma porcentagem que está fora da porcentagem de entrega insuficiente permitida.

## <a name="resolution"></a>Resolução

Para corrigir esse problema, execute uma das seguintes tarefas:

- Defina a quantidade da linha de carga.
- Defina a porcentagem de entrega insuficiente.

### <a name="set-the-load-line-quantity"></a>Definir a quantidade da linha de carga

Para definir a quantidade da linha de carga, siga estas etapas.

1. Acesse **Gerenciamento de depósito \> Cargas \> Todas as cargas**.
1. Selecione a carga para a qual a remessa não pode ser confirmada.
1. Na FastTab **Linhas de carga**, selecione a linha de carga do item que excede a porcentagem de entrega insuficiente.
1. Na FastTab **Detalhes da linha**, selecione **Ordem**.
1. No campo **Quantidade**, defina o valor como a quantidade separada (ou seja, como o valor **Quantidade de trabalho criado**), de forma que a confirmação da remessa possa ocorrer.

### <a name="set-the-underdelivery-percentage"></a>Definir a porcentagem de entrega insuficiente

Para definir a porcentagem de entrega insuficiente, siga estas etapas.

1. Acesse **Gerenciamento de depósito \> Cargas \> Todas as cargas**.
1. Selecione a carga para a qual a remessa não pode ser confirmada.
1. Na FastTab **Linhas de carga**, selecione a linha de carga do item que excede a porcentagem de entrega insuficiente.
1. Na FastTab **Detalhes da linha**, selecione **Geral**.
1. No campo **Entrega insuficiente**, defina o valor como uma porcentagem maior que acomode a quantidade separada em relação à quantidade de carga, de forma que a confirmação da remessa possa ocorrer.
