---
title: Trabalho de separação bloqueado devido ao trabalho de reabastecimento não concluído
description: O trabalho de separação pode ser bloqueado por causa do trabalho de reabastecimento dependente. Conclua o trabalho de reabastecimento e processe o trabalho de separação.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 53b50d1e3e2d7bb64e78514affe80076ddcb9052
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2021
ms.locfileid: "7475626"
---
# <a name="picking-work-cant-be-unblocked-because-of-unfinished-replenishment-work"></a>Não é possível desbloquear o trabalho de separação por causa do trabalho de reabastecimento não concluído

## <a name="symptoms"></a>Sintomas

Ao usar o reabastecimento de demanda em ciclos, o trabalho de separação pode ser bloqueado por causa do trabalho de reabastecimento dependente. Se um local de separação precisar ser reabastecido para atender à demanda da ordem de origem, o sistema criará o trabalho de reabastecimento e o trabalho de separação. No entanto, ele bloqueia o trabalho de separação até o trabalho de reabastecimento ser concluído, e a seguinte mensagem de erro será exibida:

> Não é possível desbloquear o trabalho %1 porque ele tem um trabalho de reabastecimento não concluído.

## <a name="resolution"></a>Resolução

Esse comportamento é intencional, porque o local de separação não terá estoque suficiente a menos que o trabalho de reabastecimento seja concluído. Conclua o trabalho de reabastecimento e processe o trabalho de separação.
