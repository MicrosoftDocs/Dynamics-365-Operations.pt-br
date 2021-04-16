---
title: Função de ER LEN
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) LEN é usada.
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
ms.openlocfilehash: 394e07a7a573cc4462196b17440f8b0547d8dd48
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5746306"
---
# <a name="len-er-function"></a><span data-ttu-id="a21c6-103">Função de ER LEN</span><span class="sxs-lookup"><span data-stu-id="a21c6-103">LEN ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="a21c6-104">A função `LEN` retorna o número de caracteres na cadeia de caracteres especificada como um valor *Inteiro*.</span><span class="sxs-lookup"><span data-stu-id="a21c6-104">The `LEN` function returns the number of characters in the specified string as an *Integer* value.</span></span>

## <a name="syntax"></a><span data-ttu-id="a21c6-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="a21c6-105">Syntax</span></span>

```vb
LEN (text)
```

## <a name="arguments"></a><span data-ttu-id="a21c6-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="a21c6-106">Arguments</span></span>

<span data-ttu-id="a21c6-107">`text`: *Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="a21c6-107">`text`: *String*</span></span>

<span data-ttu-id="a21c6-108">Um valor de *Cadeia de caracteres* que especifica o texto.</span><span class="sxs-lookup"><span data-stu-id="a21c6-108">A *String* value that specifies the text.</span></span>

## <a name="return-values"></a><span data-ttu-id="a21c6-109">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="a21c6-109">Return values</span></span>

<span data-ttu-id="a21c6-110">*Inteiro*</span><span class="sxs-lookup"><span data-stu-id="a21c6-110">*Integer*</span></span>

<span data-ttu-id="a21c6-111">O valor numérico resultante.</span><span class="sxs-lookup"><span data-stu-id="a21c6-111">The resulting numeric value.</span></span>

## <a name="example"></a><span data-ttu-id="a21c6-112">Exemplo</span><span class="sxs-lookup"><span data-stu-id="a21c6-112">Example</span></span>

<span data-ttu-id="a21c6-113">`LEN ("Sample")` retorna **6**.</span><span class="sxs-lookup"><span data-stu-id="a21c6-113">`LEN ("Sample")` returns **6**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="a21c6-114">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="a21c6-114">Additional resources</span></span>

[<span data-ttu-id="a21c6-115">Funções de texto</span><span class="sxs-lookup"><span data-stu-id="a21c6-115">Text functions</span></span>](er-functions-category-text.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]