---
title: Função de ER NUMBERFORMAT
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) NUMBERFORMAT é usada.
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
ms.openlocfilehash: 392135abaf7db05d5ac591ab56312a0e0f6ae5ff
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/20/2019
ms.locfileid: "2916789"
---
# <span data-ttu-id="da210-103"><a name="NUMBERFORMAT">Função de ER NUMBERFORMAT</a></span><span class="sxs-lookup"><span data-stu-id="da210-103"><a name="NUMBERFORMAT">NUMBERFORMAT ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="da210-104">A função `NUMBERFORMAT` retorna um valor de *Cadeia de caracteres* que apresenta o número especificado no formato especificado e em uma [cultura](https://docs.microsoft.com/bingmaps/rest-services/common-parameters-and-types/supported-culture-codes) opcionalmente especificada.</span><span class="sxs-lookup"><span data-stu-id="da210-104">The `NUMBERFORMAT` function returns a *String* value that presents the specified number in the specified format and in an optionally specified [culture](https://docs.microsoft.com/bingmaps/rest-services/common-parameters-and-types/supported-culture-codes).</span></span> <span data-ttu-id="da210-105">Para obter informações sobre os formatos com suporte, consulte [padrão](https://msdn.microsoft.com/library/dwhawy9k(v=vs.110).aspx) e [personalizado](https://msdn.microsoft.com/library/0c899ak8(v=vs.110).aspx).</span><span class="sxs-lookup"><span data-stu-id="da210-105">For information about the supported formats, see [standard](https://msdn.microsoft.com/library/dwhawy9k(v=vs.110).aspx) and [custom](https://msdn.microsoft.com/library/0c899ak8(v=vs.110).aspx).</span></span>

## <a name="syntax-1"></a><span data-ttu-id="da210-106">Sintaxe 1</span><span class="sxs-lookup"><span data-stu-id="da210-106">Syntax 1</span></span>

```
NUMBERFORMAT (number, format)
```

## <a name="syntax-2"></a><span data-ttu-id="da210-107">Sintaxe 2</span><span class="sxs-lookup"><span data-stu-id="da210-107">Syntax 2</span></span>

```
NUMBERFORMAT (number, format, culture)
```

## <a name="arguments"></a><span data-ttu-id="da210-108">Argumentos</span><span class="sxs-lookup"><span data-stu-id="da210-108">Arguments</span></span>

<span data-ttu-id="da210-109">`number`: *Inteiro* ou *Real*</span><span class="sxs-lookup"><span data-stu-id="da210-109">`number`: *Integer* or *Real*</span></span>

<span data-ttu-id="da210-110">Um valor numérico que especifica o número que deve ser formatado.</span><span class="sxs-lookup"><span data-stu-id="da210-110">A numeric value that specifies the number that must be formatted.</span></span>

<span data-ttu-id="da210-111">`format`: *Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="da210-111">`format` : *String*</span></span>

<span data-ttu-id="da210-112">Um valor de *Cadeia de caracteres* que representa o formato.</span><span class="sxs-lookup"><span data-stu-id="da210-112">A *String* value that represents the format.</span></span>

<span data-ttu-id="da210-113">`culture`: *Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="da210-113">`culture`: *String*</span></span>

<span data-ttu-id="da210-114">Um valor de *Cadeia de caracteres* que representa a cultura a ser usada para a formatação.</span><span class="sxs-lookup"><span data-stu-id="da210-114">A *String* value that represents the culture to use for formatting.</span></span>

## <a name="return-values"></a><span data-ttu-id="da210-115">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="da210-115">Return values</span></span>

<span data-ttu-id="da210-116">*Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="da210-116">*String*</span></span>

<span data-ttu-id="da210-117">O valor de texto resultante.</span><span class="sxs-lookup"><span data-stu-id="da210-117">The resulting text value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="da210-118">Notas de uso</span><span class="sxs-lookup"><span data-stu-id="da210-118">Usage notes</span></span>

<span data-ttu-id="da210-119">Se a cultura não estiver definida como um argumento da função chamada, o contexto no qual esta função é executada determinará a cultura usada para formatar números.</span><span class="sxs-lookup"><span data-stu-id="da210-119">If the culture isn't defined as an argument of the called function, the context that this function is run in determines the culture that is used to format numbers.</span></span>

## <a name="example-1"></a><span data-ttu-id="da210-120">Exemplo 1</span><span class="sxs-lookup"><span data-stu-id="da210-120">Example 1</span></span>

<span data-ttu-id="da210-121">Para a cultura **EN-US**, `NUMBERFORMAT (0.45, "p")` retorna **"45.00 %"** e `NUMBERFORMAT (10.45, "#")` retorna **"10"**.</span><span class="sxs-lookup"><span data-stu-id="da210-121">For the **EN-US** culture, `NUMBERFORMAT (0.45, "p")` returns **"45.00 %"**, and `NUMBERFORMAT (10.45, "#")` returns **"10"**.</span></span>

## <a name="example-2"></a><span data-ttu-id="da210-122">Exemplo 2</span><span class="sxs-lookup"><span data-stu-id="da210-122">Example 2</span></span>

<span data-ttu-id="da210-123">`NUMBERFORMAT (10/3, "F2", "de")` retorna **3,33**, enquanto `NUMBERFORMAT (10/3, "F2", "en-us")` retorna **3.33**.</span><span class="sxs-lookup"><span data-stu-id="da210-123">`NUMBERFORMAT (10/3, "F2", "de")` returns **3,33**, whereas `NUMBERFORMAT (10/3, "F2", "en-us")` returns **3.33**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="da210-124">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="da210-124">Additional resources</span></span>

[<span data-ttu-id="da210-125">Funções de texto</span><span class="sxs-lookup"><span data-stu-id="da210-125">Text functions</span></span>](er-functions-category-text.md)