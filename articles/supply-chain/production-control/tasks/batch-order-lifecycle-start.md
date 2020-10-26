---
title: Ciclo de vida da ordem de lotes da criação ao início
description: Este procedimento o conduz através da primeira parte do ciclo de vida da ordem de lote.
author: ShylaThompson
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProdTableListPage, ProdTableCreate, ProdBOM, PmfProdCoBy, ProdParmCostEstimation, ProdCalcTrans, ProdParmRelease, ProdSchedule, ProdRouteJob, ProdParmStartUp, ProdJournalTransBOM, ProdJournalTransRoute
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e57cd9254185b73f544e8ff4f7658cf743b672f2
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/10/2020
ms.locfileid: "3981295"
---
# <a name="batch-order-lifecycle-from-create-to-start"></a><span data-ttu-id="8458b-103">Ciclo de vida da ordem de lotes da criação ao início</span><span class="sxs-lookup"><span data-stu-id="8458b-103">Batch order lifecycle from create to start</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="8458b-104">Este procedimento o conduz através da primeira parte do ciclo de vida da ordem de lote.</span><span class="sxs-lookup"><span data-stu-id="8458b-104">This procedure takes you through the first part of the life cycle of a batch order.</span></span>

<span data-ttu-id="8458b-105">A partir da criação, da estimativa de custo e em um agendamento de trabalho de produção até o início real de uma ordem de lote.</span><span class="sxs-lookup"><span data-stu-id="8458b-105">From creation, cost estimation, and over production job scheduling to the actual start of a batch order.</span></span>



<span data-ttu-id="8458b-106">A empresa de dados demo usada para criar este procedimento é USMF.</span><span class="sxs-lookup"><span data-stu-id="8458b-106">The demo data company used to create this procedure is USMF.</span></span> 



<span data-ttu-id="8458b-107">Os pré-requisitos para executar o procedimento com outro conjunto de dados são um produto liberado com uma fórmula ativa e a versão de roteiro.</span><span class="sxs-lookup"><span data-stu-id="8458b-107">The prerequisites for running the procedure with another dataset are a released product with an active formula and route version.</span></span>


## <a name="create-a-batch-order"></a><span data-ttu-id="8458b-108">Criar uma ordem de lotes</span><span class="sxs-lookup"><span data-stu-id="8458b-108">Create a batch order</span></span>
1. <span data-ttu-id="8458b-109">Vá para Todas as ordens de produção.</span><span class="sxs-lookup"><span data-stu-id="8458b-109">Go to All production orders.</span></span>
2. <span data-ttu-id="8458b-110">Clique em Nova ordem de lote.</span><span class="sxs-lookup"><span data-stu-id="8458b-110">Click New batch order.</span></span>
3. <span data-ttu-id="8458b-111">No campo Número do item, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="8458b-111">In the Item number field, enter or select a value.</span></span>
4. <span data-ttu-id="8458b-112">Clique em Criar.</span><span class="sxs-lookup"><span data-stu-id="8458b-112">Click Create.</span></span>
5. <span data-ttu-id="8458b-113">Use o Filtro Rápido para filtrar o campo Produção com o valor 'b'.</span><span class="sxs-lookup"><span data-stu-id="8458b-113">Use the Quick Filter to filter on the Production field with a value of 'b'.</span></span>

## <a name="view-production-formula-and-expected-co-products"></a><span data-ttu-id="8458b-114">Exiba a fórmula de produção e os coprodutos previstos</span><span class="sxs-lookup"><span data-stu-id="8458b-114">View production formula and expected co-products</span></span>
1. <span data-ttu-id="8458b-115">No Painel de Ação, clique em Ordem de produção.</span><span class="sxs-lookup"><span data-stu-id="8458b-115">On the Action Pane, click Production order.</span></span>
2. <span data-ttu-id="8458b-116">Clique em Fórmula.</span><span class="sxs-lookup"><span data-stu-id="8458b-116">Click Formula.</span></span>
3. <span data-ttu-id="8458b-117">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="8458b-117">Close the page.</span></span>
4. <span data-ttu-id="8458b-118">Clique em Co-produtos.</span><span class="sxs-lookup"><span data-stu-id="8458b-118">Click Co-products.</span></span>
5. <span data-ttu-id="8458b-119">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="8458b-119">Close the page.</span></span>

## <a name="estimate-the-batch-order"></a><span data-ttu-id="8458b-120">Estime a ordem de lote</span><span class="sxs-lookup"><span data-stu-id="8458b-120">Estimate the batch order</span></span>
1. <span data-ttu-id="8458b-121">Clique em Estimar.</span><span class="sxs-lookup"><span data-stu-id="8458b-121">Click Estimate.</span></span>
2. <span data-ttu-id="8458b-122">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="8458b-122">Click OK.</span></span>
3. <span data-ttu-id="8458b-123">No Painel de Ação, clique em Gerenciar custos.</span><span class="sxs-lookup"><span data-stu-id="8458b-123">On the Action Pane, click Manage costs.</span></span>
4. <span data-ttu-id="8458b-124">Clique em Exibir detalhes do cálculo.</span><span class="sxs-lookup"><span data-stu-id="8458b-124">Click View calculation details.</span></span>
5. <span data-ttu-id="8458b-125">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="8458b-125">Close the page.</span></span>

## <a name="release-the-batch-order"></a><span data-ttu-id="8458b-126">Libere a ordem de lote</span><span class="sxs-lookup"><span data-stu-id="8458b-126">Release the batch order</span></span>
1. <span data-ttu-id="8458b-127">No Painel de Ação, clique em Ordem de produção.</span><span class="sxs-lookup"><span data-stu-id="8458b-127">On the Action Pane, click Production order.</span></span>
2. <span data-ttu-id="8458b-128">Clique em Liberar.</span><span class="sxs-lookup"><span data-stu-id="8458b-128">Click Release.</span></span>
3. <span data-ttu-id="8458b-129">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="8458b-129">Click OK.</span></span>

## <a name="schedule-production-jobs"></a><span data-ttu-id="8458b-130">Agende os trabalhos de produção</span><span class="sxs-lookup"><span data-stu-id="8458b-130">Schedule production jobs</span></span>
1. <span data-ttu-id="8458b-131">No Painel de Ação, clique em Agenda.</span><span class="sxs-lookup"><span data-stu-id="8458b-131">On the Action Pane, click Schedule.</span></span>
2. <span data-ttu-id="8458b-132">Clique em Agendar trabalhos.</span><span class="sxs-lookup"><span data-stu-id="8458b-132">Click Schedule jobs.</span></span>
3. <span data-ttu-id="8458b-133">Selecione Não no campo Capacidade finita.</span><span class="sxs-lookup"><span data-stu-id="8458b-133">Select No in the Finite capacity field.</span></span>
4. <span data-ttu-id="8458b-134">Selecione Não no campo Material finito.</span><span class="sxs-lookup"><span data-stu-id="8458b-134">Select No in the Finite material field.</span></span>
5. <span data-ttu-id="8458b-135">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="8458b-135">Click OK.</span></span>
6. <span data-ttu-id="8458b-136">No Painel de Ação, clique em Ordem de produção.</span><span class="sxs-lookup"><span data-stu-id="8458b-136">On the Action Pane, click Production order.</span></span>
7. <span data-ttu-id="8458b-137">Clique em Todos os trabalhos.</span><span class="sxs-lookup"><span data-stu-id="8458b-137">Click All jobs.</span></span>
8. <span data-ttu-id="8458b-138">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="8458b-138">Close the page.</span></span>

## <a name="start-the-batch-order"></a><span data-ttu-id="8458b-139">Inicie a ordem de lote</span><span class="sxs-lookup"><span data-stu-id="8458b-139">Start the batch order</span></span>
1. <span data-ttu-id="8458b-140">Clique em Iniciar.</span><span class="sxs-lookup"><span data-stu-id="8458b-140">Click Start.</span></span>
2. <span data-ttu-id="8458b-141">Clique na guia Geral.</span><span class="sxs-lookup"><span data-stu-id="8458b-141">Click the General tab.</span></span>
3. <span data-ttu-id="8458b-142">Selecione Não no campo Lançar lista de separação agora.</span><span class="sxs-lookup"><span data-stu-id="8458b-142">Select No in the Post picking list now field.</span></span>
4. <span data-ttu-id="8458b-143">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="8458b-143">Click OK.</span></span>
5. <span data-ttu-id="8458b-144">No Painel de Ação, clique em Exibir.</span><span class="sxs-lookup"><span data-stu-id="8458b-144">On the Action Pane, click View.</span></span>
6. <span data-ttu-id="8458b-145">Clique em Lista de separação.</span><span class="sxs-lookup"><span data-stu-id="8458b-145">Click Picking list.</span></span>
7. <span data-ttu-id="8458b-146">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="8458b-146">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="8458b-147">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="8458b-147">Close the page.</span></span>
9. <span data-ttu-id="8458b-148">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="8458b-148">Close the page.</span></span>
10. <span data-ttu-id="8458b-149">Clique em Cartão de roteiro.</span><span class="sxs-lookup"><span data-stu-id="8458b-149">Click Route card.</span></span>
11. <span data-ttu-id="8458b-150">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="8458b-150">In the list, click the link in the selected row.</span></span>
12. <span data-ttu-id="8458b-151">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="8458b-151">Close the page.</span></span>
13. <span data-ttu-id="8458b-152">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="8458b-152">Close the page.</span></span>

