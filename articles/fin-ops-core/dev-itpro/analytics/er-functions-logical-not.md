---
title: Função de ER NOT
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) NOT é usada.
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
ms.openlocfilehash: b15277dba26dc7864193b11a127944daca6b989f
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/20/2019
ms.locfileid: "2916030"
---
# <span data-ttu-id="9a778-103"><a name="NOT">Função de ER NOT</a></span><span class="sxs-lookup"><span data-stu-id="9a778-103"><a name="NOT">NOT ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="9a778-104">A função `NOT` retorna o valor lógico revertido da condição especificada como um valor *Booliano*.</span><span class="sxs-lookup"><span data-stu-id="9a778-104">The `NOT` function returns the reversed logical value of the specified condition as a *Boolean* value.</span></span>

## <a name="syntax"></a><span data-ttu-id="9a778-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="9a778-105">Syntax</span></span>

```
NOT (condition)
```

## <a name="arguments"></a><span data-ttu-id="9a778-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="9a778-106">Arguments</span></span>

<span data-ttu-id="9a778-107">`condition`: *Booliano*</span><span class="sxs-lookup"><span data-stu-id="9a778-107">`condition`: *Boolean*</span></span>

<span data-ttu-id="9a778-108">Uma expressão condicional válida que deve ser revertida.</span><span class="sxs-lookup"><span data-stu-id="9a778-108">A valid conditional expression that must be reversed.</span></span>

## <a name="return-values"></a><span data-ttu-id="9a778-109">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="9a778-109">Return values</span></span>

<span data-ttu-id="9a778-110">*Booleano*</span><span class="sxs-lookup"><span data-stu-id="9a778-110">*Boolean*</span></span>

<span data-ttu-id="9a778-111">O valor *Booliano* resultante.</span><span class="sxs-lookup"><span data-stu-id="9a778-111">The resulting *Boolean* value.</span></span>

## <a name="example"></a><span data-ttu-id="9a778-112">Exemplo</span><span class="sxs-lookup"><span data-stu-id="9a778-112">Example</span></span>

<span data-ttu-id="9a778-113">`NOT (TRUE)` retorna **FALSE**.</span><span class="sxs-lookup"><span data-stu-id="9a778-113">`NOT (TRUE)` returns **FALSE**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="9a778-114">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="9a778-114">Additional resources</span></span>

[<span data-ttu-id="9a778-115">Funções lógicas</span><span class="sxs-lookup"><span data-stu-id="9a778-115">Logical functions</span></span>](er-functions-category-logical.md)
