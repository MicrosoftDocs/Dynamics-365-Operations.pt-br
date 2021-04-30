---
title: Função DATEFORMAT ER
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) DATEFORMAT é usada.
author: NickSelin
ms.date: 01/04/2021
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
ms.openlocfilehash: 1b3a0a2608328b233004034f7ab2ccfa833c17e3
ms.sourcegitcommit: 951393b05bf409333cb3c7ad977bcaa804aa801b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/13/2021
ms.locfileid: "5890901"
---
# <a name="dateformat-er-function"></a><span data-ttu-id="ef4a5-103">Função DATEFORMAT ER</span><span class="sxs-lookup"><span data-stu-id="ef4a5-103">DATEFORMAT ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="ef4a5-104">A função `DATEFORMAT` retorna um valor de *Cadeia de caracteres* que apresenta um valor de data determinado como texto no formato especificado e em uma [cultura](/bingmaps/rest-services/common-parameters-and-types/supported-culture-codes) opcionalmente especificada.</span><span class="sxs-lookup"><span data-stu-id="ef4a5-104">The `DATEFORMAT` function returns a *String* value that presents a given date value as text in the specified format and in an optionally specified [culture](/bingmaps/rest-services/common-parameters-and-types/supported-culture-codes).</span></span> <span data-ttu-id="ef4a5-105">Para obter informações sobre os formatos com suporte, consulte [padrão](/dotnet/standard/base-types/standard-date-and-time-format-strings) e [personalizado](/dotnet/standard/base-types/custom-date-and-time-format-strings).</span><span class="sxs-lookup"><span data-stu-id="ef4a5-105">For information about the supported formats, see [standard](/dotnet/standard/base-types/standard-date-and-time-format-strings) and [custom](/dotnet/standard/base-types/custom-date-and-time-format-strings).</span></span>

## <a name="syntax-1"></a><span data-ttu-id="ef4a5-106">Sintaxe 1</span><span class="sxs-lookup"><span data-stu-id="ef4a5-106">Syntax 1</span></span>

```vb
DATEFORMAT (date, format)
```

## <a name="syntax-2"></a><span data-ttu-id="ef4a5-107">Sintaxe 2</span><span class="sxs-lookup"><span data-stu-id="ef4a5-107">Syntax 2</span></span>

```vb
DATEFORMAT (date, format, culture)
```

## <a name="arguments"></a><span data-ttu-id="ef4a5-108">Argumentos</span><span class="sxs-lookup"><span data-stu-id="ef4a5-108">Arguments</span></span>

<span data-ttu-id="ef4a5-109">`date`: *Data*</span><span class="sxs-lookup"><span data-stu-id="ef4a5-109">`date`: *Date*</span></span>

<span data-ttu-id="ef4a5-110">Um valor de data que representa a data do formato.</span><span class="sxs-lookup"><span data-stu-id="ef4a5-110">A date value that represents the date to format.</span></span>

<span data-ttu-id="ef4a5-111">`format`: *Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="ef4a5-111">`format`: *String*</span></span>

<span data-ttu-id="ef4a5-112">O formato da cadeia de caracteres de saída.</span><span class="sxs-lookup"><span data-stu-id="ef4a5-112">The format of the output string.</span></span>

> [!NOTE]
> <span data-ttu-id="ef4a5-113">A cadeia de caracteres de formato diferencia maiúsculas de minúsculas quando você usa um formato padrão ou um formato personalizado.</span><span class="sxs-lookup"><span data-stu-id="ef4a5-113">The format string is case-sensitive when you use either a standard format or a custom format.</span></span> <span data-ttu-id="ef4a5-114">Por exemplo, o especificador de formato "d" [padrão](/dotnet/standard/base-types/standard-date-and-time-format-strings) retorna a data usando o padrão de data abreviada, enquanto o especificador de formato "D" padrão retorna a data usando o padrão de data por extenso.</span><span class="sxs-lookup"><span data-stu-id="ef4a5-114">For example, the [standard](/dotnet/standard/base-types/standard-date-and-time-format-strings) "d" format specifier returns the date by using the short date pattern, whereas the standard "D" format specifier returns the date by using the long date pattern.</span></span> <span data-ttu-id="ef4a5-115">Além disso, o especificador de formato "M" [personalizado](/dotnet/standard/base-types/custom-date-and-time-format-strings) retorna o mês de 1 a 12, enquanto o especificador "m" de formato personalizado retorna o minuto de 0 a 59.</span><span class="sxs-lookup"><span data-stu-id="ef4a5-115">Additionally, the [custom](/dotnet/standard/base-types/custom-date-and-time-format-strings) "M" format specifier returns the month from 1 through 12, whereas the custom "m" format specifier returns the minute from 0 through 59.</span></span>

<span data-ttu-id="ef4a5-116">`culture`: *Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="ef4a5-116">`culture`: *String*</span></span>

<span data-ttu-id="ef4a5-117">A cultura a ser usada para formatação.</span><span class="sxs-lookup"><span data-stu-id="ef4a5-117">The culture to use for formatting.</span></span>

## <a name="return-values"></a><span data-ttu-id="ef4a5-118">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="ef4a5-118">Return values</span></span>

<span data-ttu-id="ef4a5-119">*Sequência de caracteres*</span><span class="sxs-lookup"><span data-stu-id="ef4a5-119">*String*</span></span>

<span data-ttu-id="ef4a5-120">O valor da cadeia de caracteres resultante.</span><span class="sxs-lookup"><span data-stu-id="ef4a5-120">The resulting string value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="ef4a5-121">Notas de uso</span><span class="sxs-lookup"><span data-stu-id="ef4a5-121">Usage notes</span></span>

<span data-ttu-id="ef4a5-122">Se a cultura não é definida como um argumento da função chamada, o valor de `culture` é definido pelo contexto de chamada.</span><span class="sxs-lookup"><span data-stu-id="ef4a5-122">If the culture isn't defined as an argument of the called function, the value of `culture` is defined by the calling context.</span></span> <span data-ttu-id="ef4a5-123">Por exemplo, se a função `DATEFORMAT` for chamada usando a sintaxe 1 em um formato de relatório eletrônico (ER) para um elemento **FILE** de arquivo configurado para usar a cultura alemã, a conversão será feita usando a cultura alemã.</span><span class="sxs-lookup"><span data-stu-id="ef4a5-123">For example, if the `DATEFORMAT` function is called by using syntax 1 in an Electronic reporting (ER) format for a **FILE** element that is configured to use the German culture, the conversion will be done by using the German culture.</span></span> <span data-ttu-id="ef4a5-124">O valor padrão `culture` é **EN-US**.</span><span class="sxs-lookup"><span data-stu-id="ef4a5-124">The default `culture` value is **EN-US**.</span></span>

## <a name="example-1"></a><span data-ttu-id="ef4a5-125">Exemplo 1</span><span class="sxs-lookup"><span data-stu-id="ef4a5-125">Example 1</span></span>

<span data-ttu-id="ef4a5-126">`DATEFORMAT (TODAY (), "dd-MM-yyyy")` retorna a data atual do servidor do aplicativo, 24 de dezembro de 2015, como a cadeia de caracteres **"24-12-2015"**, com base no formato personalizado especificado.</span><span class="sxs-lookup"><span data-stu-id="ef4a5-126">`DATEFORMAT (TODAY (), "dd-MM-yyyy")` returns the current application server date, December 24, 2015, as the string **"24-12-2015"**, based on the specified custom format.</span></span>

## <a name="example-2"></a><span data-ttu-id="ef4a5-127">Exemplo 2</span><span class="sxs-lookup"><span data-stu-id="ef4a5-127">Example 2</span></span>

<span data-ttu-id="ef4a5-128">`DATEFORMAT (SESSIONTODAY (), "d", "DE")` retorna a data atual da sessão do aplicativo, 24 de dezembro de 2015, como a cadeia de caracteres **"24-12-2015"**, com base na cultura alemã selecionada e no formato especificado.</span><span class="sxs-lookup"><span data-stu-id="ef4a5-128">`DATEFORMAT (SESSIONTODAY (), "d", "DE")` returns the current application session date, December 24, 2015, as the string **"24-12-2015"**, based on the selected German culture and the specified format.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="ef4a5-129">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="ef4a5-129">Additional resources</span></span>

[<span data-ttu-id="ef4a5-130">Funções de data e de hora</span><span class="sxs-lookup"><span data-stu-id="ef4a5-130">Date and time functions</span></span>](er-functions-category-datetime.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]