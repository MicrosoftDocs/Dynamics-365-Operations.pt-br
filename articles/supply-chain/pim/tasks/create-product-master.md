---
title: Criar um produto mestre
description: Crie um produto mestre para as variáveis predefinidas.
author: ShylaThompson
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: EcoResProductListPage, EcoResProductCreate, EcoResProductDetails, EcoResProductInventoryDimensionGroups
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 70008e903763fff35c6cff12c42396fe5fcabbee
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5832073"
---
# <a name="create-a-product-master"></a><span data-ttu-id="daa03-103">Criar um produto mestre</span><span class="sxs-lookup"><span data-stu-id="daa03-103">Create a product master</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="daa03-104">Crie um produto mestre para as variáveis predefinidas.</span><span class="sxs-lookup"><span data-stu-id="daa03-104">Create a product master for the predefined variants.</span></span> <span data-ttu-id="daa03-105">A empresa de dados demo usada para criar este procedimento é USMF.</span><span class="sxs-lookup"><span data-stu-id="daa03-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="daa03-106">Este procedimento é voltado ao designer de produtos.</span><span class="sxs-lookup"><span data-stu-id="daa03-106">This procedure is intended for the product designer.</span></span>


## <a name="create-a-new-product-master"></a><span data-ttu-id="daa03-107">Criar um novo produto mestre</span><span class="sxs-lookup"><span data-stu-id="daa03-107">Create a new product master</span></span>
1. <span data-ttu-id="daa03-108">Vá para **Painel de navegação > Módulos > Gerenciamento de informações sobre produtos > Produtos > Produtos mestres**.</span><span class="sxs-lookup"><span data-stu-id="daa03-108">Go to **Navigation pane > Modules > Product information management > Products > Product masters**.</span></span>
2. <span data-ttu-id="daa03-109">Clique em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="daa03-109">Click **New**.</span></span>
3. <span data-ttu-id="daa03-110">No campo **Número do produto**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="daa03-110">In the **Product number** field, type a value.</span></span> <span data-ttu-id="daa03-111">O número deve ser exclusivo.</span><span class="sxs-lookup"><span data-stu-id="daa03-111">The number must be unique.</span></span> <span data-ttu-id="daa03-112">É possível definir uma sequência numérica para o campo **Número do produto**.</span><span class="sxs-lookup"><span data-stu-id="daa03-112">A number sequence can be set for the **Product number** field.</span></span> <span data-ttu-id="daa03-113">Nesse caso, o usuário não precisará inserir um valor.</span><span class="sxs-lookup"><span data-stu-id="daa03-113">In this case, the user doesn't have to enter a value.</span></span>
4. <span data-ttu-id="daa03-114">No campo **Nome do produto**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="daa03-114">In the **Product name** field, type a value.</span></span> <span data-ttu-id="daa03-115">Insira um nome de produto descritivo.</span><span class="sxs-lookup"><span data-stu-id="daa03-115">Enter a descriptive product name.</span></span> <span data-ttu-id="daa03-116">O valor será padronizada pelo nome de pesquisa, mas isso pode ser alterado pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="daa03-116">The value defaults to the search name, but this can be changed by the user.</span></span>
5. <span data-ttu-id="daa03-117">No campo **Grupo de dimensões do produto**, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="daa03-117">In the **Product dimension group** field, click the drop-down button to open the lookup.</span></span> <span data-ttu-id="daa03-118">O grupo de dimensões do produto determina quais das 4 dimensões do produto podem ser usadas para criar variantes do produto.</span><span class="sxs-lookup"><span data-stu-id="daa03-118">The product dimension group determines which of the 4 product dimensions that can be used to create product variants.</span></span> <span data-ttu-id="daa03-119">Este exemplo usa um grupo com cor e tamanho.</span><span class="sxs-lookup"><span data-stu-id="daa03-119">This example uses a group with color and size.</span></span>
6. <span data-ttu-id="daa03-120">Na lista, localize e selecione o registro desejado.</span><span class="sxs-lookup"><span data-stu-id="daa03-120">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="daa03-121">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="daa03-121">In the list, click the link in the selected row.</span></span> <span data-ttu-id="daa03-122">A **Tecnologia de configuração** padrão é 'Grade predefinida'.</span><span class="sxs-lookup"><span data-stu-id="daa03-122">The default **Configuration technology** is 'Predefined variant'.</span></span> <span data-ttu-id="daa03-123">Isso será usado neste exemplo.</span><span class="sxs-lookup"><span data-stu-id="daa03-123">This will be used for this example.</span></span>
8. <span data-ttu-id="daa03-124">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="daa03-124">Click **OK**.</span></span>

## <a name="select-product-dimension-groups"></a><span data-ttu-id="daa03-125">Selecionar os grupos de dimensão do produto</span><span class="sxs-lookup"><span data-stu-id="daa03-125">Select product dimension groups</span></span>
1. <span data-ttu-id="daa03-126">No campo **Grupo de cores**, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="daa03-126">In the **Color group** field, click the drop-down button to open the lookup.</span></span>
2. <span data-ttu-id="daa03-127">Na lista, localize e selecione o registro desejado.</span><span class="sxs-lookup"><span data-stu-id="daa03-127">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="daa03-128">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="daa03-128">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="daa03-129">No campo **Grupo de tamanhos**, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="daa03-129">In the **Size group** field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="daa03-130">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="daa03-130">In the list, find and select the desired record.</span></span>
6. <span data-ttu-id="daa03-131">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="daa03-131">In the list, click the link in the selected row.</span></span>

## <a name="add-dimension-groups"></a><span data-ttu-id="daa03-132">Adicionar grupos de dimensões</span><span class="sxs-lookup"><span data-stu-id="daa03-132">Add dimension groups</span></span>
1. <span data-ttu-id="daa03-133">No **Painel de Ação**, clique em **Produto**.</span><span class="sxs-lookup"><span data-stu-id="daa03-133">On the **Action Pane**, click **Product**.</span></span>
2. <span data-ttu-id="daa03-134">Clique em **Grupos de dimensões** para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="daa03-134">Click **Dimension groups** to open the drop dialog.</span></span>
3. <span data-ttu-id="daa03-135">No campo **Grupo de dimensões de armazenamento**, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="daa03-135">In the **Storage dimension group** field, click the drop-down button to open the lookup.</span></span> <span data-ttu-id="daa03-136">As dimensões de armazenamento ajudam a controlar como os itens são armazenados e retirados do estoque.</span><span class="sxs-lookup"><span data-stu-id="daa03-136">The storage dimensions help you control how items are stored and taken from inventory.</span></span> <span data-ttu-id="daa03-137">Por exemplo, uma dimensão de armazenamento pode incluir o Local e o Depósito.</span><span class="sxs-lookup"><span data-stu-id="daa03-137">For example, a storage dimension can include Site and Warehouse.</span></span>
4. <span data-ttu-id="daa03-138">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="daa03-138">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="daa03-139">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="daa03-139">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="daa03-140">No campo **Grupo de dimensões de rastreamento**, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="daa03-140">In the **Tracking dimension group** field, click the drop-down button to open the lookup.</span></span> <span data-ttu-id="daa03-141">O grupo de dimensões de rastreamento determina quais dimensões de rastreamento você pode adicionar a um produto.</span><span class="sxs-lookup"><span data-stu-id="daa03-141">The tracking dimension group determines which tracking dimensions you can add to a product.</span></span> <span data-ttu-id="daa03-142">Por exemplo, o número de lote e o número de série são usados para rastrear itens de estoque.</span><span class="sxs-lookup"><span data-stu-id="daa03-142">For example, the batch number and serial number are used to track inventory items.</span></span>
7. <span data-ttu-id="daa03-143">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="daa03-143">In the list, find and select the desired record.</span></span>
8. <span data-ttu-id="daa03-144">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="daa03-144">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="daa03-145">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="daa03-145">Click **OK**.</span></span>
10. <span data-ttu-id="daa03-146">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="daa03-146">Click **Save**.</span></span>
11. <span data-ttu-id="daa03-147">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="daa03-147">Close the page.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]