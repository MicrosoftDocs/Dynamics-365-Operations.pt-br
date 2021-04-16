---
title: Função de ER LOWER
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) LOWER é usada.
author: NickSelin
ms.date: 12/11/2019
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
ms.openlocfilehash: e684883d4262e4c3cd8a84d0a1c6f1d685bb650b
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5746282"
---
# <a name="lower-er-function"></a><span data-ttu-id="5e264-103">Função de ER LOWER</span><span class="sxs-lookup"><span data-stu-id="5e264-103">LOWER ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="5e264-104">A função `LOWER` retorna a cadeia de caracteres de texto especificada como um valor de *Cadeia de caracteres* após ser convertida em letras minúsculas.</span><span class="sxs-lookup"><span data-stu-id="5e264-104">The `LOWER` function returns the specified text string as a *String* value after it has been converted to lowercase letters.</span></span>

## <a name="syntax"></a><span data-ttu-id="5e264-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="5e264-105">Syntax</span></span>

```vb
LOWER (text)
```

## <a name="arguments"></a><span data-ttu-id="5e264-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="5e264-106">Arguments</span></span>

<span data-ttu-id="5e264-107">`text`: *Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="5e264-107">`text`: *String*</span></span>

<span data-ttu-id="5e264-108">Um valor de *Cadeia de caracteres* que especifica o texto.</span><span class="sxs-lookup"><span data-stu-id="5e264-108">A *String* value that specifies the text.</span></span>

## <a name="return-values"></a><span data-ttu-id="5e264-109">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="5e264-109">Return values</span></span>

<span data-ttu-id="5e264-110">*Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="5e264-110">*String*</span></span>

<span data-ttu-id="5e264-111">O valor de texto resultante.</span><span class="sxs-lookup"><span data-stu-id="5e264-111">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="5e264-112">Exemplo</span><span class="sxs-lookup"><span data-stu-id="5e264-112">Example</span></span>

<span data-ttu-id="5e264-113">`LOWER ("Sample")` retorna **"exemplo"**.</span><span class="sxs-lookup"><span data-stu-id="5e264-113">`LOWER ("Sample")` returns **"sample"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="5e264-114">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="5e264-114">Additional resources</span></span>

[<span data-ttu-id="5e264-115">Funções de texto</span><span class="sxs-lookup"><span data-stu-id="5e264-115">Text functions</span></span>](er-functions-category-text.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]