---
title: O trabalho não pode ser cancelado porque está bloqueado
description: O trabalho não pode ser cancelado porque está bloqueado
author: perlynne
ms.date: 04/15/2021
ms.topic: troubleshooting
ms.search.form: WHSWorkTable_WHSWorkCancel
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-05-15
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: a7ab4c7263947767164702fb7dd6da7573175253
ms.sourcegitcommit: 5f5afb46431e1abd8fb6e92e0189914b598dc7fd
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2021
ms.locfileid: "5924270"
---
# <a name="work-cant-be-canceled-because-its-blocked"></a>O trabalho não pode ser cancelado porque está bloqueado

Código de erro: WHSCancellationOfWorkBlockedByExecutingWave_ErrorMessage

## <a name="symptoms"></a>Sintomas

O sistema mostra a seguinte mensagem de erro:

> O trabalho %1 não pode ser cancelado porque está bloqueado pelo tipo de motivo %2. O trabalho deve ser desbloqueado para que possa ser cancelado.

## <a name="cause"></a>Causa

O trabalho está bloqueado e não pode ser cancelado.

Na página **Trabalho**, na guia **Geral**, a opção **Bloqueado** está definida como *Sim*. Essa configuração indica que o trabalho está bloqueado. A guia **Motivos do bloqueio** mostra por que o trabalho foi bloqueado.

## <a name="resolution"></a>Resolução

Para desbloquear o trabalho, selecione a guia **Motivos do bloqueio** e, em seguida, siga uma destas etapas:

- Se o campo **Motivo do bloqueio do trabalho** estiver definido como *Motivo não definido*: no Painel de Ações, na guia **Trabalho**, no grupo **Trabalho**, selecione **Desbloquear trabalho**.
- Se o campo **Motivo do bloqueio do trabalho** estiver definido como *Ciclo de processamento*: no Painel de Ações, na guia **Informações relacionadas**, no grupo **Informações relacionadas**, selecione **Ciclo**. Em seguida, na página **Ciclos**, no Painel de Ações, na guia **Ciclo**, no grupo **Ciclo**, selecione **Limpar dados do ciclo**.

## <a name="workaround"></a>Solução alternativa

Se as etapas anteriores não corrigiram o problema, você pode cancelar o trabalho seguindo estas etapas.

1. Vá para **Gerenciamento de depósito \> Tarefas periódicas \> Limpar \> Cancelar trabalho**.
1. No campo **ID do trabalho**, especifique a ID do trabalho que deseja cancelar e que, atualmente, tem um valor **Status do trabalho** de *Aberto*, *Em andamento*, *Cancelado*, *Combinado* ou *Fechado*.
1. Selecione **OK**.
1. Selecione **Sim** para confirmar que você deseja cancelar o trabalho.

Para obter mais informações, consulte [Cancelar trabalho de depósito para tratamento de exceções](../../warehousing/cancel-warehouse-work.md).
