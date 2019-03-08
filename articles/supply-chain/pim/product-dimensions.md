---
title: Dimensões do produto
description: Existem quatro dimensões do produto - Cor, Configuração, Tamanho e Estilo. Você combina dimensões de produto em grupos de dimensões e atribui grupos de dimensões a produtos mestres. As combinações de dimensões de produto determinam como as variantes de produto serão definidas.
author: cvocph
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EcoResProductDimension, EcoResProductDimensionGroup, EcoResProductMasterDimension, RetailEcoResColor, RetailEcoResSize, RetailEcoResStyle
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 19171
ms.assetid: 81fa3709-4ab8-4fbf-9806-359892a05985
ms.search.region: Global
ms.search.industry: Retail
ms.author: conradv
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ccb9d47bf6f081dbcc9590bddd4516cf7385ec23
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2019
ms.locfileid: "363283"
---
# <a name="product-dimensions"></a><span data-ttu-id="8a937-105">Dimensões do produto</span><span class="sxs-lookup"><span data-stu-id="8a937-105">Product dimensions</span></span>

[!include [banner](../includes/banner.md)]

[!include [Retail name](../includes/retail-name.md)]

<span data-ttu-id="8a937-106">Existem quatro dimensões do produto - Cor, Configuração, Tamanho e Estilo.</span><span class="sxs-lookup"><span data-stu-id="8a937-106">There are four product dimensions -  Color, Configuration, Size and Style.</span></span> <span data-ttu-id="8a937-107">Você combina dimensões de produto em grupos de dimensões e atribui grupos de dimensões a produtos mestres.</span><span class="sxs-lookup"><span data-stu-id="8a937-107">You combine product dimensions in dimension groups and assign dimension groups to product masters.</span></span> <span data-ttu-id="8a937-108">As combinações de dimensões de produto determinam como as variantes de produto serão definidas.</span><span class="sxs-lookup"><span data-stu-id="8a937-108">The combinations of product dimensions determine how product variants are defined.</span></span>

<span data-ttu-id="8a937-109">As dimensões de produto são as características que servem para identificar uma variante do produto.</span><span class="sxs-lookup"><span data-stu-id="8a937-109">Product dimensions are characteristics that serve to identify a product variant.</span></span> <span data-ttu-id="8a937-110">Você pode usar combinações de dimensões do produto para definir variantes de produto.</span><span class="sxs-lookup"><span data-stu-id="8a937-110">You can use combinations of product dimensions to define product variants.</span></span> <span data-ttu-id="8a937-111">Você deve definir pelo menos uma dimensão de produto para um produto mestre para criar uma variante do produto.</span><span class="sxs-lookup"><span data-stu-id="8a937-111">You must define at least one product dimension for a product master in order to create a product variant.</span></span>
<span data-ttu-id="8a937-112">Grades de produtos</span><span class="sxs-lookup"><span data-stu-id="8a937-112">Product variants</span></span>
----------------

<span data-ttu-id="8a937-113">As variantes dos produtos também são chamadas de itens.</span><span class="sxs-lookup"><span data-stu-id="8a937-113">Product variants are also referred to as items.</span></span> <span data-ttu-id="8a937-114">Um item é um produto real, que não é o mesmo que um serviço.</span><span class="sxs-lookup"><span data-stu-id="8a937-114">An item is a tangible product, which is not the same as a service.</span></span> <span data-ttu-id="8a937-115">Também é possível definir um produto mestre com o tipo Serviço.</span><span class="sxs-lookup"><span data-stu-id="8a937-115">It is also possible to define a product master with the Service type.</span></span> <span data-ttu-id="8a937-116">Usando o tipo de Serviço você poderá especificar as variantes de produtos que incluem serviços.</span><span class="sxs-lookup"><span data-stu-id="8a937-116">By using the Service type, you can specify product variants that include services.</span></span> <span data-ttu-id="8a937-117">Por exemplo, você pode especificar um produto mestre do serviço de consultoria e variantes de produtos para serviços que são realizados por consultores superiores e por consultores júnior.</span><span class="sxs-lookup"><span data-stu-id="8a937-117">For example, you can specify a product master for Consultancy work and product variants for work that is performed by senior consultants and junior consultants.</span></span>

## <a name="product-dimensions"></a><span data-ttu-id="8a937-118">Dimensões do produto</span><span class="sxs-lookup"><span data-stu-id="8a937-118">Product dimensions</span></span>
<span data-ttu-id="8a937-119">As dimensões de produto a seguir estão disponíveis: Configuração, Cor, Tamanho e Estilo.</span><span class="sxs-lookup"><span data-stu-id="8a937-119">The following product dimensions are available: Configuration, Color, Size, and Style.</span></span> <span data-ttu-id="8a937-120">Uma grade de produto pode ser gerada com base nos valores de dimensão de produto.</span><span class="sxs-lookup"><span data-stu-id="8a937-120">A product variant can be generated based on the product dimension values.</span></span>

<span data-ttu-id="8a937-121">Os valores das dimensões do produto como Tamanho, Cor e Estilo podem ser criados nas páginas **Tamanho**, **Cor** e **Estilo**, que podem ser acessadas dos seguintes locais **Gerenciamento de informações do produto** &gt; **Configuração** &gt; **Grupos de dimensões e variantes** &gt; **Tamanhos/Cores/Estilos**.</span><span class="sxs-lookup"><span data-stu-id="8a937-121">Product dimensions values such as Size, Color and Style can be created on the **Size**, **Color** and **Style** pages, which can be accessed from the following locations: **Product information management** &gt; **Setup** &gt; **Dimension and variant Groups** &gt; **Sizes/Colors/Styles**.</span></span> <span data-ttu-id="8a937-122">Os valores de dimensão do produto para a Dimensão de configuração, geralmente, são desenvolvidos usando o Configurador de produtos ou o Configurador com base na dimensão.</span><span class="sxs-lookup"><span data-stu-id="8a937-122">Product dimension values for the Configuration dimension are typically created using either the Product configurator or the Dimension-based configurator.</span></span> <span data-ttu-id="8a937-123">As dimensões do produto também podem ser criadas e mantidas na página **Dimensões do produto**, que podem ser acessadas dos seguintes locais:</span><span class="sxs-lookup"><span data-stu-id="8a937-123">Product dimensions can also be created and maintained on the **Product dimensions** page, which can be accessed from the following locations:</span></span>
-   <span data-ttu-id="8a937-124">Clique em **Gerenciamento de informações do produto** &gt; **Produtos** &gt; **Produtos mestres**.</span><span class="sxs-lookup"><span data-stu-id="8a937-124">Click **Product information management** &gt; **Products** &gt; **Product masters**.</span></span> <span data-ttu-id="8a937-125">No **Painel de Ação**, clique em **Dimensões do produto**.</span><span class="sxs-lookup"><span data-stu-id="8a937-125">On the **Action Pane**, click **Product dimensions**.</span></span>
-   <span data-ttu-id="8a937-126">Clique em **Gerenciamento de informações do produto** &gt; **Produtos** &gt; **Todos os produtos e produtos mestres**.</span><span class="sxs-lookup"><span data-stu-id="8a937-126">Click **Product information management** &gt; **Products** &gt; **All products and product masters**.</span></span> <span data-ttu-id="8a937-127">Selecione um produto mestre.</span><span class="sxs-lookup"><span data-stu-id="8a937-127">Select a product master.</span></span> <span data-ttu-id="8a937-128">No **Painel de Ação**, clique em **Dimensões do produto**.</span><span class="sxs-lookup"><span data-stu-id="8a937-128">On the **Action Pane**, click **Product dimensions**.</span></span>
-   <span data-ttu-id="8a937-129">Clique em **Gerenciamento de informações do produto** &gt; **Produtos liberados**.</span><span class="sxs-lookup"><span data-stu-id="8a937-129">Click **Product information management** &gt; **Released products**.</span></span> <span data-ttu-id="8a937-130">Selecione um produto mestre.</span><span class="sxs-lookup"><span data-stu-id="8a937-130">Select a product master.</span></span> <span data-ttu-id="8a937-131">No **Painel de Ação**, clique em **Produto**.</span><span class="sxs-lookup"><span data-stu-id="8a937-131">On the **Action Pane**, click **Product**.</span></span> <span data-ttu-id="8a937-132">No grupo de **Produto mestre**, clique em **Dimensões do produto**.</span><span class="sxs-lookup"><span data-stu-id="8a937-132">In the **Product master** group, click **Product dimensions**.</span></span>

<span data-ttu-id="8a937-133">O número de variantes que você pode criar para um item é limitado pelo número de possíveis combinações de dimensão do produto.</span><span class="sxs-lookup"><span data-stu-id="8a937-133">The number of variants that you can create for an item is limited by the number of possible product dimension combinations.</span></span>

| <span data-ttu-id="8a937-134">**Dica**</span><span class="sxs-lookup"><span data-stu-id="8a937-134">**Tip**</span></span>                                                                                                                                              |
|------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="8a937-135">Quando você usa um produto, por exemplo, em uma linha de ordem, você seleciona as dimensões do produto para identificar a variante do produto com a qual você deseja trabalhar.</span><span class="sxs-lookup"><span data-stu-id="8a937-135">When you use a product on, for example, an order line, you select the product dimensions to identify the product variant that you want to work with.</span></span> |

## <a name="example"></a><span data-ttu-id="8a937-136">Exemplo</span><span class="sxs-lookup"><span data-stu-id="8a937-136">Example</span></span>
<span data-ttu-id="8a937-137">Uma empresa vende jeans denim.</span><span class="sxs-lookup"><span data-stu-id="8a937-137">A company sells denim jeans.</span></span> <span data-ttu-id="8a937-138">O item, Jeans, usa as dimensões de Cor e de Tamanho do produto.</span><span class="sxs-lookup"><span data-stu-id="8a937-138">The item, Jeans, uses the Color and Size product dimensions.</span></span> <span data-ttu-id="8a937-139">Os jeans são vendidos em três cores diferentes e seis tamanhos diferentes.</span><span class="sxs-lookup"><span data-stu-id="8a937-139">The jeans are sold in three different colors and six different sizes.</span></span> <span data-ttu-id="8a937-140">Cores: Azul, Preto, Marrom - Tamanhos: PP, P, M, G, GG, GGG Nem todos estão disponíveis nas três cores.</span><span class="sxs-lookup"><span data-stu-id="8a937-140">Colors: Blue, Black, Brown Sizes: XS, S, M, L, XL, XXL Not all sizes are available in all the three colors.</span></span> <span data-ttu-id="8a937-141">Se todas as combinações estivessem disponíveis, seriam criados 18 tipos diferentes de jeans.</span><span class="sxs-lookup"><span data-stu-id="8a937-141">If all combinations were available, it would create 18 different types of jeans.</span></span> <span data-ttu-id="8a937-142">Neste exemplo, somente as nove combinações de variante de produto a seguir são produzidas.</span><span class="sxs-lookup"><span data-stu-id="8a937-142">In this example, only the following nine product variant combinations are produced.</span></span>

| <span data-ttu-id="8a937-143">Cor</span><span class="sxs-lookup"><span data-stu-id="8a937-143">Color</span></span> | <span data-ttu-id="8a937-144">Tamanho</span><span class="sxs-lookup"><span data-stu-id="8a937-144">Size</span></span> |
|-------|------|
| <span data-ttu-id="8a937-145">Azul</span><span class="sxs-lookup"><span data-stu-id="8a937-145">Blue</span></span>  | <span data-ttu-id="8a937-146">PP</span><span class="sxs-lookup"><span data-stu-id="8a937-146">XS</span></span>   |
| <span data-ttu-id="8a937-147">Azul</span><span class="sxs-lookup"><span data-stu-id="8a937-147">Blue</span></span>  | <span data-ttu-id="8a937-148">D</span><span class="sxs-lookup"><span data-stu-id="8a937-148">S</span></span>    |
| <span data-ttu-id="8a937-149">Azul</span><span class="sxs-lookup"><span data-stu-id="8a937-149">Blue</span></span>  | <span data-ttu-id="8a937-150">S</span><span class="sxs-lookup"><span data-stu-id="8a937-150">M</span></span>    |
| <span data-ttu-id="8a937-151">Preto</span><span class="sxs-lookup"><span data-stu-id="8a937-151">Black</span></span> | <span data-ttu-id="8a937-152">S</span><span class="sxs-lookup"><span data-stu-id="8a937-152">M</span></span>    |
| <span data-ttu-id="8a937-153">Preto</span><span class="sxs-lookup"><span data-stu-id="8a937-153">Black</span></span> | <span data-ttu-id="8a937-154">G</span><span class="sxs-lookup"><span data-stu-id="8a937-154">L</span></span>    |
| <span data-ttu-id="8a937-155">Preto</span><span class="sxs-lookup"><span data-stu-id="8a937-155">Black</span></span> | <span data-ttu-id="8a937-156">GG</span><span class="sxs-lookup"><span data-stu-id="8a937-156">XL</span></span>   |
| <span data-ttu-id="8a937-157">Marrom</span><span class="sxs-lookup"><span data-stu-id="8a937-157">Brown</span></span> | <span data-ttu-id="8a937-158">P</span><span class="sxs-lookup"><span data-stu-id="8a937-158">L</span></span>    |
| <span data-ttu-id="8a937-159">Marrom</span><span class="sxs-lookup"><span data-stu-id="8a937-159">Brown</span></span> | <span data-ttu-id="8a937-160">GG</span><span class="sxs-lookup"><span data-stu-id="8a937-160">XL</span></span>   |
| <span data-ttu-id="8a937-161">Marrom</span><span class="sxs-lookup"><span data-stu-id="8a937-161">Brown</span></span> | <span data-ttu-id="8a937-162">GGG</span><span class="sxs-lookup"><span data-stu-id="8a937-162">XXL</span></span>  |





