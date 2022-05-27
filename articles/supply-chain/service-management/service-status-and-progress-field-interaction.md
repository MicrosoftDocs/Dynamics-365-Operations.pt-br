---
title: Interação do Status do serviço e do campo de andamento
description: No formulário Ordens de serviço, o campo Progresso, no cabeçalho da ordem de serviço, reflete o status da ordem de serviço inteira, e o Status informa o status de linhas individuais da ordem de serviço.
author: sorenva
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SMAServiceOrderTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: sorenand
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0e83df9ca8ee19b5e29d4eccf2bd883ee6ddff62
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/03/2022
ms.locfileid: "8677636"
---
# <a name="service-status-and-progress-field-interaction"></a>Interação do Status do serviço e do campo de andamento

[!include [banner](../includes/banner.md)]

No formulário **Ordens de serviço**, o campo **Progresso**, no cabeçalho da ordem de serviço, reflete o status da ordem de serviço inteira, e o **Status** informa o status de linhas individuais da ordem de serviço.

<table>
<colgroup>
<col />
<col />
<col />
<col />
</colgroup>
<thead>
<tr class="header">
<th><p>Progresso</p></th>
<th><p>Status da Linha 1</p></th>
<th><p>Status da Linha 2</p></th>
<th><p>Status da Linha 3</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Em processamento</strong></p></td>
<td><p><strong>Criado</strong></p></td>
<td><p><strong>Criado</strong></p></td>
<td><p><strong>Criado</strong></p></td>
</tr>
<tr class="even">
<td><p><strong>Em processamento</strong></p></td>
<td><p><strong>Cancelado</strong></p></td>
<td><p><strong>Criado</strong></p></td>
<td><p><strong>Criado</strong></p></td>
</tr>
<tr class="odd">
<td><p><strong>Em processamento</strong></p></td>
<td><p><strong>Criado</strong></p></td>
<td><p><strong>Cancelado</strong></p></td>
<td><p><strong>Lançado</strong></p></td>
</tr>
<tr class="even">
<td><p><strong>Cancelado</strong></p></td>
<td><p><strong>Cancelado</strong></p></td>
<td><p><strong>Cancelado</strong></p></td>
<td><p><strong>Cancelado</strong></p></td>
</tr>
<tr class="odd">
<td><p><strong>Lançado</strong></p></td>
<td><p><strong>Lançado</strong></p></td>
<td><p><strong>Lançado</strong></p></td>
<td><p><strong>Lançado</strong></p></td>
</tr>
<tr class="even">
<td><p><strong>Lançado</strong></p></td>
<td><p><strong>Lançado</strong></p></td>
<td><p><strong>Cancelado</strong></p></td>
<td><p><strong>Cancelado</strong></p></td>
</tr>
</tbody>
</table>

O andamento de uma ordem de serviço está em processo se todas as linhas tiverem o status **Criado**. Ele ainda estará em processo se uma das linhas tiver o status **Cancelado** ou **Lançado**.

Se todas as linhas de uma ordem de serviço estiverem marcadas com **Lançado**, o andamento da ordem será **Lançado**. Se algumas linhas forem **Lançado** e algumas forem **Cancelado**, o andamento ainda será **Lançado**.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
