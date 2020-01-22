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
ms.openlocfilehash: 2d29b82a8c3b108f7651e6d593cb17e7ec8ca872
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/20/2019
ms.locfileid: "2916237"
---
# <span data-ttu-id="3af05-103"><a name="COUNT">Função de ER COUNT</a></span><span class="sxs-lookup"><span data-stu-id="3af05-103"><a name="COUNT">COUNT ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="3af05-104">A função `COUNT` retorna um valor *Inteiro* que representa o número de registros na lista especificada, se a lista não estiver vazia.</span><span class="sxs-lookup"><span data-stu-id="3af05-104">The `COUNT` function returns an *Integer* value that represents the number of records in the specified list, if the list isn't empty.</span></span> <span data-ttu-id="3af05-105">Se a lista estiver vazia, essa função retornará **0** (zero).</span><span class="sxs-lookup"><span data-stu-id="3af05-105">If the list is empty, this function returns **0** (zero).</span></span>

## <a name="syntax"></a><span data-ttu-id="3af05-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="3af05-106">Syntax</span></span>

```
COUNT (list)
```

## <a name="arguments"></a><span data-ttu-id="3af05-107">Argumentos</span><span class="sxs-lookup"><span data-stu-id="3af05-107">Arguments</span></span>

<span data-ttu-id="3af05-108">`list`: *Lista de registros*</span><span class="sxs-lookup"><span data-stu-id="3af05-108">`list`: *Record list*</span></span>

<span data-ttu-id="3af05-109">O caminho válido de uma fonte de dados do tipo *Lista de registros*.</span><span class="sxs-lookup"><span data-stu-id="3af05-109">The valid path of a data source of the *Record list* data type.</span></span>

## <a name="return-values"></a><span data-ttu-id="3af05-110">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="3af05-110">Return values</span></span>

<span data-ttu-id="3af05-111">*Inteiro*</span><span class="sxs-lookup"><span data-stu-id="3af05-111">*Integer*</span></span>

<span data-ttu-id="3af05-112">O valor numérico resultante.</span><span class="sxs-lookup"><span data-stu-id="3af05-112">The resulting numeric value.</span></span>

## <a name="example"></a><span data-ttu-id="3af05-113">Exemplo</span><span class="sxs-lookup"><span data-stu-id="3af05-113">Example</span></span>

<span data-ttu-id="3af05-114">`COUNT (SPLIT("abcd" , 3))` retorna **2**, porque a função `SPLIT` usada neste exemplo cria uma lista que consiste em dois registros.</span><span class="sxs-lookup"><span data-stu-id="3af05-114">`COUNT (SPLIT("abcd" , 3))` returns **2**, because the `SPLIT` function that is used in this example creates a list that consists of two records.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="3af05-115">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="3af05-115">Additional resources</span></span>

[<span data-ttu-id="3af05-116">Funções de listagem</span><span class="sxs-lookup"><span data-stu-id="3af05-116">List functions</span></span>](er-functions-category-list.md)
