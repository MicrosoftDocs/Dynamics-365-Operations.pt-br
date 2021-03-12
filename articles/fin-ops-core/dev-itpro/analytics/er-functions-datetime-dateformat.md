---
title: Função DATEFORMAT ER
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) DATEFORMAT é usada.
author: NickSelin
manager: kfend
ms.date: 01/04/2021
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
ms.openlocfilehash: cdc1671f818bc2c4d8a78d0a35337298e83c5060
ms.sourcegitcommit: 7cfe8931dd454e811a691f5118a4ecae7ba4b478
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/04/2021
ms.locfileid: "4826002"
---
# <a name="dateformat-er-function"></a><span data-ttu-id="9b301-103">Função DATEFORMAT ER</span><span class="sxs-lookup"><span data-stu-id="9b301-103">DATEFORMAT ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="9b301-104">A função `DATEFORMAT` retorna um valor de *Cadeia de caracteres* que apresenta um valor de data determinado como texto no formato especificado e em uma [cultura](https://docs.microsoft.com/bingmaps/rest-services/common-parameters-and-types/supported-culture-codes) opcionalmente especificada.</span><span class="sxs-lookup"><span data-stu-id="9b301-104">The `DATEFORMAT` function returns a *String* value that presents a given date value as text in the specified format and in an optionally specified [culture](https://docs.microsoft.com/bingmaps/rest-services/common-parameters-and-types/supported-culture-codes).</span></span> <span data-ttu-id="9b301-105">Para obter informações sobre os formatos com suporte, consulte [padrão](https://msdn.microsoft.com/library/az4se3k1(v=vs.110).aspx) e [personalizado](https://msdn.microsoft.com/library/8kb3ddd4(v=vs.110).aspx).</span><span class="sxs-lookup"><span data-stu-id="9b301-105">For information about the supported formats, see [standard](https://msdn.microsoft.com/library/az4se3k1(v=vs.110).aspx) and [custom](https://msdn.microsoft.com/library/8kb3ddd4(v=vs.110).aspx).</span></span>

## <a name="syntax-1"></a><span data-ttu-id="9b301-106">Sintaxe 1</span><span class="sxs-lookup"><span data-stu-id="9b301-106">Syntax 1</span></span>

```vb
DATEFORMAT (date, format)
```

## <a name="syntax-2"></a><span data-ttu-id="9b301-107">Sintaxe 2</span><span class="sxs-lookup"><span data-stu-id="9b301-107">Syntax 2</span></span>

```vb
DATEFORMAT (date, format, culture)
```

## <a name="arguments"></a><span data-ttu-id="9b301-108">Argumentos</span><span class="sxs-lookup"><span data-stu-id="9b301-108">Arguments</span></span>

<span data-ttu-id="9b301-109">`date`: *Data*</span><span class="sxs-lookup"><span data-stu-id="9b301-109">`date`: *Date*</span></span>

<span data-ttu-id="9b301-110">Um valor de data que representa a data do formato.</span><span class="sxs-lookup"><span data-stu-id="9b301-110">A date value that represents the date to format.</span></span>

<span data-ttu-id="9b301-111">`format`: *Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="9b301-111">`format`: *String*</span></span>

<span data-ttu-id="9b301-112">O formato da cadeia de caracteres de saída.</span><span class="sxs-lookup"><span data-stu-id="9b301-112">The format of the output string.</span></span>

> [!NOTE]
> <span data-ttu-id="9b301-113">A cadeia de caracteres de formato diferencia maiúsculas de minúsculas quando você usa um formato padrão ou um formato personalizado.</span><span class="sxs-lookup"><span data-stu-id="9b301-113">The format string is case-sensitive when you use either a standard format or a custom format.</span></span> <span data-ttu-id="9b301-114">Por exemplo, o especificador de formato "d" [padrão](https://msdn.microsoft.com/library/az4se3k1(v=vs.110).aspx) retorna a data usando o padrão de data abreviada, enquanto o especificador de formato "D" padrão retorna a data usando o padrão de data por extenso.</span><span class="sxs-lookup"><span data-stu-id="9b301-114">For example, the [standard](https://msdn.microsoft.com/library/az4se3k1(v=vs.110).aspx) "d" format specifier returns the date by using the short date pattern, whereas the standard "D" format specifier returns the date by using the long date pattern.</span></span> <span data-ttu-id="9b301-115">Além disso, o especificador de formato "M" [personalizado](https://msdn.microsoft.com/library/8kb3ddd4(v=vs.110).aspx) retorna o mês de 1 a 12, enquanto o especificador "m" de formato personalizado retorna o minuto de 0 a 59.</span><span class="sxs-lookup"><span data-stu-id="9b301-115">Additionally, the [custom](https://msdn.microsoft.com/library/8kb3ddd4(v=vs.110).aspx) "M" format specifier returns the month from 1 through 12, whereas the custom "m" format specifier returns the minute from 0 through 59.</span></span>

<span data-ttu-id="9b301-116">`culture`: *Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="9b301-116">`culture`: *String*</span></span>

<span data-ttu-id="9b301-117">A cultura a ser usada para formatação.</span><span class="sxs-lookup"><span data-stu-id="9b301-117">The culture to use for formatting.</span></span>

## <a name="return-values"></a><span data-ttu-id="9b301-118">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="9b301-118">Return values</span></span>

<span data-ttu-id="9b301-119">*Sequência de caracteres*</span><span class="sxs-lookup"><span data-stu-id="9b301-119">*String*</span></span>

<span data-ttu-id="9b301-120">O valor da cadeia de caracteres resultante.</span><span class="sxs-lookup"><span data-stu-id="9b301-120">The resulting string value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="9b301-121">Notas de uso</span><span class="sxs-lookup"><span data-stu-id="9b301-121">Usage notes</span></span>

<span data-ttu-id="9b301-122">Se a cultura não é definida como um argumento da função chamada, o valor de `culture` é definido pelo contexto de chamada.</span><span class="sxs-lookup"><span data-stu-id="9b301-122">If the culture isn't defined as an argument of the called function, the value of `culture` is defined by the calling context.</span></span> <span data-ttu-id="9b301-123">Por exemplo, se a função `DATEFORMAT` for chamada usando a sintaxe 1 em um formato de relatório eletrônico (ER) para um elemento **FILE** de arquivo configurado para usar a cultura alemã, a conversão será feita usando a cultura alemã.</span><span class="sxs-lookup"><span data-stu-id="9b301-123">For example, if the `DATEFORMAT` function is called by using syntax 1 in an Electronic reporting (ER) format for a **FILE** element that is configured to use the German culture, the conversion will be done by using the German culture.</span></span> <span data-ttu-id="9b301-124">O valor padrão `culture` é **EN-US**.</span><span class="sxs-lookup"><span data-stu-id="9b301-124">The default `culture` value is **EN-US**.</span></span>

## <a name="example-1"></a><span data-ttu-id="9b301-125">Exemplo 1</span><span class="sxs-lookup"><span data-stu-id="9b301-125">Example 1</span></span>

<span data-ttu-id="9b301-126">`DATEFORMAT (TODAY (), "dd-MM-yyyy")` retorna a data atual do servidor do aplicativo, 24 de dezembro de 2015, como a cadeia de caracteres **"24-12-2015"**, com base no formato personalizado especificado.</span><span class="sxs-lookup"><span data-stu-id="9b301-126">`DATEFORMAT (TODAY (), "dd-MM-yyyy")` returns the current application server date, December 24, 2015, as the string **"24-12-2015"**, based on the specified custom format.</span></span>

## <a name="example-2"></a><span data-ttu-id="9b301-127">Exemplo 2</span><span class="sxs-lookup"><span data-stu-id="9b301-127">Example 2</span></span>

<span data-ttu-id="9b301-128">`DATEFORMAT (SESSIONTODAY (), "d", "DE")` retorna a data atual da sessão do aplicativo, 24 de dezembro de 2015, como a cadeia de caracteres **"24-12-2015"**, com base na cultura alemã selecionada e no formato especificado.</span><span class="sxs-lookup"><span data-stu-id="9b301-128">`DATEFORMAT (SESSIONTODAY (), "d", "DE")` returns the current application session date, December 24, 2015, as the string **"24-12-2015"**, based on the selected German culture and the specified format.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="9b301-129">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="9b301-129">Additional resources</span></span>

[<span data-ttu-id="9b301-130">Funções de data e de hora</span><span class="sxs-lookup"><span data-stu-id="9b301-130">Date and time functions</span></span>](er-functions-category-datetime.md)
