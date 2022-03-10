---
title: Não é possível confirmar uma remessa porque as linhas de carregamento têm quantidade zero
description: Não é possível confirmar uma remessa porque as linhas de carregamento têm quantidade zero.
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
ms.openlocfilehash: 15aa7f5e72ff8f2c027b5b020a23328978aa02b0
ms.sourcegitcommit: b9c2798aa994e1526d1c50726f807e6335885e1a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/13/2021
ms.locfileid: "7344225"
---
# <a name="you-cant-confirm-a-shipment-because-load-lines-have-zero-quantity"></a>Não é possível confirmar uma remessa porque as linhas de carregamento têm quantidade zero

Código de erro: WAX:LoadTableWarningAllLinesZero, WAX2543

## <a name="symptoms"></a>Sintomas

Ao tentar confirmar uma remessa, o sistema mostra a seguinte mensagem de erro:

> Todas as linhas na carga %1 têm quantidade zero.  
> Não foi possível confirmar a remessa da carga %1.

Portanto, não é possível confirmar a remessa da carga.

## <a name="cause"></a>Causa

O sistema avalia se a linha de carregamento pode ser remetida com base nas IDs de trabalho criadas, no carregamento da quantidade de linha e na porcentagem de entrega insuficiente. Se o sistema entender que não há IDs de trabalho e se a porcentagem de entrega insuficiente estiver definida como 100%, você não poderá confirmar a remessa.

Por exemplo, esse problema poderá ocorrer se o trabalho tiver sido cancelado, e a porcentagem de entrega insuficiente na linha de carga for 100%.

## <a name="resolution"></a>Resolução

A carga ou a remessa estão em um estado no qual a confirmação de remessa falha. Para corrigir esse problema, execute uma das seguintes tarefas:

- Revise suas linhas de carga para verificar se todos os trabalhos relacionados foram concluídos no local de remessa final e se as quantidades coincidem.
- Revise as linhas de carga para garantir que a porcentagem de entrega insuficiente e as quantidades estejam alinhadas com o trabalho separado.

### <a name="review-your-load-lines-to-make-sure-that-all-the-related-work-has-been-completed-at-the-final-shipping-location-and-that-the-quantities-match"></a>Revise suas linhas de carga para verificar se todos os trabalhos relacionados foram concluídos no local de remessa final e se as quantidades coincidem

Use o seguinte procedimento para revisar suas linhas de carga para verificar se todos os trabalhos relacionados foram concluídos no local de remessa final e se as quantidades coincidem.

1. Acesse **Gerenciamento de depósito \> Cargas \> Todas as cargas**.
1. Abra a carga para a qual a remessa não pode ser confirmada.
1. Na FastTab **Linhas de carga**, selecione a linha de carga.
1. Anote o valor do campo **Quantidade de trabalho criado**.
1. No Painel de Ações, na guia **Cargas**, no grupo **Informações relacionadas**, selecione **Trabalho**.
1. Verifique se o trabalho foi concluído no local de remessa final e se a quantidade de trabalho separada corresponde à quantidade de trabalho criada na linha de carga.
1. Se você encontrar uma correspondência incorreta, cancele o trabalho relevante, reconfigure a diretiva de localização e libere a carga novamente. Para mais informações, consulte [Não é possível confirmar uma remessa devido a itens que não foram separados](picked-quantity-is-not-on-final.md).
1. Repita este procedimento para todas as linhas de carga para garantir que todos os critérios sejam atendidos.

### <a name="review-your-load-lines-to-make-sure-that-the-underdelivery-percentage-and-quantities-are-aligned-with-the-picked-work"></a>Revise as linhas de carregamento para garantir que a porcentagem de entrega insuficiente e as quantidades estejam alinhadas com o trabalho separado

Use o seguinte procedimento para revisar, as linhas de carregamento para garantir que a porcentagem de entrega insuficiente e as quantidades estejam alinhadas com o trabalho separado.

1. Acesse **Gerenciamento de depósito \> Cargas \> Todas as cargas**.
1. Abra a carga para a qual a remessa não pode ser confirmada.
1. Na FastTab **Linhas de carga**, selecione a linha de carga do item que excede a porcentagem de entrega insuficiente.
1. Ajuste o valor do campo **Entrega insuficiente** ou o campo **Quantidade**, conforme necessário.

> [!TIP]
> Se o problema ainda não for corrigido, talvez seja necessário concluir mais trabalho de separação para as ordens de venda ou ordens de transferência relacionadas até que a quantidade disponível esteja alinhada com a carga ou a remessa.
