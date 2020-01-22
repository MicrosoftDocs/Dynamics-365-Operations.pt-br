---
title: Função de ER VALUEIN
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) VALUEIN é usada.
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
ms.openlocfilehash: cb9a387c8b68d0da4dd485116089f1cf4c5ab72c
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/20/2019
ms.locfileid: "2915961"
---
# <span data-ttu-id="0c9f9-103"><a name="VALUEIN">Função de ER VALUEIN</a></span><span class="sxs-lookup"><span data-stu-id="0c9f9-103"><a name="VALUEIN">VALUEIN ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="0c9f9-104">A função `VALUEIN` determina se a entrada especificada corresponde a algum valor de um item especificado na lista especificada.</span><span class="sxs-lookup"><span data-stu-id="0c9f9-104">The `VALUEIN` function determines whether the specified input matches any value of a specified item in the specified list.</span></span> <span data-ttu-id="0c9f9-105">Ela retorna um valor *Booliano* de **TRUE** se a entrada especificada corresponder ao resultado da execução da expressão especificada para pelo menos um registro da lista especificada.</span><span class="sxs-lookup"><span data-stu-id="0c9f9-105">It returns a *Boolean* value of **TRUE** if the specified input matches the result of running the specified expression for at least one record of the specified list.</span></span> <span data-ttu-id="0c9f9-106">Caso contrário, ela retorna um valor *Booliano* de **FALSE**.</span><span class="sxs-lookup"><span data-stu-id="0c9f9-106">Otherwise, it returns a *Boolean* value of **FALSE**.</span></span>

## <a name="syntax"></a><span data-ttu-id="0c9f9-107">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="0c9f9-107">Syntax</span></span>

```
VALUEIN (input, list, list item expression)
```

## <a name="arguments"></a><span data-ttu-id="0c9f9-108">Argumentos</span><span class="sxs-lookup"><span data-stu-id="0c9f9-108">Arguments</span></span>

<span data-ttu-id="0c9f9-109">`input`: *Campo*</span><span class="sxs-lookup"><span data-stu-id="0c9f9-109">`input`: *Field*</span></span>

<span data-ttu-id="0c9f9-110">O caminho válido de um item de uma fonte de dados do tipo *Lista de registros*.</span><span class="sxs-lookup"><span data-stu-id="0c9f9-110">The valid path of an item of a data source of the *Record list* type.</span></span> <span data-ttu-id="0c9f9-111">O valor desse item será correspondido.</span><span class="sxs-lookup"><span data-stu-id="0c9f9-111">The value of this item will be matched.</span></span>

<span data-ttu-id="0c9f9-112">`list`: *Lista de registros*</span><span class="sxs-lookup"><span data-stu-id="0c9f9-112">`list`: *Record list*</span></span>

<span data-ttu-id="0c9f9-113">O caminho válido de uma fonte de dados do tipo *Lista de registros*.</span><span class="sxs-lookup"><span data-stu-id="0c9f9-113">The valid path of a data source of the *Record list* data type.</span></span>

<span data-ttu-id="0c9f9-114">`list item expression`: *Booliano*</span><span class="sxs-lookup"><span data-stu-id="0c9f9-114">`list item expression`: *Boolean*</span></span>

<span data-ttu-id="0c9f9-115">Uma expressão condicional válida que aponta para ou contém um único campo da lista especificada que deve ser usado na correspondência.</span><span class="sxs-lookup"><span data-stu-id="0c9f9-115">A valid conditional expression that either points to or contains a single field of the specified list that should be used for the matching.</span></span>

## <a name="return-values"></a><span data-ttu-id="0c9f9-116">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="0c9f9-116">Return values</span></span>

<span data-ttu-id="0c9f9-117">*Booleano*</span><span class="sxs-lookup"><span data-stu-id="0c9f9-117">*Boolean*</span></span>

<span data-ttu-id="0c9f9-118">O valor *Booliano* resultante.</span><span class="sxs-lookup"><span data-stu-id="0c9f9-118">The resulting *Boolean* value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="0c9f9-119">Notas de uso</span><span class="sxs-lookup"><span data-stu-id="0c9f9-119">Usage notes</span></span>

<span data-ttu-id="0c9f9-120">Em geral, a função `VALUEIN` é convertida em um conjunto de condições **OR**.</span><span class="sxs-lookup"><span data-stu-id="0c9f9-120">In general, the `VALUEIN` function is translated to a set of **OR** conditions.</span></span>

```
(input = list.item1.value) OR (input = list.item2.value) OR …
```

<span data-ttu-id="0c9f9-121">Em alguns casos, ela pode ser convertida em uma instrução SQL de banco de dados usando o operador `EXISTS JOIN`.</span><span class="sxs-lookup"><span data-stu-id="0c9f9-121">In some cases, it can be translated to a database SQL statement by using the `EXISTS JOIN` operator.</span></span>

## <a name="example-1"></a><span data-ttu-id="0c9f9-122">Exemplo 1</span><span class="sxs-lookup"><span data-stu-id="0c9f9-122">Example 1</span></span>

<span data-ttu-id="0c9f9-123">No seu mapeamento de modelo, você define a fonte de dados **Lista** do tipo *Campo calculado*.</span><span class="sxs-lookup"><span data-stu-id="0c9f9-123">In your model mapping, you define the **List** data source of the *Calculated field* type.</span></span> <span data-ttu-id="0c9f9-124">Essa fonte de dados contém a expressão `SPLIT ("a,b,c", ",")`.</span><span class="sxs-lookup"><span data-stu-id="0c9f9-124">This data source contains the expression `SPLIT ("a,b,c", ",")`.</span></span>

<span data-ttu-id="0c9f9-125">Quando uma fonte de dados é chamada, se tiver sido configurada como a expressão `VALUEIN ("B", List, List.Value)`, ela retorna **TRUE**.</span><span class="sxs-lookup"><span data-stu-id="0c9f9-125">When a data source is called, if it has been configured as the `VALUEIN ("B", List, List.Value)` expression, it returns **TRUE**.</span></span> <span data-ttu-id="0c9f9-126">Nesse caso, a função `VALUEIN` é convertida no seguinte conjunto de condições: `(("B" = "a") or ("B" = "b") or ("B" = "c"))`, onde `("B" = "b")` é igual a **TRUE**.</span><span class="sxs-lookup"><span data-stu-id="0c9f9-126">In this case, the `VALUEIN` function is translated to the following set of conditions: `(("B" = "a") or ("B" = "b") or ("B" = "c"))`, where `("B" = "b")` equals **TRUE**.</span></span>

<span data-ttu-id="0c9f9-127">Quando uma fonte de dados é chamada, se tiver sido configurada como a expressão `VALUEIN ("B", List, LEFT(List.Value, 0))`, ela retorna **FALSE**.</span><span class="sxs-lookup"><span data-stu-id="0c9f9-127">When a data source is called, if it has been configured as the `VALUEIN ("B", List, LEFT(List.Value, 0))` expression, it returns **FALSE**.</span></span> <span data-ttu-id="0c9f9-128">Nesse caso, a função `VALUEIN` é convertida na seguinte condição: `("B" = "")`, que não é igual a **TRUE**.</span><span class="sxs-lookup"><span data-stu-id="0c9f9-128">In this case, the `VALUEIN` function is translated to the following condition: `("B" = "")`, which doesn't equal **TRUE**.</span></span>

<span data-ttu-id="0c9f9-129">O limite superior para o número de caracteres no texto dessa condição é de 32.768 caracteres.</span><span class="sxs-lookup"><span data-stu-id="0c9f9-129">The upper limit for the number of characters in the text of such a condition is 32,768 characters.</span></span> <span data-ttu-id="0c9f9-130">Portanto, você não deve criar fontes de dados que possam exceder esse limite no tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="0c9f9-130">Therefore, you should not create data sources that might exceed this limit at runtime.</span></span> <span data-ttu-id="0c9f9-131">Se o limite for excedido, o aplicativo interrompe a execução e uma exceção é gerada.</span><span class="sxs-lookup"><span data-stu-id="0c9f9-131">If the limit is exceeded, the application stops running, and an exception is thrown.</span></span> <span data-ttu-id="0c9f9-132">Por exemplo, essa situação poderá ocorrer se a fonte de dados for configurada como `WHERE (List1, VALUEIN (List1.ID, List2, List2.ID)` e as listas **List1** e **List2** contiverem muitos registros.</span><span class="sxs-lookup"><span data-stu-id="0c9f9-132">For example, this situation can occur if the data source is configured as `WHERE (List1, VALUEIN (List1.ID, List2, List2.ID)`, and the **List1** and **List2** lists contain a large volume of records.</span></span>

<span data-ttu-id="0c9f9-133">Em alguns casos, a função `VALUEIN` é convertida em uma instrução de banco de dados usando o operador `EXISTS JOIN`.</span><span class="sxs-lookup"><span data-stu-id="0c9f9-133">In some cases, the `VALUEIN` function is translated to a database statement by using the `EXISTS JOIN` operator.</span></span> <span data-ttu-id="0c9f9-134">Esse comportamento ocorre quando a função [FILTER](er-functions-list-filter.md) é usada e as seguintes condições são atendidas:</span><span class="sxs-lookup"><span data-stu-id="0c9f9-134">This behavior occurs when the [FILTER](er-functions-list-filter.md) function is used and the following conditions are met:</span></span>

- <span data-ttu-id="0c9f9-135">A opção **SOLICITAR CONSULTA** é desativada para a fonte de dados da função `VALUEIN` que se refere à lista de registros.</span><span class="sxs-lookup"><span data-stu-id="0c9f9-135">The **ASK FOR QUERY** option is turned off for the data source of the `VALUEIN` function that refers to the list of records.</span></span> <span data-ttu-id="0c9f9-136">Nenhuma condição adicional será aplicada a essa fonte de dados no tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="0c9f9-136">No additional conditions will be applied to this data source at runtime.</span></span>
- <span data-ttu-id="0c9f9-137">Nenhuma expressão aninhada é configurada para a fonte de dados da função `VALUEIN` que se refere à lista de registros.</span><span class="sxs-lookup"><span data-stu-id="0c9f9-137">No nested expressions are configured for the data source of the `VALUEIN` function that refers to the list of records.</span></span>
- <span data-ttu-id="0c9f9-138">Um item de lista da função `VALUEIN` se refere a um campo da fonte de dados especificada, não a uma expressão ou um método dessa fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="0c9f9-138">A list item of the `VALUEIN` function refers to a field of the specified data source, not to an expression or method of that data source.</span></span>

<span data-ttu-id="0c9f9-139">Considere usar esta opção em vez da função [WHERE](er-functions-list-where.md) descrita anteriormente neste exemplo.</span><span class="sxs-lookup"><span data-stu-id="0c9f9-139">Consider using this option instead of the [WHERE](er-functions-list-where.md) function that is described earlier in this example.</span></span>

## <a name="example-2"></a><span data-ttu-id="0c9f9-140">Exemplo 2</span><span class="sxs-lookup"><span data-stu-id="0c9f9-140">Example 2</span></span>

<span data-ttu-id="0c9f9-141">Você define as seguintes fontes de dados no mapeamento de modelo:</span><span class="sxs-lookup"><span data-stu-id="0c9f9-141">You define the following data sources in your model mapping:</span></span>

- <span data-ttu-id="0c9f9-142">A fonte de dados **In** do tipo *Registros de tabela*.</span><span class="sxs-lookup"><span data-stu-id="0c9f9-142">The **In** data source of the *Table records* type.</span></span> <span data-ttu-id="0c9f9-143">Essa fonte de dados se refere à tabela Intrastat.</span><span class="sxs-lookup"><span data-stu-id="0c9f9-143">This data source refers to the Intrastat table.</span></span>
- <span data-ttu-id="0c9f9-144">A fonte de dados **Port** do tipo *Registros de tabela*.</span><span class="sxs-lookup"><span data-stu-id="0c9f9-144">The **Port** data source of the *Table records* type.</span></span> <span data-ttu-id="0c9f9-145">Essa fonte de dados se refere à tabela IntrastatPort.</span><span class="sxs-lookup"><span data-stu-id="0c9f9-145">This data source refers to the IntrastatPort table.</span></span>

<span data-ttu-id="0c9f9-146">Quando uma fonte de dados que tenha sido configurada como a expressão `FILTER (In, VALUEIN(In.Port, Port, Port.PortId)` é chamada, a seguinte instrução SQL é gerada para retornar registros filtrados da tabela Intrastat.</span><span class="sxs-lookup"><span data-stu-id="0c9f9-146">When a data source is called that has been configured as the `FILTER (In, VALUEIN(In.Port, Port, Port.PortId)` expression, the following SQL statement is generated to return filtered records of the Intrastat table.</span></span>

```
select … from Intrastat
exists join TableId from IntrastatPort
where IntrastatPort.PortId = Intrastat.Port
```

<span data-ttu-id="0c9f9-147">Para campos **dataAreaId**, a instrução SQL final é gerada usando o operador `IN`.</span><span class="sxs-lookup"><span data-stu-id="0c9f9-147">For **dataAreaId** fields, the final SQL statement is generated by the using `IN` operator.</span></span>

## <a name="example-3"></a><span data-ttu-id="0c9f9-148">Exemplo 3</span><span class="sxs-lookup"><span data-stu-id="0c9f9-148">Example 3</span></span>

<span data-ttu-id="0c9f9-149">Você define as seguintes fontes de dados no mapeamento de modelo:</span><span class="sxs-lookup"><span data-stu-id="0c9f9-149">You define the following data sources in your model mapping:</span></span>

- <span data-ttu-id="0c9f9-150">A fonte de dados **Le** do tipo *Campo calculado*.</span><span class="sxs-lookup"><span data-stu-id="0c9f9-150">The **Le** data source of the *Calculated field* type.</span></span> <span data-ttu-id="0c9f9-151">Essa fonte de dados contém a expressão `SPLIT ("DEMF,GBSI,USMF", ",")`.</span><span class="sxs-lookup"><span data-stu-id="0c9f9-151">This data source contains the expression `SPLIT ("DEMF,GBSI,USMF", ",")`.</span></span>
- <span data-ttu-id="0c9f9-152">A fonte de dados **In** do tipo *Registros de tabela*.</span><span class="sxs-lookup"><span data-stu-id="0c9f9-152">The **In** data source of the *Table records* type.</span></span> <span data-ttu-id="0c9f9-153">Essa fonte de dados se refere à tabela Intrastat e a opção **Interempresarial** é ativada para ela.</span><span class="sxs-lookup"><span data-stu-id="0c9f9-153">This data source refers to the Intrastat table, and the **Cross-company** option is turned on for it.</span></span>

<span data-ttu-id="0c9f9-154">Quando uma fonte de dados que tenha sido configurada como a expressão `FILTER (In, VALUEIN (In.dataAreaId, Le, Le.Value)` é chamada, a instrução SQL final contém a seguinte condição.</span><span class="sxs-lookup"><span data-stu-id="0c9f9-154">When a data source is called that has been configured as the `FILTER (In, VALUEIN (In.dataAreaId, Le, Le.Value)` expression, the final SQL statement contains the following condition.</span></span>

```
Intrastat.dataAreaId IN ('DEMF', 'GBSI', 'USMF')
```

## <a name="additional-resources"></a><span data-ttu-id="0c9f9-155">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="0c9f9-155">Additional resources</span></span>

[<span data-ttu-id="0c9f9-156">Funções lógicas</span><span class="sxs-lookup"><span data-stu-id="0c9f9-156">Logical functions</span></span>](er-functions-category-logical.md)
