---
title: O arredondamento decimal da quantidade de atualização física está incorreto
description: Quando você gera uma guia de remessa, a carga de saída contém uma quantidade que não corresponde à precisão decimal definida na unidade.
author: GalynaFedorova
ms.date: 5/31/2021
ms.topic: troubleshooting
ms.search.form: WHSLoadPlanningListPage_WHSSalesPackingSlipPost, WHSLoadTable_WHSSalesPackingSlipPost
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: v-gfedorova
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 1e63440834f516879aa8ad711bd789e62b0ee993
ms.sourcegitcommit: e6437d994c3be0c5bb4a9263af3aa8351020d83a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/14/2021
ms.locfileid: "6248767"
---
# <a name="decimal-rounding-of-the-physical-updating-quantity-is-incorrect"></a>O arredondamento decimal da quantidade de atualização física está incorreto

Código de erro: SYS19589

## <a name="symptoms"></a>Sintomas

Quando você gera uma guia de remessa, a carga de saída contém uma quantidade que não corresponde à precisão decimal definida na unidade.

Ao tentar gerar uma guia de remessa, o sistema mostra a seguinte mensagem de erro:

> O arredondamento decimal da quantidade de atualização física na unidade %1 está incorreto.

Portanto, não é possível gerar a guia de remessa da carga.

## <a name="cause"></a>Causa

O sistema avalia se o arredondamento decimal da quantidade de transporte corresponde à precisão decimal definida para a unidade de transporte. Quando o sistema arredondar a quantidade de envio para o número especificado de casas decimais, se descobrir que a quantidade arredondada de envio não corresponde à quantidade de envio real, você não poderá gerar o deslizamento de embalagem. Por exemplo, esse problema pode ocorrer se a quantidade de vendas for de 1,75 kg (kg), mas a precisão decimal estiver definida como *1*.

## <a name="resolution"></a>Resolução

A carga ou a remessa estão em um estado no qual a geração da guia de remessa falha. Para corrigir esse problema, execute uma das seguintes tarefas:

- Revise suas linhas de carga e faça ajustes para garantir que a quantidade possa ser convertida de forma limpa sem problemas de arredondamento e de números decimais.
- Revise suas linhas de carga e faça ajustes para garantir que a unidade e a quantidade estejam alinhadas com a precisão decimal da unidade.

### <a name="review-your-load-lines-and-make-adjustments-to-ensure-that-the-quantity-can-be-cleanly-converted-without-decimal-numbers-and-any-other-rounding-issues"></a>Revisar suas linhas de carga e fazer ajustes para garantir que a quantidade possa ser convertida de forma limpa sem problemas de arredondamento e de números decimais

Use o seguinte procedimento para revisar suas linhas de carga e fazer ajustes para garantir que a quantidade possa ser convertida de forma limpa sem problemas de arredondamento e de números decimais.

1. Acesse **Gerenciamento de depósito \> Cargas \> Todas as cargas**.
1. Selecione a carga para a qual a guia de remessa não pode ser gerada.
1. No Painel de Ações, na guia  **Enviar e receber**, no grupo  **Reverter**, selecione  **Confirmação de envio reverso**.
1. Na guia  **Linhas de carga**, selecione a linha de carga para o item que causa um problema.
1. Selecione **Reduzir a quantidade escolhida** para ajustar a quantidade escolhida.
1. Na guia  **Detalhes da linha**, selecione **Ordem**.
1. Defina o campo **Quantidade** como a quantidade separada (ou seja, o valor do campo **Quantidade de trabalho criado**), de forma que a guia de remessa possa ser gerada.

### <a name="review-your-load-lines-and-make-adjustments-to-ensure-that-the-unit-and-quantity-are-aligned-with-the-decimal-precision-of-the-unit"></a>Revise suas linhas de carga e faça ajustes para garantir que a unidade e a quantidade estejam alinhadas com a precisão decimal da unidade

Use o seguinte procedimento para revisar suas linhas de carga e fazer ajustes para garantir que a unidade e a quantidade estejam alinhadas com a precisão decimal da unidade.

1. Acesse **Gerenciamento de depósito \> Cargas \> Todas as cargas**.
1. Selecione a carga para a qual a guia de remessa não pode ser gerada.
1. Na FastTab **Linhas de carga**, selecione a linha de carga para o item que causa um problema. Anote o valor dos campos **Quantidade** e **Unidade**.
1. Vá para **Administração de organização \> Unidades \> Unidades**.
1. Selecione a unidade para a qual a guia de remessa não pode ser gerada.
1. Ajuste o valor do campo **Precisão decimal** conforme necessário.
