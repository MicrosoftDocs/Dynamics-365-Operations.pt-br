---
title: Relatório financeiro do demonstrativo de renda
description: Este artigo descreve o relatório padrão para declarações de imposto. Também mostra os blocos de construção associados a este relatório.
author: jcart1106
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: FinancialReports
audience: Application User
ms.reviewer: roschlom
ms.custom: 12294
ms.assetid: 30820be0-d943-4f8b-8c25-6414ec393b3d
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 146d4b9946c1b29105cff637fa9d8803db3d0c0f
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4988768"
---
# <a name="income-statement-financial-report"></a><span data-ttu-id="9ef65-104">Relatório financeiro do demonstrativo de renda</span><span class="sxs-lookup"><span data-stu-id="9ef65-104">Income statement financial report</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="9ef65-105">Este artigo descreve o relatório padrão para declarações de imposto.</span><span class="sxs-lookup"><span data-stu-id="9ef65-105">This article describes the default report for income statements.</span></span> <span data-ttu-id="9ef65-106">Também mostra os blocos de construção associados a este relatório.</span><span class="sxs-lookup"><span data-stu-id="9ef65-106">It also describes the building blocks that are associated with this report.</span></span> 

<a name="default-income-statement-report"></a><span data-ttu-id="9ef65-107">Relatório do demonstrativo de renda padrão</span><span class="sxs-lookup"><span data-stu-id="9ef65-107">Default income statement report</span></span>
-------------------------------

| <span data-ttu-id="9ef65-108">Relatório padrão</span><span class="sxs-lookup"><span data-stu-id="9ef65-108">Default report</span></span>             | <span data-ttu-id="9ef65-109">O que ele faz</span><span class="sxs-lookup"><span data-stu-id="9ef65-109">What it does</span></span>                                                                                              |
|----------------------------|-----------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="9ef65-110">Demonstrativo de renda – Padrão</span><span class="sxs-lookup"><span data-stu-id="9ef65-110">Income Statement – Default</span></span> | <span data-ttu-id="9ef65-111">Fornece uma visualização da lucratividade da organização para o período atual e para o acumulado do ano.</span><span class="sxs-lookup"><span data-stu-id="9ef65-111">Provides a view of the organization’s profitability for the current period and also for the year to date.</span></span> |

## <a name="building-blocks"></a><span data-ttu-id="9ef65-112">Bloco de construção</span><span class="sxs-lookup"><span data-stu-id="9ef65-112">Building blocks</span></span>
<span data-ttu-id="9ef65-113">O relatório financeiro do demonstrativo de renda usa os seguintes blocos de construção.</span><span class="sxs-lookup"><span data-stu-id="9ef65-113">The income statement financial report uses the following building blocks.</span></span>

| <span data-ttu-id="9ef65-114">Relatório padrão</span><span class="sxs-lookup"><span data-stu-id="9ef65-114">Default report</span></span>             | <span data-ttu-id="9ef65-115">Definição de linha</span><span class="sxs-lookup"><span data-stu-id="9ef65-115">Row definition</span></span>                     | <span data-ttu-id="9ef65-116">Definição de coluna</span><span class="sxs-lookup"><span data-stu-id="9ef65-116">Column definition</span></span>          |
|----------------------------|------------------------------------|----------------------------|
| <span data-ttu-id="9ef65-117">Demonstrativo de renda – Padrão</span><span class="sxs-lookup"><span data-stu-id="9ef65-117">Income Statement - Default</span></span> | <span data-ttu-id="9ef65-118">Resumo do demonstrativo de renda - Padrão</span><span class="sxs-lookup"><span data-stu-id="9ef65-118">Summary Income Statement - Default</span></span> | <span data-ttu-id="9ef65-119">Periódico e acumulado do ano - Padrão</span><span class="sxs-lookup"><span data-stu-id="9ef65-119">Periodic and YTD - Default</span></span> |

### <a name="row-definition"></a><span data-ttu-id="9ef65-120">Definição de linha</span><span class="sxs-lookup"><span data-stu-id="9ef65-120">Row definition</span></span>

<span data-ttu-id="9ef65-121">A definição da linha Resumo do demonstrativo de renda - Padrão contém uma seção para cada parte de um demonstrativo de renda tradicional.</span><span class="sxs-lookup"><span data-stu-id="9ef65-121">The row definition, Summary Income Statement – Default, contains a section for each part of a traditional income statement.</span></span> <span data-ttu-id="9ef65-122">A dimensão Categoria de conta principal é usada para criar esta definição da linha.</span><span class="sxs-lookup"><span data-stu-id="9ef65-122">The Main Account Category dimension is used to build this row definition.</span></span> <span data-ttu-id="9ef65-123">Consequentemente, qualquer pessoa pode gerar o relatório sem fazer modificações.</span><span class="sxs-lookup"><span data-stu-id="9ef65-123">Therefore, anyone can generate the report without having to make any modifications.</span></span>

### <a name="column-definition"></a><span data-ttu-id="9ef65-124">Definição da coluna</span><span class="sxs-lookup"><span data-stu-id="9ef65-124">Column Definition</span></span>

<span data-ttu-id="9ef65-125">As definições da coluna contêm diferentes tipos de colunas para fornecer níveis diferentes de detalhes e dados financeiros.</span><span class="sxs-lookup"><span data-stu-id="9ef65-125">The column definitions contain different types of columns to provide different levels of detail and financial data.</span></span>

-   <span data-ttu-id="9ef65-126">**Periódico e acumulado do ano - Tipos de coluna padrão:**</span><span class="sxs-lookup"><span data-stu-id="9ef65-126">**Periodic and YTD – Default column types:**</span></span>
    -   <span data-ttu-id="9ef65-127">**DESC** – A descrição da definição da linha</span><span class="sxs-lookup"><span data-stu-id="9ef65-127">**DESC** – The description from the row definition</span></span>
    -   <span data-ttu-id="9ef65-128">**DF** – Dados financeiros para o período atual</span><span class="sxs-lookup"><span data-stu-id="9ef65-128">**FD** – Financial data for the current period</span></span>
    -   <span data-ttu-id="9ef65-129">**DF** – Dados financeiros acumulados do ano</span><span class="sxs-lookup"><span data-stu-id="9ef65-129">**FD** – Financial data for the year to date</span></span>



<a name="additional-resources"></a><span data-ttu-id="9ef65-130">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="9ef65-130">Additional resources</span></span>
--------

[<span data-ttu-id="9ef65-131">Visão geral de relatórios financeiros</span><span class="sxs-lookup"><span data-stu-id="9ef65-131">Financial reporting overview</span></span>](financial-reporting-getting-started.md)

[<span data-ttu-id="9ef65-132">Exibir relatórios financeiros</span><span class="sxs-lookup"><span data-stu-id="9ef65-132">View financial reports</span></span>](view-financial-reports.md)

[<span data-ttu-id="9ef65-133">Blog de Relatório Financeiro do Dynamics</span><span class="sxs-lookup"><span data-stu-id="9ef65-133">Dynamics Financial Reporting Blog</span></span>](https://community.dynamics.com/365/financeandoperations/b/dynamics-365-finance-blog)



