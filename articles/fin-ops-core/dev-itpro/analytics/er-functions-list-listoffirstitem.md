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
ms.search.scope: Core, Operations
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 069ec0c6d5578ca6ab68814adf325bd79e73b9e8
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/01/2020
ms.locfileid: "3745048"
---
# <a name="listoffirstitem-er-function"></a><span data-ttu-id="8ce10-103">Função de ER LISTOFFIRSTITEM</span><span class="sxs-lookup"><span data-stu-id="8ce10-103">LISTOFFIRSTITEM ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="8ce10-104">A função `LISTOFFIRSTITEM` retorna um valor de *Lista de registros* que consiste somente no primeiro registro da lista especificada.</span><span class="sxs-lookup"><span data-stu-id="8ce10-104">The `LISTOFFIRSTITEM` function returns a *Record list* value that consists of only the first record of the specified list.</span></span>

## <a name="syntax"></a><span data-ttu-id="8ce10-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="8ce10-105">Syntax</span></span>

```vb
LISTOFFIRSTITEM (list)
```

## <a name="arguments"></a><span data-ttu-id="8ce10-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="8ce10-106">Arguments</span></span>

<span data-ttu-id="8ce10-107">`list`: *Lista de registros*</span><span class="sxs-lookup"><span data-stu-id="8ce10-107">`list`: *Record list*</span></span>

<span data-ttu-id="8ce10-108">O caminho válido de uma fonte de dados do tipo *Lista de registros*.</span><span class="sxs-lookup"><span data-stu-id="8ce10-108">The valid path of a data source of the *Record list* data type.</span></span>

## <a name="return-values"></a><span data-ttu-id="8ce10-109">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="8ce10-109">Return values</span></span>

<span data-ttu-id="8ce10-110">*Lista de registros*</span><span class="sxs-lookup"><span data-stu-id="8ce10-110">*Record list*</span></span>

<span data-ttu-id="8ce10-111">A lista de registros resultante.</span><span class="sxs-lookup"><span data-stu-id="8ce10-111">The resulting list of records.</span></span>

## <a name="example"></a><span data-ttu-id="8ce10-112">Exemplo</span><span class="sxs-lookup"><span data-stu-id="8ce10-112">Example</span></span>

<span data-ttu-id="8ce10-113">A expressão `FIRST( LISTOFFIRSTITEM ( SPLIT ("ABC",1))).Value` retorna o valor de texto **"A"**.</span><span class="sxs-lookup"><span data-stu-id="8ce10-113">The expression `FIRST( LISTOFFIRSTITEM ( SPLIT ("ABC",1))).Value` returns the text value **"A"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="8ce10-114">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="8ce10-114">Additional resources</span></span>

[<span data-ttu-id="8ce10-115">Funções de listagem</span><span class="sxs-lookup"><span data-stu-id="8ce10-115">List functions</span></span>](er-functions-category-list.md)
