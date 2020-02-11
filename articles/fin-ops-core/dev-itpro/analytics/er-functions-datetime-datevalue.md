---
title: Função DATEVALUE ER
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) DATEVALUE é usada.
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
ms.openlocfilehash: 700a48d2c5a77398267e6daaaea3ecb6c95e7f6e
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/20/2019
ms.locfileid: "2916352"
---
# <span data-ttu-id="f8701-103"><a name="DATEVALUE">Função DATEVALUE ER</a></span><span class="sxs-lookup"><span data-stu-id="f8701-103"><a name="DATEVALUE">DATEVALUE ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="f8701-104">A função `DATEVALUE` retorna um valor de *Data* que é convertido de um valor de texto determinado no formato especificado e em uma [cultura](https://docs.microsoft.com/bingmaps/rest-services/common-parameters-and-types/supported-culture-codes) opcionalmente especificada para um valor de data.</span><span class="sxs-lookup"><span data-stu-id="f8701-104">The `DATEVALUE` function returns a *Date* value that is converted from a given text value in the specified format and in an optionally specified [culture](https://docs.microsoft.com/bingmaps/rest-services/common-parameters-and-types/supported-culture-codes) to a date value.</span></span> <span data-ttu-id="f8701-105">Para obter informações sobre os formatos com suporte, consulte [padrão](https://msdn.microsoft.com/library/az4se3k1(v=vs.110).aspx) e [personalizado](https://msdn.microsoft.com/library/8kb3ddd4(v=vs.110).aspx).</span><span class="sxs-lookup"><span data-stu-id="f8701-105">For information about the supported formats, see [standard](https://msdn.microsoft.com/library/az4se3k1(v=vs.110).aspx) and [custom](https://msdn.microsoft.com/library/8kb3ddd4(v=vs.110).aspx).</span></span>

## <a name="syntax-1"></a><span data-ttu-id="f8701-106">Sintaxe 1</span><span class="sxs-lookup"><span data-stu-id="f8701-106">Syntax 1</span></span>

```
DATEVALUE (text, format)
```

## <a name="syntax-2"></a><span data-ttu-id="f8701-107">Sintaxe 2</span><span class="sxs-lookup"><span data-stu-id="f8701-107">Syntax 2</span></span>

```
DATEVALUE (text, format, culture)
```

## <a name="arguments"></a><span data-ttu-id="f8701-108">Argumentos</span><span class="sxs-lookup"><span data-stu-id="f8701-108">Arguments</span></span>

<span data-ttu-id="f8701-109">`text`: *Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="f8701-109">`text`: *String*</span></span>

<span data-ttu-id="f8701-110">Texto que representa o valor do formato.</span><span class="sxs-lookup"><span data-stu-id="f8701-110">Text that represents the value to format.</span></span>

<span data-ttu-id="f8701-111">`format`: *Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="f8701-111">`format`: *String*</span></span>

<span data-ttu-id="f8701-112">O formato de determinado texto.</span><span class="sxs-lookup"><span data-stu-id="f8701-112">The format of the given text.</span></span>

<span data-ttu-id="f8701-113">`culture`: *Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="f8701-113">`culture`: *String*</span></span>

<span data-ttu-id="f8701-114">A cultura usada para a formatação do texto especificado.</span><span class="sxs-lookup"><span data-stu-id="f8701-114">The culture that is used for formatting of the given text.</span></span>

## <a name="return-values"></a><span data-ttu-id="f8701-115">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="f8701-115">Return values</span></span>

<span data-ttu-id="f8701-116">*Data*</span><span class="sxs-lookup"><span data-stu-id="f8701-116">*Date*</span></span>

<span data-ttu-id="f8701-117">O valor de data resultante.</span><span class="sxs-lookup"><span data-stu-id="f8701-117">The resulting date value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="f8701-118">Notas de uso</span><span class="sxs-lookup"><span data-stu-id="f8701-118">Usage notes</span></span>

<span data-ttu-id="f8701-119">Quando a cultura não é definida como um argumento da função chamada, o valor de `culture` é definido pelo contexto de chamada.</span><span class="sxs-lookup"><span data-stu-id="f8701-119">When the culture isn't defined as an argument of the called function, the value of `culture` is defined by the calling context.</span></span> <span data-ttu-id="f8701-120">Por exemplo, se a função `DATEVALUE` for chamada usando a sintaxe 1 em um formato de relatório eletrônico (ER) para um elemento **FILE** de arquivo configurado para usar a cultura alemã, a conversão será feita usando a cultura alemã.</span><span class="sxs-lookup"><span data-stu-id="f8701-120">For example, if the `DATEVALUE` function is called by using syntax 1 in an Electronic reporting (ER) format for a **FILE** element that is configured to use the German culture, the conversion will be done by using the German culture.</span></span> <span data-ttu-id="f8701-121">O valor padrão `culture` é **EN-US**.</span><span class="sxs-lookup"><span data-stu-id="f8701-121">The default `culture` value is **EN-US**.</span></span>

## <a name="example-1"></a><span data-ttu-id="f8701-122">Exemplo 1</span><span class="sxs-lookup"><span data-stu-id="f8701-122">Example 1</span></span>

<span data-ttu-id="f8701-123">`DATEVALUE ("21-Dec-2016", "dd-MMM-yyyy")` retorna o valor de data **21 de dezembro de 2016** com base no formato personalizado especificado e na cultura padrão **EN-US** do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="f8701-123">`DATEVALUE ("21-Dec-2016", "dd-MMM-yyyy")` returns the date value **December 21, 2016**, based on the specified custom format and the default application's **EN-US** culture.</span></span>

## <a name="example-2"></a><span data-ttu-id="f8701-124">Exemplo 2</span><span class="sxs-lookup"><span data-stu-id="f8701-124">Example 2</span></span>

<span data-ttu-id="f8701-125">`DATEVALUE ("21-Gen-2016", "dd-MMM-yyyy", "IT")` retorna o valor de data **21 de janeiro de 2016**, com base no formato e cultura personalizados especificados.</span><span class="sxs-lookup"><span data-stu-id="f8701-125">`DATEVALUE ("21-Gen-2016", "dd-MMM-yyyy", "IT")` returns the date value **January 21, 2016**, based on the specified custom format and culture.</span></span>

<span data-ttu-id="f8701-126">Porém, `DATEVALUE ("21-Gen-2016", "dd-MMM-yyyy", "EN-US")` gerará uma exceção para informar ao usuário que a sequência de caracteres especificada não é reconhecida como uma data válida da cultura especificada.</span><span class="sxs-lookup"><span data-stu-id="f8701-126">However, `DATEVALUE ("21-Gen-2016", "dd-MMM-yyyy", "EN-US")` throws an exception to inform the user that the specified string isn't recognized as a valid date for the specified culture.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="f8701-127">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="f8701-127">Additional resources</span></span>

[<span data-ttu-id="f8701-128">Funções de data e de hora</span><span class="sxs-lookup"><span data-stu-id="f8701-128">Date and time functions</span></span>](er-functions-category-datetime.md)