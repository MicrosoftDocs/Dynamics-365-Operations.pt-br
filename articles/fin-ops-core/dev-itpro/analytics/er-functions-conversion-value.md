---
title: Função VALUE ER
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) VALUE é usada.
author: NickSelin
manager: kfend
ms.date: 12/05/2019
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
ms.openlocfilehash: 56b32a802674725347ab496d3a09b99c8f04446d
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2020
ms.locfileid: "4681199"
---
# <a name="value-er-function"></a><span data-ttu-id="68346-103">Função VALUE ER</span><span class="sxs-lookup"><span data-stu-id="68346-103">VALUE ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="68346-104">A função `VALUE` retorna um valor Real que é convertido do valor de *Cadeia de caracteres especificado*.</span><span class="sxs-lookup"><span data-stu-id="68346-104">The `VALUE` function returns a *Real* value that is converted from the specified string.</span></span>

## <a name="syntax"></a><span data-ttu-id="68346-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="68346-105">Syntax</span></span>

```vb
VALUE (text)
```

## <a name="arguments"></a><span data-ttu-id="68346-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="68346-106">Arguments</span></span>

<span data-ttu-id="68346-107">`text`: *Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="68346-107">`text`: *String*</span></span>

<span data-ttu-id="68346-108">Uma cadeia de caracteres deve ser convertida para um valor numérico.</span><span class="sxs-lookup"><span data-stu-id="68346-108">A string value that must be converted to a numeric value.</span></span>

## <a name="return-values"></a><span data-ttu-id="68346-109">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="68346-109">Return values</span></span>

<span data-ttu-id="68346-110">*Real*</span><span class="sxs-lookup"><span data-stu-id="68346-110">*Real*</span></span>

<span data-ttu-id="68346-111">O valor numérico resultante.</span><span class="sxs-lookup"><span data-stu-id="68346-111">The resulting numeric value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="68346-112">Notas de uso</span><span class="sxs-lookup"><span data-stu-id="68346-112">Usage notes</span></span>

<span data-ttu-id="68346-113">As vírgulas e os caracteres de ponto (.) são considerados separadores decimais, e um hífen principal (-) é usado como um sinal negativo.</span><span class="sxs-lookup"><span data-stu-id="68346-113">Commas and dot characters (.) are considered decimal separators, and a leading hyphen (-) is used as a negative sign.</span></span> <span data-ttu-id="68346-114">Uma exceção é gerada no momento de execução da sequência de caracteres especificada contiver outros caracteres não numéricos.</span><span class="sxs-lookup"><span data-stu-id="68346-114">An exception is thrown at runtime if the specified string contains other non-numeric characters.</span></span>

## <a name="example-1"></a><span data-ttu-id="68346-115">Exemplo 1</span><span class="sxs-lookup"><span data-stu-id="68346-115">Example 1</span></span>

<span data-ttu-id="68346-116">`VALUE ("1 234,56")` aciona uma exceção.</span><span class="sxs-lookup"><span data-stu-id="68346-116">`VALUE ("1 234,56")` throws an exception.</span></span>

## <a name="example-2"></a><span data-ttu-id="68346-117">Exemplo 2</span><span class="sxs-lookup"><span data-stu-id="68346-117">Example 2</span></span>

<span data-ttu-id="68346-118">`VALUE ("1234,56")` retorna **1234.56**.</span><span class="sxs-lookup"><span data-stu-id="68346-118">`VALUE ("1234,56")` returns **1234.56**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="68346-119">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="68346-119">Additional resources</span></span>

[<span data-ttu-id="68346-120">Funções de conversão de tipo</span><span class="sxs-lookup"><span data-stu-id="68346-120">Type conversion functions</span></span>](er-functions-category-type-conversion.md)
