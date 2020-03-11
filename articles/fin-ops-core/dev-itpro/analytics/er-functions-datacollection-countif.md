---
title: Função COUNTIF ER
description: Este tópico fornece informações sobre como a função de relatório eletrônico COUNTIF é usada.
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
ms.search.scope: Core, Operations
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 188f79e10610f8cb5281cfee351ab0eef48dccd2
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/12/2020
ms.locfileid: "3042564"
---
# <span data-ttu-id="836f8-103"><a name="COUNTIF">Função COUNTIF ER</a></span><span class="sxs-lookup"><span data-stu-id="836f8-103"><a name="COUNTIF">COUNTIF ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="836f8-104">A função `COUNTIF` retorna um valor *Inteiro* que representa o número de elementos de formato que foram coletados quando os elementos de formato foram usados para gerar um documento de saída durante a execução do formato, e que satisfaçam a condição especificada.</span><span class="sxs-lookup"><span data-stu-id="836f8-104">The `COUNTIF` function returns an *Integer* value that represents the number of format elements that was collected when the format elements were used to generate an outbound document during the format run, and that satisfies the specified condition.</span></span> <span data-ttu-id="836f8-105">A condição consiste em um intervalo de chaves e um valor de chave.</span><span class="sxs-lookup"><span data-stu-id="836f8-105">The condition consists of a key range and a key value.</span></span>

## <a name="syntax"></a><span data-ttu-id="836f8-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="836f8-106">Syntax</span></span>

```vb
COUNTIF (condition range, condition value)
```

## <a name="arguments"></a><span data-ttu-id="836f8-107">Argumentos</span><span class="sxs-lookup"><span data-stu-id="836f8-107">Arguments</span></span>

<span data-ttu-id="836f8-108">`condition range`: *Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="836f8-108">`condition range`: *String*</span></span>

<span data-ttu-id="836f8-109">Um valor retornado pela expressão que foi configurada na propriedade **Nome da chave de dados coletada** de um componente de formato de relatório eletrônico (ER).</span><span class="sxs-lookup"><span data-stu-id="836f8-109">A value that is returned by the expression that has been configured in the **Collected data key name** property of an Electronic reporting (ER) format component.</span></span>

<span data-ttu-id="836f8-110">`condition value`: *Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="836f8-110">`condition value`: *String*</span></span>

<span data-ttu-id="836f8-111">Um valor retornado pela expressão que foi configurada na propriedade **Valor da chave de dados coletada** de um componente de formato de ER.</span><span class="sxs-lookup"><span data-stu-id="836f8-111">A value that is returned by the expression that has been configured in the **Collected data key value** property of an ER format component.</span></span>

## <a name="return-values"></a><span data-ttu-id="836f8-112">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="836f8-112">Return values</span></span>

<span data-ttu-id="836f8-113">*Inteiro*</span><span class="sxs-lookup"><span data-stu-id="836f8-113">*Integer*</span></span>

<span data-ttu-id="836f8-114">O valor numérico resultante.</span><span class="sxs-lookup"><span data-stu-id="836f8-114">The resulting numeric value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="836f8-115">Notas de uso</span><span class="sxs-lookup"><span data-stu-id="836f8-115">Usage notes</span></span>

<span data-ttu-id="836f8-116">As propriedade **Nome da chave de dados coletada** e **Valor da chave de dados coletada** podem ser configuradas para um componente **Sequência** ou um componente **Elemento XML** de um formato de ER que está no componente **Arquivo \\ comum** onde a opção **Coletar detalhes de saída** está ativada.</span><span class="sxs-lookup"><span data-stu-id="836f8-116">The **Collected data key name** and **Collected data key value** properties can be configured for either the **Sequence** component or the **XML Element** component of an ER format that resides under the **Common\\File** component where the **Collect output details** option is turned on.</span></span>

<span data-ttu-id="836f8-117">Esta função retorna um valor de **0** (zero) quando a opção **Coletar detalhes de saída** do componente **Arquivo \\ comum** está desativada.</span><span class="sxs-lookup"><span data-stu-id="836f8-117">This function returns a **0** (zero) value when the **Collect output details** option of the current **Common\\File** component is turned off.</span></span>

<span data-ttu-id="836f8-118">No argumento `condition range`, o caractere curinga **"\*"** pode ser usado para representar quaisquer caracteres múltiplos.</span><span class="sxs-lookup"><span data-stu-id="836f8-118">In the `condition range` argument, the wildcard character **"\*"** can be used to represent any multiple characters.</span></span>

<span data-ttu-id="836f8-119">No argumento `condition value`, o caractere curinga **"\*"** pode ser usado para representar quaisquer caracteres múltiplos.</span><span class="sxs-lookup"><span data-stu-id="836f8-119">In the `condition value` argument, the wildcard character **"\*"** can be used to represent any multiple characters.</span></span>

## <a name="example"></a><span data-ttu-id="836f8-120">Exemplo</span><span class="sxs-lookup"><span data-stu-id="836f8-120">Example</span></span>

<span data-ttu-id="836f8-121">Para obter informações sobre como usar esta função, consulte o guia de tarefas [ER Usar dados de saída do formato contagem e soma](tasks/er-format-counting-summing-1.md), que faz parte do processo de negócios **Adquirir/Desenvolver componentes de solução/serviço de TI**.</span><span class="sxs-lookup"><span data-stu-id="836f8-121">For more information about how to use this function, see the [ER Use data of format output for counting and summing](tasks/er-format-counting-summing-1.md) task guide, which is part of the **Acquire/Develop IT service/solution components** business process.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="836f8-122">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="836f8-122">Additional resources</span></span>

[<span data-ttu-id="836f8-123">Funções de coleta de dados</span><span class="sxs-lookup"><span data-stu-id="836f8-123">Data collection functions</span></span>](er-functions-category-data-collection.md)
