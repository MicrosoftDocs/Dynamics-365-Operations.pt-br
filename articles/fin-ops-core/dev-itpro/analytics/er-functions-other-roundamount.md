---
title: Função de ER ROUNDAMOUNT
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) ROUNDAMOUNT é usada.
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
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 15a84b086b324ec390d88e8b2617022ad4773977
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2020
ms.locfileid: "4683054"
---
# <a name="roundamount-er-function"></a><span data-ttu-id="5ca47-103">Função de ER ROUNDAMOUNT</span><span class="sxs-lookup"><span data-stu-id="5ca47-103">ROUNDAMOUNT ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="5ca47-104">A função `ROUNDAMOUNT` retorna um valor *Real* como resultado do arredondamento do número especificado para o múltiplo mais próximo de outro número de acordo com a regra de arredondamento especificada.</span><span class="sxs-lookup"><span data-stu-id="5ca47-104">The `ROUNDAMOUNT` function returns a *Real* value as the result of the rounding of the specified number to the nearest multiple of another number according to the specified rounding rule.</span></span>

## <a name="syntax"></a><span data-ttu-id="5ca47-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="5ca47-105">Syntax</span></span>

```vb
ROUNDAMOUNT (number, decimals, round rule)
```

## <a name="arguments"></a><span data-ttu-id="5ca47-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="5ca47-106">Arguments</span></span>

<span data-ttu-id="5ca47-107">`number`: *Int* ou *Real*</span><span class="sxs-lookup"><span data-stu-id="5ca47-107">`number`: *Int* or *Real*</span></span>

<span data-ttu-id="5ca47-108">Um valor numérico que deve ser arredondado.</span><span class="sxs-lookup"><span data-stu-id="5ca47-108">A numeric value that must be rounded.</span></span>

<span data-ttu-id="5ca47-109">`decimals`: *Int* ou *Real*</span><span class="sxs-lookup"><span data-stu-id="5ca47-109">`decimals`: *Int* or *Real*</span></span>

<span data-ttu-id="5ca47-110">O valor do parâmetro `number` deve ser arredondado para um múltiplo desse número.</span><span class="sxs-lookup"><span data-stu-id="5ca47-110">The number that the value of the `number` parameter must be rounded to a multiple of.</span></span>

<span data-ttu-id="5ca47-111">`round rule`: *Valor de enumeração*</span><span class="sxs-lookup"><span data-stu-id="5ca47-111">`round rule`: *Enum value*</span></span>

<span data-ttu-id="5ca47-112">Um valor de enumeração da enumeração **RoundOffType** que define a regra de arredondamento.</span><span class="sxs-lookup"><span data-stu-id="5ca47-112">An enumeration value of the **RoundOffType** enumeration that defines the rounding rule.</span></span> <span data-ttu-id="5ca47-113">Essa enumeração oferece os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="5ca47-113">This enumeration offers the following values:</span></span>

- <span data-ttu-id="5ca47-114">Normal (Ordinary)</span><span class="sxs-lookup"><span data-stu-id="5ca47-114">Normal (Ordinary)</span></span>
- <span data-ttu-id="5ca47-115">Para baixo (RoundDown)</span><span class="sxs-lookup"><span data-stu-id="5ca47-115">Downward (RoundDown)</span></span>
- <span data-ttu-id="5ca47-116">Para cima (RoundUp)</span><span class="sxs-lookup"><span data-stu-id="5ca47-116">Rounding-up (RoundUp)</span></span>

## <a name="return-values"></a><span data-ttu-id="5ca47-117">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="5ca47-117">Return values</span></span>

<span data-ttu-id="5ca47-118">*Real*</span><span class="sxs-lookup"><span data-stu-id="5ca47-118">*Real*</span></span>

<span data-ttu-id="5ca47-119">O valor numérico resultante é um múltiplo do valor especificado pelo parâmetro `decimals` e está mais próximo do valor especificado pelo parâmetro `number`.</span><span class="sxs-lookup"><span data-stu-id="5ca47-119">The resulting numeric value is a multiple of the value specified by the `decimals` parameter and is closest to the value specified by the `number` parameter.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="5ca47-120">Notas de uso</span><span class="sxs-lookup"><span data-stu-id="5ca47-120">Usage notes</span></span>

<span data-ttu-id="5ca47-121">Quando o parâmetro `number` é zero, esta função sempre retorna zero.</span><span class="sxs-lookup"><span data-stu-id="5ca47-121">When the `number` parameter is zero, this function always returns zero.</span></span>

<span data-ttu-id="5ca47-122">Quando o parâmetro `decimals` é zero, esta função arredonda para o valor de arredondamento padrão.</span><span class="sxs-lookup"><span data-stu-id="5ca47-122">When the `decimals` parameter is zero, this function rounds to the default round-off value.</span></span> <span data-ttu-id="5ca47-123">Quando o parâmetro `round rule` está definido como **RoundOffType.Ordinary**, o valor de arredondamento padrão é **0,01**.</span><span class="sxs-lookup"><span data-stu-id="5ca47-123">When the `round rule` parameter is set to **RoundOffType.Ordinary**, the default round-off value is **0.01**.</span></span> <span data-ttu-id="5ca47-124">Caso contrário, o valor de arredondamento padrão é **1,0**.</span><span class="sxs-lookup"><span data-stu-id="5ca47-124">Otherwise, the default round-off value is **1.0**.</span></span>

<span data-ttu-id="5ca47-125">Quando o parâmetro `round rule` está definido como **RoundOffType.Ordinary**, esta função arredonda para o valor de arredondamento mais próximo.</span><span class="sxs-lookup"><span data-stu-id="5ca47-125">When the `round rule` parameter is set to **RoundOffType.Ordinary**, this function rounds to the nearest round-off amount.</span></span>

<span data-ttu-id="5ca47-126">Quando o parâmetro `round rule` está definido como **RoundOffType.RoundDown**, esta função arredonda em direção ao zero para o valor de arredondamento mais próximo.</span><span class="sxs-lookup"><span data-stu-id="5ca47-126">When the `round rule` parameter is set to **RoundOffType.RoundDown**, this function rounds towards zero to the nearest round-off amount.</span></span>

<span data-ttu-id="5ca47-127">Quando o parâmetro `round rule` está definido como **RoundOffType.RoundUp**, esta função arredonda se afastando do zero para o valor de arredondamento mais próximo.</span><span class="sxs-lookup"><span data-stu-id="5ca47-127">When the `round rule` parameter is set to **RoundOffType.RoundUp**, this function rounds away from zero to the nearest round-off amount.</span></span>

<span data-ttu-id="5ca47-128">Quando o parâmetro `round rule` está definido como **RoundOffType.Ordinary**, esta função se comporta como a função [MROUND](https://support.office.com/article/mround-function-c299c3b0-15a5-426d-aa4b-d2d5b3baf427) do Excel e a função [ROUND](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/dev-ref/xpp-math-run-time-functions#round) do X++.</span><span class="sxs-lookup"><span data-stu-id="5ca47-128">When the `round rule` parameter is set to **RoundOffType.Ordinary**, this function behaves like the [MROUND](https://support.office.com/article/mround-function-c299c3b0-15a5-426d-aa4b-d2d5b3baf427) Excel function and the [ROUND](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/dev-ref/xpp-math-run-time-functions#round) X++ function.</span></span>

## <a name="remarks"></a><span data-ttu-id="5ca47-129">Comentários</span><span class="sxs-lookup"><span data-stu-id="5ca47-129">Remarks</span></span>

<span data-ttu-id="5ca47-130">Para arredondar um valor numérico para um número especificado de casas decimais, use a função [ROUND](er-functions-mathematical-round.md).</span><span class="sxs-lookup"><span data-stu-id="5ca47-130">To round a numeric value to a specified number of decimal places, use the [ROUND](er-functions-mathematical-round.md) function.</span></span>

## <a name="example"></a><span data-ttu-id="5ca47-131">Exemplo</span><span class="sxs-lookup"><span data-stu-id="5ca47-131">Example</span></span>

<span data-ttu-id="5ca47-132">Se o parâmetro **model.RoundOff** estiver definido como **RoundOffType.Ordinary**, `ROUNDAMOUNT (7.45, 1.05, model.RoundOff)` retorna 7,35.</span><span class="sxs-lookup"><span data-stu-id="5ca47-132">If the **model.RoundOff** parameter is set to **RoundOffType.Ordinary**, `ROUNDAMOUNT (7.45, 1.05, model.RoundOff)` returns 7.35.</span></span> 

<span data-ttu-id="5ca47-133">Se o parâmetro **model.RoundOff** estiver definido como **RoundOffType.RoundDown**, `ROUNDAMOUNT (7.45, 1.05, model.RoundOff)` retorna 7,35.</span><span class="sxs-lookup"><span data-stu-id="5ca47-133">If the **model.RoundOff** parameter is set to **RoundOffType.RoundDown**, `ROUNDAMOUNT (7.45, 1.05, model.RoundOff)` returns 7.35.</span></span> 

<span data-ttu-id="5ca47-134">Se o parâmetro **model.RoundOff** estiver definido como **RoundOffType.RoundUp**, `ROUNDAMOUNT (7.45, 1.05, model.RoundOff)` retorna 8,4.</span><span class="sxs-lookup"><span data-stu-id="5ca47-134">If the **model.RoundOff** parameter is set to **RoundOffType.RoundUp**, `ROUNDAMOUNT (7.45, 1.05, model.RoundOff)` returns 8.4.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="5ca47-135">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="5ca47-135">Additional resources</span></span>

[<span data-ttu-id="5ca47-136">Outras funções (específicas de domínio comercial)</span><span class="sxs-lookup"><span data-stu-id="5ca47-136">Other (business domain–specific) functions</span></span>](er-functions-category-other.md)

[<span data-ttu-id="5ca47-137">Funções matemáticas</span><span class="sxs-lookup"><span data-stu-id="5ca47-137">Mathematical functions</span></span>](er-functions-category-mathematical.md)
