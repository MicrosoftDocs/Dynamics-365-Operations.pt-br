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
ms.openlocfilehash: 5e06236bf1d158a4cf579b8b89cc0a5f7d815c38
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/12/2020
ms.locfileid: "3042634"
---
# <span data-ttu-id="0ae8e-103"><a name="INTVALUE">Função de ER INTVALUE</a></span><span class="sxs-lookup"><span data-stu-id="0ae8e-103"><a name="INTVALUE">INTVALUE ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="0ae8e-104">A função `INTVALUE` retorna um valor *Int* que representa a cadeia de caracteres especificada.</span><span class="sxs-lookup"><span data-stu-id="0ae8e-104">The `INTVALUE` function returns an *Int* value that represents the specified string.</span></span>

## <a name="syntax-1"></a><span data-ttu-id="0ae8e-105">Sintaxe 1</span><span class="sxs-lookup"><span data-stu-id="0ae8e-105">Syntax 1</span></span>

```vb
INTVALUE (text)
```

## <a name="syntax-2"></a><span data-ttu-id="0ae8e-106">Sintaxe 2</span><span class="sxs-lookup"><span data-stu-id="0ae8e-106">Syntax 2</span></span>

```vb
INTVALUE (number)
```

## <a name="arguments"></a><span data-ttu-id="0ae8e-107">Argumentos</span><span class="sxs-lookup"><span data-stu-id="0ae8e-107">Arguments</span></span>

<span data-ttu-id="0ae8e-108">`text`: *Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="0ae8e-108">`text`: *String*</span></span>

<span data-ttu-id="0ae8e-109">Um valor de texto que deve ser convertido para um número *Int*.</span><span class="sxs-lookup"><span data-stu-id="0ae8e-109">A text value that must be converted to an *Int* number.</span></span>

<span data-ttu-id="0ae8e-110">`number`: *Real* ou *Inteiro*</span><span class="sxs-lookup"><span data-stu-id="0ae8e-110">`number`: *Real* or *Integer*</span></span>

<span data-ttu-id="0ae8e-111">Um valor *Real* ou *Inteiro* numérico que deve ser convertido a um número *Int*.</span><span class="sxs-lookup"><span data-stu-id="0ae8e-111">A numeric *Real* or *Integer* value that must be converted to an *Int* number.</span></span>

## <a name="return-values"></a><span data-ttu-id="0ae8e-112">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="0ae8e-112">Return values</span></span>

<span data-ttu-id="0ae8e-113">*Int*</span><span class="sxs-lookup"><span data-stu-id="0ae8e-113">*Int*</span></span>

<span data-ttu-id="0ae8e-114">O valor numérico resultante.</span><span class="sxs-lookup"><span data-stu-id="0ae8e-114">The resulting numeric value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="0ae8e-115">Notas de uso</span><span class="sxs-lookup"><span data-stu-id="0ae8e-115">Usage notes</span></span>

<span data-ttu-id="0ae8e-116">Todas as casas decimais são truncadas.</span><span class="sxs-lookup"><span data-stu-id="0ae8e-116">Any decimal places are truncated.</span></span>

## <a name="example-1"></a><span data-ttu-id="0ae8e-117">Exemplo 1</span><span class="sxs-lookup"><span data-stu-id="0ae8e-117">Example 1</span></span>

<span data-ttu-id="0ae8e-118">`INTVALUE ("100.77")` retorna o valor *Int* **100**.</span><span class="sxs-lookup"><span data-stu-id="0ae8e-118">`INTVALUE ("100.77")` returns the *Int* value **100**.</span></span>

## <a name="example-2"></a><span data-ttu-id="0ae8e-119">Exemplo 2</span><span class="sxs-lookup"><span data-stu-id="0ae8e-119">Example 2</span></span>

<span data-ttu-id="0ae8e-120">`INTVALUE (-100.77)` retorna o valor *Int* **-100**.</span><span class="sxs-lookup"><span data-stu-id="0ae8e-120">`INTVALUE (-100.77)` returns the *Int* value **-100**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="0ae8e-121">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="0ae8e-121">Additional resources</span></span>

[<span data-ttu-id="0ae8e-122">Funções de conversão de tipo</span><span class="sxs-lookup"><span data-stu-id="0ae8e-122">Type conversion functions</span></span>](er-functions-category-type-conversion.md)
