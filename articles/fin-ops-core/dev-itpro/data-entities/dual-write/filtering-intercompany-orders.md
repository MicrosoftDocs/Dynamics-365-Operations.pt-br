---
title: Filtrar ordens intercompanhia para evitar sincronizar Ordens e Linhas da Ordem
description: Este tópico explica como filtrar ordens intercompanhia para que as entidades Ordens e Linhas da Ordem não sejam sincronizadas.
author: negudava
ms.date: 11/09/2020
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: negudava
ms.search.validFrom: 2020-01-06
ms.openlocfilehash: 8575f38ca23ef245947a41c35846983604662ef2
ms.sourcegitcommit: 9acfb9ddba9582751f53501b82a7e9e60702a613
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/10/2021
ms.locfileid: "7782544"
---
# <a name="filter-intercompany-orders-to-avoid-syncing-orders-and-orderlines"></a>Filtrar ordens intercompanhia para evitar sincronizar Ordens e Linhas da Ordem

[!include [banner](../../includes/banner.md)]

Você pode filtrar ordens intercompanhia para que as entidades **Ordens** e **OrderLines** não sejam sincronizadas. Em algumas situações, os detalhes da ordem intercompanhia não são necessários em um aplicativo Customer Engagement.

Cada tabela Dataverse padrão é estendida com referências à coluna **IntercompanyOrder**, e os mapas de gravação dupla são modificados para se referirem às colunas adicionais nos filtros. Portanto, as ordens intercompanhia não são sincronizadas. Esse processo ajuda a impedir dados desnecessários no aplicativo do Customer Engagement.

1. Estenda a tabela **Cabeçalhos da ordem de venda do CDS** adicionando uma referência à coluna **IntercompanyOrder**. Esta coluna só é preenchida em ordens intercompanhia. A coluna **IntercompanyOrder** está disponível na tabela **SalesTable**.

    :::image type="content" source="media/filter-sales-order-header-field-display.png" alt-text="Mapear a página de destino para cabeçalhos de ordem de venda do CDS.":::

2. Depois que os **Cabeçalhos de ordem de venda do CDS** forem estendidos, a coluna **IntercompanyOrder** ficará disponível no mapeamento. Aplicar um filtro que tenha `INTERCOMPANYORDER == ""` como a cadeia de caracteres de consulta.

    :::image type="content" source="media/filter-sales-order-header.png" alt-text="Editar a caixa de diálogo de consulta para cabeçalhos de ordem de venda do CDS.":::

3. Estenda a tabela **Linhas da ordem de venda do CDS** adicionando uma referência à coluna **IntercompanyInventTransId**. Esta coluna só é preenchida em ordens intercompanhia. A coluna **InterCompanyInventTransId** está disponível na tabela **SalesLine**.

    :::image type="content" source="media/filter-sales-order-line-field-display.png" alt-text="Mapear a página de destino para linhas de ordem de venda do CDS.":::

4. Depois que as **Linhas de ordem de venda do CDS** forem estendidas, a coluna **IntercompanyInventTransId** ficará disponível no mapeamento. Aplicar um filtro que tenha `INTERCOMPANYINVENTTRANSID == ""` como a cadeia de caracteres de consulta.

    :::image type="content" source="media/filter-sales-order-lines.png" alt-text="Editar a caixa de diálogo de consulta para linhas de ordem de venda do CDS.":::

5. Repita as etapas 1 e 2 para estender a tabela **Cabeçalho da fatura de venda V2** e adicione uma consulta de filtro. Neste caso, use `(INTERCOMPANYORDER == "") && (SALESORDERNUMBER != "")` como cadeia de caracteres da consulta para o filtro.

    :::image type="content" source="media/filter-sales-invoice-header-field-display.png" alt-text="Mapear a página de destino para cabeçalho de fatura de venda V2.":::

    :::image type="content" source="media/filter-sales-invoice-header-filter.png" alt-text="Editar a caixa de diálogo de consulta para o cabeçalho de fatura de venda V2.":::

6. Repita as etapas 3 e 4 para estender a tabela **Linhas da fatura de venda V2** e adicione uma consulta de filtro. Neste caso, use `INTERCOMPANYINVENTTRANSID == ""` como cadeia de caracteres da consulta para o filtro.

    :::image type="content" source="media/filter-sales-invoice-lines-filter.png" alt-text="Editar a caixa de diálogo de consulta para linhas de fatura de venda V2.":::

7. A tabela **Cotações** não tem uma relação intercompanhia. Se alguém criar uma cotação para um de seus clientes intercompanhia, você poderá usar todos a coluna **CustGroup** a colocar todos esses clientes em um grupo de clientes. Para estender o cabeçalho e as linhas, adicione a coluna **CustGroup** e filtre para que o grupo não seja incluído.

    :::image type="content" source="media/filter-cust-group.png" alt-text="Mapear a página de destino para o cabeçalho de cotação de venda do CDS.":::

8. Depois de estender **Cotações**, aplique um filtro que tenha `CUSTGROUP != "<company>"` como a sequência de caracteres de consulta.

    :::image type="content" source="media/filter-cust-group-edit.png" alt-text="Editar a caixa de diálogo de consulta para o cabeçalho de cotação de venda do CDS.":::


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]