---
title: Especificar o destino dos itens devolvidos
description: Especificar o destino dos itens devolvidos.
author: ShylaThompson
manager: AnnBe
ms.date: 05/07/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventQuarantineOrder
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: ShylaThompson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e6fcdfec083aeb9c58d63f6e03542758e4d07e4d
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2019
ms.locfileid: "325057"
---
# <a name="specify-how-to-dispose-of-returned-items"></a>Especificar o destino dos itens devolvidos 

[!include [banner](../includes/banner.md)]


Ao lidar com uma ordem de devolução, você deve especificar um código de motivo de devolução para identificar porque o produto está sendo devolvido. Você também deve especificar um código de disposição e uma ação de disposição para determinar o que deve ser feito com o produto devolvido.

Um código de disposição pode ser aplicado quando você cria a ordem de devolução, registra a entrada de item ou atualiza a guia de remessa da entrada de item e conclui uma ordem de quarentena.

Você pode definir quaisquer códigos de disposição necessários para dar suporte aos processos comerciais. A tabela a seguir fornece um conjunto de códigos tipicamente usados para atribuir disposição item de devolução.

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Tipo de disposição</p></th>
<th><p>Código comum</p></th>
<th><p>Descrição</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Alienação</p></td>
<td><p>SC</p></td>
<td><p>Sucata/Destruir</p></td>
</tr>
<tr class="even">
<td><p>Alienação</p></td>
<td><p>DC</p></td>
<td><p>Doar para caridade</p></td>
</tr>
<tr class="odd">
<td><p>Alienação</p></td>
<td><p>TD</p></td>
<td><p>Eliminação de terceiros</p></td>
</tr>
<tr class="even">
<td><p>Alienação</p></td>
<td><p>SL</p></td>
<td><p>Recuperar</p></td>
</tr>
<tr class="odd">
<td><p>Alienação</p></td>
<td><p>TS</p></td>
<td><p>Venda de terceiros (mercados secunDiários)</p></td>
</tr>
<tr class="even">
<td><p>Reparar/Modificar</p></td>
<td><p>RW</p></td>
<td><p>Reformular</p></td>
</tr>
<tr class="odd">
<td><p>Reparar/Modificar</p></td>
<td><p>RF</p></td>
<td><p>Refabricar/Recondicionar</p></td>
</tr>
<tr class="even">
<td><p>Reparar/Modificar</p></td>
<td><p>MD</p></td>
<td><p>Modificar</p></td>
</tr>
<tr class="odd">
<td><p>Reparar/Modificar</p></td>
<td><p>RP</p></td>
<td><p>Reparar</p></td>
</tr>
<tr class="even">
<td><p>Reparar/Modificar</p></td>
<td><p>RV</p></td>
<td><p>Devolver para o fornecedor</p></td>
</tr>
<tr class="odd">
<td><p>Outros</p></td>
<td><p>AI</p></td>
<td><p>Usar como</p></td>
</tr>
<tr class="even">
<td><p>Outro</p></td>
<td><p>RS</p></td>
<td><p>Revenda</p></td>
</tr>
<tr class="odd">
<td><p>Outro</p></td>
<td><p>EX</p></td>
<td><p>Troca</p></td>
</tr>
<tr class="even">
<td><p>Outro</p></td>
<td><p>MS</p></td>
<td><p>Diversos</p></td>
</tr>
</tbody>
</table>


Para cada código de disposição definidos por você, selecione uma ação de disposição. A ação de disposição determina as implicações físicas e financeiras dos códigos de disposição. Por exemplo, a ação de disposição determina o manuseio físico do item devolvido, o efeito financeiro do item devolvido e se um item de substituição deverá ser enviado ao cliente. Você pode definir um número ilimitado de códigos de disposição de acordo com suas necessidades comerciais, mas existem apenas seis ações de disposição predefinidas que podem ser selecionadas. A tabela a seguir oferece as ações de disposição e suas definições.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Ação de disposição</p></th>
<th><p>descrição</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Crédito</strong></p></td>
<td><p>Devolver o item ao estoque e creditar o cliente.</p></td>
</tr>
<tr class="even">
<td><p><strong>Somente crédito</strong></p></td>
<td><p>creditar o cliente sem exigir ou esperar que o item seja devolvido.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Sucata</strong></p></td>
<td><p>Sucatear o item e creditar o cliente.</p></td>
</tr>
<tr class="even">
<td><p><strong>Substituir e creditar</strong></p></td>
<td><p>Devolver o item ao estoque, criar uma ordem de substituição e creditar o cliente.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Substituir e sucata</strong></p></td>
<td><p>Sucatear o item, criar uma ordem de substituição e creditar o cliente.</p></td>
</tr>
<tr class="even">
<td><p><strong>Devolver ao cliente</strong></p></td>
<td><p>Rejeitar o item devolvido e devolvê-lo ao cliente.</p></td>
</tr>
</tbody>
</table>


## <a name="select-a-disposition-code-for-a-quarantine-order"></a>Selecione um código de disposição para uma ordem de quarentena

1.  Clique em **Gerenciamento de estoque** \> **Periódico** \> **Gerenciamento de qualidade** \> **Ordens de quarentena**.

2.  Para uma ordem de quarentena existente, selecione uma ação do campo **Código de disposição** na guia **Visão geral**.



## <a name="see-also"></a>Consulte também

[Ordem de quarentena (formulário)](https://technet.microsoft.com/en-us/library/aa554073(v=ax.60))

[Códigos de disposição (formulário)](https://technet.microsoft.com/en-us/library/hh597113\(v=ax.60\))

  


