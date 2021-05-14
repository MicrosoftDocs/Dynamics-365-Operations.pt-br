---
title: Gerenciar unidades de medida
description: Este tópico descreve como definir uma unidade de medida, fornecer traduções para a unidade e sua descrição, e definir regras de conversão para unidades relacionadas.
author: sorenva
ms.date: 04/09/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: EcoResProductMaintainWorkspace, EcoResProductOpenCasesFormPart, UnitOfMeasure, UnitOfMeasureReportingTranslation, UnitOfMeasureTranslation, UnitOfMeasureConversion, UnitOfMeasureConversionEditOrCreate, UnitOfMeasureLookup, UnitOfMeasureCalculator, UnitOfMeasureWizard, UnitOfMeasureLookupTest
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: sorenand
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d36839cd8e3398225d3421bf0f268068599ca49f
ms.sourcegitcommit: fa99a36c3d30d0c0577fd3f63ed6bf2f71599e40
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/20/2021
ms.locfileid: "5921332"
---
# <a name="manage-units-of-measure"></a><span data-ttu-id="b1736-103">Gerenciar unidades de medida</span><span class="sxs-lookup"><span data-stu-id="b1736-103">Manage units of measure</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="b1736-104">Este tópico descreve como definir uma unidade de medida, fornecer traduções para a unidade e sua descrição, e definir regras de conversão para unidades relacionadas.</span><span class="sxs-lookup"><span data-stu-id="b1736-104">This topic describes how to define a unit of measure, provide translations for the unit and its description, and define conversion rules for related units.</span></span>

## <a name="open-the-units-page"></a><span data-ttu-id="b1736-105">Abra a página Unidades</span><span class="sxs-lookup"><span data-stu-id="b1736-105">Open the Units page</span></span>

<span data-ttu-id="b1736-106">Para criar e trabalhar com as unidades de medida disponíveis no sistema, acesse **Administração da organização \> Configuração \> Unidades \> Unidades**.</span><span class="sxs-lookup"><span data-stu-id="b1736-106">To create and work with the units of measure that are available in your system, go to **Organization administration \> Setup \> Units \> Units**.</span></span>

<span data-ttu-id="b1736-107">As demais seções deste tópico descrevem o que você pode fazer na página **Unidades**.</span><span class="sxs-lookup"><span data-stu-id="b1736-107">The remaining sections of this topic describe what you can do on the **Units** page.</span></span>

## <a name="create-standard-units-and-conversions"></a><span data-ttu-id="b1736-108">Criar unidades e conversões padrão</span><span class="sxs-lookup"><span data-stu-id="b1736-108">Create standard units and conversions</span></span>

<span data-ttu-id="b1736-109">Se o sistema ainda não incluir as unidades de medida mais usadas para o sistema métrico e/ou o USCS (sistema de unidades de medidas dos EUA), o assistente de configuração da unidade poderá ajudá-lo a iniciar rapidamente as definições e conversões de unidades básicas.</span><span class="sxs-lookup"><span data-stu-id="b1736-109">If your system doesn't already include the most commonly used units of measure for the metric system and/or the US customary system (USCS), the unit setup wizard can help you quickly get started with basic unit definitions and conversions.</span></span> <span data-ttu-id="b1736-110">Para concluir o assistente, selecione **Assistente de criação de unidade** no Painel de Ações e siga as instruções na tela.</span><span class="sxs-lookup"><span data-stu-id="b1736-110">To complete the wizard, select **Unit creation wizard** on the Action Pane, and then follow the on-screen instructions.</span></span>

## <a name="create-or-edit-a-unit-of-measure"></a><span data-ttu-id="b1736-111">Criar ou editar uma unidade de medida</span><span class="sxs-lookup"><span data-stu-id="b1736-111">Create or edit a unit of measure</span></span>

<span data-ttu-id="b1736-112">Para criar ou editar uma unidade de medida, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="b1736-112">To create or edit a unit of measure, follow these steps.</span></span>

1. <span data-ttu-id="b1736-113">Siga uma destas etapas:</span><span class="sxs-lookup"><span data-stu-id="b1736-113">Follow one of these steps:</span></span>

    - <span data-ttu-id="b1736-114">Para editar uma unidade existente, selecione-a no painel de lista.</span><span class="sxs-lookup"><span data-stu-id="b1736-114">To edit an existing unit, select it in the list pane.</span></span>
    - <span data-ttu-id="b1736-115">Para criar uma nova unidade, selecione **Novo** no Painel de Ações.</span><span class="sxs-lookup"><span data-stu-id="b1736-115">To create a new unit, select **New** on the Action Pane.</span></span>

1. <span data-ttu-id="b1736-116">No cabeçalho do registro, defina os seguintes campos:</span><span class="sxs-lookup"><span data-stu-id="b1736-116">On the header of the record, set the following fields:</span></span>

    - <span data-ttu-id="b1736-117">**Unidade** – insira a ID ou o símbolo a ser usado para fazer referência à unidade no idioma do sistema.</span><span class="sxs-lookup"><span data-stu-id="b1736-117">**Unit** – Enter the ID or symbol to use to refer to the unit in the system language.</span></span> <span data-ttu-id="b1736-118">Essa ID ou símbolo é geralmente uma abreviação comum da unidade, como *ea* para cada ou *cm* para centímetro.</span><span class="sxs-lookup"><span data-stu-id="b1736-118">This ID or symbol is usually a common abbreviation for the unit, such as *ea* for each or *cm* for centimeter.</span></span>
    - <span data-ttu-id="b1736-119">**Descrição** – insira um nome descritivo para a unidade no idioma do sistema.</span><span class="sxs-lookup"><span data-stu-id="b1736-119">**Description** – Enter a descriptive name for the unit in the system language.</span></span> <span data-ttu-id="b1736-120">Esse nome costuma ser o nome completo da unidade, como *Cada* ou *Centímetro*.</span><span class="sxs-lookup"><span data-stu-id="b1736-120">This name is usually the full name of the unit, such as *Each* or *Centimeter*.</span></span>

1. <span data-ttu-id="b1736-121">Na Guia Rápida **Geral**, defina os seguintes campos:</span><span class="sxs-lookup"><span data-stu-id="b1736-121">On the **General** FastTab, set the following fields:</span></span><!-- KFM: confirm this:    - **Fixed unit assignment** and **Fixed unit** – These fields have an effect only if you're using the Microsoft Retail Essentials product. If the current unit can be mapped to one of the fixed units that are used by Retail Essentials, set the **Fixed unit assignment** option to *Yes*. Then select the fixed unit in the **Fixed unit** field. -->

    - <span data-ttu-id="b1736-122">**Classe de unidade** – selecione a propriedade que a unidade mede (como comprimento, área, massa ou quantidade).</span><span class="sxs-lookup"><span data-stu-id="b1736-122">**Unit class** – Select the property that the unit measures (such as length, area, mass, or quantity).</span></span>
    - <span data-ttu-id="b1736-123">**Sistema de unidades** – selecione o sistema de medição ao qual a unidade pertence (*Unidades métricas* ou *Unidades personalizadas dos Estados Unidos*).</span><span class="sxs-lookup"><span data-stu-id="b1736-123">**System of units** – Select the measurement system that the unit belongs to (*Metric units* or *United States customary units*).</span></span>
    - <span data-ttu-id="b1736-124">**Unidade base** – defina esta opção como *Sim* para usar a unidade atual como a unidade base da sua classe de unidade.</span><span class="sxs-lookup"><span data-stu-id="b1736-124">**Base unit** – Set this option to *Yes* to use the current unit as the base unit for its unit class.</span></span> <span data-ttu-id="b1736-125">Nesse caso, você só precisa especificar o fator de conversão entre a unidade base e cada unidade adicional na classe de unidade.</span><span class="sxs-lookup"><span data-stu-id="b1736-125">In this case, you only have to specify the conversion factor between the base unit and each additional unit in the unit class.</span></span> <span data-ttu-id="b1736-126">O sistema pode converter entre todas as unidades dessa classe de unidade.</span><span class="sxs-lookup"><span data-stu-id="b1736-126">The system can then convert between all units in that unit class.</span></span> <span data-ttu-id="b1736-127">Portanto, é mais fácil configurar conversões.</span><span class="sxs-lookup"><span data-stu-id="b1736-127">Therefore, it's easier to set up conversions.</span></span>

        <span data-ttu-id="b1736-128">Por exemplo, se galão for a unidade base para a classe da unidade *Volume*, você só precisará configurar fatores de conversão de quarto para galão e de litro para galão.</span><span class="sxs-lookup"><span data-stu-id="b1736-128">For example, if gallon is the base unit for the *Volume* unit class, you only have to set up conversion factors from quart to gallon and from pint to gallon.</span></span> <span data-ttu-id="b1736-129">O sistema pode, então, ser convertido de quarto para litro.</span><span class="sxs-lookup"><span data-stu-id="b1736-129">The system can then also convert from quart to pint.</span></span>

        <span data-ttu-id="b1736-130">Só é possível ter uma unidade base por classe de unidade.</span><span class="sxs-lookup"><span data-stu-id="b1736-130">You can have only one base unit per unit class.</span></span>

    - <span data-ttu-id="b1736-131">**Unidade do sistema** – defina esta opção como *Sim* para usar a unidade atual como a unidade presumida de todas as medidas na classe de unidade.</span><span class="sxs-lookup"><span data-stu-id="b1736-131">**System unit** – Set this option to *Yes* to use the current unit as the assumed unit for all unspecified measurements in its unit class.</span></span> <span data-ttu-id="b1736-132">Por exemplo, se um campo usado para inserir uma quantidade não permitir que uma unidade seja especificada (ou se o usuário não selecionar uma unidade), o sistema usará a unidade definida como a unidade do sistema para a classe de unidade *Quantidade*.</span><span class="sxs-lookup"><span data-stu-id="b1736-132">For example, if a field that is used to enter a quantity doesn't allow a unit to be specified (of if the user doesn't select a unit), the system uses the unit that is set as the system unit for the *Quantity* unit class.</span></span> <span data-ttu-id="b1736-133">Só é possível ter uma unidade de sistema por classe de unidade.</span><span class="sxs-lookup"><span data-stu-id="b1736-133">You can have only one system unit per unit class.</span></span>
    - <span data-ttu-id="b1736-134">**Precisão decimal** – especifique o número de casas decimais para arredondamento de valores especificados para a unidade atual ou convertidas nela.</span><span class="sxs-lookup"><span data-stu-id="b1736-134">**Decimal precision** – Specify the number of decimal places that values that are specified for the current unit or converted to it should be rounded to.</span></span>

1. <span data-ttu-id="b1736-135">No Painel de ações, selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="b1736-135">On the Action Pane, select **Save**.</span></span>

## <a name="define-unit-translations"></a><span data-ttu-id="b1736-136">Definir traduções de unidades</span><span class="sxs-lookup"><span data-stu-id="b1736-136">Define unit translations</span></span>

<span data-ttu-id="b1736-137">Para definir traduções para a ID ou o símbolo e a descrição de uma unidade de medida, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="b1736-137">To define translations for the ID or symbol and the description for a unit of measure, follow these steps.</span></span>

1. <span data-ttu-id="b1736-138">Crie ou selecione a unidade para a qual traduções serão criadas.</span><span class="sxs-lookup"><span data-stu-id="b1736-138">Create or select the unit to create translations for.</span></span>
1. <span data-ttu-id="b1736-139">No Painel de Ações, selecione **Textos de unidade**.</span><span class="sxs-lookup"><span data-stu-id="b1736-139">On the Action Pane, select **Unit texts**.</span></span>

    <span data-ttu-id="b1736-140">A página **Textos de unidade** é exibida.</span><span class="sxs-lookup"><span data-stu-id="b1736-140">The **Unit texts** page appears.</span></span> <span data-ttu-id="b1736-141">Use esta página para definir traduções para a ID ou o símbolo da unidade selecionada.</span><span class="sxs-lookup"><span data-stu-id="b1736-141">You use this page to define translations for the ID or symbol for the selected unit.</span></span> <span data-ttu-id="b1736-142">Essas traduções podem ser usadas em documentos externos em idiomas específicos do cliente ou do fornecedor.</span><span class="sxs-lookup"><span data-stu-id="b1736-142">Those translations can then be used on external documents in customer-specific or vendor-specific languages.</span></span>

1. <span data-ttu-id="b1736-143">No Painel de Ações, selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="b1736-143">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="b1736-144">No campo **Idioma**, selecione o idioma para o qual a ID de unidade ou o símbolo será traduzido.</span><span class="sxs-lookup"><span data-stu-id="b1736-144">In the **Language** field, select the language to translate the unit ID or symbol to.</span></span>
1. <span data-ttu-id="b1736-145">No campo **Texto**, insira a tradução da ID da unidade ou o símbolo no idioma selecionado.</span><span class="sxs-lookup"><span data-stu-id="b1736-145">In the **Text** field, enter the translation of the unit ID or symbol in the selected language.</span></span>
1. <span data-ttu-id="b1736-146">No Painel de ações, selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="b1736-146">On the Action Pane, select **Save**.</span></span>
1. <span data-ttu-id="b1736-147">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="b1736-147">Close the page.</span></span>
1. <span data-ttu-id="b1736-148">No **Painel de Ações**, selecione **Descrições da unidade traduzida**.</span><span class="sxs-lookup"><span data-stu-id="b1736-148">On the **Action Pane**, select **Translated unit descriptions**.</span></span>

    <span data-ttu-id="b1736-149">A página **Descrições da unidade traduzida** aparece.</span><span class="sxs-lookup"><span data-stu-id="b1736-149">The **Translated unit descriptions** page appears.</span></span> <span data-ttu-id="b1736-150">Use esta página para definir descrições específicas do idioma para a unidade selecionada.</span><span class="sxs-lookup"><span data-stu-id="b1736-150">You use this page to define language-specific descriptions for the selected unit.</span></span>

1. <span data-ttu-id="b1736-151">No Painel de Ações, selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="b1736-151">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="b1736-152">No campo **Idioma**, selecione o idioma para o qual a descrição de unidade será traduzida.</span><span class="sxs-lookup"><span data-stu-id="b1736-152">In the **Language** field, select the language to translate the unit description to.</span></span>
1. <span data-ttu-id="b1736-153">No campo **Descrição**, insira a tradução da descrição da unidade no idioma selecionado.</span><span class="sxs-lookup"><span data-stu-id="b1736-153">In the **Description** field, enter the translation of the unit description in the selected language.</span></span>
1. <span data-ttu-id="b1736-154">No Painel de ações, selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="b1736-154">On the Action Pane, select **Save**.</span></span>
1. <span data-ttu-id="b1736-155">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="b1736-155">Close the page.</span></span>

## <a name="define-unit-conversion-rules"></a><span data-ttu-id="b1736-156">Definir regras de conversão de unidades</span><span class="sxs-lookup"><span data-stu-id="b1736-156">Define unit conversion rules</span></span>

<span data-ttu-id="b1736-157">Para definir regras para conversões entre unidades de medida, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="b1736-157">To define rules for conversions between units of measure, follow these steps.</span></span>

1. <span data-ttu-id="b1736-158">Crie ou selecione a unidade para a qual regras de conversão serão definidas.</span><span class="sxs-lookup"><span data-stu-id="b1736-158">Create or select the unit to define conversion rules for.</span></span>
1. <span data-ttu-id="b1736-159">No Painel de Ações, selecione **Conversões de unidade**.</span><span class="sxs-lookup"><span data-stu-id="b1736-159">On the Action Pane, select **Unit conversions**.</span></span>

    <span data-ttu-id="b1736-160">A página **Conversões de unidade** aparece.</span><span class="sxs-lookup"><span data-stu-id="b1736-160">The **Unit conversions** page appears.</span></span> <span data-ttu-id="b1736-161">Use esta página para definir regras de conversão da unidade selecionada de e para outras unidades na classe de unidade.</span><span class="sxs-lookup"><span data-stu-id="b1736-161">You use this page to define rules for converting the selected unit to and from other units in the unit class.</span></span>

1. <span data-ttu-id="b1736-162">Selecione uma das seguintes guias, de acordo com o tipo de conversão a ser configurada:</span><span class="sxs-lookup"><span data-stu-id="b1736-162">Select one of the following tabs, depending on the type of conversion that you want to set up:</span></span>

    - <span data-ttu-id="b1736-163">**Conversões padrão** – configure regras de conversão padrão para todos os produtos.</span><span class="sxs-lookup"><span data-stu-id="b1736-163">**Standard conversions** – Set up standard conversion rules for all products.</span></span>
    - <span data-ttu-id="b1736-164">**Conversões na mesma classe** – configure regras de conversão específicas de produtos para unidades na mesma classe de unidade.</span><span class="sxs-lookup"><span data-stu-id="b1736-164">**Intra-class conversions** – Set up product-specific conversion rules for units in the same unit class.</span></span>
    - <span data-ttu-id="b1736-165">**Conversões entre classes** – configure regras de conversão específicas de produtos para unidades entre classes de unidade.</span><span class="sxs-lookup"><span data-stu-id="b1736-165">**Inter-class conversions** – Set up product-specific conversion rules for units across unit classes.</span></span>

1. <span data-ttu-id="b1736-166">Siga uma destas etapas:</span><span class="sxs-lookup"><span data-stu-id="b1736-166">Follow one of these steps:</span></span>

    - <span data-ttu-id="b1736-167">Para criar uma nova conversão, selecione **Novo** no barra de ferramentas.</span><span class="sxs-lookup"><span data-stu-id="b1736-167">To create a new conversion, select **New** on the toolbar.</span></span>
    - <span data-ttu-id="b1736-168">Para editar uma conversão existente, selecione a conversão na grade e, depois, selecione **Editar** na barra de ferramentas.</span><span class="sxs-lookup"><span data-stu-id="b1736-168">To edit an existing conversion, select the conversion in the grid, and then select **Edit** on the toolbar.</span></span>

1. <span data-ttu-id="b1736-169">Na caixa de diálogo suspensa que aparecer, defina os seguintes campos:</span><span class="sxs-lookup"><span data-stu-id="b1736-169">In the drop-down dialog box that appears, set the following fields:</span></span>

    - <span data-ttu-id="b1736-170">**Produto** – selecione o produto específico ao qual a conversão se aplica.</span><span class="sxs-lookup"><span data-stu-id="b1736-170">**Product** – Select the specific product that the conversion applies to.</span></span> <span data-ttu-id="b1736-171">Este campo está disponível somente para conversões na mesma classe e entre classes.</span><span class="sxs-lookup"><span data-stu-id="b1736-171">This field is available only for intra-class and inter-class conversions.</span></span>
    - <span data-ttu-id="b1736-172">**Layout da fórmula** – deixe este campo definido como *Simples* para especificar uma conversão simples que tenha um único fator.</span><span class="sxs-lookup"><span data-stu-id="b1736-172">**Formula layout** – Leave this field set to *Simple* to specify a simple conversion that has a single factor.</span></span> <span data-ttu-id="b1736-173">Defina-o como *Avançado* para configurar uma equação mais complexa.</span><span class="sxs-lookup"><span data-stu-id="b1736-173">Set it to *Advanced* to set up a more complex equation.</span></span> <span data-ttu-id="b1736-174">O formato das equações avançadas varia, dependendo da classe de unidade.</span><span class="sxs-lookup"><span data-stu-id="b1736-174">The format for advanced equations varies, depending on the unit class.</span></span>
    - <span data-ttu-id="b1736-175">**Da unidade** – este campo mostra a unidade selecionada.</span><span class="sxs-lookup"><span data-stu-id="b1736-175">**From unit** – This field shows the selected unit.</span></span> <span data-ttu-id="b1736-176">Normalmente, você não deve alterar o valor.</span><span class="sxs-lookup"><span data-stu-id="b1736-176">Usually, you should not change the value.</span></span> <span data-ttu-id="b1736-177">(Se você alterar o valor, deverá abrir a página **Conversões de unidade** da unidade selecionada para exibir a nova conversão após salvá-la.)</span><span class="sxs-lookup"><span data-stu-id="b1736-177">(If you do change the value, you must open the **Unit conversions** page for the selected unit to view your new conversion after you save it.)</span></span>
    - <span data-ttu-id="b1736-178">**Para unidade** – selecione a unidade a ser convertida.</span><span class="sxs-lookup"><span data-stu-id="b1736-178">**To unit** – Select the unit to convert to.</span></span>
    - <span data-ttu-id="b1736-179">**Arredondamento** – selecione como frações devem ser arredondadas, com base no valor **Precisão decimal** da unidade selecionada (*Para o mais próximo*, *Para cima* ou *Para baixo*).</span><span class="sxs-lookup"><span data-stu-id="b1736-179">**Rounding** – Select how fractions should be rounded, based on the **Decimal precision** value of the selected unit (*To nearest*, *Up*, or *Down*).</span></span>
    - <span data-ttu-id="b1736-180">**Fórmula de conversão** – use os campos restantes na parte superior da caixa de diálogo suspensa para especificar a fórmula para a conversão entre as duas unidades.</span><span class="sxs-lookup"><span data-stu-id="b1736-180">**Conversion formula** – Use the remaining fields at the top of the drop-down dialog box to specify the formula for converting between the two units.</span></span> <span data-ttu-id="b1736-181">Os campos disponíveis variam de acordo com a classe de unidade e o layout da fórmula selecionados.</span><span class="sxs-lookup"><span data-stu-id="b1736-181">The available fields vary, depending on the unit class and formula layout that you've selected.</span></span>

1. <span data-ttu-id="b1736-182">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="b1736-182">Select **OK**.</span></span>
1. <span data-ttu-id="b1736-183">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="b1736-183">Close the page.</span></span>

> [!TIP]
> <span data-ttu-id="b1736-184">Você também pode configurar conversões de unidades por grade de produto.</span><span class="sxs-lookup"><span data-stu-id="b1736-184">You can also set up unit conversions per product variant.</span></span> <span data-ttu-id="b1736-185">Para obter mais informações, consulte [Conversão de unidade de medida por grade de produto](../uom-conversion-per-product-variant.md).</span><span class="sxs-lookup"><span data-stu-id="b1736-185">For more information, see [Unit of measure conversion per product variant](../uom-conversion-per-product-variant.md).</span></span>

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
