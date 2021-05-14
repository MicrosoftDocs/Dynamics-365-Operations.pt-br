---
title: O trabalho permanece bloqueado
description: O trabalho permanece bloqueado
author: perlynne
ms.date: 04/15/2021
ms.topic: troubleshooting
ms.search.form: WHSWorkTableListPage_WHSWorkUnblocking
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-05-15
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: f85364d1ecfadc36b26c3395ab4402d3cb3b1603
ms.sourcegitcommit: 5f5afb46431e1abd8fb6e92e0189914b598dc7fd
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2021
ms.locfileid: "5924121"
---
# <a name="work-remains-blocked"></a>O trabalho permanece bloqueado

Código de erro: WHSWorkBlockingExecutingWaveReason_ErrorMessage

## <a name="symptoms"></a>Sintomas

O sistema mostra a seguinte mensagem de erro:

> O trabalho %1 permanece bloqueado porque o ciclo relacionado %2 tem o status %3.

## <a name="cause"></a>Causa

No momento, o trabalho está sendo processado em um ciclo e não pode ser desbloqueado, como indicado por uma das seguintes condições:

- Na guia **Motivos do bloqueio**, o campo **Motivo do bloqueio do trabalho** de uma ou mais linhas está definido como *Ciclo de processamento*.
- Ao selecionar **Ciclo** no grupo **Informações relacionadas**, na guia **Informações relacionadas** do Painel de Ações, o campo **Status do ciclo** é definido como *Processando*.

## <a name="resolution"></a>Resolução

No Painel de Ações, na guia **Informações relacionadas**, no grupo **Informações relacionadas**, selecione **Ciclo**. Em seguida, na página **Ciclos**, no Painel de Ações, na guia **Ciclo**, no grupo **Ciclo**, selecione **Limpar dados do ciclo**.

## <a name="workaround"></a>Solução alternativa

Se as etapas anteriores não corrigiram o problema, você pode cancelar o trabalho seguindo estas etapas.

1. Vá para **Gerenciamento de depósito \> Tarefas periódicas \> Limpar \> Cancelar trabalho**.
1. No campo **ID do trabalho**, especifique a ID do trabalho que deseja cancelar e que, atualmente, tem um valor **Status do trabalho** de *Aberto*, *Em andamento*, *Cancelado*, *Combinado* ou *Fechado*.
1. Selecione **OK**.
1. Selecione **Sim** para confirmar que você deseja cancelar o trabalho.

Para obter mais informações, consulte [Cancelar trabalho de depósito para tratamento de exceções](../../warehousing/cancel-warehouse-work.md).
