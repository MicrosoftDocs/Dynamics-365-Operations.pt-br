--- 
title: Criar um produto mestre
description: "Crie um produto mestre para as variáveis predefinidas."
author: YuyuScheller
manager: AnnBe
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.author: bis
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: fa2ea0f36f059b582b5e8658ffacde527425fcba
ms.contentlocale: pt-br
ms.lasthandoff: 05/08/2018

---
# <a name="create-a-product-master"></a><span data-ttu-id="df3b3-103">Criar um produto mestre</span><span class="sxs-lookup"><span data-stu-id="df3b3-103">Create a product master</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="df3b3-104">Crie um produto mestre para as variáveis predefinidas.</span><span class="sxs-lookup"><span data-stu-id="df3b3-104">Create a product master for the predefined variants.</span></span> <span data-ttu-id="df3b3-105">A empresa de dados demo usada para criar este procedimento é USMF.</span><span class="sxs-lookup"><span data-stu-id="df3b3-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="df3b3-106">Este procedimento é voltado ao designer de produtos.</span><span class="sxs-lookup"><span data-stu-id="df3b3-106">This procedure is intended for the product designer.</span></span>


## <a name="create-a-new-product-master"></a><span data-ttu-id="df3b3-107">Criar um novo produto mestre</span><span class="sxs-lookup"><span data-stu-id="df3b3-107">Create a new product master</span></span>
1. <span data-ttu-id="df3b3-108">Vá para Gerenciamento de informações sobre produtos > Produtos > Produtos mestres.</span><span class="sxs-lookup"><span data-stu-id="df3b3-108">Go to Product information management > Products > Product masters.</span></span>
2. <span data-ttu-id="df3b3-109">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="df3b3-109">Click New.</span></span>
3. <span data-ttu-id="df3b3-110">No campo Número do produto, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="df3b3-110">In the Product number field, type a value.</span></span>
    * <span data-ttu-id="df3b3-111">O número deve ser exclusivo.</span><span class="sxs-lookup"><span data-stu-id="df3b3-111">The number must be unique.</span></span> <span data-ttu-id="df3b3-112">Uma sequência numérica pode ser definida para o campo Número do produto.</span><span class="sxs-lookup"><span data-stu-id="df3b3-112">A number sequence can be set for the Product number field.</span></span> <span data-ttu-id="df3b3-113">Nesse caso, o usuário não precisará inserir um valor.</span><span class="sxs-lookup"><span data-stu-id="df3b3-113">In this case, the user doesn't have to enter a value.</span></span>  
4. <span data-ttu-id="df3b3-114">No campo Nome do produto, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="df3b3-114">In the Product name field, type a value.</span></span>
    * <span data-ttu-id="df3b3-115">Insira um nome de produto descritivo.</span><span class="sxs-lookup"><span data-stu-id="df3b3-115">Enter a descriptive product name.</span></span> <span data-ttu-id="df3b3-116">O valor será padronizada pelo nome de pesquisa, mas isso pode ser alterado pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="df3b3-116">The value defaults to the search name, but this can be changed by the user.</span></span>  
5. <span data-ttu-id="df3b3-117">No campo Grupo de dimensões do produto, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="df3b3-117">In the Product dimension group field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="df3b3-118">O grupo de dimensões do produto determina quais das 4 dimensões do produto podem ser usadas para criar variantes do produto.</span><span class="sxs-lookup"><span data-stu-id="df3b3-118">The product dimension group determines which of the 4 product dimensions that can be used to create product variants.</span></span> <span data-ttu-id="df3b3-119">Este exemplo usa um grupo com cor e tamanho.</span><span class="sxs-lookup"><span data-stu-id="df3b3-119">This example uses a group with color and size.</span></span>  
6. <span data-ttu-id="df3b3-120">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="df3b3-120">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="df3b3-121">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="df3b3-121">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="df3b3-122">A tecnologia de configuração padrão é Variável predefinida.</span><span class="sxs-lookup"><span data-stu-id="df3b3-122">The default configuration technology is Predefined variant.</span></span> <span data-ttu-id="df3b3-123">Isso será usado neste exemplo.</span><span class="sxs-lookup"><span data-stu-id="df3b3-123">This will be used for this example.</span></span>  
8. <span data-ttu-id="df3b3-124">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="df3b3-124">Click OK.</span></span>

## <a name="select-product-dimension-groups"></a><span data-ttu-id="df3b3-125">Selecionar os grupos de dimensão do produto</span><span class="sxs-lookup"><span data-stu-id="df3b3-125">Select product dimension groups</span></span>
1. <span data-ttu-id="df3b3-126">No campo Grupo de cores, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="df3b3-126">In the Color group field, click the drop-down button to open the lookup.</span></span>
2. <span data-ttu-id="df3b3-127">Na lista, localize e selecione o registro desejado.</span><span class="sxs-lookup"><span data-stu-id="df3b3-127">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="df3b3-128">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="df3b3-128">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="df3b3-129">No campo Grupo de tamanhos, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="df3b3-129">In the Size group field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="df3b3-130">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="df3b3-130">In the list, find and select the desired record.</span></span>
6. <span data-ttu-id="df3b3-131">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="df3b3-131">In the list, click the link in the selected row.</span></span>

## <a name="add-dimension-groups"></a><span data-ttu-id="df3b3-132">Adicionar grupos de dimensões</span><span class="sxs-lookup"><span data-stu-id="df3b3-132">Add dimension groups</span></span>
1. <span data-ttu-id="df3b3-133">No Painel de Ação, clique em Produto.</span><span class="sxs-lookup"><span data-stu-id="df3b3-133">On the Action Pane, click Product.</span></span>
2. <span data-ttu-id="df3b3-134">Clique em Grupos de dimensões para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="df3b3-134">Click Dimension groups to open the drop dialog.</span></span>
3. <span data-ttu-id="df3b3-135">No campo Grupo de dimensão de armazenamento, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="df3b3-135">In the Storage dimension group field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="df3b3-136">As dimensões de armazenamento ajudam a controlar como os itens são armazenados e retirados do estoque.</span><span class="sxs-lookup"><span data-stu-id="df3b3-136">The storage dimensions help you control how items are stored and taken from inventory.</span></span> <span data-ttu-id="df3b3-137">Por exemplo, uma dimensão de armazenamento pode incluir o Local e o Depósito.</span><span class="sxs-lookup"><span data-stu-id="df3b3-137">For example, a storage dimension can include Site and Warehouse.</span></span>  
4. <span data-ttu-id="df3b3-138">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="df3b3-138">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="df3b3-139">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="df3b3-139">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="df3b3-140">No campo Grupo de dimensão de rastreamento, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="df3b3-140">In the Tracking dimension group field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="df3b3-141">O grupo de dimensões de rastreamento determina quais dimensões de rastreamento você pode adicionar a um produto.</span><span class="sxs-lookup"><span data-stu-id="df3b3-141">The tracking dimension group determines which tracking dimensions you can add to a product.</span></span> <span data-ttu-id="df3b3-142">Por exemplo, o número de lote e o número de série são usados para rastrear itens de estoque.</span><span class="sxs-lookup"><span data-stu-id="df3b3-142">For example, the batch number and serial number are used to track inventory items.</span></span>  
7. <span data-ttu-id="df3b3-143">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="df3b3-143">In the list, find and select the desired record.</span></span>
8. <span data-ttu-id="df3b3-144">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="df3b3-144">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="df3b3-145">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="df3b3-145">Click OK.</span></span>
10. <span data-ttu-id="df3b3-146">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="df3b3-146">Click Save.</span></span>
11. <span data-ttu-id="df3b3-147">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="df3b3-147">Close the page.</span></span>


