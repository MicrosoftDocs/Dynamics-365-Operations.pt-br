---
title: Função de ER ROUNDUP
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) ROUNDUP é usada.
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
ms.openlocfilehash: 84a62639b49db17fef1abcda75bc5ad7f08d1005
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/20/2019
ms.locfileid: "2917042"
---
# <span data-ttu-id="bced2-103"><a name="ROUNDUP">Função de ER ROUNDUP</a></span><span class="sxs-lookup"><span data-stu-id="bced2-103"><a name="ROUNDUP">ROUNDUP ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="bced2-104">A função `ROUNDUP` retorna o número especificado como um valor *Real* após ele ser arredondado para cima para o número especificado de casas decimais.</span><span class="sxs-lookup"><span data-stu-id="bced2-104">The `ROUNDUP` function returns the specified number as a *Real* value after it has been rounded up to the specified number of decimal places.</span></span>

## <a name="syntax"></a><span data-ttu-id="bced2-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="bced2-105">Syntax</span></span>

```
ROUNDDOWN (number, decimals)
```

## <a name="arguments"></a><span data-ttu-id="bced2-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="bced2-106">Arguments</span></span>

<span data-ttu-id="bced2-107">`number`: *Real*</span><span class="sxs-lookup"><span data-stu-id="bced2-107">`number`: *Real*</span></span>

<span data-ttu-id="bced2-108">Um valor numérico que deve ser arredondado para cima.</span><span class="sxs-lookup"><span data-stu-id="bced2-108">A numeric value that must be rounded up.</span></span>

<span data-ttu-id="bced2-109">`decimals`: *Inteiro*</span><span class="sxs-lookup"><span data-stu-id="bced2-109">`decimals`: *Integer*</span></span>

<span data-ttu-id="bced2-110">Um valor numérico que representa o número de casas decimais.</span><span class="sxs-lookup"><span data-stu-id="bced2-110">A numeric value that represents the number of decimal places.</span></span>

## <a name="return-values"></a><span data-ttu-id="bced2-111">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="bced2-111">Return values</span></span>

<span data-ttu-id="bced2-112">*Real*</span><span class="sxs-lookup"><span data-stu-id="bced2-112">*Real*</span></span>

<span data-ttu-id="bced2-113">O valor numérico resultante.</span><span class="sxs-lookup"><span data-stu-id="bced2-113">The resulting numeric value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="bced2-114">Notas de uso</span><span class="sxs-lookup"><span data-stu-id="bced2-114">Usage notes</span></span>

<span data-ttu-id="bced2-115">Esta função comporta-se como [ROUND](er-functions-mathematical-round.md), mas sempre arredonda o número especificado para cima (longe do zero).</span><span class="sxs-lookup"><span data-stu-id="bced2-115">This function behaves like [ROUND](er-functions-mathematical-round.md), but it always rounds the specified number up (away from zero).</span></span>

## <a name="example-1"></a><span data-ttu-id="bced2-116">Exemplo 1</span><span class="sxs-lookup"><span data-stu-id="bced2-116">Example 1</span></span>

<span data-ttu-id="bced2-117">`ROUNDUP (1200.763, 2)` arredonda para cima para duas casas decimais e retorna **1200,77**.</span><span class="sxs-lookup"><span data-stu-id="bced2-117">`ROUNDUP (1200.763, 2)` rounds up to two decimal places and returns **1200.77**.</span></span>

## <a name="example-2"></a><span data-ttu-id="bced2-118">Exemplo 2</span><span class="sxs-lookup"><span data-stu-id="bced2-118">Example 2</span></span>

<span data-ttu-id="bced2-119">`ROUNDUP (1200.767, -3)` arredonda para cima para o múltiplo mais próximo de 1.000 e retorna **2000**.</span><span class="sxs-lookup"><span data-stu-id="bced2-119">`ROUNDUP (1200.767, -3)` rounds up to the nearest multiple of 1,000 and returns **2000**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="bced2-120">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="bced2-120">Additional resources</span></span>

[<span data-ttu-id="bced2-121">Funções matemáticas</span><span class="sxs-lookup"><span data-stu-id="bced2-121">Mathematical functions</span></span>](er-functions-category-mathematical.md)
