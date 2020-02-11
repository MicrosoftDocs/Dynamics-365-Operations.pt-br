---
title: Função de ER ORDERBY
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) ORDERBY é usada.
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
ms.openlocfilehash: a6aed53dcad6d402fc2ca61ae0687016cdb3af5b
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/20/2019
ms.locfileid: "2916191"
---
# <span data-ttu-id="b389c-103"><a name="ORDERBY">Função de ER ORDERBY</a></span><span class="sxs-lookup"><span data-stu-id="b389c-103"><a name="ORDERBY">ORDERBY ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b389c-104">A função `ORDERBY` retorna a lista especificada como um valor de *Lista de registros* após ela ser classificada de acordo com os argumentos especificados.</span><span class="sxs-lookup"><span data-stu-id="b389c-104">The `ORDERBY` function returns the specified list as a *Record list* value after it has been sorted according to the specified arguments.</span></span> <span data-ttu-id="b389c-105">Esses argumentos podem ser definidos como expressões.</span><span class="sxs-lookup"><span data-stu-id="b389c-105">These arguments can be defined as expressions.</span></span>

## <a name="syntax"></a><span data-ttu-id="b389c-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="b389c-106">Syntax</span></span>

```
ORDERBY (list , expression 1[, expression 2, …, expression N])
```

## <a name="arguments"></a><span data-ttu-id="b389c-107">Argumentos</span><span class="sxs-lookup"><span data-stu-id="b389c-107">Arguments</span></span>

<span data-ttu-id="b389c-108">`list`: *Lista de registros*</span><span class="sxs-lookup"><span data-stu-id="b389c-108">`list`: *Record list*</span></span>

<span data-ttu-id="b389c-109">O caminho válido de uma fonte de dados do tipo *Lista de registros*.</span><span class="sxs-lookup"><span data-stu-id="b389c-109">The valid path of a data source of the *Record list* data type.</span></span>

<span data-ttu-id="b389c-110">`expression 1`: *Campo*</span><span class="sxs-lookup"><span data-stu-id="b389c-110">`expression 1`: *Field*</span></span>

<span data-ttu-id="b389c-111">O caminho válido de um campo da fonte de dados que é referenciado pelo argumento `list` da função chamada.</span><span class="sxs-lookup"><span data-stu-id="b389c-111">The valid path of a field of the data source that is referenced by the `list` argument of the called function.</span></span> <span data-ttu-id="b389c-112">O campo referenciado deve ser um campo do tipo de dados primitivo.</span><span class="sxs-lookup"><span data-stu-id="b389c-112">The referenced field must be a field of the primitive data type.</span></span> <span data-ttu-id="b389c-113">Esse argumento é obrigatório.</span><span class="sxs-lookup"><span data-stu-id="b389c-113">This argument is required.</span></span>

<span data-ttu-id="b389c-114">`expression N`: *Campo*</span><span class="sxs-lookup"><span data-stu-id="b389c-114">`expression N`: *Field*</span></span>

<span data-ttu-id="b389c-115">O caminho válido de um campo da fonte de dados que é referenciado pelo argumento `list` da função chamada.</span><span class="sxs-lookup"><span data-stu-id="b389c-115">The valid path of a field of the data source that is referenced by the `list` argument of the called function.</span></span> <span data-ttu-id="b389c-116">O campo referenciado deve ser um campo do tipo de dados primitivo.</span><span class="sxs-lookup"><span data-stu-id="b389c-116">The referenced field must be a field of the primitive data type.</span></span> <span data-ttu-id="b389c-117">Esses argumentos adicionais são opcionais.</span><span class="sxs-lookup"><span data-stu-id="b389c-117">These additional arguments are optional.</span></span>

## <a name="return-values"></a><span data-ttu-id="b389c-118">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="b389c-118">Return values</span></span>

<span data-ttu-id="b389c-119">*Lista de registros*</span><span class="sxs-lookup"><span data-stu-id="b389c-119">*Record list*</span></span>

<span data-ttu-id="b389c-120">A lista de registros resultante.</span><span class="sxs-lookup"><span data-stu-id="b389c-120">The resulting list of records.</span></span>

## <a name="example-1"></a><span data-ttu-id="b389c-121">Exemplo 1</span><span class="sxs-lookup"><span data-stu-id="b389c-121">Example 1</span></span>

<span data-ttu-id="b389c-122">Se você inserir a fonte de dados **DS** do tipo *Campo calculado* e ela contiver a expressão `SPLIT ("C|B|A", "|")`, a expressão `FIRST( ORDERBY( DS, DS. Value)).Value` retornará o valor de texto **"A"**.</span><span class="sxs-lookup"><span data-stu-id="b389c-122">If you enter data source **DS** of the *Calculated field* type, and it contains the expression `SPLIT ("C|B|A", "|")`, the expression `FIRST( ORDERBY( DS, DS. Value)).Value` returns the text value **"A"**.</span></span>

## <a name="example-2"></a><span data-ttu-id="b389c-123">Exemplo 2</span><span class="sxs-lookup"><span data-stu-id="b389c-123">Example 2</span></span>

<span data-ttu-id="b389c-124">Se **Fornecedor** estiver configurado como uma fonte de dados de relatório eletrônico (ER) que se refere à tabela VendTable, a expressão `ORDERBY (Vendors, Vendors.'name()')` retornará uma lista de fornecedores que é classificada por nome em ordem crescente.</span><span class="sxs-lookup"><span data-stu-id="b389c-124">If **Vendor** is configured as an Electronic reporting (ER) data source that refers to the VendTable table, the expression `ORDERBY (Vendors, Vendors.'name()')` returns a list of vendors that is sorted by name in ascending order.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="b389c-125">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="b389c-125">Additional resources</span></span>

[<span data-ttu-id="b389c-126">Funções de listagem</span><span class="sxs-lookup"><span data-stu-id="b389c-126">List functions</span></span>](er-functions-category-list.md)