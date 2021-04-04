---
title: Função NUMBERVALUE ER
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) NUMBERVALUE é usada.
author: NickSelin
manager: kfend
ms.date: 12/05/2019
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
ms.openlocfilehash: f542621c4bcc29e03d8c92b0c700e2c80c9846f6
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/09/2021
ms.locfileid: "5561413"
---
# <a name="numbervalue-er-function"></a><span data-ttu-id="0fcc8-103">Função NUMBERVALUE ER</span><span class="sxs-lookup"><span data-stu-id="0fcc8-103">NUMBERVALUE ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="0fcc8-104">A função `NUMBERVALUE` retorna um valor *Real* que é convertido do valor de *Cadeia de caracteres* especificado.</span><span class="sxs-lookup"><span data-stu-id="0fcc8-104">The `NUMBERVALUE` function returns a *Real* value that is converted from the specified *String* value.</span></span> <span data-ttu-id="0fcc8-105">Durante a conversão, os separadores de agrupamento de dígitos e decimais especificados são considerados.</span><span class="sxs-lookup"><span data-stu-id="0fcc8-105">During the conversion, the specified decimal and digit grouping separators are considered.</span></span>

## <a name="syntax"></a><span data-ttu-id="0fcc8-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="0fcc8-106">Syntax</span></span>

```vb
NUMBERVALUE (text, decimal separator, digit grouping separator)
```

## <a name="arguments"></a><span data-ttu-id="0fcc8-107">Argumentos</span><span class="sxs-lookup"><span data-stu-id="0fcc8-107">Arguments</span></span>

<span data-ttu-id="0fcc8-108">`text`: *Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="0fcc8-108">`text`: *String*</span></span>

<span data-ttu-id="0fcc8-109">Um valor de texto que deve ser convertido para um número *Real*.</span><span class="sxs-lookup"><span data-stu-id="0fcc8-109">A text value that must be converted to a *Real* number.</span></span>

<span data-ttu-id="0fcc8-110">`decimal separator`: Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="0fcc8-110">`decimal separator`: String</span></span>

<span data-ttu-id="0fcc8-111">Um separador decimal.</span><span class="sxs-lookup"><span data-stu-id="0fcc8-111">A decimal separator.</span></span> <span data-ttu-id="0fcc8-112">Ele é usado para separar as partes inteira e fracionária de um número decimal.</span><span class="sxs-lookup"><span data-stu-id="0fcc8-112">It's used to separate the integer and fractional parts of a decimal number.</span></span>

<span data-ttu-id="0fcc8-113">`digit grouping separator`: *Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="0fcc8-113">`digit grouping separator`: *String*</span></span>

<span data-ttu-id="0fcc8-114">Um separador de agrupamento de dígitos.</span><span class="sxs-lookup"><span data-stu-id="0fcc8-114">A digit grouping separator.</span></span> <span data-ttu-id="0fcc8-115">É usado como separador de milhar.</span><span class="sxs-lookup"><span data-stu-id="0fcc8-115">It's used as the thousands separator.</span></span>

## <a name="return-values"></a><span data-ttu-id="0fcc8-116">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="0fcc8-116">Return values</span></span>

<span data-ttu-id="0fcc8-117">*Real*</span><span class="sxs-lookup"><span data-stu-id="0fcc8-117">*Real*</span></span>

<span data-ttu-id="0fcc8-118">O valor numérico resultante.</span><span class="sxs-lookup"><span data-stu-id="0fcc8-118">The resulting numeric value.</span></span>

## <a name="example"></a><span data-ttu-id="0fcc8-119">Exemplo</span><span class="sxs-lookup"><span data-stu-id="0fcc8-119">Example</span></span>

<span data-ttu-id="0fcc8-120">`NUMBERVALUE( "1 234,56", ",", " ")` retorna **1234.56**.</span><span class="sxs-lookup"><span data-stu-id="0fcc8-120">`NUMBERVALUE( "1 234,56", ",", " ")` returns **1234.56**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="0fcc8-121">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="0fcc8-121">Additional resources</span></span>

[<span data-ttu-id="0fcc8-122">Funções de conversão de tipo</span><span class="sxs-lookup"><span data-stu-id="0fcc8-122">Type conversion functions</span></span>](er-functions-category-type-conversion.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]