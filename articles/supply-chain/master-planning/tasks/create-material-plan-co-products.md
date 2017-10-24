--- 
title: Criar um plano de materiais para coprodutos
description: "O planejador de produção planeja os requisitos de materiais para itens que são coprodutos de fórmula."
author: YuyuScheller
manager: AnnBe
ms.date: 11/14/2016
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
ms.openlocfilehash: c8805ca02525ae001fbd5e10ad9405fe60c7473e
ms.contentlocale: pt-br
ms.lasthandoff: 09/29/2017

---
# <a name="create-a-material-plan-for-co-products"></a><span data-ttu-id="4aab6-103">Criar um plano de materiais para coprodutos</span><span class="sxs-lookup"><span data-stu-id="4aab6-103">Create a material plan for co-products</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="4aab6-104">O planejador de produção planeja os requisitos de materiais para itens que são coprodutos de fórmula.</span><span class="sxs-lookup"><span data-stu-id="4aab6-104">The production planner plans the material requirements for items that are formula co-products.</span></span> <span data-ttu-id="4aab6-105">A empresa de dados demonstrativos utilizada para criar esse procedimento é a USP2.</span><span class="sxs-lookup"><span data-stu-id="4aab6-105">The demo data company used to create this procedure is USP2.</span></span>


## <a name="create-requirement-for-a-co-product"></a><span data-ttu-id="4aab6-106">Criar requisito para um coproduto</span><span class="sxs-lookup"><span data-stu-id="4aab6-106">Create requirement for a co-product</span></span>
1. <span data-ttu-id="4aab6-107">Ir para o painel Padrão.</span><span class="sxs-lookup"><span data-stu-id="4aab6-107">Go to Default dashboard.</span></span>
2. <span data-ttu-id="4aab6-108">Clique em Consulta e processamento de ordem de venda.</span><span class="sxs-lookup"><span data-stu-id="4aab6-108">Click Sales order processing and inquiry.</span></span>
3. <span data-ttu-id="4aab6-109">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="4aab6-109">Click New.</span></span>
4. <span data-ttu-id="4aab6-110">Clique Ordem de venda.</span><span class="sxs-lookup"><span data-stu-id="4aab6-110">Click Sales order.</span></span>
5. <span data-ttu-id="4aab6-111">No campo Conta de cliente, insira um valor.</span><span class="sxs-lookup"><span data-stu-id="4aab6-111">In the Customer account field, type a value.</span></span>
    * <span data-ttu-id="4aab6-112">Exemplo: US-001</span><span class="sxs-lookup"><span data-stu-id="4aab6-112">Example: US-001</span></span>  
6. <span data-ttu-id="4aab6-113">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="4aab6-113">Click OK.</span></span>
7. <span data-ttu-id="4aab6-114">No campo Número de item, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="4aab6-114">In the Item number field, type a value.</span></span>
    * <span data-ttu-id="4aab6-115">Exemplo: P6003</span><span class="sxs-lookup"><span data-stu-id="4aab6-115">Example: P6003</span></span>  
8. <span data-ttu-id="4aab6-116">No campo Quantidade, insira um número.</span><span class="sxs-lookup"><span data-stu-id="4aab6-116">In the Quantity field, enter a number.</span></span>
    * <span data-ttu-id="4aab6-117">Exemplo: 50000</span><span class="sxs-lookup"><span data-stu-id="4aab6-117">Example: 50000</span></span>  
9. <span data-ttu-id="4aab6-118">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="4aab6-118">Click Save.</span></span>

## <a name="create-a-material-plan-for-co-products"></a><span data-ttu-id="4aab6-119">Criar um plano de materiais para coprodutos</span><span class="sxs-lookup"><span data-stu-id="4aab6-119">Create a material plan for co-products</span></span>
1. <span data-ttu-id="4aab6-120">Clique em Planejamento mestre.</span><span class="sxs-lookup"><span data-stu-id="4aab6-120">Click Master planning.</span></span>
2. <span data-ttu-id="4aab6-121">No campo Plano, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="4aab6-121">In the Plan field, click the drop-down button to open the lookup.</span></span>
3. <span data-ttu-id="4aab6-122">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="4aab6-122">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="4aab6-123">Exemplo: Plano Mestre</span><span class="sxs-lookup"><span data-stu-id="4aab6-123">Example: MasterPlan</span></span>  
4. <span data-ttu-id="4aab6-124">Clique em Executar.</span><span class="sxs-lookup"><span data-stu-id="4aab6-124">Click Run.</span></span>
5. <span data-ttu-id="4aab6-125">Expanda ou recolha a seção de Registros a serem incluídos.</span><span class="sxs-lookup"><span data-stu-id="4aab6-125">Expand or collapse the Records to include section.</span></span>
6. <span data-ttu-id="4aab6-126">Clique em Filtro.</span><span class="sxs-lookup"><span data-stu-id="4aab6-126">Click Filter.</span></span>
7. <span data-ttu-id="4aab6-127">Na lista, selecione a linha para Campo = Número do item.</span><span class="sxs-lookup"><span data-stu-id="4aab6-127">In the list, select the row for Field = Item number.</span></span>
8. <span data-ttu-id="4aab6-128">No campo Critérios, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="4aab6-128">In the Criteria field, type a value.</span></span>
    * <span data-ttu-id="4aab6-129">Exemplo: P6003</span><span class="sxs-lookup"><span data-stu-id="4aab6-129">Example: P6003</span></span>  
9. <span data-ttu-id="4aab6-130">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="4aab6-130">Click OK.</span></span>
10. <span data-ttu-id="4aab6-131">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="4aab6-131">Click OK.</span></span>
11. <span data-ttu-id="4aab6-132">Clique em Ordens planejadas.</span><span class="sxs-lookup"><span data-stu-id="4aab6-132">Click Planned orders.</span></span>
12. <span data-ttu-id="4aab6-133">Use o Filtro Rápido para localizar registros.</span><span class="sxs-lookup"><span data-stu-id="4aab6-133">Use the Quick Filter to find records.</span></span> <span data-ttu-id="4aab6-134">Por exemplo, filtre o campo Número do item com um valor de 'P6000'.</span><span class="sxs-lookup"><span data-stu-id="4aab6-134">For example, filter on the Item number field with a value of 'P6000'.</span></span>
    * <span data-ttu-id="4aab6-135">Filtre pelo item de fórmula que contenha uma ordem de venda como coproduto do item que você criou.</span><span class="sxs-lookup"><span data-stu-id="4aab6-135">Filter by the formula item that has as co-product of the item that you created a sales order for.</span></span>  
13. <span data-ttu-id="4aab6-136">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="4aab6-136">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="4aab6-137">Selecione uma das linhas retornadas pelo filtro.</span><span class="sxs-lookup"><span data-stu-id="4aab6-137">Select any of the rows returned by the filter.</span></span>  
14. <span data-ttu-id="4aab6-138">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="4aab6-138">In the list, click the link in the selected row.</span></span>
15. <span data-ttu-id="4aab6-139">Expandir ou recolher a seção Vinculação.</span><span class="sxs-lookup"><span data-stu-id="4aab6-139">Expand or collapse the Pegging section.</span></span>
16. <span data-ttu-id="4aab6-140">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="4aab6-140">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="4aab6-141">A ordem planejada está vinculada a ordem de venda para o coproduto.</span><span class="sxs-lookup"><span data-stu-id="4aab6-141">The planned order is pegged to the sales order for the co-product.</span></span>  
17. <span data-ttu-id="4aab6-142">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="4aab6-142">Close the page.</span></span>


