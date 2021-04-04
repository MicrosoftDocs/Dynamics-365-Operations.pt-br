---
title: Função de ER INT64VALUE
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) INT64VALUE é usada.
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
ms.openlocfilehash: 9db2e9abcac36a8331a494c886218bbfc82e93aa
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/09/2021
ms.locfileid: "5561485"
---
# <a name="int64value-er-function"></a><span data-ttu-id="bcad4-103">Função de ER INT64VALUE</span><span class="sxs-lookup"><span data-stu-id="bcad4-103">INT64VALUE ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="bcad4-104">A função `INT64VALUE` retorna um valor *Int64* que representa a cadeia de caracteres especificada.</span><span class="sxs-lookup"><span data-stu-id="bcad4-104">The `INT64VALUE` function returns an *Int64* value that represents the specified string.</span></span>

## <a name="syntax-1"></a><span data-ttu-id="bcad4-105">Sintaxe 1</span><span class="sxs-lookup"><span data-stu-id="bcad4-105">Syntax 1</span></span>

```vb
INT64VALUE (text)
```

## <a name="syntax-2"></a><span data-ttu-id="bcad4-106">Sintaxe 2</span><span class="sxs-lookup"><span data-stu-id="bcad4-106">Syntax 2</span></span>

```vb
INT64VALUE (number)
```

## <a name="arguments"></a><span data-ttu-id="bcad4-107">Argumentos</span><span class="sxs-lookup"><span data-stu-id="bcad4-107">Arguments</span></span>

<span data-ttu-id="bcad4-108">`text`: *Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="bcad4-108">`text`: *String*</span></span>

<span data-ttu-id="bcad4-109">Um valor de texto que deve ser convertido para um número *Int64*.</span><span class="sxs-lookup"><span data-stu-id="bcad4-109">A text value that must be converted to an *Int64* number.</span></span>

<span data-ttu-id="bcad4-110">`number`: *Real* ou *Inteiro*</span><span class="sxs-lookup"><span data-stu-id="bcad4-110">`number`: *Real* or *Integer*</span></span>

<span data-ttu-id="bcad4-111">Um valor *Real* ou *Inteiro* numérico que deve ser convertido a um número *Int64*.</span><span class="sxs-lookup"><span data-stu-id="bcad4-111">A numeric *Real* or *Integer* value that must be converted to an *Int64* number.</span></span>

## <a name="return-values"></a><span data-ttu-id="bcad4-112">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="bcad4-112">Return values</span></span>

<span data-ttu-id="bcad4-113">*Int64*</span><span class="sxs-lookup"><span data-stu-id="bcad4-113">*Int64*</span></span>

<span data-ttu-id="bcad4-114">O valor numérico resultante.</span><span class="sxs-lookup"><span data-stu-id="bcad4-114">The resulting numeric value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="bcad4-115">Notas de uso</span><span class="sxs-lookup"><span data-stu-id="bcad4-115">Usage notes</span></span>

<span data-ttu-id="bcad4-116">Todas as casas decimais são truncadas.</span><span class="sxs-lookup"><span data-stu-id="bcad4-116">Any decimal places are truncated.</span></span>

## <a name="example-1"></a><span data-ttu-id="bcad4-117">Exemplo 1</span><span class="sxs-lookup"><span data-stu-id="bcad4-117">Example 1</span></span>

<span data-ttu-id="bcad4-118">`INT64VALUE ("22565422744")` retorna o valor *Int64* **22565422744**.</span><span class="sxs-lookup"><span data-stu-id="bcad4-118">`INT64VALUE ("22565422744")` returns the *Int64* value **22565422744**.</span></span>

## <a name="example-2"></a><span data-ttu-id="bcad4-119">Exemplo 2</span><span class="sxs-lookup"><span data-stu-id="bcad4-119">Example 2</span></span>

<span data-ttu-id="bcad4-120">`INT64VALUE ( VALUE("22565422744.77"))` retorna o valor *Int64* **22565422744**.</span><span class="sxs-lookup"><span data-stu-id="bcad4-120">`INT64VALUE ( VALUE("22565422744.77"))` returns the *Int64* value **22565422744**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="bcad4-121">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="bcad4-121">Additional resources</span></span>

[<span data-ttu-id="bcad4-122">Funções de conversão de tipo</span><span class="sxs-lookup"><span data-stu-id="bcad4-122">Type conversion functions</span></span>](er-functions-category-type-conversion.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]