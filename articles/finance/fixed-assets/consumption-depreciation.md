---
title: Depreciação de consumo
description: Este artigo fornece uma visão geral do Método de consumo de depreciação.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetDepreciationProfile
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 13751
ms.assetid: d25a681f-49a5-4bfc-aa76-1c6373e35dd8
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 2c9d95a7a45ed99c63516749285126c786685c87
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4440229"
---
# <a name="consumption-depreciation"></a><span data-ttu-id="c4e72-103">Depreciação de consumo</span><span class="sxs-lookup"><span data-stu-id="c4e72-103">Consumption depreciation</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="c4e72-104">Este artigo fornece uma visão geral do Método de consumo de depreciação.</span><span class="sxs-lookup"><span data-stu-id="c4e72-104">This article gives an overview of the Consumption method of depreciation.</span></span>

<span data-ttu-id="c4e72-105">Se você configurar um perfil de depreciação para ativos fixos e selecionar **Consumo** no campo **Método** na página **Perfis de depreciação**, os ativos fixos são atribuídos ao perfil de depreciação com base em sua utilização.</span><span class="sxs-lookup"><span data-stu-id="c4e72-105">If you set up a depreciation profile for fixed assets and select **Consumption** in the **Method** field on the **Depreciation profiles** page, fixed assets are assigned to the depreciation profile based on their usage.</span></span> <span data-ttu-id="c4e72-106">Você não precisa definir porcentagens e intervalos na página **Perfis de depreciação**.</span><span class="sxs-lookup"><span data-stu-id="c4e72-106">You don't have to set up percentages and intervals on the **Depreciation profiles** page.</span></span> <span data-ttu-id="c4e72-107">Depois de criar um período de depreciação que utiliza o método de consumo, você pode configurar o método de várias maneiras.</span><span class="sxs-lookup"><span data-stu-id="c4e72-107">After you create a depreciation profile that uses the Consumption method, you can set up the method in various ways.</span></span>

## <a name="set-up-and-use-consumption-depreciation"></a><span data-ttu-id="c4e72-108">Configurar e usar a depreciação de consumo</span><span class="sxs-lookup"><span data-stu-id="c4e72-108">Set up and use consumption depreciation</span></span>
1.  <span data-ttu-id="c4e72-109">Na página **Perfis de depreciação**, crie o perfil de depreciação.</span><span class="sxs-lookup"><span data-stu-id="c4e72-109">On the **Depreciation profiles** page, create the depreciation profile.</span></span> <span data-ttu-id="c4e72-110">Para cálculos de consumo, o perfil de depreciação deve ter uma ID e um nome, e **Consumo** deve ser selecionado no campo **Método**.</span><span class="sxs-lookup"><span data-stu-id="c4e72-110">For consumption calculations, the depreciation profile must have an ID and a name, and **Consumption** must be selected in the **Method** field.</span></span>
2.  <span data-ttu-id="c4e72-111">Na página **Fatores de consumo**, configure os fatores de consumo.</span><span class="sxs-lookup"><span data-stu-id="c4e72-111">On the **Consumption factors** page, set up consumption factors.</span></span> <span data-ttu-id="c4e72-112">Todos os fatores de consumo devem ter uma ID e o nome, e um fator de consumo que é especificado como uma quantidade ou porcentagem.</span><span class="sxs-lookup"><span data-stu-id="c4e72-112">Each consumption factor must have an ID and a name, and a consumption factor that is specified as either a quantity or a percentage.</span></span>
3.  <span data-ttu-id="c4e72-113">Na página **Unidades de consumo**, configure as unidades de consumo.</span><span class="sxs-lookup"><span data-stu-id="c4e72-113">On the **Consumption units** page, set up consumption units.</span></span> <span data-ttu-id="c4e72-114">Cada unidade de consumo devem ter uma ID e um nome.</span><span class="sxs-lookup"><span data-stu-id="c4e72-114">Each consumption unit must have an ID and a name.</span></span> <span data-ttu-id="c4e72-115">As unidades de depreciação são usadas para calcular a depreciação de consumo na página **Depreciação de consumo**.</span><span class="sxs-lookup"><span data-stu-id="c4e72-115">Depreciation units are used to calculate consumption depreciation on the **Consumption depreciation** page.</span></span> <span data-ttu-id="c4e72-116">Exemplos de unidades são quilômetro (km), quilograma (kg) ou hora.</span><span class="sxs-lookup"><span data-stu-id="c4e72-116">Examples of units are kilometer (km), kilogram (kg), and hour.</span></span>
4.  <span data-ttu-id="c4e72-117">Na página **Ativos fixos**, configure ativos fixos individuais.</span><span class="sxs-lookup"><span data-stu-id="c4e72-117">On the **Fixed assets** page, set up individual fixed assets.</span></span> <span data-ttu-id="c4e72-118">Os perfis de depreciação fazem parte do método ou do registro de depreciação selecionado para cada ativo fixo.</span><span class="sxs-lookup"><span data-stu-id="c4e72-118">For each fixed asset, select value models and depreciation books that have depreciation profiles.</span></span> <span data-ttu-id="c4e72-119">Você deve configurar modelos de depreciação ou registros de depreciação para depreciação de consumo se algum de seus ativos fixos utilizar perfis de depreciação com base no método de consumo.</span><span class="sxs-lookup"><span data-stu-id="c4e72-119">You must set up value models or depreciation books for consumption depreciation if any of your fixed assets use depreciation profiles that are based on the Consumption method.</span></span> <span data-ttu-id="c4e72-120">Essa configuração é feita na guia **Depreciação** da página **Modelos de depreciação** ou na Guia Rápida **Geral** da página **Perfil de depreciação**.</span><span class="sxs-lookup"><span data-stu-id="c4e72-120">This setup is done either on the **Depreciation** tab of the **Value models** page or on the **General** FastTab of the **Depreciation profile** page.</span></span> <span data-ttu-id="c4e72-121">É possível usar o mesmo método de depreciação para muitos ativos fixos.</span><span class="sxs-lookup"><span data-stu-id="c4e72-121">You can use the same value model for multiple fixed assets.</span></span> <span data-ttu-id="c4e72-122">Os perfis de depreciação fazem parte do método ou do registro de depreciação selecionado para cada ativo fixo.</span><span class="sxs-lookup"><span data-stu-id="c4e72-122">Depreciation profiles are part of the value model or depreciation book that you select for each fixed asset.</span></span> <span data-ttu-id="c4e72-123">Não é possível adicionar ou modificar perfis de depreciação diretamente na página **Ativos fixos**.</span><span class="sxs-lookup"><span data-stu-id="c4e72-123">You can't add or modify depreciation profiles directly on the **Fixed assets** page.</span></span> <span data-ttu-id="c4e72-124">Você pode modificar perfis de depreciação somente na página **Registros de depreciação**.</span><span class="sxs-lookup"><span data-stu-id="c4e72-124">You can modify depreciation profiles only on the **Depreciation books** page.</span></span>
5.  <span data-ttu-id="c4e72-125">Na página **Modelos de depreciação** ou página **Registros de depreciação**, no grupo de campos **Depreciação de consumo**, insira informações nos seguintes campos.</span><span class="sxs-lookup"><span data-stu-id="c4e72-125">On the **Value models** page or the **Depreciation books** page, in the **Consumption depreciation** field group, enter information in the following fields:</span></span>
    -   <span data-ttu-id="c4e72-126">Fator de consumo</span><span class="sxs-lookup"><span data-stu-id="c4e72-126">Consumption factor</span></span>
    -   <span data-ttu-id="c4e72-127">Unidade</span><span class="sxs-lookup"><span data-stu-id="c4e72-127">Unit</span></span>
    -   <span data-ttu-id="c4e72-128">Depreciação de unidade</span><span class="sxs-lookup"><span data-stu-id="c4e72-128">Unit depreciation</span></span>
    -   <span data-ttu-id="c4e72-129">Consumo estimado</span><span class="sxs-lookup"><span data-stu-id="c4e72-129">Estimated consumption</span></span>

    <span data-ttu-id="c4e72-130">O campo **Consumo lançado** mostra a depreciação de consumo, em unidades, já lançada para a combinação do ativo fixo e método de depreciação, ou para o registro de depreciação.</span><span class="sxs-lookup"><span data-stu-id="c4e72-130">The **Posted consumption** field shows the consumption depreciation, in units, that has already been posted either for the combination of the fixed asset and value model, or for the depreciation book.</span></span> <span data-ttu-id="c4e72-131">Não é possível atualizar manualmente o valor deste campo.</span><span class="sxs-lookup"><span data-stu-id="c4e72-131">You can't manually update the value in this field.</span></span>

## <a name="examples"></a><span data-ttu-id="c4e72-132">Exemplos</span><span class="sxs-lookup"><span data-stu-id="c4e72-132">Examples</span></span>
### <a name="example-1"></a><span data-ttu-id="c4e72-133">Exemplo 1</span><span class="sxs-lookup"><span data-stu-id="c4e72-133">Example 1</span></span>

<span data-ttu-id="c4e72-134">O seguinte fator de consumo é definido para o dia 31 de janeiro:</span><span class="sxs-lookup"><span data-stu-id="c4e72-134">The following consumption factor is set up for January 31:</span></span>

-   <span data-ttu-id="c4e72-135">A quantidade</span><span class="sxs-lookup"><span data-stu-id="c4e72-135">The quantity is 1,000.</span></span>
-   <span data-ttu-id="c4e72-136">O preço unitário de depreciação que é especificado para o ativo fixo é 1,5.</span><span class="sxs-lookup"><span data-stu-id="c4e72-136">The unit depreciation price that is specified for the fixed asset is 1.5.</span></span>

<span data-ttu-id="c4e72-137">A proposta de depreciação em 31 de janeiro é a seguinte: Quantidade × Depreciação de unidade 1.000 × 1,5 = 1.500. Se o fator especificado para o ativo fixo for um fator de porcentagem, a quantidade estimada no campo **Consumo estimado** para o modelo de depreciação do ativo fixo é multiplicada pela porcentagem configurada par a data final selecionada.</span><span class="sxs-lookup"><span data-stu-id="c4e72-137">The depreciation proposal on January 31 is as follows: Quantity × Unit depreciation 1,000 × 1.5 = 1,500 If the factor that is specified for the fixed asset is a percentage factor, the quantity that is estimated in the **Estimated consumption** field for the value model of the fixed asset is multiplied by the percentage that is set up for the selected end date.</span></span> <span data-ttu-id="c4e72-138">A quantidade resultante então é sugerida como a quantidade de depreciação para o período.</span><span class="sxs-lookup"><span data-stu-id="c4e72-138">The resulting quantity is then suggested as the depreciation quantity for the period.</span></span>

### <a name="example-2"></a><span data-ttu-id="c4e72-139">Exemplo 2</span><span class="sxs-lookup"><span data-stu-id="c4e72-139">Example 2</span></span>

<span data-ttu-id="c4e72-140">O seguinte fator da depreciação de consumo está definido para o dia 31 de janeiro:</span><span class="sxs-lookup"><span data-stu-id="c4e72-140">The following factor for consumption depreciation is set up for January 31:</span></span>

-   <span data-ttu-id="c4e72-141">A porcentagem é 10.</span><span class="sxs-lookup"><span data-stu-id="c4e72-141">The percentage is 10 percent.</span></span>
-   <span data-ttu-id="c4e72-142">O preço unitário de depreciação que é especificado para o ativo fixo é 1,5.</span><span class="sxs-lookup"><span data-stu-id="c4e72-142">The unit depreciation price that is specified for the fixed asset is 1.5.</span></span>
-   <span data-ttu-id="c4e72-143">A quantidade prevista do ativo fixo é 2.000.</span><span class="sxs-lookup"><span data-stu-id="c4e72-143">The estimated quantity of the fixed asset is 2,000.</span></span>

<span data-ttu-id="c4e72-144">A proposta de depreciação em 31 de janeiro é a seguinte: Quantidade estimada × Porcentagem × Depreciação de unidade 2.000 × 0,10 × 1,5 = 300</span><span class="sxs-lookup"><span data-stu-id="c4e72-144">The depreciation proposal on January 31 is as follows: Estimated quantity × Percentage × Unit depreciation 2,000 × .10 × 1.5 = 300</span></span>



