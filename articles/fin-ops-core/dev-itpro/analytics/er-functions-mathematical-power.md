---
title: Função de ER POWER
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) POWER é usada.
author: NickSelin
manager: kfend
ms.date: 12/17/2019
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
ms.openlocfilehash: 9c45e7f9b47a3f0ff4445b1dd160def0ada3a56e
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/09/2021
ms.locfileid: "5570413"
---
# <a name="power-er-function"></a><span data-ttu-id="f5c8d-103">Função de ER POWER</span><span class="sxs-lookup"><span data-stu-id="f5c8d-103">POWER ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="f5c8d-104">A função `POWER` retorna um valor *Real* que representa o resultado da elevação do número positivo especificado à potência especificada.</span><span class="sxs-lookup"><span data-stu-id="f5c8d-104">The `POWER` function returns a *Real* value that represents the result of raising the specified positive number to the specified power.</span></span>

## <a name="syntax"></a><span data-ttu-id="f5c8d-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="f5c8d-105">Syntax</span></span>

```vb
POWER (number, power)
```

## <a name="arguments"></a><span data-ttu-id="f5c8d-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="f5c8d-106">Arguments</span></span>

<span data-ttu-id="f5c8d-107">`number`: *Real* ou *Inteiro*</span><span class="sxs-lookup"><span data-stu-id="f5c8d-107">`number`: *Real* or *Integer*</span></span>

<span data-ttu-id="f5c8d-108">Um valor numérico que deve ser elevado à potência especificada.</span><span class="sxs-lookup"><span data-stu-id="f5c8d-108">A numeric value that must be raised to the specified power.</span></span>

<span data-ttu-id="f5c8d-109">`power`: *Real* ou *Inteiro*</span><span class="sxs-lookup"><span data-stu-id="f5c8d-109">`power`: *Real* or *Integer*</span></span>

<span data-ttu-id="f5c8d-110">Um valor numérico que representa a potência específica.</span><span class="sxs-lookup"><span data-stu-id="f5c8d-110">A numeric value that represents the specific power.</span></span>

## <a name="return-values"></a><span data-ttu-id="f5c8d-111">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="f5c8d-111">Return values</span></span>

<span data-ttu-id="f5c8d-112">*Real*</span><span class="sxs-lookup"><span data-stu-id="f5c8d-112">*Real*</span></span>

<span data-ttu-id="f5c8d-113">O valor numérico resultante.</span><span class="sxs-lookup"><span data-stu-id="f5c8d-113">The resulting numeric value.</span></span>

## <a name="example-1"></a><span data-ttu-id="f5c8d-114">Exemplo 1</span><span class="sxs-lookup"><span data-stu-id="f5c8d-114">Example 1</span></span>

<span data-ttu-id="f5c8d-115">`POWER (10, 2)` retorna **100**.</span><span class="sxs-lookup"><span data-stu-id="f5c8d-115">`POWER (10, 2)` returns **100**.</span></span>

## <a name="example-2"></a><span data-ttu-id="f5c8d-116">Exemplo 2</span><span class="sxs-lookup"><span data-stu-id="f5c8d-116">Example 2</span></span>

<span data-ttu-id="f5c8d-117">`POWER (4, 0.5)` retorna **2**.</span><span class="sxs-lookup"><span data-stu-id="f5c8d-117">`POWER (4, 0.5)` returns **2**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="f5c8d-118">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="f5c8d-118">Additional resources</span></span>

[<span data-ttu-id="f5c8d-119">Funções matemáticas</span><span class="sxs-lookup"><span data-stu-id="f5c8d-119">Mathematical functions</span></span>](er-functions-category-mathematical.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]