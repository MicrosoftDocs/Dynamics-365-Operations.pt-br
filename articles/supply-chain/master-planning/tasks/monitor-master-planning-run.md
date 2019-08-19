---
title: Monitorar uma execução do planejamento mestre
description: O planejador de produção deseja ver se uma execução do planejamento mestre está em andamento.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, ReqCreatePlanWorkspace, ReqTransPlanCard, SysQueryForm, InventItemIdLookupSimple, ReqLog, ReqProcessTaskTrace
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b923b215528ecceaed9b5057ddb736ec959f1d65
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/01/2019
ms.locfileid: "1845104"
---
# <a name="monitor-a-master-planning-run"></a><span data-ttu-id="67022-103">Monitorar uma execução do planejamento mestre</span><span class="sxs-lookup"><span data-stu-id="67022-103">Monitor a master planning run</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="67022-104">O planejador de produção deseja ver se uma execução do planejamento mestre está em andamento.</span><span class="sxs-lookup"><span data-stu-id="67022-104">The production planner wants to see if a master planning run is in progress.</span></span> <span data-ttu-id="67022-105">Use empresa de dados demo USMF para completar este procedimento.</span><span class="sxs-lookup"><span data-stu-id="67022-105">Use the demo data company USMF to complete this procedure.</span></span>


## <a name="run-master-planning"></a><span data-ttu-id="67022-106">Executar planejamento mestre</span><span class="sxs-lookup"><span data-stu-id="67022-106">Run master planning</span></span>
1. <span data-ttu-id="67022-107">Clique em Planejamento mestre.</span><span class="sxs-lookup"><span data-stu-id="67022-107">Click Master planning.</span></span>
    * <span data-ttu-id="67022-108">Você encontrará isso no painel padrão.</span><span class="sxs-lookup"><span data-stu-id="67022-108">You'll find this on the default dashboard.</span></span>  
2. <span data-ttu-id="67022-109">No campo Plano, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="67022-109">In the Plan field, enter or select a value.</span></span>
    * <span data-ttu-id="67022-110">Exemplo: StaticPlan</span><span class="sxs-lookup"><span data-stu-id="67022-110">Example: StaticPlan</span></span>  
3. <span data-ttu-id="67022-111">Clique em Executar.</span><span class="sxs-lookup"><span data-stu-id="67022-111">Click Run.</span></span>
4. <span data-ttu-id="67022-112">Selecione Sim no campo Rastrear tempo de processamento.</span><span class="sxs-lookup"><span data-stu-id="67022-112">Select Yes in the Track processing time field.</span></span>
    * <span data-ttu-id="67022-113">Se o campo já estiver selecionado, pule esta etapa.</span><span class="sxs-lookup"><span data-stu-id="67022-113">If the field is already selected, skip this step.</span></span>  
5. <span data-ttu-id="67022-114">No campo Número de threads, insira um número.</span><span class="sxs-lookup"><span data-stu-id="67022-114">In the Number of threads field, enter a number.</span></span>
6. <span data-ttu-id="67022-115">Expanda os Registros para incluir a seção.</span><span class="sxs-lookup"><span data-stu-id="67022-115">Expand the Records to include section.</span></span>
7. <span data-ttu-id="67022-116">Clique em Filtro.</span><span class="sxs-lookup"><span data-stu-id="67022-116">Click Filter.</span></span>
8. <span data-ttu-id="67022-117">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="67022-117">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="67022-118">Marque a linha onde Campo = Número de item.</span><span class="sxs-lookup"><span data-stu-id="67022-118">Mark the row where Field = Item number.</span></span>  
9. <span data-ttu-id="67022-119">No campo Critérios, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="67022-119">In the Criteria field, enter or select a value.</span></span>
    * <span data-ttu-id="67022-120">Exemplo: T0001</span><span class="sxs-lookup"><span data-stu-id="67022-120">Example: T0001</span></span>  
10. <span data-ttu-id="67022-121">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="67022-121">Click OK.</span></span>
11. <span data-ttu-id="67022-122">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="67022-122">Click OK.</span></span>

## <a name="monitor-the-master-planning-run"></a><span data-ttu-id="67022-123">Monitore a execução do planejamento mestre</span><span class="sxs-lookup"><span data-stu-id="67022-123">Monitor the master planning run</span></span>
1. <span data-ttu-id="67022-124">Clique em Histórico.</span><span class="sxs-lookup"><span data-stu-id="67022-124">Click History.</span></span>
2. <span data-ttu-id="67022-125">Clique em Consultas.</span><span class="sxs-lookup"><span data-stu-id="67022-125">Click Inquiries.</span></span>
3. <span data-ttu-id="67022-126">Clique em Processar duração da tarefa.</span><span class="sxs-lookup"><span data-stu-id="67022-126">Click Process task duration.</span></span>
4. <span data-ttu-id="67022-127">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="67022-127">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="67022-128">Para cada item é possível obter uma visão geral do período necessária para preencher cada etapa de planejamento.</span><span class="sxs-lookup"><span data-stu-id="67022-128">For each item you can get an overview of how long it took to complete each planning step.</span></span>  

