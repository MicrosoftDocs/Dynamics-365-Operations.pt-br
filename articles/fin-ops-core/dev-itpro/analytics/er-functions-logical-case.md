---
title: Função de ER CASE
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) CASE é usada.
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
ms.openlocfilehash: f466e3ffe368bf30236060d820621e723106fc1d
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/09/2021
ms.locfileid: "5562460"
---
# <a name="case-er-function"></a><span data-ttu-id="be001-103">Função de ER CASE</span><span class="sxs-lookup"><span data-stu-id="be001-103">CASE ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="be001-104">A função `CASE` avalia o valor da expressão especificada em relação às opções alternativas especificadas e retorna o resultado da primeira opção igual ao valor dessa expressão.</span><span class="sxs-lookup"><span data-stu-id="be001-104">The `CASE` function evaluates the value of the specified expression against the specified alternative options and returns the result of the first option that equals the value of the specified expression.</span></span> <span data-ttu-id="be001-105">Caso contrário, ela retorna o resultado padrão opcional, se um resultado padrão for especificado como o último argumento da função chamada não precedida por uma opção.</span><span class="sxs-lookup"><span data-stu-id="be001-105">Otherwise, it returns the optional default result, if a default result is specified as the last argument of the called function that isn't preceded by an option.</span></span> <span data-ttu-id="be001-106">O valor retornado pode ser um valor de qualquer um dos tipos de dados com suporte.</span><span class="sxs-lookup"><span data-stu-id="be001-106">The value that is returned can be a value of any of the supported data types.</span></span>

## <a name="syntax"></a><span data-ttu-id="be001-107">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="be001-107">Syntax</span></span>

```vb
CASE (expression, option 1, result 1[, option 2, result 2, …, option N, result N, default result])
```

## <a name="arguments"></a><span data-ttu-id="be001-108">Argumentos</span><span class="sxs-lookup"><span data-stu-id="be001-108">Arguments</span></span>

<span data-ttu-id="be001-109">`expression`: *Tipo de dados primitivo* (booliano, numérico ou texto)</span><span class="sxs-lookup"><span data-stu-id="be001-109">`expression`: *Primitive data type* (Boolean, numeric, or text)</span></span>

<span data-ttu-id="be001-110">Uma expressão válida que retorna um valor do tipo de dados primitivo.</span><span class="sxs-lookup"><span data-stu-id="be001-110">A valid expression that returns a value of the primitive data type.</span></span>

<span data-ttu-id="be001-111">`option 1`: *Tipo de dados primitivo* (booliano, numérico ou texto)</span><span class="sxs-lookup"><span data-stu-id="be001-111">`option 1`: *Primitive data type* (Boolean, numeric, or text)</span></span>

<span data-ttu-id="be001-112">Uma expressão válida que retorna um valor do mesmo tipo de dados primitivo que o argumento `expression` da função chamada.</span><span class="sxs-lookup"><span data-stu-id="be001-112">A valid expression that returns a value of the same primitive data type as the `expression` argument of the called function.</span></span> <span data-ttu-id="be001-113">Esse argumento é obrigatório.</span><span class="sxs-lookup"><span data-stu-id="be001-113">This argument is required.</span></span>

<span data-ttu-id="be001-114">`result 1`: *Qualquer um dos tipos de dados com suporte*</span><span class="sxs-lookup"><span data-stu-id="be001-114">`result 1`: *Any of the supported data types*</span></span>

<span data-ttu-id="be001-115">O resultado retornado que corresponde à opção anterior.</span><span class="sxs-lookup"><span data-stu-id="be001-115">The returned result that corresponds to the preceding option.</span></span> <span data-ttu-id="be001-116">Esse argumento é obrigatório.</span><span class="sxs-lookup"><span data-stu-id="be001-116">This argument is required.</span></span>

<span data-ttu-id="be001-117">`option N`: *Tipo de dados primitivo* (booliano, numérico ou texto)</span><span class="sxs-lookup"><span data-stu-id="be001-117">`option N`: *Primitive data type* (Boolean, numeric, or text)</span></span>

<span data-ttu-id="be001-118">Uma expressão válida que retorna um valor do mesmo tipo de dados primitivo que o argumento `expression` da função chamada.</span><span class="sxs-lookup"><span data-stu-id="be001-118">A valid expression that returns a value of the same primitive data type as the `expression` argument of the called function.</span></span> <span data-ttu-id="be001-119">Esse argumento é opcional.</span><span class="sxs-lookup"><span data-stu-id="be001-119">This argument is optional.</span></span>

<span data-ttu-id="be001-120">`result N`: *Qualquer um dos tipos de dados com suporte*</span><span class="sxs-lookup"><span data-stu-id="be001-120">`result N`: *Any of the supported data types*</span></span>

<span data-ttu-id="be001-121">O resultado retornado que corresponde à opção anterior.</span><span class="sxs-lookup"><span data-stu-id="be001-121">The returned result that corresponds to the preceding option.</span></span> <span data-ttu-id="be001-122">Esse argumento é opcional.</span><span class="sxs-lookup"><span data-stu-id="be001-122">This argument is optional.</span></span>

<span data-ttu-id="be001-123">`default result`: *Qualquer um dos tipos de dados com suporte*</span><span class="sxs-lookup"><span data-stu-id="be001-123">`default result`: *Any of the supported data types*</span></span>

<span data-ttu-id="be001-124">O resultado que deve ser retornado se não houver correspondência.</span><span class="sxs-lookup"><span data-stu-id="be001-124">The result that should be returned if there is no match.</span></span> <span data-ttu-id="be001-125">Esse argumento é opcional.</span><span class="sxs-lookup"><span data-stu-id="be001-125">This argument is optional.</span></span>

## <a name="return-values"></a><span data-ttu-id="be001-126">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="be001-126">Return values</span></span>

<span data-ttu-id="be001-127">*Qualquer um dos tipos de dados com suporte*</span><span class="sxs-lookup"><span data-stu-id="be001-127">*Any of the supported data types*</span></span>

<span data-ttu-id="be001-128">O valor resultante de qualquer um dos tipos de dados com suporte.</span><span class="sxs-lookup"><span data-stu-id="be001-128">The resulting value of any of the supported data types.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="be001-129">Notas de uso</span><span class="sxs-lookup"><span data-stu-id="be001-129">Usage notes</span></span>

<span data-ttu-id="be001-130">Uma exceção é gerada no tempo de execução se não houver correspondência e um resultado padrão opcional não estiver definido.</span><span class="sxs-lookup"><span data-stu-id="be001-130">An exception is thrown at runtime if there is no match and an optional default result isn't defined.</span></span>

<span data-ttu-id="be001-131">Todos os resultados devem ser especificados usando o mesmo tipo de dados.</span><span class="sxs-lookup"><span data-stu-id="be001-131">All results must be specified by using the same data type.</span></span> <span data-ttu-id="be001-132">Uma exceção é gerada no momento do design se os tipos de dados dos resultados configurados não forem correspondentes.</span><span class="sxs-lookup"><span data-stu-id="be001-132">An exception is thrown at design time if the data types of the configured results don't match.</span></span>

<span data-ttu-id="be001-133">Se o primeiro valor de resultado e o *N* º valor de resultado forem valores do tipo de dados *Contêiner (registro)* ou *Lista de registros*, o resultado terá somente os campos existentes nos dois valores.</span><span class="sxs-lookup"><span data-stu-id="be001-133">If the first result value and the *N* th result value are values of the *Container (record)* or *Record list* data type, the result has only the fields that exist in both values.</span></span>

## <a name="example"></a><span data-ttu-id="be001-134">Exemplo</span><span class="sxs-lookup"><span data-stu-id="be001-134">Example</span></span>

<span data-ttu-id="be001-135">`CASE( DATETIMEFORMAT( NOW(), "MM"), "10", "WINTER", "11", "WINTER", "12", "WINTER", "")` retorna a cadeia de caracteres **"WINTER"** se a data atual da sessão do aplicativo estiver entre outubro e dezembro.</span><span class="sxs-lookup"><span data-stu-id="be001-135">`CASE( DATETIMEFORMAT( NOW(), "MM"), "10", "WINTER", "11", "WINTER", "12", "WINTER", "")` returns the string **"WINTER"** if the current application session date is between October and December.</span></span> <span data-ttu-id="be001-136">Caso contrário, retorna uma cadeia de caracteres em branco.</span><span class="sxs-lookup"><span data-stu-id="be001-136">Otherwise, it returns a blank string.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="be001-137">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="be001-137">Additional resources</span></span>

[<span data-ttu-id="be001-138">Funções lógicas</span><span class="sxs-lookup"><span data-stu-id="be001-138">Logical functions</span></span>](er-functions-category-logical.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]