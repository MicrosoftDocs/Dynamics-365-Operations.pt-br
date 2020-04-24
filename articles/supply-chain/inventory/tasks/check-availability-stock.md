---
title: Verificar a disponibilidade do estoque
description: Este procedimento mostra como verificar um valor disponível e o estoque físico disponível de um número de item específico.
author: ShylaThompson
manager: tfehr
ms.date: 06/25/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventOnHandItemListPage, SysQueryForm, InventDimParmFixed, InventSupply, DefaultDashboard, WHSInventPhysicalOnhand, WHSOnHand
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: ShylaThompson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e76c123ffbeb33cbc3ba01b4b2758208ed0c445f
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/02/2020
ms.locfileid: "3204208"
---
# <a name="check-the-availability-of-stock"></a><span data-ttu-id="3d9ed-103">Verificar a disponibilidade do estoque</span><span class="sxs-lookup"><span data-stu-id="3d9ed-103">Check the availability of stock</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="3d9ed-104">Este procedimento mostra como verificar um valor disponível e o estoque físico disponível de um número de item específico.</span><span class="sxs-lookup"><span data-stu-id="3d9ed-104">This procedure shows you how to check on-hand and physical on-hand inventory for a specific item number.</span></span> <span data-ttu-id="3d9ed-105">Ele também mostra como obter informações de fornecimento relacionadas ao item.</span><span class="sxs-lookup"><span data-stu-id="3d9ed-105">It also shows you how to get supply information related to an item.</span></span> <span data-ttu-id="3d9ed-106">O estoque físico disponível é o estoque disponível que está disponível ou seja, comprado, recebido e registrado.</span><span class="sxs-lookup"><span data-stu-id="3d9ed-106">Physical on-hand inventory is the on-hand inventory that's available – that is, it's purchased, received and registered.</span></span> <span data-ttu-id="3d9ed-107">O estoque disponível inclui o estoque disponível, mas também o estoque que é ordenado e esperado, mas que ainda não foi recebido ou registrado.</span><span class="sxs-lookup"><span data-stu-id="3d9ed-107">On-hand inventory includes the available on-hand inventory, but also the inventory that's been ordered and is expected, but not yet received or registered.</span></span> <span data-ttu-id="3d9ed-108">Você pode ver todo esse procedimento na empresa USMF de dados demo, ou usando seus próprios dados.</span><span class="sxs-lookup"><span data-stu-id="3d9ed-108">You can walk through this procedure in demo data company USMF, or using your own data.</span></span> <span data-ttu-id="3d9ed-109">Se você estiver usando USMF você pode usar os valores de exemplo mostrados.</span><span class="sxs-lookup"><span data-stu-id="3d9ed-109">If you are using USMF you can use the example values that are shown.</span></span> <span data-ttu-id="3d9ed-110">Essas tarefas normalmente seriam realizadas por um funcionário do depósito.</span><span class="sxs-lookup"><span data-stu-id="3d9ed-110">These tasks would typically be carried out by a warehouse worker.</span></span>


## <a name="check-on-hand-inventory-for-an-item"></a><span data-ttu-id="3d9ed-111">Verifique estoque disponível de um item</span><span class="sxs-lookup"><span data-stu-id="3d9ed-111">Check on-hand inventory for an item</span></span>
1. <span data-ttu-id="3d9ed-112">Vá para **Painel de navegação > Módulos > Gerenciamento de estoque > Consultas e relatórios > Estoque disponível**.</span><span class="sxs-lookup"><span data-stu-id="3d9ed-112">Go to **Navigation pane > Modules > Inventory management > Inquiries and reports > On-hand inventory**.</span></span>
2. <span data-ttu-id="3d9ed-113">Selecione a linha **Número do item**.</span><span class="sxs-lookup"><span data-stu-id="3d9ed-113">Select the **Item number** row.</span></span> <span data-ttu-id="3d9ed-114">Para consultar o estoque disponível por número do item, selecione a linha em que a tabela está definida como **Estoque disponível** e o campo está definido como o número do **Item**.</span><span class="sxs-lookup"><span data-stu-id="3d9ed-114">To query the on-hand inventory by item number, select the row where the Table is set to **On-hand inventory** and Field is set to **Item** number.</span></span>
3. <span data-ttu-id="3d9ed-115">No campo **Critérios**, selecione o item que você deseja consultar.</span><span class="sxs-lookup"><span data-stu-id="3d9ed-115">In the **Criteria** field, select the item you want to query.</span></span> <span data-ttu-id="3d9ed-116">Se você estiver usando a empresa de dados de demonstração USMF, poderá selecionar 'M9201'.</span><span class="sxs-lookup"><span data-stu-id="3d9ed-116">If you're using the USMF demo data company, you can select 'M9201'.</span></span>  
4. <span data-ttu-id="3d9ed-117">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="3d9ed-117">Click **OK**.</span></span>
5. <span data-ttu-id="3d9ed-118">No **Painel de Ação**, clique em **Dimensões**.</span><span class="sxs-lookup"><span data-stu-id="3d9ed-118">On the **Action pane**, click **Dimensions**.</span></span> <span data-ttu-id="3d9ed-119">A guia **Dimensões** permite selecionar o nível de detalhes de seu estoque disponível que você deseja ver.</span><span class="sxs-lookup"><span data-stu-id="3d9ed-119">The **Dimensions** tab allows you select how much detail you want to see about your on-hand inventory.</span></span> <span data-ttu-id="3d9ed-120">Se for necessário os dados relacionados à reserva, você deve exibir todas as dimensões de estoque dos itens que usam processos avançados de depósito (WHS).</span><span class="sxs-lookup"><span data-stu-id="3d9ed-120">If you need data related to reservation, you must display all inventory dimensions for the items that use advanced warehouse (WHS) processes.</span></span>
6. <span data-ttu-id="3d9ed-121">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="3d9ed-121">Click **OK**.</span></span>
7. <span data-ttu-id="3d9ed-122">No **Painel de Ação**, clique em **Informações relacionadas**.</span><span class="sxs-lookup"><span data-stu-id="3d9ed-122">On the **Action Pane**, click **Related information**.</span></span> <span data-ttu-id="3d9ed-123">Se essa opção não for exibida, talvez você precise clicar no botão de reticências (…) para ver opções adicionais do painel de ação.</span><span class="sxs-lookup"><span data-stu-id="3d9ed-123">If you don't see this option, you may need to click on the Ellipsis button (…) to see additional action pane options.</span></span>
8. <span data-ttu-id="3d9ed-124">Clique em **Visão geral do fornecimento**.</span><span class="sxs-lookup"><span data-stu-id="3d9ed-124">Click **Supply overview**.</span></span> <span data-ttu-id="3d9ed-125">A guia **Visão geral do fornecimento** apresenta informações de fornecimento de um item específico, como a quantidade disponível, o tempo de entrega e informações do fornecedor.</span><span class="sxs-lookup"><span data-stu-id="3d9ed-125">The **Supply overview** tab provides supply information for a specific item, such as the quantity on-hand, the lead time, and vendor information.</span></span>  
9. <span data-ttu-id="3d9ed-126">Expanda a seção **Disponível**.</span><span class="sxs-lookup"><span data-stu-id="3d9ed-126">Expand the **On-hand** section.</span></span>
10. <span data-ttu-id="3d9ed-127">Expanda a seção **Fornecedores**.</span><span class="sxs-lookup"><span data-stu-id="3d9ed-127">Expand the **Vendors** section.</span></span>
11. <span data-ttu-id="3d9ed-128">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="3d9ed-128">Close the page.</span></span>
12. <span data-ttu-id="3d9ed-129">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="3d9ed-129">Close the page.</span></span>

## <a name="check-physical-on-hand-inventory"></a><span data-ttu-id="3d9ed-130">Verifique Estoque disponível físico</span><span class="sxs-lookup"><span data-stu-id="3d9ed-130">Check physical on-hand inventory</span></span>
1. <span data-ttu-id="3d9ed-131">Vá para **Painel de navegação > Módulos > Gerenciamento de depósito > Consultas e relatórios > Estoque disponível físico**.</span><span class="sxs-lookup"><span data-stu-id="3d9ed-131">Go to **Navigation pane > Modules > Warehouse management > Inquiries and reports > Physical on-hand inventory**.</span></span>
2. <span data-ttu-id="3d9ed-132">No campo **Número de item**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="3d9ed-132">In the **Item number** field, type a value.</span></span> <span data-ttu-id="3d9ed-133">Você pode usar os campos de site e depósito para filtrar a lista de itens.</span><span class="sxs-lookup"><span data-stu-id="3d9ed-133">You can use the Site and Warehouse fields to filter the list of items.</span></span> 
3. <span data-ttu-id="3d9ed-134">Atualize a página.</span><span class="sxs-lookup"><span data-stu-id="3d9ed-134">Refresh the page.</span></span>
4. <span data-ttu-id="3d9ed-135">No **Painel de Ação**, clique em **Exibir Dimensões**.</span><span class="sxs-lookup"><span data-stu-id="3d9ed-135">On the **Action pane**, click **Display Dimensions**.</span></span> <span data-ttu-id="3d9ed-136">A guia Exibir dimensões permite selecionar quantos detalhes você deseja ver sobre seu estoque disponível.</span><span class="sxs-lookup"><span data-stu-id="3d9ed-136">The Dimensions Display tab allows you select how much detail you want to see about your on-hand inventory.</span></span>
5. <span data-ttu-id="3d9ed-137">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="3d9ed-137">Click **OK**.</span></span>
6. <span data-ttu-id="3d9ed-138">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="3d9ed-138">Close the page.</span></span>

## <a name="check-on-hand-inventory-by-location"></a><span data-ttu-id="3d9ed-139">Verifique o estoque disponível por localização</span><span class="sxs-lookup"><span data-stu-id="3d9ed-139">Check on-hand inventory by location</span></span>
1. <span data-ttu-id="3d9ed-140">Vá para **Painel de navegação > Módulos > Gerenciamento de depósito > Consultas e relatórios > Disponibilidade por localização**.</span><span class="sxs-lookup"><span data-stu-id="3d9ed-140">Go to **Navigation pane > Modules > Warehouse management > Inquiries and reports > On hand by location**.</span></span>
2. <span data-ttu-id="3d9ed-141">No campo **Depósito**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="3d9ed-141">In the **Warehouse** field, type a value.</span></span> <span data-ttu-id="3d9ed-142">Se você estiver usando a empresa de dados de demonstração USMF, você pode usar '51'.</span><span class="sxs-lookup"><span data-stu-id="3d9ed-142">If you're using the USMF demo data company, you can use '51'.</span></span>  
3. <span data-ttu-id="3d9ed-143">Atualize a página.</span><span class="sxs-lookup"><span data-stu-id="3d9ed-143">Refresh the page.</span></span>
4. <span data-ttu-id="3d9ed-144">Clique em **Exibir Dimensões**.</span><span class="sxs-lookup"><span data-stu-id="3d9ed-144">Click **Display Dimensions**.</span></span>
5. <span data-ttu-id="3d9ed-145">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="3d9ed-145">Click **OK**.</span></span>
6. <span data-ttu-id="3d9ed-146">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="3d9ed-146">Close the page.</span></span>

