---
title: Problemas de conversão de moeda do contrato comercial
description: Os preços do contrato comercial não são recalculados, de acordo com a moeda, quando a moeda é diferente em uma ordem de compra
author: kamaybac
ms.date: 05/31/2021
ms.topic: troubleshooting
ms.search.form: PurchTable, PurchTablePart, PurchRFQTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yanansong
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: 1b6dc36c5f5ee6b611eebd81f378399ce1748c63
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2021
ms.locfileid: "7475544"
---
# <a name="trade-agreement-currency-conversion-issues"></a>Problemas de conversão de moeda do contrato comercial

## <a name="symptoms"></a>Sintomas

Os preços do contrato comercial não são recalculados, de acordo com a moeda, quando a moeda é diferente em uma ordem de compra.

## <a name="resolution"></a>Resolução

O recurso *Moeda genérica* permite definir preços e descontos em apenas uma moeda. Em seguida, você pode converter para outras moedas, conforme necessário. Além disso, após a conversão ser concluída, o recurso pode aplicar o arredondamento inteligente automaticamente.
