---
title: Função LISTJOIN ER
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) LISTJOIN é usada.
author: NickSelin
ms.date: 04/01/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: 58771
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 9b300cef0a508f7cc37397480738091158efdead
ms.sourcegitcommit: cabd991fda2bfcabb55db84c225b24a7bb061631
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/12/2021
ms.locfileid: "6027906"
---
# <a name="listjoin-er-function"></a><span data-ttu-id="21663-103">Função LISTJOIN ER</span><span class="sxs-lookup"><span data-stu-id="21663-103">LISTJOIN ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="21663-104">A função `LISTJOIN` retorna um valor de *Lista de registros* que representa uma nova lista associada de registros criada dos argumentos especificados.</span><span class="sxs-lookup"><span data-stu-id="21663-104">The `LISTJOIN` function returns a *Record list* value that represents a new joined list of records that is created from the specified arguments.</span></span>

## <a name="syntax"></a><span data-ttu-id="21663-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="21663-105">Syntax</span></span>

```vb
LISTJOIN (list 1 [, list 2, …, list N])
```

## <a name="arguments"></a><span data-ttu-id="21663-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="21663-106">Arguments</span></span>

<span data-ttu-id="21663-107">`list 1`: *Lista de registros*</span><span class="sxs-lookup"><span data-stu-id="21663-107">`list 1`: *Record list*</span></span>

<span data-ttu-id="21663-108">Uma referência a uma fonte de dados do tipo *Lista de registros*.</span><span class="sxs-lookup"><span data-stu-id="21663-108">A reference to a data source of the *Record list* data type.</span></span> <span data-ttu-id="21663-109">Esse argumento é obrigatório.</span><span class="sxs-lookup"><span data-stu-id="21663-109">This argument is mandatory.</span></span>

<span data-ttu-id="21663-110">`list N`: *Lista de registros*</span><span class="sxs-lookup"><span data-stu-id="21663-110">`list N`: *Record list*</span></span>

<span data-ttu-id="21663-111">Uma referência a uma fonte de dados do tipo *Lista de registros*.</span><span class="sxs-lookup"><span data-stu-id="21663-111">A reference to a data source of the *Record list* data type.</span></span> <span data-ttu-id="21663-112">Esses argumentos adicionais são opcionais.</span><span class="sxs-lookup"><span data-stu-id="21663-112">These additional arguments are optional.</span></span>

## <a name="return-values"></a><span data-ttu-id="21663-113">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="21663-113">Return values</span></span>

<span data-ttu-id="21663-114">*Lista de registros*</span><span class="sxs-lookup"><span data-stu-id="21663-114">*Record list*</span></span>

<span data-ttu-id="21663-115">A lista de registros resultante.</span><span class="sxs-lookup"><span data-stu-id="21663-115">The resulting list of records.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="21663-116">Notas de uso</span><span class="sxs-lookup"><span data-stu-id="21663-116">Usage notes</span></span>

<span data-ttu-id="21663-117">A estrutura da lista criada contém somente os campos presentes na estrutura de cada lista de registro mencionada nos argumentos.</span><span class="sxs-lookup"><span data-stu-id="21663-117">The structure of the list that is created contains only the fields that are present in the structure of every record list that is referenced in the arguments.</span></span>

## <a name="example"></a><span data-ttu-id="21663-118">Exemplo</span><span class="sxs-lookup"><span data-stu-id="21663-118">Example</span></span>

<span data-ttu-id="21663-119">Você insere a fonte de dados **Registro 1** do tipo `Container`.</span><span class="sxs-lookup"><span data-stu-id="21663-119">You enter data source **Record 1** of the `Container` type.</span></span> <span data-ttu-id="21663-120">Essa fonte de dados contém os seguintes campos aninhados do tipo `Calculated field`:</span><span class="sxs-lookup"><span data-stu-id="21663-120">This data source contains the following nested fields of the `Calculated field` type:</span></span>

- <span data-ttu-id="21663-121">**Código**: este campo contém uma expressão que retorna um valor do tipo `String`.</span><span class="sxs-lookup"><span data-stu-id="21663-121">**Code**: This field contains an expression that returns a value of the `String` type.</span></span>
- <span data-ttu-id="21663-122">**Valor**: este campo contém uma expressão que retorna um valor do tipo `Real`.</span><span class="sxs-lookup"><span data-stu-id="21663-122">**Amount**: This field contains an expression that returns a value of the `Real` type.</span></span>

<span data-ttu-id="21663-123">Em seguida, você insere a fonte de dados **Registro 2** do tipo `Container`.</span><span class="sxs-lookup"><span data-stu-id="21663-123">You then enter data source **Record 2** of the `Container` type.</span></span> <span data-ttu-id="21663-124">Essa fonte de dados contém os seguintes campos aninhados do tipo `Calculated field`:</span><span class="sxs-lookup"><span data-stu-id="21663-124">This data source contains the following nested fields of the `Calculated field` type:</span></span>

- <span data-ttu-id="21663-125">**Valor**: este campo contém uma expressão que retorna um valor do tipo `Real`.</span><span class="sxs-lookup"><span data-stu-id="21663-125">**Amount**: This field contains an expression that returns a value of the `Real` type.</span></span>
- <span data-ttu-id="21663-126">**IsValid**: este campo contém uma expressão que retorna um valor do tipo `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="21663-126">**IsValid**: This field contains an expression that returns a value of the `Boolean` type.</span></span>

![Página de designer de mapeamento de modelo de ER](./media/er-functions-list-listjoin-image1.gif)

<span data-ttu-id="21663-128">Nesse caso, a expressão `LISTJOIN(LIST('Record 1'), LIST('Record 2'))` retorna uma nova lista que contém dois registros.</span><span class="sxs-lookup"><span data-stu-id="21663-128">In this case, the expression `LISTJOIN(LIST('Record 1'), LIST('Record 2'))` returns a new list that contains two records.</span></span>

![Página de designer de mapeamento de modelo de ER com dois registros](./media/er-functions-list-listjoin-image2.gif)

<span data-ttu-id="21663-130">A estrutura dessa lista consiste em um único campo **Valor** do tipo `Real`, pois esse campo é o único apresentado em todos os argumentos da função chamada.</span><span class="sxs-lookup"><span data-stu-id="21663-130">The structure of this list consists of a single **Amount** field of the `Real` type, because this field is the only field that is presented in every argument of the called function.</span></span>

![Campo Valor da página de designer de mapeamento de modelo de ER](./media/er-functions-list-listjoin-image3.gif)

## <a name="additional-resources"></a><span data-ttu-id="21663-132">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="21663-132">Additional resources</span></span>

[<span data-ttu-id="21663-133">Funções de listagem</span><span class="sxs-lookup"><span data-stu-id="21663-133">List functions</span></span>](er-functions-category-list.md)

[<span data-ttu-id="21663-134">Depurar fontes de dados de um formato de relatório eletrônico executado para analisar o fluxo de dados e a transformação</span><span class="sxs-lookup"><span data-stu-id="21663-134">Debug data sources of an executed ER format to analyze data flow and transformation</span></span>](er-debug-data-sources.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
