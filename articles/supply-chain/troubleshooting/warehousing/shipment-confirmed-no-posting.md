---
title: A remessa para carga foi confirmada, mas nenhuma linha foi lançada
description: A confirmação da remessa não afeta o lançamento. Ela apenas atualiza a remessa e o status da carga. O lançamento deve ocorrer em um processo separado.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: e754f1461672c1e9f2d8dd1a7ceffc81f3809120
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2021
ms.locfileid: "7475615"
---
# <a name="shipment-for-load-has-been-confirmed-but-no-lines-are-posted"></a>A remessa para carga foi confirmada, mas nenhuma linha foi lançada

## <a name="symptoms"></a>Sintomas

Ao trabalhar com operações de depósito de saída, talvez seja exibida a seguinte mensagem:

> 1% da remessa da carga foi confirmado.

No entanto, não ocorreu nenhum lançamento adicional.

## <a name="resolution"></a>Resolução

Isso ocorre por design. A confirmação da remessa não afeta o lançamento. Ela apenas atualiza a remessa e o status da carga. O lançamento deve ocorrer em um processo separado.
