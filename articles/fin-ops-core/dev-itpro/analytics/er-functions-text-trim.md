---
title: Função de ER TRIM
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) TRIM é usada.
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
ms.openlocfilehash: b671ef72a3558c17fb16db939770394b225656da
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/09/2021
ms.locfileid: "5560026"
---
# <a name="trim-er-function"></a><span data-ttu-id="d6749-103">Função de ER TRIM</span><span class="sxs-lookup"><span data-stu-id="d6749-103">TRIM ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="d6749-104">A função `TRIM` retorna a cadeia de caracteres de texto especificada como um valor de *Cadeia de caracteres* após os espaços à direita e à esquerda serem truncados e após vários espaços entre as palavras serem removidos.</span><span class="sxs-lookup"><span data-stu-id="d6749-104">The `TRIM` function returns the specified text string as a *String* value after leading and trailing spaces have been truncated, and after multiple spaces between words have been removed.</span></span>

## <a name="syntax"></a><span data-ttu-id="d6749-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="d6749-105">Syntax</span></span>

```vb
TRIM (text )
```

## <a name="arguments"></a><span data-ttu-id="d6749-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="d6749-106">Arguments</span></span>

<span data-ttu-id="d6749-107">`text`: *Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="d6749-107">`text`: *String*</span></span>

<span data-ttu-id="d6749-108">O caminho válido de uma fonte de dados do tipo *Cadeia de caracteres*.</span><span class="sxs-lookup"><span data-stu-id="d6749-108">The valid path of a data source of the *String* type.</span></span>

## <a name="return-values"></a><span data-ttu-id="d6749-109">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="d6749-109">Return values</span></span>

<span data-ttu-id="d6749-110">*Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="d6749-110">*String*</span></span>

<span data-ttu-id="d6749-111">O valor de texto resultante.</span><span class="sxs-lookup"><span data-stu-id="d6749-111">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="d6749-112">Exemplo</span><span class="sxs-lookup"><span data-stu-id="d6749-112">Example</span></span>

<span data-ttu-id="d6749-113">`TRIM ("`&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`Sample`&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`text`&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`")` retorna **"Texto de exemplo"**.</span><span class="sxs-lookup"><span data-stu-id="d6749-113">`TRIM ("`&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`Sample`&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`text`&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`")` returns **"Sample text"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="d6749-114">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="d6749-114">Additional resources</span></span>

[<span data-ttu-id="d6749-115">Funções de texto</span><span class="sxs-lookup"><span data-stu-id="d6749-115">Text functions</span></span>](er-functions-category-text.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]