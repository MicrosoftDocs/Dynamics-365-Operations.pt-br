---
title: Função de ER COUNT
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) COUNT é usada.
author: NickSelin
manager: kfend
ms.date: 12/12/2019
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: e36347d928148e85bc9295d529cbf2801946433a
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/09/2021
ms.locfileid: "5567883"
---
# <a name="count-er-function"></a><span data-ttu-id="05a69-103">Função de ER COUNT</span><span class="sxs-lookup"><span data-stu-id="05a69-103">COUNT ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="05a69-104">A função `COUNT` retorna um valor *Inteiro* que representa o número de registros na lista especificada, se a lista não estiver vazia.</span><span class="sxs-lookup"><span data-stu-id="05a69-104">The `COUNT` function returns an *Integer* value that represents the number of records in the specified list, if the list isn't empty.</span></span> <span data-ttu-id="05a69-105">Se a lista estiver vazia, essa função retornará **0** (zero).</span><span class="sxs-lookup"><span data-stu-id="05a69-105">If the list is empty, this function returns **0** (zero).</span></span>

## <a name="syntax"></a><span data-ttu-id="05a69-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="05a69-106">Syntax</span></span>

```vb
COUNT (list)
```

## <a name="arguments"></a><span data-ttu-id="05a69-107">Argumentos</span><span class="sxs-lookup"><span data-stu-id="05a69-107">Arguments</span></span>

<span data-ttu-id="05a69-108">`list`: *Lista de registros*</span><span class="sxs-lookup"><span data-stu-id="05a69-108">`list`: *Record list*</span></span>

<span data-ttu-id="05a69-109">O caminho válido de uma fonte de dados do tipo *Lista de registros*.</span><span class="sxs-lookup"><span data-stu-id="05a69-109">The valid path of a data source of the *Record list* data type.</span></span>

## <a name="return-values"></a><span data-ttu-id="05a69-110">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="05a69-110">Return values</span></span>

<span data-ttu-id="05a69-111">*Inteiro*</span><span class="sxs-lookup"><span data-stu-id="05a69-111">*Integer*</span></span>

<span data-ttu-id="05a69-112">O valor numérico resultante.</span><span class="sxs-lookup"><span data-stu-id="05a69-112">The resulting numeric value.</span></span>

## <a name="example"></a><span data-ttu-id="05a69-113">Exemplo</span><span class="sxs-lookup"><span data-stu-id="05a69-113">Example</span></span>

<span data-ttu-id="05a69-114">`COUNT (SPLIT("abcd" , 3))` retorna **2**, porque a função `SPLIT` usada neste exemplo cria uma lista que consiste em dois registros.</span><span class="sxs-lookup"><span data-stu-id="05a69-114">`COUNT (SPLIT("abcd" , 3))` returns **2**, because the `SPLIT` function that is used in this example creates a list that consists of two records.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="05a69-115">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="05a69-115">Additional resources</span></span>

[<span data-ttu-id="05a69-116">Funções de listagem</span><span class="sxs-lookup"><span data-stu-id="05a69-116">List functions</span></span>](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]