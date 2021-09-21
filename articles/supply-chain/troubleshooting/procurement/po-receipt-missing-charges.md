---
title: Um recibo de ordem de compra não inclui todos os encargos
description: Um recibo de ordem de compra não inclui todos os encargos
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
ms.openlocfilehash: bb567e00ef52269db0dc866148a37c73f0a9827c
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2021
ms.locfileid: "7475538"
---
# <a name="a-purchase-order-receipt-doesnt-include-all-charges"></a>Um recibo de ordem de compra não inclui todos os encargos

## <a name="symptoms"></a>Sintomas

Quando você recebe uma ordem de compra, nem todos os encargos são incluídos no recibo.

### <a name="reproduce-the-issue"></a>Reproduzir o problema

O seguinte procedimento mostra uma forma de reproduzir o problema.

1. Na página **Parâmetros de compras**, na guia **Entrega**, certifique-se de que a opção **Gerar encargos no recibo do produto** está definida como *Sim*.
1. Crie uma ordem de compra que inclui encargos.
1. Confirme uma ordem de compra.
1. Receba a ordem de compra.
1. Examine o total do recibo e compare-o com o total esperado.
1. Observe que nem todos os encargos estão incluídos no recebimento da ordem de compra.

## <a name="resolution"></a>Resolução

A resolução depende da forma como os encargos diversos foram configurados. Para obter informações sobre como configurar encargos diversos de acordo com suas necessidades, consulte a seguinte postagem de blog: [Lançar encargos diversos no momento do recebimento do produto](https://cloudblogs.microsoft.com/dynamics365/no-audience/2014/11/11/post-misc-charges-at-time-of-product-receipt/).
