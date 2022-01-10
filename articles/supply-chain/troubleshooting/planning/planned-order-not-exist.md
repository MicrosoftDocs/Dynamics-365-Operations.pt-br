---
title: O sistema não consegue encontrar um pedido planejado durante operações em vários pedidos
description: O erro "O pedido planejado não existe" ocorre quando você executa operações em vários pedidos planejados e pelo menos dois deles pertencem à mesma ID do item.
author: t-benebo
ms.date: 12/07/2021
ms.topic: troubleshooting
ms.search.form: ReqTransPo_ReqTransPoMarkChangeType
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2021-12-07
ms.dyn365.ops.version: 10.0.24
ms.openlocfilehash: 0ece4a331b63b86e896c5b337a58185ed3ea1049
ms.sourcegitcommit: 008779c530798f563fe216810d34b2d56f2c8d3c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/14/2021
ms.locfileid: "7920789"
---
# <a name="the-system-cant-find-a-planned-order-during-operations-on-multiple-orders"></a>O sistema não consegue encontrar um pedido planejado durante operações em vários pedidos

Código de erro: SYS24774

## <a name="symptoms"></a>Sintomas

Você recebe a seguinte mensagem de erro ao tentar executar uma operação em vários pedidos planejados ao mesmo tempo e pelo menos dois deles pertencerem à mesma ID do item. Por exemplo, o erro pode ocorrer quando os pedidos são firmados ou o tipo de pedido é alterado.

> A ordem planejada %1 não existe.

## <a name="cause"></a>Causa

Quando o sistema firma ou altera o tipo de pedido, ele deve reconsiderar os pedidos planejados existentes para o item para verificar se o fornecimento planejado corresponde à demanda e ao fornecimento existente. Como parte desse processo, o sistema recria pedidos planejados para o item. Portanto, o segundo pedido planejado que o sistema espera processar não existe mais.

## <a name="workaround"></a>Solução alternativa

Aprove os pedidos antes de processá-los. Dessa forma, os pedidos não serão excluídos quando o sistema processar o primeiro pedido do item.
