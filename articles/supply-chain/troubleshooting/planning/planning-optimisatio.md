---
title: O pedido de compra planejado é criado quando uma compra existe em dias negativos
description: Se o código de cobertura for Mín/Máx, a Otimização de planejamento cria um pedido de compra planejado quando uma compra existe em dias negativos.
author: ChristianRytt
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: ReqTransPo,MpsIntegrationParameters
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: ilebedev
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 826496c2de956ff949dd79ab8aa643053719bf75
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026275"
---
# <a name="planned-purchase-order-is-created-when-a-purchase-exists-within-negative-days"></a>O pedido de compra planejado é criado quando uma compra existe em dias negativos

Número da base de dados de conhecimento: 4614298

## <a name="symptoms"></a>Sintomas

Se o código de cobertura for *Mín/Máx*, a Otimização de planejamento cria um pedido de compra planejado quando uma compra existe em dias negativos.

## <a name="resolution"></a>Resolução

A Otimização de planejamento não dá suporte a dias negativos. Entretanto, isso sempre garante que os pedidos planejados não serão agendados dentro do prazo relacionado à data atual. Por exemplo, o prazo de compra é de 10 dias, e espera-se que um pedido de compra chegue 8 dias a contar de hoje. Neste caso, o pedido de compra será usado como oferta para a demanda que é 5 dias a contar de hoje.

Portanto, recomendamos que você ajuste seus prazos para cobrir todas (ou quase todas) as suas situações.
