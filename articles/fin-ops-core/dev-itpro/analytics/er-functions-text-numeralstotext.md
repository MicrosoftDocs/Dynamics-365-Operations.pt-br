---
title: Função de ER NUMERALSTOTEXT
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) NUMERALSTOTEXT é usada.
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
ms.openlocfilehash: 459123a66dae7a3d87a22b042e1be6585959ac15
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/20/2019
ms.locfileid: "2915616"
---
# <span data-ttu-id="78265-103"><a name="NUMERALSTOTEXT">Função de ER NUMERALSTOTEXT</a></span><span class="sxs-lookup"><span data-stu-id="78265-103"><a name="NUMERALSTOTEXT">NUMERALSTOTEXT ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="78265-104">A função `NUMERALSTOTEXT` retorna o número especificado como um valor de *Cadeia de caracteres* após ele ser soletrado (ou seja, convertido em cadeias de caracteres de texto) no idioma especificado.</span><span class="sxs-lookup"><span data-stu-id="78265-104">The `NUMERALSTOTEXT` function returns the specified number as a *String* value after it has been spelled out (that is, converted to text strings) in the specified language.</span></span>

## <a name="syntax"></a><span data-ttu-id="78265-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="78265-105">Syntax</span></span>

```
NUMERALSTOTEXT (number, language, currency, print currency name flag, decimal points)
```

## <a name="arguments"></a><span data-ttu-id="78265-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="78265-106">Arguments</span></span>

<span data-ttu-id="78265-107">`number`: *Inteiro* ou *Real*</span><span class="sxs-lookup"><span data-stu-id="78265-107">`number`: *Integer* or *Real*</span></span>

<span data-ttu-id="78265-108">Um valor numérico que especifica o número que deve ser soletrado.</span><span class="sxs-lookup"><span data-stu-id="78265-108">A numeric value that specifies the number that must be spelled out.</span></span>

<span data-ttu-id="78265-109">`language`: *Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="78265-109">`language`: *String*</span></span>

<span data-ttu-id="78265-110">Um valor de *Cadeia de caracteres* que representa o código de idioma.</span><span class="sxs-lookup"><span data-stu-id="78265-110">A *String* value that represents the language code.</span></span>

<span data-ttu-id="78265-111">`currency`: *Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="78265-111">`currency`: *String*</span></span>

<span data-ttu-id="78265-112">Um valor de *Cadeia de caracteres* que representa o código de moeda.</span><span class="sxs-lookup"><span data-stu-id="78265-112">A *String* value that represents the currency code.</span></span>

<span data-ttu-id="78265-113">`print currency name flag`: *Booliano*</span><span class="sxs-lookup"><span data-stu-id="78265-113">`print currency name flag`: *Boolean*</span></span>

<span data-ttu-id="78265-114">Um valor *Booliano* que indica se um nome de moeda deve ser adicionado ao texto soletrado.</span><span class="sxs-lookup"><span data-stu-id="78265-114">A *Boolean* value that indicates whether a currency name must be added to the spelled-out text.</span></span>

<span data-ttu-id="78265-115">`decimal points`: *Inteiro*</span><span class="sxs-lookup"><span data-stu-id="78265-115">`decimal points`: *Integer*</span></span>

<span data-ttu-id="78265-116">Um valor *Inteiro* que indica o número de casas decimais que o texto soletrado deve ter.</span><span class="sxs-lookup"><span data-stu-id="78265-116">An *Integer* value that indicates the number of decimal places that the spelled-out text should have.</span></span>

## <a name="return-values"></a><span data-ttu-id="78265-117">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="78265-117">Return values</span></span>

<span data-ttu-id="78265-118">*Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="78265-118">*String*</span></span>

<span data-ttu-id="78265-119">O valor de texto resultante.</span><span class="sxs-lookup"><span data-stu-id="78265-119">The resulting text value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="78265-120">Notas de uso</span><span class="sxs-lookup"><span data-stu-id="78265-120">Usage notes</span></span>

<span data-ttu-id="78265-121">O código de idioma é opcional.</span><span class="sxs-lookup"><span data-stu-id="78265-121">The language code is optional.</span></span> <span data-ttu-id="78265-122">Se for definido como uma cadeia de caracteres vazia, o código de idioma do contexto em execução será utilizado.</span><span class="sxs-lookup"><span data-stu-id="78265-122">If it's defined as an empty string, the language code for the running context is used.</span></span> <span data-ttu-id="78265-123">O código de idioma padrão é **EN-US**.</span><span class="sxs-lookup"><span data-stu-id="78265-123">The default language code is **EN-US**.</span></span> <span data-ttu-id="78265-124">O código de idioma do contexto em execução é definido em um elemento **Pasta** ou **Arquivo** do formato de relatório eletrônico (ER) que está sendo executado.</span><span class="sxs-lookup"><span data-stu-id="78265-124">The language code for the running context is defined in a **Folder** or **File** element of the Electronic reporting (ER) format that is running.</span></span>

<span data-ttu-id="78265-125">O código de moeda é opcional.</span><span class="sxs-lookup"><span data-stu-id="78265-125">The currency code is optional.</span></span> <span data-ttu-id="78265-126">Se for definido como uma cadeia de caracteres vazia, a moeda da empresa do contexto em execução será utilizada.</span><span class="sxs-lookup"><span data-stu-id="78265-126">If it's defined as an empty string, the company currency for the running context is used.</span></span>

> [!NOTE] 
> <span data-ttu-id="78265-127">Os argumentos `print currency name flag` e `decimal points` são analisados somente para os seguintes códigos de idioma: **CS**, **ET**, **HU**, **LT**, **LV**, **PL** e **RU**.</span><span class="sxs-lookup"><span data-stu-id="78265-127">The `print currency name flag` and `decimal points` arguments are analyzed only for the following language codes: **CS**, **ET**, **HU**, **LT**, **LV**, **PL**, and **RU**.</span></span> <span data-ttu-id="78265-128">Além disso, o argumento `print currency name flag` é analisado somente para empresas nas quais o contexto do país ou da região ofereça suporte a variações de nomes de moeda.</span><span class="sxs-lookup"><span data-stu-id="78265-128">Additionally, the `print currency name flag` argument is analyzed only for companies where the country's or region's context supports declension of currency names.</span></span>

## <a name="example-1"></a><span data-ttu-id="78265-129">Exemplo 1</span><span class="sxs-lookup"><span data-stu-id="78265-129">Example 1</span></span>

<span data-ttu-id="78265-130">`NUMERALSTOTEXT (1234.56, "EN-US", "", false, 2)` retorna **"One Thousand Two Hundred Thirty Four and 56"**.</span><span class="sxs-lookup"><span data-stu-id="78265-130">`NUMERALSTOTEXT (1234.56, "EN-US", "", false, 2)` returns **"One Thousand Two Hundred Thirty Four and 56"**.</span></span>

## <a name="example-2"></a><span data-ttu-id="78265-131">Exemplo 2</span><span class="sxs-lookup"><span data-stu-id="78265-131">Example 2</span></span>

<span data-ttu-id="78265-132">`NUMERALSTOTEXT (120, "PL", "", false, 0)` retorna **"Sto dwadzieścia"**.</span><span class="sxs-lookup"><span data-stu-id="78265-132">`NUMERALSTOTEXT (120, "PL", "", false, 0)` returns **"Sto dwadzieścia"**.</span></span> 

## <a name="example-3"></a><span data-ttu-id="78265-133">Exemplo 3</span><span class="sxs-lookup"><span data-stu-id="78265-133">Example 3</span></span>

<span data-ttu-id="78265-134">`NUMERALSTOTEXT (120.21, "RU", "EUR", true, 2)` retorna **"Сто двадцать евро 21 евроцент"**.</span><span class="sxs-lookup"><span data-stu-id="78265-134">`NUMERALSTOTEXT (120.21, "RU", "EUR", true, 2)` returns **"Сто двадцать евро 21 евроцент"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="78265-135">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="78265-135">Additional resources</span></span>

[<span data-ttu-id="78265-136">Funções de texto</span><span class="sxs-lookup"><span data-stu-id="78265-136">Text functions</span></span>](er-functions-category-text.md)
