---
title: Função de ER TRIM
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) TRIM é usada.
author: NickSelin
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
ms.openlocfilehash: 93b08792a7aab7245d0443da05e0330bf8b2d56e
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5746040"
---
# <a name="trim-er-function"></a><span data-ttu-id="7707e-103">Função de ER TRIM</span><span class="sxs-lookup"><span data-stu-id="7707e-103">TRIM ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="7707e-104">A função `TRIM` retorna a cadeia de caracteres de texto especificada como um valor de *Cadeia de caracteres* após os espaços à direita e à esquerda serem truncados e após vários espaços entre as palavras serem removidos.</span><span class="sxs-lookup"><span data-stu-id="7707e-104">The `TRIM` function returns the specified text string as a *String* value after leading and trailing spaces have been truncated, and after multiple spaces between words have been removed.</span></span>

## <a name="syntax"></a><span data-ttu-id="7707e-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="7707e-105">Syntax</span></span>

```vb
TRIM (text )
```

## <a name="arguments"></a><span data-ttu-id="7707e-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="7707e-106">Arguments</span></span>

<span data-ttu-id="7707e-107">`text`: *Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="7707e-107">`text`: *String*</span></span>

<span data-ttu-id="7707e-108">O caminho válido de uma fonte de dados do tipo *Cadeia de caracteres*.</span><span class="sxs-lookup"><span data-stu-id="7707e-108">The valid path of a data source of the *String* type.</span></span>

## <a name="return-values"></a><span data-ttu-id="7707e-109">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="7707e-109">Return values</span></span>

<span data-ttu-id="7707e-110">*Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="7707e-110">*String*</span></span>

<span data-ttu-id="7707e-111">O valor de texto resultante.</span><span class="sxs-lookup"><span data-stu-id="7707e-111">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="7707e-112">Exemplo</span><span class="sxs-lookup"><span data-stu-id="7707e-112">Example</span></span>

<span data-ttu-id="7707e-113">`TRIM ("`&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`Sample`&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`text`&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`")` retorna **"Texto de exemplo"**.</span><span class="sxs-lookup"><span data-stu-id="7707e-113">`TRIM ("`&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`Sample`&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`text`&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`")` returns **"Sample text"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="7707e-114">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="7707e-114">Additional resources</span></span>

[<span data-ttu-id="7707e-115">Funções de texto</span><span class="sxs-lookup"><span data-stu-id="7707e-115">Text functions</span></span>](er-functions-category-text.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]