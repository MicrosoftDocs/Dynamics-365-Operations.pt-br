---
title: O valor de atraso não é atualizado quando você reprograma uma ordem planejada
description: O valor de atraso não é atualizado quando você reprograma uma ordem planejada
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
ms.openlocfilehash: 566702913774cf002ab38e367f690a479d968657
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2021
ms.locfileid: "7475603"
---
# <a name="the-delay-value-isnt-updated-when-you-reschedule-a-planned-order"></a>O valor de atraso não é atualizado quando você reprograma uma ordem planejada

## <a name="symptoms"></a>Sintomas

O valor de atraso não é atualizado quando você reprograma uma ordem planejada.

## <a name="resolution"></a>Resolução

Para atualizar o atraso de ordens planejadas, abra a caixa de diálogo **Reprogramação** para a ordem planejada. Na FastTab **Detalhamento**, verifique se a opção **Executar detalhamento após reprogramação** está definida como *Sim*.
