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
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 908da840ffcb94f4a60bb41ce041f5f263c921eb
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2020
ms.locfileid: "4688356"
---
# <a name="trim-er-function"></a><span data-ttu-id="f68bf-103">Função de ER TRIM</span><span class="sxs-lookup"><span data-stu-id="f68bf-103">TRIM ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="f68bf-104">A função `TRIM` retorna a cadeia de caracteres de texto especificada como um valor de *Cadeia de caracteres* após os espaços à direita e à esquerda serem truncados e após vários espaços entre as palavras serem removidos.</span><span class="sxs-lookup"><span data-stu-id="f68bf-104">The `TRIM` function returns the specified text string as a *String* value after leading and trailing spaces have been truncated, and after multiple spaces between words have been removed.</span></span>

## <a name="syntax"></a><span data-ttu-id="f68bf-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="f68bf-105">Syntax</span></span>

```vb
TRIM (text )
```

## <a name="arguments"></a><span data-ttu-id="f68bf-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="f68bf-106">Arguments</span></span>

<span data-ttu-id="f68bf-107">`text`: *Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="f68bf-107">`text`: *String*</span></span>

<span data-ttu-id="f68bf-108">O caminho válido de uma fonte de dados do tipo *Cadeia de caracteres*.</span><span class="sxs-lookup"><span data-stu-id="f68bf-108">The valid path of a data source of the *String* type.</span></span>

## <a name="return-values"></a><span data-ttu-id="f68bf-109">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="f68bf-109">Return values</span></span>

<span data-ttu-id="f68bf-110">*Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="f68bf-110">*String*</span></span>

<span data-ttu-id="f68bf-111">O valor de texto resultante.</span><span class="sxs-lookup"><span data-stu-id="f68bf-111">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="f68bf-112">Exemplo</span><span class="sxs-lookup"><span data-stu-id="f68bf-112">Example</span></span>

<span data-ttu-id="f68bf-113">`TRIM ("`&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`Sample`&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`text`&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`")` retorna **"Texto de exemplo"**.</span><span class="sxs-lookup"><span data-stu-id="f68bf-113">`TRIM ("`&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`Sample`&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`text`&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`")` returns **"Sample text"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="f68bf-114">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="f68bf-114">Additional resources</span></span>

[<span data-ttu-id="f68bf-115">Funções de texto</span><span class="sxs-lookup"><span data-stu-id="f68bf-115">Text functions</span></span>](er-functions-category-text.md)
