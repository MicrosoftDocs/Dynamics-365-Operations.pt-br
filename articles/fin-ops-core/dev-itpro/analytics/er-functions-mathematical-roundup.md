---
title: Função de ER ROUNDUP
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) ROUNDUP é usada.
author: NickSelin
manager: kfend
ms.date: 12/17/2019
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
ms.openlocfilehash: d23a984bd59c4d2d37c407e3fcfed9c7017dcc7f
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/09/2021
ms.locfileid: "5569326"
---
# <a name="roundup-er-function"></a><span data-ttu-id="0e105-103">Função de ER ROUNDUP</span><span class="sxs-lookup"><span data-stu-id="0e105-103">ROUNDUP ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="0e105-104">A função `ROUNDUP` retorna o número especificado como um valor *Real* após ele ser arredondado para cima para o número especificado de casas decimais.</span><span class="sxs-lookup"><span data-stu-id="0e105-104">The `ROUNDUP` function returns the specified number as a *Real* value after it has been rounded up to the specified number of decimal places.</span></span>

## <a name="syntax"></a><span data-ttu-id="0e105-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="0e105-105">Syntax</span></span>

```vb
ROUNDDOWN (number, decimals)
```

## <a name="arguments"></a><span data-ttu-id="0e105-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="0e105-106">Arguments</span></span>

<span data-ttu-id="0e105-107">`number`: *Real*</span><span class="sxs-lookup"><span data-stu-id="0e105-107">`number`: *Real*</span></span>

<span data-ttu-id="0e105-108">Um valor numérico que deve ser arredondado para cima.</span><span class="sxs-lookup"><span data-stu-id="0e105-108">A numeric value that must be rounded up.</span></span>

<span data-ttu-id="0e105-109">`decimals`: *Inteiro*</span><span class="sxs-lookup"><span data-stu-id="0e105-109">`decimals`: *Integer*</span></span>

<span data-ttu-id="0e105-110">Um valor numérico que representa o número de casas decimais.</span><span class="sxs-lookup"><span data-stu-id="0e105-110">A numeric value that represents the number of decimal places.</span></span>

## <a name="return-values"></a><span data-ttu-id="0e105-111">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="0e105-111">Return values</span></span>

<span data-ttu-id="0e105-112">*Real*</span><span class="sxs-lookup"><span data-stu-id="0e105-112">*Real*</span></span>

<span data-ttu-id="0e105-113">O valor numérico resultante.</span><span class="sxs-lookup"><span data-stu-id="0e105-113">The resulting numeric value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="0e105-114">Notas de uso</span><span class="sxs-lookup"><span data-stu-id="0e105-114">Usage notes</span></span>

<span data-ttu-id="0e105-115">Esta função comporta-se como [ROUND](er-functions-mathematical-round.md), mas sempre arredonda o número especificado para cima (longe do zero).</span><span class="sxs-lookup"><span data-stu-id="0e105-115">This function behaves like [ROUND](er-functions-mathematical-round.md), but it always rounds the specified number up (away from zero).</span></span>

## <a name="example-1"></a><span data-ttu-id="0e105-116">Exemplo 1</span><span class="sxs-lookup"><span data-stu-id="0e105-116">Example 1</span></span>

<span data-ttu-id="0e105-117">`ROUNDUP (1200.763, 2)` arredonda para cima para duas casas decimais e retorna **1200,77**.</span><span class="sxs-lookup"><span data-stu-id="0e105-117">`ROUNDUP (1200.763, 2)` rounds up to two decimal places and returns **1200.77**.</span></span>

## <a name="example-2"></a><span data-ttu-id="0e105-118">Exemplo 2</span><span class="sxs-lookup"><span data-stu-id="0e105-118">Example 2</span></span>

<span data-ttu-id="0e105-119">`ROUNDUP (1200.767, -3)` arredonda para cima para o múltiplo mais próximo de 1.000 e retorna **2000**.</span><span class="sxs-lookup"><span data-stu-id="0e105-119">`ROUNDUP (1200.767, -3)` rounds up to the nearest multiple of 1,000 and returns **2000**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="0e105-120">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="0e105-120">Additional resources</span></span>

[<span data-ttu-id="0e105-121">Funções matemáticas</span><span class="sxs-lookup"><span data-stu-id="0e105-121">Mathematical functions</span></span>](er-functions-category-mathematical.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]