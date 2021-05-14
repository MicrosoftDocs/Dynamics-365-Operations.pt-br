---
title: Não é possível confirmar uma remessa porque há quantidade zero
description: Não é possível confirmar uma remessa porque há quantidade zero
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
ms.openlocfilehash: 7a06f0651db741a867e1e9fe7dbab841a928c22b
ms.sourcegitcommit: cd9016e9787169cb800889d335b9c5919ddbe4af
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2021
ms.locfileid: "5938419"
---
# <a name="you-cant-confirm-a-shipment-because-there-is-zero-quantity"></a>Não é possível confirmar uma remessa porque há quantidade zero

Código de erro: LoadLineWarningUpdatedToZero

## <a name="symptoms"></a>Sintomas

Ao tentar confirmar uma remessa, o sistema mostra a seguinte mensagem de erro:

> A linha de carga para o item %1 e a remessa %2 foi atualizado para ter quantidade zero devido a uma configuração de entrega insuficiente, o que permite não enviar nenhuma quantidade para este item.

Portanto, não é possível confirmar a remessa da carga.

## <a name="cause"></a>Causa

O sistema avalia se a quantidade separada está dentro dos limites esperados, com base na quantidade separada, na quantidade da linha de carga e na porcentagem de entrega insuficiente. Se o sistema descobrir que a quantidade separada na linha de carga é 0 (zero), você não poderá confirmar a remessa. Por exemplo, esse problema poderá ocorrer se o trabalho tiver sido cancelado, e a porcentagem de entrega insuficiente na linha de carga for 100%.

## <a name="resolution"></a>Resolução

Verifique as linhas de carga para garantir que a porcentagem de entrega insuficiente e as quantidades estejam alinhadas com o trabalho separado.

1. Acesse **Gerenciamento de depósito \> Cargas \> Todas as cargas**.
1. Selecione a carga para a qual a remessa não pode ser confirmada.
1. Na FastTab **Linhas de carga**, selecione a linha de carga do item que excede a porcentagem de entrega insuficiente.
1. Ajuste o valor do campo **Entrega insuficiente** ou o campo **Quantidade**, conforme necessário.

> [!TIP]
> Se o problema ainda não for corrigido, talvez seja necessário concluir mais trabalho de separação para as ordens de venda ou ordens de transferência relacionadas até que a quantidade disponível esteja alinhada com a carga ou a remessa.
