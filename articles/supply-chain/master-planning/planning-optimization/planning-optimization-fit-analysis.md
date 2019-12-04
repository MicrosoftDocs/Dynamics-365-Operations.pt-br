---
title: Análise de ajuste da Otimização de Planejamento
description: Este tópico explica como verificar sua configuração e seus dados atuais em relação aos recursos da funcionalidade Otimização de Planejamento.
author: ChristianRytt
manager: AnnBe
ms.date: 1030/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: AX 10.0.5
ms.openlocfilehash: 26b067f8526df16474c0ab52d0abf816170ff5cb
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/06/2019
ms.locfileid: "2773902"
---
[!include [banner](../../includes/preview-banner.md)]
[!include [banner](../../includes/banner.md)]

# <a name="planning-optimization-fit-analysis"></a><span data-ttu-id="e1e51-103">Análise de ajuste da Otimização de Planejamento</span><span class="sxs-lookup"><span data-stu-id="e1e51-103">Planning Optimization fit analysis</span></span>

<span data-ttu-id="e1e51-104">Para ver o grau de compatibilidade da sua configuração e seus dados atuais com a funcionalidade Otimização de Planejamento, acesse **Planejamento mestre** \> **Configuração** \> **Análise de ajuste à Otimização de Planejamento** e então selecione **Executar análise**.</span><span class="sxs-lookup"><span data-stu-id="e1e51-104">To see how compatible your current setup and data are with the Planning Optimization functionality, go to **Master planning** \> **Setup** \> **Planning Optimization fit analysis**, and then select **Run analysis**.</span></span> <span data-ttu-id="e1e51-105">Se a análise localizar inconsistências, elas serão listadas na mesma página.</span><span class="sxs-lookup"><span data-stu-id="e1e51-105">If the analysis finds any inconsistencies, they are listed on the same page.</span></span> <span data-ttu-id="e1e51-106">(A análise pode demorar alguns minutos).</span><span class="sxs-lookup"><span data-stu-id="e1e51-106">(The analysis can take a few minutes to run.)</span></span>

> [!NOTE]
> <span data-ttu-id="e1e51-107">Se forem encontradas inconsistências, você ainda poderá usar a Otimização de Planejamento.</span><span class="sxs-lookup"><span data-stu-id="e1e51-107">If inconsistencies are found, you can still use Planning Optimization.</span></span> <span data-ttu-id="e1e51-108">Os resultados da análise de ajuste simplesmente mostram locais onde os serviços de planejamento não honrarão sua configuração atual.</span><span class="sxs-lookup"><span data-stu-id="e1e51-108">The results of the fit analysis just show places where the planning service won't honor your current setup.</span></span> <span data-ttu-id="e1e51-109">Em outras palavras, eles mostram os locais onde alguns processos podem estar sendo ignorados ou onde não têm suporte.</span><span class="sxs-lookup"><span data-stu-id="e1e51-109">In other words, they show places where some processes might be ignored or might not be supported.</span></span>

## <a name="analysis-results-example-1"></a><span data-ttu-id="e1e51-110">Resultados da análise: exemplo 1</span><span class="sxs-lookup"><span data-stu-id="e1e51-110">Analysis results: Example 1</span></span>

- <span data-ttu-id="e1e51-111">**Recurso:** produção</span><span class="sxs-lookup"><span data-stu-id="e1e51-111">**Feature:** Production</span></span>
- <span data-ttu-id="e1e51-112">**Problema:** itens com o nível de BOM maior do que zero: 56</span><span class="sxs-lookup"><span data-stu-id="e1e51-112">**Issue:** Items with BOM level greater than zero: 56</span></span>
- <span data-ttu-id="e1e51-113">**Explicação:** a análise de ajuste encontrou 56 itens com uma configuração de lista de materiais (BOM) de produção.</span><span class="sxs-lookup"><span data-stu-id="e1e51-113">**Explanation:** The fit analysis found 56 items that have a bill of materials (BOM) setup for production.</span></span> <span data-ttu-id="e1e51-114">Como a versão atual da Otimização de Planejamento não dá suporte a produção, a Otimização de Planejamento gerará ordens de compra planejadas em vez de ordens de produção planejadas.</span><span class="sxs-lookup"><span data-stu-id="e1e51-114">Because the current version of Planning Optimization doesn't support production, Planning Optimization will generate planned purchase orders instead of planned production orders.</span></span> <span data-ttu-id="e1e51-115">Também mostrará um aviso que lista os itens afetados.</span><span class="sxs-lookup"><span data-stu-id="e1e51-115">It will also show a warning that lists the affected items.</span></span>

### <a name="analysis-results-example-2"></a><span data-ttu-id="e1e51-116">Resultados da análise: exemplo 2</span><span class="sxs-lookup"><span data-stu-id="e1e51-116">Analysis results: Example 2</span></span>

- <span data-ttu-id="e1e51-117">**Recurso:** ações</span><span class="sxs-lookup"><span data-stu-id="e1e51-117">**Feature:** Actions</span></span>
- <span data-ttu-id="e1e51-118">**Problema:** grupos de cobertura com cálculo de ações habilitado: 6</span><span class="sxs-lookup"><span data-stu-id="e1e51-118">**Issue:** Coverage groups with actions calculation enabled: 6</span></span>
- <span data-ttu-id="e1e51-119">**Explicação:** a análise de ajuste encontrou seis grupos de cobertura onde o cálculo de ação está ativado.</span><span class="sxs-lookup"><span data-stu-id="e1e51-119">**Explanation:** The fit analysis found six coverage groups where action calculation is turned on.</span></span> <span data-ttu-id="e1e51-120">Como a versão atual da Otimização de Planejamento não dá suporte a ações, nenhuma ação será gerada durante o planejamento mestre.</span><span class="sxs-lookup"><span data-stu-id="e1e51-120">Because the current version of Planning Optimization doesn't support actions, no actions will be generated during master planning.</span></span>

## <a name="related-resources"></a><span data-ttu-id="e1e51-121">Recursos relacionados</span><span class="sxs-lookup"><span data-stu-id="e1e51-121">Related resources</span></span>

[<span data-ttu-id="e1e51-122">Visão geral da Otimização de Planejamento</span><span class="sxs-lookup"><span data-stu-id="e1e51-122">Planning Optimization overview</span></span>](planning-optimization-overview.md)

[<span data-ttu-id="e1e51-123">Introdução à Otimização de Planejamento</span><span class="sxs-lookup"><span data-stu-id="e1e51-123">Get started with Planning Optimization</span></span>](get-started.md)

[<span data-ttu-id="e1e51-124">Exibir logs de histórico de plano e de planejamento</span><span class="sxs-lookup"><span data-stu-id="e1e51-124">View plan history and planning logs</span></span>](plan-history-logs.md)

[<span data-ttu-id="e1e51-125">Aplicar filtros a um plano</span><span class="sxs-lookup"><span data-stu-id="e1e51-125">Apply filters to a plan</span></span>](plan-filters.md)

[<span data-ttu-id="e1e51-126">Cancelar um trabalho de planejamento</span><span class="sxs-lookup"><span data-stu-id="e1e51-126">Cancel a planning job</span></span>](cancel-planning-job.md)
