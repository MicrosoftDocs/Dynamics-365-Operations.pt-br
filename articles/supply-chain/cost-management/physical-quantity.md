---
title: Valores de objeto de estoque
description: Este artigo fornece informações sobre como os valores de um objeto do estoque são calculados.
author: JennySong-SH
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventCostOnhandItem
audience: Application User
ms.reviewer: kamaybac
ms.custom: 19111
ms.assetid: 56a7c8ba-bf4a-4b1d-918d-56bb96926c4f
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: yanansong
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4a5dd487b9213f8f1289412a6a7b8112e6b57df6
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/03/2022
ms.locfileid: "8670374"
---
# <a name="inventory-object-values"></a>Valores de objeto de estoque

[!include [banner](../includes/banner.md)]

Este artigo fornece informações sobre como os valores de um objeto do estoque são calculados. 

Uma nova funcionalidade chamada de **quantidade física** permite visualizar os valores de um objeto de estoque específico. 

Um objeto de custo representa o nível da entidade onde a contabilidade de estoque é executada. Para obter mais informações sobre os objetos de custo, consulte [Objetos de custo](cost-object.md). 

Para visualizar os valores de um objeto de estoque específico, clique em **Quantidade física** na página **Objeto de custo**. Veja aqui como o valor de um objeto de estoque é calculado: 

Objeto de estoque. Valor = Objeto de custo. Custo unitário médio x Objeto de estoque.Quantidade 

Os exemplos a seguir mostram como os valores de um objeto de estoque e de um objeto de custo são calculados. Dois eventos de recebimento de produtos são registrados para o item A:

-   Recebimento de produtos 1: Quantidade = 100 pcs., Valor = $1.000,00, Local = 1, Depósito = 11, Nº do lote = B1
-   Recebimento de produtos 2 = Quantidade = 50 pcs., Valor = $800,00, Local = 1, Depósito = 11, Nº do lote = B2

A tabela a seguir mostra o resultado do cálculo para um objeto de custo. Você pode exibir o resultado na página **Objeto de custo**.

<table>
<colgroup>
<col width="14%" />
<col width="14%" />
<col width="14%" />
<col width="14%" />
<col width="14%" />
<col width="14%" />
<col width="14%" />
</colgroup>
<thead>
<tr class="header">
<th>Tipo de Objeto</th>
<th>Nº do item</th>
<th>Local</th>
<th>Quantidade</th>
<th>Unidade de estoque</th>
<th>Valor</th>
<th>Custo unitário médio</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Objeto de custo</td>
<td>S</td>
<td>1</td>
<td>150</td>
<td>Pçs.</td>
<td><p>$1.800,00</p></td>
<td><p>$12,00</p></td>
</tr>
</tbody>
</table>

A tabela a seguir mostra o resultado do cálculo para um objeto de estoque. Você pode exibir o resultado clicando em **Quantidade física** na página **Objeto de custo**.

<table>
<colgroup>
<col width="11%" />
<col width="11%" />
<col width="11%" />
<col width="11%" />
<col width="11%" />
<col width="11%" />
<col width="11%" />
<col width="11%" />
<col width="11%" />
</colgroup>
<thead>
<tr class="header">
<th>Tipo de Objeto</th>
<th>Nº do item</th>
<th>Local</th>
<th>Depósito</th>
<th>Nº do lote</th>
<th>Quantidade</th>
<th>Unidade de estoque</th>
<th>Valor</th>
<th>Custo unitário médio</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Objeto de estoque</td>
<td>S</td>
<td>1</td>
<td>11</td>
<td>B1</td>
<td>100</td>
<td>Pçs.</td>
<td><p>$1.200,00</p></td>
<td><p>$12,00</p></td>
</tr>
<tr class="even">
<td>Objeto de estoque</td>
<td>A</td>
<td>1</td>
<td>11</td>
<td>B2</td>
<td>50</td>
<td>Pçs.</td>
<td><p>$600,00</p></td>
<td><p>$12,00</p></td>
</tr>
</tbody>
</table>



## <a name="additional-resources"></a>Recursos adicionais

[Objetos de custo](cost-object.md)

[Entradas de custo](cost-entries.md)

[Novidades e alterações](../../fin-ops-core/fin-ops/get-started/whats-new-changed.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]