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
ms.openlocfilehash: c9384d5975e4a25d18ff741f87431daa4b0bbd7e
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/20/2019
ms.locfileid: "2917065"
---
# <span data-ttu-id="1a8a6-103"><a name="ROUND">Função de ER ROUND</a></span><span class="sxs-lookup"><span data-stu-id="1a8a6-103"><a name="ROUND">ROUND ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="1a8a6-104">A função `ROUND` retorna o número especificado como um valor *Real* após ele ser arredondado para o número especificado de casas decimais.</span><span class="sxs-lookup"><span data-stu-id="1a8a6-104">The `ROUND` function returns the specified number as a *Real* value after it has been rounded to the specified number of decimal places.</span></span>

## <a name="syntax"></a><span data-ttu-id="1a8a6-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="1a8a6-105">Syntax</span></span>

```
ROUND (number, decimals)
```

## <a name="arguments"></a><span data-ttu-id="1a8a6-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="1a8a6-106">Arguments</span></span>

<span data-ttu-id="1a8a6-107">`number`: *Real*</span><span class="sxs-lookup"><span data-stu-id="1a8a6-107">`number`: *Real*</span></span>

<span data-ttu-id="1a8a6-108">Um valor numérico que deve ser arredondado.</span><span class="sxs-lookup"><span data-stu-id="1a8a6-108">A numeric value that must be rounded.</span></span>

<span data-ttu-id="1a8a6-109">`decimals`: *Inteiro*</span><span class="sxs-lookup"><span data-stu-id="1a8a6-109">`decimals`: *Integer*</span></span>

<span data-ttu-id="1a8a6-110">Um valor numérico que representa o número de casas decimais.</span><span class="sxs-lookup"><span data-stu-id="1a8a6-110">A numeric value that represents the number of decimal places.</span></span>

## <a name="return-values"></a><span data-ttu-id="1a8a6-111">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="1a8a6-111">Return values</span></span>

<span data-ttu-id="1a8a6-112">*Real*</span><span class="sxs-lookup"><span data-stu-id="1a8a6-112">*Real*</span></span>

<span data-ttu-id="1a8a6-113">O valor numérico resultante.</span><span class="sxs-lookup"><span data-stu-id="1a8a6-113">The resulting numeric value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="1a8a6-114">Notas de uso</span><span class="sxs-lookup"><span data-stu-id="1a8a6-114">Usage notes</span></span>

<span data-ttu-id="1a8a6-115">Se o valor do argumento `decimals` for maior do que 0 (zero), o número especificado é arredondado para essa quantidade de casas decimais.</span><span class="sxs-lookup"><span data-stu-id="1a8a6-115">If the value of the `decimals` argument is more than 0 (zero), the specified number is rounded to that many decimal places.</span></span>

<span data-ttu-id="1a8a6-116">Se o valor do argumento `decimals` for **0** (zero), o número especificado é arredondado para o inteiro mais próximo.</span><span class="sxs-lookup"><span data-stu-id="1a8a6-116">If the value of the `decimals` argument is **0** (zero), the specified number is rounded to the nearest integer.</span></span>

<span data-ttu-id="1a8a6-117">Se o valor do argumento `decimals` for menor do que 0 (zero), o número especificado é arredondado para a esquerda do separador decimal.</span><span class="sxs-lookup"><span data-stu-id="1a8a6-117">If the value of the `decimals` argument is less than 0 (zero), the specified number is rounded to the left of the decimal point.</span></span>

## <a name="example-1"></a><span data-ttu-id="1a8a6-118">Exemplo 1</span><span class="sxs-lookup"><span data-stu-id="1a8a6-118">Example 1</span></span>

<span data-ttu-id="1a8a6-119">`ROUND (1200.767, 2)` arredonda para duas casas decimais e retorna **1200,77**.</span><span class="sxs-lookup"><span data-stu-id="1a8a6-119">`ROUND (1200.767, 2)` rounds to two decimal places and returns **1200.77**.</span></span>

## <a name="example-2"></a><span data-ttu-id="1a8a6-120">Exemplo 2</span><span class="sxs-lookup"><span data-stu-id="1a8a6-120">Example 2</span></span>

<span data-ttu-id="1a8a6-121">`ROUND (1200.767, -3)` arredonda para o múltiplo mais próximo de 1.000 e retorna **1000**.</span><span class="sxs-lookup"><span data-stu-id="1a8a6-121">`ROUND (1200.767, -3)` rounds to the nearest multiple of 1,000 and returns **1000**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="1a8a6-122">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="1a8a6-122">Additional resources</span></span>

[<span data-ttu-id="1a8a6-123">Funções matemáticas</span><span class="sxs-lookup"><span data-stu-id="1a8a6-123">Mathematical functions</span></span>](er-functions-category-mathematical.md)
