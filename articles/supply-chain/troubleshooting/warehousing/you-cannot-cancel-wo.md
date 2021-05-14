---
title: Não é possível cancelar um trabalho que esteja em um usuário
description: Não é possível cancelar um trabalho que esteja em um usuário
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
ms.openlocfilehash: e5f6912cfb1d5be8e46b7989856af99f8a611c11
ms.sourcegitcommit: 5f5afb46431e1abd8fb6e92e0189914b598dc7fd
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2021
ms.locfileid: "5924392"
---
# <a name="you-cant-cancel-work-that-is-on-a-user"></a>Não é possível cancelar um trabalho que esteja em um usuário

Código de erro: WAX708

## <a name="symptoms"></a>Sintomas

O sistema mostra a seguinte mensagem de erro:

> Você não pode cancelar o trabalho que está em um usuário.

## <a name="cause"></a>Causa

O trabalho está bloqueado por um usuário e não pode ser cancelado. Para confirmar isso, abra a ID do trabalho e, em seguida, abra a guia **Geral**. Se o trabalho estiver bloqueado, o campo **Status do trabalho** será definido como *Em andamento*, e o campo **Bloqueado por** será definido como uma ID de usuário.

## <a name="resolution"></a>Resolução

Para cancelar o trabalho, siga estas etapas.

1. Vá para **Gerenciamento de depósito \> Tarefas periódicas \> Limpar \> Cancelar trabalho**.
1. No campo **ID do trabalho**, especifique a ID do trabalho que deseja cancelar.
1. Selecione **OK**.
1. Selecione **Sim** para confirmar que você deseja cancelar o trabalho.

Para obter mais informações, consulte [Cancelar trabalho de depósito para tratamento de exceções](../../warehousing/cancel-warehouse-work.md).
