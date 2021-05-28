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
ms.openlocfilehash: 6f796bdaa88d32b1c58dd8a4bca19f0ce4f3943d
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026280"
---
# <a name="the-last-tested-date-field-isnt-updated-when-multiple-quality-orders-are-created"></a>O campo "Data do último teste" não atualiza quando várias ordens de qualidade são criadas

Número de KB: 4612803

## <a name="symptoms"></a>Sintomas

O campo **Data do último teste** não atualiza quando várias ordens de qualidade são criadas.

## <a name="resolution"></a>Resolução

O sistema está agindo como esperado. A data do último teste não está relacionada a ordens de qualidade. Ela guarda a data em que os bens acabados foram comprados ou fabricados pela primeira vez. Esta data é usada para calcular a data de aviso de validade.
