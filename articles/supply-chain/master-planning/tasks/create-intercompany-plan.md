---
title: Criar um plano intercompanhia
description: Este procedimento mostra como criar um plano intercompanhia.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqIntercompanyPlanningGroupSetup,  ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d378a89bbb4de6d67db0019dc72a27945d50c4e9
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2019
ms.locfileid: "333728"
---
# <a name="create-an-intercompany-plan"></a><span data-ttu-id="e2928-103">Criar um plano intercompanhia</span><span class="sxs-lookup"><span data-stu-id="e2928-103">Create an intercompany plan</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="e2928-104">Este procedimento mostra como criar um plano intercompanhia.</span><span class="sxs-lookup"><span data-stu-id="e2928-104">This procedure shows how to create an intercompany plan.</span></span> <span data-ttu-id="e2928-105">A empresa de dados demo usada para criar este procedimento é USMF.</span><span class="sxs-lookup"><span data-stu-id="e2928-105">The demo data company used to create this procedure is USMF.</span></span>


## <a name="set-up-an-intercompany-planning-group"></a><span data-ttu-id="e2928-106">Configurar um grupo de planejamento intercompanhia</span><span class="sxs-lookup"><span data-stu-id="e2928-106">Set up an intercompany planning group</span></span> 
1. <span data-ttu-id="e2928-107">Vá para Grupos de planejamento intercompanhia.</span><span class="sxs-lookup"><span data-stu-id="e2928-107">Go to Intercompany planning groups.</span></span>
    * <span data-ttu-id="e2928-108">Planejamento mestre > Configuração > Grupos de planejamento intercompanhia.</span><span class="sxs-lookup"><span data-stu-id="e2928-108">Master planning > Setup > Intercompany planning groups</span></span>  
2. <span data-ttu-id="e2928-109">Use o Filtro Rápido para localizar registros.</span><span class="sxs-lookup"><span data-stu-id="e2928-109">Use the Quick Filter to find records.</span></span> <span data-ttu-id="e2928-110">Por exemplo, filtre o campo Nome com um valor de '10'.</span><span class="sxs-lookup"><span data-stu-id="e2928-110">For example, filter on the Name field with a value of '10'.</span></span>
3. <span data-ttu-id="e2928-111">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="e2928-111">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="e2928-112">Clique em Excluir.</span><span class="sxs-lookup"><span data-stu-id="e2928-112">Click Delete.</span></span>
    * <span data-ttu-id="e2928-113">Esta etapa é necessária para encurtar a execução de planejamento intercompanhia.</span><span class="sxs-lookup"><span data-stu-id="e2928-113">This step is necessary in order to shorten the intercompany planning run.</span></span>   <span data-ttu-id="e2928-114">O planejamento intercompanhia executará o planejamento mestre em todas as empresas de um grupo de planejamento a partir da sequência de planejamento mais baixa.</span><span class="sxs-lookup"><span data-stu-id="e2928-114">Intercompany planning will run master planning in all the companies in a planning group, starting from the lowest scheduling sequence.</span></span>  
5. <span data-ttu-id="e2928-115">Clique em Sim.</span><span class="sxs-lookup"><span data-stu-id="e2928-115">Click Yes.</span></span>
6. <span data-ttu-id="e2928-116">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="e2928-116">Close the page.</span></span>

## <a name="create-an-intercompany-plan"></a><span data-ttu-id="e2928-117">Criar um plano intercompanhia</span><span class="sxs-lookup"><span data-stu-id="e2928-117">Create an intercompany plan</span></span>
1. <span data-ttu-id="e2928-118">Clique em Planejamento mestre intercompanhia.</span><span class="sxs-lookup"><span data-stu-id="e2928-118">Click Intercompany master planning.</span></span>
    * <span data-ttu-id="e2928-119">Isso está no espaço de trabalho do Planejamento mestre.</span><span class="sxs-lookup"><span data-stu-id="e2928-119">This is on the Master planning workspace.</span></span>  
2. <span data-ttu-id="e2928-120">No campo Grupo de planejamento intercompanhia, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="e2928-120">In the Intercompany planning group field, click the drop-down button to open the lookup.</span></span>
3. <span data-ttu-id="e2928-121">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="e2928-121">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="e2928-122">Selecione Grupo de planejamento intercompanhia 10.</span><span class="sxs-lookup"><span data-stu-id="e2928-122">Select intercompany planning group 10.</span></span>  
4. <span data-ttu-id="e2928-123">No campo Número de iterações de planejamento intercompanhia, insira '2'.</span><span class="sxs-lookup"><span data-stu-id="e2928-123">In the Number of intercompany planning iterations field, enter '2'.</span></span>
    * <span data-ttu-id="e2928-124">O grupo de planejamento intercompanhia 10 tem dois membros.</span><span class="sxs-lookup"><span data-stu-id="e2928-124">Intercompany planning group 10 has two members.</span></span> <span data-ttu-id="e2928-125">Para propagar os atrasos da empresa de origem (USMF) para a empresa do cliente (DEMF), será necessário executar a intercompanhia nas duas empresas duas vezes.</span><span class="sxs-lookup"><span data-stu-id="e2928-125">In order to propagate the delays from the source company (USMF) to the customer company (DEMF), you will need to run intercompany in both companies two times.</span></span> <span data-ttu-id="e2928-126">A primeira iteração propagará a demanda e identificará os atrasos na empresa de origem (USMF).</span><span class="sxs-lookup"><span data-stu-id="e2928-126">The first iteration will propagate the demand and identify the delays in the source company (USMF).</span></span> <span data-ttu-id="e2928-127">A segunda iteração propagará os atrasos da USMF para a DEMF.</span><span class="sxs-lookup"><span data-stu-id="e2928-127">The second iteration will propagate the delays from USMF to DEMF.</span></span>  
5. <span data-ttu-id="e2928-128">No campo Primeira iteração, selecione uma opção.</span><span class="sxs-lookup"><span data-stu-id="e2928-128">In the First iteration field, select an option.</span></span>
6. <span data-ttu-id="e2928-129">No campo Primeira iteração, selecione 'Regeneração'.</span><span class="sxs-lookup"><span data-stu-id="e2928-129">In the First iteration field, select 'Regeneration'.</span></span>
7. <span data-ttu-id="e2928-130">No campo Iterações subsequentes, selecione 'Regeneração'.</span><span class="sxs-lookup"><span data-stu-id="e2928-130">In the Subsequent iterations field, select 'Regeneration'.</span></span>
8. <span data-ttu-id="e2928-131">No campo Número de threads, insira um número.</span><span class="sxs-lookup"><span data-stu-id="e2928-131">In the Number of threads field, enter a number.</span></span>
    * <span data-ttu-id="e2928-132">Isso representa o número de threads paralelos usados no planejamento.</span><span class="sxs-lookup"><span data-stu-id="e2928-132">This represents the number of parallel threads used for planning.</span></span>  
9. <span data-ttu-id="e2928-133">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="e2928-133">Click OK.</span></span>

## <a name="view-the-result-of-the-plan"></a><span data-ttu-id="e2928-134">Exibir o resultado do plano</span><span class="sxs-lookup"><span data-stu-id="e2928-134">View the result of the plan</span></span>
1. <span data-ttu-id="e2928-135">No campo Plano, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="e2928-135">In the Plan field, click the drop-down button to open the lookup.</span></span>
2. <span data-ttu-id="e2928-136">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="e2928-136">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="e2928-137">Clique no link para StaticPlan.</span><span class="sxs-lookup"><span data-stu-id="e2928-137">Click the link for StaticPlan.</span></span> <span data-ttu-id="e2928-138">Você precisa estar na empresa USMF.</span><span class="sxs-lookup"><span data-stu-id="e2928-138">You need to be in company USMF.</span></span>  
3. <span data-ttu-id="e2928-139">Clique em Ordens planejadas.</span><span class="sxs-lookup"><span data-stu-id="e2928-139">Click Planned orders.</span></span>

