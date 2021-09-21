---
title: Um desconto de fornecedor não é acumulado com base em faturas
description: Um desconto de fornecedor não é acumulado com base em faturas
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
ms.openlocfilehash: 9d4596a7351969bf181982a24ea1dcc6f5732831
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2021
ms.locfileid: "7475623"
---
# <a name="a-vendor-rebate-isnt-cumulated-based-on-invoices"></a>Um desconto de fornecedor não é acumulado com base em faturas

## <a name="symptoms"></a>Sintomas

Se as faturas lançadas tiverem datas de conclusão diferentes, essas faturas serão refletidas em descontos de fornecedor que são gerados a partir delas.

## <a name="resolution"></a>Resolução

A data de conclusão não é considerada quando o reembolso do fornecedor é calculado. Considere a personalização do sistema para que a data de conclusão e a relação com a fatura sejam mais aparentes em relação ao desconto real do fornecedor.
