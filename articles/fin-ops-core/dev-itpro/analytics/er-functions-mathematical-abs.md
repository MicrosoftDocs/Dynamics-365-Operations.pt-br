---
title: Função de ER ABS
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) ABS é usada.
author: NickSelin
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
ms.openlocfilehash: 2a3613483d53fb265741b5d6a34a91da443dcef7
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5753135"
---
# <a name="abs-er-function"></a><span data-ttu-id="5f4c0-103">Função de ER ABS</span><span class="sxs-lookup"><span data-stu-id="5f4c0-103">ABS ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="5f4c0-104">A função `ABS` retorna o valor absoluto (módulo) do número especificado como um valor *Real*.</span><span class="sxs-lookup"><span data-stu-id="5f4c0-104">The `ABS` function returns the absolute value (modulus) of the specified number as a *Real* value.</span></span> <span data-ttu-id="5f4c0-105">Em outras palavras, ela retorna o número sem seu sinal.</span><span class="sxs-lookup"><span data-stu-id="5f4c0-105">In other words, it returns the number without its sign.</span></span>

## <a name="syntax"></a><span data-ttu-id="5f4c0-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="5f4c0-106">Syntax</span></span>

```vb
ABS (number)
```

## <a name="arguments"></a><span data-ttu-id="5f4c0-107">Argumentos</span><span class="sxs-lookup"><span data-stu-id="5f4c0-107">Arguments</span></span>

<span data-ttu-id="5f4c0-108">`number`: *Real*</span><span class="sxs-lookup"><span data-stu-id="5f4c0-108">`number`: *Real*</span></span>

<span data-ttu-id="5f4c0-109">Um valor numérico do qual você deseja obter o módulo.</span><span class="sxs-lookup"><span data-stu-id="5f4c0-109">A numeric value that you want the modulus of.</span></span>

## <a name="return-values"></a><span data-ttu-id="5f4c0-110">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="5f4c0-110">Return values</span></span>

<span data-ttu-id="5f4c0-111">*Real*</span><span class="sxs-lookup"><span data-stu-id="5f4c0-111">*Real*</span></span>

<span data-ttu-id="5f4c0-112">O valor numérico resultante.</span><span class="sxs-lookup"><span data-stu-id="5f4c0-112">The resulting numeric value.</span></span>

## <a name="example"></a><span data-ttu-id="5f4c0-113">Exemplo</span><span class="sxs-lookup"><span data-stu-id="5f4c0-113">Example</span></span>

<span data-ttu-id="5f4c0-114">`ABS (-1)` retorna **1**.</span><span class="sxs-lookup"><span data-stu-id="5f4c0-114">`ABS (-1)` returns **1**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="5f4c0-115">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="5f4c0-115">Additional resources</span></span>

[<span data-ttu-id="5f4c0-116">Funções matemáticas</span><span class="sxs-lookup"><span data-stu-id="5f4c0-116">Mathematical functions</span></span>](er-functions-category-mathematical.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]