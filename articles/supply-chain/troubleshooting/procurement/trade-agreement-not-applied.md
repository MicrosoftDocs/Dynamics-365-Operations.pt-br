---
title: As condições do contrato comercial não são aplicadas às linhas da ordem importadas
description: Os preços e descontos do contrato comercial não são aplicados a linhas de ordem de compra ou de venda que são importadas por meio do gerenciamento de dados
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
ms.openlocfilehash: fef38819efaff2f2a927cf09fc7f469490149574
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2021
ms.locfileid: "7475608"
---
# <a name="trade-agreement-conditions-arent-applied-to-imported-order-lines"></a>As condições do contrato comercial não são aplicadas às linhas da ordem importadas

## <a name="symptoms"></a>Sintomas

Os contratos comerciais que não são aplicados a linhas de ordem de compra ou de venda não são aplicados a linhas que são importadas por meio do gerenciamento de dados. No entanto, os mesmos contratos comerciais são aplicados a linhas de ordem de compra ou de venda que são criadas manualmente.

## <a name="cause"></a>Causa

Se as linhas da ordem de compra que são importadas por meio do gerenciamento de dados já incluírem informações de preço, o contrato comercial não será reavaliado para essas linhas. Por exemplo, se **Porcentagem de desconto de linha** ou qualquer um dos valores de preço e desconto for definido para uma linha, os contratos comerciais não serão pesquisados para essa linha.

## <a name="workaround"></a>Solução alternativa

Esse comportamento é esperado e é semelhante para ordens de venda e ordens de compra.

Para solucionar o problema, importe as linhas da ordem de compra sem definir as informações de preço. Os contratos comerciais serão aplicados, e as linhas da ordem de compra serão atualizadas com base nos contratos comerciais definidos.
