---
title: O campo "Data do último teste" não atualiza quando várias ordens de qualidade são criadas
description: O campo "Data do último teste" não atualiza quando várias ordens de qualidade são criadas.
author: niwang
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: InventBatch
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 46523c55f4fd42b0985397752f0c62a3e1a55e177f2308e20b7064e339758269
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6742019"
---
# <a name="the-last-tested-date-field-isnt-updated-when-multiple-quality-orders-are-created"></a>O campo "Data do último teste" não atualiza quando várias ordens de qualidade são criadas

Número de KB: 4612803

## <a name="symptoms"></a>Sintomas

O campo **Data do último teste** não atualiza quando várias ordens de qualidade são criadas.

## <a name="resolution"></a>Resolução

O sistema está agindo como esperado. A data do último teste não está relacionada a ordens de qualidade. Ela guarda a data em que os bens acabados foram comprados ou fabricados pela primeira vez. Esta data é usada para calcular a data de aviso de validade.
