---
title: Conteúdo do Power BI real vs orçamento
description: Este tópico descreve o Conteúdo do Power BI real versus orçamento. Ele explica como acessar os relatórios incluídos no conteúdo, além de fornecer informações sobre o modelo de dados e as entidades usadas para criar o conteúdo.
author: ryansandness
manager: AnnBe
ms.date: 12/18/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BudgetTrackingWorkspace
audience: Application user, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: ryansand
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.openlocfilehash: c801544e9e37a528203f5a1730aa8cb526d63dbf
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1553729"
---
# <a name="actual-vs-budget-power-bi-content"></a><span data-ttu-id="64bfb-104">Conteúdo do Power BI real vs orçamento</span><span class="sxs-lookup"><span data-stu-id="64bfb-104">Actual vs budget Power BI content</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="64bfb-105">Este tópico descreve o conteúdo **Real vs orçamento** do Microsoft Power BI.</span><span class="sxs-lookup"><span data-stu-id="64bfb-105">This topic describes the **Actual vs budget** Microsoft Power BI content.</span></span> <span data-ttu-id="64bfb-106">Ele explica como acessar os relatórios do Power BI e fornece informações sobre o modelo de dados e entidades que foram usados para criar o conteúdo.</span><span class="sxs-lookup"><span data-stu-id="64bfb-106">It explains how to access the Power BI reports, and provides information about the data model and entities that were used to build the content.</span></span>

## <a name="overview"></a><span data-ttu-id="64bfb-107">Visão Geral</span><span class="sxs-lookup"><span data-stu-id="64bfb-107">Overview</span></span>

<span data-ttu-id="64bfb-108">O conteúdo do **Real vs orçamento** do Power BI foi criado para indivíduos responsáveis por monitorar o desempenho real versus orçamento da organização.</span><span class="sxs-lookup"><span data-stu-id="64bfb-108">The **Actual vs budget** Power BI content was created for individuals who are responsible for monitoring actual versus budget performance in their organization.</span></span> <span data-ttu-id="64bfb-109">O conteúdo **Real vs orçamento** do Power BI fornece visibilidade em suas variações de orçamento.</span><span class="sxs-lookup"><span data-stu-id="64bfb-109">The **Actual vs budget** Power BI content provides visibility into your budget variances.</span></span> <span data-ttu-id="64bfb-110">Você pode analisar o orçamento do ano atual por categoria de conta, código de orçamento, conta principal, descrições de conta principal ou período fiscal para obter um melhor entendimento sobre a causa das variações.</span><span class="sxs-lookup"><span data-stu-id="64bfb-110">You can analyze budget for the current year by account category, budget code, main account, main account descriptions, or fiscal period to get a better understanding of the cause of any variances.</span></span>

## <a name="accessing-the-power-bi-content"></a><span data-ttu-id="64bfb-111">Acessando o conteúdo do Power BI</span><span class="sxs-lookup"><span data-stu-id="64bfb-111">Accessing the Power BI content</span></span>
<span data-ttu-id="64bfb-112">Os relatórios de conteúdo **Real vs orçamento** do Power BI são mostrados nos espaços de trabalho **Orçamentos e previsão do razão** e **CFO**.</span><span class="sxs-lookup"><span data-stu-id="64bfb-112">Reports from the **Actual vs budget** Power BI content are shown in the **Ledger budget and forecasts** and **CFO** workspaces.</span></span>

## <a name="reports-that-are-included-in-the-power-bi-content"></a><span data-ttu-id="64bfb-113">Relatórios incluídos no conteúdo do Power BI</span><span class="sxs-lookup"><span data-stu-id="64bfb-113">Reports that are included in the Power BI content</span></span>
<span data-ttu-id="64bfb-114">A tabela a seguir fornece detalhes sobre as métricas encontradas em cada página de relatório no conteúdo **Real vs orçamento** do Power BI.</span><span class="sxs-lookup"><span data-stu-id="64bfb-114">The following table provides details about the metrics that are found on each report page in the **Actual vs budget** Power BI content.</span></span>

| <span data-ttu-id="64bfb-115">Relatório</span><span class="sxs-lookup"><span data-stu-id="64bfb-115">Report</span></span>                      | <span data-ttu-id="64bfb-116">Métrica</span><span class="sxs-lookup"><span data-stu-id="64bfb-116">Metrics</span></span>                                                                             |
|-----------------------------|-------------------------------------------------------------------------------------|
| <span data-ttu-id="64bfb-117">Despesas - Real vs de orçamento</span><span class="sxs-lookup"><span data-stu-id="64bfb-117">Expenses - Actual vs budget</span></span> | <ul><li><span data-ttu-id="64bfb-118">Despesas totais deste ano</span><span class="sxs-lookup"><span data-stu-id="64bfb-118">Total expenses this year</span></span></li><li><span data-ttu-id="64bfb-119">Total de despesas de orçamento deste ano</span><span class="sxs-lookup"><span data-stu-id="64bfb-119">Budget total expenses this year</span></span></li></ul>  |
| <span data-ttu-id="64bfb-120">Receita - Real vs de Orçamento</span><span class="sxs-lookup"><span data-stu-id="64bfb-120">Revenue - Actual vs budget</span></span>  | <ul><li><span data-ttu-id="64bfb-121">Receita total deste ano</span><span class="sxs-lookup"><span data-stu-id="64bfb-121">Total revenue this year</span></span></li><li><span data-ttu-id="64bfb-122">Receita total de orçamento deste ano</span><span class="sxs-lookup"><span data-stu-id="64bfb-122">Budget total revenue this year</span></span></li><ul>     |
| <span data-ttu-id="64bfb-123">Despesa</span><span class="sxs-lookup"><span data-stu-id="64bfb-123">Expense</span></span>                     | <ul><li><span data-ttu-id="64bfb-124">Despesas totais deste ano</span><span class="sxs-lookup"><span data-stu-id="64bfb-124">Total expenses this year</span></span></li><li><span data-ttu-id="64bfb-125">Meta de despesas com base no orçamento</span><span class="sxs-lookup"><span data-stu-id="64bfb-125">Goal for expenses based on budget</span></span></li><ul> |
| <span data-ttu-id="64bfb-126">Receita</span><span class="sxs-lookup"><span data-stu-id="64bfb-126">Revenue</span></span>                     | <ul><li><span data-ttu-id="64bfb-127">Receita total deste ano</span><span class="sxs-lookup"><span data-stu-id="64bfb-127">Total revenue this year</span></span></li><li><span data-ttu-id="64bfb-128">Meta de receita com base no orçamento</span><span class="sxs-lookup"><span data-stu-id="64bfb-128">Goal for revenue based on budget</span></span></li><ul>   |
| <span data-ttu-id="64bfb-129">Renda líquida</span><span class="sxs-lookup"><span data-stu-id="64bfb-129">Net income</span></span>                  | <ul><li><span data-ttu-id="64bfb-130">Rendimento líquido deste ano</span><span class="sxs-lookup"><span data-stu-id="64bfb-130">Net income this year</span></span></li><li><span data-ttu-id="64bfb-131">Meta de rendimento líquido com base no orçamento</span><span class="sxs-lookup"><span data-stu-id="64bfb-131">Goal for net income based on budget</span></span></li><ul>   |

## <a name="understanding-the-data-model-and-entities"></a><span data-ttu-id="64bfb-132">Noções básicas sobre o modelo de dados e as entidades</span><span class="sxs-lookup"><span data-stu-id="64bfb-132">Understanding the data model and entities</span></span>

| <span data-ttu-id="64bfb-133">Entidade</span><span class="sxs-lookup"><span data-stu-id="64bfb-133">Entity</span></span>                    | <span data-ttu-id="64bfb-134">Conteúdo</span><span class="sxs-lookup"><span data-stu-id="64bfb-134">Contents</span></span>                                                                         |
|---------------------------|----------------------------------------------------------------------------------|
| <span data-ttu-id="64bfb-135">Atividades de contabilidade</span><span class="sxs-lookup"><span data-stu-id="64bfb-135">General Ledger Activities</span></span> | <span data-ttu-id="64bfb-136">Valores de transação referente à contabilidade</span><span class="sxs-lookup"><span data-stu-id="64bfb-136">Transaction amounts for the general ledger</span></span>                                       |
| <span data-ttu-id="64bfb-137">Atividades de orçamento</span><span class="sxs-lookup"><span data-stu-id="64bfb-137">Budget Activities</span></span>         | <span data-ttu-id="64bfb-138">Valores de transação para o registro de orçamento</span><span class="sxs-lookup"><span data-stu-id="64bfb-138">Transaction amounts for the budget register</span></span>                                      |
| <span data-ttu-id="64bfb-139">Contas Principais</span><span class="sxs-lookup"><span data-stu-id="64bfb-139">Main Accounts</span></span>             | <span data-ttu-id="64bfb-140">Contas principais para filtrar relatórios</span><span class="sxs-lookup"><span data-stu-id="64bfb-140">Main accounts to filter reports by</span></span>                                               |
| <span data-ttu-id="64bfb-141">Calendários fiscais</span><span class="sxs-lookup"><span data-stu-id="64bfb-141">Fiscal Calendars</span></span>          | <span data-ttu-id="64bfb-142">Calendários fiscais para filtrar relatórios</span><span class="sxs-lookup"><span data-stu-id="64bfb-142">Fiscal calendars to filter reports by</span></span>                                            |
| <span data-ttu-id="64bfb-143">Razões</span><span class="sxs-lookup"><span data-stu-id="64bfb-143">Ledgers</span></span>                   | <span data-ttu-id="64bfb-144">Razões que podem ser usados para filtrar relatório para o razão atual</span><span class="sxs-lookup"><span data-stu-id="64bfb-144">Ledgers that can be used to filter the report to the current ledger</span></span>              |
| <span data-ttu-id="64bfb-145">Códigos de orçamento</span><span class="sxs-lookup"><span data-stu-id="64bfb-145">Budget Codes</span></span>              | <span data-ttu-id="64bfb-146">Códigos de orçamento para filtrar relatórios</span><span class="sxs-lookup"><span data-stu-id="64bfb-146">Budget codes to filter reports by</span></span>                                                |
| <span data-ttu-id="64bfb-147">Entidades legais</span><span class="sxs-lookup"><span data-stu-id="64bfb-147">Legal Entities</span></span>            | <span data-ttu-id="64bfb-148">Entidades legais que podem ser usadas para filtrar relatório para a entidade legal atual</span><span class="sxs-lookup"><span data-stu-id="64bfb-148">Legal entities that can be used to filter the report to the current legal entity</span></span> |
