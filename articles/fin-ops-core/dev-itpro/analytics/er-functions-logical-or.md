---
title: Função de ER OR
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) OR é usada.
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
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 107241dbf9a5127d61343fc1cf42c3bab577adb3
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2020
ms.locfileid: "4686969"
---
# <a name="or-er-function"></a><span data-ttu-id="808ac-103">Função de ER OR</span><span class="sxs-lookup"><span data-stu-id="808ac-103">OR ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="808ac-104">A função `OR` retorna um valor *Booliano* de **FALSE** se todas as condições especificadas forem falsas.</span><span class="sxs-lookup"><span data-stu-id="808ac-104">The `OR` function returns a *Boolean* value of **FALSE** if all the specified conditions are false.</span></span> <span data-ttu-id="808ac-105">Se qualquer condição especificada for verdade, a função retorna um valor *Booliano* como **TRUE**.</span><span class="sxs-lookup"><span data-stu-id="808ac-105">If any specified condition is true, the function returns a *Boolean* value of **TRUE**.</span></span>

## <a name="syntax"></a><span data-ttu-id="808ac-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="808ac-106">Syntax</span></span>

```vb
OR (condition 1[, condition 2, …, condition N])
```

## <a name="arguments"></a><span data-ttu-id="808ac-107">Argumentos</span><span class="sxs-lookup"><span data-stu-id="808ac-107">Arguments</span></span>

<span data-ttu-id="808ac-108">`condition 1`: *Booliano*</span><span class="sxs-lookup"><span data-stu-id="808ac-108">`condition 1`: *Boolean*</span></span>

<span data-ttu-id="808ac-109">Uma expressão condicional válida que deve ser testada.</span><span class="sxs-lookup"><span data-stu-id="808ac-109">A valid conditional expression that must be tested.</span></span> <span data-ttu-id="808ac-110">Esse argumento é obrigatório.</span><span class="sxs-lookup"><span data-stu-id="808ac-110">This argument is required.</span></span>

<span data-ttu-id="808ac-111">`condition N`: *Booliano*</span><span class="sxs-lookup"><span data-stu-id="808ac-111">`condition N`: *Boolean*</span></span>

<span data-ttu-id="808ac-112">Uma expressão condicional válida que deve ser testada.</span><span class="sxs-lookup"><span data-stu-id="808ac-112">A valid conditional expression that must be tested.</span></span> <span data-ttu-id="808ac-113">Esses argumentos adicionais são opcionais.</span><span class="sxs-lookup"><span data-stu-id="808ac-113">These additional arguments are optional.</span></span>

## <a name="return-values"></a><span data-ttu-id="808ac-114">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="808ac-114">Return values</span></span>

<span data-ttu-id="808ac-115">*Booleano*</span><span class="sxs-lookup"><span data-stu-id="808ac-115">*Boolean*</span></span>

<span data-ttu-id="808ac-116">O valor *Booliano* resultante.</span><span class="sxs-lookup"><span data-stu-id="808ac-116">The resulting *Boolean* value.</span></span>

## <a name="example"></a><span data-ttu-id="808ac-117">Exemplo</span><span class="sxs-lookup"><span data-stu-id="808ac-117">Example</span></span>

<span data-ttu-id="808ac-118">`OR (1=2, "a"="a")` retorna **TRUE**.</span><span class="sxs-lookup"><span data-stu-id="808ac-118">`OR (1=2, "a"="a")` returns **TRUE**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="808ac-119">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="808ac-119">Additional resources</span></span>

[<span data-ttu-id="808ac-120">Funções lógicas</span><span class="sxs-lookup"><span data-stu-id="808ac-120">Logical functions</span></span>](er-functions-category-logical.md)
