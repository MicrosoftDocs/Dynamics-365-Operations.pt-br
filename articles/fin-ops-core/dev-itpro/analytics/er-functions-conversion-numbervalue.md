---
title: Função NUMBERVALUE ER
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) NUMBERVALUE é usada.
author: NickSelin
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
ms.openlocfilehash: 84d7f17f37a83547522cf09047b72100f6f5b859
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5755339"
---
# <a name="numbervalue-er-function"></a><span data-ttu-id="1c8eb-103">Função NUMBERVALUE ER</span><span class="sxs-lookup"><span data-stu-id="1c8eb-103">NUMBERVALUE ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="1c8eb-104">A função `NUMBERVALUE` retorna um valor *Real* que é convertido do valor de *Cadeia de caracteres* especificado.</span><span class="sxs-lookup"><span data-stu-id="1c8eb-104">The `NUMBERVALUE` function returns a *Real* value that is converted from the specified *String* value.</span></span> <span data-ttu-id="1c8eb-105">Durante a conversão, os separadores de agrupamento de dígitos e decimais especificados são considerados.</span><span class="sxs-lookup"><span data-stu-id="1c8eb-105">During the conversion, the specified decimal and digit grouping separators are considered.</span></span>

## <a name="syntax"></a><span data-ttu-id="1c8eb-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="1c8eb-106">Syntax</span></span>

```vb
NUMBERVALUE (text, decimal separator, digit grouping separator)
```

## <a name="arguments"></a><span data-ttu-id="1c8eb-107">Argumentos</span><span class="sxs-lookup"><span data-stu-id="1c8eb-107">Arguments</span></span>

<span data-ttu-id="1c8eb-108">`text`: *Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="1c8eb-108">`text`: *String*</span></span>

<span data-ttu-id="1c8eb-109">Um valor de texto que deve ser convertido para um número *Real*.</span><span class="sxs-lookup"><span data-stu-id="1c8eb-109">A text value that must be converted to a *Real* number.</span></span>

<span data-ttu-id="1c8eb-110">`decimal separator`: Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="1c8eb-110">`decimal separator`: String</span></span>

<span data-ttu-id="1c8eb-111">Um separador decimal.</span><span class="sxs-lookup"><span data-stu-id="1c8eb-111">A decimal separator.</span></span> <span data-ttu-id="1c8eb-112">Ele é usado para separar as partes inteira e fracionária de um número decimal.</span><span class="sxs-lookup"><span data-stu-id="1c8eb-112">It's used to separate the integer and fractional parts of a decimal number.</span></span>

<span data-ttu-id="1c8eb-113">`digit grouping separator`: *Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="1c8eb-113">`digit grouping separator`: *String*</span></span>

<span data-ttu-id="1c8eb-114">Um separador de agrupamento de dígitos.</span><span class="sxs-lookup"><span data-stu-id="1c8eb-114">A digit grouping separator.</span></span> <span data-ttu-id="1c8eb-115">É usado como separador de milhar.</span><span class="sxs-lookup"><span data-stu-id="1c8eb-115">It's used as the thousands separator.</span></span>

## <a name="return-values"></a><span data-ttu-id="1c8eb-116">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="1c8eb-116">Return values</span></span>

<span data-ttu-id="1c8eb-117">*Real*</span><span class="sxs-lookup"><span data-stu-id="1c8eb-117">*Real*</span></span>

<span data-ttu-id="1c8eb-118">O valor numérico resultante.</span><span class="sxs-lookup"><span data-stu-id="1c8eb-118">The resulting numeric value.</span></span>

## <a name="example"></a><span data-ttu-id="1c8eb-119">Exemplo</span><span class="sxs-lookup"><span data-stu-id="1c8eb-119">Example</span></span>

<span data-ttu-id="1c8eb-120">`NUMBERVALUE( "1 234,56", ",", " ")` retorna **1234.56**.</span><span class="sxs-lookup"><span data-stu-id="1c8eb-120">`NUMBERVALUE( "1 234,56", ",", " ")` returns **1234.56**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="1c8eb-121">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="1c8eb-121">Additional resources</span></span>

[<span data-ttu-id="1c8eb-122">Funções de conversão de tipo</span><span class="sxs-lookup"><span data-stu-id="1c8eb-122">Type conversion functions</span></span>](er-functions-category-type-conversion.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]