---
title: "Relatório financeiro do demonstrativo de renda"
description: "Este artigo descreve o relatório padrão para declarações de imposto. Também mostra os blocos de construção associados a este relatório."
author: jcart1106
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 12294
ms.assetid: 30820be0-d943-4f8b-8c25-6414ec393b3d
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 0017d13b7f7594462dfff4ef896f4139607d4bc5
ms.contentlocale: pt-br
ms.lasthandoff: 08/29/2017

---

# <a name="income-statement-financial-report"></a><span data-ttu-id="23a4a-104">Relatório financeiro do demonstrativo de renda</span><span class="sxs-lookup"><span data-stu-id="23a4a-104">Income statement financial report</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="23a4a-105">Este artigo descreve o relatório padrão para declarações de imposto.</span><span class="sxs-lookup"><span data-stu-id="23a4a-105">This article describes the default report for income statements.</span></span> <span data-ttu-id="23a4a-106">Também mostra os blocos de construção associados a este relatório.</span><span class="sxs-lookup"><span data-stu-id="23a4a-106">It also describes the building blocks that are associated with this report.</span></span> 

<a name="default-income-statement-report"></a><span data-ttu-id="23a4a-107">Relatório do demonstrativo de renda padrão</span><span class="sxs-lookup"><span data-stu-id="23a4a-107">Default income statement report</span></span>
-------------------------------

| <span data-ttu-id="23a4a-108">Relatório padrão</span><span class="sxs-lookup"><span data-stu-id="23a4a-108">Default report</span></span>             | <span data-ttu-id="23a4a-109">O que ele faz</span><span class="sxs-lookup"><span data-stu-id="23a4a-109">What it does</span></span>                                                                                              |
|----------------------------|-----------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="23a4a-110">Demonstrativo de renda – Padrão</span><span class="sxs-lookup"><span data-stu-id="23a4a-110">Income Statement – Default</span></span> | <span data-ttu-id="23a4a-111">Fornece uma visualização da lucratividade da organização para o período atual e para o acumulado do ano.</span><span class="sxs-lookup"><span data-stu-id="23a4a-111">Provides a view of the organization’s profitability for the current period and also for the year to date.</span></span> |

## <a name="building-blocks"></a><span data-ttu-id="23a4a-112">Bloco de construção</span><span class="sxs-lookup"><span data-stu-id="23a4a-112">Building blocks</span></span>
<span data-ttu-id="23a4a-113">O relatório financeiro do demonstrativo de renda usa os seguintes blocos de construção.</span><span class="sxs-lookup"><span data-stu-id="23a4a-113">The income statement financial report uses the following building blocks.</span></span>

| <span data-ttu-id="23a4a-114">Relatório padrão</span><span class="sxs-lookup"><span data-stu-id="23a4a-114">Default report</span></span>             | <span data-ttu-id="23a4a-115">Definição de linha</span><span class="sxs-lookup"><span data-stu-id="23a4a-115">Row definition</span></span>                     | <span data-ttu-id="23a4a-116">Definição de coluna</span><span class="sxs-lookup"><span data-stu-id="23a4a-116">Column definition</span></span>          |
|----------------------------|------------------------------------|----------------------------|
| <span data-ttu-id="23a4a-117">Demonstrativo de renda – Padrão</span><span class="sxs-lookup"><span data-stu-id="23a4a-117">Income Statement - Default</span></span> | <span data-ttu-id="23a4a-118">Resumo do demonstrativo de renda - Padrão</span><span class="sxs-lookup"><span data-stu-id="23a4a-118">Summary Income Statement - Default</span></span> | <span data-ttu-id="23a4a-119">Periódico e acumulado do ano - Padrão</span><span class="sxs-lookup"><span data-stu-id="23a4a-119">Periodic and YTD - Default</span></span> |

### <a name="row-definition"></a><span data-ttu-id="23a4a-120">Definição de linha</span><span class="sxs-lookup"><span data-stu-id="23a4a-120">Row definition</span></span>

<span data-ttu-id="23a4a-121">A definição da linha Resumo do demonstrativo de renda - Padrão contém uma seção para cada parte de um demonstrativo de renda tradicional.</span><span class="sxs-lookup"><span data-stu-id="23a4a-121">The row definition, Summary Income Statement – Default, contains a section for each part of a traditional income statement.</span></span> <span data-ttu-id="23a4a-122">A dimensão Categoria de conta principal é usada para criar esta definição da linha.</span><span class="sxs-lookup"><span data-stu-id="23a4a-122">The Main Account Category dimension is used to build this row definition.</span></span> <span data-ttu-id="23a4a-123">Consequentemente, qualquer pessoa pode gerar o relatório sem fazer modificações.</span><span class="sxs-lookup"><span data-stu-id="23a4a-123">Therefore, anyone can generate the report without having to make any modifications.</span></span>

### <a name="column-definition"></a><span data-ttu-id="23a4a-124">Definição da coluna</span><span class="sxs-lookup"><span data-stu-id="23a4a-124">Column Definition</span></span>

<span data-ttu-id="23a4a-125">As definições da coluna contêm diferentes tipos de colunas para fornecer níveis diferentes de detalhes e dados financeiros.</span><span class="sxs-lookup"><span data-stu-id="23a4a-125">The column definitions contain different types of columns to provide different levels of detail and financial data.</span></span>

-   <span data-ttu-id="23a4a-126">**Periódico e acumulado do ano - Tipos de coluna padrão:**</span><span class="sxs-lookup"><span data-stu-id="23a4a-126">**Periodic and YTD – Default column types:**</span></span>
    -   <span data-ttu-id="23a4a-127">**DESC** – A descrição da definição da linha</span><span class="sxs-lookup"><span data-stu-id="23a4a-127">**DESC** – The description from the row definition</span></span>
    -   <span data-ttu-id="23a4a-128">**DF** – Dados financeiros para o período atual</span><span class="sxs-lookup"><span data-stu-id="23a4a-128">**FD** – Financial data for the current period</span></span>
    -   <span data-ttu-id="23a4a-129">**DF** – Dados financeiros acumulados do ano</span><span class="sxs-lookup"><span data-stu-id="23a4a-129">**FD** – Financial data for the year to date</span></span>

 

<a name="see-also"></a><span data-ttu-id="23a4a-130">Consulte também</span><span class="sxs-lookup"><span data-stu-id="23a4a-130">See also</span></span>
--------

[<span data-ttu-id="23a4a-131">Relatórios financeiros</span><span class="sxs-lookup"><span data-stu-id="23a4a-131">Financial reporting</span></span>](financial-reporting-getting-started.md)

[<span data-ttu-id="23a4a-132">Exibir relatórios financeiros</span><span class="sxs-lookup"><span data-stu-id="23a4a-132">View financial reports</span></span>](view-financial-reports.md)

[<span data-ttu-id="23a4a-133">Blog de Relatório Financeiro do Dynamics</span><span class="sxs-lookup"><span data-stu-id="23a4a-133">Dynamics Financial Reporting Blog</span></span>](http://blogs.msdn.com/b/dynamics_financial_reporting/)




