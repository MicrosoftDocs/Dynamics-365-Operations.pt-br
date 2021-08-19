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
ms.openlocfilehash: 6b4361682246397732e8326b98b1b86ff878664e54c8c352296b0d7eaff6bbbd
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6719542"
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
