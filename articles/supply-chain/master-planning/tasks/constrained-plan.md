---
title: Gerar um plano restrito
description: Este procedimento mostra como criar um plano que leve em consideração restrições de materiais e de capacidade.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, ReqCreatePlanWorkspace, ReqTransPlanCard, ReqPlanSched
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 0e2265f7788fd2a4a37f6fb96d7562649dbc5b1c
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1556014"
---
# <a name="generate-a-constrained-plan"></a><span data-ttu-id="929a3-103">Gerar um plano restrito</span><span class="sxs-lookup"><span data-stu-id="929a3-103">Generate a constrained plan</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="929a3-104">Este procedimento mostra como criar um plano que leve em consideração restrições de materiais e de capacidade.</span><span class="sxs-lookup"><span data-stu-id="929a3-104">This procedure shows how to create a plan that takes into account both material and capacity constraints.</span></span> <span data-ttu-id="929a3-105">O plano garante que a fabricação não seja iniciada antes dos materiais estarem disponíveis e os recursos e não estarem reservados.</span><span class="sxs-lookup"><span data-stu-id="929a3-105">The plan ensures that manufacturing doesn't start before materials are available and resources are not overbooked.</span></span> 

<span data-ttu-id="929a3-106">A empresa de dados demo usada para criar este procedimento é USMF.</span><span class="sxs-lookup"><span data-stu-id="929a3-106">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="929a3-107">Esse procedimento é criado para o planejador de produção.</span><span class="sxs-lookup"><span data-stu-id="929a3-107">This procedure is intended for the production planner.</span></span>


## <a name="set-up-a-constrained-plan"></a><span data-ttu-id="929a3-108">Configurar um plano restrito</span><span class="sxs-lookup"><span data-stu-id="929a3-108">Set up a constrained plan</span></span>
1. <span data-ttu-id="929a3-109">Clique em Planejamento mestre.</span><span class="sxs-lookup"><span data-stu-id="929a3-109">Click Master planning.</span></span>
2. <span data-ttu-id="929a3-110">Clique em Planos mestre.</span><span class="sxs-lookup"><span data-stu-id="929a3-110">Click Master plans.</span></span>
3. <span data-ttu-id="929a3-111">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="929a3-111">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="929a3-112">Exemplo: StaticPlan</span><span class="sxs-lookup"><span data-stu-id="929a3-112">Example: StaticPlan</span></span>  
4. <span data-ttu-id="929a3-113">Selecione Sim no campo da capacidade finita.</span><span class="sxs-lookup"><span data-stu-id="929a3-113">Select Yes in the Finite capacity field.</span></span>
5. <span data-ttu-id="929a3-114">No tempo limite da Capacidade finita, insira '30'.</span><span class="sxs-lookup"><span data-stu-id="929a3-114">In the Finite capacity time fence field, enter '30'.</span></span>
6. <span data-ttu-id="929a3-115">Expanda os limites de tempo na seção de dias.</span><span class="sxs-lookup"><span data-stu-id="929a3-115">Expand the Time fences in days section.</span></span>
7. <span data-ttu-id="929a3-116">Selecione Sim no campo da Capacidade.</span><span class="sxs-lookup"><span data-stu-id="929a3-116">Select Yes in the Capacity field.</span></span>
8. <span data-ttu-id="929a3-117">No tempo limite de programação de capacidade (dias), insira um número.</span><span class="sxs-lookup"><span data-stu-id="929a3-117">In the Capacity scheduling time fence (days) field, enter a number.</span></span>
    * <span data-ttu-id="929a3-118">Exemplo 60</span><span class="sxs-lookup"><span data-stu-id="929a3-118">Example: 60</span></span>  
9. <span data-ttu-id="929a3-119">Selecione Sim no campo Atrasos calculados.</span><span class="sxs-lookup"><span data-stu-id="929a3-119">Select Yes in the Calculated delays field.</span></span>
10. <span data-ttu-id="929a3-120">No tempo limite de Atrasos calculados (dias), insira um número.</span><span class="sxs-lookup"><span data-stu-id="929a3-120">In the Calculate delays time fence (days) field, enter a number.</span></span>
    * <span data-ttu-id="929a3-121">Exemplo 60</span><span class="sxs-lookup"><span data-stu-id="929a3-121">Example: 60</span></span>  
11. <span data-ttu-id="929a3-122">Expanda a seção de atrasos calculada.</span><span class="sxs-lookup"><span data-stu-id="929a3-122">Expand the Calculated delays section.</span></span>
12. <span data-ttu-id="929a3-123">Selecione Sim no campo Adicionar o atraso calculado à data da requisição.</span><span class="sxs-lookup"><span data-stu-id="929a3-123">Select Yes in the Add the calculated delay to the requirement date field.</span></span>
13. <span data-ttu-id="929a3-124">Selecione Sim no campo Adicionar o atraso calculado à data da requisição.</span><span class="sxs-lookup"><span data-stu-id="929a3-124">Select Yes in the Add the calculated delay to the requirement date field.</span></span>
14. <span data-ttu-id="929a3-125">Selecione Sim no campo Adicionar o atraso calculado à data da requisição.</span><span class="sxs-lookup"><span data-stu-id="929a3-125">Select Yes in the Add the calculated delay to the requirement date field.</span></span>
15. <span data-ttu-id="929a3-126">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="929a3-126">Close the page.</span></span>

## <a name="create-a-constrained-plan"></a><span data-ttu-id="929a3-127">Criar um plano restrito</span><span class="sxs-lookup"><span data-stu-id="929a3-127">Create a constrained plan</span></span>
1. <span data-ttu-id="929a3-128">Clique em Executar.</span><span class="sxs-lookup"><span data-stu-id="929a3-128">Click Run.</span></span>
2. <span data-ttu-id="929a3-129">No campo Plano mestre, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="929a3-129">In the Master plan field, enter or select a value.</span></span>
    * <span data-ttu-id="929a3-130">Selecione o plano para o qual você configurou restrições.</span><span class="sxs-lookup"><span data-stu-id="929a3-130">Select the plan for which you have set up constraints.</span></span>  
3. <span data-ttu-id="929a3-131">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="929a3-131">Click OK.</span></span>
    * <span data-ttu-id="929a3-132">Isso pode levar algum tempo.</span><span class="sxs-lookup"><span data-stu-id="929a3-132">This may take a while.</span></span>  
4. <span data-ttu-id="929a3-133">Clique em Ordens planejadas.</span><span class="sxs-lookup"><span data-stu-id="929a3-133">Click Planned orders.</span></span>

