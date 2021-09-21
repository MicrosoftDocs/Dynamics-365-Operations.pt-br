---
title: Ordens de compra importadas mostram números de linha incorretos
description: Quando as ordens de compra são importadas por meio do gerenciamento de dados, os números de linha da ordem de compra não seguem o incremento definido nos parâmetros do sistema
author: kamaybac
ms.date: 05/31/2021
ms.topic: troubleshooting
ms.search.form: PurchTable, PurchTablePart
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yanansong
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: e1cf5cf1d04824213f495ac3ebf556796c96611a
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2021
ms.locfileid: "7475535"
---
# <a name="imported-purchase-orders-show-incorrect-line-numbers"></a>Ordens de compra importadas mostram números de linha incorretos

## <a name="symptoms"></a>Sintomas

Por padrão, os números de linha gerados automaticamente para linhas de ordem de compra que são importadas por meio da entidade de dados *Linhas da ordem de compra V2* não usam o incremento de número de linha do sistema especificado nos parâmetros do sistema. Se você criar manualmente uma ordem de compra e adicionar linhas por meio da interface do usuário (IU), os números de linha serão incrementados corretamente. No entanto, se você usar a estrutura de gerenciamento de dados (DMF), elas não serão incrementadas corretamente.

Esse problema ocorre porque, quando você importa linhas via DMF, se os números de linha ainda não estiverem atribuídos na entidade importada, o sistema usará o método de DMF para atribuí-los. Esse método sempre incrementa os números de linha em um.

## <a name="workaround"></a>Solução alternativa

Certifique-se de que os números de linha desejados já tenham sido fornecidos nos campos de número de linha da entidade de dados quando você importar as linhas da ordem de compra. Nesse caso, a DMF não substituirá os números de linha.
