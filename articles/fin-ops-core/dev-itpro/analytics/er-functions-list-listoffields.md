---
title: Função de ER LISTOFFIELDS
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) LISTOFFIELDS é usada.
author: NickSelin
manager: kfend
ms.date: 12/12/2019
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
ms.openlocfilehash: 91e4658043278b9b8d73766cc0deac5d50d51a59
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/20/2019
ms.locfileid: "2916145"
---
# <span data-ttu-id="5690c-103"><a name="LISTOFFIELDS">Função de ER LISTOFFIELDS</a></span><span class="sxs-lookup"><span data-stu-id="5690c-103"><a name="LISTOFFIELDS">LISTOFFIELDS ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="5690c-104">A função `LISTOFFIELDS` retorna um valor de *Lista de registros* que é criado com base na estrutura do argumento especificado do tipo *Enumeração* ou *Contêiner (registro)*.</span><span class="sxs-lookup"><span data-stu-id="5690c-104">The `LISTOFFIELDS` function returns a *Record list* value that is created based on the structure of the specified argument of the *Enumeration* or *Container (record)* type.</span></span>

## <a name="syntax-1"></a><span data-ttu-id="5690c-105">Sintaxe 1</span><span class="sxs-lookup"><span data-stu-id="5690c-105">Syntax 1</span></span>

```
LISTOFFIELDS (path)
```

## <a name="syntax-2"></a><span data-ttu-id="5690c-106">Sintaxe 2</span><span class="sxs-lookup"><span data-stu-id="5690c-106">Syntax 2</span></span>

```
LISTOFFIELDS (path, language)
```

## <a name="arguments"></a><span data-ttu-id="5690c-107">Argumentos</span><span class="sxs-lookup"><span data-stu-id="5690c-107">Arguments</span></span>

<span data-ttu-id="5690c-108">`path`: Referência de fonte de dados</span><span class="sxs-lookup"><span data-stu-id="5690c-108">`path`: Data source reference</span></span>

<span data-ttu-id="5690c-109">O caminho de referência válido de uma fonte de dados de um dos seguintes tipos de dados:</span><span class="sxs-lookup"><span data-stu-id="5690c-109">The valid reference path of a data source of one of the following data types:</span></span>

- <span data-ttu-id="5690c-110">Enumeração do modelo</span><span class="sxs-lookup"><span data-stu-id="5690c-110">Model enumeration</span></span>
- <span data-ttu-id="5690c-111">Enumeração de formato</span><span class="sxs-lookup"><span data-stu-id="5690c-111">Format enumeration</span></span>
- <span data-ttu-id="5690c-112">Enumeração de aplicativo</span><span class="sxs-lookup"><span data-stu-id="5690c-112">Application enumeration</span></span>
- <span data-ttu-id="5690c-113">Contêiner (registro)</span><span class="sxs-lookup"><span data-stu-id="5690c-113">Container (record)</span></span>

<span data-ttu-id="5690c-114">`language`: *Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="5690c-114">`language`: *String*</span></span>

<span data-ttu-id="5690c-115">Texto que representa um código de idioma.</span><span class="sxs-lookup"><span data-stu-id="5690c-115">Text that represents a language code.</span></span>

## <a name="return-values"></a><span data-ttu-id="5690c-116">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="5690c-116">Return values</span></span>

<span data-ttu-id="5690c-117">*Lista de registros*</span><span class="sxs-lookup"><span data-stu-id="5690c-117">*Record list*</span></span>

<span data-ttu-id="5690c-118">A lista de registros resultante.</span><span class="sxs-lookup"><span data-stu-id="5690c-118">The resulting list of records.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="5690c-119">Notas de uso</span><span class="sxs-lookup"><span data-stu-id="5690c-119">Usage notes</span></span>

<span data-ttu-id="5690c-120">A lista que é criada consistem em registros que têm os seguintes campos:</span><span class="sxs-lookup"><span data-stu-id="5690c-120">The list that is created consists of records that have the following fields:</span></span>

- <span data-ttu-id="5690c-121">**Nome** (tipo de dados *Cadeia de caracteres*)</span><span class="sxs-lookup"><span data-stu-id="5690c-121">**Name** (*String* data type)</span></span>
- <span data-ttu-id="5690c-122">**Rótulo** (tipo de dados *Cadeia de caracteres*)</span><span class="sxs-lookup"><span data-stu-id="5690c-122">**Label** (*String* data type)</span></span>
- <span data-ttu-id="5690c-123">**Descrição** (tipo de dados *Cadeia de caracteres*)</span><span class="sxs-lookup"><span data-stu-id="5690c-123">**Description** (*String* data type)</span></span>
- <span data-ttu-id="5690c-124">**IsTranslated** (tipo de dados *Booliano*)</span><span class="sxs-lookup"><span data-stu-id="5690c-124">**IsTranslated** (*Boolean* data type)</span></span>

<span data-ttu-id="5690c-125">Se o argumento `path` se referir a uma fonte de dados do tipo *Contêiner (registro)*, para cada campo do registro de contêiner referenciado, um novo registro será adicionado à lista criada.</span><span class="sxs-lookup"><span data-stu-id="5690c-125">If the `path` argument refers to a data source of the *Container (Record)* type, for every field of the referenced container record, a new record is added to the list that is created.</span></span> <span data-ttu-id="5690c-126">Para cada registro criado, o campo **Nome** retorna o nome do campo do registro de contêiner referenciado para o qual o registro atual foi criado.</span><span class="sxs-lookup"><span data-stu-id="5690c-126">For every record that is created, the **Name** field returns the name of the field of the referenced container record that the current record was created for.</span></span>

<span data-ttu-id="5690c-127">Se o argumento `path` se referir a uma fonte de dados de um dos tipos de *Enumeração*, para cada valor de enumeração da enumeração referenciada, um novo registro será adicionado à lista criada.</span><span class="sxs-lookup"><span data-stu-id="5690c-127">If the `path` argument refers to a data source of one of the *Enumeration* types, for every enumeration value of the referenced enumeration, a new record is added to the list that is created.</span></span> <span data-ttu-id="5690c-128">Para cada registro criado, o campo **Nome** retorna o valor da enumeração referenciada para a qual o registro atual foi criado, o campo **Descrição** retorna a descrição e o campo **Rótulo** retorna o rótulo dessa enumeração.</span><span class="sxs-lookup"><span data-stu-id="5690c-128">For every record that is created, the **Name** field returns the value of the referenced enumeration that the current record was created for, the **Description** field returns the description of that enumeration, and the **Label** field returns the label of that enumeration.</span></span>

<span data-ttu-id="5690c-129">No tempo de execução, quando a sintaxe 1 é usada, os campos **Rótulo** e **Descrição** devem retornar valores baseados nas configurações de idioma do formato de relatório eletrônico (ER) em execução:</span><span class="sxs-lookup"><span data-stu-id="5690c-129">At runtime, when syntax 1 is used, the **Label** and **Description** fields must return values that are based on the language settings of the Electronic reporting (ER) format that is running:</span></span>

- <span data-ttu-id="5690c-130">Se os rótulos e descrições para o idioma solicitado estiverem disponíveis, os campos **Rótulo** e **Descrição** retornarão valores baseados nesse idioma e o campo **IsTranslated** retornará **Verdadeiro**.</span><span class="sxs-lookup"><span data-stu-id="5690c-130">If the labels and descriptions for the requested language are available, the **Label** and **Description** fields return values that are based on that language, and the **IsTranslated** field returns **True**.</span></span>
- <span data-ttu-id="5690c-131">Se os rótulos e descrições para o idioma solicitado não estiverem disponíveis, os campos **Rótulo** e **Descrição** retornarão valores baseados no idioma padrão **EN-US** e o campo **IsTranslated** retornará **Falso**.</span><span class="sxs-lookup"><span data-stu-id="5690c-131">If the labels and descriptions for the requested language aren't available, the **Label** and **Description** fields return values that are based on the default **EN-US** language, and the **IsTranslated** field returns **False**.</span></span>

<span data-ttu-id="5690c-132">No tempo de execução, quando a sintaxe 2 é usada, os campos **Rótulo** e **Descrição** devem retornar valores baseados no idioma definido como o segundo argumento da função chamada:</span><span class="sxs-lookup"><span data-stu-id="5690c-132">At runtime, when syntax 2 is used, the **Label** and **Description** fields must return values that are based on the language that is defined as the second argument of the called function:</span></span>

- <span data-ttu-id="5690c-133">Se os rótulos e descrições para o idioma solicitado estiverem disponíveis, os campos **Rótulo** e **Descrição** retornarão valores baseados nesse idioma e o campo **IsTranslated** retornará **Verdadeiro**.</span><span class="sxs-lookup"><span data-stu-id="5690c-133">If the labels and descriptions for the requested language are available, the **Label** and **Description** fields return values that are based on that language, and the **IsTranslated** field returns **True**.</span></span>
- <span data-ttu-id="5690c-134">Se os rótulos e descrições para o idioma solicitado não estiverem disponíveis, os campos **Rótulo** e **Descrição** retornarão valores baseados no idioma **EN-US** e o campo **IsTranslated** retornará **Falso**.</span><span class="sxs-lookup"><span data-stu-id="5690c-134">If the labels and descriptions for the requested language aren't available, the **Label** and **Description** fields return values that are based on the **EN-US** language, and the **IsTranslated** field returns **False**.</span></span>

## <a name="example-1"></a><span data-ttu-id="5690c-135">Exemplo 1</span><span class="sxs-lookup"><span data-stu-id="5690c-135">Example 1</span></span>

<span data-ttu-id="5690c-136">Na ilustração a seguir, uma enumeração é apresentada em um modelo de dados de ER.</span><span class="sxs-lookup"><span data-stu-id="5690c-136">In the following illustration, an enumeration is introduced in an ER data model.</span></span>

<a href="./media/ger-listoffields-function-model-enumeration.png"><img src="./media/ger-listoffields-function-model-enumeration-e1474545790761.png" alt="Enumeration in a model" class="alignnone wp-image-1203943 size-full" width="514" height="155" /></a>

<span data-ttu-id="5690c-137">A ilustração a seguir mostra estes detalhes:</span><span class="sxs-lookup"><span data-stu-id="5690c-137">The following illustration shows these details:</span></span>

- <span data-ttu-id="5690c-138">A enumeração do modelo inserida em um relatório como uma fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="5690c-138">The model enumeration is inserted into a report as a data source.</span></span>
- <span data-ttu-id="5690c-139">Uma expressão de ER usa a enumeração do modelo como um parâmetro da função `LISTOFFIELDS`.</span><span class="sxs-lookup"><span data-stu-id="5690c-139">An ER expression uses the model enumeration as a parameter of the `LISTOFFIELDS` function.</span></span>
- <span data-ttu-id="5690c-140">Uma fonte de dados do tipo *Lista de registros* é inserida em um relatório usando a expressão de ER que é criada.</span><span class="sxs-lookup"><span data-stu-id="5690c-140">A data source of the *Record list* type is inserted into a report by using the ER expression that is created.</span></span>

<a href="./media/ger-listoffields-function-in-format-expression.png"><img src="./media/ger-listoffields-function-in-format-expression-e1474546110395.png" alt="Format" class="alignnone wp-image-1204033 size-full" width="549" height="318" /></a>

<span data-ttu-id="5690c-141">O exemplo a seguir mostra os elementos do formato de ER associados à fonte de dados do tipo *Lista de registros* que foi criada usando a função `LISTOFFIELDS`.</span><span class="sxs-lookup"><span data-stu-id="5690c-141">The following example shows the ER format elements that are bound to the data source of the *Record list* type that was created by using the `LISTOFFIELDS` function.</span></span>

<a href="./media/ger-listoffields-function-format-design.png"><img src="./media/ger-listoffields-function-format-design.png" alt="Format design" class="alignnone size-full wp-image-1204043" width="466" height="221" /></a>

<span data-ttu-id="5690c-142">A ilustração a seguir mostra o formato o resultado quando o formato criado é executado.</span><span class="sxs-lookup"><span data-stu-id="5690c-142">The following illustration shows the result when the designed format is run.</span></span>

<a href="./media/ger-listoffields-function-format-output.png"><img src="./media/ger-listoffields-function-format-output.png" alt="Format output" class="alignnone size-full wp-image-1204053" width="585" height="158" /></a>

> [!NOTE] 
> <span data-ttu-id="5690c-143">Com base nas configurações de idioma dos elementos de formato **FILE** e **FOLDER** pais, o texto traduzido para rótulos e descrições é inserido na saída do formato de ER.</span><span class="sxs-lookup"><span data-stu-id="5690c-143">Based on the language settings of the parent **FILE** and **FOLDER** format elements, translated text for labels and descriptions is entered in the output of the ER format.</span></span>

## <a name="example-2"></a><span data-ttu-id="5690c-144">Exemplo 2</span><span class="sxs-lookup"><span data-stu-id="5690c-144">Example 2</span></span>

<span data-ttu-id="5690c-145">Você usa o tipo de fonte de dados *Campo calculado* a fim de configurar as fontes de dados **enumType\_de** e **enumType\_deCH** para a enumeração do modelo de dados **enumType**:</span><span class="sxs-lookup"><span data-stu-id="5690c-145">You use the *Calculated field* data source type to configure **enumType\_de** and **enumType\_deCH** data sources for the **enumType** data model enumeration:</span></span>

- <span data-ttu-id="5690c-146">**enumType\_de** = `LISTOFFIELDS (enumType, "de")`</span><span class="sxs-lookup"><span data-stu-id="5690c-146">**enumType\_de** = `LISTOFFIELDS (enumType, "de")`</span></span>
- <span data-ttu-id="5690c-147">**enumType\_deCH** = `LISTOFFIELDS (enumType, "de-CH")`</span><span class="sxs-lookup"><span data-stu-id="5690c-147">**enumType\_deCH** = `LISTOFFIELDS (enumType, "de-CH")`</span></span>

<span data-ttu-id="5690c-148">Nesse caso, você pode usar a seguinte expressão para obter o rótulo do valor de enumeração em alemão suíço, se essa tradução estiver disponível.</span><span class="sxs-lookup"><span data-stu-id="5690c-148">In this case, you can use the following expression to get the label of the enumeration value in Swiss German, if that translation is available.</span></span> <span data-ttu-id="5690c-149">Se a tradução de alemão suíço não estiver disponível, o rótulo ficará em alemão.</span><span class="sxs-lookup"><span data-stu-id="5690c-149">If the Swiss German translation isn't available, the label is in German.</span></span>

```
IF (NOT (enumType_deCH.IsTranslated), enumType_de.Label, enumType_deCH.Label)
```

## <a name="additional-resources"></a><span data-ttu-id="5690c-150">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="5690c-150">Additional resources</span></span>

[<span data-ttu-id="5690c-151">Funções de listagem</span><span class="sxs-lookup"><span data-stu-id="5690c-151">List functions</span></span>](er-functions-category-list.md)
