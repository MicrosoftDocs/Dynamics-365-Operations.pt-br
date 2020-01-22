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
ms.openlocfilehash: c1453be0c93764f9f0364206822a9e3899061a58
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/20/2019
ms.locfileid: "2917571"
---
# <span data-ttu-id="b8825-103"><a name="DATEFORMAT">Função DATEFORMAT ER</a></span><span class="sxs-lookup"><span data-stu-id="b8825-103"><a name="DATEFORMAT">DATEFORMAT ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b8825-104">A função `DATEFORMAT` retorna um valor de *Cadeia de caracteres* que apresenta um valor de data determinado como texto no formato especificado e em uma [cultura](https://docs.microsoft.com/bingmaps/rest-services/common-parameters-and-types/supported-culture-codes) opcionalmente especificada.</span><span class="sxs-lookup"><span data-stu-id="b8825-104">The `DATEFORMAT` function returns a *String* value that presents a given date value as text in the specified format and in an optionally specified [culture](https://docs.microsoft.com/bingmaps/rest-services/common-parameters-and-types/supported-culture-codes).</span></span> <span data-ttu-id="b8825-105">Para obter informações sobre os formatos com suporte, consulte [padrão](https://msdn.microsoft.com/library/az4se3k1(v=vs.110).aspx) e [personalizado](https://msdn.microsoft.com/library/8kb3ddd4(v=vs.110).aspx).</span><span class="sxs-lookup"><span data-stu-id="b8825-105">For information about the supported formats, see [standard](https://msdn.microsoft.com/library/az4se3k1(v=vs.110).aspx) and [custom](https://msdn.microsoft.com/library/8kb3ddd4(v=vs.110).aspx).</span></span>

## <a name="syntax-1"></a><span data-ttu-id="b8825-106">Sintaxe 1</span><span class="sxs-lookup"><span data-stu-id="b8825-106">Syntax 1</span></span>

```
DATEFORMAT (date, format)
```

## <a name="syntax-2"></a><span data-ttu-id="b8825-107">Sintaxe 2</span><span class="sxs-lookup"><span data-stu-id="b8825-107">Syntax 2</span></span>

```
DATEFORMAT (date, format, culture)
```

## <a name="arguments"></a><span data-ttu-id="b8825-108">Argumentos</span><span class="sxs-lookup"><span data-stu-id="b8825-108">Arguments</span></span>

<span data-ttu-id="b8825-109">`date`: *Data*</span><span class="sxs-lookup"><span data-stu-id="b8825-109">`date`: *Date*</span></span>

<span data-ttu-id="b8825-110">Um valor de data que representa a data do formato.</span><span class="sxs-lookup"><span data-stu-id="b8825-110">A date value that represents the date to format.</span></span>

<span data-ttu-id="b8825-111">`format`: *Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="b8825-111">`format`: *String*</span></span>

<span data-ttu-id="b8825-112">O formato da cadeia de caracteres de saída.</span><span class="sxs-lookup"><span data-stu-id="b8825-112">The format of the output string.</span></span>

<span data-ttu-id="b8825-113">`culture`: *Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="b8825-113">`culture`: *String*</span></span>

<span data-ttu-id="b8825-114">A cultura a ser usada para formatação.</span><span class="sxs-lookup"><span data-stu-id="b8825-114">The culture to use for formatting.</span></span>

## <a name="return-values"></a><span data-ttu-id="b8825-115">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="b8825-115">Return values</span></span>

<span data-ttu-id="b8825-116">*Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="b8825-116">*String*</span></span>

<span data-ttu-id="b8825-117">O valor da cadeia de caracteres resultante.</span><span class="sxs-lookup"><span data-stu-id="b8825-117">The resulting string value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="b8825-118">Notas de uso</span><span class="sxs-lookup"><span data-stu-id="b8825-118">Usage notes</span></span>

<span data-ttu-id="b8825-119">Quando a cultura não é definida como um argumento da função chamada, o valor de `culture` é definido pelo contexto de chamada.</span><span class="sxs-lookup"><span data-stu-id="b8825-119">When the culture isn't defined as an argument of the called function, the value of `culture` is defined by the calling context.</span></span> <span data-ttu-id="b8825-120">Por exemplo, se a função `DATEFORMAT` for chamada usando a sintaxe 1 em um formato de relatório eletrônico (ER) para um elemento **FILE** de arquivo configurado para usar a cultura alemã, a conversão será feita usando a cultura alemã.</span><span class="sxs-lookup"><span data-stu-id="b8825-120">For example, if the `DATEFORMAT` function is called by using syntax 1 in an Electronic reporting (ER) format for a **FILE** element that is configured to use the German culture, the conversion will be done by using the German culture.</span></span> <span data-ttu-id="b8825-121">O valor padrão `culture` é **EN-US**.</span><span class="sxs-lookup"><span data-stu-id="b8825-121">The default `culture` value is **EN-US**.</span></span>

## <a name="example-1"></a><span data-ttu-id="b8825-122">Exemplo 1</span><span class="sxs-lookup"><span data-stu-id="b8825-122">Example 1</span></span>

<span data-ttu-id="b8825-123">`DATEFORMAT (TODAY (), "dd-MM-yyyy")` retorna a data atual do servidor do aplicativo, 24 de dezembro de 2015, como a cadeia de caracteres **"24-12-2015"**, com base no formato personalizado especificado.</span><span class="sxs-lookup"><span data-stu-id="b8825-123">`DATEFORMAT (TODAY (), "dd-MM-yyyy")` returns the current application server date, December 24, 2015, as the string **"24-12-2015"**, based on the specified custom format.</span></span>

## <a name="example-2"></a><span data-ttu-id="b8825-124">Exemplo 2</span><span class="sxs-lookup"><span data-stu-id="b8825-124">Example 2</span></span>

<span data-ttu-id="b8825-125">`DATEFORMAT (SESSIONTODAY (), "d", "DE")` retorna a data atual da sessão do aplicativo, 24 de dezembro de 2015, como a cadeia de caracteres **"24-12-2015"**, com base na cultura alemã selecionada e no formato especificado.</span><span class="sxs-lookup"><span data-stu-id="b8825-125">`DATEFORMAT (SESSIONTODAY (), "d", "DE")` returns the current application session date, December 24, 2015, as the string  **"24-12-2015"**, based on the selected German culture and the specified format.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="b8825-126">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="b8825-126">Additional resources</span></span>

[<span data-ttu-id="b8825-127">Funções de data e de hora</span><span class="sxs-lookup"><span data-stu-id="b8825-127">Date and time functions</span></span>](er-functions-category-datetime.md)
