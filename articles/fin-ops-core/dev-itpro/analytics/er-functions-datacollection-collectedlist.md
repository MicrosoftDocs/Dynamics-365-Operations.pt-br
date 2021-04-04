---
title: Função COLLECTEDLIST ER
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) COLLECTEDLIST é usada.
author: NickSelin
manager: kfend
ms.date: 12/05/2019
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: ff48170247130a03b10dc8fe2973f8d774046944
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/09/2021
ms.locfileid: "5561389"
---
# <a name="collectedlist-er-function"></a><span data-ttu-id="8ca58-103">Função COLLECTEDLIST ER</span><span class="sxs-lookup"><span data-stu-id="8ca58-103">COLLECTEDLIST ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="8ca58-104">A função `COLLECTEDLIST` retorna um valor de *Lista de registros* que contém a lista de valores que foram retornados pela propriedade **Valor da chave de dados coletada** de formato e coletados quando os elementos de formato foram usados para gerar documentos de saída durante a execução do formato, e que satisfaçam as condições especificadas.</span><span class="sxs-lookup"><span data-stu-id="8ca58-104">The `COLLECTEDLIST` function a *Record list* value that contains the list of values that were returned by the **Collected data key value** property of format elements and collected when the format elements were used to generate outbound documents during the format run, and that satisfies the specified conditions.</span></span> <span data-ttu-id="8ca58-105">Cada condição consiste em um intervalo de chaves e um valor de chave.</span><span class="sxs-lookup"><span data-stu-id="8ca58-105">Each condition consists of a key range and a key value.</span></span>

## <a name="syntax"></a><span data-ttu-id="8ca58-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="8ca58-106">Syntax</span></span>

```vb
COLLECTEDLIST (condition 1 range, condition 1 value[, condition 2 range, condition 2 value, …, condition N range, condition N value])
```

## <a name="arguments"></a><span data-ttu-id="8ca58-107">Argumentos</span><span class="sxs-lookup"><span data-stu-id="8ca58-107">Arguments</span></span>

<span data-ttu-id="8ca58-108">`condition 1 range`: *Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="8ca58-108">`condition 1 range`: *String*</span></span>

<span data-ttu-id="8ca58-109">Um valor retornado pela expressão que foi configurada na propriedade **Nome da chave de dados coletada** de um componente de formato de relatório eletrônico (ER).</span><span class="sxs-lookup"><span data-stu-id="8ca58-109">A value that is returned by the expression that has been configured in the **Collected data key name** property of an Electronic reporting (ER) format component.</span></span> <span data-ttu-id="8ca58-110">Esse argumento é obrigatório.</span><span class="sxs-lookup"><span data-stu-id="8ca58-110">This argument is mandatory.</span></span>

<span data-ttu-id="8ca58-111">`condition 1 value`: *Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="8ca58-111">`condition 1 value`: *String*</span></span>

<span data-ttu-id="8ca58-112">Um valor retornado pela expressão que foi configurada na propriedade **Valor da chave de dados coletada** de um componente de formato de ER.</span><span class="sxs-lookup"><span data-stu-id="8ca58-112">A value that is returned by the expression that has been configured in the **Collected data key value** property of an ER format component.</span></span> <span data-ttu-id="8ca58-113">Esse argumento é obrigatório.</span><span class="sxs-lookup"><span data-stu-id="8ca58-113">This argument is mandatory.</span></span>

<span data-ttu-id="8ca58-114">`condition N range`: *Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="8ca58-114">`condition N range`: *String*</span></span>

<span data-ttu-id="8ca58-115">Um valor retornado pela expressão que foi configurada na propriedade **Nome da chave de dados coletada** de um componente de formato de ER.</span><span class="sxs-lookup"><span data-stu-id="8ca58-115">A value that is returned by the expression that has been configured in the **Collected data key name** property of an ER format component.</span></span> <span data-ttu-id="8ca58-116">Esses argumentos adicionais são opcionais.</span><span class="sxs-lookup"><span data-stu-id="8ca58-116">These additional arguments are optional.</span></span>

<span data-ttu-id="8ca58-117">`condition N value`: *Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="8ca58-117">`condition N value`: *String*</span></span>

<span data-ttu-id="8ca58-118">Um valor retornado pela expressão que foi configurada na propriedade **Valor da chave de dados coletada** de um componente de formato de ER.</span><span class="sxs-lookup"><span data-stu-id="8ca58-118">A value that is returned by the expression that has been configured in the **Collected data key value** property of an ER format component.</span></span> <span data-ttu-id="8ca58-119">Esses argumentos adicionais são opcionais.</span><span class="sxs-lookup"><span data-stu-id="8ca58-119">These additional arguments are optional.</span></span>

## <a name="return-values"></a><span data-ttu-id="8ca58-120">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="8ca58-120">Return values</span></span>

<span data-ttu-id="8ca58-121">*Lista de registros*</span><span class="sxs-lookup"><span data-stu-id="8ca58-121">*Record list*</span></span>

<span data-ttu-id="8ca58-122">A lista de registros resultante.</span><span class="sxs-lookup"><span data-stu-id="8ca58-122">The resulting list of records.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="8ca58-123">Notas de uso</span><span class="sxs-lookup"><span data-stu-id="8ca58-123">Usage notes</span></span>

<span data-ttu-id="8ca58-124">As propriedade **Nome da chave de dados coletada** e **Valor da chave de dados coletada** podem ser configuradas para um componente **Sequência** ou um componente **Elemento XML** de um formato de ER que está no componente **Arquivo \\ comum** onde a opção **Coletar detalhes de saída** está ativada.</span><span class="sxs-lookup"><span data-stu-id="8ca58-124">The **Collected data key name** and **Collected data key value** properties can be configured for either the **Sequence** component or the **XML Element** component of an ER format that resides under the **Common\\File** component where the **Collect output details** option is turned on.</span></span>

<span data-ttu-id="8ca58-125">Esta função retorna uma lista vazia quando a opção **Coletar detalhes de saída** do componente **Arquivo \\ comum** está desativada.</span><span class="sxs-lookup"><span data-stu-id="8ca58-125">This function returns an empty list when the **Collect output details** option of the current **Common\\File** component is turned off.</span></span>

<span data-ttu-id="8ca58-126">Nos argumentos `condition range`, o caractere curinga **"\*"** pode ser usado para representar quaisquer caracteres múltiplos.</span><span class="sxs-lookup"><span data-stu-id="8ca58-126">In `condition range` arguments, the wildcard character **"\*"** can be used to represent any multiple characters.</span></span>

<span data-ttu-id="8ca58-127">Nos argumentos `condition value`, o caractere curinga **"\*"** pode ser usado para representar quaisquer caracteres múltiplos.</span><span class="sxs-lookup"><span data-stu-id="8ca58-127">In `condition value` arguments, the wildcard character **"\*"** can be used to represent any multiple characters.</span></span>

## <a name="example"></a><span data-ttu-id="8ca58-128">Exemplo</span><span class="sxs-lookup"><span data-stu-id="8ca58-128">Example</span></span>

<span data-ttu-id="8ca58-129">Para obter informações sobre como usar esta função, consulte o guia de tarefas [ER Usar dados de saída do formato contagem e soma](tasks/er-format-counting-summing-1.md), que faz parte do processo de negócios **Adquirir/Desenvolver componentes de solução/serviço de TI**.</span><span class="sxs-lookup"><span data-stu-id="8ca58-129">For more information about how to use this function, see the [ER Use data of format output for counting and summing](tasks/er-format-counting-summing-1.md) task guide, which is part of the **Acquire/Develop IT service/solution components** business process.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="8ca58-130">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="8ca58-130">Additional resources</span></span>

[<span data-ttu-id="8ca58-131">Funções de coleta de dados</span><span class="sxs-lookup"><span data-stu-id="8ca58-131">Data collection functions</span></span>](er-functions-category-data-collection.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]