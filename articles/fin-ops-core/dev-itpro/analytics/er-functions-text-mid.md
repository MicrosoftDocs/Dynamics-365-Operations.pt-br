---
title: Função de ER MID
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) MID é usada.
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
ms.openlocfilehash: e178b01740954b46e2afbd2a2be6200a652a18c0
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/20/2019
ms.locfileid: "2915593"
---
# <span data-ttu-id="7ef4e-103"><a name="MID">Função de ER MID</a></span><span class="sxs-lookup"><span data-stu-id="7ef4e-103"><a name="MID">MID ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="7ef4e-104">A função `MID` retorna um valor de *Cadeia de caracteres* que apresenta o número de caracteres especificado da cadeia de caracteres especificada, a partir da posição especificada.</span><span class="sxs-lookup"><span data-stu-id="7ef4e-104">The `MID` function returns a *String* value that presents the specified number of characters from the specified string, starting at the specified position.</span></span>

## <a name="syntax"></a><span data-ttu-id="7ef4e-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="7ef4e-105">Syntax</span></span>

```
MID (text, starting position, number of characters)
```

## <a name="arguments"></a><span data-ttu-id="7ef4e-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="7ef4e-106">Arguments</span></span>

<span data-ttu-id="7ef4e-107">`text`: *Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="7ef4e-107">`text`: *String*</span></span>

<span data-ttu-id="7ef4e-108">Um valor de *Cadeia de caracteres* que especifica o texto do qual os caracteres devem ser retornados.</span><span class="sxs-lookup"><span data-stu-id="7ef4e-108">A *String* value that specifies the text to return characters from.</span></span>

<span data-ttu-id="7ef4e-109">`starting position`: *Inteiro*</span><span class="sxs-lookup"><span data-stu-id="7ef4e-109">`starting position`: *Integer*</span></span>

<span data-ttu-id="7ef4e-110">Um valor *Inteiro* que especifica a posição do primeiro caractere que deve ser retornado do texto especificado.</span><span class="sxs-lookup"><span data-stu-id="7ef4e-110">An *Integer* value that specifies the position of the first character that must be returned from the specified text.</span></span>

<span data-ttu-id="7ef4e-111">`number of characters`: *Inteiro*</span><span class="sxs-lookup"><span data-stu-id="7ef4e-111">`number of characters`: *Integer*</span></span>

<span data-ttu-id="7ef4e-112">Um valor *Inteiro* que especifica o número de caracteres que deve ser retornado, a partir da posição inicial especificada.</span><span class="sxs-lookup"><span data-stu-id="7ef4e-112">An *Integer* value that specifies the number of characters that must be returned, starting at the specified starting position.</span></span>

## <a name="return-values"></a><span data-ttu-id="7ef4e-113">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="7ef4e-113">Return values</span></span>

<span data-ttu-id="7ef4e-114">*Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="7ef4e-114">*String*</span></span>

<span data-ttu-id="7ef4e-115">O valor de texto resultante.</span><span class="sxs-lookup"><span data-stu-id="7ef4e-115">The resulting text value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="7ef4e-116">Notas de uso</span><span class="sxs-lookup"><span data-stu-id="7ef4e-116">Usage notes</span></span>

<span data-ttu-id="7ef4e-117">Se o valor do argumento `starting position` for menor do que 0 (zero), os caracteres retornados serão contados a partir da primeira posição na cadeia de caracteres especificada.</span><span class="sxs-lookup"><span data-stu-id="7ef4e-117">If the value of the `starting position` argument is less than 0 (zero), the characters that are returned are counted from the first position in the specified string.</span></span>

<span data-ttu-id="7ef4e-118">Se o valor do argumento `starting position` exceder o tamanho da cadeia de caracteres especificada, uma cadeia de caracteres vazia será retornada.</span><span class="sxs-lookup"><span data-stu-id="7ef4e-118">If the value of the `starting position` argument exceeds length of the specified string, an empty string is returned.</span></span>

## <a name="example"></a><span data-ttu-id="7ef4e-119">Exemplo</span><span class="sxs-lookup"><span data-stu-id="7ef4e-119">Example</span></span>

<span data-ttu-id="7ef4e-120">`MID ("Sample", 2, 3)` retorna **"amp"**.</span><span class="sxs-lookup"><span data-stu-id="7ef4e-120">`MID ("Sample", 2, 3)` returns **"amp"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="7ef4e-121">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="7ef4e-121">Additional resources</span></span>

[<span data-ttu-id="7ef4e-122">Funções de texto</span><span class="sxs-lookup"><span data-stu-id="7ef4e-122">Text functions</span></span>](er-functions-category-text.md)