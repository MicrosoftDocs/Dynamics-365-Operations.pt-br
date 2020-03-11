---
title: Função de ER TRANSLATE
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) TRANSLATE é usada.
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
ms.openlocfilehash: 07fe19c5f66c33e336f76f3a72d3bbda0c7e8d86
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/12/2020
ms.locfileid: "3040900"
---
# <span data-ttu-id="94c74-103"><a name="TRANSLATE">Função de ER TRANSLATE</a></span><span class="sxs-lookup"><span data-stu-id="94c74-103"><a name="TRANSLATE">TRANSLATE ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="94c74-104">A função `TRANSLATE` retorna a cadeia de caracteres de texto especificada como um valor de *Cadeia de caracteres* após toda ou parte dela ser substituída por outra cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="94c74-104">The `TRANSLATE` function returns the specified text string as a *String* value after all or part of it has been replaced with another string.</span></span>

## <a name="syntax"></a><span data-ttu-id="94c74-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="94c74-105">Syntax</span></span>

```vb
TRANSLATE (text , pattern, replacement)
```

## <a name="arguments"></a><span data-ttu-id="94c74-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="94c74-106">Arguments</span></span>

<span data-ttu-id="94c74-107">`text`: *Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="94c74-107">`text`: *String*</span></span>

<span data-ttu-id="94c74-108">O caminho válido de uma fonte de dados do tipo *Cadeia de caracteres*.</span><span class="sxs-lookup"><span data-stu-id="94c74-108">The valid path of a data source of the *String* type.</span></span>

<span data-ttu-id="94c74-109">`pattern`: *Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="94c74-109">`pattern`: *String*</span></span>

<span data-ttu-id="94c74-110">O texto que deve ser substituído.</span><span class="sxs-lookup"><span data-stu-id="94c74-110">The text that must be replaced.</span></span>

<span data-ttu-id="94c74-111">`replacement`: *Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="94c74-111">`replacement`: *String*</span></span>

<span data-ttu-id="94c74-112">O texto a ser usado como substituto.</span><span class="sxs-lookup"><span data-stu-id="94c74-112">The text to use as a replacement.</span></span>

## <a name="return-values"></a><span data-ttu-id="94c74-113">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="94c74-113">Return values</span></span>

<span data-ttu-id="94c74-114">*Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="94c74-114">*String*</span></span>

<span data-ttu-id="94c74-115">O valor de texto resultante.</span><span class="sxs-lookup"><span data-stu-id="94c74-115">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="94c74-116">Exemplo</span><span class="sxs-lookup"><span data-stu-id="94c74-116">Example</span></span>

<span data-ttu-id="94c74-117">`TRANSLATE ("abcdef", "cd", "GH")` substitui o padrão **"cd"** pela cadeia de caracteres **"GH"** e retorna **"abGHef"**.</span><span class="sxs-lookup"><span data-stu-id="94c74-117">`TRANSLATE ("abcdef", "cd", "GH")` replaces the pattern **"cd"** with the string **"GH"** and returns **"abGHef"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="94c74-118">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="94c74-118">Additional resources</span></span>

[<span data-ttu-id="94c74-119">Funções de texto</span><span class="sxs-lookup"><span data-stu-id="94c74-119">Text functions</span></span>](er-functions-category-text.md)
