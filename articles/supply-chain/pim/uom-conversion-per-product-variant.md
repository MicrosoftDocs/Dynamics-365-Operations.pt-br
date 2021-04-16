---
title: Conversão de unidade de medida por grade de produto
description: Este tópico explica como configurar conversões de unidade de medida para grades do produto. Ele iInclui um exemplo da instalação.
author: johanhoffmann
ms.date: 05/11/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: UnitOfMeasureConversion
ROBOTS: noindex, nofollow
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-04-01
ms.dyn365.ops.version: 10
ms.openlocfilehash: eaa20f9a8f145fa8d44bfe77cc85f4dc565c2d27
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5841494"
---
# <a name="unit-of-measure-conversion-per-product-variant"></a><span data-ttu-id="aace6-104">Conversão de unidade de medida por grade de produto</span><span class="sxs-lookup"><span data-stu-id="aace6-104">Unit of measure conversion per product variant</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="aace6-105">Este tópico explica como configurar conversões de unidade de medida para várias grades do produto.</span><span class="sxs-lookup"><span data-stu-id="aace6-105">This topic explains how to set up unit of measure conversions for various product variants.</span></span>

<span data-ttu-id="aace6-106">Em vez de criar vários produtos individuais que devem ser mantidos, você pode usar variantes de produto para criar variações de um único produto.</span><span class="sxs-lookup"><span data-stu-id="aace6-106">Instead of creating multiple individual products that must be maintained, you can use product variants to create variations of a single product.</span></span> <span data-ttu-id="aace6-107">Por exemplo, uma grade de produto pode ser uma camiseta de um determinado tamanho e cor.</span><span class="sxs-lookup"><span data-stu-id="aace6-107">For example, a product variant might be a T-shirt of a given size and color.</span></span>

<span data-ttu-id="aace6-108">Anteriormente, as conversões de unidades podiam ser configuradas somente no produto mestre.</span><span class="sxs-lookup"><span data-stu-id="aace6-108">Previously, unit conversions could be set up only on the product master.</span></span> <span data-ttu-id="aace6-109">Portanto, todas as grades de produto tinham as mesmas regras de conversão de unidades.</span><span class="sxs-lookup"><span data-stu-id="aace6-109">Therefore, all product variants had the same unit conversion rules.</span></span> <span data-ttu-id="aace6-110">No entanto, quando o recurso *Conversões de unidade de medida para variantes de produto* são ativadas, se suas camisas forem vendidas em caixas e o número de camisas que podem ser embaladas em uma caixa depender do tamanho das camisetas, você poderá configurar conversões de unidade entre os tamanhos de camisa diferentes e as caixas usadas para a embalagem.</span><span class="sxs-lookup"><span data-stu-id="aace6-110">However, when the *Unit of measure conversions for product variants* feature is turned on, if your T-shirts are sold in boxes, and the number of T-shirts that can be packed in a box depends on the size of the T-shirts, you can now set up unit conversions between the different shirt sizes and the boxes that are used for packaging.</span></span>

## <a name="turn-on-the-feature-in-your-system"></a><span data-ttu-id="aace6-111">Ative o recurso no seu sistema</span><span class="sxs-lookup"><span data-stu-id="aace6-111">Turn on the feature in your system</span></span>

<span data-ttu-id="aace6-112">Se você ainda não tiver visto esse recurso no sistema, vá para [Gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) e ative o recurso *Conversões de unidade de medida para variantes de produtos*.</span><span class="sxs-lookup"><span data-stu-id="aace6-112">If you don't already see this feature in your system, go to [Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md), and turn on the *Unit of measure conversions for product variants* feature.</span></span>

## <a name="set-up-a-product-for-unit-conversion-per-variant"></a><span data-ttu-id="aace6-113">Configurar um produto para a conversão de unidade por grade</span><span class="sxs-lookup"><span data-stu-id="aace6-113">Set up a product for unit conversion per variant</span></span>

<span data-ttu-id="aace6-114">Grades de produto só podem ser criadas para produtos que são produtos mestre.</span><span class="sxs-lookup"><span data-stu-id="aace6-114">Product variants can be created only for products that are product masters.</span></span> <span data-ttu-id="aace6-115">Para obter mais informações, consulte [Criar um produto mestre](tasks/create-product-master.md).</span><span class="sxs-lookup"><span data-stu-id="aace6-115">For more information, see [Create a product master](tasks/create-product-master.md).</span></span> <span data-ttu-id="aace6-116">O recurso *Conversões de unidade de medida para variantes de produto* não estão disponíveis para os produtos que estão configurados para processos de peso variável.</span><span class="sxs-lookup"><span data-stu-id="aace6-116">The *Unit of measure conversions for product variants* feature isn't available for products that are set up for catch-weight processes.</span></span>

<span data-ttu-id="aace6-117">Para configurar um produto mestre para oferecer suporte à conversão de unidades por grade, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="aace6-117">To configure a product master to support unit conversion per variant, follow these steps.</span></span>

1. <span data-ttu-id="aace6-118">Vá para **Gerenciamento de informações sobre produtos \> Produtos \> Produtos mestre**.</span><span class="sxs-lookup"><span data-stu-id="aace6-118">Go to **Product information management \> Products \> Product masters**.</span></span>
1. <span data-ttu-id="aace6-119">Crie ou abra um produto mestre para ir para a **Página detalhes do produto**.</span><span class="sxs-lookup"><span data-stu-id="aace6-119">Create or open a product master to go to its **Product details** page.</span></span>
1. <span data-ttu-id="aace6-120">Defina a opção **Habilitar conversões de unidade de medida** como *Sim*.</span><span class="sxs-lookup"><span data-stu-id="aace6-120">Set the **Enable unit of measure conversions** option to *Yes*.</span></span>
1. <span data-ttu-id="aace6-121">No Painel de Ações, na guia **Produto**, no grupo **Configuração**, selecione **Conversões de unidade**.</span><span class="sxs-lookup"><span data-stu-id="aace6-121">On the Action Pane, on the **Product** tab, in the **Set up** group, select **Unit conversions**.</span></span>
1. <span data-ttu-id="aace6-122">A página **Conversões de unidade** é aberta.</span><span class="sxs-lookup"><span data-stu-id="aace6-122">The **Unit conversions** page opens.</span></span> <span data-ttu-id="aace6-123">Selecione uma das guias a seguir:</span><span class="sxs-lookup"><span data-stu-id="aace6-123">Select one of the following tabs:</span></span>

    - <span data-ttu-id="aace6-124">**Conversões entre classes** – Selecione esta guia para converter entre as unidades que pertencem à mesma classe de unidade.</span><span class="sxs-lookup"><span data-stu-id="aace6-124">**Intra-class conversions** – Select this tab to convert between units that belong to the same unit class.</span></span>
    - <span data-ttu-id="aace6-125">**Conversões entre classes** – Selecione esta guia para converter entre as unidades que pertencem à classes de unidade diferentes.</span><span class="sxs-lookup"><span data-stu-id="aace6-125">**Inter-class conversions** – Select this tab to convert between units that belong to different unit classes.</span></span>

1. <span data-ttu-id="aace6-126">Selecione **Novo** para adicionar uma nova conversão de unidade.</span><span class="sxs-lookup"><span data-stu-id="aace6-126">Select **New** to add a new unit conversion.</span></span>
1. <span data-ttu-id="aace6-127">Defina o campo **Criar conversão para** como um dos seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="aace6-127">Set the **Create conversion for** field to one of the following values:</span></span>

    - <span data-ttu-id="aace6-128">**Produto** – Se você selecionar esse valor, você pode configurar uma conversão de unidade para os produtos mestres.</span><span class="sxs-lookup"><span data-stu-id="aace6-128">**Product** – If you select this value, you can set up a unit conversion for the product master.</span></span> <span data-ttu-id="aace6-129">Essa conversão de unidade será usada como um fallback para todas as grades de produto para as quais nenhuma conversão de unidade é definida.</span><span class="sxs-lookup"><span data-stu-id="aace6-129">That unit conversion will be used as a fallback for all product variants that no unit conversion is defined for.</span></span>
    - <span data-ttu-id="aace6-130">**Grade de produto** – Se você selecionar esse valor, você pode configurar uma conversão de unidade para uma grade de produto específica.</span><span class="sxs-lookup"><span data-stu-id="aace6-130">**Product variant** – If you select this value, you can set up a unit conversion for a specific product variant.</span></span> <span data-ttu-id="aace6-131">Use o campo **Grade do produto** para selecionar a grade.</span><span class="sxs-lookup"><span data-stu-id="aace6-131">Use the **Product variant** field to select the variant.</span></span>

    <span data-ttu-id="aace6-132">![Adicionando uma nova conversão de unidades](media/uom-new-conversion.png "Adicionando uma nova conversão de unidades")</span><span class="sxs-lookup"><span data-stu-id="aace6-132">![Adding a new unit conversion](media/uom-new-conversion.png "Adding a new unit conversion")</span></span>

1. <span data-ttu-id="aace6-133">Use os outros campos fornecidos para configurar a conversão de unidades.</span><span class="sxs-lookup"><span data-stu-id="aace6-133">Use the other fields that are provided to set up your unit conversion.</span></span>
1. <span data-ttu-id="aace6-134">Selecione **OK** para salvar a nova conversão de unidades.</span><span class="sxs-lookup"><span data-stu-id="aace6-134">Select **OK** to save the new unit conversion.</span></span>

> [!TIP]
> <span data-ttu-id="aace6-135">Você pode abrir a página **Conversões de unidade** para um produto ou uma grade de produto em qualquer uma das páginas a seguir:</span><span class="sxs-lookup"><span data-stu-id="aace6-135">You can open the **Unit conversions** page for a product or a product variant from any of the following pages:</span></span>
> 
> - <span data-ttu-id="aace6-136">Detalhes do produto</span><span class="sxs-lookup"><span data-stu-id="aace6-136">Product details</span></span>
> - <span data-ttu-id="aace6-137">Detalhes de produtos liberados</span><span class="sxs-lookup"><span data-stu-id="aace6-137">Released products details</span></span>
> - <span data-ttu-id="aace6-138">Grades de produtos liberadas</span><span class="sxs-lookup"><span data-stu-id="aace6-138">Released product variants</span></span>

## <a name="example-scenario"></a><span data-ttu-id="aace6-139">Cenário de exemplo</span><span class="sxs-lookup"><span data-stu-id="aace6-139">Example scenario</span></span>

<span data-ttu-id="aace6-140">Nesse cenário, uma empresa vende camisetas nos tamanhos pequeno, médio, grande e extra grande.</span><span class="sxs-lookup"><span data-stu-id="aace6-140">In this scenario, a company sells T-shirts in sizes small, medium, large, and extra-large.</span></span> <span data-ttu-id="aace6-141">A camiseta é definida como um produto; os diferentes tamanhos são definidos como grades desse produto.</span><span class="sxs-lookup"><span data-stu-id="aace6-141">The T-shirt is defined as a product, and the different sizes are defined as variants of that product.</span></span> <span data-ttu-id="aace6-142">As camisas estão embaladas nas caixas.</span><span class="sxs-lookup"><span data-stu-id="aace6-142">The shirts are packed in boxes.</span></span> <span data-ttu-id="aace6-143">Para tamanhos pequenos, médios e grandes, pode haver cinco camisas em cada caixa.</span><span class="sxs-lookup"><span data-stu-id="aace6-143">For sizes small, medium, and large, there can be five shirts in each box.</span></span> <span data-ttu-id="aace6-144">No entanto, para o tamanho extra-grande, há espaço para apenas quatro camisas em cada caixa.</span><span class="sxs-lookup"><span data-stu-id="aace6-144">However, for size extra-large, there is space for only four shirts in each box.</span></span>

<span data-ttu-id="aace6-145">A empresa deseja rastrear as diferentes grades das camisetas na unidade em *Peças* mas está vendendo as camisetas na unidade *Caixas*.</span><span class="sxs-lookup"><span data-stu-id="aace6-145">The company wants to track the different variants in the *Pieces* unit, but it's selling them in the *Boxes* unit.</span></span> <span data-ttu-id="aace6-146">Para tamanhos pequenos, médios e grandes, a conversão entre a unidade de estoque e a unidade de vendas é de 1 caixa = 5 peças.</span><span class="sxs-lookup"><span data-stu-id="aace6-146">For sizes small, medium, and large, the conversion between the inventory unit and the sales unit is 1 Box = 5 Pieces.</span></span> <span data-ttu-id="aace6-147">Para tamanho extra-grande, a conversão é 1 caixa = 4 peças.</span><span class="sxs-lookup"><span data-stu-id="aace6-147">For size extra-large, the conversion is 1 Box = 4 Pieces.</span></span>

1. <span data-ttu-id="aace6-148">Na página **Detalhes de produto lançados** do produto **Camisa**, abra a página **Conversões de unidade**.</span><span class="sxs-lookup"><span data-stu-id="aace6-148">From the **Released product details** page for the **T-Shirt** product, open the **Unit conversions** page.</span></span>
1. <span data-ttu-id="aace6-149">Na página **Conversões de unidades**, configure a conversão de unidades a seguir para a grade de produtos liberados **Extra Grande**.</span><span class="sxs-lookup"><span data-stu-id="aace6-149">On the **Unit conversions** page, set up the following unit conversion for the **X-Large** released product variant.</span></span>

    | <span data-ttu-id="aace6-150">Campo</span><span class="sxs-lookup"><span data-stu-id="aace6-150">Field</span></span>                 | <span data-ttu-id="aace6-151">Configuração</span><span class="sxs-lookup"><span data-stu-id="aace6-151">Setting</span></span>                 |
    |-----------------------|-------------------------|
    | <span data-ttu-id="aace6-152">Criar conversão para</span><span class="sxs-lookup"><span data-stu-id="aace6-152">Create conversion for</span></span> | <span data-ttu-id="aace6-153">Grade de produto</span><span class="sxs-lookup"><span data-stu-id="aace6-153">Product variant</span></span>         |
    | <span data-ttu-id="aace6-154">Grade de produto</span><span class="sxs-lookup"><span data-stu-id="aace6-154">Product variant</span></span>       | <span data-ttu-id="aace6-155">Camiseta: : extra grande: :</span><span class="sxs-lookup"><span data-stu-id="aace6-155">T-Shirt : : X-Large : :</span></span> |
    | <span data-ttu-id="aace6-156">De unidade</span><span class="sxs-lookup"><span data-stu-id="aace6-156">From unit</span></span>             | <span data-ttu-id="aace6-157">Caixas</span><span class="sxs-lookup"><span data-stu-id="aace6-157">Boxes</span></span>                   |
    | <span data-ttu-id="aace6-158">Fator</span><span class="sxs-lookup"><span data-stu-id="aace6-158">Factor</span></span>                | <span data-ttu-id="aace6-159">4</span><span class="sxs-lookup"><span data-stu-id="aace6-159">4</span></span>                       |
    | <span data-ttu-id="aace6-160">Para unidade</span><span class="sxs-lookup"><span data-stu-id="aace6-160">To Unit</span></span>               | <span data-ttu-id="aace6-161">Peças</span><span class="sxs-lookup"><span data-stu-id="aace6-161">Pieces</span></span>                  |

1. <span data-ttu-id="aace6-162">Como as grades de produto **Pequeno**, **Médio** e **Grande** têm a mesma conversão de unidade entre unidades *Caixa* e *Peças*, você pode definir a conversão de unidade a seguir para elas no produto mestre.</span><span class="sxs-lookup"><span data-stu-id="aace6-162">Because the **Small**, **Medium**, and **Large** product variants all have the same unit conversion between the *Box* and *Pieces* units, you can define the following unit conversion for them on the product master.</span></span>

    | <span data-ttu-id="aace6-163">Campo</span><span class="sxs-lookup"><span data-stu-id="aace6-163">Field</span></span>                 | <span data-ttu-id="aace6-164">Configuração</span><span class="sxs-lookup"><span data-stu-id="aace6-164">Setting</span></span> |
    |-----------------------|---------|
    | <span data-ttu-id="aace6-165">Criar conversão para</span><span class="sxs-lookup"><span data-stu-id="aace6-165">Create conversion for</span></span> | <span data-ttu-id="aace6-166">Produto</span><span class="sxs-lookup"><span data-stu-id="aace6-166">Product</span></span> |
    | <span data-ttu-id="aace6-167">Produto</span><span class="sxs-lookup"><span data-stu-id="aace6-167">Product</span></span>               | <span data-ttu-id="aace6-168">Camiseta</span><span class="sxs-lookup"><span data-stu-id="aace6-168">T-Shirt</span></span> |
    | <span data-ttu-id="aace6-169">De unidade</span><span class="sxs-lookup"><span data-stu-id="aace6-169">From unit</span></span>             | <span data-ttu-id="aace6-170">Caixas</span><span class="sxs-lookup"><span data-stu-id="aace6-170">Boxes</span></span>   |
    | <span data-ttu-id="aace6-171">Fator</span><span class="sxs-lookup"><span data-stu-id="aace6-171">Factor</span></span>                | <span data-ttu-id="aace6-172">5</span><span class="sxs-lookup"><span data-stu-id="aace6-172">5</span></span>       |
    | <span data-ttu-id="aace6-173">Para unidade</span><span class="sxs-lookup"><span data-stu-id="aace6-173">To Unit</span></span>               | <span data-ttu-id="aace6-174">Partes</span><span class="sxs-lookup"><span data-stu-id="aace6-174">Pieces</span></span>  |

## <a name="using-excel-to-update-the-unit-conversions"></a><span data-ttu-id="aace6-175">Usando o Excel para atualizar as conversões de unidade</span><span class="sxs-lookup"><span data-stu-id="aace6-175">Using Excel to update the unit conversions</span></span>

<span data-ttu-id="aace6-176">Se um produto tiver muitas grades de produto com diferentes conversões de unidade, é uma boa ideia exportar as conversões de unidade para uma pasta de trabalho do Microsoft Excel, atualizá-las e publicá-las novamente no Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="aace6-176">If a product has many product variants that have different unit conversions, it's a good idea to export the unit conversions to a Microsoft Excel workbook, update them, and then publish them back to Dynamics 365 Supply Chain Management.</span></span>

<span data-ttu-id="aace6-177">Para exportar conversões de unidade para o Excel, na página **Conversões de unidade**, no Painel de Ações, selecione **Abrir em Microsoft Office**.</span><span class="sxs-lookup"><span data-stu-id="aace6-177">To export unit conversions to Excel, on the **Unit conversions** page, on the Action Pane, select **Open in Microsoft Office**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="aace6-178">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="aace6-178">Additional resources</span></span>

[<span data-ttu-id="aace6-179">Gerenciar unidade de medida</span><span class="sxs-lookup"><span data-stu-id="aace6-179">Manage unit of measure</span></span>](tasks/manage-unit-measure.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]