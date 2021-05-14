---
title: Não é possível confirmar uma remessa devido a trabalho incompleto ou ausente
description: Não é possível confirmar uma remessa devido a trabalho incompleto ou ausente
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
ms.openlocfilehash: da6388d433d6021a99840ae9781c717db1b540a9
ms.sourcegitcommit: cd9016e9787169cb800889d335b9c5919ddbe4af
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2021
ms.locfileid: "5938421"
---
# <a name="you-cant-confirm-a-shipment-because-of-incomplete-or-missing-work"></a>Não é possível confirmar uma remessa devido a trabalho incompleto ou ausente

Código de erro: WAX515

## <a name="symptoms"></a>Sintomas

Ao tentar confirmar uma remessa, o sistema mostra a seguinte mensagem de erro:

> Não foi possível confirmar a remessa da carga %1 porque todos os trabalhos da carga devem ser concluídos.

Portanto, não é possível confirmar a remessa da carga.

## <a name="cause"></a>Causa

A carga ou a remessa estão em um estado no qual a confirmação de remessa falha. Para poder confirmar a remessa, deve existir pelo menos um trabalho para a carga e todo esse trabalho deve ter o status *Fechado* ou *Cancelado*.

## <a name="resolution"></a>Resolução

Verifique as ordens de venda relacionadas ou as ordens de transferência para a carga ou remessa e verifique se todos os trabalhos relacionados foram concluídos ou cancelados.

Você pode trabalhar com remessas e cargas em várias páginas. As subseções a seguir fornecem alguns exemplos.

### <a name="all-loads-page"></a>Página todas as cargas

1. Acesse **Gerenciamento de depósito \> Cargas \> Todas as cargas**.
1. Selecione a carga para a qual a remessa não pode ser confirmada.
1. No Painel de Ações, na guia **Cargas**, no grupo **Informações relacionadas**, selecione **Trabalho**.
1. Inspecione o status de cada ID de trabalho. Acompanhamento de cada ID de trabalho sem status *Fechado* ou *Cancelado*.
1. Quando cada ID de trabalho tiver um status *Fechado* ou *Cancelado*, tente confirmar novamente a remessa.

### <a name="all-shipments-page"></a>Página Todas as remessas

1. Acesse **Gerenciamento de depósito \> Remessas \> Todas as remessas**.
1. Selecione a remessa que não pode ser confirmada.
1. No Painel de Ações, na guia **Remessas**, no grupo **Trabalho**, selecione **Detalhes do trabalho**.
1. Inspecione o status de cada ID de trabalho. Acompanhamento de cada ID de trabalho sem status *Fechado* ou *Cancelado*.
1. Quando cada ID de trabalho tiver um status *Fechado* ou *Cancelado*, tente confirmar novamente a remessa.

### <a name="all-work-page"></a>Página Todos os trabalhos

1. Acesse **Gerenciamento de depósito \> Trabalho \> Todos os trabalhos**.
1. Selecione o trabalho para o número da ordem para o qual a remessa não pode ser confirmada.
1. No painel de Ações, na guia **Remessa** , no grupo **Remessa** , selecione **Confirmar remessa**.
1. Inspecione o status de cada ID de trabalho. Acompanhamento de cada ID de trabalho sem status *Fechado* ou *Cancelado*.
1. Quando cada ID de trabalho tiver um status *Fechado* ou *Cancelado*, tente confirmar novamente a remessa.
