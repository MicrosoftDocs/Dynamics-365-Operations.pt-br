---
title: Não é possível confirmar uma remessa porque os itens não foram separados
description: Não é possível confirmar uma remessa porque os itens não foram separados
author: perlynne
ms.date: 04/21/2021
ms.topic: troubleshooting
ms.search.form: WHSLoadTable_WHSShipConfirm,WHSLoadPlanningListPage_WHSShipConfirm,WHSLoadPlanningWorkbench_WHSShipConfirm,WHSTransportLoad_WHSShipConfirm,WHSShipPlanningListPage_WHSShipConfirm,WHSShipmentDetails_WHSShipConfirm,WHSWorkTable_WHSShipConfirm,WHSWorkTableListPage_WHSShipConfirm,Dialog_WHSOutboundShipConfirmController_WHSOutboundShipConfirm
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: lbc
ms.search.validFrom: 2021-04-21
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 23a517e7769dc86ebec30e4f17c62172a6ad8801
ms.sourcegitcommit: cd9016e9787169cb800889d335b9c5919ddbe4af
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2021
ms.locfileid: "5938420"
---
# <a name="you-cant-confirm-a-shipment-because-items-havent-been-picked"></a>Não é possível confirmar uma remessa porque os itens não foram separados

Código de erro: LoadNotPickedAndMovedToFinalShippingLocation

## <a name="symptoms"></a>Sintomas

Ao tentar confirmar uma remessa, o sistema mostra a seguinte mensagem de erro:

> Alguns dos itens necessários para carregar %1 ainda não foram separados e movidos para a localização de remessa final.

Portanto, não é possível confirmar a remessa da carga.

## <a name="cause"></a>Causa

A carga ou a remessa não pode ser confirmada no estado atual porque pode existir uma das seguintes condições:

- O trabalho relacionado ainda não foi separado e movido para o local de remessa final.
- A quantidade de trabalho separada não corresponde à quantidade de trabalho criada na linha de carga.

## <a name="resolution"></a>Resolução

Verifique as ordens de venda relacionadas ou as ordens de transferência para a carga ou remessa. Verifique se todos os trabalhos relacionados foram concluídos no local de remessa final e se as quantidades coincidem.

1. Acesse **Gerenciamento de depósito \> Cargas \> Todas as cargas**.
1. Selecione a carga para a qual a remessa não pode ser confirmada.
1. Na FastTab **Linhas de carga**, selecione a linha de carga.
1. Anote o valor do campo **Quantidade de trabalho criado**.
1. No Painel de Ações, na guia **Cargas**, no grupo **Informações relacionadas**, selecione **Trabalho**.
1. Verifique se o trabalho foi concluído no local de remessa final e se a quantidade de trabalho separada corresponde à quantidade de trabalho criada na linha de carga.
1. Repita este procedimento para todas as linhas de carga para garantir que todos os critérios sejam atendidos.
