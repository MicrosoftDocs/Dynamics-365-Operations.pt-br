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
ms.openlocfilehash: bbc5797df2b7465b36ec5ea546a67441626daeb1c72f82dfca4eb7db3503b713
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6760265"
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
