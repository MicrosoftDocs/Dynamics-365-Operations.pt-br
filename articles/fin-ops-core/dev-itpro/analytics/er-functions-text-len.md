---
title: Função de ER LEN
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) LEN é usada.
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
ms.openlocfilehash: d6f2a661dd3a85c658ff85f5886d98f665e28718
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/20/2019
ms.locfileid: "2915570"
---
# <span data-ttu-id="8fcc3-103"><a name="LEN">Função de ER LEN</a></span><span class="sxs-lookup"><span data-stu-id="8fcc3-103"><a name="LEN">LEN ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="8fcc3-104">A função `LEN` retorna o número de caracteres na cadeia de caracteres especificada como um valor *Inteiro*.</span><span class="sxs-lookup"><span data-stu-id="8fcc3-104">The `LEN` function returns the number of characters in the specified string as an *Integer* value.</span></span>

## <a name="syntax"></a><span data-ttu-id="8fcc3-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="8fcc3-105">Syntax</span></span>

```
LEN (text)
```

## <a name="arguments"></a><span data-ttu-id="8fcc3-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="8fcc3-106">Arguments</span></span>

<span data-ttu-id="8fcc3-107">`text`: *Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="8fcc3-107">`text`: *String*</span></span>

<span data-ttu-id="8fcc3-108">Um valor de *Cadeia de caracteres* que especifica o texto.</span><span class="sxs-lookup"><span data-stu-id="8fcc3-108">A *String* value that specifies the text.</span></span>

## <a name="return-values"></a><span data-ttu-id="8fcc3-109">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="8fcc3-109">Return values</span></span>

<span data-ttu-id="8fcc3-110">*Inteiro*</span><span class="sxs-lookup"><span data-stu-id="8fcc3-110">*Integer*</span></span>

<span data-ttu-id="8fcc3-111">O valor numérico resultante.</span><span class="sxs-lookup"><span data-stu-id="8fcc3-111">The resulting numeric value.</span></span>

## <a name="example"></a><span data-ttu-id="8fcc3-112">Exemplo</span><span class="sxs-lookup"><span data-stu-id="8fcc3-112">Example</span></span>

<span data-ttu-id="8fcc3-113">`LEN ("Sample")` retorna **6**.</span><span class="sxs-lookup"><span data-stu-id="8fcc3-113">`LEN ("Sample")` returns **6**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="8fcc3-114">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="8fcc3-114">Additional resources</span></span>

[<span data-ttu-id="8fcc3-115">Funções de texto</span><span class="sxs-lookup"><span data-stu-id="8fcc3-115">Text functions</span></span>](er-functions-category-text.md)
