---
title: Os preços unitários das ordens de compra não são calculados com base na conversão de unidades
description: Os preços unitários das ordens de compra não são calculados com base na conversão de unidades
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
ms.openlocfilehash: 4695f4661c3abb8ab38e3ca74b513e8529e37d20
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2021
ms.locfileid: "7475575"
---
# <a name="unit-prices-on-purchase-orders-arent-calculated-based-on-the-unit-conversion"></a>Os preços unitários das ordens de compra não são calculados com base na conversão de unidades

## <a name="symptoms"></a>Sintomas

Quando uma unidade é alterada em uma ordem de compra, os preços do contrato comercial não são recalculados de acordo com as definições de conversão de unidades.

## <a name="cause"></a>Causa

Os preços sempre obtidos de contratos comerciais (ou outras configurações de preço no sistema, como contratos de venda ou preços de item), e são definidos para uma unidade.

Se a unidade for alterada em uma linha da ordem, o sistema procurará um preço para a nova unidade e aplicará esse preço. Se nenhum preço for encontrado para a unidade, o sistema não aplicará um preço. A conversão de unidades não pode ser usada para recalcular o preço em outra unidade. Teoricamente, o preço de uma caixa de dez pode não ser igual a dez vezes o preço de uma caixa.

## <a name="workaround"></a>Solução alternativa

Uma forma de solucionar esse problema é verificar se há contratos comerciais para as unidades esperadas que serão usadas nas linhas da ordem para o item.
