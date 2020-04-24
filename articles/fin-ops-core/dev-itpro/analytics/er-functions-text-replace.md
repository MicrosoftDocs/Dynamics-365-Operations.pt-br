---
title: Função de ER REPLACE
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) REPLACE é usada.
author: NickSelin
manager: kfend
ms.date: 04/02/2020
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
ms.openlocfilehash: 83d5095620a938f1ac4b8428fff9209fda7a7831
ms.sourcegitcommit: fb8ad8e2b142441a6530b364f3258bbcc0c724d2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/02/2020
ms.locfileid: "3201057"
---
# <a name=""></a><span data-ttu-id="40da3-103"><a name="REPLACE">Função de ER REPLACE</a></span><span class="sxs-lookup"><span data-stu-id="40da3-103"><a name="REPLACE">REPLACE ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="40da3-104">A função `REPLACE` retorna a cadeia de caracteres de texto especificada como um valor de *Cadeia de caracteres* após toda ou parte dela ser substituída por outra cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="40da3-104">The `REPLACE` function returns the specified text string as a *String* value after all or part of it has been replaced with another string.</span></span>

## <a name="syntax"></a><span data-ttu-id="40da3-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="40da3-105">Syntax</span></span>

```vb
REPLACE (text, pattern, replacement, regular expression flag)
```

## <a name="arguments"></a><span data-ttu-id="40da3-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="40da3-106">Arguments</span></span>

<span data-ttu-id="40da3-107">`text`: *Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="40da3-107">`text`: *String*</span></span>

<span data-ttu-id="40da3-108">O caminho válido de uma fonte de dados do tipo *Cadeia de caracteres*.</span><span class="sxs-lookup"><span data-stu-id="40da3-108">The valid path of a data source of the *String* type.</span></span>

<span data-ttu-id="40da3-109">`pattern`: *Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="40da3-109">`pattern`: *String*</span></span>

<span data-ttu-id="40da3-110">Se o argumento `regular expression flag` for **FALSE**, este argumento conterá o texto que deve ser substituído.</span><span class="sxs-lookup"><span data-stu-id="40da3-110">If the `regular expression flag` argument is **FALSE**, this argument contains the text that must be replaced.</span></span>

<span data-ttu-id="40da3-111">Se o argumento `regular expression flag` for **TRUE**, este argumento conterá uma expressão regular que define um padrão de pesquisa e o texto substituto.</span><span class="sxs-lookup"><span data-stu-id="40da3-111">If the `regular expression flag` argument is **TRUE**, this argument contains a regular expression that defines both a search pattern and the replacement text.</span></span>

<span data-ttu-id="40da3-112">`replacement`: *Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="40da3-112">`replacement`: *String*</span></span>

<span data-ttu-id="40da3-113">Se o argumento `regular expression flag` for **FALSE**, este argumento conterá o texto a ser usado como substituto.</span><span class="sxs-lookup"><span data-stu-id="40da3-113">If the `regular expression flag` argument is **FALSE**, this argument contains the text to use as a replacement.</span></span>

<span data-ttu-id="40da3-114">Se o argumento `regular expression flag` for **TRUE**, este argumento não será usado.</span><span class="sxs-lookup"><span data-stu-id="40da3-114">If the `regular expression flag` argument is **TRUE**, this argument isn't used.</span></span>

<span data-ttu-id="40da3-115">`regular expression flag`: *Booliano*</span><span class="sxs-lookup"><span data-stu-id="40da3-115">`regular expression flag`: *Boolean*</span></span>

<span data-ttu-id="40da3-116">Um valor *Booliano* que indica se uma expressão regular é usada para fazer a substituição.</span><span class="sxs-lookup"><span data-stu-id="40da3-116">A *Boolean* value that indicates whether a regular expression is used to do the replacement.</span></span>

## <a name="return-values"></a><span data-ttu-id="40da3-117">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="40da3-117">Return values</span></span>

<span data-ttu-id="40da3-118">*Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="40da3-118">*String*</span></span>

<span data-ttu-id="40da3-119">O valor de texto resultante.</span><span class="sxs-lookup"><span data-stu-id="40da3-119">The resulting text value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="40da3-120">Notas de uso</span><span class="sxs-lookup"><span data-stu-id="40da3-120">Usage notes</span></span>

<span data-ttu-id="40da3-121">Se o argumento `regular expression flag` for **TRUE**, esta função retornará a cadeia de caracteres especificada depois de ter sido alterada, aplicando a expressão regular especificada pelo argumento `pattern`.</span><span class="sxs-lookup"><span data-stu-id="40da3-121">If the `regular expression flag` argument is **TRUE**, this function returns the specified string after it has been changed by applying the regular expression that is specified by the `pattern` argument.</span></span> <span data-ttu-id="40da3-122">A expressão regular é usada para encontrar os caracteres que devem ser substituídos.</span><span class="sxs-lookup"><span data-stu-id="40da3-122">The regular expression is used to find the characters that must be replaced.</span></span>

<span data-ttu-id="40da3-123">Se o argumento `regular expression flag` for **FALSE**, essa função retorna a cadeia de caracteres especificada após o conjunto de caracteres que foram definidos no argumento `pattern` foram substituídos pelos caracteres do argumento `replacement`.</span><span class="sxs-lookup"><span data-stu-id="40da3-123">If the `regular expression flag` argument is **FALSE**, this function returns the specified string after the set of characters that are defined in the `pattern` argument have been replaced by characters of the `replacement` argument.</span></span> 

## <a name="example-1"></a><span data-ttu-id="40da3-124">Exemplo 1</span><span class="sxs-lookup"><span data-stu-id="40da3-124">Example 1</span></span>

<span data-ttu-id="40da3-125">`REPLACE ("+1 923 456 4971", "[^0-9]", "", true)` aplica uma expressão regular que remove todos os símbolos não numéricos e retorna **"19234564971"**.</span><span class="sxs-lookup"><span data-stu-id="40da3-125">`REPLACE ("+1 923 456 4971", "[^0-9]", "", true)` applies a regular expression that removes all non-numeric symbols, and it returns **"19234564971"**.</span></span> 

## <a name="example-2"></a><span data-ttu-id="40da3-126">Exemplo 2</span><span class="sxs-lookup"><span data-stu-id="40da3-126">Example 2</span></span>

<span data-ttu-id="40da3-127">`REPLACE ("abcdef", "cd", "GH", false)` substitui o padrão **"cd"** pela cadeia de caracteres **"GH"** e retorna **"abGHef"**.</span><span class="sxs-lookup"><span data-stu-id="40da3-127">`REPLACE ("abcdef", "cd", "GH", false)` replaces the pattern **"cd"** with the string **"GH"** and returns **"abGHef"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="40da3-128">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="40da3-128">Additional resources</span></span>

[<span data-ttu-id="40da3-129">Funções de texto</span><span class="sxs-lookup"><span data-stu-id="40da3-129">Text functions</span></span>](er-functions-category-text.md)
