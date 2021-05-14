---
title: O ciclo não está qualificado para limpeza
description: O ciclo não está qualificado para limpeza
author: perlynne
ms.date: 04/15/2021
ms.topic: troubleshooting
ms.search.form: WHSWaveTable_WHSWaveProcessingDataCleanup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-05-15
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 3e5142cf40a6c0d308e8e952bbe17e85b498826d
ms.sourcegitcommit: 5f5afb46431e1abd8fb6e92e0189914b598dc7fd
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2021
ms.locfileid: "5924318"
---
# <a name="wave-isnt-eligible-for-cleanup"></a>O ciclo não está qualificado para limpeza

Código de erro: WaveNotEligibleForCleanup

## <a name="symptoms"></a>Sintomas

O sistema mostra a seguinte mensagem de erro:

> A onda %1 não está inteligível para a limpeza.

Os dados do ciclo não podem ser limpos.  

## <a name="cause"></a>Causa

No momento, o ciclo está sendo processado, como indicado por uma das seguintes condições:

- O campo **Status do ciclo** está definido como *Executando*.
- Ao selecionar **Trabalho em lotes** no grupo **Ciclo**, na guia **Ciclo** do Painel de Ações, o campo **Status** não é definido como *Concluído*, *Erro* ou *Cancelado*. Portanto, um trabalho em lotes está em execução no momento.

## <a name="resolution"></a>Resolução

No Painel de Ações, na guia **Ciclo**, no grupo **Ciclo**, selecione **Trabalho em lotes** e siga uma destas etapas:

- Se o campo **Status** estiver definido como *Executando*: no Painel de Ações, na guia **Trabalho em lotes**, no grupo **Trabalho em lotes**, selecione **Exibir tarefas**. Você pode acompanhar o progresso atualizando a página **Tarefas em lote**.
- Se o campo **Status** não estiver definido como *Executando*: no Painel de Ações, na guia **Trabalho em lotes**, no grupo **Funções**, selecione **Alterar status**. No campo **Selecionar novo status**, selecione *Aguardando*. Em seguida, selecione **OK**.
