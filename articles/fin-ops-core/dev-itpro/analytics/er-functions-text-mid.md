---
title: Função de ER MID
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) MID é usada.
author: NickSelin
manager: kfend
ms.date: 12/10/2019
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
ms.openlocfilehash: e2addace5c5606ebaae56ca658700347978a805b
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/01/2020
ms.locfileid: "3744710"
---
# <a name="mid-er-function"></a><span data-ttu-id="45ef5-103">Função de ER MID</span><span class="sxs-lookup"><span data-stu-id="45ef5-103">MID ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="45ef5-104">A função `MID` retorna um valor de *Cadeia de caracteres* que apresenta o número de caracteres especificado da cadeia de caracteres especificada, a partir da posição especificada.</span><span class="sxs-lookup"><span data-stu-id="45ef5-104">The `MID` function returns a *String* value that presents the specified number of characters from the specified string, starting at the specified position.</span></span>

## <a name="syntax"></a><span data-ttu-id="45ef5-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="45ef5-105">Syntax</span></span>

```vb
MID (text, starting position, number of characters)
```

## <a name="arguments"></a><span data-ttu-id="45ef5-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="45ef5-106">Arguments</span></span>

<span data-ttu-id="45ef5-107">`text`: *Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="45ef5-107">`text`: *String*</span></span>

<span data-ttu-id="45ef5-108">Um valor de *Cadeia de caracteres* que especifica o texto do qual os caracteres devem ser retornados.</span><span class="sxs-lookup"><span data-stu-id="45ef5-108">A *String* value that specifies the text to return characters from.</span></span>

<span data-ttu-id="45ef5-109">`starting position`: *Inteiro*</span><span class="sxs-lookup"><span data-stu-id="45ef5-109">`starting position`: *Integer*</span></span>

<span data-ttu-id="45ef5-110">Um valor *Inteiro* que especifica a posição do primeiro caractere que deve ser retornado do texto especificado.</span><span class="sxs-lookup"><span data-stu-id="45ef5-110">An *Integer* value that specifies the position of the first character that must be returned from the specified text.</span></span>

<span data-ttu-id="45ef5-111">`number of characters`: *Inteiro*</span><span class="sxs-lookup"><span data-stu-id="45ef5-111">`number of characters`: *Integer*</span></span>

<span data-ttu-id="45ef5-112">Um valor *Inteiro* que especifica o número de caracteres que deve ser retornado, a partir da posição inicial especificada.</span><span class="sxs-lookup"><span data-stu-id="45ef5-112">An *Integer* value that specifies the number of characters that must be returned, starting at the specified starting position.</span></span>

## <a name="return-values"></a><span data-ttu-id="45ef5-113">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="45ef5-113">Return values</span></span>

<span data-ttu-id="45ef5-114">*Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="45ef5-114">*String*</span></span>

<span data-ttu-id="45ef5-115">O valor de texto resultante.</span><span class="sxs-lookup"><span data-stu-id="45ef5-115">The resulting text value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="45ef5-116">Notas de uso</span><span class="sxs-lookup"><span data-stu-id="45ef5-116">Usage notes</span></span>

<span data-ttu-id="45ef5-117">Se o valor do argumento `starting position` for menor do que 0 (zero), os caracteres retornados serão contados a partir da primeira posição na cadeia de caracteres especificada.</span><span class="sxs-lookup"><span data-stu-id="45ef5-117">If the value of the `starting position` argument is less than 0 (zero), the characters that are returned are counted from the first position in the specified string.</span></span>

<span data-ttu-id="45ef5-118">Se o valor do argumento `starting position` exceder o tamanho da cadeia de caracteres especificada, uma cadeia de caracteres vazia será retornada.</span><span class="sxs-lookup"><span data-stu-id="45ef5-118">If the value of the `starting position` argument exceeds length of the specified string, an empty string is returned.</span></span>

## <a name="example"></a><span data-ttu-id="45ef5-119">Exemplo</span><span class="sxs-lookup"><span data-stu-id="45ef5-119">Example</span></span>

<span data-ttu-id="45ef5-120">`MID ("Sample", 2, 3)` retorna **"amp"**.</span><span class="sxs-lookup"><span data-stu-id="45ef5-120">`MID ("Sample", 2, 3)` returns **"amp"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="45ef5-121">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="45ef5-121">Additional resources</span></span>

[<span data-ttu-id="45ef5-122">Funções de texto</span><span class="sxs-lookup"><span data-stu-id="45ef5-122">Text functions</span></span>](er-functions-category-text.md)
