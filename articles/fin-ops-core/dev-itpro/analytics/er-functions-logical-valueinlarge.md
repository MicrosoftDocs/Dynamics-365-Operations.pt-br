---
title: Função VALUEINLARGE do ER
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) VALUEINLARGE é usada.
author: NickSelin
manager: kfend
ms.date: 08/17/2020
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
ms.search.validFrom: 2020-08-01
ms.dyn365.ops.version: AX 10.0.14
ms.openlocfilehash: 26a7148a4caa80a191688145bac625bdf0bf83b2
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2020
ms.locfileid: "4686897"
---
# <a name="valueinlarge-er-function"></a><span data-ttu-id="9285c-103">Função VALUEINLARGE do ER</span><span class="sxs-lookup"><span data-stu-id="9285c-103">VALUEINLARGE ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="9285c-104">A função `VALUEINLARGE` determina se a entrada especificada do tipo *Int64* ou *Inteiro* corresponde a qualquer valor de um item especificado na lista especificada.</span><span class="sxs-lookup"><span data-stu-id="9285c-104">The `VALUEINLARGE` function determines whether the specified input of the *Int64* or *Integer* type matches any value of a specified item in the specified list.</span></span> <span data-ttu-id="9285c-105">A função retorna um valor *Booliano* de **TRUE** se a entrada especificada corresponder ao resultado da execução da expressão especificada para pelo menos um registro da lista especificada.</span><span class="sxs-lookup"><span data-stu-id="9285c-105">The function returns a *Boolean* value of **TRUE** if the specified input matches the result of running the specified expression for at least one record of the specified list.</span></span> <span data-ttu-id="9285c-106">Caso contrário, ela retorna um valor *Booliano* de **FALSE**.</span><span class="sxs-lookup"><span data-stu-id="9285c-106">Otherwise, it returns a *Boolean* value of **FALSE**.</span></span> <span data-ttu-id="9285c-107">Para compreender a diferença com a função `VALUEIN`, consulte a seção [Observação de uso](#usage_note) posteriormente neste tópico.</span><span class="sxs-lookup"><span data-stu-id="9285c-107">To understand the difference with the `VALUEIN` function, see the [Usage note](#usage_note) section later in this topic.</span></span>

## <a name="syntax"></a><span data-ttu-id="9285c-108">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="9285c-108">Syntax</span></span>

```vb
VALUEINLARGE (input, list, list item expression)
```

## <a name="arguments"></a><span data-ttu-id="9285c-109">Argumentos</span><span class="sxs-lookup"><span data-stu-id="9285c-109">Arguments</span></span>

<span data-ttu-id="9285c-110">`input`: *Campo*</span><span class="sxs-lookup"><span data-stu-id="9285c-110">`input`: *Field*</span></span>

<span data-ttu-id="9285c-111">O caminho válido de um item da fonte de dados do tipo *Lista de registros*.</span><span class="sxs-lookup"><span data-stu-id="9285c-111">The valid path of a data source item of the *Record list* type.</span></span> <span data-ttu-id="9285c-112">O valor desse item será correspondido.</span><span class="sxs-lookup"><span data-stu-id="9285c-112">The value of this item will be matched.</span></span>

<span data-ttu-id="9285c-113">`list`: *Lista de registros*</span><span class="sxs-lookup"><span data-stu-id="9285c-113">`list`: *Record list*</span></span>

<span data-ttu-id="9285c-114">O caminho válido de uma fonte de dados do tipo *Lista de registros*.</span><span class="sxs-lookup"><span data-stu-id="9285c-114">The valid path of a data source of the *Record list* data type.</span></span>

<span data-ttu-id="9285c-115">`list item expression`: *Expressão*</span><span class="sxs-lookup"><span data-stu-id="9285c-115">`list item expression`: *Expression*</span></span>

<span data-ttu-id="9285c-116">Uma expressão condicional válida que aponta para ou contém um único campo da lista especificada que deve ser usado na correspondência.</span><span class="sxs-lookup"><span data-stu-id="9285c-116">A valid conditional expression that either points to or contains a single field of the specified list that should be used for the matching.</span></span>

## <a name="return-values"></a><span data-ttu-id="9285c-117">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="9285c-117">Return values</span></span>

<span data-ttu-id="9285c-118">*Booleano*</span><span class="sxs-lookup"><span data-stu-id="9285c-118">*Boolean*</span></span>

<span data-ttu-id="9285c-119">O valor *Booliano* resultante.</span><span class="sxs-lookup"><span data-stu-id="9285c-119">The resulting *Boolean* value.</span></span>

## <a name=""></a><span data-ttu-id="9285c-120"><a name="usage_note">Notas de uso</a></span><span class="sxs-lookup"><span data-stu-id="9285c-120"><a name="usage_note">Usage notes</a></span></span>

<span data-ttu-id="9285c-121">Quando a entrada especificada representa um tipo *Int64* ou *Inteiro* de um item da fonte de dados, a chamada para a qual é traduzível para uma instrução SQL direta, a lista especificada é convertida em uma tabela SQL temporária e a correspondência é realizada no banco de dados executando uma única consulta `EXISTS JOIN`.</span><span class="sxs-lookup"><span data-stu-id="9285c-121">When the specified input represents an *Int64* or *Integer* type of a data source item, the call to which is translatable to a direct SQL statement, the specified list is converted to a temporary SQL table and matching is performed in the database by executing a single `EXISTS JOIN` query.</span></span> <span data-ttu-id="9285c-122">Caso contrário, essa função funcionará como a função [`VALUEIN`](er-functions-logical-valuein.md).</span><span class="sxs-lookup"><span data-stu-id="9285c-122">Otherwise, this function works as the [`VALUEIN`](er-functions-logical-valuein.md) function.</span></span>

<span data-ttu-id="9285c-123">Quando a entrada especificada representa um item de fonte de dados criado como um item diferente do tipo *Int64* e *Inteiro*, ocorre um erro no tempo de design informando que a função `VALUEINLARGE` não é aplicável à expressão de ER configurada.</span><span class="sxs-lookup"><span data-stu-id="9285c-123">When the specified input represents a data source item that is designed as an item other than *Int64* and *Integer* type, an error occurs at design time informing you that the `VALUEINLARGE` function is not applicable for the configured ER expression.</span></span>

<span data-ttu-id="9285c-124">Quando expressão da função `VALUEINLARGE` é executada e mais de uma tabela temporária é usada no escopo dessa execução, ocorre um erro de tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="9285c-124">When the `VALUEINLARGE` function expression is executed and more than one temporary table is used in scope of this execution, a runtime error occurs.</span></span>

## <a name="example"></a><span data-ttu-id="9285c-125">Exemplo</span><span class="sxs-lookup"><span data-stu-id="9285c-125">Example</span></span>

<span data-ttu-id="9285c-126">Você define as seguintes fontes de dados no mapeamento de modelo:</span><span class="sxs-lookup"><span data-stu-id="9285c-126">You define the following data sources in your model mapping:</span></span>

- <span data-ttu-id="9285c-127">A fonte de dados **In** do tipo *Registros de tabela*.</span><span class="sxs-lookup"><span data-stu-id="9285c-127">The **In** data source of the *Table records* type.</span></span>
    - <span data-ttu-id="9285c-128">Essa fonte de dados se refere à tabela **Intrastat**.</span><span class="sxs-lookup"><span data-stu-id="9285c-128">This data source refers to the **Intrastat** table.</span></span>
    - <span data-ttu-id="9285c-129">A opção **Interempresarial** é definida como **Não**.</span><span class="sxs-lookup"><span data-stu-id="9285c-129">The **Cross-company** option is set to **No**.</span></span>
- <span data-ttu-id="9285c-130">A fonte de dados **InMemory** do tipo *Campo calculado*.</span><span class="sxs-lookup"><span data-stu-id="9285c-130">The **InMemory** data source of the *Calculated field* type.</span></span>
    - <span data-ttu-id="9285c-131">Essa fonte de dados contém a expressão `WHERE (In, In.Port <> "")`.</span><span class="sxs-lookup"><span data-stu-id="9285c-131">This data source contains the expression `WHERE (In, In.Port <> "")`.</span></span>
- <span data-ttu-id="9285c-132">A fonte de dados **InFiltered** do tipo *Campo calculado*.</span><span class="sxs-lookup"><span data-stu-id="9285c-132">The **InFiltered** data source of the *Calculated field* type.</span></span>
    - <span data-ttu-id="9285c-133">Essa fonte de dados contém a expressão `FILTER (In, VALUEINLARGE(In.RecId, InMemory, InMemory.RecId)`.</span><span class="sxs-lookup"><span data-stu-id="9285c-133">This data source contains the expression `FILTER (In, VALUEINLARGE(In.RecId, InMemory, InMemory.RecId)`.</span></span>

<span data-ttu-id="9285c-134">Quando a fonte de dados **InFiltered** é chamada no contexto da empresa **DEMF**, uma nova tabela temporária é criada no banco de dados do aplicativo, a lista de códigos de identificação de registros coletada na memória é inserida nesta tabela, e a instrução SQL a seguir é gerada para retornar os registros filtrados da **Intrastat**.</span><span class="sxs-lookup"><span data-stu-id="9285c-134">When the data source **InFiltered** is called under the context of the company **DEMF**, a new temporary table is created in the application database, the collected in memory list of record identification codes are inserted to this table, and the following SQL statement is generated to return filtered records of the **Intrastat** table.</span></span>

```xpp
SELECT … from Intrastat T1
WHERE ((T1.PARTITION=?) AND (T1.DATAAREAID IN (N'DEMF'))) AND
EXISTS (SELECT 'x' FROM tempdb."DBO".? T2 WHERE ((T2.PARTITION=?) AND (T1.RecId=T2.RecId)))
```

## <a name="additional-resources"></a><span data-ttu-id="9285c-135">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="9285c-135">Additional resources</span></span>

[<span data-ttu-id="9285c-136">Funções lógicas</span><span class="sxs-lookup"><span data-stu-id="9285c-136">Logical functions</span></span>](er-functions-category-logical.md)

[<span data-ttu-id="9285c-137">Funções VALUEIN</span><span class="sxs-lookup"><span data-stu-id="9285c-137">VALUEIN functions</span></span>](er-functions-logical-valuein.md)
