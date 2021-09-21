---
title: Estoque disponível não considerado para itens acima do lote
description: Alguns modelos de slots não consideram o estoque disponível atual para itens acima do lote. O lote ou o número de série deve ser especificado na ordem de demanda.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: df5642b32f5e053144230eab3dbcf633f526279a
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2021
ms.locfileid: "7475580"
---
# <a name="slotting-templates-dont-consider-on-hand-inventory-for-batch-above-items"></a>Os modelos de slots não consideram estoque disponível para itens acima do lote

## <a name="symptoms"></a>Sintomas

Os modelos de slots com o critério de slot *Considerar disponível* não consideram o estoque disponível atual para itens *acima do número do lote*. Eles só o considerarão se o número do lote for especificado na linha da ordem de venda.

No entanto, quando você usa itens *abaixo do número do lote*, o estoque disponível atual é considerado esperado.

Para obter mais informações, consulte [Slots de depósito](/dynamics365/supply-chain/warehousing/warehouse-slotting).

## <a name="resolution"></a>Resolução

O cabeçalho do modelo de slot pode ser definido para a estratégia de demanda *Encomendado*, *Reservado* ou *Liberado*. Para a estratégia de demanda *Encomendado*, os mesmos requisitos de hierarquia de reservas se aplicam para reserva ou liberação para processos de depósito. Portanto, para os itens com hierarquias de reservas *acima do número do lote* e *abaixo do número de série*, o número do lote ou de série deverá ser especificado na ordem de demanda (venda ou transferência).

Como alternativa, a estratégia de demanda *Reservado* poderá ser usada para selecionar o número do lote ou de série antes que a demanda de slots de depósito seja gerada.
