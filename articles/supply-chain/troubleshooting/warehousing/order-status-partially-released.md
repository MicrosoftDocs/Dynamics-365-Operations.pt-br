---
title: O status da ordem permanece Parcialmente liberado mesmo depois de ser faturada
description: Em alguns casos, o status de liberação de uma ordem de venda permanece Parcialmente liberada, mesmo depois que a ordem de venda foi faturada. Esta página explica o motivo e uma possível solução.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 8bfe7ecfd4beb6e77e8dd1e23ccd896d067bdb51
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2021
ms.locfileid: "7475590"
---
# <a name="order-status-remains-partially-released-even-after-the-sales-order-is-invoiced"></a>O status da ordem permanece Parcialmente liberado mesmo depois que a ordem de venda é faturada

## <a name="symptoms"></a>Sintomas

Uma ordem de venda é uma ordem de entrega, mas um ou mais itens contidos nela possuem um modo de entrega diferente. Depois que a ordem é faturada, ela ainda tem um status de liberação de *Parcialmente liberada*.

Por exemplo, uma ordem de venda tem dois itens: um para entrega e outro para retirada. A entrega e a retirada foram realizadas. Portanto, ambas as linhas foram faturadas. No entanto, o status de liberação ainda é mostrado como *Parcialmente liberada*, o que é enganoso.

## <a name="workaround"></a>Solução alternativa

O status de liberação se aplica apenas a linhas de ordem em que os itens estão habilitados para gerenciamento de depósito. Portanto, o status de liberação permanece *Parcialmente liberada* neste cenário. A Microsoft avaliou esse problema e determinou que é uma limitação de recurso. Uma extensão pode ser adicionada como parte da guia de remessa e do processo de faturamento para atualizar o status de liberação.
