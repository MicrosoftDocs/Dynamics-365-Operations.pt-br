---
title: Conteúdo do Power BI real vs orçamento
description: Este tópico descreve o Conteúdo do Power BI real versus orçamento. Ele explica como acessar os relatórios e fornece informações sobre o modelo de dados.
author: panolte
ms.date: 12/18/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BudgetTrackingWorkspace
audience: Application user, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: panolte
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.openlocfilehash: 9cc52f4cdab3084c9ac43078b0b0d534119ab514
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5744230"
---
# <a name="actual-vs-budget-power-bi-content"></a><span data-ttu-id="fc523-104">Conteúdo do Power BI real vs orçamento</span><span class="sxs-lookup"><span data-stu-id="fc523-104">Actual vs budget Power BI content</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="fc523-105">Este tópico descreve o conteúdo **Real vs. orçamento** do Microsoft Power BI.</span><span class="sxs-lookup"><span data-stu-id="fc523-105">This topic describes the **Actual vs budget** Microsoft Power BI content.</span></span> <span data-ttu-id="fc523-106">Ele explica como acessar os relatórios do Power BI e fornece informações sobre o modelo de dados e entidades que foram usados para criar o conteúdo.</span><span class="sxs-lookup"><span data-stu-id="fc523-106">It explains how to access the Power BI reports, and provides information about the data model and entities that were used to build the content.</span></span>

## <a name="overview"></a><span data-ttu-id="fc523-107">Visão Geral</span><span class="sxs-lookup"><span data-stu-id="fc523-107">Overview</span></span>

<span data-ttu-id="fc523-108">O conteúdo do **Real vs orçamento** do Power BI foi criado para indivíduos responsáveis por monitorar o desempenho real versus orçamento da organização.</span><span class="sxs-lookup"><span data-stu-id="fc523-108">The **Actual vs budget** Power BI content was created for individuals who are responsible for monitoring actual versus budget performance in their organization.</span></span> <span data-ttu-id="fc523-109">O conteúdo **Real vs orçamento** do Power BI fornece visibilidade em suas variações de orçamento.</span><span class="sxs-lookup"><span data-stu-id="fc523-109">The **Actual vs budget** Power BI content provides visibility into your budget variances.</span></span> <span data-ttu-id="fc523-110">Você pode analisar o orçamento do ano atual por categoria de conta, código de orçamento, conta principal, descrições de conta principal ou período fiscal para obter um melhor entendimento sobre a causa das variações.</span><span class="sxs-lookup"><span data-stu-id="fc523-110">You can analyze budget for the current year by account category, budget code, main account, main account descriptions, or fiscal period to get a better understanding of the cause of any variances.</span></span>

## <a name="accessing-the-power-bi-content"></a><span data-ttu-id="fc523-111">Acessando o conteúdo do Power BI</span><span class="sxs-lookup"><span data-stu-id="fc523-111">Accessing the Power BI content</span></span>
<span data-ttu-id="fc523-112">Os relatórios de conteúdo **Real vs orçamento** do Power BI são mostrados nos espaços de trabalho **Orçamentos e previsão do razão** e **CFO**.</span><span class="sxs-lookup"><span data-stu-id="fc523-112">Reports from the **Actual vs budget** Power BI content are shown in the **Ledger budget and forecasts** and **CFO** workspaces.</span></span>

## <a name="reports-that-are-included-in-the-power-bi-content"></a><span data-ttu-id="fc523-113">Relatórios incluídos no conteúdo do Power BI</span><span class="sxs-lookup"><span data-stu-id="fc523-113">Reports that are included in the Power BI content</span></span>
<span data-ttu-id="fc523-114">A tabela a seguir fornece detalhes sobre as métricas encontradas em cada página de relatório no conteúdo **Real vs orçamento** do Power BI.</span><span class="sxs-lookup"><span data-stu-id="fc523-114">The following table provides details about the metrics that are found on each report page in the **Actual vs budget** Power BI content.</span></span>

| <span data-ttu-id="fc523-115">Relatório</span><span class="sxs-lookup"><span data-stu-id="fc523-115">Report</span></span>                      | <span data-ttu-id="fc523-116">Métrica</span><span class="sxs-lookup"><span data-stu-id="fc523-116">Metrics</span></span>                                                                             |
|-----------------------------|-------------------------------------------------------------------------------------|
| <span data-ttu-id="fc523-117">Despesas - Real vs de orçamento</span><span class="sxs-lookup"><span data-stu-id="fc523-117">Expenses - Actual vs budget</span></span> | <ul><li><span data-ttu-id="fc523-118">Despesas totais deste ano</span><span class="sxs-lookup"><span data-stu-id="fc523-118">Total expenses this year</span></span></li><li><span data-ttu-id="fc523-119">Total de despesas de orçamento deste ano</span><span class="sxs-lookup"><span data-stu-id="fc523-119">Budget total expenses this year</span></span></li></ul>  |
| <span data-ttu-id="fc523-120">Receita - Real vs de Orçamento</span><span class="sxs-lookup"><span data-stu-id="fc523-120">Revenue - Actual vs budget</span></span>  | <ul><li><span data-ttu-id="fc523-121">Receita total deste ano</span><span class="sxs-lookup"><span data-stu-id="fc523-121">Total revenue this year</span></span></li><li><span data-ttu-id="fc523-122">Receita total de orçamento deste ano</span><span class="sxs-lookup"><span data-stu-id="fc523-122">Budget total revenue this year</span></span></li><ul>     |
| <span data-ttu-id="fc523-123">Despesa</span><span class="sxs-lookup"><span data-stu-id="fc523-123">Expense</span></span>                     | <ul><li><span data-ttu-id="fc523-124">Despesas totais deste ano</span><span class="sxs-lookup"><span data-stu-id="fc523-124">Total expenses this year</span></span></li><li><span data-ttu-id="fc523-125">Meta de despesas com base no orçamento</span><span class="sxs-lookup"><span data-stu-id="fc523-125">Goal for expenses based on budget</span></span></li><ul> |
| <span data-ttu-id="fc523-126">Receita</span><span class="sxs-lookup"><span data-stu-id="fc523-126">Revenue</span></span>                     | <ul><li><span data-ttu-id="fc523-127">Receita total deste ano</span><span class="sxs-lookup"><span data-stu-id="fc523-127">Total revenue this year</span></span></li><li><span data-ttu-id="fc523-128">Meta de receita com base no orçamento</span><span class="sxs-lookup"><span data-stu-id="fc523-128">Goal for revenue based on budget</span></span></li><ul>   |
| <span data-ttu-id="fc523-129">Renda líquida</span><span class="sxs-lookup"><span data-stu-id="fc523-129">Net income</span></span>                  | <ul><li><span data-ttu-id="fc523-130">Rendimento líquido deste ano</span><span class="sxs-lookup"><span data-stu-id="fc523-130">Net income this year</span></span></li><li><span data-ttu-id="fc523-131">Meta de rendimento líquido com base no orçamento</span><span class="sxs-lookup"><span data-stu-id="fc523-131">Goal for net income based on budget</span></span></li><ul>   |

## <a name="understanding-the-data-model-and-entities"></a><span data-ttu-id="fc523-132">Noções básicas sobre o modelo de dados e as entidades</span><span class="sxs-lookup"><span data-stu-id="fc523-132">Understanding the data model and entities</span></span>

| <span data-ttu-id="fc523-133">Entidade</span><span class="sxs-lookup"><span data-stu-id="fc523-133">Entity</span></span>                    | <span data-ttu-id="fc523-134">Conteúdo</span><span class="sxs-lookup"><span data-stu-id="fc523-134">Contents</span></span>                                                                         |
|---------------------------|----------------------------------------------------------------------------------|
| <span data-ttu-id="fc523-135">Atividades de contabilidade</span><span class="sxs-lookup"><span data-stu-id="fc523-135">General Ledger Activities</span></span> | <span data-ttu-id="fc523-136">Valores de transação referente à contabilidade</span><span class="sxs-lookup"><span data-stu-id="fc523-136">Transaction amounts for the general ledger</span></span>                                       |
| <span data-ttu-id="fc523-137">Atividades de orçamento</span><span class="sxs-lookup"><span data-stu-id="fc523-137">Budget Activities</span></span>         | <span data-ttu-id="fc523-138">Valores de transação para o registro de orçamento</span><span class="sxs-lookup"><span data-stu-id="fc523-138">Transaction amounts for the budget register</span></span>                                      |
| <span data-ttu-id="fc523-139">Contas Principais</span><span class="sxs-lookup"><span data-stu-id="fc523-139">Main Accounts</span></span>             | <span data-ttu-id="fc523-140">Contas principais para filtrar relatórios</span><span class="sxs-lookup"><span data-stu-id="fc523-140">Main accounts to filter reports by</span></span>                                               |
| <span data-ttu-id="fc523-141">Calendários fiscais</span><span class="sxs-lookup"><span data-stu-id="fc523-141">Fiscal Calendars</span></span>          | <span data-ttu-id="fc523-142">Calendários fiscais para filtrar relatórios</span><span class="sxs-lookup"><span data-stu-id="fc523-142">Fiscal calendars to filter reports by</span></span>                                            |
| <span data-ttu-id="fc523-143">Razões</span><span class="sxs-lookup"><span data-stu-id="fc523-143">Ledgers</span></span>                   | <span data-ttu-id="fc523-144">Razões que podem ser usados para filtrar relatório para o razão atual</span><span class="sxs-lookup"><span data-stu-id="fc523-144">Ledgers that can be used to filter the report to the current ledger</span></span>              |
| <span data-ttu-id="fc523-145">Códigos de orçamento</span><span class="sxs-lookup"><span data-stu-id="fc523-145">Budget Codes</span></span>              | <span data-ttu-id="fc523-146">Códigos de orçamento para filtrar relatórios</span><span class="sxs-lookup"><span data-stu-id="fc523-146">Budget codes to filter reports by</span></span>                                                |
| <span data-ttu-id="fc523-147">Entidades legais</span><span class="sxs-lookup"><span data-stu-id="fc523-147">Legal Entities</span></span>            | <span data-ttu-id="fc523-148">Entidades legais que podem ser usadas para filtrar relatório para a entidade legal atual</span><span class="sxs-lookup"><span data-stu-id="fc523-148">Legal entities that can be used to filter the report to the current legal entity</span></span> |


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]