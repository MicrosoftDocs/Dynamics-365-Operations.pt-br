---
title: Função de ER SPLIT
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) SPLIT é usada.
author: NickSelin
ms.date: 04/01/2021
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
ms.openlocfilehash: 26b6ddeb2880fc220283b6389327a497549a4511
ms.sourcegitcommit: 74f5b04b482b2ae023c728e0df0eb78305493c6a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/02/2021
ms.locfileid: "5853434"
---
# <a name="split-er-function"></a><span data-ttu-id="e531c-103">Função de ER SPLIT</span><span class="sxs-lookup"><span data-stu-id="e531c-103">SPLIT ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="e531c-104">A função `SPLIT` divide a cadeia de caracteres de entrada especificada em subcadeias de caracteres e retorna o resultado como um novo valor de *Lista de registros*.</span><span class="sxs-lookup"><span data-stu-id="e531c-104">The `SPLIT` function splits the specified input string into substrings and returns the result as a new *Record list* value.</span></span>

## <a name="syntax-1"></a><span data-ttu-id="e531c-105">Sintaxe 1</span><span class="sxs-lookup"><span data-stu-id="e531c-105">Syntax 1</span></span>

```vb
SPLIT (input, length)
```

<span data-ttu-id="e531c-106">Esta sintaxe é usada para dividir a cadeia de caracteres de entrada especificada em subcadeias de caracteres, cada uma com o tamanho especificado.</span><span class="sxs-lookup"><span data-stu-id="e531c-106">This syntax is used to split the specified input string into substrings, each of which has the specified length.</span></span>

## <a name="syntax-2"></a><span data-ttu-id="e531c-107">Sintaxe 2</span><span class="sxs-lookup"><span data-stu-id="e531c-107">Syntax 2</span></span>

```vb
SPLIT (input, delimiter)
```

<span data-ttu-id="e531c-108">Esta sintaxe é usada para dividir a cadeia de caracteres de entrada especificada em subcadeias de caracteres, com base no delimitador especificado.</span><span class="sxs-lookup"><span data-stu-id="e531c-108">This syntax is used to split the specified input string into substrings, based on the specified delimiter.</span></span>

## <a name="arguments"></a><span data-ttu-id="e531c-109">Argumentos</span><span class="sxs-lookup"><span data-stu-id="e531c-109">Arguments</span></span>

<span data-ttu-id="e531c-110">`input`: *Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="e531c-110">`input`: *String*</span></span>

<span data-ttu-id="e531c-111">O texto a ser dividido.</span><span class="sxs-lookup"><span data-stu-id="e531c-111">The text to split.</span></span>

<span data-ttu-id="e531c-112">`length`: *Inteiro*</span><span class="sxs-lookup"><span data-stu-id="e531c-112">`length`: *Integer*</span></span>

<span data-ttu-id="e531c-113">O tamanho máximo de uma única subcadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="e531c-113">The maximum length of a single substring.</span></span>

<span data-ttu-id="e531c-114">`delimiter`: *Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="e531c-114">`delimiter`: *String*</span></span>

<span data-ttu-id="e531c-115">Um delimitador usado para separar as subcadeias de caracteres.</span><span class="sxs-lookup"><span data-stu-id="e531c-115">A delimiter that is used to separate substrings.</span></span>

## <a name="return-values"></a><span data-ttu-id="e531c-116">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="e531c-116">Return values</span></span>

<span data-ttu-id="e531c-117">*Lista de registros*</span><span class="sxs-lookup"><span data-stu-id="e531c-117">*Record list*</span></span>

<span data-ttu-id="e531c-118">A lista de registros resultante.</span><span class="sxs-lookup"><span data-stu-id="e531c-118">The resulting list of records.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="e531c-119">Notas de uso</span><span class="sxs-lookup"><span data-stu-id="e531c-119">Usage notes</span></span>

<span data-ttu-id="e531c-120">A estrutura de registro da lista retornada consiste no campo **Valor** do tipo *Cadeia de caracteres*.</span><span class="sxs-lookup"><span data-stu-id="e531c-120">The record structure of the list that is returned consists of the **Value** field of the *String* type.</span></span> <span data-ttu-id="e531c-121">Todos os registros da lista retornada contêm subcadeias de caracteres geradas nesse campo.</span><span class="sxs-lookup"><span data-stu-id="e531c-121">Every record of the list that is returned contains generated substrings in this field.</span></span>

<span data-ttu-id="e531c-122">Se o argumento `delimiter` estiver vazio, a nova lista retornada consistirá em um registro com o campo **Valor** do tipo *Cadeia de caracteres*.</span><span class="sxs-lookup"><span data-stu-id="e531c-122">If the `delimiter` argument is empty, the new list that is returned consists of one record that has the **Value** field of the *String* type.</span></span> <span data-ttu-id="e531c-123">Esse campo contém o texto de entrada.</span><span class="sxs-lookup"><span data-stu-id="e531c-123">This field contains the input text.</span></span>

<span data-ttu-id="e531c-124">Se o argumento `input` estiver vazio, uma nova lista vazia será retornada.</span><span class="sxs-lookup"><span data-stu-id="e531c-124">If the `input` argument is empty, a new empty list is returned.</span></span> <span data-ttu-id="e531c-125">Se o argumento `input` ou `delimiter` não estiver especificado (nulo), uma exceção de aplicativo será gerada.</span><span class="sxs-lookup"><span data-stu-id="e531c-125">If either the `input` or `delimiter` argument is unspecified (null), an application exception is thrown.</span></span>

## <a name="example-1"></a><span data-ttu-id="e531c-126">Exemplo 1</span><span class="sxs-lookup"><span data-stu-id="e531c-126">Example 1</span></span>

<span data-ttu-id="e531c-127">`SPLIT ("abcd", 3)` retorna uma nova lista que consiste em dois registros com o campo **Valor** do tipo *Cadeia de caracteres*.</span><span class="sxs-lookup"><span data-stu-id="e531c-127">`SPLIT ("abcd", 3)` returns a new list that consists of two records that have the **Value** field of the *String* type.</span></span> <span data-ttu-id="e531c-128">O campo **Valor** no primeiro registro contém o texto **"abc"** e o campo **Valor** no segundo registro contém o texto **“d”**.</span><span class="sxs-lookup"><span data-stu-id="e531c-128">The **Value** field in the first record contains the text **"abc"**, and the **Value** field in the second record contains the text **"d"**.</span></span>

## <a name="example-2"></a><span data-ttu-id="e531c-129">Exemplo 2</span><span class="sxs-lookup"><span data-stu-id="e531c-129">Example 2</span></span>

<span data-ttu-id="e531c-130">`SPLIT ("XAb aBy", "aB")` retorna uma nova lista que consiste em três registros com o campo **Valor** do tipo *Cadeia de caracteres*.</span><span class="sxs-lookup"><span data-stu-id="e531c-130">`SPLIT ("XAb aBy", "aB")` returns a new list that consists of three records that have the **Value** field of the *String* type.</span></span> <span data-ttu-id="e531c-131">O campo **Valor** no primeiro registro contém o texto **"X"**, o campo **Valor** no segundo registro contém o texto **"&nbsp;"** e o campo **Valor** no terceiro registro contém o texto **"y"**.</span><span class="sxs-lookup"><span data-stu-id="e531c-131">The **Value** field in the first record contains the text **"X"**, the **Value** field in the second record contains the text **"&nbsp;"**, and the **Value** field in the third record contains the text **"y"**.</span></span> 

## <a name="example-3"></a><span data-ttu-id="e531c-132">Exemplo 3</span><span class="sxs-lookup"><span data-stu-id="e531c-132">Example 3</span></span>

<span data-ttu-id="e531c-133">Você pode usar a função [INDEX](er-functions-list-index.md) para acessar elementos individuais da cadeia de caracteres de entrada especificada.</span><span class="sxs-lookup"><span data-stu-id="e531c-133">Yo can use the [INDEX](er-functions-list-index.md) function to access individual elements of the specified input string.</span></span> <span data-ttu-id="e531c-134">Se você inserir a fonte de dados **MyList** do tipo **Campo calculado** e configurar a expressão `SPLIT("abc", 1)` para ela, a expressão `INDEX(MyList,2).Value` retornará o valor de texto **"b"**.</span><span class="sxs-lookup"><span data-stu-id="e531c-134">If you enter the **MyList** data source of the **Calculated field** type and configure for it the `SPLIT("abc", 1)` expression, the expression `INDEX(MyList,2).Value` returns the text **"b"**.</span></span>

## <a name="example-4"></a><span data-ttu-id="e531c-135">Exemplo 4</span><span class="sxs-lookup"><span data-stu-id="e531c-135">Example 4</span></span>

<span data-ttu-id="e531c-136">A função [ENUMERATE](er-functions-list-enumerate.md) também ajuda a acessar elementos individuais da cadeia de caracteres de entrada especificada.</span><span class="sxs-lookup"><span data-stu-id="e531c-136">The [ENUMERATE](er-functions-list-enumerate.md) function can also help you access individual elements of the specified input string.</span></span> <span data-ttu-id="e531c-137">Se você inserir primeiro a fonte de dados **MyList** do tipo **Campo calculado** e configurá-la para a expressão `SPLIT("abc", 1)` e, em seguida, inserir a fonte de dados **EnumeratedList** do tipo **Campo calculado** e configurar a expressão `ENUMERATE(MyList)` para ela, a expressão `FIRSTORNULL(WHERE(EnumeratedList, EnumeratedList.Number=2)).Value` retornará o texto **"b"**.</span><span class="sxs-lookup"><span data-stu-id="e531c-137">If you first enter the **MyList** data source of the **Calculated field** type and configure for it the `SPLIT("abc", 1)` expression, and then enter the **EnumeratedList** data source of the **Calculated field** type and configure for it the `ENUMERATE(MyList)` expression, the expression `FIRSTORNULL(WHERE(EnumeratedList, EnumeratedList.Number=2)).Value` returns the text **"b"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="e531c-138">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="e531c-138">Additional resources</span></span>

[<span data-ttu-id="e531c-139">Funções de listagem</span><span class="sxs-lookup"><span data-stu-id="e531c-139">List functions</span></span>](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
