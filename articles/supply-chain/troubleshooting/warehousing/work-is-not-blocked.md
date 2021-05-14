---
title: O trabalho não está bloqueado
description: O trabalho não está bloqueado
author: perlynne
ms.date: 04/15/2021
ms.topic: troubleshooting
ms.search.form: WHSWorkTable_WHSWorkUnblocking
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-05-15
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: d64ab282972e46e8857581b59e5705dd15667328
ms.sourcegitcommit: 5f5afb46431e1abd8fb6e92e0189914b598dc7fd
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2021
ms.locfileid: "5924195"
---
# <a name="work-isnt-blocked"></a>O trabalho não está bloqueado

Código de erro: WHSUnblockNotBlockedWorkErrorMessage

## <a name="symptoms"></a>Sintomas

O sistema mostra a seguinte mensagem de erro:

> O trabalho com a ID %1 não está bloqueado.

## <a name="cause"></a>Causa

A opção **Ciclo bloqueado** no ciclo está definida como *Não*. O trabalho não pode ser desbloqueado porque não está bloqueado no momento.

## <a name="resolution"></a>Resolução

 Somente o trabalho em que a opção **Ciclo bloqueado** esteja definida como *Sim* pode ser desbloqueado.
