---
title: Função de ER PADLEFT
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) PADLEFT é usada.
author: NickSelin
manager: kfend
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
ms.openlocfilehash: 86957808ca30db87e6f8202c2024d9929969fc3d
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/09/2021
ms.locfileid: "5562676"
---
# <a name="padleft-er-function"></a><span data-ttu-id="f1ef3-103">Função de ER PADLEFT</span><span class="sxs-lookup"><span data-stu-id="f1ef3-103">PADLEFT ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="f1ef3-104">A função `PADLEFT` retorna um valor de *Cadeia de caracteres* do tamanho especificado, em que o início da cadeia de caracteres especificada é preenchido com os caracteres especificados.</span><span class="sxs-lookup"><span data-stu-id="f1ef3-104">The `PADLEFT` function returns a *String* value of the specified length, where the start of the specified string is padded with the specified characters.</span></span>

## <a name="syntax"></a><span data-ttu-id="f1ef3-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="f1ef3-105">Syntax</span></span>

```vb
PADLEFT (text, length, padding chars)
```

## <a name="arguments"></a><span data-ttu-id="f1ef3-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="f1ef3-106">Arguments</span></span>

<span data-ttu-id="f1ef3-107">`text`: *Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="f1ef3-107">`text`: *String*</span></span>

<span data-ttu-id="f1ef3-108">Um valor de *Cadeia de caracteres* que representa o texto original.</span><span class="sxs-lookup"><span data-stu-id="f1ef3-108">A *String* value that represents the original text.</span></span>

<span data-ttu-id="f1ef3-109">`length`: *Inteiro*</span><span class="sxs-lookup"><span data-stu-id="f1ef3-109">`length`: *Integer*</span></span>

<span data-ttu-id="f1ef3-110">Um valor *Inteiro* que representa o número final de caracteres na cadeia de caracteres preenchida.</span><span class="sxs-lookup"><span data-stu-id="f1ef3-110">An *Integer* value that represents the final number of characters in the padded string.</span></span>

<span data-ttu-id="f1ef3-111">`padding chars`: *Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="f1ef3-111">`padding chars`: *String*</span></span>

<span data-ttu-id="f1ef3-112">Os caracteres a serem usados para o preenchimento.</span><span class="sxs-lookup"><span data-stu-id="f1ef3-112">The characters to use for padding.</span></span>

## <a name="return-values"></a><span data-ttu-id="f1ef3-113">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="f1ef3-113">Return values</span></span>

<span data-ttu-id="f1ef3-114">*Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="f1ef3-114">*String*</span></span>

<span data-ttu-id="f1ef3-115">O valor de texto resultante.</span><span class="sxs-lookup"><span data-stu-id="f1ef3-115">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="f1ef3-116">Exemplo</span><span class="sxs-lookup"><span data-stu-id="f1ef3-116">Example</span></span>

<span data-ttu-id="f1ef3-117">`PADLEFT ("1234", 10, "`&nbsp;`")` retorna a cadeia de caracteres de texto **"&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;1234"**.</span><span class="sxs-lookup"><span data-stu-id="f1ef3-117">`PADLEFT ("1234", 10, "`&nbsp;`")` returns the text string **"&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;1234"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="f1ef3-118">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="f1ef3-118">Additional resources</span></span>

[<span data-ttu-id="f1ef3-119">Funções de texto</span><span class="sxs-lookup"><span data-stu-id="f1ef3-119">Text functions</span></span>](er-functions-category-text.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]