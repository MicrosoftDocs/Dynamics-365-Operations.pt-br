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
# <a name="filter-intercompany-orders-to-avoid-synchronizing-orders-and-orderlines"></a><span data-ttu-id="0ab06-103">Filtrar ordens intercompanhia para evitar sincronizar Ordens e Linhas da Ordem</span><span class="sxs-lookup"><span data-stu-id="0ab06-103">Filter intercompany orders to avoid synchronizing Orders and OrderLines</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="0ab06-104">Você pode filtrar ordens intercompanhia para evitar sincronizar as entidades **Ordens** e **OrderLines**.</span><span class="sxs-lookup"><span data-stu-id="0ab06-104">You can filter intercompany orders to avoid synchronizing the **Orders** and **OrderLines** entities.</span></span> <span data-ttu-id="0ab06-105">Em algumas situações, os detalhes da ordem intercompanhia não são necessários no aplicativo Customer Engagement.</span><span class="sxs-lookup"><span data-stu-id="0ab06-105">In some scenarios, the intercompany order details are not necessary in customer engagement app.</span></span>

<span data-ttu-id="0ab06-106">Cada uma das entidades Common Data Service padrão é estendida com referências ao campo **IntercompanyOrder**, e os mapas de gravação dupla são modificados para se referirem aos campos adicionais nos filtros.</span><span class="sxs-lookup"><span data-stu-id="0ab06-106">Each of the standard Common Data Service entities is extended with references to the **IntercompanyOrder** field, and the dual-write maps are modified to refer to the additional fields in the filters.</span></span> <span data-ttu-id="0ab06-107">O resultado é que as ordens intercompanhia não são mais sincronizadas.</span><span class="sxs-lookup"><span data-stu-id="0ab06-107">The result is that the intercompany orders are no longer synchronized.</span></span> <span data-ttu-id="0ab06-108">Esse processo evita dados desnecessários no aplicativo do Customer Engagement.</span><span class="sxs-lookup"><span data-stu-id="0ab06-108">This process avoids unnecessary data in the customer engagement app.</span></span>

1. <span data-ttu-id="0ab06-109">Adicione uma referência a **IntercompanyOrder** em **Cabeçalhos de ordem de venda do CDS**.</span><span class="sxs-lookup"><span data-stu-id="0ab06-109">Add a reference to **IntercompanyOrder** to **CDS Sales Order Headers**.</span></span> <span data-ttu-id="0ab06-110">Ele é preenchido somente em ordens intercompanhia.</span><span class="sxs-lookup"><span data-stu-id="0ab06-110">It is populated on only intercompany orders.</span></span> <span data-ttu-id="0ab06-111">O campo **IntercompanyOrder** está disponível no **SalesTable**.</span><span class="sxs-lookup"><span data-stu-id="0ab06-111">The field **IntercompanyOrder** is available in **SalesTable**.</span></span>

    :::image type="content" source="media/filter-sales-order-header-field-display.png" alt-text="Mapear transferência para o destino, SalesOrderHeader":::
    
2. <span data-ttu-id="0ab06-113">Depois que os **Cabeçalhos de ordem de venda do CDS** forem estendidos, o campo **IntercompanyOrder** estará disponível no mapeamento.</span><span class="sxs-lookup"><span data-stu-id="0ab06-113">After **CDS Sales Order Headers** is extended, the **IntercompanyOrder** field is available in the mapping.</span></span> <span data-ttu-id="0ab06-114">Aplicar um filtro com `INTERCOMPANYORDER == ""` como a cadeia de caracteres de consulta.</span><span class="sxs-lookup"><span data-stu-id="0ab06-114">Apply a filter with `INTERCOMPANYORDER == ""` as the query string.</span></span>

    :::image type="content" source="media/filter-sales-order-header.png" alt-text="Cabeçalhos de ordens de venda, editar consulta":::

3. <span data-ttu-id="0ab06-116">Adicione uma referência a **IntercompanyInventTransId** para **Linhas de ordem de venda do CDS**.</span><span class="sxs-lookup"><span data-stu-id="0ab06-116">Add a reference to **IntercompanyInventTransId** to **CDS Sales Order Lines**.</span></span>  <span data-ttu-id="0ab06-117">Ele é preenchido somente em ordens intercompanhia.</span><span class="sxs-lookup"><span data-stu-id="0ab06-117">It is populated on only intercompany orders.</span></span> <span data-ttu-id="0ab06-118">O campo **InterCompanyInventTransID** está disponível no **SalesLine**.</span><span class="sxs-lookup"><span data-stu-id="0ab06-118">The field **InterCompanyInventTransID** is available in **SalesLine**.</span></span>

    :::image type="content" source="media/filter-sales-order-line-field-display.png" alt-text="Mapear transferência para o destino, SalesOrderLine":::

4. <span data-ttu-id="0ab06-120">Depois que os **Linhas de ordem de venda do CDS** forem estendidos, o campo **IntercompanyInventTransId** estará disponível no mapeamento.</span><span class="sxs-lookup"><span data-stu-id="0ab06-120">After **CDS Sales Order Lines** is extended, the **IntercompanyInventTransId** field is available in the mapping.</span></span> <span data-ttu-id="0ab06-121">Aplicar um filtro com `INTERCOMPANYINVENTTRANSID == ""` como a cadeia de caracteres de consulta.</span><span class="sxs-lookup"><span data-stu-id="0ab06-121">Apply a filter with `INTERCOMPANYINVENTTRANSID == ""` as the query string.</span></span>

    :::image type="content" source="media/filter-sales-order-lines.png" alt-text="Linhas de ordem de venda, editar consulta":::

5. <span data-ttu-id="0ab06-123">Amplie o **Cabeçalho da fatura de venda V2** e as **Linhas da fatura de venda V2** da mesma forma que você estendeu as entidades Common Data Service nas etapas 1 e 2.</span><span class="sxs-lookup"><span data-stu-id="0ab06-123">Extend **Sales Invoice Header V2** and **Sales Invoice Lines V2** in the same way you extended the Common Data Service entities in steps 1 and 2.</span></span> <span data-ttu-id="0ab06-124">Em seguida, adicione as consultas de filtro.</span><span class="sxs-lookup"><span data-stu-id="0ab06-124">Then add the filter queries.</span></span> <span data-ttu-id="0ab06-125">A sequência de caracteres do filtro para o **Cabeçalho da fatura de venda V2** é `(INTERCOMPANYORDER == "") && (SALESORDERNUMBER != "")`.</span><span class="sxs-lookup"><span data-stu-id="0ab06-125">The filter string for **Sales Invoice Header V2** is `(INTERCOMPANYORDER == "") && (SALESORDERNUMBER != "")`.</span></span> <span data-ttu-id="0ab06-126">A sequência de caracteres do filtro para o **Linhas da fatura de venda V2** é `INTERCOMPANYINVENTTRANSID == ""`.</span><span class="sxs-lookup"><span data-stu-id="0ab06-126">The filter string for **Sales Invoice Lines V2** is `INTERCOMPANYINVENTTRANSID == ""`.</span></span>

    :::image type="content" source="media/filter-sales-invoice-header-field-display.png" alt-text="Mapear transferência para o destino, Cabeçalhos da fatura de venda":::

    :::image type="content" source="media/filter-sales-invoice-header-filter.png" alt-text="Cabeçalhos da fatura de venda, editar consulta":::

    :::image type="content" source="media/filter-sales-invoice-lines-filter.png" alt-text="Linhas da fatura de venda, editar consulta":::

6. <span data-ttu-id="0ab06-130">A entidade **Cotações** não tem uma relação intercompanhia.</span><span class="sxs-lookup"><span data-stu-id="0ab06-130">The **Quotations** entity doesn't have an intercompany relationship.</span></span> <span data-ttu-id="0ab06-131">Se alguém criar uma cotação para um de seus clientes intercompanhia, você poderá colocar todos esses clientes em um grupo de clientes usando o campo **CustGroup**.</span><span class="sxs-lookup"><span data-stu-id="0ab06-131">If someone creates a quote for one of your intercompany customers, you can put all of these customers in one customer group by using the **CustGroup** field.</span></span>  <span data-ttu-id="0ab06-132">Cabeçalho e linhas podem ser estendidos para adicionar o campo **CustGroup** e, em seguida, filtrar para não incluir esse grupo.</span><span class="sxs-lookup"><span data-stu-id="0ab06-132">Header and lines can be extended to add the **CustGroup** field and then filter to not include this group.</span></span>

    :::image type="content" source="media/filter-cust-group.png" alt-text="Mapear transferência para o destino, Cabeçalho da cotação de venda":::

7. <span data-ttu-id="0ab06-134">Depois de ter estendido a entidade **Cotações**, aplique um filtro com `CUSTGROUP !=  "<company>"` como a sequência de caracteres de consulta.</span><span class="sxs-lookup"><span data-stu-id="0ab06-134">After you extent the **Quotations** entity, apply a filter with `CUSTGROUP !=  "<company>"` as the query string.</span></span>

    :::image type="content" source="media/filter-cust-group-edit.png" alt-text="Cabeçalho da cotação de venda, editar consulta":::
