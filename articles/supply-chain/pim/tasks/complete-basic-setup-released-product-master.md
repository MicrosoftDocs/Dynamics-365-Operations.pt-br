--- 
title: "Completar instalação básica de um produto mestre lançado"
description: "Este procedimento mostra como concluir a configuração mínima necessária antes que o produto mestre possa ser usado em versões de Listas de Materiais."
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: EcoResProductDetailsExtended, InventTableInventoryDimensionGroups, InventItemOrderSetup
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0312b8cfadd45f8e59225e9daba78b9e216cff51
ms.openlocfilehash: 0d3a91977c38c0ce0f9fe114bec943c7cb32a5d4
ms.contentlocale: pt-br
ms.lasthandoff: 09/14/2018

---
# <a name="complete-basic-setup-of-a-released-product-master"></a><span data-ttu-id="a3ebb-103">Completar instalação básica de um produto mestre lançado</span><span class="sxs-lookup"><span data-stu-id="a3ebb-103">Complete basic setup of a released product master</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="a3ebb-104">Este procedimento mostra como concluir a configuração mínima necessária antes que o produto mestre possa ser usado em versões de Listas de Materiais.</span><span class="sxs-lookup"><span data-stu-id="a3ebb-104">This procedure shows how to complete the minimum setup that is required before the product master can be used in BOM versions.</span></span>

<span data-ttu-id="a3ebb-105">Este é o terceiro procedimento dos oito que explicam como criar combinações para configuração baseada em dimensão.</span><span class="sxs-lookup"><span data-stu-id="a3ebb-105">This is the third procedure out of eight which explains how to build combinations for dimension-based configuration.</span></span> <span data-ttu-id="a3ebb-106">A empresa de dados demo usada para criar este procedimento é USMF.</span><span class="sxs-lookup"><span data-stu-id="a3ebb-106">The demo data company used to create this procedure is USMF.</span></span>

1. <span data-ttu-id="a3ebb-107">Vá para Gerenciamento de informações do produto > Produtos > Produtos liberados.</span><span class="sxs-lookup"><span data-stu-id="a3ebb-107">Go to Product information management > Products > Released products.</span></span>
2. <span data-ttu-id="a3ebb-108">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="a3ebb-108">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="a3ebb-109">Selecione o produto mestre que você liberou no segundo procedimento.</span><span class="sxs-lookup"><span data-stu-id="a3ebb-109">Select the product master that you have released in the second procedure.</span></span> <span data-ttu-id="a3ebb-110">Esse produto mestre foi criado com a tecnologia de configuração baseada em dimensão.</span><span class="sxs-lookup"><span data-stu-id="a3ebb-110">This product master is created with the dimension-based configuration technology.</span></span>  
3. <span data-ttu-id="a3ebb-111">No Painel de Ação, clique em Produto.</span><span class="sxs-lookup"><span data-stu-id="a3ebb-111">On the Action Pane, click Product.</span></span>
4. <span data-ttu-id="a3ebb-112">Clique em Grupos de dimensões para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="a3ebb-112">Click Dimension groups to open the drop dialog.</span></span>
5. <span data-ttu-id="a3ebb-113">No campo Grupo de dimensão de armazenamento, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="a3ebb-113">In the Storage dimension group field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="a3ebb-114">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="a3ebb-114">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="a3ebb-115">O grupo dimensões de armazenamento determina quais dimensões de armazenamento são usadas na transação do produto.</span><span class="sxs-lookup"><span data-stu-id="a3ebb-115">The storage dimension group determines which storage dimensions are used for product transaction.</span></span> <span data-ttu-id="a3ebb-116">Selecione Local para esse procedimento.</span><span class="sxs-lookup"><span data-stu-id="a3ebb-116">Select Site for this procedure.</span></span>  
7. <span data-ttu-id="a3ebb-117">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="a3ebb-117">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="a3ebb-118">No campo Grupo de dimensão de rastreamento, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="a3ebb-118">In the Tracking dimension group field, click the drop-down button to open the lookup.</span></span>
9. <span data-ttu-id="a3ebb-119">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="a3ebb-119">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="a3ebb-120">O grupo dimensões de rastreamento determina quais dimensões de rastreamento são usadas na transação do produto.</span><span class="sxs-lookup"><span data-stu-id="a3ebb-120">The tracking dimension group determines which tracking dimensions are used for product transaction.</span></span> <span data-ttu-id="a3ebb-121">Selecione Nenhum para esse procedimento.</span><span class="sxs-lookup"><span data-stu-id="a3ebb-121">Select None for this procedure.</span></span>  
10. <span data-ttu-id="a3ebb-122">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="a3ebb-122">In the list, click the link in the selected row.</span></span>
11. <span data-ttu-id="a3ebb-123">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="a3ebb-123">Click OK.</span></span>
12. <span data-ttu-id="a3ebb-124">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="a3ebb-124">In the list, click the link in the selected row.</span></span>
13. <span data-ttu-id="a3ebb-125">Clique em Editar.</span><span class="sxs-lookup"><span data-stu-id="a3ebb-125">Click Edit.</span></span>
    * <span data-ttu-id="a3ebb-126">Abra o formulário Detalhes do produto liberado para continuar a tarefa de configuração.</span><span class="sxs-lookup"><span data-stu-id="a3ebb-126">Open the Released product details form to continue the setup task.</span></span>  
14. <span data-ttu-id="a3ebb-127">No campo Grupo de modelo do item, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="a3ebb-127">In the Item model group field, click the drop-down button to open the lookup.</span></span>
15. <span data-ttu-id="a3ebb-128">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="a3ebb-128">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="a3ebb-129">Os grupos de modelo de item contêm configurações que determinam como os itens são controlados e processados em recebimentos e saídas.</span><span class="sxs-lookup"><span data-stu-id="a3ebb-129">Item model groups contain settings that determine how items are controlled and handled on item receipts and issues.</span></span> <span data-ttu-id="a3ebb-130">Eles também determinam como o consumo de itens é calculado.</span><span class="sxs-lookup"><span data-stu-id="a3ebb-130">They also determine how item consumption is calculated.</span></span> <span data-ttu-id="a3ebb-131">Selecione PEPS para esse procedimento.</span><span class="sxs-lookup"><span data-stu-id="a3ebb-131">Select   FIFO for this procedure.</span></span>  
16. <span data-ttu-id="a3ebb-132">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="a3ebb-132">In the list, click the link in the selected row.</span></span>
17. <span data-ttu-id="a3ebb-133">Expandir ou recolher a seção Gerenciar custos.</span><span class="sxs-lookup"><span data-stu-id="a3ebb-133">Expand or collapse the Manage costs section.</span></span>
18. <span data-ttu-id="a3ebb-134">No campo Grupo de item, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="a3ebb-134">In the Item group field, click the drop-down button to open the lookup.</span></span>
19. <span data-ttu-id="a3ebb-135">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="a3ebb-135">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="a3ebb-136">Os grupos de itens são usados para gerenciar o estoque, dividindo os itens de estoque em grupos.</span><span class="sxs-lookup"><span data-stu-id="a3ebb-136">Item groups are used to manage inventory by dividing inventory items into groups.</span></span> <span data-ttu-id="a3ebb-137">Selecione CarAudio para esse procedimento.</span><span class="sxs-lookup"><span data-stu-id="a3ebb-137">Select   CarAudio for this procedure.</span></span>  
20. <span data-ttu-id="a3ebb-138">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="a3ebb-138">In the list, click the link in the selected row.</span></span>
21. <span data-ttu-id="a3ebb-139">No Painel de Ação, clique em Plano.</span><span class="sxs-lookup"><span data-stu-id="a3ebb-139">On the Action Pane, click Plan.</span></span>
22. <span data-ttu-id="a3ebb-140">Clique em Configurações de ordem padrão.</span><span class="sxs-lookup"><span data-stu-id="a3ebb-140">Click Default order settings.</span></span>
23. <span data-ttu-id="a3ebb-141">No campo Tipo de ordem padrão, selecione uma opção.</span><span class="sxs-lookup"><span data-stu-id="a3ebb-141">In the Default order type field, select an option.</span></span>
    * <span data-ttu-id="a3ebb-142">Selecione Produção para especificar que a opção padrão de fornecimento para esse produto mestre é produzi-lo.</span><span class="sxs-lookup"><span data-stu-id="a3ebb-142">Select Production to specify that the default supply option for this product master is to produce it.</span></span>  
24. <span data-ttu-id="a3ebb-143">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="a3ebb-143">Close the page.</span></span>
25. <span data-ttu-id="a3ebb-144">Feche o formulário Detalhes do produto liberado.</span><span class="sxs-lookup"><span data-stu-id="a3ebb-144">Close the Released product details form.</span></span>


