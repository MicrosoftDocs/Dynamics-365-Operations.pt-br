---
title: Funções CONTAINS ER
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) CONTAINS é usada.
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
ms.openlocfilehash: 81964681688cebf870bc9b6c59aff0b7fdd82449
ms.sourcegitcommit: 08ac570bece3e4ee4a0f632f51623e328536dfcf
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/08/2021
ms.locfileid: "5557497"
---
# <a name="contains-er-function"></a><span data-ttu-id="0bc87-103">Funções CONTAINS ER</span><span class="sxs-lookup"><span data-stu-id="0bc87-103">CONTAINS ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="0bc87-104">A função `CONTAINS` determina se a entrada especificada contém o texto especificado.</span><span class="sxs-lookup"><span data-stu-id="0bc87-104">The `CONTAINS` function determines whether the specified input contains the specified text.</span></span> <span data-ttu-id="0bc87-105">Ele retorna um valor *Booliano* **TRUE** se a entrada especificada contém o texto especificado.</span><span class="sxs-lookup"><span data-stu-id="0bc87-105">It returns a *Boolean* value of **TRUE** if the specified input contains the specified text.</span></span> <span data-ttu-id="0bc87-106">Caso contrário, ela retorna um valor *Booliano* de **FALSE**.</span><span class="sxs-lookup"><span data-stu-id="0bc87-106">Otherwise, it returns a *Boolean* value of **FALSE**.</span></span>

## <a name="syntax"></a><span data-ttu-id="0bc87-107">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="0bc87-107">Syntax</span></span>

```vb
CONTAINS (input, search text)
```

## <a name="arguments"></a><span data-ttu-id="0bc87-108">Argumentos</span><span class="sxs-lookup"><span data-stu-id="0bc87-108">Arguments</span></span>

<span data-ttu-id="0bc87-109">`input`: *Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="0bc87-109">`input`: *String*</span></span>

<span data-ttu-id="0bc87-110">O caminho válido de um item de uma fonte de dados do tipo *Cadeia de Caracteres* ou uma constante de cadeia de caracteres, o valor que pode conter o segundo argumento.</span><span class="sxs-lookup"><span data-stu-id="0bc87-110">The valid path of an item of a data source of the *String* type or a string constant, the value of which might contain the second argument.</span></span>

<span data-ttu-id="0bc87-111">`search text`: *Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="0bc87-111">`search text`: *String*</span></span>

<span data-ttu-id="0bc87-112">O caminho válido de uma fonte de dados do tipo de dados *Cadeia de Caracteres* ou uma constante de cadeia de caracteres, o valor que pode estar contido no primeiro argumento.</span><span class="sxs-lookup"><span data-stu-id="0bc87-112">The valid path of a data source of the *String* data type or a string constant, the value of which might be contained in the first argument.</span></span>

## <a name="return-values"></a><span data-ttu-id="0bc87-113">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="0bc87-113">Return values</span></span>

<span data-ttu-id="0bc87-114">*Booleano*</span><span class="sxs-lookup"><span data-stu-id="0bc87-114">*Boolean*</span></span>

<span data-ttu-id="0bc87-115">O valor *Booliano* resultante.</span><span class="sxs-lookup"><span data-stu-id="0bc87-115">The resulting *Boolean* value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="0bc87-116">Notas de uso</span><span class="sxs-lookup"><span data-stu-id="0bc87-116">Usage notes</span></span>

<span data-ttu-id="0bc87-117">Esta função pode ser usada para especificar uma expressão de condição da função [FILTER](er-functions-list-filter.md) somente quando o mapeamento relevante é configurado no [Regulatory Configuration Services](../../../finance/localizations/rcs-globalization-feature.md) para acessar o [Microsoft Dataverse](../data-entities/data-integration-cds.md).</span><span class="sxs-lookup"><span data-stu-id="0bc87-117">This function can be used to specify a condition expression of the [FILTER](er-functions-list-filter.md) function only when the relevant mapping is configured in [Regulatory Configuration Services](../../../finance/localizations/rcs-globalization-feature.md) to access [Microsoft Dataverse](../data-entities/data-integration-cds.md).</span></span> <span data-ttu-id="0bc87-118">Caso contrário, uma exceção é lançada no tempo de design.</span><span class="sxs-lookup"><span data-stu-id="0bc87-118">Otherwise, an exception is thrown at design time.</span></span> <span data-ttu-id="0bc87-119">A mensagem recomenda que você use a função [WHERE](er-functions-list-where.md) em vez da função `FILTER`.</span><span class="sxs-lookup"><span data-stu-id="0bc87-119">The message that you receive recommends that you use the [WHERE](er-functions-list-where.md) function instead of the `FILTER` function.</span></span>

## <a name="example-1"></a><span data-ttu-id="0bc87-120">Exemplo 1</span><span class="sxs-lookup"><span data-stu-id="0bc87-120">Example 1</span></span>

<span data-ttu-id="0bc87-121">A expressão `CONTAINS ("abc", "d")` retorna **FALSE**, enquanto a expressão `CONTAINS ("abc", "C")` retorna **TRUE**.</span><span class="sxs-lookup"><span data-stu-id="0bc87-121">The expression `CONTAINS ("abc", "d")` returns **FALSE**, whereas the expression `CONTAINS ("abc", "C")` returns **TRUE**.</span></span>

## <a name="example-2"></a><span data-ttu-id="0bc87-122">Exemplo 2</span><span class="sxs-lookup"><span data-stu-id="0bc87-122">Example 2</span></span>

<span data-ttu-id="0bc87-123">A expressão `CONTAINS (model.InvoiceBase.Customer.PostalAddress.Address, "DEU")` retornará **TRUE** se o valor do campo **Endereço** da fonte de dados do **modelo** contiver a cadeia de caracteres **DEU**.</span><span class="sxs-lookup"><span data-stu-id="0bc87-123">The expression `CONTAINS (model.InvoiceBase.Customer.PostalAddress.Address, "DEU")` returns **TRUE** if the value of the **Address** field of the **model** data source contains the string **DEU**.</span></span> <span data-ttu-id="0bc87-124">Caso contrário, ele retornará **FALSO**.</span><span class="sxs-lookup"><span data-stu-id="0bc87-124">Otherwise, it returns **FALSE**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="0bc87-125">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="0bc87-125">Additional resources</span></span>

[<span data-ttu-id="0bc87-126">Funções lógicas</span><span class="sxs-lookup"><span data-stu-id="0bc87-126">Logical functions</span></span>](er-functions-category-logical.md)
