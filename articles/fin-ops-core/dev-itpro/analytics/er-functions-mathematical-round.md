---
title: Função de ER ROUND
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) ROUND é usada.
author: NickSelin
manager: kfend
ms.date: 12/17/2019
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
ms.openlocfilehash: 12af71a024a76fca98fc2e876da9b59e5762cf07
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/01/2020
ms.locfileid: "3744542"
---
# <a name="round-er-function"></a><span data-ttu-id="d7c53-103">Função de ER ROUND</span><span class="sxs-lookup"><span data-stu-id="d7c53-103">ROUND ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="d7c53-104">A função `ROUND` retorna o número especificado como um valor *Real* após ele ser arredondado para o número especificado de casas decimais.</span><span class="sxs-lookup"><span data-stu-id="d7c53-104">The `ROUND` function returns the specified number as a *Real* value after it has been rounded to the specified number of decimal places.</span></span>

## <a name="syntax"></a><span data-ttu-id="d7c53-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="d7c53-105">Syntax</span></span>

```vb
ROUND (number, decimals)
```

## <a name="arguments"></a><span data-ttu-id="d7c53-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="d7c53-106">Arguments</span></span>

<span data-ttu-id="d7c53-107">`number`: *Real*</span><span class="sxs-lookup"><span data-stu-id="d7c53-107">`number`: *Real*</span></span>

<span data-ttu-id="d7c53-108">Um valor numérico que deve ser arredondado.</span><span class="sxs-lookup"><span data-stu-id="d7c53-108">A numeric value that must be rounded.</span></span>

<span data-ttu-id="d7c53-109">`decimals`: *Inteiro*</span><span class="sxs-lookup"><span data-stu-id="d7c53-109">`decimals`: *Integer*</span></span>

<span data-ttu-id="d7c53-110">Um valor numérico que representa o número de casas decimais.</span><span class="sxs-lookup"><span data-stu-id="d7c53-110">A numeric value that represents the number of decimal places.</span></span>

## <a name="return-values"></a><span data-ttu-id="d7c53-111">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="d7c53-111">Return values</span></span>

<span data-ttu-id="d7c53-112">*Real*</span><span class="sxs-lookup"><span data-stu-id="d7c53-112">*Real*</span></span>

<span data-ttu-id="d7c53-113">O valor numérico resultante.</span><span class="sxs-lookup"><span data-stu-id="d7c53-113">The resulting numeric value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="d7c53-114">Notas de uso</span><span class="sxs-lookup"><span data-stu-id="d7c53-114">Usage notes</span></span>

<span data-ttu-id="d7c53-115">Se o valor do argumento `decimals` for maior do que 0 (zero), o número especificado é arredondado para essa quantidade de casas decimais.</span><span class="sxs-lookup"><span data-stu-id="d7c53-115">If the value of the `decimals` argument is more than 0 (zero), the specified number is rounded to that many decimal places.</span></span>

<span data-ttu-id="d7c53-116">Se o valor do argumento `decimals` for **0** (zero), o número especificado é arredondado para o inteiro mais próximo.</span><span class="sxs-lookup"><span data-stu-id="d7c53-116">If the value of the `decimals` argument is **0** (zero), the specified number is rounded to the nearest integer.</span></span>

<span data-ttu-id="d7c53-117">Se o valor do argumento `decimals` for menor do que 0 (zero), o número especificado é arredondado para a esquerda do separador decimal.</span><span class="sxs-lookup"><span data-stu-id="d7c53-117">If the value of the `decimals` argument is less than 0 (zero), the specified number is rounded to the left of the decimal point.</span></span>

## <a name="example-1"></a><span data-ttu-id="d7c53-118">Exemplo 1</span><span class="sxs-lookup"><span data-stu-id="d7c53-118">Example 1</span></span>

<span data-ttu-id="d7c53-119">`ROUND (1200.767, 2)` arredonda para duas casas decimais e retorna **1200,77**.</span><span class="sxs-lookup"><span data-stu-id="d7c53-119">`ROUND (1200.767, 2)` rounds to two decimal places and returns **1200.77**.</span></span>

## <a name="example-2"></a><span data-ttu-id="d7c53-120">Exemplo 2</span><span class="sxs-lookup"><span data-stu-id="d7c53-120">Example 2</span></span>

<span data-ttu-id="d7c53-121">`ROUND (1200.767, -3)` arredonda para o múltiplo mais próximo de 1.000 e retorna **1000**.</span><span class="sxs-lookup"><span data-stu-id="d7c53-121">`ROUND (1200.767, -3)` rounds to the nearest multiple of 1,000 and returns **1000**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="d7c53-122">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="d7c53-122">Additional resources</span></span>

[<span data-ttu-id="d7c53-123">Funções matemáticas</span><span class="sxs-lookup"><span data-stu-id="d7c53-123">Mathematical functions</span></span>](er-functions-category-mathematical.md)
