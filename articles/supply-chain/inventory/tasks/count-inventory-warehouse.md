---
title: Contar estoque em um depósito
description: Este tópico descreve o processo de criação e lançamento de um diário de contagem de estoque para que um item específico em um local do depósito seja contabilizado.
author: MarkusFogelberg
manager: AnnBe
ms.date: 07/09/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventJournalCount, InventJournalCreate, HcmWorkerLookUp, InventItemIdLookupSimple, InventLocationIdLookup, WMSLocationIdLookup, InventTrans
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mafoge
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 53e9457074b696efaf5958b3a3b4616f06f5a6ff
ms.sourcegitcommit: fcb27d6a46cd544feef34f6ec7607bdd46b0c12b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/18/2020
ms.locfileid: "3145746"
---
# <a name="count-inventory-in-a-warehouse"></a><span data-ttu-id="5759a-103">Contar estoque em um depósito</span><span class="sxs-lookup"><span data-stu-id="5759a-103">Count inventory in a warehouse</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="5759a-104">Este tópico descreve o processo de criação e lançamento de um diário de contagem de estoque para que um item específico em um local do depósito seja contabilizado.</span><span class="sxs-lookup"><span data-stu-id="5759a-104">This topic describes the process of creating and posting an inventory counting journal in order to count a specific item at a location in the warehouse.</span></span> <span data-ttu-id="5759a-105">O procedimento é aplicado à funcionalidade de "armazenamento básico", disponível no módulo Gerenciamento de estoque, não à funcionalidade de armazenamento que está disponível no módulo Gerenciamento de depósito.</span><span class="sxs-lookup"><span data-stu-id="5759a-105">The procedure applies to "basic warehousing" functionality, available in the Inventory management module, not to the warehousing functionality that's available in the Warehouse management module.</span></span> <span data-ttu-id="5759a-106">Você pode ver todo esse procedimento na empresa USMF de dados demo, ou usando seus próprios dados.</span><span class="sxs-lookup"><span data-stu-id="5759a-106">You can walk through this procedure in demo data company USMF, or using your own data.</span></span> <span data-ttu-id="5759a-107">Se estiver usando seus próprios dados, certifique-se de que os produtos e localizações estão configurados e que você criou um nome de diário de estoque para diários de contagem.</span><span class="sxs-lookup"><span data-stu-id="5759a-107">If you're using your own data, make sure that you have products and locations set up, and that you've created an inventory journal name for counting journals.</span></span> <span data-ttu-id="5759a-108">A contagem de estoque costuma ser realizada por um funcionário de depósito.</span><span class="sxs-lookup"><span data-stu-id="5759a-108">Inventory counting is normally carried out by a warehouse employee.</span></span>


## <a name="create-an-inventory-counting-journal"></a><span data-ttu-id="5759a-109">Criar diário de contagem de estoque</span><span class="sxs-lookup"><span data-stu-id="5759a-109">Create an inventory counting journal</span></span>
1. <span data-ttu-id="5759a-110">Vá para **Painel de navegação > Módulos > Gerenciamento de estoque > Entradas de diário > Contagem de itens > Contagem**.</span><span class="sxs-lookup"><span data-stu-id="5759a-110">Go to **Navigation pane > Modules > Inventory management > Journal entries > Item counting > Counting**.</span></span>
2. <span data-ttu-id="5759a-111">Selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="5759a-111">Select **New**.</span></span>
3. <span data-ttu-id="5759a-112">No campo **Nome** , selecione o nome de diário de contagem de estoque a ser usado na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="5759a-112">In the **Name** field, select the inventory counting journal name you want to use from the drop-down list.</span></span> <span data-ttu-id="5759a-113">Alguns outros campos serão preenchidos com base na configuração do nome do diário de contagem de estoque que você selecionar.</span><span class="sxs-lookup"><span data-stu-id="5759a-113">Some other fields will be populated based on the setup of the inventory counting journal name that you select.</span></span>  
4. <span data-ttu-id="5759a-114">No campo **Trabalhador**, selecione o botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="5759a-114">In the **Worker** field, select the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="5759a-115">Na lista, **Selecionar** o trabalhador que você deseja utilizar.</span><span class="sxs-lookup"><span data-stu-id="5759a-115">In the list, **Select** the worker you want to use.</span></span>
6. <span data-ttu-id="5759a-116">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="5759a-116">Select **OK**.</span></span>

## <a name="create-journal-lines"></a><span data-ttu-id="5759a-117">Criar linhas do diário</span><span class="sxs-lookup"><span data-stu-id="5759a-117">Create journal lines</span></span>
1. <span data-ttu-id="5759a-118">Selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="5759a-118">Select **New**.</span></span>
2. <span data-ttu-id="5759a-119">No campo **Número do item**, selecione o registro desejado na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="5759a-119">In the **Item number** field, select the desired record from the drop-down list.</span></span> <span data-ttu-id="5759a-120">Se estiver usando a empresa de dados de demonstração USMF, selecione **A0001**.</span><span class="sxs-lookup"><span data-stu-id="5759a-120">If you are using demo data company USMF, select **A0001**.</span></span>  
3. <span data-ttu-id="5759a-121">No campo **Site**, selecione o registro desejado na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="5759a-121">In the **Site** field, select the desired record from the drop-down list.</span></span> <span data-ttu-id="5759a-122">Se estiver usando a empresa de dados de demonstração USMF, selecione o site **2**.</span><span class="sxs-lookup"><span data-stu-id="5759a-122">If you are using demo data company USMF, select site **2**.</span></span>
4. <span data-ttu-id="5759a-123">No campo **Depósito**, selecione o registro desejado na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="5759a-123">In the **Warehouse** field, select the desired record from the drop-down list.</span></span> <span data-ttu-id="5759a-124">Se estiver usando a empresa de dados de demonstração USMF, selecione o depósito **24**.</span><span class="sxs-lookup"><span data-stu-id="5759a-124">If you are using demo data company USMF, select warehouse **24**.</span></span>  
5. <span data-ttu-id="5759a-125">No campo **Local**, selecione o registro desejado na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="5759a-125">In the **Location** field, select the desired record from the drop-down list.</span></span> <span data-ttu-id="5759a-126">Se estiver usando a empresa de dados de demonstração USMF, selecione o local **BULK-001**.</span><span class="sxs-lookup"><span data-stu-id="5759a-126">If you are using demo data company USMF, select location **BULK-001**.</span></span>  
6. <span data-ttu-id="5759a-127">No campo Contado, insira um número.</span><span class="sxs-lookup"><span data-stu-id="5759a-127">In the Counted field, enter a number.</span></span> <span data-ttu-id="5759a-128">Se você inserir um número contabilizado que é diferente do número mostrado no campo **Disponível**, o campo **Quantidade** será atualizado para mostrar a discrepância.</span><span class="sxs-lookup"><span data-stu-id="5759a-128">If you enter a counted number that's different to the number shown in the **On-hand** field, the **Quantity** field is updated to show the discrepancy.</span></span>  
7. <span data-ttu-id="5759a-129">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="5759a-129">Select **Save**.</span></span>

## <a name="post-the-inventory-counting-journal"></a><span data-ttu-id="5759a-130">Lançar o diário de contagem de estoque</span><span class="sxs-lookup"><span data-stu-id="5759a-130">Post the inventory counting journal</span></span>
1. <span data-ttu-id="5759a-131">Selecione **Lançar**.</span><span class="sxs-lookup"><span data-stu-id="5759a-131">Select **Post**.</span></span> <span data-ttu-id="5759a-132">Ao lançar um diário de contagem de estoque, se o valor contabilizado diferir do valor informado no campo **Disponível**, um recebimento ou emissão de estoque será lançado, o nível e o valor do estoque serão alterados e as transações do razão serão geradas.</span><span class="sxs-lookup"><span data-stu-id="5759a-132">When you post an inventory counting journal, if the counted amount differs from amount that's reported in the **On-hand** field an inventory receipt or issue is posted, the inventory level and value are changed, and ledger transactions are generated.</span></span>
2. <span data-ttu-id="5759a-133">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="5759a-133">Select **OK**.</span></span>

## <a name="view-inventory-transactions"></a><span data-ttu-id="5759a-134">Exibir transações de estoque</span><span class="sxs-lookup"><span data-stu-id="5759a-134">View inventory transactions</span></span>
1. <span data-ttu-id="5759a-135">Selecione **Estoque**.</span><span class="sxs-lookup"><span data-stu-id="5759a-135">Select **Inventory**.</span></span>
2. <span data-ttu-id="5759a-136">Selecione **Transações**.</span><span class="sxs-lookup"><span data-stu-id="5759a-136">Select **Transactions**.</span></span> <span data-ttu-id="5759a-137">Aqui é possível ver qualquer transação relacionada que será criada quando você lançar seu diário de contagem de estoque.</span><span class="sxs-lookup"><span data-stu-id="5759a-137">Here you can see any related transactions that will be created when you post your inventory counting journal.</span></span>   

