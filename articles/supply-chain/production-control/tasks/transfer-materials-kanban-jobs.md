--- 
title: Transferir materiais com trabalhos kanban (somente em fevereiro de 2016)
description: "Esse procedimento se concentra na execução de um trabalho kanban de retirada para transferir materiais."
author: ChristianRytt
manager: AnnBe
ms.date: 02/07/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: c79480d844627a7eed8129515924f1f70ad04f95
ms.contentlocale: pt-br
ms.lasthandoff: 08/29/2017

---
# <a name="transfer-materials-with-kanban-jobs-february-2016-only"></a><span data-ttu-id="1cae9-103">Transferir materiais com trabalhos kanban (somente em fevereiro de 2016)</span><span class="sxs-lookup"><span data-stu-id="1cae9-103">Transfer materials with kanban jobs (February 2016 only)</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="1cae9-104">Esse procedimento se concentra na execução de um trabalho kanban de retirada para transferir materiais.</span><span class="sxs-lookup"><span data-stu-id="1cae9-104">This procedure focuses on executing a withdrawal kanban job to transfer materials.</span></span> <span data-ttu-id="1cae9-105">A empresa de dados demo usada para criar este procedimento é USMF.</span><span class="sxs-lookup"><span data-stu-id="1cae9-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="1cae9-106">Esse procedimento é destinado ao trabalhador do depósito.</span><span class="sxs-lookup"><span data-stu-id="1cae9-106">This procedure is intended for the warehouse worker.</span></span>


## <a name="display-transfer-jobs"></a><span data-ttu-id="1cae9-107">Exibir trabalhos de transferência</span><span class="sxs-lookup"><span data-stu-id="1cae9-107">Display transfer jobs</span></span>
1. <span data-ttu-id="1cae9-108">Vá para Controle de produção > Kanban > Quadro kanban para trabalhos de transferência.</span><span class="sxs-lookup"><span data-stu-id="1cae9-108">Go to Production control > Kanban > Kanban board for transfer jobs.</span></span>
2. <span data-ttu-id="1cae9-109">Expandir ou recolher a seção Filtros.</span><span class="sxs-lookup"><span data-stu-id="1cae9-109">Expand or collapse the Filters section.</span></span>
    * <span data-ttu-id="1cae9-110">Na seção Filtros, você pode especificar quais trabalhos você deseja visualizar filtrando por Fluxo de produção, Nome da atividade, Do depósito e localização, e Para o depósito e localização.</span><span class="sxs-lookup"><span data-stu-id="1cae9-110">In the Filters section, you can specify what jobs you want to see by filtering on Production flow, Activity name, From warehouse and location, and To warehouse and location.</span></span>  
3. <span data-ttu-id="1cae9-111">No campo Do depósito, digite '11'.</span><span class="sxs-lookup"><span data-stu-id="1cae9-111">In the From warehouse field, type '11'.</span></span>
4. <span data-ttu-id="1cae9-112">No campo Para o local, digite '12'.</span><span class="sxs-lookup"><span data-stu-id="1cae9-112">In the To location field, type '12'.</span></span>

## <a name="start-a-transfer-job"></a><span data-ttu-id="1cae9-113">Iniciar um trabalho de transferência</span><span class="sxs-lookup"><span data-stu-id="1cae9-113">Start a transfer job</span></span>
1. <span data-ttu-id="1cae9-114">Na lista, desmarque a linha selecionada - se houver alguma.</span><span class="sxs-lookup"><span data-stu-id="1cae9-114">In the list, deselect the selected row - if any.</span></span>
2. <span data-ttu-id="1cae9-115">Na lista, selecione a linha 4.</span><span class="sxs-lookup"><span data-stu-id="1cae9-115">In the list, select row 4.</span></span>
    * <span data-ttu-id="1cae9-116">Selecione o primeiro trabalho com o status Não planejado.</span><span class="sxs-lookup"><span data-stu-id="1cae9-116">Select the first job with status Not planned.</span></span> <span data-ttu-id="1cae9-117">Verifique se este é o único trabalho selecionado.</span><span class="sxs-lookup"><span data-stu-id="1cae9-117">Make sure this is the only job selected.</span></span>  
3. <span data-ttu-id="1cae9-118">Clique em Iniciar.</span><span class="sxs-lookup"><span data-stu-id="1cae9-118">Click Start.</span></span>
    * <span data-ttu-id="1cae9-119">Observe que um ícone indica que o trabalho esta iniciado.</span><span class="sxs-lookup"><span data-stu-id="1cae9-119">Notice that an icon indicates that the job is started.</span></span>  

## <a name="select-a-second-transfer-job-and-change-quantity"></a><span data-ttu-id="1cae9-120">Selecione um segundo trabalho de transferência e altere a quantidade</span><span class="sxs-lookup"><span data-stu-id="1cae9-120">Select a second transfer job and change quantity</span></span>
1. <span data-ttu-id="1cae9-121">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="1cae9-121">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="1cae9-122">Você pode ter vários trabalhos selecionados, mas por enquanto selecione a linha 5.</span><span class="sxs-lookup"><span data-stu-id="1cae9-122">You can have multiple jobs selected, but for now select row 5.</span></span>  
2. <span data-ttu-id="1cae9-123">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="1cae9-123">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="1cae9-124">Verifique se o trabalho da etapa anterior é o único selecionado.</span><span class="sxs-lookup"><span data-stu-id="1cae9-124">Make sure the job in the previous step is the only one selected.</span></span> <span data-ttu-id="1cae9-125">Desmarque todos os outros trabalhos.</span><span class="sxs-lookup"><span data-stu-id="1cae9-125">Deselect all other jobs.</span></span>  
3. <span data-ttu-id="1cae9-126">Anote o valor do campo Quantidade do trabalho para referência futura</span><span class="sxs-lookup"><span data-stu-id="1cae9-126">Note the value in the Job quantity field to reference later</span></span>
4. <span data-ttu-id="1cae9-127">Defina Quantidade do trabalho para '30'.</span><span class="sxs-lookup"><span data-stu-id="1cae9-127">Set Job quantity to '30'.</span></span>
    * <span data-ttu-id="1cae9-128">Observe o aviso!</span><span class="sxs-lookup"><span data-stu-id="1cae9-128">Notice the warning!</span></span> <span data-ttu-id="1cae9-129">Você não tem permissão para transferir 30.</span><span class="sxs-lookup"><span data-stu-id="1cae9-129">You are not allowed to transfer 30.</span></span> <span data-ttu-id="1cae9-130">De acordo com a instalação da regra kanban, você só pode transferir a quantidade original.</span><span class="sxs-lookup"><span data-stu-id="1cae9-130">According to the setup of the kanban rule, you can only transfer the original quantity.</span></span>  
5. <span data-ttu-id="1cae9-131">Use o valor anotado anteriormente no campo Quantidade do trabalho</span><span class="sxs-lookup"><span data-stu-id="1cae9-131">Use the value noted previously in the Job quantity field</span></span>
    * <span data-ttu-id="1cae9-132">Defina a Quantidade do trabalho para o valor anterior.</span><span class="sxs-lookup"><span data-stu-id="1cae9-132">Set the Job quantity to the previous value.</span></span>  

## <a name="start-the-second-transfer-job"></a><span data-ttu-id="1cae9-133">Inicie o segundo trabalho de transferência</span><span class="sxs-lookup"><span data-stu-id="1cae9-133">Start the second transfer job</span></span>
1. <span data-ttu-id="1cae9-134">Clique em Iniciar.</span><span class="sxs-lookup"><span data-stu-id="1cae9-134">Click Start.</span></span>
    * <span data-ttu-id="1cae9-135">Isso iniciará a transferência do trabalho da linha 5.</span><span class="sxs-lookup"><span data-stu-id="1cae9-135">This will start the transfer of the job in row 5.</span></span>  

## <a name="complete-both-transfer-jobs"></a><span data-ttu-id="1cae9-136">Conclua ambos os trabalhos de transferência</span><span class="sxs-lookup"><span data-stu-id="1cae9-136">Complete both transfer jobs</span></span>
1. <span data-ttu-id="1cae9-137">Na lista, selecione a linha 4.</span><span class="sxs-lookup"><span data-stu-id="1cae9-137">In the list, select row 4.</span></span>
    * <span data-ttu-id="1cae9-138">Agora dois trabalhos de transferência são selecionados na linha 4 e na linha 5.</span><span class="sxs-lookup"><span data-stu-id="1cae9-138">Now two transfer jobs are selected on row 4 and row 5.</span></span>  
2. <span data-ttu-id="1cae9-139">Clique em Concluir.</span><span class="sxs-lookup"><span data-stu-id="1cae9-139">Click Complete.</span></span>
    * <span data-ttu-id="1cae9-140">Isso irá concluir a transferência de ambos os trabalhos.</span><span class="sxs-lookup"><span data-stu-id="1cae9-140">This will complete the transfer of both jobs.</span></span>  


