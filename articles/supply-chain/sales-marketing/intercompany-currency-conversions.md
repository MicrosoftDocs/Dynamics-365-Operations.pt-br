---
title: Conversões de moeda intercompanhia
description: Este tópico explica as conversões de moeda para transações intercompanhia
author: GalynaFedorova
ms.date: 09/01/2021
ms.topic: article
ms.search.form: SalesTableListPage, SalesCreateOrder, SalesTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: v-gfedorova
ms.search.validFrom: 2021-09-01
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: 540849003d532ef2f0905c18332d9cb82a04cf7c
ms.sourcegitcommit: fcfd85a508c0de52cfe11d1986892219e39ef406
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/23/2021
ms.locfileid: "7548111"
---
# <a name="intercompany-currency-conversions"></a>Conversões de moeda intercompanhia

[!include [banner](../../includes/banner.md)]

Quando o código de moeda na ordem de venda original e na ordem de compra intercompanhia forem diferentes, os campos a seguir serão convertidos em moeda se a sincronização estiver habilitada:

- **Preço unitário**
- **Encargos de venda** ou **Encargos sobre compras**
- **Desconto**
- **Desconto combinado**

Em seguida, esses campos serão sincronizados com a linha da ordem de venda intercompanhia.

No entanto, como a moeda na ordem de compra intercompanhia e na ordem de venda intercompanhia está sempre sincronizada, os campos a seguir serão sincronizados sem usar a conversão de moeda:

- **Preço unitário**
- **Encargos de venda** ou **Encargos sobre compras**
- **Desconto**
- **Porcentagem de desconto**
- **Desconto combinado**
- **Porcentagem de desconto combinado**

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
