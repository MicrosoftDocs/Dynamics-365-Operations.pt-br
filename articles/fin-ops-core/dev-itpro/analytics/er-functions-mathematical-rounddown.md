---
title: Função de ER ROUNDDOWN
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) ROUNDDOWN é usada.
author: NickSelin
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
ms.openlocfilehash: 89fc134ec11a47506211ce68ec3aaf966d9a308b
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5744454"
---
# <a name="rounddown-er-function"></a><span data-ttu-id="b2446-103">Função de ER ROUNDDOWN</span><span class="sxs-lookup"><span data-stu-id="b2446-103">ROUNDDOWN ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b2446-104">A função `ROUNDDOWN` retorna o número especificado como um valor *Real* após ele ser arredondado para baixo para o número especificado de casas decimais.</span><span class="sxs-lookup"><span data-stu-id="b2446-104">The `ROUNDDOWN` function returns the specified number as a *Real* value after it has been rounded down to the specified number of decimal places.</span></span>

## <a name="syntax"></a><span data-ttu-id="b2446-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="b2446-105">Syntax</span></span>

```vb
ROUNDDOWN (number, decimals)
```

## <a name="arguments"></a><span data-ttu-id="b2446-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="b2446-106">Arguments</span></span>

<span data-ttu-id="b2446-107">`number`: *Real*</span><span class="sxs-lookup"><span data-stu-id="b2446-107">`number`: *Real*</span></span>

<span data-ttu-id="b2446-108">Um valor numérico que deve ser arredondado para baixo.</span><span class="sxs-lookup"><span data-stu-id="b2446-108">A numeric value that must be rounded down.</span></span>

<span data-ttu-id="b2446-109">`decimals`: *Inteiro*</span><span class="sxs-lookup"><span data-stu-id="b2446-109">`decimals`: *Integer*</span></span>

<span data-ttu-id="b2446-110">Um valor numérico que representa o número de casas decimais.</span><span class="sxs-lookup"><span data-stu-id="b2446-110">A numeric value that represents the number of decimal places.</span></span>

## <a name="return-values"></a><span data-ttu-id="b2446-111">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="b2446-111">Return values</span></span>

<span data-ttu-id="b2446-112">*Real*</span><span class="sxs-lookup"><span data-stu-id="b2446-112">*Real*</span></span>

<span data-ttu-id="b2446-113">O valor numérico resultante.</span><span class="sxs-lookup"><span data-stu-id="b2446-113">The resulting numeric value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="b2446-114">Notas de uso</span><span class="sxs-lookup"><span data-stu-id="b2446-114">Usage notes</span></span>

<span data-ttu-id="b2446-115">Esta função comporta-se como [ROUND](er-functions-mathematical-round.md), mas sempre arredonda o número especificado para baixo (para zero).</span><span class="sxs-lookup"><span data-stu-id="b2446-115">This function behaves like [ROUND](er-functions-mathematical-round.md), but it always rounds the specified number down (toward zero).</span></span>

## <a name="example-1"></a><span data-ttu-id="b2446-116">Exemplo 1</span><span class="sxs-lookup"><span data-stu-id="b2446-116">Example 1</span></span>

<span data-ttu-id="b2446-117">`ROUNDDOWN (1200.767, 2)` arredonda para baixo para duas casas decimais e retorna **1200,76**.</span><span class="sxs-lookup"><span data-stu-id="b2446-117">`ROUNDDOWN (1200.767, 2)` rounds down to two decimal places and returns **1200.76**.</span></span> 

## <a name="example-2"></a><span data-ttu-id="b2446-118">Exemplo 2</span><span class="sxs-lookup"><span data-stu-id="b2446-118">Example 2</span></span>

<span data-ttu-id="b2446-119">`ROUNDDOWN (1700.767, -3)` arredonda para baixo para o múltiplo mais próximo de 1.000 e retorna **1000**.</span><span class="sxs-lookup"><span data-stu-id="b2446-119">`ROUNDDOWN (1700.767, -3)` rounds down to the nearest multiple of 1,000 and returns **1000**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="b2446-120">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="b2446-120">Additional resources</span></span>

[<span data-ttu-id="b2446-121">Funções matemáticas</span><span class="sxs-lookup"><span data-stu-id="b2446-121">Mathematical functions</span></span>](er-functions-category-mathematical.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]