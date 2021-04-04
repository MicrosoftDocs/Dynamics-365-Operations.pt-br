---
title: Função DATETIMEVALUE ER
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) DATETIMEVALUE é usada.
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
ms.openlocfilehash: a4887db488b4cf137824ed34dedcd5d1773b7c99
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/09/2021
ms.locfileid: "5563597"
---
# <a name="datetimevalue-er-function"></a><span data-ttu-id="4b2f5-103">Função DATETIMEVALUE ER</span><span class="sxs-lookup"><span data-stu-id="4b2f5-103">DATETIMEVALUE ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="4b2f5-104">A função `DATETIMEVALUE` retorna um valor de *DateTime* que é convertido de um valor de texto determinado no formato especificado e em uma [cultura](https://docs.microsoft.com/bingmaps/rest-services/common-parameters-and-types/supported-culture-codes) opcionalmente especificada para um valor de data/hora.</span><span class="sxs-lookup"><span data-stu-id="4b2f5-104">The `DATETIMEVALUE` function returns a *DateTime* value that is converted from a given text value in the specified format and in an optionally specified [culture](https://docs.microsoft.com/bingmaps/rest-services/common-parameters-and-types/supported-culture-codes) to a date/time value.</span></span> <span data-ttu-id="4b2f5-105">Para obter informações sobre os formatos com suporte, consulte [padrão](https://msdn.microsoft.com/library/az4se3k1(v=vs.110).aspx) e [personalizado](https://msdn.microsoft.com/library/8kb3ddd4(v=vs.110).aspx).</span><span class="sxs-lookup"><span data-stu-id="4b2f5-105">For information about the supported formats, see [standard](https://msdn.microsoft.com/library/az4se3k1(v=vs.110).aspx) and [custom](https://msdn.microsoft.com/library/8kb3ddd4(v=vs.110).aspx).</span></span>

## <a name="syntax-1"></a><span data-ttu-id="4b2f5-106">Sintaxe 1</span><span class="sxs-lookup"><span data-stu-id="4b2f5-106">Syntax 1</span></span>

```vb
DATETIMEVALUE (text, format)
```

## <a name="syntax-2"></a><span data-ttu-id="4b2f5-107">Sintaxe 2</span><span class="sxs-lookup"><span data-stu-id="4b2f5-107">Syntax 2</span></span>

```vb
DATETIMEVALUE (text, format, culture)
```

## <a name="arguments"></a><span data-ttu-id="4b2f5-108">Argumentos</span><span class="sxs-lookup"><span data-stu-id="4b2f5-108">Arguments</span></span>

<span data-ttu-id="4b2f5-109">`text`: *Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="4b2f5-109">`text`: *String*</span></span>

<span data-ttu-id="4b2f5-110">Texto que representa o valor do formato.</span><span class="sxs-lookup"><span data-stu-id="4b2f5-110">Text that represents the value to format.</span></span>

<span data-ttu-id="4b2f5-111">`format`: *Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="4b2f5-111">`format`: *String*</span></span>

<span data-ttu-id="4b2f5-112">O formato de determinado texto.</span><span class="sxs-lookup"><span data-stu-id="4b2f5-112">The format of the given text.</span></span>

<span data-ttu-id="4b2f5-113">`culture`: *Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="4b2f5-113">`culture`: *String*</span></span>

<span data-ttu-id="4b2f5-114">A cultura usada para a formatação do texto especificado.</span><span class="sxs-lookup"><span data-stu-id="4b2f5-114">The culture that is used for formatting of the given text.</span></span>

## <a name="return-values"></a><span data-ttu-id="4b2f5-115">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="4b2f5-115">Return values</span></span>

<span data-ttu-id="4b2f5-116">*Data/Hora*</span><span class="sxs-lookup"><span data-stu-id="4b2f5-116">*DateTime*</span></span>

<span data-ttu-id="4b2f5-117">O valor de data/hora resultante.</span><span class="sxs-lookup"><span data-stu-id="4b2f5-117">The resulting date/time value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="4b2f5-118">Notas de uso</span><span class="sxs-lookup"><span data-stu-id="4b2f5-118">Usage notes</span></span>

<span data-ttu-id="4b2f5-119">Quando a cultura não é definida como um argumento da função chamada, o valor de `culture` é definido pelo contexto de chamada.</span><span class="sxs-lookup"><span data-stu-id="4b2f5-119">When the culture isn't defined as an argument of the called function, the value of `culture` is defined by the calling context.</span></span> <span data-ttu-id="4b2f5-120">Por exemplo, se a função `DATETIMEVALUE` for chamada usando a sintaxe 1 em um formato de relatório eletrônico (ER) para um elemento **FILE** de arquivo configurado para usar a cultura alemã, a conversão será feita usando a cultura alemã.</span><span class="sxs-lookup"><span data-stu-id="4b2f5-120">For example, if the `DATETIMEVALUE` function is called by using syntax 1 in an Electronic reporting (ER) format for a **FILE** element that is configured to use the German culture, the conversion will be done by using the German culture.</span></span> <span data-ttu-id="4b2f5-121">O valor padrão `culture` é **EN-US**.</span><span class="sxs-lookup"><span data-stu-id="4b2f5-121">The default `culture` value is **EN-US**.</span></span>

## <a name="example-1"></a><span data-ttu-id="4b2f5-122">Exemplo 1</span><span class="sxs-lookup"><span data-stu-id="4b2f5-122">Example 1</span></span>

<span data-ttu-id="4b2f5-123">`DATETIMEVALUE ("21-Dec-2016 02:55:00", "dd-MMM-yyyy hh:mm:ss")` retorna o valor de data **2:55:00 AM em 21 de dezembro de 2016** com base no formato personalizado especificado e na cultura padrão **EN-US** do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="4b2f5-123">`DATETIMEVALUE ("21-Dec-2016 02:55:00", "dd-MMM-yyyy hh:mm:ss")` returns **2:55:00 AM on December 21, 2016**, based on the specified custom format and the default application's **EN-US** culture.</span></span>

## <a name="example-2"></a><span data-ttu-id="4b2f5-124">Exemplo 2</span><span class="sxs-lookup"><span data-stu-id="4b2f5-124">Example 2</span></span>

<span data-ttu-id="4b2f5-125">`DATETIMEVALUE ("21-Gen-2016 02:55:00", "dd-MMM-yyyy hh:mm:ss", "IT")` retorna **2:55:00 AM em 21 de dezembro de 2016**, com base no formato e cultura personalizados especificados.</span><span class="sxs-lookup"><span data-stu-id="4b2f5-125">`DATETIMEVALUE ("21-Gen-2016 02:55:00", "dd-MMM-yyyy hh:mm:ss", "IT")` returns **2:55:00 AM on December 21, 2016**, based on the specified custom format and culture.</span></span>

<span data-ttu-id="4b2f5-126">Porém, `DATETIMEVALUE ("21-Gen-2016 02:55:00", "dd-MMM-yyyy hh:mm:ss", "EN-US")` gerará uma exceção para informar ao usuário que a sequência de caracteres especificada não é reconhecida como um valor de data/tempo válido da cultura especificada.</span><span class="sxs-lookup"><span data-stu-id="4b2f5-126">However, `DATETIMEVALUE ("21-Gen-2016 02:55:00", "dd-MMM-yyyy hh:mm:ss", "EN-US")` throws an exception to inform the user that the specified string isn't recognized as a valid date/time value for the specified culture.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="4b2f5-127">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="4b2f5-127">Additional resources</span></span>

[<span data-ttu-id="4b2f5-128">Funções de data e de hora</span><span class="sxs-lookup"><span data-stu-id="4b2f5-128">Date and time functions</span></span>](er-functions-category-datetime.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]