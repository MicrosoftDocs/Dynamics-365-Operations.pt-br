---
title: Função de ER ABS
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) ABS é usada.
author: NickSelin
manager: kfend
ms.date: 12/17/2019
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
ms.openlocfilehash: b53535d1a000b72577be5c6284cc4676c43d591b
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/01/2020
ms.locfileid: "3744590"
---
# <a name="abs-er-function"></a><span data-ttu-id="181d8-103">Função de ER ABS</span><span class="sxs-lookup"><span data-stu-id="181d8-103">ABS ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="181d8-104">A função `ABS` retorna o valor absoluto (módulo) do número especificado como um valor *Real*.</span><span class="sxs-lookup"><span data-stu-id="181d8-104">The `ABS` function returns the absolute value (modulus) of the specified number as a *Real* value.</span></span> <span data-ttu-id="181d8-105">Em outras palavras, ela retorna o número sem seu sinal.</span><span class="sxs-lookup"><span data-stu-id="181d8-105">In other words, it returns the number without its sign.</span></span>

## <a name="syntax"></a><span data-ttu-id="181d8-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="181d8-106">Syntax</span></span>

```vb
ABS (number)
```

## <a name="arguments"></a><span data-ttu-id="181d8-107">Argumentos</span><span class="sxs-lookup"><span data-stu-id="181d8-107">Arguments</span></span>

<span data-ttu-id="181d8-108">`number`: *Real*</span><span class="sxs-lookup"><span data-stu-id="181d8-108">`number`: *Real*</span></span>

<span data-ttu-id="181d8-109">Um valor numérico do qual você deseja obter o módulo.</span><span class="sxs-lookup"><span data-stu-id="181d8-109">A numeric value that you want the modulus of.</span></span>

## <a name="return-values"></a><span data-ttu-id="181d8-110">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="181d8-110">Return values</span></span>

<span data-ttu-id="181d8-111">*Real*</span><span class="sxs-lookup"><span data-stu-id="181d8-111">*Real*</span></span>

<span data-ttu-id="181d8-112">O valor numérico resultante.</span><span class="sxs-lookup"><span data-stu-id="181d8-112">The resulting numeric value.</span></span>

## <a name="example"></a><span data-ttu-id="181d8-113">Exemplo</span><span class="sxs-lookup"><span data-stu-id="181d8-113">Example</span></span>

<span data-ttu-id="181d8-114">`ABS (-1)` retorna **1**.</span><span class="sxs-lookup"><span data-stu-id="181d8-114">`ABS (-1)` returns **1**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="181d8-115">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="181d8-115">Additional resources</span></span>

[<span data-ttu-id="181d8-116">Funções matemáticas</span><span class="sxs-lookup"><span data-stu-id="181d8-116">Mathematical functions</span></span>](er-functions-category-mathematical.md)
