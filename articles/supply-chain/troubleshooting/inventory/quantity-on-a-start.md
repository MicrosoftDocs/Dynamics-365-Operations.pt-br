---
title: A quantidade em um pedido de quarentena iniciado não é atualizado quando o pedido é dividido
description: Quando você cria um pedido de quarentena e tenta dividi-lo, a quantidade do pedido não é atualizada para a quantidade dividida restante.
author: niwang
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: InventQuarantineOrder
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: shawan
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: a8af535257ce217629d5ba92e624623c3ea39345
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026282"
---
# <a name="quantity-on-a-started-quarantine-order-isnt-updated-when-the-order-is-split"></a>A quantidade em um pedido de quarentena iniciado não é atualizado quando o pedido é dividido

Número da base de dados de conhecimento: 4613113

## <a name="symptoms"></a>Sintomas

Quando você cria um pedido de quarentena e tenta dividi-lo, a quantidade do pedido não é atualizada para a quantidade restante após a divisão.

## <a name="resolution"></a>Resolução

O sistema não altera a quantidade original de um pedido de quarentena para garantir que você possa acompanhar a quantidade original que foi criada para esse pedido de quarentena. No entanto, o sistema acompanha a quantidade que foi dividida de um pedido de quarentena. Para fazer esse acompanhamento, ele usa um campo do banco de dados chamado `QuantityThatHasSplitIntoOtherQuarantineOrders`. No entanto, este campo não está visível na interface de usuário (UI).
