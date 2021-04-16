---
title: Função DAYS ER
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) DAYS é usada.
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
ms.openlocfilehash: 310359a29a506d69d1f34aaa710a82b0f2ea528e
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5746882"
---
# <a name="days-er-function"></a><span data-ttu-id="a1272-103">Função DAYS ER</span><span class="sxs-lookup"><span data-stu-id="a1272-103">DAYS ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="a1272-104">A função `DAYS` retorna um valor *Inteiro* que representa o número de dias entre uma data especificada e uma segunda data especificada.</span><span class="sxs-lookup"><span data-stu-id="a1272-104">The `DAYS` function returns an *Integer* value that represents the number of days between one specified date and a second specified date.</span></span>

## <a name="syntax"></a><span data-ttu-id="a1272-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="a1272-105">Syntax</span></span>

```vb
DAYS (date 1, date 2) as Integer
```

## <a name="arguments"></a><span data-ttu-id="a1272-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="a1272-106">Arguments</span></span>

<span data-ttu-id="a1272-107">`date 1`: *Data*</span><span class="sxs-lookup"><span data-stu-id="a1272-107">`date 1`: *Date*</span></span>

<span data-ttu-id="a1272-108">Um valor de data que representa a data inicial para o cálculo do número de dias.</span><span class="sxs-lookup"><span data-stu-id="a1272-108">A date value that represents the start date for the calculation of the number of days.</span></span>

<span data-ttu-id="a1272-109">`date 2`: *Data*</span><span class="sxs-lookup"><span data-stu-id="a1272-109">`date 2`: *Date*</span></span>

<span data-ttu-id="a1272-110">Um valor de data que representa a data final para o cálculo do número de dias.</span><span class="sxs-lookup"><span data-stu-id="a1272-110">A date value that represents the end date for the calculation of the number of days.</span></span>

## <a name="return-values"></a><span data-ttu-id="a1272-111">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="a1272-111">Return values</span></span>

<span data-ttu-id="a1272-112">*Inteiro*</span><span class="sxs-lookup"><span data-stu-id="a1272-112">*Integer*</span></span>

<span data-ttu-id="a1272-113">O valor numérico resultante.</span><span class="sxs-lookup"><span data-stu-id="a1272-113">The resulting numeric value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="a1272-114">Notas de uso</span><span class="sxs-lookup"><span data-stu-id="a1272-114">Usage notes</span></span>

<span data-ttu-id="a1272-115">A função `DAYS` retorna um valor positivo quando a primeira data for posterior à segunda, retorna **0** (zero) quando a primeira data for igual à segunda e retorna um valor negativo quando a primeira data for anterior à segunda data.</span><span class="sxs-lookup"><span data-stu-id="a1272-115">The `DAYS` function returns a positive value when the first date is later than the second date, it returns **0** (zero) when the first date equals the second date, and it returns a negative value when the first date is earlier than the second date.</span></span>

## <a name="example"></a><span data-ttu-id="a1272-116">Exemplo</span><span class="sxs-lookup"><span data-stu-id="a1272-116">Example</span></span>

<span data-ttu-id="a1272-117">`DAYS (TODAY (), DATEVALUE( DATETIMEFORMAT( ADDDAYS ( NOW(), 1), "yyyyMMdd"), "yyyyMMdd"))` retorna **-1**.</span><span class="sxs-lookup"><span data-stu-id="a1272-117">`DAYS (TODAY (), DATEVALUE( DATETIMEFORMAT( ADDDAYS ( NOW(), 1), "yyyyMMdd"), "yyyyMMdd"))` returns **-1**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="a1272-118">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="a1272-118">Additional resources</span></span>

[<span data-ttu-id="a1272-119">Funções de data e de hora</span><span class="sxs-lookup"><span data-stu-id="a1272-119">Date and time functions</span></span>](er-functions-category-datetime.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]