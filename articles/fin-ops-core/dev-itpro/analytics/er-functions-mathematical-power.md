---
title: Função de ER POWER
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) POWER é usada.
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
ms.openlocfilehash: cb768b400e3ddb99e7c8b05905d7a2dd9e4392de
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/20/2019
ms.locfileid: "2915892"
---
# <span data-ttu-id="7bded-103"><a name="POWER">Função de ER POWER</a></span><span class="sxs-lookup"><span data-stu-id="7bded-103"><a name="POWER">POWER ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="7bded-104">A função `POWER` retorna um valor *Real* que representa o resultado da elevação do número positivo especificado à potência especificada.</span><span class="sxs-lookup"><span data-stu-id="7bded-104">The `POWER` function returns a *Real* value that represents the result of raising the specified positive number to the specified power.</span></span>

## <a name="syntax"></a><span data-ttu-id="7bded-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="7bded-105">Syntax</span></span>

```
POWER (number, power)
```

## <a name="arguments"></a><span data-ttu-id="7bded-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="7bded-106">Arguments</span></span>

<span data-ttu-id="7bded-107">`number`: *Real* ou *Inteiro*</span><span class="sxs-lookup"><span data-stu-id="7bded-107">`number`: *Real* or *Integer*</span></span>

<span data-ttu-id="7bded-108">Um valor numérico que deve ser elevado à potência especificada.</span><span class="sxs-lookup"><span data-stu-id="7bded-108">A numeric value that must be raised to the specified power.</span></span>

<span data-ttu-id="7bded-109">`power`: *Real* ou *Inteiro*</span><span class="sxs-lookup"><span data-stu-id="7bded-109">`power`: *Real* or *Integer*</span></span>

<span data-ttu-id="7bded-110">Um valor numérico que representa a potência específica.</span><span class="sxs-lookup"><span data-stu-id="7bded-110">A numeric value that represents the specific power.</span></span>

## <a name="return-values"></a><span data-ttu-id="7bded-111">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="7bded-111">Return values</span></span>

<span data-ttu-id="7bded-112">*Real*</span><span class="sxs-lookup"><span data-stu-id="7bded-112">*Real*</span></span>

<span data-ttu-id="7bded-113">O valor numérico resultante.</span><span class="sxs-lookup"><span data-stu-id="7bded-113">The resulting numeric value.</span></span>

## <a name="example-1"></a><span data-ttu-id="7bded-114">Exemplo 1</span><span class="sxs-lookup"><span data-stu-id="7bded-114">Example 1</span></span>

<span data-ttu-id="7bded-115">`POWER (10, 2)` retorna **100**.</span><span class="sxs-lookup"><span data-stu-id="7bded-115">`POWER (10, 2)` returns **100**.</span></span>

## <a name="example-2"></a><span data-ttu-id="7bded-116">Exemplo 2</span><span class="sxs-lookup"><span data-stu-id="7bded-116">Example 2</span></span>

<span data-ttu-id="7bded-117">`POWER (4, 0.5)` retorna **2**.</span><span class="sxs-lookup"><span data-stu-id="7bded-117">`POWER (4, 0.5)` returns **2**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="7bded-118">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="7bded-118">Additional resources</span></span>

[<span data-ttu-id="7bded-119">Funções matemáticas</span><span class="sxs-lookup"><span data-stu-id="7bded-119">Mathematical functions</span></span>](er-functions-category-mathematical.md)
