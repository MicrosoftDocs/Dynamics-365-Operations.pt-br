---
title: Função de ER COUNT
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) COUNT é usada.
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
ms.openlocfilehash: 72d2ea1b26c295c97575a3c7a479ee4e06762424
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/12/2020
ms.locfileid: "3042196"
---
# <span data-ttu-id="d4fd3-103"><a name="COUNT">Função de ER COUNT</a></span><span class="sxs-lookup"><span data-stu-id="d4fd3-103"><a name="COUNT">COUNT ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="d4fd3-104">A função `COUNT` retorna um valor *Inteiro* que representa o número de registros na lista especificada, se a lista não estiver vazia.</span><span class="sxs-lookup"><span data-stu-id="d4fd3-104">The `COUNT` function returns an *Integer* value that represents the number of records in the specified list, if the list isn't empty.</span></span> <span data-ttu-id="d4fd3-105">Se a lista estiver vazia, essa função retornará **0** (zero).</span><span class="sxs-lookup"><span data-stu-id="d4fd3-105">If the list is empty, this function returns **0** (zero).</span></span>

## <a name="syntax"></a><span data-ttu-id="d4fd3-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="d4fd3-106">Syntax</span></span>

```vb
COUNT (list)
```

## <a name="arguments"></a><span data-ttu-id="d4fd3-107">Argumentos</span><span class="sxs-lookup"><span data-stu-id="d4fd3-107">Arguments</span></span>

<span data-ttu-id="d4fd3-108">`list`: *Lista de registros*</span><span class="sxs-lookup"><span data-stu-id="d4fd3-108">`list`: *Record list*</span></span>

<span data-ttu-id="d4fd3-109">O caminho válido de uma fonte de dados do tipo *Lista de registros*.</span><span class="sxs-lookup"><span data-stu-id="d4fd3-109">The valid path of a data source of the *Record list* data type.</span></span>

## <a name="return-values"></a><span data-ttu-id="d4fd3-110">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="d4fd3-110">Return values</span></span>

<span data-ttu-id="d4fd3-111">*Inteiro*</span><span class="sxs-lookup"><span data-stu-id="d4fd3-111">*Integer*</span></span>

<span data-ttu-id="d4fd3-112">O valor numérico resultante.</span><span class="sxs-lookup"><span data-stu-id="d4fd3-112">The resulting numeric value.</span></span>

## <a name="example"></a><span data-ttu-id="d4fd3-113">Exemplo</span><span class="sxs-lookup"><span data-stu-id="d4fd3-113">Example</span></span>

<span data-ttu-id="d4fd3-114">`COUNT (SPLIT("abcd" , 3))` retorna **2**, porque a função `SPLIT` usada neste exemplo cria uma lista que consiste em dois registros.</span><span class="sxs-lookup"><span data-stu-id="d4fd3-114">`COUNT (SPLIT("abcd" , 3))` returns **2**, because the `SPLIT` function that is used in this example creates a list that consists of two records.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="d4fd3-115">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="d4fd3-115">Additional resources</span></span>

[<span data-ttu-id="d4fd3-116">Funções de listagem</span><span class="sxs-lookup"><span data-stu-id="d4fd3-116">List functions</span></span>](er-functions-category-list.md)
