---
title: Criar grades de produtos predefinidas
description: Este procedimento mostra como criar variantes de produto para um produto mestre que usam as combinações de dimensões do produto.
author: ShylaThompson
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EcoResProductListPage, EcoResProductCreate, EcoResProductDetails, EcoResProductMasterDimension, EcoResProductVariants, EcoResProductVariantSuggestions, EcoResProductVariantsPendingReleaseFormPart
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 6009f6de76155ea7c2982b28fe4505232447c9c8
ms.sourcegitcommit: 97d4a9bd442fe20f90605d8154c3a947c7645b37
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/28/2020
ms.locfileid: "3895296"
---
# <a name="create-predefined-product-variants"></a><span data-ttu-id="045b2-103">Criar grades de produtos predefinidas</span><span class="sxs-lookup"><span data-stu-id="045b2-103">Create predefined product variants</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="045b2-104">Este procedimento mostra como criar variantes de produto para um produto mestre que usam as combinações de dimensões do produto.</span><span class="sxs-lookup"><span data-stu-id="045b2-104">This procedure walks through creating product variants for a product master using the combinations of product dimensions.</span></span> <span data-ttu-id="045b2-105">A empresa de demonstração usada para criar este procedimento é USMF.</span><span class="sxs-lookup"><span data-stu-id="045b2-105">The demo company used to create this procedure is USMF.</span></span>


## <a name="create-a-product-master"></a><span data-ttu-id="045b2-106">Criar um produto mestre</span><span class="sxs-lookup"><span data-stu-id="045b2-106">Create a product master</span></span>
1. <span data-ttu-id="045b2-107">Vá para Gerenciamento de informações sobre produtos > Produtos > Produtos mestres.</span><span class="sxs-lookup"><span data-stu-id="045b2-107">Go to Product information management > Products > Product masters.</span></span>
2. <span data-ttu-id="045b2-108">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="045b2-108">Click New.</span></span>
3. <span data-ttu-id="045b2-109">No campo Número do produto, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="045b2-109">In the Product number field, type a value.</span></span>
    * <span data-ttu-id="045b2-110">Inserir um número de produto manualmente é apenas obrigatório se nenhuma sequência numérica foi configurada para o campo número do produto.</span><span class="sxs-lookup"><span data-stu-id="045b2-110">Entering a product number manually is only required if no number sequence has been set for the product number field.</span></span> <span data-ttu-id="045b2-111">Ou seja, ignore essa etapa se a sequência numérica foi definida para o campo.</span><span class="sxs-lookup"><span data-stu-id="045b2-111">In other words, skip the step if number sequence has been set for the field.</span></span>  
4. <span data-ttu-id="045b2-112">No campo Nome do produto, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="045b2-112">In the Product name field, type a value.</span></span>
5. <span data-ttu-id="045b2-113">No campo Grupo de dimensões de produto, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="045b2-113">In the Product dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="045b2-114">Selecione o grupo de dimensões do produto SizeCol (Tamanho e cor).</span><span class="sxs-lookup"><span data-stu-id="045b2-114">Select the product dimension group SizeCol (Size and Color).</span></span>  
6. <span data-ttu-id="045b2-115">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="045b2-115">Click OK.</span></span>

## <a name="add-product-dimensions"></a><span data-ttu-id="045b2-116">Adicionar dimensões do produto</span><span class="sxs-lookup"><span data-stu-id="045b2-116">Add product dimensions</span></span>
1. <span data-ttu-id="045b2-117">Clique em Dimensões de produto.</span><span class="sxs-lookup"><span data-stu-id="045b2-117">Click Product dimensions.</span></span>
    * <span data-ttu-id="045b2-118">Este exemplo a seguir mostra como inserir manualmente as dimensões do produto.</span><span class="sxs-lookup"><span data-stu-id="045b2-118">This example shows how to manually enter product dimensions.</span></span> <span data-ttu-id="045b2-119">Você pode escolher para selecionar um tamanho, cores ou estilos para o grupo que inclui os valores de dimensão de produto que deseja usar.</span><span class="sxs-lookup"><span data-stu-id="045b2-119">You can also choose to select a size, color or style group that includes the product dimension values you want to use.</span></span>  
2. <span data-ttu-id="045b2-120">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="045b2-120">Click New.</span></span>
3. <span data-ttu-id="045b2-121">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="045b2-121">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="045b2-122">No campo Tamanho, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="045b2-122">In the Size field, enter or select a value.</span></span>
5. <span data-ttu-id="045b2-123">No campo Nome, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="045b2-123">In the Name field, type a value.</span></span>
6. <span data-ttu-id="045b2-124">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="045b2-124">Click New.</span></span>
7. <span data-ttu-id="045b2-125">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="045b2-125">In the list, mark the selected row.</span></span>
8. <span data-ttu-id="045b2-126">No campo Tamanho, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="045b2-126">In the Size field, enter or select a value.</span></span>
9. <span data-ttu-id="045b2-127">No campo Nome, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="045b2-127">In the Name field, type a value.</span></span>
10. <span data-ttu-id="045b2-128">Clique na guia Cores.</span><span class="sxs-lookup"><span data-stu-id="045b2-128">Click the Colors tab.</span></span>
11. <span data-ttu-id="045b2-129">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="045b2-129">Click New.</span></span>
12. <span data-ttu-id="045b2-130">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="045b2-130">In the list, mark the selected row.</span></span>
13. <span data-ttu-id="045b2-131">No campo Cor, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="045b2-131">In the Color field, enter or select a value.</span></span>
14. <span data-ttu-id="045b2-132">No campo Nome, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="045b2-132">In the Name field, type a value.</span></span>
15. <span data-ttu-id="045b2-133">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="045b2-133">Click New.</span></span>
16. <span data-ttu-id="045b2-134">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="045b2-134">In the list, mark the selected row.</span></span>
17. <span data-ttu-id="045b2-135">No campo Cor, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="045b2-135">In the Color field, enter or select a value.</span></span>
18. <span data-ttu-id="045b2-136">No campo Nome, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="045b2-136">In the Name field, type a value.</span></span>
19. <span data-ttu-id="045b2-137">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="045b2-137">Click Save.</span></span>
20. <span data-ttu-id="045b2-138">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="045b2-138">Close the page.</span></span>

## <a name="generate-product-variants"></a><span data-ttu-id="045b2-139">Gerar grades de produtos</span><span class="sxs-lookup"><span data-stu-id="045b2-139">Generate product variants</span></span>
1. <span data-ttu-id="045b2-140">Clique em Grades de produtos.</span><span class="sxs-lookup"><span data-stu-id="045b2-140">Click Product variants.</span></span>
2. <span data-ttu-id="045b2-141">Clique em Sugestões de grade.</span><span class="sxs-lookup"><span data-stu-id="045b2-141">Click Variant suggestions.</span></span>
3. <span data-ttu-id="045b2-142">Clique em Selecionar tudo.</span><span class="sxs-lookup"><span data-stu-id="045b2-142">Click Select all.</span></span>
    * <span data-ttu-id="045b2-143">Neste exemplo, todas as grades possíveis são selecionadas.</span><span class="sxs-lookup"><span data-stu-id="045b2-143">In this example, all possible variants are selected.</span></span> <span data-ttu-id="045b2-144">Se somente um subconjunto de possíveis combinações de dimensões do produto for usado para criar grades, você pode selecionar as entradas individuais.</span><span class="sxs-lookup"><span data-stu-id="045b2-144">If only a subset of the possible product dimension combinations will be used to create variants, you can select the individual entries.</span></span>  
4. <span data-ttu-id="045b2-145">Clique em Criar.</span><span class="sxs-lookup"><span data-stu-id="045b2-145">Click Create.</span></span>
    * <span data-ttu-id="045b2-146">Você pode gerar descrições de todas as grades com base na combinação de valores de dimensão de produto.</span><span class="sxs-lookup"><span data-stu-id="045b2-146">You can generate descriptions for all your variants based on the combination of product dimension values.</span></span> <span data-ttu-id="045b2-147">As descrições são opcionais.</span><span class="sxs-lookup"><span data-stu-id="045b2-147">The descriptions are optional.</span></span>  
5. <span data-ttu-id="045b2-148">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="045b2-148">Click Save.</span></span>

