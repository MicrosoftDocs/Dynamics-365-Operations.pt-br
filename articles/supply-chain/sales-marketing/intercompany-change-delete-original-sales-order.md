---
title: Alterar ou excluir uma ordem de venda intercompanhia original
description: Este tópico explica como alterar e excluir uma funcionalidade de ordem de venda original
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
ms.openlocfilehash: cfacd1710aa5812230395409f1dd7c2e882faa9f
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/03/2022
ms.locfileid: "8673736"
---
# <a name="change-or-delete-an-original-intercompany-sales-order"></a>Alterar ou excluir uma ordem de venda intercompanhia original

[!include [banner](../../includes/banner.md)]

Quando você altera uma ordem de venda, essas alterações são sincronizadas automaticamente com a ordem de compra intercompanhia relevante e com a ordem de venda intercompanhia.

> [!NOTE]
> As ordens de compra de fornecedores externos não serão afetadas pelas alterações que você realizar, nem as linhas de vendas originais relacionadas às linhas da ordem de compra dos fornecedores externos.

A tabela a seguir resume as alterações que você pode fazer e os resultados esperados.

| Operação | Resultado |
|---|---|
| Excluir&nbsp;uma&nbsp;ordem&nbsp;de venda&nbsp;original. | A ordem de compra intercompanhia e a ordem de venda intercompanhia relacionadas também serão excluídas. Se o status da ordem for **Lista de separação** ou posterior no processo, não será possível excluir a ordem de venda. |
| Excluir uma linha da ordem de venda original. | A linha da ordem de compra intercompanhia relacionada e a linha da ordem de venda intercompanhia serão excluídas. Se o status da ordem for **Lista de separação** ou posterior no processo, não será possível excluir a linha da ordem de venda. |
| Adicione uma nova linha de venda a uma ordem de venda original. | A nova linha de venda será criada tanto na ordem de compra intercompanhia como na ordem de venda intercompanhia. |
| Altere a quantidade em uma linha da ordem de venda original. | A quantidade será sincronizada com a linha da ordem de compra intercompanhia e com a linha da ordem de venda intercompanhia. O valor líquido será recalculado em todas as ordens. |
| Desabilite a entrega direta em uma ordem de venda original. | Não será possível alterar o campo **Entrega direta** na ordem de venda original se a linha da ordem de venda intercompanhia tiver alcançado um status mínimo de **Lista de separação**, **Ordem de saída** ou **Diário de lista de separação**. O endereço de entrega na ordem de compra intercompanhia será alterado para o endereço de entrega padrão (endereço de entrega padrão da ordem de compra). Além disso, as linhas da ordem de compra intercompanhia também são alteradas para o endereço de entrega padrão para as linhas. Ambas são sincronizadas com a ordem de venda intercompanhia e com as linhas. O tipo de entrega em todas as linhas da ordem de venda original será alterado para **Nenhum** e o campo será sincronizado com as linhas da ordem de compra intercompanhia. As ordens de compra dos fornecedores externos não serão afetadas, nem as linhas de vendas originais relacionadas às linhas da ordem de compra dos fornecedores externos. A data de entrega na ordem de compra intercompanhia e nas linhas, e as datas de recebimento/remessa solicitadas na ordem de venda intercompanhia e nas linhas serão atualizadas. |
| Habilitar a entrega direta em uma ordem de venda original. | Se a linha da ordem de venda intercompanhia tiver alcançado um status mínimo de **Lista de separação**, **Ordem de saída** ou **Diário de lista de separação**, você não poderá alterar o campo **Entrega direta** na ordem de venda original. O endereço de entrega na ordem de compra intercompanhia será alterado para o endereço de entrega da ordem de venda original e sincronizado com a ordem de venda intercompanhia. O tipo de entrega em todas as linhas da ordem de venda original será alterado para **Entrega direta** e o campo será sincronizado com as linhas da ordem de compra intercompanhia. O endereço de entrega em cada linha da ordem de venda original será sincronizado com as linhas da ordem de compra intercompanhia e com as linhas da ordem de venda intercompanhia. A data de entrega na ordem de compra intercompanhia e nas linhas, e as datas de recebimento/remessa solicitadas na ordem de venda intercompanhia e nas linhas serão atualizadas. |
| Adicione uma anotação ao cabeçalho da ordem de venda original e às linhas. | A anotação será copiada para a ordem de compra intercompanhia e para a ordem de venda intercompanhia. |
| Altere ou exclua uma anotação. | Se você alterar ou excluir uma anotação, a anotação correspondente sobre a ordem de compra intercompanhia e a ordem de venda intercompanhia será devidamente alterada ou excluída. |

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
