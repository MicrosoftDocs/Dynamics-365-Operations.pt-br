---
title: Ordens de compra para um projeto
description: "Este artigo descreve os diversos métodos que podem ser usados para criar ordens de compra para um projeto. O método usado dependerá da finalidade da ordem de compra e de quando os itens comprados serão consumidos cobrados para um projeto."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 83972
ms.assetid: 247e4d72-610b-4fa5-9873-601ed0f4b2d6
ms.search.region: Global
ms.author: kfend
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: eb32cf1b96dfef75131b8c7541e20a93615a87f7
ms.openlocfilehash: 82305cfe38e7193cece3b9e7784fb81fd40f9c70
ms.lasthandoff: 03/31/2017


---

# <a name="purchase-orders-for-a-project"></a>Ordens de compra para um projeto

[!include[banner](../includes/banner.md)]


Este artigo descreve os diversos métodos que podem ser usados para criar ordens de compra para um projeto. O método usado dependerá da finalidade da ordem de compra e de quando os itens comprados serão consumidos cobrados para um projeto.

No Microsoft Dynamics 365 for Operations, você pode usar vários métodos para criar ordens de compra para um projeto. O método usado dependerá da finalidade da ordem de compra, de quando os itens comprados serão consumidos e de quando eles serão cobrados para um projeto.

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



