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
ms.openlocfilehash: 5b6fde7cbadec7aae052742ef598e1af4dbae793
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/01/2020
ms.locfileid: "3745120"
---
# <a name="isempty-er-function"></a><span data-ttu-id="70bca-103">Função de ER ISEMPTY</span><span class="sxs-lookup"><span data-stu-id="70bca-103">ISEMPTY ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="70bca-104">A função `ISEMPTY` retorna um valor *Booliano* de **TRUE** se a lista especificada não contiver registros.</span><span class="sxs-lookup"><span data-stu-id="70bca-104">The `ISEMPTY` function returns a *Boolean* value of **TRUE** if the specified list contains no records.</span></span> <span data-ttu-id="70bca-105">Caso contrário, ela retorna um valor *Booliano* de **FALSE**.</span><span class="sxs-lookup"><span data-stu-id="70bca-105">Otherwise, it returns a *Boolean* value of **FALSE**.</span></span>

## <a name="syntax"></a><span data-ttu-id="70bca-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="70bca-106">Syntax</span></span>

```vb
ISEMPTY (list)
```

## <a name="arguments"></a><span data-ttu-id="70bca-107">Argumentos</span><span class="sxs-lookup"><span data-stu-id="70bca-107">Arguments</span></span>

<span data-ttu-id="70bca-108">`list`: *Lista de registros*</span><span class="sxs-lookup"><span data-stu-id="70bca-108">`list`: *Record list*</span></span>

<span data-ttu-id="70bca-109">O caminho válido de uma fonte de dados do tipo *Lista de registros*.</span><span class="sxs-lookup"><span data-stu-id="70bca-109">The valid path of a data source of the *Record list* data type.</span></span>

## <a name="return-values"></a><span data-ttu-id="70bca-110">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="70bca-110">Return values</span></span>

<span data-ttu-id="70bca-111">*Booleano*</span><span class="sxs-lookup"><span data-stu-id="70bca-111">*Boolean*</span></span>

<span data-ttu-id="70bca-112">O valor *Booliano* resultante.</span><span class="sxs-lookup"><span data-stu-id="70bca-112">The resulting *Boolean* value.</span></span>

## <a name="example-1"></a><span data-ttu-id="70bca-113">Exemplo 1</span><span class="sxs-lookup"><span data-stu-id="70bca-113">Example 1</span></span>

<span data-ttu-id="70bca-114">Se você inserir a fonte de dados **DS** do tipo *Campo calculado* e ela contiver a expressão `SPLIT ("A|B|C", "|")`, a expressão `ISEMPTY(DS)` retornará **FALSE**.</span><span class="sxs-lookup"><span data-stu-id="70bca-114">If you enter data source **DS** of the *Calculated field* type, and it contains the expression `SPLIT ("A|B|C", "|")`, the expression `ISEMPTY(DS)` returns **FALSE**.</span></span>

## <a name="example-2"></a><span data-ttu-id="70bca-115">Exemplo 2</span><span class="sxs-lookup"><span data-stu-id="70bca-115">Example 2</span></span>

<span data-ttu-id="70bca-116">A expressão `ISEMPTY (SPLIT ("",1))` retorna **TRUE**.</span><span class="sxs-lookup"><span data-stu-id="70bca-116">The expression `ISEMPTY (SPLIT ("",1))` returns **TRUE**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="70bca-117">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="70bca-117">Additional resources</span></span>

[<span data-ttu-id="70bca-118">Funções de listagem</span><span class="sxs-lookup"><span data-stu-id="70bca-118">List functions</span></span>](er-functions-category-list.md)
