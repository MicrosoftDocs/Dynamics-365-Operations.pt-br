---
title: O aviso de reserva automática é mostrado com o estoque disponível
description: Quando você usar um item em um depósito que não tem os processos de depósito habilitados, o aviso de reserva automática será exibido. Especifique todas as dimensões acima do Local.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: a15502ce8c5bc61d37cedd746985176408a2f362
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2021
ms.locfileid: "7475617"
---
# <a name="auto-reservation-prompt-for-batch-number-is-shown-even-with-available-inventory"></a>O aviso de reserva automática para número de lote é mostrado mesmo com o estoque disponível

## <a name="symptoms"></a>Sintomas

Quando você usa um item com uma hierarquia de reservas *acima do número do lote* em um depósito que não tenha habilitado processos de depósito, e se a reserva automática estiver habilitada, o aviso de reserva automática para um número do lote será mostrado mesmo se apenas um lote estiver disponível para separação.

No entanto, quando você usar o mesmo item em um depósito onde os processos de depósito estiverem habilitados, o prompt de reserva automática não será exibido.

## <a name="resolution"></a>Resolução

Se uma hierarquia de reserva for definida como um *acima do número do lote* ou *acima do número de série*, a dimensão referenciada (**número do lote** ou **Número de série**) sempre deverá ser especificada em ordens de demanda. Talvez os processos de depósito consigam completar as informações se um único número do lote ou de série estiver disponível. No entanto, como o depósito não está habilitado para processos de depósito, o usuário sempre deverá especificar todas as dimensões acima do **Local**.
