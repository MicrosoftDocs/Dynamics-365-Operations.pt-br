---
title: Função de ER INTVALUE
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) INTVALUE é usada.
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
ms.openlocfilehash: c5c3e4c8bd918fa1154d2c111970d2f6d0e90e08
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/01/2020
ms.locfileid: "3743630"
---
# <a name="intvalue-er-function"></a><span data-ttu-id="bd739-103">Função de ER INTVALUE</span><span class="sxs-lookup"><span data-stu-id="bd739-103">INTVALUE ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="bd739-104">A função `INTVALUE` retorna um valor *Int* que representa a cadeia de caracteres especificada.</span><span class="sxs-lookup"><span data-stu-id="bd739-104">The `INTVALUE` function returns an *Int* value that represents the specified string.</span></span>

## <a name="syntax-1"></a><span data-ttu-id="bd739-105">Sintaxe 1</span><span class="sxs-lookup"><span data-stu-id="bd739-105">Syntax 1</span></span>

```vb
INTVALUE (text)
```

## <a name="syntax-2"></a><span data-ttu-id="bd739-106">Sintaxe 2</span><span class="sxs-lookup"><span data-stu-id="bd739-106">Syntax 2</span></span>

```vb
INTVALUE (number)
```

## <a name="arguments"></a><span data-ttu-id="bd739-107">Argumentos</span><span class="sxs-lookup"><span data-stu-id="bd739-107">Arguments</span></span>

<span data-ttu-id="bd739-108">`text`: *Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="bd739-108">`text`: *String*</span></span>

<span data-ttu-id="bd739-109">Um valor de texto que deve ser convertido para um número *Int*.</span><span class="sxs-lookup"><span data-stu-id="bd739-109">A text value that must be converted to an *Int* number.</span></span>

<span data-ttu-id="bd739-110">`number`: *Real* ou *Inteiro*</span><span class="sxs-lookup"><span data-stu-id="bd739-110">`number`: *Real* or *Integer*</span></span>

<span data-ttu-id="bd739-111">Um valor *Real* ou *Inteiro* numérico que deve ser convertido a um número *Int*.</span><span class="sxs-lookup"><span data-stu-id="bd739-111">A numeric *Real* or *Integer* value that must be converted to an *Int* number.</span></span>

## <a name="return-values"></a><span data-ttu-id="bd739-112">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="bd739-112">Return values</span></span>

<span data-ttu-id="bd739-113">*Int*</span><span class="sxs-lookup"><span data-stu-id="bd739-113">*Int*</span></span>

<span data-ttu-id="bd739-114">O valor numérico resultante.</span><span class="sxs-lookup"><span data-stu-id="bd739-114">The resulting numeric value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="bd739-115">Notas de uso</span><span class="sxs-lookup"><span data-stu-id="bd739-115">Usage notes</span></span>

<span data-ttu-id="bd739-116">Todas as casas decimais são truncadas.</span><span class="sxs-lookup"><span data-stu-id="bd739-116">Any decimal places are truncated.</span></span>

## <a name="example-1"></a><span data-ttu-id="bd739-117">Exemplo 1</span><span class="sxs-lookup"><span data-stu-id="bd739-117">Example 1</span></span>

<span data-ttu-id="bd739-118">`INTVALUE ("100.77")` retorna o valor *Int* **100**.</span><span class="sxs-lookup"><span data-stu-id="bd739-118">`INTVALUE ("100.77")` returns the *Int* value **100**.</span></span>

## <a name="example-2"></a><span data-ttu-id="bd739-119">Exemplo 2</span><span class="sxs-lookup"><span data-stu-id="bd739-119">Example 2</span></span>

<span data-ttu-id="bd739-120">`INTVALUE (-100.77)` retorna o valor *Int* **-100**.</span><span class="sxs-lookup"><span data-stu-id="bd739-120">`INTVALUE (-100.77)` returns the *Int* value **-100**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="bd739-121">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="bd739-121">Additional resources</span></span>

[<span data-ttu-id="bd739-122">Funções de conversão de tipo</span><span class="sxs-lookup"><span data-stu-id="bd739-122">Type conversion functions</span></span>](er-functions-category-type-conversion.md)
