---
title: A quantidade física remanescente na unidade não pode ser zero
description: Quando você gera um guia de remessa, os dados fornecidos a ela têm uma quantidade de estoque não zero, mas uma quantidade de venda zero.
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
ms.openlocfilehash: d767fdce861ccb481a3fe289480a51a7534dc207
ms.sourcegitcommit: 008779c530798f563fe216810d34b2d56f2c8d3c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/14/2021
ms.locfileid: "7920215"
---
# <a name="physical-remaining-quantity-in-the-unit-must-not-be-zero"></a>A quantidade física remanescente na unidade não pode ser zero

Código de erro: SYS19591

## <a name="symptoms"></a>Sintomas

Quando você gera um guia de remessa, os dados fornecidos a ela têm uma quantidade de estoque não zero, mas uma quantidade de venda zero.

Ao tentar gerar uma guia de remessa, o sistema mostra a seguinte mensagem de erro:

> A quantidade física restante na unidade %1 deve ser diferente de zero.

Portanto, não é possível gerar a guia de remessa da carga.

## <a name="cause"></a>Causa

O sistema avalia a quantidade física remanescente na unidade de estoque e a quantidade física restante na unidade de transporte. Se o sistema descobrir que a quantidade física restante na unidade de transporte é 0 (zero), mas a quantidade física restante na unidade de estoque não é 0, você não poderá gerar a guia de remessa. Por exemplo, esse problema pode ocorrer se a unidade de vendas e a unidade de estoque do item forem diferentes, e a conversão entre as unidades não for precisa.

## <a name="resolution"></a>Resolução

A carga ou a remessa estão em um estado no qual a geração da guia de remessa falha. Para corrigir esse problema, execute uma das seguintes tarefas:

- Revise suas linhas de carga e verifique se todos os trabalhos relacionados foram concluídos no local de remessa final e se as quantidades coincidem.
- Revise suas linhas de carga e faça ajustes para garantir que a quantidade possa ser convertida de forma limpa sem problemas de arredondamento.
- Revise suas linhas de carga e faça ajustes para garantir que a unidade e a quantidade estejam alinhadas com a precisão decimal da unidade.
- Certifique-se de que a unidade de inventário da medida é menor do que a unidade de medida da venda.

### <a name="review-your-load-lines-and-make-sure-that-all-the-related-work-has-been-completed-at-the-final-shipping-location-and-that-the-quantities-match"></a>Revise suas linhas de carga e verifique se todos os trabalhos relacionados foram concluídos no local de remessa final e se as quantidades coincidem

Use o seguinte procedimento para revisar suas linhas de carga e verificar se todos os trabalhos relacionados foram concluídos no local de remessa final e se as quantidades coincidem.

1. Acesse **Gerenciamento de depósito \> Cargas \> Todas as cargas**.
1. Selecione a carga para a qual a remessa não pode ser confirmada.
1. Na FastTab **Linhas de carga**, selecione a linha de carga.
1. Anote o valor do campo **Quantidade de trabalho criado**.
1. No Painel de Ações, na guia **Cargas**, no grupo **Informações relacionadas**, selecione **Trabalho**.
1. Verifique se o trabalho foi concluído no local de remessa final e se a quantidade de trabalho separada corresponde à quantidade de trabalho criada na linha de carga.
1. Repita este procedimento para todas as linhas de carga para garantir que todos os critérios sejam atendidos.

### <a name="review-your-load-lines-and-make-adjustments-to-ensure-that-the-quantity-can-be-cleanly-converted-without-rounding-issues"></a>Revise suas linhas de carga e faça ajustes para garantir que a quantidade possa ser convertida de forma limpa sem problemas de arredondamento

Use o seguinte procedimento para revisar suas linhas de carga e fazer ajustes para garantir que a quantidade possa ser convertida de forma limpa sem problemas de arredondamento.

1. Acesse **Gerenciamento de depósito \> Cargas \> Todas as cargas**.
1. Selecione a carga para a qual a guia de remessa não pode ser gerada.
1. No Painel de Ações, na guia **Enviar e receber**, no grupo **Reverter**, selecione **Confirmação de remessa reversa**.
1. Na guia **Linhas de carga**, selecione a linha de carga do item que excede a entrega excedente.
1. Selecione **Reduzir a quantidade escolhida** para ajustar a quantidade escolhida.
1. Na guia **Detalhes da linha**, selecione **Pedido**.
1. Defina o campo **Quantidade** como a quantidade separada (ou seja, o valor do campo **Quantidade de trabalho criado**), de forma que a guia de remessa possa ser gerada.

### <a name="review-your-load-lines-and-make-adjustments-to-ensure-that-the-unit-and-quantity-are-aligned-with-the-decimal-precision-of-the-unit"></a>Revise suas linhas de carga e faça ajustes para garantir que a unidade e a quantidade estejam alinhadas com a precisão decimal da unidade

Use o seguinte procedimento para revisar suas linhas de carga e fazer ajustes para garantir que a unidade e a quantidade estejam alinhadas com a precisão decimal da unidade.

1. Acesse **Gerenciamento de depósito \> Cargas \> Todas as cargas**.
1. Selecione a carga para a qual a guia de remessa não pode ser gerada.
1. Na FastTab **Linhas de carga**, selecione a linha de carga para o item que causa um problema. Anote o valor dos campos **Quantidade** e **Unidade**.
1. Acesse **Administração de organização \> Unidades \> Unidades**.
1. Selecione a unidade para a qual a guia de remessa não pode ser gerada.
1. Ajuste o valor do campo **Precisão decimal** conforme necessário.

### <a name="make-sure-that-the-inventory-unit-of-measure-is-smaller-than-the-sales-unit-of-measure"></a>Certifique-se de que a unidade de medida do estoque é menor do que a unidade de medida da venda

Certifique-se de que a unidade de inventário da medida é menor do que a unidade de medida da venda. Considere reconfigurar a unidade de medida para o item conforme necessário.
