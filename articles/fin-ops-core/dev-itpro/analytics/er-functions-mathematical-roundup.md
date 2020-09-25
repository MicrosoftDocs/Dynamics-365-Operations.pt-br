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
ms.openlocfilehash: 83262a11f92a924e5e49461cf414fb07ab278541
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/01/2020
ms.locfileid: "3744494"
---
# <a name="roundup-er-function"></a><span data-ttu-id="457eb-103">Função de ER ROUNDUP</span><span class="sxs-lookup"><span data-stu-id="457eb-103">ROUNDUP ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="457eb-104">A função `ROUNDUP` retorna o número especificado como um valor *Real* após ele ser arredondado para cima para o número especificado de casas decimais.</span><span class="sxs-lookup"><span data-stu-id="457eb-104">The `ROUNDUP` function returns the specified number as a *Real* value after it has been rounded up to the specified number of decimal places.</span></span>

## <a name="syntax"></a><span data-ttu-id="457eb-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="457eb-105">Syntax</span></span>

```vb
ROUNDDOWN (number, decimals)
```

## <a name="arguments"></a><span data-ttu-id="457eb-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="457eb-106">Arguments</span></span>

<span data-ttu-id="457eb-107">`number`: *Real*</span><span class="sxs-lookup"><span data-stu-id="457eb-107">`number`: *Real*</span></span>

<span data-ttu-id="457eb-108">Um valor numérico que deve ser arredondado para cima.</span><span class="sxs-lookup"><span data-stu-id="457eb-108">A numeric value that must be rounded up.</span></span>

<span data-ttu-id="457eb-109">`decimals`: *Inteiro*</span><span class="sxs-lookup"><span data-stu-id="457eb-109">`decimals`: *Integer*</span></span>

<span data-ttu-id="457eb-110">Um valor numérico que representa o número de casas decimais.</span><span class="sxs-lookup"><span data-stu-id="457eb-110">A numeric value that represents the number of decimal places.</span></span>

## <a name="return-values"></a><span data-ttu-id="457eb-111">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="457eb-111">Return values</span></span>

<span data-ttu-id="457eb-112">*Real*</span><span class="sxs-lookup"><span data-stu-id="457eb-112">*Real*</span></span>

<span data-ttu-id="457eb-113">O valor numérico resultante.</span><span class="sxs-lookup"><span data-stu-id="457eb-113">The resulting numeric value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="457eb-114">Notas de uso</span><span class="sxs-lookup"><span data-stu-id="457eb-114">Usage notes</span></span>

<span data-ttu-id="457eb-115">Esta função comporta-se como [ROUND](er-functions-mathematical-round.md), mas sempre arredonda o número especificado para cima (longe do zero).</span><span class="sxs-lookup"><span data-stu-id="457eb-115">This function behaves like [ROUND](er-functions-mathematical-round.md), but it always rounds the specified number up (away from zero).</span></span>

## <a name="example-1"></a><span data-ttu-id="457eb-116">Exemplo 1</span><span class="sxs-lookup"><span data-stu-id="457eb-116">Example 1</span></span>

<span data-ttu-id="457eb-117">`ROUNDUP (1200.763, 2)` arredonda para cima para duas casas decimais e retorna **1200,77**.</span><span class="sxs-lookup"><span data-stu-id="457eb-117">`ROUNDUP (1200.763, 2)` rounds up to two decimal places and returns **1200.77**.</span></span>

## <a name="example-2"></a><span data-ttu-id="457eb-118">Exemplo 2</span><span class="sxs-lookup"><span data-stu-id="457eb-118">Example 2</span></span>

<span data-ttu-id="457eb-119">`ROUNDUP (1200.767, -3)` arredonda para cima para o múltiplo mais próximo de 1.000 e retorna **2000**.</span><span class="sxs-lookup"><span data-stu-id="457eb-119">`ROUNDUP (1200.767, -3)` rounds up to the nearest multiple of 1,000 and returns **2000**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="457eb-120">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="457eb-120">Additional resources</span></span>

[<span data-ttu-id="457eb-121">Funções matemáticas</span><span class="sxs-lookup"><span data-stu-id="457eb-121">Mathematical functions</span></span>](er-functions-category-mathematical.md)
