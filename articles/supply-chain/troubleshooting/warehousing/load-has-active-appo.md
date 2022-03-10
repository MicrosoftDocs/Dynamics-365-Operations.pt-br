---
title: Não é possível confirmar uma remessa devido a um problema com o calendário
description: Não é possível confirmar uma remessa devido a um problema com o calendário
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
ms.openlocfilehash: 8aae45beeef1934760d620874897f46a1cf901995e2b83e148a1d56898d9c717
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6735935"
---
# <a name="you-cant-confirm-a-shipment-because-of-an-issue-with-the-calendar"></a>Não é possível confirmar uma remessa devido a um problema com o calendário

Código de erro: TRX2716

## <a name="symptoms"></a>Sintomas

Ao tentar confirmar uma remessa, o sistema mostra a seguinte mensagem de erro:

> O tipo de calendário %1 requer que sejam feitos o check-in e o check-out do compromisso %2.

Portanto, não é possível confirmar a remessa da carga.

## <a name="cause"></a>Causa

Há compromissos ativos para a carga. Por exemplo, há uma regra que exige o check-in de driver. Então, a carga está em um estado no qual a confirmação de remessa falha.

## <a name="resolution"></a>Resolução

Você deve investigar e corrigir problemas com os compromissos ativos vinculados à carga.

1. Acesse **Gerenciamento de depósito \> Cargas \> Todas as cargas**.
1. Selecione a carga para a qual a remessa não pode ser confirmada.
1. No Painel de Ações, na guia **Transporte**, no grupo **Compromissos**, selecione **Agendamento de compromissos**.
1. Siga uma destas etapas:

    - Verifique se o check-in/check-out do driver foi concluído para o compromisso.
    - Conclua ou cancele o compromisso.
    - Desative a opção **Check-in de driver necessário** para a regra de compromisso relacionada.
