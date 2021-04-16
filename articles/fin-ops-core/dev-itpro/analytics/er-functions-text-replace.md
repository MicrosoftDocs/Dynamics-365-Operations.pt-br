---
title: Função de ER REPLACE
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) REPLACE é usada.
author: NickSelin
ms.date: 04/02/2020
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
ms.openlocfilehash: 21cdd8532730925b7d5c6f5b3bb565dcd365dd6d
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5746186"
---
# <a name="replace-er-function"></a><span data-ttu-id="f184f-103">Função de ER REPLACE</span><span class="sxs-lookup"><span data-stu-id="f184f-103">REPLACE ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="f184f-104">A função `REPLACE` retorna a cadeia de caracteres de texto especificada como um valor de *Cadeia de caracteres* após toda ou parte dela ser substituída por outra cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="f184f-104">The `REPLACE` function returns the specified text string as a *String* value after all or part of it has been replaced with another string.</span></span>

## <a name="syntax"></a><span data-ttu-id="f184f-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="f184f-105">Syntax</span></span>

```vb
REPLACE (text, pattern, replacement, regular expression flag)
```

## <a name="arguments"></a><span data-ttu-id="f184f-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="f184f-106">Arguments</span></span>

<span data-ttu-id="f184f-107">`text`: *Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="f184f-107">`text`: *String*</span></span>

<span data-ttu-id="f184f-108">O caminho válido de uma fonte de dados do tipo *Cadeia de caracteres*.</span><span class="sxs-lookup"><span data-stu-id="f184f-108">The valid path of a data source of the *String* type.</span></span>

<span data-ttu-id="f184f-109">`pattern`: *Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="f184f-109">`pattern`: *String*</span></span>

<span data-ttu-id="f184f-110">Se o argumento `regular expression flag` for **FALSE**, este argumento conterá o texto que deve ser substituído.</span><span class="sxs-lookup"><span data-stu-id="f184f-110">If the `regular expression flag` argument is **FALSE**, this argument contains the text that must be replaced.</span></span>

<span data-ttu-id="f184f-111">Se o argumento `regular expression flag` for **TRUE**, este argumento conterá uma expressão regular que define um padrão de pesquisa e o texto substituto.</span><span class="sxs-lookup"><span data-stu-id="f184f-111">If the `regular expression flag` argument is **TRUE**, this argument contains a regular expression that defines both a search pattern and the replacement text.</span></span>

<span data-ttu-id="f184f-112">`replacement`: *Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="f184f-112">`replacement`: *String*</span></span>

<span data-ttu-id="f184f-113">Se o argumento `regular expression flag` for **FALSE**, este argumento conterá o texto a ser usado como substituto.</span><span class="sxs-lookup"><span data-stu-id="f184f-113">If the `regular expression flag` argument is **FALSE**, this argument contains the text to use as a replacement.</span></span>

<span data-ttu-id="f184f-114">Se o argumento `regular expression flag` for **TRUE**, este argumento não será usado.</span><span class="sxs-lookup"><span data-stu-id="f184f-114">If the `regular expression flag` argument is **TRUE**, this argument isn't used.</span></span>

<span data-ttu-id="f184f-115">`regular expression flag`: *Booliano*</span><span class="sxs-lookup"><span data-stu-id="f184f-115">`regular expression flag`: *Boolean*</span></span>

<span data-ttu-id="f184f-116">Um valor *Booliano* que indica se uma expressão regular é usada para fazer a substituição.</span><span class="sxs-lookup"><span data-stu-id="f184f-116">A *Boolean* value that indicates whether a regular expression is used to do the replacement.</span></span>

## <a name="return-values"></a><span data-ttu-id="f184f-117">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="f184f-117">Return values</span></span>

<span data-ttu-id="f184f-118">*Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="f184f-118">*String*</span></span>

<span data-ttu-id="f184f-119">O valor de texto resultante.</span><span class="sxs-lookup"><span data-stu-id="f184f-119">The resulting text value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="f184f-120">Notas de uso</span><span class="sxs-lookup"><span data-stu-id="f184f-120">Usage notes</span></span>

<span data-ttu-id="f184f-121">Se o argumento `regular expression flag` for **TRUE**, esta função retornará a cadeia de caracteres especificada depois de ter sido alterada, aplicando a expressão regular especificada pelo argumento `pattern`.</span><span class="sxs-lookup"><span data-stu-id="f184f-121">If the `regular expression flag` argument is **TRUE**, this function returns the specified string after it has been changed by applying the regular expression that is specified by the `pattern` argument.</span></span> <span data-ttu-id="f184f-122">A expressão regular é usada para encontrar os caracteres que devem ser substituídos.</span><span class="sxs-lookup"><span data-stu-id="f184f-122">The regular expression is used to find the characters that must be replaced.</span></span>

<span data-ttu-id="f184f-123">Se o argumento `regular expression flag` for **FALSE**, essa função retorna a cadeia de caracteres especificada após o conjunto de caracteres que foram definidos no argumento `pattern` foram substituídos pelos caracteres do argumento `replacement`.</span><span class="sxs-lookup"><span data-stu-id="f184f-123">If the `regular expression flag` argument is **FALSE**, this function returns the specified string after the set of characters that are defined in the `pattern` argument have been replaced by characters of the `replacement` argument.</span></span> 

## <a name="example-1"></a><span data-ttu-id="f184f-124">Exemplo 1</span><span class="sxs-lookup"><span data-stu-id="f184f-124">Example 1</span></span>

<span data-ttu-id="f184f-125">`REPLACE ("+1 923 456 4971", "[^0-9]", "", true)` aplica uma expressão regular que remove todos os símbolos não numéricos e retorna **"19234564971"**.</span><span class="sxs-lookup"><span data-stu-id="f184f-125">`REPLACE ("+1 923 456 4971", "[^0-9]", "", true)` applies a regular expression that removes all non-numeric symbols, and it returns **"19234564971"**.</span></span> 

## <a name="example-2"></a><span data-ttu-id="f184f-126">Exemplo 2</span><span class="sxs-lookup"><span data-stu-id="f184f-126">Example 2</span></span>

<span data-ttu-id="f184f-127">`REPLACE ("abcdef", "cd", "GH", false)` substitui o padrão **"cd"** pela cadeia de caracteres **"GH"** e retorna **"abGHef"**.</span><span class="sxs-lookup"><span data-stu-id="f184f-127">`REPLACE ("abcdef", "cd", "GH", false)` replaces the pattern **"cd"** with the string **"GH"** and returns **"abGHef"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="f184f-128">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="f184f-128">Additional resources</span></span>

[<span data-ttu-id="f184f-129">Funções de texto</span><span class="sxs-lookup"><span data-stu-id="f184f-129">Text functions</span></span>](er-functions-category-text.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]