--- 
title: Gerar um plano restrito
description: "Este procedimento mostra como criar um plano que leve em consideração restrições de materiais e de capacidade."
author: YuyuScheller
manager: AnnBe
ms.date: 03/02/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.author: yuyus
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 9deb615d05b90865ea6a050599bf91879b5688d0
ms.contentlocale: pt-br
ms.lasthandoff: 08/29/2017

---
# <a name="generate-a-constrained-plan"></a><span data-ttu-id="db3e4-103">Gerar um plano restrito</span><span class="sxs-lookup"><span data-stu-id="db3e4-103">Generate a constrained plan</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="db3e4-104">Este procedimento mostra como criar um plano que leve em consideração restrições de materiais e de capacidade.</span><span class="sxs-lookup"><span data-stu-id="db3e4-104">This procedure shows how to create a plan that takes into account both material and capacity constraints.</span></span> <span data-ttu-id="db3e4-105">O plano garante que a fabricação não seja iniciada antes dos materiais estarem disponíveis e os recursos e não estarem reservados.</span><span class="sxs-lookup"><span data-stu-id="db3e4-105">The plan ensures that manufacturing doesn't start before materials are available and resources are not overbooked.</span></span> 

<span data-ttu-id="db3e4-106">A empresa de dados demo usada para criar este procedimento é USMF.</span><span class="sxs-lookup"><span data-stu-id="db3e4-106">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="db3e4-107">Esse procedimento é criado para o planejador de produção.</span><span class="sxs-lookup"><span data-stu-id="db3e4-107">This procedure is intended for the production planner.</span></span>


## <a name="set-up-a-constrained-plan"></a><span data-ttu-id="db3e4-108">Configurar um plano restrito</span><span class="sxs-lookup"><span data-stu-id="db3e4-108">Set up a constrained plan</span></span>
1. <span data-ttu-id="db3e4-109">Clique em Planejamento mestre.</span><span class="sxs-lookup"><span data-stu-id="db3e4-109">Click Master planning.</span></span>
2. <span data-ttu-id="db3e4-110">Clique em Planos mestre.</span><span class="sxs-lookup"><span data-stu-id="db3e4-110">Click Master plans.</span></span>
3. <span data-ttu-id="db3e4-111">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="db3e4-111">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="db3e4-112">Exemplo: StaticPlan</span><span class="sxs-lookup"><span data-stu-id="db3e4-112">Example: StaticPlan</span></span>  
4. <span data-ttu-id="db3e4-113">Selecione Sim no campo da capacidade finita.</span><span class="sxs-lookup"><span data-stu-id="db3e4-113">Select Yes in the Finite capacity field.</span></span>
5. <span data-ttu-id="db3e4-114">No tempo limite da Capacidade finita, insira '30'.</span><span class="sxs-lookup"><span data-stu-id="db3e4-114">In the Finite capacity time fence field, enter '30'.</span></span>
6. <span data-ttu-id="db3e4-115">Expanda os limites de tempo na seção de dias.</span><span class="sxs-lookup"><span data-stu-id="db3e4-115">Expand the Time fences in days section.</span></span>
7. <span data-ttu-id="db3e4-116">Selecione Sim no campo da Capacidade.</span><span class="sxs-lookup"><span data-stu-id="db3e4-116">Select Yes in the Capacity field.</span></span>
8. <span data-ttu-id="db3e4-117">No tempo limite de programação de capacidade (dias), insira um número.</span><span class="sxs-lookup"><span data-stu-id="db3e4-117">In the Capacity scheduling time fence (days) field, enter a number.</span></span>
    * <span data-ttu-id="db3e4-118">Exemplo 60</span><span class="sxs-lookup"><span data-stu-id="db3e4-118">Example: 60</span></span>  
9. <span data-ttu-id="db3e4-119">Selecione Sim no campo Atrasos calculados.</span><span class="sxs-lookup"><span data-stu-id="db3e4-119">Select Yes in the Calculated delays field.</span></span>
10. <span data-ttu-id="db3e4-120">No tempo limite de Atrasos calculados (dias), insira um número.</span><span class="sxs-lookup"><span data-stu-id="db3e4-120">In the Calculate delays time fence (days) field, enter a number.</span></span>
    * <span data-ttu-id="db3e4-121">Exemplo 60</span><span class="sxs-lookup"><span data-stu-id="db3e4-121">Example: 60</span></span>  
11. <span data-ttu-id="db3e4-122">Expanda a seção de atrasos calculada.</span><span class="sxs-lookup"><span data-stu-id="db3e4-122">Expand the Calculated delays section.</span></span>
12. <span data-ttu-id="db3e4-123">Selecione Sim no campo Adicionar o atraso calculado à data da requisição.</span><span class="sxs-lookup"><span data-stu-id="db3e4-123">Select Yes in the Add the calculated delay to the requirement date field.</span></span>
13. <span data-ttu-id="db3e4-124">Selecione Sim no campo Adicionar o atraso calculado à data da requisição.</span><span class="sxs-lookup"><span data-stu-id="db3e4-124">Select Yes in the Add the calculated delay to the requirement date field.</span></span>
14. <span data-ttu-id="db3e4-125">Selecione Sim no campo Adicionar o atraso calculado à data da requisição.</span><span class="sxs-lookup"><span data-stu-id="db3e4-125">Select Yes in the Add the calculated delay to the requirement date field.</span></span>
15. <span data-ttu-id="db3e4-126">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="db3e4-126">Close the page.</span></span>

## <a name="create-a-constrained-plan"></a><span data-ttu-id="db3e4-127">Criar um plano restrito</span><span class="sxs-lookup"><span data-stu-id="db3e4-127">Create a constrained plan</span></span>
1. <span data-ttu-id="db3e4-128">Clique em Executar.</span><span class="sxs-lookup"><span data-stu-id="db3e4-128">Click Run.</span></span>
2. <span data-ttu-id="db3e4-129">No campo Plano mestre, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="db3e4-129">In the Master plan field, enter or select a value.</span></span>
    * <span data-ttu-id="db3e4-130">Selecione o plano para o qual você configurou restrições.</span><span class="sxs-lookup"><span data-stu-id="db3e4-130">Select the plan for which you have set up constraints.</span></span>  
3. <span data-ttu-id="db3e4-131">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="db3e4-131">Click OK.</span></span>
    * <span data-ttu-id="db3e4-132">Isso pode levar algum tempo.</span><span class="sxs-lookup"><span data-stu-id="db3e4-132">This may take a while.</span></span>  
4. <span data-ttu-id="db3e4-133">Clique em Ordens planejadas.</span><span class="sxs-lookup"><span data-stu-id="db3e4-133">Click Planned orders.</span></span>


