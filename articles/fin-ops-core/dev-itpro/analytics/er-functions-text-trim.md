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
ms.openlocfilehash: c95663f1aacaf93c1c4bfc8d36d9515f495bf61e
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/12/2020
ms.locfileid: "3040816"
---
# <span data-ttu-id="a5d14-103"><a name="TRIM">Função de ER TRIM</a></span><span class="sxs-lookup"><span data-stu-id="a5d14-103"><a name="TRIM">TRIM ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="a5d14-104">A função `TRIM` retorna a cadeia de caracteres de texto especificada como um valor de *Cadeia de caracteres* após os espaços à direita e à esquerda serem truncados e após vários espaços entre as palavras serem removidos.</span><span class="sxs-lookup"><span data-stu-id="a5d14-104">The `TRIM` function returns the specified text string as a *String* value after leading and trailing spaces have been truncated, and after multiple spaces between words have been removed.</span></span>

## <a name="syntax"></a><span data-ttu-id="a5d14-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="a5d14-105">Syntax</span></span>

```vb
TRIM (text )
```

## <a name="arguments"></a><span data-ttu-id="a5d14-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="a5d14-106">Arguments</span></span>

<span data-ttu-id="a5d14-107">`text`: *Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="a5d14-107">`text`: *String*</span></span>

<span data-ttu-id="a5d14-108">O caminho válido de uma fonte de dados do tipo *Cadeia de caracteres*.</span><span class="sxs-lookup"><span data-stu-id="a5d14-108">The valid path of a data source of the *String* type.</span></span>

## <a name="return-values"></a><span data-ttu-id="a5d14-109">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="a5d14-109">Return values</span></span>

<span data-ttu-id="a5d14-110">*Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="a5d14-110">*String*</span></span>

<span data-ttu-id="a5d14-111">O valor de texto resultante.</span><span class="sxs-lookup"><span data-stu-id="a5d14-111">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="a5d14-112">Exemplo</span><span class="sxs-lookup"><span data-stu-id="a5d14-112">Example</span></span>

<span data-ttu-id="a5d14-113">`TRIM ("`&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`Sample`&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`text`&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`")` retorna **"Texto de exemplo"**.</span><span class="sxs-lookup"><span data-stu-id="a5d14-113">`TRIM ("`&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`Sample`&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`text`&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`")` returns **"Sample text"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="a5d14-114">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="a5d14-114">Additional resources</span></span>

[<span data-ttu-id="a5d14-115">Funções de texto</span><span class="sxs-lookup"><span data-stu-id="a5d14-115">Text functions</span></span>](er-functions-category-text.md)
