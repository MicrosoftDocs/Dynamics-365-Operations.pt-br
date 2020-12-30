---
title: Função DAYS ER
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) DAYS é usada.
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
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 66398e624e4b9d69d4dc3ccf3ee8f97758f4f861
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2020
ms.locfileid: "4682332"
---
# <a name="days-er-function"></a><span data-ttu-id="9f06f-103">Função DAYS ER</span><span class="sxs-lookup"><span data-stu-id="9f06f-103">DAYS ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="9f06f-104">A função `DAYS` retorna um valor *Inteiro* que representa o número de dias entre uma data especificada e uma segunda data especificada.</span><span class="sxs-lookup"><span data-stu-id="9f06f-104">The `DAYS` function returns an *Integer* value that represents the number of days between one specified date and a second specified date.</span></span>

## <a name="syntax"></a><span data-ttu-id="9f06f-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="9f06f-105">Syntax</span></span>

```vb
DAYS (date 1, date 2) as Integer
```

## <a name="arguments"></a><span data-ttu-id="9f06f-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="9f06f-106">Arguments</span></span>

<span data-ttu-id="9f06f-107">`date 1`: *Data*</span><span class="sxs-lookup"><span data-stu-id="9f06f-107">`date 1`: *Date*</span></span>

<span data-ttu-id="9f06f-108">Um valor de data que representa a data inicial para o cálculo do número de dias.</span><span class="sxs-lookup"><span data-stu-id="9f06f-108">A date value that represents the start date for the calculation of the number of days.</span></span>

<span data-ttu-id="9f06f-109">`date 2`: *Data*</span><span class="sxs-lookup"><span data-stu-id="9f06f-109">`date 2`: *Date*</span></span>

<span data-ttu-id="9f06f-110">Um valor de data que representa a data final para o cálculo do número de dias.</span><span class="sxs-lookup"><span data-stu-id="9f06f-110">A date value that represents the end date for the calculation of the number of days.</span></span>

## <a name="return-values"></a><span data-ttu-id="9f06f-111">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="9f06f-111">Return values</span></span>

<span data-ttu-id="9f06f-112">*Inteiro*</span><span class="sxs-lookup"><span data-stu-id="9f06f-112">*Integer*</span></span>

<span data-ttu-id="9f06f-113">O valor numérico resultante.</span><span class="sxs-lookup"><span data-stu-id="9f06f-113">The resulting numeric value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="9f06f-114">Notas de uso</span><span class="sxs-lookup"><span data-stu-id="9f06f-114">Usage notes</span></span>

<span data-ttu-id="9f06f-115">A função `DAYS` retorna um valor positivo quando a primeira data for posterior à segunda, retorna **0** (zero) quando a primeira data for igual à segunda e retorna um valor negativo quando a primeira data for anterior à segunda data.</span><span class="sxs-lookup"><span data-stu-id="9f06f-115">The `DAYS` function returns a positive value when the first date is later than the second date, it returns **0** (zero) when the first date equals the second date, and it returns a negative value when the first date is earlier than the second date.</span></span>

## <a name="example"></a><span data-ttu-id="9f06f-116">Exemplo</span><span class="sxs-lookup"><span data-stu-id="9f06f-116">Example</span></span>

<span data-ttu-id="9f06f-117">`DAYS (TODAY (), DATEVALUE( DATETIMEFORMAT( ADDDAYS ( NOW(), 1), "yyyyMMdd"), "yyyyMMdd"))` retorna **-1**.</span><span class="sxs-lookup"><span data-stu-id="9f06f-117">`DAYS (TODAY (), DATEVALUE( DATETIMEFORMAT( ADDDAYS ( NOW(), 1), "yyyyMMdd"), "yyyyMMdd"))` returns **-1**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="9f06f-118">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="9f06f-118">Additional resources</span></span>

[<span data-ttu-id="9f06f-119">Funções de data e de hora</span><span class="sxs-lookup"><span data-stu-id="9f06f-119">Date and time functions</span></span>](er-functions-category-datetime.md)
