---
title: Função de ER NOT
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) NOT é usada.
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
ms.openlocfilehash: 9b55b3d8930ece7e2f2925579821ca88749801f7
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/09/2021
ms.locfileid: "5565871"
---
# <a name="not-er-function"></a><span data-ttu-id="0be47-103">Função de ER NOT</span><span class="sxs-lookup"><span data-stu-id="0be47-103">NOT ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="0be47-104">A função `NOT` retorna o valor lógico revertido da condição especificada como um valor *Booliano*.</span><span class="sxs-lookup"><span data-stu-id="0be47-104">The `NOT` function returns the reversed logical value of the specified condition as a *Boolean* value.</span></span>

## <a name="syntax"></a><span data-ttu-id="0be47-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="0be47-105">Syntax</span></span>

```vb
NOT (condition)
```

## <a name="arguments"></a><span data-ttu-id="0be47-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="0be47-106">Arguments</span></span>

<span data-ttu-id="0be47-107">`condition`: *Booliano*</span><span class="sxs-lookup"><span data-stu-id="0be47-107">`condition`: *Boolean*</span></span>

<span data-ttu-id="0be47-108">Uma expressão condicional válida que deve ser revertida.</span><span class="sxs-lookup"><span data-stu-id="0be47-108">A valid conditional expression that must be reversed.</span></span>

## <a name="return-values"></a><span data-ttu-id="0be47-109">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="0be47-109">Return values</span></span>

<span data-ttu-id="0be47-110">*Booleano*</span><span class="sxs-lookup"><span data-stu-id="0be47-110">*Boolean*</span></span>

<span data-ttu-id="0be47-111">O valor *Booliano* resultante.</span><span class="sxs-lookup"><span data-stu-id="0be47-111">The resulting *Boolean* value.</span></span>

## <a name="example"></a><span data-ttu-id="0be47-112">Exemplo</span><span class="sxs-lookup"><span data-stu-id="0be47-112">Example</span></span>

<span data-ttu-id="0be47-113">`NOT (TRUE)` retorna **FALSE**.</span><span class="sxs-lookup"><span data-stu-id="0be47-113">`NOT (TRUE)` returns **FALSE**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="0be47-114">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="0be47-114">Additional resources</span></span>

[<span data-ttu-id="0be47-115">Funções lógicas</span><span class="sxs-lookup"><span data-stu-id="0be47-115">Logical functions</span></span>](er-functions-category-logical.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]