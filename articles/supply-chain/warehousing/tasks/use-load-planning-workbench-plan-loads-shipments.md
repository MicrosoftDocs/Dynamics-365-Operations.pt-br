---
title: Planejar cargas e remessas usando a Bancada de planejamento de carga
description: Este procedimento mostra como usar a bancada de planejamento de carga para criar uma carga para uma ordem de venda.
author: ShylaThompson
manager: AnnBe
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1927cff48beb30f934bd066c32ab48dfb9d06f74
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2019
ms.locfileid: "343894"
---
# <a name="plan-loads-and-shipments-using-the-load-planning-workbench"></a><span data-ttu-id="467e7-103">Planejar cargas e remessas usando a Bancada de planejamento de carga</span><span class="sxs-lookup"><span data-stu-id="467e7-103">Plan loads and shipments using the Load planning workbench</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="467e7-104">Este procedimento mostra como usar a bancada de planejamento de carga para criar uma carga para uma ordem de venda.</span><span class="sxs-lookup"><span data-stu-id="467e7-104">This procedure shows how to use the load planning workbench to create a load for a sales order.</span></span> <span data-ttu-id="467e7-105">Como um pré-requisito iremos criar a ordem de venda primeiro.</span><span class="sxs-lookup"><span data-stu-id="467e7-105">As a prerequisite we'll create the sales order first.</span></span> <span data-ttu-id="467e7-106">Este procedimento é parte do trabalho diário do coordenador de transporte.</span><span class="sxs-lookup"><span data-stu-id="467e7-106">This procedure is part of the daily work for the transportation coordinator.</span></span> <span data-ttu-id="467e7-107">A empresa de dados demo usada para criar este procedimento é USMF.</span><span class="sxs-lookup"><span data-stu-id="467e7-107">The demo data company used to create this procedure is USMF.</span></span>


## <a name="create-a-sales-order"></a><span data-ttu-id="467e7-108">Criar uma ordem de venda</span><span class="sxs-lookup"><span data-stu-id="467e7-108">Create a sales order</span></span>
1. <span data-ttu-id="467e7-109">Vá para Contas a receber > Ordens > Todas as ordens de venda.</span><span class="sxs-lookup"><span data-stu-id="467e7-109">Go to Accounts receivable > Orders > All sales orders.</span></span>
2. <span data-ttu-id="467e7-110">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="467e7-110">Click New.</span></span>
3. <span data-ttu-id="467e7-111">No campo Conta do cliente, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="467e7-111">In the Customer account field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="467e7-112">Selecione a conta US-004.</span><span class="sxs-lookup"><span data-stu-id="467e7-112">Select account US-004.</span></span>
5. <span data-ttu-id="467e7-113">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="467e7-113">Click OK.</span></span>
6. <span data-ttu-id="467e7-114">No campo Número de item, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="467e7-114">In the Item number field, click the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="467e7-115">Selecione o item A0001.</span><span class="sxs-lookup"><span data-stu-id="467e7-115">Select item A0001.</span></span>
    * <span data-ttu-id="467e7-116">A0001 está habilitado para o gerenciamento de transporte.</span><span class="sxs-lookup"><span data-stu-id="467e7-116">A0001 is enabled for transportation management.</span></span>  
8. <span data-ttu-id="467e7-117">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="467e7-117">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="467e7-118">No campo Quantidade, insira um número.</span><span class="sxs-lookup"><span data-stu-id="467e7-118">In the Quantity field, enter a number.</span></span>
10. <span data-ttu-id="467e7-119">No campo Depósito, digite '24'.</span><span class="sxs-lookup"><span data-stu-id="467e7-119">In the Warehouse field, type '24'.</span></span>
    * <span data-ttu-id="467e7-120">Neste exemplo selecione o depósito 24.</span><span class="sxs-lookup"><span data-stu-id="467e7-120">In this example select warehouse 24.</span></span> <span data-ttu-id="467e7-121">Este depósito está habilitado para o gerenciamento de transporte e para o gerenciamento de depósito avançado.</span><span class="sxs-lookup"><span data-stu-id="467e7-121">This warehouse is enabled for transportation management and advanced warehouse management.</span></span>  
11. <span data-ttu-id="467e7-122">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="467e7-122">Click Save.</span></span>
12. <span data-ttu-id="467e7-123">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="467e7-123">Close the page.</span></span>

## <a name="create-a-new-load"></a><span data-ttu-id="467e7-124">Criar uma nova carga</span><span class="sxs-lookup"><span data-stu-id="467e7-124">Create a new load</span></span>
1. <span data-ttu-id="467e7-125">Vá para Gerenciamento de transporte > Planejamento > Bancada de planejamento de carga.</span><span class="sxs-lookup"><span data-stu-id="467e7-125">Go to Transportation management > Planning > Load planning workbench.</span></span>
2. <span data-ttu-id="467e7-126">Clique na aba Linhas de Vendas.</span><span class="sxs-lookup"><span data-stu-id="467e7-126">Click the Sales lines tab.</span></span>
    * <span data-ttu-id="467e7-127">Agora você irá montar a carga para a ordem de venda que você acabou de criar.</span><span class="sxs-lookup"><span data-stu-id="467e7-127">Now you'll build the load for the sales order that you just created.</span></span> <span data-ttu-id="467e7-128">Cargas podem ser montadas de acordo com a oferta e procura das ordens de compra, ordens de transferência, e ordens de venda.</span><span class="sxs-lookup"><span data-stu-id="467e7-128">Loads can be built based on supply and demand from purchase orders, transfer orders, and sales orders.</span></span>  
3. <span data-ttu-id="467e7-129">No Painel de Ação, clique em Oferta e demanda.</span><span class="sxs-lookup"><span data-stu-id="467e7-129">On the Action Pane, click Supply and demand.</span></span>
4. <span data-ttu-id="467e7-130">Clique em Para nova carga.</span><span class="sxs-lookup"><span data-stu-id="467e7-130">Click To new load.</span></span>
5. <span data-ttu-id="467e7-131">No campo ID do modelo de carga, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="467e7-131">In the Load template ID field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="467e7-132">O modelo de carga define as medidas máximas para peso e volume da carga total.</span><span class="sxs-lookup"><span data-stu-id="467e7-132">The Load template defines maximum measurements for weight and volume of the entire load.</span></span> <span data-ttu-id="467e7-133">Por exemplo, o modelo de carga pode representar o tamanho de um contêiner ou caminhão.</span><span class="sxs-lookup"><span data-stu-id="467e7-133">For example, the load template might represent the size of a container or truck.</span></span>  
6. <span data-ttu-id="467e7-134">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="467e7-134">In the list, click the link in the selected row.</span></span>
7. <span data-ttu-id="467e7-135">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="467e7-135">Click OK.</span></span>

## <a name="rate-and-route-the-load"></a><span data-ttu-id="467e7-136">Avaliar e encaminhar a carga</span><span class="sxs-lookup"><span data-stu-id="467e7-136">Rate and route the load</span></span>
1. <span data-ttu-id="467e7-137">Clique em Classificação e roteiro.</span><span class="sxs-lookup"><span data-stu-id="467e7-137">Click Rating and routing.</span></span>
2. <span data-ttu-id="467e7-138">Clique em Bancada do roteiro de taxa.</span><span class="sxs-lookup"><span data-stu-id="467e7-138">Click Rate route workbench.</span></span>
3. <span data-ttu-id="467e7-139">Clique em Loja de taxas.</span><span class="sxs-lookup"><span data-stu-id="467e7-139">Click Rate shop.</span></span>
4. <span data-ttu-id="467e7-140">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="467e7-140">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="467e7-141">Clique em Atribuir.</span><span class="sxs-lookup"><span data-stu-id="467e7-141">Click Assign.</span></span>
6. <span data-ttu-id="467e7-142">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="467e7-142">Close the page.</span></span>
7. <span data-ttu-id="467e7-143">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="467e7-143">Close the page.</span></span>

