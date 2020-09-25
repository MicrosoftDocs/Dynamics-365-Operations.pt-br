---
title: Função de ER EMPTYLIST
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) EMPTYLIST é usada.
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
ms.openlocfilehash: 747b661d0dee4e9c27741e167c89f9ef7eefa470
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/01/2020
ms.locfileid: "3745312"
---
# <a name="emptylist-er-function"></a><span data-ttu-id="1084f-103">Função de ER EMPTYLIST</span><span class="sxs-lookup"><span data-stu-id="1084f-103">EMPTYLIST ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="1084f-104">A função `EMPTYLIST` retorna um valor de *Lista de registros* vazio usando a lista especificada como uma fonte para a estrutura da lista.</span><span class="sxs-lookup"><span data-stu-id="1084f-104">The `EMPTYLIST` function returns an empty *Record list* value by using the specified list as a source for the list structure.</span></span>

## <a name="syntax"></a><span data-ttu-id="1084f-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="1084f-105">Syntax</span></span>

```vb
EMPTYLIST (list)
```

## <a name="arguments"></a><span data-ttu-id="1084f-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="1084f-106">Arguments</span></span>

<span data-ttu-id="1084f-107">`list`: *Lista de registros*</span><span class="sxs-lookup"><span data-stu-id="1084f-107">`list`: *Record list*</span></span>

<span data-ttu-id="1084f-108">O caminho válido de uma fonte de dados do tipo *Lista de registros*.</span><span class="sxs-lookup"><span data-stu-id="1084f-108">The valid path of a data source of the *Record list* data type.</span></span>

## <a name="return-values"></a><span data-ttu-id="1084f-109">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="1084f-109">Return values</span></span>

<span data-ttu-id="1084f-110">*Lista de registros*</span><span class="sxs-lookup"><span data-stu-id="1084f-110">*Record list*</span></span>

<span data-ttu-id="1084f-111">A lista de registros resultante.</span><span class="sxs-lookup"><span data-stu-id="1084f-111">The resulting list of records.</span></span>

## <a name="example"></a><span data-ttu-id="1084f-112">Exemplo</span><span class="sxs-lookup"><span data-stu-id="1084f-112">Example</span></span>

<span data-ttu-id="1084f-113">`EMPTYLIST (SPLIT ("abc", 1))` retorna uma nova lista vazia que tem a mesma estrutura da lista retornada pela função `SPLIT` usada.</span><span class="sxs-lookup"><span data-stu-id="1084f-113">`EMPTYLIST (SPLIT ("abc", 1))` returns a new empty list that has the same structure as the list that is returned by the `SPLIT` function that is used.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="1084f-114">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="1084f-114">Additional resources</span></span>

[<span data-ttu-id="1084f-115">Funções de listagem</span><span class="sxs-lookup"><span data-stu-id="1084f-115">List functions</span></span>](er-functions-category-list.md)
