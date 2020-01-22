---
title: Função de ER LEFT
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) LEFT é usada.
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
ms.openlocfilehash: 8280a05ea180d9de499d87efa53eca8ca912b0e3
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/20/2019
ms.locfileid: "2915639"
---
# <span data-ttu-id="bc6f8-103"><a name="LEFT">Função de ER LEFT</a></span><span class="sxs-lookup"><span data-stu-id="bc6f8-103"><a name="LEFT">LEFT ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="bc6f8-104">A função `LEFT` retorna um valor de *Cadeia de caracteres* que apresenta o número de caracteres especificado a partir do início da cadeia de caracteres especificada.</span><span class="sxs-lookup"><span data-stu-id="bc6f8-104">The `LEFT` function returns a *String* value that presents the specified number of characters from the start of the specified string.</span></span>

## <a name="syntax"></a><span data-ttu-id="bc6f8-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="bc6f8-105">Syntax</span></span>

```
LEFT (text, number)
```

## <a name="arguments"></a><span data-ttu-id="bc6f8-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="bc6f8-106">Arguments</span></span>

<span data-ttu-id="bc6f8-107">`text`: *Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="bc6f8-107">`text`: *String*</span></span>

<span data-ttu-id="bc6f8-108">Um valor de *Cadeia de caracteres* que representa o texto original.</span><span class="sxs-lookup"><span data-stu-id="bc6f8-108">A *String* value that represents the original text.</span></span>

<span data-ttu-id="bc6f8-109">`number`: *Inteiro*</span><span class="sxs-lookup"><span data-stu-id="bc6f8-109">`number`: *Integer*</span></span>

<span data-ttu-id="bc6f8-110">O número de caracteres que deve ser retornado a partir do início do texto original.</span><span class="sxs-lookup"><span data-stu-id="bc6f8-110">The number of characters that must be returned from the start of the original text.</span></span>

## <a name="return-values"></a><span data-ttu-id="bc6f8-111">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="bc6f8-111">Return values</span></span>

<span data-ttu-id="bc6f8-112">*Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="bc6f8-112">*String*</span></span>

<span data-ttu-id="bc6f8-113">O valor de texto resultante.</span><span class="sxs-lookup"><span data-stu-id="bc6f8-113">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="bc6f8-114">Exemplo</span><span class="sxs-lookup"><span data-stu-id="bc6f8-114">Example</span></span>

<span data-ttu-id="bc6f8-115">`LEFT ("Sample", 3)` retorna **"Sam"**.</span><span class="sxs-lookup"><span data-stu-id="bc6f8-115">`LEFT ("Sample", 3)` returns **"Sam"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="bc6f8-116">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="bc6f8-116">Additional resources</span></span>

[<span data-ttu-id="bc6f8-117">Funções de texto</span><span class="sxs-lookup"><span data-stu-id="bc6f8-117">Text functions</span></span>](er-functions-category-text.md)
