---
title: Função de ER RIGHT
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) RIGHT é usada.
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
ms.openlocfilehash: 01718f9b153c1d6c46d50a9b17e899ccfba16915
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/20/2019
ms.locfileid: "2916720"
---
# <span data-ttu-id="9bfb1-103"><a name="RIGHT">Função de ER RIGHT</a></span><span class="sxs-lookup"><span data-stu-id="9bfb1-103"><a name="RIGHT">RIGHT ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="9bfb1-104">A função `RIGHT` retorna um valor de *Cadeia de caracteres* que apresenta o número de caracteres especificado a partir do final da cadeia de caracteres especificada.</span><span class="sxs-lookup"><span data-stu-id="9bfb1-104">The `RIGHT` function returns a *String* value that presents the specified number of characters from the end of the specified string.</span></span>

## <a name="syntax"></a><span data-ttu-id="9bfb1-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="9bfb1-105">Syntax</span></span>

```
RIGHT (text, number)
```

## <a name="arguments"></a><span data-ttu-id="9bfb1-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="9bfb1-106">Arguments</span></span>

<span data-ttu-id="9bfb1-107">`text`: *Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="9bfb1-107">`text`: *String*</span></span>

<span data-ttu-id="9bfb1-108">Um valor de *Cadeia de caracteres* que representa o texto original.</span><span class="sxs-lookup"><span data-stu-id="9bfb1-108">A *String* value that represents the original text.</span></span>

<span data-ttu-id="9bfb1-109">`number`: *Inteiro*</span><span class="sxs-lookup"><span data-stu-id="9bfb1-109">`number`: *Integer*</span></span>

<span data-ttu-id="9bfb1-110">O número de caracteres que deve ser retornado a partir do final do texto original.</span><span class="sxs-lookup"><span data-stu-id="9bfb1-110">The number of characters that must be returned from the end of the original text.</span></span>

## <a name="return-values"></a><span data-ttu-id="9bfb1-111">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="9bfb1-111">Return values</span></span>

<span data-ttu-id="9bfb1-112">*Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="9bfb1-112">*String*</span></span>

<span data-ttu-id="9bfb1-113">O valor de texto resultante.</span><span class="sxs-lookup"><span data-stu-id="9bfb1-113">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="9bfb1-114">Exemplo</span><span class="sxs-lookup"><span data-stu-id="9bfb1-114">Example</span></span>

<span data-ttu-id="9bfb1-115">`RIGHT ("Sample", 3)` retorna **"ple"**.</span><span class="sxs-lookup"><span data-stu-id="9bfb1-115">`RIGHT ("Sample", 3)` returns **"ple"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="9bfb1-116">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="9bfb1-116">Additional resources</span></span>

[<span data-ttu-id="9bfb1-117">Funções de texto</span><span class="sxs-lookup"><span data-stu-id="9bfb1-117">Text functions</span></span>](er-functions-category-text.md)
