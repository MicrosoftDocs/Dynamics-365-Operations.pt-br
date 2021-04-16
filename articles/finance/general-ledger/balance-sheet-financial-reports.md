---
title: Relatórios financeiros de balanço
description: Este artigo descreve os relatórios padrão para balanços. Também mostra os blocos de construção associados a esses relatórios.
author: jcart1106
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: FinanicalReports
audience: Application User
ms.reviewer: roschlom
ms.custom: 12274
ms.assetid: 52f78229-f531-4d16-b337-e2628994acb6
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d916b6593b641ec1c8365475103b1520e07e3768
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5821928"
---
# <a name="balance-sheet-financial-reports"></a><span data-ttu-id="515da-104">Relatórios financeiros de balanço</span><span class="sxs-lookup"><span data-stu-id="515da-104">Balance sheet financial reports</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="515da-105">Este artigo descreve os relatórios padrão para balanços.</span><span class="sxs-lookup"><span data-stu-id="515da-105">This article describes the default reports for balance sheets.</span></span> <span data-ttu-id="515da-106">Também mostra os blocos de construção associados a esses relatórios.</span><span class="sxs-lookup"><span data-stu-id="515da-106">It also describes the building blocks that are associated with these reports.</span></span> 

<a name="default-balance-sheet-reports"></a><span data-ttu-id="515da-107">Relatórios do balanço padrão</span><span class="sxs-lookup"><span data-stu-id="515da-107">Default balance sheet reports</span></span>
-----------------------------

<span data-ttu-id="515da-108">Há dois relatórios do balanço padrão.</span><span class="sxs-lookup"><span data-stu-id="515da-108">There are two default balance sheet reports.</span></span> <span data-ttu-id="515da-109">Em um relatório, as seções são empilhadas.</span><span class="sxs-lookup"><span data-stu-id="515da-109">On one report, the sections are stacked.</span></span> <span data-ttu-id="515da-110">No outro relatório, as seções estão lado a lado.</span><span class="sxs-lookup"><span data-stu-id="515da-110">On the other report, the sections are side by side.</span></span>

| <span data-ttu-id="515da-111">Relatório padrão</span><span class="sxs-lookup"><span data-stu-id="515da-111">Default report</span></span>                       | <span data-ttu-id="515da-112">O que ele faz</span><span class="sxs-lookup"><span data-stu-id="515da-112">What it does</span></span>                                                                                                                           |
|--------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="515da-113">Balanço - Padrão</span><span class="sxs-lookup"><span data-stu-id="515da-113">Balance Sheet – Default</span></span>              | <span data-ttu-id="515da-114">Fornece uma exibição do cargo financeiro da organização para o ano.</span><span class="sxs-lookup"><span data-stu-id="515da-114">Provides a view of the organization's financial position for the year.</span></span>                                                                 |
| <span data-ttu-id="515da-115">Balanço Lado a Lado – Padrão</span><span class="sxs-lookup"><span data-stu-id="515da-115">Side by Side Balance Sheet – Default</span></span> | <span data-ttu-id="515da-116">Fornece uma exibição do cargo financeiro da organização para o ano.</span><span class="sxs-lookup"><span data-stu-id="515da-116">Provides a view of the organization's financial position for the year.</span></span> <span data-ttu-id="515da-117">Os ativos e passivos e o capital próprio do acionista estão lado a lado.</span><span class="sxs-lookup"><span data-stu-id="515da-117">Assets and liability and shareholder’s equity are side by side.</span></span> |

## <a name="building-blocks"></a><span data-ttu-id="515da-118">Bloco de construção</span><span class="sxs-lookup"><span data-stu-id="515da-118">Building blocks</span></span>
<span data-ttu-id="515da-119">Os relatórios financeiros de balanço usam os seguintes blocos de construção.</span><span class="sxs-lookup"><span data-stu-id="515da-119">The balance sheet financial reports use the following building blocks.</span></span>

| <span data-ttu-id="515da-120">Relatório padrão</span><span class="sxs-lookup"><span data-stu-id="515da-120">Default report</span></span>                       | <span data-ttu-id="515da-121">Definição de linha</span><span class="sxs-lookup"><span data-stu-id="515da-121">Row definition</span></span>                       | <span data-ttu-id="515da-122">Definição de coluna</span><span class="sxs-lookup"><span data-stu-id="515da-122">Column definition</span></span>             |
|--------------------------------------|--------------------------------------|-------------------------------|
| <span data-ttu-id="515da-123">Balanço - Padrão</span><span class="sxs-lookup"><span data-stu-id="515da-123">Balance Sheet - Default</span></span>              | <span data-ttu-id="515da-124">Balanço - Padrão</span><span class="sxs-lookup"><span data-stu-id="515da-124">Balance Sheet - Default</span></span>              | <span data-ttu-id="515da-125">Desde o início do ano e Variação - Padrão</span><span class="sxs-lookup"><span data-stu-id="515da-125">YTD and Variance - Default</span></span>    |
| <span data-ttu-id="515da-126">Balanço Lado a Lado – Padrão</span><span class="sxs-lookup"><span data-stu-id="515da-126">Side by Side Balance Sheet – Default</span></span> | <span data-ttu-id="515da-127">Balanço Lado a Lado – Padrão</span><span class="sxs-lookup"><span data-stu-id="515da-127">Side by Side Balance Sheet – Default</span></span> | <span data-ttu-id="515da-128">Coluna Desde o início do ano - Padrão</span><span class="sxs-lookup"><span data-stu-id="515da-128">Year to Date Column - Default</span></span> |

### <a name="row-definition"></a><span data-ttu-id="515da-129">Definição de linha</span><span class="sxs-lookup"><span data-stu-id="515da-129">Row definition</span></span>

<span data-ttu-id="515da-130">As definições de linha para os relatórios do balanço contêm as seções para cada parte de um balanço tradicional.</span><span class="sxs-lookup"><span data-stu-id="515da-130">The row definitions for both balance sheet reports contain sections for each part of a traditional balance sheet.</span></span> <span data-ttu-id="515da-131">O relatório inclui lado a lado inclui uma quebra de coluna, de modo que o e o capital próprio do proprietário são exibidos aos ativos.</span><span class="sxs-lookup"><span data-stu-id="515da-131">The side-by-side report includes a column break, so that liability and the owner’s equity appear next to assets.</span></span> <span data-ttu-id="515da-132">A dimensão da Categoria de conta principal é usada para criar as definições da linha.</span><span class="sxs-lookup"><span data-stu-id="515da-132">The Main Account Category dimension is used to build both row definitions.</span></span> <span data-ttu-id="515da-133">Consequentemente, qualquer pessoa pode gerar os relatórios sem fazer modificações.</span><span class="sxs-lookup"><span data-stu-id="515da-133">Therefore, anyone can generate the reports without having to make any modifications.</span></span>

### <a name="column-definition"></a><span data-ttu-id="515da-134">Definição de coluna</span><span class="sxs-lookup"><span data-stu-id="515da-134">Column definition</span></span>

<span data-ttu-id="515da-135">As definições da coluna contêm diferentes tipos de colunas para fornecer níveis diferentes de detalhes e dados financeiros.</span><span class="sxs-lookup"><span data-stu-id="515da-135">The column definitions contain different types of columns to provide different levels of detail and financial data.</span></span>

-   <span data-ttu-id="515da-136">**Desde o início do ano e variação – Tipos da coluna padrão:**</span><span class="sxs-lookup"><span data-stu-id="515da-136">**YTD and Variance – Default column types:**</span></span>
    -   <span data-ttu-id="515da-137">**DESC** – A descrição da definição da linha</span><span class="sxs-lookup"><span data-stu-id="515da-137">**DESC** – The description from the row definition</span></span>
    -   <span data-ttu-id="515da-138">**FD** – Dados financeiros acumulados do ano para o ano atual</span><span class="sxs-lookup"><span data-stu-id="515da-138">**FD** – Year-to-date financial data for the current year</span></span>
    -   <span data-ttu-id="515da-139">**FD** – Dados financeiros acumulados do último ano</span><span class="sxs-lookup"><span data-stu-id="515da-139">**FD** – Year-to-date financial data for the last year</span></span>
    -   <span data-ttu-id="515da-140">**CALC** – A variação ao subtrair o último ano deste ano</span><span class="sxs-lookup"><span data-stu-id="515da-140">**CALC** – The variance from subtracting last year from this year</span></span>

<!-- -->

-   <span data-ttu-id="515da-141">**Coluna desde o início do ano – Padrão:**</span><span class="sxs-lookup"><span data-stu-id="515da-141">**Year to Date Column – Default:**</span></span>
    -   <span data-ttu-id="515da-142">**DESC** – A descrição da definição da linha</span><span class="sxs-lookup"><span data-stu-id="515da-142">**DESC** – The description from the row definition</span></span>
    -   <span data-ttu-id="515da-143">**FD** – Dados financeiros acumulados do ano para o ano atual</span><span class="sxs-lookup"><span data-stu-id="515da-143">**FD** – Year-to-date financial data for the current year</span></span>



<a name="additional-resources"></a><span data-ttu-id="515da-144">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="515da-144">Additional resources</span></span>
--------

[<span data-ttu-id="515da-145">Visão geral de relatórios financeiros</span><span class="sxs-lookup"><span data-stu-id="515da-145">Financial reporting overview</span></span>](financial-reporting-getting-started.md)

[<span data-ttu-id="515da-146">Exibir relatórios financeiros</span><span class="sxs-lookup"><span data-stu-id="515da-146">View financial reports</span></span>](view-financial-reports.md)

[<span data-ttu-id="515da-147">Blog de Relatório Financeiro do Dynamics</span><span class="sxs-lookup"><span data-stu-id="515da-147">Dynamics Financial Reporting Blog</span></span>](https://blogs.msdn.com/b/dynamics_financial_reporting/)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]