---
title: A quantidade excede a porcentagem de entrega excedente durante a geração da guia de remessa
description: Quando você gera uma guia de remessa, a carga de saída contém uma quantidade que excede a porcentagem de entrega excedente.
author: GalynaFedorova
ms.date: 5/31/2021
ms.topic: troubleshooting
ms.search.form: WHSLoadTable_WHSSalesPackingSlipPost,WHSLoadPlanningListPage_WHSSalesPackingSlipPost,WHSLoadPlanningWorkbench_WHSSalesPackingSlipPost
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: v-gfedorova
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: bc74c5748950b1f0f001fd89acb2e023640065ee
ms.sourcegitcommit: 008779c530798f563fe216810d34b2d56f2c8d3c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/14/2021
ms.locfileid: "7920041"
---
# <a name="quantity-exceeds-over-delivery-percentage-during-packing-slip-generation"></a>A quantidade excede a porcentagem de entrega excedente durante a geração da guia de remessa

Código de erro: SYS24920

## <a name="symptoms"></a>Sintomas

Quando você gera uma guia de remessa, a carga de saída contém uma quantidade que excede a porcentagem de entrega excedente.

Ao tentar gerar uma guia de remessa, o sistema mostra a seguinte mensagem de erro:

> A entrega excedente da linha é de %1%, mas o percentual permitido para entrega excedente é de apenas %2%.

Portanto, não é possível gerar a guia de remessa da carga.

## <a name="cause"></a>Causa

A quantidade escolhida para a carga ou remessa é maior do que a quantidade da ordem e não está dentro do intervalo da porcentagem de entrega excedente.

## <a name="resolution"></a>Resolução

A carga ou a remessa estão em um estado no qual a geração da guia de remessa falha. Para corrigir esse problema, execute uma das seguintes tarefas:

- Ajuste a quantidade da linha de carga.
- Ajustar a porcentagem de entrega excedente.
- Inverta e faça ajustes.

### <a name="adjust-the-load-line-quantity"></a>Ajustar a quantidade da linha de carga

Use o seguinte procedimento para ajustar a quantidade da linha de carga.

1. Acesse **Gerenciamento de depósito \> Cargas \> Todas as cargas**.
1. Selecione a carga para a qual a guia de remessa não pode ser gerada.
1. No Painel de Ações, na guia **Enviar e receber**, no grupo **Reverter**, selecione **Confirmação de remessa reversa**.
1. Na guia **Linhas de carga**, selecione a linha de carga do item que excede a porcentagem de entrega excedente.
1. Selecione **Reduzir a quantidade escolhida** para ajustar a quantidade escolhida.
1. Na guia **Detalhes da linha**, selecione **Pedido**.
1. Defina o campo **Quantidade** como a quantidade separada (ou seja, o valor do campo **Quantidade de trabalho criado**), de forma que a guia de remessa possa ser gerada.

### <a name="adjust-the-over-delivery-percentage"></a>Ajustar a porcentagem de entrega excedente

Use o seguinte procedimento para ajustar a porcentagem de entrega excedente.

1. Acesse **Contas a receber \> Ordens \> Todas as ordens**.
1. Selecione a ordem de venda para a qual você não pode postar uma guia de remessa para a carga.
1. Na guia **Linhas da ordem de venda**, selecione a linha da ordem de venda do item que excede a porcentagem de entrega excedente.
1. Na guia **Detalhes da linha**, selecione **Entrega**.
1. Defina o campo **Entrega excedente** como uma porcentagem maior que acomode a quantidade que foi separada em relação à quantidade de carga, de forma que a guia de remessa possa ser gerada.

### <a name="reverse-and-make-adjustments"></a>Inverter e fazer ajustes

Reverta tudo o que foi lançado para a carga (por exemplo, a guia de remessa, confirmação de remessa e trabalho), faça ajustes a ordens de venda, libere novamente o pedido para depósito e conclua o procedimento de remessa.

Use o procedimento a seguir para cancelar uma guia de remessa.

1. Acesse **Gerenciamento de depósito \> Cargas \> Todas as cargas**.
1. No Painel de Ações, na guia **Enviar e receber**, no grupo **Reverter**, selecione **Cancelar guias de remessa**.

Use o procedimento a seguir para reverter a confirmação de remessa.

1. Acesse **Gerenciamento de depósito \> Cargas \> Todas as cargas**.
1. No Painel de Ações, na guia **Enviar e receber**, no grupo **Reverter**, selecione **Confirmação de remessa reversa**.

Use o procedimento a seguir para reverter o trabalho.

1. Acesse **Gerenciamento de depósito \> Cargas \> Todas as cargas**.
1. No Painel de Ações, na guia **Cargas**, no grupo **Trabalho**, selecione **Reverter trabalho**.
