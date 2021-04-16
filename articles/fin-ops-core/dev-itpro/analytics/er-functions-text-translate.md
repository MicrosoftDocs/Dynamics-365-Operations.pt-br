---
title: Função de ER TRANSLATE
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) TRANSLATE é usada.
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
ms.openlocfilehash: 7e4d6417757e27190ab7cabf2bf01243bb87b55c
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5746064"
---
# <a name="translate-er-function"></a><span data-ttu-id="72a3f-103">Função de ER TRANSLATE</span><span class="sxs-lookup"><span data-stu-id="72a3f-103">TRANSLATE ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="72a3f-104">A função `TRANSLATE` retorna um valor *Cadeia de caracteres* que contém o resultado da substituição de caractere do texto especificado em caracteres para outro conjunto fornecido.</span><span class="sxs-lookup"><span data-stu-id="72a3f-104">The `TRANSLATE` function returns a *String* value that contains the result of the character replacement of specified text in characters of another provided set.</span></span>

## <a name="syntax"></a><span data-ttu-id="72a3f-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="72a3f-105">Syntax</span></span>

```vb
TRANSLATE (text , pattern, replacement)
```

## <a name="arguments"></a><span data-ttu-id="72a3f-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="72a3f-106">Arguments</span></span>

<span data-ttu-id="72a3f-107">`text`: *Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="72a3f-107">`text`: *String*</span></span>

<span data-ttu-id="72a3f-108">O caminho válido de uma fonte de dados do tipo *Cadeia de caracteres*.</span><span class="sxs-lookup"><span data-stu-id="72a3f-108">The valid path of a data source of the *String* type.</span></span>

<span data-ttu-id="72a3f-109">`pattern`: *Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="72a3f-109">`pattern`: *String*</span></span>

<span data-ttu-id="72a3f-110">O texto que deve ser substituído.</span><span class="sxs-lookup"><span data-stu-id="72a3f-110">The text that must be replaced.</span></span>

<span data-ttu-id="72a3f-111">`replacement`: *Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="72a3f-111">`replacement`: *String*</span></span>

<span data-ttu-id="72a3f-112">O texto a ser usado como substituto.</span><span class="sxs-lookup"><span data-stu-id="72a3f-112">The text to use as a replacement.</span></span>

## <a name="return-values"></a><span data-ttu-id="72a3f-113">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="72a3f-113">Return values</span></span>

<span data-ttu-id="72a3f-114">*Sequência de caracteres*</span><span class="sxs-lookup"><span data-stu-id="72a3f-114">*String*</span></span>

<span data-ttu-id="72a3f-115">O valor de texto resultante.</span><span class="sxs-lookup"><span data-stu-id="72a3f-115">The resulting text value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="72a3f-116">Notas de uso</span><span class="sxs-lookup"><span data-stu-id="72a3f-116">Usage notes</span></span>

<span data-ttu-id="72a3f-117">A função `TRANSLATE` substitui um caractere por vez.</span><span class="sxs-lookup"><span data-stu-id="72a3f-117">The `TRANSLATE` function replaces one character at a time.</span></span> <span data-ttu-id="72a3f-118">A função substitui o primeiro caractere do argumento `text` pelo primeiro caractere do argumento `pattern` e, em seguida, o segundo caractere e segue o mesmo fluxo até concluir.</span><span class="sxs-lookup"><span data-stu-id="72a3f-118">The function replaces the first character of the `text` argument with the first character of the `pattern` argument and then the second character and follows the same flow until finished.</span></span> <span data-ttu-id="72a3f-119">Quando um caractere dos argumentos `text` e `pattern` é correspondente, ele é substituído por um caractere do argumento `replacement` localizado na mesma posição que o caractere do argumento `pattern`.</span><span class="sxs-lookup"><span data-stu-id="72a3f-119">When a character from the `text` and `pattern` arguments match, it is replaced by a character from the `replacement` argument that is located in the same position as the character from the `pattern` argument.</span></span> <span data-ttu-id="72a3f-120">Se um caractere aparecer várias vezes no argumento `pattern`, será usado o mapeamento de argumento `replacement` que corresponde à primeira ocorrência deste caractere.</span><span class="sxs-lookup"><span data-stu-id="72a3f-120">If a character appears multiple times in the `pattern` argument, the `replacement` argument mapping that corresponds to the first occurrence of this character is used.</span></span>

## <a name="example-1"></a><span data-ttu-id="72a3f-121">Exemplo 1</span><span class="sxs-lookup"><span data-stu-id="72a3f-121">Example 1</span></span>

<span data-ttu-id="72a3f-122">`TRANSLATE ("abcdef", "cd", "GH")` substitui o caractere **"c"** do texto **“abcdef”** especificado com o caractere **"G"** do texto `replacement` devido ao seguinte:</span><span class="sxs-lookup"><span data-stu-id="72a3f-122">`TRANSLATE ("abcdef", "cd", "GH")` replaces the **"c"** character of the specified  **“abcdef”** text with the **"G"** character of the `replacement` text due to the following:</span></span>
-   <span data-ttu-id="72a3f-123">O caractere **"c"** é apresentado no texto `pattern` da primeira posição.</span><span class="sxs-lookup"><span data-stu-id="72a3f-123">The **"c"** character is presented in the `pattern` text in the first position.</span></span>
-   <span data-ttu-id="72a3f-124">A primeira posição do texto `replacement` contém o caractere **"G"**.</span><span class="sxs-lookup"><span data-stu-id="72a3f-124">The first position of the `replacement` text contains the **"G"** character.</span></span>

## <a name="example-2"></a><span data-ttu-id="72a3f-125">Exemplo 2</span><span class="sxs-lookup"><span data-stu-id="72a3f-125">Example 2</span></span>

<span data-ttu-id="72a3f-126">`TRANSLATE ("abcdef", "ccd", "GH")` retorna **"abGdef"**.</span><span class="sxs-lookup"><span data-stu-id="72a3f-126">`TRANSLATE ("abcdef", "ccd", "GH")` returns **"abGdef"**.</span></span>

## <a name="example-3"></a><span data-ttu-id="72a3f-127">Exemplo 3</span><span class="sxs-lookup"><span data-stu-id="72a3f-127">Example 3</span></span>

<span data-ttu-id="72a3f-128">`TRANSLATE ("abccba", "abc", "123")` retorna **"123321"**.</span><span class="sxs-lookup"><span data-stu-id="72a3f-128">`TRANSLATE ("abccba", "abc", "123")` returns **"123321"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="72a3f-129">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="72a3f-129">Additional resources</span></span>

[<span data-ttu-id="72a3f-130">Funções de texto</span><span class="sxs-lookup"><span data-stu-id="72a3f-130">Text functions</span></span>](er-functions-category-text.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]