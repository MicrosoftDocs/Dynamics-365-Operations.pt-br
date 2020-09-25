---
title: Função DATEFORMAT ER
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) DATEFORMAT é usada.
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
ms.search.scope: Core, Operations
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4e9347937d088f15b4f489f0b85704a8688f8131
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/01/2020
ms.locfileid: "3743294"
---
# <a name="dateformat-er-function"></a><span data-ttu-id="cd42f-103">Função DATEFORMAT ER</span><span class="sxs-lookup"><span data-stu-id="cd42f-103">DATEFORMAT ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="cd42f-104">A função `DATEFORMAT` retorna um valor de *Cadeia de caracteres* que apresenta um valor de data determinado como texto no formato especificado e em uma [cultura](https://docs.microsoft.com/bingmaps/rest-services/common-parameters-and-types/supported-culture-codes) opcionalmente especificada.</span><span class="sxs-lookup"><span data-stu-id="cd42f-104">The `DATEFORMAT` function returns a *String* value that presents a given date value as text in the specified format and in an optionally specified [culture](https://docs.microsoft.com/bingmaps/rest-services/common-parameters-and-types/supported-culture-codes).</span></span> <span data-ttu-id="cd42f-105">Para obter informações sobre os formatos com suporte, consulte [padrão](https://msdn.microsoft.com/library/az4se3k1(v=vs.110).aspx) e [personalizado](https://msdn.microsoft.com/library/8kb3ddd4(v=vs.110).aspx).</span><span class="sxs-lookup"><span data-stu-id="cd42f-105">For information about the supported formats, see [standard](https://msdn.microsoft.com/library/az4se3k1(v=vs.110).aspx) and [custom](https://msdn.microsoft.com/library/8kb3ddd4(v=vs.110).aspx).</span></span>

## <a name="syntax-1"></a><span data-ttu-id="cd42f-106">Sintaxe 1</span><span class="sxs-lookup"><span data-stu-id="cd42f-106">Syntax 1</span></span>

```vb
DATEFORMAT (date, format)
```

## <a name="syntax-2"></a><span data-ttu-id="cd42f-107">Sintaxe 2</span><span class="sxs-lookup"><span data-stu-id="cd42f-107">Syntax 2</span></span>

```vb
DATEFORMAT (date, format, culture)
```

## <a name="arguments"></a><span data-ttu-id="cd42f-108">Argumentos</span><span class="sxs-lookup"><span data-stu-id="cd42f-108">Arguments</span></span>

<span data-ttu-id="cd42f-109">`date`: *Data*</span><span class="sxs-lookup"><span data-stu-id="cd42f-109">`date`: *Date*</span></span>

<span data-ttu-id="cd42f-110">Um valor de data que representa a data do formato.</span><span class="sxs-lookup"><span data-stu-id="cd42f-110">A date value that represents the date to format.</span></span>

<span data-ttu-id="cd42f-111">`format`: *Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="cd42f-111">`format`: *String*</span></span>

<span data-ttu-id="cd42f-112">O formato da cadeia de caracteres de saída.</span><span class="sxs-lookup"><span data-stu-id="cd42f-112">The format of the output string.</span></span>

<span data-ttu-id="cd42f-113">`culture`: *Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="cd42f-113">`culture`: *String*</span></span>

<span data-ttu-id="cd42f-114">A cultura a ser usada para formatação.</span><span class="sxs-lookup"><span data-stu-id="cd42f-114">The culture to use for formatting.</span></span>

## <a name="return-values"></a><span data-ttu-id="cd42f-115">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="cd42f-115">Return values</span></span>

<span data-ttu-id="cd42f-116">*Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="cd42f-116">*String*</span></span>

<span data-ttu-id="cd42f-117">O valor da cadeia de caracteres resultante.</span><span class="sxs-lookup"><span data-stu-id="cd42f-117">The resulting string value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="cd42f-118">Notas de uso</span><span class="sxs-lookup"><span data-stu-id="cd42f-118">Usage notes</span></span>

<span data-ttu-id="cd42f-119">Quando a cultura não é definida como um argumento da função chamada, o valor de `culture` é definido pelo contexto de chamada.</span><span class="sxs-lookup"><span data-stu-id="cd42f-119">When the culture isn't defined as an argument of the called function, the value of `culture` is defined by the calling context.</span></span> <span data-ttu-id="cd42f-120">Por exemplo, se a função `DATEFORMAT` for chamada usando a sintaxe 1 em um formato de relatório eletrônico (ER) para um elemento **FILE** de arquivo configurado para usar a cultura alemã, a conversão será feita usando a cultura alemã.</span><span class="sxs-lookup"><span data-stu-id="cd42f-120">For example, if the `DATEFORMAT` function is called by using syntax 1 in an Electronic reporting (ER) format for a **FILE** element that is configured to use the German culture, the conversion will be done by using the German culture.</span></span> <span data-ttu-id="cd42f-121">O valor padrão `culture` é **EN-US**.</span><span class="sxs-lookup"><span data-stu-id="cd42f-121">The default `culture` value is **EN-US**.</span></span>

## <a name="example-1"></a><span data-ttu-id="cd42f-122">Exemplo 1</span><span class="sxs-lookup"><span data-stu-id="cd42f-122">Example 1</span></span>

<span data-ttu-id="cd42f-123">`DATEFORMAT (TODAY (), "dd-MM-yyyy")` retorna a data atual do servidor do aplicativo, 24 de dezembro de 2015, como a cadeia de caracteres **"24-12-2015"**, com base no formato personalizado especificado.</span><span class="sxs-lookup"><span data-stu-id="cd42f-123">`DATEFORMAT (TODAY (), "dd-MM-yyyy")` returns the current application server date, December 24, 2015, as the string **"24-12-2015"**, based on the specified custom format.</span></span>

## <a name="example-2"></a><span data-ttu-id="cd42f-124">Exemplo 2</span><span class="sxs-lookup"><span data-stu-id="cd42f-124">Example 2</span></span>

<span data-ttu-id="cd42f-125">`DATEFORMAT (SESSIONTODAY (), "d", "DE")` retorna a data atual da sessão do aplicativo, 24 de dezembro de 2015, como a cadeia de caracteres **"24-12-2015"**, com base na cultura alemã selecionada e no formato especificado.</span><span class="sxs-lookup"><span data-stu-id="cd42f-125">`DATEFORMAT (SESSIONTODAY (), "d", "DE")` returns the current application session date, December 24, 2015, as the string  **"24-12-2015"**, based on the selected German culture and the specified format.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="cd42f-126">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="cd42f-126">Additional resources</span></span>

[<span data-ttu-id="cd42f-127">Funções de data e de hora</span><span class="sxs-lookup"><span data-stu-id="cd42f-127">Date and time functions</span></span>](er-functions-category-datetime.md)
