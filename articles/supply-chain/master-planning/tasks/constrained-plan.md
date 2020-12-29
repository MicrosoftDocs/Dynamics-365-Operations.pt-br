---
title: Gerar um plano restrito
description: Este tópico explica como criar um plano que leve em consideração restrições de materiais e de capacidade.
author: ShylaThompson
manager: tfehr
ms.date: 08/02/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, ReqCreatePlanWorkspace, ReqTransPlanCard, ReqPlanSched
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d8b9d5712dd1b4f9958de775e1a2224b64485d05
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4422204"
---
# <a name="generate-a-constrained-plan"></a><span data-ttu-id="8276b-103">Gerar um plano restrito</span><span class="sxs-lookup"><span data-stu-id="8276b-103">Generate a constrained plan</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="8276b-104">Este tópico explica como criar um plano que leve em consideração restrições de materiais e de capacidade.</span><span class="sxs-lookup"><span data-stu-id="8276b-104">This topic explains how to create a plan that takes into account both material and capacity constraints.</span></span> <span data-ttu-id="8276b-105">O plano garante que a fabricação não seja iniciada antes dos materiais estarem disponíveis e os recursos e não estarem reservados.</span><span class="sxs-lookup"><span data-stu-id="8276b-105">The plan ensures that manufacturing doesn't start before materials are available and resources are not overbooked.</span></span> 

<span data-ttu-id="8276b-106">A empresa de dados demo usada para criar este procedimento é USMF.</span><span class="sxs-lookup"><span data-stu-id="8276b-106">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="8276b-107">Esse procedimento é criado para o planejador de produção.</span><span class="sxs-lookup"><span data-stu-id="8276b-107">This procedure is intended for the production planner.</span></span>


## <a name="set-up-a-constrained-plan"></a><span data-ttu-id="8276b-108">Configurar um plano restrito</span><span class="sxs-lookup"><span data-stu-id="8276b-108">Set up a constrained plan</span></span>
1. <span data-ttu-id="8276b-109">Na página inicial, selecione o espaço de trabalho **Planejamento mestre**.</span><span class="sxs-lookup"><span data-stu-id="8276b-109">In the home page, select the **Master planning** workspace.</span></span>
2. <span data-ttu-id="8276b-110">Selecione **Planos mestres** na lista de links no lado direito da área de trabalho.</span><span class="sxs-lookup"><span data-stu-id="8276b-110">Select **Master plans** in the list of links on the far right side of the workspace.</span></span>
3. <span data-ttu-id="8276b-111">Na lista, localize e selecione o registro desejado.</span><span class="sxs-lookup"><span data-stu-id="8276b-111">In the list, find and select the desired record.</span></span> <span data-ttu-id="8276b-112">Exemplo: **StaticPlan**</span><span class="sxs-lookup"><span data-stu-id="8276b-112">Example: **StaticPlan**</span></span>  
4. <span data-ttu-id="8276b-113">Selecione **Sim** no campo **Capacidade finita**.</span><span class="sxs-lookup"><span data-stu-id="8276b-113">Select **Yes** in the **Finite capacity** field.</span></span>
5. <span data-ttu-id="8276b-114">No campo **Limite de tempo de capacidade finita**, insira `30`.</span><span class="sxs-lookup"><span data-stu-id="8276b-114">In the **Finite capacity time fence** field, enter `30`.</span></span>
6. <span data-ttu-id="8276b-115">Expanda a seção **Limites de tempo em dias**.</span><span class="sxs-lookup"><span data-stu-id="8276b-115">Expand the **Time fences in days** section.</span></span>
7. <span data-ttu-id="8276b-116">Selecione **Sim** no campo **Capacidade**.</span><span class="sxs-lookup"><span data-stu-id="8276b-116">Select **Yes** in the **Capacity** field.</span></span>
8. <span data-ttu-id="8276b-117">No campo **Limite de tempo de agendamento de capacidade (dias)**, insira um número.</span><span class="sxs-lookup"><span data-stu-id="8276b-117">In the **Capacity scheduling time fence (days)** field, enter a number.</span></span> <span data-ttu-id="8276b-118">Exemplo: `60`</span><span class="sxs-lookup"><span data-stu-id="8276b-118">Example: `60`</span></span>  
9. <span data-ttu-id="8276b-119">Selecione **Sim** no campo **Atrasos calculados**.</span><span class="sxs-lookup"><span data-stu-id="8276b-119">Select **Yes** in the **Calculated delays** field.</span></span>
10. <span data-ttu-id="8276b-120">No campo **Calcular limite de tempo para atrasos (dias)**, insira um número.</span><span class="sxs-lookup"><span data-stu-id="8276b-120">In the **Calculate delays time fence (days)** field, enter a number.</span></span> <span data-ttu-id="8276b-121">Exemplo: `60`</span><span class="sxs-lookup"><span data-stu-id="8276b-121">Example: `60`</span></span> 
11. <span data-ttu-id="8276b-122">Expanda a seção **Atrasos calculados**.</span><span class="sxs-lookup"><span data-stu-id="8276b-122">Expand the **Calculated delays** section.</span></span>
12. <span data-ttu-id="8276b-123">Selecione **Sim** em todos os campos **Adicionar o atraso calculado à data da requisição**.</span><span class="sxs-lookup"><span data-stu-id="8276b-123">Select **Yes** in all **Add the calculated delay to the requirement date** fields.</span></span>
13. <span data-ttu-id="8276b-124">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="8276b-124">Close the page.</span></span>

## <a name="create-a-constrained-plan"></a><span data-ttu-id="8276b-125">Criar um plano restrito</span><span class="sxs-lookup"><span data-stu-id="8276b-125">Create a constrained plan</span></span>
1. <span data-ttu-id="8276b-126">Selecione **Executar**.</span><span class="sxs-lookup"><span data-stu-id="8276b-126">Select **Run**.</span></span>
2. <span data-ttu-id="8276b-127">No campo **Plano mestre**, insira ou selecione o plano para o qual você configurou restrições.</span><span class="sxs-lookup"><span data-stu-id="8276b-127">In the **Master plan** field, enter or select the plan for which you have set up constraints.</span></span>  
3. <span data-ttu-id="8276b-128">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="8276b-128">Select **OK**.</span></span>
4. <span data-ttu-id="8276b-129">Selecione **Ordens planejadas**.</span><span class="sxs-lookup"><span data-stu-id="8276b-129">Select **Planned orders**.</span></span>

