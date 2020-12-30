---
title: Função ADDDAYS ER
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) ADDDAYS é usada.
author: NickSelin
manager: kfend
ms.date: 12/03/2019
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
ms.openlocfilehash: e3d90c19ddc64286843347976c000267e416bf05
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2020
ms.locfileid: "4688434"
---
# <a name="adddays-er-function"></a><span data-ttu-id="156c5-103">Função ADDDAYS ER</span><span class="sxs-lookup"><span data-stu-id="156c5-103">ADDDAYS ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="156c5-104">A função `ADDDAYS` calcula um valor *DateTime* que é o número especificado de dias antes ou depois de uma data inicial especificada.</span><span class="sxs-lookup"><span data-stu-id="156c5-104">The `ADDDAYS` function calculates a *DateTime* value that is the specified number of days before or after a specified start date.</span></span>

## <a name="syntax"></a><span data-ttu-id="156c5-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="156c5-105">Syntax</span></span>

```vb
ADDDAYS (datetime, days)
```

## <a name="arguments"></a><span data-ttu-id="156c5-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="156c5-106">Arguments</span></span>

<span data-ttu-id="156c5-107">`datetime`: *DateTime*</span><span class="sxs-lookup"><span data-stu-id="156c5-107">`datetime`: *DateTime*</span></span>

<span data-ttu-id="156c5-108">Um valor de data/hora que representa a data inicial.</span><span class="sxs-lookup"><span data-stu-id="156c5-108">A date/time value that represents the start date.</span></span>

<span data-ttu-id="156c5-109">`days`: *Inteiro*</span><span class="sxs-lookup"><span data-stu-id="156c5-109">`days`: *Integer*</span></span>

<span data-ttu-id="156c5-110">O número de dias antes ou depois de `datetime`.</span><span class="sxs-lookup"><span data-stu-id="156c5-110">The number of days before or after `datetime`.</span></span>

## <a name="return-values"></a><span data-ttu-id="156c5-111">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="156c5-111">Return values</span></span>

<span data-ttu-id="156c5-112">*Data/Hora*</span><span class="sxs-lookup"><span data-stu-id="156c5-112">*DateTime*</span></span>

<span data-ttu-id="156c5-113">O valor de data/hora resultante.</span><span class="sxs-lookup"><span data-stu-id="156c5-113">The resulting date/time value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="156c5-114">Notas de uso</span><span class="sxs-lookup"><span data-stu-id="156c5-114">Usage notes</span></span>

<span data-ttu-id="156c5-115">Um valor positivo para `days` gera uma data futura.</span><span class="sxs-lookup"><span data-stu-id="156c5-115">A positive value for `days` yields a future date.</span></span> <span data-ttu-id="156c5-116">Um valor negativo gera uma data passada.</span><span class="sxs-lookup"><span data-stu-id="156c5-116">A negative value yields a past date.</span></span>

## <a name="example-1"></a><span data-ttu-id="156c5-117">Exemplo 1</span><span class="sxs-lookup"><span data-stu-id="156c5-117">Example 1</span></span>

<span data-ttu-id="156c5-118">`ADDDAYS (NOW(), 7)` retorna a data e a hora de sete dias no futuro.</span><span class="sxs-lookup"><span data-stu-id="156c5-118">`ADDDAYS (NOW(), 7)` returns the date and time seven days in the future.</span></span>

## <a name="example-2"></a><span data-ttu-id="156c5-119">Exemplo 2</span><span class="sxs-lookup"><span data-stu-id="156c5-119">Example 2</span></span>

<span data-ttu-id="156c5-120">`ADDDAYS (NOW(), -3)` retorna a data e a hora de três dias no passado.</span><span class="sxs-lookup"><span data-stu-id="156c5-120">`ADDDAYS (NOW(), -3)` returns the date and time three days in the past.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="156c5-121">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="156c5-121">Additional resources</span></span>

[<span data-ttu-id="156c5-122">Funções de data e de hora</span><span class="sxs-lookup"><span data-stu-id="156c5-122">Date and time functions</span></span>](er-functions-category-datetime.md)
