---
title: Transferir estoque físico no depósito
description: Este procedimento aborda o processo de criação e lançamento de um diário de transferência de estoque para registrar a movimentação de um item de um local em um depósito para outro.
author: MarkusFogelberg
manager: tfehr
ms.date: 08/08/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventJournalTransfer, InventJournalCreate, InventItemIdLookupSimple, InventLocationIdLookup, WMSLocationIdLookup, InventTrans
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mafoge
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 540ba2266ea74c36babce57670f84159c89018f1
ms.sourcegitcommit: 8a2127c5af6cdbda30ccc1f9bef9bd4ab61e9e50
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/18/2020
ms.locfileid: "3383406"
---
# <a name="transfer-physical-inventory-within-the-warehouse"></a><span data-ttu-id="dfbae-103">Transferir estoque físico no depósito</span><span class="sxs-lookup"><span data-stu-id="dfbae-103">Transfer physical inventory within the warehouse</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="dfbae-104">Este procedimento aborda o processo de criação e lançamento de um diário de transferência de estoque para registrar a movimentação de um item de um local em um depósito para outro.</span><span class="sxs-lookup"><span data-stu-id="dfbae-104">This procedure walks you through the process of creating and posting an inventory transfer journal in order to register movement of an item from one location in a warehouse to another.</span></span> <span data-ttu-id="dfbae-105">Você precisa definir um nome de diário de estoque para transferências de estoque antes de criar este.</span><span class="sxs-lookup"><span data-stu-id="dfbae-105">You need to have an inventory journal name set up for inventory transfers before you start this.</span></span> <span data-ttu-id="dfbae-106">Você pode seguir esse procedimento na empresa de dados de demonstração USMF usando os valores do exemplo que são mostrados ou usando seus próprios dados se tiver produtos e locais configurados.</span><span class="sxs-lookup"><span data-stu-id="dfbae-106">You can walk through this procedure in demo data company USMF using the example values that are shown, or using you can use your own data if you have products and locations set up.</span></span> <span data-ttu-id="dfbae-107">Essas tarefas normalmente seriam realizadas por um funcionário do depósito.</span><span class="sxs-lookup"><span data-stu-id="dfbae-107">These tasks would normally be carried out by a warehouse employee.</span></span>


## <a name="create-an-inventory-transfer-journal"></a><span data-ttu-id="dfbae-108">Criar um diário de transferência de estoque</span><span class="sxs-lookup"><span data-stu-id="dfbae-108">Create an inventory transfer journal</span></span>
1. <span data-ttu-id="dfbae-109">No **Painel de navegação**, acesse **Gerenciamento de estoque > Entradas de diário > Itens > Transferência**.</span><span class="sxs-lookup"><span data-stu-id="dfbae-109">In the **Navigation pane**, go to **Inventory management > Journal entries > Items > Transfer**.</span></span>
2. <span data-ttu-id="dfbae-110">Clique em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="dfbae-110">Click **New**.</span></span>
3. <span data-ttu-id="dfbae-111">No campo **Nome**, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="dfbae-111">In the **Name** field, enter or select a value.</span></span>
4. <span data-ttu-id="dfbae-112">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="dfbae-112">Click **OK**.</span></span> <span data-ttu-id="dfbae-113">Há uma opção para especificar as dimensões 'De' e 'Para' de cada linha do diário.</span><span class="sxs-lookup"><span data-stu-id="dfbae-113">There is the option to specify 'From' and 'To' dimensions for each journal line.</span></span> <span data-ttu-id="dfbae-114">Elas são essenciais para esse tipo de diário.</span><span class="sxs-lookup"><span data-stu-id="dfbae-114">These are essential for this journal type.</span></span> <span data-ttu-id="dfbae-115">Você pode transferir os itens para localizações com diferentes regras.</span><span class="sxs-lookup"><span data-stu-id="dfbae-115">You can transfer items to locations using different rules.</span></span> <span data-ttu-id="dfbae-116">Neste exemplo, transferiremos um item, no mesmo depósito, de um local controlado por placa de licença a um local que não é controlado por placa de licença.</span><span class="sxs-lookup"><span data-stu-id="dfbae-116">In this example we'll transfer an item within the same warehouse, from a license plate controlled location to a location that is not license plate controlled.</span></span>   

## <a name="create-journal-lines"></a><span data-ttu-id="dfbae-117">Criar linhas do diário</span><span class="sxs-lookup"><span data-stu-id="dfbae-117">Create journal lines</span></span>
1. <span data-ttu-id="dfbae-118">Na Guia Rápida **Linhas do diário**, clique em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="dfbae-118">Int the **Journal lines fastTab**, click **New**.</span></span>
2. <span data-ttu-id="dfbae-119">No campo **Número do item**, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="dfbae-119">In the **Item number** field, enter or select a value.</span></span> <span data-ttu-id="dfbae-120">Se você estiver usando USMF, você pode selecionar 'A0001'.</span><span class="sxs-lookup"><span data-stu-id="dfbae-120">If you are using USMF, you can select 'A0001'.</span></span>  
3. <span data-ttu-id="dfbae-121">No campo **Site de origem**, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="dfbae-121">In the **From site** field, enter or select a value.</span></span> <span data-ttu-id="dfbae-122">Se você estiver usando USMF, você pode selecionar '2'.</span><span class="sxs-lookup"><span data-stu-id="dfbae-122">If you are using USMF, you can select '2'.</span></span>  
4. <span data-ttu-id="dfbae-123">No campo **Site de destino**, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="dfbae-123">In the **To site** field, enter or select a value.</span></span> <span data-ttu-id="dfbae-124">Se você estiver usando USMF, você pode selecionar '2'.</span><span class="sxs-lookup"><span data-stu-id="dfbae-124">If you are using USMF, you can select '2'.</span></span>  
5. <span data-ttu-id="dfbae-125">No campo **Depósito de origem**, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="dfbae-125">In the **From warehouse** field, enter or select a value.</span></span> <span data-ttu-id="dfbae-126">Se você estiver usando USMF, você pode selecionar '24'.</span><span class="sxs-lookup"><span data-stu-id="dfbae-126">If you are using USMF, you can select '24'.</span></span>  
6. <span data-ttu-id="dfbae-127">No campo **Depósito de destino**, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="dfbae-127">In the **To warehouse** field, enter or select a value.</span></span> <span data-ttu-id="dfbae-128">Se você estiver usando USMF, você pode selecionar '24'.</span><span class="sxs-lookup"><span data-stu-id="dfbae-128">If you are using USMF, you can select '24'.</span></span>  
7. <span data-ttu-id="dfbae-129">No campo **Localização de origem**, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="dfbae-129">In the **From location** field, enter or select a value.</span></span> <span data-ttu-id="dfbae-130">Se você estiver usando USMF, você pode selecionar 'FL-001'.</span><span class="sxs-lookup"><span data-stu-id="dfbae-130">If you are using USMF, you can select 'FL-001'.</span></span>  
8. <span data-ttu-id="dfbae-131">No campo **Local de destino**, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="dfbae-131">In the **To location** field, enter or select a value.</span></span> <span data-ttu-id="dfbae-132">Se você estiver usando USMF, você pode selecionar 'BULK-001'.</span><span class="sxs-lookup"><span data-stu-id="dfbae-132">If you are using USMF, you can select 'BULK-001'.</span></span>  
9. <span data-ttu-id="dfbae-133">No campo **Quantidade.**, insira um número</span><span class="sxs-lookup"><span data-stu-id="dfbae-133">In the **Quantity** field, enter a number.</span></span>
10. <span data-ttu-id="dfbae-134">Na Guia Rápida **Detalhes da linha**, clique na guia **Dimensões de estoque**.</span><span class="sxs-lookup"><span data-stu-id="dfbae-134">In the **Line details** fastTab, click the **Inventory dimensions** tab.</span></span>
11. <span data-ttu-id="dfbae-135">Em **Das dimensões de estoque**, no campo **Placa de licença**, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="dfbae-135">In **From inventory dimensions**, in the **License plate** field, enter or select a value.</span></span> <span data-ttu-id="dfbae-136">Se você estiver usando USMF, você pode selecionar '24'.</span><span class="sxs-lookup"><span data-stu-id="dfbae-136">If you are using USMF, you can select '24'.</span></span>  
12. <span data-ttu-id="dfbae-137">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="dfbae-137">Click **Save**.</span></span>

## <a name="post-the-inventory-transfer-journal"></a><span data-ttu-id="dfbae-138">Lançar o diário de transferência de estoque</span><span class="sxs-lookup"><span data-stu-id="dfbae-138">Post the inventory transfer journal</span></span>
1. <span data-ttu-id="dfbae-139">No **Painel de ações**, clique em **Lançar**.</span><span class="sxs-lookup"><span data-stu-id="dfbae-139">On the **Action Pane**, click **Post**.</span></span>
2. <span data-ttu-id="dfbae-140">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="dfbae-140">Click **OK**.</span></span>

## <a name="view-inventory-transactions"></a><span data-ttu-id="dfbae-141">Exibir transações de estoque</span><span class="sxs-lookup"><span data-stu-id="dfbae-141">View inventory transactions</span></span>
1. <span data-ttu-id="dfbae-142">Clique em **Estoque**.</span><span class="sxs-lookup"><span data-stu-id="dfbae-142">Click **Inventory**.</span></span>
2. <span data-ttu-id="dfbae-143">Clique em **Transações**.</span><span class="sxs-lookup"><span data-stu-id="dfbae-143">Click **Transactions**.</span></span> <span data-ttu-id="dfbae-144">Aqui é possível ver as transações que foram criadas quando você lançou seu diário.</span><span class="sxs-lookup"><span data-stu-id="dfbae-144">Here you can see the transactions that were created when you posted your journal.</span></span>  

