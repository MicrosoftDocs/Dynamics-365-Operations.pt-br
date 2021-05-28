---
title: Os pedidos de compra recebidos fisicamente não aparecem no relatório de fechamento de inventário
description: Os pedidos de compra recebidos fisicamente não aparecem no relatório de fechamento de inventário Verificar quantidades em aberto.
author: niwang
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: InventOpenQtyCritical
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 9508d6d75d8ebee7ca10140ed4c4215d7ad1dda7
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026269"
---
# <a name="physically-received-purchase-orders-dont-appear-on-the-inventory-closing-report"></a>Os pedidos de compra recebidos fisicamente não aparecem no relatório de fechamento de inventário

Número da base de dados de conhecimento: 4612595

## <a name="symptoms"></a>Sintomas

Os pedidos de compra recebidos fisicamente não aparecem no relatório de fechamento de inventário **Verificar quantidades em aberto**.

## <a name="resolution"></a>Resolução

O relatório **Verificar quantidades em aberto** mostra transações emitidas que não podem ser liquidadas com base nos recebimentos de inventário atualizados financeiramente a partir da data de fechamento selecionada. Você pode incluir recibos físicos no relatório. Nesse caso, os recibos físicos serão mostrados se puderem cobrir as transações emitidas que não podem ser liquidadas. Para mais informações, consulte [Preparar para realizar fechamento de inventário](/dynamicsax-2012/appuser-itpro/preparing-to-run-inventory-close).
