---
title: Função de ER VALUEIN
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) VALUEIN é usada.
author: NickSelin
manager: kfend
ms.date: 08/18/2020
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
ms.openlocfilehash: 0a133067ab74c711084cc1d7f456cbe49acdf79d
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2020
ms.locfileid: "4686921"
---
# <a name="valuein-er-function"></a><span data-ttu-id="b8561-103">Função de ER VALUEIN</span><span class="sxs-lookup"><span data-stu-id="b8561-103">VALUEIN ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b8561-104">A função `VALUEIN` determina se a entrada especificada corresponde a algum valor de um item especificado na lista especificada.</span><span class="sxs-lookup"><span data-stu-id="b8561-104">The `VALUEIN` function determines whether the specified input matches any value of a specified item in the specified list.</span></span> <span data-ttu-id="b8561-105">Ela retorna um valor *Booliano* de **TRUE** se a entrada especificada corresponder ao resultado da execução da expressão especificada para pelo menos um registro da lista especificada.</span><span class="sxs-lookup"><span data-stu-id="b8561-105">It returns a *Boolean* value of **TRUE** if the specified input matches the result of running the specified expression for at least one record of the specified list.</span></span> <span data-ttu-id="b8561-106">Caso contrário, ela retorna um valor *Booliano* de **FALSE**.</span><span class="sxs-lookup"><span data-stu-id="b8561-106">Otherwise, it returns a *Boolean* value of **FALSE**.</span></span>

## <a name="syntax"></a><span data-ttu-id="b8561-107">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="b8561-107">Syntax</span></span>

```vb
VALUEIN (input, list, list item expression)
```

## <a name="arguments"></a><span data-ttu-id="b8561-108">Argumentos</span><span class="sxs-lookup"><span data-stu-id="b8561-108">Arguments</span></span>

<span data-ttu-id="b8561-109">`input`: *Campo*</span><span class="sxs-lookup"><span data-stu-id="b8561-109">`input`: *Field*</span></span>

<span data-ttu-id="b8561-110">O caminho válido de um item de uma fonte de dados do tipo *Lista de registros*.</span><span class="sxs-lookup"><span data-stu-id="b8561-110">The valid path of an item of a data source of the *Record list* type.</span></span> <span data-ttu-id="b8561-111">O valor desse item será correspondido.</span><span class="sxs-lookup"><span data-stu-id="b8561-111">The value of this item will be matched.</span></span>

<span data-ttu-id="b8561-112">`list`: *Lista de registros*</span><span class="sxs-lookup"><span data-stu-id="b8561-112">`list`: *Record list*</span></span>

<span data-ttu-id="b8561-113">O caminho válido de uma fonte de dados do tipo *Lista de registros*.</span><span class="sxs-lookup"><span data-stu-id="b8561-113">The valid path of a data source of the *Record list* data type.</span></span>

<span data-ttu-id="b8561-114">`list item expression`: *Booliano*</span><span class="sxs-lookup"><span data-stu-id="b8561-114">`list item expression`: *Boolean*</span></span>

<span data-ttu-id="b8561-115">Uma expressão condicional válida que aponta para ou contém um único campo da lista especificada que deve ser usado na correspondência.</span><span class="sxs-lookup"><span data-stu-id="b8561-115">A valid conditional expression that either points to or contains a single field of the specified list that should be used for the matching.</span></span>

## <a name="return-values"></a><span data-ttu-id="b8561-116">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="b8561-116">Return values</span></span>

<span data-ttu-id="b8561-117">*Booleano*</span><span class="sxs-lookup"><span data-stu-id="b8561-117">*Boolean*</span></span>

<span data-ttu-id="b8561-118">O valor *Booliano* resultante.</span><span class="sxs-lookup"><span data-stu-id="b8561-118">The resulting *Boolean* value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="b8561-119">Notas de uso</span><span class="sxs-lookup"><span data-stu-id="b8561-119">Usage notes</span></span>

<span data-ttu-id="b8561-120">Em geral, a função `VALUEIN` é convertida em um conjunto de condições **OR**.</span><span class="sxs-lookup"><span data-stu-id="b8561-120">In general, the `VALUEIN` function is translated to a set of **OR** conditions.</span></span> <span data-ttu-id="b8561-121">Se a lista de condições **OU** for grande e o tamanho máximo total de uma instrução SQL puder ser excedido, use a função [`VALUEINLARGE`](er-functions-logical-valueinlarge.md).</span><span class="sxs-lookup"><span data-stu-id="b8561-121">If the list of **OR** conditions is large and the maximum total length of an SQL statement might be exceeded, consider using the [`VALUEINLARGE`](er-functions-logical-valueinlarge.md) function.</span></span>

```vb
(input = list.item1.value) OR (input = list.item2.value) OR …
```

<span data-ttu-id="b8561-122">Em alguns casos, ela pode ser convertida em uma instrução SQL de banco de dados usando o operador `EXISTS JOIN`.</span><span class="sxs-lookup"><span data-stu-id="b8561-122">In some cases, it can be translated to a database SQL statement by using the `EXISTS JOIN` operator.</span></span>

## <a name="example-1"></a><span data-ttu-id="b8561-123">Exemplo 1</span><span class="sxs-lookup"><span data-stu-id="b8561-123">Example 1</span></span>

<span data-ttu-id="b8561-124">No seu mapeamento de modelo, você define a fonte de dados **Lista** do tipo *Campo calculado*.</span><span class="sxs-lookup"><span data-stu-id="b8561-124">In your model mapping, you define the **List** data source of the *Calculated field* type.</span></span> <span data-ttu-id="b8561-125">Essa fonte de dados contém a expressão `SPLIT ("a,b,c", ",")`.</span><span class="sxs-lookup"><span data-stu-id="b8561-125">This data source contains the expression `SPLIT ("a,b,c", ",")`.</span></span>

<span data-ttu-id="b8561-126">Quando uma fonte de dados é chamada, se tiver sido configurada como a expressão `VALUEIN ("B", List, List.Value)`, ela retorna **TRUE**.</span><span class="sxs-lookup"><span data-stu-id="b8561-126">When a data source is called, if it has been configured as the `VALUEIN ("B", List, List.Value)` expression, it returns **TRUE**.</span></span> <span data-ttu-id="b8561-127">Nesse caso, a função `VALUEIN` é convertida no seguinte conjunto de condições: `(("B" = "a") or ("B" = "b") or ("B" = "c"))`, onde `("B" = "b")` é igual a **TRUE**.</span><span class="sxs-lookup"><span data-stu-id="b8561-127">In this case, the `VALUEIN` function is translated to the following set of conditions: `(("B" = "a") or ("B" = "b") or ("B" = "c"))`, where `("B" = "b")` equals **TRUE**.</span></span>

<span data-ttu-id="b8561-128">Quando uma fonte de dados é chamada, se tiver sido configurada como a expressão `VALUEIN ("B", List, LEFT(List.Value, 0))`, ela retorna **FALSE**.</span><span class="sxs-lookup"><span data-stu-id="b8561-128">When a data source is called, if it has been configured as the `VALUEIN ("B", List, LEFT(List.Value, 0))` expression, it returns **FALSE**.</span></span> <span data-ttu-id="b8561-129">Nesse caso, a função `VALUEIN` é convertida na seguinte condição: `("B" = "")`, que não é igual a **TRUE**.</span><span class="sxs-lookup"><span data-stu-id="b8561-129">In this case, the `VALUEIN` function is translated to the following condition: `("B" = "")`, which doesn't equal **TRUE**.</span></span>

<span data-ttu-id="b8561-130">O limite superior para o número de caracteres no texto dessa condição é de 32.768 caracteres.</span><span class="sxs-lookup"><span data-stu-id="b8561-130">The upper limit for the number of characters in the text of such a condition is 32,768 characters.</span></span> <span data-ttu-id="b8561-131">Portanto, você não deve criar fontes de dados que possam exceder esse limite no tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="b8561-131">Therefore, you should not create data sources that might exceed this limit at runtime.</span></span> <span data-ttu-id="b8561-132">Se o limite for excedido, o aplicativo interrompe a execução e uma exceção é gerada.</span><span class="sxs-lookup"><span data-stu-id="b8561-132">If the limit is exceeded, the application stops running, and an exception is thrown.</span></span> <span data-ttu-id="b8561-133">Por exemplo, essa situação poderá ocorrer se a fonte de dados for configurada como `WHERE (List1, VALUEIN (List1.ID, List2, List2.ID)` e as listas **List1** e **List2** contiverem muitos registros.</span><span class="sxs-lookup"><span data-stu-id="b8561-133">For example, this situation can occur if the data source is configured as `WHERE (List1, VALUEIN (List1.ID, List2, List2.ID)`, and the **List1** and **List2** lists contain a large volume of records.</span></span>

<span data-ttu-id="b8561-134">Em alguns casos, a função `VALUEIN` é convertida em uma instrução de banco de dados usando o operador `EXISTS JOIN`.</span><span class="sxs-lookup"><span data-stu-id="b8561-134">In some cases, the `VALUEIN` function is translated to a database statement by using the `EXISTS JOIN` operator.</span></span> <span data-ttu-id="b8561-135">Esse comportamento ocorre quando a função [`FILTER`](er-functions-list-filter.md) é usada e as seguintes condições são atendidas:</span><span class="sxs-lookup"><span data-stu-id="b8561-135">This behavior occurs when the [`FILTER`](er-functions-list-filter.md) function is used and the following conditions are met:</span></span>

- <span data-ttu-id="b8561-136">A opção **SOLICITAR CONSULTA** é desativada para a fonte de dados da função `VALUEIN` que se refere à lista de registros.</span><span class="sxs-lookup"><span data-stu-id="b8561-136">The **ASK FOR QUERY** option is turned off for the data source of the `VALUEIN` function that refers to the list of records.</span></span> <span data-ttu-id="b8561-137">Nenhuma condição adicional será aplicada a essa fonte de dados no tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="b8561-137">No additional conditions will be applied to this data source at runtime.</span></span>
- <span data-ttu-id="b8561-138">Nenhuma expressão aninhada é configurada para a fonte de dados da função `VALUEIN` que se refere à lista de registros.</span><span class="sxs-lookup"><span data-stu-id="b8561-138">No nested expressions are configured for the data source of the `VALUEIN` function that refers to the list of records.</span></span>
- <span data-ttu-id="b8561-139">Um item de lista da função `VALUEIN` se refere a um campo da fonte de dados especificada, não a uma expressão ou um método dessa fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="b8561-139">A list item of the `VALUEIN` function refers to a field of the specified data source, not to an expression or method of that data source.</span></span>

<span data-ttu-id="b8561-140">Use esta opção, em vez da função [`WHERE`](er-functions-list-where.md) descrita anteriormente neste exemplo.</span><span class="sxs-lookup"><span data-stu-id="b8561-140">Consider using this option instead of the [`WHERE`](er-functions-list-where.md) function that is described earlier in this example.</span></span>

## <a name="example-2"></a><span data-ttu-id="b8561-141">Exemplo 2</span><span class="sxs-lookup"><span data-stu-id="b8561-141">Example 2</span></span>

<span data-ttu-id="b8561-142">Você define as seguintes fontes de dados no mapeamento de modelo:</span><span class="sxs-lookup"><span data-stu-id="b8561-142">You define the following data sources in your model mapping:</span></span>

- <span data-ttu-id="b8561-143">A fonte de dados **In** do tipo *Registros de tabela*.</span><span class="sxs-lookup"><span data-stu-id="b8561-143">The **In** data source of the *Table records* type.</span></span> <span data-ttu-id="b8561-144">Essa fonte de dados se refere à tabela Intrastat.</span><span class="sxs-lookup"><span data-stu-id="b8561-144">This data source refers to the Intrastat table.</span></span>
- <span data-ttu-id="b8561-145">A fonte de dados **Port** do tipo *Registros de tabela*.</span><span class="sxs-lookup"><span data-stu-id="b8561-145">The **Port** data source of the *Table records* type.</span></span> <span data-ttu-id="b8561-146">Essa fonte de dados se refere à tabela IntrastatPort.</span><span class="sxs-lookup"><span data-stu-id="b8561-146">This data source refers to the IntrastatPort table.</span></span>

<span data-ttu-id="b8561-147">Quando uma fonte de dados que tenha sido configurada como a expressão `FILTER (In, VALUEIN(In.Port, Port, Port.PortId)` é chamada, a seguinte instrução SQL é gerada para retornar registros filtrados da tabela Intrastat.</span><span class="sxs-lookup"><span data-stu-id="b8561-147">When a data source is called that has been configured as the `FILTER (In, VALUEIN(In.Port, Port, Port.PortId)` expression, the following SQL statement is generated to return filtered records of the Intrastat table.</span></span>

```vb
select … from Intrastat
exists join TableId from IntrastatPort
where IntrastatPort.PortId = Intrastat.Port
```

<span data-ttu-id="b8561-148">Para campos **dataAreaId**, a instrução SQL final é gerada usando o operador `IN`.</span><span class="sxs-lookup"><span data-stu-id="b8561-148">For **dataAreaId** fields, the final SQL statement is generated by the using `IN` operator.</span></span>

## <a name="example-3"></a><span data-ttu-id="b8561-149">Exemplo 3</span><span class="sxs-lookup"><span data-stu-id="b8561-149">Example 3</span></span>

<span data-ttu-id="b8561-150">Você define as seguintes fontes de dados no mapeamento de modelo:</span><span class="sxs-lookup"><span data-stu-id="b8561-150">You define the following data sources in your model mapping:</span></span>

- <span data-ttu-id="b8561-151">A fonte de dados **Le** do tipo *Campo calculado*.</span><span class="sxs-lookup"><span data-stu-id="b8561-151">The **Le** data source of the *Calculated field* type.</span></span> <span data-ttu-id="b8561-152">Essa fonte de dados contém a expressão `SPLIT ("DEMF,GBSI,USMF", ",")`.</span><span class="sxs-lookup"><span data-stu-id="b8561-152">This data source contains the expression `SPLIT ("DEMF,GBSI,USMF", ",")`.</span></span>
- <span data-ttu-id="b8561-153">A fonte de dados **In** do tipo *Registros de tabela*.</span><span class="sxs-lookup"><span data-stu-id="b8561-153">The **In** data source of the *Table records* type.</span></span> <span data-ttu-id="b8561-154">Essa fonte de dados se refere à tabela Intrastat e a opção **Interempresarial** é ativada para ela.</span><span class="sxs-lookup"><span data-stu-id="b8561-154">This data source refers to the Intrastat table, and the **Cross-company** option is turned on for it.</span></span>

<span data-ttu-id="b8561-155">Quando uma fonte de dados que tenha sido configurada como a expressão `FILTER (In, VALUEIN (In.dataAreaId, Le, Le.Value)` é chamada, a instrução SQL final contém a seguinte condição.</span><span class="sxs-lookup"><span data-stu-id="b8561-155">When a data source is called that has been configured as the `FILTER (In, VALUEIN (In.dataAreaId, Le, Le.Value)` expression, the final SQL statement contains the following condition.</span></span>

```vb
Intrastat.dataAreaId IN ('DEMF', 'GBSI', 'USMF')
```

## <a name="additional-resources"></a><span data-ttu-id="b8561-156">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="b8561-156">Additional resources</span></span>

[<span data-ttu-id="b8561-157">Funções lógicas</span><span class="sxs-lookup"><span data-stu-id="b8561-157">Logical functions</span></span>](er-functions-category-logical.md)

[<span data-ttu-id="b8561-158">Funções VALUEINLARGE</span><span class="sxs-lookup"><span data-stu-id="b8561-158">VALUEINLARGE functions</span></span>](er-functions-logical-valueinlarge.md)
