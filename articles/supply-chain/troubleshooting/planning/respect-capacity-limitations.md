---
title: O planejamento mestre está agendando mais do que a capacidade disponível
description: O planejamento mestre não parece respeitar as limitações de capacidade e está programando mais do que a capacidade disponível
author: ChristianRytt
ms.date: 05/31/2021
ms.topic: troubleshooting
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: 48b3d179bb923ff6f6cc5b6be291408b3eb34d98
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2021
ms.locfileid: "7475594"
---
# <a name="master-planning-is-scheduling-more-than-the-available-capacity"></a>O planejamento mestre está agendando mais do que a capacidade disponível

## <a name="symptoms"></a>Sintomas

O planejamento mestre não parece respeitar as limitações de capacidade e está programando mais do que a capacidade disponível.

Quando você usa a programação de operação em que há capacidade finita e a rota especifica uma combinação de requisitos para um grupo de recursos e recursos individuais, existe uma pequena chance de reserva excessiva devida à forma como o algoritmo valida os conflitos de capacidade. Essa reserva excessiva pode ocorrer quando você usa auxiliares para executar o planejamento mestre. É mais provável que ela ocorra se houver muitos trabalhos com um tempo de execução relativamente curto.

## <a name="resolution"></a>Resolução

Se for essencial que nenhuma reserva reserva excessiva ocorra na programação da operação, você pode tornar a parte da programação do planejamento mestre em thread único ativando a opção **Capacidade finita precisa para programação de operação** na página **Parâmetros de planejamento mestre**. Essa opção não está disponível por padrão. Você deve adicioná-la manualmente à página usando recursos de personalização. Quando você usa essa opção, a programação será executada mais lentamente pela falta de processamento paralelo.
