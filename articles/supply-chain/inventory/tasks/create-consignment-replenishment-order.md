---
title: Criar uma ordem de reabastecimento de consignação
description: Este tópico explica como criar uma ordem de reabastecimento de remessa que possa acompanhar a entrega esperada de um fornecedor no estoque de remessa.
author: mkirknel
manager: AnnBe
ms.date: 08/19/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ConsignmentReplenishmentOrder, ConsignmentReplenishmentOrderCreate, InventTrans, ConsignmentDraftReplenishmentOrderJournal, InventOnhandMovement, InventOnhandItem, InventItemIdLookupSimple
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f426dbf00eace23da2f26eb50dd9675fe22ed445
ms.sourcegitcommit: e10491a2ff04f65d9f306ef6e068ee123213b23b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/21/2019
ms.locfileid: "1914760"
---
# <a name="create-a-consignment-replenishment-order"></a><span data-ttu-id="b5bb9-103">Criar uma ordem de reabastecimento de consignação</span><span class="sxs-lookup"><span data-stu-id="b5bb9-103">Create a consignment replenishment order</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="b5bb9-104">Este tópico explica como criar uma ordem de reabastecimento de remessa que possa acompanhar a entrega esperada de um fornecedor no estoque de remessa.</span><span class="sxs-lookup"><span data-stu-id="b5bb9-104">This topic explains how to create a consignment replenishment order where you can track the expected delivery from a vendor into your consignment inventory.</span></span> <span data-ttu-id="b5bb9-105">Também mostra como registrar o recebimento de produtos de modo que o estoque da remessa esteja registrado em um inventário disponível pertencido ao fornecedor.</span><span class="sxs-lookup"><span data-stu-id="b5bb9-105">It also shows how to record a receipt of products so that the consignment inventory is registered as on-hand inventory owned by the vendor.</span></span> <span data-ttu-id="b5bb9-106">Esse procedimento seria feito normalmente por um profissional de compras.</span><span class="sxs-lookup"><span data-stu-id="b5bb9-106">This procedure would typically be done by a procurement professional.</span></span> <span data-ttu-id="b5bb9-107">Você pode usar este guia na empresa USMF de dados de demonstração.</span><span class="sxs-lookup"><span data-stu-id="b5bb9-107">You can use this guide in demo data company USMF.</span></span> <span data-ttu-id="b5bb9-108">Este procedimento é para um recurso que foi adicionado na versão 1611 do Dynamics 365 for Operations.</span><span class="sxs-lookup"><span data-stu-id="b5bb9-108">This procedure is for a feature that was added in Dynamics 365 for Operations, version 1611.</span></span>

## <a name="create-a-consignment-replenishment-order"></a><span data-ttu-id="b5bb9-109">Criar uma ordem de reabastecimento de consignação</span><span class="sxs-lookup"><span data-stu-id="b5bb9-109">Create a consignment replenishment order</span></span>
1. <span data-ttu-id="b5bb9-110">No Painel de Navegação, vá para **Módulos > Compras e fornecimento > Consignação > Ordens de reabastecimento de consignação**.</span><span class="sxs-lookup"><span data-stu-id="b5bb9-110">In the navigation pane, go to **Modules > Procurement and sourcing > Consignment > Consignment replenishment orders**.</span></span>
2. <span data-ttu-id="b5bb9-111">Selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="b5bb9-111">Select **New**.</span></span>
3. <span data-ttu-id="b5bb9-112">No campo **Conta de fornecedor**, selecione o fornecedor **US-104** (é preciso selecionar um fornecedor registrado como proprietário na página **proprietários de estoque**).</span><span class="sxs-lookup"><span data-stu-id="b5bb9-112">In the **Vendor account** field, select vendor **US-104** (you must select a vendor that's registered as an owner in the **inventory owners** page).</span></span> 
4. <span data-ttu-id="b5bb9-113">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="b5bb9-113">Select **OK**.</span></span>
5. <span data-ttu-id="b5bb9-114">Selecione **Adicionar linha**.</span><span class="sxs-lookup"><span data-stu-id="b5bb9-114">Select **Add line**.</span></span>
6. <span data-ttu-id="b5bb9-115">No campo **Número do item**, digite `M9211CI` (é preciso selecionar um item configurado para o estoque em consignação).</span><span class="sxs-lookup"><span data-stu-id="b5bb9-115">In the **Item number** field, type `M9211CI` (you must select an item that is set up for consignment inventory).</span></span>
7. <span data-ttu-id="b5bb9-116">No campo **Quantidade.**, insira um número</span><span class="sxs-lookup"><span data-stu-id="b5bb9-116">In the **Quantity** field, enter a number.</span></span>
8. <span data-ttu-id="b5bb9-117">No campo **Data de entrega solicitada**, insira uma data.</span><span class="sxs-lookup"><span data-stu-id="b5bb9-117">In the **Requested delivery date** field, enter a date.</span></span> <span data-ttu-id="b5bb9-118">Datas solicitadas e confirmadas são usadas por mecanismo de MRP para entrada esperada de mercadorias.</span><span class="sxs-lookup"><span data-stu-id="b5bb9-118">The requested and confirmed dates are used by the MRP engine for the expected arrival of the goods.</span></span>  
9. <span data-ttu-id="b5bb9-119">No campo **Data de entrega confirmada**, insira uma data.</span><span class="sxs-lookup"><span data-stu-id="b5bb9-119">In the **Confirmed delivery date** field, enter a date.</span></span>
10. <span data-ttu-id="b5bb9-120">Expanda a seção **Detalhes da linha**.</span><span class="sxs-lookup"><span data-stu-id="b5bb9-120">Expand the **Line details** section.</span></span>
11. <span data-ttu-id="b5bb9-121">Selecione a guia **Dimensões de estoque**.</span><span class="sxs-lookup"><span data-stu-id="b5bb9-121">Select the **Inventory dimensions** tab.</span></span>
12. <span data-ttu-id="b5bb9-122">Para mostrar o proprietário no campo **Proprietário de dimensões de estoque**, atualize a página.</span><span class="sxs-lookup"><span data-stu-id="b5bb9-122">To show the owner in the **Inventory dimensions owner** field, refresh the page.</span></span> <span data-ttu-id="b5bb9-123">O fornecedor US-104 agora está listado como proprietário.</span><span class="sxs-lookup"><span data-stu-id="b5bb9-123">Vendor US-104 is now listed as the owner.</span></span>  

## <a name="check-the-inventory-transaction-status"></a><span data-ttu-id="b5bb9-124">Verifique o status da Data da transação de estoque</span><span class="sxs-lookup"><span data-stu-id="b5bb9-124">Check the inventory transaction status</span></span>
1. <span data-ttu-id="b5bb9-125">Selecione **Estoque**.</span><span class="sxs-lookup"><span data-stu-id="b5bb9-125">Select **Inventory**.</span></span>
2. <span data-ttu-id="b5bb9-126">Selecione **Transações**.</span><span class="sxs-lookup"><span data-stu-id="b5bb9-126">Select **Transactions**.</span></span>
3. <span data-ttu-id="b5bb9-127">Na linha desejada, observe que o campo **Recibo** é definido como **Encomendado**.</span><span class="sxs-lookup"><span data-stu-id="b5bb9-127">In the desired row, notice that the **Receipt** field is set to **Ordered**.</span></span>  
4. <span data-ttu-id="b5bb9-128">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="b5bb9-128">Close the page.</span></span>

## <a name="receive-items"></a><span data-ttu-id="b5bb9-129">Receber itens</span><span class="sxs-lookup"><span data-stu-id="b5bb9-129">Receive items</span></span>
1. <span data-ttu-id="b5bb9-130">Selecione **Recebimento de produtos**.</span><span class="sxs-lookup"><span data-stu-id="b5bb9-130">Select **Product receipt**.</span></span>
2. <span data-ttu-id="b5bb9-131">No campo **Recebimento de produtos externos**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="b5bb9-131">In the **External product receipt** field, type a value.</span></span>
3. <span data-ttu-id="b5bb9-132">No campo **Quantidade**, insira um número que é menor que o número que é mostrado.</span><span class="sxs-lookup"><span data-stu-id="b5bb9-132">In the **Quantity** field, enter a number that’s lower than the number that’s shown there.</span></span> 
4. <span data-ttu-id="b5bb9-133">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="b5bb9-133">Select **OK**.</span></span>

## <a name="check-the-on-hand-inventory"></a><span data-ttu-id="b5bb9-134">Verifique o estoque disponível</span><span class="sxs-lookup"><span data-stu-id="b5bb9-134">Check the on-hand inventory</span></span>
1. <span data-ttu-id="b5bb9-135">Selecione **Estoque**.</span><span class="sxs-lookup"><span data-stu-id="b5bb9-135">Select **Inventory**.</span></span>
2. <span data-ttu-id="b5bb9-136">Selecione **Disponível**.</span><span class="sxs-lookup"><span data-stu-id="b5bb9-136">Select **On-hand**.</span></span>
3. <span data-ttu-id="b5bb9-137">Selecione **Visão Geral**.</span><span class="sxs-lookup"><span data-stu-id="b5bb9-137">Select **Overview**.</span></span> <span data-ttu-id="b5bb9-138">Os itens recebidos como o estoque de remessa possuído por fornecedor disponíveis disponível.</span><span class="sxs-lookup"><span data-stu-id="b5bb9-138">The items that have been received as consignment inventory owned by the vendor are available on-hand.</span></span> <span data-ttu-id="b5bb9-139">A quantidade pendente na ordem de reabastecimento da consignação é mostrada no campo **Total encomendado**.</span><span class="sxs-lookup"><span data-stu-id="b5bb9-139">The remaining quantity on the consignment replenishment order is shown in the **Ordered in total** field.</span></span>  
4. <span data-ttu-id="b5bb9-140">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="b5bb9-140">Close the page.</span></span>

