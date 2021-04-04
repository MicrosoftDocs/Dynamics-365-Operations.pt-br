---
title: Função de ER OR
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) OR é usada.
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
ms.openlocfilehash: 7c2f110185330ee1e0cc6dc9ac534ae697e4b19b
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/09/2021
ms.locfileid: "5565847"
---
# <a name="or-er-function"></a><span data-ttu-id="81ece-103">Função de ER OR</span><span class="sxs-lookup"><span data-stu-id="81ece-103">OR ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="81ece-104">A função `OR` retorna um valor *Booliano* de **FALSE** se todas as condições especificadas forem falsas.</span><span class="sxs-lookup"><span data-stu-id="81ece-104">The `OR` function returns a *Boolean* value of **FALSE** if all the specified conditions are false.</span></span> <span data-ttu-id="81ece-105">Se qualquer condição especificada for verdade, a função retorna um valor *Booliano* como **TRUE**.</span><span class="sxs-lookup"><span data-stu-id="81ece-105">If any specified condition is true, the function returns a *Boolean* value of **TRUE**.</span></span>

## <a name="syntax"></a><span data-ttu-id="81ece-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="81ece-106">Syntax</span></span>

```vb
OR (condition 1[, condition 2, …, condition N])
```

## <a name="arguments"></a><span data-ttu-id="81ece-107">Argumentos</span><span class="sxs-lookup"><span data-stu-id="81ece-107">Arguments</span></span>

<span data-ttu-id="81ece-108">`condition 1`: *Booliano*</span><span class="sxs-lookup"><span data-stu-id="81ece-108">`condition 1`: *Boolean*</span></span>

<span data-ttu-id="81ece-109">Uma expressão condicional válida que deve ser testada.</span><span class="sxs-lookup"><span data-stu-id="81ece-109">A valid conditional expression that must be tested.</span></span> <span data-ttu-id="81ece-110">Esse argumento é obrigatório.</span><span class="sxs-lookup"><span data-stu-id="81ece-110">This argument is required.</span></span>

<span data-ttu-id="81ece-111">`condition N`: *Booliano*</span><span class="sxs-lookup"><span data-stu-id="81ece-111">`condition N`: *Boolean*</span></span>

<span data-ttu-id="81ece-112">Uma expressão condicional válida que deve ser testada.</span><span class="sxs-lookup"><span data-stu-id="81ece-112">A valid conditional expression that must be tested.</span></span> <span data-ttu-id="81ece-113">Esses argumentos adicionais são opcionais.</span><span class="sxs-lookup"><span data-stu-id="81ece-113">These additional arguments are optional.</span></span>

## <a name="return-values"></a><span data-ttu-id="81ece-114">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="81ece-114">Return values</span></span>

<span data-ttu-id="81ece-115">*Booleano*</span><span class="sxs-lookup"><span data-stu-id="81ece-115">*Boolean*</span></span>

<span data-ttu-id="81ece-116">O valor *Booliano* resultante.</span><span class="sxs-lookup"><span data-stu-id="81ece-116">The resulting *Boolean* value.</span></span>

## <a name="example"></a><span data-ttu-id="81ece-117">Exemplo</span><span class="sxs-lookup"><span data-stu-id="81ece-117">Example</span></span>

<span data-ttu-id="81ece-118">`OR (1=2, "a"="a")` retorna **TRUE**.</span><span class="sxs-lookup"><span data-stu-id="81ece-118">`OR (1=2, "a"="a")` returns **TRUE**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="81ece-119">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="81ece-119">Additional resources</span></span>

[<span data-ttu-id="81ece-120">Funções lógicas</span><span class="sxs-lookup"><span data-stu-id="81ece-120">Logical functions</span></span>](er-functions-category-logical.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]