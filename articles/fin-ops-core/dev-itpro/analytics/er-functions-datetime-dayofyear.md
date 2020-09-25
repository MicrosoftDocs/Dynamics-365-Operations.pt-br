---
title: Função DAYOFYEAR ER
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) DAYOFYEAR é usada.
author: NickSelin
manager: kfend
ms.date: 12/04/2019
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
ms.openlocfilehash: 755f5f1de28f95ed682648caf47155ad71c8f4b0
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/01/2020
ms.locfileid: "3745480"
---
# <a name="dayofyear-er-function"></a><span data-ttu-id="df019-103">Função DAYOFYEAR ER</span><span class="sxs-lookup"><span data-stu-id="df019-103">DAYOFYEAR ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="df019-104">A função `DAYOFYEAR` retorna um valor *Inteiro* que representa o número de dias entre 1 de janeiro e a data especificada.</span><span class="sxs-lookup"><span data-stu-id="df019-104">The `DAYOFYEAR` function returns an *Integer* value that represents the number of days between January 1 and the specified date.</span></span>

## <a name="syntax"></a><span data-ttu-id="df019-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="df019-105">Syntax</span></span>

```vb
DAYOFYEAR (date) as Integer
```

## <a name="arguments"></a><span data-ttu-id="df019-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="df019-106">Arguments</span></span>

<span data-ttu-id="df019-107">`date`: *Data*</span><span class="sxs-lookup"><span data-stu-id="df019-107">`date`: *Date*</span></span>

<span data-ttu-id="df019-108">Um valor de data que representa a data para usar o cálculo do número de dias.</span><span class="sxs-lookup"><span data-stu-id="df019-108">A date value that represents the date to use for the calculation of the number of days.</span></span>

## <a name="return-values"></a><span data-ttu-id="df019-109">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="df019-109">Return values</span></span>

<span data-ttu-id="df019-110">*Inteiro*</span><span class="sxs-lookup"><span data-stu-id="df019-110">*Integer*</span></span>

<span data-ttu-id="df019-111">O valor numérico resultante.</span><span class="sxs-lookup"><span data-stu-id="df019-111">The resulting numeric value.</span></span>

## <a name="example-1"></a><span data-ttu-id="df019-112">Exemplo 1</span><span class="sxs-lookup"><span data-stu-id="df019-112">Example 1</span></span>

<span data-ttu-id="df019-113">`DAYOFYEAR (DATEVALUE ("01-03-2016", "dd-MM-yyyy"))` retorna **61**.</span><span class="sxs-lookup"><span data-stu-id="df019-113">`DAYOFYEAR (DATEVALUE ("01-03-2016", "dd-MM-yyyy"))` returns **61**.</span></span>

## <a name="example-2"></a><span data-ttu-id="df019-114">Exemplo 2</span><span class="sxs-lookup"><span data-stu-id="df019-114">Example 2</span></span>

<span data-ttu-id="df019-115">`DAYOFYEAR (DATEVALUE ("01-01-2016", "dd-MM-yyyy"))` retorna **1**.</span><span class="sxs-lookup"><span data-stu-id="df019-115">`DAYOFYEAR (DATEVALUE ("01-01-2016", "dd-MM-yyyy"))` returns **1**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="df019-116">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="df019-116">Additional resources</span></span>

[<span data-ttu-id="df019-117">Funções de data e de hora</span><span class="sxs-lookup"><span data-stu-id="df019-117">Date and time functions</span></span>](er-functions-category-datetime.md)
