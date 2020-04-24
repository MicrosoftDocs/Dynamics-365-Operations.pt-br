---
title: Função LISTJOIN ER
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) LISTJOIN é usada.
author: NickSelin
manager: kfend
ms.date: 04/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 58771
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c3b5b82917e3083b5ffe4546a6a15fd14938383a
ms.sourcegitcommit: ff6dde637d2f5d2bd18a582eb41573d4c69acdd6
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/08/2020
ms.locfileid: "3249026"
---
# <a name=""></a><span data-ttu-id="11a34-103"><a name="LISTJOIN">Função LISTJOIN ER</a></span><span class="sxs-lookup"><span data-stu-id="11a34-103"><a name="LISTJOIN">LISTJOIN ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="11a34-104">A função `LISTJOIN` retorna um valor de *Lista de registros* que representa uma nova lista associada de registros criada dos argumentos especificados.</span><span class="sxs-lookup"><span data-stu-id="11a34-104">The `LISTJOIN` function returns a *Record list* value that represents a new joined list of records that is created from the specified arguments.</span></span>

## <a name="syntax"></a><span data-ttu-id="11a34-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="11a34-105">Syntax</span></span>

```vb
LIST (list 1 [, list 2, …, list N])
```

## <a name="arguments"></a><span data-ttu-id="11a34-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="11a34-106">Arguments</span></span>

<span data-ttu-id="11a34-107">`list 1`: *Lista de registros*</span><span class="sxs-lookup"><span data-stu-id="11a34-107">`list 1`: *Record list*</span></span>

<span data-ttu-id="11a34-108">Uma referência a uma fonte de dados do tipo *Lista de registros*.</span><span class="sxs-lookup"><span data-stu-id="11a34-108">A reference to a data source of the *Record list* data type.</span></span> <span data-ttu-id="11a34-109">Esse argumento é obrigatório.</span><span class="sxs-lookup"><span data-stu-id="11a34-109">This argument is mandatory.</span></span>

<span data-ttu-id="11a34-110">`list N`: *Lista de registros*</span><span class="sxs-lookup"><span data-stu-id="11a34-110">`list N`: *Record list*</span></span>

<span data-ttu-id="11a34-111">Uma referência a uma fonte de dados do tipo *Lista de registros*.</span><span class="sxs-lookup"><span data-stu-id="11a34-111">A reference to a data source of the *Record list* data type.</span></span> <span data-ttu-id="11a34-112">Esses argumentos adicionais são opcionais.</span><span class="sxs-lookup"><span data-stu-id="11a34-112">These additional arguments are optional.</span></span>

## <a name="return-values"></a><span data-ttu-id="11a34-113">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="11a34-113">Return values</span></span>

<span data-ttu-id="11a34-114">*Lista de registros*</span><span class="sxs-lookup"><span data-stu-id="11a34-114">*Record list*</span></span>

<span data-ttu-id="11a34-115">A lista de registros resultante.</span><span class="sxs-lookup"><span data-stu-id="11a34-115">The resulting list of records.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="11a34-116">Notas de uso</span><span class="sxs-lookup"><span data-stu-id="11a34-116">Usage notes</span></span>

<span data-ttu-id="11a34-117">A estrutura da lista criada contém somente os campos presentes na estrutura de cada lista de registro mencionada nos argumentos.</span><span class="sxs-lookup"><span data-stu-id="11a34-117">The structure of the list that is created contains only the fields that are present in the structure of every record list that is referenced in the arguments.</span></span>

## <a name="example"></a><span data-ttu-id="11a34-118">Exemplo</span><span class="sxs-lookup"><span data-stu-id="11a34-118">Example</span></span>

<span data-ttu-id="11a34-119">Você insere a fonte de dados **Registro 1** do tipo `Container`.</span><span class="sxs-lookup"><span data-stu-id="11a34-119">You enter data source **Record 1** of the `Container` type.</span></span> <span data-ttu-id="11a34-120">Essa fonte de dados contém os seguintes campos aninhados do tipo `Calculated field`:</span><span class="sxs-lookup"><span data-stu-id="11a34-120">This data source contains the following nested fields of the `Calculated field` type:</span></span>

- <span data-ttu-id="11a34-121">**Código**: este campo contém uma expressão que retorna um valor do tipo `String`.</span><span class="sxs-lookup"><span data-stu-id="11a34-121">**Code**: This field contains an expression that returns a value of the `String` type.</span></span>
- <span data-ttu-id="11a34-122">**Valor**: este campo contém uma expressão que retorna um valor do tipo `Real`.</span><span class="sxs-lookup"><span data-stu-id="11a34-122">**Amount**: This field contains an expression that returns a value of the `Real` type.</span></span>

<span data-ttu-id="11a34-123">Em seguida, você insere a fonte de dados **Registro 2** do tipo `Container`.</span><span class="sxs-lookup"><span data-stu-id="11a34-123">You then enter data source **Record 2** of the `Container` type.</span></span> <span data-ttu-id="11a34-124">Essa fonte de dados contém os seguintes campos aninhados do tipo `Calculated field`:</span><span class="sxs-lookup"><span data-stu-id="11a34-124">This data source contains the following nested fields of the `Calculated field` type:</span></span>

- <span data-ttu-id="11a34-125">**Valor**: este campo contém uma expressão que retorna um valor do tipo `Real`.</span><span class="sxs-lookup"><span data-stu-id="11a34-125">**Amount**: This field contains an expression that returns a value of the `Real` type.</span></span>
- <span data-ttu-id="11a34-126">**IsValid**: este campo contém uma expressão que retorna um valor do tipo `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="11a34-126">**IsValid**: This field contains an expression that returns a value of the `Boolean` type.</span></span>

<span data-ttu-id="11a34-127">Nesse caso, a expressão `LISTJOIN(LIST('Record 1'), LIST('Record 2'))` retorna uma nova lista que contém dois registros.</span><span class="sxs-lookup"><span data-stu-id="11a34-127">In this case, the expression `LISTJOIN(LIST('Record 1'), LIST('Record 2'))` returns a new list that contains two records.</span></span> <span data-ttu-id="11a34-128">A estrutura dessa lista consiste em um único campo **Valor** do tipo `Real`, pois esse campo é o único apresentado em todos os argumentos da função chamada.</span><span class="sxs-lookup"><span data-stu-id="11a34-128">The structure of this list consists of a single **Amount** field of the `Real` type, because this field is the only field that is presented in every argument of the called function.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="11a34-129">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="11a34-129">Additional resources</span></span>

[<span data-ttu-id="11a34-130">Funções de listagem</span><span class="sxs-lookup"><span data-stu-id="11a34-130">List functions</span></span>](er-functions-category-list.md)
