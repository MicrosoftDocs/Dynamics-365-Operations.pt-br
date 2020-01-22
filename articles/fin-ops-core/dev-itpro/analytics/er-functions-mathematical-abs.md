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
ms.openlocfilehash: 9b32c5e8a413be3583177f565e2d4909330ad1e0
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/20/2019
ms.locfileid: "2917088"
---
# <span data-ttu-id="7036e-103"><a name="ABS">Função de ER ABS</a></span><span class="sxs-lookup"><span data-stu-id="7036e-103"><a name="ABS">ABS ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="7036e-104">A função `ABS` retorna o valor absoluto (módulo) do número especificado como um valor *Real*.</span><span class="sxs-lookup"><span data-stu-id="7036e-104">The `ABS` function returns the absolute value (modulus) of the specified number as a *Real* value.</span></span> <span data-ttu-id="7036e-105">Em outras palavras, ela retorna o número sem seu sinal.</span><span class="sxs-lookup"><span data-stu-id="7036e-105">In other words, it returns the number without its sign.</span></span>

## <a name="syntax"></a><span data-ttu-id="7036e-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="7036e-106">Syntax</span></span>

```
ABS (number)
```

## <a name="arguments"></a><span data-ttu-id="7036e-107">Argumentos</span><span class="sxs-lookup"><span data-stu-id="7036e-107">Arguments</span></span>

<span data-ttu-id="7036e-108">`number`: *Real*</span><span class="sxs-lookup"><span data-stu-id="7036e-108">`number`: *Real*</span></span>

<span data-ttu-id="7036e-109">Um valor numérico do qual você deseja obter o módulo.</span><span class="sxs-lookup"><span data-stu-id="7036e-109">A numeric value that you want the modulus of.</span></span>

## <a name="return-values"></a><span data-ttu-id="7036e-110">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="7036e-110">Return values</span></span>

<span data-ttu-id="7036e-111">*Real*</span><span class="sxs-lookup"><span data-stu-id="7036e-111">*Real*</span></span>

<span data-ttu-id="7036e-112">O valor numérico resultante.</span><span class="sxs-lookup"><span data-stu-id="7036e-112">The resulting numeric value.</span></span>

## <a name="example"></a><span data-ttu-id="7036e-113">Exemplo</span><span class="sxs-lookup"><span data-stu-id="7036e-113">Example</span></span>

<span data-ttu-id="7036e-114">`ABS (-1)` retorna **1**.</span><span class="sxs-lookup"><span data-stu-id="7036e-114">`ABS (-1)` returns **1**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="7036e-115">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="7036e-115">Additional resources</span></span>

[<span data-ttu-id="7036e-116">Funções matemáticas</span><span class="sxs-lookup"><span data-stu-id="7036e-116">Mathematical functions</span></span>](er-functions-category-mathematical.md)
