---
title: O trabalho não pode ser cancelado por causa de seu status
description: O trabalho não pode ser cancelado por causa de seu status
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
ms.openlocfilehash: f983501b490c5516525b4d5904603ed62e8799f9e6124e5672b36a12804ecb0a
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6755969"
---
# <a name="work-cant-be-canceled-because-of-its-status"></a>O trabalho não pode ser cancelado por causa de seu status

Código de erro: WAX2190

## <a name="symptoms"></a>Sintomas

O sistema mostra a seguinte mensagem de erro:

> Você não pode cancelar o trabalho %1 porque ele tem o status %2.

## <a name="cause"></a>Causa

O trabalho não pode ser cancelado no estado atual.

O cabeçalho ou as linhas do trabalho não têm o valor **Status do trabalho** esperado. O campo **Status do trabalho** no cabeçalho do trabalho não está definido como *Aberto* ou *Em andamento*.

## <a name="resolution"></a>Resolução

Para cancelar o trabalho, siga estas etapas.

1. Acesse **Gerenciamento de depósito \> Tarefas periódicas \> Limpar \> Cancelar trabalho**.
1. No campo **ID do trabalho**, especifique a ID do trabalho que deseja cancelar.
1. Selecione **OK**.
1. Selecione **Sim** para confirmar que você deseja cancelar o trabalho.

Para obter mais informações, consulte [Cancelar trabalho de depósito para tratamento de exceções](../../warehousing/cancel-warehouse-work.md).
