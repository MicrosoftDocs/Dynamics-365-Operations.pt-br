---
title: Gerar trabalho de separação imediatamente quando a carga é liberada
description: Se o trabalho deve ser gerado imediatamente quando a carga é liberada, você deve configurar o modelo de ciclo adequadamente. Esta página orienta você sobre as etapas.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: fdeb0b27f4d2c1a2cc9f8e0c4ba537cdce604bd2
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2021
ms.locfileid: "7475598"
---
# <a name="picking-work-isnt-generated-immediately-when-outbound-load-is-released"></a>O trabalho de separação não é gerado imediatamente quando a carga de saída é liberada

## <a name="symptoms"></a>Sintomas

Você cria uma carga de saída usando uma ordem de venda ou de transferência e libera a carga para o depósito. No entanto, você nota que nenhum trabalho de separação foi gerado ainda.

## <a name="resolution"></a>Resolução

Se o trabalho deve ser gerado imediatamente quando a carga é liberada, você deve configurar o modelo de ciclo adequadamente. No modelo de ciclo, defina as seguintes opções como *Sim*:

- Automatizar criação da onda
- Processar onda na liberação para o depósito
- Automatizar liberação da onda
