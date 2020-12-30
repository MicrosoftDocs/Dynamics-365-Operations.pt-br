---
title: Função COUNTIFS ER
description: Este tópico fornece informações sobre como a função de relatório eletrônico COUNTIFS é usada.
author: NickSelin
manager: kfend
ms.date: 12/05/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 554750b2dae5ec1f0fcf6fdbdf439b4dbe4fa615
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2020
ms.locfileid: "4681125"
---
# <a name="countifs-er-function"></a><span data-ttu-id="dcd71-103">Função COUNTIFS ER</span><span class="sxs-lookup"><span data-stu-id="dcd71-103">COUNTIFS ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="dcd71-104">A função `COUNTIFS` retorna um valor *Inteiro* que representa o número de elementos de formato que foram coletados quando os elementos de formato foram usados para gerar um documento de saída durante a execução do formato, e que satisfaçam as condições especificadas.</span><span class="sxs-lookup"><span data-stu-id="dcd71-104">The `COUNTIFS` function returns an *Integer* value that represents the number of format elements that was collected when the format elements were used to generate an outbound document during the format run, and that satisfies the specified conditions.</span></span> <span data-ttu-id="dcd71-105">Cada condição consiste em um intervalo de chaves e um valor de chave.</span><span class="sxs-lookup"><span data-stu-id="dcd71-105">Each condition consists of a key range and a key value.</span></span>

## <a name="syntax"></a><span data-ttu-id="dcd71-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="dcd71-106">Syntax</span></span>

```vb
COUNTIFS (condition 1 range, condition 1 value[, condition 2 range, condition 2 value, …, condition N range, condition N value])
```

## <a name="arguments"></a><span data-ttu-id="dcd71-107">Argumentos</span><span class="sxs-lookup"><span data-stu-id="dcd71-107">Arguments</span></span>

<span data-ttu-id="dcd71-108">`condition 1 range`: *Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="dcd71-108">`condition 1 range`: *String*</span></span>

<span data-ttu-id="dcd71-109">Um valor retornado pela expressão que foi configurada na propriedade **Nome da chave de dados coletada** de um componente de formato de relatório eletrônico (ER).</span><span class="sxs-lookup"><span data-stu-id="dcd71-109">A value that is returned by the expression that has been configured in the **Collected data key name** property of an Electronic reporting (ER) format component.</span></span> <span data-ttu-id="dcd71-110">Esse argumento é obrigatório.</span><span class="sxs-lookup"><span data-stu-id="dcd71-110">This argument is mandatory.</span></span>

<span data-ttu-id="dcd71-111">`condition 1 value`: *Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="dcd71-111">`condition 1 value`: *String*</span></span>

<span data-ttu-id="dcd71-112">Um valor retornado pela expressão que foi configurada na propriedade **Valor da chave de dados coletada** de um componente de formato de ER.</span><span class="sxs-lookup"><span data-stu-id="dcd71-112">A value that is returned by the expression that has been configured in the **Collected data key value** property of an ER format component.</span></span> <span data-ttu-id="dcd71-113">Esse argumento é obrigatório.</span><span class="sxs-lookup"><span data-stu-id="dcd71-113">This argument is mandatory.</span></span>

<span data-ttu-id="dcd71-114">`condition N range`: *Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="dcd71-114">`condition N range`: *String*</span></span>

<span data-ttu-id="dcd71-115">Um valor retornado pela expressão que foi configurada na propriedade **Nome da chave de dados coletada** de um componente de formato de ER.</span><span class="sxs-lookup"><span data-stu-id="dcd71-115">A value that is returned by the expression that has been configured in the **Collected data key name** property of an ER format component.</span></span> <span data-ttu-id="dcd71-116">Esses argumentos adicionais são opcionais.</span><span class="sxs-lookup"><span data-stu-id="dcd71-116">These additional arguments are optional.</span></span>

<span data-ttu-id="dcd71-117">`condition N value`: *Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="dcd71-117">`condition N value`: *String*</span></span>

<span data-ttu-id="dcd71-118">Um valor retornado pela expressão que foi configurada na propriedade **Valor da chave de dados coletada** de um componente de formato de ER.</span><span class="sxs-lookup"><span data-stu-id="dcd71-118">A value that is returned by the expression that has been configured in the **Collected data key value** property of an ER format component.</span></span> <span data-ttu-id="dcd71-119">Esses argumentos adicionais são opcionais.</span><span class="sxs-lookup"><span data-stu-id="dcd71-119">These additional arguments are optional.</span></span>

## <a name="return-values"></a><span data-ttu-id="dcd71-120">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="dcd71-120">Return values</span></span>

<span data-ttu-id="dcd71-121">*Inteiro*</span><span class="sxs-lookup"><span data-stu-id="dcd71-121">*Integer*</span></span>

<span data-ttu-id="dcd71-122">O valor numérico resultante.</span><span class="sxs-lookup"><span data-stu-id="dcd71-122">The resulting numeric value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="dcd71-123">Notas de uso</span><span class="sxs-lookup"><span data-stu-id="dcd71-123">Usage notes</span></span>

<span data-ttu-id="dcd71-124">As propriedade **Nome da chave de dados coletada** e **Valor da chave de dados coletada** podem ser configuradas para um componente **Sequência** ou um componente **Elemento XML** de um formato de ER que está no componente **Arquivo \\ comum** onde a opção **Coletar detalhes de saída** está ativada.</span><span class="sxs-lookup"><span data-stu-id="dcd71-124">The **Collected data key name** and **Collected data key value** properties can be configured for either the **Sequence** component or the **XML Element** component of an ER format that resides under the **Common\\File** component where the **Collect output details** option is turned on.</span></span>

<span data-ttu-id="dcd71-125">Esta função retorna um valor de **0** (zero) quando a opção **Coletar detalhes de saída** do componente **Arquivo \\ comum** está desativada.</span><span class="sxs-lookup"><span data-stu-id="dcd71-125">This function returns a **0** (zero) value when the **Collect output details** option of the current **Common\\File** component is turned off.</span></span>

<span data-ttu-id="dcd71-126">Nos argumentos `condition range`, o caractere curinga **"\*"** pode ser usado para representar quaisquer caracteres múltiplos.</span><span class="sxs-lookup"><span data-stu-id="dcd71-126">In `condition range` arguments, the wildcard character **"\*"** can be used to represent any multiple characters.</span></span>

<span data-ttu-id="dcd71-127">Nos argumentos `condition value`, o caractere curinga **"\*"** pode ser usado para representar quaisquer caracteres múltiplos.</span><span class="sxs-lookup"><span data-stu-id="dcd71-127">In `condition value` arguments, the wildcard character **"\*"** can be used to represent any multiple characters.</span></span>

## <a name="example"></a><span data-ttu-id="dcd71-128">Exemplo</span><span class="sxs-lookup"><span data-stu-id="dcd71-128">Example</span></span>

<span data-ttu-id="dcd71-129">Para obter informações sobre como usar esta função, consulte o guia de tarefas [ER Usar dados de saída do formato contagem e soma](tasks/er-format-counting-summing-1.md), que faz parte do processo de negócios **Adquirir/Desenvolver componentes de solução/serviço de TI**.</span><span class="sxs-lookup"><span data-stu-id="dcd71-129">For more information about how to use this function, see the [ER Use data of format output for counting and summing](tasks/er-format-counting-summing-1.md) task guide, which is part of the **Acquire/Develop IT service/solution components** business process.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="dcd71-130">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="dcd71-130">Additional resources</span></span>

[<span data-ttu-id="dcd71-131">Funções de coleta de dados</span><span class="sxs-lookup"><span data-stu-id="dcd71-131">Data collection functions</span></span>](er-functions-category-data-collection.md)
