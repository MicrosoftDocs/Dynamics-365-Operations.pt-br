---
title: Função de ER LISTOFFIRSTITEM
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) LISTOFFIRSTITEM é usada.
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
ms.openlocfilehash: 8ea81bce8cd6b922f3ef1d53ec0c4b2574780377
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2020
ms.locfileid: "4686479"
---
# <a name="listoffirstitem-er-function"></a><span data-ttu-id="b3cc6-103">Função de ER LISTOFFIRSTITEM</span><span class="sxs-lookup"><span data-stu-id="b3cc6-103">LISTOFFIRSTITEM ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b3cc6-104">A função `LISTOFFIRSTITEM` retorna um valor de *Lista de registros* que consiste somente no primeiro registro da lista especificada.</span><span class="sxs-lookup"><span data-stu-id="b3cc6-104">The `LISTOFFIRSTITEM` function returns a *Record list* value that consists of only the first record of the specified list.</span></span>

## <a name="syntax"></a><span data-ttu-id="b3cc6-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="b3cc6-105">Syntax</span></span>

```vb
LISTOFFIRSTITEM (list)
```

## <a name="arguments"></a><span data-ttu-id="b3cc6-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="b3cc6-106">Arguments</span></span>

<span data-ttu-id="b3cc6-107">`list`: *Lista de registros*</span><span class="sxs-lookup"><span data-stu-id="b3cc6-107">`list`: *Record list*</span></span>

<span data-ttu-id="b3cc6-108">O caminho válido de uma fonte de dados do tipo *Lista de registros*.</span><span class="sxs-lookup"><span data-stu-id="b3cc6-108">The valid path of a data source of the *Record list* data type.</span></span>

## <a name="return-values"></a><span data-ttu-id="b3cc6-109">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="b3cc6-109">Return values</span></span>

<span data-ttu-id="b3cc6-110">*Lista de registros*</span><span class="sxs-lookup"><span data-stu-id="b3cc6-110">*Record list*</span></span>

<span data-ttu-id="b3cc6-111">A lista de registros resultante.</span><span class="sxs-lookup"><span data-stu-id="b3cc6-111">The resulting list of records.</span></span>

## <a name="example"></a><span data-ttu-id="b3cc6-112">Exemplo</span><span class="sxs-lookup"><span data-stu-id="b3cc6-112">Example</span></span>

<span data-ttu-id="b3cc6-113">A expressão `FIRST( LISTOFFIRSTITEM ( SPLIT ("ABC",1))).Value` retorna o valor de texto **"A"**.</span><span class="sxs-lookup"><span data-stu-id="b3cc6-113">The expression `FIRST( LISTOFFIRSTITEM ( SPLIT ("ABC",1))).Value` returns the text value **"A"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="b3cc6-114">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="b3cc6-114">Additional resources</span></span>

[<span data-ttu-id="b3cc6-115">Funções de listagem</span><span class="sxs-lookup"><span data-stu-id="b3cc6-115">List functions</span></span>](er-functions-category-list.md)
