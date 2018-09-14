--- 
title: Verificar a disponibilidade do estoque
description: "Este procedimento mostra como verificar um valor disponível e o estoque físico disponível de um número de item específico."
author: 
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: InventOnHandItemListPage, SysQueryForm, InventDimParmFixed, InventSupply, DefaultDashboard, WHSInventPhysicalOnhand, WHSOnHand
audience: Application User
ms.reviewer: 
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: 
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0312b8cfadd45f8e59225e9daba78b9e216cff51
ms.openlocfilehash: 1a7c8309a121dc2adeb450d0a81f5b17820bca97
ms.contentlocale: pt-br
ms.lasthandoff: 09/14/2018

---
# <a name="check-the-availability-of-stock"></a><span data-ttu-id="a8798-103">Verificar a disponibilidade do estoque</span><span class="sxs-lookup"><span data-stu-id="a8798-103">Check the availability of stock</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="a8798-104">Este procedimento mostra como verificar um valor disponível e o estoque físico disponível de um número de item específico.</span><span class="sxs-lookup"><span data-stu-id="a8798-104">This procedure shows you how to check on-hand and physical on-hand inventory for a specific item number.</span></span> <span data-ttu-id="a8798-105">Ele também mostra como obter informações de fornecimento relacionadas ao item.</span><span class="sxs-lookup"><span data-stu-id="a8798-105">It also shows you how to get supply information related to an item.</span></span> <span data-ttu-id="a8798-106">O estoque físico disponível é o estoque disponível que está disponível ou seja, comprado, recebido e registrado.</span><span class="sxs-lookup"><span data-stu-id="a8798-106">Physical on-hand inventory is the on-hand inventory that’s available – that is, it’s purchased, received and registered.</span></span> <span data-ttu-id="a8798-107">O estoque disponível inclui o estoque disponível, mas também o estoque que é ordenado e esperado, mas que ainda não foi recebido ou registrado.</span><span class="sxs-lookup"><span data-stu-id="a8798-107">On-hand inventory includes the available on-hand inventory, but also the inventory that’s been ordered and is expected, but not yet received or registered.</span></span> <span data-ttu-id="a8798-108">Você pode ver todo esse procedimento na empresa USMF de dados demo, ou usando seus próprios dados.</span><span class="sxs-lookup"><span data-stu-id="a8798-108">You can walk through this procedure in demo data company USMF, or using your own data.</span></span> <span data-ttu-id="a8798-109">Se você estiver usando USMF você pode usar os valores de exemplo mostrados.</span><span class="sxs-lookup"><span data-stu-id="a8798-109">If you are using USMF you can use the example values that are shown.</span></span> <span data-ttu-id="a8798-110">Essas tarefas normalmente seriam realizadas por um funcionário do depósito.</span><span class="sxs-lookup"><span data-stu-id="a8798-110">These tasks would typically be carried out by a warehouse worker.</span></span>


## <a name="check-on-hand-inventory-for-an-item"></a><span data-ttu-id="a8798-111">Verifique estoque disponível de um item</span><span class="sxs-lookup"><span data-stu-id="a8798-111">Check on-hand inventory for an item</span></span>
1. <span data-ttu-id="a8798-112">Vá para Gerenciamento de estoque > Consultas e relatórios > Estoque disponível.</span><span class="sxs-lookup"><span data-stu-id="a8798-112">Go to Inventory management > Inquiries and reports > On-hand inventory.</span></span>
2. <span data-ttu-id="a8798-113">Selecione a linha do número do item.</span><span class="sxs-lookup"><span data-stu-id="a8798-113">Select the Item number row.</span></span>
    * <span data-ttu-id="a8798-114">Para ver o estoque disponível por número de item, selecione a linha na tabela definida como o estoque disponível e o campo que está definido como o número do item.</span><span class="sxs-lookup"><span data-stu-id="a8798-114">To query the on-hand inventory by item number, select the row where the Table is set to On-hand inventory and Field is set to Item number.</span></span>  
3. <span data-ttu-id="a8798-115">No campo Critérios, selecione o item que você deseja consultar.</span><span class="sxs-lookup"><span data-stu-id="a8798-115">In the Criteria field, select the item you want to query.</span></span>
    * <span data-ttu-id="a8798-116">Se você estiver usando a empresa de dados de demonstração USMF, poderá selecionar 'M9201'.</span><span class="sxs-lookup"><span data-stu-id="a8798-116">If you're using the USMF demo data company, you can select 'M9201'.</span></span>  
4. <span data-ttu-id="a8798-117">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="a8798-117">Click OK.</span></span>
5. <span data-ttu-id="a8798-118">Clique em Dimensões.</span><span class="sxs-lookup"><span data-stu-id="a8798-118">Click Dimensions.</span></span>
    * <span data-ttu-id="a8798-119">A guia Dimensões permite selecionar quantos detalhes você deseja ver sobre seu estoque disponível.</span><span class="sxs-lookup"><span data-stu-id="a8798-119">The Dimensions tab allows you select how much detail you want to see about your on-hand inventory.</span></span> <span data-ttu-id="a8798-120">Se for necessário os dados relacionados à reserva, você deve exibir todas as dimensões de estoque dos itens que usam processos avançados de depósito (WHS).</span><span class="sxs-lookup"><span data-stu-id="a8798-120">If you need data related to reservation, you must display all inventory dimensions for the items that use advanced warehouse (WHS) processes.</span></span>  
6. <span data-ttu-id="a8798-121">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="a8798-121">Click OK.</span></span>
7. <span data-ttu-id="a8798-122">No Painel de Ação, clique em Informações relacionadas.</span><span class="sxs-lookup"><span data-stu-id="a8798-122">On the Action Pane, click Related information.</span></span>
    * <span data-ttu-id="a8798-123">Se não for exibido isso, talvez você precise clicar no botão de reticências (…) para ver opções adicionais do painel de ações.</span><span class="sxs-lookup"><span data-stu-id="a8798-123">If you don’t see this, you may need to click on the Ellipsis button (…) to see additional action pane options.</span></span>  
8. <span data-ttu-id="a8798-124">Clique em Visão geral de fornecimento.</span><span class="sxs-lookup"><span data-stu-id="a8798-124">Click Supply overview.</span></span>
    * <span data-ttu-id="a8798-125">A guia de visão geral de fornecimento fornece informações de fornecimento de um item específico, como a quantidade disponível, o tempo de entrega e informações do fornecedor.</span><span class="sxs-lookup"><span data-stu-id="a8798-125">The Supply overview tab provides supply information for a specific item, such as the quantity on-hand, the lead time, and vendor information.</span></span>  
9. <span data-ttu-id="a8798-126">Expanda a seção Disponível.</span><span class="sxs-lookup"><span data-stu-id="a8798-126">Expand the On-hand section.</span></span>
10. <span data-ttu-id="a8798-127">Expanda a seção Fornecedores.</span><span class="sxs-lookup"><span data-stu-id="a8798-127">Expand the Vendors section.</span></span>
11. <span data-ttu-id="a8798-128">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="a8798-128">Close the page.</span></span>
12. <span data-ttu-id="a8798-129">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="a8798-129">Close the page.</span></span>

## <a name="check-physical-on-hand-inventory"></a><span data-ttu-id="a8798-130">Verifique Estoque disponível físico</span><span class="sxs-lookup"><span data-stu-id="a8798-130">Check physical on-hand inventory</span></span>
1. <span data-ttu-id="a8798-131">Vá para Gerenciamento de depósito > Consultas e relatórios > Estoque disponível ou físico.</span><span class="sxs-lookup"><span data-stu-id="a8798-131">Go to Warehouse management > Inquiries and reports > Physical on-hand inventory.</span></span>
2. <span data-ttu-id="a8798-132">No campo Número de item, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="a8798-132">In the Item number field, type a value.</span></span>
    * <span data-ttu-id="a8798-133">Você pode usar os campos de site e depósito para filtrar a lista de itens.</span><span class="sxs-lookup"><span data-stu-id="a8798-133">You can use the Site and Warehouse fields to filter the list of items.</span></span>  
3. <span data-ttu-id="a8798-134">Atualize a página.</span><span class="sxs-lookup"><span data-stu-id="a8798-134">Refresh the page.</span></span>
4. <span data-ttu-id="a8798-135">Clique em Exibir dimensões.</span><span class="sxs-lookup"><span data-stu-id="a8798-135">Click Display Dimensions.</span></span>
    * <span data-ttu-id="a8798-136">A guia Exibir dimensões permite selecionar quantos detalhes você deseja ver sobre seu estoque disponível.</span><span class="sxs-lookup"><span data-stu-id="a8798-136">The Dimensions Display tab allows you select how much detail you want to see about your on-hand inventory.</span></span>  
5. <span data-ttu-id="a8798-137">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="a8798-137">Click OK.</span></span>
6. <span data-ttu-id="a8798-138">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="a8798-138">Close the page.</span></span>

## <a name="check-on-hand-inventory-by-location"></a><span data-ttu-id="a8798-139">Verifique o estoque disponível por localização</span><span class="sxs-lookup"><span data-stu-id="a8798-139">Check on-hand inventory by location</span></span>
1. <span data-ttu-id="a8798-140">Vá para Gerenciamento de depósito > Consultas e relatórios > Disponível por local.</span><span class="sxs-lookup"><span data-stu-id="a8798-140">Go to Warehouse management > Inquiries and reports > On hand by location.</span></span>
2. <span data-ttu-id="a8798-141">No campo Depósito, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="a8798-141">In the Warehouse field, type a value.</span></span>
    * <span data-ttu-id="a8798-142">Se você estiver usando a empresa de dados de demonstração USMF, você pode usar '51'.</span><span class="sxs-lookup"><span data-stu-id="a8798-142">If you're using the USMF demo data company, you can use '51'.</span></span>  
3. <span data-ttu-id="a8798-143">Atualize a página.</span><span class="sxs-lookup"><span data-stu-id="a8798-143">Refresh the page.</span></span>
4. <span data-ttu-id="a8798-144">Clique em Exibir dimensões.</span><span class="sxs-lookup"><span data-stu-id="a8798-144">Click Display Dimensions.</span></span>
5. <span data-ttu-id="a8798-145">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="a8798-145">Click OK.</span></span>
6. <span data-ttu-id="a8798-146">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="a8798-146">Close the page.</span></span>


