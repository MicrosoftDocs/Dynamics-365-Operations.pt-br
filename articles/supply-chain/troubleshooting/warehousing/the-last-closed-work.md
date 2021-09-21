---
title: A última linha de trabalho fechada deve ser de colocação
description: A última linha de trabalho fechada deve ser de colocação
author: perlynne
ms.date: 04/15/2021
ms.topic: troubleshooting
ms.search.form: WHSWorkTable_WHSWorkCancel, WHSWorkTableListPage_WHSWorkCancel
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-05-15
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 221c64c89d0e8addbf44acab8e7561e5f3a27239
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2021
ms.locfileid: "7474739"
---
# <a name="the-last-closed-work-line-must-be-a-put"></a>A última linha de trabalho fechada deve ser de colocação

Código de erro: WAX1285

## <a name="symptoms"></a>Sintomas

O sistema mostra a seguinte mensagem de erro:

> A última linha de trabalho fechada deve ser de colocação.

## <a name="cause"></a>Causa

O trabalho não pode ser cancelado no estado atual.

Na última linha de trabalho, o campo **Status do trabalho** está definido como *Fechado*, mas o campo **Tipo de trabalho** não está definido como *Colocado*.

## <a name="resolution"></a>Resolução

Para cancelar o trabalho, siga estas etapas.

1. Acesse **Gerenciamento de depósito \> Tarefas periódicas \> Limpar \> Cancelar trabalho**.
1. No campo **ID do trabalho**, especifique a ID do trabalho que deseja cancelar.
1. Selecione **OK**.
1. Selecione **Sim** para confirmar que você deseja cancelar o trabalho.

Para obter mais informações, consulte [Cancelar trabalho de depósito para tratamento de exceções](../../warehousing/cancel-warehouse-work.md).
