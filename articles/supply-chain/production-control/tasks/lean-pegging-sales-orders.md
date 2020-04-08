---
title: Vinculação leve de ordens de venda
description: Esse procedimento se concentra em validar a árvore de vinculação de uma linha de venda na qual o item é gerado com kanbans.
author: ChristianRytt
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SalesTableListPage, SalesCreateOrder, SalesTable, LeanPeggingTree
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: a5142fe552147a9b2988a8828ba1206fad9e252e
ms.sourcegitcommit: fcb27d6a46cd544feef34f6ec7607bdd46b0c12b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/18/2020
ms.locfileid: "3146735"
---
# <a name="lean-pegging-from-sales-orders"></a><span data-ttu-id="0b757-103">Vinculação leve de ordens de venda</span><span class="sxs-lookup"><span data-stu-id="0b757-103">Lean pegging from sales orders</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="0b757-104">Esse procedimento se concentra em validar a árvore de vinculação de uma linha de venda na qual o item é gerado com kanbans.</span><span class="sxs-lookup"><span data-stu-id="0b757-104">This procedure focuses on validating the pegging tree from a sales line where the item is produced with kanbans.</span></span> <span data-ttu-id="0b757-105">Após validar a árvore de vinculação, todos os trabalhos kanban são planejados.</span><span class="sxs-lookup"><span data-stu-id="0b757-105">After validating the pegging tree, all the kanban jobs are planned.</span></span> <span data-ttu-id="0b757-106">Isso é útil para os cenários de ordem nos quais o tomador da ordem precisa garantir que possa iniciar a produção imediatamente.</span><span class="sxs-lookup"><span data-stu-id="0b757-106">This is useful for order scenarios where the order taker needs to ensure that production can start right away.</span></span> <span data-ttu-id="0b757-107">A empresa de dados demo usada para criar este procedimento é USMF.</span><span class="sxs-lookup"><span data-stu-id="0b757-107">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="0b757-108">Esse procedimento se destina ao tomador de ordem avançada que trabalha em uma empresa de lean manufacturing.</span><span class="sxs-lookup"><span data-stu-id="0b757-108">This procedure is intended for the advanced order taker working in a lean company.</span></span>


## <a name="create-a-sales-order-for-a-kanban-controlled-item"></a><span data-ttu-id="0b757-109">Crie uma ordem de venda para um item controlado por kanban</span><span class="sxs-lookup"><span data-stu-id="0b757-109">Create a sales order for a kanban controlled item</span></span>
1. <span data-ttu-id="0b757-110">Ir para Todas as ordens de venda.</span><span class="sxs-lookup"><span data-stu-id="0b757-110">Go to All sales orders.</span></span>
2. <span data-ttu-id="0b757-111">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="0b757-111">Click New.</span></span>
3. <span data-ttu-id="0b757-112">No campo Conta de cliente, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="0b757-112">In the Customer account field, enter or select a value.</span></span>
    * <span data-ttu-id="0b757-113">Usar US-001.</span><span class="sxs-lookup"><span data-stu-id="0b757-113">Use US-001.</span></span>  
4. <span data-ttu-id="0b757-114">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="0b757-114">Click OK.</span></span>
5. <span data-ttu-id="0b757-115">No campo Número do item, digite 'L0001'.</span><span class="sxs-lookup"><span data-stu-id="0b757-115">In the Item number field, type 'L0001'.</span></span>
6. <span data-ttu-id="0b757-116">Defina a quantidade como '30'.</span><span class="sxs-lookup"><span data-stu-id="0b757-116">Set Quantity to '30'.</span></span>
    * <span data-ttu-id="0b757-117">É importante que a quantidade seja maior do que 24 para disparar a regra kanban de evento.</span><span class="sxs-lookup"><span data-stu-id="0b757-117">It is important that the quantity is higher than 24 in order to trigger the event kanban rule.</span></span>  

## <a name="open-a-pegging-tree"></a><span data-ttu-id="0b757-118">Abra uma árvore de vinculação</span><span class="sxs-lookup"><span data-stu-id="0b757-118">Open a pegging tree</span></span> 
1. <span data-ttu-id="0b757-119">Clique em Produtos e fornecimento.</span><span class="sxs-lookup"><span data-stu-id="0b757-119">Click Product and supply.</span></span>
2. <span data-ttu-id="0b757-120">Clique em Exibir árvore de vinculação.</span><span class="sxs-lookup"><span data-stu-id="0b757-120">Click View pegging tree.</span></span>
    * <span data-ttu-id="0b757-121">Observe que a árvore de vinculação mostra todos os níveis de vinculação necessários para a linha da ordem de venda.</span><span class="sxs-lookup"><span data-stu-id="0b757-121">Notice that the pegging tree shows all levels of the pegging needed for the sales order line.</span></span> <span data-ttu-id="0b757-122">Nesse caso, há dois níveis de kanbans e todos os componentes necessários.</span><span class="sxs-lookup"><span data-stu-id="0b757-122">In this case, there are two levels of kanbans and all the required components.</span></span>  

## <a name="plan-the-pegging-tree"></a><span data-ttu-id="0b757-123">Planeje a árvore de vinculação</span><span class="sxs-lookup"><span data-stu-id="0b757-123">Plan the pegging tree</span></span>
1. <span data-ttu-id="0b757-124">Na árvore, selecione a linha de venda 000832\Kanban 000558'.</span><span class="sxs-lookup"><span data-stu-id="0b757-124">In the tree, select 'Sales line 000832\Kanban 000558'.</span></span>
2. <span data-ttu-id="0b757-125">Expanda a seção trabalhos Kanban.</span><span class="sxs-lookup"><span data-stu-id="0b757-125">Expand the Kanban jobs section.</span></span>
    * <span data-ttu-id="0b757-126">Observe que o status do trabalho para o trabalho kanban é Não planejado.</span><span class="sxs-lookup"><span data-stu-id="0b757-126">Notice that the job status for the kanban job is Not planned.</span></span>  
3. <span data-ttu-id="0b757-127">Clique em Planejar toda a árvore de vinculação.</span><span class="sxs-lookup"><span data-stu-id="0b757-127">Click Plan entire pegging tree.</span></span>
    * <span data-ttu-id="0b757-128">Isso planejará todos os trabalhos kanban na árvore de vinculação, alterando o status do trabalho de não planejado para planejado.</span><span class="sxs-lookup"><span data-stu-id="0b757-128">This will plan all kanban jobs in the pegging tree, changing the Job status from Not planned to Planned.</span></span>  
4. <span data-ttu-id="0b757-129">Atualize a página.</span><span class="sxs-lookup"><span data-stu-id="0b757-129">Refresh the page.</span></span>
    * <span data-ttu-id="0b757-130">Observe que o status do trabalho kanban foi alterado de Não planejado para Planejado.</span><span class="sxs-lookup"><span data-stu-id="0b757-130">Notice that the kanban Job status changed from Not planned to Planned.</span></span>  
5. <span data-ttu-id="0b757-131">Na árvore, selecione 'Linha de venda 000832\Kanban 000558\Saída para L0001\Kanban 000559'.</span><span class="sxs-lookup"><span data-stu-id="0b757-131">In the tree, select 'Sales line 000832\Kanban 000558\Issue for L0001\Kanban 000559'.</span></span>
    * <span data-ttu-id="0b757-132">O trabalho para o segundo kanban também é planejado porque a árvore inteira de vinculação é planejada.</span><span class="sxs-lookup"><span data-stu-id="0b757-132">The job for the second kanban is also planned, because the entire pegging tree is planned.</span></span> <span data-ttu-id="0b757-133">Observe que o status do trabalho kanban é alterado de Não planejado para Planejado.</span><span class="sxs-lookup"><span data-stu-id="0b757-133">Notice that the kanban job status is changed from Not planned to Planned.</span></span>  

