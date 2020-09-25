---
title: Função de ER INDEX
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) INDEX é usada.
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
ms.openlocfilehash: 051e22daa3fe2d6c328e36403201d940f724bd29
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/01/2020
ms.locfileid: "3745168"
---
# <a name="index-er-function"></a><span data-ttu-id="b36fa-103">Função de ER INDEX</span><span class="sxs-lookup"><span data-stu-id="b36fa-103">INDEX ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b36fa-104">A função `INDEX` retorna um valor de *Contêiner (registro)* que é selecionado usando o índice numérico especificado na lista especificada.</span><span class="sxs-lookup"><span data-stu-id="b36fa-104">The `INDEX` function returns a *Container (record)* value that is selected by using the specified numeric index in the specified list.</span></span> <span data-ttu-id="b36fa-105">Se o índice estiver fora do intervalo dos registros na lista especificada, uma exceção será gerada.</span><span class="sxs-lookup"><span data-stu-id="b36fa-105">If the index is out of range for the records in the specified list, an exception is thrown.</span></span>

## <a name="syntax"></a><span data-ttu-id="b36fa-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="b36fa-106">Syntax</span></span>

```vb
INDEX (list, index)
```

## <a name="arguments"></a><span data-ttu-id="b36fa-107">Argumentos</span><span class="sxs-lookup"><span data-stu-id="b36fa-107">Arguments</span></span>

<span data-ttu-id="b36fa-108">`list`: *Lista de registros*</span><span class="sxs-lookup"><span data-stu-id="b36fa-108">`list`: *Record list*</span></span>

<span data-ttu-id="b36fa-109">O caminho válido de uma fonte de dados do tipo *Lista de registros*.</span><span class="sxs-lookup"><span data-stu-id="b36fa-109">The valid path of a data source of the *Record list* data type.</span></span>

<span data-ttu-id="b36fa-110">`index`: *Inteiro*</span><span class="sxs-lookup"><span data-stu-id="b36fa-110">`index`: *Integer*</span></span>

<span data-ttu-id="b36fa-111">Um índice numérico que indica a posição do registro desejado na lista especificada.</span><span class="sxs-lookup"><span data-stu-id="b36fa-111">A numeric index that indicates the position of the desired record in the specified list.</span></span>

## <a name="return-values"></a><span data-ttu-id="b36fa-112">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="b36fa-112">Return values</span></span>

<span data-ttu-id="b36fa-113">*Contêiner (registro)*</span><span class="sxs-lookup"><span data-stu-id="b36fa-113">*Container (record)*</span></span>

<span data-ttu-id="b36fa-114">O valor de registro resultante.</span><span class="sxs-lookup"><span data-stu-id="b36fa-114">The resulting record value.</span></span>

## <a name="example-1"></a><span data-ttu-id="b36fa-115">Exemplo 1</span><span class="sxs-lookup"><span data-stu-id="b36fa-115">Example 1</span></span>

<span data-ttu-id="b36fa-116">Se você inserir a fonte de dados **DS** do tipo *Campo calculado* e ela contiver a expressão `SPLIT ("A|B|C", "|")`, a expressão `DS.Value` retornará o valor de texto **"B"** para o segundo registro dessa lista de registros.</span><span class="sxs-lookup"><span data-stu-id="b36fa-116">If you enter data source **DS** of the *Calculated field* type, and it contains the expression `SPLIT ("A|B|C", "|")`, the expression `DS.Value` returns the text value **"B"** for the second record of this record list.</span></span> <span data-ttu-id="b36fa-117">A expressão `INDEX (SPLIT ("A|B|C", "|"), 2).Value` também retorna o valor de texto **"B"**.</span><span class="sxs-lookup"><span data-stu-id="b36fa-117">The expression `INDEX (SPLIT ("A|B|C", "|"), 2).Value` also returns the text value **"B"**.</span></span>

## <a name="example-2"></a><span data-ttu-id="b36fa-118">Exemplo 2</span><span class="sxs-lookup"><span data-stu-id="b36fa-118">Example 2</span></span>

<span data-ttu-id="b36fa-119">Se você inserir a fonte de dados **DS** do tipo *Campo calculado* e ela contiver a expressão `SPLIT ("A|B|C", "|")`, a expressão `INDEX (SPLIT ("A|B|C", "|"), 4).Value` gerará uma exceção no tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="b36fa-119">If you enter data source **DS** of the *Calculated field* type, and it contains the expression `SPLIT ("A|B|C", "|")`, the expression `INDEX (SPLIT ("A|B|C", "|"), 4).Value` throws an exception at runtime.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="b36fa-120">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="b36fa-120">Additional resources</span></span>

[<span data-ttu-id="b36fa-121">Funções de listagem</span><span class="sxs-lookup"><span data-stu-id="b36fa-121">List functions</span></span>](er-functions-category-list.md)
