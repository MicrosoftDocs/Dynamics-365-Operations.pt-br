---
title: Inicializar níveis de estoque no depósito
description: Esse procedimento mostra como obter o estoque disponível atualizado manualmente usando um diário de movimentação de estoque.
author: perlynne
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventJournalMovement, InventJournalCreate, InventItemIdLookupSimple, InventLocationIdLookup, WMSLocationIdLookup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 6934fc8142a589532cbd9d360ca0f8276456b20e
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "5011538"
---
# <a name="initialize-stock-levels-in-the-warehouse"></a><span data-ttu-id="6a8e8-103">Inicializar níveis de estoque no depósito</span><span class="sxs-lookup"><span data-stu-id="6a8e8-103">Initialize stock levels in the warehouse</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="6a8e8-104">Esse procedimento mostra como obter o estoque disponível atualizado manualmente usando um diário de movimentação de estoque.</span><span class="sxs-lookup"><span data-stu-id="6a8e8-104">This procedure shows you how to get the on-hand inventory updated manually using an Inventory movement journal.</span></span> <span data-ttu-id="6a8e8-105">(Também é possível atualizar o estoque disponível importando transações em entidades de dados.) Você pode executar esse guia na empresa de dados de demonstração USMF na qual estão disponíveis todos os pré-requisitos, como nome do diário, configuração do item, perfis de lançamento e contas.</span><span class="sxs-lookup"><span data-stu-id="6a8e8-105">(It's also possible to update on-hand inventory by importing transactions in data entities.) You can run this guide in demo data company USMF where all the prerequisites like journal name, item setup, posting profiles, and accounts are available.</span></span> <span data-ttu-id="6a8e8-106">Esse guia sugere valores específicos para o item e as dimensões que são usados.</span><span class="sxs-lookup"><span data-stu-id="6a8e8-106">The guide suggests specific values for the item and dimensions that are used.</span></span> <span data-ttu-id="6a8e8-107">Se selecionar um item diferente, você talvez precise inserir valores para diferentes dimensões.</span><span class="sxs-lookup"><span data-stu-id="6a8e8-107">If you choose a different item, you may need to enter values for different dimensions.</span></span>

1. <span data-ttu-id="6a8e8-108">Vá para Gerenciamento de estoque > Entradas de diário > Itens > Movimento.</span><span class="sxs-lookup"><span data-stu-id="6a8e8-108">Go to Inventory management > Journal entries > Items > Movement.</span></span>
2. <span data-ttu-id="6a8e8-109">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="6a8e8-109">Click New.</span></span>
3. <span data-ttu-id="6a8e8-110">No campo Nome, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="6a8e8-110">In the Name field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="6a8e8-111">Selecione IMov.</span><span class="sxs-lookup"><span data-stu-id="6a8e8-111">Select IMov.</span></span>
    * <span data-ttu-id="6a8e8-112">É uma boa prática usar modelos de nomes de diários diferentes para fins comerciais diferentes.</span><span class="sxs-lookup"><span data-stu-id="6a8e8-112">It's a good practice to use different journal name templates for the different business purposes.</span></span>  
5. <span data-ttu-id="6a8e8-113">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="6a8e8-113">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="6a8e8-114">No campo Contrapartida, especifique os valores '140200'.</span><span class="sxs-lookup"><span data-stu-id="6a8e8-114">In the Offset account field, specify the values '140200'.</span></span>
    * <span data-ttu-id="6a8e8-115">Essa contrapartida será a conta padrão nas linhas do diário.</span><span class="sxs-lookup"><span data-stu-id="6a8e8-115">This is the offset account that will be the default account on the journal lines.</span></span> <span data-ttu-id="6a8e8-116">É possível substituir o padrão para atribuir contrapartidas diferentes por linha.</span><span class="sxs-lookup"><span data-stu-id="6a8e8-116">It's possible to override the default to assign different offset accounts per line.</span></span>  
7. <span data-ttu-id="6a8e8-117">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="6a8e8-117">Click OK.</span></span>
8. <span data-ttu-id="6a8e8-118">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="6a8e8-118">Click New.</span></span>
9. <span data-ttu-id="6a8e8-119">No campo Número de item, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="6a8e8-119">In the Item number field, click the drop-down button to open the lookup.</span></span>
10. <span data-ttu-id="6a8e8-120">Selecione o item A0001.</span><span class="sxs-lookup"><span data-stu-id="6a8e8-120">Select item A0001.</span></span>
11. <span data-ttu-id="6a8e8-121">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="6a8e8-121">In the list, click the link in the selected row.</span></span>
12. <span data-ttu-id="6a8e8-122">Clique na guia Dimensões de estoque.</span><span class="sxs-lookup"><span data-stu-id="6a8e8-122">Click the Inventory dimensions tab.</span></span>
13. <span data-ttu-id="6a8e8-123">No campo Local, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="6a8e8-123">In the Site field, click the drop-down button to open the lookup.</span></span>
14. <span data-ttu-id="6a8e8-124">Selecione site 1.</span><span class="sxs-lookup"><span data-stu-id="6a8e8-124">Select site 1.</span></span>
15. <span data-ttu-id="6a8e8-125">No campo Depósito, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="6a8e8-125">In the Warehouse field, click the drop-down button to open the lookup.</span></span>
16. <span data-ttu-id="6a8e8-126">Selecione depósito 13.</span><span class="sxs-lookup"><span data-stu-id="6a8e8-126">Select warehouse 13.</span></span>
17. <span data-ttu-id="6a8e8-127">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="6a8e8-127">In the list, click the link in the selected row.</span></span>
18. <span data-ttu-id="6a8e8-128">No campo Localização, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="6a8e8-128">In the Location field, click the drop-down button to open the lookup.</span></span>
19. <span data-ttu-id="6a8e8-129">Selecione localização 13.</span><span class="sxs-lookup"><span data-stu-id="6a8e8-129">Select location 13.</span></span>
20. <span data-ttu-id="6a8e8-130">No campo Quantidade, insira um número.</span><span class="sxs-lookup"><span data-stu-id="6a8e8-130">In the Quantity field, enter a number.</span></span>
21. <span data-ttu-id="6a8e8-131">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="6a8e8-131">Click Save.</span></span>
22. <span data-ttu-id="6a8e8-132">Clique em Lançar.</span><span class="sxs-lookup"><span data-stu-id="6a8e8-132">Click Post.</span></span>
23. <span data-ttu-id="6a8e8-133">Marque ou desmarque a caixa de seleção Transferir todos os erros de lançamento para um novo diário.</span><span class="sxs-lookup"><span data-stu-id="6a8e8-133">Check or uncheck the Transfer all posting errors to a new journal check box.</span></span>
    * <span data-ttu-id="6a8e8-134">Se essa opção for habilitada, qualquer linha que não puder ser lançada será copiada em um novo diário.</span><span class="sxs-lookup"><span data-stu-id="6a8e8-134">If you enable this option, any lines that fail to post will be copied to a new journal.</span></span> <span data-ttu-id="6a8e8-135">Você pode usar as informações no log para corrigir os problemas e relançar as linhas.</span><span class="sxs-lookup"><span data-stu-id="6a8e8-135">You can use the information in the log to correct the issues and then re-post the lines.</span></span>  
24. <span data-ttu-id="6a8e8-136">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="6a8e8-136">Click OK.</span></span>
25. <span data-ttu-id="6a8e8-137">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="6a8e8-137">Close the page.</span></span>
26. <span data-ttu-id="6a8e8-138">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="6a8e8-138">Close the page.</span></span>

