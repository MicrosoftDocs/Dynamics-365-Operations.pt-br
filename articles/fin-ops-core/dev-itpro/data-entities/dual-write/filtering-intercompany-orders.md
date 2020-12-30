---
title: Filtrar ordens intercompanhia para evitar sincronizar Ordens e Linhas da Ordem
description: Este tópico descreve como filtrar ordens intercompanhia para evitar sincronizar Ordens e Linhas da Ordem.
author: negudava
manager: tfehr
ms.date: 11/09/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: negudava
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-09-20
ms.openlocfilehash: 6c5e1e2467673badd20366d3bd8e1b93b8078b26
ms.sourcegitcommit: 0eb33909a419d526eb84b4e4b64d3595d01731ef
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/08/2020
ms.locfileid: "4701024"
---
# <a name="filter-intercompany-orders-to-avoid-synchronizing-orders-and-orderlines"></a>Filtrar ordens intercompanhia para evitar sincronizar Ordens e Linhas da Ordem

[!include [banner](../../includes/banner.md)]

Você pode filtrar ordens intercompanhia para evitar sincronizar as entidades **Ordens** e **OrderLines**. Em algumas situações, os detalhes da ordem intercompanhia não são necessários no aplicativo Customer Engagement.

Cada uma das entidades Common Data Service padrão é estendida com referências ao campo **IntercompanyOrder**, e os mapas de gravação dupla são modificados para se referirem aos campos adicionais nos filtros. O resultado é que as ordens intercompanhia não são mais sincronizadas. Esse processo evita dados desnecessários no aplicativo do Customer Engagement.

1. Adicione uma referência a **IntercompanyOrder** em **Cabeçalhos de ordem de venda do CDS**. Ele é preenchido somente em ordens intercompanhia. O campo **IntercompanyOrder** está disponível no **SalesTable**.

    :::image type="content" source="media/filter-sales-order-header-field-display.png" alt-text="Mapear transferência para o destino, SalesOrderHeader":::
    
2. Depois que os **Cabeçalhos de ordem de venda do CDS** forem estendidos, o campo **IntercompanyOrder** estará disponível no mapeamento. Aplicar um filtro com `INTERCOMPANYORDER == ""` como a cadeia de caracteres de consulta.

    :::image type="content" source="media/filter-sales-order-header.png" alt-text="Cabeçalhos de ordens de venda, editar consulta":::

3. Adicione uma referência a **IntercompanyInventTransId** para **Linhas de ordem de venda do CDS**.  Ele é preenchido somente em ordens intercompanhia. O campo **InterCompanyInventTransID** está disponível no **SalesLine**.

    :::image type="content" source="media/filter-sales-order-line-field-display.png" alt-text="Mapear transferência para o destino, SalesOrderLine":::

4. Depois que os **Linhas de ordem de venda do CDS** forem estendidos, o campo **IntercompanyInventTransId** estará disponível no mapeamento. Aplicar um filtro com `INTERCOMPANYINVENTTRANSID == ""` como a cadeia de caracteres de consulta.

    :::image type="content" source="media/filter-sales-order-lines.png" alt-text="Linhas de ordem de venda, editar consulta":::

5. Amplie o **Cabeçalho da fatura de venda V2** e as **Linhas da fatura de venda V2** da mesma forma que você estendeu as entidades Common Data Service nas etapas 1 e 2. Em seguida, adicione as consultas de filtro. A sequência de caracteres do filtro para o **Cabeçalho da fatura de venda V2** é `(INTERCOMPANYORDER == "") && (SALESORDERNUMBER != "")`. A sequência de caracteres do filtro para o **Linhas da fatura de venda V2** é `INTERCOMPANYINVENTTRANSID == ""`.

    :::image type="content" source="media/filter-sales-invoice-header-field-display.png" alt-text="Mapear transferência para o destino, Cabeçalhos da fatura de venda":::

    :::image type="content" source="media/filter-sales-invoice-header-filter.png" alt-text="Cabeçalhos da fatura de venda, editar consulta":::

    :::image type="content" source="media/filter-sales-invoice-lines-filter.png" alt-text="Linhas da fatura de venda, editar consulta":::

6. A entidade **Cotações** não tem uma relação intercompanhia. Se alguém criar uma cotação para um de seus clientes intercompanhia, você poderá colocar todos esses clientes em um grupo de clientes usando o campo **CustGroup**.  Cabeçalho e linhas podem ser estendidos para adicionar o campo **CustGroup** e, em seguida, filtrar para não incluir esse grupo.

    :::image type="content" source="media/filter-cust-group.png" alt-text="Mapear transferência para o destino, Cabeçalho da cotação de venda":::

7. Depois de ter estendido a entidade **Cotações**, aplique um filtro com `CUSTGROUP !=  "<company>"` como a sequência de caracteres de consulta.

    :::image type="content" source="media/filter-cust-group-edit.png" alt-text="Cabeçalho da cotação de venda, editar consulta":::
