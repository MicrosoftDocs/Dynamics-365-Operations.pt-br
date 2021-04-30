---
title: Função DATETIMEVALUE ER
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) DATETIMEVALUE é usada.
author: NickSelin
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
ms.openlocfilehash: db5b2c56f0c6dcc019419801821d7a6eae8a0e91
ms.sourcegitcommit: 951393b05bf409333cb3c7ad977bcaa804aa801b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/13/2021
ms.locfileid: "5891272"
---
# <a name="datetimevalue-er-function"></a><span data-ttu-id="e517b-103">Função DATETIMEVALUE ER</span><span class="sxs-lookup"><span data-stu-id="e517b-103">DATETIMEVALUE ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="e517b-104">A função `DATETIMEVALUE` retorna um valor de *DateTime* que é convertido de um valor de texto determinado no formato especificado e em uma [cultura](/bingmaps/rest-services/common-parameters-and-types/supported-culture-codes) opcionalmente especificada para um valor de data/hora.</span><span class="sxs-lookup"><span data-stu-id="e517b-104">The `DATETIMEVALUE` function returns a *DateTime* value that is converted from a given text value in the specified format and in an optionally specified [culture](/bingmaps/rest-services/common-parameters-and-types/supported-culture-codes) to a date/time value.</span></span> <span data-ttu-id="e517b-105">Para obter informações sobre os formatos com suporte, consulte [padrão](/dotnet/standard/base-types/standard-date-and-time-format-strings) e [personalizado](/dotnet/standard/base-types/custom-date-and-time-format-strings).</span><span class="sxs-lookup"><span data-stu-id="e517b-105">For information about the supported formats, see [standard](/dotnet/standard/base-types/standard-date-and-time-format-strings) and [custom](/dotnet/standard/base-types/custom-date-and-time-format-strings).</span></span>

## <a name="syntax-1"></a><span data-ttu-id="e517b-106">Sintaxe 1</span><span class="sxs-lookup"><span data-stu-id="e517b-106">Syntax 1</span></span>

```vb
DATETIMEVALUE (text, format)
```

## <a name="syntax-2"></a><span data-ttu-id="e517b-107">Sintaxe 2</span><span class="sxs-lookup"><span data-stu-id="e517b-107">Syntax 2</span></span>

```vb
DATETIMEVALUE (text, format, culture)
```

## <a name="arguments"></a><span data-ttu-id="e517b-108">Argumentos</span><span class="sxs-lookup"><span data-stu-id="e517b-108">Arguments</span></span>

<span data-ttu-id="e517b-109">`text`: *Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="e517b-109">`text`: *String*</span></span>

<span data-ttu-id="e517b-110">Texto que representa o valor do formato.</span><span class="sxs-lookup"><span data-stu-id="e517b-110">Text that represents the value to format.</span></span>

<span data-ttu-id="e517b-111">`format`: *Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="e517b-111">`format`: *String*</span></span>

<span data-ttu-id="e517b-112">O formato de determinado texto.</span><span class="sxs-lookup"><span data-stu-id="e517b-112">The format of the given text.</span></span>

<span data-ttu-id="e517b-113">`culture`: *Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="e517b-113">`culture`: *String*</span></span>

<span data-ttu-id="e517b-114">A cultura usada para a formatação do texto especificado.</span><span class="sxs-lookup"><span data-stu-id="e517b-114">The culture that is used for formatting of the given text.</span></span>

## <a name="return-values"></a><span data-ttu-id="e517b-115">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="e517b-115">Return values</span></span>

<span data-ttu-id="e517b-116">*Data/Hora*</span><span class="sxs-lookup"><span data-stu-id="e517b-116">*DateTime*</span></span>

<span data-ttu-id="e517b-117">O valor de data/hora resultante.</span><span class="sxs-lookup"><span data-stu-id="e517b-117">The resulting date/time value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="e517b-118">Notas de uso</span><span class="sxs-lookup"><span data-stu-id="e517b-118">Usage notes</span></span>

<span data-ttu-id="e517b-119">Quando a cultura não é definida como um argumento da função chamada, o valor de `culture` é definido pelo contexto de chamada.</span><span class="sxs-lookup"><span data-stu-id="e517b-119">When the culture isn't defined as an argument of the called function, the value of `culture` is defined by the calling context.</span></span> <span data-ttu-id="e517b-120">Por exemplo, se a função `DATETIMEVALUE` for chamada usando a sintaxe 1 em um formato de relatório eletrônico (ER) para um elemento **FILE** de arquivo configurado para usar a cultura alemã, a conversão será feita usando a cultura alemã.</span><span class="sxs-lookup"><span data-stu-id="e517b-120">For example, if the `DATETIMEVALUE` function is called by using syntax 1 in an Electronic reporting (ER) format for a **FILE** element that is configured to use the German culture, the conversion will be done by using the German culture.</span></span> <span data-ttu-id="e517b-121">O valor padrão `culture` é **EN-US**.</span><span class="sxs-lookup"><span data-stu-id="e517b-121">The default `culture` value is **EN-US**.</span></span>

## <a name="example-1"></a><span data-ttu-id="e517b-122">Exemplo 1</span><span class="sxs-lookup"><span data-stu-id="e517b-122">Example 1</span></span>

<span data-ttu-id="e517b-123">`DATETIMEVALUE ("21-Dec-2016 02:55:00", "dd-MMM-yyyy hh:mm:ss")` retorna o valor de data **2:55:00 AM em 21 de dezembro de 2016** com base no formato personalizado especificado e na cultura padrão **EN-US** do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="e517b-123">`DATETIMEVALUE ("21-Dec-2016 02:55:00", "dd-MMM-yyyy hh:mm:ss")` returns **2:55:00 AM on December 21, 2016**, based on the specified custom format and the default application's **EN-US** culture.</span></span>

## <a name="example-2"></a><span data-ttu-id="e517b-124">Exemplo 2</span><span class="sxs-lookup"><span data-stu-id="e517b-124">Example 2</span></span>

<span data-ttu-id="e517b-125">`DATETIMEVALUE ("21-Gen-2016 02:55:00", "dd-MMM-yyyy hh:mm:ss", "IT")` retorna **2:55:00 AM em 21 de dezembro de 2016**, com base no formato e cultura personalizados especificados.</span><span class="sxs-lookup"><span data-stu-id="e517b-125">`DATETIMEVALUE ("21-Gen-2016 02:55:00", "dd-MMM-yyyy hh:mm:ss", "IT")` returns **2:55:00 AM on December 21, 2016**, based on the specified custom format and culture.</span></span>

<span data-ttu-id="e517b-126">Porém, `DATETIMEVALUE ("21-Gen-2016 02:55:00", "dd-MMM-yyyy hh:mm:ss", "EN-US")` gerará uma exceção para informar ao usuário que a sequência de caracteres especificada não é reconhecida como um valor de data/tempo válido da cultura especificada.</span><span class="sxs-lookup"><span data-stu-id="e517b-126">However, `DATETIMEVALUE ("21-Gen-2016 02:55:00", "dd-MMM-yyyy hh:mm:ss", "EN-US")` throws an exception to inform the user that the specified string isn't recognized as a valid date/time value for the specified culture.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="e517b-127">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="e517b-127">Additional resources</span></span>

[<span data-ttu-id="e517b-128">Funções de data e de hora</span><span class="sxs-lookup"><span data-stu-id="e517b-128">Date and time functions</span></span>](er-functions-category-datetime.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]