---
title: Ciclo de vida da ordem de lotes da criação ao início
description: Este procedimento o conduz através da primeira parte do ciclo de vida da ordem de lote.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProdTableListPage, ProdTableCreate, ProdBOM, PmfProdCoBy, ProdParmCostEstimation, ProdCalcTrans, ProdParmRelease, ProdSchedule, ProdRouteJob, ProdParmStartUp, ProdJournalTransBOM, ProdJournalTransRoute
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 7a1803822bebf58a3370afe8c5dc9f519c65917d
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/01/2019
ms.locfileid: "1843808"
---
# <a name="batch-order-lifecycle-from-create-to-start"></a><span data-ttu-id="2bb4e-103">Ciclo de vida da ordem de lotes da criação ao início</span><span class="sxs-lookup"><span data-stu-id="2bb4e-103">Batch order lifecycle from create to start</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="2bb4e-104">Este procedimento o conduz através da primeira parte do ciclo de vida da ordem de lote.</span><span class="sxs-lookup"><span data-stu-id="2bb4e-104">This procedure takes you through the first part of the life cycle of a batch order.</span></span>

<span data-ttu-id="2bb4e-105">A partir da criação, da estimativa de custo e em um agendamento de trabalho de produção até o início real de uma ordem de lote.</span><span class="sxs-lookup"><span data-stu-id="2bb4e-105">From creation, cost estimation, and over production job scheduling to the actual start of a batch order.</span></span>



<span data-ttu-id="2bb4e-106">A empresa de dados demo usada para criar este procedimento é USMF.</span><span class="sxs-lookup"><span data-stu-id="2bb4e-106">The demo data company used to create this procedure is USMF.</span></span> 



<span data-ttu-id="2bb4e-107">Os pré-requisitos para executar o procedimento com outro conjunto de dados são um produto liberado com uma fórmula ativa e a versão de roteiro.</span><span class="sxs-lookup"><span data-stu-id="2bb4e-107">The prerequisites for running the procedure with another dataset are a released product with an active formula and route version.</span></span>


## <a name="create-a-batch-order"></a><span data-ttu-id="2bb4e-108">Criar uma ordem de lotes</span><span class="sxs-lookup"><span data-stu-id="2bb4e-108">Create a batch order</span></span>
1. <span data-ttu-id="2bb4e-109">Vá para Todas as ordens de produção.</span><span class="sxs-lookup"><span data-stu-id="2bb4e-109">Go to All production orders.</span></span>
2. <span data-ttu-id="2bb4e-110">Clique em Nova ordem de lote.</span><span class="sxs-lookup"><span data-stu-id="2bb4e-110">Click New batch order.</span></span>
3. <span data-ttu-id="2bb4e-111">No campo Número do item, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="2bb4e-111">In the Item number field, enter or select a value.</span></span>
4. <span data-ttu-id="2bb4e-112">Clique em Criar.</span><span class="sxs-lookup"><span data-stu-id="2bb4e-112">Click Create.</span></span>
5. <span data-ttu-id="2bb4e-113">Use o Filtro Rápido para filtrar o campo Produção com o valor 'b'.</span><span class="sxs-lookup"><span data-stu-id="2bb4e-113">Use the Quick Filter to filter on the Production field with a value of 'b'.</span></span>

## <a name="view-production-formula-and-expected-co-products"></a><span data-ttu-id="2bb4e-114">Exiba a fórmula de produção e os coprodutos previstos</span><span class="sxs-lookup"><span data-stu-id="2bb4e-114">View production formula and expected co-products</span></span>
1. <span data-ttu-id="2bb4e-115">No Painel de Ação, clique em Ordem de produção.</span><span class="sxs-lookup"><span data-stu-id="2bb4e-115">On the Action Pane, click Production order.</span></span>
2. <span data-ttu-id="2bb4e-116">Clique em Fórmula.</span><span class="sxs-lookup"><span data-stu-id="2bb4e-116">Click Formula.</span></span>
3. <span data-ttu-id="2bb4e-117">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="2bb4e-117">Close the page.</span></span>
4. <span data-ttu-id="2bb4e-118">Clique em Co-produtos.</span><span class="sxs-lookup"><span data-stu-id="2bb4e-118">Click Co-products.</span></span>
5. <span data-ttu-id="2bb4e-119">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="2bb4e-119">Close the page.</span></span>

## <a name="estimate-the-batch-order"></a><span data-ttu-id="2bb4e-120">Estime a ordem de lote</span><span class="sxs-lookup"><span data-stu-id="2bb4e-120">Estimate the batch order</span></span>
1. <span data-ttu-id="2bb4e-121">Clique em Estimar.</span><span class="sxs-lookup"><span data-stu-id="2bb4e-121">Click Estimate.</span></span>
2. <span data-ttu-id="2bb4e-122">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="2bb4e-122">Click OK.</span></span>
3. <span data-ttu-id="2bb4e-123">No Painel de Ação, clique em Gerenciar custos.</span><span class="sxs-lookup"><span data-stu-id="2bb4e-123">On the Action Pane, click Manage costs.</span></span>
4. <span data-ttu-id="2bb4e-124">Clique em Exibir detalhes do cálculo.</span><span class="sxs-lookup"><span data-stu-id="2bb4e-124">Click View calculation details.</span></span>
5. <span data-ttu-id="2bb4e-125">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="2bb4e-125">Close the page.</span></span>

## <a name="release-the-batch-order"></a><span data-ttu-id="2bb4e-126">Libere a ordem de lote</span><span class="sxs-lookup"><span data-stu-id="2bb4e-126">Release the batch order</span></span>
1. <span data-ttu-id="2bb4e-127">No Painel de Ação, clique em Ordem de produção.</span><span class="sxs-lookup"><span data-stu-id="2bb4e-127">On the Action Pane, click Production order.</span></span>
2. <span data-ttu-id="2bb4e-128">Clique em Liberar.</span><span class="sxs-lookup"><span data-stu-id="2bb4e-128">Click Release.</span></span>
3. <span data-ttu-id="2bb4e-129">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="2bb4e-129">Click OK.</span></span>

## <a name="schedule-production-jobs"></a><span data-ttu-id="2bb4e-130">Agende os trabalhos de produção</span><span class="sxs-lookup"><span data-stu-id="2bb4e-130">Schedule production jobs</span></span>
1. <span data-ttu-id="2bb4e-131">No Painel de Ação, clique em Agenda.</span><span class="sxs-lookup"><span data-stu-id="2bb4e-131">On the Action Pane, click Schedule.</span></span>
2. <span data-ttu-id="2bb4e-132">Clique em Agendar trabalhos.</span><span class="sxs-lookup"><span data-stu-id="2bb4e-132">Click Schedule jobs.</span></span>
3. <span data-ttu-id="2bb4e-133">Selecione Não no campo Capacidade finita.</span><span class="sxs-lookup"><span data-stu-id="2bb4e-133">Select No in the Finite capacity field.</span></span>
4. <span data-ttu-id="2bb4e-134">Selecione Não no campo Material finito.</span><span class="sxs-lookup"><span data-stu-id="2bb4e-134">Select No in the Finite material field.</span></span>
5. <span data-ttu-id="2bb4e-135">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="2bb4e-135">Click OK.</span></span>
6. <span data-ttu-id="2bb4e-136">No Painel de Ação, clique em Ordem de produção.</span><span class="sxs-lookup"><span data-stu-id="2bb4e-136">On the Action Pane, click Production order.</span></span>
7. <span data-ttu-id="2bb4e-137">Clique em Todos os trabalhos.</span><span class="sxs-lookup"><span data-stu-id="2bb4e-137">Click All jobs.</span></span>
8. <span data-ttu-id="2bb4e-138">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="2bb4e-138">Close the page.</span></span>

## <a name="start-the-batch-order"></a><span data-ttu-id="2bb4e-139">Inicie a ordem de lote</span><span class="sxs-lookup"><span data-stu-id="2bb4e-139">Start the batch order</span></span>
1. <span data-ttu-id="2bb4e-140">Clique em Iniciar.</span><span class="sxs-lookup"><span data-stu-id="2bb4e-140">Click Start.</span></span>
2. <span data-ttu-id="2bb4e-141">Clique na guia Geral.</span><span class="sxs-lookup"><span data-stu-id="2bb4e-141">Click the General tab.</span></span>
3. <span data-ttu-id="2bb4e-142">Selecione Não no campo Lançar lista de separação agora.</span><span class="sxs-lookup"><span data-stu-id="2bb4e-142">Select No in the Post picking list now field.</span></span>
4. <span data-ttu-id="2bb4e-143">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="2bb4e-143">Click OK.</span></span>
5. <span data-ttu-id="2bb4e-144">No Painel de Ação, clique em Exibir.</span><span class="sxs-lookup"><span data-stu-id="2bb4e-144">On the Action Pane, click View.</span></span>
6. <span data-ttu-id="2bb4e-145">Clique em Lista de separação.</span><span class="sxs-lookup"><span data-stu-id="2bb4e-145">Click Picking list.</span></span>
7. <span data-ttu-id="2bb4e-146">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="2bb4e-146">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="2bb4e-147">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="2bb4e-147">Close the page.</span></span>
9. <span data-ttu-id="2bb4e-148">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="2bb4e-148">Close the page.</span></span>
10. <span data-ttu-id="2bb4e-149">Clique em Cartão de roteiro.</span><span class="sxs-lookup"><span data-stu-id="2bb4e-149">Click Route card.</span></span>
11. <span data-ttu-id="2bb4e-150">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="2bb4e-150">In the list, click the link in the selected row.</span></span>
12. <span data-ttu-id="2bb4e-151">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="2bb4e-151">Close the page.</span></span>
13. <span data-ttu-id="2bb4e-152">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="2bb4e-152">Close the page.</span></span>

