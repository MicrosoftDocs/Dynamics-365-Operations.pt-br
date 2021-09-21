---
title: Não é possível cancelar a reserva de estoque em uma linha da ordem de venda
description: Se houver trabalho em aberto em uma linha de venda e você tentar cancelar a reserva do estoque na linha, haverá um erro. Conclua ou exclua o trabalho para liberar a reserva.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 1a042065dc4cd637aff58e55cf16179b7022f6ca
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2021
ms.locfileid: "7475589"
---
# <a name="cant-unreserve-inventory-on-a-sales-order-line"></a>Não é possível cancelar a reserva de estoque em uma linha da ordem de venda

## <a name="symptoms"></a>Sintomas

Se houver trabalho em aberto em uma linha da ordem de venda e você tentar cancelar a reserva do estoque nessa linha, será exibida a seguinte mensagem de erro:

> As reservas não podem ser removidas porque há um trabalho criado com base nas reservas.

## <a name="resolution"></a>Resolução

Investigue se existe trabalho de grupo de embalagem aberto para mudar o item de uma estação de embalagem para outro local (como *Baydoor*). Revise os registros nas páginas **Log de histórico de criação de trabalho** e **Detalhes do trabalho** para determinar o que está reservando fisicamente o estoque e, depois, conclua ou exclua o trabalho para liberar a reserva.
