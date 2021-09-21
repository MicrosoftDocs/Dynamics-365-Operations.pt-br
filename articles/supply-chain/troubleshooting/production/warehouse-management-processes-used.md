---
title: Os processos de gerenciamento de depósito estão sendo usados no momento
description: Ao reservar ou liberar trabalho, você poderá receber uma mensagem informando que os processos de gerenciamento de depósito estão sendo usados no momento. Corrija o problema usando uma das seguintes etapas.
author: SmithaNataraj
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: bfda2fae824cdc64d722310d20cf16e6306d766c
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2021
ms.locfileid: "7475532"
---
# <a name="cant-reserve-or-release-work-because-processes-are-currently-being-used"></a>Não é possível reservar ou liberar trabalho porque os processos estão sendo usados no momento

## <a name="symptoms"></a>Sintomas

Ao trabalhar com fabricação discreta, você receberá o seguinte erro:

> Os processos de gerenciamento de depósito estão sendo usados no momento. Se as linhas de trabalho ainda não estiverem registradas, você poderá cancelar o trabalho criado e qualquer linha de carga ou expedição e continuar com o processo de separação ou remessa".

## <a name="cause"></a>Causa

Esse problema ocorre se você tentar reservar ou liberar trabalho para uma linha, mas a transação de estoque tiver um status de *Separado*, o que indica que o material foi separado.

## <a name="resolution"></a>Resolução

Para corrigir esse problema, siga uma destas etapas:

- Altere o status da ordem de produção de volta para *Previsto* ou *Liberado*.
- Abra a página de detalhes da ordem de produção relevante. No Painel de ações, na guia **Depósito**, no grupo **Parar**, selecione **Parar e desfazer separação** para desmarcar todas as transações selecionadas. Em seguida, selecione **Remover parada** para processar a ordem de produção.

Aqui está uma explicação das funções *Desfazer separação* e *Parar*:
  
- **Desfazer separação** - Esta função inverte o status das transações de estoque para linhas da lista de materiais (BOM) e linhas de fórmula que têm um status de *Separado* a *Em ordem*. Quando o trabalho de separação de matéria-prima é concluído, o status das linhas é definido como *Separado*. Este status evita que a ordem de produção seja redefinida para o status *Criado*. Nesse caso, você pode usar a função *Desfazer separação* para reverter as transações do status *Separado* e redefinir a ordem de produção para o status *Criado*.
- **Parar** – Esta função define um sinalizador **Interrompido** na ordem de produção para evitar qualquer atualização de status na ordem. É possível encontrar o sinalizador **Interrompido** na guia rápida **Depósito** da página de detalhes da ordem de produção.

> [!NOTE]
>
> - Os botões são visíveis somente quando a ordem de produção é criada para itens habilitados para processos de depósito.
> - O grupo **Parar** está visível apenas na guia **Depósito** no Painel de ações da página de detalhes da ordem de produção. Não está visível na FastTab **Depósito** da página de lista **Ordens de Produção**.
