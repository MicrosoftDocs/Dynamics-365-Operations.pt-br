---
title: Ordens de compra para um projeto
description: "Este artigo descreve os diversos métodos que podem ser usados para criar ordens de compra para um projeto. O método usado dependerá da finalidade da ordem de compra e de quando os itens comprados serão consumidos cobrados para um projeto."
author: KimANelson
manager: AnnBe
ms.date: 09/14/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 83972
ms.assetid: 247e4d72-610b-4fa5-9873-601ed0f4b2d6
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 985a57ae9fb116b1c4514b836b35c5da0f8838fd
ms.contentlocale: pt-br
ms.lasthandoff: 09/29/2017

---

# <a name="purchase-orders-for-a-project"></a>Ordens de compra para um projeto

[!include[banner](../includes/banner.md)]


Este artigo descreve os diversos métodos que podem ser usados para criar ordens de compra para um projeto. O método usado dependerá da finalidade da ordem de compra e de quando os itens comprados serão consumidos cobrados para um projeto.

No Microsoft Dynamics 365 for Finance and Operations, edição Enterprise, você pode usar vários métodos para criar ordens de compra para um projeto. O método usado dependerá da finalidade da ordem de compra, de quando os itens comprados serão consumidos e de quando eles serão cobrados para um projeto.

### <a name="methods-for-creating-a-purchase-order"></a>Métodos para criar uma ordem de compra

Você pode usar um dos seguintes métodos para criar uma ordem de compra em Gerenciamento e contabilidade de projetos. A finalidade da ordem de compra determina quando ela é consumida e, portanto, quando os itens são cobrados para um projeto.

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th>Método</th>
<th>Finalidade</th>
<th>Consumo de itens</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Crie uma ordem de compra diretamente de um projeto.</td>
<td>Use este método para comprar itens de um fornecedor externo para consumo em um projeto. Você pode criar a ordem de compra de duas maneiras:
<ul>
<li>No próprio projeto. Neste caso o projeto já está definido para a ordem de compra.</li>
<li>Navegando na ordem de compra de projeto. Você deve selecionar o fornecedor e o projeto para os quais a ordem de compra será criada.</li>
</ul></td>
<td>Os itens serão consumidos quando a nota fiscal do fornecedor for atualizada.</td>
</tr>
<tr class="even">
<td>Criar uma ordem de compra a partir de uma ordem de venda.</td>
<td>Use este método para comprar itens ao criar uma ordem de venda de um projeto.</td>
<td>Os itens serão consumidos quando a ordem de venda for faturada para o cliente.</td>
</tr>
<tr class="odd">
<td>Criar uma ordem de compra a partir de uma requisição de itens.</td>
<td>Use este método para comprar itens ao criar uma requisição de itens a partir de um projeto.</td>
<td>Os itens serão consumidos quando a guia de remessa da requisição de itens for atualizada.</td>
</tr>
</tbody>
</table>

> [!NOTE] 
> Quando você atualiza a fatura do fornecedor ou a guia de remessa, o programa solicita a atualização da guia de remessa na requisição de itens.

Para saber mais, consulte [Receber itens na ordem de compra da requisição de itens](tasks/receive-items-purchase-order-item-requirement.md).


