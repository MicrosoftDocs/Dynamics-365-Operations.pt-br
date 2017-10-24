--- 
title: Criar um produto mestre
description: "Crie um produto mestre para as variáveis predefinidas."
author: BibiSp
manager: AnnBe
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.author: bis
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 4e8d438da1524850c115f5c38865fac2f19f3ff5
ms.contentlocale: pt-br
ms.lasthandoff: 09/29/2017

---
# <a name="create-a-product-master"></a><span data-ttu-id="ffa42-103">Criar um produto mestre</span><span class="sxs-lookup"><span data-stu-id="ffa42-103">Create a product master</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="ffa42-104">Crie um produto mestre para as variáveis predefinidas.</span><span class="sxs-lookup"><span data-stu-id="ffa42-104">Create a product master for the predefined variants.</span></span> <span data-ttu-id="ffa42-105">A empresa de dados demo usada para criar este procedimento é USMF.</span><span class="sxs-lookup"><span data-stu-id="ffa42-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="ffa42-106">Este procedimento é voltado ao designer de produtos.</span><span class="sxs-lookup"><span data-stu-id="ffa42-106">This procedure is intended for the product designer.</span></span>


## <a name="create-a-new-product-master"></a><span data-ttu-id="ffa42-107">Criar um novo produto mestre</span><span class="sxs-lookup"><span data-stu-id="ffa42-107">Create a new product master</span></span>
1. <span data-ttu-id="ffa42-108">Vá para Gerenciamento de informações sobre produtos > Produtos > Produtos mestres.</span><span class="sxs-lookup"><span data-stu-id="ffa42-108">Go to Product information management > Products > Product masters.</span></span>
2. <span data-ttu-id="ffa42-109">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="ffa42-109">Click New.</span></span>
3. <span data-ttu-id="ffa42-110">No campo Número do produto, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="ffa42-110">In the Product number field, type a value.</span></span>
    * <span data-ttu-id="ffa42-111">O número deve ser exclusivo.</span><span class="sxs-lookup"><span data-stu-id="ffa42-111">The number must be unique.</span></span> <span data-ttu-id="ffa42-112">Uma sequência numérica pode ser definida para o campo Número do produto.</span><span class="sxs-lookup"><span data-stu-id="ffa42-112">A number sequence can be set for the Product number field.</span></span> <span data-ttu-id="ffa42-113">Nesse caso, o usuário não precisará inserir um valor.</span><span class="sxs-lookup"><span data-stu-id="ffa42-113">In this case, the user doesn't have to enter a value.</span></span>  
4. <span data-ttu-id="ffa42-114">No campo Nome do produto, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="ffa42-114">In the Product name field, type a value.</span></span>
    * <span data-ttu-id="ffa42-115">Insira um nome de produto descritivo.</span><span class="sxs-lookup"><span data-stu-id="ffa42-115">Enter a descriptive product name.</span></span> <span data-ttu-id="ffa42-116">O valor será padronizada pelo nome de pesquisa, mas isso pode ser alterado pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="ffa42-116">The value defaults to the search name, but this can be changed by the user.</span></span>  
5. <span data-ttu-id="ffa42-117">No campo Grupo de dimensões do produto, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="ffa42-117">In the Product dimension group field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="ffa42-118">O grupo de dimensões do produto determina quais das 4 dimensões do produto podem ser usadas para criar variantes do produto.</span><span class="sxs-lookup"><span data-stu-id="ffa42-118">The product dimension group determines which of the 4 product dimensions that can be used to create product variants.</span></span> <span data-ttu-id="ffa42-119">Este exemplo usa um grupo com cor e tamanho.</span><span class="sxs-lookup"><span data-stu-id="ffa42-119">This example uses a group with color and size.</span></span>  
6. <span data-ttu-id="ffa42-120">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="ffa42-120">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="ffa42-121">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="ffa42-121">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="ffa42-122">A tecnologia de configuração padrão é Variável predefinida.</span><span class="sxs-lookup"><span data-stu-id="ffa42-122">The default configuration technology is Predefined variant.</span></span> <span data-ttu-id="ffa42-123">Isso será usado neste exemplo.</span><span class="sxs-lookup"><span data-stu-id="ffa42-123">This will be used for this example.</span></span>  
8. <span data-ttu-id="ffa42-124">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="ffa42-124">Click OK.</span></span>

## <a name="select-product-dimension-groups"></a><span data-ttu-id="ffa42-125">Selecionar os grupos de dimensão do produto</span><span class="sxs-lookup"><span data-stu-id="ffa42-125">Select product dimension groups</span></span>
1. <span data-ttu-id="ffa42-126">No campo Grupo de cores, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="ffa42-126">In the Color group field, click the drop-down button to open the lookup.</span></span>
2. <span data-ttu-id="ffa42-127">Na lista, localize e selecione o registro desejado.</span><span class="sxs-lookup"><span data-stu-id="ffa42-127">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="ffa42-128">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="ffa42-128">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="ffa42-129">No campo Grupo de tamanhos, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="ffa42-129">In the Size group field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="ffa42-130">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="ffa42-130">In the list, find and select the desired record.</span></span>
6. <span data-ttu-id="ffa42-131">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="ffa42-131">In the list, click the link in the selected row.</span></span>

## <a name="add-dimension-groups"></a><span data-ttu-id="ffa42-132">Adicionar grupos de dimensões</span><span class="sxs-lookup"><span data-stu-id="ffa42-132">Add dimension groups</span></span>
1. <span data-ttu-id="ffa42-133">No Painel de Ação, clique em Produto.</span><span class="sxs-lookup"><span data-stu-id="ffa42-133">On the Action Pane, click Product.</span></span>
2. <span data-ttu-id="ffa42-134">Clique em Grupos de dimensões para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="ffa42-134">Click Dimension groups to open the drop dialog.</span></span>
3. <span data-ttu-id="ffa42-135">No campo Grupo de dimensão de armazenamento, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="ffa42-135">In the Storage dimension group field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="ffa42-136">As dimensões de armazenamento ajudam a controlar como os itens são armazenados e retirados do estoque.</span><span class="sxs-lookup"><span data-stu-id="ffa42-136">The storage dimensions help you control how items are stored and taken from inventory.</span></span> <span data-ttu-id="ffa42-137">Por exemplo, uma dimensão de armazenamento pode incluir o Local e o Depósito.</span><span class="sxs-lookup"><span data-stu-id="ffa42-137">For example, a storage dimension can include Site and Warehouse.</span></span>  
4. <span data-ttu-id="ffa42-138">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="ffa42-138">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="ffa42-139">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="ffa42-139">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="ffa42-140">No campo Grupo de dimensão de rastreamento, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="ffa42-140">In the Tracking dimension group field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="ffa42-141">O grupo de dimensões de rastreamento determina quais dimensões de rastreamento você pode adicionar a um produto.</span><span class="sxs-lookup"><span data-stu-id="ffa42-141">The tracking dimension group determines which tracking dimensions you can add to a product.</span></span> <span data-ttu-id="ffa42-142">Por exemplo, o número de lote e o número de série são usados para rastrear itens de estoque.</span><span class="sxs-lookup"><span data-stu-id="ffa42-142">For example, the batch number and serial number are used to track inventory items.</span></span>  
7. <span data-ttu-id="ffa42-143">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="ffa42-143">In the list, find and select the desired record.</span></span>
8. <span data-ttu-id="ffa42-144">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="ffa42-144">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="ffa42-145">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="ffa42-145">Click OK.</span></span>
10. <span data-ttu-id="ffa42-146">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="ffa42-146">Click Save.</span></span>
11. <span data-ttu-id="ffa42-147">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="ffa42-147">Close the page.</span></span>


