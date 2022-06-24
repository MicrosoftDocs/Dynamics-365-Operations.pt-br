---
title: Conversões de moeda intercompanhia
description: Este artigo explica as conversões de moeda para transações intercompanhia
author: Henrikan
ms.date: 09/01/2021
ms.topic: article
ms.search.form: SalesTableListPage, SalesCreateOrder, SalesTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2021-09-01
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: 41bfafc0dcb3bd356931b67dc63b717c0d098116
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8851468"
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
