---
title: Função NUMBERVALUE ER
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) NUMBERVALUE é usada.
author: NickSelin
manager: kfend
ms.date: 12/05/2019
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
ms.openlocfilehash: 6eeb66f4206eb39141a5b2573fcb9d15428ae52a
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/12/2020
ms.locfileid: "3042635"
---
# <span data-ttu-id="3021f-103"><a name="NUMBERVALUE">Função NUMBERVALUE ER</a></span><span class="sxs-lookup"><span data-stu-id="3021f-103"><a name="NUMBERVALUE">NUMBERVALUE ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="3021f-104">A função `NUMBERVALUE` retorna um valor *Real* que é convertido do valor de *Cadeia de caracteres* especificado.</span><span class="sxs-lookup"><span data-stu-id="3021f-104">The `NUMBERVALUE` function returns a *Real* value that is converted from the specified *String* value.</span></span> <span data-ttu-id="3021f-105">Durante a conversão, os separadores de agrupamento de dígitos e decimais especificados são considerados.</span><span class="sxs-lookup"><span data-stu-id="3021f-105">During the conversion, the specified decimal and digit grouping separators are considered.</span></span>

## <a name="syntax"></a><span data-ttu-id="3021f-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="3021f-106">Syntax</span></span>

```vb
NUMBERVALUE (text, decimal separator, digit grouping separator)
```

## <a name="arguments"></a><span data-ttu-id="3021f-107">Argumentos</span><span class="sxs-lookup"><span data-stu-id="3021f-107">Arguments</span></span>

<span data-ttu-id="3021f-108">`text`: *Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="3021f-108">`text`: *String*</span></span>

<span data-ttu-id="3021f-109">Um valor de texto que deve ser convertido para um número *Real*.</span><span class="sxs-lookup"><span data-stu-id="3021f-109">A text value that must be converted to a *Real* number.</span></span>

<span data-ttu-id="3021f-110">`decimal separator`: Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="3021f-110">`decimal separator`: String</span></span>

<span data-ttu-id="3021f-111">Um separador decimal.</span><span class="sxs-lookup"><span data-stu-id="3021f-111">A decimal separator.</span></span> <span data-ttu-id="3021f-112">Ele é usado para separar as partes inteira e fracionária de um número decimal.</span><span class="sxs-lookup"><span data-stu-id="3021f-112">It's used to separate the integer and fractional parts of a decimal number.</span></span>

<span data-ttu-id="3021f-113">`digit grouping separator`: *Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="3021f-113">`digit grouping separator`: *String*</span></span>

<span data-ttu-id="3021f-114">Um separador de agrupamento de dígitos.</span><span class="sxs-lookup"><span data-stu-id="3021f-114">A digit grouping separator.</span></span> <span data-ttu-id="3021f-115">É usado como separador de milhar.</span><span class="sxs-lookup"><span data-stu-id="3021f-115">It's used as the thousands separator.</span></span>

## <a name="return-values"></a><span data-ttu-id="3021f-116">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="3021f-116">Return values</span></span>

<span data-ttu-id="3021f-117">*Real*</span><span class="sxs-lookup"><span data-stu-id="3021f-117">*Real*</span></span>

<span data-ttu-id="3021f-118">O valor numérico resultante.</span><span class="sxs-lookup"><span data-stu-id="3021f-118">The resulting numeric value.</span></span>

## <a name="example"></a><span data-ttu-id="3021f-119">Exemplo</span><span class="sxs-lookup"><span data-stu-id="3021f-119">Example</span></span>

<span data-ttu-id="3021f-120">`NUMBERVALUE( "1 234,56", ",", " ")` retorna **1234.56**.</span><span class="sxs-lookup"><span data-stu-id="3021f-120">`NUMBERVALUE( "1 234,56", ",", " ")` returns **1234.56**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="3021f-121">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="3021f-121">Additional resources</span></span>

[<span data-ttu-id="3021f-122">Funções de conversão de tipo</span><span class="sxs-lookup"><span data-stu-id="3021f-122">Type conversion functions</span></span>](er-functions-category-type-conversion.md)
