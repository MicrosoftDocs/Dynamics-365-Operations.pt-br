--- 
title: "Transferir estoque físico no depósito"
description: "Este procedimento aborda o processo de criação e lançamento de um diário de transferência de estoque para registrar a movimentação de um item de um local em um depósito para outro."
author: MarkusFogelberg
manager: AnnBe
ms.date: 8/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: InventJournalTransfer, InventJournalCreate, InventItemIdLookupSimple, InventLocationIdLookup, WMSLocationIdLookup, InventTrans
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mafoge
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 32d71167fdad65cb1dec37671999a497759ca484
ms.openlocfilehash: 41057d0a35cab122840a20a5c65ab7ae3133052c
ms.contentlocale: pt-br
ms.lasthandoff: 09/11/2018

---
# <a name="transfer-physical-inventory-within-the-warehouse"></a><span data-ttu-id="38580-103">Transferir estoque físico no depósito</span><span class="sxs-lookup"><span data-stu-id="38580-103">Transfer physical inventory within the warehouse</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="38580-104">Este procedimento aborda o processo de criação e lançamento de um diário de transferência de estoque para registrar a movimentação de um item de um local em um depósito para outro.</span><span class="sxs-lookup"><span data-stu-id="38580-104">This procedure walks you through the process of creating and posting an inventory transfer journal in order to register movement of an item from one location in a warehouse to another.</span></span> <span data-ttu-id="38580-105">Você precisa definir um nome de diário de estoque para transferências de estoque antes de criar este.</span><span class="sxs-lookup"><span data-stu-id="38580-105">You need to have an inventory journal name set up for inventory transfers before you start this.</span></span> <span data-ttu-id="38580-106">Você pode seguir esse procedimento na empresa de dados de demonstração USMF usando os valores do exemplo que são mostrados ou usando seus próprios dados se tiver produtos e locais configurados.</span><span class="sxs-lookup"><span data-stu-id="38580-106">You can walk through this procedure in demo data company USMF using the example values that are shown, or using you can use your own data if you have products and locations set up.</span></span> <span data-ttu-id="38580-107">Essas tarefas normalmente seriam realizadas por um funcionário do depósito.</span><span class="sxs-lookup"><span data-stu-id="38580-107">These tasks would normally be carried out by a warehouse employee.</span></span>


## <a name="create-an-inventory-transfer-journal"></a><span data-ttu-id="38580-108">Criar um diário de transferência de estoque</span><span class="sxs-lookup"><span data-stu-id="38580-108">Create an inventory transfer journal</span></span>
1. <span data-ttu-id="38580-109">Vá para Transferência.</span><span class="sxs-lookup"><span data-stu-id="38580-109">Go to Transfer.</span></span>
2. <span data-ttu-id="38580-110">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="38580-110">Click New.</span></span>
3. <span data-ttu-id="38580-111">No campo Nome, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="38580-111">In the Name field, enter or select a value.</span></span>
4. <span data-ttu-id="38580-112">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="38580-112">Click OK.</span></span>
    * <span data-ttu-id="38580-113">Há uma opção para especificar as dimensões 'De' e 'Para' de cada linha do diário.</span><span class="sxs-lookup"><span data-stu-id="38580-113">There is the option to specify 'From' and 'To' dimensions for each journal line.</span></span> <span data-ttu-id="38580-114">Elas são essenciais para esse tipo de diário.</span><span class="sxs-lookup"><span data-stu-id="38580-114">These are essential for this journal type.</span></span> <span data-ttu-id="38580-115">Você pode transferir os itens para localizações com diferentes regras.</span><span class="sxs-lookup"><span data-stu-id="38580-115">You can transfer items to locations using different rules.</span></span> <span data-ttu-id="38580-116">Neste exemplo, transferiremos um item, no mesmo depósito, de um local controlado por placa de licença a um local que não é controlado por placa de licença.</span><span class="sxs-lookup"><span data-stu-id="38580-116">In this example we’ll transfer an item within the same warehouse, from a license plate controlled location to a location that is not license plate controlled.</span></span>   

## <a name="create-journal-lines"></a><span data-ttu-id="38580-117">Criar linhas de diário</span><span class="sxs-lookup"><span data-stu-id="38580-117">Create journal lines</span></span>
1. <span data-ttu-id="38580-118">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="38580-118">Click New.</span></span>
2. <span data-ttu-id="38580-119">No campo Número do item, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="38580-119">In the Item number field, enter or select a value.</span></span>
    * <span data-ttu-id="38580-120">Se você estiver usando USMF, você pode selecionar 'A0001'.</span><span class="sxs-lookup"><span data-stu-id="38580-120">If you are using USMF, you can select 'A0001'.</span></span>  
3. <span data-ttu-id="38580-121">No campo Site de origem, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="38580-121">In the From site field, enter or select a value.</span></span>
    * <span data-ttu-id="38580-122">Se você estiver usando USMF, você pode selecionar '2'.</span><span class="sxs-lookup"><span data-stu-id="38580-122">If you are using USMF, you can select '2'.</span></span>  
4. <span data-ttu-id="38580-123">No campo Site de destino, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="38580-123">In the To site field, enter or select a value.</span></span>
    * <span data-ttu-id="38580-124">Se você estiver usando USMF, você pode selecionar '2'.</span><span class="sxs-lookup"><span data-stu-id="38580-124">If you are using USMF, you can select '2'.</span></span>  
5. <span data-ttu-id="38580-125">No campo Depósito de origem, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="38580-125">In the From warehouse field, enter or select a value.</span></span>
    * <span data-ttu-id="38580-126">Se você estiver usando USMF, você pode selecionar '24'.</span><span class="sxs-lookup"><span data-stu-id="38580-126">If you are using USMF, you can select '24'.</span></span>  
6. <span data-ttu-id="38580-127">No campo Depósito de destino, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="38580-127">In the To warehouse field, enter or select a value.</span></span>
    * <span data-ttu-id="38580-128">Se você estiver usando USMF, você pode selecionar '24'.</span><span class="sxs-lookup"><span data-stu-id="38580-128">If you are using USMF, you can select '24'.</span></span>  
7. <span data-ttu-id="38580-129">No campo Localização de origem, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="38580-129">In the From location field, enter or select a value.</span></span>
    * <span data-ttu-id="38580-130">Se você estiver usando USMF, você pode selecionar 'FL-001'.</span><span class="sxs-lookup"><span data-stu-id="38580-130">If you are using USMF, you can select 'FL-001'.</span></span>  
8. <span data-ttu-id="38580-131">No campo Local de destino, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="38580-131">In the To location field, enter or select a value.</span></span>
    * <span data-ttu-id="38580-132">Se você estiver usando USMF, você pode selecionar 'BULK-001'.</span><span class="sxs-lookup"><span data-stu-id="38580-132">If you are using USMF, you can select 'BULK-001'.</span></span>  
9. <span data-ttu-id="38580-133">No campo Quantidade, insira um número.</span><span class="sxs-lookup"><span data-stu-id="38580-133">In the Quantity field, enter a number.</span></span>
10. <span data-ttu-id="38580-134">Clique na guia Dimensões de estoque.</span><span class="sxs-lookup"><span data-stu-id="38580-134">Click the Inventory dimensions tab.</span></span>
11. <span data-ttu-id="38580-135">No campo Placa de licença, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="38580-135">In the License plate field, enter or select a value.</span></span>
    * <span data-ttu-id="38580-136">Se você estiver usando USMF, você pode selecionar '24'.</span><span class="sxs-lookup"><span data-stu-id="38580-136">If you are using USMF, you can select '24'.</span></span>  
12. <span data-ttu-id="38580-137">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="38580-137">Click Save.</span></span>

## <a name="post-the-inventory-transfer-journal"></a><span data-ttu-id="38580-138">Lançar o diário de transferência de estoque</span><span class="sxs-lookup"><span data-stu-id="38580-138">Post the inventory transfer journal</span></span>
1. <span data-ttu-id="38580-139">Clique em Lançar.</span><span class="sxs-lookup"><span data-stu-id="38580-139">Click Post.</span></span>
2. <span data-ttu-id="38580-140">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="38580-140">Click OK.</span></span>

## <a name="view-inventory-transactions"></a><span data-ttu-id="38580-141">Exibir transações de estoque</span><span class="sxs-lookup"><span data-stu-id="38580-141">View inventory transactions</span></span>
1. <span data-ttu-id="38580-142">Clique em Estoque.</span><span class="sxs-lookup"><span data-stu-id="38580-142">Click Inventory.</span></span>
2. <span data-ttu-id="38580-143">Clique em Transações.</span><span class="sxs-lookup"><span data-stu-id="38580-143">Click Transactions.</span></span>
    * <span data-ttu-id="38580-144">Aqui é possível ver as transações que foram criadas quando você lançou seu diário.</span><span class="sxs-lookup"><span data-stu-id="38580-144">Here you can see the transactions that were created when you posted your journal.</span></span>  


