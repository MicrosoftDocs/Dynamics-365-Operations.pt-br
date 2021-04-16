---
title: Função VALUE ER
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) VALUE é usada.
author: NickSelin
ms.date: 12/05/2019
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
ms.openlocfilehash: 2252823d98b63d36d9bb195696abef34ac9c98b6
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5752571"
---
# <a name="value-er-function"></a><span data-ttu-id="ca67c-103">Função VALUE ER</span><span class="sxs-lookup"><span data-stu-id="ca67c-103">VALUE ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="ca67c-104">A função `VALUE` retorna um valor Real que é convertido do valor de *Cadeia de caracteres especificado*.</span><span class="sxs-lookup"><span data-stu-id="ca67c-104">The `VALUE` function returns a *Real* value that is converted from the specified string.</span></span>

## <a name="syntax"></a><span data-ttu-id="ca67c-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="ca67c-105">Syntax</span></span>

```vb
VALUE (text)
```

## <a name="arguments"></a><span data-ttu-id="ca67c-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="ca67c-106">Arguments</span></span>

<span data-ttu-id="ca67c-107">`text`: *Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="ca67c-107">`text`: *String*</span></span>

<span data-ttu-id="ca67c-108">Uma cadeia de caracteres deve ser convertida para um valor numérico.</span><span class="sxs-lookup"><span data-stu-id="ca67c-108">A string value that must be converted to a numeric value.</span></span>

## <a name="return-values"></a><span data-ttu-id="ca67c-109">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="ca67c-109">Return values</span></span>

<span data-ttu-id="ca67c-110">*Real*</span><span class="sxs-lookup"><span data-stu-id="ca67c-110">*Real*</span></span>

<span data-ttu-id="ca67c-111">O valor numérico resultante.</span><span class="sxs-lookup"><span data-stu-id="ca67c-111">The resulting numeric value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="ca67c-112">Notas de uso</span><span class="sxs-lookup"><span data-stu-id="ca67c-112">Usage notes</span></span>

<span data-ttu-id="ca67c-113">As vírgulas e os caracteres de ponto (.) são considerados separadores decimais, e um hífen principal (-) é usado como um sinal negativo.</span><span class="sxs-lookup"><span data-stu-id="ca67c-113">Commas and dot characters (.) are considered decimal separators, and a leading hyphen (-) is used as a negative sign.</span></span> <span data-ttu-id="ca67c-114">Uma exceção é gerada no momento de execução da sequência de caracteres especificada contiver outros caracteres não numéricos.</span><span class="sxs-lookup"><span data-stu-id="ca67c-114">An exception is thrown at runtime if the specified string contains other non-numeric characters.</span></span>

## <a name="example-1"></a><span data-ttu-id="ca67c-115">Exemplo 1</span><span class="sxs-lookup"><span data-stu-id="ca67c-115">Example 1</span></span>

<span data-ttu-id="ca67c-116">`VALUE ("1 234,56")` aciona uma exceção.</span><span class="sxs-lookup"><span data-stu-id="ca67c-116">`VALUE ("1 234,56")` throws an exception.</span></span>

## <a name="example-2"></a><span data-ttu-id="ca67c-117">Exemplo 2</span><span class="sxs-lookup"><span data-stu-id="ca67c-117">Example 2</span></span>

<span data-ttu-id="ca67c-118">`VALUE ("1234,56")` retorna **1234.56**.</span><span class="sxs-lookup"><span data-stu-id="ca67c-118">`VALUE ("1234,56")` returns **1234.56**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="ca67c-119">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="ca67c-119">Additional resources</span></span>

[<span data-ttu-id="ca67c-120">Funções de conversão de tipo</span><span class="sxs-lookup"><span data-stu-id="ca67c-120">Type conversion functions</span></span>](er-functions-category-type-conversion.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]