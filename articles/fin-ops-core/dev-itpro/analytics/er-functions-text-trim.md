---
title: Função de ER TRIM
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) TRIM é usada.
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
ms.openlocfilehash: 2673b0167f7602a6d6eaa79be639905028e99822
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/20/2019
ms.locfileid: "2915524"
---
# <span data-ttu-id="b1443-103"><a name="TRIM">Função de ER TRIM</a></span><span class="sxs-lookup"><span data-stu-id="b1443-103"><a name="TRIM">TRIM ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b1443-104">A função `TRIM` retorna a cadeia de caracteres de texto especificada como um valor de *Cadeia de caracteres* após os espaços à direita e à esquerda serem truncados e após vários espaços entre as palavras serem removidos.</span><span class="sxs-lookup"><span data-stu-id="b1443-104">The `TRIM` function returns the specified text string as a *String* value after leading and trailing spaces have been truncated, and after multiple spaces between words have been removed.</span></span>

## <a name="syntax"></a><span data-ttu-id="b1443-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="b1443-105">Syntax</span></span>

```
TRIM (text )
```

## <a name="arguments"></a><span data-ttu-id="b1443-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="b1443-106">Arguments</span></span>

<span data-ttu-id="b1443-107">`text`: *Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="b1443-107">`text`: *String*</span></span>

<span data-ttu-id="b1443-108">O caminho válido de uma fonte de dados do tipo *Cadeia de caracteres*.</span><span class="sxs-lookup"><span data-stu-id="b1443-108">The valid path of a data source of the *String* type.</span></span>

## <a name="return-values"></a><span data-ttu-id="b1443-109">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="b1443-109">Return values</span></span>

<span data-ttu-id="b1443-110">*Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="b1443-110">*String*</span></span>

<span data-ttu-id="b1443-111">O valor de texto resultante.</span><span class="sxs-lookup"><span data-stu-id="b1443-111">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="b1443-112">Exemplo</span><span class="sxs-lookup"><span data-stu-id="b1443-112">Example</span></span>

<span data-ttu-id="b1443-113">`TRIM ("`&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`Sample`&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`text`&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`")` retorna **"Texto de exemplo"**.</span><span class="sxs-lookup"><span data-stu-id="b1443-113">`TRIM ("`&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`Sample`&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`text`&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`")` returns **"Sample text"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="b1443-114">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="b1443-114">Additional resources</span></span>

[<span data-ttu-id="b1443-115">Funções de texto</span><span class="sxs-lookup"><span data-stu-id="b1443-115">Text functions</span></span>](er-functions-category-text.md)
