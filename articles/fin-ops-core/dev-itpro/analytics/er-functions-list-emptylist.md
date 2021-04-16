---
title: Função de ER EMPTYLIST
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) EMPTYLIST é usada.
author: NickSelin
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
ms.openlocfilehash: 1e2a92d9951c3ad27503cf82f1b45026f16c3835
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5746666"
---
# <a name="emptylist-er-function"></a><span data-ttu-id="63a44-103">Função de ER EMPTYLIST</span><span class="sxs-lookup"><span data-stu-id="63a44-103">EMPTYLIST ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="63a44-104">A função `EMPTYLIST` retorna um valor de *Lista de registros* vazio usando a lista especificada como uma fonte para a estrutura da lista.</span><span class="sxs-lookup"><span data-stu-id="63a44-104">The `EMPTYLIST` function returns an empty *Record list* value by using the specified list as a source for the list structure.</span></span>

## <a name="syntax"></a><span data-ttu-id="63a44-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="63a44-105">Syntax</span></span>

```vb
EMPTYLIST (list)
```

## <a name="arguments"></a><span data-ttu-id="63a44-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="63a44-106">Arguments</span></span>

<span data-ttu-id="63a44-107">`list`: *Lista de registros*</span><span class="sxs-lookup"><span data-stu-id="63a44-107">`list`: *Record list*</span></span>

<span data-ttu-id="63a44-108">O caminho válido de uma fonte de dados do tipo *Lista de registros*.</span><span class="sxs-lookup"><span data-stu-id="63a44-108">The valid path of a data source of the *Record list* data type.</span></span>

## <a name="return-values"></a><span data-ttu-id="63a44-109">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="63a44-109">Return values</span></span>

<span data-ttu-id="63a44-110">*Lista de registros*</span><span class="sxs-lookup"><span data-stu-id="63a44-110">*Record list*</span></span>

<span data-ttu-id="63a44-111">A lista de registros resultante.</span><span class="sxs-lookup"><span data-stu-id="63a44-111">The resulting list of records.</span></span>

## <a name="example"></a><span data-ttu-id="63a44-112">Exemplo</span><span class="sxs-lookup"><span data-stu-id="63a44-112">Example</span></span>

<span data-ttu-id="63a44-113">`EMPTYLIST (SPLIT ("abc", 1))` retorna uma nova lista vazia que tem a mesma estrutura da lista retornada pela função `SPLIT` usada.</span><span class="sxs-lookup"><span data-stu-id="63a44-113">`EMPTYLIST (SPLIT ("abc", 1))` returns a new empty list that has the same structure as the list that is returned by the `SPLIT` function that is used.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="63a44-114">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="63a44-114">Additional resources</span></span>

[<span data-ttu-id="63a44-115">Funções de listagem</span><span class="sxs-lookup"><span data-stu-id="63a44-115">List functions</span></span>](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]