---
title: Função de ER INT64VALUE
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) INT64VALUE é usada.
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
ms.openlocfilehash: 7fcb8a617507801d82d16175e9e86c9193091a12
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/12/2020
ms.locfileid: "3042679"
---
# <span data-ttu-id="53c48-103"><a name="INT64VALUE">Função de ER INT64VALUE</a></span><span class="sxs-lookup"><span data-stu-id="53c48-103"><a name="INT64VALUE">INT64VALUE ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="53c48-104">A função `INT64VALUE` retorna um valor *Int64* que representa a cadeia de caracteres especificada.</span><span class="sxs-lookup"><span data-stu-id="53c48-104">The `INT64VALUE` function returns an *Int64* value that represents the specified string.</span></span>

## <a name="syntax-1"></a><span data-ttu-id="53c48-105">Sintaxe 1</span><span class="sxs-lookup"><span data-stu-id="53c48-105">Syntax 1</span></span>

```vb
INT64VALUE (text)
```

## <a name="syntax-2"></a><span data-ttu-id="53c48-106">Sintaxe 2</span><span class="sxs-lookup"><span data-stu-id="53c48-106">Syntax 2</span></span>

```vb
INT64VALUE (number)
```

## <a name="arguments"></a><span data-ttu-id="53c48-107">Argumentos</span><span class="sxs-lookup"><span data-stu-id="53c48-107">Arguments</span></span>

<span data-ttu-id="53c48-108">`text`: *Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="53c48-108">`text`: *String*</span></span>

<span data-ttu-id="53c48-109">Um valor de texto que deve ser convertido para um número *Int64*.</span><span class="sxs-lookup"><span data-stu-id="53c48-109">A text value that must be converted to an *Int64* number.</span></span>

<span data-ttu-id="53c48-110">`number`: *Real* ou *Inteiro*</span><span class="sxs-lookup"><span data-stu-id="53c48-110">`number`: *Real* or *Integer*</span></span>

<span data-ttu-id="53c48-111">Um valor *Real* ou *Inteiro* numérico que deve ser convertido a um número *Int64*.</span><span class="sxs-lookup"><span data-stu-id="53c48-111">A numeric *Real* or *Integer* value that must be converted to an *Int64* number.</span></span>

## <a name="return-values"></a><span data-ttu-id="53c48-112">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="53c48-112">Return values</span></span>

<span data-ttu-id="53c48-113">*Int64*</span><span class="sxs-lookup"><span data-stu-id="53c48-113">*Int64*</span></span>

<span data-ttu-id="53c48-114">O valor numérico resultante.</span><span class="sxs-lookup"><span data-stu-id="53c48-114">The resulting numeric value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="53c48-115">Notas de uso</span><span class="sxs-lookup"><span data-stu-id="53c48-115">Usage notes</span></span>

<span data-ttu-id="53c48-116">Todas as casas decimais são truncadas.</span><span class="sxs-lookup"><span data-stu-id="53c48-116">Any decimal places are truncated.</span></span>

## <a name="example-1"></a><span data-ttu-id="53c48-117">Exemplo 1</span><span class="sxs-lookup"><span data-stu-id="53c48-117">Example 1</span></span>

<span data-ttu-id="53c48-118">`INT64VALUE ("22565422744")` retorna o valor *Int64* **22565422744**.</span><span class="sxs-lookup"><span data-stu-id="53c48-118">`INT64VALUE ("22565422744")` returns the *Int64* value **22565422744**.</span></span>

## <a name="example-2"></a><span data-ttu-id="53c48-119">Exemplo 2</span><span class="sxs-lookup"><span data-stu-id="53c48-119">Example 2</span></span>

<span data-ttu-id="53c48-120">`INT64VALUE ( VALUE("22565422744.77"))` retorna o valor *Int64* **22565422744**.</span><span class="sxs-lookup"><span data-stu-id="53c48-120">`INT64VALUE ( VALUE("22565422744.77"))` returns the *Int64* value **22565422744**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="53c48-121">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="53c48-121">Additional resources</span></span>

[<span data-ttu-id="53c48-122">Funções de conversão de tipo</span><span class="sxs-lookup"><span data-stu-id="53c48-122">Type conversion functions</span></span>](er-functions-category-type-conversion.md)
