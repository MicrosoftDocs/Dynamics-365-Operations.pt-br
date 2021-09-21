---
title: Não é possível liberar uma carga para a quantidade parcial com hierarquia acima do lote
description: Quando você usar um item com a hierarquia de reserva acima do lote, as linhas de carregamento deverão especificar dimensões acima do local para que o estoque seja alocado.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: eb7e71cc271903cb689c33777b72862246f2dd42
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2021
ms.locfileid: "7475555"
---
# <a name="cant-release-a-load-for-partial-quantity-with-batch-above-reservation-hierarchy"></a>Não é possível liberar uma carga para a quantidade parcial com hierarquia de reserva acima do lote

## <a name="symptoms"></a>Sintomas

Quando você usa um item com uma hierarquia de reservas *acima do número do lote*, o comando **Liberar para o depósito** na página **Bancada do planejamento de carga** não funcionará se você tentar liberar uma carga para uma quantidade parcial. Você receberá a seguinte mensagem de erro:

> Para serem atribuídas ao ciclo, as linhas de carga deverão especificar as dimensões acima do local. Para atribuir essas dimensões, reserve e recrie a linha de carga.

Contudo, quando usar um item com uma hierarquia de reservas *acima do número do lote*, você poderá liberar uma carga para a quantidade parcial da página **Bancada do planejamento de carga**.

## <a name="cause"></a>Causa

Quando uma dimensão estiver acima da dimensão **Local** na hierarquia de reservas, ela deverá ser especificada antes da liberação para o depósito. O estoque só poderá ser alocado com êxito se não houver intervalos nas dimensões acima do local.

## <a name="resolution"></a>Resolução

Verifique se todas as dimensões acima de **Local** foram atribuídas, reservando e recriando a linha de carregamento.
