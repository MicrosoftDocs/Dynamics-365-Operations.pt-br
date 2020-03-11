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
ms.openlocfilehash: 214fb2808f024487795f27de45de1d4de8cead2d
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/12/2020
ms.locfileid: "3041644"
---
# <span data-ttu-id="b47a6-103"><a name="ABS">Função de ER ABS</a></span><span class="sxs-lookup"><span data-stu-id="b47a6-103"><a name="ABS">ABS ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b47a6-104">A função `ABS` retorna o valor absoluto (módulo) do número especificado como um valor *Real*.</span><span class="sxs-lookup"><span data-stu-id="b47a6-104">The `ABS` function returns the absolute value (modulus) of the specified number as a *Real* value.</span></span> <span data-ttu-id="b47a6-105">Em outras palavras, ela retorna o número sem seu sinal.</span><span class="sxs-lookup"><span data-stu-id="b47a6-105">In other words, it returns the number without its sign.</span></span>

## <a name="syntax"></a><span data-ttu-id="b47a6-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="b47a6-106">Syntax</span></span>

```vb
ABS (number)
```

## <a name="arguments"></a><span data-ttu-id="b47a6-107">Argumentos</span><span class="sxs-lookup"><span data-stu-id="b47a6-107">Arguments</span></span>

<span data-ttu-id="b47a6-108">`number`: *Real*</span><span class="sxs-lookup"><span data-stu-id="b47a6-108">`number`: *Real*</span></span>

<span data-ttu-id="b47a6-109">Um valor numérico do qual você deseja obter o módulo.</span><span class="sxs-lookup"><span data-stu-id="b47a6-109">A numeric value that you want the modulus of.</span></span>

## <a name="return-values"></a><span data-ttu-id="b47a6-110">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="b47a6-110">Return values</span></span>

<span data-ttu-id="b47a6-111">*Real*</span><span class="sxs-lookup"><span data-stu-id="b47a6-111">*Real*</span></span>

<span data-ttu-id="b47a6-112">O valor numérico resultante.</span><span class="sxs-lookup"><span data-stu-id="b47a6-112">The resulting numeric value.</span></span>

## <a name="example"></a><span data-ttu-id="b47a6-113">Exemplo</span><span class="sxs-lookup"><span data-stu-id="b47a6-113">Example</span></span>

<span data-ttu-id="b47a6-114">`ABS (-1)` retorna **1**.</span><span class="sxs-lookup"><span data-stu-id="b47a6-114">`ABS (-1)` returns **1**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="b47a6-115">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="b47a6-115">Additional resources</span></span>

[<span data-ttu-id="b47a6-116">Funções matemáticas</span><span class="sxs-lookup"><span data-stu-id="b47a6-116">Mathematical functions</span></span>](er-functions-category-mathematical.md)
