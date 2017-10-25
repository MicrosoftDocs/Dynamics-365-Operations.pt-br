---
title: "Criar uma ordem de reabastecimento de consignação"
description: Este procedimento mostra como criar uma ordem de reabastecimento de remessa que possa acompanhar a entrega esperada de um fornecedor no estoque de remessa.
author: mkirknel
manager: AnnBe
ms.date: 10/13/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: f7f8005ec9e723c94d53e6ab81f04ee388c83faa
ms.contentlocale: pt-br
ms.lasthandoff: 09/29/2017

---
# <a name="create-a-consignment-replenishment-order"></a><span data-ttu-id="7220e-103">Criar uma ordem de reabastecimento de consignação</span><span class="sxs-lookup"><span data-stu-id="7220e-103">Create a consignment replenishment order</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="7220e-104">Este procedimento mostra como criar uma ordem de reabastecimento de remessa que possa acompanhar a entrega esperada de um fornecedor no estoque de remessa.</span><span class="sxs-lookup"><span data-stu-id="7220e-104">This procedure shows how to create a consignment replenishment order where you can track the expected delivery from a vendor into your consignment inventory.</span></span> <span data-ttu-id="7220e-105">Também mostra como registrar o recebimento de produtos de modo que o estoque da remessa esteja registrado em um inventário disponível pertencido ao fornecedor.</span><span class="sxs-lookup"><span data-stu-id="7220e-105">It also shows how to record a receipt of products so that the consignment inventory is registered as on-hand inventory owned by the vendor.</span></span> <span data-ttu-id="7220e-106">Esse procedimento seria feito normalmente por um profissional de compras.</span><span class="sxs-lookup"><span data-stu-id="7220e-106">This procedure would typically be done by a procurement professional.</span></span> <span data-ttu-id="7220e-107">Você pode usar este guia na empresa USMF de dados de demonstração.</span><span class="sxs-lookup"><span data-stu-id="7220e-107">You can use this guide in demo data company USMF.</span></span> <span data-ttu-id="7220e-108">Este procedimento é para um recurso que foi adicionado à versão 1611 do Dynamics 365 for Operations.</span><span class="sxs-lookup"><span data-stu-id="7220e-108">This procedure is for a feature that was added in Dynamics 365 for Operations, version 1611.</span></span>




## <a name="create-a-consignment-replenishment-order"></a><span data-ttu-id="7220e-109">Criar uma ordem de reabastecimento de consignação</span><span class="sxs-lookup"><span data-stu-id="7220e-109">Create a consignment replenishment order</span></span>
1. <span data-ttu-id="7220e-110">Vá para Compras > Consignação > Ordens de reabastecimento de consignação.</span><span class="sxs-lookup"><span data-stu-id="7220e-110">Go to Procurement and sourcing > Consignment > Consignment replenishment orders.</span></span>
2. <span data-ttu-id="7220e-111">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="7220e-111">Click New.</span></span>
3. <span data-ttu-id="7220e-112">No campo Conta de fornecedor, selecione o fornecedor US-104.</span><span class="sxs-lookup"><span data-stu-id="7220e-112">In the Vendor account field, select vendor US-104.</span></span>
    * <span data-ttu-id="7220e-113">Marque um fornecedor que está registrado como o proprietário da os proprietários de estoque.</span><span class="sxs-lookup"><span data-stu-id="7220e-113">You must select a vendor that’s registered as an owner in the Inventory owners page.</span></span>  
4. <span data-ttu-id="7220e-114">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="7220e-114">Click OK.</span></span>
5. <span data-ttu-id="7220e-115">Clique em Adicionar linha.</span><span class="sxs-lookup"><span data-stu-id="7220e-115">Click Add line.</span></span>
6. <span data-ttu-id="7220e-116">No campo Número do item, digite M9211CI.</span><span class="sxs-lookup"><span data-stu-id="7220e-116">In the Item number field, type M9211CI.</span></span>
    * <span data-ttu-id="7220e-117">Você deve selecionar um item configurado para estoque de remessa.</span><span class="sxs-lookup"><span data-stu-id="7220e-117">You must select an item that is set up for consignment inventory.</span></span>  
7. <span data-ttu-id="7220e-118">No campo Quantidade, insira um número.</span><span class="sxs-lookup"><span data-stu-id="7220e-118">In the Quantity field, enter a number.</span></span>
8. <span data-ttu-id="7220e-119">No campo Data de entrega solicitada, insira uma data.</span><span class="sxs-lookup"><span data-stu-id="7220e-119">In the Requested delivery date field, enter a date.</span></span>
    * <span data-ttu-id="7220e-120">Datas solicitadas e confirmadas são usadas por mecanismo de MRP para entrada esperada de mercadorias.</span><span class="sxs-lookup"><span data-stu-id="7220e-120">The requested and confirmed dates are used by the MRP engine for the expected arrival of the goods.</span></span>  
9. <span data-ttu-id="7220e-121">No campo Data de entrega confirmada, insira uma data.</span><span class="sxs-lookup"><span data-stu-id="7220e-121">In the Confirmed delivery date field, enter a date.</span></span>
10. <span data-ttu-id="7220e-122">Expanda a seção Detalhes da linha.</span><span class="sxs-lookup"><span data-stu-id="7220e-122">Expand the Line details section.</span></span>
11. <span data-ttu-id="7220e-123">Clique na guia Dimensões de estoque.</span><span class="sxs-lookup"><span data-stu-id="7220e-123">Click the Inventory dimensions tab.</span></span>
12. <span data-ttu-id="7220e-124">Mostrar para o proprietário no proprietário de dimensões de estoque, atualizar a página.</span><span class="sxs-lookup"><span data-stu-id="7220e-124">To show the owner in the Inventory dimensions owner field, refresh the page.</span></span>
    * <span data-ttu-id="7220e-125">O fornecedor US-104 agora está listado como proprietário.</span><span class="sxs-lookup"><span data-stu-id="7220e-125">Vendor US-104 is now listed as the owner.</span></span>  

## <a name="check-the-inventory-transaction-status"></a><span data-ttu-id="7220e-126">Verifique o status da Data da transação de estoque</span><span class="sxs-lookup"><span data-stu-id="7220e-126">Check the inventory transaction status</span></span>
1. <span data-ttu-id="7220e-127">Clique em Estoque.</span><span class="sxs-lookup"><span data-stu-id="7220e-127">Click Inventory.</span></span>
2. <span data-ttu-id="7220e-128">Clique em Transações.</span><span class="sxs-lookup"><span data-stu-id="7220e-128">Click Transactions.</span></span>
3. <span data-ttu-id="7220e-129">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="7220e-129">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="7220e-130">Observe que o campo de recebimento será definido como Encomendado.</span><span class="sxs-lookup"><span data-stu-id="7220e-130">Notice that the Receipt field is set to Ordered.</span></span>  
4. <span data-ttu-id="7220e-131">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="7220e-131">Close the page.</span></span>

## <a name="receive-items"></a><span data-ttu-id="7220e-132">Receber itens</span><span class="sxs-lookup"><span data-stu-id="7220e-132">Receive items</span></span>
1. <span data-ttu-id="7220e-133">Clique em Recebimento de produtos.</span><span class="sxs-lookup"><span data-stu-id="7220e-133">Click Product receipt.</span></span>
2. <span data-ttu-id="7220e-134">No campo Recebimento de produtos externos, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="7220e-134">In the External product receipt field, type a value.</span></span>
3. <span data-ttu-id="7220e-135">No campo quantidade, insira um número que é menor que o número que é mostrado.</span><span class="sxs-lookup"><span data-stu-id="7220e-135">In the Quantity field, enter a number that’s lower than the number that’s shown there.</span></span>
4. <span data-ttu-id="7220e-136">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="7220e-136">Click OK.</span></span>

## <a name="check-the-on-hand-inventory"></a><span data-ttu-id="7220e-137">Verifique o estoque disponível</span><span class="sxs-lookup"><span data-stu-id="7220e-137">Check the on-hand inventory</span></span>
1. <span data-ttu-id="7220e-138">Clique em Estoque.</span><span class="sxs-lookup"><span data-stu-id="7220e-138">Click Inventory.</span></span>
2. <span data-ttu-id="7220e-139">Clique em Disponível.</span><span class="sxs-lookup"><span data-stu-id="7220e-139">Click On-hand.</span></span>
3. <span data-ttu-id="7220e-140">Clique em Visão geral.</span><span class="sxs-lookup"><span data-stu-id="7220e-140">Click Overview.</span></span>
    * <span data-ttu-id="7220e-141">Os itens recebidos como o estoque de remessa possuído por fornecedor disponíveis disponível.</span><span class="sxs-lookup"><span data-stu-id="7220e-141">The items that have been received as consignment inventory owned by the vendor are available on-hand.</span></span> <span data-ttu-id="7220e-142">A quantidade pendente na ordem de reabastecimento de remessa é mostrada no campo total de Solicitado.</span><span class="sxs-lookup"><span data-stu-id="7220e-142">The remaining quantity on the consignment replenishment order is shown in the Ordered in total field.</span></span>  
4. <span data-ttu-id="7220e-143">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="7220e-143">Close the page.</span></span>
5. <span data-ttu-id="7220e-144">Clique em Fechar.</span><span class="sxs-lookup"><span data-stu-id="7220e-144">Click Close.</span></span>
