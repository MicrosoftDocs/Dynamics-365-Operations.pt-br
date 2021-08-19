---
title: Não é possível atualizar uma linha de carregamento porque a quantidade liberada seria negativa
description: Esse problema ocorre quando a atualização ou a exclusão de uma linha de carregamento causa uma quantidade liberada negativa.
author: GalynaFedorova
ms.date: 6/30/2021
ms.topic: troubleshooting
ms.search.form: WHSLoadPlanningListPage_WHSLoadLineUnShipQty,WHSLoadTable_WHSLoadLineUnShipQty,WHSLoadPlanningWorkbench_WHSLoadLineUnShipQty,WHSShipmentDetails_WHSLoadLineUnShipQty,WHSLoadPlanningListPage_DeleteButtonLoadLine,WHSLoadTable_DeleteButtonLoadLine,WHSLoadPlanningWorkbench_DeleteButtonLoadLine,WHSShipmentDetails_DeleteButtonShipment
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: v-gfedorova
ms.search.validFrom: 2021-06-30
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: a6325a632e1f68a0a3a9cb6b6091c48da014a405e8ce9ad69ea841f5cceb216f
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6728450"
---
# <a name="cant-update-a-load-line-because-the-released-quantity-would-be-negative"></a>Não é possível atualizar uma linha de carregamento porque a quantidade liberada seria negativa

Código de erro: @WAX:ReleasedQtyCannotBeNegative

## <a name="symptoms"></a>Sintomas

Esse problema ocorre quando a atualização ou a exclusão de uma linha de carregamento causa uma quantidade liberada negativa. Neste caso, ao tentar atualizar ou excluir a linha de carregamento, o sistema mostra a seguinte mensagem de erro:

> A quantidade liberada não pode ser negativa para o item %1, lote %2.

Portanto, não é possível atualizar ou excluir a linha de carregamento.

## <a name="cause"></a>Causa

Depois de atualizar ou excluir uma linha de carregamento, o sistema atualiza a quantidade liberada da linha de venda relacionada (*whsSalesLine.ReleaseQty*). O sistema avalia a quantidade liberada e, se achar que a quantidade liberada da linha seria negativa após a atualização, ela não permitirá que você atualize ou exclua a linha. Essa validação ocorre sempre que você tenta atualizar a quantidade de linha de carregamento ou a unidade de medida por meio de várias ações, tais como excluir uma linha de carregamento, excluir uma remessa, alterar a quantidade de uma linha de carga, reduzir a quantidade separada e uma separação curta.

A causa principal mais comum desse problema é uma alteração na conversão de unidades usada para linhas de carregamento abertas. Por exemplo, a conversão de unidades quando uma ordem de venda foi liberada era *50 Ea = 1 PL*. No entanto, antes que a remessa de carga relacionada fosse finalizada, a conversão da unidade foi alterada para *100 Ea = 1 PL*.

## <a name="resolution"></a>Resolução

A solução é reverter as alterações de conversão de unidades, atualizar ou excluir a linha de carga e reimplementar a conversão. Você deve evitar outras cargas que incluam o item que causou o processamento da saída até que a saída seja corrigida. Caso contrário, as novas conversões podem ser usadas para outras cargas que já estão abertas.

Para solucionar esse problema, conclua as seguintes tarefas:

1. Revise a conversão de unidades que foi usada para a linha de carregamento.
2. Revise a conversão de unidade atual para o item e faça ajustes que permitirão que a linha de carregamento seja atualizada ou excluída.
3. Atualize ou exclua a linha de carregamento e reverta os ajustes de conversão de unidades.

### <a name="review-the-unit-conversion-that-was-used-for-the-load-line"></a>Revisar a conversão de unidades que foi usada para a linha de carregamento

Use o procedimento a seguir para revisar as linhas de carregamento e anote a conversão de unidades que foi usada para a linha de carregamento.

1. Acesse **Gerenciamento de depósito \> Cargas \> Todas as cargas**.
1. Selecione a carga que inclui a linha de carga que não pode ser excluída ou atualizada.
1. No Painel de Ações, na guia **Cargas**, no grupo **Informações relacionadas**, selecione **Trabalho**.
1. Na grade superior, selecione a ID do trabalho relevante.
1. Na guia **Geral** na parte inferior da página, calcule a taxa de conversão entre o valor de **Quantidade de trabalho de estoque** e o valor **Quantidade de trabalho**. Anote a taxa.
1. Repita este procedimento para todas as IDs de trabalho relevantes para ter certeza de que a mesma conversão foi usada.

### <a name="review-the-current-unit-conversion-for-the-item-and-make-adjustments"></a>Revisar a conversão de unidade atual para o item e fazer ajustes

Use o seguinte procedimento para revisar a conversão de unidade do seu produto e fazer ajustes para garantir que a conversão esteja alinhada com a linha de carga.

1. Acesse **Gerenciamento de informações do produto \> Produtos \> Produtos liberados**.
1. Abra o produto relevante para ir para a página **Detalhes do produto liberado** dele.
1. No Painel de Ações, na guia **Produto**, no grupo **Configuração**, selecione **Conversões de unidade**.
1. Selecione a conversão entre as unidades e faça ajustes usando a conversão encontrada na seção anterior.

### <a name="update-or-delete-the-load-line-and-revert-the-unit-conversion-adjustments"></a>Atualizar ou excluir a linha de carregamento e reverta os ajustes de conversão de unidades

Use o procedimento a seguir para processar a linha de carregamento conforme necessário e reverta as conversões de unidade.

1. Acesse **Gerenciamento de depósito \> Cargas \> Todas as cargas**.
1. Abra a carga que inclui a linha de carga que não pode ser excluída ou atualizada.
1. Na FastTab **Linhas de carga**, selecione a linha de carga.
1. Continue com as ações necessárias. (Por exemplo, exclua a linha de carregamento ou altere sua quantidade.)
1. Acesse **Gerenciamento de informações do produto \> Produtos \> Produtos liberados**.
1. Abra o produto relevante para ir para a página **Detalhes do produto liberado** dele.
1. No Painel de Ações, na guia **Produto**, no grupo **Configuração**, selecione **Conversões de unidade**.
1. Selecione a conversão entre as unidades e reverta os ajustes que fez na seção anterior.
