---
title: As ordens de produção não mostradas na página Marcação
description: Algumas ordens de produção não são mostradas na página Marcação. Este tópico explica as três configurações de produtos que não estão disponíveis para marcação.
author: SmithaNataraj
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 87507e91d3feb2557e7ba771b8e34ff7ca105749
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2021
ms.locfileid: "7475526"
---
# <a name="production-orders-arent-shown-on-the-marking-page"></a>As ordens de produção não são mostradas na página Marcação

## <a name="symptoms"></a>Sintomas

Ao trabalhar com a fabricação discreta, algumas ordens de produção não são mostradas na página **Marcação**.

## <a name="resolution"></a>Resolução

Produtos que possuem as seguintes configurações não estão disponíveis para marcação. Portanto, eles não serão mostrados na página **Marcação**:

- Os produtos são definidos como produtos do tipo de *peso variável*.
- Eles são habilitados para os processos avançados de depósito.
- Eles são configurados para serem controlados pelo princípio *Custo padrão*.
