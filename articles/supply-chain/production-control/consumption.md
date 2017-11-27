---
title: Calcular o consumo de materiais
description: "Este artigo oferece informações sobre as diversas opções relacionadas ao cálculo do consumo de material."
author: johanhoffmann
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: BOMDesignerEditBOM, BOMTable, ProdBOM
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 53401
ms.assetid: 9cff88e4-0425-4707-9178-3c2cb10df7c2
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: f674a1f0051ee4b228b8a92f717ef5348a452bed
ms.contentlocale: pt-br
ms.lasthandoff: 11/03/2017

---

# <a name="calculate-material-consumption"></a><span data-ttu-id="33ba1-103">Calcular o consumo de materiais</span><span class="sxs-lookup"><span data-stu-id="33ba1-103">Calculate material consumption</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="33ba1-104">Este artigo oferece informações sobre as diversas opções relacionadas ao cálculo do consumo de material.</span><span class="sxs-lookup"><span data-stu-id="33ba1-104">This article provides information about various options that are related to the calculation of material consumption.</span></span> 

<span data-ttu-id="33ba1-105">As opções a seguir relacionadas ao cálculo de consumo de materiais estão disponíveis nas guias **Configuração** e **Consumo em etapas** na Guia Rápida **Detalhes da linha** da página **Lista de materiais**.</span><span class="sxs-lookup"><span data-stu-id="33ba1-105">The following options that are related to the calculation of material consumption are available on the **Setup** and **Step consumption** tabs on the **Line details** FastTab of the **Bill of materials** page.</span></span>

## <a name="variable-and-constant-consumption"></a><span data-ttu-id="33ba1-106">Consumo variável e constante</span><span class="sxs-lookup"><span data-stu-id="33ba1-106">Variable and constant consumption</span></span>
<span data-ttu-id="33ba1-107">No campo **O consumo é**, você pode selecionar se o consumo deve ser calculado como uma quantidade constante ou uma quantidade variável</span><span class="sxs-lookup"><span data-stu-id="33ba1-107">In the **Consumption is** field, you can select whether consumption should be calculated as a constant quantity or a variable quantity.</span></span> <span data-ttu-id="33ba1-108">Selecione **Constante** se um volume ou uma quantidade fixa for necessário para a produção, independentemente da quantidade produzida.</span><span class="sxs-lookup"><span data-stu-id="33ba1-108">Select **Constant** if a fixed quantity or volume is required for the production, regardless of the quantity that is produced.</span></span> <span data-ttu-id="33ba1-109">Selecione **Variável**, que é a configuração padrão, se o valor do material necessário nas mercadorias concluídas for proporcional ao número de mercadorias concluídas produzidas.</span><span class="sxs-lookup"><span data-stu-id="33ba1-109">Select **Variable**, which is the default setting, if the required amount of material in the finished goods is proportional to the number of finished goods that are produced.</span></span>

## <a name="calculating-consumption-from-a-formula"></a><span data-ttu-id="33ba1-110">Cálculo de consumo usando uma fórmula</span><span class="sxs-lookup"><span data-stu-id="33ba1-110">Calculating consumption from a formula</span></span>
<span data-ttu-id="33ba1-111">No campo **Fórmula**, você pode configurar diversas fórmulas para calcular o consumo de materiais.</span><span class="sxs-lookup"><span data-stu-id="33ba1-111">In the **Formula** field, you can set up various formulas for calculating material consumption.</span></span> <span data-ttu-id="33ba1-112">Se você usar o valor padrão, **Padrão**, o consumo não será calculado com uma fórmula.</span><span class="sxs-lookup"><span data-stu-id="33ba1-112">If you use the default value, **Standard**, the consumption isn't calculated from a formula.</span></span> <span data-ttu-id="33ba1-113">As seguintes fórmulas funcionam junto com os campos **Altura**, **Largura**, **Profundidade**, **Densidade** e **Constante**:</span><span class="sxs-lookup"><span data-stu-id="33ba1-113">The following formulas work together with the **Height**, **Width**, **Depth**, **Density**, and **Constant** fields:</span></span>

-   <span data-ttu-id="33ba1-114">Altura \* constante</span><span class="sxs-lookup"><span data-stu-id="33ba1-114">Height \* Constant</span></span>
-   <span data-ttu-id="33ba1-115">Altura \* largura \* constante</span><span class="sxs-lookup"><span data-stu-id="33ba1-115">Height \* Width \* Constant</span></span>
-   <span data-ttu-id="33ba1-116">Altura \* largura \* profundidade \* constante</span><span class="sxs-lookup"><span data-stu-id="33ba1-116">Height \* Width \* Depth \* Constant</span></span>
-   <span data-ttu-id="33ba1-117">(Altura \* largura \* profundidade / densidade) \* constante</span><span class="sxs-lookup"><span data-stu-id="33ba1-117">(Height \* Width \* Depth / Density) \* Constant</span></span>

## <a name="rounding-up-and-multiples"></a><span data-ttu-id="33ba1-118">Arredondamento e múltiplos</span><span class="sxs-lookup"><span data-stu-id="33ba1-118">Rounding up and multiples</span></span>
<span data-ttu-id="33ba1-119">Juntos, os campos **Arredondamento** e **Múltiplos** permitem que você arredonde o valor de consumo de materiais.</span><span class="sxs-lookup"><span data-stu-id="33ba1-119">Together, the **Rounding up** and **Multiples** fields let you round up the material consumption value.</span></span> <span data-ttu-id="33ba1-120">Por exemplo, você pode arredondar o valor de acordo com a unidade de manuseio em que a matéria-prima é separada para a produção.</span><span class="sxs-lookup"><span data-stu-id="33ba1-120">For example, you can round up the value according to the handling unit in which the raw material is picked for production.</span></span> <span data-ttu-id="33ba1-121">As seguintes opções estão disponíveis no campo **Arredondamento**: **Quantidade**, **Medida** e **Consumo**.</span><span class="sxs-lookup"><span data-stu-id="33ba1-121">The following options are available in the **Rounding up** field: **Quantity**, **Measurement**, and **Consumption**.</span></span>

### <a name="quantity"></a><span data-ttu-id="33ba1-122">Quantidade</span><span class="sxs-lookup"><span data-stu-id="33ba1-122">Quantity</span></span>

<span data-ttu-id="33ba1-123">Se você selecionar **Quantidade** como o mecanismo de arredondamento, a quantidade deverá ser um múltiplo da quantidade especificada.</span><span class="sxs-lookup"><span data-stu-id="33ba1-123">If you select **Quantity** as the rounding-up mechanism, the quantity must be a multiple of the specified quantity.</span></span> <span data-ttu-id="33ba1-124">Por exemplo, se forem necessários números inteiros, selecione **1** no campo **Múltiplos**.</span><span class="sxs-lookup"><span data-stu-id="33ba1-124">For example, if whole numbers are required, select **1** in the **Multiples** field.</span></span> <span data-ttu-id="33ba1-125">Os números serão arredondados até uma quantidade que seja divisível por 1.</span><span class="sxs-lookup"><span data-stu-id="33ba1-125">Numbers are then rounded up to a quantity that is divisible by 1.</span></span>

### <a name="measurement"></a><span data-ttu-id="33ba1-126">Medida</span><span class="sxs-lookup"><span data-stu-id="33ba1-126">Measurement</span></span>

<span data-ttu-id="33ba1-127">Normalmente, você selecionará **Medida** como o mecanismo de arredondamento quando a matéria-prima tiver dimensões específicas.</span><span class="sxs-lookup"><span data-stu-id="33ba1-127">Typically, you select **Measurement** as the rounding-up mechanism when the raw material comes in specific dimensions.</span></span> <span data-ttu-id="33ba1-128">Por exemplo, uma peça de tubo de metal de dois metros é necessária para uma mercadoria concluída, e o tubo de metal é armazenado em comprimentos de 4,5 metros.</span><span class="sxs-lookup"><span data-stu-id="33ba1-128">For example, a piece of 2-meter metal tube is required for a finished good, and the metal tube is stored in 4.5-meter lengths.</span></span> <span data-ttu-id="33ba1-129">Nesse caso, o mecanismo de arredondamento de **Medida** pode ser usado para calcular quantos tubos de metal são necessários para produzir um número específico de peças da mercadoria concluída.</span><span class="sxs-lookup"><span data-stu-id="33ba1-129">In this case, the **Measurement** rounding-up mechanism can be used to calculate how many metal tubes are required to produce a specific number of pieces of the finished good.</span></span> <span data-ttu-id="33ba1-130">Para esse exemplo, o campo **Fórmula** é definido como **Altura \* Constante**.</span><span class="sxs-lookup"><span data-stu-id="33ba1-130">For this example, the **Formula** field is set to **Height \* Constant**.</span></span> <span data-ttu-id="33ba1-131">O campo **Altura** definido como **2** para indicar o comprimento do tubo exigido para a mercadoria concluída.</span><span class="sxs-lookup"><span data-stu-id="33ba1-131">The **Height** field is set to **2** to indicate the length of the tube that is required for the finished good.</span></span> <span data-ttu-id="33ba1-132">O campo **Múltiplo** é definido como **4,5** para indicar que o tubo será separado em comprimentos de 4,5 metros.</span><span class="sxs-lookup"><span data-stu-id="33ba1-132">The **Multiple** field is set to **4.5** to indicate that the tube is picked in lengths of 4.5 meters.</span></span> <span data-ttu-id="33ba1-133">Este é o cálculo:</span><span class="sxs-lookup"><span data-stu-id="33ba1-133">Here is the calculation:</span></span>

1.  <span data-ttu-id="33ba1-134">Número de múltiplos necessários para 10 peças da mercadoria concluída: 10 ÷ 2 = 5 peças</span><span class="sxs-lookup"><span data-stu-id="33ba1-134">Number of multiples that are required for 10 pieces of the finished good: 10 ÷ 2 = 5 pieces</span></span>
2.  <span data-ttu-id="33ba1-135">Consumo total: 4,5 × 5 = 22,5 metros de tubo de metal</span><span class="sxs-lookup"><span data-stu-id="33ba1-135">Total consumption:  4.5 × 5 = 22.5 meters of metal tube</span></span>

<span data-ttu-id="33ba1-136">Presume-se que 0,5 metro de tubo será sucateado para cada cinco peças de tubo consumidas.</span><span class="sxs-lookup"><span data-stu-id="33ba1-136">It's assumed that 0.5 meter of tube is scrapped for every five pieces of tube that are consumed.</span></span>

### <a name="consumption"></a><span data-ttu-id="33ba1-137">Consumo</span><span class="sxs-lookup"><span data-stu-id="33ba1-137">Consumption</span></span>

<span data-ttu-id="33ba1-138">Normalmente, você seleciona**Consumo** como o mecanismo de arredondamento quando a matéria-prima deve ser separada em quantidades inteiras de uma unidade de manuseio específica do produto.</span><span class="sxs-lookup"><span data-stu-id="33ba1-138">Typically, you select **Consumption** as the rounding-up mechanism when raw material must be picked in whole quantities of a specific handling unit of the product.</span></span> <span data-ttu-id="33ba1-139">Por exemplo, 2 ml de tinta são usados para produzir uma peça de uma mercadoria concluída, e a tinta é escolhida em latas de 25 litros.</span><span class="sxs-lookup"><span data-stu-id="33ba1-139">For example, 2 quarts of paint are used to produce one piece of a finished good, and the paint is picked in 25-quart cans.</span></span> <span data-ttu-id="33ba1-140">Nesse caso, o mecanismo de arredondamento de **Consumo** pode ser usado para arredondar o consumo para números inteiros de 25 litros.</span><span class="sxs-lookup"><span data-stu-id="33ba1-140">In this case, the **Consumption** rounding-up mechanism can be used to round up consumption to whole numbers of 25-quart cans.</span></span> <span data-ttu-id="33ba1-141">Veja o cálculo para a quantidade de tinta necessária caso 180 peças da mercadoria concluída tenham de ser produzidas:</span><span class="sxs-lookup"><span data-stu-id="33ba1-141">Here is the calculation for the amount of paint that is required if 180 pieces of the finished good must be produced:</span></span>

1.  <span data-ttu-id="33ba1-142">A tinta necessária, excluindo a sucata: 180 × 2 = 360 ml.</span><span class="sxs-lookup"><span data-stu-id="33ba1-142">Paint that is required, excluding scrap: 180 × 2 = 360 quarts</span></span>
2.  <span data-ttu-id="33ba1-143">Número de latas: 360 ÷ 25 = 14,4, que é arredondado para 15</span><span class="sxs-lookup"><span data-stu-id="33ba1-143">Number of cans: 360 ÷ 25 = 14.4, which is rounded up to 15</span></span>
3.  <span data-ttu-id="33ba1-144">A tinta necessária, incluindo a sucata: 15 × 25 = 375 ml.</span><span class="sxs-lookup"><span data-stu-id="33ba1-144">Paint that is required, including scrap: 15 × 25 = 375 quarts</span></span>

## <a name="step-consumption"></a><span data-ttu-id="33ba1-145">Consumo em etapas</span><span class="sxs-lookup"><span data-stu-id="33ba1-145">Step consumption</span></span>
<span data-ttu-id="33ba1-146">O consumo em etapas é usado para calcular o consumo constante em intervalos de quantidade.</span><span class="sxs-lookup"><span data-stu-id="33ba1-146">Step consumption is used to calculate constant consumption in quantity intervals.</span></span> <span data-ttu-id="33ba1-147">Se você selecionar **Consumo em etapas** no campo **Fórmula** na guia **Configuração**, você pode adicionar informações sobre as etapas na guia **Consumo da etapa**. A quantidade consumida fixa pode ser configurada em intervalos da quantidade produzida.</span><span class="sxs-lookup"><span data-stu-id="33ba1-147">If you select **Step consumption** in the **Formula** field on the **Setup** tab, you can add information about the steps on the **Step consumption** tab. The fixed consumed quantity can be set up in intervals of the produced quantity.</span></span> <span data-ttu-id="33ba1-148">Por exemplo, o consumo em etapas é configurado como mostrado na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="33ba1-148">For example, step consumption is set up as shown in the following table.</span></span>

| <span data-ttu-id="33ba1-149">Da série</span><span class="sxs-lookup"><span data-stu-id="33ba1-149">From series</span></span> | <span data-ttu-id="33ba1-150">Quantidade</span><span class="sxs-lookup"><span data-stu-id="33ba1-150">Quantity</span></span> |
|-------------|----------|
| <span data-ttu-id="33ba1-151">0,00</span><span class="sxs-lookup"><span data-stu-id="33ba1-151">0.00</span></span>        | <span data-ttu-id="33ba1-152">10,0000</span><span class="sxs-lookup"><span data-stu-id="33ba1-152">10.0000</span></span>  |
| <span data-ttu-id="33ba1-153">100,00</span><span class="sxs-lookup"><span data-stu-id="33ba1-153">100.00</span></span>      | <span data-ttu-id="33ba1-154">20,0000</span><span class="sxs-lookup"><span data-stu-id="33ba1-154">20.0000</span></span>  |
| <span data-ttu-id="33ba1-155">200,00</span><span class="sxs-lookup"><span data-stu-id="33ba1-155">200.00</span></span>      | <span data-ttu-id="33ba1-156">40,0000</span><span class="sxs-lookup"><span data-stu-id="33ba1-156">40.0000</span></span>  |

<span data-ttu-id="33ba1-157">A quantidade da lista de materiais (BOM) é 1, a quantidade de produção é 110.</span><span class="sxs-lookup"><span data-stu-id="33ba1-157">The bill of materials (BOM) quantity is 1, and the production quantity is 110.</span></span> <span data-ttu-id="33ba1-158">A fórmula para o consumo é De séries (Quantidade) = Consume.</span><span class="sxs-lookup"><span data-stu-id="33ba1-158">The formula for the consumption is From series (Quantity) = Consumption.</span></span> <span data-ttu-id="33ba1-159">Como a quantidade de produção é 110, ela recai na "série A partir de 100".</span><span class="sxs-lookup"><span data-stu-id="33ba1-159">Because the production quantity is 110, it falls into the "From 100 series."</span></span> <span data-ttu-id="33ba1-160">Portanto, a quantidade é 20.</span><span class="sxs-lookup"><span data-stu-id="33ba1-160">Therefore, the quantity is 20.</span></span>




