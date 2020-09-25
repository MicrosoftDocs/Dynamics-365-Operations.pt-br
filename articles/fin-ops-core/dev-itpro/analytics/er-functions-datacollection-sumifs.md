---
title: Função SUMIFS ER
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) SUMIFS é usada.
author: NickSelin
manager: kfend
ms.date: 12/04/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a6815a8c9f4141649532f9cd56ac3bc442b48686
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/01/2020
ms.locfileid: "3743318"
---
# <a name="sumifs-er-function"></a><span data-ttu-id="ab7c4-103">Função SUMIFS ER</span><span class="sxs-lookup"><span data-stu-id="ab7c4-103">SUMIFS ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="ab7c4-104">A função `SUMIFS` retorna um valor *Real* que representa a soma de valores que foram retornados por associações de elementos de formato e coletados quando os elementos de formato foram usados para gerar um documento de saída durante a execução do formato, e que satisfaçam as condições especificadas.</span><span class="sxs-lookup"><span data-stu-id="ab7c4-104">The `SUMIFS` function returns a *Real* value that represents the sum of values that were returned by bindings of format elements and collected when the format elements were used to generate an outbound document during the format run, and that satisfies the specified conditions.</span></span> <span data-ttu-id="ab7c4-105">Cada condição consiste em um intervalo de chaves e um valor de chave.</span><span class="sxs-lookup"><span data-stu-id="ab7c4-105">Each condition consists of a key range and a key value.</span></span>

## <a name="syntax"></a><span data-ttu-id="ab7c4-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="ab7c4-106">Syntax</span></span>

```vb
SUMIFS (key name for summing, condition 1 range, condition 1 value[, condition 2 range, condition 2 value, …, condition N range, condition N value])
```

## <a name="arguments"></a><span data-ttu-id="ab7c4-107">Argumentos</span><span class="sxs-lookup"><span data-stu-id="ab7c4-107">Arguments</span></span>

<span data-ttu-id="ab7c4-108">`key name for summing`: *Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="ab7c4-108">`key name for summing`: *String*</span></span>

<span data-ttu-id="ab7c4-109">Um valor retornado pela expressão que foi configurada na propriedade **Nome da chave de dados coletados** do componente de formato de relatório eletrônico (ER) para o qual o valor da associação deve ser usado para fins de soma.</span><span class="sxs-lookup"><span data-stu-id="ab7c4-109">A value that is returned by the expression that has been configured in the **Collected data key name** property of the Electronic reporting (ER) format component for which the value of the binding must be used for summing purposes.</span></span>

<span data-ttu-id="ab7c4-110">A propriedade **Nome da chave de dados coletada** pode ser configurada para um componente **Numérico** ou um componente **Cadeia de caracteres** de um formato de ER que está no componente **Arquivo \\ comum** onde a opção **Coletar detalhes de saída** está ativada.</span><span class="sxs-lookup"><span data-stu-id="ab7c4-110">The **Collected data key name** property can be configured for either a **Numeric** component or a **String** component of an ER format that resides under the **Common\\File** component where the **Collect output details** option is turned on.</span></span>

<span data-ttu-id="ab7c4-111">`condition 1 range`: *Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="ab7c4-111">`condition 1 range`: *String*</span></span>

<span data-ttu-id="ab7c4-112">Um valor retornado pela expressão que foi configurada na propriedade **Nome da chave de dados coletada** de um componente de formato de ER.</span><span class="sxs-lookup"><span data-stu-id="ab7c4-112">A value that is returned by the expression that has been configured in the **Collected data key name** property of an ER format component.</span></span> <span data-ttu-id="ab7c4-113">Esse argumento é obrigatório.</span><span class="sxs-lookup"><span data-stu-id="ab7c4-113">This argument is mandatory.</span></span>

<span data-ttu-id="ab7c4-114">A propriedade **Nome da chave de dados coletada** pode ser configurada para um componente **Sequência** ou um componente **Elemento XML** de um formato de ER que está no componente **Arquivo \\ comum** onde a opção **Coletar detalhes de saída** está ativada.</span><span class="sxs-lookup"><span data-stu-id="ab7c4-114">The **Collected data key name** property can be configured for either a **Sequence** component or an **XML Element** component of an ER format that resides under the **Common\\File** component where the **Collect output details** option is turned on.</span></span>

<span data-ttu-id="ab7c4-115">`condition 1 value`: *Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="ab7c4-115">`condition 1 value`: *String*</span></span>

<span data-ttu-id="ab7c4-116">Um valor retornado pela expressão que foi configurada na propriedade **Valor da chave de dados coletada** de um componente de formato de ER.</span><span class="sxs-lookup"><span data-stu-id="ab7c4-116">A value that is returned by the expression that has been configured in the **Collected data key value** property of an ER format component.</span></span> <span data-ttu-id="ab7c4-117">Esse argumento é obrigatório.</span><span class="sxs-lookup"><span data-stu-id="ab7c4-117">This argument is mandatory.</span></span>

<span data-ttu-id="ab7c4-118">A propriedade **Valor da chave de dados coletada** pode ser configurada para um componente **Sequência** ou um componente **Elemento XML** de um formato de ER que está no componente **Arquivo \\ comum** onde a opção **Coletar detalhes de saída** está ativada.</span><span class="sxs-lookup"><span data-stu-id="ab7c4-118">The **Collected data key value** property can be configured for either a **Sequence** component or an **XML Element** component of an ER format that resides under the **Common\\File** component where the **Collect output details** option is turned on.</span></span>

<span data-ttu-id="ab7c4-119">`condition N range`: *Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="ab7c4-119">`condition N range`: *String*</span></span>

<span data-ttu-id="ab7c4-120">Um valor retornado pela expressão que foi configurada na propriedade **Nome da chave de dados coletada** de um componente de formato de ER.</span><span class="sxs-lookup"><span data-stu-id="ab7c4-120">A value that is returned by the expression that has been configured in the **Collected data key name** property of an ER format component.</span></span> <span data-ttu-id="ab7c4-121">Esses argumentos adicionais são opcionais.</span><span class="sxs-lookup"><span data-stu-id="ab7c4-121">These additional arguments are optional.</span></span>

<span data-ttu-id="ab7c4-122">A propriedade **Nome da chave de dados coletada** pode ser configurada para um componente **Sequência** ou um componente **Elemento XML** de um formato de ER que está no componente **Arquivo \\ comum** onde a opção **Coletar detalhes de saída** está ativada.</span><span class="sxs-lookup"><span data-stu-id="ab7c4-122">The **Collected data key name** property can be configured for either a **Sequence** component or an **XML Element** component of an ER format that resides under the **Common\\File** component where the **Collect output details** option is turned on.</span></span>

<span data-ttu-id="ab7c4-123">`condition N value`: *Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="ab7c4-123">`condition N value`: *String*</span></span>

<span data-ttu-id="ab7c4-124">Um valor retornado pela expressão que foi configurada na propriedade **Valor da chave de dados coletada** de um componente de formato de ER.</span><span class="sxs-lookup"><span data-stu-id="ab7c4-124">A value that is returned by the expression that has been configured in the **Collected data key value** property of an ER format component.</span></span> <span data-ttu-id="ab7c4-125">Esses argumentos adicionais são opcionais.</span><span class="sxs-lookup"><span data-stu-id="ab7c4-125">These additional arguments are optional.</span></span>

<span data-ttu-id="ab7c4-126">A propriedade **Valor da chave de dados coletada** pode ser configurada para um componente **Sequência** ou um componente **Elemento XML** de um formato de ER que está no componente **Arquivo \\ comum** onde a opção **Coletar detalhes de saída** está ativada.</span><span class="sxs-lookup"><span data-stu-id="ab7c4-126">The **Collected data key value** property can be configured for either a **Sequence** component or an **XML Element** component of an ER format that resides under the **Common\\File** component where the **Collect output details** option is turned on.</span></span>

## <a name="return-values"></a><span data-ttu-id="ab7c4-127">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="ab7c4-127">Return values</span></span>

<span data-ttu-id="ab7c4-128">*Real*</span><span class="sxs-lookup"><span data-stu-id="ab7c4-128">*Real*</span></span>

<span data-ttu-id="ab7c4-129">O valor numérico resultante.</span><span class="sxs-lookup"><span data-stu-id="ab7c4-129">The resulting numeric value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="ab7c4-130">Notas de uso</span><span class="sxs-lookup"><span data-stu-id="ab7c4-130">Usage notes</span></span>

<span data-ttu-id="ab7c4-131">Esta função retorna um valor de **0** (zero) quando a opção **Coletar detalhes de saída** do componente **Arquivo \\ comum** está desativada.</span><span class="sxs-lookup"><span data-stu-id="ab7c4-131">This function returns a **0** (zero) value when the **Collect output details** option of the current **Common\\File** component is turned off.</span></span>

<span data-ttu-id="ab7c4-132">Nos argumentos `condition range`, o caractere curinga **"\*"** pode ser usado para representar quaisquer caracteres múltiplos.</span><span class="sxs-lookup"><span data-stu-id="ab7c4-132">In the `condition range` arguments, the wildcard character **"\*"** can be used to represent any multiple characters.</span></span>

<span data-ttu-id="ab7c4-133">Nos argumentos `condition value`, o caractere curinga **"\*"** pode ser usado para representar quaisquer caracteres múltiplos.</span><span class="sxs-lookup"><span data-stu-id="ab7c4-133">In the `condition value` arguments, the wildcard character **"\*"** can be used to represent any multiple characters.</span></span>

## <a name="example"></a><span data-ttu-id="ab7c4-134">Exemplo</span><span class="sxs-lookup"><span data-stu-id="ab7c4-134">Example</span></span>

<span data-ttu-id="ab7c4-135">Para obter informações sobre como usar esta função, consulte o guia de tarefas [ER Usar dados de saída do formato contagem e soma](tasks/er-format-counting-summing-1.md), que faz parte do processo de negócios **Adquirir/Desenvolver componentes de solução/serviço de TI**.</span><span class="sxs-lookup"><span data-stu-id="ab7c4-135">For more information about how to use this function, see the [ER Use data of format output for counting and summing](tasks/er-format-counting-summing-1.md) task guide, which is part of the **Acquire/Develop IT service/solution components** business process.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="ab7c4-136">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="ab7c4-136">Additional resources</span></span>

[<span data-ttu-id="ab7c4-137">Funções de coleta de dados</span><span class="sxs-lookup"><span data-stu-id="ab7c4-137">Data collection functions</span></span>](er-functions-category-data-collection.md)
