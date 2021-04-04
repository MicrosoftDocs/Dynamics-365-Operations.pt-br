---
title: Função ADDDAYS ER
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) ADDDAYS é usada.
author: NickSelin
manager: kfend
ms.date: 12/03/2019
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
ms.openlocfilehash: 85ad6508c0d16796efbf1ad81e25d74365de8f30
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/09/2021
ms.locfileid: "5570763"
---
# <a name="adddays-er-function"></a><span data-ttu-id="8444f-103">Função ADDDAYS ER</span><span class="sxs-lookup"><span data-stu-id="8444f-103">ADDDAYS ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="8444f-104">A função `ADDDAYS` calcula um valor *DateTime* que é o número especificado de dias antes ou depois de uma data inicial especificada.</span><span class="sxs-lookup"><span data-stu-id="8444f-104">The `ADDDAYS` function calculates a *DateTime* value that is the specified number of days before or after a specified start date.</span></span>

## <a name="syntax"></a><span data-ttu-id="8444f-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="8444f-105">Syntax</span></span>

```vb
ADDDAYS (datetime, days)
```

## <a name="arguments"></a><span data-ttu-id="8444f-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="8444f-106">Arguments</span></span>

<span data-ttu-id="8444f-107">`datetime`: *DateTime*</span><span class="sxs-lookup"><span data-stu-id="8444f-107">`datetime`: *DateTime*</span></span>

<span data-ttu-id="8444f-108">Um valor de data/hora que representa a data inicial.</span><span class="sxs-lookup"><span data-stu-id="8444f-108">A date/time value that represents the start date.</span></span>

<span data-ttu-id="8444f-109">`days`: *Inteiro*</span><span class="sxs-lookup"><span data-stu-id="8444f-109">`days`: *Integer*</span></span>

<span data-ttu-id="8444f-110">O número de dias antes ou depois de `datetime`.</span><span class="sxs-lookup"><span data-stu-id="8444f-110">The number of days before or after `datetime`.</span></span>

## <a name="return-values"></a><span data-ttu-id="8444f-111">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="8444f-111">Return values</span></span>

<span data-ttu-id="8444f-112">*Data/Hora*</span><span class="sxs-lookup"><span data-stu-id="8444f-112">*DateTime*</span></span>

<span data-ttu-id="8444f-113">O valor de data/hora resultante.</span><span class="sxs-lookup"><span data-stu-id="8444f-113">The resulting date/time value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="8444f-114">Notas de uso</span><span class="sxs-lookup"><span data-stu-id="8444f-114">Usage notes</span></span>

<span data-ttu-id="8444f-115">Um valor positivo para `days` gera uma data futura.</span><span class="sxs-lookup"><span data-stu-id="8444f-115">A positive value for `days` yields a future date.</span></span> <span data-ttu-id="8444f-116">Um valor negativo gera uma data passada.</span><span class="sxs-lookup"><span data-stu-id="8444f-116">A negative value yields a past date.</span></span>

## <a name="example-1"></a><span data-ttu-id="8444f-117">Exemplo 1</span><span class="sxs-lookup"><span data-stu-id="8444f-117">Example 1</span></span>

<span data-ttu-id="8444f-118">`ADDDAYS (NOW(), 7)` retorna a data e a hora de sete dias no futuro.</span><span class="sxs-lookup"><span data-stu-id="8444f-118">`ADDDAYS (NOW(), 7)` returns the date and time seven days in the future.</span></span>

## <a name="example-2"></a><span data-ttu-id="8444f-119">Exemplo 2</span><span class="sxs-lookup"><span data-stu-id="8444f-119">Example 2</span></span>

<span data-ttu-id="8444f-120">`ADDDAYS (NOW(), -3)` retorna a data e a hora de três dias no passado.</span><span class="sxs-lookup"><span data-stu-id="8444f-120">`ADDDAYS (NOW(), -3)` returns the date and time three days in the past.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="8444f-121">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="8444f-121">Additional resources</span></span>

[<span data-ttu-id="8444f-122">Funções de data e de hora</span><span class="sxs-lookup"><span data-stu-id="8444f-122">Date and time functions</span></span>](er-functions-category-datetime.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]