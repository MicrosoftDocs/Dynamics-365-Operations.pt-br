---
title: Gerar um plano restrito
description: Este tópico explica como criar um plano que leve em consideração restrições de materiais e de capacidade.
author: ShylaThompson
manager: AnnBe
ms.date: 08/02/2019
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
ms.openlocfilehash: 6b5d37de41fe68845cec3f2285aed2484ac117aa
ms.sourcegitcommit: a368682f9cf3897347d155f1a2d4b33e555cc2c4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/08/2019
ms.locfileid: "1867164"
---
# <a name="generate-a-constrained-plan"></a><span data-ttu-id="e9331-103">Gerar um plano restrito</span><span class="sxs-lookup"><span data-stu-id="e9331-103">Generate a constrained plan</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="e9331-104">Este tópico explica como criar um plano que leve em consideração restrições de materiais e de capacidade.</span><span class="sxs-lookup"><span data-stu-id="e9331-104">This topic explains how to create a plan that takes into account both material and capacity constraints.</span></span> <span data-ttu-id="e9331-105">O plano garante que a fabricação não seja iniciada antes dos materiais estarem disponíveis e os recursos e não estarem reservados.</span><span class="sxs-lookup"><span data-stu-id="e9331-105">The plan ensures that manufacturing doesn't start before materials are available and resources are not overbooked.</span></span> 

<span data-ttu-id="e9331-106">A empresa de dados demo usada para criar este procedimento é USMF.</span><span class="sxs-lookup"><span data-stu-id="e9331-106">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="e9331-107">Esse procedimento é criado para o planejador de produção.</span><span class="sxs-lookup"><span data-stu-id="e9331-107">This procedure is intended for the production planner.</span></span>


## <a name="set-up-a-constrained-plan"></a><span data-ttu-id="e9331-108">Configurar um plano restrito</span><span class="sxs-lookup"><span data-stu-id="e9331-108">Set up a constrained plan</span></span>
1. <span data-ttu-id="e9331-109">Na página inicial, selecione o espaço de trabalho **Planejamento mestre**.</span><span class="sxs-lookup"><span data-stu-id="e9331-109">In the home page, select the **Master planning** workspace.</span></span>
2. <span data-ttu-id="e9331-110">Selecione **Planos mestres** na lista de links no lado direito da área de trabalho.</span><span class="sxs-lookup"><span data-stu-id="e9331-110">Select **Master plans** in the list of links on the far right side of the workspace.</span></span>
3. <span data-ttu-id="e9331-111">Na lista, localize e selecione o registro desejado.</span><span class="sxs-lookup"><span data-stu-id="e9331-111">In the list, find and select the desired record.</span></span> <span data-ttu-id="e9331-112">Exemplo: **StaticPlan**</span><span class="sxs-lookup"><span data-stu-id="e9331-112">Example: **StaticPlan**</span></span>  
4. <span data-ttu-id="e9331-113">Selecione **Sim** no campo **Capacidade finita**.</span><span class="sxs-lookup"><span data-stu-id="e9331-113">Select **Yes** in the **Finite capacity** field.</span></span>
5. <span data-ttu-id="e9331-114">No campo **Limite de tempo de capacidade finita**, insira `30`.</span><span class="sxs-lookup"><span data-stu-id="e9331-114">In the **Finite capacity time fence** field, enter `30`.</span></span>
6. <span data-ttu-id="e9331-115">Expanda a seção **Limites de tempo em dias**.</span><span class="sxs-lookup"><span data-stu-id="e9331-115">Expand the **Time fences in days** section.</span></span>
7. <span data-ttu-id="e9331-116">Selecione **Sim** no campo **Capacidade**.</span><span class="sxs-lookup"><span data-stu-id="e9331-116">Select **Yes** in the **Capacity** field.</span></span>
8. <span data-ttu-id="e9331-117">No campo **Limite de tempo de agendamento de capacidade (dias)**, insira um número.</span><span class="sxs-lookup"><span data-stu-id="e9331-117">In the **Capacity scheduling time fence (days)** field, enter a number.</span></span> <span data-ttu-id="e9331-118">Exemplo: `60`</span><span class="sxs-lookup"><span data-stu-id="e9331-118">Example: `60`</span></span>  
9. <span data-ttu-id="e9331-119">Selecione **Sim** no campo **Atrasos calculados**.</span><span class="sxs-lookup"><span data-stu-id="e9331-119">Select **Yes** in the **Calculated delays** field.</span></span>
10. <span data-ttu-id="e9331-120">No campo **Calcular limite de tempo para atrasos (dias)**, insira um número.</span><span class="sxs-lookup"><span data-stu-id="e9331-120">In the **Calculate delays time fence (days)** field, enter a number.</span></span> <span data-ttu-id="e9331-121">Exemplo: `60`</span><span class="sxs-lookup"><span data-stu-id="e9331-121">Example: `60`</span></span> 
11. <span data-ttu-id="e9331-122">Expanda a seção **Atrasos calculados**.</span><span class="sxs-lookup"><span data-stu-id="e9331-122">Expand the **Calculated delays** section.</span></span>
12. <span data-ttu-id="e9331-123">Selecione **Sim** em todos os campos **Adicionar o atraso calculado à data da requisição**.</span><span class="sxs-lookup"><span data-stu-id="e9331-123">Select **Yes** in all **Add the calculated delay to the requirement date** fields.</span></span>
13. <span data-ttu-id="e9331-124">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="e9331-124">Close the page.</span></span>

## <a name="create-a-constrained-plan"></a><span data-ttu-id="e9331-125">Criar um plano restrito</span><span class="sxs-lookup"><span data-stu-id="e9331-125">Create a constrained plan</span></span>
1. <span data-ttu-id="e9331-126">Selecione **Executar**.</span><span class="sxs-lookup"><span data-stu-id="e9331-126">Select **Run**.</span></span>
2. <span data-ttu-id="e9331-127">No campo **Plano mestre**, insira ou selecione o plano para o qual você configurou restrições.</span><span class="sxs-lookup"><span data-stu-id="e9331-127">In the **Master plan** field, enter or select the plan for which you have set up constraints.</span></span>  
3. <span data-ttu-id="e9331-128">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="e9331-128">Select **OK**.</span></span>
4. <span data-ttu-id="e9331-129">Selecione **Ordens planejadas**.</span><span class="sxs-lookup"><span data-stu-id="e9331-129">Select **Planned orders**.</span></span>

