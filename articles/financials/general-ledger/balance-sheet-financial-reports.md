---
title: Relatórios financeiros de balanço
description: Este artigo descreve os relatórios padrão para balanços. Também mostra os blocos de construção associados a esses relatórios.
author: jcart1106
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: FinanicalReports
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 12274
ms.assetid: 52f78229-f531-4d16-b337-e2628994acb6
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 9ff778af1bb3af3a10132ab3193ad1cd5daa24e1
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1567320"
---
# <a name="balance-sheet-financial-reports"></a><span data-ttu-id="cca17-104">Relatórios financeiros de balanço</span><span class="sxs-lookup"><span data-stu-id="cca17-104">Balance sheet financial reports</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="cca17-105">Este artigo descreve os relatórios padrão para balanços.</span><span class="sxs-lookup"><span data-stu-id="cca17-105">This article describes the default reports for balance sheets.</span></span> <span data-ttu-id="cca17-106">Também mostra os blocos de construção associados a esses relatórios.</span><span class="sxs-lookup"><span data-stu-id="cca17-106">It also describes the building blocks that are associated with these reports.</span></span> 

<a name="default-balance-sheet-reports"></a><span data-ttu-id="cca17-107">Relatórios do balanço padrão</span><span class="sxs-lookup"><span data-stu-id="cca17-107">Default balance sheet reports</span></span>
-----------------------------

<span data-ttu-id="cca17-108">Há dois relatórios do balanço padrão.</span><span class="sxs-lookup"><span data-stu-id="cca17-108">There are two default balance sheet reports.</span></span> <span data-ttu-id="cca17-109">Em um relatório, as seções são empilhadas.</span><span class="sxs-lookup"><span data-stu-id="cca17-109">On one report, the sections are stacked.</span></span> <span data-ttu-id="cca17-110">No outro relatório, as seções estão lado a lado.</span><span class="sxs-lookup"><span data-stu-id="cca17-110">On the other report, the sections are side by side.</span></span>

| <span data-ttu-id="cca17-111">Relatório padrão</span><span class="sxs-lookup"><span data-stu-id="cca17-111">Default report</span></span>                       | <span data-ttu-id="cca17-112">O que ele faz</span><span class="sxs-lookup"><span data-stu-id="cca17-112">What it does</span></span>                                                                                                                           |
|--------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="cca17-113">Balanço - Padrão</span><span class="sxs-lookup"><span data-stu-id="cca17-113">Balance Sheet – Default</span></span>              | <span data-ttu-id="cca17-114">Fornece uma exibição do cargo financeiro da organização para o ano.</span><span class="sxs-lookup"><span data-stu-id="cca17-114">Provides a view of the organization's financial position for the year.</span></span>                                                                 |
| <span data-ttu-id="cca17-115">Balanço Lado a Lado – Padrão</span><span class="sxs-lookup"><span data-stu-id="cca17-115">Side by Side Balance Sheet – Default</span></span> | <span data-ttu-id="cca17-116">Fornece uma exibição do cargo financeiro da organização para o ano.</span><span class="sxs-lookup"><span data-stu-id="cca17-116">Provides a view of the organization's financial position for the year.</span></span> <span data-ttu-id="cca17-117">Os ativos e passivos e o capital próprio do acionista estão lado a lado.</span><span class="sxs-lookup"><span data-stu-id="cca17-117">Assets and liability and shareholder’s equity are side by side.</span></span> |

## <a name="building-blocks"></a><span data-ttu-id="cca17-118">Bloco de construção</span><span class="sxs-lookup"><span data-stu-id="cca17-118">Building blocks</span></span>
<span data-ttu-id="cca17-119">Os relatórios financeiros de balanço usam os seguintes blocos de construção.</span><span class="sxs-lookup"><span data-stu-id="cca17-119">The balance sheet financial reports use the following building blocks.</span></span>

| <span data-ttu-id="cca17-120">Relatório padrão</span><span class="sxs-lookup"><span data-stu-id="cca17-120">Default report</span></span>                       | <span data-ttu-id="cca17-121">Definição de linha</span><span class="sxs-lookup"><span data-stu-id="cca17-121">Row definition</span></span>                       | <span data-ttu-id="cca17-122">Definição de coluna</span><span class="sxs-lookup"><span data-stu-id="cca17-122">Column definition</span></span>             |
|--------------------------------------|--------------------------------------|-------------------------------|
| <span data-ttu-id="cca17-123">Balanço - Padrão</span><span class="sxs-lookup"><span data-stu-id="cca17-123">Balance Sheet - Default</span></span>              | <span data-ttu-id="cca17-124">Balanço - Padrão</span><span class="sxs-lookup"><span data-stu-id="cca17-124">Balance Sheet - Default</span></span>              | <span data-ttu-id="cca17-125">Desde o início do ano e Variação - Padrão</span><span class="sxs-lookup"><span data-stu-id="cca17-125">YTD and Variance - Default</span></span>    |
| <span data-ttu-id="cca17-126">Balanço Lado a Lado – Padrão</span><span class="sxs-lookup"><span data-stu-id="cca17-126">Side by Side Balance Sheet – Default</span></span> | <span data-ttu-id="cca17-127">Balanço Lado a Lado – Padrão</span><span class="sxs-lookup"><span data-stu-id="cca17-127">Side by Side Balance Sheet – Default</span></span> | <span data-ttu-id="cca17-128">Coluna Desde o início do ano - Padrão</span><span class="sxs-lookup"><span data-stu-id="cca17-128">Year to Date Column - Default</span></span> |

### <a name="row-definition"></a><span data-ttu-id="cca17-129">Definição de linha</span><span class="sxs-lookup"><span data-stu-id="cca17-129">Row definition</span></span>

<span data-ttu-id="cca17-130">As definições de linha para os relatórios do balanço contêm as seções para cada parte de um balanço tradicional.</span><span class="sxs-lookup"><span data-stu-id="cca17-130">The row definitions for both balance sheet reports contain sections for each part of a traditional balance sheet.</span></span> <span data-ttu-id="cca17-131">O relatório inclui lado a lado inclui uma quebra de coluna, de modo que o e o capital próprio do proprietário são exibidos aos ativos.</span><span class="sxs-lookup"><span data-stu-id="cca17-131">The side-by-side report includes a column break, so that liability and the owner’s equity appear next to assets.</span></span> <span data-ttu-id="cca17-132">A dimensão da Categoria de conta principal é usada para criar as definições da linha.</span><span class="sxs-lookup"><span data-stu-id="cca17-132">The Main Account Category dimension is used to build both row definitions.</span></span> <span data-ttu-id="cca17-133">Consequentemente, qualquer pessoa pode gerar os relatórios sem fazer modificações.</span><span class="sxs-lookup"><span data-stu-id="cca17-133">Therefore, anyone can generate the reports without having to make any modifications.</span></span>

### <a name="column-definition"></a><span data-ttu-id="cca17-134">Definição de coluna</span><span class="sxs-lookup"><span data-stu-id="cca17-134">Column definition</span></span>

<span data-ttu-id="cca17-135">As definições da coluna contêm diferentes tipos de colunas para fornecer níveis diferentes de detalhes e dados financeiros.</span><span class="sxs-lookup"><span data-stu-id="cca17-135">The column definitions contain different types of columns to provide different levels of detail and financial data.</span></span>

-   <span data-ttu-id="cca17-136">**Desde o início do ano e variação – Tipos da coluna padrão:**</span><span class="sxs-lookup"><span data-stu-id="cca17-136">**YTD and Variance – Default column types:**</span></span>
    -   <span data-ttu-id="cca17-137">**DESC** – A descrição da definição da linha</span><span class="sxs-lookup"><span data-stu-id="cca17-137">**DESC** – The description from the row definition</span></span>
    -   <span data-ttu-id="cca17-138">**FD** – Dados financeiros acumulados do ano para o ano atual</span><span class="sxs-lookup"><span data-stu-id="cca17-138">**FD** – Year-to-date financial data for the current year</span></span>
    -   <span data-ttu-id="cca17-139">**FD** – Dados financeiros acumulados do último ano</span><span class="sxs-lookup"><span data-stu-id="cca17-139">**FD** – Year-to-date financial data for the last year</span></span>
    -   <span data-ttu-id="cca17-140">**CALC** – A variação ao subtrair o último ano deste ano</span><span class="sxs-lookup"><span data-stu-id="cca17-140">**CALC** – The variance from subtracting last year from this year</span></span>

<!-- -->

-   <span data-ttu-id="cca17-141">**Coluna desde o início do ano – Padrão:**</span><span class="sxs-lookup"><span data-stu-id="cca17-141">**Year to Date Column – Default:**</span></span>
    -   <span data-ttu-id="cca17-142">**DESC** – A descrição da definição da linha</span><span class="sxs-lookup"><span data-stu-id="cca17-142">**DESC** – The description from the row definition</span></span>
    -   <span data-ttu-id="cca17-143">**FD** – Dados financeiros acumulados do ano para o ano atual</span><span class="sxs-lookup"><span data-stu-id="cca17-143">**FD** – Year-to-date financial data for the current year</span></span>



<a name="additional-resources"></a><span data-ttu-id="cca17-144">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="cca17-144">Additional resources</span></span>
--------

[<span data-ttu-id="cca17-145">Relatórios financeiros</span><span class="sxs-lookup"><span data-stu-id="cca17-145">Financial reporting</span></span>](financial-reporting-getting-started.md)

[<span data-ttu-id="cca17-146">Exibir relatórios financeiros</span><span class="sxs-lookup"><span data-stu-id="cca17-146">View financial reports</span></span>](view-financial-reports.md)

[<span data-ttu-id="cca17-147">Blog de Relatório Financeiro do Dynamics</span><span class="sxs-lookup"><span data-stu-id="cca17-147">Dynamics Financial Reporting Blog</span></span>](http://blogs.msdn.com/b/dynamics_financial_reporting/)



