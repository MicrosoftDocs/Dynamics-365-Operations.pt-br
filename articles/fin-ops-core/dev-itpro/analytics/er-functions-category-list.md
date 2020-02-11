---
title: Lista de funções ER na categoria de lista
description: Este tópico fornece informações sobre as funções de lista que são compatíveis no relatório eletrônico (ER).
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
ms.openlocfilehash: 9461d0afd75f421cf03ddefed5dac379f1369ec7
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/20/2019
ms.locfileid: "2917755"
---
# <a name="list-of-er-functions-in-the-list-category"></a><span data-ttu-id="45920-103">Lista de funções ER na categoria de lista</span><span class="sxs-lookup"><span data-stu-id="45920-103">List of ER functions in the list category</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="45920-104">As funções de lista de relatório eletrônico (ER) podem ser usadas para extrair informações de e executar operações em, fontes de dados dos tipos de dados *Lista de registros* e *Contêiner (registro)*.</span><span class="sxs-lookup"><span data-stu-id="45920-104">Electronic reporting (ER) list functions can be used to extract information from, and perform operations on, data sources of the *Record list* and *Container (record)* data types.</span></span> <span data-ttu-id="45920-105">Este tópico fornece um resumo dessas funções.</span><span class="sxs-lookup"><span data-stu-id="45920-105">This topic provides a summary of these functions.</span></span>

## <a name="list-of-supported-functions"></a><span data-ttu-id="45920-106">Lista de funções com suporte</span><span class="sxs-lookup"><span data-stu-id="45920-106">List of supported functions</span></span>

| <span data-ttu-id="45920-107">Função</span><span class="sxs-lookup"><span data-stu-id="45920-107">Function</span></span> | <span data-ttu-id="45920-108">Descrição</span><span class="sxs-lookup"><span data-stu-id="45920-108">Description</span></span> |
|----------|-------------|
| [<span data-ttu-id="45920-109">AllItems</span><span class="sxs-lookup"><span data-stu-id="45920-109">AllItems</span></span>](er-functions-list-allitems.md)                 | <span data-ttu-id="45920-110">Essa função é executada como uma seleção na memória.</span><span class="sxs-lookup"><span data-stu-id="45920-110">This function runs as an in-memory selection.</span></span> <span data-ttu-id="45920-111">Ela retorna um novo valor de *Lista de registros* simplificado que consiste em uma lista de registros que representam todos os itens correspondentes ao caminho especificado.</span><span class="sxs-lookup"><span data-stu-id="45920-111">It returns a new flattened *Record list* value that consists of a list of records that represents all items that match the specified path.</span></span> |
| [<span data-ttu-id="45920-112">AllItemsQuery</span><span class="sxs-lookup"><span data-stu-id="45920-112">AllItemsQuery</span></span>](er-functions-list-allitemsquery.md)       | <span data-ttu-id="45920-113">Essa função é executada como uma consulta SQL associada.</span><span class="sxs-lookup"><span data-stu-id="45920-113">This function runs as a joined SQL query.</span></span> <span data-ttu-id="45920-114">Ela retorna um novo valor de *Lista de registros* simplificado que consiste em uma lista de registros que representam todos os itens correspondentes ao caminho especificado.</span><span class="sxs-lookup"><span data-stu-id="45920-114">It returns a new flattened *Record list* value that consists of a list of records that represents all items that match the specified path.</span></span> |
| [<span data-ttu-id="45920-115">Contagem</span><span class="sxs-lookup"><span data-stu-id="45920-115">Count</span></span>](er-functions-list-count.md)                       | <span data-ttu-id="45920-116">Essa função retorna um valor *Inteiro* que representa o número de registros na lista especificada, se a lista não estiver vazia.</span><span class="sxs-lookup"><span data-stu-id="45920-116">This function returns an *Integer* value that represents the number of records in the specified list, if the list isn't empty.</span></span> <span data-ttu-id="45920-117">Se a lista estiver vazia, essa função retornará **0** (zero).</span><span class="sxs-lookup"><span data-stu-id="45920-117">If the list is empty, this function returns **0** (zero).</span></span> |
| [<span data-ttu-id="45920-118">EmptyList</span><span class="sxs-lookup"><span data-stu-id="45920-118">EmptyList</span></span>](er-functions-list-emptylist.md)               | <span data-ttu-id="45920-119">Essa função retorna um valor de *Lista de registros vazio* usando a lista especificada como uma fonte para a estrutura da lista.</span><span class="sxs-lookup"><span data-stu-id="45920-119">This function returns an empty *Record list* value by using the specified list as a source for the list structure.</span></span>|
| [<span data-ttu-id="45920-120">Enumerar</span><span class="sxs-lookup"><span data-stu-id="45920-120">Enumerate</span></span>](er-functions-list-enumerate.md)               | <span data-ttu-id="45920-121">Essa função retorna um novo valor de *Lista de registros* que consiste em registros enumerados da lista especificada.</span><span class="sxs-lookup"><span data-stu-id="45920-121">This function returns a new *Record list* value that consists of enumerated records of the specified list.</span></span> |
| [<span data-ttu-id="45920-122">Filtro</span><span class="sxs-lookup"><span data-stu-id="45920-122">Filter</span></span>](er-functions-list-filter.md)                     | <span data-ttu-id="45920-123">Essa função retorna a lista especificada como um valor de *Lista de registros* após a consulta ser alterada, de forma que ela filtre para a condição especificada.</span><span class="sxs-lookup"><span data-stu-id="45920-123">This function returns the specified list as a *Record list* value after the query has been changed so that it filters for the specified condition.</span></span> |
| [<span data-ttu-id="45920-124">Primeiro</span><span class="sxs-lookup"><span data-stu-id="45920-124">First</span></span>](er-functions-list-first.md)                       | <span data-ttu-id="45920-125">Essa função retorna o primeiro registro da lista especificada como um valor de *Contêiner (registro)*, se essa lista não estiver vazia.</span><span class="sxs-lookup"><span data-stu-id="45920-125">This function returns the first record of the specified list as a *Container (record)* value, if that list isn't empty.</span></span> <span data-ttu-id="45920-126">Se a lista estiver vazia, essa função gerará uma exceção.</span><span class="sxs-lookup"><span data-stu-id="45920-126">If the list is empty, this function throws an exception.</span></span> |
| [<span data-ttu-id="45920-127">FirstOrNull</span><span class="sxs-lookup"><span data-stu-id="45920-127">FirstOrNull</span></span>](er-functions-list-firstornull.md)           | <span data-ttu-id="45920-128">Essa função retorna o primeiro registro da lista especificada como um valor de *Contêiner (registro)*, se esse registro não estiver vazio.</span><span class="sxs-lookup"><span data-stu-id="45920-128">This function returns the first record of the specified list as a *Container (record)* value, if that record isn't empty.</span></span> <span data-ttu-id="45920-129">Se o registro estiver vazio, essa função retornará um valor de *Contêiner (registro)* nulo.</span><span class="sxs-lookup"><span data-stu-id="45920-129">If the record is empty, this function returns a null *Container (record)* value.</span></span> |
| [<span data-ttu-id="45920-130">Índice</span><span class="sxs-lookup"><span data-stu-id="45920-130">Index</span></span>](er-functions-list-index.md)                       | <span data-ttu-id="45920-131">Essa função retorna um valor de *Contêiner (registro)* que é selecionado usando o índice numérico especificado na lista especificada.</span><span class="sxs-lookup"><span data-stu-id="45920-131">This function returns a *Container (record)* value that is selected by using the specified numeric index in the specified list.</span></span> <span data-ttu-id="45920-132">Se o índice estiver fora do intervalo dos registros na lista especificada, essa função gerará uma exceção.</span><span class="sxs-lookup"><span data-stu-id="45920-132">If the index is out of range for the records in the specified list, this function throws an exception.</span></span> |
| [<span data-ttu-id="45920-133">IsEmpty</span><span class="sxs-lookup"><span data-stu-id="45920-133">IsEmpty</span></span>](er-functions-list-isempty.md)                   | <span data-ttu-id="45920-134">Essa função retorna um valor *Booliano* de **TRUE** se a lista especificada não contiver registros.</span><span class="sxs-lookup"><span data-stu-id="45920-134">This function returns a *Boolean* value of **TRUE** if the specified list contains no records.</span></span> <span data-ttu-id="45920-135">Caso contrário, ela retorna um valor *Booliano* de **FALSE**.</span><span class="sxs-lookup"><span data-stu-id="45920-135">Otherwise, it returns a *Boolean* value of **FALSE**.</span></span> |
| [<span data-ttu-id="45920-136">Lista</span><span class="sxs-lookup"><span data-stu-id="45920-136">List</span></span>](er-functions-list-list.md)                         | <span data-ttu-id="45920-137">Essa função retorna um valor de *Lista de registros* que consiste em uma nova lista criada a partir dos argumentos especificados.</span><span class="sxs-lookup"><span data-stu-id="45920-137">This function returns a *Record list* value that consists of a new list that is created from the specified arguments.</span></span>|
| [<span data-ttu-id="45920-138">ListOfFields</span><span class="sxs-lookup"><span data-stu-id="45920-138">ListOfFields</span></span>](er-functions-list-listoffields.md)         | <span data-ttu-id="45920-139">Essa função retorna um valor de *Lista de registros* que é criado com base na estrutura do argumento especificado do tipo *Enumeração* ou *Contêiner (registro)*.</span><span class="sxs-lookup"><span data-stu-id="45920-139">This function returns a *Record list* value that is created based on the structure of the specified argument of the *Enumeration* or *Container (record)* type.</span></span> |
| [<span data-ttu-id="45920-140">ListOfFirstItem</span><span class="sxs-lookup"><span data-stu-id="45920-140">ListOfFirstItem</span></span>](er-functions-list-listoffirstitem.md)   | <span data-ttu-id="45920-141">Essa função retorna um valor de *Lista de registros* que consiste somente no primeiro registro da lista especificada.</span><span class="sxs-lookup"><span data-stu-id="45920-141">This function returns a *Record list* value that consists of only the first record of the specified list.</span></span>|
| [<span data-ttu-id="45920-142">OrderBy</span><span class="sxs-lookup"><span data-stu-id="45920-142">OrderBy</span></span>](er-functions-list-orderby.md)                   | <span data-ttu-id="45920-143">Essa função retorna a lista especificada como um valor de *Lista de registros* após ela ser classificada de acordo com os argumentos especificados.</span><span class="sxs-lookup"><span data-stu-id="45920-143">This function returns the specified list as a *Record list* value after it has been sorted according to the specified arguments.</span></span> <span data-ttu-id="45920-144">Esses argumentos podem ser definidos como expressões.</span><span class="sxs-lookup"><span data-stu-id="45920-144">These arguments can be defined as expressions.</span></span> |
| [<span data-ttu-id="45920-145">Reverter</span><span class="sxs-lookup"><span data-stu-id="45920-145">Reverse</span></span>](er-functions-list-reverse.md)                   | <span data-ttu-id="45920-146">Essa função retorna a lista especificada como um valor de *Lista de registros* na ordem de classificação inversa.</span><span class="sxs-lookup"><span data-stu-id="45920-146">This function returns the specified list as a *Record list* value in reversed sort order.</span></span> |
| [<span data-ttu-id="45920-147">Dividir</span><span class="sxs-lookup"><span data-stu-id="45920-147">Split</span></span>](er-functions-list-split.md)                       | <span data-ttu-id="45920-148">Essa função divide a cadeia de caracteres de entrada especificada em subcadeias de caracteres e retorna o resultado como um novo valor de *Lista de registros*.</span><span class="sxs-lookup"><span data-stu-id="45920-148">This function splits the specified input string into substrings and returns the result as a new *Record list* value.</span></span> |
| [<span data-ttu-id="45920-149">SplitList</span><span class="sxs-lookup"><span data-stu-id="45920-149">SplitList</span></span>](er-functions-list-splitlist.md)               | <span data-ttu-id="45920-150">Essa função divide a lista especificada em sublistas (ou lotes) e cada uma delas contém o número de registros especificado.</span><span class="sxs-lookup"><span data-stu-id="45920-150">This function splits the specified list into sublists (or batches), each of which contains the specified number of records.</span></span> <span data-ttu-id="45920-151">Em seguida, ela retorna o resultado como um novo valor de *Lista de registros* que consiste nos lotes.</span><span class="sxs-lookup"><span data-stu-id="45920-151">It then returns the result as a new *Record list* value that consists of the batches.</span></span> |
| [<span data-ttu-id="45920-152">SplitListByLimit</span><span class="sxs-lookup"><span data-stu-id="45920-152">SplitListByLimit</span></span>](er-functions-list-splitlistbylimit.md) | <span data-ttu-id="45920-153">Essa função divide a lista especificada em uma nova lista de sublistas (lotes).</span><span class="sxs-lookup"><span data-stu-id="45920-153">This function splits the specified list into a new list of sublists (batches).</span></span> <span data-ttu-id="45920-154">O número de registros em cada lote é calculado dinamicamente.</span><span class="sxs-lookup"><span data-stu-id="45920-154">The number of records in each batch is dynamically calculated.</span></span> <span data-ttu-id="45920-155">Em seguida, a função retorna o resultado como um novo valor de *Lista de registros* que consiste nos lotes.</span><span class="sxs-lookup"><span data-stu-id="45920-155">The function then returns the result as a new *Record list* value that consists of the batches.</span></span> |
| [<span data-ttu-id="45920-156">StringJoin</span><span class="sxs-lookup"><span data-stu-id="45920-156">StringJoin</span></span>](er-functions-list-stringjoin.md)             | <span data-ttu-id="45920-157">Essa função retorna um valor de *Cadeia de caracteres* que consiste em valores concatenados do campo especificado da lista especificada.</span><span class="sxs-lookup"><span data-stu-id="45920-157">This function returns a *String* value that consists of concatenated values of the specified field from the specified list.</span></span> <span data-ttu-id="45920-158">Os valores podem ser separados pelo delimitador especificado.</span><span class="sxs-lookup"><span data-stu-id="45920-158">The values can be separated by the specified delimiter.</span></span> |
| [<span data-ttu-id="45920-159">Onde</span><span class="sxs-lookup"><span data-stu-id="45920-159">Where</span></span>](er-functions-list-where.md)                       | <span data-ttu-id="45920-160">Essa função retorna a lista especificada como um valor de *Lista de registros* após ser filtrada de acordo com a condição especificada.</span><span class="sxs-lookup"><span data-stu-id="45920-160">This function returns the specified list as a *Record list* value after it has been filtered according to the specified condition.</span></span> |

## <a name="additional-resources"></a><span data-ttu-id="45920-161">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="45920-161">Additional resources</span></span>

[<span data-ttu-id="45920-162">Visão geral do Relatório Eletrônico</span><span class="sxs-lookup"><span data-stu-id="45920-162">Electronic Reporting overview</span></span>](general-electronic-reporting.md)

[<span data-ttu-id="45920-163">Designer de fórmulas no Relatório eletrônico</span><span class="sxs-lookup"><span data-stu-id="45920-163">Formula designer in Electronic reporting</span></span>](general-electronic-reporting-formula-designer.md)

[<span data-ttu-id="45920-164">Linguagem da fórmula de relatório eletrônico</span><span class="sxs-lookup"><span data-stu-id="45920-164">Electronic reporting formula language</span></span>](er-formula-language.md)