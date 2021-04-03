---
title: Função de ER ROUND
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) ROUND é usada.
author: NickSelin
manager: kfend
ms.date: 10/21/2020
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
ms.openlocfilehash: 716ac0bbc9fec992ec1bbfc99bfc86434bf97984
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/09/2021
ms.locfileid: "5570389"
---
# <a name="round-er-function"></a><span data-ttu-id="66b3c-103">Função de ER ROUND</span><span class="sxs-lookup"><span data-stu-id="66b3c-103">ROUND ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="66b3c-104">A função `ROUND` retorna o número especificado como um valor *Real* após ele ser arredondado para o número especificado de casas decimais.</span><span class="sxs-lookup"><span data-stu-id="66b3c-104">The `ROUND` function returns the specified number as a *Real* value after it has been rounded to the specified number of decimal places.</span></span>

## <a name="syntax"></a><span data-ttu-id="66b3c-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="66b3c-105">Syntax</span></span>

```vb
ROUND (number, decimals)
```

## <a name="arguments"></a><span data-ttu-id="66b3c-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="66b3c-106">Arguments</span></span>

<span data-ttu-id="66b3c-107">`number`: *Real*</span><span class="sxs-lookup"><span data-stu-id="66b3c-107">`number`: *Real*</span></span>

<span data-ttu-id="66b3c-108">Um valor numérico que deve ser arredondado.</span><span class="sxs-lookup"><span data-stu-id="66b3c-108">A numeric value that must be rounded.</span></span>

<span data-ttu-id="66b3c-109">`decimals`: *Inteiro*</span><span class="sxs-lookup"><span data-stu-id="66b3c-109">`decimals`: *Integer*</span></span>

<span data-ttu-id="66b3c-110">Um valor numérico que representa o número de casas decimais.</span><span class="sxs-lookup"><span data-stu-id="66b3c-110">A numeric value that represents the number of decimal places.</span></span>

## <a name="return-values"></a><span data-ttu-id="66b3c-111">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="66b3c-111">Return values</span></span>

<span data-ttu-id="66b3c-112">*Real*</span><span class="sxs-lookup"><span data-stu-id="66b3c-112">*Real*</span></span>

<span data-ttu-id="66b3c-113">O valor numérico resultante.</span><span class="sxs-lookup"><span data-stu-id="66b3c-113">The resulting numeric value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="66b3c-114">Notas de uso</span><span class="sxs-lookup"><span data-stu-id="66b3c-114">Usage notes</span></span>

<span data-ttu-id="66b3c-115">Se o valor do argumento `decimals` for maior do que 0 (zero), o número especificado é arredondado para essa quantidade de casas decimais.</span><span class="sxs-lookup"><span data-stu-id="66b3c-115">If the value of the `decimals` argument is more than 0 (zero), the specified number is rounded to that many decimal places.</span></span>

<span data-ttu-id="66b3c-116">Se o valor do argumento `decimals` for **0** (zero), o número especificado é arredondado para o inteiro par mais próximo.</span><span class="sxs-lookup"><span data-stu-id="66b3c-116">If the value of the `decimals` argument is **0** (zero), the specified number is rounded to the nearest even integer.</span></span>

<span data-ttu-id="66b3c-117">Se o valor do argumento `decimals` for menor do que 0 (zero), o número especificado é arredondado para a esquerda do separador decimal.</span><span class="sxs-lookup"><span data-stu-id="66b3c-117">If the value of the `decimals` argument is less than 0 (zero), the specified number is rounded to the left of the decimal point.</span></span>

## <a name="example-1"></a><span data-ttu-id="66b3c-118">Exemplo 1</span><span class="sxs-lookup"><span data-stu-id="66b3c-118">Example 1</span></span>

<span data-ttu-id="66b3c-119">`ROUND (1200.767, 2)` arredonda para duas casas decimais e retorna **1200,77**.</span><span class="sxs-lookup"><span data-stu-id="66b3c-119">`ROUND (1200.767, 2)` rounds to two decimal places and returns **1200.77**.</span></span>

## <a name="example-2"></a><span data-ttu-id="66b3c-120">Exemplo 2</span><span class="sxs-lookup"><span data-stu-id="66b3c-120">Example 2</span></span>

<span data-ttu-id="66b3c-121">`ROUND (1200.767, -3)` arredonda para o múltiplo mais próximo de 1.000 e retorna **1000**.</span><span class="sxs-lookup"><span data-stu-id="66b3c-121">`ROUND (1200.767, -3)` rounds to the nearest multiple of 1,000 and returns **1000**.</span></span>

## <a name="example-3"></a><span data-ttu-id="66b3c-122">Exemplo 3</span><span class="sxs-lookup"><span data-stu-id="66b3c-122">Example 3</span></span>

<span data-ttu-id="66b3c-123">`ROUND (1200.5, 0)` arredonda para o inteiro par mais próximo e retorna **1200**, enquanto `ROUND (1201.5, 0)` faz o mesmo e retorna **1202**.</span><span class="sxs-lookup"><span data-stu-id="66b3c-123">`ROUND (1200.5, 0)` rounds to the nearest even integer and returns **1200**, while `ROUND (1201.5, 0)` does the same and returns **1202**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="66b3c-124">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="66b3c-124">Additional resources</span></span>

[<span data-ttu-id="66b3c-125">Funções matemáticas</span><span class="sxs-lookup"><span data-stu-id="66b3c-125">Mathematical functions</span></span>](er-functions-category-mathematical.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]