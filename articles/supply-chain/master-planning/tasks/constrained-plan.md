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
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 72cddd58b7068e08cddf24df83da8da2f7af7168
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/01/2019
ms.locfileid: "1845275"
---
# <a name="generate-a-constrained-plan"></a><span data-ttu-id="3c6ba-103">Gerar um plano restrito</span><span class="sxs-lookup"><span data-stu-id="3c6ba-103">Generate a constrained plan</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="3c6ba-104">Este procedimento mostra como criar um plano que leve em consideração restrições de materiais e de capacidade.</span><span class="sxs-lookup"><span data-stu-id="3c6ba-104">This procedure shows how to create a plan that takes into account both material and capacity constraints.</span></span> <span data-ttu-id="3c6ba-105">O plano garante que a fabricação não seja iniciada antes dos materiais estarem disponíveis e os recursos e não estarem reservados.</span><span class="sxs-lookup"><span data-stu-id="3c6ba-105">The plan ensures that manufacturing doesn't start before materials are available and resources are not overbooked.</span></span> 

<span data-ttu-id="3c6ba-106">A empresa de dados demo usada para criar este procedimento é USMF.</span><span class="sxs-lookup"><span data-stu-id="3c6ba-106">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="3c6ba-107">Esse procedimento é criado para o planejador de produção.</span><span class="sxs-lookup"><span data-stu-id="3c6ba-107">This procedure is intended for the production planner.</span></span>


## <a name="set-up-a-constrained-plan"></a><span data-ttu-id="3c6ba-108">Configurar um plano restrito</span><span class="sxs-lookup"><span data-stu-id="3c6ba-108">Set up a constrained plan</span></span>
1. <span data-ttu-id="3c6ba-109">Clique em Planejamento mestre.</span><span class="sxs-lookup"><span data-stu-id="3c6ba-109">Click Master planning.</span></span>
2. <span data-ttu-id="3c6ba-110">Clique em Planos mestre.</span><span class="sxs-lookup"><span data-stu-id="3c6ba-110">Click Master plans.</span></span>
3. <span data-ttu-id="3c6ba-111">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="3c6ba-111">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="3c6ba-112">Exemplo: StaticPlan</span><span class="sxs-lookup"><span data-stu-id="3c6ba-112">Example: StaticPlan</span></span>  
4. <span data-ttu-id="3c6ba-113">Selecione Sim no campo da capacidade finita.</span><span class="sxs-lookup"><span data-stu-id="3c6ba-113">Select Yes in the Finite capacity field.</span></span>
5. <span data-ttu-id="3c6ba-114">No tempo limite da Capacidade finita, insira '30'.</span><span class="sxs-lookup"><span data-stu-id="3c6ba-114">In the Finite capacity time fence field, enter '30'.</span></span>
6. <span data-ttu-id="3c6ba-115">Expanda os limites de tempo na seção de dias.</span><span class="sxs-lookup"><span data-stu-id="3c6ba-115">Expand the Time fences in days section.</span></span>
7. <span data-ttu-id="3c6ba-116">Selecione Sim no campo da Capacidade.</span><span class="sxs-lookup"><span data-stu-id="3c6ba-116">Select Yes in the Capacity field.</span></span>
8. <span data-ttu-id="3c6ba-117">No tempo limite de programação de capacidade (dias), insira um número.</span><span class="sxs-lookup"><span data-stu-id="3c6ba-117">In the Capacity scheduling time fence (days) field, enter a number.</span></span>
    * <span data-ttu-id="3c6ba-118">Exemplo 60</span><span class="sxs-lookup"><span data-stu-id="3c6ba-118">Example: 60</span></span>  
9. <span data-ttu-id="3c6ba-119">Selecione Sim no campo Atrasos calculados.</span><span class="sxs-lookup"><span data-stu-id="3c6ba-119">Select Yes in the Calculated delays field.</span></span>
10. <span data-ttu-id="3c6ba-120">No tempo limite de Atrasos calculados (dias), insira um número.</span><span class="sxs-lookup"><span data-stu-id="3c6ba-120">In the Calculate delays time fence (days) field, enter a number.</span></span>
    * <span data-ttu-id="3c6ba-121">Exemplo 60</span><span class="sxs-lookup"><span data-stu-id="3c6ba-121">Example: 60</span></span>  
11. <span data-ttu-id="3c6ba-122">Expanda a seção de atrasos calculada.</span><span class="sxs-lookup"><span data-stu-id="3c6ba-122">Expand the Calculated delays section.</span></span>
12. <span data-ttu-id="3c6ba-123">Selecione Sim no campo Adicionar o atraso calculado à data da requisição.</span><span class="sxs-lookup"><span data-stu-id="3c6ba-123">Select Yes in the Add the calculated delay to the requirement date field.</span></span>
13. <span data-ttu-id="3c6ba-124">Selecione Sim no campo Adicionar o atraso calculado à data da requisição.</span><span class="sxs-lookup"><span data-stu-id="3c6ba-124">Select Yes in the Add the calculated delay to the requirement date field.</span></span>
14. <span data-ttu-id="3c6ba-125">Selecione Sim no campo Adicionar o atraso calculado à data da requisição.</span><span class="sxs-lookup"><span data-stu-id="3c6ba-125">Select Yes in the Add the calculated delay to the requirement date field.</span></span>
15. <span data-ttu-id="3c6ba-126">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="3c6ba-126">Close the page.</span></span>

## <a name="create-a-constrained-plan"></a><span data-ttu-id="3c6ba-127">Criar um plano restrito</span><span class="sxs-lookup"><span data-stu-id="3c6ba-127">Create a constrained plan</span></span>
1. <span data-ttu-id="3c6ba-128">Clique em Executar.</span><span class="sxs-lookup"><span data-stu-id="3c6ba-128">Click Run.</span></span>
2. <span data-ttu-id="3c6ba-129">No campo Plano mestre, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="3c6ba-129">In the Master plan field, enter or select a value.</span></span>
    * <span data-ttu-id="3c6ba-130">Selecione o plano para o qual você configurou restrições.</span><span class="sxs-lookup"><span data-stu-id="3c6ba-130">Select the plan for which you have set up constraints.</span></span>  
3. <span data-ttu-id="3c6ba-131">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="3c6ba-131">Click OK.</span></span>
    * <span data-ttu-id="3c6ba-132">Isso pode levar algum tempo.</span><span class="sxs-lookup"><span data-stu-id="3c6ba-132">This may take a while.</span></span>  
4. <span data-ttu-id="3c6ba-133">Clique em Ordens planejadas.</span><span class="sxs-lookup"><span data-stu-id="3c6ba-133">Click Planned orders.</span></span>

