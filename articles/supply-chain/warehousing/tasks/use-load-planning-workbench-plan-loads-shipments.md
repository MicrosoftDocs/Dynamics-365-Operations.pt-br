---
title: Planejar cargas e remessas usando a Bancada de planejamento de carga
description: Este tópico mostra como usar a bancada de planejamento de carga para criar uma carga para uma ordem de venda.
author: ShylaThompson
manager: tfehr
ms.date: 07/08/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSHistory, WHSLoadTable, WHSLoadPlanningListPage, WHSLoadPlanningWorkbench
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c37a98a3728cb1233a6e1207975a6b8f23f8120d
ms.sourcegitcommit: a36a4f9915ae3eb36bf8220111cf1486387713d9
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "4015909"
---
# <a name="plan-loads-and-shipments-using-the-load-planning-workbench"></a><span data-ttu-id="98cec-103">Planejar cargas e remessas usando a Bancada de planejamento de carga</span><span class="sxs-lookup"><span data-stu-id="98cec-103">Plan loads and shipments using the Load planning workbench</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="98cec-104">Este tópico mostra como usar a bancada de planejamento de carga para criar uma carga para uma ordem de venda.</span><span class="sxs-lookup"><span data-stu-id="98cec-104">This topic shows how to use the load planning workbench to create a load for a sales order.</span></span> <span data-ttu-id="98cec-105">Como um pré-requisito iremos criar a ordem de venda primeiro.</span><span class="sxs-lookup"><span data-stu-id="98cec-105">As a prerequisite we'll create the sales order first.</span></span> <span data-ttu-id="98cec-106">Este procedimento é parte do trabalho diário do coordenador de transporte.</span><span class="sxs-lookup"><span data-stu-id="98cec-106">This procedure is part of the daily work for the transportation coordinator.</span></span> <span data-ttu-id="98cec-107">A empresa de dados demo usada para criar este procedimento é USMF.</span><span class="sxs-lookup"><span data-stu-id="98cec-107">The demo data company used to create this procedure is USMF.</span></span>


## <a name="create-a-sales-order"></a><span data-ttu-id="98cec-108">Criar uma ordem de venda</span><span class="sxs-lookup"><span data-stu-id="98cec-108">Create a sales order</span></span>
1. <span data-ttu-id="98cec-109">Vá para o **Painel de navegação > Módulos > Contas a receber > Ordens > Todas as ordens de venda**.</span><span class="sxs-lookup"><span data-stu-id="98cec-109">Go to the **Navigation pane > Modules > Accounts receivable > Orders > All sales orders**.</span></span>
2. <span data-ttu-id="98cec-110">Selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="98cec-110">Select **New**.</span></span>
3. <span data-ttu-id="98cec-111">No campo **Conta do cliente** , selecione o botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="98cec-111">In the **Customer account** field, select the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="98cec-112">Selecione a conta **US-004**.</span><span class="sxs-lookup"><span data-stu-id="98cec-112">Select account **US-004**.</span></span>
5. <span data-ttu-id="98cec-113">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="98cec-113">Select **OK**.</span></span>
6. <span data-ttu-id="98cec-114">No campo **Número do item** , selecione o botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="98cec-114">In the **Item number** field, select the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="98cec-115">Selecione o item **A0001**.</span><span class="sxs-lookup"><span data-stu-id="98cec-115">Select item **A0001**.</span></span> <span data-ttu-id="98cec-116">**A0001** está habilitado para o gerenciamento de transporte.</span><span class="sxs-lookup"><span data-stu-id="98cec-116">**A0001** is enabled for transportation management.</span></span>  
8. <span data-ttu-id="98cec-117">No campo **Site** , selecione o botão suspenso para abrir a pesquisa e então selecione um item.</span><span class="sxs-lookup"><span data-stu-id="98cec-117">In the **Site** field, select the drop-down button to open the lookup, then select an item.</span></span>
9. <span data-ttu-id="98cec-118">No campo **Quantidade.** , insira um número</span><span class="sxs-lookup"><span data-stu-id="98cec-118">In the **Quantity** field, enter a number.</span></span>
10. <span data-ttu-id="98cec-119">No campo **Depósito** , digite '24' neste exemplo.</span><span class="sxs-lookup"><span data-stu-id="98cec-119">In the **Warehouse** field, type '24' for this example.</span></span> <span data-ttu-id="98cec-120">Este depósito está habilitado para o gerenciamento de transporte e para o gerenciamento de depósito avançado.</span><span class="sxs-lookup"><span data-stu-id="98cec-120">This warehouse is enabled for transportation management and advanced warehouse management.</span></span>  
11. <span data-ttu-id="98cec-121">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="98cec-121">Select **Save**.</span></span>
12. <span data-ttu-id="98cec-122">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="98cec-122">Close the page.</span></span>

## <a name="create-a-new-load"></a><span data-ttu-id="98cec-123">Criar uma nova carga</span><span class="sxs-lookup"><span data-stu-id="98cec-123">Create a new load</span></span>
1. <span data-ttu-id="98cec-124">Vá para o **Painel de navegação > Módulos > Gerenciamento de transporte > Planejamento > Bancada de planejamento de carga**.</span><span class="sxs-lookup"><span data-stu-id="98cec-124">Go to the **Navigation pane > Modules > Transportation management > Planning > Load planning workbench**.</span></span>
2. <span data-ttu-id="98cec-125">Selecione a guia **Linhas de vendas**. Agora você irá montar a carga para a ordem de venda que você acabou de criar.</span><span class="sxs-lookup"><span data-stu-id="98cec-125">Select the **Sales lines** tab. Now you'll build the load for the sales order that you just created.</span></span> <span data-ttu-id="98cec-126">Cargas podem ser montadas de acordo com a oferta e procura das ordens de compra, ordens de transferência, e ordens de venda.</span><span class="sxs-lookup"><span data-stu-id="98cec-126">Loads can be built based on supply and demand from purchase orders, transfer orders, and sales orders.</span></span>  
3. <span data-ttu-id="98cec-127">No Painel de Ação, selecione **Oferta e demanda**.</span><span class="sxs-lookup"><span data-stu-id="98cec-127">On the Action Pane, select **Supply and demand**.</span></span>
4. <span data-ttu-id="98cec-128">Selecione **Para nova carga**.</span><span class="sxs-lookup"><span data-stu-id="98cec-128">Select **To new load**.</span></span>
5. <span data-ttu-id="98cec-129">No campo **ID do modelo de carga** , selecione o botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="98cec-129">In the **Load template ID** field, select the drop-down button to open the lookup.</span></span> <span data-ttu-id="98cec-130">O modelo de carga define as medidas máximas para peso e volume da carga total.</span><span class="sxs-lookup"><span data-stu-id="98cec-130">The Load template defines maximum measurements for weight and volume of the entire load.</span></span> <span data-ttu-id="98cec-131">Por exemplo, o modelo de carga pode representar o tamanho de um contêiner ou caminhão.</span><span class="sxs-lookup"><span data-stu-id="98cec-131">For example, the load template might represent the size of a container or truck.</span></span> <span data-ttu-id="98cec-132">Selecione um item.</span><span class="sxs-lookup"><span data-stu-id="98cec-132">Select an item.</span></span>
6. <span data-ttu-id="98cec-133">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="98cec-133">Select **OK**.</span></span>

## <a name="rate-and-route-the-load"></a><span data-ttu-id="98cec-134">Avaliar e encaminhar a carga</span><span class="sxs-lookup"><span data-stu-id="98cec-134">Rate and route the load</span></span>
1. <span data-ttu-id="98cec-135">Selecione **Classificação e roteiro**.</span><span class="sxs-lookup"><span data-stu-id="98cec-135">Select **Rating and routing**.</span></span>
2. <span data-ttu-id="98cec-136">Selecione **Bancada da taxa de roteiro**.</span><span class="sxs-lookup"><span data-stu-id="98cec-136">Select **Rate route workbench**.</span></span>
3. <span data-ttu-id="98cec-137">Selecione **Loja de taxas**.</span><span class="sxs-lookup"><span data-stu-id="98cec-137">Select **Rate shop**.</span></span>
4. <span data-ttu-id="98cec-138">Na lista, localize e selecione o registro desejado.</span><span class="sxs-lookup"><span data-stu-id="98cec-138">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="98cec-139">Selecionar **Atribuir**.</span><span class="sxs-lookup"><span data-stu-id="98cec-139">Select **Assign**.</span></span>
6. <span data-ttu-id="98cec-140">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="98cec-140">Close the page.</span></span>

