---
title: Filtrar ordens intercompanhia para evitar sincronizar Ordens e Linhas da Ordem
description: Este tópico explica como filtrar ordens intercompanhia para que as entidades Ordens e Linhas da Ordem não sejam sincronizadas.
author: negudava
ms.date: 11/09/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: negudava
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-09-20
ms.openlocfilehash: 123427db61782490d348489c23e0eaf5f8b513c9
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5748632"
---
# <a name="filter-intercompany-orders-to-avoid-syncing-orders-and-orderlines"></a><span data-ttu-id="fc1b1-103">Filtrar ordens intercompanhia para evitar sincronizar Ordens e Linhas da Ordem</span><span class="sxs-lookup"><span data-stu-id="fc1b1-103">Filter intercompany orders to avoid syncing Orders and OrderLines</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="fc1b1-104">Você pode filtrar ordens intercompanhia para que as entidades **Ordens** e **OrderLines** não sejam sincronizadas.</span><span class="sxs-lookup"><span data-stu-id="fc1b1-104">You can filter intercompany orders so that the **Orders** and **OrderLines** tables aren't synced.</span></span> <span data-ttu-id="fc1b1-105">Em algumas situações, os detalhes da ordem intercompanhia não são necessários em um aplicativo Customer Engagement.</span><span class="sxs-lookup"><span data-stu-id="fc1b1-105">In some scenarios, the intercompany order details aren't required in a customer engagement app.</span></span>

<span data-ttu-id="fc1b1-106">Cada tabela Dataverse padrão é estendida com referências à coluna **IntercompanyOrder**, e os mapas de gravação dupla são modificados para se referirem às colunas adicionais nos filtros.</span><span class="sxs-lookup"><span data-stu-id="fc1b1-106">Each standard Dataverse table is extended through references to the **IntercompanyOrder** column, and the dual-write maps are modified so that they refer to the additional columns in the filters.</span></span> <span data-ttu-id="fc1b1-107">Portanto, as ordens intercompanhia não são sincronizadas.</span><span class="sxs-lookup"><span data-stu-id="fc1b1-107">Therefore, the intercompany orders are no longer synced.</span></span> <span data-ttu-id="fc1b1-108">Esse processo ajuda a impedir dados desnecessários no aplicativo do Customer Engagement.</span><span class="sxs-lookup"><span data-stu-id="fc1b1-108">This process helps prevent unnecessary data in the customer engagement app.</span></span>

1. <span data-ttu-id="fc1b1-109">Estenda a tabela **Cabeçalhos da ordem de venda do CDS** adicionando uma referência à coluna **IntercompanyOrder**.</span><span class="sxs-lookup"><span data-stu-id="fc1b1-109">Extend the **CDS Sales Order Headers** table by adding a reference to the **IntercompanyOrder** column.</span></span> <span data-ttu-id="fc1b1-110">Esta coluna só é preenchida em ordens intercompanhia.</span><span class="sxs-lookup"><span data-stu-id="fc1b1-110">This column is filled in only on intercompany orders.</span></span> <span data-ttu-id="fc1b1-111">A coluna **IntercompanyOrder** está disponível na tabela **SalesTable**.</span><span class="sxs-lookup"><span data-stu-id="fc1b1-111">The **IntercompanyOrder** column is available in the **SalesTable** table.</span></span>

    :::image type="content" source="media/filter-sales-order-header-field-display.png" alt-text="Mapear a página de destino para cabeçalhos de ordem de venda do CDS":::

2. <span data-ttu-id="fc1b1-113">Depois que os **Cabeçalhos de ordem de venda do CDS** forem estendidos, a coluna **IntercompanyOrder** ficará disponível no mapeamento.</span><span class="sxs-lookup"><span data-stu-id="fc1b1-113">After **CDS Sales Order Headers** is extended, the **IntercompanyOrder** column is available in the mapping.</span></span> <span data-ttu-id="fc1b1-114">Aplicar um filtro que tenha `INTERCOMPANYORDER == ""` como a cadeia de caracteres de consulta.</span><span class="sxs-lookup"><span data-stu-id="fc1b1-114">Apply a filter that has `INTERCOMPANYORDER == ""` as the query string.</span></span>

    :::image type="content" source="media/filter-sales-order-header.png" alt-text="Editar a caixa de diálogo de consulta para cabeçalhos de ordem de venda do CDS":::

3. <span data-ttu-id="fc1b1-116">Estenda a tabela **Linhas da ordem de venda do CDS** adicionando uma referência à coluna **IntercompanyInventTransId**.</span><span class="sxs-lookup"><span data-stu-id="fc1b1-116">Extend the **CDS Sales Order Lines** table by adding a reference to the **IntercompanyInventTransId** column.</span></span> <span data-ttu-id="fc1b1-117">Esta coluna só é preenchida em ordens intercompanhia.</span><span class="sxs-lookup"><span data-stu-id="fc1b1-117">This column is filled in only on intercompany orders.</span></span> <span data-ttu-id="fc1b1-118">A coluna **InterCompanyInventTransId** está disponível na tabela **SalesLine**.</span><span class="sxs-lookup"><span data-stu-id="fc1b1-118">The **InterCompanyInventTransId** column is available in the **SalesLine** table.</span></span>

    :::image type="content" source="media/filter-sales-order-line-field-display.png" alt-text="Mapear a página de destino para linhas de ordem de venda do CDS":::

4. <span data-ttu-id="fc1b1-120">Depois que as **Linhas de ordem de venda do CDS** forem estendidas, a coluna **IntercompanyInventTransId** ficará disponível no mapeamento.</span><span class="sxs-lookup"><span data-stu-id="fc1b1-120">After **CDS Sales Order Lines** is extended, the **IntercompanyInventTransId** column is available in the mapping.</span></span> <span data-ttu-id="fc1b1-121">Aplicar um filtro que tenha `INTERCOMPANYINVENTTRANSID == ""` como a cadeia de caracteres de consulta.</span><span class="sxs-lookup"><span data-stu-id="fc1b1-121">Apply a filter that has `INTERCOMPANYINVENTTRANSID == ""` as the query string.</span></span>

    :::image type="content" source="media/filter-sales-order-lines.png" alt-text="Editar a caixa de diálogo de consulta para linhas de ordem de venda do CDS":::

5. <span data-ttu-id="fc1b1-123">Repita as etapas 1 e 2 para estender a tabela **Cabeçalho da fatura de venda V2** e adicione uma consulta de filtro.</span><span class="sxs-lookup"><span data-stu-id="fc1b1-123">Repeat steps 1 and 2 to extend the **Sales Invoice Header V2** table and add a filter query.</span></span> <span data-ttu-id="fc1b1-124">Neste caso, use `(INTERCOMPANYORDER == "") && (SALESORDERNUMBER != "")` como cadeia de caracteres da consulta para o filtro.</span><span class="sxs-lookup"><span data-stu-id="fc1b1-124">In this case, use `(INTERCOMPANYORDER == "") && (SALESORDERNUMBER != "")` as the query string for the filter.</span></span>

    :::image type="content" source="media/filter-sales-invoice-header-field-display.png" alt-text="Mapear a página de destino para cabeçalho de fatura de venda V2":::

    :::image type="content" source="media/filter-sales-invoice-header-filter.png" alt-text="Editar a caixa de diálogo de consulta para o cabeçalho de fatura de venda V2":::

6. <span data-ttu-id="fc1b1-127">Repita as etapas 3 e 4 para estender a tabela **Linhas da fatura de venda V2** e adicione uma consulta de filtro.</span><span class="sxs-lookup"><span data-stu-id="fc1b1-127">Repeat steps 3 and 4 to extend the **Sales Invoice Lines V2** table and add a filter query.</span></span> <span data-ttu-id="fc1b1-128">Neste caso, use `INTERCOMPANYINVENTTRANSID == ""` como cadeia de caracteres da consulta para o filtro.</span><span class="sxs-lookup"><span data-stu-id="fc1b1-128">In this case, use `INTERCOMPANYINVENTTRANSID == ""` as the query string for the filter.</span></span>

    :::image type="content" source="media/filter-sales-invoice-lines-filter.png" alt-text="Editar a caixa de diálogo de consulta para linhas de fatura de venda V2":::

7. <span data-ttu-id="fc1b1-130">A tabela **Cotações** não tem uma relação intercompanhia.</span><span class="sxs-lookup"><span data-stu-id="fc1b1-130">The **Quotations** table doesn't have an intercompany relationship.</span></span> <span data-ttu-id="fc1b1-131">Se alguém criar uma cotação para um de seus clientes intercompanhia, você poderá usar todos a coluna **CustGroup** a colocar todos esses clientes em um grupo de clientes.</span><span class="sxs-lookup"><span data-stu-id="fc1b1-131">If someone creates a quotation for one of your intercompany customers, you can use the **CustGroup** column to put all those customers into one customer group.</span></span> <span data-ttu-id="fc1b1-132">Para estender o cabeçalho e as linhas, adicione a coluna **CustGroup** e filtre para que o grupo não seja incluído.</span><span class="sxs-lookup"><span data-stu-id="fc1b1-132">You can extend the header and lines by adding the **CustGroup** column, and then filter so that the group isn't included.</span></span>

    :::image type="content" source="media/filter-cust-group.png" alt-text="Mapear a página de destino para o cabeçalho de cotação de venda do CDS":::

8. <span data-ttu-id="fc1b1-134">Depois de estender **Cotações**, aplique um filtro que tenha `CUSTGROUP != "<company>"` como a sequência de caracteres de consulta.</span><span class="sxs-lookup"><span data-stu-id="fc1b1-134">After **Quotations** is extended, apply a filter that has `CUSTGROUP != "<company>"` as the query string.</span></span>

    :::image type="content" source="media/filter-cust-group-edit.png" alt-text="Editar a caixa de diálogo de consulta para o cabeçalho de cotação de venda do CDS":::


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]