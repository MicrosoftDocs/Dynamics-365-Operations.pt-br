---
title: "Contar estoque em um depósito"
description: "Este procedimento aborda o processo de criação e lançamento de um diário de contagem de estoque para que um item específico em um local do depósito seja contabilizado."
author: MarkusFogelberg
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mafoge
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0e7f66cccd76e5326fce75d1a13aff294c16fb9b
ms.openlocfilehash: fa72cb0d651f5e60797fa41f6e2b2cf1891730b5
ms.contentlocale: pt-br
ms.lasthandoff: 09/12/2017

---
# <a name="count-inventory-in-a-warehouse"></a><span data-ttu-id="37c87-103">Contar estoque em um depósito</span><span class="sxs-lookup"><span data-stu-id="37c87-103">Count inventory in a warehouse</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="37c87-104">Este procedimento aborda o processo de criação e lançamento de um diário de contagem de estoque para que um item específico em um local do depósito seja contabilizado.</span><span class="sxs-lookup"><span data-stu-id="37c87-104">This procedure walks you through the process of creating and posting an inventory counting journal in order to count a specific item at a location in the warehouse.</span></span> <span data-ttu-id="37c87-105">O procedimento é aplicado à funcionalidade de “armazenamento básico“, disponível no módulo Gerenciamento de estoque, não à funcionalidade de armazenamento que está disponível no módulo Gerenciamento de depósito.</span><span class="sxs-lookup"><span data-stu-id="37c87-105">The procedure applies to “basic warehousing” functionality, available in the Inventory management module, not to the warehousing functionality that’s available in the Warehouse management module.</span></span> <span data-ttu-id="37c87-106">Você pode ver todo esse procedimento na empresa USMF de dados demo, ou usando seus próprios dados.</span><span class="sxs-lookup"><span data-stu-id="37c87-106">You can walk through this procedure in demo data company USMF, or using your own data.</span></span> <span data-ttu-id="37c87-107">Se estiver usando seus próprios dados, certifique-se de que os produtos e localizações estão configurados e que você criou um nome de diário de estoque para diários de contagem.</span><span class="sxs-lookup"><span data-stu-id="37c87-107">If you’re using your own data, make sure that you have products and locations set up, and that you’ve created an inventory journal name for counting journals.</span></span> <span data-ttu-id="37c87-108">A contagem de estoque costuma ser realizada por um funcionário de depósito.</span><span class="sxs-lookup"><span data-stu-id="37c87-108">Inventory counting is normally carried out by a warehouse employee.</span></span>


## <a name="create-an-inventory-counting-journal"></a><span data-ttu-id="37c87-109">Criar diário de contagem de estoque</span><span class="sxs-lookup"><span data-stu-id="37c87-109">Create an inventory counting journal</span></span>
1. <span data-ttu-id="37c87-110">Vá para Gerenciamento de estoque > Entradas de diário > Contagem de itens > Contagem.</span><span class="sxs-lookup"><span data-stu-id="37c87-110">Go to Inventory management > Journal entries > Item counting > Counting.</span></span>
2. <span data-ttu-id="37c87-111">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="37c87-111">Click New.</span></span>
3. <span data-ttu-id="37c87-112">No campo Nome, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="37c87-112">In the Name field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="37c87-113">Na lista, clique no nome do diário de contagem de estoque que deseja usar</span><span class="sxs-lookup"><span data-stu-id="37c87-113">In the list, click on the inventory counting journal name you want to use</span></span>
    * <span data-ttu-id="37c87-114">Alguns outros campos serão preenchidos com base na configuração do nome do diário de contagem de estoque que você selecionar.</span><span class="sxs-lookup"><span data-stu-id="37c87-114">Some other fields will be populated based on the setup of the inventory counting journal name that you select.</span></span>  
5. <span data-ttu-id="37c87-115">No campo Trabalhador, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="37c87-115">In the Worker field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="37c87-116">Na lista, selecione o trabalhador que deseja utilizar.</span><span class="sxs-lookup"><span data-stu-id="37c87-116">In the list, select the worker you want to use.</span></span>
7. <span data-ttu-id="37c87-117">Clique em Selecionar.</span><span class="sxs-lookup"><span data-stu-id="37c87-117">Click Select.</span></span>
8. <span data-ttu-id="37c87-118">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="37c87-118">Click OK.</span></span>

## <a name="create-journal-lines"></a><span data-ttu-id="37c87-119">Criar linhas de diário</span><span class="sxs-lookup"><span data-stu-id="37c87-119">Create journal lines</span></span>
1. <span data-ttu-id="37c87-120">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="37c87-120">Click New.</span></span>
2. <span data-ttu-id="37c87-121">No campo Número de item, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="37c87-121">In the Item number field, click the drop-down button to open the lookup.</span></span>
3. <span data-ttu-id="37c87-122">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="37c87-122">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="37c87-123">Se estiver usando a empresa de dados de demonstração USMF, selecione 'A0001'.</span><span class="sxs-lookup"><span data-stu-id="37c87-123">If you are using demo data company USMF, select 'A0001'.</span></span>  
4. <span data-ttu-id="37c87-124">No campo Local, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="37c87-124">In the Site field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="37c87-125">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="37c87-125">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="37c87-126">Se estiver usando a empresa de dados de demonstração USMF, selecione o site '2'.</span><span class="sxs-lookup"><span data-stu-id="37c87-126">If you are using demo data company USMF, select site '2'.</span></span>  
6. <span data-ttu-id="37c87-127">No campo Depósito, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="37c87-127">In the Warehouse field, click the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="37c87-128">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="37c87-128">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="37c87-129">Se estiver usando a empresa de dados de demonstração USMF, selecione o depósito '24'.</span><span class="sxs-lookup"><span data-stu-id="37c87-129">If you are using demo data company USMF, select warehouse '24'.</span></span>  
8. <span data-ttu-id="37c87-130">No campo Localização, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="37c87-130">In the Location field, click the drop-down button to open the lookup.</span></span>
9. <span data-ttu-id="37c87-131">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="37c87-131">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="37c87-132">Se estiver usando a empresa de dados de demonstração USMF, selecione a localização 'BULK-001'.</span><span class="sxs-lookup"><span data-stu-id="37c87-132">If you are using demo data company USMF, select location 'BULK-001'</span></span>  
10. <span data-ttu-id="37c87-133">No campo Contado, insira um número.</span><span class="sxs-lookup"><span data-stu-id="37c87-133">In the Counted field, enter a number.</span></span>
    * <span data-ttu-id="37c87-134">Se você inserir um número contabilizado que é diferente do número mostrado no campo Disponível, o campo Quantidade é atualizado para mostrar a discrepância.</span><span class="sxs-lookup"><span data-stu-id="37c87-134">If you enter a counted number that’s different to the number shown in the On-hand field, the Quantity field is updated to show the discrepancy.</span></span>  
11. <span data-ttu-id="37c87-135">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="37c87-135">Click Save.</span></span>

## <a name="post-the-inventory-counting-journal"></a><span data-ttu-id="37c87-136">Lançar o diário de contagem de estoque</span><span class="sxs-lookup"><span data-stu-id="37c87-136">Post the inventory counting journal</span></span>
1. <span data-ttu-id="37c87-137">Clique em Lançar.</span><span class="sxs-lookup"><span data-stu-id="37c87-137">Click Post.</span></span>
    * <span data-ttu-id="37c87-138">Ao lançar um diário de contagem de estoque, se o valor contabilizado diferir do valor informado no campo Disponível, um recebimento ou emissão de estoque é lançado, o nível e o valor do estoque são alterados e as transações do razão são geradas.</span><span class="sxs-lookup"><span data-stu-id="37c87-138">When you post an inventory counting journal, if the counted amount differs from amount that’s reported in the On-hand field an inventory receipt or issue is posted, the inventory level and value are changed, and ledger transactions are generated.</span></span>  
2. <span data-ttu-id="37c87-139">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="37c87-139">Click OK.</span></span>

## <a name="view-inventory-transactions"></a><span data-ttu-id="37c87-140">Exibir transações de estoque</span><span class="sxs-lookup"><span data-stu-id="37c87-140">View inventory transactions</span></span>
1. <span data-ttu-id="37c87-141">Clique em Estoque.</span><span class="sxs-lookup"><span data-stu-id="37c87-141">Click Inventory.</span></span>
2. <span data-ttu-id="37c87-142">Clique em Transações.</span><span class="sxs-lookup"><span data-stu-id="37c87-142">Click Transactions.</span></span>
    * <span data-ttu-id="37c87-143">Aqui é possível ver qualquer transação relacionada que será criada quando você lançar seu diário de contagem de estoque.</span><span class="sxs-lookup"><span data-stu-id="37c87-143">Here you can see any related transactions that will be created when you post your inventory counting journal.</span></span>   

