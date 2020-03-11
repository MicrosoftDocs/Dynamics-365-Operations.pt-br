---
title: Função SUMIF ER
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) SUMIF é usada.
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
ms.openlocfilehash: 374569d3bbe59f1b96eee9c789b97b7b2a6004bf
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/12/2020
ms.locfileid: "3042472"
---
# <span data-ttu-id="6cf5d-103"><a name="SUMIF">Função SUMIF ER</a></span><span class="sxs-lookup"><span data-stu-id="6cf5d-103"><a name="SUMIF">SUMIF ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="6cf5d-104">A função `SUMIF` retorna um valor *Real* que representa a soma de valores que foram retornados por associações de elementos de formato e coletados quando os elementos de formato foram usados para gerar um documento de saída durante a execução do formato, e que satisfaçam a condição especificada.</span><span class="sxs-lookup"><span data-stu-id="6cf5d-104">The `SUMIF` function returns a *Real* value that represents the sum of values that were returned by bindings of format elements and collected when the format elements were used to generate an outbound document during the format run, and that satisfies the specified condition.</span></span> <span data-ttu-id="6cf5d-105">A condição consiste em um intervalo de chaves e um valor de chave.</span><span class="sxs-lookup"><span data-stu-id="6cf5d-105">The condition consists of a key range and a key value.</span></span>

## <a name="syntax"></a><span data-ttu-id="6cf5d-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="6cf5d-106">Syntax</span></span>

```vb
SUMIF (key name for summing, condition range, condition value)
```

## <a name="arguments"></a><span data-ttu-id="6cf5d-107">Argumentos</span><span class="sxs-lookup"><span data-stu-id="6cf5d-107">Arguments</span></span>

<span data-ttu-id="6cf5d-108">`key name for summing`: *Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="6cf5d-108">`key name for summing`: *String*</span></span>

<span data-ttu-id="6cf5d-109">Um valor retornado pela expressão que foi configurada na propriedade **Nome da chave de dados coletados** do componente de formato de relatório eletrônico (ER) para o qual o valor da associação deve ser usado para fins de soma.</span><span class="sxs-lookup"><span data-stu-id="6cf5d-109">A value that is returned by the expression that has been configured in the **Collected data key name** property of the Electronic reporting (ER) format component for which the value of the binding must be used for summing purposes.</span></span>

<span data-ttu-id="6cf5d-110">A propriedade **Valor da chave de dados coletada** pode ser configurada para um componente **Sequência** ou um componente **Elemento XML** de um formato de ER que está no componente **Arquivo \\ comum** onde a opção **Coletar detalhes de saída** está ativada.</span><span class="sxs-lookup"><span data-stu-id="6cf5d-110">The **Collected data key value** property can be configured for either a **Sequence** component or an **XML Element** component of an ER format that resides under the **Common\\File** component where the **Collect output details** option is turned on.</span></span>

## <a name="return-values"></a><span data-ttu-id="6cf5d-111">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="6cf5d-111">Return values</span></span>

<span data-ttu-id="6cf5d-112">*Real*</span><span class="sxs-lookup"><span data-stu-id="6cf5d-112">*Real*</span></span>

<span data-ttu-id="6cf5d-113">O valor numérico resultante.</span><span class="sxs-lookup"><span data-stu-id="6cf5d-113">The resulting numeric value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="6cf5d-114">Notas de uso</span><span class="sxs-lookup"><span data-stu-id="6cf5d-114">Usage notes</span></span>

<span data-ttu-id="6cf5d-115">Esta função retorna um valor de **0** (zero) quando a opção **Coletar detalhes de saída** do componente **Arquivo \\ comum** está desativada.</span><span class="sxs-lookup"><span data-stu-id="6cf5d-115">This function returns a **0** (zero) value when the **Collect output details** option of the current **Common\\File** component is turned off.</span></span>

<span data-ttu-id="6cf5d-116">No argumento `condition range`, o caractere curinga **"\*"** pode ser usado para representar quaisquer caracteres múltiplos.</span><span class="sxs-lookup"><span data-stu-id="6cf5d-116">In the `condition range` argument, the wildcard character **"\*"** can be used to represent any multiple characters.</span></span>

<span data-ttu-id="6cf5d-117">No argumento `condition value`, o caractere curinga **"\*"** pode ser usado para representar quaisquer caracteres múltiplos.</span><span class="sxs-lookup"><span data-stu-id="6cf5d-117">In the `condition value` argument, the wildcard character **"\*"** can be used to represent any multiple characters.</span></span>

## <a name="example"></a><span data-ttu-id="6cf5d-118">Exemplo</span><span class="sxs-lookup"><span data-stu-id="6cf5d-118">Example</span></span>

<span data-ttu-id="6cf5d-119">Para obter informações sobre como usar esta função, consulte o guia de tarefas [ER Usar dados de saída do formato contagem e soma](tasks/er-format-counting-summing-1.md), que faz parte do processo de negócios **Adquirir/Desenvolver componentes de solução/serviço de TI**.</span><span class="sxs-lookup"><span data-stu-id="6cf5d-119">For more information about how to use this function, see the [ER Use data of format output for counting and summing](tasks/er-format-counting-summing-1.md) task guide, which is part of the **Acquire/Develop IT service/solution components** business process.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="6cf5d-120">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="6cf5d-120">Additional resources</span></span>

[<span data-ttu-id="6cf5d-121">Funções de coleta de dados</span><span class="sxs-lookup"><span data-stu-id="6cf5d-121">Data collection functions</span></span>](er-functions-category-data-collection.md)
