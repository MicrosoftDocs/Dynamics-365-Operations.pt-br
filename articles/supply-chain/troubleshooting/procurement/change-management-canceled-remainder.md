---
title: Cancelar a entrega pendente move a ordem de compra para um estado Confirmado
description: Se a entrega pendente for cancelada em uma ordem de compra na qual o gerenciamento de alterações está ativado, a ordem de compra vai para um estado Confirmado
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
ms.openlocfilehash: 1d8b331bc5699487dff3491d65daa36293f3212f
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2021
ms.locfileid: "7475592"
---
# <a name="cancelling-delivery-remainder-moves-purchase-order-to-a-confirmed-state"></a>Cancelar a entrega pendente move a ordem de compra para um estado Confirmado

## <a name="symptoms"></a>Sintomas

Para uma ordem de compra sujeita ao gerenciamento de alterações, se a única alteração solicitada for o cancelamento de uma entrega pendente em uma ou mais linhas, a ordem de compra irá diretamente para um estado *Confirmado* quando for aprovada e nenhum diário será criado.

## <a name="resolution"></a>Resolução

O cancelamento de uma pendência de entrega não afeta o conteúdo do diário de confirmação. Essa funcionalidade deve ser usada quando a linha foi parcialmente recebida e a qualidade final deve ser cancelada na etapa do processo após a confirmação da ordem de compra com o fornecedor.

Se isso deve ser refletido na confirmação da ordem de compra, a quantidade deve ser ajustada na linha da ordem de compra para que a confirmação seja obrigatória. Como alternativa, se nada foi recebido na linha, a quantidade pode ser removida. Nesse caso, será necessário reconfirmar.
