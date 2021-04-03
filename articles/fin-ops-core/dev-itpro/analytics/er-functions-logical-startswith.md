---
title: Função STARTSWITH ER
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) STARTSWITH é usada.
author: NickSelin
manager: kfend
ms.date: 02/11/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2021-02-01
ms.dyn365.ops.version: AX 10.0.18
ms.openlocfilehash: 22e99d9e131410820abd12536b8d4f3e868c6863
ms.sourcegitcommit: 08ac570bece3e4ee4a0f632f51623e328536dfcf
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/08/2021
ms.locfileid: "5557498"
---
# <a name="startswith-er-function"></a><span data-ttu-id="94a8e-103">Função STARTSWITH ER</span><span class="sxs-lookup"><span data-stu-id="94a8e-103">STARTSWITH ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="94a8e-104">A função `STARTSWITH` determina se a entrada especificada começa com o texto especificado.</span><span class="sxs-lookup"><span data-stu-id="94a8e-104">The `STARTSWITH` function determines whether the specified input starts with the specified text.</span></span> <span data-ttu-id="94a8e-105">Ele retorna um valor *Booliano* **TRUE** se a entrada especificada começa com o texto especificado.</span><span class="sxs-lookup"><span data-stu-id="94a8e-105">It returns a *Boolean* value of **TRUE** if the specified input starts with the specified text.</span></span> <span data-ttu-id="94a8e-106">Caso contrário, ela retorna um valor *Booliano* de **FALSE**.</span><span class="sxs-lookup"><span data-stu-id="94a8e-106">Otherwise, it returns a *Boolean* value of **FALSE**.</span></span>

## <a name="syntax"></a><span data-ttu-id="94a8e-107">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="94a8e-107">Syntax</span></span>

```vb
STARTSWITH (input, start text)
```

## <a name="arguments"></a><span data-ttu-id="94a8e-108">Argumentos</span><span class="sxs-lookup"><span data-stu-id="94a8e-108">Arguments</span></span>

<span data-ttu-id="94a8e-109">`input`: *Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="94a8e-109">`input`: *String*</span></span>

<span data-ttu-id="94a8e-110">O caminho válido de um item de uma fonte de dados do tipo *Cadeia de Caracteres* ou uma constante de cadeia de caracteres, o valor que pode começar com o segundo argumento.</span><span class="sxs-lookup"><span data-stu-id="94a8e-110">The valid path of an item of a data source of the *String* type or a string constant, the value of which might start with the second argument.</span></span>

<span data-ttu-id="94a8e-111">`start text`: *Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="94a8e-111">`start text`: *String*</span></span>

<span data-ttu-id="94a8e-112">O caminho válido de uma fonte de dados do tipo de dados *Cadeia de Caracteres* ou uma constante de cadeia de caracteres, o valor que pode estar no início do primeiro argumento.</span><span class="sxs-lookup"><span data-stu-id="94a8e-112">The valid path of a data source of the *String* data type or a string constant, the value of which might be at the beginning of the first argument.</span></span>

## <a name="return-values"></a><span data-ttu-id="94a8e-113">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="94a8e-113">Return values</span></span>

<span data-ttu-id="94a8e-114">*Booleano*</span><span class="sxs-lookup"><span data-stu-id="94a8e-114">*Boolean*</span></span>

<span data-ttu-id="94a8e-115">O valor *Booliano* resultante.</span><span class="sxs-lookup"><span data-stu-id="94a8e-115">The resulting *Boolean* value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="94a8e-116">Notas de uso</span><span class="sxs-lookup"><span data-stu-id="94a8e-116">Usage notes</span></span>

<span data-ttu-id="94a8e-117">Esta função pode ser usada para especificar uma expressão de condição da função [FILTER](er-functions-list-filter.md) somente quando o mapeamento relevante é configurado no [Regulatory Configuration Services](../../../finance/localizations/rcs-globalization-feature.md) para acessar o [Microsoft Dataverse](../data-entities/data-integration-cds.md).</span><span class="sxs-lookup"><span data-stu-id="94a8e-117">This function can be used to specify a condition expression of the [FILTER](er-functions-list-filter.md) function only when the relevant mapping is configured in [Regulatory Configuration Services](../../../finance/localizations/rcs-globalization-feature.md) to access [Microsoft Dataverse](../data-entities/data-integration-cds.md).</span></span> <span data-ttu-id="94a8e-118">Caso contrário, uma exceção é lançada no tempo de design.</span><span class="sxs-lookup"><span data-stu-id="94a8e-118">Otherwise, an exception is thrown at design time.</span></span> <span data-ttu-id="94a8e-119">A mensagem recomenda que você use a função [WHERE](er-functions-list-where.md) em vez da função `FILTER`.</span><span class="sxs-lookup"><span data-stu-id="94a8e-119">The message that you receive recommends that you use the [WHERE](er-functions-list-where.md) function instead of the `FILTER` function.</span></span>

## <a name="example-1"></a><span data-ttu-id="94a8e-120">Exemplo 1</span><span class="sxs-lookup"><span data-stu-id="94a8e-120">Example 1</span></span>

<span data-ttu-id="94a8e-121">A expressão `STARTSWITH ("abc", "d")` retorna **FALSE**, enquanto a expressão `STARTSWITH ("abc", "A")` retorna **TRUE**.</span><span class="sxs-lookup"><span data-stu-id="94a8e-121">The expression `STARTSWITH ("abc", "d")` returns **FALSE**, whereas the expression `STARTSWITH ("abc", "A")` returns **TRUE**.</span></span>

## <a name="example-2"></a><span data-ttu-id="94a8e-122">Exemplo 2</span><span class="sxs-lookup"><span data-stu-id="94a8e-122">Example 2</span></span>

<span data-ttu-id="94a8e-123">A expressão `STARTSWITH (model.InvoiceBase.Customer.PostalAddress.Address, "123 Coffee Street")` retornará **TRUE** se o valor do campo **Endereço** da fonte de dados do **modelo** iniciar com a cadeia de caracteres **123 Coffee Street**.</span><span class="sxs-lookup"><span data-stu-id="94a8e-123">The expression `STARTSWITH (model.InvoiceBase.Customer.PostalAddress.Address, "123 Coffee Street")` returns **TRUE** if the value of the **Address** field of the **model** data source starts with the string **123 Coffee Street**.</span></span> <span data-ttu-id="94a8e-124">Caso contrário, ele retornará **FALSO**.</span><span class="sxs-lookup"><span data-stu-id="94a8e-124">Otherwise, it returns **FALSE**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="94a8e-125">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="94a8e-125">Additional resources</span></span>

[<span data-ttu-id="94a8e-126">Funções lógicas</span><span class="sxs-lookup"><span data-stu-id="94a8e-126">Logical functions</span></span>](er-functions-category-logical.md)
