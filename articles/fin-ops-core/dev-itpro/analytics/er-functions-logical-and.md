---
title: Função de ER AND
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) AND é usada.
author: NickSelin
ms.date: 12/12/2019
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
ms.openlocfilehash: 9851321137b4c7744634df30f85aa3a0b1a0a588
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5745464"
---
# <a name="and-er-function"></a><span data-ttu-id="4ad51-103">Função de ER AND</span><span class="sxs-lookup"><span data-stu-id="4ad51-103">AND ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="4ad51-104">A função `AND` retorna um valor *Booliano* de **TRUE** se todas as condições especificadas forem verdadeiras.</span><span class="sxs-lookup"><span data-stu-id="4ad51-104">The `AND` function returns a *Boolean* value of **TRUE** if all the specified conditions are true.</span></span> <span data-ttu-id="4ad51-105">Caso contrário, ela retorna um valor *Booliano* de **FALSE**.</span><span class="sxs-lookup"><span data-stu-id="4ad51-105">Otherwise, it returns a *Boolean* value of **FALSE**.</span></span>

## <a name="syntax"></a><span data-ttu-id="4ad51-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="4ad51-106">Syntax</span></span>

```vb
AND (condition 1[, condition 2, …, condition N])
```

## <a name="arguments"></a><span data-ttu-id="4ad51-107">Argumentos</span><span class="sxs-lookup"><span data-stu-id="4ad51-107">Arguments</span></span>

<span data-ttu-id="4ad51-108">`condition 1`: *Booliano*</span><span class="sxs-lookup"><span data-stu-id="4ad51-108">`condition 1`: *Boolean*</span></span>

<span data-ttu-id="4ad51-109">Uma expressão condicional válida que deve ser testada.</span><span class="sxs-lookup"><span data-stu-id="4ad51-109">A valid conditional expression that must be tested.</span></span> <span data-ttu-id="4ad51-110">Esse argumento é obrigatório.</span><span class="sxs-lookup"><span data-stu-id="4ad51-110">This argument is required.</span></span>

<span data-ttu-id="4ad51-111">`condition N`: *Booliano*</span><span class="sxs-lookup"><span data-stu-id="4ad51-111">`condition N`: *Boolean*</span></span>

<span data-ttu-id="4ad51-112">Uma expressão condicional válida que deve ser testada.</span><span class="sxs-lookup"><span data-stu-id="4ad51-112">A valid conditional expression that must be tested.</span></span> <span data-ttu-id="4ad51-113">Esses argumentos adicionais são opcionais.</span><span class="sxs-lookup"><span data-stu-id="4ad51-113">These additional arguments are optional.</span></span>

## <a name="return-values"></a><span data-ttu-id="4ad51-114">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="4ad51-114">Return values</span></span>

<span data-ttu-id="4ad51-115">*Booleano*</span><span class="sxs-lookup"><span data-stu-id="4ad51-115">*Boolean*</span></span>

<span data-ttu-id="4ad51-116">O valor *Booliano* resultante.</span><span class="sxs-lookup"><span data-stu-id="4ad51-116">The resulting *Boolean* value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="4ad51-117">Notas de uso</span><span class="sxs-lookup"><span data-stu-id="4ad51-117">Usage notes</span></span>

<span data-ttu-id="4ad51-118">Nos argumentos de funções lógicas, você pode usar referências de fontes de dados, valores numéricos e de texto, valores boolianos, operadores de comparação e outras funções de relatório eletrônico (ER).</span><span class="sxs-lookup"><span data-stu-id="4ad51-118">In the arguments of logical functions, you can use data source references, numeric and text values, Boolean values, comparison operators, and other Electronic reporting (ER) functions.</span></span> <span data-ttu-id="4ad51-119">No entanto, todos os argumentos devem ser avaliados como um valor *Booliano* de **TRUE** ou **FALSE**.</span><span class="sxs-lookup"><span data-stu-id="4ad51-119">However, all the arguments must be evaluated to a *Boolean* value of **TRUE** or **FALSE**.</span></span>

## <a name="example"></a><span data-ttu-id="4ad51-120">Exemplo</span><span class="sxs-lookup"><span data-stu-id="4ad51-120">Example</span></span>

<span data-ttu-id="4ad51-121">`AND (1=1, "a"="a")` retorna **TRUE**.</span><span class="sxs-lookup"><span data-stu-id="4ad51-121">`AND (1=1, "a"="a")` returns **TRUE**.</span></span>

<span data-ttu-id="4ad51-122">`AND (1=2, "a"="a")` retorna **FALSE**.</span><span class="sxs-lookup"><span data-stu-id="4ad51-122">`AND (1=2, "a"="a")` returns **FALSE**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="4ad51-123">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="4ad51-123">Additional resources</span></span>

[<span data-ttu-id="4ad51-124">Funções lógicas</span><span class="sxs-lookup"><span data-stu-id="4ad51-124">Logical functions</span></span>](er-functions-category-logical.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]