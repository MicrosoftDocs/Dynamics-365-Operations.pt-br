---
title: Condições de fluxo de trabalho do diário de estoque se aplicam no nível do diário, não no nível da linha
description: As condições de fluxo de trabalho do diário de estoque se aplicam apenas no nível do diário, não no nível da linha.
author: sherry-zheng
ms.date: 05/31/2021
ms.topic: troubleshooting
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.16
ms.openlocfilehash: 46bdde7f09c639fbefd46162431762b056d521ae
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2021
ms.locfileid: "7475579"
---
# <a name="inventory-journal-workflow-conditions-apply-at-the-journal-level-not-line-level"></a>Condições de fluxo de trabalho do diário de estoque se aplicam no nível do diário, não no nível da linha

## <a name="symptoms"></a>Sintomas

Você pode enfrentar esse problema se, por exemplo, tentar configurar uma condição de fluxo de trabalho do diário de estoque no valor de custo. Configure a condição de forma que a etapa 1 seja executada apenas quando o valor de custo for menor do que 100. Depois, configure outra condição de forma que a etapa 2 seja executada apenas quando o valor de custo for maior do que ou igual a 100. Então, quando o fluxo de trabalho for executado, seu histórico mostrará somente uma linha, e a primeira condição será sempre avaliada como *verdadeira*, independentemente do valor enviado.

## <a name="workaround"></a>Solução alternativa

Na versão atual, as condições de fluxo de trabalho de estoque se aplicam apenas no nível do diário, não no nível da linha. Esse comportamento é por design. É recomendável definir seus critérios de condição somente em atributos no nível do diário.
