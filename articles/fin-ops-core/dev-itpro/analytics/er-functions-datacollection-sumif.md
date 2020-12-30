---
title: Função SUMIF ER
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) SUMIF é usada.
author: NickSelin
manager: kfend
ms.date: 04/27/2020
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
ms.openlocfilehash: 52f9cdb78efa6fe0dbebd2ffd78cd6e9185d6b2e
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2020
ms.locfileid: "4685342"
---
# <a name="sumif-er-function"></a><span data-ttu-id="ac4b5-103">Função SUMIF ER</span><span class="sxs-lookup"><span data-stu-id="ac4b5-103">SUMIF ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="ac4b5-104">A função `SUMIF` retorna um valor *Real* que representa a soma de valores que foram retornados por associações de elementos de formato e coletados quando os elementos de formato foram usados para gerar um documento de saída durante a execução do formato, e que satisfaçam a condição especificada.</span><span class="sxs-lookup"><span data-stu-id="ac4b5-104">The `SUMIF` function returns a *Real* value that represents the sum of values that were returned by bindings of format elements and collected when the format elements were used to generate an outbound document during the format run, and that satisfies the specified condition.</span></span> <span data-ttu-id="ac4b5-105">A condição consiste em um intervalo de chaves e um valor de chave.</span><span class="sxs-lookup"><span data-stu-id="ac4b5-105">The condition consists of a key range and a key value.</span></span>

## <a name="syntax"></a><span data-ttu-id="ac4b5-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="ac4b5-106">Syntax</span></span>

```vb
SUMIF (key name for summing, condition range, condition value)
```

## <a name="arguments"></a><span data-ttu-id="ac4b5-107">Argumentos</span><span class="sxs-lookup"><span data-stu-id="ac4b5-107">Arguments</span></span>

<span data-ttu-id="ac4b5-108">`key name for summing`: *Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="ac4b5-108">`key name for summing`: *String*</span></span>

<span data-ttu-id="ac4b5-109">Um valor retornado pela expressão que foi configurada na propriedade **Nome da chave de dados coletados** do componente de formato de relatório eletrônico (ER) para o qual o valor da associação deve ser usado para fins de soma.</span><span class="sxs-lookup"><span data-stu-id="ac4b5-109">A value that is returned by the expression that has been configured in the **Collected data key name** property of the Electronic reporting (ER) format component for which the value of the binding must be used for summing purposes.</span></span>

<span data-ttu-id="ac4b5-110">A propriedade **Valor da chave de dados coletada** pode ser configurada para um componente **Sequência** ou um componente **Elemento XML** de um formato de ER que está no componente **Arquivo \\ comum** onde a opção **Coletar detalhes de saída** está ativada.</span><span class="sxs-lookup"><span data-stu-id="ac4b5-110">The **Collected data key value** property can be configured for either a **Sequence** component or an **XML Element** component of an ER format that resides under the **Common\\File** component where the **Collect output details** option is turned on.</span></span>

## <a name="return-values"></a><span data-ttu-id="ac4b5-111">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="ac4b5-111">Return values</span></span>

<span data-ttu-id="ac4b5-112">*Real*</span><span class="sxs-lookup"><span data-stu-id="ac4b5-112">*Real*</span></span>

<span data-ttu-id="ac4b5-113">O valor numérico resultante.</span><span class="sxs-lookup"><span data-stu-id="ac4b5-113">The resulting numeric value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="ac4b5-114">Notas de uso</span><span class="sxs-lookup"><span data-stu-id="ac4b5-114">Usage notes</span></span>

<span data-ttu-id="ac4b5-115">Esta função retorna um valor de **0** (zero) quando a opção **Coletar detalhes de saída** do componente **Arquivo \\ comum** está desativada.</span><span class="sxs-lookup"><span data-stu-id="ac4b5-115">This function returns a **0** (zero) value when the **Collect output details** option of the current **Common\\File** component is turned off.</span></span>

<span data-ttu-id="ac4b5-116">No argumento `condition range`, o caractere curinga **"\*"** pode ser usado para representar quaisquer caracteres múltiplos.</span><span class="sxs-lookup"><span data-stu-id="ac4b5-116">In the `condition range` argument, the wildcard character **"\*"** can be used to represent any multiple characters.</span></span>

<span data-ttu-id="ac4b5-117">No argumento `condition value`, o caractere curinga **"\*"** pode ser usado para representar quaisquer caracteres múltiplos.</span><span class="sxs-lookup"><span data-stu-id="ac4b5-117">In the `condition value` argument, the wildcard character **"\*"** can be used to represent any multiple characters.</span></span>

## <a name="example"></a><span data-ttu-id="ac4b5-118">Exemplo</span><span class="sxs-lookup"><span data-stu-id="ac4b5-118">Example</span></span>

<span data-ttu-id="ac4b5-119">Para obter informações sobre como usar esta função, consulte o guia de tarefas [ER Usar dados de saída do formato contagem e soma](tasks/er-format-counting-summing-1.md), que faz parte do processo de negócios **Adquirir/Desenvolver componentes de solução/serviço de TI**.</span><span class="sxs-lookup"><span data-stu-id="ac4b5-119">For more information about how to use this function, see the [ER Use data of format output for counting and summing](tasks/er-format-counting-summing-1.md) task guide, which is part of the **Acquire/Develop IT service/solution components** business process.</span></span>

<span data-ttu-id="ac4b5-120">Para obter mais informações e exemplos sobre como usar essa função, consulte [Adiar a execução de elementos de sequência nos formatos ER](er-defer-sequence-element.md#Example) e [Adiar a execução de elementos XML nos formatos ER](er-defer-xml-element.md#Example).</span><span class="sxs-lookup"><span data-stu-id="ac4b5-120">For more information and examples about using this function, see [Defer the execution of sequence elements in ER formats](er-defer-sequence-element.md#Example) and [Defer the execution of XML elements in ER formats](er-defer-xml-element.md#Example).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="ac4b5-121">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="ac4b5-121">Additional resources</span></span>

[<span data-ttu-id="ac4b5-122">Funções de coleta de dados</span><span class="sxs-lookup"><span data-stu-id="ac4b5-122">Data collection functions</span></span>](er-functions-category-data-collection.md)
