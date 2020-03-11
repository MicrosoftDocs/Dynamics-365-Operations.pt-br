---
title: Função de ER UPPER
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) UPPER é usada.
author: NickSelin
manager: kfend
ms.date: 12/05/2019
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
ms.openlocfilehash: 77854d645ba5b65a2819437af510fcd67be6d99d
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/12/2020
ms.locfileid: "3040931"
---
# <span data-ttu-id="eeed9-103"><a name="UPPER">Função de ER UPPER</a></span><span class="sxs-lookup"><span data-stu-id="eeed9-103"><a name="UPPER">UPPER ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="eeed9-104">A função `UPPER` retorna a cadeia de caracteres de texto especificada como um valor de *Cadeia de caracteres* após ela ser convertida em letras maiúsculas.</span><span class="sxs-lookup"><span data-stu-id="eeed9-104">The `UPPER` function returns the specified text string as a *String* value after it has been converted to uppercase letters.</span></span>

## <a name="syntax"></a><span data-ttu-id="eeed9-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="eeed9-105">Syntax</span></span>

```vb
UPPER (text )
```

## <a name="arguments"></a><span data-ttu-id="eeed9-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="eeed9-106">Arguments</span></span>

<span data-ttu-id="eeed9-107">`text`: *Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="eeed9-107">`text`: *String*</span></span>

<span data-ttu-id="eeed9-108">O caminho válido de uma fonte de dados do tipo *Cadeia de caracteres*.</span><span class="sxs-lookup"><span data-stu-id="eeed9-108">The valid path of a data source of the *String* type.</span></span>

## <a name="return-values"></a><span data-ttu-id="eeed9-109">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="eeed9-109">Return values</span></span>

<span data-ttu-id="eeed9-110">*Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="eeed9-110">*String*</span></span>

<span data-ttu-id="eeed9-111">O valor de texto resultante.</span><span class="sxs-lookup"><span data-stu-id="eeed9-111">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="eeed9-112">Exemplo</span><span class="sxs-lookup"><span data-stu-id="eeed9-112">Example</span></span>

<span data-ttu-id="eeed9-113">`UPPER ("Sample")` retorna **"SAMPLE"**.</span><span class="sxs-lookup"><span data-stu-id="eeed9-113">`UPPER ("Sample")` returns **"SAMPLE"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="eeed9-114">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="eeed9-114">Additional resources</span></span>

[<span data-ttu-id="eeed9-115">Funções de texto</span><span class="sxs-lookup"><span data-stu-id="eeed9-115">Text functions</span></span>](er-functions-category-text.md)
