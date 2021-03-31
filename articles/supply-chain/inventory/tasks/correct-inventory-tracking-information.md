---
title: Corrigir informações de rastreamento de estoque
description: Este procedimento apresenta o processo de criação e lançamento de um diário de transferência de estoque para corrigir informações de rastreamento de estoque.
author: MarkusFogelberg
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventJournalTransfer, InventJournalCreate, InventItemIdLookupSimple, InventBatchIdLookup, InventLocationIdLookup, InventDimTracking, InventTrans
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mafoge
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 76e73f10df5bb520b6d0d787eda08053a5e33c81
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5223401"
---
# <a name="correct-inventory-tracking-information"></a><span data-ttu-id="60e90-103">Corrigir informações de rastreamento de estoque</span><span class="sxs-lookup"><span data-stu-id="60e90-103">Correct inventory tracking information</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="60e90-104">Este procedimento apresenta o processo de criação e lançamento de um diário de transferência de estoque para corrigir informações de rastreamento de estoque.</span><span class="sxs-lookup"><span data-stu-id="60e90-104">This procedure walks you through the process of creating and posting an inventory transfer journal in order to correct inventory tracking information.</span></span> <span data-ttu-id="60e90-105">Neste exemplo, vamos atualizar as informações de um item controlado por lote alterando um lote registrado incorretamente em outro lote.</span><span class="sxs-lookup"><span data-stu-id="60e90-105">In this example, we'll update the information of a batch controlled item by changing an incorrectly registered batch to another batch.</span></span> <span data-ttu-id="60e90-106">Você pode ver todo esse procedimento na empresa de dados de demonstração USPI, ou usando seus próprios dados.</span><span class="sxs-lookup"><span data-stu-id="60e90-106">You can walk through this procedure in demo data company USPI, or using your own data.</span></span> <span data-ttu-id="60e90-107">Se você usar seus próprios dados, precisará ter um item habilitado por lote, e não deve ser controlado por localização.</span><span class="sxs-lookup"><span data-stu-id="60e90-107">If you use your own data, you need to have an item that's batch-enabled, and it must not be location-controlled.</span></span> <span data-ttu-id="60e90-108">Você também precisa ter um nome do diário de estoque configurado para transferências de estoque.</span><span class="sxs-lookup"><span data-stu-id="60e90-108">You also need to have an inventory journal name set up for inventory transfers.</span></span> <span data-ttu-id="60e90-109">Essas tarefas normalmente seriam realizadas por um funcionário do depósito.</span><span class="sxs-lookup"><span data-stu-id="60e90-109">These tasks would normally be carried out by a warehouse employee.</span></span>


## <a name="create-an-inventory-transfer-journal"></a><span data-ttu-id="60e90-110">Criar um diário de transferência de estoque</span><span class="sxs-lookup"><span data-stu-id="60e90-110">Create an inventory transfer journal</span></span>
1. <span data-ttu-id="60e90-111">Vá para Transferência.</span><span class="sxs-lookup"><span data-stu-id="60e90-111">Go to Transfer.</span></span>
2. <span data-ttu-id="60e90-112">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="60e90-112">Click New.</span></span>
3. <span data-ttu-id="60e90-113">No campo Nome, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="60e90-113">In the Name field, enter or select a value.</span></span>
4. <span data-ttu-id="60e90-114">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="60e90-114">Click OK.</span></span>

## <a name="create-journal-lines"></a><span data-ttu-id="60e90-115">Criar linhas de diário</span><span class="sxs-lookup"><span data-stu-id="60e90-115">Create journal lines</span></span>
1. <span data-ttu-id="60e90-116">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="60e90-116">Click New.</span></span>
2. <span data-ttu-id="60e90-117">No campo Número do item, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="60e90-117">In the Item number field, enter or select a value.</span></span>
    * <span data-ttu-id="60e90-118">Se você estiver usando o USPI, selecione o item M5003.</span><span class="sxs-lookup"><span data-stu-id="60e90-118">If you are using USPI, select item M5003.</span></span>  
3. <span data-ttu-id="60e90-119">No campo Quantidade, insira um número.</span><span class="sxs-lookup"><span data-stu-id="60e90-119">In the Quantity field, enter a number.</span></span>
4. <span data-ttu-id="60e90-120">Clique na guia Dimensões de estoque.</span><span class="sxs-lookup"><span data-stu-id="60e90-120">Click the Inventory dimensions tab.</span></span>
5. <span data-ttu-id="60e90-121">No campo Número do lote, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="60e90-121">In the Batch number field, enter or select a value.</span></span>
6. <span data-ttu-id="60e90-122">No campo Local, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="60e90-122">In the Site field, enter or select a value.</span></span>
7. <span data-ttu-id="60e90-123">No campo Depósito, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="60e90-123">In the Warehouse field, enter or select a value.</span></span>
8. <span data-ttu-id="60e90-124">No campo Número do lote, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="60e90-124">In the Batch number field, enter or select a value.</span></span>

## <a name="post-the-journal"></a><span data-ttu-id="60e90-125">Lançar o diário</span><span class="sxs-lookup"><span data-stu-id="60e90-125">Post the journal</span></span>
1. <span data-ttu-id="60e90-126">Clique em Lançar.</span><span class="sxs-lookup"><span data-stu-id="60e90-126">Click Post.</span></span>
2. <span data-ttu-id="60e90-127">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="60e90-127">Click OK.</span></span>

## <a name="check-tracing-information"></a><span data-ttu-id="60e90-128">Verifique as informações de rastreamento</span><span class="sxs-lookup"><span data-stu-id="60e90-128">Check tracing information</span></span>
1. <span data-ttu-id="60e90-129">Clique em Estoque.</span><span class="sxs-lookup"><span data-stu-id="60e90-129">Click Inventory.</span></span>
2. <span data-ttu-id="60e90-130">Clique em Rastrear.</span><span class="sxs-lookup"><span data-stu-id="60e90-130">Click Trace.</span></span>
3. <span data-ttu-id="60e90-131">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="60e90-131">Click OK.</span></span>
    * <span data-ttu-id="60e90-132">Usando estas informações você pode rastrear novamente qual lote você corrigiu do estoque.</span><span class="sxs-lookup"><span data-stu-id="60e90-132">Using this tracing information you can back trace which batch you corrected inventory from.</span></span>  <span data-ttu-id="60e90-133">Você também pode usar a página de rastreamento do item para consultar essas informações.</span><span class="sxs-lookup"><span data-stu-id="60e90-133">You can also use the Item tracing page to see this information.</span></span>  
4. <span data-ttu-id="60e90-134">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="60e90-134">Close the page.</span></span>

## <a name="check-inventory-transactions"></a><span data-ttu-id="60e90-135">Verifique as transações de estoque</span><span class="sxs-lookup"><span data-stu-id="60e90-135">Check inventory transactions</span></span>
1. <span data-ttu-id="60e90-136">Clique em Estoque.</span><span class="sxs-lookup"><span data-stu-id="60e90-136">Click Inventory.</span></span>
2. <span data-ttu-id="60e90-137">Clique em Transações.</span><span class="sxs-lookup"><span data-stu-id="60e90-137">Click Transactions.</span></span>
    * <span data-ttu-id="60e90-138">Aqui é possível ver as transações que foram criadas quando você lançou seu diário.</span><span class="sxs-lookup"><span data-stu-id="60e90-138">Here you can see the transactions that were created when you posted your journal.</span></span>   



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]