---
title: "Nomenclatura de números e de nomes de grade de produto"
description: "Este tópico descreve como você pode configurar uma nomenclatura de número de produto para substituir o formato fixo [Número do produto mestre - Configuração - Tamanho - Cor - Estilo]. A nova nomenclatura tem um formato de destino que inclui o número do produto mestre, as dimensões ativas do produto e os delimitadores de texto de sua escolha. Você também pode criar uma nomenclatura para os nomes de produto. Por fim, você pode criar uma nomenclatura para identificar configurações criadas pelo configurador de produto baseado em restrições. Essas nomenclaturas podem conter os atributos de sua preferência."
author: roxanadiaconu
manager: AnnBe
ms.date: 05/10/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: EcoResNomenclature, EcoResProductDimensionGroup, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelDetails
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations, UnifiedOperations
ms.custom: 220104
ms.assetid: 3fe69fb7-5c32-423c-98a8-2f53186cda68
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.dyn365.ops.intro: Version 1611
ms.search.validFrom: 2016-11-30
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: d1a9ced00d8dc09e59512056392a250a76ba5b97
ms.contentlocale: pt-br
ms.lasthandoff: 08/29/2017

---

# <a name="nomenclature-of-product-variant-numbers-and-names"></a><span data-ttu-id="6baf2-107">Nomenclatura de números e de nomes de grade de produto</span><span class="sxs-lookup"><span data-stu-id="6baf2-107">Nomenclature of product variant numbers and names</span></span>

<span data-ttu-id="6baf2-108">Este tópico descreve como você pode configurar uma nomenclatura de número de produto para substituir o formato fixo [Número do produto mestre - Configuração - Tamanho - Cor - Estilo].</span><span class="sxs-lookup"><span data-stu-id="6baf2-108">This topic describes how you can set up a product number nomenclature to replace the fixed [Product master number - Configuration - Size - Color - Style] format.</span></span> <span data-ttu-id="6baf2-109">A nova nomenclatura tem um formato de destino que inclui o número do produto mestre, as dimensões ativas do produto e os delimitadores de texto de sua escolha.</span><span class="sxs-lookup"><span data-stu-id="6baf2-109">The new nomenclature has a targeted format that includes the product master number, active product dimensions, and text delimiters of your choice.</span></span> <span data-ttu-id="6baf2-110">Você também pode criar uma nomenclatura para os nomes de produto.</span><span class="sxs-lookup"><span data-stu-id="6baf2-110">You can also create a nomenclature for product names.</span></span> <span data-ttu-id="6baf2-111">Por fim, você pode criar uma nomenclatura para identificar configurações criadas pelo configurador de produto baseado em restrições.</span><span class="sxs-lookup"><span data-stu-id="6baf2-111">Finally, you can build a nomenclature to identify configurations that are created by the constraint-based product configurator.</span></span> <span data-ttu-id="6baf2-112">Essas nomenclaturas podem conter os atributos de sua preferência.</span><span class="sxs-lookup"><span data-stu-id="6baf2-112">These nomenclatures can contain attributes of your choice.</span></span>

<span data-ttu-id="6baf2-113">As novas nomenclaturas para números de grade de produto e nomes de grade de produto permitem incluir segmentos nos identificadores de grades de produto.</span><span class="sxs-lookup"><span data-stu-id="6baf2-113">The new nomenclatures for product variant numbers and product variant names let you include segments in the identifiers for product variants.</span></span> <span data-ttu-id="6baf2-114">Esses segmentos podem incluir o número e o nome do produto mestre, as IDs os nomes de dimensão de produto, as sequências numéricas, as constantes de texto e os atributos.</span><span class="sxs-lookup"><span data-stu-id="6baf2-114">These segments can include the product master number and name, product dimension IDs and names, number sequences, text constants, and attributes.</span></span> <span data-ttu-id="6baf2-115">Tal funcionalidade permite que você encontre rapidamente uma grade de produto específica ao criar uma ordem de venda ou de compra.</span><span class="sxs-lookup"><span data-stu-id="6baf2-115">This functionality lets you quickly find a specific product variant when you create a sales order or a purchase order.</span></span> <span data-ttu-id="6baf2-116">Você cria nomenclaturas para números e nomes de grade de produto usando a página **Nomenclatura de produtos**.</span><span class="sxs-lookup"><span data-stu-id="6baf2-116">You create nomenclatures for both product variant numbers and product variant names by using the **Product nomenclature** page.</span></span> <span data-ttu-id="6baf2-117">Para abrir essa página, clique em **Gerenciamento de informações do produto** &gt; **Configuração**.</span><span class="sxs-lookup"><span data-stu-id="6baf2-117">To open this page, click **Product information management** &gt; **Setup**.</span></span>

## <a name="nomenclature-of-predefined-product-variants"></a><span data-ttu-id="6baf2-118">Nomenclatura de grades de produto predefinidas</span><span class="sxs-lookup"><span data-stu-id="6baf2-118">Nomenclature of predefined product variants</span></span>
<span data-ttu-id="6baf2-119">As grades de produto são geradas para produtos mestres de acordo com uma das três tecnologias de configuração:</span><span class="sxs-lookup"><span data-stu-id="6baf2-119">Product variants are generated for product masters according to one of three configuration technologies:</span></span>

-   <span data-ttu-id="6baf2-120">Grades predefinidas</span><span class="sxs-lookup"><span data-stu-id="6baf2-120">Predefined variants</span></span>
-   <span data-ttu-id="6baf2-121">Baseadas em restrições</span><span class="sxs-lookup"><span data-stu-id="6baf2-121">Constraint-based</span></span>
-   <span data-ttu-id="6baf2-122">Baseadas em dimensões</span><span class="sxs-lookup"><span data-stu-id="6baf2-122">Dimension-based</span></span>

<span data-ttu-id="6baf2-123">Cada grade de produto tem um número e um nome, e as nomenclaturas de identificação para grade de produto permitem que você selecione os segmentos que serão incluídos no número de cada grade de produto.</span><span class="sxs-lookup"><span data-stu-id="6baf2-123">Each product variant has a number and a name, and the product variant identification nomenclatures let you select the segments that will be included in each product variant number or name.</span></span> <span data-ttu-id="6baf2-124">Você pode selecionar os seguintes segmentos na página **Nomenclatura de produtos**:</span><span class="sxs-lookup"><span data-stu-id="6baf2-124">You can select the following segments on the **Product nomenclature** page:</span></span>

-   <span data-ttu-id="6baf2-125">Número do produto mestre</span><span class="sxs-lookup"><span data-stu-id="6baf2-125">Product master number</span></span>
-   <span data-ttu-id="6baf2-126">Nome do produto mestre</span><span class="sxs-lookup"><span data-stu-id="6baf2-126">Product master name</span></span>
-   <span data-ttu-id="6baf2-127">Valor de sequência numérica</span><span class="sxs-lookup"><span data-stu-id="6baf2-127">Number sequence value</span></span>
-   <span data-ttu-id="6baf2-128">Constante de texto</span><span class="sxs-lookup"><span data-stu-id="6baf2-128">Text constant</span></span>
-   <span data-ttu-id="6baf2-129">Dimensões do produto</span><span class="sxs-lookup"><span data-stu-id="6baf2-129">Product dimensions</span></span>
    -   <span data-ttu-id="6baf2-130">ID ou nome da configuração</span><span class="sxs-lookup"><span data-stu-id="6baf2-130">Configuration ID or name</span></span>
    -   <span data-ttu-id="6baf2-131">ID ou nome da cor</span><span class="sxs-lookup"><span data-stu-id="6baf2-131">Color ID or name</span></span>
    -   <span data-ttu-id="6baf2-132">ID ou nome do tamanho</span><span class="sxs-lookup"><span data-stu-id="6baf2-132">Size ID or name</span></span>
    -   <span data-ttu-id="6baf2-133">ID ou nome do estilo</span><span class="sxs-lookup"><span data-stu-id="6baf2-133">Style ID or name</span></span>

<span data-ttu-id="6baf2-134">Depois de definir uma nomenclatura de número de identificação de grade de produto, será possível associá-la a um grupo de dimensões do produto.</span><span class="sxs-lookup"><span data-stu-id="6baf2-134">After you define a product variant identification number nomenclature, you can associate it with a product dimension group.</span></span> <span data-ttu-id="6baf2-135">Todos os produtos mestres que fizerem referência a esse grupo de dimensões de produto receberão números de grade de produto de acordo com a nomenclatura.</span><span class="sxs-lookup"><span data-stu-id="6baf2-135">All product masters that reference this product dimension group will then be assigned product variant numbers according to the nomenclature.</span></span> <span data-ttu-id="6baf2-136">Contudo, as nomenclaturas de nome de grade de produto não podem ser associadas a grupos de dimensões do produto.</span><span class="sxs-lookup"><span data-stu-id="6baf2-136">However, product variant name nomenclatures can't be associated with product dimension groups.</span></span> <span data-ttu-id="6baf2-137">Você também pode atribuir uma identificação de grade de produto diretamente a um produto mestre.</span><span class="sxs-lookup"><span data-stu-id="6baf2-137">You can also assign a product variant identification nomenclature directly to a product master.</span></span> <span data-ttu-id="6baf2-138">Nesse caso, as grades do produto que pertencem ao produto mestre receberão números e nomes de grade de produto de acordo com as nomenclaturas.</span><span class="sxs-lookup"><span data-stu-id="6baf2-138">In this case, the product variants that belong to the product master will be assigned product variant numbers and names according to the nomenclatures.</span></span>

### <a name="example"></a><span data-ttu-id="6baf2-139">Exemplo</span><span class="sxs-lookup"><span data-stu-id="6baf2-139">Example</span></span>

<span data-ttu-id="6baf2-140">Uma camiseta (TS1234) é produzida em três tamanhos (P, M, G), quatro cores (Vermelho, Verde, Azul, Amarelo) e dois estilos (Polo, Gola em V).</span><span class="sxs-lookup"><span data-stu-id="6baf2-140">A T-shirt (TS1234) is produced in three sizes (S, M, L), four colors (Red, Green, Blue, Yellow), and two styles (Polo, V).</span></span> <span data-ttu-id="6baf2-141">Portanto, 24 grades de produto são possíveis (= 3 × 4 × 2).</span><span class="sxs-lookup"><span data-stu-id="6baf2-141">Therefore, 24 product variants are possible (= 3 × 4 × 2).</span></span> <span data-ttu-id="6baf2-142">Você cria uma nomenclatura de número de grade de produto com os seguintes segmentos:</span><span class="sxs-lookup"><span data-stu-id="6baf2-142">You create a product variant number nomenclature that has the following segments:</span></span>

1.  <span data-ttu-id="6baf2-143">Número do produto mestre</span><span class="sxs-lookup"><span data-stu-id="6baf2-143">Product master number</span></span>
2.  <span data-ttu-id="6baf2-144">Constante de texto: "-"</span><span class="sxs-lookup"><span data-stu-id="6baf2-144">Text constant: "-"</span></span>
3.  <span data-ttu-id="6baf2-145">Cor</span><span class="sxs-lookup"><span data-stu-id="6baf2-145">Color</span></span>
4.  <span data-ttu-id="6baf2-146">Constante de texto: "-"</span><span class="sxs-lookup"><span data-stu-id="6baf2-146">Text constant: "-"</span></span>
5.  <span data-ttu-id="6baf2-147">Tamanho</span><span class="sxs-lookup"><span data-stu-id="6baf2-147">Size</span></span>
6.  <span data-ttu-id="6baf2-148">Constante de texto: "-"</span><span class="sxs-lookup"><span data-stu-id="6baf2-148">Text constant: "-"</span></span>
7.  <span data-ttu-id="6baf2-149">Estilo</span><span class="sxs-lookup"><span data-stu-id="6baf2-149">Style</span></span>

<span data-ttu-id="6baf2-150">Nesse caso, o número da grade de produto para uma camiseta polo vermelha pequena será TS1234-Vermelho-Pequena-Polo</span><span class="sxs-lookup"><span data-stu-id="6baf2-150">In this case, the product variant number for a red, small, polo T-shirt will be TS1234-Red-Small-Polo.</span></span>

## <a name="nomenclature-of-constraintbased-configurations"></a><span data-ttu-id="6baf2-151">Nomenclatura de configurações baseadas em restrições</span><span class="sxs-lookup"><span data-stu-id="6baf2-151">Nomenclature of constraintbased configurations</span></span>
<span data-ttu-id="6baf2-152">Em configurações baseadas em restrições, você pode criar uma nomenclatura dedicada para a dimensão de configuração de produto.</span><span class="sxs-lookup"><span data-stu-id="6baf2-152">For constraint-based configurations, you can create a dedicated nomenclature for the configuration product dimension.</span></span> <span data-ttu-id="6baf2-153">Você pode selecionar os seguintes segmentos na página **Nomenclatura de produtos**:</span><span class="sxs-lookup"><span data-stu-id="6baf2-153">You can select the following segments on the **Product nomenclature** page:</span></span>

-   <span data-ttu-id="6baf2-154">Valor de sequência numérica</span><span class="sxs-lookup"><span data-stu-id="6baf2-154">Number sequence value</span></span>
-   <span data-ttu-id="6baf2-155">Constante de texto</span><span class="sxs-lookup"><span data-stu-id="6baf2-155">Text constant</span></span>
-   <span data-ttu-id="6baf2-156">Valor do atributo</span><span class="sxs-lookup"><span data-stu-id="6baf2-156">Attribute value</span></span>

<span data-ttu-id="6baf2-157">Cada componente em um modelo de configuração de produto pode ter sua própria nomenclatura de configuração.</span><span class="sxs-lookup"><span data-stu-id="6baf2-157">Each component in a product configuration model can have its own configuration nomenclature.</span></span> <span data-ttu-id="6baf2-158">Apenas os atributos que pertencem ao componente podem ser usados.</span><span class="sxs-lookup"><span data-stu-id="6baf2-158">Only attributes that belong to the component can be used.</span></span> <span data-ttu-id="6baf2-159">Os atributos de subcomponentes ou os requisitos de usuário não podem ser usados.</span><span class="sxs-lookup"><span data-stu-id="6baf2-159">Attributes from subcomponents or user requirements can't be used.</span></span>

### <a name="example"></a><span data-ttu-id="6baf2-160">Exemplo</span><span class="sxs-lookup"><span data-stu-id="6baf2-160">Example</span></span>

<span data-ttu-id="6baf2-161">Um modelo de configuração de produto tem um componente raiz com dois atributos:</span><span class="sxs-lookup"><span data-stu-id="6baf2-161">A product configuration model has a root component that has two attributes:</span></span>

-   <span data-ttu-id="6baf2-162">Material (plástico, madeira, aço)</span><span class="sxs-lookup"><span data-stu-id="6baf2-162">Material (Plastic, Wood, Steel)</span></span>
-   <span data-ttu-id="6baf2-163">Tamanho (10...100)</span><span class="sxs-lookup"><span data-stu-id="6baf2-163">Length (10...100)</span></span>

<span data-ttu-id="6baf2-164">Você cria uma nomenclatura de configuração com os seguintes segmentos:</span><span class="sxs-lookup"><span data-stu-id="6baf2-164">You create a configuration nomenclature that has the following segments:</span></span>

1.  <span data-ttu-id="6baf2-165">Valor do atributo: material</span><span class="sxs-lookup"><span data-stu-id="6baf2-165">Attribute value: Material</span></span>
2.  <span data-ttu-id="6baf2-166">Constante de texto: "AAA"</span><span class="sxs-lookup"><span data-stu-id="6baf2-166">Text constant: "AAA"</span></span>
3.  <span data-ttu-id="6baf2-167">Valor do atributo: tamanho</span><span class="sxs-lookup"><span data-stu-id="6baf2-167">Attribute value: Length</span></span>

<span data-ttu-id="6baf2-168">Nesse caso, a ID de configuração do material de madeira com um comprimento 78 será MadeiraAAA78.</span><span class="sxs-lookup"><span data-stu-id="6baf2-168">In this case, the configuration ID for wood material that has a length of 78 will be WoodAAA78.</span></span>

## <a name="nomenclature-of-dimensionbased-configurations"></a><span data-ttu-id="6baf2-169">Nomenclatura de configurações baseadas em dimensões</span><span class="sxs-lookup"><span data-stu-id="6baf2-169">Nomenclature of dimensionbased configurations</span></span>
<span data-ttu-id="6baf2-170">Em configurações baseadas em dimensões, você pode criar uma nomenclatura dedicada para a dimensão de configuração de produto.</span><span class="sxs-lookup"><span data-stu-id="6baf2-170">For dimension-based configurations, you can create a dedicated nomenclature for the configuration product dimension.</span></span> <span data-ttu-id="6baf2-171">Você pode selecionar os seguintes segmentos na página **Nomenclatura de produtos**:</span><span class="sxs-lookup"><span data-stu-id="6baf2-171">You can select the following segments on the **Product nomenclature** page:</span></span>

-   <span data-ttu-id="6baf2-172">Valor de sequência numérica</span><span class="sxs-lookup"><span data-stu-id="6baf2-172">Number sequence value</span></span>
-   <span data-ttu-id="6baf2-173">Constante de texto</span><span class="sxs-lookup"><span data-stu-id="6baf2-173">Text constant</span></span>
-   <span data-ttu-id="6baf2-174">Item de grupo de configuração</span><span class="sxs-lookup"><span data-stu-id="6baf2-174">Configuration group item</span></span>

<span data-ttu-id="6baf2-175">Você pode definir uma nomenclatura de configuração para uma lista de materiais (BOM).</span><span class="sxs-lookup"><span data-stu-id="6baf2-175">You can define a configuration nomenclature for a bill of materials (BOM).</span></span>

### <a name="example"></a><span data-ttu-id="6baf2-176">Exemplo</span><span class="sxs-lookup"><span data-stu-id="6baf2-176">Example</span></span>

<span data-ttu-id="6baf2-177">Uma BOM tem quatro linhas de BOM divididas em dois grupos de configuração:</span><span class="sxs-lookup"><span data-stu-id="6baf2-177">A BOM has four BOM lines that are divided into two configuration groups:</span></span>

-   <span data-ttu-id="6baf2-178">Linha de BOM: M0007, gabinete padrão</span><span class="sxs-lookup"><span data-stu-id="6baf2-178">BOM line: M0007, Standard cabinet</span></span>
    -   <span data-ttu-id="6baf2-179">Grupo de configuração: gabinete</span><span class="sxs-lookup"><span data-stu-id="6baf2-179">Configuration group: Cabinet</span></span>
-   <span data-ttu-id="6baf2-180">Linha de BOM: M0008, gabinete avançado</span><span class="sxs-lookup"><span data-stu-id="6baf2-180">BOM line: M0008, High end cabinet</span></span>
    -   <span data-ttu-id="6baf2-181">Grupo de configuração: gabinete</span><span class="sxs-lookup"><span data-stu-id="6baf2-181">Configuration group: Cabinet</span></span>
-   <span data-ttu-id="6baf2-182">Linha de BOM: M0021, tecido de grade frontal</span><span class="sxs-lookup"><span data-stu-id="6baf2-182">BOM line: M0021, Front grill cloth</span></span>
    -   <span data-ttu-id="6baf2-183">Grupo de configuração: grade frontal</span><span class="sxs-lookup"><span data-stu-id="6baf2-183">Configuration group: Front grill</span></span>
-   <span data-ttu-id="6baf2-184">Linha de BOM: M0022, metal de grade frontal</span><span class="sxs-lookup"><span data-stu-id="6baf2-184">BOM line: M0022, Front grill metal</span></span>
    -   <span data-ttu-id="6baf2-185">Grupo de configuração: grade frontal</span><span class="sxs-lookup"><span data-stu-id="6baf2-185">Configuration group: Front grill</span></span>

<span data-ttu-id="6baf2-186">Você cria uma nomenclatura de configuração com os seguintes segmentos:</span><span class="sxs-lookup"><span data-stu-id="6baf2-186">You create a configuration nomenclature that has the following segments:</span></span>

1.  <span data-ttu-id="6baf2-187">Grupo de configuração: gabinete</span><span class="sxs-lookup"><span data-stu-id="6baf2-187">Configuration group: Cabinet</span></span>
2.  <span data-ttu-id="6baf2-188">Constante de texto: "&"</span><span class="sxs-lookup"><span data-stu-id="6baf2-188">Text constant: "&"</span></span>
3.  <span data-ttu-id="6baf2-189">Grupo de configuração: grade frontal</span><span class="sxs-lookup"><span data-stu-id="6baf2-189">Configuration group: Front grill</span></span>

<span data-ttu-id="6baf2-190">Nesse caso, a ID de configuração para um gabinete padrão com grade frontal de tecido será: M0007&M0021.</span><span class="sxs-lookup"><span data-stu-id="6baf2-190">In this case, the configuration ID for a standard cabinet that has a cloth front grill will be M0007&M0021.</span></span>

## <a name="nomenclature-for-a-combination-of-product-variants-and-configurations"></a><span data-ttu-id="6baf2-191">Nomenclatura para uma combinação de grades de produto e configurações</span><span class="sxs-lookup"><span data-stu-id="6baf2-191">Nomenclature for a combination of product variants and configurations</span></span>
<span data-ttu-id="6baf2-192">Quando você usa a tecnologia de configuração baseada em restrição ou a tecnologia de configuração baseada em dimensão para configurar grades de produto para um produto mestre, os números das grades de produto podem incluir a nomenclatura da dimensão de configuração.</span><span class="sxs-lookup"><span data-stu-id="6baf2-192">When you use either the constraint-based configuration technology or the dimension-based configuration technology to configure product variants for a product master, the product variant numbers of the product variants can include the nomenclature from the configuration dimension.</span></span> <span data-ttu-id="6baf2-193">Siga estas etapas para configurar as variantes.</span><span class="sxs-lookup"><span data-stu-id="6baf2-193">Follow these steps to configure variants.</span></span>

1.  <span data-ttu-id="6baf2-194">Na página **Nomenclatura de produtos**, defina uma nomenclatura de número de grade de produto que inclua a dimensão de configuração.</span><span class="sxs-lookup"><span data-stu-id="6baf2-194">On the **Product nomenclature** page, define a product variant number nomenclature that includes the configuration dimension.</span></span>
2.  <span data-ttu-id="6baf2-195">Atribua a nomenclatura a um grupo de dimensões de produto com a dimensão de configuração.</span><span class="sxs-lookup"><span data-stu-id="6baf2-195">Assign the nomenclature to a product dimension group that has the configuration dimension.</span></span>
3.  <span data-ttu-id="6baf2-196">Defina uma nomenclatura de configuração para os componentes ou BOMs que serão usados para configurar as grades de produto.</span><span class="sxs-lookup"><span data-stu-id="6baf2-196">Define a configuration nomenclature for the components or BOMs that will be used to configure the product variants.</span></span>

<span data-ttu-id="6baf2-197">Você também pode criar nomenclaturas para os nomes de grade de produto.</span><span class="sxs-lookup"><span data-stu-id="6baf2-197">You can also create nomenclatures for the product variant names.</span></span> <span data-ttu-id="6baf2-198">Os nomes de grade de produto podem ser configurados para incluir a ID ou o nome da configuração.</span><span class="sxs-lookup"><span data-stu-id="6baf2-198">The product variant names can be configured to include the configuration ID or name.</span></span>

### <a name="example-for-constraint-based-configurations"></a><span data-ttu-id="6baf2-199">Exemplo de configurações baseadas em restrições</span><span class="sxs-lookup"><span data-stu-id="6baf2-199">Example for constraint-based configurations</span></span>

<span data-ttu-id="6baf2-200">Neste exemplo, use uma nomenclatura de número de grade de produto que consista nestes segmentos:</span><span class="sxs-lookup"><span data-stu-id="6baf2-200">For this example, you use a product variant number nomenclature that consists of the following segments:</span></span>

1.  <span data-ttu-id="6baf2-201">Número do produto mestre</span><span class="sxs-lookup"><span data-stu-id="6baf2-201">Product master number</span></span>
2.  <span data-ttu-id="6baf2-202">Constante de texto "\_"</span><span class="sxs-lookup"><span data-stu-id="6baf2-202">Text constant "\_"</span></span>
3.  <span data-ttu-id="6baf2-203">Configuração</span><span class="sxs-lookup"><span data-stu-id="6baf2-203">Configuration</span></span>

<span data-ttu-id="6baf2-204">A nomenclatura de configuração consiste nestes segmentos:</span><span class="sxs-lookup"><span data-stu-id="6baf2-204">The configuration nomenclature consists of the following segments:</span></span>

1.  <span data-ttu-id="6baf2-205">Valor do atributo: material</span><span class="sxs-lookup"><span data-stu-id="6baf2-205">Attribute value: Material</span></span>
2.  <span data-ttu-id="6baf2-206">Constante de texto: "AAA"</span><span class="sxs-lookup"><span data-stu-id="6baf2-206">Text constant: "AAA"</span></span>
3.  <span data-ttu-id="6baf2-207">Valor do atributo: tamanho</span><span class="sxs-lookup"><span data-stu-id="6baf2-207">Attribute value: Length</span></span>

<span data-ttu-id="6baf2-208">É possível inserir os seguintes valores para segmentos:</span><span class="sxs-lookup"><span data-stu-id="6baf2-208">You enter the following values for segments:</span></span>

-   <span data-ttu-id="6baf2-209">Número do produto mestre = **M0099**</span><span class="sxs-lookup"><span data-stu-id="6baf2-209">Product master number = **M0099**</span></span>
-   <span data-ttu-id="6baf2-210">Material = **Plástico**</span><span class="sxs-lookup"><span data-stu-id="6baf2-210">Material = **Plastic**</span></span>
-   <span data-ttu-id="6baf2-211">Comprimento = **12**</span><span class="sxs-lookup"><span data-stu-id="6baf2-211">Length = **12**</span></span>

<span data-ttu-id="6baf2-212">Nesse caso, o número da grade de produto será M0099\_PlásticoAAA12.</span><span class="sxs-lookup"><span data-stu-id="6baf2-212">In this case, the product variant number will be M0099\_PlasticAAA12.</span></span>

### <a name="example-for-dimension-based-configurations"></a><span data-ttu-id="6baf2-213">Exemplo de configurações baseadas em dimensões</span><span class="sxs-lookup"><span data-stu-id="6baf2-213">Example for dimension-based configurations</span></span>

<span data-ttu-id="6baf2-214">Neste exemplo, use uma nomenclatura de número de grade de produto que consista nestes segmentos:</span><span class="sxs-lookup"><span data-stu-id="6baf2-214">For this example, you use a product variant number nomenclature that consists of the following segments:</span></span>

1.  <span data-ttu-id="6baf2-215">Número do produto mestre</span><span class="sxs-lookup"><span data-stu-id="6baf2-215">Product master number</span></span>
2.  <span data-ttu-id="6baf2-216">Constante de texto "//"</span><span class="sxs-lookup"><span data-stu-id="6baf2-216">Text constant "//"</span></span>
3.  <span data-ttu-id="6baf2-217">Configuração</span><span class="sxs-lookup"><span data-stu-id="6baf2-217">Configuration</span></span>

<span data-ttu-id="6baf2-218">A nomenclatura de configuração consiste nestes segmentos:</span><span class="sxs-lookup"><span data-stu-id="6baf2-218">The configuration nomenclature consists of the following segments:</span></span>

1.  <span data-ttu-id="6baf2-219">Grupo de configuração: gabinete</span><span class="sxs-lookup"><span data-stu-id="6baf2-219">Configuration group: Cabinet</span></span>
2.  <span data-ttu-id="6baf2-220">Constante de texto: "&"</span><span class="sxs-lookup"><span data-stu-id="6baf2-220">Text constant: "&"</span></span>
3.  <span data-ttu-id="6baf2-221">Grupo de configuração: grade frontal</span><span class="sxs-lookup"><span data-stu-id="6baf2-221">Configuration group: Front grill</span></span>

<span data-ttu-id="6baf2-222">É possível inserir os seguintes valores para segmentos:</span><span class="sxs-lookup"><span data-stu-id="6baf2-222">You enter the following values for segments:</span></span>

-   <span data-ttu-id="6baf2-223">Número do produto mestre = **D0123**</span><span class="sxs-lookup"><span data-stu-id="6baf2-223">Product master number = **D0123**</span></span>
-   <span data-ttu-id="6baf2-224">Gabinete = **M0008**</span><span class="sxs-lookup"><span data-stu-id="6baf2-224">Cabinet = **M0008**</span></span>
-   <span data-ttu-id="6baf2-225">Grade frontal = **M0022**</span><span class="sxs-lookup"><span data-stu-id="6baf2-225">Front grill = **M0022**</span></span>

<span data-ttu-id="6baf2-226">Nesse caso, o número da grade de produto será D0123//M0008&M0022.</span><span class="sxs-lookup"><span data-stu-id="6baf2-226">In this case, the product variant number will be D0123//M0008&M0022.</span></span>

## <a name="numbering-conflicts"></a><span data-ttu-id="6baf2-227">Conflitos de numeração</span><span class="sxs-lookup"><span data-stu-id="6baf2-227">Numbering conflicts</span></span>
<span data-ttu-id="6baf2-228">Em alguns casos, uma nomenclatura de número de grade de produto configurada pode não produzir números de grade de produto exclusivos.</span><span class="sxs-lookup"><span data-stu-id="6baf2-228">In some cases, a product variant number nomenclature that you set up might not produce unique product variant numbers.</span></span> <span data-ttu-id="6baf2-229">Por exemplo, os número de grade de produto não serão exclusivos se uma dimensão de produto ativa não for incluída na nomenclatura para um produto mestre que use a tecnologia de configuração de grade predefinida.</span><span class="sxs-lookup"><span data-stu-id="6baf2-229">For example, the product variant numbers won't be unique if one active product dimension isn't included in the nomenclature for a product master that uses the predefined variant configuration technology.</span></span> <span data-ttu-id="6baf2-230">A forma como você lida com os conflitos varia, dependendo da tecnologia de configuração.</span><span class="sxs-lookup"><span data-stu-id="6baf2-230">The way that you handle conflicts varies, depending on the configuration technology.</span></span>

### <a name="predefined-variants"></a><span data-ttu-id="6baf2-231">Grades predefinidas</span><span class="sxs-lookup"><span data-stu-id="6baf2-231">Predefined variants</span></span>

<span data-ttu-id="6baf2-232">Ocorrerá um erro se você tentar criar manualmente ou gerar de forma automática as grades de produto, e mais de uma grade de produto terminará com o mesmo número de grade de produto.</span><span class="sxs-lookup"><span data-stu-id="6baf2-232">An error occurs if you try to manually create or automatically generate product variants, and more than one product variant ends up with the same product variant number.</span></span> <span data-ttu-id="6baf2-233">Para evitar esse cenário, sempre utilize todas as dimensões de produto ativas no grupo de dimensões de produto.</span><span class="sxs-lookup"><span data-stu-id="6baf2-233">To avoid this scenario, you should use all active product dimensions in the product dimension group.</span></span> <span data-ttu-id="6baf2-234">Como alternativa, inclua uma sequência numérica para ajudar a garantir que os números de grade de produto sejam exclusivos.</span><span class="sxs-lookup"><span data-stu-id="6baf2-234">Alternatively, include a number sequence to help guarantee that the product variant numbers are unique.</span></span>

### <a name="constraint-based-configurations"></a><span data-ttu-id="6baf2-235">Configurações baseadas em restrições</span><span class="sxs-lookup"><span data-stu-id="6baf2-235">Constraint-based configurations</span></span>

<span data-ttu-id="6baf2-236">Dependendo da nomenclatura, o sistema poderá tentar atribuir um número de grade de produto não exclusivo a uma configuração.</span><span class="sxs-lookup"><span data-stu-id="6baf2-236">Depending on the nomenclature, the system might try to assign a non-unique product variant number to a configuration.</span></span> <span data-ttu-id="6baf2-237">Nesse caso, o sistema usa a sequência numérica para a dimensão de configuração como o número de grade de produto e você recebe um aviso.</span><span class="sxs-lookup"><span data-stu-id="6baf2-237">In this case, the system uses the number sequence for the configuration dimension as the product variant number instead, and you receive a warning.</span></span> <span data-ttu-id="6baf2-238">Para evitar esse cenário, inclua atributos suficientes na nomenclatura para ajudar a garantir o uso de números de variante de produto exclusivos.</span><span class="sxs-lookup"><span data-stu-id="6baf2-238">To avoid this scenario, you should include enough attributes in the nomenclature to help guarantee unique product variant numbers.</span></span> <span data-ttu-id="6baf2-239">Você também deve garantir que a opção **Reutilizar** esteja ativada para o componente.</span><span class="sxs-lookup"><span data-stu-id="6baf2-239">You should also make sure that the **Reuse** option is turned on for the component.</span></span>

### <a name="dimension-based-configurations"></a><span data-ttu-id="6baf2-240">Configurações baseadas em dimensões</span><span class="sxs-lookup"><span data-stu-id="6baf2-240">Dimension-based configurations</span></span>

<span data-ttu-id="6baf2-241">Durante uma etapa do processo de configuração, o sistema sugere um valor de configuração de acordo com a nomenclatura.</span><span class="sxs-lookup"><span data-stu-id="6baf2-241">During one step of the configuration process, the system suggests a configuration value according to the nomenclature.</span></span> <span data-ttu-id="6baf2-242">Nessa etapa, você alterará manualmente o valor da configuração.</span><span class="sxs-lookup"><span data-stu-id="6baf2-242">In this step, you can manually change the configuration value.</span></span> <span data-ttu-id="6baf2-243">Quando você salva a configuração, o sistema verifica se o valor da configuração é exclusivo.</span><span class="sxs-lookup"><span data-stu-id="6baf2-243">When you save the configuration, the system verifies that the configuration value is unique.</span></span> <span data-ttu-id="6baf2-244">Se o valor inserido não for exclusivo, você receberá uma mensagem de erro.</span><span class="sxs-lookup"><span data-stu-id="6baf2-244">If the value that you entered isn't unique, you receive an error message.</span></span> <span data-ttu-id="6baf2-245">Para salvar a configuração, insira um valor de configuração exclusivo.</span><span class="sxs-lookup"><span data-stu-id="6baf2-245">To save the configuration, you must enter a unique configuration value.</span></span>

<a name="see-also"></a><span data-ttu-id="6baf2-246">Consulte também</span><span class="sxs-lookup"><span data-stu-id="6baf2-246">See also</span></span>
--------

[<span data-ttu-id="6baf2-247">Criar uma nomenclatura de número de produto para grades de produto predefinidas</span><span class="sxs-lookup"><span data-stu-id="6baf2-247">Create a product number nomenclature for predefined product variants</span></span>](/dynamics365/unified-operations/supply-chain/pim/tasks/create-product-number-nomenclature-predefined-variants-2016-11)

[<span data-ttu-id="6baf2-248">Criar uma nomenclatura de número de produto para grades de produto configuradas</span><span class="sxs-lookup"><span data-stu-id="6baf2-248">Create a product number nomenclature for configured product variants</span></span>](/dynamics365/unified-operations/supply-chain/pim/tasks/create-product-number-nomenclature-product-variants_2016_11)


