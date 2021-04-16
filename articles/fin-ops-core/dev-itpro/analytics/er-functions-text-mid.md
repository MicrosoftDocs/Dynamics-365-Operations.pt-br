---
title: Função de ER MID
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) MID é usada.
author: NickSelin
ms.date: 12/10/2019
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
ms.openlocfilehash: 9a9ff3f1055f6757d6d4073dbb816773d8bfc8ba
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5746258"
---
# <a name="mid-er-function"></a><span data-ttu-id="7637b-103">Função de ER MID</span><span class="sxs-lookup"><span data-stu-id="7637b-103">MID ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="7637b-104">A função `MID` retorna um valor de *Cadeia de caracteres* que apresenta o número de caracteres especificado da cadeia de caracteres especificada, a partir da posição especificada.</span><span class="sxs-lookup"><span data-stu-id="7637b-104">The `MID` function returns a *String* value that presents the specified number of characters from the specified string, starting at the specified position.</span></span>

## <a name="syntax"></a><span data-ttu-id="7637b-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="7637b-105">Syntax</span></span>

```vb
MID (text, starting position, number of characters)
```

## <a name="arguments"></a><span data-ttu-id="7637b-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="7637b-106">Arguments</span></span>

<span data-ttu-id="7637b-107">`text`: *Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="7637b-107">`text`: *String*</span></span>

<span data-ttu-id="7637b-108">Um valor de *Cadeia de caracteres* que especifica o texto do qual os caracteres devem ser retornados.</span><span class="sxs-lookup"><span data-stu-id="7637b-108">A *String* value that specifies the text to return characters from.</span></span>

<span data-ttu-id="7637b-109">`starting position`: *Inteiro*</span><span class="sxs-lookup"><span data-stu-id="7637b-109">`starting position`: *Integer*</span></span>

<span data-ttu-id="7637b-110">Um valor *Inteiro* que especifica a posição do primeiro caractere que deve ser retornado do texto especificado.</span><span class="sxs-lookup"><span data-stu-id="7637b-110">An *Integer* value that specifies the position of the first character that must be returned from the specified text.</span></span>

<span data-ttu-id="7637b-111">`number of characters`: *Inteiro*</span><span class="sxs-lookup"><span data-stu-id="7637b-111">`number of characters`: *Integer*</span></span>

<span data-ttu-id="7637b-112">Um valor *Inteiro* que especifica o número de caracteres que deve ser retornado, a partir da posição inicial especificada.</span><span class="sxs-lookup"><span data-stu-id="7637b-112">An *Integer* value that specifies the number of characters that must be returned, starting at the specified starting position.</span></span>

## <a name="return-values"></a><span data-ttu-id="7637b-113">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="7637b-113">Return values</span></span>

<span data-ttu-id="7637b-114">*Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="7637b-114">*String*</span></span>

<span data-ttu-id="7637b-115">O valor de texto resultante.</span><span class="sxs-lookup"><span data-stu-id="7637b-115">The resulting text value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="7637b-116">Notas de uso</span><span class="sxs-lookup"><span data-stu-id="7637b-116">Usage notes</span></span>

<span data-ttu-id="7637b-117">Se o valor do argumento `starting position` for menor do que 0 (zero), os caracteres retornados serão contados a partir da primeira posição na cadeia de caracteres especificada.</span><span class="sxs-lookup"><span data-stu-id="7637b-117">If the value of the `starting position` argument is less than 0 (zero), the characters that are returned are counted from the first position in the specified string.</span></span>

<span data-ttu-id="7637b-118">Se o valor do argumento `starting position` exceder o tamanho da cadeia de caracteres especificada, uma cadeia de caracteres vazia será retornada.</span><span class="sxs-lookup"><span data-stu-id="7637b-118">If the value of the `starting position` argument exceeds length of the specified string, an empty string is returned.</span></span>

## <a name="example"></a><span data-ttu-id="7637b-119">Exemplo</span><span class="sxs-lookup"><span data-stu-id="7637b-119">Example</span></span>

<span data-ttu-id="7637b-120">`MID ("Sample", 2, 3)` retorna **"amp"**.</span><span class="sxs-lookup"><span data-stu-id="7637b-120">`MID ("Sample", 2, 3)` returns **"amp"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="7637b-121">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="7637b-121">Additional resources</span></span>

[<span data-ttu-id="7637b-122">Funções de texto</span><span class="sxs-lookup"><span data-stu-id="7637b-122">Text functions</span></span>](er-functions-category-text.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]