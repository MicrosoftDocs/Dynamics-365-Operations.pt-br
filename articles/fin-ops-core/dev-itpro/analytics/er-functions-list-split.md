---
title: Função de ER SPLIT
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) SPLIT é usada.
author: NickSelin
manager: kfend
ms.date: 12/12/2019
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
ms.openlocfilehash: 806a0995f0c138f4e80396bb993bc6f41bc7c827
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/09/2021
ms.locfileid: "5567333"
---
# <a name="split-er-function"></a><span data-ttu-id="a329b-103">Função de ER SPLIT</span><span class="sxs-lookup"><span data-stu-id="a329b-103">SPLIT ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="a329b-104">A função `SPLIT` divide a cadeia de caracteres de entrada especificada em subcadeias de caracteres e retorna o resultado como um novo valor de *Lista de registros*.</span><span class="sxs-lookup"><span data-stu-id="a329b-104">The `SPLIT` function splits the specified input string into substrings and returns the result as a new *Record list* value.</span></span>

## <a name="syntax-1"></a><span data-ttu-id="a329b-105">Sintaxe 1</span><span class="sxs-lookup"><span data-stu-id="a329b-105">Syntax 1</span></span>

```vb
SPLIT (input, length)
```

<span data-ttu-id="a329b-106">Esta sintaxe é usada para dividir a cadeia de caracteres de entrada especificada em subcadeias de caracteres, cada uma com o tamanho especificado.</span><span class="sxs-lookup"><span data-stu-id="a329b-106">This syntax is used to split the specified input string into substrings, each of which has the specified length.</span></span>

## <a name="syntax-2"></a><span data-ttu-id="a329b-107">Sintaxe 2</span><span class="sxs-lookup"><span data-stu-id="a329b-107">Syntax 2</span></span>

```vb
SPLIT (input, delimiter)
```

<span data-ttu-id="a329b-108">Esta sintaxe é usada para dividir a cadeia de caracteres de entrada especificada em subcadeias de caracteres, com base no delimitador especificado.</span><span class="sxs-lookup"><span data-stu-id="a329b-108">This syntax is used to split the specified input string into substrings, based on the specified delimiter.</span></span>

## <a name="arguments"></a><span data-ttu-id="a329b-109">Argumentos</span><span class="sxs-lookup"><span data-stu-id="a329b-109">Arguments</span></span>

<span data-ttu-id="a329b-110">`input`: *Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="a329b-110">`input`: *String*</span></span>

<span data-ttu-id="a329b-111">O texto a ser dividido.</span><span class="sxs-lookup"><span data-stu-id="a329b-111">The text to split.</span></span>

<span data-ttu-id="a329b-112">`length`: *Inteiro*</span><span class="sxs-lookup"><span data-stu-id="a329b-112">`length`: *Integer*</span></span>

<span data-ttu-id="a329b-113">O tamanho máximo de uma única subcadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="a329b-113">The maximum length of a single substring.</span></span>

<span data-ttu-id="a329b-114">`delimiter`: *Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="a329b-114">`delimiter`: *String*</span></span>

<span data-ttu-id="a329b-115">Um delimitador usado para separar as subcadeias de caracteres.</span><span class="sxs-lookup"><span data-stu-id="a329b-115">A delimiter that is used to separate substrings.</span></span>

## <a name="return-values"></a><span data-ttu-id="a329b-116">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="a329b-116">Return values</span></span>

<span data-ttu-id="a329b-117">*Lista de registros*</span><span class="sxs-lookup"><span data-stu-id="a329b-117">*Record list*</span></span>

<span data-ttu-id="a329b-118">A lista de registros resultante.</span><span class="sxs-lookup"><span data-stu-id="a329b-118">The resulting list of records.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="a329b-119">Notas de uso</span><span class="sxs-lookup"><span data-stu-id="a329b-119">Usage notes</span></span>

<span data-ttu-id="a329b-120">A estrutura de registro da lista retornada consiste no campo **Valor** do tipo *Cadeia de caracteres*.</span><span class="sxs-lookup"><span data-stu-id="a329b-120">The record structure of the list that is returned consists of the **Value** field of the *String* type.</span></span> <span data-ttu-id="a329b-121">Todos os registros da lista retornada contêm subcadeias de caracteres geradas nesse campo.</span><span class="sxs-lookup"><span data-stu-id="a329b-121">Every record of the list that is returned contains generated substrings in this field.</span></span>

<span data-ttu-id="a329b-122">Se o argumento `delimiter` estiver vazio, a nova lista retornada consistirá em um registro com o campo **Valor** do tipo *Cadeia de caracteres*.</span><span class="sxs-lookup"><span data-stu-id="a329b-122">If the `delimiter` argument is empty, the new list that is returned consists of one record that has the **Value** field of the *String* type.</span></span> <span data-ttu-id="a329b-123">Esse campo contém o texto de entrada.</span><span class="sxs-lookup"><span data-stu-id="a329b-123">This field contains the input text.</span></span>

<span data-ttu-id="a329b-124">Se o argumento `input` estiver vazio, uma nova lista vazia será retornada.</span><span class="sxs-lookup"><span data-stu-id="a329b-124">If the `input` argument is empty, a new empty list is returned.</span></span> <span data-ttu-id="a329b-125">Se o argumento `input` ou `delimiter` não estiver especificado (nulo), uma exceção de aplicativo será gerada.</span><span class="sxs-lookup"><span data-stu-id="a329b-125">If either the `input` or `delimiter` argument is unspecified (null), an application exception is thrown.</span></span>

## <a name="example-1"></a><span data-ttu-id="a329b-126">Exemplo 1</span><span class="sxs-lookup"><span data-stu-id="a329b-126">Example 1</span></span>

<span data-ttu-id="a329b-127">`SPLIT ("abcd", 3)` retorna uma nova lista que consiste em dois registros com o campo **Valor** do tipo *Cadeia de caracteres*.</span><span class="sxs-lookup"><span data-stu-id="a329b-127">`SPLIT ("abcd", 3)` returns a new list that consists of two records that have the **Value** field of the *String* type.</span></span> <span data-ttu-id="a329b-128">O campo **Valor** no primeiro registro contém o texto **"abc"** e o campo **Valor** no segundo registro contém o texto **“d”**.</span><span class="sxs-lookup"><span data-stu-id="a329b-128">The **Value** field in the first record contains the text **"abc"**, and the **Value** field in the second record contains the text **"d"**.</span></span>

## <a name="example-2"></a><span data-ttu-id="a329b-129">Exemplo 2</span><span class="sxs-lookup"><span data-stu-id="a329b-129">Example 2</span></span>

<span data-ttu-id="a329b-130">`SPLIT ("XAb aBy", "aB")` retorna uma nova lista que consiste em três registros com o campo **Valor** do tipo *Cadeia de caracteres*.</span><span class="sxs-lookup"><span data-stu-id="a329b-130">`SPLIT ("XAb aBy", "aB")` returns a new list that consists of three records that have the **Value** field of the *String* type.</span></span> <span data-ttu-id="a329b-131">O campo **Valor** no primeiro registro contém o texto **"X"**, o campo **Valor** no segundo registro contém o texto **"&nbsp;"** e o campo **Valor** no terceiro registro contém o texto **"y"**.</span><span class="sxs-lookup"><span data-stu-id="a329b-131">The **Value** field in the first record contains the text **"X"**, the **Value** field in the second record contains the text **"&nbsp;"**, and the **Value** field in the third record contains the text **"y"**.</span></span> 

## <a name="additional-resources"></a><span data-ttu-id="a329b-132">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="a329b-132">Additional resources</span></span>

[<span data-ttu-id="a329b-133">Funções de listagem</span><span class="sxs-lookup"><span data-stu-id="a329b-133">List functions</span></span>](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]