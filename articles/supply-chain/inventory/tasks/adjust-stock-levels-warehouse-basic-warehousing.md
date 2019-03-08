---
title: Ajustar níveis de estoque no depósito (armazenamento básico)
description: Esse procedimento o orientará no processo de criação e lançamento de um diário de ajuste de estoque para que os níveis de estoque de produtos no depósito sejam ajustados.
author: MarkusFogelberg
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventJournalLossProfit, InventJournalCreate, InventLocationIdLookup
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mafoge
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 330ebacf4a036b2df6ca22728477cae5b347354d
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2019
ms.locfileid: "317444"
---
# <a name="adjust-stock-levels-in-the-warehouse-basic-warehousing"></a><span data-ttu-id="6bd64-103">Ajustar níveis de estoque no depósito (armazenamento básico)</span><span class="sxs-lookup"><span data-stu-id="6bd64-103">Adjust stock levels in the warehouse (basic warehousing)</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="6bd64-104">Esse procedimento o orientará no processo de criação e lançamento de um diário de ajuste de estoque para que os níveis de estoque de produtos no depósito sejam ajustados.</span><span class="sxs-lookup"><span data-stu-id="6bd64-104">This procedure walks you through the process of creating and posting an inventory adjustment journal in order to adjust stock levels of products in the warehouse.</span></span> <span data-ttu-id="6bd64-105">Você precisa definir um nome de diário de estoque para ajustes de estoque antes de criar este.</span><span class="sxs-lookup"><span data-stu-id="6bd64-105">You need to have an inventory journal name set up for inventory adjustments before you start this.</span></span> <span data-ttu-id="6bd64-106">Você pode ver todo esse procedimento na empresa USMF de dados demo, ou usando seus próprios dados.</span><span class="sxs-lookup"><span data-stu-id="6bd64-106">You can walk through this procedure in demo data company USMF, or using your own data.</span></span> <span data-ttu-id="6bd64-107">Essas tarefas normalmente seriam realizadas por um funcionário do depósito.</span><span class="sxs-lookup"><span data-stu-id="6bd64-107">These tasks would normally be carried out by a warehouse employee.</span></span>


## <a name="create-an-inventory-adjustment-journal"></a><span data-ttu-id="6bd64-108">Criar um diário de ajuste de estoque</span><span class="sxs-lookup"><span data-stu-id="6bd64-108">Create an inventory adjustment journal</span></span>
1. <span data-ttu-id="6bd64-109">Vá para Gerenciamento de estoque > Entradas de diário > Itens > Ajuste de estoque.</span><span class="sxs-lookup"><span data-stu-id="6bd64-109">Go to Inventory management > Journal entries > Items > Inventory adjustment.</span></span>
2. <span data-ttu-id="6bd64-110">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="6bd64-110">Click New.</span></span>
3. <span data-ttu-id="6bd64-111">No campo Nome, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="6bd64-111">In the Name field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="6bd64-112">Na lista, clique no nome do diário de ajuste de estoque que deseja usar.</span><span class="sxs-lookup"><span data-stu-id="6bd64-112">In the list, click on the inventory adjustment journal name you want to use.</span></span>
    * <span data-ttu-id="6bd64-113">Alguns outros campos serão preenchidos com base na configuração do nome do diário de ajuste de estoque que você selecionar.</span><span class="sxs-lookup"><span data-stu-id="6bd64-113">Some other fields will be populated based on the setup of the inventory adjustment journal name you select.</span></span>  
5. <span data-ttu-id="6bd64-114">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="6bd64-114">Click OK.</span></span>

## <a name="create-journal-lines"></a><span data-ttu-id="6bd64-115">Criar linhas de diário</span><span class="sxs-lookup"><span data-stu-id="6bd64-115">Create journal lines</span></span>
1. <span data-ttu-id="6bd64-116">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="6bd64-116">Click New.</span></span>
2. <span data-ttu-id="6bd64-117">Na lista, marque o campo de número do item.</span><span class="sxs-lookup"><span data-stu-id="6bd64-117">In the list, mark the item number field.</span></span>
3. <span data-ttu-id="6bd64-118">No campo de número do item, selecione um item.</span><span class="sxs-lookup"><span data-stu-id="6bd64-118">In the Item number field, Select an item.</span></span> <span data-ttu-id="6bd64-119">Se estiver usando a empresa USMF de dados de demonstração, digite 'D0001'.</span><span class="sxs-lookup"><span data-stu-id="6bd64-119">If you are using demo data company USMF, type 'D0001'.</span></span>
4. <span data-ttu-id="6bd64-120">No campo Local, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="6bd64-120">In the Site field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="6bd64-121">Na lista, selecione um site.</span><span class="sxs-lookup"><span data-stu-id="6bd64-121">In the list, select a site.</span></span>
6. <span data-ttu-id="6bd64-122">No campo Depósito, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="6bd64-122">In the Warehouse field, click the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="6bd64-123">Na lista, selecione um depósito.</span><span class="sxs-lookup"><span data-stu-id="6bd64-123">In the list, select a warehouse.</span></span>
    * <span data-ttu-id="6bd64-124">Se já selecionou um item com Localização como dimensão obrigatória, você precisaria especificar a localização aqui.</span><span class="sxs-lookup"><span data-stu-id="6bd64-124">If you have selected an item with Location as a mandatory dimension, you would have to specify the location here.</span></span>  
8. <span data-ttu-id="6bd64-125">No campo Quantidade, insira um número.</span><span class="sxs-lookup"><span data-stu-id="6bd64-125">In the Quantity field, enter a number.</span></span>
    * <span data-ttu-id="6bd64-126">O campo de preço de custo especifica o custo por unidade para recebimentos de estoque.</span><span class="sxs-lookup"><span data-stu-id="6bd64-126">The cost price field specifies the cost per unit for inventory receipts.</span></span> <span data-ttu-id="6bd64-127">Se o custo não for especificado para o número do item ou se você pretendia alterá-lo manualmente, você poderia fazer isso aqui.</span><span class="sxs-lookup"><span data-stu-id="6bd64-127">If the cost is not specified for the item number or if you wanted to change it manually, you would do this here.</span></span>  

## <a name="validate-and-post-the-inventory-adjustment-journal"></a><span data-ttu-id="6bd64-128">Validar e lançar o diário de ajuste de estoque</span><span class="sxs-lookup"><span data-stu-id="6bd64-128">Validate and post the inventory adjustment journal</span></span>
1. <span data-ttu-id="6bd64-129">Clique em Validar.</span><span class="sxs-lookup"><span data-stu-id="6bd64-129">Click Validate.</span></span>
2. <span data-ttu-id="6bd64-130">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="6bd64-130">Click OK.</span></span>
3. <span data-ttu-id="6bd64-131">Clique em Lançar.</span><span class="sxs-lookup"><span data-stu-id="6bd64-131">Click Post.</span></span>
    * <span data-ttu-id="6bd64-132">Quando você lança esse tipo de diário, é lançado um recebimento ou uma saída de estoque, o nível de estoque e o valor são alterados e as transações do razão são geradas.</span><span class="sxs-lookup"><span data-stu-id="6bd64-132">When you post this kind of journal, an inventory receipt or issue is posted, the inventory level and value are changed, and ledger transactions are generated.</span></span>  
4. <span data-ttu-id="6bd64-133">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="6bd64-133">Click OK.</span></span>
5. <span data-ttu-id="6bd64-134">Feche o formulário.</span><span class="sxs-lookup"><span data-stu-id="6bd64-134">Close the form.</span></span>
6. <span data-ttu-id="6bd64-135">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="6bd64-135">Close the page.</span></span>

