---
title: Função ENDSWITH ER
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) ENDSWITH é usada.
author: NickSelin
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
ms.openlocfilehash: bdd2f364e2d0b80d3df20592ec827dcabf99a06c
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5745392"
---
# <a name="endswith-er-function"></a><span data-ttu-id="9a22e-103">Função ENDSWITH ER</span><span class="sxs-lookup"><span data-stu-id="9a22e-103">ENDSWITH ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="9a22e-104">A função `ENDSWITH` determina se a entrada especificada termina com o texto especificado.</span><span class="sxs-lookup"><span data-stu-id="9a22e-104">The `ENDSWITH` function determines whether the specified input ends with the specified text.</span></span> <span data-ttu-id="9a22e-105">Ele retorna um valor *Booliano* **TRUE** se a entrada especificada termina com o texto especificado.</span><span class="sxs-lookup"><span data-stu-id="9a22e-105">It returns a *Boolean* value of **TRUE** if the specified input ends with the specified text.</span></span> <span data-ttu-id="9a22e-106">Caso contrário, ela retorna um valor *Booliano* de **FALSE**.</span><span class="sxs-lookup"><span data-stu-id="9a22e-106">Otherwise, it returns a *Boolean* value of **FALSE**.</span></span>

## <a name="syntax"></a><span data-ttu-id="9a22e-107">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="9a22e-107">Syntax</span></span>

```vb
ENDSWITH (input, end text)
```

## <a name="arguments"></a><span data-ttu-id="9a22e-108">Argumentos</span><span class="sxs-lookup"><span data-stu-id="9a22e-108">Arguments</span></span>

<span data-ttu-id="9a22e-109">`input`: *Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="9a22e-109">`input`: *String*</span></span>

<span data-ttu-id="9a22e-110">O caminho válido de um item de uma fonte de dados do tipo *Cadeia de Caracteres* ou uma constante de cadeia de caracteres, o valor que pode terminar com o segundo argumento.</span><span class="sxs-lookup"><span data-stu-id="9a22e-110">The valid path of an item of a data source of the *String* type or a string constant, the value of which might end with the second argument.</span></span>

<span data-ttu-id="9a22e-111">`start text`: *Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="9a22e-111">`start text`: *String*</span></span>

<span data-ttu-id="9a22e-112">O caminho válido de uma fonte de dados do tipo de dados *Cadeia de Caracteres* ou uma constante de cadeia de caracteres, o valor que pode estar no fim do primeiro argumento.</span><span class="sxs-lookup"><span data-stu-id="9a22e-112">The valid path of a data source of the *String* data type or a string constant, the value of which might be at the end of the first argument.</span></span>

## <a name="return-values"></a><span data-ttu-id="9a22e-113">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="9a22e-113">Return values</span></span>

<span data-ttu-id="9a22e-114">*Booleano*</span><span class="sxs-lookup"><span data-stu-id="9a22e-114">*Boolean*</span></span>

<span data-ttu-id="9a22e-115">O valor *Booliano* resultante.</span><span class="sxs-lookup"><span data-stu-id="9a22e-115">The resulting *Boolean* value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="9a22e-116">Notas de uso</span><span class="sxs-lookup"><span data-stu-id="9a22e-116">Usage notes</span></span>

<span data-ttu-id="9a22e-117">Esta função pode ser usada para especificar uma expressão de condição da função [FILTER](er-functions-list-filter.md) somente quando o mapeamento relevante é configurado no [Regulatory Configuration Services](../../../finance/localizations/rcs-globalization-feature.md) para acessar o [Microsoft Dataverse](../data-entities/data-integration-cds.md).</span><span class="sxs-lookup"><span data-stu-id="9a22e-117">This function can be used to specify a condition expression of the [FILTER](er-functions-list-filter.md) function only when the relevant mapping is configured in [Regulatory Configuration Services](../../../finance/localizations/rcs-globalization-feature.md) to access [Microsoft Dataverse](../data-entities/data-integration-cds.md).</span></span> <span data-ttu-id="9a22e-118">Caso contrário, uma exceção é lançada no tempo de design.</span><span class="sxs-lookup"><span data-stu-id="9a22e-118">Otherwise, an exception is thrown at design time.</span></span> <span data-ttu-id="9a22e-119">A mensagem recomenda que você use a função [WHERE](er-functions-list-where.md) em vez da função `FILTER`.</span><span class="sxs-lookup"><span data-stu-id="9a22e-119">The message that you receive recommends that you use the [WHERE](er-functions-list-where.md) function instead of the `FILTER` function.</span></span>

## <a name="example-1"></a><span data-ttu-id="9a22e-120">Exemplo 1</span><span class="sxs-lookup"><span data-stu-id="9a22e-120">Example 1</span></span>

<span data-ttu-id="9a22e-121">A expressão `ENDSWITH ("abc", "d")` retorna **FALSE**, enquanto a expressão `ENDSWITH ("abc", "C")` retorna **TRUE**.</span><span class="sxs-lookup"><span data-stu-id="9a22e-121">The expression `ENDSWITH ("abc", "d")` returns **FALSE**, whereas the expression `ENDSWITH ("abc", "C")` returns **TRUE**.</span></span>

## <a name="example-2"></a><span data-ttu-id="9a22e-122">Exemplo 2</span><span class="sxs-lookup"><span data-stu-id="9a22e-122">Example 2</span></span>

<span data-ttu-id="9a22e-123">A expressão `ENDSWITH (model.InvoiceBase.Customer.PostalAddress.Address, "USA")` retornará **TRUE** se o valor do campo **Endereço** da fonte de dados do **modelo** terminar com a cadeia de caracteres **USA**.</span><span class="sxs-lookup"><span data-stu-id="9a22e-123">The expression `ENDSWITH (model.InvoiceBase.Customer.PostalAddress.Address, "USA")` returns **TRUE** if the value of the **Address** field of the **model** data source ends with the string **USA**.</span></span> <span data-ttu-id="9a22e-124">Caso contrário, ele retornará **FALSO**.</span><span class="sxs-lookup"><span data-stu-id="9a22e-124">Otherwise, it returns **FALSE**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="9a22e-125">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="9a22e-125">Additional resources</span></span>

[<span data-ttu-id="9a22e-126">Funções lógicas</span><span class="sxs-lookup"><span data-stu-id="9a22e-126">Logical functions</span></span>](er-functions-category-logical.md)
