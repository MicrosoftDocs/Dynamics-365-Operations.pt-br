--- 
title: "Monitorar uma execução do planejamento mestre"
description: "O planejador de produção deseja ver se uma execução do planejamento mestre está em andamento."
author: YuyuScheller
manager: AnnBe
ms.date: 06/10/2016
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
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 1e08d9fd3388561563e6fb982416186a652b4ce2
ms.contentlocale: pt-br
ms.lasthandoff: 09/29/2017

---
# <a name="monitor-a-master-planning-run"></a><span data-ttu-id="96549-103">Monitorar uma execução do planejamento mestre</span><span class="sxs-lookup"><span data-stu-id="96549-103">Monitor a master planning run</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="96549-104">O planejador de produção deseja ver se uma execução do planejamento mestre está em andamento.</span><span class="sxs-lookup"><span data-stu-id="96549-104">The production planner wants to see if a master planning run is in progress.</span></span> <span data-ttu-id="96549-105">Use empresa de dados demo USMF para completar este procedimento.</span><span class="sxs-lookup"><span data-stu-id="96549-105">Use the demo data company USMF to complete this procedure.</span></span>


## <a name="run-master-planning"></a><span data-ttu-id="96549-106">Executar planejamento mestre</span><span class="sxs-lookup"><span data-stu-id="96549-106">Run master planning</span></span>
1. <span data-ttu-id="96549-107">Clique em Planejamento mestre.</span><span class="sxs-lookup"><span data-stu-id="96549-107">Click Master planning.</span></span>
    * <span data-ttu-id="96549-108">Você encontrará isso no painel padrão.</span><span class="sxs-lookup"><span data-stu-id="96549-108">You'll find this on the default dashboard.</span></span>  
2. <span data-ttu-id="96549-109">No campo Plano, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="96549-109">In the Plan field, enter or select a value.</span></span>
    * <span data-ttu-id="96549-110">Exemplo: StaticPlan</span><span class="sxs-lookup"><span data-stu-id="96549-110">Example: StaticPlan</span></span>  
3. <span data-ttu-id="96549-111">Clique em Executar.</span><span class="sxs-lookup"><span data-stu-id="96549-111">Click Run.</span></span>
4. <span data-ttu-id="96549-112">Selecione Sim no campo Rastrear tempo de processamento.</span><span class="sxs-lookup"><span data-stu-id="96549-112">Select Yes in the Track processing time field.</span></span>
    * <span data-ttu-id="96549-113">Se o campo já estiver selecionado, pule esta etapa.</span><span class="sxs-lookup"><span data-stu-id="96549-113">If the field is already selected, skip this step.</span></span>  
5. <span data-ttu-id="96549-114">No campo Número de threads, insira um número.</span><span class="sxs-lookup"><span data-stu-id="96549-114">In the Number of threads field, enter a number.</span></span>
6. <span data-ttu-id="96549-115">Expanda os Registros para incluir a seção.</span><span class="sxs-lookup"><span data-stu-id="96549-115">Expand the Records to include section.</span></span>
7. <span data-ttu-id="96549-116">Clique em Filtro.</span><span class="sxs-lookup"><span data-stu-id="96549-116">Click Filter.</span></span>
8. <span data-ttu-id="96549-117">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="96549-117">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="96549-118">Marque a linha onde Campo = Número de item.</span><span class="sxs-lookup"><span data-stu-id="96549-118">Mark the row where Field = Item number.</span></span>  
9. <span data-ttu-id="96549-119">No campo Critérios, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="96549-119">In the Criteria field, enter or select a value.</span></span>
    * <span data-ttu-id="96549-120">Exemplo: T0001</span><span class="sxs-lookup"><span data-stu-id="96549-120">Example: T0001</span></span>  
10. <span data-ttu-id="96549-121">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="96549-121">Click OK.</span></span>
11. <span data-ttu-id="96549-122">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="96549-122">Click OK.</span></span>

## <a name="monitor-the-master-planning-run"></a><span data-ttu-id="96549-123">Monitore a execução do planejamento mestre</span><span class="sxs-lookup"><span data-stu-id="96549-123">Monitor the master planning run</span></span>
1. <span data-ttu-id="96549-124">Clique em Histórico.</span><span class="sxs-lookup"><span data-stu-id="96549-124">Click History.</span></span>
2. <span data-ttu-id="96549-125">Clique em Consultas.</span><span class="sxs-lookup"><span data-stu-id="96549-125">Click Inquiries.</span></span>
3. <span data-ttu-id="96549-126">Clique em Processar duração da tarefa.</span><span class="sxs-lookup"><span data-stu-id="96549-126">Click Process task duration.</span></span>
4. <span data-ttu-id="96549-127">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="96549-127">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="96549-128">Para cada item é possível obter uma visão geral do período necessária para preencher cada etapa de planejamento.</span><span class="sxs-lookup"><span data-stu-id="96549-128">For each item you can get an overview of how long it took to complete each planning step.</span></span>  


