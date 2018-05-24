---
title: "Exemplo de dias de redução"
description: "Exemplo de dias de redução."
author: YuyuScheller
manager: AnnBe
ms.date: 05/01/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SMASubscriptionTable
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: YuyuScheller
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 69e4b1b0fe100b17e5b2c59be81604019347956f
ms.contentlocale: pt-br
ms.lasthandoff: 05/08/2018

---


# <a name="reduction-days-example"></a>Exemplo de dias de redução 

[!include [banner](../includes/banner.md)]


Você criou uma transação de subscrição para a subscrição de manutenção de um cliente, conforme descrito na tabela a seguir.

<table>
<colgroup>
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
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
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
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

  



