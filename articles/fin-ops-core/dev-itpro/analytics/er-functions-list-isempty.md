---
title: Função de ER ISEMPTY
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) ISEMPTY é usada.
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
ms.openlocfilehash: c8450c17fe2de964016951197b0d4e231c550a99
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/20/2019
ms.locfileid: "2916122"
---
# <span data-ttu-id="639d8-103"><a name="ISEMPTY">Função de ER ISEMPTY</a></span><span class="sxs-lookup"><span data-stu-id="639d8-103"><a name="ISEMPTY">ISEMPTY ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="639d8-104">A função `ISEMPTY` retorna um valor *Booliano* de **TRUE** se a lista especificada não contiver registros.</span><span class="sxs-lookup"><span data-stu-id="639d8-104">The `ISEMPTY` function returns a *Boolean* value of **TRUE** if the specified list contains no records.</span></span> <span data-ttu-id="639d8-105">Caso contrário, ela retorna um valor *Booliano* de **FALSE**.</span><span class="sxs-lookup"><span data-stu-id="639d8-105">Otherwise, it returns a *Boolean* value of **FALSE**.</span></span>

## <a name="syntax"></a><span data-ttu-id="639d8-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="639d8-106">Syntax</span></span>

```
ISEMPTY (list)
```

## <a name="arguments"></a><span data-ttu-id="639d8-107">Argumentos</span><span class="sxs-lookup"><span data-stu-id="639d8-107">Arguments</span></span>

<span data-ttu-id="639d8-108">`list`: *Lista de registros*</span><span class="sxs-lookup"><span data-stu-id="639d8-108">`list`: *Record list*</span></span>

<span data-ttu-id="639d8-109">O caminho válido de uma fonte de dados do tipo *Lista de registros*.</span><span class="sxs-lookup"><span data-stu-id="639d8-109">The valid path of a data source of the *Record list* data type.</span></span>

## <a name="return-values"></a><span data-ttu-id="639d8-110">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="639d8-110">Return values</span></span>

<span data-ttu-id="639d8-111">*Booleano*</span><span class="sxs-lookup"><span data-stu-id="639d8-111">*Boolean*</span></span>

<span data-ttu-id="639d8-112">O valor *Booliano* resultante.</span><span class="sxs-lookup"><span data-stu-id="639d8-112">The resulting *Boolean* value.</span></span>

## <a name="example-1"></a><span data-ttu-id="639d8-113">Exemplo 1</span><span class="sxs-lookup"><span data-stu-id="639d8-113">Example 1</span></span>

<span data-ttu-id="639d8-114">Se você inserir a fonte de dados **DS** do tipo *Campo calculado* e ela contiver a expressão `SPLIT ("A|B|C", "|")`, a expressão `ISEMPTY(DS)` retornará **FALSE**.</span><span class="sxs-lookup"><span data-stu-id="639d8-114">If you enter data source **DS** of the *Calculated field* type, and it contains the expression `SPLIT ("A|B|C", "|")`, the expression `ISEMPTY(DS)` returns **FALSE**.</span></span>

## <a name="example-2"></a><span data-ttu-id="639d8-115">Exemplo 2</span><span class="sxs-lookup"><span data-stu-id="639d8-115">Example 2</span></span>

<span data-ttu-id="639d8-116">A expressão `ISEMPTY (SPLIT ("",1))` retorna **TRUE**.</span><span class="sxs-lookup"><span data-stu-id="639d8-116">The expression `ISEMPTY (SPLIT ("",1))` returns **TRUE**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="639d8-117">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="639d8-117">Additional resources</span></span>

[<span data-ttu-id="639d8-118">Funções de listagem</span><span class="sxs-lookup"><span data-stu-id="639d8-118">List functions</span></span>](er-functions-category-list.md)
