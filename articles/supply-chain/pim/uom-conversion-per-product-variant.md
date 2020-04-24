---
title: Conversão de unidade de medida por variante de produto
description: Este tópico explica como as conversões de unidade de medida podem ser configuradas em grades do produto.
author: johanhoffmann
manager: tfehr
ms.date: 01/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: UnitOfMeasureConversion
ROBOTS: noindex, nofollow
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-04-01
ms.dyn365.ops.version: 10
ms.openlocfilehash: e50be7fa6fa686a90b2dd5c5200c881e4629f019
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/02/2020
ms.locfileid: "3204484"
---
# <a name="unit-of-measure-conversion-per-product-variant"></a><span data-ttu-id="34fa3-103">Conversão de unidade de medida por variante de produto</span><span class="sxs-lookup"><span data-stu-id="34fa3-103">Unit of measure conversion per product variant</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="34fa3-104">Este tópico explica como as conversões de unidade de medida podem ser configuradas em grades do produto.</span><span class="sxs-lookup"><span data-stu-id="34fa3-104">This topic explains how unit of measure conversions can be set up on product variants.</span></span> <span data-ttu-id="34fa3-105">Ele iInclui um exemplo da instalação.</span><span class="sxs-lookup"><span data-stu-id="34fa3-105">It includes an example of the setup.</span></span>

<span data-ttu-id="34fa3-106">Esse recurso permite que as empresas definam a conversão de unidades diferentes entre as grades do mesmo produto.</span><span class="sxs-lookup"><span data-stu-id="34fa3-106">This feature makes it possible for companies to define different unit conversion between the variants of the same product.</span></span> <span data-ttu-id="34fa3-107">O exemplo a seguir é usado neste tópico.</span><span class="sxs-lookup"><span data-stu-id="34fa3-107">The following example is used in this topic.</span></span> <span data-ttu-id="34fa3-108">Uma empresa vende camisetas nos tamanhos pequeno, médio, grande e extra grande.</span><span class="sxs-lookup"><span data-stu-id="34fa3-108">A company sells T-shirts in sizes Small, Medium, Large, and Extra-Large.</span></span> <span data-ttu-id="34fa3-109">A camiseta é definida como um produto; os diferentes tamanhos são definidos como grades do produto.</span><span class="sxs-lookup"><span data-stu-id="34fa3-109">The T-shirt is defined as a product, and the different sizes are defined as variants of the product.</span></span> <span data-ttu-id="34fa3-110">As camisetas são embaladas em caixas e uma caixa pode conter cinco camisetas, exceto no tamanho extra grande, em que há espaço para apenas quatro camisetas.</span><span class="sxs-lookup"><span data-stu-id="34fa3-110">The T-shirts are packed in boxes and there can be five T-shirts in a box, except for the Extra-Large size where there is only space for four T-shirts.</span></span> <span data-ttu-id="34fa3-111">A empresa deseja rastrear as diferentes grades das camisetas na unidade em **Peças** mas está vendendo as camisetas na unidade **Caixas**.</span><span class="sxs-lookup"><span data-stu-id="34fa3-111">The company wants to track the different variants of the T-shirts in the unit **Pieces** but is selling the T-shirts in the unit **Boxes**.</span></span> <span data-ttu-id="34fa3-112">A conversão entre a unidade de estoque e a unidade de venda é 1 caixa = 5 peças, exceto para a grade extra grande, onde a conversão é 1 caixa = 4 peças.</span><span class="sxs-lookup"><span data-stu-id="34fa3-112">The conversion between the inventory unit and the sales unit is 1 Box = 5 Pieces, except for the variant Extra-Large, where the conversion is 1 Box = 4 Pieces.</span></span>

### <a name="set-up-a-product-for-unit-conversion-per-variant"></a><span data-ttu-id="34fa3-113">Configurar um produto para a conversão de unidade por grade</span><span class="sxs-lookup"><span data-stu-id="34fa3-113">Set up a product for unit conversion per variant</span></span>

<span data-ttu-id="34fa3-114">Grades de produto só podem ser criadas para o **Subtipo de produto**: **Produto mestre**.</span><span class="sxs-lookup"><span data-stu-id="34fa3-114">Product variants can only be created for products of **Product subtype**: **Product master**.</span></span> <span data-ttu-id="34fa3-115">Para obter mais informações, consulte [Criar um produto mestre](tasks/create-product-master.md).</span><span class="sxs-lookup"><span data-stu-id="34fa3-115">For more information, see [Create a product master](tasks/create-product-master.md).</span></span>

<span data-ttu-id="34fa3-116">O recurso não está habilitado para produtos configurados para processos de peso variável.</span><span class="sxs-lookup"><span data-stu-id="34fa3-116">The feature is not enabled for products that are set up for Catch Weight processes.</span></span> 

<span data-ttu-id="34fa3-117">Quando o produto mestre com grades de produtos liberados for criado, as conversões de unidade por grades poderão ser configuradas.</span><span class="sxs-lookup"><span data-stu-id="34fa3-117">When the product master with released products variants is created, unit conversions per variants can be set up.</span></span> <span data-ttu-id="34fa3-118">Você pode encontrar o item de menu para abrir a página de conversão de unidade no contexto de um produto ou de uma grade de produtos nas páginas a seguir.</span><span class="sxs-lookup"><span data-stu-id="34fa3-118">You can find the menu item for opening the unit conversion page in context of a product or a product variant on the following pages.</span></span>

-   <span data-ttu-id="34fa3-119">Página **Detalhes de produto**</span><span class="sxs-lookup"><span data-stu-id="34fa3-119">**Product details** page</span></span>
-   <span data-ttu-id="34fa3-120">Página **Detalhes de produtos liberados**</span><span class="sxs-lookup"><span data-stu-id="34fa3-120">**Released products details** page</span></span>
-   <span data-ttu-id="34fa3-121">Página **Grades de produtos liberados**</span><span class="sxs-lookup"><span data-stu-id="34fa3-121">**Released product variants** page</span></span>

<span data-ttu-id="34fa3-122">Quando você abre a página **Conversão de unidades** no contexto de um produto mestre ou de uma grade de produtos liberados, pode selecionar se deseja configurar a conversão de unidade para o produto ou para uma grade de produtos.</span><span class="sxs-lookup"><span data-stu-id="34fa3-122">When you open the **Unit conversion** page in context of a product master or released product variant, you can select if you want to set up the unit conversion for the product or for a product variant.</span></span> <span data-ttu-id="34fa3-123">Para fazer isso, selecione **Grade de produto** ou **Produto** no campo **Criar conversão para**.</span><span class="sxs-lookup"><span data-stu-id="34fa3-123">You do that by selecting either **Product variant** or **Product** in the **Create conversion for** field.</span></span>

### <a name="product-variant"></a><span data-ttu-id="34fa3-124">Grade de produto</span><span class="sxs-lookup"><span data-stu-id="34fa3-124">Product variant</span></span>

<span data-ttu-id="34fa3-125">Se você selecionar **Grade de produto**, poderá selecionar para que grade deseja configurar a conversão de unidade no campo **Grade de produto**.</span><span class="sxs-lookup"><span data-stu-id="34fa3-125">If you select **Product variant,** then you can select for which variant you want to set up the unit conversion in the **Product variant** field.</span></span>

### <a name="product"></a><span data-ttu-id="34fa3-126">Produto</span><span class="sxs-lookup"><span data-stu-id="34fa3-126">Product</span></span>

<span data-ttu-id="34fa3-127">Se você selecionar **Produto**, poderá configurar uma conversão de unidade para os produtos mestres.</span><span class="sxs-lookup"><span data-stu-id="34fa3-127">If you select **Product**, then you can set up a unit conversion for the product master.</span></span> <span data-ttu-id="34fa3-128">Essa conversão de unidade será aplicada a todas as grades de produtos sem uma conversão de unidades definida.</span><span class="sxs-lookup"><span data-stu-id="34fa3-128">This unit conversion will apply for all product variants with no defined unit conversion.</span></span>

### <a name="example"></a><span data-ttu-id="34fa3-129">Exemplo</span><span class="sxs-lookup"><span data-stu-id="34fa3-129">Example</span></span>

<span data-ttu-id="34fa3-130">Um produto mestre, **Camiseta**, tem quatro grades de produtos liberadas, pequeno, médio, grande e extra grande.</span><span class="sxs-lookup"><span data-stu-id="34fa3-130">A product master, **T-Shirt**, has four released products variants Small, Medium, Large, and X-Large.</span></span> <span data-ttu-id="34fa3-131">As camisetas são embaladas em caixas e uma caixa pode conter cinco camisetas, exceto no tamanho extra grande, em que há espaço para apenas quatro camisetas.</span><span class="sxs-lookup"><span data-stu-id="34fa3-131">The T-shirts are packed in boxes and there can be five T-shirts in a box, except for the Extra-large size where there is only space for four T-shirts.</span></span>

<span data-ttu-id="34fa3-132">Primeiro, abra a página **Conversão de unidades** da página Detalhes de produtos liberados para **Camiseta**.</span><span class="sxs-lookup"><span data-stu-id="34fa3-132">First, open the **Unit conversion** page from the Release product details page for **T-shirt.**</span></span>

<span data-ttu-id="34fa3-133">Na página **Conversão de unidades**, configure a conversão de unidades para a grade de produtos liberados Extra Grande.</span><span class="sxs-lookup"><span data-stu-id="34fa3-133">On the **Unit conversion** page, set up the unit conversion for the release product variant X-Large.</span></span>

| <span data-ttu-id="34fa3-134">**Campo**</span><span class="sxs-lookup"><span data-stu-id="34fa3-134">**Field**</span></span>             | <span data-ttu-id="34fa3-135">**Configuração**</span><span class="sxs-lookup"><span data-stu-id="34fa3-135">**Setting**</span></span>             |
|-----------------------|-------------------------|
| <span data-ttu-id="34fa3-136">Criar conversão para</span><span class="sxs-lookup"><span data-stu-id="34fa3-136">Create conversion for</span></span> | <span data-ttu-id="34fa3-137">Grade de produto</span><span class="sxs-lookup"><span data-stu-id="34fa3-137">Product variant</span></span>         |
| <span data-ttu-id="34fa3-138">Grade de produto</span><span class="sxs-lookup"><span data-stu-id="34fa3-138">Product variant</span></span>       | <span data-ttu-id="34fa3-139">Camiseta: : extra grande: :</span><span class="sxs-lookup"><span data-stu-id="34fa3-139">T-Shirt : : X-Large : :</span></span> |
| <span data-ttu-id="34fa3-140">De unidade</span><span class="sxs-lookup"><span data-stu-id="34fa3-140">From unit</span></span>             | <span data-ttu-id="34fa3-141">Caixas</span><span class="sxs-lookup"><span data-stu-id="34fa3-141">Boxes</span></span>                   |
| <span data-ttu-id="34fa3-142">Fator</span><span class="sxs-lookup"><span data-stu-id="34fa3-142">Factor</span></span>                | <span data-ttu-id="34fa3-143">4</span><span class="sxs-lookup"><span data-stu-id="34fa3-143">4</span></span>                       |
| <span data-ttu-id="34fa3-144">Para unidade</span><span class="sxs-lookup"><span data-stu-id="34fa3-144">To Unit</span></span>               | <span data-ttu-id="34fa3-145">Partes</span><span class="sxs-lookup"><span data-stu-id="34fa3-145">Pieces</span></span>                  |

<span data-ttu-id="34fa3-146">As variantes de produtos liberados pequena, médio e grande têm a mesma unidade de conversão entre a caixa de unidade e peças. Isso significa que você pode definir a conversão de unidade para essas grades de produtos no produto mestre.</span><span class="sxs-lookup"><span data-stu-id="34fa3-146">The Released product variants Small, Medium, and Large have the same unit conversion between the unit Box and Pieces, which means that you can define the unit conversion for these product variants on the product master.</span></span>

| <span data-ttu-id="34fa3-147">**Campo**</span><span class="sxs-lookup"><span data-stu-id="34fa3-147">**Field**</span></span>             | <span data-ttu-id="34fa3-148">**Configuração**</span><span class="sxs-lookup"><span data-stu-id="34fa3-148">**Setting**</span></span> |
|-----------------------|-------------|
| <span data-ttu-id="34fa3-149">Criar conversão para</span><span class="sxs-lookup"><span data-stu-id="34fa3-149">Create conversion for</span></span> | <span data-ttu-id="34fa3-150">Produto</span><span class="sxs-lookup"><span data-stu-id="34fa3-150">Product</span></span>     |
| <span data-ttu-id="34fa3-151">Produto</span><span class="sxs-lookup"><span data-stu-id="34fa3-151">Product</span></span>               | <span data-ttu-id="34fa3-152">Camiseta</span><span class="sxs-lookup"><span data-stu-id="34fa3-152">T-Shirt</span></span>     |
| <span data-ttu-id="34fa3-153">De unidade</span><span class="sxs-lookup"><span data-stu-id="34fa3-153">From unit</span></span>             | <span data-ttu-id="34fa3-154">Caixas</span><span class="sxs-lookup"><span data-stu-id="34fa3-154">Boxes</span></span>       |
| <span data-ttu-id="34fa3-155">Fator</span><span class="sxs-lookup"><span data-stu-id="34fa3-155">Factor</span></span>                | <span data-ttu-id="34fa3-156">5</span><span class="sxs-lookup"><span data-stu-id="34fa3-156">5</span></span>           |
| <span data-ttu-id="34fa3-157">Para unidade</span><span class="sxs-lookup"><span data-stu-id="34fa3-157">To Unit</span></span>               | <span data-ttu-id="34fa3-158">Partes</span><span class="sxs-lookup"><span data-stu-id="34fa3-158">Pieces</span></span>      |

### <a name="using-excel-to-update-the-unit-conversions"></a><span data-ttu-id="34fa3-159">Usando o Excel para atualizar as conversões de unidade</span><span class="sxs-lookup"><span data-stu-id="34fa3-159">Using Excel to update the unit conversions</span></span>

<span data-ttu-id="34fa3-160">Se um produto tiver muitas grades de produtos com conversões de unidade diferentes, será aconselhável exportar as conversões de unidades da página **Conversão de unidades** para uma planilha do Excel, atualizar as conversões e publicá-las novamente no Supply Chain Mangement.</span><span class="sxs-lookup"><span data-stu-id="34fa3-160">If a product has many product variants with different unit conversions, it's a good idea to export the unit conversions from the **Unit conversion** page to an Excel spreadsheet, update the conversions, and then publish them back to Supply Chain Mangement.</span></span>

<span data-ttu-id="34fa3-161">A opção para exportar para o Excel e publicar as edições no Supply Chain Mangement é habilitada do item de menu **Abrir no Microsoft Office** no Painel de ações na página **Conversão de unidade**.</span><span class="sxs-lookup"><span data-stu-id="34fa3-161">The option to export to Excel and publish the edits back to Supply Chain Mangement is enabled from the **Open in Microsoft office** menu item on the Action Pane on the **Unit conversion** page.</span></span>
