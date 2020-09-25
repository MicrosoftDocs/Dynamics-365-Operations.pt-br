---
title: Função de ER LIST
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) LIST é usada.
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
ms.openlocfilehash: a31288885abda69873ae23b28a36e2a54852f593
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/01/2020
ms.locfileid: "3745144"
---
# <a name="list-er-function"></a><span data-ttu-id="dff1b-103">Função de ER LIST</span><span class="sxs-lookup"><span data-stu-id="dff1b-103">LIST ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="dff1b-104">A função `LIST` retorna um valor de *Lista de registros* que consiste em uma nova lista de registros criada a partir dos argumentos especificados.</span><span class="sxs-lookup"><span data-stu-id="dff1b-104">The `LIST` function returns a *Record list* value that consists of a new list of records that is created from the specified arguments.</span></span>

## <a name="syntax"></a><span data-ttu-id="dff1b-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="dff1b-105">Syntax</span></span>

```vb
LIST (record 1 [, record 2, …, record N])
```

## <a name="arguments"></a><span data-ttu-id="dff1b-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="dff1b-106">Arguments</span></span>

<span data-ttu-id="dff1b-107">`record 1`: *Contêiner (registro)*</span><span class="sxs-lookup"><span data-stu-id="dff1b-107">`record 1`: *Container (record)*</span></span>

<span data-ttu-id="dff1b-108">Uma referência a uma fonte de dados do tipo *Registro*.</span><span class="sxs-lookup"><span data-stu-id="dff1b-108">A reference to a data source of the *Record* data type.</span></span> <span data-ttu-id="dff1b-109">Esse argumento é obrigatório.</span><span class="sxs-lookup"><span data-stu-id="dff1b-109">This argument is required.</span></span>

<span data-ttu-id="dff1b-110">`record N`: *Contêiner (registro)*</span><span class="sxs-lookup"><span data-stu-id="dff1b-110">`record N`: *Container (record)*</span></span>

<span data-ttu-id="dff1b-111">Uma referência a uma fonte de dados do tipo *Registro*.</span><span class="sxs-lookup"><span data-stu-id="dff1b-111">A reference to a data source of the *Record* data type.</span></span> <span data-ttu-id="dff1b-112">Esses argumentos adicionais são opcionais.</span><span class="sxs-lookup"><span data-stu-id="dff1b-112">These additional arguments are optional.</span></span>

## <a name="return-values"></a><span data-ttu-id="dff1b-113">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="dff1b-113">Return values</span></span>

<span data-ttu-id="dff1b-114">*Lista de registros*</span><span class="sxs-lookup"><span data-stu-id="dff1b-114">*Record list*</span></span>

<span data-ttu-id="dff1b-115">A lista de registros resultante.</span><span class="sxs-lookup"><span data-stu-id="dff1b-115">The resulting list of records.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="dff1b-116">Notas de uso</span><span class="sxs-lookup"><span data-stu-id="dff1b-116">Usage notes</span></span>

<span data-ttu-id="dff1b-117">A estrutura da lista criada contém somente os campos apresentados na estrutura de cada registro mencionado nos argumentos.</span><span class="sxs-lookup"><span data-stu-id="dff1b-117">The structure of the list that is created contains only the fields that are presented in the structure of every record that is mentioned in the arguments.</span></span>

## <a name="example"></a><span data-ttu-id="dff1b-118">Exemplo</span><span class="sxs-lookup"><span data-stu-id="dff1b-118">Example</span></span>

<span data-ttu-id="dff1b-119">Você insere a fonte de dados **Registro 1** do tipo *Contêiner*.</span><span class="sxs-lookup"><span data-stu-id="dff1b-119">You enter data source **Record 1** of the *Container* type.</span></span> <span data-ttu-id="dff1b-120">Essa fonte de dados contém os seguintes campos aninhados do tipo *Campo calculado*:</span><span class="sxs-lookup"><span data-stu-id="dff1b-120">This data source contains the following nested fields of the *Calculated field* type:</span></span>

- <span data-ttu-id="dff1b-121">**Código:** este campo contém uma expressão que retorna um valor do tipo *Cadeia de caracteres*.</span><span class="sxs-lookup"><span data-stu-id="dff1b-121">**Code:** This field contains an expression that returns a value of the *String* type.</span></span>
- <span data-ttu-id="dff1b-122">**Valor:** este campo contém uma expressão que retorna um valor do tipo *Real*.</span><span class="sxs-lookup"><span data-stu-id="dff1b-122">**Amount:** This field contains an expression that returns a value of the *Real* type.</span></span>

<span data-ttu-id="dff1b-123">Em seguida, você insere a fonte de dados **Registro 2** do tipo *Contêiner*.</span><span class="sxs-lookup"><span data-stu-id="dff1b-123">You then enter data source **Record 2** of the *Container* type.</span></span> <span data-ttu-id="dff1b-124">Essa fonte de dados contém os seguintes campos aninhados do tipo *Campo calculado*:</span><span class="sxs-lookup"><span data-stu-id="dff1b-124">This data source contains the following nested fields of the *Calculated field* type:</span></span>

- <span data-ttu-id="dff1b-125">**Valor:** este campo contém uma expressão que retorna um valor do tipo *Real*.</span><span class="sxs-lookup"><span data-stu-id="dff1b-125">**Amount:** This field contains an expression that returns a value of the *Real* type.</span></span>
- <span data-ttu-id="dff1b-126">**IsValid:** este campo contém uma expressão que retorna um valor do tipo *Booliano*.</span><span class="sxs-lookup"><span data-stu-id="dff1b-126">**IsValid:** This field contains an expression that returns a value of the *Boolean* type.</span></span>

<span data-ttu-id="dff1b-127">Nesse caso, a expressão `LIST('Record 1', 'Record 2')` retorna uma nova lista que contém dois registros.</span><span class="sxs-lookup"><span data-stu-id="dff1b-127">In this case, the expression `LIST('Record 1', 'Record 2')` returns a new list that contains two records.</span></span> <span data-ttu-id="dff1b-128">A estrutura dessa lista consiste em um único campo **Valor** do tipo *Real*, pois esse campo é o único apresentado em todos os argumentos da função chamada.</span><span class="sxs-lookup"><span data-stu-id="dff1b-128">The structure of this list consists of a single **Amount** field of the *Real* type, because this field is the only field that is presented in every argument of the called function.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="dff1b-129">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="dff1b-129">Additional resources</span></span>

[<span data-ttu-id="dff1b-130">Funções de listagem</span><span class="sxs-lookup"><span data-stu-id="dff1b-130">List functions</span></span>](er-functions-category-list.md)
