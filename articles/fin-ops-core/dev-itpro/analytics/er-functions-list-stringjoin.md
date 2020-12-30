---
title: Função de ER STRINGJOIN
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) STRINGJOIN é usada.
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
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 586dbcb98d237325188f4b0384580613ab7a9347
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2020
ms.locfileid: "4683717"
---
# <a name="stringjoin-er-function"></a><span data-ttu-id="896eb-103">Função de ER STRINGJOIN</span><span class="sxs-lookup"><span data-stu-id="896eb-103">STRINGJOIN ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="896eb-104">A função `STRINGJOIN` retorna um valor de *Cadeia de caracteres* que consiste em valores concatenados do campo especificado da lista especificada.</span><span class="sxs-lookup"><span data-stu-id="896eb-104">The `STRINGJOIN` function returns a *String* value that consists of concatenated values of the specified field from the specified list.</span></span> <span data-ttu-id="896eb-105">Os valores podem ser separados pelo delimitador especificado.</span><span class="sxs-lookup"><span data-stu-id="896eb-105">The values can be separated by the specified delimiter.</span></span>

## <a name="syntax"></a><span data-ttu-id="896eb-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="896eb-106">Syntax</span></span>

```vb
STRINGJOIN (list, field, delimiter)
```

## <a name="arguments"></a><span data-ttu-id="896eb-107">Argumentos</span><span class="sxs-lookup"><span data-stu-id="896eb-107">Arguments</span></span>

<span data-ttu-id="896eb-108">`list`: *Lista de registros*</span><span class="sxs-lookup"><span data-stu-id="896eb-108">`list`: *Record list*</span></span>

<span data-ttu-id="896eb-109">O caminho válido de uma fonte de dados do tipo *Lista de registros*.</span><span class="sxs-lookup"><span data-stu-id="896eb-109">The valid path of a data source of the *Record list* data type.</span></span>

<span data-ttu-id="896eb-110">`field`: *Campo*</span><span class="sxs-lookup"><span data-stu-id="896eb-110">`field`: *Field*</span></span>

<span data-ttu-id="896eb-111">O caminho válido de um campo do tipo de dados *Cadeia de caracteres* na lista especificada.</span><span class="sxs-lookup"><span data-stu-id="896eb-111">The valid path of a field of the *String* data type in the specified list.</span></span>

<span data-ttu-id="896eb-112">`delimiter`: *Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="896eb-112">`delimiter`: *String*</span></span>

<span data-ttu-id="896eb-113">Um delimitador usado para separar as subcadeias de caracteres.</span><span class="sxs-lookup"><span data-stu-id="896eb-113">A delimiter that is used to separate substrings.</span></span>

## <a name="return-values"></a><span data-ttu-id="896eb-114">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="896eb-114">Return values</span></span>

<span data-ttu-id="896eb-115">*Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="896eb-115">*String*</span></span>

<span data-ttu-id="896eb-116">O valor de texto resultante.</span><span class="sxs-lookup"><span data-stu-id="896eb-116">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="896eb-117">Exemplo</span><span class="sxs-lookup"><span data-stu-id="896eb-117">Example</span></span>

<span data-ttu-id="896eb-118">Se você inserir `SPLIT("abc" , 1)` como a fonte de dados **DS**, a expressão `STRINGJOIN (DS, DS.Value, "-")` retornará **"a-b-c"**.</span><span class="sxs-lookup"><span data-stu-id="896eb-118">If you enter `SPLIT("abc" , 1)` as data source **DS**, the expression `STRINGJOIN (DS, DS.Value, "-")` returns **"a-b-c"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="896eb-119">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="896eb-119">Additional resources</span></span>

[<span data-ttu-id="896eb-120">Funções de listagem</span><span class="sxs-lookup"><span data-stu-id="896eb-120">List functions</span></span>](er-functions-category-list.md)
