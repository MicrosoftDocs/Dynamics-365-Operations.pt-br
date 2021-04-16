---
title: Função DAYOFYEAR ER
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) DAYOFYEAR é usada.
author: NickSelin
ms.date: 12/04/2019
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
ms.openlocfilehash: 569e988db91ff992fb7db6e7fd6e8c6aa6a1a3e8
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5746906"
---
# <a name="dayofyear-er-function"></a><span data-ttu-id="89cf8-103">Função DAYOFYEAR ER</span><span class="sxs-lookup"><span data-stu-id="89cf8-103">DAYOFYEAR ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="89cf8-104">A função `DAYOFYEAR` retorna um valor *Inteiro* que representa o número de dias entre 1 de janeiro e a data especificada.</span><span class="sxs-lookup"><span data-stu-id="89cf8-104">The `DAYOFYEAR` function returns an *Integer* value that represents the number of days between January 1 and the specified date.</span></span>

## <a name="syntax"></a><span data-ttu-id="89cf8-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="89cf8-105">Syntax</span></span>

```vb
DAYOFYEAR (date) as Integer
```

## <a name="arguments"></a><span data-ttu-id="89cf8-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="89cf8-106">Arguments</span></span>

<span data-ttu-id="89cf8-107">`date`: *Data*</span><span class="sxs-lookup"><span data-stu-id="89cf8-107">`date`: *Date*</span></span>

<span data-ttu-id="89cf8-108">Um valor de data que representa a data para usar o cálculo do número de dias.</span><span class="sxs-lookup"><span data-stu-id="89cf8-108">A date value that represents the date to use for the calculation of the number of days.</span></span>

## <a name="return-values"></a><span data-ttu-id="89cf8-109">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="89cf8-109">Return values</span></span>

<span data-ttu-id="89cf8-110">*Inteiro*</span><span class="sxs-lookup"><span data-stu-id="89cf8-110">*Integer*</span></span>

<span data-ttu-id="89cf8-111">O valor numérico resultante.</span><span class="sxs-lookup"><span data-stu-id="89cf8-111">The resulting numeric value.</span></span>

## <a name="example-1"></a><span data-ttu-id="89cf8-112">Exemplo 1</span><span class="sxs-lookup"><span data-stu-id="89cf8-112">Example 1</span></span>

<span data-ttu-id="89cf8-113">`DAYOFYEAR (DATEVALUE ("01-03-2016", "dd-MM-yyyy"))` retorna **61**.</span><span class="sxs-lookup"><span data-stu-id="89cf8-113">`DAYOFYEAR (DATEVALUE ("01-03-2016", "dd-MM-yyyy"))` returns **61**.</span></span>

## <a name="example-2"></a><span data-ttu-id="89cf8-114">Exemplo 2</span><span class="sxs-lookup"><span data-stu-id="89cf8-114">Example 2</span></span>

<span data-ttu-id="89cf8-115">`DAYOFYEAR (DATEVALUE ("01-01-2016", "dd-MM-yyyy"))` retorna **1**.</span><span class="sxs-lookup"><span data-stu-id="89cf8-115">`DAYOFYEAR (DATEVALUE ("01-01-2016", "dd-MM-yyyy"))` returns **1**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="89cf8-116">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="89cf8-116">Additional resources</span></span>

[<span data-ttu-id="89cf8-117">Funções de data e de hora</span><span class="sxs-lookup"><span data-stu-id="89cf8-117">Date and time functions</span></span>](er-functions-category-datetime.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]