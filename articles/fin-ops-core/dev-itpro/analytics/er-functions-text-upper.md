---
title: Função de ER UPPER
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) UPPER é usada.
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
ms.openlocfilehash: 0e0e9837765914c657a72c5ce04c6f565fa13788
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5749132"
---
# <a name="upper-er-function"></a><span data-ttu-id="b6db3-103">Função de ER UPPER</span><span class="sxs-lookup"><span data-stu-id="b6db3-103">UPPER ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b6db3-104">A função `UPPER` retorna a cadeia de caracteres de texto especificada como um valor de *Cadeia de caracteres* após ela ser convertida em letras maiúsculas.</span><span class="sxs-lookup"><span data-stu-id="b6db3-104">The `UPPER` function returns the specified text string as a *String* value after it has been converted to uppercase letters.</span></span>

## <a name="syntax"></a><span data-ttu-id="b6db3-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="b6db3-105">Syntax</span></span>

```vb
UPPER (text )
```

## <a name="arguments"></a><span data-ttu-id="b6db3-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="b6db3-106">Arguments</span></span>

<span data-ttu-id="b6db3-107">`text`: *Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="b6db3-107">`text`: *String*</span></span>

<span data-ttu-id="b6db3-108">O caminho válido de uma fonte de dados do tipo *Cadeia de caracteres*.</span><span class="sxs-lookup"><span data-stu-id="b6db3-108">The valid path of a data source of the *String* type.</span></span>

## <a name="return-values"></a><span data-ttu-id="b6db3-109">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="b6db3-109">Return values</span></span>

<span data-ttu-id="b6db3-110">*Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="b6db3-110">*String*</span></span>

<span data-ttu-id="b6db3-111">O valor de texto resultante.</span><span class="sxs-lookup"><span data-stu-id="b6db3-111">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="b6db3-112">Exemplo</span><span class="sxs-lookup"><span data-stu-id="b6db3-112">Example</span></span>

<span data-ttu-id="b6db3-113">`UPPER ("Sample")` retorna **"SAMPLE"**.</span><span class="sxs-lookup"><span data-stu-id="b6db3-113">`UPPER ("Sample")` returns **"SAMPLE"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="b6db3-114">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="b6db3-114">Additional resources</span></span>

[<span data-ttu-id="b6db3-115">Funções de texto</span><span class="sxs-lookup"><span data-stu-id="b6db3-115">Text functions</span></span>](er-functions-category-text.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]