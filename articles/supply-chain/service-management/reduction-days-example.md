---
title: Exemplo de dias de redução
description: Exemplo de dias de redução.
author: kamaybac
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SMASubscriptionTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 97fb032d02df1dbedaeccec14496cb1d63e8cf70
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/29/2021
ms.locfileid: "7567934"
---
# <a name="reduction-days-example"></a>Exemplo de dias de redução

[!include [banner](../includes/banner.md)]

Você criou uma transação de subscrição para a subscrição de manutenção de um cliente, conforme descrito na tabela a seguir.

<table>
<colgroup>
<col />
<col />
<col />
<col />
<col />
<col />
<col />
<col />
</colgroup>
<thead>
<tr class="header">
<th><p>De</p></th>
<th><p>Até</p></th>
<th><p>Subscrição</p></th>
<th><p>Tipo de subscrição</p></th>
<th><p>Project</p></th>
<th><p>Categoria</p></th>
<th><p>Moeda de venda</p></th>
<th><p>Preço de venda</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>01 de março, 2011</p></td>
<td><p>31 de março, 2011</p></td>
<td><p>NR-2</p></td>
<td><p><strong>Normal</strong></p></td>
<td><p>9013</p></td>
<td><p>SubCat2</p></td>
<td><p>EUR</p></td>
<td><p>200,00</p></td>
</tr>
</tbody>
</table>

O cliente informa que não precisa da cobertura do serviço por dois dias (10 e 11 de março). Você concorda em reduzir esses dois dias da subscrição.

Você cria uma nova transação do tipo **Dias de redução**, conforme descrito na tabela a seguir.

<table>
<colgroup>
<col />
<col />
<col />
<col />
<col />
<col />
<col />
<col />
</colgroup>
<thead>
<tr class="header">
<th><p>De</p></th>
<th><p>Até</p></th>
<th><p>Subscrição</p></th>
<th><p>Tipo de subscrição</p></th>
<th><p>Project</p></th>
<th><p>Categoria</p></th>
<th><p>Moeda de venda</p></th>
<th><p>Preço de venda</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>10 de março, 2011</p></td>
<td><p>11 de março, 2011</p></td>
<td><p>NR-2</p></td>
<td><p><strong>Dias de redução</strong></p></td>
<td><p>9013</p></td>
<td><p>SubCat2</p></td>
<td><p>EUR</p></td>
<td><p>-12,90</p></td>
</tr>
</tbody>
</table>

Quando as transações de março de 2011 são faturadas, o preço de venda de 200 euros é reduzido em 12,90 euros. Portanto, o valor passível de cobrança da transação de subscrição é de 187,10 euros, e duas transações são faturadas no total de 187,10 euros.

## <a name="see-also"></a>Consulte também

[Reduzir os dias em taxas de subscrição](reduce-the-days-on-subscription-fees.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]