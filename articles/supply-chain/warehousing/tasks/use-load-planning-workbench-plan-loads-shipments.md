--- 
title: Planejar cargas e remessas usando a Bancada de planejamento de carga
description: Este procedimento mostra como usar a bancada de planejamento de carga para criar uma carga para uma ordem de venda.
author: BibiSp
manager: AnnBe
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: bis
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: e948861920897cae7570984f97e3ff3893924a28
ms.contentlocale: pt-br
ms.lasthandoff: 04/13/2018

---
# <a name="plan-loads-and-shipments-using-the-load-planning-workbench"></a><span data-ttu-id="b4ec5-103">Planejar cargas e remessas usando a Bancada de planejamento de carga</span><span class="sxs-lookup"><span data-stu-id="b4ec5-103">Plan loads and shipments using the Load planning workbench</span></span>

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="b4ec5-104">Este procedimento mostra como usar a bancada de planejamento de carga para criar uma carga para uma ordem de venda.</span><span class="sxs-lookup"><span data-stu-id="b4ec5-104">This procedure shows how to use the load planning workbench to create a load for a sales order.</span></span> <span data-ttu-id="b4ec5-105">Como um pré-requisito iremos criar a ordem de venda primeiro.</span><span class="sxs-lookup"><span data-stu-id="b4ec5-105">As a prerequisite we'll create the sales order first.</span></span> <span data-ttu-id="b4ec5-106">Este procedimento é parte do trabalho diário do coordenador de transporte.</span><span class="sxs-lookup"><span data-stu-id="b4ec5-106">This procedure is part of the daily work for the transportation coordinator.</span></span> <span data-ttu-id="b4ec5-107">A empresa de dados demo usada para criar este procedimento é USMF.</span><span class="sxs-lookup"><span data-stu-id="b4ec5-107">The demo data company used to create this procedure is USMF.</span></span>


## <a name="create-a-sales-order"></a><span data-ttu-id="b4ec5-108">Criar uma ordem de venda</span><span class="sxs-lookup"><span data-stu-id="b4ec5-108">Create a sales order</span></span>
1. <span data-ttu-id="b4ec5-109">Vá para Contas a receber > Ordens > Todas as ordens de venda.</span><span class="sxs-lookup"><span data-stu-id="b4ec5-109">Go to Accounts receivable > Orders > All sales orders.</span></span>
2. <span data-ttu-id="b4ec5-110">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="b4ec5-110">Click New.</span></span>
3. <span data-ttu-id="b4ec5-111">No campo Conta do cliente, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="b4ec5-111">In the Customer account field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="b4ec5-112">Selecione a conta US-004.</span><span class="sxs-lookup"><span data-stu-id="b4ec5-112">Select account US-004.</span></span>
5. <span data-ttu-id="b4ec5-113">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="b4ec5-113">Click OK.</span></span>
6. <span data-ttu-id="b4ec5-114">No campo Número de item, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="b4ec5-114">In the Item number field, click the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="b4ec5-115">Selecione o item A0001.</span><span class="sxs-lookup"><span data-stu-id="b4ec5-115">Select item A0001.</span></span>
    * <span data-ttu-id="b4ec5-116">A0001 está habilitado para o gerenciamento de transporte.</span><span class="sxs-lookup"><span data-stu-id="b4ec5-116">A0001 is enabled for transportation management.</span></span>  
8. <span data-ttu-id="b4ec5-117">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="b4ec5-117">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="b4ec5-118">No campo Quantidade, insira um número.</span><span class="sxs-lookup"><span data-stu-id="b4ec5-118">In the Quantity field, enter a number.</span></span>
10. <span data-ttu-id="b4ec5-119">No campo Depósito, digite '24'.</span><span class="sxs-lookup"><span data-stu-id="b4ec5-119">In the Warehouse field, type '24'.</span></span>
    * <span data-ttu-id="b4ec5-120">Neste exemplo selecione o depósito 24.</span><span class="sxs-lookup"><span data-stu-id="b4ec5-120">In this example select warehouse 24.</span></span> <span data-ttu-id="b4ec5-121">Este depósito está habilitado para o gerenciamento de transporte e para o gerenciamento de depósito avançado.</span><span class="sxs-lookup"><span data-stu-id="b4ec5-121">This warehouse is enabled for transportation management and advanced warehouse management.</span></span>  
11. <span data-ttu-id="b4ec5-122">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="b4ec5-122">Click Save.</span></span>
12. <span data-ttu-id="b4ec5-123">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="b4ec5-123">Close the page.</span></span>

## <a name="create-a-new-load"></a><span data-ttu-id="b4ec5-124">Criar uma nova carga</span><span class="sxs-lookup"><span data-stu-id="b4ec5-124">Create a new load</span></span>
1. <span data-ttu-id="b4ec5-125">Vá para Gerenciamento de transporte > Planejamento > Bancada de planejamento de carga.</span><span class="sxs-lookup"><span data-stu-id="b4ec5-125">Go to Transportation management > Planning > Load planning workbench.</span></span>
2. <span data-ttu-id="b4ec5-126">Clique na aba Linhas de Vendas.</span><span class="sxs-lookup"><span data-stu-id="b4ec5-126">Click the Sales lines tab.</span></span>
    * <span data-ttu-id="b4ec5-127">Agora você irá montar a carga para a ordem de venda que você acabou de criar.</span><span class="sxs-lookup"><span data-stu-id="b4ec5-127">Now you'll build the load for the sales order that you just created.</span></span> <span data-ttu-id="b4ec5-128">Cargas podem ser montadas de acordo com a oferta e procura das ordens de compra, ordens de transferência, e ordens de venda.</span><span class="sxs-lookup"><span data-stu-id="b4ec5-128">Loads can be built based on supply and demand from purchase orders, transfer orders, and sales orders.</span></span>  
3. <span data-ttu-id="b4ec5-129">No Painel de Ação, clique em Oferta e demanda.</span><span class="sxs-lookup"><span data-stu-id="b4ec5-129">On the Action Pane, click Supply and demand.</span></span>
4. <span data-ttu-id="b4ec5-130">Clique em Para nova carga.</span><span class="sxs-lookup"><span data-stu-id="b4ec5-130">Click To new load.</span></span>
5. <span data-ttu-id="b4ec5-131">No campo ID do modelo de carga, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="b4ec5-131">In the Load template ID field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="b4ec5-132">O modelo de carga define as medidas máximas para peso e volume da carga total.</span><span class="sxs-lookup"><span data-stu-id="b4ec5-132">The Load template defines maximum measurements for weight and volume of the entire load.</span></span> <span data-ttu-id="b4ec5-133">Por exemplo, o modelo de carga pode representar o tamanho de um contêiner ou caminhão.</span><span class="sxs-lookup"><span data-stu-id="b4ec5-133">For example, the load template might represent the size of a container or truck.</span></span>  
6. <span data-ttu-id="b4ec5-134">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="b4ec5-134">In the list, click the link in the selected row.</span></span>
7. <span data-ttu-id="b4ec5-135">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="b4ec5-135">Click OK.</span></span>

## <a name="rate-and-route-the-load"></a><span data-ttu-id="b4ec5-136">Avaliar e encaminhar a carga</span><span class="sxs-lookup"><span data-stu-id="b4ec5-136">Rate and route the load</span></span>
1. <span data-ttu-id="b4ec5-137">Clique em Classificação e roteiro.</span><span class="sxs-lookup"><span data-stu-id="b4ec5-137">Click Rating and routing.</span></span>
2. <span data-ttu-id="b4ec5-138">Clique em Bancada do roteiro de taxa.</span><span class="sxs-lookup"><span data-stu-id="b4ec5-138">Click Rate route workbench.</span></span>
3. <span data-ttu-id="b4ec5-139">Clique em Loja de taxas.</span><span class="sxs-lookup"><span data-stu-id="b4ec5-139">Click Rate shop.</span></span>
4. <span data-ttu-id="b4ec5-140">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="b4ec5-140">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="b4ec5-141">Clique em Atribuir.</span><span class="sxs-lookup"><span data-stu-id="b4ec5-141">Click Assign.</span></span>
6. <span data-ttu-id="b4ec5-142">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="b4ec5-142">Close the page.</span></span>
7. <span data-ttu-id="b4ec5-143">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="b4ec5-143">Close the page.</span></span>


