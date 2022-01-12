---
title: A quantidade escolhida não é suficiente durante a geração de guias de remessa
description: Quando você gera uma guia de remessa, a carga de saída contém uma quantidade escolhida que não corresponde à quantidade de trabalho criada na linha de carga.
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
ms.openlocfilehash: 6febc340f140d0b3a3f08ea32a59d9eb4e6e5204
ms.sourcegitcommit: 008779c530798f563fe216810d34b2d56f2c8d3c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/14/2021
ms.locfileid: "7920439"
---
# <a name="picked-quantity-isnt-sufficient-during-packing-slip-generation"></a>A quantidade escolhida não é suficiente durante a geração de guias de remessa

Código de erro: SYS54073

## <a name="symptoms"></a>Sintomas

Quando você gera uma guia de remessa, a carga de saída contém uma quantidade escolhida que não corresponde à quantidade de trabalho criada na linha de carga.

Ao tentar gerar uma guia de remessa, o sistema mostra a seguinte mensagem de erro:

> Foram separados %1, o que não é suficiente para atualizar %2, quando, subsequentemente, o pendente deve ser %3.

Portanto, não é possível gerar a guia de remessa da carga.

## <a name="cause"></a>Causa

A guia de remessa não pode ser gerada no estado atual porque pode existir uma das seguintes condições:

- O trabalho relacionado ainda não foi separado e movido para o local de remessa final.
- A quantidade de trabalho separada não corresponde à quantidade de trabalho criada na linha de carga.
- A quantidade de linha da carga, a quantidade criada de trabalho e a quantidade escolhida não correspondem.

## <a name="resolution"></a>Resolução

A carga ou a remessa estão em um estado no qual a geração da guia de remessa falha. Para corrigir esse problema, execute uma das seguintes tarefas:

- Revise suas linhas de carga e verifique se todos os trabalhos relacionados foram concluídos no local de remessa final e se as quantidades coincidem.
- Ajuste a quantidade da linha de carga.
- Inverta todos os registros de separação e refaça a separação.

### <a name="review-your-load-lines-and-make-sure-that-all-the-related-work-has-been-completed-at-the-final-shipping-location-and-that-the-quantities-match"></a>Revise suas linhas de carga e verifique se todos os trabalhos relacionados foram concluídos no local de remessa final e se as quantidades coincidem

Use o seguinte procedimento para revisar suas linhas de carga e verificar se todos os trabalhos relacionados foram concluídos no local de remessa final e se as quantidades coincidem.

1. Acesse **Gerenciamento de depósito \> Cargas \> Todas as cargas**.
1. Selecione a carga para a qual a guia de remessa não pode ser gerada.
1. Na FastTab **Linhas de carga**, selecione a linha de carga.
1. Anote o valor do campo **Quantidade de trabalho criado**.
1. No Painel de Ações, na guia **Cargas**, no grupo **Informações relacionadas**, selecione **Trabalho**.
1. Verifique se o trabalho foi concluído no local de remessa final e se a quantidade de trabalho separada corresponde à quantidade de trabalho criada na linha de carga.
1. Repita este procedimento para todas as linhas de carga para garantir que todos os critérios sejam atendidos.

### <a name="adjust-the-load-line-quantity"></a>Ajustar a quantidade da linha de carga

Use o seguinte procedimento para ajustar a quantidade da linha de carga.

1. Acesse **Gerenciamento de depósito \> Cargas \> Todas as cargas**.
1. Selecione a carga para a qual a guia de remessa não pode ser gerada.
1. No Painel de Ações, na guia **Enviar e receber**, no grupo **Reverter**, selecione **Confirmação de remessa reversa**.
1. Na guia **Linhas de carga**, selecione a linha de carga para o item que causa um problema.
1. Selecione **Reduzir a quantidade escolhida** para ajustar a quantidade escolhida.
1. Defina o campo **Reduzir linha de carga** para refletir os ajustes na linha de carga.

### <a name="reverse-all-pick-registrations-and-redo-picking"></a>Inverta todos os registros de separação e refaça a separação

O problema pode ocorrer porque alguém usou o registro de escolha para fechar uma linha de carga sem trabalho. Neste caso, o registro manual de escolha deve ser invertido, e a escolha deve ser concluída usando o aplicativo móvel Warehouse Management.

Use o procedimento a seguir para reverter o registro de escolha.

1. Acesse **Contas a receber \> Ordens \> Todas as ordens**.
1. Selecione a ordem de venda para a qual você não pode postar uma guia de remessa para a carga.
1. Na guia **Linhas de ordem de venda**, selecione a linha de ordem de venda para a qual o registro de escolha foi feito.
1. Selecione **Atualizar linha \> Escolher** para cancelar a seleção dos itens.
