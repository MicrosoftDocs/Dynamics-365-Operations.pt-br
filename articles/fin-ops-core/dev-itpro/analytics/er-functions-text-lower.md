---
title: Função de ER LOWER
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) LOWER é usada.
author: NickSelin
manager: kfend
ms.date: 12/11/2019
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
ms.openlocfilehash: 12577e571c8e87db79395895e2a22e66ee7df32c
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/01/2020
ms.locfileid: "3745672"
---
# <a name="lower-er-function"></a><span data-ttu-id="b2ca3-103">Função de ER LOWER</span><span class="sxs-lookup"><span data-stu-id="b2ca3-103">LOWER ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b2ca3-104">A função `LOWER` retorna a cadeia de caracteres de texto especificada como um valor de *Cadeia de caracteres* após ser convertida em letras minúsculas.</span><span class="sxs-lookup"><span data-stu-id="b2ca3-104">The `LOWER` function returns the specified text string as a *String* value after it has been converted to lowercase letters.</span></span>

## <a name="syntax"></a><span data-ttu-id="b2ca3-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="b2ca3-105">Syntax</span></span>

```vb
LOWER (text)
```

## <a name="arguments"></a><span data-ttu-id="b2ca3-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="b2ca3-106">Arguments</span></span>

<span data-ttu-id="b2ca3-107">`text`: *Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="b2ca3-107">`text`: *String*</span></span>

<span data-ttu-id="b2ca3-108">Um valor de *Cadeia de caracteres* que especifica o texto.</span><span class="sxs-lookup"><span data-stu-id="b2ca3-108">A *String* value that specifies the text.</span></span>

## <a name="return-values"></a><span data-ttu-id="b2ca3-109">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="b2ca3-109">Return values</span></span>

<span data-ttu-id="b2ca3-110">*Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="b2ca3-110">*String*</span></span>

<span data-ttu-id="b2ca3-111">O valor de texto resultante.</span><span class="sxs-lookup"><span data-stu-id="b2ca3-111">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="b2ca3-112">Exemplo</span><span class="sxs-lookup"><span data-stu-id="b2ca3-112">Example</span></span>

<span data-ttu-id="b2ca3-113">`LOWER ("Sample")` retorna **"exemplo"**.</span><span class="sxs-lookup"><span data-stu-id="b2ca3-113">`LOWER ("Sample")` returns **"sample"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="b2ca3-114">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="b2ca3-114">Additional resources</span></span>

[<span data-ttu-id="b2ca3-115">Funções de texto</span><span class="sxs-lookup"><span data-stu-id="b2ca3-115">Text functions</span></span>](er-functions-category-text.md)
