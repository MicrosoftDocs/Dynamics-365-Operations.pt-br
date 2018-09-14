--- 
title: Registrar o recebimento de mercadorias na ordem de compra
description: Este procedimento mostra como registrar o recebimento de mercadorias diretamente em uma ordem de compra.
author: FrankDahl
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: PurchTable, PurchCreateOrder, InventItemIdLookupPurchase, PurchEditLines
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: fdahl
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0312b8cfadd45f8e59225e9daba78b9e216cff51
ms.openlocfilehash: 14d1d43479f9864d8fd5ed94a98a654e75eeedf0
ms.contentlocale: pt-br
ms.lasthandoff: 09/14/2018

---
# <a name="record-the-receipt-of-goods-on-the-purchase-order"></a><span data-ttu-id="02006-103">Registrar o recebimento de mercadorias na ordem de compra</span><span class="sxs-lookup"><span data-stu-id="02006-103">Record the receipt of goods on the purchase order</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="02006-104">Este procedimento mostra como registrar o recebimento de mercadorias diretamente em uma ordem de compra.</span><span class="sxs-lookup"><span data-stu-id="02006-104">This procedure shows you how to record receipt of goods directly on a purchase order.</span></span> <span data-ttu-id="02006-105">Também é possível registrar o recebimento de produtos no depósito e, posteriormente, registrá-lo na ordem de compra.</span><span class="sxs-lookup"><span data-stu-id="02006-105">It’s also possible to register product receipt in the warehouse, and then later record it on the purchase order.</span></span> <span data-ttu-id="02006-106">Essa tarefa é normalmente executada por um agente de compras ou um coordenador de contas a pagar.</span><span class="sxs-lookup"><span data-stu-id="02006-106">This task is typically done by a purchasing agent or an accounts payable coordinator.</span></span> <span data-ttu-id="02006-107">O exemplo mostrado neste guia pode ser usado na empresa dos dados do programa demonstrativo de USMF.</span><span class="sxs-lookup"><span data-stu-id="02006-107">The example shown in this guide can be used in the USMF demo data company.</span></span> <span data-ttu-id="02006-108">O exemplo inclui etapas para criar uma ordem de compra simples de modo que você possa usar o procedimento como um guia da tarefa.</span><span class="sxs-lookup"><span data-stu-id="02006-108">The example includes steps to create a simple purchase order so that you can play the procedure as a task guide.</span></span> <span data-ttu-id="02006-109">Se você usava o procedimento em seus próprios dados, começaria na subtarefa Registrar recebimento de mercadorias.</span><span class="sxs-lookup"><span data-stu-id="02006-109">If you were using the procedure on your own data, you would start at the Record receipt of goods subtask.</span></span>


## <a name="prepare-a-new-purchase-order-for-receipt-of-goods"></a><span data-ttu-id="02006-110">Registrar o recebimento de mercadorias para uma linha da ordem de compra</span><span class="sxs-lookup"><span data-stu-id="02006-110">Prepare a new purchase order for receipt of goods</span></span>
1. <span data-ttu-id="02006-111">Vá para Aquisição e fornecimento > Ordens de compra > Todas as ordens de compra.</span><span class="sxs-lookup"><span data-stu-id="02006-111">Go to Procurement and sourcing > Purchase orders > All purchase orders.</span></span>
2. <span data-ttu-id="02006-112">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="02006-112">Click New.</span></span>
3. <span data-ttu-id="02006-113">No campo Conta de fornecedor, digite US-101.</span><span class="sxs-lookup"><span data-stu-id="02006-113">In the Vendor account field, enter US-101.</span></span>
4. <span data-ttu-id="02006-114">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="02006-114">Click OK.</span></span>
5. <span data-ttu-id="02006-115">No campo Número do item, insira M0001.</span><span class="sxs-lookup"><span data-stu-id="02006-115">In the Item number field, enter M0001.</span></span>
6. <span data-ttu-id="02006-116">No campo Quantidade, insira 5.</span><span class="sxs-lookup"><span data-stu-id="02006-116">In the Quantity field, enter 5.</span></span>
7. <span data-ttu-id="02006-117">No Painel de Ação, clique em Compra.</span><span class="sxs-lookup"><span data-stu-id="02006-117">On the Action Pane, click Purchase.</span></span>
8. <span data-ttu-id="02006-118">Clique em Confirmar.</span><span class="sxs-lookup"><span data-stu-id="02006-118">Click Confirm.</span></span>

## <a name="record-receipt-of-goods"></a><span data-ttu-id="02006-119">Registrar recebimento de mercadorias</span><span class="sxs-lookup"><span data-stu-id="02006-119">Record receipt of goods</span></span>
1. <span data-ttu-id="02006-120">No Painel de Ação, clique em Receber.</span><span class="sxs-lookup"><span data-stu-id="02006-120">On the Action Pane, click Receive.</span></span>
2. <span data-ttu-id="02006-121">Clique em Recebimento de produtos.</span><span class="sxs-lookup"><span data-stu-id="02006-121">Click Product receipt.</span></span>
    * <span data-ttu-id="02006-122">O campo Quantidade permite que você selecione opções diferentes para a quantidade que você quer receber.</span><span class="sxs-lookup"><span data-stu-id="02006-122">The Quantity field allows you to select different options for the quantity that you want to receive.</span></span> <span data-ttu-id="02006-123">Por exemplo, se uma quantidade foi registrada previamente no armazém, você pode selecionar a quantidade registrada.</span><span class="sxs-lookup"><span data-stu-id="02006-123">For example, if a quantity has previously been registered in the warehouse, you can select Registered quantity.</span></span>  <span data-ttu-id="02006-124">Para este exemplo, use o valor de Quantidade solicitada.</span><span class="sxs-lookup"><span data-stu-id="02006-124">For this example, use the value Ordered quantity.</span></span>   
3. <span data-ttu-id="02006-125">No campo Recebimento de produtos, digite qualquer valor.</span><span class="sxs-lookup"><span data-stu-id="02006-125">In the Product receipt field, type any value.</span></span>
    * <span data-ttu-id="02006-126">Este campo é usado para inserir uma referência que seja usada como comprovante do diário de recebimentos de produtos.</span><span class="sxs-lookup"><span data-stu-id="02006-126">This field is used to enter a reference that will be used as voucher for the product receipt journal.</span></span>  
4. <span data-ttu-id="02006-127">Expandir a seção Linhas.</span><span class="sxs-lookup"><span data-stu-id="02006-127">Expand the Lines section.</span></span>
5. <span data-ttu-id="02006-128">Defina a quantidade como '4'.</span><span class="sxs-lookup"><span data-stu-id="02006-128">Set Quantity to '4'.</span></span>
    * <span data-ttu-id="02006-129">Aqui você pode especificar manualmente a quantidade que está sendo recebida para cada linha na ordem.</span><span class="sxs-lookup"><span data-stu-id="02006-129">Here you are able to manually specify the quantity that is being received for each line on the order.</span></span>  
6. <span data-ttu-id="02006-130">Recolha a seção Linhas.</span><span class="sxs-lookup"><span data-stu-id="02006-130">Collapse the Lines section.</span></span>
7. <span data-ttu-id="02006-131">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="02006-131">Click OK.</span></span>
    * <span data-ttu-id="02006-132">As mercadorias foram agora registradas como recebidas na ordem de compra, e um diário de recebimentos de produtos foi criado como documento para refletir isto.</span><span class="sxs-lookup"><span data-stu-id="02006-132">The goods have now been recorded as received on the purchase order, and a product receipt journal has been created as document to reflect this.</span></span> <span data-ttu-id="02006-133">Você pode usar a ação de Recebimento de produtos para revisar os diários criados com a ordem de compra e ver o que foi recebido, e quando.</span><span class="sxs-lookup"><span data-stu-id="02006-133">You can use the Product receipt action to review the journals created with the purchase order, and see what was received, and when.</span></span>  


